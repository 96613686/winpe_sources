# GetMD5HashFromFileHandle(void *,ulong * const)

- ea: `0x1800fe6ec`
- end: `0x1800fe8f1`
- name: `?GetMD5HashFromFileHandle@@YAKPEAXQEAK@Z`
- size: `517`
- prototype: `unsigned int __fastcall(HANDLE hFile, unsigned int *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800fe574`

## callees

- `0x1800fe6ec`
- `0x1802651ea`
- `0x180265240`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800fe8d4`
- `KERNEL32!GetLastError` at `0x1800fe8d4`
- `KERNEL32!GlobalAlloc` at `0x1800fe735`
- `KERNEL32!GlobalAlloc` at `0x1800fe735`
- `KERNEL32!GlobalFree` at `0x1800fe869`
- `KERNEL32!GlobalFree` at `0x1800fe8a6`
- `KERNEL32!GlobalFree` at `0x1800fe8b9`
- `KERNEL32!GlobalFree` at `0x1800fe869`
- `KERNEL32!GlobalFree` at `0x1800fe8a6`
- `KERNEL32!GlobalFree` at `0x1800fe8b9`
- `KERNEL32!ReadFile` at `0x1800fe7d1`
- `KERNEL32!ReadFile` at `0x1800fe7d1`
- `bcrypt!BCryptFinishHash` at `0x1800fe824`
- `bcrypt!BCryptFinishHash` at `0x1800fe824`
- `bcrypt!BCryptCreateHash` at `0x1800fe7a1`
- `bcrypt!BCryptCreateHash` at `0x1800fe7a1`
- `bcrypt!BCryptHashData` at `0x1800fe7f6`
- `bcrypt!BCryptHashData` at `0x1800fe7f6`
- `bcrypt!BCryptDestroyHash` at `0x1800fe83c`
- `bcrypt!BCryptDestroyHash` at `0x1800fe83c`

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
0x1800fe6ec  mov     [rsp-18h+arg_10], rbx
0x1800fe6f1  mov     [rsp-18h+arg_18], rsi
0x1800fe6f6  push    rbp
0x1800fe6f7  push    rdi
0x1800fe6f8  push    r12
0x1800fe6fa  mov     rbp, rsp
0x1800fe6fd  sub     rsp, 80h
0x1800fe704  mov     rax, cs:__security_cookie
0x1800fe70b  xor     rax, rsp
0x1800fe70e  mov     [rbp+var_8], rax
0x1800fe712  mov     rdi, rdx
0x1800fe715  mov     [rbp+nNumberOfBytesToRead], 1
0x1800fe71c  mov     rsi, rcx
0x1800fe71f  lea     rax, [rbp+var_28]
0x1800fe723  mov     r12d, 7FFFh
0x1800fe729  mov     [rbp+lpBuffer], rax
0x1800fe72d  mov     edx, r12d; dwBytes
0x1800fe730  mov     ecx, 40h ; '@'; uFlags
0x1800fe735  call    cs:__imp_GlobalAlloc
0x1800fe73c  nop     dword ptr [rax+rax+00h]
0x1800fe741  mov     rbx, rax
0x1800fe744  test    rax, rax
0x1800fe747  jz      loc_1800FE89C
0x1800fe74d  mov     rcx, [rbp+lpBuffer]; hMem
0x1800fe751  lea     rax, [rbp+var_28]
0x1800fe755  cmp     rcx, rax
0x1800fe758  jnz     loc_1800FE8B9
0x1800fe75e  mov     r8, r12; Size
0x1800fe761  mov     [rbp+lpBuffer], rbx
0x1800fe765  xor     edx, edx; Val
0x1800fe767  mov     [rbp+nNumberOfBytesToRead], r12d
0x1800fe76b  mov     rcx, rbx; void *
0x1800fe76e  call    memset_0
0x1800fe773  xor     eax, eax
0x1800fe775  mov     [rbp+NumberOfBytesRead], 0
0x1800fe77c  mov     [rsp+80h+dwFlags], eax; dwFlags
0x1800fe780  lea     rdx, [rbp+phHash]; phHash
0x1800fe784  xorps   xmm0, xmm0
0x1800fe787  mov     [rsp+80h+cbSecret], eax; cbSecret
0x1800fe78b  xor     r9d, r9d; cbHashObject
0x1800fe78e  mov     [rbp+var_10], rax
0x1800fe792  lea     ecx, [rax+21h]; hAlgorithm
0x1800fe795  mov     [rsp+80h+pbSecret], rax; pbSecret
0x1800fe79a  xor     r8d, r8d; pbHashObject
0x1800fe79d  movups  xmmword ptr [rbp+phHash], xmm0
0x1800fe7a1  call    cs:__imp_BCryptCreateHash
0x1800fe7a8  nop     dword ptr [rax+rax+00h]
0x1800fe7ad  mov     r12d, 7
0x1800fe7b3  test    eax, eax
0x1800fe7b5  js      loc_1800FE8CA
0x1800fe7bb  xor     ebx, ebx
0x1800fe7bd  mov     r8d, [rbp+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x1800fe7c1  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800fe7c5  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x1800fe7c9  mov     rcx, rsi; hFile
0x1800fe7cc  mov     [rsp+80h+pbSecret], rbx; lpOverlapped
0x1800fe7d1  call    cs:__imp_ReadFile
0x1800fe7d8  nop     dword ptr [rax+rax+00h]
0x1800fe7dd  cmp     eax, 1
0x1800fe7e0  jnz     short loc_1800FE80D
0x1800fe7e2  mov     r8d, [rbp+NumberOfBytesRead]; cbInput
0x1800fe7e6  test    r8d, r8d
0x1800fe7e9  jz      short loc_1800FE815
0x1800fe7eb  mov     rdx, [rbp+lpBuffer]; pbInput
0x1800fe7ef  xor     r9d, r9d; dwFlags
0x1800fe7f2  mov     rcx, [rbp+phHash]; hHash
0x1800fe7f6  call    cs:__imp_BCryptHashData
0x1800fe7fd  nop     dword ptr [rax+rax+00h]
0x1800fe802  test    eax, eax
0x1800fe804  jns     short loc_1800FE7BD
0x1800fe806  mov     rcx, r12
0x1800fe809  int     29h; Win8: RtlFailFast(ecx)
0x1800fe80b  jmp     short loc_1800FE7BD
0x1800fe80d  test    eax, eax
0x1800fe80f  jz      loc_1800FE8D4
0x1800fe815  mov     rcx, [rbp+phHash]; hHash
0x1800fe819  lea     rdx, [rbp+phHash+8]; pbOutput
0x1800fe81d  xor     r9d, r9d; dwFlags
0x1800fe820  lea     r8d, [r9+10h]; cbOutput
0x1800fe824  call    cs:__imp_BCryptFinishHash
0x1800fe82b  nop     dword ptr [rax+rax+00h]
0x1800fe830  test    eax, eax
0x1800fe832  js      loc_1800FE8E7
0x1800fe838  mov     rcx, [rbp+phHash]; hHash
0x1800fe83c  call    cs:__imp_BCryptDestroyHash
0x1800fe843  nop     dword ptr [rax+rax+00h]
0x1800fe848  cmp     [rbp+nNumberOfBytesToRead], 1
0x1800fe84c  mov     rax, [rbp+phHash+8]
0x1800fe850  mov     [rdi], rax
0x1800fe853  mov     rax, [rbp+var_10]
0x1800fe857  mov     [rdi+8], rax
0x1800fe85b  mov     [rbp+phHash], 0
0x1800fe863  jle     short loc_1800FE875
0x1800fe865  mov     rcx, [rbp+lpBuffer]; hMem
0x1800fe869  call    cs:__imp_GlobalFree
0x1800fe870  nop     dword ptr [rax+rax+00h]
0x1800fe875  mov     eax, ebx
0x1800fe877  mov     rcx, [rbp+var_8]
0x1800fe87b  xor     rcx, rsp; StackCookie
0x1800fe87e  call    __security_check_cookie
0x1800fe883  lea     r11, [rsp+80h+var_s0]
0x1800fe88b  mov     rbx, [r11+30h]
0x1800fe88f  mov     rsi, [r11+38h]
0x1800fe893  mov     rsp, r11
0x1800fe896  pop     r12
0x1800fe898  pop     rdi
0x1800fe899  pop     rbp
0x1800fe89a  retn
0x1800fe89c  cmp     [rbp+nNumberOfBytesToRead], 1
0x1800fe8a0  jle     short loc_1800FE8B2
0x1800fe8a2  mov     rcx, [rbp+lpBuffer]; hMem
0x1800fe8a6  call    cs:__imp_GlobalFree
0x1800fe8ad  nop     dword ptr [rax+rax+00h]
0x1800fe8b2  mov     eax, 8
0x1800fe8b7  jmp     short loc_1800FE877
0x1800fe8b9  call    cs:__imp_GlobalFree
0x1800fe8c0  nop     dword ptr [rax+rax+00h]
0x1800fe8c5  jmp     loc_1800FE75E
0x1800fe8ca  mov     rcx, r12
0x1800fe8cd  int     29h; Win8: RtlFailFast(ecx)
0x1800fe8cf  jmp     loc_1800FE7BB
0x1800fe8d4  call    cs:__imp_GetLastError
0x1800fe8db  nop     dword ptr [rax+rax+00h]
0x1800fe8e0  mov     ebx, eax
0x1800fe8e2  jmp     loc_1800FE815
0x1800fe8e7  mov     rcx, r12
0x1800fe8ea  int     29h; Win8: RtlFailFast(ecx)
0x1800fe8ec  jmp     loc_1800FE838
```
