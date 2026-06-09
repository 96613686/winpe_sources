# ProcessStopPPP

- ea: `0x180018160`
- end: `0x18001819b`
- name: `ProcessStopPPP`
- size: `59`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003170`
- `0x180005054`
- `0x180018160`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18001818e`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18001818e`

## pseudocode

```c
void __noreturn ProcessStopPPP()
{
  if ( (byte_18004DF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasPppTraceInfo,
      L"All clients disconnected PPP-Stopped");
  PPPCleanUp();
  ExitThread(0);
}

```

## disassembly

```asm
0x180018160  sub     rsp, 28h
0x180018164  test    cs:byte_18004DF34, 1
0x18001816b  jz      short loc_180018187
0x18001816d  lea     r8, aAllClientsDisc; "All clients disconnected PPP-Stopped"
0x180018174  lea     rdx, RasPppTraceInfo
0x18001817b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180018182  call    McTemplateU0z_EventWriteTransfer
0x180018187  call    PPPCleanUp
0x18001818c  xor     ecx, ecx; dwExitCode
0x18001818e  call    cs:__imp_ExitThread
```
