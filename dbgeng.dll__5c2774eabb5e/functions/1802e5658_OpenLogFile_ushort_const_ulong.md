# OpenLogFile(ushort const *,ulong)

- ea: `0x1802e5658`
- end: `0x1802e57c6`
- name: `?OpenLogFile@@YAXPEBGK@Z`
- size: `366`
- prototype: `void __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1801be0e0`
- `0x1802e6c58`

## callees

- `0x1800727b8`
- `0x1800793cc`
- `0x1800986ec`
- `0x180098d04`
- `0x1802aa190`
- `0x1802e2ec4`
- `0x1802e5658`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e56e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e56e0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e5722`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1802e5722`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1802e5744`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1802e5744`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802e56bb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802e56bb`

## string_xrefs

- `0x1802e579e`: `Log file could not be opened\n`
- `0x1802e5780`: `Opened log file '%s'\n`

## pseudocode

```c
void __fastcall OpenLogFile(LPCWSTR lpFileName, int a2)
{
  __int16 Buffer; // [rsp+60h] [rbp+18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+20h] BYREF

  if ( IsSecureMode() )
  {
    ErrOut(L"Log file operations are not allowed in SECURE mode\n");
  }
  else
  {
    CloseLogFile();
    g_LogFile = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 2 * (a2 & 1u) + 2, 0x80u, 0);
    if ( (char *)g_LogFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      ErrOut(L"Log file could not be opened\n");
      g_LogFile = 0;
    }
    else
    {
      if ( (a2 & 2) != 0 && !GetLastError() )
      {
        NumberOfBytesWritten = 0;
        Buffer = -257;
        WriteFile(g_LogFile, &Buffer, 2u, &NumberOfBytesWritten, 0);
      }
      if ( (a2 & 1) != 0 )
        SetFilePointer(g_LogFile, 0, 0, 2u);
      CopyNStringW(&g_OpenLogFileName);
      g_LogConvFlags = 0;
      g_LogFlags = a2 | 0x80000000;
      dprintf(L"Opened log file '%s'\n", lpFileName);
      NotifyChangeEngineState(0x40u, 1u, 1);
    }
  }
}

```

## disassembly

```asm
0x1802e5658  mov     [rsp+arg_0], rbx
0x1802e565d  mov     [rsp+arg_8], rsi
0x1802e5662  push    rdi
0x1802e5663  sub     rsp, 40h
0x1802e5667  mov     ebx, edx
0x1802e5669  mov     rsi, rcx
0x1802e566c  call    ?IsSecureMode@@YA_NXZ; IsSecureMode(void)
0x1802e5671  test    al, al
0x1802e5673  jz      short loc_1802E5686
0x1802e5675  lea     rcx, aLogFileOperati; "Log file operations are not allowed in "...
0x1802e567c  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1802e5681  jmp     loc_1802E57B5
0x1802e5686  call    ?CloseLogFile@@YAXXZ; CloseLogFile(void)
0x1802e568b  xor     r9d, r9d; lpSecurityAttributes
0x1802e568e  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1802e5697  mov     edi, ebx
0x1802e5699  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1802e56a1  and     edi, 1
0x1802e56a4  mov     edx, 0C0000000h; dwDesiredAccess
0x1802e56a9  mov     rcx, rsi; lpFileName
0x1802e56ac  lea     r8d, [r9+3]; dwShareMode
0x1802e56b0  lea     eax, ds:2[rdi*2]
0x1802e56b7  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x1802e56bb  call    cs:__imp_CreateFileW
0x1802e56c2  nop     dword ptr [rax+rax+00h]
0x1802e56c7  mov     cs:?g_LogFile@@3PEAXEA, rax; void * g_LogFile
0x1802e56ce  dec     rax
0x1802e56d1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1802e56d5  ja      loc_1802E579E
0x1802e56db  test    bl, 2
0x1802e56de  jz      short loc_1802E572E
0x1802e56e0  call    cs:__imp_GetLastError
0x1802e56e7  nop     dword ptr [rax+rax+00h]
0x1802e56ec  test    eax, eax
0x1802e56ee  jnz     short loc_1802E572E
0x1802e56f0  mov     rcx, cs:?g_LogFile@@3PEAXEA; hFile
0x1802e56f7  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802e56fc  mov     eax, 0FEFFh
0x1802e5701  mov     [rsp+48h+NumberOfBytesWritten], 0
0x1802e5709  mov     r8d, 2; nNumberOfBytesToWrite
0x1802e570f  mov     [rsp+48h+Buffer], ax
0x1802e5714  lea     rdx, [rsp+48h+Buffer]; lpBuffer
0x1802e5719  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x1802e5722  call    cs:__imp_WriteFile
0x1802e5729  nop     dword ptr [rax+rax+00h]
0x1802e572e  test    edi, edi
0x1802e5730  jz      short loc_1802E5750
0x1802e5732  mov     rcx, cs:?g_LogFile@@3PEAXEA; hFile
0x1802e5739  mov     r9d, 2; dwMoveMethod
0x1802e573f  xor     r8d, r8d; lpDistanceToMoveHigh
0x1802e5742  xor     edx, edx; lDistanceToMove
0x1802e5744  call    cs:__imp_SetFilePointer
0x1802e574b  nop     dword ptr [rax+rax+00h]
0x1802e5750  mov     r9d, 105h
0x1802e5756  lea     rcx, ?g_OpenLogFileName@@3PAGA; void *
0x1802e575d  or      r8d, 0FFFFFFFFh
0x1802e5761  mov     rdx, rsi
0x1802e5764  call    CopyNStringW
0x1802e5769  bts     ebx, 1Fh
0x1802e576d  mov     cs:?g_LogConvFlags@@3KA, 0; ulong g_LogConvFlags
0x1802e5777  mov     rdx, rsi
0x1802e577a  mov     cs:?g_LogFlags@@3KA, ebx; ulong g_LogFlags
0x1802e5780  lea     rcx, aOpenedLogFileS; "Opened log file '%s'\n"
0x1802e5787  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1802e578c  mov     edx, 1; unsigned __int64
0x1802e5791  mov     r8d, edx; int
0x1802e5794  lea     ecx, [rdx+3Fh]; unsigned int
0x1802e5797  call    ?NotifyChangeEngineState@@YAXK_KH@Z; NotifyChangeEngineState(ulong,unsigned __int64,int)
0x1802e579c  jmp     short loc_1802E57B5
0x1802e579e  lea     rcx, aLogFileCouldNo; "Log file could not be opened\n"
0x1802e57a5  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1802e57aa  mov     cs:?g_LogFile@@3PEAXEA, 0; void * g_LogFile
0x1802e57b5  mov     rbx, [rsp+48h+arg_0]
0x1802e57ba  mov     rsi, [rsp+48h+arg_8]
0x1802e57bf  add     rsp, 40h
0x1802e57c3  pop     rdi
0x1802e57c4  retn
```
