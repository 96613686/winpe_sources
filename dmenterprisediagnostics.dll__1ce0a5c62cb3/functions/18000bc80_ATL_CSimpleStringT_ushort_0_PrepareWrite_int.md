# ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)

- ea: `0x18000bc80`
- end: `0x18000bcb0`
- name: `?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180009860`
- `0x18000a604`
- `0x18000b0c0`
- `0x18000c3d8`
- `0x180010e80`
- `0x180013adc`
- `0x180013bc0`
- `0x180013dac`
- `0x18001457c`
- `0x1800184fc`
- `0x18001a038`

## callees

- `0x18000bc14`
- `0x18000bc80`

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
0x18000bc80  push    rbx
0x18000bc82  sub     rsp, 20h
0x18000bc86  mov     rax, [rcx]
0x18000bc89  mov     r9d, 1
0x18000bc8f  mov     rbx, rcx
0x18000bc92  mov     r8d, [rax-0Ch]
0x18000bc96  sub     r9d, [rax-8]
0x18000bc9a  sub     r8d, edx
0x18000bc9d  or      r9d, r8d
0x18000bca0  jge     short loc_18000BCA7
0x18000bca2  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000bca7  mov     rax, [rbx]
0x18000bcaa  add     rsp, 20h
0x18000bcae  pop     rbx
0x18000bcaf  retn
```
