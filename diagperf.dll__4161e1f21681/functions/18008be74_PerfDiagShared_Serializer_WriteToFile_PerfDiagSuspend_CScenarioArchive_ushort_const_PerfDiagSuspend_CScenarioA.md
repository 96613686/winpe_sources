# PerfDiagShared::Serializer::WriteToFile<PerfDiagSuspend::CScenarioArchive>(ushort const *,PerfDiagSuspend::CScenarioArchive const &)

- ea: `0x18008be74`
- end: `0x18008c012`
- name: `??$WriteToFile@UCScenarioArchive@PerfDiagSuspend@@@Serializer@PerfDiagShared@@YAJPEBGAEBUCScenarioArchive@PerfDiagSuspend@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18008e668`
- `0x18008f1e0`

## callees

- `0x180056c14`
- `0x180056c20`
- `0x18008b918`
- `0x18008bdcc`
- `0x18008be74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bf78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bfb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bf78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bfb8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008bfae`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008bfae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008bf69`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008bf69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008bfe5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008bfe5`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::WriteToFile<PerfDiagSuspend::CScenarioArchive>(
        LPCWSTR lpFileName,
        __int64 a2)
{
  void *v4; // rsi
  signed int v5; // ebx
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r14
  HANDLE FileW; // rax
  void *v9; // rdi
  signed int LastError; // eax
  signed int v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 nNumberOfBytesToWrite; // [rsp+80h] [rbp+18h] BYREF
  void *v14; // [rsp+88h] [rbp+20h]

  if ( !lpFileName )
    return 2147942487LL;
  nNumberOfBytesToWrite = 0;
  v4 = 0;
  v14 = 0;
  v5 = PerfDiagShared::Serializer::GetSize<PerfDiagSuspend::CScenarioArchive>(a2, &nNumberOfBytesToWrite);
  if ( v5 >= 0 )
  {
    v6 = nNumberOfBytesToWrite;
    if ( nNumberOfBytesToWrite )
    {
      if ( nNumberOfBytesToWrite == (unsigned int)nNumberOfBytesToWrite )
      {
        try
        {
          v4 = operator new[](nNumberOfBytesToWrite);
          v14 = v4;
          nNumberOfBytesToWrite = 0;
        }
        catch ( std::bad_alloc )
        {
          LODWORD(nNumberOfBytesToWrite) = -2147024882;
          v4 = v14;
          v5 = -2147024882;
          goto LABEL_19;
        }
        v5 = PerfDiagShared::Serializer::Write<PerfDiagSuspend::CScenarioArchive>();
        if ( v5 >= 0 )
        {
          v7 = nNumberOfBytesToWrite;
          if ( nNumberOfBytesToWrite <= v6 )
          {
            FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 2u, 0, 0);
            v9 = FileW;
            if ( FileW == (HANDLE)-1LL )
            {
              LastError = GetLastError();
              v5 = LastError;
              if ( LastError > 0 )
                v5 = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              NumberOfBytesWritten = 0;
              if ( WriteFile(FileW, v4, v7, &NumberOfBytesWritten, 0) )
              {
                v5 = v7 != NumberOfBytesWritten ? 0x85541001 : 0;
              }
              else
              {
                v11 = GetLastError();
                v5 = v11;
                if ( v11 > 0 )
                  v5 = (unsigned __int16)v11 | 0x80070000;
              }
              CloseHandle(v9);
            }
          }
          else
          {
            v5 = -2058088447;
          }
        }
      }
      else
      {
        v5 = -2147024362;
      }
    }
    else
    {
      v5 = 1;
    }
  }
