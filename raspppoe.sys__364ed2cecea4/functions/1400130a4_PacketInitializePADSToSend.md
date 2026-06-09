# PacketInitializePADSToSend

- ea: `0x1400130a4`
- end: `0x14001333e`
- name: `PacketInitializePADSToSend`
- size: `666`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140011560`
- `0x140016534`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x140006b80`
- `0x140011cdc`
- `0x1400130a4`
- `0x140013c90`

## pseudocode

```c
__int64 __fastcall PacketInitializePADSToSend(__int64 a1, __int64 *a2, __int16 a3)
{
  __int64 PPPoEPacket; // rax
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // edi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x44u,
      (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
  }
  if ( (unsigned __int16)(*(_WORD *)(a1 + 48)
                        + *(_WORD *)(a1 + 80)
                        + *(_WORD *)(a1 + 16)
                        + (*(_WORD *)(a1 + 48) != 0 ? 8 : 4)
                        + (*(_WORD *)(a1 + 80) != 0 ? 4 : 0)) <= 0x5D6u )
  {
    PPPoEPacket = AllocatePPPoEPacket();
    v8 = PPPoEPacket;
    if ( PPPoEPacket )
    {
      v9 = *(_QWORD *)(PPPoEPacket + 112);
      *(_DWORD *)(PPPoEPacket + 144) = 1;
      v10 = *(_QWORD *)(a1 + 112);
      *(_DWORD *)(v9 + 6) = *(_DWORD *)v10;
      *(_WORD *)(v9 + 10) = *(_WORD *)(v10 + 4);
      v11 = *(_QWORD *)(a1 + 112);
      v12 = *(_QWORD *)(PPPoEPacket + 112);
      *(_DWORD *)v12 = *(_DWORD *)(v11 + 6);
      *(_WORD *)(v12 + 4) = *(_WORD *)(v11 + 10);
      *(_WORD *)(*(_QWORD *)(PPPoEPacket + 112) + 12LL) = 25480;
      *(_BYTE *)(*(_QWORD *)(PPPoEPacket + 112) + 14LL) |= 0x10u;
      *(_BYTE *)(*(_QWORD *)(PPPoEPacket + 112) + 14LL) |= 1u;
      *(_BYTE *)(*(_QWORD *)(PPPoEPacket + 112) + 15LL) = 101;
      *(_WORD *)(*(_QWORD *)(PPPoEPacket + 112) + 16LL) = __ROR2__(a3, 8);
      *(_WORD *)(*(_QWORD *)(PPPoEPacket + 112) + 18LL) = 0;
      *(_WORD *)(PPPoEPacket + 16) = *(_WORD *)(a1 + 16);
      *(_QWORD *)(PPPoEPacket + 24) = *(_QWORD *)(a1 + 24);
      *(_WORD *)(PPPoEPacket + 48) = *(_WORD *)(a1 + 48);
      *(_QWORD *)(PPPoEPacket + 56) = *(_QWORD *)(a1 + 56);
      *(_WORD *)(PPPoEPacket + 80) = *(_WORD *)(a1 + 80);
      *(_QWORD *)(PPPoEPacket + 88) = *(_QWORD *)(a1 + 88);
      v13 = PreparePacketForWire(PPPoEPacket);
      v14 = v13;
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x49u,
            (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids,
            v13);
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(__int64))(v8 + 8))(v8);
        v8 = 0;
      }
      *a2 = v8;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_d(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x4Au,
          (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids,
          v14);
      }
      return v14;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x47u,
            (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_d(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x48u,
            (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids,
            -1073741670);
        }
      }
      return 3221225626LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x45u,
          (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_d(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x46u,
          (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids,
          -1073676273);
      }
    }
    return 3221291023LL;
  }
}

```

## disassembly

