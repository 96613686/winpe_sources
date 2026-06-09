# OpenClassesRootKeyExW

- ea: `0x18003a394`
- end: `0x18003a6f7`
- name: `OpenClassesRootKeyExW`
- size: `867`
- prototype: `int __fastcall(const wchar_t *pszSubKey, unsigned int samDesired, HKEY__ **phkResult)`
- caller_count: `15`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180059038`
- `0x180059380`
- `0x18007774c`
- `0x18007cde4`
- `0x18009ab88`
- `0x18009b454`
- `0x18009b6c8`
- `0x18009ce6c`
- `0x18009eac8`
- `0x1800afe20`
- `0x1800b445c`
- `0x1800b5650`
- `0x1800b8e64`
- `0x1800c0648`
- `0x1800c8934`

## callees

- `0x18002ef3c`
- `0x18002f2bc`
- `0x18003a394`
- `0x1800443f0`
- `0x18004548c`
- `0x1800475e8`
- `0x1800475f4`
- `0x180047873`
- `0x18004c40c`
- `0x18004d474`
- `0x180087068`
- `0x1800c83c0`
- `0x1800c8838`
- `0x1800c8a2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a417`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a417`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a4eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a4eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a58f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a58f`
- `KERNEL32!RegOpenUserClassesRoot` at `0x18003a471`
- `KERNEL32!RegOpenUserClassesRoot` at `0x18003a471`

## string_xrefs

- `0x18003a4bf`: `onecore\com\published\comutils\reghelp.cxx`
- `0x18003a536`: `onecore\com\published\comutils\reghelp.cxx`
- `0x18003a5f2`: `onecore\com\published\comutils\reghelp.cxx`
- `0x18003a6b7`: `onecore\com\published\comutils\reghelp.cxx`
- `0x18003a4ad`: `OpenClassesRootKeyExW`
- `0x18003a527`: `OpenClassesRootKeyExW`
- `0x18003a5eb`: `OpenClassesRootKeyExW`
- `0x18003a6ab`: `OpenClassesRootKeyExW`

## pseudocode

```c
__int64 __fastcall OpenClassesRootKeyExW(const wchar_t *pszSubKey, unsigned int samDesired, HKEY__ **phkResult)
{
  DWORD LastError_0; // ebx
  int v8; // r14d
  HKEY__ *v9; // rax
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
  unsigned int v22; // r8d
  unsigned int v23; // eax
  unsigned __int16 *file; // [rsp+28h] [rbp-38h]
  unsigned __int16 *filea; // [rsp+28h] [rbp-38h]
  void *hProcToken; // [rsp+50h] [rbp-10h] BYREF
  void *hImpToken; // [rsp+58h] [rbp-8h] BYREF
  int fIsUserHiveOK; // [rsp+B0h] [rbp+50h] BYREF
  HKEY__ *hkcr; // [rsp+B8h] [rbp+58h] BYREF

  hImpToken = 0;
  hProcToken = 0;
  hkcr = 0;
  LastError_0 = 0;
  if ( !phkResult )
    return 87;
  *phkResult = 0;
  v8 = 512;
  if ( pszSubKey )
  {
    if ( *pszSubKey )
    {
      v9 = cachedHKCR;
      if ( cachedHKCR )
      {
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
        LastError_0 = (unsigned __int16)v11;
LABEL_31:
        CloseHandle_0(hProcToken);
        goto LABEL_36;
      }
      if ( fIsUserHiveOK )
      {
        v12 = RegOpenUserClassesRoot(hProcToken, 0, 0x2000000u, &hkcr);
        LastError_0 = v12;
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
            LastError_0);
        }
      }
    }
    v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes", 0, 0x2000000u, &hkcr);
    LastError_0 = v14;
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
            LastError_0);
        if ( LastError_0 == 5 && ComTrace::IsEnabled(v16, v15) )
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
  LastError_0 = GetLastError_0();
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    ComTraceMessageT<long>(
      "onecore\\com\\published\\comutils\\reghelp.cxx",
      "OpenClassesRootKeyExW",
      548,
      v21,
      L"%!WINERROR!",
      LastError_0);
