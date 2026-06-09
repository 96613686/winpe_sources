# PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCause,std::allocator<PerfDiagOutput::CRootCause>>>(void *,PerfDiagShared::Serializer::CStringInterner &,std::vector<PerfDiagOutput::CRootCause,std::allocator<PerfDiagOutput::CRootCause>> &)

- ea: `0x1800b270c`
- end: `0x1800b2806`
- name: `??$ReadFromFile@V?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(HANDLE hFile, struct PerfDiagShared::Serializer::CStringInterner *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180043150`
- `0x180043758`
- `0x1800bb0e4`

## callees

- `0x180056c14`
- `0x180056c20`
- `0x1800b2630`
- `0x1800b270c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2780`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800b2735`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800b2735`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b2776`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b2776`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::ReadFromFile<std::vector<PerfDiagOutput::CRootCause>>(
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
        v8 = PerfDiagShared::Serializer::Read<std::vector<PerfDiagOutput::CRootCause>>(a2, (__int64)&v10);
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
0x1800b270c  mov     rax, rsp
0x1800b270f  push    rbx
0x1800b2710  push    rsi
0x1800b2711  push    rdi
0x1800b2712  push    r12
0x1800b2714  push    r14
0x1800b2716  push    r15
0x1800b2718  sub     rsp, 48h
0x1800b271c  mov     r15, r8
0x1800b271f  mov     r12, rdx
0x1800b2722  mov     r14, rcx
0x1800b2725  xor     edi, edi
0x1800b2727  mov     [rsp+78h+var_40], rdi
0x1800b272c  mov     [rax+20h], edi
0x1800b272f  mov     [rax-48h], rdi
0x1800b2733  xor     edx, edx; lpFileSizeHigh
0x1800b2735  call    cs:__imp_GetFileSize
0x1800b273b  mov     ebx, eax
0x1800b273d  lea     r9d, [rbx-1]
0x1800b2741  cmp     r9d, 0FFFFFFFDh
0x1800b2745  ja      loc_1800B27E9
0x1800b274b  mov     esi, ebx
0x1800b274d  mov     ecx, ebx; unsigned __int64
0x1800b274f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b2754  mov     rdi, rax
0x1800b2757  mov     [rsp+78h+var_40], rax
0x1800b275c  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800b2765  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800b276d  mov     r8d, ebx; nNumberOfBytesToRead
0x1800b2770  mov     rdx, rdi; lpBuffer
0x1800b2773  mov     rcx, r14; hFile
0x1800b2776  call    cs:__imp_ReadFile
0x1800b277c  test    eax, eax
0x1800b277e  jnz     short loc_1800B2797
0x1800b2780  call    cs:__imp_GetLastError
0x1800b2786  mov     ebx, eax
0x1800b2788  test    eax, eax
0x1800b278a  jle     short loc_1800B27EE
0x1800b278c  movzx   ebx, ax
0x1800b278f  or      ebx, 80070000h
0x1800b2795  jmp     short loc_1800B27EE
0x1800b2797  cmp     [rsp+78h+NumberOfBytesRead], ebx
0x1800b279e  jz      short loc_1800B27A7
0x1800b27a0  mov     ebx, 85541001h
0x1800b27a5  jmp     short loc_1800B27EE
0x1800b27a7  lea     rax, [rsp+78h+var_48]
0x1800b27ac  mov     [rsp+78h+lpOverlapped], rax; __int64
0x1800b27b1  mov     r9, r15
0x1800b27b4  mov     r8, rsi
0x1800b27b7  mov     rdx, rdi
0x1800b27ba  mov     rcx, r12; struct PerfDiagShared::Serializer::CStringInterner *
0x1800b27bd  call    ??$Read@V?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@@Serializer@PerfDiagShared@@YAJAEAVCStringInterner@01@PEBX_KAEAV?$vector@VCRootCause@PerfDiagOutput@@V?$allocator@VCRootCause@PerfDiagOutput@@@std@@@std@@AEA_K@Z; PerfDiagShared::Serializer::Read<std::vector<PerfDiagOutput::CRootCause>>(PerfDiagShared::Serializer::CStringInterner &,void const *,unsigned __int64,std::vector<PerfDiagOutput::CRootCause> &,unsigned __int64 &)
0x1800b27c2  mov     ebx, eax
0x1800b27c4  test    eax, eax
0x1800b27c6  js      short loc_1800B27EE
0x1800b27c8  mov     rax, [rsp+78h+var_48]
0x1800b27cd  sub     rax, rsi
0x1800b27d0  neg     rax
0x1800b27d3  sbb     eax, eax
0x1800b27d5  mov     ebx, 85541001h
0x1800b27da  and     ebx, eax
0x1800b27dc  jmp     short loc_1800B27EE
0x1800b27de  mov     ebx, dword ptr [rsp+78h+var_48]
0x1800b27e2  mov     rdi, [rsp+78h+var_40]
0x1800b27e7  jmp     short loc_1800B27EE
0x1800b27e9  mov     ebx, 85541002h
0x1800b27ee  mov     rcx, rdi; Block
0x1800b27f1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b27f6  mov     eax, ebx
0x1800b27f8  add     rsp, 48h
0x1800b27fc  pop     r15
0x1800b27fe  pop     r14
0x1800b2800  pop     r12
0x1800b2802  pop     rdi
0x1800b2803  pop     rsi
0x1800b2804  pop     rbx
0x1800b2805  retn
```
