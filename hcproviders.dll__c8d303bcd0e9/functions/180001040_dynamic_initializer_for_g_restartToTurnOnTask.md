# _dynamic_initializer_for__g_restartToTurnOnTask__

- ea: `0x180001040`
- end: `0x18000106d`
- name: `_dynamic_initializer_for__g_restartToTurnOnTask__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000104b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000104b`

## pseudocode

```c
PVOID dynamic_initializer_for__g_restartToTurnOnTask__()
{
  PVOID result; // rax

  result = EncodePointer(PromptForRestartToTurnOn);
  qword_180010320 = (__int64)result;
  word_180010328 = 1;
  return result;
}

```

## disassembly

```asm
0x180001040  sub     rsp, 28h
0x180001044  lea     rcx, ?PromptForRestartToTurnOn@@YAJPEAUIUnknown@@PEAUHWND__@@@Z; Ptr
0x18000104b  call    cs:__imp_EncodePointer
0x180001052  nop     dword ptr [rax+rax+00h]
0x180001057  mov     cs:qword_180010320, rax
0x18000105e  mov     cs:word_180010328, 1
0x180001067  add     rsp, 28h
0x18000106b  retn
```
