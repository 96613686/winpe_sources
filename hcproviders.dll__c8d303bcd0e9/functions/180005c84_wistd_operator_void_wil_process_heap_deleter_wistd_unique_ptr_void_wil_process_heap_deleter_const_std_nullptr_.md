# wistd::operator==<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> const &,std::nullptr_t)

- ea: `0x180005c84`
- end: `0x180005c8c`
- name: `??$?8XUprocess_heap_deleter@wil@@@wistd@@YA_NAEBV?$unique_ptr@XUprocess_heap_deleter@wil@@@0@$$T@Z`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800077f0`

## pseudocode

```c
bool __fastcall wistd::operator==<void,wil::process_heap_deleter>(_QWORD *a1)
{
  return *a1 == 0;
}

```

## disassembly

```asm
0x180005c84  cmp     qword ptr [rcx], 0
0x180005c88  setz    al
0x180005c8b  retn
```
