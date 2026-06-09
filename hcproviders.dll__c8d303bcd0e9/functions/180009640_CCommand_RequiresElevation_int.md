# CCommand::RequiresElevation(int *)

- ea: `0x180009640`
- end: `0x180009648`
- name: `?RequiresElevation@CCommand@@UEAAJPEAH@Z`
- size: `8`
- prototype: `__int64 __fastcall(CCommand *__hidden this, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CCommand::RequiresElevation(CCommand *this, int *a2)
{
  *a2 = *((_DWORD *)this - 1);
  return 0;
}

```

## disassembly

```asm
0x180009640  mov     eax, [rcx-4]
0x180009643  mov     [rdx], eax
0x180009645  xor     eax, eax
0x180009647  retn
```
