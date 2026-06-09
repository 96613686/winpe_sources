# Cabinet::GetFileList(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> *,std::vector<unsigned __int64,std::allocator<unsigned __int64>> *)

- ea: `0x18000a400`
- end: `0x18000a744`
- name: `?GetFileList@Cabinet@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@PEAV?$vector@_KV?$allocator@_K@std@@@3@@Z`
- size: `836`
- prototype: `__int64 __fastcall(__int64, char ***, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800076f0`

## callees

- `0x180001540`
- `0x180003648`
- `0x18000553c`
- `0x1800080a0`
- `0x1800081d8`
- `0x180008248`
- `0x1800082b8`
- `0x18000a400`
- `0x18000b4c0`
- `0x18000b658`
- `0x18000e2fc`

## import_xrefs

- `Cabinet!__imp_FDICreate` at `0x18000a54e`
- `Cabinet!__imp_FDICreate` at `0x18000a54e`
- `Cabinet!__imp_FDICopy` at `0x18000a674`
- `Cabinet!__imp_FDICopy` at `0x18000a674`
- `Cabinet!__imp_FDIDestroy` at `0x18000a5ef`
- `Cabinet!__imp_FDIDestroy` at `0x18000a716`
- `Cabinet!__imp_FDIDestroy` at `0x18000a5ef`
- `Cabinet!__imp_FDIDestroy` at `0x18000a716`

## pseudocode

```c
__int64 __fastcall Cabinet::GetFileList(__int64 a1, char ***a2, _QWORD *a3)
{
  char **v7; // r14
  char **v8; // rbx
  int SelectedFiles; // ebx
  __int64 v10; // rdx
  CHAR *v11; // rdx
  int pfnwrite; // [rsp+28h] [rbp-E0h]
  HFDI hfdi; // [rsp+68h] [rbp-A0h]
  ERF perf; // [rsp+70h] [rbp-98h] BYREF
  __int128 v15; // [rsp+80h] [rbp-88h] BYREF
  __m128i v16; // [rsp+90h] [rbp-78h]
  WCHAR WideCharStr[8]; // [rsp+A0h] [rbp-68h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-58h]
  _BYTE pvUser[16]; // [rsp+C8h] [rbp-40h] BYREF
  void *v20[2]; // [rsp+D8h] [rbp-30h] BYREF
  void *v21[2]; // [rsp+E8h] [rbp-20h] BYREF
  void *v22[2]; // [rsp+F8h] [rbp-10h] BYREF
  char *v23[4]; // [rsp+108h] [rbp+0h] BYREF
  char *v24[4]; // [rsp+128h] [rbp+20h] BYREF
  char *v25[8]; // [rsp+148h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C0h] [rbp+B8h]

  if ( !*(_QWORD *)(a1 + 16) )
    return 2147942487LL;
  if ( !a2 )
    return 2147500035LL;
  v7 = a2[1];
  v8 = *a2;
  if ( *a2 != v7 )
  {
    do
    {
      std::wstring::~wstring(v8);
      v8 += 4;
    }
    while ( v8 != v7 );
    a2[1] = *a2;
  }
  if ( a3 && *a3 != a3[1] )
    a3[1] = *a3;
  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  CabContext::CabContext((__int64)pvUser, a1, 3, 0, 0);
  *(_OWORD *)WideCharStr = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  WideCharStr[0] = 0;
  v15 = 0;
  v16 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v15) = 0;
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
  if ( hfdi )
  {
    SelectedFiles = Utils::ConvertPointerToString((__int64)pvUser, (__int64)WideCharStr);
    if ( SelectedFiles < 0 )
    {
      v10 = 256;
      goto LABEL_17;
    }
    SelectedFiles = Utils::ConvertUnicodeToMultiByte(WideCharStr, &v15);
    if ( SelectedFiles < 0 )
    {
      v10 = 258;
      goto LABEL_17;
    }
    v11 = (CHAR *)&v15;
    if ( v16.m128i_i64[1] > 0xFuLL )
      v11 = (CHAR *)v15;
    if ( !FDICopy(hfdi, v11, (LPSTR)&pszCabPath, 0, (PFNFDINOTIFY)FdiCallbacks::CallbackFDINotify, 0, pvUser) )
    {
      if ( (unsigned int)(perf.erfOper - 1) > 0xA )
      {
        SelectedFiles = -2145877265;
      }
      else
      {
        SelectedFiles = perf.erfOper - 2145877280;
        if ( perf.erfOper - 2145877280 >= 0 )
          goto LABEL_30;
      }
      v10 = 271;
      goto LABEL_17;
    }
LABEL_30:
    SelectedFiles = CabContext::GetSelectedFiles(pvUser, a2, a3);
    if ( SelectedFiles >= 0 )
    {
      std::string::~string((char **)&v15);
      std::wstring::~wstring((char **)WideCharStr);
      std::wstring::~wstring(v25);
      std::wstring::~wstring(v24);
      std::wstring::~wstring(v23);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v22);
      std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v21);
      std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v20);
      FDIDestroy(hfdi);
      return 0;
    }
    v10 = 274;
    goto LABEL_17;
  }
  if ( (unsigned int)(perf.erfOper - 1) > 0xA )
  {
    SelectedFiles = -2145877265;
LABEL_16:
    v10 = 254;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)(unsigned int)SelectedFiles,
      pfnwrite);
    goto LABEL_18;
  }
  SelectedFiles = perf.erfOper - 2145877280;
  if ( perf.erfOper - 2145877280 < 0 )
    goto LABEL_16;
LABEL_18:
  std::string::~string((char **)&v15);
  std::wstring::~wstring((char **)WideCharStr);
  std::wstring::~wstring(v25);
  std::wstring::~wstring(v24);
  std::wstring::~wstring(v23);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v22);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v21);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v20);
  if ( hfdi )
    FDIDestroy(hfdi);
  return (unsigned int)SelectedFiles;
}

```

