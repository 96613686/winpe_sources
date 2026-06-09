# DoAddSmartCard(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180005850`
- end: `0x180005b53`
- name: `?DoAddSmartCard@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `771`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x180005850`
- `0x18000f370`
- `0x18000f780`
- `0x18000f830`

## import_xrefs

- `FVEAPI!FveCloseVolume` at `0x180005962`
- `FVEAPI!FveCloseVolume` at `0x180005b16`
- `FVEAPI!FveCloseVolume` at `0x180005962`
- `FVEAPI!FveCloseVolume` at `0x180005b16`
- `FVEAPI!FveCommitChanges` at `0x180005abe`
- `FVEAPI!FveCommitChanges` at `0x180005abe`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180005aad`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180005aad`
- `FVEAPI!FveOpenVolumeW` at `0x180005904`
- `FVEAPI!FveOpenVolumeW` at `0x180005a90`
- `FVEAPI!FveOpenVolumeW` at `0x180005904`
- `FVEAPI!FveOpenVolumeW` at `0x180005a90`
- `FVEAPI!FveGetStatus` at `0x180005934`
- `FVEAPI!FveGetStatus` at `0x180005934`
- `FVECERTS!FveCertGetPublicKeyHandle` at `0x1800059f3`
- `FVECERTS!FveCertGetPublicKeyHandle` at `0x1800059f3`
- `FVECERTS!FveCertFreeCertInfo` at `0x180005ad7`
- `FVECERTS!FveCertFreeCertInfo` at `0x180005ad7`
- `FVECERTS!FveCertCreateCertInfo` at `0x180005a0d`
- `FVECERTS!FveCertCreateCertInfo` at `0x180005a0d`
- `CRYPT32!CertFreeCertificateContext` at `0x180005ae5`
- `CRYPT32!CertFreeCertificateContext` at `0x180005ae5`
- `CRYPT32!CertCloseStore` at `0x1800059a3`
- `CRYPT32!CertCloseStore` at `0x180005b05`
- `CRYPT32!CertCloseStore` at `0x1800059a3`
- `CRYPT32!CertCloseStore` at `0x180005b05`
- `ncrypt!BCryptDestroyKey` at `0x180005af5`
- `ncrypt!BCryptDestroyKey` at `0x180005af5`

## pseudocode

