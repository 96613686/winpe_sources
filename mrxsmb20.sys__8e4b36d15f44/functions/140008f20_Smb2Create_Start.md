# Smb2Create_Start

- ea: `0x140008f20`
- end: `0x1400095c3`
- name: `Smb2Create_Start`
- size: `1699`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140008f20`
- `0x1400095d0`
- `0x14000a570`
- `0x140023010`
- `0x1400372c0`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140009428`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140009461`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140009428`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140009461`
- `rdbss!RxFreeMdl` at `0x140009349`
- `rdbss!RxFreeMdl` at `0x140009358`
- `rdbss!RxFreeMdl` at `0x140009349`
- `rdbss!RxFreeMdl` at `0x140009358`
- `rdbss!RxAllocateMdl2` at `0x1400093ca`
- `rdbss!RxAllocateMdl2` at `0x14000944a`
- `rdbss!RxAllocateMdl2` at `0x1400093ca`
- `rdbss!RxAllocateMdl2` at `0x14000944a`
- `mrxsmb!SmbCeAllocateExchangeBuffer` at `0x140009023`
- `mrxsmb!SmbCeAllocateExchangeBuffer` at `0x140009023`
- `mrxsmb!MRxSmbIsStreamFile` at `0x1400092be`
- `mrxsmb!MRxSmbIsStreamFile` at `0x1400092be`
- `mrxsmb!RDR_PERF_ENTER` at `0x140008f80`
- `mrxsmb!RDR_PERF_ENTER` at `0x140008f80`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x1400094d2`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x1400094d2`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x1400094a5`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x1400094a5`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140009195`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140009195`

## pseudocode

```c
__int64 __fastcall Smb2Create_Start(__int64 a1, __int64 a2)
{
  __int64 v2; // rbp
  __int64 v4; // rbx
  struct _MDL *v5; // r12
  struct _MDL *v6; // r13
  _DWORD *v7; // rdi
  int v8; // r15d
  unsigned int v9; // r14d
  int ContextsToRequest; // ebx
  int v11; // ecx
  __int64 ExchangeBuffer; // rax
  _DWORD *v13; // rdi
  unsigned int v14; // r15d
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  _WORD *v18; // rdx
  char v19; // al
  unsigned int v20; // edx
  __int64 v21; // r8
  char v22; // cl
  int v23; // r14d
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // edx
  __int64 v28; // rcx
  _DWORD *v29; // rcx
  int v30; // edx
  int v31; // eax
  unsigned int v32; // r14d
  unsigned int v34; // eax
  unsigned int v35; // ebx
  struct _MDL *Mdl2; // rax
  bool v37; // zf
  struct _MDL *v38; // rax
  __int16 v39; // ax
  __int64 v40; // [rsp+50h] [rbp-68h]
  _DWORD *v41; // [rsp+58h] [rbp-60h]
  __int64 v42; // [rsp+60h] [rbp-58h]
  __int64 v43; // [rsp+68h] [rbp-50h]
  unsigned int v44; // [rsp+C0h] [rbp+8h]
  int v45; // [rsp+C0h] [rbp+8h]
  int v46; // [rsp+C8h] [rbp+10h] BYREF
  unsigned int v47; // [rsp+D0h] [rbp+18h]
  _DWORD *v48; // [rsp+D8h] [rbp+20h]

  v2 = *(_QWORD *)(a1 + 48);
  v4 = *(_QWORD *)(a1 + 80);
  v5 = 0;
  LOBYTE(a2) = 15;
  v6 = 0;
  v7 = *(_DWORD **)(*(_QWORD *)(v2 + 72) + 48LL);
  v42 = *(_QWORD *)(a1 + 72);
  v8 = v7[2];
  v41 = v7;
  v40 = *(_QWORD *)(v2 + 56);
  v9 = *(unsigned __int16 *)(v40 + 360);
  v44 = v9;
  v46 = 0;
  RDR_PERF_ENTER(a1 + 512, a2);
  *(_WORD *)(a1 + 2408) = 0;
  ContextsToRequest = Smb2ValidateSrvOpenRestrictions(v2, v7, v4, a1);
  if ( ContextsToRequest < 0 )
    goto LABEL_45;
  v7[11] = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 264LL);
  v11 = *(_DWORD *)(v2 + 512) | 0x80;
  v7[12] = v11;
  *(_DWORD *)(*(_QWORD *)(v2 + 72) + 120LL) = v11;
  v7[13] = *(_DWORD *)(v2 + 532);
  v46 = 0;
  ContextsToRequest = Smb2AddCreateContextsToRequest(v2, 0, (unsigned int *)&v46, 0);
  if ( (int)(ContextsToRequest + 0x80000000) >= 0 && ContextsToRequest != -1073741789 )
    goto LABEL_45;
  v47 = v9 + v46 + 216;
  ExchangeBuffer = SmbCeAllocateExchangeBuffer(a1);
  v43 = ExchangeBuffer;
  if ( !ExchangeBuffer )
  {
LABEL_52:
    ContextsToRequest = -1073741670;
LABEL_45:
    RxFreeMdl(v5);
    RxFreeMdl(v6);
    return (unsigned int)ContextsToRequest;
  }
  v13 = (_DWORD *)(ExchangeBuffer + 32);
  LODWORD(v48) = v8 & 4;
  if ( *(_QWORD *)(v2 + 560) == 4282664531LL )
    _InterlockedOr((volatile signed __int32 *)(a1 + 68), 0x8000u);
  v14 = 121;
  memset(v13, 0, 0x79u);
  v15 = *(_QWORD *)(a1 + 72);
  v16 = *(_QWORD *)(a1 + 80);
  v17 = *(_QWORD *)(a1 + 88);
  *v13 = 1112364030;
  v13[8] = 65279;
  *((_WORD *)v13 + 2) = 64;
  if ( *(char *)(v15 + 736) < 0 )
    v13[4] = (16 * *(_BYTE *)(a1 + 33) + 16) & 0x70;
  *((_WORD *)v13 + 7) = 1;
  if ( v16 )
  {
    *((_QWORD *)v13 + 5) = *(_QWORD *)(v16 + 440);
    if ( (*(_DWORD *)(v15 + 716) & 0x3000) != 0 )
      *((_WORD *)v13 + 4) = *(_WORD *)(v15 + 700);
  }
  if ( v17 )
  {
    v13[9] = *(_DWORD *)(v17 + 436);
    if ( (*(_DWORD *)(*(_QWORD *)(v17 + 424) + 176LL) & 2) != 0 && (*(_DWORD *)(a1 + 68) & 0x8000) != 0 )
      v13[4] |= 0x10000000u;
  }
  if ( (*(_DWORD *)(v15 + 716) & 0x3000) != 0 && (*(_DWORD *)(a1 + 68) & 0x4000) != 0 )
    v13[4] |= 0x20000000u;
  *((_WORD *)v13 + 6) = 5;
  *((_WORD *)v13 + 32) = 57;
  *((_WORD *)v13 + 54) = 120;
  if ( v9 )
  {
    v18 = *(_WORD **)(v40 + 368);
    if ( *v18 == 92 )
    {
      ++v18;
      v9 -= 2;
      v44 = v9;
    }
    memmove(v13 + 30, v18, v9);
  }
  if ( (*(_BYTE *)(v2 + 746) & 0x10) != 0 )
  {
    StripSnapshotDesignationFromName(v13 + 30);
    v9 = v44;
  }
  *((_WORD *)v13 + 55) = v9;
  if ( v9 )
    v14 = v9 + 120;
  v13[22] = v41[12];
  v13[24] = v41[13];
  v19 = SmbCeCheckServerEntryDialect(v42, 3, 0, 0);
  v20 = *(_DWORD *)(v2 + 528);
  if ( !v19 )
    v20 = *(_DWORD *)(v2 + 528) & 0xFFFD7FFF;
  v13[23] = v20;
  v13[25] = *(_DWORD *)(v2 + 536);
  v13[26] = *(_DWORD *)(v2 + 540);
  v13[17] = *(_DWORD *)(v2 + 552);
  *((_BYTE *)v13 + 66) = 0;
  *((_QWORD *)v13 + 10) = 0;
  *((_QWORD *)v13 + 14) = 0;
  if ( (_DWORD)v48 )
  {
    v22 = *((_BYTE *)v41 + 24);
    goto LABEL_42;
  }
  v21 = *(_QWORD *)(v2 + 72);
  v22 = 0;
  v23 = 0;
  LOBYTE(v45) = 0;
  if ( (*(_DWORD *)(v21 + 72) & 0x200) != 0 )
    goto LABEL_40;
  v24 = *(_QWORD *)(v2 + 56);
  v25 = *(_QWORD *)(v24 + 120);
  if ( (*(_DWORD *)(*(_QWORD *)(v25 + 32) + 96LL) & 0x80u) != 0 )
    goto LABEL_39;
  if ( *(_BYTE *)(v25 + 77) )
    goto LABEL_39;
  v26 = *(_QWORD *)(v2 + 672);
  if ( v26 )
  {
    if ( (*(_DWORD *)(v26 + 12) & 4) != 0 )
      goto LABEL_39;
  }
  v27 = *(_DWORD *)(v2 + 512);
  if ( (v27 & 0xFFEFFF7F) == 0 )
    goto LABEL_39;
  v28 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v21 + 40) + 40LL) + 424LL) + 88LL);
  if ( (*(_DWORD *)(v2 + 540) & 1) != 0 )
  {
    v37 = (*(_DWORD *)(v28 + 716) & 0x4000) == 0;
    v48 = (_DWORD *)(v28 + 716);
    if ( v37 )
      goto LABEL_39;
    v23 = (v27 & 1) != 0 ? 0x29 : 0;
    goto LABEL_36;
  }
  v29 = (_DWORD *)(v28 + 716);
  v30 = *(_DWORD *)(v2 + 512) & 0x23;
  v48 = v29;
  if ( (*v29 & 0x20) != 0 )
  {
    v48 = v29;
    v23 = v30 != 0 ? 0x2F : 0;
LABEL_36:
    v31 = 255;
    goto LABEL_37;
  }
  if ( !v30 )
    goto LABEL_39;
  v39 = *(_WORD *)(v2 + 746);
  if ( (v39 & 0x800) != 0 )
  {
    v22 = 0;
    goto LABEL_40;
  }
  v23 = 9;
  if ( (v39 & 0x400) == 0 )
  {
    v45 = 9;
    v23 = 31;
    v48 = v29;
    goto LABEL_38;
  }
  v31 = 1;
