# _dynamic_initializer_for__g_settingTask__

- ea: `0x180004740`
- end: `0x18000476d`
- name: `_dynamic_initializer_for__g_settingTask__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000474b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000474b`

## pseudocode

```c
PVOID dynamic_initializer_for__g_settingTask__()
{
  PVOID result; // rax

  result = EncodePointer(OpenUACControlPanel);
  qword_180010368 = (__int64)result;
  word_180010370 = 257;
  return result;
}

```

## disassembly

```asm
0x180004740  sub     rsp, 28h
0x180004744  lea     rcx, ?OpenUACControlPanel@@YAJPEAUIUnknown@@PEAUHWND__@@@Z; Ptr
0x18000474b  call    cs:__imp_EncodePointer
0x180004752  nop     dword ptr [rax+rax+00h]
0x180004757  mov     cs:qword_180010368, rax
0x18000475e  mov     cs:word_180010370, 101h
0x180004767  add     rsp, 28h
0x18000476b  retn
```
