# Cabinet::CheckForFile(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,int *)

- ea: `0x1800085ac`
- end: `0x1800088d6`
- name: `?CheckForFile@Cabinet@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0PEAH@Z`
- size: `810`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800069c0`

## callees

- `0x180001540`
- `0x180003648`
- `0x18000553c`
- `0x1800080a0`
- `0x1800081d8`
- `0x180008248`
- `0x1800082b8`
- `0x1800085ac`
- `0x18000b4c0`
- `0x18000b658`
- `0x18000e604`

## import_xrefs

- `Cabinet!__imp_FDICreate` at `0x1800086ea`
- `Cabinet!__imp_FDICreate` at `0x1800086ea`
- `Cabinet!__imp_FDICopy` at `0x180008812`
- `Cabinet!__imp_FDICopy` at `0x180008812`
- `Cabinet!__imp_FDIDestroy` at `0x18000878f`
- `Cabinet!__imp_FDIDestroy` at `0x18000889c`
- `Cabinet!__imp_FDIDestroy` at `0x18000878f`
- `Cabinet!__imp_FDIDestroy` at `0x18000889c`

## pseudocode

```c
__int64 __fastcall Cabinet::CheckForFile(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v5; // rdx
  int v6; // ebx
  __int64 v8; // rdx
  CHAR *v9; // rdx
  int pfnwrite; // [rsp+28h] [rbp-E0h]
  int pfnwritea; // [rsp+28h] [rbp-E0h]
  HFDI hfdi; // [rsp+68h] [rbp-A0h]
  ERF perf; // [rsp+70h] [rbp-98h] BYREF
  __int128 v14; // [rsp+80h] [rbp-88h] BYREF
  __m128i v15; // [rsp+90h] [rbp-78h]
  WCHAR WideCharStr[8]; // [rsp+A0h] [rbp-68h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-58h]
  _BYTE pvUser[16]; // [rsp+C8h] [rbp-40h] BYREF
  void *v19[2]; // [rsp+D8h] [rbp-30h] BYREF
  void *v20[2]; // [rsp+E8h] [rbp-20h] BYREF
  void *v21[2]; // [rsp+F8h] [rbp-10h] BYREF
  char *v22[4]; // [rsp+108h] [rbp+0h] BYREF
  char *v23[4]; // [rsp+128h] [rbp+20h] BYREF
  char *v24[8]; // [rsp+148h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B0h] [rbp+A8h]

  if ( !*(_QWORD *)(a1 + 16) )
  {
    v5 = 285;
LABEL_3:
    v6 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)(unsigned int)v6,
      pfnwrite);
    return (unsigned int)v6;
  }
  if ( !*(_QWORD *)(a2 + 16) )
  {
    v5 = 286;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v6 = -2147467261;
    v5 = 287;
    goto LABEL_4;
  }
  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  CabContext::CabContext((__int64)pvUser, a1, 3, 0, 0);
  *(_OWORD *)WideCharStr = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  WideCharStr[0] = 0;
  v14 = 0;
  v15 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v14) = 0;
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
      v6 = -2145877265;
    }
    else
    {
      v6 = perf.erfOper - 2145877280;
      if ( perf.erfOper - 2145877280 >= 0 )
        goto LABEL_17;
    }
    v8 = 308;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabinetapi.cpp",
      (const char *)(unsigned int)v6,
      pfnwritea);
