# LuafvSplitRootPathLeft

- ea: `0x14002199c`
- end: `0x1400219f4`
- name: `LuafvSplitRootPathLeft`
- size: `88`
- prototype: `char __fastcall(unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140017648`
- `0x1400217d8`

## callees

- `0x14002199c`
- `0x1400219fc`

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
0x14002199c  sub     rsp, 28h
0x1400219a0  movzx   r8d, word ptr [rcx]
0x1400219a4  mov     r11, rdx
0x1400219a7  shr     r8d, 1
0x1400219aa  jz      short loc_1400219EC
0x1400219ac  mov     r10, [rcx+8]
0x1400219b0  cmp     word ptr [r10], 5Ch ; '\'
0x1400219b5  jnz     short loc_1400219C5
0x1400219b7  mov     edx, 1
0x1400219bc  xor     r9d, r9d
0x1400219bf  cmp     r9d, 2
0x1400219c3  jb      short loc_1400219DB
0x1400219c5  mov     rdx, r11
0x1400219c8  call    LuafvSplitPathLeft
0x1400219cd  jmp     short loc_1400219EE
0x1400219cf  mov     eax, edx
0x1400219d1  cmp     word ptr [r10+rax*2], 5Ch ; '\'
0x1400219d7  jz      short loc_1400219E0
0x1400219d9  inc     edx
0x1400219db  cmp     edx, r8d
0x1400219de  jb      short loc_1400219CF
0x1400219e0  inc     edx
0x1400219e2  cmp     edx, r8d
0x1400219e5  jnb     short loc_1400219EC
0x1400219e7  inc     r9d
0x1400219ea  jmp     short loc_1400219BF
0x1400219ec  xor     al, al
0x1400219ee  add     rsp, 28h
0x1400219f2  retn
```
