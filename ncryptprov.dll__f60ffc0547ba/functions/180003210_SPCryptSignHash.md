# SPCryptSignHash

- ea: `0x180003210`
- end: `0x18000376a`
- name: `SPCryptSignHash`
- size: `1370`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180003068`
- `0x180003210`
- `0x180004400`
- `0x1800086d0`
- `0x180009440`
- `0x18000af80`
- `0x18000b250`
- `0x180014160`
- `0x180035064`
- `0x18005df90`
- `0x18005e3c4`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180003429`
- `bcrypt!BCryptGetProperty` at `0x180003429`

## string_xrefs

- `0x180003277`: `onecore\ds\security\cryptoapi\ncrypt\storage\sign.c`
- `0x1800033a9`: `onecore\ds\security\cryptoapi\ncrypt\storage\sign.c`
- `0x1800033d2`: `onecore\ds\security\cryptoapi\ncrypt\storage\sign.c`
- `0x180003482`: `onecore\ds\security\cryptoapi\ncrypt\storage\sign.c`
- `0x180003601`: `onecore\ds\security\cryptoapi\ncrypt\storage\sign.c`
- `0x1800036bf`: `onecore\ds\security\cryptoapi\ncrypt\storage\sign.c`

## pseudocode

```c
__int64 __fastcall SPCryptSignHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        UCHAR *a4,
        ULONG a5,
        __int64 a6,
        int a7,
        _DWORD *a8,
        unsigned int a9)
{
  __int64 v11; // rsi
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  int v15; // edx
  __int64 v16; // r15
  int v17; // r14d
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  NTSTATUS Property; // eax
  __int64 v22; // r9
  void *v23; // rcx
  ULONG v24; // r13d
  __int64 v25; // r9
  __int64 v26; // rcx
  UCHAR *v27; // rdi
  void *v28; // r12
  __int64 v29; // rdx
  __int64 v30; // rbx
  bool v31; // zf
  UCHAR *v32; // rax
  int v33; // eax
  UCHAR *v34; // r8
  int v35; // ebx
  int v36; // r8d
  UCHAR *v37; // rax
  __int64 v39; // [rsp-20h] [rbp-A0h] BYREF
  int v40; // [rsp+30h] [rbp-50h]
  _BYTE v41[24]; // [rsp+38h] [rbp-48h] BYREF
  UCHAR *v42; // [rsp+80h] [rbp+0h]
  __int64 v43; // [rsp+88h] [rbp+8h]
  UCHAR pbOutput[4]; // [rsp+90h] [rbp+10h] BYREF
  ULONG pcbResult; // [rsp+94h] [rbp+14h] BYREF

  v42 = a4;
  v43 = a3;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  v11 = KspValidateKeyHandle(a2);
  if ( v11 )
  {
    if ( !a8 )
    {
      v12 = -2146893785;
      v13 = 522;
      v14 = 2148073511LL;
      goto LABEL_3;
    }
    if ( (unsigned int)Feature_PQ_NCrypt_External_Mu_And_PKCS8__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( (a9 & 0xFFFFFF15) != 0 )
      {
        v13 = 535;
LABEL_9:
        v12 = -2146893815;
        v14 = 2148073481LL;
        goto LABEL_3;
      }
    }
    else if ( (a9 & 0xFFFFFF95) != 0 )
    {
      v13 = 547;
      goto LABEL_9;
    }
    v16 = 64;
    if ( (a9 & 8) != 0 )
    {
      v17 = 8;
    }
    else if ( (a9 & 2) != 0 )
    {
      v17 = 2;
    }
    else if ( (a9 & 0x20) != 0 )
    {
      v17 = 32;
    }
    else
    {
      v17 = 0;
      if ( (unsigned int)Feature_PQ_NCrypt_External_Mu_And_PKCS8__private_IsEnabledDeviceUsageNoInline()
        && (a9 & 0x80u) != 0 )
      {
        v17 = 64;
      }
    }
    if ( (*(_BYTE *)(v11 + 40) & 2) == 0 )
    {
      v12 = -2146893808;
      v13 = 582;
      v14 = 2148073488LL;
      goto LABEL_3;
    }
    v18 = *(_DWORD *)(*(_QWORD *)(v11 + 64) + 32LL);
    if ( !a6 )
    {
      if ( v18 == 196609 || v18 == 196620 )
        goto LABEL_37;
      if ( a3 || v17 )
      {
        v12 = -2146893785;
        DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\sign.c", 602);
        return v12;
      }
      v19 = v18 - 196615;
      if ( v19 && (v20 = v19 - 1) != 0 && (unsigned int)(v20 - 1) > 1 )
      {
LABEL_37:
        v23 = *(void **)(v11 + 104);
      }
      else
      {
        if ( !*(_QWORD *)(v11 + 128) )
        {
          Property = OpenEccAltSigKey(v11, 1);
          v12 = Property;
          if ( Property < 0 )
          {
            v22 = 618;
LABEL_34:
            DebugTraceError(
              (unsigned int)Property,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\sign.c",
              v22);
LABEL_102:
            if ( v12 == -2146893778 )
              return v12;
            goto LABEL_103;
          }
        }
        v23 = *(void **)(v11 + 128);
      }
      if ( !v23 )
        return (unsigned int)-2146893813;
      Property = BCryptGetProperty(v23, L"SignatureLength", pbOutput, 4u, &pcbResult, 0);
      v12 = Property;
      if ( !Property )
      {
        *a8 = *(_DWORD *)pbOutput;
        return v12;
      }
      v22 = 646;
      goto LABEL_34;
    }
    if ( v18 == 196620 )
    {
      v24 = a5;
      if ( !a4 && a5 )
      {
        v25 = 666;
        goto LABEL_47;
      }
      if ( (v17 & 0x40) != 0 && a3 )
      {
        v25 = 674;
        goto LABEL_47;
      }
    }
    else if ( !a4 || (v24 = a5) == 0 )
    {
      v25 = 685;
LABEL_47:
      v12 = -2146893785;
      v26 = 2148073511LL;
LABEL_48:
      DebugTraceError(v26, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\sign.c", v25);
LABEL_104:
      KspCryptAuditCryptOperation(0, v15, v11, 2485, v12);
      return v12;
    }
    Property = KspCheckStrongKeyAndUnprotect(v11, a9);
    v12 = Property;
    if ( Property < 0 )
    {
      v22 = 700;
      goto LABEL_34;
    }
    v27 = 0;
    if ( *(_DWORD *)(*(_QWORD *)(v11 + 64) + 32LL) == 196615
      || *(_DWORD *)(*(_QWORD *)(v11 + 64) + 32LL) == 196616
      || *(_DWORD *)(*(_QWORD *)(v11 + 64) + 32LL) == 196617
      || *(_DWORD *)(*(_QWORD *)(v11 + 64) + 32LL) == 196618 )
    {
      if ( !*(_QWORD *)(v11 + 136) )
      {
        Property = OpenEccAltSigKey(v11, 0);
        v12 = Property;
        if ( Property < 0 )
        {
          v22 = 715;
          goto LABEL_34;
        }
      }
      v28 = *(void **)(v11 + 136);
      goto LABEL_88;
    }
    if ( *(_DWORD *)(*(_QWORD *)(v11 + 64) + 32LL) != 196620 )
    {
      v28 = *(void **)(v11 + 112);
LABEL_88:
      v30 = v43;
      goto LABEL_89;
    }
    if ( !(unsigned int)Feature_PQ_NCrypt_External_Mu_And_PKCS8__private_IsEnabledDeviceUsageNoInline() )
    {
      v28 = 0;
      goto LABEL_88;
    }
    v28 = *(void **)(v11 + 112);
    v30 = v43;
    if ( (v17 & 0x40) != 0 || v24 < 0x8000 )
      goto LABEL_89;
    if ( v17 == 32 )
    {
      if ( !v43 )
        goto LABEL_72;
      v31 = *(_QWORD *)(v43 + 16) == 0;
    }
    else
    {
      v31 = v43 == 0;
    }
    if ( !v31 )
    {
LABEL_89:
      v34 = v42;
      goto LABEL_90;
    }
LABEL_72:
    if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x40
      || (unsigned __int64)(g_ulAdditionalProbeSize + 72) < 0x40
      || !(unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 72, v29)
      || &v39 == (__int64 *)-80LL
      || (v40 = 1801679955, (v27 = v41) == 0) )
    {
      v32 = (UCHAR *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(72);
      v27 = v32;
      if ( v32 )
      {
        *(_DWORD *)v32 = 1885431112;
        v27 = v32 + 8;
      }
    }
    if ( !v27 )
    {
      v12 = -2146893810;
      v25 = 757;
      v26 = 2148073486LL;
      goto LABEL_48;
    }
    v33 = ComputeMlDsaExternalMu(v28, v30, v42, v24, v27);
    v12 = v33;
    if ( v33 < 0 )
    {
      DebugTraceError((unsigned int)v33, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\sign.c", 772);
      goto LABEL_97;
    }
    v34 = v27;
    v24 = 64;
    v17 = 64;
    v30 = 0;
LABEL_90:
    v35 = (*(__int64 (__fastcall **)(void *, __int64, UCHAR *, _QWORD, __int64, int, _DWORD *, int))(*(_QWORD *)(v11 + 168) + 144LL))(
            v28,
            v30,
            v34,
            v24,
            a6,
            a7,
            a8,
            v17);
    if ( v35 >= 0 )
    {
      v12 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)WPP_GLOBAL_Control,
          v36,
          (unsigned int)"Status",
          v35,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\sign.c",
          33);
      v12 = NormalizeNteStatus((unsigned int)v35);
    }
    if ( !v27 )
    {
LABEL_101:
      if ( !v12 )
        return v12;
      goto LABEL_102;
    }
LABEL_97:
    v37 = v27;
    do
    {
      *v37++ = 0;
      --v16;
    }
    while ( v16 );
    if ( *((_DWORD *)v27 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    goto LABEL_101;
  }
  v12 = -2146893786;
  v13 = 515;
  v14 = 2148073510LL;
LABEL_3:
  DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\sign.c", v13);
LABEL_103:
  if ( a6 )
    goto LABEL_104;
  return v12;
}

```

