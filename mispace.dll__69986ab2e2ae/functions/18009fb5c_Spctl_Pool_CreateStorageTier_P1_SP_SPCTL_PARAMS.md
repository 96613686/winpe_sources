# Spctl_Pool_CreateStorageTier_P1(_SP_SPCTL_PARAMS *)

- ea: `0x18009fb5c`
- end: `0x1800a0275`
- name: `?Spctl_Pool_CreateStorageTier_P1@@YAKPEAU_SP_SPCTL_PARAMS@@@Z`
- size: `1817`
- prototype: `unsigned int __fastcall(struct _SP_SPCTL_PARAMS *)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x1800958b8`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x18000722d`
- `0x18000cd3c`
- `0x18000f484`
- `0x180026a6c`
- `0x18002aae0`
- `0x18002aba4`
- `0x18002ac20`
- `0x18002d674`
- `0x18006b4b0`
- `0x18009fb5c`
- `0x1800aef0c`
- `0x1801bb1cc`
- `0x1801c1a74`
- `0x1801c3344`
- `0x1801c33b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009fec0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009fed4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009fee8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009fec0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009fed4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009fee8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009fe12`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009fe12`

## string_xrefs

- `0x18009fb7d`: `Spctl_Pool_CreateStorageTier_P1`
- `0x18009fd81`: `Spctl_Pool_CreateStorageTier_P1`
- `0x18009fe4c`: `Spctl_Pool_CreateStorageTier_P1`
- `0x18009feff`: `Spctl_Pool_CreateStorageTier_P1`
- `0x18009ffa0`: `Spctl_Pool_CreateStorageTier_P1`
- `0x1800a0044`: `Spctl_Pool_CreateStorageTier_P1`
- `0x1800a023a`: `Spctl_Pool_CreateStorageTier_P1`

## pseudocode

