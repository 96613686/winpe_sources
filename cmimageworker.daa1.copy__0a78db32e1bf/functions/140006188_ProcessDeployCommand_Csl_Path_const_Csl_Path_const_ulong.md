# ProcessDeployCommand(Csl::Path const &,Csl::Path const &,ulong)

- ea: `0x140006188`
- end: `0x1400066da`
- name: `?ProcessDeployCommand@@YAJAEBVPath@Csl@@0K@Z`
- size: `1362`
- prototype: `__int64 __fastcall(const unsigned __int16 **, const unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400094c8`

## callees

- `0x1400020b0`
- `0x140002344`
- `0x1400038bc`
- `0x140003b30`
- `0x1400046d4`
- `0x140006188`
- `0x140006fc4`
- `0x140006fe4`
- `0x140007a84`
- `0x140007d1c`
- `0x140008f90`
- `0x14000a9b8`
- `0x14000aa8c`
- `0x14000ad64`
- `0x14000bc44`
- `0x14000cd84`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x14000641f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x14000641f`
- `wcimage!WcProcessContainerLayer` at `0x14000661e`
- `wcimage!WcProcessContainerLayer` at `0x14000661e`
- `wcimage!WcExpandContainerWim` at `0x1400061f6`
- `wcimage!WcExpandContainerWim` at `0x1400061f6`
- `ntdll!RtlDoesFileExists_U` at `0x1400062cf`
- `ntdll!RtlDoesFileExists_U` at `0x1400065f8`
- `ntdll!RtlDoesFileExists_U` at `0x1400062cf`
- `ntdll!RtlDoesFileExists_U` at `0x1400065f8`

## pseudocode

```c
__int64 __fastcall ProcessDeployCommand(const unsigned __int16 **a1, const unsigned __int16 **a2, unsigned int a3)
{
  const unsigned __int16 *v6; // rbx
  const unsigned __int16 *v7; // rdi
  int v8; // eax
  unsigned int LastError; // ebx
  __int64 v10; // rdx
  WCHAR *v11; // rcx
  int DirectoryRecursive; // eax
  const struct Path *v13; // rdx
  struct _SECURITY_ATTRIBUTES *v14; // r8
  __int64 v15; // rdx
  LPCWSTR *i; // rbx
  const char *v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rdx
  int v20; // eax
  int v22; // [rsp+20h] [rbp-E0h]
  PCWSTR FileName; // [rsp+30h] [rbp-D0h] BYREF
  _WORD *v24; // [rsp+38h] [rbp-C8h]
  _WORD v25[8]; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  void *v28; // [rsp+60h] [rbp-A0h] BYREF
  char *v29; // [rsp+68h] [rbp-98h]
  _WORD v30[8]; // [rsp+70h] [rbp-90h] BYREF
  __m128i si128; // [rsp+80h] [rbp-80h] BYREF
  __int64 v32; // [rsp+90h] [rbp-70h]
  LPCWSTR lpNewFileName[2]; // [rsp+98h] [rbp-68h] BYREF
  _WORD v34[8]; // [rsp+A8h] [rbp-58h] BYREF
  PCWSTR v35[2]; // [rsp+B8h] [rbp-48h] BYREF
  _WORD v36[12]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v37[42]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v6 = *a2;
  v7 = *a1;
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v37,
    "Deploy");
  v37[0] = &WorkerEtwProvider::Deploy::`vftable';
  WorkerEtwProvider::Deploy::StartActivity((WorkerEtwProvider::Deploy *)v37, v7, v6);
  v8 = WcExpandContainerWim(*a2, a3, *a1);
  LastError = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\exe\\main.cpp",
      (const char *)(unsigned int)v8,
      v22);
    goto LABEL_60;
  }
  FileName = v25;
  v24 = v25;
  v25[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &FileName,
                           *a1,
                           a1[1] - *a1) )
  {
    v10 = 149;
    goto LABEL_5;
  }
  v26 = L"Files";
  v27 = 5;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)&FileName) )
  {
    v10 = 150;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\exe\\main.cpp",
      (const char *)0x8007000ELL,
      v22);
    v11 = (WCHAR *)FileName;
    if ( FileName != v25 )
      goto LABEL_42;
    goto LABEL_43;
  }
  if ( !RtlDoesFileExists_U(FileName) )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v32 = -1;
    DirectoryRecursive = Csl::EnumerateDirectory(a1, 1, &si128);
    LastError = DirectoryRecursive;
    if ( DirectoryRecursive < 0 )
    {
      v15 = 162;
      goto LABEL_12;
    }
    DirectoryRecursive = Csl::CreateDirectoryRecursive((Csl *)&FileName, v13, v14);
    LastError = DirectoryRecursive;
    if ( DirectoryRecursive < 0 )
    {
      v15 = 165;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\exe\\main.cpp",
        (const char *)(unsigned int)DirectoryRecursive,
        v22);
LABEL_13:
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&si128);
      goto LABEL_14;
    }
    for ( i = (LPCWSTR *)si128.m128i_i64[0]; ; i += 4 )
    {
      if ( i == (LPCWSTR *)si128.m128i_i64[1] )
      {
        utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&si128);
        goto LABEL_45;
      }
      v28 = v30;
      v29 = (char *)v30;
      v30[0] = 0;
      if ( !(unsigned __int8)Csl::Path::GetFileName(i, &v28) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAB,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\exe\\main.cpp",
          (const char *)0x8007000ELL,
          v22);
        goto LABEL_38;
      }
      lpNewFileName[0] = v34;
      lpNewFileName[1] = v34;
      v34[0] = 0;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               lpNewFileName,
                               FileName,
                               v24 - FileName) )
        break;
      v26 = (const wchar_t *)v28;
      v27 = (v29 - (_BYTE *)v28) >> 1;
      if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)lpNewFileName) )
      {
        v18 = 175;
        goto LABEL_34;
      }
      if ( !MoveFileW(*i, lpNewFileName[0]) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xB2,
                      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\exe\\main.cpp",
                      v17);
        if ( lpNewFileName[0] != v34 )
          operator delete((void *)lpNewFileName[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v28 != v30 )
          operator delete(v28, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_13;
      }
      if ( lpNewFileName[0] != v34 )
        operator delete((void *)lpNewFileName[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v28 != v30 )
        operator delete(v28, (const struct std::nothrow_t *)&std::nothrow);
    }
    v18 = 174;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\exe\\main.cpp",
      (const char *)0x8007000ELL,
      v22);
    if ( lpNewFileName[0] != v34 )
      operator delete((void *)lpNewFileName[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_38:
    if ( v28 != v30 )
      operator delete(v28, (const struct std::nothrow_t *)&std::nothrow);
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&si128);
LABEL_41:
    v11 = (WCHAR *)FileName;
    if ( FileName != v25 )
LABEL_42:
      operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
LABEL_43:
    LastError = -2147024882;
    goto LABEL_60;
  }
LABEL_45:
  v35[0] = v36;
  v35[1] = v36;
  v36[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v35,
                           FileName,
                           v24 - FileName) )
  {
    v19 = 183;
    goto LABEL_49;
  }
  v26 = L"ContainerImage.def";
  v27 = 18;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v35) )
  {
    v19 = 184;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\exe\\main.cpp",
      (const char *)0x8007000ELL,
      v22);
    if ( v35[0] != v36 )
      operator delete((void *)v35[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_41;
  }
  if ( RtlDoesFileExists_U(v35[0]) )
  {
    v20 = WcProcessContainerLayer(FileName, 0, 1, 0);
    LastError = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimageworker\\exe\\main.cpp",
        (const char *)(unsigned int)v20,
        0);
      if ( v35[0] != v36 )
        operator delete((void *)v35[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_14:
      if ( FileName != v25 )
        operator delete((void *)FileName, (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_60;
    }
  }
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v37);
  if ( v35[0] != v36 )
    operator delete((void *)v35[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( FileName != v25 )
    operator delete((void *)FileName, (const struct std::nothrow_t *)&std::nothrow);
  LastError = 0;
LABEL_60:
  v37[0] = &WorkerEtwProvider::Deploy::`vftable';
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v37);
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v37);
  return LastError;
}

