# DfsTrustedDomain::LoadDcReferralData(DfsReferralData *)

- ea: `0x14003bee4`
- end: `0x14003c786`
- name: `?LoadDcReferralData@DfsTrustedDomain@@AEAAKPEAVDfsReferralData@@@Z`
- size: `2210`
- prototype: `unsigned int __fastcall(DfsTrustedDomain *__hidden this, struct DfsReferralData *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x14003bafc`

## callees

- `0x1400011d0`
- `0x140005a94`
- `0x140005ad8`
- `0x140005b28`
- `0x140005c10`
- `0x1400096ac`
- `0x14000fd24`
- `0x1400152c8`
- `0x14002ff9c`
- `0x14003b85c`
- `0x14003bee4`
- `0x14003c78c`
- `0x14003ccd0`
- `0x1400586a8`

## import_xrefs

- `msvcrt!bsearch_s` at `0x14003c404`
- `msvcrt!bsearch_s` at `0x14003c404`
- `msvcrt!qsort_s` at `0x14003c2cf`
- `msvcrt!qsort_s` at `0x14003c2cf`
- `msvcrt!free` at `0x14003c35c`
- `msvcrt!free` at `0x14003c35c`
- `msvcrt!malloc` at `0x14003c213`
- `msvcrt!malloc` at `0x14003c213`
- `NTDSAPI!DsUnBindW` at `0x14003c12e`
- `NTDSAPI!DsUnBindW` at `0x14003c12e`
- `NTDSAPI!DsBindW` at `0x14003bfa7`
- `NTDSAPI!DsBindW` at `0x14003c00b`
- `NTDSAPI!DsBindW` at `0x14003bfa7`
- `NTDSAPI!DsBindW` at `0x14003c00b`
- `NTDSAPI!DsGetDomainControllerInfoW` at `0x14003c07c`
- `NTDSAPI!DsGetDomainControllerInfoW` at `0x14003c0e1`
- `NTDSAPI!DsGetDomainControllerInfoW` at `0x14003c07c`
- `NTDSAPI!DsGetDomainControllerInfoW` at `0x14003c0e1`
- `NTDSAPI!DsFreeDomainControllerInfoW` at `0x14003c379`
- `NTDSAPI!DsFreeDomainControllerInfoW` at `0x14003c396`
- `NTDSAPI!DsFreeDomainControllerInfoW` at `0x14003c379`
- `NTDSAPI!DsFreeDomainControllerInfoW` at `0x14003c396`
- `logoncli!DsGetDcCloseW` at `0x14003c56b`
- `logoncli!DsGetDcCloseW` at `0x14003c56b`
- `logoncli!DsGetDcNextW` at `0x14003c3c6`
- `logoncli!DsGetDcNextW` at `0x14003c4c3`
- `logoncli!DsGetDcNextW` at `0x14003c3c6`
- `logoncli!DsGetDcNextW` at `0x14003c4c3`
- `logoncli!DsGetDcOpenW` at `0x14003c303`
- `logoncli!DsGetDcOpenW` at `0x14003c303`
- `netutils!NetApiBufferFree` at `0x14003c4a6`
- `netutils!NetApiBufferFree` at `0x14003c4a6`

## pseudocode

