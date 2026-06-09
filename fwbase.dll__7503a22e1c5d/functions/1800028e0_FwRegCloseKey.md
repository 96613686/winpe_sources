# FwRegCloseKey

- ea: `0x1800028e0`
- end: `0x180002901`
- name: `FwRegCloseKey`
- size: `33`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001270`
- `0x180001400`
- `0x1800014d0`
- `0x180001650`
- `0x180001a58`
- `0x180001b80`
- `0x180002160`
- `0x180002280`
- `0x180002440`
- `0x180002610`
- `0x1800027a0`
- `0x180002910`
- `0x180006030`
- `0x180013140`
- `0x180029d10`
- `0x18002b2a0`

## callees

- `0x1800028e0`
- `0x18002f43c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800028ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800028ee`

## pseudocode

```c
void __fastcall FwRegCloseKey(HKEY a1)
{
  if ( a1 )
  {
    if ( RegCloseKey(a1) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
}

```

## disassembly

```asm
0x1800028e0  sub     rsp, 28h
0x1800028e4  test    rcx, rcx
0x1800028e7  jnz     short loc_1800028EE
0x1800028e9  add     rsp, 28h
0x1800028ed  retn
0x1800028ee  call    cs:__imp_RegCloseKey
0x1800028f4  test    eax, eax
0x1800028f6  jz      short loc_1800028E9
0x1800028f8  add     rsp, 28h; __annotation("Debug", "TelemetryAssert", "regError == ERROR_SUCCESS")
0x1800028fc  jmp     MicrosoftTelemetryAssertTriggeredNoArgs
```
