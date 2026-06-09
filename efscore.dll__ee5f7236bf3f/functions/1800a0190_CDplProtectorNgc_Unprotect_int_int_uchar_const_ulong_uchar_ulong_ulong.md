# CDplProtectorNgc::Unprotect(int,int,uchar const *,ulong,uchar *,ulong,ulong *)

- ea: `0x1800a0190`
- end: `0x1800a0b16`
- name: `?Unprotect@CDplProtectorNgc@@MEAAJHHPEBEKPEAEKPEAK@Z`
- size: `2438`
- prototype: `__int64 __fastcall(CDplProtectorNgc *this, unsigned int, unsigned int, const unsigned __int8 *, unsigned int dwBytes, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001a7c`
- `0x180001f5c`
- `0x180004f86`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180063c24`
- `0x180082bb8`
- `0x180082d60`
- `0x180085ba0`
- `0x1800a0190`
- `0x1800dca3c`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0338`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0338`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a0327`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a063b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a0327`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a063b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a0649`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a0649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a079d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a08ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a095b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a079d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a08ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a095b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a0786`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a0786`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a076d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a076d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a0951`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a0951`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a05a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a05a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a067b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a067b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800a08a4`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800a08a4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a07df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a07df`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800a03b1`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800a03b1`
- `ncrypt!NCryptFreeObject` at `0x1800a06f2`
- `ncrypt!NCryptFreeObject` at `0x1800a0705`
- `ncrypt!NCryptFreeObject` at `0x1800a06f2`
- `ncrypt!NCryptFreeObject` at `0x1800a0705`
- `ncrypt!NCryptOpenKey` at `0x1800a042e`
- `ncrypt!NCryptOpenKey` at `0x1800a042e`
- `ncrypt!NCryptSetProperty` at `0x1800a06a4`
- `ncrypt!NCryptSetProperty` at `0x1800a06a4`
- `ncrypt!NCryptGetProperty` at `0x1800a04af`
- `ncrypt!NCryptGetProperty` at `0x1800a04af`
- `cryptngc!NgcDecryptWithUserIdKey` at `0x1800a0a37`
- `cryptngc!NgcDecryptWithUserIdKey` at `0x1800a0a37`
- `cryptngc!NgcDecryptWithUserIdKeySilent` at `0x1800a0531`
- `cryptngc!NgcDecryptWithUserIdKeySilent` at `0x1800a0a83`
- `cryptngc!NgcDecryptWithUserIdKeySilent` at `0x1800a0531`
- `cryptngc!NgcDecryptWithUserIdKeySilent` at `0x1800a0a83`
- `USER32!GetDesktopWindow` at `0x1800a09b3`
- `USER32!GetDesktopWindow` at `0x1800a09b3`
- `USER32!GetForegroundWindow` at `0x1800a09a5`
- `USER32!GetForegroundWindow` at `0x1800a09a5`

## string_xrefs

- `0x1800a04a8`: `PinCacheApplicationTicket`
- `0x1800a069d`: `PinCacheFreeApplicationTicket`

## pseudocode

