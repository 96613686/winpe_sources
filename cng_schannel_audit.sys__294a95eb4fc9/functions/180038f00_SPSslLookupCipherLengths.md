# SPSslLookupCipherLengths

- ea: `0x180038f00`
- end: `0x180039195`
- name: `SPSslLookupCipherLengths`
- size: `661`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, int, __int64, __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180038f00`
- `0x1800391a0`

## string_xrefs

- `0x180038f71`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180038fae`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180039091`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180039129`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180039148`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

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
0x180038f00  mov     [rsp+arg_0], rbx
0x180038f05  mov     [rsp+arg_8], rsi
0x180038f0a  push    rdi
0x180038f0b  sub     rsp, 40h
0x180038f0f  mov     ebx, r8d
0x180038f12  mov     esi, edx
0x180038f14  mov     rdi, rcx
0x180038f17  call    GetExternalSchannelAlgorithmsDeferred
0x180038f1c  cmp     esi, 302h
0x180038f22  jb      loc_18003906A
0x180038f28  test    rdi, rdi
0x180038f2b  jz      short loc_180038F42
0x180038f2d  cmp     dword ptr [rdi], 390h
0x180038f33  jb      short loc_180038F42
0x180038f35  cmp     dword ptr [rdi+4], 73736C31h
0x180038f3c  jz      loc_1800390AA
0x180038f42  mov     ebx, 80090026h
0x180038f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f4e  lea     rax, WPP_GLOBAL_Control
0x180038f55  cmp     rcx, rax
0x180038f58  jz      loc_18003901B
0x180038f5e  mov     eax, [rcx+2Ch]
0x180038f61  test    al, 1
0x180038f63  jz      loc_18003901B
0x180038f69  mov     [rsp+48h+var_18], 1064h
0x180038f71  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180038f78  mov     [rsp+48h+var_20], rax
0x180038f7d  mov     [rsp+48h+var_28], 80090026h
0x180038f85  jmp     short loc_180038FC2
0x180038f87  mov     ebx, 80090027h
0x180038f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f93  lea     rax, WPP_GLOBAL_Control
0x180038f9a  cmp     rcx, rax
0x180038f9d  jz      short loc_18003901B
0x180038f9f  mov     eax, [rcx+2Ch]
0x180038fa2  test    al, 1
0x180038fa4  jz      short loc_18003901B
0x180038fa6  mov     [rsp+48h+var_18], 107Ch
0x180038fae  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180038fb5  mov     [rsp+48h+var_20], rax
0x180038fba  mov     [rsp+48h+var_28], 80090027h
0x180038fc2  mov     rcx, [rcx+18h]
0x180038fc6  lea     r9, aStatus; "Status"
0x180038fcd  call    WPP_SF_sDsd
0x180038fd2  jmp     short loc_18003901B
0x180038fd4  test    [rdx], r9d
0x180038fd7  jz      loc_180039066
0x180038fdd  mov     [r8+4], r11
0x180038fe1  mov     [r8+0Ch], r11
0x180038fe5  mov     dword ptr [r8], 14h
0x180038fec  mov     eax, [rdx+28h]
0x180038fef  sub     eax, 5
0x180038ff2  cmp     eax, 1
0x180038ff5  ja      loc_18003916A
0x180038ffb  cmp     esi, 304h
0x180039001  mov     dword ptr [r8+8], 10h
0x180039009  mov     eax, r11d
0x18003900c  mov     ecx, 8
0x180039011  cmovnz  eax, ecx
0x180039014  mov     [r8+4], eax
0x180039018  mov     ebx, r11d
0x18003901b  mov     rsi, [rsp+48h+arg_8]
0x180039020  mov     eax, ebx
0x180039022  mov     rbx, [rsp+48h+arg_0]
0x180039027  add     rsp, 40h
0x18003902b  pop     rdi
0x18003902c  retn
0x18003902e  mov     r9d, [rdx+r10+0BA974h]
0x180039036  test    r9d, r9d
0x180039039  jz      loc_180038F87
0x18003903f  mov     eax, r11d
0x180039042  cmp     eax, cs:g_dwCipherSuiteInfoTotalCount
0x180039048  jnb     loc_180038F87
0x18003904e  mov     ecx, eax
0x180039050  mov     rdx, rva g_pCipherSuiteInfo[r10+rcx*8]
0x180039058  test    rdx, rdx
0x18003905b  jz      short loc_180039066
0x18003905d  cmp     [rdx+4], ebx
0x180039060  jz      loc_180038FD4
0x180039066  inc     eax
0x180039068  jmp     short loc_180039042
0x18003906a  mov     ebx, 80090029h
0x18003906f  mov     rcx, cs:WPP_GLOBAL_Control
0x180039076  lea     rax, WPP_GLOBAL_Control
0x18003907d  cmp     rcx, rax
0x180039080  jz      short loc_18003901B
0x180039082  mov     eax, [rcx+2Ch]
0x180039085  test    al, 1
0x180039087  jz      short loc_18003901B
0x180039089  mov     [rsp+48h+var_18], 1057h
0x180039091  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039098  mov     [rsp+48h+var_20], rax
0x18003909d  mov     [rsp+48h+var_28], 80090029h
0x1800390a5  jmp     loc_180038FC2
0x1800390aa  mov     r8, [rsp+48h+arg_20]
0x1800390af  test    r8, r8
0x1800390b2  jz      short loc_1800390FA
0x1800390b4  cmp     [rsp+48h+arg_28], 14h
0x1800390b9  jb      short loc_1800390FA
0x1800390bb  cmp     [rsp+48h+arg_30], 0
0x1800390c3  jnz     short loc_180039142
0x1800390c5  xor     r11d, r11d
0x1800390c8  lea     r10, cs:180000000h
0x1800390cf  mov     ecx, r11d
0x1800390d2  cmp     ecx, 7
0x1800390d5  jnb     loc_180038F87
0x1800390db  mov     eax, ecx
0x1800390dd  lea     rdx, ds:0[rax*8]
0x1800390e5  movzx   eax, word ptr [rdx+r10+0BA970h]
0x1800390ee  cmp     eax, esi
0x1800390f0  jz      loc_18003902E
0x1800390f6  inc     ecx
0x1800390f8  jmp     short loc_1800390D2
0x1800390fa  mov     ebx, 80090027h
0x1800390ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180039106  lea     rax, WPP_GLOBAL_Control
0x18003910d  cmp     rcx, rax
0x180039110  jz      loc_18003901B
0x180039116  mov     eax, [rcx+2Ch]
0x180039119  test    al, 1
0x18003911b  jz      loc_18003901B
0x180039121  mov     [rsp+48h+var_18], 106Ch
0x180039129  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039130  mov     [rsp+48h+var_20], rax
0x180039135  mov     [rsp+48h+var_28], 80090027h
0x18003913d  jmp     loc_180038FC2
0x180039142  mov     r9d, 1073h
0x180039148  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003914f  lea     rdx, aStatus; "Status"
0x180039156  mov     ecx, 80090009h
0x18003915b  mov     ebx, 80090009h
0x180039160  call    DebugTraceError
0x180039165  jmp     loc_18003901B
0x18003916a  mov     eax, [rdx+44h]
0x18003916d  mov     [r8+8], eax
0x180039171  mov     eax, [rdx+24h]
0x180039174  cmp     eax, 1
0x180039177  jbe     loc_180039018
0x18003917d  mov     [r8+4], eax
0x180039181  mov     eax, [rdx+24h]
0x180039184  mov     [r8+0Ch], eax
0x180039188  mov     dword ptr [r8+10h], 1
0x180039190  jmp     loc_180039018
```
