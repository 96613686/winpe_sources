# _TpmEndorsementKeyGetEkPub(_CERT_PUBLIC_KEY_INFO * *)

- ea: `0x180005680`
- end: `0x18000588c`
- name: `?_TpmEndorsementKeyGetEkPub@@YAKPEAPEAU_CERT_PUBLIC_KEY_INFO@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(struct _CERT_PUBLIC_KEY_INFO **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001970`

## callees

- `0x180003750`
- `0x180005680`
- `0x180005b68`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000581d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000584e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005857`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000581d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000584e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005857`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000574a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000574a`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800056ba`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800056ba`
- `ncrypt!NCryptGetProperty` at `0x18000572b`
- `ncrypt!NCryptGetProperty` at `0x18000572b`
- `ncrypt!NCryptFreeObject` at `0x18000587e`
- `ncrypt!NCryptFreeObject` at `0x18000587e`

## string_xrefs

- `0x1800056cc`: `ERROR: NCryptOpenStorageProvider. Hr=%x\n`

## pseudocode

```c
__int64 __fastcall _TpmEndorsementKeyGetEkPub(struct _CERT_PUBLIC_KEY_INFO **a1)
{
  struct _CERT_PUBLIC_KEY_INFO *v1; // rdi
  SECURITY_STATUS v3; // eax
  unsigned int v4; // ebx
  BYTE *v5; // rsi
  BYTE *v6; // rbp
  NCRYPT_HANDLE v7; // r12
  DWORD v8; // r15d
  SECURITY_STATUS Property; // eax
  unsigned int v10; // eax
  DWORD *pcbResult; // [rsp+20h] [rbp-48h]
  DWORD v13; // [rsp+78h] [rbp+10h] BYREF
  struct _CERT_PUBLIC_KEY_INFO *v14; // [rsp+80h] [rbp+18h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+88h] [rbp+20h] BYREF

  v1 = 0;
  hObject = 0;
  v14 = 0;
  v3 = NCryptOpenStorageProvider(&hObject, L"Microsoft Platform Crypto Provider", 0x40u);
  v4 = v3;
  v5 = 0;
  if ( v3 )
  {
    ekTraceFmt(0x3A812C2u, 1, "ERROR: NCryptOpenStorageProvider. Hr=%x\n", v3);
  }
  else
  {
    v6 = 0;
    v7 = hObject;
    v8 = 0;
    while ( 1 )
    {
      v13 = 0;
      Property = NCryptGetProperty(v7, L"PCP_EKPUB", v6, v8, &v13, 0x40u);
      v4 = Property;
      if ( Property )
      {
        LODWORD(pcbResult) = Property;
        ekTraceFmt(0x4912C2u, 1, "ERROR: NCryptGetProperty(%ws) Hr=%x\n", L"PCP_EKPUB", pcbResult);
        goto LABEL_14;
      }
      if ( v6 )
        break;
      v8 = v13;
      v6 = (BYTE *)LocalAlloc(0, v13);
      if ( !v6 )
      {
        v4 = -2147024882;
        ekTraceFmt(0x5C12C2u, 1, "ERROR: LocalAlloc. Return=%d\n", -2147024882);
LABEL_14:
        LocalFree(v6);
        ekTraceFmt(0x3B812C2u, 1, "ERROR: _GetNCryptBlobProperty(EKPUB). Hr=%x\n", v4);
        goto LABEL_15;
      }
    }
    if ( v8 != v13 )
    {
      v4 = -2147024736;
      ekTraceFmt(0x5112C2u, 1, "ERROR: cbProp != cbPropT. Hr=%x\n", -2147024736);
      goto LABEL_14;
    }
    v5 = v6;
    LocalFree(0);
    v10 = _ConvertRsaPublicKeyBlob(v6, v8, &v14);
    v4 = v10;
    if ( v10 )
    {
      ekTraceFmt(0x3C212C2u, 1, "ERROR: _ConvertRsaPublicKeyBlob. Hr=%x\n", v10);
      v1 = v14;
    }
    else
    {
      v4 = 0;
      *a1 = v14;
    }
  }
LABEL_15:
  LocalFree(v5);
  LocalFree(v1);
  if ( hObject )
    NCryptFreeObject(hObject);
  return v4;
}

