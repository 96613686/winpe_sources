# CompressedStreamDump::DumpWriter::Init(void)

- ea: `0x180027938`
- end: `0x180027af6`
- name: `?Init@DumpWriter@CompressedStreamDump@@QEAAXXZ`
- size: `446`
- prototype: `void __fastcall(CompressedStreamDump::DumpWriter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001e8f0`

## callees

- `0x180002200`
- `0x18000f34c`
- `0x1800278e8`
- `0x180027938`
- `0x1800289b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002798e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002798e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ab9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800279bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027a10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800279bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027a10`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180027971`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180027971`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180027956`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180027956`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800279ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027a08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800279ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027a08`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800279e6`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800279e6`

## string_xrefs

- `0x180027a72`: `VirtualAlloc failed to allocate memory for I/O cache buffer. GetLastError: %u.\n`
- `0x180027abf`: `DumpWriter::Init: failed to create IO event for the dump file. GetLastError() returned:%u.\n`
- `0x180027ad3`: `DumpWriter initialize failure!`
- `0x180027a35`: `DumpWriter::Init: failed to ReOpenFile the dump file. GetLastError() returned:%u.\n`
- `0x180027a49`: `DumpWriter init-ReOpenFile failure!`

## pseudocode

```c
void __fastcall CompressedStreamDump::DumpWriter::Init(CompressedStreamDump::DumpWriter *this)
{
  LPVOID v2; // rax
  void *v3; // rcx
  HANDLE EventW; // rax
  void *v5; // rsi
  HANDLE v6; // rbx
  DWORD v7; // ebp
  unsigned int v8; // r8d
  const char *v9; // r9
  HANDLE v10; // rax
  char *v11; // rbp
  HANDLE v12; // rsi
  DWORD v13; // ebx
  DWORD v14; // eax
  DWORD LastError; // eax
  DWORD v16; // eax
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = VirtualAlloc(0, *(unsigned int *)(*(_QWORD *)this + 16LL), 0x3000u, 4u);
  v3 = (void *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = v2;
  if ( v3 )
    VirtualFree(v3, 0, 0x8000u);
  if ( !*((_QWORD *)this + 2) )
  {
    LastError = GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"VirtualAlloc failed to allocate memory for I/O cache buffer. GetLastError: %u.\n",
      (const char *)LastError);
    std::exception::exception((std::exception *)pExceptionObject, "VirtualAlloc failed.");
    throw (std::exception *)pExceptionObject;
  }
  EventW = CreateEventW(0, 1, 1, 0);
  v5 = (void *)*((_QWORD *)this + 4);
  v6 = EventW;
  if ( v5 )
  {
    v7 = GetLastError();
    if ( !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
    SetLastError(v7);
  }
  *((_QWORD *)this + 4) = v6;
  if ( !v6 )
  {
    v16 = GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"DumpWriter::Init: failed to create IO event for the dump file. GetLastError() returned:%u.\n",
      (const char *)v16);
    std::exception::exception((std::exception *)pExceptionObject, "DumpWriter initialize failure!");
    throw (std::exception *)pExceptionObject;
  }
  v10 = ReOpenFile(*(HANDLE *)(*(_QWORD *)this + 24LL), 0xC0000000, 3u, 0x60000000u);
  v11 = (char *)*((_QWORD *)this + 3);
  v12 = v10;
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v13 = GetLastError();
    CloseHandle(v11);
    SetLastError(v13);
  }
  *((_QWORD *)this + 3) = v12;
  if ( (((unsigned __int64)v12 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v14 = GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"DumpWriter::Init: failed to ReOpenFile the dump file. GetLastError() returned:%u.\n",
      (const char *)v14);
    std::exception::exception((std::exception *)pExceptionObject, "DumpWriter init-ReOpenFile failure!");
    throw (std::exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180027938  push    rbx
0x18002793a  push    rbp
0x18002793b  push    rsi
0x18002793c  push    rdi
0x18002793d  sub     rsp, 48h
0x180027941  mov     rax, [rcx]
0x180027944  mov     rdi, rcx
0x180027947  xor     ecx, ecx; lpAddress
0x180027949  mov     r8d, 3000h; flAllocationType
0x18002794f  mov     edx, [rax+10h]; dwSize
0x180027952  lea     r9d, [rcx+4]; flProtect
0x180027956  call    cs:__imp_VirtualAlloc
0x18002795c  mov     rcx, [rdi+10h]; lpAddress
0x180027960  mov     [rdi+10h], rax
0x180027964  test    rcx, rcx
0x180027967  jz      short loc_180027977
0x180027969  xor     edx, edx; dwSize
0x18002796b  mov     r8d, 8000h; dwFreeType
0x180027971  call    cs:__imp_VirtualFree
0x180027977  cmp     qword ptr [rdi+10h], 0
0x18002797c  jz      loc_180027A6C
0x180027982  xor     r9d, r9d; lpName
0x180027985  xor     ecx, ecx; lpEventAttributes
0x180027987  lea     edx, [r9+1]; bManualReset
0x18002798b  mov     r8d, edx; bInitialState
0x18002798e  call    cs:__imp_CreateEventW
0x180027994  mov     rsi, [rdi+20h]
0x180027998  mov     rbx, rax
0x18002799b  test    rsi, rsi
0x18002799e  jz      short loc_1800279C1
0x1800279a0  call    cs:__imp_GetLastError
0x1800279a6  mov     rcx, rsi; hObject
0x1800279a9  mov     ebp, eax
0x1800279ab  call    cs:__imp_CloseHandle
0x1800279b1  test    eax, eax
0x1800279b3  jz      loc_180027AA9
0x1800279b9  mov     ecx, ebp; dwErrCode
0x1800279bb  call    cs:__imp_SetLastError
0x1800279c1  mov     [rdi+20h], rbx
0x1800279c5  test    rbx, rbx
0x1800279c8  jz      loc_180027AB9
0x1800279ce  mov     rcx, [rdi]
0x1800279d1  mov     edx, 0C0000000h; dwDesiredAccess
0x1800279d6  mov     r9d, 60000000h; dwFlagsAndAttributes
0x1800279dc  mov     r8d, 3; dwShareMode
0x1800279e2  mov     rcx, [rcx+18h]; hOriginalFile
0x1800279e6  call    cs:__imp_ReOpenFile
0x1800279ec  mov     rbp, [rdi+18h]
0x1800279f0  mov     rsi, rax
0x1800279f3  lea     rdx, [rbp-1]
0x1800279f7  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800279fb  ja      short loc_180027A16
0x1800279fd  call    cs:__imp_GetLastError
0x180027a03  mov     rcx, rbp; hObject
0x180027a06  mov     ebx, eax
0x180027a08  call    cs:__imp_CloseHandle
0x180027a0e  mov     ecx, ebx; dwErrCode
0x180027a10  call    cs:__imp_SetLastError
0x180027a16  lea     rax, [rsi+1]
0x180027a1a  mov     [rdi+18h], rsi
0x180027a1e  test    rax, 0FFFFFFFFFFFFFFFEh
0x180027a24  jz      short loc_180027A2F
0x180027a26  add     rsp, 48h
0x180027a2a  pop     rdi
0x180027a2b  pop     rsi
0x180027a2c  pop     rbp
0x180027a2d  pop     rbx
0x180027a2e  retn
0x180027a2f  call    cs:__imp_GetLastError
0x180027a35  lea     rdx, aDumpwriterInit_1; "DumpWriter::Init: failed to ReOpenFile "...
0x180027a3c  mov     ecx, 4; this
0x180027a41  mov     r8d, eax; char *
0x180027a44  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180027a49  lea     rdx, aDumpwriterInit_0; "DumpWriter init-ReOpenFile failure!"
0x180027a50  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180027a55  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180027a5a  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x180027a61  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180027a66  call    _CxxThrowException_0
0x180027a6c  call    cs:__imp_GetLastError
0x180027a72  lea     rdx, aVirtualallocFa_0; "VirtualAlloc failed to allocate memory "...
0x180027a79  mov     ecx, 4; this
0x180027a7e  mov     r8d, eax; char *
0x180027a81  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180027a86  lea     rdx, aVirtualallocFa; "VirtualAlloc failed."
0x180027a8d  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180027a92  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180027a97  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x180027a9e  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180027aa3  call    _CxxThrowException_0
0x180027aa9  mov     rcx, [rsp+68h]; this
0x180027aae  mov     edx, 0A0Bh; void *
0x180027ab3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180027ab9  call    cs:__imp_GetLastError
0x180027abf  lea     rdx, aDumpwriterInit; "DumpWriter::Init: failed to create IO e"...
0x180027ac6  mov     ecx, 4; this
0x180027acb  mov     r8d, eax; char *
0x180027ace  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180027ad3  lea     rdx, aDumpwriterInit_2; "DumpWriter initialize failure!"
0x180027ada  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180027adf  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180027ae4  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x180027aeb  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180027af0  call    _CxxThrowException_0
```
