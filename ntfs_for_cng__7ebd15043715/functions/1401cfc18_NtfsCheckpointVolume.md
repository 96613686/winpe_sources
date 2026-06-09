# NtfsCheckpointVolume

- ea: `0x1401cfc18`
- end: `0x1401d1f54`
- name: `NtfsCheckpointVolume`
- size: `9020`
- prototype: `void __fastcall(unsigned int *Context1, __int64, char, char, char, char, __int64)`
- caller_count: `10`
- callee_count: `49`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003c454`
- `0x1400cc78c`
- `0x1400deecc`
- `0x140138c20`
- `0x1401cf440`
- `0x1401cf860`
- `0x1401f63f8`
- `0x14021ebd0`
- `0x140230170`
- `0x14023030c`

## callees

- `0x1400054e8`
- `0x140007ea0`
- `0x14000c290`
- `0x140014e74`
- `0x14002066c`
- `0x140020de0`
- `0x140021220`
- `0x1400224cc`
- `0x1400226f0`
- `0x140022a00`
- `0x140022da8`
- `0x1400284b0`
- `0x14002f230`
- `0x140038f44`
- `0x14003c34c`
- `0x14004062c`
- `0x140040d48`
- `0x14004a7c4`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x14012e4f0`
- `0x14013af10`
- `0x14013f374`
- `0x140140660`
- `0x140141870`
- `0x1401aab20`
- `0x1401ae808`
- `0x1401b2830`
- `0x1401b4080`
- `0x1401bfc38`
- `0x1401c1bbc`
- `0x1401cf1c8`
- `0x1401cfc18`
- `0x1401d24d8`
- `0x1401d2cec`
- `0x1401f3850`
- `0x1401f3890`
- `0x1401ffe5c`
- `0x14020950c`
- `0x1402096ac`
- `0x14020f350`
- `0x1402230d8`
- `0x14022adc0`
- `0x14022bdf0`
- `0x140230888`
- `0x14027379c`
- `0x140274a08`
- `0x14029bbe8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1401d0c43`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d0e96`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d14f5`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d0c43`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d0e96`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d14f5`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401cfe2f`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401d1a68`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401cfe2f`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401d1a68`
- `ntoskrnl!IoClearActivityIdThread` at `0x1401d1a21`
- `ntoskrnl!IoClearActivityIdThread` at `0x1401d1a90`
- `ntoskrnl!IoClearActivityIdThread` at `0x1402b0254`
- `ntoskrnl!IoClearActivityIdThread` at `0x1401d1a21`
- `ntoskrnl!IoClearActivityIdThread` at `0x1401d1a90`
- `ntoskrnl!IoClearActivityIdThread` at `0x1402b0254`
- `ntoskrnl!KeSetPriorityThread` at `0x1401d1da6`
- `ntoskrnl!KeSetPriorityThread` at `0x1401d1edf`
- `ntoskrnl!KeSetPriorityThread` at `0x1402b01fd`
- `ntoskrnl!KeSetPriorityThread` at `0x1401d1da6`
- `ntoskrnl!KeSetPriorityThread` at `0x1401d1edf`
- `ntoskrnl!KeSetPriorityThread` at `0x1402b01fd`
- `ntoskrnl!CcGetDirtyPages` at `0x1401d05ab`
- `ntoskrnl!CcGetDirtyPages` at `0x1401d05ab`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401cfe0c`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401cfe0c`
- `ntoskrnl!KeClearEvent` at `0x1401d12e4`
- `ntoskrnl!KeClearEvent` at `0x1401d1c72`
- `ntoskrnl!KeClearEvent` at `0x1401d12e4`
- `ntoskrnl!KeClearEvent` at `0x1401d1c72`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d1325`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402cc4b1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d1325`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402cc4b1`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401d1c81`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401d1cb8`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402cc483`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401d1c81`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401d1cb8`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402cc483`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0980`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0d47`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0dbd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0e54`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d13be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1711`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1760`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1c2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1e19`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b00b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b00cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b00e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0980`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0d47`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0dbd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0e54`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d13be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1711`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1760`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1c2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1e19`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b00b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b00cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b00e8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401d0364`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401d1457`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401d0364`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401d1457`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401d1adf`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402cc4ca`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401d1adf`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402cc4ca`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0096`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d00ac`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d050b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0526`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d08ee`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0904`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d09c1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d09d7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0c61`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0d8d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0da3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d12bb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d16be`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d1e37`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d1e98`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402b010b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402b0174`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0096`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d00ac`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d050b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0526`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d08ee`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0904`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d09c1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d09d7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0c61`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0d8d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0da3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d12bb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d16be`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d1e37`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d1e98`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402b010b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402b0174`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d005f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d00fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d010d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d02bc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0499`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d04a8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d08d3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d09a8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0a26`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0a35`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0afe`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0de1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0df4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0f14`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d12fa`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1dd8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1df0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1e03`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1e55`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1eaf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b006a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b0084`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b0097`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b0131`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b018e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d005f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d00fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d010d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d02bc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0499`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d04a8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d08d3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d09a8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0a26`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0a35`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0afe`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0de1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0df4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0f14`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d12fa`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1dd8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1df0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1e03`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1e55`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1eaf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b006a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b0084`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b0097`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b0131`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b018e`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401cfe7d`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401cfe7d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401cfeba`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401cfeba`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401d0433`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401d044c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401d0ef4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401d0433`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401d044c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401d0ef4`
- `ntoskrnl!CcFlushCache` at `0x1401d0c10`
- `ntoskrnl!CcFlushCache` at `0x1401d0c10`

## pseudocode

```c
void __fastcall NtfsCheckpointVolume(
        unsigned int *Context1,
        __int64 a2,
        char a3,
        char a4,
        char a5,
        char a6,
        __int64 a7)
{
  char v7; // bl
  char v10; // r12
  PVOID QuadPart; // rdi
  __int64 v12; // rcx
  _QWORD *ActivityIdThread; // rax
  char *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  struct _ERESOURCE *v20; // rcx
  int v21; // eax
  _DWORD *FirstRestartTable; // rsi
  __int64 *v23; // r11
  char v24; // cl
  unsigned __int16 *v25; // r11
  __int64 v26; // r9
  _DWORD *v27; // r8
  __int64 v28; // rax
  union _LARGE_INTEGER v29; // r9
  union _LARGE_INTEGER v30; // rdx
  unsigned int v31; // esi
  unsigned __int16 *v32; // rdx
  char v33; // si
  __int64 v34; // r9
  char v35; // r12
  char v36; // di
  __int64 *v37; // rdx
  int v38; // esi
  __int64 v39; // rcx
  char *v40; // rcx
  int v41; // edx
  int v42; // r8d
  unsigned int v43; // esi
  PVOID v44; // r12
  unsigned __int16 *v45; // r8
  __int64 v46; // r9
  unsigned __int16 *v47; // rsi
  unsigned __int16 *v48; // rdx
  unsigned __int16 *v49; // rdx
  _DWORD *i; // rax
  unsigned __int16 *v51; // rax
  __int64 v52; // rcx
  __int64 v53; // rcx
  unsigned __int16 *v54; // rdx
  __int64 v55; // r9
  unsigned __int16 *v56; // r9
  __int64 v57; // r8
  char *v58; // r8
  _DWORD *v59; // r9
  unsigned int v60; // eax
  __int64 v61; // r12
  __int64 v62; // r8
  char v63; // r9
  __int64 v64; // rcx
  unsigned int v65; // eax
  unsigned int v66; // edx
  __int64 *v67; // r8
  bool v68; // si
  struct _ERESOURCE *v69; // r12
  __int64 v70; // rax
  __int64 LastLsn; // rbx
  __int64 v72; // r8
  __int64 v73; // rbx
  unsigned __int16 *v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // rcx
  union _LARGE_INTEGER v77; // rdx
  ULONG v78; // esi
  __int64 v79; // rcx
  char v80; // di
  __int64 v81; // rcx
  int v82; // r8d
  _QWORD *v83; // rcx
  unsigned int v84; // esi
  __int64 v85; // r12
  __int64 v86; // rdx
  _QWORD *v87; // rax
  __int64 v88; // rax
  __int64 *v89; // rdx
  int v90; // r9d
  char v91; // si
  _DWORD *k; // rsi
  __int64 v93; // rcx
  unsigned int v94; // eax
  __int64 v95; // rbx
  __int64 v96; // rax
  char v97; // bl
  __int64 v98; // rcx
  __int64 v99; // rdi
  __int64 v100; // rbx
  __int64 v102; // rcx
  signed __int64 v103; // rax
  __int64 *v104; // rdx
  NTSTATUS v105; // esi
  PLARGE_INTEGER Timeout; // [rsp+98h] [rbp-488h]
  char v107; // [rsp+E9h] [rbp-437h] BYREF
  char v108; // [rsp+EAh] [rbp-436h]
  char v109; // [rsp+EBh] [rbp-435h]
  char v110; // [rsp+ECh] [rbp-434h]
  char v111; // [rsp+EDh] [rbp-433h]
  char v112; // [rsp+EEh] [rbp-432h]
  unsigned int RestartTableIndex; // [rsp+F0h] [rbp-430h] BYREF
  _WORD v114[2]; // [rsp+F4h] [rbp-42Ch] BYREF
  char v115; // [rsp+F8h] [rbp-428h]
  int v116; // [rsp+FCh] [rbp-424h]
  int v117; // [rsp+100h] [rbp-420h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+108h] [rbp-418h] BYREF
  int v119; // [rsp+110h] [rbp-410h]
  int v120; // [rsp+114h] [rbp-40Ch]
  char v121; // [rsp+118h] [rbp-408h]
  int v122; // [rsp+11Ch] [rbp-404h]
  KPRIORITY Priority; // [rsp+120h] [rbp-400h]
  int v124; // [rsp+124h] [rbp-3FCh] BYREF
  __int64 v125; // [rsp+128h] [rbp-3F8h] BYREF
  PVOID PoolWithTag; // [rsp+130h] [rbp-3F0h]
  __int64 *v127; // [rsp+138h] [rbp-3E8h] BYREF
  __int64 v128; // [rsp+140h] [rbp-3E0h] BYREF
  _DWORD *v129; // [rsp+148h] [rbp-3D8h]
  unsigned int v130; // [rsp+150h] [rbp-3D0h]
  PVOID P; // [rsp+158h] [rbp-3C8h]
  __int64 v132; // [rsp+160h] [rbp-3C0h] BYREF
  __int64 v133; // [rsp+168h] [rbp-3B8h]
  __int64 v134; // [rsp+170h] [rbp-3B0h]
  __int64 v135; // [rsp+178h] [rbp-3A8h]
  __int64 v136; // [rsp+180h] [rbp-3A0h]
  __int64 v137; // [rsp+188h] [rbp-398h]
  __int64 v138; // [rsp+190h] [rbp-390h]
  __int64 v139; // [rsp+198h] [rbp-388h]
  unsigned int v140; // [rsp+1A0h] [rbp-380h]
  unsigned __int16 *j; // [rsp+1A8h] [rbp-378h]
  unsigned __int16 *v142; // [rsp+1B0h] [rbp-370h]
  __int64 v143; // [rsp+1B8h] [rbp-368h]
  unsigned int *v144; // [rsp+1C0h] [rbp-360h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+1C8h] [rbp-358h] BYREF
  __int64 v146; // [rsp+1D8h] [rbp-348h]
  PVOID v147; // [rsp+1E0h] [rbp-340h]
  __int64 *v148; // [rsp+1E8h] [rbp-338h]
  __int64 v149; // [rsp+1F0h] [rbp-330h]
  union _LARGE_INTEGER v150; // [rsp+1F8h] [rbp-328h]
  _QWORD v151[28]; // [rsp+208h] [rbp-318h] BYREF
  _BYTE Resource[224]; // [rsp+2E8h] [rbp-238h] BYREF
  __int128 v153; // [rsp+3C8h] [rbp-158h] BYREF
  __int64 v154; // [rsp+3D8h] [rbp-148h]
  __int128 Context2; // [rsp+3E0h] [rbp-140h] BYREF
  PVOID Object[2]; // [rsp+3F0h] [rbp-130h]
  __int128 v157; // [rsp+400h] [rbp-120h] BYREF
  __int64 v158; // [rsp+410h] [rbp-110h] BYREF
  _QWORD v159[14]; // [rsp+418h] [rbp-108h] BYREF
  _QWORD v160[10]; // [rsp+488h] [rbp-98h] BYREF

  v7 = a4;
  v144 = Context1;
  v137 = a2;
  memset(v159, 0, sizeof(v159));
  memset(Resource, 0, sizeof(Resource));
  memset(v151, 0, sizeof(v151));
  v128 = 0;
  v107 = 0;
  v108 = 0;
  v10 = 0;
  RestartTableIndex = 0;
  v114[0] = 0;
  v117 = 0;
  v153 = 0;
  v154 = 0;
  if ( (*(_DWORD *)(a2 + 4) & 0x2000000) != 0 )
    return;
  P = 0;
  FileOffset.QuadPart = 0;
  v138 = 0;
  PoolWithTag = 0;
  QuadPart = (PVOID)NtfsLarge0.QuadPart;
  Priority = 16;
  v134 = 0;
  v120 = 0;
  v136 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v139 = 0;
  if ( !v7 && (Context1[4] & 0x200LL) != 0 )
  {
    v143 = MEMORY[0xFFFFF78000000320];
    if ( (dword_140095BE8 & 1) == 0 || (unsigned int)dword_1400953B0 * v143 > 300000000 )
    {
      if ( (*(_DWORD *)(a2 + 24) & 0x1000) == 0 )
        NtfsLockUnlockSystemFilePages(Context1, a2, 0);
      if ( *(_BYTE *)(a2 + 8417) )
        NtfsFspCloseInternal(0, a2, 0, 0, 0);
    }
  }
  if ( !a3 )
  {
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
    while ( 1 )
    {
      v102 = *(unsigned int *)(a2 + 572);
      v124 = v102;
      if ( (v102 & 0x12) == 0 )
        break;
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
      if ( !a4 )
        return;
      v105 = KeWaitForSingleObject((PVOID)(a2 + 632), Executive, 0, 0, 0);
      if ( v105 < 0 )
      {
        if ( NtfsStatusDebugFlags
          && (unsigned int)v105 < 0xFFFFFFED
          && v105 != -1073741802
          && v105 != -1073741807
          && (unsigned int)(v105 + 2147483643) > 1
          && v105 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal((__int64)Context1, v105, 0x160726u);
        }
        NtfsRaiseStatusInternal((__int64)Context1, v105, 0, 0, 1443622);
      }
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
      if ( (v124 & 2) != 0 && (*(_DWORD *)(a2 + 572) & 4) != 0 )
        a7 = 0;
    }
    if ( (*(_DWORD *)(a2 + 4) & 0x1000) != 0
      && ((a6 & 0xC) != 0 || !a4 || a7 == *(_QWORD *)(a2 + 824) || (v102 & 0x24) == 0) )
    {
      if ( (Context1[4] & 0x200LL) == 0 )
        goto LABEL_304;
      v103 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a2 + 7392), 0);
      if ( !v103 )
      {
        if ( (Context1[4] & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
        {
          McTemplateU0p_EtwWriteTransfer(v102, (const EVENT_DESCRIPTOR *)logsup_c1913, a2);
        }
        goto LABEL_304;
      }
      if ( (Context1[4] & 0x400LL) != 0 && v103 <= MEMORY[0xFFFFF78000000320] )
      {
LABEL_304:
        *(_DWORD *)(a2 + 572) |= 0x12u;
        *(_QWORD *)(a2 + 1424) = KeGetCurrentThread();
        KeClearEvent((PRKEVENT)(a2 + 632));
        KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
        v7 = a4;
        if ( a4 )
        {
          Priority = KeSetPriorityThread(KeGetCurrentThread(), 16);
          v10 = RestartTableIndex;
          if ( Priority != 16 )
            v111 = 1;
        }
        else
        {
          v10 = RestartTableIndex;
        }
        goto LABEL_4;
      }
    }
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
    return;
  }
LABEL_4:
  v119 = 0;
  if ( !v7 && (Context1[4] & 0x200LL) != 0 && NtfsLWWaitLogThreshold )
  {
    NtfsQueryLogFileUsage(*(_QWORD *)(a2 + 232), v114);
    v112 = 1;
    v121 = 1;
    v10 = v114[0];
    if ( v114[0] >= (unsigned int)NtfsLWWaitLogThreshold )
    {
      NtfsFlushLsnStreamsOnLogTooFull(Context1, a2, v114[0]);
      if ( (*(_DWORD *)(a2 + 4) & 0x8000823) != 1 )
        goto LABEL_133;
    }
    v7 = a4;
  }
  memset(v159, 0, sizeof(v159));
  memset(Resource, 0, sizeof(Resource));
  if ( a3 )
  {
    if ( v7 )
    {
      v120 = 1;
      v122 = 1;
      if ( (a6 & 4) != 0 )
      {
        v12 = 3;
        v122 = 3;
        if ( (a6 & 8) != 0 )
          v12 = 11;
        v120 = v12;
        v122 = v12;
        if ( (dword_1400956B8 & 0x1000) != 0 )
        {
          v12 = (unsigned int)v12 | 4;
          v120 = v12;
          v122 = v12;
        }
      }
    }
  }
  v143 = MEMORY[0xFFFFF78000000320];
  if ( (!Context1 || (Context1[4] & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
  {
    McTemplateU0p_EtwWriteTransfer(v12, (const EVENT_DESCRIPTOR *)logsup_c2018, a2);
  }
  if ( Context1 && (v12 = *((_QWORD *)Context1 + 15)) != 0 )
  {
    *((_QWORD *)&v153 + 1) = *(_QWORD *)v12;
    v154 = *(_QWORD *)(v12 + 8);
    *(_QWORD *)&v153 = (char *)&v153 + 8;
    v14 = (char *)&v153 + 8;
  }
  else
  {
    ActivityIdThread = (_QWORD *)IoGetActivityIdThread(v12);
    if ( ActivityIdThread )
    {
      *((_QWORD *)&v153 + 1) = *ActivityIdThread;
      v154 = ActivityIdThread[1];
      *(_QWORD *)&v153 = (char *)&v153 + 8;
      v14 = (char *)&v153 + 8;
    }
    else
    {
      *(_QWORD *)&v153 = 0;
      v14 = 0;
    }
  }
  v139 = IoSetActivityIdThread(v14);
  if ( (Microsoft_Windows_NtfsEnableBits & 0x800000) != 0 || (Microsoft_Windows_NtfsEnableBits & 0x1000000) != 0 )
  {
    if ( !v112 )
    {
      NtfsQueryLogFileUsage(*(_QWORD *)(a2 + 232), v114);
      v10 = v114[0];
    }
    if ( a4 )
    {
      if ( (Microsoft_Windows_NtfsEnableBits & 0x1000000) == 0 )
        goto LABEL_16;
      v89 = NTFS_ETW_CLEAN_CHECKPOINT_START;
    }
    else
    {
      if ( (Microsoft_Windows_NtfsEnableBits & 0x800000) == 0 )
        goto LABEL_16;
      v89 = NTFS_ETW_PERIODIC_CHECKPOINT_START;
    }
    McTemplateK0phh_EtwWriteTransfer(
      v15,
      (const EVENT_DESCRIPTOR *)v89,
      (const GUID *)v153,
      v16,
      *((_WORD *)Context1 + 196),
      v10);
  }
LABEL_16:
  v17 = *(_QWORD *)(a2 + 40);
  if ( v17 )
  {
    NtfsAcquireResourceShared(v15, v17, 1u);
    ExAcquireFastMutex((PFAST_MUTEX)(a2 + 1992));
    v18 = *(_QWORD *)(a2 + 1976);
    if ( v18 == a2 + 1976 )
      v136 = *(_QWORD *)(*(_QWORD *)(a2 + 40) + 32LL);
    else
      v136 = *(_QWORD *)(*(_QWORD *)(v18 - 24) + 288LL);
    v146 = v136;
    ExReleaseFastMutex((PFAST_MUTEX)(a2 + 1992));
    v19 = *(_QWORD *)(a2 + 40);
    if ( *(_WORD *)v19 == 1794 )
      v20 = (struct _ERESOURCE *)(*(_QWORD *)(v19 + 104) + 64LL);
    else
      v20 = *(struct _ERESOURCE **)(v19 + 8);
    ExReleaseResourceLite(v20);
  }
  ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1064), 1u);
  ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1168), 1u);
  if ( (a6 & 1) != 0 )
  {
    v127 = 0;
    Context2 = 0;
    *(_OWORD *)Object = 0;
    v157 = 0;
    v158 = 0;
    IoStatus.Pointer = &Context2;
    IoStatus.Information = 56;
    RestartTableIndex = NtfsAllocateRestartTableIndex((__int64)Context1, a2 + 1064);
    v127 = 0;
    LfsGetActiveLsnRange(*(_QWORD *)(a2 + 232), (char *)&v157 + 8, &v158);
    LfsWrite(
      *(_QWORD *)(a2 + 232),
      1,
      (int)&IoStatus,
      v90,
      (__int64)&RestartTableIndex,
      (__int64)v127,
      (__int64)v127,
      0,
      a6 & 3,
      0,
      (__int64)&v127);
    NtfsFreeRestartTableIndex((__int64)Context1, a2 + 1064, RestartTableIndex);
    NtfsCommitCurrentTransaction((__int64)Context1);
  }
  LastLsn = LfsQueryLastLsn(*(_QWORD *)(a2 + 232));
  v159[1] = LastLsn;
  v133 = LastLsn;
  v128 = LastLsn;
  ExReleaseResourceLite((PERESOURCE)(a2 + 1168));
  ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
  if ( !a4 )
  {
    Context2 = 0;
    *(_OWORD *)Object = 0;
    v157 = 0;
    v135 = 0;
    v116 = 0;
    ExAcquireResourceSharedLite((PERESOURCE)(a2 + 1064), 1u);
    ExAcquireResourceSharedLite((PERESOURCE)(a2 + 1168), 1u);
    for ( i = NtfsGetFirstRestartTable(a2 + 1064); i; i = (_DWORD *)NtfsGetNextRestartTable(a2 + 1064, i) )
    {
      v93 = *((_QWORD *)i + 1);
      if ( v93 )
      {
        if ( v93 < LastLsn )
          LastLsn = *((_QWORD *)i + 1);
        v133 = LastLsn;
      }
    }
    if ( *(_DWORD *)(a2 + 1296) )
    {
      if ( *(_QWORD *)(a2 + 1288) < LastLsn )
        LastLsn = *(_QWORD *)(a2 + 1288);
      v133 = LastLsn;
    }
    v128 = LastLsn;
    v51 = *(unsigned __int16 **)(a2 + 1272);
    if ( v51[2] )
    {
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), *v51 * (unsigned int)v51[1] + 24, 0x4C46744Eu);
      memmove(
        PoolWithTag,
        *(const void **)(a2 + 1272),
        **(unsigned __int16 **)(a2 + 1272) * (unsigned int)*(unsigned __int16 *)(*(_QWORD *)(a2 + 1272) + 2LL) + 24);
      HIDWORD(v159[7]) = **(unsigned __int16 **)(a2 + 1272) * *(unsigned __int16 *)(*(_QWORD *)(a2 + 1272) + 2LL) + 24;
    }
    ExReleaseResourceLite((PERESOURCE)(a2 + 1168));
    ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
    v35 = 0;
    NtfsInitializeRestartTable(
      (*(_DWORD *)(a2 + 4892) != 0 ? 40 : 44) + 8 * (*(_DWORD *)(a2 + 404) - 1),
      *(_DWORD *)(a2 + 5360),
      *(_DWORD *)(a2 + 4892) >= 2u,
      0,
      (PERESOURCE)Resource);
    ExAcquireResourceExclusiveLite((PERESOURCE)Resource, 1u);
    v109 = 1;
    ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 832), 1u);
    v107 = 1;
    if ( *(_DWORD *)(a2 + 4892) < 2u )
      v119 = NtfsCalculateNamedBytes(v52, a2);
    Object[0] = 0;
    *(_QWORD *)&v157 = 0;
    Context2 = (unsigned __int64)Resource;
    Object[1] = (PVOID)0x7FFFFFFFFFFFFFFFLL;
    *((_QWORD *)&v157 + 1) = &v117;
    CcGetDirtyPages(*(PVOID *)(a2 + 232), (PDIRTY_PAGE_ROUTINE)DirtyPageRoutine, Context1, &Context2);
    QuadPart = Object[1];
    v147 = Object[1];
    if ( (_BYTE)v157 )
    {
      ++*(_DWORD *)(a2 + 4876);
      if ( (!Context1 || (Context1[4] & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
      {
        McTemplateU0pd_EtwWriteTransfer(v53, (const EVENT_DESCRIPTOR *)logsup_c2672, a2, *(_DWORD *)(a2 + 4876));
      }
      if ( Object[0] )
      {
        ObfDereferenceObject(Object[0]);
        Object[0] = 0;
      }
      Context1[98] = 1;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)Context1, 0xC0000188, 0x160A82u);
      NtfsRaiseStatusInternal((__int64)Context1, -1073741432, 0, 0, 1444482);
    }
    ++*(_DWORD *)(a2 + 4868);
    if ( (!Context1 || (Context1[4] & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
    {
      McTemplateU0pd_EtwWriteTransfer(v53, (const EVENT_DESCRIPTOR *)logsup_c2696, a2, *(_DWORD *)(a2 + 4868));
    }
    v45 = *(unsigned __int16 **)&Resource[208];
    *(_DWORD *)(a2 + 5360) = (*(_WORD *)(*(_QWORD *)&Resource[208] + 4LL) & 0xFFE0) + 32;
    if ( QuadPart != *(PVOID *)(a2 + 1328) )
    {
      if ( Object[0] )
      {
        ObfDereferenceObject(Object[0]);
        v45 = *(unsigned __int16 **)&Resource[208];
      }
      if ( QuadPart != (PVOID)0x7FFFFFFFFFFFFFFFLL )
        *(_QWORD *)(a2 + 1328) = QuadPart;
      if ( QuadPart )
      {
        if ( (__int64)QuadPart < *(_QWORD *)(a2 + 1056) )
          QuadPart = *(PVOID *)(a2 + 1056);
        v147 = QuadPart;
      }
      j = 0;
      if ( v45[2] )
      {
        v47 = v45 + 12;
        v54 = v45 + 12;
        for ( j = v45 + 12; ; j = v47 )
        {
          v55 = *v45;
          if ( (int)v54 - (int)v45 >= (unsigned int)v55 * v45[1] + 24 )
            break;
          if ( *(_DWORD *)v54 == -1 )
            goto LABEL_92;
          v47 = (unsigned __int16 *)((char *)v47 + v55);
          v54 = v47;
        }
      }
      v47 = 0;
LABEL_92:
      v135 = (__int64)v47;
      v49 = v47;
      while ( v47 )
      {
        if ( *((_DWORD *)v49 + 2) )
        {
          v56 = *(unsigned __int16 **)(a2 + 1040);
          if ( (v56[3] & 1) != 0 )
            v57 = (unsigned int)*v56 * (*((_DWORD *)v49 + 1) - 1) + 24LL;
          else
            v57 = *((unsigned int *)v49 + 1);
          v58 = (char *)v56 + v57;
          v58[12] = 1;
          *((_DWORD *)v49 + 1) = *(_DWORD *)(*((_QWORD *)v58 + 4) + 16LL);
          v59 = *(_DWORD **)(*((_QWORD *)v58 + 4) + 24LL);
          v129 = v59;
          if ( v59 == *(_DWORD **)(a2 + 40) )
          {
            v88 = *(_QWORD *)(a2 + 1952);
            if ( *(_DWORD *)(a2 + 4892) )
              *((_QWORD *)v49 + 2) += v88;
            else
              *(_QWORD *)(v49 + 10) += v88;
          }
          v60 = (unsigned int)(*((_DWORD *)v49 + 2) + *(_DWORD *)(a2 + 480)) >> *(_DWORD *)(a2 + 488);
          RestartTableIndex = v60;
          *((_DWORD *)v49 + 3) = v60;
          if ( *(_DWORD *)(a2 + 4892) )
          {
            if ( *((_QWORD *)v49 + 3) < (__int64)QuadPart )
              *((_QWORD *)v49 + 3) = QuadPart;
            v61 = *((__int64 *)v49 + 2) >> *(_DWORD *)(a2 + 488);
            *((_QWORD *)v49 + 2) = v61;
            v62 = (__int64)(v49 + 16);
          }
          else
          {
            *((_DWORD *)v49 + 4) = 0;
            if ( *(_QWORD *)(v49 + 14) < (__int64)QuadPart )
              *(_QWORD *)(v49 + 14) = QuadPart;
            v61 = *(__int64 *)(v49 + 10) >> *(_DWORD *)(a2 + 488);
            *(_QWORD *)(v49 + 10) = v61;
            v62 = (__int64)(v49 + 18);
          }
          v127 = (__int64 *)v62;
          v148 = (__int64 *)v62;
          v140 = v60;
          v149 = v61;
          v125 = 0;
          v132 = 0;
          v130 = 0;
          while ( v60 )
          {
            v63 = NtfsLookupNtfsMcbEntryWithSyncFlag((__int64)(v59 + 100), v61, &v132, &v125, 0, 0, 0, 0);
            if ( !v63 || (v64 = v132, v132 == -1) )
            {
              v64 = 0;
              v132 = 0;
              v125 = RestartTableIndex;
              v63 = 0;
            }
            v65 = RestartTableIndex;
            if ( v125 > RestartTableIndex )
              v125 = RestartTableIndex;
            v66 = 0;
            v67 = v127;
            while ( 1 )
            {
              v130 = v66;
              if ( v66 >= (unsigned int)v125 )
                break;
              *v67++ = v64;
              v127 = v67;
              v148 = v67;
              if ( v63 )
                v132 = ++v64;
              ++v66;
            }
            v61 += v125;
            v149 = v61;
            v60 = v65 - v125;
            RestartTableIndex = v60;
            v140 = v60;
            v59 = v129;
          }
        }
        else
        {
          v94 = (_DWORD)v47 - (_DWORD)v45;
          if ( (v45[3] & 1) != 0 )
            v94 = (v94 - 24) / *v45 + 1;
          NtfsFreeRestartTableIndex((__int64)Context1, (__int64)Resource, v94);
        }
        v142 = v47;
        v45 = *(unsigned __int16 **)&Resource[208];
        v46 = (unsigned __int16)**(_WORD **)&Resource[208];
        v47 = (unsigned __int16 *)((char *)v47 + v46);
        v48 = v47;
        v142 = v47;
        while ( (int)v48 - *(_DWORD *)&Resource[208] < (unsigned int)v46
                                                     * *(unsigned __int16 *)(*(_QWORD *)&Resource[208] + 2LL)
                                                     + 24 )
        {
          if ( *(_DWORD *)v48 == -1 )
            goto LABEL_71;
          v47 = (unsigned __int16 *)((char *)v47 + v46);
          v48 = v47;
          v142 = v47;
        }
        v47 = 0;
LABEL_71:
        v49 = v47;
        v135 = (__int64)v47;
      }
      if ( (*(_DWORD *)(a2 + 572) & 0x20) != 0 && v159[1] == *(_QWORD *)(a2 + 1304) && !v45[2] )
      {
        v69 = (struct _ERESOURCE *)(a2 + 1064);
        ExAcquireResourceSharedLite((PERESOURCE)(a2 + 1064), 1u);
        v68 = *(_WORD *)(*(_QWORD *)(a2 + 1272) + 4LL) == 0;
        ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
      }
      else
      {
        v68 = 0;
        v69 = (struct _ERESOURCE *)(a2 + 1064);
      }
      if ( v68 )
      {
        if ( v159[1] == v128 )
        {
          memset(v160, 0, sizeof(v160));
          v124 = 80;
          LfsQueryLogFileInformation(*(_QWORD *)(a2 + 232), v160, &v124);
          v95 = v160[5];
          if ( v160[6] < v160[5]
            && (*(_DWORD *)(a2 + 4) & 0x20) == 0
            && (int)NtfsFlushDiskCache(*(_QWORD *)(a2 + 216)) >= 0 )
          {
            LfsSetDurableLsn(*(_QWORD *)(a2 + 232), v95);
            ++v128;
          }
        }
        v70 = *(_QWORD *)(a2 + 1040);
        if ( !*(_WORD *)(v70 + 4) && *(_WORD *)(v70 + 2) > 0x10u )
        {
          InitializeNewTable(0x28u, 8u, *(_DWORD *)(a2 + 4892) >= 2u, (__int64)v151);
          ExFreePoolWithTag(*(PVOID *)(a2 + 1040), 0);
          *(_QWORD *)(a2 + 1040) = v151[26];
          if ( *(_QWORD *)(a2 + 4920) != a2 + 832 )
          {
            InitializeNewTable(0x2Cu, 8u, 0, (__int64)v151);
            ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(a2 + 4920) + 208LL), 0);
            *(_QWORD *)(*(_QWORD *)(a2 + 4920) + 208LL) = v151[26];
          }
        }
        ExReleaseResourceLite((PERESOURCE)(a2 + 832));
        v36 = 0;
        v107 = 0;
        ExAcquireResourceExclusiveLite(v69, 1u);
        ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1168), 1u);
        v35 = 1;
        if ( !*(_WORD *)(*(_QWORD *)(a2 + 1272) + 4LL) )
        {
          LfsResetUndoTotal(*(_QWORD *)(a2 + 232), 2, 8304);
          if ( *(_WORD *)(*(_QWORD *)(a2 + 1272) + 2LL) > 0xAu )
          {
            InitializeNewTable(*(_DWORD *)(a2 + 4892) < 2u ? 40 : 48, 5u, *(_DWORD *)(a2 + 4892) >= 2u, (__int64)v151);
            ExFreePoolWithTag(*(PVOID *)(a2 + 1272), 0);
            *(_QWORD *)(a2 + 1272) = v151[26];
          }
        }
        goto LABEL_134;
      }
      *(_DWORD *)(a2 + 572) &= ~0x20u;
      v21 = v119;
      if ( v119 )
      {
        v119 += 4;
        v43 = v21 + 4;
        v44 = ExAllocatePoolWithTag((POOL_TYPE)528, (unsigned int)(v21 + 4), 0x4C46744Eu);
        P = v44;
        memset(v44, 0, v43);
        FileOffset.QuadPart = (LONGLONG)v44;
        v150.QuadPart = (LONGLONG)v44;
      }
      FirstRestartTable = NtfsGetFirstRestartTable(a2 + 832);
LABEL_24:
      while ( FirstRestartTable )
      {
        v24 = (char)v23;
        v115 = (char)v23;
        if ( *((_BYTE *)FirstRestartTable + 12) == (_BYTE)v23
          && *(__int64 **)(*((_QWORD *)FirstRestartTable + 4) + 24LL) == v23 )
        {
          NtfsFreeAttributeEntry((__int64)Context1, a2, (__int64)FirstRestartTable);
          v24 = 1;
          v115 = 1;
          LOWORD(v23) = 0;
        }
        if ( *(_DWORD *)(a2 + 4892) < 2u && !v24 )
        {
          v28 = *((_QWORD *)FirstRestartTable + 4);
          if ( *(_WORD *)(v28 + 32) != (_WORD)v23 )
          {
            v29 = FileOffset;
            *(_WORD *)FileOffset.QuadPart = *(_WORD *)(v28 + 16);
            *(_WORD *)(v29.QuadPart + 2) = *(_WORD *)(*((_QWORD *)FirstRestartTable + 4) + 32LL);
            memmove(
              (void *)(v29.QuadPart + 4),
              *(const void **)(*((_QWORD *)FirstRestartTable + 4) + 40LL),
              *(unsigned __int16 *)(*((_QWORD *)FirstRestartTable + 4) + 32LL));
            v30 = FileOffset;
            *(_WORD *)(FileOffset.QuadPart
                     + 2 * ((unsigned __int64)*(unsigned __int16 *)(FileOffset.QuadPart + 2) >> 1)
                     + 4) = 0;
            FileOffset.QuadPart = *(unsigned __int16 *)(v30.QuadPart + 2) + v30.QuadPart + 6;
            v150 = FileOffset;
          }
        }
        v129 = FirstRestartTable;
        v25 = *(unsigned __int16 **)(a2 + 1040);
        v26 = *v25;
        FirstRestartTable = (_DWORD *)((char *)FirstRestartTable + v26);
        v27 = FirstRestartTable;
        v129 = FirstRestartTable;
        while ( (int)v27 - *(_DWORD *)(a2 + 1040) < (unsigned int)v26 * v25[1] + 24 )
        {
          if ( *v27 == -1 )
          {
            v23 = 0;
            goto LABEL_24;
          }
          FirstRestartTable = (_DWORD *)((char *)FirstRestartTable + v26);
          v27 = FirstRestartTable;
          v129 = FirstRestartTable;
        }
        v23 = 0;
        FirstRestartTable = 0;
      }
      if ( P != v23 )
        *(_DWORD *)FileOffset.QuadPart = 0;
      if ( *(_DWORD *)(a2 + 4892) < 2u )
      {
        v37 = *(__int64 **)(*(_QWORD *)(a2 + 4920) + 208LL);
        if ( *((_WORD *)v37 + 2) != (_WORD)v23 )
        {
          v159[2] = NtfsWriteLog(
                      (__int64)Context1,
                      *(_QWORD *)(a2 + 48),
                      0,
                      29,
                      v37,
                      *(unsigned __int16 *)v37 * (unsigned int)*((unsigned __int16 *)v37 + 1) + 24,
                      (int)v23,
                      v23,
                      (unsigned int)v23,
                      (__int64)v23,
                      (__int16)v23,
                      (__int16)v23,
                      (int)v23).QuadPart;
          LODWORD(v159[6]) = **(unsigned __int16 **)(*(_QWORD *)(a2 + 4920) + 208LL)
                           * *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(a2 + 4920) + 208LL) + 2LL)
                           + 24;
          v116 = 1;
        }
        ExReleaseResourceLite((PERESOURCE)(a2 + 832));
        v107 = 0;
        v38 = v119;
        if ( v119 )
        {
          v159[3] = NtfsWriteLog(
                      (__int64)Context1,
                      *(_QWORD *)(a2 + 48),
                      0,
                      30,
                      (__int64 *)P,
                      v119,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0).QuadPart;
          HIDWORD(v159[6]) = v38;
          v31 = 1;
          v116 = 1;
        }
        else
        {
          v31 = v116;
        }
      }
      else
      {
        ExReleaseResourceLite((PERESOURCE)(a2 + 832));
        v107 = 0;
        v31 = 0;
      }
      if ( *(_WORD *)(*(_QWORD *)&Resource[208] + 4LL) )
      {
        v159[4] = NtfsWriteLog(
                    (__int64)Context1,
                    *(_QWORD *)(a2 + 48),
                    0,
                    31,
                    *(__int64 **)&Resource[208],
                    (unsigned __int16)**(_WORD **)&Resource[208]
                  * (unsigned int)*(unsigned __int16 *)(*(_QWORD *)&Resource[208] + 2LL)
                  + 24,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0).QuadPart;
        LODWORD(v159[7]) = (unsigned __int16)**(_WORD **)&Resource[208]
                         * *(unsigned __int16 *)(*(_QWORD *)&Resource[208] + 2LL)
                         + 24;
        v31 = 1;
        v116 = 1;
      }
      ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1064), 1u);
      ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1168), 1u);
      *(_DWORD *)(a2 + 572) &= ~4u;
      if ( PoolWithTag )
      {
        v159[5] = NtfsWriteLog(
                    (__int64)Context1,
                    *(_QWORD *)(a2 + 48),
                    0,
                    32,
                    (__int64 *)PoolWithTag,
                    SHIDWORD(v159[7]),
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0).QuadPart;
        v31 = 1;
        v116 = 1;
      }
      v32 = *(unsigned __int16 **)(a2 + 1272);
      if ( v32[2] <= v31 )
      {
        v39 = Context1[7];
        if ( (_DWORD)v39 )
        {
          if ( (v32[3] & 1) != 0 )
            v39 = (unsigned int)*v32 * ((_DWORD)v39 - 1) + 24LL;
          v40 = (char *)v32 + v39;
          v41 = *((_DWORD *)v40 + 8) + 2;
          v42 = *((_DWORD *)v40 + 9) + 8304;
        }
        else
        {
          v41 = 2;
          v42 = 8304;
        }
        LfsResetUndoTotal(*(_QWORD *)(a2 + 232), v41, v42);
        if ( !*(_WORD *)(*(_QWORD *)&Resource[208] + 4LL) )
          *(_DWORD *)(a2 + 572) |= 0x20u;
      }
      ExReleaseResourceLite((PERESOURCE)(a2 + 1168));
      ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
      goto LABEL_48;
    }
    ExReleaseResourceLite((PERESOURCE)(a2 + 832));
    v72 = 0;
    v36 = 0;
    v107 = 0;
    if ( !Object[0] )
      goto LABEL_134;
    IoStatus = 0;
    FileOffset.QuadPart = 0;
    v73 = *((_QWORD *)Object[0] + 3);
    v74 = *(unsigned __int16 **)(Context2 + 208);
    if ( (v74[3] & 1) != 0 )
      v75 = (unsigned int)*v74 * (DWORD2(Context2) - 1) + 24LL;
    else
      v75 = DWORD2(Context2);
    v76 = (__int64)v74 + v75;
    v135 = v76;
    if ( *(_DWORD *)(a2 + 4892) )
      v77 = *(union _LARGE_INTEGER *)(v76 + 16);
    else
      v77 = *(union _LARGE_INTEGER *)(v76 + 20);
    FileOffset = v77;
    v78 = *(_DWORD *)(v76 + 8);
    if ( v73 == *(_QWORD *)(a2 + 40) )
    {
      v76 = v77.QuadPart + *(_QWORD *)(a2 + 1952);
      FileOffset.QuadPart = v76;
    }
    ++*(_DWORD *)(a2 + 4888);
    if ( (!Context1 || (Context1[4] & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
    {
      McTemplateU0pd_EtwWriteTransfer(v76, (const EVENT_DESCRIPTOR *)logsup_c2781, a2, *(_DWORD *)(a2 + 4888));
    }
    v80 = NtfsAcquireScbForLazyWrite(v73, 1u, v72);
    if ( (!Context1 || (Context1[4] & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
    {
      McTemplateU0pp_EtwWriteTransfer(
        v79,
        (const EVENT_DESCRIPTOR *)logsup_c2790,
        a2,
        *(_QWORD *)(*(_QWORD *)(v73 + 184) + 8LL) & 0xFFFFFFFFFFFFLL);
    }
    CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v73 + 288) + 16LL), &FileOffset, v78, &IoStatus);
    if ( (!Context1 || (Context1[4] & 0x100000LL) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
    {
      McTemplateU0pp_EtwWriteTransfer(v81, (const EVENT_DESCRIPTOR *)logsup_c2799, a2, Object[0]);
    }
    if ( v80 )
      NtfsReleaseScbFromLazyWrite(v73);
    ObfDereferenceObject(Object[0]);
LABEL_133:
    v36 = v107;
    v35 = 0;
LABEL_134:
    v33 = a4;
    goto LABEL_257;
  }
  ++*(_DWORD *)(a2 + 4864);
  if ( (!Context1 || (Context1[4] & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
  {
    McTemplateU0pd_EtwWriteTransfer(0, (const EVENT_DESCRIPTOR *)logsup_c2230, a2, *(_DWORD *)(a2 + 4864));
  }
  if ( a5 )
  {
    NtfsAcquireAllFiles(Context1, a2, 7);
    v110 = 1;
  }
  else
  {
    v91 = 0;
    NtfsAcquireSharedVcb((__int64)Context1, a2, 1);
    v108 = 1;
    ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1064), 1u);
    *(_BYTE *)(a2 + 1281) = 1;
    if ( *(_WORD *)(*(_QWORD *)(a2 + 1272) + 4LL) )
    {
      KeClearEvent((PRKEVENT)(a2 + 1400));
      v91 = 1;
    }
    ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
    if ( v91 )
      KeWaitForSingleObject((PVOID)(a2 + 1400), Executive, 0, 0, 0);
  }
  if ( !NtfsIsVcbAvailableForThisRequest((__int64)Context1, a2) )
    goto LABEL_133;
  ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 832), 1u);
  v107 = 1;
  LfsResetUndoTotal(*(_QWORD *)(a2 + 232), 1, -8192);
  if ( a5 )
  {
    NtfsFlushVolume((int)Context1);
    for ( k = NtfsGetFirstRestartTable(a2 + 832); k; k = (_DWORD *)NtfsGetNextRestartTable(a2 + 832, k) )
      NtfsFreeAttributeEntry((__int64)Context1, a2, (__int64)k);
  }
  else
  {
    LOBYTE(v82) = 1;
    NtfsFlushLsnStreams((_DWORD)Context1, a2, v82, 0, (__int64)&v107);
  }
  *(_DWORD *)(a2 + 572) |= 4u;
  while ( 1 )
  {
    v83 = *(_QWORD **)(a2 + 4928);
    if ( v83 == (_QWORD *)(a2 + 4928) )
      break;
    v86 = *v83;
    if ( *(_QWORD **)(*v83 + 8LL) != v83 || (v87 = (_QWORD *)v83[1], (_QWORD *)*v87 != v83) )
      __fastfail(3u);
    *v87 = v86;
    *(_QWORD *)(v86 + 8) = v87;
    ExFreePoolWithTag(v83, 0);
  }
  v84 = 1;
  if ( *(_DWORD *)(a2 + 4892) > 1u )
    v84 = *(_DWORD *)(a2 + 4892);
  InitializeNewTable(0x28u, 8u, v84 >= 2, (__int64)v151);
  v129 = (_DWORD *)v151[26];
  v138 = v151[26];
  if ( v84 < 2 )
    InitializeNewTable(0x28u, 5u, 0, (__int64)v151);
  else
    InitializeNewTable(0x30u, 5u, 1u, (__int64)v151);
  v85 = v151[26];
  PoolWithTag = (PVOID)v151[26];
  ExFreePoolWithTag(*(PVOID *)(a2 + 1040), 0);
  *(_QWORD *)(a2 + 1040) = v129;
  v138 = 0;
  if ( v84 != *(_DWORD *)(a2 + 4892) )
    NtfsUpdateOatVersion(a2, v84);
  NtfsCommitCurrentTransaction((__int64)Context1);
  ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1064), 1u);
  ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1168), 1u);
  ExFreePoolWithTag(*(PVOID *)(a2 + 1272), 0);
  *(_QWORD *)(a2 + 1272) = v85;
  PoolWithTag = 0;
  ExReleaseResourceLite((PERESOURCE)(a2 + 1168));
  ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
  v159[1] = LfsQueryLastLsn(*(_QWORD *)(a2 + 232));
