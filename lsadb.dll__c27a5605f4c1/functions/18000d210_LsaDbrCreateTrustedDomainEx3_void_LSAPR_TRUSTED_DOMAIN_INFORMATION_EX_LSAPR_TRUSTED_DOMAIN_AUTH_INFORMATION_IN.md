# LsaDbrCreateTrustedDomainEx3(void *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *,_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *,ulong,void * *)

- ea: `0x18000d210`
- end: `0x18000d3dc`
- name: `?LsaDbrCreateTrustedDomainEx3@@YAJPEAXPEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@PEAU_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES@@KPEAPEAX@Z`
- size: `460`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *@<rdx>, struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *@<r8>, unsigned int@<r9d>, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18000a080`
- `0x18000a2bc`
- `0x18000bd80`
- `0x18000d210`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fd80`
- `0x180016e14`
- `0x180018fa4`
- `0x1800356a0`
- `0x180035d6c`
- `0x180035ee0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d2d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d389`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d2d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d389`
- `LSASRV!LsapCrServerGetSessionKeySafe` at `0x18000d333`
- `LSASRV!LsapCrServerGetSessionKeySafe` at `0x18000d333`

## pseudocode

```c
__int64 __fastcall LsaDbrCreateTrustedDomainEx3(
        _BYTE *a1,
        struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *a2,
        struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *a3,
        int a4,
        void **a5)
{
  void *v9; // rcx
  HLOCAL v10; // rbx
  const wchar_t *v11; // r9
  int TrustedDomain2; // ebx
  unsigned __int8 v14[8]; // [rsp+30h] [rbp-31h] BYREF
  HLOCAL v15; // [rsp+38h] [rbp-29h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-21h] BYREF
  struct _TRUSTED_DOMAIN_AUTH_INFORMATION v17; // [rsp+48h] [rbp-19h] BYREF

  v15 = 0;
  memset(&v17, 0, sizeof(v17));
  v14[0] = 0;
  hMem = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      LsaDbGetCallerInfo(v9, (unsigned __int16 **)&hMem);
      v10 = hMem;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        v11 = L"Unknown";
        if ( hMem )
          v11 = (const wchar_t *)hMem;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids, v11);
      }
      LocalFree(v10);
    }
  }
  memset(&v17, 0, sizeof(v17));
  if ( LsaDbpValidateTrustedDomainInformationEx((struct _TRUSTED_DOMAIN_INFORMATION_EX *)a2)
    && LsaDbpValidateLsaprTrustedDomainAuthInformationInternalAes(a3) )
  {
    TrustedDomain2 = LsaDbpCheckIfCallerHasAccessToTDOs(a1);
    if ( TrustedDomain2 >= 0 )
    {
      TrustedDomain2 = LsaDbpIsCallLocal(v14);
      if ( TrustedDomain2 >= 0 )
      {
        if ( v14[0] || (TrustedDomain2 = LsapCrServerGetSessionKeySafe(a1, 1, &v15), TrustedDomain2 >= 0) )
        {
          TrustedDomain2 = LsaDbpDecryptAuthDataWithSessionKeyAes((unsigned __int8 **)v15, v14[0], a3, &v17);
          if ( TrustedDomain2 >= 0 )
            TrustedDomain2 = LsaDbpCreateTrustedDomain2(
                               a1,
                               a2,
                               (struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION *)&v17,
                               a4 | 0x20u,
                               a5);
        }
      }
    }
  }
  else
  {
    TrustedDomain2 = -1073741811;
  }
  if ( v15 )
    LocalFree(v15);
  LsaDbpDsFreeUnmarshalAuthInfoHalf((struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)&v17);
  LsaDbpDsFreeUnmarshalAuthInfoHalf((struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)&v17.OutgoingAuthInfos);
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids,
      (unsigned int)TrustedDomain2);
  return (unsigned int)TrustedDomain2;
}

