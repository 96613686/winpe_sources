# AhgGetGenome

- ea: `0x18000a60c`
- end: `0x18000a8e7`
- name: `AhgGetGenome`
- size: `731`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180009200`

## callees

- `0x180009cdc`
- `0x18000a60c`
- `0x18000b1f0`
- `0x18000e240`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x18000a7dd`
- `KERNEL32!MapViewOfFile` at `0x18000a7dd`
- `KERNEL32!CreateFileMappingW` at `0x18000a79e`
- `KERNEL32!CreateFileMappingW` at `0x18000a79e`
- `KERNEL32!UnmapViewOfFile` at `0x18000a8a8`
- `KERNEL32!UnmapViewOfFile` at `0x18000a8a8`
- `KERNEL32!GetLastError` at `0x18000a757`
- `KERNEL32!GetLastError` at `0x18000a7ac`
- `KERNEL32!GetLastError` at `0x18000a7eb`
- `KERNEL32!GetLastError` at `0x18000a757`
- `KERNEL32!GetLastError` at `0x18000a7ac`
- `KERNEL32!GetLastError` at `0x18000a7eb`
- `KERNEL32!CloseHandle` at `0x18000a8b6`
- `KERNEL32!CloseHandle` at `0x18000a8c5`
- `KERNEL32!CloseHandle` at `0x18000a8b6`
- `KERNEL32!CloseHandle` at `0x18000a8c5`
- `KERNEL32!CreateFileW` at `0x18000a748`
- `KERNEL32!CreateFileW` at `0x18000a748`
- `ntdll!RtlFreeHeap` at `0x18000a6ef`
- `ntdll!RtlFreeHeap` at `0x18000a89a`
- `ntdll!RtlFreeHeap` at `0x18000a6ef`
- `ntdll!RtlFreeHeap` at `0x18000a89a`
- `ntdll!RtlAllocateHeap` at `0x18000a651`
- `ntdll!RtlAllocateHeap` at `0x18000a651`

## string_xrefs

- `0x18000a66c`: `AhgGenomeCreate`
- `0x18000a6cc`: `AhgGenomeCreate`
- `0x18000a6fa`: `Cannot create genome handle [%d]`
- `0x18000a84e`: `Cannot compute genome [%d]`

## pseudocode

