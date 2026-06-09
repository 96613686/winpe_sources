# PerfDiagShared::Serializer::ReadFromFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(void *,PerfDiagShared::Serializer::CStringInterner &,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881> &)

- ea: `0x1800bfca0`
- end: `0x1800bfd9a`
- name: `??$ReadFromFile@U?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAU?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(HANDLE hFile, struct PerfDiagShared::Serializer::CStringInterner *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1800bfda0`

## callees

- `0x18002906c`
- `0x180056c14`
- `0x180056c20`
- `0x1800bfca0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfd14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfd14`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800bfcc9`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800bfcc9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800bfd0a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800bfd0a`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::ReadFromFile<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(
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
        v8 = PerfDiagShared::Serializer::Read<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(
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
0x1800bfca0  mov     rax, rsp
0x1800bfca3  push    rbx
0x1800bfca4  push    rsi
0x1800bfca5  push    rdi
0x1800bfca6  push    r12
0x1800bfca8  push    r14
0x1800bfcaa  push    r15
0x1800bfcac  sub     rsp, 48h
0x1800bfcb0  mov     r15, r8
0x1800bfcb3  mov     r12, rdx
0x1800bfcb6  mov     r14, rcx
0x1800bfcb9  xor     edi, edi
0x1800bfcbb  mov     [rsp+78h+var_40], rdi
0x1800bfcc0  mov     [rax+20h], edi
0x1800bfcc3  mov     [rax-48h], rdi
0x1800bfcc7  xor     edx, edx; lpFileSizeHigh
0x1800bfcc9  call    cs:__imp_GetFileSize
0x1800bfccf  mov     ebx, eax
0x1800bfcd1  lea     r9d, [rbx-1]
0x1800bfcd5  cmp     r9d, 0FFFFFFFDh
0x1800bfcd9  ja      loc_1800BFD7D
0x1800bfcdf  mov     esi, ebx
0x1800bfce1  mov     ecx, ebx; unsigned __int64
0x1800bfce3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800bfce8  mov     rdi, rax
0x1800bfceb  mov     [rsp+78h+var_40], rax
0x1800bfcf0  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800bfcf9  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800bfd01  mov     r8d, ebx; nNumberOfBytesToRead
0x1800bfd04  mov     rdx, rdi; lpBuffer
0x1800bfd07  mov     rcx, r14; hFile
0x1800bfd0a  call    cs:__imp_ReadFile
0x1800bfd10  test    eax, eax
0x1800bfd12  jnz     short loc_1800BFD2B
0x1800bfd14  call    cs:__imp_GetLastError
0x1800bfd1a  mov     ebx, eax
0x1800bfd1c  test    eax, eax
0x1800bfd1e  jle     short loc_1800BFD82
0x1800bfd20  movzx   ebx, ax
0x1800bfd23  or      ebx, 80070000h
0x1800bfd29  jmp     short loc_1800BFD82
0x1800bfd2b  cmp     [rsp+78h+NumberOfBytesRead], ebx
0x1800bfd32  jz      short loc_1800BFD3B
0x1800bfd34  mov     ebx, 85541001h
0x1800bfd39  jmp     short loc_1800BFD82
0x1800bfd3b  lea     rax, [rsp+78h+var_48]
0x1800bfd40  mov     [rsp+78h+lpOverlapped], rax; __int64
0x1800bfd45  mov     r9, r15
0x1800bfd48  mov     r8, rsi
0x1800bfd4b  mov     rdx, rdi
0x1800bfd4e  mov     rcx, r12; struct PerfDiagShared::Serializer::CStringInterner *
0x1800bfd51  call    ??$Read@U?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@@Serializer@PerfDiagShared@@YAJAEAVCStringInterner@01@PEBX_KAEAU?$CScenarioArchiveBase@UCFlatUserThresholdingConfig@PerfDiagBoot@@$0JAGFEEOJ@@PerfDiagBoot@@AEA_K@Z; PerfDiagShared::Serializer::Read<PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881>>(PerfDiagShared::Serializer::CStringInterner &,void const *,unsigned __int64,PerfDiagBoot::CScenarioArchiveBase<PerfDiagBoot::CFlatUserThresholdingConfig,2422555881> &,unsigned __int64 &)
0x1800bfd56  mov     ebx, eax
0x1800bfd58  test    eax, eax
0x1800bfd5a  js      short loc_1800BFD82
0x1800bfd5c  mov     rax, [rsp+78h+var_48]
0x1800bfd61  sub     rax, rsi
0x1800bfd64  neg     rax
0x1800bfd67  sbb     eax, eax
0x1800bfd69  mov     ebx, 85541001h
0x1800bfd6e  and     ebx, eax
0x1800bfd70  jmp     short loc_1800BFD82
0x1800bfd72  mov     ebx, dword ptr [rsp+78h+var_48]
0x1800bfd76  mov     rdi, [rsp+78h+var_40]
0x1800bfd7b  jmp     short loc_1800BFD82
0x1800bfd7d  mov     ebx, 85541002h
0x1800bfd82  mov     rcx, rdi; Block
0x1800bfd85  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800bfd8a  mov     eax, ebx
0x1800bfd8c  add     rsp, 48h
0x1800bfd90  pop     r15
0x1800bfd92  pop     r14
0x1800bfd94  pop     r12
0x1800bfd96  pop     rdi
0x1800bfd97  pop     rsi
0x1800bfd98  pop     rbx
0x1800bfd99  retn
```
