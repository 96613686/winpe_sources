# W3_TRACE_LOG_FACTORY::TimerCallback(void *,uchar)

- ea: `0x18002bed0`
- end: `0x18002bf3d`
- name: `?TimerCallback@W3_TRACE_LOG_FACTORY@@CAXPEAXE@Z`
- size: `109`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800171b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bf25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bf25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bee9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bee9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002bf0e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002bf0e`

## pseudocode

```c
void __fastcall W3_TRACE_LOG_FACTORY::TimerCallback(char *a1)
{
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
  WriteFile(*(HANDLE *)a1, *((LPCVOID *)a1 + 7), *((_DWORD *)a1 + 4), &NumberOfBytesWritten, 0);
  *((_DWORD *)a1 + 4) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
}

```

## disassembly

```asm
0x18002bed0  mov     [rsp+arg_8], rbx
0x18002bed5  push    rdi
0x18002bed6  sub     rsp, 30h
0x18002beda  mov     rdi, rcx
0x18002bedd  mov     [rsp+38h+NumberOfBytesWritten], 0
0x18002bee5  add     rcx, 48h ; 'H'; lpCriticalSection
0x18002bee9  call    cs:__imp_EnterCriticalSection
0x18002bef0  nop     dword ptr [rax+rax+00h]
0x18002bef5  mov     r8d, [rdi+10h]; nNumberOfBytesToWrite
0x18002bef9  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002befe  mov     rdx, [rdi+38h]; lpBuffer
0x18002bf02  mov     rcx, [rdi]; hFile
0x18002bf05  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18002bf0e  call    cs:__imp_WriteFile
0x18002bf15  nop     dword ptr [rax+rax+00h]
0x18002bf1a  lea     rcx, [rdi+48h]; lpCriticalSection
0x18002bf1e  mov     dword ptr [rdi+10h], 0
0x18002bf25  call    cs:__imp_LeaveCriticalSection
0x18002bf2c  nop     dword ptr [rax+rax+00h]
0x18002bf31  mov     rbx, [rsp+38h+arg_8]
0x18002bf36  add     rsp, 30h
0x18002bf3a  pop     rdi
0x18002bf3b  retn
```
