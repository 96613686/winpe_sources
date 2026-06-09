# LuafvDereferenceUserStore

- ea: `0x14001dec8`
- end: `0x14001df0b`
- name: `LuafvDereferenceUserStore`
- size: `67`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1400179b0`
- `0x14001a3c8`
- `0x14001dc20`
- `0x140024a8c`
- `0x140024c20`

## callees

- `0x1400178a0`
- `0x14001d930`
- `0x14001dd90`
- `0x14001dec8`

## pseudocode

```c
void __fastcall LuafvDereferenceUserStore(__int64 a1)
{
  __int64 v2; // rcx

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 24), 0xFFFFFFFF) == 1 )
  {
    v2 = *(_QWORD *)(a1 + 72);
    if ( v2 )
      LuafvDereferenceTableNodeEx(v2, 0, 0);
    LuafvDereferenceUser(*(_QWORD *)(a1 + 16));
    LuafvFreePool(a1);
  }
}

```

## disassembly

```asm
0x14001dec8  push    rbx
0x14001deca  sub     rsp, 20h
0x14001dece  mov     rbx, rcx
0x14001ded1  or      eax, 0FFFFFFFFh
0x14001ded4  lock xadd [rcx+18h], eax
0x14001ded9  cmp     eax, 1
0x14001dedc  jz      short loc_14001DEE5
0x14001dede  add     rsp, 20h
0x14001dee2  pop     rbx
0x14001dee3  retn
0x14001dee5  mov     rcx, [rcx+48h]
0x14001dee9  test    rcx, rcx
0x14001deec  jz      short loc_14001DEF8
0x14001deee  xor     r8d, r8d
0x14001def1  xor     edx, edx
0x14001def3  call    LuafvDereferenceTableNodeEx
0x14001def8  mov     rcx, [rbx+10h]
0x14001defc  call    LuafvDereferenceUser
0x14001df01  mov     rcx, rbx
0x14001df04  call    LuafvFreePool
0x14001df09  jmp     short loc_14001DEDE
```
