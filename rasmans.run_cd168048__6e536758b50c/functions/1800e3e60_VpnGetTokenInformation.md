# VpnGetTokenInformation

- ea: `0x1800e3e60`
- end: `0x1800e3fa6`
- name: `VpnGetTokenInformation`
- size: `326`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800c6be8`

## callees

- `0x180005bcc`
- `0x1800ab634`
- `0x1800e3ca0`
- `0x1800e3e60`
- `0x1800e4080`
- `0x1800e4184`
- `0x1800e6f64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3ee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3ee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3f50`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e3ecd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e3f39`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e3ecd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800e3f39`

## string_xrefs

- `0x1800e3ef9`: `GetTokenInformation`
- `0x1800e3f49`: `GetTokenInformation`
- `0x1800e3f5f`: `VpnGetTokenInformation`
- `0x1800e3f7e`: `VpnGetTokenInformation`

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
0x1800e3e60  mov     [rsp+arg_0], rbx
0x1800e3e65  mov     [rsp+arg_10], rsi
0x1800e3e6a  mov     [rsp+TokenInformationLength], edx
0x1800e3e6e  push    rdi
0x1800e3e6f  sub     rsp, 30h
0x1800e3e73  mov     rsi, r8
0x1800e3e76  mov     rbx, rcx
0x1800e3e79  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3e80  lea     rax, WPP_GLOBAL_Control
0x1800e3e87  cmp     rcx, rax
0x1800e3e8a  jz      short loc_1800E3EA7
0x1800e3e8c  test    byte ptr [rcx+1Ch], 8
0x1800e3e90  jz      short loc_1800E3EA7
0x1800e3e92  mov     rcx, [rcx+10h]
0x1800e3e96  lea     r8, WPP_f6c99ea100633433985745fbf1db6cda_Traceguids
0x1800e3e9d  mov     edx, 30h ; '0'
0x1800e3ea2  call    WPP_SF_
0x1800e3ea7  xor     r9d, r9d; TokenInformationLength
0x1800e3eaa  mov     [rsp+38h+TokenInformationLength], 0
0x1800e3eb2  lea     rax, [rsp+38h+TokenInformationLength]
0x1800e3eb7  mov     qword ptr [rsi], 0
0x1800e3ebe  xor     r8d, r8d; TokenInformation
0x1800e3ec1  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800e3ec6  mov     rcx, rbx; TokenHandle
0x1800e3ec9  lea     edx, [r9+1]; TokenInformationClass
0x1800e3ecd  call    cs:__imp_GetTokenInformation
0x1800e3ed4  nop     dword ptr [rax+rax+00h]
0x1800e3ed9  test    eax, eax
0x1800e3edb  jz      short loc_1800E3EE2
0x1800e3edd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800e3ee2  call    cs:__imp_GetLastError
0x1800e3ee9  nop     dword ptr [rax+rax+00h]
0x1800e3eee  cmp     eax, 7Ah ; 'z'
0x1800e3ef1  jz      short loc_1800E3F02
0x1800e3ef3  test    eax, eax
0x1800e3ef5  jz      short loc_1800E3F02
0x1800e3ef7  xor     edi, edi
0x1800e3ef9  lea     rbx, aGettokeninform; "GetTokenInformation"
0x1800e3f00  jmp     short loc_1800E3F5C
0x1800e3f02  mov     ecx, [rsp+38h+TokenInformationLength]
0x1800e3f06  call    VpnAlloc
0x1800e3f0b  mov     rdi, rax
0x1800e3f0e  test    rax, rax
0x1800e3f11  jnz     short loc_1800E3F1F
0x1800e3f13  lea     rbx, aVpnalloc; "VpnAlloc"
0x1800e3f1a  lea     eax, [rdi+8]
0x1800e3f1d  jmp     short loc_1800E3F5C
0x1800e3f1f  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800e3f24  lea     rax, [rsp+38h+TokenInformationLength]
0x1800e3f29  mov     r8, rdi; TokenInformation
0x1800e3f2c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800e3f31  mov     edx, 1; TokenInformationClass
0x1800e3f36  mov     rcx, rbx; TokenHandle
0x1800e3f39  call    cs:__imp_GetTokenInformation
0x1800e3f40  nop     dword ptr [rax+rax+00h]
0x1800e3f45  test    eax, eax
0x1800e3f47  jnz     short loc_1800E3F8E
0x1800e3f49  lea     rbx, aGettokeninform; "GetTokenInformation"
0x1800e3f50  call    cs:__imp_GetLastError
0x1800e3f57  nop     dword ptr [rax+rax+00h]
0x1800e3f5c  mov     r8d, eax
0x1800e3f5f  lea     rcx, aVpngettokeninf; "VpnGetTokenInformation"
0x1800e3f66  mov     rdx, rbx
0x1800e3f69  call    VpnReportErrorAsWinError
0x1800e3f6e  mov     ebx, eax
0x1800e3f70  test    eax, eax
0x1800e3f72  jns     short loc_1800E3F93
0x1800e3f74  mov     rcx, rdi; lpMem
0x1800e3f77  call    MprCommonFree
0x1800e3f7c  mov     edx, ebx
0x1800e3f7e  lea     rcx, aVpngettokeninf; "VpnGetTokenInformation"
0x1800e3f85  call    VpnReportReturnError
0x1800e3f8a  mov     ebx, eax
0x1800e3f8c  jmp     short loc_1800E3F93
0x1800e3f8e  xor     ebx, ebx
0x1800e3f90  mov     [rsi], rdi
0x1800e3f93  mov     rsi, [rsp+38h+arg_10]
0x1800e3f98  mov     eax, ebx
0x1800e3f9a  mov     rbx, [rsp+38h+arg_0]
0x1800e3f9f  add     rsp, 30h
0x1800e3fa3  pop     rdi
0x1800e3fa4  retn
```
