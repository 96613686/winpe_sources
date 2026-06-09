# CUstUser::_GetUserSid(void *,ushort *,ushort * *)

- ea: `0x18001cdb0`
- end: `0x18001d001`
- name: `?_GetUserSid@CUstUser@@KAJPEAXPEAGPEAPEAG@Z`
- size: `593`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPCWSTR lpString1, LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c64c`

## callees

- `0x18001afa0`
- `0x18001afc8`
- `0x18001b008`
- `0x18001cc24`
- `0x18001cdb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cdfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfa6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001cfe8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001cfe8`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001ce0f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001ce0f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cdec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cebb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cdec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cebb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001ceed`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001ceed`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001cf3a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001cf3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUstUser::_GetUserSid(HANDLE TokenHandle, LPCWSTR lpString1, LPWSTR *StringSid)
{
  PSID *v6; // rsi
  __int64 v7; // r9
  unsigned int v8; // ebx
  signed int v9; // eax
  PSID v10; // rcx
  int UserDomain; // edi
  __int64 v12; // r9
  signed int LastError; // eax
  UstCommon::CImpersonator *v14; // rcx
  __int64 v15; // rdx
  signed int v16; // eax
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF
  LPCWSTR lpString2; // [rsp+78h] [rbp+20h] BYREF

  *StringSid = 0;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
  {
    v6 = (PSID *)GlobalAlloc(0x40u, TokenInformationLength);
    if ( !v6 )
    {
      v8 = -2147024882;
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids, v7);
      }
      return v8;
    }
LABEL_13:
    if ( GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
    {
      v10 = *v6;
      lpString2 = 0;
      UserDomain = CUstUser::_GetUserDomain(v10, (unsigned __int16 **)&lpString2);
      if ( UserDomain >= 0 )
      {
        if ( lstrcmpiW(lpString1, lpString2) )
        {
          v8 = -2147024846;
          UserDomain = -2147024846;
          if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids, v12);
LABEL_35:
            GlobalFree(v6);
            return v8;
          }
        }
      }
      v8 = UserDomain;
      if ( UserDomain < 0 )
        goto LABEL_35;
      if ( ConvertSidToStringSidW(*v6, StringSid) )
      {
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids, *StringSid);
        }
        goto LABEL_35;
      }
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_35;
      }
      v15 = 16;
    }
    else
    {
      v16 = GetLastError();
      v8 = v16;
      if ( v16 > 0 )
        v8 = (unsigned __int16)v16 | 0x80070000;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_35;
      }
      v15 = 17;
    }
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids, v8);
    goto LABEL_35;
  }
  v6 = 0;
  v9 = GetLastError();
  v8 = v9;
  if ( v9 > 0 )
    v8 = (unsigned __int16)v9 | 0x80070000;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids, v8);
  }
  if ( (v8 & 0x80000000) == 0 )
    goto LABEL_13;
  return v8;
}

```

## disassembly

