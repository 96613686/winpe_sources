# DwGetSidAfterImpersonation

- ea: `0x18003d2e0`
- end: `0x18003d6b1`
- name: `DwGetSidAfterImpersonation`
- size: `977`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001c9d0`
- `0x18002d0b0`
- `0x18002e720`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18003d2e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d3bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003d3bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003d3da`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003d3da`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18003d5c1`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18003d5c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d661`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d47c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d4e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d47c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d4e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d557`
- `RPCRT4!RpcImpersonateClient` at `0x18003d34a`
- `RPCRT4!RpcImpersonateClient` at `0x18003d34a`
- `RPCRT4!RpcRevertToSelf` at `0x18003d604`
- `RPCRT4!RpcRevertToSelf` at `0x18003d604`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003d469`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003d547`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003d469`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003d547`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d4ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003d4ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d5e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d5e5`

## pseudocode

```c
__int64 __fastcall DwGetSidAfterImpersonation(WCHAR *a1, USHORT *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  struct _LIST_ENTRY *v6; // rcx
  __int64 v7; // rdx
  HANDLE CurrentThread; // rax
  int v9; // r12d
  DWORD v10; // eax
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  PSID *v13; // rsi
  DWORD LastError; // eax
  unsigned int v15; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+80h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 602, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
  }
  TokenInformationLength = 0;
  TokenHandle = 0;
  UnicodeString = 0;
  v4 = RpcImpersonateClient(0);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 603, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v4);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v6[1].Blink) & 0x2000) != 0
        && BYTE1(v6[1].Blink) >= 6u )
      {
        v7 = 604;
LABEL_55:
        WPP_SF_d(v6[1].Flink, v7, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v5);
        return v5;
      }
    }
    return v5;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    TokenInformationLength = 0;
    v9 = 1;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( TokenInformationLength )
    {
      v13 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
      if ( v13 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v13, TokenInformationLength, &TokenInformationLength) )
        {
          UnicodeString.Buffer = a1;
          UnicodeString.Length = 0;
          UnicodeString.MaximumLength = *a2;
          v5 = RtlConvertSidToUnicodeString(&UnicodeString, *v13, 0);
          if ( !v5 )
            *a2 = UnicodeString.Length;
        }
        else
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 608, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, LastError);
          }
        }
        LocalFree(v13);
      }
      else
      {
        v10 = GetLastError();
        v5 = v10;
        if ( v10 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v12 = 607;
            goto LABEL_20;
          }
        }
      }
    }
    else
    {
      v10 = GetLastError();
      v5 = v10;
      if ( v10 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v12 = 606;
          goto LABEL_20;
        }
      }
    }
  }
  else
  {
    v9 = 0;
    v10 = GetLastError();
    v5 = v10;
    if ( v10 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v12 = 605;
LABEL_20:
        WPP_SF_d(v11[1].Flink, v12, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v10);
      }
    }
  }
  v15 = RpcRevertToSelf();
  if ( !v15 )
  {
LABEL_47:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 610, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v15);
    goto LABEL_47;
  }
LABEL_48:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && v9 == 1 )
  {
    CloseHandle(TokenHandle);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v6[1].Blink) & 0x2000) != 0
    && BYTE1(v6[1].Blink) >= 6u )
  {
    v7 = 611;
    goto LABEL_55;
  }
  return v5;
}