```

## disassembly

```asm
0x140006188  push    rbp
0x14000618a  push    rbx
0x14000618b  push    rsi
0x14000618c  push    rdi
0x14000618d  push    r12
0x14000618f  push    r14
0x140006191  push    r15
0x140006193  lea     rbp, [rsp-140h]
0x14000619b  sub     rsp, 240h
0x1400061a2  mov     rax, cs:__security_cookie
0x1400061a9  xor     rax, rsp
0x1400061ac  mov     [rbp+170h+var_40], rax
0x1400061b3  mov     r14d, r8d
0x1400061b6  mov     rsi, rdx
0x1400061b9  mov     r15, rcx
0x1400061bc  mov     rbx, [rdx]
0x1400061bf  mov     rdi, [rcx]
0x1400061c2  lea     rdx, aDeploy_0; "Deploy"
0x1400061c9  lea     rcx, [rbp+170h+var_190]
0x1400061cd  call    ??0?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400061d2  lea     r12, ??_7Deploy@WorkerEtwProvider@@6B@; const WorkerEtwProvider::Deploy::`vftable'
0x1400061d9  mov     [rbp+170h+var_190], r12
0x1400061dd  mov     r8, rbx; unsigned __int16 *
0x1400061e0  mov     rdx, rdi; unsigned __int16 *
0x1400061e3  lea     rcx, [rbp+170h+var_190]; this
0x1400061e7  call    ?StartActivity@Deploy@WorkerEtwProvider@@QEAAXPEBG0@Z; WorkerEtwProvider::Deploy::StartActivity(ushort const *,ushort const *)
0x1400061ec  nop
0x1400061ed  mov     r8, [r15]
0x1400061f0  mov     edx, r14d
0x1400061f3  mov     rcx, [rsi]
0x1400061f6  call    cs:__imp_WcExpandContainerWim
0x1400061fd  nop     dword ptr [rax+rax+00h]
0x140006202  mov     ebx, eax
0x140006204  test    eax, eax
0x140006206  jns     short loc_140006228
0x140006208  mov     rcx, [rbp+178h]; this
0x14000620f  mov     r9d, eax; char *
0x140006212  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140006219  mov     edx, 92h; void *
0x14000621e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006223  jmp     loc_1400066A0
0x140006228  lea     rax, [rsp+270h+var_230]
0x14000622d  mov     [rsp+270h+FileName], rax
0x140006232  lea     rax, [rsp+270h+var_230]
0x140006237  mov     [rsp+270h+var_238], rax
0x14000623c  xor     eax, eax
0x14000623e  mov     [rsp+270h+var_230], ax
0x140006243  mov     r8, [r15+8]
0x140006247  sub     r8, [r15]
0x14000624a  sar     r8, 1
0x14000624d  mov     rdx, [r15]
0x140006250  lea     rcx, [rsp+270h+FileName]
0x140006255  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14000625a  test    al, al
0x14000625c  jnz     short loc_14000629B
0x14000625e  mov     edx, 95h; void *
0x140006263  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14000626a  mov     r9d, 8007000Eh; char *
0x140006270  mov     rcx, [rbp+178h]; this
0x140006277  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000627c  mov     rcx, [rsp+270h+FileName]
0x140006281  lea     rax, [rsp+270h+var_230]
0x140006286  cmp     rcx, rax
0x140006289  jz      loc_140006544
0x14000628f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140006296  jmp     loc_14000653F
0x14000629b  lea     rax, aFiles; "Files"
0x1400062a2  mov     [rsp+270h+var_220], rax
0x1400062a7  mov     [rsp+270h+var_218], 5
0x1400062b0  lea     rdx, [rsp+270h+var_220]
0x1400062b5  lea     rcx, [rsp+270h+FileName]; this
0x1400062ba  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1400062bf  test    al, al
0x1400062c1  jnz     short loc_1400062CA
0x1400062c3  mov     edx, 96h
0x1400062c8  jmp     short loc_140006263
0x1400062ca  mov     rcx, [rsp+270h+FileName]; FileName
0x1400062cf  call    cs:__imp_RtlDoesFileExists_U
0x1400062d6  nop     dword ptr [rax+rax+00h]
0x1400062db  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1400062e2  mov     esi, 1
0x1400062e7  test    al, al
0x1400062e9  jnz     loc_140006557
0x1400062ef  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400062f7  movdqu  [rbp+170h+var_1F0], xmm0
0x1400062fc  mov     [rbp+170h+var_1E0], 0FFFFFFFFFFFFFFFFh
0x140006304  lea     r8, [rbp+170h+var_1F0]
0x140006308  mov     edx, esi
0x14000630a  mov     rcx, r15
0x14000630d  call    ?EnumerateDirectory@Csl@@YAJAEBVPath@1@W4EnumerateDirectoryOption@1@AEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@PEBG@Z; Csl::EnumerateDirectory(Csl::Path const &,Csl::EnumerateDirectoryOption,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &,ushort const *)
0x140006312  mov     ebx, eax
0x140006314  test    eax, eax
0x140006316  jns     short loc_14000635C
0x140006318  mov     edx, 0A2h; void *
0x14000631d  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140006324  mov     r9d, eax; char *
0x140006327  mov     rcx, [rbp+178h]; this
0x14000632e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006333  lea     rcx, [rbp+170h+var_1F0]
0x140006337  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14000633c  mov     rcx, [rsp+270h+FileName]; void *
0x140006341  lea     rax, [rsp+270h+var_230]
0x140006346  cmp     rcx, rax
0x140006349  jz      loc_1400066A0
0x14000634f  mov     rdx, rdi; struct std::nothrow_t *
0x140006352  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006357  jmp     loc_1400066A0
0x14000635c  lea     rcx, [rsp+270h+FileName]; this
0x140006361  call    ?CreateDirectoryRecursive@Csl@@YAJAEBVPath@1@PEAU_SECURITY_ATTRIBUTES@@@Z; Csl::CreateDirectoryRecursive(Csl::Path const &,_SECURITY_ATTRIBUTES *)
0x140006366  mov     ebx, eax
0x140006368  test    eax, eax
0x14000636a  jns     short loc_140006373
0x14000636c  mov     edx, 0A5h
0x140006371  jmp     short loc_14000631D
0x140006373  mov     rbx, qword ptr [rbp+170h+var_1F0]
0x140006377  cmp     rbx, qword ptr [rbp+170h+var_1F0+8]
0x14000637b  jz      loc_14000654E
0x140006381  lea     rax, [rsp+270h+var_200]
0x140006386  mov     [rsp+270h+var_210], rax
0x14000638b  lea     rax, [rsp+270h+var_200]
0x140006390  mov     [rsp+270h+var_208], rax
0x140006395  xor     eax, eax
0x140006397  mov     [rsp+270h+var_200], ax
0x14000639c  lea     rdx, [rsp+270h+var_210]
0x1400063a1  mov     rcx, rbx
0x1400063a4  call    ?GetFileName@Path@Csl@@QEBA_NAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::Path::GetFileName(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1400063a9  test    al, al
0x1400063ab  jz      loc_1400064EF
0x1400063b1  lea     rax, [rbp+170h+var_1C8]
0x1400063b5  mov     [rbp+170h+lpNewFileName], rax
0x1400063b9  lea     rax, [rbp+170h+var_1C8]
0x1400063bd  mov     [rbp+170h+var_1D0], rax
0x1400063c1  xor     eax, eax
0x1400063c3  mov     [rbp+170h+var_1C8], ax
0x1400063c7  mov     rdx, [rsp+270h+FileName]
0x1400063cc  mov     r8, [rsp+270h+var_238]
0x1400063d1  sub     r8, rdx
0x1400063d4  sar     r8, 1
0x1400063d7  lea     rcx, [rbp+170h+lpNewFileName]
0x1400063db  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1400063e0  test    al, al
0x1400063e2  jz      loc_1400064E8
0x1400063e8  mov     rax, [rsp+270h+var_210]
0x1400063ed  mov     [rsp+270h+var_220], rax
0x1400063f2  mov     rcx, [rsp+270h+var_208]
0x1400063f7  sub     rcx, rax
0x1400063fa  sar     rcx, 1
0x1400063fd  mov     [rsp+270h+var_218], rcx
0x140006402  lea     rdx, [rsp+270h+var_220]
0x140006407  lea     rcx, [rbp+170h+lpNewFileName]; this
0x14000640b  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140006410  test    al, al
0x140006412  jz      loc_1400064B3
0x140006418  mov     rdx, [rbp+170h+lpNewFileName]; lpNewFileName
0x14000641c  mov     rcx, [rbx]; lpExistingFileName
0x14000641f  call    cs:__imp_MoveFileW
0x140006426  nop     dword ptr [rax+rax+00h]
0x14000642b  test    eax, eax
0x14000642d  jz      short loc_140006464
0x14000642f  mov     rcx, [rbp+170h+lpNewFileName]; void *
0x140006433  lea     rax, [rbp+170h+var_1C8]
0x140006437  cmp     rcx, rax
0x14000643a  jz      short loc_140006444
0x14000643c  mov     rdx, rdi; struct std::nothrow_t *
0x14000643f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006444  lea     rax, [rsp+270h+var_200]
0x140006449  mov     rcx, [rsp+270h+var_210]; void *
0x14000644e  cmp     rcx, rax
0x140006451  jz      short loc_14000645B
0x140006453  mov     rdx, rdi; struct std::nothrow_t *
0x140006456  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000645b  add     rbx, 20h ; ' '
0x14000645f  jmp     loc_140006377
0x140006464  mov     rcx, [rbp+178h]; this
0x14000646b  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140006472  mov     edx, 0B2h; void *
0x140006477  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000647c  mov     ebx, eax
0x14000647e  mov     rcx, [rbp+170h+lpNewFileName]; void *
0x140006482  lea     rax, [rbp+170h+var_1C8]
0x140006486  cmp     rcx, rax
0x140006489  jz      short loc_140006493
0x14000648b  mov     rdx, rdi; struct std::nothrow_t *
0x14000648e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006493  lea     rax, [rsp+270h+var_200]
0x140006498  mov     rcx, [rsp+270h+var_210]; void *
0x14000649d  cmp     rcx, rax
0x1400064a0  jz      loc_140006333
0x1400064a6  mov     rdx, rdi; struct std::nothrow_t *
0x1400064a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400064ae  jmp     loc_140006333
0x1400064b3  mov     edx, 0AFh; void *
0x1400064b8  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1400064bf  mov     r9d, 8007000Eh; char *
0x1400064c5  mov     rcx, [rbp+178h]; this
0x1400064cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400064d1  mov     rcx, [rbp+170h+lpNewFileName]; void *
0x1400064d5  lea     rax, [rbp+170h+var_1C8]
0x1400064d9  cmp     rcx, rax
0x1400064dc  jz      short loc_14000650D
0x1400064de  mov     rdx, rdi; struct std::nothrow_t *
0x1400064e1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400064e6  jmp     short loc_14000650D
0x1400064e8  mov     edx, 0AEh
0x1400064ed  jmp     short loc_1400064B8
0x1400064ef  mov     rcx, [rbp+178h]; this
0x1400064f6  mov     r9d, 8007000Eh; char *
0x1400064fc  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140006503  mov     edx, 0ABh; void *
0x140006508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000650d  lea     rax, [rsp+270h+var_200]
0x140006512  mov     rcx, [rsp+270h+var_210]; void *
0x140006517  cmp     rcx, rax
0x14000651a  jz      short loc_140006524
0x14000651c  mov     rdx, rdi; struct std::nothrow_t *
0x14000651f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006524  lea     rcx, [rbp+170h+var_1F0]
0x140006528  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14000652d  lea     rax, [rsp+270h+var_230]
0x140006532  mov     rcx, [rsp+270h+FileName]; void *
0x140006537  cmp     rcx, rax
0x14000653a  jz      short loc_140006544
0x14000653c  mov     rdx, rdi; struct std::nothrow_t *
0x14000653f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006544  mov     ebx, 8007000Eh
0x140006549  jmp     loc_1400066A0
0x14000654e  lea     rcx, [rbp+170h+var_1F0]
0x140006552  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x140006557  lea     rax, [rbp+170h+var_1A8]
0x14000655b  mov     [rbp+170h+var_1B8], rax
0x14000655f  lea     rax, [rbp+170h+var_1A8]
0x140006563  mov     [rbp+170h+var_1B0], rax
0x140006567  xor     eax, eax
0x140006569  mov     [rbp+170h+var_1A8], ax
0x14000656d  mov     rdx, [rsp+270h+FileName]
0x140006572  mov     r8, [rsp+270h+var_238]
0x140006577  sub     r8, rdx
0x14000657a  sar     r8, 1
0x14000657d  lea     rcx, [rbp+170h+var_1B8]
0x140006581  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140006586  test    al, al
0x140006588  jnz     short loc_140006591
0x14000658a  mov     edx, 0B7h
0x14000658f  jmp     short loc_1400065BD
0x140006591  lea     rax, aContainerimage; "ContainerImage.def"
0x140006598  mov     [rsp+270h+var_220], rax
0x14000659d  mov     [rsp+270h+var_218], 12h
0x1400065a6  lea     rdx, [rsp+270h+var_220]
0x1400065ab  lea     rcx, [rbp+170h+var_1B8]; this
0x1400065af  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1400065b4  test    al, al
0x1400065b6  jnz     short loc_1400065F4
0x1400065b8  mov     edx, 0B8h; void *
0x1400065bd  mov     r9d, 8007000Eh; char *
0x1400065c3  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1400065ca  mov     rcx, [rbp+178h]; this
0x1400065d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400065d6  lea     rax, [rbp+170h+var_1A8]
0x1400065da  mov     rcx, [rbp+170h+var_1B8]; void *
0x1400065de  cmp     rcx, rax
0x1400065e1  jz      loc_14000652D
0x1400065e7  mov     rdx, rdi; struct std::nothrow_t *
0x1400065ea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400065ef  jmp     loc_14000652D
0x1400065f4  mov     rcx, [rbp+170h+var_1B8]; FileName
0x1400065f8  call    cs:__imp_RtlDoesFileExists_U
0x1400065ff  nop     dword ptr [rax+rax+00h]
0x140006604  test    al, al
0x140006606  jz      short loc_140006669
0x140006608  mov     qword ptr [rsp+270h+var_250], 0; int
0x140006611  xor     r9d, r9d
0x140006614  mov     r8d, esi
0x140006617  xor     edx, edx
0x140006619  mov     rcx, [rsp+270h+FileName]
0x14000661e  call    cs:__imp_WcProcessContainerLayer
0x140006625  nop     dword ptr [rax+rax+00h]
0x14000662a  mov     ebx, eax
0x14000662c  test    eax, eax
0x14000662e  jns     short loc_140006669
0x140006630  mov     rcx, [rbp+178h]; this
0x140006637  mov     r9d, eax; char *
0x14000663a  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140006641  mov     edx, 0C1h; void *
0x140006646  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000664b  mov     rcx, [rbp+170h+var_1B8]; void *
0x14000664f  lea     rax, [rbp+170h+var_1A8]
0x140006653  cmp     rcx, rax
0x140006656  jz      loc_14000633C
0x14000665c  mov     rdx, rdi; struct std::nothrow_t *
0x14000665f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006664  jmp     loc_14000633C
0x140006669  lea     rcx, [rbp+170h+var_190]
0x14000666d  call    ?Stop@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140006672  mov     rcx, [rbp+170h+var_1B8]; void *
0x140006676  lea     rax, [rbp+170h+var_1A8]
0x14000667a  cmp     rcx, rax
0x14000667d  jz      short loc_140006687
0x14000667f  mov     rdx, rdi; struct std::nothrow_t *
0x140006682  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006687  mov     rcx, [rsp+270h+FileName]; void *
  ... truncated ...
```
