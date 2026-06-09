# CJob::SetTaskFlags(ulong)

- ea: `0x18000de50`
- end: `0x18000de65`
- name: `?SetTaskFlags@CJob@@UEAAJK@Z`
- size: `21`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CJob::SetTaskFlags(CJob *this, unsigned __int16 a2)
{
  int v2; // eax

  v2 = *((_DWORD *)this + 23);
  *((_DWORD *)this + 22) |= 0x40000000u;
  *((_DWORD *)this + 23) ^= (a2 ^ (unsigned __int16)v2) & 0x7FFF;
  return 0;
}

```

## disassembly

```asm
0x18000de50  mov     eax, [rcx+5Ch]
0x18000de53  bts     dword ptr [rcx+58h], 1Eh
0x18000de58  xor     eax, edx
0x18000de5a  and     eax, 7FFFh
0x18000de5f  xor     [rcx+5Ch], eax
0x18000de62  xor     eax, eax
0x18000de64  retn
```
