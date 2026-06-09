# CEnergyTaskHandler::ReportsCleanup(ushort const *,ushort const *,ulong)

- ea: `0x1800023f8`
- end: `0x180002721`
- name: `?ReportsCleanup@CEnergyTaskHandler@@AEAAJPEBG0K@Z`
- size: `809`
- prototype: `__int64 __fastcall(CEnergyTaskHandler *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x180002728`

## callees

- `0x1800023f8`
- `0x180003a86`
- `0x180003ac0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800025d7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800025d7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800026cf`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800026cf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800024d3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800024d3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000267f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000267f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002527`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002527`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800026f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002513`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002513`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800026e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000269a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000269a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800024b7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000266c`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800024b7`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000266c`

## string_xrefs

- `0x1800024a6`: `energy-report-????-??-??.xml`

## pseudocode

```c
__int64 __fastcall CEnergyTaskHandler::ReportsCleanup(
        CEnergyTaskHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  WCHAR *v4; // r8
  FILETIME *v5; // r14
  __int64 v6; // rax
  const unsigned __int16 *v7; // rcx
  __int64 v8; // rdx
  WCHAR *v9; // rcx
  signed int v10; // esi
  HANDLE FirstFileW; // rdi
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  FILETIME *v14; // rax
  FILETIME *v15; // rbx
  WCHAR *cFileName; // r8
  __int64 v17; // rcx
  __int64 v18; // rdx
  FILETIME *v19; // rax
  FILETIME *v20; // rcx
  FILETIME **i; // rcx
  BOOL NextFileW; // eax
  const WCHAR *v23; // rbx
  int v24; // eax
  __int64 v25; // rcx
  WCHAR *v26; // rax
  const unsigned __int16 *v27; // r8
  __int64 v28; // rdx
  WCHAR *v29; // rcx
  signed int v30; // eax
  HANDLE v31; // rax
  FILETIME *v32; // rbx
  HANDLE v33; // rax
  FILETIME *v35; // [rsp+20h] [rbp-E0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[264]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v4 = pszPath;
  v35 = 0;
  v5 = 0;
  v6 = 2147483646;
  v7 = a2;
  v8 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*v7 )
      break;
    *v4++ = *v7++;
    --v6;
    --v8;
  }
  while ( v8 );
  v9 = v4 - 1;
  v10 = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v9 = v4;
  *v9 = 0;
  if ( v8 )
  {
    v10 = PathCchAppend(pszPath, 0x104u, L"energy-report-????-??-??.xml");
    if ( v10 < 0 )
      return (unsigned int)v10;
    FirstFileW = FindFirstFileW(pszPath, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      if ( GetLastError() == 2 )
      {
        return 0;
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
      return (unsigned int)v10;
    }
    do
    {
      ProcessHeap = GetProcessHeap();
      v14 = (FILETIME *)HeapAlloc(ProcessHeap, 8u, 0x218u);
      v15 = v14;
      if ( !v14 )
      {
        v10 = -2147024882;
        goto LABEL_47;
      }
      cFileName = FindFileData.cFileName;
      v14[1] = FindFileData.ftCreationTime;
      v17 = 2147483646;
      v18 = 260;
      v19 = v14 + 2;
      do
      {
        if ( !v17 )
          break;
        if ( !*cFileName )
          break;
        LOWORD(v19->dwLowDateTime) = *cFileName++;
        v19 = (FILETIME *)((char *)v19 + 2);
        --v17;
        --v18;
      }
      while ( v18 );
      v20 = (FILETIME *)((char *)v19 - 2);
      if ( v18 )
        v20 = v19;
      LOWORD(v20->dwLowDateTime) = 0;
      v10 = v18 == 0 ? 0x8007007A : 0;
      if ( !v18 )
      {
        v31 = GetProcessHeap();
        HeapFree(v31, 0, v15);
        goto LABEL_47;
      }
      for ( i = &v35; v5; v5 = (FILETIME *)*v5 )
      {
        if ( *(_QWORD *)&v5[1] <= *(_QWORD *)&v15[1] )
          break;
        i = (FILETIME **)v5;
      }
      *v15 = (FILETIME)*i;
      *i = v15;
      NextFileW = FindNextFileW(FirstFileW, &FindFileData);
      v5 = v35;
    }
    while ( NextFileW );
    v23 = (const WCHAR *)v35;
    v24 = 20;
    do
    {
      if ( v23 )
        v23 = *(const WCHAR **)v23;
      --v24;
    }
    while ( v24 );
    while ( 1 )
    {
      if ( !v23 )
      {
        v10 = 0;
        goto LABEL_47;
      }
      v25 = 2147483646;
      v26 = pszPath;
      v27 = a2;
      v28 = 260;
      do
      {
        if ( !v25 )
          break;
        if ( !*v27 )
          break;
        *v26++ = *v27++;
        --v25;
        --v28;
      }
      while ( v28 );
      v29 = v26 - 1;
      if ( v28 )
        v29 = v26;
      *v29 = 0;
      v10 = v28 == 0 ? 0x8007007A : 0;
      if ( !v28 )
        goto LABEL_47;
      v10 = PathCchAppend(pszPath, 0x104u, v23 + 8);
      if ( v10 < 0 )
        goto LABEL_47;
      if ( !DeleteFileW(pszPath) )
        break;
      v23 = *(const WCHAR **)v23;
    }
    v30 = GetLastError();
    v10 = v30;
    if ( v30 > 0 )
      v10 = (unsigned __int16)v30 | 0x80070000;
LABEL_47:
    FindClose(FirstFileW);
  }
  while ( v5 )
  {
    v32 = v5;
    v5 = (FILETIME *)*v5;
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v32);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800023f8  push    rbp
0x1800023fa  push    rbx
0x1800023fb  push    rsi
0x1800023fc  push    rdi
0x1800023fd  push    r12
0x1800023ff  push    r13
0x180002401  push    r14
0x180002403  push    r15
0x180002405  lea     rbp, [rsp-3A8h]
0x18000240d  sub     rsp, 4A8h
0x180002414  mov     rax, cs:__security_cookie
0x18000241b  xor     rax, rsp
0x18000241e  mov     [rbp+3E0h+var_50], rax
0x180002425  mov     r15, rdx
0x180002428  lea     rcx, [rsp+4E0h+FindFileData]; void *
0x18000242d  xor     edx, edx; Val
0x18000242f  mov     r8d, 250h; Size
0x180002435  call    memset_0
0x18000243a  xor     r12d, r12d
0x18000243d  lea     r8, [rbp+3E0h+pszPath]
0x180002444  mov     r13d, 104h
0x18000244a  mov     [rsp+4E0h+var_4C0], r12
0x18000244f  mov     r14d, r12d
0x180002452  mov     eax, 7FFFFFFEh
0x180002457  mov     rcx, r15
0x18000245a  mov     edx, r13d
0x18000245d  test    rax, rax
0x180002460  jz      short loc_180002481
0x180002462  movzx   r9d, word ptr [rcx]
0x180002466  test    r9w, r9w
0x18000246a  jz      short loc_180002481
0x18000246c  mov     [r8], r9w
0x180002470  add     rcx, 2
0x180002474  add     r8, 2
0x180002478  dec     rax
0x18000247b  sub     rdx, 1
0x18000247f  jnz     short loc_18000245D
0x180002481  mov     rax, rdx
0x180002484  lea     rcx, [r8-2]
0x180002488  neg     rax
0x18000248b  sbb     esi, esi
0x18000248d  not     esi
0x18000248f  and     esi, 8007007Ah
0x180002495  test    rdx, rdx
0x180002498  cmovnz  rcx, r8
0x18000249c  mov     [rcx], r12w
0x1800024a0  jz      loc_1800026D5
0x1800024a6  lea     r8, pszMore; "energy-report-????-??-??.xml"
0x1800024ad  mov     rdx, r13; cchPath
0x1800024b0  lea     rcx, [rbp+3E0h+pszPath]; pszPath
0x1800024b7  call    cs:__imp_PathCchAppend
0x1800024bd  mov     esi, eax
0x1800024bf  test    eax, eax
0x1800024c1  js      loc_1800026FC
0x1800024c7  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x1800024cc  lea     rcx, [rbp+3E0h+pszPath]; lpFileName
0x1800024d3  call    cs:__imp_FindFirstFileW
0x1800024d9  mov     rdi, rax
0x1800024dc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800024e0  jnz     short loc_180002513
0x1800024e2  call    cs:__imp_GetLastError
0x1800024e8  cmp     eax, 2
0x1800024eb  jnz     short loc_1800024F5
0x1800024ed  mov     esi, r12d
0x1800024f0  jmp     loc_1800026FC
0x1800024f5  call    cs:__imp_GetLastError
0x1800024fb  mov     esi, eax
0x1800024fd  test    eax, eax
0x1800024ff  jle     loc_1800026FC
0x180002505  movzx   esi, ax
0x180002508  or      esi, 80070000h
0x18000250e  jmp     loc_1800026FC
0x180002513  call    cs:__imp_GetProcessHeap
0x180002519  mov     edx, 8; dwFlags
0x18000251e  mov     r8d, 218h; dwBytes
0x180002524  mov     rcx, rax; hHeap
0x180002527  call    cs:__imp_HeapAlloc
0x18000252d  mov     rbx, rax
0x180002530  test    rax, rax
0x180002533  jz      loc_1800026C7
0x180002539  mov     eax, [rsp+4E0h+FindFileData.ftCreationTime.dwHighDateTime]
0x18000253d  lea     r8, [rsp+4E0h+FindFileData.cFileName]
0x180002542  mov     [rbx+0Ch], eax
0x180002545  mov     ecx, 7FFFFFFEh
0x18000254a  mov     eax, [rsp+4E0h+FindFileData.ftCreationTime.dwLowDateTime]
0x18000254e  mov     rdx, r13
0x180002551  mov     [rbx+8], eax
0x180002554  lea     rax, [rbx+10h]
0x180002558  test    rcx, rcx
0x18000255b  jz      short loc_18000257C
0x18000255d  movzx   r9d, word ptr [r8]
0x180002561  test    r9w, r9w
0x180002565  jz      short loc_18000257C
0x180002567  mov     [rax], r9w
0x18000256b  add     r8, 2
0x18000256f  add     rax, 2
0x180002573  dec     rcx
0x180002576  sub     rdx, 1
0x18000257a  jnz     short loc_180002558
0x18000257c  test    rdx, rdx
0x18000257f  lea     rcx, [rax-2]
0x180002583  cmovnz  rcx, rax
0x180002587  mov     rax, rdx
0x18000258a  neg     rax
0x18000258d  sbb     esi, esi
0x18000258f  not     esi
0x180002591  mov     [rcx], r12w
0x180002595  and     esi, 8007007Ah
0x18000259b  test    rdx, rdx
0x18000259e  jz      loc_1800026B1
0x1800025a4  lea     rcx, [rsp+4E0h+var_4C0]
0x1800025a9  test    r14, r14
0x1800025ac  jz      short loc_1800025C6
0x1800025ae  mov     rdx, [rbx+8]
0x1800025b2  cmp     [r14+8], rdx
0x1800025b6  jbe     short loc_1800025C6
0x1800025b8  mov     rax, [r14]
0x1800025bb  mov     rcx, r14
0x1800025be  mov     r14, rax
0x1800025c1  test    rax, rax
0x1800025c4  jnz     short loc_1800025B2
0x1800025c6  mov     rax, [rcx]
0x1800025c9  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x1800025ce  mov     [rbx], rax
0x1800025d1  mov     [rcx], rbx
0x1800025d4  mov     rcx, rdi; hFindFile
0x1800025d7  call    cs:__imp_FindNextFileW
0x1800025dd  mov     r14, [rsp+4E0h+var_4C0]
0x1800025e2  test    eax, eax
0x1800025e4  jnz     loc_180002513
0x1800025ea  mov     rbx, r14
0x1800025ed  mov     eax, 14h
0x1800025f2  test    rbx, rbx
0x1800025f5  jz      short loc_1800025FA
0x1800025f7  mov     rbx, [rbx]
0x1800025fa  add     eax, 0FFFFFFFFh
0x1800025fd  jnz     short loc_1800025F2
0x1800025ff  jmp     loc_18000268C
0x180002604  mov     ecx, 7FFFFFFEh
0x180002609  lea     rax, [rbp+3E0h+pszPath]
0x180002610  mov     r8, r15
0x180002613  mov     rdx, r13
0x180002616  test    rcx, rcx
0x180002619  jz      short loc_18000263A
0x18000261b  movzx   r9d, word ptr [r8]
0x18000261f  test    r9w, r9w
0x180002623  jz      short loc_18000263A
0x180002625  mov     [rax], r9w
0x180002629  add     r8, 2
0x18000262d  add     rax, 2
0x180002631  dec     rcx
0x180002634  sub     rdx, 1
0x180002638  jnz     short loc_180002616
0x18000263a  test    rdx, rdx
0x18000263d  lea     rcx, [rax-2]
0x180002641  cmovnz  rcx, rax
0x180002645  mov     rax, rdx
0x180002648  neg     rax
0x18000264b  sbb     esi, esi
0x18000264d  not     esi
0x18000264f  mov     [rcx], r12w
0x180002653  and     esi, 8007007Ah
0x180002659  test    rdx, rdx
0x18000265c  jz      short loc_1800026CC
0x18000265e  lea     r8, [rbx+10h]; pszMore
0x180002662  mov     rdx, r13; cchPath
0x180002665  lea     rcx, [rbp+3E0h+pszPath]; pszPath
0x18000266c  call    cs:__imp_PathCchAppend
0x180002672  mov     esi, eax
0x180002674  test    eax, eax
0x180002676  js      short loc_1800026CC
0x180002678  lea     rcx, [rbp+3E0h+pszPath]; lpFileName
0x18000267f  call    cs:__imp_DeleteFileW
0x180002685  test    eax, eax
0x180002687  jz      short loc_18000269A
0x180002689  mov     rbx, [rbx]
0x18000268c  test    rbx, rbx
0x18000268f  jnz     loc_180002604
0x180002695  mov     esi, r12d
0x180002698  jmp     short loc_1800026CC
0x18000269a  call    cs:__imp_GetLastError
0x1800026a0  mov     esi, eax
0x1800026a2  test    eax, eax
0x1800026a4  jle     short loc_1800026CC
0x1800026a6  movzx   esi, ax
0x1800026a9  or      esi, 80070000h
0x1800026af  jmp     short loc_1800026CC
0x1800026b1  call    cs:__imp_GetProcessHeap
0x1800026b7  mov     r8, rbx; lpMem
0x1800026ba  xor     edx, edx; dwFlags
0x1800026bc  mov     rcx, rax; hHeap
0x1800026bf  call    cs:__imp_HeapFree
0x1800026c5  jmp     short loc_1800026CC
0x1800026c7  mov     esi, 8007000Eh
0x1800026cc  mov     rcx, rdi; hFindFile
0x1800026cf  call    cs:__imp_FindClose
0x1800026d5  test    r14, r14
0x1800026d8  jz      short loc_1800026FC
0x1800026da  mov     rdi, [r14]
0x1800026dd  mov     rbx, r14
0x1800026e0  mov     r14, rdi
0x1800026e3  call    cs:__imp_GetProcessHeap
0x1800026e9  mov     r8, rbx; lpMem
0x1800026ec  xor     edx, edx; dwFlags
0x1800026ee  mov     rcx, rax; hHeap
0x1800026f1  call    cs:__imp_HeapFree
0x1800026f7  test    rdi, rdi
0x1800026fa  jnz     short loc_1800026DA
0x1800026fc  mov     eax, esi
0x1800026fe  mov     rcx, [rbp+3E0h+var_50]
0x180002705  xor     rcx, rsp; StackCookie
0x180002708  call    __security_check_cookie
0x18000270d  add     rsp, 4A8h
0x180002714  pop     r15
0x180002716  pop     r14
0x180002718  pop     r13
0x18000271a  pop     r12
0x18000271c  pop     rdi
0x18000271d  pop     rsi
0x18000271e  pop     rbx
0x18000271f  pop     rbp
0x180002720  retn
```
