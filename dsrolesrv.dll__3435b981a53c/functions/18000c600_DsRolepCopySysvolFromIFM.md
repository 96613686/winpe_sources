# DsRolepCopySysvolFromIFM

- ea: `0x18000c600`
- end: `0x18000c86a`
- name: `DsRolepCopySysvolFromIFM`
- size: `618`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012460`

## callees

- `0x18000bf74`
- `0x18000c600`
- `0x18000de20`
- `0x18000e4d0`
- `0x180020dbc`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000c66a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000c66a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c805`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c67c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c67c`
- `ntdll!RtlAllocateHeap` at `0x18000c713`
- `ntdll!RtlAllocateHeap` at `0x18000c77e`
- `ntdll!RtlAllocateHeap` at `0x18000c713`
- `ntdll!RtlAllocateHeap` at `0x18000c77e`
- `ntdll!RtlFreeHeap` at `0x18000c822`
- `ntdll!RtlFreeHeap` at `0x18000c83f`
- `ntdll!RtlFreeHeap` at `0x18000c822`
- `ntdll!RtlFreeHeap` at `0x18000c83f`

## string_xrefs

- `0x18000c6b1`: `SeBackupPrivilege`
- `0x18000c7d4`: `SeBackupPrivilege`
- `0x18000c6c2`: `SeSecurityPrivilege`
- `0x18000c7e2`: `SeSecurityPrivilege`
- `0x18000c6d3`: `SeRestorePrivilege`
- `0x18000c7f0`: `SeRestorePrivilege`
- `0x18000c7c1`: `DsRolepTreeCopy failed with %lu\n`

## pseudocode

```c
__int64 __fastcall DsRolepCopySysvolFromIFM(LPCWSTR lpFileName, __int64 a2, __int64 a3)
{
  wchar_t *v6; // rdi
  wchar_t *v7; // rbp
  HANDLE FirstFileW; // r12
  DWORD LastError; // eax
  unsigned int v10; // ebx
  __int64 v12; // rcx
  __int64 v13; // rax
  size_t v14; // rbx
  wchar_t *Heap; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  size_t v18; // rbx
  wchar_t *v19; // rax
  unsigned int v20; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-2B8h] BYREF
  wchar_t pszFormat[16]; // [rsp+280h] [rbp-68h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v6 = 0;
  v7 = 0;
  wcscpy(pszFormat, L"%ws\\syvol\\%ws");
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError == 2 )
      return 0;
    DsRolepLogPrintRoutine(1, "FindFirstFile on %ws failed with %lu\n", lpFileName, LastError);
  }
  else
  {
    DsRolepAssertPrivilege(L"SeBackupPrivilege");
    DsRolepAssertPrivilege(L"SeSecurityPrivilege");
    DsRolepAssertPrivilege(L"SeRestorePrivilege");
    v12 = -1;
    do
      ++v12;
    while ( lpFileName[v12] );
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(a3 + 2 * v13) );
    v14 = v13 + v12 + 2;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v14);
    v6 = Heap;
    if ( !Heap )
      goto LABEL_10;
    StringCchPrintfW(Heap, v14, L"%ws\\%ws", lpFileName, a3);
    v16 = -1;
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)(a2 + 2 * v17) );
    do
      ++v16;
    while ( *(_WORD *)(a3 + 2 * v16) );
    v18 = v16 + v17 + 15;
    v19 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v18);
    v7 = v19;
    if ( v19 )
    {
      StringCchPrintfW(v19, v18, pszFormat, a2, a3);
      v20 = DsRolepTreeCopy((__int64)v6, (__int64)v7, 1u);
      v10 = v20;
      if ( v20 )
        DsRolepLogPrintRoutine(1, "DsRolepTreeCopy failed with %lu\n", v20);
    }
    else
    {
LABEL_10:
      v10 = 8;
    }
  }
  DsRolepAssertPrivilege(L"SeBackupPrivilege");
  DsRolepAssertPrivilege(L"SeSecurityPrivilege");
  DsRolepAssertPrivilege(L"SeRestorePrivilege");
  if ( FirstFileW != (HANDLE)-1LL )
    FindClose(FirstFileW);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  return v10;
}

