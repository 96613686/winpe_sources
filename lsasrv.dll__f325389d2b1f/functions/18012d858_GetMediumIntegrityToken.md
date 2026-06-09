# GetMediumIntegrityToken

- ea: `0x18012d858`
- end: `0x18012da2a`
- name: `GetMediumIntegrityToken`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180090c2c`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x18012d594`
- `0x18012d858`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012d8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012d910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012d986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012d9c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012d8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012d910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012d986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012d9c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012da0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012da0d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012d900`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012d976`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012d900`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012d976`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18012d8c4`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18012d8c4`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18012d9b9`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18012d9b9`

## pseudocode

```c
__int64 __fastcall GetMediumIntegrityToken(void *a1, HANDLE *a2)
{
  unsigned int v2; // ebx
  DWORD LastError; // eax
  DWORD v6; // esi
  __int64 v7; // rdi
  DWORD v8; // eax
  __int64 v9; // rdx
  void *v10; // rdx
  DWORD cbSid; // [rsp+50h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  TokenHandle = 0;
  cbSid = 0;
  v2 = -2146892963;
  if ( !a2 )
    return v2;
  *a2 = 0;
  v2 = a1 == 0 ? 0x8009035D : 0;
  if ( !a1 )
    return v2;
  if ( !DuplicateTokenEx(a1, 0x8Eu, 0, SecurityImpersonation, TokenImpersonation, &TokenHandle) )
  {
    LastError = GetLastError();
    return ConvertWin32StatusToSecStatus(LastError, 2148074248LL);
  }
  v6 = 0;
  if ( CreateWellKnownSid(WinMediumLabelSid, 0, 0, &cbSid) || (v6 = GetLastError(), v6 != 122) )
  {
    if ( !v6 )
    {
      v2 = -2146893008;
      goto LABEL_21;
    }
    v7 = 0;
    v2 = ConvertWin32StatusToSecStatus(v6, 2148074288LL);
  }
  else
  {
    v7 = LsapAllocate(cbSid + 16LL);
    if ( v7 )
      goto LABEL_13;
    v2 = -2146893056;
  }
  if ( (v2 & 0x80000000) == 0 )
  {
LABEL_13:
    if ( CreateWellKnownSid(WinMediumLabelSid, 0, (PSID)(v7 + 16), &cbSid) )
    {
      *(_DWORD *)(v7 + 8) = 96;
      *(_QWORD *)v7 = v7 + 16;
      if ( SetTokenInformation(TokenHandle, TokenIntegrityLevel, (LPVOID)v7, cbSid + 16) )
      {
        *a2 = TokenHandle;
        TokenHandle = 0;
LABEL_19:
        if ( v7 )
          LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v7, v10);
        goto LABEL_21;
      }
      v8 = GetLastError();
      v9 = 2148074248LL;
    }
    else
    {
      v8 = GetLastError();
      v9 = 2148074288LL;
    }
    v2 = ConvertWin32StatusToSecStatus(v8, v9);
    goto LABEL_19;
  }
LABEL_21:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v2;
}

```

## disassembly

