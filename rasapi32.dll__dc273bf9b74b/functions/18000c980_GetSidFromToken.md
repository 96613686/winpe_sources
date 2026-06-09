# GetSidFromToken

- ea: `0x18000c980`
- end: `0x18000ce88`
- name: `GetSidFromToken`
- size: `1288`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c190`
- `0x18004e81c`
- `0x1800c1c78`
- `0x1800cb7dc`

## callees

- `0x18000c980`
- `0x18004e580`
- `0x18007f18c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cb12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cb12`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ca0f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ca77`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ca0f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ca77`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000caf8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000ce73`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000caf8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000ce73`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c9f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000ca3b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c9f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000ca3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd24`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000ca64`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000ca64`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ca51`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ca51`
- `rtutils!TracePrintfExA` at `0x18000cc6d`
- `rtutils!TracePrintfExA` at `0x18000ccb8`
- `rtutils!TracePrintfExA` at `0x18000cce5`
- `rtutils!TracePrintfExA` at `0x18000cd46`
- `rtutils!TracePrintfExA` at `0x18000cdea`
- `rtutils!TracePrintfExA` at `0x18000cc6d`
- `rtutils!TracePrintfExA` at `0x18000ccb8`
- `rtutils!TracePrintfExA` at `0x18000cce5`
- `rtutils!TracePrintfExA` at `0x18000cd46`
- `rtutils!TracePrintfExA` at `0x18000cdea`

## string_xrefs

- `0x18000cc61`: `GetSidFromToken: GetTokenInformation failed with %d`
- `0x18000cd3a`: `GetSidFromToken: ConvertSidToStringSid failed with %d`
- `0x18000cdde`: `GetSidFromToken: StringCchCopy failed with %d`
- `0x18000ccac`: `GetSidFromToken: Malloc token_user failed with %d`
- `0x18000ccd9`: `GetSidFromToken: GetTokenInformation2 failed with %d`

## pseudocode

