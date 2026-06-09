# BaseDllCaptureIniFileParameters

- ea: `0x18000e468`
- end: `0x18000eaad`
- name: `BaseDllCaptureIniFileParameters`
- size: `1605`
- prototype: `__int64 __fastcall(int, int, int, int, wchar_t *String, PCSZ SourceString, __int64, wchar_t *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000d700`

## callees

- `0x18000e468`
- `0x180010644`
- `0x180031114`
- `0x180084010`

## import_xrefs

- `ntdll!strlen` at `0x18000e892`
- `ntdll!strlen` at `0x18000e994`
- `ntdll!strlen` at `0x18000e892`
- `ntdll!strlen` at `0x18000e994`
- `ntdll!wcslen` at `0x18000e74a`
- `ntdll!wcslen` at `0x18000e76b`
- `ntdll!wcslen` at `0x18000e7a8`
- `ntdll!wcslen` at `0x18000e74a`
- `ntdll!wcslen` at `0x18000e76b`
- `ntdll!wcslen` at `0x18000e7a8`
- `ntdll!RtlInitAnsiString` at `0x18000e5df`
- `ntdll!RtlInitAnsiString` at `0x18000e614`
- `ntdll!RtlInitAnsiString` at `0x18000e5df`
- `ntdll!RtlInitAnsiString` at `0x18000e614`
- `ntdll!RtlGetLongestNtPathLength` at `0x18000e4e5`
- `ntdll!RtlGetLongestNtPathLength` at `0x18000e7b8`
- `ntdll!RtlGetLongestNtPathLength` at `0x18000e4e5`
- `ntdll!RtlGetLongestNtPathLength` at `0x18000e7b8`
- `ntdll!RtlInitUnicodeString` at `0x18000e59e`
- `ntdll!RtlInitUnicodeString` at `0x18000e5f1`
- `ntdll!RtlInitUnicodeString` at `0x18000e626`
- `ntdll!RtlInitUnicodeString` at `0x18000e59e`
- `ntdll!RtlInitUnicodeString` at `0x18000e5f1`
- `ntdll!RtlInitUnicodeString` at `0x18000e626`
- `ntdll!RtlFreeHeap` at `0x18000ea01`
- `ntdll!RtlFreeHeap` at `0x18000ea01`
- `ntdll!RtlAllocateHeap` at `0x18000e533`
- `ntdll!RtlAllocateHeap` at `0x18000e533`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000e508`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18000e508`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x18000e9cc`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x18000e9cc`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18000e8a3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x18000e8a3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000e793`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000e793`

## pseudocode

