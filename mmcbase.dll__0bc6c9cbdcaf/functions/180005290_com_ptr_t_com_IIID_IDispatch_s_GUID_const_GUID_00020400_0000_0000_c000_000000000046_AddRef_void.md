# _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::_AddRef(void)

- ea: `0x180005290`
- end: `0x1800052ae`
- name: `?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIDispatch@@$1?_GUID_00020400_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ`
- size: `30`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004bf0`
- `0x180004e20`
- `0x180008064`
- `0x180013740`

## callees

- `0x180005290`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::_AddRef(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180005290  sub     rsp, 28h
0x180005294  mov     rcx, [rcx]
0x180005297  test    rcx, rcx
0x18000529a  jz      short loc_1800052A9
0x18000529c  mov     rax, [rcx]
0x18000529f  mov     rax, [rax+8]
0x1800052a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052a8  nop
0x1800052a9  add     rsp, 28h
0x1800052ad  retn
```
