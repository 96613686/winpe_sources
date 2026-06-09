# PrjfPrepareCommandForFilePath

- ea: `0x140032fd8`
- end: `0x1400333bd`
- name: `PrjfPrepareCommandForFilePath`
- size: `997`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400047cc`
- `0x140032db4`
- `0x1400339a8`
- `0x140034428`
- `0x140034c70`
- `0x140034e88`

## callees

- `0x14000bb80`
- `0x14000be80`
- `0x14000d008`
- `0x14000d128`
- `0x140032fd8`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140033161`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140033161`
- `ntoskrnl!ExAllocatePool2` at `0x14003318d`
- `ntoskrnl!ExAllocatePool2` at `0x14003318d`

## pseudocode

```c
__int64 __fastcall PrjfPrepareCommandForFilePath(
        unsigned __int16 *a1,
        _OWORD *a2,
        int a3,
        const void **a4,
        _OWORD *a5,
        __int64 a6,
        unsigned __int16 **a7,
        _QWORD *a8,
        unsigned int *a9)
{
  unsigned int v11; // esi
  unsigned __int16 v12; // dx
  __int64 v13; // r8
  unsigned __int16 v14; // cx
  unsigned int v15; // edi
  unsigned __int16 *v16; // rax
  _DWORD *Pool2; // rbx
  int v18; // edx
  int v19; // r8d
  _OWORD *v20; // rax
  __int64 v21; // rdx
  _OWORD *v22; // rcx
  __int128 v23; // xmm1
  unsigned int v24; // ebp
  const void **v25; // rdx
  _OWORD *v27; // [rsp+A8h] [rbp+10h]
  int v28; // [rsp+B0h] [rbp+18h]

  v28 = a3;
  v27 = a2;
  if ( !a3 )
  {
    v11 = -1073741811;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
      WPP_RECORDER_AND_TRACE_SF_sD(
        526,
        (_DWORD)a2,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        130,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        20);
    }
    return v11;
  }
  if ( !a9 )
  {
    v11 = -1073741811;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        526,
        (_DWORD)a2,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        131,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        27);
    }
    return v11;
  }
  v12 = *a1 >> 1;
  if ( v12 )
  {
    v13 = *((_QWORD *)a1 + 1);
    v14 = 0;
    while ( *(_WORD *)(v13 + 2LL * v14) != 58 )
    {
      if ( ++v14 >= v12 )
        goto LABEL_16;
    }
    *a1 = 2 * v14;
  }
LABEL_16:
  v15 = *a1 + 898;
  if ( a4 )
    v15 += *(unsigned __int16 *)a4 + 2;
  if ( a6 )
  {
    v16 = *(unsigned __int16 **)(a6 + 72);
  }
  else
  {
    if ( !a7 )
      goto LABEL_23;
    v16 = *a7;
  }
  v15 += *v16 + 2;
LABEL_23:
  if ( v15 > 0x790 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(256, v15, 1650674256);
  }
  else
  {
    Pool2 = ExAllocateFromPagedLookasideList(&stru_14001AAC0);
    memset(Pool2, 0, 0x790u);
  }
  if ( Pool2 )
  {
    v11 = 0;
    memset(Pool2, 0, v15);
    Pool2[1] = v28;
    *Pool2 = v15;
    v20 = a5;
    *(_OWORD *)(Pool2 + 2) = *v27;
    if ( a5 )
    {
      v21 = 4;
      v22 = Pool2 + 80;
      do
      {
        *v22 = *v20;
        v22[1] = v20[1];
        v22[2] = v20[2];
        v22[3] = v20[3];
        v22[4] = v20[4];
        v22[5] = v20[5];
        v22[6] = v20[6];
        v23 = v20[7];
        v20 += 8;
        v22[7] = v23;
        v22 += 8;
        --v21;
      }
      while ( v21 );
      *v22 = *v20;
      v22[1] = v20[1];
    }
    Pool2[217] = *a1;
    Pool2[216] = 896;
    memmove(Pool2 + 224, *((const void **)a1 + 1), *a1);
    v24 = Pool2[217] + 898;
    if ( a4 )
    {
      Pool2[219] = *(unsigned __int16 *)a4;
      Pool2[218] = v24;
      memmove((char *)Pool2 + v24, a4[1], *(unsigned __int16 *)a4);
      v24 += Pool2[219] + 2;
    }
    if ( a6 )
    {
      *(_OWORD *)(Pool2 + 11) = *(_OWORD *)(a6 + 56);
      Pool2[220] = *(_DWORD *)(a6 + 80);
      Pool2[222] = **(unsigned __int16 **)(a6 + 72);
      Pool2[221] = v24;
      v25 = *(const void ***)(a6 + 72);
    }
    else
    {
      if ( !a7 )
      {
LABEL_41:
        *a8 = Pool2;
        *a9 = v15;
        return v11;
      }
      Pool2[220] = *((_DWORD *)a7 + 2);
      Pool2[222] = **a7;
      Pool2[221] = v24;
      v25 = (const void **)*a7;
    }
    memmove((char *)Pool2 + v24, v25[1], *(unsigned __int16 *)v25);
    goto LABEL_41;
  }
  v11 = -1073741670;
  if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v18) = BYTE1(xmmword_14001A3D0) & 0x40;
    LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      526,
      v18,
      v19,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      132,
      (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      67,
      154);
  }
  return v11;
}

