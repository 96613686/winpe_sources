# PerfDiagShared::Serializer::ReadFromFile<PerfDiagSuspend::CScenarioArchive>(ushort const *,PerfDiagShared::Serializer::CStringInterner &,PerfDiagSuspend::CScenarioArchive &)

- ea: `0x18008bb7c`
- end: `0x18008bc13`
- name: `??$ReadFromFile@UCScenarioArchive@PerfDiagSuspend@@@Serializer@PerfDiagShared@@YAJPEBGAEAVCStringInterner@01@AEAUCScenarioArchive@PerfDiagSuspend@@@Z`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18008e668`
- `0x18008ef70`

## callees

- `0x18008ba7c`
- `0x18008bb7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bbd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bbd1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008bbc2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008bbc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008bbfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008bbfb`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::ReadFromFile<PerfDiagSuspend::CScenarioArchive>(
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
    v7 = PerfDiagShared::Serializer::ReadFromFile<PerfDiagSuspend::CScenarioArchive>(FileW, a2);
    CloseHandle(v5);
  }
  return v7;
}

```

## disassembly

```asm
0x18008bb7c  mov     [rsp+arg_0], rbx
0x18008bb81  mov     [rsp+arg_8], rsi
0x18008bb86  push    rdi
0x18008bb87  sub     rsp, 40h
0x18008bb8b  mov     rbx, r8
0x18008bb8e  mov     rsi, rdx
0x18008bb91  test    rcx, rcx
0x18008bb94  jnz     short loc_18008BB9D
0x18008bb96  mov     eax, 80070057h
0x18008bb9b  jmp     short loc_18008BC03
0x18008bb9d  xor     r9d, r9d; lpSecurityAttributes
0x18008bba0  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18008bba9  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18008bbb1  mov     edx, 80000000h; dwDesiredAccess
0x18008bbb6  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18008bbbe  lea     r8d, [r9+1]; dwShareMode
0x18008bbc2  call    cs:__imp_CreateFileW
0x18008bbc8  mov     rdi, rax
0x18008bbcb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008bbcf  jnz     short loc_18008BBE8
0x18008bbd1  call    cs:__imp_GetLastError
0x18008bbd7  mov     ebx, eax
0x18008bbd9  test    eax, eax
0x18008bbdb  jle     short loc_18008BC01
0x18008bbdd  movzx   ebx, ax
0x18008bbe0  or      ebx, 80070000h
0x18008bbe6  jmp     short loc_18008BC01
0x18008bbe8  mov     r8, rbx
0x18008bbeb  mov     rdx, rsi; struct PerfDiagShared::Serializer::CStringInterner *
0x18008bbee  mov     rcx, rdi; hFile
0x18008bbf1  call    ??$ReadFromFile@UCScenarioArchive@PerfDiagSuspend@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAUCScenarioArchive@PerfDiagSuspend@@@Z; PerfDiagShared::Serializer::ReadFromFile<PerfDiagSuspend::CScenarioArchive>(void *,PerfDiagShared::Serializer::CStringInterner &,PerfDiagSuspend::CScenarioArchive &)
0x18008bbf6  mov     ebx, eax
0x18008bbf8  mov     rcx, rdi; hObject
0x18008bbfb  call    cs:__imp_CloseHandle
0x18008bc01  mov     eax, ebx
0x18008bc03  mov     rbx, [rsp+48h+arg_0]
0x18008bc08  mov     rsi, [rsp+48h+arg_8]
0x18008bc0d  add     rsp, 40h
0x18008bc11  pop     rdi
0x18008bc12  retn
```