```

## disassembly

```asm
0x18003d2e0  mov     [rsp-28h+arg_0], rbx
0x18003d2e5  push    rbp
0x18003d2e6  push    rsi
0x18003d2e7  push    r12
0x18003d2e9  push    r14
0x18003d2eb  push    r15
0x18003d2ed  mov     rbp, rsp
0x18003d2f0  sub     rsp, 40h
0x18003d2f4  mov     r14, rdx
0x18003d2f7  mov     r15, rcx
0x18003d2fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d301  lea     r12, WPP_GLOBAL_Control
0x18003d308  mov     esi, 2000h
0x18003d30d  cmp     rcx, r12
0x18003d310  jz      short loc_18003D332
0x18003d312  test    [rcx+1Ch], esi
0x18003d315  jz      short loc_18003D332
0x18003d317  cmp     byte ptr [rcx+19h], 6
0x18003d31b  jb      short loc_18003D332
0x18003d31d  mov     rcx, [rcx+10h]
0x18003d321  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003d328  mov     edx, 25Ah
0x18003d32d  call    WPP_SF_
0x18003d332  xorps   xmm0, xmm0
0x18003d335  mov     [rbp+TokenInformationLength], 0
0x18003d33c  xor     ecx, ecx; BindingHandle
0x18003d33e  mov     [rbp+TokenHandle], 0
0x18003d346  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18003d34a  call    cs:__imp_RpcImpersonateClient
0x18003d351  nop     dword ptr [rax+rax+00h]
0x18003d356  mov     ebx, eax
0x18003d358  test    eax, eax
0x18003d35a  jz      short loc_18003D3BC
0x18003d35c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d363  cmp     rcx, r12
0x18003d366  jz      loc_18003D69C
0x18003d36c  test    [rcx+1Ch], esi
0x18003d36f  jz      short loc_18003D396
0x18003d371  cmp     byte ptr [rcx+19h], 2
0x18003d375  jb      short loc_18003D396
0x18003d377  mov     rcx, [rcx+10h]
0x18003d37b  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003d382  mov     edx, 25Bh
0x18003d387  mov     r9d, eax
0x18003d38a  call    WPP_SF_d
0x18003d38f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d396  cmp     rcx, r12
0x18003d399  jz      loc_18003D69C
0x18003d39f  test    [rcx+1Ch], esi
0x18003d3a2  jz      loc_18003D69C
0x18003d3a8  cmp     byte ptr [rcx+19h], 6
0x18003d3ac  jb      loc_18003D69C
0x18003d3b2  mov     edx, 25Ch
0x18003d3b7  jmp     loc_18003D689
0x18003d3bc  call    cs:__imp_GetCurrentThread
0x18003d3c3  nop     dword ptr [rax+rax+00h]
0x18003d3c8  mov     ebx, 1
0x18003d3cd  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18003d3d1  mov     rcx, rax; ThreadHandle
0x18003d3d4  mov     r8d, ebx; OpenAsSelf
0x18003d3d7  lea     edx, [rbx+7]; DesiredAccess
0x18003d3da  call    cs:__imp_OpenThreadToken
0x18003d3e1  nop     dword ptr [rax+rax+00h]
0x18003d3e6  test    eax, eax
0x18003d3e8  jnz     short loc_18003D44A
0x18003d3ea  xor     r12d, r12d
0x18003d3ed  call    cs:__imp_GetLastError
0x18003d3f4  nop     dword ptr [rax+rax+00h]
0x18003d3f9  mov     ebx, eax
0x18003d3fb  test    eax, eax
0x18003d3fd  jz      loc_18003D5FD
0x18003d403  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d40a  lea     r14, WPP_GLOBAL_Control
0x18003d411  cmp     rcx, r14
0x18003d414  jz      loc_18003D604
0x18003d41a  test    [rcx+1Ch], esi
0x18003d41d  jz      loc_18003D604
0x18003d423  cmp     byte ptr [rcx+19h], 2
0x18003d427  jb      loc_18003D604
0x18003d42d  mov     edx, 25Dh
0x18003d432  mov     rcx, [rcx+10h]
0x18003d436  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003d43d  mov     r9d, eax
0x18003d440  call    WPP_SF_d
0x18003d445  jmp     loc_18003D604
0x18003d44a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003d44e  lea     rax, [rbp+TokenInformationLength]
0x18003d452  xor     r9d, r9d; TokenInformationLength
0x18003d455  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18003d45a  xor     r8d, r8d; TokenInformation
0x18003d45d  mov     [rbp+TokenInformationLength], 0
0x18003d464  mov     edx, ebx; TokenInformationClass
0x18003d466  mov     r12d, ebx
0x18003d469  call    cs:__imp_GetTokenInformation
0x18003d470  nop     dword ptr [rax+rax+00h]
0x18003d475  mov     eax, [rbp+TokenInformationLength]
0x18003d478  test    eax, eax
0x18003d47a  jnz     short loc_18003D4C6
0x18003d47c  call    cs:__imp_GetLastError
0x18003d483  nop     dword ptr [rax+rax+00h]
0x18003d488  mov     ebx, eax
0x18003d48a  test    eax, eax
0x18003d48c  jz      loc_18003D5FD
0x18003d492  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d499  lea     r14, WPP_GLOBAL_Control
0x18003d4a0  cmp     rcx, r14
0x18003d4a3  jz      loc_18003D604
0x18003d4a9  test    [rcx+1Ch], esi
0x18003d4ac  jz      loc_18003D604
0x18003d4b2  cmp     byte ptr [rcx+19h], 2
0x18003d4b6  jb      loc_18003D604
0x18003d4bc  mov     edx, 25Eh
0x18003d4c1  jmp     loc_18003D432
0x18003d4c6  mov     rdx, rax; uBytes
0x18003d4c9  mov     ecx, 40h ; '@'; uFlags
0x18003d4ce  call    cs:__imp_LocalAlloc
0x18003d4d5  nop     dword ptr [rax+rax+00h]
0x18003d4da  mov     rsi, rax
0x18003d4dd  test    rax, rax
0x18003d4e0  jnz     short loc_18003D531
0x18003d4e2  call    cs:__imp_GetLastError
0x18003d4e9  nop     dword ptr [rax+rax+00h]
0x18003d4ee  mov     ebx, eax
0x18003d4f0  test    eax, eax
0x18003d4f2  jz      loc_18003D5F8
0x18003d4f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d4ff  lea     r14, WPP_GLOBAL_Control
0x18003d506  mov     esi, 2000h
0x18003d50b  cmp     rcx, r14
0x18003d50e  jz      loc_18003D604
0x18003d514  test    [rcx+1Ch], esi
0x18003d517  jz      loc_18003D604
0x18003d51d  cmp     byte ptr [rcx+19h], 2
0x18003d521  jb      loc_18003D604
0x18003d527  mov     edx, 25Fh
0x18003d52c  jmp     loc_18003D432
0x18003d531  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18003d535  lea     rax, [rbp+TokenInformationLength]
0x18003d539  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003d53d  mov     r8, rsi; TokenInformation
0x18003d540  mov     edx, ebx; TokenInformationClass
0x18003d542  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18003d547  call    cs:__imp_GetTokenInformation
0x18003d54e  nop     dword ptr [rax+rax+00h]
0x18003d553  test    eax, eax
0x18003d555  jnz     short loc_18003D5A5
0x18003d557  call    cs:__imp_GetLastError
0x18003d55e  nop     dword ptr [rax+rax+00h]
0x18003d563  mov     ebx, eax
0x18003d565  test    eax, eax
0x18003d567  jz      short loc_18003D5DB
0x18003d569  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d570  lea     r14, WPP_GLOBAL_Control
0x18003d577  cmp     rcx, r14
0x18003d57a  jz      short loc_18003D5E2
0x18003d57c  test    dword ptr [rcx+1Ch], 2000h
0x18003d583  jz      short loc_18003D5E2
0x18003d585  cmp     byte ptr [rcx+19h], 2
0x18003d589  jb      short loc_18003D5E2
0x18003d58b  mov     rcx, [rcx+10h]
0x18003d58f  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003d596  mov     edx, 260h
0x18003d59b  mov     r9d, eax
0x18003d59e  call    WPP_SF_d
0x18003d5a3  jmp     short loc_18003D5E2
0x18003d5a5  xor     eax, eax
0x18003d5a7  mov     [rbp+UnicodeString.Buffer], r15
0x18003d5ab  mov     [rbp+UnicodeString.Length], ax
0x18003d5af  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18003d5b3  movzx   eax, word ptr [r14]
0x18003d5b7  xor     r8d, r8d; AllocateDestinationString
0x18003d5ba  mov     [rbp+UnicodeString.MaximumLength], ax
0x18003d5be  mov     rdx, [rsi]; Sid
0x18003d5c1  call    cs:__imp_RtlConvertSidToUnicodeString
0x18003d5c8  nop     dword ptr [rax+rax+00h]
0x18003d5cd  mov     ebx, eax
0x18003d5cf  test    eax, eax
0x18003d5d1  jnz     short loc_18003D5DB
0x18003d5d3  movzx   eax, [rbp+UnicodeString.Length]
0x18003d5d7  mov     [r14], ax
0x18003d5db  lea     r14, WPP_GLOBAL_Control
0x18003d5e2  mov     rcx, rsi; hMem
0x18003d5e5  call    cs:__imp_LocalFree
0x18003d5ec  nop     dword ptr [rax+rax+00h]
0x18003d5f1  mov     esi, 2000h
0x18003d5f6  jmp     short loc_18003D604
0x18003d5f8  mov     esi, 2000h
0x18003d5fd  lea     r14, WPP_GLOBAL_Control
0x18003d604  call    cs:__imp_RpcRevertToSelf
0x18003d60b  nop     dword ptr [rax+rax+00h]
0x18003d610  test    eax, eax
0x18003d612  jz      short loc_18003D643
0x18003d614  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d61b  cmp     rcx, r14
0x18003d61e  jz      short loc_18003D64A
0x18003d620  test    [rcx+1Ch], esi
0x18003d623  jz      short loc_18003D64A
0x18003d625  cmp     byte ptr [rcx+19h], 2
0x18003d629  jb      short loc_18003D64A
0x18003d62b  mov     rcx, [rcx+10h]
0x18003d62f  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003d636  mov     edx, 262h
0x18003d63b  mov     r9d, eax
0x18003d63e  call    WPP_SF_d
0x18003d643  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d64a  mov     rdx, [rbp+TokenHandle]
0x18003d64e  lea     rax, [rdx-1]
0x18003d652  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003d656  ja      short loc_18003D674
0x18003d658  cmp     r12d, 1
0x18003d65c  jnz     short loc_18003D674
0x18003d65e  mov     rcx, rdx; hObject
0x18003d661  call    cs:__imp_CloseHandle
0x18003d668  nop     dword ptr [rax+rax+00h]
0x18003d66d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d674  cmp     rcx, r14
0x18003d677  jz      short loc_18003D69C
0x18003d679  test    [rcx+1Ch], esi
0x18003d67c  jz      short loc_18003D69C
0x18003d67e  cmp     byte ptr [rcx+19h], 6
0x18003d682  jb      short loc_18003D69C
0x18003d684  mov     edx, 263h
0x18003d689  mov     rcx, [rcx+10h]
0x18003d68d  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003d694  mov     r9d, ebx
0x18003d697  call    WPP_SF_d
0x18003d69c  mov     eax, ebx
0x18003d69e  mov     rbx, [rsp+40h+arg_0]
0x18003d6a3  add     rsp, 40h
0x18003d6a7  pop     r15
0x18003d6a9  pop     r14
0x18003d6ab  pop     r12
0x18003d6ad  pop     rsi
0x18003d6ae  pop     rbp
0x18003d6af  retn
```
