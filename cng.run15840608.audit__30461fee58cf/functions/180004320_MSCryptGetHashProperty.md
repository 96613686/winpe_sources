# MSCryptGetHashProperty

- ea: `0x180004320`
- end: `0x180004819`
- name: `MSCryptGetHashProperty`
- size: `1273`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001cc4`
- `0x180004820`
- `0x18007cfc4`
- `0x18007d330`
- `0x18007da38`
- `0x1800801a8`
- `0x180080c58`

## callees

- `0x180004320`
- `0x180005644`
- `0x18000743c`
- `0x1800082b0`
- `0x180011f00`
- `0x18009d746`
- `0x18009da40`

## string_xrefs

- `0x180004516`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000455b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800045af`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800046e5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18000474b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18009eaf1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18009eb4e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptGetHashProperty(
        _DWORD *a1,
        const wchar_t *a2,
        _QWORD *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  int v10; // ebp
  unsigned int v11; // edi
  int v12; // edx
  int v13; // r8d
  __int64 v15; // rax
  int v16; // edx
  int v17; // r8d
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 *v22; // r13
  __int64 v23; // rsi
  unsigned int v24; // edx
  unsigned int v25; // ecx
  __int64 v26; // rax
  _QWORD *v27; // rdx
  unsigned int v28; // r14d
  __int64 v29; // r12
  char *v30; // rbp
  __int64 v31; // rbx
  char *v32; // rcx
  const void *v33; // rdx
  __int64 v34; // rax
  int v35; // edx
  int v36; // r8d
  __int64 v37; // r9
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 *v42; // rdx
  __int64 v43; // rax
  unsigned int v45; // eax
  int v46; // eax
  BOOL v47; // eax
  __int64 v48; // rdx
  __int64 v49; // r8
  char v50; // [rsp+30h] [rbp-48h]

  if ( a6 )
  {
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        184);
    return v11;
  }
  if ( !a1 || (v10 = a1[1], v10 != 1297303617) && v10 != 1297303624 )
  {
    v11 = -1073741816;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      return v11;
    v50 = -63;
    goto LABEL_34;
  }
  if ( !a5 )
  {
    v37 = 3528;
LABEL_87:
    v11 = -1073741811;
    v39 = 3221225485LL;
    goto LABEL_88;
  }
  v11 = 0;
  if ( !wcscmp_0(a2, L"AlgorithmName") )
  {
    v38 = (unsigned int)(unsigned __int16)a1[2] - 1;
    if ( (unsigned int)v38 < 0x1A )
    {
      v42 = &rgHashAlgorithmDefaults[12 * v38];
      v43 = -1;
      while ( *(_WORD *)(v42[7] + 2 * v43++ + 2) != 0 )
        ;
      v45 = 2 * v43 + 2;
      *a5 = v45;
      if ( a3 )
      {
        if ( a4 >= v45 )
        {
          memmove(a3, (const void *)v42[7], v45);
          return v11;
        }
        return (unsigned int)-1073741789;
      }
      return v11;
    }
    v11 = -1073741816;
    v37 = 3539;
    v39 = 3221225480LL;
LABEL_88:
    DebugTraceError(v39, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v37);
    return v11;
  }
  if ( !wcscmp_0(a2, L"HashDigestLength") )
  {
    *a5 = 4;
    if ( !a3 )
      return v11;
    if ( a4 >= 4 )
    {
      *(_DWORD *)a3 = a1[3];
      return v11;
    }
    return (unsigned int)-1073741789;
  }
  if ( wcscmp_0(a2, L"ObjectLength") )
  {
    if ( !wcscmp_0(a2, L"MultiObjectLength") )
    {
      v34 = validateMSCryptHashAlgorithm(a1);
      if ( v34 )
      {
        *a5 = 8;
        if ( !a3 )
          return v11;
        if ( a4 >= 8 )
        {
          *a3 = __PAIR64__(*(_DWORD *)(v34 + 24), *(_DWORD *)(v34 + 20) - *(_DWORD *)(v34 + 24));
          return v11;
        }
        return (unsigned int)-1073741789;
      }
      v11 = -1073741637;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v35,
          v36,
          (unsigned int)"Status",
          187,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
          32);
      return v11;
    }
    if ( wcscmp_0(a2, L"HashOIDList") )
    {
      if ( !wcscmp_0(a2, L"HashBlockLength") )
      {
        v15 = validateMSCryptHashAlgorithm(a1);
        if ( v15 )
        {
          *a5 = 4;
          if ( !a3 )
            return v11;
          if ( a4 >= 4 )
          {
            *(_DWORD *)a3 = *(_DWORD *)(v15 + 28);
            return v11;
          }
          return (unsigned int)-1073741789;
        }
        v11 = -1073741637;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v16,
            v17,
            (unsigned int)"Status",
            187,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            120);
        return v11;
      }
      if ( !wcscmp_0(a2, L"IsKeyedHash") )
      {
        v41 = validateMSCryptHash(a1, 0);
        if ( v41 || (v40 = validateMSCryptHashAlgorithm(a1)) != 0 )
        {
          v46 = a1[2];
          *a5 = 4;
          if ( !a3 )
            return v11;
          if ( a4 < 4 )
            return (unsigned int)-1073741789;
          v47 = LODWORD(rgHashAlgorithmDefaults[12 * (unsigned int)(unsigned __int16)v46 - 8])
             || v41 && *(_DWORD *)(v41 + 28) == 1
             || v40 && *(_DWORD *)(v40 + 52) == 1;
          *(_DWORD *)a3 = v47;
          return v11;
        }
        v37 = 3737;
      }
      else
      {
        if ( wcscmp_0(a2, L"IsReusableHash") )
        {
          v11 = -1073741637;
          DebugTraceError(
            3221225659LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
            3812);
          return v11;
        }
        v49 = validateMSCryptHash(a1, 0);
        if ( v49 || (v48 = validateMSCryptHashAlgorithm(a1)) != 0 )
        {
          *a5 = 4;
          if ( !a3 )
            return v11;
          if ( a4 < 4 )
            return (unsigned int)-1073741789;
          *(_DWORD *)a3 = v49 && *(_DWORD *)(v49 + 24) == 1 || v48 && *(_DWORD *)(v48 + 40) == 1;
          return v11;
        }
        v37 = 3780;
      }
      goto LABEL_87;
    }
    v18 = (unsigned int)(unsigned __int16)a1[2] - 1;
    if ( (unsigned int)v18 < 0x1A )
    {
      _mm_lfence();
      v20 = 12 * v18;
      v21 = rgHashAlgorithmDefaults[v20 + 10];
      v22 = &rgHashAlgorithmDefaults[v20];
      v23 = LODWORD(rgHashAlgorithmDefaults[v20 + 9]);
      v24 = 16 * (v23 + 1);
      *a5 = v24;
      if ( (_DWORD)v23 )
      {
        v25 = 0;
        do
        {
          v26 = v25++;
          v24 += *(_DWORD *)(16 * v26 + v21);
          *a5 = v24;
        }
        while ( v25 < (unsigned int)v23 );
      }
      if ( a3 )
      {
        if ( a4 < v24 )
          return (unsigned int)-1073741789;
        *(_DWORD *)a3 = v23;
        v27 = a3 + 2;
        a3[1] = a3 + 2;
        if ( (_DWORD)v23 )
        {
          v28 = 0;
          v29 = 0;
          v30 = (char *)&a3[2 * v23 + 2];
          do
          {
            v31 = 2 * v29;
            LODWORD(v27[2 * v29]) = *(_DWORD *)(v22[10] + 16 * v29);
            v32 = v30;
            v33 = *(const void **)(v22[10] + 16 * v29 + 8);
            if ( !v33 )
              v32 = 0;
            *(_QWORD *)(a3[1] + 16 * v29 + 8) = v32;
            memmove(v30, v33, *(unsigned int *)(a3[1] + 16 * v29));
            v27 = (_QWORD *)a3[1];
            ++v28;
            ++v29;
            v30 += LODWORD(v27[v31]);
          }
          while ( v28 < (unsigned int)v23 );
        }
      }
      return v11;
    }
    v11 = -1073741816;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      return v11;
    v50 = 66;