LABEL_17:
    std::string::~string((char **)&v14);
    std::wstring::~wstring((char **)WideCharStr);
    std::wstring::~wstring(v24);
    std::wstring::~wstring(v23);
    std::wstring::~wstring(v22);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v21);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v20);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v19);
    if ( hfdi )
      FDIDestroy(hfdi);
    return (unsigned int)v6;
  }
  v6 = Utils::ConvertPointerToString(pvUser, WideCharStr);
  if ( v6 < 0 )
  {
    v8 = 310;
    goto LABEL_16;
  }
  v6 = Utils::ConvertUnicodeToMultiByte(WideCharStr, &v14);
  if ( v6 < 0 )
  {
    v8 = 312;
    goto LABEL_16;
  }
  v9 = (CHAR *)&v14;
  if ( v15.m128i_i64[1] > 0xFuLL )
    v9 = (CHAR *)v14;
  if ( !FDICopy(hfdi, v9, (LPSTR)&pszCabPath, 0, (PFNFDINOTIFY)FdiCallbacks::CallbackFDINotify, 0, pvUser) )
  {
    if ( (unsigned int)(perf.erfOper - 1) > 0xA )
    {
      v6 = -2145877265;
    }
    else
    {
      v6 = perf.erfOper - 2145877280;
      if ( perf.erfOper - 2145877280 >= 0 )
        goto LABEL_28;
    }
    v8 = 325;
    goto LABEL_16;
  }
LABEL_28:
  *a3 = CabContext::IsSelected(pvUser, a2);
  std::string::~string((char **)&v14);
  std::wstring::~wstring((char **)WideCharStr);
  std::wstring::~wstring(v24);
  std::wstring::~wstring(v23);
  std::wstring::~wstring(v22);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v21);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v20);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v19);
  FDIDestroy(hfdi);
  return 0;
}

