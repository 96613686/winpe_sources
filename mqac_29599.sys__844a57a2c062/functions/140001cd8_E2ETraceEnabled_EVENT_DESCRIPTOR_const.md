# E2ETraceEnabled(_EVENT_DESCRIPTOR const *)

- ea: `0x140001cd8`
- end: `0x140001d04`
- name: `?E2ETraceEnabled@@YAHPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `44`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140001d0c`
- `0x140001df4`
- `0x140001f7c`
- `0x140002094`

## callees

- `0x140001cd8`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140001ceb`
- `ntoskrnl!EtwEventEnabled` at `0x140001ceb`

## pseudocode

```c
__int64 __fastcall E2ETraceEnabled(PCEVENT_DESCRIPTOR EventDescriptor)
{
  if ( g_e2eTraceHandle )
    return EtwEventEnabled(g_e2eTraceHandle, EventDescriptor);
  else
    return 0;
}

```

## disassembly

```asm
0x140001cd8  sub     rsp, 28h
0x140001cdc  mov     rdx, rcx; EventDescriptor
0x140001cdf  mov     rcx, cs:?g_e2eTraceHandle@@3_KA; RegHandle
0x140001ce6  test    rcx, rcx
0x140001ce9  jz      short loc_140001CFC
0x140001ceb  call    cs:__imp_EtwEventEnabled
0x140001cf2  nop     dword ptr [rax+rax+00h]
0x140001cf7  movzx   eax, al
0x140001cfa  jmp     short loc_140001CFE
0x140001cfc  xor     eax, eax
0x140001cfe  add     rsp, 28h
0x140001d02  retn
```
