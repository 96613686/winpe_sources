# SPSslLookupCipherSuiteInfo

- ea: `0x1800106d0`
- end: `0x180010b1d`
- name: `SPSslLookupCipherSuiteInfo`
- size: `1101`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800106d0`
- `0x18001155c`
- `0x1800123d0`
- `0x18008b618`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180010a8a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180010a8a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010a9f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010a9f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a5ba1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a5ba1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5bad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5bad`

## string_xrefs

- `0x18001071f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800109f1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180010a32`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

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
  if ( !dword_1800D40E4 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( !dword_1800D40E4 )
    {
      GetExternalSchannelAlgorithms();
      dword_1800D40E4 = 1;
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
0x1800106d0  mov     [rsp+arg_8], rbx
0x1800106d5  mov     [rsp+arg_10], rsi
0x1800106da  push    rdi
0x1800106db  sub     rsp, 40h
0x1800106df  cmp     cs:dword_1800D40E4, 0
0x1800106e6  mov     ebx, r8d
0x1800106e9  mov     esi, edx
0x1800106eb  mov     rdi, rcx
0x1800106ee  jz      loc_180010A8A
0x1800106f4  mov     [rsp+48h+arg_0], r14
0x1800106f9  test    rdi, rdi
0x1800106fc  jz      short loc_18001070F
0x1800106fe  cmp     dword ptr [rdi], 390h
0x180010704  jb      short loc_18001070F
0x180010706  cmp     dword ptr [rdi+4], 73736C31h
0x18001070d  jz      short loc_18001074A
0x18001070f  mov     ebx, 80090026h
0x180010714  mov     r9d, 0FE3h
0x18001071a  mov     ecx, 80090026h
0x18001071f  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010726  lea     rdx, aStatus; "Status"
0x18001072d  call    DebugTraceError
0x180010732  mov     r14, [rsp+48h+arg_0]
0x180010737  mov     eax, ebx
0x180010739  mov     rbx, [rsp+48h+arg_8]
0x18001073e  mov     rsi, [rsp+48h+arg_10]
0x180010743  add     rsp, 40h
0x180010747  pop     rdi
0x180010748  retn
0x18001074a  mov     r14, [rsp+48h+arg_20]
0x18001074f  test    r14, r14
0x180010752  jz      loc_180010ACC
0x180010758  cmp     [rsp+48h+arg_28], 0
0x18001075d  jnz     loc_180010AE1
0x180010763  xor     ecx, ecx
0x180010765  lea     r9, cs:180000000h
0x18001076c  nop     dword ptr [rax+00h]
0x180010770  cmp     ecx, 7
0x180010773  jnb     loc_180010A03
0x180010779  lea     rdx, ds:0[rcx*8]
0x180010781  movzx   eax, word ptr [rdx+r9+0C3570h]
0x18001078a  cmp     eax, esi
0x18001078c  jz      short loc_180010792
0x18001078e  inc     ecx
0x180010790  jmp     short loc_180010770
0x180010792  mov     r8d, [rdx+r9+0C3574h]
0x18001079a  test    r8d, r8d
0x18001079d  jz      loc_180010A03
0x1800107a3  xor     eax, eax
0x1800107a5  nop     word ptr [rax+rax+00000000h]
0x1800107b0  cmp     eax, cs:g_dwCipherSuiteInfoTotalCount
0x1800107b6  jnb     loc_180010A03
0x1800107bc  mov     rdx, rva g_pCipherSuiteInfo[r9+rax*8]
0x1800107c4  test    rdx, rdx
0x1800107c7  jz      short loc_1800107CE
0x1800107c9  cmp     [rdx+4], ebx
0x1800107cc  jz      short loc_1800107D2
0x1800107ce  inc     eax
0x1800107d0  jmp     short loc_1800107B0
0x1800107d2  test    [rdx], r8d
0x1800107d5  jz      short loc_1800107CE
0x1800107d7  mov     [r14], esi
0x1800107da  lea     r10, [r14+0Ch]
0x1800107de  mov     eax, [rdx+4]
0x1800107e1  mov     edi, 7FFFFFFEh
0x1800107e6  mov     [r14+4], eax
0x1800107ea  mov     r8d, 40h ; '@'
0x1800107f0  mov     eax, [rdx+4]
0x1800107f3  mov     r9d, r8d
0x1800107f6  mov     [r14+8], eax
0x1800107fa  mov     eax, edi
0x1800107fc  mov     rcx, [rdx+8]
0x180010800  test    rax, rax
0x180010803  jz      short loc_180010824
0x180010805  movzx   r11d, word ptr [rcx]
0x180010809  test    r11w, r11w
0x18001080d  jz      short loc_180010824
0x18001080f  mov     [r10], r11w
0x180010813  add     rcx, 2
0x180010817  add     r10, 2
0x18001081b  dec     rax
0x18001081e  sub     r9, 1
0x180010822  jnz     short loc_180010800
0x180010824  xor     eax, eax
0x180010826  lea     rcx, [r10-2]
0x18001082a  test    r9, r9
0x18001082d  mov     ebx, 8007007Ah
0x180010832  cmovnz  rcx, r10
0x180010836  cmovnz  ebx, eax
0x180010839  mov     [rcx], ax
0x18001083c  jz      loc_1800109C7
0x180010842  mov     rcx, [rdx+10h]
0x180010846  lea     r10, [r14+8Ch]
0x18001084d  mov     rax, rdi
0x180010850  mov     r9, r8
0x180010853  test    rax, rax
0x180010856  jz      short loc_180010877
0x180010858  movzx   r11d, word ptr [rcx]
0x18001085c  test    r11w, r11w
0x180010860  jz      short loc_180010877
0x180010862  mov     [r10], r11w
0x180010866  add     rcx, 2
0x18001086a  add     r10, 2
0x18001086e  dec     rax
0x180010871  sub     r9, 1
0x180010875  jnz     short loc_180010853
0x180010877  xor     eax, eax
0x180010879  lea     rcx, [r10-2]
0x18001087d  test    r9, r9
0x180010880  mov     ebx, 8007007Ah
0x180010885  cmovnz  rcx, r10
0x180010889  cmovnz  ebx, eax
0x18001088c  mov     [rcx], ax
0x18001088f  jz      loc_180010A5B
0x180010895  mov     eax, [rdx+1Ch]
0x180010898  lea     r10, [r14+114h]
0x18001089f  mov     [r14+10Ch], eax
0x1800108a6  mov     r9, r8
0x1800108a9  mov     eax, [rdx+24h]
0x1800108ac  mov     [r14+110h], eax
0x1800108b3  mov     rax, rdi
0x1800108b6  mov     rcx, [rdx+38h]
0x1800108ba  nop     word ptr [rax+rax+00h]
0x1800108c0  test    rax, rax
0x1800108c3  jz      short loc_1800108E4
0x1800108c5  movzx   r11d, word ptr [rcx]
0x1800108c9  test    r11w, r11w
0x1800108cd  jz      short loc_1800108E4
0x1800108cf  mov     [r10], r11w
0x1800108d3  add     rcx, 2
0x1800108d7  add     r10, 2
0x1800108db  dec     rax
0x1800108de  sub     r9, 1
0x1800108e2  jnz     short loc_1800108C0
0x1800108e4  xor     eax, eax
0x1800108e6  lea     rcx, [r10-2]
0x1800108ea  test    r9, r9
0x1800108ed  mov     ebx, 8007007Ah
0x1800108f2  cmovnz  rcx, r10
0x1800108f6  cmovnz  ebx, eax
0x1800108f9  mov     [rcx], ax
0x1800108fc  jz      loc_180010AF6
0x180010902  mov     eax, [rdx+44h]
0x180010905  lea     r10, [r14+198h]
0x18001090c  shl     eax, 3
0x18001090f  mov     r9, r8
0x180010912  mov     [r14+194h], eax
0x180010919  mov     rax, rdi
0x18001091c  mov     rcx, [rdx+50h]
0x180010920  test    rax, rax
0x180010923  jz      short loc_180010944
0x180010925  movzx   r11d, word ptr [rcx]
0x180010929  test    r11w, r11w
0x18001092d  jz      short loc_180010944
0x18001092f  mov     [r10], r11w
0x180010933  add     rcx, 2
0x180010937  add     r10, 2
0x18001093b  dec     rax
0x18001093e  sub     r9, 1
0x180010942  jnz     short loc_180010920
0x180010944  xor     eax, eax
0x180010946  lea     rcx, [r10-2]
0x18001094a  test    r9, r9
0x18001094d  mov     ebx, 8007007Ah
0x180010952  cmovnz  rcx, r10
0x180010956  cmovnz  ebx, eax
0x180010959  mov     [rcx], ax
0x18001095c  jz      loc_180010B03
0x180010962  mov     eax, [rdx+5Ch]
0x180010965  mov     [r14+218h], eax
0x18001096c  mov     eax, [rdx+60h]
0x18001096f  mov     [r14+21Ch], eax
0x180010976  mov     rax, [rdx+78h]
0x18001097a  lea     rdx, [r14+220h]
0x180010981  test    rdi, rdi
0x180010984  jz      short loc_1800109A2
0x180010986  movzx   ecx, word ptr [rax]
0x180010989  test    cx, cx
0x18001098c  jz      short loc_1800109A2
0x18001098e  mov     [rdx], cx
0x180010991  add     rax, 2
0x180010995  add     rdx, 2
0x180010999  dec     rdi
0x18001099c  sub     r8, 1
0x1800109a0  jnz     short loc_180010981
0x1800109a2  xor     eax, eax
0x1800109a4  lea     rcx, [rdx-2]
0x1800109a8  test    r8, r8
0x1800109ab  mov     ebx, 8007007Ah
0x1800109b0  cmovnz  rcx, rdx
0x1800109b4  cmovnz  ebx, eax
0x1800109b7  mov     [rcx], ax
0x1800109ba  jz      loc_180010B10
0x1800109c0  xor     ebx, ebx
0x1800109c2  jmp     loc_180010732
0x1800109c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109ce  lea     rax, WPP_GLOBAL_Control
0x1800109d5  cmp     rcx, rax
0x1800109d8  jz      loc_180010732
0x1800109de  mov     eax, [rcx+2Ch]
0x1800109e1  test    al, 1
0x1800109e3  jz      loc_180010732
0x1800109e9  mov     dword ptr [rsp+48h+var_18], 1009h
0x1800109f1  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800109f8  mov     [rsp+48h+var_20], r8
0x1800109fd  mov     [rsp+48h+var_28], ebx
0x180010a01  jmp     short loc_180010A46
0x180010a03  mov     ebx, 80090027h
0x180010a08  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a0f  lea     rax, WPP_GLOBAL_Control
0x180010a16  cmp     rcx, rax
0x180010a19  jz      loc_180010732
0x180010a1f  mov     eax, [rcx+2Ch]
0x180010a22  test    al, 1
0x180010a24  jz      loc_180010732
0x180010a2a  mov     dword ptr [rsp+48h+var_18], 0FFBh
0x180010a32  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010a39  mov     [rsp+48h+var_20], r8
0x180010a3e  mov     [rsp+48h+var_28], 80090027h
0x180010a46  mov     rcx, [rcx+18h]
0x180010a4a  lea     r9, aStatus; "Status"
0x180010a51  call    WPP_SF_sDsd
0x180010a56  jmp     loc_180010732
0x180010a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a62  lea     rax, WPP_GLOBAL_Control
0x180010a69  cmp     rcx, rax
0x180010a6c  jz      loc_180010732
0x180010a72  mov     eax, [rcx+2Ch]
0x180010a75  test    al, 1
0x180010a77  jz      loc_180010732
0x180010a7d  mov     dword ptr [rsp+48h+var_18], 1012h
0x180010a85  jmp     loc_1800109F1
0x180010a8a  call    cs:__imp_KeEnterCriticalRegion
0x180010a91  nop     dword ptr [rax+rax+00h]
0x180010a96  mov     dl, 1; Wait
0x180010a98  lea     rcx, Resource; Resource
0x180010a9f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180010aa6  nop     dword ptr [rax+rax+00h]
0x180010aab  cmp     cs:dword_1800D40E4, 0
0x180010ab2  jnz     loc_1800A5B9A
0x180010ab8  call    GetExternalSchannelAlgorithms
0x180010abd  mov     cs:dword_1800D40E4, 1
0x180010ac7  jmp     loc_1800A5B9A
0x180010acc  mov     ebx, 80090027h
0x180010ad1  mov     r9d, 0FEAh
0x180010ad7  mov     ecx, 80090027h
0x180010adc  jmp     loc_18001071F
0x180010ae1  mov     ebx, 80090009h
0x180010ae6  mov     r9d, 0FF1h
0x180010aec  mov     ecx, 80090009h
0x180010af1  jmp     loc_18001071F
0x180010af6  mov     r9d, 101Eh
0x180010afc  mov     ecx, ebx
0x180010afe  jmp     loc_18001071F
0x180010b03  mov     r9d, 1029h
0x180010b09  mov     ecx, ebx
0x180010b0b  jmp     loc_18001071F
0x180010b10  mov     r9d, 1035h
0x180010b16  mov     ecx, ebx
0x180010b18  jmp     loc_18001071F
0x1800a5b9a  lea     rcx, Resource; Resource
0x1800a5ba1  call    cs:__imp_ExReleaseResourceLite
0x1800a5ba8  nop     dword ptr [rax+rax+00h]
0x1800a5bad  call    cs:__imp_KeLeaveCriticalRegion
0x1800a5bb4  nop     dword ptr [rax+rax+00h]
0x1800a5bb9  nop
0x1800a5bba  jmp     loc_1800106F4
```
