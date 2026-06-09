# PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCauseDriver,std::allocator<PerfDiagOutput::CRootCauseDriver>>>(ushort const *,PerfDiagShared::Serializer::CStringInterner &,std::vector<PerfDiagOutput::CRootCauseDriver,std::allocator<PerfDiagOutput::CRootCauseDriver>> &)

- ea: `0x1800bb044`
- end: `0x1800bb0db`
- name: `??$ReadFromFile@V?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEBGAEAVCStringInterner@01@AEAV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800baa4c`

## callees

- `0x1800b74d8`
- `0x1800bb044`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb099`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bb08a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bb08a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb0c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb0c3`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(
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
    v7 = PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(FileW, a2);
    CloseHandle(v5);
  }
  return v7;
}

```

## disassembly

```asm
0x1800bb044  mov     [rsp+arg_0], rbx
0x1800bb049  mov     [rsp+arg_8], rsi
0x1800bb04e  push    rdi
0x1800bb04f  sub     rsp, 40h
0x1800bb053  mov     rbx, r8
0x1800bb056  mov     rsi, rdx
0x1800bb059  test    rcx, rcx
0x1800bb05c  jnz     short loc_1800BB065
0x1800bb05e  mov     eax, 80070057h
0x1800bb063  jmp     short loc_1800BB0CB
0x1800bb065  xor     r9d, r9d; lpSecurityAttributes
0x1800bb068  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800bb071  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800bb079  mov     edx, 80000000h; dwDesiredAccess
0x1800bb07e  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800bb086  lea     r8d, [r9+1]; dwShareMode
0x1800bb08a  call    cs:__imp_CreateFileW
0x1800bb090  mov     rdi, rax
0x1800bb093  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bb097  jnz     short loc_1800BB0B0
0x1800bb099  call    cs:__imp_GetLastError
0x1800bb09f  mov     ebx, eax
0x1800bb0a1  test    eax, eax
0x1800bb0a3  jle     short loc_1800BB0C9
0x1800bb0a5  movzx   ebx, ax
0x1800bb0a8  or      ebx, 80070000h
0x1800bb0ae  jmp     short loc_1800BB0C9
0x1800bb0b0  mov     r8, rbx
0x1800bb0b3  mov     rdx, rsi; struct PerfDiagShared::Serializer::CStringInterner *
0x1800bb0b6  mov     rcx, rdi; hFile
0x1800bb0b9  call    ??$ReadFromFile@V?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Z; PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(void *,PerfDiagShared::Serializer::CStringInterner &,std::vector<PerfDiagOutput::CRootCauseDriver> &)
0x1800bb0be  mov     ebx, eax
0x1800bb0c0  mov     rcx, rdi; hObject
0x1800bb0c3  call    cs:__imp_CloseHandle
0x1800bb0c9  mov     eax, ebx
0x1800bb0cb  mov     rbx, [rsp+48h+arg_0]
0x1800bb0d0  mov     rsi, [rsp+48h+arg_8]
0x1800bb0d5  add     rsp, 40h
0x1800bb0d9  pop     rdi
0x1800bb0da  retn
```
