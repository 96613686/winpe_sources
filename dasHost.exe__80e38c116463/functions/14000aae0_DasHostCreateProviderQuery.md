# DasHostCreateProviderQuery

- ea: `0x14000aae0`
- end: `0x14000ace9`
- name: `DasHostCreateProviderQuery`
- size: `521`
- prototype: `__int64 __fastcall(__int64, GUID *, int, __int64, const unsigned __int16 *, __int64, __int64, __int64, HANDLE **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140008eec`
- `0x140008f88`
- `0x14000aae0`
- `0x140011ea4`
- `0x140015cc4`
- `0x1400160d8`
- `0x14001c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000ab49`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000ab49`

## pseudocode

```c
__int64 __fastcall DasHostCreateProviderQuery(
        __int64 a1,
        GUID *a2,
        int a3,
        __int64 a4,
        const unsigned __int16 *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        HANDLE **a9)
{
  unsigned int ProviderByName; // eax
  int v13; // edx
  __int64 v14; // rcx
  int v15; // r8d
  __int64 v16; // r9
  volatile signed __int32 *v17; // rbx
  unsigned int started; // edi
  unsigned int v19; // r8d
  HANDLE *v20; // r9
  const unsigned __int16 *v21; // rdx
  __int64 v22; // rcx
  int v24; // [rsp+28h] [rbp-90h]
  __int64 v25; // [rsp+60h] [rbp-58h] BYREF
  _OWORD v26[4]; // [rsp+70h] [rbp-48h] BYREF

  v26[0] = 0;
  v25 = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      a3,
      14,
      &WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids);
  EventActivityIdControl(2u, a2);
  ProviderByName = DAS::ProviderManagement::ProviderManager::GetProviderByName((__int64)g_providerManager, a4, v26);
  v17 = (volatile signed __int32 *)*((_QWORD *)&v26[0] + 1);
  started = ProviderByName;
  if ( !ProviderByName )
  {
    if ( a3 == 2 )
    {
      v19 = 4;
    }
    else
    {
      v19 = 0;
      if ( a3 == 1 )
        v19 = 2;
    }
    if ( *((_QWORD *)&v26[0] + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v26[0] + 1) + 8LL));
    started = CreateProviderQueryEntry(v14, v26, v19, v16, a8, &v25);
    if ( !started )
    {
      v20 = (HANDLE *)v25;
      v21 = a5;
      *(_QWORD *)(v25 + 160) = a7;
      *a9 = v20;
      if ( !a5 )
        goto LABEL_15;
      v22 = -1;
      do
        ++v22;
      while ( a5[v22] );
      if ( !v22 )
LABEL_15:
        v21 = 0;
      started = StartProviderQuery(
                  (__int64)a2,
                  v21,
                  a3,
                  (__int64)v20,
                  v20,
                  (void *)a6,
                  *(_DWORD *)(a6 + 64),
                  *(void **)(a6 + 72),
                  *(_DWORD *)(a6 + 96),
                  *(_QWORD *)(a6 + 104),
                  0,
                  v20[20]);
      if ( started )
        *a9 = 0;
    }
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v13,
      v15,
      15,
      &WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids,
      v24,
      started);
  if ( v17 )
  {
    if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  return started;
}

