# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x18000e5d4`
- end: `0x18000e62b`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d0fc`
- `0x18000d178`
- `0x1800157d8`

## callees

- `0x18000be40`
- `0x18000e5d4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e60f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e60f`

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
0x18000e5d4  push    rbx
0x18000e5d6  sub     rsp, 30h
0x18000e5da  mov     rax, cs:__security_cookie
0x18000e5e1  xor     rax, rsp
0x18000e5e4  mov     [rsp+38h+var_10], rax
0x18000e5e9  mov     rcx, [rcx]; pti
0x18000e5ec  mov     rbx, rdx
0x18000e5ef  test    rcx, rcx
0x18000e5f2  jz      short loc_18000E618
0x18000e5f4  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x18000e5fb  shr     r8d, 2
0x18000e5ff  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000e604  mov     r9d, r8d; msWindowLength
0x18000e607  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000e60c  xor     r8d, r8d; msPeriod
0x18000e60f  call    cs:__imp_SetThreadpoolTimer
0x18000e615  mov     byte ptr [rbx], 1
0x18000e618  mov     rcx, [rsp+38h+var_10]
0x18000e61d  xor     rcx, rsp; StackCookie
0x18000e620  call    __security_check_cookie
0x18000e625  add     rsp, 30h
0x18000e629  pop     rbx
0x18000e62a  retn
```