```c
__int64 __fastcall BaseDllCaptureIniFileParameters(
        __int64 a1,
        int a2,
        char a3,
        char a4,
        wchar_t *String,
        PCSZ SourceString,
        const char *a7,
        wchar_t *a8,
        int *a9,
        _QWORD *a10)
{
  char v11; // r14
  unsigned int v12; // r15d
  __int64 v13; // rax
  wchar_t *v14; // rsi
  int v15; // r13d
  __int64 v16; // rdx
  __int64 v17; // rcx
  ULONG LongestNtPathLength; // ebx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdi
  int v22; // ebx
  ULONG *GlobalData; // rax
  char *Heap; // rax
  char *v25; // rbx
  UNICODE_STRING *v26; // r9
  char *v27; // rdi
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  PCSZ v31; // rdx
  char v32; // al
  int v33; // eax
  unsigned int v35; // eax
  __int64 v36; // rcx
  unsigned int v37; // eax
  int v38; // eax
  DWORD FullPathNameA; // eax
  unsigned __int64 v40; // r8
  UNICODE_STRING *v41; // rdx
  _WORD *v42; // rcx
  USHORT v43; // r15
  __int16 v44; // cx
  __int16 v45; // ax
  __int16 v46; // cx
  __int16 v47; // ax
  __int16 v48; // ax
  _WORD *v50; // rax
  __int64 (__fastcall *EightBitStringToUnicodeStringRoutine)(char *, __int128 *, _QWORD); // rax
  int v52; // r12d
  PCSZ v53; // [rsp+20h] [rbp-28h]
  __int128 v54; // [rsp+28h] [rbp-20h] BYREF
  unsigned int v55; // [rsp+90h] [rbp+48h]
  char v58; // [rsp+A8h] [rbp+60h]
  unsigned int Stringa; // [rsp+B0h] [rbp+68h]

  v58 = a4;
  v11 = a1;
  v54 = 0;
  if ( String )
  {
    if ( (_BYTE)a1 )
      v37 = wcslen(String);
    else
      v37 = strlen((const char *)String);
    a4 = v58;
    v12 = v37;
  }
  else
  {
    v12 = 0;
  }
  if ( SourceString )
  {
    LOBYTE(a1) = v11;
    v55 = BaseDllIniFileNameLength(a1, &SourceString);
    v13 = (__int64)a7;
    v53 = a7;
  }
  else
  {
    v55 = 0;
    v13 = 0;
    v53 = 0;
    a7 = 0;
  }
  if ( v13 )
  {
    LOBYTE(a1) = v11;
    v35 = BaseDllIniFileNameLength(a1, &a7);
    v53 = a7;
    Stringa = v35;
  }
  else
  {
    Stringa = 0;
  }
  v14 = a8;
  if ( !a8 || a9 )
  {
    v15 = 0;
  }
  else
  {
    v36 = (__int64)a8;
    if ( a4 )
    {
      if ( v11 )
      {
        if ( *a8 )
        {
          do
          {
            do
            {
              v48 = *(_WORD *)v36;
              v36 += 2;
            }
            while ( v48 );
          }
          while ( *(_WORD *)v36 );
        }
        v36 = (v36 - (__int64)a8) >> 1;
      }
      else
      {
        if ( *(_BYTE *)a8 )
        {
          do
          {
            while ( *(_BYTE *)v36++ )
              ;
          }
          while ( *(_BYTE *)v36 );
        }
        LODWORD(v36) = v36 - (_DWORD)a8;
      }
      v15 = v36;
    }
    else
    {
      if ( v11 )
        v38 = wcslen(a8);
      else
        v38 = strlen((const char *)a8);
      v15 = v38;
    }
  }
  if ( !String
    || (!v11
      ? (FullPathNameA = GetFullPathNameA((LPCSTR)String, 0, 0, 0))
      : (FullPathNameA = GetFullPathNameW(String, 0, 0, 0)),
        LongestNtPathLength = wcslen(L"\\\\?\\") + 1 + FullPathNameA,
        LongestNtPathLength <= RtlGetLongestNtPathLength()) )
  {
    LongestNtPathLength = RtlGetLongestNtPathLength();
  }
  v21 = 2 * LongestNtPathLength;
  v22 = v21 + 344;
  if ( !v11 )
    v22 += 2 * v12 + 2;
  GlobalData = (ULONG *)KernelBaseGetGlobalData(v17, v16, v19, v20);
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, v22 + 2 * (v55 + v15 + Stringa + 3));
  v25 = Heap;
  if ( !Heap )
    return 3221225495LL;
  *(_DWORD *)Heap = a2;
  v26 = (UNICODE_STRING *)(Heap + 40);
  Heap[4] = a3;
  Heap[136] = v58;
  *((_WORD *)Heap + 29) = v21;
  v27 = &Heap[v21 + 344];
  Heap[5] = v11;
  *((_QWORD *)Heap + 2) = 0;
  Heap[6] = 0;
  *((_QWORD *)Heap + 8) = Heap + 344;
  *((_WORD *)Heap + 28) = 0;
  if ( !String )
  {
    RtlInitUnicodeString((PUNICODE_STRING)(Heap + 40), L"win.ini");
    v28 = BaseDllIniFileMapping;
    *(_OWORD *)(v25 + 24) = *(_OWORD *)(v25 + 40);
    v29 = *(_QWORD *)(v28 + 16);
    if ( v29 )
      v30 = BaseStaticServerData + v29 - *(_QWORD *)(BaseStaticServerData + 2536);
    else
      v30 = 0;
    *((_QWORD *)v25 + 1) = v30;
    goto LABEL_18;
  }
  *((_WORD *)Heap + 21) = 2 * v12 + 2;
  if ( v11 )
  {
    v26->Length = 2 * v12;
    *((_QWORD *)Heap + 6) = String;
LABEL_56:
    v40 = *((_QWORD *)v25 + 6);
    v41 = (UNICODE_STRING *)(v25 + 24);
    *((_WORD *)v25 + 12) = 0;
    v42 = (_WORD *)(v40 + 2LL * v12);
    if ( v12 )
    {
      while ( 1 )
      {
        v50 = v42--;
        if ( (unsigned __int64)v42 <= v40 )
          break;
        if ( *v42 == 92 || *v42 == 47 || *v42 == 58 )
        {
          v42 = v50;
          break;
        }
      }
    }
    *((_QWORD *)v25 + 4) = v42;
    v43 = 2 * (v12 - ((__int64)((__int64)v42 - v40) >> 1));
    v41->Length = v43;
    *((_WORD *)v25 + 13) = v43 + 2;
    BaseDllFindIniFileNameMapping(v26, v41);
LABEL_18:
    v31 = SourceString;
    if ( SourceString )
    {
      v44 = 2 * v55;
      *((_WORD *)v25 + 37) = 2 * v55 + 1;
      *((_WORD *)v25 + 53) = 2 * (2 * v55 + 1);
      if ( v11 )
      {
        *((_QWORD *)v25 + 10) = v27;
        v45 = 0;
        *((_QWORD *)v25 + 14) = v31;
        v27 += 2 * v55 + 1;
      }
      else
      {
        *((_QWORD *)v25 + 14) = v27;
        v27 += 2 * v55 + 2;
        *((_QWORD *)v25 + 10) = v31;
        v45 = v55;
        v44 = 0;
      }
      *((_WORD *)v25 + 36) = v45;
      *((_WORD *)v25 + 52) = v44;
    }
    else
    {
      RtlInitAnsiString((PANSI_STRING)(v25 + 72), 0);
      RtlInitUnicodeString((PUNICODE_STRING)(v25 + 104), 0);
    }
    if ( v53 )
    {
      v46 = 2 * Stringa;
      *((_WORD *)v25 + 45) = 2 * Stringa + 1;
      *((_WORD *)v25 + 61) = 2 * (2 * Stringa + 1);
      if ( v11 )
      {
        *((_QWORD *)v25 + 12) = v27;
        v47 = 0;
        *((_QWORD *)v25 + 16) = v53;
        v27 += 2 * Stringa + 1;
      }
      else
      {
        *((_QWORD *)v25 + 16) = v27;
        v27 += 2 * Stringa + 2;
        *((_QWORD *)v25 + 12) = v53;
        v47 = Stringa;
        v46 = 0;
      }
      *((_WORD *)v25 + 44) = v47;
      *((_WORD *)v25 + 60) = v46;
    }
    else
    {
      RtlInitAnsiString((PANSI_STRING)(v25 + 88), 0);
      RtlInitUnicodeString((PUNICODE_STRING)(v25 + 120), 0);
    }
    v32 = v25[4];
    if ( v14 )
    {
      if ( !v32 )
      {
        if ( a9 )
          v33 = *a9;
        else
          v33 = 0;
        *((_DWORD *)v25 + 37) = v33;
        *((_DWORD *)v25 + 36) = 0;
        if ( !v11 )
        {
          *((_QWORD *)v25 + 19) = v14;
          *((_QWORD *)v25 + 20) = 0;
          goto LABEL_29;
        }
        *((_QWORD *)v25 + 20) = v14;
        goto LABEL_28;
      }
      if ( v11 )
      {
        *((_QWORD *)v25 + 20) = v14;
        *((_DWORD *)v25 + 42) = 2 * v15;
        *v27 = 0;
        *((_QWORD *)v25 + 18) = v27;
        *((_DWORD *)v25 + 38) = 0;
        goto LABEL_29;
      }
      *((_QWORD *)v25 + 18) = v14;
      *((_DWORD *)v25 + 38) = v15;
      *(_WORD *)v27 = 0;
      *((_QWORD *)v25 + 20) = v27;
    }
    else
    {
      *((_QWORD *)v25 + 20) = 0;
      if ( !v32 )
      {
        *((_QWORD *)v25 + 18) = 0;
LABEL_28:
        *((_QWORD *)v25 + 19) = 0;
LABEL_29:
        *a10 = v25;
        return 0;
      }
      *((_QWORD *)v25 + 18) = 0;
      *((_DWORD *)v25 + 38) = 0;
    }
    *((_DWORD *)v25 + 42) = 0;
    goto LABEL_29;
  }
  *((_QWORD *)&v54 + 1) = String;
  LOWORD(v54) = v12;
  WORD1(v54) = v12 + 1;
  v26->Length = 0;
  *((_QWORD *)Heap + 6) = v27;
  v27 += 2 * v12 + 2;
  EightBitStringToUnicodeStringRoutine = (__int64 (__fastcall *)(char *, __int128 *, _QWORD))GetEightBitStringToUnicodeStringRoutine();
  v52 = EightBitStringToUnicodeStringRoutine(v25 + 40, &v54, 0);
  if ( v52 >= 0 )
  {
    v26 = (UNICODE_STRING *)(v25 + 40);
    goto LABEL_56;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v25);
  return (unsigned int)v52;
}

```