LABEL_48:
  if ( QuadPart )
  {
    if ( (__int64)QuadPart < LastLsn )
      LastLsn = (__int64)QuadPart;
    v133 = LastLsn;
  }
  v159[0] = *(unsigned int *)(a2 + 4892);
  v159[9] = *(_QWORD *)(a2 + 1320);
  v159[10] = *(unsigned int *)(a2 + 356);
  v159[11] = *(_QWORD *)(a2 + 1944);
  v159[12] = *(_QWORD *)(a2 + 1952);
  v134 = *(_QWORD *)(a2 + 40);
  if ( v134 )
  {
    v96 = v136;
    *(_QWORD *)(a2 + 1936) = v136;
    v159[8] = v96;
  }
  *(_QWORD *)(a2 + 824) = LastLsn;
  *(_QWORD *)(a2 + 1056) = LastLsn;
  v159[13] = LastLsn;
  LfsWriteRestartArea(*(_QWORD *)(a2 + 232), 0x70u, (__int64)v159, v120, (unsigned __int64 *)(a2 + 824));
  if ( (Context1[4] & 0x200LL) != 0 )
    _InterlockedExchange64((volatile __int64 *)(a2 + 7392), qword_140095A90);
  v33 = a4;
  if ( a4 )
  {
    *(_DWORD *)(a2 + 4856) = *(_DWORD *)(a2 + 4852);
    *(_DWORD *)(a2 + 4860) = 0;
    *(_QWORD *)(a2 + 1336) = 0;
    *(_QWORD *)(a2 + 1056) = *(_QWORD *)(a2 + 824);
    LfsResetUndoTotal(*(_QWORD *)(a2 + 232), 2, 8304);
    *(_DWORD *)(a2 + 5360) = 32;
  }
  *(_QWORD *)(a2 + 1304) = LfsQueryLastLsn(*(_QWORD *)(a2 + 232));
  v35 = 0;
  v36 = v107;
