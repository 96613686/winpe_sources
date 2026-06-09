# CsrLocateThreadByClientId

- ea: `0x180006270`
- end: `0x1800062d2`
- name: `CsrLocateThreadByClientId`
- size: `98`
- prototype: `__int64 *__fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800097f0`
- `0x18000a1f0`

## callees

- `0x180006270`

## pseudocode

```c
__int64 *__fastcall CsrLocateThreadByClientId(_QWORD *a1, __int64 a2)
{
  unsigned int v3; // eax
  __int64 *v4; // rdx
  __int64 *i; // rax

  v3 = (*(_DWORD *)(a2 + 8) >> 2) & 0x3FF;
  if ( a1 )
    *a1 = 0;
  v4 = &CsrThreadHashTable[2 * v3];
  for ( i = (__int64 *)*v4; ; i = (__int64 *)*i )
  {
    if ( i == v4 )
      return 0;
    if ( i[3] == *(_QWORD *)(a2 + 8) && i[2] == *(_QWORD *)a2 )
      break;
  }
  if ( a1 )
    *a1 = i[4];
  return i - 3;
}

```

## disassembly

```asm
0x180006270  mov     eax, [rdx+8]
0x180006273  mov     r10, rdx
0x180006276  shr     eax, 2
0x180006279  mov     r9, rcx
0x18000627c  and     eax, 3FFh
0x180006281  test    rcx, rcx
0x180006284  jz      short loc_18000628D
0x180006286  mov     qword ptr [rcx], 0
0x18000628d  mov     edx, eax
0x18000628f  lea     rcx, CsrThreadHashTable
0x180006296  shl     rdx, 4
0x18000629a  add     rdx, rcx
0x18000629d  mov     rax, [rdx]
0x1800062a0  cmp     rax, rdx
0x1800062a3  jz      short loc_1800062CF
0x1800062a5  mov     rcx, [r10+8]
0x1800062a9  cmp     [rax+18h], rcx
0x1800062ad  jz      short loc_1800062B4
0x1800062af  mov     rax, [rax]
0x1800062b2  jmp     short loc_1800062A0
0x1800062b4  mov     rcx, [r10]
0x1800062b7  cmp     [rax+10h], rcx
0x1800062bb  jnz     short loc_1800062AF
0x1800062bd  test    r9, r9
0x1800062c0  jz      short loc_1800062C9
0x1800062c2  mov     rcx, [rax+20h]
0x1800062c6  mov     [r9], rcx
0x1800062c9  add     rax, 0FFFFFFFFFFFFFFE8h
0x1800062cd  retn
0x1800062cf  xor     eax, eax
0x1800062d1  retn
```
