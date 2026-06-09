# LuafvDereferenceUserStore

- ea: `0x14001de78`
- end: `0x14001debb`
- name: `LuafvDereferenceUserStore`
- size: `67`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140017960`
- `0x14001a378`
- `0x14001dbd0`
- `0x140024a3c`
- `0x140024bd0`

## callees

- `0x140017850`
- `0x14001d8e0`
- `0x14001dd40`
- `0x14001de78`

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
0x14001de78  push    rbx
0x14001de7a  sub     rsp, 20h
0x14001de7e  mov     rbx, rcx
0x14001de81  or      eax, 0FFFFFFFFh
0x14001de84  lock xadd [rcx+18h], eax
0x14001de89  cmp     eax, 1
0x14001de8c  jz      short loc_14001DE95
0x14001de8e  add     rsp, 20h
0x14001de92  pop     rbx
0x14001de93  retn
0x14001de95  mov     rcx, [rcx+48h]
0x14001de99  test    rcx, rcx
0x14001de9c  jz      short loc_14001DEA8
0x14001de9e  xor     r8d, r8d
0x14001dea1  xor     edx, edx
0x14001dea3  call    LuafvDereferenceTableNodeEx
0x14001dea8  mov     rcx, [rbx+10h]
0x14001deac  call    LuafvDereferenceUser
0x14001deb1  mov     rcx, rbx
0x14001deb4  call    LuafvFreePool
0x14001deb9  jmp     short loc_14001DE8E
```
