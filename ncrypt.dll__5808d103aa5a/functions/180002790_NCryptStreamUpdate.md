# NCryptStreamUpdate

- ea: `0x180002790`
- end: `0x180002c2e`
- name: `NCryptStreamUpdate`
- size: `1182`
- prototype: `__int64 __fastcall(__int64, char *, unsigned __int64, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000260c`
- `0x180002790`
- `0x180002c34`
- `0x180003a50`
- `0x180007098`
- `0x18000d02c`
- `0x18000e120`
- `0x18001f15d`
- `0x18001f175`

## import_xrefs

- `NTASN1!__imp_ASN1DER_DecTagLength` at `0x180002892`
- `NTASN1!__imp_ASN1DER_DecTagLength` at `0x180002892`

## string_xrefs

- `0x18000299c`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`
- `0x180002a39`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`
- `0x180002a80`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`
- `0x180002afd`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`
- `0x180002b3b`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`

## pseudocode

```c
__int64 __fastcall NCryptStreamUpdate(__int64 a1, char *a2, unsigned __int64 a3, unsigned int a4)
{
  unsigned __int64 v5; // rsi
  char *v6; // r12
  unsigned __int64 v8; // rax
  bool v9; // zf
  unsigned int v10; // edx
  const void **v11; // r13
  unsigned int v12; // r8d
  char *v13; // rcx
  unsigned int updated; // eax
  int v15; // edx
  int v16; // r8d
  unsigned int v17; // ebx
  void *v18; // rax
  int v19; // edx
  int v20; // r8d
  size_t v21; // r8
  void *v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // r13d
  __int64 v25; // rcx
  __int64 v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // r13
  _BOOL8 v30; // r9
  int v31; // edx
  int v32; // r8d
  __int64 v33; // r9
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r8
  unsigned __int64 v37; // [rsp+40h] [rbp-19h] BYREF
  _DWORD v38[2]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v39; // [rsp+58h] [rbp-1h]
  char *v40; // [rsp+60h] [rbp+7h]
  char *v41; // [rsp+68h] [rbp+Fh]
  __int64 v42; // [rsp+70h] [rbp+17h]
  __int64 v43; // [rsp+78h] [rbp+1Fh]
  __int128 v44; // [rsp+80h] [rbp+27h]
  int v45; // [rsp+C0h] [rbp+67h] BYREF

  v5 = a3;
  v6 = a2;
  if ( !a1 || *(_QWORD *)a1 != 192 )
  {
    v17 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
        71);
    return v17;
  }
  if ( *(_DWORD *)(a1 + 40) )
  {
    v17 = -2146893786;
    v33 = 590;
    v34 = 2148073510LL;
    goto LABEL_49;
  }
  v8 = *(_QWORD *)(a1 + 48);
  *(_DWORD *)(a1 + 40) = a4;
  if ( v8 + a3 < v8 )
  {
    v17 = -1073741675;
    v33 = 603;
    v34 = 3221225621LL;
    goto LABEL_49;
  }
  v9 = *(_DWORD *)(a1 + 36) == 0;
  *(_QWORD *)(a1 + 48) = v8 + a3;
  if ( !v9 || *(_QWORD *)(a1 + 72) )
    goto LABEL_22;
  if ( !*(_QWORD *)(a1 + 144) )
  {
    v10 = *(_DWORD *)(a1 + 168);
    v11 = (const void **)(a1 + 160);
    v12 = 17 - v10;
    if ( v10 != 17 )
    {
      v27 = *(unsigned int *)(a1 + 168);
      v28 = (unsigned int)v5;
      if ( v5 >= v12 )
        v28 = v12;
      memcpy_0((char *)*v11 + v27, v6, (unsigned int)v28);
      *(_DWORD *)(a1 + 168) += v28;
      v6 += v28;
      v10 = *(_DWORD *)(a1 + 168);
      v5 -= v28;
    }
    if ( v10 < 2 )
      return 0;
    v13 = (char *)*v11;
    v38[0] = (unsigned int)*v11;
    v38[1] = HIDWORD(v13);
    v39 = v10;
    v40 = v13;
    v41 = &v13[v10];
    v45 = 0;
    v37 = 0;
    v44 = 0;
    v42 = 0;
    v43 = 0;
    updated = ASN1DER_DecTagLength(v38, &v45, &v37);
    v17 = updated;
    if ( updated )
    {
      if ( !a4 && *(_QWORD *)(a1 + 48) <= 6u )
        return 0;
      v33 = 674;
      goto LABEL_54;
    }
    if ( v45 != 536870928 || v37 > 0x7FFFFFF0 )
    {
      v17 = -2146893819;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          v16,
          (unsigned int)"Status",
          5,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
          179);
      return v17;
    }
    *(_DWORD *)(a1 + 156) = (_DWORD)v40 + v37 - v38[0];
    v18 = (void *)I_DefaultExtrenalAlloc();
    *(_QWORD *)(a1 + 144) = v18;
    if ( !v18 )
    {
      v17 = -2146893810;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v19,
          v20,
          (unsigned int)"Status",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
          195);
      return v17;
    }
    memcpy_0(v18, *v11, *(unsigned int *)(a1 + 168));
    v21 = *(unsigned int *)(a1 + 168);
    v22 = (void *)*v11;
    *(_DWORD *)(a1 + 152) = v21;
    memset_0(v22, 0, v21);
  }
  v23 = *(unsigned int *)(a1 + 152);
  v24 = v5;
  if ( (unsigned int)(*(_DWORD *)(a1 + 156) - v23) <= v5 )
    v24 = *(_DWORD *)(a1 + 156) - v23;
  if ( v24 )
  {
    memcpy_0((void *)(*(_QWORD *)(a1 + 144) + v23), v6, v24);
    *(_DWORD *)(a1 + 152) += v24;
    v6 += v24;
    v23 = *(unsigned int *)(a1 + 152);
    v5 -= v24;
  }
  if ( (unsigned int)v23 < *(_DWORD *)(a1 + 156) )
    return 0;
  updated = I_StreamOpenProtectedMessage(a1, v23, a4);
  v17 = updated;
  if ( updated )
  {
    v33 = 766;
LABEL_54:
    v34 = updated;
    goto LABEL_49;
  }
  v25 = *(_QWORD *)(a1 + 136);
  *(_QWORD *)(a1 + 72) = *(_QWORD *)(v25 + 24);
  if ( (*(_DWORD *)(a1 + 64) & 1) == 0 )
  {
    updated = CMSG_ImportContentEncryptionKey(
                *(_QWORD *)(v25 + 24),
                *(_QWORD *)(v25 + 32) + 72LL,
                *(_QWORD *)(a1 + 176),
                *(unsigned int *)(a1 + 184));
    v17 = updated;
    if ( updated )
    {
      v33 = 784;
      goto LABEL_54;
    }
    v35 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 32LL);
    v36 = *(unsigned int *)(v35 + 112);
    if ( !(_DWORD)v36 )
      goto LABEL_22;
    if ( !v5 && a4 )
    {
      updated = CMSG_UpdateStream(a1, *(_QWORD *)(v35 + 120), v36, 1);
      v17 = updated;
      if ( !updated )
        return v17;
      v33 = 809;
      goto LABEL_54;
    }
    v17 = -2146893819;
    v33 = 797;
    v34 = 2148073477LL;
