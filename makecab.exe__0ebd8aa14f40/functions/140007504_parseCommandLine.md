# parseCommandLine

- ea: `0x140007504`
- end: `0x1400078a3`
- name: `parseCommandLine`
- size: `927`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140006a6c`

## callees

- `0x1400021cc`
- `0x140003c88`
- `0x140007504`
- `0x14000836c`
- `0x140008620`
- `0x14000907c`
- `0x14000e412`
- `0x14000e4e0`

## import_xrefs

- `msvcrt!atoi` at `0x1400076df`
- `msvcrt!atoi` at `0x1400076df`
- `msvcrt!toupper` at `0x1400076ab`
- `msvcrt!toupper` at `0x1400076ab`
- `msvcrt!free` at `0x140007837`
- `msvcrt!free` at `0x140007837`
- `msvcrt!_strdup` at `0x140007810`
- `msvcrt!_strdup` at `0x140007810`

## pseudocode

```c
__int64 __fastcall parseCommandLine(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  int v4; // edi
  int v6; // edx
  int v8; // ecx
  int v9; // r13d
  int v10; // eax
  int v11; // r12d
  const char *v14; // r8
  __int64 v15; // rbp
  const char *v16; // rsi
  __int64 v17; // rdx
  __int64 v18; // rax
  _BYTE *v19; // r8
  __int64 v20; // rdx
  _BYTE *v21; // rax
  int v22; // ecx
  __int64 v23; // rax
  int v24; // eax
  const char *v25; // r9
  int v26; // eax
  int v27; // edi
  int v28; // edi
  const char *v29; // rdx
  char *v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rdi
  void *v33; // rsi
  char *v34; // rax
  const char *v36; // rdx
  int v37; // [rsp+20h] [rbp-1188h]
  int v38; // [rsp+24h] [rbp-1184h]
  int v39; // [rsp+28h] [rbp-1180h]
  char *Source[2]; // [rsp+30h] [rbp-1178h]
  _BYTE v41[4]; // [rsp+40h] [rbp-1168h] BYREF
  int v42; // [rsp+44h] [rbp-1164h]
  char v43[32]; // [rsp+48h] [rbp-1160h] BYREF
  char v44[4416]; // [rsp+68h] [rbp-1140h] BYREF

  v4 = 0;
  v6 = 0;
  v8 = 0;
  v37 = 0;
  v9 = 0;
  v38 = 0;
  v10 = 1;
  v11 = 0;
  v39 = 1;
  *(_OWORD *)Source = 0;
  if ( a2 <= 1 )
    goto LABEL_72;
  v14 = (const char *)(unsigned int)a2;
  do
  {
    v15 = v10;
    v16 = *(const char **)(a3 + 8LL * v10);
    if ( ((*v16 - 45) & 0xFD) == 0 )
    {
      if ( v9 )
        goto LABEL_76;
      if ( v8 )
        goto LABEL_75;
      if ( v11 )
        goto LABEL_74;
      v24 = toupper(v16[1]);
      v25 = *(const char **)(a3 + 8 * v15);
      switch ( v24 )
      {
        case '?':
          if ( !v25[2] )
            goto LABEL_72;
LABEL_68:
          v29 = "Invalid switch: %1";
LABEL_69:
          ErrSet(a4, v29, "%s", v25);
          return 0;
        case 'D':
          if ( v25[2] )
            goto LABEL_68;
          if ( v4 && v4 != 3 )
          {
LABEL_61:
            v29 = "Switch not expected: %1";
            goto LABEL_69;
          }
          v9 = 1;
          break;
        case 'F':
          if ( v25[2] )
            goto LABEL_68;
          if ( v4 && v4 != 3 )
            goto LABEL_61;
          v4 = 3;
          v8 = 1;
          goto LABEL_7;
        case 'L':
          if ( v25[2] )
            goto LABEL_68;
          v11 = 1;
          break;
        case 'V':
          if ( v25[2] )
            v26 = atoi(v25 + 2);
          else
            v26 = 3;
          *(_DWORD *)(a1 + 80) = v26;
          break;
        default:
          goto LABEL_68;
      }
LABEL_47:
      v8 = v38;
      goto LABEL_48;
    }
    if ( v8 )
    {
      if ( !addDirectiveFile(a1, v16, a4) )
        return 0;
      v8 = 0;
LABEL_7:
      v38 = v8;
LABEL_48:
      v6 = v37;
      v14 = (const char *)(unsigned int)a2;
      goto LABEL_49;
    }
    if ( v9 )
    {
      v42 = 0;
      memset_0(v41, 0, 0x1114u);
      if ( !(unsigned int)DFPParseVarAssignment((__int64)v41, v17, v16, a4) || !(unsigned int)setVariable(a1, v43, v44) )
        return 0;
      v9 = 0;
      goto LABEL_47;
    }
    if ( v11 )
    {
      v18 = 2147483646;
      v19 = (_BYTE *)(a1 + 2868);
      v20 = 256;
      do
      {
        if ( !v18 )
          break;
        if ( !*v16 )
          break;
        *v19++ = *v16++;
        --v18;
        --v20;
      }
      while ( v20 );
      v21 = v19 - 1;
      if ( v20 )
        v21 = v19;
      *v21 = 0;
      if ( !v20 )
      {
        v25 = *(const char **)(a3 + 8 * v15);
        v29 = "Location too long: %1";
        goto LABEL_69;
      }
      if ( !(unsigned int)ensureDirectory((char *)(a1 + 2868), 0, a4) )
        return 0;
      v11 = 0;
      goto LABEL_47;
    }
    if ( (v4 & 0xFFFFFFFD) != 0 )
    {
      v25 = *(const char **)(a3 + 8LL * v10);
      v29 = "Invalid parameter: %1";
      goto LABEL_69;
    }
    v22 = v6 + 1;
    if ( v6 + 1 > 2 )
    {
      v25 = *(const char **)(a3 + 8LL * v10);
      v29 = "Too many parameters: %1";
      goto LABEL_69;
    }
    v23 = v6;
    v4 = 2;
    ++v6;
    v37 = v22;
    v8 = v38;
    Source[v23] = (char *)v16;
LABEL_49:
    v10 = v39 + 1;
    v39 = v10;
  }
  while ( v10 < (int)v14 );
  if ( v9 )
  {
LABEL_76:
    v36 = "Variable definition missing";
    goto LABEL_77;
  }
  if ( v8 )
  {
LABEL_75:
    v36 = "Directive file name missing";
    goto LABEL_77;
  }
  if ( v11 )
  {
LABEL_74:
    v36 = "Location missing";
LABEL_77:
    ErrSet(a4, v36, v14);
    return 0;
  }
  if ( !v4 || (v27 = v4 - 1) == 0 )
  {
LABEL_72:
    *(_DWORD *)a1 = 1;
    return 1;
  }
  v28 = v27 - 1;
  if ( v28 )
  {
    if ( v28 == 1 )
      *(_DWORD *)a1 = 3;
  }
  else
  {
    v30 = Source[0];
    *(_DWORD *)a1 = 2;
    v31 = addDirectiveFile(a1, v30, a4);
    v32 = v31;
    if ( !v31 )
      return 0;
    if ( v37 != 2 )
      return 1;
    v33 = *(void **)(v31 + 8);
    v34 = _strdup(Source[1]);
    *(_QWORD *)(v32 + 8) = v34;
    if ( !v34 )
    {
      v25 = "Changing destination";
      v29 = "Out of memory: %1";
      goto LABEL_69;
    }
    if ( v33 )
      free(v33);
  }
  return 1;
}

