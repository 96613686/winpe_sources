# CNotification::GetOptions(IHCCommand * *)

- ea: `0x180009930`
- end: `0x18000995b`
- name: `?GetOptions@CNotification@@UEAAJPEAPEAUIHCCommand@@@Z`
- size: `43`
- prototype: `__int64 __fastcall(CNotification *__hidden this, struct IHCCommand **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009930`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CNotification::GetOptions(CNotification *this, struct IHCCommand **a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *((_QWORD *)this + 24);
  result = 0;
  if ( v2 )
    return (**(__int64 (__fastcall ***)(__int64, GUID *, struct IHCCommand **))(v2 + 32))(
             v2 + 32,
             &GUID_3d2eafc0_96d0_4925_9f7d_ff80b168f243,
             a2);
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180009930  mov     rcx, [rcx+0C0h]
0x180009937  xor     eax, eax
0x180009939  test    rcx, rcx
0x18000993c  jz      short loc_180009957
0x18000993e  add     rcx, 20h ; ' '
0x180009942  mov     r8, rdx
0x180009945  lea     rdx, _GUID_3d2eafc0_96d0_4925_9f7d_ff80b168f243
0x18000994c  mov     rax, [rcx]
0x18000994f  mov     rax, [rax]
0x180009952  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180009957  mov     [rdx], rax
0x18000995a  retn
```
