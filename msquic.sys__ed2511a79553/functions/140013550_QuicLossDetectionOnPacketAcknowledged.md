# QuicLossDetectionOnPacketAcknowledged

- ea: `0x140013550`
- end: `0x140013a3a`
- name: `QuicLossDetectionOnPacketAcknowledged`
- size: `1258`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x140008f50`
- `0x140013b30`

## callees

- `0x14000d230`
- `0x140013550`
- `0x140014630`
- `0x14001b700`
- `0x14001be88`
- `0x14001cc0c`
- `0x14001df0c`
- `0x14001ec28`
- `0x14001eee0`
- `0x140021898`
- `0x1400255dc`
- `0x140029ef0`
- `0x14002e9ac`
- `0x140030ad0`
- `0x14003c8e0`
- `0x14003ec10`
- `0x1400456a4`
- `0x14004572c`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140013617`
- `ntoskrnl!_snprintf_s` at `0x140013698`
- `ntoskrnl!_snprintf_s` at `0x140013990`
- `ntoskrnl!_snprintf_s` at `0x140013617`
- `ntoskrnl!_snprintf_s` at `0x140013698`
- `ntoskrnl!_snprintf_s` at `0x140013990`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138c0`

## string_xrefs

- `0x140013974`: `Path[%hhu] Minimum MTU validated`

## pseudocode

```c
void __fastcall QuicLossDetectionOnPacketAcknowledged(_QWORD *a1, int a2, __int64 a3, char a4, __int64 a5, __int64 a6)
{
  char v6; // r11
  __int64 v7; // rsi
  __int64 v9; // r15
  unsigned __int8 v10; // r8
  unsigned __int8 v11; // r10
  _QWORD *v13; // r13
  unsigned __int8 *v14; // r14
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rbx
  unsigned __int8 v18; // cl
  __int64 v19; // rcx
  unsigned __int8 v20; // bp
  __int64 v21; // r9
  unsigned __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r15
  __int64 v25; // r8
  unsigned __int64 v26; // r10
  __int64 v27; // rcx
  unsigned int v28; // r11d
  unsigned __int64 *v29; // rcx
  unsigned __int64 v30; // r9
  __int64 v31; // rdx
  __int64 SourceCidFromSeq; // rax
  void *DestCidFromSeq; // rax
  unsigned __int16 v34; // ax
  unsigned __int8 v35; // cl
  bool v36; // bl
  unsigned __int16 v37; // bp
  unsigned __int16 v38; // ax
  __int64 v39; // rcx
  __int64 v40; // rax
  char v41[8]; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v42; // [rsp+38h] [rbp-E0h]
  __int64 v43; // [rsp+40h] [rbp-D8h]
  _QWORD *v44; // [rsp+48h] [rbp-D0h]
  char DstBuf[128]; // [rsp+50h] [rbp-C8h] BYREF

  v6 = *(_BYTE *)(a3 + 42);
  v7 = (__int64)(a1 - 329);
  v9 = a2;
  v10 = *((_BYTE *)a1 - 2357);
  v11 = 0;
  v44 = a1;
  v13 = a1;
  if ( v10 )
  {
    while ( 1 )
    {
      v14 = (unsigned __int8 *)(v7 + 240LL * v11 + 320);
      if ( *v14 == v6 )
        break;
      if ( ++v11 >= v10 )
        goto LABEL_4;
    }
  }
  else
  {
LABEL_4:
    v14 = 0;
  }
  if ( (unsigned __int8)QuicConnIsClient(a1 - 329) && (*(_BYTE *)(v7 + 250) & 2) == 0 && (*(_BYTE *)(a3 + 88) & 3) == 3 )
  {
    if ( byte_14005C48B < 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Handshake confirmed (ack)");
      McTemplateU0ps_EtwWriteTransfer(v16, QuicConnLogInfo, v7, DstBuf);
    }
    LOBYTE(v15) = 1;
    QuicCryptoHandshakeConfirmed(v7 + 2784, v15);
  }
  v17 = *(_QWORD *)(v7 + 2776);
  if ( (_DWORD)v9 == 2 )
  {
    v18 = *(_BYTE *)(v17 + 424);
    if ( (v18 & 2) != 0
      && ((v18 ^ (*(_BYTE *)(a3 + 88) >> 4)) & 1) == 0
      && *(_QWORD *)(a3 + 16) >= *(_QWORD *)(v17 + 400) )
    {
      if ( (byte_14005C48C & 1) != 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Key change confirmed by peer");
        McTemplateU0ps_EtwWriteTransfer(v19, QuicConnLogVerbose, v7, DstBuf);
      }
      *(_BYTE *)(v17 + 424) &= ~2u;
    }
  }
  v20 = 0;
  if ( *(_BYTE *)(a3 + 90) )
  {
    v21 = v9;
    v42 = v9;
    while ( 2 )
    {
      v22 = v20;
      v23 = a3 + 24LL * v20;
      switch ( *(_WORD *)(v23 + 114) )
      {
        case 2:
        case 3:
          v24 = *(_QWORD *)(v7 + 8 * v21 + 2760);
          v25 = 0;
          v26 = *(_QWORD *)(a3 + 24LL * v20 + 96) + 1LL;
          v27 = *(_QWORD *)(v24 + 32);
          v28 = *(_DWORD *)(v24 + 208);
          v43 = v27;
          if ( !v28 )
            goto LABEL_30;
          break;
        case 4:
          QuicStreamOnResetAck(*(_QWORD *)(a3 + 24LL * v20 + 96));
          goto LABEL_46;
        case 6:
          QuicCryptoOnAck(v7 + 2784, v23 + 96);
          goto LABEL_46;
        case 8:
        case 9:
        case 0xA:
        case 0xB:
        case 0xC:
        case 0xD:
        case 0xE:
        case 0xF:
          QuicStreamOnAck(*(_QWORD *)(a3 + 24LL * v20 + 96), *(unsigned __int16 *)(a3 + 88), v23 + 96);
          goto LABEL_46;
        case 0x15:
          v31 = *(_QWORD *)(a3 + 24LL * v20 + 96);
          if ( (*(_BYTE *)(v31 + 98) & 0x40) == 0 )
            goto LABEL_47;
          QuicSendSetStreamSendFlag(v7 + 3416, v31, 1);
          goto LABEL_46;
        case 0x18:
          v41[0] = 0;
          SourceCidFromSeq = QuicConnGetSourceCidFromSeq(v7, *(_QWORD *)(a3 + 24LL * v20 + 96), 0, v41);
          v21 = v42;
          if ( SourceCidFromSeq )
            *(_BYTE *)(SourceCidFromSeq + 40) |= 4u;
          goto LABEL_47;
        case 0x19:
          LOBYTE(v23) = 1;
          DestCidFromSeq = (void *)QuicConnGetDestCidFromSeq(v7, *(_QWORD *)(a3 + 24LL * v20 + 96), v23);
          if ( !DestCidFromSeq )
            goto LABEL_47;
          --*(_BYTE *)(v7 + 273);
          ExFreePoolWithTag(DestCidFromSeq, 0x45306351u);
LABEL_46:
          v21 = v42;
LABEL_47:
          if ( ++v20 < *(_BYTE *)(a3 + 90) )
            continue;
          v13 = v44;
          goto LABEL_49;
        case 0x1E:
          LOBYTE(v22) = 1;
          QuicCryptoHandshakeConfirmed(v7 + 2784, v22);
          goto LABEL_46;
        case 0x21:
          QuicStreamOnResetReliableAck(*(_QWORD *)(a3 + 24LL * v20 + 96));
          goto LABEL_46;
        case 0x30:
        case 0x31:
          QuicDatagramIndicateSendStateChange(v7, a3 + 24 * (v20 + 4LL), (*(_BYTE *)(a3 + 88) & 0x20 | 0x80u) >> 5);
          *(_QWORD *)(a3 + 24 * (v20 + 4LL)) = 0;
          goto LABEL_46;
        default:
          goto LABEL_47;
      }
      break;
    }
    while ( 1 )
    {
      v29 = (unsigned __int64 *)(*(_QWORD *)(v24 + 200) + 16LL * (unsigned int)v25);
      v22 = *v29;
      if ( *v29 >= v26 )
        goto LABEL_27;
      v30 = v29[1];
      if ( v22 + v30 - 1 >= v26 )
        break;
      v25 = (unsigned int)(v25 + 1);
      if ( (unsigned int)v25 >= v28 )
        goto LABEL_27;
    }
    *v29 = v26;
    v29[1] = v22 + v30 - v26;
LABEL_27:
    if ( (_DWORD)v25 )
      QuicRangeRemoveSubranges(v24 + 200, 0);
    v27 = v43;
LABEL_30:
    if ( ((*(_BYTE *)(v24 + 394) & 1) != 0 || !*(_DWORD *)(v24 + 208)) && *(_WORD *)(v24 + 392) )
    {
      *(_WORD *)(v24 + 392) = 0;
      QuicSendUpdateAckState(v27 + 3416, v22, v25);
    }
    goto LABEL_46;
  }
LABEL_49:
  if ( v14 )
  {
    v34 = PacketSizeFromUdpPayloadSize(*((unsigned __int16 *)v14 + 28), *(unsigned __int16 *)(a3 + 40));
    v35 = v14[1];
    v36 = 0;
    v37 = v34;
    if ( (v35 & 0x40) == 0 )
    {
      v38 = *((_WORD *)v14 + 8);
      if ( v37 >= v38 )
      {
        v14[1] = v35 | 0x40;
        v36 = v37 != v38;
        if ( byte_14005C48B < 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Path[%hhu] Minimum MTU validated", *v14);
          McTemplateU0ps_EtwWriteTransfer(v39, QuicConnLogInfo, v7, DstBuf);
        }
      }
    }
    if ( (*(_BYTE *)(a3 + 88) & 8) != 0 && QuicMtuDiscoveryOnAckedPacket((__int64)(v14 + 24), v37, v7) || v36 )
      QuicDatagramOnSendStateChanged(v7 + 3552);
  }
  if ( !a4 )
  {
    v13[8] += *(unsigned __int16 *)(a3 + 40);
    v40 = *(_QWORD *)(a3 + 24);
    v13[4] = a5;
    v13[9] = v40;
    v13[5] = *(_QWORD *)(a3 + 32);
    v13[6] = a5 - a6;
  }
}

