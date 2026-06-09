# DxgkDrtTestEscape(DXGADAPTER *,_D3DKMT_DRT_ESCAPE_HEAD *,COREADAPTERACCESS *)

- ea: `0x140231100`
- end: `0x140233c65`
- name: `?DxgkDrtTestEscape@@YAJPEAVDXGADAPTER@@PEAU_D3DKMT_DRT_ESCAPE_HEAD@@PEAVCOREADAPTERACCESS@@@Z`
- size: `11109`
- prototype: `__int64 __fastcall(struct DXGADAPTER *, struct _D3DKMT_DRT_ESCAPE_HEAD *, struct COREADAPTERACCESS *this)`
- caller_count: `1`
- callee_count: `98`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14035a080`

## callees

- `0x140012380`
- `0x140014a9c`
- `0x1400158b0`
- `0x140015910`
- `0x140015970`
- `0x140015d70`
- `0x140016330`
- `0x14001667c`
- `0x140017fb8`
- `0x1400180f0`
- `0x14001a2ec`
- `0x14001ab20`
- `0x14001b890`
- `0x14001bd70`
- `0x14001c320`
- `0x14001ccf0`
- `0x14001cec0`
- `0x14001e15c`
- `0x14001f088`
- `0x14001f120`
- `0x140021c80`
- `0x140021fe0`
- `0x14002dc20`
- `0x14002fdc0`
- `0x140030820`
- `0x140035dc0`
- `0x140037a84`
- `0x14003d0dc`
- `0x14003fb68`
- `0x140041b54`
- `0x140042498`
- `0x1400496ec`
- `0x14004d73c`
- `0x140050284`
- `0x140052380`
- `0x140054bdc`
- `0x140057858`
- `0x14005813c`
- `0x14005a924`
- `0x14006291c`
- `0x14006d9a0`
- `0x14006f9f8`
- `0x140071d04`
- `0x140071d70`
- `0x140089094`
- `0x1400890ac`
- `0x1400890cc`
- `0x140089190`
- `0x1400a0100`
- `0x1400a01e0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402314c8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402314c8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402314b7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402314b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023158c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14023158c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140231580`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140231580`
- `ntoskrnl!ExFreePoolWithTag` at `0x140233368`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402334c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140233368`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402334c4`
- `ntoskrnl!KeInitializeEvent` at `0x1402325e5`
- `ntoskrnl!KeInitializeEvent` at `0x1402325e5`
- `ntoskrnl!ObfDereferenceObject` at `0x140232599`
- `ntoskrnl!ObfDereferenceObject` at `0x140232687`
- `ntoskrnl!ObfDereferenceObject` at `0x140232698`
- `ntoskrnl!ObfDereferenceObject` at `0x1402326fa`
- `ntoskrnl!ObfDereferenceObject` at `0x14023270b`
- `ntoskrnl!ObfDereferenceObject` at `0x140232599`
- `ntoskrnl!ObfDereferenceObject` at `0x140232687`
- `ntoskrnl!ObfDereferenceObject` at `0x140232698`
- `ntoskrnl!ObfDereferenceObject` at `0x1402326fa`
- `ntoskrnl!ObfDereferenceObject` at `0x14023270b`
- `ntoskrnl!ObfReferenceObject` at `0x140232519`
- `ntoskrnl!ObfReferenceObject` at `0x140232519`
- `ntoskrnl!IofCallDriver` at `0x1402326b1`
- `ntoskrnl!IofCallDriver` at `0x1402326b1`
- `ntoskrnl!ExEventObjectType` at `0x140231edd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140231ef0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140231ef0`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14023261f`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14023261f`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140232673`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140232673`
- `ntoskrnl!KeWaitForSingleObject` at `0x140231f7c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402326dd`
- `ntoskrnl!KeWaitForSingleObject` at `0x140231f7c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402326dd`
- `watchdog!WdLogSingleEntry3` at `0x140232288`
- `watchdog!WdLogSingleEntry3` at `0x140232288`
- `watchdog!WdLogSingleEntry0` at `0x140231205`
- `watchdog!WdLogSingleEntry0` at `0x140231268`
- `watchdog!WdLogSingleEntry0` at `0x1402312ba`
- `watchdog!WdLogSingleEntry0` at `0x140231353`
- `watchdog!WdLogSingleEntry0` at `0x140231389`
- `watchdog!WdLogSingleEntry0` at `0x1402313c2`
- `watchdog!WdLogSingleEntry0` at `0x140231439`
- `watchdog!WdLogSingleEntry0` at `0x140231464`
- `watchdog!WdLogSingleEntry0` at `0x1402315c5`
- `watchdog!WdLogSingleEntry0` at `0x140231702`
- `watchdog!WdLogSingleEntry0` at `0x140231746`
- `watchdog!WdLogSingleEntry0` at `0x140231897`
- `watchdog!WdLogSingleEntry0` at `0x1402318be`
- `watchdog!WdLogSingleEntry0` at `0x1402318f5`
- `watchdog!WdLogSingleEntry0` at `0x140231920`
- `watchdog!WdLogSingleEntry0` at `0x140231a97`
- `watchdog!WdLogSingleEntry0` at `0x140231e42`
- `watchdog!WdLogSingleEntry0` at `0x140231e6a`
- `watchdog!WdLogSingleEntry0` at `0x140231fa1`
- `watchdog!WdLogSingleEntry0` at `0x140231fcc`
- `watchdog!WdLogSingleEntry0` at `0x1402321ce`
- `watchdog!WdLogSingleEntry0` at `0x14023222f`
- `watchdog!WdLogSingleEntry0` at `0x14023230d`
- `watchdog!WdLogSingleEntry0` at `0x140232335`
- `watchdog!WdLogSingleEntry0` at `0x14023273f`
- `watchdog!WdLogSingleEntry0` at `0x140232822`
- `watchdog!WdLogSingleEntry0` at `0x1402328e0`
- `watchdog!WdLogSingleEntry0` at `0x140232910`
- `watchdog!WdLogSingleEntry0` at `0x140232993`
- `watchdog!WdLogSingleEntry0` at `0x140232a17`
- `watchdog!WdLogSingleEntry0` at `0x140232a3f`
- `watchdog!WdLogSingleEntry0` at `0x140232abe`
- `watchdog!WdLogSingleEntry0` at `0x140232b12`
- `watchdog!WdLogSingleEntry0` at `0x140232b5a`
- `watchdog!WdLogSingleEntry0` at `0x140232bb7`
- `watchdog!WdLogSingleEntry0` at `0x140232c13`
- `watchdog!WdLogSingleEntry0` at `0x140232c82`
- `watchdog!WdLogSingleEntry0` at `0x140232ccf`
- `watchdog!WdLogSingleEntry0` at `0x140232d2d`
- `watchdog!WdLogSingleEntry0` at `0x140232e39`
- `watchdog!WdLogSingleEntry0` at `0x140232e63`
- `watchdog!WdLogSingleEntry0` at `0x140232e93`
- `watchdog!WdLogSingleEntry0` at `0x140232f12`
- `watchdog!WdLogSingleEntry0` at `0x14023301d`
- `watchdog!WdLogSingleEntry0` at `0x1402330ba`
- `watchdog!WdLogSingleEntry0` at `0x140233176`
- `watchdog!WdLogSingleEntry0` at `0x140233336`
- `watchdog!WdLogSingleEntry0` at `0x14023352e`
- `watchdog!WdLogSingleEntry0` at `0x140233571`
- `watchdog!WdLogSingleEntry0` at `0x1402335a3`
- `watchdog!WdLogSingleEntry0` at `0x1402335e3`
- `watchdog!WdLogSingleEntry0` at `0x140233665`
- `watchdog!WdLogSingleEntry0` at `0x140233690`
- `watchdog!WdLogSingleEntry0` at `0x1402336c5`
- `watchdog!WdLogSingleEntry0` at `0x14023377f`
- `watchdog!WdLogSingleEntry0` at `0x1402337b6`
- `watchdog!WdLogSingleEntry0` at `0x14023383d`
- `watchdog!WdLogSingleEntry0` at `0x1402339ff`
- `watchdog!WdLogSingleEntry0` at `0x140233a87`
- `watchdog!WdLogSingleEntry0` at `0x140233b29`
- `watchdog!WdLogSingleEntry0` at `0x140233b81`
- `watchdog!WdLogSingleEntry0` at `0x140233bab`
- `watchdog!WdLogSingleEntry0` at `0x140233bdc`
- `watchdog!WdLogSingleEntry0` at `0x140233c06`
- `watchdog!WdLogSingleEntry0` at `0x140231205`
- `watchdog!WdLogSingleEntry0` at `0x140231268`
- `watchdog!WdLogSingleEntry0` at `0x1402312ba`
- `watchdog!WdLogSingleEntry0` at `0x140231353`
- `watchdog!WdLogSingleEntry0` at `0x140231389`
- `watchdog!WdLogSingleEntry0` at `0x1402313c2`
- `watchdog!WdLogSingleEntry0` at `0x140231439`
- `watchdog!WdLogSingleEntry0` at `0x140231464`
- `watchdog!WdLogSingleEntry0` at `0x1402315c5`
- `watchdog!WdLogSingleEntry0` at `0x140231702`
- `watchdog!WdLogSingleEntry0` at `0x140231746`
- `watchdog!WdLogSingleEntry0` at `0x140231897`
- `watchdog!WdLogSingleEntry0` at `0x1402318be`
- `watchdog!WdLogSingleEntry0` at `0x1402318f5`
- `watchdog!WdLogSingleEntry0` at `0x140231920`
- `watchdog!WdLogSingleEntry0` at `0x140231a97`
- `watchdog!WdLogSingleEntry0` at `0x140231e42`
- `watchdog!WdLogSingleEntry0` at `0x140231e6a`
- `watchdog!WdLogSingleEntry0` at `0x140231fa1`
- `watchdog!WdLogSingleEntry0` at `0x140231fcc`
- `watchdog!WdLogSingleEntry0` at `0x1402321ce`
- `watchdog!WdLogSingleEntry0` at `0x14023222f`
- `watchdog!WdLogSingleEntry0` at `0x14023230d`
- `watchdog!WdLogSingleEntry0` at `0x140232335`
- `watchdog!WdLogSingleEntry0` at `0x14023273f`
- `watchdog!WdLogSingleEntry0` at `0x140232822`
- `watchdog!WdLogSingleEntry0` at `0x1402328e0`
- `watchdog!WdLogSingleEntry0` at `0x140232910`
- `watchdog!WdLogSingleEntry0` at `0x140232993`
- `watchdog!WdLogSingleEntry0` at `0x140232a17`
- `watchdog!WdLogSingleEntry0` at `0x140232a3f`
- `watchdog!WdLogSingleEntry0` at `0x140232abe`
- `watchdog!WdLogSingleEntry0` at `0x140232b12`
- `watchdog!WdLogSingleEntry0` at `0x140232b5a`
- `watchdog!WdLogSingleEntry0` at `0x140232bb7`
- `watchdog!WdLogSingleEntry0` at `0x140232c13`
- `watchdog!WdLogSingleEntry0` at `0x140232c82`
- `watchdog!WdLogSingleEntry0` at `0x140232ccf`
- `watchdog!WdLogSingleEntry0` at `0x140232d2d`
- `watchdog!WdLogSingleEntry0` at `0x140232e39`
- `watchdog!WdLogSingleEntry0` at `0x140232e63`
- `watchdog!WdLogSingleEntry0` at `0x140232e93`
- `watchdog!WdLogSingleEntry0` at `0x140232f12`
- `watchdog!WdLogSingleEntry0` at `0x14023301d`
- `watchdog!WdLogSingleEntry0` at `0x1402330ba`
- `watchdog!WdLogSingleEntry0` at `0x140233176`
- `watchdog!WdLogSingleEntry0` at `0x140233336`
- `watchdog!WdLogSingleEntry0` at `0x14023352e`
- `watchdog!WdLogSingleEntry0` at `0x140233571`
- `watchdog!WdLogSingleEntry0` at `0x1402335a3`
- `watchdog!WdLogSingleEntry0` at `0x1402335e3`
- `watchdog!WdLogSingleEntry0` at `0x140233665`
- `watchdog!WdLogSingleEntry0` at `0x140233690`
- `watchdog!WdLogSingleEntry0` at `0x1402336c5`
- `watchdog!WdLogSingleEntry0` at `0x14023377f`
- `watchdog!WdLogSingleEntry0` at `0x1402337b6`
- `watchdog!WdLogSingleEntry0` at `0x14023383d`
- `watchdog!WdLogSingleEntry0` at `0x1402339ff`
- `watchdog!WdLogSingleEntry0` at `0x140233a87`
- `watchdog!WdLogSingleEntry0` at `0x140233b29`
- `watchdog!WdLogSingleEntry0` at `0x140233b81`
- `watchdog!WdLogSingleEntry0` at `0x140233bab`
- `watchdog!WdLogSingleEntry0` at `0x140233bdc`
- `watchdog!WdLogSingleEntry0` at `0x140233c06`
- `watchdog!WdLogSingleEntry1` at `0x14023122a`
- `watchdog!WdLogSingleEntry1` at `0x14023151c`
- `watchdog!WdLogSingleEntry1` at `0x140231964`
- `watchdog!WdLogSingleEntry1` at `0x140231eab`
- `watchdog!WdLogSingleEntry1` at `0x140231f0d`
- `watchdog!WdLogSingleEntry1` at `0x14023200f`
- `watchdog!WdLogSingleEntry1` at `0x14023213d`
- `watchdog!WdLogSingleEntry1` at `0x140232377`
- `watchdog!WdLogSingleEntry1` at `0x140233469`
- `watchdog!WdLogSingleEntry1` at `0x1402337f4`
- `watchdog!WdLogSingleEntry1` at `0x140233878`
- `watchdog!WdLogSingleEntry1` at `0x1402338a8`
- `watchdog!WdLogSingleEntry1` at `0x1402338cb`
- `watchdog!WdLogSingleEntry1` at `0x1402339df`
- `watchdog!WdLogSingleEntry1` at `0x140233a4a`
- `watchdog!WdLogSingleEntry1` at `0x140233ac3`
- `watchdog!WdLogSingleEntry1` at `0x14023122a`
- `watchdog!WdLogSingleEntry1` at `0x14023151c`
- `watchdog!WdLogSingleEntry1` at `0x140231964`
- `watchdog!WdLogSingleEntry1` at `0x140231eab`
- `watchdog!WdLogSingleEntry1` at `0x140231f0d`
- `watchdog!WdLogSingleEntry1` at `0x14023200f`
- `watchdog!WdLogSingleEntry1` at `0x14023213d`
- `watchdog!WdLogSingleEntry1` at `0x140232377`
- `watchdog!WdLogSingleEntry1` at `0x140233469`
- `watchdog!WdLogSingleEntry1` at `0x1402337f4`
- `watchdog!WdLogSingleEntry1` at `0x140233878`
- `watchdog!WdLogSingleEntry1` at `0x1402338a8`
- `watchdog!WdLogSingleEntry1` at `0x1402338cb`
- `watchdog!WdLogSingleEntry1` at `0x1402339df`
- `watchdog!WdLogSingleEntry1` at `0x140233a4a`

