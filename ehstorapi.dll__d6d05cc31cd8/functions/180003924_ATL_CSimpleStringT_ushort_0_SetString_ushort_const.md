# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)

- ea: `0x180003924`
- end: `0x180003945`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d68`
- `0x1800046b4`
- `0x180004a60`
- `0x180005960`
- `0x18000664c`
- `0x180006af0`
- `0x180007840`

## callees

- `0x18000394c`
- `0x180003a20`

## pseudocode

```c
void __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 a1, const unsigned __int16 *a2)
{
  unsigned int v2; // eax
  _BYTE *v3; // rcx
  char **v4; // r10

  v2 = ocslen(a2);
  ATL::CSimpleStringT<unsigned short,0>::SetString(v4, v3, v2);
}

```

## disassembly

```asm
0x180003924  sub     rsp, 28h
0x180003928  mov     r10, rcx
0x18000392b  mov     rcx, rdx; unsigned __int16 *
0x18000392e  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180003933  mov     rdx, rcx
0x180003936  mov     r8d, eax
0x180003939  mov     rcx, r10
0x18000393c  add     rsp, 28h
0x180003940  jmp     ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
```
