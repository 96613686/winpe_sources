# SPSslLookupCipherSuiteInfo

- ea: `0x1800065b0`
- end: `0x1800069fd`
- name: `SPSslLookupCipherSuiteInfo`
- size: `1101`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800065b0`
- `0x18000743c`
- `0x1800082b0`
- `0x180082418`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18000696a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000696a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000697f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000697f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a0c33`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a0c33`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a0c3f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a0c3f`

## string_xrefs

- `0x1800065ff`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800068d1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180006912`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslLookupCipherSuiteInfo(_DWORD *a1, __int64 a2, int a3, __int64 a4, _DWORD *a5, int a6)
{
  int v7; // esi
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 i; // rcx
  int v14; // r8d
  __int64 j; // rax
  _WORD *v16; // r10
  __int64 v17; // rdi
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rax
  _WORD *v21; // rcx
  _WORD *v22; // rcx
  _WORD *v23; // rcx
  _WORD *v24; // r10
  __int64 v25; // rax
  __int64 v26; // r9
  _WORD *v27; // rcx
  _WORD *v28; // r10
  __int64 v29; // r9
  __int64 v30; // rax
  _WORD *v31; // rcx
  _WORD *v32; // rcx
  _WORD *v33; // r10
  __int64 v34; // r9
  __int64 v35; // rax
  _WORD *v36; // rcx
  _WORD *v37; // rcx
  _WORD *v38; // rax
  _WORD *v39; // rdx
  _WORD *v40; // rcx
  _QWORD *v41; // rcx
  char v42; // [rsp+30h] [rbp-18h]

  v7 = a2;
  if ( !dword_1800CE0E4 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( !dword_1800CE0E4 )
    {
      GetExternalSchannelAlgorithms();
      dword_1800CE0E4 = 1;
    }
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
  if ( !a1 || *a1 < 0x390u || a1[1] != 1936944177 )
  {
    v9 = -2146893786;
    v10 = 4067;
    v11 = 2148073510LL;
LABEL_6:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v10);
    return v9;
  }
  if ( !a5 )
  {
    v9 = -2146893785;
    v10 = 4074;
    v11 = 2148073511LL;
    goto LABEL_6;
  }
  if ( a6 )
  {
    v9 = -2146893815;
    v10 = 4081;
    v11 = 2148073481LL;
    goto LABEL_6;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 7 )
      goto LABEL_61;
    a2 = 8 * i;
    if ( LOWORD(ProtocolVersionList[i]) == v7 )
      break;
  }
  v14 = *(_DWORD *)((char *)ProtocolVersionList + a2 + 4);
  if ( v14 )
  {
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      if ( (unsigned int)j >= g_dwCipherSuiteInfoTotalCount )
        goto LABEL_61;
      a2 = g_pCipherSuiteInfo[j];
      if ( a2 )
      {
        if ( *(_DWORD *)(a2 + 4) == a3 && (v14 & *(_DWORD *)a2) != 0 )
          break;
      }
    }
    *a5 = v7;
    v16 = a5 + 3;
    v17 = 2147483646;
    a5[1] = *(_DWORD *)(a2 + 4);
    v18 = 64;
    v19 = 64;
    a5[2] = *(_DWORD *)(a2 + 4);
    v20 = 2147483646;
    v21 = *(_WORD **)(a2 + 8);
    do
    {
      if ( !v20 )
        break;
      if ( !*v21 )
        break;
      *v16++ = *v21++;
      --v20;
      --v19;
    }
    while ( v19 );
    v22 = v16 - 1;
    v9 = -2147024774;
    if ( v19 )
    {
      v22 = v16;
      v9 = 0;
    }
    *v22 = 0;
    if ( v19 )
    {
      v23 = *(_WORD **)(a2 + 16);
      v24 = a5 + 35;
      v25 = 2147483646;
      v26 = 64;
      do
      {
        if ( !v25 )
          break;
        if ( !*v23 )
          break;
        *v24++ = *v23++;
        --v25;
        --v26;
      }
      while ( v26 );
      v27 = v24 - 1;
      v9 = -2147024774;
      if ( v26 )
      {
        v27 = v24;
        v9 = 0;
      }
      *v27 = 0;
      if ( v26 )
      {
        v28 = a5 + 69;
        a5[67] = *(_DWORD *)(a2 + 28);
        v29 = 64;
        a5[68] = *(_DWORD *)(a2 + 36);
        v30 = 2147483646;
        v31 = *(_WORD **)(a2 + 56);
        do
        {
          if ( !v30 )
            break;
          if ( !*v31 )
            break;
          *v28++ = *v31++;
          --v30;
          --v29;
        }
        while ( v29 );
        v32 = v28 - 1;
        v9 = -2147024774;
        if ( v29 )
        {
          v32 = v28;
          v9 = 0;
        }
        *v32 = 0;
        if ( v29 )
        {
          v33 = a5 + 102;
          v34 = 64;
          a5[101] = 8 * *(_DWORD *)(a2 + 68);
          v35 = 2147483646;
          v36 = *(_WORD **)(a2 + 80);
          do
          {
            if ( !v35 )
              break;
            if ( !*v36 )
              break;
            *v33++ = *v36++;
            --v35;
            --v34;
          }
          while ( v34 );
          v37 = v33 - 1;
          v9 = -2147024774;
          if ( v34 )
          {
            v37 = v33;
            v9 = 0;
          }
          *v37 = 0;
          if ( v34 )
          {
            a5[134] = *(_DWORD *)(a2 + 92);
            a5[135] = *(_DWORD *)(a2 + 96);
            v38 = *(_WORD **)(a2 + 120);
            v39 = a5 + 136;
            do
            {
              if ( !v17 )
                break;
              if ( !*v38 )
                break;
              *v39++ = *v38++;
              --v17;
              --v18;
            }
            while ( v18 );
            v40 = v39 - 1;
            v9 = -2147024774;
            if ( v18 )
            {
              v40 = v39;
              v9 = 0;
            }
            *v40 = 0;
            if ( v18 )
              return 0;
            v10 = 4149;
            v11 = v9;
          }
          else
          {
            v10 = 4137;
            v11 = v9;
          }
        }
        else
        {
          v10 = 4126;
          v11 = v9;
        }
        goto LABEL_6;
      }
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      {
        v42 = 18;
        goto LABEL_60;
      }
    }
    else
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      {
        v42 = 9;
LABEL_60:
        WPP_SF_sDsd(
          v41[3],
          a2,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          (unsigned int)"Status",
          v9,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          v42);
      }
    }
  }
  else
  {
LABEL_61:
    v9 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        251);
  }
  return v9;
}

```

