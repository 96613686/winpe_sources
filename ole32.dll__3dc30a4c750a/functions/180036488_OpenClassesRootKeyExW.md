# OpenClassesRootKeyExW

- ea: `0x180036488`
- end: `0x18003679e`
- name: `OpenClassesRootKeyExW`
- size: `790`
- prototype: `int __fastcall(const wchar_t *pszSubKey, unsigned int samDesired, HKEY__ **phkResult)`
- caller_count: `15`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800478bc`
- `0x180048e9c`
- `0x18004d258`
- `0x18004f860`
- `0x18004fb0c`
- `0x180066370`
- `0x180066678`
- `0x18007e360`
- `0x180099274`
- `0x18009ab30`
- `0x1800a89c0`
- `0x1800ad620`
- `0x1800b0a68`
- `0x1800b80b8`
- `0x1800bf6c4`

## callees

- `0x18002c774`
- `0x18002c9f0`
- `0x180036488`
- `0x180041fc8`
- `0x180047540`
- `0x18005315c`
- `0x180053168`
- `0x1800533e7`
- `0x180059088`
- `0x18008be08`
- `0x1800bdc98`
- `0x1800bf140`
- `0x1800bf5bc`
- `0x1800bf7a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003650a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003650a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003666c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003666c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800365cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800365cd`
- `KERNEL32!RegOpenUserClassesRoot` at `0x18003655a`
- `KERNEL32!RegOpenUserClassesRoot` at `0x18003655a`

## string_xrefs

- `0x1800365a1`: `onecore\com\published\comutils\reghelp.cxx`
- `0x180036613`: `onecore\com\published\comutils\reghelp.cxx`
- `0x1800366ca`: `onecore\com\published\comutils\reghelp.cxx`
- `0x18003658f`: `OpenClassesRootKeyExW`
- `0x180036604`: `OpenClassesRootKeyExW`
- `0x1800366c3`: `OpenClassesRootKeyExW`

## pseudocode

```c
__int64 __fastcall OpenClassesRootKeyExW(const wchar_t *pszSubKey, unsigned int samDesired, HKEY__ **phkResult)
{
  int v7; // esi
  HKEY__ *v8; // rax
  unsigned int format; // ebx
  HANDLE CurrentProcess_0; // rax
  int v11; // eax
  LSTATUS v12; // eax
  TraceLevel v13; // r9d
  LSTATUS v14; // eax
  unsigned __int64 v15; // rdx
  unsigned __int8 v16; // cl
  TraceLevel v17; // r9d
  wil::details::static_lazy<ComTrace> *v18; // rcx
  ComTrace *v19; // rax
  unsigned int v20; // r8d
  TraceLevel v21; // r9d
  const char *v22; // rdx
  const char *v23; // rcx
  unsigned int v24; // r8d
  TraceLevel v25; // r9d
  unsigned int v26; // eax
  const wchar_t *hKey; // [rsp+20h] [rbp-30h]
  unsigned __int16 *file; // [rsp+28h] [rbp-28h]
  unsigned __int16 *filea; // [rsp+28h] [rbp-28h]
  void *hProcToken; // [rsp+40h] [rbp-10h] BYREF
  void *hImpToken; // [rsp+48h] [rbp-8h] BYREF
  int fIsUserHiveOK; // [rsp+A0h] [rbp+50h] BYREF
  HKEY__ *hkcr; // [rsp+A8h] [rbp+58h] BYREF

  hImpToken = 0;
  hProcToken = 0;
  hkcr = 0;
  if ( !phkResult )
    return 87;
  *phkResult = 0;
  v7 = 512;
  if ( pszSubKey )
  {
    if ( *pszSubKey )
    {
      v8 = cachedHKCR;
      if ( cachedHKCR )
      {
        format = 0;
        hkcr = cachedHKCR;
        goto LABEL_38;
      }
    }
  }
  RegHelpSuspendImpersonate(&hImpToken);
  CurrentProcess_0 = GetCurrentProcess_0();
  if ( OpenProcessToken(CurrentProcess_0, 8u, &hProcToken) )
  {
    fIsUserHiveOK = 0;
    if ( (g_GLBOPT_RoFlags & 0x100) == 0 )
    {
      v11 = IsUserHiveOK(hProcToken, &fIsUserHiveOK);
      if ( v11 < 0 )
      {
        format = (unsigned __int16)v11;
LABEL_31:
        CloseHandle_0(hProcToken);
        goto LABEL_36;
      }
      if ( fIsUserHiveOK )
      {
        v12 = RegOpenUserClassesRoot(hProcToken, 0, 0x2000000u, &hkcr);
        format = v12;
        if ( !v12 )
          goto LABEL_27;
        if ( v12 != 2
          && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS)) )
        {
          ComTraceMessageT<long>(
            "onecore\\com\\published\\comutils\\reghelp.cxx",
            "OpenClassesRootKeyExW",
            491,
            v13,
            L"%!WINERROR!",
            format);
        }
      }
    }
    v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes", 0, 0x2000000u, &hkcr);
    format = v14;
    if ( v14 )
    {
      if ( v14 != 2 )
      {
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
          ComTraceMessageT<long>(
            "onecore\\com\\published\\comutils\\reghelp.cxx",
            "OpenClassesRootKeyExW",
            512,
            v17,
            L"%!WINERROR!",
            format);
        if ( format == 5 && ComTrace::IsEnabled(v16, v15) )
        {
          v19 = wil::details::static_lazy<ComTrace>::get(
                  v18,
                  _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_);
          ComTrace::LogTokenInfoImp(v19, hProcToken, v20);
        }
      }
      goto LABEL_31;
    }
