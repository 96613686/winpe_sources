# PerfDiagShared::Serializer::ReadFromFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(void *,PerfDiagShared::Serializer::CStringInterner &,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419> &)

- ea: `0x1800bfb00`
- end: `0x1800bfbfa`
- name: `??$ReadFromFile@U?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAU?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(HANDLE hFile, struct PerfDiagShared::Serializer::CStringInterner *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1800bfc00`

## callees

- `0x180029124`
- `0x180056c14`
- `0x180056c20`
- `0x1800bfb00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfb74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfb74`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800bfb29`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800bfb29`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800bfb6a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800bfb6a`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::ReadFromFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(
        HANDLE hFile,
        struct PerfDiagShared::Serializer::CStringInterner *a2)
{
  void *v4; // rdi
  DWORD FileSize; // ebx
  __int64 v6; // rsi
  signed int LastError; // eax
  signed int v8; // ebx
  __int64 v10; // [rsp+30h] [rbp-48h] BYREF
  void *v11; // [rsp+38h] [rbp-40h]
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+20h] BYREF

  v4 = 0;
  v11 = 0;
  NumberOfBytesRead = 0;
  v10 = 0;
  FileSize = GetFileSize(hFile, 0);
  if ( FileSize - 1 > 0xFFFFFFFD )
  {
    v8 = -2058088446;
  }
  else
  {
    v6 = FileSize;
    v4 = operator new[](FileSize);
    v11 = v4;
    if ( ReadFile(hFile, v4, FileSize, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead == FileSize )
      {
        v8 = PerfDiagShared::Serializer::Read<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(
               a2,
               (__int64)&v10);
        if ( v8 >= 0 )
          v8 = v6 != v10 ? 0x85541001 : 0;
      }
      else
      {
        v8 = -2058088447;
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  operator delete(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800bfb00  mov     rax, rsp
0x1800bfb03  push    rbx
0x1800bfb04  push    rsi
0x1800bfb05  push    rdi
0x1800bfb06  push    r12
0x1800bfb08  push    r14
0x1800bfb0a  push    r15
0x1800bfb0c  sub     rsp, 48h
0x1800bfb10  mov     r15, r8
0x1800bfb13  mov     r12, rdx
0x1800bfb16  mov     r14, rcx
0x1800bfb19  xor     edi, edi
0x1800bfb1b  mov     [rsp+78h+var_40], rdi
0x1800bfb20  mov     [rax+20h], edi
0x1800bfb23  mov     [rax-48h], rdi
0x1800bfb27  xor     edx, edx; lpFileSizeHigh
0x1800bfb29  call    cs:__imp_GetFileSize
0x1800bfb2f  mov     ebx, eax
0x1800bfb31  lea     r9d, [rbx-1]
0x1800bfb35  cmp     r9d, 0FFFFFFFDh
0x1800bfb39  ja      loc_1800BFBDD
0x1800bfb3f  mov     esi, ebx
0x1800bfb41  mov     ecx, ebx; unsigned __int64
0x1800bfb43  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800bfb48  mov     rdi, rax
0x1800bfb4b  mov     [rsp+78h+var_40], rax
0x1800bfb50  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800bfb59  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800bfb61  mov     r8d, ebx; nNumberOfBytesToRead
0x1800bfb64  mov     rdx, rdi; lpBuffer
0x1800bfb67  mov     rcx, r14; hFile
0x1800bfb6a  call    cs:__imp_ReadFile
0x1800bfb70  test    eax, eax
0x1800bfb72  jnz     short loc_1800BFB8B
0x1800bfb74  call    cs:__imp_GetLastError
0x1800bfb7a  mov     ebx, eax
0x1800bfb7c  test    eax, eax
0x1800bfb7e  jle     short loc_1800BFBE2
0x1800bfb80  movzx   ebx, ax
0x1800bfb83  or      ebx, 80070000h
0x1800bfb89  jmp     short loc_1800BFBE2
0x1800bfb8b  cmp     [rsp+78h+NumberOfBytesRead], ebx
0x1800bfb92  jz      short loc_1800BFB9B
0x1800bfb94  mov     ebx, 85541001h
0x1800bfb99  jmp     short loc_1800BFBE2
0x1800bfb9b  lea     rax, [rsp+78h+var_48]
0x1800bfba0  mov     [rsp+78h+lpOverlapped], rax; __int64
0x1800bfba5  mov     r9, r15
0x1800bfba8  mov     r8, rsi
0x1800bfbab  mov     rdx, rdi
0x1800bfbae  mov     rcx, r12; struct PerfDiagShared::Serializer::CStringInterner *
0x1800bfbb1  call    ??$Read@U?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJAEAVCStringInterner@01@PEBX_KAEAU?$CScenarioArchiveBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@$0EOMJBGML@@PerfDiagBoot@@AEA_K@Z; PerfDiagShared::Serializer::Read<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419>>(PerfDiagShared::Serializer::CStringInterner &,void const *,unsigned __int64,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatSystemThresholdingConfig,1321801419> &,unsigned __int64 &)
0x1800bfbb6  mov     ebx, eax
0x1800bfbb8  test    eax, eax
0x1800bfbba  js      short loc_1800BFBE2
0x1800bfbbc  mov     rax, [rsp+78h+var_48]
0x1800bfbc1  sub     rax, rsi
0x1800bfbc4  neg     rax
0x1800bfbc7  sbb     eax, eax
0x1800bfbc9  mov     ebx, 85541001h
0x1800bfbce  and     ebx, eax
0x1800bfbd0  jmp     short loc_1800BFBE2
0x1800bfbd2  mov     ebx, dword ptr [rsp+78h+var_48]
0x1800bfbd6  mov     rdi, [rsp+78h+var_40]
0x1800bfbdb  jmp     short loc_1800BFBE2
0x1800bfbdd  mov     ebx, 85541002h
0x1800bfbe2  mov     rcx, rdi; Block
0x1800bfbe5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800bfbea  mov     eax, ebx
0x1800bfbec  add     rsp, 48h
0x1800bfbf0  pop     r15
0x1800bfbf2  pop     r14
0x1800bfbf4  pop     r12
0x1800bfbf6  pop     rdi
0x1800bfbf7  pop     rsi
0x1800bfbf8  pop     rbx
0x1800bfbf9  retn
```
