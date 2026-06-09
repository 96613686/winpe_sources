# QueryTokenIntegrityLevel(void *,ulong *)

- ea: `0x180024058`
- end: `0x1800241e1`
- name: `?QueryTokenIntegrityLevel@@YAJPEAXPEAK@Z`
- size: `393`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023f3c`

## callees

- `0x180002da0`
- `0x1800034f0`
- `0x180024058`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800240fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024171`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800240fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024171`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002419e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002419e`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002413b`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002413b`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800240db`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800240db`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024161`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024161`

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
0x180024058  mov     [rsp-8+arg_10], rbx
0x18002405d  push    rbp
0x18002405e  push    rsi
0x18002405f  push    rdi
0x180024060  lea     rbp, [rsp-80h]
0x180024065  sub     rsp, 180h
0x18002406c  mov     rax, cs:__security_cookie
0x180024073  xor     rax, rsp
0x180024076  mov     [rbp+90h+var_20], rax
0x18002407a  mov     rdi, rdx
0x18002407d  mov     rsi, rcx
0x180024080  test    rcx, rcx
0x180024083  jz      loc_1800241BC
0x180024089  test    rdx, rdx
0x18002408c  jz      loc_1800241BC
0x180024092  xor     edx, edx; Val
0x180024094  mov     [rsp+190h+TokenInformationLength], 0
0x18002409c  mov     r8d, 0FFh; Size
0x1800240a2  mov     dword ptr [rsp+190h+pIdentifierAuthority.Value], 0
0x1800240aa  lea     rcx, [rsp+190h+var_11F]; void *
0x1800240af  mov     word ptr [rsp+190h+pIdentifierAuthority.Value+4], 1000h
0x1800240b6  call    memset_0
0x1800240bb  lea     rax, [rsp+190h+var_120]
0x1800240c0  mov     [rsp+190h+var_120], 0
0x1800240c5  mov     cl, 1; nSubAuthorityCount
0x1800240c7  mov     [rsp+190h+TokenInformation], rax
0x1800240cc  mov     [rsp+190h+var_130], 100h
0x1800240d4  mov     [rsp+190h+var_12C], 100h
0x1800240db  call    cs:__imp_GetSidLengthRequired
0x1800240e2  nop     dword ptr [rax+rax+00h]
0x1800240e7  add     eax, 10h
0x1800240ea  lea     rcx, [rsp+190h+var_158]; this
0x1800240ef  mov     edx, eax; unsigned int
0x1800240f1  mov     [rsp+190h+TokenInformationLength], eax
0x1800240f5  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800240fa  test    al, al
0x1800240fc  jnz     short loc_18002411B
0x1800240fe  call    cs:__imp_GetLastError
0x180024105  nop     dword ptr [rax+rax+00h]
0x18002410a  mov     ebx, eax
0x18002410c  test    eax, eax
0x18002410e  jle     short loc_18002418B
0x180024110  movzx   ebx, ax
0x180024113  or      ebx, 80070000h
0x180024119  jmp     short loc_18002418B
0x18002411b  mov     rbx, [rsp+190h+TokenInformation]
0x180024120  test    rbx, rbx
0x180024123  jnz     short loc_18002412C
0x180024125  mov     ebx, 80070008h
0x18002412a  jmp     short loc_18002418B
0x18002412c  lea     rcx, [rbx+10h]; Sid
0x180024130  mov     r8b, 1; nSubAuthorityCount
0x180024133  lea     rdx, [rsp+190h+pIdentifierAuthority]; pIdentifierAuthority
0x180024138  mov     [rbx], rcx
0x18002413b  call    cs:__imp_InitializeSid
0x180024142  nop     dword ptr [rax+rax+00h]
0x180024147  mov     r9d, [rsp+190h+TokenInformationLength]; TokenInformationLength
0x18002414c  lea     rax, [rsp+190h+TokenInformationLength]
0x180024151  mov     r8, rbx; TokenInformation
0x180024154  mov     [rsp+190h+ReturnLength], rax; ReturnLength
0x180024159  mov     edx, 19h; TokenInformationClass
0x18002415e  mov     rcx, rsi; TokenHandle
0x180024161  call    cs:__imp_GetTokenInformation
0x180024168  nop     dword ptr [rax+rax+00h]
0x18002416d  test    eax, eax
0x18002416f  jnz     short loc_180024199
0x180024171  call    cs:__imp_GetLastError
0x180024178  nop     dword ptr [rax+rax+00h]
0x18002417d  test    eax, eax
0x18002417f  jle     short loc_180024189
0x180024181  movzx   eax, ax
0x180024184  or      eax, 80070000h
0x180024189  mov     ebx, eax
0x18002418b  lea     rcx, [rsp+190h+var_158]; this
0x180024190  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024195  mov     eax, ebx
0x180024197  jmp     short loc_1800241C1
0x180024199  mov     rcx, [rbx]; pSid
0x18002419c  xor     edx, edx; nSubAuthority
0x18002419e  call    cs:__imp_GetSidSubAuthority
0x1800241a5  nop     dword ptr [rax+rax+00h]
0x1800241aa  mov     ecx, [rax]
0x1800241ac  mov     [rdi], ecx
0x1800241ae  lea     rcx, [rsp+190h+var_158]; this
0x1800241b3  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800241b8  xor     eax, eax
0x1800241ba  jmp     short loc_1800241C1
0x1800241bc  mov     eax, 80070057h
0x1800241c1  mov     rcx, [rbp+90h+var_20]
0x1800241c5  xor     rcx, rsp; StackCookie
0x1800241c8  call    __security_check_cookie
0x1800241cd  mov     rbx, [rsp+190h+arg_10]
0x1800241d5  add     rsp, 180h
0x1800241dc  pop     rdi
0x1800241dd  pop     rsi
0x1800241de  pop     rbp
0x1800241df  retn
```
