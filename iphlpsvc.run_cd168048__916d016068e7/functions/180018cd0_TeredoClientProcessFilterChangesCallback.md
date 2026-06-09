# TeredoClientProcessFilterChangesCallback

- ea: `0x180018cd0`
- end: `0x1800190cc`
- name: `TeredoClientProcessFilterChangesCallback`
- size: `1020`
- prototype: `void __stdcall(void *context, const FWPM_FILTER_CHANGE0 *change)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004f50`
- `0x1800077d8`
- `0x18000d7b0`
- `0x180018cd0`
- `0x1800190e0`
- `0x180036840`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018f85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018f85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018f99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018f99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018e92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018e92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018eea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018eea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f48`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180018e3e`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180018e3e`
- `fwpuclnt!FwpmFreeMemory0` at `0x180018f0b`
- `fwpuclnt!FwpmFreeMemory0` at `0x180018f0b`
- `fwpuclnt!FwpmFilterGetByKey0` at `0x180018d15`
- `fwpuclnt!FwpmFilterGetByKey0` at `0x180018d15`

## string_xrefs

- `0x180018dcb`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x180018deb`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x180018e52`: `Teredo processing filter changes: Failed to schedule TeredoReevluateFilters worker thread`

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
0x180018cd0  mov     [rsp+arg_10], rbx
0x180018cd5  mov     [rsp+arg_18], rbp
0x180018cda  push    rsi
0x180018cdb  push    rdi
0x180018cdc  push    r14
0x180018cde  sub     rsp, 30h
0x180018ce2  mov     eax, [rdx]
0x180018ce4  mov     rbx, rdx
0x180018ce7  mov     [rsp+48h+filter], 0
0x180018cf0  mov     rdi, rcx
0x180018cf3  cmp     eax, 2
0x180018cf6  jz      loc_180018E8B
0x180018cfc  cmp     eax, 1
0x180018cff  jnz     loc_180018F17
0x180018d05  mov     rcx, [rcx+0AE8h]; engineHandle
0x180018d0c  lea     r8, [rsp+48h+filter]; filter
0x180018d11  add     rdx, 4; key
0x180018d15  call    cs:__imp_FwpmFilterGetByKey0
0x180018d1c  nop     dword ptr [rax+rax+00h]
0x180018d21  test    eax, eax
0x180018d23  jnz     loc_180018F2B
0x180018d29  mov     rax, [rsp+48h+filter]
0x180018d2e  mov     rcx, [rax+28h]
0x180018d32  test    rcx, rcx
0x180018d35  jz      short loc_180018D57
0x180018d37  mov     rax, [rcx]
0x180018d3a  sub     rax, [rdi+4C40h]
0x180018d41  jnz     short loc_180018D4E
0x180018d43  mov     rax, [rcx+8]
0x180018d47  sub     rax, [rdi+4C48h]
0x180018d4e  test    rax, rax
0x180018d51  jz      loc_180018EFE
0x180018d57  mov     rdx, [rsp+48h+filter]
0x180018d5c  mov     eax, [rdx+80h]
0x180018d62  cmp     eax, 5003h
0x180018d67  jnz     loc_180018F56
0x180018d6d  mov     rax, [rdx+50h]
0x180018d71  sub     rax, qword ptr cs:FWPM_SUBLAYER_TEREDO.Data1
0x180018d78  jnz     short loc_180018D85
0x180018d7a  mov     rax, [rdx+58h]
0x180018d7e  sub     rax, qword ptr cs:FWPM_SUBLAYER_TEREDO.Data4
0x180018d85  test    rax, rax
0x180018d88  jnz     loc_180018EFE
0x180018d8e  xor     r11d, r11d
0x180018d91  xor     r10d, r10d
0x180018d94  xor     r8d, r8d
0x180018d97  mov     ebp, 1
0x180018d9c  xor     r9d, r9d
0x180018d9f  cmp     r9d, [rdx+70h]
0x180018da3  jb      loc_180018FD0
0x180018da9  test    r11d, r11d
0x180018dac  jz      loc_180018EFE
0x180018db2  test    r10d, r10d
0x180018db5  jz      loc_180018EFE
0x180018dbb  test    r8d, r8d
0x180018dbe  jnz     loc_180018EFE
0x180018dc4  mov     r8d, cs:g_Reference
0x180018dcb  lea     rbx, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180018dd2  shr     r8d, 1
0x180018dd5  lea     r9, aTeredoclientre; "TeredoClientReevaluateFiltersWorker"
0x180018ddc  and     r8d, 3FFFFFFFh
0x180018de3  mov     [rsp+48h+var_20], 74Ah
0x180018deb  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x180018df2  mov     [rsp+48h+var_28], rbx
0x180018df7  mov     ecx, 40000h
0x180018dfc  call    EventWrite0
0x180018e01  mov     eax, cs:g_Reference
0x180018e07  test    al, 1
0x180018e09  jnz     loc_180018EFE
0x180018e0f  lea     ecx, [rax+2]
0x180018e12  lock cmpxchg cs:g_Reference, ecx
0x180018e1a  jnz     short loc_180018E01
0x180018e1c  mov     r8d, 74Eh
0x180018e22  mov     rdx, rbx
0x180018e25  mov     rcx, rdi
0x180018e28  call    ReferenceCompartmentEx
0x180018e2d  lea     r8, CallbackEnvironment; pcbe
0x180018e34  mov     rdx, rdi; pv
0x180018e37  lea     rcx, TeredoClientReevaluateFiltersWorker; pfns
0x180018e3e  call    cs:__imp_TrySubmitThreadpoolCallback
0x180018e45  nop     dword ptr [rax+rax+00h]
0x180018e4a  test    eax, eax
0x180018e4c  jnz     loc_180018EFE
0x180018e52  lea     rdx, aTeredoProcessi; "Teredo processing filter changes: Faile"...
0x180018e59  mov     ecx, 100000h
0x180018e5e  call    EventWriteError0
0x180018e63  mov     r8d, 755h
0x180018e69  mov     rdx, rbx
0x180018e6c  mov     rcx, rdi
0x180018e6f  call    DereferenceCompartmentEx
0x180018e74  mov     r8d, 756h
0x180018e7a  lea     rcx, aTeredoclientre; "TeredoClientReevaluateFiltersWorker"
0x180018e81  mov     rdx, rbx
0x180018e84  call    DereferenceServiceEx
0x180018e89  jmp     short loc_180018EFE
0x180018e8b  lea     rcx, TeredoFiltersLock; lpCriticalSection
0x180018e92  call    cs:__imp_EnterCriticalSection
0x180018e99  nop     dword ptr [rax+rax+00h]
0x180018e9e  cmp     byte ptr [rdi+0AE4h], 1
0x180018ea5  jz      loc_180018F41
0x180018eab  lea     r14, [rdi+4C30h]
0x180018eb2  mov     rsi, [r14]
0x180018eb5  cmp     rsi, r14
0x180018eb8  jz      loc_180018F41
0x180018ebe  xor     ebp, ebp
0x180018ec0  mov     rax, [rbx+4]
0x180018ec4  sub     rax, [rsi+10h]
0x180018ec8  jnz     short loc_180018ED2
0x180018eca  mov     rax, [rbx+0Ch]
0x180018ece  sub     rax, [rsi+18h]
0x180018ed2  test    rax, rax
0x180018ed5  jz      loc_180018F63
0x180018edb  mov     rsi, [rsi]
0x180018ede  cmp     rsi, r14
0x180018ee1  jnz     short loc_180018EC0
0x180018ee3  lea     rcx, TeredoFiltersLock; lpCriticalSection
0x180018eea  call    cs:__imp_LeaveCriticalSection
0x180018ef1  nop     dword ptr [rax+rax+00h]
0x180018ef6  test    ebp, ebp
0x180018ef8  jnz     loc_180018DC4
0x180018efe  cmp     [rsp+48h+filter], 0
0x180018f04  jz      short loc_180018F17
0x180018f06  lea     rcx, [rsp+48h+filter]; p
0x180018f0b  call    cs:__imp_FwpmFreeMemory0
0x180018f12  nop     dword ptr [rax+rax+00h]
0x180018f17  mov     rbx, [rsp+48h+arg_10]
0x180018f1c  mov     rbp, [rsp+48h+arg_18]
0x180018f21  add     rsp, 30h
0x180018f25  pop     r14
0x180018f27  pop     rdi
0x180018f28  pop     rsi
0x180018f29  retn
0x180018f2b  mov     r8d, eax
0x180018f2e  lea     rdx, aTeredoProcessi_0; "Teredo processing filter changes: Unabl"...
0x180018f35  mov     ecx, 100000h
0x180018f3a  call    EventWriteError0
0x180018f3f  jmp     short loc_180018EFE
0x180018f41  lea     rcx, TeredoFiltersLock; lpCriticalSection
0x180018f48  call    cs:__imp_LeaveCriticalSection
0x180018f4f  nop     dword ptr [rax+rax+00h]
0x180018f54  jmp     short loc_180018EFE
0x180018f56  cmp     eax, 1001h
0x180018f5b  jz      loc_180018D6D
0x180018f61  jmp     short loc_180018EFE
0x180018f63  cmp     rsi, r14
0x180018f66  jz      loc_180018EE3
0x180018f6c  mov     rax, [rsi]
0x180018f6f  cmp     [rax+8], rsi
0x180018f73  jnz     short loc_180018FC9
0x180018f75  mov     rcx, [rsi+8]
0x180018f79  cmp     [rcx], rsi
0x180018f7c  jnz     short loc_180018FC9
0x180018f7e  mov     [rcx], rax
0x180018f81  mov     [rax+8], rcx
0x180018f85  call    cs:__imp_GetProcessHeap
0x180018f8c  nop     dword ptr [rax+rax+00h]
0x180018f91  mov     r8, rsi; lpMem
0x180018f94  xor     edx, edx; dwFlags
0x180018f96  mov     rcx, rax; hHeap
0x180018f99  call    cs:__imp_HeapFree
0x180018fa0  nop     dword ptr [rax+rax+00h]
0x180018fa5  cmp     [r14], r14
0x180018fa8  jnz     loc_180018EE3
0x180018fae  lea     rdx, aTeredoBlockFil; "Teredo Block Filter List is empty."
0x180018fb5  mov     ecx, 100000h
0x180018fba  mov     ebp, 1
0x180018fbf  call    EventWrite0
0x180018fc4  jmp     loc_180018EE3
0x180018fc9  mov     ecx, 3
0x180018fce  int     29h; Win8: RtlFailFast(ecx)
0x180018fd0  mov     rax, [rdx+78h]
0x180018fd4  lea     rcx, [r9+r9*4]
0x180018fd8  mov     rbx, [rax+rcx*8]
0x180018fdc  sub     rbx, qword ptr cs:FWPM_CONDITION_ARRIVAL_INTERFACE_TYPE.Data1
0x180018fe3  jnz     short loc_180018FF1
0x180018fe5  mov     rbx, [rax+rcx*8+8]
0x180018fea  sub     rbx, qword ptr cs:FWPM_CONDITION_ARRIVAL_INTERFACE_TYPE.Data4
0x180018ff1  test    rbx, rbx
0x180018ff4  jz      short loc_180019014
0x180018ff6  mov     rbx, [rax+rcx*8]
0x180018ffa  sub     rbx, qword ptr cs:FWPM_CONDITION_INTERFACE_TYPE.Data1
0x180019001  jnz     short loc_18001900F
0x180019003  mov     rbx, [rax+rcx*8+8]
0x180019008  sub     rbx, qword ptr cs:FWPM_CONDITION_INTERFACE_TYPE.Data4
0x18001900f  test    rbx, rbx
0x180019012  jnz     short loc_180019034
0x180019014  cmp     [rax+rcx*8+10h], r8d
0x180019019  jnz     short loc_180019034
0x18001901b  cmp     dword ptr [rax+rcx*8+18h], 3
0x180019020  jnz     short loc_180019034
0x180019022  cmp     dword ptr [rax+rcx*8+20h], 83h
0x18001902a  jnz     short loc_180019034
0x18001902c  mov     r11d, ebp
0x18001902f  jmp     loc_1800190BC
0x180019034  mov     rbx, [rax+rcx*8]
0x180019038  sub     rbx, qword ptr cs:FWPM_CONDITION_ARRIVAL_TUNNEL_TYPE.Data1
0x18001903f  jnz     short loc_18001904D
0x180019041  mov     rbx, [rax+rcx*8+8]
0x180019046  sub     rbx, qword ptr cs:FWPM_CONDITION_ARRIVAL_TUNNEL_TYPE.Data4
0x18001904d  test    rbx, rbx
0x180019050  jz      short loc_180019070
0x180019052  mov     rbx, [rax+rcx*8]
0x180019056  sub     rbx, qword ptr cs:FWPM_CONDITION_TUNNEL_TYPE.Data1
0x18001905d  jnz     short loc_18001906B
0x18001905f  mov     rbx, [rax+rcx*8+8]
0x180019064  sub     rbx, qword ptr cs:FWPM_CONDITION_TUNNEL_TYPE.Data4
0x18001906b  test    rbx, rbx
0x18001906e  jnz     short loc_18001908A
0x180019070  cmp     [rax+rcx*8+10h], r8d
0x180019075  jnz     short loc_18001908A
0x180019077  cmp     dword ptr [rax+rcx*8+18h], 3
0x18001907c  jnz     short loc_18001908A
0x18001907e  cmp     dword ptr [rax+rcx*8+20h], 0Eh
0x180019083  jnz     short loc_18001908A
0x180019085  mov     r10d, ebp
0x180019088  jmp     short loc_1800190BC
0x18001908a  mov     rbx, [rax+rcx*8]
0x18001908e  sub     rbx, qword ptr cs:FWPM_CONDITION_FLAGS.Data1
0x180019095  jnz     short loc_1800190A3
0x180019097  mov     rbx, [rax+rcx*8+8]
0x18001909c  sub     rbx, qword ptr cs:FWPM_CONDITION_FLAGS.Data4
0x1800190a3  test    rbx, rbx
0x1800190a6  jnz     short loc_1800190C4
0x1800190a8  cmp     dword ptr [rax+rcx*8+10h], 8
0x1800190ad  jnz     short loc_1800190C4
0x1800190af  cmp     dword ptr [rax+rcx*8+18h], 3
0x1800190b4  jnz     short loc_1800190C4
0x1800190b6  cmp     [rax+rcx*8+20h], ebp
0x1800190ba  jnz     short loc_1800190C4
0x1800190bc  inc     r9d
0x1800190bf  jmp     loc_180018D9F
0x1800190c4  mov     r8d, ebp
0x1800190c7  jmp     loc_180018DA9
```
