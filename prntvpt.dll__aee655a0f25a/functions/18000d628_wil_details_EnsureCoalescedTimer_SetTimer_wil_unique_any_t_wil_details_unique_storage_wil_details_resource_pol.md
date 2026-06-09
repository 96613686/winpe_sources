# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x18000d628`
- end: `0x18000d663`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `59`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000d458`
- `0x18000d540`
- `0x180014a98`

## callees

- `0x18000d628`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18000d654`
- `KERNEL32!SetThreadpoolTimer` at `0x18000d654`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(struct _TP_TIMER **a1, _BYTE *a2, __int64 a3)
{
  struct _TP_TIMER *v3; // rcx
  _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

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
0x18000d628  push    rbx
0x18000d62a  sub     rsp, 20h
0x18000d62e  mov     rcx, [rcx]; pti
0x18000d631  mov     rbx, rdx
0x18000d634  test    rcx, rcx
0x18000d637  jz      short loc_18000D65D
0x18000d639  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x18000d640  shr     r8d, 2
0x18000d644  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000d649  mov     r9d, r8d; msWindowLength
0x18000d64c  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000d651  xor     r8d, r8d; msPeriod
0x18000d654  call    cs:__imp_SetThreadpoolTimer
0x18000d65a  mov     byte ptr [rbx], 1
0x18000d65d  add     rsp, 20h
0x18000d661  pop     rbx
0x18000d662  retn
```
