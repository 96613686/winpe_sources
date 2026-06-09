# ClRtlInitializeQueue

- ea: `0x18009e238`
- end: `0x18009e2cf`
- name: `ClRtlInitializeQueue`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002e04c`
- `0x18005cbb4`

## callees

- `0x18009e238`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009e258`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009e258`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009e26e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009e293`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009e26e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009e293`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009e2b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009e2b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e27d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e2a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e27d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e2a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e2ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e2ae`

## pseudocode

```c
__int64 __fastcall ClRtlInitializeQueue(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  DWORD LastError; // ebx
  HANDLE EventW; // rax
  HANDLE v5; // rax

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  *(_QWORD *)(a1 + 8) = a1;
  *(_QWORD *)a1 = a1;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  LastError = 0;
  *(_DWORD *)(a1 + 64) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(a1 + 56) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
LABEL_5:
    DeleteCriticalSection(v1);
    return LastError;
  }
  v5 = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(a1 + 72) = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    CloseHandle(*(HANDLE *)(a1 + 56));
    goto LABEL_5;
  }
  return LastError;
}

```

## disassembly

```asm
0x18009e238  mov     [rsp+arg_0], rbx
0x18009e23d  mov     [rsp+arg_8], rsi
0x18009e242  push    rdi
0x18009e243  sub     rsp, 20h
0x18009e247  lea     rsi, [rcx+10h]
0x18009e24b  mov     [rcx+8], rcx
0x18009e24f  mov     rdi, rcx
0x18009e252  mov     [rcx], rcx
0x18009e255  mov     rcx, rsi; lpCriticalSection
0x18009e258  call    cs:__imp_InitializeCriticalSection
0x18009e25e  xor     ebx, ebx
0x18009e260  xor     r9d, r9d; lpName
0x18009e263  xor     r8d, r8d; bInitialState
0x18009e266  mov     [rdi+40h], ebx
0x18009e269  xor     ecx, ecx; lpEventAttributes
0x18009e26b  lea     edx, [rbx+1]; bManualReset
0x18009e26e  call    cs:__imp_CreateEventW
0x18009e274  mov     [rdi+38h], rax
0x18009e278  test    rax, rax
0x18009e27b  jnz     short loc_18009E287
0x18009e27d  call    cs:__imp_GetLastError
0x18009e283  mov     ebx, eax
0x18009e285  jmp     short loc_18009E2B4
0x18009e287  xor     r9d, r9d; lpName
0x18009e28a  xor     r8d, r8d; bInitialState
0x18009e28d  xor     ecx, ecx; lpEventAttributes
0x18009e28f  lea     edx, [r9+1]; bManualReset
0x18009e293  call    cs:__imp_CreateEventW
0x18009e299  mov     [rdi+48h], rax
0x18009e29d  test    rax, rax
0x18009e2a0  jnz     short loc_18009E2BD
0x18009e2a2  call    cs:__imp_GetLastError
0x18009e2a8  mov     rcx, [rdi+38h]; hObject
0x18009e2ac  mov     ebx, eax
0x18009e2ae  call    cs:__imp_CloseHandle
0x18009e2b4  mov     rcx, rsi; lpCriticalSection
0x18009e2b7  call    cs:__imp_DeleteCriticalSection
0x18009e2bd  mov     rsi, [rsp+28h+arg_8]
0x18009e2c2  mov     eax, ebx
0x18009e2c4  mov     rbx, [rsp+28h+arg_0]
0x18009e2c9  add     rsp, 20h
0x18009e2cd  pop     rdi
0x18009e2ce  retn
```
