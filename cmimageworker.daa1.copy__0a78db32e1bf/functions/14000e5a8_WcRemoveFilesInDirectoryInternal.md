# WcRemoveFilesInDirectoryInternal

- ea: `0x14000e5a8`
- end: `0x14000e94c`
- name: `WcRemoveFilesInDirectoryInternal`
- size: `932`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x14000e4c0`
- `0x14000e5a8`

## callees

- `0x1400020b0`
- `0x140002b2c`
- `0x14000e5a8`
- `0x14000e954`
- `0x14000ecc4`
- `0x14000efd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e6ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e7c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e6ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e7c7`
- `ntdll!RtlAllocateHeap` at `0x14000e615`
- `ntdll!RtlAllocateHeap` at `0x14000e615`
- `ntdll!RtlFreeHeap` at `0x14000e90d`
- `ntdll!RtlFreeHeap` at `0x14000e90d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000e89c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000e8d9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000e89c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000e8d9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000e882`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000e882`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x14000e747`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x14000e747`

## pseudocode

```c
__int64 __fastcall WcRemoveFilesInDirectoryInternal(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  WCHAR *Heap; // r14
  signed int v8; // ebx
  unsigned __int64 v9; // rsi
  _WORD *v10; // rdi
  __int64 v11; // rax
  const wchar_t *v12; // rcx
  unsigned __int64 v13; // rdx
  _WORD *v14; // r8
  _WORD *v15; // rcx
  int v16; // ebx
  HANDLE i; // rax
  __int64 v18; // r9
  void *v19; // r15
  __int64 v20; // rcx
  WCHAR *cFileName; // r8
  unsigned __int64 v22; // rdx
  _WORD *v23; // rax
  _WORD *v24; // rcx
  signed int LastError; // eax
  int v26; // eax
  __int64 v27; // r9
  int v28; // eax
  unsigned __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  _WORD *v31; // [rsp+38h] [rbp-C8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF

  v31 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v30 = 0;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x10000u);
  if ( !Heap )
    return (unsigned int)-2147024882;
  v8 = WciEnsureLongPath(Heap, v6, a1, &v31, &v30);
  if ( v8 >= 0 )
  {
    v9 = v30;
    v10 = v31;
    if ( v30 )
    {
      if ( v30 > 0x7FFFFFFF )
      {
        v8 = -2147024809;
        *v31 = 0;
        goto LABEL_52;
      }
      v11 = 2147483646;
      v12 = L"*.*";
      v13 = v30;
      v14 = v31;
      do
      {
        if ( !v11 )
          break;
        if ( !*v12 )
          break;
        *v14++ = *v12++;
        --v11;
        --v13;
      }
      while ( v13 );
      v15 = v14 - 1;
      v8 = v13 == 0 ? 0x8007007A : 0;
      if ( v13 )
        v15 = v14;
      *v15 = 0;
      if ( !v13 )
        goto LABEL_52;
      v16 = 0;
      for ( i = FindFirstFileExW(Heap, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 2u);
            ;
            i = FindFirstFileExW(Heap, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 2u) )
      {
        v19 = i;
        if ( i != (HANDLE)-1LL )
          break;
        if ( GetLastError() != 5 || v16 )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_48:
          if ( v19 != (void *)-1LL && !FindClose(v19) )
            __int2c();
          goto LABEL_52;
        }
        *v10 = 0;
        v8 = WcpTakeOwnership(Heap);
        if ( v8 < 0 )
          goto LABEL_48;
        v16 = 1;
        *v10 = 42;
      }
      while ( 1 )
      {
        if ( v9 )
        {
          if ( v9 > 0x7FFFFFFF )
          {
            *v10 = 0;
            v8 = -2147024809;
            goto LABEL_48;
          }
          v20 = 2147483646;
          cFileName = FindFileData.cFileName;
          v22 = v9;
          v23 = v10;
          do
          {
            if ( !v20 )
              break;
            v18 = *cFileName;
            if ( !(_WORD)v18 )
              break;
            *v23 = v18;
            ++cFileName;
            ++v23;
            --v20;
            --v22;
          }
          while ( v22 );
          v24 = v23 - 1;
          if ( v22 )
            v24 = v23;
          v8 = v22 == 0 ? 0x8007007A : 0;
          *v24 = 0;
        }
        else
        {
          v8 = -2147024809;
        }
        if ( v8 < 0 )
          goto LABEL_48;
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
          goto LABEL_43;
        if ( *(_DWORD *)FindFileData.cFileName != 46
          && (*(_DWORD *)FindFileData.cFileName != 3014702 || FindFileData.cFileName[2]) )
        {
          break;
        }
LABEL_45:
        if ( !FindNextFileW(v19, &FindFileData) )
        {
          FindClose(v19);
          *(v10 - 1) = 0;
          v8 = WcpRemoveFile((__int64)Heap, a2, a3, v27, 0);
          goto LABEL_52;
        }
      }
      if ( (FindFileData.dwFileAttributes & 0x400) == 0
        || FindFileData.dwReserved0 == -2147483624
        || FindFileData.dwReserved0 == -1879044072
        || FindFileData.dwReserved0 == -1610612697
        || FindFileData.dwReserved0 == -1610608601 )
      {
        v26 = WcRemoveFilesInDirectoryInternal(Heap, a2, a3, 1);
      }
      else
      {
LABEL_43:
        v26 = WcpRemoveFile((__int64)Heap, a2, a3, v18, 0);
      }
      v8 = v26;
      if ( v26 < 0 )
        goto LABEL_48;
      goto LABEL_45;
    }
    v8 = -2147024809;
  }
LABEL_52:
  LOBYTE(v28) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( !v28 )
    __int2c();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000e5a8  mov     [rsp-8+arg_18], rbx
0x14000e5ad  push    rbp
0x14000e5ae  push    rsi
0x14000e5af  push    rdi
0x14000e5b0  push    r12
0x14000e5b2  push    r13
0x14000e5b4  push    r14
0x14000e5b6  push    r15
0x14000e5b8  lea     rbp, [rsp-1A0h]
0x14000e5c0  sub     rsp, 2A0h
0x14000e5c7  mov     rax, cs:__security_cookie
0x14000e5ce  xor     rax, rsp
0x14000e5d1  mov     [rbp+1D0h+var_40], rax
0x14000e5d8  mov     r13, r8
0x14000e5db  mov     r12, rdx
0x14000e5de  mov     rbx, rcx
0x14000e5e1  xor     r15d, r15d
0x14000e5e4  xor     edx, edx; Val
0x14000e5e6  mov     [rsp+2D0h+var_298], r15
0x14000e5eb  mov     r8d, 250h; Size
0x14000e5f1  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x14000e5f6  call    memset_0
0x14000e5fb  mov     rcx, gs:60h
0x14000e604  xor     edx, edx; Flags
0x14000e606  mov     r8d, 10000h; Size
0x14000e60c  mov     [rsp+2D0h+var_2A0], r15
0x14000e611  mov     rcx, [rcx+30h]; HeapHandle
0x14000e615  call    cs:__imp_RtlAllocateHeap
0x14000e61c  nop     dword ptr [rax+rax+00h]
0x14000e621  mov     r14, rax
0x14000e624  test    rax, rax
0x14000e627  jnz     short loc_14000E633
0x14000e629  mov     ebx, 8007000Eh
0x14000e62e  jmp     loc_14000E91F
0x14000e633  lea     rax, [rsp+2D0h+var_2A0]
0x14000e638  mov     r8, rbx
0x14000e63b  lea     r9, [rsp+2D0h+var_298]
0x14000e640  mov     [rsp+2D0h+lpSearchFilter], rax
0x14000e645  mov     rcx, r14
0x14000e648  call    WciEnsureLongPath
0x14000e64d  mov     ebx, eax
0x14000e64f  test    eax, eax
0x14000e651  js      loc_14000E8FB
0x14000e657  mov     rsi, [rsp+2D0h+var_2A0]
0x14000e65c  mov     rdi, [rsp+2D0h+var_298]
0x14000e661  test    rsi, rsi
0x14000e664  jz      loc_14000E8ED
0x14000e66a  cmp     rsi, 7FFFFFFFh
0x14000e671  jbe     short loc_14000E67D
0x14000e673  mov     ebx, 80070057h
0x14000e678  jmp     loc_14000E8F7
0x14000e67d  mov     eax, 7FFFFFFEh
0x14000e682  lea     rcx, asc_1400372C8; "*.*"
0x14000e689  mov     rdx, rsi
0x14000e68c  mov     r8, rdi
0x14000e68f  test    rax, rax
0x14000e692  jz      short loc_14000E6B3
0x14000e694  movzx   r9d, word ptr [rcx]
0x14000e698  test    r9w, r9w
0x14000e69c  jz      short loc_14000E6B3
0x14000e69e  mov     [r8], r9w
0x14000e6a2  add     rcx, 2
0x14000e6a6  add     r8, 2
0x14000e6aa  dec     rax
0x14000e6ad  sub     rdx, 1
0x14000e6b1  jnz     short loc_14000E68F
0x14000e6b3  mov     rax, rdx
0x14000e6b6  lea     rcx, [r8-2]
0x14000e6ba  neg     rax
0x14000e6bd  sbb     ebx, ebx
0x14000e6bf  not     ebx
0x14000e6c1  and     ebx, 8007007Ah
0x14000e6c7  test    rdx, rdx
0x14000e6ca  cmovnz  rcx, r8
0x14000e6ce  mov     [rcx], r15w
0x14000e6d2  jz      loc_14000E8FB
0x14000e6d8  mov     [rsp+2D0h+dwAdditionalFlags], 2
0x14000e6e0  mov     ebx, r15d
0x14000e6e3  mov     [rsp+2D0h+lpSearchFilter], r15
0x14000e6e8  mov     edx, 1
0x14000e6ed  jmp     short loc_14000E73C
0x14000e6ef  call    cs:__imp_GetLastError
0x14000e6f6  nop     dword ptr [rax+rax+00h]
0x14000e6fb  cmp     eax, 5
0x14000e6fe  jnz     loc_14000E7C7
0x14000e704  xor     eax, eax
0x14000e706  test    ebx, ebx
0x14000e708  jnz     loc_14000E7C7
0x14000e70e  mov     rcx, r14; pObjectName
0x14000e711  mov     [rdi], ax
0x14000e714  call    WcpTakeOwnership
0x14000e719  xor     ecx, ecx
0x14000e71b  mov     ebx, eax
0x14000e71d  test    eax, eax
0x14000e71f  js      loc_14000E8D0
0x14000e725  lea     ebx, [rcx+1]
0x14000e728  mov     [rsp+2D0h+dwAdditionalFlags], 2; dwAdditionalFlags
0x14000e730  mov     edx, ebx; fInfoLevelId
0x14000e732  mov     word ptr [rdi], 2Ah ; '*'
0x14000e737  mov     [rsp+2D0h+lpSearchFilter], rcx; lpSearchFilter
0x14000e73c  xor     r9d, r9d; fSearchOp
0x14000e73f  lea     r8, [rsp+2D0h+FindFileData]; lpFindFileData
0x14000e744  mov     rcx, r14; lpFileName
0x14000e747  call    cs:__imp_FindFirstFileExW
0x14000e74e  nop     dword ptr [rax+rax+00h]
0x14000e753  mov     r15, rax
0x14000e756  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000e75a  jz      short loc_14000E6EF
0x14000e75c  xor     r10d, r10d
0x14000e75f  test    rsi, rsi
0x14000e762  jz      loc_14000E7EB
0x14000e768  cmp     rsi, 7FFFFFFFh
0x14000e76f  ja      loc_14000E8C7
0x14000e775  mov     ecx, 7FFFFFFEh
0x14000e77a  lea     r8, [rsp+2D0h+var_264]
0x14000e77f  mov     rdx, rsi
0x14000e782  mov     rax, rdi
0x14000e785  test    rcx, rcx
0x14000e788  jz      short loc_14000E7A9
0x14000e78a  movzx   r9d, word ptr [r8]
0x14000e78e  test    r9w, r9w
0x14000e792  jz      short loc_14000E7A9
0x14000e794  mov     [rax], r9w
0x14000e798  add     r8, 2
0x14000e79c  add     rax, 2
0x14000e7a0  dec     rcx
0x14000e7a3  sub     rdx, 1
0x14000e7a7  jnz     short loc_14000E785
0x14000e7a9  test    rdx, rdx
0x14000e7ac  lea     rcx, [rax-2]
0x14000e7b0  cmovnz  rcx, rax
0x14000e7b4  neg     rdx
0x14000e7b7  sbb     ebx, ebx
0x14000e7b9  not     ebx
0x14000e7bb  and     ebx, 8007007Ah
0x14000e7c1  mov     [rcx], r10w
0x14000e7c5  jmp     short loc_14000E7F9
0x14000e7c7  call    cs:__imp_GetLastError
0x14000e7ce  nop     dword ptr [rax+rax+00h]
0x14000e7d3  mov     ebx, eax
0x14000e7d5  test    eax, eax
0x14000e7d7  jle     loc_14000E8D0
0x14000e7dd  movzx   ebx, ax
0x14000e7e0  or      ebx, 80070000h
0x14000e7e6  jmp     loc_14000E8D0
0x14000e7eb  mov     ebx, 80070057h
0x14000e7f0  test    rsi, rsi
0x14000e7f3  jnz     loc_14000E8C7
0x14000e7f9  test    ebx, ebx
0x14000e7fb  js      loc_14000E8D0
0x14000e801  test    byte ptr [rsp+2D0h+FindFileData], 10h
0x14000e806  jz      short loc_14000E861
0x14000e808  cmp     [rsp+2D0h+var_264], 2Eh ; '.'
0x14000e80d  jz      short loc_14000E87A
0x14000e80f  cmp     [rsp+2D0h+var_264], 2E002Eh
0x14000e817  jnz     short loc_14000E821
0x14000e819  cmp     [rsp+2D0h+var_260], r10w
0x14000e81f  jz      short loc_14000E87A
0x14000e821  test    [rsp+2D0h+FindFileData], 400h
0x14000e829  jz      short loc_14000E84B
0x14000e82b  mov     eax, [rsp+2D0h+var_26C]
0x14000e82f  cmp     eax, 80000018h
0x14000e834  jz      short loc_14000E84B
0x14000e836  cmp     eax, 90001018h
0x14000e83b  jz      short loc_14000E84B
0x14000e83d  cmp     eax, 0A0000027h
0x14000e842  jz      short loc_14000E84B
0x14000e844  cmp     eax, 0A0001027h
0x14000e849  jnz     short loc_14000E861
0x14000e84b  mov     r9d, 1
0x14000e851  mov     r8, r13
0x14000e854  mov     rdx, r12
0x14000e857  mov     rcx, r14
0x14000e85a  call    WcRemoveFilesInDirectoryInternal
0x14000e85f  jmp     short loc_14000E874
0x14000e861  mov     r8, r13
0x14000e864  mov     byte ptr [rsp+2D0h+lpSearchFilter], r10b
0x14000e869  mov     rdx, r12
0x14000e86c  mov     rcx, r14
0x14000e86f  call    WcpRemoveFile
0x14000e874  mov     ebx, eax
0x14000e876  test    eax, eax
0x14000e878  js      short loc_14000E8D0
0x14000e87a  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x14000e87f  mov     rcx, r15; hFindFile
0x14000e882  call    cs:__imp_FindNextFileW
0x14000e889  nop     dword ptr [rax+rax+00h]
0x14000e88e  xor     r10d, r10d
0x14000e891  test    eax, eax
0x14000e893  jnz     loc_14000E75F
0x14000e899  mov     rcx, r15; hFindFile
0x14000e89c  call    cs:__imp_FindClose
0x14000e8a3  nop     dword ptr [rax+rax+00h]
0x14000e8a8  xor     r15d, r15d
0x14000e8ab  mov     r8, r13
0x14000e8ae  mov     rdx, r12
0x14000e8b1  mov     [rdi-2], r15w
0x14000e8b6  mov     rcx, r14
0x14000e8b9  mov     byte ptr [rsp+2D0h+lpSearchFilter], r15b
0x14000e8be  call    WcpRemoveFile
0x14000e8c3  mov     ebx, eax
0x14000e8c5  jmp     short loc_14000E8FB
0x14000e8c7  mov     [rdi], r10w
0x14000e8cb  mov     ebx, 80070057h
0x14000e8d0  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x14000e8d4  jz      short loc_14000E8FB
0x14000e8d6  mov     rcx, r15; hFindFile
0x14000e8d9  call    cs:__imp_FindClose
0x14000e8e0  nop     dword ptr [rax+rax+00h]
0x14000e8e5  test    eax, eax
0x14000e8e7  jnz     short loc_14000E8FB
0x14000e8e9  int     2Ch; Windows NT - assertion failure
0x14000e8eb  jmp     short loc_14000E8FB
0x14000e8ed  mov     ebx, 80070057h
0x14000e8f2  test    rsi, rsi
0x14000e8f5  jz      short loc_14000E8FB
0x14000e8f7  mov     [rdi], r15w
0x14000e8fb  mov     rcx, gs:60h
0x14000e904  mov     r8, r14; P
0x14000e907  xor     edx, edx; Flags
0x14000e909  mov     rcx, [rcx+30h]; HeapHandle
0x14000e90d  call    cs:__imp_RtlFreeHeap
0x14000e914  nop     dword ptr [rax+rax+00h]
0x14000e919  test    eax, eax
0x14000e91b  jnz     short loc_14000E91F
0x14000e91d  int     2Ch; Windows NT - assertion failure
0x14000e91f  mov     eax, ebx
0x14000e921  mov     rcx, [rbp+1D0h+var_40]
0x14000e928  xor     rcx, rsp; StackCookie
0x14000e92b  call    __security_check_cookie
0x14000e930  mov     rbx, [rsp+2D0h+arg_18]
0x14000e938  add     rsp, 2A0h
0x14000e93f  pop     r15
0x14000e941  pop     r14
0x14000e943  pop     r13
0x14000e945  pop     r12
0x14000e947  pop     rdi
0x14000e948  pop     rsi
0x14000e949  pop     rbp
0x14000e94a  retn
```
