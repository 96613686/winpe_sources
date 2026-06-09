# GetHeaderComment

- ea: `0x14006823c`
- end: `0x140068710`
- name: `GetHeaderComment`
- size: `1236`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400359ac`

## callees

- `0x140062794`
- `0x14006823c`
- `0x140073de0`
- `0x140074984`
- `0x1400961c4`
- `0x1400961d0`
- `0x140098010`

## string_xrefs

- `0x140068597`: `tdCompFont`

## pseudocode

```c
__int64 __fastcall GetHeaderComment(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v4; // rdi
  const char *v5; // rcx
  __int64 v6; // rsi
  unsigned int v7; // eax
  int v8; // eax
  int v9; // ebx
  int v10; // eax
  __int64 v11; // r10
  char *v12; // rsi
  const char *v13; // rax
  int v14; // edi
  __int64 v15; // rsi
  int v16; // eax
  int v17; // r8d
  const char *v18; // rax
  __int64 v19; // rcx
  int v20; // edi
  struct _POLICY_ELEMENT *v21; // rdx
  DWORD v22; // ecx
  PGENERIC_XML_TOKEN *v23; // r8
  PINFORMATIONCARD_CRYPTO_HANDLE *v24; // r9
  STRSAFE_LPCSTR v25; // rdi
  __int64 v27; // [rsp+48h] [rbp+10h] BYREF
  __int64 v28; // [rsp+50h] [rbp+18h] BYREF

  v4 = (char *)token;
  v5 = (const char *)*((_QWORD *)&in + 1);
  v6 = *(unsigned int *)(tokenbuf + 8);
  while ( 1 )
  {
    do
    {
LABEL_2:
      if ( (unsigned __int64)v5 >= (unsigned __int64)xmmword_1400B71F0 )
      {
        v7 = FillBuf(v5, a2, a3, a4);
        v5 = (const char *)*((_QWORD *)&in + 1);
        a2 = v7;
      }
      else
      {
        a2 = *(unsigned __int8 *)v5++;
        *((_QWORD *)&in + 1) = v5;
      }
      if ( (_DWORD)a2 == -1 )
        return 1;
    }
    while ( (atmparse_chartab[(int)a2] & 0x10) != 0 );
    if ( (_DWORD)a2 != 37 )
    {
      *((_QWORD *)&in + 1) = v5 - 1;
      *((_BYTE *)v5 - 1) = a2;
      return 1;
    }
    if ( (unsigned __int64)v5 >= (unsigned __int64)xmmword_1400B71F0 )
    {
      v8 = FillBuf(v5, a2, a3, a4);
      v5 = (const char *)*((_QWORD *)&in + 1);
    }
    else
    {
      v8 = *(unsigned __int8 *)v5++;
      *((_QWORD *)&in + 1) = v5;
    }
    if ( v8 == 33 )
      break;
    while ( v8 != 10 && v8 != 13 && v8 != -1 )
    {
      if ( (unsigned __int64)v5 >= (unsigned __int64)xmmword_1400B71F0 )
      {
        v8 = FillBuf(v5, a2, a3, a4);
        v5 = (const char *)*((_QWORD *)&in + 1);
      }
      else
      {
        v8 = *(unsigned __int8 *)v5++;
        *((_QWORD *)&in + 1) = v5;
      }
    }
  }
  while ( 1 )
  {
    if ( (unsigned __int64)v5 >= (unsigned __int64)xmmword_1400B71F0 )
    {
      v10 = FillBuf(v5, a2, a3, a4);
      v5 = (const char *)*((_QWORD *)&in + 1);
      v9 = v10;
    }
    else
    {
      v9 = *(unsigned __int8 *)v5++;
      *((_QWORD *)&in + 1) = v5;
    }
    if ( v9 == -1 || (atmparse_chartab[v9] & 0x10) == 0 )
      break;
    if ( v9 == 10 || v9 == 13 )
      goto LABEL_2;
  }
  v11 = tokenbuf;
  v12 = &v4[v6];
  do
  {
    if ( v9 == -1 )
      break;
    if ( v4 >= v12 )
    {
      v27 = *(_QWORD *)v11;
      v13 = (const char *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(procs + 752) + 40LL))(
                            *(_QWORD *)(procs + 752),
                            *(_QWORD *)v11,
                            (unsigned int)(*(_DWORD *)(v11 + 8) + 1024));
      v11 = tokenbuf;
      *(_QWORD *)tokenbuf = v13;
      if ( !v13 )
      {
        (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(procs + 752) + 16LL))(*(_QWORD *)(procs + 752), &v27);
        *(_DWORD *)(tokenbuf + 8) = 0;
        ParseError(4294967290LL);
        JUMPOUT(0x14006870FLL);
      }
      v14 = (_DWORD)v4 - (_DWORD)token;
      *(_DWORD *)(v11 + 8) += 1024;
      v15 = *(unsigned int *)(v11 + 8);
      v4 = (char *)&v13[v14];
      token = v13;
      v12 = (char *)&v13[v15];
    }
    *v4++ = v9;
    if ( *((_QWORD *)&in + 1) >= (unsigned __int64)xmmword_1400B71F0 )
    {
      v16 = FillBuf(v5, a2, a3, a4);
      v11 = tokenbuf;
      v9 = v16;
    }
    else
    {
      v9 = (unsigned __int8)**((_BYTE **)&in + 1);
      ++*((_QWORD *)&in + 1);
    }
    v5 = "0";
  }
  while ( (atmparse_chartab[v9] & 0x20) == 0 );
  if ( v4 >= v12 )
  {
    v17 = *(_DWORD *)(v11 + 8);
    v28 = *(_QWORD *)v11;
    v18 = (const char *)(*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(procs + 752) + 40LL))(
                          *(_QWORD *)(procs + 752),
                          v28,
                          (unsigned int)(v17 + 1024));
    v19 = tokenbuf;
    *(_QWORD *)tokenbuf = v18;
    if ( !v18 )
    {
      (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(procs + 752) + 16LL))(*(_QWORD *)(procs + 752), &v28);
      *(_DWORD *)(tokenbuf + 8) = 0;
      ParseError(4294967290LL);
      __debugbreak();
    }
    v20 = (_DWORD)v4 - (_DWORD)token;
    *(_DWORD *)(v19 + 8) += 1024;
    v4 = (char *)&v18[v20];
    token = v18;
  }
  *v4 = 0;
  if ( v9 != -1 && (atmparse_chartab[v9] & 0x10) == 0 )
  {
    --*((_QWORD *)&in + 1);
    **((_BYTE **)&in + 1) = v9;
  }
  if ( strncmp_0(token, "PS-Adobe-", 9u) )
    return 1;
  GetToken(v22, v21, v23, v24);
  v25 = token;
  if ( *token != 65 )
  {
    if ( *token == 82 )
    {
      if ( !strncmp_0(token, "Resource-CMap", 0xDu) )
        return 8;
      if ( !strncmp_0(v25, "Resource-CIDFont", 0x10u) )
        return 9;
      if ( !strncmp_0(v25, "Resource-Font", 0xDu) )
        return 7;
    }
    return 1;
  }
  if ( strncmp_0(token, "Adobe", 5u) )
    return 1;
  switch ( v25[5] )
  {
    case 'C':
      if ( !strcmp_0(v25 + 6, "ompositeFont_BDY") || !strcmp_0(v25 + 6, "ompositeFont") )
        return 10;
      else
        return strcmp_0(v25 + 6, "ompositeEncoding") != 0 ? 1 : 8;
    case 'D':
      return strcmp_0(v25 + 6, "erivedFont") != 0 ? 1 : 6;
    case 'P':
      if ( strncmp_0(v25 + 6, "rimogenitalFont", 0xFu) )
        return 1;
      if ( v25[21] )
        return strcmp_0(v25 + 21, "_CSA") != 0 ? 1 : 5;
      else
        return 4;
    default:
      if ( v25[5] == 83 && !strncmp_0(v25 + 6, "tdCompFont", 0xAu) )
      {
        if ( v25[16] )
          return strcmp_0(v25 + 16, "_BDY") != 0 ? 1 : 3;
        else
          return 2;
      }
      return 1;
  }
}