```c
__int64 __fastcall DoAddSmartCard(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  HCERTSTORE v2; // rsi
  const CERT_CONTEXT *v5; // rdi
  VARIANTARG *rgvarg; // rcx
  LONG Status; // ebx
  HWND lVal; // rsi
  HWND v9; // rdx
  int v10; // eax
  VARIANTARG *v11; // rcx
  __int64 result; // rax
  __int64 v13; // [rsp+20h] [rbp-E0h] BYREF
  HCERTSTORE hCertStore; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  const CERT_CONTEXT *v16; // [rsp+38h] [rbp-C8h]
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v19; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v21; // [rsp+68h] [rbp-98h]
  __int128 v22; // [rsp+78h] [rbp-88h]
  __int64 v23; // [rsp+88h] [rbp-78h]
  _DWORD v24[4]; // [rsp+90h] [rbp-70h] BYREF
  BCRYPT_KEY_HANDLE v25; // [rsp+A0h] [rbp-60h]
  int v26; // [rsp+A8h] [rbp-58h]
  __int64 v27; // [rsp+B0h] [rbp-50h]
  __int128 v28; // [rsp+2E0h] [rbp+1E0h] BYREF
  _DWORD v29[2]; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int16 v30; // [rsp+2F8h] [rbp+1F8h]

  v2 = 0;
  hCertStore = 0;
  hKey = 0;
  v5 = 0;
  v13 = -1;
  v16 = 0;
  v17 = 0;
  memset_0(v24, 0, 0x248u);
  v19 = 0;
  v23 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v28 = 0;
  memset_0(v29, 0, 0x90u);
  rgvarg = a1->rgvarg;
  v15 = 0;
  Status = FveOpenVolumeW(rgvarg->llVal, 0, &v13);
  if ( Status >= 0 )
  {
    v29[0] = 144;
    v29[1] = 10;
    Status = FveGetStatus(v13, v29);
    if ( Status >= 0 )
    {
      if ( v30 == 2 )
      {
        if ( v13 != -1 )
        {
          FveCloseVolume();
          v13 = -1;
        }
        lVal = (HWND)a1->rgvarg[1].lVal;
        Status = FveuiEnumSmartCardCerts(0, &hCertStore, &v15);
        if ( Status < 0
          || v15 > 1
          && (CertCloseStore(hCertStore, 0),
              hCertStore = 0,
              Status = FveuiUserSelectSmartCard(lVal, 0, &hCertStore),
              Status < 0) )
        {
          v2 = hCertStore;
        }
        else
        {
          v9 = lVal;
          v2 = hCertStore;
          v10 = FveuiUserSelectCert(hCertStore, v9);
          v5 = v16;
          Status = v10;
          if ( v10 >= 0 )
          {
            Status = FveCertGetPublicKeyHandle(v16, &hKey);
            if ( Status >= 0 )
            {
              Status = FveCertCreateCertInfo(v5, 0, &v17);
              if ( Status >= 0 )
              {
                v11 = a1->rgvarg;
                v25 = hKey;
                v27 = v17;
                v24[0] = 40;
                v24[1] = 1;
                v24[3] = 5;
                v24[2] = 1;
                v26 = *(_DWORD *)(v17 + 4);
                v19 = v24;
                v21 = (unsigned __int64)&v19;
                *(_QWORD *)&v20 = 0x100000038LL;
                *((_QWORD *)&v20 + 1) = 0x100200000LL;
                Status = FveOpenVolumeW(v11->llVal, 1, &v13);
                if ( Status >= 0 )
                {
                  Status = FveAddAuthMethodInformation(v13, &v20, &v28);
                  if ( Status >= 0 )
                    Status = FveCommitChanges(v13);
                }
              }
            }
          }
        }
      }
      else
      {
        Status = -2144272279;
      }
    }
  }
  if ( v17 )
    FveCertFreeCertInfo();
  if ( v5 )
    CertFreeCertificateContext(v5);
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( v2 )
    CertCloseStore(v2, 0);
  if ( v13 != -1 )
    FveCloseVolume();
  a2->vt = 19;
  result = (unsigned int)Status;
  a2->lVal = Status;
  return result;
}

```

## disassembly

