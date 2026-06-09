# ATL::CComObject<CWrapMgr<DocTraitsACP>>::AddRef(void)

- ea: `0x180005c30`
- end: `0x180005c43`
- name: `?AddRef@?$CComObject@V?$CWrapMgr@VDocTraitsACP@@@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005c30`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWrapMgr<DocTraitsACP>>::AddRef(__int64 a1)
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
0x180005c30  mov     edx, [rcx+8]
0x180005c33  mov     eax, 7FFFFFFFh
0x180005c38  cmp     edx, eax
0x180005c3a  jz      short locret_180005C42
0x180005c3c  lea     eax, [rdx+1]
0x180005c3f  mov     [rcx+8], eax
0x180005c42  retn
```
