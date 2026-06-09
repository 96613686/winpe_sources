# GetSidString(void *,ushort * *)

- ea: `0x180004b80`
- end: `0x180004d8c`
- name: `?GetSidString@@YAJPEAXPEAPEAG@Z`
- size: `524`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034438`

## callees

- `0x180004170`
- `0x180004b80`
- `0x180004ff4`
- `0x180006580`
- `0x18003e8fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004bb4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004c1b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004bb4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004c1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004caf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004c5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004caf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ba0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ca1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ba0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ca1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004c37`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004c37`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004bfe`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004bfe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004be7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004d1e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004be7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004d1e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004c84`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004c84`

## pseudocode

```c
__int64 __fastcall GetSidString(HANDLE TokenHandle, unsigned __int16 **a2)
{
  HANDLE ProcessHeap; // rax
  LPWSTR v5; // rbx
  void *v6; // rsi
  int Error; // edi
  DWORD LengthSid; // edi
  HANDLE v9; // rax
  void *v10; // rax
  void *v11; // rbp
  HANDLE v12; // rax
  int v13; // ebx
  HANDLE v14; // rax
  int v16; // eax
  BOOL TokenInformation; // eax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+20h] BYREF

  TokenInformationLength = 200;
  ProcessHeap = GetProcessHeap();
  StringSid = (LPWSTR)HeapAlloc(ProcessHeap, 8u, 0xC8u);
  v5 = StringSid;
  if ( !StringSid )
    return (unsigned int)-2147024882;
  v6 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, StringSid, TokenInformationLength, &TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      v16 = ResultFromHeapReAlloc(v5, TokenInformationLength, (void **)&StringSid);
      v5 = StringSid;
      Error = v16;
      if ( v16 < 0 )
        goto LABEL_9;
      TokenInformation = GetTokenInformation(
                           TokenHandle,
                           TokenUser,
                           StringSid,
                           TokenInformationLength,
                           &TokenInformationLength);
      Error = ResultFromWin32Bool(TokenInformation);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*(PSID *)v5);
    TokenInformationLength = LengthSid;
    v9 = GetProcessHeap();
    v10 = HeapAlloc(v9, 8u, LengthSid);
    v11 = v10;
    if ( !v10 )
    {
      Error = -2147024882;
      goto LABEL_9;
    }
    if ( CopySid(TokenInformationLength, v10, *(PSID *)v5) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        ResultFromHeapFree(v11);
        goto LABEL_9;
      }
    }
    v6 = v11;
  }
LABEL_9:
  if ( v5 )
  {
    v12 = GetProcessHeap();
    if ( !HeapFree(v12, 0, v5) )
      ResultFromKnownLastError();
  }
  if ( Error < 0 )
    return (unsigned int)Error;
  StringSid = 0;
  if ( ConvertSidToStringSidW(v6, &StringSid) )
  {
    v13 = 0;
  }
  else
  {
    v13 = ResultFromKnownLastError();
    if ( v13 < 0 )
      goto LABEL_16;
  }
  *a2 = StringSid;
