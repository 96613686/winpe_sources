# CHttpBase::SendRequest(uchar *,uint)

- ea: `0x180046d9c`
- end: `0x1800472b4`
- name: `?SendRequest@CHttpBase@@IEAAJPEAEI@Z`
- size: `1304`
- prototype: `int(CHttpBase *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180043bc0`
- `0x180045c78`
- `0x180046c7c`

## callees

- `0x180001284`
- `0x180001290`
- `0x1800046c8`
- `0x180034bb0`
- `0x1800370d8`
- `0x180046d9c`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004706a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004713f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800471eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004706a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004713f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800471eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047205`
- `WINHTTP!WinHttpSetOption` at `0x180046e49`
- `WINHTTP!WinHttpSetOption` at `0x180046e49`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046f83`
- `WINHTTP!WinHttpQueryHeaders` at `0x18004711c`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800471d0`
- `WINHTTP!WinHttpQueryHeaders` at `0x180046f83`
- `WINHTTP!WinHttpQueryHeaders` at `0x18004711c`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800471d0`
- `WINHTTP!WinHttpReceiveResponse` at `0x180046e82`
- `WINHTTP!WinHttpReceiveResponse` at `0x180046e82`
- `WINHTTP!WinHttpSendRequest` at `0x180046e70`
- `WINHTTP!WinHttpSendRequest` at `0x180046e70`
- `USER32!GetDesktopWindow` at `0x180046ef4`
- `USER32!GetDesktopWindow` at `0x180046f43`
- `USER32!GetDesktopWindow` at `0x180046fdc`
- `USER32!GetDesktopWindow` at `0x18004700f`
- `USER32!GetDesktopWindow` at `0x180046ef4`
- `USER32!GetDesktopWindow` at `0x180046f43`
- `USER32!GetDesktopWindow` at `0x180046fdc`
- `USER32!GetDesktopWindow` at `0x18004700f`
- `WININET!HttpQueryInfoW` at `0x180046f97`
- `WININET!HttpQueryInfoW` at `0x180047130`
- `WININET!HttpQueryInfoW` at `0x1800471e1`
- `WININET!HttpQueryInfoW` at `0x180046f97`
- `WININET!HttpQueryInfoW` at `0x180047130`
- `WININET!HttpQueryInfoW` at `0x1800471e1`
- `WININET!InternetErrorDlg` at `0x180046f0f`
- `WININET!InternetErrorDlg` at `0x180046ff9`
- `WININET!InternetErrorDlg` at `0x180047045`
- `WININET!InternetErrorDlg` at `0x180046f0f`
- `WININET!InternetErrorDlg` at `0x180046ff9`
- `WININET!InternetErrorDlg` at `0x180047045`
- `WININET!HttpSendRequestW` at `0x180046ebb`
- `WININET!HttpSendRequestW` at `0x180046ebb`
- `WININET!IncrementUrlCacheHeaderData` at `0x180047264`
- `WININET!IncrementUrlCacheHeaderData` at `0x180047264`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHttpBase::SendRequest(CHttpBase *this, unsigned __int8 *a2, DWORD a3)
{
  int v6; // r12d
  signed int v7; // ebx
  int (__fastcall *v8)(_QWORD, __int64, _QWORD, _QWORD); // rax
  void *v9; // rcx
  BOOL v10; // ebx
  const char *v11; // rcx
  DWORD LastError; // ebx
  HWND DesktopWindow; // rax
  DWORD v14; // r8d
  DWORD v15; // eax
  bool v16; // zf
  _DWORD *v17; // rsi
  void *v18; // rcx
  BOOL v19; // eax
  HWND v20; // rax
  HWND v21; // rbx
  void *v22; // rcx
  BOOL v23; // eax
  signed int v24; // eax
  void *v25; // r8
  void *v26; // rcx
  BOOL v27; // eax
  signed int v28; // eax
  signed int v29; // eax
  int (__fastcall *v30)(_QWORD, __int64, _QWORD, _QWORD); // rax
  DWORD dwBufferLength; // [rsp+40h] [rbp-20h] BYREF
  DWORD dwData; // [rsp+44h] [rbp-1Ch] BYREF
  _QWORD v34[3]; // [rsp+48h] [rbp-18h] BYREF
  DWORD v35; // [rsp+A0h] [rbp+40h] BYREF
  int Buffer; // [rsp+B8h] [rbp+58h] BYREF

  v34[1] = -2;
  dwBufferLength = 4;
  Buffer = 0;
  v35 = 0;
  v6 = 0;
  if ( (*((_BYTE *)this + 40) & 2) == 0 && (!a3 || !a2) )
  {
    v7 = -2147024809;
    goto LABEL_76;
  }
  v8 = (int (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v8 && v8(*((unsigned int *)this + 4), 315138, 0, *((_QWORD *)this + 3)) < 0 )
  {
    v7 = -2147168447;
    goto LABEL_76;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      v9 = (void *)*((_QWORD *)this + 13);
      if ( g_fGlobalOptionUseWinhttp )
      {
        Buffer = 1;
        WinHttpSetOption(v9, 0x4Du, &Buffer, 4u);
        GetLastError();
        v10 = WinHttpSendRequest(*((HINTERNET *)this + 13), 0, 0, a2, a3, a3, 0);
        if ( v10 )
        {
          v10 = WinHttpReceiveResponse(*((HINTERNET *)this + 13), 0);
          v11 = "[msdrm]:SUCCESS WinHttpReceiveResponse ";
          if ( !v10 )
            v11 = "[msdrm]:FAILED  WinHttpReceiveResponse ";
        }
        else
        {
          v11 = "[msdrm]:FAILED WinHttpSendRequest ";
        }
        _RTLTRACE(v11);
      }
      else
      {
        v10 = HttpSendRequestW(v9, 0, 0, a2, a3);
      }
      if ( v10 )
        break;
      LastError = GetLastError();
      if ( ((LastError - 12037) & 0xFFFFFFF6) != 0 || LastError == 12046 )
      {
        if ( LastError == 12044 )
        {
          v6 = 1;
          if ( g_fGlobalOptionUseWinhttp )
            goto LABEL_41;
          DesktopWindow = GetDesktopWindow();
          v14 = 12044;
          goto LABEL_21;
        }
        if ( LastError == 12157 )
        {
LABEL_41:
          v7 = -2147168445;
          goto LABEL_76;
        }
        *((_DWORD *)this + 30) = GetLastError();
LABEL_44:
        v7 = -2147168453;
        goto LABEL_76;
      }
      if ( g_fGlobalOptionUseWinhttp )
        goto LABEL_41;
      DesktopWindow = GetDesktopWindow();
      v14 = LastError;
LABEL_21:
      v15 = InternetErrorDlg(DesktopWindow, *((HINTERNET *)this + 13), v14, 7u, 0);
LABEL_22:
      if ( v15 != 12032 )
      {
        v16 = v15 == 0;
        goto LABEL_40;
      }
    }
    v17 = (_DWORD *)((char *)this + 120);
    v18 = (void *)*((_QWORD *)this + 13);
    if ( g_fGlobalOptionUseWinhttp )
      v19 = WinHttpQueryHeaders(
              v18,
              0x20000013u,
              g_wszWINHTTP_HEADER_NAME_BY_INDEX,
              (char *)this + 120,
              &dwBufferLength,
              lpdwWINHTTP_NO_HEADER_INDEX);
    else
      v19 = HttpQueryInfoW(v18, 0x20000013u, (char *)this + 120, &dwBufferLength, 0);
    if ( !v19 )
    {
      v29 = GetLastError();
      v7 = v29;
      if ( v29 > 0 )
        v7 = (unsigned __int16)v29 | 0x80070000;
LABEL_74:
      if ( v7 >= 0 )
        v7 = -2147467259;
      goto LABEL_76;
    }
    if ( *v17 == 302 )
      break;
    if ( *v17 != 401 && *v17 != 407 )
    {
      if ( *v17 == 12044 )
      {
        v6 = 1;
        if ( g_fGlobalOptionUseWinhttp )
          goto LABEL_41;
        v20 = GetDesktopWindow();
        v15 = InternetErrorDlg(v20, *((HINTERNET *)this + 13), 0x2F0Cu, 7u, 0);
        goto LABEL_22;
      }
      v7 = 0;
      switch ( *v17 )
      {
        case 0xC8:
        case 0x64:
          goto LABEL_76;
        case 0x194:
          v7 = -2147168438;
          goto LABEL_76;
        case 0x12F:
          v7 = -2147168421;
          goto LABEL_76;
        case 0x19A:
          v7 = -2147168420;
          goto LABEL_76;
      }
      if ( *v17 != 502 )
      {
        LOBYTE(v7) = *v17 != 403;
        v7 -= 2147168445;
        goto LABEL_76;
      }
      goto LABEL_44;
    }
    if ( (*((_BYTE *)this + 40) & 0x10) != 0 )
      goto LABEL_41;
    v21 = GetDesktopWindow();
    if ( g_fGlobalOptionUseWinhttp )
      goto LABEL_41;
    _RTLTRACE("[msdrm]:CHttpBase:Wininet Dialog Pop up for taking credentials happened");
    v16 = InternetErrorDlg(v21, *((HINTERNET *)this + 13), 0x2EEEu, 7u, 0) == 12032;
LABEL_40:
    if ( !v16 )
      goto LABEL_41;
  }
  v22 = (void *)*((_QWORD *)this + 13);
  if ( g_fGlobalOptionUseWinhttp )
    v23 = WinHttpQueryHeaders(v22, 0x21u, g_wszWINHTTP_HEADER_NAME_BY_INDEX, 0, &v35, lpdwWINHTTP_NO_HEADER_INDEX);
  else
    v23 = HttpQueryInfoW(v22, 0x21u, 0, &v35, 0);
  if ( v23 )
    goto LABEL_63;
  v24 = GetLastError();
  v7 = v24;
  if ( v24 == 122 )
    goto LABEL_63;
  if ( v24 > 0 )
    v7 = (unsigned __int16)v24 | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_63:
    operator delete(*((void **)this + 14));
    v25 = operator new[](saturated_mul(++v35, 2u));
    *((_QWORD *)this + 14) = v25;
    if ( v25 )
    {
      v26 = (void *)*((_QWORD *)this + 13);
      if ( g_fGlobalOptionUseWinhttp )
        v27 = WinHttpQueryHeaders(v26, 0x21u, g_wszWINHTTP_HEADER_NAME_BY_INDEX, v25, &v35, lpdwWINHTTP_NO_HEADER_INDEX);
      else
        v27 = HttpQueryInfoW(v26, 0x21u, v25, &v35, 0);
      if ( !v27 )
      {
        v28 = GetLastError();
        v7 = v28;
        if ( v28 > 0 )
          v7 = (unsigned __int16)v28 | 0x80070000;
        goto LABEL_74;
      }
      v7 = 315360;
    }
    else
    {
      v7 = -2147024882;
    }
  }
