# CMp3Decode::Decode(uchar *,int,int *)

- ea: `0x1800045d0`
- end: `0x180004905`
- name: `?Decode@CMp3Decode@@QEAA?AW4SSC@@PEAEHPEAH@Z`
- size: `821`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180003ce0`

## callees

- `0x1800045d0`
- `0x180004910`
- `0x180004da0`
- `0x180005480`
- `0x18000a590`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CMp3Decode::Decode(__int64 a1, __int16 *a2, int a3, int *a4)
{
  int v7; // ecx
  _DWORD *v8; // r8
  __int64 v9; // r9
  int v11; // r11d
  int v12; // esi
  char v13; // cl
  int v14; // esi
  int v15; // edx
  int v16; // ecx
  int v17; // r12d
  struct CBitStream *v18; // rcx
  int v19; // eax
  char v20; // al
  struct CBitStream *v21; // r10
  char v22; // cl
  int v23; // eax
  int v24; // ebp
  int v25; // ebp
  int v26; // r9d
  int v27; // ebx
  int v28; // eax
  int v29; // r8d
  int v30; // ecx
  int v31; // edx
  int v32; // eax
  int v33; // ecx
  int v34; // r8d
  int v35; // ecx
  char v36; // bp
  int v37; // eax
  _DWORD *v38; // r8
  int v39; // ebx
  int v40; // edx
  int v41; // ecx
  int v42; // eax
  char v43; // [rsp+60h] [rbp+8h]

  if ( *(_DWORD *)(a1 + 41200) )
    LOBYTE(v7) = 1;
  else
    v7 = *(_DWORD *)(*(_QWORD *)(a1 + 30352) + 136LL);
  v8 = *(_DWORD **)(a1 + 30352);
  v9 = (int)v8[21];
  if ( (_DWORD)v9 != 3 )
    return 3238068226LL;
  v11 = *(_DWORD *)(a1 + 41196);
  v12 = dword_180014BB4[3 * v8[33] + v9] << v7;
  if ( v11 < 0 )
  {
    v12 *= 2;
    v13 = *(_DWORD *)(a1 + 41192);
  }
  else
  {
    v13 = v11 + *(_DWORD *)(a1 + 41192);
  }
  v14 = v12 >> v13;
  if ( a3 < v14 )
    return 3238068227LL;
  v15 = v8[5];
  v16 = v8[22] != 0 ? 0x10 : 0;
  v17 = 32;
  v8[8] += v16 + 32;
  v8[6] += -32 - v16;
  v8[9] = (v8[9] + 32 + v16) & (v15 - 1);
  v18 = *(struct CBitStream **)(a1 + 30352);
  *(_DWORD *)(a1 + 30312) = *((_DWORD *)v18 + 34);
  *(_DWORD *)(a1 + 30316) = *((_DWORD *)v18 + 24);
  *(_DWORD *)(a1 + 30320) = *((_DWORD *)v18 + 37);
  *(_DWORD *)(a1 + 30324) = *((_DWORD *)v18 + 27);
  *(_DWORD *)(a1 + 30328) = *((_DWORD *)v18 + 28);
  v19 = 48;
  if ( !*((_DWORD *)v18 + 22) )
    v19 = 32;
  *(_DWORD *)(a1 + 30332) = v19;
  *(_BYTE *)(a1 + 30344) = *((_DWORD *)v18 + 33) == 0;
  *(_DWORD *)(a1 + 30336) = dword_180013900[*((int *)v18 + 33)];
  *(_DWORD *)(a1 + 30340) = *((_DWORD *)v18 + 22);
  v20 = mp3SideInfoRead(v18, (struct MP3SI *)(a1 + 30424), (const struct MPEG_INFO *)(a1 + 30312));
  v21 = *(struct CBitStream **)(a1 + 30352);
  v22 = *(_BYTE *)(a1 + 30344);
  v43 = v20;
  v23 = 17;
  v24 = (*(_DWORD *)(a1 + 30320) - *(_DWORD *)(a1 + 30332)) / 8;
  if ( *(_DWORD *)(a1 + 30312) == 1 )
  {
    if ( !v22 )
      v23 = 9;
    v25 = v24 - v23;
  }
  else
  {
    if ( !v22 )
      v17 = 17;
    v25 = v24 - v17;
  }
  v26 = *(_DWORD *)(a1 + 30380);
  v27 = *(_DWORD *)(a1 + 30384);
  v28 = (v26 - v27) / 8;
  if ( v28 < v25 )
  {
    v29 = 8 * (v25 - v28);
    if ( v29 > 0 )
    {
      v30 = *(_DWORD *)(a1 + 30396);
      *(_DWORD *)(a1 + 30392) += v29;
      *(_DWORD *)(a1 + 30384) = v27 - v29;
      *(_DWORD *)(a1 + 30396) = (v26 - 1) & (v29 + v30);
    }
  }
  if ( (unsigned int)CBitStream::Fill((CBitStream *)(a1 + 30360), v21, v25) == v25
    && v27 >> 3 >= *(_DWORD *)(a1 + 30424) )
  {
    v31 = *(_DWORD *)(a1 + 30384);
    if ( v31 > 0 )
    {
      v32 = *(_DWORD *)(a1 + 30380);
      v33 = v31 + *(_DWORD *)(a1 + 30396);
      *(_DWORD *)(a1 + 30392) += v31;
      *(_DWORD *)(a1 + 30384) = 0;
      *(_DWORD *)(a1 + 30396) = (v32 - 1) & v33;
      v31 = 0;
    }
    v34 = 8 * (v25 + *(_DWORD *)(a1 + 30424));
    if ( v34 > 0 )
    {
      v35 = *(_DWORD *)(a1 + 30396);
      *(_DWORD *)(a1 + 30392) -= v34;
      *(_DWORD *)(a1 + 30384) = v31 + v34;
      *(_DWORD *)(a1 + 30396) = (*(_DWORD *)(a1 + 30380) - 1) & (v35 - v34);
    }
    v36 = v43;
    v37 = CMp3Decode::DecodeNormal(a1, a2, v43);
  }
  else
  {
    v37 = CMp3Decode::DecodeOnNoMainData(a1, a2);
    v36 = v43;
  }
  v38 = *(_DWORD **)(a1 + 30352);
  v39 = v37;
  v40 = v38[37] - v38[8];
  v38[8] = v38[37];
  v41 = v38[5];
  v42 = v40 + v38[9];
  v38[6] -= v40;
  v38[9] = v42 & (v41 - 1);
  if ( a4 && v39 >= 0 )
    *a4 = v14;
  if ( !v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 30360) + 8LL))(a1 + 30360);
    if ( v39 >= 0 )
      return 1090584577;
  }
  return (unsigned int)v39;
}

```