```

## disassembly

```asm
0x180005680  mov     rax, rsp
0x180005683  push    rbx
0x180005684  sub     rsp, 60h
0x180005688  mov     [rax-10h], rsi
0x18000568c  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180005693  mov     [rax-18h], rdi
0x180005697  mov     r8d, 40h ; '@'; dwFlags
0x18000569d  mov     [rax-28h], r13
0x1800056a1  xor     r13d, r13d
0x1800056a4  mov     [rax-30h], r14
0x1800056a8  mov     edi, r13d
0x1800056ab  mov     r14, rcx
0x1800056ae  mov     [rax+20h], r13
0x1800056b2  lea     rcx, [rax+20h]; phProvider
0x1800056b6  mov     [rax+18h], r13
0x1800056ba  call    cs:__imp_NCryptOpenStorageProvider
0x1800056c0  mov     ebx, eax
0x1800056c2  mov     esi, r13d
0x1800056c5  test    eax, eax
0x1800056c7  jz      short loc_1800056E7
0x1800056c9  mov     r9d, eax
0x1800056cc  lea     r8, aErrorNcryptope; "ERROR: NCryptOpenStorageProvider. Hr=%x"...
0x1800056d3  mov     edx, 1; unsigned int
0x1800056d8  mov     ecx, 3A812C2h; unsigned int
0x1800056dd  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800056e2  jmp     loc_18000584B
0x1800056e7  mov     [rsp+68h+arg_0], rbp
0x1800056ec  mov     rbp, r13
0x1800056ef  mov     [rsp+68h+var_20], r12
0x1800056f4  mov     r12, [rsp+68h+hObject]
0x1800056fc  mov     [rsp+68h+var_38], r15
0x180005701  mov     r15d, r13d
0x180005704  lea     rax, [rsp+68h+arg_8]
0x180005709  mov     [rsp+68h+dwFlags], 40h ; '@'; dwFlags
0x180005711  mov     r9d, r15d; cbOutput
0x180005714  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180005719  mov     r8, rbp; pbOutput
0x18000571c  mov     [rsp+68h+arg_8], r13d
0x180005721  lea     rdx, aPcpEkpub; "PCP_EKPUB"
0x180005728  mov     rcx, r12; hObject
0x18000572b  call    cs:__imp_NCryptGetProperty
0x180005731  mov     ebx, eax
0x180005733  test    eax, eax
0x180005735  jnz     loc_1800057F9
0x18000573b  test    rbp, rbp
0x18000573e  jnz     short loc_18000577B
0x180005740  mov     r15d, [rsp+68h+arg_8]
0x180005745  xor     ecx, ecx; uFlags
0x180005747  mov     edx, r15d; uBytes
0x18000574a  call    cs:__imp_LocalAlloc
0x180005750  mov     rbp, rax
0x180005753  test    rax, rax
0x180005756  jnz     short loc_180005704
0x180005758  mov     ebx, 8007000Eh
0x18000575d  lea     r8, aErrorLocalallo_0; "ERROR: LocalAlloc. Return=%d\n"
0x180005764  mov     r9d, ebx
0x180005767  mov     edx, 1; unsigned int
0x18000576c  mov     ecx, 5C12C2h; unsigned int
0x180005771  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180005776  jmp     loc_18000581A
0x18000577b  cmp     r15d, [rsp+68h+arg_8]
0x180005780  jz      short loc_1800057A2
0x180005782  mov     ebx, 800700A0h
0x180005787  lea     r8, aErrorCbpropCbp; "ERROR: cbProp != cbPropT. Hr=%x\n"
0x18000578e  mov     r9d, ebx
0x180005791  mov     edx, 1; unsigned int
0x180005796  mov     ecx, 5112C2h; unsigned int
0x18000579b  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800057a0  jmp     short loc_18000581A
0x1800057a2  xor     ecx, ecx; hMem
0x1800057a4  mov     rsi, rbp
0x1800057a7  call    cs:__imp_LocalFree
0x1800057ad  lea     r8, [rsp+68h+arg_10]; struct _CERT_PUBLIC_KEY_INFO **
0x1800057b5  mov     edx, r15d; cbData
0x1800057b8  mov     rcx, rbp; pbData
0x1800057bb  call    ?_ConvertRsaPublicKeyBlob@@YAJPEAEKPEAPEAU_CERT_PUBLIC_KEY_INFO@@@Z; _ConvertRsaPublicKeyBlob(uchar *,ulong,_CERT_PUBLIC_KEY_INFO * *)
0x1800057c0  mov     ebx, eax
0x1800057c2  test    eax, eax
0x1800057c4  jz      short loc_1800057E9
0x1800057c6  mov     r9d, eax
0x1800057c9  lea     r8, aErrorConvertrs; "ERROR: _ConvertRsaPublicKeyBlob. Hr=%x"...
0x1800057d0  mov     edx, 1; unsigned int
0x1800057d5  mov     ecx, 3C212C2h; unsigned int
0x1800057da  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800057df  mov     rdi, [rsp+68h+arg_10]
0x1800057e7  jmp     short loc_18000583C
0x1800057e9  mov     rax, [rsp+68h+arg_10]
0x1800057f1  mov     ebx, r13d
0x1800057f4  mov     [r14], rax
0x1800057f7  jmp     short loc_18000583C
0x1800057f9  lea     r9, aPcpEkpub; "PCP_EKPUB"
0x180005800  mov     dword ptr [rsp+68h+pcbResult], eax
0x180005804  lea     r8, aErrorNcryptget; "ERROR: NCryptGetProperty(%ws) Hr=%x\n"
0x18000580b  mov     edx, 1; unsigned int
0x180005810  mov     ecx, 4912C2h; unsigned int
0x180005815  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000581a  mov     rcx, rbp; hMem
0x18000581d  call    cs:__imp_LocalFree
0x180005823  mov     r9d, ebx
0x180005826  lea     r8, aErrorGetncrypt; "ERROR: _GetNCryptBlobProperty(EKPUB). H"...
0x18000582d  mov     edx, 1; unsigned int
0x180005832  mov     ecx, 3B812C2h; unsigned int
0x180005837  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000583c  mov     r12, [rsp+68h+var_20]
0x180005841  mov     rbp, [rsp+68h+arg_0]
0x180005846  mov     r15, [rsp+68h+var_38]
0x18000584b  mov     rcx, rsi; hMem
0x18000584e  call    cs:__imp_LocalFree
0x180005854  mov     rcx, rdi; hMem
0x180005857  call    cs:__imp_LocalFree
0x18000585d  mov     rcx, [rsp+68h+hObject]; hObject
0x180005865  mov     r14, [rsp+68h+var_30]
0x18000586a  mov     r13, [rsp+68h+var_28]
0x18000586f  mov     rdi, [rsp+68h+var_18]
0x180005874  mov     rsi, [rsp+68h+var_10]
0x180005879  test    rcx, rcx
0x18000587c  jz      short loc_180005884
0x18000587e  call    cs:__imp_NCryptFreeObject
0x180005884  mov     eax, ebx
0x180005886  add     rsp, 60h
0x18000588a  pop     rbx
0x18000588b  retn
```
