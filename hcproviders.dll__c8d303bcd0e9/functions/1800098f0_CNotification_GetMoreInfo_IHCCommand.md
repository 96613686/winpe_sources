# CNotification::GetMoreInfo(IHCCommand * *)

- ea: `0x1800098f0`
- end: `0x18000991b`
- name: `?GetMoreInfo@CNotification@@UEAAJPEAPEAUIHCCommand@@@Z`
- size: `43`
- prototype: `__int64 __fastcall(CNotification *__hidden this, struct IHCCommand **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800098f0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CNotification::GetMoreInfo(CNotification *this, struct IHCCommand **a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *((_QWORD *)this + 23);
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
0x1800098f0  mov     rcx, [rcx+0B8h]
0x1800098f7  xor     eax, eax
0x1800098f9  test    rcx, rcx
0x1800098fc  jz      short loc_180009917
0x1800098fe  add     rcx, 20h ; ' '
0x180009902  mov     r8, rdx
0x180009905  lea     rdx, _GUID_3d2eafc0_96d0_4925_9f7d_ff80b168f243
0x18000990c  mov     rax, [rcx]
0x18000990f  mov     rax, [rax]
0x180009912  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180009917  mov     [rdx], rax
0x18000991a  retn
```
