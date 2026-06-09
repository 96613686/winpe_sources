# DwGetSidAfterImpersonation

- ea: `0x18003b578`
- end: `0x18003b8f4`
- name: `DwGetSidAfterImpersonation`
- size: `892`
- prototype: `__int64 __fastcall(WCHAR *, USHORT *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001bef0`
- `0x18002be00`
- `0x18002d3e0`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18003b578`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003b666`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003b666`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003b64e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003b64e`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18003b81d`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18003b81d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b8ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b8ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b6f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b7b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b673`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b6f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b7b9`
- `RPCRT4!RpcImpersonateClient` at `0x18003b5e2`
- `RPCRT4!RpcImpersonateClient` at `0x18003b5e2`
- `RPCRT4!RpcRevertToSelf` at `0x18003b854`
- `RPCRT4!RpcRevertToSelf` at `0x18003b854`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003b6e9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003b7af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003b6e9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003b7af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b742`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b742`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b83b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b83b`

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
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 604, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
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
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 605, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v4);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v6[1].Blink) & 0x2000) != 0
        && BYTE1(v6[1].Blink) >= 6u )
      {
        v7 = 606;
LABEL_55:
        WPP_SF_d(v6[1].Flink, v7, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v5);
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
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 610, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, LastError);
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
            v12 = 609;
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
          v12 = 608;
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
        v12 = 607;
LABEL_20:
        WPP_SF_d(v11[1].Flink, v12, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v10);
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
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 612, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v15);
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
    v7 = 613;
    goto LABEL_55;
  }
  return v5;
}

