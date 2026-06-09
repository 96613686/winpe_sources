# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x18004b2a0`
- end: `0x18004b2e2`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18004641c`
- `0x180051fd0`
- `0x1800593ec`

## callees

- `0x18004b2a0`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18004b2cc`
- `KERNEL32!SetThreadpoolTimer` at `0x18004b2cc`

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
0x18004b2a0  push    rbx
0x18004b2a2  sub     rsp, 20h
0x18004b2a6  mov     rcx, [rcx]; pti
0x18004b2a9  mov     rbx, rdx
0x18004b2ac  test    rcx, rcx
0x18004b2af  jz      short loc_18004B2DB
0x18004b2b1  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x18004b2b8  shr     r8d, 2
0x18004b2bc  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18004b2c1  mov     r9d, r8d; msWindowLength
0x18004b2c4  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18004b2c9  xor     r8d, r8d; msPeriod
0x18004b2cc  call    cs:__imp_SetThreadpoolTimer
0x18004b2d3  nop     dword ptr [rax+rax+00h]
0x18004b2d8  mov     byte ptr [rbx], 1
0x18004b2db  add     rsp, 20h
0x18004b2df  pop     rbx
0x18004b2e0  retn
```
