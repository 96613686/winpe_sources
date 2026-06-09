# CCreatePacket::ReplaceCreatePacketRequestContext(CPacket *,CPacket *)

- ea: `0x14001255c`
- end: `0x140012616`
- name: `?ReplaceCreatePacketRequestContext@CCreatePacket@@QEAA_NPEAVCPacket@@0@Z`
- size: `186`
- prototype: `bool __fastcall(CCreatePacket *__hidden this, struct CPacket *, struct CPacket *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140012368`

## callees

- `0x14001255c`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400125fe`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400125fe`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140012573`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140012573`

## pseudocode

```c
char __fastcall CCreatePacket::ReplaceCreatePacketRequestContext(
        CCreatePacket **this,
        struct CPacket *a2,
        struct CPacket *a3)
{
  CCreatePacket *v6; // r10
  char v7; // bl
  char *v8; // rax
  char *v9; // r9
  _QWORD **v10; // r11
  _QWORD *i; // rdx
  _QWORD *v12; // r8
  _QWORD *v13; // rcx
  KIRQL Irql; // [rsp+50h] [rbp+8h] BYREF

  IoAcquireCancelSpinLock(&Irql);
  v6 = *this;
  v7 = 1;
  while ( 1 )
  {
    v8 = 0;
    v9 = (char *)v6 - 168;
    if ( this != (CCreatePacket **)v6 )
      v8 = (char *)v6 - 168;
    if ( !v8 )
      break;
    if ( this == (CCreatePacket **)v6 )
    {
      v9 = 0;
LABEL_7:
      v10 = (_QWORD **)*((_QWORD *)v9 + 7);
      for ( i = *v10; ; i = (_QWORD *)*i )
      {
        v12 = 0;
        if ( v10 != i )
          v12 = i;
        if ( !v12 )
          break;
        v13 = i;
        if ( v10 == i )
          v13 = 0;
        if ( (struct CPacket *)v13[2] == a2 )
        {
          v12[2] = a3;
          goto LABEL_22;
        }
      }
      goto LABEL_19;
    }
    if ( v6 == (CCreatePacket *)168 || (*((_DWORD *)v9 + 36) & 0x80) != 0 )
      goto LABEL_7;
    if ( *((struct CPacket **)v9 + 7) == a2 )
    {
      *((_QWORD *)v9 + 7) = a3;
      goto LABEL_22;
    }
LABEL_19:
    v6 = *(CCreatePacket **)v6;
  }
  v7 = 0;
LABEL_22:
  IoReleaseCancelSpinLock(Irql);
  return v7;
}

```

## disassembly

```asm
0x14001255c  push    rbx
0x14001255e  push    rbp
0x14001255f  push    rsi
0x140012560  push    rdi
0x140012561  sub     rsp, 28h
0x140012565  mov     rsi, rcx
0x140012568  mov     rdi, r8
0x14001256b  lea     rcx, [rsp+48h+Irql]; Irql
0x140012570  mov     rbp, rdx
0x140012573  call    cs:__imp_IoAcquireCancelSpinLock
0x14001257a  nop     dword ptr [rax+rax+00h]
0x14001257f  mov     r10, [rsi]
0x140012582  mov     bl, 1
0x140012584  xor     eax, eax
0x140012586  lea     r9, [r10-0A8h]
0x14001258d  cmp     rsi, r10
0x140012590  cmovnz  rax, r9
0x140012594  test    rax, rax
0x140012597  jz      short loc_1400125F8
0x140012599  cmp     rsi, r10
0x14001259c  jnz     short loc_1400125CE
0x14001259e  xor     r9d, r9d
0x1400125a1  mov     r11, [r9+38h]
0x1400125a5  mov     rdx, [r11]
0x1400125a8  xor     r8d, r8d
0x1400125ab  cmp     r11, rdx
0x1400125ae  cmovnz  r8, rdx
0x1400125b2  test    r8, r8
0x1400125b5  jz      short loc_1400125ED
0x1400125b7  xor     eax, eax
0x1400125b9  mov     rcx, rdx
0x1400125bc  cmp     r11, rdx
0x1400125bf  cmovz   rcx, rax
0x1400125c3  cmp     [rcx+10h], rbp
0x1400125c7  jz      short loc_1400125F2
0x1400125c9  mov     rdx, [rdx]
0x1400125cc  jmp     short loc_1400125A8
0x1400125ce  test    r9, r9
0x1400125d1  jz      short loc_1400125A1
0x1400125d3  mov     eax, [r9+90h]
0x1400125da  shr     eax, 7
0x1400125dd  test    bl, al
0x1400125df  jnz     short loc_1400125A1
0x1400125e1  cmp     [r9+38h], rbp
0x1400125e5  jnz     short loc_1400125ED
0x1400125e7  mov     [r9+38h], rdi
0x1400125eb  jmp     short loc_1400125FA
0x1400125ed  mov     r10, [r10]
0x1400125f0  jmp     short loc_140012584
0x1400125f2  mov     [r8+10h], rdi
0x1400125f6  jmp     short loc_1400125FA
0x1400125f8  xor     ebx, ebx
0x1400125fa  mov     cl, [rsp+48h+Irql]; Irql
0x1400125fe  call    cs:__imp_IoReleaseCancelSpinLock
0x140012605  nop     dword ptr [rax+rax+00h]
0x14001260a  mov     al, bl
0x14001260c  add     rsp, 28h
0x140012610  pop     rdi
0x140012611  pop     rsi
0x140012612  pop     rbp
0x140012613  pop     rbx
0x140012614  retn
```
