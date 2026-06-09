# ClientOperationCompleter::ClientOperationCompleter(std::shared_ptr<ClientOperation> const &)

- ea: `0x18003479c`
- end: `0x18003495f`
- name: `??0ClientOperationCompleter@@QEAA@AEBV?$shared_ptr@VClientOperation@@@std@@@Z`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180036ae0`

## callees

- `0x1800067e4`
- `0x180006bf8`
- `0x180006d80`
- `0x18001017c`
- `0x18002a700`
- `0x18003479c`
- `0x1800355b8`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034929`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034916`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180034904`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180034904`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180034921`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180034921`

## string_xrefs

- `0x18003494d`: `onecore\vm\compute\dll\lib\core\ClientOperation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ClientOperationCompleter::ClientOperationCompleter(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  char *v5; // rbx
  ClientOperationCompleter::CompleteContext *v6; // rbp
  _QWORD *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rcx
  volatile signed __int32 *v10; // rbx
  PTP_WORK ThreadpoolWork; // rsi
  const char *v12; // r9
  struct _TP_WORK *v13; // rbp
  DWORD LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v4 = *(_QWORD *)(a2 + 8);
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
  *(_QWORD *)a1 = *(_QWORD *)a2;
  *(_QWORD *)(a1 + 8) = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  if ( ClientOperation::HasCompletionCallback(*(PSRWLOCK *)a2) )
  {
    v5 = (char *)operator new(0x48u);
    *((_DWORD *)v5 + 5) = 0;
    *((_QWORD *)v5 + 8) = 0;
    *(_QWORD *)v5 = 0;
    *((_QWORD *)v5 + 1) = 0;
    *((_DWORD *)v5 + 4) = -2147418113;
    *((_QWORD *)v5 + 3) = 0;
    *((_DWORD *)v5 + 8) = -1;
    *((_DWORD *)v5 + 9) = 0;
    *(_OWORD *)(v5 + 40) = 0;
    *((_QWORD *)v5 + 7) = 0;
    `eh vector constructor iterator'(
      v5 + 40,
      8u,
      3u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>);
    v5[64] = 0;
    v6 = *(ClientOperationCompleter::CompleteContext **)(a1 + 24);
    *(_QWORD *)(a1 + 24) = v5;
    if ( v6 )
    {
      ClientOperationCompleter::CompleteContext::~CompleteContext(v6);
      operator delete(v6, 0x48u);
    }
    v7 = *(_QWORD **)(a1 + 24);
    v8 = *(_QWORD *)(a2 + 8);
    if ( v8 )
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
    v9 = *(_QWORD *)(a2 + 8);
    *v7 = *(_QWORD *)a2;
    v10 = (volatile signed __int32 *)v7[1];
    v7[1] = v9;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    ThreadpoolWork = CreateThreadpoolWork(ClientOperationCompleter::CompleteWorker, *(PVOID *)(a1 + 24), 0);
    v13 = *(struct _TP_WORK **)(a1 + 16);
    if ( v13 )
    {
      LastError = GetLastError();
      CloseThreadpoolWork(v13);
      SetLastError(LastError);
    }
    *(_QWORD *)(a1 + 16) = ThreadpoolWork;
    if ( !ThreadpoolWork )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x171,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\ClientOperation.h",
        v12);
  }
  return a1;
}

```

## disassembly

```asm
0x18003479c  mov     [rsp+arg_10], rbx
0x1800347a1  push    rbp
0x1800347a2  push    rsi
0x1800347a3  push    rdi
0x1800347a4  sub     rsp, 40h
0x1800347a8  mov     rsi, rdx
0x1800347ab  mov     rdi, rcx
0x1800347ae  mov     [rsp+58h+var_20], rcx
0x1800347b3  mov     qword ptr [rcx], 0
0x1800347ba  mov     qword ptr [rcx+8], 0
0x1800347c2  mov     rax, [rdx+8]
0x1800347c6  test    rax, rax
0x1800347c9  jz      short loc_1800347CF
0x1800347cb  lock inc dword ptr [rax+8]
0x1800347cf  mov     rax, [rdx]
0x1800347d2  mov     [rcx], rax
0x1800347d5  mov     rax, [rdx+8]
0x1800347d9  mov     [rcx+8], rax
0x1800347dd  mov     qword ptr [rcx+10h], 0
0x1800347e5  mov     qword ptr [rcx+18h], 0
0x1800347ed  mov     rcx, [rdx]; SRWLock
0x1800347f0  call    ?HasCompletionCallback@ClientOperation@@QEAA_NXZ; ClientOperation::HasCompletionCallback(void)
0x1800347f5  test    al, al
0x1800347f7  jz      loc_18003493D
0x1800347fd  mov     ecx, 48h ; 'H'; Size
0x180034802  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034807  mov     rbx, rax
0x18003480a  mov     dword ptr [rax+14h], 0
0x180034811  mov     qword ptr [rax+40h], 0
0x180034819  mov     qword ptr [rax], 0
0x180034820  mov     qword ptr [rax+8], 0
0x180034828  mov     dword ptr [rax+10h], 8000FFFFh
0x18003482f  mov     qword ptr [rax+18h], 0
0x180034837  mov     dword ptr [rax+20h], 0FFFFFFFFh
0x18003483e  xor     eax, eax
0x180034840  mov     [rbx+24h], eax
0x180034843  lea     rcx, [rbx+28h]; void *
0x180034847  xorps   xmm0, xmm0
0x18003484a  movups  xmmword ptr [rcx], xmm0
0x18003484d  mov     [rcx+10h], rax
0x180034851  lea     rax, ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x180034858  mov     [rsp+58h+var_38], rax; void (*)(void *)
0x18003485d  lea     r9, ??0?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180034864  mov     edx, 8; unsigned __int64
0x180034869  lea     r8d, [rdx-5]; unsigned __int64
0x18003486d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180034872  mov     byte ptr [rbx+40h], 0
0x180034876  mov     rbp, [rdi+18h]
0x18003487a  mov     [rdi+18h], rbx
0x18003487e  test    rbp, rbp
0x180034881  jz      short loc_180034898
0x180034883  mov     rcx, rbp; this
0x180034886  call    ??1CompleteContext@ClientOperationCompleter@@QEAA@XZ; ClientOperationCompleter::CompleteContext::~CompleteContext(void)
0x18003488b  mov     edx, 48h ; 'H'; unsigned __int64
0x180034890  mov     rcx, rbp; void *
0x180034893  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180034898  mov     rdx, [rdi+18h]
0x18003489c  mov     rax, [rsi+8]
0x1800348a0  test    rax, rax
0x1800348a3  jz      short loc_1800348A9
0x1800348a5  lock inc dword ptr [rax+8]
0x1800348a9  mov     rcx, [rsi+8]
0x1800348ad  mov     rax, [rsi]
0x1800348b0  mov     [rdx], rax
0x1800348b3  mov     rbx, [rdx+8]
0x1800348b7  mov     [rdx+8], rcx
0x1800348bb  test    rbx, rbx
0x1800348be  jz      short loc_1800348F6
0x1800348c0  or      esi, 0FFFFFFFFh
0x1800348c3  mov     eax, esi
0x1800348c5  lock xadd [rbx+8], eax
0x1800348ca  add     eax, esi
0x1800348cc  jnz     short loc_1800348F6
0x1800348ce  mov     rax, [rbx]
0x1800348d1  mov     rcx, rbx
0x1800348d4  mov     rax, [rax]
0x1800348d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348dc  mov     eax, esi
0x1800348de  lock xadd [rbx+0Ch], eax
0x1800348e3  add     eax, esi
0x1800348e5  jnz     short loc_1800348F6
0x1800348e7  mov     rax, [rbx]
0x1800348ea  mov     rcx, rbx
0x1800348ed  mov     rax, [rax+8]
0x1800348f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348f6  xor     r8d, r8d; pcbe
0x1800348f9  mov     rdx, [rdi+18h]; pv
0x1800348fd  lea     rcx, ?CompleteWorker@ClientOperationCompleter@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180034904  call    cs:__imp_CreateThreadpoolWork
0x18003490a  mov     rsi, rax
0x18003490d  mov     rbp, [rdi+10h]
0x180034911  test    rbp, rbp
0x180034914  jz      short loc_18003492F
0x180034916  call    cs:__imp_GetLastError
0x18003491c  mov     ebx, eax
0x18003491e  mov     rcx, rbp; pwk
0x180034921  call    cs:__imp_CloseThreadpoolWork
0x180034927  mov     ecx, ebx; dwErrCode
0x180034929  call    cs:__imp_SetLastError
0x18003492f  mov     [rdi+10h], rsi
0x180034933  mov     rcx, [rsp+58h]; this
0x180034938  test    rsi, rsi
0x18003493b  jz      short loc_18003494D
0x18003493d  mov     rax, rdi
0x180034940  mov     rbx, [rsp+58h+arg_10]
0x180034945  add     rsp, 40h
0x180034949  pop     rdi
0x18003494a  pop     rsi
0x18003494b  pop     rbp
0x18003494c  retn
0x18003494d  lea     r8, aOnecoreVmCompu_22; "onecore\\vm\\compute\\dll\\lib\\core\\C"...
0x180034954  mov     edx, 171h; void *
0x180034959  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