```

## disassembly

```asm
0x14000aae0  push    rbx
0x14000aae2  push    rbp
0x14000aae3  push    rsi
0x14000aae4  push    rdi
0x14000aae5  push    r12
0x14000aae7  push    r14
0x14000aae9  push    r15
0x14000aaeb  sub     rsp, 80h
0x14000aaf2  xorps   xmm0, xmm0
0x14000aaf5  xor     r12d, r12d
0x14000aaf8  movdqa  [rsp+0B8h+var_48], xmm0
0x14000aafe  mov     rbx, r9
0x14000ab01  mov     [rsp+0B8h+var_58], r12
0x14000ab06  mov     esi, r8d
0x14000ab09  mov     rbp, rdx
0x14000ab0c  lea     rax, WPP_RECORDER_INITIALIZED
0x14000ab13  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ab1a  lea     r15, WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids
0x14000ab21  jz      short loc_14000AB3D
0x14000ab23  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ab2a  lea     r9d, [r12+0Eh]; int
0x14000ab2f  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x14000ab34  mov     rcx, [rcx+28h]; int
0x14000ab38  call    WPP_RECORDER_SF_s
0x14000ab3d  mov     r14d, 2
0x14000ab43  mov     rdx, rbp; ActivityId
0x14000ab46  mov     ecx, r14d; ControlCode
0x14000ab49  call    cs:__imp_EventActivityIdControl
0x14000ab4f  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x14000ab56  lea     r8, [rsp+0B8h+var_48]
0x14000ab5b  mov     rdx, rbx
0x14000ab5e  call    ?GetProviderByName@ProviderManager@ProviderManagement@DAS@@QEAAJPEBGAEAV?$shared_ptr@VProviderContext@@@std@@@Z; DAS::ProviderManagement::ProviderManager::GetProviderByName(ushort const *,std::shared_ptr<ProviderContext> &)
0x14000ab63  mov     rbx, qword ptr [rsp+0B8h+var_48+8]
0x14000ab68  mov     edi, eax
0x14000ab6a  test    eax, eax
0x14000ab6c  jnz     loc_14000AC6A
0x14000ab72  cmp     esi, r14d
0x14000ab75  jnz     short loc_14000AB7D
0x14000ab77  lea     r8d, [r14+2]
0x14000ab7b  jmp     short loc_14000AB87
0x14000ab7d  cmp     esi, 1
0x14000ab80  mov     r8d, r12d
0x14000ab83  cmovz   r8d, r14d
0x14000ab87  test    rbx, rbx
0x14000ab8a  jz      short loc_14000AB90
0x14000ab8c  lock inc dword ptr [rbx+8]
0x14000ab90  movaps  xmm0, [rsp+0B8h+var_48]
0x14000ab95  lea     rax, [rsp+0B8h+var_58]
0x14000ab9a  mov     qword ptr [rsp+0B8h+var_90], rax
0x14000ab9f  lea     rdx, [rsp+0B8h+var_48]
0x14000aba4  mov     rax, [rsp+0B8h+arg_38]
0x14000abac  mov     [rsp+0B8h+MessageGuid], rax
0x14000abb1  movdqa  [rsp+0B8h+var_48], xmm0
0x14000abb7  call    ?CreateProviderQueryEntry@@YAJPEAXV?$shared_ptr@VProviderContext@@@std@@KPEAU_DAS_LOCKED_LIST@@0PEAPEAU_PROVIDER_QUERY_ENTRY@@@Z; CreateProviderQueryEntry(void *,std::shared_ptr<ProviderContext>,ulong,_DAS_LOCKED_LIST *,void *,_PROVIDER_QUERY_ENTRY * *)
0x14000abbc  mov     edi, eax
0x14000abbe  test    eax, eax
0x14000abc0  jnz     loc_14000AC6A
0x14000abc6  mov     r9, [rsp+0B8h+var_58]
0x14000abcb  mov     rax, [rsp+0B8h+arg_30]
0x14000abd3  mov     r14, [rsp+0B8h+arg_40]
0x14000abdb  mov     rdx, [rsp+0B8h+arg_20]
0x14000abe3  mov     [r9+0A0h], rax
0x14000abea  mov     rax, [rsp+0B8h+arg_28]
0x14000abf2  mov     [r14], r9
0x14000abf5  mov     r8, [r9+0A0h]
0x14000abfc  mov     r10, [rax+68h]
0x14000ac00  mov     r11d, [rax+60h]
0x14000ac04  mov     rdi, [rax+48h]
0x14000ac08  mov     r15d, [rax+40h]
0x14000ac0c  test    rdx, rdx
0x14000ac0f  jz      short loc_14000AC24
0x14000ac11  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000ac15  inc     rcx
0x14000ac18  cmp     [rdx+rcx*2], r12w
0x14000ac1d  jnz     short loc_14000AC15
0x14000ac1f  test    rcx, rcx
0x14000ac22  jnz     short loc_14000AC27
0x14000ac24  mov     rdx, r12
0x14000ac27  mov     [rsp+0B8h+var_60], r8
0x14000ac2c  mov     rcx, rbp
0x14000ac2f  mov     [rsp+0B8h+var_68], r12
0x14000ac34  mov     r8d, esi
0x14000ac37  mov     [rsp+0B8h+var_70], r10
0x14000ac3c  mov     [rsp+0B8h+var_78], r11d
0x14000ac41  mov     [rsp+0B8h+var_80], rdi
0x14000ac46  mov     dword ptr [rsp+0B8h+var_88], r15d
0x14000ac4b  mov     qword ptr [rsp+0B8h+var_90], rax; int
0x14000ac50  mov     [rsp+0B8h+MessageGuid], r9
0x14000ac55  call    ?StartProviderQuery@@YAJPEBU_GUID@@PEBGW4_PROVIDER_QUERY_TYPE@@PEAU_PROVIDER_QUERY_ENTRY@@PEAXPEAU_DEV_QUERY_DATA@@KPEBU_DEVPROPCOMPKEY@@KPEBU_DEV_QUERY_PARAMETER@@PEAU_DAS_LOCKED_LIST@@4@Z; StartProviderQuery(_GUID const *,ushort const *,_PROVIDER_QUERY_TYPE,_PROVIDER_QUERY_ENTRY *,void *,_DEV_QUERY_DATA *,ulong,_DEVPROPCOMPKEY const *,ulong,_DEV_QUERY_PARAMETER const *,_DAS_LOCKED_LIST *,void *)
0x14000ac5a  lea     r15, WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids
0x14000ac61  mov     edi, eax
0x14000ac63  test    eax, eax
0x14000ac65  jz      short loc_14000AC6A
0x14000ac67  mov     [r14], r12
0x14000ac6a  lea     rax, WPP_RECORDER_INITIALIZED
0x14000ac71  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ac78  jz      short loc_14000AC99
0x14000ac7a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ac81  mov     r9d, 0Fh; int
0x14000ac87  mov     dword ptr [rsp+0B8h+var_88], edi; char
0x14000ac8b  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x14000ac90  mov     rcx, [rcx+28h]; int
0x14000ac94  call    WPP_RECORDER_SF_sd
0x14000ac99  test    rbx, rbx
0x14000ac9c  jz      short loc_14000ACD5
0x14000ac9e  or      eax, 0FFFFFFFFh
0x14000aca1  lock xadd [rbx+8], eax
0x14000aca6  cmp     eax, 1
0x14000aca9  jnz     short loc_14000ACD5
0x14000acab  mov     rax, [rbx]
0x14000acae  mov     rcx, rbx
0x14000acb1  mov     rax, [rax]
0x14000acb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000acb9  or      eax, 0FFFFFFFFh
0x14000acbc  lock xadd [rbx+0Ch], eax
0x14000acc1  cmp     eax, 1
0x14000acc4  jnz     short loc_14000ACD5
0x14000acc6  mov     rax, [rbx]
0x14000acc9  mov     rcx, rbx
0x14000accc  mov     rax, [rax+8]
0x14000acd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000acd5  mov     eax, edi
0x14000acd7  add     rsp, 80h
0x14000acde  pop     r15
0x14000ace0  pop     r14
0x14000ace2  pop     r12
0x14000ace4  pop     rdi
0x14000ace5  pop     rsi
0x14000ace6  pop     rbp
0x14000ace7  pop     rbx
0x14000ace8  retn
```
