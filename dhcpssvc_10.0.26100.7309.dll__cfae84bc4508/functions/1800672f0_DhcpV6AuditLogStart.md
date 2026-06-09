# DhcpV6AuditLogStart

- ea: `0x1800672f0`
- end: `0x180067605`
- name: `DhcpV6AuditLogStart`
- size: `789`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180051cfc`
- `0x1800670ec`
- `0x180067e24`

## callees

- `0x18000323c`
- `0x180004fb4`
- `0x1800055ec`
- `0x1800056c0`
- `0x1800059b4`
- `0x180025b98`
- `0x180062964`
- `0x1800672f0`
- `0x18008f540`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800673ae`
- `KERNEL32!HeapAlloc` at `0x1800673ae`
- `KERNEL32!WriteFile` at `0x1800675aa`
- `KERNEL32!WriteFile` at `0x1800675aa`
- `KERNEL32!FreeLibrary` at `0x1800675e2`
- `KERNEL32!FreeLibrary` at `0x1800675e2`
- `KERNEL32!FormatMessageW` at `0x180067544`
- `KERNEL32!FormatMessageW` at `0x180067544`
- `KERNEL32!GetLastError` at `0x180067457`
- `KERNEL32!GetLastError` at `0x180067457`
- `KERNEL32!LocalFree` at `0x1800675d3`
- `KERNEL32!LocalFree` at `0x1800675d3`
- `KERNEL32!HeapFree` at `0x180067352`
- `KERNEL32!HeapFree` at `0x1800674bc`
- `KERNEL32!HeapFree` at `0x1800675c2`
- `KERNEL32!HeapFree` at `0x180067352`
- `KERNEL32!HeapFree` at `0x1800674bc`
- `KERNEL32!HeapFree` at `0x1800675c2`
- `KERNEL32!CreateFileW` at `0x18006743f`
- `KERNEL32!CreateFileW` at `0x18006743f`
- `KERNEL32!SetFilePointer` at `0x1800674e4`
- `KERNEL32!SetFilePointer` at `0x1800674e4`
- `KERNEL32!LoadLibraryExW` at `0x1800674fc`
- `KERNEL32!LoadLibraryExW` at `0x1800674fc`
- `USER32!OemToCharBuffA` at `0x18006757e`
- `USER32!OemToCharBuffA` at `0x18006757e`

## string_xrefs

- `0x1800674f3`: `dhcpssvc.dll`

## pseudocode

