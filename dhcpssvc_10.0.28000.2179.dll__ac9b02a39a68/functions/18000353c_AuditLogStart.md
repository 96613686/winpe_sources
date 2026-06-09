# AuditLogStart

- ea: `0x18000353c`
- end: `0x180003850`
- name: `AuditLogStart`
- size: `788`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x1800038f0`
- `0x180004a5c`
- `0x180051a00`

## callees

- `0x180003228`
- `0x18000353c`
- `0x180004fb4`
- `0x1800055e8`
- `0x1800056ac`
- `0x1800059a4`
- `0x1800250e8`
- `0x1800626dc`
- `0x18008f6d8`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800035fb`
- `KERNEL32!HeapAlloc` at `0x1800035fb`
- `KERNEL32!WriteFile` at `0x1800037f5`
- `KERNEL32!WriteFile` at `0x1800037f5`
- `KERNEL32!FreeLibrary` at `0x18000382d`
- `KERNEL32!FreeLibrary` at `0x18000382d`
- `KERNEL32!GetLastError` at `0x1800036a4`
- `KERNEL32!GetLastError` at `0x1800036a4`
- `KERNEL32!LocalFree` at `0x18000381e`
- `KERNEL32!LocalFree` at `0x18000381e`
- `KERNEL32!HeapFree` at `0x18000359e`
- `KERNEL32!HeapFree` at `0x180003709`
- `KERNEL32!HeapFree` at `0x18000380d`
- `KERNEL32!HeapFree` at `0x18000359e`
- `KERNEL32!HeapFree` at `0x180003709`
- `KERNEL32!HeapFree` at `0x18000380d`
- `KERNEL32!CreateFileW` at `0x18000368c`
- `KERNEL32!CreateFileW` at `0x18000368c`
- `KERNEL32!SetFilePointer` at `0x180003731`
- `KERNEL32!SetFilePointer` at `0x180003731`
- `KERNEL32!LoadLibraryExW` at `0x180003749`
- `KERNEL32!LoadLibraryExW` at `0x180003749`
- `KERNEL32!FormatMessageW` at `0x18000378f`
- `KERNEL32!FormatMessageW` at `0x18000378f`
- `USER32!OemToCharBuffA` at `0x1800037c9`
- `USER32!OemToCharBuffA` at `0x1800037c9`

## string_xrefs

- `0x180003740`: `dhcpssvc.dll`

## pseudocode

```c
__int64 AuditLogStart()
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids);
  if ( AuditLogFileName )
    HeapFree(gDhcpHeap, 0, AuditLogFileName);
  v0 = AuditLogFilePath;
  v1 = -1;
  String = (const wchar_t *)GetString((unsigned int)(CurrentDay + 1091));
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
    AuditLogFileName = v7;
    v9 = OpenExisting(v7);
    dwCreationDisposition = v9 != 0 ? 4 : 2;
    FileW = CreateFileW(v7, 0x40000000u, 1u, 0, dwCreationDisposition, 0x80u, 0);
    AuditLogHandle = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
        WPP_SF_Sdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)&WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids,
          (_DWORD)v7,
          dwCreationDisposition,
          LastError);
      DhcpServerEventLog(1028, 1, LastError);
      HeapFree(gDhcpHeap, 0, v7);
      result = LastError;
      AuditLogFileName = 0;
    }
    else
    {
      SetFilePointer(FileW, 0, 0, 2u);
      Library = LoadLibraryExW(L"dhcpssvc.dll", 0, 0);
      if ( Library )
      {
        if ( !v9 && FormatMessageW(0x900u, Library, 0x440u, 0x400u, (LPWSTR)&Buffer, 1u, 0) )
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
            WriteFile(AuditLogHandle, v15, v1, &NumberOfBytesWritten, 0);
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
    AuditLogFileName = 0;
    return 8;
  }
  return result;
}

```

## disassembly

