# NfsCreatePFsPersistentPath

- ea: `0x18002d2b4`
- end: `0x18002d455`
- name: `NfsCreatePFsPersistentPath`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x18002d45c`

## callees

- `0x18002be68`
- `0x18002c964`
- `0x18002cb04`
- `0x18002cc78`
- `0x18002cd8c`
- `0x18002d19c`
- `0x18002d1f8`
- `0x18002d2b4`
- `0x180035b02`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002d431`
- `KERNEL32!HeapFree` at `0x18002d431`
- `KERNEL32!HeapAlloc` at `0x18002d353`
- `KERNEL32!HeapAlloc` at `0x18002d353`
- `KERNEL32!GetProcessHeap` at `0x18002d342`
- `KERNEL32!GetProcessHeap` at `0x18002d423`
- `KERNEL32!GetProcessHeap` at `0x18002d342`
- `KERNEL32!GetProcessHeap` at `0x18002d423`

## pseudocode

```c
__int64 __fastcall NfsCreatePFsPersistentPath(_WORD *a1, __int64 a2, __int64 a3, unsigned int *a4, _QWORD *a5, int a6)
{
  int v7; // r14d
  _WORD *v8; // r8
  unsigned int v9; // r10d
  __int16 v10; // ax
  __int16 v11; // ax
  _WORD *v12; // rcx
  bool v13; // zf
  unsigned int v14; // eax
  SIZE_T v15; // rbx
  HANDLE ProcessHeap; // rax
  void *v17; // rax
  void *v18; // rsi
  unsigned int v20; // eax
  unsigned int ReturnPFsPersistentPathRecursive; // ebx
  char v22; // di
  int v23; // r9d
  __int64 v24; // rdx
  HANDLE v25; // rax
  HKEY phkResult; // [rsp+70h] [rbp+30h] BYREF
  bool v27; // [rsp+80h] [rbp+40h] BYREF

  v7 = (int)a1;
  phkResult = 0;
  v8 = a1;
  a6 = 0;
  v9 = 0;
  v27 = 0;
  if ( *a1 )
  {
    do
    {
      v10 = *v8;
      do
      {
        if ( v10 != 47 )
          break;
        v10 = *++v8;
      }
      while ( *v8 );
      v11 = *v8;
      v12 = v8;
      while ( v11 && v11 != 47 )
        v11 = *++v12;
      v13 = v12 == v8;
      v14 = v9 + 1;
      v8 = v12;
      if ( v13 )
        v14 = v9;
      v9 = v14;
    }
    while ( *v12 );
  }
  v15 = 4LL * v9;
  *a4 = v9;
  ProcessHeap = GetProcessHeap();
  v17 = HeapAlloc(ProcessHeap, 8u, v15);
  v18 = v17;
  if ( !v17 )
    return 8;
  memset_0(v17, 0, v15);
  if ( a2 )
    v20 = PFsPersistOpenClusterRootKey(&phkResult, a2);
  else
    v20 = PFsPersistOpenLocalRootKey(&phkResult);
  ReturnPFsPersistentPathRecursive = v20;
  if ( !v20 )
  {
    v22 = a2 != 0;
    ReturnPFsPersistentPathRecursive = QueryPFsIdSequenceNumber(phkResult, v22, &a6, &v27);
    if ( !ReturnPFsPersistentPathRecursive )
    {
      LOBYTE(v23) = v22;
      ReturnPFsPersistentPathRecursive = CreateReturnPFsPersistentPathRecursive(
                                           (_DWORD)phkResult,
                                           (_DWORD)phkResult,
                                           v7,
                                           v23);
      if ( !ReturnPFsPersistentPathRecursive )
      {
        ReturnPFsPersistentPathRecursive = SetPFsIdSequenceNumber(phkResult, v22, a6);
        if ( ReturnPFsPersistentPathRecursive )
        {
          if ( !v27 )
            SetPFsIdSequenceNumberDuplicateCheck(phkResult, v22, 1);
        }
      }
      LOBYTE(v24) = v22;
      NfsPFsCloseKey(phkResult, v24);
      if ( !ReturnPFsPersistentPathRecursive )
        goto LABEL_25;
    }
  }
  v25 = GetProcessHeap();
  HeapFree(v25, 0, v18);
  if ( !ReturnPFsPersistentPathRecursive )
LABEL_25:
    *a5 = v18;
  return ReturnPFsPersistentPathRecursive;
}

```

## disassembly

