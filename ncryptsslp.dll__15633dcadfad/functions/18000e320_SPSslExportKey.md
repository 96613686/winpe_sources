# SPSslExportKey

- ea: `0x18000e320`
- end: `0x18000e7dc`
- name: `SPSslExportKey`
- size: `1212`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, __int64, unsigned int, int *, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x180007960`
- `0x18000b594`
- `0x18000b654`
- `0x18000e320`
- `0x18000e7f0`
- `0x180013c6c`
- `0x1800185e0`
- `0x180021da8`
- `0x180022e04`

## import_xrefs

- `bcrypt!BCryptExportKey` at `0x18000e494`
- `bcrypt!BCryptExportKey` at `0x18000e533`
- `bcrypt!BCryptExportKey` at `0x18000e494`
- `bcrypt!BCryptExportKey` at `0x18000e533`

## string_xrefs

- `0x18000e3b8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000e4cd`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000e7c4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslExportKey(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        unsigned int a5,
        int *a6,
        int a7)
{
  ULONG v7; // r15d
  __int64 v10; // rdx
  __int64 v11; // r10
  int v12; // eax
  int v13; // edx
  __int64 v14; // rbp
  unsigned int v15; // ebx
  _QWORD *v16; // rcx
  int v18; // eax
  int v19; // ecx
  int v20; // edx
  _QWORD *v21; // rcx
  int v22; // ecx
  NTSTATUS v23; // eax
  int v24; // edx
  __int128 v25; // xmm0
  __int64 v26; // rbx
  __int64 v27; // r9
  __int64 v28; // rcx
  char dwFlags; // [rsp+30h] [rbp-58h]
  char dwFlagsa; // [rsp+30h] [rbp-58h]
  ULONG pcbResult[18]; // [rsp+40h] [rbp-48h] BYREF

  v7 = 0;
  pcbResult[0] = 0;
  if ( !SslpValidateProvHandle(a1) )
  {
    v27 = 2203;
    goto LABEL_69;
  }
  if ( !a6 )
  {
    v15 = -2146893785;
    v27 = 2210;
    v28 = 2148073511LL;
LABEL_70:
    DebugTraceError(v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v27);
    return v15;
  }
  if ( a7 )
  {
    v15 = -2146893815;
    v27 = 2217;
    v28 = 2148073481LL;
    goto LABEL_70;
  }
  if ( !v10 )
  {
    v27 = 2224;
    goto LABEL_69;
  }
  v12 = *(_DWORD *)(v10 + 4);
  if ( v12 == 1936944179 )
  {
    v14 = SslpValidateKeyHandle(v10);
    if ( !v14 )
    {
      v15 = -2146893786;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        dwFlags = -67;
LABEL_10:
        WPP_SF_sDsd(
          v16[2],
          v13,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          dwFlags);
        return v15;
      }
      return v15;
    }
    if ( !wcscmp(a3, L"OpaqueKeyBlob") )
    {
      if ( a4 && a5 >= 0x50 )
      {
        if ( !*(_QWORD *)(v14 + 32) )
        {
LABEL_33:
          *(_DWORD *)(a4 + 4) = 1936944179;
          v24 = v7 + 80;
          *(_DWORD *)a4 = v7 + 80;
          *(_DWORD *)(a4 + 8) = *(_DWORD *)(v14 + 8);
          *(_DWORD *)(a4 + 12) = *(_DWORD *)(*(_QWORD *)(v14 + 16) + 4LL);
          *(_DWORD *)(a4 + 16) = *(_DWORD *)(v14 + 24);
          *(_DWORD *)(a4 + 20) = v7;
          *(_DWORD *)(a4 + 24) = *(_DWORD *)(v14 + 104);
          *(_DWORD *)(a4 + 76) = *(_DWORD *)(v14 + 108);
          *(_OWORD *)(a4 + 28) = *(_OWORD *)(v14 + 56);
          *(_OWORD *)(a4 + 44) = *(_OWORD *)(v14 + 72);
          v25 = *(_OWORD *)(v14 + 88);
LABEL_34:
          *(_OWORD *)(a4 + 60) = v25;
          *a6 = v24;
          return 0;
        }
        v22 = *(_DWORD *)(v14 + 108);
        if ( ((v22 - 4) & 0xFFFFFFFC) == 0 && v22 != 5 )
          a3 = L"KeyDataBlob";
        v23 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)(v14 + 32), 0, a3, (PUCHAR)(a4 + 80), a5 - 80, pcbResult, 0);
        v15 = v23;
        if ( v23 != -1073741789 )
        {
          if ( v23 >= 0 )
          {
            v7 = pcbResult[0];
            goto LABEL_33;
          }
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v15;
          dwFlagsa = 9;
LABEL_26:
          WPP_SF_sDsd(
            v21[2],
            v20,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            (unsigned int)"Status",
            v15,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            dwFlagsa);
          return v15;
        }
        *a6 = pcbResult[0] + 80;
      }
      else
      {
        v15 = 0;
        if ( *(_QWORD *)(v14 + 32) )
        {
          v19 = *(_DWORD *)(v14 + 108);
          if ( ((v19 - 4) & 0xFFFFFFFC) == 0 && v19 != 5 )
            a3 = L"KeyDataBlob";
          v15 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)(v14 + 32), 0, a3, 0, 0, pcbResult, 0);
          if ( (v15 & 0x80000000) != 0 )
          {
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              return v15;
            dwFlagsa = -34;
            goto LABEL_26;
          }
          v7 = pcbResult[0];
        }
        *a6 = v7 + 80;
        if ( !a4 )
          return v15;
      }
      return (unsigned int)-2146893784;
    }
    v27 = 2244;
    goto LABEL_52;
  }
  if ( v12 != 1936944181 )
  {
    switch ( v12 )
    {
      case 1936944182:
        v18 = SslpExportEphemeralKey(v11, a3, a4, a5, a6, 0);
        v15 = v18;
        if ( v18 >= 0 )
          return 0;
        v27 = 2403;
        goto LABEL_61;
      case 1936944188:
        v18 = SslpExportKemKey(v11, a3, a4, a5, a6, 0);
        v15 = v18;
        if ( v18 >= 0 )
          return 0;
        v27 = 2418;
        goto LABEL_61;
      case 1936944187:
        v18 = SslpExportHybridKey(v11, a3, a4, a5, a6, 0);
        v15 = v18;
        if ( v18 >= 0 )
          return 0;
        v27 = 2433;
LABEL_61:
        v28 = (unsigned int)v18;
        goto LABEL_70;
    }
    v27 = 2441;
LABEL_69:
    v28 = 2148073510LL;
    v15 = -2146893786;
    goto LABEL_70;
  }
  v26 = SslpValidateMasterKeyHandle(v11);
  if ( v26 )
  {
    if ( !wcscmp(a3, L"OpaqueKeyBlob") )
    {
      v24 = 80;
      if ( !a4 || a5 < 0x50 )
      {
        *a6 = 80;
        return a4 != 0 ? 0x80090028 : 0;
      }
      *(_DWORD *)a4 = 80;
      *(_DWORD *)(a4 + 4) = 1936944181;
      *(_DWORD *)(a4 + 8) = *(_DWORD *)(v26 + 8);
      *(_DWORD *)(a4 + 12) = *(_DWORD *)(*(_QWORD *)(v26 + 16) + 4LL);
      *(_DWORD *)(a4 + 16) = *(_DWORD *)(v26 + 24);
      *(_DWORD *)(a4 + 20) = 0;
      *(_DWORD *)(a4 + 24) = *(_DWORD *)(v26 + 76);
      *(_OWORD *)(a4 + 28) = *(_OWORD *)(v26 + 28);
      *(_OWORD *)(a4 + 44) = *(_OWORD *)(v26 + 44);
      v25 = *(_OWORD *)(v26 + 60);
      goto LABEL_34;
    }
    v27 = 2354;
LABEL_52:
    v15 = -2146893783;
    v28 = 2148073513LL;
    goto LABEL_70;
  }
  v15 = -2146893786;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    dwFlags = 43;
    goto LABEL_10;
  }
  return v15;
}

```

