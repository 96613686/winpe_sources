# _dynamic_initializer_for__g_turnonTask__

- ea: `0x1800010c0`
- end: `0x1800010ed`
- name: `_dynamic_initializer_for__g_turnonTask__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800010cb`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800010cb`

## pseudocode

```c
PVOID dynamic_initializer_for__g_turnonTask__()
{
  PVOID result; // rax

  result = EncodePointer(OpenUACControlPanel);
  qword_180010338 = (__int64)result;
  word_180010340 = 257;
  return result;
}

```

## disassembly

```asm
0x1800010c0  sub     rsp, 28h
0x1800010c4  lea     rcx, ?OpenUACControlPanel@@YAJPEAUIUnknown@@PEAUHWND__@@@Z; Ptr
0x1800010cb  call    cs:__imp_EncodePointer
0x1800010d2  nop     dword ptr [rax+rax+00h]
0x1800010d7  mov     cs:qword_180010338, rax
0x1800010de  mov     cs:word_180010340, 101h
0x1800010e7  add     rsp, 28h
0x1800010eb  retn
```
