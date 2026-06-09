# ATL::CComPtr<IXMLDOMParseError2>::~CComPtr<IXMLDOMParseError2>(void)

- ea: `0x18000e524`
- end: `0x18000e542`
- name: `??1?$CComPtr@UIXMLDOMParseError2@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025f80`
- `0x180025fa0`
- `0x180025fc0`
- `0x180026000`
- `0x180026020`
- `0x180026140`
- `0x180026264`
- `0x18002629a`

## callees

- `0x18000e524`
- `0x180027010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<IXMLDOMParseError2>::~CComPtr<IXMLDOMParseError2>(__int64 *a1)
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
0x18000e524  sub     rsp, 28h
0x18000e528  mov     rcx, [rcx]
0x18000e52b  test    rcx, rcx
0x18000e52e  jz      short loc_18000E53D
0x18000e530  mov     rax, [rcx]
0x18000e533  mov     rax, [rax+10h]
0x18000e537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e53c  nop
0x18000e53d  add     rsp, 28h
0x18000e541  retn
```
