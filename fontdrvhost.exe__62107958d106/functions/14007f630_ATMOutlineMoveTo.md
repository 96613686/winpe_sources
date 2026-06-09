# ATMOutlineMoveTo

- ea: `0x14007f630`
- end: `0x14007f698`
- name: `ATMOutlineMoveTo`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x140051e28`
- `0x14005c484`
- `0x14007f490`
- `0x14007f630`

## pseudocode

```c
int __fastcall ATMOutlineMoveTo(__int64 a1, __int64 a2)
{
  int result; // eax
  POINTFIX ptfx; // [rsp+30h] [rbp+8h]

  ATMOutlineClosePath(a2);
  ptfx.x = *(int *)a1 >> 12;
  ptfx.y = *(int *)(a1 + 4) >> 12;
  result = PATHOBJ_bMoveTo(*(PATHOBJ **)(a2 + 32), ptfx);
  if ( !result )
    *(_BYTE *)(a2 + 40) |= 2u;
  if ( (*(_BYTE *)(a2 + 40) & 4) != 0 )
    return UpdatePoint(*(_QWORD *)a1, (_DWORD *)(a2 + 8));
  return result;
}

```

## disassembly

```asm
0x14007f630  mov     [rsp+arg_8], rbx
0x14007f635  mov     [rsp+arg_10], rsi
0x14007f63a  push    rdi
0x14007f63b  sub     rsp, 20h
0x14007f63f  mov     rsi, rcx
0x14007f642  mov     rdi, rdx
0x14007f645  mov     rcx, rdx
0x14007f648  call    ATMOutlineClosePath
0x14007f64d  mov     eax, [rsi]
0x14007f64f  mov     rcx, [rdi+20h]; ppo
0x14007f653  sar     eax, 0Ch
0x14007f656  mov     [rsp+28h+ptfx.x], eax
0x14007f65a  mov     eax, [rsi+4]
0x14007f65d  sar     eax, 0Ch
0x14007f660  mov     [rsp+28h+ptfx.y], eax
0x14007f664  mov     rdx, qword ptr [rsp+28h+ptfx.x]; ptfx
0x14007f669  call    PATHOBJ_bMoveTo
0x14007f66e  test    eax, eax
0x14007f670  jnz     short loc_14007F676
0x14007f672  or      byte ptr [rdi+28h], 2
0x14007f676  test    byte ptr [rdi+28h], 4
0x14007f67a  jz      short loc_14007F688
0x14007f67c  mov     rcx, [rsi]
0x14007f67f  lea     rdx, [rdi+8]
0x14007f683  call    UpdatePoint
0x14007f688  mov     rbx, [rsp+28h+arg_8]
0x14007f68d  mov     rsi, [rsp+28h+arg_10]
0x14007f692  add     rsp, 20h
0x14007f696  pop     rdi
0x14007f697  retn
```