## disassembly

```asm
0x1800045d0  mov     [rsp+arg_18], r9
0x1800045d5  push    rbx
0x1800045d6  push    r13
0x1800045d8  push    r14
0x1800045da  push    r15
0x1800045dc  sub     rsp, 38h
0x1800045e0  cmp     dword ptr [rcx+0A0F0h], 0
0x1800045e7  mov     ebx, r8d
0x1800045ea  mov     r13, rdx
0x1800045ed  mov     r14, rcx
0x1800045f0  jz      short loc_1800045F9
0x1800045f2  mov     ecx, 1
0x1800045f7  jmp     short loc_180004606
0x1800045f9  mov     rax, [rcx+7690h]
0x180004600  mov     ecx, [rax+88h]
0x180004606  mov     r8, [r14+7690h]
0x18000460d  movsxd  r9, dword ptr [r8+54h]
0x180004611  cmp     r9d, 3
0x180004615  jz      short loc_180004628
0x180004617  mov     eax, 0C1010002h
0x18000461c  add     rsp, 38h
0x180004620  pop     r15
0x180004622  pop     r14
0x180004624  pop     r13
0x180004626  pop     rbx
0x180004627  retn
0x180004628  movsxd  rax, dword ptr [r8+84h]
0x18000462f  mov     r11d, [r14+0A0ECh]
0x180004636  mov     r10d, [r14+0A0E8h]
0x18000463d  mov     [rsp+58h+var_28], rsi
0x180004642  lea     rdx, [rax+rax*2]
0x180004646  add     rdx, r9
0x180004649  lea     r9, __ImageBase
0x180004650  mov     esi, ds:rva dword_180014BB4[r9+rdx*4]
0x180004658  shl     esi, cl
0x18000465a  test    r11d, r11d
0x18000465d  js      short loc_180004665
0x18000465f  lea     ecx, [r11+r10]
0x180004663  jmp     short loc_18000466A
0x180004665  add     esi, esi
0x180004667  mov     ecx, r10d
0x18000466a  sar     esi, cl
0x18000466c  cmp     ebx, esi
0x18000466e  jge     short loc_180004686
0x180004670  mov     rsi, [rsp+58h+var_28]
0x180004675  mov     eax, 0C1010003h
0x18000467a  add     rsp, 38h
0x18000467e  pop     r15
0x180004680  pop     r14
0x180004682  pop     r13
0x180004684  pop     rbx
0x180004685  retn
0x180004686  mov     eax, [r8+58h]
0x18000468a  lea     rbx, [r14+7668h]
0x180004691  mov     edx, [r8+14h]
0x180004695  neg     eax
0x180004697  mov     [rsp+58h+arg_8], rbp
0x18000469c  sbb     ecx, ecx
0x18000469e  mov     [rsp+58h+var_30], rdi
0x1800046a3  and     ecx, 10h
0x1800046a6  mov     [rsp+58h+var_38], r12
0x1800046ab  dec     edx
0x1800046ad  mov     r12d, 20h ; ' '
0x1800046b3  lea     eax, [rcx+20h]
0x1800046b6  add     [r8+20h], eax
0x1800046ba  mov     eax, 0FFFFFFE0h
0x1800046bf  sub     eax, ecx
0x1800046c1  add     [r8+18h], eax
0x1800046c5  mov     eax, [r8+24h]
0x1800046c9  add     eax, 20h ; ' '
0x1800046cc  add     ecx, eax
0x1800046ce  and     edx, ecx
0x1800046d0  mov     [r8+24h], edx
0x1800046d4  lea     rdx, [r14+76D8h]; struct MP3SI *
0x1800046db  mov     rcx, [r14+7690h]; struct CBitStream *
0x1800046e2  mov     r8, rbx; struct MPEG_INFO *
0x1800046e5  mov     eax, [rcx+88h]
0x1800046eb  mov     [rbx], eax
0x1800046ed  mov     eax, [rcx+60h]
0x1800046f0  mov     [r14+766Ch], eax
0x1800046f7  mov     eax, [rcx+94h]
0x1800046fd  mov     [r14+7670h], eax
0x180004704  mov     eax, [rcx+6Ch]
0x180004707  mov     [r14+7674h], eax
0x18000470e  mov     eax, [rcx+70h]
0x180004711  mov     [r14+7678h], eax
0x180004718  mov     eax, 30h ; '0'
0x18000471d  cmp     dword ptr [rcx+58h], 0
0x180004721  cmovz   eax, r12d
0x180004725  mov     [r14+767Ch], eax
0x18000472c  cmp     dword ptr [rcx+84h], 0
0x180004733  setz    al
0x180004736  mov     [r14+7688h], al
0x18000473d  movsxd  rax, dword ptr [rcx+84h]
0x180004744  mov     eax, ds:rva dword_180013900[r9+rax*4]
0x18000474c  mov     [r14+7680h], eax
0x180004753  mov     eax, [rcx+58h]
0x180004756  mov     [r14+7684h], eax
0x18000475d  call    ?mp3SideInfoRead@@YA_NAEAVCBitStream@@AEAUMP3SI@@AEBUMPEG_INFO@@@Z; mp3SideInfoRead(CBitStream &,MP3SI &,MPEG_INFO const &)
0x180004762  mov     r10, [r14+7690h]
0x180004769  lea     rdi, [r14+7698h]
0x180004770  movzx   ecx, byte ptr [rbx+20h]
0x180004774  mov     [rsp+58h+arg_0], al
0x180004778  mov     eax, [rbx+8]
0x18000477b  sub     eax, [rbx+14h]
0x18000477e  cdq
0x18000477f  and     edx, 7
0x180004782  lea     ebp, [rdx+rax]
0x180004785  mov     eax, 11h
0x18000478a  sar     ebp, 3
0x18000478d  cmp     dword ptr [rbx], 1
0x180004790  jnz     short loc_1800047A0
0x180004792  test    cl, cl
0x180004794  mov     edx, 9
0x180004799  cmovz   eax, edx
0x18000479c  sub     ebp, eax
0x18000479e  jmp     short loc_1800047A9
0x1800047a0  test    cl, cl
0x1800047a2  cmovz   r12d, eax
0x1800047a6  sub     ebp, r12d
0x1800047a9  mov     r9d, [rdi+14h]
0x1800047ad  mov     eax, r9d
0x1800047b0  mov     ebx, [rdi+18h]
0x1800047b3  sub     eax, ebx
0x1800047b5  mov     r12, [rsp+58h+var_38]
0x1800047ba  cdq
0x1800047bb  and     edx, 7
0x1800047be  add     eax, edx
0x1800047c0  sar     eax, 3
0x1800047c3  cmp     eax, ebp
0x1800047c5  jge     short loc_1800047F1
0x1800047c7  mov     r8d, ebp
0x1800047ca  sub     r8d, eax
0x1800047cd  shl     r8d, 3
0x1800047d1  test    r8d, r8d
0x1800047d4  jle     short loc_1800047F1
0x1800047d6  mov     ecx, [rdi+24h]
0x1800047d9  mov     eax, ebx
0x1800047db  add     [rdi+20h], r8d
0x1800047df  sub     eax, r8d
0x1800047e2  mov     [rdi+18h], eax
0x1800047e5  add     ecx, r8d
0x1800047e8  lea     eax, [r9-1]
0x1800047ec  and     ecx, eax
0x1800047ee  mov     [rdi+24h], ecx
0x1800047f1  mov     r8d, ebp; int
0x1800047f4  mov     rdx, r10; struct CBitStream *
0x1800047f7  mov     rcx, rdi; this
0x1800047fa  call    ?Fill@CBitStream@@QEAAHAEAV1@H@Z; CBitStream::Fill(CBitStream &,int)
0x1800047ff  cmp     eax, ebp
0x180004801  jnz     short loc_180004878
0x180004803  sar     ebx, 3
0x180004806  cmp     ebx, [r14+76D8h]
0x18000480d  jl      short loc_180004878
0x18000480f  mov     edx, [rdi+18h]
0x180004812  test    edx, edx
0x180004814  jle     short loc_180004831
0x180004816  mov     ecx, [rdi+24h]
0x180004819  mov     eax, [rdi+14h]
0x18000481c  add     ecx, edx
0x18000481e  add     [rdi+20h], edx
0x180004821  dec     eax
0x180004823  and     ecx, eax
0x180004825  mov     dword ptr [rdi+18h], 0
0x18000482c  mov     [rdi+24h], ecx
0x18000482f  xor     edx, edx
0x180004831  mov     eax, [r14+76D8h]
0x180004838  add     eax, ebp
0x18000483a  lea     r8d, ds:0[rax*8]
0x180004842  test    r8d, r8d
0x180004845  jle     short loc_180004862
0x180004847  mov     ecx, [rdi+24h]
0x18000484a  lea     eax, [rdx+r8]
0x18000484e  sub     [rdi+20h], r8d
0x180004852  sub     ecx, r8d
0x180004855  mov     [rdi+18h], eax
0x180004858  mov     eax, [rdi+14h]
0x18000485b  dec     eax
0x18000485d  and     ecx, eax
0x18000485f  mov     [rdi+24h], ecx
0x180004862  movzx   ebp, [rsp+58h+arg_0]
0x180004867  mov     rdx, r13
0x18000486a  movzx   r8d, bpl
0x18000486e  mov     rcx, r14
0x180004871  call    ?DecodeNormal@CMp3Decode@@IEAA?AW4SSC@@PEAE_N@Z; CMp3Decode::DecodeNormal(uchar *,bool)
0x180004876  jmp     short loc_180004888
0x180004878  mov     rdx, r13
0x18000487b  mov     rcx, r14
0x18000487e  call    ?DecodeOnNoMainData@CMp3Decode@@IEAA?AW4SSC@@PEAE@Z; CMp3Decode::DecodeOnNoMainData(uchar *)
0x180004883  movzx   ebp, [rsp+58h+arg_0]
0x180004888  mov     r8, [r14+7690h]
0x18000488f  mov     ebx, eax
0x180004891  mov     eax, [r8+94h]
0x180004898  mov     edx, eax
0x18000489a  sub     edx, [r8+20h]
0x18000489e  mov     [r8+20h], eax
0x1800048a2  mov     eax, [r8+24h]
0x1800048a6  mov     ecx, [r8+14h]
0x1800048aa  add     eax, edx
0x1800048ac  sub     [r8+18h], edx
0x1800048b0  dec     ecx
0x1800048b2  and     ecx, eax
0x1800048b4  mov     rax, [rsp+58h+arg_18]
0x1800048b9  mov     [r8+24h], ecx
0x1800048bd  test    rax, rax
0x1800048c0  jz      short loc_1800048C8
0x1800048c2  test    ebx, ebx
0x1800048c4  js      short loc_1800048C8
0x1800048c6  mov     [rax], esi
0x1800048c8  test    bpl, bpl
0x1800048cb  mov     rbp, [rsp+58h+arg_8]
0x1800048d0  jnz     short loc_1800048ED
0x1800048d2  mov     rax, [rdi]
0x1800048d5  mov     rcx, rdi
0x1800048d8  mov     rax, [rax+8]
0x1800048dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e1  bt      ebx, 1Fh
0x1800048e5  mov     eax, 41010001h
0x1800048ea  cmovnb  ebx, eax
0x1800048ed  mov     rdi, [rsp+58h+var_30]
0x1800048f2  mov     eax, ebx
0x1800048f4  mov     rsi, [rsp+58h+var_28]
0x1800048f9  add     rsp, 38h
0x1800048fd  pop     r15
0x1800048ff  pop     r14
0x180004901  pop     r13
0x180004903  pop     rbx
0x180004904  retn
```
