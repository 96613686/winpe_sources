# DXGDEVICE::OpenResourceObject(_D3DKMT_CREATEALLOCATION *,_D3DDDI_ALLOCATIONINFO2 *,uchar,_EPROCESS *,_DXGSHAREDALLOCOBJECT *,DXGRESOURCEREFERENCE *,uchar *,_D3DKM_CREATESTANDARDALLOCATION const *,DXGAUTOMUTEX *,DXGAUTOPUSHLOCK *)

- ea: `0x14036e5d4`
- end: `0x14036f96f`
- name: `?OpenResourceObject@DXGDEVICE@@QEAAJPEAU_D3DKMT_CREATEALLOCATION@@PEAU_D3DDDI_ALLOCATIONINFO2@@EPEAU_EPROCESS@@PEAU_DXGSHAREDALLOCOBJECT@@PEAVDXGRESOURCEREFERENCE@@PEAEPEBU_D3DKM_CREATESTANDARDALLOCATION@@PEAVDXGAUTOMUTEX@@PEAVDXGAUTOPUSHLOCK@@@Z`
- size: `5019`
- prototype: `__int64 __usercall@<rax>(DXGDEVICE *__hidden this@<rcx>, struct _D3DKMT_CREATEALLOCATION *@<rdx>, struct _D3DDDI_ALLOCATIONINFO2 *@<r8>, unsigned __int8@<r9b>, struct _EPROCESS *, struct _DXGSHAREDALLOCOBJECT *, struct DXGRESOURCEREFERENCE *, unsigned __int8 *, const struct _D3DKM_CREATESTANDARDALLOCATION *, struct DXGAUTOMUTEX *, struct DXGAUTOPUSHLOCK *)`
- caller_count: `1`
- callee_count: `29`
- tags: ``

## callers