```

## disassembly

```asm
0x1800085ac  mov     rax, rsp
0x1800085af  push    rbp
0x1800085b0  push    rsi
0x1800085b1  push    rdi
0x1800085b2  lea     rbp, [rax-0A8h]
0x1800085b9  sub     rsp, 190h
0x1800085c0  mov     [rsp+1A0h+var_150], 0FFFFFFFFFFFFFFFEh
0x1800085c9  mov     [rax+20h], rbx
0x1800085cd  mov     rax, cs:__security_cookie
0x1800085d4  xor     rax, rsp
0x1800085d7  mov     [rbp+0A0h+var_20], rax
0x1800085de  mov     rdi, r8
0x1800085e1  mov     rsi, rdx
0x1800085e4  cmp     qword ptr [rcx+10h], 0
0x1800085e9  jnz     short loc_180008612
0x1800085eb  mov     edx, 11Dh; void *
0x1800085f0  mov     ebx, 80070057h
0x1800085f5  mov     rcx, [rbp+0A8h]; this
0x1800085fc  mov     r9d, ebx; char *
0x1800085ff  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x180008606  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000860b  mov     eax, ebx
0x18000860d  jmp     loc_1800088A4
0x180008612  cmp     qword ptr [rdx+10h], 0
0x180008617  jnz     short loc_180008620
0x180008619  mov     edx, 11Eh
0x18000861e  jmp     short loc_1800085F0
0x180008620  test    rdi, rdi
0x180008623  jnz     short loc_180008631
0x180008625  mov     ebx, 80004003h
0x18000862a  mov     edx, 11Fh
0x18000862f  jmp     short loc_1800085F5
0x180008631  xor     eax, eax
0x180008633  mov     qword ptr [rsp+1A0h+perf.erfOper], rax
0x180008638  mov     [rsp+1A0h+perf.fError], eax
0x18000863c  mov     [rsp+1A0h+hfdi], rax
0x180008641  lea     rax, [rsp+1A0h+hfdi]
0x180008646  mov     [rsp+1A0h+var_148], rax
0x18000864b  mov     [rsp+1A0h+pfnwrite], 0
0x180008654  xor     r9d, r9d
0x180008657  lea     r8d, [r9+3]
0x18000865b  mov     rdx, rcx
0x18000865e  lea     rcx, [rbp+0A0h+pvUser]
0x180008662  call    ??0CabContext@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KPEAPEAEPEAK@Z; CabContext::CabContext(std::wstring const &,ulong,uchar * *,ulong *)
0x180008667  nop
0x180008668  xorps   xmm0, xmm0
0x18000866b  movups  xmmword ptr [rbp+0A0h+WideCharStr], xmm0
0x18000866f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180008677  movdqu  [rbp+0A0h+var_F8], xmm1
0x18000867c  xor     eax, eax
0x18000867e  mov     [rbp+0A0h+WideCharStr], ax
0x180008682  movups  [rsp+1A0h+var_128], xmm0
0x180008687  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18000868f  movdqu  [rbp+0A0h+var_118], xmm1
0x180008694  mov     byte ptr [rsp+1A0h+var_128], al
0x180008698  lea     rax, [rsp+1A0h+perf]
0x18000869d  mov     [rsp+40h], rax; perf
0x1800086a2  mov     [rsp+1A0h+cpuType], 0FFFFFFFFh; cpuType
0x1800086aa  lea     rax, ?CallbackFileSeek@FdiCallbacks@@SAJ_JJH@Z; FdiCallbacks::CallbackFileSeek(__int64,long,int)
0x1800086b1  mov     [rsp+1A0h+pfnseek], rax; pfnseek
0x1800086b6  lea     rax, ?CallbackFileClose@FdiCallbacks@@SAH_J@Z; FdiCallbacks::CallbackFileClose(__int64)
0x1800086bd  mov     [rsp+1A0h+pfnclose], rax; pfnclose
0x1800086c2  lea     rax, ?CallbackFileWrite@FdiCallbacks@@SAI_JPEAXI@Z; FdiCallbacks::CallbackFileWrite(__int64,void *,uint)
0x1800086c9  mov     [rsp+1A0h+pfnwrite], rax; int
0x1800086ce  lea     r9, ?CallbackFileRead@FdiCallbacks@@SAI_JPEAXI@Z; pfnread
0x1800086d5  lea     r8, ?CallbackFileOpen@FdiCallbacks@@SA_JPEADHH@Z; pfnopen
0x1800086dc  lea     rdx, ?CallbackFree@FdiCallbacks@@SAXPEAX@Z; pfnfree
0x1800086e3  lea     rcx, ?CallbackAlloc@FdiCallbacks@@SAPEAXK@Z; pfnalloc
0x1800086ea  call    cs:__imp_FDICreate
0x1800086f0  mov     [rsp+1A0h+hfdi], rax
0x1800086f5  test    rax, rax
0x1800086f8  jnz     loc_18000879A
0x1800086fe  mov     ebx, [rsp+1A0h+perf.erfOper]
0x180008702  lea     eax, [rbx-1]
0x180008705  cmp     eax, 0Ah
0x180008708  ja      short loc_180008714
0x18000870a  add     ebx, 801882E0h
0x180008710  jns     short loc_180008735
0x180008712  jmp     short loc_180008719
0x180008714  mov     ebx, 801882EFh
0x180008719  mov     edx, 134h; void *
0x18000871e  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x180008725  mov     r9d, ebx; char *
0x180008728  mov     rcx, [rbp+0A8h]; this
0x18000872f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008734  nop
0x180008735  lea     rcx, [rsp+1A0h+var_128]
0x18000873a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000873f  nop
0x180008740  lea     rcx, [rbp+0A0h+WideCharStr]
0x180008744  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008749  nop
0x18000874a  lea     rcx, [rbp+0A0h+var_60]
0x18000874e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008753  lea     rcx, [rbp+0A0h+var_80]
0x180008757  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000875c  lea     rcx, [rbp+0A0h+var_A0]
0x180008760  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008765  lea     rcx, [rbp+0A0h+var_B0]
0x180008769  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18000876e  lea     rcx, [rbp+0A0h+var_C0]
0x180008772  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x180008777  lea     rcx, [rbp+0A0h+var_D0]
0x18000877b  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x180008780  nop
0x180008781  mov     rcx, [rsp+1A0h+hfdi]; hfdi
0x180008786  test    rcx, rcx
0x180008789  jz      loc_18000860B
0x18000878f  call    cs:__imp_FDIDestroy
0x180008795  jmp     loc_18000860B
0x18000879a  lea     rdx, [rbp+0A0h+WideCharStr]
0x18000879e  lea     rcx, [rbp+0A0h+pvUser]
0x1800087a2  call    ?ConvertPointerToString@Utils@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Utils::ConvertPointerToString(void *,std::wstring *)
0x1800087a7  mov     ebx, eax
0x1800087a9  test    eax, eax
0x1800087ab  jns     short loc_1800087B7
0x1800087ad  mov     edx, 136h
0x1800087b2  jmp     loc_18000871E
0x1800087b7  lea     rdx, [rsp+1A0h+var_128]; void *
0x1800087bc  lea     rcx, [rbp+0A0h+WideCharStr]; lpWideCharStr
0x1800087c0  call    ?ConvertUnicodeToMultiByte@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; Utils::ConvertUnicodeToMultiByte(std::wstring const &,std::string *)
0x1800087c5  mov     ebx, eax
0x1800087c7  test    eax, eax
0x1800087c9  jns     short loc_1800087D5
0x1800087cb  mov     edx, 138h
0x1800087d0  jmp     loc_18000871E
0x1800087d5  lea     rdx, [rsp+1A0h+var_128]
0x1800087da  cmp     qword ptr [rbp+0A0h+var_118+8], 0Fh
0x1800087df  cmova   rdx, qword ptr [rsp+1A0h+var_128]; pszCabinet
0x1800087e5  lea     rax, [rbp+0A0h+pvUser]
0x1800087e9  mov     [rsp+1A0h+pfnseek], rax; pvUser
0x1800087ee  mov     [rsp+1A0h+pfnclose], 0; pfnfdid
0x1800087f7  lea     rax, ?CallbackFDINotify@FdiCallbacks@@SA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; FdiCallbacks::CallbackFDINotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x1800087fe  mov     [rsp+1A0h+pfnwrite], rax; pfnfdin
0x180008803  xor     r9d, r9d; flags
0x180008806  lea     r8, pszCabPath; pszCabPath
0x18000880d  mov     rcx, [rsp+1A0h+hfdi]; hfdi
0x180008812  call    cs:__imp_FDICopy
0x180008818  test    eax, eax
0x18000881a  jnz     short loc_180008838
0x18000881c  mov     ebx, [rsp+1A0h+perf.erfOper]
0x180008820  lea     eax, [rbx-1]
0x180008823  cmp     eax, 0Ah
0x180008826  ja      loc_1800088C6
0x18000882c  add     ebx, 801882E0h
0x180008832  js      loc_1800088CB
0x180008838  mov     rdx, rsi
0x18000883b  lea     rcx, [rbp+0A0h+pvUser]
0x18000883f  call    ?IsSelected@CabContext@@QEBAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; CabContext::IsSelected(std::wstring const &)
0x180008844  mov     [rdi], eax
0x180008846  lea     rcx, [rsp+1A0h+var_128]
0x18000884b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180008850  nop
0x180008851  lea     rcx, [rbp+0A0h+WideCharStr]
0x180008855  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000885a  nop
0x18000885b  lea     rcx, [rbp+0A0h+var_60]
0x18000885f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008864  lea     rcx, [rbp+0A0h+var_80]
0x180008868  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000886d  lea     rcx, [rbp+0A0h+var_A0]
0x180008871  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008876  lea     rcx, [rbp+0A0h+var_B0]
0x18000887a  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18000887f  lea     rcx, [rbp+0A0h+var_C0]
0x180008883  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x180008888  lea     rcx, [rbp+0A0h+var_D0]
0x18000888c  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KUWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x180008891  nop
0x180008892  mov     rcx, [rsp+1A0h+hfdi]; hfdi
0x180008897  test    rcx, rcx
0x18000889a  jz      short loc_1800088A2
0x18000889c  call    cs:__imp_FDIDestroy
0x1800088a2  xor     eax, eax
0x1800088a4  mov     rcx, [rbp+0A0h+var_20]
0x1800088ab  xor     rcx, rsp; StackCookie
0x1800088ae  call    __security_check_cookie
0x1800088b3  mov     rbx, [rsp+1A0h+arg_18]
0x1800088bb  add     rsp, 190h
0x1800088c2  pop     rdi
0x1800088c3  pop     rsi
0x1800088c4  pop     rbp
0x1800088c5  retn
0x1800088c6  mov     ebx, 801882EFh
0x1800088cb  mov     edx, 145h
0x1800088d0  jmp     loc_18000871E
```
