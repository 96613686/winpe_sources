# DXGDEVICE::OpenResourceObject(_D3DKMT_CREATEALLOCATION *,_D3DDDI_ALLOCATIONINFO2 *,uchar,_EPROCESS *,_DXGSHAREDALLOCOBJECT *,DXGRESOURCEREFERENCE *,uchar *,_D3DKM_CREATESTANDARDALLOCATION const *,DXGAUTOMUTEX *,DXGAUTOPUSHLOCK *)

- ea: `0x14036e614`
- end: `0x14036f9af`
- name: `?OpenResourceObject@DXGDEVICE@@QEAAJPEAU_D3DKMT_CREATEALLOCATION@@PEAU_D3DDDI_ALLOCATIONINFO2@@EPEAU_EPROCESS@@PEAU_DXGSHAREDALLOCOBJECT@@PEAVDXGRESOURCEREFERENCE@@PEAEPEBU_D3DKM_CREATESTANDARDALLOCATION@@PEAVDXGAUTOMUTEX@@PEAVDXGAUTOPUSHLOCK@@@Z`
- size: `5019`
- prototype: `__int64 __usercall@<rax>(DXGDEVICE *__hidden this@<rcx>, struct _D3DKMT_CREATEALLOCATION *@<rdx>, struct _D3DDDI_ALLOCATIONINFO2 *@<r8>, unsigned __int8@<r9b>, struct _EPROCESS *, struct _DXGSHAREDALLOCOBJECT *, struct DXGRESOURCEREFERENCE *, unsigned __int8 *, const struct _D3DKM_CREATESTANDARDALLOCATION *, struct DXGAUTOMUTEX *, struct DXGAUTOPUSHLOCK *)`
- caller_count: `1`
- callee_count: `29`
- tags: ``

## callers