```asm
0x18001cdb0  mov     [rsp+arg_0], rbx
0x18001cdb5  push    rbp
0x18001cdb6  push    rsi
0x18001cdb7  push    rdi
0x18001cdb8  push    r12
0x18001cdba  push    r14
0x18001cdbc  sub     rsp, 30h
0x18001cdc0  xor     r9d, r9d; TokenInformationLength
0x18001cdc3  mov     qword ptr [r8], 0
0x18001cdca  mov     r14, r8
0x18001cdcd  mov     [rsp+58h+TokenInformationLength], 0
0x18001cdd5  mov     rbp, rdx
0x18001cdd8  lea     rax, [rsp+58h+TokenInformationLength]
0x18001cddd  xor     r8d, r8d; TokenInformation
0x18001cde0  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18001cde5  lea     edx, [r9+1]; TokenInformationClass
0x18001cde9  mov     rdi, rcx
0x18001cdec  call    cs:__imp_GetTokenInformation
0x18001cdf2  lea     r12, WPP_GLOBAL_Control
0x18001cdf9  test    eax, eax
0x18001cdfb  jnz     short loc_18001CE58
0x18001cdfd  call    cs:__imp_GetLastError
0x18001ce03  cmp     eax, 7Ah ; 'z'
0x18001ce06  jnz     short loc_18001CE58
0x18001ce08  mov     edx, [rsp+58h+TokenInformationLength]; dwBytes
0x18001ce0c  lea     ecx, [rax-3Ah]; uFlags
0x18001ce0f  call    cs:__imp_GlobalAlloc
0x18001ce15  mov     rsi, rax
0x18001ce18  test    rax, rax
0x18001ce1b  jnz     loc_18001CEA1
0x18001ce21  mov     ebx, 8007000Eh
0x18001ce26  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce2d  cmp     rcx, r12
0x18001ce30  jz      loc_18001CFEE
0x18001ce36  test    byte ptr [rcx+1Ch], 1
0x18001ce3a  jz      loc_18001CFEE
0x18001ce40  mov     rcx, [rcx+10h]
0x18001ce44  lea     edx, [rax+0Dh]
0x18001ce47  lea     r8, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids
0x18001ce4e  call    WPP_SF_
0x18001ce53  jmp     loc_18001CFEE
0x18001ce58  xor     esi, esi
0x18001ce5a  call    cs:__imp_GetLastError
0x18001ce60  mov     ebx, eax
0x18001ce62  test    eax, eax
0x18001ce64  jle     short loc_18001CE6F
0x18001ce66  movzx   ebx, ax
0x18001ce69  or      ebx, 80070000h
0x18001ce6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce76  cmp     rcx, r12
0x18001ce79  jz      short loc_18001CE99
0x18001ce7b  test    byte ptr [rcx+1Ch], 1
0x18001ce7f  jz      short loc_18001CE99
0x18001ce81  mov     rcx, [rcx+10h]
0x18001ce85  lea     r8, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids
0x18001ce8c  mov     edx, 0Eh
0x18001ce91  mov     r9d, ebx
0x18001ce94  call    WPP_SF_d
0x18001ce99  test    ebx, ebx
0x18001ce9b  js      loc_18001CFEE
0x18001cea1  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18001cea6  lea     rax, [rsp+58h+TokenInformationLength]
0x18001ceab  mov     r8, rsi; TokenInformation
0x18001ceae  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18001ceb3  mov     edx, 1; TokenInformationClass
0x18001ceb8  mov     rcx, rdi; TokenHandle
0x18001cebb  call    cs:__imp_GetTokenInformation
0x18001cec1  test    eax, eax
0x18001cec3  jz      loc_18001CFA6
0x18001cec9  mov     rcx, [rsi]; Sid
0x18001cecc  lea     rdx, [rsp+58h+lpString2]; unsigned __int16 **
0x18001ced1  mov     [rsp+58h+lpString2], 0
0x18001ceda  call    ?_GetUserDomain@CUstUser@@KAJPEAXPEAPEAG@Z; CUstUser::_GetUserDomain(void *,ushort * *)
0x18001cedf  mov     edi, eax
0x18001cee1  test    eax, eax
0x18001cee3  js      short loc_18001CF2A
0x18001cee5  mov     rdx, [rsp+58h+lpString2]; lpString2
0x18001ceea  mov     rcx, rbp; lpString1
0x18001ceed  call    cs:__imp_lstrcmpiW
0x18001cef3  test    eax, eax
0x18001cef5  jz      short loc_18001CF2A
0x18001cef7  mov     ebx, 80070032h
0x18001cefc  mov     edi, ebx
0x18001cefe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf05  cmp     rcx, r12
0x18001cf08  jz      short loc_18001CF2A
0x18001cf0a  test    byte ptr [rcx+1Ch], 1
0x18001cf0e  jz      short loc_18001CF2A
0x18001cf10  mov     rcx, [rcx+10h]
0x18001cf14  lea     r8, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids
0x18001cf1b  mov     edx, 0Ch
0x18001cf20  call    WPP_SF_
0x18001cf25  jmp     loc_18001CFE5
0x18001cf2a  mov     ebx, edi
0x18001cf2c  test    edi, edi
0x18001cf2e  js      loc_18001CFE5
0x18001cf34  mov     rcx, [rsi]; Sid
0x18001cf37  mov     rdx, r14; StringSid
0x18001cf3a  call    cs:__imp_ConvertSidToStringSidW
0x18001cf40  test    eax, eax
0x18001cf42  jz      short loc_18001CF78
0x18001cf44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf4b  cmp     rcx, r12
0x18001cf4e  jz      loc_18001CFE5
0x18001cf54  test    byte ptr [rcx+1Ch], 2
0x18001cf58  jz      loc_18001CFE5
0x18001cf5e  mov     r9, [r14]
0x18001cf61  lea     r8, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids
0x18001cf68  mov     rcx, [rcx+10h]
0x18001cf6c  mov     edx, 0Fh
0x18001cf71  call    WPP_SF_S
0x18001cf76  jmp     short loc_18001CFE5
0x18001cf78  call    cs:__imp_GetLastError
0x18001cf7e  mov     ebx, eax
0x18001cf80  test    eax, eax
0x18001cf82  jle     short loc_18001CF8D
0x18001cf84  movzx   ebx, ax
0x18001cf87  or      ebx, 80070000h
0x18001cf8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf94  cmp     rcx, r12
0x18001cf97  jz      short loc_18001CFE5
0x18001cf99  test    byte ptr [rcx+1Ch], 1
0x18001cf9d  jz      short loc_18001CFE5
0x18001cf9f  mov     edx, 10h
0x18001cfa4  jmp     short loc_18001CFD2
0x18001cfa6  call    cs:__imp_GetLastError
0x18001cfac  mov     ebx, eax
0x18001cfae  test    eax, eax
0x18001cfb0  jle     short loc_18001CFBB
0x18001cfb2  movzx   ebx, ax
0x18001cfb5  or      ebx, 80070000h
0x18001cfbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfc2  cmp     rcx, r12
0x18001cfc5  jz      short loc_18001CFE5
0x18001cfc7  test    byte ptr [rcx+1Ch], 1
0x18001cfcb  jz      short loc_18001CFE5
0x18001cfcd  mov     edx, 11h
0x18001cfd2  mov     rcx, [rcx+10h]
0x18001cfd6  lea     r8, WPP_fcee56d15a133c462e9c41fa2120893a_Traceguids
0x18001cfdd  mov     r9d, ebx
0x18001cfe0  call    WPP_SF_d
0x18001cfe5  mov     rcx, rsi; hMem
0x18001cfe8  call    cs:__imp_GlobalFree
0x18001cfee  mov     eax, ebx
0x18001cff0  mov     rbx, [rsp+58h+arg_0]
0x18001cff5  add     rsp, 30h
0x18001cff9  pop     r14
0x18001cffb  pop     r12
0x18001cffd  pop     rdi
0x18001cffe  pop     rsi
0x18001cfff  pop     rbp
0x18001d000  retn
```
