# WcmCommon::details::TPEnvironment::create_tp(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)

- ea: `0x180030134`
- end: `0x18003019a`
- name: `?create_tp@TPEnvironment@details@WcmCommon@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002ed64`
- `0x18002ee10`

## callees

- `0x18002ffe0`
- `0x180030134`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180030165`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180030165`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PTP_WORK *__fastcall WcmCommon::details::TPEnvironment::create_tp(__int64 a1, PTP_WORK *a2, __int64 a3, void *a4)
{
  PTP_WORK ThreadpoolWork; // rax
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a2 = 0;
  ThreadpoolWork = CreateThreadpoolWork(
                     (PTP_WORK_CALLBACK)WcmCommon::ThreadPoolWorkQueue::WorkCallback,
                     a4,
                     (PTP_CALLBACK_ENVIRON)(a1 & -(__int64)(*(_QWORD *)(a1 + 72) != 0)));
  *a2 = ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecore\\internal\\net\\inc\\wcm\\wcm_work_queue.h",
      v6);
  return a2;
}

```

## disassembly

```asm
0x180030134  mov     [rsp+arg_8], rdx
0x180030139  push    rbx
0x18003013a  sub     rsp, 30h
0x18003013e  mov     rbx, rdx
0x180030141  mov     [rsp+38h+var_18], 0
0x180030149  xor     eax, eax
0x18003014b  mov     [rdx], rax
0x18003014e  mov     rax, [rcx+48h]
0x180030152  neg     rax
0x180030155  sbb     r8, r8
0x180030158  and     r8, rcx; pcbe
0x18003015b  mov     rdx, r9; pv
0x18003015e  lea     rcx, ?WorkCallback@ThreadPoolWorkQueue@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180030165  call    cs:__imp_CreateThreadpoolWork
0x18003016b  mov     [rbx], rax
0x18003016e  mov     [rsp+38h+var_18], 1
0x180030176  test    rax, rax
0x180030179  jnz     short loc_180030190
0x18003017b  mov     rcx, [rsp+38h]; this
0x180030180  lea     r8, aOnecoreInterna_2; "onecore\\internal\\net\\inc\\wcm\\wcm_w"...
0x180030187  lea     edx, [rax+75h]; void *
0x18003018a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180030190  mov     rax, rbx
0x180030193  add     rsp, 30h
0x180030197  pop     rbx
0x180030198  retn
```