```c
__int64 __fastcall DhcpV6AuditLogStart(__int64 a1, __int64 a2)
{
  LPVOID v2; // r8
  const wchar_t *v3; // r14
  __int64 String; // rax
  __int64 v5; // rdi
  const wchar_t *v6; // rbp
  __int64 v7; // rcx
  __int64 v8; // rax
  size_t v9; // rsi
  wchar_t *v10; // rax
  wchar_t *v11; // rbx
  __int64 result; // rax
  int v13; // ebp
  int dwCreationDisposition; // esi
  HANDLE FileW; // rax
  DWORD LastError; // edi
  HMODULE Library; // rsi
  CHAR *v18; // rax
  CHAR *v19; // rbx
  __int64 v20; // r8
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+8h] BYREF
  WCHAR *Buffer; // [rsp+78h] [rbp+10h] BYREF

  Buffer = 0;
  NumberOfBytesWritten = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids);
  v2 = DhcpV6AuditLogFileName;
  if ( DhcpV6AuditLogFileName )
    HeapFree(gDhcpHeap, 0, DhcpV6AuditLogFileName);
  v3 = DhcpV6AuditLogFilePath;
  String = GetString((unsigned int)(DhcpV6CurrentDay + 1176), a2, v2);
  v5 = -1;
  v6 = (const wchar_t *)String;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(String + 2 * v7) );
  v8 = -1;
  do
    ++v8;
  while ( v3[v8] );
  v9 = v7 + v8 + 4;
  v10 = (wchar_t *)HeapAlloc(gDhcpHeap, 8u, 2 * v9);
  v11 = v10;
  if ( v10 )
  {
    StringCchCopyW(v10, v9, v3);
    StringCchCatW(v11, v9, L"\\");
    StringCchCatW(v11, v9, v6);
    DhcpV6AuditLogFileName = v11;
    v13 = OpenExisting(v11);
    dwCreationDisposition = v13 != 0 ? 4 : 2;
    FileW = CreateFileW(v11, 0x40000000u, 1u, 0, dwCreationDisposition, 0x80u, 0);
    DhcpV6AuditLogHandle = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids,
          (_DWORD)v11,
          dwCreationDisposition,
          LastError);
      DhcpServerEventLog(1028, 1, LastError);
      HeapFree(gDhcpHeap, 0, v11);
      result = LastError;
      DhcpV6AuditLogFileName = 0;
    }
    else
    {
      SetFilePointer(FileW, 0, 0, 2u);
      Library = LoadLibraryExW(L"dhcpssvc.dll", 0, 0);
      if ( Library )
      {
        if ( !v13 && FormatMessageW(0x900u, Library, 0x4B3u, 0x400u, (LPWSTR)&Buffer, 1u, 0) )
        {
          v18 = (CHAR *)DhcpUnicodeToOem(Buffer);
          v19 = v18;
          if ( v18 )
          {
            v20 = -1;
            do
              ++v20;
            while ( v18[v20] );
            OemToCharBuffA(v18, v18, v20);
            do
              ++v5;
            while ( v19[v5] );
            WriteFile(DhcpV6AuditLogHandle, v19, v5, &NumberOfBytesWritten, 0);
            HeapFree(gDhcpHeap, 0, v19);
          }
          LocalFree(Buffer);
        }
        FreeLibrary(Library);
      }
      return 0;
    }
  }
  else
  {
    DhcpV6AuditLogFileName = 0;
    return 8;
  }
  return result;
}

```

## disassembly

