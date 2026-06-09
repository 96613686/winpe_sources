# LipsStateIpsecFilterCreate

- ea: `0x18004642c`
- end: `0x180046743`
- name: `LipsStateIpsecFilterCreate`
- size: `791`
- prototype: `__int64 __fastcall(unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000b2c8`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000c8b4`
- `0x18000e510`
- `0x180042ef8`
- `0x18004642c`

## string_xrefs

- `0x180046720`: `LipsStateIpsecFilterCreate`

## pseudocode

```c
__int64 __fastcall LipsStateIpsecFilterCreate(unsigned int a1, _QWORD *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // esi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  _QWORD *v9; // r14
  __int64 i; // r15
  _QWORD *v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rbx
  _QWORD *v19; // [rsp+68h] [rbp+10h] BYREF
  SIZE_T v20; // [rsp+70h] [rbp+18h] BYREF

  *a2 = 0;
  v20 = 0;
  v19 = 0;
  v4 = NsuSizeTMultiply(a1, 8, &v20);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_43;
    v7 = 22;
    v8 = v4;
    goto LABEL_5;
  }
  v19 = IpsecAllocMem(v20);
  v9 = v19;
  if ( !v19 )
  {
    v5 = 8;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_43;
    v7 = 23;
    v8 = 8;
LABEL_5:
    WPP_SF_d(v6[2], v7, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids, v8);
    goto LABEL_43;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a1 )
    {
      *a2 = v9;
      v19 = 0;
      goto LABEL_43;
    }
    v11 = IpsecAllocMem(0x40u);
    v9[i] = v11;
    if ( !v11 )
    {
      v5 = 8;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 24;
        goto LABEL_41;
      }
      goto LABEL_43;
    }
    *v11 = IpsecAllocMem(0x10u);
    if ( !*(_QWORD *)v9[i] )
    {
      v5 = 8;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 25;
        goto LABEL_41;
      }
      goto LABEL_43;
    }
    v12 = v9[i];
    *(_QWORD *)(v12 + 8) = IpsecAllocMem(0x10u);
    if ( !*(_QWORD *)(v9[i] + 8LL) )
    {
      v5 = 8;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 26;
        goto LABEL_41;
      }
      goto LABEL_43;
    }
    v13 = v9[i];
    *(_QWORD *)(v13 + 24) = IpsecAllocMem(0x10u);
    if ( !*(_QWORD *)(v9[i] + 24LL) )
    {
      v5 = 8;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 27;
        goto LABEL_41;
      }
      goto LABEL_43;
    }
    v14 = v9[i];
    *(_QWORD *)(v14 + 32) = IpsecAllocMem(0x10u);
    v15 = v9[i];
    *(_QWORD *)(v15 + 40) = IpsecAllocMem(0x10u);
    if ( !*(_QWORD *)(v9[i] + 40LL) )
    {
      v5 = 8;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 29;
        goto LABEL_41;
      }
      goto LABEL_43;
    }
    v16 = v9[i];
    *(_QWORD *)(v16 + 48) = IpsecAllocMem(0x10u);
    if ( !*(_QWORD *)(v9[i] + 48LL) )
      break;
    v17 = v9[i];
    *(_QWORD *)(v17 + 56) = IpsecAllocMem(0x10u);
    if ( !*(_QWORD *)(v9[i] + 56LL) )
    {
      v5 = 8;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 31;
LABEL_41:
        v8 = 8;
        goto LABEL_5;
      }
      goto LABEL_43;
    }
  }
  v5 = 8;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v7 = 30;
    goto LABEL_41;
  }
