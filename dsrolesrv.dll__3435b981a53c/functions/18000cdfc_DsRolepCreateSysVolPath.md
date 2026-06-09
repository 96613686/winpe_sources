# DsRolepCreateSysVolPath

- ea: `0x18000cdfc`
- end: `0x18000d2fd`
- name: `DsRolepCreateSysVolPath`
- size: `1281`
- prototype: `__int64 __fastcall(wchar_t *pszSrc, const wchar_t *, _WORD *, __int64, __int64, size_t cchDest, unsigned __int8, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180011240`
- `0x180012460`

## callees

- `0x180008fd4`
- `0x18000c120`
- `0x18000cae0`
- `0x18000cdfc`
- `0x18000d304`
- `0x18000d698`
- `0x18000e4d0`
- `0x180016538`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000cf2b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000d094`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000cf2b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000d094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0a0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18000cf9e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18000cf9e`
- `ntdll!RtlAllocateHeap` at `0x18000ced3`
- `ntdll!RtlAllocateHeap` at `0x18000d12f`
- `ntdll!RtlAllocateHeap` at `0x18000ced3`
- `ntdll!RtlAllocateHeap` at `0x18000d12f`
- `ntdll!RtlFreeHeap` at `0x18000d2c4`
- `ntdll!RtlFreeHeap` at `0x18000d2e1`
- `ntdll!RtlFreeHeap` at `0x18000d2c4`
- `ntdll!RtlFreeHeap` at `0x18000d2e1`
- `DFSRAPI!DfsrPrepareForPromotionW` at `0x18000d194`
- `DFSRAPI!DfsrPrepareForPromotionW` at `0x18000d194`
- `DFSRAPI!DfsrStartPromotionW` at `0x18000d237`
- `DFSRAPI!DfsrStartPromotionW` at `0x18000d237`

## string_xrefs

- `0x18000cf69`: `Deleting current sysvol path %ws \n`
- `0x18000cfc9`: `Failed to create path %ws: %lu\n`
- `0x18000d0c7`: `Failed to create path %ws: %lu\n`
- `0x18000d29e`: `Failed to delete path %ws: %lu\n`

## pseudocode

