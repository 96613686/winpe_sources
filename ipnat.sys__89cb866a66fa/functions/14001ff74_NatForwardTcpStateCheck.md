# NatForwardTcpStateCheck

- ea: `0x14001ff74`
- end: `0x14002021d`
- name: `NatForwardTcpStateCheck`
- size: `681`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140020580`
- `0x140020970`
- `0x140021010`
- `0x140021150`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14001ff74`

## pseudocode

```c
__int64 __fastcall NatForwardTcpStateCheck(__int64 a1, __int64 a2)
{
  unsigned __int16 v4; // bx
  int v5; // eax
  unsigned int v6; // ebx
  PDEVICE_OBJECT v8; // rcx
  unsigned __int16 v9; // dx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
  }
  v4 = *(_WORD *)(a2 + 12) & 0x3F00;
  if ( DisableTcpFlagChecks )
    v4 = *(_WORD *)(a2 + 12) & 0x1700;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xBu,
      (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids,
      v4);
  }
  v5 = *(_DWORD *)(a1 + 240);
  if ( (v5 & 0x200) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xCu,
        (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
    }
    v6 = (v4 >> 9) & 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xDu,
        (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids,
        v6);
    }
    return v6;
  }
  if ( (v5 & 4) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xEu,
        (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
    }
    if ( (v4 & 0x1200) == 0x1000 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0xFu,
          (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
      }
      *(_DWORD *)(a1 + 240) |= 0x200u;
      goto LABEL_54;
    }
    if ( ((v4 - 512) & 0xEDFF) != 0 || v4 == 4608 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return 1;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x10u,
          (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
      {
        return 1;
      }
      v9 = 17;
      goto LABEL_51;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x12u,
        (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
    }
    if ( v4 != 512 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
      {
        return 1;
      }
      v9 = 19;
LABEL_51:
      WPP_SF_d((__int64)v8->AttachedDevice, v9, (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids, 1);
      return 1;
    }
    *(_DWORD *)(a1 + 240) |= 2u;
  }
LABEL_54:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x14u,
      (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x14001ff74  push    rbx
0x14001ff76  push    rbp
0x14001ff77  push    rsi
0x14001ff78  push    rdi
0x14001ff79  push    r13
0x14001ff7b  push    r14
0x14001ff7d  push    r15
0x14001ff7f  sub     rsp, 20h
0x14001ff83  mov     rsi, rdx
0x14001ff86  mov     rdi, rcx
0x14001ff89  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ff90  lea     r14, WPP_GLOBAL_Control
0x14001ff97  lea     r15, WPP_876e08a63f053efae1df392b423d899c_Traceguids
0x14001ff9e  mov     ebp, 1
0x14001ffa3  cmp     rcx, r14
0x14001ffa6  jz      short loc_14001FFC5
0x14001ffa8  mov     eax, [rcx+2Ch]
0x14001ffab  test    bpl, al
0x14001ffae  jz      short loc_14001FFC5
0x14001ffb0  cmp     byte ptr [rcx+29h], 6
0x14001ffb4  jb      short loc_14001FFC5
0x14001ffb6  mov     rcx, [rcx+18h]
0x14001ffba  lea     edx, [rbp+9]
0x14001ffbd  mov     r8, r15
0x14001ffc0  call    WPP_SF_
0x14001ffc5  mov     ebx, 3F00h
0x14001ffca  and     bx, [rsi+0Ch]
0x14001ffce  cmp     cs:DisableTcpFlagChecks, 0
0x14001ffd5  jz      short loc_14001FFDF
0x14001ffd7  mov     eax, 0D7FFh
0x14001ffdc  and     bx, ax
0x14001ffdf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ffe6  mov     sil, 5
0x14001ffe9  cmp     rcx, r14
0x14001ffec  jz      short loc_140020011
0x14001ffee  mov     eax, [rcx+2Ch]
0x14001fff1  test    bpl, al
0x14001fff4  jz      short loc_140020011
0x14001fff6  cmp     [rcx+29h], sil
0x14001fffa  jb      short loc_140020011
0x14001fffc  mov     rcx, [rcx+18h]
0x140020000  mov     edx, 0Bh
0x140020005  movzx   r9d, bx
0x140020009  mov     r8, r15
0x14002000c  call    WPP_SF_d
0x140020011  mov     eax, [rdi+0F0h]
0x140020017  mov     r13d, 200h
0x14002001d  test    r13d, eax
0x140020020  jz      short loc_14002008A
0x140020022  mov     rcx, cs:WPP_GLOBAL_Control
0x140020029  cmp     rcx, r14
0x14002002c  jz      short loc_14002004D
0x14002002e  mov     eax, [rcx+2Ch]
0x140020031  test    bpl, al
0x140020034  jz      short loc_14002004D
0x140020036  cmp     [rcx+29h], sil
0x14002003a  jb      short loc_14002004D
0x14002003c  mov     rcx, [rcx+18h]
0x140020040  mov     edx, 0Ch
0x140020045  mov     r8, r15
0x140020048  call    WPP_SF_
0x14002004d  movzx   ebx, bx
0x140020050  shr     ebx, 9
0x140020053  and     ebx, ebp
0x140020055  mov     rcx, cs:WPP_GLOBAL_Control
0x14002005c  cmp     rcx, r14
0x14002005f  jz      short loc_140020083
0x140020061  mov     eax, [rcx+2Ch]
0x140020064  test    bpl, al
0x140020067  jz      short loc_140020083
0x140020069  cmp     byte ptr [rcx+29h], 6
0x14002006d  jb      short loc_140020083
0x14002006f  mov     rcx, [rcx+18h]
0x140020073  mov     edx, 0Dh
0x140020078  mov     r9d, ebx
0x14002007b  mov     r8, r15
0x14002007e  call    WPP_SF_d
0x140020083  mov     eax, ebx
0x140020085  jmp     loc_14002020D
0x14002008a  test    al, 4
0x14002008c  jz      loc_140020173
0x140020092  mov     rcx, cs:WPP_GLOBAL_Control
0x140020099  cmp     rcx, r14
0x14002009c  jz      short loc_1400200BD
0x14002009e  mov     eax, [rcx+2Ch]
0x1400200a1  test    bpl, al
0x1400200a4  jz      short loc_1400200BD
0x1400200a6  cmp     [rcx+29h], sil
0x1400200aa  jb      short loc_1400200BD
0x1400200ac  mov     rcx, [rcx+18h]
0x1400200b0  mov     edx, 0Eh
0x1400200b5  mov     r8, r15
0x1400200b8  call    WPP_SF_
0x1400200bd  movzx   eax, bx
0x1400200c0  mov     edx, 1200h
0x1400200c5  and     ax, dx
0x1400200c8  mov     ecx, 1000h
0x1400200cd  cmp     ax, cx
0x1400200d0  jnz     short loc_140020109
0x1400200d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400200d9  cmp     rcx, r14
0x1400200dc  jz      short loc_1400200FD
0x1400200de  mov     eax, [rcx+2Ch]
0x1400200e1  test    bpl, al
0x1400200e4  jz      short loc_1400200FD
0x1400200e6  cmp     [rcx+29h], sil
0x1400200ea  jb      short loc_1400200FD
0x1400200ec  mov     rcx, [rcx+18h]
0x1400200f0  mov     edx, 0Fh
0x1400200f5  mov     r8, r15
0x1400200f8  call    WPP_SF_
0x1400200fd  or      [rdi+0F0h], r13d
0x140020104  jmp     loc_1400201DD
0x140020109  movzx   eax, bx
0x14002010c  mov     ecx, 0EDFFh
0x140020111  sub     ax, r13w
0x140020115  test    cx, ax
0x140020118  jnz     short loc_140020123
0x14002011a  cmp     bx, dx
0x14002011d  jnz     loc_1400201DD
0x140020123  mov     rcx, cs:WPP_GLOBAL_Control
0x14002012a  cmp     rcx, r14
0x14002012d  jz      loc_1400201D2
0x140020133  mov     eax, [rcx+2Ch]
0x140020136  test    bpl, al
0x140020139  jz      short loc_140020152
0x14002013b  cmp     [rcx+29h], sil
0x14002013f  jb      short loc_140020152
0x140020141  mov     rcx, [rcx+18h]
0x140020145  mov     edx, 10h
0x14002014a  mov     r8, r15
0x14002014d  call    WPP_SF_
0x140020152  mov     rcx, cs:WPP_GLOBAL_Control
0x140020159  cmp     rcx, r14
0x14002015c  jz      short loc_1400201D2
0x14002015e  mov     eax, [rcx+2Ch]
0x140020161  test    bpl, al
0x140020164  jz      short loc_1400201D2
0x140020166  cmp     byte ptr [rcx+29h], 6
0x14002016a  jb      short loc_1400201D2
0x14002016c  mov     edx, 11h
0x140020171  jmp     short loc_1400201C3
0x140020173  mov     rcx, cs:WPP_GLOBAL_Control
0x14002017a  cmp     rcx, r14
0x14002017d  jz      short loc_14002019E
0x14002017f  mov     eax, [rcx+2Ch]
0x140020182  test    bpl, al
0x140020185  jz      short loc_14002019E
0x140020187  cmp     [rcx+29h], sil
0x14002018b  jb      short loc_14002019E
0x14002018d  mov     rcx, [rcx+18h]
0x140020191  mov     edx, 12h
0x140020196  mov     r8, r15
0x140020199  call    WPP_SF_
0x14002019e  cmp     r13w, bx
0x1400201a2  jz      short loc_1400201D6
0x1400201a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400201ab  cmp     rcx, r14
0x1400201ae  jz      short loc_1400201D2
0x1400201b0  mov     edx, [rcx+2Ch]
0x1400201b3  test    bpl, dl
0x1400201b6  jz      short loc_1400201D2
0x1400201b8  cmp     byte ptr [rcx+29h], 6
0x1400201bc  jb      short loc_1400201D2
0x1400201be  mov     edx, 13h
0x1400201c3  mov     rcx, [rcx+18h]
0x1400201c7  mov     r9d, ebp
0x1400201ca  mov     r8, r15
0x1400201cd  call    WPP_SF_d
0x1400201d2  mov     eax, ebp
0x1400201d4  jmp     short loc_14002020D
0x1400201d6  or      dword ptr [rdi+0F0h], 2
0x1400201dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400201e4  cmp     rcx, r14
0x1400201e7  jz      short loc_14002020B
0x1400201e9  mov     eax, [rcx+2Ch]
0x1400201ec  test    bpl, al
0x1400201ef  jz      short loc_14002020B
0x1400201f1  cmp     byte ptr [rcx+29h], 6
0x1400201f5  jb      short loc_14002020B
0x1400201f7  mov     rcx, [rcx+18h]
0x1400201fb  mov     edx, 14h
0x140020200  xor     r9d, r9d
0x140020203  mov     r8, r15
0x140020206  call    WPP_SF_d
0x14002020b  xor     eax, eax
0x14002020d  add     rsp, 20h
0x140020211  pop     r15
0x140020213  pop     r14
0x140020215  pop     r13
0x140020217  pop     rdi
0x140020218  pop     rsi
0x140020219  pop     rbp
0x14002021a  pop     rbx
0x14002021b  retn
```