```c
__int64 __fastcall CDplProtectorNgc::Unprotect(
        CDplProtectorNgc *this,
        unsigned int a2,
        unsigned int a3,
        const unsigned __int8 *a4,
        unsigned int dwBytes,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int *a8)
{
  unsigned int v9; // edi
  void *v10; // r15
  __int64 v11; // r12
  unsigned int Property; // ebx
  int v13; // r8d
  HANDLE ProcessHeap; // rax
  void *v15; // rax
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  __int64 v20; // rdx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  HANDLE v24; // rax
  _BYTE *v25; // rcx
  __int64 v26; // rax
  SECURITY_STATUS v27; // edi
  BYTE *v28; // rax
  HANDLE CurrentThread; // rax
  int v31; // ecx
  signed int v32; // eax
  signed int LastError; // eax
  int v34; // ecx
  signed int v35; // eax
  signed int v36; // eax
  HWND ForegroundWindow; // rbx
  int v38; // ecx
  unsigned int v39; // eax
  _OWORD *v40; // rax
  char dwFlags; // [rsp+20h] [rbp-E0h]
  char dwFlagsa; // [rsp+20h] [rbp-E0h]
  char dwFlagsb; // [rsp+20h] [rbp-E0h]
  char v44; // [rsp+30h] [rbp-D0h]
  void *v46; // [rsp+48h] [rbp-B8h]
  unsigned int v47; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v48; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v49; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  int TokenInformation; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbResult; // [rsp+6Ch] [rbp-94h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  CDplProtectorNgc *v55; // [rsp+80h] [rbp-80h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+88h] [rbp-78h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+90h] [rbp-70h] BYREF
  DWORD ReturnLength; // [rsp+98h] [rbp-68h] BYREF
  void *v59[2]; // [rsp+A0h] [rbp-60h] BYREF
  BYTE pbOutput[96]; // [rsp+B0h] [rbp-50h] BYREF

  v9 = a2;
  v49 = a3;
  v10 = 0;
  v55 = this;
  v48 = dwBytes;
  hMem = 0;
  v47 = 0;
  phProvider = 0;
  phKey = 0;
  pcbResult = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v59[0] = 0;
  TokenHandle = 0;
  hObject = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 35, 117);
  if ( a8 )
    *a8 = 0;
  v11 = 90;
  if ( !a4 )
  {
    dwFlags = 125;
LABEL_5:
    Property = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 35, dwFlags);
    goto LABEL_24;
  }
  if ( !dwBytes || (a6 == 0) != (a7 == 0) )
  {
LABEL_92:
    dwFlags = -125;
    goto LABEL_5;
  }
  if ( a6 )
  {
    if ( a7 < 0x20 )
    {
      Property = -2147024774;
      dwFlagsa = -106;
      v13 = -2147024774;
LABEL_13:
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v13, 35, dwFlagsa);
      goto LABEL_23;
    }
    ProcessHeap = GetProcessHeap();
    v15 = HeapAlloc(ProcessHeap, 8u, dwBytes);
    v46 = v15;
    v10 = v15;
    if ( !v15 )
    {
      Property = -2147024882;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024882, 35, 159);
      goto LABEL_23;
    }
    memcpy_0(v15, a4, dwBytes);
    if ( a2 )
    {
      fnEfsLogTrace1Strings(v16, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 35, 174);
      Property = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  Property,
                  35,
                  174) < 0 )
        goto LABEL_22;
      fnEfsLogTrace1Strings(v17, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 35, 176);
      Property = NCryptOpenKey(phProvider, &phKey, *((LPCWSTR *)v55 + 6), 0, 0);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  Property,
                  35,
                  176) < 0 )
        goto LABEL_22;
      fnEfsLogTrace1Strings(v18, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 35, 183);
      Property = NCryptGetProperty(phKey, L"PinCacheApplicationTicket", pbOutput, 0x5Au, &pcbResult, 0);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  Property,
                  35,
                  183) < 0 )
        goto LABEL_22;
      fnEfsLogTrace1Strings(v19, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 35, 194);
      Property = NgcDecryptWithUserIdKeySilent(*((_QWORD *)v55 + 6), 0, v46, v48, &hMem, &v47);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  Property,
                  35,
                  194) < 0 )
        goto LABEL_22;
LABEL_87:
      if ( v47 == 32 )
      {
        if ( a8 )
          *a8 = 32;
        v40 = hMem;
        *(_OWORD *)a6 = *(_OWORD *)hMem;
        *((_OWORD *)a6 + 1) = v40[1];
      }
      else
      {
        Property = -2147418113;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 35, 40);
      }
      goto LABEL_22;
    }
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
    {
      if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
      {
        LastError = GetLastError();
        Property = LastError;
        if ( LastError > 0 )
          Property = (unsigned __int16)LastError | 0x80070000;
        dwFlagsa = -33;
        goto LABEL_60;
      }
    }
    else if ( GetLastError() != 1008 )
    {
      v32 = GetLastError();
      Property = v32;
      if ( v32 > 0 )
        Property = (unsigned __int16)v32 | 0x80070000;
      dwFlagsa = -44;
LABEL_60:
      v13 = Property;
      goto LABEL_13;
    }
    if ( TokenInformation )
    {
      fnEfsLogTrace1Strings(v31, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 35, 233);
      Property = EdpCredSvcGetImpersonationCtxAndRevertToSelf(v59);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  Property,
                  35,
                  233) < 0 )
        goto LABEL_22;
      if ( !DuplicateTokenEx(TokenHandle, 0, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
      {
        v35 = GetLastError();
        Property = v35;
        if ( v35 > 0 )
          Property = (unsigned __int16)v35 | 0x80070000;
        dwFlagsb = -14;
LABEL_71:
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, Property, 35, dwFlagsb);
        goto LABEL_22;
      }
      fnEfsLogTrace1Strings(v34, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 35, 245);
      Property = EdpCredSvcElevateTokenToMediumIL(hObject);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  Property,
                  35,
                  245) < 0 )
        goto LABEL_22;
      if ( !SetThreadToken(0, hObject) )
      {
        v36 = GetLastError();
        Property = v36;
        if ( v36 > 0 )
          Property = (unsigned __int16)v36 | 0x80070000;
        dwFlagsb = -1;
        goto LABEL_71;
      }
    }
    if ( v49 )
    {
      fnEfsLogTrace1Strings(v31, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 35, 33);
      v39 = NgcDecryptWithUserIdKeySilent(*((_QWORD *)v55 + 6), 0, v46, v48, &hMem, &v47);
      v44 = 33;
    }
    else
    {
      fnEfsLogTrace1Strings(v31, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 35, 10);
      ForegroundWindow = GetForegroundWindow();
      if ( !ForegroundWindow )
        ForegroundWindow = GetDesktopWindow();
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  0,
                  35,
                  10) < 0 )
      {
        Property = 0;
        goto LABEL_22;
      }
      fnEfsLogTrace1Strings(v38, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 35, 21);
      v39 = NgcDecryptWithUserIdKey(*((_QWORD *)v55 + 6), ForegroundWindow, v46, v48, &hMem, &v47);
      v44 = 21;
    }
    Property = v39;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v39,
                35,
                v44) >= 0 )
    {
      EdpCredSvcRestoreImpersonationCtx(v59);
      goto LABEL_87;
    }
LABEL_22:
    v10 = v46;
    v11 = 90;
    goto LABEL_23;
  }
  if ( !a8 )
    goto LABEL_92;
  Property = 0;
  *a8 = 32;
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
    (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
    (unsigned int)L"Returning required key buffer size",
    32,
    35,
    143);
LABEL_23:
  v9 = a2;
LABEL_24:
  EdpCredSvcRestoreImpersonationCtx(v59);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( (a6 || Property)
    && (unsigned int)dword_180114250 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
  {
    v49 = Property;
    v48 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v21,
      (unsigned int)byte_180103001,
      v22,
      v23,
      (__int64)&v48,
      (__int64)&v49);
  }
  if ( v9 && a6 && Property )
    fnEfsLogTraceEtw1String1Dword(g_hPublisher, v20, *(_QWORD *)(*((_QWORD *)v55 + 4) + 8LL), Property);
  if ( v10 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v10);
  }
  v25 = hMem;
  if ( hMem )
  {
    v26 = v47;
    if ( v47 )
    {
      do
      {
        *v25++ = 0;
        --v26;
      }
      while ( v26 );
      v25 = hMem;
    }
    if ( v25 )
    {
      LocalFree(v25);
      hMem = 0;
    }
  }
  if ( pcbResult )
  {
    v27 = NCryptSetProperty(phProvider, L"PinCacheFreeApplicationTicket", pbOutput, 0x5Au, 0);
    if ( v27 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, v27, 35, 112);
    v28 = pbOutput;
    do
    {
      *v28++ = 0;
      --v11;
    }
    while ( v11 );
  }
  if ( phKey )
  {
    NCryptFreeObject(phKey);
    phKey = 0;
  }
  if ( phProvider )
  {
    NCryptFreeObject(phProvider);
    phProvider = 0;
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    Property,
    35,
    129);
  return Property;
}

```