```

## disassembly

```asm
0x140013550  mov     [rsp+arg_18], rbx
0x140013555  push    rbp
0x140013556  push    rsi
0x140013557  push    rdi
0x140013558  push    r12
0x14001355a  push    r13
0x14001355c  push    r14
0x14001355e  push    r15
0x140013560  sub     rsp, 0E0h
0x140013567  mov     rax, cs:__security_cookie
0x14001356e  xor     rax, rsp
0x140013571  mov     [rsp+118h+var_48], rax
0x140013579  movzx   r11d, byte ptr [r8+2Ah]
0x14001357e  lea     rsi, [rcx-0A48h]
0x140013585  mov     rdi, r8
0x140013588  movsxd  r15, edx
0x14001358b  movzx   r8d, byte ptr [rsi+113h]
0x140013593  xor     r10b, r10b
0x140013596  xor     edx, edx
0x140013598  mov     [rsp+118h+var_D0], rcx
0x14001359d  movzx   r12d, r9b
0x1400135a1  mov     r13, rcx
0x1400135a4  test    r8b, r8b
0x1400135a7  jz      short loc_1400135D2
0x1400135a9  nop     dword ptr [rax+00000000h]
0x1400135b0  movzx   eax, r10b
0x1400135b4  imul    r14, rax, 0F0h
0x1400135bb  add     r14, 140h
0x1400135c2  add     r14, rsi
0x1400135c5  cmp     [r14], r11b
0x1400135c8  jz      short loc_1400135D5
0x1400135ca  inc     r10b
0x1400135cd  cmp     r10b, r8b
0x1400135d0  jb      short loc_1400135B0
0x1400135d2  mov     r14, rdx
0x1400135d5  mov     rcx, rsi
0x1400135d8  call    QuicConnIsClient
0x1400135dd  test    al, al
0x1400135df  jz      short loc_140013645
0x1400135e1  test    byte ptr [rsi+0FAh], 2
0x1400135e8  jnz     short loc_140013645
0x1400135ea  movzx   eax, byte ptr [rdi+58h]
0x1400135ee  and     al, 3
0x1400135f0  cmp     al, 3
0x1400135f2  jnz     short loc_140013645
0x1400135f4  movzx   eax, cs:byte_14005C48B
0x1400135fb  test    al, al
0x1400135fd  jns     short loc_140013637
0x1400135ff  lea     r9, aHandshakeConfi_0; "Handshake confirmed (ack)"
0x140013606  mov     edx, 80h; SizeInBytes
0x14001360b  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140013612  lea     rcx, [rsp+118h+DstBuf]; DstBuf
0x140013617  call    cs:__imp__snprintf_s
0x14001361e  nop     dword ptr [rax+rax+00h]
0x140013623  lea     r9, [rsp+118h+DstBuf]
0x140013628  mov     r8, rsi
0x14001362b  lea     rdx, QuicConnLogInfo
0x140013632  call    McTemplateU0ps_EtwWriteTransfer
0x140013637  lea     rcx, [rsi+0AE0h]
0x14001363e  mov     dl, 1
0x140013640  call    QuicCryptoHandshakeConfirmed
0x140013645  mov     rbx, [rsi+0AD8h]
0x14001364c  cmp     r15d, 2
0x140013650  jnz     short loc_1400136BF
0x140013652  movzx   ecx, byte ptr [rbx+1A8h]
0x140013659  test    r15b, cl
0x14001365c  jz      short loc_1400136BF
0x14001365e  movzx   eax, byte ptr [rdi+58h]
0x140013662  shr     al, 4
0x140013665  xor     al, cl
0x140013667  test    al, 1
0x140013669  jnz     short loc_1400136BF
0x14001366b  mov     rax, [rbx+190h]
0x140013672  cmp     [rdi+10h], rax
0x140013676  jb      short loc_1400136BF
0x140013678  test    cs:byte_14005C48C, 1
0x14001367f  jz      short loc_1400136B8
0x140013681  lea     r9, aKeyChangeConfi; "Key change confirmed by peer"
0x140013688  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001368f  lea     edx, [r15+7Eh]; SizeInBytes
0x140013693  lea     rcx, [rsp+118h+DstBuf]; DstBuf
0x140013698  call    cs:__imp__snprintf_s
0x14001369f  nop     dword ptr [rax+rax+00h]
0x1400136a4  lea     r9, [rsp+118h+DstBuf]
0x1400136a9  mov     r8, rsi
0x1400136ac  lea     rdx, QuicConnLogVerbose
0x1400136b3  call    McTemplateU0ps_EtwWriteTransfer
0x1400136b8  and     byte ptr [rbx+1A8h], 0FDh
0x1400136bf  xor     bpl, bpl
0x1400136c2  cmp     [rdi+5Ah], bpl
0x1400136c6  jbe     loc_140013928
0x1400136cc  mov     r9, r15
0x1400136cf  mov     [rsp+118h+var_E0], r15
0x1400136d4  lea     r10, cs:140000000h
0x1400136db  xor     r13d, r13d
0x1400136de  xchg    ax, ax
0x1400136e0  movzx   edx, bpl
0x1400136e4  lea     rax, [rdx+rdx*2]
0x1400136e8  lea     r8, [rdi+rax*8]
0x1400136ec  movzx   eax, word ptr [rdi+rax*8+72h]
0x1400136f1  add     eax, 0FFFFFFFEh; switch 48 cases
0x1400136f4  cmp     eax, 2Fh
0x1400136f7  ja      def_140013713; jumptable 0000000140013713 default case, cases 5,7,16-20,22,23,26-29,31,32,34-47
0x1400136fd  cdqe
0x1400136ff  movzx   eax, ds:(byte_140056CDF - 140000000h)[r10+rax]
0x140013708  mov     ecx, ds:(jpt_140013713 - 140000000h)[r10+rax*4]
0x140013710  add     rcx, r10
0x140013713  jmp     rcx; switch jump
0x140013719  mov     r15, [rsi+r9*8+0AC8h]; jumptable 0000000140013713 cases 2,3
0x140013721  lea     rax, [rdx+rdx*2]
0x140013725  mov     r10, [rdi+rax*8+60h]
0x14001372a  mov     r8d, r13d
0x14001372d  inc     r10
0x140013730  mov     rcx, [r15+20h]
0x140013734  mov     r11d, [r15+0D0h]
0x14001373b  mov     [rsp+118h+var_D8], rcx
0x140013740  test    r11d, r11d
0x140013743  jz      short loc_1400137A1
0x140013745  mov     rbx, [r15+0C8h]
0x14001374c  nop     dword ptr [rax+00h]
0x140013750  mov     ecx, r8d
0x140013753  shl     rcx, 4
0x140013757  add     rcx, rbx
0x14001375a  mov     rdx, [rcx]
0x14001375d  cmp     rdx, r10
0x140013760  jnb     short loc_140013789
0x140013762  mov     r9, [rcx+8]
0x140013766  lea     rax, [r9-1]
0x14001376a  add     rax, rdx
0x14001376d  cmp     rax, r10
0x140013770  jnb     short loc_14001377C
0x140013772  inc     r8d
0x140013775  cmp     r8d, r11d
0x140013778  jb      short loc_140013750
0x14001377a  jmp     short loc_140013789
0x14001377c  sub     r9, r10
0x14001377f  mov     [rcx], r10
0x140013782  add     r9, rdx
0x140013785  mov     [rcx+8], r9
0x140013789  test    r8d, r8d
0x14001378c  jz      short loc_14001379C
0x14001378e  xor     edx, edx
0x140013790  lea     rcx, [r15+0C8h]
0x140013797  call    QuicRangeRemoveSubranges
0x14001379c  mov     rcx, [rsp+118h+var_D8]
0x1400137a1  test    byte ptr [r15+18Ah], 1
0x1400137a9  jnz     short loc_1400137B8
0x1400137ab  cmp     [r15+0D0h], r13d
0x1400137b2  jnz     loc_14001390A
0x1400137b8  cmp     [r15+188h], r13w
0x1400137c0  jz      loc_14001390A
0x1400137c6  add     rcx, 0D58h
0x1400137cd  mov     [r15+188h], r13w
0x1400137d5  call    QuicSendUpdateAckState
0x1400137da  jmp     loc_14001390A
0x1400137df  lea     rcx, [rdx+rdx*2]; jumptable 0000000140013713 case 4
0x1400137e3  mov     rcx, [rdi+rcx*8+60h]
0x1400137e8  call    QuicStreamOnResetAck
0x1400137ed  jmp     loc_14001390A
0x1400137f2  lea     rcx, [rdx+rdx*2]; jumptable 0000000140013713 case 33
0x1400137f6  mov     rcx, [rdi+rcx*8+60h]
0x1400137fb  call    QuicStreamOnResetReliableAck
0x140013800  jmp     loc_14001390A
0x140013805  lea     rdx, [r8+60h]; jumptable 0000000140013713 case 6
0x140013809  lea     rcx, [rsi+0AE0h]
0x140013810  call    QuicCryptoOnAck
0x140013815  jmp     loc_14001390A
0x14001381a  lea     rcx, [rdx+rdx*2]; jumptable 0000000140013713 cases 8-15
0x14001381e  add     r8, 60h ; '`'
0x140013822  mov     rcx, [rdi+rcx*8+60h]
0x140013827  movzx   edx, word ptr [rdi+58h]
0x14001382b  call    QuicStreamOnAck
0x140013830  jmp     loc_14001390A
0x140013835  lea     rax, [rdx+rdx*2]; jumptable 0000000140013713 case 21
0x140013839  mov     rdx, [rdi+rax*8+60h]
0x14001383e  test    byte ptr [rdx+62h], 40h
0x140013842  jz      def_140013713; jumptable 0000000140013713 default case, cases 5,7,16-20,22,23,26-29,31,32,34-47
0x140013848  xor     r9d, r9d
0x14001384b  lea     rcx, [rsi+0D58h]
0x140013852  lea     r8d, [r9+1]
0x140013856  call    QuicSendSetStreamSendFlag
0x14001385b  jmp     loc_14001390A
0x140013860  lea     rdx, [rdx+rdx*2]; jumptable 0000000140013713 case 24
0x140013864  mov     [rsp+118h+var_E8], r13b
0x140013869  mov     rdx, [rdi+rdx*8+60h]
0x14001386e  lea     r9, [rsp+118h+var_E8]
0x140013873  xor     r8d, r8d
0x140013876  mov     rcx, rsi
0x140013879  call    QuicConnGetSourceCidFromSeq
0x14001387e  mov     r9, [rsp+118h+var_E0]
0x140013883  lea     r10, cs:140000000h
0x14001388a  test    rax, rax
0x14001388d  jz      def_140013713; jumptable 0000000140013713 default case, cases 5,7,16-20,22,23,26-29,31,32,34-47
0x140013893  or      byte ptr [rax+28h], 4
0x140013897  jmp     short def_140013713; jumptable 0000000140013713 default case, cases 5,7,16-20,22,23,26-29,31,32,34-47
0x140013899  lea     rdx, [rdx+rdx*2]; jumptable 0000000140013713 case 25
0x14001389d  mov     r8b, 1
0x1400138a0  mov     rdx, [rdi+rdx*8+60h]
0x1400138a5  mov     rcx, rsi
0x1400138a8  call    QuicConnGetDestCidFromSeq
0x1400138ad  test    rax, rax
0x1400138b0  jz      short def_140013713; jumptable 0000000140013713 default case, cases 5,7,16-20,22,23,26-29,31,32,34-47
0x1400138b2  dec     byte ptr [rsi+111h]
0x1400138b8  mov     edx, 45306351h; Tag
0x1400138bd  mov     rcx, rax; P
0x1400138c0  call    cs:__imp_ExFreePoolWithTag
0x1400138c7  nop     dword ptr [rax+rax+00h]
0x1400138cc  jmp     short loc_14001390A
0x1400138ce  movzx   r8d, byte ptr [rdi+58h]; jumptable 0000000140013713 cases 48,49
0x1400138d3  add     rdx, 4
0x1400138d7  and     r8d, 20h
0x1400138db  mov     rcx, rsi
0x1400138de  bts     r8d, 7
0x1400138e3  shr     r8d, 5
0x1400138e7  lea     rax, [rdx+rdx*2]
0x1400138eb  lea     rbx, [rdi+rax*8]
0x1400138ef  mov     rdx, rbx
0x1400138f2  call    QuicDatagramIndicateSendStateChange
0x1400138f7  mov     [rbx], r13
0x1400138fa  jmp     short loc_14001390A
0x1400138fc  lea     rcx, [rsi+0AE0h]; jumptable 0000000140013713 case 30
0x140013903  mov     dl, 1
0x140013905  call    QuicCryptoHandshakeConfirmed
0x14001390a  mov     r9, [rsp+118h+var_E0]
0x14001390f  lea     r10, cs:140000000h
0x140013916  inc     bpl; jumptable 0000000140013713 default case, cases 5,7,16-20,22,23,26-29,31,32,34-47
0x140013919  cmp     bpl, [rdi+5Ah]
0x14001391d  jb      loc_1400136E0
0x140013923  mov     r13, [rsp+118h+var_D0]
0x140013928  test    r14, r14
0x14001392b  jz      loc_1400139D9
0x140013931  movzx   edx, word ptr [rdi+28h]
0x140013935  movzx   ecx, word ptr [r14+38h]
0x14001393a  call    PacketSizeFromUdpPayloadSize
0x14001393f  movzx   ecx, byte ptr [r14+1]
0x140013944  xor     bl, bl
0x140013946  movzx   ebp, ax
0x140013949  test    cl, 40h
0x14001394c  jnz     short loc_1400139B0
0x14001394e  movzx   eax, word ptr [r14+10h]
0x140013953  cmp     bp, ax
0x140013956  jb      short loc_1400139B0
0x140013958  or      cl, 40h
0x14001395b  cmp     bp, ax
0x14001395e  mov     [r14+1], cl
0x140013962  movzx   eax, cs:byte_14005C48B
0x140013969  setnbe  bl
0x14001396c  test    al, al
0x14001396e  jns     short loc_1400139B0
0x140013970  movzx   eax, byte ptr [r14]
0x140013974  lea     r9, aPathHhuMinimum; "Path[%hhu] Minimum MTU validated"
0x14001397b  mov     edx, 80h; SizeInBytes
0x140013980  mov     [rsp+118h+var_F8], eax
0x140013984  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001398b  lea     rcx, [rsp+118h+DstBuf]; DstBuf
0x140013990  call    cs:__imp__snprintf_s
0x140013997  nop     dword ptr [rax+rax+00h]
0x14001399c  lea     r9, [rsp+118h+DstBuf]
0x1400139a1  mov     r8, rsi
0x1400139a4  lea     rdx, QuicConnLogInfo
0x1400139ab  call    McTemplateU0ps_EtwWriteTransfer
0x1400139b0  test    byte ptr [rdi+58h], 8
0x1400139b4  jz      short loc_1400139C9
0x1400139b6  lea     rcx, [r14+18h]
0x1400139ba  mov     r8, rsi
0x1400139bd  movzx   edx, bp
0x1400139c0  call    QuicMtuDiscoveryOnAckedPacket
0x1400139c5  test    al, al
0x1400139c7  jnz     short loc_1400139CD
0x1400139c9  test    bl, bl
0x1400139cb  jz      short loc_1400139D9
0x1400139cd  lea     rcx, [rsi+0DE0h]
0x1400139d4  call    QuicDatagramOnSendStateChanged
0x1400139d9  test    r12b, r12b
0x1400139dc  jnz     short loc_140013A0E
0x1400139de  movzx   eax, word ptr [rdi+28h]
0x1400139e2  add     [r13+40h], rax
0x1400139e6  mov     rax, [rdi+18h]
0x1400139ea  mov     rcx, [rsp+118h+arg_20]
0x1400139f2  mov     [r13+20h], rcx
0x1400139f6  sub     rcx, [rsp+118h+arg_28]
0x1400139fe  mov     [r13+48h], rax
0x140013a02  mov     rax, [rdi+20h]
0x140013a06  mov     [r13+28h], rax
0x140013a0a  mov     [r13+30h], rcx
0x140013a0e  mov     rcx, [rsp+118h+var_48]
0x140013a16  xor     rcx, rsp; StackCookie
0x140013a19  call    __security_check_cookie
0x140013a1e  mov     rbx, [rsp+118h+arg_18]
0x140013a26  add     rsp, 0E0h
0x140013a2d  pop     r15
0x140013a2f  pop     r14
0x140013a31  pop     r13
0x140013a33  pop     r12
0x140013a35  pop     rdi
0x140013a36  pop     rsi
0x140013a37  pop     rbp
0x140013a38  retn
```
