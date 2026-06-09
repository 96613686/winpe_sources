# CPacket::CreateXactDummy(CTransaction *)

- ea: `0x140015490`
- end: `0x1400155c1`
- name: `?CreateXactDummy@CPacket@@QEAAPEAV1@PEAVCTransaction@@@Z`
- size: `305`
- prototype: `struct CPacket *__fastcall(CPacket *__hidden this, struct CTransaction *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001fb20`

## callees

- `0x1400126fc`
- `0x140015490`
- `0x14001837c`
- `0x140019124`
- `0x140019148`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400154af`
- `ntoskrnl!ExAllocatePool2` at `0x1400154af`

## pseudocode

```c
struct CPacket *__fastcall CPacket::CreateXactDummy(CPacket *this, struct CTransaction *a2)
{
  struct CPacket *result; // rax
  struct CPacket *v5; // rdi
  CBaseObject *v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rax
  struct CPacket *v9; // rdx
  struct CDeviceExt *v10; // rcx
  struct CPacket *v11; // rdx
  unsigned int v12; // r8d
  unsigned int v13; // ecx
  unsigned __int32 v14; // edx

  result = (struct CPacket *)ExAllocatePool2(256, 112, 1096307021);
  v5 = result;
  if ( result )
  {
    v6 = (CBaseObject *)*((_QWORD *)this + 3);
    v7 = *((_QWORD *)this + 13);
    *((_DWORD *)result + 2) = 1;
    *(_QWORD *)result = &CQEntry::`vftable';
    *((_DWORD *)result + 4) = *((_DWORD *)this + 4);
    *((_QWORD *)result + 3) = v6;
    *((_QWORD *)result + 4) = 0;
    *((_QWORD *)result + 5) = 0;
    *((_DWORD *)result + 13) = 0;
    *((_QWORD *)result + 7) = 0;
    *((_QWORD *)result + 8) = 0;
    CBaseObject::AddRef(v6);
    *((_DWORD *)v5 + 24) = 0;
    *((_QWORD *)v5 + 9) = 0;
    *((_QWORD *)v5 + 10) = 0;
    *((_QWORD *)v5 + 11) = 0;
    *(_QWORD *)v5 = &CPacket::`vftable';
    v8 = *((_QWORD *)this + 13);
    *((_QWORD *)v5 + 13) = v7;
    SetLowestPacketAllocated(*(struct CDeviceExt **)(v8 + 64), v5);
    SetHighestPacketAllocated(v10, v9);
    *((_DWORD *)this + 13) |= 0x40000u;
    CQEntry::OtherPacket(this, v11);
    CQEntry::OtherPacket(v5, this);
    v12 = *((_DWORD *)this + 13);
    v13 = *((_DWORD *)v5 + 13) & 0xFE7FFFFF;
    *((_QWORD *)v5 + 5) = a2;
    v14 = v12 & 0x800000 ^ v13 | _byteswap_ulong(HIBYTE(v12) & 1);
    *((_DWORD *)v5 + 13) = v14 ^ (v12 ^ v14) & 0x2000000 ^ (v12 ^ v14 ^ (v12 ^ v14) & 0x2000000) & 0x40000;
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x140015490  push    rbx
0x140015492  push    rbp
0x140015493  push    rsi
0x140015494  push    rdi
0x140015495  sub     rsp, 28h
0x140015499  mov     rbp, rdx
0x14001549c  mov     rsi, rcx
0x14001549f  mov     edx, 70h ; 'p'
0x1400154a4  mov     ecx, 100h
0x1400154a9  mov     r8d, 4158514Dh
0x1400154af  call    cs:__imp_ExAllocatePool2
0x1400154b6  nop     dword ptr [rax+rax+00h]
0x1400154bb  mov     rdi, rax
0x1400154be  test    rax, rax
0x1400154c1  jz      loc_1400155B7
0x1400154c7  mov     rcx, [rsi+18h]; this
0x1400154cb  mov     rbx, [rsi+68h]
0x1400154cf  mov     dword ptr [rax+8], 1
0x1400154d6  lea     rax, ??_7CQEntry@@6B@; const CQEntry::`vftable'
0x1400154dd  mov     [rdi], rax
0x1400154e0  mov     eax, [rsi+10h]
0x1400154e3  mov     [rdi+10h], eax
0x1400154e6  mov     [rdi+18h], rcx
0x1400154ea  mov     qword ptr [rdi+20h], 0
0x1400154f2  mov     qword ptr [rdi+28h], 0
0x1400154fa  mov     dword ptr [rdi+34h], 0
0x140015501  mov     qword ptr [rdi+38h], 0
0x140015509  mov     qword ptr [rdi+40h], 0
0x140015511  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x140015516  mov     dword ptr [rdi+60h], 0
0x14001551d  lea     rax, ??_7CPacket@@6B@; const CPacket::`vftable'
0x140015524  mov     qword ptr [rdi+48h], 0
0x14001552c  mov     rdx, rdi; struct CPacket *
0x14001552f  mov     qword ptr [rdi+50h], 0
0x140015537  mov     qword ptr [rdi+58h], 0
0x14001553f  mov     [rdi], rax
0x140015542  mov     rax, [rsi+68h]
0x140015546  mov     [rdi+68h], rbx
0x14001554a  mov     rcx, [rax+40h]; struct CDeviceExt *
0x14001554e  call    ?SetLowestPacketAllocated@@YAXPEAUCDeviceExt@@PEAVCPacket@@@Z; SetLowestPacketAllocated(CDeviceExt *,CPacket *)
0x140015553  call    ?SetHighestPacketAllocated@@YAXPEAUCDeviceExt@@PEAVCPacket@@@Z; SetHighestPacketAllocated(CDeviceExt *,CPacket *)
0x140015558  mov     ebx, 40000h
0x14001555d  mov     rcx, rsi; this
0x140015560  or      [rsi+34h], ebx
0x140015563  call    ?OtherPacket@CQEntry@@QEAAXPEAVCPacket@@@Z; CQEntry::OtherPacket(CPacket *)
0x140015568  mov     rdx, rsi; struct CPacket *
0x14001556b  mov     rcx, rdi; this
0x14001556e  call    ?OtherPacket@CQEntry@@QEAAXPEAVCPacket@@@Z; CQEntry::OtherPacket(CPacket *)
0x140015573  mov     r8d, [rsi+34h]
0x140015577  mov     edx, r8d
0x14001557a  mov     ecx, [rdi+34h]
0x14001557d  mov     eax, r8d
0x140015580  and     ecx, 0FE7FFFFFh
0x140015586  shr     edx, 18h
0x140015589  and     eax, 800000h
0x14001558e  mov     [rdi+28h], rbp
0x140015592  xor     ecx, eax
0x140015594  and     edx, 1
0x140015597  bswap   edx
0x140015599  or      edx, ecx
0x14001559b  mov     ecx, edx
0x14001559d  xor     ecx, r8d
0x1400155a0  and     ecx, 2000000h
0x1400155a6  xor     ecx, edx
0x1400155a8  mov     eax, ecx
0x1400155aa  xor     eax, r8d
0x1400155ad  and     eax, ebx
0x1400155af  xor     eax, ecx
0x1400155b1  mov     [rdi+34h], eax
0x1400155b4  mov     rax, rdi
0x1400155b7  add     rsp, 28h
0x1400155bb  pop     rdi
0x1400155bc  pop     rsi
0x1400155bd  pop     rbp
0x1400155be  pop     rbx
0x1400155bf  retn
```
