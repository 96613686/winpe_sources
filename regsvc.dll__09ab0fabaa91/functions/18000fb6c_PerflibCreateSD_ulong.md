# PerflibCreateSD(ulong)

- ea: `0x18000fb6c`
- end: `0x18000fdc7`
- name: `?PerflibCreateSD@@YAHK@Z`
- size: `603`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e1a8`

## callees

- `0x180005da0`
- `0x180007740`
- `0x180008050`
- `0x18000fb6c`
- `0x180011ad4`
- `0x18001e431`

## import_xrefs

- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18000fd5f`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18000fd5f`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000fd0a`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000fd27`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000fd0a`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000fd27`
- `ntdll!RtlLengthSid` at `0x18000fc44`
- `ntdll!RtlLengthSid` at `0x18000fc44`
- `ntdll!NtQueryInformationToken` at `0x18000fc18`
- `ntdll!NtQueryInformationToken` at `0x18000fc18`
- `ntdll!NtOpenProcessToken` at `0x18000fbb9`
- `ntdll!NtOpenProcessToken` at `0x18000fbb9`
- `ntdll!RtlCreateAcl` at `0x18000fce1`
- `ntdll!RtlCreateAcl` at `0x18000fce1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fc6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fc6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fba7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fba7`

## pseudocode

```c
__int64 __fastcall PerflibCreateSD(int a1)
{
  HANDLE CurrentProcess; // rax
  unsigned int v2; // edi
  PSID v3; // r12
  ULONG v4; // edi
  ULONG v5; // r15d
  __int64 v6; // rax
  _DWORD *v7; // rsi
  struct _ACL *v9; // rax
  struct _ACL *v10; // r14
  PSID TokenInformation[6]; // [rsp+10h] [rbp-60h] BYREF
  ULONG TokenInformationLength; // [rsp+70h] [rbp+0h] BYREF
  void *TokenHandle[2]; // [rsp+78h] [rbp+8h] BYREF
  size_t Size; // [rsp+88h] [rbp+18h]
  _DWORD pSid[4]; // [rsp+90h] [rbp+20h] BYREF

  TokenHandle[0] = 0;
  if ( a1 && a1 != 1008 )
    return 0;
  CurrentProcess = GetCurrentProcess();
  if ( NtOpenProcessToken(CurrentProcess, 8u, TokenHandle) < 0 )
    return 0;
  TokenInformationLength = 88;
  TokenHandle[1] = TokenInformation;
  if ( NtQueryInformationToken(TokenHandle[0], TokenUser, TokenInformation, 0x58u, &TokenInformationLength) >= 0 )
  {
    pSid[0] = 257;
    pSid[1] = 83886080;
    pSid[2] = 18;
    v3 = TokenInformation[0];
    TokenInformationLength = RtlLengthSid(TokenInformation[0]);
    v4 = TokenInformationLength + 36;
    v5 = TokenInformationLength + 36 + 2 * (TokenInformationLength + 10);
    v6 = operator new(v5);
    v7 = (_DWORD *)v6;
    if ( v6 )
    {
      *(_BYTE *)v6 = 1;
      *(_WORD *)(v6 + 2) = -32764;
      memcpy_0((void *)(v6 + 20), v3, TokenInformationLength);
      v7[1] = 20;
      memcpy_0((char *)v7 + TokenInformationLength + 20, v3, TokenInformationLength);
      v7[2] = TokenInformationLength + 20;
      Size = v4;
      v9 = (struct _ACL *)operator new(v4);
      v10 = v9;
      if ( v9 )
      {
        if ( RtlCreateAcl(v9, v4, 2u) >= 0
          && RtlAddAccessAllowedAceEx(v10, 2u, 0, 0x1F0001u, pSid) >= 0
          && RtlAddAccessAllowedAceEx(v10, 2u, 0, 0x1F0001u, v3) >= 0
          && (memcpy_0((char *)v7 + 2 * TokenInformationLength + 20, v10, Size),
              v7[4] = 2 * TokenInformationLength + 20,
              RtlValidRelativeSecurityDescriptor(v7, v5, 7u)) )
        {
          v2 = 1;
          g_SizeSD = v5;
          memcpy_0(&g_RuntimeSD, v7, v5);
        }
        else
        {
          v2 = 0;
        }
        operator delete(v7);
        operator delete(v10);
        goto LABEL_18;
      }
      operator delete(v7);
    }
    CloseHandle(TokenHandle[0]);
    return 0;
  }
  v2 = 0;
LABEL_18:
  CloseHandle(TokenHandle[0]);
  return v2;
}

