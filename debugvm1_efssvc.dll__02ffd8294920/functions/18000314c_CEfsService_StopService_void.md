# CEfsService::StopService(void)

- ea: `0x18000314c`
- end: `0x18000319a`
- name: `?StopService@CEfsService@@QEAAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(CEfsService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x1800031a0`

## callees

- `0x18000314c`
- `0x1800031f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003178`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000316e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000316e`

## pseudocode

```c
__int64 __fastcall CEfsService::StopService(CEfsService *this)
{
  signed int updated; // ebx
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
0x18000314c  mov     [rsp+arg_0], rbx
0x180003151  push    rdi
0x180003152  sub     rsp, 20h
0x180003156  xor     edx, edx; unsigned int
0x180003158  mov     rdi, rcx
0x18000315b  lea     r8d, [rdx+3]; unsigned int
0x18000315f  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x180003164  mov     ebx, eax
0x180003166  test    eax, eax
0x180003168  js      short loc_18000318D
0x18000316a  mov     rcx, [rdi+28h]; hEvent
0x18000316e  call    cs:__imp_SetEvent
0x180003174  test    eax, eax
0x180003176  jnz     short loc_18000318D
0x180003178  call    cs:__imp_GetLastError
0x18000317e  mov     ebx, eax
0x180003180  test    eax, eax
0x180003182  jle     short loc_18000318D
0x180003184  movzx   ebx, ax
0x180003187  or      ebx, 80070000h
0x18000318d  mov     eax, ebx
0x18000318f  mov     rbx, [rsp+28h+arg_0]
0x180003194  add     rsp, 20h
0x180003198  pop     rdi
0x180003199  retn
```
