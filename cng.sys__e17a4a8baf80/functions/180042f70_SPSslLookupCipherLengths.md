# SPSslLookupCipherLengths

- ea: `0x180042f70`
- end: `0x180043205`
- name: `SPSslLookupCipherLengths`
- size: `661`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x180042f70`
- `0x180043210`

## string_xrefs

- `0x180042fe1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18004301e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180043101`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180043199`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800431b8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslLookupCipherLengths(
        _DWORD *a1,
        unsigned int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  _DWORD *v10; // rdx
  int v11; // r8d
  unsigned int v12; // ebx
  int v13; // eax
  int v15; // r9d
  unsigned int j; // eax
  unsigned int i; // ecx
  unsigned int v18; // eax

  GetExternalSchannelAlgorithmsDeferred();
  if ( a2 < 0x302 )
  {
    v12 = -2146893783;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)v10,
        v11,
        (unsigned int)"Status",
        41,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        87);
  }
  else if ( a1 && *a1 >= 0x390u && a1[1] == 1936944177 )
  {
    if ( a5 && a6 >= 0x14 )
    {
      if ( a7 )
      {
        v12 = -2146893815;
        DebugTraceError(2148073481LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 4211);
      }
      else
      {
        for ( i = 0; i < 7; ++i )
        {
          v10 = (_DWORD *)(8LL * i);
          if ( *(unsigned __int16 *)((char *)ProtocolVersionList + (_QWORD)v10) == a2 )
          {
            v15 = *(_DWORD *)((char *)ProtocolVersionList + (_QWORD)v10 + 4);
            if ( v15 )
            {
              for ( j = 0; j < g_dwCipherSuiteInfoTotalCount; ++j )
              {
                v10 = (_DWORD *)g_pCipherSuiteInfo[j];
                if ( v10 && v10[1] == a3 && (v15 & *v10) != 0 )
                {
                  *(_QWORD *)(a5 + 4) = 0;
                  *(_QWORD *)(a5 + 12) = 0;
                  *(_DWORD *)a5 = 20;
                  if ( (unsigned int)(v10[10] - 5) > 1 )
                  {
                    *(_DWORD *)(a5 + 8) = v10[17];
                    v18 = v10[9];
                    if ( v18 > 1 )
                    {
                      *(_DWORD *)(a5 + 4) = v18;
                      *(_DWORD *)(a5 + 12) = v10[9];
                      *(_DWORD *)(a5 + 16) = 1;
                    }
                  }
                  else
                  {
                    *(_DWORD *)(a5 + 8) = 16;
                    v13 = 0;
                    if ( a2 != 772 )
                      v13 = 8;
                    *(_DWORD *)(a5 + 4) = v13;
                  }
                  return 0;
                }
              }
            }
            break;
          }
        }
        v12 = -2146893785;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            (_DWORD)v10,
            a5,
            (unsigned int)"Status",
            39,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            124);
      }
    }
    else
    {
      v12 = -2146893785;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          (_DWORD)v10,
          a5,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          108);
    }
  }
  else
  {
    v12 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)v10,
        v11,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        100);
  }
  return v12;
}