## disassembly

```asm
0x1800065b0  mov     [rsp+arg_8], rbx
0x1800065b5  mov     [rsp+arg_10], rsi
0x1800065ba  push    rdi
0x1800065bb  sub     rsp, 40h
0x1800065bf  cmp     cs:dword_1800CE0E4, 0
0x1800065c6  mov     ebx, r8d
0x1800065c9  mov     esi, edx
0x1800065cb  mov     rdi, rcx
0x1800065ce  jz      loc_18000696A
0x1800065d4  mov     [rsp+48h+arg_0], r14
0x1800065d9  test    rdi, rdi
0x1800065dc  jz      short loc_1800065EF
0x1800065de  cmp     dword ptr [rdi], 390h
0x1800065e4  jb      short loc_1800065EF
0x1800065e6  cmp     dword ptr [rdi+4], 73736C31h
0x1800065ed  jz      short loc_18000662A
0x1800065ef  mov     ebx, 80090026h
0x1800065f4  mov     r9d, 0FE3h
0x1800065fa  mov     ecx, 80090026h
0x1800065ff  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006606  lea     rdx, aStatus; "Status"
0x18000660d  call    DebugTraceError
0x180006612  mov     r14, [rsp+48h+arg_0]
0x180006617  mov     eax, ebx
0x180006619  mov     rbx, [rsp+48h+arg_8]
0x18000661e  mov     rsi, [rsp+48h+arg_10]
0x180006623  add     rsp, 40h
0x180006627  pop     rdi
0x180006628  retn
0x18000662a  mov     r14, [rsp+48h+arg_20]
0x18000662f  test    r14, r14
0x180006632  jz      loc_1800069AC
0x180006638  cmp     [rsp+48h+arg_28], 0
0x18000663d  jnz     loc_1800069C1
0x180006643  xor     ecx, ecx
0x180006645  lea     r9, cs:180000000h
0x18000664c  nop     dword ptr [rax+00h]
0x180006650  cmp     ecx, 7
0x180006653  jnb     loc_1800068E3
0x180006659  lea     rdx, ds:0[rcx*8]
0x180006661  movzx   eax, word ptr [rdx+r9+0BCE60h]
0x18000666a  cmp     eax, esi
0x18000666c  jz      short loc_180006672
0x18000666e  inc     ecx
0x180006670  jmp     short loc_180006650
0x180006672  mov     r8d, [rdx+r9+0BCE64h]
0x18000667a  test    r8d, r8d
0x18000667d  jz      loc_1800068E3
0x180006683  xor     eax, eax
0x180006685  nop     word ptr [rax+rax+00000000h]
0x180006690  cmp     eax, cs:g_dwCipherSuiteInfoTotalCount
0x180006696  jnb     loc_1800068E3
0x18000669c  mov     rdx, rva g_pCipherSuiteInfo[r9+rax*8]
0x1800066a4  test    rdx, rdx
0x1800066a7  jz      short loc_1800066AE
0x1800066a9  cmp     [rdx+4], ebx
0x1800066ac  jz      short loc_1800066B2
0x1800066ae  inc     eax
0x1800066b0  jmp     short loc_180006690
0x1800066b2  test    [rdx], r8d
0x1800066b5  jz      short loc_1800066AE
0x1800066b7  mov     [r14], esi
0x1800066ba  lea     r10, [r14+0Ch]
0x1800066be  mov     eax, [rdx+4]
0x1800066c1  mov     edi, 7FFFFFFEh
0x1800066c6  mov     [r14+4], eax
0x1800066ca  mov     r8d, 40h ; '@'
0x1800066d0  mov     eax, [rdx+4]
0x1800066d3  mov     r9d, r8d
0x1800066d6  mov     [r14+8], eax
0x1800066da  mov     eax, edi
0x1800066dc  mov     rcx, [rdx+8]
0x1800066e0  test    rax, rax
0x1800066e3  jz      short loc_180006704
0x1800066e5  movzx   r11d, word ptr [rcx]
0x1800066e9  test    r11w, r11w
0x1800066ed  jz      short loc_180006704
0x1800066ef  mov     [r10], r11w
0x1800066f3  add     rcx, 2
0x1800066f7  add     r10, 2
0x1800066fb  dec     rax
0x1800066fe  sub     r9, 1
0x180006702  jnz     short loc_1800066E0
0x180006704  xor     eax, eax
0x180006706  lea     rcx, [r10-2]
0x18000670a  test    r9, r9
0x18000670d  mov     ebx, 8007007Ah
0x180006712  cmovnz  rcx, r10
0x180006716  cmovnz  ebx, eax
0x180006719  mov     [rcx], ax
0x18000671c  jz      loc_1800068A7
0x180006722  mov     rcx, [rdx+10h]
0x180006726  lea     r10, [r14+8Ch]
0x18000672d  mov     rax, rdi
0x180006730  mov     r9, r8
0x180006733  test    rax, rax
0x180006736  jz      short loc_180006757
0x180006738  movzx   r11d, word ptr [rcx]
0x18000673c  test    r11w, r11w
0x180006740  jz      short loc_180006757
0x180006742  mov     [r10], r11w
0x180006746  add     rcx, 2
0x18000674a  add     r10, 2
0x18000674e  dec     rax
0x180006751  sub     r9, 1
0x180006755  jnz     short loc_180006733
0x180006757  xor     eax, eax
0x180006759  lea     rcx, [r10-2]
0x18000675d  test    r9, r9
0x180006760  mov     ebx, 8007007Ah
0x180006765  cmovnz  rcx, r10
0x180006769  cmovnz  ebx, eax
0x18000676c  mov     [rcx], ax
0x18000676f  jz      loc_18000693B
0x180006775  mov     eax, [rdx+1Ch]
0x180006778  lea     r10, [r14+114h]
0x18000677f  mov     [r14+10Ch], eax
0x180006786  mov     r9, r8
0x180006789  mov     eax, [rdx+24h]
0x18000678c  mov     [r14+110h], eax
0x180006793  mov     rax, rdi
0x180006796  mov     rcx, [rdx+38h]
0x18000679a  nop     word ptr [rax+rax+00h]
0x1800067a0  test    rax, rax
0x1800067a3  jz      short loc_1800067C4
0x1800067a5  movzx   r11d, word ptr [rcx]
0x1800067a9  test    r11w, r11w
0x1800067ad  jz      short loc_1800067C4
0x1800067af  mov     [r10], r11w
0x1800067b3  add     rcx, 2
0x1800067b7  add     r10, 2
0x1800067bb  dec     rax
0x1800067be  sub     r9, 1
0x1800067c2  jnz     short loc_1800067A0
0x1800067c4  xor     eax, eax
0x1800067c6  lea     rcx, [r10-2]
0x1800067ca  test    r9, r9
0x1800067cd  mov     ebx, 8007007Ah
0x1800067d2  cmovnz  rcx, r10
0x1800067d6  cmovnz  ebx, eax
0x1800067d9  mov     [rcx], ax
0x1800067dc  jz      loc_1800069D6
0x1800067e2  mov     eax, [rdx+44h]
0x1800067e5  lea     r10, [r14+198h]
0x1800067ec  shl     eax, 3
0x1800067ef  mov     r9, r8
0x1800067f2  mov     [r14+194h], eax
0x1800067f9  mov     rax, rdi
0x1800067fc  mov     rcx, [rdx+50h]
0x180006800  test    rax, rax
0x180006803  jz      short loc_180006824
0x180006805  movzx   r11d, word ptr [rcx]
0x180006809  test    r11w, r11w
0x18000680d  jz      short loc_180006824
0x18000680f  mov     [r10], r11w
0x180006813  add     rcx, 2
0x180006817  add     r10, 2
0x18000681b  dec     rax
0x18000681e  sub     r9, 1
0x180006822  jnz     short loc_180006800
0x180006824  xor     eax, eax
0x180006826  lea     rcx, [r10-2]
0x18000682a  test    r9, r9
0x18000682d  mov     ebx, 8007007Ah
0x180006832  cmovnz  rcx, r10
0x180006836  cmovnz  ebx, eax
0x180006839  mov     [rcx], ax
0x18000683c  jz      loc_1800069E3
0x180006842  mov     eax, [rdx+5Ch]
0x180006845  mov     [r14+218h], eax
0x18000684c  mov     eax, [rdx+60h]
0x18000684f  mov     [r14+21Ch], eax
0x180006856  mov     rax, [rdx+78h]
0x18000685a  lea     rdx, [r14+220h]
0x180006861  test    rdi, rdi
0x180006864  jz      short loc_180006882
0x180006866  movzx   ecx, word ptr [rax]
0x180006869  test    cx, cx
0x18000686c  jz      short loc_180006882
0x18000686e  mov     [rdx], cx
0x180006871  add     rax, 2
0x180006875  add     rdx, 2
0x180006879  dec     rdi
0x18000687c  sub     r8, 1
0x180006880  jnz     short loc_180006861
0x180006882  xor     eax, eax
0x180006884  lea     rcx, [rdx-2]
0x180006888  test    r8, r8
0x18000688b  mov     ebx, 8007007Ah
0x180006890  cmovnz  rcx, rdx
0x180006894  cmovnz  ebx, eax
0x180006897  mov     [rcx], ax
0x18000689a  jz      loc_1800069F0
0x1800068a0  xor     ebx, ebx
0x1800068a2  jmp     loc_180006612
0x1800068a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068ae  lea     rax, WPP_GLOBAL_Control
0x1800068b5  cmp     rcx, rax
0x1800068b8  jz      loc_180006612
0x1800068be  mov     eax, [rcx+2Ch]
0x1800068c1  test    al, 1
0x1800068c3  jz      loc_180006612
0x1800068c9  mov     dword ptr [rsp+48h+var_18], 1009h
0x1800068d1  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800068d8  mov     [rsp+48h+var_20], r8
0x1800068dd  mov     [rsp+48h+var_28], ebx
0x1800068e1  jmp     short loc_180006926
0x1800068e3  mov     ebx, 80090027h
0x1800068e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068ef  lea     rax, WPP_GLOBAL_Control
0x1800068f6  cmp     rcx, rax
0x1800068f9  jz      loc_180006612
0x1800068ff  mov     eax, [rcx+2Ch]
0x180006902  test    al, 1
0x180006904  jz      loc_180006612
0x18000690a  mov     dword ptr [rsp+48h+var_18], 0FFBh
0x180006912  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006919  mov     [rsp+48h+var_20], r8
0x18000691e  mov     [rsp+48h+var_28], 80090027h
0x180006926  mov     rcx, [rcx+18h]
0x18000692a  lea     r9, aStatus; "Status"
0x180006931  call    WPP_SF_sDsd
0x180006936  jmp     loc_180006612
0x18000693b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006942  lea     rax, WPP_GLOBAL_Control
0x180006949  cmp     rcx, rax
0x18000694c  jz      loc_180006612
0x180006952  mov     eax, [rcx+2Ch]
0x180006955  test    al, 1
0x180006957  jz      loc_180006612
0x18000695d  mov     dword ptr [rsp+48h+var_18], 1012h
0x180006965  jmp     loc_1800068D1
0x18000696a  call    cs:__imp_KeEnterCriticalRegion
0x180006971  nop     dword ptr [rax+rax+00h]
0x180006976  mov     dl, 1; Wait
0x180006978  lea     rcx, Resource; Resource
0x18000697f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180006986  nop     dword ptr [rax+rax+00h]
0x18000698b  cmp     cs:dword_1800CE0E4, 0
0x180006992  jnz     loc_1800A0C2C
0x180006998  call    GetExternalSchannelAlgorithms
0x18000699d  mov     cs:dword_1800CE0E4, 1
0x1800069a7  jmp     loc_1800A0C2C
0x1800069ac  mov     ebx, 80090027h
0x1800069b1  mov     r9d, 0FEAh
0x1800069b7  mov     ecx, 80090027h
0x1800069bc  jmp     loc_1800065FF
0x1800069c1  mov     ebx, 80090009h
0x1800069c6  mov     r9d, 0FF1h
0x1800069cc  mov     ecx, 80090009h
0x1800069d1  jmp     loc_1800065FF
0x1800069d6  mov     r9d, 101Eh
0x1800069dc  mov     ecx, ebx
0x1800069de  jmp     loc_1800065FF
0x1800069e3  mov     r9d, 1029h
0x1800069e9  mov     ecx, ebx
0x1800069eb  jmp     loc_1800065FF
0x1800069f0  mov     r9d, 1035h
0x1800069f6  mov     ecx, ebx
0x1800069f8  jmp     loc_1800065FF
0x1800a0c2c  lea     rcx, Resource; Resource
0x1800a0c33  call    cs:__imp_ExReleaseResourceLite
0x1800a0c3a  nop     dword ptr [rax+rax+00h]
0x1800a0c3f  call    cs:__imp_KeLeaveCriticalRegion
0x1800a0c46  nop     dword ptr [rax+rax+00h]
0x1800a0c4b  nop
0x1800a0c4c  jmp     loc_1800065D4
```
