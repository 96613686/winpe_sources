# ServiceCallbackOnStopping

- ea: `0x180008c20`
- end: `0x180008c97`
- name: `ServiceCallbackOnStopping`
- size: `119`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800023d0`
- `0x180008c20`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c44`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180008c63`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180008c63`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180008c32`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180008c32`
- `LocationFramework!UnregisterLocationCOMServer` at `0x180008c26`
- `LocationFramework!UnregisterLocationCOMServer` at `0x180008c26`

## pseudocode

```c
__int64 ServiceCallbackOnStopping()
{
  unsigned int v0; // ebx
  __int64 result; // rax

  v0 = UnregisterLocationCOMServer();
  CoRegisterServerShutdownDelay(0, 0);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( WaitHandle && UnregisterWaitEx(WaitHandle, 0) )
    WaitHandle = 0;
  result = SvcEngUpdateServiceStatus(1u, v0, 0);
  qword_180012450 = 0;
  return result;
}

```

## disassembly

```asm
0x180008c20  push    rbx
0x180008c22  sub     rsp, 20h
0x180008c26  call    cs:__imp_?UnregisterLocationCOMServer@@YAJXZ; UnregisterLocationCOMServer(void)
0x180008c2c  xor     edx, edx
0x180008c2e  xor     ecx, ecx
0x180008c30  mov     ebx, eax
0x180008c32  call    cs:__imp_CoRegisterServerShutdownDelay
0x180008c38  mov     rcx, cs:hObject; hObject
0x180008c3f  test    rcx, rcx
0x180008c42  jz      short loc_180008C55
0x180008c44  call    cs:__imp_CloseHandle
0x180008c4a  mov     cs:hObject, 0
0x180008c55  mov     rcx, cs:WaitHandle; WaitHandle
0x180008c5c  test    rcx, rcx
0x180008c5f  jz      short loc_180008C78
0x180008c61  xor     edx, edx; CompletionEvent
0x180008c63  call    cs:__imp_UnregisterWaitEx
0x180008c69  test    eax, eax
0x180008c6b  jz      short loc_180008C78
0x180008c6d  mov     cs:WaitHandle, 0
0x180008c78  xor     r8d, r8d; unsigned int
0x180008c7b  mov     edx, ebx; unsigned int
0x180008c7d  lea     ecx, [r8+1]; unsigned int
0x180008c81  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x180008c86  mov     cs:qword_180012450, 0
0x180008c91  add     rsp, 20h
0x180008c95  pop     rbx
0x180008c96  retn
```
