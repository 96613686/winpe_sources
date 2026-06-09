# QuicStreamWriteStreamFrames

- ea: `0x1400183d0`
- end: `0x1400188dd`
- name: `QuicStreamWriteStreamFrames`
- size: `1293`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140018050`

## callees

- `0x14000d230`
- `0x14000d490`
- `0x140010820`
- `0x1400183d0`
- `0x1400188f0`
- `0x1400217f0`
- `0x140022dfc`
- `0x14003c8e0`
- `0x14003e884`
- `0x14003ec10`
- `0x1400426e8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400187b6`
- `ntoskrnl!_snprintf_s` at `0x140018830`
- `ntoskrnl!_snprintf_s` at `0x140018896`
- `ntoskrnl!_snprintf_s` at `0x1400187b6`
- `ntoskrnl!_snprintf_s` at `0x140018830`
- `ntoskrnl!_snprintf_s` at `0x140018896`

## pseudocode

```c
int __fastcall QuicStreamWriteStreamFrames(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 *a4, __int64 a5)
{
  unsigned __int16 v5; // r11
  unsigned int v7; // r14d
  __int64 v8; // rax
  unsigned __int16 *v9; // rsi
  __int64 v10; // r15
  unsigned __int16 v11; // r13
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r8
  __int64 v14; // r9
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rbp
  char v18; // r12
  __int64 v19; // r9
  unsigned __int64 *v20; // rdi
  unsigned __int64 v21; // r8
  __int64 v22; // rax
  unsigned __int64 v23; // rdx
  __int64 v24; // r15
  unsigned __int64 v25; // r15
  __int16 v26; // ax
  _BOOL8 v27; // rdx
  unsigned __int64 v28; // rsi
  __int64 v29; // rax
  __int64 v30; // rcx
  unsigned __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  unsigned int v34; // eax
  __int64 v35; // rdi
  __int64 v36; // rcx
  unsigned __int64 i; // rcx
  __int64 v38; // rdi
  _QWORD *v39; // rdi
  __int64 v40; // rcx
  __int64 v41; // rcx
  _WORD v43[2]; // [rsp+70h] [rbp-F8h] BYREF
  unsigned __int16 v44; // [rsp+74h] [rbp-F4h] BYREF
  __int64 v45; // [rsp+78h] [rbp-F0h]
  __int64 v46; // [rsp+80h] [rbp-E8h]
  unsigned __int16 *v47; // [rsp+88h] [rbp-E0h]
  __int64 v48; // [rsp+90h] [rbp-D8h]
  char DstBuf[128]; // [rsp+A0h] [rbp-C8h] BYREF

  v5 = *a4;
  v7 = 0;
  v8 = a3;
  v47 = a4;
  v9 = a4;
  v10 = *(_QWORD *)(a1 + 72);
  v11 = 0;
  v45 = v10;
  v46 = a3;
  v48 = a5;
  if ( v5 )
  {
    do
    {
      if ( *(_BYTE *)(v8 + 90) >= 0xCu )
        break;
      v12 = *(_QWORD *)(a1 + 232);
      v13 = *(_QWORD *)(a1 + 240);
      v14 = *(_QWORD *)(a1 + 224);
      v15 = v5 - (unsigned __int64)v11;
      if ( v12 >= v13 )
      {
        v18 = 0;
        v17 = *(_QWORD *)(a1 + 224);
        v16 = v14 + v15;
      }
      else
      {
        v16 = v12 + v15;
        v17 = *(_QWORD *)(a1 + 232);
        v18 = 1;
        if ( v16 > v13 && v13 != v14 )
          v16 = *(_QWORD *)(a1 + 240);
      }
      v19 = *(_QWORD *)(a1 + 208);
      if ( v17 == v19 )
      {
        v20 = 0;
LABEL_10:
        v21 = v16;
        if ( v16 > *(_QWORD *)(a1 + 160) )
          v21 = *(_QWORD *)(a1 + 160);
      }
      else
      {
        v34 = 0;
        do
        {
          if ( v34 >= *(_DWORD *)(a1 + 272) )
          {
            v20 = 0;
            goto LABEL_10;
          }
          v35 = v34++;
          v20 = (unsigned __int64 *)(*(_QWORD *)(a1 + 264) + 16 * v35);
          if ( !v20 )
            goto LABEL_10;
        }
        while ( *v20 < v17 );
        v21 = *v20;
        if ( v16 <= *v20 )
          v21 = v16;
      }
      v22 = *(_QWORD *)(v10 + 3472);
      v23 = *(_QWORD *)(a1 + 184);
      v24 = *(_QWORD *)(v10 + 3456);
      if ( v21 <= v23 )
        v23 = v21;
      v25 = v19 + v24 - v22;
      v43[0] = v5 - v11;
      v26 = v25;
      if ( v23 <= v25 )
        v26 = v23;
      v44 = v26 - v17;
      QuicStreamWriteOneFrame(a1, v23, v17, (unsigned int)&v44, (__int64)v43, v11 + v48, v46);
      v11 += v43[0];
      LODWORD(v8) = v44;
      v27 = v44 == 0;
      v28 = v44 + v17;
      if ( v28 == *(_QWORD *)(a1 + 160) )
      {
        if ( (*(_BYTE *)(a1 + 91) & 2) != 0 && *(char *)(a1 + 98) >= 0 )
        {
          v29 = QuicTimePlat(1, v27);
          *(_QWORD *)(a1 + 880) = QuicTimePlatToUs64(v29);
          LODWORD(v8) = *(unsigned __int8 *)(a1 + 98);
          LOBYTE(v8) = v8 | 0x80;
          *(_BYTE *)(a1 + 98) = v8;
          if ( (byte_14005C48C & 4) != 0 )
            LODWORD(v8) = McTemplateU0pu_EtwWriteTransfer(
                            v30,
                            (const EVENT_DESCRIPTOR *)QuicStreamOutFlowBlocked,
                            a1,
                            v8);
        }
        LOBYTE(v27) = 1;
      }
      if ( v28 == *(_QWORD *)(a1 + 184) )
      {
        LODWORD(v8) = QuicStreamAddOutFlowBlockedReason(a1, 64);
        if ( (_BYTE)v8 )
          LODWORD(v8) = QuicSendSetStreamSendFlag(*(_QWORD *)(a1 + 72) + 3416LL, a1, 1);
        LOBYTE(v27) = 1;
      }
      if ( v28 == v25 )
      {
        LODWORD(v8) = QuicConnAddOutFlowBlockedReason(*(_QWORD *)(a1 + 72), 16);
        if ( (_BYTE)v8 )
          LODWORD(v8) = QuicSendSetSendFlag(*(_QWORD *)(a1 + 72) + 3416LL, 16);
        LOBYTE(v27) = 1;
      }
      if ( v18 )
      {
        *(_QWORD *)(a1 + 232) = v28;
        if ( v20 )
        {
          if ( v28 == *v20 )
            *(_QWORD *)(a1 + 232) = v28 + v20[1];
        }
      }
      if ( *(_QWORD *)(a1 + 224) < v28 )
      {
        *(_QWORD *)(a1 + 224) = v28;
        if ( v20 )
        {
          if ( v28 == *v20 )
            *(_QWORD *)(a1 + 224) = v28 + v20[1];
        }
      }
      v31 = *(_QWORD *)(a1 + 208);
      v10 = v45;
      if ( v31 < v28 )
      {
        v8 = v28 + *(_QWORD *)(v45 + 3472) - v31;
        *(_QWORD *)(v45 + 3472) = v8;
        *(_QWORD *)(a1 + 208) = v28;
      }
      v9 = v47;
      if ( v27 )
        break;
      v5 = *v47;
      v8 = v46;
    }
    while ( v11 < *v47 );
  }
  if ( (byte_14005C48D & 1) != 0 )
  {
    if ( (*(_BYTE *)(a1 + 90) & 8) != 0 )
    {
      v32 = *(_QWORD *)(a1 + 232);
      v33 = *(_QWORD *)(a1 + 240);
    }
    else
    {
      v32 = 0;
      v33 = 0;
    }
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "SF:%hX FC:%llu QS:%llu MAX:%llu UNA:%llu NXT:%llu RECOV:%llu-%llu REL: %llu",
      *(unsigned __int16 *)(a1 + 96),
      *(_QWORD *)(a1 + 184),
      *(_QWORD *)(a1 + 160),
      *(_QWORD *)(a1 + 208),
      *(_QWORD *)(a1 + 216),
      *(_QWORD *)(a1 + 224),
      v32,
      v33,
      *(_QWORD *)(a1 + 248));
    LODWORD(v8) = McTemplateU0ps_EtwWriteTransfer(v36, (const EVENT_DESCRIPTOR *)QuicStreamLogVerbose, a1, DstBuf);
    for ( i = *(_QWORD *)(a1 + 216); v7 < *(_DWORD *)(a1 + 272); i = *v39 + v39[1] )
    {
      v38 = v7++;
      v39 = (_QWORD *)(*(_QWORD *)(a1 + 264) + 16 * v38);
      if ( !v39 )
        break;
      if ( (byte_14005C48D & 1) != 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "  unACKed: [%llu, %llu]", i, *v39);
        LODWORD(v8) = McTemplateU0ps_EtwWriteTransfer(v40, (const EVENT_DESCRIPTOR *)QuicStreamLogVerbose, a1, DstBuf);
      }
    }
    if ( i < *(_QWORD *)(a1 + 208) && (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "  unACKed: [%llu, %llu]", i, *(_QWORD *)(a1 + 208));
      LODWORD(v8) = McTemplateU0ps_EtwWriteTransfer(v41, (const EVENT_DESCRIPTOR *)QuicStreamLogVerbose, a1, DstBuf);
    }
  }
  *v9 = v11;
  return v8;
}

