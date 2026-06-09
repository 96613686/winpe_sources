# _PkcsExportPlainTextKeyRsa

- ea: `0x18001f0e0`
- end: `0x18001f4f8`
- name: `_PkcsExportPlainTextKeyRsa`
- size: `1048`
- prototype: `__int64 __fastcall(__int64, _BYTE *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180034e80`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18001f0e0`
- `0x180025018`
- `0x180038970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f18e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f18e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2ac`
- `CRYPT32!CryptEncodeObjectEx` at `0x18001f349`
- `CRYPT32!CryptEncodeObjectEx` at `0x18001f493`
- `CRYPT32!CryptEncodeObjectEx` at `0x18001f349`
- `CRYPT32!CryptEncodeObjectEx` at `0x18001f493`
- `CRYPT32!CryptEncodeObject` at `0x18001f17a`
- `CRYPT32!CryptEncodeObject` at `0x18001f43f`
- `CRYPT32!CryptEncodeObject` at `0x18001f17a`
- `CRYPT32!CryptEncodeObject` at `0x18001f43f`

## string_xrefs

- `0x18001f202`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18001f24d`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18001f294`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18001f307`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`

## pseudocode

```c
__int64 __fastcall PkcsExportPlainTextKeyRsa(__int64 a1, _BYTE *a2, unsigned int a3, unsigned int *a4)
{
  char v4; // al
  __int64 v5; // r13
  void *v6; // rsi
  int v8; // ecx
  signed int LastError; // eax
  int v12; // edx
  unsigned int v13; // ebx
  __int64 v14; // rax
  _BYTE *v15; // rcx
  signed int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rax
  signed int v21; // eax
  __int64 v22; // r9
  __int64 v23; // rcx
  signed int v24; // eax
  int v25; // eax
  DWORD v26; // r15d
  unsigned int v27; // eax
  unsigned int v28; // ecx
  DWORD v29; // r14d
  unsigned int v30; // eax
  _DWORD *v31; // rdx
  unsigned int pvEncoded; // [rsp+28h] [rbp-50h]
  DWORD v33; // [rsp+40h] [rbp-38h] BYREF
  DWORD pcbEncoded; // [rsp+44h] [rbp-34h] BYREF
  unsigned int v35; // [rsp+48h] [rbp-30h] BYREF
  void *v36; // [rsp+50h] [rbp-28h] BYREF
  __int128 pvStructInfo; // [rsp+58h] [rbp-20h] BYREF
  __int64 v38; // [rsp+68h] [rbp-10h]
  __int16 v39; // [rsp+C0h] [rbp+48h] BYREF

  v4 = 0;
  v5 = a3;
  v6 = 0;
  v39 = 0;
  v36 = 0;
  v8 = *(_DWORD *)(a1 + 40);
  v35 = 0;
  v33 = 0;
  pcbEncoded = 0;
  v38 = 0;
  pvStructInfo = 0;
  if ( v8 != 0xFFFFFF )
  {
    LOBYTE(v39) = 0;
    if ( (v8 & 1) != 0 )
    {
      v4 = 16;
      LOBYTE(v39) = 16;
    }
    if ( (v8 & 2) != 0 )
    {
      v4 |= 0x80u;
      LOBYTE(v39) = v4;
    }
    if ( (v8 & 4) != 0 )
      LOBYTE(v39) = v4 | 8;
    LODWORD(pvStructInfo) = 1;
    LODWORD(v38) = 0;
    *((_QWORD *)&pvStructInfo + 1) = &v39;
    if ( !CryptEncodeObject(1u, (LPCSTR)0x1A, &pvStructInfo, 0, &pcbEncoded) )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v12,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
          (unsigned int)"status",
          v13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
          140);
LABEL_14:
      if ( !a2 )
        goto LABEL_15;
      goto LABEL_25;
    }
  }
  v25 = PkcsAllocAndExportKeyBlob(
          *(_QWORD *)(a1 + 112),
          a1,
          (__int64)L"RSAFULLPRIVATEBLOB",
          (__int64 *)&v36,
          &v35,
          pvEncoded);
  v13 = v25;
  if ( v25 < 0 )
  {
    DebugTraceError((unsigned int)v25, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 2204);
    v6 = v36;
    goto LABEL_14;
  }
  v6 = v36;
  if ( !CryptEncodeObjectEx(1u, (LPCSTR)0x53, v36, 0, 0, 0, &v33) )
  {
    v21 = GetLastError();
    v13 = v21;
    if ( v21 > 0 )
      v13 = (unsigned __int16)v21 | 0x80070000;
    v22 = 2219;
    v23 = v13;
    goto LABEL_31;
  }
  v26 = pcbEncoded;
  v27 = 77;
  if ( pcbEncoded )
    v27 = 143;
  v28 = v27 + pcbEncoded;
  if ( v27 + pcbEncoded < v27 || (v29 = v33, v30 = v28 + v33, v28 + v33 < v28) )
  {
    v13 = -2146893819;
    v22 = 2239;
    v23 = 2148073477LL;
LABEL_31:
    DebugTraceError(v23, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v22);
    goto LABEL_14;
  }
  *a4 = v30;
  if ( !a2 )
    goto LABEL_15;
  if ( (unsigned int)v5 < v30 )
  {
    v13 = -2146893784;
    v18 = 2252;
    v19 = 2148073512LL;
    goto LABEL_24;
  }
  memset_0(a2, 0, v30);
  v31 = a2 + 56;
  if ( !v26 )
    goto LABEL_48;
  *((_QWORD *)a2 + 6) = v31;
  *((_QWORD *)a2 + 8) = a2 + 72;
  *((_DWORD *)a2 + 20) = 1;
  *((_QWORD *)a2 + 9) = a2 + 112;
  *((_QWORD *)a2 + 11) = a2 + 96;
  *v31 = 1;
  *((_DWORD *)a2 + 24) = v26;
  *((_QWORD *)a2 + 13) = *((_QWORD *)a2 + 9) + 10LL;
  strcpy(*((char **)a2 + 9), "2.5.29.15");
  if ( CryptEncodeObject(1u, (LPCSTR)0x1A, &pvStructInfo, *((BYTE **)a2 + 13), (DWORD *)a2 + 24) )
  {
    v31 = (_DWORD *)(*((_QWORD *)a2 + 13) + *((unsigned int *)a2 + 24));
    v29 = v33;
LABEL_48:
    *((_QWORD *)a2 + 5) = v31;
    *((_QWORD *)a2 + 1) = (char *)v31 + v29;
    *((_DWORD *)a2 + 8) = v29;
    if ( CryptEncodeObjectEx(1u, (LPCSTR)0x53, v6, 0, 0, v31, (DWORD *)a2 + 8) )
    {
      strcpy(*((char **)a2 + 1), "1.2.840.113549.1.1.1");
      goto LABEL_15;
    }
    v17 = GetLastError();
    v13 = v17;
    if ( v17 > 0 )
      v13 = (unsigned __int16)v17 | 0x80070000;
    v18 = 2319;
    goto LABEL_23;
  }
  v24 = GetLastError();
  v13 = v24;
  if ( v24 > 0 )
    v13 = (unsigned __int16)v24 | 0x80070000;
  v18 = 2293;
