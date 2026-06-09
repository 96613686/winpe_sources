# SetLogonTaskAdditionalThread(LogonTaskAdditionalThread,LogonTaskAdditionalThreadFlags)

- ea: `0x140031f18`
- end: `0x140031fa6`
- name: `?SetLogonTaskAdditionalThread@@YAXW4LogonTaskAdditionalThread@@W4LogonTaskAdditionalThreadFlags@@@Z`
- size: `142`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callers

- `0x140031eb0`
- `0x1400a6d70`
- `0x14012a594`

## callees

- `0x140031f18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140031f2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140031f2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140031f27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140031f27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140031f95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140031f95`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140031f86`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140031f86`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140031f68`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140031f68`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140031f44`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140031f44`

## string_xrefs

- `0x140031f37`: `LogonTaskProgressMapping`

## pseudocode

```c
int __fastcall SetLogonTaskAdditionalThread(unsigned int a1, int a2)
{
  __int64 v3; // rsi
  DWORD CurrentThreadId; // ebp
  DWORD CurrentProcessId; // r14d
  HANDLE v6; // rax
  void *v7; // rbx
  __int64 v8; // rdx

  v3 = a1;
  CurrentThreadId = GetCurrentThreadId();
  CurrentProcessId = GetCurrentProcessId();
  v6 = OpenFileMappingW(2u, 0, L"LogonTaskProgressMapping");
  v7 = v6;
  if ( v6 )
  {
    v6 = MapViewOfFile(v6, 2u, 0, 0, 0x3Cu);
    if ( v6 )
    {
      v8 = 3 * v3;
      *((_DWORD *)v6 + v8) = a2;
      *((_DWORD *)v6 + v8 + 1) = CurrentProcessId;
      *((_DWORD *)v6 + v8 + 2) = CurrentThreadId;
      LODWORD(v6) = UnmapViewOfFile(v6);
    }
    if ( v7 != (void *)-1LL )
      LODWORD(v6) = CloseHandle(v7);
  }
  return (int)v6;
}

```

## disassembly

```asm
0x140031f18  push    rbx
0x140031f1a  push    rbp
0x140031f1b  push    rsi
0x140031f1c  push    rdi
0x140031f1d  push    r14
0x140031f1f  sub     rsp, 30h
0x140031f23  mov     edi, edx
0x140031f25  mov     esi, ecx
0x140031f27  call    cs:__imp_GetCurrentThreadId
0x140031f2d  mov     ebp, eax
0x140031f2f  call    cs:__imp_GetCurrentProcessId
0x140031f35  xor     edx, edx; bInheritHandle
0x140031f37  lea     r8, ?AdditionalThreadMappingName@LogonTaskFrameworkInternal@@3QBGB; "LogonTaskProgressMapping"
0x140031f3e  mov     r14d, eax
0x140031f41  lea     ecx, [rdx+2]; dwDesiredAccess
0x140031f44  call    cs:__imp_OpenFileMappingW
0x140031f4a  mov     rbx, rax
0x140031f4d  test    rax, rax
0x140031f50  jz      short loc_140031F9B
0x140031f52  xor     r9d, r9d; dwFileOffsetLow
0x140031f55  mov     [rsp+58h+dwNumberOfBytesToMap], 3Ch ; '<'; dwNumberOfBytesToMap
0x140031f5e  xor     r8d, r8d; dwFileOffsetHigh
0x140031f61  mov     rcx, rax; hFileMappingObject
0x140031f64  lea     edx, [r9+2]; dwDesiredAccess
0x140031f68  call    cs:__imp_MapViewOfFile
0x140031f6e  test    rax, rax
0x140031f71  jz      short loc_140031F8C
0x140031f73  lea     rdx, [rsi+rsi*2]
0x140031f77  mov     rcx, rax; lpBaseAddress
0x140031f7a  mov     [rax+rdx*4], edi
0x140031f7d  mov     [rax+rdx*4+4], r14d
0x140031f82  mov     [rax+rdx*4+8], ebp
0x140031f86  call    cs:__imp_UnmapViewOfFile
0x140031f8c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140031f90  jz      short loc_140031F9B
0x140031f92  mov     rcx, rbx; hObject
0x140031f95  call    cs:__imp_CloseHandle
0x140031f9b  add     rsp, 30h
0x140031f9f  pop     r14
0x140031fa1  pop     rdi
0x140031fa2  pop     rsi
0x140031fa3  pop     rbp
0x140031fa4  pop     rbx
0x140031fa5  retn
```
