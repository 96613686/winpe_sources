# CWorkerThreadState::WaitForThread(void)

- ea: `0x18000e020`
- end: `0x18000e085`
- name: `?WaitForThread@CWorkerThreadState@@QEAAKXZ`
- size: `101`
- prototype: `unsigned int __fastcall(CWorkerThreadState *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800125a4`
- `0x1800233e8`

## callees

- `0x18000e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e050`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e05f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e05f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e077`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e02f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e02f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e046`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e046`

## pseudocode

```c
__int64 __fastcall CWorkerThreadState::WaitForThread(CWorkerThreadState *this)
{
  DWORD LastError; // ebx

  LastError = 0;
  EnterCriticalSection(&g_EapCredThreadState);
  if ( hObject )
  {
    if ( WaitForSingleObject(hObject, 0xFFFFFFFF) )
      LastError = GetLastError();
    CloseHandle(hObject);
    hObject = 0;
  }
  LeaveCriticalSection(&g_EapCredThreadState);
  return LastError;
}

```

## disassembly

```asm
0x18000e020  push    rbx
0x18000e022  sub     rsp, 20h
0x18000e026  lea     rcx, ?g_EapCredThreadState@@3VCWorkerThreadState@@A; lpCriticalSection
0x18000e02d  xor     ebx, ebx
0x18000e02f  call    cs:__imp_EnterCriticalSection
0x18000e035  mov     rcx, cs:hObject; hHandle
0x18000e03c  test    rcx, rcx
0x18000e03f  jz      short loc_18000E070
0x18000e041  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000e046  call    cs:__imp_WaitForSingleObject
0x18000e04c  test    eax, eax
0x18000e04e  jz      short loc_18000E058
0x18000e050  call    cs:__imp_GetLastError
0x18000e056  mov     ebx, eax
0x18000e058  mov     rcx, cs:hObject; hObject
0x18000e05f  call    cs:__imp_CloseHandle
0x18000e065  mov     cs:hObject, 0
0x18000e070  lea     rcx, ?g_EapCredThreadState@@3VCWorkerThreadState@@A; lpCriticalSection
0x18000e077  call    cs:__imp_LeaveCriticalSection
0x18000e07d  mov     eax, ebx
0x18000e07f  add     rsp, 20h
0x18000e083  pop     rbx
0x18000e084  retn
```