## disassembly

```asm
0x18000e468  mov     [rsp-40h+arg_18], r9b
0x18000e46d  mov     [rsp-40h+arg_10], r8b
0x18000e472  mov     [rsp-40h+arg_8], edx
0x18000e476  push    rbp
0x18000e477  push    rbx
0x18000e478  push    rsi
0x18000e479  push    rdi
0x18000e47a  push    r12
0x18000e47c  push    r13
0x18000e47e  push    r14
0x18000e480  push    r15
0x18000e482  mov     rbp, rsp
0x18000e485  sub     rsp, 48h
0x18000e489  mov     r12, [rbp+String]
0x18000e48d  xor     ebx, ebx
0x18000e48f  xorps   xmm0, xmm0
0x18000e492  mov     r14b, cl
0x18000e495  movups  [rbp+var_20], xmm0
0x18000e499  test    r12, r12
0x18000e49c  jnz     loc_18000E73E
0x18000e4a2  mov     r15d, ebx
0x18000e4a5  cmp     [rbp+SourceString], rbx
0x18000e4a9  jnz     loc_18000E69A
0x18000e4af  mov     [rbp+arg_0], ebx
0x18000e4b2  mov     rax, rbx
0x18000e4b5  mov     [rbp+var_28], rbx
0x18000e4b9  mov     [rbp+arg_30], rbx
0x18000e4bd  test    rax, rax
0x18000e4c0  jnz     loc_18000E6B6
0x18000e4c6  mov     dword ptr [rbp+String], ebx
0x18000e4c9  mov     rsi, [rbp+arg_38]
0x18000e4d0  test    rsi, rsi
0x18000e4d3  jnz     loc_18000E6E8
0x18000e4d9  mov     r13d, ebx
0x18000e4dc  test    r12, r12
0x18000e4df  jnz     loc_18000E77F
0x18000e4e5  call    cs:__imp_RtlGetLongestNtPathLength
0x18000e4ec  nop     dword ptr [rax+rax+00h]
0x18000e4f1  mov     ebx, eax
0x18000e4f3  lea     edi, [rbx+rbx]
0x18000e4f6  lea     ebx, [rdi+158h]
0x18000e4fc  test    r14b, r14b
0x18000e4ff  jnz     short loc_18000E508
0x18000e501  lea     ebx, [rbx+r15*2]
0x18000e505  add     ebx, 2
0x18000e508  call    cs:__imp_KernelBaseGetGlobalData
0x18000e50f  nop     dword ptr [rax+rax+00h]
0x18000e514  mov     ecx, dword ptr [rbp+String]
0x18000e517  add     ecx, 3
0x18000e51a  add     ecx, r13d
0x18000e51d  add     ecx, [rbp+arg_0]
0x18000e520  lea     r8d, [rbx+rcx*2]; Size
0x18000e524  mov     rcx, gs:60h
0x18000e52d  mov     edx, [rax]; Flags
0x18000e52f  mov     rcx, [rcx+30h]; HeapHandle
0x18000e533  call    cs:__imp_RtlAllocateHeap
0x18000e53a  nop     dword ptr [rax+rax+00h]
0x18000e53f  mov     rbx, rax
0x18000e542  test    rax, rax
0x18000e545  jz      loc_18000E871
0x18000e54b  mov     eax, [rbp+arg_8]
0x18000e54e  lea     rcx, [rbx+158h]
0x18000e555  mov     [rbx], eax
0x18000e557  lea     r9, [rbx+28h]
0x18000e55b  mov     al, [rbp+arg_10]
0x18000e55e  mov     [rbx+4], al
0x18000e561  mov     al, [rbp+arg_18]
0x18000e564  mov     [rbx+88h], al
0x18000e56a  xor     eax, eax
0x18000e56c  mov     [rbx+3Ah], di
0x18000e570  add     rdi, rcx
0x18000e573  mov     [rbx+5], r14b
0x18000e577  mov     qword ptr [rbx+10h], 0
0x18000e57f  mov     byte ptr [rbx+6], 0
0x18000e583  mov     [rbx+40h], rcx
0x18000e587  mov     [rbx+38h], ax
0x18000e58b  test    r12, r12
0x18000e58e  jnz     loc_18000E7FC
0x18000e594  lea     rdx, SourceString; "win.ini"
0x18000e59b  mov     rcx, r9; DestinationString
0x18000e59e  call    cs:__imp_RtlInitUnicodeString
0x18000e5a5  nop     dword ptr [rax+rax+00h]
0x18000e5aa  movups  xmm0, xmmword ptr [rbx+28h]
0x18000e5ae  mov     rax, cs:BaseDllIniFileMapping
0x18000e5b5  movdqu  xmmword ptr [rbx+18h], xmm0
0x18000e5ba  mov     rcx, [rax+10h]
0x18000e5be  test    rcx, rcx
0x18000e5c1  jnz     loc_18000E6D2
0x18000e5c7  mov     rcx, r12
0x18000e5ca  mov     [rbx+8], rcx
0x18000e5ce  mov     rdx, [rbp+SourceString]; SourceString
0x18000e5d2  test    rdx, rdx
0x18000e5d5  jnz     loc_18000E8B4
0x18000e5db  lea     rcx, [rbx+48h]; DestinationString
0x18000e5df  call    cs:__imp_RtlInitAnsiString
0x18000e5e6  nop     dword ptr [rax+rax+00h]
0x18000e5eb  xor     edx, edx; SourceString
0x18000e5ed  lea     rcx, [rbx+68h]; DestinationString
0x18000e5f1  call    cs:__imp_RtlInitUnicodeString
0x18000e5f8  nop     dword ptr [rax+rax+00h]
0x18000e5fd  mov     r10d, 1
0x18000e603  mov     rdx, [rbp+var_28]; SourceString
0x18000e607  test    rdx, rdx
0x18000e60a  jnz     loc_18000E8FC
0x18000e610  lea     rcx, [rbx+58h]; DestinationString
0x18000e614  call    cs:__imp_RtlInitAnsiString
0x18000e61b  nop     dword ptr [rax+rax+00h]
0x18000e620  xor     edx, edx; SourceString
0x18000e622  lea     rcx, [rbx+78h]; DestinationString
0x18000e626  call    cs:__imp_RtlInitUnicodeString
0x18000e62d  nop     dword ptr [rax+rax+00h]
0x18000e632  mov     al, [rbx+4]
0x18000e635  test    rsi, rsi
0x18000e638  jz      loc_18000E715
0x18000e63e  test    al, al
0x18000e640  jnz     loc_18000EA5F
0x18000e646  mov     rax, [rbp+arg_40]
0x18000e64d  test    rax, rax
0x18000e650  jz      loc_18000E7F4
0x18000e656  mov     eax, [rax]
0x18000e658  mov     [rbx+94h], eax
0x18000e65e  mov     [rbx+90h], r12d
0x18000e665  test    r14b, r14b
0x18000e668  jz      loc_18000E7E1
0x18000e66e  mov     [rbx+0A0h], rsi
0x18000e675  mov     [rbx+98h], r12
0x18000e67c  mov     rax, [rbp+arg_48]
0x18000e683  mov     [rax], rbx
0x18000e686  xor     eax, eax
0x18000e688  add     rsp, 48h
0x18000e68c  pop     r15
0x18000e68e  pop     r14
0x18000e690  pop     r13
0x18000e692  pop     r12
0x18000e694  pop     rdi
0x18000e695  pop     rsi
0x18000e696  pop     rbx
0x18000e697  pop     rbp
0x18000e698  retn
0x18000e69a  lea     rdx, [rbp+SourceString]
0x18000e69e  mov     cl, r14b
0x18000e6a1  call    BaseDllIniFileNameLength
0x18000e6a6  mov     [rbp+arg_0], eax
0x18000e6a9  mov     rax, [rbp+arg_30]
0x18000e6ad  mov     [rbp+var_28], rax
0x18000e6b1  jmp     loc_18000E4BD
0x18000e6b6  lea     rdx, [rbp+arg_30]
0x18000e6ba  mov     cl, r14b
0x18000e6bd  call    BaseDllIniFileNameLength
0x18000e6c2  mov     rcx, [rbp+arg_30]
0x18000e6c6  mov     [rbp+var_28], rcx
0x18000e6ca  mov     dword ptr [rbp+String], eax
0x18000e6cd  jmp     loc_18000E4C9
0x18000e6d2  mov     rax, cs:BaseStaticServerData
0x18000e6d9  sub     rcx, [rax+9E8h]
0x18000e6e0  add     rcx, rax
0x18000e6e3  jmp     loc_18000E5CA
0x18000e6e8  cmp     [rbp+arg_40], rbx
0x18000e6ef  jnz     loc_18000E4D9
0x18000e6f5  mov     rcx, rsi; Str
0x18000e6f8  test    r9b, r9b
0x18000e6fb  jz      short loc_18000E762
0x18000e6fd  test    r14b, r14b
0x18000e700  jnz     loc_18000E87B
0x18000e706  cmp     [rsi], bl
0x18000e708  jnz     loc_18000E958
0x18000e70e  sub     ecx, esi
0x18000e710  jmp     loc_18000E88A
0x18000e715  mov     [rbx+0A0h], r12
0x18000e71c  test    al, al
0x18000e71e  jz      loc_18000E7D1
0x18000e724  mov     [rbx+90h], r12
0x18000e72b  mov     [rbx+98h], r12d
0x18000e732  mov     [rbx+0A8h], r12d
0x18000e739  jmp     loc_18000E67C
0x18000e73e  mov     rcx, r12; Str
0x18000e741  test    r14b, r14b
0x18000e744  jz      loc_18000E994
0x18000e74a  call    cs:__imp_wcslen
0x18000e751  nop     dword ptr [rax+rax+00h]
0x18000e756  mov     r9b, [rbp+arg_18]
0x18000e75a  mov     r15, rax
0x18000e75d  jmp     loc_18000E4A5
0x18000e762  test    r14b, r14b
0x18000e765  jz      loc_18000E892
0x18000e76b  call    cs:__imp_wcslen
0x18000e772  nop     dword ptr [rax+rax+00h]
0x18000e777  mov     r13, rax
0x18000e77a  jmp     loc_18000E4DC
0x18000e77f  xor     r9d, r9d; lpFilePart
0x18000e782  xor     r8d, r8d; lpBuffer
0x18000e785  xor     edx, edx; nBufferLength
0x18000e787  mov     rcx, r12; lpFileName
0x18000e78a  test    r14b, r14b
0x18000e78d  jz      loc_18000E8A3
0x18000e793  call    cs:__imp_GetFullPathNameW
0x18000e79a  nop     dword ptr [rax+rax+00h]
0x18000e79f  lea     rcx, String; "\\\\?\\"
0x18000e7a6  mov     ebx, eax
0x18000e7a8  call    cs:__imp_wcslen
0x18000e7af  nop     dword ptr [rax+rax+00h]
0x18000e7b4  inc     eax
0x18000e7b6  add     ebx, eax
0x18000e7b8  call    cs:__imp_RtlGetLongestNtPathLength
0x18000e7bf  nop     dword ptr [rax+rax+00h]
0x18000e7c4  cmp     ebx, eax
0x18000e7c6  ja      loc_18000E4F3
0x18000e7cc  jmp     loc_18000E4E5
0x18000e7d1  mov     qword ptr [rbx+90h], 0
0x18000e7dc  jmp     loc_18000E675
0x18000e7e1  mov     [rbx+98h], rsi
0x18000e7e8  mov     [rbx+0A0h], r12
0x18000e7ef  jmp     loc_18000E67C
0x18000e7f4  mov     eax, r12d
0x18000e7f7  jmp     loc_18000E658
0x18000e7fc  movzx   ecx, r15w
0x18000e800  mov     r10d, 2
0x18000e806  add     cx, cx
0x18000e809  lea     eax, [r10+rcx]
0x18000e80d  mov     [rbx+2Ah], ax
0x18000e811  test    r14b, r14b
0x18000e814  jz      loc_18000E9A5
0x18000e81a  mov     [r9], cx
0x18000e81e  mov     [rbx+30h], r12
0x18000e822  mov     r8, [rbx+30h]
0x18000e826  lea     rdx, [rbx+18h]; String1
0x18000e82a  xor     r12d, r12d
0x18000e82d  mov     eax, r15d
0x18000e830  mov     [rdx], r12w
0x18000e834  lea     rcx, [r8+rax*2]
0x18000e838  test    r15d, r15d
0x18000e83b  jnz     loc_18000E96B
0x18000e841  mov     [rbx+20h], rcx
0x18000e845  sub     rcx, r8
0x18000e848  sar     rcx, 1
0x18000e84b  lea     r8, [rbx+8]
0x18000e84f  sub     r15w, cx
0x18000e853  mov     rcx, r9; String2
0x18000e856  add     r15w, r15w
0x18000e85a  mov     [rdx], r15w
0x18000e85e  add     r15w, r10w
0x18000e862  mov     [rbx+1Ah], r15w
0x18000e867  call    BaseDllFindIniFileNameMapping
0x18000e86c  jmp     loc_18000E5CE
0x18000e871  mov     eax, 0C0000017h
0x18000e876  jmp     loc_18000E688
0x18000e87b  cmp     [rsi], bx
0x18000e87e  jnz     loc_18000E941
0x18000e884  sub     rcx, rsi
0x18000e887  sar     rcx, 1
0x18000e88a  mov     r13d, ecx
0x18000e88d  jmp     loc_18000E4DC
0x18000e892  call    cs:__imp_strlen
0x18000e899  nop     dword ptr [rax+rax+00h]
0x18000e89e  jmp     loc_18000E777
0x18000e8a3  call    cs:__imp_GetFullPathNameA
0x18000e8aa  nop     dword ptr [rax+rax+00h]
0x18000e8af  jmp     loc_18000E79F
0x18000e8b4  mov     r9d, [rbp+arg_0]
0x18000e8b8  mov     r10d, 1
0x18000e8be  movzx   eax, r9w
0x18000e8c2  lea     ecx, [rax+rax]
0x18000e8c5  lea     eax, [r10+rcx]
0x18000e8c9  mov     [rbx+4Ah], ax
0x18000e8cd  add     ax, ax
0x18000e8d0  mov     [rbx+6Ah], ax
0x18000e8d4  test    r14b, r14b
0x18000e8d7  jz      loc_18000EA24
0x18000e8dd  mov     [rbx+50h], rdi
0x18000e8e1  mov     eax, r12d
0x18000e8e4  lea     rdi, [rdi+r9*2]
0x18000e8e8  mov     [rbx+70h], rdx
0x18000e8ec  inc     rdi
0x18000e8ef  mov     [rbx+48h], ax
0x18000e8f3  mov     [rbx+68h], cx
0x18000e8f7  jmp     loc_18000E603
0x18000e8fc  mov     r9d, dword ptr [rbp+String]
0x18000e900  movzx   eax, r9w
0x18000e904  lea     ecx, [rax+rax]
0x18000e907  lea     eax, [r10+rcx]
0x18000e90b  mov     [rbx+5Ah], ax
0x18000e90f  add     ax, ax
0x18000e912  mov     [rbx+7Ah], ax
0x18000e916  test    r14b, r14b
0x18000e919  jz      loc_18000EA40
0x18000e91f  mov     [rbx+60h], rdi
0x18000e923  mov     eax, r12d
0x18000e926  lea     rdi, [rdi+r9*2]
0x18000e92a  mov     [rbx+80h], rdx
0x18000e931  inc     rdi
0x18000e934  mov     [rbx+58h], ax
0x18000e938  mov     [rbx+78h], cx
0x18000e93c  jmp     loc_18000E632
0x18000e941  movzx   eax, word ptr [rcx]
0x18000e944  add     rcx, 2
0x18000e948  test    ax, ax
0x18000e94b  jnz     short loc_18000E941
0x18000e94d  cmp     [rcx], bx
0x18000e950  jz      loc_18000E884
0x18000e956  jmp     short loc_18000E941
  ... truncated ...
```
