# ValidateAccountDomain

- ea: `0x180031c0c`
- end: `0x180031ea3`
- name: `ValidateAccountDomain`
- size: `663`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ada0`

## callees

- `0x180031c0c`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180031cd0`
- `msvcrt!wcscat_s` at `0x180031ce1`
- `msvcrt!wcscat_s` at `0x180031cd0`
- `msvcrt!wcscat_s` at `0x180031ce1`
- `msvcrt!wcscpy_s` at `0x180031cbb`
- `msvcrt!wcscpy_s` at `0x180031cbb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031d17`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031d17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031cfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031cfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031e33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031e33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d60`
- `RPCRT4!RpcImpersonateClient` at `0x180031ce9`
- `RPCRT4!RpcImpersonateClient` at `0x180031ce9`
- `RPCRT4!RpcRevertToSelf` at `0x180031e70`
- `RPCRT4!RpcRevertToSelf` at `0x180031e70`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180031e02`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180031e02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031e4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031e65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031e4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031e65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031d75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031d9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031d75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031d9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e57`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031d84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031dad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031d84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031dad`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180031d56`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180031de7`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180031d56`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180031de7`

## pseudocode

```c
__int64 __fastcall ValidateAccountDomain(wchar_t *Source, wchar_t *a2)
{
  int v4; // r15d
  WCHAR *ReferencedDomainName; // rsi
  void *v6; // rdi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  DWORD v11; // ebx
  HANDLE v12; // rax
  HANDLE v13; // rax
  HANDLE v14; // rax
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v19; // [rsp+4Ch] [rbp-B4h] BYREF
  WINBOOL IsMember; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Destination[280]; // [rsp+60h] [rbp-A0h] BYREF

  TokenHandle = (void *)-1LL;
  v4 = 0;
  memset_0(Destination, 0, 0x222u);
  cchReferencedDomainName = 0;
  ReferencedDomainName = 0;
  v19 = 0;
  v6 = 0;
  peUse = 0;
  IsMember = 0;
  cbSid = 0;
  if ( a2 && Source && *a2 && *Source )
  {
    wcscpy_s(Destination, 0x111u, a2);
    wcscat_s(Destination, 0x111u, L"\\");
    wcscat_s(Destination, 0x111u, Source);
    LastError = RpcImpersonateClient(0);
    if ( LastError )
      goto LABEL_18;
    v4 = 1;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      goto LABEL_7;
    if ( LookupAccountNameW(0, Destination, 0, &cbSid, 0, &cchReferencedDomainName, &peUse)
      || (LastError = GetLastError(), LastError == 122) )
    {
      v9 = cbSid;
      ProcessHeap = GetProcessHeap();
      v6 = HeapAlloc(ProcessHeap, 8u, v9);
      if ( !v6
        || (v19 = 2 * cchReferencedDomainName,
            v11 = 2 * cchReferencedDomainName,
            v12 = GetProcessHeap(),
            (ReferencedDomainName = (WCHAR *)HeapAlloc(v12, 8u, v11)) == 0)
        || !LookupAccountNameW(0, Destination, v6, &cbSid, ReferencedDomainName, &v19, &peUse)
        || !CheckTokenMembership(TokenHandle, v6, &IsMember) )
      {
LABEL_7:
        LastError = GetLastError();
        goto LABEL_18;
      }
      if ( IsMember )
        LastError = 0;
      else
        LastError = 5;
    }
  }
  else
  {
    LastError = 87;
  }
LABEL_18:
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  if ( v6 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v6);
  }
  if ( ReferencedDomainName )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, ReferencedDomainName);
  }
  if ( v4 )
    RpcRevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x180031c0c  mov     [rsp-8+arg_10], rbx
0x180031c11  mov     [rsp-8+arg_18], rsi
0x180031c16  push    rbp
0x180031c17  push    rdi
0x180031c18  push    r12
0x180031c1a  push    r14
0x180031c1c  push    r15
0x180031c1e  lea     rbp, [rsp-1A0h]
0x180031c26  sub     rsp, 2A0h
0x180031c2d  mov     rax, cs:__security_cookie
0x180031c34  xor     rax, rsp
0x180031c37  mov     [rbp+1C0h+var_30], rax
0x180031c3e  mov     r14, rdx
0x180031c41  mov     [rsp+2C0h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180031c4a  mov     rbx, rcx
0x180031c4d  xor     r12d, r12d
0x180031c50  xor     edx, edx; Val
0x180031c52  lea     rcx, [rsp+2C0h+Destination]; void *
0x180031c57  mov     r8d, 222h; Size
0x180031c5d  mov     r15d, r12d
0x180031c60  call    memset_0
0x180031c65  mov     [rsp+2C0h+var_27C], r12d
0x180031c6a  mov     esi, r12d
0x180031c6d  mov     [rsp+2C0h+var_274], r12d
0x180031c72  mov     edi, r12d
0x180031c75  mov     [rsp+2C0h+var_278], r12d
0x180031c7a  mov     [rsp+2C0h+IsMember], r12d
0x180031c7f  mov     [rsp+2C0h+cbSid], r12d
0x180031c84  test    r14, r14
0x180031c87  jz      loc_180031E23
0x180031c8d  test    rbx, rbx
0x180031c90  jz      loc_180031E23
0x180031c96  cmp     [r14], r12w
0x180031c9a  jz      loc_180031E23
0x180031ca0  cmp     [rbx], r12w
0x180031ca4  jz      loc_180031E23
0x180031caa  mov     r8, r14; Source
0x180031cad  lea     rcx, [rsp+2C0h+Destination]; Destination
0x180031cb2  mov     r14d, 111h
0x180031cb8  mov     edx, r14d; SizeInWords
0x180031cbb  call    cs:__imp_wcscpy_s
0x180031cc1  lea     r8, Source; "\\"
0x180031cc8  mov     edx, r14d; SizeInWords
0x180031ccb  lea     rcx, [rsp+2C0h+Destination]; Destination
0x180031cd0  call    cs:__imp_wcscat_s
0x180031cd6  mov     r8, rbx; Source
0x180031cd9  lea     rcx, [rsp+2C0h+Destination]; Destination
0x180031cde  mov     edx, r14d; SizeInWords
0x180031ce1  call    cs:__imp_wcscat_s
0x180031ce7  xor     ecx, ecx; BindingHandle
0x180031ce9  call    cs:__imp_RpcImpersonateClient
0x180031cef  mov     ebx, eax
0x180031cf1  test    eax, eax
0x180031cf3  jnz     loc_180031E28
0x180031cf9  lea     r15d, [r12+1]
0x180031cfe  call    cs:__imp_GetCurrentThread
0x180031d04  lea     r14d, [r12+8]
0x180031d09  mov     r8d, r15d; OpenAsSelf
0x180031d0c  mov     rcx, rax; ThreadHandle
0x180031d0f  lea     r9, [rsp+2C0h+TokenHandle]; TokenHandle
0x180031d14  mov     edx, r14d; DesiredAccess
0x180031d17  call    cs:__imp_OpenThreadToken
0x180031d1d  test    eax, eax
0x180031d1f  jnz     short loc_180031D2E
0x180031d21  call    cs:__imp_GetLastError
0x180031d27  mov     ebx, eax
0x180031d29  jmp     loc_180031E28
0x180031d2e  lea     rax, [rsp+2C0h+var_278]
0x180031d33  xor     r8d, r8d; Sid
0x180031d36  mov     [rsp+2C0h+peUse], rax; peUse
0x180031d3b  lea     r9, [rsp+2C0h+cbSid]; cbSid
0x180031d40  lea     rax, [rsp+2C0h+var_27C]
0x180031d45  xor     ecx, ecx; lpSystemName
0x180031d47  mov     [rsp+2C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180031d4c  lea     rdx, [rsp+2C0h+Destination]; lpAccountName
0x180031d51  mov     [rsp+2C0h+ReferencedDomainName], r12; ReferencedDomainName
0x180031d56  call    cs:__imp_LookupAccountNameW
0x180031d5c  test    eax, eax
0x180031d5e  jnz     short loc_180031D71
0x180031d60  call    cs:__imp_GetLastError
0x180031d66  mov     ebx, eax
0x180031d68  cmp     eax, 7Ah ; 'z'
0x180031d6b  jnz     loc_180031E28
0x180031d71  mov     ebx, [rsp+2C0h+cbSid]
0x180031d75  call    cs:__imp_GetProcessHeap
0x180031d7b  mov     r8d, ebx; dwBytes
0x180031d7e  mov     edx, r14d; dwFlags
0x180031d81  mov     rcx, rax; hHeap
0x180031d84  call    cs:__imp_HeapAlloc
0x180031d8a  mov     rdi, rax
0x180031d8d  test    rax, rax
0x180031d90  jz      short loc_180031D21
0x180031d92  mov     eax, [rsp+2C0h+var_27C]
0x180031d96  add     eax, eax
0x180031d98  mov     [rsp+2C0h+var_274], eax
0x180031d9c  mov     ebx, eax
0x180031d9e  call    cs:__imp_GetProcessHeap
0x180031da4  mov     r8d, ebx; dwBytes
0x180031da7  mov     edx, r14d; dwFlags
0x180031daa  mov     rcx, rax; hHeap
0x180031dad  call    cs:__imp_HeapAlloc
0x180031db3  mov     rsi, rax
0x180031db6  test    rax, rax
0x180031db9  jz      loc_180031D21
0x180031dbf  lea     rax, [rsp+2C0h+var_278]
0x180031dc4  mov     r8, rdi; Sid
0x180031dc7  mov     [rsp+2C0h+peUse], rax; peUse
0x180031dcc  lea     r9, [rsp+2C0h+cbSid]; cbSid
0x180031dd1  lea     rax, [rsp+2C0h+var_274]
0x180031dd6  xor     ecx, ecx; lpSystemName
0x180031dd8  mov     [rsp+2C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180031ddd  lea     rdx, [rsp+2C0h+Destination]; lpAccountName
0x180031de2  mov     [rsp+2C0h+ReferencedDomainName], rsi; ReferencedDomainName
0x180031de7  call    cs:__imp_LookupAccountNameW
0x180031ded  test    eax, eax
0x180031def  jz      loc_180031D21
0x180031df5  mov     rcx, [rsp+2C0h+TokenHandle]; TokenHandle
0x180031dfa  lea     r8, [rsp+2C0h+IsMember]; IsMember
0x180031dff  mov     rdx, rdi; SidToCheck
0x180031e02  call    cs:__imp_CheckTokenMembership
0x180031e08  test    eax, eax
0x180031e0a  jz      loc_180031D21
0x180031e10  cmp     [rsp+2C0h+IsMember], r12d
0x180031e15  jnz     short loc_180031E1E
0x180031e17  mov     ebx, 5
0x180031e1c  jmp     short loc_180031E28
0x180031e1e  mov     ebx, r12d
0x180031e21  jmp     short loc_180031E28
0x180031e23  mov     ebx, 57h ; 'W'
0x180031e28  mov     rcx, [rsp+2C0h+TokenHandle]; hObject
0x180031e2d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180031e31  jz      short loc_180031E39
0x180031e33  call    cs:__imp_CloseHandle
0x180031e39  test    rdi, rdi
0x180031e3c  jz      short loc_180031E52
0x180031e3e  call    cs:__imp_GetProcessHeap
0x180031e44  mov     r8, rdi; lpMem
0x180031e47  xor     edx, edx; dwFlags
0x180031e49  mov     rcx, rax; hHeap
0x180031e4c  call    cs:__imp_HeapFree
0x180031e52  test    rsi, rsi
0x180031e55  jz      short loc_180031E6B
0x180031e57  call    cs:__imp_GetProcessHeap
0x180031e5d  mov     r8, rsi; lpMem
0x180031e60  xor     edx, edx; dwFlags
0x180031e62  mov     rcx, rax; hHeap
0x180031e65  call    cs:__imp_HeapFree
0x180031e6b  test    r15d, r15d
0x180031e6e  jz      short loc_180031E76
0x180031e70  call    cs:__imp_RpcRevertToSelf
0x180031e76  mov     eax, ebx
0x180031e78  mov     rcx, [rbp+1C0h+var_30]
0x180031e7f  xor     rcx, rsp; StackCookie
0x180031e82  call    __security_check_cookie
0x180031e87  lea     r11, [rsp+2C0h+var_20]
0x180031e8f  mov     rbx, [r11+40h]
0x180031e93  mov     rsi, [r11+48h]
0x180031e97  mov     rsp, r11
0x180031e9a  pop     r15
0x180031e9c  pop     r14
0x180031e9e  pop     r12
0x180031ea0  pop     rdi
0x180031ea1  pop     rbp
0x180031ea2  retn
```
