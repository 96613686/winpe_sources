# IPolicyWriter::WriteSpecialFwRule(_tag_FW_RULE *,_LIST_ENTRY *,_tag_FW_OBJECT_METADATA *)

- ea: `0x180022ad0`
- end: `0x18002354c`
- name: `?WriteSpecialFwRule@IPolicyWriter@@QEAAJPEAU_tag_FW_RULE@@PEAU_LIST_ENTRY@@PEAU_tag_FW_OBJECT_METADATA@@@Z`
- size: `2684`
- prototype: `int(IPolicyWriter *__hidden this, struct _tag_FW_RULE *, struct _LIST_ENTRY *, struct _tag_FW_OBJECT_METADATA *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022ab0`

## callees

- `0x18000af3c`
- `0x180022a14`
- `0x180022ad0`
- `0x180024380`
- `0x180024770`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022b3a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022b64`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022bc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022bf0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022c1b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022c46`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022c71`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022c9c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022cc7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022cf2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022d1d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022d48`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022d76`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022e47`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022fbe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022fec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180023034`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180023220`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180023337`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022b3a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022b64`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022bc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022bf0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022c1b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022c46`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022c71`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022c9c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022cc7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022cf2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022d1d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022d48`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022d76`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022e47`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022fbe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022fec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180023034`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180023220`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180023337`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180022df9`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180022e67`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180023237`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180022df9`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180022e67`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180023237`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x180022dbe`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x180022dbe`

## pseudocode

