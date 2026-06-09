# GetUserTextualSid

- ea: `0x18000d130`
- end: `0x18000d4ad`
- name: `GetUserTextualSid`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800285dc`

## callees

- `0x18000d130`
- `0x18001d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d256`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d411`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d256`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000d411`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000d276`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000d276`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000d2aa`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000d2aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d199`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d44c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d199`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000d44c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d17a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d42d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d17a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000d42d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d2d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d381`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d477`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d2d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d381`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d477`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d28c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d3dd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d28c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d3dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d488`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d488`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000d320`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000d320`

## pseudocode

```c
__int64 __fastcall GetUserTextualSid(void *a1, _WORD *a2)
{
  HANDLE v2; // rdi
  HLOCAL v4; // r14
  unsigned int v5; // esi
  HANDLE CurrentThread; // rax
  int v8; // ebp
  void *v9; // r13
  HANDLE v10; // rcx
  PSID *v11; // r12
  DWORD LengthSid; // r15d
  HLOCAL v13; // rax
  void *v14; // rsi
  int v15; // edi
  BOOL v16; // eax
  LPWSTR v17; // r9
  __int64 v18; // rcx
  LPWSTR v19; // rdx
  __int64 v20; // r8
  _WORD *v21; // rdx
  HANDLE v22; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-178h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-174h]
  HANDLE hObject; // [rsp+38h] [rbp-170h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-168h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-160h] BYREF
  void *v28; // [rsp+50h] [rbp-158h]
  _BYTE TokenInformation[256]; // [rsp+60h] [rbp-148h] BYREF

  v2 = a1;
  v4 = 0;
  v28 = a1;
  TokenHandle = 0;
  v5 = 0;
  v24 = 0;
  if ( a1 )
  {
    TokenHandle = a1;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      goto LABEL_3;
    v2 = TokenHandle;
  }
  v8 = 0;
  v9 = 0;
  TokenInformationLength = 0;
  hObject = 0;
  if ( v2 )
  {
    v10 = v2;
    hObject = v2;
  }
  else
  {
    v22 = GetCurrentThread();
    if ( !OpenThreadToken(v22, 8u, 1, &hObject) )
      goto LABEL_16;
    v10 = hObject;
  }
  TokenInformationLength = 256;
  v11 = (PSID *)TokenInformation;
  if ( GetTokenInformation(v10, TokenUser, TokenInformation, 0x100u, &TokenInformationLength) || GetLastError() != 122 )
    goto LABEL_11;
  v4 = LocalAlloc(0x40u, TokenInformationLength);
  if ( v4 )
  {
    if ( !GetTokenInformation(hObject, TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
    {
LABEL_15:
      LocalFree(v4);
      goto LABEL_16;
    }
    v11 = (PSID *)v4;
LABEL_11:
    LengthSid = GetLengthSid(*v11);
    v13 = LocalAlloc(0x40u, LengthSid);
    v14 = v13;
    if ( v13 )
    {
      if ( CopySid(LengthSid, v13, *v11) )
      {
        v9 = v14;
        v8 = 1;
      }
      else
      {
        LocalFree(v14);
      }
    }
    if ( !v4 )
      goto LABEL_16;
    goto LABEL_15;
  }
LABEL_16:
  if ( hObject && hObject != v2 )
    CloseHandle(hObject);
  if ( !v8 )
    goto LABEL_32;
  StringSid = 0;
  v15 = 0;
  v16 = ConvertSidToStringSidW(v9, &StringSid);
  v17 = StringSid;
  if ( v16 )
  {
    v18 = 2147483646;
    v19 = StringSid;
    v20 = 261;
    do
    {
      if ( !v18 )
        break;
      if ( !*v19 )
        break;
      *a2++ = *v19++;
      --v18;
      --v20;
    }
    while ( v20 );
    v21 = a2 - 1;
    if ( v20 )
      v21 = a2;
    *v21 = 0;
    if ( v20 )
      v15 = 1;
  }
  if ( v17 )
    LocalFree(v17);
  if ( v15 )
    v5 = 1;
  else
LABEL_32:
    v5 = v24;
  if ( v9 )
    LocalFree(v9);
  v2 = v28;
LABEL_3:
  if ( TokenHandle && TokenHandle != v2 )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x18000d130  mov     r11, rsp
0x18000d133  push    rsi
0x18000d134  push    rdi
0x18000d135  sub     rsp, 198h
0x18000d13c  mov     rax, cs:__security_cookie
0x18000d143  xor     rax, rsp
0x18000d146  mov     [rsp+1A8h+var_48], rax
0x18000d14e  mov     [r11+18h], rbx
0x18000d152  mov     rdi, rcx
0x18000d155  mov     [r11-30h], r14
0x18000d159  mov     rbx, rdx
0x18000d15c  xor     r14d, r14d
0x18000d15f  mov     [rsp+1A8h+var_158], rcx
0x18000d164  mov     [rsp+1A8h+TokenHandle], r14
0x18000d169  mov     esi, r14d
0x18000d16c  mov     [rsp+1A8h+var_174], r14d
0x18000d171  test    rcx, rcx
0x18000d174  jnz     loc_18000D46A
0x18000d17a  call    cs:__imp_GetCurrentThread
0x18000d181  nop     dword ptr [rax+rax+00h]
0x18000d186  lea     r9, [rsp+1A8h+TokenHandle]; TokenHandle
0x18000d18b  mov     edx, 8; DesiredAccess
0x18000d190  mov     rcx, rax; ThreadHandle
0x18000d193  mov     r8d, 1; OpenAsSelf
0x18000d199  call    cs:__imp_OpenThreadToken
0x18000d1a0  nop     dword ptr [rax+rax+00h]
0x18000d1a5  test    eax, eax
0x18000d1a7  jnz     short loc_18000D1F1
0x18000d1a9  mov     rcx, [rsp+1A8h+TokenHandle]; hObject
0x18000d1ae  mov     r14, [rsp+1A8h+var_30]
0x18000d1b6  mov     rbx, [rsp+1A8h+arg_10]
0x18000d1be  test    rcx, rcx
0x18000d1c1  jz      short loc_18000D1D4
0x18000d1c3  cmp     rcx, rdi
0x18000d1c6  jz      short loc_18000D1D4
0x18000d1c8  call    cs:__imp_CloseHandle
0x18000d1cf  nop     dword ptr [rax+rax+00h]
0x18000d1d4  mov     eax, esi
0x18000d1d6  mov     rcx, [rsp+1A8h+var_48]
0x18000d1de  xor     rcx, rsp; StackCookie
0x18000d1e1  call    __security_check_cookie
0x18000d1e6  add     rsp, 198h
0x18000d1ed  pop     rdi
0x18000d1ee  pop     rsi
0x18000d1ef  retn
0x18000d1f1  mov     rdi, [rsp+1A8h+TokenHandle]
0x18000d1f6  mov     [rsp+1A8h+var_18], rbp
0x18000d1fe  mov     ebp, r14d
0x18000d201  mov     [rsp+1A8h+var_28], r13
0x18000d209  mov     r13, r14
0x18000d20c  mov     [rsp+1A8h+TokenInformationLength], r14d
0x18000d211  mov     [rsp+1A8h+hObject], r14
0x18000d216  test    rdi, rdi
0x18000d219  jz      loc_18000D42D
0x18000d21f  mov     rcx, rdi; TokenHandle
0x18000d222  mov     [rsp+1A8h+hObject], rcx
0x18000d227  lea     rax, [rsp+1A8h+TokenInformationLength]
0x18000d22c  mov     [rsp+1A8h+var_20], r12
0x18000d234  mov     r9d, 100h; TokenInformationLength
0x18000d23a  mov     [rsp+1A8h+ReturnLength], rax; ReturnLength
0x18000d23f  lea     r8, [rsp+1A8h+TokenInformation]; TokenInformation
0x18000d244  mov     [rsp+1A8h+TokenInformationLength], 100h
0x18000d24c  mov     edx, 1; TokenInformationClass
0x18000d251  lea     r12, [rsp+1A8h+TokenInformation]
0x18000d256  call    cs:__imp_GetTokenInformation
0x18000d25d  nop     dword ptr [rax+rax+00h]
0x18000d262  test    eax, eax
0x18000d264  jz      loc_18000D3BF
0x18000d26a  mov     rcx, [r12]; pSid
0x18000d26e  mov     [rsp+1A8h+var_38], r15
0x18000d276  call    cs:__imp_GetLengthSid
0x18000d27d  nop     dword ptr [rax+rax+00h]
0x18000d282  mov     edx, eax; uBytes
0x18000d284  mov     ecx, 40h ; '@'; uFlags
0x18000d289  mov     r15d, eax
0x18000d28c  call    cs:__imp_LocalAlloc
0x18000d293  nop     dword ptr [rax+rax+00h]
0x18000d298  mov     rsi, rax
0x18000d29b  test    rax, rax
0x18000d29e  jz      short loc_18000D2C6
0x18000d2a0  mov     r8, [r12]; pSourceSid
0x18000d2a4  mov     rdx, rax; pDestinationSid
0x18000d2a7  mov     ecx, r15d; nDestinationSidLength
0x18000d2aa  call    cs:__imp_CopySid
0x18000d2b1  nop     dword ptr [rax+rax+00h]
0x18000d2b6  test    eax, eax
0x18000d2b8  jz      loc_18000D474
0x18000d2be  mov     r13, rsi
0x18000d2c1  mov     ebp, 1
0x18000d2c6  mov     r15, [rsp+1A8h+var_38]
0x18000d2ce  test    r14, r14
0x18000d2d1  jz      short loc_18000D2E2
0x18000d2d3  mov     rcx, r14; hMem
0x18000d2d6  call    cs:__imp_LocalFree
0x18000d2dd  nop     dword ptr [rax+rax+00h]
0x18000d2e2  mov     r12, [rsp+1A8h+var_20]
0x18000d2ea  xor     r14d, r14d
0x18000d2ed  mov     rcx, [rsp+1A8h+hObject]; hObject
0x18000d2f2  test    rcx, rcx
0x18000d2f5  jz      short loc_18000D300
0x18000d2f7  cmp     rcx, rdi
0x18000d2fa  jnz     loc_18000D488
0x18000d300  test    ebp, ebp
0x18000d302  mov     rbp, [rsp+1A8h+var_18]
0x18000d30a  jz      loc_18000D395
0x18000d310  lea     rdx, [rsp+1A8h+StringSid]; StringSid
0x18000d315  mov     [rsp+1A8h+StringSid], r14
0x18000d31a  mov     rcx, r13; Sid
0x18000d31d  mov     edi, r14d
0x18000d320  call    cs:__imp_ConvertSidToStringSidW
0x18000d327  nop     dword ptr [rax+rax+00h]
0x18000d32c  mov     r9, [rsp+1A8h+StringSid]
0x18000d331  test    eax, eax
0x18000d333  jz      short loc_18000D379
0x18000d335  mov     ecx, 7FFFFFFEh
0x18000d33a  mov     rdx, r9
0x18000d33d  mov     r8d, 105h
0x18000d343  test    rcx, rcx
0x18000d346  jz      short loc_18000D364
0x18000d348  movzx   eax, word ptr [rdx]
0x18000d34b  test    ax, ax
0x18000d34e  jz      short loc_18000D364
0x18000d350  mov     [rbx], ax
0x18000d353  add     rdx, 2
0x18000d357  add     rbx, 2
0x18000d35b  dec     rcx
0x18000d35e  sub     r8, 1
0x18000d362  jnz     short loc_18000D343
0x18000d364  test    r8, r8
0x18000d367  lea     rdx, [rbx-2]
0x18000d36b  cmovnz  rdx, rbx
0x18000d36f  mov     [rdx], r14w
0x18000d373  jnz     loc_18000D499
0x18000d379  test    r9, r9
0x18000d37c  jz      short loc_18000D38D
0x18000d37e  mov     rcx, r9; hMem
0x18000d381  call    cs:__imp_LocalFree
0x18000d388  nop     dword ptr [rax+rax+00h]
0x18000d38d  test    edi, edi
0x18000d38f  jnz     loc_18000D4A3
0x18000d395  mov     esi, [rsp+1A8h+var_174]
0x18000d399  test    r13, r13
0x18000d39c  jz      short loc_18000D3AD
0x18000d39e  mov     rcx, r13; hMem
0x18000d3a1  call    cs:__imp_LocalFree
0x18000d3a8  nop     dword ptr [rax+rax+00h]
0x18000d3ad  mov     rdi, [rsp+1A8h+var_158]
0x18000d3b2  mov     r13, [rsp+1A8h+var_28]
0x18000d3ba  jmp     loc_18000D1A9
0x18000d3bf  call    cs:__imp_GetLastError
0x18000d3c6  nop     dword ptr [rax+rax+00h]
0x18000d3cb  cmp     eax, 7Ah ; 'z'
0x18000d3ce  jnz     loc_18000D26A
0x18000d3d4  mov     edx, [rsp+1A8h+TokenInformationLength]; uBytes
0x18000d3d8  mov     ecx, 40h ; '@'; uFlags
0x18000d3dd  call    cs:__imp_LocalAlloc
0x18000d3e4  nop     dword ptr [rax+rax+00h]
0x18000d3e9  mov     r14, rax
0x18000d3ec  test    rax, rax
0x18000d3ef  jz      loc_18000D2E2
0x18000d3f5  mov     r9d, [rsp+1A8h+TokenInformationLength]; TokenInformationLength
0x18000d3fa  lea     rax, [rsp+1A8h+TokenInformationLength]
0x18000d3ff  mov     rcx, [rsp+1A8h+hObject]; TokenHandle
0x18000d404  mov     r8, r14; TokenInformation
0x18000d407  mov     edx, 1; TokenInformationClass
0x18000d40c  mov     [rsp+1A8h+ReturnLength], rax; ReturnLength
0x18000d411  call    cs:__imp_GetTokenInformation
0x18000d418  nop     dword ptr [rax+rax+00h]
0x18000d41d  test    eax, eax
0x18000d41f  jz      loc_18000D2D3
0x18000d425  mov     r12, r14
0x18000d428  jmp     loc_18000D26A
0x18000d42d  call    cs:__imp_GetCurrentThread
0x18000d434  nop     dword ptr [rax+rax+00h]
0x18000d439  lea     r9, [rsp+1A8h+hObject]; TokenHandle
0x18000d43e  mov     edx, 8; DesiredAccess
0x18000d443  mov     rcx, rax; ThreadHandle
0x18000d446  mov     r8d, 1; OpenAsSelf
0x18000d44c  call    cs:__imp_OpenThreadToken
0x18000d453  nop     dword ptr [rax+rax+00h]
0x18000d458  test    eax, eax
0x18000d45a  jz      loc_18000D2ED
0x18000d460  mov     rcx, [rsp+1A8h+hObject]
0x18000d465  jmp     loc_18000D227
0x18000d46a  mov     [rsp+1A8h+TokenHandle], rcx
0x18000d46f  jmp     loc_18000D1F6
0x18000d474  mov     rcx, rsi; hMem
0x18000d477  call    cs:__imp_LocalFree
0x18000d47e  nop     dword ptr [rax+rax+00h]
0x18000d483  jmp     loc_18000D2C6
0x18000d488  call    cs:__imp_CloseHandle
0x18000d48f  nop     dword ptr [rax+rax+00h]
0x18000d494  jmp     loc_18000D300
0x18000d499  mov     edi, 1
0x18000d49e  jmp     loc_18000D379
0x18000d4a3  mov     esi, 1
0x18000d4a8  jmp     loc_18000D399
```
