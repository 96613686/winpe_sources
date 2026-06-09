# FTP_VDIR_PARENT_TABLE::InitializeFromCustomHomeDirectoryInfo(ushort const *)

- ea: `0x180018764`
- end: `0x180018ab9`
- name: `?InitializeFromCustomHomeDirectoryInfo@FTP_VDIR_PARENT_TABLE@@QEAAJPEBG@Z`
- size: `853`
- prototype: `__int64 __fastcall(FTP_VDIR_PARENT_TABLE *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180010370`
- `0x180011c38`

## callees

- `0x180017db0`
- `0x180017ed8`
- `0x180018014`
- `0x180018764`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800188b2`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x1800188b2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001885a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018881`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018968`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800189bd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001885a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018881`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018968`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800189bd`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180018928`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800189c5`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180018928`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800189c5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800187d5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800187f6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001881e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800187d5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800187f6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001881e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018a3b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018a46`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018a52`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018a70`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018a7b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018a87`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018a3b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018a46`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018a52`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018a70`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018a7b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018a87`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FTP_VDIR_PARENT_TABLE::InitializeFromCustomHomeDirectoryInfo(
        FTP_VDIR_PARENT_TABLE **this,
        const unsigned __int16 *a2)
{
  int Entry; // ebx
  int v5; // r15d
  const unsigned __int16 *v6; // rsi
  const unsigned __int16 *v7; // rdi
  unsigned __int16 v8; // ax
  __int64 v9; // rcx
  const unsigned __int16 *v10; // rdx
  unsigned __int16 v11; // ax
  const unsigned __int16 *v12; // rdi
  const unsigned __int16 *v13; // rax
  unsigned __int16 i; // cx
  int v15; // eax
  FTP_VDIR_PARENT_ENTRY ***v16; // rcx
  struct FTP_VDIR_PARENT_ENTRY *v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-C8h] BYREF
  const unsigned __int16 *v20; // [rsp+58h] [rbp-A8h]
  unsigned int v21; // [rsp+60h] [rbp-A0h]
  unsigned int v22; // [rsp+68h] [rbp-98h]
  _BYTE v23[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v24; // [rsp+90h] [rbp-70h]
  _BYTE v25[32]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v26; // [rsp+C8h] [rbp-38h]
  int v27; // [rsp+D8h] [rbp-28h]
  unsigned __int16 v28[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v29[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v30[64]; // [rsp+1E0h] [rbp+E0h] BYREF

  Entry = 0;
  v18 = 0;
  v5 = 0;
  v6 = a2;
  if ( !*a2 )
    return (unsigned int)Entry;
  while ( 1 )
  {
    memset_0(v28, 0, sizeof(v28));
    STRU::STRU((STRU *)v19, v28, 0x40u);
    memset_0(v29, 0, sizeof(v29));
    STRU::STRU((STRU *)v25, v29, 0x40u);
    memset_0(v30, 0, sizeof(v30));
    STRU::STRU((STRU *)v23, v30, 0x40u);
    v7 = v6;
    if ( *v6 != 124 )
    {
      v8 = *v6;
      do
      {
        if ( !v8 )
          break;
        v8 = *++v7;
      }
      while ( *v7 != 124 );
    }
    if ( v5 || *v7 )
    {
      if ( *v6 == 47 )
      {
        *v20 = 0;
        v22 = 0;
      }
      else
      {
        Entry = STRU::Copy((STRU *)v19, L"/");
        if ( Entry < 0 )
          goto LABEL_53;
      }
      Entry = STRU::Append((STRU *)v19, v6, v7 - v6);
      if ( Entry < 0 )
        goto LABEL_53;
    }
    else
    {
      Entry = STRU::Copy((STRU *)v19, L"/");
      if ( Entry < 0 )
        goto LABEL_53;
      v7 = a2;
    }
    if ( v22 >= 2 )
    {
      v9 = v22 - 1;
      if ( v20[v9] == 47 && (unsigned int)v9 < v21 >> 1 )
      {
        v20[v9] = 0;
        v22 = v9;
      }
    }
    if ( *v7 == 124 )
    {
      v10 = ++v7;
      if ( *v7 == 124 )
        goto LABEL_26;
    }
    else
    {
      v10 = v7;
    }
    v11 = *v7;
    do
    {
      if ( !v11 )
        break;
      v11 = *++v7;
    }
    while ( *v7 != 124 );
LABEL_26:
    Entry = STRU::Copy((STRU *)v25, v10, v7 - v10);
    if ( Entry < 0 )
      goto LABEL_53;
    if ( !v27 )
      break;
    v6 = v7 + 1;
    if ( *v7 != 124 )
      v6 = v7;
    if ( *v20 != 47 || v20[1] )
    {
      v12 = 0;
      v13 = v20;
      for ( i = *v20; i; i = *v13 )
      {
        ++v13;
        if ( i == 47 )
          v12 = v13;
      }
      if ( (unsigned int)(v12 - v20) == 1 )
        v15 = STRU::Copy((STRU *)v23, L"/");
      else
        v15 = STRU::Copy((STRU *)v23, v20, v12 - v20 - 1);
      Entry = v15;
      if ( v15 < 0 )
        goto LABEL_53;
      Entry = FTP_VDIR_PARENT_TABLE::FindEntry(this, v24, &v18);
      if ( Entry < 0 )
        goto LABEL_53;
      v16 = (FTP_VDIR_PARENT_ENTRY ***)v18;
      if ( !v18 )
      {
        Entry = FTP_VDIR_PARENT_TABLE::AddEntry((FTP_VDIR_PARENT_TABLE *)this, v24, &v18);
        if ( Entry < 0 )
          goto LABEL_53;
        v16 = (FTP_VDIR_PARENT_ENTRY ***)v18;
      }
      if ( v12 )
      {
        if ( *v12 )
        {
          Entry = FTP_VDIR_PARENT_ENTRY::AddChildEntry(v16, 0, v26, v12, 0);
          if ( Entry < 0 )
            goto LABEL_53;
        }
      }
    }
    else
    {
      Entry = STRU::Copy((STRU *)(this + 2), v26);
      if ( Entry < 0 )
        goto LABEL_53;
    }
    STRU::~STRU(v23);
    STRU::~STRU(v25);
    STRU::~STRU(v19);
    if ( !*v6 )
      return (unsigned int)Entry;
    ++v5;
  }
  Entry = -2147024809;
LABEL_53:
  STRU::~STRU(v23);
  STRU::~STRU(v25);
  STRU::~STRU(v19);
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x180018764  mov     [rsp-8+arg_10], rbx
0x180018769  push    rbp
0x18001876a  push    rsi
0x18001876b  push    rdi
0x18001876c  push    r12
0x18001876e  push    r13
0x180018770  push    r14
0x180018772  push    r15
0x180018774  lea     rbp, [rsp-170h]
0x18001877c  sub     rsp, 270h
0x180018783  mov     rax, cs:__security_cookie
0x18001878a  xor     rax, rsp
0x18001878d  mov     [rbp+1A0h+var_40], rax
0x180018794  mov     r14, rdx
0x180018797  mov     r13, rcx
0x18001879a  xor     r12d, r12d
0x18001879d  mov     ebx, r12d
0x1800187a0  mov     [rsp+2A0h+var_270], r12
0x1800187a5  mov     r15d, r12d
0x1800187a8  mov     rsi, rdx
0x1800187ab  cmp     [rdx], r12w
0x1800187af  jz      loc_180018A8D
0x1800187b5  mov     ebx, 80h
0x1800187ba  mov     r8d, ebx; Size
0x1800187bd  xor     edx, edx; Val
0x1800187bf  lea     rcx, [rbp+1A0h+var_1C0]; void *
0x1800187c3  call    memset_0
0x1800187c8  lea     r8d, [rbx-40h]
0x1800187cc  lea     rdx, [rbp+1A0h+var_1C0]
0x1800187d0  lea     rcx, [rsp+2A0h+var_268]
0x1800187d5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800187db  nop
0x1800187dc  mov     r8d, ebx; Size
0x1800187df  xor     edx, edx; Val
0x1800187e1  lea     rcx, [rbp+1A0h+var_140]; void *
0x1800187e5  call    memset_0
0x1800187ea  lea     r8d, [rbx-40h]
0x1800187ee  lea     rdx, [rbp+1A0h+var_140]
0x1800187f2  lea     rcx, [rbp+1A0h+var_1F8]
0x1800187f6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800187fc  nop
0x1800187fd  mov     r8d, ebx; Size
0x180018800  xor     edx, edx; Val
0x180018802  lea     rcx, [rbp+1A0h+var_C0]; void *
0x180018809  call    memset_0
0x18001880e  lea     r8d, [rbx-40h]
0x180018812  lea     rdx, [rbp+1A0h+var_C0]
0x180018819  lea     rcx, [rsp+2A0h+var_230]
0x18001881e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180018824  nop
0x180018825  mov     rdi, rsi
0x180018828  cmp     word ptr [rsi], 7Ch ; '|'
0x18001882c  jz      short loc_180018843
0x18001882e  movzx   eax, word ptr [rsi]
0x180018831  test    ax, ax
0x180018834  jz      short loc_180018843
0x180018836  add     rdi, 2
0x18001883a  movzx   eax, word ptr [rdi]
0x18001883d  cmp     ax, 7Ch ; '|'
0x180018841  jnz     short loc_180018831
0x180018843  test    r15d, r15d
0x180018846  jnz     short loc_18001886F
0x180018848  cmp     [rdi], r12w
0x18001884c  jnz     short loc_18001886F
0x18001884e  lea     rdx, asc_18004BD14; "/"
0x180018855  lea     rcx, [rsp+2A0h+var_268]
0x18001885a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018860  mov     ebx, eax
0x180018862  test    eax, eax
0x180018864  js      loc_180018A6B
0x18001886a  mov     rdi, r14
0x18001886d  jmp     short loc_1800188C2
0x18001886f  cmp     word ptr [rsi], 2Fh ; '/'
0x180018873  jz      short loc_180018893
0x180018875  lea     rdx, asc_18004BD14; "/"
0x18001887c  lea     rcx, [rsp+2A0h+var_268]
0x180018881  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018887  mov     ebx, eax
0x180018889  test    eax, eax
0x18001888b  js      loc_180018A6B
0x180018891  jmp     short loc_1800188A1
0x180018893  mov     rax, [rsp+2A0h+var_248]
0x180018898  mov     [rax], r12w
0x18001889c  mov     [rsp+2A0h+var_238], r12d
0x1800188a1  mov     r8, rdi
0x1800188a4  sub     r8, rsi
0x1800188a7  sar     r8, 1
0x1800188aa  mov     rdx, rsi
0x1800188ad  lea     rcx, [rsp+2A0h+var_268]
0x1800188b2  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x1800188b8  mov     ebx, eax
0x1800188ba  test    eax, eax
0x1800188bc  js      loc_180018A6B
0x1800188c2  mov     ecx, [rsp+2A0h+var_238]
0x1800188c6  cmp     ecx, 2
0x1800188c9  jb      short loc_1800188ED
0x1800188cb  dec     ecx
0x1800188cd  mov     r8, [rsp+2A0h+var_248]
0x1800188d2  cmp     word ptr [r8+rcx*2], 2Fh ; '/'
0x1800188d8  jnz     short loc_1800188ED
0x1800188da  mov     eax, [rsp+2A0h+var_240]
0x1800188de  shr     eax, 1
0x1800188e0  cmp     ecx, eax
0x1800188e2  jnb     short loc_1800188ED
0x1800188e4  mov     [r8+rcx*2], r12w
0x1800188e9  mov     [rsp+2A0h+var_238], ecx
0x1800188ed  mov     si, 7Ch ; '|'
0x1800188f1  cmp     [rdi], si
0x1800188f4  jnz     short loc_180018904
0x1800188f6  add     rdi, 2
0x1800188fa  mov     rdx, rdi
0x1800188fd  cmp     [rdi], si
0x180018900  jz      short loc_18001891B
0x180018902  jmp     short loc_180018907
0x180018904  mov     rdx, rdi
0x180018907  movzx   eax, word ptr [rdi]
0x18001890a  test    ax, ax
0x18001890d  jz      short loc_18001891B
0x18001890f  add     rdi, 2
0x180018913  movzx   eax, word ptr [rdi]
0x180018916  cmp     ax, si
0x180018919  jnz     short loc_18001890A
0x18001891b  mov     r8, rdi
0x18001891e  sub     r8, rdx
0x180018921  sar     r8, 1
0x180018924  lea     rcx, [rbp+1A0h+var_1F8]
0x180018928  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18001892e  mov     ebx, eax
0x180018930  test    eax, eax
0x180018932  js      loc_180018A6B
0x180018938  cmp     [rbp+1A0h+var_1C8], r12d
0x18001893c  jz      loc_180018A66
0x180018942  cmp     [rdi], si
0x180018945  lea     rsi, [rdi+2]
0x180018949  jz      short loc_18001894E
0x18001894b  mov     rsi, rdi
0x18001894e  mov     rdx, [rsp+2A0h+var_248]
0x180018953  cmp     word ptr [rdx], 2Fh ; '/'
0x180018957  jnz     short loc_180018982
0x180018959  cmp     [rdx+2], r12w
0x18001895e  jnz     short loc_180018982
0x180018960  lea     rcx, [r13+10h]
0x180018964  mov     rdx, [rbp+1A0h+var_1D8]
0x180018968  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001896e  mov     ebx, eax
0x180018970  lea     rcx, [rsp+2A0h+var_230]
0x180018975  test    eax, eax
0x180018977  js      loc_180018A70
0x18001897d  jmp     loc_180018A3B
0x180018982  mov     rdi, r12
0x180018985  mov     rax, rdx
0x180018988  movzx   ecx, word ptr [rdx]
0x18001898b  jmp     short loc_18001899D
0x18001898d  add     rax, 2
0x180018991  cmp     cx, 2Fh ; '/'
0x180018995  jnz     short loc_18001899A
0x180018997  mov     rdi, rax
0x18001899a  movzx   ecx, word ptr [rax]
0x18001899d  test    cx, cx
0x1800189a0  jnz     short loc_18001898D
0x1800189a2  mov     r8, rdi
0x1800189a5  sub     r8, rdx
0x1800189a8  sar     r8, 1
0x1800189ab  sub     r8d, 1
0x1800189af  lea     rcx, [rsp+2A0h+var_230]
0x1800189b4  jnz     short loc_1800189C5
0x1800189b6  lea     rdx, asc_18004BD14; "/"
0x1800189bd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800189c3  jmp     short loc_1800189CB
0x1800189c5  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800189cb  mov     ebx, eax
0x1800189cd  test    eax, eax
0x1800189cf  js      loc_180018A6B
0x1800189d5  lea     r8, [rsp+2A0h+var_270]; struct FTP_VDIR_PARENT_ENTRY **
0x1800189da  mov     rdx, [rbp+1A0h+var_210]; unsigned __int16 *
0x1800189de  mov     rcx, r13; this
0x1800189e1  call    ?FindEntry@FTP_VDIR_PARENT_TABLE@@QEAAJPEBGPEAPEAVFTP_VDIR_PARENT_ENTRY@@@Z; FTP_VDIR_PARENT_TABLE::FindEntry(ushort const *,FTP_VDIR_PARENT_ENTRY * *)
0x1800189e6  mov     ebx, eax
0x1800189e8  test    eax, eax
0x1800189ea  js      short loc_180018A6B
0x1800189ec  mov     rcx, [rsp+2A0h+var_270]
0x1800189f1  test    rcx, rcx
0x1800189f4  jnz     short loc_180018A12
0x1800189f6  lea     r8, [rsp+2A0h+var_270]; struct FTP_VDIR_PARENT_ENTRY **
0x1800189fb  mov     rdx, [rbp+1A0h+var_210]; unsigned __int16 *
0x1800189ff  mov     rcx, r13; this
0x180018a02  call    ?AddEntry@FTP_VDIR_PARENT_TABLE@@QEAAJPEBGPEAPEAVFTP_VDIR_PARENT_ENTRY@@@Z; FTP_VDIR_PARENT_TABLE::AddEntry(ushort const *,FTP_VDIR_PARENT_ENTRY * *)
0x180018a07  mov     ebx, eax
0x180018a09  test    eax, eax
0x180018a0b  js      short loc_180018A6B
0x180018a0d  mov     rcx, [rsp+2A0h+var_270]; this
0x180018a12  test    rdi, rdi
0x180018a15  jz      short loc_180018A36
0x180018a17  cmp     [rdi], r12w
0x180018a1b  jz      short loc_180018A36
0x180018a1d  mov     [rsp+2A0h+var_280], r12d; int
0x180018a22  mov     r9, rdi; unsigned __int16 *
0x180018a25  mov     r8, [rbp+1A0h+var_1D8]; unsigned __int16 *
0x180018a29  xor     edx, edx; unsigned int
0x180018a2b  call    ?AddChildEntry@FTP_VDIR_PARENT_ENTRY@@QEAAJKPEBG0H@Z; FTP_VDIR_PARENT_ENTRY::AddChildEntry(ulong,ushort const *,ushort const *,int)
0x180018a30  mov     ebx, eax
0x180018a32  test    eax, eax
0x180018a34  js      short loc_180018A6B
0x180018a36  lea     rcx, [rsp+2A0h+var_230]
0x180018a3b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180018a41  nop
0x180018a42  lea     rcx, [rbp+1A0h+var_1F8]
0x180018a46  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180018a4c  nop
0x180018a4d  lea     rcx, [rsp+2A0h+var_268]
0x180018a52  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180018a58  cmp     [rsi], r12w
0x180018a5c  jz      short loc_180018A8D
0x180018a5e  inc     r15d
0x180018a61  jmp     loc_1800187B5
0x180018a66  mov     ebx, 80070057h
0x180018a6b  lea     rcx, [rsp+2A0h+var_230]
0x180018a70  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180018a76  nop
0x180018a77  lea     rcx, [rbp+1A0h+var_1F8]
0x180018a7b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180018a81  nop
0x180018a82  lea     rcx, [rsp+2A0h+var_268]
0x180018a87  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180018a8d  mov     eax, ebx
0x180018a8f  mov     rcx, [rbp+1A0h+var_40]
0x180018a96  xor     rcx, rsp; StackCookie
0x180018a99  call    __security_check_cookie
0x180018a9e  mov     rbx, [rsp+2A0h+arg_10]
0x180018aa6  add     rsp, 270h
0x180018aad  pop     r15
0x180018aaf  pop     r14
0x180018ab1  pop     r13
0x180018ab3  pop     r12
0x180018ab5  pop     rdi
0x180018ab6  pop     rsi
0x180018ab7  pop     rbp
0x180018ab8  retn
```