## string_xrefs

- `0x140231aae`: `VmBusSendEscape failed to create standard allocation`
- `0x1402321e5`: `Allocation is already pinned`
- `0x1402330cb`: `Invalid command buffer size`
- `0x140232be7`: `DRT Test: Wrong value of ArgSize passed for D3DKMT_DRT_TEST_COMMAND_DISPLAY_DIAGNOSTICS_TEST.`
- `0x140233676`: `Caller should not set the HardwareAccess so DxgkEscape will acquire the adapter lock shared.`
- `0x1402335f4`: `Failed to acquire the adapter core access exclusively.`
- `0x14023384e`: `DRT test specified invalid buffer size for D3DKMT_DRT_TEST_COMMAND_SOFTGPU_FEATURE_SAMPLE.`
- `0x140233b59`: `D3DKMT_DRT_TEST_COMMAND_PURGE_RESTORE_SEGMENTS must supply a render adapter`

## pseudocode

```c
__int64 __fastcall DxgkDrtTestEscape(struct DXGADAPTER *a1, struct _D3DKMT_DRT_ESCAPE_HEAD *a2, DXGADAPTER **this)
{
  unsigned __int64 AllocationSizeInSystemMemory; // rbx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rcx
  struct DXGPROCESS *Current; // r15
  int v11; // esi
  unsigned int v12; // edi
  unsigned int v13; // esi
  unsigned int HostProcess; // eax
  int StandardAllocation; // esi
  __int64 v16; // rax
  const wchar_t *v17; // r9
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v18; // r12
  unsigned __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v22; // rcx
  int MonitorDeviceObject; // eax
  struct DXGPROCESS *v24; // rax
  struct DXGPROCESS *v25; // r13
  __int64 v26; // rax
  const wchar_t *v27; // r9
  char *v28; // r15
  DXGDEVICE *v29; // rdi
  unsigned int v30; // edx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned int v35; // r8d
  __int64 v36; // rdx
  __int64 v37; // r9
  __int64 v38; // r10
  __int64 v39; // r11
  _OWORD *v40; // rax
  _OWORD *v41; // rcx
  __int64 v42; // rdi
  struct DXGPROCESS *v43; // rax
  DXGPROCESS *v44; // r13
  _QWORD *v45; // r12
  __int64 v46; // rax
  const wchar_t *v47; // r9
  ENSURE_DEVICE_DEREFERENCE_NOLOCKS *v48; // rcx
  __int64 v49; // rax
  unsigned int v50; // esi
  unsigned int v51; // edi
  unsigned int v52; // eax
  DXGDEVICEACCESSLOCKEXCLUSIVE *p_IoStatusBlock; // rcx
  int v54; // ecx
  __int64 v55; // r8
  __int64 AllocationSafe; // rax
  __int64 v57; // rcx
  DXGALLOCATIONREFERENCE *v58; // rcx
  __int64 v59; // rax
  _BYTE *v60; // rax
  int v61; // edx
  __int64 ResourceSafe; // rax
  struct DXGPROCESS *v63; // rax
  NTSTATUS v64; // eax
  __int64 v65; // rdi
  struct DXGPROCESS *v66; // rax
  struct DXGPROCESS *v67; // r12
  struct DXGDEVICE *v68; // r13
  __int64 v69; // rax
  struct DXGCONTEXT *v70; // rdi
  __int64 v71; // rax
  const wchar_t *v72; // r9
  __int64 v73; // r10
  struct DXGPROCESS *v74; // rax
  _QWORD *v75; // rax
  struct DXGPROCESS *v76; // rax
  struct CCD_BTL *v77; // rax
  unsigned int *v78; // r12
  unsigned int v79; // edx
  void *v80; // rdi
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rdi
  IRP *v82; // rax
  struct DXGPROCESS *v83; // rax
  __int64 v84; // rcx
  struct _DXGKARG_COLLECTDIAGNOSTICINFO *DiagnosticInfoArgs; // rax
  struct _DXGKARG_COLLECTDIAGNOSTICINFO *v86; // rdi
  __int64 v87; // rcx
  unsigned int MonitorHash; // eax
  int v89; // ecx
  __int64 v90; // rdx
  int v91; // edi
  RAPID_HPD_MANAGER *v92; // rsi
  __int64 v93; // rcx
  __int64 v94; // rdx
  struct DXGADAPTER *v95; // rax
  struct DXGDEVICE *v96; // rdi
  unsigned int v97; // edi
  __int64 v98; // rax
  const wchar_t *v99; // r9
  unsigned int v100; // esi
  struct DXGADAPTER *v101; // rdi
  struct _D3DDDI_ALLOCATIONLIST *v102; // r12
  unsigned __int8 *v103; // rax
  struct DXGCONTEXT *v104; // r10
  unsigned __int8 IsDxgmms2; // r14
  struct DXGALLOCATION **v106; // rdi
  struct DXGALLOCATION **v107; // rax
  struct DXGADAPTER **HeadIterator; // rax
  DXGCONTEXT *v109; // r10
  struct DXGADAPTER *v110; // rdx
  struct DXGDEVICE *VidPnSourceOwner; // rax
  unsigned int v112; // edx
  int v113; // eax
  int v114; // eax
  __int16 v115; // di
  int v116; // eax
  unsigned int v117; // ecx
  int v118; // eax
  struct DXGADAPTER *v119; // rax
  __int64 v120; // rsi
  unsigned __int8 v121[8]; // [rsp+50h] [rbp-4C8h] BYREF
  struct DXGCONTEXT *v122; // [rsp+58h] [rbp-4C0h] BYREF
  unsigned int v123[2]; // [rsp+60h] [rbp-4B8h] BYREF
  PVOID Object; // [rsp+68h] [rbp-4B0h] BYREF
  PVOID v125[2]; // [rsp+70h] [rbp-4A8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-498h] BYREF
  struct DXGADAPTER *v127[2]; // [rsp+90h] [rbp-488h] BYREF
  _BYTE v128[24]; // [rsp+A0h] [rbp-478h] BYREF
  struct _EX_RUNDOWN_REF *v129; // [rsp+B8h] [rbp-460h] BYREF
  _BYTE v130[8]; // [rsp+C0h] [rbp-458h] BYREF
  struct _DXGK_DISPLAY_SCENARIO_CONTEXT *v131; // [rsp+C8h] [rbp-450h]
  int v132; // [rsp+D0h] [rbp-448h]
  struct _KEVENT Event; // [rsp+D8h] [rbp-440h] BYREF
  _BYTE v134[8]; // [rsp+F0h] [rbp-428h] BYREF
  DXGPUSHLOCK *v135; // [rsp+F8h] [rbp-420h]
  int v136; // [rsp+100h] [rbp-418h]
  PVOID P; // [rsp+110h] [rbp-408h] BYREF
  _BYTE v138[256]; // [rsp+118h] [rbp-400h] BYREF
  int v139; // [rsp+218h] [rbp-300h]
  unsigned __int8 v140[80]; // [rsp+220h] [rbp-2F8h] BYREF
  __int128 v141; // [rsp+270h] [rbp-2A8h]
  _BYTE v142[424]; // [rsp+280h] [rbp-298h] BYREF
  _BYTE v143[160]; // [rsp+430h] [rbp-E8h] BYREF

  AllocationSizeInSystemMemory = 0;
  v130[0] = 0;
  CDisplayScenarioContextScope::ContextScopeConstructor((CDisplayScenarioContextScope *)v130, 0, 0x2Du, 0);
  if ( !*((_DWORD *)a2 + 2) )
  {
    if ( *((_DWORD *)a2 + 1) < 0x10u )
    {
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 286;
      StandardAllocation = -1073741789;
      goto LABEL_465;
    }
    v8 = *((_DWORD *)a2 + 3);
    Current = DXGPROCESS::GetCurrent();
    if ( Current )
    {
      v11 = v8 && (unsigned __int8)DxgkpIsDrtEnabled(v9);
      *((_DWORD *)Current + 102) = (v11 << 12) | *((_DWORD *)Current + 102) & 0xFFFFEFFF;
    }
    if ( a1 && *((_BYTE *)a1 + 209) )
    {
      v12 = *((_DWORD *)a2 + 1);
      v13 = *((_DWORD *)a1 + 1216);
      HostProcess = DXGPROCESS::GetHostProcess(Current);
      StandardAllocation = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendEscape(
                             (struct DXGADAPTER *)((char *)a1 + 4776),
                             HostProcess,
                             v13,
                             0,
                             0,
                             D3DKMT_ESCAPE_DRT_TEST,
                             0,
                             v12,
                             (unsigned __int8 *)a2);
      if ( StandardAllocation < 0 )
      {
        WdLogSingleEntry0(2);
        v16 = 275;
        v17 = L"VmBusSendEscape D3DKMT_ESCAPE_DRT_TEST failed";
LABEL_383:
        WdLogGlobalForLineNumber = v16;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v17, v16, 0, 0, 0, 0);
        goto LABEL_465;
      }
      goto LABEL_465;
    }
LABEL_195:
    StandardAllocation = 0;
    goto LABEL_465;
  }
  v18 = v131;
  if ( !g_OSTestSigningEnabled && !(unsigned __int8)DxgkpIsDrtEnabled(v7) )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 1987;
    goto LABEL_224;
  }
  if ( (*((_DWORD *)DXGPROCESS::GetCurrent() + 102) & 0x100) != 0 )
  {
    v19 = *((unsigned int *)a2 + 2);
    if ( (unsigned int)v19 > 0x31 || (v20 = 0x2000020010000LL, !_bittest64(&v20, v19)) )
    {
      WdLogSingleEntry0(4);
      WdLogGlobalForLineNumber = 299;
LABEL_21:
      CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v130);
      return -1073741811;
    }
  }
  StandardAllocation = 0;
  v22 = *((int *)a2 + 2);
  if ( (int)v22 <= 28 )
  {
    if ( (_DWORD)v22 == 28 )
    {
      if ( !g_OSTestSigningEnabled || *((_DWORD *)a2 + 1) < 0x10u )
        goto LABEL_224;
      v83 = DXGPROCESS::GetCurrent();
      if ( v83 )
      {
        *((_DWORD *)v83 + 102) = *((_DWORD *)v83 + 102) & 0xFFFFDFFF | (*((_BYTE *)a2 + 12) != 0 ? 0x2000 : 0);
        goto LABEL_465;
      }
    }
    else
    {
      if ( (int)v22 <= 16 )
      {
        if ( (_DWORD)v22 != 16 )
        {
          if ( (int)v22 <= 6 )
          {
            if ( (_DWORD)v22 != 6 )
            {
              if ( (_DWORD)v22 != 1 )
              {
                if ( (_DWORD)v22 != 2 )
                {
                  switch ( (_DWORD)v22 )
                  {
                    case 3:
                      if ( DXGADAPTER::IsCoreResourceSharedOwner(this[11]) )
                        COREADAPTERACCESS::Release((COREADAPTERACCESS *)this);
                      StandardAllocation = COREADAPTERACCESS::AcquireExclusive(this, 1, 0);
                      if ( StandardAllocation >= 0 )
                        COREADAPTERACCESS::Release((COREADAPTERACCESS *)this);
                      goto LABEL_465;
                    case 4:
                      if ( *((_DWORD *)a2 + 1) >= 0x10u )
                      {
                        if ( (unsigned int)(*((_DWORD *)a2 + 3) - 1) <= 0x3FF )
                        {
                          g_HmgrTableSizeIncrement = *((_DWORD *)a2 + 3);
                          goto LABEL_465;
                        }
                        WdLogSingleEntry0(3);
                        WdLogGlobalForLineNumber = 384;
                      }
                      else
                      {
                        WdLogSingleEntry0(3);
                        WdLogGlobalForLineNumber = 375;
                      }
                      goto LABEL_224;
                    case 5:
                      if ( *((_DWORD *)a2 + 1) >= 0x14u )
                      {
                        g_DxgkDestroyAllocationFailMemoryAlloc = *((_DWORD *)a2 + 4);
                        goto LABEL_465;
                      }
                      WdLogSingleEntry0(3);
                      WdLogGlobalForLineNumber = 398;
                      goto LABEL_224;
                  }
LABEL_443:
                  WdLogSingleEntry1(3);
                  WdLogGlobalForLineNumber = 1978;
                  goto LABEL_224;
                }
LABEL_407:
                StandardAllocation = -1073741637;
                goto LABEL_465;
              }
              MonitorDeviceObject = MonitorDRTTest(a1, a2, v18);
LABEL_464:
              StandardAllocation = MonitorDeviceObject;
              goto LABEL_465;
            }
            if ( *((_DWORD *)a2 + 1) < 0x114u )
            {
              WdLogSingleEntry0(3);
              WdLogGlobalForLineNumber = 472;
              goto LABEL_224;
            }
            v24 = DXGPROCESS::GetCurrent();
            v25 = v24;
            if ( !v24 )
            {
              WdLogSingleEntry0(2);
              v26 = 480;
LABEL_50:
              v27 = L"Cannot get the current DXGPROCESS";
LABEL_51:
              WdLogGlobalForLineNumber = v26;
              DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v27, v26, 0, 0, 0, 0);
              goto LABEL_224;
            }
            v28 = (char *)v24 + 216;
            KeEnterCriticalRegion();
            ExAcquirePushLockExclusiveEx(v28, 0);
            *((_QWORD *)v28 + 1) = KeGetCurrentThread();
            v29 = 0;
            v125[0] = 0;
            v30 = *((_DWORD *)a2 + 3);
            if ( v30 )
            {
              DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE((DXGDEVICEBYHANDLE *)&v122, v30, v25, (struct DXGDEVICE **)v125);
              v29 = (DXGDEVICE *)v125[0];
              if ( !v125[0] )
              {
                WdLogSingleEntry1(2);
                WdLogGlobalForLineNumber = 496;
                DxgkLogInternalTriageEvent(
                  0,
                  0x40000,
                  -1,
                  (unsigned int)L"The device handle is invalid: 0x%I64x",
                  *((unsigned int *)a2 + 3),
                  0,
                  0,
                  0,
                  0);
                StandardAllocation = -1073741811;
                ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v122);
LABEL_55:
                *((_QWORD *)v28 + 1) = 0;
                ExReleasePushLockExclusiveEx(v28, 0);
                KeLeaveCriticalRegion();
                goto LABEL_465;
              }
              ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v122);
            }
            if ( v29
              || (v29 = (DXGDEVICE *)((*((_QWORD *)v25 + 40) - 24LL) & -(__int64)(*((_QWORD *)v25 + 40) != 0))) != 0 )
            {
              DXGDEVICE::GetContexts(v29, (unsigned int *)a2 + 4, (unsigned int *const)a2 + 5);
              *((_DWORD *)a2 + 3) = *((_DWORD *)v29 + 117);
            }
            else
            {
              WdLogSingleEntry0(2);
              WdLogGlobalForLineNumber = 507;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"The process does not have any devices",
                507,
                0,
                0,
                0,
                0);
              StandardAllocation = -1073741811;
            }
            goto LABEL_55;
          }
          switch ( (_DWORD)v22 )
          {
            case 0xA:
              if ( *((_DWORD *)a2 + 1) >= 0x10u )
              {
                *((_DWORD *)a2 + 3) = *((_DWORD *)a1 + 870);
                goto LABEL_465;
              }
              WdLogSingleEntry0(3);
              WdLogGlobalForLineNumber = 415;
              goto LABEL_224;
            case 0xB:
              v35 = *((_DWORD *)a1 + 870);
              if ( v35 && *((unsigned int *)a2 + 1) >= 344 * (unsigned __int64)(v35 - 1) + 360 )
              {
                v36 = 0;
                do
                {
                  v37 = 520 * v36;
                  v38 = *((_QWORD *)a1 + 417);
                  v39 = 344 * v36;
                  v40 = (_OWORD *)((char *)a2 + 344 * v36 + 16);
                  v41 = (_OWORD *)(520 * v36 + v38 + 8);
                  v42 = 2;
                  do
                  {
                    *v40 = *v41;
                    v40[1] = v41[1];
                    v40[2] = v41[2];
                    v40[3] = v41[3];
                    v40[4] = v41[4];
                    v40[5] = v41[5];
                    v40[6] = v41[6];
                    v40[7] = v41[7];
                    v40 += 8;
                    v41 += 8;
                    --v42;
                  }
                  while ( v42 );
                  *v40 = *v41;
                  v40[1] = v41[1];
                  v40[2] = v41[2];
                  v40[3] = v41[3];
                  v40[4] = v41[4];
                  *(_DWORD *)((char *)a2 + v39 + 352) = *(_DWORD *)(v37 + v38 + 344);
                  *((_BYTE *)a2 + v39 + 356) = *(_BYTE *)(v37 + v38 + 356);
                  LODWORD(AllocationSizeInSystemMemory) = AllocationSizeInSystemMemory + 1;
                  ++v36;
                }
                while ( (unsigned int)AllocationSizeInSystemMemory < v35 );
                goto LABEL_465;
              }
              WdLogSingleEntry0(3);
              WdLogGlobalForLineNumber = 434;
              goto LABEL_224;
            case 0xC:
              if ( *((_DWORD *)a2 + 1) >= 0x10u )
              {
                v34 = *((_QWORD *)a1 + 405);
                if ( v34 )
                  *(_BYTE *)(v34 + 1024) = *((_BYTE *)a2 + 12);
                goto LABEL_465;
              }
              WdLogSingleEntry0(3);
              WdLogGlobalForLineNumber = 453;
              goto LABEL_224;
          }
          if ( (_DWORD)v22 != 14 )
          {
            if ( (_DWORD)v22 == 15 )
            {
              if ( *((_DWORD *)a2 + 1) >= 0xA8u )
              {
                v31 = *((unsigned int *)a2 + 4);
                if ( (unsigned int)v31 < *((_DWORD *)a1 + 870) )
                {
                  v32 = *((unsigned int *)a2 + 3);
                  switch ( (_DWORD)v32 )
                  {
                    case 0:
                      DXGADAPTER::ForcePStateAcrossNodes(a1, *((_DWORD *)a2 + 6));
                      goto LABEL_465;
                    case 1:
                    case 2:
                    case 3:
                      DXGADAPTER::ForcePState(a1, v32, v31, *((unsigned int *)a2 + 6));
                      goto LABEL_465;
                    case 4:
                      *((_DWORD *)a2 + 7) = *((_DWORD *)a1 + 1136);
                      goto LABEL_465;
                    case 5:
                      DXGADAPTER::QueryPStateEngineData(
                        a1,
                        *((_DWORD *)a2 + 5),
                        (struct _DXGK_POWER_P_COMPONENT *)((char *)a2 + 32),
                        (unsigned int *)a2 + 4);
                      goto LABEL_465;
                  }
                }
              }
              goto LABEL_224;
            }
            goto LABEL_443;
          }
          if ( *((_DWORD *)a2 + 1) < 0x14u )
          {
            WdLogSingleEntry0(3);
            WdLogGlobalForLineNumber = 1042;
            goto LABEL_224;
          }
          v33 = *((_QWORD *)a1 + 27);
          if ( v33 )
          {
            MonitorDeviceObject = DxgkHandleThermalCoolingDrtEscape(v33, a2);
            goto LABEL_464;
          }
LABEL_215:
          StandardAllocation = -1073741823;
          goto LABEL_465;
        }
        if ( *((_DWORD *)a2 + 1) < 0x60u )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 522;
          goto LABEL_224;
        }
        v43 = DXGPROCESS::GetCurrent();
        v44 = v43;
        if ( !v43 )
        {
          WdLogSingleEntry0(2);
          v26 = 530;
          goto LABEL_50;
        }
        v125[0] = 0;
        DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(
          (DXGDEVICEBYHANDLE *)&v122,
          *((_DWORD *)a2 + 3),
          v43,
          (struct DXGDEVICE **)v125);
        v45 = v125[0];
        if ( !v125[0] )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 541;
LABEL_103:
          v46 = *((unsigned int *)a2 + 3);
          v47 = L"Cannot get the device by handle: 0x%I64x";
LABEL_104:
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v47, v46, 0, 0, 0, 0);
          StandardAllocation = -1073741811;
LABEL_105:
          v48 = (ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v122;
          goto LABEL_106;
        }
        COREADAPTERACCESS::Release((COREADAPTERACCESS *)this);
        v49 = *(_QWORD *)(v45[2] + 16LL);
        v125[0] = (PVOID)v49;
        if ( *(_BYTE *)(v49 + 209) )
        {
          *(_OWORD *)v140 = *(_OWORD *)a2;
          *(_OWORD *)&v140[16] = *((_OWORD *)a2 + 1);
          *(_OWORD *)&v140[32] = *((_OWORD *)a2 + 2);
          *(_OWORD *)&v140[48] = *((_OWORD *)a2 + 3);
          *(_OWORD *)&v140[64] = *((_OWORD *)a2 + 4);
          v141 = *((_OWORD *)a2 + 5);
          *(_DWORD *)&v140[12] = *((_DWORD *)v45 + 118);
          v50 = *(_DWORD *)&v140[12];
          v51 = *(_DWORD *)(v49 + 4864);
          v52 = DXGPROCESS::GetHostProcess(v44);
          if ( (int)DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendEscape(
                      (DXG_GUEST_VIRTUALGPU_VMBUS *)((char *)v125[0] + 4776),
                      v52,
                      v51,
                      v50,
                      0,
                      D3DKMT_ESCAPE_DRT_TEST,
                      0,
                      0x60u,
                      v140) < 0 )
          {
            WdLogSingleEntry0(2);
            v46 = 572;
            WdLogGlobalForLineNumber = 572;
            v47 = L"VmBusSendEscape failed to create standard allocation";
            goto LABEL_104;
          }
          LODWORD(v129) = *(_DWORD *)&v140[44];
          v123[0] = *(_DWORD *)&v140[48];
          Object = (PVOID)v141;
        }
        else
        {
          LODWORD(v129) = 0;
          Object = 0;
          v123[0] = 0;
        }
        DXGDEVICEACCESSLOCKEXCLUSIVE::DXGDEVICEACCESSLOCKEXCLUSIVE(
          (DXGDEVICEACCESSLOCKEXCLUSIVE *)&IoStatusBlock,
          (struct DXGDEVICE *)v45);
        DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED(
          (DXGADAPTERSTOPRESETLOCKSHARED *)v128,
          *(struct DXGADAPTER **)(v45[2] + 16LL),
          1u);
        COREDEVICEACCESS::COREDEVICEACCESS(v143, v45, 0);
        StandardAllocation = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v143, 0);
        if ( StandardAllocation < 0 )
          goto LABEL_113;
        memset(v142, 0, sizeof(v142));
        *(_DWORD *)&v142[4] = *((_DWORD *)a2 + 3);
        *(_DWORD *)&v142[16] = 4;
        *(_QWORD *)&v142[24] = (char *)a2 + 16;
        v54 = 512;
        if ( *((_BYTE *)a2 + 60) )
          v54 = 513;
        *(_DWORD *)v142 = v54;
        if ( *((_BYTE *)a2 + 65) )
        {
          v54 |= 0x20u;
          *(_DWORD *)v142 = v54;
        }
        if ( *((_BYTE *)a2 + 61) )
        {
          v54 |= 0x400u;
          *(_DWORD *)v142 = v54;
        }
        if ( *((_BYTE *)a2 + 62) )
        {
          v54 |= 0x1000u;
          *(_DWORD *)v142 = v54;
        }
        if ( *((_BYTE *)a2 + 63) )
        {
          v54 |= 0x2000u;
          *(_DWORD *)v142 = v54;
        }
        if ( (*((_DWORD *)a2 + 22) & 1) != 0 )
          *(_DWORD *)v142 = v54 | 0x8000;
        v142[408] = *((_BYTE *)a2 + 64);
        *(_DWORD *)&v142[384] = *((_DWORD *)a2 + 14);
        *(_DWORD *)&v142[388] = *((_DWORD *)a2 + 17);
        *(_DWORD *)&v142[380] = *((_DWORD *)a2 + 10);
        *(_DWORD *)&v142[392] = *((_DWORD *)a2 + 18);
        *(_QWORD *)&v142[400] = *((_QWORD *)a2 + 10);
        StandardAllocation = DXGDEVICE::CreateStandardAllocation(
                               (DXGDEVICE *)v45,
                               (struct _D3DKM_CREATESTANDARDALLOCATION *)v142,
                               (struct COREDEVICEACCESS *)v143);
        if ( StandardAllocation < 0 )
        {
          StandardAllocation = -1073741811;
LABEL_113:
          COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v143);
          DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v128);
          p_IoStatusBlock = (DXGDEVICEACCESSLOCKEXCLUSIVE *)&IoStatusBlock;
          goto LABEL_114;
        }
        v55 = *(unsigned int *)&v142[52];
        *((_DWORD *)a2 + 11) = *(_DWORD *)&v142[52];
        *((_DWORD *)a2 + 12) = *(_DWORD *)&v142[8];
        *((_DWORD *)a2 + 13) = *(_DWORD *)&v142[12];
        if ( (*((_DWORD *)v44 + 102) & 0x100) != 0 )
        {
          *(_QWORD *)v123 = 0;
          AllocationSafe = DXGPROCESS::GetAllocationSafe(v44, &Object, v55);
          DXGALLOCATIONREFERENCE::MoveAssign(v123, AllocationSafe);
          DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&Object);
          if ( *(_QWORD *)v123 )
          {
            v57 = v45[2];
            if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v123 + 8LL) + 16LL) + 16LL) == *(_QWORD *)(v57 + 16) )
              AllocationSizeInSystemMemory = VIDMM_EXPORT::VidMmQueryAllocationSizeInSystemMemory(
                                               *(VIDMM_EXPORT **)(v57 + 760),
                                               *(const struct VIDMM_MULTI_ALLOC **)(*(_QWORD *)v123 + 24LL),
                                               0);
          }
          *((_QWORD *)a2 + 10) = AllocationSizeInSystemMemory;
          v58 = (DXGALLOCATIONREFERENCE *)v123;
        }
        else
        {
          if ( !*((_BYTE *)v125[0] + 209) )
            goto LABEL_113;
          v125[0] = 0;
          v59 = DXGPROCESS::GetAllocationSafe(v44, v127, v55);
          DXGALLOCATIONREFERENCE::MoveAssign(v125, v59);
          DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v127);
          v60 = v125[0];
          if ( v125[0] )
          {
            *((_DWORD *)v125[0] + 5) = (_DWORD)v129;
            v60[128] |= 4u;
            v61 = (int)Object;
            *(_QWORD *)(*((_QWORD *)v60 + 6) + 112LL) = Object;
            *((_DWORD *)v60 + 30) = v61;
          }
          v129 = 0;
          ResourceSafe = DXGPROCESS::GetResourceSafe(v44, v127, *((unsigned int *)a2 + 12));
          DXGRESOURCEREFERENCE::MoveAssign(&v129, ResourceSafe);
          DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE((struct _EX_RUNDOWN_REF **)v127);
          if ( v129 )
            HIDWORD(v129[2].Ptr) = v123[0];
          DXGRESOURCEREFERENCE::~DXGRESOURCEREFERENCE(&v129);
          v58 = (DXGALLOCATIONREFERENCE *)v125;
        }
        DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(v58);
        goto LABEL_113;
      }
      if ( (int)v22 <= 22 )
      {
        if ( (_DWORD)v22 == 22 )
        {
          v121[0] = 0;
          StandardAllocation = DxgkIsConsoleSessionDispBrokerEnabled(v121);
          if ( StandardAllocation < 0 )
            goto LABEL_465;
          if ( !v121[0] )
          {
            v76 = DXGPROCESS::GetCurrent();
            DXGUSERCRIT::DXGUSERCRIT((DXGUSERCRIT *)v128, v76);
            DXGUSERCRIT::Acquire((DXGUSERCRIT *)v128, 0);
            v77 = CCD_BTL::Global();
            CCD_TOPOLOGY::Clear((struct CCD_BTL *)((char *)v77 + 8));
            StandardAllocation = 0;
            DXGUSERCRIT::~DXGUSERCRIT((DXGUSERCRIT *)v128);
            goto LABEL_465;
          }
          StandardAllocation = DxgkRequestDisplayPrivateTest();
          if ( !(unsigned int)Feature_FixCleanCCDDataBaseRace__private_IsEnabledDeviceUsageNoInline()
            || StandardAllocation != -1073741772 )
          {
            goto LABEL_465;
          }
          goto LABEL_195;
        }
        if ( (_DWORD)v22 != 17 )
        {
          if ( (_DWORD)v22 == 18 )
          {
            if ( *((_DWORD *)a2 + 1) < 0x10u )
            {
              WdLogSingleEntry0(3);
              WdLogGlobalForLineNumber = 1011;
              goto LABEL_224;
            }
            v74 = DXGPROCESS::GetCurrent();
            if ( !v74 )
            {
              WdLogSingleEntry0(2);
              v26 = 1019;
              goto LABEL_50;
            }
            Object = 0;
            DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(
              (DXGDEVICEBYHANDLE *)v125,
              *((_DWORD *)a2 + 3),
              v74,
              (struct DXGDEVICE **)&Object);
            v75 = Object;
            if ( Object )
            {
              *((_BYTE *)Object + 1919) = 1;
              *(_BYTE *)(v75[5] + 337LL) = 1;
            }
            else
            {
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 1030;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"Cannot get the device by handle: 0x%I64x",
                *((unsigned int *)a2 + 3),
                0,
                0,
                0,
                0);
              StandardAllocation = -1073741811;
            }
            v48 = (ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v125;
LABEL_106:
            ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(v48);
            goto LABEL_465;
          }
          if ( (_DWORD)v22 == 19 )
          {
            if ( *((_DWORD *)a2 + 1) < 0x10u )
              goto LABEL_224;
            if ( g_OSTestSigningEnabled )
            {
              *((_BYTE *)DXGGLOBAL::GetGlobal() + 1600) = *((_DWORD *)a2 + 3) != 0;
              goto LABEL_465;
            }
            goto LABEL_407;
          }
          if ( (_DWORD)v22 != 20 )
          {
            if ( *((_DWORD *)a2 + 1) < 0x18u )
            {
              WdLogSingleEntry0(3);
              WdLogGlobalForLineNumber = 774;
              goto LABEL_224;
            }
            v63 = DXGPROCESS::GetCurrent();
            if ( !v63 )
            {
              WdLogSingleEntry0(2);
              v26 = 782;
              goto LABEL_50;
            }
            v125[0] = 0;
            DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(
              (DXGDEVICEBYHANDLE *)&v122,
              *((_DWORD *)a2 + 3),
              v63,
              (struct DXGDEVICE **)v125);
            if ( !v125[0] )
            {
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 793;
              goto LABEL_103;
            }
            Object = 0;
            v64 = ObReferenceObjectByHandle(
                    *((HANDLE *)a2 + 2),
                    0x1F0003u,
                    (POBJECT_TYPE)ExEventObjectType,
                    1,
                    &Object,
                    0);
            StandardAllocation = v64;
            if ( v64 < 0 )
            {
              v65 = v64;
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 807;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"hEvent is invalid, returning 0x%I64x",
                v65,
                0,
                0,
                0,
                0);
              goto LABEL_105;
            }
            DXGDEVICEACCESSLOCKEXCLUSIVE::DXGDEVICEACCESSLOCKEXCLUSIVE(
              (DXGDEVICEACCESSLOCKEXCLUSIVE *)&Event,
              (struct DXGDEVICE *)v125[0]);
            KeWaitForSingleObject(Object, Executive, 0, 1u, 0);
            p_IoStatusBlock = (DXGDEVICEACCESSLOCKEXCLUSIVE *)&Event;
LABEL_114:
            DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE(p_IoStatusBlock);
            goto LABEL_105;
          }
          if ( *((_DWORD *)a2 + 1) < 0x18u )
          {
            WdLogSingleEntry0(3);
            WdLogGlobalForLineNumber = 685;
            goto LABEL_224;
          }
          v66 = DXGPROCESS::GetCurrent();
          v67 = v66;
          if ( !v66 )
          {
            WdLogSingleEntry0(2);
            v26 = 693;
            goto LABEL_50;
          }
          Object = 0;
          DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(
            (DXGDEVICEBYHANDLE *)v123,
            *((_DWORD *)a2 + 3),
            v66,
            (struct DXGDEVICE **)&Object);
          v68 = (struct DXGDEVICE *)Object;
          if ( !Object )
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 704;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Cannot get the device by handle: 0x%I64x",
              *((unsigned int *)a2 + 3),
              0,
              0,
              0,
              0);
            StandardAllocation = -1073741811;
LABEL_162:
            v48 = (ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)v123;
            goto LABEL_106;
          }
          COREADAPTERACCESS::Release((COREADAPTERACCESS *)this);
          DXGDEVICEACCESSLOCKEXCLUSIVE::DXGDEVICEACCESSLOCKEXCLUSIVE(
            (DXGDEVICEACCESSLOCKEXCLUSIVE *)&IoStatusBlock,
            v68);
          DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED(
            (DXGADAPTERSTOPRESETLOCKSHARED *)v128,
            *(struct DXGADAPTER **)(*((_QWORD *)v68 + 2) + 16LL),
            1u);
          COREDEVICEACCESS::COREDEVICEACCESS(v143, v68, 0);
          StandardAllocation = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v143, 0);
          if ( StandardAllocation < 0 )
          {
LABEL_164:
            COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v143);
            DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v128);
            DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE((DXGDEVICEACCESSLOCKEXCLUSIVE *)&IoStatusBlock);
            goto LABEL_162;
          }
          DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v122, 0);
          v69 = DXGPROCESS::GetAllocationSafe(v67, v127, *((unsigned int *)a2 + 4));
          DXGALLOCATIONREFERENCE::MoveAssign(&v122, v69);
          DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v127);
          v70 = v122;
          if ( v122 )
          {
            v73 = *((_QWORD *)v68 + 2);
            if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v122 + 1) + 16LL) + 16LL) != *(_QWORD *)(v73 + 16) )
            {
              StandardAllocation = -1073741811;
              WdLogSingleEntry3(2, v68, v122, -1073741811);
              WdLogGlobalForLineNumber = 732;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"Device 0x%p does not match allocation 0x%p owner, returning 0x%I64x",
                (__int64)v68,
                (__int64)v70,
                -1073741811,
                0,
                0);
              goto LABEL_168;
            }
            if ( *((_BYTE *)a2 + 20) )
            {
              if ( (*((_DWORD *)v122 + 18) & 0x800) == 0 )
              {
                StandardAllocation = VIDMM_EXPORT::VidMmPinAllocation(
                                       *(VIDMM_EXPORT **)(v73 + 760),
                                       *(struct VIDMM_GLOBAL **)(v73 + 768),
                                       *((struct VIDMM_MULTI_ALLOC **)v122 + 3),
                                       0,
                                       0);
                if ( StandardAllocation >= 0 )
                  *((_DWORD *)v70 + 18) |= 0x800u;
                goto LABEL_168;
              }
              WdLogSingleEntry0(2);
              v71 = 741;
              WdLogGlobalForLineNumber = 741;
              v72 = L"Allocation is already pinned";
            }
            else
            {
              if ( _bittest((const signed __int32 *)v122 + 18, 0xBu) )
              {
                VIDMM_EXPORT::VidMmUnpinAllocation(
                  *(VIDMM_EXPORT **)(v73 + 760),
                  *(struct VIDMM_GLOBAL **)(v73 + 768),
                  *((struct VIDMM_MULTI_ALLOC **)v122 + 3));
                *((_DWORD *)v70 + 18) &= ~0x800u;
                goto LABEL_168;
              }
              WdLogSingleEntry0(2);
              v71 = 759;
              WdLogGlobalForLineNumber = 759;
              v72 = L"Allocation is not pinned";
            }
          }
          else
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 723;
            v71 = *((unsigned int *)a2 + 4);
            v72 = L"Cannot get the allocation by handle: 0x%I64x";
          }
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v72, v71, 0, 0, 0, 0);
          StandardAllocation = -1073741811;
LABEL_168:
          DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v122);
          goto LABEL_164;
        }
LABEL_326:
        if ( *((_DWORD *)a2 + 1) < 0xA8u )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 853;
          goto LABEL_21;
        }
        v95 = DXGPROCESS::GetCurrent();
        v127[0] = v95;
        if ( !v95 )
        {
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 860;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Cannot get the current DXGPROCESS",
            860,
            0,
            0,
            0,
            0);
          goto LABEL_21;
        }
        v122 = 0;
        DXGCONTEXTBYHANDLE::DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)&Event, *((_DWORD *)a2 + 3), v95, &v122, 0, 1);
        if ( !v122 )
        {
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 869;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Cannot get the context", 869, 0, 0, 0, 0);
LABEL_339:
          StandardAllocation = -1073741811;
LABEL_371:
          DXGCONTEXTBYHANDLE::~DXGCONTEXTBYHANDLE((DXGCONTEXTBYHANDLE *)&Event);
          goto LABEL_465;
        }
        if ( DXGADAPTER::IsCoreResourceSharedOwner(this[11]) )
          COREADAPTERACCESS::Release((COREADAPTERACCESS *)this);
        v96 = (struct DXGDEVICE *)*((_QWORD *)v122 + 2);
        DXGDEVICEACCESSLOCKEXCLUSIVE::DXGDEVICEACCESSLOCKEXCLUSIVE((DXGDEVICEACCESSLOCKEXCLUSIVE *)&IoStatusBlock, v96);
        DXGAUTOPUSHLOCK::DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v134, (struct DXGCONTEXT *)((char *)v122 + 440), 0);
        DXGPUSHLOCK::AcquireExclusive(v135);
        v136 = 2;
        DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v128, a1, 1u);
        COREDEVICEACCESS::COREDEVICEACCESS(v143, v96, 0);
        StandardAllocation = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v143, 0);
        if ( StandardAllocation >= 0 )
        {
          v97 = *((_DWORD *)a2 + 8);
          LODWORD(v129) = v97;
          if ( v97 > 0x10 )
          {
            WdLogSingleEntry0(2);
            v98 = 891;
            v99 = L"Invalid number of allocations";
LABEL_337:
            WdLogGlobalForLineNumber = v98;
            DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v99, v98, 0, 0, 0, 0);
LABEL_338:
            COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v143);
            DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v128);
            DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v134);
            DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE((DXGDEVICEACCESSLOCKEXCLUSIVE *)&IoStatusBlock);
            goto LABEL_339;
          }
          v123[0] = *((_DWORD *)a2 + 4);
          if ( !v123[0] && *((_DWORD *)a2 + 2) == 17 )
          {
            WdLogSingleEntry0(2);
            v98 = 897;
            v99 = L"Invalid command buffer size";
            goto LABEL_337;
          }
          if ( *((_BYTE *)a1 + 209) )
          {
            *((_DWORD *)a2 + 3) = *((_DWORD *)v122 + 7);
            v100 = 0;
            if ( !v97 )
            {
LABEL_348:
              COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v143);
              DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v128);
              DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v134);
              DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE((DXGDEVICEACCESSLOCKEXCLUSIVE *)&IoStatusBlock);
              StandardAllocation = 0;
              goto LABEL_371;
            }
            v101 = v127[0];
            while ( 1 )
            {
              DXGPROCESS::GetAllocationSafe(v101, v125, *((unsigned int *)a2 + 2 * v100 + 9));
              if ( !v125[0] )
                break;
              *((_DWORD *)a2 + 2 * v100 + 9) = *((_DWORD *)v125[0] + 5);
              DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v125);
              if ( ++v100 >= *((_DWORD *)a2 + 8) )
                goto LABEL_348;
            }
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 911;
            DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Invalid allocation handle", 911, 0, 0, 0, 0);
            DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)v125);
            goto LABEL_338;
          }
          memset(v142, 0, 0x170u);
          *(_DWORD *)v142 = *((_DWORD *)a2 + 3);
          *(_DWORD *)&v142[12] = v97;
          v102 = (struct _D3DDDI_ALLOCATIONLIST *)((char *)a2 + 36);
          *(_QWORD *)&v142[40] = (char *)a2 + 36;
          *(_DWORD *)&v142[68] = 32;
          if ( *((_DWORD *)a2 + 2) == 17 )
          {
            *(_DWORD *)&v142[8] = v123[0];
            v103 = (unsigned __int8 *)*((_QWORD *)a2 + 3);
          }
          else
          {
            memset(v140, 0, sizeof(v140));
            *(_DWORD *)&v140[4] = 80;
            *(_DWORD *)v140 = 1;
            *(_QWORD *)&v140[40] = 0x100000000LL;
            *(_DWORD *)&v140[48] = 1;
            *(_OWORD *)&v140[8] = *(_OWORD *)((char *)a2 + 168);
            *(_OWORD *)&v140[24] = *(_OWORD *)&v140[8];
            *(_QWORD *)&v140[68] = *((_QWORD *)a2 + 25);
            *(_QWORD *)&v140[56] = &v140[24];
            *(_WORD *)&v140[64] = 1;
            *(_DWORD *)&v142[8] = 80;
            v103 = v140;
          }
          *(_QWORD *)&v142[24] = v103;
          IsDxgmms2 = DXGADAPTER::IsDxgmms2(*(DXGADAPTER **)(*(_QWORD *)(*((_QWORD *)v122 + 2) + 16LL) + 16LL));
          v121[0] = IsDxgmms2;
          v123[0] = v97;
          P = 0;
          v139 = 0;
          v106 = 0;
          Object = 0;
          if ( IsDxgmms2 )
          {
            v107 = (struct DXGALLOCATION **)PagedPoolZeroedArray<DXGALLOCATION *,32>::AllocateElements(
                                              &P,
                                              (unsigned int)v129);
            v106 = v107;
            Object = v107;
            if ( !v107 )
            {
              WdLogSingleEntry0(3);
              WdLogGlobalForLineNumber = 969;
              if ( P != v138 && P )
                ExFreePoolWithTag(P, 0);
              P = 0;
              v139 = 0;
              COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v143);
              DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v128);
              DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v134);
              DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE((DXGDEVICEACCESSLOCKEXCLUSIVE *)&IoStatusBlock);
              StandardAllocation = -1073741801;
              goto LABEL_371;
            }
            StandardAllocation = DxgkReferenceAllocationList(v123, v102, v107, *((struct DXGDEVICE **)v122 + 2));
            v104 = v122;
          }
          if ( StandardAllocation >= 0 )
          {
            HeadIterator = (struct DXGADAPTER **)DXGNODELIST<DXGCONTEXT,DXGHWQUEUE>::GetHeadIterator(
                                                   (char *)v104 + 400,
                                                   v125);
            v110 = HeadIterator[1];
            if ( v110 == *HeadIterator )
              v110 = 0;
            v127[0] = v110;
            *(_OWORD *)v125 = 0;
            StandardAllocation = DXGCONTEXT::Render(
                                   v109,
                                   (struct _D3DKMT_RENDER *)v142,
                                   (struct COREDEVICEACCESS *)v143,
                                   (struct DXGADAPTERSTOPRESETLOCKSHARED *)v128,
                                   &v122,
                                   v106,
                                   v127);
            v132 = StandardAllocation;
          }
          if ( IsDxgmms2 )
            DxgkUnreferenceAllocationList(v123[0], v106);
          if ( P != v138 && P )
            ExFreePoolWithTag(P, 0);
          P = 0;
          v139 = 0;
        }
        COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v143);
        DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v128);
        DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v134);
        DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE((DXGDEVICEACCESSLOCKEXCLUSIVE *)&IoStatusBlock);
        goto LABEL_371;
      }
      switch ( (_DWORD)v22 )
      {
        case 0x17:
          if ( *((_DWORD *)a2 + 1) < 0x30u )
          {
            WdLogSingleEntry0(3);
            WdLogGlobalForLineNumber = 364;
            goto LABEL_224;
          }
          MonitorDeviceObject = DxgkpSendTestVmBusCommand(a1, a2);
          goto LABEL_464;
        case 0x18:
          if ( *((_DWORD *)a2 + 1) >= 0x10u )
          {
            g_bDMgrIsSetupRunning = *((_DWORD *)a2 + 3) != 0;
            goto LABEL_465;
          }
          goto LABEL_224;
        case 0x19:
          if ( *((_DWORD *)a2 + 1) < 0x1Cu )
            goto LABEL_224;
          memset(&Event, 0, sizeof(Event));
          KeInitializeEvent(&Event, SynchronizationEvent, 0);
          Object = 0;
          v125[0] = 0;
          MonitorDeviceObject = DxgkGetMonitorDeviceObject(
                                  (const struct _LUID *)((char *)a2 + 12),
                                  *((_DWORD *)a2 + 5),
                                  (struct _FILE_OBJECT **)v125,
                                  (struct _DEVICE_OBJECT **)&Object);
          if ( MonitorDeviceObject < 0 )
            goto LABEL_464;
          AttachedDeviceReference = IoGetAttachedDeviceReference((PDEVICE_OBJECT)Object);
          IoStatusBlock = 0;
          v82 = IoBuildDeviceIoControlRequest(
                  0x232433u,
                  AttachedDeviceReference,
                  (char *)a2 + 24,
                  4u,
                  0,
                  0,
                  1u,
                  &Event,
                  &IoStatusBlock);
          if ( v82 )
          {
            StandardAllocation = IofCallDriver(AttachedDeviceReference, v82);
            if ( StandardAllocation == 259 )
            {
              while ( KeWaitForSingleObject(&Event, UserRequest, 0, 1u, 0) == 257 )
                ;
              StandardAllocation = IoStatusBlock.Status;
            }
            ObfDereferenceObject(AttachedDeviceReference);
            ObfDereferenceObject(v125[0]);
            goto LABEL_465;
          }
          ObfDereferenceObject(AttachedDeviceReference);
          ObfDereferenceObject(v125[0]);
          goto LABEL_215;
      }
      if ( (_DWORD)v22 != 26 )
        goto LABEL_443;
      if ( g_OSTestSigningEnabled )
      {
        if ( *((_DWORD *)a2 + 1) < 0x14u )
          goto LABEL_224;
        DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v128, a1, 1u);
        v78 = (unsigned int *)((char *)a2 + 12);
        if ( *((_DWORD *)a1 + 50) != 1 )
        {
          v80 = 0;
LABEL_209:
          DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v128);
          if ( v80 )
          {
            LOBYTE(IoStatusBlock.Status) = 0;
            CDisplayScenarioContextScope::ContextScopeConstructor(
              (CDisplayScenarioContextScope *)&IoStatusBlock,
              0,
              0x2Du,
              0);
            v123[0] = *((_BYTE *)a2 + 16) != 0 ? 1 : 4;
            StandardAllocation = DxgkPowerOnOffMonitor(
                                   (_DWORD)v80,
                                   1,
                                   (int)a2 + 12,
                                   (unsigned int)v123,
                                   1,
                                   (struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)IoStatusBlock.Information);
            ObfDereferenceObject(v80);
            CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)&IoStatusBlock);
            goto LABEL_465;
          }
          goto LABEL_215;
        }
        v79 = *v78;
        if ( *v78 == -1 )
        {
LABEL_207:
          v80 = (void *)*((_QWORD *)a1 + 27);
          ObfReferenceObject(v80);
          goto LABEL_209;
        }
        v121[0] = 0;
        StandardAllocation = DmmIsTargetInClientVidPnTopology(a1, v79, v121);
        if ( StandardAllocation >= 0 )
        {
          if ( !v121[0] )
          {
            DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v128);
            goto LABEL_224;
          }
          goto LABEL_207;
        }
LABEL_276:
        DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v128);
        goto LABEL_465;
      }
    }
LABEL_240:
    StandardAllocation = -1073741790;
    goto LABEL_465;
  }
  if ( (int)v22 > 45 )
  {
    if ( (int)v22 > 51 )
    {
      switch ( (_DWORD)v22 )
      {
        case '4':
          MonitorDeviceObject = DpiDrtClearInternalPanelInfoCacheMux(v22, 0);
          goto LABEL_464;
        case '5':
          if ( !(unsigned int)Feature_DisplayMux_PostGA_BugBundle_3__private_IsEnabledDeviceUsageNoInline() )
          {
            WdLogSingleEntry0(3);
            WdLogGlobalForLineNumber = 1766;
            goto LABEL_224;
          }
          if ( *((_DWORD *)a2 + 1) < 0xE0u )
          {
            WdLogSingleEntry0(3);
            WdLogGlobalForLineNumber = 1755;
            goto LABEL_224;
          }
          MonitorDeviceObject = DpiDrtGetInternalPanelInfoCacheMux(a2);
          goto LABEL_464;
        case '6':
          if ( !(unsigned int)Feature_DisplayMux_PostGA_BugBundle_3__private_IsEnabledDeviceUsageNoInline() )
          {
            WdLogSingleEntry0(3);
            WdLogGlobalForLineNumber = 1744;
            goto LABEL_224;
          }
          if ( *((_DWORD *)a2 + 1) < 0xE0u )
          {
            WdLogSingleEntry0(3);
            WdLogGlobalForLineNumber = 1733;
            goto LABEL_224;
          }
          MonitorDeviceObject = DpiDrtSetInternalPanelInfoCacheMux(a2);
          goto LABEL_464;
      }
      if ( (_DWORD)v22 != 55 )
        goto LABEL_443;
      if ( !a1 || !*((_QWORD *)a1 + 405) )
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 1932;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"D3DKMT_DRT_TEST_COMMAND_PURGE_RESTORE_SEGMENTS must supply a render adapter",
          1932,
          0,
          0,
          0,
          0);
        goto LABEL_407;
      }
      if ( *((_DWORD *)a2 + 1) >= 0x10u )
      {
        v120 = *((int *)a2 + 3);
        if ( (unsigned int)(v120 - 1) <= 2 || (_DWORD)v120 == 5 )
        {
          DXGADAPTER::AcquireCoreSync(a1, 3);
          DXGADAPTER::ApplyCoreSyncAction(a1, (unsigned int)v120);
          DXGADAPTER::ReleaseCoreSync(a1, 5);
          goto LABEL_195;
        }
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 1956;
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Invalid Sync action specified", v120, 0, 0, 0, 0);
      }
      else
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 1938;
      }
LABEL_224:
      StandardAllocation = -1073741811;
      goto LABEL_465;
    }
    if ( (_DWORD)v22 != 51 )
    {
      if ( (_DWORD)v22 == 46 )
        goto LABEL_392;
      if ( (_DWORD)v22 == 47 )
      {
        v112 = *((_DWORD *)a2 + 1);
        if ( v112 < 0x23 )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 1643;
          goto LABEL_224;
        }
        if ( v112 < 20 * *((_DWORD *)a2 + 7) + 35 )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 1651;
          goto LABEL_224;
        }
        MonitorHash = DxgkGetMonitorHash(
                        *(struct _LUID *)((char *)a2 + 12),
                        *((_DWORD *)a2 + 5),
                        (unsigned int *)a2 + 7,
                        (struct _D3DKMT_DRT_ESCAPE_HEAD *)((char *)a2 + 32));
        goto LABEL_280;
      }
      if ( (_DWORD)v22 != 48 )
      {
        if ( (_DWORD)v22 != 49 )
        {
          MonitorDeviceObject = DpiDrtToggleMux();
          goto LABEL_464;
        }
        if ( *((_DWORD *)a2 + 1) < 0xD0u )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 845;
          goto LABEL_21;
        }
        goto LABEL_326;
      }
      if ( a1 )
      {
        if ( !this || DXGADAPTER::IsCoreResourceExclusiveOwner(this[11]) )
        {
          WdLogSingleEntry0(2);
          v26 = 1674;
          v27 = L"Caller should not set the HardwareAccess so DxgkEscape will acquire the adapter lock shared.";
        }
        else if ( *((_DWORD *)a2 + 1) >= 0x10u )
        {
          if ( *((_DWORD *)a2 + 3) < *(_DWORD *)(*((_QWORD *)a1 + 404) + 96LL) )
          {
            COREADAPTERACCESS::Release((COREADAPTERACCESS *)this);
            StandardAllocation = COREADAPTERACCESS::AcquireExclusive(this, 2, 0);
            if ( StandardAllocation < 0 )
            {
              WdLogSingleEntry0(2);
              v16 = 1704;
              v17 = L"Failed to acquire the adapter core access exclusively.";
              goto LABEL_383;
            }
            VidPnSourceOwner = ADAPTER_DISPLAY::GetVidPnSourceOwner(
                                 *((ADAPTER_DISPLAY **)a1 + 404),
                                 *((_DWORD *)a2 + 3));
            if ( VidPnSourceOwner )
              ADAPTER_DISPLAY::ReleaseVidPnSourceOwner(
                *((ADAPTER_DISPLAY **)a1 + 404),
                VidPnSourceOwner,
                *((_DWORD *)a2 + 3));
            goto LABEL_195;
          }
          WdLogSingleEntry0(2);
          v26 = 1690;
          v27 = L"Caller specified VidPn source ID is invalid.";
        }
        else
        {
          WdLogSingleEntry0(2);
          v26 = 1682;
          v27 = L"DRT test specified invalid buffer size for D3DKMT_DRT_RESET_DISPLAY_OWNERSHIP.";
        }
        goto LABEL_51;
      }
      WdLogSingleEntry0(2);
      v26 = 1667;
LABEL_374:
      v27 = L"Caller should specify the adapter.";
      goto LABEL_51;
    }
    if ( !a1 )
    {
      WdLogSingleEntry0(2);
      v26 = 1775;
      goto LABEL_374;
    }
    if ( (*((_DWORD *)a1 + 111) & 8) == 0 )
    {
      WdLogSingleEntry0(2);
      v26 = 1782;
      v27 = L"Call only valid on SoftGPU adapters.";
      goto LABEL_51;
    }
    if ( *((int *)a1 + 779) < 3200 )
    {
      WdLogSingleEntry0(2);
      v26 = 1789;
      v27 = L"Call only valid on WDDM >=3.2 adapters.";
      goto LABEL_51;
    }
    DXGADAPTER::IsFeatureEnabled(a1, v123, 31);
    if ( (v123[0] & 0x10000) == 0 )
    {
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 1799;
      goto LABEL_407;
    }
    v115 = v123[0];
    if ( (unsigned __int16)(LOWORD(v123[0]) - 3) > 2u )
    {
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 1806;
      goto LABEL_407;
    }
    if ( *((_DWORD *)a2 + 1) < 0x18u )
    {
      WdLogSingleEntry0(2);
      v26 = 1814;
      v27 = L"DRT test specified invalid buffer size for D3DKMT_DRT_TEST_COMMAND_SOFTGPU_FEATURE_SAMPLE.";
      goto LABEL_51;
    }
    v116 = *((_DWORD *)a2 + 5);
    if ( v116 )
    {
      if ( v116 == 1 )
      {
        if ( LOWORD(v123[0]) < 4u )
        {
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 1829;
          goto LABEL_407;
        }
      }
      else
      {
        if ( v116 != 2 )
        {
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 1845;
          goto LABEL_224;
        }
        if ( LOWORD(v123[0]) < 5u )
        {
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 1838;
          goto LABEL_407;
        }
      }
    }
    *(_OWORD *)v127 = 0;
    DXGADAPTER::QueryFeatureInterface(a1, 31, LOWORD(v123[0]));
    if ( v115 == 3 )
    {
      if ( v127[0] )
        goto LABEL_224;
    }
    else
    {
      if ( v115 != 4 )
      {
        if ( v115 == 5 && (!v127[0] || !v127[1]) )
          goto LABEL_224;
        goto LABEL_429;
      }
      if ( !v127[0] )
        goto LABEL_224;
    }
    if ( v127[1] )
      goto LABEL_224;
LABEL_429:
    v117 = *((_DWORD *)a2 + 3);
    v118 = *((_DWORD *)a2 + 5);
    if ( !v118 )
      *((_DWORD *)a2 + 4) = v117;
    if ( v118 == 1 )
    {
      v119 = v127[0];
    }
    else
    {
      StandardAllocation = 0;
      if ( v118 != 2 )
        goto LABEL_465;
      v119 = v127[1];
    }
    v125[0] = (PVOID)v117;
    StandardAllocation = ((__int64 (__fastcall *)(_QWORD, PVOID *))v119)(*((_QWORD *)a1 + 36), v125);
    if ( StandardAllocation >= 0 )
      *((_DWORD *)a2 + 4) = HIDWORD(v125[0]);
    goto LABEL_465;
  }
  if ( (_DWORD)v22 == 45 )
  {
    if ( *((_DWORD *)a2 + 1) >= 0x40u )
    {
      v92 = (struct DXGGLOBAL *)((char *)DXGGLOBAL::GetGlobal() + 305640);
      if ( !RAPID_HPD_MANAGER::IsEnabled(v92) )
      {
        StandardAllocation = -1073740959;
        goto LABEL_465;
      }
      if ( *((_DWORD *)a2 + 5) )
      {
        if ( *((_DWORD *)a2 + 6) )
          v94 = 2 - (unsigned int)(*((_DWORD *)a2 + 7) != 0);
        else
          v94 = 0;
        RAPID_HPD_MANAGER::SetTestControl(v93, v94);
      }
      if ( *((_DWORD *)a2 + 3) )
        RAPID_HPD_MANAGER::ReportTriggerEvent(v92, 4, 0);
      if ( *((_DWORD *)a2 + 4) )
        RAPID_HPD_MANAGER::ExtendExistingHPDPeriod(v92, 4, 0);
      if ( *((_DWORD *)a2 + 8) )
        RAPID_HPD_MANAGER::GetCurrenRapidHPDState(
          v92,
          1,
          (struct _D3DKMT_DRT_ESCAPE_HEAD *)((char *)a2 + 36),
          (struct _GUID *)((char *)a2 + 40),
          0);
      *((_DWORD *)a2 + 14) = *((_DWORD *)v92 + 6);
      *((_DWORD *)a2 + 15) = *((_DWORD *)v92 + 7);
      goto LABEL_195;
    }
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 1580;
    goto LABEL_224;
  }
  if ( (int)v22 <= 36 )
  {
    if ( (_DWORD)v22 == 36 )
    {
      MonitorDeviceObject = ForceGpupTdr(a2);
      goto LABEL_464;
    }
    if ( (_DWORD)v22 == 29 )
    {
      MonitorDeviceObject = DrtTestSignalEventCb(a1, a2);
      goto LABEL_464;
    }
    if ( (_DWORD)v22 != 30 )
    {
      if ( (_DWORD)v22 == 31 )
      {
        if ( *((_DWORD *)a2 + 1) < 0x1Cu )
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 1379;
          goto LABEL_224;
        }
        MonitorDeviceObject = DrtTestUpdateRegistryForNewOverride(
                                *(struct _LUID *)((char *)a2 + 12),
                                *((_DWORD *)a2 + 5),
                                *((_DWORD *)a2 + 6));
        goto LABEL_464;
      }
      if ( (_DWORD)v22 == 34 )
      {
        if ( *((_DWORD *)a2 + 1) >= 0x10u )
        {
          v84 = *((unsigned int *)a2 + 3);
          if ( (unsigned int)(v84 - 1) <= 2 )
          {
            if ( *((int *)a1 + 779) >= 2600 && *((_QWORD *)a1 + 404) && *((_QWORD *)a1 + 405) )
            {
              DiagnosticInfoArgs = (struct _DXGKARG_COLLECTDIAGNOSTICINFO *)DxgAllocateDiagnosticInfoArgs(v84);
              v86 = DiagnosticInfoArgs;
              if ( DiagnosticInfoArgs )
              {
                StandardAllocation = DXGADAPTER::DdiCollectDiagnosticInfo(a1, DiagnosticInfoArgs);
                DxgFreeDiagnosticInfoArgs(v86);
              }
              else
              {
                StandardAllocation = -1073741801;
              }
            }
            goto LABEL_465;
          }
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 1408;
        }
        else
        {
          WdLogSingleEntry0(3);
          WdLogGlobalForLineNumber = 1393;
        }
        goto LABEL_224;
      }
      if ( (_DWORD)v22 != 35 )
        goto LABEL_443;
      if ( g_OSTestSigningEnabled )
      {
        if ( *((_DWORD *)a2 + 1) >= 0x18u )
        {
          if ( *((_QWORD *)a2 + 2) )
            StandardAllocation = DxgkSetIndirectDisplayRenderAdapterByHandle(
                                   *((_DWORD *)a2 + 3),
                                   (struct _LUID *)a2 + 2);
          v127[0] = 0;
          DXGADAPTER_REFERENCE::AssignByHandle(v127, *((_DWORD *)a2 + 3));
          if ( v127[0] )
          {
            IoStatusBlock.Pointer = 0;
            ADAPTER_DISPLAY::GetPairedRenderAdapter(
              *((ADAPTER_DISPLAY **)v127[0] + 404),
              (struct DXGADAPTER_REFERENCE *)&IoStatusBlock,
              0);
            if ( IoStatusBlock.Pointer )
              AllocationSizeInSystemMemory = *(_QWORD *)((char *)IoStatusBlock.Pointer + 412);
            *((_QWORD *)a2 + 2) = AllocationSizeInSystemMemory;
            DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)&IoStatusBlock, 0);
          }
          DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v127, 0);
          goto LABEL_465;
        }
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 1509;
        goto LABEL_224;
      }
      goto LABEL_240;
    }
LABEL_392:
    if ( !_bittest((const signed __int32 *)a1 + 645, 0xBu) )
      goto LABEL_465;
    DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v128, a1, 1u);
    if ( !*((_QWORD *)a1 + 405) || *((_DWORD *)a1 + 50) != 1 )
      goto LABEL_276;
    v113 = *((_DWORD *)a2 + 2);
    if ( v113 == 30 )
    {
      v114 = ADAPTER_RENDER::EnableIommuForDrt(*((ADAPTER_RENDER **)a1 + 405), *((struct SYSMM_ADAPTER **)a1 + 28));
    }
    else
    {
      if ( v113 != 46 )
        goto LABEL_276;
      v114 = ADAPTER_RENDER::DisableIommuForDrt(*((ADAPTER_RENDER **)a1 + 405), *((struct SYSMM_ADAPTER **)a1 + 28));
    }
    StandardAllocation = v114;
    goto LABEL_276;
  }
  if ( (_DWORD)v22 == 37 )
  {
    if ( *((_DWORD *)a2 + 1) >= 0x14u )
    {
      v90 = *(_QWORD *)(*((_QWORD *)a1 + 404) + 464LL);
      if ( v90 )
        v91 = *(_DWORD *)(3040LL * *((unsigned int *)a2 + 3) + *(_QWORD *)(v90 + 8) + 136);
      else
        v91 = -1;
      *((_DWORD *)a2 + 4) = v91;
      goto LABEL_465;
    }
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 1551;
    goto LABEL_224;
  }
  if ( (_DWORD)v22 != 38 )
  {
    if ( (_DWORD)v22 != 40 )
    {
      if ( (_DWORD)v22 != 44 )
        goto LABEL_443;
      if ( *((_DWORD *)a2 + 1) < 0x14u )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 821;
        goto LABEL_224;
      }
      if ( !DXGPROCESS::GetCurrent() )
      {
        WdLogSingleEntry0(2);
        v26 = 828;
        goto LABEL_50;
      }
      DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v128, a1, 1u);
      if ( *((_DWORD *)a1 + 50) == 1 )
      {
        v87 = *(_QWORD *)(*((_QWORD *)a1 + 27) + 64LL);
        *((_DWORD *)a2 + 3) = *(_DWORD *)(v87 + 284);
        *((_DWORD *)a2 + 4) = *(_DWORD *)(v87 + 4436);
        *(_DWORD *)(v87 + 4436) = 0;
      }
      else
      {
        StandardAllocation = -1073741130;
      }
      goto LABEL_276;
    }
    if ( *((_DWORD *)a2 + 1) < 0x1Cu )
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 1567;
      goto LABEL_224;
    }
    DXGTRACKEDWORKLOAD::m_enableBypassPowerLevel = *((_DWORD *)a2 + 3);
    DXGTRACKEDWORKLOAD::m_bypassPowerLevel = *((_DWORD *)a2 + 4);
    *((_DWORD *)a2 + 5) = DXGTRACKEDWORKLOAD::m_lastTrackedWorkloadPhysicalAdapterIndex;
    MonitorHash = DXGTRACKEDWORKLOAD::m_lastTrackedWorkloadNodeOrdinal;
LABEL_280:
    *((_DWORD *)a2 + 6) = MonitorHash;
    goto LABEL_465;
  }
  if ( *((_DWORD *)a2 + 1) < 0x30u )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 1435;
    goto LABEL_224;
  }
  if ( *((int *)a1 + 779) < 2700 || !DXGADAPTER::IsFullWDDMAdapter(a1) )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 1446;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"DRT Test: Test is only valid for full WDDM2.7 and above adapters.",
      1446,
      0,
      0,
      0,
      0);
  }
  if ( *((_QWORD *)a2 + 3) != 28 || *((_DWORD *)a2 + 10) != 264 )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 1454;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"DRT Test: Wrong value of ArgSize passed for D3DKMT_DRT_TEST_COMMAND_DISPLAY_DIAGNOSTICS_TEST.",
      1454,
      0,
      0,
      0,
      0);
  }
  v89 = *((_DWORD *)a2 + 3);
  if ( !v89 )
  {
    *((_DWORD *)a2 + 11) = !ADAPTER_DISPLAY::IsDisplayDiagnosticsInterfaceSupported(*((ADAPTER_DISPLAY **)a1 + 404))
                         ? 0xC00000BB
                         : 0;
    goto LABEL_465;
  }
  if ( v89 != 1 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 1487;
    goto LABEL_224;
  }
  v127[0] = *((struct DXGADAPTER **)a2 + 4);
  IoStatusBlock.Pointer = (PVOID)0x10800000001LL;
  IoStatusBlock.Information = (ULONG_PTR)v127;
  StandardAllocation = ADAPTER_DISPLAY::DdiGetDisplayStateIntrusive(
                         *((ADAPTER_DISPLAY **)a1 + 404),
                         (struct _DXGKARG_GETDISPLAYSTATE_INTRUSIVE *)&IoStatusBlock);
  *((_DWORD *)a2 + 11) = StandardAllocation;
  if ( StandardAllocation < 0 )
  {
    WdLogSingleEntry0(2);
    v16 = 1480;
    v17 = L"DRT Test: DdiGetDisplayStateIntrusive failed.";
    goto LABEL_383;
  }
LABEL_465:
  CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v130);
  return (unsigned int)StandardAllocation;
}

```

