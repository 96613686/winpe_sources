# _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::~_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>(void)

- ea: `0x1800068a4`
- end: `0x1800068c2`
- name: `??1?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e6e6`
- `0x18000e71c`
- `0x18000e72e`
- `0x18000e740`
- `0x18000e776`
- `0x18000e9f5`
- `0x18000ec3e`
- `0x18000ec50`
- `0x18000ec62`
- `0x18000ec74`
- `0x18000ec86`
- `0x18000ecfb`
- `0x18000ed0d`
- `0x18000ed1f`

## callees

- `0x1800068a4`
- `0x180010010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>::~_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNodeList,&__s_GUID const _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60>>(
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
0x1800068a4  sub     rsp, 28h
0x1800068a8  mov     rcx, [rcx]
0x1800068ab  test    rcx, rcx
0x1800068ae  jz      short loc_1800068BD
0x1800068b0  mov     rax, [rcx]
0x1800068b3  mov     rax, [rax+10h]
0x1800068b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068bc  nop
0x1800068bd  add     rsp, 28h
0x1800068c1  retn
```
