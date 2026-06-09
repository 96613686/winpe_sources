# AuditLogStart

- ea: `0x180003548`
- end: `0x18000385b`
- name: `AuditLogStart`
- size: `787`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x1800038fc`
- `0x180004a5c`
- `0x180051cfc`

## callees

- `0x18000323c`
- `0x180003548`
- `0x180004fb4`
- `0x1800055ec`
- `0x1800056c0`
- `0x1800059b4`
- `0x180025b98`
- `0x180062964`
- `0x18008f540`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180003606`
- `KERNEL32!HeapAlloc` at `0x180003606`
- `KERNEL32!WriteFile` at `0x180003800`
- `KERNEL32!WriteFile` at `0x180003800`
- `KERNEL32!FreeLibrary` at `0x180003838`
- `KERNEL32!FreeLibrary` at `0x180003838`
- `KERNEL32!FormatMessageW` at `0x18000379a`
- `KERNEL32!FormatMessageW` at `0x18000379a`
- `KERNEL32!GetLastError` at `0x1800036af`
- `KERNEL32!GetLastError` at `0x1800036af`
- `KERNEL32!LocalFree` at `0x180003829`
- `KERNEL32!LocalFree` at `0x180003829`
- `KERNEL32!HeapFree` at `0x1800035aa`
- `KERNEL32!HeapFree` at `0x180003714`
- `KERNEL32!HeapFree` at `0x180003818`
- `KERNEL32!HeapFree` at `0x1800035aa`
- `KERNEL32!HeapFree` at `0x180003714`
- `KERNEL32!HeapFree` at `0x180003818`
- `KERNEL32!CreateFileW` at `0x180003697`
- `KERNEL32!CreateFileW` at `0x180003697`
- `KERNEL32!SetFilePointer` at `0x18000373c`
- `KERNEL32!SetFilePointer` at `0x18000373c`
- `KERNEL32!LoadLibraryExW` at `0x180003754`
- `KERNEL32!LoadLibraryExW` at `0x180003754`
- `USER32!OemToCharBuffA` at `0x1800037d4`
- `USER32!OemToCharBuffA` at `0x1800037d4`

## string_xrefs

- `0x18000374b`: `dhcpssvc.dll`

## pseudocode

```c
__int64 __fastcall AuditLogStart(__int64 a1, __int64 a2)
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids);
  v2 = AuditLogFileName;
  if ( AuditLogFileName )
    HeapFree(gDhcpHeap, 0, AuditLogFileName);
  v3 = AuditLogFilePath;
  String = GetString((unsigned int)(CurrentDay + 1091), a2, v2);
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
    AuditLogFileName = v11;
    v13 = OpenExisting(v11);
    dwCreationDisposition = v13 != 0 ? 4 : 2;
    FileW = CreateFileW(v11, 0x40000000u, 1u, 0, dwCreationDisposition, 0x80u, 0);
    AuditLogHandle = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)&WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids,
          (_DWORD)v11,
          dwCreationDisposition,
          LastError);
      DhcpServerEventLog(1028, 1, LastError);
      HeapFree(gDhcpHeap, 0, v11);
      result = LastError;
      AuditLogFileName = 0;
    }
    else
    {
      SetFilePointer(FileW, 0, 0, 2u);
      Library = LoadLibraryExW(L"dhcpssvc.dll", 0, 0);
      if ( Library )
      {
        if ( !v13 && FormatMessageW(0x900u, Library, 0x440u, 0x400u, (LPWSTR)&Buffer, 1u, 0) )
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
            WriteFile(AuditLogHandle, v19, v5, &NumberOfBytesWritten, 0);
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
    AuditLogFileName = 0;
    return 8;
  }
  return result;
}

```

## disassembly

