# DeleteLogFile

- ea: `0x18000a9c0`
- end: `0x18000aa90`
- name: `DeleteLogFile`
- size: `208`
- prototype: `BOOL __stdcall(LPCWSTR pszLogFileName, PVOID pvReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180009fe0`
- `0x18000a9c0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000aa50`
- `ntdll!RtlNtStatusToDosError` at `0x18000aa50`
- `ntdll!NtSetInformationFile` at `0x18000aa42`
- `ntdll!NtSetInformationFile` at `0x18000aa42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aa76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aa76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa61`

## pseudocode

```c
BOOL __stdcall DeleteLogFile(LPCWSTR pszLogFileName, PVOID pvReserved)
{
  HANDLE LogFile; // rax
  void *v4; // rbx
  NTSTATUS v5; // eax
  DWORD v6; // edi
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-18h] BYREF
  char FileInformation; // [rsp+50h] [rbp+8h] BYREF

  IoStatusBlock.Pointer = 0;
  IoStatusBlock.Information = 0;
  FileInformation = 1;
  if ( !pszLogFileName )
  {
    SetLastError(0x57u);
    return 0;
  }
  LogFile = CreateLogFile(pszLogFileName, 0x10000u, 7u, 0, 3u, 0x80u);
  v4 = LogFile;
  if ( LogFile == (HANDLE)-1LL )
    return 0;
  v5 = NtSetInformationFile(LogFile, &IoStatusBlock, &FileInformation, 1u, FileDispositionInformation);
  v6 = RtlNtStatusToDosError(v5);
  CloseHandle(v4);
  SetLastError(v6);
  return v6 == 0;
}

```

## disassembly

```asm
0x18000a9c0  mov     rax, rsp
0x18000a9c3  mov     [rax+10h], rbx
0x18000a9c7  push    rdi
0x18000a9c8  sub     rsp, 40h
0x18000a9cc  mov     qword ptr [rax-18h], 0
0x18000a9d4  mov     qword ptr [rax-10h], 0
0x18000a9dc  mov     byte ptr [rax+8], 1
0x18000a9e0  test    rcx, rcx
0x18000a9e3  jnz     short loc_18000A9FD
0x18000a9e5  mov     ecx, 57h ; 'W'; dwErrCode
0x18000a9ea  call    cs:__imp_SetLastError
0x18000a9f1  nop     dword ptr [rax+rax+00h]
0x18000a9f6  xor     eax, eax
0x18000a9f8  jmp     loc_18000AA84
0x18000a9fd  xor     r9d, r9d; psaLogFile
0x18000aa00  mov     [rsp+48h+fFlagsAndAttributes], 80h; fFlagsAndAttributes
0x18000aa08  mov     edx, 10000h; fDesiredAccess
0x18000aa0d  mov     [rsp+48h+fCreateDisposition], 3; fCreateDisposition
0x18000aa15  lea     r8d, [r9+7]; dwShareMode
0x18000aa19  call    CreateLogFile
0x18000aa1e  mov     rbx, rax
0x18000aa21  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000aa25  jz      short loc_18000A9F6
0x18000aa27  mov     r9d, 1; Length
0x18000aa2d  mov     [rsp+48h+fCreateDisposition], 0Dh; FileInformationClass
0x18000aa35  lea     r8, [rsp+48h+FileInformation]; FileInformation
0x18000aa3a  mov     rcx, rax; FileHandle
0x18000aa3d  lea     rdx, [rsp+48h+IoStatusBlock]; IoStatusBlock
0x18000aa42  call    cs:__imp_NtSetInformationFile
0x18000aa49  nop     dword ptr [rax+rax+00h]
0x18000aa4e  mov     ecx, eax; Status
0x18000aa50  call    cs:__imp_RtlNtStatusToDosError
0x18000aa57  nop     dword ptr [rax+rax+00h]
0x18000aa5c  mov     rcx, rbx; hObject
0x18000aa5f  mov     edi, eax
0x18000aa61  call    cs:__imp_CloseHandle
0x18000aa68  nop     dword ptr [rax+rax+00h]
0x18000aa6d  xor     ebx, ebx
0x18000aa6f  mov     ecx, edi; dwErrCode
0x18000aa71  test    edi, edi
0x18000aa73  setz    bl
0x18000aa76  call    cs:__imp_SetLastError
0x18000aa7d  nop     dword ptr [rax+rax+00h]
0x18000aa82  mov     eax, ebx
0x18000aa84  mov     rbx, [rsp+48h+arg_8]
0x18000aa89  add     rsp, 40h
0x18000aa8d  pop     rdi
0x18000aa8e  retn
```
