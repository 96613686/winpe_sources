# JsonException::JsonException(long)

- ea: `0x14001c78c`
- end: `0x14001c7a4`
- name: `??0JsonException@@QEAA@J@Z`
- size: `24`
- prototype: `JsonException *__fastcall(JsonException *__hidden this, int)`
- caller_count: `13`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x14001cda4`
- `0x14001ce88`
- `0x14001d2d4`
- `0x14001d400`
- `0x140023578`
- `0x140023844`
- `0x1400239a4`
- `0x140023c5c`
- `0x140023e64`
- `0x14002401c`
- `0x14002410c`
- `0x1400244d4`
- `0x1400245d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
JsonException *__fastcall JsonException::JsonException(JsonException *this, int a2)
{
  JsonException *result; // rax

  *((_DWORD *)this + 2) = a2;
  *(_QWORD *)this = &JsonException::`vftable';
  result = this;
  *((_DWORD *)this + 3) = 0;
  return result;
}

```

## disassembly

```asm
0x14001c78c  lea     rax, ??_7JsonException@@6B@; const JsonException::`vftable'
0x14001c793  mov     [rcx+8], edx
0x14001c796  mov     [rcx], rax
0x14001c799  mov     rax, rcx
0x14001c79c  mov     dword ptr [rcx+0Ch], 0
0x14001c7a3  retn
```
