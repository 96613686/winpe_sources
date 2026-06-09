# Common::DirectoryTreeWalker::InitializePath(ushort const *)

- ea: `0x180007374`
- end: `0x1800075bc`
- name: `?InitializePath@DirectoryTreeWalker@Common@@AEAAJPEBG@Z`
- size: `584`
- prototype: `int(Common::DirectoryTreeWalker *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800069f0`

## callees

- `0x180007374`
- `0x1800076c0`
- `0x180007804`
- `0x180007880`
- `0x180010e8c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800074a5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800074a5`

## pseudocode

```c
__int64 __fastcall Common::DirectoryTreeWalker::InitializePath(
        Common::DirectoryTreeWalker *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // r15
  __int64 v5; // rdx
  const unsigned __int16 *v6; // rax
  unsigned __int64 v7; // rbx
  unsigned __int8 v8; // bp
  char v9; // r14
  unsigned __int16 *v10; // rax
  __int64 v11; // r8
  unsigned __int16 *v12; // rsi
  __int64 v13; // rcx
  const wchar_t *v14; // rdx
  unsigned __int16 *v15; // rcx
  const unsigned __int16 *v16; // r8
  unsigned __int16 *v17; // rcx
  __int64 result; // rax

  v4 = 0x8000;
  if ( !a2 )
    goto LABEL_35;
  v5 = 0x8000;
  v6 = a2;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  v7 = (0x8000 - v5) & -(__int64)(v5 != 0);
  if ( v5 )
  {
    if ( v7 >= 4 && *a2 == 92 && a2[1] == 92 && a2[2] == 63 && a2[3] == 92 )
    {
      v8 = 1;
      goto LABEL_8;
    }
  }
  else
  {
LABEL_35:
    v7 = 0;
  }
  v8 = 0;
LABEL_8:
  if ( v7 < 4 * (unsigned __int64)v8 + 1 || a2[4 * v8 + 1] != 58 )
  {
    if ( v8 )
    {
      if ( v7 < 8 || a2[4] != 85 || a2[5] != 78 || a2[6] != 67 || a2[7] != 92 )
        return 87;
    }
    else if ( v7 < 2 || *a2 != 92 || a2[1] != 92 )
    {
      return 87;
    }
    v9 = 1;
    goto LABEL_11;
  }
  v9 = 0;
LABEL_11:
  if ( !v8 )
  {
    if ( v9 )
      v7 += 6LL;
    else
      v7 += 4LL;
  }
  if ( v7 > 0x7FFF )
    return 206;
  v10 = (unsigned __int16 *)operator new(0x10000u);
  v12 = v10;
  if ( !v10 )
    return 14;
  if ( v8 )
  {
    RtlStringCopyWorkerW(v10, 0x8000, v11, a2);
  }
  else
  {
    if ( v9 )
    {
      RtlStringCchCopyW(v10, 0x8000u, L"\\\\?\\UNC\\");
      v16 = a2 + 2;
    }
    else
    {
      v13 = 2147483646;
      v14 = L"\\\\?\\";
      do
      {
        if ( !v13 )
          break;
        if ( !*v14 )
          break;
        *v10++ = *v14++;
        --v13;
        --v4;
      }
      while ( v4 );
      v15 = v10 - 1;
      v16 = a2;
      if ( v4 )
        v15 = v10;
      *v15 = 0;
    }
    RtlStringCchCatW(v12, (unsigned __int64)v14, v16);
  }
  if ( v12[v7 - 1] == 92 )
    v12[--v7] = 0;
  v17 = (unsigned __int16 *)*((_QWORD *)this + 1);
  if ( v17 != v12 )
  {
    operator delete(v17);
    *((_QWORD *)this + 1) = v12;
  }
  *((_QWORD *)this + 2) = v7;
  result = 0;
  *((_QWORD *)this + 3) = v7;
  return result;
}

```

## disassembly

