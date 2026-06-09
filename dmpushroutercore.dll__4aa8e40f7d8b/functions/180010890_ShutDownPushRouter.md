# ShutDownPushRouter

- ea: `0x180010890`
- end: `0x18001091c`
- name: `ShutDownPushRouter`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180010890`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800108d2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800108d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800108fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800108fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010909`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010909`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800108a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800108a7`

## pseudocode

```c
__int64 ShutDownPushRouter()
{
  unsigned int v0; // ebx
  HANDLE v1; // rdi
  signed int LastError; // eax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  ThreadId = 0;
  EnterCriticalSection(&g_csPushRouter);
  if ( g_pPushRouter )
  {
    v1 = CreateThread(0, 0, AsyncShutDownPushRouterThread, 0, 0, &ThreadId);
    if ( !v1 )
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v1 = 0;
  }
  CloseHandle(v1);
  LeaveCriticalSection(&g_csPushRouter);
  return v0;
}

```

## disassembly

```asm
0x180010890  mov     [rsp+arg_8], rbx
0x180010895  push    rdi
0x180010896  sub     rsp, 30h
0x18001089a  xor     ebx, ebx
0x18001089c  lea     rcx, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800108a3  mov     [rsp+38h+ThreadId], ebx
0x1800108a7  call    cs:__imp_EnterCriticalSection
0x1800108ad  cmp     cs:?g_pPushRouter@@3PEAVPushRouter@@EA, rbx; PushRouter * g_pPushRouter
0x1800108b4  jz      short loc_1800108F7
0x1800108b6  lea     rax, [rsp+38h+ThreadId]
0x1800108bb  xor     r9d, r9d; lpParameter
0x1800108be  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800108c3  lea     r8, ?AsyncShutDownPushRouterThread@@YAKPEAX@Z; lpStartAddress
0x1800108ca  xor     edx, edx; dwStackSize
0x1800108cc  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x1800108d0  xor     ecx, ecx; lpThreadAttributes
0x1800108d2  call    cs:__imp_CreateThread
0x1800108d8  mov     rdi, rax
0x1800108db  test    rax, rax
0x1800108de  jnz     short loc_1800108F9
0x1800108e0  call    cs:__imp_GetLastError
0x1800108e6  mov     ebx, eax
0x1800108e8  test    eax, eax
0x1800108ea  jle     short loc_1800108F9
0x1800108ec  movzx   ebx, ax
0x1800108ef  or      ebx, 80070000h
0x1800108f5  jmp     short loc_1800108F9
0x1800108f7  xor     edi, edi
0x1800108f9  mov     rcx, rdi; hObject
0x1800108fc  call    cs:__imp_CloseHandle
0x180010902  lea     rcx, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180010909  call    cs:__imp_LeaveCriticalSection
0x18001090f  mov     eax, ebx
0x180010911  mov     rbx, [rsp+38h+arg_8]
0x180010916  add     rsp, 30h
0x18001091a  pop     rdi
0x18001091b  retn
```