```asm
0x1800672f0  mov     [rsp+arg_10], rbx
0x1800672f5  push    rbp
0x1800672f6  push    rsi
0x1800672f7  push    rdi
0x1800672f8  push    r14
0x1800672fa  push    r15
0x1800672fc  sub     rsp, 40h
0x180067300  xor     r15d, r15d
0x180067303  mov     [rsp+68h+Buffer], r15
0x180067308  mov     [rsp+68h+NumberOfBytesWritten], r15d
0x18006730d  mov     rcx, cs:WPP_GLOBAL_Control
0x180067314  lea     rax, WPP_GLOBAL_Control
0x18006731b  cmp     rcx, rax
0x18006731e  jz      short loc_18006733D
0x180067320  test    dword ptr [rcx+1Ch], 2000h
0x180067327  jz      short loc_18006733D
0x180067329  mov     rcx, [rcx+10h]
0x18006732d  lea     edx, [r15+0Ah]
0x180067331  lea     r8, WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids
0x180067338  call    WPP_SF_
0x18006733d  mov     r8, cs:DhcpV6AuditLogFileName; lpMem
0x180067344  test    r8, r8
0x180067347  jz      short loc_18006735E
0x180067349  mov     rcx, cs:gDhcpHeap; hHeap
0x180067350  xor     edx, edx; dwFlags
0x180067352  call    cs:__imp_HeapFree
0x180067359  nop     dword ptr [rax+rax+00h]
0x18006735e  mov     ecx, cs:DhcpV6CurrentDay
0x180067364  mov     r14, cs:DhcpV6AuditLogFilePath
0x18006736b  add     ecx, 498h
0x180067371  call    GetString
0x180067376  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006737a  mov     rbp, rax
0x18006737d  mov     rcx, rdi
0x180067380  inc     rcx
0x180067383  cmp     [rax+rcx*2], r15w
0x180067388  jnz     short loc_180067380
0x18006738a  mov     rax, rdi
0x18006738d  inc     rax
0x180067390  cmp     [r14+rax*2], r15w
0x180067395  jnz     short loc_18006738D
0x180067397  lea     rsi, [rax+4]
0x18006739b  mov     edx, 8; dwFlags
0x1800673a0  add     rsi, rcx
0x1800673a3  mov     rcx, cs:gDhcpHeap; hHeap
0x1800673aa  lea     r8, [rsi+rsi]; dwBytes
0x1800673ae  call    cs:__imp_HeapAlloc
0x1800673b5  nop     dword ptr [rax+rax+00h]
0x1800673ba  mov     rbx, rax
0x1800673bd  test    rax, rax
0x1800673c0  jnz     short loc_1800673D1
0x1800673c2  mov     cs:DhcpV6AuditLogFileName, r15
0x1800673c9  lea     eax, [rbx+8]
0x1800673cc  jmp     loc_1800675F0
0x1800673d1  mov     r8, r14; pszSrc
0x1800673d4  mov     rdx, rsi; cchDest
0x1800673d7  mov     rcx, rbx; pszDest
0x1800673da  call    StringCchCopyW
0x1800673df  lea     r8, pszSrc; "\\"
0x1800673e6  mov     rdx, rsi; cchDest
0x1800673e9  mov     rcx, rbx; pszDest
0x1800673ec  call    StringCchCatW
0x1800673f1  mov     r8, rbp; pszSrc
0x1800673f4  mov     rdx, rsi; cchDest
0x1800673f7  mov     rcx, rbx; pszDest
0x1800673fa  call    StringCchCatW
0x1800673ff  mov     rcx, rbx; lpFileName
0x180067402  mov     cs:DhcpV6AuditLogFileName, rbx
0x180067409  call    OpenExisting
0x18006740e  mov     ecx, eax
0x180067410  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x180067415  neg     ecx
0x180067417  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006741f  mov     edx, 40000000h; dwDesiredAccess
0x180067424  mov     rcx, rbx; lpFileName
0x180067427  sbb     esi, esi
0x180067429  mov     ebp, eax
0x18006742b  xor     r9d, r9d; lpSecurityAttributes
0x18006742e  and     esi, 2
0x180067431  add     esi, 2
0x180067434  mov     [rsp+68h+dwCreationDisposition], esi; dwCreationDisposition
0x180067438  lea     r14d, [r9+1]
0x18006743c  mov     r8d, r14d; dwShareMode
0x18006743f  call    cs:__imp_CreateFileW
0x180067446  nop     dword ptr [rax+rax+00h]
0x18006744b  mov     cs:DhcpV6AuditLogHandle, rax
0x180067452  cmp     rax, rdi
0x180067455  jnz     short loc_1800674D6
0x180067457  call    cs:__imp_GetLastError
0x18006745e  nop     dword ptr [rax+rax+00h]
0x180067463  mov     edi, eax
0x180067465  mov     rcx, cs:WPP_GLOBAL_Control
0x18006746c  lea     rax, WPP_GLOBAL_Control
0x180067473  cmp     rcx, rax
0x180067476  jz      short loc_1800674A0
0x180067478  test    dword ptr [rcx+1Ch], 2000h
0x18006747f  jz      short loc_1800674A0
0x180067481  mov     rcx, [rcx+10h]
0x180067485  lea     edx, [r14+0Ah]
0x180067489  mov     [rsp+68h+dwFlagsAndAttributes], edi
0x18006748d  lea     r8, WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids
0x180067494  mov     r9, rbx
0x180067497  mov     [rsp+68h+dwCreationDisposition], esi
0x18006749b  call    WPP_SF_Sdd
0x1800674a0  mov     r8d, edi
0x1800674a3  mov     edx, r14d
0x1800674a6  mov     ecx, 404h
0x1800674ab  call    DhcpServerEventLog
0x1800674b0  mov     rcx, cs:gDhcpHeap; hHeap
0x1800674b7  mov     r8, rbx; lpMem
0x1800674ba  xor     edx, edx; dwFlags
0x1800674bc  call    cs:__imp_HeapFree
0x1800674c3  nop     dword ptr [rax+rax+00h]
0x1800674c8  mov     eax, edi
0x1800674ca  mov     cs:DhcpV6AuditLogFileName, r15
0x1800674d1  jmp     loc_1800675F0
0x1800674d6  mov     r9d, 2; dwMoveMethod
0x1800674dc  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800674df  xor     edx, edx; lDistanceToMove
0x1800674e1  mov     rcx, rax; hFile
0x1800674e4  call    cs:__imp_SetFilePointer
0x1800674eb  nop     dword ptr [rax+rax+00h]
0x1800674f0  xor     r8d, r8d; dwFlags
0x1800674f3  lea     rcx, LibFileName; "dhcpssvc.dll"
0x1800674fa  xor     edx, edx; hFile
0x1800674fc  call    cs:__imp_LoadLibraryExW
0x180067503  nop     dword ptr [rax+rax+00h]
0x180067508  mov     rsi, rax
0x18006750b  test    rax, rax
0x18006750e  jz      loc_1800675EE
0x180067514  test    ebp, ebp
0x180067516  jnz     loc_1800675DF
0x18006751c  mov     [rsp+68h+hTemplateFile], r15; Arguments
0x180067521  lea     rax, [rsp+68h+Buffer]
0x180067526  mov     [rsp+68h+dwFlagsAndAttributes], r14d; nSize
0x18006752b  mov     r9d, 400h; dwLanguageId
0x180067531  mov     r8d, 4B3h; dwMessageId
0x180067537  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; lpBuffer
0x18006753c  mov     rdx, rsi; lpSource
0x18006753f  mov     ecx, 900h; dwFlags
0x180067544  call    cs:__imp_FormatMessageW
0x18006754b  nop     dword ptr [rax+rax+00h]
0x180067550  test    eax, eax
0x180067552  jz      loc_1800675DF
0x180067558  mov     rcx, [rsp+68h+Buffer]; SourceString
0x18006755d  xor     edx, edx
0x18006755f  call    DhcpUnicodeToOem
0x180067564  mov     rbx, rax
0x180067567  test    rax, rax
0x18006756a  jz      short loc_1800675CE
0x18006756c  mov     r8, rdi
0x18006756f  inc     r8; cchDstLength
0x180067572  cmp     [rax+r8], r15b
0x180067576  jnz     short loc_18006756F
0x180067578  mov     rdx, rbx; lpszDst
0x18006757b  mov     rcx, rbx; lpszSrc
0x18006757e  call    cs:__imp_OemToCharBuffA
0x180067585  nop     dword ptr [rax+rax+00h]
0x18006758a  inc     rdi
0x18006758d  cmp     [rbx+rdi], r15b
0x180067591  jnz     short loc_18006758A
0x180067593  mov     rcx, cs:DhcpV6AuditLogHandle; hFile
0x18006759a  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18006759f  mov     r8, rdi; nNumberOfBytesToWrite
0x1800675a2  mov     qword ptr [rsp+68h+dwCreationDisposition], r15; lpOverlapped
0x1800675a7  mov     rdx, rbx; lpBuffer
0x1800675aa  call    cs:__imp_WriteFile
0x1800675b1  nop     dword ptr [rax+rax+00h]
0x1800675b6  mov     rcx, cs:gDhcpHeap; hHeap
0x1800675bd  mov     r8, rbx; lpMem
0x1800675c0  xor     edx, edx; dwFlags
0x1800675c2  call    cs:__imp_HeapFree
0x1800675c9  nop     dword ptr [rax+rax+00h]
0x1800675ce  mov     rcx, [rsp+68h+Buffer]; hMem
0x1800675d3  call    cs:__imp_LocalFree
0x1800675da  nop     dword ptr [rax+rax+00h]
0x1800675df  mov     rcx, rsi; hLibModule
0x1800675e2  call    cs:__imp_FreeLibrary
0x1800675e9  nop     dword ptr [rax+rax+00h]
0x1800675ee  xor     eax, eax
0x1800675f0  mov     rbx, [rsp+68h+arg_10]
0x1800675f8  add     rsp, 40h
0x1800675fc  pop     r15
0x1800675fe  pop     r14
0x180067600  pop     rdi
0x180067601  pop     rsi
0x180067602  pop     rbp
0x180067603  retn
```
