# GetCurrentUserSid(void * *)

- ea: `0x1800ceb24`
- end: `0x1800cec62`
- name: `?GetCurrentUserSid@@YA_NPEAPEAX@Z`
- size: `318`
- prototype: `bool __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180097ad0`

## callees

- `0x1800ceb24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ceb88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ceb88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ceb4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ceb4b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ceb5d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ceb5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ceb97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cebea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ceb97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cebea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800cebaa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800cec06`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800cebaa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800cec06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cebde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cec2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cec37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cec47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cebde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cec2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cec37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cec47`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ceb82`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800cebd1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ceb82`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800cebd1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cebf6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cebf6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800cec1d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800cec1d`

## pseudocode

```c
char __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentProcess; // rax
  void *v3; // rcx
  PSID *v4; // rax
  PSID *v5; // rbx
  PSID v6; // rsi
  DWORD LengthSid; // r14d
  HLOCAL v8; // rax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  TokenInformationLength = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    return 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( GetLastError() != 122 )
    goto LABEL_3;
  v4 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
  v3 = TokenHandle;
  v5 = v4;
  if ( !v4 )
    goto LABEL_4;
  if ( !GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
  {
    LocalFree(v5);
LABEL_3:
    v3 = TokenHandle;
LABEL_4:
    CloseHandle(v3);
    return 0;
  }
  CloseHandle(TokenHandle);
  v6 = *v5;
  LengthSid = GetLengthSid(*v5);
  v8 = LocalAlloc(0x40u, LengthSid);
  *a1 = v8;
  if ( v8 && CopySid(LengthSid, v8, v6) )
  {
    LocalFree(v5);
    return 1;
  }
  LocalFree(*a1);
  *a1 = 0;
  LocalFree(v5);
  return 0;
}

```

## disassembly

```asm
0x1800ceb24  mov     [rsp-18h+arg_0], rbx
0x1800ceb29  mov     [rsp-18h+arg_18], rsi
0x1800ceb2e  push    rbp
0x1800ceb2f  push    rdi
0x1800ceb30  push    r14
0x1800ceb32  mov     rbp, rsp
0x1800ceb35  sub     rsp, 30h
0x1800ceb39  mov     rdi, rcx
0x1800ceb3c  mov     [rbp+TokenInformationLength], 0
0x1800ceb43  mov     [rbp+TokenHandle], 0
0x1800ceb4b  call    cs:__imp_GetCurrentProcess
0x1800ceb51  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800ceb55  mov     edx, 8; DesiredAccess
0x1800ceb5a  mov     rcx, rax; ProcessHandle
0x1800ceb5d  call    cs:__imp_OpenProcessToken
0x1800ceb63  test    eax, eax
0x1800ceb65  jz      loc_1800CEC4D
0x1800ceb6b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800ceb6f  lea     rax, [rbp+TokenInformationLength]
0x1800ceb73  xor     r9d, r9d; TokenInformationLength
0x1800ceb76  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800ceb7b  xor     r8d, r8d; TokenInformation
0x1800ceb7e  lea     edx, [r9+1]; TokenInformationClass
0x1800ceb82  call    cs:__imp_GetTokenInformation
0x1800ceb88  call    cs:__imp_GetLastError
0x1800ceb8e  cmp     eax, 7Ah ; 'z'
0x1800ceb91  jz      short loc_1800CEBA2
0x1800ceb93  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ceb97  call    cs:__imp_CloseHandle
0x1800ceb9d  jmp     loc_1800CEC4D
0x1800ceba2  mov     edx, [rbp+TokenInformationLength]; uBytes
0x1800ceba5  mov     ecx, 40h ; '@'; uFlags
0x1800cebaa  call    cs:__imp_LocalAlloc
0x1800cebb0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800cebb4  mov     rbx, rax
0x1800cebb7  test    rax, rax
0x1800cebba  jz      short loc_1800CEB97
0x1800cebbc  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800cebc0  lea     rax, [rbp+TokenInformationLength]
0x1800cebc4  mov     r8, rbx; TokenInformation
0x1800cebc7  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800cebcc  mov     edx, 1; TokenInformationClass
0x1800cebd1  call    cs:__imp_GetTokenInformation
0x1800cebd7  test    eax, eax
0x1800cebd9  jnz     short loc_1800CEBE6
0x1800cebdb  mov     rcx, rbx; hMem
0x1800cebde  call    cs:__imp_LocalFree
0x1800cebe4  jmp     short loc_1800CEB93
0x1800cebe6  mov     rcx, [rbp+TokenHandle]; hObject
0x1800cebea  call    cs:__imp_CloseHandle
0x1800cebf0  mov     rsi, [rbx]
0x1800cebf3  mov     rcx, rsi; pSid
0x1800cebf6  call    cs:__imp_GetLengthSid
0x1800cebfc  mov     edx, eax; uBytes
0x1800cebfe  mov     ecx, 40h ; '@'; uFlags
0x1800cec03  mov     r14d, eax
0x1800cec06  call    cs:__imp_LocalAlloc
0x1800cec0c  mov     [rdi], rax
0x1800cec0f  test    rax, rax
0x1800cec12  jz      short loc_1800CEC34
0x1800cec14  mov     r8, rsi; pSourceSid
0x1800cec17  mov     rdx, rax; pDestinationSid
0x1800cec1a  mov     ecx, r14d; nDestinationSidLength
0x1800cec1d  call    cs:__imp_CopySid
0x1800cec23  test    eax, eax
0x1800cec25  jz      short loc_1800CEC34
0x1800cec27  mov     rcx, rbx; hMem
0x1800cec2a  call    cs:__imp_LocalFree
0x1800cec30  mov     al, 1
0x1800cec32  jmp     short loc_1800CEC4F
0x1800cec34  mov     rcx, [rdi]; hMem
0x1800cec37  call    cs:__imp_LocalFree
0x1800cec3d  mov     rcx, rbx; hMem
0x1800cec40  mov     qword ptr [rdi], 0
0x1800cec47  call    cs:__imp_LocalFree
0x1800cec4d  xor     al, al
0x1800cec4f  mov     rbx, [rsp+30h+arg_0]
0x1800cec54  mov     rsi, [rsp+30h+arg_18]
0x1800cec59  add     rsp, 30h
0x1800cec5d  pop     r14
0x1800cec5f  pop     rdi
0x1800cec60  pop     rbp
0x1800cec61  retn
```
