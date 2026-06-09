# PerfDiagShared::Serializer::ReadFromFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(ushort const *,PerfDiagShared::Serializer::CStringInterner &,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881> &)

- ea: `0x1800bfda0`
- end: `0x1800bfe37`
- name: `??$ReadFromFile@U?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJPEBGAEAVCStringInterner@01@AEAU?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800c0df0`
- `0x1800c277c`

## callees

- `0x1800bfca0`
- `0x1800bfda0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfdf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfdf5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bfde6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bfde6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bfe1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bfe1f`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::ReadFromFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(
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
    v7 = PerfDiagShared::Serializer::ReadFromFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(
           FileW,
           a2);
    CloseHandle(v5);
  }
  return v7;
}

```

## disassembly

```asm
0x1800bfda0  mov     [rsp+arg_0], rbx
0x1800bfda5  mov     [rsp+arg_8], rsi
0x1800bfdaa  push    rdi
0x1800bfdab  sub     rsp, 40h
0x1800bfdaf  mov     rbx, r8
0x1800bfdb2  mov     rsi, rdx
0x1800bfdb5  test    rcx, rcx
0x1800bfdb8  jnz     short loc_1800BFDC1
0x1800bfdba  mov     eax, 80070057h
0x1800bfdbf  jmp     short loc_1800BFE27
0x1800bfdc1  xor     r9d, r9d; lpSecurityAttributes
0x1800bfdc4  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800bfdcd  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800bfdd5  mov     edx, 80000000h; dwDesiredAccess
0x1800bfdda  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800bfde2  lea     r8d, [r9+1]; dwShareMode
0x1800bfde6  call    cs:__imp_CreateFileW
0x1800bfdec  mov     rdi, rax
0x1800bfdef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bfdf3  jnz     short loc_1800BFE0C
0x1800bfdf5  call    cs:__imp_GetLastError
0x1800bfdfb  mov     ebx, eax
0x1800bfdfd  test    eax, eax
0x1800bfdff  jle     short loc_1800BFE25
0x1800bfe01  movzx   ebx, ax
0x1800bfe04  or      ebx, 80070000h
0x1800bfe0a  jmp     short loc_1800BFE25
0x1800bfe0c  mov     r8, rbx
0x1800bfe0f  mov     rdx, rsi; struct PerfDiagShared::Serializer::CStringInterner *
0x1800bfe12  mov     rcx, rdi; hFile
0x1800bfe15  call    ??$ReadFromFile@U?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAU?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@@Z; PerfDiagShared::Serializer::ReadFromFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(void *,PerfDiagShared::Serializer::CStringInterner &,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881> &)
0x1800bfe1a  mov     ebx, eax
0x1800bfe1c  mov     rcx, rdi; hObject
0x1800bfe1f  call    cs:__imp_CloseHandle
0x1800bfe25  mov     eax, ebx
0x1800bfe27  mov     rbx, [rsp+48h+arg_0]
0x1800bfe2c  mov     rsi, [rsp+48h+arg_8]
0x1800bfe31  add     rsp, 40h
0x1800bfe35  pop     rdi
0x1800bfe36  retn
```
