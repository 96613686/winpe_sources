# QueryTokenIntegrityLevel(void *,ulong *)

- ea: `0x18002286c`
- end: `0x1800229d0`
- name: `?QueryTokenIntegrityLevel@@YAJPEAXPEAK@Z`
- size: `356`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022770`

## callees

- `0x180002470`
- `0x180002b60`
- `0x18002286c`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002290c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002296d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002290c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002296d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180022994`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180022994`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180022943`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180022943`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800228ef`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800228ef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022963`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022963`

## pseudocode

```c
__int64 __fastcall QueryTokenIntegrityLevel(HANDLE TokenHandle, unsigned int *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  PSID *v6; // rbx
  char *v7; // rcx
  signed int v8; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v11[32]; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID TokenInformation; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+60h] [rbp-A0h]
  __int16 v14; // [rsp+64h] [rbp-9Ch]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-98h] BYREF
  char v16; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v17[255]; // [rsp+71h] [rbp-8Fh] BYREF

  if ( !TokenHandle || !a2 )
    return 2147942487LL;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  memset_0(v17, 0, sizeof(v17));
  v16 = 0;
  TokenInformation = &v16;
  v13 = 256;
  v14 = 256;
  TokenInformationLength = GetSidLengthRequired(1u) + 16;
  if ( !BUFFER::Resize((BUFFER *)v11, TokenInformationLength) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_12;
  }
  v6 = (PSID *)TokenInformation;
  if ( !TokenInformation )
  {
    v5 = -2147024888;
LABEL_12:
    BUFFER::~BUFFER((BUFFER *)v11);
    return v5;
  }
  v7 = (char *)TokenInformation + 16;
  *(_QWORD *)TokenInformation = (char *)TokenInformation + 16;
  InitializeSid(v7, &pIdentifierAuthority, 1u);
  if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, v6, TokenInformationLength, &TokenInformationLength) )
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v5 = v8;
    goto LABEL_12;
  }
  *a2 = *GetSidSubAuthority(*v6, 0);
  BUFFER::~BUFFER((BUFFER *)v11);
  return 0;
}

```

## disassembly

```asm
0x18002286c  mov     [rsp-8+arg_10], rbx
0x180022871  push    rbp
0x180022872  push    rsi
0x180022873  push    rdi
0x180022874  lea     rbp, [rsp-80h]
0x180022879  sub     rsp, 180h
0x180022880  mov     rax, cs:__security_cookie
0x180022887  xor     rax, rsp
0x18002288a  mov     [rbp+90h+var_20], rax
0x18002288e  mov     rdi, rdx
0x180022891  mov     rsi, rcx
0x180022894  test    rcx, rcx
0x180022897  jz      loc_1800229AC
0x18002289d  test    rdx, rdx
0x1800228a0  jz      loc_1800229AC
0x1800228a6  xor     edx, edx; Val
0x1800228a8  mov     [rsp+190h+TokenInformationLength], 0
0x1800228b0  mov     r8d, 0FFh; Size
0x1800228b6  mov     dword ptr [rsp+190h+pIdentifierAuthority.Value], 0
0x1800228be  lea     rcx, [rsp+190h+var_11F]; void *
0x1800228c3  mov     word ptr [rsp+190h+pIdentifierAuthority.Value+4], 1000h
0x1800228ca  call    memset_0
0x1800228cf  lea     rax, [rsp+190h+var_120]
0x1800228d4  mov     [rsp+190h+var_120], 0
0x1800228d9  mov     cl, 1; nSubAuthorityCount
0x1800228db  mov     [rsp+190h+TokenInformation], rax
0x1800228e0  mov     [rsp+190h+var_130], 100h
0x1800228e8  mov     [rsp+190h+var_12C], 100h
0x1800228ef  call    cs:__imp_GetSidLengthRequired
0x1800228f5  add     eax, 10h
0x1800228f8  lea     rcx, [rsp+190h+var_158]; this
0x1800228fd  mov     edx, eax; unsigned int
0x1800228ff  mov     [rsp+190h+TokenInformationLength], eax
0x180022903  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180022908  test    al, al
0x18002290a  jnz     short loc_180022923
0x18002290c  call    cs:__imp_GetLastError
0x180022912  mov     ebx, eax
0x180022914  test    eax, eax
0x180022916  jle     short loc_180022981
0x180022918  movzx   ebx, ax
0x18002291b  or      ebx, 80070000h
0x180022921  jmp     short loc_180022981
0x180022923  mov     rbx, [rsp+190h+TokenInformation]
0x180022928  test    rbx, rbx
0x18002292b  jnz     short loc_180022934
0x18002292d  mov     ebx, 80070008h
0x180022932  jmp     short loc_180022981
0x180022934  lea     rcx, [rbx+10h]; Sid
0x180022938  mov     r8b, 1; nSubAuthorityCount
0x18002293b  lea     rdx, [rsp+190h+pIdentifierAuthority]; pIdentifierAuthority
0x180022940  mov     [rbx], rcx
0x180022943  call    cs:__imp_InitializeSid
0x180022949  mov     r9d, [rsp+190h+TokenInformationLength]; TokenInformationLength
0x18002294e  lea     rax, [rsp+190h+TokenInformationLength]
0x180022953  mov     r8, rbx; TokenInformation
0x180022956  mov     [rsp+190h+ReturnLength], rax; ReturnLength
0x18002295b  mov     edx, 19h; TokenInformationClass
0x180022960  mov     rcx, rsi; TokenHandle
0x180022963  call    cs:__imp_GetTokenInformation
0x180022969  test    eax, eax
0x18002296b  jnz     short loc_18002298F
0x18002296d  call    cs:__imp_GetLastError
0x180022973  test    eax, eax
0x180022975  jle     short loc_18002297F
0x180022977  movzx   eax, ax
0x18002297a  or      eax, 80070000h
0x18002297f  mov     ebx, eax
0x180022981  lea     rcx, [rsp+190h+var_158]; this
0x180022986  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002298b  mov     eax, ebx
0x18002298d  jmp     short loc_1800229B1
0x18002298f  mov     rcx, [rbx]; pSid
0x180022992  xor     edx, edx; nSubAuthority
0x180022994  call    cs:__imp_GetSidSubAuthority
0x18002299a  mov     ecx, [rax]
0x18002299c  mov     [rdi], ecx
0x18002299e  lea     rcx, [rsp+190h+var_158]; this
0x1800229a3  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800229a8  xor     eax, eax
0x1800229aa  jmp     short loc_1800229B1
0x1800229ac  mov     eax, 80070057h
0x1800229b1  mov     rcx, [rbp+90h+var_20]
0x1800229b5  xor     rcx, rsp; StackCookie
0x1800229b8  call    __security_check_cookie
0x1800229bd  mov     rbx, [rsp+190h+arg_10]
0x1800229c5  add     rsp, 180h
0x1800229cc  pop     rdi
0x1800229cd  pop     rsi
0x1800229ce  pop     rbp
0x1800229cf  retn
```
