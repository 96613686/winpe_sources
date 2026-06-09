# GetUserSid(void *,void * *)

- ea: `0x180001cfc`
- end: `0x180001e92`
- name: `?GetUserSid@@YAJPEAXPEAPEAX@Z`
- size: `406`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a80`
- `0x18000ca58`
- `0x180013de4`
- `0x180018c68`
- `0x18001fed0`

## callees

- `0x180001cfc`
- `0x180001e98`
- `0x18001a718`
- `0x18001a784`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001d8e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001d8e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180001dd3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180001dd3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180001d71`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180001e41`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180001d71`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180001e41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001d3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001db6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001d3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001db6`

## pseudocode

```c
__int64 __fastcall GetUserSid(HANDLE TokenHandle, void **a2)
{
  HANDLE ProcessHeap; // rax
  PSID *v5; // rdi
  int Error; // ebx
  DWORD LengthSid; // ebx
  HANDLE v8; // rax
  void *v9; // rax
  void *v10; // rsi
  int v12; // eax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF

  *a2 = 0;
  TokenInformationLength = 200;
  ProcessHeap = GetProcessHeap();
  TokenInformation = HeapAlloc(ProcessHeap, 8u, 0xC8u);
  v5 = (PSID *)TokenInformation;
  if ( !TokenInformation )
    return (unsigned int)-2147024882;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
LABEL_3:
    Error = 0;
    goto LABEL_4;
  }
  Error = ResultFromKnownLastError();
  if ( Error == -2147024774 )
  {
    v12 = ResultFromHeapReAlloc(v5, TokenInformationLength, &TokenInformation);
    v5 = (PSID *)TokenInformation;
    Error = v12;
    if ( v12 < 0 )
      goto LABEL_9;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_3;
    Error = ResultFromKnownLastError();
  }
LABEL_4:
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*v5);
    TokenInformationLength = LengthSid;
    v8 = GetProcessHeap();
    v9 = HeapAlloc(v8, 8u, LengthSid);
    v10 = v9;
    if ( v9 )
    {
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
    else
    {
      Error = -2147024882;
    }
  }
LABEL_9:
  ResultFromHeapFree(v5);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180001cfc  mov     [rsp-18h+arg_0], rbx
0x180001d01  mov     [rsp-18h+arg_18], rsi
0x180001d06  push    rbp
0x180001d07  push    rdi
0x180001d08  push    r14
0x180001d0a  mov     rbp, rsp
0x180001d0d  sub     rsp, 30h
0x180001d11  mov     ebx, 0C8h
0x180001d16  mov     qword ptr [rdx], 0
0x180001d1d  mov     [rbp+TokenInformationLength], ebx
0x180001d20  mov     r14, rdx
0x180001d23  mov     rsi, rcx
0x180001d26  call    cs:__imp_GetProcessHeap
0x180001d2d  nop     dword ptr [rax+rax+00h]
0x180001d32  mov     r8d, ebx; dwBytes
0x180001d35  mov     edx, 8; dwFlags
0x180001d3a  mov     rcx, rax; hHeap
0x180001d3d  call    cs:__imp_HeapAlloc
0x180001d44  nop     dword ptr [rax+rax+00h]
0x180001d49  mov     [rbp+TokenInformation], rax
0x180001d4d  mov     rdi, rax
0x180001d50  test    rax, rax
0x180001d53  jz      loc_180001E0D
0x180001d59  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180001d5d  lea     rax, [rbp+TokenInformationLength]
0x180001d61  mov     r8, rdi; TokenInformation
0x180001d64  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180001d69  mov     edx, 1; TokenInformationClass
0x180001d6e  mov     rcx, rsi; TokenHandle
0x180001d71  call    cs:__imp_GetTokenInformation
0x180001d78  nop     dword ptr [rax+rax+00h]
0x180001d7d  test    eax, eax
0x180001d7f  jz      loc_180001E61
0x180001d85  xor     ebx, ebx
0x180001d87  test    ebx, ebx
0x180001d89  js      short loc_180001DE8
0x180001d8b  mov     rcx, [rdi]; pSid
0x180001d8e  call    cs:__imp_GetLengthSid
0x180001d95  nop     dword ptr [rax+rax+00h]
0x180001d9a  mov     ebx, eax
0x180001d9c  mov     [rbp+TokenInformationLength], ebx
0x180001d9f  call    cs:__imp_GetProcessHeap
0x180001da6  nop     dword ptr [rax+rax+00h]
0x180001dab  mov     r8d, ebx; dwBytes
0x180001dae  mov     edx, 8; dwFlags
0x180001db3  mov     rcx, rax; hHeap
0x180001db6  call    cs:__imp_HeapAlloc
0x180001dbd  nop     dword ptr [rax+rax+00h]
0x180001dc2  mov     rsi, rax
0x180001dc5  test    rax, rax
0x180001dc8  jz      short loc_180001E06
0x180001dca  mov     r8, [rdi]; pSourceSid
0x180001dcd  mov     rdx, rax; pDestinationSid
0x180001dd0  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x180001dd3  call    cs:__imp_CopySid
0x180001dda  nop     dword ptr [rax+rax+00h]
0x180001ddf  test    eax, eax
0x180001de1  jz      short loc_180001E14
0x180001de3  xor     ebx, ebx
0x180001de5  mov     [r14], rsi
0x180001de8  mov     rcx, rdi; lpMem
0x180001deb  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180001df0  mov     rsi, [rsp+30h+arg_18]
0x180001df5  mov     eax, ebx
0x180001df7  mov     rbx, [rsp+30h+arg_0]
0x180001dfc  add     rsp, 30h
0x180001e00  pop     r14
0x180001e02  pop     rdi
0x180001e03  pop     rbp
0x180001e04  retn
0x180001e06  mov     ebx, 8007000Eh
0x180001e0b  jmp     short loc_180001DE8
0x180001e0d  mov     ebx, 8007000Eh
0x180001e12  jmp     short loc_180001DF0
0x180001e14  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180001e19  mov     ebx, eax
0x180001e1b  test    eax, eax
0x180001e1d  jns     short loc_180001DE5
0x180001e1f  mov     rcx, rsi; lpMem
0x180001e22  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180001e27  jmp     short loc_180001DE8
0x180001e29  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180001e2d  lea     rax, [rbp+TokenInformationLength]
0x180001e31  mov     r8, rdi; TokenInformation
0x180001e34  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180001e39  mov     edx, 1; TokenInformationClass
0x180001e3e  mov     rcx, rsi; TokenHandle
0x180001e41  call    cs:__imp_GetTokenInformation
0x180001e48  nop     dword ptr [rax+rax+00h]
0x180001e4d  test    eax, eax
0x180001e4f  jnz     loc_180001D85
0x180001e55  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180001e5a  mov     ebx, eax
0x180001e5c  jmp     loc_180001D87
0x180001e61  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180001e66  mov     ebx, eax
0x180001e68  cmp     eax, 8007007Ah
0x180001e6d  jnz     loc_180001D87
0x180001e73  mov     edx, [rbp+TokenInformationLength]; dwBytes
0x180001e76  lea     r8, [rbp+TokenInformation]; void **
0x180001e7a  mov     rcx, rdi; lpMem
0x180001e7d  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180001e82  mov     rdi, [rbp+TokenInformation]
0x180001e86  mov     ebx, eax
0x180001e88  test    eax, eax
0x180001e8a  js      loc_180001DE8
0x180001e90  jmp     short loc_180001E29
```
