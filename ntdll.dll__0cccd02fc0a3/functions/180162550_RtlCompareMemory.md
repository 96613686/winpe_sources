# RtlCompareMemory

- ea: `0x180162550`
- end: `0x1801625ca`
- name: `RtlCompareMemory`
- size: `122`
- prototype: `SIZE_T __stdcall(const void *Source1, const void *Source2, SIZE_T Length)`
- caller_count: `19`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012e60`
- `0x18001aa40`
- `0x180028440`
- `0x180028520`
- `0x180029590`
- `0x18002af40`
- `0x18002b300`
- `0x180034d20`
- `0x180038e20`
- `0x180039210`
- `0x180079d70`
- `0x180085ad0`
- `0x180088ec4`
- `0x1800a9b38`
- `0x1800aa904`
- `0x1800b5d40`
- `0x1800cd5c0`
- `0x1800f8060`
- `0x18013b6b4`

## callees

- `0x180162550`

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
0x180162550  push    rdi
0x180162551  push    rsi
0x180162552  mov     rsi, rcx
0x180162555  mov     rdi, rdx
0x180162558  xor     edx, ecx
0x18016255a  and     edx, 7
0x18016255d  jnz     short loc_1801625B2
0x18016255f  cmp     r8, 8
0x180162563  jb      short loc_1801625B2
0x180162565  mov     r9, rdi
0x180162568  neg     ecx
0x18016256a  and     ecx, 7
0x18016256d  jz      short loc_180162576
0x18016256f  sub     r8, rcx
0x180162572  repe cmpsb
0x180162574  jnz     short loc_1801625A6
0x180162576  mov     rcx, r8
0x180162579  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18016257d  jz      short loc_18016259A
0x18016257f  sub     r8, rcx
0x180162582  shr     rcx, 3
0x180162586  repe cmpsq
0x180162589  jz      short loc_18016259A
0x18016258b  inc     rcx
0x18016258e  sub     rsi, 8
0x180162592  sub     rdi, 8
0x180162596  shl     rcx, 3
0x18016259a  add     r8, rcx
0x18016259d  jz      short loc_1801625A9
0x18016259f  mov     rcx, r8
0x1801625a2  repe cmpsb
0x1801625a4  jz      short loc_1801625A9
0x1801625a6  dec     rdi
0x1801625a9  sub     rdi, r9
0x1801625ac  mov     rax, rdi
0x1801625af  pop     rsi
0x1801625b0  pop     rdi
0x1801625b1  retn
0x1801625b2  test    r8, r8
0x1801625b5  jz      short loc_1801625C4
0x1801625b7  mov     rcx, r8
0x1801625ba  repe cmpsb
0x1801625bc  jz      short loc_1801625C4
0x1801625be  inc     rcx
0x1801625c1  sub     r8, rcx
0x1801625c4  mov     rax, r8
0x1801625c7  pop     rsi
0x1801625c8  pop     rdi
0x1801625c9  retn
```
