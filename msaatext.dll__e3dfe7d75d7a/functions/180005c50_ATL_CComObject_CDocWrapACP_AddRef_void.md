# ATL::CComObject<CDocWrapACP>::AddRef(void)

- ea: `0x180005c50`
- end: `0x180005c63`
- name: `?AddRef@?$CComObject@VCDocWrapACP@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005c70`
- `0x180005c80`
- `0x180005c90`
- `0x180005ca0`
- `0x180005cb0`
- `0x180005cc0`

## callees

- `0x180005c50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDocWrapACP>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 80);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 80) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180005c50  mov     edx, [rcx+50h]
0x180005c53  mov     eax, 7FFFFFFFh
0x180005c58  cmp     edx, eax
0x180005c5a  jz      short locret_180005C62
0x180005c5c  lea     eax, [rdx+1]
0x180005c5f  mov     [rcx+50h], eax
0x180005c62  retn
```