LABEL_23:
  v19 = v13;
LABEL_24:
  DebugTraceError(v19, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v18);
LABEL_25:
  v20 = v5;
  if ( (_DWORD)v5 )
  {
    do
    {
      *a2++ = 0;
      --v20;
    }
    while ( v20 );
  }
LABEL_15:
  if ( v6 )
  {
    v14 = v35;
    v15 = v6;
    if ( v35 )
    {
      do
      {
        *v15++ = 0;
        --v14;
      }
      while ( v14 );
    }
    MSCryptFree(v6);
  }
  return v13;
}

```

## disassembly

```asm
0x18001f0e0  push    rbp
0x18001f0e2  push    rbx
0x18001f0e3  push    rsi
0x18001f0e4  push    rdi
0x18001f0e5  push    r12
0x18001f0e7  push    r13
0x18001f0e9  push    r14
0x18001f0eb  push    r15
0x18001f0ed  mov     rbp, rsp
0x18001f0f0  sub     rsp, 78h
0x18001f0f4  xor     eax, eax
0x18001f0f6  mov     r13d, r8d
0x18001f0f9  xor     esi, esi
0x18001f0fb  mov     [rbp+arg_0], ax
0x18001f0ff  mov     rbx, rcx
0x18001f102  mov     [rbp+var_28], rsi
0x18001f106  mov     ecx, [rcx+28h]
0x18001f109  xorps   xmm0, xmm0
0x18001f10c  mov     [rbp+var_30], eax
0x18001f10f  lea     r14d, [rax+1]
0x18001f113  mov     [rbp+var_38], eax
0x18001f116  mov     r12, r9
0x18001f119  mov     [rbp+var_34], eax
0x18001f11c  mov     rdi, rdx
0x18001f11f  mov     [rbp+var_10], rax
0x18001f123  movups  [rbp+pvStructInfo], xmm0
0x18001f127  cmp     ecx, 0FFFFFFh
0x18001f12d  jz      loc_18001F2DB
0x18001f133  mov     byte ptr [rbp+arg_0], al
0x18001f136  test    r14b, cl
0x18001f139  jz      short loc_18001F140
0x18001f13b  mov     al, 10h
0x18001f13d  mov     byte ptr [rbp+arg_0], al
0x18001f140  test    cl, 2
0x18001f143  jz      short loc_18001F14A
0x18001f145  or      al, 80h
0x18001f147  mov     byte ptr [rbp+arg_0], al
0x18001f14a  test    cl, 4
0x18001f14d  jz      short loc_18001F154
0x18001f14f  or      al, 8
0x18001f151  mov     byte ptr [rbp+arg_0], al
0x18001f154  xor     r9d, r9d; pbEncoded
0x18001f157  mov     dword ptr [rbp+pvStructInfo], r14d
0x18001f15b  lea     rax, [rbp+arg_0]
0x18001f15f  mov     dword ptr [rbp+var_10], esi
0x18001f162  mov     qword ptr [rbp+pvStructInfo+8], rax
0x18001f166  lea     r8, [rbp+pvStructInfo]; pvStructInfo
0x18001f16a  lea     rax, [rbp+var_34]
0x18001f16e  mov     ecx, r14d; dwCertEncodingType
0x18001f171  lea     edx, [r9+1Ah]; lpszStructType
0x18001f175  mov     [rsp+78h+pcbEncoded], rax; pcbEncoded
0x18001f17a  call    cs:__imp_CryptEncodeObject
0x18001f181  nop     dword ptr [rax+rax+00h]
0x18001f186  test    eax, eax
0x18001f188  jnz     loc_18001F2DB
0x18001f18e  call    cs:__imp_GetLastError
0x18001f195  nop     dword ptr [rax+rax+00h]
0x18001f19a  mov     ebx, eax
0x18001f19c  test    eax, eax
0x18001f19e  jg      loc_18001F2CD
0x18001f1a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1ab  lea     rax, WPP_GLOBAL_Control
0x18001f1b2  cmp     rcx, rax
0x18001f1b5  jz      short loc_18001F1BD
0x18001f1b7  test    [rcx+1Ch], r14b
0x18001f1bb  jnz     short loc_18001F1FE
0x18001f1bd  test    rdi, rdi
0x18001f1c0  jnz     loc_18001F259
0x18001f1c6  test    rsi, rsi
0x18001f1c9  jz      short loc_18001F1EA
0x18001f1cb  mov     eax, [rbp+var_30]
0x18001f1ce  mov     rcx, rsi
0x18001f1d1  test    rax, rax
0x18001f1d4  jz      short loc_18001F1E2
0x18001f1d6  mov     byte ptr [rcx], 0
0x18001f1d9  inc     rcx
0x18001f1dc  sub     rax, 1
0x18001f1e0  jnz     short loc_18001F1D6
0x18001f1e2  mov     rcx, rsi
0x18001f1e5  call    MSCryptFree
0x18001f1ea  mov     eax, ebx
0x18001f1ec  add     rsp, 78h
0x18001f1f0  pop     r15
0x18001f1f2  pop     r14
0x18001f1f4  pop     r13
0x18001f1f6  pop     r12
0x18001f1f8  pop     rdi
0x18001f1f9  pop     rsi
0x18001f1fa  pop     rbx
0x18001f1fb  pop     rbp
0x18001f1fc  retn
0x18001f1fe  mov     rcx, [rcx+10h]
0x18001f202  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001f209  mov     dword ptr [rsp+78h+var_48], 88Ch
0x18001f211  lea     r9, aStatus_0; "status"
0x18001f218  mov     [rsp+78h+pvEncoded], r8
0x18001f21d  mov     dword ptr [rsp+78h+pcbEncoded], ebx
0x18001f221  call    WPP_SF_sDsd
0x18001f226  jmp     short loc_18001F1BD
0x18001f228  call    cs:__imp_GetLastError
0x18001f22f  nop     dword ptr [rax+rax+00h]
0x18001f234  mov     ebx, eax
0x18001f236  test    eax, eax
0x18001f238  jg      loc_18001F4D5
0x18001f23e  mov     r9d, 90Fh
0x18001f244  mov     ecx, ebx
0x18001f246  lea     rdx, aStatus_0; "status"
0x18001f24d  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001f254  call    DebugTraceError
0x18001f259  mov     rax, r13
0x18001f25c  test    r13d, r13d
0x18001f25f  jz      loc_18001F1C6
0x18001f265  mov     byte ptr [rdi], 0
0x18001f268  inc     rdi
0x18001f26b  sub     rax, 1
0x18001f26f  jnz     short loc_18001F265
0x18001f271  jmp     loc_18001F1C6
0x18001f276  call    cs:__imp_GetLastError
0x18001f27d  nop     dword ptr [rax+rax+00h]
0x18001f282  mov     ebx, eax
0x18001f284  test    eax, eax
0x18001f286  jg      loc_18001F3B2
0x18001f28c  mov     r9d, 8ABh
0x18001f292  mov     ecx, ebx
0x18001f294  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001f29b  lea     rdx, aStatus_0; "status"
0x18001f2a2  call    DebugTraceError
0x18001f2a7  jmp     loc_18001F1BD
0x18001f2ac  call    cs:__imp_GetLastError
0x18001f2b3  nop     dword ptr [rax+rax+00h]
0x18001f2b8  mov     ebx, eax
0x18001f2ba  test    eax, eax
0x18001f2bc  jg      loc_18001F4C7
0x18001f2c2  mov     r9d, 8F5h
0x18001f2c8  jmp     loc_18001F244
0x18001f2cd  movzx   ebx, ax
0x18001f2d0  or      ebx, 80070000h
0x18001f2d6  jmp     loc_18001F1A4
0x18001f2db  mov     rcx, [rbx+70h]
0x18001f2df  lea     rax, [rbp+var_30]
0x18001f2e3  lea     r9, [rbp+var_28]
0x18001f2e7  mov     [rsp+78h+pcbEncoded], rax
0x18001f2ec  lea     r8, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x18001f2f3  mov     rdx, rbx
0x18001f2f6  call    _PkcsAllocAndExportKeyBlob
0x18001f2fb  mov     ebx, eax
0x18001f2fd  test    eax, eax
0x18001f2ff  jns     short loc_18001F325
0x18001f301  mov     r9d, 89Ch
0x18001f307  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001f30e  lea     rdx, aStatus_0; "status"
0x18001f315  mov     ecx, eax
0x18001f317  call    DebugTraceError
0x18001f31c  mov     rsi, [rbp+var_28]
0x18001f320  jmp     loc_18001F1BD
0x18001f325  lea     rax, [rbp+var_38]
0x18001f329  xor     r9d, r9d; dwFlags
0x18001f32c  mov     [rsp+78h+var_48], rax; pcbEncoded
0x18001f331  mov     ecx, r14d; dwCertEncodingType
0x18001f334  mov     [rsp+78h+pvEncoded], rsi; pvEncoded
0x18001f339  mov     [rsp+78h+pcbEncoded], rsi; pEncodePara
0x18001f33e  mov     rsi, [rbp+var_28]
0x18001f342  lea     edx, [r9+53h]; lpszStructType
0x18001f346  mov     r8, rsi; pvStructInfo
0x18001f349  call    cs:__imp_CryptEncodeObjectEx
0x18001f350  nop     dword ptr [rax+rax+00h]
0x18001f355  test    eax, eax
0x18001f357  jz      loc_18001F276
0x18001f35d  mov     r15d, [rbp+var_34]
0x18001f361  mov     eax, 4Dh ; 'M'
0x18001f366  test    r15d, r15d
0x18001f369  lea     ecx, [rax+42h]
0x18001f36c  cmovnz  eax, ecx
0x18001f36f  lea     ecx, [rax+r15]
0x18001f373  cmp     ecx, eax
0x18001f375  jb      loc_18001F4E3
0x18001f37b  mov     r14d, [rbp+var_38]
0x18001f37f  lea     eax, [rcx+r14]
0x18001f383  cmp     eax, ecx
0x18001f385  jb      loc_18001F4E3
0x18001f38b  mov     [r12], eax
0x18001f38f  test    rdi, rdi
0x18001f392  jz      loc_18001F1C6
0x18001f398  cmp     r13d, eax
0x18001f39b  jnb     short loc_18001F3C0
0x18001f39d  mov     ebx, 80090028h
0x18001f3a2  mov     r9d, 8CCh
0x18001f3a8  mov     ecx, 80090028h
0x18001f3ad  jmp     loc_18001F246
0x18001f3b2  movzx   ebx, ax
0x18001f3b5  or      ebx, 80070000h
0x18001f3bb  jmp     loc_18001F28C
0x18001f3c0  mov     r8d, eax; Size
0x18001f3c3  xor     edx, edx; Val
0x18001f3c5  mov     rcx, rdi; void *
0x18001f3c8  call    memset_0
0x18001f3cd  lea     rdx, [rdi+38h]
0x18001f3d1  test    r15d, r15d
0x18001f3d4  jz      loc_18001F45E
0x18001f3da  lea     rcx, [rdx+10h]
0x18001f3de  mov     [rdi+30h], rdx
0x18001f3e2  mov     [rdx+8], rcx
0x18001f3e6  lea     r14, [rcx+18h]
0x18001f3ea  mov     dword ptr [rcx+8], 1
0x18001f3f1  lea     rax, [r14+10h]
0x18001f3f5  mov     [rcx], rax
0x18001f3f8  lea     r8, [rbp+pvStructInfo]; pvStructInfo
0x18001f3fc  mov     [rcx+10h], r14
0x18001f400  mov     dword ptr [rdx], 1
0x18001f406  mov     edx, 1Ah; lpszStructType
0x18001f40b  mov     [r14], r15d
0x18001f40e  mov     rax, [rcx]
0x18001f411  add     rax, 0Ah
0x18001f415  mov     [rsp+78h+pcbEncoded], r14; pcbEncoded
0x18001f41a  mov     [r14+8], rax
0x18001f41e  mov     rcx, [rcx]
0x18001f421  movsd   xmm0, qword ptr cs:Str2; "2.5.29.15"
0x18001f429  movsd   qword ptr [rcx], xmm0
0x18001f42d  movzx   eax, word ptr cs:Str2+8; "5"
0x18001f434  mov     [rcx+8], ax
0x18001f438  lea     ecx, [rdx-19h]; dwCertEncodingType
0x18001f43b  mov     r9, [r14+8]; pbEncoded
0x18001f43f  call    cs:__imp_CryptEncodeObject
0x18001f446  nop     dword ptr [rax+rax+00h]
0x18001f44b  test    eax, eax
0x18001f44d  jz      loc_18001F2AC
0x18001f453  mov     edx, [r14]
0x18001f456  add     rdx, [r14+8]
0x18001f45a  mov     r14d, [rbp+var_38]
0x18001f45e  xor     r9d, r9d; dwFlags
0x18001f461  mov     [rdi+28h], rdx
0x18001f465  mov     eax, r14d
0x18001f468  mov     r8, rsi; pvStructInfo
0x18001f46b  add     rax, rdx
0x18001f46e  mov     [rdi+8], rax
0x18001f472  lea     rax, [rdi+20h]
0x18001f476  mov     [rsp+78h+var_48], rax; pcbEncoded
0x18001f47b  mov     [rsp+78h+pvEncoded], rdx; pvEncoded
0x18001f480  lea     edx, [r9+53h]; lpszStructType
0x18001f484  lea     ecx, [rdx-52h]; dwCertEncodingType
0x18001f487  mov     [rax], r14d
0x18001f48a  mov     [rsp+78h+pcbEncoded], 0; pEncodePara
0x18001f493  call    cs:__imp_CryptEncodeObjectEx
0x18001f49a  nop     dword ptr [rax+rax+00h]
0x18001f49f  test    eax, eax
0x18001f4a1  jz      loc_18001F228
0x18001f4a7  mov     rax, [rdi+8]
0x18001f4ab  movups  xmm0, xmmword ptr cs:a12840113549111; "1.2.840.113549.1.1.1"
0x18001f4b2  movups  xmmword ptr [rax], xmm0
0x18001f4b5  movsd   xmm1, qword ptr cs:a12840113549111+0Dh; "9.1.1.1"
0x18001f4bd  movsd   qword ptr [rax+0Dh], xmm1
0x18001f4c2  jmp     loc_18001F1C6
0x18001f4c7  movzx   ebx, ax
0x18001f4ca  or      ebx, 80070000h
0x18001f4d0  jmp     loc_18001F2C2
0x18001f4d5  movzx   ebx, ax
0x18001f4d8  or      ebx, 80070000h
0x18001f4de  jmp     loc_18001F23E
0x18001f4e3  mov     ebx, 80090005h
0x18001f4e8  mov     r9d, 8BFh
0x18001f4ee  mov     ecx, 80090005h
0x18001f4f3  jmp     loc_18001F294
```