```c
__int64 __fastcall GetSidFromToken(HANDLE TokenHandle, HGLOBAL *a2)
{
  _BYTE *v4; // rcx
  PSID *v5; // rsi
  unsigned __int64 v6; // rbx
  _WORD *v7; // rax
  _WORD *v8; // r8
  LPWSTR v9; // rdx
  __int64 v10; // rcx
  _WORD *v11; // rcx
  unsigned __int16 v12; // cx
  unsigned int v13; // edi
  unsigned int v14; // ebx
  DWORD v16; // eax
  DWORD v17; // eax
  __int64 v18; // rdx
  DWORD v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  DWORD LastError; // eax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp+18h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  StringSid = 0;
  TokenInformationLength = 0;
  if ( TokenHandle == (HANDLE)-1LL || !a2 )
  {
    v14 = 87;
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || (v4[28] & 4) == 0 || v4[25] < 2u )
    {
LABEL_84:
      if ( *a2 )
      {
        GlobalFree(*a2);
        v4 = WPP_GLOBAL_Control;
        *a2 = 0;
      }
      goto LABEL_25;
    }
    v18 = 20;
    goto LABEL_83;
  }
  *a2 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
LABEL_5:
    v5 = (PSID *)GlobalAlloc(0x40u, TokenInformationLength);
    if ( v5 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
      {
        if ( ConvertSidToStringSidW(*v5, &StringSid) )
        {
          v6 = (unsigned int)(lstrlenW(StringSid) + 1);
          v7 = GlobalAlloc(0x40u, 2 * v6);
          *a2 = v7;
          v8 = v7;
          if ( !v7 )
          {
            v14 = 14;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_20;
            }
            v21 = 26;
            v22 = 14;
            goto LABEL_78;
          }
          if ( v6 )
          {
            if ( v6 > 0x7FFFFFFF )
            {
              v14 = 87;
              *v7 = 0;
              v13 = 87;
LABEL_72:
              if ( g_dwTraceId != -1 )
                TracePrintfExA(g_dwTraceId, 0xCu, "GetSidFromToken: StringCchCopy failed with %d", v13);
              v20 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_20;
              }
              v21 = 27;
              v22 = v13;
              goto LABEL_78;
            }
            v9 = StringSid;
            v10 = 2147483646;
            do
            {
              if ( !v10 )
                break;
              if ( !*v9 )
                break;
              *v8++ = *v9++;
              --v10;
              --v6;
            }
            while ( v6 );
            v11 = v8 - 1;
            if ( v6 )
              v11 = v8;
            *v11 = 0;
            v12 = 122;
            if ( v6 )
              v12 = 0;
          }
          else
          {
            v12 = 87;
          }
          v13 = v12;
          v14 = v12;
          if ( !v12 )
          {
LABEL_20:
            GlobalFree(v5);
LABEL_21:
            v4 = WPP_GLOBAL_Control;
            goto LABEL_22;
          }
          goto LABEL_72;
        }
        LastError = GetLastError();
        v14 = LastError;
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "GetSidFromToken: ConvertSidToStringSid failed with %d", LastError);
        if ( !v14 )
          goto LABEL_20;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_20;
        }
        v21 = 25;
        v22 = v14;
      }
      else
      {
        v19 = GetLastError();
        v14 = v19;
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "GetSidFromToken: GetTokenInformation2 failed with %d", v19);
        if ( !v14 )
          goto LABEL_20;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_20;
        }
        v21 = 24;
        v22 = v14;
      }
LABEL_78:
      WPP_SF_d(v20[2], v21, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v22);
      goto LABEL_20;
    }
    v17 = GetLastError();
    v14 = v17;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "GetSidFromToken: Malloc token_user failed with %d", v17);
    if ( !v14 )
      goto LABEL_21;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 23;
LABEL_83:
      WPP_SF_d(*((_QWORD *)v4 + 2), v18, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v14);
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  v16 = GetLastError();
  v14 = v16;
  if ( v16 == 122 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, 122);
    }
    goto LABEL_5;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GetSidFromToken: GetTokenInformation failed with %d", v16);
  if ( !v14 )
    goto LABEL_21;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = 21;
    goto LABEL_83;
  }
LABEL_22:
  if ( StringSid )
  {
    LocalFree(StringSid);
    v4 = WPP_GLOBAL_Control;
    StringSid = 0;
  }
  if ( v14 )
    goto LABEL_84;
LABEL_25:
  if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 4) != 0 && v4[25] >= 6u )
    WPP_SF_d(*((_QWORD *)v4 + 2), 28, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18000c980  sub     rsp, 58h
0x18000c984  mov     [rsp+58h+var_8], rbp
0x18000c989  mov     [rsp+58h+var_18], rdi
0x18000c98e  mov     rdi, rcx
0x18000c991  mov     [rsp+58h+var_20], r14
0x18000c996  mov     r14, rdx
0x18000c999  mov     [rsp+58h+var_28], r15
0x18000c99e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9a5  lea     r15, WPP_GLOBAL_Control
0x18000c9ac  cmp     rcx, r15
0x18000c9af  jnz     loc_18000CB56
0x18000c9b5  xor     ebp, ebp
0x18000c9b7  mov     [rsp+58h+arg_8], rbx
0x18000c9bc  mov     [rsp+58h+var_10], rsi
0x18000c9c1  mov     [rsp+58h+StringSid], rbp
0x18000c9c6  mov     [rsp+58h+TokenInformationLength], ebp
0x18000c9ca  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000c9ce  jz      loc_18000CE31
0x18000c9d4  test    r14, r14
0x18000c9d7  jz      loc_18000CE31
0x18000c9dd  lea     rax, [rsp+58h+TokenInformationLength]
0x18000c9e2  mov     [r14], rbp
0x18000c9e5  xor     r9d, r9d; TokenInformationLength
0x18000c9e8  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000c9ed  xor     r8d, r8d; TokenInformation
0x18000c9f0  mov     edx, 1; TokenInformationClass
0x18000c9f5  mov     rcx, rdi; TokenHandle
0x18000c9f8  call    cs:__imp_GetTokenInformation
0x18000c9fe  test    eax, eax
0x18000ca00  jz      loc_18000CBB4
0x18000ca06  mov     edx, [rsp+58h+TokenInformationLength]; dwBytes
0x18000ca0a  mov     ecx, 40h ; '@'; uFlags
0x18000ca0f  call    cs:__imp_GlobalAlloc
0x18000ca15  mov     rsi, rax
0x18000ca18  test    rax, rax
0x18000ca1b  jz      loc_18000CC06
0x18000ca21  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18000ca26  lea     rax, [rsp+58h+TokenInformationLength]
0x18000ca2b  mov     r8, rsi; TokenInformation
0x18000ca2e  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000ca33  mov     edx, 1; TokenInformationClass
0x18000ca38  mov     rcx, rdi; TokenHandle
0x18000ca3b  call    cs:__imp_GetTokenInformation
0x18000ca41  test    eax, eax
0x18000ca43  jz      loc_18000CCC3
0x18000ca49  mov     rcx, [rsi]; Sid
0x18000ca4c  lea     rdx, [rsp+58h+StringSid]; StringSid
0x18000ca51  call    cs:__imp_ConvertSidToStringSidW
0x18000ca57  test    eax, eax
0x18000ca59  jz      loc_18000CD24
0x18000ca5f  mov     rcx, [rsp+58h+StringSid]; lpString
0x18000ca64  call    cs:__imp_lstrlenW
0x18000ca6a  inc     eax
0x18000ca6c  mov     ecx, 40h ; '@'; uFlags
0x18000ca71  mov     ebx, eax
0x18000ca73  lea     rdx, [rax+rax]; dwBytes
0x18000ca77  call    cs:__imp_GlobalAlloc
0x18000ca7d  mov     [r14], rax
0x18000ca80  mov     r8, rax
0x18000ca83  test    rax, rax
0x18000ca86  jz      loc_18000CD85
0x18000ca8c  test    rbx, rbx
0x18000ca8f  jz      loc_18000CDB8
0x18000ca95  cmp     rbx, 7FFFFFFFh
0x18000ca9c  ja      loc_18000CDC6
0x18000caa2  mov     rdx, [rsp+58h+StringSid]
0x18000caa7  mov     ecx, 7FFFFFFEh
0x18000caac  nop     dword ptr [rax+00h]
0x18000cab0  test    rcx, rcx
0x18000cab3  jz      short loc_18000CAD2
0x18000cab5  movzx   eax, word ptr [rdx]
0x18000cab8  test    ax, ax
0x18000cabb  jz      short loc_18000CAD2
0x18000cabd  mov     [r8], ax
0x18000cac1  add     rdx, 2
0x18000cac5  add     r8, 2
0x18000cac9  dec     rcx
0x18000cacc  sub     rbx, 1
0x18000cad0  jnz     short loc_18000CAB0
0x18000cad2  test    rbx, rbx
0x18000cad5  lea     rcx, [r8-2]
0x18000cad9  cmovnz  rcx, r8
0x18000cadd  mov     [rcx], bp
0x18000cae0  mov     ecx, 8007007Ah
0x18000cae5  cmovnz  ecx, ebp
0x18000cae8  movzx   edi, cx
0x18000caeb  mov     ebx, edi
0x18000caed  test    edi, edi
0x18000caef  jnz     loc_18000CDD0
0x18000caf5  mov     rcx, rsi; hMem
0x18000caf8  call    cs:__imp_GlobalFree
0x18000cafe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb05  mov     rax, [rsp+58h+StringSid]
0x18000cb0a  test    rax, rax
0x18000cb0d  jz      short loc_18000CB24
0x18000cb0f  mov     rcx, rax; hMem
0x18000cb12  call    cs:__imp_LocalFree
0x18000cb18  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb1f  mov     [rsp+58h+StringSid], rbp
0x18000cb24  test    ebx, ebx
0x18000cb26  jnz     loc_18000CE64
0x18000cb2c  mov     r14, [rsp+58h+var_20]
0x18000cb31  cmp     rcx, r15
0x18000cb34  mov     r15, [rsp+58h+var_28]
0x18000cb39  mov     rdi, [rsp+58h+var_18]
0x18000cb3e  mov     rsi, [rsp+58h+var_10]
0x18000cb43  mov     rbp, [rsp+58h+var_8]
0x18000cb48  jnz     short loc_18000CB8E
0x18000cb4a  mov     eax, ebx
0x18000cb4c  mov     rbx, [rsp+58h+arg_8]
0x18000cb51  add     rsp, 58h
0x18000cb55  retn
0x18000cb56  test    byte ptr [rcx+1Ch], 4
0x18000cb5a  jz      loc_18000C9B5
0x18000cb60  cmp     byte ptr [rcx+19h], 6
0x18000cb64  jb      loc_18000C9B5
0x18000cb6a  mov     rcx, [rcx+10h]
0x18000cb6e  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18000cb75  mov     edx, 13h
0x18000cb7a  mov     r9, rdi
0x18000cb7d  call    WPP_SF_q
0x18000cb82  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb89  jmp     loc_18000C9B5
0x18000cb8e  test    byte ptr [rcx+1Ch], 4
0x18000cb92  jz      short loc_18000CB4A
0x18000cb94  cmp     byte ptr [rcx+19h], 6
0x18000cb98  jb      short loc_18000CB4A
0x18000cb9a  mov     rcx, [rcx+10h]
0x18000cb9e  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18000cba5  mov     edx, 1Ch
0x18000cbaa  mov     r9d, ebx
0x18000cbad  call    WPP_SF_d
0x18000cbb2  jmp     short loc_18000CB4A
0x18000cbb4  call    cs:__imp_GetLastError
0x18000cbba  mov     ebx, eax
0x18000cbbc  cmp     eax, 7Ah ; 'z'
0x18000cbbf  jnz     loc_18000CC53
0x18000cbc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbcc  cmp     rcx, r15
0x18000cbcf  jz      loc_18000CA06
0x18000cbd5  test    byte ptr [rcx+1Ch], 4
0x18000cbd9  jz      loc_18000CA06
0x18000cbdf  cmp     byte ptr [rcx+19h], 2
0x18000cbe3  jb      loc_18000CA06
0x18000cbe9  mov     rcx, [rcx+10h]
0x18000cbed  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18000cbf4  mov     edx, 16h
0x18000cbf9  mov     r9d, eax
0x18000cbfc  call    WPP_SF_d
0x18000cc01  jmp     loc_18000CA06
0x18000cc06  call    cs:__imp_GetLastError
0x18000cc0c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000cc12  mov     ebx, eax
0x18000cc14  cmp     ecx, 0FFFFFFFFh
0x18000cc17  jnz     loc_18000CCA9
0x18000cc1d  test    ebx, ebx
0x18000cc1f  jz      loc_18000CAFE
0x18000cc25  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc2c  cmp     rcx, r15
0x18000cc2f  jz      loc_18000CB05
0x18000cc35  test    byte ptr [rcx+1Ch], 4
0x18000cc39  jz      loc_18000CB05
0x18000cc3f  cmp     byte ptr [rcx+19h], 2
0x18000cc43  jb      loc_18000CB05
0x18000cc49  mov     edx, 17h
0x18000cc4e  jmp     loc_18000CE4C
0x18000cc53  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000cc59  cmp     ecx, 0FFFFFFFFh
0x18000cc5c  jz      short loc_18000CC73
0x18000cc5e  mov     r9d, ebx
0x18000cc61  lea     r8, aGetsidfromtoke_1; "GetSidFromToken: GetTokenInformation fa"...
0x18000cc68  mov     edx, 0Ch; dwFlags
0x18000cc6d  call    cs:__imp_TracePrintfExA
0x18000cc73  test    ebx, ebx
0x18000cc75  jz      loc_18000CAFE
0x18000cc7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc82  cmp     rcx, r15
0x18000cc85  jz      loc_18000CB05
0x18000cc8b  test    byte ptr [rcx+1Ch], 4
0x18000cc8f  jz      loc_18000CB05
0x18000cc95  cmp     byte ptr [rcx+19h], 2
0x18000cc99  jb      loc_18000CB05
0x18000cc9f  mov     edx, 15h
0x18000cca4  jmp     loc_18000CE4C
0x18000cca9  mov     r9d, ebx
0x18000ccac  lea     r8, aGetsidfromtoke; "GetSidFromToken: Malloc token_user fail"...
0x18000ccb3  mov     edx, 0Ch; dwFlags
0x18000ccb8  call    cs:__imp_TracePrintfExA
0x18000ccbe  jmp     loc_18000CC1D
0x18000ccc3  call    cs:__imp_GetLastError
0x18000ccc9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000cccf  mov     ebx, eax
0x18000ccd1  cmp     ecx, 0FFFFFFFFh
0x18000ccd4  jz      short loc_18000CCEB
0x18000ccd6  mov     r9d, eax
0x18000ccd9  lea     r8, aGetsidfromtoke_3; "GetSidFromToken: GetTokenInformation2 f"...
0x18000cce0  mov     edx, 0Ch; dwFlags
0x18000cce5  call    cs:__imp_TracePrintfExA
0x18000cceb  test    ebx, ebx
0x18000cced  jz      loc_18000CAF5
0x18000ccf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccfa  cmp     rcx, r15
0x18000ccfd  jz      loc_18000CAF5
0x18000cd03  test    byte ptr [rcx+1Ch], 4
0x18000cd07  jz      loc_18000CAF5
0x18000cd0d  cmp     byte ptr [rcx+19h], 2
0x18000cd11  jb      loc_18000CAF5
0x18000cd17  mov     edx, 18h
0x18000cd1c  mov     r9d, ebx
0x18000cd1f  jmp     loc_18000CE1C
0x18000cd24  call    cs:__imp_GetLastError
0x18000cd2a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000cd30  mov     ebx, eax
0x18000cd32  cmp     ecx, 0FFFFFFFFh
0x18000cd35  jz      short loc_18000CD4C
0x18000cd37  mov     r9d, eax
0x18000cd3a  lea     r8, aGetsidfromtoke_2; "GetSidFromToken: ConvertSidToStringSid "...
0x18000cd41  mov     edx, 0Ch; dwFlags
0x18000cd46  call    cs:__imp_TracePrintfExA
0x18000cd4c  test    ebx, ebx
0x18000cd4e  jz      loc_18000CAF5
0x18000cd54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd5b  cmp     rcx, r15
0x18000cd5e  jz      loc_18000CAF5
0x18000cd64  test    byte ptr [rcx+1Ch], 4
0x18000cd68  jz      loc_18000CAF5
0x18000cd6e  cmp     byte ptr [rcx+19h], 2
0x18000cd72  jb      loc_18000CAF5
0x18000cd78  mov     edx, 19h
0x18000cd7d  mov     r9d, ebx
0x18000cd80  jmp     loc_18000CE1C
0x18000cd85  mov     ebx, 0Eh
0x18000cd8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd91  cmp     rcx, r15
0x18000cd94  jz      loc_18000CAF5
0x18000cd9a  test    byte ptr [rcx+1Ch], 4
0x18000cd9e  jz      loc_18000CAF5
0x18000cda4  cmp     byte ptr [rcx+19h], 2
0x18000cda8  jb      loc_18000CAF5
0x18000cdae  mov     edx, 1Ah
0x18000cdb3  mov     r9d, ebx
0x18000cdb6  jmp     short loc_18000CE1C
0x18000cdb8  mov     ecx, 80070057h
0x18000cdbd  test    rbx, rbx
0x18000cdc0  jz      loc_18000CAE8
0x18000cdc6  mov     ebx, 57h ; 'W'
0x18000cdcb  mov     [rax], bp
0x18000cdce  mov     edi, ebx
0x18000cdd0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000cdd6  cmp     ecx, 0FFFFFFFFh
0x18000cdd9  jz      short loc_18000CDF0
0x18000cddb  mov     r9d, edi
0x18000cdde  lea     r8, aGetsidfromtoke_0; "GetSidFromToken: StringCchCopy failed w"...
0x18000cde5  mov     edx, 0Ch; dwFlags
0x18000cdea  call    cs:__imp_TracePrintfExA
0x18000cdf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdf7  cmp     rcx, r15
0x18000cdfa  jz      loc_18000CAF5
0x18000ce00  test    byte ptr [rcx+1Ch], 4
0x18000ce04  jz      loc_18000CAF5
0x18000ce0a  cmp     byte ptr [rcx+19h], 2
0x18000ce0e  jb      loc_18000CAF5
0x18000ce14  mov     edx, 1Bh
0x18000ce19  mov     r9d, edi
0x18000ce1c  mov     rcx, [rcx+10h]
0x18000ce20  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18000ce27  call    WPP_SF_d
0x18000ce2c  jmp     loc_18000CAF5
0x18000ce31  mov     ebx, 57h ; 'W'
0x18000ce36  cmp     rcx, r15
0x18000ce39  jz      short loc_18000CE64
0x18000ce3b  test    byte ptr [rcx+1Ch], 4
0x18000ce3f  jz      short loc_18000CE64
0x18000ce41  cmp     byte ptr [rcx+19h], 2
0x18000ce45  jb      short loc_18000CE64
0x18000ce47  mov     edx, 14h
0x18000ce4c  mov     rcx, [rcx+10h]
0x18000ce50  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18000ce57  mov     r9d, ebx
0x18000ce5a  call    WPP_SF_d
0x18000ce5f  jmp     loc_18000CAFE
0x18000ce64  mov     rax, [r14]
0x18000ce67  test    rax, rax
0x18000ce6a  jz      loc_18000CB2C
0x18000ce70  mov     rcx, rax; hMem
0x18000ce73  call    cs:__imp_GlobalFree
0x18000ce79  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce80  mov     [r14], rbp
0x18000ce83  jmp     loc_18000CB2C
```