LABEL_257:
  if ( v109 )
    NtfsFreeRestartTable((PERESOURCE)Resource);
  if ( v36 )
    ExReleaseResourceLite((PERESOURCE)(a2 + 832));
  if ( v35 )
  {
    ExReleaseResourceLite((PERESOURCE)(a2 + 1168));
    ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  if ( Context1[7] )
  {
    ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1064), 1u);
    NtfsFreeRestartTableIndex((__int64)Context1, a2 + 1064, Context1[7]);
    ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
    Context1[7] = 0;
  }
  if ( v110 )
    NtfsReleaseAllFiles(Context1, a2, 6);
  v97 = v108;
  v98 = 0;
  if ( v108 )
  {
    if ( v33 )
    {
      ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1064), 1u);
      *(_BYTE *)(a2 + 1281) = 0;
      ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
    }
    NtfsReleaseVcb((__int64)Context1, a2);
    v98 = 0;
    v97 = 0;
    v108 = 0;
  }
  v99 = v134;
  if ( !a3 && (!v134 || v33) )
  {
    NtfsReleaseCheckpointSynchronization(0, a2, 19);
    v98 = 0;
  }
  if ( v111 )
    KeSetPriorityThread(KeGetCurrentThread(), Priority);
  if ( v33 )
  {
    if ( (Microsoft_Windows_NtfsEnableBits & 0x1000000) == 0 )
      goto LABEL_277;
    v104 = NTFS_ETW_CLEAN_CHECKPOINT_COMPLETE;
  }
  else
  {
    if ( (Microsoft_Windows_NtfsEnableBits & 0x800000) == 0 )
      goto LABEL_277;
    v104 = NTFS_ETW_PERIODIC_CHECKPOINT_COMPLETE;
  }
  LODWORD(Timeout) = v117;
  McTemplateK0pq_EtwWriteTransfer(v98, (const EVENT_DESCRIPTOR *)v104, (const GUID *)v153, v34, (__int64)Timeout);
