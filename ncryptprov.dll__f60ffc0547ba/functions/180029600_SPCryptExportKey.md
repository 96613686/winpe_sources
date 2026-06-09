# SPCryptExportKey

- ea: `0x180029600`
- end: `0x18002a0b1`
- name: `SPCryptExportKey`
- size: `2737`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const wchar_t *, __int64, UCHAR *pbOutput, ULONG cbOutput, ULONG *pcbResult, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004400`
- `0x18000af80`
- `0x18000afd0`
- `0x180013d2c`
- `0x180014160`
- `0x180017a80`
- `0x180021120`
- `0x180027f18`
- `0x180029600`
- `0x180047efc`
- `0x180049cf8`
- `0x18005a688`
- `0x18005aca0`
- `0x18005b818`
- `0x1800622e0`
- `0x180063010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180029a3b`
- `ntdll!RtlReleaseResource` at `0x18002a091`
- `ntdll!RtlReleaseResource` at `0x180029a3b`
- `ntdll!RtlReleaseResource` at `0x18002a091`
- `ntdll!RtlAcquireResourceShared` at `0x180029a08`
- `ntdll!RtlAcquireResourceShared` at `0x180029a08`
- `bcrypt!BCryptExportKey` at `0x180029ddb`
- `bcrypt!BCryptExportKey` at `0x180029ddb`

## string_xrefs

- `0x18002964b`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180029865`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180029c0a`: `COMPMLKEMPUBLICBLOB`
- `0x180029be4`: `COMPMLKEMPRIVATELAMPSBLOB`
- `0x180029bf7`: `COMPMLKEMPRIVATEIRTFSEEDBLOB`

## pseudocode

```c
__int64 __fastcall SPCryptExportKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        __int64 a5,
        UCHAR *pbOutput,
        ULONG cbOutput,
        ULONG *pcbResult,
        unsigned int a9)
{
  __int64 v12; // r14
  __int64 v13; // rsi
  __int64 v14; // r9
  unsigned int v15; // edi
  __int64 v16; // rcx
  int v17; // edx
  __int64 v18; // rax
  int v19; // ebx
  int v20; // r14d
  int v21; // r12d
  __int64 v22; // r9
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  __int64 v27; // [rsp+40h] [rbp-78h]
  int v28; // [rsp+48h] [rbp-70h] BYREF
  int v29; // [rsp+4Ch] [rbp-6Ch]
  int v30; // [rsp+50h] [rbp-68h]
  int v31; // [rsp+54h] [rbp-64h]
  int v32; // [rsp+58h] [rbp-60h]
  int v33; // [rsp+5Ch] [rbp-5Ch]
  int v34; // [rsp+60h] [rbp-58h]
  __int64 v35; // [rsp+68h] [rbp-50h]
  int v36; // [rsp+C0h] [rbp+8h]

  v36 = a1;
  v27 = KspValidateAndLockProvider(a1, 0);
  v12 = v27;
  if ( !v27 )
  {
    LODWORD(v13) = 0;
    v14 = 5348;
LABEL_3:
    v15 = -2146893786;
    v16 = 2148073510LL;
LABEL_4:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v14);
    goto LABEL_148;
  }
  v18 = KspValidateKeyHandle(a2);
  v13 = v18;
  if ( !v18 )
  {
    v14 = 5357;
    goto LABEL_3;
  }
  if ( !pcbResult )
  {
    v15 = -2146893785;
    v14 = 5364;
    v16 = 2148073511LL;
    goto LABEL_4;
  }
  if ( !*(_DWORD *)(v18 + 44) )
  {
    v15 = -2146893813;
    v14 = 5371;
    v16 = 2148073483LL;
    goto LABEL_4;
  }
  if ( (a9 & 0xFFFFF7BF) != 0 )
  {
    v15 = -2146893815;
    v14 = 5378;
    v16 = 2148073481LL;
    goto LABEL_4;
  }
  v35 = 0;
  if ( a3 )
  {
    v35 = KspValidateKeyHandle(a3);
    if ( !v35 )
    {
      v14 = 5388;
      goto LABEL_3;
    }
  }
  v19 = 0;
  v30 = 0;
  v29 = 0;
  v31 = 0;
  v32 = 0;
  v20 = 0;
  v33 = 0;
  v28 = 0;
  v34 = 0;
  if ( !wcscmp_0(a4, L"PUBLICBLOB") )
  {
LABEL_85:
    v21 = 1;
    goto LABEL_111;
  }
  v21 = 0;
  if ( !wcscmp_0(a4, L"PRIVATEBLOB") || !wcscmp_0(a4, L"KeyDataBlob") )
    goto LABEL_89;
  if ( !wcscmp_0(a4, L"RSAPUBLICBLOB") || !wcscmp_0(a4, L"CAPIPUBLICBLOB") )
  {
    if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) != 196609 )
    {
      v22 = 5412;
      goto LABEL_31;
    }
    goto LABEL_85;
  }
  if ( !wcscmp_0(a4, L"DSAPUBLICBLOB") || !wcscmp_0(a4, L"CAPIDSAPUBLICBLOB") || !wcscmp_0(a4, L"V2CAPIDSAPUBLICBLOB") )
  {
    if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) != 196611 )
    {
      v22 = 5425;
      goto LABEL_31;
    }
    goto LABEL_85;
  }
  if ( !wcscmp_0(a4, L"DHPUBLICBLOB") || !wcscmp_0(a4, L"CAPIDHPUBLICBLOB") )
  {
    if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) != 196610 )
    {
      v22 = 5437;
      goto LABEL_31;
    }
    goto LABEL_85;
  }
  if ( !wcscmp_0(a4, L"ECCPUBLICBLOB") || !wcscmp_0(a4, L"ECCFULLPUBLICBLOB") )
  {
    if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) - 196612) > 7 )
    {
      v22 = 5456;
      goto LABEL_31;
    }
    goto LABEL_85;
  }
  if ( wcscmp_0(a4, L"CipherKeyBlob") )
  {
    if ( !wcscmp_0(a4, L"KDFKeyBlob") )
    {
      if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 8LL) != 7 )
      {
        v22 = 5479;
        goto LABEL_31;
      }
      v20 = 1;
      v28 = 1;
      goto LABEL_111;
    }
    if ( !wcscmp_0(a4, L"RSAPRIVATEBLOB") || !wcscmp_0(a4, L"RSAFULLPRIVATEBLOB") || !wcscmp_0(a4, L"CAPIPRIVATEBLOB") )
    {
      if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) != 196609 )
      {
        v22 = 5493;
        goto LABEL_31;
      }
    }
    else if ( !wcscmp_0(a4, L"DSAPRIVATEBLOB")
           || !wcscmp_0(a4, L"CAPIDSAPRIVATEBLOB")
           || !wcscmp_0(a4, L"V2CAPIDSAPRIVATEBLOB") )
    {
      if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) != 196611 )
      {
        v22 = 5506;
        goto LABEL_31;
      }
    }
    else if ( !wcscmp_0(a4, L"DHPRIVATEBLOB") || !wcscmp_0(a4, L"CAPIDHPRIVATEBLOB") )
    {
      if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) != 196610 )
      {
        v22 = 5518;
        goto LABEL_31;
      }
    }
    else if ( !wcscmp_0(a4, L"ECCPRIVATEBLOB") || !wcscmp_0(a4, L"ECCFULLPRIVATEBLOB") )
    {
      if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) - 196612) > 7 )
      {
        v22 = 5537;
        goto LABEL_31;
      }
    }
    else
    {
      if ( !wcscmp_0(a4, L"OpaqueTransport") )
      {
        if ( *(_DWORD *)(v13 + 144) )
        {
          v22 = 5553;
LABEL_51:
          v15 = -2146893783;
          v23 = 2148073513LL;
          goto LABEL_32;
        }
        if ( (*(_DWORD *)(v13 + 428) & 0x20) != 0 )
        {
          v22 = 5561;
LABEL_54:
          v15 = -2146893808;
          v23 = 2148073488LL;
          goto LABEL_32;
        }
        RtlAcquireResourceShared((PRTL_RESOURCE)(v13 + 304), 1u);
        v15 = KspExportOpaqueBlob(v27, v13, (_DWORD)pbOutput, cbOutput, (__int64)pcbResult);
        RtlReleaseResource((PRTL_RESOURCE)(v13 + 304));
        if ( v15 )
        {
          v22 = 5578;
          v23 = v15;
          goto LABEL_32;
        }
        v19 = 0;
LABEL_111:
        if ( (a9 & 0x800) != 0 && !v19 )
        {
          v15 = -2146893815;
          v22 = 5689;
          v23 = 2148073481LL;
          goto LABEL_32;
        }
        if ( v21 )
        {
          v25 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)(v13 + 104), 0, a4, pbOutput, cbOutput, pcbResult, 0);
          v15 = v25;
          if ( v25 )
          {
            v22 = 5707;
LABEL_117:
            v23 = (unsigned int)v25;
            goto LABEL_32;
          }
        }
        if ( v20 )
        {
          if ( (*(_DWORD *)(v13 + 428) & 0x20) != 0 )
          {
            v22 = 5718;
            goto LABEL_54;
          }
          if ( !v29
            && !v30
            && (*(_BYTE *)(v13 + 36) & 2) == 0
            && (!v31 || !(unsigned int)SPPkcs8IsKeyExportable(v13, a5))
            && (!v32 || (*(_BYTE *)(v13 + 36) & 0x13) == 0) )
          {
            v22 = 5730;
            goto LABEL_51;
          }
          v25 = KspCheckStrongKeyAndUnprotect(v13, a9);
          v15 = v25;
          if ( v25 < 0 )
          {
            v22 = 5744;
            goto LABEL_117;
          }
          if ( v33 || v28 )
          {
            v25 = KspExportCipherOrKDFBlob(v13, (_DWORD)pbOutput, cbOutput, (_DWORD)pcbResult, a9);
            v15 = v25;
            if ( v25 )
            {
              v22 = 5759;
              goto LABEL_117;
            }
          }
          else if ( v30 )
          {
            v25 = KspExportProtectedBlob(v13, a5, (_DWORD)pbOutput, cbOutput, (__int64)pcbResult, a9);
            v15 = v25;
            if ( v25 )
            {
              v22 = 5775;
              goto LABEL_117;
            }
          }
          else if ( v29 )
          {
            v25 = KspExportPKCS7Blob(v13, a5, pbOutput, cbOutput, pcbResult, a9 & 0x800);
            v15 = v25;
            if ( v25 )
            {
              v22 = 5790;
              goto LABEL_117;
            }
          }
          else if ( v31 )
          {
            v25 = SPPkcs8ExportKey(v13, a5, pbOutput, cbOutput, pcbResult, a9);
            v15 = v25;
            if ( v25 )
            {
              v22 = 5805;
              goto LABEL_117;
            }
          }
          else if ( v32 )
          {
            v28 = cbOutput;
            v25 = SPPkcs11ExportKey(v36, v35, v13, a5, (__int64)pbOutput, (__int64)&v28, a9);
            v15 = v25;
            if ( v25 )
            {
              v22 = 5823;
              goto LABEL_117;
            }
            *pcbResult = v28;
          }
          else if ( v34 )
          {
            v25 = ExportPqPrivateKey(v13, pbOutput, cbOutput, pcbResult);
            v15 = v25;
            if ( v25 )
            {
              v22 = 5838;
              goto LABEL_117;
            }
          }
          else
          {
            v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, UCHAR *, ULONG, ULONG *, _DWORD))(*(_QWORD *)(v13 + 168) + 120LL))(
                    *(_QWORD *)(v13 + 112),
                    0,
                    a4,
                    pbOutput,
                    cbOutput,
                    pcbResult,
                    0);
            v15 = v25;
            if ( v25 )
            {
              v22 = 5855;
              goto LABEL_117;
            }
          }
        }
        v15 = 0;
        goto LABEL_147;
      }
      if ( !wcscmp_0(a4, L"ProtectedKeyBlob") )
      {
        v20 = 1;
        v30 = 1;
        goto LABEL_111;
      }
      if ( !wcscmp_0(a4, L"PKCS7_ENVELOPE") )
      {
        v20 = 1;
        v29 = 1;
        v19 = 1;
        goto LABEL_111;
      }
      if ( !wcscmp_0(a4, L"PKCS8_PRIVATEKEY") )
      {
        v20 = 1;
        v31 = 1;
        goto LABEL_111;
      }
      if ( !wcscmp_0(a4, L"PKCS11RsaAesWrapBlob") )
      {
        v20 = 1;
        v32 = 1;
        goto LABEL_111;
      }
      if ( !wcscmp_0(a4, L"PQDSAPRIVATEBLOB") || !wcscmp_0(a4, L"PQDSAPRIVATESEEDBLOB") )
      {
        if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) != 196620 )
        {
          v22 = 5608;
          goto LABEL_31;
        }
      }
      else
      {
        if ( !wcscmp_0(a4, L"PQDSAPUBLICBLOB") )
        {
          if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) != 196620 )
          {
            v22 = 5618;
            goto LABEL_31;
          }
          goto LABEL_85;
        }
        if ( !wcscmp_0(a4, L"PQPrivateKeyBlob") )
        {
          v24 = *(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL);
          if ( v24 != 196620 && (unsigned int)(v24 - 458753) > 1 )
          {
            v22 = 5630;
            goto LABEL_31;
          }
          v20 = 1;
          v34 = 1;
          goto LABEL_111;
        }
        if ( !wcscmp_0(a4, L"MLKEMPRIVATEBLOB") || !wcscmp_0(a4, L"MLKEMPRIVATESEEDBLOB") )
        {
          if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) != 458753 )
          {
            v22 = 5643;
            goto LABEL_31;
          }
        }
        else
        {
          if ( !wcscmp_0(a4, L"MLKEMPUBLICBLOB") )
          {
            if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) != 458753 )
            {
              v22 = 5653;
              goto LABEL_31;
            }
            goto LABEL_85;
          }
          if ( wcscmp_0(a4, L"COMPMLKEMPRIVATELAMPSBLOB") && wcscmp_0(a4, L"COMPMLKEMPRIVATEIRTFSEEDBLOB") )
          {
            if ( wcscmp_0(a4, L"COMPMLKEMPUBLICBLOB") )
            {
              v15 = -2146893785;
              v22 = 5682;
              v23 = 2148073511LL;
              goto LABEL_32;
            }
            if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) != 458754 )
            {
              v22 = 5674;
              goto LABEL_31;
            }
            goto LABEL_85;
          }
          if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 32LL) != 458754 )
          {
            v22 = 5664;
            goto LABEL_31;
          }
        }
      }
    }