```

## disassembly

```asm
0x18000d210  push    rbp
0x18000d212  push    rbx
0x18000d213  push    rsi
0x18000d214  push    r12
0x18000d216  push    r14
0x18000d218  push    r15
0x18000d21a  lea     rbp, [rsp-27h]
0x18000d21f  sub     rsp, 88h
0x18000d226  xorps   xmm0, xmm0
0x18000d229  mov     [rbp+4Fh+var_78], 0
0x18000d231  movups  xmmword ptr [rbp+4Fh+var_68.IncomingAuthInfos], xmm0
0x18000d235  mov     r15d, r9d
0x18000d238  mov     r14, r8
0x18000d23b  movups  xmmword ptr [rbp+4Fh+var_68.IncomingPreviousAuthenticationInformation], xmm0
0x18000d23f  mov     r12, rdx
0x18000d242  mov     rsi, rcx
0x18000d245  movups  xmmword ptr [rbp+4Fh+var_68.OutgoingAuthenticationInformation], xmm0
0x18000d249  mov     [rbp+4Fh+var_80], 0
0x18000d24d  mov     [rbp+4Fh+hMem], 0
0x18000d255  mov     rax, cs:WPP_GLOBAL_Control
0x18000d25c  test    dword ptr [rax+1Ch], 100h
0x18000d263  jz      short loc_18000D2D9
0x18000d265  mov     rcx, [rax+10h]
0x18000d269  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000d270  mov     edx, 35h ; '5'
0x18000d275  call    WPP_SF_
0x18000d27a  mov     rax, cs:WPP_GLOBAL_Control
0x18000d281  test    dword ptr [rax+1Ch], 100h
0x18000d288  jz      short loc_18000D2D9
0x18000d28a  cmp     byte ptr [rax+19h], 4
0x18000d28e  jb      short loc_18000D2D9
0x18000d290  lea     rdx, [rbp+4Fh+hMem]; unsigned __int16 **
0x18000d294  call    ?LsaDbGetCallerInfo@@YAXPEAXPEAPEAG@Z; LsaDbGetCallerInfo(void *,ushort * *)
0x18000d299  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2a0  mov     rbx, [rbp+4Fh+hMem]
0x18000d2a4  test    dword ptr [rcx+1Ch], 100h
0x18000d2ab  jz      short loc_18000D2D0
0x18000d2ad  mov     rcx, [rcx+10h]
0x18000d2b1  lea     r9, aUnknown_0; "Unknown"
0x18000d2b8  test    rbx, rbx
0x18000d2bb  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000d2c2  mov     edx, 36h ; '6'
0x18000d2c7  cmovnz  r9, rbx
0x18000d2cb  call    WPP_SF_S
0x18000d2d0  mov     rcx, rbx; hMem
0x18000d2d3  call    cs:__imp_LocalFree
0x18000d2d9  xorps   xmm0, xmm0
0x18000d2dc  mov     rcx, r12; struct _TRUSTED_DOMAIN_INFORMATION_EX *
0x18000d2df  movups  xmmword ptr [rbp+4Fh+var_68.IncomingAuthInfos], xmm0
0x18000d2e3  movups  xmmword ptr [rbp+4Fh+var_68.IncomingPreviousAuthenticationInformation], xmm0
0x18000d2e7  movups  xmmword ptr [rbp+4Fh+var_68.OutgoingAuthenticationInformation], xmm0
0x18000d2eb  call    ?LsaDbpValidateTrustedDomainInformationEx@@YAEPEAU_TRUSTED_DOMAIN_INFORMATION_EX@@@Z; LsaDbpValidateTrustedDomainInformationEx(_TRUSTED_DOMAIN_INFORMATION_EX *)
0x18000d2f0  test    al, al
0x18000d2f2  jz      loc_18000D37B
0x18000d2f8  mov     rcx, r14; struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *
0x18000d2fb  call    ?LsaDbpValidateLsaprTrustedDomainAuthInformationInternalAes@@YAEPEAU_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES@@@Z; LsaDbpValidateLsaprTrustedDomainAuthInformationInternalAes(_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *)
0x18000d300  test    al, al
0x18000d302  jz      short loc_18000D37B
0x18000d304  mov     rcx, rsi; void *
0x18000d307  call    ?LsaDbpCheckIfCallerHasAccessToTDOs@@YAJQEAX@Z; LsaDbpCheckIfCallerHasAccessToTDOs(void * const)
0x18000d30c  mov     ebx, eax
0x18000d30e  test    eax, eax
0x18000d310  js      short loc_18000D380
0x18000d312  lea     rcx, [rbp+4Fh+var_80]; unsigned __int8 *
0x18000d316  call    ?LsaDbpIsCallLocal@@YAJPEAE@Z; LsaDbpIsCallLocal(uchar *)
0x18000d31b  mov     ebx, eax
0x18000d31d  test    eax, eax
0x18000d31f  js      short loc_18000D380
0x18000d321  cmp     [rbp+4Fh+var_80], 0
0x18000d325  jnz     short loc_18000D33F
0x18000d327  lea     r8, [rbp+4Fh+var_78]
0x18000d32b  mov     edx, 1
0x18000d330  mov     rcx, rsi
0x18000d333  call    cs:__imp_LsapCrServerGetSessionKeySafe
0x18000d339  mov     ebx, eax
0x18000d33b  test    eax, eax
0x18000d33d  js      short loc_18000D380
0x18000d33f  mov     dl, [rbp+4Fh+var_80]; unsigned __int8
0x18000d342  lea     r9, [rbp+4Fh+var_68]; struct _TRUSTED_DOMAIN_AUTH_INFORMATION *
0x18000d346  mov     rcx, [rbp+4Fh+var_78]; struct _LSAP_CR_CIPHER_KEY *
0x18000d34a  mov     r8, r14; struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *
0x18000d34d  call    ?LsaDbpDecryptAuthDataWithSessionKeyAes@@YAJPEAU_LSAP_CR_CIPHER_KEY@@EPEAU_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES@@PEAU_TRUSTED_DOMAIN_AUTH_INFORMATION@@@Z; LsaDbpDecryptAuthDataWithSessionKeyAes(_LSAP_CR_CIPHER_KEY *,uchar,_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *,_TRUSTED_DOMAIN_AUTH_INFORMATION *)
0x18000d352  mov     ebx, eax
0x18000d354  test    eax, eax
0x18000d356  js      short loc_18000D380
0x18000d358  mov     rax, [rbp+4Fh+arg_20]
0x18000d35c  lea     r8, [rbp+4Fh+var_68]; struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION *
0x18000d360  or      r15d, 20h
0x18000d364  mov     [rsp+0B0h+var_90], rax; void **
0x18000d369  mov     r9d, r15d; unsigned int
0x18000d36c  mov     rdx, r12; struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *
0x18000d36f  mov     rcx, rsi; void *
0x18000d372  call    ?LsaDbpCreateTrustedDomain2@@YAJPEAXPEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@PEAU_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION@@KPEAPEAX@Z; LsaDbpCreateTrustedDomain2(void *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *,_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION *,ulong,void * *)
0x18000d377  mov     ebx, eax
0x18000d379  jmp     short loc_18000D380
0x18000d37b  mov     ebx, 0C000000Dh
0x18000d380  mov     rcx, [rbp+4Fh+var_78]; hMem
0x18000d384  test    rcx, rcx
0x18000d387  jz      short loc_18000D38F
0x18000d389  call    cs:__imp_LocalFree
0x18000d38f  lea     rcx, [rbp+4Fh+var_68]; struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *
0x18000d393  call    ?LsaDbpDsFreeUnmarshalAuthInfoHalf@@YAXPEAU_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF@@@Z; LsaDbpDsFreeUnmarshalAuthInfoHalf(_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)
0x18000d398  lea     rcx, [rbp+4Fh+var_68.OutgoingAuthInfos]; struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *
0x18000d39c  call    ?LsaDbpDsFreeUnmarshalAuthInfoHalf@@YAXPEAU_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF@@@Z; LsaDbpDsFreeUnmarshalAuthInfoHalf(_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)
0x18000d3a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3a8  test    dword ptr [rcx+1Ch], 100h
0x18000d3af  jz      short loc_18000D3C9
0x18000d3b1  mov     rcx, [rcx+10h]
0x18000d3b5  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000d3bc  mov     edx, 37h ; '7'
0x18000d3c1  mov     r9d, ebx
0x18000d3c4  call    WPP_SF_d
0x18000d3c9  mov     eax, ebx
0x18000d3cb  add     rsp, 88h
0x18000d3d2  pop     r15
0x18000d3d4  pop     r14
0x18000d3d6  pop     r12
0x18000d3d8  pop     rsi
0x18000d3d9  pop     rbx
0x18000d3da  pop     rbp
0x18000d3db  retn
```