LABEL_277:
  IoClearActivityIdThread(v139);
  if ( a3 )
    goto LABEL_282;
  if ( !v97 )
  {
    v97 = NtfsAcquireSharedVcb((__int64)Context1, a2, 0);
    v108 = v97;
  }
  if ( v97 && (*(_DWORD *)(a2 + 4) & 0x21) == 1 )
  {
LABEL_282:
    v100 = IoSetActivityIdThread(v153);
    NtfsFreeRecentlyDeallocated(Context1, a2, &v128, 0);
    IoClearActivityIdThread(v100);
    v97 = v108;
  }
  if ( v97 )
  {
    NtfsReleaseVcb((__int64)Context1, a2);
    v108 = 0;
  }
  if ( !v33 && v99 && !a3 )
    NtfsTrimUsnJournal((__int64)Context1, *(_QWORD *)(a2 + 40), 0, 0);
}

```

## disassembly

```asm
0x1401cfc18  mov     [rsp+arg_18], r9b
0x1401cfc1d  mov     [rsp+arg_10], r8b
0x1401cfc22  push    rbx
0x1401cfc23  push    rsi
0x1401cfc24  push    rdi
0x1401cfc25  push    r12
0x1401cfc27  push    r13
0x1401cfc29  push    r14
0x1401cfc2b  push    r15
0x1401cfc2d  sub     rsp, 470h
0x1401cfc34  mov     rax, cs:__security_cookie
0x1401cfc3b  xor     rax, rsp
0x1401cfc3e  mov     [rsp+4A8h+var_48], rax
0x1401cfc46  mov     bl, r9b
0x1401cfc49  mov     r14, rdx
0x1401cfc4c  mov     r13, rcx
0x1401cfc4f  mov     [rsp+4A8h+var_360], rcx
0x1401cfc57  mov     [rsp+4A8h+var_398], rdx
0x1401cfc5f  xor     edx, edx; Val
0x1401cfc61  lea     r8d, [rdx+70h]; Size
0x1401cfc65  lea     rcx, [rsp+4A8h+var_108]; void *
0x1401cfc6d  call    memset
0x1401cfc72  mov     edi, 0E0h
0x1401cfc77  mov     r8d, edi; Size
0x1401cfc7a  xor     edx, edx; Val
0x1401cfc7c  lea     rcx, [rsp+4A8h+Resource]; void *
0x1401cfc84  call    memset
0x1401cfc89  mov     r8d, edi; Size
0x1401cfc8c  xor     edx, edx; Val
0x1401cfc8e  lea     rcx, [rsp+4A8h+var_318]; void *
0x1401cfc96  call    memset
0x1401cfc9b  xor     esi, esi
0x1401cfc9d  mov     [rsp+4A8h+var_3E0], rsi
0x1401cfca5  mov     [rsp+4A8h+var_437], sil
0x1401cfcaa  mov     [rsp+4A8h+var_436], sil
0x1401cfcaf  mov     r12d, esi
0x1401cfcb2  mov     [rsp+4A8h+var_430], esi
0x1401cfcb6  mov     [rsp+4A8h+var_42C], si
0x1401cfcbb  mov     [rsp+4A8h+var_420], esi
0x1401cfcc2  xorps   xmm0, xmm0
0x1401cfcc5  xor     eax, eax
0x1401cfcc7  movups  [rsp+4A8h+var_158], xmm0
0x1401cfccf  mov     [rsp+4A8h+var_148], rax
0x1401cfcd7  test    dword ptr [r14+4], 2000000h
0x1401cfcdf  jnz     loc_1401D1AB1
0x1401cfce5  mov     [rsp+4A8h+P], rsi
0x1401cfced  mov     qword ptr [rsp+4A8h+FileOffset], rsi
0x1401cfcf5  mov     [rsp+4A8h+var_390], rax
0x1401cfcfd  mov     [rsp+4A8h+var_3F0], rsi
0x1401cfd05  mov     rdi, qword ptr cs:NtfsLarge0
0x1401cfd0c  mov     [rsp+4A8h+Priority], 10h
0x1401cfd17  mov     [rsp+4A8h+var_3B0], rsi
0x1401cfd1f  mov     [rsp+4A8h+var_40C], esi
0x1401cfd26  mov     [rsp+4A8h+var_3A0], rsi
0x1401cfd2e  mov     [rsp+4A8h+var_435], sil
0x1401cfd33  mov     [rsp+4A8h+var_438], sil
0x1401cfd38  mov     [rsp+4A8h+var_434], sil
0x1401cfd3d  mov     [rsp+4A8h+var_433], sil
0x1401cfd42  mov     [rsp+4A8h+var_432], sil
0x1401cfd47  mov     [rsp+4A8h+var_388], rsi
0x1401cfd4f  lea     r15d, [rsi+1]
0x1401cfd53  test    bl, bl
0x1401cfd55  jz      loc_1401D1B8A
0x1401cfd5b  cmp     [rsp+4A8h+arg_10], sil
0x1401cfd63  jz      loc_1401D1AD5
0x1401cfd69  mov     esi, 100000h
0x1401cfd6e  mov     [rsp+4A8h+var_410], 0
0x1401cfd79  test    bl, bl
0x1401cfd7b  jnz     short loc_1401CFD96
0x1401cfd7d  mov     eax, [r13+10h]
0x1401cfd81  bt      rax, 9
0x1401cfd86  jnb     short loc_1401CFD96
0x1401cfd88  mov     eax, cs:NtfsLWWaitLogThreshold
0x1401cfd8e  test    eax, eax
0x1401cfd90  jnz     loc_1401D0FAC
0x1401cfd96  xor     edx, edx; Val
0x1401cfd98  lea     r8d, [rdx+70h]; Size
0x1401cfd9c  lea     rcx, [rsp+4A8h+var_108]; void *
0x1401cfda4  call    memset
0x1401cfda9  xor     edx, edx; Val
0x1401cfdab  mov     r8d, 0E0h; Size
0x1401cfdb1  lea     rcx, [rsp+4A8h+Resource]; void *
0x1401cfdb9  call    memset
0x1401cfdbe  xor     eax, eax
0x1401cfdc0  cmp     [rsp+4A8h+arg_10], al
0x1401cfdc7  jnz     loc_1401D109B
0x1401cfdcd  mov     rax, 0FFFFF78000000320h
0x1401cfdd7  mov     rax, [rax]
0x1401cfdda  mov     [rsp+4A8h+var_368], rax
0x1401cfde2  xor     ebx, ebx
0x1401cfde4  test    r13, r13
0x1401cfde7  jz      loc_1401D0F8B
0x1401cfded  mov     eax, [r13+10h]
0x1401cfdf1  test    rsi, rax
0x1401cfdf4  jz      loc_1401D0F8B
0x1401cfdfa  test    r13, r13
0x1401cfdfd  jz      short loc_1401CFE0C
0x1401cfdff  mov     rcx, [r13+78h]
0x1401cfe03  test    rcx, rcx
0x1401cfe06  jnz     loc_1401D0F57
0x1401cfe0c  call    cs:__imp_IoGetActivityIdThread
0x1401cfe13  nop     dword ptr [rax+rax+00h]
0x1401cfe18  mov     rcx, rax
0x1401cfe1b  test    rax, rax
0x1401cfe1e  jnz     loc_1401D100A
0x1401cfe24  mov     qword ptr [rsp+4A8h+var_158], rbx
0x1401cfe2c  mov     rcx, rbx
0x1401cfe2f  call    cs:__imp_IoSetActivityIdThread
0x1401cfe36  nop     dword ptr [rax+rax+00h]
0x1401cfe3b  mov     [rsp+4A8h+var_388], rax
0x1401cfe43  mov     al, byte ptr cs:Microsoft_Windows_NtfsEnableBits+2
0x1401cfe49  test    al, al
0x1401cfe4b  js      loc_1401D110D
0x1401cfe51  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, r15b
0x1401cfe58  jnz     loc_1401D110D
0x1401cfe5e  mov     rdx, [r14+28h]
0x1401cfe62  test    rdx, rdx
0x1401cfe65  jz      loc_1401D09B4
0x1401cfe6b  mov     r8b, r15b
0x1401cfe6e  call    NtfsAcquireResourceShared
0x1401cfe73  lea     rbx, [r14+7C8h]
0x1401cfe7a  mov     rcx, rbx; FastMutex
0x1401cfe7d  call    cs:__imp_ExAcquireFastMutex
0x1401cfe84  nop     dword ptr [rax+rax+00h]
0x1401cfe89  lea     rax, [r14+7B8h]
0x1401cfe90  mov     rcx, [rax]
0x1401cfe93  cmp     rcx, rax
0x1401cfe96  jz      loc_1401D103E
0x1401cfe9c  mov     rax, [rcx-18h]
0x1401cfea0  mov     rax, [rax+120h]
0x1401cfea7  mov     [rsp+4A8h+var_3A0], rax
0x1401cfeaf  mov     [rsp+4A8h+var_348], rax
0x1401cfeb7  mov     rcx, rbx; FastMutex
0x1401cfeba  call    cs:__imp_ExReleaseFastMutex
0x1401cfec1  nop     dword ptr [rax+rax+00h]
0x1401cfec6  mov     rcx, [r14+28h]
0x1401cfeca  mov     eax, 702h
0x1401cfecf  cmp     ax, [rcx]
0x1401cfed2  jz      loc_1401D09A0
0x1401cfed8  mov     rcx, [rcx+8]
0x1401cfedc  jmp     loc_1401D09A8
0x1401cfee1  and     dword ptr [r14+23Ch], 0FFFFFFDFh
0x1401cfee9  mov     eax, [rsp+4A8h+var_410]
0x1401cfef0  test    eax, eax
0x1401cfef2  jnz     loc_1401D034B
0x1401cfef8  lea     r12, [r14+340h]
0x1401cfeff  mov     rcx, r12
0x1401cff02  call    NtfsGetFirstRestartTable
0x1401cff07  mov     rsi, rax
0x1401cff0a  test    rsi, rsi
0x1401cff0d  jz      loc_1401D0040
0x1401cff13  mov     cl, r11b
0x1401cff16  mov     [rsp+4A8h+var_428], cl
0x1401cff1d  cmp     [rsi+0Ch], r11b
0x1401cff21  jz      short loc_1401CFF8E
0x1401cff23  cmp     dword ptr [r14+131Ch], 2
0x1401cff2b  jb      loc_1401CFFC0
0x1401cff31  mov     [rsp+4A8h+var_3D8], rsi
0x1401cff39  mov     r11, [r14+410h]
0x1401cff40  movzx   r9d, word ptr [r11]
0x1401cff44  add     rsi, r9
0x1401cff47  mov     r8, rsi
0x1401cff4a  mov     [rsp+4A8h+var_3D8], rsi
0x1401cff52  mov     r10, rsi
0x1401cff55  mov     edx, r8d
0x1401cff58  sub     edx, [r14+410h]
0x1401cff5f  movzx   ecx, word ptr [r11+2]
0x1401cff64  imul    ecx, r9d
0x1401cff68  add     ecx, 18h
0x1401cff6b  cmp     edx, ecx
0x1401cff6d  jnb     short loc_1401CFFB8
0x1401cff6f  cmp     dword ptr [r8], 0FFFFFFFFh
0x1401cff73  jz      short loc_1401CFF86
0x1401cff75  lea     rsi, [rsi+r9]
0x1401cff79  mov     r8, rsi
0x1401cff7c  mov     [rsp+4A8h+var_3D8], rsi
0x1401cff84  jmp     short loc_1401CFF52
0x1401cff86  xor     r11d, r11d
0x1401cff89  jmp     loc_1401CFF0A
0x1401cff8e  mov     rax, [rsi+20h]
0x1401cff92  cmp     [rax+18h], r11
0x1401cff96  jnz     short loc_1401CFF23
0x1401cff98  mov     r8, rsi
0x1401cff9b  mov     rdx, r14
0x1401cff9e  mov     rcx, r13
0x1401cffa1  call    NtfsFreeAttributeEntry
0x1401cffa6  mov     cl, r15b
0x1401cffa9  mov     [rsp+4A8h+var_428], cl
0x1401cffb0  xor     r11d, r11d
0x1401cffb3  jmp     loc_1401CFF23
0x1401cffb8  xor     r11d, r11d
0x1401cffbb  mov     esi, r11d
0x1401cffbe  jmp     short loc_1401CFF89
0x1401cffc0  test    cl, cl
0x1401cffc2  jnz     loc_1401CFF31
0x1401cffc8  mov     rax, [rsi+20h]
0x1401cffcc  cmp     [rax+20h], r11w
0x1401cffd1  jz      loc_1401CFF31
0x1401cffd7  movzx   eax, word ptr [rax+10h]
0x1401cffdb  mov     r9, qword ptr [rsp+4A8h+FileOffset]
0x1401cffe3  mov     [r9], ax
0x1401cffe7  mov     rax, [rsi+20h]
0x1401cffeb  movzx   ecx, word ptr [rax+20h]
0x1401cffef  mov     [r9+2], cx
0x1401cfff4  mov     rdx, [rsi+20h]
0x1401cfff8  movzx   r8d, word ptr [rdx+20h]; Size
0x1401cfffd  lea     rcx, [r9+4]; void *
0x1401d0001  mov     rdx, [rdx+28h]; Src
0x1401d0005  call    memmove
0x1401d000a  mov     rdx, qword ptr [rsp+4A8h+FileOffset]
0x1401d0012  movzx   ecx, word ptr [rdx+2]
0x1401d0016  shr     rcx, 1
0x1401d0019  xor     eax, eax
0x1401d001b  mov     [rdx+rcx*2+4], ax
0x1401d0020  movzx   eax, word ptr [rdx+2]
0x1401d0024  add     rdx, 6
0x1401d0028  add     rdx, rax
0x1401d002b  mov     qword ptr [rsp+4A8h+FileOffset], rdx
0x1401d0033  mov     [rsp+4A8h+var_328], rdx
0x1401d003b  jmp     loc_1401CFF31
0x1401d0040  cmp     [rsp+4A8h+P], r11
0x1401d0048  jnz     loc_1401D1787
0x1401d004e  cmp     dword ptr [r14+131Ch], 2
0x1401d0056  jb      loc_1401D0220
0x1401d005c  mov     rcx, r12; Resource
0x1401d005f  call    cs:__imp_ExReleaseResourceLite
0x1401d0066  nop     dword ptr [rax+rax+00h]
0x1401d006b  xor     r12d, r12d
0x1401d006e  mov     [rsp+4A8h+var_437], r12b
0x1401d0073  mov     esi, r12d
0x1401d0076  mov     rdx, [rsp+4A8h+var_168]
0x1401d007e  cmp     [rdx+4], r12w
0x1401d0083  jnz     loc_1401D1802
0x1401d0089  mov     dl, r15b; Wait
0x1401d008c  lea     r12, [r14+428h]
0x1401d0093  mov     rcx, r12; Resource
0x1401d0096  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401d009d  nop     dword ptr [rax+rax+00h]
0x1401d00a2  mov     dl, r15b; Wait
0x1401d00a5  lea     rcx, [r14+490h]; Resource
0x1401d00ac  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401d00b3  nop     dword ptr [rax+rax+00h]
0x1401d00b8  mov     [rsp+4A8h+var_438], r15b
0x1401d00bd  mov     eax, [r14+23Ch]
0x1401d00c4  and     eax, 0FFFFFFFBh
0x1401d00c7  mov     [r14+23Ch], eax
0x1401d00ce  mov     rcx, [rsp+4A8h+var_3F0]
0x1401d00d6  xor     r8d, r8d
0x1401d00d9  test    rcx, rcx
0x1401d00dc  jnz     loc_1401D1884
0x1401d00e2  mov     rdx, [r14+4F8h]
0x1401d00e9  movzx   eax, word ptr [rdx+4]
0x1401d00ed  cmp     eax, esi
0x1401d00ef  jbe     loc_1401D02EB
0x1401d00f5  xor     esi, esi
0x1401d00f7  lea     rcx, [r14+490h]; Resource
0x1401d00fe  call    cs:__imp_ExReleaseResourceLite
0x1401d0105  nop     dword ptr [rax+rax+00h]
0x1401d010a  mov     rcx, r12; Resource
0x1401d010d  call    cs:__imp_ExReleaseResourceLite
0x1401d0114  nop     dword ptr [rax+rax+00h]
0x1401d0119  mov     [rsp+4A8h+var_438], sil
0x1401d011e  test    rdi, rdi
0x1401d0121  jnz     loc_1401D1902
0x1401d0127  mov     eax, [r14+131Ch]
0x1401d012e  mov     [rsp+4A8h+var_108], eax
0x1401d0135  mov     [rsp+4A8h+var_104], esi
0x1401d013c  mov     rax, [r14+528h]
0x1401d0143  mov     [rsp+4A8h+var_C0], rax
0x1401d014b  mov     eax, [r14+164h]
0x1401d0152  mov     [rsp+4A8h+var_B8], eax
0x1401d0159  mov     [rsp+4A8h+var_B4], esi
0x1401d0160  mov     rax, [r14+798h]
0x1401d0167  mov     [rsp+4A8h+var_B0], rax
0x1401d016f  mov     rax, [r14+7A0h]
0x1401d0176  mov     [rsp+4A8h+var_A8], rax
0x1401d017e  mov     rax, [r14+28h]
0x1401d0182  mov     [rsp+4A8h+var_3B0], rax
0x1401d018a  test    rax, rax
0x1401d018d  jnz     loc_1401D1916
0x1401d0193  lea     rdi, [r14+338h]
0x1401d019a  mov     [rdi], rbx
0x1401d019d  mov     [r14+420h], rbx
0x1401d01a4  mov     [rsp+4A8h+var_A0], rbx
0x1401d01ac  mov     [rsp+4A8h+Timeout], rdi
0x1401d01b1  mov     r9d, [rsp+4A8h+var_40C]
0x1401d01b9  lea     r8, [rsp+4A8h+var_108]
0x1401d01c1  mov     edx, 70h ; 'p'
0x1401d01c6  mov     rcx, [r14+0E8h]
0x1401d01cd  call    LfsWriteRestartArea
0x1401d01d2  mov     eax, [r13+10h]
0x1401d01d6  bt      rax, 9
0x1401d01db  jnb     short loc_1401D01EB
0x1401d01dd  mov     rax, cs:qword_140095A90
0x1401d01e4  xchg    rax, [r14+1CE0h]
0x1401d01eb  mov     sil, [rsp+4A8h+arg_18]
0x1401d01f3  xor     ebx, ebx
0x1401d01f5  test    sil, sil
0x1401d01f8  jnz     loc_1401D1932
0x1401d01fe  mov     rcx, [r14+0E8h]
  ... truncated ...
```
