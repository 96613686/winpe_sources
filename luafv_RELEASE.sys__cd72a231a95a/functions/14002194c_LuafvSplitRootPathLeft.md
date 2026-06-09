# LuafvSplitRootPathLeft

- ea: `0x14002194c`
- end: `0x1400219a4`
- name: `LuafvSplitRootPathLeft`
- size: `88`
- prototype: `char __fastcall(unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400175f8`
- `0x140021788`

## callees

- `0x14002194c`
- `0x1400219ac`

## pseudocode

```c
char __fastcall LuafvSplitRootPathLeft(unsigned __int16 *a1, __int64 a2)
{
  unsigned int v3; // r8d
  _WORD *v4; // r10
  unsigned int v5; // edx
  unsigned int i; // r9d

  v3 = *a1 >> 1;
  if ( !v3 )
    return 0;
  v4 = (_WORD *)*((_QWORD *)a1 + 1);
  if ( *v4 == 92 )
  {
    v5 = 1;
    for ( i = 0; i < 2; ++i )
    {
      while ( v5 < v3 && v4[v5] != 92 )
        ++v5;
      if ( ++v5 >= v3 )
        return 0;
    }
  }
  return LuafvSplitPathLeft(a1, a2);
}

```

## disassembly

```asm
0x14002194c  sub     rsp, 28h
0x140021950  movzx   r8d, word ptr [rcx]
0x140021954  mov     r11, rdx
0x140021957  shr     r8d, 1
0x14002195a  jz      short loc_14002199C
0x14002195c  mov     r10, [rcx+8]
0x140021960  cmp     word ptr [r10], 5Ch ; '\'
0x140021965  jnz     short loc_140021975
0x140021967  mov     edx, 1
0x14002196c  xor     r9d, r9d
0x14002196f  cmp     r9d, 2
0x140021973  jb      short loc_14002198B
0x140021975  mov     rdx, r11
0x140021978  call    LuafvSplitPathLeft
0x14002197d  jmp     short loc_14002199E
0x14002197f  mov     eax, edx
0x140021981  cmp     word ptr [r10+rax*2], 5Ch ; '\'
0x140021987  jz      short loc_140021990
0x140021989  inc     edx
0x14002198b  cmp     edx, r8d
0x14002198e  jb      short loc_14002197F
0x140021990  inc     edx
0x140021992  cmp     edx, r8d
0x140021995  jnb     short loc_14002199C
0x140021997  inc     r9d
0x14002199a  jmp     short loc_14002196F
0x14002199c  xor     al, al
0x14002199e  add     rsp, 28h
0x1400219a2  retn
```
