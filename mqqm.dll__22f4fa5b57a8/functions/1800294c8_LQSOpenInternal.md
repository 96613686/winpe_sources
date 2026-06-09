# LQSOpenInternal

- ea: `0x1800294c8`
- end: `0x180029949`
- name: `LQSOpenInternal`
- size: `1153`
- prototype: `__int64 __usercall@<rax>(wchar_t *Str@<rcx>, wchar_t *)`
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180029138`
- `0x180029268`
- `0x180029394`

## callees

- `0x18000bab8`
- `0x18000cb80`
- `0x18000d1f0`
- `0x180011578`
- `0x1800261a4`
- `0x1800261e0`
- `0x180027780`
- `0x1800280a8`
- `0x1800287a4`
- `0x1800294c8`
- `0x18002a424`
- `0x18002c61c`
- `0x1800cff88`
- `0x1800d6e56`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x180029716`
- `msvcrt!free` at `0x18002977b`
- `msvcrt!free` at `0x180029817`
- `msvcrt!free` at `0x180029836`
- `msvcrt!free` at `0x180029886`
- `msvcrt!free` at `0x1800298ac`
- `msvcrt!free` at `0x180029716`
- `msvcrt!free` at `0x18002977b`
- `msvcrt!free` at `0x180029817`
- `msvcrt!free` at `0x180029836`
- `msvcrt!free` at `0x180029886`
- `msvcrt!free` at `0x1800298ac`
- `KERNEL32!GetLastError` at `0x18002984b`
- `KERNEL32!GetLastError` at `0x18002984b`
- `KERNEL32!CompareStringW` at `0x1800296a9`
- `KERNEL32!CompareStringW` at `0x1800296a9`
- `KERNEL32!FindFirstFileW` at `0x180029545`
- `KERNEL32!FindFirstFileW` at `0x180029545`
- `KERNEL32!FindNextFileW` at `0x18002976a`
- `KERNEL32!FindNextFileW` at `0x18002976a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LQSOpenInternal(wchar_t *Str, const WCHAR *a2, int a3, _QWORD *a4, wchar_t *a5)
{
  int CachedFilename; // r12d
  __int64 FirstFileW; // rdi
  int v8; // esi
  unsigned int v9; // ebx
  wchar_t *v10; // rax
  int v11; // eax
  int v12; // ebx
  int v13; // eax
  wchar_t *bstrVal; // rbx
  unsigned int v15; // r15d
  wchar_t *v16; // rax
  int v17; // eax
  wchar_t *v18; // rsi
  unsigned __int16 v19; // r8
  __int64 v20; // rax
  signed int LastError; // eax
  void *v23; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+38h] [rbp-C8h]
  unsigned int v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  PCNZWCH lpString2; // [rsp+50h] [rbp-B0h]
  _QWORD *v28; // [rsp+58h] [rbp-A8h]
  struct tagPROPVARIANT v29; // [rsp+60h] [rbp-A0h] BYREF
  LARGE_INTEGER hVal; // [rsp+78h] [rbp-88h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF
  wchar_t v32[312]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v28 = a4;
  v24 = a3;
  lpString2 = a2;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  CachedFilename = LQSpGetCachedFilename(Str, v32);
  FirstFileW = -1;
  v26 = -1;
  if ( CachedFilename || (FirstFileW = (__int64)FindFirstFileW(Str, &FindFileData), v26 = FirstFileW, FirstFileW != -1) )
  {
    while ( 1 )
    {
      v23 = 0;
      if ( !CachedFilename )
      {
        v9 = 306 - mqwcslen(v32);
        v10 = (wchar_t *)LQSGetDirectory(v32);
        v11 = StringCchCopyW(v10, v9, FindFileData.cFileName);
        v8 = v11;
        if ( v11 < 0 )
        {
          v19 = 5840;
LABEL_27:
          LogMsgHR(v11, (wchar_t *)L"lqs", v19);
          goto LABEL_38;
        }
      }
      if ( a5 )
      {
        v11 = StringCchCopyW(a5, 0x132u, v32);
        v8 = v11;
        if ( v11 < 0 )
        {
          v19 = 5850;
          goto LABEL_27;
        }
      }
      v12 = LQSCreateHandle_0(0, v32);
      if ( v12 < 0 )
        break;
      v25[0] = 103;
      v29.hVal.QuadPart = 0;
      v29.vt = 1;
      v13 = LQSGetProperties(v23, 1u, v25, &v29, 1);
      bstrVal = v29.bstrVal;
      hVal = v29.hVal;
      if ( v13 < 0 )
      {
        if ( v13 == -1072824216 )
        {
          v18 = v32;
          if ( v29.hVal.QuadPart && mqwcslen(v29.bstrVal) > 1 )
            v18 = v29.bstrVal;
          EvReport(0xC00E0068, 2u, FindFileData.cFileName, v18);
        }
      }
      else if ( !lpString2 || CompareStringW(0x7Fu, 1u, v29.bstrVal, -1, lpString2, -1) == 2 )
      {
        *(_QWORD *)v25 = 0;
        if ( CachedFilename
          || (v15 = 306 - mqwcslen(v32),
              v16 = (wchar_t *)LQSGetDirectory(v32),
              v17 = StringCchCopyW(v16, v15, FindFileData.cFileName),
              v8 = v17,
              v17 >= 0) )
        {
          v8 = LQSCreateHandle_0(bstrVal, v32);
          if ( v8 >= 0 )
          {
            v20 = *(_QWORD *)v25;
            ++*(_DWORD *)(*(_QWORD *)v25 + 24LL);
            *v28 = v20;
            free(bstrVal);
            P<_HLQS>::~P<_HLQS>(&v23);
            v8 = 0;
            goto LABEL_39;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids);
          LogMsgHR(v8, (wchar_t *)L"lqs", 0x493u);
          free(bstrVal);
        }
        else
        {
          LogMsgHR(v17, (wchar_t *)L"lqs", 0x16E4u);
          free(bstrVal);
        }
        goto LABEL_38;
      }
      if ( CachedFilename )
        goto LABEL_37;
      if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
      {
        LastError = GetLastError();
        if ( LastError < 0 )
          LogMsgHR(LastError, (wchar_t *)L"lqs", 0xBEu);
LABEL_37:
        v8 = -1072824317;
        LogMsgHR(-1072824317, (wchar_t *)L"lqs", 0x495u);
        free(bstrVal);
LABEL_38:
        P<_HLQS>::~P<_HLQS>(&v23);
        goto LABEL_39;
      }
      free(bstrVal);
      P<_HLQS>::~P<_HLQS>(&v23);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids);
    LogMsgHR(v12, (wchar_t *)L"lqs", 0x48Au);
    P<_HLQS>::~P<_HLQS>(&v23);
    CAutoCloseFindFile::~CAutoCloseFindFile((CAutoCloseFindFile *)&v26);
    return (unsigned int)v12;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && ((unsigned __int8)(CachedFilename + 2) & *((_BYTE *)WPP_GLOBAL_Control + 28)) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
    v8 = -1072824317;
    LogMsgHR(-1072824317, (wchar_t *)L"lqs", 0x489u);
LABEL_39:
    CAutoCloseFindFile::~CAutoCloseFindFile((CAutoCloseFindFile *)&v26);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x1800294c8  push    rbp
0x1800294ca  push    rbx
0x1800294cb  push    rsi
0x1800294cc  push    rdi
0x1800294cd  push    r12
0x1800294cf  push    r13
0x1800294d1  push    r14
0x1800294d3  push    r15
0x1800294d5  lea     rbp, [rsp-458h]
0x1800294dd  sub     rsp, 558h
0x1800294e4  mov     rax, cs:__security_cookie
0x1800294eb  xor     rax, rsp
0x1800294ee  mov     [rbp+490h+var_50], rax
0x1800294f5  mov     [rsp+590h+var_538], r9
0x1800294fa  mov     [rsp+590h+var_558], r8d
0x1800294ff  mov     [rsp+590h+var_540], rdx
0x180029504  mov     rbx, rcx
0x180029507  mov     r13, [rbp+490h+arg_20]
0x18002950e  xor     edx, edx; Val
0x180029510  mov     r8d, 250h; Size
0x180029516  lea     rcx, [rbp+490h+FindFileData]; void *
0x18002951a  call    memset_0
0x18002951f  lea     rdx, [rbp+490h+var_2C0]; wchar_t *
0x180029526  mov     rcx, rbx; Str
0x180029529  call    ?LQSpGetCachedFilename@@YAHPEB_WPEA_W@Z; LQSpGetCachedFilename(wchar_t const *,wchar_t *)
0x18002952e  mov     r12d, eax
0x180029531  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180029535  mov     [rsp+590h+var_548], rdi
0x18002953a  test    eax, eax
0x18002953c  jnz     short loc_1800295AB
0x18002953e  lea     rdx, [rbp+490h+FindFileData]; lpFindFileData
0x180029542  mov     rcx, rbx; lpFileName
0x180029545  call    cs:__imp_FindFirstFileW
0x18002954b  mov     rdi, rax
0x18002954e  mov     [rsp+590h+var_548], rax
0x180029553  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029557  jnz     short loc_1800295AB
0x180029559  lea     rax, WPP_GLOBAL_Control
0x180029560  mov     rcx, cs:WPP_GLOBAL_Control
0x180029567  cmp     rcx, rax
0x18002956a  jz      short loc_18002958D
0x18002956c  lea     r14d, [r12+2]
0x180029571  test    [rcx+1Ch], r14b
0x180029575  jz      short loc_18002958D
0x180029577  lea     edx, [rdi+1Fh]
0x18002957a  mov     r9, rbx
0x18002957d  lea     r8, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids
0x180029584  mov     rcx, [rcx+10h]; LoggerHandle
0x180029588  call    WPP_SF_S
0x18002958d  mov     r8d, 489h; unsigned __int16
0x180029593  lea     rdx, aLqs_0; "lqs"
0x18002959a  mov     esi, 0C00E0003h
0x18002959f  mov     ecx, esi; int
0x1800295a1  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800295a6  jmp     loc_1800298BE
0x1800295ab  mov     r14d, 2
0x1800295b1  mov     r15d, 132h
0x1800295b7  mov     [rsp+590h+var_560], 0
0x1800295c0  test    r12d, r12d
0x1800295c3  jnz     short loc_1800295FA
0x1800295c5  lea     rcx, [rbp+490h+var_2C0]; wchar_t *
0x1800295cc  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800295d1  mov     ebx, r15d
0x1800295d4  sub     ebx, eax
0x1800295d6  lea     rcx, [rbp+490h+var_2C0]; wchar_t *
0x1800295dd  call    LQSGetDirectory
0x1800295e2  lea     r8, [rbp+490h+FindFileData.cFileName]; wchar_t *
0x1800295e6  mov     edx, ebx; unsigned __int64
0x1800295e8  mov     rcx, rax; wchar_t *
0x1800295eb  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800295f0  mov     esi, eax
0x1800295f2  test    eax, eax
0x1800295f4  js      loc_180029791
0x1800295fa  test    r13, r13
0x1800295fd  jz      short loc_18002961B
0x1800295ff  lea     r8, [rbp+490h+var_2C0]; wchar_t *
0x180029606  mov     rdx, r15; unsigned __int64
0x180029609  mov     rcx, r13; wchar_t *
0x18002960c  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180029611  mov     esi, eax
0x180029613  test    eax, eax
0x180029615  js      loc_1800297AA
0x18002961b  lea     r9, [rsp+590h+var_560]
0x180029620  mov     r8d, [rsp+590h+var_558]
0x180029625  lea     rdx, [rbp+490h+var_2C0]; wchar_t *
0x18002962c  xor     ecx, ecx; wchar_t *
0x18002962e  call    LQSCreateHandle_0
0x180029633  mov     ebx, eax
0x180029635  test    eax, eax
0x180029637  js      loc_1800298CC
0x18002963d  mov     [rsp+590h+var_550], 67h ; 'g'
0x180029645  mov     qword ptr [rsp+590h+var_530+8], 0
0x18002964e  mov     esi, 1
0x180029653  mov     word ptr [rsp+590h+var_530], si
0x180029658  mov     dword ptr [rsp+590h+lpString2], esi; int
0x18002965c  lea     r9, [rsp+590h+var_530]; struct tagPROPVARIANT *
0x180029661  lea     r8, [rsp+590h+var_550]; unsigned int *
0x180029666  mov     edx, esi; unsigned int
0x180029668  mov     rcx, [rsp+590h+var_560]; void *
0x18002966d  call    ?LQSGetProperties@@YAJPEAXKQEAKQEAUtagPROPVARIANT@@H@Z; LQSGetProperties(void *,ulong,ulong * const,tagPROPVARIANT * const,int)
0x180029672  mov     rbx, qword ptr [rsp+590h+var_530+8]
0x180029677  mov     [rsp+590h+var_518], rbx
0x18002967c  test    eax, eax
0x18002967e  js      loc_180029722
0x180029684  mov     rsi, [rsp+590h+var_540]
0x180029689  test    rsi, rsi
0x18002968c  jz      short loc_1800296B8
0x18002968e  mov     [rsp+590h+cchCount2], 0FFFFFFFFh; cchCount2
0x180029696  mov     [rsp+590h+lpString2], rsi; lpString2
0x18002969b  or      r9d, 0FFFFFFFFh; cchCount1
0x18002969f  mov     r8, rbx; lpString1
0x1800296a2  lea     edx, [r9+2]; dwCmpFlags
0x1800296a6  lea     ecx, [rdx+7Eh]; Locale
0x1800296a9  call    cs:__imp_CompareStringW
0x1800296af  cmp     eax, r14d
0x1800296b2  jnz     loc_18002975A
0x1800296b8  mov     qword ptr [rsp+590h+var_550], 0
0x1800296c1  test    r12d, r12d
0x1800296c4  jnz     loc_1800297B2
0x1800296ca  lea     rcx, [rbp+490h+var_2C0]; wchar_t *
0x1800296d1  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800296d6  sub     r15d, eax
0x1800296d9  lea     rcx, [rbp+490h+var_2C0]; wchar_t *
0x1800296e0  call    LQSGetDirectory
0x1800296e5  lea     r8, [rbp+490h+FindFileData.cFileName]; wchar_t *
0x1800296e9  mov     edx, r15d; unsigned __int64
0x1800296ec  mov     rcx, rax; wchar_t *
0x1800296ef  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800296f4  mov     esi, eax
0x1800296f6  test    eax, eax
0x1800296f8  jns     loc_1800297B2
0x1800296fe  mov     r8d, 16E4h; unsigned __int16
0x180029704  lea     rdx, aLqs_0; "lqs"
0x18002970b  mov     ecx, eax; int
0x18002970d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029712  nop
0x180029713  mov     rcx, rbx; Block
0x180029716  call    cs:__imp_free
0x18002971c  nop
0x18002971d  jmp     loc_1800298B3
0x180029722  cmp     eax, 0C00E0068h
0x180029727  jnz     short loc_18002975A
0x180029729  lea     rsi, [rbp+490h+var_2C0]
0x180029730  test    rbx, rbx
0x180029733  jz      short loc_180029746
0x180029735  mov     rcx, rbx; wchar_t *
0x180029738  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18002973d  cmp     eax, 1
0x180029740  cmova   rsi, qword ptr [rsp+590h+var_530+8]
0x180029746  mov     r9, rsi
0x180029749  lea     r8, [rbp+490h+FindFileData.cFileName]
0x18002974d  mov     edx, r14d; unsigned __int16
0x180029750  mov     ecx, 0C00E0068h; unsigned int
0x180029755  call    ?EvReport@@YAXKGZZ; EvReport(ulong,ushort,...)
0x18002975a  test    r12d, r12d
0x18002975d  jnz     loc_18002988F
0x180029763  lea     rdx, [rbp+490h+FindFileData]; lpFindFileData
0x180029767  mov     rcx, rdi; hFindFile
0x18002976a  call    cs:__imp_FindNextFileW
0x180029770  test    eax, eax
0x180029772  jz      loc_18002984B
0x180029778  mov     rcx, rbx; Block
0x18002977b  call    cs:__imp_free
0x180029781  nop
0x180029782  lea     rcx, [rsp+590h+var_560]
0x180029787  call    ??1?$P@V_HLQS@@@@QEAA@XZ; P<_HLQS>::~P<_HLQS>(void)
0x18002978c  jmp     loc_1800295B7
0x180029791  mov     r8d, 16D0h; unsigned __int16
0x180029797  lea     rdx, aLqs_0; "lqs"
0x18002979e  mov     ecx, eax; int
0x1800297a0  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800297a5  jmp     loc_1800298B3
0x1800297aa  mov     r8d, 16DAh
0x1800297b0  jmp     short loc_180029797
0x1800297b2  lea     r9, [rsp+590h+var_550]
0x1800297b7  mov     r8d, [rsp+590h+var_558]
0x1800297bc  lea     rdx, [rbp+490h+var_2C0]; wchar_t *
0x1800297c3  mov     rcx, rbx; wchar_t *
0x1800297c6  call    LQSCreateHandle_0
0x1800297cb  mov     esi, eax
0x1800297cd  test    eax, eax
0x1800297cf  jns     short loc_180029823
0x1800297d1  lea     rax, WPP_GLOBAL_Control
0x1800297d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297df  cmp     rcx, rax
0x1800297e2  jz      short loc_1800297FF
0x1800297e4  test    byte ptr [rcx+1Ch], 1
0x1800297e8  jz      short loc_1800297FF
0x1800297ea  mov     edx, 20h ; ' '
0x1800297ef  lea     r8, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids
0x1800297f6  mov     rcx, [rcx+10h]
0x1800297fa  call    WPP_SF_
0x1800297ff  mov     r8d, 493h; unsigned __int16
0x180029805  lea     rdx, aLqs_0; "lqs"
0x18002980c  mov     ecx, esi; int
0x18002980e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029813  nop
0x180029814  mov     rcx, rbx; Block
0x180029817  call    cs:__imp_free
0x18002981d  nop
0x18002981e  jmp     loc_1800298B3
0x180029823  mov     rax, qword ptr [rsp+590h+var_550]
0x180029828  inc     dword ptr [rax+18h]
0x18002982b  mov     rcx, [rsp+590h+var_538]
0x180029830  mov     [rcx], rax
0x180029833  mov     rcx, rbx; Block
0x180029836  call    cs:__imp_free
0x18002983c  nop
0x18002983d  lea     rcx, [rsp+590h+var_560]
0x180029842  call    ??1?$P@V_HLQS@@@@QEAA@XZ; P<_HLQS>::~P<_HLQS>(void)
0x180029847  xor     esi, esi
0x180029849  jmp     short loc_1800298BE
0x18002984b  call    cs:__imp_GetLastError
0x180029851  test    eax, eax
0x180029853  jns     short loc_180029869
0x180029855  mov     r8d, 0BEh; unsigned __int16
0x18002985b  lea     rdx, aLqs_0; "lqs"
0x180029862  mov     ecx, eax; int
0x180029864  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029869  mov     r8d, 495h; unsigned __int16
0x18002986f  lea     rdx, aLqs_0; "lqs"
0x180029876  mov     esi, 0C00E0003h
0x18002987b  mov     ecx, esi; int
0x18002987d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029882  nop
0x180029883  mov     rcx, rbx; Block
0x180029886  call    cs:__imp_free
0x18002988c  nop
0x18002988d  jmp     short loc_1800298B3
0x18002988f  mov     r8d, 495h; unsigned __int16
0x180029895  lea     rdx, aLqs_0; "lqs"
0x18002989c  mov     esi, 0C00E0003h
0x1800298a1  mov     ecx, esi; int
0x1800298a3  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800298a8  nop
0x1800298a9  mov     rcx, rbx; Block
0x1800298ac  call    cs:__imp_free
0x1800298b2  nop
0x1800298b3  lea     rcx, [rsp+590h+var_560]
0x1800298b8  call    ??1?$P@V_HLQS@@@@QEAA@XZ; P<_HLQS>::~P<_HLQS>(void)
0x1800298bd  nop
0x1800298be  lea     rcx, [rsp+590h+var_548]; this
0x1800298c3  call    ??1CAutoCloseFindFile@@QEAA@XZ; CAutoCloseFindFile::~CAutoCloseFindFile(void)
0x1800298c8  mov     eax, esi
0x1800298ca  jmp     short loc_180029926
0x1800298cc  lea     rax, WPP_GLOBAL_Control
0x1800298d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800298da  cmp     rcx, rax
0x1800298dd  jz      short loc_1800298FA
0x1800298df  test    byte ptr [rcx+1Ch], 1
0x1800298e3  jz      short loc_1800298FA
0x1800298e5  mov     edx, 1Fh
0x1800298ea  lea     r8, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids
0x1800298f1  mov     rcx, [rcx+10h]
0x1800298f5  call    WPP_SF_
0x1800298fa  mov     r8d, 48Ah; unsigned __int16
0x180029900  lea     rdx, aLqs_0; "lqs"
0x180029907  mov     ecx, ebx; int
0x180029909  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002990e  nop
0x18002990f  lea     rcx, [rsp+590h+var_560]
0x180029914  call    ??1?$P@V_HLQS@@@@QEAA@XZ; P<_HLQS>::~P<_HLQS>(void)
0x180029919  nop
0x18002991a  lea     rcx, [rsp+590h+var_548]; this
0x18002991f  call    ??1CAutoCloseFindFile@@QEAA@XZ; CAutoCloseFindFile::~CAutoCloseFindFile(void)
0x180029924  mov     eax, ebx
0x180029926  mov     rcx, [rbp+490h+var_50]
0x18002992d  xor     rcx, rsp; StackCookie
0x180029930  call    __security_check_cookie
0x180029935  add     rsp, 558h
0x18002993c  pop     r15
0x18002993e  pop     r14
0x180029940  pop     r13
0x180029942  pop     r12
0x180029944  pop     rdi
0x180029945  pop     rsi
0x180029946  pop     rbx
0x180029947  pop     rbp
0x180029948  retn
```
