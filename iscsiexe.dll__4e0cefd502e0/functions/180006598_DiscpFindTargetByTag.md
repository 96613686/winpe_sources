# DiscpFindTargetByTag

- ea: `0x180006598`
- end: `0x18000661b`
- name: `DiscpFindTargetByTag`
- size: `131`
- prototype: `__int64 __fastcall(__int64, int, volatile signed __int32 **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ea0`
- `0x1800064f8`
- `0x180006c30`
- `0x180007320`

## callees

- `0x180006404`
- `0x180006598`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x180006603`
- `ISCSIUM!DiscpFreeMemory` at `0x180006603`

## pseudocode

```c
__int64 __fastcall DiscpFindTargetByTag(__int64 a1, int a2, volatile signed __int32 **a3)
{
  unsigned int Target; // ebx
  __int64 v6; // rcx
  _QWORD *v7; // rdx
  volatile signed __int32 *v8; // rax
  __int64 v10; // [rsp+48h] [rbp+20h] BYREF

  v10 = 0;
  Target = DiscpFindTarget(a1, 0, 0, &v10);
  if ( !Target )
  {
    v6 = v10;
    Target = -268500951;
    v7 = (_QWORD *)(v10 + 16);
    while ( 1 )
    {
      v8 = (volatile signed __int32 *)(v7 - 2);
      if ( *((_DWORD *)v7 + 7) == a2 )
        break;
      v7 = (_QWORD *)*v7;
      if ( v7 == (_QWORD *)(v10 + 16) )
        goto LABEL_7;
    }
    _InterlockedIncrement(v8 + 8);
    *a3 = v8;
    Target = 0;
LABEL_7:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 32), 0xFFFFFFFF) == 1 )
      DiscpFreeMemory(v6);
  }
  return Target;
}

```

## disassembly

```asm
0x180006598  mov     rax, rsp
0x18000659b  mov     [rax+8], rbx
0x18000659f  mov     [rax+10h], rsi
0x1800065a3  push    rdi
0x1800065a4  sub     rsp, 20h
0x1800065a8  mov     rdi, r8
0x1800065ab  mov     qword ptr [rax+20h], 0
0x1800065b3  mov     esi, edx
0x1800065b5  lea     r9, [rax+20h]
0x1800065b9  xor     r8d, r8d
0x1800065bc  xor     edx, edx
0x1800065be  call    DiscpFindTarget
0x1800065c3  mov     ebx, eax
0x1800065c5  test    eax, eax
0x1800065c7  jnz     short loc_180006609
0x1800065c9  mov     rcx, [rsp+28h+arg_18]
0x1800065ce  mov     ebx, 0EFFF0029h
0x1800065d3  lea     r8, [rcx+10h]
0x1800065d7  mov     rdx, r8
0x1800065da  lea     rax, [rdx-10h]
0x1800065de  cmp     [rax+2Ch], esi
0x1800065e1  jz      short loc_1800065ED
0x1800065e3  mov     rdx, [rdx]
0x1800065e6  cmp     rdx, r8
0x1800065e9  jnz     short loc_1800065DA
0x1800065eb  jmp     short loc_1800065F6
0x1800065ed  lock inc dword ptr [rax+20h]
0x1800065f1  mov     [rdi], rax
0x1800065f4  xor     ebx, ebx
0x1800065f6  or      eax, 0FFFFFFFFh
0x1800065f9  lock xadd [rcx+20h], eax
0x1800065fe  cmp     eax, 1
0x180006601  jnz     short loc_180006609
0x180006603  call    cs:__imp_DiscpFreeMemory
0x180006609  mov     rsi, [rsp+28h+arg_8]
0x18000660e  mov     eax, ebx
0x180006610  mov     rbx, [rsp+28h+arg_0]
0x180006615  add     rsp, 20h
0x180006619  pop     rdi
0x18000661a  retn
```
