# CIISDsCrMap::CreateMapping(tagVARIANT,ushort *,ushort *,ushort *,long)

- ea: `0x18000ac50`
- end: `0x18000b223`
- name: `?CreateMapping@CIISDsCrMap@@UEAAJUtagVARIANT@@PEAG11J@Z`
- size: `1491`
- prototype: `__int64 __fastcall(CIISDsCrMap *this, VARIANTARG *pvargSrc, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000a8e0`
- `0x18000ac50`
- `0x18000b22c`
- `0x18000c460`
- `0x18000c55c`
- `0x18000c5ec`
- `0x18000d210`
- `0x18000d6d8`
- `0x1800111e0`
- `0x180012010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000b05b`
- `msvcrt!swprintf_s` at `0x18000b05b`
- `KERNEL32!LocalFree` at `0x18000b1c5`
- `KERNEL32!LocalFree` at `0x18000b1d4`
- `KERNEL32!LocalFree` at `0x18000b1e3`
- `KERNEL32!LocalFree` at `0x18000b1f1`
- `KERNEL32!LocalFree` at `0x18000b1c5`
- `KERNEL32!LocalFree` at `0x18000b1d4`
- `KERNEL32!LocalFree` at `0x18000b1e3`
- `KERNEL32!LocalFree` at `0x18000b1f1`
- `CRYPT32!CertCreateCertificateContext` at `0x18000ad86`
- `CRYPT32!CertCreateCertificateContext` at `0x18000ad86`
- `CRYPT32!CertFreeCertificateContext` at `0x18000ade0`
- `CRYPT32!CertFreeCertificateContext` at `0x18000ade0`
- `IisRTL!PuDbgPrint` at `0x18000adc1`
- `IisRTL!PuDbgPrint` at `0x18000ae73`
- `IisRTL!PuDbgPrint` at `0x18000adc1`
- `IisRTL!PuDbgPrint` at `0x18000ae73`

## string_xrefs

- `0x18000ada1`: `Invalid cert passed to CreateMapping()\n`
- `0x18000ada8`: `CIISDsCrMap::CreateMapping`
- `0x18000ae5a`: `CIISDsCrMap::CreateMapping`

## pseudocode

