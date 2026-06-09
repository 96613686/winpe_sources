# PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCause,std::allocator<PerfDiagOutput::CRootCause>>>(void *,std::vector<PerfDiagOutput::CRootCause,std::allocator<PerfDiagOutput::CRootCause>> const &)

- ea: `0x1800b2c0c`
- end: `0x1800b2d2b`
- name: `??$WriteToFile@V?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180043150`
- `0x180043758`

## callees

- `0x180056c14`
- `0x180056c20`
- `0x1800b2178`
- `0x1800b28bc`
- `0x1800b2c0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2cdd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b2cd3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b2cd3`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCause>>(
        HANDLE hFile,
        __int64 a2)
{
  void *v3; // rsi
  signed int v4; // ebx
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int64 v8; // [rsp+78h] [rbp+20h] BYREF

  v8 = 0;
  v3 = 0;
  v4 = PerfDiagShared::Serializer::GetSize<std::vector<PerfDiagOutput::CRootCause>>(a2, &v8);
  if ( v4 >= 0 )
  {
    if ( v8 )
    {
      if ( v8 == (unsigned int)v8 )
      {
        try
        {
          v3 = operator new[](v8);
        }
        catch ( std::bad_alloc )
        {
          LODWORD(v8) = -2147024882;
          v3 = 0;
          v4 = -2147024882;
          goto LABEL_11;
        }
        v4 = PerfDiagShared::Serializer::Write<std::vector<PerfDiagOutput::CRootCause>>();
        if ( v4 >= 0 )
        {
          NumberOfBytesWritten = 0;
          if ( WriteFile(hFile, v3, 0, &NumberOfBytesWritten, 0) )
          {
            v4 = NumberOfBytesWritten != 0 ? 0x85541001 : 0;
          }
          else
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
      else
      {
        v4 = -2147024362;
      }
    }
    else
    {
      v4 = 1;
    }
  }
LABEL_11:
  operator delete(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800b2c0c  mov     [rsp+arg_0], rbx
0x1800b2c11  push    rsi
0x1800b2c12  push    r14
0x1800b2c14  push    r15
0x1800b2c16  sub     rsp, 40h
0x1800b2c1a  mov     r14, rdx
0x1800b2c1d  mov     r15, rcx
0x1800b2c20  mov     [rsp+58h+arg_18], 0
0x1800b2c29  xor     esi, esi
0x1800b2c2b  mov     qword ptr [rsp+58h+nNumberOfBytesToWrite], rsi
0x1800b2c30  lea     rdx, [rsp+58h+arg_18]
0x1800b2c35  mov     rcx, r14
0x1800b2c38  call    ??$GetSize@V?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJAEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@AEA_K_N@Z; PerfDiagShared::Serializer::GetSize<std::vector<PerfDiagOutput::CRootCause>>(std::vector<PerfDiagOutput::CRootCause> const &,unsigned __int64 &,bool)
0x1800b2c3d  mov     ebx, eax
0x1800b2c3f  test    eax, eax
0x1800b2c41  js      loc_1800B2D12
0x1800b2c47  cmp     [rsp+58h+arg_18], rsi
0x1800b2c4c  jnz     short loc_1800B2C56
0x1800b2c4e  lea     ebx, [rsi+1]
0x1800b2c51  jmp     loc_1800B2D12
0x1800b2c56  mov     eax, dword ptr [rsp+58h+arg_18]
0x1800b2c5a  cmp     [rsp+58h+arg_18], rax
0x1800b2c5f  jz      short loc_1800B2C6B
0x1800b2c61  mov     ebx, 80070216h
0x1800b2c66  jmp     loc_1800B2D12
0x1800b2c6b  mov     rcx, [rsp+58h+arg_18]; unsigned __int64
0x1800b2c70  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b2c75  mov     rsi, rax
0x1800b2c78  mov     qword ptr [rsp+58h+nNumberOfBytesToWrite], rax
0x1800b2c7d  mov     qword ptr [rsp+58h+nNumberOfBytesToWrite], 0
0x1800b2c86  lea     r9, [rsp+58h+nNumberOfBytesToWrite]
0x1800b2c8b  mov     r8, r14
0x1800b2c8e  mov     rdx, [rsp+58h+arg_18]
0x1800b2c93  mov     rcx, rsi
0x1800b2c96  call    ??$Write@V?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAX_KAEBV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@AEA_K_N@Z; PerfDiagShared::Serializer::Write<std::vector<PerfDiagOutput::CRootCause>>(void *,unsigned __int64,std::vector<PerfDiagOutput::CRootCause> const &,unsigned __int64 &,bool)
0x1800b2c9b  mov     ebx, eax
0x1800b2c9d  test    eax, eax
0x1800b2c9f  js      short loc_1800B2D12
0x1800b2ca1  mov     rbx, qword ptr [rsp+58h+nNumberOfBytesToWrite]
0x1800b2ca6  cmp     rbx, [rsp+58h+arg_18]
0x1800b2cab  jbe     short loc_1800B2CB4
0x1800b2cad  mov     ebx, 85541001h
0x1800b2cb2  jmp     short loc_1800B2D12
0x1800b2cb4  mov     [rsp+58h+NumberOfBytesWritten], 0
0x1800b2cbc  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800b2cc5  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800b2cca  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800b2ccd  mov     rdx, rsi; lpBuffer
0x1800b2cd0  mov     rcx, r15; hFile
0x1800b2cd3  call    cs:__imp_WriteFile
0x1800b2cd9  test    eax, eax
0x1800b2cdb  jnz     short loc_1800B2CF4
0x1800b2cdd  call    cs:__imp_GetLastError
0x1800b2ce3  mov     ebx, eax
0x1800b2ce5  test    eax, eax
0x1800b2ce7  jle     short loc_1800B2D12
0x1800b2ce9  movzx   ebx, ax
0x1800b2cec  or      ebx, 80070000h
0x1800b2cf2  jmp     short loc_1800B2D12
0x1800b2cf4  mov     eax, [rsp+58h+NumberOfBytesWritten]
0x1800b2cf8  sub     rax, rbx
0x1800b2cfb  neg     rax
0x1800b2cfe  sbb     eax, eax
0x1800b2d00  mov     ebx, 85541001h
0x1800b2d05  and     ebx, eax
0x1800b2d07  jmp     short loc_1800B2D12
0x1800b2d09  mov     rsi, qword ptr [rsp+58h+nNumberOfBytesToWrite]
0x1800b2d0e  mov     ebx, dword ptr [rsp+58h+arg_18]
0x1800b2d12  mov     rcx, rsi; Block
0x1800b2d15  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b2d1a  mov     eax, ebx
0x1800b2d1c  mov     rbx, [rsp+58h+arg_0]
0x1800b2d21  add     rsp, 40h
0x1800b2d25  pop     r15
0x1800b2d27  pop     r14
0x1800b2d29  pop     rsi
0x1800b2d2a  retn
```
