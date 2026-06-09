# PreparePacketForWire

- ea: `0x140013c90`
- end: `0x14001415c`
- name: `PreparePacketForWire`
- size: `1228`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140012854`
- `0x140012aa8`
- `0x140012dc8`
- `0x1400130a4`
- `0x140013344`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x1400138d0`
- `0x140013c90`

## pseudocode

```c
__int64 __fastcall PreparePacketForWire(__int64 a1)
{
  unsigned int inserted; // edi
  __int64 v3; // rax
  __int64 v4; // r8
  _QWORD *v5; // r9
  __int64 v6; // rdx

  inserted = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xFu, (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
  }
  v3 = *(_QWORD *)(a1 + 112);
  switch ( *(_BYTE *)(v3 + 15) )
  {
    case 0:
      goto LABEL_66;
    case 7:
      inserted = PacketInsertTag(a1, 257, *(unsigned __int16 *)(a1 + 16), *(_QWORD *)(a1 + 24), a1 + 24);
      if ( inserted )
        goto LABEL_76;
      if ( *(_WORD *)(a1 + 48) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x11u,
            (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
        }
        inserted = PacketInsertTag(a1, 259, *(unsigned __int16 *)(a1 + 48), *(_QWORD *)(a1 + 56), a1 + 56);
        if ( inserted )
          goto LABEL_76;
      }
      if ( *(_WORD *)(a1 + 80) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x12u,
            (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
        }
        inserted = PacketInsertTag(a1, 272, *(unsigned __int16 *)(a1 + 80), *(_QWORD *)(a1 + 88), a1 + 88);
        if ( inserted )
          goto LABEL_76;
      }
      inserted = PacketInsertTag(a1, 258, *(unsigned __int16 *)(a1 + 32), *(_QWORD *)(a1 + 40), a1 + 40);
      if ( inserted )
        goto LABEL_76;
LABEL_64:
      v4 = *(unsigned __int16 *)(a1 + 64);
      v5 = (_QWORD *)(a1 + 72);
      v6 = 260;
      goto LABEL_65;
    case 9:
      inserted = PacketInsertTag(a1, 257, *(unsigned __int16 *)(a1 + 16), *(_QWORD *)(a1 + 24), a1 + 24);
      if ( inserted )
        goto LABEL_76;
      if ( !*(_WORD *)(a1 + 48) )
        goto LABEL_66;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x10u,
          (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
      }
      v4 = *(unsigned __int16 *)(a1 + 48);
      v5 = (_QWORD *)(a1 + 56);
      v6 = 259;
      goto LABEL_65;
    case 0x19:
      inserted = PacketInsertTag(a1, 257, *(unsigned __int16 *)(a1 + 16), *(_QWORD *)(a1 + 24), a1 + 24);
      if ( inserted )
        goto LABEL_76;
      if ( *(_WORD *)(a1 + 48) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x13u,
            (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
        }
        inserted = PacketInsertTag(a1, 259, *(unsigned __int16 *)(a1 + 48), *(_QWORD *)(a1 + 56), a1 + 56);
        if ( inserted )
          goto LABEL_76;
      }
      if ( *(_WORD *)(a1 + 80) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x14u,
            (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
        }
        inserted = PacketInsertTag(a1, 272, *(unsigned __int16 *)(a1 + 80), *(_QWORD *)(a1 + 88), a1 + 88);
        if ( inserted )
          goto LABEL_76;
      }
      if ( !*(_WORD *)(a1 + 64) )
        goto LABEL_66;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x15u,
          (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
      }
      goto LABEL_64;
    case 0x65:
      inserted = PacketInsertTag(a1, 257, *(unsigned __int16 *)(a1 + 16), *(_QWORD *)(a1 + 24), a1 + 24);
      if ( inserted )
        goto LABEL_76;
      if ( *(_WORD *)(a1 + 48) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x16u,
            (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
        }
        inserted = PacketInsertTag(a1, 259, *(unsigned __int16 *)(a1 + 48), *(_QWORD *)(a1 + 56), a1 + 56);
        if ( inserted )
          goto LABEL_76;
      }
      if ( !*(_WORD *)(a1 + 80) )
        goto LABEL_66;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x17u,
          (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
      }
      v4 = *(unsigned __int16 *)(a1 + 80);
      v5 = (_QWORD *)(a1 + 88);
      v6 = 272;
LABEL_65:
      inserted = PacketInsertTag(a1, v6, v4, *v5, v5);
      if ( inserted )
        goto LABEL_76;
      goto LABEL_66;
  }
  if ( *(unsigned __int8 *)(v3 + 15) != 167 )
  {
    inserted = -1073676273;
    goto LABEL_76;
  }
LABEL_66:
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 112) + 15LL) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x18u,
        (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
    }
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 8LL) + 24LL) = (unsigned __int16)__ROR2__(
                                                                                       *(_WORD *)(*(_QWORD *)(a1 + 112)
                                                                                                + 18LL),
                                                                                       8)
                                                                 + 20;
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return inserted;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x19u,
        (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
  }
LABEL_76:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x1Au,
      (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids,
      inserted);
  }
  return inserted;
}

```