- `0x140377040`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140012380`
- `0x1400144ec`
- `0x1400160e4`
- `0x1400161c8`
- `0x14001b6ac`
- `0x14001b890`
- `0x14001bd70`
- `0x14001d070`
- `0x14002d9f0`
- `0x14002e110`
- `0x14002fdc0`
- `0x14003bab8`
- `0x14003c104`
- `0x140041260`
- `0x1400425f4`
- `0x140055d4c`
- `0x140061134`
- `0x14006db20`
- `0x140323854`
- `0x14036e5d4`
- `0x14036f9f0`
- `0x14036fd90`
- `0x14036fe0c`
- `0x14038dd14`
- `0x1403aac20`
- `0x1403ad354`
- `0x1403dca68`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14036ed96`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14036ee7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14036ed96`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14036ee7b`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14036e79f`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14036f632`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14036e79f`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14036f632`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14036ed8a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14036ee6f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14036ed8a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14036ee6f`
- `ntoskrnl!ObfDereferenceObject` at `0x14036ec96`
- `ntoskrnl!ObfDereferenceObject` at `0x14036ec96`
- `ntoskrnl!ObfReferenceObject` at `0x14036ec64`
- `ntoskrnl!ObfReferenceObject` at `0x14036ec64`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e664`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e91c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e664`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e91c`
- `ntoskrnl!PsIsProtectedProcess` at `0x14036e9fc`
- `ntoskrnl!PsIsProtectedProcess` at `0x14036f67c`
- `ntoskrnl!PsIsProtectedProcess` at `0x14036e9fc`
- `ntoskrnl!PsIsProtectedProcess` at `0x14036f67c`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x14036f694`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x14036f871`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x14036f694`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x14036f871`
- `watchdog!WdLogSingleEntry4` at `0x14036e82f`
- `watchdog!WdLogSingleEntry4` at `0x14036eff5`
- `watchdog!WdLogSingleEntry4` at `0x14036f0c9`
- `watchdog!WdLogSingleEntry4` at `0x14036f192`
- `watchdog!WdLogSingleEntry4` at `0x14036f28c`
- `watchdog!WdLogSingleEntry4` at `0x14036f5d8`
- `watchdog!WdLogSingleEntry4` at `0x14036f60d`
- `watchdog!WdLogSingleEntry4` at `0x14036e82f`
- `watchdog!WdLogSingleEntry4` at `0x14036eff5`
- `watchdog!WdLogSingleEntry4` at `0x14036f0c9`
- `watchdog!WdLogSingleEntry4` at `0x14036f192`
- `watchdog!WdLogSingleEntry4` at `0x14036f28c`
- `watchdog!WdLogSingleEntry4` at `0x14036f5d8`
- `watchdog!WdLogSingleEntry4` at `0x14036f60d`
- `watchdog!WdLogSingleEntry2` at `0x14036e6b7`
- `watchdog!WdLogSingleEntry2` at `0x14036e88b`
- `watchdog!WdLogSingleEntry2` at `0x14036f10d`
- `watchdog!WdLogSingleEntry2` at `0x14036f434`
- `watchdog!WdLogSingleEntry2` at `0x14036f4b6`
- `watchdog!WdLogSingleEntry2` at `0x14036f4e0`
- `watchdog!WdLogSingleEntry2` at `0x14036f529`
- `watchdog!WdLogSingleEntry2` at `0x14036f8ca`
- `watchdog!WdLogSingleEntry2` at `0x14036e6b7`
- `watchdog!WdLogSingleEntry2` at `0x14036e88b`
- `watchdog!WdLogSingleEntry2` at `0x14036f10d`
- `watchdog!WdLogSingleEntry2` at `0x14036f434`
- `watchdog!WdLogSingleEntry2` at `0x14036f4b6`
- `watchdog!WdLogSingleEntry2` at `0x14036f4e0`
- `watchdog!WdLogSingleEntry2` at `0x14036f529`
- `watchdog!WdLogSingleEntry2` at `0x14036f8ca`
- `watchdog!WdLogSingleEntry3` at `0x14036eaef`
- `watchdog!WdLogSingleEntry3` at `0x14036ebdf`
- `watchdog!WdLogSingleEntry3` at `0x14036eec4`
- `watchdog!WdLogSingleEntry3` at `0x14036f151`
- `watchdog!WdLogSingleEntry3` at `0x14036f24e`
- `watchdog!WdLogSingleEntry3` at `0x14036f2ee`
- `watchdog!WdLogSingleEntry3` at `0x14036f31c`
- `watchdog!WdLogSingleEntry3` at `0x14036f550`
- `watchdog!WdLogSingleEntry3` at `0x14036f5aa`
- `watchdog!WdLogSingleEntry3` at `0x14036f6b6`
- `watchdog!WdLogSingleEntry3` at `0x14036f783`
- `watchdog!WdLogSingleEntry3` at `0x14036f84b`
- `watchdog!WdLogSingleEntry3` at `0x14036eaef`
- `watchdog!WdLogSingleEntry3` at `0x14036ebdf`
- `watchdog!WdLogSingleEntry3` at `0x14036eec4`
- `watchdog!WdLogSingleEntry3` at `0x14036f151`
- `watchdog!WdLogSingleEntry3` at `0x14036f24e`
- `watchdog!WdLogSingleEntry3` at `0x14036f2ee`
- `watchdog!WdLogSingleEntry3` at `0x14036f31c`
- `watchdog!WdLogSingleEntry3` at `0x14036f550`
- `watchdog!WdLogSingleEntry3` at `0x14036f5aa`
- `watchdog!WdLogSingleEntry3` at `0x14036f6b6`
- `watchdog!WdLogSingleEntry3` at `0x14036f783`
- `watchdog!WdLogSingleEntry3` at `0x14036f84b`
- `watchdog!WdLogSingleEntry0` at `0x14036eb5d`
- `watchdog!WdLogSingleEntry0` at `0x14036ed2c`
- `watchdog!WdLogSingleEntry0` at `0x14036ee0b`
- `watchdog!WdLogSingleEntry0` at `0x14036f04d`
- `watchdog!WdLogSingleEntry0` at `0x14036eb5d`
- `watchdog!WdLogSingleEntry0` at `0x14036ed2c`
- `watchdog!WdLogSingleEntry0` at `0x14036ee0b`
- `watchdog!WdLogSingleEntry0` at `0x14036f04d`
- `watchdog!WdLogSingleEntry5` at `0x14036f215`
- `watchdog!WdLogSingleEntry5` at `0x14036f659`
- `watchdog!WdLogSingleEntry5` at `0x14036f6e6`
- `watchdog!WdLogSingleEntry5` at `0x14036f215`
- `watchdog!WdLogSingleEntry5` at `0x14036f659`
- `watchdog!WdLogSingleEntry5` at `0x14036f6e6`
- `watchdog!WdLogSingleEntry1` at `0x14036ecaa`
- `watchdog!WdLogSingleEntry1` at `0x14036ecaa`

## string_xrefs

- `0x14036e89c`: `Device 0x%I64x: Out of memory allocating DXGSHAREDRESOURCEACCESS class, returning 0x%I64x`
- `0x14036f8e7`: `Device 0x%I64x: Attempting to create shared displayable resource without expected flags, returning 0x%I64x`
- `0x14036ecbf`: `Out of memory allocating DXGPROCESSSHAREDACCESS class, returning 0x%I64x`

## pseudocode

```c

```
