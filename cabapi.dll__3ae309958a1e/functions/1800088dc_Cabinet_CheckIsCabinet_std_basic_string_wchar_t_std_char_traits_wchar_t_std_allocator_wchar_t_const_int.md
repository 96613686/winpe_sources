# Cabinet::CheckIsCabinet(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,int *)

- ea: `0x1800088dc`
- end: `0x180008c1b`
- name: `?CheckIsCabinet@Cabinet@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAH@Z`
- size: `831`
- prototype: `__int64 __fastcall(__int64, BOOL *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180006ac0`

## callees

- `0x180001540`
- `0x180003648`
- `0x180005514`
- `0x18000553c`
- `0x1800080a0`
- `0x1800081d8`
- `0x180008248`
- `0x1800082b8`
- `0x1800088dc`
- `0x18000b4c0`
- `0x18000b658`
- `0x18000ce80`
- `0x18000cee0`

## import_xrefs

- `Cabinet!__imp_FDICreate` at `0x180008a2b`
- `Cabinet!__imp_FDICreate` at `0x180008a2b`
- `Cabinet!__imp_FDIIsCabinet` at `0x180008b7e`
- `Cabinet!__imp_FDIIsCabinet` at `0x180008b7e`
- `Cabinet!__imp_FDIDestroy` at `0x180008ae3`
- `Cabinet!__imp_FDIDestroy` at `0x180008bf0`
- `Cabinet!__imp_FDIDestroy` at `0x180008ae3`
- `Cabinet!__imp_FDIDestroy` at `0x180008bf0`

## pseudocode

```c
__int64 __fastcall Cabinet::CheckIsCabinet(__int64 a1, BOOL *a2)
{
  int LastError; // ebx
  __int64 v4; // rdx
  __int64 v6; // rdx
  CHAR *v7; // rcx
  INT_PTR v8; // rax
  const char *v9; // r9
  int pfnwrite; // [rsp+28h] [rbp-E0h]
  int pfnwritea; // [rsp+28h] [rbp-E0h]
  HFDI hfdi; // [rsp+70h] [rbp-98h]
  INT_PTR hf[3]; // [rsp+78h] [rbp-90h] BYREF
  __m128i v14; // [rsp+90h] [rbp-78h]
  ERF perf; // [rsp+A0h] [rbp-68h] BYREF
  WCHAR WideCharStr[8]; // [rsp+B0h] [rbp-58h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-48h]
  _BYTE v18[16]; // [rsp+D8h] [rbp-30h] BYREF
  void *v19[2]; // [rsp+E8h] [rbp-20h] BYREF
  void *v20[2]; // [rsp+F8h] [rbp-10h] BYREF
  void *v21[2]; // [rsp+108h] [rbp+0h] BYREF
  char *v22[4]; // [rsp+118h] [rbp+10h] BYREF
  char *v23[4]; // [rsp+138h] [rbp+30h] BYREF
  char *v24[8]; // [rsp+158h] [rbp+50h] BYREF
  FDICABINETINFO pfdici; // [rsp+198h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]

  if ( !*(_QWORD *)(a1 + 16) )
  {
    LastError = -2147024809;
    v4 = 343;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)(unsigned int)LastError,
      pfnwrite);
    return (unsigned int)LastError;
  }
  if ( !a2 )
  {
    LastError = -2147467261;
    v4 = 344;
    goto LABEL_3;
  }
  *a2 = 0;
  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  memset(hf, 0, sizeof(hf));
  memset(&pfdici, 0, sizeof(pfdici));
  *(_OWORD *)WideCharStr = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  WideCharStr[0] = 0;
  v14 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(hf[1]) = 0;
  CabContext::CabContext((__int64)v18, a1, 3, 0, 0);
  hfdi = FDICreate(
           FdiCallbacks::CallbackAlloc,
           (PFNFREE)FdiCallbacks::CallbackFree,
           (PFNOPEN)FdiCallbacks::CallbackFileOpen,
           (PFNREAD)FdiCallbacks::CallbackFileRead,
           (PFNWRITE)FdiCallbacks::CallbackFileWrite,
           FdiCallbacks::CallbackFileClose,
           (PFNSEEK)FdiCallbacks::CallbackFileSeek,
           -1,
           &perf);
  if ( !hfdi )
  {
    if ( (unsigned int)(perf.erfOper - 1) > 0xA )
    {
      LastError = -2145877265;
    }
    else
    {
      LastError = perf.erfOper - 2145877280;
      if ( perf.erfOper - 2145877280 >= 0 )
      {
LABEL_14:
        std::wstring::~wstring(v24);
        std::wstring::~wstring(v23);
        std::wstring::~wstring(v22);
        std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v21);
        std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v20);
        std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v19);
        std::string::~string((char **)&hf[1]);
        std::wstring::~wstring((char **)WideCharStr);
        if ( hf[0] != -1 )
          FdiCallbacks::CallbackFileClose(hf[0]);
        if ( hfdi )
          FDIDestroy(hfdi);
        return (unsigned int)LastError;
      }
    }
    v6 = 369;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)(unsigned int)LastError,
      pfnwritea);
    goto LABEL_14;
  }
  LastError = Utils::ConvertPointerToString(v18, WideCharStr);
  if ( LastError < 0 )
  {
    v6 = 371;
    goto LABEL_13;
  }
  LastError = Utils::ConvertUnicodeToMultiByte(WideCharStr, &hf[1]);
  if ( LastError < 0 )
  {
    v6 = 373;
    goto LABEL_13;
  }
  v7 = (CHAR *)&hf[1];
  if ( v14.m128i_i64[1] > 0xFuLL )
    v7 = (CHAR *)hf[1];
  v8 = FdiCallbacks::CallbackFileOpen(v7, 0x8000u, 0);
  hf[0] = v8;
  if ( v8 == -1 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x17C,
                  (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
                  v9);
    goto LABEL_14;
  }
  *a2 = FDIIsCabinet(hfdi, v8, &pfdici);
  std::wstring::~wstring(v24);
  std::wstring::~wstring(v23);
  std::wstring::~wstring(v22);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v21);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v20);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v19);
  std::string::~string((char **)&hf[1]);
  std::wstring::~wstring((char **)WideCharStr);
  FdiCallbacks::CallbackFileClose(hf[0]);
  FDIDestroy(hfdi);
  return 0;
}

```

