# CPacket::PacketRundown(long)

- ea: `0x1400183c4`
- end: `0x14001840a`
- name: `?PacketRundown@CPacket@@QEAAXJ@Z`
- size: `70`
- prototype: `void __fastcall(CPacket *__hidden this, int)`
- caller_count: `12`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000df60`
- `0x140014ef8`
- `0x140015ac4`
- `0x1400177c4`
- `0x140017d9c`
- `0x140017ec4`
- `0x14001821c`
- `0x140018b58`
- `0x14001d390`
- `0x14001e0c0`
- `0x14001f1c4`
- `0x14001f8d4`

## callees

- `0x140012754`
- `0x140014850`
- `0x140014c48`
- `0x1400183c4`

## pseudocode

```c
void __fastcall CPacket::PacketRundown(CPacket *this, int a2)
{
  int v4; // eax

  *((_DWORD *)this + 13) |= 0x30000u;
  CPacket::CancelTimeout(this);
  CPacket::CompleteWriter(this, a2);
  v4 = *((_DWORD *)this + 13);
  if ( v4 >= 0 && (v4 & 0x40000) == 0 )
    CBaseObject::Release(this);
}

```

## disassembly

```asm
0x1400183c4  mov     [rsp+arg_0], rbx
0x1400183c9  push    rdi
0x1400183ca  sub     rsp, 20h
0x1400183ce  or      dword ptr [rcx+34h], 30000h
0x1400183d5  mov     ebx, edx
0x1400183d7  mov     rdi, rcx
0x1400183da  call    ?CancelTimeout@CPacket@@AEAAXXZ; CPacket::CancelTimeout(void)
0x1400183df  mov     edx, ebx; int
0x1400183e1  mov     rcx, rdi; this
0x1400183e4  call    ?CompleteWriter@CPacket@@QEAAXJ@Z; CPacket::CompleteWriter(long)
0x1400183e9  mov     eax, [rdi+34h]
0x1400183ec  test    eax, eax
0x1400183ee  js      short loc_1400183FE
0x1400183f0  bt      eax, 12h
0x1400183f4  jb      short loc_1400183FE
0x1400183f6  mov     rcx, rdi; this
0x1400183f9  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x1400183fe  mov     rbx, [rsp+28h+arg_0]
0x140018403  add     rsp, 20h
0x140018407  pop     rdi
0x140018408  retn
```
