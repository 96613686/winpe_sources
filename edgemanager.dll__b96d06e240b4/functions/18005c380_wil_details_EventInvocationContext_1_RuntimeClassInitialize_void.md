# wil::details::EventInvocationContext<1>::RuntimeClassInitialize(void)

- ea: `0x18005c380`
- end: `0x18005c43e`
- name: `?RuntimeClassInitialize@?$EventInvocationContext@$00@details@wil@@QEAAJXZ`
- size: `190`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005aeac`

## callees

- `0x1800154cc`
- `0x180021270`
- `0x1800212f4`
- `0x1800376e4`
- `0x18005c380`
- `0x18005c774`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005c3fb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005c3fb`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18005c3c5`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18005c3c5`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18005c3ab`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18005c3ab`

## pseudocode

```c
__int64 __fastcall wil::details::EventInvocationContext<1>::RuntimeClassInitialize(char *pv)
{
  _QWORD *v1; // rbx
  __int64 v3; // rsi
  int v4; // eax
  unsigned int v5; // ebx
  struct _TP_WORK *ThreadpoolWork; // rax
  const char *v8; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v11; // [rsp+30h] [rbp+8h] BYREF

  v1 = pv + 72;
  v3 = *((_QWORD *)pv + 9);
  if ( v3 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
    CoDecrementMTAUsage(v3);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
  }
  *v1 = 0;
  v4 = CoIncrementMTAUsage(v1);
  v5 = v4;
  if ( v4 >= 0 )
  {
    ThreadpoolWork = CreateThreadpoolWork(wil::details::EventInvocationContext<1>::AsyncEventWorkCallback, pv, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      (struct _TP_WORK **)pv + 10,
      ThreadpoolWork);
    if ( *((_QWORD *)pv + 10) )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x1B6,
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\WrlEvent.h",
               v8);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\WrlEvent.h",
      (const char *)(unsigned int)v4,
      v9);
    return v5;
  }
}

```

## disassembly

```asm
0x18005c380  mov     [rsp+arg_8], rbx
0x18005c385  mov     [rsp+arg_10], rsi
0x18005c38a  push    rdi; int
0x18005c38b  sub     rsp, 20h
0x18005c38f  lea     rbx, [rcx+48h]
0x18005c393  mov     rdi, rcx
0x18005c396  mov     rsi, [rbx]
0x18005c399  test    rsi, rsi
0x18005c39c  jz      short loc_18005C3BB
0x18005c39e  lea     rcx, [rsp+28h+arg_0]; this
0x18005c3a3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005c3a8  mov     rcx, rsi
0x18005c3ab  call    cs:__imp_CoDecrementMTAUsage
0x18005c3b1  lea     rcx, [rsp+28h+arg_0]; this
0x18005c3b6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005c3bb  mov     rcx, rbx
0x18005c3be  mov     qword ptr [rbx], 0
0x18005c3c5  call    cs:__imp_CoIncrementMTAUsage
0x18005c3cb  mov     ebx, eax
0x18005c3cd  test    eax, eax
0x18005c3cf  jns     short loc_18005C3EE
0x18005c3d1  mov     rcx, [rsp+28h]; this
0x18005c3d6  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\WrlEv"...
0x18005c3dd  mov     r9d, eax; char *
0x18005c3e0  mov     edx, 1B4h; void *
0x18005c3e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c3ea  mov     eax, ebx
0x18005c3ec  jmp     short loc_18005C42E
0x18005c3ee  xor     r8d, r8d; pcbe
0x18005c3f1  lea     rcx, ?AsyncEventWorkCallback@?$EventInvocationContext@$00@details@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18005c3f8  mov     rdx, rdi; pv
0x18005c3fb  call    cs:__imp_CreateThreadpoolWork
0x18005c401  mov     rdx, rax
0x18005c404  lea     rcx, [rdi+50h]
0x18005c408  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18005c40d  cmp     qword ptr [rdi+50h], 0
0x18005c412  jnz     short loc_18005C42C
0x18005c414  mov     rcx, [rsp+28h]; this
0x18005c419  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\WrlEv"...
0x18005c420  mov     edx, 1B6h; void *
0x18005c425  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c42a  jmp     short loc_18005C42E
0x18005c42c  xor     eax, eax
0x18005c42e  mov     rbx, [rsp+28h+arg_8]
0x18005c433  mov     rsi, [rsp+28h+arg_10]
0x18005c438  add     rsp, 20h
0x18005c43c  pop     rdi
0x18005c43d  retn
```
