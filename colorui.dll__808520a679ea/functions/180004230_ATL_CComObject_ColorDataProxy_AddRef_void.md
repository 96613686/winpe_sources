# ATL::CComObject<ColorDataProxy>::AddRef(void)

- ea: `0x180004230`
- end: `0x180004243`
- name: `?AddRef@?$CComObject@VColorDataProxy@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004230`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ColorDataProxy>::AddRef(__int64 a1)
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
0x180004230  mov     edx, [rcx+8]
0x180004233  mov     eax, 7FFFFFFFh
0x180004238  cmp     edx, eax
0x18000423a  jz      short locret_180004242
0x18000423c  lea     eax, [rdx+1]
0x18000423f  mov     [rcx+8], eax
0x180004242  retn
```
