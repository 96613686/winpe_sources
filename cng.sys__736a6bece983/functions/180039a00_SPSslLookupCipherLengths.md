# SPSslLookupCipherLengths

- ea: `0x180039a00`
- end: `0x180039c95`
- name: `SPSslLookupCipherLengths`
- size: `661`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180039a00`
- `0x180039ca0`

## string_xrefs

- `0x180039a71`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180039aae`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180039b91`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180039c29`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180039c48`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

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
0x180039a00  mov     [rsp+arg_0], rbx
0x180039a05  mov     [rsp+arg_8], rsi
0x180039a0a  push    rdi
0x180039a0b  sub     rsp, 40h
0x180039a0f  mov     ebx, r8d
0x180039a12  mov     esi, edx
0x180039a14  mov     rdi, rcx
0x180039a17  call    GetExternalSchannelAlgorithmsDeferred
0x180039a1c  cmp     esi, 302h
0x180039a22  jb      loc_180039B6A
0x180039a28  test    rdi, rdi
0x180039a2b  jz      short loc_180039A42
0x180039a2d  cmp     dword ptr [rdi], 390h
0x180039a33  jb      short loc_180039A42
0x180039a35  cmp     dword ptr [rdi+4], 73736C31h
0x180039a3c  jz      loc_180039BAA
0x180039a42  mov     ebx, 80090026h
0x180039a47  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a4e  lea     rax, WPP_GLOBAL_Control
0x180039a55  cmp     rcx, rax
0x180039a58  jz      loc_180039B1B
0x180039a5e  mov     eax, [rcx+2Ch]
0x180039a61  test    al, 1
0x180039a63  jz      loc_180039B1B
0x180039a69  mov     [rsp+48h+var_18], 1064h
0x180039a71  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039a78  mov     [rsp+48h+var_20], rax
0x180039a7d  mov     [rsp+48h+var_28], 80090026h
0x180039a85  jmp     short loc_180039AC2
0x180039a87  mov     ebx, 80090027h
0x180039a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a93  lea     rax, WPP_GLOBAL_Control
0x180039a9a  cmp     rcx, rax
0x180039a9d  jz      short loc_180039B1B
0x180039a9f  mov     eax, [rcx+2Ch]
0x180039aa2  test    al, 1
0x180039aa4  jz      short loc_180039B1B
0x180039aa6  mov     [rsp+48h+var_18], 107Ch
0x180039aae  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039ab5  mov     [rsp+48h+var_20], rax
0x180039aba  mov     [rsp+48h+var_28], 80090027h
0x180039ac2  mov     rcx, [rcx+18h]
0x180039ac6  lea     r9, aStatus; "Status"
0x180039acd  call    WPP_SF_sDsd
0x180039ad2  jmp     short loc_180039B1B
0x180039ad4  test    [rdx], r9d
0x180039ad7  jz      loc_180039B66
0x180039add  mov     [r8+4], r11
0x180039ae1  mov     [r8+0Ch], r11
0x180039ae5  mov     dword ptr [r8], 14h
0x180039aec  mov     eax, [rdx+28h]
0x180039aef  sub     eax, 5
0x180039af2  cmp     eax, 1
0x180039af5  ja      loc_180039C6A
0x180039afb  cmp     esi, 304h
0x180039b01  mov     dword ptr [r8+8], 10h
0x180039b09  mov     eax, r11d
0x180039b0c  mov     ecx, 8
0x180039b11  cmovnz  eax, ecx
0x180039b14  mov     [r8+4], eax
0x180039b18  mov     ebx, r11d
0x180039b1b  mov     rsi, [rsp+48h+arg_8]
0x180039b20  mov     eax, ebx
0x180039b22  mov     rbx, [rsp+48h+arg_0]
0x180039b27  add     rsp, 40h
0x180039b2b  pop     rdi
0x180039b2c  retn
0x180039b2e  mov     r9d, [rdx+r10+0BCE64h]
0x180039b36  test    r9d, r9d
0x180039b39  jz      loc_180039A87
0x180039b3f  mov     eax, r11d
0x180039b42  cmp     eax, cs:g_dwCipherSuiteInfoTotalCount
0x180039b48  jnb     loc_180039A87
0x180039b4e  mov     ecx, eax
0x180039b50  mov     rdx, rva g_pCipherSuiteInfo[r10+rcx*8]
0x180039b58  test    rdx, rdx
0x180039b5b  jz      short loc_180039B66
0x180039b5d  cmp     [rdx+4], ebx
0x180039b60  jz      loc_180039AD4
0x180039b66  inc     eax
0x180039b68  jmp     short loc_180039B42
0x180039b6a  mov     ebx, 80090029h
0x180039b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b76  lea     rax, WPP_GLOBAL_Control
0x180039b7d  cmp     rcx, rax
0x180039b80  jz      short loc_180039B1B
0x180039b82  mov     eax, [rcx+2Ch]
0x180039b85  test    al, 1
0x180039b87  jz      short loc_180039B1B
0x180039b89  mov     [rsp+48h+var_18], 1057h
0x180039b91  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039b98  mov     [rsp+48h+var_20], rax
0x180039b9d  mov     [rsp+48h+var_28], 80090029h
0x180039ba5  jmp     loc_180039AC2
0x180039baa  mov     r8, [rsp+48h+arg_20]
0x180039baf  test    r8, r8
0x180039bb2  jz      short loc_180039BFA
0x180039bb4  cmp     [rsp+48h+arg_28], 14h
0x180039bb9  jb      short loc_180039BFA
0x180039bbb  cmp     [rsp+48h+arg_30], 0
0x180039bc3  jnz     short loc_180039C42
0x180039bc5  xor     r11d, r11d
0x180039bc8  lea     r10, cs:180000000h
0x180039bcf  mov     ecx, r11d
0x180039bd2  cmp     ecx, 7
0x180039bd5  jnb     loc_180039A87
0x180039bdb  mov     eax, ecx
0x180039bdd  lea     rdx, ds:0[rax*8]
0x180039be5  movzx   eax, word ptr [rdx+r10+0BCE60h]
0x180039bee  cmp     eax, esi
0x180039bf0  jz      loc_180039B2E
0x180039bf6  inc     ecx
0x180039bf8  jmp     short loc_180039BD2
0x180039bfa  mov     ebx, 80090027h
0x180039bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c06  lea     rax, WPP_GLOBAL_Control
0x180039c0d  cmp     rcx, rax
0x180039c10  jz      loc_180039B1B
0x180039c16  mov     eax, [rcx+2Ch]
0x180039c19  test    al, 1
0x180039c1b  jz      loc_180039B1B
0x180039c21  mov     [rsp+48h+var_18], 106Ch
0x180039c29  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039c30  mov     [rsp+48h+var_20], rax
0x180039c35  mov     [rsp+48h+var_28], 80090027h
0x180039c3d  jmp     loc_180039AC2
0x180039c42  mov     r9d, 1073h
0x180039c48  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180039c4f  lea     rdx, aStatus; "Status"
0x180039c56  mov     ecx, 80090009h
0x180039c5b  mov     ebx, 80090009h
0x180039c60  call    DebugTraceError
0x180039c65  jmp     loc_180039B1B
0x180039c6a  mov     eax, [rdx+44h]
0x180039c6d  mov     [r8+8], eax
0x180039c71  mov     eax, [rdx+24h]
0x180039c74  cmp     eax, 1
0x180039c77  jbe     loc_180039B18
0x180039c7d  mov     [r8+4], eax
0x180039c81  mov     eax, [rdx+24h]
0x180039c84  mov     [r8+0Ch], eax
0x180039c88  mov     dword ptr [r8+10h], 1
0x180039c90  jmp     loc_180039B18
```
