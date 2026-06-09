# CompressedStreamDump::ParallelDumpTask::AllocateMemory(unsigned __int64)

- ea: `0x1800295f0`
- end: `0x1800296bc`
- name: `?AllocateMemory@ParallelDumpTask@CompressedStreamDump@@AEAAPEAD_K@Z`
- size: `204`
- prototype: `char *(CompressedStreamDump::ParallelDumpTask *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029b30`

## callees

- `0x180002200`
- `0x1800278e8`
- `0x1800289b8`
- `0x1800295f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002967f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002967f`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x180029632`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x180029632`
- `api-ms-win-core-memory-l1-1-2!VirtualAllocExNuma` at `0x18002961d`
- `api-ms-win-core-memory-l1-1-2!VirtualAllocExNuma` at `0x18002961d`

## pseudocode

```c
char *__fastcall CompressedStreamDump::ParallelDumpTask::AllocateMemory(
        CompressedStreamDump::ParallelDumpTask *this,
        SIZE_T a2)
{
  DWORD *v2; // rax
  void *v3; // rcx
  char *result; // rax
  DWORD LastError; // eax
  DWORD v6; // eax
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF

  v2 = (DWORD *)*((_QWORD *)this + 1);
  v3 = (void *)*((_QWORD *)this + 37);
  if ( v2 )
  {
    result = (char *)VirtualAllocExNuma(v3, 0, a2, 0x3000u, 4u, *v2);
    if ( !result )
    {
      LastError = GetLastError();
      CompressedStreamDump::LogMessage(
        (CompressedStreamDump *)4,
        "VirtualAllocExNuma failed. GetLastError: %u.",
        (const char *)LastError);
      std::exception::exception((std::exception *)pExceptionObject, "VirtualAllocExNuma failed.");
      throw (std::exception *)pExceptionObject;
    }
  }
  else
  {
    result = (char *)VirtualAllocEx(v3, 0, a2, 0x3000u, 4u);
    if ( !result )
    {
      v6 = GetLastError();
      CompressedStreamDump::LogMessage(
        (CompressedStreamDump *)4,
        "VirtualAllocEx failed. GetLastError: %u.\n",
        (const char *)v6);
      std::exception::exception((std::exception *)pExceptionObject, "VirtualAllocEx failed!");
      throw (std::exception *)pExceptionObject;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800295f0  sub     rsp, 58h
0x1800295f4  mov     rax, [rcx+8]
0x1800295f8  mov     r8, rdx; dwSize
0x1800295fb  mov     rcx, [rcx+128h]; hProcess
0x180029602  xor     edx, edx; lpAddress
0x180029604  mov     r9d, 3000h; flAllocationType
0x18002960a  test    rax, rax
0x18002960d  jz      short loc_18002962A
0x18002960f  mov     eax, [rax]
0x180029611  mov     [rsp+58h+nndPreferred], eax; nndPreferred
0x180029615  mov     [rsp+58h+flProtect], 4; flProtect
0x18002961d  call    cs:__imp_VirtualAllocExNuma
0x180029623  test    rax, rax
0x180029626  jz      short loc_180029642
0x180029628  jmp     short loc_18002963D
0x18002962a  mov     [rsp+58h+flProtect], 4; flProtect
0x180029632  call    cs:__imp_VirtualAllocEx
0x180029638  test    rax, rax
0x18002963b  jz      short loc_18002967F
0x18002963d  add     rsp, 58h
0x180029641  retn
0x180029642  call    cs:__imp_GetLastError
0x180029648  lea     rdx, aVirtualallocex_0; "VirtualAllocExNuma failed. GetLastError"...
0x18002964f  mov     ecx, 4; this
0x180029654  mov     r8d, eax; char *
0x180029657  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18002965c  lea     rdx, aVirtualallocex_1; "VirtualAllocExNuma failed."
0x180029663  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180029668  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x18002966d  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x180029674  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180029679  call    _CxxThrowException_0
0x18002967f  call    cs:__imp_GetLastError
0x180029685  lea     rdx, aVirtualallocex; "VirtualAllocEx failed. GetLastError: %u"...
0x18002968c  mov     ecx, 4; this
0x180029691  mov     r8d, eax; char *
0x180029694  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180029699  lea     rdx, aVirtualallocex_2; "VirtualAllocEx failed!"
0x1800296a0  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800296a5  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x1800296aa  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x1800296b1  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800296b6  call    _CxxThrowException_0
```
