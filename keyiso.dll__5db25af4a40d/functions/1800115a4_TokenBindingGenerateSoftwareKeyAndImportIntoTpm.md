# TokenBindingGenerateSoftwareKeyAndImportIntoTpm

- ea: `0x1800115a4`
- end: `0x180011785`
- name: `TokenBindingGenerateSoftwareKeyAndImportIntoTpm`
- size: `481`
- prototype: `__int64 __fastcall(__int64, BYTE *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011790`

## callees

- `0x180003cf0`
- `0x180006280`
- `0x18001140c`
- `0x1800115a4`

## import_xrefs

- `ncrypt!NCryptImportKey` at `0x1800116f8`
- `ncrypt!NCryptImportKey` at `0x1800116f8`
- `ncrypt!NCryptFreeObject` at `0x18001175e`
- `ncrypt!NCryptFreeObject` at `0x18001176d`
- `ncrypt!NCryptFreeObject` at `0x18001175e`
- `ncrypt!NCryptFreeObject` at `0x18001176d`
- `ncrypt!NCryptSetProperty` at `0x1800116b2`
- `ncrypt!NCryptSetProperty` at `0x1800116b2`
- `ncrypt!NCryptOpenStorageProvider` at `0x180011681`
- `ncrypt!NCryptOpenStorageProvider` at `0x180011681`

## string_xrefs

- `0x18001161c`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\tokenbindingcryptoapi.c`
- `0x18001171e`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\tokenbindingcryptoapi.c`

## pseudocode

```c
__int64 __fastcall TokenBindingGenerateSoftwareKeyAndImportIntoTpm(__int64 a1, BYTE *a2, __int64 a3, unsigned int a4)
{
  PBYTE v6; // rdi
  unsigned int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rdi
  __int64 v11; // rax
  unsigned int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rax
  PBYTE v16; // rcx
  PBYTE pbData; // [rsp+40h] [rbp-19h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+48h] [rbp-11h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-9h] BYREF
  __int128 v21; // [rsp+58h] [rbp-1h] BYREF
  NCryptBufferDesc pParameterList; // [rsp+68h] [rbp+Fh] BYREF
  DWORD cbData; // [rsp+C0h] [rbp+67h] BYREF

  phProvider = 0;
  phKey = 0;
  pbData = 0;
  cbData = 0;
  v6 = 0;
  v21 = 0;
  pParameterList = 0;
  if ( !a1 || !a2 || !a3 )
  {
    v8 = -2146893785;
    v13 = 136;
    v14 = 2148073511LL;
    goto LABEL_17;
  }
  v7 = TokenBindingGenerateBCryptKeyBlob(a1, a4, &pbData, &cbData);
  v8 = v7;
  if ( v7 )
  {
    v9 = 143;
LABEL_6:
    DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\tokenbindingcryptoapi.c", v9);
LABEL_7:
    v6 = pbData;
    goto LABEL_18;
  }
  v10 = -1;
  DWORD1(v21) = 45;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a3 + 2 * v11) );
  *((_QWORD *)&v21 + 1) = a3;
  LODWORD(v21) = 2 * v11 + 2;
  pParameterList.ulVersion = 0;
  pParameterList.pBuffers = (PBCryptBuffer)&v21;
  pParameterList.cBuffers = 1;
  v8 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  if ( v8 )
    goto LABEL_7;
  do
    ++v10;
  while ( *(_WORD *)&a2[2 * v10] );
  v7 = NCryptSetProperty(phProvider, L"PCP_ALTERNATE_KEY_STORAGE_LOCATION", a2, 2 * v10 + 2, 0);
  v8 = v7;
  if ( v7 )
  {
    v9 = 180;
    goto LABEL_6;
  }
  v6 = pbData;
  v12 = NCryptImportKey(phProvider, 0, L"RSAPRIVATEBLOB", &pParameterList, &phKey, pbData, cbData, 0);
  v8 = v12;
  if ( v12 )
  {
    v13 = 187;
    v14 = v12;
LABEL_17:
    DebugTraceError(
      v14,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\tokenbindingcryptoapi.c",
      v13);
  }
LABEL_18:
  if ( v6 )
  {
    v15 = cbData;
    v16 = v6;
    if ( cbData )
    {
      do
      {
        *v16++ = 0;
        --v15;
      }
      while ( v15 );
    }
    MSCryptFree(v6);
  }
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( phKey )
    NCryptFreeObject(phKey);
  return v8;
}

```

## disassembly