## disassembly

```asm
0x1800088dc  mov     rax, rsp
0x1800088df  push    rbp
0x1800088e0  push    rdi
0x1800088e1  push    r14
0x1800088e3  lea     rbp, [rax-0C8h]
0x1800088ea  sub     rsp, 1B0h
0x1800088f1  mov     [rsp+1C0h+var_170], 0FFFFFFFFFFFFFFFEh
0x1800088fa  mov     [rax+18h], rbx
0x1800088fe  mov     rax, cs:__security_cookie
0x180008905  xor     rax, rsp
0x180008908  mov     [rbp+0C0h+var_18], rax
0x18000890f  mov     rdi, rdx
0x180008912  cmp     qword ptr [rcx+10h], 0
0x180008917  jnz     short loc_180008940
0x180008919  mov     ebx, 80070057h
0x18000891e  mov     edx, 157h; void *
0x180008923  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000892a  mov     r9d, ebx; char *
0x18000892d  mov     rcx, [rbp+0C8h]; this
0x180008934  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008939  mov     eax, ebx
0x18000893b  jmp     loc_180008BF8
0x180008940  test    rdi, rdi
0x180008943  jnz     short loc_180008951
0x180008945  mov     ebx, 80004003h
0x18000894a  mov     edx, 158h
0x18000894f  jmp     short loc_180008923
0x180008951  mov     dword ptr [rdx], 0
0x180008957  xor     eax, eax
0x180008959  mov     qword ptr [rbp+0C0h+perf.erfOper], rax
0x18000895d  mov     [rbp+0C0h+perf.fError], eax
0x180008960  mov     [rsp+1C0h+hfdi], rax
0x180008965  lea     rax, [rsp+1C0h+hfdi]
0x18000896a  mov     [rsp+1C0h+var_168], rax
0x18000896f  mov     qword ptr [rsp+1C0h+hf], 0
0x180008978  lea     rax, [rsp+1C0h+hf]
0x18000897d  mov     [rsp+1C0h+var_160], rax
0x180008982  xorps   xmm0, xmm0
0x180008985  xor     eax, eax
0x180008987  movups  xmmword ptr [rbp+0C0h+pfdici.cbCabinet], xmm0
0x18000898e  mov     qword ptr [rbp+0C0h+pfdici.hasprev], rax
0x180008995  movups  xmmword ptr [rbp+0C0h+WideCharStr], xmm0
0x180008999  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800089a1  movdqu  [rbp+0C0h+var_108], xmm1
0x1800089a6  mov     [rbp+0C0h+WideCharStr], ax
0x1800089aa  movups  xmmword ptr [rsp+1C0h+hf+8], xmm0
0x1800089af  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800089b7  movdqu  [rbp+0C0h+var_138], xmm1
0x1800089bc  mov     [rsp+1C0h+hf+8], al
0x1800089c0  mov     [rsp+1C0h+pfnwrite], rax
0x1800089c5  xor     r9d, r9d
0x1800089c8  lea     r8d, [rax+3]
0x1800089cc  mov     rdx, rcx
0x1800089cf  lea     rcx, [rbp+0C0h+var_F0]
0x1800089d3  call    ??0CabContext@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KPEAPEAEPEAK@Z; CabContext::CabContext(std::wstring const &,ulong,uchar * *,ulong *)
0x1800089d8  nop
0x1800089d9  lea     rax, [rbp+0C0h+perf]
0x1800089dd  mov     [rsp+40h], rax; perf
0x1800089e2  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800089e6  mov     [rsp+1C0h+cpuType], r14d; cpuType
0x1800089eb  lea     rax, ?CallbackFileSeek@FdiCallbacks@@SAJ_JJH@Z; FdiCallbacks::CallbackFileSeek(__int64,long,int)
0x1800089f2  mov     [rsp+1C0h+pfnseek], rax; pfnseek
0x1800089f7  lea     rax, ?CallbackFileClose@FdiCallbacks@@SAH_J@Z; FdiCallbacks::CallbackFileClose(__int64)
0x1800089fe  mov     [rsp+1C0h+pfnclose], rax; pfnclose
0x180008a03  lea     rax, ?CallbackFileWrite@FdiCallbacks@@SAI_JPEAXI@Z; FdiCallbacks::CallbackFileWrite(__int64,void *,uint)
0x180008a0a  mov     [rsp+1C0h+pfnwrite], rax; int
0x180008a0f  lea     r9, ?CallbackFileRead@FdiCallbacks@@SAI_JPEAXI@Z; pfnread
0x180008a16  lea     r8, ?CallbackFileOpen@FdiCallbacks@@SA_JPEADHH@Z; pfnopen
0x180008a1d  lea     rdx, ?CallbackFree@FdiCallbacks@@SAXPEAX@Z; pfnfree
0x180008a24  lea     rcx, ?CallbackAlloc@FdiCallbacks@@SAPEAXK@Z; pfnalloc
0x180008a2b  call    cs:__imp_FDICreate
0x180008a31  mov     [rsp+1C0h+hfdi], rax
0x180008a36  test    rax, rax
0x180008a39  jnz     loc_180008AEE
0x180008a3f  mov     ebx, [rbp+0C0h+perf.erfOper]
0x180008a42  lea     eax, [rbx-1]
0x180008a45  cmp     eax, 0Ah
0x180008a48  ja      short loc_180008A54
0x180008a4a  add     ebx, 801882E0h
0x180008a50  jns     short loc_180008A75
0x180008a52  jmp     short loc_180008A59
0x180008a54  mov     ebx, 801882EFh
0x180008a59  mov     edx, 171h; void *
0x180008a5e  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x180008a65  mov     r9d, ebx; char *
0x180008a68  mov     rcx, [rbp+0C8h]; this
0x180008a6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a74  nop
0x180008a75  lea     rcx, [rbp+0C0h+var_70]
0x180008a79  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008a7e  lea     rcx, [rbp+0C0h+var_90]
0x180008a82  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008a87  lea     rcx, [rbp+0C0h+var_B0]
0x180008a8b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008a90  lea     rcx, [rbp+0C0h+var_C0]
0x180008a94  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180008a99  lea     rcx, [rbp+0C0h+var_D0]
0x180008a9d  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x180008aa2  lea     rcx, [rbp+0C0h+var_E0]
0x180008aa6  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x180008aab  nop
0x180008aac  lea     rcx, [rsp+1C0h+hf+8]
0x180008ab1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180008ab6  nop
0x180008ab7  lea     rcx, [rbp+0C0h+WideCharStr]
0x180008abb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008ac0  nop
0x180008ac1  mov     rcx, qword ptr [rsp+1C0h+hf]; hf
0x180008ac6  cmp     rcx, r14
0x180008ac9  jz      short loc_180008AD5
0x180008acb  call    ?CallbackFileClose@FdiCallbacks@@SAH_J@Z; FdiCallbacks::CallbackFileClose(__int64)
0x180008ad0  mov     qword ptr [rsp+1C0h+hf], r14
0x180008ad5  mov     rcx, [rsp+1C0h+hfdi]; hfdi
0x180008ada  test    rcx, rcx
0x180008add  jz      loc_180008939
0x180008ae3  call    cs:__imp_FDIDestroy
0x180008ae9  jmp     loc_180008939
0x180008aee  lea     rdx, [rbp+0C0h+WideCharStr]
0x180008af2  lea     rcx, [rbp+0C0h+var_F0]
0x180008af6  call    ?ConvertPointerToString@Utils@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Utils::ConvertPointerToString(void *,std::wstring *)
0x180008afb  mov     ebx, eax
0x180008afd  test    eax, eax
0x180008aff  jns     short loc_180008B0B
0x180008b01  mov     edx, 173h
0x180008b06  jmp     loc_180008A5E
0x180008b0b  lea     rdx, [rsp+1C0h+hf+8]; void *
0x180008b10  lea     rcx, [rbp+0C0h+WideCharStr]; lpWideCharStr
0x180008b14  call    ?ConvertUnicodeToMultiByte@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; Utils::ConvertUnicodeToMultiByte(std::wstring const &,std::string *)
0x180008b19  mov     ebx, eax
0x180008b1b  test    eax, eax
0x180008b1d  jns     short loc_180008B29
0x180008b1f  mov     edx, 175h
0x180008b24  jmp     loc_180008A5E
0x180008b29  lea     rcx, [rsp+1C0h+hf+8]
0x180008b2e  cmp     qword ptr [rbp+0C0h+var_138+8], 0Fh
0x180008b33  cmova   rcx, qword ptr [rsp+1C0h+hf+8]; pszFile
0x180008b39  xor     r8d, r8d; pmode
0x180008b3c  mov     edx, 8000h; oflag
0x180008b41  call    ?CallbackFileOpen@FdiCallbacks@@SA_JPEADHH@Z; FdiCallbacks::CallbackFileOpen(char *,int,int)
0x180008b46  mov     qword ptr [rsp+1C0h+hf], rax
0x180008b4b  cmp     rax, r14
0x180008b4e  jnz     short loc_180008B6F
0x180008b50  mov     rcx, [rbp+0C8h]; this
0x180008b57  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x180008b5e  mov     edx, 17Ch; void *
0x180008b63  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008b68  mov     ebx, eax
0x180008b6a  jmp     loc_180008A75
0x180008b6f  lea     r8, [rbp+0C0h+pfdici]; pfdici
0x180008b76  mov     rdx, rax; hf
0x180008b79  mov     rcx, [rsp+1C0h+hfdi]; hfdi
0x180008b7e  call    cs:__imp_FDIIsCabinet
0x180008b84  mov     [rdi], eax
0x180008b86  lea     rcx, [rbp+0C0h+var_70]
0x180008b8a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008b8f  lea     rcx, [rbp+0C0h+var_90]
0x180008b93  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008b98  lea     rcx, [rbp+0C0h+var_B0]
0x180008b9c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008ba1  lea     rcx, [rbp+0C0h+var_C0]
0x180008ba5  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180008baa  lea     rcx, [rbp+0C0h+var_D0]
0x180008bae  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x180008bb3  lea     rcx, [rbp+0C0h+var_E0]
0x180008bb7  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x180008bbc  nop
0x180008bbd  lea     rcx, [rsp+1C0h+hf+8]
0x180008bc2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180008bc7  nop
0x180008bc8  lea     rcx, [rbp+0C0h+WideCharStr]
0x180008bcc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008bd1  nop
0x180008bd2  mov     rcx, qword ptr [rsp+1C0h+hf]; hf
0x180008bd7  cmp     rcx, r14
0x180008bda  jz      short loc_180008BE6
0x180008bdc  call    ?CallbackFileClose@FdiCallbacks@@SAH_J@Z; FdiCallbacks::CallbackFileClose(__int64)
0x180008be1  mov     qword ptr [rsp+1C0h+hf], r14
0x180008be6  mov     rcx, [rsp+1C0h+hfdi]; hfdi
0x180008beb  test    rcx, rcx
0x180008bee  jz      short loc_180008BF6
0x180008bf0  call    cs:__imp_FDIDestroy
0x180008bf6  xor     eax, eax
0x180008bf8  mov     rcx, [rbp+0C0h+var_18]
0x180008bff  xor     rcx, rsp; StackCookie
0x180008c02  call    __security_check_cookie
0x180008c07  mov     rbx, [rsp+1C0h+arg_10]
0x180008c0f  add     rsp, 1B0h
0x180008c16  pop     r14
0x180008c18  pop     rdi
0x180008c19  pop     rbp
0x180008c1a  retn
```