```asm
0x18002d2b4  mov     [rsp-28h+arg_8], rbx
0x18002d2b9  mov     [rsp-28h+arg_10], r8b
0x18002d2be  push    rbp
0x18002d2bf  push    rsi
0x18002d2c0  push    rdi
0x18002d2c1  push    r14
0x18002d2c3  push    r15
0x18002d2c5  mov     rbp, rsp
0x18002d2c8  sub     rsp, 40h
0x18002d2cc  xor     r15d, r15d
0x18002d2cf  mov     rdi, rdx
0x18002d2d2  mov     r14, rcx
0x18002d2d5  mov     [rbp+phkResult], r15
0x18002d2d9  mov     r8, rcx
0x18002d2dc  mov     [rbp+arg_28], r15d
0x18002d2e0  mov     r10d, r15d
0x18002d2e3  mov     [rbp+arg_10], r15b
0x18002d2e7  cmp     [rcx], r15w
0x18002d2eb  jz      short loc_18002D338
0x18002d2ed  lea     edx, [r15+2Fh]
0x18002d2f1  movzx   eax, word ptr [r8]
0x18002d2f5  cmp     dx, ax
0x18002d2f8  jnz     short loc_18002D307
0x18002d2fa  add     r8, 2
0x18002d2fe  movzx   eax, word ptr [r8]
0x18002d302  test    ax, ax
0x18002d305  jnz     short loc_18002D2F5
0x18002d307  movzx   eax, word ptr [r8]
0x18002d30b  mov     rcx, r8
0x18002d30e  jmp     short loc_18002D31C
0x18002d310  cmp     dx, ax
0x18002d313  jz      short loc_18002D321
0x18002d315  add     rcx, 2
0x18002d319  movzx   eax, word ptr [rcx]
0x18002d31c  test    ax, ax
0x18002d31f  jnz     short loc_18002D310
0x18002d321  cmp     rcx, r8
0x18002d324  lea     eax, [r10+1]
0x18002d328  mov     r8, rcx
0x18002d32b  cmovz   eax, r10d
0x18002d32f  mov     r10d, eax
0x18002d332  cmp     [rcx], r15w
0x18002d336  jnz     short loc_18002D2F1
0x18002d338  mov     ebx, r10d
0x18002d33b  shl     rbx, 2
0x18002d33f  mov     [r9], r10d
0x18002d342  call    cs:__imp_GetProcessHeap
0x18002d348  mov     r8, rbx; dwBytes
0x18002d34b  mov     edx, 8; dwFlags
0x18002d350  mov     rcx, rax; hHeap
0x18002d353  call    cs:__imp_HeapAlloc
0x18002d359  mov     rsi, rax
0x18002d35c  test    rax, rax
0x18002d35f  jnz     short loc_18002D369
0x18002d361  lea     eax, [rsi+8]
0x18002d364  jmp     loc_18002D444
0x18002d369  mov     r8, rbx; Size
0x18002d36c  xor     edx, edx; Val
0x18002d36e  mov     rcx, rsi; void *
0x18002d371  call    memset_0
0x18002d376  lea     rcx, [rbp+phkResult]; phkResult
0x18002d37a  test    rdi, rdi
0x18002d37d  jz      short loc_18002D389
0x18002d37f  mov     rdx, rdi
0x18002d382  call    PFsPersistOpenClusterRootKey
0x18002d387  jmp     short loc_18002D38E
0x18002d389  call    PFsPersistOpenLocalRootKey
0x18002d38e  mov     ebx, eax
0x18002d390  test    eax, eax
0x18002d392  jnz     loc_18002D423
0x18002d398  mov     rcx, [rbp+phkResult]; hKey
0x18002d39c  lea     r9, [rbp+arg_10]
0x18002d3a0  test    rdi, rdi
0x18002d3a3  lea     r8, [rbp+arg_28]
0x18002d3a7  setnz   dil
0x18002d3ab  mov     dl, dil
0x18002d3ae  call    QueryPFsIdSequenceNumber
0x18002d3b3  mov     ebx, eax
0x18002d3b5  test    eax, eax
0x18002d3b7  jnz     short loc_18002D423
0x18002d3b9  mov     rcx, [rbp+phkResult]
0x18002d3bd  lea     rax, [rbp+arg_10]
0x18002d3c1  mov     [rsp+40h+var_8], rax
0x18002d3c6  mov     r9b, dil
0x18002d3c9  lea     rax, [rbp+arg_28]
0x18002d3cd  mov     r8, r14
0x18002d3d0  mov     [rsp+40h+var_10], rax
0x18002d3d5  mov     rdx, rcx
0x18002d3d8  mov     [rsp+40h+var_18], rsi
0x18002d3dd  call    CreateReturnPFsPersistentPathRecursive
0x18002d3e2  mov     ebx, eax
0x18002d3e4  test    eax, eax
0x18002d3e6  jnz     short loc_18002D413
0x18002d3e8  mov     r8d, [rbp+arg_28]
0x18002d3ec  mov     dl, dil
0x18002d3ef  mov     rcx, [rbp+phkResult]
0x18002d3f3  call    SetPFsIdSequenceNumber
0x18002d3f8  mov     ebx, eax
0x18002d3fa  test    eax, eax
0x18002d3fc  jz      short loc_18002D413
0x18002d3fe  cmp     [rbp+arg_10], r15b
0x18002d402  jnz     short loc_18002D413
0x18002d404  mov     rcx, [rbp+phkResult]
0x18002d408  mov     r8b, 1
0x18002d40b  mov     dl, dil
0x18002d40e  call    SetPFsIdSequenceNumberDuplicateCheck
0x18002d413  mov     rcx, [rbp+phkResult]
0x18002d417  mov     dl, dil
0x18002d41a  call    NfsPFsCloseKey
0x18002d41f  test    ebx, ebx
0x18002d421  jz      short loc_18002D43B
0x18002d423  call    cs:__imp_GetProcessHeap
0x18002d429  mov     r8, rsi; lpMem
0x18002d42c  xor     edx, edx; dwFlags
0x18002d42e  mov     rcx, rax; hHeap
0x18002d431  call    cs:__imp_HeapFree
0x18002d437  test    ebx, ebx
0x18002d439  jnz     short loc_18002D442
0x18002d43b  mov     rax, [rbp+arg_20]
0x18002d43f  mov     [rax], rsi
0x18002d442  mov     eax, ebx
0x18002d444  mov     rbx, [rsp+40h+arg_8]
0x18002d449  add     rsp, 40h
0x18002d44d  pop     r15
0x18002d44f  pop     r14
0x18002d451  pop     rdi
0x18002d452  pop     rsi
0x18002d453  pop     rbp
0x18002d454  retn
```
