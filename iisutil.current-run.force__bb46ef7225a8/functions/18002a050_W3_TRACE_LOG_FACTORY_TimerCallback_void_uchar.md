# W3_TRACE_LOG_FACTORY::TimerCallback(void *,uchar)

- ea: `0x18002a050`
- end: `0x18002a0aa`
- name: `?TimerCallback@W3_TRACE_LOG_FACTORY@@CAXPEAXE@Z`
- size: `90`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180016590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a099`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a099`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a069`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a069`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002a088`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002a088`

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
0x18002a050  mov     [rsp+arg_8], rbx
0x18002a055  push    rdi
0x18002a056  sub     rsp, 30h
0x18002a05a  mov     rdi, rcx
0x18002a05d  mov     [rsp+38h+NumberOfBytesWritten], 0
0x18002a065  add     rcx, 48h ; 'H'; lpCriticalSection
0x18002a069  call    cs:__imp_EnterCriticalSection
0x18002a06f  mov     r8d, [rdi+10h]; nNumberOfBytesToWrite
0x18002a073  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002a078  mov     rdx, [rdi+38h]; lpBuffer
0x18002a07c  mov     rcx, [rdi]; hFile
0x18002a07f  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18002a088  call    cs:__imp_WriteFile
0x18002a08e  lea     rcx, [rdi+48h]; lpCriticalSection
0x18002a092  mov     dword ptr [rdi+10h], 0
0x18002a099  call    cs:__imp_LeaveCriticalSection
0x18002a09f  mov     rbx, [rsp+38h+arg_8]
0x18002a0a4  add     rsp, 30h
0x18002a0a8  pop     rdi
0x18002a0a9  retn
```
