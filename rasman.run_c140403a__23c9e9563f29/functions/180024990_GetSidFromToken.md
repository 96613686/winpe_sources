# GetSidFromToken

- ea: `0x180024990`
- end: `0x180024d82`
- name: `GetSidFromToken`
- size: `1010`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800245e4`
- `0x180024d88`

## callees

- `0x1800139e0`
- `0x180021000`
- `0x180021488`
- `0x1800246f4`
- `0x180024990`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d13`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180024d2e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180024d2e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180024ad0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180024c45`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180024ad0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180024c45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bcf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180024c32`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180024c32`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024a26`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024b55`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024a26`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024b55`
- `rtutils!TracePrintfExA` at `0x180024a5e`
- `rtutils!TracePrintfExA` at `0x180024aff`
- `rtutils!TracePrintfExA` at `0x180024b81`
- `rtutils!TracePrintfExA` at `0x180024bf1`
- `rtutils!TracePrintfExA` at `0x180024cb0`
- `rtutils!TracePrintfExA` at `0x180024a5e`
- `rtutils!TracePrintfExA` at `0x180024aff`
- `rtutils!TracePrintfExA` at `0x180024b81`
- `rtutils!TracePrintfExA` at `0x180024bf1`
- `rtutils!TracePrintfExA` at `0x180024cb0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180024bc5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180024bc5`

## string_xrefs

- `0x180024a53`: `GetSidFromToken: GetTokenInformation failed with %d`
- `0x180024af4`: `GetSidFromToken: Malloc token_user failed with %d`
- `0x180024b75`: `GetSidFromToken: GetTokenInformation2 failed with %d`
- `0x180024be5`: `GetSidFromToken: ConvertSidToStringSid failed with %d`
- `0x180024ca4`: `GetSidFromToken: StringCchCopy failed with %d`

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
0x180024990  mov     [rsp+arg_8], rbx
0x180024995  mov     [rsp+arg_18], rsi
0x18002499a  push    r13
0x18002499c  push    r14
0x18002499e  push    r15
0x1800249a0  sub     rsp, 30h
0x1800249a4  mov     r15, rdx
0x1800249a7  mov     rsi, rcx
0x1800249aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249b1  lea     r13, WPP_GLOBAL_Control
0x1800249b8  cmp     rcx, r13
0x1800249bb  jz      short loc_1800249E8
0x1800249bd  test    byte ptr [rcx+1Ch], 4
0x1800249c1  jz      short loc_1800249E8
0x1800249c3  cmp     byte ptr [rcx+19h], 6
0x1800249c7  jb      short loc_1800249E8
0x1800249c9  mov     rcx, [rcx+10h]
0x1800249cd  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x1800249d4  mov     edx, 13h
0x1800249d9  mov     r9, rsi
0x1800249dc  call    WPP_SF_q
0x1800249e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249e8  xor     r14d, r14d
0x1800249eb  mov     [rsp+48h+StringSid], 0
0x1800249f4  mov     [rsp+48h+TokenInformationLength], r14d
0x1800249f9  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800249fd  jz      loc_180024CD5
0x180024a03  test    r15, r15
0x180024a06  jz      loc_180024CD5
0x180024a0c  lea     rax, [rsp+48h+TokenInformationLength]
0x180024a11  mov     [r15], r14
0x180024a14  xor     r9d, r9d; TokenInformationLength
0x180024a17  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180024a1c  xor     r8d, r8d; TokenInformation
0x180024a1f  lea     edx, [r14+1]; TokenInformationClass
0x180024a23  mov     rcx, rsi; TokenHandle
0x180024a26  call    cs:__imp_GetTokenInformation
0x180024a2c  test    eax, eax
0x180024a2e  jnz     loc_180024AC7
0x180024a34  call    cs:__imp_GetLastError
0x180024a3a  lea     r9d, [r14+7Ah]
0x180024a3e  mov     ebx, eax
0x180024a40  cmp     eax, r9d
0x180024a43  jz      short loc_180024A9A
0x180024a45  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180024a4b  cmp     ecx, 0FFFFFFFFh
0x180024a4e  jz      short loc_180024A64
0x180024a50  mov     r9d, eax
0x180024a53  lea     r8, aGetsidfromtoke_1; "GetSidFromToken: GetTokenInformation fa"...
0x180024a5a  lea     edx, [r14+0Ch]; dwFlags
0x180024a5e  call    cs:__imp_TracePrintfExA
0x180024a64  test    ebx, ebx
0x180024a66  jz      loc_180024D01
0x180024a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a73  cmp     rcx, r13
0x180024a76  jz      loc_180024D01
0x180024a7c  test    byte ptr [rcx+1Ch], 4
0x180024a80  jz      loc_180024D01
0x180024a86  cmp     byte ptr [rcx+19h], 2
0x180024a8a  jb      loc_180024D01
0x180024a90  mov     edx, 15h
0x180024a95  jmp     loc_180024CEE
0x180024a9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024aa1  cmp     rcx, r13
0x180024aa4  jz      short loc_180024AC7
0x180024aa6  test    byte ptr [rcx+1Ch], 4
0x180024aaa  jz      short loc_180024AC7
0x180024aac  cmp     byte ptr [rcx+19h], 2
0x180024ab0  jb      short loc_180024AC7
0x180024ab2  mov     rcx, [rcx+10h]
0x180024ab6  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x180024abd  mov     edx, 16h
0x180024ac2  call    WPP_SF_d
0x180024ac7  mov     edx, [rsp+48h+TokenInformationLength]; dwBytes
0x180024acb  mov     ecx, 40h ; '@'; uFlags
0x180024ad0  call    cs:__imp_GlobalAlloc
0x180024ad6  mov     r14, rax
0x180024ad9  test    rax, rax
0x180024adc  jnz     short loc_180024B3B
0x180024ade  call    cs:__imp_GetLastError
0x180024ae4  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180024aea  mov     ebx, eax
0x180024aec  cmp     ecx, 0FFFFFFFFh
0x180024aef  jz      short loc_180024B05
0x180024af1  mov     r9d, eax
0x180024af4  lea     r8, aGetsidfromtoke; "GetSidFromToken: Malloc token_user fail"...
0x180024afb  lea     edx, [r14+0Ch]; dwFlags
0x180024aff  call    cs:__imp_TracePrintfExA
0x180024b05  test    ebx, ebx
0x180024b07  jz      loc_180024D01
0x180024b0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b14  cmp     rcx, r13
0x180024b17  jz      loc_180024D01
0x180024b1d  test    byte ptr [rcx+1Ch], 4
0x180024b21  jz      loc_180024D01
0x180024b27  cmp     byte ptr [rcx+19h], 2
0x180024b2b  jb      loc_180024D01
0x180024b31  mov     edx, 17h
0x180024b36  jmp     loc_180024CEE
0x180024b3b  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180024b40  lea     rax, [rsp+48h+TokenInformationLength]
0x180024b45  mov     r8, r14; TokenInformation
0x180024b48  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180024b4d  mov     edx, 1; TokenInformationClass
0x180024b52  mov     rcx, rsi; TokenHandle
0x180024b55  call    cs:__imp_GetTokenInformation
0x180024b5b  test    eax, eax
0x180024b5d  jnz     short loc_180024BBD
0x180024b5f  call    cs:__imp_GetLastError
0x180024b65  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180024b6b  mov     ebx, eax
0x180024b6d  cmp     ecx, 0FFFFFFFFh
0x180024b70  jz      short loc_180024B87
0x180024b72  mov     r9d, eax
0x180024b75  lea     r8, aGetsidfromtoke_3; "GetSidFromToken: GetTokenInformation2 f"...
0x180024b7c  mov     edx, 0Ch; dwFlags
0x180024b81  call    cs:__imp_TracePrintfExA
0x180024b87  test    ebx, ebx
0x180024b89  jz      loc_180024D01
0x180024b8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b96  cmp     rcx, r13
0x180024b99  jz      loc_180024D01
0x180024b9f  test    byte ptr [rcx+1Ch], 4
0x180024ba3  jz      loc_180024D01
0x180024ba9  cmp     byte ptr [rcx+19h], 2
0x180024bad  jb      loc_180024D01
0x180024bb3  mov     edx, 18h
0x180024bb8  jmp     loc_180024CEE
0x180024bbd  mov     rcx, [r14]; Sid
0x180024bc0  lea     rdx, [rsp+48h+StringSid]; StringSid
0x180024bc5  call    cs:__imp_ConvertSidToStringSidW
0x180024bcb  test    eax, eax
0x180024bcd  jnz     short loc_180024C2D
0x180024bcf  call    cs:__imp_GetLastError
0x180024bd5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180024bdb  mov     ebx, eax
0x180024bdd  cmp     ecx, 0FFFFFFFFh
0x180024be0  jz      short loc_180024BF7
0x180024be2  mov     r9d, eax
0x180024be5  lea     r8, aGetsidfromtoke_2; "GetSidFromToken: ConvertSidToStringSid "...
0x180024bec  mov     edx, 0Ch; dwFlags
0x180024bf1  call    cs:__imp_TracePrintfExA
0x180024bf7  test    ebx, ebx
0x180024bf9  jz      loc_180024D01
0x180024bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c06  cmp     rcx, r13
0x180024c09  jz      loc_180024D01
0x180024c0f  test    byte ptr [rcx+1Ch], 4
0x180024c13  jz      loc_180024D01
0x180024c19  cmp     byte ptr [rcx+19h], 2
0x180024c1d  jb      loc_180024D01
0x180024c23  mov     edx, 19h
0x180024c28  jmp     loc_180024CEE
0x180024c2d  mov     rcx, [rsp+48h+StringSid]; lpString
0x180024c32  call    cs:__imp_lstrlenW
0x180024c38  inc     eax
0x180024c3a  mov     ecx, 40h ; '@'; uFlags
0x180024c3f  mov     ebx, eax
0x180024c41  lea     rdx, [rax+rax]; dwBytes
0x180024c45  call    cs:__imp_GlobalAlloc
0x180024c4b  mov     [r15], rax
0x180024c4e  test    rax, rax
0x180024c51  jnz     short loc_180024C7F
0x180024c53  lea     ebx, [rax+0Eh]
0x180024c56  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c5d  cmp     rcx, r13
0x180024c60  jz      loc_180024D01
0x180024c66  test    byte ptr [rcx+1Ch], 4
0x180024c6a  jz      loc_180024D01
0x180024c70  cmp     byte ptr [rcx+19h], 2
0x180024c74  jb      loc_180024D01
0x180024c7a  lea     edx, [rax+1Ah]
0x180024c7d  jmp     short loc_180024CEE
0x180024c7f  mov     r8, [rsp+48h+StringSid]; pszSrc
0x180024c84  mov     rdx, rbx; cchDest
0x180024c87  mov     rcx, rax; pszDest
0x180024c8a  call    StringCchCopyW
0x180024c8f  movzx   ebx, ax
0x180024c92  test    ebx, ebx
0x180024c94  jz      short loc_180024D01
0x180024c96  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180024c9c  cmp     ecx, 0FFFFFFFFh
0x180024c9f  jz      short loc_180024CB6
0x180024ca1  mov     r9d, ebx
0x180024ca4  lea     r8, aGetsidfromtoke_0; "GetSidFromToken: StringCchCopy failed w"...
0x180024cab  mov     edx, 0Ch; dwFlags
0x180024cb0  call    cs:__imp_TracePrintfExA
0x180024cb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180024cbd  cmp     rcx, r13
0x180024cc0  jz      short loc_180024D01
0x180024cc2  test    byte ptr [rcx+1Ch], 4
0x180024cc6  jz      short loc_180024D01
0x180024cc8  cmp     byte ptr [rcx+19h], 2
0x180024ccc  jb      short loc_180024D01
0x180024cce  mov     edx, 1Bh
0x180024cd3  jmp     short loc_180024CEE
0x180024cd5  mov     ebx, 57h ; 'W'
0x180024cda  cmp     rcx, r13
0x180024cdd  jz      short loc_180024D01
0x180024cdf  test    byte ptr [rcx+1Ch], 4
0x180024ce3  jz      short loc_180024D01
0x180024ce5  cmp     byte ptr [rcx+19h], 2
0x180024ce9  jb      short loc_180024D01
0x180024ceb  lea     edx, [rbx-43h]
0x180024cee  mov     rcx, [rcx+10h]
0x180024cf2  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x180024cf9  mov     r9d, ebx
0x180024cfc  call    WPP_SF_d
0x180024d01  mov     rcx, r14
0x180024d04  call    Free0
0x180024d09  mov     rcx, [rsp+48h+StringSid]; hMem
0x180024d0e  test    rcx, rcx
0x180024d11  jz      short loc_180024D22
0x180024d13  call    cs:__imp_LocalFree
0x180024d19  mov     [rsp+48h+StringSid], 0
0x180024d22  test    ebx, ebx
0x180024d24  jz      short loc_180024D3B
0x180024d26  mov     rcx, [r15]; hMem
0x180024d29  test    rcx, rcx
0x180024d2c  jz      short loc_180024D3B
0x180024d2e  call    cs:__imp_GlobalFree
0x180024d34  mov     qword ptr [r15], 0
0x180024d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d42  cmp     rcx, r13
0x180024d45  jz      short loc_180024D6B
0x180024d47  test    byte ptr [rcx+1Ch], 4
0x180024d4b  jz      short loc_180024D6B
0x180024d4d  cmp     byte ptr [rcx+19h], 6
0x180024d51  jb      short loc_180024D6B
0x180024d53  mov     rcx, [rcx+10h]
0x180024d57  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x180024d5e  mov     edx, 1Ch
0x180024d63  mov     r9d, ebx
0x180024d66  call    WPP_SF_d
0x180024d6b  mov     rsi, [rsp+48h+arg_18]
0x180024d70  mov     eax, ebx
0x180024d72  mov     rbx, [rsp+48h+arg_8]
0x180024d77  add     rsp, 30h
0x180024d7b  pop     r15
0x180024d7d  pop     r14
0x180024d7f  pop     r13
0x180024d81  retn
```
