# IsDomainBackupRequired(void *)

- ea: `0x18000a830`
- end: `0x18000ab1f`
- name: `?IsDomainBackupRequired@@YAHPEAX@Z`
- size: `751`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a7a0`
- `0x180014c80`
- `0x180018a20`
- `0x18002a03c`

## callees

- `0x18000a830`
- `0x18001d810`
- `0x18003e010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a8bc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aa96`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a8bc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aa96`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000a98e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000a98e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a8dc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a8dc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000a914`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000a914`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a9ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a9ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a9af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a9af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa46`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000aae8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000aae8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000aacc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000aacc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a944`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aab5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a944`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aab5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a8f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa64`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a8f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab06`

## string_xrefs

- `0x18000a9a4`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall IsDomainBackupRequired(_QWORD *a1)
{
  unsigned int v1; // edi
  int v2; // ebp
  HANDLE v3; // rsi
  void *v4; // rbx
  HANDLE v5; // rcx
  HLOCAL v6; // r14
  PSID *v7; // r13
  DWORD LengthSid; // r12d
  HLOCAL v9; // rax
  void *v10; // r15
  PUCHAR SidSubAuthorityCount; // rax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  HANDLE CurrentThread; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-148h] BYREF
  int v17; // [rsp+34h] [rbp-144h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-140h] BYREF
  _BYTE TokenInformation[256]; // [rsp+40h] [rbp-138h] BYREF

  v1 = 0;
  v2 = 0;
  v3 = (HANDLE)a1[3];
  v4 = 0;
  TokenInformationLength = 0;
  TokenHandle = 0;
  if ( v3 )
  {
    v5 = v3;
    TokenHandle = v3;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      goto LABEL_9;
    v5 = TokenHandle;
  }
  TokenInformationLength = 256;
  v6 = 0;
  v7 = (PSID *)TokenInformation;
  if ( !GetTokenInformation(v5, TokenUser, TokenInformation, 0x100u, &TokenInformationLength) && GetLastError() == 122 )
  {
    v6 = LocalAlloc(0x40u, TokenInformationLength);
    if ( !v6 )
      goto LABEL_9;
    if ( !GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_8;
    v7 = (PSID *)v6;
  }
  LengthSid = GetLengthSid(*v7);
  v9 = LocalAlloc(0x40u, LengthSid);
  v10 = v9;
  if ( v9 )
  {
    if ( CopySid(LengthSid, v9, *v7) )
    {
      v4 = v10;
      v2 = 1;
    }
    else
    {
      LocalFree(v10);
    }
  }
  if ( v6 )
LABEL_8:
    LocalFree(v6);
LABEL_9:
  if ( TokenHandle && TokenHandle != v3 )
    CloseHandle(TokenHandle);
  if ( v2 )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(v4);
    if ( SidSubAuthorityCount )
    {
      if ( *SidSubAuthorityCount != 1 )
      {
        v17 = 0;
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        if ( ModuleHandleW
          && (ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetNtProductType")) != 0
          && ((unsigned __int8 (__fastcall *)(int *))ProcAddress)(&v17)
          && v17 == 2 )
        {
          v1 = 1;
        }
        else if ( (*((unsigned __int8 (__fastcall **)(void *))g_pDPAPILsasrvIfTable + 14))(v4) )
        {
          v1 = 1;
        }
      }
    }
  }
  if ( v4 )
    LocalFree(v4);
  return v1;
}

```

## disassembly

