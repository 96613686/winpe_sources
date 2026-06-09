# IPolicyWriter::WriteSpecialFwRule(_tag_FW_RULE *,_LIST_ENTRY *,_tag_FW_OBJECT_METADATA *)

- ea: `0x180024e70`
- end: `0x180025977`
- name: `?WriteSpecialFwRule@IPolicyWriter@@QEAAJPEAU_tag_FW_RULE@@PEAU_LIST_ENTRY@@PEAU_tag_FW_OBJECT_METADATA@@@Z`
- size: `2823`
- prototype: `int(IPolicyWriter *__hidden this, struct _tag_FW_RULE *, struct _LIST_ENTRY *, struct _tag_FW_OBJECT_METADATA *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024e50`

## callees

- `0x18000a710`
- `0x180024db4`
- `0x180024e70`
- `0x180026850`
- `0x180026c60`
- `0x1800729c0`
- `0x180073488`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024eda`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024f0a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024f72`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024fa3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024fd4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025005`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025036`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025067`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025098`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800250c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800250fa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002512b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002515f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025242`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800253c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800253f9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025447`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025639`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002575c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024eda`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024f0a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024f72`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024fa3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024fd4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025005`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025036`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025067`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025098`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800250c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800250fa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002512b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002515f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025242`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800253c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800253f9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025447`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025639`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002575c`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800251ee`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180025268`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180025656`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800251ee`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180025268`
- `fwbase!FwMetaDataAddEnforcementState` at `0x180025656`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x1800251ad`
- `fwbase!FwGetProfileIndexFromProfileType` at `0x1800251ad`

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
    if ( (dword_1801375A8 & 4) != 0
      && (CompareStringOrdinal(a2[39], -1, L"DefaultActions", -1, 1) != 2 || (dword_1801375A8 & 1) != 0) )
    {
      FwMetaDataAddEnforcementState(a4, 3);
      return 0;
    }
    v11 = 0;
    if ( (dword_180135A5C & 4) != 0 )
      v12 = 4;
    else
      v12 = ((dword_180135A5C & 2) != 0) + 1;
    if ( (dword_180135A5C & (_DWORD)a2[5]) == 0 )
    {
      v13 = 5;
LABEL_23:
      FwMetaDataAddEnforcementState(a4, v13);
      return 0;
    }
    v14 = &dword_180135878[40 * ProfileIndexFromProfileType];
    if ( !*v14
      && (CompareStringOrdinal(a2[39], -1, L"DefaultActions", -1, 1) != 2
       || !*v14 && *((_DWORD *)a2 + 72) == 2 && (unsigned int)FwHasSingleProfile((unsigned int)dword_180135A5C))
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
      LOBYTE(v11) = (unsigned int)FwHasSingleProfile((unsigned int)dword_180135A5C) != 0;
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
        WPP_SF_d(*(_QWORD *)(v34 + 16), v35, WPP_9246bb9fff193791a74cbfd2838cb9b7_Traceguids, (unsigned int)v11);
        return (unsigned int)v11;
      }
    }
    else if ( CompareStringOrdinal(a2[39], -1, L"DefaultActions", -1, 1) == 2 )
    {
      (*(void (__fastcall **)(IPolicyWriter *, __int64))(*(_QWORD *)v4 + 88LL))(v4, 5);
      if ( !*v14 || (dword_1801375A8 & 4) != 0 )
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
0x180024e70  mov     [rsp+arg_0], rbx
0x180024e75  push    rbp
0x180024e76  push    rsi
0x180024e77  push    rdi
0x180024e78  push    r12
0x180024e7a  push    r13
0x180024e7c  push    r14
0x180024e7e  push    r15
0x180024e80  sub     rsp, 250h
0x180024e87  mov     rax, cs:__security_cookie
0x180024e8e  xor     rax, rsp
0x180024e91  mov     [rsp+288h+var_48], rax
0x180024e99  mov     rdi, cs:pWriterModule
0x180024ea0  lea     rcx, [rsp+288h+var_248]; void *
0x180024ea5  mov     rbp, r8
0x180024ea8  mov     rbx, rdx
0x180024eab  xor     edx, edx; Val
0x180024ead  mov     r8d, 1F8h; Size
0x180024eb3  mov     rsi, r9
0x180024eb6  call    memset_0
0x180024ebb  mov     rcx, [rbx+138h]; lpString1
0x180024ec2  lea     r8, String2; "AppCDefaultRule"
0x180024ec9  mov     r9d, 0FFFFFFFFh; cchCount2
0x180024ecf  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180024ed7  mov     edx, r9d; cchCount1
0x180024eda  call    cs:__imp_CompareStringOrdinal
0x180024ee1  nop     dword ptr [rax+rax+00h]
0x180024ee6  mov     r9d, 0FFFFFFFFh; cchCount2
0x180024eec  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180024ef4  mov     edx, r9d; cchCount1
0x180024ef7  cmp     eax, 2
0x180024efa  jz      short loc_180024F67
0x180024efc  mov     rcx, [rbx+138h]; lpString1
0x180024f03  lea     r8, aCsaddressiso; "CSAddressIso"
0x180024f0a  call    cs:__imp_CompareStringOrdinal
0x180024f11  nop     dword ptr [rax+rax+00h]
0x180024f16  cmp     eax, 2
0x180024f19  jnz     loc_1800251AA
0x180024f1f  mov     rax, [rdi]
0x180024f22  mov     rcx, rdi
0x180024f25  mov     rax, [rax+0D0h]
0x180024f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f31  test    al, 8
0x180024f33  jnz     loc_180025802
0x180024f39  xor     eax, eax
0x180024f3b  mov     rcx, [rsp+288h+var_48]
0x180024f43  xor     rcx, rsp; StackCookie
0x180024f46  call    __security_check_cookie
0x180024f4b  mov     rbx, [rsp+288h+arg_0]
0x180024f53  add     rsp, 250h
0x180024f5a  pop     r15
0x180024f5c  pop     r14
0x180024f5e  pop     r13
0x180024f60  pop     r12
0x180024f62  pop     rdi
0x180024f63  pop     rsi
0x180024f64  pop     rbp
0x180024f65  retn
0x180024f67  mov     rcx, [rbx+18h]; lpString1
0x180024f6b  lea     r8, aPrivatenetwork; "PrivateNetwork Inbound Default Rule"
0x180024f72  call    cs:__imp_CompareStringOrdinal
0x180024f79  nop     dword ptr [rax+rax+00h]
0x180024f7e  cmp     eax, 2
0x180024f81  jz      loc_180025471
0x180024f87  mov     rcx, [rbx+18h]; lpString1
0x180024f8b  lea     r8, aPrivatenetwork_0; "PrivateNetwork Outbound Default Rule"
0x180024f92  mov     r9d, 0FFFFFFFFh; cchCount2
0x180024f98  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180024fa0  mov     edx, r9d; cchCount1
0x180024fa3  call    cs:__imp_CompareStringOrdinal
0x180024faa  nop     dword ptr [rax+rax+00h]
0x180024faf  cmp     eax, 2
0x180024fb2  jz      loc_1800254DD
0x180024fb8  mov     rcx, [rbx+18h]; lpString1
0x180024fbc  lea     r8, aRemoteprivnetw; "RemotePrivNetwork Inbound Default Rule"
0x180024fc3  mov     r9d, 0FFFFFFFFh; cchCount2
0x180024fc9  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180024fd1  mov     edx, r9d; cchCount1
0x180024fd4  call    cs:__imp_CompareStringOrdinal
0x180024fdb  nop     dword ptr [rax+rax+00h]
0x180024fe0  cmp     eax, 2
0x180024fe3  jz      loc_1800251FF
0x180024fe9  mov     rcx, [rbx+18h]; lpString1
0x180024fed  lea     r8, aRemoteprivnetw_0; "RemotePrivNetwork Outbound Default Rule"
0x180024ff4  mov     r9d, 0FFFFFFFFh; cchCount2
0x180024ffa  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180025002  mov     edx, r9d; cchCount1
0x180025005  call    cs:__imp_CompareStringOrdinal
0x18002500c  nop     dword ptr [rax+rax+00h]
0x180025011  cmp     eax, 2
0x180025014  jz      loc_180025279
0x18002501a  mov     rcx, [rbx+18h]; lpString1
0x18002501e  lea     r8, aInternetclient_0; "InternetClientServer Inbound Default Ru"...
0x180025025  mov     r9d, 0FFFFFFFFh; cchCount2
0x18002502b  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180025033  mov     edx, r9d; cchCount1
0x180025036  call    cs:__imp_CompareStringOrdinal
0x18002503d  nop     dword ptr [rax+rax+00h]
0x180025042  cmp     eax, 2
0x180025045  jz      loc_18002529D
0x18002504b  mov     rcx, [rbx+18h]; lpString1
0x18002504f  lea     r8, aInternetclient_1; "InternetClientServer Outbound Default R"...
0x180025056  mov     r9d, 0FFFFFFFFh; cchCount2
0x18002505c  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180025064  mov     edx, r9d; cchCount1
0x180025067  call    cs:__imp_CompareStringOrdinal
0x18002506e  nop     dword ptr [rax+rax+00h]
0x180025073  cmp     eax, 2
0x180025076  jz      loc_1800254B9
0x18002507c  mov     rcx, [rbx+18h]; lpString1
0x180025080  lea     r8, aInternetclient; "InternetClient Default Rule"
0x180025087  mov     r9d, 0FFFFFFFFh; cchCount2
0x18002508d  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180025095  mov     edx, r9d; cchCount1
0x180025098  call    cs:__imp_CompareStringOrdinal
0x18002509f  nop     dword ptr [rax+rax+00h]
0x1800250a4  cmp     eax, 2
0x1800250a7  jz      loc_180025495
0x1800250ad  mov     rcx, [rbx+18h]; lpString1
0x1800250b1  lea     r8, aBlockInboundDe; "Block Inbound Default Rule"
0x1800250b8  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800250be  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x1800250c6  mov     edx, r9d; cchCount1
0x1800250c9  call    cs:__imp_CompareStringOrdinal
0x1800250d0  nop     dword ptr [rax+rax+00h]
0x1800250d5  cmp     eax, 2
0x1800250d8  jz      loc_1800256E8
0x1800250de  mov     rcx, [rbx+18h]; lpString1
0x1800250e2  lea     r8, aBlockOutboundD; "Block Outbound Default Rule"
0x1800250e9  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800250ef  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x1800250f7  mov     edx, r9d; cchCount1
0x1800250fa  call    cs:__imp_CompareStringOrdinal
0x180025101  nop     dword ptr [rax+rax+00h]
0x180025106  cmp     eax, 2
0x180025109  jz      loc_1800255F6
0x18002510f  mov     rcx, [rbx+18h]; lpString1
0x180025113  lea     r8, aBlockInboundDe; "Block Inbound Default Rule"
0x18002511a  mov     r9d, 0FFFFFFFFh; cchCount2
0x180025120  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180025128  mov     edx, r9d; cchCount1
0x18002512b  call    cs:__imp_CompareStringOrdinal
0x180025132  nop     dword ptr [rax+rax+00h]
0x180025137  cmp     eax, 2
0x18002513a  jz      loc_180025923
0x180025140  mov     rcx, [rbx+18h]; lpString1
0x180025144  lea     r8, aBlockOutboundD; "Block Outbound Default Rule"
0x18002514b  mov     r9d, 0FFFFFFFFh; cchCount2
0x180025151  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180025159  mov     edx, r9d; cchCount1
0x18002515c  xor     r14d, r14d
0x18002515f  call    cs:__imp_CompareStringOrdinal
0x180025166  nop     dword ptr [rax+rax+00h]
0x18002516b  cmp     eax, 2
0x18002516e  jz      loc_180025923
0x180025174  mov     rax, [rdi]
0x180025177  mov     edx, 0Eh
0x18002517c  mov     rcx, rdi
0x18002517f  mov     rax, [rax+58h]
0x180025183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025188  mov     r9d, r14d; int
0x18002518b  mov     [rsp+288h+var_260], rsi; struct _tag_FW_OBJECT_METADATA *
0x180025190  mov     r8, rbx; struct _tag_FW_RULE *
0x180025193  mov     qword ptr [rsp+288h+bIgnoreCase], rbp; struct _LIST_ENTRY *
0x180025198  mov     edx, 7FFFFFFFh; unsigned int
0x18002519d  mov     rcx, rdi; this
0x1800251a0  call    ?WriteFwRule@IPolicyWriter@@QEAAJKPEAU_tag_FW_RULE@@HPEAU_LIST_ENTRY@@PEAU_tag_FW_OBJECT_METADATA@@@Z; IPolicyWriter::WriteFwRule(ulong,_tag_FW_RULE *,int,_LIST_ENTRY *,_tag_FW_OBJECT_METADATA *)
0x1800251a5  jmp     loc_180024F3B
0x1800251aa  mov     ecx, [rbx+28h]
0x1800251ad  call    cs:__imp_FwGetProfileIndexFromProfileType
0x1800251b4  nop     dword ptr [rax+rax+00h]
0x1800251b9  test    byte ptr cs:dword_1801375A8, 4
0x1800251c0  movsxd  r15, eax
0x1800251c3  jnz     short loc_180025223
0x1800251c5  mov     edx, cs:dword_180135A5C
0x1800251cb  xor     r14d, r14d
0x1800251ce  test    dl, 4
0x1800251d1  jz      loc_18002550B
0x1800251d7  mov     r12d, 4
0x1800251dd  test    [rbx+28h], edx
0x1800251e0  jnz     loc_1800252C1
0x1800251e6  mov     edx, 5
0x1800251eb  mov     rcx, rsi
0x1800251ee  call    cs:__imp_FwMetaDataAddEnforcementState
0x1800251f5  nop     dword ptr [rax+rax+00h]
0x1800251fa  jmp     loc_180024F39
0x1800251ff  mov     rax, [rdi]
0x180025202  mov     edx, 3
0x180025207  mov     rcx, rdi
0x18002520a  mov     rax, [rax+0C0h]
0x180025211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025216  test    eax, eax
0x180025218  jz      loc_180024F39
0x18002521e  jmp     loc_180024FE9
0x180025223  mov     rcx, [rbx+138h]; lpString1
0x18002522a  lea     r8, aDefaultactions; "DefaultActions"
0x180025231  mov     r9d, 0FFFFFFFFh; cchCount2
0x180025237  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x18002523f  mov     edx, r9d; cchCount1
0x180025242  call    cs:__imp_CompareStringOrdinal
0x180025249  nop     dword ptr [rax+rax+00h]
0x18002524e  cmp     eax, 2
0x180025251  jnz     short loc_180025260
0x180025253  test    byte ptr cs:dword_1801375A8, 1
0x18002525a  jz      loc_1800251C5
0x180025260  mov     edx, 3
0x180025265  mov     rcx, rsi
0x180025268  call    cs:__imp_FwMetaDataAddEnforcementState
0x18002526f  nop     dword ptr [rax+rax+00h]
0x180025274  jmp     loc_180024F39
0x180025279  mov     rax, [rdi]
0x18002527c  mov     edx, 4
0x180025281  mov     rcx, rdi
0x180025284  mov     rax, [rax+0C0h]
0x18002528b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025290  test    eax, eax
0x180025292  jz      loc_180024F39
0x180025298  jmp     loc_18002501A
0x18002529d  mov     rax, [rdi]
0x1800252a0  mov     edx, 5
0x1800252a5  mov     rcx, rdi
0x1800252a8  mov     rax, [rax+0C0h]
0x1800252af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252b4  test    eax, eax
0x1800252b6  jz      loc_180024F39
0x1800252bc  jmp     loc_18002504B
0x1800252c1  lea     r13, [r15+r15*4]
0x1800252c5  shl     r13, 5
0x1800252c9  lea     rax, dword_180135878
0x1800252d0  add     r13, rax
0x1800252d3  cmp     [r13+0], r14d
0x1800252d7  jz      loc_18002561A
0x1800252dd  call    GetFwONProfiles
0x1800252e2  test    eax, eax
0x1800252e4  jz      loc_18002564E
0x1800252ea  test    byte ptr [rbx+124h], 1
0x1800252f1  jz      loc_180025501
0x1800252f7  test    byte ptr [rbx+1A8h], 8
0x1800252fe  jnz     loc_180025501
0x180025304  mov     r15d, 3
0x18002530a  lea     rcx, [rsp+288h+var_248]
0x18002530f  mov     edx, r15d
0x180025312  mov     rax, rbx
0x180025315  lea     rcx, [rcx+80h]
0x18002531c  movups  xmm0, xmmword ptr [rax]
0x18002531f  movups  xmm1, xmmword ptr [rax+10h]
0x180025323  lea     rax, [rax+80h]
0x18002532a  movups  xmmword ptr [rcx-80h], xmm0
0x18002532e  movups  xmm0, xmmword ptr [rax-60h]
0x180025332  movups  xmmword ptr [rcx-70h], xmm1
0x180025336  movups  xmm1, xmmword ptr [rax-50h]
0x18002533a  movups  xmmword ptr [rcx-60h], xmm0
0x18002533e  movups  xmm0, xmmword ptr [rax-40h]
0x180025342  movups  xmmword ptr [rcx-50h], xmm1
0x180025346  movups  xmm1, xmmword ptr [rax-30h]
0x18002534a  movups  xmmword ptr [rcx-40h], xmm0
0x18002534e  movups  xmm0, xmmword ptr [rax-20h]
0x180025352  movups  xmmword ptr [rcx-30h], xmm1
0x180025356  movups  xmm1, xmmword ptr [rax-10h]
0x18002535a  movups  xmmword ptr [rcx-20h], xmm0
0x18002535e  movups  xmmword ptr [rcx-10h], xmm1
0x180025362  sub     rdx, 1
0x180025366  jnz     short loc_180025315
0x180025368  movups  xmm0, xmmword ptr [rax]
0x18002536b  mov     r9d, 0FFFFFFFFh; cchCount2
0x180025371  lea     r8, aShieldedmode; "ShieldedMode"
0x180025378  movups  xmm1, xmmword ptr [rax+10h]
0x18002537c  mov     edx, r9d; cchCount1
0x18002537f  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x180025387  movups  xmmword ptr [rcx], xmm0
0x18002538a  movups  xmm0, xmmword ptr [rax+20h]
0x18002538e  movups  xmmword ptr [rcx+10h], xmm1
0x180025392  movups  xmm1, xmmword ptr [rax+30h]
0x180025396  movups  xmmword ptr [rcx+20h], xmm0
0x18002539a  movups  xmm0, xmmword ptr [rax+40h]
0x18002539e  movups  xmmword ptr [rcx+30h], xmm1
0x1800253a2  movups  xmm1, xmmword ptr [rax+50h]
0x1800253a6  movups  xmmword ptr [rcx+40h], xmm0
0x1800253aa  movups  xmm0, xmmword ptr [rax+60h]
0x1800253ae  mov     rax, [rax+70h]
0x1800253b2  movups  xmmword ptr [rcx+50h], xmm1
0x1800253b6  movups  xmmword ptr [rcx+60h], xmm0
0x1800253ba  mov     [rcx+70h], rax
0x1800253be  mov     rcx, [rbx+138h]; lpString1
0x1800253c5  call    cs:__imp_CompareStringOrdinal
0x1800253cc  nop     dword ptr [rax+rax+00h]
0x1800253d1  cmp     eax, 2
0x1800253d4  jz      loc_180025771
0x1800253da  mov     rcx, [rbx+138h]; lpString1
0x1800253e1  lea     r8, aDisabledintf; "DisabledIntf"
0x1800253e8  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800253ee  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x1800253f6  mov     edx, r9d; cchCount1
0x1800253f9  call    cs:__imp_CompareStringOrdinal
0x180025400  nop     dword ptr [rax+rax+00h]
0x180025405  cmp     eax, 2
0x180025408  jz      loc_180025771
0x18002540e  mov     rax, [rdi]
0x180025411  mov     rcx, rdi
0x180025414  mov     rax, [rax+0D0h]
  ... truncated ...
```
