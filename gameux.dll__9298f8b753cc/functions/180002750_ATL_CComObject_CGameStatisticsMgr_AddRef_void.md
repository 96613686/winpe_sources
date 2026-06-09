# ATL::CComObject<CGameStatisticsMgr>::AddRef(void)

- ea: `0x180002750`
- end: `0x180002763`
- name: `?AddRef@?$CComObject@VCGameStatisticsMgr@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002750`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CGameStatisticsMgr>::AddRef(__int64 a1)
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
0x180002750  mov     edx, [rcx+8]
0x180002753  mov     eax, 7FFFFFFFh
0x180002758  cmp     edx, eax
0x18000275a  jz      short locret_180002762
0x18000275c  lea     eax, [rdx+1]
0x18000275f  mov     [rcx+8], eax
0x180002762  retn
```
