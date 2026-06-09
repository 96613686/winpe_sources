# NcbUtilsGetClientUserSid

- ea: `0x180004dc0`
- end: `0x180004ff4`
- name: `NcbUtilsGetClientUserSid`
- size: `564`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c3f0`
- `0x180020914`

## callees

- `0x180003ed0`
- `0x180004dc0`
- `0x1800050d0`
- `0x180009740`
- `0x18000a0a0`
- `0x18000a160`
- `0x18001d8e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fe7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004e06`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004e65`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004e06`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004e65`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180004e76`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180004e76`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004e83`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004e83`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004ea6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004ea6`

## string_xrefs

- `0x180004f03`: `NcbUtils: User sid information ended with`
- `0x180004fd6`: `Failed to malloc token buffer\n`
- `0x180004f71`: `NcbUtils: Failed to query thread tokenuser length`
- `0x180004f82`: `Failed to malloc user token buffer\n`
- `0x180004fb3`: `NcbUtils: Failed to query thread tokenuser buffer`

## pseudocode

```c
__int64 __fastcall NcbUtilsGetClientUserSid(HANDLE TokenHandle, void **a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  PSID *v6; // rbx
  __int64 v7; // r8
  DWORD v8; // edi
  void *v9; // rcx
  DWORD LengthSid; // esi
  void *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  DWORD LastError; // eax
  __int64 v16; // rdx
  DWORD v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  DWORD TokenInformationLength; // [rsp+30h] [rbp-68h] BYREF
  DWORD v21; // [rsp+38h] [rbp-60h] BYREF
  char v22[16]; // [rsp+40h] [rbp-58h] BYREF
  const wchar_t *v23; // [rsp+50h] [rbp-48h]
  __int64 v24; // [rsp+58h] [rbp-40h]
  DWORD *v25; // [rsp+60h] [rbp-38h]
  __int64 v26; // [rsp+68h] [rbp-30h]

  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError != 122 )
    {
      v6 = 0;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v9, v16, L"NcbUtils: Failed to query thread tokenuser length", LastError);
      goto LABEL_12;
    }
  }
  v6 = (PSID *)MALLOC(TokenInformationLength);
  if ( !v6 )
  {
    v8 = 8;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v5, v4, L"Failed to malloc user token buffer\n");
    goto LABEL_5;
  }
  v8 = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
  {
    v17 = GetLastError();
    v8 = v17;
    if ( v17 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v19, v18, L"NcbUtils: Failed to query thread tokenuser buffer", v17);
      goto LABEL_5;
    }
  }
  if ( IsValidSid(*v6) )
  {
    LengthSid = GetLengthSid(*v6);
    v11 = MALLOC(LengthSid);
    *a2 = v11;
    if ( v11 )
    {
      if ( !CopySid(LengthSid, v11, *v6) )
        v8 = GetLastError();
LABEL_12:
      if ( !v8 )
        goto LABEL_13;
      goto LABEL_5;
    }
    v8 = 8;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v13, v12, L"Failed to malloc token buffer\n");
LABEL_5:
    v9 = *a2;
    if ( *a2 )
    {
      VpnFree(v9);
      *a2 = 0;
    }
LABEL_13:
    if ( !v6 )
      goto LABEL_15;
  }
  VpnFree(v6);
LABEL_15:
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v21 = v8;
    v23 = L"NcbUtils: User sid information ended with";
    v24 = 84;
    v25 = &v21;
    v26 = 4;
    McGenEventWrite_EventWriteTransfer(v9, NcbApiStatus, v7, 3, v22);
  }
  return v8;
}

