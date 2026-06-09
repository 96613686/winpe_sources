# VidSchiOpenProcessAdapterInfo

- ea: `0x14011dabc`
- end: `0x14011e02e`
- name: `VidSchiOpenProcessAdapterInfo`
- size: `1394`
- prototype: `__int64 __fastcall(struct _VIDSCH_PROCESS *, struct _VIDSCH_GLOBAL *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x140113fb0`

## callees

- `0x140004268`
- `0x14002e6c0`
- `0x14002ed58`
- `0x1400349c0`
- `0x1400383b4`
- `0x1400390bc`
- `0x140039150`
- `0x1400392d4`
- `0x14011dabc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14011deab`
- `ntoskrnl!RtlInitUnicodeString` at `0x14011deab`
- `ntoskrnl!PcwCreateInstance` at `0x14011defc`
- `ntoskrnl!PcwCreateInstance` at `0x14011defc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14011dae2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14011dae2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011db09`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011db5b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011dce9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011db09`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011db5b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14011dce9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011dc1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011dc84`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011dccc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011dc1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011dc84`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011dccc`
- `ntoskrnl!ExAllocatePool2` at `0x14011db2c`
- `ntoskrnl!ExAllocatePool2` at `0x14011dd86`
- `ntoskrnl!ExAllocatePool2` at `0x14011dfdf`
- `ntoskrnl!ExAllocatePool2` at `0x14011db2c`
- `ntoskrnl!ExAllocatePool2` at `0x14011dd86`
- `ntoskrnl!ExAllocatePool2` at `0x14011dfdf`
- `watchdog!WdLogSingleEntry0` at `0x14011db40`
- `watchdog!WdLogSingleEntry0` at `0x14011dbe1`
- `watchdog!WdLogSingleEntry0` at `0x14011dd29`
- `watchdog!WdLogSingleEntry0` at `0x14011df18`
- `watchdog!WdLogSingleEntry0` at `0x14011df4f`
- `watchdog!WdLogSingleEntry0` at `0x14011df94`
- `watchdog!WdLogSingleEntry0` at `0x14011e013`
- `watchdog!WdLogSingleEntry0` at `0x14011db40`
- `watchdog!WdLogSingleEntry0` at `0x14011dbe1`
- `watchdog!WdLogSingleEntry0` at `0x14011dd29`
- `watchdog!WdLogSingleEntry0` at `0x14011df18`
- `watchdog!WdLogSingleEntry0` at `0x14011df4f`
- `watchdog!WdLogSingleEntry0` at `0x14011df94`
- `watchdog!WdLogSingleEntry0` at `0x14011e013`

## string_xrefs

- `0x14011dd3a`: `Failed to create name string for GpuPerformanceCounterSetEngine`
- `0x14011df5d`: `Failed to create name string for GpuPerformanceCounterSetEngine`
- `0x14011df2d`: `Failed to create GpuPerformanceCounterSetEngine`

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
    WdLogGlobalForLineNumber = 29065;
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
          v34 = *(_QWORD *)(352LL * *(unsigned __int16 *)(*(_QWORD *)v33 + 6LL) + *(_QWORD *)(v32 + 3120) + 32);
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
            v45 = 29130;
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
            v45 = 29138;