```c
__int64 __fastcall AhgGetGenome(unsigned __int64 *a1, const WCHAR *a2)
{
  void *v2; // r15
  unsigned int v5; // esi
  _WORD *Heap; // rax
  void *v7; // rbx
  __int64 v8; // rcx
  const WCHAR *v9; // r8
  __int64 v10; // rdx
  _WORD *v11; // rcx
  const void *v12; // r12
  HANDLE FileW; // rax
  void *v14; // r14
  DWORD LastError; // eax
  const char *v16; // r9
  __int64 v17; // r8
  DWORD v18; // edi
  HANDLE FileMappingW; // rax
  const void *v20; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-48h]
  int v23; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v24; // [rsp+80h] [rbp+18h] BYREF

  v2 = 0;
  *a1 = 0;
  v23 = 0;
  v5 = 8;
  v24 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x338u);
  v7 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "AhgGenomeCreate", 172, "Out of memory");
LABEL_11:
    AslLogCallPrintf(1, "AhgGetGenome", 849, "Cannot create genome handle [%d]", v5);
    return v5;
  }
  v8 = 2147483646;
  v9 = a2;
  v10 = 260;
  do
  {
    if ( !v8 )
      break;
    if ( !*v9 )
      break;
    *Heap++ = *v9++;
    --v8;
    --v10;
  }
  while ( v10 );
  v11 = Heap - 1;
  if ( v10 )
    v11 = Heap;
  *v11 = 0;
  if ( !v10 )
  {
    AslLogCallPrintf(1, "AhgGenomeCreate", 179, "Buffer overflow");
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    v5 = 111;
    goto LABEL_11;
  }
  v12 = 0;
  FileW = CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v14 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v16 = "Bad file name [%d]";
    v17 = 866;
    v18 = LastError;
  }
  else
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 0x11000002u, 0, 0, 0);
    v2 = FileMappingW;
    if ( FileMappingW )
    {
      v20 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      v12 = v20;
      if ( v20 )
      {
        LastError = AhgGenomeGetAll(v7, v14, v20);
        v18 = LastError;
        if ( LastError )
        {
          v16 = "Cannot get attributes [%d]";
          v17 = 903;
        }
        else
        {
          LastError = AhgGenomeCompute(&v23, &v24, v7);
          v18 = LastError;
          if ( !LastError )
          {
            *a1 = ((unsigned __int64)v24 << 32) | ((BYTE2(v23) | ((unsigned __int8)v23 << 8)) << 16);
            v18 = 0;
            goto LABEL_26;
          }
          v16 = "Cannot compute genome [%d]";
          v17 = 913;
        }
      }
      else
      {
        LastError = GetLastError();
        v18 = LastError;
        if ( LastError == 8 )
          goto LABEL_26;
        v16 = "Failed to map a view of file mapping [%d]";
        v17 = 892;
      }
    }
    else
    {
      LastError = GetLastError();
      v18 = LastError;
      if ( LastError == 8 )
        goto LABEL_26;
      v16 = "Failed to map file [%d]";
      v17 = 879;
    }
  }
  dwCreationDisposition[0] = LastError;
  AslLogCallPrintf(1, "AhgGetGenome", v17, v16, *(_QWORD *)dwCreationDisposition);
LABEL_26:
  v5 = v18;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( v12 )
    UnmapViewOfFile(v12);
  if ( v2 )
    CloseHandle(v2);
  if ( v14 != (void *)-1LL )
    CloseHandle(v14);
  return v5;
}

```

## disassembly

