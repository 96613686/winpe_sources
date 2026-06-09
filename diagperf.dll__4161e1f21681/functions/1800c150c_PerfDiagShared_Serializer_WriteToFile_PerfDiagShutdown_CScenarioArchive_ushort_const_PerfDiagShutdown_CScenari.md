# PerfDiagShared::Serializer::WriteToFile<PerfDiagShutdown::CScenarioArchive>(ushort const *,PerfDiagShutdown::CScenarioArchive const &)

- ea: `0x1800c150c`
- end: `0x1800c16aa`
- name: `??$WriteToFile@UCScenarioArchive@PerfDiagShutdown@@@Serializer@PerfDiagShared@@YAJPEBGAEBUCScenarioArchive@PerfDiagShutdown@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800c1f80`
- `0x1800c96e0`

## callees

- `0x18001f5d8`
- `0x180056c14`
- `0x180056c20`
- `0x1800c10b0`
- `0x1800c150c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1650`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c1646`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c1646`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c1601`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c1601`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c167d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c167d`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::WriteToFile<PerfDiagShutdown::CScenarioArchive>(
        LPCWSTR lpFileName,
        __int64 a2)
{
  void *v5; // rsi
  signed int v6; // ebx
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // r14
  HANDLE FileW; // rax
  void *v10; // rdi
  signed int LastError; // eax
  signed int v12; // eax
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 nNumberOfBytesToWrite; // [rsp+80h] [rbp+18h] BYREF
  void *v15; // [rsp+88h] [rbp+20h]

  if ( !lpFileName )
    return 2147942487LL;
  nNumberOfBytesToWrite = 0;
  v5 = 0;
  v15 = 0;
  v6 = PerfDiagShared::Serializer::GetSize<PerfDiagShutdown::CScenarioArchive>(a2, &nNumberOfBytesToWrite);
  if ( v6 >= 0 )
  {
    v7 = nNumberOfBytesToWrite;
    if ( nNumberOfBytesToWrite )
    {
      if ( nNumberOfBytesToWrite == (unsigned int)nNumberOfBytesToWrite )
      {
        v5 = operator new[](nNumberOfBytesToWrite);
        v15 = v5;
        nNumberOfBytesToWrite = 0;
        v6 = PerfDiagShared::Serializer::Write<PerfDiagShutdown::CScenarioArchive>(v5, v7, a2, &nNumberOfBytesToWrite);
        if ( v6 >= 0 )
        {
          v8 = nNumberOfBytesToWrite;
          if ( nNumberOfBytesToWrite <= v7 )
          {
            FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 2u, 0, 0);
            v10 = FileW;
            if ( FileW == (HANDLE)-1LL )
            {
              LastError = GetLastError();
              v6 = LastError;
              if ( LastError > 0 )
                v6 = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              NumberOfBytesWritten = 0;
              if ( WriteFile(FileW, v5, v8, &NumberOfBytesWritten, 0) )
              {
                v6 = v8 != NumberOfBytesWritten ? 0x85541001 : 0;
              }
              else
              {
                v12 = GetLastError();
                v6 = v12;
                if ( v12 > 0 )
                  v6 = (unsigned __int16)v12 | 0x80070000;
              }
              CloseHandle(v10);
            }
          }
          else
          {
            v6 = -2058088447;
          }
        }
      }
      else
      {
        v6 = -2147024362;
      }
    }
    else
    {
      v6 = 1;
    }
  }
  operator delete(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c150c  push    rbx
0x1800c150e  push    rsi
0x1800c150f  push    rdi
0x1800c1510  push    r14
0x1800c1512  push    r15
0x1800c1514  sub     rsp, 40h
0x1800c1518  mov     r14, rdx
0x1800c151b  mov     r15, rcx
0x1800c151e  test    rcx, rcx
0x1800c1521  jnz     short loc_1800C152D
0x1800c1523  mov     eax, 80070057h
0x1800c1528  jmp     loc_1800C169E
0x1800c152d  mov     [rsp+68h+nNumberOfBytesToWrite], 0
0x1800c1539  xor     esi, esi
0x1800c153b  mov     [rsp+68h+arg_18], rsi
0x1800c1543  lea     rdx, [rsp+68h+nNumberOfBytesToWrite]
0x1800c154b  mov     rcx, r14
0x1800c154e  call    ??$GetSize@UCScenarioArchive@PerfDiagShutdown@@@Serializer@PerfDiagShared@@YAJAEBUCScenarioArchive@PerfDiagShutdown@@AEA_K_N@Z; PerfDiagShared::Serializer::GetSize<PerfDiagShutdown::CScenarioArchive>(PerfDiagShutdown::CScenarioArchive const &,unsigned __int64 &,bool)
0x1800c1553  mov     ebx, eax
0x1800c1555  test    eax, eax
0x1800c1557  js      loc_1800C1694
0x1800c155d  mov     rdi, [rsp+68h+nNumberOfBytesToWrite]
0x1800c1565  test    rdi, rdi
0x1800c1568  jnz     short loc_1800C1572
0x1800c156a  lea     ebx, [rsi+1]
0x1800c156d  jmp     loc_1800C1694
0x1800c1572  mov     eax, edi
0x1800c1574  cmp     rdi, rax
0x1800c1577  jz      short loc_1800C1583
0x1800c1579  mov     ebx, 80070216h
0x1800c157e  jmp     loc_1800C1694
0x1800c1583  mov     rcx, rdi; unsigned __int64
0x1800c1586  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c158b  mov     rsi, rax
0x1800c158e  mov     [rsp+68h+arg_18], rax
0x1800c1596  mov     [rsp+68h+nNumberOfBytesToWrite], 0
0x1800c15a2  lea     r9, [rsp+68h+nNumberOfBytesToWrite]
0x1800c15aa  mov     r8, r14
0x1800c15ad  mov     rdx, rdi
0x1800c15b0  mov     rcx, rsi
0x1800c15b3  call    ??$Write@UCScenarioArchive@PerfDiagShutdown@@@Serializer@PerfDiagShared@@YAJPEAX_KAEBUCScenarioArchive@PerfDiagShutdown@@AEA_K_N@Z; PerfDiagShared::Serializer::Write<PerfDiagShutdown::CScenarioArchive>(void *,unsigned __int64,PerfDiagShutdown::CScenarioArchive const &,unsigned __int64 &,bool)
0x1800c15b8  mov     ebx, eax
0x1800c15ba  test    eax, eax
0x1800c15bc  js      loc_1800C1694
0x1800c15c2  mov     r14, [rsp+68h+nNumberOfBytesToWrite]
0x1800c15ca  cmp     r14, rdi
0x1800c15cd  jbe     short loc_1800C15D9
0x1800c15cf  mov     ebx, 85541001h
0x1800c15d4  jmp     loc_1800C1694
0x1800c15d9  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800c15e2  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800c15ea  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x1800c15f2  xor     r9d, r9d; lpSecurityAttributes
0x1800c15f5  mov     edx, 40000000h; dwDesiredAccess
0x1800c15fa  lea     r8d, [r9+1]; dwShareMode
0x1800c15fe  mov     rcx, r15; lpFileName
0x1800c1601  call    cs:__imp_CreateFileW
0x1800c1607  mov     rdi, rax
0x1800c160a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c160e  jnz     short loc_1800C1627
0x1800c1610  call    cs:__imp_GetLastError
0x1800c1616  mov     ebx, eax
0x1800c1618  test    eax, eax
0x1800c161a  jle     short loc_1800C1694
0x1800c161c  movzx   ebx, ax
0x1800c161f  or      ebx, 80070000h
0x1800c1625  jmp     short loc_1800C1694
0x1800c1627  mov     [rsp+68h+NumberOfBytesWritten], 0
0x1800c162f  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x1800c1638  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c163d  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800c1640  mov     rdx, rsi; lpBuffer
0x1800c1643  mov     rcx, rdi; hFile
0x1800c1646  call    cs:__imp_WriteFile
0x1800c164c  test    eax, eax
0x1800c164e  jnz     short loc_1800C1667
0x1800c1650  call    cs:__imp_GetLastError
0x1800c1656  mov     ebx, eax
0x1800c1658  test    eax, eax
0x1800c165a  jle     short loc_1800C167A
0x1800c165c  movzx   ebx, ax
0x1800c165f  or      ebx, 80070000h
0x1800c1665  jmp     short loc_1800C167A
0x1800c1667  mov     eax, [rsp+68h+NumberOfBytesWritten]
0x1800c166b  sub     rax, r14
0x1800c166e  neg     rax
0x1800c1671  sbb     eax, eax
0x1800c1673  mov     ebx, 85541001h
0x1800c1678  and     ebx, eax
0x1800c167a  mov     rcx, rdi; hObject
0x1800c167d  call    cs:__imp_CloseHandle
0x1800c1683  jmp     short loc_1800C1694
0x1800c1685  mov     rsi, [rsp+68h+arg_18]
0x1800c168d  mov     ebx, dword ptr [rsp+68h+nNumberOfBytesToWrite]
0x1800c1694  mov     rcx, rsi; Block
0x1800c1697  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c169c  mov     eax, ebx
0x1800c169e  add     rsp, 40h
0x1800c16a2  pop     r15
0x1800c16a4  pop     r14
0x1800c16a6  pop     rdi
0x1800c16a7  pop     rsi
0x1800c16a8  pop     rbx
0x1800c16a9  retn
```
