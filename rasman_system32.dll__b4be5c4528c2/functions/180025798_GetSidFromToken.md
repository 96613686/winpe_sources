# GetSidFromToken

- ea: `0x180025798`
- end: `0x180025bf1`
- name: `GetSidFromToken`
- size: `1113`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025398`
- `0x180025bf8`

## callees

- `0x180014230`
- `0x180021b14`
- `0x180021fd4`
- `0x1800254c4`
- `0x180025798`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025b75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025b75`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180025b96`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180025b96`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800258ea`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180025a9b`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800258ea`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180025a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a13`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180025a82`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180025a82`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002582e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025981`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002582e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025981`
- `rtutils!TracePrintfExA` at `0x180025872`
- `rtutils!TracePrintfExA` at `0x180025925`
- `rtutils!TracePrintfExA` at `0x1800259b9`
- `rtutils!TracePrintfExA` at `0x180025a3b`
- `rtutils!TracePrintfExA` at `0x180025b0c`
- `rtutils!TracePrintfExA` at `0x180025872`
- `rtutils!TracePrintfExA` at `0x180025925`
- `rtutils!TracePrintfExA` at `0x1800259b9`
- `rtutils!TracePrintfExA` at `0x180025a3b`
- `rtutils!TracePrintfExA` at `0x180025b0c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180025a03`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180025a03`

## string_xrefs

- `0x180025867`: `GetSidFromToken: GetTokenInformation failed with %d`
- `0x18002591a`: `GetSidFromToken: Malloc token_user failed with %d`
- `0x1800259ad`: `GetSidFromToken: GetTokenInformation2 failed with %d`
- `0x180025a2f`: `GetSidFromToken: ConvertSidToStringSid failed with %d`
- `0x180025b00`: `GetSidFromToken: StringCchCopy failed with %d`

## pseudocode

```c
__int64 __fastcall GetSidFromToken(HANDLE TokenHandle, HGLOBAL *a2)
{
  PVOID *v4; // rcx
  PSID *v5; // r14
  DWORD LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  size_t v12; // rbx
  wchar_t *v13; // rax
  unsigned __int16 v14; // ax
  DWORD TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp+18h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, TokenHandle);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = 0;
  StringSid = 0;
  TokenInformationLength = 0;
  if ( TokenHandle == (HANDLE)-1LL || !a2 )
  {
    v7 = 87;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 && *((_BYTE *)v4 + 25) >= 2u )
    {
      v8 = 20;
      goto LABEL_60;
    }
    goto LABEL_61;
  }
  *a2 = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError != 122 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "GetSidFromToken: GetTokenInformation failed with %d", LastError);
      if ( v7 )
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 21;
LABEL_60:
          WPP_SF_d(v4[2], v8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v7);
          goto LABEL_61;
        }
      }
      goto LABEL_61;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, 122);
    }
  }
  v5 = (PSID *)GlobalAlloc(0x40u, TokenInformationLength);
  if ( v5 )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
    {
      if ( ConvertSidToStringSidW(*v5, &StringSid) )
      {
        v12 = (unsigned int)(lstrlenW(StringSid) + 1);
        v13 = (wchar_t *)GlobalAlloc(0x40u, 2 * v12);
        *a2 = v13;
        if ( v13 )
        {
          v14 = StringCchCopyW(v13, v12, StringSid);
          v7 = v14;
          if ( v14 )
          {
            if ( g_dwTraceId != -1 )
              TracePrintfExA(g_dwTraceId, 0xCu, "GetSidFromToken: StringCchCopy failed with %d", v14);
            v4 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v8 = 27;
              goto LABEL_60;
            }
          }
        }
        else
        {
          v7 = 14;
          v4 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = 26;
            goto LABEL_60;
          }
        }
      }
      else
      {
        v11 = GetLastError();
        v7 = v11;
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "GetSidFromToken: ConvertSidToStringSid failed with %d", v11);
        if ( v7 )
        {
          v4 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = 25;
            goto LABEL_60;
          }
        }
      }
    }
    else
    {
      v10 = GetLastError();
      v7 = v10;
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "GetSidFromToken: GetTokenInformation2 failed with %d", v10);
      if ( v7 )
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 24;
          goto LABEL_60;
        }
      }
    }
  }
  else
  {
    v9 = GetLastError();
    v7 = v9;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "GetSidFromToken: Malloc token_user failed with %d", v9);
    if ( v7 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 23;
        goto LABEL_60;
      }
    }
  }
