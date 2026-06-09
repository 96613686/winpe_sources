# DhcpV6AuditLogStart

- ea: `0x180067094`
- end: `0x1800673aa`
- name: `DhcpV6AuditLogStart`
- size: `790`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180051a00`
- `0x180066e90`
- `0x180067bd0`

## callees

- `0x180003228`
- `0x180004fb4`
- `0x1800055e8`
- `0x1800056ac`
- `0x1800059a4`
- `0x1800250e8`
- `0x1800626dc`
- `0x180067094`
- `0x18008f6d8`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180067153`
- `KERNEL32!HeapAlloc` at `0x180067153`
- `KERNEL32!WriteFile` at `0x18006734f`
- `KERNEL32!WriteFile` at `0x18006734f`
- `KERNEL32!FreeLibrary` at `0x180067387`
- `KERNEL32!FreeLibrary` at `0x180067387`
- `KERNEL32!GetLastError` at `0x1800671fc`
- `KERNEL32!GetLastError` at `0x1800671fc`
- `KERNEL32!LocalFree` at `0x180067378`
- `KERNEL32!LocalFree` at `0x180067378`
- `KERNEL32!HeapFree` at `0x1800670f6`
- `KERNEL32!HeapFree` at `0x180067261`
- `KERNEL32!HeapFree` at `0x180067367`
- `KERNEL32!HeapFree` at `0x1800670f6`
- `KERNEL32!HeapFree` at `0x180067261`
- `KERNEL32!HeapFree` at `0x180067367`
- `KERNEL32!CreateFileW` at `0x1800671e4`
- `KERNEL32!CreateFileW` at `0x1800671e4`
- `KERNEL32!SetFilePointer` at `0x180067289`
- `KERNEL32!SetFilePointer` at `0x180067289`
- `KERNEL32!LoadLibraryExW` at `0x1800672a1`
- `KERNEL32!LoadLibraryExW` at `0x1800672a1`
- `KERNEL32!FormatMessageW` at `0x1800672e9`
- `KERNEL32!FormatMessageW` at `0x1800672e9`
- `USER32!OemToCharBuffA` at `0x180067323`
- `USER32!OemToCharBuffA` at `0x180067323`

## string_xrefs

- `0x180067298`: `dhcpssvc.dll`

## pseudocode

