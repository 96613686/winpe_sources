# ATL::CComPtrBase<IXMLDOMSchemaCollection2>::~CComPtrBase<IXMLDOMSchemaCollection2>(void)

- ea: `0x18002dc94`
- end: `0x18002dcb1`
- name: `??1?$CComPtrBase@UIXMLDOMSchemaCollection2@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002dd30`
- `0x18002e118`

## callees

- `0x18002dc94`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IXMLDOMSchemaCollection2>::~CComPtrBase<IXMLDOMSchemaCollection2>(__int64 *a1)
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
0x18002dc94  sub     rsp, 28h
0x18002dc98  mov     rcx, [rcx]
0x18002dc9b  test    rcx, rcx
0x18002dc9e  jz      short loc_18002DCAC
0x18002dca0  mov     rax, [rcx]
0x18002dca3  mov     rax, [rax+10h]
0x18002dca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcac  add     rsp, 28h
0x18002dcb0  retn
```
