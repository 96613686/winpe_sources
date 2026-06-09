# TeredoClientProcessFilterChangesCallback

- ea: `0x180018ce0`
- end: `0x1800190dc`
- name: `TeredoClientProcessFilterChangesCallback`
- size: `1020`
- prototype: `void __stdcall(void *context, const FWPM_FILTER_CHANGE0 *change)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004f60`
- `0x1800077e8`
- `0x18000d7c0`
- `0x180018ce0`
- `0x1800190f0`
- `0x180036850`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018f95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018f95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018fa9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018fa9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ea2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ea2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018efa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018efa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f58`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180018e4e`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180018e4e`
- `fwpuclnt!FwpmFreeMemory0` at `0x180018f1b`
- `fwpuclnt!FwpmFreeMemory0` at `0x180018f1b`
- `fwpuclnt!FwpmFilterGetByKey0` at `0x180018d25`
- `fwpuclnt!FwpmFilterGetByKey0` at `0x180018d25`

## string_xrefs

- `0x180018ddb`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180018dfb`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x180018e62`: `Teredo processing filter changes: Failed to schedule TeredoReevluateFilters worker thread`

## pseudocode

```c
void __fastcall TeredoClientProcessFilterChangesCallback(char *context, const FWPM_FILTER_CHANGE0 *change)
{
  FWPM_CHANGE_TYPE changeType; // eax
  DWORD v5; // eax
  GUID *providerKey; // rcx
  __int64 v7; // rax
  FWP_ACTION_TYPE type; // eax
  __int64 v9; // rax
  int v10; // r11d
  int v11; // r10d
  int v12; // r8d
  __int64 i; // r9
  int v14; // eax
  char *v15; // r14
  char *v16; // rsi
  int v17; // ebp
  __int64 v18; // rax
  char *v19; // rax
  char **v20; // rcx
  HANDLE ProcessHeap; // rax
  FWPM_FILTER_CONDITION0 *filterCondition; // rax
  __int64 v23; // rbx
  __int64 v24; // rbx
  __int64 v25; // rbx
  __int64 v26; // rbx
  __int64 v27; // rbx
  FWPM_FILTER0 *filter; // [rsp+58h] [rbp+10h] BYREF

  changeType = change->changeType;
  filter = 0;
  if ( changeType == FWPM_CHANGE_DELETE )
  {
    EnterCriticalSection(&TeredoFiltersLock);
    if ( context[2788] != 1 )
    {
      v15 = context + 19504;
      v16 = (char *)*((_QWORD *)context + 2438);
      if ( v16 != context + 19504 )
      {
        v17 = 0;
        while ( 1 )
        {
          v18 = *(_QWORD *)&change->filterKey.Data1 - *((_QWORD *)v16 + 2);
          if ( !v18 )
            v18 = *(_QWORD *)change->filterKey.Data4 - *((_QWORD *)v16 + 3);
          if ( !v18 )
            break;
          v16 = *(char **)v16;
          if ( v16 == v15 )
            goto LABEL_29;
        }
        if ( v16 != v15 )
        {
          v19 = *(char **)v16;
          if ( *(char **)(*(_QWORD *)v16 + 8LL) != v16 || (v20 = (char **)*((_QWORD *)v16 + 1), *v20 != v16) )
            __fastfail(3u);
          *v20 = v19;
          *((_QWORD *)v19 + 1) = v20;
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v16);
          if ( *(char **)v15 == v15 )
          {
            v17 = 1;
            EventWrite0(0x100000, L"Teredo Block Filter List is empty.");
          }
        }
LABEL_29:
        LeaveCriticalSection(&TeredoFiltersLock);
        if ( !v17 )
          goto LABEL_30;
LABEL_17:
        EventWrite0(
          0x40000,
          L"ReferenceService: ++%u (%hs) @ %ls:%u",
          ((unsigned int)g_Reference >> 1) & 0x3FFFFFFF,
          "TeredoClientReevaluateFiltersWorker",
          L"onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c",
          1866);
        while ( 1 )
        {
          v14 = g_Reference;
          if ( (g_Reference & 1) != 0 )
            goto LABEL_30;
          if ( v14 == _InterlockedCompareExchange(&g_Reference, g_Reference + 2, g_Reference) )
          {
            ReferenceCompartmentEx(context, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c", 1870);
            if ( !TrySubmitThreadpoolCallback(TeredoClientReevaluateFiltersWorker, context, &CallbackEnvironment) )
            {
              EventWriteError0(
                0x100000,
                L"Teredo processing filter changes: Failed to schedule TeredoReevluateFilters worker thread");
              DereferenceCompartmentEx(context, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c", 1877);
              DereferenceServiceEx(
                "TeredoClientReevaluateFiltersWorker",
                L"onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c",
                1878);
            }
            goto LABEL_30;
          }
        }
      }
    }
    LeaveCriticalSection(&TeredoFiltersLock);
  }
  else
  {
    if ( changeType != FWPM_CHANGE_ADD )
      return;
    v5 = FwpmFilterGetByKey0(*((HANDLE *)context + 349), &change->filterKey, &filter);
    if ( !v5 )
    {
      providerKey = filter->providerKey;
      if ( providerKey )
      {
        v7 = *(_QWORD *)&providerKey->Data1 - *((_QWORD *)context + 2440);
        if ( *(_QWORD *)&providerKey->Data1 == *((_QWORD *)context + 2440) )
          v7 = *(_QWORD *)providerKey->Data4 - *((_QWORD *)context + 2441);
        if ( !v7 )
          goto LABEL_30;
      }
      type = filter->action.type;
      if ( type != 20483 && type != 4097 )
        goto LABEL_30;
      v9 = *(_QWORD *)&filter->subLayerKey.Data1 - *(_QWORD *)&FWPM_SUBLAYER_TEREDO.Data1;
      if ( !v9 )
        v9 = *(_QWORD *)filter->subLayerKey.Data4 - *(_QWORD *)FWPM_SUBLAYER_TEREDO.Data4;
      if ( v9 )
        goto LABEL_30;
      v10 = 0;
      v11 = 0;
      v12 = 0;
      for ( i = 0; (unsigned int)i < filter->numFilterConditions; i = (unsigned int)(i + 1) )
      {
        filterCondition = filter->filterCondition;
        v23 = *(_QWORD *)&filterCondition[i].fieldKey.Data1 - *(_QWORD *)&FWPM_CONDITION_ARRIVAL_INTERFACE_TYPE.Data1;
        if ( !v23 )
          v23 = *(_QWORD *)filterCondition[i].fieldKey.Data4 - *(_QWORD *)FWPM_CONDITION_ARRIVAL_INTERFACE_TYPE.Data4;
        if ( v23 )
        {
          v24 = *(_QWORD *)&filterCondition[i].fieldKey.Data1 - *(_QWORD *)&FWPM_CONDITION_INTERFACE_TYPE.Data1;
          if ( !v24 )
            v24 = *(_QWORD *)filterCondition[i].fieldKey.Data4 - *(_QWORD *)FWPM_CONDITION_INTERFACE_TYPE.Data4;
          if ( v24 )
            goto LABEL_53;
        }
        if ( filterCondition[i].matchType
          || filterCondition[i].conditionValue.type != FWP_UINT32
          || filterCondition[i].conditionValue.uint32 != 131 )
        {
LABEL_53:
          v25 = *(_QWORD *)&filterCondition[i].fieldKey.Data1 - *(_QWORD *)&FWPM_CONDITION_ARRIVAL_TUNNEL_TYPE.Data1;
          if ( !v25 )
            v25 = *(_QWORD *)filterCondition[i].fieldKey.Data4 - *(_QWORD *)FWPM_CONDITION_ARRIVAL_TUNNEL_TYPE.Data4;
          if ( v25 )
          {
            v26 = *(_QWORD *)&filterCondition[i].fieldKey.Data1 - *(_QWORD *)&FWPM_CONDITION_TUNNEL_TYPE.Data1;
            if ( !v26 )
              v26 = *(_QWORD *)filterCondition[i].fieldKey.Data4 - *(_QWORD *)FWPM_CONDITION_TUNNEL_TYPE.Data4;
            if ( v26 )
              goto LABEL_63;
          }
          if ( filterCondition[i].matchType
            || filterCondition[i].conditionValue.type != FWP_UINT32
            || filterCondition[i].conditionValue.uint32 != 14 )
          {
LABEL_63:
            v27 = *(_QWORD *)&filterCondition[i].fieldKey.Data1 - *(_QWORD *)&FWPM_CONDITION_FLAGS.Data1;
            if ( !v27 )
              v27 = *(_QWORD *)filterCondition[i].fieldKey.Data4 - *(_QWORD *)FWPM_CONDITION_FLAGS.Data4;
            if ( v27
              || filterCondition[i].matchType != FWP_MATCH_FLAGS_NONE_SET
              || filterCondition[i].conditionValue.type != FWP_UINT32
              || filterCondition[i].conditionValue.uint32 != 1 )
            {
              v12 = 1;
              break;
            }
          }
          else
          {
            v11 = 1;
          }
        }
        else
        {
          v10 = 1;
        }
      }
      if ( !v10 || !v11 || v12 )
        goto LABEL_30;
      goto LABEL_17;
    }
    EventWriteError0(
      0x100000,
      L"Teredo processing filter changes: Unable to retrieve filter based on the GUID. Error %u",
      v5);
  }
LABEL_30:
  if ( filter )
    FwpmFreeMemory0((void **)&filter);
}

```

## disassembly

```asm
0x180018ce0  mov     [rsp+arg_10], rbx
0x180018ce5  mov     [rsp+arg_18], rbp
0x180018cea  push    rsi
0x180018ceb  push    rdi
0x180018cec  push    r14
0x180018cee  sub     rsp, 30h
0x180018cf2  mov     eax, [rdx]
0x180018cf4  mov     rbx, rdx
0x180018cf7  mov     [rsp+48h+filter], 0
0x180018d00  mov     rdi, rcx
0x180018d03  cmp     eax, 2
0x180018d06  jz      loc_180018E9B
0x180018d0c  cmp     eax, 1
0x180018d0f  jnz     loc_180018F27
0x180018d15  mov     rcx, [rcx+0AE8h]; engineHandle
0x180018d1c  lea     r8, [rsp+48h+filter]; filter
0x180018d21  add     rdx, 4; key
0x180018d25  call    cs:__imp_FwpmFilterGetByKey0
0x180018d2c  nop     dword ptr [rax+rax+00h]
0x180018d31  test    eax, eax
0x180018d33  jnz     loc_180018F3B
0x180018d39  mov     rax, [rsp+48h+filter]
0x180018d3e  mov     rcx, [rax+28h]
0x180018d42  test    rcx, rcx
0x180018d45  jz      short loc_180018D67
0x180018d47  mov     rax, [rcx]
0x180018d4a  sub     rax, [rdi+4C40h]
0x180018d51  jnz     short loc_180018D5E
0x180018d53  mov     rax, [rcx+8]
0x180018d57  sub     rax, [rdi+4C48h]
0x180018d5e  test    rax, rax
0x180018d61  jz      loc_180018F0E
0x180018d67  mov     rdx, [rsp+48h+filter]
0x180018d6c  mov     eax, [rdx+80h]
0x180018d72  cmp     eax, 5003h
0x180018d77  jnz     loc_180018F66
0x180018d7d  mov     rax, [rdx+50h]
0x180018d81  sub     rax, qword ptr cs:FWPM_SUBLAYER_TEREDO.Data1
0x180018d88  jnz     short loc_180018D95
0x180018d8a  mov     rax, [rdx+58h]
0x180018d8e  sub     rax, qword ptr cs:FWPM_SUBLAYER_TEREDO.Data4
0x180018d95  test    rax, rax
0x180018d98  jnz     loc_180018F0E
0x180018d9e  xor     r11d, r11d
0x180018da1  xor     r10d, r10d
0x180018da4  xor     r8d, r8d
0x180018da7  mov     ebp, 1
0x180018dac  xor     r9d, r9d
0x180018daf  cmp     r9d, [rdx+70h]
0x180018db3  jb      loc_180018FE0
0x180018db9  test    r11d, r11d
0x180018dbc  jz      loc_180018F0E
0x180018dc2  test    r10d, r10d
0x180018dc5  jz      loc_180018F0E
0x180018dcb  test    r8d, r8d
0x180018dce  jnz     loc_180018F0E
0x180018dd4  mov     r8d, cs:g_Reference
0x180018ddb  lea     rbx, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180018de2  shr     r8d, 1
0x180018de5  lea     r9, aTeredoclientre; "TeredoClientReevaluateFiltersWorker"
0x180018dec  and     r8d, 3FFFFFFFh
0x180018df3  mov     [rsp+48h+var_20], 74Ah
0x180018dfb  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x180018e02  mov     [rsp+48h+var_28], rbx
0x180018e07  mov     ecx, 40000h
0x180018e0c  call    EventWrite0
0x180018e11  mov     eax, cs:g_Reference
0x180018e17  test    al, 1
0x180018e19  jnz     loc_180018F0E
0x180018e1f  lea     ecx, [rax+2]
0x180018e22  lock cmpxchg cs:g_Reference, ecx
0x180018e2a  jnz     short loc_180018E11
0x180018e2c  mov     r8d, 74Eh
0x180018e32  mov     rdx, rbx
0x180018e35  mov     rcx, rdi
0x180018e38  call    ReferenceCompartmentEx
0x180018e3d  lea     r8, CallbackEnvironment; pcbe
0x180018e44  mov     rdx, rdi; pv
0x180018e47  lea     rcx, TeredoClientReevaluateFiltersWorker; pfns
0x180018e4e  call    cs:__imp_TrySubmitThreadpoolCallback
0x180018e55  nop     dword ptr [rax+rax+00h]
0x180018e5a  test    eax, eax
0x180018e5c  jnz     loc_180018F0E
0x180018e62  lea     rdx, aTeredoProcessi; "Teredo processing filter changes: Faile"...
0x180018e69  mov     ecx, 100000h
0x180018e6e  call    EventWriteError0
0x180018e73  mov     r8d, 755h
0x180018e79  mov     rdx, rbx
0x180018e7c  mov     rcx, rdi
0x180018e7f  call    DereferenceCompartmentEx
0x180018e84  mov     r8d, 756h
0x180018e8a  lea     rcx, aTeredoclientre; "TeredoClientReevaluateFiltersWorker"
0x180018e91  mov     rdx, rbx
0x180018e94  call    DereferenceServiceEx
0x180018e99  jmp     short loc_180018F0E
0x180018e9b  lea     rcx, TeredoFiltersLock; lpCriticalSection
0x180018ea2  call    cs:__imp_EnterCriticalSection
0x180018ea9  nop     dword ptr [rax+rax+00h]
0x180018eae  cmp     byte ptr [rdi+0AE4h], 1
0x180018eb5  jz      loc_180018F51
0x180018ebb  lea     r14, [rdi+4C30h]
0x180018ec2  mov     rsi, [r14]
0x180018ec5  cmp     rsi, r14
0x180018ec8  jz      loc_180018F51
0x180018ece  xor     ebp, ebp
0x180018ed0  mov     rax, [rbx+4]
0x180018ed4  sub     rax, [rsi+10h]
0x180018ed8  jnz     short loc_180018EE2
0x180018eda  mov     rax, [rbx+0Ch]
0x180018ede  sub     rax, [rsi+18h]
0x180018ee2  test    rax, rax
0x180018ee5  jz      loc_180018F73
0x180018eeb  mov     rsi, [rsi]
0x180018eee  cmp     rsi, r14
0x180018ef1  jnz     short loc_180018ED0
0x180018ef3  lea     rcx, TeredoFiltersLock; lpCriticalSection
0x180018efa  call    cs:__imp_LeaveCriticalSection
0x180018f01  nop     dword ptr [rax+rax+00h]
0x180018f06  test    ebp, ebp
0x180018f08  jnz     loc_180018DD4
0x180018f0e  cmp     [rsp+48h+filter], 0
0x180018f14  jz      short loc_180018F27
0x180018f16  lea     rcx, [rsp+48h+filter]; p
0x180018f1b  call    cs:__imp_FwpmFreeMemory0
0x180018f22  nop     dword ptr [rax+rax+00h]
0x180018f27  mov     rbx, [rsp+48h+arg_10]
0x180018f2c  mov     rbp, [rsp+48h+arg_18]
0x180018f31  add     rsp, 30h
0x180018f35  pop     r14
0x180018f37  pop     rdi
0x180018f38  pop     rsi
0x180018f39  retn
0x180018f3b  mov     r8d, eax
0x180018f3e  lea     rdx, aTeredoProcessi_0; "Teredo processing filter changes: Unabl"...
0x180018f45  mov     ecx, 100000h
0x180018f4a  call    EventWriteError0
0x180018f4f  jmp     short loc_180018F0E
0x180018f51  lea     rcx, TeredoFiltersLock; lpCriticalSection
0x180018f58  call    cs:__imp_LeaveCriticalSection
0x180018f5f  nop     dword ptr [rax+rax+00h]
0x180018f64  jmp     short loc_180018F0E
0x180018f66  cmp     eax, 1001h
0x180018f6b  jz      loc_180018D7D
0x180018f71  jmp     short loc_180018F0E
0x180018f73  cmp     rsi, r14
0x180018f76  jz      loc_180018EF3
0x180018f7c  mov     rax, [rsi]
0x180018f7f  cmp     [rax+8], rsi
0x180018f83  jnz     short loc_180018FD9
0x180018f85  mov     rcx, [rsi+8]
0x180018f89  cmp     [rcx], rsi
0x180018f8c  jnz     short loc_180018FD9
0x180018f8e  mov     [rcx], rax
0x180018f91  mov     [rax+8], rcx
0x180018f95  call    cs:__imp_GetProcessHeap
0x180018f9c  nop     dword ptr [rax+rax+00h]
0x180018fa1  mov     r8, rsi; lpMem
0x180018fa4  xor     edx, edx; dwFlags
0x180018fa6  mov     rcx, rax; hHeap
0x180018fa9  call    cs:__imp_HeapFree
0x180018fb0  nop     dword ptr [rax+rax+00h]
0x180018fb5  cmp     [r14], r14
0x180018fb8  jnz     loc_180018EF3
0x180018fbe  lea     rdx, aTeredoBlockFil; "Teredo Block Filter List is empty."
0x180018fc5  mov     ecx, 100000h
0x180018fca  mov     ebp, 1
0x180018fcf  call    EventWrite0
0x180018fd4  jmp     loc_180018EF3
0x180018fd9  mov     ecx, 3
0x180018fde  int     29h; Win8: RtlFailFast(ecx)
0x180018fe0  mov     rax, [rdx+78h]
0x180018fe4  lea     rcx, [r9+r9*4]
0x180018fe8  mov     rbx, [rax+rcx*8]
0x180018fec  sub     rbx, qword ptr cs:FWPM_CONDITION_ARRIVAL_INTERFACE_TYPE.Data1
0x180018ff3  jnz     short loc_180019001
0x180018ff5  mov     rbx, [rax+rcx*8+8]
0x180018ffa  sub     rbx, qword ptr cs:FWPM_CONDITION_ARRIVAL_INTERFACE_TYPE.Data4
0x180019001  test    rbx, rbx
0x180019004  jz      short loc_180019024
0x180019006  mov     rbx, [rax+rcx*8]
0x18001900a  sub     rbx, qword ptr cs:FWPM_CONDITION_INTERFACE_TYPE.Data1
0x180019011  jnz     short loc_18001901F
0x180019013  mov     rbx, [rax+rcx*8+8]
0x180019018  sub     rbx, qword ptr cs:FWPM_CONDITION_INTERFACE_TYPE.Data4
0x18001901f  test    rbx, rbx
0x180019022  jnz     short loc_180019044
0x180019024  cmp     [rax+rcx*8+10h], r8d
0x180019029  jnz     short loc_180019044
0x18001902b  cmp     dword ptr [rax+rcx*8+18h], 3
0x180019030  jnz     short loc_180019044
0x180019032  cmp     dword ptr [rax+rcx*8+20h], 83h
0x18001903a  jnz     short loc_180019044
0x18001903c  mov     r11d, ebp
0x18001903f  jmp     loc_1800190CC
0x180019044  mov     rbx, [rax+rcx*8]
0x180019048  sub     rbx, qword ptr cs:FWPM_CONDITION_ARRIVAL_TUNNEL_TYPE.Data1
0x18001904f  jnz     short loc_18001905D
0x180019051  mov     rbx, [rax+rcx*8+8]
0x180019056  sub     rbx, qword ptr cs:FWPM_CONDITION_ARRIVAL_TUNNEL_TYPE.Data4
0x18001905d  test    rbx, rbx
0x180019060  jz      short loc_180019080
0x180019062  mov     rbx, [rax+rcx*8]
0x180019066  sub     rbx, qword ptr cs:FWPM_CONDITION_TUNNEL_TYPE.Data1
0x18001906d  jnz     short loc_18001907B
0x18001906f  mov     rbx, [rax+rcx*8+8]
0x180019074  sub     rbx, qword ptr cs:FWPM_CONDITION_TUNNEL_TYPE.Data4
0x18001907b  test    rbx, rbx
0x18001907e  jnz     short loc_18001909A
0x180019080  cmp     [rax+rcx*8+10h], r8d
0x180019085  jnz     short loc_18001909A
0x180019087  cmp     dword ptr [rax+rcx*8+18h], 3
0x18001908c  jnz     short loc_18001909A
0x18001908e  cmp     dword ptr [rax+rcx*8+20h], 0Eh
0x180019093  jnz     short loc_18001909A
0x180019095  mov     r10d, ebp
0x180019098  jmp     short loc_1800190CC
0x18001909a  mov     rbx, [rax+rcx*8]
0x18001909e  sub     rbx, qword ptr cs:FWPM_CONDITION_FLAGS.Data1
0x1800190a5  jnz     short loc_1800190B3
0x1800190a7  mov     rbx, [rax+rcx*8+8]
0x1800190ac  sub     rbx, qword ptr cs:FWPM_CONDITION_FLAGS.Data4
0x1800190b3  test    rbx, rbx
0x1800190b6  jnz     short loc_1800190D4
0x1800190b8  cmp     dword ptr [rax+rcx*8+10h], 8
0x1800190bd  jnz     short loc_1800190D4
0x1800190bf  cmp     dword ptr [rax+rcx*8+18h], 3
0x1800190c4  jnz     short loc_1800190D4
0x1800190c6  cmp     [rax+rcx*8+20h], ebp
0x1800190ca  jnz     short loc_1800190D4
0x1800190cc  inc     r9d
0x1800190cf  jmp     loc_180018DAF
0x1800190d4  mov     r8d, ebp
0x1800190d7  jmp     loc_180018DB9
```
