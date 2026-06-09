# _dynamic_initializer_for__g_turnonTaskManager__

- ea: `0x180004400`
- end: `0x18000442d`
- name: `_dynamic_initializer_for__g_turnonTaskManager__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000440b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000440b`

## pseudocode

```c
PVOID dynamic_initializer_for__g_turnonTaskManager__()
{
  PVOID result; // rax

  result = EncodePointer(OpenTaskManagerUI);
  qword_1800102A0 = (__int64)result;
  LOWORD(qword_1800102A8) = 1;
  return result;
}

```

## disassembly

```asm
0x180004400  sub     rsp, 28h
0x180004404  lea     rcx, ?OpenTaskManagerUI@@YAJPEAUIUnknown@@PEAUHWND__@@@Z; Ptr
0x18000440b  call    cs:__imp_EncodePointer
0x180004412  nop     dword ptr [rax+rax+00h]
0x180004417  mov     cs:qword_1800102A0, rax
0x18000441e  mov     word ptr cs:qword_1800102A8, 1
0x180004427  add     rsp, 28h
0x18000442b  retn
```