```c
__int64 __fastcall DsRolepCreateSysVolPath(
        wchar_t *pszSrc,
        const wchar_t *a2,
        _WORD *a3,
        __int64 a4,
        __int64 a5,
        size_t cchDest,
        unsigned __int8 a7,
        int a8)
{
  __int64 v8; // r14
  wchar_t *v9; // rsi
  wchar_t *v10; // rbx
  _WORD *v11; // r12
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  SIZE_T v15; // r15
  wchar_t *Heap; // rax
  WCHAR *v17; // rdi
  unsigned int LastError; // ebx
  size_t v19; // rbp
  size_t v20; // rdx
  __int64 v21; // r15
  unsigned int v22; // eax
  int v23; // r13d
  wchar_t *v24; // r9
  size_t v25; // rcx
  unsigned __int64 v26; // r15
  DWORD v27; // eax
  __int64 v28; // r8
  wchar_t *v29; // rax
  __int64 v30; // rax
  wchar_t *v31; // r14
  size_t v32; // rbp
  unsigned int v33; // eax
  unsigned int started; // eax
  __int64 v35; // rdx
  unsigned int v36; // eax
  __int64 v38; // [rsp+28h] [rbp-C0h]
  SIZE_T Size; // [rsp+60h] [rbp-88h]
  STRSAFE_LPCWSTR pszSrca[16]; // [rsp+68h] [rbp-80h]
  wchar_t *pszDest; // [rsp+100h] [rbp+18h]
  size_t cchDesta; // [rsp+118h] [rbp+30h]
  char v47; // [rsp+130h] [rbp+48h]

  v8 = -1;
  pszSrca[0] = L"domain";
  v9 = 0;
  v10 = pszSrc;
  pszSrca[1] = L"domain\\scripts";
  pszSrca[2] = L"staging areas";
  pszSrca[3] = L"staging";
  pszSrca[4] = L"staging\\domain";
  pszSrca[5] = L"sysvol";
  v11 = a3;
  if ( a3 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    if ( v12 > 2 && *a3 == 92 && a3[1] == 92 )
      v11 = a3 + 2;
  }
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  v14 = -1;
  do
    ++v14;
  while ( v10[v14] );
  v15 = 2 * (v13 + v14) + 44;
  Size = v15;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  v17 = Heap;
  if ( !Heap )
  {
    LastError = 8;
    goto LABEL_33;
  }
  v19 = v15 >> 1;
  v20 = v15 >> 1;
  if ( v15 <= 0x208 )
    StringCchCopyW(Heap, v20, v10);
  else
    StringCchPrintfW(Heap, v20, L"\\\\?\\%ws", v10);
  v21 = -1;
  do
    ++v21;
  while ( v17[v21] );
  if ( !CreateDirectoryW(v17, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 183 )
    {
      v47 = 0;
      if ( (a8 & 0x800000) != 0 )
      {
LABEL_30:
        v10 = pszSrc;
        goto LABEL_31;
      }
      DsRolepLogPrintRoutine(4, "Deleting current sysvol path %ws \n", v17);
      v22 = DsRolepDelnodePath(v17, Size, 0);
      LastError = 0;
      if ( v22 != 87 )
        LastError = v22;
    }
    else
    {
      if ( LastError == 5 && PathIsRootW(v17) )
      {
        DsRolepSetFailureMessage(5, 3221254708LL, 0, 0, 0);
        goto LABEL_60;
      }
      DsRolepLogPrintRoutine(4, "Failed to create path %ws: %lu\n", v17, LastError);
    }
    v47 = 0;
    if ( LastError )
      goto LABEL_33;
    goto LABEL_30;
  }
  v47 = 1;
LABEL_31:
  v23 = a8 & 0x800000;
  if ( (a8 & 0x800000) != 0 )
  {
    LastError = DsRolepCleanupDFSRDBFolder(v10);
    if ( LastError )
    {
LABEL_33:
      DsRolepSetFailureMessage(LastError, 1073771056, 0, 0, 0);
      if ( !v17 )
        return LastError;
      goto LABEL_60;
    }
  }
  v17[v21] = 92;
  v24 = &v17[v21 + 1];
  pszDest = v24;
  v25 = v19 - ((2 * v21) >> 1) - 1;
  v26 = 0;
  cchDesta = v25;
  while ( v26 < 6 )
  {
    if ( v26 != 1 || a7 )
    {
      StringCchCopyW(v24, v25, pszSrca[v26]);
      if ( !CreateDirectoryW(v17, 0) )
      {
        v27 = GetLastError();
        LastError = v27;
        if ( !v23 )
        {
          DsRolepLogPrintRoutine(4, "Failed to create path %ws: %lu\n", v17, v27);
          if ( LastError )
            goto LABEL_58;
          v24 = pszDest;
          break;
        }
      }
      v24 = pszDest;
      v25 = cchDesta;
    }
    ++v26;
  }
  *v24 = 0;
  if ( v23 || (LastError = DsRolepCreateSysVolLinks((__int64)pszSrc, a2)) == 0 )
  {
    v29 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Size);
    v9 = v29;
    if ( v29 )
    {
      StringCchPrintfW(v29, v19, L"\\\\?\\%ws", pszSrc);
      do
        ++v8;
      while ( v9[v8] );
      v30 = 2 * v8;
      v31 = &v9[v8];
      v32 = v19 - (v30 >> 1);
      if ( *v31 != 92 )
      {
        *v31++ = 92;
        --v32;
      }
      v33 = DfsrPrepareForPromotionW(DsRolepDfsrStringErrorUpdateCallback);
      LastError = v33;
      if ( v33 )
      {
        DsRolepLogPrintRoutine(1, "DfsrPrepareForPromotionW failed with %lu\n", v33);
      }
      else
      {
        StringCchPrintfW(v31, v32, L"%ws\\%ws", L"staging areas", a2);
        StringCchPrintfW(pszDest, cchDesta, L"%ws\\%ws", L"sysvol", a2);
        started = DfsrStartPromotionW(
                    0,
                    v11,
                    a4,
                    a5,
                    DsRolepDfsrStringUpdateCallbackNoFlags,
                    DsRolepDfsrStringErrorUpdateCallback,
                    a2,
                    L"Domain",
                    a7,
                    v9,
                    v17);
        LastError = started;
        if ( !started )
          goto LABEL_60;
        LODWORD(v38) = started;
        DsRolepLogPrintRoutine(1, "DfsrStartPromotionW on %ws / %ws / %ws failed with %lu\n", a2, v9, v17, v38);
        LOBYTE(v35) = 1;
        DsRolepFinishSysVolPropagation(0, v35);
      }
    }
    else
    {
      LastError = 8;
    }
  }
LABEL_58:
  LOBYTE(v28) = v47;
  v36 = DsRolepDelnodePath(v17, Size, v28);
  if ( v36 )
    DsRolepLogPrintRoutine(4, "Failed to delete path %ws: %lu\n", v17, v36);
LABEL_60:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
  if ( v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  return LastError;
}

```

