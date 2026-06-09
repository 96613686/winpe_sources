# VidSchiOpenProcessAdapterInfo

- ea: `0x14011a2cc`
- end: `0x14011a83e`
- name: `VidSchiOpenProcessAdapterInfo`
- size: `1394`
- prototype: `__int64 __fastcall(struct _VIDSCH_PROCESS *, struct _VIDSCH_GLOBAL *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x140111370`

## callees

- `0x1400045ec`
- `0x140030ae0`
- `0x140031178`
- `0x140035bc8`
- `0x140039354`
- `0x14003a13c`
- `0x14003a1d0`
- `0x14003a354`
- `0x14011a2cc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14011a6bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011a6bb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14011a2f2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14011a2f2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011a319`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011a36b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011a4f9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011a319`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011a36b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011a4f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011a42d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011a494`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011a4dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011a42d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011a494`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011a4dc`
- `ntoskrnl!ExAllocatePool2` at `0x14011a33c`
- `ntoskrnl!ExAllocatePool2` at `0x14011a596`
- `ntoskrnl!ExAllocatePool2` at `0x14011a7ef`
- `ntoskrnl!ExAllocatePool2` at `0x14011a33c`
- `ntoskrnl!ExAllocatePool2` at `0x14011a596`
- `ntoskrnl!ExAllocatePool2` at `0x14011a7ef`
- `ntoskrnl!PcwCreateInstance` at `0x14011a70c`
- `ntoskrnl!PcwCreateInstance` at `0x14011a70c`
- `watchdog!WdLogSingleEntry0` at `0x14011a350`
- `watchdog!WdLogSingleEntry0` at `0x14011a3f1`
- `watchdog!WdLogSingleEntry0` at `0x14011a539`
- `watchdog!WdLogSingleEntry0` at `0x14011a728`
- `watchdog!WdLogSingleEntry0` at `0x14011a75f`
- `watchdog!WdLogSingleEntry0` at `0x14011a7a4`
- `watchdog!WdLogSingleEntry0` at `0x14011a823`
- `watchdog!WdLogSingleEntry0` at `0x14011a350`
- `watchdog!WdLogSingleEntry0` at `0x14011a3f1`
- `watchdog!WdLogSingleEntry0` at `0x14011a539`
- `watchdog!WdLogSingleEntry0` at `0x14011a728`
- `watchdog!WdLogSingleEntry0` at `0x14011a75f`
- `watchdog!WdLogSingleEntry0` at `0x14011a7a4`
- `watchdog!WdLogSingleEntry0` at `0x14011a823`

## string_xrefs

- `0x14011a54a`: `Failed to create name string for GpuPerformanceCounterSetEngine`
- `0x14011a76d`: `Failed to create name string for GpuPerformanceCounterSetEngine`
- `0x14011a73d`: `Failed to create GpuPerformanceCounterSetEngine`

## pseudocode

