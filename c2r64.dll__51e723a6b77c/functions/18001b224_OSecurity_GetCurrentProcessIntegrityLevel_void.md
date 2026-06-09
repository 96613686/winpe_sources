# OSecurity::GetCurrentProcessIntegrityLevel(void)

- ea: `0x18001b224`
- end: `0x18001b54c`
- name: `?GetCurrentProcessIntegrityLevel@OSecurity@@SAKXZ`
- size: `808`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800077d4`
- `0x180019848`

## callees

- `0x18000cc6c`
- `0x18001b224`
- `0x18001b54c`
- `0x18001b5c0`
- `0x18001b964`
- `0x18003882c`
- `0x18003e690`
- `0x1800409e0`
- `0x1801320a8`
- `0x180135890`
- `0x180135968`
- `0x1801460c0`
- `0x180146440`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18001b266`
- `KERNEL32!GetCurrentProcess` at `0x18001b266`
- `KERNEL32!GetLastError` at `0x18001b2dc`
- `KERNEL32!GetLastError` at `0x18001b4a2`
- `KERNEL32!GetLastError` at `0x18001b4fa`
- `KERNEL32!GetLastError` at `0x18001b51d`
- `KERNEL32!GetLastError` at `0x18001b2dc`
- `KERNEL32!GetLastError` at `0x18001b4a2`
- `KERNEL32!GetLastError` at `0x18001b4fa`
- `KERNEL32!GetLastError` at `0x18001b51d`
- `KERNEL32!CloseHandle` at `0x18001b426`
- `KERNEL32!CloseHandle` at `0x18001b426`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001b375`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001b46a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001b375`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001b46a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b40e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18001b40e`
- `ADVAPI32!OpenProcessToken` at `0x18001b277`
- `ADVAPI32!OpenProcessToken` at `0x18001b277`
- `ADVAPI32!GetTokenInformation` at `0x18001b2ce`
- `ADVAPI32!GetTokenInformation` at `0x18001b395`
- `ADVAPI32!GetTokenInformation` at `0x18001b2ce`
- `ADVAPI32!GetTokenInformation` at `0x18001b395`
- `ADVAPI32!IsValidSid` at `0x18001b3a2`
- `ADVAPI32!IsValidSid` at `0x18001b3a2`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x18001b3b3`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x18001b3b3`
- `ADVAPI32!GetSidSubAuthority` at `0x18001b3ca`
- `ADVAPI32!GetSidSubAuthority` at `0x18001b3ca`

## string_xrefs

- `0x18001b471`: `Failed to get token's integrity level information`
- `0x18001b4ab`: `Cannot open process token`
- `0x18001b526`: `GetSidSubAuthority failed for a valid sid`
- `0x18001b4d4`: `GetTokenInformation returned an invalid sid : IsValidSid failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 OSecurity::GetCurrentProcessIntegrityLevel(void)
{
  DWORD v0; // edi
  HANDLE CurrentProcess; // rax
  bool v2; // r8
  DWORD v3; // eax
  DWORD v4; // r9d
  DWORD v5; // esi
  void *v6; // rbx
  PSID *v7; // rbx
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax
  HANDLE v10; // rcx
  DWORD LastError; // eax
  DWORD v13; // eax
  __int64 v14; // rdx
  DWORD v15; // eax
  DWORD TokenInformationLength[2]; // [rsp+38h] [rbp-D0h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE TokenHandle_8[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-B0h]
  void **v20; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+68h] [rbp-A0h]
  HANDLE hObject; // [rsp+70h] [rbp-98h]
  char v23; // [rsp+78h] [rbp-90h]
  int v24; // [rsp+7Ch] [rbp-8Ch]
  _BYTE pExceptionObject[912]; // [rsp+88h] [rbp-80h] BYREF

  TokenHandle = 0;
  TokenInformationLength[0] = 0;
  v0 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
    OException::OException(pExceptionObject, 15, LastError, L"Cannot open process token");
    throw (OException *)pExceptionObject;
  }
  LODWORD(v21) = 0;
  v20 = &OHandle::`vftable';
  hObject = 0;
  v23 = 0;
  v24 = 85;
  OHandle::SetHandle((OHandle *)&v20, TokenHandle, v2);
  if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, TokenInformationLength) )
  {
    v3 = GetLastError();
    if ( v3 != 122 )
    {
      OException::OException(pExceptionObject, 15, v3, L"Failed to get token's integrity level information");
      throw (OException *)pExceptionObject;
    }
    v4 = TokenInformationLength[0];
    v5 = TokenInformationLength[0];
    *(_OWORD *)TokenHandle_8 = 0;
    v19 = 0;
    if ( TokenInformationLength[0] )
    {
      _mm_lfence();
      v6 = std::_Allocate<16,std::_Default_allocate_traits>(TokenInformationLength[0]);
      memset(v6, 0, v5);
      memmove(v6, TokenHandle_8[0], (char *)TokenHandle_8[1] - (char *)TokenHandle_8[0]);
      std::vector<unsigned char>::_Change_array(TokenHandle_8, v6, v5, v5);
      v4 = TokenInformationLength[0];
    }
    v7 = (PSID *)TokenHandle_8[0];
    if ( TokenHandle_8[1] == TokenHandle_8[0] )
    {
      v7 = 0;
    }
    else if ( TokenHandle_8[1] == TokenHandle_8[0] )
    {
      _invoke_watson(0, 0, 0, 0, 0);
    }
    if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v7, v4, TokenInformationLength) )
    {
      if ( !IsValidSid(*v7) )
      {
        OException::OException(pExceptionObject, 88, L"GetTokenInformation returned an invalid sid : IsValidSid failed");
        throw (OException *)pExceptionObject;
      }
      SidSubAuthorityCount = GetSidSubAuthorityCount(*v7);
      if ( !SidSubAuthorityCount )
      {
        v13 = GetLastError();
        OException::OException(pExceptionObject, v14, v13);
        throw (OException *)pExceptionObject;
      }
      SidSubAuthority = GetSidSubAuthority(*v7, (unsigned int)*SidSubAuthorityCount - 1);
      if ( !SidSubAuthority )
      {
        v15 = GetLastError();
        OException::OException(pExceptionObject, 15, v15, L"GetSidSubAuthority failed for a valid sid");
        throw (OException *)pExceptionObject;
      }
      v0 = *SidSubAuthority;
    }
    v10 = TokenHandle_8[0];
    if ( TokenHandle_8[0] )
    {
      if ( v19 - (unsigned __int64)TokenHandle_8[0] >= 0x1000 )
      {
        _mm_lfence();
        v10 = (HANDLE)*((_QWORD *)TokenHandle_8[0] - 1);
        if ( (unsigned __int64)((char *)TokenHandle_8[0] - (char *)v10 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v10);
    }
  }
  if ( hObject && v23 )
    CloseHandle(hObject);
  return v0;
}

