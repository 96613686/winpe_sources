# ATL::CComObject<CExtractIcon>::AddRef(void)

- ea: `0x180002e30`
- end: `0x180002e43`
- name: `?AddRef@?$CComObject@VCExtractIcon@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002e50`

## callees

- `0x180002e30`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CExtractIcon>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 16);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 16) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180002e30  mov     edx, [rcx+10h]
0x180002e33  mov     eax, 7FFFFFFFh
0x180002e38  cmp     edx, eax
0x180002e3a  jz      short locret_180002E42
0x180002e3c  lea     eax, [rdx+1]
0x180002e3f  mov     [rcx+10h], eax
0x180002e42  retn
```
