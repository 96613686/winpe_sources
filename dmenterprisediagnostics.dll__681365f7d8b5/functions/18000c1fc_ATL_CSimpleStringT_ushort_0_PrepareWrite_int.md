# ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)

- ea: `0x18000c1fc`
- end: `0x18000c22d`
- name: `?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z`
- size: `49`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180009d30`
- `0x18000ab7c`
- `0x18000b684`
- `0x18000c9a8`
- `0x180011618`
- `0x1800142d0`
- `0x1800143b0`
- `0x1800145bc`
- `0x180014dec`
- `0x180019294`
- `0x18001aab8`

## callees

- `0x18000c18c`
- `0x18000c1fc`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(__int64 a1, __int64 a2)
{
  __int64 v3; // r8

  v3 = (unsigned int)(*(_DWORD *)(*(_QWORD *)a1 - 12LL) - a2);
  if ( (int)(v3 | (1 - *(_DWORD *)(*(_QWORD *)a1 - 8LL))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(
      a1,
      a2,
      v3,
      (unsigned int)v3 | (1 - *(_DWORD *)(*(_QWORD *)a1 - 8LL)));
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x18000c1fc  push    rbx
0x18000c1fe  sub     rsp, 20h
0x18000c202  mov     rax, [rcx]
0x18000c205  mov     r9d, 1
0x18000c20b  mov     rbx, rcx
0x18000c20e  mov     r8d, [rax-0Ch]
0x18000c212  sub     r9d, [rax-8]
0x18000c216  sub     r8d, edx
0x18000c219  or      r9d, r8d
0x18000c21c  jge     short loc_18000C223
0x18000c21e  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000c223  mov     rax, [rbx]
0x18000c226  add     rsp, 20h
0x18000c22a  pop     rbx
0x18000c22b  retn
```
