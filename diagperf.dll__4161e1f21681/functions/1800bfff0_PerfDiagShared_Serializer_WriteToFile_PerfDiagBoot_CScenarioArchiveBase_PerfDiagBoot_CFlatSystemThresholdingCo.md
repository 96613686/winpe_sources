# PerfDiagShared::Serializer::WriteToFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(ushort const *,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419> const &)

- ea: `0x1800bfff0`
- end: `0x1800c018e`
- name: `??$WriteToFile@U?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJPEBGAEBU?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1800c1060`
- `0x1800c25a8`

## callees

- `0x18001f444`
- `0x18001f6a0`
- `0x180056c14`
- `0x180056c20`
- `0x1800bfff0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c00f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c00f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0134`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c012a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c012a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c00e5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c00e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0161`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c0161`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::WriteToFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(
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
  v6 = PerfDiagShared::Serializer::GetSize<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(
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
        v6 = PerfDiagShared::Serializer::Write<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(
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
0x1800bfff0  push    rbx
0x1800bfff2  push    rsi
0x1800bfff3  push    rdi
0x1800bfff4  push    r14
0x1800bfff6  push    r15
0x1800bfff8  sub     rsp, 40h
0x1800bfffc  mov     r14, rdx
0x1800bffff  mov     r15, rcx
0x1800c0002  test    rcx, rcx
0x1800c0005  jnz     short loc_1800C0011
0x1800c0007  mov     eax, 80070057h
0x1800c000c  jmp     loc_1800C0182
0x1800c0011  mov     [rsp+68h+nNumberOfBytesToWrite], 0
0x1800c001d  xor     esi, esi
0x1800c001f  mov     [rsp+68h+arg_18], rsi
0x1800c0027  lea     rdx, [rsp+68h+nNumberOfBytesToWrite]
0x1800c002f  mov     rcx, r14
0x1800c0032  call    ??$GetSize@U?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJAEBU?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@AEA_K_N@Z; PerfDiagShared::Serializer::GetSize<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419> const &,unsigned __int64 &,bool)
0x1800c0037  mov     ebx, eax
0x1800c0039  test    eax, eax
0x1800c003b  js      loc_1800C0178
0x1800c0041  mov     rdi, [rsp+68h+nNumberOfBytesToWrite]
0x1800c0049  test    rdi, rdi
0x1800c004c  jnz     short loc_1800C0056
0x1800c004e  lea     ebx, [rsi+1]
0x1800c0051  jmp     loc_1800C0178
0x1800c0056  mov     eax, edi
0x1800c0058  cmp     rdi, rax
0x1800c005b  jz      short loc_1800C0067
0x1800c005d  mov     ebx, 80070216h
0x1800c0062  jmp     loc_1800C0178
0x1800c0067  mov     rcx, rdi; unsigned __int64
0x1800c006a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c006f  mov     rsi, rax
0x1800c0072  mov     [rsp+68h+arg_18], rax
0x1800c007a  mov     [rsp+68h+nNumberOfBytesToWrite], 0
0x1800c0086  lea     r9, [rsp+68h+nNumberOfBytesToWrite]
0x1800c008e  mov     r8, r14
0x1800c0091  mov     rdx, rdi
0x1800c0094  mov     rcx, rsi
0x1800c0097  call    ??$Write@U?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJPEAX_KAEBU?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@AEA_K_N@Z; PerfDiagShared::Serializer::Write<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(void *,unsigned __int64,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419> const &,unsigned __int64 &,bool)
0x1800c009c  mov     ebx, eax
0x1800c009e  test    eax, eax
0x1800c00a0  js      loc_1800C0178
0x1800c00a6  mov     r14, [rsp+68h+nNumberOfBytesToWrite]
0x1800c00ae  cmp     r14, rdi
0x1800c00b1  jbe     short loc_1800C00BD
0x1800c00b3  mov     ebx, 85541001h
0x1800c00b8  jmp     loc_1800C0178
0x1800c00bd  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800c00c6  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800c00ce  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x1800c00d6  xor     r9d, r9d; lpSecurityAttributes
0x1800c00d9  mov     edx, 40000000h; dwDesiredAccess
0x1800c00de  lea     r8d, [r9+1]; dwShareMode
0x1800c00e2  mov     rcx, r15; lpFileName
0x1800c00e5  call    cs:__imp_CreateFileW
0x1800c00eb  mov     rdi, rax
0x1800c00ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c00f2  jnz     short loc_1800C010B
0x1800c00f4  call    cs:__imp_GetLastError
0x1800c00fa  mov     ebx, eax
0x1800c00fc  test    eax, eax
0x1800c00fe  jle     short loc_1800C0178
0x1800c0100  movzx   ebx, ax
0x1800c0103  or      ebx, 80070000h
0x1800c0109  jmp     short loc_1800C0178
0x1800c010b  mov     [rsp+68h+NumberOfBytesWritten], 0
0x1800c0113  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x1800c011c  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c0121  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800c0124  mov     rdx, rsi; lpBuffer
0x1800c0127  mov     rcx, rdi; hFile
0x1800c012a  call    cs:__imp_WriteFile
0x1800c0130  test    eax, eax
0x1800c0132  jnz     short loc_1800C014B
0x1800c0134  call    cs:__imp_GetLastError
0x1800c013a  mov     ebx, eax
0x1800c013c  test    eax, eax
0x1800c013e  jle     short loc_1800C015E
0x1800c0140  movzx   ebx, ax
0x1800c0143  or      ebx, 80070000h
0x1800c0149  jmp     short loc_1800C015E
0x1800c014b  mov     eax, [rsp+68h+NumberOfBytesWritten]
0x1800c014f  sub     rax, r14
0x1800c0152  neg     rax
0x1800c0155  sbb     eax, eax
0x1800c0157  mov     ebx, 85541001h
0x1800c015c  and     ebx, eax
0x1800c015e  mov     rcx, rdi; hObject
0x1800c0161  call    cs:__imp_CloseHandle
0x1800c0167  jmp     short loc_1800C0178
0x1800c0169  mov     rsi, [rsp+68h+arg_18]
0x1800c0171  mov     ebx, dword ptr [rsp+68h+nNumberOfBytesToWrite]
0x1800c0178  mov     rcx, rsi; Block
0x1800c017b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c0180  mov     eax, ebx
0x1800c0182  add     rsp, 40h
0x1800c0186  pop     r15
0x1800c0188  pop     r14
0x1800c018a  pop     rdi
0x1800c018b  pop     rsi
0x1800c018c  pop     rbx
0x1800c018d  retn
```
