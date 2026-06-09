# ModCache::LoadTypes(void)

- ea: `0x1800beef0`
- end: `0x1800bf497`
- name: `?LoadTypes@ModCache@@QEAA_NXZ`
- size: `1447`
- prototype: `bool __fastcall(ModCache *__hidden this)`
- caller_count: `5`
- callee_count: `12`
- tags: ``

## callers

- `0x1800bbcb0`
- `0x1800bc920`
- `0x1800beef0`
- `0x1800c7b30`
- `0x1800c7ff0`

## callees

- `0x180026980`
- `0x1800269f8`
- `0x1800beef0`
- `0x1800bfb40`
- `0x1800c0690`
- `0x1800c0e90`
- `0x1800c4d90`
- `0x1801286c0`
- `0x18016944c`
- `0x180169470`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__fullpath` at `0x1800bf016`
- `api-ms-win-crt-private-l1-1-0!_o__fullpath` at `0x1800bf112`
- `api-ms-win-crt-private-l1-1-0!_o__fullpath` at `0x1800bf016`
- `api-ms-win-crt-private-l1-1-0!_o__fullpath` at `0x1800bf112`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800bf0e3`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800bf12b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800bf19b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800bf3ef`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800bf0e3`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800bf12b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800bf19b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800bf3ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ModCache::LoadTypes(ModCache *this)
{
  ModCache *v1; // r15
  unsigned int v2; // r13d
  const char *v3; // rbx
  char *v4; // rax
  char *v5; // r12
  PSGSI1::EnumPubsByAddr *v6; // rdi
  unsigned int v7; // r14d
  __int64 v8; // rdx
  unsigned int v9; // r15d
  ModCache *v10; // rsi
  int v11; // eax
  bool v12; // cl
  char *v13; // rbx
  char *v14; // rax
  unsigned __int64 v15; // r15
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rax
  PSGSI1::EnumPubsByAddr *v18; // rbx
  unsigned int i; // ecx
  char v20; // r8
  unsigned __int8 *v21; // rbx
  __int16 v22; // ax
  unsigned __int64 v24; // rax
  unsigned __int64 v25; // rcx
  __int64 v26; // rcx
  char *v27; // rcx
  char v28; // al
  char v29; // [rsp+38h] [rbp-D0h]
  __int16 v30; // [rsp+39h] [rbp-CFh]
  char *Str; // [rsp+40h] [rbp-C8h]
  int v32; // [rsp+48h] [rbp-C0h] BYREF
  int v33; // [rsp+4Ch] [rbp-BCh]
  ModCache *v34; // [rsp+50h] [rbp-B8h]
  unsigned __int8 *v35; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v36; // [rsp+60h] [rbp-A8h]
  unsigned int v37[2]; // [rsp+68h] [rbp-A0h] BYREF
  PSGSI1::EnumPubsByAddr *v38; // [rsp+70h] [rbp-98h]
  __int64 v39; // [rsp+78h] [rbp-90h]
  __int64 v40; // [rsp+80h] [rbp-88h]
  char Path[272]; // [rsp+88h] [rbp-80h] BYREF
  char Buffer[272]; // [rsp+198h] [rbp+90h] BYREF
  wchar_t WideCharStr[264]; // [rsp+2A8h] [rbp+1A0h] BYREF

  v40 = -2;
  v1 = this;
  v34 = this;
  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 488LL))(*((_QWORD *)this + 32)) )
    return 1;
  if ( !ModCache::OpenObjectFile(v1) || !DiaObjectFile::QueryTypes(*((DiaObjectFile **)v1 + 82), &v35, v37) )
    return 0;
  if ( !v35 )
    return 1;
  v2 = 0;
  if ( !SymCache::fRegisterPDBMappings(*((SymCache **)v1 + 81), 1, 0, 0, 0) )
    return 0;
  if ( *((_WORD *)v35 + 3) != 5385 )
    goto LABEL_55;
  v3 = (const char *)(v35 + 20);
  Str = (char *)(v35 + 20);
  if ( v35[20] != 37 )
  {
    v5 = (char *)v36;
    goto LABEL_11;
  }
  v4 = strchr_0((const char *)v35 + 21, 37);
  v5 = v4;
  if ( !v4 )
  {
LABEL_11:
    LOBYTE(v30) = 0;
    HIBYTE(v30) = _fullpath(Buffer, v3, 0x104u) != 0;
    goto LABEL_12;
  }
  v30 = 1;
  v5 = v4 + 1;