```c
DWORD __fastcall DfsTrustedDomain::LoadDcReferralData(DfsTrustedDomain *this, struct DfsReferralData *a2)
{
  const WCHAR *v2; // rax
  struct DfsReferralData *v3; // rdi
  const WCHAR *v5; // rdx
  DWORD v6; // eax
  DWORD DcOpenW; // ebx
  unsigned int *v8; // rcx
  DWORD v9; // eax
  DWORD DomainControllerInfoW; // eax
  DWORD v11; // eax
  unsigned int v13; // ebx
  struct _NORMAL_DC_INFO *v14; // r12
  unsigned int v15; // r13d
  unsigned int v16; // r15d
  rsize_t v17; // rdi
  const WCHAR *v18; // rcx
  void *v19; // rax
  _BYTE *v20; // rbx
  __int64 v21; // rax
  bool v22; // cf
  size_t v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // rdi
  unsigned int v26; // r14d
  struct DfsReferralData *v27; // rax
  unsigned int *v28; // rcx
  __int64 v29; // rdi
  struct DfsReferralData *v30; // r15
  __int64 v31; // rbx
  unsigned int v32; // [rsp+40h] [rbp-29h] BYREF
  LPCWSTR DomainControllerName; // [rsp+48h] [rbp-21h] BYREF
  HANDLE phDS; // [rsp+50h] [rbp-19h] BYREF
  HANDLE GetDcContextHandle; // [rsp+58h] [rbp-11h] BYREF
  void *pInfo; // [rsp+60h] [rbp-9h] BYREF
  struct DS_DOMAIN_CONTROLLER_INFO_3W *ppInfo; // [rsp+68h] [rbp-1h] BYREF
  struct _UNICODE_STRING v38; // [rsp+70h] [rbp+7h] BYREF
  unsigned __int8 v39; // [rsp+D0h] [rbp+67h] BYREF
  struct DfsReferralData *v40; // [rsp+D8h] [rbp+6Fh]
  DWORD pcOut; // [rsp+E0h] [rbp+77h] BYREF
  rsize_t NumOfElements; // [rsp+E8h] [rbp+7Fh] BYREF

  v40 = a2;
  v2 = 0;
  pInfo = 0;
  DomainControllerName = 0;
  v3 = a2;
  ppInfo = 0;
  phDS = 0;
  pcOut = 0;
  LODWORD(NumOfElements) = 0;
  v32 = 0;
  v39 = 0;
  v38 = 0;
  GetDcContextHandle = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_ZZd(
      *((_QWORD *)pWppControl + 2),
      27,
      (_DWORD)this + 16,
      (_DWORD)this,
      (__int64)this + 16,
      *((_BYTE *)this + 32));
    v2 = DomainControllerName;
  }
  *((_DWORD *)v3 + 15) = 900;
  v5 = (const WCHAR *)*((_QWORD *)this + 3);
  if ( !v5 )
    v5 = (const WCHAR *)*((_QWORD *)this + 1);
  v6 = DsBindW(v2, v5, &phDS);
  DcOpenW = v6;
  v8 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 28, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, v6);
    v8 = pWppControl;
  }
  if ( !DcOpenW )
    goto LABEL_21;
  if ( *((_BYTE *)this + 32) == 1 )
  {
    v9 = DsBindW(DomainControllerName, *((LPCWSTR *)this + 1), &phDS);
    DcOpenW = v9;
    v8 = pWppControl;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)pWppControl + 2), 29, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, v9);
      v8 = pWppControl;
    }
  }
  if ( !DcOpenW )
  {
LABEL_21:
    DomainControllerInfoW = DsGetDomainControllerInfoW(phDS, *((LPCWSTR *)this + 1), 3u, &pcOut, (void **)&ppInfo);
    DcOpenW = DomainControllerInfoW;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)pWppControl + 2), 30, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, DomainControllerInfoW);
    }
    if ( DcOpenW == 50 )
    {
      v11 = DsGetDomainControllerInfoW(phDS, *((LPCWSTR *)this + 1), 1u, &pcOut, &pInfo);
      DcOpenW = v11;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x20) != 0
        && *((_BYTE *)pWppControl + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)pWppControl + 2), 31, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, v11);
      }
    }
    DsUnBindW(&phDS);
    if ( DcOpenW )
    {
      v8 = pWppControl;
      v3 = v40;
      goto LABEL_34;
    }
    DfsTrustedDomain::CountOrFillEnabledDcList(
      this,
      (struct DS_DOMAIN_CONTROLLER_INFO_1W *)pInfo,
      ppInfo,
      pcOut,
      0,
      (unsigned int *)&NumOfElements,
      0);
    v13 = NumOfElements;
    if ( !(_DWORD)NumOfElements )
    {
      DcOpenW = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x20) != 0
        && *((_BYTE *)pWppControl + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)pWppControl + 2), 33, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids);
      }
      goto LABEL_64;
    }
    v14 = (struct _NORMAL_DC_INFO *)malloc(24LL * (unsigned int)NumOfElements);
    if ( !v14 )
    {
      DcOpenW = 8;
      goto LABEL_64;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 2u )
    {
      WPP_SF_dD(*((_QWORD *)pWppControl + 2), 34, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, v13, pcOut);
    }
    DfsTrustedDomain::CountOrFillEnabledDcList(
      this,
      (struct DS_DOMAIN_CONTROLLER_INFO_1W *)pInfo,
      ppInfo,
      pcOut,
      v14,
      (unsigned int *)&NumOfElements,
      &v32);
    v15 = NumOfElements;
    DcOpenW = 0;
    v16 = v32;
    if ( (unsigned int)NumOfElements < v32 )
    {
      v17 = (unsigned int)NumOfElements;
      qsort_s(v14, (unsigned int)NumOfElements, 0x18u, DfsNDCISortFunc, 0);
      v18 = (const WCHAR *)*((_QWORD *)this + 3);
      if ( !v18 )
        v18 = (const WCHAR *)*((_QWORD *)this + 1);
      DcOpenW = DsGetDcOpenW(v18, 0, 0, 0, 0, 0, &GetDcContextHandle);
      if ( DcOpenW )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x20) != 0
          && *((_BYTE *)pWppControl + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)pWppControl + 2), 35, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, DcOpenW);
        }
LABEL_63:
        free(v14);
        goto LABEL_64;
      }
      DcOpenW = DsGetDcNextW(GetDcContextHandle, 0, 0, (LPWSTR *)&DomainControllerName);
      if ( !DcOpenW )
      {
        do
        {
          v19 = bsearch_s(DomainControllerName, v14, v17, 0x18u, DfsNDCISearchFunc, 0);
          v20 = v19;
          if ( v19 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && pWppControl
              && (pWppControl[7] & 0x20) != 0
              && *((_BYTE *)pWppControl + 25) >= 2u )
            {
              WPP_SF_SS(
                *((_QWORD *)pWppControl + 2),
                38,
                (unsigned int)WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids,
                *((_QWORD *)v19 + 2),
                *((_QWORD *)v19 + 1));
            }
            if ( !*v20 )
            {
              *v20 = 1;
              ++v16;
            }
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && pWppControl
                 && (pWppControl[7] & 0x20) != 0
                 && *((_BYTE *)pWppControl + 25) >= 2u )
          {
            WPP_SF_S(
              *((_QWORD *)pWppControl + 2),
              39,
              WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids,
              DomainControllerName);
          }
          NetApiBufferFree((LPVOID)DomainControllerName);
          DomainControllerName = 0;
          DcOpenW = DsGetDcNextW(GetDcContextHandle, 0, 0, (LPWSTR *)&DomainControllerName);
        }
        while ( !DcOpenW );
        v15 = NumOfElements;
      }
      if ( DcOpenW == 259 )
      {
        DcOpenW = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x20) != 0
          && *((_BYTE *)pWppControl + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)pWppControl + 2), 36, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids);
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && pWppControl
             && (pWppControl[7] & 0x20) != 0
             && *((_BYTE *)pWppControl + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)pWppControl + 2), 37, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, DcOpenW);
      }
      DsGetDcCloseW(GetDcContextHandle);
    }
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x20) != 0
        && *((_BYTE *)pWppControl + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)pWppControl + 2), 40, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, v16);
      }
      v21 = 56LL * v16;
      DcOpenW = 8;
      if ( !is_mul_ok(v16, 0x38u) )
        v21 = -1;
      v22 = __CFADD__(v21, 8);
      v23 = v21 + 8;
      if ( v22 )
        v23 = -1;
      v24 = operator new(v23);
      if ( v24 )
      {
        v25 = v24 + 1;
        *v24 = v16;
        `vector constructor iterator'(v24 + 1, 0x38u, v16, (void *(*)(void *))DfsReplica::DfsReplica);
        v26 = 0;
      }
      else
      {
        v26 = 0;
        v25 = 0;
      }
      v27 = v40;
      *((_QWORD *)v40 + 6) = v25;
      if ( v25 )
      {
        v28 = pWppControl;
        DcOpenW = 0;
        *((_DWORD *)v27 + 10) = v16;
        v29 = 0;
        v30 = v27;
        while ( (unsigned int)v29 < v15 )
        {
          if ( *((_BYTE *)v14 + 24 * v29) == 1 )
          {
            if ( *((_BYTE *)this + 32) == 1 )
              v31 = *((_QWORD *)v14 + 3 * v29 + 1);
            else
              v31 = *((_QWORD *)v14 + 3 * v29 + 2);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && v28
              && (v28[7] & 0x20) != 0
              && *((_BYTE *)v28 + 25) >= 2u )
            {
              WPP_SF_S(*((_QWORD *)v28 + 2), 42, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids, v31);
            }
            DcOpenW = DfsRtlInitUnicodeStringEx(&v38, v31);
            if ( DcOpenW )
              goto LABEL_63;
            DcOpenW = DfsReplica::SetTargetServer((DfsReplica *)(*((_QWORD *)v30 + 6) + 56LL * v26), &v38, &v39);
            v28 = pWppControl;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && pWppControl
              && (pWppControl[7] & 0x20) != 0
              && *((_BYTE *)pWppControl + 25) >= 2u )
            {
              WPP_SF_ZD(
                *((_QWORD *)pWppControl + 2),
                43,
                (unsigned int)WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids,
                (unsigned int)&v38,
                DcOpenW);
              v28 = pWppControl;
            }
            if ( DcOpenW )
              goto LABEL_63;
            ++v26;
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && v28
                 && (v28[7] & 0x20) != 0
                 && *((_BYTE *)v28 + 25) >= 2u )
          {
            WPP_SF_SS(
              *((_QWORD *)v28 + 2),
              41,
              (unsigned int)WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids,
              *((_QWORD *)v14 + 3 * v29 + 2),
              *((_QWORD *)v14 + 3 * v29 + 1));
            v28 = pWppControl;
          }
          v29 = (unsigned int)(v29 + 1);
        }
      }
    }
    goto LABEL_63;
  }
