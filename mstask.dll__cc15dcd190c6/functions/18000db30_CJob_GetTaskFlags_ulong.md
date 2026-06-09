# CJob::GetTaskFlags(ulong *)

- ea: `0x18000db30`
- end: `0x18000db3d`
- name: `?GetTaskFlags@CJob@@UEAAJPEAK@Z`
- size: `13`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CJob::GetTaskFlags(CJob *this, unsigned int *a2)
{
  *a2 = *((_DWORD *)this + 23) & 0x7FFF;
  return 0;
}

```

## disassembly

```asm
0x18000db30  mov     eax, [rcx+5Ch]
0x18000db33  and     eax, 7FFFh
0x18000db38  mov     [rdx], eax
0x18000db3a  xor     eax, eax
0x18000db3c  retn
```
