# SPSslGenerateMasterKey

- ea: `0x180006070`
- end: `0x1800066e7`
- name: `SPSslGenerateMasterKey`
- size: `1655`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180003ef0`
- `0x180006070`
- `0x1800066f0`
- `0x1800068e0`
- `0x180007940`
- `0x180007990`
- `0x18000b594`
- `0x18000b654`
- `0x180012d98`
- `0x18001355c`
- `0x180020a70`
- `0x180024ef0`

## string_xrefs

- `0x1800062de`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180006318`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180006373`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800063ca`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180006416`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000645d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000648e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800064b6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800064ed`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180006522`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180006599`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000660c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180006634`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000668a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslGenerateMasterKey(
        __int64 a1,
        _DWORD *a2,
        __int64 a3,
        __int64 *a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        __int64 a10,
        int a11)
{
  __int64 v11; // r12
  __int64 v14; // rdx
  int v15; // r8d
  __int64 v16; // r9
  __int64 i; // rcx
  int v18; // r9d
  __int64 v19; // rax
  _DWORD *v20; // rbx
  int v21; // esi
  int v22; // edx
  __int64 v23; // rdi
  int v24; // r8d
  __int64 v25; // rcx
  int v26; // r9d
  __int64 v27; // rax
  int v28; // edx
  __int64 v29; // r8
  int v30; // edx
  unsigned int SecretAgreementMasterKey; // ebx
  int v32; // r8d
  char *v34; // rsi
  __int64 v35; // rbp
  __int64 v36; // r9
  int MasterKey; // eax
  __int64 v38; // r9
  __int64 v39; // r9
  int v40; // eax
  __int64 v41; // [rsp+40h] [rbp-B8h]
  __int64 v42; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+50h] [rbp-A8h]
  __int64 v44; // [rsp+58h] [rbp-A0h]
  __int64 v45; // [rsp+60h] [rbp-98h]
  _DWORD v46[3]; // [rsp+68h] [rbp-90h] BYREF
  char v47; // [rsp+74h] [rbp-84h] BYREF
  __int16 v48; // [rsp+75h] [rbp-83h]
  char v49; // [rsp+77h] [rbp-81h]
  __int128 v50; // [rsp+78h] [rbp-80h]
  _BYTE v51[28]; // [rsp+88h] [rbp-70h] BYREF

  v11 = 0;
  v45 = a8;
  v44 = a10;
  memset(v51, 0, sizeof(v51));
  v48 = 0;
  v49 = 0;
  v43 = a3;
  v46[0] = 60;
  v46[1] = 1936944183;
  v46[2] = a5;
  v47 = 0;
  v50 = 0;
  v42 = 0;
  v41 = SslpValidateProvHandle(a1);
  if ( v41 )
  {
    if ( v16 )
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned int)i >= 7 )
          goto LABEL_28;
        v14 = 8 * i;
        if ( (unsigned __int16)ProtocolVersionList[4 * i] == a5 )
          break;
      }
      v18 = *(int *)((char *)&dword_180031A24 + v14);
      if ( v18 )
      {
        v15 = a6;
        v19 = 0;
        LODWORD(v14) = g_dwCipherSuiteInfoTotalCount;
        while ( 1 )
        {
          if ( (unsigned int)v19 >= g_dwCipherSuiteInfoTotalCount )
            goto LABEL_28;
          v20 = (_DWORD *)g_pCipherSuiteInfo[v19];
          if ( v20 )
          {
            if ( v20[1] == a6 && (v18 & *v20) != 0 )
              break;
          }
          v19 = (unsigned int)(v19 + 1);
        }
        if ( !a7 )
        {
          SecretAgreementMasterKey = -2146893785;
          DebugTraceError(
            2148073511LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            2829);
          return SecretAgreementMasterKey;
        }
        if ( (a11 & 0xFFFFFFFC) != 0 )
        {
          SecretAgreementMasterKey = -2146893815;
          DebugTraceError(
            2148073481LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            2836);
          return SecretAgreementMasterKey;
        }
        if ( (a11 & 1) != 0 )
        {
          v21 = 1;
        }
        else
        {
          if ( (a11 & 2) == 0 )
            return (unsigned int)-2146893815;
          v21 = 0;
        }
        v23 = SafeAllocaAllocateFromHeap(80);
        if ( !v23 )
        {
          SecretAgreementMasterKey = -2146893810;
          DebugTraceError(
            2148073486LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            2866);
LABEL_25:
          if ( v11 )
            MSCryptFree(v11);
          return SecretAgreementMasterKey;
        }
        *(_DWORD *)(v23 + 12) = 0;
        *(_QWORD *)(v23 + 28) = 0;
        *(_QWORD *)(v23 + 36) = 0;
        *(_QWORD *)(v23 + 44) = 0;
        *(_QWORD *)(v23 + 52) = 0;
        *(_QWORD *)(v23 + 60) = 0;
        *(_QWORD *)(v23 + 68) = 0;
        *(_DWORD *)(v23 + 76) = 0;
        *(_DWORD *)v23 = 80;
        *(_DWORD *)(v23 + 4) = 1936944181;
        *(_DWORD *)(v23 + 8) = a5;
        *(_QWORD *)(v23 + 16) = v20;
        *(_DWORD *)(v23 + 24) = v21;
        v25 = (unsigned int)v20[25];
        if ( (_DWORD)v25 != 1 )
        {
          v26 = v20[22];
          if ( v26 != 196610 && (unsigned int)(v26 - 196615) > 3 )
          {
            if ( (_DWORD)v25 == 4 )
            {
              v40 = TlsGeneratePSKPreMasterKey(4, a5, a7, &v42);
              SecretAgreementMasterKey = v40;
              if ( v40 < 0 )
              {
                DebugTraceError(
                  (unsigned int)v40,
                  "Status",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                  2996);
                v11 = v42;
                goto LABEL_34;
              }
              v11 = v42;
              MasterKey = TlsGenerateMasterKey(v41, v42, v23, a7);
              SecretAgreementMasterKey = MasterKey;
              if ( MasterKey < 0 )
              {
                v38 = 3007;
                goto LABEL_62;
              }
LABEL_24:
              *a4 = v23;
              goto LABEL_25;
            }
            v36 = 3014;
LABEL_58:
            SecretAgreementMasterKey = -2146893783;
            DebugTraceError(
              2148073513LL,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              v36);
LABEL_34:
            MSCryptFree(v23);
            goto LABEL_25;
          }
          if ( SslpValidateEphemeralHandle(a2) )
          {
            v27 = SslpValidateEphemeralHandle(v43);
            if ( !v27 )
            {
              SecretAgreementMasterKey = -2146893786;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v28,
                  v29,
                  (unsigned int)"Status",
                  38,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                  151);
              }
              goto LABEL_34;
            }
            SecretAgreementMasterKey = TlsGenerateSecretAgreementMasterKey(
                                         v41,
                                         v23,
                                         *(_QWORD *)(v29 + 24),
                                         *(_QWORD *)(v27 + 24),
                                         a7);
            if ( (SecretAgreementMasterKey & 0x80000000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v30,
                  v32,
                  (unsigned int)"Status",
                  SecretAgreementMasterKey,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                  167);
              }
              goto LABEL_34;
            }
            goto LABEL_24;
          }
          v39 = 2959;
LABEL_71:
          SecretAgreementMasterKey = -2146893786;
          DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v39);
          goto LABEL_34;
        }
        if ( !v21 )
        {
          SecretAgreementMasterKey = -2146893783;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v22,
              v24,
              (unsigned int)"Status",
              41,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              67);
          goto LABEL_34;
        }
        if ( a5 == 2 )
        {
          v36 = 2895;
          goto LABEL_58;
        }
        if ( a2 )
        {
          if ( *a2 < 0x3Cu || a2[1] != 1936944183 )
          {
            v39 = 2925;
            goto LABEL_71;
          }
          SecretAgreementMasterKey = TlsGenerateMasterKey(v41, a2, v23, a7);
        }
        else
        {
          MasterKey = TlsEncryptPreMasterKey(v25, v46, v43, a7, v20[28], v45, a9, v44);
          SecretAgreementMasterKey = MasterKey;
          if ( MasterKey < 0 )
          {
            v38 = 2915;
LABEL_62:
            DebugTraceError(
              (unsigned int)MasterKey,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              v38);
            goto LABEL_34;
          }
          v34 = &v47;
          v35 = 48;
          SecretAgreementMasterKey = TlsGenerateMasterKey(v41, v46, v23, a7);
          do
          {
            *v34++ = 0;
            --v35;
          }
          while ( v35 );
        }
        if ( (SecretAgreementMasterKey & 0x80000000) != 0 )
        {
          DebugTraceError(
            SecretAgreementMasterKey,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            2940);
          goto LABEL_34;
        }
        goto LABEL_24;
      }
LABEL_28:
      SecretAgreementMasterKey = -2146893783;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          v15,
          (unsigned int)"Status",
          41,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          6);
    }
    else
    {
      SecretAgreementMasterKey = -2146893785;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          v15,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          254);
    }
  }
  else
  {
    SecretAgreementMasterKey = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        v15,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        247);
  }
  return SecretAgreementMasterKey;
}

```

