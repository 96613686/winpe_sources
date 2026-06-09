# CflApi::CanProcessCleanupTempUserAccountProfile

- ea: `0x18001bcfc`
- end: `0x18001bf5a`
- name: `CflApi::CanProcessCleanupTempUserAccountProfile`
- size: `606`
- prototype: `__int64 __fastcall(_BYTE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001c500`

## callees

- `0x180002ef8`
- `0x1800067a4`
- `0x1800067c4`
- `0x180016350`
- `0x18001aa1c`
- `0x18001b0bc`
- `0x18001bcfc`
- `0x180021420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bde4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bde4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001bd61`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001bd61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bd4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001bd4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bd90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf3f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001bd23`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001bd23`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bdbb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001be75`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001bdbb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001be75`

## string_xrefs

- `0x18001bd31`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001bd6f`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001bdcf`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001be83`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001bd1a`: `SeTakeOwnershipPrivilege`

## pseudocode

```c
__int64 __fastcall CflApi::CanProcessCleanupTempUserAccountProfile(_BYTE *a1)
{
  const char *v2; // r9
  HANDLE CurrentProcess; // rax
  const char *v5; // r9
  unsigned int LastError; // ebx
  __int64 v7; // rdx
  signed int v8; // eax
  DWORD v9; // r9d
  __int64 v10; // rdi
  char *v11; // rbx
  const char *v12; // r9
  char *v13; // rdi
  char *v14; // rax
  size_t v15; // rbx
  __int64 v16; // rcx
  int ReturnLength; // [rsp+20h] [rbp-30h]
  __int64 v18; // [rsp+30h] [rbp-20h] BYREF
  void *TokenInformation[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v20; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD TokenInformationLength; // [rsp+78h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+30h] BYREF
  _LUID Luid; // [rsp+88h] [rbp+38h] BYREF

  Luid = 0;
  if ( !LookupPrivilegeValueW(0, L"SeTakeOwnershipPrivilege", &Luid) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x3A5,
             (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
             v2);
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3A8,
                  (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
                  v5);
LABEL_5:
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return LastError;
  }
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength) )
  {
    LastError = -2147418113;
    v7 = 945;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)LastError,
      ReturnLength);
    goto LABEL_5;
  }
  v8 = GetLastError();
  LastError = v8;
  if ( v8 != 122 )
  {
    if ( v8 > 0 )
      LastError = (unsigned __int16)v8 | 0x80070000;
    if ( (LastError & 0x80000000) == 0 )
      goto LABEL_5;
    v7 = 947;
    goto LABEL_10;
  }
  v9 = TokenInformationLength;
  v10 = TokenInformationLength;
  *(_OWORD *)TokenInformation = 0;
  v20 = 0;
  if ( TokenInformationLength )
  {
    std::vector<unsigned char>::_Buy_nonzero(TokenInformation, TokenInformationLength);
    v11 = (char *)TokenInformation[0];
    memset_0(TokenInformation[0], 0, (unsigned int)v10);
    TokenInformation[1] = &v11[v10];
    v18 = 0;
    std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v18);
    v9 = TokenInformationLength;
  }
  if ( !GetTokenInformation(TokenHandle, TokenPrivileges, TokenInformation[0], v9, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3BC,
                  (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
                  v12);
    std::vector<char>::~vector<char>(TokenInformation);
    goto LABEL_5;
  }
  v13 = (char *)TokenInformation[1];
  if ( (void *)TokenInformationLength < (void *)((char *)TokenInformation[1] - (char *)TokenInformation[0]) )
  {
    v14 = (char *)TokenInformation[0] + TokenInformationLength;
LABEL_26:
    TokenInformation[1] = v14;
    goto LABEL_27;
  }
  if ( (void *)TokenInformationLength > (void *)((char *)TokenInformation[1] - (char *)TokenInformation[0]) )
  {
    if ( TokenInformationLength <= v20 - (unsigned __int64)TokenInformation[0] )
    {
      v15 = TokenInformationLength - (unsigned __int64)((char *)TokenInformation[1] - (char *)TokenInformation[0]);
      memset_0(TokenInformation[1], 0, v15);
      v14 = &v13[v15];
      goto LABEL_26;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(TokenInformation, TokenInformationLength);
  }
LABEL_27:
  v16 = 0;
  if ( *(_DWORD *)TokenInformation[0] )
  {
    while ( *((_DWORD *)TokenInformation[0] + 3 * v16 + 1) != Luid.LowPart
         || *((_DWORD *)TokenInformation[0] + 3 * v16 + 2) != Luid.HighPart )
    {
      if ( ++v16 >= (unsigned __int64)*(unsigned int *)TokenInformation[0] )
        goto LABEL_31;
    }
    *a1 = 1;
  }
  else
  {
LABEL_31:
    *a1 = 0;
  }
  std::vector<char>::~vector<char>(TokenInformation);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x18001bcfc  mov     [rsp-18h+arg_0], rbx
0x18001bd01  push    rbp
0x18001bd02  push    rsi
0x18001bd03  push    rdi
0x18001bd04  mov     rbp, rsp
0x18001bd07  sub     rsp, 50h
0x18001bd0b  mov     rsi, rcx
0x18001bd0e  mov     qword ptr [rbp+Luid.LowPart], 0
0x18001bd16  lea     r8, [rbp+Luid]; lpLuid
0x18001bd1a  lea     rdx, Name; "SeTakeOwnershipPrivilege"
0x18001bd21  xor     ecx, ecx; lpSystemName
0x18001bd23  call    cs:__imp_LookupPrivilegeValueW
0x18001bd29  test    eax, eax
0x18001bd2b  jnz     short loc_18001BD47
0x18001bd2d  mov     rcx, [rbp+18h]; this
0x18001bd31  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001bd38  mov     edx, 3A5h; void *
0x18001bd3d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bd42  jmp     loc_18001BF47
0x18001bd47  mov     [rbp+TokenHandle], 0
0x18001bd4f  call    cs:__imp_GetCurrentProcess
0x18001bd55  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001bd59  mov     edx, 8; DesiredAccess
0x18001bd5e  mov     rcx, rax; ProcessHandle
0x18001bd61  call    cs:__imp_OpenProcessToken
0x18001bd67  test    eax, eax
0x18001bd69  jnz     short loc_18001BD9D
0x18001bd6b  mov     rcx, [rbp+18h]; this
0x18001bd6f  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001bd76  mov     edx, 3A8h; void *
0x18001bd7b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bd80  mov     ebx, eax
0x18001bd82  mov     rcx, [rbp+TokenHandle]; hObject
0x18001bd86  lea     rdx, [rcx-1]
0x18001bd8a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001bd8e  ja      short loc_18001BD96
0x18001bd90  call    cs:__imp_CloseHandle
0x18001bd96  mov     eax, ebx
0x18001bd98  jmp     loc_18001BF47
0x18001bd9d  mov     [rbp+TokenInformationLength], 0
0x18001bda4  lea     rax, [rbp+TokenInformationLength]
0x18001bda8  mov     qword ptr [rsp+50h+ReturnLength], rax; int
0x18001bdad  xor     r9d, r9d; TokenInformationLength
0x18001bdb0  xor     r8d, r8d; TokenInformation
0x18001bdb3  lea     edx, [r9+3]; TokenInformationClass
0x18001bdb7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001bdbb  call    cs:__imp_GetTokenInformation
0x18001bdc1  test    eax, eax
0x18001bdc3  jz      short loc_18001BDE4
0x18001bdc5  mov     ebx, 8000FFFFh
0x18001bdca  mov     edx, 3B1h; void *
0x18001bdcf  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001bdd6  mov     r9d, ebx; char *
0x18001bdd9  mov     rcx, [rbp+18h]; this
0x18001bddd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bde2  jmp     short loc_18001BD82
0x18001bde4  call    cs:__imp_GetLastError
0x18001bdea  mov     ebx, eax
0x18001bdec  cmp     eax, 7Ah ; 'z'
0x18001bdef  jz      short loc_18001BE09
0x18001bdf1  test    eax, eax
0x18001bdf3  jle     short loc_18001BDFE
0x18001bdf5  movzx   ebx, ax
0x18001bdf8  or      ebx, 80070000h
0x18001bdfe  test    ebx, ebx
0x18001be00  jns     short loc_18001BD82
0x18001be02  mov     edx, 3B3h
0x18001be07  jmp     short loc_18001BDCF
0x18001be09  mov     r9d, [rbp+TokenInformationLength]
0x18001be0d  mov     edi, r9d
0x18001be10  xorps   xmm0, xmm0
0x18001be13  movdqu  xmmword ptr [rbp+TokenInformation], xmm0
0x18001be18  mov     [rbp+var_8], 0
0x18001be20  test    r9d, r9d
0x18001be23  jz      short loc_18001BE5F
0x18001be25  mov     edx, r9d
0x18001be28  lea     rcx, [rbp+TokenInformation]
0x18001be2c  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x18001be31  mov     rbx, [rbp+TokenInformation]
0x18001be35  mov     r8d, edi; Size
0x18001be38  xor     edx, edx; Val
0x18001be3a  mov     rcx, rbx; void *
0x18001be3d  call    memset_0
0x18001be42  lea     rax, [rdi+rbx]
0x18001be46  mov     [rbp+TokenInformation+8], rax
0x18001be4a  mov     [rbp+var_20], 0
0x18001be52  lea     rcx, [rbp+var_20]
0x18001be56  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18001be5b  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001be5f  lea     rax, [rbp+TokenInformationLength]
0x18001be63  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x18001be68  mov     r8, [rbp+TokenInformation]; TokenInformation
0x18001be6c  mov     edx, 3; TokenInformationClass
0x18001be71  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001be75  call    cs:__imp_GetTokenInformation
0x18001be7b  test    eax, eax
0x18001be7d  jnz     short loc_18001BEA4
0x18001be7f  mov     rcx, [rbp+18h]; this
0x18001be83  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001be8a  mov     edx, 3BCh; void *
0x18001be8f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001be94  mov     ebx, eax
0x18001be96  lea     rcx, [rbp+TokenInformation]
0x18001be9a  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001be9f  jmp     loc_18001BD82
0x18001bea4  mov     ebx, [rbp+TokenInformationLength]
0x18001bea7  mov     rdx, [rbp+TokenInformation]
0x18001beab  mov     rdi, [rbp+TokenInformation+8]
0x18001beaf  mov     rcx, rdi
0x18001beb2  sub     rcx, rdx
0x18001beb5  cmp     rbx, rcx
0x18001beb8  jnb     short loc_18001BEC0
0x18001beba  lea     rax, [rbx+rdx]
0x18001bebe  jmp     short loc_18001BEF0
0x18001bec0  jbe     short loc_18001BEF4
0x18001bec2  mov     rax, [rbp+var_8]
0x18001bec6  sub     rax, rdx
0x18001bec9  cmp     rbx, rax
0x18001becc  jbe     short loc_18001BEDC
0x18001bece  mov     rdx, rbx
0x18001bed1  lea     rcx, [rbp+TokenInformation]
0x18001bed5  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001beda  jmp     short loc_18001BEF4
0x18001bedc  sub     rbx, rcx
0x18001bedf  mov     r8, rbx; Size
0x18001bee2  xor     edx, edx; Val
0x18001bee4  mov     rcx, rdi; void *
0x18001bee7  call    memset_0
0x18001beec  lea     rax, [rbx+rdi]
0x18001bef0  mov     [rbp+TokenInformation+8], rax
0x18001bef4  mov     rdx, [rbp+TokenInformation]
0x18001bef8  xor     ecx, ecx
0x18001befa  mov     r8d, [rdx]
0x18001befd  test    r8, r8
0x18001bf00  jz      short loc_18001BF24
0x18001bf02  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18001bf06  mov     r10d, [rbp+Luid.HighPart]
0x18001bf0a  lea     r9, [rcx+rcx*2]
0x18001bf0e  cmp     [rdx+r9*4+4], eax
0x18001bf13  jnz     short loc_18001BF1C
0x18001bf15  cmp     [rdx+r9*4+8], r10d
0x18001bf1a  jz      short loc_18001BF54
0x18001bf1c  inc     rcx
0x18001bf1f  cmp     rcx, r8
0x18001bf22  jb      short loc_18001BF0A
0x18001bf24  mov     byte ptr [rsi], 0
0x18001bf27  lea     rcx, [rbp+TokenInformation]
0x18001bf2b  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001bf30  nop
0x18001bf31  mov     rcx, [rbp+TokenHandle]; hObject
0x18001bf35  lea     rax, [rcx-1]
0x18001bf39  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001bf3d  ja      short loc_18001BF45
0x18001bf3f  call    cs:__imp_CloseHandle
0x18001bf45  xor     eax, eax
0x18001bf47  mov     rbx, [rsp+50h+arg_0]
0x18001bf4c  add     rsp, 50h
0x18001bf50  pop     rdi
0x18001bf51  pop     rsi
0x18001bf52  pop     rbp
0x18001bf53  retn
0x18001bf54  mov     byte ptr [rsi], 1
0x18001bf57  jmp     short loc_18001BF27
```
