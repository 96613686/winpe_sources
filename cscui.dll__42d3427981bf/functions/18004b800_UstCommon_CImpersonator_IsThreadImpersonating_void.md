# UstCommon::CImpersonator::_IsThreadImpersonating(void)

- ea: `0x18004b800`
- end: `0x18004b936`
- name: `?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ`
- size: `310`
- prototype: `bool __fastcall(UstCommon::CImpersonator *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002950`

## callees

- `0x18001101c`
- `0x180013d9c`
- `0x18004ada0`
- `0x18004b800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b89f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b89f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b8be`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004b870`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004b870`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004b81a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004b81a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004b831`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004b831`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall UstCommon::CImpersonator::_IsThreadImpersonating(UstCommon::CImpersonator *this)
{
  bool v1; // bl
  HANDLE CurrentThread; // rax
  BOOL v3; // eax
  UstCommon::CImpersonator *v4; // rcx
  DWORD LastError; // eax
  __int64 v6; // rdx
  const wchar_t *v7; // r9
  UstCommon::CImpersonator *TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = this;
  v1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
      goto LABEL_16;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_11;
    LastError = GetLastError();
    v6 = 15;
    goto LABEL_10;
  }
  LODWORD(TokenInformation) = 0;
  ReturnLength = 0;
  v3 = GetTokenInformation(TokenHandle, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength);
  v4 = WPP_GLOBAL_Control;
  if ( v3 )
  {
    v1 = (unsigned int)((_DWORD)TokenInformation - 2) <= 1;
    goto LABEL_11;
  }
  if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
    goto LABEL_16;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    v6 = 14;
LABEL_10:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids, LastError);
    v4 = WPP_GLOBAL_Control;
  }
LABEL_11:
  if ( v4 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
  {
    v7 = L"YES";
    if ( !v1 )
      v7 = L"NO";
    WPP_SF_S(*((_QWORD *)v4 + 2), 16, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids, v7);
  }
LABEL_16:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x18004b800  mov     [rsp+arg_18], rbx
0x18004b805  mov     [rsp+TokenInformation], rcx
0x18004b80a  push    rbp
0x18004b80b  sub     rsp, 30h
0x18004b80f  xor     bl, bl
0x18004b811  mov     [rsp+38h+TokenHandle], 0
0x18004b81a  call    cs:__imp_GetCurrentThread
0x18004b820  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18004b825  mov     edx, 8; DesiredAccess
0x18004b82a  lea     r8d, [rdx-7]; OpenAsSelf
0x18004b82e  mov     rcx, rax; ThreadHandle
0x18004b831  call    cs:__imp_OpenThreadToken
0x18004b837  lea     rbp, WPP_GLOBAL_Control
0x18004b83e  test    eax, eax
0x18004b840  jz      short loc_18004B8AC
0x18004b842  mov     dword ptr [rsp+38h+TokenInformation], 0
0x18004b84a  mov     [rsp+38h+arg_8], 0
0x18004b852  lea     rax, [rsp+38h+arg_8]
0x18004b857  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18004b85c  mov     r9d, 4; TokenInformationLength
0x18004b862  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18004b867  lea     edx, [r9+5]; TokenInformationClass
0x18004b86b  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18004b870  call    cs:__imp_GetTokenInformation
0x18004b876  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b87d  test    eax, eax
0x18004b87f  jz      short loc_18004B890
0x18004b881  mov     eax, dword ptr [rsp+38h+TokenInformation]
0x18004b885  add     eax, 0FFFFFFFEh
0x18004b888  cmp     eax, 1
0x18004b88b  setbe   bl
0x18004b88e  jmp     short loc_18004B8EA
0x18004b890  cmp     rcx, rbp
0x18004b893  jz      loc_18004B91F
0x18004b899  test    byte ptr [rcx+1Ch], 2
0x18004b89d  jz      short loc_18004B8EA
0x18004b89f  call    cs:__imp_GetLastError
0x18004b8a5  mov     edx, 0Eh
0x18004b8aa  jmp     short loc_18004B8C9
0x18004b8ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b8b3  cmp     rcx, rbp
0x18004b8b6  jz      short loc_18004B91F
0x18004b8b8  test    byte ptr [rcx+1Ch], 2
0x18004b8bc  jz      short loc_18004B8EA
0x18004b8be  call    cs:__imp_GetLastError
0x18004b8c4  mov     edx, 0Fh
0x18004b8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b8d0  mov     r9d, eax
0x18004b8d3  lea     r8, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids
0x18004b8da  mov     rcx, [rcx+10h]
0x18004b8de  call    WPP_SF_d
0x18004b8e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b8ea  cmp     rcx, rbp
0x18004b8ed  jz      short loc_18004B91F
0x18004b8ef  test    byte ptr [rcx+1Ch], 2
0x18004b8f3  jz      short loc_18004B91F
0x18004b8f5  lea     rax, aNo; "NO"
0x18004b8fc  lea     r9, aYes; "YES"
0x18004b903  test    bl, bl
0x18004b905  cmovz   r9, rax
0x18004b909  mov     edx, 10h
0x18004b90e  lea     r8, WPP_c06c96a323453971d4faaa040fed6bff_Traceguids
0x18004b915  mov     rcx, [rcx+10h]
0x18004b919  call    WPP_SF_S
0x18004b91e  nop
0x18004b91f  lea     rcx, [rsp+38h+TokenHandle]
0x18004b924  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004b929  mov     al, bl
0x18004b92b  mov     rbx, [rsp+38h+arg_18]
0x18004b930  add     rsp, 30h
0x18004b934  pop     rbp
0x18004b935  retn
```
