# ATL::CComPtr<IXMLDOMElement>::~CComPtr<IXMLDOMElement>(void)

- ea: `0x180010f74`
- end: `0x180010f92`
- name: `??1?$CComPtr@UIXMLDOMElement@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020198`
- `0x1800201aa`
- `0x1800201ce`
- `0x1800201e0`
- `0x1800201f2`
- `0x180020258`
- `0x180020280`
- `0x180020292`
- `0x1800202a4`
- `0x18002082d`
- `0x180020922`

## callees

- `0x180010f74`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IXMLDOMElement>::~CComPtr<IXMLDOMElement>(__int64 *a1)
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
0x180010f74  sub     rsp, 28h
0x180010f78  mov     rcx, [rcx]
0x180010f7b  test    rcx, rcx
0x180010f7e  jz      short loc_180010F8D
0x180010f80  mov     rax, [rcx]
0x180010f83  mov     rax, [rax+10h]
0x180010f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f8c  nop
0x180010f8d  add     rsp, 28h
0x180010f91  retn
```
