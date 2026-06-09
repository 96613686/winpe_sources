# wistd::operator==<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> const &,std::nullptr_t)

- ea: `0x1400032e0`
- end: `0x1400032e8`
- name: `??$?8XUprocess_heap_deleter@wil@@@wistd@@YA_NAEBV?$unique_ptr@XUprocess_heap_deleter@wil@@@0@$$T@Z`
- size: `8`
- prototype: `bool __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140005280`
- `0x14000f180`

## pseudocode

```c
bool __fastcall wistd::operator==<void,wil::process_heap_deleter>(_QWORD *a1)
{
  return *a1 == 0;
}

```

## disassembly

```asm
0x1400032e0  cmp     qword ptr [rcx], 0
0x1400032e4  setz    al
0x1400032e7  retn
```
