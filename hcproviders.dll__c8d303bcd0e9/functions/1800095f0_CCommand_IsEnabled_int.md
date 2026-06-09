# CCommand::IsEnabled(int *)

- ea: `0x1800095f0`
- end: `0x1800095f8`
- name: `?IsEnabled@CCommand@@UEAAJPEAH@Z`
- size: `8`
- prototype: `__int64 __fastcall(CCommand *__hidden this, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CCommand::IsEnabled(CCommand *this, int *a2)
{
  *a2 = *((_DWORD *)this - 2);
  return 0;
}

```

## disassembly

```asm
0x1800095f0  mov     eax, [rcx-8]
0x1800095f3  mov     [rdx], eax
0x1800095f5  xor     eax, eax
0x1800095f7  retn
```