```c
__int64 __fastcall CIISDsCrMap::CreateMapping(
        CIISDsCrMap *this,
        VARIANTARG *pvargSrc,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  BOOL v9; // eax
  IRecordInfo *pRecInfo; // xmm1_8
  char *v12; // r15
  int StringFromVariant; // ebx
  BYTE *v14; // r14
  const CERT_CONTEXT *CertificateContext; // rax
  void *v16; // rcx
  IRecordInfo *v17; // xmm1_8
  __int64 (__fastcall *v18)(CIISDsCrMap *, __int64, VARIANTARG *, __int128 *, __int128 *, __int128 *, __int128 *, __int128 *); // rax
  int v19; // eax
  unsigned int v20; // r8d
  IRecordInfo *v21; // xmm1_8
  __int64 (__fastcall *v22)(CIISDsCrMap *, __int64, VARIANTARG *, unsigned __int16 *); // rax
  IRecordInfo *v23; // xmm1_8
  __int64 (__fastcall *v24)(CIISDsCrMap *, __int64, VARIANTARG *, LPCWCH); // rax
  IRecordInfo *v25; // xmm1_8
  __int64 (__fastcall *v26)(CIISDsCrMap *, __int64, VARIANTARG *, unsigned __int16 *); // rax
  IRecordInfo *v27; // xmm1_8
  __int64 (__fastcall *v28)(CIISDsCrMap *, __int64, VARIANTARG *, _QWORD); // rax
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  DWORD cbCertEncoded; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v33; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v34; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v35; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v36[4]; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvargSrca; // [rsp+70h] [rbp-90h] BYREF
  char *v38; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL v40; // [rsp+A0h] [rbp-60h] BYREF
  BYTE *pbCertEncoded; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 *v42; // [rsp+B0h] [rbp-50h] BYREF
  LPCWCH lpWideCharStr; // [rsp+B8h] [rbp-48h]
  __int128 v44; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v45; // [rsp+D0h] [rbp-30h]
  __int128 v46; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v47; // [rsp+E8h] [rbp-18h]
  __int128 v48; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v49; // [rsp+100h] [rbp+0h]
  __int128 v50; // [rsp+108h] [rbp+8h] BYREF
  __int64 v51; // [rsp+118h] [rbp+18h]
  __int128 v52; // [rsp+120h] [rbp+20h] BYREF
  __int64 v53; // [rsp+130h] [rbp+30h]
  wchar_t Buffer[264]; // [rsp+140h] [rbp+40h] BYREF

  lpWideCharStr = a3;
  if ( a3 && a4 && a5 )
  {
    v9 = a6 != 0;
    a6 = v9;
    if ( *((_DWORD *)this + 35) )
    {
      pRecInfo = pvargSrc->pRecInfo;
      *(_OWORD *)&pvargSrca.vt = *(_OWORD *)&pvargSrc->vt;
      pvargSrca.pRecInfo = pRecInfo;
      return CIISDsCrMap::CreateMappingIIS6(this, &pvargSrca, a3, a4, a5, v9);
    }
    pbCertEncoded = 0;
    v51 = 0;
    v53 = 0;
    v49 = 0;
    v47 = 0;
    v45 = 0;
    cbCertEncoded = 0;
    v50 = 0;
    hMem = 0;
    v12 = 0;
    v52 = 0;
    v40 = 0;
    v48 = 0;
    v38 = 0;
    v46 = 0;
    v42 = 0;
    v44 = 0;
    v33 = 0;
    v34 = 0;
    v36[0] = 0;
    v35 = 0;
    StringFromVariant = GetStringFromVariant(pvargSrc, (char **)&pbCertEncoded, &cbCertEncoded, 0);
    if ( StringFromVariant < 0 )
      return (unsigned int)StringFromVariant;
    v14 = pbCertEncoded;
    CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
    if ( !CertificateContext )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\admin\\adsi\\iisext\\crmap.cxx",
          1131,
          "CIISDsCrMap::CreateMapping",
          "Invalid cert passed to CreateMapping()\n");
      StringFromVariant = -2147024809;
      if ( !v14 )
        return (unsigned int)StringFromVariant;
      v16 = v14;
      goto LABEL_46;
    }
    CertFreeCertificateContext(CertificateContext);
    v17 = pvargSrc->pRecInfo;
    v18 = *(__int64 (__fastcall **)(CIISDsCrMap *, __int64, VARIANTARG *, __int128 *, __int128 *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)this + 168LL);
    *(_OWORD *)&pvargSrca.vt = *(_OWORD *)&pvargSrc->vt;
    pvargSrca.pRecInfo = v17;
    v19 = v18(this, 1, &pvargSrca, &v52, &v50, &v48, &v46, &v44);
    StringFromVariant = v19;
    if ( v19 >= 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\admin\\adsi\\iisext\\crmap.cxx",
          1163,
          "CIISDsCrMap::CreateMapping",
          "Replacing old 1-1 cert mapping with new mapping\n");
      v21 = pvargSrc->pRecInfo;
      v22 = *(__int64 (__fastcall **)(CIISDsCrMap *, __int64, VARIANTARG *, unsigned __int16 *))(*(_QWORD *)this + 192LL);
      *(_OWORD *)&pvargSrca.vt = *(_OWORD *)&pvargSrc->vt;
      pvargSrca.pRecInfo = v21;
      StringFromVariant = v22(this, 1, &pvargSrca, a5);
      if ( StringFromVariant < 0 )
        goto LABEL_38;
      v23 = pvargSrc->pRecInfo;
      v24 = *(__int64 (__fastcall **)(CIISDsCrMap *, __int64, VARIANTARG *, LPCWCH))(*(_QWORD *)this + 208LL);
      *(_OWORD *)&pvargSrca.vt = *(_OWORD *)&pvargSrc->vt;
      pvargSrca.pRecInfo = v23;
      StringFromVariant = v24(this, 1, &pvargSrca, lpWideCharStr);
      if ( StringFromVariant < 0 )
        goto LABEL_38;
      v25 = pvargSrc->pRecInfo;
      v26 = *(__int64 (__fastcall **)(CIISDsCrMap *, __int64, VARIANTARG *, unsigned __int16 *))(*(_QWORD *)this + 200LL);
      *(_OWORD *)&pvargSrca.vt = *(_OWORD *)&pvargSrc->vt;
      pvargSrca.pRecInfo = v25;
      StringFromVariant = v26(this, 1, &pvargSrca, a4);
      if ( StringFromVariant < 0 )
        goto LABEL_38;
      v27 = pvargSrc->pRecInfo;
      v28 = *(__int64 (__fastcall **)(CIISDsCrMap *, __int64, VARIANTARG *, _QWORD))(*(_QWORD *)this + 184LL);
      *(_OWORD *)&pvargSrca.vt = *(_OWORD *)&pvargSrc->vt;
      pvargSrca.pRecInfo = v27;
      v29 = v28(this, 1, &pvargSrca, a6);
LABEL_35:
      StringFromVariant = v29;
      goto LABEL_38;
    }
    if ( v19 != -2147024893 )
    {
LABEL_38:
      CIISDsCrMap::CloseMd(this, StringFromVariant >= 0);
      if ( v14 )
        LocalFree(v14);
      if ( hMem )
        LocalFree(hMem);
      if ( v40 )
        LocalFree(v40);
      if ( !v12 )
        return (unsigned int)StringFromVariant;
      v16 = v12;
LABEL_46:
      LocalFree(v16);
      return (unsigned int)StringFromVariant;
    }
    StringFromVariant = CIISDsCrMap::OpenMd(this, L"Cert11", v20);
    if ( StringFromVariant == -2147024893 )
    {
      StringFromVariant = CIISDsCrMap::OpenMd(this, (unsigned __int16 *)&::hMem, v30);
      if ( StringFromVariant < 0 )
        return (unsigned int)StringFromVariant;
      (*(void (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *))(**((_QWORD **)this + 7) + 24LL))(
        *((_QWORD *)this + 7),
        *((unsigned int *)this + 16),
        L"Cert11");
      CIISDsCrMap::CloseMd(this, 0);
      StringFromVariant = CIISDsCrMap::OpenMd(this, L"Cert11", v31);
    }
    if ( StringFromVariant >= 0 )
    {
      StringFromVariant = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *))(**((_QWORD **)this + 7) + 24LL))(
                            *((_QWORD *)this + 7),
                            *((unsigned int *)this + 16),
                            L"mappings/0");
      if ( StringFromVariant < 0 )
        goto LABEL_38;
      StringFromVariant = CIISDsCrMap::GetMdData(this, (unsigned __int16 *)&::hMem, 0x819u, 1u, &v33, &v42);
      if ( StringFromVariant < 0 )
        goto LABEL_38;
      if ( v33 != 4 )
      {
        StringFromVariant = -2147467259;
        goto LABEL_38;
      }
      swprintf_s(Buffer, 0x101u, L"mappings/%u", *(unsigned int *)v42);
      StringFromVariant = GetStringFromBSTR(lpWideCharStr, (char **)&hMem, v36, 1);
      if ( StringFromVariant < 0 )
        goto LABEL_38;
      StringFromVariant = GetStringFromBSTR(a4, (char **)&v40, &v35, 1);
      if ( StringFromVariant < 0 )
        goto LABEL_38;
      StringFromVariant = GetStringFromBSTR(a5, &v38, &v34, 1);
      if ( StringFromVariant < 0
        || (StringFromVariant = CIISDsCrMap::SetMdData(this, Buffer, 0x821u, 1u, 4u, (unsigned __int8 *)&a6),
            StringFromVariant < 0) )
      {
        v12 = v38;
        goto LABEL_38;
      }
      v12 = v38;
      StringFromVariant = CIISDsCrMap::SetMdData(this, Buffer, 0x820u, 2u, v34, (unsigned __int8 *)v38);
      if ( StringFromVariant < 0 )
        goto LABEL_38;
      StringFromVariant = CIISDsCrMap::SetMdData(this, Buffer, 0x82Du, 2u, v35, (unsigned __int8 *)v40);
      if ( StringFromVariant < 0 )
        goto LABEL_38;
      StringFromVariant = CIISDsCrMap::SetMdData(this, Buffer, 0x81Fu, 2u, v36[0], (unsigned __int8 *)hMem);
      if ( StringFromVariant < 0 )
        goto LABEL_38;
      v29 = CIISDsCrMap::SetMdData(this, Buffer, 0x81Eu, 3u, cbCertEncoded, v14);
      goto LABEL_35;
    }
    return (unsigned int)StringFromVariant;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000ac50  push    rbp
0x18000ac52  push    rbx
0x18000ac53  push    rsi
0x18000ac54  push    rdi
0x18000ac55  push    r12
0x18000ac57  push    r13
0x18000ac59  push    r14
0x18000ac5b  push    r15
0x18000ac5d  lea     rbp, [rsp-268h]
0x18000ac65  sub     rsp, 368h
0x18000ac6c  mov     rax, cs:__security_cookie
0x18000ac73  xor     rax, rsp
0x18000ac76  mov     [rbp+2A0h+var_50], rax
0x18000ac7d  mov     r12, [rbp+2A0h+arg_20]
0x18000ac84  xor     r14d, r14d
0x18000ac87  mov     [rbp+2A0h+lpWideCharStr], r8
0x18000ac8b  mov     r13, r9
0x18000ac8e  mov     rsi, rdx
0x18000ac91  mov     rdi, rcx
0x18000ac94  test    r8, r8
0x18000ac97  jz      loc_18000B1FB
0x18000ac9d  test    r9, r9
0x18000aca0  jz      loc_18000B1FB
0x18000aca6  test    r12, r12
0x18000aca9  jz      loc_18000B1FB
0x18000acaf  cmp     dword ptr [rbp+2A0h+arg_28], r14d
0x18000acb6  mov     eax, r14d
0x18000acb9  setnz   al
0x18000acbc  mov     dword ptr [rbp+2A0h+arg_28], eax
0x18000acc2  cmp     [rcx+8Ch], r14d
0x18000acc9  jz      short loc_18000ACF5
0x18000accb  movups  xmm0, xmmword ptr [rdx]
0x18000acce  mov     dword ptr [rsp+3A0h+var_378], eax; int
0x18000acd2  movsd   xmm1, qword ptr [rdx+10h]
0x18000acd7  lea     rdx, [rsp+3A0h+pvargSrc]; pvargSrc
0x18000acdc  movaps  xmmword ptr [rsp+3A0h+pvargSrc], xmm0
0x18000ace1  movsd   qword ptr [rbp+2A0h+pvargSrc+10h], xmm1
0x18000ace6  mov     [rsp+3A0h+var_380], r12; unsigned __int16 *
0x18000aceb  call    ?CreateMappingIIS6@CIISDsCrMap@@AEAAJUtagVARIANT@@PEAG11J@Z; CIISDsCrMap::CreateMappingIIS6(tagVARIANT,ushort *,ushort *,ushort *,long)
0x18000acf0  jmp     loc_18000B200
0x18000acf5  xor     eax, eax
0x18000acf7  mov     [rbp+2A0h+pbCertEncoded], r14
0x18000acfb  xorps   xmm0, xmm0
0x18000acfe  mov     [rbp+2A0h+var_288], rax
0x18000ad02  xorps   xmm1, xmm1
0x18000ad05  mov     [rbp+2A0h+var_270], rax
0x18000ad09  xor     r9d, r9d; int
0x18000ad0c  mov     [rbp+2A0h+var_2A0], rax
0x18000ad10  lea     r8, [rsp+3A0h+cbCertEncoded]; unsigned int *
0x18000ad15  mov     [rbp+2A0h+var_2B8], rax
0x18000ad19  lea     rdx, [rbp+2A0h+pbCertEncoded]; char **
0x18000ad1d  mov     [rbp+2A0h+var_2D0], rax
0x18000ad21  mov     rcx, rsi; pvargSrc
0x18000ad24  mov     [rsp+3A0h+cbCertEncoded], r14d
0x18000ad29  movups  [rbp+2A0h+var_298], xmm0
0x18000ad2d  mov     [rbp+2A0h+hMem], r14
0x18000ad31  mov     r15, r14
0x18000ad34  movups  [rbp+2A0h+var_280], xmm1
0x18000ad38  mov     [rbp+2A0h+var_300], r14
0x18000ad3c  movups  [rbp+2A0h+var_2B0], xmm0
0x18000ad40  mov     [rbp+2A0h+var_310], r14
0x18000ad44  movups  [rbp+2A0h+var_2C8], xmm1
0x18000ad48  mov     [rbp+2A0h+var_2F0], r14
0x18000ad4c  movups  [rbp+2A0h+var_2E0], xmm0
0x18000ad50  mov     [rsp+3A0h+var_34C], r14d
0x18000ad55  mov     [rsp+3A0h+var_348], r14d
0x18000ad5a  mov     [rsp+3A0h+var_340], r14d
0x18000ad5f  mov     [rsp+3A0h+var_344], r14d
0x18000ad64  call    ?GetStringFromVariant@@YAJPEAUtagVARIANT@@PEAPEADPEAKH@Z; GetStringFromVariant(tagVARIANT *,char * *,ulong *,int)
0x18000ad69  mov     ebx, eax
0x18000ad6b  test    eax, eax
0x18000ad6d  js      loc_18000B1F7
0x18000ad73  mov     r14, [rbp+2A0h+pbCertEncoded]
0x18000ad77  mov     ebx, 1
0x18000ad7c  mov     r8d, [rsp+3A0h+cbCertEncoded]; cbCertEncoded
0x18000ad81  mov     rdx, r14; pbCertEncoded
0x18000ad84  mov     ecx, ebx; dwCertEncodingType
0x18000ad86  call    cs:__imp_CertCreateCertificateContext
0x18000ad8c  test    rax, rax
0x18000ad8f  jnz     short loc_18000ADDD
0x18000ad91  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ad98  jz      short loc_18000ADC7
0x18000ad9a  mov     rcx, cs:g_pDebug
0x18000ada1  lea     rax, aInvalidCertPas_0; "Invalid cert passed to CreateMapping()"...
0x18000ada8  lea     r9, aCiisdscrmapCre_0; "CIISDsCrMap::CreateMapping"
0x18000adaf  mov     [rsp+3A0h+var_380], rax
0x18000adb4  mov     r8d, 46Bh
0x18000adba  lea     rdx, aInetsrvIisAdmi; "inetsrv\\iis\\admin\\adsi\\iisext\\crma"...
0x18000adc1  call    cs:__imp_PuDbgPrint
0x18000adc7  mov     ebx, 80070057h
0x18000adcc  test    r14, r14
0x18000adcf  jz      loc_18000B1F7
0x18000add5  mov     rcx, r14
0x18000add8  jmp     loc_18000B1F1
0x18000addd  mov     rcx, rax; pCertContext
0x18000ade0  call    cs:__imp_CertFreeCertificateContext
0x18000ade6  mov     rax, [rdi]
0x18000ade9  lea     rcx, [rbp+2A0h+var_2E0]
0x18000aded  movups  xmm0, xmmword ptr [rsi]
0x18000adf0  lea     r9, [rbp+2A0h+var_280]
0x18000adf4  mov     [rsp+3A0h+var_368], rcx
0x18000adf9  movsd   xmm1, qword ptr [rsi+10h]
0x18000adfe  lea     rcx, [rbp+2A0h+var_2C8]
0x18000ae02  mov     rax, [rax+0A8h]
0x18000ae09  lea     r8, [rsp+3A0h+pvargSrc]
0x18000ae0e  mov     [rsp+3A0h+var_370], rcx
0x18000ae13  mov     edx, ebx
0x18000ae15  lea     rcx, [rbp+2A0h+var_2B0]
0x18000ae19  movaps  xmmword ptr [rsp+3A0h+pvargSrc], xmm0
0x18000ae1e  mov     [rsp+3A0h+var_378], rcx
0x18000ae23  lea     rcx, [rbp+2A0h+var_298]
0x18000ae27  mov     [rsp+3A0h+var_380], rcx
0x18000ae2c  mov     rcx, rdi
0x18000ae2f  movsd   qword ptr [rbp+2A0h+pvargSrc+10h], xmm1
0x18000ae34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae39  mov     ebx, eax
0x18000ae3b  test    eax, eax
0x18000ae3d  js      loc_18000AF63
0x18000ae43  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ae4a  jz      short loc_18000AE79
0x18000ae4c  mov     rcx, cs:g_pDebug
0x18000ae53  lea     rax, aReplacingOld11; "Replacing old 1-1 cert mapping with new"...
0x18000ae5a  lea     r9, aCiisdscrmapCre_0; "CIISDsCrMap::CreateMapping"
0x18000ae61  mov     [rsp+3A0h+var_380], rax
0x18000ae66  mov     r8d, 48Bh
0x18000ae6c  lea     rdx, aInetsrvIisAdmi; "inetsrv\\iis\\admin\\adsi\\iisext\\crma"...
0x18000ae73  call    cs:__imp_PuDbgPrint
0x18000ae79  mov     rax, [rdi]
0x18000ae7c  lea     r8, [rsp+3A0h+pvargSrc]
0x18000ae81  movups  xmm0, xmmword ptr [rsi]
0x18000ae84  mov     r9, r12
0x18000ae87  mov     r12d, 1
0x18000ae8d  movsd   xmm1, qword ptr [rsi+10h]
0x18000ae92  mov     edx, r12d
0x18000ae95  mov     rax, [rax+0C0h]
0x18000ae9c  mov     rcx, rdi
0x18000ae9f  movaps  xmmword ptr [rsp+3A0h+pvargSrc], xmm0
0x18000aea4  movsd   qword ptr [rbp+2A0h+pvargSrc+10h], xmm1
0x18000aea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeae  mov     ebx, eax
0x18000aeb0  test    eax, eax
0x18000aeb2  js      loc_18000B1AE
0x18000aeb8  mov     rax, [rdi]
0x18000aebb  lea     r8, [rsp+3A0h+pvargSrc]
0x18000aec0  movups  xmm0, xmmword ptr [rsi]
0x18000aec3  mov     edx, r12d
0x18000aec6  mov     r9, [rbp+2A0h+lpWideCharStr]
0x18000aeca  movsd   xmm1, qword ptr [rsi+10h]
0x18000aecf  mov     rcx, rdi
0x18000aed2  mov     rax, [rax+0D0h]
0x18000aed9  movaps  xmmword ptr [rsp+3A0h+pvargSrc], xmm0
0x18000aede  movsd   qword ptr [rbp+2A0h+pvargSrc+10h], xmm1
0x18000aee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee8  mov     ebx, eax
0x18000aeea  test    eax, eax
0x18000aeec  js      loc_18000B1AE
0x18000aef2  mov     rax, [rdi]
0x18000aef5  lea     r8, [rsp+3A0h+pvargSrc]
0x18000aefa  movups  xmm0, xmmword ptr [rsi]
0x18000aefd  mov     r9, r13
0x18000af00  mov     edx, r12d
0x18000af03  movsd   xmm1, qword ptr [rsi+10h]
0x18000af08  mov     rcx, rdi
0x18000af0b  mov     rax, [rax+0C8h]
0x18000af12  movaps  xmmword ptr [rsp+3A0h+pvargSrc], xmm0
0x18000af17  movsd   qword ptr [rbp+2A0h+pvargSrc+10h], xmm1
0x18000af1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af21  mov     ebx, eax
0x18000af23  test    eax, eax
0x18000af25  js      loc_18000B1AE
0x18000af2b  mov     rax, [rdi]
0x18000af2e  lea     r8, [rsp+3A0h+pvargSrc]
0x18000af33  movups  xmm0, xmmword ptr [rsi]
0x18000af36  mov     edx, r12d
0x18000af39  mov     r9d, dword ptr [rbp+2A0h+arg_28]
0x18000af40  movsd   xmm1, qword ptr [rsi+10h]
0x18000af45  mov     rcx, rdi
0x18000af48  mov     rax, [rax+0B8h]
0x18000af4f  movaps  xmmword ptr [rsp+3A0h+pvargSrc], xmm0
0x18000af54  movsd   qword ptr [rbp+2A0h+pvargSrc+10h], xmm1
0x18000af59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af5e  jmp     loc_18000B19F
0x18000af63  mov     esi, 80070003h
0x18000af68  cmp     eax, esi
0x18000af6a  jnz     loc_18000B1AE
0x18000af70  lea     rdx, aCert11; "Cert11"
0x18000af77  mov     rcx, rdi; this
0x18000af7a  call    ?OpenMd@CIISDsCrMap@@QEAAJPEAGK@Z; CIISDsCrMap::OpenMd(ushort *,ulong)
0x18000af7f  mov     ebx, eax
0x18000af81  cmp     eax, esi
0x18000af83  jnz     short loc_18000AFD3
0x18000af85  lea     rdx, hMem; unsigned __int16 *
0x18000af8c  mov     rcx, rdi; this
0x18000af8f  call    ?OpenMd@CIISDsCrMap@@QEAAJPEAGK@Z; CIISDsCrMap::OpenMd(ushort *,ulong)
0x18000af94  mov     ebx, eax
0x18000af96  test    eax, eax
0x18000af98  js      loc_18000B1F7
0x18000af9e  mov     rcx, [rdi+38h]
0x18000afa2  lea     r8, aCert11; "Cert11"
0x18000afa9  mov     edx, [rdi+40h]
0x18000afac  mov     rax, [rcx]
0x18000afaf  mov     rax, [rax+18h]
0x18000afb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afb8  xor     edx, edx; int
0x18000afba  mov     rcx, rdi; this
0x18000afbd  call    ?CloseMd@CIISDsCrMap@@QEAAJH@Z; CIISDsCrMap::CloseMd(int)
0x18000afc2  lea     rdx, aCert11; "Cert11"
0x18000afc9  mov     rcx, rdi; this
0x18000afcc  call    ?OpenMd@CIISDsCrMap@@QEAAJPEAGK@Z; CIISDsCrMap::OpenMd(ushort *,ulong)
0x18000afd1  mov     ebx, eax
0x18000afd3  test    ebx, ebx
0x18000afd5  js      loc_18000B1F7
0x18000afdb  mov     rcx, [rdi+38h]
0x18000afdf  lea     r8, aMappings0; "mappings/0"
0x18000afe6  mov     edx, [rdi+40h]
0x18000afe9  mov     rax, [rcx]
0x18000afec  mov     rax, [rax+18h]
0x18000aff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aff5  mov     ebx, eax
0x18000aff7  test    eax, eax
0x18000aff9  js      loc_18000B1AE
0x18000afff  lea     rax, [rbp+2A0h+var_2F0]
0x18000b003  mov     esi, 1
0x18000b008  mov     [rsp+3A0h+var_378], rax; unsigned __int8 **
0x18000b00d  lea     rdx, hMem; unsigned __int16 *
0x18000b014  lea     rax, [rsp+3A0h+var_34C]
0x18000b019  mov     r9d, esi; unsigned int
0x18000b01c  mov     r8d, 819h; unsigned int
0x18000b022  mov     [rsp+3A0h+var_380], rax; unsigned int *
0x18000b027  mov     rcx, rdi; this
0x18000b02a  call    ?GetMdData@CIISDsCrMap@@QEAAJPEAGKKPEAKPEAPEAE@Z; CIISDsCrMap::GetMdData(ushort *,ulong,ulong,ulong *,uchar * *)
0x18000b02f  mov     ebx, eax
0x18000b031  test    eax, eax
0x18000b033  js      loc_18000B1AE
0x18000b039  cmp     [rsp+3A0h+var_34C], 4
0x18000b03e  jnz     loc_18000B1A9
0x18000b044  mov     r9, [rbp+2A0h+var_2F0]
0x18000b048  lea     r8, aMappingsU; "mappings/%u"
0x18000b04f  mov     edx, 101h; BufferCount
0x18000b054  lea     rcx, [rbp+2A0h+Buffer]; Buffer
0x18000b058  mov     r9d, [r9]
0x18000b05b  call    cs:__imp_swprintf_s
0x18000b061  mov     rcx, [rbp+2A0h+lpWideCharStr]; lpWideCharStr
0x18000b065  lea     r8, [rsp+3A0h+var_340]; unsigned int *
0x18000b06a  mov     r9d, esi; int
0x18000b06d  lea     rdx, [rbp+2A0h+hMem]; char **
0x18000b071  call    ?GetStringFromBSTR@@YAJPEAGPEAPEADPEAKH@Z; GetStringFromBSTR(ushort *,char * *,ulong *,int)
0x18000b076  mov     ebx, eax
0x18000b078  test    eax, eax
0x18000b07a  js      loc_18000B1AE
0x18000b080  mov     r9d, esi; int
0x18000b083  lea     r8, [rsp+3A0h+var_344]; unsigned int *
0x18000b088  lea     rdx, [rbp+2A0h+var_300]; char **
0x18000b08c  mov     rcx, r13; lpWideCharStr
0x18000b08f  call    ?GetStringFromBSTR@@YAJPEAGPEAPEADPEAKH@Z; GetStringFromBSTR(ushort *,char * *,ulong *,int)
0x18000b094  mov     ebx, eax
0x18000b096  test    eax, eax
0x18000b098  js      loc_18000B1AE
0x18000b09e  mov     r9d, esi; int
0x18000b0a1  lea     r8, [rsp+3A0h+var_348]; unsigned int *
0x18000b0a6  lea     rdx, [rbp+2A0h+var_310]; char **
0x18000b0aa  mov     rcx, r12; lpWideCharStr
0x18000b0ad  call    ?GetStringFromBSTR@@YAJPEAGPEAPEADPEAKH@Z; GetStringFromBSTR(ushort *,char * *,ulong *,int)
0x18000b0b2  mov     ebx, eax
0x18000b0b4  test    eax, eax
0x18000b0b6  js      loc_18000B1A3
0x18000b0bc  lea     rax, [rbp+2A0h+arg_28]
0x18000b0c3  mov     r9d, esi; unsigned int
0x18000b0c6  mov     [rsp+3A0h+var_378], rax; unsigned __int8 *
0x18000b0cb  lea     rdx, [rbp+2A0h+Buffer]; unsigned __int16 *
0x18000b0cf  mov     r8d, 821h; unsigned int
0x18000b0d5  mov     dword ptr [rsp+3A0h+var_380], 4; unsigned int
0x18000b0dd  mov     rcx, rdi; this
0x18000b0e0  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000b0e5  mov     ebx, eax
0x18000b0e7  test    eax, eax
0x18000b0e9  js      loc_18000B1A3
0x18000b0ef  mov     eax, [rsp+3A0h+var_348]
0x18000b0f3  lea     rdx, [rbp+2A0h+Buffer]; unsigned __int16 *
0x18000b0f7  mov     r15, [rbp+2A0h+var_310]
0x18000b0fb  mov     esi, 2
0x18000b100  mov     [rsp+3A0h+var_378], r15; unsigned __int8 *
0x18000b105  mov     r9d, esi; unsigned int
0x18000b108  mov     r8d, 820h; unsigned int
0x18000b10e  mov     dword ptr [rsp+3A0h+var_380], eax; unsigned int
0x18000b112  mov     rcx, rdi; this
0x18000b115  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000b11a  mov     ebx, eax
0x18000b11c  test    eax, eax
0x18000b11e  js      loc_18000B1AE
0x18000b124  mov     rax, [rbp+2A0h+var_300]
0x18000b128  lea     rdx, [rbp+2A0h+Buffer]; unsigned __int16 *
0x18000b12c  mov     [rsp+3A0h+var_378], rax; unsigned __int8 *
0x18000b131  mov     r9d, esi; unsigned int
0x18000b134  mov     eax, [rsp+3A0h+var_344]
0x18000b138  mov     r8d, 82Dh; unsigned int
0x18000b13e  mov     rcx, rdi; this
0x18000b141  mov     dword ptr [rsp+3A0h+var_380], eax; unsigned int
0x18000b145  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000b14a  mov     ebx, eax
  ... truncated ...
```
