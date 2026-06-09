# DafConcatenateWithDelimiter

- ea: `0x18000ff38`
- end: `0x18001011d`
- name: `DafConcatenateWithDelimiter`
- size: `485`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000f748`
- `0x18000f858`
- `0x18000f95c`

## callees

- `0x1800019b0`
- `0x1800019d4`
- `0x18000fe84`
- `0x18000ff38`

## pseudocode

```c
__int64 __fastcall DafConcatenateWithDelimiter(_WORD *a1, const unsigned __int16 *a2, __int64 a3, _QWORD *a4)
{
  _WORD *v6; // rsi
  void *v7; // rdi
  _WORD *v8; // rax
  __int64 v9; // r8
  unsigned int v10; // ebx
  unsigned int v11; // ecx
  __int64 v12; // r9
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rax
  __int64 v15; // r8
  __int64 v16; // rdx
  const unsigned __int16 *v17; // rax
  size_t v18; // rbp
  _WORD *v19; // rax
  unsigned __int64 v20; // rdx
  __int64 v21; // rcx
  _WORD *v22; // rcx

  v6 = a1;
  v7 = 0;
  if ( !a1 )
  {
    v10 = -2147024809;
    goto LABEL_38;
  }
  v8 = a1;
  v9 = 0x7FFFFFFF;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v9;
  }
  while ( v9 );
  v10 = -2147024809;
  v11 = v9 == 0 ? 0x80070057 : 0;
  if ( !v9 )
    goto LABEL_36;
  v12 = (2 * (0x7FFFFFFF - v9)) & -(__int64)(v9 != 0);
  if ( !a2 )
  {
    v11 = -2147024809;
LABEL_13:
    v15 = 0;
    goto LABEL_14;
  }
  v13 = 0x7FFFFFFF;
  v14 = a2;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v11 = v13 == 0 ? 0x80070057 : 0;
  if ( !v13 )
    goto LABEL_13;
  v15 = (2 * (0x7FFFFFFF - v13)) & -(__int64)(v13 != 0);
LABEL_14:
  if ( v11 )
    goto LABEL_36;
  v16 = 0x7FFFFFFF;
  v17 = L"#";
  do
  {
    if ( !*v17 )
      break;
    ++v17;
    --v16;
  }
  while ( v16 );
  v11 = v16 == 0 ? 0x80070057 : 0;
  if ( !v16 )
  {
LABEL_36:
    v10 = v11;
    goto LABEL_38;
  }
  v18 = v15 + 2 + v12 + (-(__int64)(v16 != 0) & (2 * (0x7FFFFFFF - v16)));
  v19 = operator new(v18);
  v7 = v19;
  if ( !v19 )
  {
    v10 = -2147024882;
    goto LABEL_38;
  }
  v20 = v18 >> 1;
  if ( v18 >> 1 )
  {
    if ( v20 > 0x7FFFFFFF )
    {
      *v19 = 0;
LABEL_33:
      operator delete(v7);
      v7 = 0;
      goto LABEL_38;
    }
    v21 = 2147483646;
    do
    {
      if ( !v21 )
        break;
      if ( !*v6 )
        break;
      *v19++ = *v6++;
      --v21;
      --v20;
    }
    while ( v20 );
    v22 = v19 - 1;
    if ( v20 )
      v22 = v19;
    v10 = v20 == 0 ? 0x8007007A : 0;
    *v22 = 0;
  }
  if ( v10 )
    goto LABEL_33;
  v10 = StringCbCatW((unsigned __int16 *)v7, v18, L"#");
  if ( v10 )
    goto LABEL_33;
  v10 = StringCbCatW((unsigned __int16 *)v7, v18, a2);
  if ( v10 )
    goto LABEL_33;
LABEL_38:
  *a4 = v7;
  return v10;
}

