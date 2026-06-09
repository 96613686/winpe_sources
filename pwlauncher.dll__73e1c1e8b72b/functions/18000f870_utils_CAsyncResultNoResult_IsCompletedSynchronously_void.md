# utils::CAsyncResultNoResult::IsCompletedSynchronously(void)

- ea: `0x18000f870`
- end: `0x18000f87a`
- name: `?IsCompletedSynchronously@CAsyncResultNoResult@utils@@UEBA_NXZ`
- size: `10`
- prototype: `bool __fastcall(utils::CAsyncResultNoResult *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
bool __fastcall utils::CAsyncResultNoResult::IsCompletedSynchronously(utils::CAsyncResultNoResult *this)
{
  return *((_DWORD *)this + 12) == 1;
}

```

## disassembly

```asm
0x18000f870  mov     eax, [rcx+30h]
0x18000f873  cmp     eax, 1
0x18000f876  setz    al
0x18000f879  retn
```
