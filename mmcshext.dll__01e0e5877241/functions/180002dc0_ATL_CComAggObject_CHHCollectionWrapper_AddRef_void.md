# ATL::CComAggObject<CHHCollectionWrapper>::AddRef(void)

- ea: `0x180002dc0`
- end: `0x180002dd3`
- name: `?AddRef@?$CComAggObject@VCHHCollectionWrapper@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002dc0`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CHHCollectionWrapper>::AddRef(__int64 a1)
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
0x180002dc0  mov     edx, [rcx+8]
0x180002dc3  mov     eax, 7FFFFFFFh
0x180002dc8  cmp     edx, eax
0x180002dca  jz      short locret_180002DD2
0x180002dcc  lea     eax, [rdx+1]
0x180002dcf  mov     [rcx+8], eax
0x180002dd2  retn
```