LABEL_36:
  RegHelpResumeImpersonate(hImpToken);
  if ( !LastError_0 )
  {
    v9 = hkcr;
    if ( !pszSubKey )
    {
LABEL_49:
      *phkResult = v9;
      return LastError_0;
    }
LABEL_38:
    if ( *pszSubKey )
    {
      LastError_0 = RegOpenOtherKeyExW(v9, pszSubKey, (unsigned int)phkResult, samDesired, phkResult, file);
      if ( LastError_0 == 2 )
      {
        v23 = samDesired & 0x300;
        if ( ((samDesired & 0x300) == 0 || (v8 = v23 ^ 0x300) != 0)
          && !RegOpenOtherKeyExW(hkcr, pszSubKey, v22, samDesired | v8, phkResult, filea) )
        {
          return 0;
        }
      }
      else if ( LastError_0
             && (Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS)) )
      {
        ComTraceMessage(
          LastError_0,
          "onecore\\com\\published\\comutils\\reghelp.cxx",
          "OpenClassesRootKeyExW",
          581,
          ERRORS,
          L"%ws %d %!WINERROR!",
          pszSubKey,
          samDesired,
          LastError_0);
      }
      return LastError_0;
    }
    goto LABEL_49;
  }
  return LastError_0;
}

```

## disassembly

```asm
0x18003a394  mov     [rsp-38h+arg_0], rbx
0x18003a399  push    rbp
0x18003a39a  push    rsi
0x18003a39b  push    rdi
0x18003a39c  push    r12
0x18003a39e  push    r13
0x18003a3a0  push    r14
0x18003a3a2  push    r15
0x18003a3a4  mov     rbp, rsp
0x18003a3a7  sub     rsp, 60h
0x18003a3ab  xor     r13d, r13d
0x18003a3ae  mov     r15, phkResult
0x18003a3b1  mov     [rbp+hImpToken], r13
0x18003a3b5  mov     r12d, samDesired
0x18003a3b8  mov     [rbp+hProcToken], r13
0x18003a3bc  mov     rsi, pszSubKey
0x18003a3bf  mov     [rbp+hkcr], r13
0x18003a3c3  mov     ebx, r13d
0x18003a3c6  test    phkResult, phkResult
0x18003a3c9  jnz     short loc_18003A3D4
0x18003a3cb  lea     eax, [phkResult+57h]
0x18003a3cf  jmp     loc_18003A6DE
0x18003a3d4  mov     [phkResult], r13
0x18003a3d7  mov     r14d, 200h
0x18003a3dd  test    rsi, rsi
0x18003a3e0  jz      short loc_18003A3FD
0x18003a3e2  cmp     [pszSubKey], r13w
0x18003a3e6  jz      short loc_18003A3FD
0x18003a3e8  mov     rax, cs:?cachedHKCR@@3PEAUHKEY__@@EA; HKEY__ * cachedHKCR
0x18003a3ef  test    rax, rax
0x18003a3f2  jz      short loc_18003A3FD
0x18003a3f4  mov     [rbp+hkcr], rax
0x18003a3f8  jmp     loc_18003A61C
0x18003a3fd  lea     pszSubKey, [rbp+hImpToken]; pHandle
0x18003a401  call    ?RegHelpSuspendImpersonate@@YAJPEAPEAX@Z; RegHelpSuspendImpersonate(void * *)
0x18003a406  call    GetCurrentProcess_0
0x18003a40b  mov     pszSubKey, rax; ProcessHandle
0x18003a40e  lea     phkResult, [rbp+hProcToken]; TokenHandle
0x18003a412  mov     samDesired, 8; DesiredAccess
0x18003a417  call    cs:__imp_OpenProcessToken
0x18003a41e  nop     dword ptr [rax+rax+00h]
0x18003a423  test    eax, eax
0x18003a425  jz      loc_18003A5B1
0x18003a42b  test    cs:?g_GLBOPT_RoFlags@@3KA, 100h; ulong g_GLBOPT_RoFlags
0x18003a435  lea     rdi, aWinerror; "%!WINERROR!"
0x18003a43c  mov     [rbp+fIsUserHiveOK], r13d
0x18003a440  jnz     loc_18003A4CB
0x18003a446  mov     pszSubKey, [rbp+hProcToken]; hToken
0x18003a44a  lea     rdx, [rbp+fIsUserHiveOK]; fOK
0x18003a44e  call    IsUserHiveOK
0x18003a453  test    eax, eax
0x18003a455  js      loc_18003A56A
0x18003a45b  cmp     [rbp+fIsUserHiveOK], r13d
0x18003a45f  jz      short loc_18003A4CB
0x18003a461  mov     pszSubKey, [rbp+hProcToken]; hToken
0x18003a465  lea     r9, [rbp+hkcr]; phkResult
0x18003a469  xor     samDesired, samDesired; dwOptions
0x18003a46b  mov     r8d, 2000000h; samDesired
0x18003a471  call    cs:__imp_RegOpenUserClassesRoot
0x18003a478  nop     dword ptr [rax+rax+00h]
0x18003a47d  mov     ebx, eax
0x18003a47f  test    eax, eax
0x18003a481  jz      loc_18003A56F
0x18003a487  cmp     eax, 2
0x18003a48a  jz      short loc_18003A4CB
0x18003a48c  cmp     cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1, r13d
0x18003a493  ja      short loc_18003A4A9
0x18003a495  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x18003a49c  jz      short loc_18003A4CB
0x18003a49e  xor     ecx, ecx; level
0x18003a4a0  call    IsWppLevelEnabled
0x18003a4a5  test    al, al
0x18003a4a7  jz      short loc_18003A4CB
0x18003a4a9  mov     [rsp+60h+file], ebx; file
0x18003a4ad  lea     rdx, aOpenclassesroo; "OpenClassesRootKeyExW"
0x18003a4b4  mov     r8d, 1EBh; line
0x18003a4ba  mov     [rsp+60h+hKey], rdi; <args_0>
0x18003a4bf  lea     pszSubKey, aOnecoreComPubl; "onecore\\com\\published\\comutils\\regh"...
0x18003a4c6  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18003a4cb  lea     rax, [rbp+hkcr]
0x18003a4cf  mov     r9d, 2000000h; samDesired
0x18003a4d5  xor     r8d, r8d; ulOptions
0x18003a4d8  mov     [rsp+60h+hKey], rax; phkResult
0x18003a4dd  lea     rdx, aSoftwareClasse; "Software\\Classes"
0x18003a4e4  mov     pszSubKey, 0FFFFFFFF80000002h; hKey
0x18003a4eb  call    cs:__imp_RegOpenKeyExW
0x18003a4f2  nop     dword ptr [rax+rax+00h]
0x18003a4f7  mov     ebx, eax
0x18003a4f9  test    eax, eax
0x18003a4fb  jz      short loc_18003A56F
0x18003a4fd  cmp     eax, 2
0x18003a500  jz      loc_18003A5A6
0x18003a506  cmp     cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1, r13d
0x18003a50d  ja      short loc_18003A523
0x18003a50f  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x18003a516  jz      short loc_18003A542
0x18003a518  xor     ecx, ecx; level
0x18003a51a  call    IsWppLevelEnabled
0x18003a51f  test    al, al
0x18003a521  jz      short loc_18003A542
0x18003a523  mov     [rsp+60h+file], ebx; file
0x18003a527  lea     rdx, aOpenclassesroo; "OpenClassesRootKeyExW"
0x18003a52e  mov     r8d, r14d; line
0x18003a531  mov     [rsp+60h+hKey], rdi; <args_0>
0x18003a536  lea     pszSubKey, aOnecoreComPubl; "onecore\\com\\published\\comutils\\regh"...
0x18003a53d  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18003a542  cmp     ebx, 5
0x18003a545  jnz     short loc_18003A5A6
0x18003a547  call    ?IsEnabled@ComTrace@@SA_NE_K@Z; ComTrace::IsEnabled(uchar,unsigned __int64)
0x18003a54c  test    al, al
0x18003a54e  jz      short loc_18003A5A6
0x18003a550  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f8a79a44bba2ee3470b25df359f31864_@@CA@XZ; cleanupFunc
0x18003a557  call    ?get@?$static_lazy@VComTrace@@@details@wil@@QEAAPEAVComTrace@@P6AXXZ@Z; wil::details::static_lazy<ComTrace>::get(void (*)(void))
0x18003a55c  mov     rdx, [rbp+hProcToken]; token
0x18003a560  mov     pszSubKey, rax; this
0x18003a563  call    ?LogTokenInfoImp@ComTrace@@QEAAXPEAXK@Z; ComTrace::LogTokenInfoImp(void *,ulong)
0x18003a568  jmp     short loc_18003A5A6
0x18003a56a  movzx   ebx, ax
0x18003a56d  jmp     short loc_18003A5A6
0x18003a56f  test    rsi, rsi
0x18003a572  jz      short loc_18003A5A6
0x18003a574  cmp     [rsi], r13w
0x18003a578  jz      short loc_18003A5A6
0x18003a57a  mov     pszSubKey, [rbp+hkcr]
0x18003a57e  xor     eax, eax
0x18003a580  lock cmpxchg cs:?cachedHKCR@@3PEAUHKEY__@@EA, pszSubKey; HKEY__ * cachedHKCR
0x18003a589  jz      short loc_18003A5A6
0x18003a58b  mov     pszSubKey, [rbp+hkcr]; hKey
0x18003a58f  call    cs:__imp_RegCloseKey
0x18003a596  nop     dword ptr [rax+rax+00h]
0x18003a59b  mov     rax, cs:?cachedHKCR@@3PEAUHKEY__@@EA; HKEY__ * cachedHKCR
0x18003a5a2  mov     [rbp+hkcr], rax
0x18003a5a6  mov     pszSubKey, [rbp+hProcToken]; hObject
0x18003a5aa  call    CloseHandle_0
0x18003a5af  jmp     short loc_18003A5FE
0x18003a5b1  call    GetLastError_0
0x18003a5b6  cmp     cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1, r13d
0x18003a5bd  mov     ebx, eax
0x18003a5bf  ja      short loc_18003A5D5
0x18003a5c1  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x18003a5c8  jz      short loc_18003A5FE
0x18003a5ca  xor     ecx, ecx; level
0x18003a5cc  call    IsWppLevelEnabled
0x18003a5d1  test    al, al
0x18003a5d3  jz      short loc_18003A5FE
0x18003a5d5  lea     rdi, aWinerror; "%!WINERROR!"
0x18003a5dc  mov     [rsp+60h+file], ebx; lpSubKey
0x18003a5e0  mov     r8d, 224h; line
0x18003a5e6  mov     [rsp+60h+hKey], rdi; <args_0>
0x18003a5eb  lea     rdx, aOpenclassesroo; "OpenClassesRootKeyExW"
0x18003a5f2  lea     pszSubKey, aOnecoreComPubl; "onecore\\com\\published\\comutils\\regh"...
0x18003a5f9  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18003a5fe  mov     pszSubKey, [rbp+hImpToken]; hToken
0x18003a602  call    ?RegHelpResumeImpersonate@@YAXPEAX@Z; RegHelpResumeImpersonate(void *)
0x18003a607  test    ebx, ebx
0x18003a609  jnz     loc_18003A6DC
0x18003a60f  mov     rax, [rbp+hkcr]
0x18003a613  test    rsi, rsi
0x18003a616  jz      loc_18003A6D9
0x18003a61c  cmp     [rsi], r13w
0x18003a620  jz      loc_18003A6D9
0x18003a626  mov     r9d, r12d; phkResult
0x18003a629  mov     [rsp+60h+hKey], r15; hKey
0x18003a62e  mov     rdx, rsi; lpSubKey
0x18003a631  mov     pszSubKey, rax; hKey
0x18003a634  call    RegOpenOtherKeyExW
0x18003a639  mov     ebx, eax
0x18003a63b  mov     edi, eax
0x18003a63d  cmp     eax, 2
0x18003a640  jnz     short loc_18003A67A
0x18003a642  mov     eax, r12d
0x18003a645  mov     ecx, 300h
0x18003a64a  and     eax, ecx
0x18003a64c  jz      short loc_18003A65A
0x18003a64e  mov     r14d, eax
0x18003a651  xor     r14d, ecx
0x18003a654  jz      loc_18003A6DC
0x18003a65a  mov     pszSubKey, [rbp+hkcr]; hKey
0x18003a65e  or      r14d, r12d
0x18003a661  mov     r9d, r14d; phkResult
0x18003a664  mov     [rsp+60h+hKey], r15; hKey
0x18003a669  mov     rdx, rsi; lpSubKey
0x18003a66c  call    RegOpenOtherKeyExW
0x18003a671  test    eax, eax
0x18003a673  jnz     short loc_18003A6DC
0x18003a675  mov     ebx, r13d
0x18003a678  jmp     short loc_18003A6DC
0x18003a67a  test    edi, edi
0x18003a67c  jz      short loc_18003A6DC
0x18003a67e  cmp     cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1, r13d
0x18003a685  ja      short loc_18003A69B
0x18003a687  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x18003a68e  jz      short loc_18003A6DC
0x18003a690  xor     ecx, ecx; level
0x18003a692  call    IsWppLevelEnabled
0x18003a697  test    al, al
0x18003a699  jz      short loc_18003A6DC
0x18003a69b  mov     [rsp+60h+var_20], edi
0x18003a69f  lea     rax, aWsDWinerror; "%ws %d %!WINERROR!"
0x18003a6a6  mov     [rsp+60h+var_28], r12d
0x18003a6ab  lea     phkResult, aOpenclassesroo; "OpenClassesRootKeyExW"
0x18003a6b2  mov     [rsp+60h+var_30], rsi
0x18003a6b7  lea     rdx, aOnecoreComPubl; "onecore\\com\\published\\comutils\\regh"...
0x18003a6be  mov     qword ptr [rsp+60h+file], rax; format
0x18003a6c3  mov     r9d, 245h; line
0x18003a6c9  mov     ecx, edi; hr
0x18003a6cb  mov     dword ptr [rsp+60h+hKey], r13d; level
0x18003a6d0  call    ?ComTraceMessage@@YAXJPEBD0HW4TraceLevel@@PEBGZZ; ComTraceMessage(long,char const *,char const *,int,TraceLevel,ushort const *,...)
0x18003a6d5  mov     ebx, edi
0x18003a6d7  jmp     short loc_18003A6DC
0x18003a6d9  mov     [r15], rax
0x18003a6dc  mov     eax, ebx
0x18003a6de  mov     rbx, [rsp+60h+arg_0]
0x18003a6e6  add     rsp, 60h
0x18003a6ea  pop     r15
0x18003a6ec  pop     r14
0x18003a6ee  pop     r13
0x18003a6f0  pop     r12
0x18003a6f2  pop     rdi
0x18003a6f3  pop     rsi
0x18003a6f4  pop     rbp
0x18003a6f5  retn
```
