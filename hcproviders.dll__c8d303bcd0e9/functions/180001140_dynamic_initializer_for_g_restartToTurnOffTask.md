# _dynamic_initializer_for__g_restartToTurnOffTask__

- ea: `0x180001140`
- end: `0x18000116d`
- name: `_dynamic_initializer_for__g_restartToTurnOffTask__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000114b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000114b`

## pseudocode

```c
PVOID dynamic_initializer_for__g_restartToTurnOffTask__()
{
  PVOID result; // rax

  result = EncodePointer(PromptForRestartToTurnOff);
  qword_180010398 = (__int64)result;
  word_1800103A0 = 1;
  return result;
}

```

## disassembly

```asm
0x180001140  sub     rsp, 28h
0x180001144  lea     rcx, ?PromptForRestartToTurnOff@@YAJPEAUIUnknown@@PEAUHWND__@@@Z; Ptr
0x18000114b  call    cs:__imp_EncodePointer
0x180001152  nop     dword ptr [rax+rax+00h]
0x180001157  mov     cs:qword_180010398, rax
0x18000115e  mov     cs:word_1800103A0, 1
0x180001167  add     rsp, 28h
0x18000116b  retn
```