```asm
0x180005850  mov     [rsp-8+arg_10], rbx
0x180005855  mov     [rsp-8+arg_18], rsi
0x18000585a  push    rbp
0x18000585b  push    rdi
0x18000585c  push    r13
0x18000585e  push    r14
0x180005860  push    r15
0x180005862  lea     rbp, [rsp-290h]
0x18000586a  sub     rsp, 390h
0x180005871  mov     rax, cs:__security_cookie
0x180005878  xor     rax, rsp
0x18000587b  mov     [rbp+2B0h+var_30], rax
0x180005882  xor     esi, esi
0x180005884  mov     r14, rdx
0x180005887  mov     r15, rcx
0x18000588a  mov     [rsp+3B0h+hCertStore], rsi
0x18000588f  or      r13, 0FFFFFFFFFFFFFFFFh
0x180005893  mov     [rsp+3B0h+hKey], rsi
0x180005898  xor     edi, edi
0x18000589a  mov     [rsp+3B0h+var_390], r13
0x18000589f  xor     edx, edx; Val
0x1800058a1  mov     [rsp+3B0h+var_378], rdi
0x1800058a6  lea     rcx, [rbp+2B0h+var_320]; void *
0x1800058aa  mov     [rsp+3B0h+var_370], rsi
0x1800058af  mov     r8d, 248h; Size
0x1800058b5  call    memset_0
0x1800058ba  xorps   xmm0, xmm0
0x1800058bd  mov     [rsp+3B0h+var_360], rsi
0x1800058c2  xor     eax, eax
0x1800058c4  lea     rcx, [rbp+2B0h+var_C0]; void *
0x1800058cb  xor     edx, edx; Val
0x1800058cd  mov     [rbp+2B0h+var_328], rax
0x1800058d1  mov     r8d, 90h; Size
0x1800058d7  movups  [rsp+3B0h+var_358], xmm0
0x1800058dc  movups  [rsp+3B0h+var_348], xmm0
0x1800058e1  movups  [rsp+3B0h+var_338], xmm0
0x1800058e6  movups  [rbp+2B0h+var_D0], xmm0
0x1800058ed  call    memset_0
0x1800058f2  mov     rcx, [r15]
0x1800058f5  lea     r8, [rsp+3B0h+var_390]
0x1800058fa  xor     edx, edx
0x1800058fc  mov     [rsp+3B0h+var_380], esi
0x180005900  mov     rcx, [rcx+8]
0x180005904  call    cs:__imp_FveOpenVolumeW
0x18000590a  mov     ebx, eax
0x18000590c  test    eax, eax
0x18000590e  js      loc_180005ACD
0x180005914  mov     rcx, [rsp+3B0h+var_390]
0x180005919  lea     rdx, [rbp+2B0h+var_C0]
0x180005920  mov     [rbp+2B0h+var_C0], 90h
0x18000592a  mov     [rbp+2B0h+var_BC], 0Ah
0x180005934  call    cs:__imp_FveGetStatus
0x18000593a  mov     ebx, eax
0x18000593c  test    eax, eax
0x18000593e  js      loc_180005ACD
0x180005944  cmp     [rbp+2B0h+var_B8], 2
0x18000594c  jz      short loc_180005958
0x18000594e  mov     ebx, 80310069h
0x180005953  jmp     loc_180005ACD
0x180005958  mov     rcx, [rsp+3B0h+var_390]
0x18000595d  cmp     rcx, r13
0x180005960  jz      short loc_18000596D
0x180005962  call    cs:__imp_FveCloseVolume
0x180005968  mov     [rsp+3B0h+var_390], r13
0x18000596d  mov     rax, [r15]
0x180005970  lea     r8, [rsp+3B0h+var_380]
0x180005975  lea     rdx, [rsp+3B0h+hCertStore]
0x18000597a  xor     ecx, ecx
0x18000597c  movsxd  rsi, dword ptr [rax+20h]
0x180005980  call    FveuiEnumSmartCardCerts
0x180005985  mov     ebx, eax
0x180005987  test    eax, eax
0x180005989  js      loc_180005AC8
0x18000598f  mov     r13d, 1
0x180005995  cmp     [rsp+3B0h+var_380], r13d
0x18000599a  jbe     short loc_1800059C7
0x18000599c  mov     rcx, [rsp+3B0h+hCertStore]; hCertStore
0x1800059a1  xor     edx, edx; dwFlags
0x1800059a3  call    cs:__imp_CertCloseStore
0x1800059a9  lea     r8, [rsp+3B0h+hCertStore]
0x1800059ae  mov     [rsp+3B0h+hCertStore], rdi
0x1800059b3  xor     edx, edx
0x1800059b5  mov     rcx, rsi
0x1800059b8  call    FveuiUserSelectSmartCard
0x1800059bd  mov     ebx, eax
0x1800059bf  test    eax, eax
0x1800059c1  js      loc_180005AC8
0x1800059c7  mov     rdx, rsi; hwnd
0x1800059ca  lea     r8, [rsp+3B0h+var_378]
0x1800059cf  mov     rsi, [rsp+3B0h+hCertStore]
0x1800059d4  mov     rcx, rsi; hCertStore
0x1800059d7  call    FveuiUserSelectCert
0x1800059dc  mov     rdi, [rsp+3B0h+var_378]
0x1800059e1  mov     ebx, eax
0x1800059e3  test    eax, eax
0x1800059e5  js      loc_180005ACD
0x1800059eb  lea     rdx, [rsp+3B0h+hKey]
0x1800059f0  mov     rcx, rdi
0x1800059f3  call    cs:__imp_FveCertGetPublicKeyHandle
0x1800059f9  mov     ebx, eax
0x1800059fb  test    eax, eax
0x1800059fd  js      loc_180005ACD
0x180005a03  lea     r8, [rsp+3B0h+var_370]
0x180005a08  xor     edx, edx
0x180005a0a  mov     rcx, rdi
0x180005a0d  call    cs:__imp_FveCertCreateCertInfo
0x180005a13  mov     ebx, eax
0x180005a15  test    eax, eax
0x180005a17  js      loc_180005ACD
0x180005a1d  mov     rax, [rsp+3B0h+hKey]
0x180005a22  lea     r8, [rsp+3B0h+var_390]
0x180005a27  mov     rcx, [r15]
0x180005a2a  mov     edx, r13d
0x180005a2d  mov     [rbp+2B0h+var_310], rax
0x180005a31  mov     rax, [rsp+3B0h+var_370]
0x180005a36  mov     [rbp+2B0h+var_300], rax
0x180005a3a  mov     [rbp+2B0h+var_320], 28h ; '('
0x180005a41  mov     [rbp+2B0h+var_31C], r13d
0x180005a45  mov     [rbp+2B0h+var_314], 5
0x180005a4c  mov     [rbp+2B0h+var_318], r13d
0x180005a50  mov     eax, [rax+4]
0x180005a53  mov     [rbp+2B0h+var_308], eax
0x180005a56  lea     rax, [rbp+2B0h+var_320]
0x180005a5a  mov     [rsp+3B0h+var_360], rax
0x180005a5f  lea     rax, [rsp+3B0h+var_360]
0x180005a64  mov     qword ptr [rsp+3B0h+var_348], rax
0x180005a69  mov     dword ptr [rsp+3B0h+var_358], 38h ; '8'
0x180005a71  mov     dword ptr [rsp+3B0h+var_358+4], r13d
0x180005a76  mov     dword ptr [rsp+3B0h+var_358+8], 200000h
0x180005a7e  mov     dword ptr [rsp+3B0h+var_358+0Ch], r13d
0x180005a83  mov     qword ptr [rsp+3B0h+var_348+8], 0
0x180005a8c  mov     rcx, [rcx+8]
0x180005a90  call    cs:__imp_FveOpenVolumeW
0x180005a96  mov     ebx, eax
0x180005a98  test    eax, eax
0x180005a9a  js      short loc_180005ACD
0x180005a9c  mov     rcx, [rsp+3B0h+var_390]
0x180005aa1  lea     r8, [rbp+2B0h+var_D0]
0x180005aa8  lea     rdx, [rsp+3B0h+var_358]
0x180005aad  call    cs:__imp_FveAddAuthMethodInformation
0x180005ab3  mov     ebx, eax
0x180005ab5  test    eax, eax
0x180005ab7  js      short loc_180005ACD
0x180005ab9  mov     rcx, [rsp+3B0h+var_390]
0x180005abe  call    cs:__imp_FveCommitChanges
0x180005ac4  mov     ebx, eax
0x180005ac6  jmp     short loc_180005ACD
0x180005ac8  mov     rsi, [rsp+3B0h+hCertStore]
0x180005acd  mov     rcx, [rsp+3B0h+var_370]
0x180005ad2  test    rcx, rcx
0x180005ad5  jz      short loc_180005ADD
0x180005ad7  call    cs:__imp_FveCertFreeCertInfo
0x180005add  test    rdi, rdi
0x180005ae0  jz      short loc_180005AEB
0x180005ae2  mov     rcx, rdi; pCertContext
0x180005ae5  call    cs:__imp_CertFreeCertificateContext
0x180005aeb  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180005af0  test    rcx, rcx
0x180005af3  jz      short loc_180005AFB
0x180005af5  call    cs:__imp_BCryptDestroyKey
0x180005afb  test    rsi, rsi
0x180005afe  jz      short loc_180005B0B
0x180005b00  xor     edx, edx; dwFlags
0x180005b02  mov     rcx, rsi; hCertStore
0x180005b05  call    cs:__imp_CertCloseStore
0x180005b0b  mov     rcx, [rsp+3B0h+var_390]
0x180005b10  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005b14  jz      short loc_180005B1C
0x180005b16  call    cs:__imp_FveCloseVolume
0x180005b1c  mov     word ptr [r14], 13h
0x180005b22  mov     eax, ebx
0x180005b24  mov     [r14+8], ebx
0x180005b28  mov     rcx, [rbp+2B0h+var_30]
0x180005b2f  xor     rcx, rsp; StackCookie
0x180005b32  call    __security_check_cookie
0x180005b37  lea     r11, [rsp+3B0h+var_20]
0x180005b3f  mov     rbx, [r11+40h]
0x180005b43  mov     rsi, [r11+48h]
0x180005b47  mov     rsp, r11
0x180005b4a  pop     r15
0x180005b4c  pop     r14
0x180005b4e  pop     r13
0x180005b50  pop     rdi
0x180005b51  pop     rbp
0x180005b52  retn
```
