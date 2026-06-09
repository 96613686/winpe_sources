# ATL::CComObject<CPnpDiskCleanupHandler>::AddRef(void)

- ea: `0x180002d40`
- end: `0x180002d53`
- name: `?AddRef@?$CComObject@VCPnpDiskCleanupHandler@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002d40`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPnpDiskCleanupHandler>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 8);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 8) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180002d40  mov     edx, [rcx+8]
0x180002d43  mov     eax, 7FFFFFFFh
0x180002d48  cmp     edx, eax
0x180002d4a  jz      short locret_180002D52
0x180002d4c  lea     eax, [rdx+1]
0x180002d4f  mov     [rcx+8], eax
0x180002d52  retn
```
