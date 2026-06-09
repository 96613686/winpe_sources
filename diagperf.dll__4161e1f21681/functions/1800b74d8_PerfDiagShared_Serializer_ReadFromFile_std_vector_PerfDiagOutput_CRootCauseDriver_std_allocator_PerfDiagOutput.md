# PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCauseDriver,std::allocator<PerfDiagOutput::CRootCauseDriver>>>(void *,PerfDiagShared::Serializer::CStringInterner &,std::vector<PerfDiagOutput::CRootCauseDriver,std::allocator<PerfDiagOutput::CRootCauseDriver>> &)

- ea: `0x1800b74d8`
- end: `0x1800b75d2`
- name: `??$ReadFromFile@V?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(HANDLE hFile, struct PerfDiagShared::Serializer::CStringInterner *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800433e0`
- `0x180043aac`
- `0x1800bb044`

## callees

- `0x18004ada0`
- `0x180056c14`
- `0x180056c20`
- `0x1800b74d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b754c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b754c`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800b7501`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800b7501`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b7542`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b7542`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCauseDriver>>(
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
        v8 = PerfDiagShared::Serializer::Read<std::vector<PerfDiagOutput::CRootCauseDriver>>(a2, (__int64)&v10);
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
0x1800b74d8  mov     rax, rsp
0x1800b74db  push    rbx
0x1800b74dc  push    rsi
0x1800b74dd  push    rdi
0x1800b74de  push    r12
0x1800b74e0  push    r14
0x1800b74e2  push    r15
0x1800b74e4  sub     rsp, 48h
0x1800b74e8  mov     r15, r8
0x1800b74eb  mov     r12, rdx
0x1800b74ee  mov     r14, rcx
0x1800b74f1  xor     edi, edi
0x1800b74f3  mov     [rsp+78h+var_40], rdi
0x1800b74f8  mov     [rax+20h], edi
0x1800b74fb  mov     [rax-48h], rdi
0x1800b74ff  xor     edx, edx; lpFileSizeHigh
0x1800b7501  call    cs:__imp_GetFileSize
0x1800b7507  mov     ebx, eax
0x1800b7509  lea     r9d, [rbx-1]
0x1800b750d  cmp     r9d, 0FFFFFFFDh
0x1800b7511  ja      loc_1800B75B5
0x1800b7517  mov     esi, ebx
0x1800b7519  mov     ecx, ebx; unsigned __int64
0x1800b751b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b7520  mov     rdi, rax
0x1800b7523  mov     [rsp+78h+var_40], rax
0x1800b7528  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800b7531  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800b7539  mov     r8d, ebx; nNumberOfBytesToRead
0x1800b753c  mov     rdx, rdi; lpBuffer
0x1800b753f  mov     rcx, r14; hFile
0x1800b7542  call    cs:__imp_ReadFile
0x1800b7548  test    eax, eax
0x1800b754a  jnz     short loc_1800B7563
0x1800b754c  call    cs:__imp_GetLastError
0x1800b7552  mov     ebx, eax
0x1800b7554  test    eax, eax
0x1800b7556  jle     short loc_1800B75BA
0x1800b7558  movzx   ebx, ax
0x1800b755b  or      ebx, 80070000h
0x1800b7561  jmp     short loc_1800B75BA
0x1800b7563  cmp     [rsp+78h+NumberOfBytesRead], ebx
0x1800b756a  jz      short loc_1800B7573
0x1800b756c  mov     ebx, 85541001h
0x1800b7571  jmp     short loc_1800B75BA
0x1800b7573  lea     rax, [rsp+78h+var_48]
0x1800b7578  mov     [rsp+78h+lpOverlapped], rax; __int64
0x1800b757d  mov     r9, r15
0x1800b7580  mov     r8, rsi
0x1800b7583  mov     rdx, rdi
0x1800b7586  mov     rcx, r12; struct PerfDiagShared::Serializer::CStringInterner *
0x1800b7589  call    ??$Read@V?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJAEAVCStringInterner@01@PEBX_KAEAV?$vector@UCRootCauseDriver@PerfDiagOutput@@V?$allocator@UCRootCauseDriver@PerfDiagOutput@@@std@@@std@@AEA_K@Z; PerfDiagShared::Serializer::Read<std::vector<PerfDiagOutput::CRootCauseDriver>>(PerfDiagShared::Serializer::CStringInterner &,void const *,unsigned __int64,std::vector<PerfDiagOutput::CRootCauseDriver> &,unsigned __int64 &)
0x1800b758e  mov     ebx, eax
0x1800b7590  test    eax, eax
0x1800b7592  js      short loc_1800B75BA
0x1800b7594  mov     rax, [rsp+78h+var_48]
0x1800b7599  sub     rax, rsi
0x1800b759c  neg     rax
0x1800b759f  sbb     eax, eax
0x1800b75a1  mov     ebx, 85541001h
0x1800b75a6  and     ebx, eax
0x1800b75a8  jmp     short loc_1800B75BA
0x1800b75aa  mov     ebx, dword ptr [rsp+78h+var_48]
0x1800b75ae  mov     rdi, [rsp+78h+var_40]
0x1800b75b3  jmp     short loc_1800B75BA
0x1800b75b5  mov     ebx, 85541002h
0x1800b75ba  mov     rcx, rdi; Block
0x1800b75bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b75c2  mov     eax, ebx
0x1800b75c4  add     rsp, 48h
0x1800b75c8  pop     r15
0x1800b75ca  pop     r14
0x1800b75cc  pop     r12
0x1800b75ce  pop     rdi
0x1800b75cf  pop     rsi
0x1800b75d0  pop     rbx
0x1800b75d1  retn
```
