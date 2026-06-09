# RtlCompareMemory

- ea: `0x180162d60`
- end: `0x180162dda`
- name: `RtlCompareMemory`
- size: `122`
- prototype: `SIZE_T __stdcall(const void *Source1, const void *Source2, SIZE_T Length)`
- caller_count: `19`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012e60`
- `0x18001aa40`
- `0x180028330`
- `0x180028410`
- `0x180029480`
- `0x180034500`
- `0x1800370d0`
- `0x180037430`
- `0x180046d50`
- `0x1800475e0`
- `0x180059710`
- `0x180091f30`
- `0x180095324`
- `0x1800b2508`
- `0x1800b32d4`
- `0x1800b9b10`
- `0x1800cf150`
- `0x1800f8b40`
- `0x18013c044`

## callees

- `0x180162d60`

## pseudocode

```c
SIZE_T __stdcall RtlCompareMemory(const void *Source1, const void *Source2, SIZE_T Length)
{
  _BYTE *v3; // rsi
  _BYTE *v4; // rdi
  __int64 v5; // rcx
  bool v6; // zf
  SIZE_T v7; // rcx
  bool v8; // zf
  bool v9; // zf
  SIZE_T v10; // r8
  SIZE_T v11; // rcx
  bool v13; // zf
  SIZE_T v14; // rcx

  v3 = Source1;
  v4 = Source2;
  if ( (((unsigned __int8)Source1 ^ (unsigned __int8)Source2) & 7) != 0 || Length < 8 )
  {
    v13 = Length == 0;
    if ( Length )
    {
      v14 = Length;
      do
      {
        if ( !v14 )
          break;
        v13 = *v3++ == *v4++;
        --v14;
      }
      while ( v13 );
      if ( !v13 )
        Length -= v14 + 1;
    }
    return Length;
  }
  else
  {
    v5 = -(int)Source1 & 7;
    if ( (_DWORD)v5 )
    {
      Length -= (unsigned int)v5;
      v6 = Length == 0;
      do
      {
        if ( !v5 )
          break;
        v6 = *v3++ == *v4++;
        --v5;
      }
      while ( v6 );
      if ( !v6 )
        goto LABEL_19;
    }
    v7 = Length & 0xFFFFFFFFFFFFFFF8uLL;
    if ( (Length & 0xFFFFFFFFFFFFFFF8uLL) != 0 )
    {
      Length -= v7;
      v7 >>= 3;
      v8 = v7 == 0;
      do
      {
        if ( !v7 )
          break;
        v8 = *(_QWORD *)v3 == *(_QWORD *)v4;
        v3 += 8;
        v4 += 8;
        --v7;
      }
      while ( v8 );
      if ( !v8 )
      {
        v3 -= 8;
        v4 -= 8;
        v7 = 8 * (v7 + 1);
      }
    }
    v9 = v7 + Length == 0;
    v10 = v7 + Length;
    if ( v10 )
    {
      v11 = v10;
      do
      {
        if ( !v11 )
          break;
        v9 = *v3++ == *v4++;
        --v11;
      }
      while ( v9 );
      if ( !v9 )
LABEL_19:
        --v4;
    }
    return v4 - (_BYTE *)Source2;
  }
}

```

## disassembly

```asm
0x180162d60  push    rdi
0x180162d61  push    rsi
0x180162d62  mov     rsi, rcx
0x180162d65  mov     rdi, rdx
0x180162d68  xor     edx, ecx
0x180162d6a  and     edx, 7
0x180162d6d  jnz     short loc_180162DC2
0x180162d6f  cmp     r8, 8
0x180162d73  jb      short loc_180162DC2
0x180162d75  mov     r9, rdi
0x180162d78  neg     ecx
0x180162d7a  and     ecx, 7
0x180162d7d  jz      short loc_180162D86
0x180162d7f  sub     r8, rcx
0x180162d82  repe cmpsb
0x180162d84  jnz     short loc_180162DB6
0x180162d86  mov     rcx, r8
0x180162d89  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180162d8d  jz      short loc_180162DAA
0x180162d8f  sub     r8, rcx
0x180162d92  shr     rcx, 3
0x180162d96  repe cmpsq
0x180162d99  jz      short loc_180162DAA
0x180162d9b  inc     rcx
0x180162d9e  sub     rsi, 8
0x180162da2  sub     rdi, 8
0x180162da6  shl     rcx, 3
0x180162daa  add     r8, rcx
0x180162dad  jz      short loc_180162DB9
0x180162daf  mov     rcx, r8
0x180162db2  repe cmpsb
0x180162db4  jz      short loc_180162DB9
0x180162db6  dec     rdi
0x180162db9  sub     rdi, r9
0x180162dbc  mov     rax, rdi
0x180162dbf  pop     rsi
0x180162dc0  pop     rdi
0x180162dc1  retn
0x180162dc2  test    r8, r8
0x180162dc5  jz      short loc_180162DD4
0x180162dc7  mov     rcx, r8
0x180162dca  repe cmpsb
0x180162dcc  jz      short loc_180162DD4
0x180162dce  inc     rcx
0x180162dd1  sub     r8, rcx
0x180162dd4  mov     rax, r8
0x180162dd7  pop     rsi
0x180162dd8  pop     rdi
0x180162dd9  retn
```