```asm
0x180007374  push    rbx
0x180007376  push    rbp
0x180007377  push    rsi
0x180007378  push    rdi
0x180007379  push    r12
0x18000737b  push    r13
0x18000737d  push    r14
0x18000737f  push    r15
0x180007381  sub     rsp, 38h
0x180007385  xor     r12d, r12d
0x180007388  mov     rdi, rdx
0x18000738b  mov     r13, rcx
0x18000738e  mov     r8w, 5Ch ; '\'
0x180007393  mov     r15d, 8000h
0x180007399  test    rdx, rdx
0x18000739c  jz      loc_180007517
0x1800073a2  mov     edx, r15d
0x1800073a5  mov     rax, rdi
0x1800073a8  cmp     [rax], r12w
0x1800073ac  jz      short loc_1800073B8
0x1800073ae  add     rax, 2
0x1800073b2  sub     rdx, 1
0x1800073b6  jnz     short loc_1800073A8
0x1800073b8  mov     rcx, r15
0x1800073bb  mov     rax, rdx
0x1800073be  sub     rcx, rdx
0x1800073c1  neg     rax
0x1800073c4  sbb     rbx, rbx
0x1800073c7  and     rbx, rcx
0x1800073ca  test    rdx, rdx
0x1800073cd  jz      loc_180007517
0x1800073d3  cmp     rbx, 4
0x1800073d7  jnb     loc_1800074D1
0x1800073dd  mov     bpl, r12b
0x1800073e0  movzx   eax, bpl
0x1800073e4  lea     rcx, ds:0[rax*4]
0x1800073ec  lea     rax, [rcx+1]
0x1800073f0  cmp     rbx, rax
0x1800073f3  jb      loc_18000751F
0x1800073f9  cmp     word ptr [rdi+rcx*2+2], 3Ah ; ':'
0x1800073ff  jnz     loc_18000751F
0x180007405  mov     r14b, r12b
0x180007408  test    bpl, bpl
0x18000740b  jz      loc_180007568
0x180007411  cmp     rbx, 7FFFh
0x180007418  ja      loc_18000757F
0x18000741e  mov     ecx, 10000h; Size
0x180007423  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007428  mov     rsi, rax
0x18000742b  test    rax, rax
0x18000742e  jz      loc_180007589
0x180007434  test    bpl, bpl
0x180007437  jnz     loc_180007504
0x18000743d  test    r14b, r14b
0x180007440  jnz     loc_180007593
0x180007446  mov     ecx, 7FFFFFFEh
0x18000744b  lea     rdx, asc_180026E30; "\\\\?\\"
0x180007452  test    rcx, rcx
0x180007455  jz      short loc_180007476
0x180007457  movzx   r8d, word ptr [rdx]
0x18000745b  test    r8w, r8w
0x18000745f  jz      short loc_180007476
0x180007461  mov     [rax], r8w
0x180007465  add     rdx, 2; unsigned __int64
0x180007469  add     rax, 2
0x18000746d  dec     rcx
0x180007470  sub     r15, 1
0x180007474  jnz     short loc_180007452
0x180007476  test    r15, r15
0x180007479  lea     rcx, [rax-2]
0x18000747d  mov     r8, rdi; unsigned __int16 *
0x180007480  cmovnz  rcx, rax
0x180007484  mov     [rcx], r12w
0x180007488  mov     rcx, rsi; unsigned __int16 *
0x18000748b  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007490  cmp     word ptr [rsi+rbx*2-2], 5Ch ; '\'
0x180007496  jz      loc_1800075AE
0x18000749c  mov     rcx, [r13+8]
0x1800074a0  cmp     rcx, rsi
0x1800074a3  jz      short loc_1800074B5
0x1800074a5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800074ac  nop     dword ptr [rax+rax+00h]
0x1800074b1  mov     [r13+8], rsi
0x1800074b5  mov     [r13+10h], rbx
0x1800074b9  xor     eax, eax
0x1800074bb  mov     [r13+18h], rbx
0x1800074bf  add     rsp, 38h
0x1800074c3  pop     r15
0x1800074c5  pop     r14
0x1800074c7  pop     r13
0x1800074c9  pop     r12
0x1800074cb  pop     rdi
0x1800074cc  pop     rsi
0x1800074cd  pop     rbp
0x1800074ce  pop     rbx
0x1800074cf  retn
0x1800074d1  cmp     [rdi], r8w
0x1800074d5  jnz     loc_1800073DD
0x1800074db  cmp     [rdi+2], r8w
0x1800074e0  jnz     loc_1800073DD
0x1800074e6  cmp     word ptr [rdi+4], 3Fh ; '?'
0x1800074eb  jnz     loc_1800073DD
0x1800074f1  cmp     [rdi+6], r8w
0x1800074f6  jnz     loc_1800073DD
0x1800074fc  mov     bpl, 1
0x1800074ff  jmp     loc_1800073E0
0x180007504  mov     r9, rdi
0x180007507  mov     rdx, r15
0x18000750a  mov     rcx, rsi
0x18000750d  call    RtlStringCopyWorkerW
0x180007512  jmp     loc_180007490
0x180007517  mov     rbx, r12
0x18000751a  jmp     loc_1800073DD
0x18000751f  test    bpl, bpl
0x180007522  jnz     short loc_18000753E
0x180007524  cmp     rbx, 2
0x180007528  jb      short loc_180007537
0x18000752a  cmp     [rdi], r8w
0x18000752e  jnz     short loc_180007537
0x180007530  cmp     [rdi+2], r8w
0x180007535  jz      short loc_180007560
0x180007537  mov     eax, 57h ; 'W'
0x18000753c  jmp     short loc_1800074BF
0x18000753e  cmp     rbx, 8
0x180007542  jb      short loc_180007537
0x180007544  cmp     word ptr [rdi+8], 55h ; 'U'
0x180007549  jnz     short loc_180007537
0x18000754b  cmp     word ptr [rdi+0Ah], 4Eh ; 'N'
0x180007550  jnz     short loc_180007537
0x180007552  cmp     word ptr [rdi+0Ch], 43h ; 'C'
0x180007557  jnz     short loc_180007537
0x180007559  cmp     [rdi+0Eh], r8w
0x18000755e  jnz     short loc_180007537
0x180007560  mov     r14b, 1
0x180007563  jmp     loc_180007408
0x180007568  test    r14b, r14b
0x18000756b  jz      short loc_180007576
0x18000756d  add     rbx, 6
0x180007571  jmp     loc_180007411
0x180007576  add     rbx, 4
0x18000757a  jmp     loc_180007411
0x18000757f  mov     eax, 0CEh
0x180007584  jmp     loc_1800074BF
0x180007589  mov     eax, 0Eh
0x18000758e  jmp     loc_1800074BF
0x180007593  lea     r8, aUnc; "\\\\?\\UNC\\"
0x18000759a  mov     rdx, r15; unsigned __int64
0x18000759d  mov     rcx, rsi; unsigned __int16 *
0x1800075a0  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800075a5  lea     r8, [rdi+4]
0x1800075a9  jmp     loc_180007488
0x1800075ae  mov     [rsi+rbx*2-2], r12w
0x1800075b4  dec     rbx
0x1800075b7  jmp     loc_18000749C
```
