# ATL::CComObject<CFaxCommon>::AddRef(void)

- ea: `0x1800020d0`
- end: `0x1800020e3`
- name: `?AddRef@?$CComObject@VCFaxCommon@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800020d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFaxCommon>::AddRef(__int64 a1)
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
0x1800020d0  mov     edx, [rcx+8]
0x1800020d3  mov     eax, 7FFFFFFFh
0x1800020d8  cmp     edx, eax
0x1800020da  jz      short locret_1800020E2
0x1800020dc  lea     eax, [rdx+1]
0x1800020df  mov     [rcx+8], eax
0x1800020e2  retn
```
