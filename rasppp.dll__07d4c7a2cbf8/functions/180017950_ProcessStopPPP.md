# ProcessStopPPP

- ea: `0x180017950`
- end: `0x180017985`
- name: `ProcessStopPPP`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003110`
- `0x180004eac`
- `0x180017950`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18001797e`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18001797e`

## pseudocode

```c
void __noreturn ProcessStopPPP()
{
  if ( (byte_18004CF34 & 1) != 0 )
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
0x180017950  sub     rsp, 28h
0x180017954  test    cs:byte_18004CF34, 1
0x18001795b  jz      short loc_180017977
0x18001795d  lea     r8, aAllClientsDisc; "All clients disconnected PPP-Stopped"
0x180017964  lea     rdx, RasPppTraceInfo
0x18001796b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017972  call    McTemplateU0z_EventWriteTransfer
0x180017977  call    PPPCleanUp
0x18001797c  xor     ecx, ecx; dwExitCode
0x18001797e  call    cs:__imp_ExitThread
```