LABEL_27:
    if ( pszSubKey
      && *pszSubKey
      && _InterlockedCompareExchange64((volatile signed __int64 *)&cachedHKCR, (signed __int64)hkcr, 0) )
    {
      RegCloseKey(hkcr);
      hkcr = cachedHKCR;
    }
    goto LABEL_31;
  }
  format = GetLastError_0();
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    ComTraceMessageT<long>(
      "onecore\\com\\published\\comutils\\reghelp.cxx",
      "OpenClassesRootKeyExW",
      548,
      v21,
      L"%!WINERROR!",
      format);
LABEL_36:
  RegHelpResumeImpersonate(hImpToken);
  if ( !format )
  {
    v8 = hkcr;
    if ( !pszSubKey )
    {
LABEL_49:
      *phkResult = v8;
      return format;
    }
LABEL_38:
    if ( *pszSubKey )
    {
      format = RegOpenOtherKeyExW(v8, pszSubKey, (unsigned int)phkResult, samDesired, phkResult, file);
      if ( format == 2 )
      {
        v26 = samDesired & 0x300;
        if ( ((samDesired & 0x300) == 0 || (v7 = v26 ^ 0x300) != 0)
          && !RegOpenOtherKeyExW(hkcr, pszSubKey, v24, samDesired | v7, phkResult, filea) )
        {
          return 0;
        }
      }
      else if ( format
             && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS)) )
      {
        ComTraceMessageT<unsigned short const *,unsigned long,long>(
          v23,
          v22,
          v24,
          v25,
          hKey,
          pszSubKey,
          samDesired,
          format);
      }
      return format;
    }
    goto LABEL_49;
  }
  return format;
}

