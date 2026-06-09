# ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)

- ea: `0x18000e500`
- end: `0x18000e51e`
- name: `??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007060`
- `0x18001cbe4`
- `0x18001cf30`
- `0x18001d130`
- `0x18001d330`
- `0x18001d950`

## callees

- `0x18000e500`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(__int64 *a1)
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
0x18000e500  sub     rsp, 28h
0x18000e504  mov     rcx, [rcx]
0x18000e507  test    rcx, rcx
0x18000e50a  jz      short loc_18000E519
0x18000e50c  mov     rax, [rcx]
0x18000e50f  mov     rax, [rax+10h]
0x18000e513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e518  nop
0x18000e519  add     rsp, 28h
0x18000e51d  retn
```