```c
__int64 __fastcall IPolicyWriter::WriteSpecialFwRule(
        IPolicyWriter *this,
        LPCWCH *a2,
        struct _LIST_ENTRY *a3,
        struct _tag_FW_OBJECT_METADATA *a4)
{
  IPolicyWriter *v4; // rdi
  __int64 result; // rax
  int v9; // r14d
  __int64 ProfileIndexFromProfileType; // r15
  int v11; // r14d
  int v12; // r12d
  __int64 v13; // rdx
  int *v14; // r13
  _BYTE *v15; // rcx
  __int64 v16; // rdx
  LPCWCH *v17; // rax
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  LPCWCH v32; // rax
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rdx
  int v36; // ecx
  LPCWCH *v37; // rax
  _BYTE *v38; // rcx
  __int64 v39; // r15
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  LPCWCH v54; // rax
  _BYTE v55[40]; // [rsp+40h] [rbp-248h] BYREF
  unsigned int v56; // [rsp+68h] [rbp-220h]
  int v57; // [rsp+6Ch] [rbp-21Ch]
  int v58; // [rsp+160h] [rbp-128h]
  int v59; // [rsp+190h] [rbp-F8h]

  v4 = pWriterModule;
  memset_0(v55, 0, 0x1F8u);
  if ( CompareStringOrdinal(a2[39], -1, L"AppCDefaultRule", -1, 1) == 2 )
  {
    if ( CompareStringOrdinal(a2[3], -1, L"PrivateNetwork Inbound Default Rule", -1, 1) == 2
      && !(*(unsigned int (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 192LL))(v4, 1)
      || CompareStringOrdinal(a2[3], -1, L"PrivateNetwork Outbound Default Rule", -1, 1) == 2
      && !(*(unsigned int (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 192LL))(v4, 2)
      || CompareStringOrdinal(a2[3], -1, L"RemotePrivNetwork Inbound Default Rule", -1, 1) == 2
      && !(*(unsigned int (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 192LL))(v4, 3)
      || CompareStringOrdinal(a2[3], -1, L"RemotePrivNetwork Outbound Default Rule", -1, 1) == 2
      && !(*(unsigned int (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 192LL))(v4, 4)
      || CompareStringOrdinal(a2[3], -1, L"InternetClientServer Inbound Default Rule", -1, 1) == 2
      && !(*(unsigned int (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 192LL))(v4, 5)
      || CompareStringOrdinal(a2[3], -1, L"InternetClientServer Outbound Default Rule", -1, 1) == 2
      && !(*(unsigned int (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 192LL))(v4, 6)
      || CompareStringOrdinal(a2[3], -1, L"InternetClient Default Rule", -1, 1) == 2
      && !(*(unsigned int (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 192LL))(v4, 7)
      || CompareStringOrdinal(a2[3], -1, L"Block Inbound Default Rule", -1, 1) == 2
      && !(*(unsigned int (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 192LL))(v4, 8)
      || CompareStringOrdinal(a2[3], -1, L"Block Outbound Default Rule", -1, 1) == 2
      && !(*(unsigned int (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 192LL))(v4, 9) )
    {
      return 0;
    }
    if ( CompareStringOrdinal(a2[3], -1, L"Block Inbound Default Rule", -1, 1) == 2
      || (v9 = 0, CompareStringOrdinal(a2[3], -1, L"Block Outbound Default Rule", -1, 1) == 2) )
    {
      v9 = 1;
    }
    (*(void (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 88LL))(v4, 14);
    return IPolicyWriter::WriteFwRule(v4, 0x7FFFFFFFu, (struct _tag_FW_RULE *)a2, v9, a3, a4);
  }
  if ( CompareStringOrdinal(a2[39], -1, L"CSAddressIso", -1, 1) != 2 )
  {
    ProfileIndexFromProfileType = (int)FwGetProfileIndexFromProfileType(*((unsigned int *)a2 + 10));
    if ( (dword_1801313E8 & 4) != 0
      && (CompareStringOrdinal(a2[39], -1, L"DefaultActions", -1, 1) != 2 || (dword_1801313E8 & 1) != 0) )
    {
      FwMetaDataAddEnforcementState(a4, 3);
      return 0;
    }
    v11 = 0;
    if ( (dword_18012F89C & 4) != 0 )
      v12 = 4;
    else
      v12 = ((dword_18012F89C & 2) != 0) + 1;
    if ( (dword_18012F89C & (_DWORD)a2[5]) == 0 )
    {
      v13 = 5;
LABEL_23:
      FwMetaDataAddEnforcementState(a4, v13);
      return 0;
    }
    v14 = &dword_18012F6B8[40 * ProfileIndexFromProfileType];
    if ( !*v14
      && (CompareStringOrdinal(a2[39], -1, L"DefaultActions", -1, 1) != 2
       || !*v14 && *((_DWORD *)a2 + 72) == 2 && (unsigned int)FwHasSingleProfile((unsigned int)dword_18012F89C))
      || !(unsigned int)GetFwONProfiles() )
    {
      FwMetaDataAddEnforcementState(a4, 2);
      return 0;
    }
    if ( (*((_BYTE *)a2 + 292) & 1) == 0 || ((_BYTE)a2[53] & 8) != 0 )
    {
      v13 = 4;
      goto LABEL_23;
    }
    v15 = v55;
    v16 = 3;
    v17 = a2;
    do
    {
      v15 += 128;
      v18 = *(_OWORD *)v17;
      v19 = *((_OWORD *)v17 + 1);
      v17 += 16;
      *((_OWORD *)v15 - 8) = v18;
      v20 = *((_OWORD *)v17 - 6);
      *((_OWORD *)v15 - 7) = v19;
      v21 = *((_OWORD *)v17 - 5);
      *((_OWORD *)v15 - 6) = v20;
      v22 = *((_OWORD *)v17 - 4);
      *((_OWORD *)v15 - 5) = v21;
      v23 = *((_OWORD *)v17 - 3);
      *((_OWORD *)v15 - 4) = v22;
      v24 = *((_OWORD *)v17 - 2);
      *((_OWORD *)v15 - 3) = v23;
      v25 = *((_OWORD *)v17 - 1);
      *((_OWORD *)v15 - 2) = v24;
      *((_OWORD *)v15 - 1) = v25;
      --v16;
    }
    while ( v16 );
    v26 = *((_OWORD *)v17 + 1);
    *(_OWORD *)v15 = *(_OWORD *)v17;
    v27 = *((_OWORD *)v17 + 2);
    *((_OWORD *)v15 + 1) = v26;
    v28 = *((_OWORD *)v17 + 3);
    *((_OWORD *)v15 + 2) = v27;
    v29 = *((_OWORD *)v17 + 4);
    *((_OWORD *)v15 + 3) = v28;
    v30 = *((_OWORD *)v17 + 5);
    *((_OWORD *)v15 + 4) = v29;
    v31 = *((_OWORD *)v17 + 6);
    v32 = v17[14];
    *((_OWORD *)v15 + 5) = v30;
    *((_OWORD *)v15 + 6) = v31;
    *((_QWORD *)v15 + 14) = v32;
    if ( CompareStringOrdinal(a2[39], -1, L"ShieldedMode", -1, 1) == 2
      || CompareStringOrdinal(a2[39], -1, L"DisabledIntf", -1, 1) == 2
      || ((*(__int64 (__fastcall **)(IPolicyWriter *))(*(_QWORD *)v4 + 208LL))(v4) & 8) != 0
      && CompareStringOrdinal(a2[39], -1, L"ExemptIKE", -1, 1) == 2 )
    {
      (*(void (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 88LL))(v4, 2);
      LOBYTE(v11) = (unsigned int)FwHasSingleProfile((unsigned int)dword_18012F89C) != 0;
      v36 = v11 | 2;
      if ( (v56 & v12) == 0 )
        v36 = v11;
      v11 = (*(__int64 (__fastcall **)(IPolicyWriter *, _BYTE *, struct _LIST_ENTRY *, struct _tag_FW_OBJECT_METADATA *, unsigned int, int))(*(_QWORD *)v4 + 128LL))(
              v4,
              v55,
              a3,
              a4,
              v56,
              v36);
      if ( v11 < 0 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          return (unsigned int)v11;
        v35 = 25;
LABEL_74:
        WPP_SF_d(*(_QWORD *)(v34 + 16), v35, WPP_e5185af2dab037bd3b14417321eb8906_Traceguids, (unsigned int)v11);
        return (unsigned int)v11;
      }
    }
    else if ( CompareStringOrdinal(a2[39], -1, L"DefaultActions", -1, 1) == 2 )
    {
      (*(void (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 88LL))(v4, 5);
      if ( !*v14 || (dword_1801313E8 & 4) != 0 )
      {
        v33 = v58;
        if ( *((_DWORD *)a2 + 72) == 2 )
          v33 = 3;
        v58 = v33;
      }
      else
      {
        v33 = v58;
      }
      if ( v57 == 1 && v33 == 2 )
      {
        v11 = (*(__int64 (__fastcall **)(IPolicyWriter *, _QWORD, struct _LIST_ENTRY *, struct _tag_FW_OBJECT_METADATA *))(*(_QWORD *)v4 + 96LL))(
                v4,
                v56,
                a3,
                a4);
        if ( v11 < 0 )
        {
          v34 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            return (unsigned int)v11;
          v35 = 26;
          goto LABEL_74;
        }
        if ( (v12 & v56) != 0 )
        {
          (*(void (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 88LL))(v4, 10);
          v11 = (*(__int64 (__fastcall **)(IPolicyWriter *, __int64, struct _LIST_ENTRY *, struct _tag_FW_OBJECT_METADATA *))(*(_QWORD *)v4 + 96LL))(
                  v4,
                  0x7FFFFFFF,
                  a3,
                  a4);
          if ( v11 < 0 )
          {
            v34 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              return (unsigned int)v11;
            }
            v35 = 27;
            goto LABEL_74;
          }
        }
      }
      else
      {
        v11 = (*(__int64 (__fastcall **)(IPolicyWriter *, _BYTE *, struct _LIST_ENTRY *, struct _tag_FW_OBJECT_METADATA *, unsigned int, int))(*(_QWORD *)v4 + 128LL))(
                v4,
                v55,
                a3,
                a4,
                v56,
                (v12 & v56) != 0 ? 2 : 0);
        if ( v11 < 0 )
        {
          v34 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            return (unsigned int)v11;
          v35 = 28;
          goto LABEL_74;
        }
      }
    }
    *((_DWORD *)a2 + 84) = v59;
    return (unsigned int)v11;
  }
  if ( ((*(__int64 (__fastcall **)(IPolicyWriter *))(*(_QWORD *)v4 + 208LL))(v4) & 8) == 0 )
    return 0;
  (*(void (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 88LL))(v4, 2);
  v37 = a2;
  v38 = v55;
  v39 = 3;
  do
  {
    v38 += 128;
    v40 = *(_OWORD *)v37;
    v41 = *((_OWORD *)v37 + 1);
    v37 += 16;
    *((_OWORD *)v38 - 8) = v40;
    v42 = *((_OWORD *)v37 - 6);
    *((_OWORD *)v38 - 7) = v41;
    v43 = *((_OWORD *)v37 - 5);
    *((_OWORD *)v38 - 6) = v42;
    v44 = *((_OWORD *)v37 - 4);
    *((_OWORD *)v38 - 5) = v43;
    v45 = *((_OWORD *)v37 - 3);
    *((_OWORD *)v38 - 4) = v44;
    v46 = *((_OWORD *)v37 - 2);
    *((_OWORD *)v38 - 3) = v45;
    v47 = *((_OWORD *)v37 - 1);
    *((_OWORD *)v38 - 2) = v46;
    *((_OWORD *)v38 - 1) = v47;
    --v39;
  }
  while ( v39 );
  v48 = *((_OWORD *)v37 + 1);
  *(_OWORD *)v38 = *(_OWORD *)v37;
  v49 = *((_OWORD *)v37 + 2);
  *((_OWORD *)v38 + 1) = v48;
  v50 = *((_OWORD *)v37 + 3);
  *((_OWORD *)v38 + 2) = v49;
  v51 = *((_OWORD *)v37 + 4);
  *((_OWORD *)v38 + 3) = v50;
  v52 = *((_OWORD *)v37 + 5);
  *((_OWORD *)v38 + 4) = v51;
  v53 = *((_OWORD *)v37 + 6);
  v54 = v37[14];
  *((_OWORD *)v38 + 5) = v52;
  *((_OWORD *)v38 + 6) = v53;
  *((_QWORD *)v38 + 14) = v54;
  result = (*(__int64 (__fastcall **)(IPolicyWriter *, _BYTE *, struct _LIST_ENTRY *, struct _tag_FW_OBJECT_METADATA *, unsigned int, unsigned int))(*(_QWORD *)v4 + 128LL))(
             v4,
             v55,
             a3,
             a4,
             v56,
             (*((int *)a2 + 88) >> 31) & 0x40 | 1u);
  v11 = result;
  if ( (int)result < 0 )
  {
    v34 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      return (unsigned int)v11;
    v35 = 24;
    goto LABEL_74;
  }
  return result;
}

```

