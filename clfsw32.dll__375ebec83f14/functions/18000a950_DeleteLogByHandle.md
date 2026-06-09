# DeleteLogByHandle

- ea: `0x18000a950`
- end: `0x18000a9b9`
- name: `DeleteLogByHandle`
- size: `105`
- prototype: `BOOL __stdcall(HANDLE hLog)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, loader_planting`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000a98f`
- `ntdll!RtlNtStatusToDosError` at `0x18000a98f`
- `ntdll!NtSetInformationFile` at `0x18000a981`
- `ntdll!NtSetInformationFile` at `0x18000a981`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9a4`

## pseudocode

```c
BOOL __stdcall DeleteLogByHandle(HANDLE hLog)
{
  NTSTATUS v1; // eax
  DWORD v2; // eax
  BOOL v3; // ebx
  struct _IO_STATUS_BLOCK v5; // [rsp+30h] [rbp-18h] BYREF
  char v6; // [rsp+58h] [rbp+10h] BYREF

  v5.Pointer = 0;
  v5.Information = 0;
  v6 = 1;
  v1 = NtSetInformationFile(hLog, &v5, &v6, 1u, FileDispositionInformation);
  v2 = RtlNtStatusToDosError(v1);
  v3 = v2 == 0;
  SetLastError(v2);
  return v3;
}

```

## disassembly

```asm
0x18000a950  mov     rax, rsp
0x18000a953  push    rbx
0x18000a954  sub     rsp, 40h
0x18000a958  mov     r9d, 1; Length
0x18000a95e  mov     qword ptr [rax-18h], 0
0x18000a966  lea     r8, [rax+10h]; FileInformation
0x18000a96a  mov     qword ptr [rax-10h], 0
0x18000a972  lea     rdx, [rax-18h]; IoStatusBlock
0x18000a976  mov     byte ptr [rax+10h], 1
0x18000a97a  mov     dword ptr [rax-28h], 0Dh
0x18000a981  call    cs:__imp_NtSetInformationFile
0x18000a988  nop     dword ptr [rax+rax+00h]
0x18000a98d  mov     ecx, eax; Status
0x18000a98f  call    cs:__imp_RtlNtStatusToDosError
0x18000a996  nop     dword ptr [rax+rax+00h]
0x18000a99b  xor     ebx, ebx
0x18000a99d  mov     ecx, eax; dwErrCode
0x18000a99f  test    eax, eax
0x18000a9a1  setz    bl
0x18000a9a4  call    cs:__imp_SetLastError
0x18000a9ab  nop     dword ptr [rax+rax+00h]
0x18000a9b0  mov     eax, ebx
0x18000a9b2  add     rsp, 40h
0x18000a9b6  pop     rbx
0x18000a9b7  retn
```
