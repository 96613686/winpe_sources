# CCompRC::LoadLibraryHelper(HINSTANCE__ * *,ushort *,ulong)

- ea: `0x18003d178`
- end: `0x18003d5dd`
- name: `?LoadLibraryHelper@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEAGK@Z`
- size: `1125`
- prototype: `__int64 __fastcall(CCompRC *__hidden this, HINSTANCE *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003d5e0`

## callees

- `0x18003073c`
- `0x180030d84`
- `0x180032ef4`
- `0x18003c7ec`
- `0x18003ca34`
- `0x18003cb48`
- `0x18003d110`
- `0x18003d178`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `ucrtbase_clr0400!wcscpy_s` at `0x18003d3d2`
- `ucrtbase_clr0400!wcscpy_s` at `0x18003d3f1`
- `ucrtbase_clr0400!wcscpy_s` at `0x18003d471`
- `ucrtbase_clr0400!wcscpy_s` at `0x18003d4c3`
- `ucrtbase_clr0400!wcscpy_s` at `0x18003d559`
- `ucrtbase_clr0400!wcscpy_s` at `0x18003d3d2`
- `ucrtbase_clr0400!wcscpy_s` at `0x18003d3f1`
- `ucrtbase_clr0400!wcscpy_s` at `0x18003d471`
- `ucrtbase_clr0400!wcscpy_s` at `0x18003d4c3`
- `ucrtbase_clr0400!wcscpy_s` at `0x18003d559`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CCompRC::LoadLibraryHelper(CCompRC *this, HINSTANCE *a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r13
  CCompRC *v4; // r14
  int ResourceFile; // ebx
  __int64 v6; // r12
  __int64 v7; // r15
  __int64 (__fastcall *v8)(unsigned int *); // rax
  int v9; // r8d
  char v10; // si
  __int64 v12; // r8
  unsigned int i; // r13d
  unsigned int v14; // ecx
  __int64 *v15; // rsi
  unsigned int j; // eax
  unsigned int *v17; // rsi
  unsigned int v18; // eax
  wchar_t *v19; // rbx
  wchar_t *v20; // rbx
  unsigned int v21; // edx
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  wchar_t *v25; // rcx
  IErrorInfo *v26; // rax
  IErrorInfo *v27; // rdi
  int v28; // [rsp+20h] [rbp-358h]
  unsigned __int16 *v29; // [rsp+28h] [rbp-350h]
  unsigned __int64 v30; // [rsp+30h] [rbp-348h]
  unsigned __int16 *v31; // [rsp+38h] [rbp-340h]
  unsigned __int64 v32; // [rsp+40h] [rbp-338h]
  __int64 v33; // [rsp+50h] [rbp-328h]
  int v34; // [rsp+50h] [rbp-328h]
  unsigned __int16 *Destination; // [rsp+60h] [rbp-318h]
  HINSTANCE *v36; // [rsp+68h] [rbp-310h]
  wchar_t *v38; // [rsp+80h] [rbp-2F8h]
  __int64 v40; // [rsp+90h] [rbp-2E8h]
  int v41; // [rsp+98h] [rbp-2E0h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-2D8h]
  _QWORD v43[3]; // [rsp+A8h] [rbp-2D0h] BYREF
  CCompRC *v44; // [rsp+C0h] [rbp-2B8h]
  unsigned int v45; // [rsp+D0h] [rbp-2A8h] BYREF
  __int64 v46; // [rsp+D8h] [rbp-2A0h] BYREF
  int v47; // [rsp+E0h] [rbp-298h]
  __int64 v48; // [rsp+110h] [rbp-268h] BYREF
  wchar_t Source[4]; // [rsp+118h] [rbp-260h] BYREF
  wchar_t v50[264]; // [rsp+120h] [rbp-258h] BYREF

  v3 = a3;
  Destination = a3;
  v36 = a2;
  v4 = this;
  v44 = this;
  ResourceFile = -2147467259;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(*((_QWORD *)this + 6) + 2 * v7) );
  SString::Startup();
  v45 = 0;
  v46 = 0;
  v47 = 5;
  v8 = (__int64 (__fastcall *)(unsigned int *))*((_QWORD *)v4 + 8);
  if ( v8 )
  {
    ResourceFile = v8(&v45);
  }
  else
  {
    v10 = 0;
    v41 = 0;
    v42 = 0;
    try
    {
      try
      {
        StringArrayList::Append((StringArrayList *)&v45, *(const struct SString **)&SString::s_Empty);
      }
      catch ( Exception *v48 )
      {
        Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v41);
        v42 = v48;
        throw;
      }
    }
    catch ( ... )
    {
      v43[1] = 0;
      v43[0] = &DelegatingException::`vftable';
      v43[2] = -1;
      Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v41, 919, v9);
      v34 = (*(__int64 (__fastcall **)(_QWORD *))(v43[0] + 16LL))(v43);
      v26 = (IErrorInfo *)(*(__int64 (__fastcall **)(_QWORD *))(v43[0] + 32LL))(v43);
      v27 = v26;
      if ( v26 )
      {
        SetErrorInfo(0, v26);
        ((void (__fastcall *)(IErrorInfo *))v27->lpVtbl->Release)(v27);
      }
      DelegatingException::~DelegatingException((DelegatingException *)v43);
      v6 = -1;
      ResourceFile = v34;
      v10 = v41;
      v4 = v44;
      v3 = a3;
      Destination = a3;
      v36 = a2;
    }
    if ( (v10 & 2) != 0 && g_fpHandleStackOverflowAfterCatch )
      g_fpHandleStackOverflowAfterCatch();
  }
  if ( ResourceFile == -2147024882 )
  {
    StringArrayList::~StringArrayList((StringArrayList *)&v45);
    return 2147942414LL;
  }
  else
  {
    v50[0] = 0;
    Source[0] = 0;
    v3[259] = 0;
    SplitPath(v3, Source, v9, v50, v28, v29, v30, v31, v32);
    v12 = -1;
    do
      ++v12;
    while ( Source[v12] );
    v33 = v12;
    do
      ++v6;
    while ( v50[v6] );
    v40 = v7 + v6 + v12 + 1;
    for ( i = 0; i < v45; v12 = v33 )
    {
      v14 = i;
      v15 = &v46;
      for ( j = v47; v14 >= j; j = *((_DWORD *)v15 + 2) )
      {
        v14 -= j;
        v15 = (__int64 *)*v15;
      }
      v17 = (unsigned int *)v15[v14 + 2];
      v18 = v17[2];
      if ( (v18 & 2) != 0 && ((v18 & 7) != 7 || SString::s_IsANSIMultibyte) )
      {
        if ( !(unsigned int)SString::ScanASCII((SString *)v17) )
          SString::ConvertToUnicode((SString *)v17);
        v12 = v33;
      }
      if ( v40 + (unsigned __int64)((*v17 >> ((v17[2] & 1) == 0)) - 1) > 0x104 )
      {
        ResourceFile = -2147467259;
      }
      else
      {
        wcscpy_s(Destination, v12 + 1, Source);
        v19 = &Destination[v33];
        wcscpy_s(v19, v6 + 1, v50);
        v20 = &v19[v6];
        v21 = v17[2];
        if ( *v17 >> ((v21 & 1) == 0) == 1 )
        {
          if ( (v21 & 2) != 0
            && ((v21 & 7) != 7 || SString::s_IsANSIMultibyte)
            && !(unsigned int)SString::ScanASCII((SString *)v17) )
          {
            SString::ConvertToUnicode((SString *)v17);
          }
          v25 = &v20[(*v17 >> ((v17[2] & 1) == 0)) - 1];
        }
        else
        {
          SString::ConvertToUnicode((SString *)v17);
          v38 = (wchar_t *)*((_QWORD *)v17 + 2);
          v22 = v17[2];
          if ( (v22 & 2) != 0
            && ((v22 & 7) != 7 || SString::s_IsANSIMultibyte)
            && !(unsigned int)SString::ScanASCII((SString *)v17) )
          {
            SString::ConvertToUnicode((SString *)v17);
          }
          wcscpy_s(v20, (unsigned __int64)*v17 >> ((v17[2] & 1) == 0), v38);
          v23 = v17[2];
          if ( (v23 & 2) != 0
            && ((v23 & 7) != 7 || SString::s_IsANSIMultibyte)
            && !(unsigned int)SString::ScanASCII((SString *)v17) )
          {
            SString::ConvertToUnicode((SString *)v17);
          }
          wcscpy_s(&v20[(*v17 >> ((v17[2] & 1) == 0)) - 1], v7 + 1, L"\\");
          v24 = v17[2];
          if ( (v24 & 2) != 0
            && ((v24 & 7) != 7 || SString::s_IsANSIMultibyte)
            && !(unsigned int)SString::ScanASCII((SString *)v17) )
          {
            SString::ConvertToUnicode((SString *)v17);
          }
          v25 = &v20[*v17 >> ((v17[2] & 1) == 0)];
        }
        wcscpy_s(v25, v7 + 1, *((const wchar_t **)v4 + 6));
        ResourceFile = CCompRC::LoadResourceFile(v4, v36, Destination);
        if ( ResourceFile >= 0 )
          goto LABEL_54;
      }
      ++i;
    }
    if ( ResourceFile < 0 )
      ResourceFile = CCompRC::LoadResourceFile(v4, v36, *((const unsigned __int16 **)v4 + 6));
LABEL_54:
    StringArrayList::~StringArrayList((StringArrayList *)&v45);
    return (unsigned int)ResourceFile;
  }
}

```

## disassembly

```asm
0x18003d178  push    rbx
0x18003d17a  push    rsi
0x18003d17b  push    rdi
0x18003d17c  push    r12
0x18003d17e  push    r13
0x18003d180  push    r14
0x18003d182  push    r15
0x18003d184  sub     rsp, 340h
0x18003d18b  mov     rax, cs:__security_cookie
0x18003d192  xor     rax, rsp
0x18003d195  mov     [rsp+378h+var_48], rax
0x18003d19d  mov     r13, r8
0x18003d1a0  mov     [rsp+378h+Destination], r8
0x18003d1a5  mov     [rsp+378h+var_310], rdx
0x18003d1aa  mov     r14, rcx
0x18003d1ad  mov     [rsp+378h+var_2B8], rcx
0x18003d1b5  mov     [rsp+378h+var_2E8], rdx
0x18003d1bd  mov     [rsp+378h+var_2F8], r8
0x18003d1c5  mov     ebx, 80004005h
0x18003d1ca  mov     rax, [rcx+30h]
0x18003d1ce  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003d1d2  mov     r15, r12
0x18003d1d5  xor     edi, edi
0x18003d1d7  inc     r15
0x18003d1da  cmp     [rax+r15*2], di
0x18003d1df  jnz     short loc_18003D1D7
0x18003d1e1  mov     [rsp+378h+var_320], r15
0x18003d1e6  call    ?Startup@SString@@SAXXZ; SString::Startup(void)
0x18003d1eb  mov     [rsp+378h+var_2A8], edi
0x18003d1f2  mov     [rsp+378h+var_2A0], rdi
0x18003d1fa  mov     [rsp+378h+var_298], 5
0x18003d205  mov     rax, [r14+40h]
0x18003d209  test    rax, rax
0x18003d20c  jz      short loc_18003D223
0x18003d20e  lea     rcx, [rsp+378h+var_2A8]
0x18003d216  call    cs:__guard_dispatch_icall_fptr
0x18003d21c  mov     ebx, eax
0x18003d21e  jmp     loc_18003D2A8
0x18003d223  mov     esi, edi
0x18003d225  mov     [rsp+378h+var_2E0], edi
0x18003d22c  mov     [rsp+378h+var_2D8], rdi
0x18003d234  lea     rax, [rsp+378h+var_2E0]
0x18003d23c  mov     [rsp+378h+var_328], rax
0x18003d241  mov     rdx, cs:?s_Empty@SString@@0PEAV1@EA; struct SString *
0x18003d248  lea     rcx, [rsp+378h+var_2A8]; this
0x18003d250  call    ?Append@StringArrayList@@QEAAXAEBVSString@@@Z; StringArrayList::Append(SString const &)
0x18003d255  nop
0x18003d256  jmp     short loc_18003D290
0x18003d258  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003d25c  xor     edi, edi
0x18003d25e  mov     ebx, dword ptr [rsp+378h+var_328]
0x18003d262  mov     r15, [rsp+378h+var_320]
0x18003d267  mov     esi, [rsp+378h+var_2E0]
0x18003d26e  mov     r14, [rsp+378h+var_2B8]
0x18003d276  mov     r13, [rsp+378h+var_2F8]
0x18003d27e  mov     [rsp+378h+Destination], r13
0x18003d283  mov     rax, [rsp+378h+var_2E8]
0x18003d28b  mov     [rsp+378h+var_310], rax
0x18003d290  test    sil, 2
0x18003d294  jz      short loc_18003D2A8
0x18003d296  mov     rax, cs:?g_fpHandleStackOverflowAfterCatch@@3P6AXXZEA; void (*g_fpHandleStackOverflowAfterCatch)(void)
0x18003d29d  test    rax, rax
0x18003d2a0  jz      short loc_18003D2A8
0x18003d2a2  call    cs:__guard_dispatch_icall_fptr
0x18003d2a8  mov     esi, 8007000Eh
0x18003d2ad  cmp     ebx, esi
0x18003d2af  jnz     short loc_18003D2C5
0x18003d2b1  lea     rcx, [rsp+378h+var_2A8]; this
0x18003d2b9  call    ??1StringArrayList@@QEAA@XZ; StringArrayList::~StringArrayList(void)
0x18003d2be  mov     eax, esi
0x18003d2c0  jmp     loc_18003D5BA
0x18003d2c5  mov     [rsp+378h+var_258], di
0x18003d2cd  mov     [rsp+378h+Source], di
0x18003d2d5  mov     [r13+206h], di
0x18003d2dd  lea     r9, [rsp+378h+var_258]; unsigned __int16 *
0x18003d2e5  lea     rdx, [rsp+378h+Source]; unsigned __int16 *
0x18003d2ed  mov     rcx, r13; unsigned __int16 *
0x18003d2f0  call    ?SplitPath@@YAXPEBGPEAGH1H1_K12@Z; SplitPath(ushort const *,ushort *,int,ushort *,int,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x18003d2f5  lea     rax, [rsp+378h+Source]
0x18003d2fd  mov     r8, r12
0x18003d300  inc     r8
0x18003d303  cmp     [rax+r8*2], di
0x18003d308  jnz     short loc_18003D300
0x18003d30a  mov     [rsp+378h+var_328], r8
0x18003d30f  lea     rax, [rsp+378h+var_258]
0x18003d317  inc     r12
0x18003d31a  cmp     [rax+r12*2], di
0x18003d31f  jnz     short loc_18003D317
0x18003d321  lea     rax, [r8+1]
0x18003d325  add     rax, r12
0x18003d328  add     rax, r15
0x18003d32b  mov     [rsp+378h+var_2E8], rax
0x18003d333  mov     r13d, edi
0x18003d336  cmp     [rsp+378h+var_2A8], edi
0x18003d33d  jbe     loc_18003D594
0x18003d343  mov     ecx, r13d
0x18003d346  lea     rsi, [rsp+378h+var_2A0]
0x18003d34e  mov     eax, [rsp+378h+var_298]
0x18003d355  cmp     r13d, eax
0x18003d358  jb      short loc_18003D366
0x18003d35a  sub     ecx, eax
0x18003d35c  mov     rsi, [rsi]
0x18003d35f  mov     eax, [rsi+8]
0x18003d362  cmp     ecx, eax
0x18003d364  jnb     short loc_18003D35A
0x18003d366  mov     eax, ecx
0x18003d368  mov     rsi, [rsi+rax*8+10h]
0x18003d36d  mov     eax, [rsi+8]
0x18003d370  test    al, 2
0x18003d372  jz      short loc_18003D39C
0x18003d374  and     eax, 7
0x18003d377  cmp     al, 7
0x18003d379  jnz     short loc_18003D383
0x18003d37b  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, edi; int SString::s_IsANSIMultibyte
0x18003d381  jz      short loc_18003D39C
0x18003d383  mov     rcx, rsi; this
0x18003d386  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18003d38b  test    eax, eax
0x18003d38d  jnz     short loc_18003D397
0x18003d38f  mov     rcx, rsi; this
0x18003d392  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003d397  mov     r8, [rsp+378h+var_328]
0x18003d39c  mov     ecx, [rsi+8]
0x18003d39f  not     ecx
0x18003d3a1  and     ecx, 1
0x18003d3a4  mov     eax, [rsi]
0x18003d3a6  shr     eax, cl
0x18003d3a8  dec     eax
0x18003d3aa  add     rax, [rsp+378h+var_2E8]
0x18003d3b2  cmp     rax, 104h
0x18003d3b8  ja      loc_18003D579
0x18003d3be  lea     rdx, [r8+1]; SizeInWords
0x18003d3c2  lea     r8, [rsp+378h+Source]; Source
0x18003d3ca  mov     rbx, [rsp+378h+Destination]
0x18003d3cf  mov     rcx, rbx; Destination
0x18003d3d2  call    cs:__imp_wcscpy_s
0x18003d3d8  mov     rax, [rsp+378h+var_328]
0x18003d3dd  lea     rbx, [rbx+rax*2]
0x18003d3e1  lea     rdx, [r12+1]; SizeInWords
0x18003d3e6  lea     r8, [rsp+378h+var_258]; Source
0x18003d3ee  mov     rcx, rbx; Destination
0x18003d3f1  call    cs:__imp_wcscpy_s
0x18003d3f7  lea     rbx, [rbx+r12*2]
0x18003d3fb  mov     [rsp+378h+var_320], rbx
0x18003d400  mov     edx, [rsi+8]
0x18003d403  mov     ecx, edx
0x18003d405  not     ecx
0x18003d407  and     ecx, 1
0x18003d40a  mov     eax, [rsi]
0x18003d40c  shr     eax, cl
0x18003d40e  cmp     eax, 1
0x18003d411  jz      loc_18003D513
0x18003d417  mov     rcx, rsi; this
0x18003d41a  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003d41f  mov     rax, [rsi+10h]
0x18003d423  mov     [rsp+378h+var_2F8], rax
0x18003d42b  mov     eax, [rsi+8]
0x18003d42e  mov     bl, 2
0x18003d430  test    bl, al
0x18003d432  jz      short loc_18003D457
0x18003d434  and     eax, 7
0x18003d437  cmp     al, 7
0x18003d439  jnz     short loc_18003D443
0x18003d43b  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, edi; int SString::s_IsANSIMultibyte
0x18003d441  jz      short loc_18003D457
0x18003d443  mov     rcx, rsi; this
0x18003d446  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18003d44b  test    eax, eax
0x18003d44d  jnz     short loc_18003D457
0x18003d44f  mov     rcx, rsi; this
0x18003d452  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003d457  mov     ecx, [rsi+8]
0x18003d45a  not     ecx
0x18003d45c  and     cl, 1
0x18003d45f  mov     edx, [rsi]
0x18003d461  shr     rdx, cl; SizeInWords
0x18003d464  mov     r8, [rsp+378h+var_2F8]; Source
0x18003d46c  mov     rcx, [rsp+378h+var_320]; Destination
0x18003d471  call    cs:__imp_wcscpy_s
0x18003d477  mov     eax, [rsi+8]
0x18003d47a  test    bl, al
0x18003d47c  jz      short loc_18003D4A1
0x18003d47e  and     eax, 7
0x18003d481  cmp     al, 7
0x18003d483  jnz     short loc_18003D48D
0x18003d485  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, edi; int SString::s_IsANSIMultibyte
0x18003d48b  jz      short loc_18003D4A1
0x18003d48d  mov     rcx, rsi; this
0x18003d490  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18003d495  test    eax, eax
0x18003d497  jnz     short loc_18003D4A1
0x18003d499  mov     rcx, rsi; this
0x18003d49c  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003d4a1  mov     ecx, [rsi+8]
0x18003d4a4  not     ecx
0x18003d4a6  and     ecx, 1
0x18003d4a9  mov     edx, [rsi]
0x18003d4ab  shr     edx, cl
0x18003d4ad  dec     edx
0x18003d4af  mov     rcx, [rsp+378h+var_320]
0x18003d4b4  lea     rcx, [rcx+rdx*2]; Destination
0x18003d4b8  lea     r8, asc_180049544; "\\"
0x18003d4bf  lea     rdx, [r15+1]; SizeInWords
0x18003d4c3  call    cs:__imp_wcscpy_s
0x18003d4c9  mov     eax, [rsi+8]
0x18003d4cc  test    bl, al
0x18003d4ce  jz      short loc_18003D4F3
0x18003d4d0  and     eax, 7
0x18003d4d3  cmp     al, 7
0x18003d4d5  jnz     short loc_18003D4DF
0x18003d4d7  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, edi; int SString::s_IsANSIMultibyte
0x18003d4dd  jz      short loc_18003D4F3
0x18003d4df  mov     rcx, rsi; this
0x18003d4e2  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18003d4e7  test    eax, eax
0x18003d4e9  jnz     short loc_18003D4F3
0x18003d4eb  mov     rcx, rsi; this
0x18003d4ee  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003d4f3  mov     ecx, [rsi+8]
0x18003d4f6  not     ecx
0x18003d4f8  and     ecx, 1
0x18003d4fb  mov     r8d, [rsi]
0x18003d4fe  shr     r8d, cl
0x18003d501  dec     r8d
0x18003d504  mov     rcx, [rsp+378h+var_320]
0x18003d509  lea     rcx, [rcx+r8*2]
0x18003d50d  add     rcx, 2
0x18003d511  jmp     short loc_18003D551
0x18003d513  test    dl, 2
0x18003d516  jz      short loc_18003D53C
0x18003d518  and     edx, 7
0x18003d51b  cmp     dl, 7
0x18003d51e  jnz     short loc_18003D528
0x18003d520  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, edi; int SString::s_IsANSIMultibyte
0x18003d526  jz      short loc_18003D53C
0x18003d528  mov     rcx, rsi; this
0x18003d52b  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18003d530  test    eax, eax
0x18003d532  jnz     short loc_18003D53C
0x18003d534  mov     rcx, rsi; this
0x18003d537  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003d53c  mov     ecx, [rsi+8]
0x18003d53f  not     ecx
0x18003d541  and     ecx, 1
0x18003d544  mov     r8d, [rsi]
0x18003d547  shr     r8d, cl
0x18003d54a  dec     r8d
0x18003d54d  lea     rcx, [rbx+r8*2]; Destination
0x18003d551  mov     r8, [r14+30h]; Source
0x18003d555  lea     rdx, [r15+1]; SizeInWords
0x18003d559  call    cs:__imp_wcscpy_s
0x18003d55f  mov     r8, [rsp+378h+Destination]; unsigned __int16 *
0x18003d564  mov     rdx, [rsp+378h+var_310]; HINSTANCE *
0x18003d569  mov     rcx, r14; this
0x18003d56c  call    ?LoadResourceFile@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEBG@Z; CCompRC::LoadResourceFile(HINSTANCE__ * *,ushort const *)
0x18003d571  mov     ebx, eax
0x18003d573  test    eax, eax
0x18003d575  jns     short loc_18003D5AB
0x18003d577  jmp     short loc_18003D57E
0x18003d579  mov     ebx, 80004005h
0x18003d57e  inc     r13d
0x18003d581  cmp     r13d, [rsp+378h+var_2A8]
0x18003d589  mov     r8, [rsp+378h+var_328]
0x18003d58e  jb      loc_18003D343
0x18003d594  test    ebx, ebx
0x18003d596  jns     short loc_18003D5AB
0x18003d598  mov     r8, [r14+30h]; unsigned __int16 *
0x18003d59c  mov     rdx, [rsp+378h+var_310]; HINSTANCE *
0x18003d5a1  mov     rcx, r14; this
0x18003d5a4  call    ?LoadResourceFile@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEBG@Z; CCompRC::LoadResourceFile(HINSTANCE__ * *,ushort const *)
0x18003d5a9  mov     ebx, eax
0x18003d5ab  lea     rcx, [rsp+378h+var_2A8]; this
0x18003d5b3  call    ??1StringArrayList@@QEAA@XZ; StringArrayList::~StringArrayList(void)
0x18003d5b8  mov     eax, ebx
0x18003d5ba  mov     rcx, [rsp+378h+var_48]
0x18003d5c2  xor     rcx, rsp; StackCookie
0x18003d5c5  call    __security_check_cookie
0x18003d5ca  add     rsp, 340h
0x18003d5d1  pop     r15
0x18003d5d3  pop     r14
0x18003d5d5  pop     r13
0x18003d5d7  pop     r12
0x18003d5d9  pop     rdi
0x18003d5da  pop     rsi
0x18003d5db  pop     rbx
0x18003d5dc  retn
```
