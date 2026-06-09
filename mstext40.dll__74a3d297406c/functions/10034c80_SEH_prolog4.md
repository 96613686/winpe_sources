# __SEH_prolog4

- ea: `0x10034c80`
- end: `0x10034cc5`
- name: `__SEH_prolog4`
- size: `69`
- prototype: ``
- caller_count: `25`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1002e1ef`
- `0x1002e384`
- `0x1002e746`
- `0x1002eac8`
- `0x1002eb6e`
- `0x1002ef30`
- `0x1002f122`
- `0x10032330`
- `0x10033cf7`
- `0x100344f8`
- `0x10034efc`
- `0x10035fac`
- `0x100373d2`
- `0x10037d26`
- `0x1003a190`
- `0x1003a2a1`
- `0x1003a31c`
- `0x1003b7cd`
- `0x1003b9aa`
- `0x1003bafa`
- `0x1003bbde`
- `0x1003c2b7`
- `0x1003cbc8`
- `0x1003cc3f`
- `0x1003cd5e`

## pseudocode

```c
_DWORD *__cdecl _SEH_prolog4(int a1, int a2)
{
  void *v4; // esp
  void *v6; // [esp-18h] [ebp-18h]
  _DWORD v7[2]; // [esp-8h] [ebp-8h] BYREF
  _UNKNOWN *retaddr; // [esp+0h] [ebp+0h]
  int v9; // [esp+4h] [ebp+4h]

  v7[1] = _except_handler4;
  v7[0] = NtCurrentTeb()->NtTib.ExceptionList;
  v4 = alloca(a2);
  v9 = -2;
  retaddr = v6;
  return v7;
}

```

## disassembly

```asm
0x10034c80  push    offset __except_handler4
0x10034c85  push    large dword ptr fs:0
0x10034c8c  mov     eax, [esp+8+arg_4]
0x10034c90  mov     [esp+8+arg_4], ebp
0x10034c94  lea     ebp, [esp+8+arg_4]
0x10034c98  sub     esp, eax
0x10034c9a  push    ebx
0x10034c9b  push    esi
0x10034c9c  push    edi
0x10034c9d  mov     eax, ___security_cookie
0x10034ca2  xor     [ebp-4], eax
0x10034ca5  xor     eax, ebp
0x10034ca7  push    eax
0x10034ca8  mov     [ebp-18h], esp
0x10034cab  push    dword ptr [ebp-8]
0x10034cae  mov     eax, [ebp-4]
0x10034cb1  mov     dword ptr [ebp-4], 0FFFFFFFEh
0x10034cb8  mov     [ebp-8], eax
0x10034cbb  lea     eax, [ebp-10h]
0x10034cbe  mov     large fs:0, eax
0x10034cc4  retn
```
