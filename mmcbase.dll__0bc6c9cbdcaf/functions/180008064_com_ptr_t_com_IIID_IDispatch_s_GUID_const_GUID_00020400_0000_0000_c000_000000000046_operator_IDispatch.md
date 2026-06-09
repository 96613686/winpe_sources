# _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::operator=(IDispatch *)

- ea: `0x180008064`
- end: `0x1800080a3`
- name: `??4?$_com_ptr_t@V?$_com_IIID@UIDispatch@@$1?_GUID_00020400_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAAAEAV0@PEAUIDispatch@@@Z`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000940c`
- `0x180013d80`

## callees

- `0x180005290`
- `0x180008064`
- `0x18001d010`

## pseudocode

```c
__int64 *__fastcall _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::operator=(
        __int64 *a1,
        __int64 a2)
{
  __int64 v3; // rdi

  v3 = *a1;
  if ( *a1 != a2 )
  {
    *a1 = a2;
    _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::_AddRef(a1);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return a1;
}

```

## disassembly

```asm
0x180008064  mov     [rsp+arg_0], rbx
0x180008069  push    rdi
0x18000806a  sub     rsp, 20h
0x18000806e  mov     rbx, rcx
0x180008071  mov     rdi, [rcx]
0x180008074  cmp     rdi, rdx
0x180008077  jz      short loc_180008095
0x180008079  mov     [rcx], rdx
0x18000807c  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIDispatch@@$1?_GUID_00020400_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::_AddRef(void)
0x180008081  test    rdi, rdi
0x180008084  jz      short loc_180008095
0x180008086  mov     rax, [rdi]
0x180008089  mov     rcx, rdi
0x18000808c  mov     rax, [rax+10h]
0x180008090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008095  mov     rax, rbx
0x180008098  mov     rbx, [rsp+28h+arg_0]
0x18000809d  add     rsp, 20h
0x1800080a1  pop     rdi
0x1800080a2  retn
```
