# CTransaction::DeleteXactDummy(CPacket *)

- ea: `0x14001fb64`
- end: `0x14001fbae`
- name: `?DeleteXactDummy@CTransaction@@AEAAJPEAVCPacket@@@Z`
- size: `74`
- prototype: `int(CTransaction *__hidden this, struct CPacket *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001f8d4`

## callees

- `0x140012754`
- `0x14001837c`
- `0x14001fb64`

## pseudocode

```c
__int64 __fastcall CTransaction::DeleteXactDummy(CTransaction *this, struct CPacket *a2)
{
  CQEntry *v2; // rcx

  v2 = (CQEntry *)*((_QWORD *)a2 + 8);
  if ( !v2 )
    return 3221225626LL;
  *((_QWORD *)v2 + 5) = 0;
  CQEntry::OtherPacket(v2, 0);
  *((_DWORD *)a2 + 4) = -1;
  CQEntry::OtherPacket(a2, 0);
  CBaseObject::Release(a2);
  return 0;
}

```

## disassembly

```asm
0x14001fb64  push    rbx
0x14001fb66  sub     rsp, 20h
0x14001fb6a  mov     rcx, [rdx+40h]; this
0x14001fb6e  mov     rbx, rdx
0x14001fb71  test    rcx, rcx
0x14001fb74  jnz     short loc_14001FB7D
0x14001fb76  mov     eax, 0C000009Ah
0x14001fb7b  jmp     short loc_14001FBA7
0x14001fb7d  xor     edx, edx; struct CPacket *
0x14001fb7f  mov     qword ptr [rcx+28h], 0
0x14001fb87  call    ?OtherPacket@CQEntry@@QEAAXPEAVCPacket@@@Z; CQEntry::OtherPacket(CPacket *)
0x14001fb8c  xor     edx, edx; struct CPacket *
0x14001fb8e  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x14001fb95  mov     rcx, rbx; this
0x14001fb98  call    ?OtherPacket@CQEntry@@QEAAXPEAVCPacket@@@Z; CQEntry::OtherPacket(CPacket *)
0x14001fb9d  mov     rcx, rbx; this
0x14001fba0  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14001fba5  xor     eax, eax
0x14001fba7  add     rsp, 20h
0x14001fbab  pop     rbx
0x14001fbac  retn
```