LABEL_76:
  if ( !g_fGlobalOptionUseWinhttp && v7 == -2147168445 && v6 )
  {
    dwData = 0;
    v34[0] = 0;
    if ( CDRMCLock::Lock((CDRMCLock *)v34, L"msdrm_SSLClearState") >= 0 )
      IncrementUrlCacheHeaderData(0xEu, &dwData);
    CDRMCLock::~CDRMCLock((CDRMCLock *)v34);
  }
  v30 = (int (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v30 && !v7 && v30(*((unsigned int *)this + 4), 315139, 0, *((_QWORD *)this + 3)) < 0 )
    return (unsigned int)-2147168447;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180046d9c  mov     rax, rsp
0x180046d9f  push    rbp
0x180046da0  push    rsi
0x180046da1  push    rdi
0x180046da2  push    r12
0x180046da4  push    r13
0x180046da6  push    r14
0x180046da8  push    r15
0x180046daa  mov     rbp, rsp
0x180046dad  sub     rsp, 60h
0x180046db1  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180046db9  mov     [rax+10h], rbx
0x180046dbd  mov     r14d, r8d
0x180046dc0  mov     r15, rdx
0x180046dc3  mov     rdi, rcx
0x180046dc6  mov     [rbp+dwBufferLength], 4
0x180046dcd  xor     r13d, r13d
0x180046dd0  mov     [rbp+Buffer], r13d
0x180046dd4  mov     [rbp+arg_0], r13d
0x180046dd8  mov     r12d, r13d
0x180046ddb  mov     esi, 8004CF41h
0x180046de0  test    byte ptr [rcx+28h], 2
0x180046de4  jnz     short loc_180046DFA
0x180046de6  test    r8d, r8d
0x180046de9  jz      short loc_180046DF0
0x180046deb  test    rdx, rdx
0x180046dee  jnz     short loc_180046DFA
0x180046df0  mov     ebx, 80070057h
0x180046df5  jmp     loc_180047229
0x180046dfa  mov     rax, [rcx+8]
0x180046dfe  test    rax, rax
0x180046e01  jz      short loc_180046E22
0x180046e03  mov     r9, [rcx+18h]
0x180046e07  xor     r8d, r8d
0x180046e0a  mov     edx, 4CF02h
0x180046e0f  mov     ecx, [rcx+10h]
0x180046e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e17  test    eax, eax
0x180046e19  jns     short loc_180046E22
0x180046e1b  mov     ebx, esi
0x180046e1d  jmp     loc_180047229
0x180046e22  mov     esi, 2F00h
0x180046e27  mov     rcx, [rdi+68h]; hRequest
0x180046e2b  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r13d; int g_fGlobalOptionUseWinhttp
0x180046e32  jz      short loc_180046EAE
0x180046e34  mov     [rbp+Buffer], 1
0x180046e3b  mov     r9d, 4; dwBufferLength
0x180046e41  lea     r8, [rbp+Buffer]; lpBuffer
0x180046e45  lea     edx, [r9+49h]; dwOption
0x180046e49  call    cs:__imp_WinHttpSetOption
0x180046e4f  call    cs:__imp_GetLastError
0x180046e55  mov     [rsp+60h+dwContext], r13; dwContext
0x180046e5a  mov     [rsp+60h+dwTotalLength], r14d; dwTotalLength
0x180046e5f  mov     [rsp+60h+dwOptionalLength], r14d; dwOptionalLength
0x180046e64  mov     r9, r15; lpOptional
0x180046e67  xor     r8d, r8d; dwHeadersLength
0x180046e6a  xor     edx, edx; lpszHeaders
0x180046e6c  mov     rcx, [rdi+68h]; hRequest
0x180046e70  call    cs:__imp_WinHttpSendRequest
0x180046e76  mov     ebx, eax
0x180046e78  test    eax, eax
0x180046e7a  jz      short loc_180046EA0
0x180046e7c  xor     edx, edx; lpReserved
0x180046e7e  mov     rcx, [rdi+68h]; hRequest
0x180046e82  call    cs:__imp_WinHttpReceiveResponse
0x180046e88  mov     ebx, eax
0x180046e8a  lea     rax, aMsdrmFailedWin; "[msdrm]:FAILED  WinHttpReceiveResponse "
0x180046e91  lea     rcx, aMsdrmSuccessWi; "[msdrm]:SUCCESS WinHttpReceiveResponse "
0x180046e98  test    ebx, ebx
0x180046e9a  cmovz   rcx, rax
0x180046e9e  jmp     short loc_180046EA7
0x180046ea0  lea     rcx, aMsdrmFailedWin_0; "[msdrm]:FAILED WinHttpSendRequest "
0x180046ea7  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180046eac  jmp     short loc_180046EC3
0x180046eae  mov     [rsp+60h+dwOptionalLength], r14d; dwOptionalLength
0x180046eb3  mov     r9, r15; lpOptional
0x180046eb6  xor     r8d, r8d; dwHeadersLength
0x180046eb9  xor     edx, edx; lpszHeaders
0x180046ebb  call    cs:__imp_HttpSendRequestW
0x180046ec1  mov     ebx, eax
0x180046ec3  test    ebx, ebx
0x180046ec5  jnz     loc_180046F4E
0x180046ecb  call    cs:__imp_GetLastError
0x180046ed1  mov     ebx, eax
0x180046ed3  add     eax, 0FFFFD0FBh
0x180046ed8  test    eax, 0FFFFFFF6h
0x180046edd  jnz     short loc_180046F24
0x180046edf  cmp     ebx, 2F0Eh
0x180046ee5  jz      short loc_180046F24
0x180046ee7  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r13d; int g_fGlobalOptionUseWinhttp
0x180046eee  jnz     loc_180047058
0x180046ef4  call    cs:__imp_GetDesktopWindow
0x180046efa  mov     r8d, ebx; dwError
0x180046efd  mov     r9d, 7; dwFlags
0x180046f03  mov     qword ptr [rsp+60h+dwOptionalLength], r13; lppvData
0x180046f08  mov     rdx, [rdi+68h]; hRequest
0x180046f0c  mov     rcx, rax; hWnd
0x180046f0f  call    cs:__imp_InternetErrorDlg
0x180046f15  cmp     eax, esi
0x180046f17  jz      loc_180046E27
0x180046f1d  test    eax, eax
0x180046f1f  jmp     loc_180047052
0x180046f24  cmp     ebx, 2F0Ch
0x180046f2a  jnz     loc_180047062
0x180046f30  mov     r12d, 1
0x180046f36  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r13d; int g_fGlobalOptionUseWinhttp
0x180046f3d  jnz     loc_180047058
0x180046f43  call    cs:__imp_GetDesktopWindow
0x180046f49  mov     r8d, ebx
0x180046f4c  jmp     short loc_180046EFD
0x180046f4e  lea     rsi, [rdi+78h]
0x180046f52  mov     rcx, [rdi+68h]; hRequest
0x180046f56  mov     edx, 20000013h; dwInfoLevel
0x180046f5b  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r13d; int g_fGlobalOptionUseWinhttp
0x180046f62  jz      short loc_180046F8B
0x180046f64  mov     rax, cs:?lpdwWINHTTP_NO_HEADER_INDEX@@3PEAKEA; ulong * lpdwWINHTTP_NO_HEADER_INDEX
0x180046f6b  mov     qword ptr [rsp+60h+dwTotalLength], rax; lpdwIndex
0x180046f70  lea     rax, [rbp+dwBufferLength]
0x180046f74  mov     qword ptr [rsp+60h+dwOptionalLength], rax; lpdwBufferLength
0x180046f79  mov     r9, rsi; lpBuffer
0x180046f7c  mov     r8, cs:?g_wszWINHTTP_HEADER_NAME_BY_INDEX@@3PEAGEA; pwszName
0x180046f83  call    cs:__imp_WinHttpQueryHeaders
0x180046f89  jmp     short loc_180046F9D
0x180046f8b  mov     qword ptr [rsp+60h+dwOptionalLength], r13; lpdwIndex
0x180046f90  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x180046f94  mov     r8, rsi; lpBuffer
0x180046f97  call    cs:__imp_HttpQueryInfoW
0x180046f9d  test    eax, eax
0x180046f9f  jz      loc_180047205
0x180046fa5  cmp     dword ptr [rsi], 12Eh
0x180046fab  jz      loc_1800470E7
0x180046fb1  cmp     dword ptr [rsi], 191h
0x180046fb7  jz      short loc_180047009
0x180046fb9  cmp     dword ptr [rsi], 197h
0x180046fbf  jz      short loc_180047009
0x180046fc1  cmp     dword ptr [rsi], 2F0Ch
0x180046fc7  jnz     loc_18004707D
0x180046fcd  mov     r12d, 1
0x180046fd3  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r13d; int g_fGlobalOptionUseWinhttp
0x180046fda  jnz     short loc_180047058
0x180046fdc  call    cs:__imp_GetDesktopWindow
0x180046fe2  mov     qword ptr [rsp+60h+dwOptionalLength], r13; lppvData
0x180046fe7  lea     r9d, [r12+6]; dwFlags
0x180046fec  mov     r8d, 2F0Ch; dwError
0x180046ff2  mov     rdx, [rdi+68h]; hRequest
0x180046ff6  mov     rcx, rax; hWnd
0x180046ff9  call    cs:__imp_InternetErrorDlg
0x180046fff  mov     esi, 2F00h
0x180047004  jmp     loc_180046F15
0x180047009  test    byte ptr [rdi+28h], 10h
0x18004700d  jnz     short loc_180047058
0x18004700f  call    cs:__imp_GetDesktopWindow
0x180047015  mov     rbx, rax
0x180047018  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r13d; int g_fGlobalOptionUseWinhttp
0x18004701f  jnz     short loc_180047058
0x180047021  lea     rcx, aMsdrmChttpbase_1; "[msdrm]:CHttpBase:Wininet Dialog Pop up"...
0x180047028  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004702d  mov     qword ptr [rsp+60h+dwOptionalLength], r13; lppvData
0x180047032  mov     r9d, 7; dwFlags
0x180047038  mov     r8d, 2EEEh; dwError
0x18004703e  mov     rdx, [rdi+68h]; hRequest
0x180047042  mov     rcx, rbx; hWnd
0x180047045  call    cs:__imp_InternetErrorDlg
0x18004704b  mov     esi, 2F00h
0x180047050  cmp     eax, esi
0x180047052  jz      loc_180046E27
0x180047058  mov     ebx, 8004CF43h
0x18004705d  jmp     loc_180047224
0x180047062  cmp     ebx, 2F7Dh
0x180047068  jz      short loc_180047058
0x18004706a  call    cs:__imp_GetLastError
0x180047070  mov     [rdi+78h], eax
0x180047073  mov     ebx, 8004CF3Bh
0x180047078  jmp     loc_180047224
0x18004707d  mov     ebx, r13d
0x180047080  cmp     dword ptr [rsi], 0C8h
0x180047086  jz      loc_180047224
0x18004708c  cmp     dword ptr [rsi], 64h ; 'd'
0x18004708f  jz      loc_180047224
0x180047095  cmp     dword ptr [rsi], 194h
0x18004709b  jnz     short loc_1800470A7
0x18004709d  mov     ebx, 8004CF4Ah
0x1800470a2  jmp     loc_180047224
0x1800470a7  cmp     dword ptr [rsi], 12Fh
0x1800470ad  jnz     short loc_1800470B9
0x1800470af  mov     ebx, 8004CF5Bh
0x1800470b4  jmp     loc_180047224
0x1800470b9  cmp     dword ptr [rsi], 19Ah
0x1800470bf  jnz     short loc_1800470CB
0x1800470c1  mov     ebx, 8004CF5Ch
0x1800470c6  jmp     loc_180047224
0x1800470cb  cmp     dword ptr [rsi], 1F6h
0x1800470d1  jz      short loc_180047073
0x1800470d3  cmp     dword ptr [rsi], 193h
0x1800470d9  setnz   bl
0x1800470dc  add     ebx, 8004CF43h
0x1800470e2  jmp     loc_180047224
0x1800470e7  mov     rcx, [rdi+68h]; hRequest
0x1800470eb  mov     r14d, 21h ; '!'
0x1800470f1  mov     edx, r14d; dwInfoLevel
0x1800470f4  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r13d; int g_fGlobalOptionUseWinhttp
0x1800470fb  jz      short loc_180047124
0x1800470fd  mov     rax, cs:?lpdwWINHTTP_NO_HEADER_INDEX@@3PEAKEA; ulong * lpdwWINHTTP_NO_HEADER_INDEX
0x180047104  mov     qword ptr [rsp+60h+dwTotalLength], rax; lpdwIndex
0x180047109  lea     rax, [rbp+arg_0]
0x18004710d  mov     qword ptr [rsp+60h+dwOptionalLength], rax; lpdwBufferLength
0x180047112  xor     r9d, r9d; lpBuffer
0x180047115  mov     r8, cs:?g_wszWINHTTP_HEADER_NAME_BY_INDEX@@3PEAGEA; pwszName
0x18004711c  call    cs:__imp_WinHttpQueryHeaders
0x180047122  jmp     short loc_180047136
0x180047124  mov     qword ptr [rsp+60h+dwOptionalLength], r13; lpdwIndex
0x180047129  lea     r9, [rbp+arg_0]; lpdwBufferLength
0x18004712d  xor     r8d, r8d; lpBuffer
0x180047130  call    cs:__imp_HttpQueryInfoW
0x180047136  mov     esi, 80070000h
0x18004713b  test    eax, eax
0x18004713d  jnz     short loc_18004715D
0x18004713f  call    cs:__imp_GetLastError
0x180047145  mov     ebx, eax
0x180047147  cmp     eax, 7Ah ; 'z'
0x18004714a  jz      short loc_18004715D
0x18004714c  test    eax, eax
0x18004714e  jle     short loc_180047155
0x180047150  movzx   ebx, ax
0x180047153  or      ebx, esi
0x180047155  test    ebx, ebx
0x180047157  js      loc_180047224
0x18004715d  mov     rcx, [rdi+70h]; Block
0x180047161  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180047166  mov     ecx, [rbp+arg_0]
0x180047169  inc     ecx
0x18004716b  mov     [rbp+arg_0], ecx
0x18004716e  mov     edx, ecx
0x180047170  mov     eax, 2
0x180047175  mul     rdx
0x180047178  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004717f  cmovb   rax, rcx
0x180047183  mov     rcx, rax; unsigned __int64
0x180047186  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004718b  mov     r8, rax; lpBuffer
0x18004718e  mov     [rdi+70h], rax
0x180047192  test    rax, rax
0x180047195  jnz     short loc_1800471A1
0x180047197  mov     ebx, 8007000Eh
0x18004719c  jmp     loc_180047224
0x1800471a1  mov     rcx, [rdi+68h]; hRequest
0x1800471a5  mov     edx, r14d; dwInfoLevel
0x1800471a8  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r13d; int g_fGlobalOptionUseWinhttp
0x1800471af  jz      short loc_1800471D8
0x1800471b1  mov     rax, cs:?lpdwWINHTTP_NO_HEADER_INDEX@@3PEAKEA; ulong * lpdwWINHTTP_NO_HEADER_INDEX
0x1800471b8  mov     qword ptr [rsp+60h+dwTotalLength], rax; lpdwIndex
0x1800471bd  lea     rax, [rbp+arg_0]
0x1800471c1  mov     qword ptr [rsp+60h+dwOptionalLength], rax; lpdwBufferLength
0x1800471c6  mov     r9, r8; lpBuffer
0x1800471c9  mov     r8, cs:?g_wszWINHTTP_HEADER_NAME_BY_INDEX@@3PEAGEA; pwszName
0x1800471d0  call    cs:__imp_WinHttpQueryHeaders
0x1800471d6  jmp     short loc_1800471E7
0x1800471d8  mov     qword ptr [rsp+60h+dwOptionalLength], r13; lpdwIndex
0x1800471dd  lea     r9, [rbp+arg_0]; lpdwBufferLength
0x1800471e1  call    cs:__imp_HttpQueryInfoW
0x1800471e7  test    eax, eax
0x1800471e9  jnz     short loc_1800471FE
0x1800471eb  call    cs:__imp_GetLastError
0x1800471f1  mov     ebx, eax
0x1800471f3  test    eax, eax
0x1800471f5  jle     short loc_18004721A
0x1800471f7  movzx   ebx, ax
0x1800471fa  or      ebx, esi
0x1800471fc  jmp     short loc_18004721A
0x1800471fe  mov     ebx, 4CFE0h
0x180047203  jmp     short loc_180047224
0x180047205  call    cs:__imp_GetLastError
0x18004720b  mov     ebx, eax
0x18004720d  test    eax, eax
0x18004720f  jle     short loc_18004721A
0x180047211  movzx   ebx, ax
0x180047214  or      ebx, 80070000h
0x18004721a  test    ebx, ebx
0x18004721c  mov     eax, 80004005h
0x180047221  cmovns  ebx, eax
0x180047224  mov     esi, 8004CF41h
0x180047229  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, r13d; int g_fGlobalOptionUseWinhttp
0x180047230  jnz     short loc_180047274
0x180047232  cmp     ebx, 8004CF43h
0x180047238  jnz     short loc_180047274
0x18004723a  test    r12d, r12d
0x18004723d  jz      short loc_180047274
0x18004723f  mov     [rbp+dwData], r13d
0x180047243  mov     [rbp+var_18], r13
0x180047247  lea     rdx, aMsdrmSslclears; "msdrm_SSLClearState"
0x18004724e  lea     rcx, [rbp+var_18]; this
0x180047252  call    ?Lock@CDRMCLock@@QEAAJPEAG@Z; CDRMCLock::Lock(ushort *)
0x180047257  test    eax, eax
0x180047259  js      short loc_18004726B
0x18004725b  lea     rdx, [rbp+dwData]; lpdwData
0x18004725f  mov     ecx, 0Eh; nIdx
0x180047264  call    cs:__imp_IncrementUrlCacheHeaderData
0x18004726a  nop
0x18004726b  lea     rcx, [rbp+var_18]; this
0x18004726f  call    ??1CDRMCLock@@QEAA@XZ; CDRMCLock::~CDRMCLock(void)
  ... truncated ...
```