```

## disassembly

```asm
0x18000ff38  push    rbx
0x18000ff3a  push    rbp
0x18000ff3b  push    rsi
0x18000ff3c  push    rdi
0x18000ff3d  push    r12
0x18000ff3f  push    r13
0x18000ff41  push    r14
0x18000ff43  push    r15
0x18000ff45  sub     rsp, 28h
0x18000ff49  xor     r12d, r12d
0x18000ff4c  mov     r15, r9
0x18000ff4f  mov     r14, rdx
0x18000ff52  mov     rsi, rcx
0x18000ff55  mov     edi, r12d
0x18000ff58  test    rcx, rcx
0x18000ff5b  jz      loc_180010102
0x18000ff61  mov     r13d, 7FFFFFFFh
0x18000ff67  mov     rax, rcx
0x18000ff6a  mov     r8d, r13d
0x18000ff6d  cmp     [rax], r12w
0x18000ff71  jz      short loc_18000FF7D
0x18000ff73  add     rax, 2
0x18000ff77  sub     r8, 1
0x18000ff7b  jnz     short loc_18000FF6D
0x18000ff7d  mov     rax, r8
0x18000ff80  mov     ebx, 80070057h
0x18000ff85  neg     rax
0x18000ff88  sbb     ecx, ecx
0x18000ff8a  not     ecx
0x18000ff8c  and     ecx, ebx
0x18000ff8e  test    r8, r8
0x18000ff91  jz      loc_1800100FE
0x18000ff97  mov     rax, r13
0x18000ff9a  sub     rax, r8
0x18000ff9d  add     rax, rax
0x18000ffa0  neg     r8
0x18000ffa3  sbb     r9, r9
0x18000ffa6  and     r9, rax
0x18000ffa9  test    r14, r14
0x18000ffac  jz      short loc_18000FFE9
0x18000ffae  mov     rdx, r13
0x18000ffb1  mov     rax, r14
0x18000ffb4  cmp     [rax], r12w
0x18000ffb8  jz      short loc_18000FFC4
0x18000ffba  add     rax, 2
0x18000ffbe  sub     rdx, 1
0x18000ffc2  jnz     short loc_18000FFB4
0x18000ffc4  mov     rax, rdx
0x18000ffc7  neg     rax
0x18000ffca  sbb     ecx, ecx
0x18000ffcc  not     ecx
0x18000ffce  and     ecx, ebx
0x18000ffd0  test    rdx, rdx
0x18000ffd3  jz      short loc_18000FFEB
0x18000ffd5  mov     rax, r13
0x18000ffd8  sub     rax, rdx
0x18000ffdb  add     rax, rax
0x18000ffde  neg     rdx
0x18000ffe1  sbb     r8, r8
0x18000ffe4  and     r8, rax
0x18000ffe7  jmp     short loc_18000FFEE
0x18000ffe9  mov     ecx, ebx
0x18000ffeb  mov     r8, r12
0x18000ffee  test    ecx, ecx
0x18000fff0  jnz     loc_1800100FE
0x18000fff6  mov     rdx, r13
0x18000fff9  lea     rax, asc_180016D48; "#"
0x180010000  cmp     [rax], r12w
0x180010004  jz      short loc_180010010
0x180010006  add     rax, 2
0x18001000a  sub     rdx, 1
0x18001000e  jnz     short loc_180010000
0x180010010  mov     rax, rdx
0x180010013  neg     rax
0x180010016  sbb     ecx, ecx
0x180010018  not     ecx
0x18001001a  and     ecx, ebx
0x18001001c  test    rdx, rdx
0x18001001f  jz      loc_1800100FE
0x180010025  mov     rcx, r13
0x180010028  sub     rcx, rdx
0x18001002b  neg     rdx
0x18001002e  sbb     rax, rax
0x180010031  add     r8, 2
0x180010035  lea     rbp, [rcx+rcx]
0x180010039  and     rbp, rax
0x18001003c  add     rbp, r9
0x18001003f  add     rbp, r8
0x180010042  mov     rcx, rbp; Size
0x180010045  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001004a  mov     rdi, rax
0x18001004d  test    rax, rax
0x180010050  jnz     short loc_18001005C
0x180010052  mov     ebx, 8007000Eh
0x180010057  jmp     loc_180010107
0x18001005c  mov     rdx, rbp
0x18001005f  shr     rdx, 1
0x180010062  jz      loc_1800100F3
0x180010068  cmp     rdx, r13
0x18001006b  ja      loc_1800100F8
0x180010071  mov     ecx, 7FFFFFFEh
0x180010076  test    rcx, rcx
0x180010079  jz      short loc_18001009A
0x18001007b  movzx   r8d, word ptr [rsi]
0x18001007f  test    r8w, r8w
0x180010083  jz      short loc_18001009A
0x180010085  mov     [rax], r8w
0x180010089  add     rsi, 2
0x18001008d  add     rax, 2
0x180010091  dec     rcx
0x180010094  sub     rdx, 1
0x180010098  jnz     short loc_180010076
0x18001009a  test    rdx, rdx
0x18001009d  lea     rcx, [rax-2]
0x1800100a1  cmovnz  rcx, rax
0x1800100a5  neg     rdx
0x1800100a8  sbb     ebx, ebx
0x1800100aa  not     ebx
0x1800100ac  and     ebx, 8007007Ah
0x1800100b2  mov     [rcx], r12w
0x1800100b6  test    ebx, ebx
0x1800100b8  jnz     short loc_1800100E6
0x1800100ba  lea     r8, asc_180016D48; "#"
0x1800100c1  mov     rdx, rbp; unsigned __int64
0x1800100c4  mov     rcx, rdi; unsigned __int16 *
0x1800100c7  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800100cc  mov     ebx, eax
0x1800100ce  test    eax, eax
0x1800100d0  jnz     short loc_1800100E6
0x1800100d2  mov     r8, r14; unsigned __int16 *
0x1800100d5  mov     rdx, rbp; unsigned __int64
0x1800100d8  mov     rcx, rdi; unsigned __int16 *
0x1800100db  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800100e0  mov     ebx, eax
0x1800100e2  test    eax, eax
0x1800100e4  jz      short loc_180010107
0x1800100e6  mov     rcx, rdi; Block
0x1800100e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800100ee  mov     rdi, r12
0x1800100f1  jmp     short loc_180010107
0x1800100f3  test    rdx, rdx
0x1800100f6  jz      short loc_1800100B6
0x1800100f8  mov     [rax], r12w
0x1800100fc  jmp     short loc_1800100E6
0x1800100fe  mov     ebx, ecx
0x180010100  jmp     short loc_180010107
0x180010102  mov     ebx, 80070057h
0x180010107  mov     [r15], rdi
0x18001010a  mov     eax, ebx
0x18001010c  add     rsp, 28h
0x180010110  pop     r15
0x180010112  pop     r14
0x180010114  pop     r13
0x180010116  pop     r12
0x180010118  pop     rdi
0x180010119  pop     rsi
0x18001011a  pop     rbp
0x18001011b  pop     rbx
0x18001011c  retn
```
