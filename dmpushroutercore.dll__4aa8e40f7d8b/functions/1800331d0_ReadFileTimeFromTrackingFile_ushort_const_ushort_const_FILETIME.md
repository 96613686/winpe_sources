# ReadFileTimeFromTrackingFile(ushort const *,ushort const *,_FILETIME *)

- ea: `0x1800331d0`
- end: `0x180033447`
- name: `?ReadFileTimeFromTrackingFile@@YAJPEBG0PEAU_FILETIME@@@Z`
- size: `631`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180032ea8`

## callees

- `0x18000ba94`
- `0x18000bab4`
- `0x18001cc68`
- `0x180032d0c`
- `0x1800331d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800332e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800332e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003334f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800333c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003334f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800333c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033413`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033255`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800332a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003335e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003336e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800333b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800333d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800333e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033405`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033432`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033255`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800332a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003335e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003336e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800333b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800333d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800333e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033405`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033432`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003331c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003331c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800332d5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800332d5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180033394`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180033394`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180033277`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180033277`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadFileTimeFromTrackingFile(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct _FILETIME *a3)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  int StoragePath; // eax
  HRESULT v8; // eax
  HANDLE FileW; // rbx
  DWORD LastError; // eax
  struct _FILETIME *v11; // rax
  struct _FILETIME *v12; // rdi
  const char *v13; // r9
  __int64 v14; // rdx
  unsigned int v15; // esi
  int dwCreationDisposition; // [rsp+20h] [rbp-20h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HLOCAL hMem; // [rsp+60h] [rbp+20h] BYREF
  const unsigned __int16 *NumberOfBytesRead; // [rsp+68h] [rbp+28h] BYREF
  PWSTR ppszPathOut; // [rsp+78h] [rbp+38h] BYREF

  NumberOfBytesRead = a2;
  if ( !a1 )
  {
    v4 = 448;
LABEL_3:
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return v5;
  }
  if ( !a3 )
  {
    v4 = 450;
    goto LABEL_3;
  }
  hMem = 0;
  StoragePath = GetStoragePath(a1, (PWSTR *)&hMem);
  v5 = StoragePath;
  if ( StoragePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C5,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)StoragePath,
      dwCreationDisposition);
LABEL_9:
    if ( hMem )
      LocalFree(hMem);
    return v5;
  }
  ppszPathOut = 0;
  v8 = PathAllocCombine((PCWSTR)hMem, L"2bf1e654-2be5-42e4-ab28-b80a4dc9eeee", 0, &ppszPathOut);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C8,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)v8,
      dwCreationDisposition);
    goto LABEL_13;
  }
  FileW = CreateFileW(ppszPathOut, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1D9,
             (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
             (const char *)LastError,
             dwCreationDispositiona);
LABEL_13:
      if ( ppszPathOut )
        LocalFree(ppszPathOut);
      goto LABEL_9;
    }
    goto LABEL_39;
  }
  LODWORD(NumberOfBytesRead) = 0;
  v11 = (struct _FILETIME *)LocalAlloc(0, 8u);
  v12 = v11;
  if ( v11 )
  {
    if ( ReadFile(FileW, v11, 8u, (LPDWORD)&NumberOfBytesRead, 0) )
    {
      if ( (_DWORD)NumberOfBytesRead == 8 )
      {
        *a3 = *v12;
        LocalFree(v12);
        if ( FileW )
          CloseHandle(FileW);
LABEL_39:
        if ( ppszPathOut )
          LocalFree(ppszPathOut);
        if ( hMem )
          LocalFree(hMem);
        return 0;
      }
      v14 = 490;
    }
    else
    {
      v14 = 486;
    }
    v15 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v14,
            (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
            v13);
    LocalFree(v12);
    if ( FileW )
      CloseHandle(FileW);
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    if ( hMem )
      LocalFree(hMem);
    return v15;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)0x8007000ELL,
      dwCreationDispositiona);
    if ( FileW )
      CloseHandle(FileW);
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    if ( hMem )
      LocalFree(hMem);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800331d0  mov     [rsp-18h+arg_10], rbx
0x1800331d5  mov     [rsp-18h+NumberOfBytesRead], rdx
0x1800331da  push    rbp
0x1800331db  push    rsi
0x1800331dc  push    rdi
0x1800331dd  mov     rbp, rsp
0x1800331e0  sub     rsp, 40h
0x1800331e4  mov     rsi, r8
0x1800331e7  test    rcx, rcx
0x1800331ea  jnz     short loc_180033210
0x1800331ec  mov     edx, 1C0h; void *
0x1800331f1  mov     ebx, 80070057h
0x1800331f6  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800331fd  mov     r9d, ebx; char *
0x180033200  mov     rcx, [rbp+18h]; this
0x180033204  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033209  mov     eax, ebx
0x18003320b  jmp     loc_18003343A
0x180033210  test    rsi, rsi
0x180033213  jnz     short loc_18003321C
0x180033215  mov     edx, 1C2h
0x18003321a  jmp     short loc_1800331F1
0x18003321c  mov     [rbp+hMem], 0
0x180033224  lea     rdx, [rbp+hMem]; ppszPathOut
0x180033228  call    ?GetStoragePath@@YAJPEBGPEAPEAG@Z; GetStoragePath(ushort const *,ushort * *)
0x18003322d  mov     ebx, eax
0x18003322f  test    eax, eax
0x180033231  jns     short loc_18003325D
0x180033233  mov     rcx, [rbp+18h]; this
0x180033237  mov     r9d, eax; char *
0x18003323a  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033241  mov     edx, 1C5h; void *
0x180033246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003324b  nop
0x18003324c  mov     rcx, [rbp+hMem]; hMem
0x180033250  test    rcx, rcx
0x180033253  jz      short loc_180033209
0x180033255  call    cs:__imp_LocalFree
0x18003325b  jmp     short loc_180033209
0x18003325d  mov     [rbp+ppszPathOut], 0
0x180033265  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180033269  xor     r8d, r8d; dwFlags
0x18003326c  lea     rdx, a2bf1e6542be542; "2bf1e654-2be5-42e4-ab28-b80a4dc9eeee"
0x180033273  mov     rcx, [rbp+hMem]; pszPathIn
0x180033277  call    cs:__imp_PathAllocCombine
0x18003327d  mov     ebx, eax
0x18003327f  test    eax, eax
0x180033281  jns     short loc_1800332AC
0x180033283  mov     rcx, [rbp+18h]; this
0x180033287  mov     r9d, eax; char *
0x18003328a  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033291  mov     edx, 1C8h; void *
0x180033296  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003329b  mov     rcx, [rbp+ppszPathOut]; hMem
0x18003329f  test    rcx, rcx
0x1800332a2  jz      short loc_18003324C
0x1800332a4  call    cs:__imp_LocalFree
0x1800332aa  jmp     short loc_18003324C
0x1800332ac  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x1800332b5  mov     [rsp+40h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800332bd  mov     [rsp+40h+dwCreationDisposition], 3; int
0x1800332c5  xor     r9d, r9d; lpSecurityAttributes
0x1800332c8  mov     edx, 80000000h; dwDesiredAccess
0x1800332cd  lea     r8d, [r9+1]; dwShareMode
0x1800332d1  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x1800332d5  call    cs:__imp_CreateFileW
0x1800332db  mov     rbx, rax
0x1800332de  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800332e2  jnz     short loc_18003330E
0x1800332e4  call    cs:__imp_GetLastError
0x1800332ea  test    eax, eax
0x1800332ec  jz      loc_180033419
0x1800332f2  mov     rcx, [rbp+18h]; this
0x1800332f6  mov     r9d, eax; char *
0x1800332f9  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033300  mov     edx, 1D9h; void *
0x180033305  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003330a  mov     ebx, eax
0x18003330c  jmp     short loc_18003329B
0x18003330e  mov     dword ptr [rbp+NumberOfBytesRead], 0
0x180033315  mov     edx, 8; uBytes
0x18003331a  xor     ecx, ecx; uFlags
0x18003331c  call    cs:__imp_LocalAlloc
0x180033322  mov     rdi, rax
0x180033325  test    rax, rax
0x180033328  jnz     short loc_18003337B
0x18003332a  mov     rcx, [rbp+18h]; this
0x18003332e  mov     edi, 8007000Eh
0x180033333  mov     r9d, edi; char *
0x180033336  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18003333d  mov     edx, 1E0h; void *
0x180033342  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033347  test    rbx, rbx
0x18003334a  jz      short loc_180033355
0x18003334c  mov     rcx, rbx; hObject
0x18003334f  call    cs:__imp_CloseHandle
0x180033355  mov     rcx, [rbp+ppszPathOut]; hMem
0x180033359  test    rcx, rcx
0x18003335c  jz      short loc_180033365
0x18003335e  call    cs:__imp_LocalFree
0x180033364  nop
0x180033365  mov     rcx, [rbp+hMem]; hMem
0x180033369  test    rcx, rcx
0x18003336c  jz      short loc_180033374
0x18003336e  call    cs:__imp_LocalFree
0x180033374  mov     eax, edi
0x180033376  jmp     loc_18003343A
0x18003337b  mov     qword ptr [rsp+40h+dwCreationDisposition], 0; lpOverlapped
0x180033384  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180033388  mov     r8d, 8; nNumberOfBytesToRead
0x18003338e  mov     rdx, rdi; lpBuffer
0x180033391  mov     rcx, rbx; hFile
0x180033394  call    cs:__imp_ReadFile
0x18003339a  test    eax, eax
0x18003339c  jnz     short loc_1800333EF
0x18003339e  mov     edx, 1E6h; void *
0x1800333a3  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800333aa  mov     rcx, [rbp+18h]; this
0x1800333ae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800333b3  mov     esi, eax
0x1800333b5  mov     rcx, rdi; hMem
0x1800333b8  call    cs:__imp_LocalFree
0x1800333be  test    rbx, rbx
0x1800333c1  jz      short loc_1800333CC
0x1800333c3  mov     rcx, rbx; hObject
0x1800333c6  call    cs:__imp_CloseHandle
0x1800333cc  mov     rcx, [rbp+ppszPathOut]; hMem
0x1800333d0  test    rcx, rcx
0x1800333d3  jz      short loc_1800333DC
0x1800333d5  call    cs:__imp_LocalFree
0x1800333db  nop
0x1800333dc  mov     rcx, [rbp+hMem]; hMem
0x1800333e0  test    rcx, rcx
0x1800333e3  jz      short loc_1800333EB
0x1800333e5  call    cs:__imp_LocalFree
0x1800333eb  mov     eax, esi
0x1800333ed  jmp     short loc_18003343A
0x1800333ef  cmp     dword ptr [rbp+NumberOfBytesRead], 8
0x1800333f3  jz      short loc_1800333FC
0x1800333f5  mov     edx, 1EAh
0x1800333fa  jmp     short loc_1800333A3
0x1800333fc  mov     rax, [rdi]
0x1800333ff  mov     [rsi], rax
0x180033402  mov     rcx, rdi; hMem
0x180033405  call    cs:__imp_LocalFree
0x18003340b  test    rbx, rbx
0x18003340e  jz      short loc_180033419
0x180033410  mov     rcx, rbx; hObject
0x180033413  call    cs:__imp_CloseHandle
0x180033419  mov     rcx, [rbp+ppszPathOut]; hMem
0x18003341d  test    rcx, rcx
0x180033420  jz      short loc_180033429
0x180033422  call    cs:__imp_LocalFree
0x180033428  nop
0x180033429  mov     rcx, [rbp+hMem]; hMem
0x18003342d  test    rcx, rcx
0x180033430  jz      short loc_180033438
0x180033432  call    cs:__imp_LocalFree
0x180033438  xor     eax, eax
0x18003343a  mov     rbx, [rsp+40h+arg_10]
0x18003343f  add     rsp, 40h
0x180033443  pop     rdi
0x180033444  pop     rsi
0x180033445  pop     rbp
0x180033446  retn
```