```

## disassembly

```asm
0x18001b224  mov     rax, rsp
0x18001b227  mov     [rax+8], rbx
0x18001b22b  mov     [rax+10h], rsi
0x18001b22f  mov     [rax+18h], rdi
0x18001b233  push    rbp
0x18001b234  lea     rbp, [rax-328h]
0x18001b23b  sub     rsp, 420h
0x18001b242  mov     rax, cs:__security_cookie
0x18001b249  xor     rax, rsp
0x18001b24c  mov     [rbp+320h+var_10], rax
0x18001b253  mov     [rsp+420h+TokenHandle], 0
0x18001b25c  mov     [rsp+420h+TokenInformationLength], 0
0x18001b264  xor     edi, edi
0x18001b266  call    cs:__imp_GetCurrentProcess
0x18001b26c  mov     rcx, rax; ProcessHandle
0x18001b26f  lea     r8, [rsp+420h+TokenHandle]; TokenHandle
0x18001b274  lea     edx, [rdi+8]; DesiredAccess
0x18001b277  call    cs:__imp_OpenProcessToken
0x18001b27d  test    eax, eax
0x18001b27f  jz      loc_18001B4A2
0x18001b285  mov     dword ptr [rsp+420h+var_3C0], edi
0x18001b289  lea     rax, ??_7OHandle@@6B@; const OHandle::`vftable'
0x18001b290  mov     [rsp+420h+var_3C8], rax
0x18001b295  mov     [rsp+420h+hObject], rdi
0x18001b29a  mov     [rsp+420h+var_3B0], dil
0x18001b29f  mov     [rsp+420h+var_3AC], 55h ; 'U'
0x18001b2a7  mov     rdx, [rsp+420h+TokenHandle]; void *
0x18001b2ac  lea     rcx, [rsp+420h+var_3C8]; this
0x18001b2b1  call    ?SetHandle@OHandle@@QEAAXPEAX_N@Z; OHandle::SetHandle(void *,bool)
0x18001b2b6  lea     rax, [rsp+420h+TokenInformationLength]
0x18001b2bb  mov     [rsp+420h+ReturnLength], rax; ReturnLength
0x18001b2c0  xor     r9d, r9d; TokenInformationLength
0x18001b2c3  xor     r8d, r8d; TokenInformation
0x18001b2c6  lea     edx, [rdi+19h]; TokenInformationClass
0x18001b2c9  mov     rcx, [rsp+420h+TokenHandle]; TokenHandle
0x18001b2ce  call    cs:__imp_GetTokenInformation
0x18001b2d4  test    eax, eax
0x18001b2d6  jnz     loc_18001B415
0x18001b2dc  call    cs:__imp_GetLastError
0x18001b2e2  cmp     eax, 7Ah ; 'z'
0x18001b2e5  jnz     loc_18001B471
0x18001b2eb  mov     r9d, [rsp+420h+TokenInformationLength]
0x18001b2f0  mov     esi, r9d
0x18001b2f3  xorps   xmm0, xmm0
0x18001b2f6  movdqu  xmmword ptr [rsp+420h+TokenHandle+8], xmm0
0x18001b2fc  mov     [rsp+420h+var_3D0], rdi
0x18001b301  test    r9d, r9d
0x18001b304  jz      short loc_18001B34E
0x18001b306  lfence
0x18001b309  mov     ecx, r9d
0x18001b30c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001b311  mov     rbx, rax
0x18001b314  mov     r8d, esi; Size
0x18001b317  xor     edx, edx; Val
0x18001b319  mov     rcx, rax; void *
0x18001b31c  call    memset
0x18001b321  mov     r8, [rsp+420h+var_3D8]
0x18001b326  mov     rdx, [rsp+420h+TokenHandle+8]; Src
0x18001b32b  sub     r8, rdx; Size
0x18001b32e  mov     rcx, rbx; void *
0x18001b331  call    memmove
0x18001b336  mov     r9d, esi
0x18001b339  mov     r8d, esi
0x18001b33c  mov     rdx, rbx
0x18001b33f  lea     rcx, [rsp+420h+TokenHandle+8]
0x18001b344  call    ?_Change_array@?$vector@EV?$allocator@E@std@@@std@@AEAAXQEAE_K1@Z; std::vector<uchar>::_Change_array(uchar * const,unsigned __int64,unsigned __int64)
0x18001b349  mov     r9d, [rsp+420h+TokenInformationLength]; TokenInformationLength
0x18001b34e  mov     rax, [rsp+420h+var_3D8]
0x18001b353  mov     rbx, [rsp+420h+TokenHandle+8]
0x18001b358  sub     rax, rbx
0x18001b35b  jz      short loc_18001B37C
0x18001b35d  test    rax, rax
0x18001b360  jnz     loc_18001B49D
0x18001b366  mov     [rsp+420h+ReturnLength], rax; Reserved
0x18001b36b  xor     r9d, r9d; LineNo
0x18001b36e  xor     r8d, r8d; FileName
0x18001b371  xor     edx, edx; FunctionName
0x18001b373  xor     ecx, ecx; Expression
0x18001b375  call    cs:__imp__invoke_watson
0x18001b37c  xor     ebx, ebx
0x18001b37e  lea     rax, [rsp+420h+TokenInformationLength]
0x18001b383  mov     [rsp+420h+ReturnLength], rax; ReturnLength
0x18001b388  mov     r8, rbx; TokenInformation
0x18001b38b  mov     edx, 19h; TokenInformationClass
0x18001b390  mov     rcx, [rsp+420h+TokenHandle]; TokenHandle
0x18001b395  call    cs:__imp_GetTokenInformation
0x18001b39b  test    eax, eax
0x18001b39d  jz      short loc_18001B3DB
0x18001b39f  mov     rcx, [rbx]; pSid
0x18001b3a2  call    cs:__imp_IsValidSid
0x18001b3a8  test    eax, eax
0x18001b3aa  jz      loc_18001B4D4
0x18001b3b0  mov     rcx, [rbx]; pSid
0x18001b3b3  call    cs:__imp_GetSidSubAuthorityCount
0x18001b3b9  test    rax, rax
0x18001b3bc  jz      loc_18001B4FA
0x18001b3c2  movzx   edx, byte ptr [rax]
0x18001b3c5  dec     edx; nSubAuthority
0x18001b3c7  mov     rcx, [rbx]; pSid
0x18001b3ca  call    cs:__imp_GetSidSubAuthority
0x18001b3d0  test    rax, rax
0x18001b3d3  jz      loc_18001B51D
0x18001b3d9  mov     edi, [rax]
0x18001b3db  mov     rcx, [rsp+420h+TokenHandle+8]
0x18001b3e0  test    rcx, rcx
0x18001b3e3  jz      short loc_18001B415
0x18001b3e5  mov     rax, [rsp+420h+var_3D0]
0x18001b3ea  sub     rax, rcx
0x18001b3ed  cmp     rax, 1000h
0x18001b3f3  jb      short loc_18001B40E
0x18001b3f5  lfence
0x18001b3f8  mov     rax, [rsp+420h+TokenHandle+8]
0x18001b3fd  mov     rcx, [rax-8]; Block
0x18001b401  sub     rax, rcx
0x18001b404  add     rax, 0FFFFFFFFFFFFFFF8h
0x18001b408  cmp     rax, 1Fh
0x18001b40c  ja      short loc_18001B457
0x18001b40e  call    cs:__imp_free
0x18001b414  nop
0x18001b415  mov     rcx, [rsp+420h+hObject]; hObject
0x18001b41a  test    rcx, rcx
0x18001b41d  jz      short loc_18001B42D
0x18001b41f  cmp     [rsp+420h+var_3B0], 0
0x18001b424  jz      short loc_18001B42D
0x18001b426  call    cs:__imp_CloseHandle
0x18001b42c  nop
0x18001b42d  mov     eax, edi
0x18001b42f  mov     rcx, [rbp+320h+var_10]
0x18001b436  xor     rcx, rsp; StackCookie
0x18001b439  call    __security_check_cookie
0x18001b43e  lea     r11, [rsp+420h+var_s0]
0x18001b446  mov     rbx, [r11+10h]
0x18001b44a  mov     rsi, [r11+18h]
0x18001b44e  mov     rdi, [r11+20h]
0x18001b452  mov     rsp, r11
0x18001b455  pop     rbp
0x18001b456  retn
0x18001b457  mov     [rsp+420h+ReturnLength], 0; Reserved
0x18001b460  xor     r9d, r9d; LineNo
0x18001b463  xor     r8d, r8d; FileName
0x18001b466  xor     edx, edx; FunctionName
0x18001b468  xor     ecx, ecx; Expression
0x18001b46a  call    cs:__imp__invoke_watson
0x18001b471  lea     r9, aFailedToGetTok; "Failed to get token's integrity level i"...
0x18001b478  mov     r8d, eax
0x18001b47b  mov     edx, 0Fh
0x18001b480  lea     rcx, [rbp+320h+pExceptionObject]
0x18001b484  call    ??$?0$0DC@@OException@@QEAA@W4exceptionType@et@@IAEAY0DC@$$CB_W@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[50])
0x18001b489  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18001b490  lea     rcx, [rbp+320h+pExceptionObject]; pExceptionObject
0x18001b494  call    _CxxThrowException
0x18001b49a  jmp     short $+2
0x18001b49c  nop
0x18001b49d  jmp     loc_18001B37E
0x18001b4a2  call    cs:__imp_GetLastError
0x18001b4a8  mov     r8d, eax
0x18001b4ab  lea     r9, aCannotOpenProc; "Cannot open process token"
0x18001b4b2  mov     edx, 0Fh
0x18001b4b7  lea     rcx, [rbp+320h+pExceptionObject]
0x18001b4bb  call    ??$?0$0BK@@OException@@QEAA@W4exceptionType@et@@IAEAY0BK@$$CB_W@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[26])
0x18001b4c0  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18001b4c7  lea     rcx, [rbp+320h+pExceptionObject]; pExceptionObject
0x18001b4cb  call    _CxxThrowException
0x18001b4d1  jmp     short $+2
0x18001b4d3  nop
0x18001b4d4  lea     r8, aGettokeninform_0; "GetTokenInformation returned an invalid"...
0x18001b4db  mov     edx, 58h ; 'X'
0x18001b4e0  lea     rcx, [rbp+320h+pExceptionObject]
0x18001b4e4  call    ??$?0$0EA@@OException@@QEAA@W4exceptionType@et@@AEAY0EA@$$CB_W@Z; OException::OException(et::exceptionType,wchar_t const (&)[64])
0x18001b4e9  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18001b4f0  lea     rcx, [rbp+320h+pExceptionObject]; pExceptionObject
0x18001b4f4  call    _CxxThrowException
0x18001b4fa  call    cs:__imp_GetLastError
0x18001b500  mov     r8d, eax
0x18001b503  lea     rcx, [rbp+320h+pExceptionObject]
0x18001b507  call    ??$?0$0CP@@OException@@QEAA@W4exceptionType@et@@IAEAY0CP@$$CB_W@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[47])
0x18001b50c  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18001b513  lea     rcx, [rbp+320h+pExceptionObject]; pExceptionObject
0x18001b517  call    _CxxThrowException
0x18001b51d  call    cs:__imp_GetLastError
0x18001b523  mov     r8d, eax
0x18001b526  lea     r9, aGetsidsubautho_1; "GetSidSubAuthority failed for a valid s"...
0x18001b52d  mov     edx, 0Fh
0x18001b532  lea     rcx, [rbp+320h+pExceptionObject]
0x18001b536  call    ??$?0$0CK@@OException@@QEAA@W4exceptionType@et@@IAEAY0CK@$$CB_W@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[42])
0x18001b53b  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18001b542  lea     rcx, [rbp+320h+pExceptionObject]; pExceptionObject
0x18001b546  call    _CxxThrowException
```