```asm
0x18000a830  mov     r11, rsp
0x18000a833  push    rbx
0x18000a834  push    rdi
0x18000a835  sub     rsp, 168h
0x18000a83c  mov     rax, cs:__security_cookie
0x18000a843  xor     rax, rsp
0x18000a846  mov     [rsp+178h+var_38], rax
0x18000a84e  mov     [r11+10h], rbp
0x18000a852  xor     edi, edi
0x18000a854  mov     [r11+18h], rsi
0x18000a858  xor     ebp, ebp
0x18000a85a  mov     rsi, [rcx+18h]
0x18000a85e  xor     ebx, ebx
0x18000a860  mov     [r11-28h], r15
0x18000a864  mov     r15d, 1
0x18000a86a  mov     [rsp+178h+TokenInformationLength], edi
0x18000a86e  mov     [rsp+178h+TokenHandle], rdi
0x18000a873  test    rsi, rsi
0x18000a876  jz      loc_18000AACC
0x18000a87c  mov     rcx, rsi; TokenHandle
0x18000a87f  mov     [rsp+178h+TokenHandle], rcx
0x18000a884  mov     [rsp+178h+var_18], r13
0x18000a88c  lea     rax, [rsp+178h+TokenInformationLength]
0x18000a891  mov     [rsp+178h+var_20], r14
0x18000a899  lea     r8, [rsp+178h+TokenInformation]; TokenInformation
0x18000a89e  mov     r9d, 100h; TokenInformationLength
0x18000a8a4  mov     [rsp+178h+ReturnLength], rax; ReturnLength
0x18000a8a9  mov     edx, r15d; TokenInformationClass
0x18000a8ac  mov     [rsp+178h+TokenInformationLength], 100h
0x18000a8b4  xor     r14d, r14d
0x18000a8b7  lea     r13, [rsp+178h+TokenInformation]
0x18000a8bc  call    cs:__imp_GetTokenInformation
0x18000a8c3  nop     dword ptr [rax+rax+00h]
0x18000a8c8  test    eax, eax
0x18000a8ca  jz      loc_18000AA46
0x18000a8d0  mov     rcx, [r13+0]; pSid
0x18000a8d4  mov     [rsp+178h+arg_18], r12
0x18000a8dc  call    cs:__imp_GetLengthSid
0x18000a8e3  nop     dword ptr [rax+rax+00h]
0x18000a8e8  mov     edx, eax; uBytes
0x18000a8ea  mov     ecx, 40h ; '@'; uFlags
0x18000a8ef  mov     r12d, eax
0x18000a8f2  call    cs:__imp_LocalAlloc
0x18000a8f9  nop     dword ptr [rax+rax+00h]
0x18000a8fe  mov     r15, rax
0x18000a901  test    rax, rax
0x18000a904  jz      loc_18000AAC1
0x18000a90a  mov     r8, [r13+0]; pSourceSid
0x18000a90e  mov     rdx, rax; pDestinationSid
0x18000a911  mov     ecx, r12d; nDestinationSidLength
0x18000a914  call    cs:__imp_CopySid
0x18000a91b  nop     dword ptr [rax+rax+00h]
0x18000a920  test    eax, eax
0x18000a922  jz      loc_18000AAB2
0x18000a928  mov     rbx, r15
0x18000a92b  mov     r15d, 1
0x18000a931  mov     ebp, r15d
0x18000a934  mov     r12, [rsp+178h+arg_18]
0x18000a93c  test    r14, r14
0x18000a93f  jz      short loc_18000A950
0x18000a941  mov     rcx, r14; hMem
0x18000a944  call    cs:__imp_LocalFree
0x18000a94b  nop     dword ptr [rax+rax+00h]
0x18000a950  mov     r13, [rsp+178h+var_18]
0x18000a958  mov     r14, [rsp+178h+var_20]
0x18000a960  mov     rcx, [rsp+178h+TokenHandle]; hObject
0x18000a965  test    rcx, rcx
0x18000a968  jz      short loc_18000A973
0x18000a96a  cmp     rcx, rsi
0x18000a96d  jnz     loc_18000AB06
0x18000a973  mov     rsi, [rsp+178h+arg_10]
0x18000a97b  test    ebp, ebp
0x18000a97d  mov     rbp, [rsp+178h+arg_8]
0x18000a985  jz      loc_18000AA0D
0x18000a98b  mov     rcx, rbx; pSid
0x18000a98e  call    cs:__imp_GetSidSubAuthorityCount
0x18000a995  nop     dword ptr [rax+rax+00h]
0x18000a99a  test    rax, rax
0x18000a99d  jz      short loc_18000AA0D
0x18000a99f  cmp     byte ptr [rax], 1
0x18000a9a2  jz      short loc_18000AA0D
0x18000a9a4  lea     rcx, ModuleName; "ntdll.dll"
0x18000a9ab  mov     [rsp+178h+var_144], edi
0x18000a9af  call    cs:__imp_GetModuleHandleW
0x18000a9b6  nop     dword ptr [rax+rax+00h]
0x18000a9bb  test    rax, rax
0x18000a9be  jz      short loc_18000A9F4
0x18000a9c0  lea     rdx, ProcName; "RtlGetNtProductType"
0x18000a9c7  mov     rcx, rax; hModule
0x18000a9ca  call    cs:__imp_GetProcAddress
0x18000a9d1  nop     dword ptr [rax+rax+00h]
0x18000a9d6  test    rax, rax
0x18000a9d9  jz      short loc_18000A9F4
0x18000a9db  lea     rcx, [rsp+178h+var_144]
0x18000a9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9e5  test    al, al
0x18000a9e7  jz      short loc_18000A9F4
0x18000a9e9  cmp     [rsp+178h+var_144], 2
0x18000a9ee  jz      loc_18000AB17
0x18000a9f4  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x18000a9fb  mov     rcx, rbx
0x18000a9fe  mov     rax, [rax+70h]
0x18000aa02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa07  test    al, al
0x18000aa09  cmovnz  edi, r15d
0x18000aa0d  mov     r15, [rsp+178h+var_28]
0x18000aa15  test    rbx, rbx
0x18000aa18  jz      short loc_18000AA29
0x18000aa1a  mov     rcx, rbx; hMem
0x18000aa1d  call    cs:__imp_LocalFree
0x18000aa24  nop     dword ptr [rax+rax+00h]
0x18000aa29  mov     eax, edi
0x18000aa2b  mov     rcx, [rsp+178h+var_38]
0x18000aa33  xor     rcx, rsp; StackCookie
0x18000aa36  call    __security_check_cookie
0x18000aa3b  add     rsp, 168h
0x18000aa42  pop     rdi
0x18000aa43  pop     rbx
0x18000aa44  retn
0x18000aa46  call    cs:__imp_GetLastError
0x18000aa4d  nop     dword ptr [rax+rax+00h]
0x18000aa52  cmp     eax, 7Ah ; 'z'
0x18000aa55  jnz     loc_18000A8D0
0x18000aa5b  mov     edx, [rsp+178h+TokenInformationLength]; uBytes
0x18000aa5f  mov     ecx, 40h ; '@'; uFlags
0x18000aa64  call    cs:__imp_LocalAlloc
0x18000aa6b  nop     dword ptr [rax+rax+00h]
0x18000aa70  mov     r14, rax
0x18000aa73  test    rax, rax
0x18000aa76  jz      loc_18000A950
0x18000aa7c  mov     r9d, [rsp+178h+TokenInformationLength]; TokenInformationLength
0x18000aa81  lea     rax, [rsp+178h+TokenInformationLength]
0x18000aa86  mov     rcx, [rsp+178h+TokenHandle]; TokenHandle
0x18000aa8b  mov     r8, r14; TokenInformation
0x18000aa8e  mov     edx, r15d; TokenInformationClass
0x18000aa91  mov     [rsp+178h+ReturnLength], rax; ReturnLength
0x18000aa96  call    cs:__imp_GetTokenInformation
0x18000aa9d  nop     dword ptr [rax+rax+00h]
0x18000aaa2  test    eax, eax
0x18000aaa4  jz      loc_18000A941
0x18000aaaa  mov     r13, r14
0x18000aaad  jmp     loc_18000A8D0
0x18000aab2  mov     rcx, r15; hMem
0x18000aab5  call    cs:__imp_LocalFree
0x18000aabc  nop     dword ptr [rax+rax+00h]
0x18000aac1  mov     r15d, 1
0x18000aac7  jmp     loc_18000A934
0x18000aacc  call    cs:__imp_GetCurrentThread
0x18000aad3  nop     dword ptr [rax+rax+00h]
0x18000aad8  lea     r9, [rsp+178h+TokenHandle]; TokenHandle
0x18000aadd  mov     r8d, r15d; OpenAsSelf
0x18000aae0  mov     rcx, rax; ThreadHandle
0x18000aae3  mov     edx, 8; DesiredAccess
0x18000aae8  call    cs:__imp_OpenThreadToken
0x18000aaef  nop     dword ptr [rax+rax+00h]
0x18000aaf4  test    eax, eax
0x18000aaf6  jz      loc_18000A960
0x18000aafc  mov     rcx, [rsp+178h+TokenHandle]
0x18000ab01  jmp     loc_18000A884
0x18000ab06  call    cs:__imp_CloseHandle
0x18000ab0d  nop     dword ptr [rax+rax+00h]
0x18000ab12  jmp     loc_18000A973
0x18000ab17  mov     edi, r15d
0x18000ab1a  jmp     loc_18000AA0D
```
