# CACHED_FILE_INFO::GetSize(_ULARGE_INTEGER *)

- ea: `0x180002700`
- end: `0x18000270b`
- name: `?GetSize@CACHED_FILE_INFO@@UEBAXPEAT_ULARGE_INTEGER@@@Z`
- size: `11`
- prototype: `void __fastcall(CACHED_FILE_INFO *__hidden this, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall CACHED_FILE_INFO::GetSize(CACHED_FILE_INFO *this, union _ULARGE_INTEGER *a2)
{
  *a2 = *(union _ULARGE_INTEGER *)((char *)this + 352);
}

```

## disassembly

```asm
0x180002700  mov     rax, [rcx+160h]
0x180002707  mov     [rdx], rax
0x18000270a  retn
```
