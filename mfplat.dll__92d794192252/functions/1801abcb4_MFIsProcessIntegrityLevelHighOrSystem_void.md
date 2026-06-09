# MFIsProcessIntegrityLevelHighOrSystem(void)

- ea: `0x1801abcb4`
- end: `0x1801abef8`
- name: `?MFIsProcessIntegrityLevelHighOrSystem@@YAHXZ`
- size: `580`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180113cdc`

## callees

- `0x1800214fc`
- `0x180120030`
- `0x180128588`
- `0x180130b70`
- `0x18013ac20`
- `0x1801abc24`
- `0x1801abc80`
- `0x1801abcb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801abcdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801abcdb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801abceb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801abceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abcfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abd04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abd0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abd8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abd96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abda0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abda8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abe41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abe4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abe53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abcfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abd04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abd0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abd8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abd96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abda0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abda8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abe41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abe4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801abe53`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1801abe83`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1801abea7`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1801abe83`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1801abea7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801abd67`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801abe37`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801abd67`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801abe37`

## pseudocode

```c
__int64 MFIsProcessIntegrityLevelHighOrSystem(void)
{
  PSID *v0; // rdi
  HANDLE CurrentProcess; // rax
  signed int v2; // eax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  __int64 unique; // rax
  void *v6; // rcx
  __int64 v7; // rdx
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+28h] BYREF
  void *v11; // [rsp+60h] [rbp+30h] BYREF
  LPVOID TokenInformation; // [rsp+68h] [rbp+38h] BYREF

  v0 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v2 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0x80070000 : GetLastError();
    if ( v2 < 0 )
    {
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
LABEL_9:
        v4 = 0;
        goto LABEL_39;
      }
      v3 = 10;
LABEL_8:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, WPP_f849e91a226d3327bc126a7da74f5d2d_Traceguids, 0, v2);
      goto LABEL_9;
    }
  }
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
  {
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_f849e91a226d3327bc126a7da74f5d2d_Traceguids,
        0,
        -2147418113);
    goto LABEL_9;
  }
  if ( GetLastError() != 122 )
  {
    v2 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0x80070000 : GetLastError();
    if ( v2 < 0 )
    {
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_9;
      v3 = 12;
      goto LABEL_8;
    }
  }
  unique = wil::make_unique_nothrow<unsigned char [0]>(&v11, TokenInformationLength);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(&TokenInformation, unique);
  v6 = v11;
  v11 = 0;
  if ( v6 )
    operator delete(v6);
  v0 = (PSID *)TokenInformation;
  if ( !TokenInformation )
  {
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)((_DWORD)TokenInformation + 13),
        WPP_f849e91a226d3327bc126a7da74f5d2d_Traceguids,
        0,
        -2147024882);
    goto LABEL_9;
  }
  if ( !GetTokenInformation(
          TokenHandle,
          TokenIntegrityLevel,
          TokenInformation,
          TokenInformationLength,
          &TokenInformationLength) )
  {
    v2 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0x80070000 : GetLastError();
    if ( v2 < 0 )
    {
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_9;
      v3 = 14;
      goto LABEL_8;
    }
  }
  if ( IsWellKnownSid(*v0, WinHighLabelSid) )
  {
    v4 = 1;
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_39;
    v7 = 15;
    goto LABEL_38;
  }
  v4 = 0;
  if ( IsWellKnownSid(*v0, WinSystemLabelSid) )
  {
    v4 = 1;
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v7 = 16;
LABEL_38:
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_f849e91a226d3327bc126a7da74f5d2d_Traceguids);
    }
  }
LABEL_39:
  if ( v0 )
    operator delete(v0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x1801abcb4  push    rbp
0x1801abcb6  push    rbx
0x1801abcb7  push    rdi
0x1801abcb8  mov     rbp, rsp
0x1801abcbb  sub     rsp, 30h
0x1801abcbf  xor     edi, edi
0x1801abcc1  mov     [rbp+TokenHandle], 0
0x1801abcc9  xor     edx, edx
0x1801abccb  mov     [rbp+TokenInformation], rdi
0x1801abccf  lea     rcx, [rbp+TokenHandle]
0x1801abcd3  mov     [rbp+TokenInformationLength], edi
0x1801abcd6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801abcdb  call    cs:__imp_GetCurrentProcess
0x1801abce1  mov     rcx, rax; ProcessHandle
0x1801abce4  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1801abce8  lea     edx, [rdi+8]; DesiredAccess
0x1801abceb  call    cs:__imp_OpenProcessToken
0x1801abcf1  mov     ebx, 80070000h
0x1801abcf6  test    eax, eax
0x1801abcf8  jnz     short loc_1801ABD50
0x1801abcfa  call    cs:__imp_GetLastError
0x1801abd00  test    eax, eax
0x1801abd02  jg      short loc_1801ABD0C
0x1801abd04  call    cs:__imp_GetLastError
0x1801abd0a  jmp     short loc_1801ABD17
0x1801abd0c  call    cs:__imp_GetLastError
0x1801abd12  movzx   eax, ax
0x1801abd15  or      eax, ebx
0x1801abd17  test    eax, eax
0x1801abd19  jns     short loc_1801ABD50
0x1801abd1b  mov     ebx, 1
0x1801abd20  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1801abd26  jb      short loc_1801ABD49
0x1801abd28  lea     edx, [rbx+9]
0x1801abd2b  mov     dword ptr [rsp+30h+ReturnLength], eax
0x1801abd2f  mov     rcx, cs:WPP_GLOBAL_Control
0x1801abd36  lea     r8, WPP_f849e91a226d3327bc126a7da74f5d2d_Traceguids
0x1801abd3d  xor     r9d, r9d
0x1801abd40  mov     rcx, [rcx+10h]
0x1801abd44  call    WPP_SF_qD
0x1801abd49  xor     ebx, ebx
0x1801abd4b  jmp     loc_1801ABED8
0x1801abd50  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1801abd54  lea     rax, [rbp+TokenInformationLength]
0x1801abd58  xor     r9d, r9d; TokenInformationLength
0x1801abd5b  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1801abd60  xor     r8d, r8d; TokenInformation
0x1801abd63  lea     edx, [r9+19h]; TokenInformationClass
0x1801abd67  call    cs:__imp_GetTokenInformation
0x1801abd6d  test    eax, eax
0x1801abd6f  jz      short loc_1801ABD8B
0x1801abd71  mov     ebx, 1
0x1801abd76  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1801abd7c  jb      short loc_1801ABD49
0x1801abd7e  lea     edx, [rbx+0Ah]
0x1801abd81  mov     dword ptr [rsp+30h+ReturnLength], 8000FFFFh
0x1801abd89  jmp     short loc_1801ABD2F
0x1801abd8b  call    cs:__imp_GetLastError
0x1801abd91  cmp     eax, 7Ah ; 'z'
0x1801abd94  jz      short loc_1801ABDCC
0x1801abd96  call    cs:__imp_GetLastError
0x1801abd9c  test    eax, eax
0x1801abd9e  jg      short loc_1801ABDA8
0x1801abda0  call    cs:__imp_GetLastError
0x1801abda6  jmp     short loc_1801ABDB3
0x1801abda8  call    cs:__imp_GetLastError
0x1801abdae  movzx   eax, ax
0x1801abdb1  or      eax, ebx
0x1801abdb3  test    eax, eax
0x1801abdb5  jns     short loc_1801ABDCC
0x1801abdb7  mov     ebx, 1
0x1801abdbc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1801abdc2  jb      short loc_1801ABD49
0x1801abdc4  lea     edx, [rbx+0Bh]
0x1801abdc7  jmp     loc_1801ABD2B
0x1801abdcc  mov     edx, [rbp+TokenInformationLength]
0x1801abdcf  lea     rcx, [rbp+arg_10]
0x1801abdd3  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x1801abdd8  mov     rdx, rax
0x1801abddb  lea     rcx, [rbp+TokenInformation]
0x1801abddf  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x1801abde4  mov     rcx, [rbp+arg_10]; void *
0x1801abde8  mov     [rbp+arg_10], rdi
0x1801abdec  test    rcx, rcx
0x1801abdef  jz      short loc_1801ABDF6
0x1801abdf1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801abdf6  mov     rdi, [rbp+TokenInformation]
0x1801abdfa  test    rdi, rdi
0x1801abdfd  jnz     short loc_1801ABE1E
0x1801abdff  lea     ebx, [rdi+1]
0x1801abe02  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1801abe08  jb      loc_1801ABD49
0x1801abe0e  lea     edx, [rdi+0Dh]
0x1801abe11  mov     dword ptr [rsp+30h+ReturnLength], 8007000Eh
0x1801abe19  jmp     loc_1801ABD2F
0x1801abe1e  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1801abe22  lea     rax, [rbp+TokenInformationLength]
0x1801abe26  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1801abe2a  mov     r8, rdi; TokenInformation
0x1801abe2d  mov     edx, 19h; TokenInformationClass
0x1801abe32  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1801abe37  call    cs:__imp_GetTokenInformation
0x1801abe3d  test    eax, eax
0x1801abe3f  jnz     short loc_1801ABE7B
0x1801abe41  call    cs:__imp_GetLastError
0x1801abe47  test    eax, eax
0x1801abe49  jg      short loc_1801ABE53
0x1801abe4b  call    cs:__imp_GetLastError
0x1801abe51  jmp     short loc_1801ABE5E
0x1801abe53  call    cs:__imp_GetLastError
0x1801abe59  movzx   eax, ax
0x1801abe5c  or      eax, ebx
0x1801abe5e  test    eax, eax
0x1801abe60  jns     short loc_1801ABE7B
0x1801abe62  mov     ebx, 1
0x1801abe67  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1801abe6d  jb      loc_1801ABD49
0x1801abe73  lea     edx, [rbx+0Dh]
0x1801abe76  jmp     loc_1801ABD2B
0x1801abe7b  mov     rcx, [rdi]; pSid
0x1801abe7e  mov     edx, 44h ; 'D'; WellKnownSidType
0x1801abe83  call    cs:__imp_IsWellKnownSid
0x1801abe89  test    eax, eax
0x1801abe8b  jz      short loc_1801ABE9F
0x1801abe8d  mov     ebx, 1
0x1801abe92  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1801abe98  jb      short loc_1801ABED8
0x1801abe9a  lea     edx, [rbx+0Eh]
0x1801abe9d  jmp     short loc_1801ABEC1
0x1801abe9f  mov     rcx, [rdi]; pSid
0x1801abea2  xor     ebx, ebx
0x1801abea4  lea     edx, [rbx+45h]; WellKnownSidType
0x1801abea7  call    cs:__imp_IsWellKnownSid
0x1801abead  test    eax, eax
0x1801abeaf  jz      short loc_1801ABED8
0x1801abeb1  mov     ebx, 1
0x1801abeb6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1801abebc  jb      short loc_1801ABED8
0x1801abebe  lea     edx, [rbx+0Fh]
0x1801abec1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801abec8  lea     r8, WPP_f849e91a226d3327bc126a7da74f5d2d_Traceguids
0x1801abecf  mov     rcx, [rcx+10h]
0x1801abed3  call    WPP_SF_
0x1801abed8  test    rdi, rdi
0x1801abedb  jz      short loc_1801ABEE5
0x1801abedd  mov     rcx, rdi; void *
0x1801abee0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801abee5  lea     rcx, [rbp+TokenHandle]
0x1801abee9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801abeee  mov     eax, ebx
0x1801abef0  add     rsp, 30h
0x1801abef4  pop     rdi
0x1801abef5  pop     rbx
0x1801abef6  pop     rbp
0x1801abef7  retn
```
