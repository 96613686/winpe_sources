# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x18000330c`
- end: `0x180003363`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `87`
- prototype: `void __fastcall(struct _TP_TIMER **, _BYTE *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003140`
- `0x18000321c`

## callees

- `0x18000330c`
- `0x180004310`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003347`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003347`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(struct _TP_TIMER **a1, _BYTE *a2, __int64 a3)
{
  struct _TP_TIMER *v3; // rcx
  _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    pftDueTime = (_FILETIME)(-10000 * a3);
    SetThreadpoolTimer(v3, &pftDueTime, 0, (unsigned int)a3 >> 2);
    *a2 = 1;
  }
}

```

## disassembly

```asm
0x18000330c  push    rbx
0x18000330e  sub     rsp, 30h
0x180003312  mov     rax, cs:__security_cookie
0x180003319  xor     rax, rsp
0x18000331c  mov     [rsp+38h+var_10], rax
0x180003321  mov     rcx, [rcx]; pti
0x180003324  mov     rbx, rdx
0x180003327  test    rcx, rcx
0x18000332a  jz      short loc_180003350
0x18000332c  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x180003333  shr     r8d, 2
0x180003337  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000333c  mov     r9d, r8d; msWindowLength
0x18000333f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180003344  xor     r8d, r8d; msPeriod
0x180003347  call    cs:__imp_SetThreadpoolTimer
0x18000334d  mov     byte ptr [rbx], 1
0x180003350  mov     rcx, [rsp+38h+var_10]
0x180003355  xor     rcx, rsp; StackCookie
0x180003358  call    __security_check_cookie
0x18000335d  add     rsp, 30h
0x180003361  pop     rbx
0x180003362  retn
```
