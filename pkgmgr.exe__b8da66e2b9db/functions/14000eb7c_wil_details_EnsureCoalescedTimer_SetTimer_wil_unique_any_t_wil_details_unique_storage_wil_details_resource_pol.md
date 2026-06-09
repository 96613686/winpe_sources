# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x14000eb7c`
- end: `0x14000ebd3`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `87`
- prototype: `void __fastcall(struct _TP_TIMER **, _BYTE *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000e29c`
- `0x14000e318`

## callees

- `0x140002360`
- `0x14000eb7c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ebb7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ebb7`

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
0x14000eb7c  push    rbx
0x14000eb7e  sub     rsp, 30h
0x14000eb82  mov     rax, cs:__security_cookie
0x14000eb89  xor     rax, rsp
0x14000eb8c  mov     [rsp+38h+var_10], rax
0x14000eb91  mov     rcx, [rcx]; pti
0x14000eb94  mov     rbx, rdx
0x14000eb97  test    rcx, rcx
0x14000eb9a  jz      short loc_14000EBC0
0x14000eb9c  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x14000eba3  shr     r8d, 2
0x14000eba7  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x14000ebac  mov     r9d, r8d; msWindowLength
0x14000ebaf  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x14000ebb4  xor     r8d, r8d; msPeriod
0x14000ebb7  call    cs:__imp_SetThreadpoolTimer
0x14000ebbd  mov     byte ptr [rbx], 1
0x14000ebc0  mov     rcx, [rsp+38h+var_10]
0x14000ebc5  xor     rcx, rsp; StackCookie
0x14000ebc8  call    __security_check_cookie
0x14000ebcd  add     rsp, 30h
0x14000ebd1  pop     rbx
0x14000ebd2  retn
```