- `0x140377080`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012540`
- `0x1400146ac`
- `0x1400162a4`
- `0x140016388`
- `0x14001b7dc`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14001d1a0`
- `0x14002dbc0`
- `0x14002e2e0`
- `0x14002ff90`
- `0x14003bd18`
- `0x14003c364`
- `0x1400414c0`
- `0x140042854`
- `0x140055fbc`
- `0x1400614e4`
- `0x14006e080`
- `0x14032a5c4`
- `0x14036e614`
- `0x14036fa30`
- `0x14036fdd0`
- `0x14036fe4c`
- `0x14038cde4`
- `0x1403aba00`
- `0x1403ae134`
- `0x1403dce88`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14036edd6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14036eebb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14036edd6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14036eebb`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14036e7df`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14036f672`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14036e7df`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14036f672`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14036edca`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14036eeaf`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14036edca`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14036eeaf`
- `ntoskrnl!ObfDereferenceObject` at `0x14036ecd6`
- `ntoskrnl!ObfDereferenceObject` at `0x14036ecd6`
- `ntoskrnl!ObfReferenceObject` at `0x14036eca4`
- `ntoskrnl!ObfReferenceObject` at `0x14036eca4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e6a4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e95c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e6a4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14036e95c`
- `ntoskrnl!PsIsProtectedProcess` at `0x14036ea3c`
- `ntoskrnl!PsIsProtectedProcess` at `0x14036f6bc`
- `ntoskrnl!PsIsProtectedProcess` at `0x14036ea3c`
- `ntoskrnl!PsIsProtectedProcess` at `0x14036f6bc`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x14036f6d4`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x14036f8b1`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x14036f6d4`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x14036f8b1`
- `watchdog!WdLogSingleEntry4` at `0x14036e86f`
- `watchdog!WdLogSingleEntry4` at `0x14036f035`
- `watchdog!WdLogSingleEntry4` at `0x14036f109`
- `watchdog!WdLogSingleEntry4` at `0x14036f1d2`
- `watchdog!WdLogSingleEntry4` at `0x14036f2cc`
- `watchdog!WdLogSingleEntry4` at `0x14036f618`
- `watchdog!WdLogSingleEntry4` at `0x14036f64d`
- `watchdog!WdLogSingleEntry4` at `0x14036e86f`
- `watchdog!WdLogSingleEntry4` at `0x14036f035`
- `watchdog!WdLogSingleEntry4` at `0x14036f109`
- `watchdog!WdLogSingleEntry4` at `0x14036f1d2`
- `watchdog!WdLogSingleEntry4` at `0x14036f2cc`
- `watchdog!WdLogSingleEntry4` at `0x14036f618`
- `watchdog!WdLogSingleEntry4` at `0x14036f64d`
- `watchdog!WdLogSingleEntry2` at `0x14036e6f7`
- `watchdog!WdLogSingleEntry2` at `0x14036e8cb`
- `watchdog!WdLogSingleEntry2` at `0x14036f14d`
- `watchdog!WdLogSingleEntry2` at `0x14036f474`
- `watchdog!WdLogSingleEntry2` at `0x14036f4f6`
- `watchdog!WdLogSingleEntry2` at `0x14036f520`
- `watchdog!WdLogSingleEntry2` at `0x14036f569`
- `watchdog!WdLogSingleEntry2` at `0x14036f90a`
- `watchdog!WdLogSingleEntry2` at `0x14036e6f7`
- `watchdog!WdLogSingleEntry2` at `0x14036e8cb`
- `watchdog!WdLogSingleEntry2` at `0x14036f14d`
- `watchdog!WdLogSingleEntry2` at `0x14036f474`
- `watchdog!WdLogSingleEntry2` at `0x14036f4f6`
- `watchdog!WdLogSingleEntry2` at `0x14036f520`
- `watchdog!WdLogSingleEntry2` at `0x14036f569`
- `watchdog!WdLogSingleEntry2` at `0x14036f90a`
- `watchdog!WdLogSingleEntry3` at `0x14036eb2f`
- `watchdog!WdLogSingleEntry3` at `0x14036ec1f`
- `watchdog!WdLogSingleEntry3` at `0x14036ef04`
- `watchdog!WdLogSingleEntry3` at `0x14036f191`
- `watchdog!WdLogSingleEntry3` at `0x14036f28e`
- `watchdog!WdLogSingleEntry3` at `0x14036f32e`
- `watchdog!WdLogSingleEntry3` at `0x14036f35c`
- `watchdog!WdLogSingleEntry3` at `0x14036f590`
- `watchdog!WdLogSingleEntry3` at `0x14036f5ea`
- `watchdog!WdLogSingleEntry3` at `0x14036f6f6`
- `watchdog!WdLogSingleEntry3` at `0x14036f7c3`
- `watchdog!WdLogSingleEntry3` at `0x14036f88b`
- `watchdog!WdLogSingleEntry3` at `0x14036eb2f`
- `watchdog!WdLogSingleEntry3` at `0x14036ec1f`
- `watchdog!WdLogSingleEntry3` at `0x14036ef04`
- `watchdog!WdLogSingleEntry3` at `0x14036f191`
- `watchdog!WdLogSingleEntry3` at `0x14036f28e`
- `watchdog!WdLogSingleEntry3` at `0x14036f32e`
- `watchdog!WdLogSingleEntry3` at `0x14036f35c`
- `watchdog!WdLogSingleEntry3` at `0x14036f590`
- `watchdog!WdLogSingleEntry3` at `0x14036f5ea`
- `watchdog!WdLogSingleEntry3` at `0x14036f6f6`
- `watchdog!WdLogSingleEntry3` at `0x14036f7c3`
- `watchdog!WdLogSingleEntry3` at `0x14036f88b`
- `watchdog!WdLogSingleEntry0` at `0x14036eb9d`
- `watchdog!WdLogSingleEntry0` at `0x14036ed6c`
- `watchdog!WdLogSingleEntry0` at `0x14036ee4b`
- `watchdog!WdLogSingleEntry0` at `0x14036f08d`
- `watchdog!WdLogSingleEntry0` at `0x14036eb9d`
- `watchdog!WdLogSingleEntry0` at `0x14036ed6c`
- `watchdog!WdLogSingleEntry0` at `0x14036ee4b`
- `watchdog!WdLogSingleEntry0` at `0x14036f08d`
- `watchdog!WdLogSingleEntry5` at `0x14036f255`
- `watchdog!WdLogSingleEntry5` at `0x14036f699`
- `watchdog!WdLogSingleEntry5` at `0x14036f726`
- `watchdog!WdLogSingleEntry5` at `0x14036f255`
- `watchdog!WdLogSingleEntry5` at `0x14036f699`
- `watchdog!WdLogSingleEntry5` at `0x14036f726`
- `watchdog!WdLogSingleEntry1` at `0x14036ecea`
- `watchdog!WdLogSingleEntry1` at `0x14036ecea`

## string_xrefs

- `0x14036e8dc`: `Device 0x%I64x: Out of memory allocating DXGSHAREDRESOURCEACCESS class, returning 0x%I64x`
- `0x14036f927`: `Device 0x%I64x: Attempting to create shared displayable resource without expected flags, returning 0x%I64x`
- `0x14036ecff`: `Out of memory allocating DXGPROCESSSHAREDACCESS class, returning 0x%I64x`

## pseudocode

```c

```
