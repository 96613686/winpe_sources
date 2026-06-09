# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x18000f60c`
- end: `0x18000f663`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013ac8`
- `0x180013ba4`
- `0x180013fd0`

## callees

- `0x180001710`
- `0x18000f60c`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18000f647`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f647`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(struct _TP_TIMER **a1, _BYTE *a2, __int64 a3)
{
  struct _TP_TIMER *v3; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    pftDueTime = (struct _FILETIME)(-10000 * a3);
    SetThreadpoolTimer(v3, &pftDueTime, 0, (unsigned int)a3 >> 2);
    *a2 = 1;
  }
}

```

## disassembly

```asm
0x18000f60c  push    rbx
0x18000f60e  sub     rsp, 30h
0x18000f612  mov     rax, cs:__security_cookie
0x18000f619  xor     rax, rsp
0x18000f61c  mov     [rsp+38h+var_10], rax
0x18000f621  mov     rcx, [rcx]; pti
0x18000f624  mov     rbx, rdx
0x18000f627  test    rcx, rcx
0x18000f62a  jz      short loc_18000F650
0x18000f62c  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x18000f633  shr     r8d, 2
0x18000f637  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000f63c  mov     r9d, r8d; msWindowLength
0x18000f63f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000f644  xor     r8d, r8d; msPeriod
0x18000f647  call    cs:__imp_SetThreadpoolTimer
0x18000f64d  mov     byte ptr [rbx], 1
0x18000f650  mov     rcx, [rsp+38h+var_10]
0x18000f655  xor     rcx, rsp; StackCookie
0x18000f658  call    __security_check_cookie
0x18000f65d  add     rsp, 30h
0x18000f661  pop     rbx
0x18000f662  retn
```