```c
__int64 __fastcall Spctl_Pool_CreateStorageTier_P1(struct _SP_SPCTL_PARAMS *a1, __int64 a2, int a3, int a4)
{
  unsigned int v5; // eax
  unsigned int v6; // r11d
  struct _SU_POOL_OBJECT *v7; // r15
  struct _SP_TIER_INFO *v8; // rsi
  void *v10; // r13
  __int64 v11; // rbx
  unsigned int v12; // ecx
  unsigned int v13; // edi
  __int64 v14; // rax
  char v15; // r13
  __int64 v16; // rax
  unsigned int v17; // ecx
  __int64 v18; // rax
  unsigned int v19; // ecx
  _BYTE *v20; // r14
  __int64 v21; // rax
  unsigned int v22; // ecx
  unsigned __int64 v23; // rdx
  __int64 v24; // rdx
  int LastError; // eax
  int v26; // r8d
  int v27; // r9d
  unsigned int v28; // r12d
  int v29; // eax
  __int64 v30; // r14
  int v31; // r15d
  _DWORD *v32; // rax
  _DWORD *v33; // rcx
  int v34; // eax
  int v35; // r8d
  int v36; // r9d
  __int64 v37; // r12
  struct _SP_SPCTL_PARAMS *v38; // r14
  __int64 v39; // rbx
  unsigned int v40; // eax
  int v41; // r8d
  int v42; // r9d
  unsigned int v43; // eax
  int v44; // eax
  int v45; // r8d
  int v46; // r9d
  char v47; // r11
  int v48; // r8d
  int v49; // r9d
  char *v50; // rdx
  int v51; // eax
  int v52; // eax
  unsigned int v53; // edx
  unsigned int v54; // edx
  int v55; // ecx
  int v56; // eax
  int v57; // eax
  int v58; // r8d
  int v59; // r9d
  __int64 v60; // [rsp+40h] [rbp-38h]
  struct _SU_POOL_OBJECT *v61; // [rsp+48h] [rbp-30h] BYREF
  struct _SP_TIER_INFO *v62; // [rsp+50h] [rbp-28h] BYREF
  __int64 v63; // [rsp+58h] [rbp-20h] BYREF
  char v64; // [rsp+60h] [rbp-18h]
  struct _SP_SPCTL_PARAMS *v65; // [rsp+C0h] [rbp+48h] BYREF
  unsigned __int64 v66; // [rsp+C8h] [rbp+50h] BYREF
  const char *v67; // [rsp+D0h] [rbp+58h] BYREF
  _DWORD *v68; // [rsp+D8h] [rbp+60h]

  v65 = a1;
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v66) = 1481;
    v67 = "Spctl_Pool_CreateStorageTier_P1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"Spctl_Pool_CreateStorageTier_P1",
      (unsigned int)byte_180320A55,
      a3,
      a4,
      (__int64)&v67,
      (__int64)&v66);
  }
  v5 = *((_DWORD *)a1 + 142);
  v6 = 0;
  v61 = 0;
  v7 = 0;
  v63 = 0;
  v8 = 0;
  v64 = 0;
  v62 = 0;
  if ( v5 < 0x18 )
    return 87;
  if ( *((_DWORD *)a1 + 146) < 0x220u )
  {
    **((_DWORD **)a1 + 74) = 544;
    return 87;
  }
  v10 = 0;
  v11 = *((_QWORD *)a1 + 70);
  v60 = *((_QWORD *)a1 + 72);
  v68 = 0;
  v12 = *(_DWORD *)(v11 + 12);
  if ( v5 >= v12 && *(_DWORD *)(v11 + 16) == 2016 && *(_DWORD *)(v11 + 8) >= 0x54u && v12 >= *(_DWORD *)(v11 + 8) )
  {
    v14 = *(unsigned int *)(v11 + 36);
    v15 = 1;
    if ( (_DWORD)v14
      && ((unsigned int)v14 < *(_DWORD *)(v11 + 8)
       || (unsigned int)v14 > v12
       || (v14 & 1) != 0
       || (int)StringCbLengthW((const unsigned __int16 *)(v11 + v14), v12 - (unsigned int)v14, &v66) < 0) )
    {
      goto LABEL_17;
    }
    v16 = *(unsigned int *)(v11 + 24);
    if ( (_DWORD)v16 )
    {
      if ( (unsigned int)v16 < *(_DWORD *)(v11 + 8) )
        goto LABEL_17;
      v17 = *(_DWORD *)(v11 + 12);
      if ( (unsigned int)v16 > v17
        || (v16 & 1) != 0
        || (int)StringCbLengthW((const unsigned __int16 *)(v11 + v16), v17 - (unsigned int)v16, &v66) < 0 )
      {
        goto LABEL_17;
      }
    }
    if ( (v18 = *(unsigned int *)(v11 + 28), (_DWORD)v18)
      && ((unsigned int)v18 < *(_DWORD *)(v11 + 8)
       || (v19 = *(_DWORD *)(v11 + 12), (unsigned int)v18 > v19)
       || (v18 & 1) != 0
       || (int)StringCbLengthW((const unsigned __int16 *)(v11 + v18), v19 - (unsigned int)v18, &v66) < 0)
      || (v20 = (_BYTE *)(v11 + 84), *(_DWORD *)(v11 + 8) >= 0x58u)
      && *v20 != (_BYTE)v6
      && *(_DWORD *)(v11 + 8) >= 0x5Cu
      && (v21 = *(unsigned int *)(v11 + 88), (_DWORD)v21)
      && ((unsigned int)v21 < *(_DWORD *)(v11 + 8)
       || (unsigned int)v21 > *(_DWORD *)(v11 + 12)
       || (v21 & 3) != 0
       || (v22 = v21 + 4, (int)v21 + 4 < (unsigned int)v21)
       || v22 > *(_DWORD *)(v11 + 12)
       || (v23 = 16LL * *(unsigned int *)(v21 + v11), v23 > 0xFFFFFFFF)
       || (unsigned int)v23 + v22 < v22
       || (unsigned int)v23 + v22 > *(_DWORD *)(v11 + 12)) )
    {
LABEL_17:
      v13 = 87;
LABEL_18:
      v10 = 0;
      goto LABEL_54;
    }
    v13 = v6;
    if ( !(unsigned int)SiGetPool((struct _GUID *)((char *)a1 + 4), 2, &v61) )
    {
      LastError = _status_t::GetLastError((_status_t *)&v63);
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v66) = LastError;
        LODWORD(v67) = 1681;
        v62 = (struct _SP_TIER_INFO *)"Spctl_Pool_CreateStorageTier_P1";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          dword_18039EB68,
          (unsigned int)&unk_180324950,
          v26,
          v27,
          (__int64)&v62,
          (__int64)&v67,
          (__int64)&v66);
        v7 = v61;
        goto LABEL_18;
      }
      goto LABEL_52;
    }
    v28 = 0;
    if ( *(_DWORD *)(v11 + 36) )
      v28 = SmpToSpResiliencyType(v11 + *(unsigned int *)(v11 + 36), v24);
    if ( *(_DWORD *)(v11 + 8) >= 0x58u && *v20 && *(_DWORD *)(v11 + 8) >= 0x5Cu )
    {
      v29 = SmpToSpFaultDomainType(*(unsigned __int16 *)(v11 + 86));
      v30 = *(unsigned int *)(v11 + 88);
      v31 = v29;
      v32 = LocalAlloc(0x40u, 16 * *(_DWORD *)(v30 + v11) + 8LL);
      v68 = v32;
      v33 = v32;
      if ( !v32 )
      {
        v34 = _status_t::GetLastError((_status_t *)&v63);
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v66) = v34;
          LODWORD(v67) = 1702;
          v62 = (struct _SP_TIER_INFO *)"Spctl_Pool_CreateStorageTier_P1";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            dword_18039EB68,
            (unsigned int)byte_1803265C9,
            v35,
            v36,
            (__int64)&v62,
            (__int64)&v67,
            (__int64)&v66);
        }
LABEL_52:
        v7 = v61;
LABEL_53:
        v10 = v68;
        goto LABEL_54;
      }
      *v32 = v31;
      v43 = *(_DWORD *)(v30 + v11);
      v33[1] = v43;
      memcpy_0(v33 + 2, (const void *)(v30 + v11 + 4), 16LL * v43);
    }
    v7 = v61;
    if ( !(unsigned int)SuGetTierTemplate(v61, v28, v68, &v62) )
    {
      v44 = _status_t::GetLastError((_status_t *)&v63);
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v66) = v44;
        LODWORD(v67) = 1742;
        v61 = (struct _SU_POOL_OBJECT *)"Spctl_Pool_CreateStorageTier_P1";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          dword_18039EB68,
          (unsigned int)word_1803270F2,
          v45,
          v46,
          (__int64)&v61,
          (__int64)&v67,
          (__int64)&v66);
      }
      v8 = v62;
      goto LABEL_53;
    }
    v47 = *(_BYTE *)(v11 + 60);
    if ( *(_DWORD *)(v11 + 8) < 0x54u || !*(_BYTE *)(v11 + 80) )
      v15 = 0;
    v8 = v62;
    if ( *(_DWORD *)(v11 + 24)
      && (int)StringCchCopyW(
                (unsigned __int16 *)v62 + 28,
                0x100u,
                (const unsigned __int16 *)(v11 + *(unsigned int *)(v11 + 24))) < 0 )
    {
      LODWORD(v63) = -2060451835;
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_53;
      LODWORD(v67) = 1760;
      v50 = byte_1803276CB;
LABEL_76:
      v62 = (struct _SP_TIER_INFO *)"Spctl_Pool_CreateStorageTier_P1";
      LODWORD(v66) = -2060451835;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        -2060451835,
        (_DWORD)v50,
        v48,
        v49,
        (__int64)&v62,
        (__int64)&v67,
        (__int64)&v66);
      goto LABEL_53;
    }
    if ( *(_DWORD *)(v11 + 28)
      && (int)StringCchCopyW(
                (unsigned __int16 *)v8 + 284,
                0x400u,
                (const unsigned __int16 *)(v11 + *(unsigned int *)(v11 + 28))) < 0 )
    {
      LODWORD(v63) = -2060451835;
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_53;
      LODWORD(v67) = 1771;
      v50 = byte_180323D45;
      goto LABEL_76;
    }
    if ( *(_DWORD *)(v11 + 8) >= 0x60u && *(_BYTE *)(v11 + 92) )
      *((_DWORD *)v8 + 654) = *(unsigned __int16 *)(v11 + 94);
    if ( *(_DWORD *)(v11 + 8) >= 0x48u && *(_BYTE *)(v11 + 68) )
      *((_DWORD *)v8 + 662) = SmpToSpProvisioningType(*(unsigned __int16 *)(v11 + 70));
    if ( *(_DWORD *)(v11 + 8) >= 0x70u && *(_BYTE *)(v11 + 96) )
      *((_QWORD *)v8 + 332) = *(_QWORD *)(v11 + 104);
    v51 = *(_DWORD *)(v11 + 32);
    if ( v51 )
      *((_DWORD *)v8 + 666) = v51;
    if ( *(_DWORD *)(v11 + 8) >= 0x4Cu )
    {
      if ( *(_BYTE *)(v11 + 72) )
      {
        v52 = SmpToSpFaultDomainType(*(unsigned __int16 *)(v11 + 74));
        *((_DWORD *)v8 + 669) = v52;
        if ( v28 == 3 )
          *((_DWORD *)v8 + 667) = v52;
      }
    }
    if ( *(_DWORD *)(v11 + 8) >= 0x50u && *(_BYTE *)(v11 + 76) )
      *((_DWORD *)v8 + 667) = SmpToSpFaultDomainType(*(unsigned __int16 *)(v11 + 78));
    if ( v47 )
    {
      v53 = *(unsigned __int16 *)(v11 + 62);
      if ( !v15 )
      {
        SP_RESILIENCY_INFO::SetFaultTolerance((struct _SP_TIER_INFO *)((char *)v8 + 2692), v53);
        goto LABEL_107;
      }
      *((_DWORD *)v8 + 674) = v53;
    }
    else if ( !v15 )
    {
LABEL_107:
      if ( *(_DWORD *)(v11 + 8) >= 0x44u && *(_BYTE *)(v11 + 64) )
      {
        v55 = -1;
        if ( *(_WORD *)(v11 + 66) == 0xFFFF )
          v56 = -1;
        else
          v56 = *(unsigned __int16 *)(v11 + 66);
        *((_DWORD *)v8 + 676) = v56;
      }
      else
      {
        v55 = -1;
      }
      if ( *(_BYTE *)(v11 + 56) )
      {
        if ( *(_WORD *)(v11 + 58) != 0xFFFF )
          v55 = *(unsigned __int16 *)(v11 + 58);
        *((_DWORD *)v8 + 677) = v55;
      }
      if ( *(_BYTE *)(v11 + 40) )
        *((_DWORD *)v8 + 678) = *(_DWORD *)(v11 + 48);
      v37 = v60;
      if ( !(unsigned int)SuexCreateTier(v7, v8, (unsigned __int16 *const)(v60 + 4)) )
      {
        v57 = _status_t::GetLastError((_status_t *)&v63);
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v66) = v57;
          LODWORD(v67) = 1860;
          v62 = (struct _SP_TIER_INFO *)"Spctl_Pool_CreateStorageTier_P1";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            dword_18039EB68,
            (unsigned int)byte_180326509,
            v58,
            v59,
            (__int64)&v62,
            (__int64)&v67,
            (__int64)&v66);
        }
      }
      v10 = v68;
      goto LABEL_55;
    }
    v54 = *(unsigned __int16 *)(v11 + 82);
    if ( v47 )
      *((_DWORD *)v8 + 675) = v54;
    else
      SP_RESILIENCY_INFO::SetNumberOfCopies((struct _SP_TIER_INFO *)((char *)v8 + 2692), v54);
    goto LABEL_107;
  }
  v13 = 87;
LABEL_54:
  v37 = v60;
LABEL_55:
  v38 = v65;
  v39 = *((_QWORD *)v65 + 74);
  v40 = _status_t::ToSMRC(&v63);
  _FillMethodResponse(v37, *((unsigned int *)v38 + 146), v40, 0, v39);
  if ( v8 )
    LocalFree(v8);
  if ( v10 )
    LocalFree(v10);
  if ( v7 )
    LocalFree(v7);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v65) = 1877;
    v66 = (unsigned __int64)"Spctl_Pool_CreateStorageTier_P1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_18039EB68,
      (unsigned int)byte_1803255CB,
      v41,
      v42,
      (__int64)&v66,
      (__int64)&v65);
  }
  return v13;
}

```

