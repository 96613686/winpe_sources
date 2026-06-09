# LsaDbrCreateTrustedDomainEx2(void *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *,_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL *,ulong,void * *)

- ea: `0x18000d000`
- end: `0x18000d206`
- name: `?LsaDbrCreateTrustedDomainEx2@@YAJPEAXPEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@PEAU_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL@@KPEAPEAX@Z`
- size: `518`
- prototype: `__int64 __fastcall(void *, struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *, struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL *, int, void **)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x18000a080`
- `0x18000a2bc`
- `0x18000bd80`
- `0x18000d000`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fd80`
- `0x180017594`
- `0x180018fa4`
- `0x180034208`
- `0x180035664`
- `0x180035d6c`
- `0x180035ee0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d0e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d1a5`
- `LSASRV!LsapCrServerGetSessionKeySafe` at `0x18000d139`
- `LSASRV!LsapCrServerGetSessionKeySafe` at `0x18000d139`
- `LSASRV!LsapTraceEvent` at `0x18000d04d`
- `LSASRV!LsapTraceEvent` at `0x18000d1ed`
- `LSASRV!LsapTraceEvent` at `0x18000d04d`
- `LSASRV!LsapTraceEvent` at `0x18000d1ed`

## pseudocode

```c
__int64 __fastcall LsaDbrCreateTrustedDomainEx2(
        void *a1,
        struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *a2,
        struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL *a3,
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
  v14[0] = 0;
  hMem = 0;
  LsapTraceEvent(1, 14);
  memset(&v17, 0, sizeof(v17));
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      LsaDbGetCallerInfo(v9, (unsigned __int16 **)&hMem);
      v10 = hMem;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        v11 = L"Unknown";
        if ( hMem )
          v11 = (const wchar_t *)hMem;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids, v11);
      }
      LocalFree(v10);
    }
  }
  if ( LsaDbpValidateTrustedDomainInformationEx((struct _TRUSTED_DOMAIN_INFORMATION_EX *)a2)
    && LsaDbpValidateLsaprTrustedDomainAuthInformationInternal(a3) )
  {
    TrustedDomain2 = LsaDbpCheckIfCallerHasAccessToTDOs(a1);
    if ( TrustedDomain2 >= 0 )
    {
      TrustedDomain2 = LsaDbpIsCallLocal(v14);
      if ( TrustedDomain2 >= 0 )
      {
        if ( v14[0] || (TrustedDomain2 = LsapCrServerGetSessionKeySafe(a1, 1, &v15), TrustedDomain2 >= 0) )
        {
          TrustedDomain2 = LsaDbpDecryptAuthDataWithSessionKeyRc4((struct _LSAP_CR_CIPHER_KEY *)v15, v14[0], a3, &v17);
          if ( TrustedDomain2 >= 0 )
          {
            TrustedDomain2 = LsaDbpCreateTrustedDomain2(
                               a1,
                               a2,
                               (struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION *)&v17,
                               a4 | 0x20,
                               a5);
            if ( TrustedDomain2 >= 0 && !v14[0] )
              LsaDbpAdtTrustedDomainModAuthInfoWithLegacyRPCMethod((struct _UNICODE_STRING *)a2, *((void **)a2 + 4));
          }
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
      52,
      &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids,
      (unsigned int)TrustedDomain2);
  LsapTraceEvent(2, 14);
  return (unsigned int)TrustedDomain2;
}

```

## disassembly

```asm
0x18000d000  push    rbp
0x18000d002  push    rbx
0x18000d003  push    rsi
0x18000d004  push    r12
0x18000d006  push    r14
0x18000d008  push    r15
0x18000d00a  lea     rbp, [rsp-27h]
0x18000d00f  sub     rsp, 88h
0x18000d016  xorps   xmm0, xmm0
0x18000d019  mov     [rbp+4Fh+var_78], 0
0x18000d021  mov     rsi, rdx
0x18000d024  mov     [rbp+4Fh+var_80], 0
0x18000d028  mov     edx, 0Eh
0x18000d02d  mov     [rbp+4Fh+hMem], 0
0x18000d035  mov     r14, rcx
0x18000d038  mov     r12d, r9d
0x18000d03b  mov     r15, r8
0x18000d03e  movups  xmmword ptr [rbp+4Fh+var_68.IncomingAuthInfos], xmm0
0x18000d042  lea     ecx, [rdx-0Dh]
0x18000d045  movups  xmmword ptr [rbp+4Fh+var_68.IncomingPreviousAuthenticationInformation], xmm0
0x18000d049  movups  xmmword ptr [rbp+4Fh+var_68.OutgoingAuthenticationInformation], xmm0
0x18000d04d  call    cs:__imp_LsapTraceEvent
0x18000d053  xorps   xmm0, xmm0
0x18000d056  movups  xmmword ptr [rbp+4Fh+var_68.IncomingAuthInfos], xmm0
0x18000d05a  movups  xmmword ptr [rbp+4Fh+var_68.IncomingPreviousAuthenticationInformation], xmm0
0x18000d05e  movups  xmmword ptr [rbp+4Fh+var_68.OutgoingAuthenticationInformation], xmm0
0x18000d062  mov     rax, cs:WPP_GLOBAL_Control
0x18000d069  test    dword ptr [rax+1Ch], 100h
0x18000d070  jz      short loc_18000D0E6
0x18000d072  mov     rcx, [rax+10h]
0x18000d076  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000d07d  mov     edx, 32h ; '2'
0x18000d082  call    WPP_SF_
0x18000d087  mov     rax, cs:WPP_GLOBAL_Control
0x18000d08e  test    dword ptr [rax+1Ch], 100h
0x18000d095  jz      short loc_18000D0E6
0x18000d097  cmp     byte ptr [rax+19h], 4
0x18000d09b  jb      short loc_18000D0E6
0x18000d09d  lea     rdx, [rbp+4Fh+hMem]; unsigned __int16 **
0x18000d0a1  call    ?LsaDbGetCallerInfo@@YAXPEAXPEAPEAG@Z; LsaDbGetCallerInfo(void *,ushort * *)
0x18000d0a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0ad  mov     rbx, [rbp+4Fh+hMem]
0x18000d0b1  test    dword ptr [rcx+1Ch], 100h
0x18000d0b8  jz      short loc_18000D0DD
0x18000d0ba  mov     rcx, [rcx+10h]
0x18000d0be  lea     r9, aUnknown_0; "Unknown"
0x18000d0c5  test    rbx, rbx
0x18000d0c8  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000d0cf  mov     edx, 33h ; '3'
0x18000d0d4  cmovnz  r9, rbx
0x18000d0d8  call    WPP_SF_S
0x18000d0dd  mov     rcx, rbx; hMem
0x18000d0e0  call    cs:__imp_LocalFree
0x18000d0e6  mov     rcx, rsi; struct _TRUSTED_DOMAIN_INFORMATION_EX *
0x18000d0e9  call    ?LsaDbpValidateTrustedDomainInformationEx@@YAEPEAU_TRUSTED_DOMAIN_INFORMATION_EX@@@Z; LsaDbpValidateTrustedDomainInformationEx(_TRUSTED_DOMAIN_INFORMATION_EX *)
0x18000d0ee  test    al, al
0x18000d0f0  jz      loc_18000D197
0x18000d0f6  mov     rcx, r15; struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL *
0x18000d0f9  call    ?LsaDbpValidateLsaprTrustedDomainAuthInformationInternal@@YAEPEAU_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL@@@Z; LsaDbpValidateLsaprTrustedDomainAuthInformationInternal(_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL *)
0x18000d0fe  test    al, al
0x18000d100  jz      loc_18000D197
0x18000d106  mov     rcx, r14; void *
0x18000d109  call    ?LsaDbpCheckIfCallerHasAccessToTDOs@@YAJQEAX@Z; LsaDbpCheckIfCallerHasAccessToTDOs(void * const)
0x18000d10e  mov     ebx, eax
0x18000d110  test    eax, eax
0x18000d112  js      loc_18000D19C
0x18000d118  lea     rcx, [rbp+4Fh+var_80]; unsigned __int8 *
0x18000d11c  call    ?LsaDbpIsCallLocal@@YAJPEAE@Z; LsaDbpIsCallLocal(uchar *)
0x18000d121  mov     ebx, eax
0x18000d123  test    eax, eax
0x18000d125  js      short loc_18000D19C
0x18000d127  cmp     [rbp+4Fh+var_80], 0
0x18000d12b  jnz     short loc_18000D145
0x18000d12d  lea     r8, [rbp+4Fh+var_78]
0x18000d131  mov     edx, 1
0x18000d136  mov     rcx, r14
0x18000d139  call    cs:__imp_LsapCrServerGetSessionKeySafe
0x18000d13f  mov     ebx, eax
0x18000d141  test    eax, eax
0x18000d143  js      short loc_18000D19C
0x18000d145  mov     dl, [rbp+4Fh+var_80]; unsigned __int8
0x18000d148  lea     r9, [rbp+4Fh+var_68]; struct _TRUSTED_DOMAIN_AUTH_INFORMATION *
0x18000d14c  mov     rcx, [rbp+4Fh+var_78]; struct _LSAP_CR_CIPHER_KEY *
0x18000d150  mov     r8, r15; struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL *
0x18000d153  call    ?LsaDbpDecryptAuthDataWithSessionKeyRc4@@YAJPEAU_LSAP_CR_CIPHER_KEY@@EPEAU_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL@@PEAU_TRUSTED_DOMAIN_AUTH_INFORMATION@@@Z; LsaDbpDecryptAuthDataWithSessionKeyRc4(_LSAP_CR_CIPHER_KEY *,uchar,_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL *,_TRUSTED_DOMAIN_AUTH_INFORMATION *)
0x18000d158  mov     ebx, eax
0x18000d15a  test    eax, eax
0x18000d15c  js      short loc_18000D19C
0x18000d15e  mov     rax, [rbp+4Fh+arg_20]
0x18000d162  lea     r8, [rbp+4Fh+var_68]; struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION *
0x18000d166  or      r12d, 20h
0x18000d16a  mov     [rsp+0B0h+var_90], rax; void **
0x18000d16f  mov     r9d, r12d; unsigned int
0x18000d172  mov     rdx, rsi; struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *
0x18000d175  mov     rcx, r14; void *
0x18000d178  call    ?LsaDbpCreateTrustedDomain2@@YAJPEAXPEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX@@PEAU_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION@@KPEAPEAX@Z; LsaDbpCreateTrustedDomain2(void *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX *,_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION *,ulong,void * *)
0x18000d17d  mov     ebx, eax
0x18000d17f  test    eax, eax
0x18000d181  js      short loc_18000D19C
0x18000d183  cmp     [rbp+4Fh+var_80], 0
0x18000d187  jnz     short loc_18000D19C
0x18000d189  mov     rdx, [rsi+20h]; void *
0x18000d18d  mov     rcx, rsi; struct _UNICODE_STRING *
0x18000d190  call    ?LsaDbpAdtTrustedDomainModAuthInfoWithLegacyRPCMethod@@YAJPEAU_UNICODE_STRING@@PEAX@Z; LsaDbpAdtTrustedDomainModAuthInfoWithLegacyRPCMethod(_UNICODE_STRING *,void *)
0x18000d195  jmp     short loc_18000D19C
0x18000d197  mov     ebx, 0C000000Dh
0x18000d19c  mov     rcx, [rbp+4Fh+var_78]; hMem
0x18000d1a0  test    rcx, rcx
0x18000d1a3  jz      short loc_18000D1AB
0x18000d1a5  call    cs:__imp_LocalFree
0x18000d1ab  lea     rcx, [rbp+4Fh+var_68]; struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *
0x18000d1af  call    ?LsaDbpDsFreeUnmarshalAuthInfoHalf@@YAXPEAU_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF@@@Z; LsaDbpDsFreeUnmarshalAuthInfoHalf(_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)
0x18000d1b4  lea     rcx, [rbp+4Fh+var_68.OutgoingAuthInfos]; struct _LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *
0x18000d1b8  call    ?LsaDbpDsFreeUnmarshalAuthInfoHalf@@YAXPEAU_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF@@@Z; LsaDbpDsFreeUnmarshalAuthInfoHalf(_LSAPR_TRUST_DOMAIN_AUTH_INFO_HALF *)
0x18000d1bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1c4  test    dword ptr [rcx+1Ch], 100h
0x18000d1cb  jz      short loc_18000D1E5
0x18000d1cd  mov     rcx, [rcx+10h]
0x18000d1d1  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x18000d1d8  mov     edx, 34h ; '4'
0x18000d1dd  mov     r9d, ebx
0x18000d1e0  call    WPP_SF_d
0x18000d1e5  mov     edx, 0Eh
0x18000d1ea  lea     ecx, [rdx-0Ch]
0x18000d1ed  call    cs:__imp_LsapTraceEvent
0x18000d1f3  mov     eax, ebx
0x18000d1f5  add     rsp, 88h
0x18000d1fc  pop     r15
0x18000d1fe  pop     r14
0x18000d200  pop     r12
0x18000d202  pop     rsi
0x18000d203  pop     rbx
0x18000d204  pop     rbp
0x18000d205  retn
```