```asm
0x180003548  mov     [rsp+arg_10], rbx
0x18000354d  push    rbp
0x18000354e  push    rsi
0x18000354f  push    rdi
0x180003550  push    r14
0x180003552  push    r15
0x180003554  sub     rsp, 40h
0x180003558  xor     r15d, r15d
0x18000355b  mov     [rsp+68h+Buffer], r15
0x180003560  mov     [rsp+68h+NumberOfBytesWritten], r15d
0x180003565  mov     rcx, cs:WPP_GLOBAL_Control
0x18000356c  lea     rax, WPP_GLOBAL_Control
0x180003573  cmp     rcx, rax
0x180003576  jz      short loc_180003595
0x180003578  test    dword ptr [rcx+1Ch], 2000h
0x18000357f  jz      short loc_180003595
0x180003581  mov     rcx, [rcx+10h]
0x180003585  lea     edx, [r15+0Bh]
0x180003589  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x180003590  call    WPP_SF_
0x180003595  mov     r8, cs:AuditLogFileName; lpMem
0x18000359c  test    r8, r8
0x18000359f  jz      short loc_1800035B6
0x1800035a1  mov     rcx, cs:gDhcpHeap; hHeap
0x1800035a8  xor     edx, edx; dwFlags
0x1800035aa  call    cs:__imp_HeapFree
0x1800035b1  nop     dword ptr [rax+rax+00h]
0x1800035b6  mov     ecx, cs:CurrentDay
0x1800035bc  mov     r14, cs:AuditLogFilePath
0x1800035c3  add     ecx, 443h
0x1800035c9  call    GetString
0x1800035ce  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800035d2  mov     rbp, rax
0x1800035d5  mov     rcx, rdi
0x1800035d8  inc     rcx
0x1800035db  cmp     [rax+rcx*2], r15w
0x1800035e0  jnz     short loc_1800035D8
0x1800035e2  mov     rax, rdi
0x1800035e5  inc     rax
0x1800035e8  cmp     [r14+rax*2], r15w
0x1800035ed  jnz     short loc_1800035E5
0x1800035ef  lea     rsi, [rax+4]
0x1800035f3  mov     edx, 8; dwFlags
0x1800035f8  add     rsi, rcx
0x1800035fb  mov     rcx, cs:gDhcpHeap; hHeap
0x180003602  lea     r8, [rsi+rsi]; dwBytes
0x180003606  call    cs:__imp_HeapAlloc
0x18000360d  nop     dword ptr [rax+rax+00h]
0x180003612  mov     rbx, rax
0x180003615  test    rax, rax
0x180003618  jnz     short loc_180003629
0x18000361a  mov     cs:AuditLogFileName, r15
0x180003621  lea     eax, [rbx+8]
0x180003624  jmp     loc_180003846
0x180003629  mov     r8, r14; pszSrc
0x18000362c  mov     rdx, rsi; cchDest
0x18000362f  mov     rcx, rbx; pszDest
0x180003632  call    StringCchCopyW
0x180003637  lea     r8, pszSrc; "\\"
0x18000363e  mov     rdx, rsi; cchDest
0x180003641  mov     rcx, rbx; pszDest
0x180003644  call    StringCchCatW
0x180003649  mov     r8, rbp; pszSrc
0x18000364c  mov     rdx, rsi; cchDest
0x18000364f  mov     rcx, rbx; pszDest
0x180003652  call    StringCchCatW
0x180003657  mov     rcx, rbx; lpFileName
0x18000365a  mov     cs:AuditLogFileName, rbx
0x180003661  call    OpenExisting
0x180003666  mov     ecx, eax
0x180003668  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x18000366d  neg     ecx
0x18000366f  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180003677  mov     edx, 40000000h; dwDesiredAccess
0x18000367c  mov     rcx, rbx; lpFileName
0x18000367f  sbb     esi, esi
0x180003681  mov     ebp, eax
0x180003683  xor     r9d, r9d; lpSecurityAttributes
0x180003686  and     esi, 2
0x180003689  add     esi, 2
0x18000368c  mov     [rsp+68h+dwCreationDisposition], esi; dwCreationDisposition
0x180003690  lea     r14d, [r9+1]
0x180003694  mov     r8d, r14d; dwShareMode
0x180003697  call    cs:__imp_CreateFileW
0x18000369e  nop     dword ptr [rax+rax+00h]
0x1800036a3  mov     cs:AuditLogHandle, rax
0x1800036aa  cmp     rax, rdi
0x1800036ad  jnz     short loc_18000372E
0x1800036af  call    cs:__imp_GetLastError
0x1800036b6  nop     dword ptr [rax+rax+00h]
0x1800036bb  mov     edi, eax
0x1800036bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036c4  lea     rax, WPP_GLOBAL_Control
0x1800036cb  cmp     rcx, rax
0x1800036ce  jz      short loc_1800036F8
0x1800036d0  test    dword ptr [rcx+1Ch], 2000h
0x1800036d7  jz      short loc_1800036F8
0x1800036d9  mov     rcx, [rcx+10h]
0x1800036dd  lea     edx, [r14+0Bh]
0x1800036e1  mov     [rsp+68h+dwFlagsAndAttributes], edi
0x1800036e5  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x1800036ec  mov     r9, rbx
0x1800036ef  mov     [rsp+68h+dwCreationDisposition], esi
0x1800036f3  call    WPP_SF_Sdd
0x1800036f8  mov     r8d, edi
0x1800036fb  mov     edx, r14d
0x1800036fe  mov     ecx, 404h
0x180003703  call    DhcpServerEventLog
0x180003708  mov     rcx, cs:gDhcpHeap; hHeap
0x18000370f  mov     r8, rbx; lpMem
0x180003712  xor     edx, edx; dwFlags
0x180003714  call    cs:__imp_HeapFree
0x18000371b  nop     dword ptr [rax+rax+00h]
0x180003720  mov     eax, edi
0x180003722  mov     cs:AuditLogFileName, r15
0x180003729  jmp     loc_180003846
0x18000372e  mov     r9d, 2; dwMoveMethod
0x180003734  xor     r8d, r8d; lpDistanceToMoveHigh
0x180003737  xor     edx, edx; lDistanceToMove
0x180003739  mov     rcx, rax; hFile
0x18000373c  call    cs:__imp_SetFilePointer
0x180003743  nop     dword ptr [rax+rax+00h]
0x180003748  xor     r8d, r8d; dwFlags
0x18000374b  lea     rcx, LibFileName; "dhcpssvc.dll"
0x180003752  xor     edx, edx; hFile
0x180003754  call    cs:__imp_LoadLibraryExW
0x18000375b  nop     dword ptr [rax+rax+00h]
0x180003760  mov     rsi, rax
0x180003763  test    rax, rax
0x180003766  jz      loc_180003844
0x18000376c  test    ebp, ebp
0x18000376e  jnz     loc_180003835
0x180003774  mov     r9d, 400h; dwLanguageId
0x18000377a  mov     [rsp+68h+hTemplateFile], r15; Arguments
0x18000377f  lea     rax, [rsp+68h+Buffer]
0x180003784  mov     [rsp+68h+dwFlagsAndAttributes], r14d; nSize
0x180003789  mov     rdx, rsi; lpSource
0x18000378c  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; lpBuffer
0x180003791  mov     ecx, 900h; dwFlags
0x180003796  lea     r8d, [r9+40h]; dwMessageId
0x18000379a  call    cs:__imp_FormatMessageW
0x1800037a1  nop     dword ptr [rax+rax+00h]
0x1800037a6  test    eax, eax
0x1800037a8  jz      loc_180003835
0x1800037ae  mov     rcx, [rsp+68h+Buffer]; SourceString
0x1800037b3  xor     edx, edx
0x1800037b5  call    DhcpUnicodeToOem
0x1800037ba  mov     rbx, rax
0x1800037bd  test    rax, rax
0x1800037c0  jz      short loc_180003824
0x1800037c2  mov     r8, rdi
0x1800037c5  inc     r8; cchDstLength
0x1800037c8  cmp     [rax+r8], r15b
0x1800037cc  jnz     short loc_1800037C5
0x1800037ce  mov     rdx, rbx; lpszDst
0x1800037d1  mov     rcx, rbx; lpszSrc
0x1800037d4  call    cs:__imp_OemToCharBuffA
0x1800037db  nop     dword ptr [rax+rax+00h]
0x1800037e0  inc     rdi
0x1800037e3  cmp     [rbx+rdi], r15b
0x1800037e7  jnz     short loc_1800037E0
0x1800037e9  mov     rcx, cs:AuditLogHandle; hFile
0x1800037f0  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800037f5  mov     r8, rdi; nNumberOfBytesToWrite
0x1800037f8  mov     qword ptr [rsp+68h+dwCreationDisposition], r15; lpOverlapped
0x1800037fd  mov     rdx, rbx; lpBuffer
0x180003800  call    cs:__imp_WriteFile
0x180003807  nop     dword ptr [rax+rax+00h]
0x18000380c  mov     rcx, cs:gDhcpHeap; hHeap
0x180003813  mov     r8, rbx; lpMem
0x180003816  xor     edx, edx; dwFlags
0x180003818  call    cs:__imp_HeapFree
0x18000381f  nop     dword ptr [rax+rax+00h]
0x180003824  mov     rcx, [rsp+68h+Buffer]; hMem
0x180003829  call    cs:__imp_LocalFree
0x180003830  nop     dword ptr [rax+rax+00h]
0x180003835  mov     rcx, rsi; hLibModule
0x180003838  call    cs:__imp_FreeLibrary
0x18000383f  nop     dword ptr [rax+rax+00h]
0x180003844  xor     eax, eax
0x180003846  mov     rbx, [rsp+68h+arg_10]
0x18000384e  add     rsp, 40h
0x180003852  pop     r15
0x180003854  pop     r14
0x180003856  pop     rdi
0x180003857  pop     rsi
0x180003858  pop     rbp
0x180003859  retn
```
