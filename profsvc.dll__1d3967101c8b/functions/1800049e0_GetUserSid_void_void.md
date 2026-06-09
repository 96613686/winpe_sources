# GetUserSid(void *,void * *)

- ea: `0x1800049e0`
- end: `0x180004b71`
- name: `?GetUserSid@@YAJPEAXPEAPEAX@Z`
- size: `401`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004768`
- `0x18002b2a0`
- `0x180043c70`
- `0x18004debc`

## callees

- `0x180004170`
- `0x1800049e0`
- `0x180004ff4`
- `0x180006580`
- `0x18003e8fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a16`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a16`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004abd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004abd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004aaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004aaf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004a97`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004a97`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004a5e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004a5e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004a47`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004b23`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004a47`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004b23`

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
  void *v10; // rsi
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
      ResultFromKnownLastError();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800049e0  mov     [rsp+arg_0], rbx
0x1800049e5  push    rsi
0x1800049e6  push    rdi
0x1800049e7  push    r14
0x1800049e9  sub     rsp, 30h
0x1800049ed  mov     r14, rdx
0x1800049f0  mov     qword ptr [rdx], 0
0x1800049f7  mov     rsi, rcx
0x1800049fa  mov     [rsp+48h+TokenInformationLength], 0C8h
0x180004a02  call    cs:__imp_GetProcessHeap
0x180004a08  mov     edx, 8; dwFlags
0x180004a0d  mov     r8d, 0C8h; dwBytes
0x180004a13  mov     rcx, rax; hHeap
0x180004a16  call    cs:__imp_HeapAlloc
0x180004a1c  mov     [rsp+48h+TokenInformation], rax
0x180004a21  mov     rbx, rax
0x180004a24  test    rax, rax
0x180004a27  jz      loc_180004B67
0x180004a2d  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180004a32  lea     rax, [rsp+48h+TokenInformationLength]
0x180004a37  mov     r8, rbx; TokenInformation
0x180004a3a  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180004a3f  mov     edx, 1; TokenInformationClass
0x180004a44  mov     rcx, rsi; TokenHandle
0x180004a47  call    cs:__imp_GetTokenInformation
0x180004a4d  test    eax, eax
0x180004a4f  jz      loc_180004ADB
0x180004a55  xor     edi, edi
0x180004a57  test    edi, edi
0x180004a59  js      short loc_180004AAA
0x180004a5b  mov     rcx, [rbx]; pSid
0x180004a5e  call    cs:__imp_GetLengthSid
0x180004a64  mov     edi, eax
0x180004a66  mov     [rsp+48h+TokenInformationLength], edi
0x180004a6a  call    cs:__imp_GetProcessHeap
0x180004a70  mov     r8d, edi; dwBytes
0x180004a73  mov     edx, 8; dwFlags
0x180004a78  mov     rcx, rax; hHeap
0x180004a7b  call    cs:__imp_HeapAlloc
0x180004a81  mov     rsi, rax
0x180004a84  test    rax, rax
0x180004a87  jz      loc_180004B53
0x180004a8d  mov     r8, [rbx]; pSourceSid
0x180004a90  mov     rdx, rax; pDestinationSid
0x180004a93  mov     ecx, [rsp+48h+TokenInformationLength]; nDestinationSidLength
0x180004a97  call    cs:__imp_CopySid
0x180004a9d  test    eax, eax
0x180004a9f  jz      loc_180004B37
0x180004aa5  xor     edi, edi
0x180004aa7  mov     [r14], rsi
0x180004aaa  test    rbx, rbx
0x180004aad  jz      short loc_180004ACB
0x180004aaf  call    cs:__imp_GetProcessHeap
0x180004ab5  mov     r8, rbx; lpMem
0x180004ab8  xor     edx, edx; dwFlags
0x180004aba  mov     rcx, rax; hHeap
0x180004abd  call    cs:__imp_HeapFree
0x180004ac3  test    eax, eax
0x180004ac5  jz      loc_180004B5D
0x180004acb  mov     eax, edi
0x180004acd  mov     rbx, [rsp+48h+arg_0]
0x180004ad2  add     rsp, 30h
0x180004ad6  pop     r14
0x180004ad8  pop     rdi
0x180004ad9  pop     rsi
0x180004ada  retn
0x180004adb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004ae0  mov     edi, eax
0x180004ae2  cmp     eax, 8007007Ah
0x180004ae7  jnz     loc_180004A57
0x180004aed  mov     edx, [rsp+48h+TokenInformationLength]; dwBytes
0x180004af1  lea     r8, [rsp+48h+TokenInformation]; void **
0x180004af6  mov     rcx, rbx; lpMem
0x180004af9  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180004afe  mov     rbx, [rsp+48h+TokenInformation]
0x180004b03  mov     edi, eax
0x180004b05  test    eax, eax
0x180004b07  js      short loc_180004AAA
0x180004b09  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180004b0e  lea     rax, [rsp+48h+TokenInformationLength]
0x180004b13  mov     r8, rbx; TokenInformation
0x180004b16  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180004b1b  mov     edx, 1; TokenInformationClass
0x180004b20  mov     rcx, rsi; TokenHandle
0x180004b23  call    cs:__imp_GetTokenInformation
0x180004b29  mov     ecx, eax; int
0x180004b2b  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180004b30  mov     edi, eax
0x180004b32  jmp     loc_180004A57
0x180004b37  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004b3c  mov     edi, eax
0x180004b3e  test    eax, eax
0x180004b40  jns     loc_180004AA7
0x180004b46  mov     rcx, rsi; lpMem
0x180004b49  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180004b4e  jmp     loc_180004AAA
0x180004b53  mov     edi, 8007000Eh
0x180004b58  jmp     loc_180004AAA
0x180004b5d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004b62  jmp     loc_180004ACB
0x180004b67  mov     eax, 8007000Eh
0x180004b6c  jmp     loc_180004ACD
```
