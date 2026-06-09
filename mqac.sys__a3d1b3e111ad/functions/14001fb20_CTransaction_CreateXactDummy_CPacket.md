# CTransaction::CreateXactDummy(CPacket *)

- ea: `0x14001fb20`
- end: `0x14001fb5b`
- name: `?CreateXactDummy@CTransaction@@AEAAJPEAVCPacket@@@Z`
- size: `59`
- prototype: `__int64 __fastcall(CTransaction *__hidden this, struct CPacket *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140018150`
- `0x1400201b8`

## callees

- `0x140015490`
- `0x140019770`
- `0x14001fb20`

## pseudocode

```c
__int64 __fastcall CTransaction::CreateXactDummy(CTransaction *this, struct CPacket *a2)
{
  struct CPacket *XactDummy; // rax

  XactDummy = CPacket::CreateXactDummy(a2, this);
  if ( !XactDummy )
    return 3221225626LL;
  XList<CPacket,72>::insert((char *)this + 72, XactDummy);
  ++*((_DWORD *)this + 22);
  return 0;
}

```

## disassembly

```asm
0x14001fb20  push    rbx
0x14001fb22  sub     rsp, 20h
0x14001fb26  mov     rax, rdx
0x14001fb29  mov     rbx, rcx
0x14001fb2c  mov     rdx, rcx; struct CTransaction *
0x14001fb2f  mov     rcx, rax; this
0x14001fb32  call    ?CreateXactDummy@CPacket@@QEAAPEAV1@PEAVCTransaction@@@Z; CPacket::CreateXactDummy(CTransaction *)
0x14001fb37  test    rax, rax
0x14001fb3a  jnz     short loc_14001FB43
0x14001fb3c  mov     eax, 0C000009Ah
0x14001fb41  jmp     short loc_14001FB54
0x14001fb43  lea     rcx, [rbx+48h]
0x14001fb47  mov     rdx, rax
0x14001fb4a  call    ?insert@?$XList@VCPacket@@$0EI@@@QEAAXPEAVCPacket@@@Z; XList<CPacket,72>::insert(CPacket *)
0x14001fb4f  inc     dword ptr [rbx+58h]
0x14001fb52  xor     eax, eax
0x14001fb54  add     rsp, 20h
0x14001fb58  pop     rbx
0x14001fb59  retn
```
