# RtlHashLBlob

- ea: `0x180114758`
- end: `0x180114a80`
- name: `RtlHashLBlob`
- size: `808`
- prototype: ``
- caller_count: `12`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800d571c`
- `0x1800e1170`
- `0x180109608`
- `0x180110964`
- `0x180110a38`
- `0x180110b0c`
- `0x180110d0c`
- `0x1801112e8`
- `0x180111454`
- `0x180112f98`
- `0x180113178`
- `0x1801133e8`

## callees

- `0x1800069e5`
- `0x180012b1c`
- `0x180018b30`
- `0x1800567b4`
- `0x180114700`
- `0x180114758`
- `0x180121380`
- `0x1801213d4`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180114947`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180114947`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x180114848`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextA` at `0x180114848`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1801148ae`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1801148ae`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1801148e8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180114973`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1801148e8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180114973`

## string_xrefs

- `0x180114780`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\crypto.cpp`

## pseudocode

```c
__int64 __fastcall RtlHashLBlob(DWORD a1, unsigned int a2, unsigned __int64 *a3, __int64 a4)
{
  unsigned int v7; // ebx
  unsigned int *v8; // r8
  unsigned __int64 v9; // rdx
  _QWORD *v10; // r10
  unsigned __int64 v11; // rcx
  ALG_ID v12; // esi
  DWORD v13; // eax
  unsigned int v14; // eax
  int v15; // r9d
  __int64 v16; // rdx
  int v17; // r8d
  unsigned __int64 v18; // rdx
  DWORD LastError_0; // eax
  DWORD v20; // eax
  unsigned __int64 v21; // rsi
  const BYTE *i; // r14
  DWORD v23; // edi
  unsigned __int64 v24; // rdx
  DWORD v25; // eax
  Windows::Rtl *v26; // rcx
  DWORD v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  HCRYPTHASH phHash; // [rsp+30h] [rbp-30h] BYREF
  HCRYPTPROV phProv; // [rsp+38h] [rbp-28h] BYREF
  const char *v35; // [rsp+40h] [rbp-20h] BYREF
  int v36; // [rsp+48h] [rbp-18h]
  unsigned int v37; // [rsp+50h] [rbp-10h]
  DWORD pbData; // [rsp+A0h] [rbp+40h] BYREF
  DWORD pdwDataLen; // [rsp+B8h] [rbp+58h] BYREF

  pbData = a1;
  v37 = -1073741595;
  v35 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\crypto.cpp";
  if ( a4 )
    *(_QWORD *)a4 = 0;
  if ( !a3 )
  {
    v36 = 357;
LABEL_5:
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v35);
    return v37;
  }
  v8 = (unsigned int *)a3[2];
  if ( !v8 && *a3 || (v9 = *a3, *a3 > a3[1]) )
  {
    v36 = 358;
    goto LABEL_5;
  }
  if ( !a4 )
  {
    v36 = 359;
    goto LABEL_5;
  }
  v10 = *(_QWORD **)(a4 + 16);
  if ( !v10 && *(_QWORD *)a4 || (v11 = *(_QWORD *)(a4 + 8), *(_QWORD *)a4 > v11) )
  {
    v36 = 360;
    goto LABEL_5;
  }
  if ( a2 == 1 )
  {
    if ( v11 < 8 )
    {
      v7 = -1073741789;
      Windows::ErrorHandling::COM::ReportNtErrorOrigination(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\crypto.cpp",
        (const char *)0x16E,
        -1073741789,
        1);
      return v7;
    }
    v28 = 0;
    if ( v9 >= 4 )
    {
      if ( ((unsigned __int8)v8 & 3) != 0 )
      {
        do
        {
          v30 = *v8;
          v9 -= 4LL;
          ++v8;
          v28 = v30 + 0x1FFFFFFF7LL * v28;
        }
        while ( v9 >= 4 );
      }
      else
      {
        do
        {
          v29 = *v8;
          v9 -= 4LL;
          ++v8;
          v28 = v29 + 0x1FFFFFFF7LL * v28;
        }
        while ( v9 >= 4 );
      }
    }
    for ( ; v9; --v9 )
    {
      v31 = *(unsigned __int8 *)v8;
      v8 = (unsigned int *)((char *)v8 + 1);
      v28 = v31 + 0x1FFFFFFF7LL * v28;
    }
    *v10 = v28;
    *(_QWORD *)a4 = 8;
    return 0;
  }
  phProv = 0;
  phHash = 0;
  pbData = 0;
  pdwDataLen = 0;
  v12 = HashAlgorithmToAlgId(a2);
  if ( CryptAcquireContextA(&phProv, 0, 0, 1u, 0xF0000000) )
  {
    if ( !CryptCreateHash(phProv, v12, 0, 0, &phHash) )
    {
      LastError_0 = GetLastError_0();
      v14 = isowin32_ConvertWin32ErrorToNtStatus(LastError_0);
      v16 = 436;
      goto LABEL_19;
    }
    pdwDataLen = 4;
    if ( !CryptGetHashParam(phHash, 4u, (BYTE *)&pbData, &pdwDataLen, 0) )
    {
      v20 = GetLastError_0();
      v14 = isowin32_ConvertWin32ErrorToNtStatus(v20);
      v16 = 444;
      goto LABEL_19;
    }
    if ( *(_QWORD *)(a4 + 8) < (unsigned __int64)pbData )
    {
      v7 = -1073741789;
      v16 = 446;
      v17 = -1073741789;
      goto LABEL_20;
    }
    v21 = *a3;
    for ( i = (const BYTE *)a3[2]; ; i += v23 )
    {
      v23 = -1;
      if ( v21 <= 0xFFFFFFFF )
        v23 = v21;
      if ( !CryptHashData(phHash, i, v23, 0) )
      {
        v27 = GetLastError_0();
        v14 = isowin32_ConvertWin32ErrorToNtStatus(v27);
        v16 = 460;
        goto LABEL_19;
      }
      v21 -= v23;
      if ( !v21 )
        break;
    }
    if ( !CryptGetHashParam(phHash, 2u, *(BYTE **)(a4 + 16), &pbData, 0) )
    {
      v25 = GetLastError_0();
      v14 = isowin32_ConvertWin32ErrorToNtStatus(v25);
      v16 = 473;
      goto LABEL_19;
    }
    v26 = (Windows::Rtl *)phHash;
    *(_QWORD *)a4 = pbData;
    if ( v26 )
    {
      Windows::Rtl::CloseCryptHash(v26, v24);
      phHash = 0;
    }
    if ( phProv )
      Windows::Rtl::CloseCryptProv((Windows::Rtl *)phProv, v24);
    return 0;
  }
  v13 = GetLastError_0();
  v14 = isowin32_ConvertWin32ErrorToNtStatus(v13);
  v16 = 428;
LABEL_19:
  v17 = v14;
  v7 = v14;
LABEL_20:
  Windows::ErrorHandling::COM::ReportNtErrorOrigination(
    (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\crypto.cpp",
    (const char *)v16,
    v17,
    v15);
  if ( phHash )
  {
    Windows::Rtl::CloseCryptHash((Windows::Rtl *)phHash, v18);
    phHash = 0;
  }
  if ( phProv )
    Windows::Rtl::CloseCryptProv((Windows::Rtl *)phProv, v18);
  return v7;
}

```