```

## disassembly

```asm
0x140007504  mov     [rsp+arg_8], edx
0x140007508  push    rbx
0x140007509  push    rbp
0x14000750a  push    rsi
0x14000750b  push    rdi
0x14000750c  push    r12
0x14000750e  push    r13
0x140007510  push    r14
0x140007512  push    r15
0x140007514  mov     eax, 1168h
0x140007519  call    _alloca_probe
0x14000751e  sub     rsp, rax
0x140007521  xor     edi, edi
0x140007523  mov     esi, edx
0x140007525  xor     edx, edx
0x140007527  mov     r14, rcx
0x14000752a  xor     ecx, ecx
0x14000752c  mov     [rsp+11A8h+var_1188], edx
0x140007530  xor     r13d, r13d
0x140007533  mov     [rsp+11A8h+var_1184], ecx
0x140007537  lea     eax, [rdi+1]
0x14000753a  xor     r12d, r12d
0x14000753d  mov     [rsp+11A8h+var_1180], eax
0x140007541  xorps   xmm0, xmm0
0x140007544  mov     rbx, r9
0x140007547  mov     r15, r8
0x14000754a  movups  xmmword ptr [rsp+11A8h+Source], xmm0
0x14000754f  cmp     esi, eax
0x140007551  jle     loc_140007860
0x140007557  mov     r8d, [rsp+11A8h+arg_8]
0x14000755f  movsxd  rbp, eax
0x140007562  mov     rsi, [r15+rbp*8]
0x140007566  mov     al, [rsi]
0x140007568  sub     al, 2Dh ; '-'
0x14000756a  test    al, 0FDh
0x14000756c  jz      loc_14000768D
0x140007572  test    ecx, ecx
0x140007574  jz      short loc_140007598
0x140007576  mov     r8, rbx
0x140007579  mov     rdx, rsi
0x14000757c  mov     rcx, r14
0x14000757f  call    addDirectiveFile
0x140007584  test    rax, rax
0x140007587  jz      loc_140007855
0x14000758d  xor     ecx, ecx
0x14000758f  mov     [rsp+11A8h+var_1184], ecx
0x140007593  jmp     loc_14000774C
0x140007598  test    r13d, r13d
0x14000759b  jz      short loc_1400075F2
0x14000759d  xor     eax, eax
0x14000759f  lea     rcx, [rsp+11A8h+var_1168]; void *
0x1400075a4  xor     edx, edx; Val
0x1400075a6  mov     [rsp+11A8h+var_1164], eax
0x1400075aa  mov     r8d, 1114h; Size
0x1400075b0  call    memset_0
0x1400075b5  mov     r9, rbx
0x1400075b8  lea     rcx, [rsp+11A8h+var_1168]
0x1400075bd  mov     r8, rsi
0x1400075c0  call    DFPParseVarAssignment
0x1400075c5  test    eax, eax
0x1400075c7  jz      loc_140007855
0x1400075cd  mov     r9, rbx
0x1400075d0  lea     r8, [rsp+11A8h+var_1140]
0x1400075d5  lea     rdx, [rsp+11A8h+var_1160]
0x1400075da  mov     rcx, r14
0x1400075dd  call    setVariable
0x1400075e2  test    eax, eax
0x1400075e4  jz      loc_140007855
0x1400075ea  xor     r13d, r13d
0x1400075ed  jmp     loc_140007748
0x1400075f2  test    r12d, r12d
0x1400075f5  jz      short loc_140007659
0x1400075f7  lea     r9, [r14+0B34h]
0x1400075fe  mov     eax, 7FFFFFFEh
0x140007603  mov     r8, r9
0x140007606  mov     edx, 100h
0x14000760b  test    rax, rax
0x14000760e  jz      short loc_140007628
0x140007610  mov     cl, [rsi]
0x140007612  test    cl, cl
0x140007614  jz      short loc_140007628
0x140007616  mov     [r8], cl
0x140007619  inc     rsi
0x14000761c  inc     r8
0x14000761f  dec     rax
0x140007622  sub     rdx, 1
0x140007626  jnz     short loc_14000760B
0x140007628  test    rdx, rdx
0x14000762b  lea     rax, [r8-1]
0x14000762f  cmovnz  rax, r8
0x140007633  mov     byte ptr [rax], 0
0x140007636  jz      loc_1400077B0
0x14000763c  mov     r8, rbx
0x14000763f  xor     edx, edx
0x140007641  mov     rcx, r9; lpCurrentChar
0x140007644  call    ensureDirectory
0x140007649  test    eax, eax
0x14000764b  jz      loc_140007855
0x140007651  xor     r12d, r12d
0x140007654  jmp     loc_140007748
0x140007659  test    edi, 0FFFFFFFDh
0x14000765f  jnz     loc_1400077CC
0x140007665  lea     ecx, [rdx+1]
0x140007668  cmp     ecx, 2
0x14000766b  jg      loc_1400077C0
0x140007671  movsxd  rax, edx
0x140007674  mov     edi, 2
0x140007679  mov     edx, ecx
0x14000767b  mov     [rsp+11A8h+var_1188], ecx
0x14000767f  mov     ecx, [rsp+11A8h+var_1184]
0x140007683  mov     [rsp+rax*8+11A8h+Source], rsi
0x140007688  jmp     loc_140007758
0x14000768d  test    r13d, r13d
0x140007690  jnz     loc_140007892
0x140007696  test    ecx, ecx
0x140007698  jnz     loc_140007889
0x14000769e  test    r12d, r12d
0x1400076a1  jnz     loc_140007880
0x1400076a7  movsx   ecx, byte ptr [rsi+1]; C
0x1400076ab  call    cs:__imp_toupper
0x1400076b1  mov     r9, [r15+rbp*8]
0x1400076b5  cmp     eax, 3Fh ; '?'
0x1400076b8  jz      loc_140007859
0x1400076be  cmp     eax, 44h ; 'D'
0x1400076c1  jz      short loc_14000772A
0x1400076c3  cmp     eax, 46h ; 'F'
0x1400076c6  jz      short loc_140007705
0x1400076c8  cmp     eax, 4Ch ; 'L'
0x1400076cb  jz      short loc_1400076F2
0x1400076cd  cmp     eax, 56h ; 'V'
0x1400076d0  jnz     loc_14000783F
0x1400076d6  lea     rcx, [r9+2]; String
0x1400076da  cmp     [rcx], r12b
0x1400076dd  jz      short loc_1400076E7
0x1400076df  call    cs:__imp_atoi
0x1400076e5  jmp     short loc_1400076EC
0x1400076e7  mov     eax, 3
0x1400076ec  mov     [r14+50h], eax
0x1400076f0  jmp     short loc_140007748
0x1400076f2  cmp     byte ptr [r9+2], 0
0x1400076f7  jnz     loc_14000783F
0x1400076fd  mov     r12d, 1
0x140007703  jmp     short loc_140007748
0x140007705  cmp     byte ptr [r9+2], 0
0x14000770a  jnz     loc_14000783F
0x140007710  test    edi, edi
0x140007712  jz      short loc_14000771D
0x140007714  cmp     edi, 3
0x140007717  jnz     loc_1400077D8
0x14000771d  mov     edi, 3
0x140007722  lea     ecx, [rdi-2]
0x140007725  jmp     loc_14000758F
0x14000772a  cmp     byte ptr [r9+2], 0
0x14000772f  jnz     loc_14000783F
0x140007735  test    edi, edi
0x140007737  jz      short loc_140007742
0x140007739  cmp     edi, 3
0x14000773c  jnz     loc_1400077D8
0x140007742  mov     r13d, 1
0x140007748  mov     ecx, [rsp+11A8h+var_1184]
0x14000774c  mov     edx, [rsp+11A8h+var_1188]
0x140007750  mov     r8d, [rsp+11A8h+arg_8]
0x140007758  mov     eax, [rsp+11A8h+var_1180]
0x14000775c  inc     eax
0x14000775e  mov     [rsp+11A8h+var_1180], eax
0x140007762  cmp     eax, r8d
0x140007765  jl      loc_14000755F
0x14000776b  test    r13d, r13d
0x14000776e  jnz     loc_140007892
0x140007774  test    ecx, ecx
0x140007776  jnz     loc_140007889
0x14000777c  test    r12d, r12d
0x14000777f  jnz     loc_140007880
0x140007785  test    edi, edi
0x140007787  jz      loc_140007860
0x14000778d  sub     edi, 1
0x140007790  jz      loc_140007860
0x140007796  sub     edi, 1
0x140007799  jz      short loc_1400077E1
0x14000779b  cmp     edi, 1
0x14000779e  jnz     loc_140007867
0x1400077a4  mov     dword ptr [r14], 3
0x1400077ab  jmp     loc_140007867
0x1400077b0  mov     r9, [r15+rbp*8]
0x1400077b4  lea     rdx, aLocationTooLon; "Location too long: %1"
0x1400077bb  jmp     loc_140007846
0x1400077c0  mov     r9, rsi
0x1400077c3  lea     rdx, aTooManyParamet; "Too many parameters: %1"
0x1400077ca  jmp     short loc_140007846
0x1400077cc  mov     r9, rsi
0x1400077cf  lea     rdx, aInvalidParamet; "Invalid parameter: %1"
0x1400077d6  jmp     short loc_140007846
0x1400077d8  lea     rdx, aSwitchNotExpec; "Switch not expected: %1"
0x1400077df  jmp     short loc_140007846
0x1400077e1  mov     rdx, [rsp+11A8h+Source]
0x1400077e6  mov     r8, rbx
0x1400077e9  mov     rcx, r14
0x1400077ec  mov     dword ptr [r14], 2
0x1400077f3  call    addDirectiveFile
0x1400077f8  mov     rdi, rax
0x1400077fb  test    rax, rax
0x1400077fe  jz      short loc_140007855
0x140007800  cmp     [rsp+11A8h+var_1188], 2
0x140007805  jnz     short loc_140007867
0x140007807  mov     rcx, [rsp+11A8h+Source+8]; Source
0x14000780c  mov     rsi, [rax+8]
0x140007810  call    cs:__imp__strdup
0x140007816  mov     [rdi+8], rax
0x14000781a  test    rax, rax
0x14000781d  jnz     short loc_14000782F
0x14000781f  lea     r9, aChangingDestin; "Changing destination"
0x140007826  lea     rdx, aOutOfMemory1_0; "Out of memory: %1"
0x14000782d  jmp     short loc_140007846
0x14000782f  test    rsi, rsi
0x140007832  jz      short loc_140007867
0x140007834  mov     rcx, rsi; Block
0x140007837  call    cs:__imp_free
0x14000783d  jmp     short loc_140007867
0x14000783f  lea     rdx, aInvalidSwitch1; "Invalid switch: %1"
0x140007846  lea     r8, aS_4; "%s"
0x14000784d  mov     rcx, rbx
0x140007850  call    ErrSet
0x140007855  xor     eax, eax
0x140007857  jmp     short loc_14000786C
0x140007859  cmp     byte ptr [r9+2], 0
0x14000785e  jnz     short loc_14000783F
0x140007860  mov     dword ptr [r14], 1
0x140007867  mov     eax, 1
0x14000786c  add     rsp, 1168h
0x140007873  pop     r15
0x140007875  pop     r14
0x140007877  pop     r13
0x140007879  pop     r12
0x14000787b  pop     rdi
0x14000787c  pop     rsi
0x14000787d  pop     rbp
0x14000787e  pop     rbx
0x14000787f  retn
0x140007880  lea     rdx, aLocationMissin; "Location missing"
0x140007887  jmp     short loc_140007899
0x140007889  lea     rdx, aDirectiveFileN; "Directive file name missing"
0x140007890  jmp     short loc_140007899
0x140007892  lea     rdx, aVariableDefini; "Variable definition missing"
0x140007899  mov     rcx, rbx
0x14000789c  call    ErrSet
0x1400078a1  jmp     short loc_140007855
```