LABEL_53:
            WdLogGlobalForLineNumber = v45;
            DxgkLogInternalTriageEvent(v42, 0x40000, v43, (_DWORD)v44, v45, 0, 0, 0);
            goto LABEL_55;
          }
        }
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 29108;
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
              WdLogGlobalForLineNumber = 29162;
              goto LABEL_9;
            }
          }
          goto LABEL_3;
        }
        goto LABEL_10;
      }
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 29095;
      DxgkLogInternalTriageEvent(
        v22,
        0x40000,
        v23,
        (unsigned int)L"Failed to create name string for GpuPerformanceCounterSetEngine",
        29095,
        0,
        0,
        0);
    }
    else
    {
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 29084;
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
0x14011dabc  push    rbx
0x14011dabe  push    rbp
0x14011dabf  push    rsi
0x14011dac0  push    rdi
0x14011dac1  push    r12
0x14011dac3  push    r13
0x14011dac5  push    r14
0x14011dac7  push    r15
0x14011dac9  sub     rsp, 78h
0x14011dacd  mov     ebx, [rdx+4]
0x14011dad0  lea     r12, [rcx+0A68h]
0x14011dad7  mov     r14, rdx
0x14011dada  mov     rdi, rcx
0x14011dadd  mov     rcx, r12
0x14011dae0  xor     edx, edx
0x14011dae2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14011dae9  nop     dword ptr [rax+rax+00h]
0x14011daee  mov     rax, [rdi+20h]
0x14011daf2  xor     r13d, r13d
0x14011daf5  mov     rcx, [rax+rbx*8]
0x14011daf9  test    rcx, rcx
0x14011dafc  jz      short loc_14011DB1C
0x14011dafe  lea     esi, [r13+1]
0x14011db02  add     [rcx], esi
0x14011db04  xor     edx, edx
0x14011db06  mov     rcx, r12
0x14011db09  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14011db10  nop     dword ptr [rax+rax+00h]
0x14011db15  xor     eax, eax
0x14011db17  jmp     loc_14011DCF8
0x14011db1c  mov     edx, 0E8h
0x14011db21  mov     ecx, 40h ; '@'
0x14011db26  mov     r8d, 32616956h
0x14011db2c  call    cs:__imp_ExAllocatePool2
0x14011db33  nop     dword ptr [rax+rax+00h]
0x14011db38  test    rax, rax
0x14011db3b  jnz     short loc_14011DB71
0x14011db3d  lea     ecx, [rax+3]
0x14011db40  call    cs:__imp_WdLogSingleEntry0
0x14011db47  nop     dword ptr [rax+rax+00h]
0x14011db4c  xor     edx, edx
0x14011db4e  mov     cs:WdLogGlobalForLineNumber, 7189h
0x14011db58  mov     rcx, r12
0x14011db5b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14011db62  nop     dword ptr [rax+rax+00h]
0x14011db67  mov     eax, 0C0000017h
0x14011db6c  jmp     loc_14011DCF8
0x14011db71  mov     rcx, rax; this
0x14011db74  call    ??0VIDSCH_PROCESS_ADAPTER_INFO@@QEAA@XZ; VIDSCH_PROCESS_ADAPTER_INFO::VIDSCH_PROCESS_ADAPTER_INFO(void)
0x14011db79  mov     rcx, [rdi+20h]
0x14011db7d  mov     esi, 1
0x14011db82  mov     rdx, rdi; struct _VIDSCH_PROCESS *
0x14011db85  mov     [rcx+rbx*8], rax
0x14011db89  mov     rax, [rdi+20h]
0x14011db8d  mov     rcx, [rax+rbx*8]
0x14011db91  mov     [rcx], esi
0x14011db93  mov     rax, [rdi+20h]
0x14011db97  mov     rcx, [rax+rbx*8]
0x14011db9b  add     rcx, 0D8h
0x14011dba2  mov     [rcx+8], rcx
0x14011dba6  mov     [rcx], rcx
0x14011dba9  mov     rcx, r14; struct _VIDSCH_GLOBAL *
0x14011dbac  mov     r8, [rdi+20h]
0x14011dbb0  mov     r8, [r8+rbx*8]; struct VIDSCH_PROCESS_ADAPTER_INFO *
0x14011dbb4  call    ?VidSchiSetupKnownProcessBoost@@YAJPEAU_VIDSCH_GLOBAL@@PEAU_VIDSCH_PROCESS@@PEAUVIDSCH_PROCESS_ADAPTER_INFO@@@Z; VidSchiSetupKnownProcessBoost(_VIDSCH_GLOBAL *,_VIDSCH_PROCESS *,VIDSCH_PROCESS_ADAPTER_INFO *)
0x14011dbb9  mov     r15d, eax
0x14011dbbc  test    eax, eax
0x14011dbbe  js      short loc_14011DBFD
0x14011dbc0  mov     rcx, [rdi+20h]
0x14011dbc4  mov     edx, [r14+5Ch]
0x14011dbc8  mov     rcx, [rcx+rbx*8]
0x14011dbcc  add     rcx, 8
0x14011dbd0  call    ?AllocateElements@?$NonPagedPoolZeroedArray@PEAU_VIDSCH_NODE_STATISTICS@@$07$0DCGBGJFG@@@QEAAPEAPEAU_VIDSCH_NODE_STATISTICS@@I@Z; NonPagedPoolZeroedArray<_VIDSCH_NODE_STATISTICS *,8,845244758>::AllocateElements(uint)
0x14011dbd5  test    rax, rax
0x14011dbd8  jnz     loc_14011DD0A
0x14011dbde  lea     ecx, [rsi+2]
0x14011dbe1  call    cs:__imp_WdLogSingleEntry0
0x14011dbe8  nop     dword ptr [rax+rax+00h]
0x14011dbed  mov     cs:WdLogGlobalForLineNumber, 719Ch
0x14011dbf7  mov     r15d, 0C0000017h
0x14011dbfd  mov     ebp, r13d
0x14011dc00  cmp     [r14+30h], r13d
0x14011dc04  jbe     short loc_14011DC3E
0x14011dc06  mov     rax, [rdi+20h]
0x14011dc0a  mov     r12d, ebp
0x14011dc0d  mov     rcx, [rax+rbx*8]
0x14011dc11  mov     rcx, [rcx+r12*8+58h]; P
0x14011dc16  test    rcx, rcx
0x14011dc19  jz      short loc_14011DC36
0x14011dc1b  xor     edx, edx; Tag
0x14011dc1d  call    cs:__imp_ExFreePoolWithTag
0x14011dc24  nop     dword ptr [rax+rax+00h]
0x14011dc29  mov     rax, [rdi+20h]
0x14011dc2d  mov     rcx, [rax+rbx*8]
0x14011dc31  mov     [rcx+r12*8+58h], r13
0x14011dc36  add     ebp, esi
0x14011dc38  cmp     ebp, [r14+30h]
0x14011dc3c  jb      short loc_14011DC06
0x14011dc3e  mov     rax, [rdi+20h]
0x14011dc42  mov     rcx, [rax+rbx*8]
0x14011dc46  cmp     [rcx+8], r13
0x14011dc4a  jz      short loc_14011DCB0
0x14011dc4c  mov     ebp, r13d
0x14011dc4f  cmp     [r14+58h], r13d
0x14011dc53  jbe     short loc_14011DCB0
0x14011dc55  mov     rax, [rdi+20h]
0x14011dc59  mov     r12d, ebp
0x14011dc5c  mov     rcx, [rax+rbx*8]
0x14011dc60  mov     edx, [rcx+50h]
0x14011dc63  mov     rcx, [rcx+8]
0x14011dc67  lea     rax, [rcx+r12*8]
0x14011dc6b  cmp     ebp, edx
0x14011dc6d  jb      short loc_14011DC72
0x14011dc6f  mov     rax, rcx
0x14011dc72  cmp     [rax], r13
0x14011dc75  jz      short loc_14011DCA8
0x14011dc77  cmp     ebp, edx
0x14011dc79  jnb     short loc_14011DC7F
0x14011dc7b  lea     rcx, [rcx+r12*8]
0x14011dc7f  mov     rcx, [rcx]; P
0x14011dc82  xor     edx, edx; Tag
0x14011dc84  call    cs:__imp_ExFreePoolWithTag
0x14011dc8b  nop     dword ptr [rax+rax+00h]
0x14011dc90  mov     rax, [rdi+20h]
0x14011dc94  mov     rcx, [rax+rbx*8]
0x14011dc98  mov     rax, [rcx+8]
0x14011dc9c  cmp     ebp, [rcx+50h]
0x14011dc9f  jnb     short loc_14011DCA5
0x14011dca1  lea     rax, [rax+r12*8]
0x14011dca5  mov     [rax], r13
0x14011dca8  add     ebp, esi
0x14011dcaa  cmp     ebp, [r14+58h]
0x14011dcae  jb      short loc_14011DC55
0x14011dcb0  mov     rax, [rdi+20h]
0x14011dcb4  mov     rcx, [rax+rbx*8]; this
0x14011dcb8  test    rcx, rcx
0x14011dcbb  jz      short loc_14011DCE0
0x14011dcbd  call    ??_GVIDSCH_PROCESS_ADAPTER_INFO@@QEAAPEAXI@Z; VIDSCH_PROCESS_ADAPTER_INFO::`scalar deleting destructor'(uint)
0x14011dcc2  mov     rcx, [rdi+20h]
0x14011dcc6  xor     edx, edx; Tag
0x14011dcc8  mov     rcx, [rcx+rbx*8]; P
0x14011dccc  call    cs:__imp_ExFreePoolWithTag
0x14011dcd3  nop     dword ptr [rax+rax+00h]
0x14011dcd8  mov     rax, [rdi+20h]
0x14011dcdc  mov     [rax+rbx*8], r13
0x14011dce0  xor     edx, edx
0x14011dce2  lea     rcx, [rdi+0A68h]
0x14011dce9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14011dcf0  nop     dword ptr [rax+rax+00h]
0x14011dcf5  mov     eax, r15d
0x14011dcf8  add     rsp, 78h
0x14011dcfc  pop     r15
0x14011dcfe  pop     r14
0x14011dd00  pop     r13
0x14011dd02  pop     r12
0x14011dd04  pop     rdi
0x14011dd05  pop     rsi
0x14011dd06  pop     rbp
0x14011dd07  pop     rbx
0x14011dd08  retn
0x14011dd0a  mov     edx, 4B677844h
0x14011dd0f  mov     ecx, 208h
0x14011dd14  mov     r8d, 100h
0x14011dd1a  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011dd1f  mov     r13, rax
0x14011dd22  test    rax, rax
0x14011dd25  jnz     short loc_14011DD6A
0x14011dd27  mov     ecx, esi
0x14011dd29  call    cs:__imp_WdLogSingleEntry0
0x14011dd30  nop     dword ptr [rax+rax+00h]
0x14011dd35  mov     [rsp+0B8h+var_80], r13
0x14011dd3a  lea     r9, aFailedToCreate_25; "Failed to create name string for GpuPer"...
0x14011dd41  mov     eax, 71A7h
0x14011dd46  mov     [rsp+0B8h+var_88], r13
0x14011dd4b  mov     [rsp+0B8h+var_90], r13
0x14011dd50  mov     edx, 40000h
0x14011dd55  mov     cs:WdLogGlobalForLineNumber, eax
0x14011dd5b  mov     [rsp+0B8h+Data], rax
0x14011dd60  call    DxgkLogInternalTriageEvent
0x14011dd65  jmp     loc_14011DBF7
0x14011dd6a  xor     ebp, ebp
0x14011dd6c  cmp     ebp, [r14+58h]
0x14011dd70  jnb     loc_14011DFB0
0x14011dd76  mov     edx, 0E0h
0x14011dd7b  mov     ecx, 40h ; '@'
0x14011dd80  mov     r8d, 32616956h
0x14011dd86  call    cs:__imp_ExAllocatePool2
0x14011dd8d  nop     dword ptr [rax+rax+00h]
0x14011dd92  mov     rcx, [rdi+20h]
0x14011dd96  mov     rdx, [rcx+rbx*8]
0x14011dd9a  mov     rcx, [rdx+8]
0x14011dd9e  cmp     ebp, [rdx+50h]
0x14011dda1  jnb     short loc_14011DDA7
0x14011dda3  lea     rcx, [rcx+rbp*8]
0x14011dda7  mov     [rcx], rax
0x14011ddaa  mov     rax, [rdi+20h]
0x14011ddae  mov     rax, [rax+rbx*8]
0x14011ddb2  mov     rdx, [rax+8]
0x14011ddb6  cmp     ebp, [rax+50h]
0x14011ddb9  lea     rcx, [rdx+rbp*8]
0x14011ddbd  cmovnb  rcx, rdx
0x14011ddc1  cmp     qword ptr [rcx], 0
0x14011ddc5  jz      loc_14011DF8F
0x14011ddcb  mov     r9, [r14+308h]
0x14011ddd2  xorps   xmm0, xmm0
0x14011ddd5  mov     r10d, [r14+350h]
0x14011dddc  cmp     ebp, r10d
0x14011dddf  mov     r15, [r14+10h]
0x14011dde3  lea     r11, [r9+rbp*8]
0x14011dde7  mov     rax, r11
0x14011ddea  cmovnb  rax, r9
0x14011ddee  mov     rax, [rax]
0x14011ddf1  movzx   ecx, word ptr [rax+6]
0x14011ddf5  mov     rax, [r15+0C30h]
0x14011ddfc  imul    rdx, rcx, 160h
0x14011de03  cmp     ebp, r10d
0x14011de06  mov     r8, [rdx+rax+20h]
0x14011de0b  mov     rax, r9
0x14011de0e  cmovb   rax, r11
0x14011de12  mov     rax, [rax]
0x14011de15  movzx   ecx, word ptr [rax+8]
0x14011de19  imul    rax, rcx, 4Ah ; 'J'
0x14011de1d  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x14011de22  movsxd  rcx, dword ptr [rax+r8]
0x14011de26  test    ecx, ecx
0x14011de28  jz      short loc_14011DE37
0x14011de2a  lea     r8, off_14005B1F0; "Other"
0x14011de31  mov     r8, [r8+rcx*8]
0x14011de35  jmp     short loc_14011DE3E
0x14011de37  add     r8, 4
0x14011de3b  add     r8, rax
0x14011de3e  mov     [rsp+0B8h+var_78], r8
0x14011de43  mov     rax, r9
0x14011de46  cmp     ebp, r10d
0x14011de49  lea     r8, aPidIuLuid0x08x; "pid_%Iu_luid_0x%08X_0x%08X_phys_%u_eng_"...
0x14011de50  cmovb   rax, r11
0x14011de54  cmovb   r9, r11
0x14011de58  mov     rax, [rax]
0x14011de5b  movzx   edx, word ptr [rax+8]
0x14011de5f  mov     rax, [r9]
0x14011de62  mov     r9, [rdi+0A50h]
0x14011de69  mov     dword ptr [rsp+0B8h+var_80], edx
0x14011de6d  mov     edx, 208h; cbDest
0x14011de72  movzx   ecx, word ptr [rax+6]
0x14011de76  mov     eax, [r15+19Ch]
0x14011de7d  mov     dword ptr [rsp+0B8h+var_88], ecx
0x14011de81  mov     rcx, r13; pszDest
0x14011de84  mov     dword ptr [rsp+0B8h+var_90], eax
0x14011de88  mov     eax, [r15+1A0h]
0x14011de8f  mov     dword ptr [rsp+0B8h+Data], eax
0x14011de93  call    RtlStringCbPrintfW
0x14011de98  mov     r15d, eax
0x14011de9b  test    eax, eax
0x14011de9d  js      loc_14011DF4D
0x14011dea3  mov     rdx, r13; SourceString
0x14011dea6  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x14011deab  call    cs:__imp_RtlInitUnicodeString
0x14011deb2  nop     dword ptr [rax+rax+00h]
0x14011deb7  mov     rax, [rdi+20h]
0x14011debb  mov     rcx, [rax+rbx*8]
0x14011debf  mov     rax, [rcx+8]
0x14011dec3  cmp     ebp, [rcx+50h]
0x14011dec6  jnb     short loc_14011DECC
0x14011dec8  lea     rax, [rax+rbp*8]
0x14011decc  mov     rcx, [rax]
0x14011decf  lea     r8, [rsp+0B8h+DestinationString]; Name
0x14011ded4  mov     rdx, cs:GpuPerformanceCounterSetEngine; Registration
0x14011dedb  lea     rax, [rsp+0B8h+var_68]
0x14011dee0  mov     [rsp+0B8h+var_68.Data], rcx
0x14011dee5  mov     r9d, esi; Count
0x14011dee8  add     rcx, 0D8h; Instance
0x14011deef  mov     [rsp+0B8h+var_68.Size], 0E0h
0x14011def7  mov     [rsp+0B8h+Data], rax; Data
0x14011defc  call    cs:__imp_PcwCreateInstance
0x14011df03  nop     dword ptr [rax+rax+00h]
0x14011df08  mov     r15d, eax
0x14011df0b  test    eax, eax
0x14011df0d  js      short loc_14011DF16
0x14011df0f  add     ebp, esi
0x14011df11  jmp     loc_14011DD6C
0x14011df16  mov     ecx, esi
0x14011df18  call    cs:__imp_WdLogSingleEntry0
0x14011df1f  nop     dword ptr [rax+rax+00h]
0x14011df24  mov     [rsp+0B8h+var_80], 0
0x14011df2d  lea     r9, aFailedToCreate_4; "Failed to create GpuPerformanceCounterS"...
0x14011df34  mov     [rsp+0B8h+var_88], 0
0x14011df3d  mov     eax, 71D2h
0x14011df42  mov     [rsp+0B8h+var_90], 0
0x14011df4b  jmp     short loc_14011DF78
0x14011df4d  mov     ecx, esi
0x14011df4f  call    cs:__imp_WdLogSingleEntry0
0x14011df56  nop     dword ptr [rax+rax+00h]
0x14011df5b  xor     ecx, ecx
0x14011df5d  lea     r9, aFailedToCreate_25; "Failed to create name string for GpuPer"...
0x14011df64  mov     [rsp+0B8h+var_80], rcx
0x14011df69  mov     eax, 71CAh
0x14011df6e  mov     [rsp+0B8h+var_88], rcx
0x14011df73  mov     [rsp+0B8h+var_90], rcx
0x14011df78  mov     edx, 40000h
0x14011df7d  mov     [rsp+0B8h+Data], rax
  ... truncated ...
```
