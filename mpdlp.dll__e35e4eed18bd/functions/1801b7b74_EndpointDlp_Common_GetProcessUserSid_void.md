# EndpointDlp::Common::GetProcessUserSid(void *)

- ea: `0x1801b7b74`
- end: `0x1801b7d05`
- name: `?GetProcessUserSid@Common@EndpointDlp@@YA?AV?$vector@EV?$allocator@E@std@@@std@@PEAX@Z`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180180938`

## callees

- `0x180061130`
- `0x180065438`
- `0x1800a1824`
- `0x1800b9b34`
- `0x18010cb40`
- `0x180154c6c`
- `0x1801b7b74`
- `0x18023a6d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801b7bfe`
- `KERNEL32!GetLastError` at `0x1801b7bfe`
- `KERNEL32!CloseHandle` at `0x1801b7cdb`
- `KERNEL32!CloseHandle` at `0x1801b7cdb`
- `ADVAPI32!GetLengthSid` at `0x1801b7c96`
- `ADVAPI32!GetLengthSid` at `0x1801b7c96`
- `ADVAPI32!GetTokenInformation` at `0x1801b7bf4`
- `ADVAPI32!GetTokenInformation` at `0x1801b7c70`
- `ADVAPI32!GetTokenInformation` at `0x1801b7bf4`
- `ADVAPI32!GetTokenInformation` at `0x1801b7c70`
- `ADVAPI32!OpenProcessToken` at `0x1801b7bb1`
- `ADVAPI32!OpenProcessToken` at `0x1801b7bb1`

## string_xrefs

- `0x1801b7bca`: `src\epp\Dlp\EndpointDlp\Common\src\ProcessUtils.cpp`
- `0x1801b7c21`: `src\epp\Dlp\EndpointDlp\Common\src\ProcessUtils.cpp`
- `0x1801b7c82`: `src\epp\Dlp\EndpointDlp\Common\src\ProcessUtils.cpp`
- `0x1801b7bbb`: `Failed to retrieve the process user token`
- `0x1801b7c11`: `Failed to get the size of token user`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EndpointDlp::Common::GetProcessUserSid(__int64 a1, void *a2)
{
  unsigned int v3; // eax
  bool v4; // zf
  unsigned __int8 v5; // al
  PSID *v6; // rdi
  unsigned int v7; // eax
  DWORD LengthSid; // eax
  DWORD v9; // ebx
  const char *v11; // [rsp+28h] [rbp-48h]
  const char *v12; // [rsp+28h] [rbp-48h]
  const char *v13; // [rsp+28h] [rbp-48h]
  _BYTE v14[8]; // [rsp+30h] [rbp-40h] BYREF
  DWORD TokenInformationLength; // [rsp+38h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-30h] BYREF
  LPVOID TokenInformation[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v18; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  TokenHandle = 0;
  v3 = OpenProcessToken(a2, 0xAu, &TokenHandle);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x9D,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Common\\src\\ProcessUtils.cpp",
    (const char *)v3,
    (int)"Failed to retrieve the process user token",
    v11);
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength)
    || (v4 = GetLastError() == 122, v5 = 1, v4) )
  {
    v5 = 0;
  }
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0xA3,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Common\\src\\ProcessUtils.cpp",
    (const char *)v5,
    (bool)"Failed to get the size of token user",
    v12);
  *(_OWORD *)TokenInformation = 0;
  v18 = 0;
  v14[0] = 0;
  std::vector<unsigned char>::vector<unsigned char>(TokenInformation, TokenInformationLength, v14);
  v6 = (PSID *)TokenInformation[0];
  v7 = GetTokenInformation(TokenHandle, TokenUser, TokenInformation[0], TokenInformationLength, &TokenInformationLength);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0xA9,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Common\\src\\ProcessUtils.cpp",
    (const char *)v7,
    (int)"Failed to retrieve the process user token",
    v13);
  LengthSid = GetLengthSid(*v6);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v9 = LengthSid;
  std::vector<unsigned char>::vector<unsigned char>(a1, LengthSid);
  memmove(*(void **)a1, *v6, v9);
  std::vector<unsigned char>::_Tidy(TokenInformation);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return a1;
}

```

## disassembly

