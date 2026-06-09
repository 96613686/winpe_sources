# CILogRecordPointer::CompareLRP(_ULARGE_INTEGER,_ULARGE_INTEGER)

- ea: `0x1800059a0`
- end: `0x1800059d9`
- name: `?CompareLRP@CILogRecordPointer@@UEAAKT_ULARGE_INTEGER@@0@Z`
- size: `57`
- prototype: `__int64 __fastcall(CILogRecordPointer *this, union _ULARGE_INTEGER, union _ULARGE_INTEGER)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800059a0`

## pseudocode

```c
__int64 __fastcall CILogRecordPointer::CompareLRP(
        CILogRecordPointer *this,
        union _ULARGE_INTEGER a2,
        union _ULARGE_INTEGER a3)
{
  if ( a2.HighPart > a3.HighPart )
  {
    return 2;
  }
  else if ( a2.HighPart >= a3.HighPart )
  {
    if ( a3.LowPart == a2.LowPart )
      return 0;
    else
      return (unsigned int)((a3.LowPart < a2.LowPart) + 1);
  }
  else
  {
    return 1;
  }
}

```

## disassembly

```asm
0x1800059a0  mov     rax, rdx
0x1800059a3  mov     rcx, r8
0x1800059a6  shr     rax, 20h
0x1800059aa  shr     rcx, 20h
0x1800059ae  cmp     eax, ecx
0x1800059b0  ja      short loc_1800059D1
0x1800059b2  jnb     short loc_1800059BB
0x1800059b4  mov     ecx, 1
0x1800059b9  jmp     short loc_1800059D6
0x1800059bb  cmp     r8d, edx
0x1800059be  jnz     short loc_1800059C4
0x1800059c0  xor     ecx, ecx
0x1800059c2  jmp     short loc_1800059D6
0x1800059c4  sbb     eax, eax
0x1800059c6  mov     ecx, 1
0x1800059cb  neg     eax
0x1800059cd  add     ecx, eax
0x1800059cf  jmp     short loc_1800059D6
0x1800059d1  mov     ecx, 2
0x1800059d6  mov     eax, ecx
0x1800059d8  retn
```
