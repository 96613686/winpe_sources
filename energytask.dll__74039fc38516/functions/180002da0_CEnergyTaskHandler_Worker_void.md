# CEnergyTaskHandler::Worker(void)

- ea: `0x180002da0`
- end: `0x180002dd0`
- name: `?Worker@CEnergyTaskHandler@@EEAAJXZ`
- size: `48`
- prototype: `__int64 __fastcall(CEnergyTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180002728`
- `0x1800029bc`
- `0x180002da0`

## import_xrefs

- `KERNELBASE!WTSIsServerContainer` at `0x180002da9`
- `KERNELBASE!WTSIsServerContainer` at `0x180002da9`

## pseudocode

```c
__int64 __fastcall CEnergyTaskHandler::Worker(CEnergyTaskHandler *this)
{
  CEnergyTaskHandler *v2; // rcx

  if ( (unsigned __int8)WTSIsServerContainer() )
    return 2147500036LL;
  CEnergyTaskHandler::RunSleepStudyReport(v2);
  return CEnergyTaskHandler::RunEnergyReport(this);
}

```

## disassembly

```asm
0x180002da0  push    rbx
0x180002da2  sub     rsp, 20h
0x180002da6  mov     rbx, rcx
0x180002da9  call    cs:__imp_WTSIsServerContainer
0x180002daf  test    al, al
0x180002db1  jz      short loc_180002DBE
0x180002db3  mov     eax, 80004004h
0x180002db8  add     rsp, 20h
0x180002dbc  pop     rbx
0x180002dbd  retn
0x180002dbe  call    ?RunSleepStudyReport@CEnergyTaskHandler@@AEAAJXZ; CEnergyTaskHandler::RunSleepStudyReport(void)
0x180002dc3  mov     rcx, rbx; this
0x180002dc6  add     rsp, 20h
0x180002dca  pop     rbx
0x180002dcb  jmp     ?RunEnergyReport@CEnergyTaskHandler@@AEAAJXZ; CEnergyTaskHandler::RunEnergyReport(void)
```