LABEL_43:
  LipsStateIpsecFilterDestroy(a1, &v19);
  if ( v5 )
    return LipsReportError(v5, (int)"LipsStateIpsecFilterCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004642c  mov     rax, rsp
0x18004642f  mov     [rax+8], rbx
0x180046433  push    rbp
0x180046434  push    rsi
0x180046435  push    rdi
0x180046436  push    r12
0x180046438  push    r13
0x18004643a  push    r14
0x18004643c  push    r15
0x18004643e  sub     rsp, 20h
0x180046442  xor     r10d, r10d
0x180046445  mov     r13d, ecx
0x180046448  mov     r12, rdx
0x18004644b  mov     [rdx], r10
0x18004644e  mov     ecx, ecx
0x180046450  lea     r8, [rax+18h]
0x180046454  mov     [rax+18h], r10
0x180046458  lea     ebx, [r10+8]
0x18004645c  mov     [rax+10h], r10
0x180046460  mov     edx, ebx
0x180046462  call    NsuSizeTMultiply
0x180046467  mov     esi, eax
0x180046469  test    eax, eax
0x18004646b  jz      short loc_1800464AC
0x18004646d  mov     rcx, cs:WPP_GLOBAL_Control
0x180046474  lea     rdx, WPP_GLOBAL_Control
0x18004647b  cmp     rcx, rdx
0x18004647e  jz      loc_18004670B
0x180046484  lea     edi, [rbx+8]
0x180046487  test    [rcx+1Ch], dil
0x18004648b  jz      loc_18004670B
0x180046491  lea     edx, [rbx+0Eh]
0x180046494  mov     r9d, eax
0x180046497  mov     rcx, [rcx+10h]
0x18004649b  lea     r8, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids
0x1800464a2  call    WPP_SF_d
0x1800464a7  jmp     loc_18004670B
0x1800464ac  mov     rcx, [rsp+58h+arg_10]
0x1800464b1  call    IpsecAllocMem
0x1800464b6  mov     [rsp+58h+arg_8], rax
0x1800464bb  mov     r14, rax
0x1800464be  test    rax, rax
0x1800464c1  jnz     short loc_1800464F1
0x1800464c3  mov     esi, ebx
0x1800464c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800464cc  lea     rdx, WPP_GLOBAL_Control
0x1800464d3  cmp     rcx, rdx
0x1800464d6  jz      loc_18004670B
0x1800464dc  lea     edi, [rax+10h]
0x1800464df  test    [rcx+1Ch], dil
0x1800464e3  jz      loc_18004670B
0x1800464e9  lea     edx, [rax+17h]
0x1800464ec  mov     r9d, ebx
0x1800464ef  jmp     short loc_180046497
0x1800464f1  xor     r15d, r15d
0x1800464f4  lea     edi, [r15+10h]
0x1800464f8  cmp     r15d, r13d
0x1800464fb  jnb     loc_1800466FE
0x180046501  mov     ecx, 40h ; '@'
0x180046506  call    IpsecAllocMem
0x18004650b  mov     [r14+r15*8], rax
0x18004650f  mov     rbx, rax
0x180046512  test    rax, rax
0x180046515  jz      loc_1800466D5
0x18004651b  mov     rcx, rdi
0x18004651e  call    IpsecAllocMem
0x180046523  mov     [rbx], rax
0x180046526  mov     rax, [r14+r15*8]
0x18004652a  cmp     qword ptr [rax], 0
0x18004652e  jz      loc_1800466B2
0x180046534  mov     rcx, rdi
0x180046537  mov     rbx, rax
0x18004653a  call    IpsecAllocMem
0x18004653f  mov     [rbx+8], rax
0x180046543  mov     rax, [r14+r15*8]
0x180046547  cmp     qword ptr [rax+8], 0
0x18004654c  jz      loc_18004668F
0x180046552  mov     rcx, rdi
0x180046555  mov     rbx, rax
0x180046558  call    IpsecAllocMem
0x18004655d  mov     [rbx+18h], rax
0x180046561  mov     rax, [r14+r15*8]
0x180046565  cmp     qword ptr [rax+18h], 0
0x18004656a  jz      loc_180046664
0x180046570  mov     rcx, rdi
0x180046573  mov     rbx, rax
0x180046576  call    IpsecAllocMem
0x18004657b  mov     [rbx+20h], rax
0x18004657f  mov     rcx, rdi
0x180046582  mov     rbx, [r14+r15*8]
0x180046586  call    IpsecAllocMem
0x18004658b  mov     [rbx+28h], rax
0x18004658f  mov     rax, [r14+r15*8]
0x180046593  cmp     qword ptr [rax+28h], 0
0x180046598  jz      loc_180046636
0x18004659e  mov     rcx, rdi
0x1800465a1  mov     rbx, rax
0x1800465a4  call    IpsecAllocMem
0x1800465a9  mov     [rbx+30h], rax
0x1800465ad  mov     rax, [r14+r15*8]
0x1800465b1  cmp     qword ptr [rax+30h], 0
0x1800465b6  jz      short loc_180046608
0x1800465b8  mov     rcx, rdi
0x1800465bb  mov     rbx, rax
0x1800465be  call    IpsecAllocMem
0x1800465c3  mov     [rbx+38h], rax
0x1800465c7  mov     rax, [r14+r15*8]
0x1800465cb  cmp     qword ptr [rax+38h], 0
0x1800465d0  jz      short loc_1800465DA
0x1800465d2  inc     r15d
0x1800465d5  jmp     loc_1800464F8
0x1800465da  mov     esi, 8
0x1800465df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800465e6  lea     rdx, WPP_GLOBAL_Control
0x1800465ed  cmp     rcx, rdx
0x1800465f0  jz      loc_18004670B
0x1800465f6  test    [rcx+1Ch], dil
0x1800465fa  jz      loc_18004670B
0x180046600  lea     edx, [rsi+17h]
0x180046603  jmp     loc_1800466F6
0x180046608  mov     esi, 8
0x18004660d  mov     rcx, cs:WPP_GLOBAL_Control
0x180046614  lea     rdx, WPP_GLOBAL_Control
0x18004661b  cmp     rcx, rdx
0x18004661e  jz      loc_18004670B
0x180046624  test    [rcx+1Ch], dil
0x180046628  jz      loc_18004670B
0x18004662e  lea     edx, [rsi+16h]
0x180046631  jmp     loc_1800466F6
0x180046636  mov     esi, 8
0x18004663b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046642  lea     rdx, WPP_GLOBAL_Control
0x180046649  cmp     rcx, rdx
0x18004664c  jz      loc_18004670B
0x180046652  test    [rcx+1Ch], dil
0x180046656  jz      loc_18004670B
0x18004665c  lea     edx, [rsi+15h]
0x18004665f  jmp     loc_1800466F6
0x180046664  mov     esi, 8
0x180046669  mov     rcx, cs:WPP_GLOBAL_Control
0x180046670  lea     rdx, WPP_GLOBAL_Control
0x180046677  cmp     rcx, rdx
0x18004667a  jz      loc_18004670B
0x180046680  test    [rcx+1Ch], dil
0x180046684  jz      loc_18004670B
0x18004668a  lea     edx, [rsi+13h]
0x18004668d  jmp     short loc_1800466F6
0x18004668f  mov     esi, 8
0x180046694  mov     rcx, cs:WPP_GLOBAL_Control
0x18004669b  lea     rdx, WPP_GLOBAL_Control
0x1800466a2  cmp     rcx, rdx
0x1800466a5  jz      short loc_18004670B
0x1800466a7  test    [rcx+1Ch], dil
0x1800466ab  jz      short loc_18004670B
0x1800466ad  lea     edx, [rsi+12h]
0x1800466b0  jmp     short loc_1800466F6
0x1800466b2  mov     esi, 8
0x1800466b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800466be  lea     rdx, WPP_GLOBAL_Control
0x1800466c5  cmp     rcx, rdx
0x1800466c8  jz      short loc_18004670B
0x1800466ca  test    [rcx+1Ch], dil
0x1800466ce  jz      short loc_18004670B
0x1800466d0  lea     edx, [rsi+11h]
0x1800466d3  jmp     short loc_1800466F6
0x1800466d5  mov     esi, 8
0x1800466da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800466e1  lea     rdx, WPP_GLOBAL_Control
0x1800466e8  cmp     rcx, rdx
0x1800466eb  jz      short loc_18004670B
0x1800466ed  test    [rcx+1Ch], dil
0x1800466f1  jz      short loc_18004670B
0x1800466f3  lea     edx, [rsi+10h]
0x1800466f6  mov     r9d, esi
0x1800466f9  jmp     loc_180046497
0x1800466fe  mov     [r12], r14
0x180046702  mov     [rsp+58h+arg_8], 0
0x18004670b  lea     rdx, [rsp+58h+arg_8]
0x180046710  mov     ecx, r13d
0x180046713  call    LipsStateIpsecFilterDestroy
0x180046718  test    esi, esi
0x18004671a  jnz     short loc_180046720
0x18004671c  xor     eax, eax
0x18004671e  jmp     short loc_18004672E
0x180046720  lea     rdx, aLipsstateipsec_8; "LipsStateIpsecFilterCreate"
0x180046727  mov     ecx, esi
0x180046729  call    LipsReportError
0x18004672e  mov     rbx, [rsp+58h+arg_0]
0x180046733  add     rsp, 20h
0x180046737  pop     r15
0x180046739  pop     r14
0x18004673b  pop     r13
0x18004673d  pop     r12
0x18004673f  pop     rdi
0x180046740  pop     rsi
0x180046741  pop     rbp
0x180046742  retn
```
