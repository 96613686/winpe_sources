# GetMD5HashFromFileHandle(void *,ulong * const)

- ea: `0x1800f2958`
- end: `0x1800f2b20`
- name: `?GetMD5HashFromFileHandle@@YAKPEAXQEAK@Z`
- size: `456`
- prototype: `unsigned int __fastcall(HANDLE hFile, unsigned int *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800f2804`

## callees

- `0x1800f2958`
- `0x18025ab2a`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800f2b09`
- `KERNEL32!GetLastError` at `0x1800f2b09`
- `KERNEL32!GlobalAlloc` at `0x1800f29a1`
- `KERNEL32!GlobalAlloc` at `0x1800f29a1`
- `KERNEL32!GlobalFree` at `0x1800f2ab1`
- `KERNEL32!GlobalFree` at `0x1800f2ae7`
- `KERNEL32!GlobalFree` at `0x1800f2af4`
- `KERNEL32!GlobalFree` at `0x1800f2ab1`
- `KERNEL32!GlobalFree` at `0x1800f2ae7`
- `KERNEL32!GlobalFree` at `0x1800f2af4`
- `KERNEL32!ReadFile` at `0x1800f2a31`
- `KERNEL32!ReadFile` at `0x1800f2a31`
- `bcrypt!BCryptFinishHash` at `0x1800f2a78`
- `bcrypt!BCryptFinishHash` at `0x1800f2a78`
- `bcrypt!BCryptCreateHash` at `0x1800f2a07`
- `bcrypt!BCryptCreateHash` at `0x1800f2a07`
- `bcrypt!BCryptHashData` at `0x1800f2a50`
- `bcrypt!BCryptHashData` at `0x1800f2a50`
- `bcrypt!BCryptDestroyHash` at `0x1800f2a8a`
- `bcrypt!BCryptDestroyHash` at `0x1800f2a8a`

## pseudocode

```c
__int64 __fastcall GetMD5HashFromFileHandle(HANDLE hFile, unsigned int *const a2)
{
  HGLOBAL v4; // rbx
  DWORD LastError; // ebx
  BOOL v6; // eax
  bool v7; // cc
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-40h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-38h]
  DWORD nNumberOfBytesToRead; // [rsp+50h] [rbp-30h]
  char v12; // [rsp+58h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v14; // [rsp+70h] [rbp-10h]

  nNumberOfBytesToRead = 1;
  lpBuffer = &v12;
  v4 = GlobalAlloc(0x40u, 0x7FFFu);
  if ( !v4 )
    return 8;
  if ( lpBuffer != &v12 )
    GlobalFree(lpBuffer);
  lpBuffer = v4;
  nNumberOfBytesToRead = 0x7FFF;
  memset_0(v4, 0, 0x7FFFu);
  NumberOfBytesRead = 0;
  v14 = 0;
  *(_OWORD *)phHash = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  LastError = 0;
  while ( 1 )
  {
    v6 = ReadFile(hFile, lpBuffer, nNumberOfBytesToRead, &NumberOfBytesRead, 0);
    if ( !v6 )
      break;
    if ( !NumberOfBytesRead )
      goto LABEL_12;
    if ( BCryptHashData(phHash[0], (PUCHAR)lpBuffer, NumberOfBytesRead, 0) < 0 )
      __fastfail(7u);
  }
  if ( !v6 )
    LastError = GetLastError();
LABEL_12:
  if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(phHash[0]);
  v7 = (int)nNumberOfBytesToRead <= 1;
  *(BCRYPT_HASH_HANDLE *)a2 = phHash[1];
  *((_QWORD *)a2 + 1) = v14;
  phHash[0] = 0;
  if ( !v7 )
    GlobalFree(lpBuffer);
  return LastError;
}

