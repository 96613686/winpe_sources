# _utils::CThreadPool::StartUserWorkItem_::_1_::dtor$0

- ea: `0x180010a56`
- end: `0x180010a64`
- name: `_utils::CThreadPool::StartUserWorkItem_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010a5d`

## pseudocode

```c
void __fastcall utils::CThreadPool::StartUserWorkItem_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 72));
}

```

## disassembly

```asm
0x180010a56  mov     rcx, [rdx+48h]
0x180010a5d  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
