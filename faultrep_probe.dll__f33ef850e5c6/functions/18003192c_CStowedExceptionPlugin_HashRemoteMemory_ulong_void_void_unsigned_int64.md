# CStowedExceptionPlugin::HashRemoteMemory(ulong *,void *,void *,unsigned __int64)

- ea: `0x18003192c`
- end: `0x180031b18`
- name: `?HashRemoteMemory@CStowedExceptionPlugin@@CAJPEAKPEAX1_K@Z`
- size: `492`
- prototype: `__int64 __fastcall(unsigned int *, HANDLE hProcess, void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031d50`

## callees

- `0x180002890`
- `0x180031850`
- `0x18003192c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ac4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800319f1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800319f1`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180031983`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180031983`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180031af3`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180031af3`
- `bcrypt!BCryptDestroyHash` at `0x180031a4c`
- `bcrypt!BCryptDestroyHash` at `0x180031ab4`
- `bcrypt!BCryptDestroyHash` at `0x180031a4c`
- `bcrypt!BCryptDestroyHash` at `0x180031ab4`
- `bcrypt!BCryptHashData` at `0x180031a0e`
- `bcrypt!BCryptHashData` at `0x180031a0e`
- `bcrypt!BCryptCreateHash` at `0x1800319b5`
- `bcrypt!BCryptCreateHash` at `0x1800319b5`
- `bcrypt!BCryptFinishHash` at `0x180031a37`
- `bcrypt!BCryptFinishHash` at `0x180031a9f`
- `bcrypt!BCryptFinishHash` at `0x180031a37`
- `bcrypt!BCryptFinishHash` at `0x180031a9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStowedExceptionPlugin::HashRemoteMemory(
        unsigned int *a1,
        HANDLE hProcess,
        char *a3,
        unsigned __int64 a4)
{
  void *v8; // rsi
  unsigned __int64 v9; // rbx
  SIZE_T v10; // rdi
  signed int v11; // ebx
  signed int LastError; // eax
  signed int v13; // eax
  SIZE_T NumberOfBytesRead[2]; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v17; // [rsp+60h] [rbp-18h]

  NumberOfBytesRead[0] = 0;
  *(_OWORD *)phHash = 0;
  v17 = 0;
  *a1 = 0;
  v8 = VirtualAlloc(0, 0x1000u, 0x1000u, 4u);
  NumberOfBytesRead[1] = (SIZE_T)v8;
  if ( v8 )
  {
    v9 = 0;
    if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
      __fastfail(7u);
    if ( a4 )
    {
      while ( 1 )
      {
        v10 = a4 - v9;
        if ( a4 - v9 > 0x1000 )
          v10 = 4096;
        if ( !ReadProcessMemory(hProcess, &a3[v9], v8, v10, NumberOfBytesRead) )
          break;
        if ( NumberOfBytesRead[0] != v10 )
        {
          v11 = -2147024597;
          goto LABEL_20;
        }
        if ( BCryptHashData(phHash[0], (PUCHAR)v8, NumberOfBytesRead[0], 0) < 0 )
          __fastfail(7u);
        v9 += NumberOfBytesRead[0];
        if ( v9 >= a4 )
          goto LABEL_12;
      }
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
LABEL_20:
      if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
        __fastfail(7u);
      BCryptDestroyHash(phHash[0]);
      phHash[0] = 0;
    }
    else
    {
LABEL_12:
      if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
        __fastfail(7u);
      BCryptDestroyHash(phHash[0]);
      phHash[0] = 0;
      CStowedExceptionPlugin::CompactMD5Digest(a1, (unsigned __int8 *)&phHash[1]);
      v11 = 0;
    }
  }
  else
  {
    v13 = GetLastError();
    v11 = v13;
    if ( v13 > 0 )
      v11 = (unsigned __int16)v13 | 0x80070000;
    if ( v11 >= 0 )
      v11 = -2147467259;
  }
  if ( v8 )
    VirtualFree(v8, 0, 0x8000u);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003192c  push    rbp
0x18003192e  push    rbx
0x18003192f  push    rsi
0x180031930  push    rdi
0x180031931  push    r12
0x180031933  push    r13
0x180031935  push    r14
0x180031937  push    r15
0x180031939  mov     rbp, rsp
0x18003193c  sub     rsp, 78h
0x180031940  mov     rax, cs:__security_cookie
0x180031947  xor     rax, rsp
0x18003194a  mov     [rbp+var_10], rax
0x18003194e  mov     r14, r9
0x180031951  mov     r13, r8
0x180031954  mov     r12, rdx
0x180031957  mov     r15, rcx
0x18003195a  mov     [rbp+NumberOfBytesRead], 0
0x180031962  xorps   xmm0, xmm0
0x180031965  xor     eax, eax
0x180031967  movups  xmmword ptr [rbp+phHash], xmm0
0x18003196b  mov     [rbp+var_18], rax
0x18003196f  mov     [rcx], eax
0x180031971  mov     eax, 1000h
0x180031976  mov     r9d, 4; flProtect
0x18003197c  mov     r8d, eax; flAllocationType
0x18003197f  mov     edx, eax; dwSize
0x180031981  xor     ecx, ecx; lpAddress
0x180031983  call    cs:__imp_VirtualAlloc
0x180031989  mov     rsi, rax
0x18003198c  mov     [rbp+var_30], rax
0x180031990  test    rax, rax
0x180031993  jz      loc_180031AC4
0x180031999  xor     ebx, ebx
0x18003199b  mov     [rsp+78h+dwFlags], ebx; dwFlags
0x18003199f  mov     [rsp+78h+cbSecret], ebx; cbSecret
0x1800319a3  mov     [rsp+78h+pbSecret], rbx; pbSecret
0x1800319a8  xor     r9d, r9d; cbHashObject
0x1800319ab  xor     r8d, r8d; pbHashObject
0x1800319ae  lea     rdx, [rbp+phHash]; phHash
0x1800319b2  lea     ecx, [rbx+21h]; hAlgorithm
0x1800319b5  call    cs:__imp_BCryptCreateHash
0x1800319bb  test    eax, eax
0x1800319bd  jns     short loc_1800319C4
0x1800319bf  lea     ecx, [rbx+7]
0x1800319c2  int     29h; Win8: RtlFailFast(ecx)
0x1800319c4  test    r14, r14
0x1800319c7  jz      short loc_180031A28
0x1800319c9  mov     rdi, r14
0x1800319cc  sub     rdi, rbx
0x1800319cf  mov     eax, 1000h
0x1800319d4  cmp     rdi, rax
0x1800319d7  cmova   rdi, rax
0x1800319db  lea     rdx, [rbx+r13]; lpBaseAddress
0x1800319df  lea     rax, [rbp+NumberOfBytesRead]
0x1800319e3  mov     [rsp+78h+pbSecret], rax; lpNumberOfBytesRead
0x1800319e8  mov     r9, rdi; nSize
0x1800319eb  mov     r8, rsi; lpBuffer
0x1800319ee  mov     rcx, r12; hProcess
0x1800319f1  call    cs:__imp_ReadProcessMemory
0x1800319f7  test    eax, eax
0x1800319f9  jz      short loc_180031A71
0x1800319fb  mov     r8, [rbp+NumberOfBytesRead]; cbInput
0x1800319ff  cmp     r8, rdi
0x180031a02  jnz     short loc_180031A6A
0x180031a04  xor     r9d, r9d; dwFlags
0x180031a07  mov     rdx, rsi; pbInput
0x180031a0a  mov     rcx, [rbp+phHash]; hHash
0x180031a0e  call    cs:__imp_BCryptHashData
0x180031a14  test    eax, eax
0x180031a16  jns     short loc_180031A1F
0x180031a18  mov     ecx, 7
0x180031a1d  int     29h; Win8: RtlFailFast(ecx)
0x180031a1f  add     rbx, [rbp+NumberOfBytesRead]
0x180031a23  cmp     rbx, r14
0x180031a26  jb      short loc_1800319C9
0x180031a28  xor     r9d, r9d; dwFlags
0x180031a2b  lea     r8d, [r9+10h]; cbOutput
0x180031a2f  lea     rdx, [rbp+phHash+8]; pbOutput
0x180031a33  mov     rcx, [rbp+phHash]; hHash
0x180031a37  call    cs:__imp_BCryptFinishHash
0x180031a3d  test    eax, eax
0x180031a3f  jns     short loc_180031A48
0x180031a41  mov     ecx, 7
0x180031a46  int     29h; Win8: RtlFailFast(ecx)
0x180031a48  mov     rcx, [rbp+phHash]; hHash
0x180031a4c  call    cs:__imp_BCryptDestroyHash
0x180031a52  mov     [rbp+phHash], 0
0x180031a5a  lea     rdx, [rbp+phHash+8]; unsigned __int8 *
0x180031a5e  mov     rcx, r15; unsigned int *
0x180031a61  call    ?CompactMD5Digest@CStowedExceptionPlugin@@CAXPEAKPEAE@Z; CStowedExceptionPlugin::CompactMD5Digest(ulong *,uchar *)
0x180031a66  xor     ebx, ebx
0x180031a68  jmp     short loc_180031AE3
0x180031a6a  mov     ebx, 8007012Bh
0x180031a6f  jmp     short loc_180031A90
0x180031a71  call    cs:__imp_GetLastError
0x180031a77  mov     ebx, eax
0x180031a79  test    eax, eax
0x180031a7b  jle     short loc_180031A86
0x180031a7d  movzx   ebx, ax
0x180031a80  or      ebx, 80070000h
0x180031a86  mov     eax, 80004005h
0x180031a8b  test    ebx, ebx
0x180031a8d  cmovns  ebx, eax
0x180031a90  xor     r9d, r9d; dwFlags
0x180031a93  lea     r8d, [r9+10h]; cbOutput
0x180031a97  lea     rdx, [rbp+phHash+8]; pbOutput
0x180031a9b  mov     rcx, [rbp+phHash]; hHash
0x180031a9f  call    cs:__imp_BCryptFinishHash
0x180031aa5  test    eax, eax
0x180031aa7  jns     short loc_180031AB0
0x180031aa9  mov     ecx, 7
0x180031aae  int     29h; Win8: RtlFailFast(ecx)
0x180031ab0  mov     rcx, [rbp+phHash]; hHash
0x180031ab4  call    cs:__imp_BCryptDestroyHash
0x180031aba  mov     [rbp+phHash], 0
0x180031ac2  jmp     short loc_180031AE3
0x180031ac4  call    cs:__imp_GetLastError
0x180031aca  mov     ebx, eax
0x180031acc  test    eax, eax
0x180031ace  jle     short loc_180031AD9
0x180031ad0  movzx   ebx, ax
0x180031ad3  or      ebx, 80070000h
0x180031ad9  mov     eax, 80004005h
0x180031ade  test    ebx, ebx
0x180031ae0  cmovns  ebx, eax
0x180031ae3  test    rsi, rsi
0x180031ae6  jz      short loc_180031AF9
0x180031ae8  xor     edx, edx; dwSize
0x180031aea  mov     r8d, 8000h; dwFreeType
0x180031af0  mov     rcx, rsi; lpAddress
0x180031af3  call    cs:__imp_VirtualFree
0x180031af9  mov     eax, ebx
0x180031afb  mov     rcx, [rbp+var_10]
0x180031aff  xor     rcx, rsp; StackCookie
0x180031b02  call    __security_check_cookie
0x180031b07  add     rsp, 78h
0x180031b0b  pop     r15
0x180031b0d  pop     r14
0x180031b0f  pop     r13
0x180031b11  pop     r12
0x180031b13  pop     rdi
0x180031b14  pop     rsi
0x180031b15  pop     rbx
0x180031b16  pop     rbp
0x180031b17  retn
```
