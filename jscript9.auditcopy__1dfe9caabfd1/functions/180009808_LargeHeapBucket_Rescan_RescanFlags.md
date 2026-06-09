# LargeHeapBucket::Rescan(RescanFlags)

- ea: `0x180009808`
- end: `0x180009a67`
- name: `?Rescan@LargeHeapBucket@@QEAAIW4RescanFlags@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a02c`

## callees

- `0x180009724`
- `0x180009808`
- `0x180009a70`
- `0x180009c6c`

## import_xrefs

- `KERNEL32!ResetWriteWatch` at `0x1800098b9`
- `KERNEL32!ResetWriteWatch` at `0x18000994a`
- `KERNEL32!ResetWriteWatch` at `0x1800099dd`
- `KERNEL32!ResetWriteWatch` at `0x1800098b9`
- `KERNEL32!ResetWriteWatch` at `0x18000994a`
- `KERNEL32!ResetWriteWatch` at `0x1800099dd`

## pseudocode

```c
__int64 __fastcall LargeHeapBucket::Rescan(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  int v4; // r15d
  _QWORD *v6; // r12
  __int64 v7; // rbx
  int v8; // r14d
  struct Recycler *v9; // rsi
  int v10; // eax
  DWORD v11; // r8d
  __int64 v12; // rbx
  int v13; // edi
  int v14; // eax
  DWORD v15; // r8d
  __int64 v16; // rbx
  int v17; // r15d
  int v18; // edi
  int v19; // eax
  DWORD v20; // r8d
  unsigned int v21; // ebx

  v4 = 0;
  v6 = (_QWORD *)a1;
  v7 = *(_QWORD *)(a1 + 24);
  v8 = a2 & 1;
  v9 = *(struct Recycler **)(*(_QWORD *)a1 + 56LL);
  while ( v7 )
  {
    *(_DWORD *)(v7 + 120) = *(_DWORD *)(v7 + 40);
    if ( v8 )
    {
      *(_BYTE *)(v7 + 132) = 0;
    }
    else if ( *(_BYTE *)(v7 + 132) )
    {
      if ( (a2 & 2) != 0 )
        ResetWriteWatch(*(LPVOID *)(v7 + 8), 0x1000u);
      v10 = 1;
      goto LABEL_3;
    }
    if ( !*(_DWORD *)(v7 + 124) )
      goto LABEL_11;
    v11 = (a2 >> 1) & 1;
    if ( *(_QWORD *)(v7 + 32) != 1 )
    {
      if ( *(_DWORD *)v9 == 57345 || (*(_DWORD *)v9 & 0x2001) != 0x2001 )
      {
        v10 = LargeHeapBlock::RescanMultiPage((LargeHeapBlock *)v7, v9, v11);
        goto LABEL_3;
      }
LABEL_11:
      v10 = 0;
      goto LABEL_3;
    }
    v10 = (unsigned __int8)LargeHeapBlock::RescanOnePage((LargeHeapBlock *)v7, v9, v11);
LABEL_3:
    v7 = *(_QWORD *)(v7 + 64);
    v4 += v10;
  }
  v12 = v6[2];
  v13 = 0;
  while ( v12 )
  {
    *(_DWORD *)(v12 + 120) = *(_DWORD *)(v12 + 40);
    if ( v8 )
    {
      *(_BYTE *)(v12 + 132) = 0;
    }
    else if ( *(_BYTE *)(v12 + 132) )
    {
      if ( (a2 & 2) != 0 )
        ResetWriteWatch(*(LPVOID *)(v12 + 8), 0x1000u);
      v14 = 1;
      goto LABEL_18;
    }
    if ( !*(_DWORD *)(v12 + 124) )
      goto LABEL_26;
    v15 = (a2 >> 1) & 1;
    if ( *(_QWORD *)(v12 + 32) != 1 )
    {
      if ( *(_DWORD *)v9 == 57345 || (*(_DWORD *)v9 & 0x2001) != 0x2001 )
      {
        v14 = LargeHeapBlock::RescanMultiPage((LargeHeapBlock *)v12, v9, v15);
        goto LABEL_18;
      }
LABEL_26:
      v14 = 0;
      goto LABEL_18;
    }
    v14 = (unsigned __int8)LargeHeapBlock::RescanOnePage((LargeHeapBlock *)v12, v9, v15);
LABEL_18:
    v12 = *(_QWORD *)(v12 + 64);
    v13 += v14;
  }
  v16 = v6[4];
  v17 = v13 + v4;
  v18 = 0;
  while ( v16 )
  {
    *(_DWORD *)(v16 + 120) = *(_DWORD *)(v16 + 40);
    if ( v8 )
    {
      *(_BYTE *)(v16 + 132) = 0;
    }
    else if ( *(_BYTE *)(v16 + 132) )
    {
      if ( (a2 & 2) != 0 )
        ResetWriteWatch(*(LPVOID *)(v16 + 8), 0x1000u);
      v19 = 1;
      goto LABEL_33;
    }
    if ( !*(_DWORD *)(v16 + 124) )
      goto LABEL_41;
    v20 = (a2 >> 1) & 1;
    if ( *(_QWORD *)(v16 + 32) != 1 )
    {
      if ( *(_DWORD *)v9 == 57345 || (a1 = 8193, (*(_DWORD *)v9 & 0x2001) != 0x2001) )
      {
        v19 = LargeHeapBlock::RescanMultiPage((LargeHeapBlock *)v16, v9, v20);
        goto LABEL_33;
      }
LABEL_41:
      v19 = 0;
      goto LABEL_33;
    }
    v19 = (unsigned __int8)LargeHeapBlock::RescanOnePage((LargeHeapBlock *)v16, v9, v20);
LABEL_33:
    v16 = *(_QWORD *)(v16 + 64);
    v18 += v19;
  }
  v21 = v18 + v17;
  if ( *((_BYTE *)v9 + 12903) )
    return v21 + (unsigned int)LargeHeapBucket::Rescan(a1, v6[6], v9, a4, a2);
  else
    return v21;
}

```

