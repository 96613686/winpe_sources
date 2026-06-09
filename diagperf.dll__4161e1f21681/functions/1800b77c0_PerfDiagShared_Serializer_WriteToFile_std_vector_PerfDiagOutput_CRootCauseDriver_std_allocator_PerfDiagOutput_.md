# PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCauseDriver,std::allocator<PerfDiagOutput::CRootCauseDriver>>>(void *,std::vector<PerfDiagOutput::CRootCauseDriver,std::allocator<PerfDiagOutput::CRootCauseDriver>> const &)

- ea: `0x1800b77c0`
- end: `0x1800b78df`
- name: `??$WriteToFile@V?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEBV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800433e0`
- `0x180043aac`

## callees

- `0x1800472c8`
- `0x180056c14`
- `0x180056c20`
- `0x1800b7268`
- `0x1800b77c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7891`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b7887`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b7887`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::WriteToFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(
        HANDLE hFile,
        __int64 a2)
{
  void *v4; // rsi
  signed int v5; // ebx
  __int64 v6; // rbx
  signed int LastError; // eax
  DWORD nNumberOfBytesToWrite[10]; // [rsp+30h] [rbp-28h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int64 v11; // [rsp+78h] [rbp+20h] BYREF

  v11 = 0;
  v4 = 0;
  *(_QWORD *)nNumberOfBytesToWrite = 0;
  v5 = PerfDiagShared::Serializer::GetSize<std::vector<PerfDiagOutput::CRootCauseDriver>>(a2, &v11);
  if ( v5 >= 0 )
  {
    if ( v11 )
    {
      if ( v11 == (unsigned int)v11 )
      {
        v4 = operator new[](v11);
        *(_QWORD *)nNumberOfBytesToWrite = 0;
        v5 = PerfDiagShared::Serializer::Write<std::vector<PerfDiagOutput::CRootCauseDriver>>(
               v4,
               v11,
               a2,
               nNumberOfBytesToWrite);
        if ( v5 >= 0 )
        {
          v6 = *(_QWORD *)nNumberOfBytesToWrite;
          if ( *(_QWORD *)nNumberOfBytesToWrite <= v11 )
          {
            NumberOfBytesWritten = 0;
            if ( WriteFile(hFile, v4, nNumberOfBytesToWrite[0], &NumberOfBytesWritten, 0) )
            {
              v5 = v6 != NumberOfBytesWritten ? 0x85541001 : 0;
            }
            else
            {
              LastError = GetLastError();
              v5 = LastError;
              if ( LastError > 0 )
                v5 = (unsigned __int16)LastError | 0x80070000;
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
  operator delete(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b77c0  mov     [rsp+arg_0], rbx
0x1800b77c5  push    rsi
0x1800b77c6  push    r14
0x1800b77c8  push    r15
0x1800b77ca  sub     rsp, 40h
0x1800b77ce  mov     r14, rdx
0x1800b77d1  mov     r15, rcx
0x1800b77d4  mov     [rsp+58h+arg_18], 0
0x1800b77dd  xor     esi, esi
0x1800b77df  mov     qword ptr [rsp+58h+nNumberOfBytesToWrite], rsi
0x1800b77e4  lea     rdx, [rsp+58h+arg_18]
0x1800b77e9  mov     rcx, r14
0x1800b77ec  call    ??$GetSize@V?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJAEBV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@AEA_K_N@Z; PerfDiagShared::Serializer::GetSize<std::vector<PerfDiagOutput::CRootCauseDriver>>(std::vector<PerfDiagOutput::CRootCauseDriver> const &,unsigned __int64 &,bool)
0x1800b77f1  mov     ebx, eax
0x1800b77f3  test    eax, eax
0x1800b77f5  js      loc_1800B78C6
0x1800b77fb  cmp     [rsp+58h+arg_18], rsi
0x1800b7800  jnz     short loc_1800B780A
0x1800b7802  lea     ebx, [rsi+1]
0x1800b7805  jmp     loc_1800B78C6
0x1800b780a  mov     eax, dword ptr [rsp+58h+arg_18]
0x1800b780e  cmp     [rsp+58h+arg_18], rax
0x1800b7813  jz      short loc_1800B781F
0x1800b7815  mov     ebx, 80070216h
0x1800b781a  jmp     loc_1800B78C6
0x1800b781f  mov     rcx, [rsp+58h+arg_18]; unsigned __int64
0x1800b7824  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b7829  mov     rsi, rax
0x1800b782c  mov     qword ptr [rsp+58h+nNumberOfBytesToWrite], rax
0x1800b7831  mov     qword ptr [rsp+58h+nNumberOfBytesToWrite], 0
0x1800b783a  lea     r9, [rsp+58h+nNumberOfBytesToWrite]
0x1800b783f  mov     r8, r14
0x1800b7842  mov     rdx, [rsp+58h+arg_18]
0x1800b7847  mov     rcx, rsi
0x1800b784a  call    ??$Write@V?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAX_KAEBV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@AEA_K_N@Z; PerfDiagShared::Serializer::Write<std::vector<PerfDiagOutput::CRootCauseDriver>>(void *,unsigned __int64,std::vector<PerfDiagOutput::CRootCauseDriver> const &,unsigned __int64 &,bool)
0x1800b784f  mov     ebx, eax
0x1800b7851  test    eax, eax
0x1800b7853  js      short loc_1800B78C6
0x1800b7855  mov     rbx, qword ptr [rsp+58h+nNumberOfBytesToWrite]
0x1800b785a  cmp     rbx, [rsp+58h+arg_18]
0x1800b785f  jbe     short loc_1800B7868
0x1800b7861  mov     ebx, 85541001h
0x1800b7866  jmp     short loc_1800B78C6
0x1800b7868  mov     [rsp+58h+NumberOfBytesWritten], 0
0x1800b7870  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800b7879  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800b787e  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800b7881  mov     rdx, rsi; lpBuffer
0x1800b7884  mov     rcx, r15; hFile
0x1800b7887  call    cs:__imp_WriteFile
0x1800b788d  test    eax, eax
0x1800b788f  jnz     short loc_1800B78A8
0x1800b7891  call    cs:__imp_GetLastError
0x1800b7897  mov     ebx, eax
0x1800b7899  test    eax, eax
0x1800b789b  jle     short loc_1800B78C6
0x1800b789d  movzx   ebx, ax
0x1800b78a0  or      ebx, 80070000h
0x1800b78a6  jmp     short loc_1800B78C6
0x1800b78a8  mov     eax, [rsp+58h+NumberOfBytesWritten]
0x1800b78ac  sub     rax, rbx
0x1800b78af  neg     rax
0x1800b78b2  sbb     eax, eax
0x1800b78b4  mov     ebx, 85541001h
0x1800b78b9  and     ebx, eax
0x1800b78bb  jmp     short loc_1800B78C6
0x1800b78bd  mov     rsi, qword ptr [rsp+58h+nNumberOfBytesToWrite]
0x1800b78c2  mov     ebx, dword ptr [rsp+58h+arg_18]
0x1800b78c6  mov     rcx, rsi; Block
0x1800b78c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b78ce  mov     eax, ebx
0x1800b78d0  mov     rbx, [rsp+58h+arg_0]
0x1800b78d5  add     rsp, 40h
0x1800b78d9  pop     r15
0x1800b78db  pop     r14
0x1800b78dd  pop     rsi
0x1800b78de  retn
```