## disassembly

```asm
0x1800a0190  mov     [rsp-8+arg_8], rbx
0x1800a0195  push    rbp
0x1800a0196  push    rsi
0x1800a0197  push    rdi
0x1800a0198  push    r12
0x1800a019a  push    r13
0x1800a019c  push    r14
0x1800a019e  push    r15
0x1800a01a0  lea     rbp, [rsp-20h]
0x1800a01a5  sub     rsp, 120h
0x1800a01ac  mov     rax, cs:__security_cookie
0x1800a01b3  xor     rax, rsp
0x1800a01b6  mov     [rbp+50h+var_40], rax
0x1800a01ba  mov     ebx, dword ptr [rbp+50h+dwBytes]
0x1800a01c0  xor     r12d, r12d
0x1800a01c3  mov     r13, [rbp+50h+arg_28]
0x1800a01ca  mov     r14, r9
0x1800a01cd  mov     rsi, [rbp+50h+arg_38]
0x1800a01d4  mov     edi, edx
0x1800a01d6  mov     [rsp+150h+var_F8], r8d
0x1800a01db  mov     r15d, r12d
0x1800a01de  mov     [rsp+150h+var_110], edx
0x1800a01e2  lea     r9d, [r12+23h]
0x1800a01e7  lea     r8, sourceString
0x1800a01ee  mov     [rbp+50h+var_D0], rcx
0x1800a01f2  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800a01f9  mov     [rsp+150h+var_FC], ebx
0x1800a01fd  mov     [rsp+150h+hMem], r12
0x1800a0202  mov     [rsp+150h+var_100], r12d
0x1800a0207  mov     [rbp+50h+phProvider], r12
0x1800a020b  mov     [rbp+50h+phKey], r12
0x1800a020f  mov     [rsp+150h+pcbResult], r12d
0x1800a0214  mov     [rsp+150h+TokenInformation], r12d
0x1800a0219  mov     [rbp+50h+ReturnLength], r12d
0x1800a021d  mov     [rbp+50h+var_B0], r12
0x1800a0221  mov     [rsp+150h+TokenHandle], r12
0x1800a0226  mov     [rsp+150h+hObject], r12
0x1800a022b  mov     [rsp+150h+dwFlags], 675h
0x1800a0233  call    fnEfsLogTrace1Strings
0x1800a0238  test    rsi, rsi
0x1800a023b  jz      short loc_1800A0241
0x1800a023d  xor     eax, eax
0x1800a023f  mov     [rsi], eax
0x1800a0241  mov     r12d, 5Ah ; 'Z'
0x1800a0247  test    r14, r14
0x1800a024a  jnz     short loc_1800A027D
0x1800a024c  mov     [rsp+150h+dwFlags], 67Dh
0x1800a0254  mov     rcx, cs:g_hPublisher
0x1800a025b  lea     rdx, EFS_TRACE_ERROR
0x1800a0262  mov     r9d, 23h ; '#'
0x1800a0268  mov     r8d, 80070057h
0x1800a026e  mov     ebx, 80070057h
0x1800a0273  call    fnEfsLogTrace1
0x1800a0278  jmp     loc_1800A057D
0x1800a027d  test    ebx, ebx
0x1800a027f  jz      loc_1800A0B09
0x1800a0285  mov     edx, [rbp+50h+arg_30]
0x1800a028b  xor     ecx, ecx
0x1800a028d  test    r13, r13
0x1800a0290  setz    cl
0x1800a0293  xor     eax, eax
0x1800a0295  test    edx, edx
0x1800a0297  setz    al
0x1800a029a  cmp     ecx, eax
0x1800a029c  jnz     loc_1800A0B09
0x1800a02a2  test    r13, r13
0x1800a02a5  jnz     short loc_1800A02ED
0x1800a02a7  test    rsi, rsi
0x1800a02aa  jz      loc_1800A0B09
0x1800a02b0  xor     ebx, ebx
0x1800a02b2  mov     dword ptr [rsp+150h+var_120], 68Fh
0x1800a02ba  lea     rdx, EFS_TRACE_MSG_DWORD_EVENT
0x1800a02c1  mov     [rsp+150h+var_128], 23h ; '#'
0x1800a02c9  lea     r9, aReturningRequi; "Returning required key buffer size"
0x1800a02d0  mov     r8, rdx
0x1800a02d3  lea     edi, [rbx+20h]
0x1800a02d6  mov     [rsi], edi
0x1800a02d8  mov     rcx, cs:g_hPublisher
0x1800a02df  mov     [rsp+150h+dwFlags], edi
0x1800a02e3  call    fnEfsLogTrace1String1Dword
0x1800a02e8  jmp     loc_1800A0579
0x1800a02ed  mov     edi, 20h ; ' '
0x1800a02f2  cmp     edx, edi
0x1800a02f4  jnb     short loc_1800A0327
0x1800a02f6  mov     ebx, 8007007Ah
0x1800a02fb  mov     [rsp+150h+dwFlags], 696h
0x1800a0303  mov     r8d, 8007007Ah
0x1800a0309  mov     rcx, cs:g_hPublisher
0x1800a0310  lea     rdx, EFS_TRACE_ERROR
0x1800a0317  mov     r9d, 23h ; '#'
0x1800a031d  call    fnEfsLogTrace1
0x1800a0322  jmp     loc_1800A0579
0x1800a0327  call    cs:__imp_GetProcessHeap
0x1800a032d  mov     r8, rbx; dwBytes
0x1800a0330  mov     edx, 8; dwFlags
0x1800a0335  mov     rcx, rax; hHeap
0x1800a0338  call    cs:__imp_HeapAlloc
0x1800a033e  mov     [rsp+150h+var_108], rax
0x1800a0343  mov     r15, rax
0x1800a0346  test    rax, rax
0x1800a0349  jnz     short loc_1800A0360
0x1800a034b  mov     ebx, 8007000Eh
0x1800a0350  mov     [rsp+150h+dwFlags], 69Fh
0x1800a0358  mov     r8d, 8007000Eh
0x1800a035e  jmp     short loc_1800A0309
0x1800a0360  mov     r8, rbx; Size
0x1800a0363  mov     rdx, r14; Src
0x1800a0366  mov     rcx, rax; void *
0x1800a0369  call    memcpy_0
0x1800a036e  cmp     [rsp+150h+var_110], 0
0x1800a0373  jz      loc_1800A076D
0x1800a0379  mov     r12d, 23h ; '#'
0x1800a037f  lea     r14, EFS_TRACE_START_EVENT
0x1800a0386  mov     r15d, 6AEh
0x1800a038c  lea     r8, sourceString
0x1800a0393  mov     r9d, r12d
0x1800a0396  mov     [rsp+150h+dwFlags], r15d
0x1800a039b  mov     rdx, r14
0x1800a039e  call    fnEfsLogTrace1Strings
0x1800a03a3  xor     r8d, r8d; dwFlags
0x1800a03a6  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x1800a03ad  lea     rcx, [rbp+50h+phProvider]; phProvider
0x1800a03b1  call    cs:__imp_NCryptOpenStorageProvider
0x1800a03b7  mov     rcx, cs:g_hPublisher
0x1800a03be  lea     r9, sourceString
0x1800a03c5  mov     dword ptr [rsp+150h+var_120], r15d
0x1800a03ca  mov     ebx, eax
0x1800a03cc  mov     [rsp+150h+var_128], r12d
0x1800a03d1  lea     r15, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800a03d8  lea     r12, EFS_TRACE_COMPLETE_EVENT
0x1800a03df  mov     [rsp+150h+dwFlags], eax
0x1800a03e3  mov     rdx, r12
0x1800a03e6  mov     r8, r15
0x1800a03e9  call    fnEfsLogTrace1String1Dword
0x1800a03ee  test    eax, eax
0x1800a03f0  js      loc_1800A056E
0x1800a03f6  mov     r9d, 23h ; '#'
0x1800a03fc  mov     [rsp+150h+dwFlags], 6B0h
0x1800a0404  lea     r8, sourceString
0x1800a040b  mov     rdx, r14
0x1800a040e  call    fnEfsLogTrace1Strings
0x1800a0413  mov     r8, [rbp+50h+var_D0]
0x1800a0417  lea     rdx, [rbp+50h+phKey]; phKey
0x1800a041b  mov     rcx, [rbp+50h+phProvider]; hProvider
0x1800a041f  xor     r9d, r9d; dwLegacyKeySpec
0x1800a0422  mov     [rsp+150h+dwFlags], 0; dwFlags
0x1800a042a  mov     r8, [r8+30h]; pszKeyName
0x1800a042e  call    cs:__imp_NCryptOpenKey
0x1800a0434  mov     rcx, cs:g_hPublisher
0x1800a043b  lea     r9, sourceString
0x1800a0442  mov     dword ptr [rsp+150h+var_120], 6B0h
0x1800a044a  mov     r8, r15
0x1800a044d  mov     [rsp+150h+var_128], 23h ; '#'
0x1800a0455  mov     rdx, r12
0x1800a0458  mov     ebx, eax
0x1800a045a  mov     [rsp+150h+dwFlags], eax
0x1800a045e  call    fnEfsLogTrace1String1Dword
0x1800a0463  test    eax, eax
0x1800a0465  js      loc_1800A056E
0x1800a046b  mov     r9d, 23h ; '#'
0x1800a0471  mov     [rsp+150h+dwFlags], 6B7h
0x1800a0479  lea     r8, sourceString
0x1800a0480  mov     rdx, r14
0x1800a0483  call    fnEfsLogTrace1Strings
0x1800a0488  mov     rcx, [rbp+50h+phKey]; hObject
0x1800a048c  lea     rax, [rsp+150h+pcbResult]
0x1800a0491  mov     [rsp+150h+var_128], 0; dwFlags
0x1800a0499  lea     r8, [rbp+50h+pbOutput]; pbOutput
0x1800a049d  mov     r9d, 5Ah ; 'Z'; cbOutput
0x1800a04a3  mov     qword ptr [rsp+150h+dwFlags], rax; pcbResult
0x1800a04a8  lea     rdx, aPincacheapplic; "PinCacheApplicationTicket"
0x1800a04af  call    cs:__imp_NCryptGetProperty
0x1800a04b5  mov     rcx, cs:g_hPublisher
0x1800a04bc  lea     r9, sourceString
0x1800a04c3  mov     dword ptr [rsp+150h+var_120], 6B7h
0x1800a04cb  mov     r8, r15
0x1800a04ce  mov     [rsp+150h+var_128], 23h ; '#'
0x1800a04d6  mov     rdx, r12
0x1800a04d9  mov     ebx, eax
0x1800a04db  mov     [rsp+150h+dwFlags], eax
0x1800a04df  call    fnEfsLogTrace1String1Dword
0x1800a04e4  test    eax, eax
0x1800a04e6  js      loc_1800A056E
0x1800a04ec  mov     r9d, 23h ; '#'
0x1800a04f2  mov     [rsp+150h+dwFlags], 6C2h
0x1800a04fa  lea     r8, sourceString
0x1800a0501  mov     rdx, r14
0x1800a0504  call    fnEfsLogTrace1Strings
0x1800a0509  mov     r9d, [rsp+150h+var_FC]
0x1800a050e  lea     rax, [rsp+150h+var_100]
0x1800a0513  mov     r8, [rsp+150h+var_108]
0x1800a0518  xor     edx, edx
0x1800a051a  mov     qword ptr [rsp+150h+var_128], rax
0x1800a051f  lea     rax, [rsp+150h+hMem]
0x1800a0524  mov     qword ptr [rsp+150h+dwFlags], rax
0x1800a0529  mov     rax, [rbp+50h+var_D0]
0x1800a052d  mov     rcx, [rax+30h]
0x1800a0531  call    cs:__imp_NgcDecryptWithUserIdKeySilent
0x1800a0537  mov     rcx, cs:g_hPublisher
0x1800a053e  lea     r9, sourceString
0x1800a0545  mov     dword ptr [rsp+150h+var_120], 6C2h
0x1800a054d  mov     r8, r15
0x1800a0550  mov     [rsp+150h+var_128], 23h ; '#'
0x1800a0558  mov     rdx, r12
0x1800a055b  mov     ebx, eax
0x1800a055d  mov     [rsp+150h+dwFlags], eax
0x1800a0561  call    fnEfsLogTrace1String1Dword
0x1800a0566  test    eax, eax
0x1800a0568  jns     loc_1800A0AC9
0x1800a056e  mov     r15, [rsp+150h+var_108]
0x1800a0573  mov     r12d, 5Ah ; 'Z'
0x1800a0579  mov     edi, [rsp+150h+var_110]
0x1800a057d  lea     rcx, [rbp+50h+var_B0]; void **
0x1800a0581  call    ?EdpCredSvcRestoreImpersonationCtx@@YAXPEAPEAX@Z; EdpCredSvcRestoreImpersonationCtx(void * *)
0x1800a0586  mov     rcx, [rsp+150h+hObject]; hObject
0x1800a058b  test    rcx, rcx
0x1800a058e  jz      short loc_1800A059F
0x1800a0590  call    cs:__imp_CloseHandle
0x1800a0596  mov     [rsp+150h+hObject], 0
0x1800a059f  mov     rcx, [rsp+150h+TokenHandle]; hObject
0x1800a05a4  test    rcx, rcx
0x1800a05a7  jz      short loc_1800A05B8
0x1800a05a9  call    cs:__imp_CloseHandle
0x1800a05af  mov     [rsp+150h+TokenHandle], 0
0x1800a05b8  test    r13, r13
0x1800a05bb  jnz     short loc_1800A05C1
0x1800a05bd  test    ebx, ebx
0x1800a05bf  jz      short loc_1800A060E
0x1800a05c1  mov     eax, cs:dword_180114250
0x1800a05c7  cmp     eax, 5
0x1800a05ca  jbe     short loc_1800A060E
0x1800a05cc  mov     rdx, 400000000000h
0x1800a05d6  lea     rcx, dword_180114250
0x1800a05dd  call    _tlgKeywordOn
0x1800a05e2  test    al, al
0x1800a05e4  jz      short loc_1800A060E
0x1800a05e6  lea     rax, [rsp+150h+var_F8]
0x1800a05eb  mov     [rsp+150h+var_F8], ebx
0x1800a05ef  mov     qword ptr [rsp+150h+var_128], rax
0x1800a05f4  lea     rdx, byte_180103001
0x1800a05fb  lea     rax, [rsp+150h+var_FC]
0x1800a0600  mov     [rsp+150h+var_FC], edi
0x1800a0604  mov     qword ptr [rsp+150h+dwFlags], rax
0x1800a0609  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a060e  test    edi, edi
0x1800a0610  jz      short loc_1800A0636
0x1800a0612  test    r13, r13
0x1800a0615  jz      short loc_1800A0636
0x1800a0617  test    ebx, ebx
0x1800a0619  jz      short loc_1800A0636
0x1800a061b  mov     rax, [rbp+50h+var_D0]
0x1800a061f  mov     r9d, ebx
0x1800a0622  mov     rcx, cs:g_hPublisher
0x1800a0629  mov     r8, [rax+20h]
0x1800a062d  mov     r8, [r8+8]
0x1800a0631  call    fnEfsLogTraceEtw1String1Dword
0x1800a0636  test    r15, r15
0x1800a0639  jz      short loc_1800A064F
0x1800a063b  call    cs:__imp_GetProcessHeap
0x1800a0641  mov     r8, r15; lpMem
0x1800a0644  xor     edx, edx; dwFlags
0x1800a0646  mov     rcx, rax; hHeap
0x1800a0649  call    cs:__imp_HeapFree
0x1800a064f  mov     rcx, [rsp+150h+hMem]
0x1800a0654  xor     r15d, r15d
0x1800a0657  test    rcx, rcx
0x1800a065a  jz      short loc_1800A0686
0x1800a065c  mov     eax, [rsp+150h+var_100]
0x1800a0660  test    rax, rax
0x1800a0663  jz      short loc_1800A0676
0x1800a0665  mov     [rcx], r15b
0x1800a0668  inc     rcx
0x1800a066b  sub     rax, 1
0x1800a066f  jnz     short loc_1800A0665
0x1800a0671  mov     rcx, [rsp+150h+hMem]; hMem
0x1800a0676  test    rcx, rcx
0x1800a0679  jz      short loc_1800A0686
0x1800a067b  call    cs:__imp_LocalFree
0x1800a0681  mov     [rsp+150h+hMem], r15
0x1800a0686  cmp     [rsp+150h+pcbResult], r15d
0x1800a068b  jz      short loc_1800A06E9
0x1800a068d  mov     rcx, [rbp+50h+phProvider]; hObject
0x1800a0691  lea     r8, [rbp+50h+pbOutput]; pbInput
0x1800a0695  mov     r9d, r12d; cbInput
0x1800a0698  mov     [rsp+150h+dwFlags], r15d; dwFlags
0x1800a069d  lea     rdx, aPincachefreeap; "PinCacheFreeApplicationTicket"
0x1800a06a4  call    cs:__imp_NCryptSetProperty
0x1800a06aa  mov     edi, eax
0x1800a06ac  test    eax, eax
0x1800a06ae  jz      short loc_1800A06B5
0x1800a06b0  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "ERROR_SUCCESS == SecStatus")
0x1800a06b5  mov     rcx, cs:g_hPublisher
0x1800a06bc  lea     rdx, EFS_TRACE_STATUS
0x1800a06c3  mov     r9d, 23h ; '#'
0x1800a06c9  mov     [rsp+150h+dwFlags], 770h
0x1800a06d1  mov     r8d, edi
0x1800a06d4  call    fnEfsLogTrace1
0x1800a06d9  lea     rax, [rbp+50h+pbOutput]
0x1800a06dd  mov     [rax], r15b
0x1800a06e0  inc     rax
  ... truncated ...
```
