# utils::CAsyncResultNoResult::IsCompleted(void)

- ea: `0x18000f860`
- end: `0x18000f869`
- name: `?IsCompleted@CAsyncResultNoResult@utils@@UEBA_NXZ`
- size: `9`
- prototype: `bool __fastcall(utils::CAsyncResultNoResult *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
bool __fastcall utils::CAsyncResultNoResult::IsCompleted(utils::CAsyncResultNoResult *this)
{
  return *((_DWORD *)this + 12) != 0;
}

```

## disassembly

```asm
0x18000f860  mov     eax, [rcx+30h]
0x18000f863  test    eax, eax
0x18000f865  setnz   al
0x18000f868  retn
```
