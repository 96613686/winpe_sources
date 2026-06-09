# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x1800177e8`
- end: `0x18001783f`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `87`
- prototype: `void __fastcall(struct _TP_TIMER **, _BYTE *, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001a99c`
- `0x18001aa78`
- `0x18001af04`

## callees

- `0x1800120d0`
- `0x1800177e8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017823`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017823`

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
0x1800177e8  push    rbx
0x1800177ea  sub     rsp, 30h
0x1800177ee  mov     rax, cs:__security_cookie
0x1800177f5  xor     rax, rsp
0x1800177f8  mov     [rsp+38h+var_10], rax
0x1800177fd  mov     rcx, [rcx]; pti
0x180017800  mov     rbx, rdx
0x180017803  test    rcx, rcx
0x180017806  jz      short loc_18001782C
0x180017808  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x18001780f  shr     r8d, 2
0x180017813  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180017818  mov     r9d, r8d; msWindowLength
0x18001781b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180017820  xor     r8d, r8d; msPeriod
0x180017823  call    cs:__imp_SetThreadpoolTimer
0x180017829  mov     byte ptr [rbx], 1
0x18001782c  mov     rcx, [rsp+38h+var_10]
0x180017831  xor     rcx, rsp; StackCookie
0x180017834  call    __security_check_cookie
0x180017839  add     rsp, 30h
0x18001783d  pop     rbx
0x18001783e  retn
```
