# GetCurrentUserSid(void * *)

- ea: `0x140015710`
- end: `0x14001589e`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `398`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400137b8`
- `0x140013bb4`
- `0x1400155e4`
- `0x1400334f4`
- `0x14004b1bc`
- `0x140085660`

## callees

- `0x140015710`
- `0x140016b10`
- `0x1401040e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140015843`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140015843`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140015765`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140015765`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140015853`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140015853`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001574a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001574a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015805`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015805`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015893`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015893`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400157d7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400157d7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400157c3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400157c3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1400157b6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1400157b6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140015794`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140015794`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400157ed`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400157ed`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  void *v3; // rsi
  int Error; // ebx
  void *v5; // rcx
  DWORD LengthSid; // ebp
  HLOCAL v7; // rax
  void *v8; // rdi
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-98h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-90h] BYREF
  void *TokenInformation; // [rsp+40h] [rbp-88h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_2;
  Error = ResultFromKnownLastError();
  if ( Error == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_2;
    Error = ResultFromKnownLastError();
  }
  if ( Error < 0 )
    return (unsigned int)Error;
LABEL_2:
  ReturnLength = 88;
  if ( !GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x58u, &ReturnLength) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_8;
  }
  v3 = TokenInformation;
  Error = -2147024809;
  v5 = TokenInformation;
  *a1 = 0;
  if ( !IsValidSid(v5) )
    goto LABEL_8;
  LengthSid = GetLengthSid(v3);
  Error = -2147024882;
  v7 = LocalAlloc(0x40u, LengthSid);
  v8 = v7;
  if ( !v7 )
    goto LABEL_8;
  if ( CopySid(LengthSid, v7, v3) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      LocalFree(v8);
      goto LABEL_8;
    }
  }
  *a1 = v8;
LABEL_8:
  CloseHandle(TokenHandle);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x140015710  mov     [rsp+arg_8], rbx
0x140015715  mov     [rsp+arg_10], rbp
0x14001571a  push    rsi
0x14001571b  push    rdi
0x14001571c  push    r14
0x14001571e  sub     rsp, 0B0h
0x140015725  mov     rax, cs:__security_cookie
0x14001572c  xor     rax, rsp
0x14001572f  mov     [rsp+0C8h+var_28], rax
0x140015737  mov     r14, rcx
0x14001573a  mov     qword ptr [rcx], 0
0x140015741  mov     [rsp+0C8h+TokenHandle], 0
0x14001574a  call    cs:__imp_GetCurrentThread
0x140015750  mov     esi, 1
0x140015755  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x14001575a  mov     rcx, rax; ThreadHandle
0x14001575d  mov     r8d, esi; OpenAsSelf
0x140015760  lea     edi, [rsi+7]
0x140015763  mov     edx, edi; DesiredAccess
0x140015765  call    cs:__imp_OpenThreadToken
0x14001576b  test    eax, eax
0x14001576d  jz      loc_140015835
0x140015773  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x140015778  lea     rax, [rsp+0C8h+var_90]
0x14001577d  mov     r9d, 58h ; 'X'; TokenInformationLength
0x140015783  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x140015788  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x14001578d  mov     [rsp+0C8h+var_90], r9d
0x140015792  mov     edx, esi; TokenInformationClass
0x140015794  call    cs:__imp_GetTokenInformation
0x14001579a  test    eax, eax
0x14001579c  jz      loc_140015871
0x1400157a2  mov     rsi, [rsp+0C8h+TokenInformation]
0x1400157a7  mov     ebx, 80070057h
0x1400157ac  mov     rcx, rsi; pSid
0x1400157af  mov     qword ptr [r14], 0
0x1400157b6  call    cs:__imp_IsValidSid
0x1400157bc  test    eax, eax
0x1400157be  jz      short loc_140015800
0x1400157c0  mov     rcx, rsi; pSid
0x1400157c3  call    cs:__imp_GetLengthSid
0x1400157c9  mov     edx, eax; uBytes
0x1400157cb  mov     ecx, 40h ; '@'; uFlags
0x1400157d0  mov     ebp, eax
0x1400157d2  mov     ebx, 8007000Eh
0x1400157d7  call    cs:__imp_LocalAlloc
0x1400157dd  mov     rdi, rax
0x1400157e0  test    rax, rax
0x1400157e3  jz      short loc_140015800
0x1400157e5  mov     r8, rsi; pSourceSid
0x1400157e8  mov     rdx, rax; pDestinationSid
0x1400157eb  mov     ecx, ebp; nDestinationSidLength
0x1400157ed  call    cs:__imp_CopySid
0x1400157f3  test    eax, eax
0x1400157f5  jz      loc_140015881
0x1400157fb  xor     ebx, ebx
0x1400157fd  mov     [r14], rdi
0x140015800  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x140015805  call    cs:__imp_CloseHandle
0x14001580b  mov     eax, ebx
0x14001580d  mov     rcx, [rsp+0C8h+var_28]
0x140015815  xor     rcx, rsp; StackCookie
0x140015818  call    __security_check_cookie
0x14001581d  lea     r11, [rsp+0C8h+var_18]
0x140015825  mov     rbx, [r11+28h]
0x140015829  mov     rbp, [r11+30h]
0x14001582d  mov     rsp, r11
0x140015830  pop     r14
0x140015832  pop     rdi
0x140015833  pop     rsi
0x140015834  retn
0x140015835  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001583a  mov     ebx, eax
0x14001583c  cmp     eax, 800703F0h
0x140015841  jnz     short loc_140015868
0x140015843  call    cs:__imp_GetCurrentProcess
0x140015849  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x14001584e  mov     edx, edi; DesiredAccess
0x140015850  mov     rcx, rax; ProcessHandle
0x140015853  call    cs:__imp_OpenProcessToken
0x140015859  test    eax, eax
0x14001585b  jnz     loc_140015773
0x140015861  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140015866  mov     ebx, eax
0x140015868  test    ebx, ebx
0x14001586a  js      short loc_14001580B
0x14001586c  jmp     loc_140015773
0x140015871  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140015876  mov     ebx, eax
0x140015878  test    eax, eax
0x14001587a  js      short loc_140015800
0x14001587c  jmp     loc_1400157A2
0x140015881  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140015886  mov     ebx, eax
0x140015888  test    eax, eax
0x14001588a  jns     loc_1400157FD
0x140015890  mov     rcx, rdi; hMem
0x140015893  call    cs:__imp_LocalFree
0x140015899  jmp     loc_140015800
```
