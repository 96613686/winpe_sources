# PerfDiagShared::Serializer::ReadFromFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(ushort const *,PerfDiagShared::Serializer::CStringInterner &,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419> &)

- ea: `0x1800bfc00`
- end: `0x1800bfc97`
- name: `??$ReadFromFile@U?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJPEBGAEAVCStringInterner@01@AEAU?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800c0d80`
- `0x1800c25a8`

## callees

- `0x1800bfb00`
- `0x1800bfc00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfc55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfc55`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bfc46`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bfc46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bfc7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bfc7f`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::ReadFromFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(
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
    v7 = PerfDiagShared::Serializer::ReadFromFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(
           FileW,
           a2);
    CloseHandle(v5);
  }
  return v7;
}

```

## disassembly

```asm
0x1800bfc00  mov     [rsp+arg_0], rbx
0x1800bfc05  mov     [rsp+arg_8], rsi
0x1800bfc0a  push    rdi
0x1800bfc0b  sub     rsp, 40h
0x1800bfc0f  mov     rbx, r8
0x1800bfc12  mov     rsi, rdx
0x1800bfc15  test    rcx, rcx
0x1800bfc18  jnz     short loc_1800BFC21
0x1800bfc1a  mov     eax, 80070057h
0x1800bfc1f  jmp     short loc_1800BFC87
0x1800bfc21  xor     r9d, r9d; lpSecurityAttributes
0x1800bfc24  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800bfc2d  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800bfc35  mov     edx, 80000000h; dwDesiredAccess
0x1800bfc3a  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800bfc42  lea     r8d, [r9+1]; dwShareMode
0x1800bfc46  call    cs:__imp_CreateFileW
0x1800bfc4c  mov     rdi, rax
0x1800bfc4f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bfc53  jnz     short loc_1800BFC6C
0x1800bfc55  call    cs:__imp_GetLastError
0x1800bfc5b  mov     ebx, eax
0x1800bfc5d  test    eax, eax
0x1800bfc5f  jle     short loc_1800BFC85
0x1800bfc61  movzx   ebx, ax
0x1800bfc64  or      ebx, 80070000h
0x1800bfc6a  jmp     short loc_1800BFC85
0x1800bfc6c  mov     r8, rbx
0x1800bfc6f  mov     rdx, rsi; struct PerfDiagShared::Serializer::CStringInterner *
0x1800bfc72  mov     rcx, rdi; hFile
0x1800bfc75  call    ??$ReadFromFile@U?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAU?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@@Z; PerfDiagShared::Serializer::ReadFromFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(void *,PerfDiagShared::Serializer::CStringInterner &,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419> &)
0x1800bfc7a  mov     ebx, eax
0x1800bfc7c  mov     rcx, rdi; hObject
0x1800bfc7f  call    cs:__imp_CloseHandle
0x1800bfc85  mov     eax, ebx
0x1800bfc87  mov     rbx, [rsp+48h+arg_0]
0x1800bfc8c  mov     rsi, [rsp+48h+arg_8]
0x1800bfc91  add     rsp, 40h
0x1800bfc95  pop     rdi
0x1800bfc96  retn
```