```c
__int64 __fastcall VidSchiOpenProcessAdapterInfo(struct _VIDSCH_PROCESS *a1, struct _VIDSCH_GLOBAL *a2)
{
  __int64 v2; // rbx
  char *v3; // r12
  _DWORD *v6; // rcx
  VIDSCH_PROCESS_ADAPTER_INFO *Pool2; // rax
  _QWORD *v9; // rcx
  unsigned int v10; // edx
  NTSTATUS v11; // r15d
  unsigned int k; // ebp
  void *v13; // rcx
  unsigned int m; // ebp
  __int64 v15; // rcx
  PVOID *v16; // rcx
  PVOID *v17; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rax
  VIDSCH_PROCESS_ADAPTER_INFO *v20; // rcx
  wchar_t *v21; // r13
  int v22; // ecx
  int v23; // r8d
  __int64 i; // rbp
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  __int64 v28; // rax
  _QWORD *v29; // rcx
  __int64 v30; // r9
  unsigned int v31; // r10d
  __int64 v32; // r15
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rcx
  wchar_t *v38; // r8
  __int64 v39; // rax
  __int64 v40; // rcx
  const void **v41; // rax
  int v42; // ecx
  int v43; // r8d
  const wchar_t *v44; // r9
  __int64 v45; // rax
  unsigned int j; // ebp
  PPCW_DATA Data; // [rsp+20h] [rbp-98h]
  __int64 v48; // [rsp+28h] [rbp-90h]
  __int64 v49; // [rsp+30h] [rbp-88h]
  __int64 v50; // [rsp+38h] [rbp-80h]
  struct _PCW_DATA v51; // [rsp+50h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-58h] BYREF

  v2 = *((unsigned int *)a2 + 1);
  v3 = (char *)a1 + 2664;
  ExAcquirePushLockExclusiveEx((char *)a1 + 2664, 0);
  v6 = *(_DWORD **)(*((_QWORD *)a1 + 4) + 8 * v2);
  if ( v6 )
  {
    ++*v6;
LABEL_3:
    ExReleasePushLockExclusiveEx(v3, 0);
    return 0;
  }
  Pool2 = (VIDSCH_PROCESS_ADAPTER_INFO *)ExAllocatePool2(64, 232, 845244758);
  if ( !Pool2 )
  {
    WdLogSingleEntry0(3);
    WdLogGlobalForLineNumber = 29004;
    ExReleasePushLockExclusiveEx(v3, 0);
    return 3221225495LL;
  }
  *(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2) = VIDSCH_PROCESS_ADAPTER_INFO::VIDSCH_PROCESS_ADAPTER_INFO(Pool2);
  **(_DWORD **)(*((_QWORD *)a1 + 4) + 8 * v2) = 1;
  v9 = (_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2) + 216LL);
  v9[1] = v9;
  *v9 = v9;
  v11 = VidSchiSetupKnownProcessBoost(a2, a1, *(struct VIDSCH_PROCESS_ADAPTER_INFO **)(*((_QWORD *)a1 + 4) + 8 * v2));
  if ( v11 >= 0 )
  {
    if ( NonPagedPoolZeroedArray<_VIDSCH_NODE_STATISTICS *,8,845244758>::AllocateElements(
           *(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2) + 8LL,
           *((unsigned int *)a2 + 23)) )
    {
      v21 = (wchar_t *)operator new[](520, 1265072196, 256);
      if ( v21 )
      {
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)i >= *((_DWORD *)a2 + 22) )
            goto LABEL_55;
          v25 = ExAllocatePool2(64, 224, 845244758);
          v26 = *(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2);
          v27 = *(__int64 **)(v26 + 8);
          if ( (unsigned int)i < *(_DWORD *)(v26 + 80) )
            v27 += i;
          *v27 = v25;
          v28 = *(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2);
          v29 = (_QWORD *)(*(_QWORD *)(v28 + 8) + 8 * i);
          if ( (unsigned int)i >= *(_DWORD *)(v28 + 80) )
            v29 = *(_QWORD **)(v28 + 8);
          if ( !*v29 )
            break;
          v30 = *((_QWORD *)a2 + 97);
          v31 = *((_DWORD *)a2 + 212);
          v32 = *((_QWORD *)a2 + 2);
          v33 = v30 + 8 * i;
          if ( (unsigned int)i >= v31 )
            v33 = *((_QWORD *)a2 + 97);
          v34 = *(_QWORD *)(352LL * *(unsigned __int16 *)(*(_QWORD *)v33 + 6LL) + *(_QWORD *)(v32 + 3104) + 32);
          v35 = *((_QWORD *)a2 + 97);
          if ( (unsigned int)i < v31 )
            v35 = v30 + 8 * i;
          v36 = 74LL * *(unsigned __int16 *)(*(_QWORD *)v35 + 8LL);
          DestinationString = 0;
          v37 = *(int *)(v36 + v34);
          if ( (_DWORD)v37 )
            v38 = off_14005B1F0[v37];
          else
            v38 = (wchar_t *)(v36 + v34 + 4);
          v39 = v30;
          if ( (unsigned int)i < v31 )
          {
            v39 = v30 + 8 * i;
            v30 = v39;
          }
          LODWORD(v50) = *(unsigned __int16 *)(*(_QWORD *)v39 + 8LL);
          LODWORD(v49) = *(unsigned __int16 *)(*(_QWORD *)v30 + 6LL);
          LODWORD(v48) = *(_DWORD *)(v32 + 412);
          LODWORD(Data) = *(_DWORD *)(v32 + 416);
          v11 = RtlStringCbPrintfW(
                  v21,
                  0x208u,
                  L"pid_%Iu_luid_0x%08X_0x%08X_phys_%u_eng_%u_engtype_%s",
                  *((_QWORD *)a1 + 330),
                  Data,
                  v48,
                  v49,
                  v50,
                  v38);
          if ( v11 < 0 )
          {
            WdLogSingleEntry0(1);
            v42 = 0;
            v44 = L"Failed to create name string for GpuPerformanceCounterSetEngine";
            v45 = 29069;
            goto LABEL_53;
          }
          RtlInitUnicodeString(&DestinationString, v21);
          v40 = *(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2);
          v41 = *(const void ***)(v40 + 8);
          if ( (unsigned int)i < *(_DWORD *)(v40 + 80) )
            v41 += i;
          v51.Data = *v41;
          v51.Size = 224;
          v11 = PcwCreateInstance(
                  (PPCW_INSTANCE *)v51.Data + 27,
                  GpuPerformanceCounterSetEngine,
                  &DestinationString,
                  1u,
                  &v51);
          if ( v11 < 0 )
          {
            WdLogSingleEntry0(1);
            v44 = L"Failed to create GpuPerformanceCounterSetEngine";
            v45 = 29077;
LABEL_53:
            WdLogGlobalForLineNumber = v45;
            DxgkLogInternalTriageEvent(v42, 0x40000, v43, (_DWORD)v44, v45, 0, 0, 0);
            goto LABEL_55;
          }
        }
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 29047;
        v11 = -1073741801;
LABEL_55:
        operator delete(v21);
        if ( v11 >= 0 )
        {
          for ( j = 0; j < *((_DWORD *)a2 + 12); ++j )
          {
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2) + 8LL * j + 88) = ExAllocatePool2(64, 12, 845244758);
            if ( !*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2) + 8LL * j + 88) )
            {
              WdLogSingleEntry0(3);
              WdLogGlobalForLineNumber = 29101;
              goto LABEL_9;
            }
          }
          goto LABEL_3;
        }
        goto LABEL_10;
      }
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 29034;
      DxgkLogInternalTriageEvent(
        v22,
        0x40000,
        v23,
        (unsigned int)L"Failed to create name string for GpuPerformanceCounterSetEngine",
        29034,
        0,
        0,
        0);
    }
    else
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 29023;
    }
LABEL_9:
    v11 = -1073741801;
  }
LABEL_10:
  for ( k = 0; k < *((_DWORD *)a2 + 12); ++k )
  {
    v13 = *(void **)(*(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2) + 8LL * k + 88);
    if ( v13 )
    {
      ExFreePoolWithTag(v13, 0);
      *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2) + 8LL * k + 88) = 0;
    }
  }
  if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2) + 8LL) )
  {
    for ( m = 0; m < *((_DWORD *)a2 + 22); ++m )
    {
      v15 = *(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2);
      v10 = *(_DWORD *)(v15 + 80);
      v16 = *(PVOID **)(v15 + 8);
      v17 = &v16[m];
      if ( m >= v10 )
        v17 = v16;
      if ( *v17 )
      {
        if ( m < v10 )
          v16 += m;
        ExFreePoolWithTag(*v16, 0);
        v18 = *(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2);
        v19 = *(_QWORD **)(v18 + 8);
        if ( m < *(_DWORD *)(v18 + 80) )
          v19 += m;
        *v19 = 0;
      }
    }
  }
  v20 = *(VIDSCH_PROCESS_ADAPTER_INFO **)(*((_QWORD *)a1 + 4) + 8 * v2);
  if ( v20 )
  {
    VIDSCH_PROCESS_ADAPTER_INFO::`scalar deleting destructor'(v20, v10);
    ExFreePoolWithTag(*(PVOID *)(*((_QWORD *)a1 + 4) + 8 * v2), 0);
    *(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * v2) = 0;
  }
  ExReleasePushLockExclusiveEx((char *)a1 + 2664, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14011a2cc  push    rbx
0x14011a2ce  push    rbp
0x14011a2cf  push    rsi
0x14011a2d0  push    rdi
0x14011a2d1  push    r12
0x14011a2d3  push    r13
0x14011a2d5  push    r14
0x14011a2d7  push    r15
0x14011a2d9  sub     rsp, 78h
0x14011a2dd  mov     ebx, [rdx+4]
0x14011a2e0  lea     r12, [rcx+0A68h]
0x14011a2e7  mov     r14, rdx
0x14011a2ea  mov     rdi, rcx
0x14011a2ed  mov     rcx, r12
0x14011a2f0  xor     edx, edx
0x14011a2f2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14011a2f9  nop     dword ptr [rax+rax+00h]
0x14011a2fe  mov     rax, [rdi+20h]
0x14011a302  xor     r13d, r13d
0x14011a305  mov     rcx, [rax+rbx*8]
0x14011a309  test    rcx, rcx
0x14011a30c  jz      short loc_14011A32C
0x14011a30e  lea     esi, [r13+1]
0x14011a312  add     [rcx], esi
0x14011a314  xor     edx, edx
0x14011a316  mov     rcx, r12
0x14011a319  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14011a320  nop     dword ptr [rax+rax+00h]
0x14011a325  xor     eax, eax
0x14011a327  jmp     loc_14011A508
0x14011a32c  mov     edx, 0E8h
0x14011a331  mov     ecx, 40h ; '@'
0x14011a336  mov     r8d, 32616956h
0x14011a33c  call    cs:__imp_ExAllocatePool2
0x14011a343  nop     dword ptr [rax+rax+00h]
0x14011a348  test    rax, rax
0x14011a34b  jnz     short loc_14011A381
0x14011a34d  lea     ecx, [rax+3]
0x14011a350  call    cs:__imp_WdLogSingleEntry0
0x14011a357  nop     dword ptr [rax+rax+00h]
0x14011a35c  xor     edx, edx
0x14011a35e  mov     cs:WdLogGlobalForLineNumber, 714Ch
0x14011a368  mov     rcx, r12
0x14011a36b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14011a372  nop     dword ptr [rax+rax+00h]
0x14011a377  mov     eax, 0C0000017h
0x14011a37c  jmp     loc_14011A508
0x14011a381  mov     rcx, rax; this
0x14011a384  call    ??0VIDSCH_PROCESS_ADAPTER_INFO@@QEAA@XZ; VIDSCH_PROCESS_ADAPTER_INFO::VIDSCH_PROCESS_ADAPTER_INFO(void)
0x14011a389  mov     rcx, [rdi+20h]
0x14011a38d  mov     esi, 1
0x14011a392  mov     rdx, rdi; struct _VIDSCH_PROCESS *
0x14011a395  mov     [rcx+rbx*8], rax
0x14011a399  mov     rax, [rdi+20h]
0x14011a39d  mov     rcx, [rax+rbx*8]
0x14011a3a1  mov     [rcx], esi
0x14011a3a3  mov     rax, [rdi+20h]
0x14011a3a7  mov     rcx, [rax+rbx*8]
0x14011a3ab  add     rcx, 0D8h
0x14011a3b2  mov     [rcx+8], rcx
0x14011a3b6  mov     [rcx], rcx
0x14011a3b9  mov     rcx, r14; struct _VIDSCH_GLOBAL *
0x14011a3bc  mov     r8, [rdi+20h]
0x14011a3c0  mov     r8, [r8+rbx*8]; struct VIDSCH_PROCESS_ADAPTER_INFO *
0x14011a3c4  call    ?VidSchiSetupKnownProcessBoost@@YAJPEAU_VIDSCH_GLOBAL@@PEAU_VIDSCH_PROCESS@@PEAUVIDSCH_PROCESS_ADAPTER_INFO@@@Z; VidSchiSetupKnownProcessBoost(_VIDSCH_GLOBAL *,_VIDSCH_PROCESS *,VIDSCH_PROCESS_ADAPTER_INFO *)
0x14011a3c9  mov     r15d, eax
0x14011a3cc  test    eax, eax
0x14011a3ce  js      short loc_14011A40D
0x14011a3d0  mov     rcx, [rdi+20h]
0x14011a3d4  mov     edx, [r14+5Ch]
0x14011a3d8  mov     rcx, [rcx+rbx*8]
0x14011a3dc  add     rcx, 8
0x14011a3e0  call    ?AllocateElements@?$NonPagedPoolZeroedArray@PEAU_VIDSCH_NODE_STATISTICS@@$07$0DCGBGJFG@@@QEAAPEAPEAU_VIDSCH_NODE_STATISTICS@@I@Z; NonPagedPoolZeroedArray<_VIDSCH_NODE_STATISTICS *,8,845244758>::AllocateElements(uint)
0x14011a3e5  test    rax, rax
0x14011a3e8  jnz     loc_14011A51A
0x14011a3ee  lea     ecx, [rsi+2]
0x14011a3f1  call    cs:__imp_WdLogSingleEntry0
0x14011a3f8  nop     dword ptr [rax+rax+00h]
0x14011a3fd  mov     cs:WdLogGlobalForLineNumber, 715Fh
0x14011a407  mov     r15d, 0C0000017h
0x14011a40d  mov     ebp, r13d
0x14011a410  cmp     [r14+30h], r13d
0x14011a414  jbe     short loc_14011A44E
0x14011a416  mov     rax, [rdi+20h]
0x14011a41a  mov     r12d, ebp
0x14011a41d  mov     rcx, [rax+rbx*8]
0x14011a421  mov     rcx, [rcx+r12*8+58h]; P
0x14011a426  test    rcx, rcx
0x14011a429  jz      short loc_14011A446
0x14011a42b  xor     edx, edx; Tag
0x14011a42d  call    cs:__imp_ExFreePoolWithTag
0x14011a434  nop     dword ptr [rax+rax+00h]
0x14011a439  mov     rax, [rdi+20h]
0x14011a43d  mov     rcx, [rax+rbx*8]
0x14011a441  mov     [rcx+r12*8+58h], r13
0x14011a446  add     ebp, esi
0x14011a448  cmp     ebp, [r14+30h]
0x14011a44c  jb      short loc_14011A416
0x14011a44e  mov     rax, [rdi+20h]
0x14011a452  mov     rcx, [rax+rbx*8]
0x14011a456  cmp     [rcx+8], r13
0x14011a45a  jz      short loc_14011A4C0
0x14011a45c  mov     ebp, r13d
0x14011a45f  cmp     [r14+58h], r13d
0x14011a463  jbe     short loc_14011A4C0
0x14011a465  mov     rax, [rdi+20h]
0x14011a469  mov     r12d, ebp
0x14011a46c  mov     rcx, [rax+rbx*8]
0x14011a470  mov     edx, [rcx+50h]
0x14011a473  mov     rcx, [rcx+8]
0x14011a477  lea     rax, [rcx+r12*8]
0x14011a47b  cmp     ebp, edx
0x14011a47d  jb      short loc_14011A482
0x14011a47f  mov     rax, rcx
0x14011a482  cmp     [rax], r13
0x14011a485  jz      short loc_14011A4B8
0x14011a487  cmp     ebp, edx
0x14011a489  jnb     short loc_14011A48F
0x14011a48b  lea     rcx, [rcx+r12*8]
0x14011a48f  mov     rcx, [rcx]; P
0x14011a492  xor     edx, edx; Tag
0x14011a494  call    cs:__imp_ExFreePoolWithTag
0x14011a49b  nop     dword ptr [rax+rax+00h]
0x14011a4a0  mov     rax, [rdi+20h]
0x14011a4a4  mov     rcx, [rax+rbx*8]
0x14011a4a8  mov     rax, [rcx+8]
0x14011a4ac  cmp     ebp, [rcx+50h]
0x14011a4af  jnb     short loc_14011A4B5
0x14011a4b1  lea     rax, [rax+r12*8]
0x14011a4b5  mov     [rax], r13
0x14011a4b8  add     ebp, esi
0x14011a4ba  cmp     ebp, [r14+58h]
0x14011a4be  jb      short loc_14011A465
0x14011a4c0  mov     rax, [rdi+20h]
0x14011a4c4  mov     rcx, [rax+rbx*8]; this
0x14011a4c8  test    rcx, rcx
0x14011a4cb  jz      short loc_14011A4F0
0x14011a4cd  call    ??_GVIDSCH_PROCESS_ADAPTER_INFO@@QEAAPEAXI@Z; VIDSCH_PROCESS_ADAPTER_INFO::`scalar deleting destructor'(uint)
0x14011a4d2  mov     rcx, [rdi+20h]
0x14011a4d6  xor     edx, edx; Tag
0x14011a4d8  mov     rcx, [rcx+rbx*8]; P
0x14011a4dc  call    cs:__imp_ExFreePoolWithTag
0x14011a4e3  nop     dword ptr [rax+rax+00h]
0x14011a4e8  mov     rax, [rdi+20h]
0x14011a4ec  mov     [rax+rbx*8], r13
0x14011a4f0  xor     edx, edx
0x14011a4f2  lea     rcx, [rdi+0A68h]
0x14011a4f9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14011a500  nop     dword ptr [rax+rax+00h]
0x14011a505  mov     eax, r15d
0x14011a508  add     rsp, 78h
0x14011a50c  pop     r15
0x14011a50e  pop     r14
0x14011a510  pop     r13
0x14011a512  pop     r12
0x14011a514  pop     rdi
0x14011a515  pop     rsi
0x14011a516  pop     rbp
0x14011a517  pop     rbx
0x14011a518  retn
0x14011a51a  mov     edx, 4B677844h
0x14011a51f  mov     ecx, 208h
0x14011a524  mov     r8d, 100h
0x14011a52a  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011a52f  mov     r13, rax
0x14011a532  test    rax, rax
0x14011a535  jnz     short loc_14011A57A
0x14011a537  mov     ecx, esi
0x14011a539  call    cs:__imp_WdLogSingleEntry0
0x14011a540  nop     dword ptr [rax+rax+00h]
0x14011a545  mov     [rsp+0B8h+var_80], r13
0x14011a54a  lea     r9, aFailedToCreate_25; "Failed to create name string for GpuPer"...
0x14011a551  mov     eax, 716Ah
0x14011a556  mov     [rsp+0B8h+var_88], r13
0x14011a55b  mov     [rsp+0B8h+var_90], r13
0x14011a560  mov     edx, 40000h
0x14011a565  mov     cs:WdLogGlobalForLineNumber, eax
0x14011a56b  mov     [rsp+0B8h+Data], rax
0x14011a570  call    DxgkLogInternalTriageEvent
0x14011a575  jmp     loc_14011A407
0x14011a57a  xor     ebp, ebp
0x14011a57c  cmp     ebp, [r14+58h]
0x14011a580  jnb     loc_14011A7C0
0x14011a586  mov     edx, 0E0h
0x14011a58b  mov     ecx, 40h ; '@'
0x14011a590  mov     r8d, 32616956h
0x14011a596  call    cs:__imp_ExAllocatePool2
0x14011a59d  nop     dword ptr [rax+rax+00h]
0x14011a5a2  mov     rcx, [rdi+20h]
0x14011a5a6  mov     rdx, [rcx+rbx*8]
0x14011a5aa  mov     rcx, [rdx+8]
0x14011a5ae  cmp     ebp, [rdx+50h]
0x14011a5b1  jnb     short loc_14011A5B7
0x14011a5b3  lea     rcx, [rcx+rbp*8]
0x14011a5b7  mov     [rcx], rax
0x14011a5ba  mov     rax, [rdi+20h]
0x14011a5be  mov     rax, [rax+rbx*8]
0x14011a5c2  mov     rdx, [rax+8]
0x14011a5c6  cmp     ebp, [rax+50h]
0x14011a5c9  lea     rcx, [rdx+rbp*8]
0x14011a5cd  cmovnb  rcx, rdx
0x14011a5d1  cmp     qword ptr [rcx], 0
0x14011a5d5  jz      loc_14011A79F
0x14011a5db  mov     r9, [r14+308h]
0x14011a5e2  xorps   xmm0, xmm0
0x14011a5e5  mov     r10d, [r14+350h]
0x14011a5ec  cmp     ebp, r10d
0x14011a5ef  mov     r15, [r14+10h]
0x14011a5f3  lea     r11, [r9+rbp*8]
0x14011a5f7  mov     rax, r11
0x14011a5fa  cmovnb  rax, r9
0x14011a5fe  mov     rax, [rax]
0x14011a601  movzx   ecx, word ptr [rax+6]
0x14011a605  mov     rax, [r15+0C20h]
0x14011a60c  imul    rdx, rcx, 160h
0x14011a613  cmp     ebp, r10d
0x14011a616  mov     r8, [rdx+rax+20h]
0x14011a61b  mov     rax, r9
0x14011a61e  cmovb   rax, r11
0x14011a622  mov     rax, [rax]
0x14011a625  movzx   ecx, word ptr [rax+8]
0x14011a629  imul    rax, rcx, 4Ah ; 'J'
0x14011a62d  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x14011a632  movsxd  rcx, dword ptr [rax+r8]
0x14011a636  test    ecx, ecx
0x14011a638  jz      short loc_14011A647
0x14011a63a  lea     r8, off_14005B1F0; "Other"
0x14011a641  mov     r8, [r8+rcx*8]
0x14011a645  jmp     short loc_14011A64E
0x14011a647  add     r8, 4
0x14011a64b  add     r8, rax
0x14011a64e  mov     [rsp+0B8h+var_78], r8
0x14011a653  mov     rax, r9
0x14011a656  cmp     ebp, r10d
0x14011a659  lea     r8, aPidIuLuid0x08x; "pid_%Iu_luid_0x%08X_0x%08X_phys_%u_eng_"...
0x14011a660  cmovb   rax, r11
0x14011a664  cmovb   r9, r11
0x14011a668  mov     rax, [rax]
0x14011a66b  movzx   edx, word ptr [rax+8]
0x14011a66f  mov     rax, [r9]
0x14011a672  mov     r9, [rdi+0A50h]
0x14011a679  mov     dword ptr [rsp+0B8h+var_80], edx
0x14011a67d  mov     edx, 208h; cbDest
0x14011a682  movzx   ecx, word ptr [rax+6]
0x14011a686  mov     eax, [r15+19Ch]
0x14011a68d  mov     dword ptr [rsp+0B8h+var_88], ecx
0x14011a691  mov     rcx, r13; pszDest
0x14011a694  mov     dword ptr [rsp+0B8h+var_90], eax
0x14011a698  mov     eax, [r15+1A0h]
0x14011a69f  mov     dword ptr [rsp+0B8h+Data], eax
0x14011a6a3  call    RtlStringCbPrintfW
0x14011a6a8  mov     r15d, eax
0x14011a6ab  test    eax, eax
0x14011a6ad  js      loc_14011A75D
0x14011a6b3  mov     rdx, r13; SourceString
0x14011a6b6  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x14011a6bb  call    cs:__imp_RtlInitUnicodeString
0x14011a6c2  nop     dword ptr [rax+rax+00h]
0x14011a6c7  mov     rax, [rdi+20h]
0x14011a6cb  mov     rcx, [rax+rbx*8]
0x14011a6cf  mov     rax, [rcx+8]
0x14011a6d3  cmp     ebp, [rcx+50h]
0x14011a6d6  jnb     short loc_14011A6DC
0x14011a6d8  lea     rax, [rax+rbp*8]
0x14011a6dc  mov     rcx, [rax]
0x14011a6df  lea     r8, [rsp+0B8h+DestinationString]; Name
0x14011a6e4  mov     rdx, cs:GpuPerformanceCounterSetEngine; Registration
0x14011a6eb  lea     rax, [rsp+0B8h+var_68]
0x14011a6f0  mov     [rsp+0B8h+var_68.Data], rcx
0x14011a6f5  mov     r9d, esi; Count
0x14011a6f8  add     rcx, 0D8h; Instance
0x14011a6ff  mov     [rsp+0B8h+var_68.Size], 0E0h
0x14011a707  mov     [rsp+0B8h+Data], rax; Data
0x14011a70c  call    cs:__imp_PcwCreateInstance
0x14011a713  nop     dword ptr [rax+rax+00h]
0x14011a718  mov     r15d, eax
0x14011a71b  test    eax, eax
0x14011a71d  js      short loc_14011A726
0x14011a71f  add     ebp, esi
0x14011a721  jmp     loc_14011A57C
0x14011a726  mov     ecx, esi
0x14011a728  call    cs:__imp_WdLogSingleEntry0
0x14011a72f  nop     dword ptr [rax+rax+00h]
0x14011a734  mov     [rsp+0B8h+var_80], 0
0x14011a73d  lea     r9, aFailedToCreate_4; "Failed to create GpuPerformanceCounterS"...
0x14011a744  mov     [rsp+0B8h+var_88], 0
0x14011a74d  mov     eax, 7195h
0x14011a752  mov     [rsp+0B8h+var_90], 0
0x14011a75b  jmp     short loc_14011A788
0x14011a75d  mov     ecx, esi
0x14011a75f  call    cs:__imp_WdLogSingleEntry0
0x14011a766  nop     dword ptr [rax+rax+00h]
0x14011a76b  xor     ecx, ecx
0x14011a76d  lea     r9, aFailedToCreate_25; "Failed to create name string for GpuPer"...
0x14011a774  mov     [rsp+0B8h+var_80], rcx
0x14011a779  mov     eax, 718Dh
0x14011a77e  mov     [rsp+0B8h+var_88], rcx
0x14011a783  mov     [rsp+0B8h+var_90], rcx
0x14011a788  mov     edx, 40000h
0x14011a78d  mov     [rsp+0B8h+Data], rax
  ... truncated ...
```
