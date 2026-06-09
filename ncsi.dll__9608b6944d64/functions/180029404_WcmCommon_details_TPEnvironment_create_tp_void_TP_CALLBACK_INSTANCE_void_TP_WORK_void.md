# WcmCommon::details::TPEnvironment::create_tp(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)

- ea: `0x180029404`
- end: `0x18002946a`
- name: `?create_tp@TPEnvironment@details@WcmCommon@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180029228`
- `0x18006db64`

## callees

- `0x180029404`
- `0x180055860`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180029434`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180029434`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PTP_WORK *__fastcall WcmCommon::details::TPEnvironment::create_tp(
        __int64 a1,
        PTP_WORK *a2,
        void (__stdcall *a3)(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work),
        void *a4)
{
  PTP_WORK ThreadpoolWork; // rax
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a2 = 0;
  ThreadpoolWork = CreateThreadpoolWork(a3, a4, (PTP_CALLBACK_ENVIRON)(a1 & -(__int64)(*(_QWORD *)(a1 + 72) != 0)));
  *a2 = ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecore\\net\\inc\\wcm_work_queue.h",
      v6);
  return a2;
}

```

## disassembly

```asm
0x180029404  mov     [rsp+arg_8], rdx
0x180029409  push    rbx
0x18002940a  sub     rsp, 30h
0x18002940e  mov     r10, r8
0x180029411  mov     rbx, rdx
0x180029414  mov     [rsp+38h+var_18], 0
0x18002941c  xor     eax, eax
0x18002941e  mov     [rdx], rax
0x180029421  mov     rax, [rcx+48h]
0x180029425  neg     rax
0x180029428  sbb     r8, r8
0x18002942b  and     r8, rcx; pcbe
0x18002942e  mov     rdx, r9; pv
0x180029431  mov     rcx, r10; pfnwk
0x180029434  call    cs:__imp_CreateThreadpoolWork
0x18002943a  mov     [rbx], rax
0x18002943d  mov     [rsp+38h+var_18], 1
0x180029445  test    rax, rax
0x180029448  jz      short loc_180029453
0x18002944a  mov     rax, rbx
0x18002944d  add     rsp, 30h
0x180029451  pop     rbx
0x180029452  retn
0x180029453  mov     rcx, [rsp+38h]; this
0x180029458  lea     r8, aOnecoreNetIncW; "onecore\\net\\inc\\wcm_work_queue.h"
0x18002945f  mov     edx, 75h ; 'u'; void *
0x180029464  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