```

## disassembly

```asm
0x180042f70  mov     [rsp+arg_0], rbx
0x180042f75  mov     [rsp+arg_8], rsi
0x180042f7a  push    rdi
0x180042f7b  sub     rsp, 40h
0x180042f7f  mov     ebx, r8d
0x180042f82  mov     esi, edx
0x180042f84  mov     rdi, rcx
0x180042f87  call    GetExternalSchannelAlgorithmsDeferred
0x180042f8c  cmp     esi, 302h
0x180042f92  jb      loc_1800430DA
0x180042f98  test    rdi, rdi
0x180042f9b  jz      short loc_180042FB2
0x180042f9d  cmp     dword ptr [rdi], 390h
0x180042fa3  jb      short loc_180042FB2
0x180042fa5  cmp     dword ptr [rdi+4], 73736C31h
0x180042fac  jz      loc_18004311A
0x180042fb2  mov     ebx, 80090026h
0x180042fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180042fbe  lea     rax, WPP_GLOBAL_Control
0x180042fc5  cmp     rcx, rax
0x180042fc8  jz      loc_18004308B
0x180042fce  mov     eax, [rcx+2Ch]
0x180042fd1  test    al, 1
0x180042fd3  jz      loc_18004308B
0x180042fd9  mov     [rsp+48h+var_18], 1064h
0x180042fe1  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180042fe8  mov     [rsp+48h+var_20], rax
0x180042fed  mov     [rsp+48h+var_28], 80090026h
0x180042ff5  jmp     short loc_180043032
0x180042ff7  mov     ebx, 80090027h
0x180042ffc  mov     rcx, cs:WPP_GLOBAL_Control
0x180043003  lea     rax, WPP_GLOBAL_Control
0x18004300a  cmp     rcx, rax
0x18004300d  jz      short loc_18004308B
0x18004300f  mov     eax, [rcx+2Ch]
0x180043012  test    al, 1
0x180043014  jz      short loc_18004308B
0x180043016  mov     [rsp+48h+var_18], 107Ch
0x18004301e  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180043025  mov     [rsp+48h+var_20], rax
0x18004302a  mov     [rsp+48h+var_28], 80090027h
0x180043032  mov     rcx, [rcx+18h]
0x180043036  lea     r9, aStatus; "Status"
0x18004303d  call    WPP_SF_sDsd
0x180043042  jmp     short loc_18004308B
0x180043044  test    [rdx], r9d
0x180043047  jz      loc_1800430D6
0x18004304d  mov     [r8+4], r11
0x180043051  mov     [r8+0Ch], r11
0x180043055  mov     dword ptr [r8], 14h
0x18004305c  mov     eax, [rdx+28h]
0x18004305f  sub     eax, 5
0x180043062  cmp     eax, 1
0x180043065  ja      loc_1800431DA
0x18004306b  cmp     esi, 304h
0x180043071  mov     dword ptr [r8+8], 10h
0x180043079  mov     eax, r11d
0x18004307c  mov     ecx, 8
0x180043081  cmovnz  eax, ecx
0x180043084  mov     [r8+4], eax
0x180043088  mov     ebx, r11d
0x18004308b  mov     rsi, [rsp+48h+arg_8]
0x180043090  mov     eax, ebx
0x180043092  mov     rbx, [rsp+48h+arg_0]
0x180043097  add     rsp, 40h
0x18004309b  pop     rdi
0x18004309c  retn
0x18004309e  mov     r9d, [rdx+r10+0C3574h]
0x1800430a6  test    r9d, r9d
0x1800430a9  jz      loc_180042FF7
0x1800430af  mov     eax, r11d
0x1800430b2  cmp     eax, cs:g_dwCipherSuiteInfoTotalCount
0x1800430b8  jnb     loc_180042FF7
0x1800430be  mov     ecx, eax
0x1800430c0  mov     rdx, rva g_pCipherSuiteInfo[r10+rcx*8]
0x1800430c8  test    rdx, rdx
0x1800430cb  jz      short loc_1800430D6
0x1800430cd  cmp     [rdx+4], ebx
0x1800430d0  jz      loc_180043044
0x1800430d6  inc     eax
0x1800430d8  jmp     short loc_1800430B2
0x1800430da  mov     ebx, 80090029h
0x1800430df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800430e6  lea     rax, WPP_GLOBAL_Control
0x1800430ed  cmp     rcx, rax
0x1800430f0  jz      short loc_18004308B
0x1800430f2  mov     eax, [rcx+2Ch]
0x1800430f5  test    al, 1
0x1800430f7  jz      short loc_18004308B
0x1800430f9  mov     [rsp+48h+var_18], 1057h
0x180043101  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180043108  mov     [rsp+48h+var_20], rax
0x18004310d  mov     [rsp+48h+var_28], 80090029h
0x180043115  jmp     loc_180043032
0x18004311a  mov     r8, [rsp+48h+arg_20]
0x18004311f  test    r8, r8
0x180043122  jz      short loc_18004316A
0x180043124  cmp     [rsp+48h+arg_28], 14h
0x180043129  jb      short loc_18004316A
0x18004312b  cmp     [rsp+48h+arg_30], 0
0x180043133  jnz     short loc_1800431B2
0x180043135  xor     r11d, r11d
0x180043138  lea     r10, cs:180000000h
0x18004313f  mov     ecx, r11d
0x180043142  cmp     ecx, 7
0x180043145  jnb     loc_180042FF7
0x18004314b  mov     eax, ecx
0x18004314d  lea     rdx, ds:0[rax*8]
0x180043155  movzx   eax, word ptr [rdx+r10+0C3570h]
0x18004315e  cmp     eax, esi
0x180043160  jz      loc_18004309E
0x180043166  inc     ecx
0x180043168  jmp     short loc_180043142
0x18004316a  mov     ebx, 80090027h
0x18004316f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043176  lea     rax, WPP_GLOBAL_Control
0x18004317d  cmp     rcx, rax
0x180043180  jz      loc_18004308B
0x180043186  mov     eax, [rcx+2Ch]
0x180043189  test    al, 1
0x18004318b  jz      loc_18004308B
0x180043191  mov     [rsp+48h+var_18], 106Ch
0x180043199  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800431a0  mov     [rsp+48h+var_20], rax
0x1800431a5  mov     [rsp+48h+var_28], 80090027h
0x1800431ad  jmp     loc_180043032
0x1800431b2  mov     r9d, 1073h
0x1800431b8  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800431bf  lea     rdx, aStatus; "Status"
0x1800431c6  mov     ecx, 80090009h
0x1800431cb  mov     ebx, 80090009h
0x1800431d0  call    DebugTraceError
0x1800431d5  jmp     loc_18004308B
0x1800431da  mov     eax, [rdx+44h]
0x1800431dd  mov     [r8+8], eax
0x1800431e1  mov     eax, [rdx+24h]
0x1800431e4  cmp     eax, 1
0x1800431e7  jbe     loc_180043088
0x1800431ed  mov     [r8+4], eax
0x1800431f1  mov     eax, [rdx+24h]
0x1800431f4  mov     [r8+0Ch], eax
0x1800431f8  mov     dword ptr [r8+10h], 1
0x180043200  jmp     loc_180043088
```