## disassembly

```asm
0x18000a400  mov     rax, rsp
0x18000a403  push    rbp
0x18000a404  push    rsi
0x18000a405  push    rdi
0x18000a406  push    r14
0x18000a408  push    r15
0x18000a40a  lea     rbp, [rax-0B8h]
0x18000a411  sub     rsp, 190h
0x18000a418  mov     [rsp+1B0h+var_160], 0FFFFFFFFFFFFFFFEh
0x18000a421  mov     [rax+20h], rbx
0x18000a425  mov     rax, cs:__security_cookie
0x18000a42c  xor     rax, rsp
0x18000a42f  mov     [rbp+0B0h+var_30], rax
0x18000a436  mov     rsi, r8
0x18000a439  mov     rdi, rdx
0x18000a43c  mov     r15, rcx
0x18000a43f  cmp     qword ptr [rcx+10h], 0
0x18000a444  jnz     short loc_18000A450
0x18000a446  mov     eax, 80070057h
0x18000a44b  jmp     loc_18000A71E
0x18000a450  test    rdi, rdi
0x18000a453  jnz     short loc_18000A45F
0x18000a455  mov     eax, 80004003h
0x18000a45a  jmp     loc_18000A71E
0x18000a45f  mov     r14, [rdx+8]
0x18000a463  mov     rbx, [rdx]
0x18000a466  cmp     rbx, r14
0x18000a469  jz      short loc_18000A483
0x18000a46b  mov     rcx, rbx
0x18000a46e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a473  add     rbx, 20h ; ' '
0x18000a477  cmp     rbx, r14
0x18000a47a  jnz     short loc_18000A46B
0x18000a47c  mov     rax, [rdi]
0x18000a47f  mov     [rdi+8], rax
0x18000a483  test    rsi, rsi
0x18000a486  jz      short loc_18000A495
0x18000a488  mov     rax, [rsi]
0x18000a48b  cmp     rax, [rsi+8]
0x18000a48f  jz      short loc_18000A495
0x18000a491  mov     [rsi+8], rax
0x18000a495  xor     eax, eax
0x18000a497  mov     qword ptr [rsp+1B0h+perf.erfOper], rax
0x18000a49c  mov     [rsp+1B0h+perf.fError], eax
0x18000a4a0  mov     [rsp+1B0h+hfdi], rax
0x18000a4a5  lea     rax, [rsp+1B0h+hfdi]
0x18000a4aa  mov     [rsp+1B0h+var_158], rax
0x18000a4af  mov     [rsp+1B0h+pfnwrite], 0
0x18000a4b8  xor     r9d, r9d
0x18000a4bb  lea     r8d, [r9+3]
0x18000a4bf  mov     rdx, r15
0x18000a4c2  lea     rcx, [rbp+0B0h+pvUser]
0x18000a4c6  call    ??0CabContext@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KPEAPEAEPEAK@Z; CabContext::CabContext(std::wstring const &,ulong,uchar * *,ulong *)
0x18000a4cb  nop
0x18000a4cc  xorps   xmm0, xmm0
0x18000a4cf  movups  xmmword ptr [rbp+0B0h+WideCharStr], xmm0
0x18000a4d3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000a4db  movdqu  [rbp+0B0h+var_108], xmm1
0x18000a4e0  xor     eax, eax
0x18000a4e2  mov     [rbp+0B0h+WideCharStr], ax
0x18000a4e6  movups  [rsp+1B0h+var_138], xmm0
0x18000a4eb  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18000a4f3  movdqu  [rbp+0B0h+var_128], xmm1
0x18000a4f8  mov     byte ptr [rsp+1B0h+var_138], al
0x18000a4fc  lea     rax, [rsp+1B0h+perf]
0x18000a501  mov     [rsp+40h], rax; perf
0x18000a506  mov     [rsp+1B0h+cpuType], 0FFFFFFFFh; cpuType
0x18000a50e  lea     rax, ?CallbackFileSeek@FdiCallbacks@@SAJ_JJH@Z; FdiCallbacks::CallbackFileSeek(__int64,long,int)
0x18000a515  mov     [rsp+1B0h+pfnseek], rax; pfnseek
0x18000a51a  lea     rax, ?CallbackFileClose@FdiCallbacks@@SAH_J@Z; FdiCallbacks::CallbackFileClose(__int64)
0x18000a521  mov     [rsp+1B0h+pfnclose], rax; pfnclose
0x18000a526  lea     rax, ?CallbackFileWrite@FdiCallbacks@@SAI_JPEAXI@Z; FdiCallbacks::CallbackFileWrite(__int64,void *,uint)
0x18000a52d  mov     [rsp+1B0h+pfnwrite], rax; int
0x18000a532  lea     r9, ?CallbackFileRead@FdiCallbacks@@SAI_JPEAXI@Z; pfnread
0x18000a539  lea     r8, ?CallbackFileOpen@FdiCallbacks@@SA_JPEADHH@Z; pfnopen
0x18000a540  lea     rdx, ?CallbackFree@FdiCallbacks@@SAXPEAX@Z; pfnfree
0x18000a547  lea     rcx, ?CallbackAlloc@FdiCallbacks@@SAPEAXK@Z; pfnalloc
0x18000a54e  call    cs:__imp_FDICreate
0x18000a554  mov     [rsp+1B0h+hfdi], rax
0x18000a559  test    rax, rax
0x18000a55c  jnz     loc_18000A5FC
0x18000a562  mov     ebx, [rsp+1B0h+perf.erfOper]
0x18000a566  lea     eax, [rbx-1]
0x18000a569  cmp     eax, 0Ah
0x18000a56c  ja      short loc_18000A578
0x18000a56e  add     ebx, 801882E0h
0x18000a574  jns     short loc_18000A599
0x18000a576  jmp     short loc_18000A57D
0x18000a578  mov     ebx, 801882EFh
0x18000a57d  mov     edx, 0FEh; void *
0x18000a582  mov     rcx, [rbp+0B8h]; this
0x18000a589  mov     r9d, ebx; char *
0x18000a58c  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000a593  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a598  nop
0x18000a599  lea     rcx, [rsp+1B0h+var_138]
0x18000a59e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000a5a3  nop
0x18000a5a4  lea     rcx, [rbp+0B0h+WideCharStr]
0x18000a5a8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a5ad  nop
0x18000a5ae  lea     rcx, [rbp+0B0h+var_70]
0x18000a5b2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a5b7  lea     rcx, [rbp+0B0h+var_90]
0x18000a5bb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a5c0  lea     rcx, [rbp+0B0h+var_B0]
0x18000a5c4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a5c9  lea     rcx, [rbp+0B0h+var_C0]
0x18000a5cd  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18000a5d2  lea     rcx, [rbp+0B0h+var_D0]
0x18000a5d6  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x18000a5db  lea     rcx, [rbp+0B0h+var_E0]
0x18000a5df  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x18000a5e4  nop
0x18000a5e5  mov     rcx, [rsp+1B0h+hfdi]; hfdi
0x18000a5ea  test    rcx, rcx
0x18000a5ed  jz      short loc_18000A5F5
0x18000a5ef  call    cs:__imp_FDIDestroy
0x18000a5f5  mov     eax, ebx
0x18000a5f7  jmp     loc_18000A71E
0x18000a5fc  lea     rdx, [rbp+0B0h+WideCharStr]
0x18000a600  lea     rcx, [rbp+0B0h+pvUser]
0x18000a604  call    ?ConvertPointerToString@Utils@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Utils::ConvertPointerToString(void *,std::wstring *)
0x18000a609  mov     ebx, eax
0x18000a60b  test    eax, eax
0x18000a60d  jns     short loc_18000A619
0x18000a60f  mov     edx, 100h
0x18000a614  jmp     loc_18000A582
0x18000a619  lea     rdx, [rsp+1B0h+var_138]; void *
0x18000a61e  lea     rcx, [rbp+0B0h+WideCharStr]; lpWideCharStr
0x18000a622  call    ?ConvertUnicodeToMultiByte@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; Utils::ConvertUnicodeToMultiByte(std::wstring const &,std::string *)
0x18000a627  mov     ebx, eax
0x18000a629  test    eax, eax
0x18000a62b  jns     short loc_18000A637
0x18000a62d  mov     edx, 102h
0x18000a632  jmp     loc_18000A582
0x18000a637  lea     rdx, [rsp+1B0h+var_138]
0x18000a63c  cmp     qword ptr [rbp+0B0h+var_128+8], 0Fh
0x18000a641  cmova   rdx, qword ptr [rsp+1B0h+var_138]; pszCabinet
0x18000a647  lea     rax, [rbp+0B0h+pvUser]
0x18000a64b  mov     [rsp+1B0h+pfnseek], rax; pvUser
0x18000a650  mov     [rsp+1B0h+pfnclose], 0; pfnfdid
0x18000a659  lea     rax, ?CallbackFDINotify@FdiCallbacks@@SA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; FdiCallbacks::CallbackFDINotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x18000a660  mov     [rsp+1B0h+pfnwrite], rax; pfnfdin
0x18000a665  xor     r9d, r9d; flags
0x18000a668  lea     r8, pszCabPath; pszCabPath
0x18000a66f  mov     rcx, [rsp+1B0h+hfdi]; hfdi
0x18000a674  call    cs:__imp_FDICopy
0x18000a67a  test    eax, eax
0x18000a67c  jnz     short loc_18000A692
0x18000a67e  mov     ebx, [rsp+1B0h+perf.erfOper]
0x18000a682  lea     eax, [rbx-1]
0x18000a685  cmp     eax, 0Ah
0x18000a688  ja      short loc_18000A6B1
0x18000a68a  add     ebx, 801882E0h
0x18000a690  js      short loc_18000A6B6
0x18000a692  mov     r8, rsi
0x18000a695  mov     rdx, rdi
0x18000a698  lea     rcx, [rbp+0B0h+pvUser]
0x18000a69c  call    ?GetSelectedFiles@CabContext@@QEBAJPEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@PEAV?$vector@_KV?$allocator@_K@std@@@3@@Z; CabContext::GetSelectedFiles(std::vector<std::wstring> *,std::vector<unsigned __int64> *)
0x18000a6a1  mov     ebx, eax
0x18000a6a3  test    eax, eax
0x18000a6a5  jns     short loc_18000A6C0
0x18000a6a7  mov     edx, 112h
0x18000a6ac  jmp     loc_18000A582
0x18000a6b1  mov     ebx, 801882EFh
0x18000a6b6  mov     edx, 10Fh
0x18000a6bb  jmp     loc_18000A582
0x18000a6c0  lea     rcx, [rsp+1B0h+var_138]
0x18000a6c5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000a6ca  nop
0x18000a6cb  lea     rcx, [rbp+0B0h+WideCharStr]
0x18000a6cf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a6d4  nop
0x18000a6d5  lea     rcx, [rbp+0B0h+var_70]
0x18000a6d9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a6de  lea     rcx, [rbp+0B0h+var_90]
0x18000a6e2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a6e7  lea     rcx, [rbp+0B0h+var_B0]
0x18000a6eb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a6f0  lea     rcx, [rbp+0B0h+var_C0]
0x18000a6f4  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18000a6f9  lea     rcx, [rbp+0B0h+var_D0]
0x18000a6fd  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x18000a702  lea     rcx, [rbp+0B0h+var_E0]
0x18000a706  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x18000a70b  nop
0x18000a70c  mov     rcx, [rsp+1B0h+hfdi]; hfdi
0x18000a711  test    rcx, rcx
0x18000a714  jz      short loc_18000A71C
0x18000a716  call    cs:__imp_FDIDestroy
0x18000a71c  xor     eax, eax
0x18000a71e  mov     rcx, [rbp+0B0h+var_30]
0x18000a725  xor     rcx, rsp; StackCookie
0x18000a728  call    __security_check_cookie
0x18000a72d  mov     rbx, [rsp+1B0h+arg_18]
0x18000a735  add     rsp, 190h
0x18000a73c  pop     r15
0x18000a73e  pop     r14
0x18000a740  pop     rdi
0x18000a741  pop     rsi
0x18000a742  pop     rbp
0x18000a743  retn
```