```c
__int64 DhcpV6AuditLogStart()
{
  const wchar_t *v0; // rbp
  __int64 v1; // rdi
  const wchar_t *String; // r14
  __int64 v3; // rcx
  __int64 v4; // rax
  size_t v5; // rsi
  wchar_t *v6; // rax
  wchar_t *v7; // rbx
  __int64 result; // rax
  int v9; // ebp
  int dwCreationDisposition; // esi
  HANDLE FileW; // rax
  DWORD LastError; // edi
  HMODULE Library; // rsi
  CHAR *v14; // rax
  CHAR *v15; // rbx
  __int64 v16; // r8
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+8h] BYREF
  WCHAR *Buffer; // [rsp+78h] [rbp+10h] BYREF

  Buffer = 0;
  NumberOfBytesWritten = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids);
  if ( DhcpV6AuditLogFileName )
    HeapFree(gDhcpHeap, 0, DhcpV6AuditLogFileName);
  v0 = DhcpV6AuditLogFilePath;
  v1 = -1;
  String = (const wchar_t *)GetString((unsigned int)(DhcpV6CurrentDay + 1176));
  v3 = -1;
  do
    ++v3;
  while ( v0[v3] );
  v4 = -1;
  do
    ++v4;
  while ( String[v4] );
  v5 = v4 + v3 + 4;
  v6 = (wchar_t *)HeapAlloc(gDhcpHeap, 8u, 2 * v5);
  v7 = v6;
  if ( v6 )
  {
    StringCchCopyW(v6, v5, v0);
    StringCchCatW(v7, v5, L"\\");
    StringCchCatW(v7, v5, String);
    DhcpV6AuditLogFileName = v7;
    v9 = OpenExisting(v7);
    dwCreationDisposition = v9 != 0 ? 4 : 2;
    FileW = CreateFileW(v7, 0x40000000u, 1u, 0, dwCreationDisposition, 0x80u, 0);
    DhcpV6AuditLogHandle = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids,
          (_DWORD)v7,
          dwCreationDisposition,
          LastError);
      DhcpServerEventLog(1028, 1, LastError);
      HeapFree(gDhcpHeap, 0, v7);
      result = LastError;
      DhcpV6AuditLogFileName = 0;
    }
    else
    {
      SetFilePointer(FileW, 0, 0, 2u);
      Library = LoadLibraryExW(L"dhcpssvc.dll", 0, 0);
      if ( Library )
      {
        if ( !v9 && FormatMessageW(0x900u, Library, 0x4B3u, 0x400u, (LPWSTR)&Buffer, 1u, 0) )
        {
          v14 = (CHAR *)DhcpUnicodeToOem(Buffer);
          v15 = v14;
          if ( v14 )
          {
            v16 = -1;
            do
              ++v16;
            while ( v14[v16] );
            OemToCharBuffA(v14, v14, v16);
            do
              ++v1;
            while ( v15[v1] );
            WriteFile(DhcpV6AuditLogHandle, v15, v1, &NumberOfBytesWritten, 0);
            HeapFree(gDhcpHeap, 0, v15);
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
0x180067094  mov     [rsp+arg_10], rbx
0x180067099  push    rbp
0x18006709a  push    rsi
0x18006709b  push    rdi
0x18006709c  push    r14
0x18006709e  push    r15
0x1800670a0  sub     rsp, 40h
0x1800670a4  xor     r15d, r15d
0x1800670a7  mov     [rsp+68h+Buffer], r15
0x1800670ac  mov     [rsp+68h+NumberOfBytesWritten], r15d
0x1800670b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800670b8  lea     rax, WPP_GLOBAL_Control
0x1800670bf  cmp     rcx, rax
0x1800670c2  jz      short loc_1800670E1
0x1800670c4  test    dword ptr [rcx+1Ch], 2000h
0x1800670cb  jz      short loc_1800670E1
0x1800670cd  mov     rcx, [rcx+10h]
0x1800670d1  lea     edx, [r15+0Ah]
0x1800670d5  lea     r8, WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids
0x1800670dc  call    WPP_SF_
0x1800670e1  mov     r8, cs:DhcpV6AuditLogFileName; lpMem
0x1800670e8  test    r8, r8
0x1800670eb  jz      short loc_180067102
0x1800670ed  mov     rcx, cs:gDhcpHeap; hHeap
0x1800670f4  xor     edx, edx; dwFlags
0x1800670f6  call    cs:__imp_HeapFree
0x1800670fd  nop     dword ptr [rax+rax+00h]
0x180067102  mov     ecx, cs:DhcpV6CurrentDay
0x180067108  mov     rbp, cs:DhcpV6AuditLogFilePath
0x18006710f  add     ecx, 498h
0x180067115  call    GetString
0x18006711a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006711e  mov     r14, rax
0x180067121  mov     rcx, rdi
0x180067124  inc     rcx
0x180067127  cmp     [rbp+rcx*2+0], r15w
0x18006712d  jnz     short loc_180067124
0x18006712f  mov     rax, rdi
0x180067132  inc     rax
0x180067135  cmp     [r14+rax*2], r15w
0x18006713a  jnz     short loc_180067132
0x18006713c  lea     rsi, [rcx+4]
0x180067140  mov     edx, 8; dwFlags
0x180067145  mov     rcx, cs:gDhcpHeap; hHeap
0x18006714c  add     rsi, rax
0x18006714f  lea     r8, [rsi+rsi]; dwBytes
0x180067153  call    cs:__imp_HeapAlloc
0x18006715a  nop     dword ptr [rax+rax+00h]
0x18006715f  mov     rbx, rax
0x180067162  test    rax, rax
0x180067165  jnz     short loc_180067176
0x180067167  mov     cs:DhcpV6AuditLogFileName, r15
0x18006716e  lea     eax, [rbx+8]
0x180067171  jmp     loc_180067395
0x180067176  mov     r8, rbp; pszSrc
0x180067179  mov     rdx, rsi; cchDest
0x18006717c  mov     rcx, rbx; pszDest
0x18006717f  call    StringCchCopyW
0x180067184  lea     r8, pszSrc; "\\"
0x18006718b  mov     rdx, rsi; cchDest
0x18006718e  mov     rcx, rbx; pszDest
0x180067191  call    StringCchCatW
0x180067196  mov     r8, r14; pszSrc
0x180067199  mov     rdx, rsi; cchDest
0x18006719c  mov     rcx, rbx; pszDest
0x18006719f  call    StringCchCatW
0x1800671a4  mov     rcx, rbx; lpFileName
0x1800671a7  mov     cs:DhcpV6AuditLogFileName, rbx
0x1800671ae  call    OpenExisting
0x1800671b3  mov     ecx, eax
0x1800671b5  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x1800671ba  neg     ecx
0x1800671bc  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800671c4  mov     edx, 40000000h; dwDesiredAccess
0x1800671c9  mov     rcx, rbx; lpFileName
0x1800671cc  sbb     esi, esi
0x1800671ce  mov     ebp, eax
0x1800671d0  xor     r9d, r9d; lpSecurityAttributes
0x1800671d3  and     esi, 2
0x1800671d6  add     esi, 2
0x1800671d9  mov     [rsp+68h+dwCreationDisposition], esi; dwCreationDisposition
0x1800671dd  lea     r14d, [r9+1]
0x1800671e1  mov     r8d, r14d; dwShareMode
0x1800671e4  call    cs:__imp_CreateFileW
0x1800671eb  nop     dword ptr [rax+rax+00h]
0x1800671f0  mov     cs:DhcpV6AuditLogHandle, rax
0x1800671f7  cmp     rax, rdi
0x1800671fa  jnz     short loc_18006727B
0x1800671fc  call    cs:__imp_GetLastError
0x180067203  nop     dword ptr [rax+rax+00h]
0x180067208  mov     edi, eax
0x18006720a  mov     rcx, cs:WPP_GLOBAL_Control
0x180067211  lea     rax, WPP_GLOBAL_Control
0x180067218  cmp     rcx, rax
0x18006721b  jz      short loc_180067245
0x18006721d  test    dword ptr [rcx+1Ch], 2000h
0x180067224  jz      short loc_180067245
0x180067226  mov     rcx, [rcx+10h]
0x18006722a  lea     edx, [r14+0Ah]
0x18006722e  mov     [rsp+68h+dwFlagsAndAttributes], edi
0x180067232  lea     r8, WPP_e474196d152a3d3be2d8ec37988be4cf_Traceguids
0x180067239  mov     r9, rbx
0x18006723c  mov     [rsp+68h+dwCreationDisposition], esi
0x180067240  call    WPP_SF_Sdd
0x180067245  mov     r8d, edi
0x180067248  mov     edx, r14d
0x18006724b  mov     ecx, 404h
0x180067250  call    DhcpServerEventLog
0x180067255  mov     rcx, cs:gDhcpHeap; hHeap
0x18006725c  mov     r8, rbx; lpMem
0x18006725f  xor     edx, edx; dwFlags
0x180067261  call    cs:__imp_HeapFree
0x180067268  nop     dword ptr [rax+rax+00h]
0x18006726d  mov     eax, edi
0x18006726f  mov     cs:DhcpV6AuditLogFileName, r15
0x180067276  jmp     loc_180067395
0x18006727b  mov     r9d, 2; dwMoveMethod
0x180067281  xor     r8d, r8d; lpDistanceToMoveHigh
0x180067284  xor     edx, edx; lDistanceToMove
0x180067286  mov     rcx, rax; hFile
0x180067289  call    cs:__imp_SetFilePointer
0x180067290  nop     dword ptr [rax+rax+00h]
0x180067295  xor     r8d, r8d; dwFlags
0x180067298  lea     rcx, LibFileName; "dhcpssvc.dll"
0x18006729f  xor     edx, edx; hFile
0x1800672a1  call    cs:__imp_LoadLibraryExW
0x1800672a8  nop     dword ptr [rax+rax+00h]
0x1800672ad  mov     rsi, rax
0x1800672b0  test    rax, rax
0x1800672b3  jz      loc_180067393
0x1800672b9  test    ebp, ebp
0x1800672bb  jnz     loc_180067384
0x1800672c1  mov     [rsp+68h+hTemplateFile], r15; Arguments
0x1800672c6  lea     rax, [rsp+68h+Buffer]
0x1800672cb  mov     [rsp+68h+dwFlagsAndAttributes], r14d; nSize
0x1800672d0  mov     r9d, 400h; dwLanguageId
0x1800672d6  mov     r8d, 4B3h; dwMessageId
0x1800672dc  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; lpBuffer
0x1800672e1  mov     rdx, rsi; lpSource
0x1800672e4  mov     ecx, 900h; dwFlags
0x1800672e9  call    cs:__imp_FormatMessageW
0x1800672f0  nop     dword ptr [rax+rax+00h]
0x1800672f5  test    eax, eax
0x1800672f7  jz      loc_180067384
0x1800672fd  mov     rcx, [rsp+68h+Buffer]; SourceString
0x180067302  xor     edx, edx
0x180067304  call    DhcpUnicodeToOem
0x180067309  mov     rbx, rax
0x18006730c  test    rax, rax
0x18006730f  jz      short loc_180067373
0x180067311  mov     r8, rdi
0x180067314  inc     r8; cchDstLength
0x180067317  cmp     [rax+r8], r15b
0x18006731b  jnz     short loc_180067314
0x18006731d  mov     rdx, rbx; lpszDst
0x180067320  mov     rcx, rbx; lpszSrc
0x180067323  call    cs:__imp_OemToCharBuffA
0x18006732a  nop     dword ptr [rax+rax+00h]
0x18006732f  inc     rdi
0x180067332  cmp     [rbx+rdi], r15b
0x180067336  jnz     short loc_18006732F
0x180067338  mov     rcx, cs:DhcpV6AuditLogHandle; hFile
0x18006733f  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180067344  mov     r8d, edi; nNumberOfBytesToWrite
0x180067347  mov     qword ptr [rsp+68h+dwCreationDisposition], r15; lpOverlapped
0x18006734c  mov     rdx, rbx; lpBuffer
0x18006734f  call    cs:__imp_WriteFile
0x180067356  nop     dword ptr [rax+rax+00h]
0x18006735b  mov     rcx, cs:gDhcpHeap; hHeap
0x180067362  mov     r8, rbx; lpMem
0x180067365  xor     edx, edx; dwFlags
0x180067367  call    cs:__imp_HeapFree
0x18006736e  nop     dword ptr [rax+rax+00h]
0x180067373  mov     rcx, [rsp+68h+Buffer]; hMem
0x180067378  call    cs:__imp_LocalFree
0x18006737f  nop     dword ptr [rax+rax+00h]
0x180067384  mov     rcx, rsi; hLibModule
0x180067387  call    cs:__imp_FreeLibrary
0x18006738e  nop     dword ptr [rax+rax+00h]
0x180067393  xor     eax, eax
0x180067395  mov     rbx, [rsp+68h+arg_10]
0x18006739d  add     rsp, 40h
0x1800673a1  pop     r15
0x1800673a3  pop     r14
0x1800673a5  pop     rdi
0x1800673a6  pop     rsi
0x1800673a7  pop     rbp
0x1800673a8  retn
```
