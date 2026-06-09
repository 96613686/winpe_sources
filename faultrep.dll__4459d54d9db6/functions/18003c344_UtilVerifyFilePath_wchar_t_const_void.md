# UtilVerifyFilePath(wchar_t const *,void *)

- ea: `0x18003c344`
- end: `0x18003cb4e`
- name: `?UtilVerifyFilePath@@YAJPEB_WPEAX@Z`
- size: `2058`
- prototype: `__int64 __fastcall(wchar_t *, void *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003cc4c`

## callees

- `0x18000113c`
- `0x1800011dc`
- `0x180002890`
- `0x1800028b4`
- `0x180007704`
- `0x180009e04`
- `0x18000af40`
- `0x18000e330`
- `0x180024bc4`
- `0x18003c344`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003c414`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003c414`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003c435`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003c435`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c90a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c90a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c43f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c75e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c43f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c75e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c47b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c47b`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003c74e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003c81c`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003c74e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18003c81c`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x18003c918`
- `DiagnosticDataSettings!TelGetWerTelemetryMode` at `0x18003c918`

## pseudocode

```c
__int64 __fastcall UtilVerifyFilePath(wchar_t *a1, void *a2, int a3, int a4)
{
  int *v5; // r14
  signed int FinalPathByHandle; // edi
  HANDLE CurrentProcess; // rbx
  void **v8; // rax
  signed int LastError; // eax
  signed int IsLowRightsToken; // ebx
  __int16 *v11; // rdx
  __int64 v12; // r15
  __int64 v13; // r8
  char v14; // di
  unsigned int v15; // ebx
  __int64 v16; // rax
  unsigned __int16 v17; // ax
  __int64 v18; // rcx
  unsigned __int16 v19; // cx
  int *v20; // rcx
  __int64 v21; // rax
  unsigned int v22; // eax
  DWORD LongPathNameW; // eax
  DWORD v24; // edi
  signed int v25; // eax
  const struct std::nothrow_t *v26; // rdx
  _WORD *v27; // rsi
  __int64 v28; // r8
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // rsi
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rax
  unsigned __int16 v38; // ax
  __int64 v39; // rcx
  unsigned __int16 v40; // cx
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v43; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpszShortPath; // [rsp+40h] [rbp-C0h] BYREF
  _WORD *v45; // [rsp+48h] [rbp-B8h]
  _WORD v46[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v47; // [rsp+60h] [rbp-A0h]
  char *v48; // [rsp+68h] [rbp-98h]
  _WORD v49[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v51; // [rsp+88h] [rbp-78h] BYREF
  void *v52; // [rsp+90h] [rbp-70h]
  unsigned __int16 v53; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR v54; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v55; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE *p_hObject; // [rsp+C0h] [rbp-40h]
  __int64 v57; // [rsp+C8h] [rbp-38h]
  WCHAR szLongPath[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v59; // [rsp+F0h] [rbp-10h]
  __int64 v60; // [rsp+F8h] [rbp-8h]
  int *v61; // [rsp+100h] [rbp+0h]
  __int64 v62; // [rsp+108h] [rbp+8h]
  _WORD *v63; // [rsp+110h] [rbp+10h]
  __int64 v64; // [rsp+118h] [rbp+18h]
  LPCWSTR v65; // [rsp+120h] [rbp+20h]
  __int64 v66; // [rsp+128h] [rbp+28h]
  LPCWSTR v67; // [rsp+130h] [rbp+30h]
  __int64 v68; // [rsp+138h] [rbp+38h]
  void *v69; // [rsp+140h] [rbp+40h]
  int v70; // [rsp+148h] [rbp+48h]
  int v71; // [rsp+14Ch] [rbp+4Ch]
  HANDLE *v72; // [rsp+150h] [rbp+50h]
  __int64 v73; // [rsp+158h] [rbp+58h]

  v5 = (int *)a1;
  v47 = v49;
  v48 = (char *)v49;
  v49[0] = 0;
  lpszShortPath = v46;
  v45 = v46;
  v46[0] = 0;
  if ( (unsigned int)dword_180062000 > 4 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
  {
    hObject = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (_DWORD)a1,
      (unsigned int)byte_180058551,
      a3,
      a4,
      (__int64)&hObject);
  }
  FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(a2);
  if ( FinalPathByHandle == -2147024891 )
  {
    CurrentProcess = GetCurrentProcess();
    hObject = 0;
    v8 = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
    if ( OpenProcessToken(CurrentProcess, 8u, v8) )
    {
      IsLowRightsToken = UtilIsLowRightsToken(hObject);
    }
    else
    {
      LastError = GetLastError();
      IsLowRightsToken = LastError;
      if ( LastError > 0 )
        IsLowRightsToken = (unsigned __int16)LastError | 0x80070000;
      if ( IsLowRightsToken >= 0 )
        IsLowRightsToken = -2147467259;
    }
    if ( (unsigned __int64)hObject + 1 > 1 )
      CloseHandle(hObject);
    if ( !IsLowRightsToken )
    {
      if ( (unsigned int)dword_180062000 > 4 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
        tlgWriteTransfer_EventWriteTransfer(&dword_180062000, &unk_180058520, 0, 0, 2, &v54);
      FinalPathByHandle = 0;
      goto LABEL_109;
    }
    goto LABEL_22;
  }
  if ( FinalPathByHandle < 0 )
  {
LABEL_22:
    if ( (unsigned int)dword_180062000 <= 2 || (qword_180062010 & 8) == 0 || (qword_180062018 & 8) != qword_180062018 )
      goto LABEL_109;
    LODWORD(hObject) = FinalPathByHandle;
    v11 = word_1800584F2;
    goto LABEL_26;
  }
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)v5 + v13) );
  if ( !v13 )
  {
    FinalPathByHandle = -2147024809;
    goto LABEL_109;
  }
  if ( v47 == v48 || (v14 = 1, *((_WORD *)v48 - 1) != 92) )
    v14 = 0;
  if ( *((_WORD *)v5 + v13 - 1) == 92 && !v14 )
    --v13;
  v15 = 2;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpszShortPath,
                           v5,
                           v13) )
  {
    FinalPathByHandle = -2147024882;
    if ( (unsigned int)dword_180062000 <= 2 || (qword_180062010 & 8) == 0 || (qword_180062018 & 8) != qword_180062018 )
      goto LABEL_109;
    LODWORD(hObject) = -2147024882;
    v11 = (__int16 *)byte_1800584BD;
LABEL_26:
    p_hObject = &hObject;
    v57 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180062000, v11, 0, 0, 3, &v54);
    goto LABEL_109;
  }
  if ( v14
    && (unsigned int)dword_180062000 > 4
    && (qword_180062010 & 8) != 0
    && (qword_180062018 & 8) == qword_180062018 )
  {
    v16 = v45 - lpszShortPath;
    if ( (unsigned __int16)v16 > 0x7FFFu )
      v17 = -2;
    else
      v17 = 2 * v16;
    v50 = (__int64)lpszShortPath;
    v51 = v17;
    v18 = (v48 - (_BYTE *)v47) >> 1;
    if ( (unsigned __int16)v18 > 0x7FFFu )
      v19 = -2;
    else
      v19 = 2 * v18;
    hObject = v47;
    v43 = v19;
    v65 = &v51;
    v66 = 2;
    v67 = lpszShortPath;
    v68 = v17;
    v61 = (int *)&v43;
    v62 = 2;
    v63 = v47;
    v64 = v19;
    if ( v5 )
    {
      v20 = v5;
      v21 = -1;
      do
        ++v21;
      while ( *((_WORD *)v5 + v21) );
      v22 = 2 * v21 + 2;
    }
    else
    {
      v20 = &dword_18004FE4C;
      v22 = 2;
    }
    v59 = (__int64 *)v20;
    v60 = v22;
    tlgWriteTransfer_EventWriteTransfer(&dword_180062000, &dword_18005845C, 0, 0, 7, szLongPath);
  }
  LongPathNameW = GetLongPathNameW(lpszShortPath, szLongPath, 0x105u);
  v24 = LongPathNameW;
  if ( !LongPathNameW )
  {
    v25 = GetLastError();
    FinalPathByHandle = v25;
    if ( v25 > 0 )
      FinalPathByHandle = (unsigned __int16)v25 | 0x80070000;
    if ( (unsigned int)dword_180062000 > 2 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
    {
      LODWORD(hObject) = FinalPathByHandle;
      p_hObject = &hObject;
      v57 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180062000, byte_180058423, 0, 0, 3, &v54);
    }
    goto LABEL_78;
  }
  if ( LongPathNameW > 0x105 )
  {
    utl::make_unique_for_overwrite<wchar_t [0],0>(&hObject, LongPathNameW);
    v27 = hObject;
    if ( hObject )
    {
      if ( v24 > GetLongPathNameW(lpszShortPath, (LPWSTR)hObject, v24) )
      {
        if ( v27 )
        {
          v28 = -1;
          do
            ++v28;
          while ( v27[v28] );
        }
        else
        {
          v28 = 0;
        }
        v26 = (const struct std::nothrow_t *)(unsigned int)-((unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                                                                &lpszShortPath,
                                                                                v27,
                                                                                v28) == 0);
        FinalPathByHandle = (unsigned int)v26 & 0x8007000E;
      }
      else
      {
        FinalPathByHandle = -2147418113;
      }
    }
    else
    {
      FinalPathByHandle = -2147024882;
    }
    if ( v27 )
      operator delete(v27, v26);
LABEL_78:
    if ( FinalPathByHandle < 0 )
      goto LABEL_109;
    goto LABEL_84;
  }
  v29 = -1;
  do
    ++v29;
  while ( szLongPath[v29] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpszShortPath,
                           szLongPath,
                           v29) )
  {
    FinalPathByHandle = -2147024882;
    goto LABEL_109;
  }
  FinalPathByHandle = 0;
LABEL_84:
  if ( !lpszShortPath
    || *lpszShortPath != 92
    || lpszShortPath[1] != 92
    || lpszShortPath[2] != 63
    || (v30 = 0, lpszShortPath[3] != 92) )
  {
    v30 = 1;
  }
  v31 = (unsigned int)(4 * v30);
  v32 = v45 - lpszShortPath;
  if ( v32 != ((v48 - (_BYTE *)v47) >> 1) - v31
    || CompareStringOrdinal(lpszShortPath, v32, (LPCWCH)v47 + v31, v32, 1) != 2 )
  {
    if ( (unsigned int)TelGetWerTelemetryMode() == 3 && (unsigned int)dword_180062000 > 2 )
    {
      v34 = qword_180062018;
      v33 = 0x200000000008LL;
      if ( (qword_180062010 & 0x200000000008LL) != 0 && (qword_180062018 & 0x200000000008LL) == qword_180062018 )
      {
        LODWORD(hObject) = v31;
        v37 = (v48 - (_BYTE *)v47) >> 1;
        if ( (unsigned __int16)v37 > 0x7FFFu )
          v38 = -2;
        else
          v38 = 2 * v37;
        v52 = v47;
        v53 = v38;
        v39 = v45 - lpszShortPath;
        if ( (unsigned __int16)v39 > 0x7FFFu )
          v40 = -2;
        else
          v40 = 2 * v39;
        v54 = lpszShortPath;
        v55 = v40;
        v50 = 0x1000000;
        v72 = &hObject;
        v73 = 4;
        v67 = &v53;
        v68 = 2;
        v69 = v47;
        v70 = v38;
        v71 = 0;
        v63 = &v55;
        v64 = 2;
        v65 = lpszShortPath;
        v66 = v40;
        if ( v5 )
        {
          do
            ++v12;
          while ( *((_WORD *)v5 + v12) );
          v15 = 2 * v12 + 2;
        }
        else
        {
          v5 = &dword_18004FE4C;
        }
        v61 = v5;
        v62 = v15;
        v59 = &v50;
        v60 = 8;
        tlgWriteTransfer_EventWriteTransfer(&dword_180062000, &byte_1800583AF, 0, 0, 9, szLongPath);
      }
    }
    MicrosoftTelemetryAssertTriggeredNoArgs(v34, v33, v35, v36);
    FinalPathByHandle = -2147024735;
  }
LABEL_109:
  if ( (unsigned int)dword_180062000 > 4 && (qword_180062010 & 8) != 0 && (qword_180062018 & 8) == qword_180062018 )
  {
    LODWORD(hObject) = FinalPathByHandle;
    p_hObject = &hObject;
    v57 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180062000, word_180058382, 0, 0, 3, &v54);
  }
  if ( lpszShortPath != v46 )
    operator delete((void *)lpszShortPath, (const struct std::nothrow_t *)&std::nothrow);
  if ( v47 != v49 )
    operator delete(v47, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)FinalPathByHandle;
}

```

