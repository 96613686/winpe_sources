# VpnGetTokenInformation

- ea: `0x1800e1d30`
- end: `0x1800e1e5d`
- name: `VpnGetTokenInformation`
- size: `301`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800c0ef0`

## callees

- `0x180005e0c`
- `0x1800a5770`
- `0x1800e1b9c`
- `0x1800e1d30`
- `0x1800e1f38`
- `0x1800e206c`
- `0x1800e5330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1dac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1dac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1e0e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e1d9d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e1dfd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e1d9d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e1dfd`

## string_xrefs

- `0x1800e1e17`: `VpnGetTokenInformation`
- `0x1800e1e36`: `VpnGetTokenInformation`
- `0x1800e1dbd`: `GetTokenInformation`
- `0x1800e1e07`: `GetTokenInformation`

## pseudocode

```c
__int64 __fastcall VpnGetTokenInformation(HANDLE TokenHandle, DWORD a2, _QWORD *a3)
{
  DWORD LastError; // eax
  void *v6; // rdi
  const char *v7; // rbx
  unsigned int v8; // ebx
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = a2;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 48, WPP_f6c99ea100633433985745fbf1db6cda_Traceguids);
  TokenInformationLength = 0;
  *a3 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LastError = GetLastError();
  if ( LastError == 122 || !LastError )
  {
    v6 = (void *)VpnAlloc(TokenInformationLength);
    if ( v6 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
      {
        v8 = 0;
        *a3 = v6;
        return v8;
      }
      v7 = "GetTokenInformation";
      LastError = GetLastError();
    }
    else
    {
      v7 = "VpnAlloc";
      LastError = 8;
    }
  }
  else
  {
    v6 = 0;
    v7 = "GetTokenInformation";
  }
  v8 = VpnReportErrorAsWinError("VpnGetTokenInformation", v7, LastError);
  if ( (v8 & 0x80000000) != 0 )
  {
    MprCommonFree(v6);
    return (unsigned int)VpnReportReturnError("VpnGetTokenInformation", v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1800e1d30  mov     [rsp+arg_0], rbx
0x1800e1d35  mov     [rsp+arg_10], rsi
0x1800e1d3a  mov     [rsp+TokenInformationLength], edx
0x1800e1d3e  push    rdi
0x1800e1d3f  sub     rsp, 30h
0x1800e1d43  mov     rsi, r8
0x1800e1d46  mov     rbx, rcx
0x1800e1d49  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e1d50  lea     rax, WPP_GLOBAL_Control
0x1800e1d57  cmp     rcx, rax
0x1800e1d5a  jz      short loc_1800E1D77
0x1800e1d5c  test    byte ptr [rcx+1Ch], 8
0x1800e1d60  jz      short loc_1800E1D77
0x1800e1d62  mov     rcx, [rcx+10h]
0x1800e1d66  lea     r8, WPP_f6c99ea100633433985745fbf1db6cda_Traceguids
0x1800e1d6d  mov     edx, 30h ; '0'
0x1800e1d72  call    WPP_SF_
0x1800e1d77  xor     r9d, r9d; TokenInformationLength
0x1800e1d7a  mov     [rsp+38h+TokenInformationLength], 0
0x1800e1d82  lea     rax, [rsp+38h+TokenInformationLength]
0x1800e1d87  mov     qword ptr [rsi], 0
0x1800e1d8e  xor     r8d, r8d; TokenInformation
0x1800e1d91  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800e1d96  mov     rcx, rbx; TokenHandle
0x1800e1d99  lea     edx, [r9+1]; TokenInformationClass
0x1800e1d9d  call    cs:__imp_GetTokenInformation
0x1800e1da3  test    eax, eax
0x1800e1da5  jz      short loc_1800E1DAC
0x1800e1da7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800e1dac  call    cs:__imp_GetLastError
0x1800e1db2  cmp     eax, 7Ah ; 'z'
0x1800e1db5  jz      short loc_1800E1DC6
0x1800e1db7  test    eax, eax
0x1800e1db9  jz      short loc_1800E1DC6
0x1800e1dbb  xor     edi, edi
0x1800e1dbd  lea     rbx, aGettokeninform; "GetTokenInformation"
0x1800e1dc4  jmp     short loc_1800E1E14
0x1800e1dc6  mov     ecx, [rsp+38h+TokenInformationLength]
0x1800e1dca  call    VpnAlloc
0x1800e1dcf  mov     rdi, rax
0x1800e1dd2  test    rax, rax
0x1800e1dd5  jnz     short loc_1800E1DE3
0x1800e1dd7  lea     rbx, aVpnalloc; "VpnAlloc"
0x1800e1dde  lea     eax, [rdi+8]
0x1800e1de1  jmp     short loc_1800E1E14
0x1800e1de3  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800e1de8  lea     rax, [rsp+38h+TokenInformationLength]
0x1800e1ded  mov     r8, rdi; TokenInformation
0x1800e1df0  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800e1df5  mov     edx, 1; TokenInformationClass
0x1800e1dfa  mov     rcx, rbx; TokenHandle
0x1800e1dfd  call    cs:__imp_GetTokenInformation
0x1800e1e03  test    eax, eax
0x1800e1e05  jnz     short loc_1800E1E46
0x1800e1e07  lea     rbx, aGettokeninform; "GetTokenInformation"
0x1800e1e0e  call    cs:__imp_GetLastError
0x1800e1e14  mov     r8d, eax
0x1800e1e17  lea     rcx, aVpngettokeninf; "VpnGetTokenInformation"
0x1800e1e1e  mov     rdx, rbx
0x1800e1e21  call    VpnReportErrorAsWinError
0x1800e1e26  mov     ebx, eax
0x1800e1e28  test    eax, eax
0x1800e1e2a  jns     short loc_1800E1E4B
0x1800e1e2c  mov     rcx, rdi; lpMem
0x1800e1e2f  call    MprCommonFree
0x1800e1e34  mov     edx, ebx
0x1800e1e36  lea     rcx, aVpngettokeninf; "VpnGetTokenInformation"
0x1800e1e3d  call    VpnReportReturnError
0x1800e1e42  mov     ebx, eax
0x1800e1e44  jmp     short loc_1800E1E4B
0x1800e1e46  xor     ebx, ebx
0x1800e1e48  mov     [rsi], rdi
0x1800e1e4b  mov     rsi, [rsp+38h+arg_10]
0x1800e1e50  mov     eax, ebx
0x1800e1e52  mov     rbx, [rsp+38h+arg_0]
0x1800e1e57  add     rsp, 30h
0x1800e1e5b  pop     rdi
0x1800e1e5c  retn
```
