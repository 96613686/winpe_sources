# NcaReleaseCancelableLock(_tag_NCA_CANCELABLE_LOCK *)

- ea: `0x1800043bc`
- end: `0x1800043fa`
- name: `?NcaReleaseCancelableLock@@YAXPEAU_tag_NCA_CANCELABLE_LOCK@@@Z`
- size: `62`
- prototype: `void __fastcall(struct _tag_NCA_CANCELABLE_LOCK *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180007954`
- `0x180007b58`
- `0x180007f10`
- `0x180008774`
- `0x180008be4`
- `0x18000be20`
- `0x180018354`

## callees

- `0x1800043bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800043d7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800043d7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800043ee`

## pseudocode

```c
void __fastcall NcaReleaseCancelableLock(struct _tag_NCA_CANCELABLE_LOCK *a1)
{
  if ( _InterlockedExchangeAdd(&dword_180028AE8, 0xFFFFFFFF) == 1 )
    SetEvent(hHandle);
  SetEvent(qword_180028AD8);
}

```

## disassembly

```asm
0x1800043bc  sub     rsp, 28h
0x1800043c0  or      eax, 0FFFFFFFFh
0x1800043c3  lock xadd cs:dword_180028AE8, eax
0x1800043cb  cmp     eax, 1
0x1800043ce  jnz     short loc_1800043E3
0x1800043d0  mov     rcx, cs:hHandle; hEvent
0x1800043d7  call    cs:__imp_SetEvent
0x1800043de  nop     dword ptr [rax+rax+00h]
0x1800043e3  mov     rcx, cs:qword_180028AD8
0x1800043ea  add     rsp, 28h
0x1800043ee  jmp     cs:__imp_SetEvent
```
