# ServiceHandler

- ea: `0x180008830`
- end: `0x180008867`
- name: `ServiceHandler`
- size: `55`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180008830`
- `0x180008af0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000885a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000885a`

## pseudocode

```c
__int64 __fastcall ServiceHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  if ( dwControl == 1 )
  {
    UpdateServiceStatus(3, 1066, 3000);
    if ( g_hEventTerminated )
      SetEvent(g_hEventTerminated);
  }
  return 0;
}

```

## disassembly

```asm
0x180008830  sub     rsp, 28h
0x180008834  cmp     ecx, 1
0x180008837  jnz     short loc_180008860
0x180008839  mov     edx, 42Ah
0x18000883e  mov     ecx, 3
0x180008843  mov     r8d, 0BB8h
0x180008849  call    UpdateServiceStatus
0x18000884e  mov     rcx, cs:g_hEventTerminated; hEvent
0x180008855  test    rcx, rcx
0x180008858  jz      short loc_180008860
0x18000885a  call    cs:__imp_SetEvent
0x180008860  xor     eax, eax
0x180008862  add     rsp, 28h
0x180008866  retn
```
