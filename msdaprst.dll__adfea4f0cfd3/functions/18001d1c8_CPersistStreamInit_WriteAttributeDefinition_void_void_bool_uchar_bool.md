# CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)

- ea: `0x18001d1c8`
- end: `0x18001d2de`
- name: `?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z`
- size: `278`
- prototype: `__int64 __usercall@<rax>(CPersistStreamInit *__hidden this@<rcx>, void *@<rdx>, unsigned __int16 *@<r8>, bool@<r9b>, char, bool)`
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x18001d42c`
- `0x18001d6b0`
- `0x18001d828`
- `0x18001dd70`
- `0x18001ee64`
- `0x18001f1bc`
- `0x18001f7c8`
- `0x18001fbc8`

## callees

- `0x18001cd30`
- `0x18001d054`
- `0x18001d1c8`
- `0x18001ed5c`
- `0x18001fe94`
- `0x180020248`

## pseudocode

```c
int __fastcall CPersistStreamInit::WriteAttributeDefinition(
        CPersistStreamInit *this,
        void *a2,
        unsigned __int16 *a3,
        char a4,
        char a5,
        bool a6)
{
  __int64 v7; // rdx
  int result; // eax
  unsigned int v11; // eax
  _BYTE *v12; // rdx
  CPersistStreamInit *v13; // rcx
  __int64 v14; // r8
  unsigned int v15; // eax
  _BYTE *v16; // rdx
  CPersistStreamInit *v17; // rcx
  unsigned int v18; // [rsp+78h] [rbp+20h] BYREF

  LOBYTE(v18) = a4;
  v7 = *((_QWORD *)this + 9);
  v18 = 0;
  result = CPersistStreamInit::Write(this, *(_BYTE **)(v7 + 704), *(unsigned __int8 *)(v7 + 712), &v18, 1);
  if ( result >= 0 )
  {
    if ( !a5 || (result = CPersistStreamInit::WriteNamespace(this, a5), result >= 0) )
    {
      v11 = CPersistStreamInit::_len(this, a2);
      result = CPersistStreamInit::Write(v13, v12, v11, &v18, 0);
      if ( result >= 0 )
      {
        result = CPersistStreamInit::WriteTag(this, 0x2Bu, &v18);
        if ( result >= 0 )
        {
          result = CPersistStreamInit::WriteTag(this, 0x29u, &v18);
          if ( result >= 0 )
          {
            if ( a6 && *((_BYTE *)this + 64) )
            {
              v14 = -1;
              do
                ++v14;
              while ( a3[v14] );
              result = CPersistStreamInit::TextOutW(this, a3, v14, 0x82u);
            }
            else
            {
              v15 = CPersistStreamInit::_len(this, a3);
              result = CPersistStreamInit::Write(v17, v16, v15, &v18, 0);
            }
            if ( result >= 0 )
              return CPersistStreamInit::WriteTag(this, 0x29u, &v18);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d1c8  mov     rax, rsp
0x18001d1cb  mov     [rax+20h], r9b
0x18001d1cf  push    rbx
0x18001d1d0  push    rbp
0x18001d1d1  push    rsi
0x18001d1d2  push    rdi
0x18001d1d3  sub     rsp, 38h
0x18001d1d7  mov     rsi, rdx
0x18001d1da  mov     byte ptr [rax-38h], 1
0x18001d1de  mov     rdx, [rcx+48h]
0x18001d1e2  lea     r9, [rax+20h]; unsigned int *
0x18001d1e6  mov     rdi, r8
0x18001d1e9  xor     ebp, ebp
0x18001d1eb  mov     [rax+20h], ebp
0x18001d1ee  mov     rbx, rcx
0x18001d1f1  movzx   r8d, byte ptr [rdx+2C8h]; Size
0x18001d1f9  mov     rdx, [rdx+2C0h]; Src
0x18001d200  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001d205  test    eax, eax
0x18001d207  js      loc_18001D2D4
0x18001d20d  mov     dl, [rsp+58h+arg_20]; unsigned __int8
0x18001d214  test    dl, dl
0x18001d216  jz      short loc_18001D228
0x18001d218  mov     rcx, rbx; this
0x18001d21b  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001d220  test    eax, eax
0x18001d222  js      loc_18001D2D4
0x18001d228  mov     rdx, rsi; void *
0x18001d22b  mov     rcx, rbx; this
0x18001d22e  call    ?_len@CPersistStreamInit@@AEBAHPEAX@Z; CPersistStreamInit::_len(void *)
0x18001d233  mov     r8d, eax; Size
0x18001d236  mov     [rsp+58h+var_38], bpl; bool
0x18001d23b  lea     r9, [rsp+58h+arg_18]; unsigned int *
0x18001d240  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001d245  test    eax, eax
0x18001d247  js      loc_18001D2D4
0x18001d24d  lea     r8, [rsp+58h+arg_18]; unsigned int *
0x18001d252  mov     dl, 2Bh ; '+'; unsigned __int8
0x18001d254  mov     rcx, rbx; this
0x18001d257  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d25c  test    eax, eax
0x18001d25e  js      short loc_18001D2D4
0x18001d260  lea     r8, [rsp+58h+arg_18]; unsigned int *
0x18001d265  mov     dl, 29h ; ')'; unsigned __int8
0x18001d267  mov     rcx, rbx; this
0x18001d26a  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d26f  test    eax, eax
0x18001d271  js      short loc_18001D2D4
0x18001d273  cmp     [rsp+58h+arg_28], bpl
0x18001d27b  jz      short loc_18001D2A4
0x18001d27d  cmp     [rbx+40h], bpl
0x18001d281  jz      short loc_18001D2A4
0x18001d283  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d287  inc     r8; unsigned int
0x18001d28a  cmp     [rdi+r8*2], bp
0x18001d28f  jnz     short loc_18001D287
0x18001d291  mov     r9d, 82h; unsigned __int16
0x18001d297  mov     rdx, rdi; unsigned __int16 *
0x18001d29a  mov     rcx, rbx; this
0x18001d29d  call    ?TextOutW@CPersistStreamInit@@AEAAJPEAGKG@Z; CPersistStreamInit::TextOutW(ushort *,ulong,ushort)
0x18001d2a2  jmp     short loc_18001D2C1
0x18001d2a4  mov     rdx, rdi; void *
0x18001d2a7  mov     rcx, rbx; this
0x18001d2aa  call    ?_len@CPersistStreamInit@@AEBAHPEAX@Z; CPersistStreamInit::_len(void *)
0x18001d2af  mov     r8d, eax; Size
0x18001d2b2  mov     [rsp+58h+var_38], bpl; bool
0x18001d2b7  lea     r9, [rsp+58h+arg_18]; unsigned int *
0x18001d2bc  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001d2c1  test    eax, eax
0x18001d2c3  js      short loc_18001D2D4
0x18001d2c5  lea     r8, [rsp+58h+arg_18]; unsigned int *
0x18001d2ca  mov     dl, 29h ; ')'; unsigned __int8
0x18001d2cc  mov     rcx, rbx; this
0x18001d2cf  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d2d4  add     rsp, 38h
0x18001d2d8  pop     rdi
0x18001d2d9  pop     rsi
0x18001d2da  pop     rbp
0x18001d2db  pop     rbx
0x18001d2dc  retn
```
