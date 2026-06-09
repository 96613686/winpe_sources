# IsUsingSystemToken(void)

- ea: `0x180086b40`
- end: `0x180086c91`
- name: `?IsUsingSystemToken@@YA_NXZ`
- size: `337`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000eaa0`
- `0x18000ed40`
- `0x18000eec0`

## callees

- `0x180086b40`
- `0x180086c98`
- `0x180086ccc`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086bb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086bb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180086b70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180086b70`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180086b82`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180086b82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086c67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086c67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180086bc9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180086bc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086c5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086c5d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180086bae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180086bf4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180086bae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180086bf4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180086c1f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180086c1f`

## pseudocode

```c
bool IsUsingSystemToken(void)
{
  bool v0; // di
  HANDLE CurrentProcess; // rax
  PSID *v2; // rbx
  DWORD TokenInformationLength; // [rsp+30h] [rbp-49h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-41h] BYREF
  void **v6; // [rsp+40h] [rbp-39h] BYREF
  _BYTE pSid2[80]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v8[8]; // [rsp+98h] [rbp+1Fh] BYREF
  _BYTE v9[8]; // [rsp+A0h] [rbp+27h] BYREF
  _BYTE v10[8]; // [rsp+A8h] [rbp+2Fh] BYREF
  _BYTE v11[16]; // [rsp+B0h] [rbp+37h] BYREF

  v0 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    TokenInformationLength = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( GetLastError() == 122 )
    {
      v2 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
      if ( v2 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
        {
          ATL::CSid::CSid((ATL::CSid *)&v6, (struct _SID_IDENTIFIER_AUTHORITY *)&ATL::Sids::SecurityNTAuthority, 1u);
          v0 = EqualSid(*v2, pSid2);
          v6 = &ATL::CSid::`vftable';
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v11);
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v10);
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v9);
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v8);
        }
        LocalFree(v2);
      }
    }
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x180086b40  mov     [rsp-8+arg_0], rbx
0x180086b45  mov     [rsp-8+arg_8], rdi
0x180086b4a  push    rbp
0x180086b4b  lea     rbp, [rsp-57h]
0x180086b50  sub     rsp, 0D0h
0x180086b57  mov     rax, cs:__security_cookie
0x180086b5e  xor     rax, rsp
0x180086b61  mov     [rbp+57h+var_10], rax
0x180086b65  xor     dil, dil
0x180086b68  mov     [rbp+57h+TokenHandle], 0
0x180086b70  call    cs:__imp_GetCurrentProcess
0x180086b76  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180086b7a  mov     edx, 8; DesiredAccess
0x180086b7f  mov     rcx, rax; ProcessHandle
0x180086b82  call    cs:__imp_OpenProcessToken
0x180086b88  test    eax, eax
0x180086b8a  jz      loc_180086C6D
0x180086b90  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180086b94  lea     rax, [rbp+57h+TokenInformationLength]
0x180086b98  xor     r9d, r9d; TokenInformationLength
0x180086b9b  mov     [rbp+57h+TokenInformationLength], 0
0x180086ba2  xor     r8d, r8d; TokenInformation
0x180086ba5  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180086baa  lea     edx, [r9+1]; TokenInformationClass
0x180086bae  call    cs:__imp_GetTokenInformation
0x180086bb4  call    cs:__imp_GetLastError
0x180086bba  cmp     eax, 7Ah ; 'z'
0x180086bbd  jnz     loc_180086C63
0x180086bc3  mov     edx, [rbp+57h+TokenInformationLength]; uBytes
0x180086bc6  lea     ecx, [rax-3Ah]; uFlags
0x180086bc9  call    cs:__imp_LocalAlloc
0x180086bcf  mov     rbx, rax
0x180086bd2  test    rax, rax
0x180086bd5  jz      loc_180086C63
0x180086bdb  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180086bdf  lea     rax, [rbp+57h+TokenInformationLength]
0x180086be3  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180086be7  mov     r8, rbx; TokenInformation
0x180086bea  mov     edx, 1; TokenInformationClass
0x180086bef  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180086bf4  call    cs:__imp_GetTokenInformation
0x180086bfa  test    eax, eax
0x180086bfc  jz      short loc_180086C5A
0x180086bfe  mov     r9d, 12h
0x180086c04  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; struct _SID_IDENTIFIER_AUTHORITY *
0x180086c0b  lea     rcx, [rbp+57h+var_90]; this
0x180086c0f  lea     r8d, [r9-11h]; unsigned __int8
0x180086c13  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x180086c18  mov     rcx, [rbx]; pSid1
0x180086c1b  lea     rdx, [rbp+57h+pSid2]; pSid2
0x180086c1f  call    cs:__imp_EqualSid
0x180086c25  test    eax, eax
0x180086c27  lea     rcx, [rbp+57h+var_20]
0x180086c2b  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x180086c32  setnz   dil
0x180086c36  mov     [rbp+57h+var_90], rax
0x180086c3a  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x180086c3f  lea     rcx, [rbp+57h+var_28]
0x180086c43  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x180086c48  lea     rcx, [rbp+57h+var_30]
0x180086c4c  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x180086c51  lea     rcx, [rbp+57h+var_38]
0x180086c55  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x180086c5a  mov     rcx, rbx; hMem
0x180086c5d  call    cs:__imp_LocalFree
0x180086c63  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180086c67  call    cs:__imp_CloseHandle
0x180086c6d  mov     al, dil
0x180086c70  mov     rcx, [rbp+57h+var_10]
0x180086c74  xor     rcx, rsp; StackCookie
0x180086c77  call    __security_check_cookie
0x180086c7c  lea     r11, [rsp+0D0h+var_s0]
0x180086c84  mov     rbx, [r11+10h]
0x180086c88  mov     rdi, [r11+18h]
0x180086c8c  mov     rsp, r11
0x180086c8f  pop     rbp
0x180086c90  retn
```