```asm
0x1801b7b74  mov     [rsp-18h+arg_10], rbx
0x1801b7b79  mov     [rsp-18h+arg_18], rsi
0x1801b7b7e  push    rbp
0x1801b7b7f  push    rdi
0x1801b7b80  push    r12
0x1801b7b82  mov     rbp, rsp
0x1801b7b85  sub     rsp, 70h
0x1801b7b89  mov     rax, cs:__security_cookie
0x1801b7b90  xor     rax, rsp
0x1801b7b93  mov     [rbp+var_10], rax
0x1801b7b97  mov     rax, rdx
0x1801b7b9a  mov     rsi, rcx
0x1801b7b9d  mov     [rbp+TokenHandle], rcx
0x1801b7ba1  xor     ebx, ebx
0x1801b7ba3  mov     [rbp+TokenHandle], rbx
0x1801b7ba7  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1801b7bab  lea     edx, [rbx+0Ah]; DesiredAccess
0x1801b7bae  mov     rcx, rax; ProcessHandle
0x1801b7bb1  call    cs:__imp_OpenProcessToken
0x1801b7bb7  mov     rcx, [rbp+18h]; this
0x1801b7bbb  lea     r12, aFailedToRetrie_0; "Failed to retrieve the process user tok"...
0x1801b7bc2  mov     [rsp+70h+ReturnLength], r12; int
0x1801b7bc7  mov     r9d, eax; char *
0x1801b7bca  lea     r8, aSrcEppDlpEndpo_18; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x1801b7bd1  mov     edx, 9Dh; void *
0x1801b7bd6  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1801b7bdb  mov     [rbp+TokenInformationLength], ebx
0x1801b7bde  lea     rax, [rbp+TokenInformationLength]
0x1801b7be2  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1801b7be7  xor     r9d, r9d; TokenInformationLength
0x1801b7bea  xor     r8d, r8d; TokenInformation
0x1801b7bed  lea     edx, [rbx+1]; TokenInformationClass
0x1801b7bf0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1801b7bf4  call    cs:__imp_GetTokenInformation
0x1801b7bfa  test    eax, eax
0x1801b7bfc  jnz     short loc_1801B7C0B
0x1801b7bfe  call    cs:__imp_GetLastError
0x1801b7c04  cmp     eax, 7Ah ; 'z'
0x1801b7c07  mov     al, 1
0x1801b7c09  jnz     short loc_1801B7C0D
0x1801b7c0b  mov     al, bl
0x1801b7c0d  mov     rcx, [rbp+18h]; this
0x1801b7c11  lea     rdx, aFailedToGetThe; "Failed to get the size of token user"
0x1801b7c18  mov     [rsp+70h+ReturnLength], rdx; bool
0x1801b7c1d  movzx   r9d, al; char *
0x1801b7c21  lea     r8, aSrcEppDlpEndpo_18; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x1801b7c28  mov     edx, 0A3h; void *
0x1801b7c2d  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1801b7c32  xorps   xmm0, xmm0
0x1801b7c35  xor     eax, eax
0x1801b7c37  movups  xmmword ptr [rbp+TokenInformation], xmm0
0x1801b7c3b  mov     [rbp+var_18], rax
0x1801b7c3f  mov     [rbp+var_40], bl
0x1801b7c42  mov     edx, [rbp+TokenInformationLength]
0x1801b7c45  lea     r8, [rbp+var_40]
0x1801b7c49  lea     rcx, [rbp+TokenInformation]
0x1801b7c4d  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x1801b7c52  nop
0x1801b7c53  mov     rdi, [rbp+TokenInformation]
0x1801b7c57  lea     rax, [rbp+TokenInformationLength]
0x1801b7c5b  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1801b7c60  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1801b7c64  mov     r8, rdi; TokenInformation
0x1801b7c67  mov     edx, 1; TokenInformationClass
0x1801b7c6c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1801b7c70  call    cs:__imp_GetTokenInformation
0x1801b7c76  mov     rcx, [rbp+18h]; this
0x1801b7c7a  mov     [rsp+70h+ReturnLength], r12; int
0x1801b7c7f  mov     r9d, eax; char *
0x1801b7c82  lea     r8, aSrcEppDlpEndpo_18; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x1801b7c89  mov     edx, 0A9h; void *
0x1801b7c8e  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1801b7c93  mov     rcx, [rdi]; pSid
0x1801b7c96  call    cs:__imp_GetLengthSid
0x1801b7c9c  xorps   xmm0, xmm0
0x1801b7c9f  xor     ecx, ecx
0x1801b7ca1  movups  xmmword ptr [rsi], xmm0
0x1801b7ca4  mov     [rsi+10h], rcx
0x1801b7ca8  mov     ebx, eax
0x1801b7caa  mov     edx, eax
0x1801b7cac  mov     rcx, rsi
0x1801b7caf  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1801b7cb4  mov     r8d, ebx; Size
0x1801b7cb7  mov     rdx, [rdi]; Src
0x1801b7cba  mov     rcx, [rsi]; void *
0x1801b7cbd  call    memmove
0x1801b7cc2  nop
0x1801b7cc3  lea     rcx, [rbp+TokenInformation]
0x1801b7cc7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801b7ccc  nop
0x1801b7ccd  mov     rcx, [rbp+TokenHandle]; hObject
0x1801b7cd1  lea     rdx, [rcx-1]
0x1801b7cd5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801b7cd9  ja      short loc_1801B7CE1
0x1801b7cdb  call    cs:__imp_CloseHandle
0x1801b7ce1  mov     rax, rsi
0x1801b7ce4  mov     rcx, [rbp+var_10]
0x1801b7ce8  xor     rcx, rsp; StackCookie
0x1801b7ceb  call    __security_check_cookie
0x1801b7cf0  lea     r11, [rsp+70h+var_s0]
0x1801b7cf5  mov     rbx, [r11+30h]
0x1801b7cf9  mov     rsi, [r11+38h]
0x1801b7cfd  mov     rsp, r11
0x1801b7d00  pop     r12
0x1801b7d02  pop     rdi
0x1801b7d03  pop     rbp
0x1801b7d04  retn
```
