# GetCurrentSIDFromToken(void * *)

- ea: `0x180003608`
- end: `0x18000375d`
- name: `?GetCurrentSIDFromToken@@YAJPEAPEAX@Z`
- size: `341`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180003e90`

## callees

- `0x180001a94`
- `0x180001aa0`
- `0x180003608`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000373c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000373c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000368c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000368c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000362e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000362e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000363f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000363f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800036f3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800036f3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800036e2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800036e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003682`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800036d1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003682`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800036d1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000371b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000371b`

## pseudocode

```c
__int64 __fastcall GetCurrentSIDFromToken(void **a1)
{
  PSID *v2; // rsi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  DWORD LengthSid; // r14d
  void *v7; // rax
  void *v8; // rdi
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+18h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  v2 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle)
    && (GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() == 122) )
  {
    v2 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    v5 = -2147024882;
    if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
    {
      if ( IsValidSid(*v2) )
      {
        LengthSid = GetLengthSid(*v2);
        v7 = operator new[](LengthSid, (const struct std::nothrow_t *)&std::nothrow);
        v8 = v7;
        if ( !v7 )
          goto LABEL_12;
        if ( CopySid(LengthSid, v7, *v2) )
        {
          *a1 = v8;
          v5 = v2 != 0 ? 0 : 0x8007000E;
          goto LABEL_12;
        }
        operator delete(v8);
      }
    }
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  CloseHandle(TokenHandle);
  operator delete(v2);
  return v5;
}

```

## disassembly

```asm
0x180003608  mov     [rsp+arg_0], rbx
0x18000360d  push    rbp
0x18000360e  push    rsi
0x18000360f  push    rdi
0x180003610  push    r14
0x180003612  push    r15
0x180003614  sub     rsp, 30h
0x180003618  mov     r15, rcx
0x18000361b  mov     [rsp+58h+TokenHandle], 0
0x180003624  mov     [rsp+58h+TokenInformationLength], 0
0x18000362c  xor     esi, esi
0x18000362e  call    cs:__imp_GetCurrentProcess
0x180003634  mov     rcx, rax; ProcessHandle
0x180003637  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x18000363c  lea     edx, [rsi+8]; DesiredAccess
0x18000363f  call    cs:__imp_OpenProcessToken
0x180003645  test    eax, eax
0x180003647  jnz     short loc_180003667
0x180003649  call    cs:__imp_GetLastError
0x18000364f  mov     ebx, eax
0x180003651  test    eax, eax
0x180003653  jle     loc_180003737
0x180003659  movzx   ebx, ax
0x18000365c  or      ebx, 80070000h
0x180003662  jmp     loc_180003737
0x180003667  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000366c  lea     rax, [rsp+58h+TokenInformationLength]
0x180003671  xor     r9d, r9d; TokenInformationLength
0x180003674  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180003679  xor     r8d, r8d; TokenInformation
0x18000367c  lea     edi, [r9+1]
0x180003680  mov     edx, edi; TokenInformationClass
0x180003682  call    cs:__imp_GetTokenInformation
0x180003688  test    eax, eax
0x18000368a  jnz     short loc_180003697
0x18000368c  call    cs:__imp_GetLastError
0x180003692  cmp     eax, 7Ah ; 'z'
0x180003695  jnz     short loc_180003649
0x180003697  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x18000369b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800036a2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800036a7  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800036ac  mov     rsi, rax
0x1800036af  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1800036b4  neg     rax
0x1800036b7  lea     rax, [rsp+58h+TokenInformationLength]
0x1800036bc  mov     ebx, 8007000Eh
0x1800036c1  sbb     ebp, ebp
0x1800036c3  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800036c8  not     ebp
0x1800036ca  mov     r8, rsi; TokenInformation
0x1800036cd  mov     edx, edi; TokenInformationClass
0x1800036cf  and     ebp, ebx
0x1800036d1  call    cs:__imp_GetTokenInformation
0x1800036d7  test    eax, eax
0x1800036d9  jz      loc_180003649
0x1800036df  mov     rcx, [rsi]; pSid
0x1800036e2  call    cs:__imp_IsValidSid
0x1800036e8  test    eax, eax
0x1800036ea  jz      loc_180003649
0x1800036f0  mov     rcx, [rsi]; pSid
0x1800036f3  call    cs:__imp_GetLengthSid
0x1800036f9  mov     ecx, eax; unsigned __int64
0x1800036fb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003702  mov     r14d, eax
0x180003705  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000370a  mov     rdi, rax
0x18000370d  test    rax, rax
0x180003710  jz      short loc_180003737
0x180003712  mov     r8, [rsi]; pSourceSid
0x180003715  mov     rdx, rax; pDestinationSid
0x180003718  mov     ecx, r14d; nDestinationSidLength
0x18000371b  call    cs:__imp_CopySid
0x180003721  test    eax, eax
0x180003723  jnz     short loc_180003732
0x180003725  mov     rcx, rdi; Block
0x180003728  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000372d  jmp     loc_180003649
0x180003732  mov     [r15], rdi
0x180003735  mov     ebx, ebp
0x180003737  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000373c  call    cs:__imp_CloseHandle
0x180003742  mov     rcx, rsi; Block
0x180003745  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000374a  mov     eax, ebx
0x18000374c  mov     rbx, [rsp+58h+arg_0]
0x180003751  add     rsp, 30h
0x180003755  pop     r15
0x180003757  pop     r14
0x180003759  pop     rdi
0x18000375a  pop     rsi
0x18000375b  pop     rbp
0x18000375c  retn
```
