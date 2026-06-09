# ATL::CComObject<CPnpCleanTaskHandler>::AddRef(void)

- ea: `0x180003910`
- end: `0x180003923`
- name: `?AddRef@?$CComObject@VCPnpCleanTaskHandler@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003910`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPnpCleanTaskHandler>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 56);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 56) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180003910  mov     edx, [rcx+38h]
0x180003913  mov     eax, 7FFFFFFFh
0x180003918  cmp     edx, eax
0x18000391a  jz      short locret_180003922
0x18000391c  lea     eax, [rdx+1]
0x18000391f  mov     [rcx+38h], eax
0x180003922  retn
```