LABEL_61:
  Free0(v5);
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( v7 && *a2 )
  {
    GlobalFree(*a2);
    *a2 = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x180025798  mov     [rsp+arg_8], rbx
0x18002579d  mov     [rsp+arg_18], rsi
0x1800257a2  push    r13
0x1800257a4  push    r14
0x1800257a6  push    r15
0x1800257a8  sub     rsp, 30h
0x1800257ac  mov     r15, rdx
0x1800257af  mov     rsi, rcx
0x1800257b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257b9  lea     r13, WPP_GLOBAL_Control
0x1800257c0  cmp     rcx, r13
0x1800257c3  jz      short loc_1800257F0
0x1800257c5  test    byte ptr [rcx+1Ch], 4
0x1800257c9  jz      short loc_1800257F0
0x1800257cb  cmp     byte ptr [rcx+19h], 6
0x1800257cf  jb      short loc_1800257F0
0x1800257d1  mov     rcx, [rcx+10h]
0x1800257d5  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x1800257dc  mov     edx, 13h
0x1800257e1  mov     r9, rsi
0x1800257e4  call    WPP_SF_q
0x1800257e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257f0  xor     r14d, r14d
0x1800257f3  mov     [rsp+48h+StringSid], 0
0x1800257fc  mov     [rsp+48h+TokenInformationLength], r14d
0x180025801  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180025805  jz      loc_180025B37
0x18002580b  test    r15, r15
0x18002580e  jz      loc_180025B37
0x180025814  lea     rax, [rsp+48h+TokenInformationLength]
0x180025819  mov     [r15], r14
0x18002581c  xor     r9d, r9d; TokenInformationLength
0x18002581f  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180025824  xor     r8d, r8d; TokenInformation
0x180025827  lea     edx, [r14+1]; TokenInformationClass
0x18002582b  mov     rcx, rsi; TokenHandle
0x18002582e  call    cs:__imp_GetTokenInformation
0x180025835  nop     dword ptr [rax+rax+00h]
0x18002583a  test    eax, eax
0x18002583c  jnz     loc_1800258E1
0x180025842  call    cs:__imp_GetLastError
0x180025849  nop     dword ptr [rax+rax+00h]
0x18002584e  lea     r9d, [r14+7Ah]
0x180025852  mov     ebx, eax
0x180025854  cmp     eax, r9d
0x180025857  jz      short loc_1800258B4
0x180025859  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002585f  cmp     ecx, 0FFFFFFFFh
0x180025862  jz      short loc_18002587E
0x180025864  mov     r9d, eax
0x180025867  lea     r8, aGetsidfromtoke_1; "GetSidFromToken: GetTokenInformation fa"...
0x18002586e  lea     edx, [r14+0Ch]; dwFlags
0x180025872  call    cs:__imp_TracePrintfExA
0x180025879  nop     dword ptr [rax+rax+00h]
0x18002587e  test    ebx, ebx
0x180025880  jz      loc_180025B63
0x180025886  mov     rcx, cs:WPP_GLOBAL_Control
0x18002588d  cmp     rcx, r13
0x180025890  jz      loc_180025B63
0x180025896  test    byte ptr [rcx+1Ch], 4
0x18002589a  jz      loc_180025B63
0x1800258a0  cmp     byte ptr [rcx+19h], 2
0x1800258a4  jb      loc_180025B63
0x1800258aa  mov     edx, 15h
0x1800258af  jmp     loc_180025B50
0x1800258b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258bb  cmp     rcx, r13
0x1800258be  jz      short loc_1800258E1
0x1800258c0  test    byte ptr [rcx+1Ch], 4
0x1800258c4  jz      short loc_1800258E1
0x1800258c6  cmp     byte ptr [rcx+19h], 2
0x1800258ca  jb      short loc_1800258E1
0x1800258cc  mov     rcx, [rcx+10h]
0x1800258d0  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x1800258d7  mov     edx, 16h
0x1800258dc  call    WPP_SF_d
0x1800258e1  mov     edx, [rsp+48h+TokenInformationLength]; dwBytes
0x1800258e5  mov     ecx, 40h ; '@'; uFlags
0x1800258ea  call    cs:__imp_GlobalAlloc
0x1800258f1  nop     dword ptr [rax+rax+00h]
0x1800258f6  mov     r14, rax
0x1800258f9  test    rax, rax
0x1800258fc  jnz     short loc_180025967
0x1800258fe  call    cs:__imp_GetLastError
0x180025905  nop     dword ptr [rax+rax+00h]
0x18002590a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025910  mov     ebx, eax
0x180025912  cmp     ecx, 0FFFFFFFFh
0x180025915  jz      short loc_180025931
0x180025917  mov     r9d, eax
0x18002591a  lea     r8, aGetsidfromtoke; "GetSidFromToken: Malloc token_user fail"...
0x180025921  lea     edx, [r14+0Ch]; dwFlags
0x180025925  call    cs:__imp_TracePrintfExA
0x18002592c  nop     dword ptr [rax+rax+00h]
0x180025931  test    ebx, ebx
0x180025933  jz      loc_180025B63
0x180025939  mov     rcx, cs:WPP_GLOBAL_Control
0x180025940  cmp     rcx, r13
0x180025943  jz      loc_180025B63
0x180025949  test    byte ptr [rcx+1Ch], 4
0x18002594d  jz      loc_180025B63
0x180025953  cmp     byte ptr [rcx+19h], 2
0x180025957  jb      loc_180025B63
0x18002595d  mov     edx, 17h
0x180025962  jmp     loc_180025B50
0x180025967  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18002596c  lea     rax, [rsp+48h+TokenInformationLength]
0x180025971  mov     r8, r14; TokenInformation
0x180025974  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180025979  mov     edx, 1; TokenInformationClass
0x18002597e  mov     rcx, rsi; TokenHandle
0x180025981  call    cs:__imp_GetTokenInformation
0x180025988  nop     dword ptr [rax+rax+00h]
0x18002598d  test    eax, eax
0x18002598f  jnz     short loc_1800259FB
0x180025991  call    cs:__imp_GetLastError
0x180025998  nop     dword ptr [rax+rax+00h]
0x18002599d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800259a3  mov     ebx, eax
0x1800259a5  cmp     ecx, 0FFFFFFFFh
0x1800259a8  jz      short loc_1800259C5
0x1800259aa  mov     r9d, eax
0x1800259ad  lea     r8, aGetsidfromtoke_3; "GetSidFromToken: GetTokenInformation2 f"...
0x1800259b4  mov     edx, 0Ch; dwFlags
0x1800259b9  call    cs:__imp_TracePrintfExA
0x1800259c0  nop     dword ptr [rax+rax+00h]
0x1800259c5  test    ebx, ebx
0x1800259c7  jz      loc_180025B63
0x1800259cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800259d4  cmp     rcx, r13
0x1800259d7  jz      loc_180025B63
0x1800259dd  test    byte ptr [rcx+1Ch], 4
0x1800259e1  jz      loc_180025B63
0x1800259e7  cmp     byte ptr [rcx+19h], 2
0x1800259eb  jb      loc_180025B63
0x1800259f1  mov     edx, 18h
0x1800259f6  jmp     loc_180025B50
0x1800259fb  mov     rcx, [r14]; Sid
0x1800259fe  lea     rdx, [rsp+48h+StringSid]; StringSid
0x180025a03  call    cs:__imp_ConvertSidToStringSidW
0x180025a0a  nop     dword ptr [rax+rax+00h]
0x180025a0f  test    eax, eax
0x180025a11  jnz     short loc_180025A7D
0x180025a13  call    cs:__imp_GetLastError
0x180025a1a  nop     dword ptr [rax+rax+00h]
0x180025a1f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025a25  mov     ebx, eax
0x180025a27  cmp     ecx, 0FFFFFFFFh
0x180025a2a  jz      short loc_180025A47
0x180025a2c  mov     r9d, eax
0x180025a2f  lea     r8, aGetsidfromtoke_2; "GetSidFromToken: ConvertSidToStringSid "...
0x180025a36  mov     edx, 0Ch; dwFlags
0x180025a3b  call    cs:__imp_TracePrintfExA
0x180025a42  nop     dword ptr [rax+rax+00h]
0x180025a47  test    ebx, ebx
0x180025a49  jz      loc_180025B63
0x180025a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a56  cmp     rcx, r13
0x180025a59  jz      loc_180025B63
0x180025a5f  test    byte ptr [rcx+1Ch], 4
0x180025a63  jz      loc_180025B63
0x180025a69  cmp     byte ptr [rcx+19h], 2
0x180025a6d  jb      loc_180025B63
0x180025a73  mov     edx, 19h
0x180025a78  jmp     loc_180025B50
0x180025a7d  mov     rcx, [rsp+48h+StringSid]; lpString
0x180025a82  call    cs:__imp_lstrlenW
0x180025a89  nop     dword ptr [rax+rax+00h]
0x180025a8e  inc     eax
0x180025a90  mov     ecx, 40h ; '@'; uFlags
0x180025a95  mov     ebx, eax
0x180025a97  lea     rdx, [rax+rax]; dwBytes
0x180025a9b  call    cs:__imp_GlobalAlloc
0x180025aa2  nop     dword ptr [rax+rax+00h]
0x180025aa7  mov     [r15], rax
0x180025aaa  test    rax, rax
0x180025aad  jnz     short loc_180025ADB
0x180025aaf  lea     ebx, [rax+0Eh]
0x180025ab2  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ab9  cmp     rcx, r13
0x180025abc  jz      loc_180025B63
0x180025ac2  test    byte ptr [rcx+1Ch], 4
0x180025ac6  jz      loc_180025B63
0x180025acc  cmp     byte ptr [rcx+19h], 2
0x180025ad0  jb      loc_180025B63
0x180025ad6  lea     edx, [rax+1Ah]
0x180025ad9  jmp     short loc_180025B50
0x180025adb  mov     r8, [rsp+48h+StringSid]; pszSrc
0x180025ae0  mov     rdx, rbx; cchDest
0x180025ae3  mov     rcx, rax; pszDest
0x180025ae6  call    StringCchCopyW
0x180025aeb  movzx   ebx, ax
0x180025aee  test    ebx, ebx
0x180025af0  jz      short loc_180025B63
0x180025af2  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025af8  cmp     ecx, 0FFFFFFFFh
0x180025afb  jz      short loc_180025B18
0x180025afd  mov     r9d, ebx
0x180025b00  lea     r8, aGetsidfromtoke_0; "GetSidFromToken: StringCchCopy failed w"...
0x180025b07  mov     edx, 0Ch; dwFlags
0x180025b0c  call    cs:__imp_TracePrintfExA
0x180025b13  nop     dword ptr [rax+rax+00h]
0x180025b18  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b1f  cmp     rcx, r13
0x180025b22  jz      short loc_180025B63
0x180025b24  test    byte ptr [rcx+1Ch], 4
0x180025b28  jz      short loc_180025B63
0x180025b2a  cmp     byte ptr [rcx+19h], 2
0x180025b2e  jb      short loc_180025B63
0x180025b30  mov     edx, 1Bh
0x180025b35  jmp     short loc_180025B50
0x180025b37  mov     ebx, 57h ; 'W'
0x180025b3c  cmp     rcx, r13
0x180025b3f  jz      short loc_180025B63
0x180025b41  test    byte ptr [rcx+1Ch], 4
0x180025b45  jz      short loc_180025B63
0x180025b47  cmp     byte ptr [rcx+19h], 2
0x180025b4b  jb      short loc_180025B63
0x180025b4d  lea     edx, [rbx-43h]
0x180025b50  mov     rcx, [rcx+10h]
0x180025b54  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x180025b5b  mov     r9d, ebx
0x180025b5e  call    WPP_SF_d
0x180025b63  mov     rcx, r14
0x180025b66  call    Free0
0x180025b6b  mov     rcx, [rsp+48h+StringSid]; hMem
0x180025b70  test    rcx, rcx
0x180025b73  jz      short loc_180025B8A
0x180025b75  call    cs:__imp_LocalFree
0x180025b7c  nop     dword ptr [rax+rax+00h]
0x180025b81  mov     [rsp+48h+StringSid], 0
0x180025b8a  test    ebx, ebx
0x180025b8c  jz      short loc_180025BA9
0x180025b8e  mov     rcx, [r15]; hMem
0x180025b91  test    rcx, rcx
0x180025b94  jz      short loc_180025BA9
0x180025b96  call    cs:__imp_GlobalFree
0x180025b9d  nop     dword ptr [rax+rax+00h]
0x180025ba2  mov     qword ptr [r15], 0
0x180025ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025bb0  cmp     rcx, r13
0x180025bb3  jz      short loc_180025BD9
0x180025bb5  test    byte ptr [rcx+1Ch], 4
0x180025bb9  jz      short loc_180025BD9
0x180025bbb  cmp     byte ptr [rcx+19h], 6
0x180025bbf  jb      short loc_180025BD9
0x180025bc1  mov     rcx, [rcx+10h]
0x180025bc5  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x180025bcc  mov     edx, 1Ch
0x180025bd1  mov     r9d, ebx
0x180025bd4  call    WPP_SF_d
0x180025bd9  mov     rsi, [rsp+48h+arg_18]
0x180025bde  mov     eax, ebx
0x180025be0  mov     rbx, [rsp+48h+arg_8]
0x180025be5  add     rsp, 30h
0x180025be9  pop     r15
0x180025beb  pop     r14
0x180025bed  pop     r13
0x180025bef  retn
```