## disassembly

```asm
0x180114758  mov     [rsp-38h+arg_8], rbx
0x18011475d  mov     [rsp-38h+pbData], ecx
0x180114761  push    rbp
0x180114762  push    rsi
0x180114763  push    rdi
0x180114764  push    r12
0x180114766  push    r13
0x180114768  push    r14
0x18011476a  push    r15
0x18011476c  mov     rbp, rsp
0x18011476f  sub     rsp, 60h
0x180114773  mov     rbx, r9
0x180114776  mov     [rbp+var_10], 0C00000E5h
0x18011477d  xor     r15d, r15d
0x180114780  lea     r12, aOnecoreComNetf_36; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180114787  mov     [rbp+var_20], r12
0x18011478b  mov     rdi, r8
0x18011478e  mov     r9d, edx; int
0x180114791  test    rbx, rbx
0x180114794  jz      short loc_180114799
0x180114796  mov     [rbx], r15
0x180114799  test    rdi, rdi
0x18011479c  jnz     short loc_1801147B6
0x18011479e  mov     [rbp+var_18], 165h
0x1801147a5  lea     rcx, [rbp+var_20]
0x1801147a9  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1801147ae  mov     ebx, [rbp+var_10]
0x1801147b1  jmp     loc_180114A66
0x1801147b6  mov     r8, [r8+10h]
0x1801147ba  test    r8, r8
0x1801147bd  jnz     short loc_1801147C4
0x1801147bf  cmp     [rdi], r15
0x1801147c2  jnz     short loc_1801147CD
0x1801147c4  mov     rdx, [rdi]
0x1801147c7  cmp     rdx, [rdi+8]
0x1801147cb  jbe     short loc_1801147D6
0x1801147cd  mov     [rbp+var_18], 166h
0x1801147d4  jmp     short loc_180114802
0x1801147d6  test    rbx, rbx
0x1801147d9  jnz     short loc_1801147E4
0x1801147db  mov     [rbp+var_18], 167h
0x1801147e2  jmp     short loc_1801147A5
0x1801147e4  mov     r10, [rbx+10h]
0x1801147e8  test    r10, r10
0x1801147eb  jnz     short loc_1801147F2
0x1801147ed  cmp     [rbx], r15
0x1801147f0  jnz     short loc_1801147FB
0x1801147f2  mov     rcx, [rbx+8]
0x1801147f6  cmp     [rbx], rcx
0x1801147f9  jbe     short loc_18011480D
0x1801147fb  mov     [rbp+var_18], 168h
0x180114802  lea     rcx, [rbp+var_20]
0x180114806  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18011480b  jmp     short loc_1801147AE
0x18011480d  cmp     r9d, 1
0x180114811  jz      loc_1801149D8
0x180114817  mov     ecx, r9d
0x18011481a  mov     [rbp+phProv], r15
0x18011481e  mov     [rbp+phHash], r15
0x180114822  mov     [rbp+pbData], r15d
0x180114826  mov     [rbp+pdwDataLen], r15d
0x18011482a  call    HashAlgorithmToAlgId
0x18011482f  lea     rcx, [rbp+phProv]; phProv
0x180114833  mov     [rsp+60h+dwFlags], 0F0000000h; dwFlags
0x18011483b  mov     r9d, 1; dwProvType
0x180114841  xor     r8d, r8d; szProvider
0x180114844  xor     edx, edx; szContainer
0x180114846  mov     esi, eax
0x180114848  call    cs:__imp_CryptAcquireContextA
0x18011484e  test    eax, eax
0x180114850  jnz     short loc_180114899
0x180114852  call    GetLastError_0
0x180114857  mov     ecx, eax; unsigned int
0x180114859  call    ?isowin32_ConvertWin32ErrorToNtStatus@@YAJK@Z; isowin32_ConvertWin32ErrorToNtStatus(ulong)
0x18011485e  mov     edx, 1ACh; char *
0x180114863  mov     r8d, eax; int
0x180114866  mov     ebx, eax
0x180114868  mov     rcx, r12; this
0x18011486b  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x180114870  mov     rcx, [rbp+phHash]; this
0x180114874  test    rcx, rcx
0x180114877  jz      short loc_180114882
0x180114879  call    ?CloseCryptHash@Rtl@Windows@@YAX_K@Z; Windows::Rtl::CloseCryptHash(unsigned __int64)
0x18011487e  mov     [rbp+phHash], r15
0x180114882  mov     rcx, [rbp+phProv]; this
0x180114886  test    rcx, rcx
0x180114889  jz      loc_180114A66
0x18011488f  call    ?CloseCryptProv@Rtl@Windows@@YAX_K@Z; Windows::Rtl::CloseCryptProv(unsigned __int64)
0x180114894  jmp     loc_180114A66
0x180114899  mov     rcx, [rbp+phProv]; hProv
0x18011489d  lea     rax, [rbp+phHash]
0x1801148a1  xor     r9d, r9d; dwFlags
0x1801148a4  mov     qword ptr [rsp+60h+dwFlags], rax; phHash
0x1801148a9  xor     r8d, r8d; hKey
0x1801148ac  mov     edx, esi; Algid
0x1801148ae  call    cs:__imp_CryptCreateHash
0x1801148b4  test    eax, eax
0x1801148b6  jnz     short loc_1801148CB
0x1801148b8  call    GetLastError_0
0x1801148bd  mov     ecx, eax; unsigned int
0x1801148bf  call    ?isowin32_ConvertWin32ErrorToNtStatus@@YAJK@Z; isowin32_ConvertWin32ErrorToNtStatus(ulong)
0x1801148c4  mov     edx, 1B4h
0x1801148c9  jmp     short loc_180114863
0x1801148cb  mov     rcx, [rbp+phHash]; hHash
0x1801148cf  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x1801148d3  lea     r8, [rbp+pbData]; pbData
0x1801148d7  mov     [rbp+pdwDataLen], 4
0x1801148de  mov     edx, 4; dwParam
0x1801148e3  mov     [rsp+60h+dwFlags], r15d; dwFlags
0x1801148e8  call    cs:__imp_CryptGetHashParam
0x1801148ee  test    eax, eax
0x1801148f0  jnz     short loc_180114908
0x1801148f2  call    GetLastError_0
0x1801148f7  mov     ecx, eax; unsigned int
0x1801148f9  call    ?isowin32_ConvertWin32ErrorToNtStatus@@YAJK@Z; isowin32_ConvertWin32ErrorToNtStatus(ulong)
0x1801148fe  mov     edx, 1BCh
0x180114903  jmp     loc_180114863
0x180114908  mov     eax, [rbp+pbData]
0x18011490b  cmp     [rbx+8], rax
0x18011490f  jnb     short loc_180114923
0x180114911  mov     ebx, 0C0000023h
0x180114916  mov     edx, 1BEh
0x18011491b  mov     r8d, ebx
0x18011491e  jmp     loc_180114868
0x180114923  mov     rsi, [rdi]
0x180114926  mov     r13d, 0FFFFFFFFh
0x18011492c  mov     r14, [rdi+10h]
0x180114930  mov     edi, r13d
0x180114933  cmp     rsi, r13
0x180114936  ja      short loc_18011493A
0x180114938  mov     edi, esi
0x18011493a  mov     rcx, [rbp+phHash]; hHash
0x18011493e  xor     r9d, r9d; dwFlags
0x180114941  mov     r8d, edi; dwDataLen
0x180114944  mov     rdx, r14; pbData
0x180114947  call    cs:__imp_CryptHashData
0x18011494d  test    eax, eax
0x18011494f  jz      short loc_1801149C2
0x180114951  mov     eax, edi
0x180114953  sub     rsi, rax
0x180114956  jz      short loc_18011495D
0x180114958  add     r14, rax
0x18011495b  jmp     short loc_180114930
0x18011495d  mov     r8, [rbx+10h]; pbData
0x180114961  lea     r9, [rbp+pbData]; pdwDataLen
0x180114965  mov     rcx, [rbp+phHash]; hHash
0x180114969  mov     edx, 2; dwParam
0x18011496e  mov     [rsp+60h+dwFlags], r15d; dwFlags
0x180114973  call    cs:__imp_CryptGetHashParam
0x180114979  test    eax, eax
0x18011497b  jnz     short loc_180114993
0x18011497d  call    GetLastError_0
0x180114982  mov     ecx, eax; unsigned int
0x180114984  call    ?isowin32_ConvertWin32ErrorToNtStatus@@YAJK@Z; isowin32_ConvertWin32ErrorToNtStatus(ulong)
0x180114989  mov     edx, 1D9h
0x18011498e  jmp     loc_180114863
0x180114993  mov     rcx, [rbp+phHash]; this
0x180114997  mov     eax, [rbp+pbData]
0x18011499a  mov     [rbx], rax
0x18011499d  test    rcx, rcx
0x1801149a0  jz      short loc_1801149AB
0x1801149a2  call    ?CloseCryptHash@Rtl@Windows@@YAX_K@Z; Windows::Rtl::CloseCryptHash(unsigned __int64)
0x1801149a7  mov     [rbp+phHash], r15
0x1801149ab  mov     rcx, [rbp+phProv]; this
0x1801149af  test    rcx, rcx
0x1801149b2  jz      loc_180114A63
0x1801149b8  call    ?CloseCryptProv@Rtl@Windows@@YAX_K@Z; Windows::Rtl::CloseCryptProv(unsigned __int64)
0x1801149bd  jmp     loc_180114A63
0x1801149c2  call    GetLastError_0
0x1801149c7  mov     ecx, eax; unsigned int
0x1801149c9  call    ?isowin32_ConvertWin32ErrorToNtStatus@@YAJK@Z; isowin32_ConvertWin32ErrorToNtStatus(ulong)
0x1801149ce  mov     edx, 1CCh
0x1801149d3  jmp     loc_180114863
0x1801149d8  cmp     rcx, 8
0x1801149dc  jnb     short loc_1801149F5
0x1801149de  mov     ebx, 0C0000023h
0x1801149e3  mov     edx, 16Eh; char *
0x1801149e8  mov     r8d, ebx; int
0x1801149eb  mov     rcx, r12; this
0x1801149ee  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x1801149f3  jmp     short loc_180114A66
0x1801149f5  mov     rcx, r15
0x1801149f8  mov     r9, 1FFFFFFF7h
0x180114a02  cmp     rdx, 4
0x180114a06  jb      short loc_180114A40
0x180114a08  test    r8b, 3
0x180114a0c  jnz     short loc_180114A28
0x180114a0e  mov     eax, [r8]
0x180114a11  sub     rdx, 4
0x180114a15  imul    rcx, r9
0x180114a19  add     r8, 4
0x180114a1d  add     rcx, rax
0x180114a20  cmp     rdx, 4
0x180114a24  jnb     short loc_180114A0E
0x180114a26  jmp     short loc_180114A40
0x180114a28  mov     eax, [r8]
0x180114a2b  sub     rdx, 4
0x180114a2f  imul    rcx, r9
0x180114a33  add     r8, 4
0x180114a37  add     rcx, rax
0x180114a3a  cmp     rdx, 4
0x180114a3e  jnb     short loc_180114A28
0x180114a40  test    rdx, rdx
0x180114a43  jz      short loc_180114A59
0x180114a45  movzx   eax, byte ptr [r8]
0x180114a49  inc     r8
0x180114a4c  imul    rcx, r9
0x180114a50  add     rcx, rax
0x180114a53  sub     rdx, 1
0x180114a57  jnz     short loc_180114A45
0x180114a59  mov     [r10], rcx
0x180114a5c  mov     qword ptr [rbx], 8
0x180114a63  mov     ebx, r15d
0x180114a66  mov     eax, ebx
0x180114a68  mov     rbx, [rsp+60h+arg_8]
0x180114a70  add     rsp, 60h
0x180114a74  pop     r15
0x180114a76  pop     r14
0x180114a78  pop     r13
0x180114a7a  pop     r12
0x180114a7c  pop     rdi
0x180114a7d  pop     rsi
0x180114a7e  pop     rbp
0x180114a7f  retn
```