LABEL_34:
  if ( !*((_BYTE *)this + 32) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && v8 && (v8[7] & 0x20) != 0 && *((_BYTE *)v8 + 25) >= 2u )
      WPP_SF_(*((_QWORD *)v8 + 2), 32, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids);
    return DfsTrustedDomain::LoadDcReferralDataDnsOnly(this, v3);
  }
LABEL_64:
  if ( pInfo )
    DsFreeDomainControllerInfoW(1u, pcOut, pInfo);
  if ( ppInfo )
    DsFreeDomainControllerInfoW(3u, pcOut, ppInfo);
  return DcOpenW;
}

```

## disassembly

```asm
0x14003bee4  mov     [rsp-8+arg_8], rdx
0x14003bee9  push    rbp
0x14003beea  push    rbx
0x14003beeb  push    rsi
0x14003beec  push    rdi
0x14003beed  push    r12
0x14003beef  push    r13
0x14003bef1  push    r14
0x14003bef3  push    r15
0x14003bef5  lea     rbp, [rsp-1Fh]
0x14003befa  sub     rsp, 88h
0x14003bf01  xor     r14d, r14d
0x14003bf04  xorps   xmm0, xmm0
0x14003bf07  mov     eax, r14d
0x14003bf0a  mov     [rbp+57h+pInfo], r14
0x14003bf0e  mov     [rbp+57h+DomainControllerName], rax
0x14003bf12  mov     rdi, rdx
0x14003bf15  mov     rsi, rcx
0x14003bf18  mov     [rbp+57h+var_58], r14
0x14003bf1c  mov     [rbp+57h+phDS], r14
0x14003bf20  mov     [rbp+57h+pcOut], r14d
0x14003bf24  mov     dword ptr [rbp+57h+NumOfElements], r14d
0x14003bf28  mov     [rbp+57h+var_80], r14d
0x14003bf2c  mov     [rbp+57h+arg_0], r14b
0x14003bf30  movups  xmmword ptr [rbp+57h+var_50.Length], xmm0
0x14003bf34  mov     [rbp+57h+GetDcContextHandle], r14
0x14003bf38  lea     r12, WPP_GLOBAL_Control
0x14003bf3f  mov     r13b, 2
0x14003bf42  cmp     cs:WPP_GLOBAL_Control, r12
0x14003bf49  lea     r15d, [r14+20h]
0x14003bf4d  jz      short loc_14003BF8C
0x14003bf4f  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003bf56  test    rcx, rcx
0x14003bf59  jz      short loc_14003BF8C
0x14003bf5b  test    [rcx+1Ch], r15b
0x14003bf5f  jz      short loc_14003BF8C
0x14003bf61  cmp     [rcx+19h], r13b
0x14003bf65  jb      short loc_14003BF8C
0x14003bf67  movzx   eax, byte ptr [rsi+20h]
0x14003bf6b  lea     r8, [rsi+10h]
0x14003bf6f  mov     rcx, [rcx+10h]
0x14003bf73  lea     edx, [r14+1Bh]
0x14003bf77  mov     [rsp+0C0h+DcFlags], eax
0x14003bf7b  mov     r9, rsi
0x14003bf7e  mov     [rsp+0C0h+ppInfo], r8
0x14003bf83  call    WPP_SF_ZZd
0x14003bf88  mov     rax, [rbp+57h+DomainControllerName]
0x14003bf8c  mov     dword ptr [rdi+3Ch], 384h
0x14003bf93  mov     rdx, [rsi+18h]
0x14003bf97  test    rdx, rdx
0x14003bf9a  jnz     short loc_14003BFA0
0x14003bf9c  mov     rdx, [rsi+8]; DnsDomainName
0x14003bfa0  lea     r8, [rbp+57h+phDS]; phDS
0x14003bfa4  mov     rcx, rax; DomainControllerName
0x14003bfa7  call    cs:__imp_DsBindW
0x14003bfae  nop     dword ptr [rax+rax+00h]
0x14003bfb3  mov     ebx, eax
0x14003bfb5  cmp     cs:WPP_GLOBAL_Control, r12
0x14003bfbc  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003bfc3  jz      short loc_14003BFF5
0x14003bfc5  test    rcx, rcx
0x14003bfc8  jz      short loc_14003BFF5
0x14003bfca  test    [rcx+1Ch], r15b
0x14003bfce  jz      short loc_14003BFF5
0x14003bfd0  cmp     [rcx+19h], r13b
0x14003bfd4  jb      short loc_14003BFF5
0x14003bfd6  mov     rcx, [rcx+10h]
0x14003bfda  lea     r8, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids
0x14003bfe1  mov     edx, 1Ch
0x14003bfe6  mov     r9d, eax
0x14003bfe9  call    WPP_SF_D
0x14003bfee  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003bff5  test    ebx, ebx
0x14003bff7  jz      short loc_14003C061
0x14003bff9  cmp     byte ptr [rsi+20h], 1
0x14003bffd  jnz     short loc_14003C059
0x14003bfff  mov     rdx, [rsi+8]; DnsDomainName
0x14003c003  lea     r8, [rbp+57h+phDS]; phDS
0x14003c007  mov     rcx, [rbp+57h+DomainControllerName]; DomainControllerName
0x14003c00b  call    cs:__imp_DsBindW
0x14003c012  nop     dword ptr [rax+rax+00h]
0x14003c017  mov     ebx, eax
0x14003c019  cmp     cs:WPP_GLOBAL_Control, r12
0x14003c020  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c027  jz      short loc_14003C059
0x14003c029  test    rcx, rcx
0x14003c02c  jz      short loc_14003C059
0x14003c02e  test    [rcx+1Ch], r15b
0x14003c032  jz      short loc_14003C059
0x14003c034  cmp     [rcx+19h], r13b
0x14003c038  jb      short loc_14003C059
0x14003c03a  mov     rcx, [rcx+10h]
0x14003c03e  lea     r8, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids
0x14003c045  mov     edx, 1Dh
0x14003c04a  mov     r9d, eax
0x14003c04d  call    WPP_SF_D
0x14003c052  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c059  test    ebx, ebx
0x14003c05b  jnz     loc_14003C149
0x14003c061  mov     rdx, [rsi+8]; DomainName
0x14003c065  lea     rax, [rbp+57h+var_58]
0x14003c069  mov     rcx, [rbp+57h+phDS]; hDs
0x14003c06d  lea     r9, [rbp+57h+pcOut]; pcOut
0x14003c071  mov     r8d, 3; InfoLevel
0x14003c077  mov     [rsp+0C0h+ppInfo], rax; ppInfo
0x14003c07c  call    cs:__imp_DsGetDomainControllerInfoW
0x14003c083  nop     dword ptr [rax+rax+00h]
0x14003c088  mov     ebx, eax
0x14003c08a  cmp     cs:WPP_GLOBAL_Control, r12
0x14003c091  jz      short loc_14003C0C3
0x14003c093  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c09a  test    rcx, rcx
0x14003c09d  jz      short loc_14003C0C3
0x14003c09f  test    [rcx+1Ch], r15b
0x14003c0a3  jz      short loc_14003C0C3
0x14003c0a5  cmp     [rcx+19h], r13b
0x14003c0a9  jb      short loc_14003C0C3
0x14003c0ab  mov     rcx, [rcx+10h]
0x14003c0af  lea     r8, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids
0x14003c0b6  mov     edx, 1Eh
0x14003c0bb  mov     r9d, eax
0x14003c0be  call    WPP_SF_D
0x14003c0c3  cmp     ebx, 32h ; '2'
0x14003c0c6  jnz     short loc_14003C128
0x14003c0c8  mov     rdx, [rsi+8]; DomainName
0x14003c0cc  lea     rax, [rbp+57h+pInfo]
0x14003c0d0  mov     rcx, [rbp+57h+phDS]; hDs
0x14003c0d4  lea     r9, [rbp+57h+pcOut]; pcOut
0x14003c0d8  lea     r8d, [rbx-31h]; InfoLevel
0x14003c0dc  mov     [rsp+0C0h+ppInfo], rax; ppInfo
0x14003c0e1  call    cs:__imp_DsGetDomainControllerInfoW
0x14003c0e8  nop     dword ptr [rax+rax+00h]
0x14003c0ed  mov     ebx, eax
0x14003c0ef  cmp     cs:WPP_GLOBAL_Control, r12
0x14003c0f6  jz      short loc_14003C128
0x14003c0f8  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c0ff  test    rcx, rcx
0x14003c102  jz      short loc_14003C128
0x14003c104  test    [rcx+1Ch], r15b
0x14003c108  jz      short loc_14003C128
0x14003c10a  cmp     [rcx+19h], r13b
0x14003c10e  jb      short loc_14003C128
0x14003c110  mov     rcx, [rcx+10h]
0x14003c114  lea     r8, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids
0x14003c11b  mov     edx, 1Fh
0x14003c120  mov     r9d, eax
0x14003c123  call    WPP_SF_D
0x14003c128  lea     rcx, [rbp+57h+phDS]; phDS
0x14003c12c  mov     edi, ebx
0x14003c12e  call    cs:__imp_DsUnBindW
0x14003c135  nop     dword ptr [rax+rax+00h]
0x14003c13a  test    ebx, ebx
0x14003c13c  jz      short loc_14003C190
0x14003c13e  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c145  mov     rdi, [rbp+57h+arg_8]
0x14003c149  cmp     [rsi+20h], r14b
0x14003c14d  jnz     loc_14003C368
0x14003c153  cmp     cs:WPP_GLOBAL_Control, r12
0x14003c15a  jz      short loc_14003C180
0x14003c15c  test    rcx, rcx
0x14003c15f  jz      short loc_14003C180
0x14003c161  test    [rcx+1Ch], r15b
0x14003c165  jz      short loc_14003C180
0x14003c167  cmp     [rcx+19h], r13b
0x14003c16b  jb      short loc_14003C180
0x14003c16d  mov     rcx, [rcx+10h]
0x14003c171  lea     r8, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids
0x14003c178  mov     edx, r15d
0x14003c17b  call    WPP_SF_
0x14003c180  mov     rdx, rdi; struct DfsReferralData *
0x14003c183  mov     rcx, rsi; this
0x14003c186  call    ?LoadDcReferralDataDnsOnly@DfsTrustedDomain@@AEAAKPEAVDfsReferralData@@@Z; DfsTrustedDomain::LoadDcReferralDataDnsOnly(DfsReferralData *)
0x14003c18b  jmp     loc_14003C3A4
0x14003c190  mov     r9d, [rbp+57h+pcOut]; unsigned int
0x14003c194  lea     rax, [rbp+57h+NumOfElements]
0x14003c198  mov     r8, [rbp+57h+var_58]; struct DS_DOMAIN_CONTROLLER_INFO_3W *
0x14003c19c  mov     rcx, rsi; this
0x14003c19f  mov     rdx, [rbp+57h+pInfo]; struct DS_DOMAIN_CONTROLLER_INFO_1W *
0x14003c1a3  mov     [rsp+0C0h+RetGetDcContext], r14; unsigned int *
0x14003c1a8  mov     qword ptr [rsp+0C0h+DcFlags], rax; unsigned int *
0x14003c1ad  mov     [rsp+0C0h+ppInfo], r14; struct _NORMAL_DC_INFO *
0x14003c1b2  call    ?CountOrFillEnabledDcList@DfsTrustedDomain@@AEAAXPEAUDS_DOMAIN_CONTROLLER_INFO_1W@@PEAUDS_DOMAIN_CONTROLLER_INFO_3W@@KPEAU_NORMAL_DC_INFO@@PEAK3@Z; DfsTrustedDomain::CountOrFillEnabledDcList(DS_DOMAIN_CONTROLLER_INFO_1W *,DS_DOMAIN_CONTROLLER_INFO_3W *,ulong,_NORMAL_DC_INFO *,ulong *,ulong *)
0x14003c1b7  mov     ebx, dword ptr [rbp+57h+NumOfElements]
0x14003c1ba  test    ebx, ebx
0x14003c1bc  jnz     short loc_14003C20B
0x14003c1be  cmp     cs:WPP_GLOBAL_Control, r12
0x14003c1c5  mov     ebx, edi
0x14003c1c7  jz      loc_14003C368
0x14003c1cd  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c1d4  test    rcx, rcx
0x14003c1d7  jz      loc_14003C368
0x14003c1dd  test    [rcx+1Ch], r15b
0x14003c1e1  jz      loc_14003C368
0x14003c1e7  cmp     [rcx+19h], r13b
0x14003c1eb  jb      loc_14003C368
0x14003c1f1  mov     rcx, [rcx+10h]
0x14003c1f5  lea     r8, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids
0x14003c1fc  mov     edx, 21h ; '!'
0x14003c201  call    WPP_SF_
0x14003c206  jmp     loc_14003C368
0x14003c20b  lea     rcx, [rbx+rbx*2]
0x14003c20f  shl     rcx, 3; Size
0x14003c213  call    cs:__imp_malloc
0x14003c21a  nop     dword ptr [rax+rax+00h]
0x14003c21f  mov     r12, rax
0x14003c222  test    rax, rax
0x14003c225  jnz     short loc_14003C22F
0x14003c227  lea     ebx, [rax+8]
0x14003c22a  jmp     loc_14003C368
0x14003c22f  lea     rax, WPP_GLOBAL_Control
0x14003c236  cmp     cs:WPP_GLOBAL_Control, rax
0x14003c23d  jz      short loc_14003C276
0x14003c23f  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c246  test    rcx, rcx
0x14003c249  jz      short loc_14003C276
0x14003c24b  test    [rcx+1Ch], r15b
0x14003c24f  jz      short loc_14003C276
0x14003c251  cmp     [rcx+19h], r13b
0x14003c255  jb      short loc_14003C276
0x14003c257  mov     eax, [rbp+57h+pcOut]
0x14003c25a  lea     r8, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids
0x14003c261  mov     rcx, [rcx+10h]
0x14003c265  mov     edx, 22h ; '"'
0x14003c26a  mov     r9d, ebx
0x14003c26d  mov     dword ptr [rsp+0C0h+ppInfo], eax
0x14003c271  call    WPP_SF_dD
0x14003c276  mov     r9d, [rbp+57h+pcOut]; unsigned int
0x14003c27a  lea     rax, [rbp+57h+var_80]
0x14003c27e  mov     r8, [rbp+57h+var_58]; struct DS_DOMAIN_CONTROLLER_INFO_3W *
0x14003c282  mov     rcx, rsi; this
0x14003c285  mov     rdx, [rbp+57h+pInfo]; struct DS_DOMAIN_CONTROLLER_INFO_1W *
0x14003c289  mov     [rsp+0C0h+RetGetDcContext], rax; unsigned int *
0x14003c28e  lea     rax, [rbp+57h+NumOfElements]
0x14003c292  mov     qword ptr [rsp+0C0h+DcFlags], rax; unsigned int *
0x14003c297  mov     [rsp+0C0h+ppInfo], r12; struct _NORMAL_DC_INFO *
0x14003c29c  call    ?CountOrFillEnabledDcList@DfsTrustedDomain@@AEAAXPEAUDS_DOMAIN_CONTROLLER_INFO_1W@@PEAUDS_DOMAIN_CONTROLLER_INFO_3W@@KPEAU_NORMAL_DC_INFO@@PEAK3@Z; DfsTrustedDomain::CountOrFillEnabledDcList(DS_DOMAIN_CONTROLLER_INFO_1W *,DS_DOMAIN_CONTROLLER_INFO_3W *,ulong,_NORMAL_DC_INFO *,ulong *,ulong *)
0x14003c2a1  mov     r13d, dword ptr [rbp+57h+NumOfElements]
0x14003c2a5  mov     ebx, edi
0x14003c2a7  mov     r15d, [rbp+57h+var_80]
0x14003c2ab  cmp     r13d, r15d
0x14003c2ae  jnb     loc_14003C577
0x14003c2b4  lea     r9, ?DfsNDCISortFunc@@YAHPEAXPEBX1@Z; CompareFunction
0x14003c2bb  mov     [rsp+0C0h+ppInfo], r14; Context
0x14003c2c0  mov     r8d, 18h; SizeOfElements
0x14003c2c6  mov     edx, r13d; NumOfElements
0x14003c2c9  mov     rcx, r12; Base
0x14003c2cc  mov     edi, r13d
0x14003c2cf  call    cs:__imp_qsort_s
0x14003c2d6  nop     dword ptr [rax+rax+00h]
0x14003c2db  mov     rcx, [rsi+18h]
0x14003c2df  test    rcx, rcx
0x14003c2e2  jnz     short loc_14003C2E8
0x14003c2e4  mov     rcx, [rsi+8]; DnsName
0x14003c2e8  lea     rax, [rbp+57h+GetDcContextHandle]
0x14003c2ec  xor     r9d, r9d; DomainGuid
0x14003c2ef  mov     [rsp+0C0h+RetGetDcContext], rax; RetGetDcContext
0x14003c2f4  xor     r8d, r8d; SiteName
0x14003c2f7  mov     [rsp+0C0h+DcFlags], r14d; DcFlags
0x14003c2fc  xor     edx, edx; OptionFlags
0x14003c2fe  mov     [rsp+0C0h+ppInfo], r14; DnsForestName
0x14003c303  call    cs:__imp_DsGetDcOpenW
0x14003c30a  nop     dword ptr [rax+rax+00h]
0x14003c30f  mov     ebx, eax
0x14003c311  test    eax, eax
0x14003c313  jz      loc_14003C3B9
0x14003c319  lea     rax, WPP_GLOBAL_Control
0x14003c320  cmp     cs:WPP_GLOBAL_Control, rax
0x14003c327  jz      short loc_14003C359
0x14003c329  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003c330  test    rcx, rcx
0x14003c333  jz      short loc_14003C359
0x14003c335  test    byte ptr [rcx+1Ch], 20h
0x14003c339  jz      short loc_14003C359
0x14003c33b  cmp     byte ptr [rcx+19h], 2
0x14003c33f  jb      short loc_14003C359
0x14003c341  mov     rcx, [rcx+10h]
0x14003c345  lea     r8, WPP_f63a4ef67e16392ce89423ead838a9ef_Traceguids
0x14003c34c  mov     edx, 23h ; '#'
0x14003c351  mov     r9d, ebx
0x14003c354  call    WPP_SF_D
0x14003c359  mov     rcx, r12; Block
0x14003c35c  call    cs:__imp_free
0x14003c363  nop     dword ptr [rax+rax+00h]
0x14003c368  mov     r8, [rbp+57h+pInfo]; pInfo
0x14003c36c  test    r8, r8
0x14003c36f  jz      short loc_14003C385
0x14003c371  mov     edx, [rbp+57h+pcOut]; cInfo
0x14003c374  mov     ecx, 1; InfoLevel
0x14003c379  call    cs:__imp_DsFreeDomainControllerInfoW
0x14003c380  nop     dword ptr [rax+rax+00h]
0x14003c385  mov     r8, [rbp+57h+var_58]; pInfo
0x14003c389  test    r8, r8
0x14003c38c  jz      short loc_14003C3A2
0x14003c38e  mov     edx, [rbp+57h+pcOut]; cInfo
0x14003c391  mov     ecx, 3; InfoLevel
0x14003c396  call    cs:__imp_DsFreeDomainControllerInfoW
0x14003c39d  nop     dword ptr [rax+rax+00h]
0x14003c3a2  mov     eax, ebx
0x14003c3a4  add     rsp, 88h
0x14003c3ab  pop     r15
  ... truncated ...
```