LABEL_49:
    DebugTraceError(v34, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c", v33);
    return v17;
  }
LABEL_22:
  if ( (*(_DWORD *)(a1 + 64) & 1) != 0 )
    return 0;
  while ( 1 )
  {
    v29 = (unsigned int)v5;
    v5 -= (unsigned int)v5;
    v30 = a4 && !v5;
    v17 = CMSG_UpdateStream(a1, v6, (unsigned int)v29, v30);
    if ( v17 )
      break;
    if ( !v5 )
      return 0;
    v6 += v29;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v31,
      v32,
      (unsigned int)"Status",
      v17,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
      67);
  return v17;
}

```

## disassembly

```asm
0x180002790  mov     [rsp-8+arg_8], rbx
0x180002795  mov     [rsp-8+arg_10], rsi
0x18000279a  push    rbp
0x18000279b  push    rdi
0x18000279c  push    r12
0x18000279e  push    r13
0x1800027a0  push    r15
0x1800027a2  lea     rbp, [rsp-37h]
0x1800027a7  sub     rsp, 90h
0x1800027ae  mov     r15d, r9d
0x1800027b1  mov     rsi, r8
0x1800027b4  mov     r12, rdx
0x1800027b7  mov     rdi, rcx
0x1800027ba  test    rcx, rcx
0x1800027bd  jz      loc_180002976
0x1800027c3  cmp     qword ptr [rcx], 0C0h
0x1800027ca  jnz     loc_180002976
0x1800027d0  cmp     dword ptr [rcx+28h], 0
0x1800027d4  jnz     loc_180002B12
0x1800027da  mov     rax, [rcx+30h]
0x1800027de  mov     [rcx+28h], r9d
0x1800027e2  lea     rcx, [rax+r8]
0x1800027e6  cmp     rcx, rax
0x1800027e9  jb      loc_180002B4C
0x1800027ef  cmp     dword ptr [rdi+24h], 0
0x1800027f3  mov     [rdi+30h], rcx
0x1800027f7  jnz     loc_180002967
0x1800027fd  cmp     qword ptr [rdi+48h], 0
0x180002802  jnz     loc_180002967
0x180002808  cmp     qword ptr [rdi+90h], 0
0x180002810  jnz     loc_18000290D
0x180002816  mov     edx, [rdi+0A8h]
0x18000281c  lea     r13, [rdi+0A0h]
0x180002823  mov     r8d, 11h
0x180002829  sub     r8d, edx
0x18000282c  jnz     loc_1800029DE
0x180002832  cmp     edx, 2
0x180002835  jb      loc_180002972
0x18000283b  mov     rcx, [r13+0]
0x18000283f  lea     r8, [rbp+57h+var_70]
0x180002843  mov     rax, rcx
0x180002846  mov     [rbp+57h+var_60], ecx
0x180002849  sar     rax, 20h
0x18000284d  xorps   xmm0, xmm0
0x180002850  mov     [rbp+57h+var_5C], eax
0x180002853  mov     dword ptr [rbp+57h+var_50+4], eax
0x180002856  mov     eax, edx
0x180002858  lea     rdx, [rbp+57h+arg_0]
0x18000285c  mov     [rbp+57h+var_58], rax
0x180002860  add     rax, rcx
0x180002863  mov     dword ptr [rbp+57h+var_50], ecx
0x180002866  lea     rcx, [rbp+57h+var_60]
0x18000286a  mov     [rbp+57h+var_48], rax
0x18000286e  mov     [rbp+57h+arg_0], 0
0x180002875  mov     [rbp+57h+var_70], 0
0x18000287d  movdqa  [rbp+57h+var_30], xmm0
0x180002882  mov     [rbp+57h+var_40], 0
0x18000288a  mov     [rbp+57h+var_38], 0
0x180002892  call    cs:__imp_ASN1DER_DecTagLength
0x180002898  mov     ebx, eax
0x18000289a  test    eax, eax
0x18000289c  jnz     loc_180002B5E
0x1800028a2  cmp     [rbp+57h+arg_0], 20000010h
0x1800028a9  jnz     loc_180002A13
0x1800028af  mov     rcx, [rbp+57h+var_70]
0x1800028b3  cmp     rcx, 7FFFFFF0h
0x1800028ba  ja      loc_180002A13
0x1800028c0  sub     ecx, [rbp+57h+var_60]
0x1800028c3  add     ecx, dword ptr [rbp+57h+var_50]
0x1800028c6  mov     [rdi+9Ch], ecx
0x1800028cc  call    I_DefaultExtrenalAlloc
0x1800028d1  mov     [rdi+90h], rax
0x1800028d8  test    rax, rax
0x1800028db  jz      loc_180002A52
0x1800028e1  mov     r8d, [rdi+0A8h]; Size
0x1800028e8  mov     rcx, rax; void *
0x1800028eb  mov     rdx, [r13+0]; Src
0x1800028ef  call    memcpy_0
0x1800028f4  mov     r8d, [rdi+0A8h]; Size
0x1800028fb  xor     edx, edx; Val
0x1800028fd  mov     rcx, [r13+0]; void *
0x180002901  mov     [rdi+98h], r8d
0x180002908  call    memset_0
0x18000290d  mov     edx, [rdi+98h]
0x180002913  mov     r13d, esi
0x180002916  mov     eax, [rdi+9Ch]
0x18000291c  sub     eax, edx
0x18000291e  mov     ecx, eax
0x180002920  cmp     rcx, rsi
0x180002923  cmovbe  r13d, eax
0x180002927  test    r13d, r13d
0x18000292a  jnz     loc_180002B80
0x180002930  cmp     edx, [rdi+9Ch]
0x180002936  jb      short loc_180002972
0x180002938  mov     r8d, r15d
0x18000293b  mov     rcx, rdi
0x18000293e  call    I_StreamOpenProtectedMessage
0x180002943  mov     ebx, eax
0x180002945  test    eax, eax
0x180002947  jnz     loc_180002BB0
0x18000294d  mov     rcx, [rdi+88h]
0x180002954  mov     rax, [rcx+18h]
0x180002958  mov     [rdi+48h], rax
0x18000295c  mov     eax, [rdi+40h]
0x18000295f  test    al, 1
0x180002961  jz      loc_180002BB8
0x180002967  mov     eax, [rdi+40h]
0x18000296a  test    al, 1
0x18000296c  jz      loc_180002A99
0x180002972  xor     ebx, ebx
0x180002974  jmp     short loc_1800029C0
0x180002976  mov     ebx, 80090026h
0x18000297b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002982  lea     rax, WPP_GLOBAL_Control
0x180002989  cmp     rcx, rax
0x18000298c  jz      short loc_1800029C0
0x18000298e  test    byte ptr [rcx+1Ch], 1
0x180002992  jz      short loc_1800029C0
0x180002994  mov     [rsp+0B0h+var_80], 247h
0x18000299c  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800029a3  mov     [rsp+0B0h+var_88], rax
0x1800029a8  mov     [rsp+0B0h+var_90], 80090026h
0x1800029b0  mov     rcx, [rcx+10h]
0x1800029b4  lea     r9, aStatus; "Status"
0x1800029bb  call    WPP_SF_sDsd
0x1800029c0  lea     r11, [rsp+0B0h+var_20]
0x1800029c8  mov     eax, ebx
0x1800029ca  mov     rbx, [r11+38h]
0x1800029ce  mov     rsi, [r11+40h]
0x1800029d2  mov     rsp, r11
0x1800029d5  pop     r15
0x1800029d7  pop     r13
0x1800029d9  pop     r12
0x1800029db  pop     rdi
0x1800029dc  pop     rbp
0x1800029dd  retn
0x1800029de  mov     eax, r8d
0x1800029e1  mov     rcx, rdx
0x1800029e4  cmp     rsi, rax
0x1800029e7  mov     ebx, esi
0x1800029e9  mov     rdx, r12; Src
0x1800029ec  cmovnb  ebx, r8d
0x1800029f0  add     rcx, [r13+0]; void *
0x1800029f4  mov     r8d, ebx; Size
0x1800029f7  call    memcpy_0
0x1800029fc  add     [rdi+0A8h], ebx
0x180002a02  add     r12, rbx
0x180002a05  mov     edx, [rdi+0A8h]
0x180002a0b  sub     rsi, rbx
0x180002a0e  jmp     loc_180002832
0x180002a13  mov     ebx, 80090005h
0x180002a18  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a1f  lea     rax, WPP_GLOBAL_Control
0x180002a26  cmp     rcx, rax
0x180002a29  jz      short loc_1800029C0
0x180002a2b  test    byte ptr [rcx+1Ch], 1
0x180002a2f  jz      short loc_1800029C0
0x180002a31  mov     [rsp+0B0h+var_80], 2B3h
0x180002a39  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002a40  mov     [rsp+0B0h+var_88], rax
0x180002a45  mov     [rsp+0B0h+var_90], 80090005h
0x180002a4d  jmp     loc_1800029B0
0x180002a52  mov     ebx, 8009000Eh
0x180002a57  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a5e  lea     rax, WPP_GLOBAL_Control
0x180002a65  cmp     rcx, rax
0x180002a68  jz      loc_1800029C0
0x180002a6e  test    byte ptr [rcx+1Ch], 1
0x180002a72  jz      loc_1800029C0
0x180002a78  mov     [rsp+0B0h+var_80], 2C3h
0x180002a80  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002a87  mov     [rsp+0B0h+var_88], rax
0x180002a8c  mov     [rsp+0B0h+var_90], 8009000Eh
0x180002a94  jmp     loc_1800029B0
0x180002a99  mov     r13d, esi
0x180002a9c  sub     rsi, r13
0x180002a9f  test    r15d, r15d
0x180002aa2  jz      short loc_180002ACF
0x180002aa4  test    rsi, rsi
0x180002aa7  jnz     short loc_180002ACF
0x180002aa9  lea     r9d, [rsi+1]
0x180002aad  mov     r8d, r13d
0x180002ab0  mov     rdx, r12
0x180002ab3  mov     rcx, rdi
0x180002ab6  call    CMSG_UpdateStream
0x180002abb  mov     ebx, eax
0x180002abd  test    eax, eax
0x180002abf  jnz     short loc_180002AD4
0x180002ac1  test    rsi, rsi
0x180002ac4  jz      loc_180002972
0x180002aca  add     r12, r13
0x180002acd  jmp     short loc_180002A99
0x180002acf  xor     r9d, r9d
0x180002ad2  jmp     short loc_180002AAD
0x180002ad4  mov     rcx, cs:WPP_GLOBAL_Control
0x180002adb  lea     rax, WPP_GLOBAL_Control
0x180002ae2  cmp     rcx, rax
0x180002ae5  jz      loc_1800029C0
0x180002aeb  test    byte ptr [rcx+1Ch], 1
0x180002aef  jz      loc_1800029C0
0x180002af5  mov     [rsp+0B0h+var_80], 343h
0x180002afd  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002b04  mov     [rsp+0B0h+var_88], rax
0x180002b09  mov     [rsp+0B0h+var_90], ebx
0x180002b0d  jmp     loc_1800029B0
0x180002b12  mov     ebx, 80090026h
0x180002b17  mov     r9d, 24Eh
0x180002b1d  mov     ecx, 80090026h
0x180002b22  jmp     short loc_180002B34
0x180002b24  mov     ebx, 80090005h
0x180002b29  mov     r9d, 31Dh
0x180002b2f  mov     ecx, 80090005h
0x180002b34  lea     rdx, aStatus; "Status"
0x180002b3b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002b42  call    DebugTraceError
0x180002b47  jmp     loc_1800029C0
0x180002b4c  mov     ebx, 0C0000095h
0x180002b51  mov     r9d, 25Bh
0x180002b57  mov     ecx, 0C0000095h
0x180002b5c  jmp     short loc_180002B34
0x180002b5e  test    r15d, r15d
0x180002b61  jnz     short loc_180002B6E
0x180002b63  cmp     qword ptr [rdi+30h], 6
0x180002b68  jbe     loc_180002972
0x180002b6e  mov     r9d, 2A2h
0x180002b74  jmp     short loc_180002B7C
0x180002b76  mov     r9d, 329h
0x180002b7c  mov     ecx, eax
0x180002b7e  jmp     short loc_180002B34
0x180002b80  mov     rcx, rdx
0x180002b83  mov     r8d, r13d; Size
0x180002b86  add     rcx, [rdi+90h]; void *
0x180002b8d  mov     rdx, r12; Src
0x180002b90  mov     ebx, r13d
0x180002b93  call    memcpy_0
0x180002b98  add     [rdi+98h], r13d
0x180002b9f  add     r12, rbx
0x180002ba2  mov     edx, [rdi+98h]
0x180002ba8  sub     rsi, rbx
0x180002bab  jmp     loc_180002930
0x180002bb0  mov     r9d, 2FEh
0x180002bb6  jmp     short loc_180002B7C
0x180002bb8  mov     rdx, [rcx+20h]
0x180002bbc  mov     r9d, [rdi+0B8h]
0x180002bc3  add     rdx, 48h ; 'H'
0x180002bc7  mov     r8, [rdi+0B0h]
0x180002bce  mov     rcx, [rcx+18h]
0x180002bd2  call    CMSG_ImportContentEncryptionKey
0x180002bd7  mov     ebx, eax
0x180002bd9  test    eax, eax
0x180002bdb  jz      short loc_180002BE5
0x180002bdd  mov     r9d, 310h
0x180002be3  jmp     short loc_180002B7C
0x180002be5  mov     rax, [rdi+88h]
0x180002bec  mov     rdx, [rax+20h]
0x180002bf0  mov     r8d, [rdx+70h]
0x180002bf4  test    r8d, r8d
0x180002bf7  jz      loc_180002967
0x180002bfd  test    rsi, rsi
0x180002c00  jnz     loc_180002B24
0x180002c06  test    r15d, r15d
0x180002c09  jz      loc_180002B24
0x180002c0f  mov     rdx, [rdx+78h]
0x180002c13  lea     r9d, [rsi+1]
0x180002c17  mov     rcx, rdi
0x180002c1a  call    CMSG_UpdateStream
0x180002c1f  mov     ebx, eax
0x180002c21  test    eax, eax
0x180002c23  jz      loc_1800029C0
0x180002c29  jmp     loc_180002B76
```
