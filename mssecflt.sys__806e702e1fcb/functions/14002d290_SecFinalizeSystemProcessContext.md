# SecFinalizeSystemProcessContext

- ea: `0x14002d290`
- end: `0x14002d2f1`
- name: `SecFinalizeSystemProcessContext`
- size: `97`
- prototype: `CALLBACK_FUNCTION`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140006754`
- `0x140006b6c`
- `0x14002d290`

## import_xrefs

- `ntoskrnl!PsInitialSystemProcess` at `0x14002d296`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002d2c3`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002d2cd`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002d2cd`

## pseudocode

```c
void __fastcall SecFinalizeSystemProcessContext(PVOID CallbackContext, PVOID Argument1, PVOID Argument2)
{
  int ProcessContextByObject; // eax
  PSLIST_ENTRY v4; // rbx
  PSLIST_ENTRY ListEntry; // [rsp+48h] [rbp+20h] BYREF

  ListEntry = 0;
  ProcessContextByObject = SecGetProcessContextByObject(PsInitialSystemProcess, &ListEntry);
  v4 = ListEntry;
  if ( ProcessContextByObject >= 0 && !*((_QWORD *)&ListEntry[2].Next + 1) )
    *((_QWORD *)&v4[2].Next + 1) = PsGetProcessCreateTimeQuadPart(PsInitialSystemProcess);
  if ( v4 )
    SecReleaseProcessContext(v4);
}

```

## disassembly

```asm
0x14002d290  push    rbx
0x14002d292  sub     rsp, 20h
0x14002d296  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14002d29d  lea     rdx, [rsp+28h+ListEntry]
0x14002d2a2  mov     [rsp+28h+ListEntry], 0
0x14002d2ab  mov     rcx, [rcx]
0x14002d2ae  call    SecGetProcessContextByObject
0x14002d2b3  mov     rbx, [rsp+28h+ListEntry]
0x14002d2b8  test    eax, eax
0x14002d2ba  js      short loc_14002D2DD
0x14002d2bc  cmp     qword ptr [rbx+28h], 0
0x14002d2c1  jnz     short loc_14002D2DD
0x14002d2c3  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14002d2ca  mov     rcx, [rcx]; Process
0x14002d2cd  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14002d2d4  nop     dword ptr [rax+rax+00h]
0x14002d2d9  mov     [rbx+28h], rax
0x14002d2dd  test    rbx, rbx
0x14002d2e0  jz      short loc_14002D2EA
0x14002d2e2  mov     rcx, rbx; ListEntry
0x14002d2e5  call    SecReleaseProcessContext
0x14002d2ea  add     rsp, 20h
0x14002d2ee  pop     rbx
0x14002d2ef  retn
```