LABEL_16:
  if ( v6 )
  {
    v14 = GetProcessHeap();
    if ( !HeapFree(v14, 0, v6) )
      ResultFromKnownLastError();
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180004b80  mov     [rsp+arg_0], rbx
0x180004b85  mov     [rsp+arg_8], rbp
0x180004b8a  push    rsi
0x180004b8b  push    rdi
0x180004b8c  push    r14
0x180004b8e  sub     rsp, 30h
0x180004b92  mov     r14, rdx
0x180004b95  mov     [rsp+48h+TokenInformationLength], 0C8h
0x180004b9d  mov     rbp, rcx
0x180004ba0  call    cs:__imp_GetProcessHeap
0x180004ba6  mov     edx, 8; dwFlags
0x180004bab  mov     r8d, 0C8h; dwBytes
0x180004bb1  mov     rcx, rax; hHeap
0x180004bb4  call    cs:__imp_HeapAlloc
0x180004bba  mov     [rsp+48h+StringSid], rax
0x180004bbf  mov     rbx, rax
0x180004bc2  test    rax, rax
0x180004bc5  jz      loc_180004D80
0x180004bcb  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180004bd0  lea     rax, [rsp+48h+TokenInformationLength]
0x180004bd5  mov     r8, rbx; TokenInformation
0x180004bd8  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180004bdd  mov     edx, 1; TokenInformationClass
0x180004be2  mov     rcx, rbp; TokenHandle
0x180004be5  xor     esi, esi
0x180004be7  call    cs:__imp_GetTokenInformation
0x180004bed  test    eax, eax
0x180004bef  jz      loc_180004CD2
0x180004bf5  xor     edi, edi
0x180004bf7  test    edi, edi
0x180004bf9  js      short loc_180004C4A
0x180004bfb  mov     rcx, [rbx]; pSid
0x180004bfe  call    cs:__imp_GetLengthSid
0x180004c04  mov     edi, eax
0x180004c06  mov     [rsp+48h+TokenInformationLength], edi
0x180004c0a  call    cs:__imp_GetProcessHeap
0x180004c10  mov     r8d, edi; dwBytes
0x180004c13  mov     edx, 8; dwFlags
0x180004c18  mov     rcx, rax; hHeap
0x180004c1b  call    cs:__imp_HeapAlloc
0x180004c21  mov     rbp, rax
0x180004c24  test    rax, rax
0x180004c27  jz      loc_180004D62
0x180004c2d  mov     r8, [rbx]; pSourceSid
0x180004c30  mov     rdx, rax; pDestinationSid
0x180004c33  mov     ecx, [rsp+48h+TokenInformationLength]; nDestinationSidLength
0x180004c37  call    cs:__imp_CopySid
0x180004c3d  test    eax, eax
0x180004c3f  jz      loc_180004D46
0x180004c45  xor     edi, edi
0x180004c47  mov     rsi, rbp
0x180004c4a  test    rbx, rbx
0x180004c4d  jz      short loc_180004C6B
0x180004c4f  call    cs:__imp_GetProcessHeap
0x180004c55  mov     r8, rbx; lpMem
0x180004c58  xor     edx, edx; dwFlags
0x180004c5a  mov     rcx, rax; hHeap
0x180004c5d  call    cs:__imp_HeapFree
0x180004c63  test    eax, eax
0x180004c65  jz      loc_180004D6C
0x180004c6b  test    edi, edi
0x180004c6d  js      loc_180004D85
0x180004c73  lea     rdx, [rsp+48h+StringSid]; StringSid
0x180004c78  mov     [rsp+48h+StringSid], 0
0x180004c81  mov     rcx, rsi; Sid
0x180004c84  call    cs:__imp_ConvertSidToStringSidW
0x180004c8a  test    eax, eax
0x180004c8c  jz      loc_180004D32
0x180004c92  xor     ebx, ebx
0x180004c94  mov     rax, [rsp+48h+StringSid]
0x180004c99  mov     [r14], rax
0x180004c9c  test    rsi, rsi
0x180004c9f  jz      short loc_180004CBD
0x180004ca1  call    cs:__imp_GetProcessHeap
0x180004ca7  mov     r8, rsi; lpMem
0x180004caa  xor     edx, edx; dwFlags
0x180004cac  mov     rcx, rax; hHeap
0x180004caf  call    cs:__imp_HeapFree
0x180004cb5  test    eax, eax
0x180004cb7  jz      loc_180004D76
0x180004cbd  mov     eax, ebx
0x180004cbf  mov     rbx, [rsp+48h+arg_0]
0x180004cc4  mov     rbp, [rsp+48h+arg_8]
0x180004cc9  add     rsp, 30h
0x180004ccd  pop     r14
0x180004ccf  pop     rdi
0x180004cd0  pop     rsi
0x180004cd1  retn
0x180004cd2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004cd7  mov     edi, eax
0x180004cd9  cmp     eax, 8007007Ah
0x180004cde  jnz     loc_180004BF7
0x180004ce4  mov     edx, [rsp+48h+TokenInformationLength]; dwBytes
0x180004ce8  lea     r8, [rsp+48h+StringSid]; void **
0x180004ced  mov     rcx, rbx; lpMem
0x180004cf0  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180004cf5  mov     rbx, [rsp+48h+StringSid]
0x180004cfa  mov     edi, eax
0x180004cfc  test    eax, eax
0x180004cfe  js      loc_180004C4A
0x180004d04  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180004d09  lea     rax, [rsp+48h+TokenInformationLength]
0x180004d0e  mov     r8, rbx; TokenInformation
0x180004d11  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180004d16  mov     edx, 1; TokenInformationClass
0x180004d1b  mov     rcx, rbp; TokenHandle
0x180004d1e  call    cs:__imp_GetTokenInformation
0x180004d24  mov     ecx, eax; int
0x180004d26  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180004d2b  mov     edi, eax
0x180004d2d  jmp     loc_180004BF7
0x180004d32  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004d37  mov     ebx, eax
0x180004d39  test    eax, eax
0x180004d3b  jns     loc_180004C94
0x180004d41  jmp     loc_180004C9C
0x180004d46  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004d4b  mov     edi, eax
0x180004d4d  test    eax, eax
0x180004d4f  jns     loc_180004C47
0x180004d55  mov     rcx, rbp; lpMem
0x180004d58  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180004d5d  jmp     loc_180004C4A
0x180004d62  mov     edi, 8007000Eh
0x180004d67  jmp     loc_180004C4A
0x180004d6c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004d71  jmp     loc_180004C6B
0x180004d76  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004d7b  jmp     loc_180004CBD
0x180004d80  mov     edi, 8007000Eh
0x180004d85  mov     eax, edi
0x180004d87  jmp     loc_180004CBF
```