```asm
0x1800115a4  push    rbp
0x1800115a6  push    rbx
0x1800115a7  push    rsi
0x1800115a8  push    rdi
0x1800115a9  push    r14
0x1800115ab  push    r15
0x1800115ad  lea     rbp, [rsp-2Fh]
0x1800115b2  sub     rsp, 88h
0x1800115b9  xor     r15d, r15d
0x1800115bc  xorps   xmm0, xmm0
0x1800115bf  mov     [rbp+57h+phProvider], r15
0x1800115c3  xorps   xmm1, xmm1
0x1800115c6  mov     [rbp+57h+phKey], r15
0x1800115ca  mov     eax, r9d
0x1800115cd  mov     [rbp+57h+var_70], r15
0x1800115d1  mov     rsi, r8
0x1800115d4  mov     [rbp+57h+arg_0], r15d
0x1800115d8  mov     r14, rdx
0x1800115db  mov     edi, r15d
0x1800115de  movups  [rbp+57h+var_58], xmm0
0x1800115e2  movups  xmmword ptr [rbp+57h+pParameterList.ulVersion], xmm1
0x1800115e6  test    rcx, rcx
0x1800115e9  jz      loc_18001170E
0x1800115ef  test    rdx, rdx
0x1800115f2  jz      loc_18001170E
0x1800115f8  test    r8, r8
0x1800115fb  jz      loc_18001170E
0x180011601  lea     r9, [rbp+57h+arg_0]
0x180011605  mov     edx, eax
0x180011607  lea     r8, [rbp+57h+var_70]
0x18001160b  call    TokenBindingGenerateBCryptKeyBlob
0x180011610  mov     ebx, eax
0x180011612  test    eax, eax
0x180011614  jz      short loc_18001163A
0x180011616  mov     r9d, 8Fh
0x18001161c  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011623  mov     ecx, eax
0x180011625  lea     rdx, aStatus; "Status"
0x18001162c  call    DebugTraceError
0x180011631  mov     rdi, [rbp+57h+var_70]
0x180011635  jmp     loc_180011731
0x18001163a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001163e  mov     dword ptr [rbp+57h+var_58+4], 2Dh ; '-'
0x180011645  mov     rax, rdi
0x180011648  inc     rax
0x18001164b  cmp     [rsi+rax*2], r15w
0x180011650  jnz     short loc_180011648
0x180011652  lea     eax, ds:2[rax*2]
0x180011659  mov     qword ptr [rbp+57h+var_58+8], rsi
0x18001165d  mov     dword ptr [rbp+57h+var_58], eax
0x180011660  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180011667  lea     rax, [rbp+57h+var_58]
0x18001166b  mov     [rbp+57h+pParameterList.ulVersion], r15d
0x18001166f  xor     r8d, r8d; dwFlags
0x180011672  mov     [rbp+57h+pParameterList.pBuffers], rax
0x180011676  lea     rcx, [rbp+57h+phProvider]; phProvider
0x18001167a  mov     [rbp+57h+pParameterList.cBuffers], 1
0x180011681  call    cs:__imp_NCryptOpenStorageProvider
0x180011687  mov     ebx, eax
0x180011689  test    eax, eax
0x18001168b  jnz     short loc_180011631
0x18001168d  inc     rdi
0x180011690  cmp     [r14+rdi*2], r15w
0x180011695  jnz     short loc_18001168D
0x180011697  mov     rcx, [rbp+57h+phProvider]; hObject
0x18001169b  lea     r9d, ds:2[rdi*2]; cbInput
0x1800116a3  mov     r8, r14; pbInput
0x1800116a6  mov     [rsp+0B0h+dwFlags], r15d; dwFlags
0x1800116ab  lea     rdx, pszProperty; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x1800116b2  call    cs:__imp_NCryptSetProperty
0x1800116b8  mov     ebx, eax
0x1800116ba  test    eax, eax
0x1800116bc  jz      short loc_1800116C9
0x1800116be  mov     r9d, 0B4h
0x1800116c4  jmp     loc_18001161C
0x1800116c9  mov     eax, [rbp+57h+arg_0]
0x1800116cc  lea     r9, [rbp+57h+pParameterList]; pParameterList
0x1800116d0  mov     rdi, [rbp+57h+var_70]
0x1800116d4  lea     r8, pszBlobType; "RSAPRIVATEBLOB"
0x1800116db  mov     rcx, [rbp+57h+phProvider]; hProvider
0x1800116df  xor     edx, edx; hImportKey
0x1800116e1  mov     [rsp+0B0h+var_78], r15d; dwFlags
0x1800116e6  mov     [rsp+0B0h+cbData], eax; cbData
0x1800116ea  lea     rax, [rbp+57h+phKey]
0x1800116ee  mov     [rsp+0B0h+pbData], rdi; pbData
0x1800116f3  mov     qword ptr [rsp+0B0h+dwFlags], rax; phKey
0x1800116f8  call    cs:__imp_NCryptImportKey
0x1800116fe  mov     ebx, eax
0x180011700  test    eax, eax
0x180011702  jz      short loc_180011731
0x180011704  mov     r9d, 0BBh
0x18001170a  mov     ecx, eax
0x18001170c  jmp     short loc_18001171E
0x18001170e  mov     ebx, 80090027h
0x180011713  mov     r9d, 88h
0x180011719  mov     ecx, 80090027h
0x18001171e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011725  lea     rdx, aStatus; "Status"
0x18001172c  call    DebugTraceError
0x180011731  test    rdi, rdi
0x180011734  jz      short loc_180011755
0x180011736  mov     eax, [rbp+57h+arg_0]
0x180011739  mov     rcx, rdi
0x18001173c  test    rax, rax
0x18001173f  jz      short loc_18001174D
0x180011741  mov     [rcx], r15b
0x180011744  inc     rcx
0x180011747  sub     rax, 1
0x18001174b  jnz     short loc_180011741
0x18001174d  mov     rcx, rdi
0x180011750  call    MSCryptFree
0x180011755  mov     rcx, [rbp+57h+phProvider]; hObject
0x180011759  test    rcx, rcx
0x18001175c  jz      short loc_180011764
0x18001175e  call    cs:__imp_NCryptFreeObject
0x180011764  mov     rcx, [rbp+57h+phKey]; hObject
0x180011768  test    rcx, rcx
0x18001176b  jz      short loc_180011773
0x18001176d  call    cs:__imp_NCryptFreeObject
0x180011773  mov     eax, ebx
0x180011775  add     rsp, 88h
0x18001177c  pop     r15
0x18001177e  pop     r14
0x180011780  pop     rdi
0x180011781  pop     rsi
0x180011782  pop     rbx
0x180011783  pop     rbp
0x180011784  retn
```
