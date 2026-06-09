# DsRolepCreateSysVolLinks

- ea: `0x18000cae0`
- end: `0x18000cdf4`
- name: `DsRolepCreateSysVolLinks`
- size: `788`
- prototype: `__int64 __fastcall(__int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000cdfc`

## callees

- `0x180008fd4`
- `0x18000c870`
- `0x18000cae0`
- `0x18000e4d0`
- `0x180020dbc`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000ccad`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000cd48`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000ccad`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000cd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd52`
- `ntdll!RtlAllocateHeap` at `0x18000cb77`
- `ntdll!RtlAllocateHeap` at `0x18000cc0d`
- `ntdll!RtlAllocateHeap` at `0x18000cb77`
- `ntdll!RtlAllocateHeap` at `0x18000cc0d`
- `ntdll!RtlFreeHeap` at `0x18000cd9c`
- `ntdll!RtlFreeHeap` at `0x18000cdc1`
- `ntdll!RtlFreeHeap` at `0x18000cd9c`
- `ntdll!RtlFreeHeap` at `0x18000cdc1`

## string_xrefs

- `0x18000ccc0`: `Failed to create the link directory %ws: %lu\n`
- `0x18000cd5b`: `Failed to create the link directory %ws: %lu\n`

## pseudocode

```c
__int64 __fastcall DsRolepCreateSysVolLinks(__int64 a1, const wchar_t *a2)
{
  __int64 v2; // rbx
  __int64 v3; // r8
  wchar_t *v4; // rdi
  __int64 v7; // rax
  unsigned __int64 v8; // r15
  wchar_t *Heap; // rsi
  __int64 LastError; // rbx
  size_t v11; // r15
  const wchar_t *v12; // r8
  __int64 v13; // r12
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int64 v16; // rbp
  size_t v17; // rbp
  const wchar_t *v18; // r8
  __int64 v19; // rax
  wchar_t *v20; // r12
  size_t v21; // r15
  wchar_t *v22; // r14
  size_t v23; // rbp
  wchar_t *i; // rbx
  _BYTE v27[544]; // [rsp+40h] [rbp-488h] BYREF
  _BYTE P[544]; // [rsp+260h] [rbp-268h] BYREF

  v2 = -1;
  v3 = -1;
  v4 = (wchar_t *)P;
  do
    ++v3;
  while ( *(_WORD *)(a1 + 2 * v3) );
  if ( *(_WORD *)(a1 + 2 * v3 - 2) == 92 )
  {
    --v3;
    *(_WORD *)(a1 + 2 * v3) = 0;
  }
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = (unsigned int)(2 * (v3 + v7) + 31);
  if ( v8 <= 0x84 )
  {
    Heap = (wchar_t *)v27;
    v11 = 265;
    v12 = L"%ws\\";
  }
  else
  {
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v8);
    if ( !Heap )
    {
LABEL_9:
      LODWORD(LastError) = 8;
      goto LABEL_34;
    }
    v11 = v8 >> 1;
    v12 = L"\\\\?\\%ws\\";
  }
  StringCchPrintfW(Heap, v11, v12, a1);
  v13 = -1;
  do
    ++v13;
  while ( Heap[v13] );
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(a1 + 2 * v14) );
  v15 = -1;
  do
    ++v15;
  while ( a2[v15] );
  v16 = (unsigned int)(2 * (v14 + v15) + 54);
  if ( v16 <= 0x84 )
  {
    v17 = 265;
    v18 = L"%ws\\%ws\\";
  }
  else
  {
    v4 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v16);
    if ( !v4 )
      goto LABEL_9;
    v17 = v16 >> 1;
    v18 = L"\\\\?\\%ws\\%ws\\";
  }
  v19 = 2 * v13;
  v20 = &Heap[v13];
  v21 = v11 - (unsigned int)(v19 >> 1);
  StringCchPrintfW(v4, v17, v18, a1, L"sysvol");
  do
    ++v2;
  while ( v4[v2] );
  v22 = &v4[v2];
  v23 = v17 - (unsigned int)((2 * v2) >> 1);
  StringCchCopyW(v20, v21, L"domain");
  StringCchCopyW(v22, v23, a2);
  if ( CreateDirectoryW(v4, 0) )
  {
    LODWORD(LastError) = DsRolepCreateSymLink(v4, Heap);
  }
  else
  {
    LastError = GetLastError();
    DsRolepLogPrintRoutine(1, "Failed to create the link directory %ws: %lu\n", v4, LastError);
  }
  if ( !(_DWORD)LastError )
  {
    for ( i = v22 - 1; *(i - 1) != 92; --i )
      ;
    StringCchPrintfW(v20, v21, L"%ws\\%ws", L"staging", L"domain");
    StringCchPrintfW(i, v23, L"%ws\\%ws", L"staging areas", a2);
    if ( CreateDirectoryW(v4, 0) )
    {
      LODWORD(LastError) = DsRolepCreateSymLink(v4, Heap);
    }
    else
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(1, "Failed to create the link directory %ws: %lu\n", v4, LastError);
    }
  }
LABEL_34:
  if ( Heap != (wchar_t *)v27 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v4 != (wchar_t *)P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000cae0  mov     [rsp+arg_10], rbx
0x18000cae5  push    rbp
0x18000cae6  push    rsi
0x18000cae7  push    rdi
0x18000cae8  push    r12
0x18000caea  push    r13
0x18000caec  push    r14
0x18000caee  push    r15
0x18000caf0  sub     rsp, 490h
0x18000caf7  mov     rax, cs:__security_cookie
0x18000cafe  xor     rax, rsp
0x18000cb01  mov     [rsp+4C8h+var_48], rax
0x18000cb09  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000cb0d  mov     [rsp+4C8h+pszSrc], rdx
0x18000cb12  mov     r8, rbx
0x18000cb15  lea     rdi, [rsp+4C8h+P]
0x18000cb1d  xor     r12d, r12d
0x18000cb20  mov     rbp, rdx
0x18000cb23  mov     r14, rcx
0x18000cb26  inc     r8
0x18000cb29  cmp     [rcx+r8*2], r12w
0x18000cb2e  jnz     short loc_18000CB26
0x18000cb30  cmp     word ptr [rcx+r8*2-2], 5Ch ; '\'
0x18000cb37  jnz     short loc_18000CB41
0x18000cb39  dec     r8
0x18000cb3c  mov     [rcx+r8*2], r12w
0x18000cb41  mov     rax, rbx
0x18000cb44  inc     rax
0x18000cb47  cmp     [rdx+rax*2], r12w
0x18000cb4c  jnz     short loc_18000CB44
0x18000cb4e  add     rax, r8
0x18000cb51  lea     r15, ds:1Fh[rax*2]
0x18000cb59  mov     r15d, r15d
0x18000cb5c  cmp     r15, 84h
0x18000cb63  jbe     short loc_18000CB9B
0x18000cb65  mov     rcx, gs:60h
0x18000cb6e  mov     r8d, r15d; Size
0x18000cb71  xor     edx, edx; Flags
0x18000cb73  mov     rcx, [rcx+30h]; HeapHandle
0x18000cb77  call    cs:__imp_RtlAllocateHeap
0x18000cb7d  mov     rsi, rax
0x18000cb80  test    rax, rax
0x18000cb83  jnz     short loc_18000CB8F
0x18000cb85  mov     ebx, 8
0x18000cb8a  jmp     loc_18000CD80
0x18000cb8f  shr     r15, 1
0x18000cb92  lea     r8, aWs_2; "\\\\?\\%ws\\"
0x18000cb99  jmp     short loc_18000CBAD
0x18000cb9b  lea     rsi, [rsp+4C8h+var_488]
0x18000cba0  mov     r15d, 109h
0x18000cba6  lea     r8, aWs_3; "%ws\\"
0x18000cbad  mov     r9, r14
0x18000cbb0  mov     rdx, r15; cchDest
0x18000cbb3  mov     rcx, rsi; pszDest
0x18000cbb6  mov     r13, r14
0x18000cbb9  call    StringCchPrintfW
0x18000cbbe  xor     edx, edx; Flags
0x18000cbc0  mov     r12, rbx
0x18000cbc3  inc     r12
0x18000cbc6  cmp     [rsi+r12*2], dx
0x18000cbcb  jnz     short loc_18000CBC3
0x18000cbcd  mov     rcx, rbx
0x18000cbd0  inc     rcx
0x18000cbd3  cmp     [r14+rcx*2], dx
0x18000cbd8  jnz     short loc_18000CBD0
0x18000cbda  mov     rax, rbx
0x18000cbdd  inc     rax
0x18000cbe0  cmp     [rbp+rax*2+0], dx
0x18000cbe5  jnz     short loc_18000CBDD
0x18000cbe7  add     rax, rcx
0x18000cbea  lea     rbp, ds:36h[rax*2]
0x18000cbf2  mov     ebp, ebp
0x18000cbf4  cmp     rbp, 84h
0x18000cbfb  jbe     short loc_18000CC2B
0x18000cbfd  mov     rcx, gs:60h
0x18000cc06  mov     r8d, ebp; Size
0x18000cc09  mov     rcx, [rcx+30h]; HeapHandle
0x18000cc0d  call    cs:__imp_RtlAllocateHeap
0x18000cc13  mov     rdi, rax
0x18000cc16  test    rax, rax
0x18000cc19  jz      loc_18000CB85
0x18000cc1f  shr     rbp, 1
0x18000cc22  lea     r8, aWsWs_0; "\\\\?\\%ws\\%ws\\"
0x18000cc29  jmp     short loc_18000CC37
0x18000cc2b  mov     ebp, 109h
0x18000cc30  lea     r8, aWsWs_2; "%ws\\%ws\\"
0x18000cc37  lea     rax, [r12+r12]
0x18000cc3b  mov     r9, r13
0x18000cc3e  lea     r12, [rax+rsi]
0x18000cc42  mov     rdx, rbp; cchDest
0x18000cc45  sar     rax, 1
0x18000cc48  lea     rcx, aSysvol; "sysvol"
0x18000cc4f  mov     eax, eax
0x18000cc51  mov     [rsp+4C8h+var_4A8], rcx
0x18000cc56  sub     r15, rax
0x18000cc59  mov     rcx, rdi; pszDest
0x18000cc5c  mov     [rsp+4C8h+pszDest], r12
0x18000cc61  call    StringCchPrintfW
0x18000cc66  xor     r13d, r13d
0x18000cc69  inc     rbx
0x18000cc6c  cmp     [rdi+rbx*2], r13w
0x18000cc71  jnz     short loc_18000CC69
0x18000cc73  lea     rax, [rbx+rbx]
0x18000cc77  mov     rdx, r15; cchDest
0x18000cc7a  lea     r14, [rax+rdi]
0x18000cc7e  mov     rcx, r12; pszDest
0x18000cc81  sar     rax, 1
0x18000cc84  lea     r8, aDomain; "domain"
0x18000cc8b  mov     eax, eax
0x18000cc8d  sub     rbp, rax
0x18000cc90  call    StringCchCopyW
0x18000cc95  mov     r12, [rsp+4C8h+pszSrc]
0x18000cc9a  mov     rdx, rbp; cchDest
0x18000cc9d  mov     r8, r12; pszSrc
0x18000cca0  mov     rcx, r14; pszDest
0x18000cca3  call    StringCchCopyW
0x18000cca8  xor     edx, edx; lpSecurityAttributes
0x18000ccaa  mov     rcx, rdi; lpPathName
0x18000ccad  call    cs:__imp_CreateDirectoryW
0x18000ccb3  test    eax, eax
0x18000ccb5  jnz     short loc_18000CCD8
0x18000ccb7  call    cs:__imp_GetLastError
0x18000ccbd  mov     r8, rdi
0x18000ccc0  lea     rdx, aFailedToCreate_7; "Failed to create the link directory %ws"...
0x18000ccc7  mov     r9d, eax
0x18000ccca  mov     ecx, 1
0x18000cccf  mov     ebx, eax
0x18000ccd1  call    DsRolepLogPrintRoutine
0x18000ccd6  jmp     short loc_18000CCE5
0x18000ccd8  mov     rdx, rsi
0x18000ccdb  mov     rcx, rdi
0x18000ccde  call    DsRolepCreateSymLink
0x18000cce3  mov     ebx, eax
0x18000cce5  test    ebx, ebx
0x18000cce7  jnz     loc_18000CD80
0x18000cced  lea     rbx, [r14-2]
0x18000ccf1  jmp     short loc_18000CCF7
0x18000ccf3  sub     rbx, 2
0x18000ccf7  cmp     word ptr [rbx-2], 5Ch ; '\'
0x18000ccfc  jnz     short loc_18000CCF3
0x18000ccfe  mov     rcx, [rsp+4C8h+pszDest]; pszDest
0x18000cd03  lea     rax, aDomain; "domain"
0x18000cd0a  lea     r9, aStaging; "staging"
0x18000cd11  mov     [rsp+4C8h+var_4A8], rax
0x18000cd16  lea     r8, aWsWs_3; "%ws\\%ws"
0x18000cd1d  mov     rdx, r15; cchDest
0x18000cd20  call    StringCchPrintfW
0x18000cd25  lea     r9, aStagingAreas; "staging areas"
0x18000cd2c  mov     [rsp+4C8h+var_4A8], r12
0x18000cd31  lea     r8, aWsWs_3; "%ws\\%ws"
0x18000cd38  mov     rdx, rbp; cchDest
0x18000cd3b  mov     rcx, rbx; pszDest
0x18000cd3e  call    StringCchPrintfW
0x18000cd43  xor     edx, edx; lpSecurityAttributes
0x18000cd45  mov     rcx, rdi; lpPathName
0x18000cd48  call    cs:__imp_CreateDirectoryW
0x18000cd4e  test    eax, eax
0x18000cd50  jnz     short loc_18000CD73
0x18000cd52  call    cs:__imp_GetLastError
0x18000cd58  mov     r8, rdi
0x18000cd5b  lea     rdx, aFailedToCreate_7; "Failed to create the link directory %ws"...
0x18000cd62  mov     r9d, eax
0x18000cd65  mov     ecx, 1
0x18000cd6a  mov     ebx, eax
0x18000cd6c  call    DsRolepLogPrintRoutine
0x18000cd71  jmp     short loc_18000CD80
0x18000cd73  mov     rdx, rsi
0x18000cd76  mov     rcx, rdi
0x18000cd79  call    DsRolepCreateSymLink
0x18000cd7e  mov     ebx, eax
0x18000cd80  lea     rax, [rsp+4C8h+var_488]
0x18000cd85  cmp     rsi, rax
0x18000cd88  jz      short loc_18000CDA2
0x18000cd8a  mov     rcx, gs:60h
0x18000cd93  mov     r8, rsi; P
0x18000cd96  xor     edx, edx; Flags
0x18000cd98  mov     rcx, [rcx+30h]; HeapHandle
0x18000cd9c  call    cs:__imp_RtlFreeHeap
0x18000cda2  lea     rax, [rsp+4C8h+P]
0x18000cdaa  cmp     rdi, rax
0x18000cdad  jz      short loc_18000CDC7
0x18000cdaf  mov     rcx, gs:60h
0x18000cdb8  mov     r8, rdi; P
0x18000cdbb  xor     edx, edx; Flags
0x18000cdbd  mov     rcx, [rcx+30h]; HeapHandle
0x18000cdc1  call    cs:__imp_RtlFreeHeap
0x18000cdc7  mov     eax, ebx
0x18000cdc9  mov     rcx, [rsp+4C8h+var_48]
0x18000cdd1  xor     rcx, rsp; StackCookie
0x18000cdd4  call    __security_check_cookie
0x18000cdd9  mov     rbx, [rsp+4C8h+arg_10]
0x18000cde1  add     rsp, 490h
0x18000cde8  pop     r15
0x18000cdea  pop     r14
0x18000cdec  pop     r13
0x18000cdee  pop     r12
0x18000cdf0  pop     rdi
0x18000cdf1  pop     rsi
0x18000cdf2  pop     rbp
0x18000cdf3  retn
```