## disassembly

```asm
0x180003210  push    rbp
0x180003212  push    rbx
0x180003213  push    rsi
0x180003214  push    rdi
0x180003215  push    r12
0x180003217  push    r13
0x180003219  push    r14
0x18000321b  push    r15
0x18000321d  sub     rsp, 78h
0x180003221  lea     rbp, [rsp+50h]
0x180003226  mov     rax, cs:__security_cookie
0x18000322d  xor     rax, rbp
0x180003230  mov     [rbp+60h+var_48], rax
0x180003234  mov     rcx, rdx
0x180003237  mov     [rbp+60h+var_60], r9
0x18000323b  mov     r12, r9
0x18000323e  mov     [rbp+60h+var_58], r8
0x180003242  mov     rdi, r8
0x180003245  mov     dword ptr [rbp+60h+pbOutput], 0
0x18000324c  mov     [rbp+60h+var_4C], 0
0x180003253  call    KspValidateKeyHandle
0x180003258  mov     rsi, rax
0x18000325b  test    rax, rax
0x18000325e  jnz     short loc_180003288
0x180003260  mov     ebx, 80090026h
0x180003265  mov     r9d, 203h
0x18000326b  mov     ecx, 80090026h
0x180003270  lea     rdx, aStatus; "Status"
0x180003277  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000327e  call    DebugTraceError
0x180003283  jmp     loc_18000372C
0x180003288  mov     r13, [rbp+60h+arg_38]
0x18000328f  test    r13, r13
0x180003292  jnz     short loc_1800032A6
0x180003294  mov     ebx, 80090027h
0x180003299  mov     r9d, 20Ah
0x18000329f  mov     ecx, 80090027h
0x1800032a4  jmp     short loc_180003270
0x1800032a6  call    Feature_PQ_NCrypt_External_Mu_And_PKCS8__private_IsEnabledDeviceUsageNoInline
0x1800032ab  mov     ebx, [rbp+60h+arg_40]
0x1800032b1  test    eax, eax
0x1800032b3  jz      short loc_1800032CF
0x1800032b5  test    ebx, 0FFFFFF15h
0x1800032bb  jz      short loc_1800032DF
0x1800032bd  mov     r9d, 217h
0x1800032c3  mov     ebx, 80090009h
0x1800032c8  mov     ecx, 80090009h
0x1800032cd  jmp     short loc_180003270
0x1800032cf  test    ebx, 0FFFFFF95h
0x1800032d5  jz      short loc_1800032DF
0x1800032d7  mov     r9d, 223h
0x1800032dd  jmp     short loc_1800032C3
0x1800032df  mov     r15d, 40h ; '@'
0x1800032e5  test    bl, 8
0x1800032e8  jz      short loc_1800032F0
0x1800032ea  lea     r14d, [r15-38h]
0x1800032ee  jmp     short loc_18000331D
0x1800032f0  test    bl, 2
0x1800032f3  jz      short loc_1800032FD
0x1800032f5  mov     r14d, 2
0x1800032fb  jmp     short loc_18000331D
0x1800032fd  test    bl, 20h
0x180003300  jz      short loc_18000330A
0x180003302  mov     r14d, 20h ; ' '
0x180003308  jmp     short loc_18000331D
0x18000330a  xor     r14d, r14d
0x18000330d  call    Feature_PQ_NCrypt_External_Mu_And_PKCS8__private_IsEnabledDeviceUsageNoInline
0x180003312  test    eax, eax
0x180003314  jz      short loc_18000331D
0x180003316  test    bl, 80h
0x180003319  cmovnz  r14d, r15d
0x18000331d  test    byte ptr [rsi+28h], 2
0x180003321  jnz     short loc_180003338
0x180003323  mov     ebx, 80090010h
0x180003328  mov     r9d, 246h
0x18000332e  mov     ecx, 80090010h
0x180003333  jmp     loc_180003270
0x180003338  cmp     [rbp+60h+arg_28], 0
0x180003340  mov     rax, [rsi+40h]
0x180003344  mov     ecx, [rax+20h]
0x180003347  jnz     loc_180003452
0x18000334d  cmp     ecx, 30001h
0x180003353  jz      loc_1800033F4
0x180003359  cmp     ecx, 3000Ch
0x18000335f  jz      loc_1800033F4
0x180003365  test    rdi, rdi
0x180003368  jnz     short loc_1800033CC
0x18000336a  test    r14d, r14d
0x18000336d  jnz     short loc_1800033CC
0x18000336f  sub     ecx, 30007h
0x180003375  jz      short loc_180003386
0x180003377  sub     ecx, 1
0x18000337a  jz      short loc_180003386
0x18000337c  sub     ecx, 1
0x18000337f  jz      short loc_180003386
0x180003381  cmp     ecx, 1
0x180003384  jnz     short loc_1800033F4
0x180003386  cmp     qword ptr [rsi+80h], 0
0x18000338e  jnz     short loc_1800033C3
0x180003390  mov     edx, 1
0x180003395  mov     rcx, rsi
0x180003398  call    OpenEccAltSigKey
0x18000339d  mov     ebx, eax
0x18000339f  test    eax, eax
0x1800033a1  jns     short loc_1800033C3
0x1800033a3  mov     r9d, 26Ah
0x1800033a9  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800033b0  mov     ecx, eax
0x1800033b2  lea     rdx, aStatus; "Status"
0x1800033b9  call    DebugTraceError
0x1800033be  jmp     loc_180003724
0x1800033c3  mov     rcx, [rsi+80h]
0x1800033ca  jmp     short loc_1800033F8
0x1800033cc  mov     r9d, 25Ah
0x1800033d2  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800033d9  lea     rdx, aStatus; "Status"
0x1800033e0  mov     ecx, 80090027h
0x1800033e5  mov     ebx, 80090027h
0x1800033ea  call    DebugTraceError
0x1800033ef  jmp     loc_18000374A
0x1800033f4  mov     rcx, [rsi+68h]; hObject
0x1800033f8  test    rcx, rcx
0x1800033fb  jnz     short loc_180003407
0x1800033fd  mov     ebx, 8009000Bh
0x180003402  jmp     loc_18000374A
0x180003407  lea     rax, [rbp+60h+var_4C]
0x18000340b  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x180003413  mov     r9d, 4; cbOutput
0x180003419  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x18000341e  lea     r8, [rbp+60h+pbOutput]; pbOutput
0x180003422  lea     rdx, aSignaturelengt; "SignatureLength"
0x180003429  call    cs:__imp_BCryptGetProperty
0x180003430  nop     dword ptr [rax+rax+00h]
0x180003435  mov     ebx, eax
0x180003437  test    eax, eax
0x180003439  jz      short loc_180003446
0x18000343b  mov     r9d, 286h
0x180003441  jmp     loc_1800033A9
0x180003446  mov     eax, dword ptr [rbp+60h+pbOutput]
0x180003449  mov     [r13+0], eax
0x18000344d  jmp     loc_18000374A
0x180003452  cmp     ecx, 3000Ch
0x180003458  jz      short loc_180003493
0x18000345a  test    r12, r12
0x18000345d  jz      short loc_18000346B
0x18000345f  mov     r13d, [rbp+60h+arg_20]
0x180003466  test    r13d, r13d
0x180003469  jnz     short loc_1800034BE
0x18000346b  mov     r9d, 2ADh
0x180003471  mov     ebx, 80090027h
0x180003476  mov     ecx, 80090027h
0x18000347b  lea     rdx, aStatus; "Status"
0x180003482  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003489  call    DebugTraceError
0x18000348e  jmp     loc_180003736
0x180003493  mov     r13d, [rbp+60h+arg_20]
0x18000349a  test    r12, r12
0x18000349d  jnz     short loc_1800034AC
0x18000349f  test    r13d, r13d
0x1800034a2  jz      short loc_1800034AC
0x1800034a4  mov     r9d, 29Ah
0x1800034aa  jmp     short loc_180003471
0x1800034ac  test    r15b, r14b
0x1800034af  jz      short loc_1800034BE
0x1800034b1  test    rdi, rdi
0x1800034b4  jz      short loc_1800034BE
0x1800034b6  mov     r9d, 2A2h
0x1800034bc  jmp     short loc_180003471
0x1800034be  mov     edx, ebx
0x1800034c0  mov     rcx, rsi
0x1800034c3  call    KspCheckStrongKeyAndUnprotect
0x1800034c8  mov     ebx, eax
0x1800034ca  test    eax, eax
0x1800034cc  jns     short loc_1800034D9
0x1800034ce  mov     r9d, 2BCh
0x1800034d4  jmp     loc_1800033A9
0x1800034d9  mov     rcx, [rsi+40h]
0x1800034dd  xor     edi, edi
0x1800034df  mov     edx, [rcx+20h]
0x1800034e2  sub     edx, 30007h
0x1800034e8  jz      loc_180003628
0x1800034ee  sub     edx, 1
0x1800034f1  jz      loc_180003628
0x1800034f7  sub     edx, 1
0x1800034fa  jz      loc_180003628
0x180003500  sub     edx, 1
0x180003503  jz      loc_180003628
0x180003509  cmp     edx, 2
0x18000350c  jz      short loc_180003517
0x18000350e  mov     r12, [rsi+70h]
0x180003512  jmp     loc_180003653
0x180003517  call    Feature_PQ_NCrypt_External_Mu_And_PKCS8__private_IsEnabledDeviceUsageNoInline
0x18000351c  test    eax, eax
0x18000351e  jnz     short loc_180003528
0x180003520  xor     r12d, r12d
0x180003523  jmp     loc_180003653
0x180003528  mov     r12, [rsi+70h]
0x18000352c  mov     rbx, [rbp+60h+var_58]
0x180003530  test    r15b, r14b
0x180003533  jnz     loc_180003657
0x180003539  cmp     r13d, 8000h
0x180003540  jb      loc_180003657
0x180003546  cmp     r14d, 20h ; ' '
0x18000354a  jnz     short loc_180003557
0x18000354c  test    rbx, rbx
0x18000354f  jz      short loc_180003560
0x180003551  cmp     [rbx+10h], rdi
0x180003555  jmp     short loc_18000355A
0x180003557  test    rbx, rbx
0x18000355a  jnz     loc_180003657
0x180003560  cmp     cs:g_ulMaxStackAllocSize, r15
0x180003567  jb      short loc_1800035A1
0x180003569  mov     rcx, cs:g_ulAdditionalProbeSize
0x180003570  add     rcx, 48h ; 'H'
0x180003574  cmp     rcx, r15
0x180003577  jb      short loc_1800035A1
0x180003579  call    VerifyStackAvailable
0x18000357e  test    eax, eax
0x180003580  jz      short loc_1800035A1
0x180003582  mov     eax, [rsp+0B0h+var_B0]
0x180003585  sub     rsp, 50h
0x180003589  lea     rdi, [rsp+100h+var_B0]
0x18000358e  mov     eax, [rdi]
0x180003590  test    rdi, rdi
0x180003593  jz      short loc_1800035A1
0x180003595  mov     dword ptr [rdi], 6B637453h
0x18000359b  add     rdi, 8
0x18000359f  jnz     short loc_1800035C4
0x1800035a1  mov     rax, cs:g_pfnAllocate
0x1800035a8  mov     ecx, 48h ; 'H'
0x1800035ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035b2  mov     rdi, rax
0x1800035b5  test    rax, rax
0x1800035b8  jz      short loc_1800035C4
0x1800035ba  mov     dword ptr [rax], 70616548h
0x1800035c0  add     rdi, 8
0x1800035c4  test    rdi, rdi
0x1800035c7  jnz     short loc_1800035DE
0x1800035c9  mov     ebx, 8009000Eh
0x1800035ce  mov     r9d, 2F5h
0x1800035d4  mov     ecx, 8009000Eh
0x1800035d9  jmp     loc_18000347B
0x1800035de  mov     r8, [rbp+60h+var_60]
0x1800035e2  mov     r9d, r13d
0x1800035e5  mov     rdx, rbx
0x1800035e8  mov     [rsp+100h+var_E0], rdi; pbOutput
0x1800035ed  mov     rcx, r12; hKey
0x1800035f0  call    ComputeMlDsaExternalMu
0x1800035f5  mov     ebx, eax
0x1800035f7  test    eax, eax
0x1800035f9  jns     short loc_18000361B
0x1800035fb  mov     r9d, 304h
0x180003601  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003608  lea     rdx, aStatus; "Status"
0x18000360f  mov     ecx, eax
0x180003611  call    DebugTraceError
0x180003616  jmp     loc_1800036F9
0x18000361b  mov     r8, rdi
0x18000361e  mov     r13d, r15d
0x180003621  mov     r14d, r15d
0x180003624  xor     ebx, ebx
0x180003626  jmp     short loc_18000365B
0x180003628  cmp     [rsi+88h], rdi
0x18000362f  jnz     short loc_18000364C
0x180003631  xor     edx, edx
0x180003633  mov     rcx, rsi
0x180003636  call    OpenEccAltSigKey
0x18000363b  mov     ebx, eax
0x18000363d  test    eax, eax
0x18000363f  jns     short loc_18000364C
0x180003641  mov     r9d, 2CBh
0x180003647  jmp     loc_1800033A9
0x18000364c  mov     r12, [rsi+88h]
0x180003653  mov     rbx, [rbp+60h+var_58]
0x180003657  mov     r8, [rbp+60h+var_60]
0x18000365b  mov     rcx, [rbp+60h+arg_38]
0x180003662  mov     r9d, r13d
0x180003665  mov     rax, [rsi+0A8h]
0x18000366c  mov     rdx, rbx
0x18000366f  mov     r10d, [rbp+60h+arg_30]
0x180003676  mov     [rsp+0B0h+var_78], r14d
0x18000367b  mov     [rsp+0B0h+var_80], rcx
0x180003680  mov     rcx, [rbp+60h+arg_28]
0x180003687  mov     rax, [rax+90h]
0x18000368e  mov     [rsp+0B0h+dwFlags], r10d
0x180003693  mov     [rsp+0B0h+pcbResult], rcx
0x180003698  mov     rcx, r12
0x18000369b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036a0  mov     ebx, eax
0x1800036a2  test    eax, eax
0x1800036a4  jns     short loc_1800036F2
0x1800036a6  mov     rdx, cs:WPP_GLOBAL_Control
0x1800036ad  lea     rax, WPP_GLOBAL_Control
0x1800036b4  cmp     rdx, rax
0x1800036b7  jz      short loc_1800036E7
0x1800036b9  test    byte ptr [rdx+1Ch], 1
0x1800036bd  jz      short loc_1800036E7
0x1800036bf  lea     rcx, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800036c6  mov     dword ptr [rsp+0B0h+var_80], 321h
0x1800036ce  mov     qword ptr [rsp+0B0h+dwFlags], rcx
  ... truncated ...
```