```asm
0x18000353c  mov     [rsp+arg_10], rbx
0x180003541  push    rbp
0x180003542  push    rsi
0x180003543  push    rdi
0x180003544  push    r14
0x180003546  push    r15
0x180003548  sub     rsp, 40h
0x18000354c  xor     r15d, r15d
0x18000354f  mov     [rsp+68h+Buffer], r15
0x180003554  mov     [rsp+68h+NumberOfBytesWritten], r15d
0x180003559  mov     rcx, cs:WPP_GLOBAL_Control
0x180003560  lea     rax, WPP_GLOBAL_Control
0x180003567  cmp     rcx, rax
0x18000356a  jz      short loc_180003589
0x18000356c  test    dword ptr [rcx+1Ch], 2000h
0x180003573  jz      short loc_180003589
0x180003575  mov     rcx, [rcx+10h]
0x180003579  lea     edx, [r15+0Bh]
0x18000357d  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x180003584  call    WPP_SF_
0x180003589  mov     r8, cs:AuditLogFileName; lpMem
0x180003590  test    r8, r8
0x180003593  jz      short loc_1800035AA
0x180003595  mov     rcx, cs:gDhcpHeap; hHeap
0x18000359c  xor     edx, edx; dwFlags
0x18000359e  call    cs:__imp_HeapFree
0x1800035a5  nop     dword ptr [rax+rax+00h]
0x1800035aa  mov     ecx, cs:CurrentDay
0x1800035b0  mov     rbp, cs:AuditLogFilePath
0x1800035b7  add     ecx, 443h
0x1800035bd  call    GetString
0x1800035c2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800035c6  mov     r14, rax
0x1800035c9  mov     rcx, rdi
0x1800035cc  inc     rcx
0x1800035cf  cmp     [rbp+rcx*2+0], r15w
0x1800035d5  jnz     short loc_1800035CC
0x1800035d7  mov     rax, rdi
0x1800035da  inc     rax
0x1800035dd  cmp     [r14+rax*2], r15w
0x1800035e2  jnz     short loc_1800035DA
0x1800035e4  lea     rsi, [rcx+4]
0x1800035e8  mov     edx, 8; dwFlags
0x1800035ed  mov     rcx, cs:gDhcpHeap; hHeap
0x1800035f4  add     rsi, rax
0x1800035f7  lea     r8, [rsi+rsi]; dwBytes
0x1800035fb  call    cs:__imp_HeapAlloc
0x180003602  nop     dword ptr [rax+rax+00h]
0x180003607  mov     rbx, rax
0x18000360a  test    rax, rax
0x18000360d  jnz     short loc_18000361E
0x18000360f  mov     cs:AuditLogFileName, r15
0x180003616  lea     eax, [rbx+8]
0x180003619  jmp     loc_18000383B
0x18000361e  mov     r8, rbp; pszSrc
0x180003621  mov     rdx, rsi; cchDest
0x180003624  mov     rcx, rbx; pszDest
0x180003627  call    StringCchCopyW
0x18000362c  lea     r8, pszSrc; "\\"
0x180003633  mov     rdx, rsi; cchDest
0x180003636  mov     rcx, rbx; pszDest
0x180003639  call    StringCchCatW
0x18000363e  mov     r8, r14; pszSrc
0x180003641  mov     rdx, rsi; cchDest
0x180003644  mov     rcx, rbx; pszDest
0x180003647  call    StringCchCatW
0x18000364c  mov     rcx, rbx; lpFileName
0x18000364f  mov     cs:AuditLogFileName, rbx
0x180003656  call    OpenExisting
0x18000365b  mov     ecx, eax
0x18000365d  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x180003662  neg     ecx
0x180003664  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000366c  mov     edx, 40000000h; dwDesiredAccess
0x180003671  mov     rcx, rbx; lpFileName
0x180003674  sbb     esi, esi
0x180003676  mov     ebp, eax
0x180003678  xor     r9d, r9d; lpSecurityAttributes
0x18000367b  and     esi, 2
0x18000367e  add     esi, 2
0x180003681  mov     [rsp+68h+dwCreationDisposition], esi; dwCreationDisposition
0x180003685  lea     r14d, [r9+1]
0x180003689  mov     r8d, r14d; dwShareMode
0x18000368c  call    cs:__imp_CreateFileW
0x180003693  nop     dword ptr [rax+rax+00h]
0x180003698  mov     cs:AuditLogHandle, rax
0x18000369f  cmp     rax, rdi
0x1800036a2  jnz     short loc_180003723
0x1800036a4  call    cs:__imp_GetLastError
0x1800036ab  nop     dword ptr [rax+rax+00h]
0x1800036b0  mov     edi, eax
0x1800036b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036b9  lea     rax, WPP_GLOBAL_Control
0x1800036c0  cmp     rcx, rax
0x1800036c3  jz      short loc_1800036ED
0x1800036c5  test    dword ptr [rcx+1Ch], 2000h
0x1800036cc  jz      short loc_1800036ED
0x1800036ce  mov     rcx, [rcx+10h]
0x1800036d2  lea     edx, [r14+0Bh]
0x1800036d6  mov     [rsp+68h+dwFlagsAndAttributes], edi
0x1800036da  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x1800036e1  mov     r9, rbx
0x1800036e4  mov     [rsp+68h+dwCreationDisposition], esi
0x1800036e8  call    WPP_SF_Sdd
0x1800036ed  mov     r8d, edi
0x1800036f0  mov     edx, r14d
0x1800036f3  mov     ecx, 404h
0x1800036f8  call    DhcpServerEventLog
0x1800036fd  mov     rcx, cs:gDhcpHeap; hHeap
0x180003704  mov     r8, rbx; lpMem
0x180003707  xor     edx, edx; dwFlags
0x180003709  call    cs:__imp_HeapFree
0x180003710  nop     dword ptr [rax+rax+00h]
0x180003715  mov     eax, edi
0x180003717  mov     cs:AuditLogFileName, r15
0x18000371e  jmp     loc_18000383B
0x180003723  mov     r9d, 2; dwMoveMethod
0x180003729  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000372c  xor     edx, edx; lDistanceToMove
0x18000372e  mov     rcx, rax; hFile
0x180003731  call    cs:__imp_SetFilePointer
0x180003738  nop     dword ptr [rax+rax+00h]
0x18000373d  xor     r8d, r8d; dwFlags
0x180003740  lea     rcx, LibFileName; "dhcpssvc.dll"
0x180003747  xor     edx, edx; hFile
0x180003749  call    cs:__imp_LoadLibraryExW
0x180003750  nop     dword ptr [rax+rax+00h]
0x180003755  mov     rsi, rax
0x180003758  test    rax, rax
0x18000375b  jz      loc_180003839
0x180003761  test    ebp, ebp
0x180003763  jnz     loc_18000382A
0x180003769  mov     r9d, 400h; dwLanguageId
0x18000376f  mov     [rsp+68h+hTemplateFile], r15; Arguments
0x180003774  lea     rax, [rsp+68h+Buffer]
0x180003779  mov     [rsp+68h+dwFlagsAndAttributes], r14d; nSize
0x18000377e  mov     rdx, rsi; lpSource
0x180003781  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; lpBuffer
0x180003786  mov     ecx, 900h; dwFlags
0x18000378b  lea     r8d, [r9+40h]; dwMessageId
0x18000378f  call    cs:__imp_FormatMessageW
0x180003796  nop     dword ptr [rax+rax+00h]
0x18000379b  test    eax, eax
0x18000379d  jz      loc_18000382A
0x1800037a3  mov     rcx, [rsp+68h+Buffer]; SourceString
0x1800037a8  xor     edx, edx
0x1800037aa  call    DhcpUnicodeToOem
0x1800037af  mov     rbx, rax
0x1800037b2  test    rax, rax
0x1800037b5  jz      short loc_180003819
0x1800037b7  mov     r8, rdi
0x1800037ba  inc     r8; cchDstLength
0x1800037bd  cmp     [rax+r8], r15b
0x1800037c1  jnz     short loc_1800037BA
0x1800037c3  mov     rdx, rbx; lpszDst
0x1800037c6  mov     rcx, rbx; lpszSrc
0x1800037c9  call    cs:__imp_OemToCharBuffA
0x1800037d0  nop     dword ptr [rax+rax+00h]
0x1800037d5  inc     rdi
0x1800037d8  cmp     [rbx+rdi], r15b
0x1800037dc  jnz     short loc_1800037D5
0x1800037de  mov     rcx, cs:AuditLogHandle; hFile
0x1800037e5  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800037ea  mov     r8d, edi; nNumberOfBytesToWrite
0x1800037ed  mov     qword ptr [rsp+68h+dwCreationDisposition], r15; lpOverlapped
0x1800037f2  mov     rdx, rbx; lpBuffer
0x1800037f5  call    cs:__imp_WriteFile
0x1800037fc  nop     dword ptr [rax+rax+00h]
0x180003801  mov     rcx, cs:gDhcpHeap; hHeap
0x180003808  mov     r8, rbx; lpMem
0x18000380b  xor     edx, edx; dwFlags
0x18000380d  call    cs:__imp_HeapFree
0x180003814  nop     dword ptr [rax+rax+00h]
0x180003819  mov     rcx, [rsp+68h+Buffer]; hMem
0x18000381e  call    cs:__imp_LocalFree
0x180003825  nop     dword ptr [rax+rax+00h]
0x18000382a  mov     rcx, rsi; hLibModule
0x18000382d  call    cs:__imp_FreeLibrary
0x180003834  nop     dword ptr [rax+rax+00h]
0x180003839  xor     eax, eax
0x18000383b  mov     rbx, [rsp+68h+arg_10]
0x180003843  add     rsp, 40h
0x180003847  pop     r15
0x180003849  pop     r14
0x18000384b  pop     rdi
0x18000384c  pop     rsi
0x18000384d  pop     rbp
0x18000384e  retn
```