## disassembly

```asm
0x18000e320  push    rbx
0x18000e322  push    rbp
0x18000e323  push    rsi
0x18000e324  push    rdi
0x18000e325  push    r14
0x18000e327  push    r15
0x18000e329  sub     rsp, 58h
0x18000e32d  xor     r15d, r15d
0x18000e330  mov     rdi, r9
0x18000e333  mov     [rsp+88h+var_48], r15d
0x18000e338  mov     rsi, r8
0x18000e33b  mov     r10, rdx
0x18000e33e  call    SslpValidateProvHandle
0x18000e343  test    rax, rax
0x18000e346  jz      loc_18000E64A
0x18000e34c  mov     r14, [rsp+88h+arg_28]
0x18000e354  test    r14, r14
0x18000e357  jz      loc_18000E655
0x18000e35d  cmp     [rsp+88h+arg_30], r15d
0x18000e365  jnz     loc_18000E66A
0x18000e36b  test    rdx, rdx
0x18000e36e  jz      loc_18000E67F
0x18000e374  mov     eax, [rdx+4]
0x18000e377  cmp     eax, 73736C33h
0x18000e37c  jnz     short loc_18000E3EB
0x18000e37e  mov     rcx, rdx
0x18000e381  call    SslpValidateKeyHandle
0x18000e386  mov     rbp, rax
0x18000e389  test    rax, rax
0x18000e38c  jnz     loc_18000E431
0x18000e392  mov     ebx, 80090026h
0x18000e397  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e39e  lea     rax, WPP_GLOBAL_Control
0x18000e3a5  cmp     rcx, rax
0x18000e3a8  jz      short loc_18000E3DC
0x18000e3aa  test    byte ptr [rcx+1Ch], 1
0x18000e3ae  jz      short loc_18000E3DC
0x18000e3b0  mov     dword ptr [rsp+88h+dwFlags], 8BDh
0x18000e3b8  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e3bf  mov     [rsp+88h+pcbResult], r8
0x18000e3c4  mov     [rsp+88h+cbOutput], 80090026h
0x18000e3cc  mov     rcx, [rcx+10h]
0x18000e3d0  lea     r9, aStatus; "Status"
0x18000e3d7  call    WPP_SF_sDsd
0x18000e3dc  mov     eax, ebx
0x18000e3de  add     rsp, 58h
0x18000e3e2  pop     r15
0x18000e3e4  pop     r14
0x18000e3e6  pop     rdi
0x18000e3e7  pop     rsi
0x18000e3e8  pop     rbp
0x18000e3e9  pop     rbx
0x18000e3ea  retn
0x18000e3eb  mov     ebp, 73736C35h
0x18000e3f0  cmp     eax, ebp
0x18000e3f2  jz      loc_18000E5A6
0x18000e3f8  cmp     eax, 73736C36h
0x18000e3fd  jnz     loc_18000E748
0x18000e403  mov     r9d, [rsp+88h+arg_20]
0x18000e40b  mov     r8, rdi
0x18000e40e  mov     dword ptr [rsp+88h+pcbResult], r15d
0x18000e413  mov     rdx, rsi
0x18000e416  mov     rcx, r10
0x18000e419  mov     qword ptr [rsp+88h+cbOutput], r14
0x18000e41e  call    SslpExportEphemeralKey
0x18000e423  mov     ebx, eax
0x18000e425  test    eax, eax
0x18000e427  js      loc_18000E736
0x18000e42d  xor     ebx, ebx
0x18000e42f  jmp     short loc_18000E3DC
0x18000e431  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x18000e438  mov     rcx, rsi; String1
0x18000e43b  call    wcscmp
0x18000e440  test    eax, eax
0x18000e442  jnz     loc_18000E68A
0x18000e448  test    rdi, rdi
0x18000e44b  jnz     loc_18000E4E2
0x18000e451  xor     ebx, ebx
0x18000e453  cmp     [rbp+20h], rbx
0x18000e457  jz      loc_18000E5ED
0x18000e45d  mov     ecx, [rbp+6Ch]
0x18000e460  lea     eax, [rcx-4]
0x18000e463  test    eax, 0FFFFFFFCh
0x18000e468  jnz     short loc_18000E476
0x18000e46a  cmp     ecx, 5
0x18000e46d  jz      short loc_18000E476
0x18000e46f  lea     rsi, aKeydatablob; "KeyDataBlob"
0x18000e476  mov     rcx, [rbp+20h]; hKey
0x18000e47a  lea     rax, [rsp+88h+var_48]
0x18000e47f  mov     dword ptr [rsp+88h+dwFlags], ebx; dwFlags
0x18000e483  xor     r9d, r9d; pbOutput
0x18000e486  mov     [rsp+88h+pcbResult], rax; pcbResult
0x18000e48b  mov     r8, rsi; pszBlobType
0x18000e48e  xor     edx, edx; hExportKey
0x18000e490  mov     [rsp+88h+cbOutput], ebx; cbOutput
0x18000e494  call    cs:__imp_BCryptExportKey
0x18000e49a  mov     ebx, eax
0x18000e49c  test    eax, eax
0x18000e49e  jns     loc_18000E6B6
0x18000e4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4ab  lea     rax, WPP_GLOBAL_Control
0x18000e4b2  cmp     rcx, rax
0x18000e4b5  jz      loc_18000E3DC
0x18000e4bb  test    byte ptr [rcx+1Ch], 1
0x18000e4bf  jz      loc_18000E3DC
0x18000e4c5  mov     dword ptr [rsp+88h+dwFlags], 8DEh
0x18000e4cd  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e4d4  mov     [rsp+88h+pcbResult], r8
0x18000e4d9  mov     [rsp+88h+cbOutput], ebx
0x18000e4dd  jmp     loc_18000E3CC
0x18000e4e2  mov     r8d, [rsp+88h+arg_20]
0x18000e4ea  mov     edx, 50h ; 'P'
0x18000e4ef  cmp     r8d, edx
0x18000e4f2  jb      loc_18000E451
0x18000e4f8  cmp     [rbp+20h], r15
0x18000e4fc  jz      short loc_18000E553
0x18000e4fe  mov     ecx, [rbp+6Ch]
0x18000e501  lea     eax, [rcx-4]
0x18000e504  test    eax, 0FFFFFFFCh
0x18000e509  jz      loc_18000E607
0x18000e50f  lea     eax, [r8-50h]
0x18000e513  mov     dword ptr [rsp+88h+dwFlags], r15d; dwFlags
0x18000e518  lea     rcx, [rsp+88h+var_48]
0x18000e51d  mov     r8, rsi; pszBlobType
0x18000e520  mov     [rsp+88h+pcbResult], rcx; pcbResult
0x18000e525  lea     r9, [rdi+50h]; pbOutput
0x18000e529  mov     rcx, [rbp+20h]; hKey
0x18000e52d  xor     edx, edx; hExportKey
0x18000e52f  mov     [rsp+88h+cbOutput], eax; cbOutput
0x18000e533  call    cs:__imp_BCryptExportKey
0x18000e539  mov     ebx, eax
0x18000e53b  cmp     eax, 0C0000023h
0x18000e540  jz      loc_18000E6A7
0x18000e546  test    eax, eax
0x18000e548  js      loc_18000E61C
0x18000e54e  mov     r15d, [rsp+88h+var_48]
0x18000e553  mov     dword ptr [rdi+4], 73736C33h
0x18000e55a  lea     edx, [r15+50h]
0x18000e55e  mov     [rdi], edx
0x18000e560  mov     eax, [rbp+8]
0x18000e563  mov     [rdi+8], eax
0x18000e566  mov     rax, [rbp+10h]
0x18000e56a  mov     ecx, [rax+4]
0x18000e56d  mov     [rdi+0Ch], ecx
0x18000e570  mov     eax, [rbp+18h]
0x18000e573  mov     [rdi+10h], eax
0x18000e576  mov     [rdi+14h], r15d
0x18000e57a  mov     eax, [rbp+68h]
0x18000e57d  mov     [rdi+18h], eax
0x18000e580  mov     eax, [rbp+6Ch]
0x18000e583  mov     [rdi+4Ch], eax
0x18000e586  movups  xmm0, xmmword ptr [rbp+38h]
0x18000e58a  movups  xmmword ptr [rdi+1Ch], xmm0
0x18000e58e  movups  xmm1, xmmword ptr [rbp+48h]
0x18000e592  movups  xmmword ptr [rdi+2Ch], xmm1
0x18000e596  movups  xmm0, xmmword ptr [rbp+58h]
0x18000e59a  movups  xmmword ptr [rdi+3Ch], xmm0
0x18000e59e  mov     [r14], edx
0x18000e5a1  jmp     loc_18000E42D
0x18000e5a6  mov     rcx, r10
0x18000e5a9  call    SslpValidateMasterKeyHandle
0x18000e5ae  mov     rbx, rax
0x18000e5b1  test    rax, rax
0x18000e5b4  jnz     loc_18000E6C0
0x18000e5ba  mov     ebx, 80090026h
0x18000e5bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5c6  lea     rax, WPP_GLOBAL_Control
0x18000e5cd  cmp     rcx, rax
0x18000e5d0  jz      loc_18000E3DC
0x18000e5d6  test    byte ptr [rcx+1Ch], 1
0x18000e5da  jz      loc_18000E3DC
0x18000e5e0  mov     dword ptr [rsp+88h+dwFlags], 92Bh
0x18000e5e8  jmp     loc_18000E3B8
0x18000e5ed  lea     eax, [r15+50h]
0x18000e5f1  mov     [r14], eax
0x18000e5f4  test    rdi, rdi
0x18000e5f7  jz      loc_18000E3DC
0x18000e5fd  mov     ebx, 80090028h
0x18000e602  jmp     loc_18000E3DC
0x18000e607  cmp     ecx, 5
0x18000e60a  jz      loc_18000E50F
0x18000e610  lea     rsi, aKeydatablob; "KeyDataBlob"
0x18000e617  jmp     loc_18000E50F
0x18000e61c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e623  lea     rax, WPP_GLOBAL_Control
0x18000e62a  cmp     rcx, rax
0x18000e62d  jz      loc_18000E3DC
0x18000e633  test    byte ptr [rcx+1Ch], 1
0x18000e637  jz      loc_18000E3DC
0x18000e63d  mov     dword ptr [rsp+88h+dwFlags], 909h
0x18000e645  jmp     loc_18000E4CD
0x18000e64a  mov     r9d, 89Bh
0x18000e650  jmp     loc_18000E7BA
0x18000e655  mov     ebx, 80090027h
0x18000e65a  mov     r9d, 8A2h
0x18000e660  mov     ecx, 80090027h
0x18000e665  jmp     loc_18000E7C4
0x18000e66a  mov     ebx, 80090009h
0x18000e66f  mov     r9d, 8A9h
0x18000e675  mov     ecx, 80090009h
0x18000e67a  jmp     loc_18000E7C4
0x18000e67f  mov     r9d, 8B0h
0x18000e685  jmp     loc_18000E7BA
0x18000e68a  mov     r9d, 8C4h
0x18000e690  jmp     short loc_18000E698
0x18000e692  mov     r9d, 932h
0x18000e698  mov     ebx, 80090029h
0x18000e69d  mov     ecx, 80090029h
0x18000e6a2  jmp     loc_18000E7C4
0x18000e6a7  mov     eax, [rsp+88h+var_48]
0x18000e6ab  add     eax, 50h ; 'P'
0x18000e6ae  mov     [r14], eax
0x18000e6b1  jmp     loc_18000E5FD
0x18000e6b6  mov     r15d, [rsp+88h+var_48]
0x18000e6bb  jmp     loc_18000E5ED
0x18000e6c0  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x18000e6c7  mov     rcx, rsi; String1
0x18000e6ca  call    wcscmp
0x18000e6cf  test    eax, eax
0x18000e6d1  jnz     short loc_18000E692
0x18000e6d3  lea     edx, [rax+50h]
0x18000e6d6  test    rdi, rdi
0x18000e6d9  jz      short loc_18000E722
0x18000e6db  cmp     [rsp+88h+arg_20], edx
0x18000e6e2  jb      short loc_18000E722
0x18000e6e4  mov     [rdi], edx
0x18000e6e6  mov     [rdi+4], ebp
0x18000e6e9  mov     eax, [rbx+8]
0x18000e6ec  mov     [rdi+8], eax
0x18000e6ef  mov     rax, [rbx+10h]
0x18000e6f3  mov     ecx, [rax+4]
0x18000e6f6  mov     [rdi+0Ch], ecx
0x18000e6f9  mov     eax, [rbx+18h]
0x18000e6fc  mov     [rdi+10h], eax
0x18000e6ff  mov     [rdi+14h], r15d
0x18000e703  mov     eax, [rbx+4Ch]
0x18000e706  mov     [rdi+18h], eax
0x18000e709  movups  xmm0, xmmword ptr [rbx+1Ch]
0x18000e70d  movups  xmmword ptr [rdi+1Ch], xmm0
0x18000e711  movups  xmm1, xmmword ptr [rbx+2Ch]
0x18000e715  movups  xmmword ptr [rdi+2Ch], xmm1
0x18000e719  movups  xmm0, xmmword ptr [rbx+3Ch]
0x18000e71d  jmp     loc_18000E59A
0x18000e722  neg     rdi
0x18000e725  mov     [r14], edx
0x18000e728  mov     ebx, 80090028h
0x18000e72d  sbb     eax, eax
0x18000e72f  and     ebx, eax
0x18000e731  jmp     loc_18000E3DC
0x18000e736  mov     r9d, 963h
0x18000e73c  jmp     short loc_18000E744
0x18000e73e  mov     r9d, 981h
0x18000e744  mov     ecx, eax
0x18000e746  jmp     short loc_18000E7C4
0x18000e748  cmp     eax, 73736C3Ch
0x18000e74d  jnz     short loc_18000E781
0x18000e74f  mov     r9d, [rsp+88h+arg_20]
0x18000e757  mov     r8, rdi
0x18000e75a  mov     dword ptr [rsp+88h+pcbResult], r15d
0x18000e75f  mov     rdx, rsi
0x18000e762  mov     rcx, r10
0x18000e765  mov     qword ptr [rsp+88h+cbOutput], r14
0x18000e76a  call    SslpExportKemKey
0x18000e76f  mov     ebx, eax
0x18000e771  test    eax, eax
0x18000e773  jns     loc_18000E42D
0x18000e779  mov     r9d, 972h
0x18000e77f  jmp     short loc_18000E744
0x18000e781  cmp     eax, 73736C3Bh
0x18000e786  jnz     short loc_18000E7B4
0x18000e788  mov     r9d, [rsp+88h+arg_20]
0x18000e790  mov     r8, rdi
0x18000e793  mov     dword ptr [rsp+88h+pcbResult], r15d
0x18000e798  mov     rdx, rsi
0x18000e79b  mov     rcx, r10
0x18000e79e  mov     qword ptr [rsp+88h+cbOutput], r14
0x18000e7a3  call    SslpExportHybridKey
0x18000e7a8  mov     ebx, eax
0x18000e7aa  test    eax, eax
0x18000e7ac  jns     loc_18000E42D
0x18000e7b2  jmp     short loc_18000E73E
0x18000e7b4  mov     r9d, 989h
0x18000e7ba  mov     ecx, 80090026h
0x18000e7bf  mov     ebx, 80090026h
0x18000e7c4  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e7cb  lea     rdx, aStatus; "Status"
0x18000e7d2  call    DebugTraceError
0x18000e7d7  jmp     loc_18000E3DC
```