LABEL_34:
    WPP_SF_sDsd(
      v19[3],
      (_DWORD)a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      v50);
    return v11;
  }
  if ( v10 == 1297303617 )
  {
    *a5 = 4;
    if ( a3 )
    {
      if ( a4 >= 4 )
      {
        *(_DWORD *)a3 = a1[4];
        return v11;
      }
      return (unsigned int)-1073741789;
    }
  }
  else
  {
    v11 = -1073741637;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v12,
        v13,
        (unsigned int)"Status",
        187,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        2);
  }
  return v11;
}

```

## disassembly

```asm
0x180004320  mov     [rsp+arg_8], rbx
0x180004325  mov     [rsp+arg_10], rsi
0x18000432a  push    rdi
0x18000432b  push    r12
0x18000432d  push    r13
0x18000432f  push    r14
0x180004331  push    r15
0x180004333  sub     rsp, 50h
0x180004337  cmp     [rsp+78h+arg_28], 0
0x18000433f  mov     r12d, r9d
0x180004342  mov     r15, r8
0x180004345  mov     rsi, rdx
0x180004348  mov     rbx, rcx
0x18000434b  jnz     loc_180004584
0x180004351  mov     [rsp+78h+arg_0], rbp
0x180004359  test    rcx, rcx
0x18000435c  jz      loc_18000452C
0x180004362  mov     ebp, [rcx+4]
0x180004365  cmp     ebp, 4D534841h
0x18000436b  jnz     loc_1800046FE
0x180004371  mov     r14, [rsp+78h+arg_20]
0x180004379  test    r14, r14
0x18000437c  jz      loc_180004764
0x180004382  lea     rdx, aAlgorithmname; "AlgorithmName"
0x180004389  mov     rcx, rsi; Str1
0x18000438c  call    wcscmp_0
0x180004391  xor     edi, edi
0x180004393  test    eax, eax
0x180004395  jz      loc_18000476F
0x18000439b  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800043a2  mov     rcx, rsi; Str1
0x1800043a5  call    wcscmp_0
0x1800043aa  test    eax, eax
0x1800043ac  jz      short loc_18000440E
0x1800043ae  lea     rdx, aObjectlength; "ObjectLength"
0x1800043b5  mov     rcx, rsi; Str1
0x1800043b8  call    wcscmp_0
0x1800043bd  test    eax, eax
0x1800043bf  jnz     short loc_18000442C
0x1800043c1  cmp     ebp, 4D534841h
0x1800043c7  jnz     loc_1800046B6
0x1800043cd  mov     dword ptr [r14], 4
0x1800043d4  test    r15, r15
0x1800043d7  jz      short loc_1800043E9
0x1800043d9  cmp     r12d, 4
0x1800043dd  jb      loc_1800044DD
0x1800043e3  mov     eax, [rbx+10h]
0x1800043e6  mov     [r15], eax
0x1800043e9  mov     rbp, [rsp+78h+arg_0]
0x1800043f1  lea     r11, [rsp+78h+var_28]
0x1800043f6  mov     eax, edi
0x1800043f8  mov     rbx, [r11+38h]
0x1800043fc  mov     rsi, [r11+40h]
0x180004400  mov     rsp, r11
0x180004403  pop     r15
0x180004405  pop     r14
0x180004407  pop     r13
0x180004409  pop     r12
0x18000440b  pop     rdi
0x18000440c  retn
0x18000440e  mov     dword ptr [r14], 4
0x180004415  test    r15, r15
0x180004418  jz      short loc_1800043E9
0x18000441a  cmp     r12d, 4
0x18000441e  jb      loc_1800044DD
0x180004424  mov     eax, [rbx+0Ch]
0x180004427  mov     [r15], eax
0x18000442a  jmp     short loc_1800043E9
0x18000442c  lea     rdx, aMultiobjectlen; "MultiObjectLength"
0x180004433  mov     rcx, rsi; Str1
0x180004436  call    wcscmp_0
0x18000443b  test    eax, eax
0x18000443d  jz      loc_18000470F
0x180004443  lea     rdx, aHashoidlist; "HashOIDList"
0x18000444a  mov     rcx, rsi; Str1
0x18000444d  call    wcscmp_0
0x180004452  test    eax, eax
0x180004454  jz      short loc_18000449B
0x180004456  lea     rdx, aHashblocklengt; "HashBlockLength"
0x18000445d  mov     rcx, rsi; Str1
0x180004460  call    wcscmp_0
0x180004465  test    eax, eax
0x180004467  jnz     loc_1800047CC
0x18000446d  mov     rcx, rbx
0x180004470  call    validateMSCryptHashAlgorithm
0x180004475  test    rax, rax
0x180004478  jz      short loc_1800044E7
0x18000447a  mov     dword ptr [r14], 4
0x180004481  test    r15, r15
0x180004484  jz      loc_1800043E9
0x18000448a  cmp     r12d, 4
0x18000448e  jb      short loc_1800044DD
0x180004490  mov     eax, [rax+1Ch]
0x180004493  mov     [r15], eax
0x180004496  jmp     loc_1800043E9
0x18000449b  mov     eax, [rbx+8]
0x18000449e  movzx   ecx, ax
0x1800044a1  dec     ecx
0x1800044a3  cmp     ecx, 1Ah
0x1800044a6  jb      loc_1800045DC
0x1800044ac  mov     edi, 0C0000008h
0x1800044b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044b8  lea     rax, WPP_GLOBAL_Control
0x1800044bf  cmp     rcx, rax
0x1800044c2  jz      loc_1800043E9
0x1800044c8  mov     eax, [rcx+2Ch]
0x1800044cb  test    al, 1
0x1800044cd  jz      loc_1800043E9
0x1800044d3  mov     dword ptr [rsp+78h+var_48], 0E42h
0x1800044db  jmp     short loc_18000455B
0x1800044dd  mov     edi, 0C0000023h
0x1800044e2  jmp     loc_1800043E9
0x1800044e7  mov     edi, 0C00000BBh
0x1800044ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044f3  lea     rax, WPP_GLOBAL_Control
0x1800044fa  cmp     rcx, rax
0x1800044fd  jz      loc_1800043E9
0x180004503  mov     eax, [rcx+2Ch]
0x180004506  test    al, 1
0x180004508  jz      loc_1800043E9
0x18000450e  mov     dword ptr [rsp+78h+var_48], 0E78h
0x180004516  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000451d  mov     [rsp+78h+var_50], rax
0x180004522  mov     [rsp+78h+var_58], 0C00000BBh
0x18000452a  jmp     short loc_18000456F
0x18000452c  mov     edi, 0C0000008h
0x180004531  mov     rcx, cs:WPP_GLOBAL_Control
0x180004538  lea     rax, WPP_GLOBAL_Control
0x18000453f  cmp     rcx, rax
0x180004542  jz      loc_1800043E9
0x180004548  mov     eax, [rcx+2Ch]
0x18000454b  test    al, 1
0x18000454d  jz      loc_1800043E9
0x180004553  mov     dword ptr [rsp+78h+var_48], 0DC1h
0x18000455b  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004562  mov     [rsp+78h+var_50], rax
0x180004567  mov     [rsp+78h+var_58], 0C0000008h
0x18000456f  mov     rcx, [rcx+18h]
0x180004573  lea     r9, aStatus; "Status"
0x18000457a  call    WPP_SF_sDsd
0x18000457f  jmp     loc_1800043E9
0x180004584  mov     edi, 0C000000Dh
0x180004589  mov     rcx, cs:WPP_GLOBAL_Control
0x180004590  lea     rax, WPP_GLOBAL_Control
0x180004597  cmp     rcx, rax
0x18000459a  jz      loc_1800043F1
0x1800045a0  mov     eax, [rcx+2Ch]
0x1800045a3  test    al, 1
0x1800045a5  jz      loc_1800043F1
0x1800045ab  mov     rcx, [rcx+18h]
0x1800045af  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800045b6  mov     dword ptr [rsp+78h+var_48], 0DB8h
0x1800045be  lea     r9, aStatus; "Status"
0x1800045c5  mov     [rsp+78h+var_50], rax
0x1800045ca  mov     [rsp+78h+var_58], 0C000000Dh
0x1800045d2  call    WPP_SF_sDsd
0x1800045d7  jmp     loc_1800043F1
0x1800045dc  lfence
0x1800045df  lea     rax, rgHashAlgorithmDefaults
0x1800045e6  lea     rcx, [rcx+rcx*2]
0x1800045ea  shl     rcx, 5
0x1800045ee  mov     r8, [rcx+rax+50h]
0x1800045f3  lea     r13, [rcx+rax]
0x1800045f7  mov     esi, [rcx+rax+48h]
0x1800045fb  lea     edx, [rsi+1]
0x1800045fe  shl     edx, 4
0x180004601  mov     [r14], edx
0x180004604  test    esi, esi
0x180004606  jz      short loc_180004623
0x180004608  mov     ecx, edi
0x18000460a  nop     word ptr [rax+rax+00h]
0x180004610  mov     eax, ecx
0x180004612  inc     ecx
0x180004614  shl     rax, 4
0x180004618  add     edx, [rax+r8]
0x18000461c  mov     [r14], edx
0x18000461f  cmp     ecx, esi
0x180004621  jb      short loc_180004610
0x180004623  test    r15, r15
0x180004626  jz      loc_1800043E9
0x18000462c  cmp     r12d, edx
0x18000462f  jb      loc_1800044DD
0x180004635  mov     [r15], esi
0x180004638  lea     rdx, [r15+10h]
0x18000463c  mov     [r15+8], rdx
0x180004640  test    esi, esi
0x180004642  jz      loc_1800043E9
0x180004648  lea     rbp, [rsi+1]
0x18000464c  mov     r14d, edi
0x18000464f  shl     rbp, 4
0x180004653  mov     r12, rdi
0x180004656  add     rbp, r15
0x180004659  nop     dword ptr [rax+00000000h]
0x180004660  mov     rax, [r13+50h]
0x180004664  mov     rbx, r12
0x180004667  add     rbx, rbx
0x18000466a  mov     ecx, [rax+rbx*8]
0x18000466d  mov     [rdx+rbx*8], ecx
0x180004670  mov     rcx, rbp
0x180004673  mov     rax, [r13+50h]
0x180004677  mov     rdx, [rax+rbx*8+8]; Src
0x18000467c  mov     rax, [r15+8]
0x180004680  test    rdx, rdx
0x180004683  cmovz   rcx, rdi
0x180004687  mov     [rax+rbx*8+8], rcx
0x18000468c  mov     rcx, rbp; void *
0x18000468f  mov     rax, [r15+8]
0x180004693  mov     r8d, [rax+rbx*8]; Size
0x180004697  call    memmove
0x18000469c  mov     rdx, [r15+8]
0x1800046a0  inc     r14d
0x1800046a3  inc     r12
0x1800046a6  mov     eax, [rdx+rbx*8]
0x1800046a9  add     rbp, rax
0x1800046ac  cmp     r14d, esi
0x1800046af  jb      short loc_180004660
0x1800046b1  jmp     loc_1800043E9
0x1800046b6  mov     edi, 0C00000BBh
0x1800046bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046c2  lea     rax, WPP_GLOBAL_Control
0x1800046c9  cmp     rcx, rax
0x1800046cc  jz      loc_1800043E9
0x1800046d2  mov     eax, [rcx+2Ch]
0x1800046d5  test    al, 1
0x1800046d7  jz      loc_1800043E9
0x1800046dd  mov     dword ptr [rsp+78h+var_48], 0E02h
0x1800046e5  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800046ec  mov     [rsp+78h+var_50], rax
0x1800046f1  mov     [rsp+78h+var_58], 0C00000BBh
0x1800046f9  jmp     loc_18000456F
0x1800046fe  cmp     ebp, 4D534848h
0x180004704  jnz     loc_18000452C
0x18000470a  jmp     loc_180004371
0x18000470f  mov     rcx, rbx
0x180004712  call    validateMSCryptHashAlgorithm
0x180004717  test    rax, rax
0x18000471a  jnz     short loc_180004795
0x18000471c  mov     edi, 0C00000BBh
0x180004721  mov     rcx, cs:WPP_GLOBAL_Control
0x180004728  lea     rax, WPP_GLOBAL_Control
0x18000472f  cmp     rcx, rax
0x180004732  jz      loc_1800043E9
0x180004738  mov     eax, [rcx+2Ch]
0x18000473b  test    al, 1
0x18000473d  jz      loc_1800043E9
0x180004743  mov     dword ptr [rsp+78h+var_48], 0E20h
0x18000474b  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004752  mov     [rsp+78h+var_50], rax
0x180004757  mov     [rsp+78h+var_58], 0C00000BBh
0x18000475f  jmp     loc_18000456F
0x180004764  mov     r9d, 0DC8h
0x18000476a  jmp     loc_18009EAE0
0x18000476f  mov     eax, [rbx+8]
0x180004772  movzx   ecx, ax
0x180004775  dec     ecx
0x180004777  cmp     ecx, 1Ah
0x18000477a  jb      loc_18009E9E8
0x180004780  mov     edi, 0C0000008h
0x180004785  mov     r9d, 0DD3h
0x18000478b  mov     ecx, 0C0000008h
0x180004790  jmp     loc_18009EAEA
0x180004795  mov     dword ptr [r14], 8
0x18000479c  test    r15, r15
0x18000479f  jz      loc_1800043E9
0x1800047a5  cmp     r12d, 8
0x1800047a9  jb      loc_1800044DD
0x1800047af  mov     ecx, [rax+18h]
0x1800047b2  mov     eax, [rax+14h]
0x1800047b5  sub     eax, ecx
0x1800047b7  mov     dword ptr [rsp+78h+var_38+4], ecx
0x1800047bb  mov     dword ptr [rsp+78h+var_38], eax
0x1800047bf  mov     rax, [rsp+78h+var_38]
0x1800047c4  mov     [r15], rax
0x1800047c7  jmp     loc_1800043E9
0x1800047cc  lea     rdx, aIskeyedhash; "IsKeyedHash"
0x1800047d3  mov     rcx, rsi; Str1
0x1800047d6  call    wcscmp_0
0x1800047db  test    eax, eax
0x1800047dd  jnz     loc_18009EAA0
0x1800047e3  mov     rcx, rbx
0x1800047e6  mov     rdx, rdi
0x1800047e9  call    validateMSCryptHash
0x1800047ee  mov     r8, rax
0x1800047f1  test    rax, rax
0x1800047f4  jnz     loc_18009EA41
0x1800047fa  mov     rcx, rbx
0x1800047fd  call    validateMSCryptHashAlgorithm
0x180004802  mov     rdx, rax
0x180004805  test    rax, rax
0x180004808  jnz     loc_18009EA41
0x18000480e  mov     r9d, 0E99h
0x180004814  jmp     loc_18009EAE0
0x18009e9e8  lea     rdx, [rcx+rcx*2]
0x18009e9ec  lea     rax, rgHashAlgorithmDefaults
0x18009e9f3  shl     rdx, 5
0x18009e9f7  add     rdx, rax
0x18009e9fa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18009ea01  mov     rcx, [rdx+38h]
0x18009ea05  cmp     [rcx+rax*2+2], di
0x18009ea0a  lea     rax, [rax+1]
  ... truncated ...
```
