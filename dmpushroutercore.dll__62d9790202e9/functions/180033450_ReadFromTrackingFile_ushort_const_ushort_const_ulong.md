# ReadFromTrackingFile(ushort const *,ushort const *,ulong *)

- ea: `0x180033450`
- end: `0x1800336d4`
- name: `?ReadFromTrackingFile@@YAJPEBG0PEAK@Z`
- size: `644`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002feec`
- `0x180032e3c`

## callees

- `0x18000ba94`
- `0x18000bab4`
- `0x18001cc68`
- `0x180032d0c`
- `0x180033450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003356a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003356a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800335de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033655`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800336a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800335de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033655`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800336a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800334df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003352a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800335ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800335fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033647`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033664`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033674`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033692`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800336af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800336bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800334df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003352a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800335ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800335fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033647`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033664`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033674`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033692`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800336af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800336bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800335ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800335ab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003355b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003355b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180033623`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180033623`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800334fd`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800334fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadFromTrackingFile(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int StoragePath; // eax
  HRESULT v9; // eax
  HANDLE FileW; // rbx
  DWORD LastError; // eax
  unsigned int *v12; // rax
  unsigned int *v13; // rdi
  const char *v14; // r9
  __int64 v15; // rdx
  unsigned int v16; // esi
  int dwCreationDisposition; // [rsp+20h] [rbp-30h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-30h]
  PWSTR ppszPathOut; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+38h] BYREF

  if ( !a1 )
  {
    v5 = 499;
LABEL_3:
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return v6;
  }
  if ( !a2 )
  {
    v5 = 500;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v5 = 501;
    goto LABEL_3;
  }
  hMem = 0;
  StoragePath = GetStoragePath(a1, (PWSTR *)&hMem);
  v6 = StoragePath;
  if ( StoragePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F8,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)StoragePath,
      dwCreationDisposition);
LABEL_11:
    if ( hMem )
      LocalFree(hMem);
    return v6;
  }
  ppszPathOut = 0;
  v9 = PathAllocCombine((PCWSTR)hMem, a2, 0, &ppszPathOut);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FB,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)v9,
      dwCreationDisposition);
    goto LABEL_15;
  }
  FileW = CreateFileW(ppszPathOut, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError != 2 && LastError )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x20F,
             (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
             (const char *)LastError,
             dwCreationDispositiona);
LABEL_15:
      if ( ppszPathOut )
        LocalFree(ppszPathOut);
      goto LABEL_11;
    }
    goto LABEL_42;
  }
  NumberOfBytesRead = 0;
  v12 = (unsigned int *)LocalAlloc(0, 4u);
  v13 = v12;
  if ( v12 )
  {
    if ( ReadFile(FileW, v12, 4u, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead == 4 )
      {
        *a3 = *v13;
        LocalFree(v13);
        if ( FileW )
          CloseHandle(FileW);
LABEL_42:
        if ( ppszPathOut )
          LocalFree(ppszPathOut);
        if ( hMem )
          LocalFree(hMem);
        return 0;
      }
      v15 = 547;
    }
    else
    {
      v15 = 543;
    }
    v16 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v15,
            (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
            v14);
    LocalFree(v13);
    if ( FileW )
      CloseHandle(FileW);
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    if ( hMem )
      LocalFree(hMem);
    return v16;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x219,
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
0x180033450  mov     [rsp-18h+arg_8], rbx
0x180033455  push    rbp
0x180033456  push    rsi
0x180033457  push    rdi
0x180033458  mov     rbp, rsp
0x18003345b  sub     rsp, 50h
0x18003345f  mov     rsi, r8
0x180033462  mov     rdi, rdx
0x180033465  test    rcx, rcx
0x180033468  jnz     short loc_18003348E
0x18003346a  mov     edx, 1F3h; void *
0x18003346f  mov     ebx, 80070057h
0x180033474  mov     rcx, [rbp+18h]; this
0x180033478  mov     r9d, ebx; char *
0x18003347b  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033487  mov     eax, ebx
0x180033489  jmp     loc_1800336C7
0x18003348e  test    rdi, rdi
0x180033491  jnz     short loc_18003349A
0x180033493  mov     edx, 1F4h
0x180033498  jmp     short loc_18003346F
0x18003349a  test    rsi, rsi
0x18003349d  jnz     short loc_1800334A6
0x18003349f  mov     edx, 1F5h
0x1800334a4  jmp     short loc_18003346F
0x1800334a6  mov     [rbp+hMem], 0
0x1800334ae  lea     rdx, [rbp+hMem]; ppszPathOut
0x1800334b2  call    ?GetStoragePath@@YAJPEBGPEAPEAG@Z; GetStoragePath(ushort const *,ushort * *)
0x1800334b7  mov     ebx, eax
0x1800334b9  test    eax, eax
0x1800334bb  jns     short loc_1800334E7
0x1800334bd  mov     rcx, [rbp+18h]; this
0x1800334c1  mov     r9d, eax; char *
0x1800334c4  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800334cb  mov     edx, 1F8h; void *
0x1800334d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800334d5  nop
0x1800334d6  mov     rcx, [rbp+hMem]; hMem
0x1800334da  test    rcx, rcx
0x1800334dd  jz      short loc_180033487
0x1800334df  call    cs:__imp_LocalFree
0x1800334e5  jmp     short loc_180033487
0x1800334e7  mov     [rbp+ppszPathOut], 0
0x1800334ef  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x1800334f3  xor     r8d, r8d; dwFlags
0x1800334f6  mov     rdx, rdi; pszMore
0x1800334f9  mov     rcx, [rbp+hMem]; pszPathIn
0x1800334fd  call    cs:__imp_PathAllocCombine
0x180033503  mov     ebx, eax
0x180033505  test    eax, eax
0x180033507  jns     short loc_180033532
0x180033509  mov     rcx, [rbp+18h]; this
0x18003350d  mov     r9d, eax; char *
0x180033510  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033517  mov     edx, 1FBh; void *
0x18003351c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033521  mov     rcx, [rbp+ppszPathOut]; hMem
0x180033525  test    rcx, rcx
0x180033528  jz      short loc_1800334D6
0x18003352a  call    cs:__imp_LocalFree
0x180033530  jmp     short loc_1800334D6
0x180033532  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x18003353b  mov     [rsp+50h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180033543  mov     [rsp+50h+dwCreationDisposition], 3; int
0x18003354b  xor     r9d, r9d; lpSecurityAttributes
0x18003354e  mov     edx, 80000000h; dwDesiredAccess
0x180033553  lea     r8d, [r9+1]; dwShareMode
0x180033557  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x18003355b  call    cs:__imp_CreateFileW
0x180033561  mov     rbx, rax
0x180033564  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033568  jnz     short loc_18003359D
0x18003356a  call    cs:__imp_GetLastError
0x180033570  cmp     eax, 2
0x180033573  jz      loc_1800336A6
0x180033579  test    eax, eax
0x18003357b  jz      loc_1800336A6
0x180033581  mov     rcx, [rbp+18h]; this
0x180033585  mov     r9d, eax; char *
0x180033588  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18003358f  mov     edx, 20Fh; void *
0x180033594  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033599  mov     ebx, eax
0x18003359b  jmp     short loc_180033521
0x18003359d  mov     [rbp+NumberOfBytesRead], 0
0x1800335a4  mov     edx, 4; uBytes
0x1800335a9  xor     ecx, ecx; uFlags
0x1800335ab  call    cs:__imp_LocalAlloc
0x1800335b1  mov     rdi, rax
0x1800335b4  test    rax, rax
0x1800335b7  jnz     short loc_18003360A
0x1800335b9  mov     rcx, [rbp+18h]; this
0x1800335bd  mov     edi, 8007000Eh
0x1800335c2  mov     r9d, edi; char *
0x1800335c5  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x1800335cc  mov     edx, 219h; void *
0x1800335d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800335d6  test    rbx, rbx
0x1800335d9  jz      short loc_1800335E4
0x1800335db  mov     rcx, rbx; hObject
0x1800335de  call    cs:__imp_CloseHandle
0x1800335e4  mov     rcx, [rbp+ppszPathOut]; hMem
0x1800335e8  test    rcx, rcx
0x1800335eb  jz      short loc_1800335F4
0x1800335ed  call    cs:__imp_LocalFree
0x1800335f3  nop
0x1800335f4  mov     rcx, [rbp+hMem]; hMem
0x1800335f8  test    rcx, rcx
0x1800335fb  jz      short loc_180033603
0x1800335fd  call    cs:__imp_LocalFree
0x180033603  mov     eax, edi
0x180033605  jmp     loc_1800336C7
0x18003360a  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x180033613  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180033617  mov     r8d, 4; nNumberOfBytesToRead
0x18003361d  mov     rdx, rdi; lpBuffer
0x180033620  mov     rcx, rbx; hFile
0x180033623  call    cs:__imp_ReadFile
0x180033629  test    eax, eax
0x18003362b  jnz     short loc_18003367E
0x18003362d  mov     edx, 21Fh; void *
0x180033632  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033639  mov     rcx, [rbp+18h]; this
0x18003363d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180033642  mov     esi, eax
0x180033644  mov     rcx, rdi; hMem
0x180033647  call    cs:__imp_LocalFree
0x18003364d  test    rbx, rbx
0x180033650  jz      short loc_18003365B
0x180033652  mov     rcx, rbx; hObject
0x180033655  call    cs:__imp_CloseHandle
0x18003365b  mov     rcx, [rbp+ppszPathOut]; hMem
0x18003365f  test    rcx, rcx
0x180033662  jz      short loc_18003366B
0x180033664  call    cs:__imp_LocalFree
0x18003366a  nop
0x18003366b  mov     rcx, [rbp+hMem]; hMem
0x18003366f  test    rcx, rcx
0x180033672  jz      short loc_18003367A
0x180033674  call    cs:__imp_LocalFree
0x18003367a  mov     eax, esi
0x18003367c  jmp     short loc_1800336C7
0x18003367e  cmp     [rbp+NumberOfBytesRead], 4
0x180033682  jz      short loc_18003368B
0x180033684  mov     edx, 223h
0x180033689  jmp     short loc_180033632
0x18003368b  mov     eax, [rdi]
0x18003368d  mov     [rsi], eax
0x18003368f  mov     rcx, rdi; hMem
0x180033692  call    cs:__imp_LocalFree
0x180033698  test    rbx, rbx
0x18003369b  jz      short loc_1800336A6
0x18003369d  mov     rcx, rbx; hObject
0x1800336a0  call    cs:__imp_CloseHandle
0x1800336a6  mov     rcx, [rbp+ppszPathOut]; hMem
0x1800336aa  test    rcx, rcx
0x1800336ad  jz      short loc_1800336B6
0x1800336af  call    cs:__imp_LocalFree
0x1800336b5  nop
0x1800336b6  mov     rcx, [rbp+hMem]; hMem
0x1800336ba  test    rcx, rcx
0x1800336bd  jz      short loc_1800336C5
0x1800336bf  call    cs:__imp_LocalFree
0x1800336c5  xor     eax, eax
0x1800336c7  mov     rbx, [rsp+50h+arg_8]
0x1800336cc  add     rsp, 50h
0x1800336d0  pop     rdi
0x1800336d1  pop     rsi
0x1800336d2  pop     rbp
0x1800336d3  retn
```
