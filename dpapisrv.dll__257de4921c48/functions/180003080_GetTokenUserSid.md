# GetTokenUserSid

- ea: `0x180003080`
- end: `0x1800032ae`
- name: `GetTokenUserSid`
- size: `558`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002d90`
- `0x180002f18`
- `0x180003b98`
- `0x180014c80`
- `0x180024f38`
- `0x18002658c`
- `0x180028900`
- `0x180028b1c`
- `0x180029818`
- `0x18002e310`
- `0x18002fab8`
- `0x18002ffac`
- `0x180036dc0`
- `0x180037ba8`
- `0x180037e98`

## callees

- `0x180003080`
- `0x18001d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800030fb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003230`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800030fb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003230`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003123`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003123`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180003157`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180003157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031e2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000326b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000326b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000324c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000324c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000318c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000328c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000318c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000328c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003139`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003200`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003139`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003200`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000329d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000329d`

## pseudocode

```c
__int64 __fastcall GetTokenUserSid(HANDLE a1, _QWORD *a2)
{
  HANDLE v2; // rbx
  HLOCAL v4; // rdi
  unsigned int v5; // r14d
  PSID *v6; // r12
  DWORD LengthSid; // r15d
  HLOCAL v8; // rax
  void *v9; // rbp
  HANDLE CurrentThread; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-148h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-140h] BYREF
  _BYTE TokenInformation[256]; // [rsp+40h] [rbp-138h] BYREF

  v2 = a1;
  v4 = 0;
  TokenInformationLength = 0;
  v5 = 0;
  TokenHandle = 0;
  *a2 = 0;
  if ( a1 )
  {
    TokenHandle = a1;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      goto LABEL_9;
    a1 = TokenHandle;
  }
  TokenInformationLength = 256;
  v6 = (PSID *)TokenInformation;
  if ( !GetTokenInformation(a1, TokenUser, TokenInformation, 0x100u, &TokenInformationLength) && GetLastError() == 122 )
  {
    v4 = LocalAlloc(0x40u, TokenInformationLength);
    if ( !v4 )
      goto LABEL_9;
    if ( !GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_8;
    v6 = (PSID *)v4;
  }
  LengthSid = GetLengthSid(*v6);
  v8 = LocalAlloc(0x40u, LengthSid);
  v9 = v8;
  if ( v8 )
  {
    if ( CopySid(LengthSid, v8, *v6) )
    {
      *a2 = v9;
      v5 = 1;
    }
    else
    {
      LocalFree(v9);
    }
  }
  if ( v4 )
LABEL_8:
    LocalFree(v4);
LABEL_9:
  if ( TokenHandle && TokenHandle != v2 )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x180003080  mov     r11, rsp
0x180003083  push    rbx
0x180003084  push    r14
0x180003086  sub     rsp, 168h
0x18000308d  mov     rax, cs:__security_cookie
0x180003094  xor     rax, rsp
0x180003097  mov     [rsp+178h+var_38], rax
0x18000309f  mov     [r11+20h], rsi
0x1800030a3  mov     rbx, rcx
0x1800030a6  mov     [r11-18h], rdi
0x1800030aa  mov     rsi, rdx
0x1800030ad  xor     edi, edi
0x1800030af  mov     [rsp+178h+TokenInformationLength], edi
0x1800030b3  mov     r14d, edi
0x1800030b6  mov     [rsp+178h+TokenHandle], rdi
0x1800030bb  mov     [rdx], rdi
0x1800030be  test    rcx, rcx
0x1800030c1  jz      loc_18000324C
0x1800030c7  mov     [rsp+178h+TokenHandle], rcx
0x1800030cc  lea     rax, [rsp+178h+TokenInformationLength]
0x1800030d1  mov     [rsp+178h+var_20], r12
0x1800030d9  mov     r9d, 100h; TokenInformationLength
0x1800030df  mov     [rsp+178h+ReturnLength], rax; ReturnLength
0x1800030e4  lea     r8, [rsp+178h+TokenInformation]; TokenInformation
0x1800030e9  mov     [rsp+178h+TokenInformationLength], 100h
0x1800030f1  mov     edx, 1; TokenInformationClass
0x1800030f6  lea     r12, [rsp+178h+TokenInformation]
0x1800030fb  call    cs:__imp_GetTokenInformation
0x180003102  nop     dword ptr [rax+rax+00h]
0x180003107  test    eax, eax
0x180003109  jz      loc_1800031E2
0x18000310f  mov     rcx, [r12]; pSid
0x180003113  mov     [rsp+178h+arg_10], rbp
0x18000311b  mov     [rsp+178h+var_28], r15
0x180003123  call    cs:__imp_GetLengthSid
0x18000312a  nop     dword ptr [rax+rax+00h]
0x18000312f  mov     edx, eax; uBytes
0x180003131  mov     ecx, 40h ; '@'; uFlags
0x180003136  mov     r15d, eax
0x180003139  call    cs:__imp_LocalAlloc
0x180003140  nop     dword ptr [rax+rax+00h]
0x180003145  mov     rbp, rax
0x180003148  test    rax, rax
0x18000314b  jz      short loc_180003174
0x18000314d  mov     r8, [r12]; pSourceSid
0x180003151  mov     rdx, rax; pDestinationSid
0x180003154  mov     ecx, r15d; nDestinationSidLength
0x180003157  call    cs:__imp_CopySid
0x18000315e  nop     dword ptr [rax+rax+00h]
0x180003163  test    eax, eax
0x180003165  jz      loc_180003289
0x18000316b  mov     [rsi], rbp
0x18000316e  mov     r14d, 1
0x180003174  mov     r15, [rsp+178h+var_28]
0x18000317c  mov     rbp, [rsp+178h+arg_10]
0x180003184  test    rdi, rdi
0x180003187  jz      short loc_180003198
0x180003189  mov     rcx, rdi; hMem
0x18000318c  call    cs:__imp_LocalFree
0x180003193  nop     dword ptr [rax+rax+00h]
0x180003198  mov     r12, [rsp+178h+var_20]
0x1800031a0  mov     rcx, [rsp+178h+TokenHandle]; hObject
0x1800031a5  mov     rdi, [rsp+178h+var_18]
0x1800031ad  mov     rsi, [rsp+178h+arg_18]
0x1800031b5  test    rcx, rcx
0x1800031b8  jz      short loc_1800031C3
0x1800031ba  cmp     rcx, rbx
0x1800031bd  jnz     loc_18000329D
0x1800031c3  mov     eax, r14d
0x1800031c6  mov     rcx, [rsp+178h+var_38]
0x1800031ce  xor     rcx, rsp; StackCookie
0x1800031d1  call    __security_check_cookie
0x1800031d6  add     rsp, 168h
0x1800031dd  pop     r14
0x1800031df  pop     rbx
0x1800031e0  retn
0x1800031e2  call    cs:__imp_GetLastError
0x1800031e9  nop     dword ptr [rax+rax+00h]
0x1800031ee  cmp     eax, 7Ah ; 'z'
0x1800031f1  jnz     loc_18000310F
0x1800031f7  mov     edx, [rsp+178h+TokenInformationLength]; uBytes
0x1800031fb  mov     ecx, 40h ; '@'; uFlags
0x180003200  call    cs:__imp_LocalAlloc
0x180003207  nop     dword ptr [rax+rax+00h]
0x18000320c  mov     rdi, rax
0x18000320f  test    rax, rax
0x180003212  jz      short loc_180003198
0x180003214  mov     r9d, [rsp+178h+TokenInformationLength]; TokenInformationLength
0x180003219  lea     rax, [rsp+178h+TokenInformationLength]
0x18000321e  mov     rcx, [rsp+178h+TokenHandle]; TokenHandle
0x180003223  mov     r8, rdi; TokenInformation
0x180003226  mov     edx, 1; TokenInformationClass
0x18000322b  mov     [rsp+178h+ReturnLength], rax; ReturnLength
0x180003230  call    cs:__imp_GetTokenInformation
0x180003237  nop     dword ptr [rax+rax+00h]
0x18000323c  test    eax, eax
0x18000323e  jz      loc_180003189
0x180003244  mov     r12, rdi
0x180003247  jmp     loc_18000310F
0x18000324c  call    cs:__imp_GetCurrentThread
0x180003253  nop     dword ptr [rax+rax+00h]
0x180003258  lea     r9, [rsp+178h+TokenHandle]; TokenHandle
0x18000325d  mov     edx, 8; DesiredAccess
0x180003262  mov     rcx, rax; ThreadHandle
0x180003265  mov     r8d, 1; OpenAsSelf
0x18000326b  call    cs:__imp_OpenThreadToken
0x180003272  nop     dword ptr [rax+rax+00h]
0x180003277  test    eax, eax
0x180003279  jz      loc_1800031A0
0x18000327f  mov     rcx, [rsp+178h+TokenHandle]
0x180003284  jmp     loc_1800030CC
0x180003289  mov     rcx, rbp; hMem
0x18000328c  call    cs:__imp_LocalFree
0x180003293  nop     dword ptr [rax+rax+00h]
0x180003298  jmp     loc_180003174
0x18000329d  call    cs:__imp_CloseHandle
0x1800032a4  nop     dword ptr [rax+rax+00h]
0x1800032a9  jmp     loc_1800031C3
```
