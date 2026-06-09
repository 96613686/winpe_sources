# ATL::CComObject<CSinkWrapAnchor>::AddRef(void)

- ea: `0x180005cd0`
- end: `0x180005ce3`
- name: `?AddRef@?$CComObject@VCSinkWrapAnchor@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005cf0`
- `0x180005d00`

## callees

- `0x180005cd0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSinkWrapAnchor>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 24);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 24) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180005cd0  mov     edx, [rcx+18h]
0x180005cd3  mov     eax, 7FFFFFFFh
0x180005cd8  cmp     edx, eax
0x180005cda  jz      short locret_180005CE2
0x180005cdc  lea     eax, [rdx+1]
0x180005cdf  mov     [rcx+18h], eax
0x180005ce2  retn
```
