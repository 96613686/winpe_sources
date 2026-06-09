# CAssociationCallback::GetImpersonationToken(void * *)

- ea: `0x140016ff0`
- end: `0x140016ffa`
- name: `?GetImpersonationToken@CAssociationCallback@@UEAAJPEAPEAX@Z`
- size: `10`
- prototype: `__int64 __fastcall(CAssociationCallback *__hidden this, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CAssociationCallback::GetImpersonationToken(CAssociationCallback *this, void **a2)
{
  *a2 = (void *)*((_QWORD *)this + 11);
  return 0;
}

```

## disassembly

```asm
0x140016ff0  mov     rax, [rcx+58h]
0x140016ff4  mov     [rdx], rax
0x140016ff7  xor     eax, eax
0x140016ff9  retn
```
