.. _SOF_ABI_changes:

SOF ABI Change Process
######################

SOF ABI definitions
*******************

The SOF ABI consists of public structs used in host-FW communication
defined in:

- src/include/kernel/
- src/include/ipc/
- src/include/user/

SOF ABI versioning is defined in firmware source code documentation `FW Source kernel/abi.h`_

.. _FW Source kernel/abi.h: https://github.com/thesofproject/sof/blob/master/src/include/kernel/abi.h#L8

Change Process
**************

When a firmware change requires extending or modifying the public
SOF ABI, the developer must go through the ABI change process as defined
in this section. The developer must drive this process, contact the
stakeholders, request reviews (and re-reviews when needed) and coordinate
with the driver maintainers.

The main steps of the process are depicted in the following
state diagram:

.. _ABI Change Tracker: https://github.com/orgs/thesofproject/projects/2

The pull requests are classified in GitHub using the following
official `ABI Change Tracker`_

.. uml:: images/abiprocess.pu
   :caption: ABI process state diagram

When the ABI change is not backwards-compatible, Pull Requests on the
kernel side shall include code that deals with older firmware and
topology files. See :ref:`development_tree` for kernel side
documentation.

ABI change approvers
********************

TSC
---

Approval from an SOF :ref:`tsc` member is needed for all ABI changes.

SOF driver
----------

Linux driver team approval for changes can be granted by any member of the
SOF Linux driver maintainer team. The current list of members is maintained
in :ref:`sof_drv_maintainer_list`.
