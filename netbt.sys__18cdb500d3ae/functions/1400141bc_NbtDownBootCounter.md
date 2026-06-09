# NbtDownBootCounter

- ea: `0x1400141bc`
- end: `0x140014210`
- name: `NbtDownBootCounter`
- size: `84`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140012694`
- `0x140014100`
- `0x140014220`
- `0x1400471c0`

## callees

- `0x1400141bc`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400141eb`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400141eb`
- `TDI!TdiProviderReady` at `0x140014202`
- `TDI!TdiProviderReady` at `0x140014202`

## pseudocode

```c
void NbtDownBootCounter()
{
  if ( JustBooted
    && _InterlockedExchangeAdd(&BootTimeCounter, 0xFFFFFFFF) == 1
    && _InterlockedExchange(&JustBooted, 0)
    && !KeGetCurrentIrql() )
  {
    TdiProviderReady(TdiProviderHandle);
  }
}

```

## disassembly

```asm
0x1400141bc  sub     rsp, 28h
0x1400141c0  cmp     cs:JustBooted, 0
0x1400141c7  jnz     short loc_1400141CF
0x1400141c9  add     rsp, 28h
0x1400141cd  retn
0x1400141cf  or      eax, 0FFFFFFFFh
0x1400141d2  lock xadd cs:BootTimeCounter, eax
0x1400141da  cmp     eax, 1
0x1400141dd  jnz     short loc_1400141C9
0x1400141df  xor     eax, eax
0x1400141e1  xchg    eax, cs:JustBooted
0x1400141e7  test    eax, eax
0x1400141e9  jz      short loc_1400141C9
0x1400141eb  call    cs:__imp_KeGetCurrentIrql
0x1400141f2  nop     dword ptr [rax+rax+00h]
0x1400141f7  test    al, al
0x1400141f9  jnz     short loc_1400141C9
0x1400141fb  mov     rcx, cs:TdiProviderHandle; ProviderHandle
0x140014202  call    cs:__imp_TdiProviderReady
0x140014209  nop     dword ptr [rax+rax+00h]
0x14001420e  jmp     short loc_1400141C9
```
