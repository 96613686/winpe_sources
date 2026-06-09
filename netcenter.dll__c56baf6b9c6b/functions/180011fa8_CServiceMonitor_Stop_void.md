# CServiceMonitor::Stop(void)

- ea: `0x180011fa8`
- end: `0x180012014`
- name: `?Stop@CServiceMonitor@@QEAAJXZ`
- size: `108`
- prototype: `__int64 __fastcall(CServiceMonitor *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180008248`
- `0x180008780`
- `0x18000df98`

## callees

- `0x180011fa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ff2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180011fe1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180011fe1`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180011fd4`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180011fd4`

## pseudocode

```c
__int64 __fastcall CServiceMonitor::Stop(CServiceMonitor *this)
{
  unsigned int v3; // ebx
  BOOL v4; // eax
  signed int LastError; // eax

  if ( !*((_QWORD *)this + 67) )
    return 2147500037LL;
  v3 = 0;
  if ( *((_QWORD *)this + 69) )
    UnsubscribeServiceChangeNotifications();
  v4 = CloseServiceHandle(*((SC_HANDLE *)this + 67));
  *((_QWORD *)this + 67) = 0;
  if ( !v4 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x180011fa8  mov     [rsp+arg_0], rbx
0x180011fad  push    rdi
0x180011fae  sub     rsp, 20h
0x180011fb2  cmp     qword ptr [rcx+218h], 0
0x180011fba  mov     rdi, rcx
0x180011fbd  jnz     short loc_180011FC6
0x180011fbf  mov     eax, 80004005h
0x180011fc4  jmp     short loc_180012009
0x180011fc6  mov     rcx, [rcx+228h]
0x180011fcd  xor     ebx, ebx
0x180011fcf  test    rcx, rcx
0x180011fd2  jz      short loc_180011FDA
0x180011fd4  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x180011fda  mov     rcx, [rdi+218h]; hSCObject
0x180011fe1  call    cs:__imp_CloseServiceHandle
0x180011fe7  mov     [rdi+218h], rbx
0x180011fee  test    eax, eax
0x180011ff0  jnz     short loc_180012007
0x180011ff2  call    cs:__imp_GetLastError
0x180011ff8  mov     ebx, eax
0x180011ffa  test    eax, eax
0x180011ffc  jle     short loc_180012007
0x180011ffe  movzx   ebx, ax
0x180012001  or      ebx, 80070000h
0x180012007  mov     eax, ebx
0x180012009  mov     rbx, [rsp+28h+arg_0]
0x18001200e  add     rsp, 20h
0x180012012  pop     rdi
0x180012013  retn
```
