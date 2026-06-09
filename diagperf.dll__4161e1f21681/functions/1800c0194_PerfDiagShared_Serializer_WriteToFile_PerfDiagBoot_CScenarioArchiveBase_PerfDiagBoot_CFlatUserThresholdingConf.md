# PerfDiagShared::Serializer::WriteToFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(ushort const *,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881> const &)

- ea: `0x1800c0194`
- end: `0x1800c0332`
- name: `??$WriteToFile@U?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJPEBGAEBU?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1800c1080`
- `0x1800c277c`

## callees

- `0x18001f510`
- `0x180056c14`
- `0x180056c20`
- `0x1800bfa54`
- `0x1800c0194`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c02d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c02d8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c02ce`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c02ce`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c0289`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c0289`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0305`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0305`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::WriteToFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(
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
  v6 = PerfDiagShared::Serializer::GetSize<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(
         a2,
         &nNumberOfBytesToWrite);
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
        v6 = PerfDiagShared::Serializer::Write<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(
               v5,
               v7,
               a2,
               &nNumberOfBytesToWrite);
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
0x1800c0194  push    rbx
0x1800c0196  push    rsi
0x1800c0197  push    rdi
0x1800c0198  push    r14
0x1800c019a  push    r15
0x1800c019c  sub     rsp, 40h
0x1800c01a0  mov     r14, rdx
0x1800c01a3  mov     r15, rcx
0x1800c01a6  test    rcx, rcx
0x1800c01a9  jnz     short loc_1800C01B5
0x1800c01ab  mov     eax, 80070057h
0x1800c01b0  jmp     loc_1800C0326
0x1800c01b5  mov     [rsp+68h+nNumberOfBytesToWrite], 0
0x1800c01c1  xor     esi, esi
0x1800c01c3  mov     [rsp+68h+arg_18], rsi
0x1800c01cb  lea     rdx, [rsp+68h+nNumberOfBytesToWrite]
0x1800c01d3  mov     rcx, r14
0x1800c01d6  call    ??$GetSize@U?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJAEBU?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@AEA_K_N@Z; PerfDiagShared::Serializer::GetSize<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881> const &,unsigned __int64 &,bool)
0x1800c01db  mov     ebx, eax
0x1800c01dd  test    eax, eax
0x1800c01df  js      loc_1800C031C
0x1800c01e5  mov     rdi, [rsp+68h+nNumberOfBytesToWrite]
0x1800c01ed  test    rdi, rdi
0x1800c01f0  jnz     short loc_1800C01FA
0x1800c01f2  lea     ebx, [rsi+1]
0x1800c01f5  jmp     loc_1800C031C
0x1800c01fa  mov     eax, edi
0x1800c01fc  cmp     rdi, rax
0x1800c01ff  jz      short loc_1800C020B
0x1800c0201  mov     ebx, 80070216h
0x1800c0206  jmp     loc_1800C031C
0x1800c020b  mov     rcx, rdi; unsigned __int64
0x1800c020e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c0213  mov     rsi, rax
0x1800c0216  mov     [rsp+68h+arg_18], rax
0x1800c021e  mov     [rsp+68h+nNumberOfBytesToWrite], 0
0x1800c022a  lea     r9, [rsp+68h+nNumberOfBytesToWrite]
0x1800c0232  mov     r8, r14
0x1800c0235  mov     rdx, rdi
0x1800c0238  mov     rcx, rsi
0x1800c023b  call    ??$Write@U?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJPEAX_KAEBU?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@AEA_K_N@Z; PerfDiagShared::Serializer::Write<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(void *,unsigned __int64,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881> const &,unsigned __int64 &,bool)
0x1800c0240  mov     ebx, eax
0x1800c0242  test    eax, eax
0x1800c0244  js      loc_1800C031C
0x1800c024a  mov     r14, [rsp+68h+nNumberOfBytesToWrite]
0x1800c0252  cmp     r14, rdi
0x1800c0255  jbe     short loc_1800C0261
0x1800c0257  mov     ebx, 85541001h
0x1800c025c  jmp     loc_1800C031C
0x1800c0261  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800c026a  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800c0272  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x1800c027a  xor     r9d, r9d; lpSecurityAttributes
0x1800c027d  mov     edx, 40000000h; dwDesiredAccess
0x1800c0282  lea     r8d, [r9+1]; dwShareMode
0x1800c0286  mov     rcx, r15; lpFileName
0x1800c0289  call    cs:__imp_CreateFileW
0x1800c028f  mov     rdi, rax
0x1800c0292  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c0296  jnz     short loc_1800C02AF
0x1800c0298  call    cs:__imp_GetLastError
0x1800c029e  mov     ebx, eax
0x1800c02a0  test    eax, eax
0x1800c02a2  jle     short loc_1800C031C
0x1800c02a4  movzx   ebx, ax
0x1800c02a7  or      ebx, 80070000h
0x1800c02ad  jmp     short loc_1800C031C
0x1800c02af  mov     [rsp+68h+NumberOfBytesWritten], 0
0x1800c02b7  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x1800c02c0  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c02c5  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800c02c8  mov     rdx, rsi; lpBuffer
0x1800c02cb  mov     rcx, rdi; hFile
0x1800c02ce  call    cs:__imp_WriteFile
0x1800c02d4  test    eax, eax
0x1800c02d6  jnz     short loc_1800C02EF
0x1800c02d8  call    cs:__imp_GetLastError
0x1800c02de  mov     ebx, eax
0x1800c02e0  test    eax, eax
0x1800c02e2  jle     short loc_1800C0302
0x1800c02e4  movzx   ebx, ax
0x1800c02e7  or      ebx, 80070000h
0x1800c02ed  jmp     short loc_1800C0302
0x1800c02ef  mov     eax, [rsp+68h+NumberOfBytesWritten]
0x1800c02f3  sub     rax, r14
0x1800c02f6  neg     rax
0x1800c02f9  sbb     eax, eax
0x1800c02fb  mov     ebx, 85541001h
0x1800c0300  and     ebx, eax
0x1800c0302  mov     rcx, rdi; hObject
0x1800c0305  call    cs:__imp_CloseHandle
0x1800c030b  jmp     short loc_1800C031C
0x1800c030d  mov     rsi, [rsp+68h+arg_18]
0x1800c0315  mov     ebx, dword ptr [rsp+68h+nNumberOfBytesToWrite]
0x1800c031c  mov     rcx, rsi; Block
0x1800c031f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c0324  mov     eax, ebx
0x1800c0326  add     rsp, 40h
0x1800c032a  pop     r15
0x1800c032c  pop     r14
0x1800c032e  pop     rdi
0x1800c032f  pop     rsi
0x1800c0330  pop     rbx
0x1800c0331  retn
```