```

## disassembly

```asm
0x18003b578  mov     [rsp-28h+arg_0], rbx
0x18003b57d  push    rbp
0x18003b57e  push    rsi
0x18003b57f  push    r12
0x18003b581  push    r14
0x18003b583  push    r15
0x18003b585  mov     rbp, rsp
0x18003b588  sub     rsp, 40h
0x18003b58c  mov     r14, rdx
0x18003b58f  mov     r15, rcx
0x18003b592  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b599  lea     r12, WPP_GLOBAL_Control
0x18003b5a0  mov     esi, 2000h
0x18003b5a5  cmp     rcx, r12
0x18003b5a8  jz      short loc_18003B5CA
0x18003b5aa  test    [rcx+1Ch], esi
0x18003b5ad  jz      short loc_18003B5CA
0x18003b5af  cmp     byte ptr [rcx+19h], 6
0x18003b5b3  jb      short loc_18003B5CA
0x18003b5b5  mov     rcx, [rcx+10h]
0x18003b5b9  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003b5c0  mov     edx, 25Ch
0x18003b5c5  call    WPP_SF_
0x18003b5ca  xorps   xmm0, xmm0
0x18003b5cd  mov     [rbp+TokenInformationLength], 0
0x18003b5d4  xor     ecx, ecx; BindingHandle
0x18003b5d6  mov     [rbp+TokenHandle], 0
0x18003b5de  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18003b5e2  call    cs:__imp_RpcImpersonateClient
0x18003b5e8  mov     ebx, eax
0x18003b5ea  test    eax, eax
0x18003b5ec  jz      short loc_18003B64E
0x18003b5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b5f5  cmp     rcx, r12
0x18003b5f8  jz      loc_18003B8E0
0x18003b5fe  test    [rcx+1Ch], esi
0x18003b601  jz      short loc_18003B628
0x18003b603  cmp     byte ptr [rcx+19h], 2
0x18003b607  jb      short loc_18003B628
0x18003b609  mov     rcx, [rcx+10h]
0x18003b60d  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003b614  mov     edx, 25Dh
0x18003b619  mov     r9d, eax
0x18003b61c  call    WPP_SF_d
0x18003b621  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b628  cmp     rcx, r12
0x18003b62b  jz      loc_18003B8E0
0x18003b631  test    [rcx+1Ch], esi
0x18003b634  jz      loc_18003B8E0
0x18003b63a  cmp     byte ptr [rcx+19h], 6
0x18003b63e  jb      loc_18003B8E0
0x18003b644  mov     edx, 25Eh
0x18003b649  jmp     loc_18003B8CD
0x18003b64e  call    cs:__imp_GetCurrentThread
0x18003b654  mov     ebx, 1
0x18003b659  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18003b65d  mov     rcx, rax; ThreadHandle
0x18003b660  mov     r8d, ebx; OpenAsSelf
0x18003b663  lea     edx, [rbx+7]; DesiredAccess
0x18003b666  call    cs:__imp_OpenThreadToken
0x18003b66c  test    eax, eax
0x18003b66e  jnz     short loc_18003B6CA
0x18003b670  xor     r12d, r12d
0x18003b673  call    cs:__imp_GetLastError
0x18003b679  mov     ebx, eax
0x18003b67b  test    eax, eax
0x18003b67d  jz      loc_18003B84D
0x18003b683  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b68a  lea     r14, WPP_GLOBAL_Control
0x18003b691  cmp     rcx, r14
0x18003b694  jz      loc_18003B854
0x18003b69a  test    [rcx+1Ch], esi
0x18003b69d  jz      loc_18003B854
0x18003b6a3  cmp     byte ptr [rcx+19h], 2
0x18003b6a7  jb      loc_18003B854
0x18003b6ad  mov     edx, 25Fh
0x18003b6b2  mov     rcx, [rcx+10h]
0x18003b6b6  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003b6bd  mov     r9d, eax
0x18003b6c0  call    WPP_SF_d
0x18003b6c5  jmp     loc_18003B854
0x18003b6ca  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003b6ce  lea     rax, [rbp+TokenInformationLength]
0x18003b6d2  xor     r9d, r9d; TokenInformationLength
0x18003b6d5  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18003b6da  xor     r8d, r8d; TokenInformation
0x18003b6dd  mov     [rbp+TokenInformationLength], 0
0x18003b6e4  mov     edx, ebx; TokenInformationClass
0x18003b6e6  mov     r12d, ebx
0x18003b6e9  call    cs:__imp_GetTokenInformation
0x18003b6ef  mov     eax, [rbp+TokenInformationLength]
0x18003b6f2  test    eax, eax
0x18003b6f4  jnz     short loc_18003B73A
0x18003b6f6  call    cs:__imp_GetLastError
0x18003b6fc  mov     ebx, eax
0x18003b6fe  test    eax, eax
0x18003b700  jz      loc_18003B84D
0x18003b706  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b70d  lea     r14, WPP_GLOBAL_Control
0x18003b714  cmp     rcx, r14
0x18003b717  jz      loc_18003B854
0x18003b71d  test    [rcx+1Ch], esi
0x18003b720  jz      loc_18003B854
0x18003b726  cmp     byte ptr [rcx+19h], 2
0x18003b72a  jb      loc_18003B854
0x18003b730  mov     edx, 260h
0x18003b735  jmp     loc_18003B6B2
0x18003b73a  mov     rdx, rax; uBytes
0x18003b73d  mov     ecx, 40h ; '@'; uFlags
0x18003b742  call    cs:__imp_LocalAlloc
0x18003b748  mov     rsi, rax
0x18003b74b  test    rax, rax
0x18003b74e  jnz     short loc_18003B799
0x18003b750  call    cs:__imp_GetLastError
0x18003b756  mov     ebx, eax
0x18003b758  test    eax, eax
0x18003b75a  jz      loc_18003B848
0x18003b760  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b767  lea     r14, WPP_GLOBAL_Control
0x18003b76e  mov     esi, 2000h
0x18003b773  cmp     rcx, r14
0x18003b776  jz      loc_18003B854
0x18003b77c  test    [rcx+1Ch], esi
0x18003b77f  jz      loc_18003B854
0x18003b785  cmp     byte ptr [rcx+19h], 2
0x18003b789  jb      loc_18003B854
0x18003b78f  mov     edx, 261h
0x18003b794  jmp     loc_18003B6B2
0x18003b799  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18003b79d  lea     rax, [rbp+TokenInformationLength]
0x18003b7a1  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003b7a5  mov     r8, rsi; TokenInformation
0x18003b7a8  mov     edx, ebx; TokenInformationClass
0x18003b7aa  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18003b7af  call    cs:__imp_GetTokenInformation
0x18003b7b5  test    eax, eax
0x18003b7b7  jnz     short loc_18003B801
0x18003b7b9  call    cs:__imp_GetLastError
0x18003b7bf  mov     ebx, eax
0x18003b7c1  test    eax, eax
0x18003b7c3  jz      short loc_18003B831
0x18003b7c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b7cc  lea     r14, WPP_GLOBAL_Control
0x18003b7d3  cmp     rcx, r14
0x18003b7d6  jz      short loc_18003B838
0x18003b7d8  test    dword ptr [rcx+1Ch], 2000h
0x18003b7df  jz      short loc_18003B838
0x18003b7e1  cmp     byte ptr [rcx+19h], 2
0x18003b7e5  jb      short loc_18003B838
0x18003b7e7  mov     rcx, [rcx+10h]
0x18003b7eb  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003b7f2  mov     edx, 262h
0x18003b7f7  mov     r9d, eax
0x18003b7fa  call    WPP_SF_d
0x18003b7ff  jmp     short loc_18003B838
0x18003b801  xor     eax, eax
0x18003b803  mov     [rbp+UnicodeString.Buffer], r15
0x18003b807  mov     [rbp+UnicodeString.Length], ax
0x18003b80b  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18003b80f  movzx   eax, word ptr [r14]
0x18003b813  xor     r8d, r8d; AllocateDestinationString
0x18003b816  mov     [rbp+UnicodeString.MaximumLength], ax
0x18003b81a  mov     rdx, [rsi]; Sid
0x18003b81d  call    cs:__imp_RtlConvertSidToUnicodeString
0x18003b823  mov     ebx, eax
0x18003b825  test    eax, eax
0x18003b827  jnz     short loc_18003B831
0x18003b829  movzx   eax, [rbp+UnicodeString.Length]
0x18003b82d  mov     [r14], ax
0x18003b831  lea     r14, WPP_GLOBAL_Control
0x18003b838  mov     rcx, rsi; hMem
0x18003b83b  call    cs:__imp_LocalFree
0x18003b841  mov     esi, 2000h
0x18003b846  jmp     short loc_18003B854
0x18003b848  mov     esi, 2000h
0x18003b84d  lea     r14, WPP_GLOBAL_Control
0x18003b854  call    cs:__imp_RpcRevertToSelf
0x18003b85a  test    eax, eax
0x18003b85c  jz      short loc_18003B88D
0x18003b85e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b865  cmp     rcx, r14
0x18003b868  jz      short loc_18003B894
0x18003b86a  test    [rcx+1Ch], esi
0x18003b86d  jz      short loc_18003B894
0x18003b86f  cmp     byte ptr [rcx+19h], 2
0x18003b873  jb      short loc_18003B894
0x18003b875  mov     rcx, [rcx+10h]
0x18003b879  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003b880  mov     edx, 264h
0x18003b885  mov     r9d, eax
0x18003b888  call    WPP_SF_d
0x18003b88d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b894  mov     rdx, [rbp+TokenHandle]
0x18003b898  lea     rax, [rdx-1]
0x18003b89c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b8a0  ja      short loc_18003B8B8
0x18003b8a2  cmp     r12d, 1
0x18003b8a6  jnz     short loc_18003B8B8
0x18003b8a8  mov     rcx, rdx; hObject
0x18003b8ab  call    cs:__imp_CloseHandle
0x18003b8b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b8b8  cmp     rcx, r14
0x18003b8bb  jz      short loc_18003B8E0
0x18003b8bd  test    [rcx+1Ch], esi
0x18003b8c0  jz      short loc_18003B8E0
0x18003b8c2  cmp     byte ptr [rcx+19h], 6
0x18003b8c6  jb      short loc_18003B8E0
0x18003b8c8  mov     edx, 265h
0x18003b8cd  mov     rcx, [rcx+10h]
0x18003b8d1  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003b8d8  mov     r9d, ebx
0x18003b8db  call    WPP_SF_d
0x18003b8e0  mov     eax, ebx
0x18003b8e2  mov     rbx, [rsp+40h+arg_0]
0x18003b8e7  add     rsp, 40h
0x18003b8eb  pop     r15
0x18003b8ed  pop     r14
0x18003b8ef  pop     r12
0x18003b8f1  pop     rsi
0x18003b8f2  pop     rbp
0x18003b8f3  retn
```
