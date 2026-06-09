# GetUserSid(void *,void * *)

- ea: `0x1800197f0`
- end: `0x180019933`
- name: `?GetUserSid@@YAJPEAXPEAPEAX@Z`
- size: `323`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019634`

## callees

- `0x1800045d0`
- `0x180004830`
- `0x18000f97c`
- `0x18000f9c8`
- `0x1800197f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001986a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001986a`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001987e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001987e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800198c7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800198c7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800198f6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800198f6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019851`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800198b1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019851`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800198b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetUserSid(HANDLE TokenHandle, void **a2)
{
  int Error; // ebx
  PSID *v5; // rdi
  BOOL v6; // eax
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v9; // rax
  BOOL v10; // eax
  DWORD LengthSid; // eax
  void *v12; // rsi
  BOOL v13; // eax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF

  *a2 = 0;
  TokenInformation = 0;
  TokenInformationLength = 200;
  Error = ResultFromHeapAlloc(0xC8u, &TokenInformation);
  if ( Error >= 0 )
  {
    v5 = (PSID *)TokenInformation;
    v6 = GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength);
    Error = ResultFromWin32Bool(v6);
    if ( Error == -2147024774 )
    {
      v7 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v9 = (PSID *)HeapReAlloc(ProcessHeap, 8u, v5, v7);
      if ( v9 )
      {
        v5 = v9;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
LABEL_12:
          ResultFromHeapFree(v5);
          return (unsigned int)Error;
        }
      }
      v10 = GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength);
      Error = ResultFromWin32Bool(v10);
    }
    if ( Error >= 0 )
    {
      LengthSid = GetLengthSid(*v5);
      TokenInformation = 0;
      TokenInformationLength = LengthSid;
      Error = ResultFromHeapAlloc(LengthSid, &TokenInformation);
      if ( Error >= 0 )
      {
        v12 = TokenInformation;
        v13 = CopySid(TokenInformationLength, TokenInformation, *v5);
        Error = ResultFromWin32Bool(v13);
        if ( Error < 0 )
          ResultFromHeapFree(v12);
        else
          *a2 = v12;
      }
    }
    goto LABEL_12;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800197f0  mov     [rsp-18h+arg_0], rbx
0x1800197f5  mov     [rsp-18h+arg_18], rsi
0x1800197fa  push    rbp
0x1800197fb  push    rdi
0x1800197fc  push    r14
0x1800197fe  mov     rbp, rsp
0x180019801  sub     rsp, 30h
0x180019805  mov     rsi, rcx
0x180019808  mov     qword ptr [rdx], 0
0x18001980f  mov     ecx, 0C8h; dwBytes
0x180019814  mov     [rbp+TokenInformation], 0
0x18001981c  mov     r14, rdx
0x18001981f  mov     [rbp+TokenInformationLength], ecx
0x180019822  lea     rdx, [rbp+TokenInformation]; void **
0x180019826  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x18001982b  mov     ebx, eax
0x18001982d  test    eax, eax
0x18001982f  js      loc_18001991E
0x180019835  mov     rdi, [rbp+TokenInformation]
0x180019839  lea     rax, [rbp+TokenInformationLength]
0x18001983d  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180019841  mov     r8, rdi; TokenInformation
0x180019844  mov     edx, 1; TokenInformationClass
0x180019849  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001984e  mov     rcx, rsi; TokenHandle
0x180019851  call    cs:__imp_GetTokenInformation
0x180019857  mov     ecx, eax; int
0x180019859  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18001985e  mov     ebx, eax
0x180019860  cmp     eax, 8007007Ah
0x180019865  jnz     short loc_1800198C0
0x180019867  mov     ebx, [rbp+TokenInformationLength]
0x18001986a  call    cs:__imp_GetProcessHeap
0x180019870  mov     r9d, ebx; dwBytes
0x180019873  mov     r8, rdi; lpMem
0x180019876  mov     rcx, rax; hHeap
0x180019879  mov     edx, 8; dwFlags
0x18001987e  call    cs:__imp_HeapReAlloc
0x180019884  test    rax, rax
0x180019887  jz      short loc_18001988E
0x180019889  mov     rdi, rax
0x18001988c  jmp     short loc_180019899
0x18001988e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180019893  mov     ebx, eax
0x180019895  test    eax, eax
0x180019897  js      short loc_180019916
0x180019899  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001989d  lea     rax, [rbp+TokenInformationLength]
0x1800198a1  mov     r8, rdi; TokenInformation
0x1800198a4  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800198a9  mov     edx, 1; TokenInformationClass
0x1800198ae  mov     rcx, rsi; TokenHandle
0x1800198b1  call    cs:__imp_GetTokenInformation
0x1800198b7  mov     ecx, eax; int
0x1800198b9  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800198be  mov     ebx, eax
0x1800198c0  test    ebx, ebx
0x1800198c2  js      short loc_180019916
0x1800198c4  mov     rcx, [rdi]; pSid
0x1800198c7  call    cs:__imp_GetLengthSid
0x1800198cd  lea     rdx, [rbp+TokenInformation]; void **
0x1800198d1  mov     [rbp+TokenInformation], 0
0x1800198d9  mov     ecx, eax; dwBytes
0x1800198db  mov     [rbp+TokenInformationLength], ecx
0x1800198de  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x1800198e3  mov     ebx, eax
0x1800198e5  test    eax, eax
0x1800198e7  js      short loc_180019916
0x1800198e9  mov     rsi, [rbp+TokenInformation]
0x1800198ed  mov     r8, [rdi]; pSourceSid
0x1800198f0  mov     rdx, rsi; pDestinationSid
0x1800198f3  mov     ecx, [rbp+TokenInformationLength]; nDestinationSidLength
0x1800198f6  call    cs:__imp_CopySid
0x1800198fc  mov     ecx, eax; int
0x1800198fe  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180019903  mov     ebx, eax
0x180019905  test    eax, eax
0x180019907  js      short loc_18001990E
0x180019909  mov     [r14], rsi
0x18001990c  jmp     short loc_180019916
0x18001990e  mov     rcx, rsi; lpMem
0x180019911  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180019916  mov     rcx, rdi; lpMem
0x180019919  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18001991e  mov     rsi, [rsp+30h+arg_18]
0x180019923  mov     eax, ebx
0x180019925  mov     rbx, [rsp+30h+arg_0]
0x18001992a  add     rsp, 30h
0x18001992e  pop     r14
0x180019930  pop     rdi
0x180019931  pop     rbp
0x180019932  retn
```