```asm
0x18000a60c  mov     rax, rsp
0x18000a60f  mov     [rax+10h], rbx
0x18000a613  mov     [rax+20h], rsi
0x18000a617  push    rdi
0x18000a618  push    r12
0x18000a61a  push    r13
0x18000a61c  push    r14
0x18000a61e  push    r15
0x18000a620  sub     rsp, 40h
0x18000a624  xor     r15d, r15d
0x18000a627  mov     r13, rcx
0x18000a62a  mov     [rcx], r15
0x18000a62d  mov     rdi, rdx
0x18000a630  mov     rcx, gs:60h
0x18000a639  mov     r8d, 338h; Size
0x18000a63f  mov     [rax+8], r15d
0x18000a643  lea     esi, [r15+8]
0x18000a647  mov     [rax+18h], r15d
0x18000a64b  mov     edx, esi; Flags
0x18000a64d  mov     rcx, [rcx+30h]; HeapHandle
0x18000a651  call    cs:__imp_RtlAllocateHeap
0x18000a657  mov     rbx, rax
0x18000a65a  test    rax, rax
0x18000a65d  jnz     short loc_18000A67D
0x18000a65f  lea     r9, aOutOfMemory; "Out of memory"
0x18000a666  mov     r8d, 0ACh
0x18000a66c  lea     rdx, aAhggenomecreat; "AhgGenomeCreate"
0x18000a673  lea     ecx, [rsi-7]
0x18000a676  call    AslLogCallPrintf
0x18000a67b  jmp     short loc_18000A6FA
0x18000a67d  mov     ecx, 7FFFFFFEh
0x18000a682  mov     r8, rdi
0x18000a685  mov     edx, 104h
0x18000a68a  test    rcx, rcx
0x18000a68d  jz      short loc_18000A6AE
0x18000a68f  movzx   r9d, word ptr [r8]
0x18000a693  test    r9w, r9w
0x18000a697  jz      short loc_18000A6AE
0x18000a699  mov     [rax], r9w
0x18000a69d  add     r8, 2
0x18000a6a1  add     rax, 2
0x18000a6a5  dec     rcx
0x18000a6a8  sub     rdx, 1
0x18000a6ac  jnz     short loc_18000A68A
0x18000a6ae  test    rdx, rdx
0x18000a6b1  lea     rcx, [rax-2]
0x18000a6b5  cmovnz  rcx, rax
0x18000a6b9  mov     [rcx], r15w
0x18000a6bd  jnz     short loc_18000A721
0x18000a6bf  lea     r9, aBufferOverflow; "Buffer overflow"
0x18000a6c6  mov     r8d, 0B3h
0x18000a6cc  lea     rdx, aAhggenomecreat; "AhgGenomeCreate"
0x18000a6d3  mov     ecx, 1
0x18000a6d8  call    AslLogCallPrintf
0x18000a6dd  mov     rcx, gs:60h
0x18000a6e6  mov     r8, rbx; P
0x18000a6e9  xor     edx, edx; Flags
0x18000a6eb  mov     rcx, [rcx+30h]; HeapHandle
0x18000a6ef  call    cs:__imp_RtlFreeHeap
0x18000a6f5  mov     esi, 6Fh ; 'o'
0x18000a6fa  lea     r9, aCannotCreateGe; "Cannot create genome handle [%d]"
0x18000a701  mov     [rsp+68h+dwCreationDisposition], esi
0x18000a705  mov     r8d, 351h
0x18000a70b  lea     rdx, aAhggetgenome; "AhgGetGenome"
0x18000a712  mov     ecx, 1
0x18000a717  call    AslLogCallPrintf
0x18000a71c  jmp     loc_18000A8CB
0x18000a721  xor     r9d, r9d; lpSecurityAttributes
0x18000a724  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x18000a729  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000a731  mov     edx, 80000000h; dwDesiredAccess
0x18000a736  mov     rcx, rdi; lpFileName
0x18000a739  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a741  mov     r12, r15
0x18000a744  lea     r8d, [r9+7]; dwShareMode
0x18000a748  call    cs:__imp_CreateFileW
0x18000a74e  mov     r14, rax
0x18000a751  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a755  jnz     short loc_18000A786
0x18000a757  call    cs:__imp_GetLastError
0x18000a75d  lea     r9, aBadFileNameD; "Bad file name [%d]"
0x18000a764  mov     r8d, 362h
0x18000a76a  mov     edi, eax
0x18000a76c  lea     rdx, aAhggetgenome; "AhgGetGenome"
0x18000a773  mov     [rsp+68h+dwCreationDisposition], eax
0x18000a777  mov     ecx, 1
0x18000a77c  call    AslLogCallPrintf
0x18000a781  jmp     loc_18000A886
0x18000a786  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r15; lpName
0x18000a78b  xor     r9d, r9d; dwMaximumSizeHigh
0x18000a78e  xor     edx, edx; lpFileMappingAttributes
0x18000a790  mov     [rsp+68h+dwCreationDisposition], r15d; dwMaximumSizeLow
0x18000a795  mov     r8d, 11000002h; flProtect
0x18000a79b  mov     rcx, r14; hFile
0x18000a79e  call    cs:__imp_CreateFileMappingW
0x18000a7a4  mov     r15, rax
0x18000a7a7  test    rax, rax
0x18000a7aa  jnz     short loc_18000A7CB
0x18000a7ac  call    cs:__imp_GetLastError
0x18000a7b2  mov     edi, eax
0x18000a7b4  cmp     eax, esi
0x18000a7b6  jz      loc_18000A886
0x18000a7bc  lea     r9, aFailedToMapFil; "Failed to map file [%d]"
0x18000a7c3  mov     r8d, 36Fh
0x18000a7c9  jmp     short loc_18000A76C
0x18000a7cb  xor     r9d, r9d; dwFileOffsetLow
0x18000a7ce  mov     qword ptr [rsp+68h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x18000a7d3  xor     r8d, r8d; dwFileOffsetHigh
0x18000a7d6  mov     rcx, rax; hFileMappingObject
0x18000a7d9  lea     edx, [r9+4]; dwDesiredAccess
0x18000a7dd  call    cs:__imp_MapViewOfFile
0x18000a7e3  mov     r12, rax
0x18000a7e6  test    rax, rax
0x18000a7e9  jnz     short loc_18000A80D
0x18000a7eb  call    cs:__imp_GetLastError
0x18000a7f1  mov     edi, eax
0x18000a7f3  cmp     eax, esi
0x18000a7f5  jz      loc_18000A886
0x18000a7fb  lea     r9, aFailedToMapAVi; "Failed to map a view of file mapping [%"...
0x18000a802  mov     r8d, 37Ch
0x18000a808  jmp     loc_18000A76C
0x18000a80d  mov     r8, rax
0x18000a810  mov     rdx, r14
0x18000a813  mov     rcx, rbx
0x18000a816  call    AhgGenomeGetAll
0x18000a81b  mov     edi, eax
0x18000a81d  test    eax, eax
0x18000a81f  jz      short loc_18000A833
0x18000a821  lea     r9, aCannotGetAttri; "Cannot get attributes [%d]"
0x18000a828  mov     r8d, 387h
0x18000a82e  jmp     loc_18000A76C
0x18000a833  mov     r8, rbx
0x18000a836  lea     rdx, [rsp+68h+arg_10]
0x18000a83e  lea     rcx, [rsp+68h+arg_0]
0x18000a843  call    AhgGenomeCompute
0x18000a848  mov     edi, eax
0x18000a84a  test    eax, eax
0x18000a84c  jz      short loc_18000A860
0x18000a84e  lea     r9, aCannotComputeG; "Cannot compute genome [%d]"
0x18000a855  mov     r8d, 391h
0x18000a85b  jmp     loc_18000A76C
0x18000a860  movzx   ecx, [rsp+68h+arg_0]
0x18000a865  movzx   eax, [rsp+68h+arg_2]
0x18000a86a  shl     ecx, 8
0x18000a86d  or      ecx, eax
0x18000a86f  mov     eax, [rsp+68h+arg_10]
0x18000a876  shl     rax, 20h
0x18000a87a  shl     ecx, 10h
0x18000a87d  or      rcx, rax
0x18000a880  mov     [r13+0], rcx
0x18000a884  xor     edi, edi
0x18000a886  mov     rcx, gs:60h
0x18000a88f  mov     r8, rbx; P
0x18000a892  xor     edx, edx; Flags
0x18000a894  mov     esi, edi
0x18000a896  mov     rcx, [rcx+30h]; HeapHandle
0x18000a89a  call    cs:__imp_RtlFreeHeap
0x18000a8a0  test    r12, r12
0x18000a8a3  jz      short loc_18000A8AE
0x18000a8a5  mov     rcx, r12; lpBaseAddress
0x18000a8a8  call    cs:__imp_UnmapViewOfFile
0x18000a8ae  test    r15, r15
0x18000a8b1  jz      short loc_18000A8BC
0x18000a8b3  mov     rcx, r15; hObject
0x18000a8b6  call    cs:__imp_CloseHandle
0x18000a8bc  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18000a8c0  jz      short loc_18000A8CB
0x18000a8c2  mov     rcx, r14; hObject
0x18000a8c5  call    cs:__imp_CloseHandle
0x18000a8cb  lea     r11, [rsp+68h+var_28]
0x18000a8d0  mov     eax, esi
0x18000a8d2  mov     rbx, [r11+38h]
0x18000a8d6  mov     rsi, [r11+48h]
0x18000a8da  mov     rsp, r11
0x18000a8dd  pop     r15
0x18000a8df  pop     r14
0x18000a8e1  pop     r13
0x18000a8e3  pop     r12
0x18000a8e5  pop     rdi
0x18000a8e6  retn
```
