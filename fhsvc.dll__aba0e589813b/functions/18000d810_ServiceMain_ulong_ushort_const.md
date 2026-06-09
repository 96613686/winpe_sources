# ServiceMain(ulong,ushort * * const)

- ea: `0x18000d810`
- end: `0x18000d815`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `5`
- prototype: `void __fastcall(CFhService *, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180001950`

## pseudocode

```c
// attributes: thunk
void __fastcall ServiceMain(CFhService *a1, unsigned __int16 **const a2)
{
  CFhService::StartServiceW(a1);
}

```

## disassembly

```asm
0x18000d810  jmp     ?StartServiceW@CFhService@@QEAAJXZ; CFhService::StartServiceW(void)
```