```

## disassembly

```asm
0x140032fd8  mov     [rsp+arg_0], rbx
0x140032fdd  mov     [rsp+arg_10], r8d
0x140032fe2  mov     [rsp+arg_8], rdx
0x140032fe7  push    rbp
0x140032fe8  push    rsi
0x140032fe9  push    rdi
0x140032fea  push    r12
0x140032fec  push    r13
0x140032fee  push    r14
0x140032ff0  push    r15
0x140032ff2  sub     rsp, 60h
0x140032ff6  mov     r13, r9
0x140032ff9  mov     r14, rcx
0x140032ffc  test    r8d, r8d
0x140032fff  jnz     short loc_14003307A
0x140033001  mov     esi, 0C000000Dh
0x140033006  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003300c  lea     rax, WPP_RECORDER_INITIALIZED
0x140033013  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003301a  setnz   r8b
0x14003301e  and     dl, 40h
0x140033021  jnz     short loc_14003302C
0x140033023  test    r8b, r8b
0x140033026  jz      loc_1400333A2
0x14003302c  mov     [rsp+98h+var_50], 0D14h
0x140033034  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003303b  mov     [rsp+98h+var_58], rax
0x140033040  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140033047  mov     [rsp+98h+var_60], rax
0x14003304c  mov     [rsp+98h+var_68], 82h
0x140033053  mov     r9, cs:WPP_GLOBAL_Control
0x14003305a  mov     ecx, 20Eh
0x14003305f  mov     [rsp+98h+var_70], 0Eh
0x140033067  mov     [rsp+98h+var_78], 2
0x14003306c  mov     r9, [r9+40h]
0x140033070  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140033075  jmp     loc_1400333A2
0x14003307a  cmp     [rsp+98h+arg_40], 0
0x140033083  jnz     short loc_1400330DC
0x140033085  mov     esi, 0C000000Dh
0x14003308a  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140033090  lea     rax, WPP_RECORDER_INITIALIZED
0x140033097  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003309e  setnz   r8b
0x1400330a2  and     dl, 40h
0x1400330a5  jnz     short loc_1400330B0
0x1400330a7  test    r8b, r8b
0x1400330aa  jz      loc_1400333A2
0x1400330b0  mov     [rsp+98h+var_50], 0D1Bh
0x1400330b8  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400330bf  mov     [rsp+98h+var_58], rax
0x1400330c4  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400330cb  mov     [rsp+98h+var_60], rax
0x1400330d0  mov     [rsp+98h+var_68], 83h
0x1400330d7  jmp     loc_140033053
0x1400330dc  movzx   edx, word ptr [rcx]
0x1400330df  xor     eax, eax
0x1400330e1  shr     dx, 1
0x1400330e4  cmp     ax, dx
0x1400330e7  jnb     short loc_14003310B
0x1400330e9  mov     r8, [r14+8]
0x1400330ed  xor     ecx, ecx
0x1400330ef  movzx   eax, cx
0x1400330f2  cmp     word ptr [r8+rax*2], 3Ah ; ':'
0x1400330f8  jz      short loc_140033104
0x1400330fa  inc     cx
0x1400330fd  cmp     cx, dx
0x140033100  jb      short loc_1400330EF
0x140033102  jmp     short loc_14003310B
0x140033104  add     cx, cx
0x140033107  mov     [r14], cx
0x14003310b  movzx   edi, word ptr [r14]
0x14003310f  add     edi, 382h
0x140033115  test    r13, r13
0x140033118  jz      short loc_140033123
0x14003311a  movzx   eax, word ptr [r9]
0x14003311e  add     eax, 2
0x140033121  add     edi, eax
0x140033123  mov     r15, [rsp+98h+arg_28]
0x14003312b  mov     r12, [rsp+98h+arg_30]
0x140033133  test    r15, r15
0x140033136  jz      short loc_14003313E
0x140033138  mov     rax, [r15+48h]
0x14003313c  jmp     short loc_140033147
0x14003313e  test    r12, r12
0x140033141  jz      short loc_14003314F
0x140033143  mov     rax, [r12]
0x140033147  movzx   ecx, word ptr [rax]
0x14003314a  add     ecx, 2
0x14003314d  add     edi, ecx
0x14003314f  mov     esi, 790h
0x140033154  mov     ebp, edi
0x140033156  cmp     edi, esi
0x140033158  ja      short loc_14003317F
0x14003315a  lea     rcx, stru_14001AAC0; Lookaside
0x140033161  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140033168  nop     dword ptr [rax+rax+00h]
0x14003316d  mov     r8d, esi; Size
0x140033170  xor     edx, edx; Val
0x140033172  mov     rcx, rax; void *
0x140033175  mov     rbx, rax
0x140033178  call    memset
0x14003317d  jmp     short loc_14003319C
0x14003317f  mov     r8d, 62634A50h
0x140033185  mov     rdx, rbp
0x140033188  mov     ecx, 100h
0x14003318d  call    cs:__imp_ExAllocatePool2
0x140033194  nop     dword ptr [rax+rax+00h]
0x140033199  mov     rbx, rax
0x14003319c  test    rbx, rbx
0x14003319f  jnz     short loc_14003321E
0x1400331a1  mov     esi, 0C000009Ah
0x1400331a6  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400331ac  lea     rax, WPP_RECORDER_INITIALIZED
0x1400331b3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400331ba  setnz   r8b
0x1400331be  and     dl, 40h
0x1400331c1  jnz     short loc_1400331CC
0x1400331c3  test    r8b, r8b
0x1400331c6  jz      loc_1400333A2
0x1400331cc  mov     r9, cs:WPP_GLOBAL_Control
0x1400331d3  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400331da  mov     [rsp+98h+var_48], esi
0x1400331de  mov     ecx, 20Eh
0x1400331e3  mov     [rsp+98h+var_50], 0D43h
0x1400331eb  mov     [rsp+98h+var_58], rax
0x1400331f0  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400331f7  mov     r9, [r9+40h]
0x1400331fb  mov     [rsp+98h+var_60], rax
0x140033200  mov     [rsp+98h+var_68], 84h
0x140033207  mov     [rsp+98h+var_70], 0Eh
0x14003320f  mov     [rsp+98h+var_78], 2
0x140033214  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140033219  jmp     loc_1400333A2
0x14003321e  mov     r8, rbp; Size
0x140033221  xor     edx, edx; Val
0x140033223  mov     rcx, rbx; void *
0x140033226  xor     esi, esi
0x140033228  call    memset
0x14003322d  mov     eax, [rsp+98h+arg_10]
0x140033234  mov     [rbx+4], eax
0x140033237  mov     rax, [rsp+98h+arg_8]
0x14003323f  mov     [rbx], edi
0x140033241  movaps  xmm0, xmmword ptr [rax]
0x140033244  mov     rax, [rsp+98h+arg_20]
0x14003324c  movdqu  xmmword ptr [rbx+8], xmm0
0x140033251  test    rax, rax
0x140033254  jz      short loc_1400332BC
0x140033256  lea     edx, [rsi+4]
0x140033259  lea     r8d, [rdx+7Ch]
0x14003325d  lea     rcx, [rbx+140h]
0x140033264  movups  xmm0, xmmword ptr [rax]
0x140033267  movups  xmmword ptr [rcx], xmm0
0x14003326a  movups  xmm1, xmmword ptr [rax+10h]
0x14003326e  movups  xmmword ptr [rcx+10h], xmm1
0x140033272  movups  xmm0, xmmword ptr [rax+20h]
0x140033276  movups  xmmword ptr [rcx+20h], xmm0
0x14003327a  movups  xmm1, xmmword ptr [rax+30h]
0x14003327e  movups  xmmword ptr [rcx+30h], xmm1
0x140033282  movups  xmm0, xmmword ptr [rax+40h]
0x140033286  movups  xmmword ptr [rcx+40h], xmm0
0x14003328a  movups  xmm1, xmmword ptr [rax+50h]
0x14003328e  movups  xmmword ptr [rcx+50h], xmm1
0x140033292  movups  xmm0, xmmword ptr [rax+60h]
0x140033296  movups  xmmword ptr [rcx+60h], xmm0
0x14003329a  movups  xmm1, xmmword ptr [rax+70h]
0x14003329e  add     rax, r8
0x1400332a1  movups  xmmword ptr [rcx+70h], xmm1
0x1400332a5  add     rcx, r8
0x1400332a8  sub     rdx, 1
0x1400332ac  jnz     short loc_140033264
0x1400332ae  movups  xmm0, xmmword ptr [rax]
0x1400332b1  movups  xmmword ptr [rcx], xmm0
0x1400332b4  movups  xmm1, xmmword ptr [rax+10h]
0x1400332b8  movups  xmmword ptr [rcx+10h], xmm1
0x1400332bc  movzx   eax, word ptr [r14]
0x1400332c0  lea     rcx, [rbx+380h]; void *
0x1400332c7  mov     [rbx+364h], eax
0x1400332cd  mov     dword ptr [rbx+360h], 380h
0x1400332d7  movzx   r8d, word ptr [r14]; Size
0x1400332db  mov     rdx, [r14+8]; Src
0x1400332df  call    memmove
0x1400332e4  mov     ebp, [rbx+364h]
0x1400332ea  add     ebp, 382h
0x1400332f0  test    r13, r13
0x1400332f3  jz      short loc_140033322
0x1400332f5  movzx   eax, word ptr [r13+0]
0x1400332fa  mov     [rbx+36Ch], eax
0x140033300  mov     [rbx+368h], ebp
0x140033306  movzx   r8d, word ptr [r13+0]; Size
0x14003330b  mov     rdx, [r13+8]; Src
0x14003330f  mov     ecx, ebp
0x140033311  add     rcx, rbx; void *
0x140033314  call    memmove
0x140033319  add     ebp, 2
0x14003331c  add     ebp, [rbx+36Ch]
0x140033322  test    r15, r15
0x140033325  jz      short loc_140033354
0x140033327  movups  xmm0, xmmword ptr [r15+38h]
0x14003332c  movdqu  xmmword ptr [rbx+2Ch], xmm0
0x140033331  mov     eax, [r15+50h]
0x140033335  mov     [rbx+370h], eax
0x14003333b  mov     rax, [r15+48h]
0x14003333f  movzx   ecx, word ptr [rax]
0x140033342  mov     [rbx+378h], ecx
0x140033348  mov     [rbx+374h], ebp
0x14003334e  mov     rdx, [r15+48h]
0x140033352  jmp     short loc_14003337B
0x140033354  test    r12, r12
0x140033357  jz      short loc_14003338D
0x140033359  mov     eax, [r12+8]
0x14003335e  mov     [rbx+370h], eax
0x140033364  mov     rax, [r12]
0x140033368  movzx   ecx, word ptr [rax]
0x14003336b  mov     [rbx+378h], ecx
0x140033371  mov     [rbx+374h], ebp
0x140033377  mov     rdx, [r12]
0x14003337b  movzx   r8d, word ptr [rdx]; Size
0x14003337f  mov     rdx, [rdx+8]; Src
0x140033383  mov     ecx, ebp
0x140033385  add     rcx, rbx; void *
0x140033388  call    memmove
0x14003338d  mov     rcx, [rsp+98h+arg_38]
0x140033395  mov     rax, [rsp+98h+arg_40]
0x14003339d  mov     [rcx], rbx
0x1400333a0  mov     [rax], edi
0x1400333a2  mov     rbx, [rsp+98h+arg_0]
0x1400333aa  mov     eax, esi
0x1400333ac  add     rsp, 60h
0x1400333b0  pop     r15
0x1400333b2  pop     r14
0x1400333b4  pop     r13
0x1400333b6  pop     r12
0x1400333b8  pop     rdi
0x1400333b9  pop     rsi
0x1400333ba  pop     rbp
0x1400333bb  retn
```
