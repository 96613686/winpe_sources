# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x18000fc14`
- end: `0x18000fc6b`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010e40`
- `0x18001124c`
- `0x1800409f4`

## callees

- `0x180007c90`
- `0x18000fc14`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fc4f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fc4f`

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
0x18000fc14  push    rbx
0x18000fc16  sub     rsp, 30h
0x18000fc1a  mov     rax, cs:__security_cookie
0x18000fc21  xor     rax, rsp
0x18000fc24  mov     [rsp+38h+var_10], rax
0x18000fc29  mov     rcx, [rcx]; pti
0x18000fc2c  mov     rbx, rdx
0x18000fc2f  test    rcx, rcx
0x18000fc32  jz      short loc_18000FC58
0x18000fc34  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x18000fc3b  shr     r8d, 2
0x18000fc3f  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000fc44  mov     r9d, r8d; msWindowLength
0x18000fc47  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000fc4c  xor     r8d, r8d; msPeriod
0x18000fc4f  call    cs:__imp_SetThreadpoolTimer
0x18000fc55  mov     byte ptr [rbx], 1
0x18000fc58  mov     rcx, [rsp+38h+var_10]
0x18000fc5d  xor     rcx, rsp; StackCookie
0x18000fc60  call    __security_check_cookie
0x18000fc65  add     rsp, 30h
0x18000fc69  pop     rbx
0x18000fc6a  retn
```