```

## disassembly

```asm
0x180004dc0  mov     r11, rsp
0x180004dc3  push    rbp
0x180004dc4  push    rdi
0x180004dc5  sub     rsp, 88h
0x180004dcc  mov     rax, cs:__security_cookie
0x180004dd3  xor     rax, rsp
0x180004dd6  mov     [rsp+98h+var_28], rax
0x180004ddb  mov     [r11+18h], rbx
0x180004ddf  lea     rax, [r11-68h]
0x180004de3  mov     [r11+20h], rsi
0x180004de7  xor     ebp, ebp
0x180004de9  mov     [r11-18h], r14
0x180004ded  xor     r9d, r9d; TokenInformationLength
0x180004df0  mov     r14, rdx
0x180004df3  mov     [rsp+98h+TokenInformationLength], ebp
0x180004df7  mov     edx, 1; TokenInformationClass
0x180004dfc  mov     [r11-78h], rax
0x180004e00  xor     r8d, r8d; TokenInformation
0x180004e03  mov     rsi, rcx
0x180004e06  call    cs:__imp_GetTokenInformation
0x180004e0c  test    eax, eax
0x180004e0e  jz      loc_180004F4D
0x180004e14  mov     ecx, [rsp+98h+TokenInformationLength]; dwBytes
0x180004e18  call    MALLOC
0x180004e1d  mov     rbx, rax
0x180004e20  test    rax, rax
0x180004e23  jnz     short loc_180004E49
0x180004e25  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004e2c  mov     edi, 8
0x180004e31  jnz     loc_180004F82
0x180004e37  mov     rcx, [r14]; lpMem
0x180004e3a  test    rcx, rcx
0x180004e3d  jz      short loc_180004EBC
0x180004e3f  call    VpnFree
0x180004e44  mov     [r14], rbp
0x180004e47  jmp     short loc_180004EBC
0x180004e49  mov     r9d, [rsp+98h+TokenInformationLength]; TokenInformationLength
0x180004e4e  lea     rax, [rsp+98h+TokenInformationLength]
0x180004e53  mov     r8, rbx; TokenInformation
0x180004e56  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x180004e5b  mov     edx, 1; TokenInformationClass
0x180004e60  mov     rcx, rsi; TokenHandle
0x180004e63  mov     edi, ebp
0x180004e65  call    cs:__imp_GetTokenInformation
0x180004e6b  test    eax, eax
0x180004e6d  jz      loc_180004F93
0x180004e73  mov     rcx, [rbx]; pSid
0x180004e76  call    cs:__imp_IsValidSid
0x180004e7c  test    eax, eax
0x180004e7e  jz      short loc_180004EC1
0x180004e80  mov     rcx, [rbx]; pSid
0x180004e83  call    cs:__imp_GetLengthSid
0x180004e89  mov     ecx, eax; dwBytes
0x180004e8b  mov     esi, eax
0x180004e8d  call    MALLOC
0x180004e92  mov     [r14], rax
0x180004e95  test    rax, rax
0x180004e98  jz      loc_180004FC4
0x180004e9e  mov     r8, [rbx]; pSourceSid
0x180004ea1  mov     rdx, rax; pDestinationSid
0x180004ea4  mov     ecx, esi; nDestinationSidLength
0x180004ea6  call    cs:__imp_CopySid
0x180004eac  test    eax, eax
0x180004eae  jz      loc_180004FE7
0x180004eb4  test    edi, edi
0x180004eb6  jnz     loc_180004E37
0x180004ebc  test    rbx, rbx
0x180004ebf  jz      short loc_180004EC9
0x180004ec1  mov     rcx, rbx; lpMem
0x180004ec4  call    VpnFree
0x180004ec9  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004ed0  mov     r14, [rsp+98h+var_18]
0x180004ed8  mov     rsi, [rsp+98h+arg_18]
0x180004ee0  mov     rbx, [rsp+98h+arg_10]
0x180004ee8  jnz     short loc_180004F03
0x180004eea  mov     eax, edi
0x180004eec  mov     rcx, [rsp+98h+var_28]
0x180004ef1  xor     rcx, rsp; StackCookie
0x180004ef4  call    __security_check_cookie
0x180004ef9  add     rsp, 88h
0x180004f00  pop     rdi
0x180004f01  pop     rbp
0x180004f02  retn
0x180004f03  lea     rax, aNcbutilsUserSi; "NcbUtils: User sid information ended wi"...
0x180004f0a  mov     [rsp+98h+var_60], edi
0x180004f0e  mov     [rsp+98h+var_48], rax
0x180004f13  lea     rdx, NcbApiStatus
0x180004f1a  lea     rax, [rsp+98h+var_60]
0x180004f1f  mov     [rsp+98h+var_40], 54h ; 'T'
0x180004f28  mov     [rsp+98h+var_38], rax
0x180004f2d  mov     r9d, 3
0x180004f33  lea     rax, [rsp+98h+var_58]
0x180004f38  mov     [rsp+98h+var_30], 4
0x180004f41  mov     [rsp+98h+ReturnLength], rax
0x180004f46  call    McGenEventWrite_EventWriteTransfer
0x180004f4b  jmp     short loc_180004EEA
0x180004f4d  call    cs:__imp_GetLastError
0x180004f53  mov     edi, eax
0x180004f55  cmp     eax, 7Ah ; 'z'
0x180004f58  jz      loc_180004E14
0x180004f5e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004f65  mov     rbx, rbp
0x180004f68  jz      loc_180004EB4
0x180004f6e  mov     r9d, eax
0x180004f71  lea     r8, aNcbutilsFailed_1; "NcbUtils: Failed to query thread tokenu"...
0x180004f78  call    McTemplateU0zq_EventWriteTransfer
0x180004f7d  jmp     loc_180004EB4
0x180004f82  lea     r8, aFailedToMalloc; "Failed to malloc user token buffer\n"
0x180004f89  call    McTemplateU0z_EventWriteTransfer
0x180004f8e  jmp     loc_180004E37
0x180004f93  call    cs:__imp_GetLastError
0x180004f99  mov     edi, eax
0x180004f9b  test    eax, eax
0x180004f9d  jz      loc_180004E73
0x180004fa3  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004faa  jz      loc_180004E37
0x180004fb0  mov     r9d, eax
0x180004fb3  lea     r8, aNcbutilsFailed_0; "NcbUtils: Failed to query thread tokenu"...
0x180004fba  call    McTemplateU0zq_EventWriteTransfer
0x180004fbf  jmp     loc_180004E37
0x180004fc4  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004fcb  mov     edi, 8
0x180004fd0  jz      loc_180004E37
0x180004fd6  lea     r8, aFailedToMalloc_0; "Failed to malloc token buffer\n"
0x180004fdd  call    McTemplateU0z_EventWriteTransfer
0x180004fe2  jmp     loc_180004E37
0x180004fe7  call    cs:__imp_GetLastError
0x180004fed  mov     edi, eax
0x180004fef  jmp     loc_180004EB4
```
