# CPopupCommand::get_ID(uint *)

- ea: `0x180002990`
- end: `0x180002998`
- name: `?get_ID@CPopupCommand@@UEAAJPEAI@Z`
- size: `8`
- prototype: `__int64 __fastcall(CPopupCommand *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CPopupCommand::get_ID(CPopupCommand *this, unsigned int *a2)
{
  *a2 = *((_DWORD *)this + 4);
  return 0;
}

```

## disassembly

```asm
0x180002990  mov     eax, [rcx+10h]
0x180002993  mov     [rdx], eax
0x180002995  xor     eax, eax
0x180002997  retn
```