```

## disassembly

```asm
0x14006823c  mov     [rsp+arg_0], rbx
0x140068241  mov     [rsp+arg_18], rbp
0x140068246  push    rsi
0x140068247  push    rdi
0x140068248  push    r12
0x14006824a  sub     rsp, 20h
0x14006824e  mov     rax, cs:tokenbuf
0x140068255  lea     rbp, atmparse_chartab; "0"
0x14006825c  mov     rdi, cs:token
0x140068263  mov     rcx, qword ptr cs:in+8
0x14006826a  mov     esi, [rax+8]
0x14006826d  cmp     rcx, qword ptr cs:xmmword_1400B71F0
0x140068274  jnb     short loc_140068285
0x140068276  movzx   edx, byte ptr [rcx]
0x140068279  inc     rcx
0x14006827c  mov     qword ptr cs:in+8, rcx
0x140068283  jmp     short loc_140068293
0x140068285  call    FillBuf
0x14006828a  mov     rcx, qword ptr cs:in+8
0x140068291  mov     edx, eax
0x140068293  cmp     edx, 0FFFFFFFFh
0x140068296  jz      loc_140068690
0x14006829c  movsxd  rax, edx
0x14006829f  test    byte ptr [rax+rbp], 10h
0x1400682a3  jnz     short loc_14006826D
0x1400682a5  cmp     edx, 25h ; '%'
0x1400682a8  jnz     loc_140068684
0x1400682ae  cmp     rcx, qword ptr cs:xmmword_1400B71F0
0x1400682b5  jnb     short loc_1400682C6
0x1400682b7  movzx   eax, byte ptr [rcx]
0x1400682ba  inc     rcx
0x1400682bd  mov     qword ptr cs:in+8, rcx
0x1400682c4  jmp     short loc_1400682D2
0x1400682c6  call    FillBuf
0x1400682cb  mov     rcx, qword ptr cs:in+8
0x1400682d2  cmp     eax, 21h ; '!'
0x1400682d5  jnz     short loc_140068325
0x1400682d7  cmp     rcx, qword ptr cs:xmmword_1400B71F0
0x1400682de  jnb     short loc_14006832F
0x1400682e0  movzx   ebx, byte ptr [rcx]
0x1400682e3  inc     rcx
0x1400682e6  mov     qword ptr cs:in+8, rcx
0x1400682ed  jmp     short loc_14006833D
0x1400682ef  cmp     eax, 0Dh
0x1400682f2  jz      loc_14006826D
0x1400682f8  cmp     eax, 0FFFFFFFFh
0x1400682fb  jz      loc_14006826D
0x140068301  cmp     rcx, qword ptr cs:xmmword_1400B71F0
0x140068308  jnb     short loc_140068319
0x14006830a  movzx   eax, byte ptr [rcx]
0x14006830d  inc     rcx
0x140068310  mov     qword ptr cs:in+8, rcx
0x140068317  jmp     short loc_140068325
0x140068319  call    FillBuf
0x14006831e  mov     rcx, qword ptr cs:in+8
0x140068325  cmp     eax, 0Ah
0x140068328  jnz     short loc_1400682EF
0x14006832a  jmp     loc_14006826D
0x14006832f  call    FillBuf
0x140068334  mov     rcx, qword ptr cs:in+8
0x14006833b  mov     ebx, eax
0x14006833d  cmp     ebx, 0FFFFFFFFh
0x140068340  jz      short loc_140068362
0x140068342  movsxd  rax, ebx
0x140068345  test    byte ptr [rax+rbp], 10h
0x140068349  jz      short loc_140068362
0x14006834b  cmp     ebx, 0Ah
0x14006834e  jz      loc_14006826D
0x140068354  cmp     ebx, 0Dh
0x140068357  jnz     loc_1400682D7
0x14006835d  jmp     loc_14006826D
0x140068362  mov     r10, cs:tokenbuf
0x140068369  add     rsi, rdi
0x14006836c  xor     ebp, ebp
0x14006836e  mov     r12d, 400h
0x140068374  cmp     ebx, 0FFFFFFFFh
0x140068377  jz      loc_140068425
0x14006837d  cmp     rdi, rsi
0x140068380  jb      short loc_1400683DF
0x140068382  mov     rax, [r10]
0x140068385  mov     [rsp+38h+arg_8], rax
0x14006838a  mov     rax, cs:procs
0x140068391  mov     r8d, [r10+8]
0x140068395  mov     rdx, [r10]
0x140068398  add     r8d, r12d
0x14006839b  mov     rcx, [rax+2F0h]
0x1400683a2  mov     r9, [rcx]
0x1400683a5  mov     rax, [r9+28h]
0x1400683a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400683ae  mov     r10, cs:tokenbuf
0x1400683b5  mov     [r10], rax
0x1400683b8  test    rax, rax
0x1400683bb  jz      loc_1400686DC
0x1400683c1  sub     edi, dword ptr cs:token
0x1400683c7  add     [r10+8], r12d
0x1400683cb  mov     esi, [r10+8]
0x1400683cf  movsxd  rdi, edi
0x1400683d2  add     rdi, rax
0x1400683d5  mov     cs:token, rax
0x1400683dc  add     rsi, rax
0x1400683df  mov     [rdi], bl
0x1400683e1  inc     rdi
0x1400683e4  mov     rax, qword ptr cs:in+8
0x1400683eb  cmp     rax, qword ptr cs:xmmword_1400B71F0
0x1400683f2  jnb     short loc_140068403
0x1400683f4  movzx   ebx, byte ptr [rax]
0x1400683f7  inc     rax
0x1400683fa  mov     qword ptr cs:in+8, rax
0x140068401  jmp     short loc_140068411
0x140068403  call    FillBuf
0x140068408  mov     r10, cs:tokenbuf
0x14006840f  mov     ebx, eax
0x140068411  movsxd  rax, ebx
0x140068414  lea     rcx, atmparse_chartab; "0"
0x14006841b  test    byte ptr [rax+rcx], 20h
0x14006841f  jz      loc_140068374
0x140068425  cmp     rdi, rsi
0x140068428  jb      short loc_14006847D
0x14006842a  mov     rax, cs:procs
0x140068431  mov     rdx, [r10]
0x140068434  mov     r8d, [r10+8]
0x140068438  mov     [rsp+38h+arg_10], rdx
0x14006843d  add     r8d, r12d
0x140068440  mov     rcx, [rax+2F0h]
0x140068447  mov     r9, [rcx]
0x14006844a  mov     rax, [r9+28h]
0x14006844e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140068453  mov     rcx, cs:tokenbuf
0x14006845a  mov     [rcx], rax
0x14006845d  test    rax, rax
0x140068460  jz      loc_1400686A8
0x140068466  sub     edi, dword ptr cs:token
0x14006846c  add     [rcx+8], r12d
0x140068470  movsxd  rdi, edi
0x140068473  add     rdi, rax
0x140068476  mov     cs:token, rax
0x14006847d  mov     [rdi], bpl
0x140068480  cmp     ebx, 0FFFFFFFFh
0x140068483  jz      short loc_1400684A8
0x140068485  movsxd  rax, ebx
0x140068488  lea     rcx, atmparse_chartab; "0"
0x14006848f  test    byte ptr [rax+rcx], 10h
0x140068493  jnz     short loc_1400684A8
0x140068495  mov     rax, qword ptr cs:in+8
0x14006849c  dec     rax
0x14006849f  mov     qword ptr cs:in+8, rax
0x1400684a6  mov     [rax], bl
0x1400684a8  mov     rcx, cs:token; Str1
0x1400684af  lea     rdx, aPsAdobe; "PS-Adobe-"
0x1400684b6  mov     ebx, 9
0x1400684bb  mov     r8d, ebx; MaxCount
0x1400684be  call    strncmp_0
0x1400684c3  test    eax, eax
0x1400684c5  jnz     loc_140068690
0x1400684cb  call    GetToken
0x1400684d0  mov     rdi, cs:token
0x1400684d7  cmp     byte ptr [rdi], 41h ; 'A'
0x1400684da  jz      short loc_14006854B
0x1400684dc  cmp     byte ptr [rdi], 52h ; 'R'
0x1400684df  jnz     loc_140068690
0x1400684e5  lea     r8d, [rbx+4]; MaxCount
0x1400684e9  mov     rcx, rdi; Str1
0x1400684ec  lea     rdx, aResourceCmap; "Resource-CMap"
0x1400684f3  call    strncmp_0
0x1400684f8  test    eax, eax
0x1400684fa  jz      short loc_140068541
0x1400684fc  lea     r8d, [rbx+7]; MaxCount
0x140068500  mov     rcx, rdi; Str1
0x140068503  lea     rdx, aResourceCidfon; "Resource-CIDFont"
0x14006850a  call    strncmp_0
0x14006850f  test    eax, eax
0x140068511  jnz     short loc_14006851A
0x140068513  mov     eax, ebx
0x140068515  jmp     loc_140068695
0x14006851a  mov     r8d, 0Dh; MaxCount
0x140068520  lea     rdx, aResourceFont; "Resource-Font"
0x140068527  mov     rcx, rdi; Str1
0x14006852a  call    strncmp_0
0x14006852f  test    eax, eax
0x140068531  jnz     loc_140068690
0x140068537  mov     eax, 7
0x14006853c  jmp     loc_140068695
0x140068541  mov     eax, 8
0x140068546  jmp     loc_140068695
0x14006854b  mov     r8d, 5; MaxCount
0x140068551  lea     rdx, aAdobe; "Adobe"
0x140068558  mov     rcx, rdi; Str1
0x14006855b  call    strncmp_0
0x140068560  test    eax, eax
0x140068562  jnz     loc_140068690
0x140068568  movsx   ecx, byte ptr [rdi+5]
0x14006856c  lea     rbx, [rdi+6]
0x140068570  sub     ecx, 43h ; 'C'
0x140068573  jz      loc_14006863C
0x140068579  sub     ecx, 1
0x14006857c  jz      loc_140068621
0x140068582  sub     ecx, 0Ch
0x140068585  jz      short loc_1400685D9
0x140068587  cmp     ecx, 3
0x14006858a  jnz     loc_140068690
0x140068590  lea     r8d, [rax+0Ah]; MaxCount
0x140068594  mov     rcx, rbx; Str1
0x140068597  lea     rdx, aTdcompfont; "tdCompFont"
0x14006859e  call    strncmp_0
0x1400685a3  test    eax, eax
0x1400685a5  jnz     loc_140068690
0x1400685ab  lea     rcx, [rbx+0Ah]; Str1
0x1400685af  cmp     [rcx], bpl
0x1400685b2  jnz     short loc_1400685BE
0x1400685b4  mov     eax, 2
0x1400685b9  jmp     loc_140068695
0x1400685be  lea     rdx, aBdy; "_BDY"
0x1400685c5  call    strcmp_0
0x1400685ca  neg     eax
0x1400685cc  sbb     eax, eax
0x1400685ce  and     eax, 0FFFFFFFEh
0x1400685d1  add     eax, 3
0x1400685d4  jmp     loc_140068695
0x1400685d9  mov     r8d, 0Fh; MaxCount
0x1400685df  lea     rdx, aRimogenitalfon; "rimogenitalFont"
0x1400685e6  mov     rcx, rbx; Str1
0x1400685e9  call    strncmp_0
0x1400685ee  test    eax, eax
0x1400685f0  jnz     loc_140068690
0x1400685f6  lea     rcx, [rbx+0Fh]; Str1
0x1400685fa  cmp     [rcx], bpl
0x1400685fd  jnz     short loc_140068609
0x1400685ff  mov     eax, 4
0x140068604  jmp     loc_140068695
0x140068609  lea     rdx, aCsa; "_CSA"
0x140068610  call    strcmp_0
0x140068615  neg     eax
0x140068617  sbb     eax, eax
0x140068619  and     eax, 0FFFFFFFCh
0x14006861c  add     eax, 5
0x14006861f  jmp     short loc_140068695
0x140068621  lea     rdx, aErivedfont; "erivedFont"
0x140068628  mov     rcx, rbx; Str1
0x14006862b  call    strcmp_0
0x140068630  neg     eax
0x140068632  sbb     eax, eax
0x140068634  and     eax, 0FFFFFFFBh
0x140068637  add     eax, 6
0x14006863a  jmp     short loc_140068695
0x14006863c  lea     rdx, aOmpositefontBd; "ompositeFont_BDY"
0x140068643  mov     rcx, rbx; Str1
0x140068646  call    strcmp_0
0x14006864b  test    eax, eax
0x14006864d  jz      short loc_14006867D
0x14006864f  lea     rdx, aOmpositefont; "ompositeFont"
0x140068656  mov     rcx, rbx; Str1
0x140068659  call    strcmp_0
0x14006865e  test    eax, eax
0x140068660  jz      short loc_14006867D
0x140068662  lea     rdx, aOmpositeencodi; "ompositeEncoding"
0x140068669  mov     rcx, rbx; Str1
0x14006866c  call    strcmp_0
0x140068671  neg     eax
0x140068673  sbb     eax, eax
0x140068675  and     eax, 0FFFFFFF9h
0x140068678  add     eax, 8
0x14006867b  jmp     short loc_140068695
0x14006867d  mov     eax, 0Ah
0x140068682  jmp     short loc_140068695
0x140068684  dec     rcx
0x140068687  mov     qword ptr cs:in+8, rcx
0x14006868e  mov     [rcx], dl
0x140068690  mov     eax, 1
0x140068695  mov     rbx, [rsp+38h+arg_0]
0x14006869a  mov     rbp, [rsp+38h+arg_18]
0x14006869f  add     rsp, 20h
0x1400686a3  pop     r12
0x1400686a5  pop     rdi
0x1400686a6  pop     rsi
0x1400686a7  retn
0x1400686a8  mov     rax, cs:procs
0x1400686af  lea     rdx, [rsp+38h+arg_10]
0x1400686b4  mov     rcx, [rax+2F0h]
0x1400686bb  mov     rax, [rcx]
0x1400686be  mov     rax, [rax+10h]
0x1400686c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400686c7  mov     rax, cs:tokenbuf
0x1400686ce  mov     ecx, 0FFFFFFFAh
0x1400686d3  mov     [rax+8], ebp
0x1400686d6  call    ParseError
0x1400686db  int     3; Trap to Debugger
0x1400686dc  mov     rax, cs:procs
0x1400686e3  lea     rdx, [rsp+38h+arg_8]
0x1400686e8  mov     rcx, [rax+2F0h]
0x1400686ef  mov     rax, [rcx]
0x1400686f2  mov     rax, [rax+10h]
0x1400686f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400686fb  mov     rax, cs:tokenbuf
0x140068702  mov     ecx, 0FFFFFFFAh
0x140068707  mov     [rax+8], ebp
0x14006870a  call    ParseError
```