```

## disassembly

```asm
0x18000c600  push    rbx
0x18000c602  push    rbp
0x18000c603  push    rdi
0x18000c604  push    r12
0x18000c606  push    r13
0x18000c608  push    r14
0x18000c60a  push    r15
0x18000c60c  sub     rsp, 2B0h
0x18000c613  mov     rax, cs:__security_cookie
0x18000c61a  xor     rax, rsp
0x18000c61d  mov     [rsp+2E8h+var_48], rax
0x18000c625  mov     r15, r8
0x18000c628  mov     r13, rdx
0x18000c62b  mov     r14, rcx
0x18000c62e  xor     edx, edx; Val
0x18000c630  mov     r8d, 250h; Size
0x18000c636  lea     rcx, [rsp+2E8h+FindFileData]; void *
0x18000c63b  call    memset_0
0x18000c640  movups  xmm0, xmmword ptr cs:aWsSysvolWs; "%ws\\sysvol\\%ws"
0x18000c647  xor     edi, edi
0x18000c649  lea     rdx, [rsp+2E8h+FindFileData]; lpFindFileData
0x18000c64e  movups  xmm1, xmmword ptr cs:aWsSysvolWs+0Eh; "vol\\%ws"
0x18000c655  mov     rcx, r14; lpFileName
0x18000c658  mov     ebp, edi
0x18000c65a  movups  xmmword ptr [rsp+2E8h+pszFormat], xmm0
0x18000c662  movups  xmmword ptr [rsp+2E8h+pszFormat+0Eh], xmm1
0x18000c66a  call    cs:__imp_FindFirstFileW
0x18000c670  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c674  mov     r12, rax
0x18000c677  cmp     rax, rbx
0x18000c67a  jnz     short loc_18000C6AC
0x18000c67c  call    cs:__imp_GetLastError
0x18000c682  mov     ebx, eax
0x18000c684  cmp     eax, 2
0x18000c687  jnz     short loc_18000C690
0x18000c689  xor     eax, eax
0x18000c68b  jmp     loc_18000C847
0x18000c690  mov     r9d, eax
0x18000c693  lea     rdx, aFindfirstfileO; "FindFirstFile on %ws failed with %lu\n"
0x18000c69a  mov     r8, r14
0x18000c69d  mov     ecx, 1
0x18000c6a2  call    DsRolepLogPrintRoutine
0x18000c6a7  jmp     loc_18000C7D2
0x18000c6ac  mov     edx, 1
0x18000c6b1  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18000c6b8  call    DsRolepAssertPrivilege
0x18000c6bd  mov     edx, 1
0x18000c6c2  lea     rcx, aSesecuritypriv; "SeSecurityPrivilege"
0x18000c6c9  call    DsRolepAssertPrivilege
0x18000c6ce  mov     edx, 1
0x18000c6d3  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18000c6da  call    DsRolepAssertPrivilege
0x18000c6df  mov     rcx, rbx
0x18000c6e2  inc     rcx
0x18000c6e5  cmp     [r14+rcx*2], di
0x18000c6ea  jnz     short loc_18000C6E2
0x18000c6ec  mov     rax, rbx
0x18000c6ef  inc     rax
0x18000c6f2  cmp     [r15+rax*2], di
0x18000c6f7  jnz     short loc_18000C6EF
0x18000c6f9  lea     rbx, [rcx+2]
0x18000c6fd  xor     edx, edx; Flags
0x18000c6ff  mov     rcx, gs:60h
0x18000c708  add     rbx, rax
0x18000c70b  mov     rcx, [rcx+30h]; HeapHandle
0x18000c70f  lea     r8, [rbx+rbx]; Size
0x18000c713  call    cs:__imp_RtlAllocateHeap
0x18000c719  mov     rdi, rax
0x18000c71c  test    rax, rax
0x18000c71f  jnz     short loc_18000C72B
0x18000c721  mov     ebx, 8
0x18000c726  jmp     loc_18000C7D2
0x18000c72b  mov     r9, r14
0x18000c72e  mov     [rsp+2E8h+var_2C8], r15
0x18000c733  lea     r8, aWsWs_3; "%ws\\%ws"
0x18000c73a  mov     rdx, rbx; cchDest
0x18000c73d  mov     rcx, rdi; pszDest
0x18000c740  call    StringCchPrintfW
0x18000c745  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c749  mov     rcx, rax
0x18000c74c  xor     r14d, r14d
0x18000c74f  inc     rcx
0x18000c752  cmp     [r13+rcx*2+0], r14w
0x18000c758  jnz     short loc_18000C74F
0x18000c75a  inc     rax
0x18000c75d  cmp     [r15+rax*2], r14w
0x18000c762  jnz     short loc_18000C75A
0x18000c764  lea     rbx, [rcx+0Fh]
0x18000c768  xor     edx, edx; Flags
0x18000c76a  mov     rcx, gs:60h
0x18000c773  add     rbx, rax
0x18000c776  mov     rcx, [rcx+30h]; HeapHandle
0x18000c77a  lea     r8, [rbx+rbx]; Size
0x18000c77e  call    cs:__imp_RtlAllocateHeap
0x18000c784  mov     rbp, rax
0x18000c787  test    rax, rax
0x18000c78a  jz      short loc_18000C721
0x18000c78c  mov     r9, r13
0x18000c78f  mov     [rsp+2E8h+var_2C8], r15
0x18000c794  lea     r8, [rsp+2E8h+pszFormat]; pszFormat
0x18000c79c  mov     rdx, rbx; cchDest
0x18000c79f  mov     rcx, rax; pszDest
0x18000c7a2  call    StringCchPrintfW
0x18000c7a7  mov     r8d, 1
0x18000c7ad  mov     rdx, rbp
0x18000c7b0  mov     rcx, rdi
0x18000c7b3  call    DsRolepTreeCopy
0x18000c7b8  mov     ebx, eax
0x18000c7ba  test    eax, eax
0x18000c7bc  jz      short loc_18000C7D2
0x18000c7be  mov     r8d, eax
0x18000c7c1  lea     rdx, aDsroleptreecop; "DsRolepTreeCopy failed with %lu\n"
0x18000c7c8  mov     ecx, 1
0x18000c7cd  call    DsRolepLogPrintRoutine
0x18000c7d2  xor     edx, edx
0x18000c7d4  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18000c7db  call    DsRolepAssertPrivilege
0x18000c7e0  xor     edx, edx
0x18000c7e2  lea     rcx, aSesecuritypriv; "SeSecurityPrivilege"
0x18000c7e9  call    DsRolepAssertPrivilege
0x18000c7ee  xor     edx, edx
0x18000c7f0  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18000c7f7  call    DsRolepAssertPrivilege
0x18000c7fc  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18000c800  jz      short loc_18000C80B
0x18000c802  mov     rcx, r12; hFindFile
0x18000c805  call    cs:__imp_FindClose
0x18000c80b  test    rdi, rdi
0x18000c80e  jz      short loc_18000C828
0x18000c810  mov     rcx, gs:60h
0x18000c819  mov     r8, rdi; P
0x18000c81c  xor     edx, edx; Flags
0x18000c81e  mov     rcx, [rcx+30h]; HeapHandle
0x18000c822  call    cs:__imp_RtlFreeHeap
0x18000c828  test    rbp, rbp
0x18000c82b  jz      short loc_18000C845
0x18000c82d  mov     rcx, gs:60h
0x18000c836  mov     r8, rbp; P
0x18000c839  xor     edx, edx; Flags
0x18000c83b  mov     rcx, [rcx+30h]; HeapHandle
0x18000c83f  call    cs:__imp_RtlFreeHeap
0x18000c845  mov     eax, ebx
0x18000c847  mov     rcx, [rsp+2E8h+var_48]
0x18000c84f  xor     rcx, rsp; StackCookie
0x18000c852  call    __security_check_cookie
0x18000c857  add     rsp, 2B0h
0x18000c85e  pop     r15
0x18000c860  pop     r14
0x18000c862  pop     r13
0x18000c864  pop     r12
0x18000c866  pop     rdi
0x18000c867  pop     rbp
0x18000c868  pop     rbx
0x18000c869  retn
```