## disassembly

```asm
0x180022ad0  mov     [rsp+arg_0], rbx
0x180022ad5  push    rbp
0x180022ad6  push    rsi
0x180022ad7  push    rdi
0x180022ad8  push    r12
0x180022ada  push    r13
0x180022adc  push    r14
0x180022ade  push    r15
0x180022ae0  sub     rsp, 250h
0x180022ae7  mov     rax, cs:__security_cookie
0x180022aee  xor     rax, rsp
0x180022af1  mov     [rsp+288h+var_48], rax
0x180022af9  mov     rdi, cs:pWriterModule
0x180022b00  lea     rcx, [rsp+288h+var_248]; void *
0x180022b05  mov     rbp, r8
0x180022b08  mov     rbx, rdx
0x180022b0b  xor     edx, edx; Val
0x180022b0d  mov     r8d, 1F8h; Size
0x180022b13  mov     rsi, r9
0x180022b16  call    memset_0
0x180022b1b  mov     rcx, [rbx+138h]; lpString1
0x180022b22  lea     r8, String2; "AppCDefaultRule"
0x180022b29  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022b2f  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022b37  mov     edx, r9d; cchCount1
0x180022b3a  call    cs:__imp_CompareStringOrdinal
0x180022b40  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022b46  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022b4e  mov     edx, r9d; cchCount1
0x180022b51  cmp     eax, 2
0x180022b54  jz      short loc_180022BBA
0x180022b56  mov     rcx, [rbx+138h]; lpString1
0x180022b5d  lea     r8, aCsaddressiso; "CSAddressIso"
0x180022b64  call    cs:__imp_CompareStringOrdinal
0x180022b6a  cmp     eax, 2
0x180022b6d  jnz     loc_180022DBB
0x180022b73  mov     rax, [rdi]
0x180022b76  mov     rcx, rdi
0x180022b79  mov     rax, [rax+0D0h]
0x180022b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b85  test    al, 8
0x180022b87  jnz     loc_1800233D7
0x180022b8d  xor     eax, eax
0x180022b8f  mov     rcx, [rsp+288h+var_48]
0x180022b97  xor     rcx, rsp; StackCookie
0x180022b9a  call    __security_check_cookie
0x180022b9f  mov     rbx, [rsp+288h+arg_0]
0x180022ba7  add     rsp, 250h
0x180022bae  pop     r15
0x180022bb0  pop     r14
0x180022bb2  pop     r13
0x180022bb4  pop     r12
0x180022bb6  pop     rdi
0x180022bb7  pop     rsi
0x180022bb8  pop     rbp
0x180022bb9  retn
0x180022bba  mov     rcx, [rbx+18h]; lpString1
0x180022bbe  lea     r8, aPrivatenetwork; "PrivateNetwork Inbound Default Rule"
0x180022bc5  call    cs:__imp_CompareStringOrdinal
0x180022bcb  cmp     eax, 2
0x180022bce  jz      loc_180023058
0x180022bd4  mov     rcx, [rbx+18h]; lpString1
0x180022bd8  lea     r8, aPrivatenetwork_0; "PrivateNetwork Outbound Default Rule"
0x180022bdf  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022be5  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022bed  mov     edx, r9d; cchCount1
0x180022bf0  call    cs:__imp_CompareStringOrdinal
0x180022bf6  cmp     eax, 2
0x180022bf9  jz      loc_1800230C4
0x180022bff  mov     rcx, [rbx+18h]; lpString1
0x180022c03  lea     r8, aRemoteprivnetw; "RemotePrivNetwork Inbound Default Rule"
0x180022c0a  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022c10  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022c18  mov     edx, r9d; cchCount1
0x180022c1b  call    cs:__imp_CompareStringOrdinal
0x180022c21  cmp     eax, 2
0x180022c24  jz      loc_180022E04
0x180022c2a  mov     rcx, [rbx+18h]; lpString1
0x180022c2e  lea     r8, aRemoteprivnetw_0; "RemotePrivNetwork Outbound Default Rule"
0x180022c35  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022c3b  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022c43  mov     edx, r9d; cchCount1
0x180022c46  call    cs:__imp_CompareStringOrdinal
0x180022c4c  cmp     eax, 2
0x180022c4f  jz      loc_180022E72
0x180022c55  mov     rcx, [rbx+18h]; lpString1
0x180022c59  lea     r8, aInternetclient_0; "InternetClientServer Inbound Default Ru"...
0x180022c60  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022c66  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022c6e  mov     edx, r9d; cchCount1
0x180022c71  call    cs:__imp_CompareStringOrdinal
0x180022c77  cmp     eax, 2
0x180022c7a  jz      loc_180022E96
0x180022c80  mov     rcx, [rbx+18h]; lpString1
0x180022c84  lea     r8, aInternetclient_1; "InternetClientServer Outbound Default R"...
0x180022c8b  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022c91  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022c99  mov     edx, r9d; cchCount1
0x180022c9c  call    cs:__imp_CompareStringOrdinal
0x180022ca2  cmp     eax, 2
0x180022ca5  jz      loc_1800230A0
0x180022cab  mov     rcx, [rbx+18h]; lpString1
0x180022caf  lea     r8, aInternetclient; "InternetClient Default Rule"
0x180022cb6  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022cbc  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022cc4  mov     edx, r9d; cchCount1
0x180022cc7  call    cs:__imp_CompareStringOrdinal
0x180022ccd  cmp     eax, 2
0x180022cd0  jz      loc_18002307C
0x180022cd6  mov     rcx, [rbx+18h]; lpString1
0x180022cda  lea     r8, aBlockInboundDe; "Block Inbound Default Rule"
0x180022ce1  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022ce7  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022cef  mov     edx, r9d; cchCount1
0x180022cf2  call    cs:__imp_CompareStringOrdinal
0x180022cf8  cmp     eax, 2
0x180022cfb  jz      loc_1800232C3
0x180022d01  mov     rcx, [rbx+18h]; lpString1
0x180022d05  lea     r8, aBlockOutboundD; "Block Outbound Default Rule"
0x180022d0c  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022d12  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022d1a  mov     edx, r9d; cchCount1
0x180022d1d  call    cs:__imp_CompareStringOrdinal
0x180022d23  cmp     eax, 2
0x180022d26  jz      loc_1800231DD
0x180022d2c  mov     rcx, [rbx+18h]; lpString1
0x180022d30  lea     r8, aBlockInboundDe; "Block Inbound Default Rule"
0x180022d37  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022d3d  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022d45  mov     edx, r9d; cchCount1
0x180022d48  call    cs:__imp_CompareStringOrdinal
0x180022d4e  cmp     eax, 2
0x180022d51  jz      loc_1800234F8
0x180022d57  mov     rcx, [rbx+18h]; lpString1
0x180022d5b  lea     r8, aBlockOutboundD; "Block Outbound Default Rule"
0x180022d62  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022d68  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022d70  mov     edx, r9d; cchCount1
0x180022d73  xor     r14d, r14d
0x180022d76  call    cs:__imp_CompareStringOrdinal
0x180022d7c  cmp     eax, 2
0x180022d7f  jz      loc_1800234F8
0x180022d85  mov     rax, [rdi]
0x180022d88  mov     edx, 0Eh
0x180022d8d  mov     rcx, rdi
0x180022d90  mov     rax, [rax+58h]
0x180022d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d99  mov     r9d, r14d; int
0x180022d9c  mov     [rsp+288h+var_260], rsi; struct _tag_FW_OBJECT_METADATA *
0x180022da1  mov     r8, rbx; struct _tag_FW_RULE *
0x180022da4  mov     qword ptr [rsp+288h+bIgnoreCase], rbp; struct _LIST_ENTRY *
0x180022da9  mov     edx, 7FFFFFFFh; unsigned int
0x180022dae  mov     rcx, rdi; this
0x180022db1  call    ?WriteFwRule@IPolicyWriter@@QEAAJKPEAU_tag_FW_RULE@@HPEAU_LIST_ENTRY@@PEAU_tag_FW_OBJECT_METADATA@@@Z; IPolicyWriter::WriteFwRule(ulong,_tag_FW_RULE *,int,_LIST_ENTRY *,_tag_FW_OBJECT_METADATA *)
0x180022db6  jmp     loc_180022B8F
0x180022dbb  mov     ecx, [rbx+28h]
0x180022dbe  call    cs:__imp_FwGetProfileIndexFromProfileType
0x180022dc4  test    byte ptr cs:dword_1801313E8, 4
0x180022dcb  movsxd  r15, eax
0x180022dce  jnz     short loc_180022E28
0x180022dd0  mov     edx, cs:dword_18012F89C
0x180022dd6  xor     r14d, r14d
0x180022dd9  test    dl, 4
0x180022ddc  jz      loc_1800230F2
0x180022de2  mov     r12d, 4
0x180022de8  test    [rbx+28h], edx
0x180022deb  jnz     loc_180022EBA
0x180022df1  mov     edx, 5
0x180022df6  mov     rcx, rsi
0x180022df9  call    cs:__imp_FwMetaDataAddEnforcementState
0x180022dff  jmp     loc_180022B8D
0x180022e04  mov     rax, [rdi]
0x180022e07  mov     edx, 3
0x180022e0c  mov     rcx, rdi
0x180022e0f  mov     rax, [rax+0C0h]
0x180022e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e1b  test    eax, eax
0x180022e1d  jz      loc_180022B8D
0x180022e23  jmp     loc_180022C2A
0x180022e28  mov     rcx, [rbx+138h]; lpString1
0x180022e2f  lea     r8, aDefaultactions; "DefaultActions"
0x180022e36  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022e3c  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022e44  mov     edx, r9d; cchCount1
0x180022e47  call    cs:__imp_CompareStringOrdinal
0x180022e4d  cmp     eax, 2
0x180022e50  jnz     short loc_180022E5F
0x180022e52  test    byte ptr cs:dword_1801313E8, 1
0x180022e59  jz      loc_180022DD0
0x180022e5f  mov     edx, 3
0x180022e64  mov     rcx, rsi
0x180022e67  call    cs:__imp_FwMetaDataAddEnforcementState
0x180022e6d  jmp     loc_180022B8D
0x180022e72  mov     rax, [rdi]
0x180022e75  mov     edx, 4
0x180022e7a  mov     rcx, rdi
0x180022e7d  mov     rax, [rax+0C0h]
0x180022e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e89  test    eax, eax
0x180022e8b  jz      loc_180022B8D
0x180022e91  jmp     loc_180022C55
0x180022e96  mov     rax, [rdi]
0x180022e99  mov     edx, 5
0x180022e9e  mov     rcx, rdi
0x180022ea1  mov     rax, [rax+0C0h]
0x180022ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ead  test    eax, eax
0x180022eaf  jz      loc_180022B8D
0x180022eb5  jmp     loc_180022C80
0x180022eba  lea     r13, [r15+r15*4]
0x180022ebe  shl     r13, 5
0x180022ec2  lea     rax, dword_18012F6B8
0x180022ec9  add     r13, rax
0x180022ecc  cmp     [r13+0], r14d
0x180022ed0  jz      loc_180023201
0x180022ed6  call    GetFwONProfiles
0x180022edb  test    eax, eax
0x180022edd  jz      loc_18002322F
0x180022ee3  test    byte ptr [rbx+124h], 1
0x180022eea  jz      loc_1800230E8
0x180022ef0  test    byte ptr [rbx+1A8h], 8
0x180022ef7  jnz     loc_1800230E8
0x180022efd  mov     r15d, 3
0x180022f03  lea     rcx, [rsp+288h+var_248]
0x180022f08  mov     edx, r15d
0x180022f0b  mov     rax, rbx
0x180022f0e  lea     rcx, [rcx+80h]
0x180022f15  movups  xmm0, xmmword ptr [rax]
0x180022f18  movups  xmm1, xmmword ptr [rax+10h]
0x180022f1c  lea     rax, [rax+80h]
0x180022f23  movups  xmmword ptr [rcx-80h], xmm0
0x180022f27  movups  xmm0, xmmword ptr [rax-60h]
0x180022f2b  movups  xmmword ptr [rcx-70h], xmm1
0x180022f2f  movups  xmm1, xmmword ptr [rax-50h]
0x180022f33  movups  xmmword ptr [rcx-60h], xmm0
0x180022f37  movups  xmm0, xmmword ptr [rax-40h]
0x180022f3b  movups  xmmword ptr [rcx-50h], xmm1
0x180022f3f  movups  xmm1, xmmword ptr [rax-30h]
0x180022f43  movups  xmmword ptr [rcx-40h], xmm0
0x180022f47  movups  xmm0, xmmword ptr [rax-20h]
0x180022f4b  movups  xmmword ptr [rcx-30h], xmm1
0x180022f4f  movups  xmm1, xmmword ptr [rax-10h]
0x180022f53  movups  xmmword ptr [rcx-20h], xmm0
0x180022f57  movups  xmmword ptr [rcx-10h], xmm1
0x180022f5b  sub     rdx, 1
0x180022f5f  jnz     short loc_180022F0E
0x180022f61  movups  xmm0, xmmword ptr [rax]
0x180022f64  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022f6a  lea     r8, aShieldedmode; "ShieldedMode"
0x180022f71  movups  xmm1, xmmword ptr [rax+10h]
0x180022f75  mov     edx, r9d; cchCount1
0x180022f78  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022f80  movups  xmmword ptr [rcx], xmm0
0x180022f83  movups  xmm0, xmmword ptr [rax+20h]
0x180022f87  movups  xmmword ptr [rcx+10h], xmm1
0x180022f8b  movups  xmm1, xmmword ptr [rax+30h]
0x180022f8f  movups  xmmword ptr [rcx+20h], xmm0
0x180022f93  movups  xmm0, xmmword ptr [rax+40h]
0x180022f97  movups  xmmword ptr [rcx+30h], xmm1
0x180022f9b  movups  xmm1, xmmword ptr [rax+50h]
0x180022f9f  movups  xmmword ptr [rcx+40h], xmm0
0x180022fa3  movups  xmm0, xmmword ptr [rax+60h]
0x180022fa7  mov     rax, [rax+70h]
0x180022fab  movups  xmmword ptr [rcx+50h], xmm1
0x180022faf  movups  xmmword ptr [rcx+60h], xmm0
0x180022fb3  mov     [rcx+70h], rax
0x180022fb7  mov     rcx, [rbx+138h]; lpString1
0x180022fbe  call    cs:__imp_CompareStringOrdinal
0x180022fc4  cmp     eax, 2
0x180022fc7  jz      loc_180023346
0x180022fcd  mov     rcx, [rbx+138h]; lpString1
0x180022fd4  lea     r8, aDisabledintf; "DisabledIntf"
0x180022fdb  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022fe1  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180022fe9  mov     edx, r9d; cchCount1
0x180022fec  call    cs:__imp_CompareStringOrdinal
0x180022ff2  cmp     eax, 2
0x180022ff5  jz      loc_180023346
0x180022ffb  mov     rax, [rdi]
0x180022ffe  mov     rcx, rdi
0x180023001  mov     rax, [rax+0D0h]
0x180023008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002300d  test    al, 8
0x18002300f  jnz     loc_180023318
0x180023015  mov     rcx, [rbx+138h]; lpString1
0x18002301c  lea     r8, aDefaultactions; "DefaultActions"
0x180023023  mov     r9d, 0FFFFFFFFh; cchCount2
0x180023029  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180023031  mov     edx, r9d; cchCount1
0x180023034  call    cs:__imp_CompareStringOrdinal
0x18002303a  cmp     eax, 2
0x18002303d  jz      loc_180023104
0x180023043  mov     eax, [rsp+288h+var_F8]
0x18002304a  mov     [rbx+150h], eax
0x180023050  mov     eax, r14d
0x180023053  jmp     loc_180022B8F
0x180023058  mov     rax, [rdi]
0x18002305b  mov     edx, 1
0x180023060  mov     rcx, rdi
0x180023063  mov     rax, [rax+0C0h]
  ... truncated ...
```