## disassembly

```asm
0x180009808  mov     rax, rsp
0x18000980b  mov     [rax+18h], rbx
0x18000980f  mov     [rax+20h], rbp
0x180009813  mov     [rax+10h], edx
0x180009816  mov     [rax+8], rcx
0x18000981a  push    rsi
0x18000981b  push    rdi
0x18000981c  push    r12
0x18000981e  push    r14
0x180009820  push    r15
0x180009822  sub     rsp, 40h
0x180009826  mov     rax, [rcx]
0x180009829  xor     r15d, r15d
0x18000982c  mov     ebp, [rsp+68h+arg_8]
0x180009830  mov     r12, rcx
0x180009833  mov     rbx, [rcx+18h]
0x180009837  mov     r14d, ebp
0x18000983a  and     r14d, 1
0x18000983e  mov     rsi, [rax+38h]
0x180009842  jmp     short loc_180009856
0x180009844  mov     rdx, rsi; struct Recycler *
0x180009847  mov     rcx, rbx; this
0x18000984a  call    ?RescanMultiPage@LargeHeapBlock@@AEAA_KPEAVRecycler@@K@Z; LargeHeapBlock::RescanMultiPage(Recycler *,ulong)
0x18000984f  mov     rbx, [rbx+40h]
0x180009853  add     r15, rax
0x180009856  test    rbx, rbx
0x180009859  jz      short loc_1800098CC
0x18000985b  mov     eax, [rbx+28h]
0x18000985e  mov     [rbx+78h], eax
0x180009861  test    r14d, r14d
0x180009864  jz      short loc_1800098A1
0x180009866  mov     byte ptr [rbx+84h], 0
0x18000986d  cmp     dword ptr [rbx+7Ch], 0
0x180009871  jz      short loc_18000989D
0x180009873  mov     r8d, ebp
0x180009876  shr     r8d, 1
0x180009879  and     r8d, 1; unsigned int
0x18000987d  cmp     qword ptr [rbx+20h], 1
0x180009882  jz      loc_180009A19
0x180009888  mov     eax, [rsi]
0x18000988a  cmp     eax, 0E001h
0x18000988f  jz      short loc_180009844
0x180009891  and     eax, 2001h
0x180009896  cmp     eax, 2001h
0x18000989b  jnz     short loc_180009844
0x18000989d  xor     eax, eax
0x18000989f  jmp     short loc_18000984F
0x1800098a1  cmp     byte ptr [rbx+84h], 0
0x1800098a8  jz      short loc_18000986D
0x1800098aa  test    bpl, 2
0x1800098ae  jz      short loc_1800098C5
0x1800098b0  mov     rcx, [rbx+8]; lpBaseAddress
0x1800098b4  mov     edx, 1000h; dwRegionSize
0x1800098b9  call    cs:__imp_ResetWriteWatch
0x1800098c0  nop     dword ptr [rax+rax+00h]
0x1800098c5  mov     eax, 1
0x1800098ca  jmp     short loc_18000984F
0x1800098cc  mov     rbx, [r12+10h]
0x1800098d1  xor     edi, edi
0x1800098d3  jmp     short loc_1800098E7
0x1800098d5  mov     rdx, rsi; struct Recycler *
0x1800098d8  mov     rcx, rbx; this
0x1800098db  call    ?RescanMultiPage@LargeHeapBlock@@AEAA_KPEAVRecycler@@K@Z; LargeHeapBlock::RescanMultiPage(Recycler *,ulong)
0x1800098e0  mov     rbx, [rbx+40h]
0x1800098e4  add     rdi, rax
0x1800098e7  test    rbx, rbx
0x1800098ea  jz      short loc_18000995D
0x1800098ec  mov     eax, [rbx+28h]
0x1800098ef  mov     [rbx+78h], eax
0x1800098f2  test    r14d, r14d
0x1800098f5  jz      short loc_180009932
0x1800098f7  mov     byte ptr [rbx+84h], 0
0x1800098fe  cmp     dword ptr [rbx+7Ch], 0
0x180009902  jz      short loc_18000992E
0x180009904  mov     r8d, ebp
0x180009907  shr     r8d, 1
0x18000990a  and     r8d, 1; unsigned int
0x18000990e  cmp     qword ptr [rbx+20h], 1
0x180009913  jz      loc_180009A2C
0x180009919  mov     eax, [rsi]
0x18000991b  cmp     eax, 0E001h
0x180009920  jz      short loc_1800098D5
0x180009922  and     eax, 2001h
0x180009927  cmp     eax, 2001h
0x18000992c  jnz     short loc_1800098D5
0x18000992e  xor     eax, eax
0x180009930  jmp     short loc_1800098E0
0x180009932  cmp     byte ptr [rbx+84h], 0
0x180009939  jz      short loc_1800098FE
0x18000993b  test    bpl, 2
0x18000993f  jz      short loc_180009956
0x180009941  mov     rcx, [rbx+8]; lpBaseAddress
0x180009945  mov     edx, 1000h; dwRegionSize
0x18000994a  call    cs:__imp_ResetWriteWatch
0x180009951  nop     dword ptr [rax+rax+00h]
0x180009956  mov     eax, 1
0x18000995b  jmp     short loc_1800098E0
0x18000995d  mov     rbx, [r12+20h]
0x180009962  add     r15d, edi
0x180009965  xor     edi, edi
0x180009967  jmp     short loc_18000997B
0x180009969  mov     rdx, rsi; struct Recycler *
0x18000996c  mov     rcx, rbx; this
0x18000996f  call    ?RescanMultiPage@LargeHeapBlock@@AEAA_KPEAVRecycler@@K@Z; LargeHeapBlock::RescanMultiPage(Recycler *,ulong)
0x180009974  mov     rbx, [rbx+40h]
0x180009978  add     rdi, rax
0x18000997b  test    rbx, rbx
0x18000997e  jz      short loc_1800099F0
0x180009980  mov     eax, [rbx+28h]
0x180009983  mov     [rbx+78h], eax
0x180009986  test    r14d, r14d
0x180009989  jz      short loc_1800099C5
0x18000998b  mov     byte ptr [rbx+84h], 0
0x180009992  cmp     dword ptr [rbx+7Ch], 0
0x180009996  jz      short loc_1800099C1
0x180009998  mov     r8d, ebp
0x18000999b  shr     r8d, 1
0x18000999e  and     r8d, 1; unsigned int
0x1800099a2  cmp     qword ptr [rbx+20h], 1
0x1800099a7  jz      loc_180009A3F
0x1800099ad  mov     eax, [rsi]
0x1800099af  cmp     eax, 0E001h
0x1800099b4  jz      short loc_180009969
0x1800099b6  mov     ecx, 2001h
0x1800099bb  and     eax, ecx
0x1800099bd  cmp     eax, ecx
0x1800099bf  jnz     short loc_180009969
0x1800099c1  xor     eax, eax
0x1800099c3  jmp     short loc_180009974
0x1800099c5  cmp     byte ptr [rbx+84h], 0
0x1800099cc  jz      short loc_180009992
0x1800099ce  test    bpl, 2
0x1800099d2  jz      short loc_1800099E9
0x1800099d4  mov     rcx, [rbx+8]; lpBaseAddress
0x1800099d8  mov     edx, 1000h; dwRegionSize
0x1800099dd  call    cs:__imp_ResetWriteWatch
0x1800099e4  nop     dword ptr [rax+rax+00h]
0x1800099e9  mov     eax, 1
0x1800099ee  jmp     short loc_180009974
0x1800099f0  cmp     byte ptr [rsi+3267h], 0
0x1800099f7  lea     ebx, [rdi+r15]
0x1800099fb  jnz     short loc_180009A52
0x1800099fd  mov     eax, ebx
0x1800099ff  lea     r11, [rsp+68h+var_28]
0x180009a04  mov     rbx, [r11+40h]
0x180009a08  mov     rbp, [r11+48h]
0x180009a0c  mov     rsp, r11
0x180009a0f  pop     r15
0x180009a11  pop     r14
0x180009a13  pop     r12
0x180009a15  pop     rdi
0x180009a16  pop     rsi
0x180009a17  retn
0x180009a19  mov     rdx, rsi; struct Recycler *
0x180009a1c  mov     rcx, rbx; this
0x180009a1f  call    ?RescanOnePage@LargeHeapBlock@@AEAA_NPEAVRecycler@@K@Z; LargeHeapBlock::RescanOnePage(Recycler *,ulong)
0x180009a24  movzx   eax, al
0x180009a27  jmp     loc_18000984F
0x180009a2c  mov     rdx, rsi; struct Recycler *
0x180009a2f  mov     rcx, rbx; this
0x180009a32  call    ?RescanOnePage@LargeHeapBlock@@AEAA_NPEAVRecycler@@K@Z; LargeHeapBlock::RescanOnePage(Recycler *,ulong)
0x180009a37  movzx   eax, al
0x180009a3a  jmp     loc_1800098E0
0x180009a3f  mov     rdx, rsi; struct Recycler *
0x180009a42  mov     rcx, rbx; this
0x180009a45  call    ?RescanOnePage@LargeHeapBlock@@AEAA_NPEAVRecycler@@K@Z; LargeHeapBlock::RescanOnePage(Recycler *,ulong)
0x180009a4a  movzx   eax, al
0x180009a4d  jmp     loc_180009974
0x180009a52  mov     rdx, [r12+30h]
0x180009a57  mov     r8, rsi
0x180009a5a  mov     [rsp+68h+var_48], ebp
0x180009a5e  call    ?Rescan@LargeHeapBucket@@AEAA_KPEAVLargeHeapBlock@@PEAVRecycler@@_NW4RescanFlags@@@Z; LargeHeapBucket::Rescan(LargeHeapBlock *,Recycler *,bool,RescanFlags)
0x180009a63  add     eax, ebx
0x180009a65  jmp     short loc_1800099FF
```
