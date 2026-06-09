# HcsClient::NotificationWorker::NotificationWorker(std::shared_ptr<HcsClient::OperationTracker>)

- ea: `0x180048228`
- end: `0x18004833c`
- name: `??0NotificationWorker@HcsClient@@QEAA@V?$shared_ptr@VOperationTracker@HcsClient@@@std@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004a270`

## callees

- `0x18001017c`
- `0x180048228`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800482bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800482bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800482a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800482a9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180048297`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180048297`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800482b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800482b4`

## string_xrefs

- `0x18004832a`: `onecore\vm\compute\dll\lib\core\operationtracker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall HcsClient::NotificationWorker::NotificationWorker(_QWORD *pv, _QWORD *a2)
{
  __int64 v4; // rax
  PTP_WORK ThreadpoolWork; // rbp
  const char *v6; // r9
  struct _TP_WORK *v7; // r14
  DWORD LastError; // ebx
  volatile signed __int32 *v9; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *pv = 0;
  pv[1] = 0;
  pv[2] = 0;
  *((_BYTE *)pv + 24) = 0;
  pv[4] = 0;
  pv[5] = 0;
  pv[6] = 0;
  pv[7] = 0;
  pv[8] = 0;
  pv[9] = 0;
  if ( a2[1] )
  {
    pv[8] = *a2;
    v4 = a2[1];
    pv[9] = v4;
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 12));
  }
  ThreadpoolWork = CreateThreadpoolWork(HcsClient::NotificationWorker::Worker, pv, 0);
  v7 = (struct _TP_WORK *)pv[4];
  if ( v7 )
  {
    LastError = GetLastError();
    CloseThreadpoolWork(v7);
    SetLastError(LastError);
  }
  pv[4] = ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\operationtracker.cpp",
      v6);
  v9 = (volatile signed __int32 *)a2[1];
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return pv;
}

```

## disassembly

```asm
0x180048228  mov     rax, rsp
0x18004822b  mov     [rax+18h], rbx
0x18004822f  mov     [rax+20h], rbp
0x180048233  mov     [rax+10h], rdx
0x180048237  mov     [rax+8], rcx
0x18004823b  push    rsi
0x18004823c  push    rdi
0x18004823d  push    r14
0x18004823f  sub     rsp, 20h
0x180048243  mov     rsi, rdx
0x180048246  mov     rdi, rcx
0x180048249  xor     eax, eax
0x18004824b  mov     [rcx], rax
0x18004824e  mov     [rcx+8], rax
0x180048252  mov     [rcx+10h], rax
0x180048256  mov     [rcx+18h], al
0x180048259  mov     [rcx+20h], rax
0x18004825d  mov     [rcx+28h], rax
0x180048261  mov     [rcx+30h], rax
0x180048265  mov     [rcx+38h], rax
0x180048269  mov     [rcx+40h], rax
0x18004826d  mov     [rcx+48h], rax
0x180048271  cmp     [rdx+8], rax
0x180048275  jz      short loc_18004828A
0x180048277  mov     rax, [rdx]
0x18004827a  mov     [rcx+40h], rax
0x18004827e  mov     rax, [rdx+8]
0x180048282  mov     [rcx+48h], rax
0x180048286  lock inc dword ptr [rax+0Ch]
0x18004828a  xor     r8d, r8d; pcbe
0x18004828d  mov     rdx, rdi; pv
0x180048290  lea     rcx, ?Worker@NotificationWorker@HcsClient@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180048297  call    cs:__imp_CreateThreadpoolWork
0x18004829d  mov     rbp, rax
0x1800482a0  mov     r14, [rdi+20h]
0x1800482a4  test    r14, r14
0x1800482a7  jz      short loc_1800482C2
0x1800482a9  call    cs:__imp_GetLastError
0x1800482af  mov     ebx, eax
0x1800482b1  mov     rcx, r14; pwk
0x1800482b4  call    cs:__imp_CloseThreadpoolWork
0x1800482ba  mov     ecx, ebx; dwErrCode
0x1800482bc  call    cs:__imp_SetLastError
0x1800482c2  mov     [rdi+20h], rbp
0x1800482c6  test    rbp, rbp
0x1800482c9  setz    al
0x1800482cc  mov     rcx, [rsp+38h]; this
0x1800482d1  test    al, al
0x1800482d3  jnz     short loc_18004832A
0x1800482d5  mov     rbx, [rsi+8]
0x1800482d9  test    rbx, rbx
0x1800482dc  jz      short loc_180048314
0x1800482de  or      esi, 0FFFFFFFFh
0x1800482e1  mov     eax, esi
0x1800482e3  lock xadd [rbx+8], eax
0x1800482e8  add     eax, esi
0x1800482ea  jnz     short loc_180048314
0x1800482ec  mov     rax, [rbx]
0x1800482ef  mov     rcx, rbx
0x1800482f2  mov     rax, [rax]
0x1800482f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482fa  mov     eax, esi
0x1800482fc  lock xadd [rbx+0Ch], eax
0x180048301  add     eax, esi
0x180048303  jnz     short loc_180048314
0x180048305  mov     rax, [rbx]
0x180048308  mov     rcx, rbx
0x18004830b  mov     rax, [rax+8]
0x18004830f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048314  mov     rax, rdi
0x180048317  mov     rbx, [rsp+38h+arg_10]
0x18004831c  mov     rbp, [rsp+38h+arg_18]
0x180048321  add     rsp, 20h
0x180048325  pop     r14
0x180048327  pop     rdi
0x180048328  pop     rsi
0x180048329  retn
0x18004832a  lea     r8, aOnecoreVmCompu_7; "onecore\\vm\\compute\\dll\\lib\\core\\o"...
0x180048331  mov     edx, 72h ; 'r'; void *
0x180048336  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
