# CompressedStreamDump::DumpWriter::Init(void)

- ea: `0x180410ff4`
- end: `0x180411179`
- name: `?Init@DumpWriter@CompressedStreamDump@@QEAAXXZ`
- size: `389`
- prototype: `void __fastcall(CompressedStreamDump::DumpWriter *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180409874`

## callees

- `0x1800bb9fc`
- `0x1800d6560`
- `0x1800f2d88`
- `0x180162c3c`
- `0x1803fc9ac`
- `0x180410ff4`
- `0x180411be8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180411042`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180411042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804110b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804110f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804110b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804110f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180411136`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180411013`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180411013`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x18041107d`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x18041107d`

## string_xrefs

- `0x1804110ff`: `VirtualAlloc failed to allocate memory for I/O cache buffer. GetLastError: %u.\n`
- `0x1804110d0`: `DumpWriter init-ReOpenFile failure!`
- `0x1804110bc`: `DumpWriter::Init: failed to ReOpenFile the dump file. GetLastError() returned:%u.\n`
- `0x180411156`: `DumpWriter initialize failure!`
- `0x180411142`: `DumpWriter::Init: failed to create IO event for the dump file. GetLastError() returned:%u.\n`

## pseudocode

```c
void __fastcall CompressedStreamDump::DumpWriter::Init(CompressedStreamDump::DumpWriter *this)
{
  LPVOID v2; // rax
  HANDLE EventW; // rax
  HANDLE v4; // rax
  DWORD v5; // eax
  DWORD LastError; // eax
  DWORD v7; // eax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  v2 = VirtualAlloc(0, *(unsigned int *)(*(_QWORD *)this + 16LL), 0x3000u, 4u);
  wistd::unique_ptr<void,wil::virtualalloc_deleter>::reset((char *)this + 16, v2);
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
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 32,
    EventW);
  if ( !*((_QWORD *)this + 4) )
  {
    v7 = GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"DumpWriter::Init: failed to create IO event for the dump file. GetLastError() returned:%u.\n",
      (const char *)v7);
    std::exception::exception((std::exception *)pExceptionObject, "DumpWriter initialize failure!");
    throw (std::exception *)pExceptionObject;
  }
  v4 = ReOpenFile(*(HANDLE *)(*(_QWORD *)this + 24LL), 0xC0000000, 3u, 0x60000000u);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 24,
    v4);
  if ( ((*((_QWORD *)this + 3) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v5 = GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"DumpWriter::Init: failed to ReOpenFile the dump file. GetLastError() returned:%u.\n",
      (const char *)v5);
    std::exception::exception((std::exception *)pExceptionObject, "DumpWriter init-ReOpenFile failure!");
    throw (std::exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180410ff4  mov     [rsp+arg_0], rbx
0x180410ff9  push    rdi
0x180410ffa  sub     rsp, 40h
0x180410ffe  mov     rax, [rcx]
0x180411001  mov     rdi, rcx
0x180411004  xor     ecx, ecx; lpAddress
0x180411006  mov     r8d, 3000h; flAllocationType
0x18041100c  mov     edx, [rax+10h]; dwSize
0x18041100f  lea     r9d, [rcx+4]; flProtect
0x180411013  call    cs:__imp_VirtualAlloc
0x18041101a  nop     dword ptr [rax+rax+00h]
0x18041101f  mov     rdx, rax
0x180411022  lea     rcx, [rdi+10h]
0x180411026  call    ?reset@?$unique_ptr@XUvirtualalloc_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::virtualalloc_deleter>::reset(void *)
0x18041102b  cmp     qword ptr [rdi+10h], 0
0x180411030  jz      loc_1804110F3
0x180411036  xor     r9d, r9d; lpName
0x180411039  xor     ecx, ecx; lpEventAttributes
0x18041103b  lea     edx, [r9+1]; bManualReset
0x18041103f  mov     r8d, edx; bInitialState
0x180411042  call    cs:__imp_CreateEventW
0x180411049  nop     dword ptr [rax+rax+00h]
0x18041104e  mov     rdx, rax
0x180411051  lea     rcx, [rdi+20h]
0x180411055  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18041105a  cmp     qword ptr [rdi+20h], 0
0x18041105f  jz      loc_180411136
0x180411065  mov     rcx, [rdi]
0x180411068  mov     edx, 0C0000000h; dwDesiredAccess
0x18041106d  mov     r9d, 60000000h; dwFlagsAndAttributes
0x180411073  mov     r8d, 3; dwShareMode
0x180411079  mov     rcx, [rcx+18h]; hOriginalFile
0x18041107d  call    cs:__imp_ReOpenFile
0x180411084  nop     dword ptr [rax+rax+00h]
0x180411089  mov     rdx, rax
0x18041108c  lea     rcx, [rdi+18h]
0x180411090  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180411095  mov     rax, [rdi+18h]
0x180411099  inc     rax
0x18041109c  test    rax, 0FFFFFFFFFFFFFFFEh
0x1804110a2  jz      short loc_1804110B0
0x1804110a4  mov     rbx, [rsp+48h+arg_0]
0x1804110a9  add     rsp, 40h
0x1804110ad  pop     rdi
0x1804110ae  retn
0x1804110b0  call    cs:__imp_GetLastError
0x1804110b7  nop     dword ptr [rax+rax+00h]
0x1804110bc  lea     rdx, aDumpwriterInit_1; "DumpWriter::Init: failed to ReOpenFile "...
0x1804110c3  mov     ecx, 4; this
0x1804110c8  mov     r8d, eax; char *
0x1804110cb  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x1804110d0  lea     rdx, aDumpwriterInit_0; "DumpWriter init-ReOpenFile failure!"
0x1804110d7  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1804110dc  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x1804110e1  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x1804110e8  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1804110ed  call    _CxxThrowException
0x1804110f3  call    cs:__imp_GetLastError
0x1804110fa  nop     dword ptr [rax+rax+00h]
0x1804110ff  lea     rdx, aVirtualallocFa_0; "VirtualAlloc failed to allocate memory "...
0x180411106  mov     ecx, 4; this
0x18041110b  mov     r8d, eax; char *
0x18041110e  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180411113  lea     rdx, aVirtualallocFa; "VirtualAlloc failed."
0x18041111a  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18041111f  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180411124  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x18041112b  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180411130  call    _CxxThrowException
0x180411136  call    cs:__imp_GetLastError
0x18041113d  nop     dword ptr [rax+rax+00h]
0x180411142  lea     rdx, aDumpwriterInit; "DumpWriter::Init: failed to create IO e"...
0x180411149  mov     ecx, 4; this
0x18041114e  mov     r8d, eax; char *
0x180411151  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180411156  lea     rdx, aDumpwriterInit_2; "DumpWriter initialize failure!"
0x18041115d  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180411162  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180411167  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x18041116e  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180411173  call    _CxxThrowException
```