## disassembly

```asm
0x18003c344  mov     [rsp-8+arg_10], rbx
0x18003c349  push    rbp
0x18003c34a  push    rsi
0x18003c34b  push    rdi
0x18003c34c  push    r12
0x18003c34e  push    r13
0x18003c350  push    r14
0x18003c352  push    r15
0x18003c354  lea     rbp, [rsp-1F0h]
0x18003c35c  sub     rsp, 2F0h
0x18003c363  mov     rax, cs:__security_cookie
0x18003c36a  xor     rax, rsp
0x18003c36d  mov     [rbp+220h+var_40], rax
0x18003c374  mov     rbx, rdx
0x18003c377  mov     r14, rcx
0x18003c37a  lea     rax, [rsp+320h+var_2B0]
0x18003c37f  mov     [rsp+320h+var_2C0], rax
0x18003c384  lea     rax, [rsp+320h+var_2B0]
0x18003c389  mov     [rsp+320h+var_2B8], rax
0x18003c38e  xor     r12d, r12d
0x18003c391  mov     [rsp+320h+var_2B0], r12w
0x18003c397  lea     rax, [rsp+320h+var_2D0]
0x18003c39c  mov     [rsp+320h+lpszShortPath], rax
0x18003c3a1  lea     rax, [rsp+320h+var_2D0]
0x18003c3a6  mov     [rsp+320h+var_2D8], rax
0x18003c3ab  mov     [rsp+320h+var_2D0], r12w
0x18003c3b1  mov     eax, cs:dword_180062000
0x18003c3b7  lea     r13d, [r12+8]
0x18003c3bc  cmp     eax, 4
0x18003c3bf  jbe     short loc_18003C3FA
0x18003c3c1  mov     rdx, cs:qword_180062018
0x18003c3c8  mov     rax, cs:qword_180062010
0x18003c3cf  test    r13b, al
0x18003c3d2  jz      short loc_18003C3FA
0x18003c3d4  mov     rax, rdx
0x18003c3d7  and     rax, r13
0x18003c3da  cmp     rax, rdx
0x18003c3dd  jnz     short loc_18003C3FA
0x18003c3df  mov     [rsp+320h+hObject], rcx
0x18003c3e4  lea     rax, [rsp+320h+hObject]
0x18003c3e9  mov     qword ptr [rsp+320h+bIgnoreCase], rax
0x18003c3ee  lea     rdx, byte_180058551
0x18003c3f5  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18003c3fa  lea     rdx, [rsp+320h+var_2C0]
0x18003c3ff  mov     rcx, rbx; hFile
0x18003c402  call    ?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18003c407  mov     edi, eax
0x18003c409  cmp     eax, 80070005h
0x18003c40e  jnz     loc_18003C4E0
0x18003c414  call    cs:__imp_GetCurrentProcess
0x18003c41a  mov     rbx, rax
0x18003c41d  mov     [rsp+320h+hObject], r12
0x18003c422  lea     rcx, [rsp+320h+hObject]
0x18003c427  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18003c42c  mov     r8, rax; TokenHandle
0x18003c42f  mov     edx, r13d; DesiredAccess
0x18003c432  mov     rcx, rbx; ProcessHandle
0x18003c435  call    cs:__imp_OpenProcessToken
0x18003c43b  test    eax, eax
0x18003c43d  jnz     short loc_18003C460
0x18003c43f  call    cs:__imp_GetLastError
0x18003c445  mov     ebx, eax
0x18003c447  test    eax, eax
0x18003c449  jle     short loc_18003C454
0x18003c44b  movzx   ebx, ax
0x18003c44e  or      ebx, 80070000h
0x18003c454  mov     eax, 80004005h
0x18003c459  test    ebx, ebx
0x18003c45b  cmovns  ebx, eax
0x18003c45e  jmp     short loc_18003C46C
0x18003c460  mov     rcx, [rsp+320h+hObject]; TokenHandle
0x18003c465  call    ?UtilIsLowRightsToken@@YAJPEAX@Z; UtilIsLowRightsToken(void *)
0x18003c46a  mov     ebx, eax
0x18003c46c  mov     rcx, [rsp+320h+hObject]; hObject
0x18003c471  lea     rdx, [rcx+1]
0x18003c475  cmp     rdx, 1
0x18003c479  jbe     short loc_18003C481
0x18003c47b  call    cs:__imp_CloseHandle
0x18003c481  test    ebx, ebx
0x18003c483  jnz     short loc_18003C4E4
0x18003c485  mov     eax, cs:dword_180062000
0x18003c48b  cmp     eax, 4
0x18003c48e  jbe     short loc_18003C4D8
0x18003c490  mov     rcx, cs:qword_180062018
0x18003c497  mov     rax, cs:qword_180062010
0x18003c49e  test    r13b, al
0x18003c4a1  jz      short loc_18003C4D8
0x18003c4a3  mov     rax, rcx
0x18003c4a6  and     rax, r13
0x18003c4a9  cmp     rax, rcx
0x18003c4ac  jnz     short loc_18003C4D8
0x18003c4ae  lea     rax, [rbp+220h+var_280]
0x18003c4b2  mov     [rsp+320h+var_2F8], rax
0x18003c4b7  mov     [rsp+320h+bIgnoreCase], 2
0x18003c4bf  xor     r9d, r9d
0x18003c4c2  xor     r8d, r8d
0x18003c4c5  lea     rdx, unk_180058520
0x18003c4cc  lea     rcx, dword_180062000
0x18003c4d3  call    _tlgWriteTransfer_EventWriteTransfer
0x18003c4d8  mov     edi, r12d
0x18003c4db  jmp     loc_18003CA82
0x18003c4e0  test    edi, edi
0x18003c4e2  jns     short loc_18003C561
0x18003c4e4  mov     eax, cs:dword_180062000
0x18003c4ea  mov     ebx, 2
0x18003c4ef  cmp     eax, ebx
0x18003c4f1  jbe     loc_18003CA82
0x18003c4f7  mov     rcx, cs:qword_180062018
0x18003c4fe  mov     rax, cs:qword_180062010
0x18003c505  test    r13b, al
0x18003c508  jz      loc_18003CA82
0x18003c50e  mov     rax, rcx
0x18003c511  and     rax, r13
0x18003c514  cmp     rax, rcx
0x18003c517  jnz     loc_18003CA82
0x18003c51d  mov     dword ptr [rsp+320h+hObject], edi
0x18003c521  lea     rdx, word_1800584F2
0x18003c528  lea     rax, [rsp+320h+hObject]
0x18003c52d  mov     [rbp+220h+var_260], rax
0x18003c531  lea     rax, [rbp+220h+var_280]
0x18003c535  xor     r9d, r9d
0x18003c538  mov     [rsp+320h+var_2F8], rax
0x18003c53d  xor     r8d, r8d
0x18003c540  mov     [rsp+320h+bIgnoreCase], 3
0x18003c548  mov     [rbp+220h+var_258], 4
0x18003c550  lea     rcx, dword_180062000
0x18003c557  call    _tlgWriteTransfer_EventWriteTransfer
0x18003c55c  jmp     loc_18003CA82
0x18003c561  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003c565  mov     r8, r15
0x18003c568  inc     r8
0x18003c56b  cmp     [r14+r8*2], r12w
0x18003c570  jnz     short loc_18003C568
0x18003c572  cmp     r8, 1
0x18003c576  jnb     short loc_18003C582
0x18003c578  mov     edi, 80070057h
0x18003c57d  jmp     loc_18003CA82
0x18003c582  mov     ecx, 5Ch ; '\'
0x18003c587  mov     rax, [rsp+320h+var_2B8]
0x18003c58c  cmp     [rsp+320h+var_2C0], rax
0x18003c591  jz      short loc_18003C59C
0x18003c593  cmp     cx, [rax-2]
0x18003c597  mov     dil, 1
0x18003c59a  jz      short loc_18003C59F
0x18003c59c  mov     dil, r12b
0x18003c59f  cmp     [r14+r8*2-2], cx
0x18003c5a5  jnz     short loc_18003C5AF
0x18003c5a7  test    dil, dil
0x18003c5aa  jnz     short loc_18003C5AF
0x18003c5ac  dec     r8
0x18003c5af  mov     rdx, r14
0x18003c5b2  lea     rcx, [rsp+320h+lpszShortPath]
0x18003c5b7  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18003c5bc  mov     ebx, 2
0x18003c5c1  test    al, al
0x18003c5c3  jnz     short loc_18003C612
0x18003c5c5  mov     edi, 8007000Eh
0x18003c5ca  mov     eax, cs:dword_180062000
0x18003c5d0  cmp     eax, ebx
0x18003c5d2  jbe     loc_18003CA82
0x18003c5d8  mov     rcx, cs:qword_180062018
0x18003c5df  mov     rax, cs:qword_180062010
0x18003c5e6  test    r13b, al
0x18003c5e9  jz      loc_18003CA82
0x18003c5ef  mov     rax, rcx
0x18003c5f2  and     rax, r13
0x18003c5f5  cmp     rax, rcx
0x18003c5f8  jnz     loc_18003CA82
0x18003c5fe  mov     dword ptr [rsp+320h+hObject], 8007000Eh
0x18003c606  lea     rdx, byte_1800584BD
0x18003c60d  jmp     loc_18003C528
0x18003c612  mov     r10d, 7FFFh
0x18003c618  mov     r9d, 0FFFEh
0x18003c61e  test    dil, dil
0x18003c621  jz      loc_18003C73D
0x18003c627  mov     eax, cs:dword_180062000
0x18003c62d  cmp     eax, 4
0x18003c630  jbe     loc_18003C73D
0x18003c636  mov     rcx, cs:qword_180062018
0x18003c63d  mov     rax, cs:qword_180062010
0x18003c644  test    r13b, al
0x18003c647  jz      loc_18003C73D
0x18003c64d  mov     rax, rcx
0x18003c650  and     rax, r13
0x18003c653  cmp     rax, rcx
0x18003c656  jnz     loc_18003C73D
0x18003c65c  mov     rax, [rsp+320h+var_2D8]
0x18003c661  mov     r8, [rsp+320h+lpszShortPath]
0x18003c666  sub     rax, r8
0x18003c669  sar     rax, 1
0x18003c66c  cmp     ax, r10w
0x18003c670  ja      short loc_18003C677
0x18003c672  add     ax, ax
0x18003c675  jmp     short loc_18003C67B
0x18003c677  movzx   eax, r9w
0x18003c67b  mov     [rbp+220h+var_2A0], r8
0x18003c67f  mov     [rbp+220h+var_298], ax
0x18003c683  mov     rcx, [rsp+320h+var_2B8]
0x18003c688  mov     rdx, [rsp+320h+var_2C0]
0x18003c68d  sub     rcx, rdx
0x18003c690  sar     rcx, 1
0x18003c693  cmp     cx, r10w
0x18003c697  ja      short loc_18003C69E
0x18003c699  add     cx, cx
0x18003c69c  jmp     short loc_18003C6A2
0x18003c69e  movzx   ecx, r9w
0x18003c6a2  mov     [rsp+320h+hObject], rdx
0x18003c6a7  mov     [rsp+320h+var_2E8], cx
0x18003c6ac  lea     r9, [rbp+220h+var_298]
0x18003c6b0  mov     [rbp+220h+var_200], r9
0x18003c6b4  mov     [rbp+220h+var_1F8], rbx
0x18003c6b8  mov     [rbp+220h+var_1F0], r8
0x18003c6bc  movzx   eax, ax
0x18003c6bf  mov     dword ptr [rbp+220h+var_1E8], eax
0x18003c6c2  mov     dword ptr [rbp+220h+var_1E8+4], r12d
0x18003c6c6  lea     rax, [rsp+320h+var_2E8]
0x18003c6cb  mov     [rbp+220h+var_220], rax
0x18003c6cf  mov     [rbp+220h+var_218], rbx
0x18003c6d3  mov     [rbp+220h+var_210], rdx
0x18003c6d7  movzx   eax, cx
0x18003c6da  mov     dword ptr [rbp+220h+var_208], eax
0x18003c6dd  mov     dword ptr [rbp+220h+var_208+4], r12d
0x18003c6e1  test    r14, r14
0x18003c6e4  jz      short loc_18003C6FF
0x18003c6e6  mov     rcx, r14
0x18003c6e9  mov     rax, r15
0x18003c6ec  inc     rax
0x18003c6ef  cmp     [r14+rax*2], r12w
0x18003c6f4  jnz     short loc_18003C6EC
0x18003c6f6  lea     eax, ds:2[rax*2]
0x18003c6fd  jmp     short loc_18003C708
0x18003c6ff  lea     rcx, dword_18004FE4C
0x18003c706  mov     eax, ebx
0x18003c708  mov     [rbp+220h+var_230], rcx
0x18003c70c  mov     dword ptr [rbp+220h+var_228], eax
0x18003c70f  mov     dword ptr [rbp+220h+var_228+4], r12d
0x18003c713  lea     rax, [rbp+220h+szLongPath]
0x18003c717  mov     [rsp+320h+var_2F8], rax
0x18003c71c  mov     [rsp+320h+bIgnoreCase], 7
0x18003c724  xor     r9d, r9d
0x18003c727  xor     r8d, r8d
0x18003c72a  lea     rdx, dword_18005845C
0x18003c731  lea     rcx, dword_180062000
0x18003c738  call    _tlgWriteTransfer_EventWriteTransfer
0x18003c73d  mov     esi, 105h
0x18003c742  mov     r8d, esi; cchBuffer
0x18003c745  lea     rdx, [rbp+220h+szLongPath]; lpszLongPath
0x18003c749  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x18003c74e  call    cs:__imp_GetLongPathNameW
0x18003c754  mov     edi, eax
0x18003c756  test    eax, eax
0x18003c758  jnz     loc_18003C7EB
0x18003c75e  call    cs:__imp_GetLastError
0x18003c764  mov     edi, eax
0x18003c766  test    eax, eax
0x18003c768  jle     short loc_18003C773
0x18003c76a  movzx   edi, ax
0x18003c76d  or      edi, 80070000h
0x18003c773  mov     eax, cs:dword_180062000
0x18003c779  cmp     eax, ebx
0x18003c77b  jbe     loc_18003C86B
0x18003c781  mov     rcx, cs:qword_180062018
0x18003c788  mov     rax, cs:qword_180062010
0x18003c78f  test    r13b, al
0x18003c792  jz      loc_18003C86B
0x18003c798  mov     rax, rcx
0x18003c79b  and     rax, r13
0x18003c79e  cmp     rax, rcx
0x18003c7a1  jnz     loc_18003C86B
0x18003c7a7  mov     dword ptr [rsp+320h+hObject], edi
0x18003c7ab  lea     rax, [rsp+320h+hObject]
0x18003c7b0  mov     [rbp+220h+var_260], rax
0x18003c7b4  mov     [rbp+220h+var_258], 4
0x18003c7bc  lea     rax, [rbp+220h+var_280]
0x18003c7c0  mov     [rsp+320h+var_2F8], rax
0x18003c7c5  mov     [rsp+320h+bIgnoreCase], 3
0x18003c7cd  xor     r9d, r9d
0x18003c7d0  xor     r8d, r8d
0x18003c7d3  lea     rdx, byte_180058423
0x18003c7da  lea     rcx, dword_180062000
0x18003c7e1  call    _tlgWriteTransfer_EventWriteTransfer
0x18003c7e6  jmp     loc_18003C86B
0x18003c7eb  cmp     edi, esi
0x18003c7ed  jbe     loc_18003C875
0x18003c7f3  mov     rdx, rdi
0x18003c7f6  lea     rcx, [rsp+320h+hObject]
0x18003c7fb  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x18003c800  mov     rsi, [rsp+320h+hObject]
0x18003c805  test    rsi, rsi
0x18003c808  jnz     short loc_18003C811
0x18003c80a  mov     edi, 8007000Eh
0x18003c80f  jmp     short loc_18003C85E
0x18003c811  mov     r8d, edi; cchBuffer
0x18003c814  mov     rdx, rsi; lpszLongPath
0x18003c817  mov     rcx, [rsp+320h+lpszShortPath]; lpszShortPath
0x18003c81c  call    cs:__imp_GetLongPathNameW
0x18003c822  cmp     edi, eax
0x18003c824  ja      short loc_18003C82D
0x18003c826  mov     edi, 8000FFFFh
0x18003c82b  jmp     short loc_18003C85E
  ... truncated ...
```