```

## disassembly

```asm
0x180036488  mov     [rsp-38h+arg_0], rbx
0x18003648d  push    rbp
0x18003648e  push    rsi
0x18003648f  push    rdi
0x180036490  push    r12
0x180036492  push    r13
0x180036494  push    r14
0x180036496  push    r15
0x180036498  mov     rbp, rsp
0x18003649b  sub     rsp, 50h
0x18003649f  xor     r13d, r13d
0x1800364a2  mov     r14, phkResult
0x1800364a5  mov     [rbp+hImpToken], r13
0x1800364a9  mov     r12d, samDesired
0x1800364ac  mov     [rbp+hProcToken], r13
0x1800364b0  mov     rdi, pszSubKey
0x1800364b3  mov     [rbp+hkcr], r13
0x1800364b7  test    phkResult, phkResult
0x1800364ba  jnz     short loc_1800364C5
0x1800364bc  lea     eax, [phkResult+57h]
0x1800364c0  jmp     loc_180036786
0x1800364c5  mov     [phkResult], r13
0x1800364c8  mov     esi, 200h
0x1800364cd  test    rdi, rdi
0x1800364d0  jz      short loc_1800364F0
0x1800364d2  cmp     [pszSubKey], r13w
0x1800364d6  jz      short loc_1800364F0
0x1800364d8  mov     rax, cs:?cachedHKCR@@3PEAUHKEY__@@EA; HKEY__ * cachedHKCR
0x1800364df  test    rax, rax
0x1800364e2  jz      short loc_1800364F0
0x1800364e4  mov     ebx, r13d
0x1800364e7  mov     [rbp+hkcr], rax
0x1800364eb  jmp     loc_1800366F4
0x1800364f0  lea     pszSubKey, [rbp+hImpToken]; pHandle
0x1800364f4  call    ?RegHelpSuspendImpersonate@@YAJPEAPEAX@Z; RegHelpSuspendImpersonate(void * *)
0x1800364f9  call    GetCurrentProcess_0
0x1800364fe  mov     pszSubKey, rax; ProcessHandle
0x180036501  lea     phkResult, [rbp+hProcToken]; TokenHandle
0x180036505  mov     samDesired, 8; DesiredAccess
0x18003650a  call    cs:__imp_OpenProcessToken
0x180036510  test    eax, eax
0x180036512  jz      loc_180036688
0x180036518  test    cs:?g_GLBOPT_RoFlags@@3KA, 100h; ulong g_GLBOPT_RoFlags
0x180036522  lea     r15, aWinerror; "%!WINERROR!"
0x180036529  mov     [rbp+fIsUserHiveOK], r13d
0x18003652d  jnz     short loc_1800365AD
0x18003652f  mov     pszSubKey, [rbp+hProcToken]; hToken
0x180036533  lea     rdx, [rbp+fIsUserHiveOK]; fOK
0x180036537  call    IsUserHiveOK
0x18003653c  test    eax, eax
0x18003653e  js      loc_180036647
0x180036544  cmp     [rbp+fIsUserHiveOK], r13d
0x180036548  jz      short loc_1800365AD
0x18003654a  mov     pszSubKey, [rbp+hProcToken]; hToken
0x18003654e  lea     r9, [rbp+hkcr]; phkResult
0x180036552  xor     samDesired, samDesired; dwOptions
0x180036554  mov     r8d, 2000000h; samDesired
0x18003655a  call    cs:__imp_RegOpenUserClassesRoot
0x180036560  mov     ebx, eax
0x180036562  test    eax, eax
0x180036564  jz      loc_18003664C
0x18003656a  cmp     eax, 2
0x18003656d  jz      short loc_1800365AD
0x18003656f  mov     ecx, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1; level
0x180036575  test    ecx, ecx
0x180036577  jnz     short loc_18003658B
0x180036579  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x180036580  jz      short loc_1800365AD
0x180036582  call    IsWppLevelEnabled
0x180036587  test    al, al
0x180036589  jz      short loc_1800365AD
0x18003658b  mov     [rsp+50h+file], ebx; file
0x18003658f  lea     rdx, aOpenclassesroo; "OpenClassesRootKeyExW"
0x180036596  mov     r8d, 1EBh; line
0x18003659c  mov     [rsp+50h+hKey], r15; <args_0>
0x1800365a1  lea     pszSubKey, aOnecoreComPubl; "onecore\\com\\published\\comutils\\regh"...
0x1800365a8  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800365ad  lea     rax, [rbp+hkcr]
0x1800365b1  mov     r9d, 2000000h; samDesired
0x1800365b7  xor     r8d, r8d; ulOptions
0x1800365ba  mov     [rsp+50h+hKey], rax; phkResult
0x1800365bf  lea     rdx, aSoftwareClasse; "Software\\Classes"
0x1800365c6  mov     pszSubKey, 0FFFFFFFF80000002h; hKey
0x1800365cd  call    cs:__imp_RegOpenKeyExW
0x1800365d3  mov     ebx, eax
0x1800365d5  test    eax, eax
0x1800365d7  jz      short loc_18003664C
0x1800365d9  cmp     eax, 2
0x1800365dc  jz      loc_18003667D
0x1800365e2  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1800365e8  test    eax, eax
0x1800365ea  jnz     short loc_180036600
0x1800365ec  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800365f3  jz      short loc_18003661F
0x1800365f5  xor     ecx, ecx; level
0x1800365f7  call    IsWppLevelEnabled
0x1800365fc  test    al, al
0x1800365fe  jz      short loc_18003661F
0x180036600  mov     [rsp+50h+file], ebx; file
0x180036604  lea     rdx, aOpenclassesroo; "OpenClassesRootKeyExW"
0x18003660b  mov     r8d, esi; line
0x18003660e  mov     [rsp+50h+hKey], r15; <args_0>
0x180036613  lea     pszSubKey, aOnecoreComPubl; "onecore\\com\\published\\comutils\\regh"...
0x18003661a  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18003661f  cmp     ebx, 5
0x180036622  jnz     short loc_18003667D
0x180036624  call    ?IsEnabled@ComTrace@@SA_NE_K@Z; ComTrace::IsEnabled(uchar,unsigned __int64)
0x180036629  test    al, al
0x18003662b  jz      short loc_18003667D
0x18003662d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f8a79a44bba2ee3470b25df359f31864_@@CA@XZ; cleanupFunc
0x180036634  call    ?get@?$static_lazy@VComTrace@@@details@wil@@QEAAPEAVComTrace@@P6AXXZ@Z; wil::details::static_lazy<ComTrace>::get(void (*)(void))
0x180036639  mov     rdx, [rbp+hProcToken]; token
0x18003663d  mov     pszSubKey, rax; this
0x180036640  call    ?LogTokenInfoImp@ComTrace@@QEAAXPEAXK@Z; ComTrace::LogTokenInfoImp(void *,ulong)
0x180036645  jmp     short loc_18003667D
0x180036647  movzx   ebx, ax
0x18003664a  jmp     short loc_18003667D
0x18003664c  test    rdi, rdi
0x18003664f  jz      short loc_18003667D
0x180036651  cmp     [rdi], r13w
0x180036655  jz      short loc_18003667D
0x180036657  mov     pszSubKey, [rbp+hkcr]
0x18003665b  xor     eax, eax
0x18003665d  lock cmpxchg cs:?cachedHKCR@@3PEAUHKEY__@@EA, pszSubKey; HKEY__ * cachedHKCR
0x180036666  jz      short loc_18003667D
0x180036668  mov     pszSubKey, [rbp+hkcr]; hKey
0x18003666c  call    cs:__imp_RegCloseKey
0x180036672  mov     rax, cs:?cachedHKCR@@3PEAUHKEY__@@EA; HKEY__ * cachedHKCR
0x180036679  mov     [rbp+hkcr], rax
0x18003667d  mov     pszSubKey, [rbp+hProcToken]; hObject
0x180036681  call    CloseHandle_0
0x180036686  jmp     short loc_1800366D6
0x180036688  call    GetLastError_0
0x18003668d  mov     ebx, eax
0x18003668f  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180036695  test    eax, eax
0x180036697  jnz     short loc_1800366AD
0x180036699  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800366a0  jz      short loc_1800366D6
0x1800366a2  xor     ecx, ecx; level
0x1800366a4  call    IsWppLevelEnabled
0x1800366a9  test    al, al
0x1800366ab  jz      short loc_1800366D6
0x1800366ad  lea     r15, aWinerror; "%!WINERROR!"
0x1800366b4  mov     [rsp+50h+file], ebx; lpSubKey
0x1800366b8  mov     r8d, 224h; line
0x1800366be  mov     [rsp+50h+hKey], r15; <args_0>
0x1800366c3  lea     rdx, aOpenclassesroo; "OpenClassesRootKeyExW"
0x1800366ca  lea     pszSubKey, aOnecoreComPubl; "onecore\\com\\published\\comutils\\regh"...
0x1800366d1  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800366d6  mov     pszSubKey, [rbp+hImpToken]; hToken
0x1800366da  call    ?RegHelpResumeImpersonate@@YAXPEAX@Z; RegHelpResumeImpersonate(void *)
0x1800366df  test    ebx, ebx
0x1800366e1  jnz     loc_180036784
0x1800366e7  mov     rax, [rbp+hkcr]
0x1800366eb  test    rdi, rdi
0x1800366ee  jz      loc_180036781
0x1800366f4  cmp     [rdi], r13w
0x1800366f8  jz      loc_180036781
0x1800366fe  mov     r9d, r12d; phkResult
0x180036701  mov     [rsp+50h+hKey], r14; function
0x180036706  mov     rdx, rdi; lpSubKey
0x180036709  mov     pszSubKey, rax; hKey
0x18003670c  call    RegOpenOtherKeyExW
0x180036711  mov     ebx, eax
0x180036713  cmp     eax, 2
0x180036716  jnz     short loc_18003674A
0x180036718  mov     eax, r12d
0x18003671b  mov     ecx, 300h
0x180036720  and     eax, ecx
0x180036722  jz      short loc_18003672A
0x180036724  mov     esi, eax
0x180036726  xor     esi, ecx
0x180036728  jz      short loc_180036784
0x18003672a  mov     pszSubKey, [rbp+hkcr]; hKey
0x18003672e  or      esi, r12d
0x180036731  mov     r9d, esi; phkResult
0x180036734  mov     [rsp+50h+hKey], r14; hKey
0x180036739  mov     rdx, rdi; lpSubKey
0x18003673c  call    RegOpenOtherKeyExW
0x180036741  test    eax, eax
0x180036743  jnz     short loc_180036784
0x180036745  mov     ebx, r13d
0x180036748  jmp     short loc_180036784
0x18003674a  test    ebx, ebx
0x18003674c  jz      short loc_180036784
0x18003674e  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180036754  test    eax, eax
0x180036756  jnz     short loc_18003676C
0x180036758  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x18003675f  jz      short loc_180036784
0x180036761  xor     ecx, ecx; level
0x180036763  call    IsWppLevelEnabled
0x180036768  test    al, al
0x18003676a  jz      short loc_180036784
0x18003676c  mov     [rsp+50h+format], ebx; format
0x180036770  mov     [rsp+50h+level], r12d; level
0x180036775  mov     qword ptr [rsp+50h+file], rdi; line
0x18003677a  call    ??$ComTraceMessageT@PEBGKJ@@YAXPEBD0HW4TraceLevel@@PEBG2KJ@Z; ComTraceMessageT<ushort const *,ulong,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ulong,long)
0x18003677f  jmp     short loc_180036784
0x180036781  mov     [r14], rax
0x180036784  mov     eax, ebx
0x180036786  mov     rbx, [rsp+50h+arg_0]
0x18003678e  add     rsp, 50h
0x180036792  pop     r15
0x180036794  pop     r14
0x180036796  pop     r13
0x180036798  pop     r12
0x18003679a  pop     rdi
0x18003679b  pop     rsi
0x18003679c  pop     rbp
0x18003679d  retn
```
