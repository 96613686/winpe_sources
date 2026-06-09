# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x18000b808`
- end: `0x18000b84a`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a800`
- `0x18000a884`
- `0x180028e60`

## callees

- `0x18000b808`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b834`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b834`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(struct _TP_TIMER **a1, _BYTE *a2, __int64 a3)
{
  struct _TP_TIMER *v3; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

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
0x18000b808  push    rbx
0x18000b80a  sub     rsp, 20h
0x18000b80e  mov     rcx, [rcx]; pti
0x18000b811  mov     rbx, rdx
0x18000b814  test    rcx, rcx
0x18000b817  jz      short loc_18000B843
0x18000b819  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x18000b820  shr     r8d, 2
0x18000b824  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000b829  mov     r9d, r8d; msWindowLength
0x18000b82c  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000b831  xor     r8d, r8d; msPeriod
0x18000b834  call    cs:__imp_SetThreadpoolTimer
0x18000b83b  nop     dword ptr [rax+rax+00h]
0x18000b840  mov     byte ptr [rbx], 1
0x18000b843  add     rsp, 20h
0x18000b847  pop     rbx
0x18000b848  retn
```
