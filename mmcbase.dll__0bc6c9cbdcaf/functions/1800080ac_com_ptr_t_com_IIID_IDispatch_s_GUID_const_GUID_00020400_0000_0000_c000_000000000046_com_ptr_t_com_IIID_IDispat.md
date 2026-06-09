# _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>(void)

- ea: `0x1800080ac`
- end: `0x1800080ca`
- name: `??1?$_com_ptr_t@V?$_com_IIID@UIDispatch@@$1?_GUID_00020400_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b6e3`
- `0x18001b790`
- `0x18001b7a2`

## callees

- `0x1800080ac`
- `0x18001d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>(
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
0x1800080ac  sub     rsp, 28h
0x1800080b0  mov     rcx, [rcx]
0x1800080b3  test    rcx, rcx
0x1800080b6  jz      short loc_1800080C5
0x1800080b8  mov     rax, [rcx]
0x1800080bb  mov     rax, [rax+10h]
0x1800080bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080c4  nop
0x1800080c5  add     rsp, 28h
0x1800080c9  retn
```
