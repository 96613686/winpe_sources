# SetLogonTaskAdditionalThread(LogonTaskAdditionalThread,LogonTaskAdditionalThreadFlags)

- ea: `0x140024738`
- end: `0x1400247eb`
- name: `?SetLogonTaskAdditionalThread@@YAXW4LogonTaskAdditionalThread@@W4LogonTaskAdditionalThreadFlags@@@Z`
- size: `179`
- prototype: `int __fastcall(unsigned int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callers

- `0x1400246d0`
- `0x1400acf1c`
- `0x1401361a4`

## callees

- `0x140024738`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140024747`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140024747`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140024755`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140024755`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400247d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400247d3`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140024770`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140024770`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14002479a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14002479a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400247be`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400247be`

## string_xrefs

- `0x140024763`: `LogonTaskProgressMapping`

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
0x140024738  push    rbx
0x14002473a  push    rbp
0x14002473b  push    rsi
0x14002473c  push    rdi
0x14002473d  push    r14
0x14002473f  sub     rsp, 30h
0x140024743  mov     edi, edx
0x140024745  mov     esi, ecx
0x140024747  call    cs:__imp_GetCurrentThreadId
0x14002474e  nop     dword ptr [rax+rax+00h]
0x140024753  mov     ebp, eax
0x140024755  call    cs:__imp_GetCurrentProcessId
0x14002475c  nop     dword ptr [rax+rax+00h]
0x140024761  xor     edx, edx; bInheritHandle
0x140024763  lea     r8, ?AdditionalThreadMappingName@LogonTaskFrameworkInternal@@3QBGB; "LogonTaskProgressMapping"
0x14002476a  mov     r14d, eax
0x14002476d  lea     ecx, [rdx+2]; dwDesiredAccess
0x140024770  call    cs:__imp_OpenFileMappingW
0x140024777  nop     dword ptr [rax+rax+00h]
0x14002477c  mov     rbx, rax
0x14002477f  test    rax, rax
0x140024782  jz      short loc_1400247DF
0x140024784  xor     r9d, r9d; dwFileOffsetLow
0x140024787  mov     [rsp+58h+dwNumberOfBytesToMap], 3Ch ; '<'; dwNumberOfBytesToMap
0x140024790  xor     r8d, r8d; dwFileOffsetHigh
0x140024793  mov     rcx, rax; hFileMappingObject
0x140024796  lea     edx, [r9+2]; dwDesiredAccess
0x14002479a  call    cs:__imp_MapViewOfFile
0x1400247a1  nop     dword ptr [rax+rax+00h]
0x1400247a6  test    rax, rax
0x1400247a9  jz      short loc_1400247CA
0x1400247ab  lea     rdx, [rsi+rsi*2]
0x1400247af  mov     rcx, rax; lpBaseAddress
0x1400247b2  mov     [rax+rdx*4], edi
0x1400247b5  mov     [rax+rdx*4+4], r14d
0x1400247ba  mov     [rax+rdx*4+8], ebp
0x1400247be  call    cs:__imp_UnmapViewOfFile
0x1400247c5  nop     dword ptr [rax+rax+00h]
0x1400247ca  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400247ce  jz      short loc_1400247DF
0x1400247d0  mov     rcx, rbx; hObject
0x1400247d3  call    cs:__imp_CloseHandle
0x1400247da  nop     dword ptr [rax+rax+00h]
0x1400247df  add     rsp, 30h
0x1400247e3  pop     r14
0x1400247e5  pop     rdi
0x1400247e6  pop     rsi
0x1400247e7  pop     rbp
0x1400247e8  pop     rbx
0x1400247e9  retn
```