## disassembly

```asm
0x180006070  push    rbx
0x180006072  push    rbp
0x180006073  push    rsi
0x180006074  push    r12
0x180006076  push    r13
0x180006078  push    r14
0x18000607a  push    r15
0x18000607c  sub     rsp, 0C0h
0x180006083  mov     rax, cs:__security_cookie
0x18000608a  xor     rax, rsp
0x18000608d  mov     [rsp+0F8h+var_50], rax
0x180006095  mov     rax, [rsp+0F8h+arg_38]
0x18000609d  xorps   xmm0, xmm0
0x1800060a0  mov     ebp, [rsp+0F8h+arg_20]
0x1800060a7  xor     r12d, r12d
0x1800060aa  mov     r15, [rsp+0F8h+arg_30]
0x1800060b2  mov     r14, r9
0x1800060b5  mov     [rsp+0F8h+var_98], rax
0x1800060ba  mov     r13, rdx
0x1800060bd  mov     rax, [rsp+0F8h+arg_48]
0x1800060c5  mov     [rsp+0F8h+var_A0], rax
0x1800060ca  xor     eax, eax
0x1800060cc  movups  xmmword ptr [rsp+0F8h+var_70], xmm0
0x1800060d4  mov     [rsp+0F8h+var_83], ax
0x1800060d9  mov     [rsp+0F8h+var_81], al
0x1800060dd  mov     [rsp+0F8h+var_A8], r8
0x1800060e2  mov     [rsp+0F8h+var_90], 3Ch ; '<'
0x1800060ea  mov     [rsp+0F8h+var_8C], 73736C37h
0x1800060f2  mov     [rsp+0F8h+var_88], ebp
0x1800060f6  mov     [rsp+0F8h+var_84], 0
0x1800060fb  movups  [rsp+0F8h+var_80], xmm0
0x180006100  mov     [rsp+0F8h+var_B0], r12
0x180006105  movups  xmmword ptr [rsp+0F8h+var_70+0Ch], xmm0
0x18000610d  call    SslpValidateProvHandle
0x180006112  mov     [rsp+0F8h+var_B8], rax
0x180006117  test    rax, rax
0x18000611a  jz      loc_180006345
0x180006120  test    r9, r9
0x180006123  jz      loc_18000639C
0x180006129  xor     ecx, ecx
0x18000612b  lea     r10, __ImageBase
0x180006132  cmp     ecx, 7
0x180006135  jnb     loc_1800062B8
0x18000613b  lea     rdx, ds:0[rcx*8]
0x180006143  movzx   eax, word ptr [rdx+r10+31A20h]
0x18000614c  cmp     eax, ebp
0x18000614e  jz      short loc_180006154
0x180006150  inc     ecx
0x180006152  jmp     short loc_180006132
0x180006154  mov     r9d, [rdx+r10+31A24h]
0x18000615c  test    r9d, r9d
0x18000615f  jz      loc_1800062B8
0x180006165  mov     r8d, [rsp+0F8h+arg_28]
0x18000616d  xor     eax, eax
0x18000616f  mov     edx, cs:g_dwCipherSuiteInfoTotalCount
0x180006175  cmp     eax, edx
0x180006177  jnb     loc_1800062B8
0x18000617d  mov     rbx, rva g_pCipherSuiteInfo[r10+rax*8]
0x180006185  test    rbx, rbx
0x180006188  jz      short loc_180006190
0x18000618a  cmp     [rbx+4], r8d
0x18000618e  jz      short loc_180006194
0x180006190  inc     eax
0x180006192  jmp     short loc_180006175
0x180006194  test    [rbx], r9d
0x180006197  jz      short loc_180006190
0x180006199  test    r15, r15
0x18000619c  jz      loc_180006488
0x1800061a2  mov     eax, [rsp+0F8h+arg_50]
0x1800061a9  test    eax, 0FFFFFFFCh
0x1800061ae  jnz     loc_1800064B0
0x1800061b4  test    al, 1
0x1800061b6  jz      loc_1800064D8
0x1800061bc  mov     esi, 1
0x1800061c1  mov     ecx, 50h ; 'P'
0x1800061c6  mov     [rsp+0F8h+var_40], rdi
0x1800061ce  call    SafeAllocaAllocateFromHeap
0x1800061d3  mov     rdi, rax
0x1800061d6  test    rax, rax
0x1800061d9  jz      loc_1800064E7
0x1800061df  xor     eax, eax
0x1800061e1  mov     [rdi+0Ch], eax
0x1800061e4  mov     [rdi+1Ch], rax
0x1800061e8  mov     [rdi+24h], rax
0x1800061ec  mov     [rdi+2Ch], rax
0x1800061f0  mov     [rdi+34h], rax
0x1800061f4  mov     [rdi+3Ch], rax
0x1800061f8  mov     [rdi+44h], rax
0x1800061fc  mov     [rdi+4Ch], eax
0x1800061ff  mov     dword ptr [rdi], 50h ; 'P'
0x180006205  mov     dword ptr [rdi+4], 73736C35h
0x18000620c  mov     [rdi+8], ebp
0x18000620f  mov     [rdi+10h], rbx
0x180006213  mov     [rdi+18h], esi
0x180006216  mov     ecx, [rbx+64h]
0x180006219  cmp     ecx, 1
0x18000621c  jz      loc_1800063E0
0x180006222  mov     r9d, [rbx+58h]
0x180006226  cmp     r9d, 30002h
0x18000622d  jnz     loc_180006656
0x180006233  mov     rcx, r13
0x180006236  call    SslpValidateEphemeralHandle
0x18000623b  mov     r8, rax
0x18000623e  test    rax, rax
0x180006241  jz      loc_18000662E
0x180006247  mov     rcx, [rsp+0F8h+var_A8]
0x18000624c  call    SslpValidateEphemeralHandle
0x180006251  test    rax, rax
0x180006254  jz      loc_18000642F
0x18000625a  mov     r8, [r8+18h]
0x18000625e  mov     rdx, rdi
0x180006261  mov     rcx, [rsp+0F8h+var_B8]
0x180006266  mov     [rsp+0F8h+var_C8], r9d
0x18000626b  mov     r9, [rax+18h]
0x18000626f  mov     [rsp+0F8h+var_D8], r15
0x180006274  call    TlsGenerateSecretAgreementMasterKey
0x180006279  mov     ebx, eax
0x18000627b  test    eax, eax
0x18000627d  js      short loc_1800062F7
0x18000627f  mov     [r14], rdi
0x180006282  mov     rdi, [rsp+0F8h+var_40]
0x18000628a  test    r12, r12
0x18000628d  jnz     loc_1800066D0
0x180006293  mov     eax, ebx
0x180006295  mov     rcx, [rsp+0F8h+var_50]
0x18000629d  xor     rcx, rsp; StackCookie
0x1800062a0  call    __security_check_cookie
0x1800062a5  add     rsp, 0C0h
0x1800062ac  pop     r15
0x1800062ae  pop     r14
0x1800062b0  pop     r13
0x1800062b2  pop     r12
0x1800062b4  pop     rsi
0x1800062b5  pop     rbp
0x1800062b6  pop     rbx
0x1800062b7  retn
0x1800062b8  mov     ebx, 80090029h
0x1800062bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062c4  lea     rax, WPP_GLOBAL_Control
0x1800062cb  cmp     rcx, rax
0x1800062ce  jz      short loc_180006293
0x1800062d0  test    byte ptr [rcx+1Ch], 1
0x1800062d4  jz      short loc_180006293
0x1800062d6  mov     [rsp+0F8h+var_C8], 0B06h
0x1800062de  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800062e5  mov     [rsp+0F8h+var_D0], rax
0x1800062ea  mov     dword ptr [rsp+0F8h+var_D8], 80090029h
0x1800062f2  jmp     loc_180006387
0x1800062f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062fe  lea     rax, WPP_GLOBAL_Control
0x180006305  cmp     rcx, rax
0x180006308  jz      short loc_180006338
0x18000630a  test    byte ptr [rcx+1Ch], 1
0x18000630e  jz      short loc_180006338
0x180006310  mov     [rsp+0F8h+var_C8], 0BA7h
0x180006318  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000631f  mov     [rsp+0F8h+var_D0], rax
0x180006324  mov     dword ptr [rsp+0F8h+var_D8], ebx
0x180006328  mov     rcx, [rcx+10h]
0x18000632c  lea     r9, aStatus; "Status"
0x180006333  call    WPP_SF_sDsd
0x180006338  mov     rcx, rdi
0x18000633b  call    MSCryptFree
0x180006340  jmp     loc_180006282
0x180006345  mov     ebx, 80090026h
0x18000634a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006351  lea     rax, WPP_GLOBAL_Control
0x180006358  cmp     rcx, rax
0x18000635b  jz      loc_180006293
0x180006361  test    byte ptr [rcx+1Ch], 1
0x180006365  jz      loc_180006293
0x18000636b  mov     [rsp+0F8h+var_C8], 0AF7h
0x180006373  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000637a  mov     [rsp+0F8h+var_D0], rax
0x18000637f  mov     dword ptr [rsp+0F8h+var_D8], 80090026h
0x180006387  mov     rcx, [rcx+10h]
0x18000638b  lea     r9, aStatus; "Status"
0x180006392  call    WPP_SF_sDsd
0x180006397  jmp     loc_180006293
0x18000639c  mov     ebx, 80090027h
0x1800063a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063a8  lea     rax, WPP_GLOBAL_Control
0x1800063af  cmp     rcx, rax
0x1800063b2  jz      loc_180006293
0x1800063b8  test    byte ptr [rcx+1Ch], 1
0x1800063bc  jz      loc_180006293
0x1800063c2  mov     [rsp+0F8h+var_C8], 0AFEh
0x1800063ca  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800063d1  mov     [rsp+0F8h+var_D0], rax
0x1800063d6  mov     dword ptr [rsp+0F8h+var_D8], 80090027h
0x1800063de  jmp     short loc_180006387
0x1800063e0  test    esi, esi
0x1800063e2  jnz     loc_18000650F
0x1800063e8  mov     ebx, 80090029h
0x1800063ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063f4  lea     rax, WPP_GLOBAL_Control
0x1800063fb  cmp     rcx, rax
0x1800063fe  jz      loc_180006338
0x180006404  test    byte ptr [rcx+1Ch], 1
0x180006408  jz      loc_180006338
0x18000640e  mov     [rsp+0F8h+var_C8], 0B43h
0x180006416  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000641d  mov     [rsp+0F8h+var_D0], rax
0x180006422  mov     dword ptr [rsp+0F8h+var_D8], 80090029h
0x18000642a  jmp     loc_180006328
0x18000642f  mov     ebx, 80090026h
0x180006434  mov     rcx, cs:WPP_GLOBAL_Control
0x18000643b  lea     rax, WPP_GLOBAL_Control
0x180006442  cmp     rcx, rax
0x180006445  jz      loc_180006338
0x18000644b  test    byte ptr [rcx+1Ch], 1
0x18000644f  jz      loc_180006338
0x180006455  mov     [rsp+0F8h+var_C8], 0B97h
0x18000645d  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006464  mov     [rsp+0F8h+var_D0], rax
0x180006469  mov     dword ptr [rsp+0F8h+var_D8], 80090026h
0x180006471  jmp     loc_180006328
0x180006476  mov     [rsi], r12b
0x180006479  lea     rsi, [rsi+1]
0x18000647d  sub     rbp, 1
0x180006481  jnz     short loc_180006476
0x180006483  jmp     loc_1800065FE
0x180006488  mov     r9d, 0B0Dh
0x18000648e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006495  lea     rdx, aStatus; "Status"
0x18000649c  mov     ecx, 80090027h
0x1800064a1  mov     ebx, 80090027h
0x1800064a6  call    DebugTraceError
0x1800064ab  jmp     loc_180006293
0x1800064b0  mov     r9d, 0B14h
0x1800064b6  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800064bd  lea     rdx, aStatus; "Status"
0x1800064c4  mov     ecx, 80090009h
0x1800064c9  mov     ebx, 80090009h
0x1800064ce  call    DebugTraceError
0x1800064d3  jmp     loc_180006293
0x1800064d8  test    al, 2
0x1800064da  jz      loc_1800066DD
0x1800064e0  xor     esi, esi
0x1800064e2  jmp     loc_1800061C1
0x1800064e7  mov     r9d, 0B32h
0x1800064ed  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800064f4  lea     rdx, aStatus; "Status"
0x1800064fb  mov     ecx, 8009000Eh
0x180006500  mov     ebx, 8009000Eh
0x180006505  call    DebugTraceError
0x18000650a  jmp     loc_180006282
0x18000650f  cmp     ebp, 2
0x180006512  jnz     short loc_180006544
0x180006514  mov     r9d, 0B4Fh
0x18000651a  jmp     short loc_180006522
0x18000651c  mov     r9d, 0BC6h
0x180006522  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006529  mov     ecx, 80090029h
0x18000652e  lea     rdx, aStatus; "Status"
0x180006535  mov     ebx, 80090029h
0x18000653a  call    DebugTraceError
0x18000653f  jmp     loc_180006338
0x180006544  test    r13, r13
0x180006547  jnz     loc_1800065D8
0x18000654d  mov     rax, [rsp+0F8h+var_A0]
0x180006552  lea     rdx, [rsp+0F8h+var_90]
0x180006557  mov     r8, [rsp+0F8h+var_A8]
0x18000655c  mov     r9, r15
0x18000655f  mov     [rsp+0F8h+var_C0], rax
0x180006564  mov     eax, [rsp+0F8h+arg_40]
0x18000656b  mov     [rsp+0F8h+var_C8], eax
0x18000656f  mov     rax, [rsp+0F8h+var_98]
0x180006574  mov     [rsp+0F8h+var_D0], rax
0x180006579  mov     eax, [rbx+70h]
0x18000657c  mov     dword ptr [rsp+0F8h+var_D8], eax
0x180006580  call    TlsEncryptPreMasterKey
0x180006585  mov     ebx, eax
0x180006587  test    eax, eax
0x180006589  jns     short loc_1800065B3
0x18000658b  mov     r9d, 0B63h
0x180006591  jmp     short loc_180006599
0x180006593  mov     r9d, 0BBFh
0x180006599  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800065a0  mov     ecx, eax
0x1800065a2  lea     rdx, aStatus; "Status"
0x1800065a9  call    DebugTraceError
0x1800065ae  jmp     loc_180006338
0x1800065b3  mov     rcx, [rsp+0F8h+var_B8]
0x1800065b8  lea     rdx, [rsp+0F8h+var_90]
0x1800065bd  mov     r9, r15
0x1800065c0  lea     rsi, [rdx+0Ch]
0x1800065c4  mov     r8, rdi
0x1800065c7  mov     ebp, 30h ; '0'
0x1800065cc  call    TlsGenerateMasterKey
0x1800065d1  mov     ebx, eax
0x1800065d3  jmp     loc_180006476
0x1800065d8  cmp     dword ptr [r13+0], 3Ch ; '<'
0x1800065dd  jb      short loc_180006626
0x1800065df  cmp     dword ptr [r13+4], 73736C37h
0x1800065e7  jnz     short loc_180006626
0x1800065e9  mov     rcx, [rsp+0F8h+var_B8]
0x1800065ee  mov     r9, r15
0x1800065f1  mov     r8, rdi
0x1800065f4  mov     rdx, r13
  ... truncated ...
```