## disassembly

```asm
0x18000cdfc  mov     r11, rsp
0x18000cdff  mov     [r11+20h], r9
0x18000ce03  mov     [r11+10h], rdx
0x18000ce07  mov     [r11+8], rcx
0x18000ce0b  push    rbx
0x18000ce0c  push    rbp
0x18000ce0d  push    rsi
0x18000ce0e  push    rdi
0x18000ce0f  push    r12
0x18000ce11  push    r13
0x18000ce13  push    r14
0x18000ce15  push    r15
0x18000ce17  sub     rsp, 0A8h
0x18000ce1e  lea     rax, aDomain; "domain"
0x18000ce25  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000ce29  mov     [r11-80h], rax
0x18000ce2d  xor     esi, esi
0x18000ce2f  lea     rax, aDomainScripts; "domain\\scripts"
0x18000ce36  mov     rbx, rcx
0x18000ce39  mov     [r11-78h], rax
0x18000ce3d  lea     rax, aStagingAreas; "staging areas"
0x18000ce44  mov     [r11-70h], rax
0x18000ce48  lea     rax, aStaging; "staging"
0x18000ce4f  mov     [r11-68h], rax
0x18000ce53  lea     rax, aStagingDomain; "staging\\domain"
0x18000ce5a  mov     [r11-60h], rax
0x18000ce5e  lea     rax, aSysvol; "sysvol"
0x18000ce65  mov     [r11-58h], rax
0x18000ce69  mov     r12, r8
0x18000ce6c  lea     ecx, [r14+5Dh]
0x18000ce70  test    r8, r8
0x18000ce73  jz      short loc_18000CE99
0x18000ce75  mov     rax, r14
0x18000ce78  inc     rax
0x18000ce7b  cmp     [r8+rax*2], si
0x18000ce80  jnz     short loc_18000CE78
0x18000ce82  cmp     rax, 2
0x18000ce86  jbe     short loc_18000CE99
0x18000ce88  cmp     [r8], cx
0x18000ce8c  jnz     short loc_18000CE99
0x18000ce8e  cmp     [r8+2], cx
0x18000ce93  jnz     short loc_18000CE99
0x18000ce95  add     r12, 4
0x18000ce99  mov     rcx, r14
0x18000ce9c  inc     rcx
0x18000ce9f  cmp     [rdx+rcx*2], si
0x18000cea3  jnz     short loc_18000CE9C
0x18000cea5  mov     rax, r14
0x18000cea8  inc     rax
0x18000ceab  cmp     [rbx+rax*2], si
0x18000ceaf  jnz     short loc_18000CEA8
0x18000ceb1  add     rax, rcx
0x18000ceb4  xor     edx, edx; Flags
0x18000ceb6  mov     rcx, gs:60h
0x18000cebf  lea     r15, ds:2Ch[rax*2]
0x18000cec7  mov     rcx, [rcx+30h]; HeapHandle
0x18000cecb  mov     r8, r15; Size
0x18000cece  mov     [rsp+0E8h+Size], r15
0x18000ced3  call    cs:__imp_RtlAllocateHeap
0x18000ced9  mov     rdi, rax
0x18000cedc  test    rax, rax
0x18000cedf  jnz     short loc_18000CEE9
0x18000cee1  lea     ebx, [rax+8]
0x18000cee4  jmp     loc_18000D00B
0x18000cee9  mov     rbp, r15
0x18000ceec  mov     rcx, rdi; pszDest
0x18000ceef  shr     rbp, 1
0x18000cef2  mov     rdx, rbp; cchDest
0x18000cef5  cmp     r15, 208h
0x18000cefc  jbe     short loc_18000CF0F
0x18000cefe  mov     r9, rbx
0x18000cf01  lea     r8, aWs_1; "\\\\?\\%ws"
0x18000cf08  call    StringCchPrintfW
0x18000cf0d  jmp     short loc_18000CF17
0x18000cf0f  mov     r8, rbx; pszSrc
0x18000cf12  call    StringCchCopyW
0x18000cf17  mov     r15, r14
0x18000cf1a  xor     ecx, ecx
0x18000cf1c  inc     r15
0x18000cf1f  cmp     [rdi+r15*2], cx
0x18000cf24  jnz     short loc_18000CF1C
0x18000cf26  xor     edx, edx; lpSecurityAttributes
0x18000cf28  mov     rcx, rdi; lpPathName
0x18000cf2b  call    cs:__imp_CreateDirectoryW
0x18000cf31  mov     r13d, [rsp+0E8h+arg_38]
0x18000cf39  xor     edx, edx
0x18000cf3b  test    eax, eax
0x18000cf3d  jnz     loc_18000D030
0x18000cf43  call    cs:__imp_GetLastError
0x18000cf49  mov     ebx, eax
0x18000cf4b  cmp     eax, 0B7h
0x18000cf50  jnz     short loc_18000CF96
0x18000cf52  xor     edx, edx
0x18000cf54  mov     [rsp+0E8h+arg_40], dl
0x18000cf5b  bt      r13d, 17h
0x18000cf60  jb      loc_18000CFEA
0x18000cf66  mov     r8, rdi
0x18000cf69  lea     rdx, aDeletingCurren; "Deleting current sysvol path %ws \n"
0x18000cf70  mov     ecx, 4
0x18000cf75  call    DsRolepLogPrintRoutine
0x18000cf7a  mov     rdx, [rsp+0E8h+Size]
0x18000cf7f  xor     r8d, r8d
0x18000cf82  mov     rcx, rdi
0x18000cf85  call    DsRolepDelnodePath
0x18000cf8a  xor     edx, edx
0x18000cf8c  cmp     eax, 57h ; 'W'
0x18000cf8f  mov     ebx, edx
0x18000cf91  cmovnz  ebx, eax
0x18000cf94  jmp     short loc_18000CFDF
0x18000cf96  cmp     ebx, 5
0x18000cf99  jnz     short loc_18000CFC6
0x18000cf9b  mov     rcx, rdi; pszPath
0x18000cf9e  call    cs:__imp_PathIsRootW
0x18000cfa4  xor     ecx, ecx
0x18000cfa6  test    eax, eax
0x18000cfa8  jz      short loc_18000CFC6
0x18000cfaa  mov     [rsp+0E8h+var_C8], rcx
0x18000cfaf  xor     r9d, r9d
0x18000cfb2  mov     ecx, ebx
0x18000cfb4  xor     r8d, r8d
0x18000cfb7  mov     edx, 0C0007234h
0x18000cfbc  call    DsRolepSetFailureMessage
0x18000cfc1  jmp     loc_18000D2B2
0x18000cfc6  mov     r9d, ebx
0x18000cfc9  lea     rdx, aFailedToCreate_4; "Failed to create path %ws: %lu\n"
0x18000cfd0  mov     r8, rdi
0x18000cfd3  mov     ecx, 4
0x18000cfd8  call    DsRolepLogPrintRoutine
0x18000cfdd  xor     edx, edx
0x18000cfdf  mov     [rsp+0E8h+arg_40], dl
0x18000cfe6  test    ebx, ebx
0x18000cfe8  jnz     short loc_18000D00B
0x18000cfea  mov     rbx, [rsp+0E8h+arg_0]
0x18000cff2  and     r13d, 800000h
0x18000cff9  jz      short loc_18000D03A
0x18000cffb  mov     rcx, rbx
0x18000cffe  call    DsRolepCleanupDFSRDBFolder
0x18000d003  xor     edx, edx
0x18000d005  mov     ebx, eax
0x18000d007  test    eax, eax
0x18000d009  jz      short loc_18000D03A
0x18000d00b  xor     r9d, r9d
0x18000d00e  mov     [rsp+0E8h+var_C8], rsi
0x18000d013  xor     r8d, r8d
0x18000d016  mov     edx, 40007230h
0x18000d01b  mov     ecx, ebx
0x18000d01d  call    DsRolepSetFailureMessage
0x18000d022  test    rdi, rdi
0x18000d025  jz      loc_18000D2E7
0x18000d02b  jmp     loc_18000D2B2
0x18000d030  mov     [rsp+0E8h+arg_40], 1
0x18000d038  jmp     short loc_18000CFF2
0x18000d03a  lea     rax, [r15+r15]
0x18000d03e  mov     rcx, rbp
0x18000d041  lea     r9, [rax+2]
0x18000d045  mov     word ptr [rax+rdi], 5Ch ; '\'
0x18000d04b  sar     rax, 1
0x18000d04e  add     r9, rdi
0x18000d051  sub     rcx, rax
0x18000d054  mov     [rsp+0E8h+pszDest], r9
0x18000d05c  dec     rcx
0x18000d05f  mov     r15, rdx
0x18000d062  mov     [rsp+0E8h+cchDest], rcx
0x18000d06a  cmp     r15, 6
0x18000d06e  jnb     short loc_18000D0ED
0x18000d070  cmp     r15, 1
0x18000d074  jnz     short loc_18000D07F
0x18000d076  cmp     [rsp+0E8h+arg_30], dl
0x18000d07d  jz      short loc_18000D0BF
0x18000d07f  mov     r8, [rsp+r15*8+0E8h+pszSrc]; pszSrc
0x18000d084  mov     rdx, rcx; cchDest
0x18000d087  mov     rcx, r9; pszDest
0x18000d08a  call    StringCchCopyW
0x18000d08f  xor     edx, edx; lpSecurityAttributes
0x18000d091  mov     rcx, rdi; lpPathName
0x18000d094  call    cs:__imp_CreateDirectoryW
0x18000d09a  xor     edx, edx
0x18000d09c  test    eax, eax
0x18000d09e  jnz     short loc_18000D0AF
0x18000d0a0  call    cs:__imp_GetLastError
0x18000d0a6  xor     edx, edx
0x18000d0a8  mov     ebx, eax
0x18000d0aa  test    r13d, r13d
0x18000d0ad  jz      short loc_18000D0C4
0x18000d0af  mov     r9, [rsp+0E8h+pszDest]
0x18000d0b7  mov     rcx, [rsp+0E8h+cchDest]
0x18000d0bf  inc     r15
0x18000d0c2  jmp     short loc_18000D06A
0x18000d0c4  mov     r9d, ebx
0x18000d0c7  lea     rdx, aFailedToCreate_4; "Failed to create path %ws: %lu\n"
0x18000d0ce  mov     r8, rdi
0x18000d0d1  mov     ecx, 4
0x18000d0d6  call    DsRolepLogPrintRoutine
0x18000d0db  xor     edx, edx
0x18000d0dd  test    ebx, ebx
0x18000d0df  jnz     loc_18000D282
0x18000d0e5  mov     r9, [rsp+0E8h+pszDest]
0x18000d0ed  mov     r15, [rsp+0E8h+arg_0]
0x18000d0f5  test    r13d, r13d
0x18000d0f8  mov     r13, [rsp+0E8h+arg_8]
0x18000d100  mov     [r9], dx
0x18000d104  jnz     short loc_18000D11B
0x18000d106  mov     rdx, r13
0x18000d109  mov     rcx, r15
0x18000d10c  call    DsRolepCreateSysVolLinks
0x18000d111  mov     ebx, eax
0x18000d113  test    eax, eax
0x18000d115  jnz     loc_18000D282
0x18000d11b  mov     rcx, gs:60h
0x18000d124  xor     edx, edx; Flags
0x18000d126  mov     r8, [rsp+0E8h+Size]; Size
0x18000d12b  mov     rcx, [rcx+30h]; HeapHandle
0x18000d12f  call    cs:__imp_RtlAllocateHeap
0x18000d135  xor     ebx, ebx
0x18000d137  mov     rsi, rax
0x18000d13a  test    rax, rax
0x18000d13d  jnz     short loc_18000D147
0x18000d13f  lea     ebx, [rax+8]
0x18000d142  jmp     loc_18000D282
0x18000d147  mov     r9, r15
0x18000d14a  lea     r8, aWs_1; "\\\\?\\%ws"
0x18000d151  mov     rdx, rbp; cchDest
0x18000d154  mov     rcx, rsi; pszDest
0x18000d157  call    StringCchPrintfW
0x18000d15c  inc     r14
0x18000d15f  cmp     [rsi+r14*2], bx
0x18000d164  jnz     short loc_18000D15C
0x18000d166  lea     rax, [r14+r14]
0x18000d16a  lea     r14, [rax+rsi]
0x18000d16e  sar     rax, 1
0x18000d171  sub     rbp, rax
0x18000d174  mov     eax, 5Ch ; '\'
0x18000d179  cmp     [r14], ax
0x18000d17d  jz      short loc_18000D18A
0x18000d17f  mov     [r14], ax
0x18000d183  add     r14, 2
0x18000d187  dec     rbp
0x18000d18a  lea     r15, DsRolepDfsrStringErrorUpdateCallback
0x18000d191  mov     rcx, r15
0x18000d194  call    cs:__imp_DfsrPrepareForPromotionW
0x18000d19a  mov     ebx, eax
0x18000d19c  test    eax, eax
0x18000d19e  jnz     loc_18000D26E
0x18000d1a4  lea     r9, aStagingAreas; "staging areas"
0x18000d1ab  mov     [rsp+0E8h+var_C8], r13
0x18000d1b0  lea     r8, aWsWs_3; "%ws\\%ws"
0x18000d1b7  mov     rdx, rbp; cchDest
0x18000d1ba  mov     rcx, r14; pszDest
0x18000d1bd  call    StringCchPrintfW
0x18000d1c2  mov     rdx, [rsp+0E8h+cchDest]; cchDest
0x18000d1ca  lea     r9, aSysvol; "sysvol"
0x18000d1d1  mov     rcx, [rsp+0E8h+pszDest]; pszDest
0x18000d1d9  lea     r8, aWsWs_3; "%ws\\%ws"
0x18000d1e0  mov     [rsp+0E8h+var_C8], r13
0x18000d1e5  call    StringCchPrintfW
0x18000d1ea  movzx   eax, [rsp+0E8h+arg_30]
0x18000d1f2  mov     rdx, r12
0x18000d1f5  mov     r9, [rsp+0E8h+arg_20]
0x18000d1fd  xor     ecx, ecx
0x18000d1ff  mov     r8, [rsp+0E8h+arg_18]
0x18000d207  mov     [rsp+0E8h+var_98], rdi
0x18000d20c  mov     [rsp+0E8h+var_A0], rsi
0x18000d211  mov     [rsp+0E8h+var_A8], eax
0x18000d215  lea     rax, aDomain_0; "Domain"
0x18000d21c  mov     [rsp+0E8h+var_B0], rax
0x18000d221  lea     rax, DsRolepDfsrStringUpdateCallbackNoFlags
0x18000d228  mov     [rsp+0E8h+var_B8], r13
0x18000d22d  mov     [rsp+0E8h+var_C0], r15
0x18000d232  mov     [rsp+0E8h+var_C8], rax
0x18000d237  call    cs:__imp_DfsrStartPromotionW
0x18000d23d  mov     ebx, eax
0x18000d23f  test    eax, eax
0x18000d241  jz      short loc_18000D2B2
0x18000d243  mov     dword ptr [rsp+0E8h+var_C0], eax
0x18000d247  lea     rdx, aDfsrstartpromo_0; "DfsrStartPromotionW on %ws / %ws / %ws "...
0x18000d24e  mov     r9, rsi
0x18000d251  mov     [rsp+0E8h+var_C8], rdi
0x18000d256  mov     r8, r13
0x18000d259  mov     ecx, 1
0x18000d25e  call    DsRolepLogPrintRoutine
0x18000d263  mov     dl, 1
0x18000d265  xor     ecx, ecx
0x18000d267  call    DsRolepFinishSysVolPropagation
0x18000d26c  jmp     short loc_18000D282
0x18000d26e  mov     r8d, eax
0x18000d271  lea     rdx, aDfsrpreparefor_1; "DfsrPrepareForPromotionW failed with %l"...
0x18000d278  mov     ecx, 1
0x18000d27d  call    DsRolepLogPrintRoutine
0x18000d282  mov     r8b, [rsp+0E8h+arg_40]
0x18000d28a  mov     rcx, rdi
0x18000d28d  mov     rdx, [rsp+0E8h+Size]
0x18000d292  call    DsRolepDelnodePath
0x18000d297  test    eax, eax
0x18000d299  jz      short loc_18000D2B2
0x18000d29b  mov     r9d, eax
0x18000d29e  lea     rdx, aFailedToDelete_0; "Failed to delete path %ws: %lu\n"
0x18000d2a5  mov     r8, rdi
0x18000d2a8  mov     ecx, 4
0x18000d2ad  call    DsRolepLogPrintRoutine
0x18000d2b2  mov     rcx, gs:60h
  ... truncated ...
```