```

## disassembly

```asm
0x18000fb6c  push    rbp
0x18000fb6e  push    rsi
0x18000fb6f  push    rdi
0x18000fb70  push    r12
0x18000fb72  push    r13
0x18000fb74  push    r14
0x18000fb76  push    r15
0x18000fb78  sub     rsp, 70h
0x18000fb7c  lea     rbp, [rsp+30h]
0x18000fb81  mov     rax, cs:__security_cookie
0x18000fb88  xor     rax, rbp
0x18000fb8b  mov     [rbp+70h+var_40], rax
0x18000fb8f  mov     [rbp+70h+TokenHandle], 0
0x18000fb97  test    ecx, ecx
0x18000fb99  jz      short loc_18000FBA7
0x18000fb9b  cmp     ecx, 3F0h
0x18000fba1  jnz     loc_18000FDA7
0x18000fba7  call    cs:__imp_GetCurrentProcess
0x18000fbad  mov     rcx, rax; ProcessHandle
0x18000fbb0  lea     r8, [rbp+70h+TokenHandle]; TokenHandle
0x18000fbb4  mov     edx, 8; DesiredAccess
0x18000fbb9  call    cs:__imp_NtOpenProcessToken
0x18000fbbf  test    eax, eax
0x18000fbc1  js      loc_18000FDA7
0x18000fbc7  mov     edi, 1
0x18000fbcc  lea     r9d, [rdi+57h]
0x18000fbd0  mov     [rbp+70h+TokenInformationLength], r9d
0x18000fbd4  mov     eax, [rsp+0A0h+var_A0]
0x18000fbd7  sub     rsp, 60h
0x18000fbdb  lea     rsi, [rsp+100h+TokenInformation]
0x18000fbe0  mov     eax, [rsi]
0x18000fbe2  mov     [rbp+70h+var_60], rsi
0x18000fbe6  jmp     short loc_18000FBFB
0x18000fbe8  mov     ecx, eax; unsigned int
0x18000fbea  call    ?PerfpExceptionHandler@@YAXK@Z; PerfpExceptionHandler(ulong)
0x18000fbef  xor     esi, esi
0x18000fbf1  mov     [rbp+70h+var_60], rsi
0x18000fbf5  xor     edi, edi
0x18000fbf7  mov     r9d, [rbp+70h+TokenInformationLength]; TokenInformationLength
0x18000fbfb  test    edi, edi
0x18000fbfd  jz      loc_18000FD9B
0x18000fc03  lea     rax, [rbp+70h+TokenInformationLength]
0x18000fc07  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18000fc0c  mov     r8, rsi; TokenInformation
0x18000fc0f  mov     edx, 1; TokenInformationClass
0x18000fc14  mov     rcx, [rbp+70h+TokenHandle]; TokenHandle
0x18000fc18  call    cs:__imp_NtQueryInformationToken
0x18000fc1e  test    eax, eax
0x18000fc20  jns     short loc_18000FC29
0x18000fc22  xor     edi, edi
0x18000fc24  jmp     loc_18000FD9B
0x18000fc29  mov     [rbp+70h+pSid], 101h
0x18000fc30  mov     [rbp+70h+var_4C], 5000000h
0x18000fc37  mov     [rbp+70h+var_48], 12h
0x18000fc3e  mov     r12, [rsi]
0x18000fc41  mov     rcx, r12; Sid
0x18000fc44  call    cs:__imp_RtlLengthSid
0x18000fc4a  mov     [rbp+70h+TokenInformationLength], eax
0x18000fc4d  lea     edi, [rax+24h]
0x18000fc50  lea     eax, [rax+0Ah]
0x18000fc53  lea     r15d, [rdi+rax*2]
0x18000fc57  mov     r13d, r15d
0x18000fc5a  mov     ecx, r15d
0x18000fc5d  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000fc62  mov     rsi, rax
0x18000fc65  test    rax, rax
0x18000fc68  jnz     short loc_18000FC7B
0x18000fc6a  mov     rcx, [rbp+70h+TokenHandle]; hObject
0x18000fc6e  call    cs:__imp_CloseHandle
0x18000fc74  xor     eax, eax
0x18000fc76  jmp     loc_18000FDAB
0x18000fc7b  mov     byte ptr [rax], 1
0x18000fc7e  mov     word ptr [rax+2], 8004h
0x18000fc84  mov     r8d, [rbp+70h+TokenInformationLength]; Size
0x18000fc88  lea     rcx, [rax+14h]; void *
0x18000fc8c  mov     rdx, r12; Src
0x18000fc8f  call    memcpy_0
0x18000fc94  mov     dword ptr [rsi+4], 14h
0x18000fc9b  mov     r8d, [rbp+70h+TokenInformationLength]; Size
0x18000fc9f  lea     rcx, [r8+14h]
0x18000fca3  add     rcx, rsi; void *
0x18000fca6  mov     rdx, r12; Src
0x18000fca9  call    memcpy_0
0x18000fcae  mov     eax, [rbp+70h+TokenInformationLength]
0x18000fcb1  add     eax, 14h
0x18000fcb4  mov     [rsi+8], eax
0x18000fcb7  mov     eax, edi
0x18000fcb9  mov     [rbp+70h+Size], rax
0x18000fcbd  mov     ecx, edi
0x18000fcbf  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000fcc4  mov     r14, rax
0x18000fcc7  test    rax, rax
0x18000fcca  jnz     short loc_18000FCD6
0x18000fccc  mov     rcx, rsi; Block
0x18000fccf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fcd4  jmp     short loc_18000FC6A
0x18000fcd6  mov     r8d, 2; AclRevision
0x18000fcdc  mov     edx, edi; AclSize
0x18000fcde  mov     rcx, r14; Acl
0x18000fce1  call    cs:__imp_RtlCreateAcl
0x18000fce7  test    eax, eax
0x18000fce9  js      loc_18000FD89
0x18000fcef  lea     rax, [rbp+70h+pSid]
0x18000fcf3  mov     [rsp+100h+ReturnLength], rax; pSid
0x18000fcf8  mov     r9d, 1F0001h; AccessMask
0x18000fcfe  xor     r8d, r8d; AceFlags
0x18000fd01  lea     edi, [r8+2]
0x18000fd05  mov     edx, edi; dwAceRevision
0x18000fd07  mov     rcx, r14; pAcl
0x18000fd0a  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18000fd10  test    eax, eax
0x18000fd12  js      short loc_18000FD89
0x18000fd14  mov     [rsp+100h+ReturnLength], r12; pSid
0x18000fd19  mov     r9d, 1F0001h; AccessMask
0x18000fd1f  xor     r8d, r8d; AceFlags
0x18000fd22  mov     edx, edi; dwAceRevision
0x18000fd24  mov     rcx, r14; pAcl
0x18000fd27  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18000fd2d  test    eax, eax
0x18000fd2f  js      short loc_18000FD89
0x18000fd31  mov     eax, [rbp+70h+TokenInformationLength]
0x18000fd34  add     rax, 0Ah
0x18000fd38  lea     rcx, [rsi+rax*2]; void *
0x18000fd3c  mov     r8, [rbp+70h+Size]; Size
0x18000fd40  mov     rdx, r14; Src
0x18000fd43  call    memcpy_0
0x18000fd48  mov     eax, [rbp+70h+TokenInformationLength]
0x18000fd4b  lea     eax, ds:14h[rax*2]
0x18000fd52  mov     [rsi+10h], eax
0x18000fd55  lea     r8d, [rdi+5]; RequiredInformation
0x18000fd59  mov     edx, r15d; SecurityDescriptorLength
0x18000fd5c  mov     rcx, rsi; SecurityDescriptorInput
0x18000fd5f  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18000fd65  test    al, al
0x18000fd67  jz      short loc_18000FD89
0x18000fd69  mov     edi, 1
0x18000fd6e  mov     cs:?g_SizeSD@@3KA, r15d; ulong g_SizeSD
0x18000fd75  mov     r8, r13; Size
0x18000fd78  mov     rdx, rsi; Src
0x18000fd7b  lea     rcx, ?g_RuntimeSD@@3PAKA; void *
0x18000fd82  call    memcpy_0
0x18000fd87  jmp     short loc_18000FD8B
0x18000fd89  xor     edi, edi
0x18000fd8b  mov     rcx, rsi; Block
0x18000fd8e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fd93  mov     rcx, r14; Block
0x18000fd96  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fd9b  mov     rcx, [rbp+70h+TokenHandle]; hObject
0x18000fd9f  call    cs:__imp_CloseHandle
0x18000fda5  jmp     short loc_18000FDA9
0x18000fda7  xor     edi, edi
0x18000fda9  mov     eax, edi
0x18000fdab  mov     rcx, [rbp+70h+var_40]
0x18000fdaf  xor     rcx, rbp; StackCookie
0x18000fdb2  call    __security_check_cookie
0x18000fdb7  lea     rsp, [rbp+40h]
0x18000fdbb  pop     r15
0x18000fdbd  pop     r14
0x18000fdbf  pop     r13
0x18000fdc1  pop     r12
0x18000fdc3  pop     rdi
0x18000fdc4  pop     rsi
0x18000fdc5  pop     rbp
0x18000fdc6  retn
0x18001e601  push    rbp
0x18001e603  sub     rsp, 30h
0x18001e607  lea     rbp, [rdx+30h]
0x18001e60b  mov     rax, [rcx]
0x18001e60e  xor     ecx, ecx
0x18001e610  cmp     dword ptr [rax], 0C00000FDh
0x18001e616  setz    cl
0x18001e619  mov     eax, ecx
0x18001e61b  add     rsp, 30h
0x18001e61f  pop     rbp
0x18001e620  retn
```
