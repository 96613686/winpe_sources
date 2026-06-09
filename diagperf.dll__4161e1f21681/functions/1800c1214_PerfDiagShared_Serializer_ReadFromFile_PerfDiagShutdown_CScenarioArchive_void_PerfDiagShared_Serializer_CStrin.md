# PerfDiagShared::Serializer::ReadFromFile<PerfDiagShutdown::CScenarioArchive>(void *,PerfDiagShared::Serializer::CStringInterner &,PerfDiagShutdown::CScenarioArchive &)

- ea: `0x1800c1214`
- end: `0x1800c130e`
- name: `??$ReadFromFile@UCScenarioArchive@PerfDiagShutdown@@@Serializer@PerfDiagShared@@YAJPEAXAEAVCStringInterner@01@AEAUCScenarioArchive@PerfDiagShutdown@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(HANDLE hFile, struct PerfDiagShared::Serializer::CStringInterner *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800c1314`

## callees

- `0x180056c14`
- `0x180056c20`
- `0x1800c115c`
- `0x1800c1214`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1288`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800c123d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800c123d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c127e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c127e`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::Serializer::ReadFromFile<PerfDiagShutdown::CScenarioArchive>(
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
        v8 = PerfDiagShared::Serializer::Read<PerfDiagShutdown::CScenarioArchive>(a2, (__int64)&v10);
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
0x1800c1214  mov     rax, rsp
0x1800c1217  push    rbx
0x1800c1218  push    rsi
0x1800c1219  push    rdi
0x1800c121a  push    r12
0x1800c121c  push    r14
0x1800c121e  push    r15
0x1800c1220  sub     rsp, 48h
0x1800c1224  mov     r15, r8
0x1800c1227  mov     r12, rdx
0x1800c122a  mov     r14, rcx
0x1800c122d  xor     edi, edi
0x1800c122f  mov     [rsp+78h+var_40], rdi
0x1800c1234  mov     [rax+20h], edi
0x1800c1237  mov     [rax-48h], rdi
0x1800c123b  xor     edx, edx; lpFileSizeHigh
0x1800c123d  call    cs:__imp_GetFileSize
0x1800c1243  mov     ebx, eax
0x1800c1245  lea     r9d, [rbx-1]
0x1800c1249  cmp     r9d, 0FFFFFFFDh
0x1800c124d  ja      loc_1800C12F1
0x1800c1253  mov     esi, ebx
0x1800c1255  mov     ecx, ebx; unsigned __int64
0x1800c1257  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c125c  mov     rdi, rax
0x1800c125f  mov     [rsp+78h+var_40], rax
0x1800c1264  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800c126d  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800c1275  mov     r8d, ebx; nNumberOfBytesToRead
0x1800c1278  mov     rdx, rdi; lpBuffer
0x1800c127b  mov     rcx, r14; hFile
0x1800c127e  call    cs:__imp_ReadFile
0x1800c1284  test    eax, eax
0x1800c1286  jnz     short loc_1800C129F
0x1800c1288  call    cs:__imp_GetLastError
0x1800c128e  mov     ebx, eax
0x1800c1290  test    eax, eax
0x1800c1292  jle     short loc_1800C12F6
0x1800c1294  movzx   ebx, ax
0x1800c1297  or      ebx, 80070000h
0x1800c129d  jmp     short loc_1800C12F6
0x1800c129f  cmp     [rsp+78h+NumberOfBytesRead], ebx
0x1800c12a6  jz      short loc_1800C12AF
0x1800c12a8  mov     ebx, 85541001h
0x1800c12ad  jmp     short loc_1800C12F6
0x1800c12af  lea     rax, [rsp+78h+var_48]
0x1800c12b4  mov     [rsp+78h+lpOverlapped], rax; __int64
0x1800c12b9  mov     r9, r15
0x1800c12bc  mov     r8, rsi
0x1800c12bf  mov     rdx, rdi
0x1800c12c2  mov     rcx, r12; struct PerfDiagShared::Serializer::CStringInterner *
0x1800c12c5  call    ??$Read@UCScenarioArchive@PerfDiagShutdown@@@Serializer@PerfDiagShared@@YAJAEAVCStringInterner@01@PEBX_KAEAUCScenarioArchive@PerfDiagShutdown@@AEA_K@Z; PerfDiagShared::Serializer::Read<PerfDiagShutdown::CScenarioArchive>(PerfDiagShared::Serializer::CStringInterner &,void const *,unsigned __int64,PerfDiagShutdown::CScenarioArchive &,unsigned __int64 &)
0x1800c12ca  mov     ebx, eax
0x1800c12cc  test    eax, eax
0x1800c12ce  js      short loc_1800C12F6
0x1800c12d0  mov     rax, [rsp+78h+var_48]
0x1800c12d5  sub     rax, rsi
0x1800c12d8  neg     rax
0x1800c12db  sbb     eax, eax
0x1800c12dd  mov     ebx, 85541001h
0x1800c12e2  and     ebx, eax
0x1800c12e4  jmp     short loc_1800C12F6
0x1800c12e6  mov     ebx, dword ptr [rsp+78h+var_48]
0x1800c12ea  mov     rdi, [rsp+78h+var_40]
0x1800c12ef  jmp     short loc_1800C12F6
0x1800c12f1  mov     ebx, 85541002h
0x1800c12f6  mov     rcx, rdi; Block
0x1800c12f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c12fe  mov     eax, ebx
0x1800c1300  add     rsp, 48h
0x1800c1304  pop     r15
0x1800c1306  pop     r14
0x1800c1308  pop     r12
0x1800c130a  pop     rdi
0x1800c130b  pop     rsi
0x1800c130c  pop     rbx
0x1800c130d  retn
```
