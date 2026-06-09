# CEfsService::StopService(void)

- ea: `0x180003250`
- end: `0x1800032ab`
- name: `?StopService@CEfsService@@QEAAJXZ`
- size: `91`
- prototype: `__int64 __fastcall(CEfsService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x1800032c0`

## callees

- `0x180003250`
- `0x180003320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003282`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003272`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003272`

## pseudocode

```c
__int64 __fastcall CEfsService::StopService(CEfsService *this)
{
  int updated; // ebx
  signed int LastError; // eax

  updated = CEfsService::UpdateServiceStatus((LPSERVICE_STATUS)this, 0, 3u);
  if ( updated >= 0 && !SetEvent(*((HANDLE *)this + 5)) )
  {
    LastError = GetLastError();
    updated = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180003250  mov     [rsp+arg_0], rbx
0x180003255  push    rdi
0x180003256  sub     rsp, 20h
0x18000325a  xor     edx, edx; unsigned int
0x18000325c  mov     rdi, rcx
0x18000325f  lea     r8d, [rdx+3]; unsigned int
0x180003263  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x180003268  mov     ebx, eax
0x18000326a  test    eax, eax
0x18000326c  js      short loc_18000329D
0x18000326e  mov     rcx, [rdi+28h]; hEvent
0x180003272  call    cs:__imp_SetEvent
0x180003279  nop     dword ptr [rax+rax+00h]
0x18000327e  test    eax, eax
0x180003280  jnz     short loc_18000329D
0x180003282  call    cs:__imp_GetLastError
0x180003289  nop     dword ptr [rax+rax+00h]
0x18000328e  mov     ebx, eax
0x180003290  test    eax, eax
0x180003292  jle     short loc_18000329D
0x180003294  movzx   ebx, ax
0x180003297  or      ebx, 80070000h
0x18000329d  mov     eax, ebx
0x18000329f  mov     rbx, [rsp+28h+arg_0]
0x1800032a4  add     rsp, 20h
0x1800032a8  pop     rdi
0x1800032a9  retn
```