```

## disassembly

```asm
0x1800f2958  mov     [rsp-18h+arg_10], rbx
0x1800f295d  mov     [rsp-18h+arg_18], rsi
0x1800f2962  push    rbp
0x1800f2963  push    rdi
0x1800f2964  push    r12
0x1800f2966  mov     rbp, rsp
0x1800f2969  sub     rsp, 80h
0x1800f2970  mov     rax, cs:__security_cookie
0x1800f2977  xor     rax, rsp
0x1800f297a  mov     [rbp+var_8], rax
0x1800f297e  mov     rdi, rdx
0x1800f2981  mov     [rbp+nNumberOfBytesToRead], 1
0x1800f2988  mov     rsi, rcx
0x1800f298b  lea     rax, [rbp+var_28]
0x1800f298f  mov     r12d, 7FFFh
0x1800f2995  mov     [rbp+lpBuffer], rax
0x1800f2999  mov     edx, r12d; dwBytes
0x1800f299c  mov     ecx, 40h ; '@'; uFlags
0x1800f29a1  call    cs:__imp_GlobalAlloc
0x1800f29a7  mov     rbx, rax
0x1800f29aa  test    rax, rax
0x1800f29ad  jz      loc_1800F2ADD
0x1800f29b3  mov     rcx, [rbp+lpBuffer]; hMem
0x1800f29b7  lea     rax, [rbp+var_28]
0x1800f29bb  cmp     rcx, rax
0x1800f29be  jnz     loc_1800F2AF4
0x1800f29c4  mov     r8, r12; Size
0x1800f29c7  mov     [rbp+lpBuffer], rbx
0x1800f29cb  xor     edx, edx; Val
0x1800f29cd  mov     [rbp+nNumberOfBytesToRead], r12d
0x1800f29d1  mov     rcx, rbx; void *
0x1800f29d4  call    memset_0
0x1800f29d9  xor     eax, eax
0x1800f29db  mov     [rbp+NumberOfBytesRead], 0
0x1800f29e2  mov     [rsp+80h+dwFlags], eax; dwFlags
0x1800f29e6  lea     rdx, [rbp+phHash]; phHash
0x1800f29ea  xorps   xmm0, xmm0
0x1800f29ed  mov     [rsp+80h+cbSecret], eax; cbSecret
0x1800f29f1  xor     r9d, r9d; cbHashObject
0x1800f29f4  mov     [rbp+var_10], rax
0x1800f29f8  lea     ecx, [rax+21h]; hAlgorithm
0x1800f29fb  mov     [rsp+80h+pbSecret], rax; pbSecret
0x1800f2a00  xor     r8d, r8d; pbHashObject
0x1800f2a03  movups  xmmword ptr [rbp+phHash], xmm0
0x1800f2a07  call    cs:__imp_BCryptCreateHash
0x1800f2a0d  mov     r12d, 7
0x1800f2a13  test    eax, eax
0x1800f2a15  js      loc_1800F2AFF
0x1800f2a1b  xor     ebx, ebx
0x1800f2a1d  mov     r8d, [rbp+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x1800f2a21  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800f2a25  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x1800f2a29  mov     rcx, rsi; hFile
0x1800f2a2c  mov     [rsp+80h+pbSecret], rbx; lpOverlapped
0x1800f2a31  call    cs:__imp_ReadFile
0x1800f2a37  cmp     eax, 1
0x1800f2a3a  jnz     short loc_1800F2A61
0x1800f2a3c  mov     r8d, [rbp+NumberOfBytesRead]; cbInput
0x1800f2a40  test    r8d, r8d
0x1800f2a43  jz      short loc_1800F2A69
0x1800f2a45  mov     rdx, [rbp+lpBuffer]; pbInput
0x1800f2a49  xor     r9d, r9d; dwFlags
0x1800f2a4c  mov     rcx, [rbp+phHash]; hHash
0x1800f2a50  call    cs:__imp_BCryptHashData
0x1800f2a56  test    eax, eax
0x1800f2a58  jns     short loc_1800F2A1D
0x1800f2a5a  mov     rcx, r12
0x1800f2a5d  int     29h; Win8: RtlFailFast(ecx)
0x1800f2a5f  jmp     short loc_1800F2A1D
0x1800f2a61  test    eax, eax
0x1800f2a63  jz      loc_1800F2B09
0x1800f2a69  mov     rcx, [rbp+phHash]; hHash
0x1800f2a6d  lea     rdx, [rbp+phHash+8]; pbOutput
0x1800f2a71  xor     r9d, r9d; dwFlags
0x1800f2a74  lea     r8d, [r9+10h]; cbOutput
0x1800f2a78  call    cs:__imp_BCryptFinishHash
0x1800f2a7e  test    eax, eax
0x1800f2a80  js      loc_1800F2B16
0x1800f2a86  mov     rcx, [rbp+phHash]; hHash
0x1800f2a8a  call    cs:__imp_BCryptDestroyHash
0x1800f2a90  cmp     [rbp+nNumberOfBytesToRead], 1
0x1800f2a94  mov     rax, [rbp+phHash+8]
0x1800f2a98  mov     [rdi], rax
0x1800f2a9b  mov     rax, [rbp+var_10]
0x1800f2a9f  mov     [rdi+8], rax
0x1800f2aa3  mov     [rbp+phHash], 0
0x1800f2aab  jle     short loc_1800F2AB7
0x1800f2aad  mov     rcx, [rbp+lpBuffer]; hMem
0x1800f2ab1  call    cs:__imp_GlobalFree
0x1800f2ab7  mov     eax, ebx
0x1800f2ab9  mov     rcx, [rbp+var_8]
0x1800f2abd  xor     rcx, rsp; StackCookie
0x1800f2ac0  call    __security_check_cookie
0x1800f2ac5  lea     r11, [rsp+80h+var_s0]
0x1800f2acd  mov     rbx, [r11+30h]
0x1800f2ad1  mov     rsi, [r11+38h]
0x1800f2ad5  mov     rsp, r11
0x1800f2ad8  pop     r12
0x1800f2ada  pop     rdi
0x1800f2adb  pop     rbp
0x1800f2adc  retn
0x1800f2add  cmp     [rbp+nNumberOfBytesToRead], 1
0x1800f2ae1  jle     short loc_1800F2AED
0x1800f2ae3  mov     rcx, [rbp+lpBuffer]; hMem
0x1800f2ae7  call    cs:__imp_GlobalFree
0x1800f2aed  mov     eax, 8
0x1800f2af2  jmp     short loc_1800F2AB9
0x1800f2af4  call    cs:__imp_GlobalFree
0x1800f2afa  jmp     loc_1800F29C4
0x1800f2aff  mov     rcx, r12
0x1800f2b02  int     29h; Win8: RtlFailFast(ecx)
0x1800f2b04  jmp     loc_1800F2A1B
0x1800f2b09  call    cs:__imp_GetLastError
0x1800f2b0f  mov     ebx, eax
0x1800f2b11  jmp     loc_1800F2A69
0x1800f2b16  mov     rcx, r12
0x1800f2b19  int     29h; Win8: RtlFailFast(ecx)
0x1800f2b1b  jmp     loc_1800F2A86
```
