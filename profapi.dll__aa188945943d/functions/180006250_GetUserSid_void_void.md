# GetUserSid(void *,void * *)

- ea: `0x180006250`
- end: `0x1800063d4`
- name: `?GetUserSid@@YAJPEAXPEAPEAX@Z`
- size: `388`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006de0`

## callees

- `0x180006250`
- `0x1800063e0`
- `0x180006a9c`
- `0x180007c60`
- `0x18001214c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000632c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000632c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006285`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006285`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006271`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000631e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006271`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000631e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006336`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006336`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006306`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006306`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800062cd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800062cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800062b6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000639a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800062b6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000639a`

## pseudocode

```c
__int64 __fastcall GetUserSid(HANDLE TokenHandle, void **a2)
{
  HANDLE ProcessHeap; // rax
  PSID *v5; // rbx
  int Error; // edi
  DWORD LengthSid; // edi
  HANDLE v8; // rax
  void *v9; // rax
  void *v10; // rbp
  HANDLE v11; // rax
  int v13; // eax
  BOOL v14; // eax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  LPVOID TokenInformation; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  TokenInformationLength = 200;
  ProcessHeap = GetProcessHeap();
  TokenInformation = HeapAlloc(ProcessHeap, 8u, 0xC8u);
  v5 = (PSID *)TokenInformation;
  if ( !TokenInformation )
    return 2147942414LL;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      v13 = ResultFromHeapReAlloc(v5, TokenInformationLength, &TokenInformation);
      v5 = (PSID *)TokenInformation;
      Error = v13;
      if ( v13 < 0 )
        goto LABEL_9;
      v14 = GetTokenInformation(
              TokenHandle,
              TokenUser,
              TokenInformation,
              TokenInformationLength,
              &TokenInformationLength);
      Error = ResultFromWin32Bool(v14);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*v5);
    TokenInformationLength = LengthSid;
    v8 = GetProcessHeap();
    v9 = HeapAlloc(v8, 8u, LengthSid);
    v10 = v9;
    if ( !v9 )
    {
      Error = -2147024882;
      goto LABEL_9;
    }
    if ( CopySid(TokenInformationLength, v9, *v5) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        ResultFromHeapFree(v10);
        goto LABEL_9;
      }
    }
    *a2 = v10;
  }
LABEL_9:
  if ( v5 )
  {
    v11 = GetProcessHeap();
    if ( !HeapFree(v11, 0, v5) )
      GetLastError();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180006250  mov     [rsp+arg_0], rbx
0x180006255  push    rbp
0x180006256  push    rsi
0x180006257  push    rdi
0x180006258  sub     rsp, 30h
0x18000625c  mov     rsi, rdx
0x18000625f  mov     qword ptr [rdx], 0
0x180006266  mov     rbp, rcx
0x180006269  mov     [rsp+48h+TokenInformationLength], 0C8h
0x180006271  call    cs:__imp_GetProcessHeap
0x180006277  mov     edx, 8; dwFlags
0x18000627c  mov     r8d, 0C8h; dwBytes
0x180006282  mov     rcx, rax; hHeap
0x180006285  call    cs:__imp_HeapAlloc
0x18000628b  mov     [rsp+48h+TokenInformation], rax
0x180006290  mov     rbx, rax
0x180006293  test    rax, rax
0x180006296  jz      loc_18000634B
0x18000629c  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800062a1  lea     rax, [rsp+48h+TokenInformationLength]
0x1800062a6  mov     r8, rbx; TokenInformation
0x1800062a9  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800062ae  mov     edx, 1; TokenInformationClass
0x1800062b3  mov     rcx, rbp; TokenHandle
0x1800062b6  call    cs:__imp_GetTokenInformation
0x1800062bc  test    eax, eax
0x1800062be  jz      loc_180006352
0x1800062c4  xor     edi, edi
0x1800062c6  test    edi, edi
0x1800062c8  js      short loc_180006319
0x1800062ca  mov     rcx, [rbx]; pSid
0x1800062cd  call    cs:__imp_GetLengthSid
0x1800062d3  mov     edi, eax
0x1800062d5  mov     [rsp+48h+TokenInformationLength], edi
0x1800062d9  call    cs:__imp_GetProcessHeap
0x1800062df  mov     r8d, edi; dwBytes
0x1800062e2  mov     edx, 8; dwFlags
0x1800062e7  mov     rcx, rax; hHeap
0x1800062ea  call    cs:__imp_HeapAlloc
0x1800062f0  mov     rbp, rax
0x1800062f3  test    rax, rax
0x1800062f6  jz      loc_1800063CA
0x1800062fc  mov     r8, [rbx]; pSourceSid
0x1800062ff  mov     rdx, rax; pDestinationSid
0x180006302  mov     ecx, [rsp+48h+TokenInformationLength]; nDestinationSidLength
0x180006306  call    cs:__imp_CopySid
0x18000630c  test    eax, eax
0x18000630e  jz      loc_1800063AE
0x180006314  xor     edi, edi
0x180006316  mov     [rsi], rbp
0x180006319  test    rbx, rbx
0x18000631c  jz      short loc_18000633C
0x18000631e  call    cs:__imp_GetProcessHeap
0x180006324  mov     r8, rbx; lpMem
0x180006327  xor     edx, edx; dwFlags
0x180006329  mov     rcx, rax; hHeap
0x18000632c  call    cs:__imp_HeapFree
0x180006332  test    eax, eax
0x180006334  jnz     short loc_18000633C
0x180006336  call    cs:__imp_GetLastError
0x18000633c  mov     eax, edi
0x18000633e  mov     rbx, [rsp+48h+arg_0]
0x180006343  add     rsp, 30h
0x180006347  pop     rdi
0x180006348  pop     rsi
0x180006349  pop     rbp
0x18000634a  retn
0x18000634b  mov     eax, 8007000Eh
0x180006350  jmp     short loc_18000633E
0x180006352  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006357  mov     edi, eax
0x180006359  cmp     eax, 8007007Ah
0x18000635e  jnz     loc_1800062C6
0x180006364  mov     edx, [rsp+48h+TokenInformationLength]; dwBytes
0x180006368  lea     r8, [rsp+48h+TokenInformation]; void **
0x18000636d  mov     rcx, rbx; lpMem
0x180006370  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180006375  mov     rbx, [rsp+48h+TokenInformation]
0x18000637a  mov     edi, eax
0x18000637c  test    eax, eax
0x18000637e  js      short loc_180006319
0x180006380  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180006385  lea     rax, [rsp+48h+TokenInformationLength]
0x18000638a  mov     r8, rbx; TokenInformation
0x18000638d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180006392  mov     edx, 1; TokenInformationClass
0x180006397  mov     rcx, rbp; TokenHandle
0x18000639a  call    cs:__imp_GetTokenInformation
0x1800063a0  mov     ecx, eax; int
0x1800063a2  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800063a7  mov     edi, eax
0x1800063a9  jmp     loc_1800062C6
0x1800063ae  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800063b3  mov     edi, eax
0x1800063b5  test    eax, eax
0x1800063b7  jns     loc_180006316
0x1800063bd  mov     rcx, rbp; lpMem
0x1800063c0  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800063c5  jmp     loc_180006319
0x1800063ca  mov     edi, 8007000Eh
0x1800063cf  jmp     loc_180006319
```