## disassembly

```asm
0x18009fb5c  mov     [rsp-40h+arg_0], rcx
0x18009fb61  push    rbp
0x18009fb62  push    rbx
0x18009fb63  push    rsi
0x18009fb64  push    rdi
0x18009fb65  push    r12
0x18009fb67  push    r13
0x18009fb69  push    r14
0x18009fb6b  push    r15
0x18009fb6d  mov     rbp, rsp
0x18009fb70  sub     rsp, 78h
0x18009fb74  mov     eax, cs:dword_18039EB68
0x18009fb7a  mov     r12, rcx
0x18009fb7d  lea     rcx, aSpctlPoolCreat_0; "Spctl_Pool_CreateStorageTier_P1"
0x18009fb84  cmp     eax, 5
0x18009fb87  jbe     short loc_18009FBB2
0x18009fb89  lea     rax, [rbp+arg_8]
0x18009fb8d  mov     dword ptr [rbp+arg_8], 5C9h
0x18009fb94  mov     [rsp+78h+var_50], rax
0x18009fb99  lea     rdx, byte_180320A55
0x18009fba0  lea     rax, [rbp+arg_10]
0x18009fba4  mov     [rbp+arg_10], rcx
0x18009fba8  mov     [rsp+78h+var_58], rax
0x18009fbad  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009fbb2  mov     eax, [r12+238h]
0x18009fbba  xor     r11d, r11d
0x18009fbbd  mov     [rbp+var_30], r11
0x18009fbc1  mov     r15d, r11d
0x18009fbc4  mov     [rbp+var_20], r11
0x18009fbc8  mov     esi, r11d
0x18009fbcb  mov     [rbp+var_18], r11b
0x18009fbcf  mov     [rbp+var_28], r11
0x18009fbd3  cmp     eax, 18h
0x18009fbd6  jnb     short loc_18009FBE2
0x18009fbd8  mov     eax, 57h ; 'W'
0x18009fbdd  jmp     loc_18009FF31
0x18009fbe2  mov     ecx, 220h
0x18009fbe7  cmp     [r12+248h], ecx
0x18009fbef  jnb     short loc_18009FBFD
0x18009fbf1  mov     rax, [r12+250h]
0x18009fbf9  mov     [rax], ecx
0x18009fbfb  jmp     short loc_18009FBD8
0x18009fbfd  mov     rcx, [r12+240h]
0x18009fc05  mov     r13, r11
0x18009fc08  mov     rbx, [r12+230h]
0x18009fc10  mov     [rbp+var_38], rcx
0x18009fc14  mov     [rbp+arg_18], r11
0x18009fc18  mov     ecx, [rbx+0Ch]
0x18009fc1b  cmp     eax, ecx
0x18009fc1d  jb      short loc_18009FC2E
0x18009fc1f  cmp     dword ptr [rbx+10h], 7E0h
0x18009fc26  jnz     short loc_18009FC2E
0x18009fc28  cmp     dword ptr [rbx+8], 54h ; 'T'
0x18009fc2c  jnb     short loc_18009FC38
0x18009fc2e  mov     edi, 57h ; 'W'
0x18009fc33  jmp     loc_18009FE86
0x18009fc38  cmp     ecx, [rbx+8]
0x18009fc3b  jb      short loc_18009FC2E
0x18009fc3d  mov     eax, [rbx+24h]
0x18009fc40  mov     r13b, 1
0x18009fc43  test    eax, eax
0x18009fc45  jz      short loc_18009FC77
0x18009fc47  cmp     eax, [rbx+8]
0x18009fc4a  jb      short loc_18009FC6A
0x18009fc4c  cmp     eax, ecx
0x18009fc4e  ja      short loc_18009FC6A
0x18009fc50  test    r13b, al
0x18009fc53  jnz     short loc_18009FC6A
0x18009fc55  sub     ecx, eax
0x18009fc57  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x18009fc5b  mov     edx, ecx; unsigned __int64
0x18009fc5d  lea     rcx, [rbx+rax]; unsigned __int16 *
0x18009fc61  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009fc66  test    eax, eax
0x18009fc68  jns     short loc_18009FC77
0x18009fc6a  mov     edi, 57h ; 'W'
0x18009fc6f  mov     r13, rsi
0x18009fc72  jmp     loc_18009FE86
0x18009fc77  mov     eax, [rbx+18h]
0x18009fc7a  test    eax, eax
0x18009fc7c  jz      short loc_18009FCA4
0x18009fc7e  cmp     eax, [rbx+8]
0x18009fc81  jb      short loc_18009FC6A
0x18009fc83  mov     ecx, [rbx+0Ch]
0x18009fc86  cmp     eax, ecx
0x18009fc88  ja      short loc_18009FC6A
0x18009fc8a  test    r13b, al
0x18009fc8d  jnz     short loc_18009FC6A
0x18009fc8f  sub     ecx, eax
0x18009fc91  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x18009fc95  mov     edx, ecx; unsigned __int64
0x18009fc97  lea     rcx, [rbx+rax]; unsigned __int16 *
0x18009fc9b  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009fca0  test    eax, eax
0x18009fca2  js      short loc_18009FC6A
0x18009fca4  mov     eax, [rbx+1Ch]
0x18009fca7  test    eax, eax
0x18009fca9  jz      short loc_18009FCD1
0x18009fcab  cmp     eax, [rbx+8]
0x18009fcae  jb      short loc_18009FC6A
0x18009fcb0  mov     ecx, [rbx+0Ch]
0x18009fcb3  cmp     eax, ecx
0x18009fcb5  ja      short loc_18009FC6A
0x18009fcb7  test    r13b, al
0x18009fcba  jnz     short loc_18009FC6A
0x18009fcbc  sub     ecx, eax
0x18009fcbe  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x18009fcc2  mov     edx, ecx; unsigned __int64
0x18009fcc4  lea     rcx, [rbx+rax]; unsigned __int16 *
0x18009fcc8  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009fccd  test    eax, eax
0x18009fccf  js      short loc_18009FC6A
0x18009fcd1  cmp     dword ptr [rbx+8], 58h ; 'X'
0x18009fcd5  lea     r14, [rbx+54h]
0x18009fcd9  mov     r8d, 0FFFFFFFFh
0x18009fcdf  jb      short loc_18009FD45
0x18009fce1  cmp     [r14], r11b
0x18009fce4  jz      short loc_18009FD45
0x18009fce6  cmp     dword ptr [rbx+8], 5Ch ; '\'
0x18009fcea  jb      short loc_18009FD45
0x18009fcec  mov     eax, [rbx+58h]
0x18009fcef  test    eax, eax
0x18009fcf1  jz      short loc_18009FD45
0x18009fcf3  cmp     eax, [rbx+8]
0x18009fcf6  jb      loc_18009FC6A
0x18009fcfc  cmp     eax, [rbx+0Ch]
0x18009fcff  ja      loc_18009FC6A
0x18009fd05  test    al, 3
0x18009fd07  jnz     loc_18009FC6A
0x18009fd0d  lea     ecx, [rax+4]
0x18009fd10  cmp     ecx, eax
0x18009fd12  jb      loc_18009FC6A
0x18009fd18  cmp     ecx, [rbx+0Ch]
0x18009fd1b  ja      loc_18009FC6A
0x18009fd21  mov     edx, [rax+rbx]
0x18009fd24  shl     rdx, 4
0x18009fd28  cmp     rdx, r8
0x18009fd2b  ja      loc_18009FC6A
0x18009fd31  lea     eax, [rdx+rcx]
0x18009fd34  cmp     eax, ecx
0x18009fd36  jb      loc_18009FC6A
0x18009fd3c  cmp     eax, [rbx+0Ch]
0x18009fd3f  ja      loc_18009FC6A
0x18009fd45  lea     rcx, [r12+4]; struct _GUID *
0x18009fd4a  mov     edx, 2; unsigned int
0x18009fd4f  lea     r8, [rbp+var_30]; struct _SU_POOL_OBJECT **
0x18009fd53  mov     edi, r11d
0x18009fd56  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x18009fd5b  test    eax, eax
0x18009fd5d  jnz     short loc_18009FDBC
0x18009fd5f  lea     rcx, [rbp+var_20]; this
0x18009fd63  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x18009fd68  mov     ecx, cs:dword_18039EB68
0x18009fd6e  cmp     ecx, 2
0x18009fd71  jbe     loc_18009FE7E
0x18009fd77  mov     dword ptr [rbp+arg_8], eax
0x18009fd7a  lea     rdx, unk_180324950
0x18009fd81  lea     rax, aSpctlPoolCreat_0; "Spctl_Pool_CreateStorageTier_P1"
0x18009fd88  mov     dword ptr [rbp+arg_10], 691h
0x18009fd8f  mov     [rbp+var_28], rax
0x18009fd93  lea     rax, [rbp+arg_8]
0x18009fd97  mov     [rsp+78h+var_48], rax
0x18009fd9c  lea     rax, [rbp+arg_10]
0x18009fda0  mov     [rsp+78h+var_50], rax
0x18009fda5  lea     rax, [rbp+var_28]
0x18009fda9  mov     [rsp+78h+var_58], rax
0x18009fdae  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009fdb3  mov     r15, [rbp+var_30]
0x18009fdb7  jmp     loc_18009FC6F
0x18009fdbc  xor     r12d, r12d
0x18009fdbf  cmp     [rbx+24h], esi
0x18009fdc2  jz      short loc_18009FDD2
0x18009fdc4  mov     ecx, [rbx+24h]
0x18009fdc7  add     rcx, rbx
0x18009fdca  call    ?SmpToSpResiliencyType@@YA?AW4_SP_RESILIENCY_TYPE@@PEBG@Z; SmpToSpResiliencyType(ushort const *)
0x18009fdcf  mov     r12d, eax
0x18009fdd2  cmp     dword ptr [rbx+8], 58h ; 'X'
0x18009fdd6  jb      loc_18009FF64
0x18009fddc  cmp     [r14], sil
0x18009fddf  jz      loc_18009FF64
0x18009fde5  cmp     dword ptr [rbx+8], 5Ch ; '\'
0x18009fde9  jb      loc_18009FF64
0x18009fdef  movzx   ecx, word ptr [rbx+56h]
0x18009fdf3  call    ?SmpToSpFaultDomainType@@YA?AW4_SC_FD_TYPE@@G@Z; SmpToSpFaultDomainType(ushort)
0x18009fdf8  mov     r14d, [rbx+58h]
0x18009fdfc  mov     r15d, eax
0x18009fdff  mov     ecx, [r14+rbx]
0x18009fe03  shl     ecx, 4
0x18009fe06  movsxd  rdx, ecx
0x18009fe09  mov     ecx, 40h ; '@'; uFlags
0x18009fe0e  add     rdx, 8; uBytes
0x18009fe12  call    cs:__imp_LocalAlloc
0x18009fe19  nop     dword ptr [rax+rax+00h]
0x18009fe1e  mov     [rbp+arg_18], rax
0x18009fe22  mov     rcx, rax
0x18009fe25  test    rax, rax
0x18009fe28  jnz     loc_18009FF43
0x18009fe2e  lea     rcx, [rbp+var_20]; this
0x18009fe32  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x18009fe37  mov     ecx, cs:dword_18039EB68
0x18009fe3d  cmp     ecx, 2
0x18009fe40  jbe     short loc_18009FE7E
0x18009fe42  mov     dword ptr [rbp+arg_8], eax
0x18009fe45  lea     rdx, byte_1803265C9
0x18009fe4c  lea     rax, aSpctlPoolCreat_0; "Spctl_Pool_CreateStorageTier_P1"
0x18009fe53  mov     dword ptr [rbp+arg_10], 6A6h
0x18009fe5a  mov     [rbp+var_28], rax
0x18009fe5e  lea     rax, [rbp+arg_8]
0x18009fe62  mov     [rsp+78h+var_48], rax
0x18009fe67  lea     rax, [rbp+arg_10]
0x18009fe6b  mov     [rsp+78h+var_50], rax
0x18009fe70  lea     rax, [rbp+var_28]
0x18009fe74  mov     [rsp+78h+var_58], rax
0x18009fe79  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009fe7e  mov     r15, [rbp+var_30]
0x18009fe82  mov     r13, [rbp+arg_18]
0x18009fe86  mov     r12, [rbp+var_38]
0x18009fe8a  mov     r14, [rbp+arg_0]
0x18009fe8e  lea     rcx, [rbp+var_20]
0x18009fe92  mov     rbx, [r14+250h]
0x18009fe99  call    ?ToSMRC@_status_t@@QEAA?AW4SM_RETURN_CODE@@XZ; _status_t::ToSMRC(void)
0x18009fe9e  mov     edx, [r14+248h]
0x18009fea5  xor     r9d, r9d
0x18009fea8  mov     r8d, eax
0x18009feab  mov     [rsp+78h+var_58], rbx
0x18009feb0  mov     rcx, r12
0x18009feb3  call    ?_FillMethodResponse@@YAXPEAEKW4SM_RETURN_CODE@@PEAU_SUEX_EXTENDEDSTATUS_OBJECT@@PEAK@Z; _FillMethodResponse(uchar *,ulong,SM_RETURN_CODE,_SUEX_EXTENDEDSTATUS_OBJECT *,ulong *)
0x18009feb8  test    rsi, rsi
0x18009febb  jz      short loc_18009FECC
0x18009febd  mov     rcx, rsi; hMem
0x18009fec0  call    cs:__imp_LocalFree
0x18009fec7  nop     dword ptr [rax+rax+00h]
0x18009fecc  test    r13, r13
0x18009fecf  jz      short loc_18009FEE0
0x18009fed1  mov     rcx, r13; hMem
0x18009fed4  call    cs:__imp_LocalFree
0x18009fedb  nop     dword ptr [rax+rax+00h]
0x18009fee0  test    r15, r15
0x18009fee3  jz      short loc_18009FEF4
0x18009fee5  mov     rcx, r15; hMem
0x18009fee8  call    cs:__imp_LocalFree
0x18009feef  nop     dword ptr [rax+rax+00h]
0x18009fef4  mov     ecx, cs:dword_18039EB68
0x18009fefa  cmp     ecx, 5
0x18009fefd  jbe     short loc_18009FF2F
0x18009feff  lea     rax, aSpctlPoolCreat_0; "Spctl_Pool_CreateStorageTier_P1"
0x18009ff06  mov     dword ptr [rbp+arg_0], 755h
0x18009ff0d  mov     [rbp+arg_8], rax
0x18009ff11  lea     rdx, byte_1803255CB
0x18009ff18  lea     rax, [rbp+arg_0]
0x18009ff1c  mov     [rsp+78h+var_50], rax
0x18009ff21  lea     rax, [rbp+arg_8]
0x18009ff25  mov     [rsp+78h+var_58], rax
0x18009ff2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009ff2f  mov     eax, edi
0x18009ff31  add     rsp, 78h
0x18009ff35  pop     r15
0x18009ff37  pop     r14
0x18009ff39  pop     r13
0x18009ff3b  pop     r12
0x18009ff3d  pop     rdi
0x18009ff3e  pop     rsi
0x18009ff3f  pop     rbx
0x18009ff40  pop     rbp
0x18009ff41  retn
0x18009ff43  mov     [rax], r15d
0x18009ff46  lea     rdx, [rbx+4]
0x18009ff4a  mov     eax, [r14+rbx]
0x18009ff4e  add     rdx, r14; Src
0x18009ff51  mov     r8d, eax
0x18009ff54  mov     [rcx+4], eax
0x18009ff57  shl     r8, 4; Size
0x18009ff5b  add     rcx, 8; void *
0x18009ff5f  call    memcpy_0
0x18009ff64  mov     r15, [rbp+var_30]
0x18009ff68  lea     r9, [rbp+var_28]
0x18009ff6c  mov     r8, [rbp+arg_18]
0x18009ff70  mov     rcx, r15
0x18009ff73  mov     edx, r12d
0x18009ff76  call    ?SuGetTierTemplate@@YAHPEAU_SU_POOL_OBJECT@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_FD_IDS@@PEAPEAU_SP_TIER_INFO@@@Z; SuGetTierTemplate(_SU_POOL_OBJECT *,_SP_RESILIENCY_TYPE,_SP_FD_IDS *,_SP_TIER_INFO * *)
0x18009ff7b  xor     r14d, r14d
0x18009ff7e  test    eax, eax
0x18009ff80  jnz     short loc_18009FFDB
0x18009ff82  lea     rcx, [rbp+var_20]; this
0x18009ff86  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x18009ff8b  mov     ecx, cs:dword_18039EB68
0x18009ff91  cmp     ecx, 2
0x18009ff94  jbe     short loc_18009FFD2
0x18009ff96  mov     dword ptr [rbp+arg_8], eax
0x18009ff99  lea     rdx, word_1803270F2
0x18009ffa0  lea     rax, aSpctlPoolCreat_0; "Spctl_Pool_CreateStorageTier_P1"
0x18009ffa7  mov     dword ptr [rbp+arg_10], 6CEh
0x18009ffae  mov     [rbp+var_30], rax
0x18009ffb2  lea     rax, [rbp+arg_8]
0x18009ffb6  mov     [rsp+78h+var_48], rax
0x18009ffbb  lea     rax, [rbp+arg_10]
0x18009ffbf  mov     [rsp+78h+var_50], rax
0x18009ffc4  lea     rax, [rbp+var_30]
0x18009ffc8  mov     [rsp+78h+var_58], rax
0x18009ffcd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
  ... truncated ...
```
