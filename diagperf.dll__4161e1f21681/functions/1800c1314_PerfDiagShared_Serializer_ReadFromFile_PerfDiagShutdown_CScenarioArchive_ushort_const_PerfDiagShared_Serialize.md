# PerfDiagShared::Serializer::ReadFromFile<PerfDiagShutdown::CScenarioArchive>(ushort const *,PerfDiagShared::Serializer::CStringInterner &,PerfDiagShutdown::CScenarioArchive &)

- ea: `0x1800c1314`
- end: `0x1800c13ab`
- name: `??$ReadFromFile@UCScenarioArchive@PerfDiagShutdown@@@Serializer@PerfDiagShared@@YAJPEBGAEAVCStringInterner@01@AEAUCScenarioArchive@PerfDiagShutdown@@@Z`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800c1bf0`
- `0x1800c96e0`

## callees

- `0x1800c1214`
- `0x1800c1314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1369`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c135a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c135a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1393`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::ReadFromFile<PerfDiagShutdown::CScenarioArchive>(
        const WCHAR *a1,
        struct PerfDiagShared::Serializer::CStringInterner *a2)
{
  HANDLE FileW; // rax
  void *v5; // rdi
  signed int LastError; // eax
  unsigned int v7; // ebx

  if ( !a1 )
    return 2147942487LL;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v7 = PerfDiagShared::Serializer::ReadFromFile<PerfDiagShutdown::CScenarioArchive>(FileW, a2);
    CloseHandle(v5);
  }
  return v7;
}

```

## disassembly

```asm
0x1800c1314  mov     [rsp+arg_0], rbx
0x1800c1319  mov     [rsp+arg_8], rsi
0x1800c131e  push    rdi
0x1800c131f  sub     rsp, 40h
0x1800c1323  mov     rbx, r8
0x1800c1326  mov     rsi, rdx
0x1800c1329  test    rcx, rcx
0x1800c132c  jnz     short loc_1800C1335
0x1800c132e  mov     eax, 80070057h
0x1800c1333  jmp     short loc_1800C139B
0x1800c1335  xor     r9d, r9d; lpSecurityAttributes
0x1800c1338  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800c1341  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800c1349  mov     edx, 80000000h; dwDesiredAccess
0x1800c134e  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800c1356  lea     r8d, [r9+1]; dwShareMode
0x1800c135a  call    cs:__imp_CreateFileW
0x1800c1360  mov     rdi, rax
0x1800c1363  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c1367  jnz     short loc_1800C1380
0x1800c1369  call    cs:__imp_GetLastError
0x1800c136f  mov     ebx, eax
0x1800c1371  test    eax, eax
0x1800c1373  jle     short loc_1800C1399
0x1800c1375  movzx   ebx, ax
0x1800c1378  or      ebx, 80070000h
0x1800c137e  jmp     short loc_1800C1399
0x1800c1380  mov     r8, rbx
0x1800c1383  mov     rdx, rsi; struct PerfDiagShared::Serializer::CStringInterner *
0x1800c1386  mov     rcx, rdi; hFile
0x1800c1389  call    ??$ReadFromFile@UCScenarioArchive@PerfDiagShutdown@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAUCScenarioArchive@PerfDiagShutdown@@@Z; PerfDiagShared::Serializer::ReadFromFile<PerfDiagShutdown::CScenarioArchive>(void *,PerfDiagShared::Serializer::CStringInterner &,PerfDiagShutdown::CScenarioArchive &)
0x1800c138e  mov     ebx, eax
0x1800c1390  mov     rcx, rdi; hObject
0x1800c1393  call    cs:__imp_CloseHandle
0x1800c1399  mov     eax, ebx
0x1800c139b  mov     rbx, [rsp+48h+arg_0]
0x1800c13a0  mov     rsi, [rsp+48h+arg_8]
0x1800c13a5  add     rsp, 40h
0x1800c13a9  pop     rdi
0x1800c13aa  retn
```