LABEL_37:
  v45 = v31;
LABEL_38:
  if ( !(unsigned __int8)MRxSmbIsStreamFile(v24 + 360, 0) )
  {
LABEL_39:
    v22 = v45;
    goto LABEL_40;
  }
  if ( (*v48 & 0x4000) != 0 && (v22 = v45, v45 == 255) )
  {
    v23 &= ~0x20u;
  }
  else
  {
    v22 = 0;
    v23 = 0;
  }
LABEL_40:
  if ( v2 != -732 )
    *(_DWORD *)(v2 + 732) = v23;
LABEL_42:
  *((_BYTE *)v13 + 67) = v22;
  if ( v46 )
  {
    memset((char *)v13 + v14, 0, ((v14 + 7) & 0xFFFFFFF8) - v14);
    v14 = (v14 + 7) & 0xFFFFFFF8;
  }
  v32 = v47;
  v46 = v47 - v14 - 32;
  ContextsToRequest = Smb2AddCreateContextsToRequest(v2, (__int64)v13 + v14, (unsigned int *)&v46, (_WORD *)(a1 + 2408));
  if ( ContextsToRequest < 0 )
    goto LABEL_45;
  v34 = v46;
  if ( v46 )
  {
    v13[28] = v14;
    v13[29] = v46;
    v34 = v46;
  }
  v35 = v14 + v34;
  Mdl2 = (struct _MDL *)RxAllocateMdl2(v13, v14 + v34, 0, 0, 0);
  v5 = Mdl2;
  if ( !Mdl2 )
    goto LABEL_52;
  if ( Mdl2->ByteOffset >= 0x20 )
    Mdl2->MdlFlags |= 0x1000u;
  MmBuildMdlForNonPagedPool(Mdl2);
  v38 = (struct _MDL *)RxAllocateMdl2(v43, v32, 0, 0, 0);
  v6 = v38;
  if ( !v38 )
    goto LABEL_52;
  MmBuildMdlForNonPagedPool(v38);
  ContextsToRequest = SmbCseInitializeBufferContextWithMemoryRegistration(a1 + 1024, a1, v5, v35, v6, v47, 0, 0, 0, 4);
  if ( !ContextsToRequest )
  {
    *(_QWORD *)(a1 + 1112) = v13;
    *(_QWORD *)(a1 + 1736) = v43;
    v5 = 0;
    v6 = 0;
    ContextsToRequest = SmbCseSubmitBufferContext(a1 + 1024);
  }
  if ( ContextsToRequest < 0 )
    goto LABEL_45;
  return (unsigned int)ContextsToRequest;
}