## disassembly

```asm
0x140231100  push    rbx
0x140231102  push    rsi
0x140231103  push    rdi
0x140231104  push    r12
0x140231106  push    r13
0x140231108  push    r14
0x14023110a  push    r15
0x14023110c  sub     rsp, 4E0h
0x140231113  mov     rax, cs:__security_cookie
0x14023111a  xor     rax, rsp
0x14023111d  mov     [rsp+518h+var_48], rax
0x140231125  mov     rdi, r8
0x140231128  mov     r14, rdx
0x14023112b  mov     r13, rcx
0x14023112e  xor     ebx, ebx
0x140231130  mov     [rsp+518h+var_458], bl
0x140231137  xor     r9d, r9d; unsigned int
0x14023113a  xor     edx, edx; struct _GUID *
0x14023113c  lea     r8d, [rbx+2Dh]; unsigned int
0x140231140  lea     rcx, [rsp+518h+var_458]; this
0x140231148  call    ?ContextScopeConstructor@CDisplayScenarioContextScope@@QEAAXPEBU_GUID@@II@Z; CDisplayScenarioContextScope::ContextScopeConstructor(_GUID const *,uint,uint)
0x14023114d  cmp     [r14+8], ebx
0x140231151  jnz     loc_14023124A
0x140231157  mov     eax, [r14+4]
0x14023115b  cmp     eax, 10h
0x14023115e  jb      loc_140231222
0x140231164  mov     edi, [r14+0Ch]
0x140231168  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14023116d  mov     r15, rax
0x140231170  test    rax, rax
0x140231173  jz      short loc_1402311A0
0x140231175  test    edi, edi
0x140231177  jz      short loc_140231187
0x140231179  call    DxgkpIsDrtEnabled
0x14023117e  test    al, al
0x140231180  jz      short loc_140231187
0x140231182  lea     esi, [rbx+1]
0x140231185  jmp     short loc_140231189
0x140231187  mov     esi, ebx
0x140231189  mov     eax, [r15+198h]
0x140231190  btr     eax, 0Ch
0x140231194  shl     esi, 0Ch
0x140231197  or      eax, esi
0x140231199  mov     [r15+198h], eax
0x1402311a0  test    r13, r13
0x1402311a3  jz      loc_14023246A
0x1402311a9  cmp     [r13+0D1h], bl
0x1402311b0  jz      loc_14023246A
0x1402311b6  mov     edi, [r14+4]
0x1402311ba  mov     esi, [r13+1300h]
0x1402311c1  mov     rcx, r15; this
0x1402311c4  call    ?GetHostProcess@DXGPROCESS@@QEAAIXZ; DXGPROCESS::GetHostProcess(void)
0x1402311c9  lea     rcx, [r13+12A8h]; this
0x1402311d0  mov     [rsp+518h+IoStatusBlock], r14; unsigned __int8 *
0x1402311d5  mov     dword ptr [rsp+518h+var_4E0], edi; unsigned int
0x1402311d9  mov     dword ptr [rsp+518h+InternalDeviceIoControl], ebx; struct _D3DDDI_ESCAPEFLAGS
0x1402311dd  mov     dword ptr [rsp+518h+HandleInformation], 8; enum _D3DKMT_ESCAPETYPE
0x1402311e5  mov     dword ptr [rsp+518h+Object], ebx; unsigned int
0x1402311e9  xor     r9d, r9d; unsigned int
0x1402311ec  mov     r8d, esi; unsigned int
0x1402311ef  mov     edx, eax; unsigned int
0x1402311f1  call    ?VmBusSendEscape@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAJIIIIW4_D3DKMT_ESCAPETYPE@@U_D3DDDI_ESCAPEFLAGS@@IPEAE@Z; DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendEscape(uint,uint,uint,uint,_D3DKMT_ESCAPETYPE,_D3DDDI_ESCAPEFLAGS,uint,uchar *)
0x1402311f6  mov     esi, eax
0x1402311f8  test    eax, eax
0x1402311fa  jns     loc_140233C32
0x140231200  mov     ecx, 2
0x140231205  call    cs:__imp_WdLogSingleEntry0
0x14023120c  nop     dword ptr [rax+rax+00h]
0x140231211  mov     eax, 113h
0x140231216  lea     r9, aVmbussendescap_0; "VmBusSendEscape D3DKMT_ESCAPE_DRT_TEST "...
0x14023121d  jmp     loc_1402335FB
0x140231222  mov     rdx, rax
0x140231225  mov     ecx, 3
0x14023122a  call    cs:__imp_WdLogSingleEntry1
0x140231231  nop     dword ptr [rax+rax+00h]
0x140231236  mov     cs:WdLogGlobalForLineNumber, 11Eh
0x140231240  mov     esi, 0C0000023h
0x140231245  jmp     loc_140233C32
0x14023124a  mov     r12, [rsp+518h+var_450]
0x140231252  cmp     cs:?g_OSTestSigningEnabled@@3EA, bl; uchar g_OSTestSigningEnabled
0x140231258  jnz     short loc_140231283
0x14023125a  call    DxgkpIsDrtEnabled
0x14023125f  test    al, al
0x140231261  jnz     short loc_140231283
0x140231263  mov     ecx, 3
0x140231268  call    cs:__imp_WdLogSingleEntry0
0x14023126f  nop     dword ptr [rax+rax+00h]
0x140231274  mov     cs:WdLogGlobalForLineNumber, 7C3h
0x14023127e  jmp     loc_140232755
0x140231283  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140231288  mov     ecx, [rax+198h]
0x14023128e  shr     ecx, 8
0x140231291  mov     r15d, 1
0x140231297  test    r15b, cl
0x14023129a  jz      short loc_1402312E9
0x14023129c  mov     eax, [r14+8]
0x1402312a0  cmp     eax, 31h ; '1'
0x1402312a3  ja      short loc_1402312B5
0x1402312a5  mov     rcx, 2000020010000h
0x1402312af  bt      rcx, rax
0x1402312b3  jb      short loc_1402312E9
0x1402312b5  mov     ecx, 4
0x1402312ba  call    cs:__imp_WdLogSingleEntry0
0x1402312c1  nop     dword ptr [rax+rax+00h]
0x1402312c6  mov     cs:WdLogGlobalForLineNumber, 12Bh
0x1402312d0  lea     rcx, [rsp+518h+var_458]; this
0x1402312d8  call    ??1CDisplayScenarioContextScope@@QEAA@XZ; CDisplayScenarioContextScope::~CDisplayScenarioContextScope(void)
0x1402312dd  mov     rax, 0FFFFFFFFC000000Dh
0x1402312e4  jmp     loc_140233C41
0x1402312e9  mov     esi, ebx
0x1402312eb  movsxd  rcx, dword ptr [r14+8]
0x1402312ef  cmp     ecx, 1Ch
0x1402312f2  jg      loc_1402327B3
0x1402312f8  jz      loc_140232771
0x1402312fe  cmp     ecx, 10h
0x140231301  jg      loc_140231DF8
0x140231307  jz      loc_1402318E9
0x14023130d  cmp     ecx, 6
0x140231310  jg      loc_140231637
0x140231316  jz      loc_14023142A
0x14023131c  mov     edx, ecx
0x14023131e  sub     edx, r15d
0x140231321  jz      loc_140231417
0x140231327  sub     edx, r15d
0x14023132a  jz      loc_14023380A
0x140231330  sub     edx, r15d
0x140231333  jz      loc_1402313DD
0x140231339  sub     edx, r15d
0x14023133c  jz      short loc_14023137D
0x14023133e  cmp     edx, r15d
0x140231341  jnz     loc_140233A3E
0x140231347  cmp     dword ptr [r14+4], 14h
0x14023134c  jnb     short loc_14023136E
0x14023134e  mov     ecx, 3
0x140231353  call    cs:__imp_WdLogSingleEntry0
0x14023135a  nop     dword ptr [rax+rax+00h]
0x14023135f  mov     cs:WdLogGlobalForLineNumber, 18Eh
0x140231369  jmp     loc_140232755
0x14023136e  mov     eax, [r14+10h]
0x140231372  mov     cs:?g_DxgkDestroyAllocationFailMemoryAlloc@@3HA, eax; int g_DxgkDestroyAllocationFailMemoryAlloc
0x140231378  jmp     loc_140233C32
0x14023137d  cmp     dword ptr [r14+4], 10h
0x140231382  jnb     short loc_1402313A4
0x140231384  mov     ecx, 3
0x140231389  call    cs:__imp_WdLogSingleEntry0
0x140231390  nop     dword ptr [rax+rax+00h]
0x140231395  mov     cs:WdLogGlobalForLineNumber, 177h
0x14023139f  jmp     loc_140232755
0x1402313a4  mov     ecx, [r14+0Ch]
0x1402313a8  lea     eax, [rcx-1]
0x1402313ab  cmp     eax, 3FFh
0x1402313b0  ja      short loc_1402313BD
0x1402313b2  mov     cs:?g_HmgrTableSizeIncrement@@3IA, ecx; uint g_HmgrTableSizeIncrement
0x1402313b8  jmp     loc_140233C32
0x1402313bd  mov     ecx, 3
0x1402313c2  call    cs:__imp_WdLogSingleEntry0
0x1402313c9  nop     dword ptr [rax+rax+00h]
0x1402313ce  mov     cs:WdLogGlobalForLineNumber, 180h
0x1402313d8  jmp     loc_140232755
0x1402313dd  mov     rcx, [rdi+58h]; this
0x1402313e1  call    ?IsCoreResourceSharedOwner@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsCoreResourceSharedOwner(void)
0x1402313e6  test    al, al
0x1402313e8  jz      short loc_1402313F2
0x1402313ea  mov     rcx, rdi; this
0x1402313ed  call    ?Release@COREADAPTERACCESS@@QEAAXXZ; COREADAPTERACCESS::Release(void)
0x1402313f2  xor     r8d, r8d
0x1402313f5  mov     edx, r15d
0x1402313f8  mov     rcx, rdi
0x1402313fb  call    ?AcquireExclusive@COREADAPTERACCESS@@QEAAJW4DXGADAPTER_EXCLUSIVEACCESS_REASON@@IPEBD@Z; COREADAPTERACCESS::AcquireExclusive(DXGADAPTER_EXCLUSIVEACCESS_REASON,uint,char const *)
0x140231400  mov     esi, eax
0x140231402  test    eax, eax
0x140231404  js      loc_140233C32
0x14023140a  mov     rcx, rdi; this
0x14023140d  call    ?Release@COREADAPTERACCESS@@QEAAXXZ; COREADAPTERACCESS::Release(void)
0x140231412  jmp     loc_140233C32
0x140231417  mov     r8, r12; struct _DXGK_DISPLAY_SCENARIO_CONTEXT *
0x14023141a  mov     rdx, r14; struct _D3DKMT_DRT_ESCAPE_HEAD *
0x14023141d  mov     rcx, r13; void *
0x140231420  call    ?MonitorDRTTest@@YAJPEAXPEAU_D3DKMT_DRT_ESCAPE_HEAD@@PEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z; MonitorDRTTest(void *,_D3DKMT_DRT_ESCAPE_HEAD *,_DXGK_DISPLAY_SCENARIO_CONTEXT *)
0x140231425  jmp     loc_140233C30
0x14023142a  cmp     dword ptr [r14+4], 114h
0x140231432  jnb     short loc_140231454
0x140231434  mov     ecx, 3
0x140231439  call    cs:__imp_WdLogSingleEntry0
0x140231440  nop     dword ptr [rax+rax+00h]
0x140231445  mov     cs:WdLogGlobalForLineNumber, 1D8h
0x14023144f  jmp     loc_140232755
0x140231454  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140231459  mov     r13, rax
0x14023145c  test    rax, rax
0x14023145f  jnz     short loc_1402314B0
0x140231461  lea     ecx, [rax+2]
0x140231464  call    cs:__imp_WdLogSingleEntry0
0x14023146b  nop     dword ptr [rax+rax+00h]
0x140231470  mov     eax, 1E0h
0x140231475  lea     r9, aCannotGetTheCu; "Cannot get the current DXGPROCESS"
0x14023147c  mov     [rsp+518h+IoStatusBlock], rbx
0x140231481  mov     [rsp+518h+var_4E0], rbx
0x140231486  mov     qword ptr [rsp+518h+InternalDeviceIoControl], rbx
0x14023148b  mov     [rsp+518h+HandleInformation], rbx
0x140231490  mov     cs:WdLogGlobalForLineNumber, eax
0x140231496  mov     [rsp+518h+Object], rax
0x14023149b  or      r8d, 0FFFFFFFFh
0x14023149f  mov     edx, 40000h
0x1402314a4  xor     ecx, ecx
0x1402314a6  call    DxgkLogInternalTriageEvent
0x1402314ab  jmp     loc_140232755
0x1402314b0  lea     r15, [rax+0D8h]
0x1402314b7  call    cs:__imp_KeEnterCriticalRegion
0x1402314be  nop     dword ptr [rax+rax+00h]
0x1402314c3  xor     edx, edx
0x1402314c5  mov     rcx, r15
0x1402314c8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1402314cf  nop     dword ptr [rax+rax+00h]
0x1402314d4  mov     rax, gs:188h
0x1402314dd  mov     [r15+8], rax
0x1402314e1  mov     rdi, rbx
0x1402314e4  mov     [rsp+518h+var_4A8], rbx
0x1402314e9  mov     edx, [r14+0Ch]; unsigned int
0x1402314ed  test    edx, edx
0x1402314ef  jz      loc_1402315A7
0x1402314f5  lea     r9, [rsp+518h+var_4A8]; struct DXGDEVICE **
0x1402314fa  mov     r8, r13; struct DXGPROCESS *
0x1402314fd  lea     rcx, [rsp+518h+var_4C0]; this
0x140231502  call    ??0DXGDEVICEBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGDEVICE@@@Z; DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(uint,DXGPROCESS *,DXGDEVICE * *)
0x140231507  mov     rdi, [rsp+518h+var_4A8]
0x14023150c  test    rdi, rdi
0x14023150f  jnz     loc_14023159D
0x140231515  mov     edx, [r14+0Ch]
0x140231519  lea     ecx, [rdi+2]
0x14023151c  call    cs:__imp_WdLogSingleEntry1
0x140231523  nop     dword ptr [rax+rax+00h]
0x140231528  mov     cs:WdLogGlobalForLineNumber, 1F0h
0x140231532  mov     eax, [r14+0Ch]
0x140231536  mov     [rsp+518h+IoStatusBlock], rbx
0x14023153b  mov     [rsp+518h+var_4E0], rbx
0x140231540  mov     qword ptr [rsp+518h+InternalDeviceIoControl], rbx
0x140231545  mov     [rsp+518h+HandleInformation], rbx
0x14023154a  mov     [rsp+518h+Object], rax
0x14023154f  lea     r9, aTheDeviceHandl; "The device handle is invalid: 0x%I64x"
0x140231556  or      r8d, 0FFFFFFFFh
0x14023155a  mov     edx, 40000h
0x14023155f  xor     ecx, ecx
0x140231561  call    DxgkLogInternalTriageEvent
0x140231566  mov     rsi, 0FFFFFFFFC000000Dh
0x14023156d  lea     rcx, [rsp+518h+var_4C0]; this
0x140231572  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x140231577  mov     [r15+8], rbx
0x14023157b  xor     edx, edx
0x14023157d  mov     rcx, r15
0x140231580  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140231587  nop     dword ptr [rax+rax+00h]
0x14023158c  call    cs:__imp_KeLeaveCriticalRegion
0x140231593  nop     dword ptr [rax+rax+00h]
0x140231598  jmp     loc_140233C32
0x14023159d  lea     rcx, [rsp+518h+var_4C0]; this
0x1402315a2  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x1402315a7  test    rdi, rdi
0x1402315aa  jnz     short loc_140231618
0x1402315ac  mov     rax, [r13+140h]
0x1402315b3  lea     rcx, [rax-18h]
0x1402315b7  neg     rax
0x1402315ba  sbb     rdi, rdi
0x1402315bd  and     rdi, rcx
0x1402315c0  jnz     short loc_140231618
0x1402315c2  lea     ecx, [rdi+2]
0x1402315c5  call    cs:__imp_WdLogSingleEntry0
0x1402315cc  nop     dword ptr [rax+rax+00h]
0x1402315d1  mov     eax, 1FBh
0x1402315d6  mov     cs:WdLogGlobalForLineNumber, eax
0x1402315dc  mov     [rsp+518h+IoStatusBlock], rbx
0x1402315e1  mov     [rsp+518h+var_4E0], rbx
0x1402315e6  mov     qword ptr [rsp+518h+InternalDeviceIoControl], rbx
0x1402315eb  mov     [rsp+518h+HandleInformation], rbx
0x1402315f0  mov     [rsp+518h+Object], rax
0x1402315f5  lea     r9, aTheProcessDoes; "The process does not have any devices"
0x1402315fc  or      r8d, 0FFFFFFFFh
0x140231600  mov     edx, 40000h
0x140231605  xor     ecx, ecx
0x140231607  call    DxgkLogInternalTriageEvent
0x14023160c  mov     rsi, 0FFFFFFFFC000000Dh
0x140231613  jmp     loc_140231577
0x140231618  lea     r8, [r14+14h]; unsigned int *
0x14023161c  lea     rdx, [r14+10h]; unsigned int *
0x140231620  mov     rcx, rdi; this
0x140231623  call    ?GetContexts@DXGDEVICE@@QEAAXPEAIQEAI@Z; DXGDEVICE::GetContexts(uint *,uint * const)
0x140231628  mov     ecx, [rdi+1D4h]
0x14023162e  mov     [r14+0Ch], ecx
0x140231632  jmp     loc_140231577
0x140231637  mov     edx, ecx
0x140231639  sub     edx, 0Ah
0x14023163c  jz      loc_1402318B2
0x140231642  sub     edx, r15d
0x140231645  jz      loc_140231780
0x14023164b  sub     edx, r15d
0x14023164e  jz      loc_14023173A
0x140231654  sub     edx, 2
0x140231657  jz      loc_1402316F6
0x14023165d  cmp     edx, r15d
0x140231660  jnz     loc_140233A3E
  ... truncated ...
```
