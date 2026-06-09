# RasfileLoadEx

- ea: `0x18000e4a0`
- end: `0x18000e81a`
- name: `RasfileLoadEx`
- size: `890`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180020d14`

## callees

- `0x18000e4a0`
- `0x18000e820`
- `0x18000ead0`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `ntdll!DbgPrint` at `0x18000e7f6`
- `ntdll!DbgPrint` at `0x18000e80f`
- `ntdll!DbgPrint` at `0x18000e7f6`
- `ntdll!DbgPrint` at `0x18000e80f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e6f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e5fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e6f6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000e4fb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000e4fb`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000e76f`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000e76f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e5d6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e5d6`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18000e5e9`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18000e5e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e538`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e692`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e538`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e692`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e6a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e6a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e549`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e549`

## pseudocode

```c
__int64 __fastcall RasfileLoadEx(LPCWSTR lpFileName, int a2, __int64 a3, __int64 a4, FILETIME *a5)
{
  __int64 v7; // rdi
  unsigned int v8; // r15d
  HANDLE ProcessHeap; // rax
  _DWORD *v10; // rax
  __int64 v11; // rbp
  __int64 *v12; // r14
  HANDLE FileW; // rax
  _WORD *v14; // rcx
  __int64 v15; // rbx
  _DWORD *v16; // rax
  HANDLE v17; // rax
  void *v19; // rcx
  __int64 v20; // rcx
  _WORD *v21; // rdx
  void *v22; // rcx
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+40h] [rbp-68h] BYREF

  if ( !dword_1800FE53C )
  {
    memset_0(gpRasfiles, 0, sizeof(gpRasfiles));
    dword_1800FE53C = 1;
  }
  v7 = 260;
  if ( lstrlenW(lpFileName) >= 260 )
    return 0xFFFFFFFFLL;
  v8 = 0;
  while ( gpRasfiles[v8] )
  {
    if ( !gpRasfiles[v8 + 1] )
    {
      ++v8;
      goto LABEL_8;
    }
    if ( !gpRasfiles[v8 + 2] )
    {
      v8 += 2;
      goto LABEL_8;
    }
    if ( !gpRasfiles[v8 + 3] )
    {
      v8 += 3;
      goto LABEL_8;
    }
    if ( !gpRasfiles[v8 + 4] )
    {
      v8 += 4;
LABEL_8:
      if ( (int)v8 >= 500 )
        return 0xFFFFFFFFLL;
      break;
    }
    v8 += 5;
    if ( (int)v8 >= 500 )
      return 0xFFFFFFFFLL;
  }
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 0, 0x8A4u);
  if ( !v10 )
    return 0xFFFFFFFFLL;
  v10[4] = -1412567126;
  v11 = (__int64)(v10 + 8);
  *((_QWORD *)v10 + 3) = v10 + 552;
  v10[552] = -1412567109;
  v10[5] = 1;
  if ( v10 == (_DWORD *)-32LL )
    return 0xFFFFFFFFLL;
  gpRasfiles[v8] = v11;
  v12 = &gpRasfiles[v8];
  *((_QWORD *)v10 + 269) = v10 + 536;
  *((_QWORD *)v10 + 268) = v10 + 536;
  v10[542] = 0;
  v10[16] = a2;
  FileW = CreateFileW(lpFileName, 0x80000000, (a2 & 4 | 2u) >> 1, 0, 3u, 1u, 0);
  *(_QWORD *)(v11 + 24) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( (a2 & 2) == 0 )
    {
LABEL_15:
      DebugFree(*v12);
      goto LABEL_23;
    }
  }
  else if ( GetFileType(FileW) != 1 )
  {
    CloseHandle(*(HANDLE *)(v11 + 24));
    *(_QWORD *)(v11 + 24) = -1;
    DebugFree(*v12);
LABEL_23:
    *v12 = 0;
    return 0xFFFFFFFFLL;
  }
  if ( a5 )
  {
    v22 = *(void **)(v11 + 24);
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( GetFileInformationByHandle(v22, &FileInformation) )
      *a5 = FileInformation.ftLastWriteTime;
  }
  v20 = 2147483646;
  v21 = (_WORD *)(v11 + 52);
  do
  {
    if ( !v20 )
      break;
    if ( !*lpFileName )
      break;
    *v21++ = *lpFileName++;
    --v20;
    --v7;
  }
  while ( v7 );
  v14 = v21 - 1;
  if ( v7 )
    v14 = v21;
  *v14 = 0;
  if ( !v7 )
    goto LABEL_15;
  *(_BYTE *)(v11 + 572) = 0;
  *(_QWORD *)(v11 + 16) = IsGroup;
  if ( !(unsigned int)rasLoadFile(v11) )
  {
    _mm_lfence();
    v15 = *v12 - 32;
    if ( *(_DWORD *)(v15 + 16) == -1412567126 )
    {
      v16 = *(_DWORD **)(v15 + 24);
      if ( *v16 == -1412567109 )
      {
        *(_DWORD *)(v15 + 16) = -1426137926;
        *v16 = -1140925254;
        v17 = GetProcessHeap();
        HeapFree(v17, 0, (LPVOID)v15);
      }
      else
      {
        DbgPrint(
          "\n=======================\nFreeing Invalid memory:Tail corrupted:%0x:Id:%0x\n",
          *(_DWORD *)v12 - 32,
          *(_DWORD *)(v15 + 20));
      }
    }
    else
    {
      DbgPrint(
        "\n=======================\nFreeing Invalid memory:%0x:Id:%0x\n",
        *(_DWORD *)v12 - 32,
        *(_DWORD *)(v15 + 20));
    }
    goto LABEL_23;
  }
  *(_DWORD *)(v11 + 36) = 0;
  if ( (a2 & 0x20) == 0 )
  {
    v19 = *(void **)(v11 + 24);
    if ( v19 != (void *)-1LL )
    {
      if ( !CloseHandle(v19) )
        return 0xFFFFFFFFLL;
      *(_QWORD *)(v11 + 24) = -1;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000e4a0  push    rbx
0x18000e4a2  push    rsi
0x18000e4a3  push    rdi
0x18000e4a4  push    r12
0x18000e4a6  push    r14
0x18000e4a8  sub     rsp, 80h
0x18000e4af  mov     rax, cs:__security_cookie
0x18000e4b6  xor     rax, rsp
0x18000e4b9  mov     [rsp+0A8h+var_30], rax
0x18000e4be  cmp     cs:dword_1800FE53C, 0
0x18000e4c5  lea     r14, gpRasfiles
0x18000e4cc  mov     rsi, [rsp+0A8h+arg_20]
0x18000e4d4  mov     r12d, edx
0x18000e4d7  mov     rbx, rcx
0x18000e4da  jz      loc_18000E7C9
0x18000e4e0  mov     [rsp+0A8h+arg_8], rbp
0x18000e4e8  mov     rcx, rbx; lpString
0x18000e4eb  mov     [rsp+0A8h+arg_10], r13
0x18000e4f3  mov     [rsp+0A8h+arg_18], r15
0x18000e4fb  call    cs:__imp_lstrlenW
0x18000e501  mov     edi, 104h
0x18000e506  cmp     eax, edi
0x18000e508  jge     loc_18000E6A9
0x18000e50e  xor     r13d, r13d
0x18000e511  mov     r15d, r13d
0x18000e514  mov     eax, r15d
0x18000e517  cmp     [r14+rax*8], r13
0x18000e51b  jz      short loc_18000E538
0x18000e51d  cmp     [r14+rax*8+8], r13
0x18000e522  jnz     loc_18000E783
0x18000e528  inc     r15d
0x18000e52b  cmp     r15d, 1F4h
0x18000e532  jge     loc_18000E6A9
0x18000e538  call    cs:__imp_GetProcessHeap
0x18000e53e  xor     edx, edx; dwFlags
0x18000e540  mov     r8d, 8A4h; dwBytes
0x18000e546  mov     rcx, rax; hHeap
0x18000e549  call    cs:__imp_HeapAlloc
0x18000e54f  test    rax, rax
0x18000e552  jz      loc_18000E6A9
0x18000e558  lea     rcx, [rax+8A0h]
0x18000e55f  mov     dword ptr [rax+10h], 0ABCDEFAAh
0x18000e566  lea     rbp, [rax+20h]
0x18000e56a  mov     [rax+18h], rcx
0x18000e56e  mov     dword ptr [rcx], 0ABCDEFBBh
0x18000e574  mov     dword ptr [rax+14h], 1
0x18000e57b  test    rbp, rbp
0x18000e57e  jz      loc_18000E6A9
0x18000e584  movsxd  rax, r15d
0x18000e587  mov     r8d, r12d
0x18000e58a  mov     [r14+rax*8], rbp
0x18000e58e  lea     r14, [r14+rax*8]
0x18000e592  and     r8d, 4
0x18000e596  mov     [rsp+0A8h+hTemplateFile], r13; hTemplateFile
0x18000e59b  lea     rax, [rbp+840h]
0x18000e5a2  mov     [rsp+0A8h+dwFlagsAndAttributes], 1; dwFlagsAndAttributes
0x18000e5aa  mov     [rax+8], rax
0x18000e5ae  or      r8d, 2
0x18000e5b2  mov     [rax], rax
0x18000e5b5  xor     r9d, r9d; lpSecurityAttributes
0x18000e5b8  shr     r8d, 1; dwShareMode
0x18000e5bb  mov     edx, 80000000h; dwDesiredAccess
0x18000e5c0  mov     rcx, rbx; lpFileName
0x18000e5c3  mov     [rbp+858h], r13d
0x18000e5ca  mov     [rbp+20h], r12d
0x18000e5ce  mov     [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000e5d6  call    cs:__imp_CreateFileW
0x18000e5dc  mov     [rbp+18h], rax
0x18000e5e0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e5e4  jz      short loc_18000E617
0x18000e5e6  mov     rcx, rax; hFile
0x18000e5e9  call    cs:__imp_GetFileType
0x18000e5ef  cmp     eax, 1
0x18000e5f2  jz      loc_18000E70D
0x18000e5f8  mov     rcx, [rbp+18h]; hObject
0x18000e5fc  call    cs:__imp_CloseHandle
0x18000e602  mov     qword ptr [rbp+18h], 0FFFFFFFFFFFFFFFFh
0x18000e60a  mov     rcx, [r14]
0x18000e60d  call    DebugFree
0x18000e612  jmp     loc_18000E6A6
0x18000e617  test    r12b, 2
0x18000e61b  jnz     loc_18000E70D
0x18000e621  mov     rcx, [r14]
0x18000e624  call    DebugFree
0x18000e629  jmp     short loc_18000E6A6
0x18000e62b  test    rdi, rdi
0x18000e62e  lea     rcx, [rdx-2]
0x18000e632  cmovnz  rcx, rdx
0x18000e636  mov     [rcx], r13w
0x18000e63a  jz      short loc_18000E621
0x18000e63c  lea     rax, IsGroup
0x18000e643  mov     [rbp+23Ch], r13b
0x18000e64a  mov     rcx, rbp
0x18000e64d  mov     [rbp+10h], rax
0x18000e651  call    rasLoadFile
0x18000e656  test    eax, eax
0x18000e658  jnz     loc_18000E6E2
0x18000e65e  lfence
0x18000e661  mov     rbx, [r14]
0x18000e664  add     rbx, 0FFFFFFFFFFFFFFE0h
0x18000e668  cmp     dword ptr [rbx+10h], 0ABCDEFAAh
0x18000e66f  jnz     loc_18000E7E8
0x18000e675  mov     rax, [rbx+18h]
0x18000e679  cmp     dword ptr [rax], 0ABCDEFBBh
0x18000e67f  jnz     loc_18000E801
0x18000e685  mov     dword ptr [rbx+10h], 0AAFEDCBAh
0x18000e68c  mov     dword ptr [rax], 0BBFEDCBAh
0x18000e692  call    cs:__imp_GetProcessHeap
0x18000e698  mov     r8, rbx; lpMem
0x18000e69b  xor     edx, edx; dwFlags
0x18000e69d  mov     rcx, rax; hHeap
0x18000e6a0  call    cs:__imp_HeapFree
0x18000e6a6  mov     [r14], r13
0x18000e6a9  mov     eax, 0FFFFFFFFh
0x18000e6ae  mov     r15, [rsp+0A8h+arg_18]
0x18000e6b6  mov     r13, [rsp+0A8h+arg_10]
0x18000e6be  mov     rbp, [rsp+0A8h+arg_8]
0x18000e6c6  mov     rcx, [rsp+0A8h+var_30]
0x18000e6cb  xor     rcx, rsp; StackCookie
0x18000e6ce  call    __security_check_cookie
0x18000e6d3  add     rsp, 80h
0x18000e6da  pop     r14
0x18000e6dc  pop     r12
0x18000e6de  pop     rdi
0x18000e6df  pop     rsi
0x18000e6e0  pop     rbx
0x18000e6e1  retn
0x18000e6e2  mov     [rbp+24h], r13d
0x18000e6e6  test    r12b, 20h
0x18000e6ea  jnz     short loc_18000E708
0x18000e6ec  mov     rcx, [rbp+18h]; hObject
0x18000e6f0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e6f4  jz      short loc_18000E708
0x18000e6f6  call    cs:__imp_CloseHandle
0x18000e6fc  test    eax, eax
0x18000e6fe  jz      short loc_18000E6A9
0x18000e700  mov     qword ptr [rbp+18h], 0FFFFFFFFFFFFFFFFh
0x18000e708  mov     eax, r15d
0x18000e70b  jmp     short loc_18000E6AE
0x18000e70d  test    rsi, rsi
0x18000e710  jnz     short loc_18000E74E
0x18000e712  mov     ecx, 7FFFFFFEh
0x18000e717  lea     rdx, [rbp+34h]
0x18000e71b  nop     dword ptr [rax+rax+00h]
0x18000e720  test    rcx, rcx
0x18000e723  jz      loc_18000E62B
0x18000e729  movzx   eax, word ptr [rbx]
0x18000e72c  test    ax, ax
0x18000e72f  jz      loc_18000E62B
0x18000e735  mov     [rdx], ax
0x18000e738  add     rbx, 2
0x18000e73c  add     rdx, 2
0x18000e740  dec     rcx
0x18000e743  sub     rdi, 1
0x18000e747  jnz     short loc_18000E720
0x18000e749  jmp     loc_18000E62B
0x18000e74e  mov     rcx, [rbp+18h]; hFile
0x18000e752  lea     rdx, [rsp+0A8h+FileInformation]; lpFileInformation
0x18000e757  xorps   xmm0, xmm0
0x18000e75a  xor     eax, eax
0x18000e75c  movups  xmmword ptr [rsp+0A8h+FileInformation.dwFileAttributes], xmm0
0x18000e761  mov     [rsp+0A8h+FileInformation.nFileIndexLow], eax
0x18000e765  movups  xmmword ptr [rsp+0A8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18000e76a  movups  xmmword ptr [rsp+0A8h+FileInformation.nFileSizeHigh], xmm0
0x18000e76f  call    cs:__imp_GetFileInformationByHandle
0x18000e775  test    eax, eax
0x18000e777  jz      short loc_18000E712
0x18000e779  mov     rax, qword ptr [rsp+0A8h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x18000e77e  mov     [rsi], rax
0x18000e781  jmp     short loc_18000E712
0x18000e783  cmp     [r14+rax*8+10h], r13
0x18000e788  jnz     short loc_18000E793
0x18000e78a  add     r15d, 2
0x18000e78e  jmp     loc_18000E52B
0x18000e793  cmp     [r14+rax*8+18h], r13
0x18000e798  jnz     short loc_18000E7A3
0x18000e79a  add     r15d, 3
0x18000e79e  jmp     loc_18000E52B
0x18000e7a3  cmp     [r14+rax*8+20h], r13
0x18000e7a8  jnz     short loc_18000E7B3
0x18000e7aa  add     r15d, 4
0x18000e7ae  jmp     loc_18000E52B
0x18000e7b3  add     r15d, 5
0x18000e7b7  cmp     r15d, 1F4h
0x18000e7be  jl      loc_18000E514
0x18000e7c4  jmp     loc_18000E6A9
0x18000e7c9  xor     edx, edx; Val
0x18000e7cb  mov     r8d, 0FA0h; Size
0x18000e7d1  mov     rcx, r14; void *
0x18000e7d4  call    memset_0
0x18000e7d9  mov     cs:dword_1800FE53C, 1
0x18000e7e3  jmp     loc_18000E4E0
0x18000e7e8  mov     r8d, [rbx+14h]
0x18000e7ec  lea     rcx, aFreeingInvalid; "\n=======================\nFreeing Inva"...
0x18000e7f3  mov     rdx, rbx
0x18000e7f6  call    cs:__imp_DbgPrint
0x18000e7fc  jmp     loc_18000E6A6
0x18000e801  mov     r8d, [rbx+14h]
0x18000e805  lea     rcx, aFreeingInvalid_0; "\n=======================\nFreeing Inva"...
0x18000e80c  mov     rdx, rbx
0x18000e80f  call    cs:__imp_DbgPrint
0x18000e815  jmp     loc_18000E6A6
```
