# CSslUserContext::GetReadWriteKeys(unsigned __int64 *,unsigned __int64 *)

- ea: `0x14000afd0`
- end: `0x14000afdf`
- name: `?GetReadWriteKeys@CSslUserContext@@UEAAXPEA_K0@Z`
- size: `15`
- prototype: `void __fastcall(CSslUserContext *__hidden this, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall CSslUserContext::GetReadWriteKeys(CSslUserContext *this, unsigned __int64 *a2, unsigned __int64 *a3)
{
  *a2 = *((_QWORD *)this + 5);
  *a3 = *((_QWORD *)this + 6);
}

```

## disassembly

```asm
0x14000afd0  mov     rax, [rcx+28h]
0x14000afd4  mov     [rdx], rax
0x14000afd7  mov     rax, [rcx+30h]
0x14000afdb  mov     [r8], rax
0x14000afde  retn
```
