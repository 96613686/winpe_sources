# Cabinet::Extract_Internal(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,CabContext *,_CABCALLBACKS * const)

- ea: `0x18000a09c`
- end: `0x18000a3f7`
- name: `?Extract_Internal@Cabinet@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVCabContext@@QEAU_CABCALLBACKS@@@Z`
- size: `859`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009c20`
- `0x18000a028`

## callees

- `0x180001540`
- `0x180003648`
- `0x18000553c`
- `0x1800082b8`
- `0x18000a09c`
- `0x18000b4c0`
- `0x18000b658`

## import_xrefs

- `Cabinet!__imp_FDICreate` at `0x18000a207`
- `Cabinet!__imp_FDICreate` at `0x18000a207`
- `Cabinet!__imp_FDICopy` at `0x18000a2a7`
- `Cabinet!__imp_FDICopy` at `0x18000a2a7`
- `Cabinet!__imp_FDIDestroy` at `0x18000a1a5`
- `Cabinet!__imp_FDIDestroy` at `0x18000a26d`
- `Cabinet!__imp_FDIDestroy` at `0x18000a312`
- `Cabinet!__imp_FDIDestroy` at `0x18000a3a6`
- `Cabinet!__imp_FDIDestroy` at `0x18000a3d0`
- `Cabinet!__imp_FDIDestroy` at `0x18000a1a5`
- `Cabinet!__imp_FDIDestroy` at `0x18000a26d`
- `Cabinet!__imp_FDIDestroy` at `0x18000a312`
- `Cabinet!__imp_FDIDestroy` at `0x18000a3a6`
- `Cabinet!__imp_FDIDestroy` at `0x18000a3d0`

## pseudocode

```c
__int64 __fastcall Cabinet::Extract_Internal(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v8; // esi
  __int64 v9; // rdx
  HFDI v10; // rcx
  CHAR *v11; // rdx
  int v12; // edi
  __int64 *v13; // rax
  __int64 **v14; // rdx
  __int64 *i; // rcx
  __int64 *j; // rdx
  int pfnwrite; // [rsp+28h] [rbp-59h]
  int pfnwritea; // [rsp+28h] [rbp-59h]
  int pfnwriteb; // [rsp+28h] [rbp-59h]
  HFDI hfdi; // [rsp+68h] [rbp-19h]
  LPSTR pszCabinet[2]; // [rsp+70h] [rbp-11h] BYREF
  __m128i v22; // [rsp+80h] [rbp-1h]
  ERF perf; // [rsp+90h] [rbp+Fh] BYREF
  WCHAR WideCharStr[8]; // [rsp+A0h] [rbp+1Fh] BYREF
  __m128i si128; // [rsp+B0h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  if ( !*(_QWORD *)(a1 + 16) )
  {
    v5 = -2147024809;
    v6 = 157;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)v5,
      pfnwrite);
    return v5;
  }
  if ( !a2 )
  {
    v5 = -2147467261;
    v6 = 158;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v5 = -2147467261;
    v6 = 159;
    goto LABEL_3;
  }
  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  *(_OWORD *)WideCharStr = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  WideCharStr[0] = 0;
  *(_OWORD *)pszCabinet = 0;
  v22 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(pszCabinet[0]) = 0;
  v8 = Utils::ConvertPointerToString(a2, (__int64)WideCharStr);
  if ( v8 < 0 )
  {
    v9 = 167;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)(unsigned int)v8,
      pfnwrite);
    std::string::~string(pszCabinet);
    std::wstring::~wstring((char **)WideCharStr);
    return (unsigned int)v8;
  }
  v8 = Utils::ConvertUnicodeToMultiByte(WideCharStr, pszCabinet);
  if ( v8 < 0 )
  {
    v9 = 169;
    goto LABEL_11;
  }
  v10 = FDICreate(
          *(PFNALLOC *)a3,
          *(PFNFREE *)(a3 + 8),
          *(PFNOPEN *)(a3 + 16),
          *(PFNREAD *)(a3 + 24),
          *(PFNWRITE *)(a3 + 32),
          *(PFNCLOSE *)(a3 + 40),
          *(PFNSEEK *)(a3 + 48),
          -1,
          &perf);
  hfdi = v10;
  if ( !v10 )
  {
    if ( (unsigned int)(perf.erfOper - 1) > 0xA )
    {
      v5 = -2145877265;
    }
    else
    {
      v5 = perf.erfOper - 2145877280;
      if ( perf.erfOper - 2145877280 >= 0 )
        goto LABEL_20;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)v5,
      pfnwritea);
