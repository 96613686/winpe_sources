# PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCause,std::allocator<PerfDiagOutput::CRootCause>>>(ushort const *,PerfDiagShared::Serializer::CStringInterner &,std::vector<PerfDiagOutput::CRootCause,std::allocator<PerfDiagOutput::CRootCause>> &)

- ea: `0x1800bb0e4`
- end: `0x1800bb17b`
- name: `??$ReadFromFile@V?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEBGAEAVCStringInterner@01@AEAV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800bad48`

## callees

- `0x1800b270c`
- `0x1800bb0e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb139`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bb12a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bb12a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb163`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb163`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCause>>(
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
    v7 = PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCause>>(FileW, a2);
    CloseHandle(v5);
  }
  return v7;
}

```

## disassembly

```asm
0x1800bb0e4  mov     [rsp+arg_0], rbx
0x1800bb0e9  mov     [rsp+arg_8], rsi
0x1800bb0ee  push    rdi
0x1800bb0ef  sub     rsp, 40h
0x1800bb0f3  mov     rbx, r8
0x1800bb0f6  mov     rsi, rdx
0x1800bb0f9  test    rcx, rcx
0x1800bb0fc  jnz     short loc_1800BB105
0x1800bb0fe  mov     eax, 80070057h
0x1800bb103  jmp     short loc_1800BB16B
0x1800bb105  xor     r9d, r9d; lpSecurityAttributes
0x1800bb108  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800bb111  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800bb119  mov     edx, 80000000h; dwDesiredAccess
0x1800bb11e  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800bb126  lea     r8d, [r9+1]; dwShareMode
0x1800bb12a  call    cs:__imp_CreateFileW
0x1800bb130  mov     rdi, rax
0x1800bb133  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bb137  jnz     short loc_1800BB150
0x1800bb139  call    cs:__imp_GetLastError
0x1800bb13f  mov     ebx, eax
0x1800bb141  test    eax, eax
0x1800bb143  jle     short loc_1800BB169
0x1800bb145  movzx   ebx, ax
0x1800bb148  or      ebx, 80070000h
0x1800bb14e  jmp     short loc_1800BB169
0x1800bb150  mov     r8, rbx
0x1800bb153  mov     rdx, rsi; struct PerfDiagShared::Serializer::CStringInterner *
0x1800bb156  mov     rcx, rdi; hFile
0x1800bb159  call    ??$ReadFromFile@V?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Z; PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCause>>(void *,PerfDiagShared::Serializer::CStringInterner &,std::vector<PerfDiagOutput::CRootCause> &)
0x1800bb15e  mov     ebx, eax
0x1800bb160  mov     rcx, rdi; hObject
0x1800bb163  call    cs:__imp_CloseHandle
0x1800bb169  mov     eax, ebx
0x1800bb16b  mov     rbx, [rsp+48h+arg_0]
0x1800bb170  mov     rsi, [rsp+48h+arg_8]
0x1800bb175  add     rsp, 40h
0x1800bb179  pop     rdi
0x1800bb17a  retn
```
