# UlAllocateCacheTracker

- ea: `0x140089f80`
- end: `0x14008a2a3`
- name: `UlAllocateCacheTracker`
- size: `803`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14011d648`
- `0x14011e2e8`
- `0x14011ea2c`

## callees

- `0x140048f00`
- `0x140049d28`
- `0x140051410`
- `0x140089f80`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d2b88`
- `0x1401da550`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14017a152`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14017a152`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14008a038`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14008a038`
- `ntoskrnl!MmSizeOfMdl` at `0x140179f6f`
- `ntoskrnl!MmSizeOfMdl` at `0x140179f90`
- `ntoskrnl!MmSizeOfMdl` at `0x140179f6f`
- `ntoskrnl!MmSizeOfMdl` at `0x140179f90`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14008a211`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14008a211`
- `ntoskrnl!ExAllocatePool3` at `0x14017a00b`
- `ntoskrnl!ExAllocatePool3` at `0x14017a00b`

## pseudocode

```c
_DWORD *__fastcall UlAllocateCacheTracker(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned int v4; // ebp
  int v5; // edi
  char v6; // r15
  SIZE_T v7; // rsi
  unsigned int v8; // edi
  int LockArray_high; // edi
  unsigned __int64 v10; // rbx
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  __int64 v13; // r14
  int v14; // ebp
  int v15; // ebp
  __int64 v16; // r14
  __int64 v18; // rbx
  USHORT CurrentNodeNumber; // ax
  SIZE_T v20; // r13
  SIZE_T v21; // r12
  unsigned __int64 v22; // rax
  __int64 Pool3; // rax
  int v24; // esi
  unsigned int v25; // esi
  SIZE_T v26; // rcx
  SIZE_T v27; // rcx
  SIZE_T v28; // rdi
  SIZE_T v29; // rdi
  __int64 v30; // r9
  __int64 v31; // r10
  __int64 v32; // r8
  __int64 v33; // [rsp+40h] [rbp-38h]

  v4 = a4;
  v5 = a1;
  v6 = a3;
  v7 = (unsigned int)a2;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_LLlL(a1, a2, a3, (unsigned int)a1, a2, (unsigned __int8)a3, a4);
  if ( v4 )
    v4 += UlH3ExtraHeaderCount + 2;
  v8 = v5 + 177;
  if ( v8 > 0x200 || (unsigned int)v7 > 0x40000 || v4 > 0x14 )
  {
    v20 = (MmSizeOfMdl((PVOID)0xFFF, v8) + 7) & 0xFFFFFFF8;
    v21 = (MmSizeOfMdl((PVOID)0xFFF, v7) + 7) & 0xFFFFFFF8;
    v33 = 24LL * v4;
    v22 = v8
        + v20
        + v21
        + (unsigned int)UlVariableHeadersMdlLength
        + 352LL
        + 2 * ((unsigned int)UlVariableHeaderSize + v33);
    if ( v22 <= 0xFFFFFFFF )
    {
      Pool3 = ExAllocatePool3(66, (unsigned int)v22, 1094937685, UxLowPriorityPool, 1);
      v12 = (_DWORD *)Pool3;
      if ( Pool3 )
      {
        v24 = UlVariableHeaderSize;
        strcpy((char *)(Pool3 + 16), "UlCA");
        *(_QWORD *)(Pool3 + 136) = 0;
        *(_QWORD *)(Pool3 + 80) = 0;
        *(_QWORD *)(Pool3 + 128) = 0;
        *(_QWORD *)(Pool3 + 144) = 0;
        v25 = v8 + v24;
        *(_BYTE *)(Pool3 + 21) = v6;
        *(_DWORD *)(Pool3 + 152) = 0;
        *(_OWORD *)(Pool3 + 160) = 0;
        *(_DWORD *)(Pool3 + 176) = 0;
        memset((void *)(Pool3 + 272), 0, 0x50u);
        *((_QWORD *)v12 + 4) = 0;
        *((_QWORD *)v12 + 6) = 0;
        v26 = (SIZE_T)v12 + v20 + 352;
        *((_QWORD *)v12 + 8) = 0;
        *((_QWORD *)v12 + 14) = v26;
        *((_QWORD *)v12 + 13) = v12 + 88;
        v27 = (unsigned int)UlVariableHeadersMdlLength + v26;
        *((_QWORD *)v12 + 15) = v27;
        v28 = v27 + v21;
        UlInitializeParsedHeaders(v12 + 48, v27 + v21, v4);
        v29 = v33 + v28;
        UlInitializeParsedHeaders(v12 + 58, v29, v4);
        v30 = *((_QWORD *)v12 + 14);
        v31 = (unsigned int)UlVariableHeaderSize;
        *((_QWORD *)v12 + 23) = v33 + v29;
        v12[45] = v25;
        v12[22] = v31;
        v32 = v33 + v29 + v25;
        *((_QWORD *)v12 + 12) = v32;
        *(_QWORD *)v30 = 0;
        *(_WORD *)(v30 + 8) = 8
                            * ((((unsigned __int64)(((_WORD)v33 + (_WORD)v29 + (_WORD)v25) & 0xFFF) + v31 + 4095) >> 12)
                             + 6);
        *(_WORD *)(v30 + 10) = 0;
        *(_QWORD *)(v30 + 32) = v32 & 0xFFFFFFFFFFFFF000uLL;
        *(_DWORD *)(v30 + 44) = ((_WORD)v33 + (_WORD)v29 + (_WORD)v25) & 0xFFF;
        *(_DWORD *)(v30 + 40) = v31;
        MmBuildMdlForNonPagedPool(*((PMDL *)v12 + 14));
      }
    }
    else
    {
      v12 = 0;
    }
  }
  else
  {
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    if ( UxDebugDisableLookaside )
    {
      v11 = (_DWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0210[0])(
                        (unsigned int)dword_1401A01F8,
                        qword_1401A0200,
                        (unsigned int)dword_1401A0208,
                        0);
    }
    else if ( UxCompactMode )
    {
      v18 = qword_1401A01F0;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      v11 = (_DWORD *)PplAllocateFromLookasideListProcessor(v18, CurrentNodeNumber);
    }
    else
    {
      v10 = qword_1401A01F0 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
      if ( !*(_BYTE *)(v10 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A01F0, v10 + 64);
      v11 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v10 + 64));
    }
    v12 = v11;
    if ( v11 )
    {
      v11[4] = 1094937685;
      *((_BYTE *)v11 + 21) = v6;
      *((_QWORD *)v11 + 17) = 0;
      *((_QWORD *)v11 + 10) = 0;
      *((_QWORD *)v11 + 16) = 0;
      *((_QWORD *)v11 + 18) = 0;
      v11[38] = 0;
      *((_OWORD *)v11 + 10) = 0;
      v11[44] = 0;
      *((_BYTE *)v11 + 20) = 1;
      memset(v11 + 68, 0, 0x50u);
      *((_QWORD *)v12 + 4) = 0;
      *((_QWORD *)v12 + 6) = 0;
      *((_QWORD *)v12 + 8) = 0;
      v13 = *((_QWORD *)v12 + 24);
      v14 = v12[52];
      *((_OWORD *)v12 + 12) = 0;
      *((_OWORD *)v12 + 13) = 0;
      *((_QWORD *)v12 + 28) = 0;
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_qqD(1038, 84, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, v12 + 48, v13, v14);
      if ( v14 )
      {
        *((_QWORD *)v12 + 24) = v13;
        v12[52] = v14;
      }
      v12[54] = 0xFFFFFFF;
      v12[55] = 0xFFFFFFF;
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_(1038, 85, WPP_3bc569ebedc33674d1577199996181a5_Traceguids);
      v15 = v12[62];
      v16 = *((_QWORD *)v12 + 29);
      *(_OWORD *)(v12 + 58) = 0;
      *(_OWORD *)(v12 + 62) = 0;
      *((_QWORD *)v12 + 33) = 0;
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_qqD(1038, 84, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, v12 + 58, v16, v15);
      if ( v15 )
      {
        *((_QWORD *)v12 + 29) = v16;
        v12[62] = v15;
      }
      v12[64] = 0xFFFFFFF;
      v12[65] = 0xFFFFFFF;
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_(1038, 85, WPP_3bc569ebedc33674d1577199996181a5_Traceguids);
      *v12 = LockArray_high;
    }
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1033, 202, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x140089f80  mov     rax, rsp
0x140089f83  sub     rsp, 78h
0x140089f87  mov     [rax+10h], rbp
0x140089f8b  mov     ebp, r9d
0x140089f8e  mov     [rax+18h], rsi
0x140089f92  mov     [rax-8], rdi
0x140089f96  mov     edi, ecx
0x140089f98  mov     [rax-28h], r15
0x140089f9c  movzx   r15d, r8b
0x140089fa0  mov     esi, edx
0x140089fa2  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140089fa9  jnz     loc_14008A289
0x140089faf  test    ebp, ebp
0x140089fb1  jz      short loc_140089FBE
0x140089fb3  mov     eax, cs:UlH3ExtraHeaderCount
0x140089fb9  add     eax, 2
0x140089fbc  add     ebp, eax
0x140089fbe  add     edi, 0B1h
0x140089fc4  mov     [rsp+78h+arg_0], rbx
0x140089fcc  mov     [rsp+78h+var_20], r14
0x140089fd1  cmp     edi, 200h
0x140089fd7  ja      loc_140179F5C
0x140089fdd  cmp     esi, 40000h
0x140089fe3  ja      loc_140179F5C
0x140089fe9  cmp     ebp, 14h
0x140089fec  ja      loc_140179F5C
0x140089ff2  mov     edi, gs:1A4h
0x140089ffa  cmp     cs:UxDebugDisableLookaside, 0
0x14008a001  jnz     loc_14008A18E
0x14008a007  cmp     cs:UxCompactMode, 0
0x14008a00e  jnz     loc_14008A20A
0x14008a014  mov     rcx, cs:qword_1401A01F0
0x14008a01b  lea     ebx, [rdi+1]
0x14008a01e  shl     rbx, 7
0x14008a022  add     rbx, rcx
0x14008a025  movzx   eax, byte ptr [rbx+0B0h]
0x14008a02c  test    al, al
0x14008a02e  jz      loc_14008A22D
0x14008a034  lea     rcx, [rbx+40h]; Lookaside
0x14008a038  call    cs:__imp_ExAllocateFromLookasideListEx
0x14008a03f  nop     dword ptr [rax+rax+00h]
0x14008a044  mov     rbx, rax
0x14008a047  test    rax, rax
0x14008a04a  jz      loc_14008A155
0x14008a050  mov     dword ptr [rax+10h], 41436C55h
0x14008a057  lea     rcx, [rax+110h]; void *
0x14008a05e  xor     r14d, r14d
0x14008a061  mov     [rax+15h], r15b
0x14008a065  xorps   xmm0, xmm0
0x14008a068  mov     [rax+88h], r14
0x14008a06f  mov     [rax+50h], r14
0x14008a073  xor     edx, edx; Val
0x14008a075  mov     [rax+80h], r14
0x14008a07c  mov     r8d, 50h ; 'P'; Size
0x14008a082  mov     [rax+90h], r14
0x14008a089  mov     [rax+98h], r14d
0x14008a090  movups  xmmword ptr [rax+0A0h], xmm0
0x14008a097  mov     [rax+0B0h], r14d
0x14008a09e  mov     byte ptr [rax+14h], 1
0x14008a0a2  call    memset
0x14008a0a7  mov     [rbx+20h], r14
0x14008a0ab  lea     rsi, [rbx+0C0h]
0x14008a0b2  mov     [rbx+30h], r14
0x14008a0b6  xorps   xmm0, xmm0
0x14008a0b9  mov     [rbx+40h], r14
0x14008a0bd  xor     eax, eax
0x14008a0bf  mov     r14, [rsi]
0x14008a0c2  mov     ebp, [rbx+0D0h]
0x14008a0c8  movups  xmmword ptr [rsi], xmm0
0x14008a0cb  movups  xmmword ptr [rsi+10h], xmm0
0x14008a0cf  mov     [rsi+20h], rax
0x14008a0d3  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x14008a0da  jnz     loc_14008A23B
0x14008a0e0  test    ebp, ebp
0x14008a0e2  jz      short loc_14008A0EA
0x14008a0e4  mov     [rsi], r14
0x14008a0e7  mov     [rsi+10h], ebp
0x14008a0ea  mov     dword ptr [rsi+18h], 0FFFFFFFh
0x14008a0f1  mov     dword ptr [rsi+1Ch], 0FFFFFFFh
0x14008a0f8  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x14008a0ff  jnz     loc_14008A1B6
0x14008a105  mov     ebp, [rbx+0F8h]
0x14008a10b  lea     rsi, [rbx+0E8h]
0x14008a112  mov     r14, [rsi]
0x14008a115  xorps   xmm0, xmm0
0x14008a118  movups  xmmword ptr [rsi], xmm0
0x14008a11b  xor     eax, eax
0x14008a11d  movups  xmmword ptr [rsi+10h], xmm0
0x14008a121  mov     [rsi+20h], rax
0x14008a125  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x14008a12c  jnz     loc_14008A262
0x14008a132  test    ebp, ebp
0x14008a134  jz      short loc_14008A13C
0x14008a136  mov     [rsi], r14
0x14008a139  mov     [rsi+10h], ebp
0x14008a13c  mov     dword ptr [rsi+18h], 0FFFFFFFh
0x14008a143  mov     dword ptr [rsi+1Ch], 0FFFFFFFh
0x14008a14a  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x14008a151  jnz     short loc_14008A1D1
0x14008a153  mov     [rbx], edi
0x14008a155  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14008a15c  mov     r15, [rsp+78h+var_28]
0x14008a161  mov     r14, [rsp+78h+var_20]
0x14008a166  mov     rdi, [rsp+78h+var_8]
0x14008a16b  mov     rsi, [rsp+78h+arg_10]
0x14008a173  mov     rbp, [rsp+78h+arg_8]
0x14008a17b  jnz     short loc_14008A1EC
0x14008a17d  mov     rax, rbx
0x14008a180  mov     rbx, [rsp+78h+arg_0]
0x14008a188  add     rsp, 78h
0x14008a18c  retn
0x14008a18e  mov     rax, cs:off_1401A0210
0x14008a195  xor     r9d, r9d
0x14008a198  mov     r8d, cs:dword_1401A0208
0x14008a19f  mov     rdx, cs:qword_1401A0200
0x14008a1a6  mov     ecx, cs:dword_1401A01F8
0x14008a1ac  call    _guard_dispatch_icall
0x14008a1b1  jmp     loc_14008A044
0x14008a1b6  mov     edx, 55h ; 'U'
0x14008a1bb  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x14008a1c2  mov     ecx, 40Eh
0x14008a1c7  call    WPP_SF_
0x14008a1cc  jmp     loc_14008A105
0x14008a1d1  mov     edx, 55h ; 'U'
0x14008a1d6  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x14008a1dd  mov     ecx, 40Eh
0x14008a1e2  call    WPP_SF_
0x14008a1e7  jmp     loc_14008A153
0x14008a1ec  mov     edx, 0CAh
0x14008a1f1  lea     r8, WPP_15f48f3705be3aa367958d68836c6e27_Traceguids
0x14008a1f8  mov     ecx, 409h
0x14008a1fd  mov     r9, rbx
0x14008a200  call    WPP_SF_q
0x14008a205  jmp     loc_14008A17D
0x14008a20a  mov     rbx, cs:qword_1401A01F0
0x14008a211  call    cs:__imp_KeGetCurrentNodeNumber
0x14008a218  nop     dword ptr [rax+rax+00h]
0x14008a21d  movzx   edx, ax
0x14008a220  mov     rcx, rbx
0x14008a223  call    PplAllocateFromLookasideListProcessor
0x14008a228  jmp     loc_14008A044
0x14008a22d  lea     rdx, [rbx+40h]
0x14008a231  call    PplpLazyInitializeLookasideList
0x14008a236  jmp     loc_14008A034
0x14008a23b  mov     edx, 54h ; 'T'
0x14008a240  mov     [rsp+78h+var_50], ebp
0x14008a244  mov     ecx, 40Eh
0x14008a249  mov     [rsp+78h+var_58], r14
0x14008a24e  mov     r9, rsi
0x14008a251  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x14008a258  call    WPP_SF_qqD
0x14008a25d  jmp     loc_14008A0E0
0x14008a262  mov     edx, 54h ; 'T'
0x14008a267  mov     [rsp+78h+var_50], ebp
0x14008a26b  mov     ecx, 40Eh
0x14008a270  mov     [rsp+78h+var_58], r14
0x14008a275  mov     r9, rsi
0x14008a278  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x14008a27f  call    WPP_SF_qqD
0x14008a284  jmp     loc_14008A132
0x14008a289  mov     [rsp+78h+var_48], ebp
0x14008a28d  mov     r9d, edi
0x14008a290  mov     [rsp+78h+var_50], r15d
0x14008a295  mov     dword ptr [rsp+78h+var_58], esi
0x14008a299  call    WPP_SF_LLlL
0x14008a29e  jmp     loc_140089FAF
0x140179f5c  mov     [rsp+78h+var_10], r12
0x140179f61  mov     ecx, 0FFFh; Base
0x140179f66  mov     edx, edi; Length
0x140179f68  mov     [rsp+78h+var_18], r13
0x140179f6d  mov     ebx, edi
0x140179f6f  call    cs:__imp_MmSizeOfMdl
0x140179f76  nop     dword ptr [rax+rax+00h]
0x140179f7b  mov     r14d, 0FFFFFFF8h
0x140179f81  mov     rdx, rsi; Length
0x140179f84  mov     ecx, 0FFFh; Base
0x140179f89  lea     r13, [rax+7]
0x140179f8d  and     r13, r14
0x140179f90  call    cs:__imp_MmSizeOfMdl
0x140179f97  nop     dword ptr [rax+rax+00h]
0x140179f9c  mov     r8d, cs:UlVariableHeaderSize
0x140179fa3  mov     ecx, ebp
0x140179fa5  lea     r12, [rax+7]
0x140179fa9  and     r12, r14
0x140179fac  lea     rdx, [rcx+rcx*2]
0x140179fb0  mov     ecx, 0FFFFFFFFh
0x140179fb5  lea     rax, ds:0[rdx*8]
0x140179fbd  mov     edx, cs:UlVariableHeadersMdlLength
0x140179fc3  mov     [rsp+78h+var_38], rax
0x140179fc8  add     rdx, 160h
0x140179fcf  add     rax, r8
0x140179fd2  add     rdx, r12
0x140179fd5  lea     rax, [rdx+rax*2]
0x140179fd9  add     rax, r13
0x140179fdc  add     rax, rbx
0x140179fdf  cmp     rax, rcx
0x140179fe2  jbe     short loc_140179FEF
0x140179fe4  xor     r14d, r14d
0x140179fe7  mov     ebx, r14d
0x140179fea  jmp     loc_14017A15E
0x140179fef  mov     edx, eax
0x140179ff1  lea     r9, UxLowPriorityPool
0x140179ff8  mov     ecx, 42h ; 'B'
0x140179ffd  mov     dword ptr [rsp+78h+var_58], 1
0x14017a005  mov     r8d, 41436C55h
0x14017a00b  call    cs:__imp_ExAllocatePool3
0x14017a012  nop     dword ptr [rax+rax+00h]
0x14017a017  mov     rbx, rax
0x14017a01a  test    rax, rax
0x14017a01d  jz      loc_14017A15E
0x14017a023  mov     esi, cs:UlVariableHeaderSize
0x14017a029  lea     rcx, [rax+110h]; void *
0x14017a030  mov     dword ptr [rax+10h], 41436C55h
0x14017a037  xor     r14d, r14d
0x14017a03a  xorps   xmm0, xmm0
0x14017a03d  mov     [rax+88h], r14
0x14017a044  mov     [rax+50h], r14
0x14017a048  xor     edx, edx; Val
0x14017a04a  mov     [rax+80h], r14
0x14017a051  mov     r8d, 50h ; 'P'; Size
0x14017a057  mov     [rax+90h], r14
0x14017a05e  add     esi, edi
0x14017a060  mov     [rax+15h], r15b
0x14017a064  mov     [rax+98h], r14d
0x14017a06b  movups  xmmword ptr [rax+0A0h], xmm0
0x14017a072  mov     [rax+0B0h], r14d
0x14017a079  mov     [rax+14h], r14b
0x14017a07d  call    memset
0x14017a082  mov     [rbx+20h], r14
0x14017a086  lea     rax, [rbx+160h]
0x14017a08d  mov     [rbx+30h], r14
0x14017a091  lea     rcx, [rax+r13]
0x14017a095  mov     [rbx+40h], r14
0x14017a099  mov     r8d, ebp
0x14017a09c  mov     [rbx+70h], rcx
0x14017a0a0  mov     [rbx+68h], rax
0x14017a0a4  mov     eax, cs:UlVariableHeadersMdlLength
0x14017a0aa  add     rcx, rax
0x14017a0ad  mov     [rbx+78h], rcx
0x14017a0b1  lea     rdi, [rcx+r12]
0x14017a0b5  mov     rdx, rdi
0x14017a0b8  lea     rcx, [rbx+0C0h]
0x14017a0bf  call    UlInitializeParsedHeaders
0x14017a0c4  mov     r15, [rsp+78h+var_38]
0x14017a0c9  lea     rcx, [rbx+0E8h]
0x14017a0d0  add     rdi, r15
0x14017a0d3  mov     r8d, ebp
0x14017a0d6  mov     rdx, rdi
0x14017a0d9  call    UlInitializeParsedHeaders
0x14017a0de  mov     r9, [rbx+70h]
0x14017a0e2  lea     rcx, [r15+rdi]
0x14017a0e6  mov     r10d, cs:UlVariableHeaderSize
0x14017a0ed  lea     edx, [rcx+rsi]
0x14017a0f0  mov     [rbx+0B8h], rcx
0x14017a0f7  mov     eax, edx
0x14017a0f9  mov     [rbx+0B4h], esi
0x14017a0ff  and     eax, 0FFFh
0x14017a104  mov     [rbx+58h], r10d
0x14017a108  and     edx, 0FFFh
0x14017a10e  mov     r8d, esi
0x14017a111  add     r8, rcx
0x14017a114  lea     rcx, [r10+0FFFh]
0x14017a11b  mov     [rbx+60h], r8
0x14017a11f  add     rcx, rax
0x14017a122  shr     rcx, 0Ch
0x14017a126  and     r8, 0FFFFFFFFFFFFF000h
0x14017a12d  add     cx, 6
0x14017a131  mov     [r9], r14
0x14017a134  shl     cx, 3
0x14017a138  mov     [r9+8], cx
0x14017a13d  mov     [r9+0Ah], r14w
0x14017a142  mov     [r9+20h], r8
0x14017a146  mov     [r9+2Ch], edx
0x14017a14a  mov     [r9+28h], r10d
0x14017a14e  mov     rcx, [rbx+70h]; MemoryDescriptorList
0x14017a152  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14017a159  nop     dword ptr [rax+rax+00h]
0x14017a15e  mov     r12, [rsp+78h+var_10]
0x14017a163  mov     r13, [rsp+78h+var_18]
0x14017a168  jmp     loc_14008A155
```