## disassembly

```asm
0x140013c90  push    rbx
0x140013c92  push    rbp
0x140013c93  push    rsi
0x140013c94  push    rdi
0x140013c95  push    r14
0x140013c97  push    r15
0x140013c99  sub     rsp, 38h
0x140013c9d  xor     esi, esi
0x140013c9f  mov     rbx, rcx
0x140013ca2  mov     edi, esi
0x140013ca4  mov     rcx, cs:WPP_GLOBAL_Control
0x140013cab  lea     r14, WPP_GLOBAL_Control
0x140013cb2  lea     r15, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x140013cb9  mov     bpl, 20h ; ' '
0x140013cbc  cmp     rcx, r14
0x140013cbf  jz      short loc_140013CDE
0x140013cc1  mov     eax, [rcx+2Ch]
0x140013cc4  test    bpl, al
0x140013cc7  jz      short loc_140013CDE
0x140013cc9  cmp     byte ptr [rcx+29h], 4
0x140013ccd  jb      short loc_140013CDE
0x140013ccf  mov     rcx, [rcx+18h]
0x140013cd3  lea     edx, [rsi+0Fh]
0x140013cd6  mov     r8, r15
0x140013cd9  call    WPP_SF_
0x140013cde  mov     rax, [rbx+70h]
0x140013ce2  movzx   ecx, byte ptr [rax+0Fh]
0x140013ce6  test    ecx, ecx
0x140013ce8  jz      loc_14001409C
0x140013cee  sub     ecx, 7
0x140013cf1  jz      loc_140013F74
0x140013cf7  sub     ecx, 2
0x140013cfa  jz      loc_140013F06
0x140013d00  sub     ecx, 10h
0x140013d03  jz      loc_140013DE8
0x140013d09  sub     ecx, 4Ch ; 'L'
0x140013d0c  jz      short loc_140013D21
0x140013d0e  cmp     ecx, 42h ; 'B'
0x140013d11  jz      loc_14001409C
0x140013d17  mov     edi, 0C001000Fh
0x140013d1c  jmp     loc_14001411E
0x140013d21  movzx   r8d, word ptr [rbx+10h]
0x140013d26  lea     r9, [rbx+18h]
0x140013d2a  mov     [rsp+68h+var_48], r9
0x140013d2f  mov     edx, 101h
0x140013d34  mov     r9, [r9]
0x140013d37  mov     rcx, rbx
0x140013d3a  call    PacketInsertTag
0x140013d3f  mov     edi, eax
0x140013d41  test    eax, eax
0x140013d43  jnz     loc_14001411E
0x140013d49  cmp     [rbx+30h], si
0x140013d4d  jbe     short loc_140013DA0
0x140013d4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d56  cmp     rcx, r14
0x140013d59  jz      short loc_140013D78
0x140013d5b  mov     eax, [rcx+2Ch]
0x140013d5e  test    bpl, al
0x140013d61  jz      short loc_140013D78
0x140013d63  cmp     byte ptr [rcx+29h], 3
0x140013d67  jb      short loc_140013D78
0x140013d69  mov     rcx, [rcx+18h]
0x140013d6d  lea     edx, [rdi+16h]
0x140013d70  mov     r8, r15
0x140013d73  call    WPP_SF_
0x140013d78  movzx   r8d, word ptr [rbx+30h]
0x140013d7d  lea     r9, [rbx+38h]
0x140013d81  mov     [rsp+68h+var_48], r9
0x140013d86  mov     edx, 103h
0x140013d8b  mov     r9, [r9]
0x140013d8e  mov     rcx, rbx
0x140013d91  call    PacketInsertTag
0x140013d96  mov     edi, eax
0x140013d98  test    eax, eax
0x140013d9a  jnz     loc_14001411E
0x140013da0  cmp     [rbx+50h], si
0x140013da4  jbe     loc_14001409C
0x140013daa  mov     rcx, cs:WPP_GLOBAL_Control
0x140013db1  cmp     rcx, r14
0x140013db4  jz      short loc_140013DD5
0x140013db6  mov     eax, [rcx+2Ch]
0x140013db9  test    bpl, al
0x140013dbc  jz      short loc_140013DD5
0x140013dbe  cmp     byte ptr [rcx+29h], 3
0x140013dc2  jb      short loc_140013DD5
0x140013dc4  mov     rcx, [rcx+18h]
0x140013dc8  mov     edx, 17h
0x140013dcd  mov     r8, r15
0x140013dd0  call    WPP_SF_
0x140013dd5  movzx   r8d, word ptr [rbx+50h]
0x140013dda  lea     r9, [rbx+58h]
0x140013dde  mov     edx, 110h
0x140013de3  jmp     loc_140014082
0x140013de8  movzx   r8d, word ptr [rbx+10h]
0x140013ded  lea     r9, [rbx+18h]
0x140013df1  mov     [rsp+68h+var_48], r9
0x140013df6  mov     edx, 101h
0x140013dfb  mov     r9, [r9]
0x140013dfe  mov     rcx, rbx
0x140013e01  call    PacketInsertTag
0x140013e06  mov     edi, eax
0x140013e08  test    eax, eax
0x140013e0a  jnz     loc_14001411E
0x140013e10  cmp     [rbx+30h], si
0x140013e14  jbe     short loc_140013E67
0x140013e16  mov     rcx, cs:WPP_GLOBAL_Control
0x140013e1d  cmp     rcx, r14
0x140013e20  jz      short loc_140013E3F
0x140013e22  mov     eax, [rcx+2Ch]
0x140013e25  test    bpl, al
0x140013e28  jz      short loc_140013E3F
0x140013e2a  cmp     byte ptr [rcx+29h], 3
0x140013e2e  jb      short loc_140013E3F
0x140013e30  mov     rcx, [rcx+18h]
0x140013e34  lea     edx, [rdi+13h]
0x140013e37  mov     r8, r15
0x140013e3a  call    WPP_SF_
0x140013e3f  movzx   r8d, word ptr [rbx+30h]
0x140013e44  lea     r9, [rbx+38h]
0x140013e48  mov     [rsp+68h+var_48], r9
0x140013e4d  mov     edx, 103h
0x140013e52  mov     r9, [r9]
0x140013e55  mov     rcx, rbx
0x140013e58  call    PacketInsertTag
0x140013e5d  mov     edi, eax
0x140013e5f  test    eax, eax
0x140013e61  jnz     loc_14001411E
0x140013e67  cmp     [rbx+50h], si
0x140013e6b  jbe     short loc_140013EC0
0x140013e6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013e74  cmp     rcx, r14
0x140013e77  jz      short loc_140013E98
0x140013e79  mov     eax, [rcx+2Ch]
0x140013e7c  test    bpl, al
0x140013e7f  jz      short loc_140013E98
0x140013e81  cmp     byte ptr [rcx+29h], 3
0x140013e85  jb      short loc_140013E98
0x140013e87  mov     rcx, [rcx+18h]
0x140013e8b  mov     edx, 14h
0x140013e90  mov     r8, r15
0x140013e93  call    WPP_SF_
0x140013e98  movzx   r8d, word ptr [rbx+50h]
0x140013e9d  lea     r9, [rbx+58h]
0x140013ea1  mov     [rsp+68h+var_48], r9
0x140013ea6  mov     edx, 110h
0x140013eab  mov     r9, [r9]
0x140013eae  mov     rcx, rbx
0x140013eb1  call    PacketInsertTag
0x140013eb6  mov     edi, eax
0x140013eb8  test    eax, eax
0x140013eba  jnz     loc_14001411E
0x140013ec0  cmp     [rbx+40h], si
0x140013ec4  jbe     loc_14001409C
0x140013eca  mov     rcx, cs:WPP_GLOBAL_Control
0x140013ed1  cmp     rcx, r14
0x140013ed4  jz      loc_140014074
0x140013eda  mov     eax, [rcx+2Ch]
0x140013edd  test    bpl, al
0x140013ee0  jz      loc_140014074
0x140013ee6  cmp     byte ptr [rcx+29h], 3
0x140013eea  jb      loc_140014074
0x140013ef0  mov     rcx, [rcx+18h]
0x140013ef4  mov     edx, 15h
0x140013ef9  mov     r8, r15
0x140013efc  call    WPP_SF_
0x140013f01  jmp     loc_140014074
0x140013f06  movzx   r8d, word ptr [rbx+10h]
0x140013f0b  lea     r9, [rbx+18h]
0x140013f0f  mov     [rsp+68h+var_48], r9
0x140013f14  mov     edx, 101h
0x140013f19  mov     r9, [r9]
0x140013f1c  mov     rcx, rbx
0x140013f1f  call    PacketInsertTag
0x140013f24  mov     edi, eax
0x140013f26  test    eax, eax
0x140013f28  jnz     loc_14001411E
0x140013f2e  cmp     [rbx+30h], si
0x140013f32  jbe     loc_14001409C
0x140013f38  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f3f  cmp     rcx, r14
0x140013f42  jz      short loc_140013F61
0x140013f44  mov     eax, [rcx+2Ch]
0x140013f47  test    bpl, al
0x140013f4a  jz      short loc_140013F61
0x140013f4c  cmp     byte ptr [rcx+29h], 3
0x140013f50  jb      short loc_140013F61
0x140013f52  mov     rcx, [rcx+18h]
0x140013f56  lea     edx, [rdi+10h]
0x140013f59  mov     r8, r15
0x140013f5c  call    WPP_SF_
0x140013f61  movzx   r8d, word ptr [rbx+30h]
0x140013f66  lea     r9, [rbx+38h]
0x140013f6a  mov     edx, 103h
0x140013f6f  jmp     loc_140014082
0x140013f74  movzx   r8d, word ptr [rbx+10h]
0x140013f79  lea     r9, [rbx+18h]
0x140013f7d  mov     [rsp+68h+var_48], r9
0x140013f82  mov     edx, 101h
0x140013f87  mov     r9, [r9]
0x140013f8a  mov     rcx, rbx
0x140013f8d  call    PacketInsertTag
0x140013f92  mov     edi, eax
0x140013f94  test    eax, eax
0x140013f96  jnz     loc_14001411E
0x140013f9c  cmp     [rbx+30h], si
0x140013fa0  jbe     short loc_140013FF3
0x140013fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x140013fa9  cmp     rcx, r14
0x140013fac  jz      short loc_140013FCB
0x140013fae  mov     eax, [rcx+2Ch]
0x140013fb1  test    bpl, al
0x140013fb4  jz      short loc_140013FCB
0x140013fb6  cmp     byte ptr [rcx+29h], 3
0x140013fba  jb      short loc_140013FCB
0x140013fbc  mov     rcx, [rcx+18h]
0x140013fc0  lea     edx, [rdi+11h]
0x140013fc3  mov     r8, r15
0x140013fc6  call    WPP_SF_
0x140013fcb  movzx   r8d, word ptr [rbx+30h]
0x140013fd0  lea     r9, [rbx+38h]
0x140013fd4  mov     [rsp+68h+var_48], r9
0x140013fd9  mov     edx, 103h
0x140013fde  mov     r9, [r9]
0x140013fe1  mov     rcx, rbx
0x140013fe4  call    PacketInsertTag
0x140013fe9  mov     edi, eax
0x140013feb  test    eax, eax
0x140013fed  jnz     loc_14001411E
0x140013ff3  cmp     [rbx+50h], si
0x140013ff7  jbe     short loc_14001404C
0x140013ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x140014000  cmp     rcx, r14
0x140014003  jz      short loc_140014024
0x140014005  mov     eax, [rcx+2Ch]
0x140014008  test    bpl, al
0x14001400b  jz      short loc_140014024
0x14001400d  cmp     byte ptr [rcx+29h], 3
0x140014011  jb      short loc_140014024
0x140014013  mov     rcx, [rcx+18h]
0x140014017  mov     edx, 12h
0x14001401c  mov     r8, r15
0x14001401f  call    WPP_SF_
0x140014024  movzx   r8d, word ptr [rbx+50h]
0x140014029  lea     r9, [rbx+58h]
0x14001402d  mov     [rsp+68h+var_48], r9
0x140014032  mov     edx, 110h
0x140014037  mov     r9, [r9]
0x14001403a  mov     rcx, rbx
0x14001403d  call    PacketInsertTag
0x140014042  mov     edi, eax
0x140014044  test    eax, eax
0x140014046  jnz     loc_14001411E
0x14001404c  movzx   r8d, word ptr [rbx+20h]
0x140014051  lea     r9, [rbx+28h]
0x140014055  mov     [rsp+68h+var_48], r9
0x14001405a  mov     edx, 102h
0x14001405f  mov     r9, [r9]
0x140014062  mov     rcx, rbx
0x140014065  call    PacketInsertTag
0x14001406a  mov     edi, eax
0x14001406c  test    eax, eax
0x14001406e  jnz     loc_14001411E
0x140014074  movzx   r8d, word ptr [rbx+40h]
0x140014079  lea     r9, [rbx+48h]
0x14001407d  mov     edx, 104h
0x140014082  mov     [rsp+68h+var_48], r9
0x140014087  mov     rcx, rbx
0x14001408a  mov     r9, [r9]
0x14001408d  call    PacketInsertTag
0x140014092  mov     edi, eax
0x140014094  test    eax, eax
0x140014096  jnz     loc_14001411E
0x14001409c  mov     rax, [rbx+70h]
0x1400140a0  cmp     [rax+0Fh], sil
0x1400140a4  jz      short loc_1400140F3
0x1400140a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400140ad  cmp     rcx, r14
0x1400140b0  jz      short loc_1400140D1
0x1400140b2  mov     eax, [rcx+2Ch]
0x1400140b5  test    bpl, al
0x1400140b8  jz      short loc_1400140D1
0x1400140ba  cmp     byte ptr [rcx+29h], 4
0x1400140be  jb      short loc_1400140D1
0x1400140c0  mov     rcx, [rcx+18h]
0x1400140c4  mov     edx, 18h
0x1400140c9  mov     r8, r15
0x1400140cc  call    WPP_SF_
0x1400140d1  mov     rax, [rbx+70h]
0x1400140d5  movzx   ecx, word ptr [rax+12h]
0x1400140d9  mov     rax, [rbx+88h]
0x1400140e0  ror     cx, 8
0x1400140e4  movzx   edx, cx
0x1400140e7  add     edx, 14h
0x1400140ea  mov     rcx, [rax+8]
0x1400140ee  mov     [rcx+18h], edx
0x1400140f1  jmp     short loc_14001411E
0x1400140f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400140fa  cmp     rcx, r14
0x1400140fd  jz      short loc_14001414C
0x1400140ff  mov     eax, [rcx+2Ch]
  ... truncated ...
```