```asm
0x1400130a4  push    rbx
0x1400130a6  push    rbp
0x1400130a7  push    rsi
0x1400130a8  push    rdi
0x1400130a9  push    r12
0x1400130ab  push    r15
0x1400130ad  sub     rsp, 28h
0x1400130b1  movzx   ebp, r8w
0x1400130b5  mov     rsi, rdx
0x1400130b8  mov     rdi, rcx
0x1400130bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400130c2  lea     r15, WPP_GLOBAL_Control
0x1400130c9  lea     r12, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x1400130d0  cmp     rcx, r15
0x1400130d3  jz      short loc_1400130F3
0x1400130d5  mov     eax, [rcx+2Ch]
0x1400130d8  test    al, 20h
0x1400130da  jz      short loc_1400130F3
0x1400130dc  cmp     byte ptr [rcx+29h], 3
0x1400130e0  jb      short loc_1400130F3
0x1400130e2  mov     rcx, [rcx+18h]
0x1400130e6  mov     edx, 44h ; 'D'
0x1400130eb  mov     r8, r12
0x1400130ee  call    WPP_SF_
0x1400130f3  movzx   edx, word ptr [rdi+50h]
0x1400130f7  movzx   r9d, word ptr [rdi+30h]
0x1400130fc  movzx   eax, dx
0x1400130ff  neg     ax
0x140013102  movzx   eax, r9w
0x140013106  sbb     r8w, r8w
0x14001310a  and     r8w, 4
0x14001310f  neg     ax
0x140013112  mov     eax, 5D6h
0x140013117  sbb     cx, cx
0x14001311a  and     cx, 4
0x14001311e  add     cx, 4
0x140013122  add     r8w, cx
0x140013126  add     r8w, [rdi+10h]
0x14001312b  add     r8w, dx
0x14001312f  add     r8w, r9w
0x140013133  cmp     r8w, ax
0x140013137  jbe     short loc_14001319D
0x140013139  mov     rcx, cs:WPP_GLOBAL_Control
0x140013140  cmp     rcx, r15
0x140013143  jz      short loc_140013193
0x140013145  mov     eax, [rcx+2Ch]
0x140013148  test    al, 20h
0x14001314a  jz      short loc_140013163
0x14001314c  cmp     byte ptr [rcx+29h], 1
0x140013150  jb      short loc_140013163
0x140013152  mov     rcx, [rcx+18h]
0x140013156  mov     edx, 45h ; 'E'
0x14001315b  mov     r8, r12
0x14001315e  call    WPP_SF_
0x140013163  mov     rcx, cs:WPP_GLOBAL_Control
0x14001316a  cmp     rcx, r15
0x14001316d  jz      short loc_140013193
0x14001316f  mov     eax, [rcx+2Ch]
0x140013172  test    al, 20h
0x140013174  jz      short loc_140013193
0x140013176  cmp     byte ptr [rcx+29h], 3
0x14001317a  jb      short loc_140013193
0x14001317c  mov     rcx, [rcx+18h]
0x140013180  mov     edx, 46h ; 'F'
0x140013185  mov     r9d, 0C001000Fh
0x14001318b  mov     r8, r12
0x14001318e  call    WPP_SF_d
0x140013193  mov     eax, 0C001000Fh
0x140013198  jmp     loc_140013330
0x14001319d  call    AllocatePPPoEPacket
0x1400131a2  mov     rbx, rax
0x1400131a5  test    rax, rax
0x1400131a8  jnz     short loc_14001320C
0x1400131aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400131b1  cmp     rcx, r15
0x1400131b4  jz      short loc_140013202
0x1400131b6  mov     eax, [rcx+2Ch]
0x1400131b9  test    al, 20h
0x1400131bb  jz      short loc_1400131D2
0x1400131bd  cmp     byte ptr [rcx+29h], 1
0x1400131c1  jb      short loc_1400131D2
0x1400131c3  mov     rcx, [rcx+18h]
0x1400131c7  lea     edx, [rbx+47h]
0x1400131ca  mov     r8, r12
0x1400131cd  call    WPP_SF_
0x1400131d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400131d9  cmp     rcx, r15
0x1400131dc  jz      short loc_140013202
0x1400131de  mov     eax, [rcx+2Ch]
0x1400131e1  test    al, 20h
0x1400131e3  jz      short loc_140013202
0x1400131e5  cmp     byte ptr [rcx+29h], 3
0x1400131e9  jb      short loc_140013202
0x1400131eb  mov     rcx, [rcx+18h]
0x1400131ef  mov     edx, 48h ; 'H'
0x1400131f4  mov     r9d, 0C000009Ah
0x1400131fa  mov     r8, r12
0x1400131fd  call    WPP_SF_d
0x140013202  mov     eax, 0C000009Ah
0x140013207  jmp     loc_140013330
0x14001320c  mov     rdx, [rax+70h]
0x140013210  mov     dword ptr [rax+90h], 1
0x14001321a  mov     rcx, [rdi+70h]
0x14001321e  ror     bp, 8
0x140013222  mov     eax, [rcx]
0x140013224  mov     [rdx+6], eax
0x140013227  movzx   eax, word ptr [rcx+4]
0x14001322b  mov     [rdx+0Ah], ax
0x14001322f  mov     rcx, [rdi+70h]
0x140013233  mov     rdx, [rbx+70h]
0x140013237  mov     eax, [rcx+6]
0x14001323a  mov     [rdx], eax
0x14001323c  movzx   eax, word ptr [rcx+0Ah]
0x140013240  mov     [rdx+4], ax
0x140013244  mov     rax, [rbx+70h]
0x140013248  mov     word ptr [rax+0Ch], 6388h
0x14001324e  mov     rax, [rbx+70h]
0x140013252  or      byte ptr [rax+0Eh], 10h
0x140013256  mov     rax, [rbx+70h]
0x14001325a  or      byte ptr [rax+0Eh], 1
0x14001325e  mov     rax, [rbx+70h]
0x140013262  mov     byte ptr [rax+0Fh], 65h ; 'e'
0x140013266  mov     rax, [rbx+70h]
0x14001326a  mov     [rax+10h], bp
0x14001326e  xor     eax, eax
0x140013270  mov     rcx, [rbx+70h]
0x140013274  mov     [rcx+12h], ax
0x140013278  mov     rcx, rbx
0x14001327b  movzx   eax, word ptr [rdi+10h]
0x14001327f  mov     [rbx+10h], ax
0x140013283  mov     rax, [rdi+18h]
0x140013287  mov     [rbx+18h], rax
0x14001328b  movzx   eax, word ptr [rdi+30h]
0x14001328f  mov     [rbx+30h], ax
0x140013293  mov     rax, [rdi+38h]
0x140013297  mov     [rbx+38h], rax
0x14001329b  movzx   eax, word ptr [rdi+50h]
0x14001329f  mov     [rbx+50h], ax
0x1400132a3  mov     rax, [rdi+58h]
0x1400132a7  mov     [rbx+58h], rax
0x1400132ab  call    PreparePacketForWire
0x1400132b0  mov     edi, eax
0x1400132b2  test    eax, eax
0x1400132b4  jz      short loc_1400132FE
0x1400132b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400132bd  cmp     rcx, r15
0x1400132c0  jz      short loc_1400132E4
0x1400132c2  mov     edx, [rcx+2Ch]
0x1400132c5  test    dl, 20h
0x1400132c8  jz      short loc_1400132E4
0x1400132ca  cmp     byte ptr [rcx+29h], 1
0x1400132ce  jb      short loc_1400132E4
0x1400132d0  mov     rcx, [rcx+18h]
0x1400132d4  mov     edx, 49h ; 'I'
0x1400132d9  mov     r9d, eax
0x1400132dc  mov     r8, r12
0x1400132df  call    WPP_SF_d
0x1400132e4  or      eax, 0FFFFFFFFh
0x1400132e7  lock xadd [rbx], eax
0x1400132eb  cmp     eax, 1
0x1400132ee  jnz     short loc_1400132FC
0x1400132f0  mov     rax, [rbx+8]
0x1400132f4  mov     rcx, rbx
0x1400132f7  call    _guard_dispatch_icall
0x1400132fc  xor     ebx, ebx
0x1400132fe  mov     [rsi], rbx
0x140013301  mov     rcx, cs:WPP_GLOBAL_Control
0x140013308  cmp     rcx, r15
0x14001330b  jz      short loc_14001332E
0x14001330d  mov     eax, [rcx+2Ch]
0x140013310  test    al, 20h
0x140013312  jz      short loc_14001332E
0x140013314  cmp     byte ptr [rcx+29h], 3
0x140013318  jb      short loc_14001332E
0x14001331a  mov     rcx, [rcx+18h]
0x14001331e  mov     edx, 4Ah ; 'J'
0x140013323  mov     r9d, edi
0x140013326  mov     r8, r12
0x140013329  call    WPP_SF_d
0x14001332e  mov     eax, edi
0x140013330  add     rsp, 28h
0x140013334  pop     r15
0x140013336  pop     r12
0x140013338  pop     rdi
0x140013339  pop     rsi
0x14001333a  pop     rbp
0x14001333b  pop     rbx
0x14001333c  retn
```
