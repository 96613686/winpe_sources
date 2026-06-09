# CPacket::CacheCurrentState(CPacketBuffer *)

- ea: `0x14001428c`
- end: `0x140014366`
- name: `?CacheCurrentState@CPacket@@QEAAXPEAVCPacketBuffer@@@Z`
- size: `218`
- prototype: `void __fastcall(CPacket *__hidden this, struct CPacketBuffer *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14001569c`
- `0x140015ac4`
- `0x14001c230`
- `0x14001e0c0`
- `0x14001e634`

## callees

- `0x14001428c`

## pseudocode

```c
void __fastcall CPacket::CacheCurrentState(CPacket *this, struct CPacketBuffer *a2)
{
  unsigned __int64 v4; // r11
  __int64 v5; // r8
  int v6; // ecx
  int v7; // edx
  int v8; // eax
  unsigned int v9; // edx
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rax

  v4 = ((unsigned __int64)a2 + 4) & -(__int64)(a2 != 0);
  v5 = (__int64)a2 + 96;
  if ( !a2 )
    v5 = 60;
  v6 = *((_DWORD *)this + 13) ^ (*((_DWORD *)this + 13) ^ (*(_DWORD *)v5 << 9)) & 0x20000000;
  *((_DWORD *)this + 13) = v6;
  v7 = v6 ^ (v6 ^ (*(_DWORD *)((((unsigned __int64)a2 + 4) & -(__int64)(a2 != 0)) + 0xC) << 28)) & 0x10000000;
  *((_DWORD *)this + 13) = v7;
  if ( (*(_BYTE *)(v4 + 12) & 1) != 0 && (*(_DWORD *)v5 & 0x200) != 0 )
    v8 = 0x40000000;
  else
    v8 = 0;
  v9 = v8 | v7 & 0xBFFFFFFF;
  *((_DWORD *)this + 13) = v9;
  if ( (*(_DWORD *)v5 & 0x100000) != 0 )
  {
    v10 = 0x700000000000000LL;
  }
  else
  {
    v11 = (__int64)a2 + 38;
    if ( !a2 )
      v11 = 2;
    v10 = (7LL - (*(_BYTE *)v11 & 7)) << 56;
  }
  v12 = (v10 + (*(_QWORD *)v4 & 0xFFFFFFFFFFFFFFLL)) & -(__int64)(*(_QWORD *)v4 != 0);
  *((_DWORD *)this + 13) = v9 | 0x8000000;
  *((_QWORD *)this + 7) = v12;
}

```

## disassembly

```asm
0x14001428c  mov     r9, rcx
0x14001428f  lea     r8, [rdx+4]
0x140014293  mov     rax, rdx
0x140014296  mov     r10, rdx
0x140014299  neg     rax
0x14001429c  mov     eax, [rcx+34h]
0x14001429f  mov     ecx, 3Ch ; '<'
0x1400142a4  sbb     r11, r11
0x1400142a7  and     r11, r8
0x1400142aa  lea     r8, [rdx+60h]
0x1400142ae  test    rdx, rdx
0x1400142b1  cmovz   r8, rcx
0x1400142b5  mov     ecx, [r8]
0x1400142b8  shl     ecx, 9
0x1400142bb  xor     ecx, eax
0x1400142bd  and     ecx, 20000000h
0x1400142c3  xor     ecx, eax
0x1400142c5  mov     [r9+34h], ecx
0x1400142c9  mov     edx, [r11+0Ch]
0x1400142cd  shl     edx, 1Ch
0x1400142d0  xor     edx, ecx
0x1400142d2  and     edx, 10000000h
0x1400142d8  xor     edx, ecx
0x1400142da  mov     ecx, 2
0x1400142df  mov     [r9+34h], edx
0x1400142e3  test    byte ptr [r11+0Ch], 1
0x1400142e8  jz      short loc_1400142FB
0x1400142ea  mov     eax, [r8]
0x1400142ed  shr     eax, 8
0x1400142f0  test    cl, al
0x1400142f2  jz      short loc_1400142FB
0x1400142f4  mov     eax, 40000000h
0x1400142f9  jmp     short loc_1400142FD
0x1400142fb  xor     eax, eax
0x1400142fd  btr     edx, 1Eh
0x140014301  or      edx, eax
0x140014303  mov     [r9+34h], edx
0x140014307  test    dword ptr [r8], 100000h
0x14001430e  jz      short loc_14001431C
0x140014310  mov     r8, 700000000000000h
0x14001431a  jmp     short loc_14001433A
0x14001431c  test    r10, r10
0x14001431f  lea     rax, [r10+26h]
0x140014323  mov     r8d, 7
0x140014329  cmovz   rax, rcx
0x14001432d  movzx   ecx, byte ptr [rax]
0x140014330  and     rcx, r8
0x140014333  sub     r8, rcx
0x140014336  shl     r8, 38h
0x14001433a  mov     rax, [r11]
0x14001433d  mov     r10, 0FFFFFFFFFFFFFFh
0x140014347  mov     rcx, rax
0x14001434a  and     rcx, r10
0x14001434d  add     rcx, r8
0x140014350  neg     rax
0x140014353  sbb     rax, rax
0x140014356  bts     edx, 1Bh
0x14001435a  and     rax, rcx
0x14001435d  mov     [r9+34h], edx
0x140014361  mov     [r9+38h], rax
0x140014365  retn
```
