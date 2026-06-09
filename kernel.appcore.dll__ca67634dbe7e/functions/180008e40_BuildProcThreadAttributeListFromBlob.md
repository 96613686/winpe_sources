# BuildProcThreadAttributeListFromBlob

- ea: `0x180008e40`
- end: `0x18000904a`
- name: `BuildProcThreadAttributeListFromBlob`
- size: `522`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180008d78`
- `0x180008e40`
- `0x180009d92`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180008feb`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x180008feb`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180008ef6`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180008f4f`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180008ef6`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180008f4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ffc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000901b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000901b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008f13`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008f13`

## pseudocode

```c
signed int __fastcall BuildProcThreadAttributeListFromBlob(
        unsigned int a1,
        unsigned __int64 a2,
        int a3,
        struct _PROC_THREAD_ATTRIBUTE_LIST **a4)
{
  __int64 v4; // rbp
  unsigned int v8; // edi
  unsigned int v9; // esi
  signed int result; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v11; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v12; // rsi
  unsigned __int64 v13; // r15
  char *v14; // r13
  unsigned int i; // ebp
  __int64 v16; // rdi
  __int64 v17; // rcx
  SIZE_T cbSize; // r14
  void *v19; // r9
  const void *v20; // rdx
  signed int LastError; // eax
  unsigned int v22; // ebx
  unsigned int v23; // [rsp+80h] [rbp+8h] BYREF
  ULONG_PTR Size; // [rsp+88h] [rbp+10h] BYREF

  v4 = a1;
  *a4 = 0;
  if ( a1 < 0x18 )
    return -2147024809;
  v8 = *(_DWORD *)a2;
  v9 = 0;
  if ( *(_DWORD *)a2 )
  {
    v9 = 16 * v8 - 16;
    if ( a1 < (unsigned __int64)v9 + 24 )
      return -2147024809;
  }
  v23 = 0;
  result = ValidateAttributeListAndDetermineBlobSize(v8, (struct _PROC_THREAD_ATTRIBUTE_BLOB_ENTRY *)(a2 + 8), &v23);
  if ( result )
    return result;
  if ( v23 != (_DWORD)v4 || *(_DWORD *)(a2 + 4) > v23 || v23 - *(_DWORD *)(a2 + 4) != v9 + 24LL )
    return -2147024809;
  Size = 0;
  if ( !InitializeProcThreadAttributeList(0, v8 + a3, 0, &Size) )
    GetLastError();
  v11 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)LocalAlloc(0, Size + *(unsigned int *)(a2 + 4));
  v12 = v11;
  if ( v11 )
  {
    InitializeProcThreadAttributeList(v11, a3 + *(_DWORD *)a2, 0, &Size);
    v13 = a2 + v4;
    v14 = (char *)v12 + Size;
    for ( i = 0; i < *(_DWORD *)a2; ++i )
    {
      v16 = 16LL * i;
      v17 = *(unsigned int *)(v16 + a2 + 12);
      if ( (unsigned int)v17 > 8 || *(_DWORD *)(v16 + a2 + 8) == 131088 )
      {
        v20 = (const void *)(a2 + *(unsigned int *)(v16 + a2 + 16));
        if ( (unsigned __int64)v20 < a2
          || (unsigned __int64)v20 >= v13
          || (cbSize = *(unsigned int *)(v16 + a2 + 12), (unsigned __int64)v20 + v17 <= a2)
          || (unsigned __int64)v20 + v17 > v13 )
        {
          v22 = -2147024809;
LABEL_28:
          LocalFree(v12);
          return v22;
        }
        memcpy_0(v14, v20, *(unsigned int *)(v16 + a2 + 12));
        v19 = v14;
        v14 += *(unsigned int *)(v16 + a2 + 12);
      }
      else
      {
        cbSize = (unsigned int)v17;
        v19 = (void *)(v16 + a2 + 16);
      }
      if ( !UpdateProcThreadAttribute(v12, 0, *(unsigned int *)(v16 + a2 + 8), v19, cbSize, 0, 0) )
      {
        LastError = GetLastError();
        v22 = LastError;
        if ( LastError > 0 )
          v22 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_28;
      }
    }
    *a4 = v12;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180008e40  mov     [rsp+arg_10], rbx
0x180008e45  push    rbp
0x180008e46  push    rsi
0x180008e47  push    rdi
0x180008e48  push    r12
0x180008e4a  push    r13
0x180008e4c  push    r14
0x180008e4e  push    r15
0x180008e50  sub     rsp, 40h
0x180008e54  xor     r15d, r15d
0x180008e57  mov     ebp, ecx
0x180008e59  mov     [r9], r15
0x180008e5c  mov     r12, r9
0x180008e5f  mov     r14d, r8d
0x180008e62  mov     rbx, rdx
0x180008e65  cmp     ecx, 18h
0x180008e68  jb      loc_18000902D
0x180008e6e  mov     edi, [rdx]
0x180008e70  mov     esi, r15d
0x180008e73  test    edi, edi
0x180008e75  jz      short loc_180008E8E
0x180008e77  mov     esi, edi
0x180008e79  shl     esi, 4
0x180008e7c  add     esi, 0FFFFFFF0h
0x180008e7f  mov     ecx, esi
0x180008e81  add     rcx, 18h
0x180008e85  cmp     rbp, rcx
0x180008e88  jb      loc_18000902D
0x180008e8e  add     rdx, 8; struct _PROC_THREAD_ATTRIBUTE_BLOB_ENTRY *
0x180008e92  mov     [rsp+78h+arg_0], r15d
0x180008e9a  lea     r8, [rsp+78h+arg_0]; unsigned int *
0x180008ea2  mov     ecx, edi; unsigned int
0x180008ea4  call    ?ValidateAttributeListAndDetermineBlobSize@@YAJKPEAU_PROC_THREAD_ATTRIBUTE_BLOB_ENTRY@@PEAK@Z; ValidateAttributeListAndDetermineBlobSize(ulong,_PROC_THREAD_ATTRIBUTE_BLOB_ENTRY *,ulong *)
0x180008ea9  test    eax, eax
0x180008eab  jnz     loc_180009032
0x180008eb1  mov     eax, [rsp+78h+arg_0]
0x180008eb8  cmp     eax, ebp
0x180008eba  jnz     loc_18000902D
0x180008ec0  cmp     [rbx+4], eax
0x180008ec3  ja      loc_18000902D
0x180008ec9  sub     eax, [rbx+4]
0x180008ecc  mov     ecx, eax
0x180008ece  mov     eax, esi
0x180008ed0  add     rax, 18h
0x180008ed4  cmp     rcx, rax
0x180008ed7  jnz     loc_18000902D
0x180008edd  lea     edx, [rdi+r14]; dwAttributeCount
0x180008ee1  mov     [rsp+78h+Size], r15
0x180008ee9  lea     r9, [rsp+78h+Size]; lpSize
0x180008ef1  xor     r8d, r8d; dwFlags
0x180008ef4  xor     ecx, ecx; lpAttributeList
0x180008ef6  call    cs:__imp_InitializeProcThreadAttributeList
0x180008efc  test    eax, eax
0x180008efe  jnz     short loc_180008F06
0x180008f00  call    cs:__imp_GetLastError
0x180008f06  mov     edx, [rbx+4]
0x180008f09  xor     ecx, ecx; uFlags
0x180008f0b  add     rdx, [rsp+78h+Size]; uBytes
0x180008f13  call    cs:__imp_LocalAlloc
0x180008f19  mov     rsi, rax
0x180008f1c  test    rax, rax
0x180008f1f  jnz     short loc_180008F3C
0x180008f21  call    cs:__imp_GetLastError
0x180008f27  test    eax, eax
0x180008f29  jle     loc_180009032
0x180008f2f  movzx   eax, ax
0x180008f32  or      eax, 80070000h
0x180008f37  jmp     loc_180009032
0x180008f3c  mov     edx, [rbx]
0x180008f3e  lea     r9, [rsp+78h+Size]; lpSize
0x180008f46  add     edx, r14d; dwAttributeCount
0x180008f49  xor     r8d, r8d; dwFlags
0x180008f4c  mov     rcx, rsi; lpAttributeList
0x180008f4f  call    cs:__imp_InitializeProcThreadAttributeList
0x180008f55  mov     r13, [rsp+78h+Size]
0x180008f5d  lea     r15, [rbx+rbp]
0x180008f61  add     r13, rsi
0x180008f64  xor     ebp, ebp
0x180008f66  cmp     ebp, [rbx]
0x180008f68  jnb     loc_180009025
0x180008f6e  mov     edi, ebp
0x180008f70  shl     rdi, 4
0x180008f74  mov     ecx, [rdi+rbx+0Ch]
0x180008f78  cmp     ecx, 8
0x180008f7b  ja      short loc_180008F93
0x180008f7d  cmp     dword ptr [rdi+rbx+8], 20010h
0x180008f85  jz      short loc_180008F93
0x180008f87  lea     r9, [rbx+10h]
0x180008f8b  mov     r14d, ecx
0x180008f8e  add     r9, rdi
0x180008f91  jmp     short loc_180008FCA
0x180008f93  mov     edx, [rdi+rbx+10h]
0x180008f97  add     rdx, rbx; Src
0x180008f9a  cmp     rdx, rbx
0x180008f9d  jb      short loc_180009013
0x180008f9f  cmp     rdx, r15
0x180008fa2  jnb     short loc_180009013
0x180008fa4  lea     rax, [rdx+rcx]
0x180008fa8  mov     r14, rcx
0x180008fab  cmp     rax, rbx
0x180008fae  jbe     short loc_180009013
0x180008fb0  cmp     rax, r15
0x180008fb3  ja      short loc_180009013
0x180008fb5  mov     r8, rcx; Size
0x180008fb8  mov     rcx, r13; void *
0x180008fbb  call    memcpy_0
0x180008fc0  mov     eax, [rdi+rbx+0Ch]
0x180008fc4  mov     r9, r13; lpValue
0x180008fc7  add     r13, rax
0x180008fca  mov     r8d, [rdi+rbx+8]; Attribute
0x180008fcf  xor     edx, edx; dwFlags
0x180008fd1  mov     [rsp+78h+lpReturnSize], 0; lpReturnSize
0x180008fda  mov     rcx, rsi; lpAttributeList
0x180008fdd  mov     [rsp+78h+lpPreviousValue], 0; lpPreviousValue
0x180008fe6  mov     [rsp+78h+cbSize], r14; cbSize
0x180008feb  call    cs:__imp_UpdateProcThreadAttribute
0x180008ff1  test    eax, eax
0x180008ff3  jz      short loc_180008FFC
0x180008ff5  inc     ebp
0x180008ff7  jmp     loc_180008F66
0x180008ffc  call    cs:__imp_GetLastError
0x180009002  mov     ebx, eax
0x180009004  test    eax, eax
0x180009006  jle     short loc_180009018
0x180009008  movzx   ebx, ax
0x18000900b  or      ebx, 80070000h
0x180009011  jmp     short loc_180009018
0x180009013  mov     ebx, 80070057h
0x180009018  mov     rcx, rsi; hMem
0x18000901b  call    cs:__imp_LocalFree
0x180009021  mov     eax, ebx
0x180009023  jmp     short loc_180009032
0x180009025  mov     [r12], rsi
0x180009029  xor     eax, eax
0x18000902b  jmp     short loc_180009032
0x18000902d  mov     eax, 80070057h
0x180009032  mov     rbx, [rsp+78h+arg_10]
0x18000903a  add     rsp, 40h
0x18000903e  pop     r15
0x180009040  pop     r14
0x180009042  pop     r13
0x180009044  pop     r12
0x180009046  pop     rdi
0x180009047  pop     rsi
0x180009048  pop     rbp
0x180009049  retn
```