```

## disassembly

```asm
0x1400183d0  push    rbx
0x1400183d2  push    rsi
0x1400183d3  push    rdi
0x1400183d4  push    r13
0x1400183d6  push    r14
0x1400183d8  sub     rsp, 140h
0x1400183df  mov     rax, cs:__security_cookie
0x1400183e6  xor     rax, rsp
0x1400183e9  mov     [rsp+168h+var_48], rax
0x1400183f1  movzx   r11d, word ptr [r9]
0x1400183f5  mov     rbx, rcx
0x1400183f8  mov     rcx, [rsp+168h+arg_20]
0x140018400  xor     r14d, r14d
0x140018403  mov     [rsp+168h+var_38], r15
0x14001840b  mov     rax, r8
0x14001840e  mov     [rsp+168h+var_E0], r9
0x140018416  mov     rsi, r9
0x140018419  mov     r15, [rbx+48h]
0x14001841d  movzx   r13d, r14w
0x140018421  mov     [rsp+168h+var_F0], r15
0x140018426  mov     [rsp+168h+var_E8], rax
0x14001842e  mov     [rsp+168h+var_D8], rcx
0x140018436  cmp     r14w, r11w
0x14001843a  jnb     loc_1400186BA
0x140018440  mov     [rsp+168h+arg_8], rbp
0x140018448  mov     [rsp+168h+var_30], r12
0x140018450  cmp     byte ptr [rax+5Ah], 0Ch
0x140018454  jnb     loc_1400186AA
0x14001845a  mov     rax, [rbx+0E8h]
0x140018461  mov     r8, [rbx+0F0h]
0x140018468  mov     r9, [rbx+0E0h]
0x14001846f  movzx   edx, r13w
0x140018473  movzx   ecx, r11w
0x140018477  mov     r10d, edx
0x14001847a  sub     rcx, rdx
0x14001847d  cmp     rax, r8
0x140018480  jnb     short loc_14001849A
0x140018482  add     rcx, rax
0x140018485  mov     rbp, rax
0x140018488  mov     r12b, 1
0x14001848b  cmp     rcx, r8
0x14001848e  jbe     short loc_1400184A3
0x140018490  cmp     r8, r9
0x140018493  jz      short loc_1400184A3
0x140018495  mov     rcx, r8
0x140018498  jmp     short loc_1400184A3
0x14001849a  xor     r12b, r12b
0x14001849d  mov     rbp, r9
0x1400184a0  add     rcx, r9
0x1400184a3  mov     r9, [rbx+0D0h]
0x1400184aa  cmp     rbp, r9
0x1400184ad  jnz     loc_1400186E5
0x1400184b3  mov     rdi, r14
0x1400184b6  mov     rax, [rbx+0A0h]
0x1400184bd  mov     r8, rcx
0x1400184c0  cmp     rcx, rax
0x1400184c3  cmova   r8, rax
0x1400184c7  mov     rax, [r15+0D90h]
0x1400184ce  mov     rdx, [rbx+0B8h]
0x1400184d5  mov     r15, [r15+0D80h]
0x1400184dc  cmp     r8, rdx
0x1400184df  mov     rcx, [rsp+168h+var_E8]
0x1400184e7  cmovbe  rdx, r8
0x1400184eb  mov     [rsp+168h+var_138], rcx
0x1400184f0  sub     r15, rax
0x1400184f3  sub     r11w, r13w
0x1400184f7  add     r15, r9
0x1400184fa  mov     [rsp+168h+var_F8], r11w
0x140018500  cmp     rdx, r15
0x140018503  lea     r9, [rsp+168h+var_F4]
0x140018508  movzx   eax, r15w
0x14001850c  mov     r8, rbp
0x14001850f  cmovbe  ax, dx
0x140018513  mov     rcx, rbx
0x140018516  sub     ax, bp
0x140018519  mov     [rsp+168h+var_F4], ax
0x14001851e  mov     rax, [rsp+168h+var_D8]
0x140018526  add     rax, r10
0x140018529  mov     [rsp+168h+var_140], rax
0x14001852e  lea     rax, [rsp+168h+var_F8]
0x140018533  mov     [rsp+168h+var_148], rax
0x140018538  call    QuicStreamWriteOneFrame
0x14001853d  add     r13w, [rsp+168h+var_F8]
0x140018543  xor     al, al
0x140018545  movzx   edx, al
0x140018548  mov     ecx, 1
0x14001854d  movzx   eax, [rsp+168h+var_F4]
0x140018552  test    ax, ax
0x140018555  cmovz   edx, ecx
0x140018558  lea     rsi, [rax+rbp]
0x14001855c  cmp     rsi, [rbx+0A0h]
0x140018563  jnz     short loc_1400185AC
0x140018565  test    byte ptr [rbx+5Bh], 2
0x140018569  jz      short loc_1400185AA
0x14001856b  cmp     [rbx+62h], r14b
0x14001856f  jl      short loc_1400185AA
0x140018571  call    QuicTimePlat
0x140018576  mov     rcx, rax
0x140018579  call    QuicTimePlatToUs64
0x14001857e  mov     [rbx+370h], rax
0x140018585  movzx   eax, byte ptr [rbx+62h]
0x140018589  or      al, 80h
0x14001858b  mov     [rbx+62h], al
0x14001858e  movzx   r9d, al
0x140018592  test    cs:byte_14005C48C, 4
0x140018599  jz      short loc_1400185AA
0x14001859b  mov     r8, rbx
0x14001859e  lea     rdx, QuicStreamOutFlowBlocked
0x1400185a5  call    McTemplateU0pu_EtwWriteTransfer
0x1400185aa  mov     dl, 1
0x1400185ac  cmp     rsi, [rbx+0B8h]
0x1400185b3  jnz     short loc_1400185E2
0x1400185b5  mov     edx, 40h ; '@'
0x1400185ba  mov     rcx, rbx
0x1400185bd  call    QuicStreamAddOutFlowBlockedReason
0x1400185c2  test    al, al
0x1400185c4  jz      short loc_1400185E0
0x1400185c6  mov     rcx, [rbx+48h]
0x1400185ca  xor     r9d, r9d
0x1400185cd  add     rcx, 0D58h
0x1400185d4  mov     rdx, rbx
0x1400185d7  lea     r8d, [r9+1]
0x1400185db  call    QuicSendSetStreamSendFlag
0x1400185e0  mov     dl, 1
0x1400185e2  cmp     rsi, r15
0x1400185e5  jnz     short loc_140018610
0x1400185e7  mov     rcx, [rbx+48h]
0x1400185eb  mov     edx, 10h
0x1400185f0  call    QuicConnAddOutFlowBlockedReason
0x1400185f5  test    al, al
0x1400185f7  jz      short loc_14001860E
0x1400185f9  mov     rcx, [rbx+48h]
0x1400185fd  mov     edx, 10h
0x140018602  add     rcx, 0D58h
0x140018609  call    QuicSendSetSendFlag
0x14001860e  mov     dl, 1
0x140018610  test    r12b, r12b
0x140018613  jz      short loc_140018634
0x140018615  mov     [rbx+0E8h], rsi
0x14001861c  test    rdi, rdi
0x14001861f  jz      short loc_140018634
0x140018621  cmp     rsi, [rdi]
0x140018624  jnz     short loc_140018634
0x140018626  mov     rcx, [rdi+8]
0x14001862a  add     rcx, rsi
0x14001862d  mov     [rbx+0E8h], rcx
0x140018634  cmp     [rbx+0E0h], rsi
0x14001863b  jnb     short loc_14001865C
0x14001863d  mov     [rbx+0E0h], rsi
0x140018644  test    rdi, rdi
0x140018647  jz      short loc_14001865C
0x140018649  cmp     rsi, [rdi]
0x14001864c  jnz     short loc_14001865C
0x14001864e  mov     rcx, [rdi+8]
0x140018652  add     rcx, rsi
0x140018655  mov     [rbx+0E0h], rcx
0x14001865c  mov     rcx, [rbx+0D0h]
0x140018663  mov     r15, [rsp+168h+var_F0]
0x140018668  cmp     rcx, rsi
0x14001866b  jnb     short loc_140018688
0x14001866d  mov     rax, [r15+0D90h]
0x140018674  sub     rax, rcx
0x140018677  add     rax, rsi
0x14001867a  mov     [r15+0D90h], rax
0x140018681  mov     [rbx+0D0h], rsi
0x140018688  mov     rsi, [rsp+168h+var_E0]
0x140018690  test    dl, dl
0x140018692  jnz     short loc_1400186AA
0x140018694  movzx   r11d, word ptr [rsi]
0x140018698  mov     rax, [rsp+168h+var_E8]
0x1400186a0  cmp     r13w, r11w
0x1400186a4  jb      loc_140018450
0x1400186aa  mov     r12, [rsp+168h+var_30]
0x1400186b2  mov     rbp, [rsp+168h+arg_8]
0x1400186ba  test    cs:byte_14005C48D, 1
0x1400186c1  mov     r15, [rsp+168h+var_38]
0x1400186c9  jz      loc_1400188B9
0x1400186cf  test    byte ptr [rbx+5Ah], 8
0x1400186d3  jz      short loc_14001873B
0x1400186d5  mov     rdx, [rbx+0E8h]
0x1400186dc  mov     r8, [rbx+0F0h]
0x1400186e3  jmp     short loc_140018741
0x1400186e5  mov     edx, [rbx+110h]
0x1400186eb  mov     eax, r14d
0x1400186ee  xchg    ax, ax
0x1400186f0  cmp     eax, edx
0x1400186f2  jnb     short loc_140018720
0x1400186f4  mov     edi, eax
0x1400186f6  inc     eax
0x1400186f8  shl     rdi, 4
0x1400186fc  add     rdi, [rbx+108h]
0x140018703  test    rdi, rdi
0x140018706  jz      loc_1400184B6
0x14001870c  cmp     [rdi], rbp
0x14001870f  jb      short loc_1400186F0
0x140018711  mov     r8, [rdi]
0x140018714  cmp     rcx, r8
0x140018717  cmovbe  r8, rcx
0x14001871b  jmp     loc_1400184C7
0x140018720  mov     rdi, r14
0x140018723  test    r14, r14
0x140018726  jz      loc_1400184B6
0x14001872c  mov     r8, [r14]
0x14001872f  cmp     rcx, r8
0x140018732  cmovbe  r8, rcx
0x140018736  jmp     loc_1400184C7
0x14001873b  mov     rdx, r14
0x14001873e  mov     r8, r14
0x140018741  mov     rax, [rbx+0F8h]
0x140018748  lea     r9, aSfHxFcLluQsLlu; "SF:%hX FC:%llu QS:%llu MAX:%llu UNA:%ll"...
0x14001874f  movzx   ecx, word ptr [rbx+60h]
0x140018753  mov     [rsp+168h+var_108], rax
0x140018758  mov     rax, [rbx+0E0h]
0x14001875f  mov     [rsp+168h+var_110], r8
0x140018764  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001876b  mov     [rsp+168h+var_118], rdx
0x140018770  mov     edx, 80h; SizeInBytes
0x140018775  mov     [rsp+168h+var_120], rax
0x14001877a  mov     rax, [rbx+0D8h]
0x140018781  mov     [rsp+168h+var_128], rax
0x140018786  mov     rax, [rbx+0D0h]
0x14001878d  mov     [rsp+168h+var_130], rax
0x140018792  mov     rax, [rbx+0A0h]
0x140018799  mov     [rsp+168h+var_138], rax
0x14001879e  mov     rax, [rbx+0B8h]
0x1400187a5  mov     [rsp+168h+var_140], rax
0x1400187aa  mov     dword ptr [rsp+168h+var_148], ecx
0x1400187ae  lea     rcx, [rsp+168h+DstBuf]; DstBuf
0x1400187b6  call    cs:__imp__snprintf_s
0x1400187bd  nop     dword ptr [rax+rax+00h]
0x1400187c2  lea     r9, [rsp+168h+DstBuf]
0x1400187ca  mov     r8, rbx
0x1400187cd  lea     rdx, QuicStreamLogVerbose
0x1400187d4  call    McTemplateU0ps_EtwWriteTransfer
0x1400187d9  mov     rcx, [rbx+0D8h]
0x1400187e0  cmp     r14d, [rbx+110h]
0x1400187e7  jnb     short loc_14001885C
0x1400187e9  mov     edi, r14d
0x1400187ec  inc     r14d
0x1400187ef  shl     rdi, 4
0x1400187f3  add     rdi, [rbx+108h]
0x1400187fa  test    rdi, rdi
0x1400187fd  jz      short loc_14001885C
0x1400187ff  test    cs:byte_14005C48D, 1
0x140018806  jz      short loc_140018853
0x140018808  mov     rax, [rdi]
0x14001880b  lea     r9, aUnackedLluLlu; "  unACKed: [%llu, %llu]"
0x140018812  mov     [rsp+168h+var_140], rax
0x140018817  mov     edx, 80h; SizeInBytes
0x14001881c  mov     [rsp+168h+var_148], rcx
0x140018821  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140018828  lea     rcx, [rsp+168h+DstBuf]; DstBuf
0x140018830  call    cs:__imp__snprintf_s
0x140018837  nop     dword ptr [rax+rax+00h]
0x14001883c  lea     r9, [rsp+168h+DstBuf]
0x140018844  mov     r8, rbx
0x140018847  lea     rdx, QuicStreamLogVerbose
0x14001884e  call    McTemplateU0ps_EtwWriteTransfer
0x140018853  mov     rcx, [rdi+8]
0x140018857  add     rcx, [rdi]
0x14001885a  jmp     short loc_1400187E0
0x14001885c  mov     r10, [rbx+0D0h]
0x140018863  cmp     rcx, r10
0x140018866  jnb     short loc_1400188B9
0x140018868  test    cs:byte_14005C48D, 1
0x14001886f  jz      short loc_1400188B9
0x140018871  mov     [rsp+168h+var_140], r10
0x140018876  lea     r9, aUnackedLluLlu; "  unACKed: [%llu, %llu]"
0x14001887d  mov     [rsp+168h+var_148], rcx
0x140018882  mov     edx, 80h; SizeInBytes
0x140018887  lea     rcx, [rsp+168h+DstBuf]; DstBuf
0x14001888f  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140018896  call    cs:__imp__snprintf_s
0x14001889d  nop     dword ptr [rax+rax+00h]
0x1400188a2  lea     r9, [rsp+168h+DstBuf]
0x1400188aa  mov     r8, rbx
0x1400188ad  lea     rdx, QuicStreamLogVerbose
0x1400188b4  call    McTemplateU0ps_EtwWriteTransfer
0x1400188b9  mov     [rsi], r13w
0x1400188bd  mov     rcx, [rsp+168h+var_48]
0x1400188c5  xor     rcx, rsp; StackCookie
0x1400188c8  call    __security_check_cookie
0x1400188cd  add     rsp, 140h
0x1400188d4  pop     r14
0x1400188d6  pop     r13
0x1400188d8  pop     rdi
0x1400188d9  pop     rsi
0x1400188da  pop     rbx
0x1400188db  retn
```
