# PerfDiagShared::Serializer::ReadFromFile<PerfDiagSuspend::CScenarioArchive>(void *,PerfDiagShared::Serializer::CStringInterner &,PerfDiagSuspend::CScenarioArchive &)

- ea: `0x18008ba7c`
- end: `0x18008bb76`
- name: `??$ReadFromFile@UCScenarioArchive@PerfDiagSuspend@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAUCScenarioArchive@PerfDiagSuspend@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(HANDLE hFile, struct PerfDiagShared::Serializer::CStringInterner *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18008bb7c`

## callees

- `0x180056c14`
- `0x180056c20`
- `0x18008b9c4`
- `0x18008ba7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008baf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008baf0`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18008baa5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18008baa5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008bae6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18008bae6`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::ReadFromFile<PerfDiagSuspend::CScenarioArchive>(
        HANDLE hFile,
        struct PerfDiagShared::Serializer::CStringInterner *a2)
{
  void *v4; // rdi
  DWORD FileSize; // eax
  DWORD v6; // ebx
  __int64 v7; // rsi
  BOOL v8; // eax
  signed int LastError; // eax
  signed int v10; // ebx
  __int64 v12; // [rsp+30h] [rbp-48h] BYREF
  void *v13; // [rsp+38h] [rbp-40h]
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+20h] BYREF

  v4 = 0;
  v13 = 0;
  NumberOfBytesRead = 0;
  v12 = 0;
  FileSize = GetFileSize(hFile, 0);
  v6 = FileSize;
  if ( FileSize - 1 > 0xFFFFFFFD )
  {
    v10 = -2058088446;
  }
  else
  {
    try
    {
      v7 = FileSize;
      v4 = operator new[](FileSize);
      v13 = v4;
      v8 = ReadFile(hFile, v4, v6, &NumberOfBytesRead, 0);
    }
    catch ( std::bad_alloc )
    {
      LODWORD(v12) = -2147024882;
      v10 = -2147024882;
      v4 = v13;
      goto LABEL_11;
    }
    if ( v8 )
    {
      if ( NumberOfBytesRead == v6 )
      {
        v10 = PerfDiagShared::Serializer::Read<PerfDiagSuspend::CScenarioArchive>(a2, (__int64)&v12);
        if ( v10 >= 0 )
          v10 = v7 != v12 ? 0x85541001 : 0;
      }
      else
      {
        v10 = -2058088447;
      }
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
  }
LABEL_11:
  operator delete(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18008ba7c  mov     rax, rsp
0x18008ba7f  push    rbx
0x18008ba80  push    rsi
0x18008ba81  push    rdi
0x18008ba82  push    r12
0x18008ba84  push    r14
0x18008ba86  push    r15
0x18008ba88  sub     rsp, 48h
0x18008ba8c  mov     r15, r8
0x18008ba8f  mov     r12, rdx
0x18008ba92  mov     r14, rcx
0x18008ba95  xor     edi, edi
0x18008ba97  mov     [rsp+78h+var_40], rdi
0x18008ba9c  mov     [rax+20h], edi
0x18008ba9f  mov     [rax-48h], rdi
0x18008baa3  xor     edx, edx; lpFileSizeHigh
0x18008baa5  call    cs:__imp_GetFileSize
0x18008baab  mov     ebx, eax
0x18008baad  lea     r9d, [rbx-1]
0x18008bab1  cmp     r9d, 0FFFFFFFDh
0x18008bab5  ja      loc_18008BB59
0x18008babb  mov     esi, ebx
0x18008babd  mov     ecx, ebx; unsigned __int64
0x18008babf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008bac4  mov     rdi, rax
0x18008bac7  mov     [rsp+78h+var_40], rax
0x18008bacc  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18008bad5  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18008badd  mov     r8d, ebx; nNumberOfBytesToRead
0x18008bae0  mov     rdx, rdi; lpBuffer
0x18008bae3  mov     rcx, r14; hFile
0x18008bae6  call    cs:__imp_ReadFile
0x18008baec  test    eax, eax
0x18008baee  jnz     short loc_18008BB07
0x18008baf0  call    cs:__imp_GetLastError
0x18008baf6  mov     ebx, eax
0x18008baf8  test    eax, eax
0x18008bafa  jle     short loc_18008BB5E
0x18008bafc  movzx   ebx, ax
0x18008baff  or      ebx, 80070000h
0x18008bb05  jmp     short loc_18008BB5E
0x18008bb07  cmp     [rsp+78h+NumberOfBytesRead], ebx
0x18008bb0e  jz      short loc_18008BB17
0x18008bb10  mov     ebx, 85541001h
0x18008bb15  jmp     short loc_18008BB5E
0x18008bb17  lea     rax, [rsp+78h+var_48]
0x18008bb1c  mov     [rsp+78h+lpOverlapped], rax; __int64
0x18008bb21  mov     r9, r15
0x18008bb24  mov     r8, rsi
0x18008bb27  mov     rdx, rdi
0x18008bb2a  mov     rcx, r12; struct PerfDiagShared::Serializer::CStringInterner *
0x18008bb2d  call    ??$Read@UCScenarioArchive@PerfDiagSuspend@@@Serializer@PerfDiagShared@@YAJAEAVCStringInterner@01@PEBX_KAEAUCScenarioArchive@PerfDiagSuspend@@AEA_K@Z; PerfDiagShared::Serializer::Read<PerfDiagSuspend::CScenarioArchive>(PerfDiagShared::Serializer::CStringInterner &,void const *,unsigned __int64,PerfDiagSuspend::CScenarioArchive &,unsigned __int64 &)
0x18008bb32  mov     ebx, eax
0x18008bb34  test    eax, eax
0x18008bb36  js      short loc_18008BB5E
0x18008bb38  mov     rax, [rsp+78h+var_48]
0x18008bb3d  sub     rax, rsi
0x18008bb40  neg     rax
0x18008bb43  sbb     eax, eax
0x18008bb45  mov     ebx, 85541001h
0x18008bb4a  and     ebx, eax
0x18008bb4c  jmp     short loc_18008BB5E
0x18008bb4e  mov     ebx, dword ptr [rsp+78h+var_48]
0x18008bb52  mov     rdi, [rsp+78h+var_40]
0x18008bb57  jmp     short loc_18008BB5E
0x18008bb59  mov     ebx, 85541002h
0x18008bb5e  mov     rcx, rdi; Block
0x18008bb61  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008bb66  mov     eax, ebx
0x18008bb68  add     rsp, 48h
0x18008bb6c  pop     r15
0x18008bb6e  pop     r14
0x18008bb70  pop     r12
0x18008bb72  pop     rdi
0x18008bb73  pop     rsi
0x18008bb74  pop     rbx
0x18008bb75  retn
```