```asm
0x18012d858  mov     r11, rsp
0x18012d85b  mov     [r11+18h], rbx
0x18012d85f  push    rsi
0x18012d860  push    rdi
0x18012d861  push    r14
0x18012d863  sub     rsp, 30h
0x18012d867  mov     rax, rcx
0x18012d86a  mov     qword ptr [r11+10h], 0
0x18012d872  neg     rax
0x18012d875  mov     [rsp+48h+cbSid], 0
0x18012d87d  mov     ebx, 8009035Dh
0x18012d882  mov     r14, rdx
0x18012d885  sbb     r8d, r8d
0x18012d888  not     r8d
0x18012d88b  and     r8d, ebx
0x18012d88e  test    rdx, rdx
0x18012d891  jz      loc_18012DA19
0x18012d897  mov     qword ptr [rdx], 0
0x18012d89e  mov     ebx, r8d
0x18012d8a1  test    rcx, rcx
0x18012d8a4  jz      loc_18012DA19
0x18012d8aa  lea     rax, [r11+10h]
0x18012d8ae  mov     r9d, 2; ImpersonationLevel
0x18012d8b4  mov     [r11-20h], rax
0x18012d8b8  xor     r8d, r8d; lpTokenAttributes
0x18012d8bb  mov     edx, 8Eh; dwDesiredAccess
0x18012d8c0  mov     [r11-28h], r9d
0x18012d8c4  call    cs:__imp_DuplicateTokenEx
0x18012d8cb  nop     dword ptr [rax+rax+00h]
0x18012d8d0  test    eax, eax
0x18012d8d2  jnz     short loc_18012D8F1
0x18012d8d4  call    cs:__imp_GetLastError
0x18012d8db  nop     dword ptr [rax+rax+00h]
0x18012d8e0  mov     ecx, eax
0x18012d8e2  mov     edx, 80090308h
0x18012d8e7  call    ConvertWin32StatusToSecStatus
0x18012d8ec  jmp     loc_18012DA1B
0x18012d8f1  xor     esi, esi
0x18012d8f3  lea     r9, [rsp+48h+cbSid]; cbSid
0x18012d8f8  xor     r8d, r8d; pSid
0x18012d8fb  xor     edx, edx; DomainSid
0x18012d8fd  lea     ecx, [rsi+43h]; WellKnownSidType
0x18012d900  call    cs:__imp_CreateWellKnownSid
0x18012d907  nop     dword ptr [rax+rax+00h]
0x18012d90c  test    eax, eax
0x18012d90e  jnz     short loc_18012D93F
0x18012d910  call    cs:__imp_GetLastError
0x18012d917  nop     dword ptr [rax+rax+00h]
0x18012d91c  mov     esi, eax
0x18012d91e  cmp     eax, 7Ah ; 'z'
0x18012d921  jnz     short loc_18012D93F
0x18012d923  mov     ecx, [rsp+48h+cbSid]
0x18012d927  add     rcx, 10h
0x18012d92b  call    LsapAllocate
0x18012d930  mov     rdi, rax
0x18012d933  test    rax, rax
0x18012d936  jnz     short loc_18012D965
0x18012d938  mov     ebx, 80090300h
0x18012d93d  jmp     short loc_18012D95D
0x18012d93f  test    esi, esi
0x18012d941  jnz     short loc_18012D94D
0x18012d943  mov     ebx, 80090330h
0x18012d948  jmp     loc_18012DA03
0x18012d94d  xor     edi, edi
0x18012d94f  mov     edx, 80090330h
0x18012d954  mov     ecx, esi
0x18012d956  call    ConvertWin32StatusToSecStatus
0x18012d95b  mov     ebx, eax
0x18012d95d  test    ebx, ebx
0x18012d95f  js      loc_18012DA03
0x18012d965  xor     edx, edx; DomainSid
0x18012d967  lea     rsi, [rdi+10h]
0x18012d96b  lea     r9, [rsp+48h+cbSid]; cbSid
0x18012d970  mov     r8, rsi; pSid
0x18012d973  lea     ecx, [rdx+43h]; WellKnownSidType
0x18012d976  call    cs:__imp_CreateWellKnownSid
0x18012d97d  nop     dword ptr [rax+rax+00h]
0x18012d982  test    eax, eax
0x18012d984  jnz     short loc_18012D999
0x18012d986  call    cs:__imp_GetLastError
0x18012d98d  nop     dword ptr [rax+rax+00h]
0x18012d992  mov     edx, 80090330h
0x18012d997  jmp     short loc_18012D9DA
0x18012d999  mov     dword ptr [rdi+8], 60h ; '`'
0x18012d9a0  mov     r8, rdi; TokenInformation
0x18012d9a3  mov     [rdi], rsi
0x18012d9a6  mov     edx, 19h; TokenInformationClass
0x18012d9ab  mov     r9d, [rsp+48h+cbSid]
0x18012d9b0  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18012d9b5  add     r9d, 10h; TokenInformationLength
0x18012d9b9  call    cs:__imp_SetTokenInformation
0x18012d9c0  nop     dword ptr [rax+rax+00h]
0x18012d9c5  test    eax, eax
0x18012d9c7  jnz     short loc_18012D9E5
0x18012d9c9  call    cs:__imp_GetLastError
0x18012d9d0  nop     dword ptr [rax+rax+00h]
0x18012d9d5  mov     edx, 80090308h
0x18012d9da  mov     ecx, eax
0x18012d9dc  call    ConvertWin32StatusToSecStatus
0x18012d9e1  mov     ebx, eax
0x18012d9e3  jmp     short loc_18012D9F6
0x18012d9e5  mov     rax, [rsp+48h+TokenHandle]
0x18012d9ea  mov     [r14], rax
0x18012d9ed  mov     [rsp+48h+TokenHandle], 0
0x18012d9f6  test    rdi, rdi
0x18012d9f9  jz      short loc_18012DA03
0x18012d9fb  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x18012d9fe  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18012da03  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18012da08  test    rcx, rcx
0x18012da0b  jz      short loc_18012DA19
0x18012da0d  call    cs:__imp_CloseHandle
0x18012da14  nop     dword ptr [rax+rax+00h]
0x18012da19  mov     eax, ebx
0x18012da1b  mov     rbx, [rsp+48h+arg_10]
0x18012da20  add     rsp, 30h
0x18012da24  pop     r14
0x18012da26  pop     rdi
0x18012da27  pop     rsi
0x18012da28  retn
```