LABEL_12:
  v6 = 0;
  v38 = 0;
  v36 = 0;
  v7 = 0;
  v39 = 0;
  v8 = *((_QWORD *)v1 + 81);
  if ( (unsigned int)((unsigned __int64)(*(_DWORD *)(v8 + 104) - *(_DWORD *)(v8 + 96)) >> 3) <= 1 )
    goto LABEL_49;
  v29 = 0;
  v9 = 1;
  v33 = 1;
  do
  {
    if ( !v9 || v9 > (unsigned int)((unsigned __int64)(*(_DWORD *)(v8 + 104) - *(_DWORD *)(v8 + 96)) >> 3) )
    {
      v32 = 260;
      goto LABEL_46;
    }
    v10 = *(ModCache **)(*(_QWORD *)(v8 + 96) + 8LL * (v9 - 1));
    v32 = 260;
    if ( !v10
      || !(*(unsigned int (__fastcall **)(_QWORD *, char *, int *))(**((_QWORD **)v10 + 32) + 64LL))(
            *((_QWORD **)v10 + 32),
            Path,
            &v32) )
    {
      goto LABEL_46;
    }
    if ( (_BYTE)v30 )
    {
      v24 = -1;
      do
        ++v24;
      while ( Path[v24] );
      v25 = -1;
      do
        ++v25;
      while ( v5[v25] );
      if ( v24 > v25 )
      {
        v26 = -1;
        do
          ++v26;
        while ( v5[v26] );
        v27 = &Path[v24 - v26];
        if ( *v5 == 92 || *v5 == 47 )
          v28 = *v27;
        else
          v28 = *(v27 - 1);
        if ( v28 == 92 || v28 == 47 )
        {
          v12 = (unsigned int)_o__stricmp(v27, v5) == 0;
LABEL_75:
          if ( !v12 )
            goto LABEL_23;
          goto LABEL_76;
        }
      }
LABEL_23:
      v13 = strrchr_0(Path, 92);
      if ( !v13 )
        v13 = strrchr_0(Path, 47);
      v14 = strrchr_0(Str, 92);
      if ( !v14 )
        v14 = strrchr_0(Str, 47);
      if ( v13 && v14 && !(unsigned int)_o__stricmp(v13, v14) )
      {
        v15 = v7 + 1LL;
        if ( v15 > 0x1FFFFFFF )
          goto LABEL_80;
        if ( v15 > (unsigned int)v36 )
        {
          v16 = v7 + 1LL;
          if ( v15 <= (unsigned __int64)(unsigned int)(3 * v36) >> 1 )
            v16 = (unsigned __int64)(unsigned int)(3 * v36) >> 1;
          if ( v16 > 0x1FFFFFFF )
            v16 = 0x1FFFFFFF;
          v36 = v16;
          v17 = 8 * v16;
          if ( !is_mul_ok(v16, 8u) )
            v17 = -1;
          v18 = (PSGSI1::EnumPubsByAddr *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
          if ( !v18 )
          {
LABEL_80:
            SymCache::ReportErrorViaCallback(*((SymCache **)v34 + 81), -2147024882, 0, 0);
            goto LABEL_81;
          }
          if ( v6 )
          {
            for ( i = 0; i < v7; ++i )
              *((_QWORD *)v18 + i) = *((_QWORD *)v6 + i);
            PSGSI1::EnumPubsByAddr::release(v6);
          }
          v6 = v18;
          v38 = v18;
          HIDWORD(v39) = v36;
        }
        ++v7;
        LODWORD(v39) = v15;
        *((_QWORD *)v6 + (unsigned int)(v15 - 1)) = v10;
        v9 = v33;
      }
      v3 = Str;
LABEL_46:
      v20 = v29;
      goto LABEL_47;
    }
    v11 = _o__stricmp(Path, v3);
    v12 = v11 == 0;
    if ( !v11 || !HIBYTE(v30) )
      goto LABEL_75;
    if ( !_fullpath((char *)WideCharStr, Path, 0x104u) || (unsigned int)_o__stricmp(WideCharStr, Buffer) )
      goto LABEL_23;
LABEL_76:
    if ( !ModCache::LoadTypes(v10) )
      goto LABEL_81;
    if ( !(_BYTE)v30 )
      goto LABEL_52;
    v20 = 1;
    v29 = 1;
LABEL_47:
    v33 = ++v9;
    v8 = *((_QWORD *)v34 + 81);
  }
  while ( v9 < (unsigned int)((unsigned __int64)(*(_DWORD *)(v8 + 104) - *(_DWORD *)(v8 + 96)) >> 3) );
  if ( v20 )
    goto LABEL_52;
LABEL_49:
  if ( v7 )
  {
    while ( ModCache::LoadTypes(*((ModCache **)v6 + v2)) )
    {
      if ( ++v2 >= v7 )
        goto LABEL_52;
    }
LABEL_81:
    if ( v6 )
    {
      PSGSI1::EnumPubsByAddr::release(v6);
      return 0;
    }
    return 0;
  }
LABEL_52:
  if ( v6 )
    PSGSI1::EnumPubsByAddr::release(v6);
  v1 = v34;
LABEL_55:
  if ( !(*(unsigned int (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD))(**((_QWORD **)v1 + 32) + 16LL))(
          *((_QWORD *)v1 + 32),
          v35,
          v37[0]) )
  {
    v21 = v35;
    v22 = *((_WORD *)v35 + 3);
    if ( v22 == 22 || v22 == 5377 || v22 == 5397 )
    {
      SymCache::ReportErrorViaCallback(*((SymCache **)v1 + 81), 0, 0, 0);
      SZNameFromTSRecord_0((struct TYPTYPE *)(v21 + 4), WideCharStr, 260);
      SymCache::ReportErrorViaCallback(*((SymCache **)v1 + 81), -2140340023, WideCharStr, 0);
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800beef0  mov     rax, rsp
0x1800beef3  push    rbp
0x1800beef4  push    r12
0x1800beef6  push    r13
0x1800beef8  push    r14
0x1800beefa  push    r15
0x1800beefc  lea     rbp, [rax-3E8h]
0x1800bef03  sub     rsp, 4C0h
0x1800bef0a  mov     [rsp+4E0h+var_468], 0FFFFFFFFFFFFFFFEh
0x1800bef13  mov     [rax+10h], rbx
0x1800bef17  mov     [rax+18h], rsi
0x1800bef1b  mov     [rax+20h], rdi
0x1800bef1f  mov     rax, cs:__security_cookie
0x1800bef26  xor     rax, rsp
0x1800bef29  mov     [rbp+3E0h+var_30], rax
0x1800bef30  mov     r15, rcx
0x1800bef33  mov     [rsp+4E0h+var_498], rcx
0x1800bef38  mov     rcx, [rcx+100h]
0x1800bef3f  mov     rax, [rcx]
0x1800bef42  mov     rax, [rax+1E8h]
0x1800bef49  call    cs:__guard_dispatch_icall_fptr
0x1800bef4f  test    eax, eax
0x1800bef51  jz      loc_1800BF465
0x1800bef57  mov     rcx, r15; this
0x1800bef5a  call    ?OpenObjectFile@ModCache@@AEAA_NXZ; ModCache::OpenObjectFile(void)
0x1800bef5f  test    al, al
0x1800bef61  jz      loc_1800BF37C
0x1800bef67  lea     r8, [rsp+4E0h+var_480]; unsigned int *
0x1800bef6c  lea     rdx, [rsp+4E0h+var_490]; unsigned __int8 **
0x1800bef71  mov     rcx, [r15+290h]; this
0x1800bef78  call    ?QueryTypes@DiaObjectFile@@QEAA_NPEAPEAEPEAK@Z; DiaObjectFile::QueryTypes(uchar * *,ulong *)
0x1800bef7d  test    al, al
0x1800bef7f  jz      loc_1800BF37C
0x1800bef85  cmp     [rsp+4E0h+var_490], 0
0x1800bef8b  jz      loc_1800BF465
0x1800bef91  xor     r13d, r13d
0x1800bef94  mov     [rsp+4E0h+var_4C0], r13; wchar_t **
0x1800bef99  xor     r9d, r9d; wchar_t **
0x1800bef9c  xor     r8d, r8d; unsigned int *
0x1800bef9f  mov     dl, 1; bool
0x1800befa1  mov     rcx, [r15+288h]; this
0x1800befa8  call    ?fRegisterPDBMappings@SymCache@@QEAA_N_NPEAKPEAPEA_W2@Z; SymCache::fRegisterPDBMappings(bool,ulong *,wchar_t * *,wchar_t * *)
0x1800befad  test    al, al
0x1800befaf  jz      loc_1800BF37C
0x1800befb5  mov     rax, [rsp+4E0h+var_490]
0x1800befba  mov     ecx, 1509h
0x1800befbf  cmp     [rax+6], cx
0x1800befc3  jnz     loc_1800BF2EE
0x1800befc9  lea     rbx, [rax+14h]
0x1800befcd  mov     [rsp+4E0h+Str], rbx
0x1800befd2  cmp     byte ptr [rbx], 25h ; '%'
0x1800befd5  jnz     short loc_1800BEFFC
0x1800befd7  lea     rcx, [rbx+1]; Str
0x1800befdb  mov     edx, 25h ; '%'; Val
0x1800befe0  call    strchr_0
0x1800befe5  mov     r12, rax
0x1800befe8  test    rax, rax
0x1800befeb  jz      short loc_1800BF001
0x1800befed  mov     byte ptr [rsp+4E0h+var_4B0+1], 1
0x1800beff2  mov     byte ptr [rsp+4E0h+var_4B0+2], r13b
0x1800beff7  inc     r12
0x1800beffa  jmp     short loc_1800BF024
0x1800beffc  mov     r12, [rsp+4E0h+var_488]
0x1800bf001  mov     byte ptr [rsp+4E0h+var_4B0+1], r13b
0x1800bf006  mov     r8d, 104h; BufferCount
0x1800bf00c  mov     rdx, rbx; Path
0x1800bf00f  lea     rcx, [rbp+3E0h+Buffer]; Buffer
0x1800bf016  call    cs:__imp__fullpath
0x1800bf01c  test    rax, rax
0x1800bf01f  setnz   byte ptr [rsp+4E0h+var_4B0+2]
0x1800bf024  mov     rdi, r13
0x1800bf027  mov     [rsp+4E0h+var_478], r13
0x1800bf02c  mov     eax, r13d
0x1800bf02f  mov     [rsp+4E0h+var_488], rax
0x1800bf034  mov     dword ptr [rsp+4E0h+var_470+4], eax
0x1800bf038  mov     r14d, r13d
0x1800bf03b  mov     dword ptr [rsp+4E0h+var_470], r13d
0x1800bf040  mov     rdx, [r15+288h]
0x1800bf047  mov     eax, [rdx+68h]
0x1800bf04a  sub     eax, [rdx+60h]
0x1800bf04d  movsxd  rcx, eax
0x1800bf050  shr     rcx, 3
0x1800bf054  cmp     ecx, 1
0x1800bf057  jbe     loc_1800BF2B1
0x1800bf05d  mov     byte ptr [rsp+4E0h+var_4B0], 0
0x1800bf062  mov     r15d, 1
0x1800bf068  mov     dword ptr [rsp+4E0h+var_4A0+4], r15d
0x1800bf06d  nop     dword ptr [rax]
0x1800bf070  test    r15d, r15d
0x1800bf073  jz      loc_1800BF426
0x1800bf079  mov     eax, [rdx+68h]
0x1800bf07c  sub     eax, [rdx+60h]
0x1800bf07f  movsxd  rcx, eax
0x1800bf082  shr     rcx, 3
0x1800bf086  cmp     r15d, ecx
0x1800bf089  ja      loc_1800BF426
0x1800bf08f  lea     ecx, [r15-1]
0x1800bf093  mov     rax, [rdx+60h]
0x1800bf097  mov     rsi, [rax+rcx*8]
0x1800bf09b  mov     dword ptr [rsp+4E0h+var_4A0], 104h
0x1800bf0a3  test    rsi, rsi
0x1800bf0a6  jz      loc_1800BF27C
0x1800bf0ac  mov     rcx, [rsi+100h]
0x1800bf0b3  mov     rax, [rcx]
0x1800bf0b6  lea     r8, [rsp+4E0h+var_4A0]
0x1800bf0bb  lea     rdx, [rbp+3E0h+Path]
0x1800bf0bf  mov     rax, [rax+40h]
0x1800bf0c3  call    cs:__guard_dispatch_icall_fptr
0x1800bf0c9  test    eax, eax
0x1800bf0cb  jz      loc_1800BF27C
0x1800bf0d1  lea     rcx, [rbp+3E0h+Path]
0x1800bf0d5  cmp     byte ptr [rsp+4E0h+var_4B0+1], 0
0x1800bf0da  jnz     loc_1800BF383
0x1800bf0e0  mov     rdx, rbx
0x1800bf0e3  call    cs:__imp__o__stricmp
0x1800bf0e9  test    eax, eax
0x1800bf0eb  setz    cl
0x1800bf0ee  test    eax, eax
0x1800bf0f0  jz      loc_1800BF3FA
0x1800bf0f6  cmp     byte ptr [rsp+4E0h+var_4B0+2], 0
0x1800bf0fb  jz      loc_1800BF3FA
0x1800bf101  mov     r8d, 104h; BufferCount
0x1800bf107  lea     rdx, [rbp+3E0h+Path]; Path
0x1800bf10b  lea     rcx, [rbp+3E0h+WideCharStr]; Buffer
0x1800bf112  call    cs:__imp__fullpath
0x1800bf118  test    rax, rax
0x1800bf11b  jz      short loc_1800BF139
0x1800bf11d  lea     rdx, [rbp+3E0h+Buffer]
0x1800bf124  lea     rcx, [rbp+3E0h+WideCharStr]
0x1800bf12b  call    cs:__imp__o__stricmp
0x1800bf131  test    eax, eax
0x1800bf133  jz      loc_1800BF402
0x1800bf139  mov     edx, 5Ch ; '\'; Ch
0x1800bf13e  lea     rcx, [rbp+3E0h+Path]; Str
0x1800bf142  call    strrchr_0
0x1800bf147  mov     rbx, rax
0x1800bf14a  test    rax, rax
0x1800bf14d  jnz     short loc_1800BF160
0x1800bf14f  mov     edx, 2Fh ; '/'; Ch
0x1800bf154  lea     rcx, [rbp+3E0h+Path]; Str
0x1800bf158  call    strrchr_0
0x1800bf15d  mov     rbx, rax
0x1800bf160  mov     edx, 5Ch ; '\'; Ch
0x1800bf165  mov     rcx, [rsp+4E0h+Str]; Str
0x1800bf16a  call    strrchr_0
0x1800bf16f  test    rax, rax
0x1800bf172  jnz     short loc_1800BF183
0x1800bf174  mov     edx, 2Fh ; '/'; Ch
0x1800bf179  mov     rcx, [rsp+4E0h+Str]; Str
0x1800bf17e  call    strrchr_0
0x1800bf183  test    rbx, rbx
0x1800bf186  jz      loc_1800BF277
0x1800bf18c  test    rax, rax
0x1800bf18f  jz      loc_1800BF277
0x1800bf195  mov     rdx, rax
0x1800bf198  mov     rcx, rbx
0x1800bf19b  call    cs:__imp__o__stricmp
0x1800bf1a1  test    eax, eax
0x1800bf1a3  jnz     loc_1800BF277
0x1800bf1a9  mov     r15d, r14d
0x1800bf1ac  inc     r15
0x1800bf1af  mov     r9d, 1FFFFFFFh
0x1800bf1b5  cmp     r15, r9
0x1800bf1b8  ja      loc_1800BF433
0x1800bf1be  mov     r8, [rsp+4E0h+var_488]
0x1800bf1c3  mov     eax, r8d
0x1800bf1c6  cmp     r15, rax
0x1800bf1c9  jbe     loc_1800BF262
0x1800bf1cf  lea     ecx, [r8+r8*2]
0x1800bf1d3  shr     rcx, 1
0x1800bf1d6  mov     rdx, r15
0x1800bf1d9  cmp     r15, rcx
0x1800bf1dc  cmovbe  rdx, rcx
0x1800bf1e0  cmp     rdx, r9
0x1800bf1e3  cmova   rdx, r9
0x1800bf1e7  mov     [rsp+4E0h+var_488], rdx
0x1800bf1ec  mov     eax, 8
0x1800bf1f1  mul     rdx
0x1800bf1f4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800bf1fb  cmovb   rax, rcx
0x1800bf1ff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bf206  mov     rcx, rax; unsigned __int64
0x1800bf209  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800bf20e  mov     rbx, rax
0x1800bf211  test    rax, rax
0x1800bf214  jz      loc_1800BF433
0x1800bf21a  test    rdi, rdi
0x1800bf21d  jz      short loc_1800BF251
0x1800bf21f  mov     ecx, r13d
0x1800bf222  test    r14d, r14d
0x1800bf225  jz      short loc_1800BF249
0x1800bf227  nop     word ptr [rax+rax+00000000h]
0x1800bf230  mov     eax, ecx
0x1800bf232  lea     rdx, ds:0[rax*8]
0x1800bf23a  mov     rax, [rdx+rdi]
0x1800bf23e  mov     [rdx+rbx], rax
0x1800bf242  inc     ecx
0x1800bf244  cmp     ecx, r14d
0x1800bf247  jb      short loc_1800BF230
0x1800bf249  mov     rcx, rdi; this
0x1800bf24c  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800bf251  mov     rdi, rbx
0x1800bf254  mov     [rsp+4E0h+var_478], rbx
0x1800bf259  mov     rax, [rsp+4E0h+var_488]
0x1800bf25e  mov     dword ptr [rsp+4E0h+var_470+4], eax
0x1800bf262  mov     r14d, r15d
0x1800bf265  mov     dword ptr [rsp+4E0h+var_470], r15d
0x1800bf26a  lea     eax, [r15-1]
0x1800bf26e  mov     [rdi+rax*8], rsi
0x1800bf272  mov     r15d, dword ptr [rsp+4E0h+var_4A0+4]
0x1800bf277  mov     rbx, [rsp+4E0h+Str]
0x1800bf27c  movzx   r8d, byte ptr [rsp+4E0h+var_4B0]
0x1800bf282  inc     r15d
0x1800bf285  mov     dword ptr [rsp+4E0h+var_4A0+4], r15d
0x1800bf28a  mov     rax, [rsp+4E0h+var_498]
0x1800bf28f  mov     rdx, [rax+288h]
0x1800bf296  mov     eax, [rdx+68h]
0x1800bf299  sub     eax, [rdx+60h]
0x1800bf29c  movsxd  rcx, eax
0x1800bf29f  shr     rcx, 3
0x1800bf2a3  cmp     r15d, ecx
0x1800bf2a6  jb      loc_1800BF070
0x1800bf2ac  test    r8b, r8b
0x1800bf2af  jnz     short loc_1800BF2DC
0x1800bf2b1  test    r14d, r14d
0x1800bf2b4  jz      short loc_1800BF2DC
0x1800bf2b6  nop     word ptr [rax+rax+00000000h]
0x1800bf2c0  mov     ecx, r13d
0x1800bf2c3  mov     rcx, [rdi+rcx*8]; this
0x1800bf2c7  call    ?LoadTypes@ModCache@@QEAA_NXZ; ModCache::LoadTypes(void)
0x1800bf2cc  test    al, al
0x1800bf2ce  jz      loc_1800BF450
0x1800bf2d4  inc     r13d
0x1800bf2d7  cmp     r13d, r14d
0x1800bf2da  jb      short loc_1800BF2C0
0x1800bf2dc  test    rdi, rdi
0x1800bf2df  jz      short loc_1800BF2E9
0x1800bf2e1  mov     rcx, rdi; this
0x1800bf2e4  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1800bf2e9  mov     r15, [rsp+4E0h+var_498]
0x1800bf2ee  mov     rcx, [r15+100h]
0x1800bf2f5  mov     rax, [rcx]
0x1800bf2f8  mov     r8d, [rsp+4E0h+var_480]
0x1800bf2fd  mov     rdx, [rsp+4E0h+var_490]
0x1800bf302  mov     rax, [rax+10h]
0x1800bf306  call    cs:__guard_dispatch_icall_fptr
0x1800bf30c  test    eax, eax
0x1800bf30e  jnz     loc_1800BF465
0x1800bf314  mov     rbx, [rsp+4E0h+var_490]
0x1800bf319  movzx   eax, word ptr [rbx+6]
0x1800bf31d  cmp     ax, 16h
0x1800bf321  jz      short loc_1800BF337
0x1800bf323  mov     ecx, 1501h
0x1800bf328  cmp     ax, cx
0x1800bf32b  jz      short loc_1800BF337
0x1800bf32d  mov     ecx, 1515h
0x1800bf332  cmp     ax, cx
0x1800bf335  jnz     short loc_1800BF37C
0x1800bf337  xor     r9d, r9d; wchar_t *
0x1800bf33a  xor     r8d, r8d; wchar_t *
0x1800bf33d  xor     edx, edx; int
0x1800bf33f  mov     rcx, [r15+288h]; this
0x1800bf346  call    ?ReportErrorViaCallback@SymCache@@QEAAXJPEB_W0@Z; SymCache::ReportErrorViaCallback(long,wchar_t const *,wchar_t const *)
0x1800bf34b  mov     r8d, 104h; cchWideChar
0x1800bf351  lea     rdx, [rbp+3E0h+WideCharStr]; lpWideCharStr
0x1800bf358  lea     rcx, [rbx+4]; struct TYPTYPE *
0x1800bf35c  call    SZNameFromTSRecord_0
0x1800bf361  xor     r9d, r9d; wchar_t *
0x1800bf364  lea     r8, [rbp+3E0h+WideCharStr]; wchar_t *
0x1800bf36b  mov     edx, 806D00C9h; int
0x1800bf370  mov     rcx, [r15+288h]; this
0x1800bf377  call    ?ReportErrorViaCallback@SymCache@@QEAAXJPEB_W0@Z; SymCache::ReportErrorViaCallback(long,wchar_t const *,wchar_t const *)
0x1800bf37c  xor     al, al
0x1800bf37e  jmp     loc_1800BF467
0x1800bf383  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800bf38a  mov     rax, rdx
0x1800bf38d  nop     dword ptr [rax]
0x1800bf390  inc     rax
0x1800bf393  cmp     byte ptr [rcx+rax], 0
0x1800bf397  jnz     short loc_1800BF390
0x1800bf399  mov     rcx, rdx
0x1800bf39c  nop     dword ptr [rax+00h]
0x1800bf3a0  inc     rcx
0x1800bf3a3  cmp     byte ptr [r12+rcx], 0
0x1800bf3a8  jnz     short loc_1800BF3A0
0x1800bf3aa  cmp     rax, rcx
0x1800bf3ad  jbe     loc_1800BF139
0x1800bf3b3  mov     rcx, rdx
0x1800bf3b6  inc     rcx
0x1800bf3b9  cmp     byte ptr [r12+rcx], 0
0x1800bf3be  jnz     short loc_1800BF3B6
0x1800bf3c0  sub     rax, rcx
0x1800bf3c3  lea     rcx, [rbp+3E0h+Path]
0x1800bf3c7  add     rcx, rax
0x1800bf3ca  movzx   eax, byte ptr [r12]
0x1800bf3cf  cmp     al, 5Ch ; '\'
0x1800bf3d1  jz      short loc_1800BF3DD
0x1800bf3d3  cmp     al, 2Fh ; '/'
0x1800bf3d5  jz      short loc_1800BF3DD
0x1800bf3d7  movzx   eax, byte ptr [rcx-1]
  ... truncated ...
```
