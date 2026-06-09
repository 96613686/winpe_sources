# DacAsyncCallbackRoutine(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)

- ea: `0x180002730`
- end: `0x180002838`
- name: `?DacAsyncCallbackRoutine@@YAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z`
- size: `264`
- prototype: `void __fastcall(PRPC_ASYNC_STATE pAsync, void *, enum _RPC_ASYNC_EVENT)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002730`
- `0x180002840`
- `0x180002f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027d6`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x180002794`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x180002794`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000277b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000277b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800027a2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800027a2`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800027f3`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800027f3`

## pseudocode

```c
void __fastcall DacAsyncCallbackRoutine(PRPC_ASYNC_STATE pAsync, void *a2, enum _RPC_ASYNC_EVENT a3)
{
  char *UserInfo; // rdi
  int v5; // eax
  _DWORD *v6; // rbx
  int Reply; // [rsp+50h] [rbp+8h] BYREF

  Reply = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
  UserInfo = (char *)pAsync->UserInfo;
  EnterCriticalSection((LPCRITICAL_SECTION)(UserInfo + 16));
  while ( 1 )
  {
    v5 = RpcAsyncCompleteCall(pAsync, &Reply);
    if ( !v5 )
      break;
    if ( v5 != 997 )
    {
      if ( v5 >= 1 )
        v5 = (unsigned __int16)v5 | 0x80010000;
      Reply = v5;
      break;
    }
    SleepEx(0x1F4u, 1);
  }
  v6 = (_DWORD *)*((_QWORD *)UserInfo + 9);
  *((_QWORD *)UserInfo + 9) = 0;
  *((_DWORD *)UserInfo + 16) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(UserInfo + 16));
  v6[34] = Reply;
  if ( !TrySubmitThreadpoolCallback(DacClientCallbackThreadProc, v6, 0) )
    DacClientCallbackThreadProc(0, v6);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
}

```

## disassembly

```asm
0x180002730  push    rbx
0x180002732  push    rsi
0x180002733  push    rdi
0x180002734  push    r14
0x180002736  sub     rsp, 28h
0x18000273a  mov     rbx, rcx
0x18000273d  mov     [rsp+48h+Reply], 0
0x180002745  mov     rcx, cs:WPP_GLOBAL_Control
0x18000274c  lea     r14, WPP_GLOBAL_Control
0x180002753  cmp     rcx, r14
0x180002756  jz      short loc_180002773
0x180002758  cmp     byte ptr [rcx+19h], 4
0x18000275c  jb      short loc_180002773
0x18000275e  mov     rcx, [rcx+10h]
0x180002762  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x180002769  mov     edx, 0Fh
0x18000276e  call    WPP_SF_s
0x180002773  mov     rdi, [rbx+18h]
0x180002777  lea     rcx, [rdi+10h]; lpCriticalSection
0x18000277b  call    cs:__imp_EnterCriticalSection
0x180002781  jmp     short loc_18000279A
0x180002783  cmp     eax, 3E5h
0x180002788  jnz     short loc_1800027AE
0x18000278a  mov     edx, 1; bAlertable
0x18000278f  mov     ecx, 1F4h; dwMilliseconds
0x180002794  call    cs:__imp_SleepEx
0x18000279a  lea     rdx, [rsp+48h+Reply]; Reply
0x18000279f  mov     rcx, rbx; pAsync
0x1800027a2  call    cs:__imp_RpcAsyncCompleteCall
0x1800027a8  test    eax, eax
0x1800027aa  jnz     short loc_180002783
0x1800027ac  jmp     short loc_1800027BF
0x1800027ae  cmp     eax, 1
0x1800027b1  jl      short loc_1800027BB
0x1800027b3  movzx   eax, ax
0x1800027b6  or      eax, 80010000h
0x1800027bb  mov     [rsp+48h+Reply], eax
0x1800027bf  mov     rbx, [rdi+48h]
0x1800027c3  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800027c7  mov     qword ptr [rdi+48h], 0
0x1800027cf  mov     dword ptr [rdi+40h], 0
0x1800027d6  call    cs:__imp_LeaveCriticalSection
0x1800027dc  mov     eax, [rsp+48h+Reply]
0x1800027e0  lea     rcx, ?DacClientCallbackThreadProc@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x1800027e7  xor     r8d, r8d; pcbe
0x1800027ea  mov     [rbx+88h], eax
0x1800027f0  mov     rdx, rbx; pv
0x1800027f3  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800027f9  test    eax, eax
0x1800027fb  jnz     short loc_180002807
0x1800027fd  mov     rdx, rbx; Context
0x180002800  xor     ecx, ecx; Instance
0x180002802  call    ?DacClientCallbackThreadProc@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; DacClientCallbackThreadProc(_TP_CALLBACK_INSTANCE *,void *)
0x180002807  mov     rcx, cs:WPP_GLOBAL_Control
0x18000280e  cmp     rcx, r14
0x180002811  jz      short loc_18000282E
0x180002813  cmp     byte ptr [rcx+19h], 4
0x180002817  jb      short loc_18000282E
0x180002819  mov     rcx, [rcx+10h]
0x18000281d  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x180002824  mov     edx, 10h
0x180002829  call    WPP_SF_s
0x18000282e  add     rsp, 28h
0x180002832  pop     r14
0x180002834  pop     rdi
0x180002835  pop     rsi
0x180002836  pop     rbx
0x180002837  retn
```