```

## disassembly

```asm
0x140008f20  mov     r11, rsp
0x140008f23  push    rbx
0x140008f24  push    rbp
0x140008f25  push    rsi
0x140008f26  push    rdi
0x140008f27  push    r12
0x140008f29  push    r13
0x140008f2b  push    r14
0x140008f2d  push    r15
0x140008f2f  sub     rsp, 78h
0x140008f33  mov     rbp, [rcx+30h]
0x140008f37  mov     rsi, rcx
0x140008f3a  mov     rbx, [rcx+50h]
0x140008f3e  xor     r12d, r12d
0x140008f41  mov     dl, 0Fh
0x140008f43  xor     r13d, r13d
0x140008f46  mov     rax, [rbp+48h]
0x140008f4a  mov     rdi, [rax+30h]
0x140008f4e  mov     rax, [rcx+48h]
0x140008f52  add     rcx, 200h
0x140008f59  mov     [rsp+0B8h+var_58], rax
0x140008f5e  mov     rax, [rbp+38h]
0x140008f62  mov     r15d, [rdi+8]
0x140008f66  mov     [rsp+0B8h+var_60], rdi
0x140008f6b  mov     [rsp+0B8h+var_68], rax
0x140008f70  movzx   r14d, word ptr [rax+168h]
0x140008f78  mov     [r11+8], r14d
0x140008f7c  mov     [r11+10h], r12d
0x140008f80  call    cs:__imp_RDR_PERF_ENTER
0x140008f87  nop     dword ptr [rax+rax+00h]
0x140008f8c  xor     eax, eax
0x140008f8e  mov     r9, rsi
0x140008f91  mov     r8, rbx
0x140008f94  mov     [rsi+968h], ax
0x140008f9b  mov     rdx, rdi
0x140008f9e  mov     rcx, rbp
0x140008fa1  call    Smb2ValidateSrvOpenRestrictions
0x140008fa6  mov     ebx, eax
0x140008fa8  test    eax, eax
0x140008faa  js      loc_140009346
0x140008fb0  mov     rax, [rsi+58h]
0x140008fb4  lea     r8, [rsp+0B8h+arg_8]
0x140008fbc  xor     r9d, r9d
0x140008fbf  xor     edx, edx
0x140008fc1  mov     ecx, [rax+108h]
0x140008fc7  mov     [rdi+2Ch], ecx
0x140008fca  mov     ecx, [rbp+200h]
0x140008fd0  bts     ecx, 7
0x140008fd4  mov     [rdi+30h], ecx
0x140008fd7  mov     rax, [rbp+48h]
0x140008fdb  mov     [rax+78h], ecx
0x140008fde  mov     rcx, rbp
0x140008fe1  mov     eax, [rbp+214h]
0x140008fe7  mov     [rdi+34h], eax
0x140008fea  mov     [rsp+0B8h+arg_8], r12d
0x140008ff2  call    Smb2AddCreateContextsToRequest
0x140008ff7  mov     ecx, 80000000h
0x140008ffc  mov     ebx, eax
0x140008ffe  add     eax, ecx
0x140009000  test    ecx, eax
0x140009002  jz      loc_140009385
0x140009008  mov     eax, [rsp+0B8h+arg_8]
0x14000900f  mov     rcx, rsi
0x140009012  add     eax, 0D8h
0x140009017  add     eax, r14d
0x14000901a  mov     edx, eax
0x14000901c  mov     [rsp+0B8h+arg_10], eax
0x140009023  call    cs:__imp_SmbCeAllocateExchangeBuffer
0x14000902a  nop     dword ptr [rax+rax+00h]
0x14000902f  mov     [rsp+0B8h+var_50], rax
0x140009034  test    rax, rax
0x140009037  jz      loc_1400093DE
0x14000903d  and     r15d, 4
0x140009041  lea     rdi, [rax+20h]
0x140009045  mov     eax, 0FF444653h
0x14000904a  mov     dword ptr [rsp+0B8h+arg_18], r15d
0x140009052  cmp     [rbp+230h], rax
0x140009059  jz      loc_140009378
0x14000905f  mov     r15d, 79h ; 'y'
0x140009065  xor     edx, edx; Val
0x140009067  mov     r8d, r15d; Size
0x14000906a  mov     rcx, rdi; void *
0x14000906d  call    memset
0x140009072  mov     rdx, [rsi+48h]
0x140009076  mov     r8, [rsi+50h]
0x14000907a  mov     rcx, [rsi+58h]
0x14000907e  mov     dword ptr [rdi], 424D53FEh
0x140009084  mov     dword ptr [rdi+20h], 0FEFFh
0x14000908b  mov     word ptr [rdi+4], 40h ; '@'
0x140009091  cmp     [rdx+2E0h], r12b
0x140009098  jge     short loc_1400090AA
0x14000909a  movzx   eax, byte ptr [rsi+21h]
0x14000909e  shl     eax, 4
0x1400090a1  add     eax, 10h
0x1400090a4  and     eax, 70h
0x1400090a7  mov     [rdi+10h], eax
0x1400090aa  mov     word ptr [rdi+0Eh], 1
0x1400090b0  test    r8, r8
0x1400090b3  jz      short loc_1400090D7
0x1400090b5  mov     rax, [r8+1B8h]
0x1400090bc  mov     [rdi+28h], rax
0x1400090c0  test    dword ptr [rdx+2CCh], 3000h
0x1400090ca  jz      short loc_1400090D7
0x1400090cc  movzx   eax, word ptr [rdx+2BCh]
0x1400090d3  mov     [rdi+8], ax
0x1400090d7  test    rcx, rcx
0x1400090da  jz      short loc_1400090FB
0x1400090dc  mov     eax, [rcx+1B4h]
0x1400090e2  mov     [rdi+24h], eax
0x1400090e5  mov     rax, [rcx+1A8h]
0x1400090ec  mov     ecx, [rax+0B0h]
0x1400090f2  test    cl, 2
0x1400090f5  jnz     loc_140009533
0x1400090fb  test    dword ptr [rdx+2CCh], 3000h
0x140009105  jz      short loc_140009114
0x140009107  mov     eax, [rsi+44h]
0x14000910a  bt      eax, 0Eh
0x14000910e  jb      loc_14000954C
0x140009114  mov     word ptr [rdi+0Ch], 5
0x14000911a  mov     word ptr [rdi+40h], 39h ; '9'
0x140009120  mov     word ptr [rdi+6Ch], 78h ; 'x'
0x140009126  test    r14d, r14d
0x140009129  jz      short loc_140009159
0x14000912b  mov     rdx, [rsp+0B8h+var_68]
0x140009130  mov     rdx, [rdx+170h]
0x140009137  cmp     word ptr [rdx], 5Ch ; '\'
0x14000913b  jnz     short loc_14000914D
0x14000913d  add     rdx, 2; Src
0x140009141  add     r14d, 0FFFFFFFEh
0x140009145  mov     [rsp+0B8h+arg_0], r14d
0x14000914d  mov     r8d, r14d; Size
0x140009150  lea     rcx, [rdi+78h]; void *
0x140009154  call    memmove
0x140009159  test    byte ptr [rbp+2EAh], 10h
0x140009160  jnz     loc_140009593
0x140009166  mov     [rdi+6Eh], r14w
0x14000916b  test    r14d, r14d
0x14000916e  jz      short loc_140009174
0x140009170  lea     r15d, [r14+78h]
0x140009174  mov     rbx, [rsp+0B8h+var_60]
0x140009179  xor     r9d, r9d
0x14000917c  mov     rcx, [rsp+0B8h+var_58]
0x140009181  xor     r8d, r8d
0x140009184  mov     edx, 3
0x140009189  mov     eax, [rbx+30h]
0x14000918c  mov     [rdi+58h], eax
0x14000918f  mov     eax, [rbx+34h]
0x140009192  mov     [rdi+60h], eax
0x140009195  call    cs:__imp_SmbCeCheckServerEntryDialect
0x14000919c  nop     dword ptr [rax+rax+00h]
0x1400091a1  mov     edx, [rbp+210h]
0x1400091a7  mov     ecx, edx
0x1400091a9  and     ecx, 0FFFD7FFFh
0x1400091af  test    al, al
0x1400091b1  cmovz   edx, ecx
0x1400091b4  xor     r10d, r10d
0x1400091b7  mov     [rdi+5Ch], edx
0x1400091ba  mov     eax, [rbp+218h]
0x1400091c0  mov     [rdi+64h], eax
0x1400091c3  mov     eax, [rbp+21Ch]
0x1400091c9  mov     [rdi+68h], eax
0x1400091cc  mov     eax, [rbp+228h]
0x1400091d2  mov     [rdi+44h], eax
0x1400091d5  mov     [rdi+42h], r12b
0x1400091d9  mov     [rdi+50h], r10
0x1400091dd  mov     [rdi+70h], r10
0x1400091e1  cmp     dword ptr [rsp+0B8h+arg_18], r10d
0x1400091e9  jnz     loc_140009580
0x1400091ef  mov     r8, [rbp+48h]
0x1400091f3  lea     rbx, [rbp+2DCh]
0x1400091fa  mov     ecx, r10d
0x1400091fd  mov     r14d, r10d
0x140009200  mov     [rsp+0B8h+arg_0], ecx
0x140009207  test    dword ptr [r8+48h], 200h
0x14000920f  jnz     loc_1400092D9
0x140009215  mov     r9, [rbp+38h]
0x140009219  mov     rdx, [r9+78h]
0x14000921d  mov     rax, [rdx+20h]
0x140009221  mov     ecx, [rax+60h]
0x140009224  test    cl, cl
0x140009226  js      loc_1400092D2
0x14000922c  cmp     [rdx+4Dh], r10b
0x140009230  jnz     loc_1400092D2
0x140009236  mov     rax, [rbp+2A0h]
0x14000923d  test    rax, rax
0x140009240  jz      short loc_14000924D
0x140009242  mov     eax, [rax+0Ch]
0x140009245  test    al, 4
0x140009247  jnz     loc_1400092D2
0x14000924d  mov     edx, [rbp+200h]
0x140009253  test    edx, 0FFEFFF7Fh
0x140009259  jz      short loc_1400092D2
0x14000925b  mov     rax, [r8+28h]
0x14000925f  mov     rcx, [rax+28h]
0x140009263  mov     rax, [rcx+1A8h]
0x14000926a  mov     rcx, [rax+58h]
0x14000926e  mov     eax, [rbp+21Ch]
0x140009274  test    al, 1
0x140009276  jnz     loc_1400093E8
0x14000927c  add     rcx, 2CCh
0x140009283  and     edx, 23h
0x140009286  mov     [rsp+0B8h+arg_18], rcx
0x14000928e  mov     eax, [rcx]
0x140009290  test    al, 20h
0x140009292  jz      loc_1400094ED
0x140009298  neg     edx
0x14000929a  mov     [rsp+0B8h+arg_18], rcx
0x1400092a2  sbb     r14d, r14d
0x1400092a5  and     r14d, 2Fh
0x1400092a9  mov     eax, 0FFh
0x1400092ae  mov     [rsp+0B8h+arg_0], eax
0x1400092b5  lea     rcx, [r9+168h]
0x1400092bc  xor     edx, edx
0x1400092be  call    cs:__imp_MRxSmbIsStreamFile
0x1400092c5  nop     dword ptr [rax+rax+00h]
0x1400092ca  test    al, al
0x1400092cc  jnz     loc_140009558
0x1400092d2  mov     ecx, [rsp+0B8h+arg_0]
0x1400092d9  test    rbx, rbx
0x1400092dc  jz      short loc_1400092E1
0x1400092de  mov     [rbx], r14d
0x1400092e1  mov     [rdi+43h], cl
0x1400092e4  cmp     [rsp+0B8h+arg_8], r12d
0x1400092ec  jz      short loc_14000930B
0x1400092ee  lea     ebx, [r15+7]
0x1400092f2  mov     ecx, r15d
0x1400092f5  and     ebx, 0FFFFFFF8h
0x1400092f8  add     rcx, rdi; void *
0x1400092fb  mov     r8d, ebx
0x1400092fe  xor     edx, edx; Val
0x140009300  sub     r8d, r15d; Size
0x140009303  call    memset
0x140009308  mov     r15d, ebx
0x14000930b  mov     r14d, [rsp+0B8h+arg_10]
0x140009313  lea     r9, [rsi+968h]
0x14000931a  mov     eax, r14d
0x14000931d  mov     edx, r15d
0x140009320  sub     eax, r15d
0x140009323  lea     r8, [rsp+0B8h+arg_8]
0x14000932b  sub     eax, 20h ; ' '
0x14000932e  add     rdx, rdi
0x140009331  mov     rcx, rbp
0x140009334  mov     [rsp+0B8h+arg_8], eax
0x14000933b  call    Smb2AddCreateContextsToRequest
0x140009340  mov     ebx, eax
0x140009342  test    eax, eax
0x140009344  jns     short loc_140009393
0x140009346  mov     rcx, r12
0x140009349  call    cs:__imp_RxFreeMdl
0x140009350  nop     dword ptr [rax+rax+00h]
0x140009355  mov     rcx, r13
0x140009358  call    cs:__imp_RxFreeMdl
0x14000935f  nop     dword ptr [rax+rax+00h]
0x140009364  mov     eax, ebx
0x140009366  add     rsp, 78h
0x14000936a  pop     r15
0x14000936c  pop     r14
0x14000936e  pop     r13
0x140009370  pop     r12
0x140009372  pop     rdi
0x140009373  pop     rsi
0x140009374  pop     rbp
0x140009375  pop     rbx
0x140009376  retn
0x140009378  lock or dword ptr [rsi+44h], 8000h
0x140009380  jmp     loc_14000905F
0x140009385  cmp     ebx, 0C0000023h
0x14000938b  jz      loc_140009008
0x140009391  jmp     short loc_140009346
0x140009393  mov     eax, [rsp+0B8h+arg_8]
0x14000939a  test    eax, eax
0x14000939c  jz      short loc_1400093B3
0x14000939e  mov     [rdi+70h], r15d
0x1400093a2  mov     eax, [rsp+0B8h+arg_8]
0x1400093a9  mov     [rdi+74h], eax
0x1400093ac  mov     eax, [rsp+0B8h+arg_8]
0x1400093b3  lea     ebx, [r15+rax]
0x1400093b7  xor     r9d, r9d
0x1400093ba  xor     r15d, r15d
0x1400093bd  mov     edx, ebx
0x1400093bf  xor     r8d, r8d
0x1400093c2  mov     [rsp+0B8h+var_98], r15
0x1400093c7  mov     rcx, rdi
0x1400093ca  call    cs:__imp_RxAllocateMdl2
0x1400093d1  nop     dword ptr [rax+rax+00h]
0x1400093d6  mov     r12, rax
0x1400093d9  test    rax, rax
0x1400093dc  jnz     short loc_140009414
0x1400093de  mov     ebx, 0C000009Ah
0x1400093e3  jmp     loc_140009346
0x1400093e8  lea     rax, [rcx+2CCh]
0x1400093ef  test    dword ptr [rax], 4000h
0x1400093f5  mov     [rsp+0B8h+arg_18], rax
0x1400093fd  jz      loc_1400092D2
0x140009403  and     dl, 1
0x140009406  neg     dl
0x140009408  sbb     r14d, r14d
0x14000940b  and     r14d, 29h
0x14000940f  jmp     loc_1400092A9
0x140009414  cmp     dword ptr [rax+2Ch], 20h ; ' '
  ... truncated ...
```
