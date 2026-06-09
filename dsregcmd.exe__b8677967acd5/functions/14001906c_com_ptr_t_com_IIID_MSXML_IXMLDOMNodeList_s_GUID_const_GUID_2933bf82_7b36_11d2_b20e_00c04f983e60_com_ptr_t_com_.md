# _com_ptr_t<_com_IIID<MSXML::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::~_com_ptr_t<_com_IIID<MSXML::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>(void)

- ea: `0x14001906c`
- end: `0x14001908a`
- name: `??1?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `27`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002e426`
- `0x14002e438`
- `0x14002e44a`
- `0x14002e5a6`
- `0x14002e600`
- `0x14002e624`
- `0x14002e636`
- `0x14002e648`
- `0x14002e65a`
- `0x14002e690`
- `0x14002e6c6`
- `0x14002e6d8`
- `0x14002e744`
- `0x14002e756`
- `0x14002e768`
- `0x14002e77a`
- `0x14002e78c`
- `0x14002e79e`
- `0x14002e7b0`
- `0x14002e7c2`
- `0x14002e7d4`
- `0x14002f31d`
- `0x14002f36d`
- `0x14002f3ae`
- `0x14002f3d2`
- `0x14002f3e4`
- `0x14002f41a`

## callees

- `0x14001906c`
- `0x140030010`

## pseudocode

```c
__int64 __fastcall _com_ptr_t<_com_IIID<MSXML::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::~_com_ptr_t<_com_IIID<MSXML::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>(
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
0x14001906c  sub     rsp, 28h
0x140019070  mov     rcx, [rcx]
0x140019073  test    rcx, rcx
0x140019076  jz      short loc_140019085
0x140019078  mov     rax, [rcx]
0x14001907b  mov     rax, [rax+10h]
0x14001907f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019084  nop
0x140019085  add     rsp, 28h
0x140019089  retn
```