LABEL_19:
  operator delete(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18008be74  push    rbx
0x18008be76  push    rsi
0x18008be77  push    rdi
0x18008be78  push    r14
0x18008be7a  push    r15
0x18008be7c  sub     rsp, 40h
0x18008be80  mov     r14, rdx
0x18008be83  mov     r15, rcx
0x18008be86  test    rcx, rcx
0x18008be89  jnz     short loc_18008BE95
0x18008be8b  mov     eax, 80070057h
0x18008be90  jmp     loc_18008C006
0x18008be95  mov     [rsp+68h+nNumberOfBytesToWrite], 0
0x18008bea1  xor     esi, esi
0x18008bea3  mov     [rsp+68h+arg_18], rsi
0x18008beab  lea     rdx, [rsp+68h+nNumberOfBytesToWrite]
0x18008beb3  mov     rcx, r14
0x18008beb6  call    ??$GetSize@UCScenarioArchive@PerfDiagSuspend@@@Serializer@PerfDiagShared@@YAJAEBUCScenarioArchive@PerfDiagSuspend@@AEA_K_N@Z; PerfDiagShared::Serializer::GetSize<PerfDiagSuspend::CScenarioArchive>(PerfDiagSuspend::CScenarioArchive const &,unsigned __int64 &,bool)
0x18008bebb  mov     ebx, eax
0x18008bebd  test    eax, eax
0x18008bebf  js      loc_18008BFFC
0x18008bec5  mov     rdi, [rsp+68h+nNumberOfBytesToWrite]
0x18008becd  test    rdi, rdi
0x18008bed0  jnz     short loc_18008BEDA
0x18008bed2  lea     ebx, [rsi+1]
0x18008bed5  jmp     loc_18008BFFC
0x18008beda  mov     eax, edi
0x18008bedc  cmp     rdi, rax
0x18008bedf  jz      short loc_18008BEEB
0x18008bee1  mov     ebx, 80070216h
0x18008bee6  jmp     loc_18008BFFC
0x18008beeb  mov     rcx, rdi; unsigned __int64
0x18008beee  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008bef3  mov     rsi, rax
0x18008bef6  mov     [rsp+68h+arg_18], rax
0x18008befe  mov     [rsp+68h+nNumberOfBytesToWrite], 0
0x18008bf0a  lea     r9, [rsp+68h+nNumberOfBytesToWrite]
0x18008bf12  mov     r8, r14
0x18008bf15  mov     rdx, rdi
0x18008bf18  mov     rcx, rsi
0x18008bf1b  call    ??$Write@UCScenarioArchive@PerfDiagSuspend@@@Serializer@PerfDiagShared@@YAJPEAX_KAEBUCScenarioArchive@PerfDiagSuspend@@AEA_K_N@Z; PerfDiagShared::Serializer::Write<PerfDiagSuspend::CScenarioArchive>(void *,unsigned __int64,PerfDiagSuspend::CScenarioArchive const &,unsigned __int64 &,bool)
0x18008bf20  mov     ebx, eax
0x18008bf22  test    eax, eax
0x18008bf24  js      loc_18008BFFC
0x18008bf2a  mov     r14, [rsp+68h+nNumberOfBytesToWrite]
0x18008bf32  cmp     r14, rdi
0x18008bf35  jbe     short loc_18008BF41
0x18008bf37  mov     ebx, 85541001h
0x18008bf3c  jmp     loc_18008BFFC
0x18008bf41  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18008bf4a  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18008bf52  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x18008bf5a  xor     r9d, r9d; lpSecurityAttributes
0x18008bf5d  mov     edx, 40000000h; dwDesiredAccess
0x18008bf62  lea     r8d, [r9+1]; dwShareMode
0x18008bf66  mov     rcx, r15; lpFileName
0x18008bf69  call    cs:__imp_CreateFileW
0x18008bf6f  mov     rdi, rax
0x18008bf72  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008bf76  jnz     short loc_18008BF8F
0x18008bf78  call    cs:__imp_GetLastError
0x18008bf7e  mov     ebx, eax
0x18008bf80  test    eax, eax
0x18008bf82  jle     short loc_18008BFFC
0x18008bf84  movzx   ebx, ax
0x18008bf87  or      ebx, 80070000h
0x18008bf8d  jmp     short loc_18008BFFC
0x18008bf8f  mov     [rsp+68h+NumberOfBytesWritten], 0
0x18008bf97  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x18008bfa0  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008bfa5  mov     r8d, r14d; nNumberOfBytesToWrite
0x18008bfa8  mov     rdx, rsi; lpBuffer
0x18008bfab  mov     rcx, rdi; hFile
0x18008bfae  call    cs:__imp_WriteFile
0x18008bfb4  test    eax, eax
0x18008bfb6  jnz     short loc_18008BFCF
0x18008bfb8  call    cs:__imp_GetLastError
0x18008bfbe  mov     ebx, eax
0x18008bfc0  test    eax, eax
0x18008bfc2  jle     short loc_18008BFE2
0x18008bfc4  movzx   ebx, ax
0x18008bfc7  or      ebx, 80070000h
0x18008bfcd  jmp     short loc_18008BFE2
0x18008bfcf  mov     eax, [rsp+68h+NumberOfBytesWritten]
0x18008bfd3  sub     rax, r14
0x18008bfd6  neg     rax
0x18008bfd9  sbb     eax, eax
0x18008bfdb  mov     ebx, 85541001h
0x18008bfe0  and     ebx, eax
0x18008bfe2  mov     rcx, rdi; hObject
0x18008bfe5  call    cs:__imp_CloseHandle
0x18008bfeb  jmp     short loc_18008BFFC
0x18008bfed  mov     rsi, [rsp+68h+arg_18]
0x18008bff5  mov     ebx, dword ptr [rsp+68h+nNumberOfBytesToWrite]
0x18008bffc  mov     rcx, rsi; Block
0x18008bfff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008c004  mov     eax, ebx
0x18008c006  add     rsp, 40h
0x18008c00a  pop     r15
0x18008c00c  pop     r14
0x18008c00e  pop     rdi
0x18008c00f  pop     rsi
0x18008c010  pop     rbx
0x18008c011  retn
```
