# _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(void)

- ea: `0x180006ee0`
- end: `0x180006efe`
- name: `??1?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ad6a`
- `0x18000ae2f`

## callees

- `0x180006ee0`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180006ee0  sub     rsp, 28h
0x180006ee4  mov     rcx, [rcx]
0x180006ee7  test    rcx, rcx
0x180006eea  jz      short loc_180006EF9
0x180006eec  mov     rax, [rcx]
0x180006eef  mov     rax, [rax+10h]
0x180006ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ef8  nop
0x180006ef9  add     rsp, 28h
0x180006efd  retn
```