LABEL_20:
    std::string::~string(pszCabinet);
    std::wstring::~wstring((char **)WideCharStr);
    if ( hfdi )
      FDIDestroy(hfdi);
    return v5;
  }
  v11 = (CHAR *)pszCabinet;
  if ( v22.m128i_i64[1] > 0xFuLL )
    v11 = pszCabinet[0];
  if ( FDICopy(v10, v11, (LPSTR)&pszCabPath, 0, *(PFNFDINOTIFY *)(a3 + 56), 0, (void *)a2) )
    goto LABEL_32;
  if ( (unsigned int)(perf.erfOper - 1) > 0xA )
  {
    v5 = -2145877265;
    goto LABEL_20;
  }
  v5 = perf.erfOper - 2145877280;
  if ( perf.erfOper != 11 )
  {
    if ( (v5 & 0x80000000) != 0 )
      goto LABEL_20;
LABEL_32:
    v13 = **(__int64 ***)(a2 + 16);
    while ( !*((_BYTE *)v13 + 25) )
    {
      if ( !*((_DWORD *)v13 + 16) )
      {
        std::string::~string(pszCabinet);
        std::wstring::~wstring((char **)WideCharStr);
        if ( hfdi )
          FDIDestroy(hfdi);
        return 2149089986LL;
      }
      v14 = (__int64 **)v13[2];
      if ( *((_BYTE *)v14 + 25) )
      {
        for ( i = (__int64 *)v13[1]; !*((_BYTE *)i + 25) && v13 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v13 = i;
        v13 = i;
      }
      else
      {
        v13 = (__int64 *)v13[2];
        for ( j = *v14; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v13 = j;
      }
    }
    std::string::~string(pszCabinet);
    std::wstring::~wstring((char **)WideCharStr);
    if ( hfdi )
      FDIDestroy(hfdi);
    return 0;
  }
  v12 = *(_DWORD *)(a2 + 160);
  if ( v12 >= 0 )
    goto LABEL_20;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC6,
    (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
    (const char *)(unsigned int)v12,
    pfnwriteb);
  std::string::~string(pszCabinet);
  std::wstring::~wstring((char **)WideCharStr);
  if ( hfdi )
    FDIDestroy(hfdi);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000a09c  mov     rax, rsp
0x18000a09f  push    rbp
0x18000a0a0  push    rsi
0x18000a0a1  push    rdi
0x18000a0a2  lea     rbp, [rax-5Fh]
0x18000a0a6  sub     rsp, 0C0h
0x18000a0ad  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x18000a0b5  mov     [rax+8], rbx
0x18000a0b9  mov     rax, cs:__security_cookie
0x18000a0c0  xor     rax, rsp
0x18000a0c3  mov     [rbp+57h+var_18], rax
0x18000a0c7  mov     rbx, r8
0x18000a0ca  mov     rdi, rdx
0x18000a0cd  cmp     qword ptr [rcx+10h], 0
0x18000a0d2  jnz     short loc_18000A0F8
0x18000a0d4  mov     ebx, 80070057h
0x18000a0d9  mov     edx, 9Dh; void *
0x18000a0de  mov     rcx, [rbp+5Fh]; this
0x18000a0e2  mov     r9d, ebx; char *
0x18000a0e5  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000a0ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a0f1  mov     eax, ebx
0x18000a0f3  jmp     loc_18000A3D8
0x18000a0f8  test    rdi, rdi
0x18000a0fb  jnz     short loc_18000A109
0x18000a0fd  mov     ebx, 80004003h
0x18000a102  mov     edx, 9Eh
0x18000a107  jmp     short loc_18000A0DE
0x18000a109  test    rbx, rbx
0x18000a10c  jnz     short loc_18000A11A
0x18000a10e  mov     ebx, 80004003h
0x18000a113  mov     edx, 9Fh
0x18000a118  jmp     short loc_18000A0DE
0x18000a11a  xor     eax, eax
0x18000a11c  mov     qword ptr [rbp+57h+perf.erfOper], rax
0x18000a120  mov     [rbp+57h+perf.fError], eax
0x18000a123  mov     [rbp+57h+hfdi], rax
0x18000a127  lea     rax, [rbp+57h+hfdi]
0x18000a12b  mov     [rbp+57h+var_78], rax
0x18000a12f  xorps   xmm0, xmm0
0x18000a132  movups  xmmword ptr [rbp+57h+WideCharStr], xmm0
0x18000a136  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000a13e  movdqu  [rbp+57h+var_28], xmm1
0x18000a143  xor     eax, eax
0x18000a145  mov     [rbp+57h+WideCharStr], ax
0x18000a149  movups  xmmword ptr [rbp+57h+pszCabinet], xmm0
0x18000a14d  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18000a155  movdqu  [rbp+57h+var_58], xmm1
0x18000a15a  mov     byte ptr [rbp+57h+pszCabinet], al
0x18000a15d  lea     rdx, [rbp+57h+WideCharStr]
0x18000a161  mov     rcx, rdi
0x18000a164  call    ?ConvertPointerToString@Utils@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Utils::ConvertPointerToString(void *,std::wstring *)
0x18000a169  mov     esi, eax
0x18000a16b  test    eax, eax
0x18000a16d  jns     short loc_18000A1B2
0x18000a16f  mov     edx, 0A7h; void *
0x18000a174  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000a17b  mov     r9d, esi; char *
0x18000a17e  mov     rcx, [rbp+5Fh]; this
0x18000a182  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a187  nop
0x18000a188  lea     rcx, [rbp+57h+pszCabinet]
0x18000a18c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000a191  nop
0x18000a192  lea     rcx, [rbp+57h+WideCharStr]
0x18000a196  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a19b  nop
0x18000a19c  mov     rcx, [rbp+57h+hfdi]; hfdi
0x18000a1a0  test    rcx, rcx
0x18000a1a3  jz      short loc_18000A1AB
0x18000a1a5  call    cs:__imp_FDIDestroy
0x18000a1ab  mov     eax, esi
0x18000a1ad  jmp     loc_18000A3D8
0x18000a1b2  lea     rdx, [rbp+57h+pszCabinet]; void *
0x18000a1b6  lea     rcx, [rbp+57h+WideCharStr]; lpWideCharStr
0x18000a1ba  call    ?ConvertUnicodeToMultiByte@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; Utils::ConvertUnicodeToMultiByte(std::wstring const &,std::string *)
0x18000a1bf  mov     esi, eax
0x18000a1c1  test    eax, eax
0x18000a1c3  jns     short loc_18000A1CC
0x18000a1c5  mov     edx, 0A9h
0x18000a1ca  jmp     short loc_18000A174
0x18000a1cc  lea     rax, [rbp+57h+perf]
0x18000a1d0  mov     [rsp+40h], rax; perf
0x18000a1d5  mov     [rsp+0D0h+cpuType], 0FFFFFFFFh; cpuType
0x18000a1dd  mov     rax, [rbx+30h]
0x18000a1e1  mov     [rsp+0D0h+pfnseek], rax; pfnseek
0x18000a1e6  mov     rax, [rbx+28h]
0x18000a1ea  mov     [rsp+0D0h+pfnclose], rax; pfnclose
0x18000a1ef  mov     rax, [rbx+20h]
0x18000a1f3  mov     [rsp+0D0h+pfnwrite], rax; int
0x18000a1f8  mov     r9, [rbx+18h]; pfnread
0x18000a1fc  mov     r8, [rbx+10h]; pfnopen
0x18000a200  mov     rdx, [rbx+8]; pfnfree
0x18000a204  mov     rcx, [rbx]; pfnalloc
0x18000a207  call    cs:__imp_FDICreate
0x18000a20d  mov     rcx, rax; hfdi
0x18000a210  mov     [rbp+57h+hfdi], rax
0x18000a214  test    rax, rax
0x18000a217  jnz     short loc_18000A278
0x18000a219  mov     ebx, [rbp+57h+perf.erfOper]
0x18000a21c  lea     eax, [rbx-1]
0x18000a21f  cmp     eax, 0Ah
0x18000a222  ja      short loc_18000A22E
0x18000a224  add     ebx, 801882E0h
0x18000a22a  jns     short loc_18000A24C
0x18000a22c  jmp     short loc_18000A233
0x18000a22e  mov     ebx, 801882EFh
0x18000a233  mov     rcx, [rbp+5Fh]; this
0x18000a237  mov     r9d, ebx; char *
0x18000a23a  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000a241  mov     edx, 0B6h; void *
0x18000a246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a24b  nop
0x18000a24c  lea     rcx, [rbp+57h+pszCabinet]
0x18000a250  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000a255  nop
0x18000a256  lea     rcx, [rbp+57h+WideCharStr]
0x18000a25a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a25f  nop
0x18000a260  mov     rcx, [rbp+57h+hfdi]; hfdi
0x18000a264  test    rcx, rcx
0x18000a267  jz      loc_18000A0F1
0x18000a26d  call    cs:__imp_FDIDestroy
0x18000a273  jmp     loc_18000A0F1
0x18000a278  mov     rax, [rbx+38h]
0x18000a27c  lea     rdx, [rbp+57h+pszCabinet]
0x18000a280  cmp     qword ptr [rbp+57h+var_58+8], 0Fh
0x18000a285  cmova   rdx, [rbp+57h+pszCabinet]; pszCabinet
0x18000a28a  mov     [rsp+0D0h+pfnseek], rdi; pvUser
0x18000a28f  mov     [rsp+0D0h+pfnclose], 0; pfnfdid
0x18000a298  mov     [rsp+0D0h+pfnwrite], rax; int
0x18000a29d  xor     r9d, r9d; flags
0x18000a2a0  lea     r8, pszCabPath; pszCabPath
0x18000a2a7  call    cs:__imp_FDICopy
0x18000a2ad  test    eax, eax
0x18000a2af  jnz     short loc_18000A327
0x18000a2b1  mov     ebx, [rbp+57h+perf.erfOper]
0x18000a2b4  lea     eax, [rbx-1]
0x18000a2b7  cmp     eax, 0Ah
0x18000a2ba  ja      loc_18000A34A
0x18000a2c0  add     ebx, 801882E0h
0x18000a2c6  cmp     ebx, 801882EBh
0x18000a2cc  jnz     short loc_18000A31F
0x18000a2ce  mov     edi, [rdi+0A0h]
0x18000a2d4  test    edi, edi
0x18000a2d6  jns     loc_18000A24C
0x18000a2dc  mov     rcx, [rbp+5Fh]; this
0x18000a2e0  mov     r9d, edi; char *
0x18000a2e3  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000a2ea  mov     edx, 0C6h; void *
0x18000a2ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a2f4  nop
0x18000a2f5  lea     rcx, [rbp+57h+pszCabinet]
0x18000a2f9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000a2fe  nop
0x18000a2ff  lea     rcx, [rbp+57h+WideCharStr]
0x18000a303  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a308  nop
0x18000a309  mov     rcx, [rbp+57h+hfdi]; hfdi
0x18000a30d  test    rcx, rcx
0x18000a310  jz      short loc_18000A318
0x18000a312  call    cs:__imp_FDIDestroy
0x18000a318  mov     eax, edi
0x18000a31a  jmp     loc_18000A3D8
0x18000a31f  test    ebx, ebx
0x18000a321  js      loc_18000A24C
0x18000a327  mov     rax, [rdi+10h]
0x18000a32b  mov     rax, [rax]
0x18000a32e  cmp     byte ptr [rax+19h], 0
0x18000a332  jnz     short loc_18000A3B3
0x18000a334  cmp     dword ptr [rax+40h], 0
0x18000a338  jz      short loc_18000A389
0x18000a33a  mov     rdx, [rax+10h]
0x18000a33e  cmp     byte ptr [rdx+19h], 0
0x18000a342  jz      short loc_18000A36C
0x18000a344  mov     rcx, [rax+8]
0x18000a348  jmp     short loc_18000A361
0x18000a34a  mov     ebx, 801882EFh
0x18000a34f  jmp     loc_18000A24C
0x18000a354  cmp     rax, [rcx+10h]
0x18000a358  jnz     short loc_18000A367
0x18000a35a  mov     rax, rcx
0x18000a35d  mov     rcx, [rcx+8]
0x18000a361  cmp     byte ptr [rcx+19h], 0
0x18000a365  jz      short loc_18000A354
0x18000a367  mov     rax, rcx
0x18000a36a  jmp     short loc_18000A32E
0x18000a36c  mov     rax, rdx
0x18000a36f  mov     rdx, [rdx]
0x18000a372  cmp     byte ptr [rdx+19h], 0
0x18000a376  jnz     short loc_18000A32E
0x18000a378  mov     rax, rdx
0x18000a37b  mov     rcx, [rdx]
0x18000a37e  mov     rdx, rcx
0x18000a381  cmp     byte ptr [rcx+19h], 0
0x18000a385  jz      short loc_18000A378
0x18000a387  jmp     short loc_18000A32E
0x18000a389  lea     rcx, [rbp+57h+pszCabinet]
0x18000a38d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000a392  nop
0x18000a393  lea     rcx, [rbp+57h+WideCharStr]
0x18000a397  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a39c  nop
0x18000a39d  mov     rcx, [rbp+57h+hfdi]; hfdi
0x18000a3a1  test    rcx, rcx
0x18000a3a4  jz      short loc_18000A3AC
0x18000a3a6  call    cs:__imp_FDIDestroy
0x18000a3ac  mov     eax, 801882C2h
0x18000a3b1  jmp     short loc_18000A3D8
0x18000a3b3  lea     rcx, [rbp+57h+pszCabinet]
0x18000a3b7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000a3bc  nop
0x18000a3bd  lea     rcx, [rbp+57h+WideCharStr]
0x18000a3c1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a3c6  nop
0x18000a3c7  mov     rcx, [rbp+57h+hfdi]; hfdi
0x18000a3cb  test    rcx, rcx
0x18000a3ce  jz      short loc_18000A3D6
0x18000a3d0  call    cs:__imp_FDIDestroy
0x18000a3d6  xor     eax, eax
0x18000a3d8  mov     rcx, [rbp+57h+var_18]
0x18000a3dc  xor     rcx, rsp; StackCookie
0x18000a3df  call    __security_check_cookie
0x18000a3e4  mov     rbx, [rsp+0D0h+arg_0]
0x18000a3ec  add     rsp, 0C0h
0x18000a3f3  pop     rdi
0x18000a3f4  pop     rsi
0x18000a3f5  pop     rbp
0x18000a3f6  retn
```