LABEL_89:
    v20 = 1;
    goto LABEL_111;
  }
  if ( *(_DWORD *)(*(_QWORD *)(v13 + 64) + 8LL) == 1 )
  {
    v20 = 1;
    v33 = 1;
    goto LABEL_111;
  }
  v22 = 5467;
LABEL_31:
  v15 = -2146893814;
  v23 = 2148073482LL;
LABEL_32:
  DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v22);
LABEL_147:
  v12 = v27;
LABEL_148:
  if ( pbOutput )
  {
    if ( v15 )
    {
      if ( v15 != -2146893778 )
        KspCryptAuditKeyMigrationOperation(0, v17, v13, 2464, v15);
    }
    else
    {
      KspCryptAuditKeyMigrationOperation(1, v17, v13, 2464, 0);
    }
  }
  if ( v12 )
    RtlReleaseResource((PRTL_RESOURCE)(v12 + 64));
  return v15;
}

```

## disassembly

```asm
0x180029600  mov     [rsp+arg_0], rcx
0x180029605  push    rbx
0x180029606  push    rbp
0x180029607  push    rsi
0x180029608  push    rdi
0x180029609  push    r12
0x18002960b  push    r13
0x18002960d  push    r14
0x18002960f  push    r15
0x180029611  sub     rsp, 78h
0x180029615  mov     rdi, rdx
0x180029618  mov     rbp, r9
0x18002961b  xor     edx, edx
0x18002961d  mov     rbx, r8
0x180029620  call    KspValidateAndLockProvider
0x180029625  mov     [rsp+0B8h+var_78], rax
0x18002962a  mov     r14, rax
0x18002962d  test    rax, rax
0x180029630  jnz     short loc_18002965C
0x180029632  xor     esi, esi
0x180029634  mov     r9d, 14E4h
0x18002963a  mov     edi, 80090026h
0x18002963f  mov     ecx, 80090026h
0x180029644  lea     rdx, aStatus; "Status"
0x18002964b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180029652  call    DebugTraceError
0x180029657  jmp     loc_180029FA8
0x18002965c  mov     rcx, rdi
0x18002965f  call    KspValidateKeyHandle
0x180029664  mov     rsi, rax
0x180029667  test    rax, rax
0x18002966a  jnz     short loc_180029674
0x18002966c  mov     r9d, 14EDh
0x180029672  jmp     short loc_18002963A
0x180029674  mov     r13, [rsp+0B8h+arg_38]
0x18002967c  test    r13, r13
0x18002967f  jnz     short loc_180029693
0x180029681  mov     edi, 80090027h
0x180029686  mov     r9d, 14F4h
0x18002968c  mov     ecx, 80090027h
0x180029691  jmp     short loc_180029644
0x180029693  cmp     dword ptr [rax+2Ch], 0
0x180029697  jnz     short loc_1800296AB
0x180029699  mov     edi, 8009000Bh
0x18002969e  mov     r9d, 14FBh
0x1800296a4  mov     ecx, 8009000Bh
0x1800296a9  jmp     short loc_180029644
0x1800296ab  mov     r15d, [rsp+0B8h+arg_40]
0x1800296b3  test    r15d, 0FFFFF7BFh
0x1800296ba  jz      short loc_1800296D1
0x1800296bc  mov     edi, 80090009h
0x1800296c1  mov     r9d, 1502h
0x1800296c7  mov     ecx, 80090009h
0x1800296cc  jmp     loc_180029644
0x1800296d1  mov     [rsp+0B8h+var_50], 0
0x1800296da  test    rbx, rbx
0x1800296dd  jz      short loc_1800296FC
0x1800296df  mov     rcx, rbx
0x1800296e2  call    KspValidateKeyHandle
0x1800296e7  mov     [rsp+0B8h+var_50], rax
0x1800296ec  test    rax, rax
0x1800296ef  jnz     short loc_1800296FC
0x1800296f1  mov     r9d, 150Ch
0x1800296f7  jmp     loc_18002963A
0x1800296fc  xor     ebx, ebx
0x1800296fe  mov     [rsp+0B8h+var_68], 0
0x180029706  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18002970d  mov     [rsp+0B8h+var_6C], ebx
0x180029711  mov     rcx, rbp; String1
0x180029714  mov     [rsp+0B8h+var_64], ebx
0x180029718  mov     [rsp+0B8h+var_60], ebx
0x18002971c  xor     r14d, r14d
0x18002971f  mov     [rsp+0B8h+var_5C], ebx
0x180029723  mov     [rsp+0B8h+var_70], ebx
0x180029727  mov     [rsp+0B8h+var_58], ebx
0x18002972b  call    wcscmp_0
0x180029730  test    eax, eax
0x180029732  jz      loc_180029C35
0x180029738  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x18002973f  mov     rcx, rbp; String1
0x180029742  xor     r12d, r12d
0x180029745  call    wcscmp_0
0x18002974a  test    eax, eax
0x18002974c  jz      loc_180029C6D
0x180029752  lea     rdx, aKeydatablob; "KeyDataBlob"
0x180029759  mov     rcx, rbp; String1
0x18002975c  call    wcscmp_0
0x180029761  test    eax, eax
0x180029763  jz      loc_180029C6D
0x180029769  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x180029770  mov     rcx, rbp; String1
0x180029773  call    wcscmp_0
0x180029778  test    eax, eax
0x18002977a  jz      loc_180029D6A
0x180029780  lea     rdx, aCapipublicblob; "CAPIPUBLICBLOB"
0x180029787  mov     rcx, rbp; String1
0x18002978a  call    wcscmp_0
0x18002978f  test    eax, eax
0x180029791  jz      loc_180029D6A
0x180029797  lea     rdx, aDsapublicblob; "DSAPUBLICBLOB"
0x18002979e  mov     rcx, rbp; String1
0x1800297a1  call    wcscmp_0
0x1800297a6  test    eax, eax
0x1800297a8  jz      loc_180029D4E
0x1800297ae  lea     rdx, aCapidsapublicb; "CAPIDSAPUBLICBLOB"
0x1800297b5  mov     rcx, rbp; String1
0x1800297b8  call    wcscmp_0
0x1800297bd  test    eax, eax
0x1800297bf  jz      loc_180029D4E
0x1800297c5  lea     rdx, aV2capidsapubli; "V2CAPIDSAPUBLICBLOB"
0x1800297cc  mov     rcx, rbp; String1
0x1800297cf  call    wcscmp_0
0x1800297d4  test    eax, eax
0x1800297d6  jz      loc_180029D4E
0x1800297dc  lea     rdx, aDhpublicblob; "DHPUBLICBLOB"
0x1800297e3  mov     rcx, rbp; String1
0x1800297e6  call    wcscmp_0
0x1800297eb  test    eax, eax
0x1800297ed  jz      loc_180029D32
0x1800297f3  lea     rdx, aCapidhpublicbl; "CAPIDHPUBLICBLOB"
0x1800297fa  mov     rcx, rbp; String1
0x1800297fd  call    wcscmp_0
0x180029802  test    eax, eax
0x180029804  jz      loc_180029D32
0x18002980a  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x180029811  mov     rcx, rbp; String1
0x180029814  call    wcscmp_0
0x180029819  test    eax, eax
0x18002981b  jz      loc_180029D11
0x180029821  lea     rdx, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x180029828  mov     rcx, rbp; String1
0x18002982b  call    wcscmp_0
0x180029830  test    eax, eax
0x180029832  jz      loc_180029D11
0x180029838  lea     rdx, aCipherkeyblob; "CipherKeyBlob"
0x18002983f  mov     rcx, rbp; String1
0x180029842  call    wcscmp_0
0x180029847  test    eax, eax
0x180029849  jnz     short loc_18002988D
0x18002984b  mov     rax, [rsi+40h]
0x18002984f  cmp     dword ptr [rax+8], 1
0x180029853  jz      short loc_18002987D
0x180029855  mov     r9d, 155Bh
0x18002985b  mov     edi, 8009000Ah
0x180029860  mov     ecx, 8009000Ah
0x180029865  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002986c  lea     rdx, aStatus; "Status"
0x180029873  call    DebugTraceError
0x180029878  jmp     loc_180029FA3
0x18002987d  mov     r14d, 1
0x180029883  mov     [rsp+0B8h+var_5C], r14d
0x180029888  jmp     loc_180029D89
0x18002988d  lea     rdx, aKdfkeyblob; "KDFKeyBlob"
0x180029894  mov     rcx, rbp; String1
0x180029897  call    wcscmp_0
0x18002989c  test    eax, eax
0x18002989e  jnz     short loc_1800298C3
0x1800298a0  mov     rax, [rsi+40h]
0x1800298a4  cmp     dword ptr [rax+8], 7
0x1800298a8  jz      short loc_1800298B2
0x1800298aa  mov     r9d, 1567h
0x1800298b0  jmp     short loc_18002985B
0x1800298b2  mov     eax, 1
0x1800298b7  mov     r14d, eax
0x1800298ba  mov     [rsp+0B8h+var_70], eax
0x1800298be  jmp     loc_180029D89
0x1800298c3  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x1800298ca  mov     rcx, rbp; String1
0x1800298cd  call    wcscmp_0
0x1800298d2  test    eax, eax
0x1800298d4  jz      loc_180029CF5
0x1800298da  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x1800298e1  mov     rcx, rbp; String1
0x1800298e4  call    wcscmp_0
0x1800298e9  test    eax, eax
0x1800298eb  jz      loc_180029CF5
0x1800298f1  lea     rdx, aCapiprivateblo; "CAPIPRIVATEBLOB"
0x1800298f8  mov     rcx, rbp; String1
0x1800298fb  call    wcscmp_0
0x180029900  test    eax, eax
0x180029902  jz      loc_180029CF5
0x180029908  lea     rdx, aDsaprivateblob; "DSAPRIVATEBLOB"
0x18002990f  mov     rcx, rbp; String1
0x180029912  call    wcscmp_0
0x180029917  test    eax, eax
0x180029919  jz      loc_180029CDD
0x18002991f  lea     rdx, aCapidsaprivate; "CAPIDSAPRIVATEBLOB"
0x180029926  mov     rcx, rbp; String1
0x180029929  call    wcscmp_0
0x18002992e  test    eax, eax
0x180029930  jz      loc_180029CDD
0x180029936  lea     rdx, aV2capidsapriva; "V2CAPIDSAPRIVATEBLOB"
0x18002993d  mov     rcx, rbp; String1
0x180029940  call    wcscmp_0
0x180029945  test    eax, eax
0x180029947  jz      loc_180029CDD
0x18002994d  lea     rdx, aDhprivateblob; "DHPRIVATEBLOB"
0x180029954  mov     rcx, rbp; String1
0x180029957  call    wcscmp_0
0x18002995c  test    eax, eax
0x18002995e  jz      loc_180029CC5
0x180029964  lea     rdx, aCapidhprivateb; "CAPIDHPRIVATEBLOB"
0x18002996b  mov     rcx, rbp; String1
0x18002996e  call    wcscmp_0
0x180029973  test    eax, eax
0x180029975  jz      loc_180029CC5
0x18002997b  lea     rdx, aEccprivateblob; "ECCPRIVATEBLOB"
0x180029982  mov     rcx, rbp; String1
0x180029985  call    wcscmp_0
0x18002998a  test    eax, eax
0x18002998c  jz      loc_180029CA8
0x180029992  lea     rdx, aEccfullprivate; "ECCFULLPRIVATEBLOB"
0x180029999  mov     rcx, rbp; String1
0x18002999c  call    wcscmp_0
0x1800299a1  test    eax, eax
0x1800299a3  jz      loc_180029CA8
0x1800299a9  lea     rdx, aOpaquetranspor; "OpaqueTransport"
0x1800299b0  mov     rcx, rbp; String1
0x1800299b3  call    wcscmp_0
0x1800299b8  test    eax, eax
0x1800299ba  jnz     loc_180029A5C
0x1800299c0  cmp     [rsi+90h], ebx
0x1800299c6  jz      short loc_1800299DD
0x1800299c8  mov     r9d, 15B1h
0x1800299ce  mov     edi, 80090029h
0x1800299d3  mov     ecx, 80090029h
0x1800299d8  jmp     loc_180029865
0x1800299dd  mov     eax, [rsi+1ACh]
0x1800299e3  test    al, 20h
0x1800299e5  jz      short loc_1800299FC
0x1800299e7  mov     r9d, 15B9h
0x1800299ed  mov     edi, 80090010h
0x1800299f2  mov     ecx, 80090010h
0x1800299f7  jmp     loc_180029865
0x1800299fc  lea     rbx, [rsi+130h]
0x180029a03  mov     dl, 1; Wait
0x180029a05  mov     rcx, rbx; Resource
0x180029a08  call    cs:__imp_RtlAcquireResourceShared
0x180029a0f  nop     dword ptr [rax+rax+00h]
0x180029a14  mov     r9d, [rsp+0B8h+arg_30]
0x180029a1c  mov     rdx, rsi
0x180029a1f  mov     r8, [rsp+0B8h+pbOutput]
0x180029a27  mov     rcx, [rsp+0B8h+var_78]
0x180029a2c  mov     qword ptr [rsp+0B8h+cbOutput], r13
0x180029a31  call    KspExportOpaqueBlob
0x180029a36  mov     rcx, rbx; Resource
0x180029a39  mov     edi, eax
0x180029a3b  call    cs:__imp_RtlReleaseResource
0x180029a42  nop     dword ptr [rax+rax+00h]
0x180029a47  test    edi, edi
0x180029a49  jz      loc_180029D86
0x180029a4f  mov     r9d, 15CAh
0x180029a55  mov     ecx, edi
0x180029a57  jmp     loc_180029865
0x180029a5c  lea     rdx, aProtectedkeybl; "ProtectedKeyBlob"
0x180029a63  mov     rcx, rbp; String1
0x180029a66  call    wcscmp_0
0x180029a6b  test    eax, eax
0x180029a6d  jnz     short loc_180029A80
0x180029a6f  mov     eax, 1
0x180029a74  mov     r14d, eax
0x180029a77  mov     [rsp+0B8h+var_68], eax
0x180029a7b  jmp     loc_180029D89
0x180029a80  lea     rdx, aPkcs7Envelope; "PKCS7_ENVELOPE"
0x180029a87  mov     rcx, rbp; String1
0x180029a8a  call    wcscmp_0
0x180029a8f  test    eax, eax
0x180029a91  jnz     short loc_180029AA6
0x180029a93  mov     eax, 1
0x180029a98  mov     r14d, eax
0x180029a9b  mov     [rsp+0B8h+var_6C], eax
0x180029a9f  mov     ebx, eax
0x180029aa1  jmp     loc_180029D89
0x180029aa6  lea     rdx, aPkcs8Privateke; "PKCS8_PRIVATEKEY"
0x180029aad  mov     rcx, rbp; String1
0x180029ab0  call    wcscmp_0
0x180029ab5  test    eax, eax
0x180029ab7  jnz     short loc_180029AC7
0x180029ab9  lea     r14d, [rax+1]
0x180029abd  mov     [rsp+0B8h+var_64], r14d
0x180029ac2  jmp     loc_180029D89
0x180029ac7  lea     rdx, aPkcs11rsaaeswr; "PKCS11RsaAesWrapBlob"
0x180029ace  mov     rcx, rbp; String1
0x180029ad1  call    wcscmp_0
0x180029ad6  test    eax, eax
0x180029ad8  jnz     short loc_180029AE8
0x180029ada  lea     r14d, [rax+1]
0x180029ade  mov     [rsp+0B8h+var_60], r14d
0x180029ae3  jmp     loc_180029D89
0x180029ae8  lea     rdx, aPqdsaprivatebl; "PQDSAPRIVATEBLOB"
0x180029aef  mov     rcx, rbp; String1
0x180029af2  call    wcscmp_0
0x180029af7  test    eax, eax
0x180029af9  jz      loc_180029C90
0x180029aff  lea     rdx, aPqdsaprivatese; "PQDSAPRIVATESEEDBLOB"
0x180029b06  mov     rcx, rbp; String1
0x180029b09  call    wcscmp_0
0x180029b0e  test    eax, eax
0x180029b10  jz      loc_180029C90
0x180029b16  lea     rdx, aPqdsapublicblo; "PQDSAPUBLICBLOB"
  ... truncated ...
```
