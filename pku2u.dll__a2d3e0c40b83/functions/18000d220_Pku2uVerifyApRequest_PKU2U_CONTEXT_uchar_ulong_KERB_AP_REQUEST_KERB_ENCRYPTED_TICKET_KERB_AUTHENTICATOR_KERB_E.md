# Pku2uVerifyApRequest(_PKU2U_CONTEXT *,uchar *,ulong,KERB_AP_REQUEST * *,KERB_ENCRYPTED_TICKET * *,KERB_AUTHENTICATOR * *,KERB_ENCRYPTION_KEY *,KERB_ENCRYPTION_KEY *,long *,_SEC_CHANNEL_BINDINGS *)

- ea: `0x18000d220`
- end: `0x18000ddcd`
- name: `?Pku2uVerifyApRequest@@YAJPEAU_PKU2U_CONTEXT@@PEAEKPEAPEAUKERB_AP_REQUEST@@PEAPEAUKERB_ENCRYPTED_TICKET@@PEAPEAUKERB_AUTHENTICATOR@@PEAUKERB_ENCRYPTION_KEY@@5PEAJPEAU_SEC_CHANNEL_BINDINGS@@@Z`
- size: `2989`
- prototype: `__int64 __fastcall(struct _PKU2U_CONTEXT *, unsigned __int8 *, int, struct KERB_AP_REQUEST **, struct KERB_ENCRYPTED_TICKET **, struct KERB_AUTHENTICATOR **, struct KERB_ENCRYPTION_KEY *, struct KERB_ENCRYPTION_KEY *, int *, struct _SEC_CHANNEL_BINDINGS *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b990`

## callees

- `0x1800057f0`
- `0x180007dc8`
- `0x18000d220`
- `0x18000ddd4`
- `0x18000e1d0`
- `0x1800160e0`
- `0x18001a1d0`
- `0x18001b670`
- `0x1800210f0`
- `0x180023cb8`
- `0x180023ce0`
- `0x180023d9c`
- `0x18002b408`
- `0x18002b744`
- `0x180031de8`
- `0x180044f80`
- `0x180046010`

## import_xrefs

- `MSASN1!ASN1_CreateDecoder` at `0x18000d56b`
- `MSASN1!ASN1_CreateDecoder` at `0x18000d56b`
- `MSASN1!ASN1_CloseDecoder` at `0x18000d700`
- `MSASN1!ASN1_CloseDecoder` at `0x18000d700`
- `MSASN1!ASN1_CreateModule` at `0x18000d53e`
- `MSASN1!ASN1_CreateModule` at `0x18000d53e`
- `MSASN1!ASN1_Decode` at `0x18000d617`
- `MSASN1!ASN1_Decode` at `0x18000d617`
- `ntdll!RtlTimeFieldsToTime` at `0x18000d918`
- `ntdll!RtlTimeFieldsToTime` at `0x18000d918`

## string_xrefs

- `0x18000d971`: `onecore\ds\security\protocols\pku2u\tick.cxx`
- `0x18000dd17`: `onecore\ds\security\protocols\pku2u\tick.cxx`

## pseudocode

```c
__int64 __fastcall Pku2uVerifyApRequest(
        struct _PKU2U_CONTEXT *a1,
        unsigned __int8 *a2,
        int a3,
        struct KERB_AP_REQUEST **a4,
        struct KERB_ENCRYPTED_TICKET **a5,
        struct KERB_AUTHENTICATOR **a6,
        struct KERB_ENCRYPTION_KEY *a7,
        struct KERB_ENCRYPTION_KEY *a8,
        int *a9,
        struct _SEC_CHANNEL_BINDINGS *a10)
{
  int *v10; // r10
  int v11; // ebx
  struct KERB_AUTHENTICATOR **v12; // r12
  int v14; // r14d
  int v15; // r8d
  unsigned __int8 *v16; // rdx
  int v17; // edi
  unsigned __int8 v18; // r8
  int i; // ecx
  int v20; // eax
  int v21; // edi
  int v22; // edi
  __int64 v23; // rsi
  int v24; // edi
  unsigned __int8 *v25; // r12
  void *v26; // rsi
  int v27; // edi
  char v28; // r8
  unsigned __int8 *v29; // rdx
  int v30; // ebx
  unsigned __int8 v31; // r8
  int j; // ecx
  int v33; // eax
  int v34; // ebx
  int v35; // ebx
  __int64 v36; // rdi
  int v37; // ebx
  unsigned __int8 *v38; // r14
  int v39; // esi
  unsigned __int8 *v40; // rbx
  __int64 Module; // rax
  unsigned int v42; // eax
  PVOID *v43; // r10
  int v44; // edi
  int v45; // eax
  unsigned int v46; // ebx
  struct KERB_AP_REQUEST *v47; // r8
  _BYTE *v48; // r9
  unsigned int v49; // ebx
  __int64 v50; // r11
  unsigned int v51; // edx
  __int64 v52; // rbx
  union _LARGE_INTEGER *v53; // r14
  __int64 v54; // rdx
  __int64 v55; // r8
  struct KERB_ENCRYPTED_TICKET *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rdx
  __int64 v60; // rcx
  struct KERB_AUTHENTICATOR *v61; // rbx
  unsigned int v62; // esi
  unsigned int v63; // r12d
  unsigned int *v64; // rbx
  unsigned int v65; // eax
  __int64 v66; // r9
  char v67; // dl
  __int64 v68; // r8
  char v69; // cl
  unsigned __int8 v70; // al
  unsigned int v71; // esi
  unsigned int *v72; // rbx
  unsigned int v73; // esi
  __int64 v74; // r9
  unsigned __int8 *v75; // r14
  int v76; // eax
  char v77; // r8
  __int64 v78; // r9
  char v79; // cl
  char v80; // al
  unsigned int v82; // [rsp+58h] [rbp-B0h]
  struct KERB_AUTHENTICATOR **v83; // [rsp+70h] [rbp-98h] BYREF
  struct KERB_AP_REQUEST *v84; // [rsp+78h] [rbp-90h] BYREF
  struct _PKU2U_CONTEXT *v85; // [rsp+80h] [rbp-88h]
  void *v86; // [rsp+88h] [rbp-80h] BYREF
  __int128 v87; // [rsp+90h] [rbp-78h] BYREF
  void *v88; // [rsp+A0h] [rbp-68h]
  struct KERB_ENCRYPTION_KEY *v89; // [rsp+A8h] [rbp-60h]
  struct _SEC_CHANNEL_BINDINGS *v90; // [rsp+B0h] [rbp-58h]
  struct KERB_AP_REQUEST **v91; // [rsp+B8h] [rbp-50h]
  struct _TIME_FIELDS TimeFields; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int8 v93[16]; // [rsp+D0h] [rbp-38h] BYREF

  v10 = a9;
  v11 = a3 - 1;
  v12 = a6;
  v91 = a4;
  v90 = a10;
  *a4 = 0;
  v85 = a1;
  *((_OWORD *)a1 + 14) = 0;
  *((_QWORD *)a1 + 30) = 0;
  *(_OWORD *)a7 = 0;
  *((_QWORD *)a7 + 2) = 0;
  *(_OWORD *)a8 = 0;
  *(_QWORD *)&TimeFields.Year = a7;
  *((_QWORD *)a8 + 2) = 0;
  *a5 = 0;
  *a6 = 0;
  *a9 = 0;
  *((_DWORD *)a1 + 16) = 0;
  v83 = a6;
  v89 = a8;
  v84 = 0;
  v88 = 0;
  v86 = 0;
  v87 = 0;
  if ( a3 - 1 < 0 )
    goto LABEL_183;
  v14 = (int)pku2u_global_oids;
  if ( *a2 != 96 || v11 < 1 )
    goto LABEL_183;
  v15 = a2[1];
  v16 = a2 + 2;
  v17 = v11 - 1;
  if ( (v15 & 0x80u) == 0 )
  {
    i = v15;
  }
  else
  {
    v18 = v15 & 0x7F;
    if ( v18 + 1 > v17 || v18 > 4u )
      goto LABEL_27;
    for ( i = 0; v18; --v18 )
    {
      v20 = *v16;
      --v17;
      ++v16;
      i = v20 + (i << 8);
    }
  }
  if ( i <= v17 && i >= 0 )
  {
    if ( i == v17 )
    {
      v21 = v17 - 1;
      if ( v21 >= 0 && *v16 == 6 )
      {
        v22 = v21 - 1;
        if ( v22 >= 0 )
        {
          v23 = v16[1];
          v24 = v22 - v23;
          if ( v24 >= 0 )
          {
            if ( (_DWORD)v23 != (_DWORD)pku2u_global_oids )
              goto LABEL_27;
            v25 = v16 + 2;
            if ( memcmp_0(v16 + 2, Src, v16[1]) )
              goto LABEL_24;
            if ( v24 - 2 >= 0 )
            {
              if ( v25[v23] == 5 && !v25[v23 + 1] )
              {
                v26 = 0;
                v27 = 280;
                goto LABEL_195;
              }
LABEL_24:
              v12 = v83;
              v10 = a9;
              goto LABEL_27;
            }
            v12 = v83;
            v10 = a9;
          }
        }
      }
    }
    if ( *a2 != 96 )
      goto LABEL_183;
  }
LABEL_27:
  v28 = a2[1];
  v29 = a2 + 2;
  v30 = v11 - 1;
  if ( v28 >= 0 )
  {
    j = a2[1];
  }
  else
  {
    v31 = v28 & 0x7F;
    if ( v31 + 1 > v30 || v31 > 4u )
      goto LABEL_183;
    for ( j = 0; v31; --v31 )
    {
      v33 = *v29;
      --v30;
      ++v29;
      j = v33 + (j << 8);
    }
  }
  if ( j > v30
    || j < 0
    || j != v30
    || (v34 = v30 - 1, v34 < 0)
    || *v29 != 6
    || (v35 = v34 - 1, v35 < 0)
    || (v36 = v29[1], v37 = v35 - v36, v37 < 0)
    || (_DWORD)v36 != v14 )
  {
LABEL_183:
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_187;
    WPP_SF_dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
      0,
      (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
      231);
LABEL_186:
    v10 = a9;
LABEL_187:
    v49 = 0;
    v27 = -1073741670;
    v26 = 0;
    goto LABEL_188;
  }
  v38 = v29 + 2;
  if ( memcmp_0(v29 + 2, Src, v29[1]) || (v39 = v37 - 2, v37 - 2 < 0) || v38[v36] != 1 || v38[v36 + 1] )
  {
    v10 = a9;
    goto LABEL_183;
  }
  v83 = 0;
  if ( v37 == 2 || (v40 = &v38[v36 + 2]) == 0 )
  {
    v43 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids);
      v43 = (PVOID *)WPP_GLOBAL_Control;
    }
    v44 = 60;
    goto LABEL_179;
  }
  if ( fKRB5ModuleStarted )
  {
    Module = PKU2UMSG_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               49,
               off_180047350,
               off_1800471C0,
               off_180047030,
               qword_180049F80,
               846556016);
    PKU2UMSG_Module = Module;
  }
  v42 = ASN1_CreateDecoder(Module, &v83, 0, 0, 0);
  if ( v42 )
  {
    v43 = (PVOID *)WPP_GLOBAL_Control;
    v44 = 60;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_186;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v42);
      v43 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v43 == &WPP_GLOBAL_Control )
      goto LABEL_186;
    if ( (*((_BYTE *)v43 + 28) & 1) != 0 )
    {
      WPP_SF_d(v43[2], 80, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, 60);
      v43 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_179;
  }
  v44 = 0;
  v84 = 0;
  v45 = ASN1_Decode(v83, &v84, 35, 8, v40, v39);
  v46 = v45;
  if ( v45 >= 0 )
  {
    v43 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v43 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)v45);
      v43 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v46 == -1009 || v46 == -1002 )
    {
      if ( v43 != &WPP_GLOBAL_Control && (*((_BYTE *)v43 + 28) & 4) != 0 )
      {
        WPP_SF_d(v43[2], 82, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, 35);
        v43 = (PVOID *)WPP_GLOBAL_Control;
      }
      v44 = -2147483647;
    }
    else
    {
      if ( v46 != -1011 && v43 != &WPP_GLOBAL_Control && (*((_BYTE *)v43 + 28) & 1) != 0 )
      {
        WPP_SF_d(v43[2], 83, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v46);
        v43 = (PVOID *)WPP_GLOBAL_Control;
      }
      v44 = 60;
    }
    v84 = 0;
  }
  if ( v83 )
  {
    ASN1_CloseDecoder();
    v43 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v44 )
  {
LABEL_179:
    if ( v43 != &WPP_GLOBAL_Control && (*((_BYTE *)v43 + 28) & 1) != 0 )
      WPP_SF_dsd(
        (unsigned int)v43[2],
        23,
        (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        v44,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
        243);
    goto LABEL_186;
  }
  v47 = v84;
  v48 = (char *)&v83 + 3;
  v49 = 0;
  v50 = 0;
  v82 = 0;
  LODWORD(v83) = 0;
  v51 = *((_DWORD *)v84 + 2);
  if ( v51 <= 0x20 )
  {
    if ( v51 <= 7 )
      goto LABEL_84;
  }
  else
  {
    v51 = 32;
  }
  v52 = *((_QWORD *)v84 + 2);
  do
  {
    v51 -= 8;
    *v48 = *(_BYTE *)(v50 + v52);
    v50 = (unsigned int)(v50 + 1);
    --v48;
  }
  while ( v51 > 7 );
  v49 = (unsigned int)v83;
  v82 = (unsigned int)v83;
LABEL_84:
  if ( v51 )
  {
    *v48 = *(_BYTE *)(v50 + *((_QWORD *)v47 + 2)) & (-1 << (8 - v51));
    v49 = (unsigned int)v83;
    v82 = (unsigned int)v83;
  }
  if ( v43 != &WPP_GLOBAL_Control && (*((_BYTE *)v43 + 28) & 4) != 0 )
    WPP_SF_d(v43[2], 24, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v49);
  v53 = (union _LARGE_INTEGER *)v85;
  v27 = Pku2uDecryptServiceTicket(v84, v85, a5, v12, *(struct KERB_ENCRYPTION_KEY **)&TimeFields.Year, v89, a9);
  if ( v27 < 0 )
  {
    v88 = 0;
    v87 = 0;
    ((void (__fastcall *)(__int128 *))Pku2uGlobalLsaFunctions->GetCallInfo)(&v87);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Ddq(*((_QWORD *)WPP_GLOBAL_Control + 2), v54, v55, (unsigned int)*a9, v87, v84);
    v26 = 0;
    v10 = a9;
    goto LABEL_188;
  }
  v56 = *a5;
  *(_DWORD *)&TimeFields.Minute = 0;
  v53[6].QuadPart = 0;
  LOBYTE(TimeFields.Second) = 1;
  *(_QWORD *)&TimeFields.Year = 0;
  v57 = -*(_QWORD *)((char *)v56 + 124);
  if ( !*(_QWORD *)((char *)v56 + 124) )
  {
    v58 = *((unsigned int *)v56 + 33);
    v57 = *(unsigned int *)&TimeFields.Minute - v58;
    if ( *(unsigned int *)&TimeFields.Minute == v58 )
      v57 = -(__int64)*((unsigned __int16 *)v56 + 68);
  }
  if ( v57 )
  {
    *(_DWORD *)&TimeFields.Year = 16844722;
    v59 = *(_QWORD *)&TimeFields.Year - *(_QWORD *)((char *)v56 + 124);
    if ( *(_QWORD *)&TimeFields.Year == *(_QWORD *)((char *)v56 + 124) )
    {
      v60 = *((unsigned int *)v56 + 33);
      v59 = *(unsigned int *)&TimeFields.Minute - v60;
      if ( *(unsigned int *)&TimeFields.Minute == v60 )
        v59 = -(__int64)*((unsigned __int16 *)v56 + 68);
    }
    if ( v59 )
    {
      TimeFields.Year = *((_WORD *)v56 + 62);
      TimeFields.Month = *((unsigned __int8 *)v56 + 126);
      TimeFields.Day = *((unsigned __int8 *)v56 + 127);
      TimeFields.Hour = *((unsigned __int8 *)v56 + 128);
      TimeFields.Minute = *((unsigned __int8 *)v56 + 129);
      TimeFields.Second = *((unsigned __int8 *)v56 + 130);
      TimeFields.Milliseconds = *((_WORD *)v56 + 66);
      TimeFields.Weekday = 0;
      RtlTimeFieldsToTime(&TimeFields, v53 + 6);
    }
  }
  v61 = *v12;
  if ( *(char *)*v12 >= 0 || *((_DWORD *)v61 + 8) != 32771 )
  {
    v63 = v82;
    goto LABEL_167;
  }
  v62 = *((_DWORD *)v61 + 10);
  v63 = v82;
  if ( v62 < 0x18 )
  {
LABEL_167:
    if ( (union _LARGE_INTEGER *)v53[38].QuadPart == &v53[38] )
    {
      v26 = 0;
LABEL_172:
      if ( (v63 & 0x20000000) != 0 )
        v53[8].LowPart |= 2u;
      *v91 = v84;
      goto LABEL_192;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids);
    goto LABEL_131;
  }
  v64 = (unsigned int *)*((_QWORD *)v61 + 6);
  v65 = v64[5];
  if ( (v65 & 2) != 0 && (v82 & 0x20000000) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
        51);
    v26 = 0;
    v27 = -1073741811;
    v10 = a9;
    v49 = v82;
    goto LABEL_188;
  }
  if ( (v65 & 0x1000) != 0 )
    v53[8].LowPart |= 0x200u;
  if ( (v64[5] & 4) != 0 )
    v53[8].LowPart |= 4u;
  if ( (v64[5] & 8) != 0 )
    v53[8].LowPart |= 8u;
  if ( (v64[5] & 0x10) != 0 )
    v53[8].LowPart |= 0x10010u;
  if ( (v64[5] & 0x20) != 0 )
    v53[8].LowPart |= 0x10000u;
  if ( (v64[5] & 0x2000) != 0 )
    v53[8].LowPart |= 0x20000u;
  if ( (v64[5] & 0x4000) != 0 )
    v53[8].LowPart |= 0x4000u;
  if ( !v90 )
    goto LABEL_139;
  v66 = *v64;
  if ( (_DWORD)v66 == 16 )
  {
    v27 = Pku2uComputeGssBindHash(v90, v93);
    if ( v27 < 0 )
      goto LABEL_132;
    v67 = 0;
    v68 = 0;
    if ( *v64 )
    {
      do
      {
        v69 = *((_BYTE *)v64 + v68 + 4);
        v70 = v93[v68];
        v68 = (unsigned int)(v68 + 1);
        v67 |= v70 ^ v69;
      }
      while ( (unsigned int)v68 < *v64 );
      if ( v67 )
      {
        v49 = v82;
        v27 = -1073740965;
        v26 = 0;
        v10 = a9;
        goto LABEL_188;
      }
    }
LABEL_139:
    v71 = v62 - 24;
    v72 = v64 + 6;
    while ( 1 )
    {
      if ( v71 <= 8 )
        goto LABEL_165;
      v73 = v71 - 8;
      v74 = _byteswap_ulong(v72[1]);
      if ( v73 < (unsigned int)v74 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v74, v73);
        goto LABEL_131;
      }
      v75 = (unsigned __int8 *)(v72 + 2);
      if ( _byteswap_ulong(*v72) == 2 )
        break;
      v72 = (unsigned int *)&v75[(unsigned int)v74];
      v71 = v73 - v74;
    }
    if ( v72 == (unsigned int *)-8LL )
    {
LABEL_165:
      v53 = (union _LARGE_INTEGER *)v85;
      goto LABEL_167;
    }
    v27 = Pku2uComputeFinishedChecksum(v85, (struct _PKU2U_CONTEXT *)((char *)v85 + 224), (struct KERB_CHECKSUM *)&v87);
    if ( v27 < 0 )
    {
LABEL_148:
      v26 = v88;
      goto LABEL_133;
    }
    v76 = KerbUnpackData(v75, v73, 0x1Fu, &v86);
    if ( v76 )
    {
      v27 = KerbMapKerbError(v76);
      goto LABEL_148;
    }
    v26 = v88;
    if ( *(_DWORD *)v86 == (_DWORD)v87 && *((_DWORD *)v86 + 2) == DWORD2(v87) )
    {
      v77 = 0;
      v78 = 0;
      if ( !DWORD2(v87) )
        goto LABEL_155;
      do
      {
        v79 = *((_BYTE *)v88 + v78);
        v80 = *(_BYTE *)(v78 + *((_QWORD *)v86 + 2));
        v78 = (unsigned int)(v78 + 1);
        v77 |= v80 ^ v79;
      }
      while ( (unsigned int)v78 < DWORD2(v87) );
      if ( !v77 )
      {
LABEL_155:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids);
        v53 = (union _LARGE_INTEGER *)v85;
        goto LABEL_172;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids);
    v27 = -2146893048;
    goto LABEL_133;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v66);
LABEL_131:
  v27 = -2146893048;
LABEL_132:
  v26 = 0;
LABEL_133:
  v49 = v82;
  v10 = a9;
LABEL_188:
  if ( !v84 )
    goto LABEL_193;
  if ( (v49 & 0x20000000) == 0 )
    *v10 = 0;
  KerbFreeData(0x23u, v84);
LABEL_192:
  v84 = 0;
LABEL_193:
  if ( v86 )
    KerbFreeData(0x1Fu, v86);
LABEL_195:
  if ( v26 )
    Pku2uFree(v26);
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x18000d220  mov     r11, rsp
0x18000d223  push    rbp
0x18000d224  push    rsi
0x18000d225  push    rdi
0x18000d226  lea     rbp, [r11-28h]
0x18000d22a  sub     rsp, 110h
0x18000d231  mov     rax, cs:__security_cookie
0x18000d238  xor     rax, rsp
0x18000d23b  mov     [rbp+20h+var_48], rax
0x18000d23f  mov     rax, [rbp+20h+arg_30]
0x18000d243  xor     esi, esi
0x18000d245  mov     r10, [rbp+20h+arg_40]
0x18000d249  xorps   xmm0, xmm0
0x18000d24c  mov     [r11-20h], rbx
0x18000d250  xorps   xmm1, xmm1
0x18000d253  mov     [r11-28h], r12
0x18000d257  lea     ebx, [r8-1]
0x18000d25b  mov     r12, [rbp+20h+arg_28]
0x18000d25f  mov     [r11-30h], r13
0x18000d263  mov     r13, [rbp+20h+arg_20]
0x18000d267  mov     [r11-38h], r14
0x18000d26b  mov     [r11-40h], r15
0x18000d26f  mov     r11, r9
0x18000d272  mov     r15, rdx
0x18000d275  mov     [rbp+20h+var_70], r9
0x18000d279  mov     rdx, [rbp+20h+arg_48]
0x18000d27d  mov     r9, rcx
0x18000d280  mov     [rbp+20h+var_78], rdx
0x18000d284  xor     edx, edx
0x18000d286  mov     [r11], rsi
0x18000d289  mov     [rsp+120h+var_A8], rcx
0x18000d28e  mov     rcx, [rbp+20h+arg_38]
0x18000d292  movups  xmmword ptr [r9+0E0h], xmm0
0x18000d29a  mov     [r9+0F0h], rdx
0x18000d2a1  movups  xmmword ptr [rax], xmm1
0x18000d2a4  mov     [rax+10h], rdx
0x18000d2a8  movups  xmmword ptr [rcx], xmm1
0x18000d2ab  mov     qword ptr [rbp+20h+TimeFields.Year], rax
0x18000d2af  xor     eax, eax
0x18000d2b1  mov     [rcx+10h], rax
0x18000d2b5  mov     [r13+0], rsi
0x18000d2b9  mov     [r12], rsi
0x18000d2bd  mov     [r10], esi
0x18000d2c0  mov     [r9+40h], esi
0x18000d2c4  mov     [rsp+120h+var_B8], r12
0x18000d2c9  mov     [rbp+20h+var_80], rcx
0x18000d2cd  mov     [rsp+120h+var_C8], r10
0x18000d2d2  mov     [rsp+120h+var_B0], rsi
0x18000d2d7  mov     dword ptr [rsp+120h+var_D0], esi
0x18000d2db  mov     [rsp+120h+var_C0], rdx
0x18000d2e0  mov     [rbp+20h+var_88], rdx
0x18000d2e4  mov     [rbp+20h+var_A0], rsi
0x18000d2e8  movups  [rbp+20h+var_98], xmm0
0x18000d2ec  test    ebx, ebx
0x18000d2ee  js      loc_18000DCEA
0x18000d2f4  cmp     byte ptr [r15], 60h ; '`'
0x18000d2f8  mov     r14d, cs:?pku2u_global_oids@@3PAUgss_OID_desc_struct@@A; gss_OID_desc_struct near * pku2u_global_oids
0x18000d2ff  jnz     loc_18000DCEA
0x18000d305  cmp     ebx, 1
0x18000d308  jl      loc_18000DCEA
0x18000d30e  movzx   r8d, byte ptr [r15+1]
0x18000d313  lea     rdx, [r15+2]
0x18000d317  lea     edi, [rbx-1]
0x18000d31a  test    r8b, r8b
0x18000d31d  jns     short loc_18000D357
0x18000d31f  and     r8b, 7Fh
0x18000d323  movzx   eax, r8b
0x18000d327  inc     eax
0x18000d329  cmp     eax, edi
0x18000d32b  jg      loc_18000D3E5
0x18000d331  cmp     r8b, 4
0x18000d335  ja      loc_18000D3E5
0x18000d33b  mov     ecx, esi
0x18000d33d  test    r8b, r8b
0x18000d340  jz      short loc_18000D35A
0x18000d342  movzx   eax, byte ptr [rdx]
0x18000d345  dec     edi
0x18000d347  shl     ecx, 8
0x18000d34a  inc     rdx
0x18000d34d  add     ecx, eax
0x18000d34f  add     r8b, 0FFh
0x18000d353  jnz     short loc_18000D342
0x18000d355  jmp     short loc_18000D35A
0x18000d357  mov     ecx, r8d
0x18000d35a  cmp     ecx, edi
0x18000d35c  jg      loc_18000D3E5
0x18000d362  test    ecx, ecx
0x18000d364  js      short loc_18000D3E5
0x18000d366  cmp     ecx, edi
0x18000d368  jnz     short loc_18000D3DB
0x18000d36a  sub     edi, 1
0x18000d36d  js      short loc_18000D3DB
0x18000d36f  cmp     byte ptr [rdx], 6
0x18000d372  jnz     short loc_18000D3DB
0x18000d374  sub     edi, 1
0x18000d377  js      short loc_18000D3DB
0x18000d379  movzx   esi, byte ptr [rdx+1]
0x18000d37d  sub     edi, esi
0x18000d37f  js      short loc_18000D3DB
0x18000d381  cmp     esi, r14d
0x18000d384  jnz     short loc_18000D3EE
0x18000d386  lea     r12, [rdx+2]
0x18000d38a  movsxd  r8, esi; Size
0x18000d38d  mov     rdx, cs:Src; Buf2
0x18000d394  mov     rcx, r12; Buf1
0x18000d397  call    memcmp_0
0x18000d39c  test    eax, eax
0x18000d39e  jnz     short loc_18000D3C5
0x18000d3a0  lea     eax, [rdi-2]
0x18000d3a3  test    eax, eax
0x18000d3a5  js      short loc_18000D3D1
0x18000d3a7  cmp     byte ptr [rsi+r12], 5
0x18000d3ac  jnz     short loc_18000D3C5
0x18000d3ae  cmp     byte ptr [rsi+r12+1], 0
0x18000d3b4  jnz     short loc_18000D3C5
0x18000d3b6  mov     rsi, [rsp+120h+var_C0]
0x18000d3bb  mov     edi, 118h
0x18000d3c0  jmp     loc_18000DD7F
0x18000d3c5  mov     r12, [rsp+120h+var_B8]
0x18000d3ca  mov     r10, [rsp+120h+var_C8]
0x18000d3cf  jmp     short loc_18000D3EE
0x18000d3d1  mov     r12, [rsp+120h+var_B8]
0x18000d3d6  mov     r10, [rsp+120h+var_C8]
0x18000d3db  cmp     byte ptr [r15], 60h ; '`'
0x18000d3df  jnz     loc_18000DCEA
0x18000d3e5  cmp     ebx, 1
0x18000d3e8  jl      loc_18000DCEA
0x18000d3ee  movzx   r8d, byte ptr [r15+1]
0x18000d3f3  lea     rdx, [r15+2]
0x18000d3f7  dec     ebx
0x18000d3f9  test    r8b, r8b
0x18000d3fc  jns     short loc_18000D436
0x18000d3fe  and     r8b, 7Fh
0x18000d402  movzx   eax, r8b
0x18000d406  inc     eax
0x18000d408  cmp     eax, ebx
0x18000d40a  jg      loc_18000DCEA
0x18000d410  cmp     r8b, 4
0x18000d414  ja      loc_18000DCEA
0x18000d41a  xor     ecx, ecx
0x18000d41c  test    r8b, r8b
0x18000d41f  jz      short loc_18000D439
0x18000d421  movzx   eax, byte ptr [rdx]
0x18000d424  dec     ebx
0x18000d426  shl     ecx, 8
0x18000d429  inc     rdx
0x18000d42c  add     ecx, eax
0x18000d42e  add     r8b, 0FFh
0x18000d432  jnz     short loc_18000D421
0x18000d434  jmp     short loc_18000D439
0x18000d436  mov     ecx, r8d
0x18000d439  cmp     ecx, ebx
0x18000d43b  jg      loc_18000DCEA
0x18000d441  test    ecx, ecx
0x18000d443  js      loc_18000DCEA
0x18000d449  cmp     ecx, ebx
0x18000d44b  jnz     loc_18000DCEA
0x18000d451  sub     ebx, 1
0x18000d454  js      loc_18000DCEA
0x18000d45a  cmp     byte ptr [rdx], 6
0x18000d45d  jnz     loc_18000DCEA
0x18000d463  sub     ebx, 1
0x18000d466  js      loc_18000DCEA
0x18000d46c  movzx   edi, byte ptr [rdx+1]
0x18000d470  sub     ebx, edi
0x18000d472  js      loc_18000DCEA
0x18000d478  cmp     edi, r14d
0x18000d47b  jnz     loc_18000DCEA
0x18000d481  lea     r14, [rdx+2]
0x18000d485  movsxd  r8, edi; Size
0x18000d488  mov     rdx, cs:Src; Buf2
0x18000d48f  mov     rcx, r14; Buf1
0x18000d492  call    memcmp_0
0x18000d497  test    eax, eax
0x18000d499  jnz     loc_18000DCE5
0x18000d49f  lea     esi, [rbx-2]
0x18000d4a2  test    esi, esi
0x18000d4a4  js      loc_18000DCE5
0x18000d4aa  cmp     byte ptr [rdi+r14], 1
0x18000d4af  jnz     loc_18000DCE5
0x18000d4b5  cmp     [rdi+r14+1], al
0x18000d4ba  jnz     loc_18000DCE5
0x18000d4c0  mov     [rsp+120h+var_B8], 0
0x18000d4c9  test    esi, esi
0x18000d4cb  jz      loc_18000DC88
0x18000d4d1  lea     rbx, [r14+2]
0x18000d4d5  add     rbx, rdi
0x18000d4d8  jz      loc_18000DC88
0x18000d4de  cmp     cs:?fKRB5ModuleStarted@@3HA, eax; int fKRB5ModuleStarted
0x18000d4e4  jnz     short loc_18000D54D
0x18000d4e6  mov     dword ptr [rsp+40h], 32756B70h
0x18000d4ee  lea     rax, qword_180049F80
0x18000d4f5  mov     qword ptr [rsp+120h+var_E8], rax
0x18000d4fa  mov     edx, 400h
0x18000d4ff  lea     rax, off_180047030
0x18000d506  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x18000d510  mov     [rsp+120h+var_F0], rax
0x18000d515  mov     ecx, 10000h
0x18000d51a  lea     rax, off_1800471C0
0x18000d521  mov     r9d, 31h ; '1'
0x18000d527  mov     [rsp+120h+var_F8], rax
0x18000d52c  mov     r8d, 1000h
0x18000d532  lea     rax, off_180047350
0x18000d539  mov     [rsp+120h+var_100], rax
0x18000d53e  call    cs:__imp_ASN1_CreateModule
0x18000d544  mov     cs:PKU2UMSG_Module, rax
0x18000d54b  jmp     short loc_18000D554
0x18000d54d  mov     rax, cs:PKU2UMSG_Module
0x18000d554  xor     r9d, r9d
0x18000d557  mov     [rsp+120h+var_100], 0
0x18000d560  xor     r8d, r8d
0x18000d563  lea     rdx, [rsp+120h+var_B8]
0x18000d568  mov     rcx, rax
0x18000d56b  call    cs:__imp_ASN1_CreateDecoder
0x18000d571  test    eax, eax
0x18000d573  jz      short loc_18000D5EF
0x18000d575  mov     r10, cs:WPP_GLOBAL_Control
0x18000d57c  lea     r15, WPP_GLOBAL_Control
0x18000d583  mov     edi, 3Ch ; '<'
0x18000d588  cmp     r10, r15
0x18000d58b  jz      loc_18000DD2F
0x18000d591  test    byte ptr [r10+1Ch], 1
0x18000d596  jz      short loc_18000D5B7
0x18000d598  mov     rcx, [r10+10h]
0x18000d59c  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000d5a3  mov     edx, 4Dh ; 'M'
0x18000d5a8  mov     r9d, eax
0x18000d5ab  call    WPP_SF_d
0x18000d5b0  mov     r10, cs:WPP_GLOBAL_Control
0x18000d5b7  cmp     r10, r15
0x18000d5ba  jz      loc_18000DD2F
0x18000d5c0  test    byte ptr [r10+1Ch], 1
0x18000d5c5  jz      loc_18000DCC3
0x18000d5cb  mov     rcx, [r10+10h]
0x18000d5cf  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000d5d6  mov     edx, 50h ; 'P'
0x18000d5db  mov     r9d, edi
0x18000d5de  call    WPP_SF_d
0x18000d5e3  mov     r10, cs:WPP_GLOBAL_Control
0x18000d5ea  jmp     loc_18000DCC3
0x18000d5ef  mov     rcx, [rsp+120h+var_B8]
0x18000d5f4  lea     rdx, [rsp+120h+var_B0]
0x18000d5f9  mov     dword ptr [rsp+120h+var_F8], esi
0x18000d5fd  xor     edi, edi
0x18000d5ff  mov     esi, 8
0x18000d604  mov     [rsp+120h+var_B0], rdi
0x18000d609  mov     r9d, esi
0x18000d60c  mov     [rsp+120h+var_100], rbx
0x18000d611  mov     r8d, 23h ; '#'
0x18000d617  call    cs:__imp_ASN1_Decode
0x18000d61d  mov     ebx, eax
0x18000d61f  test    eax, eax
0x18000d621  jns     loc_18000D6E8
0x18000d627  mov     r10, cs:WPP_GLOBAL_Control
0x18000d62e  lea     r15, WPP_GLOBAL_Control
0x18000d635  cmp     r10, r15
0x18000d638  jz      short loc_18000D660
0x18000d63a  test    byte ptr [r10+1Ch], 4
0x18000d63f  jz      short loc_18000D660
0x18000d641  mov     rcx, [r10+10h]
0x18000d645  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000d64c  mov     edx, 51h ; 'Q'
0x18000d651  mov     r9d, eax
0x18000d654  call    WPP_SF_d
0x18000d659  mov     r10, cs:WPP_GLOBAL_Control
0x18000d660  cmp     ebx, 0FFFFFC0Fh
0x18000d666  jz      short loc_18000D6AA
0x18000d668  cmp     ebx, 0FFFFFC16h
0x18000d66e  jz      short loc_18000D6AA
0x18000d670  cmp     ebx, 0FFFFFC0Dh
0x18000d676  jz      short loc_18000D6A3
0x18000d678  cmp     r10, r15
0x18000d67b  jz      short loc_18000D6A3
0x18000d67d  test    byte ptr [r10+1Ch], 1
0x18000d682  jz      short loc_18000D6A3
0x18000d684  mov     rcx, [r10+10h]
0x18000d688  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000d68f  mov     edx, 53h ; 'S'
0x18000d694  mov     r9d, ebx
0x18000d697  call    WPP_SF_d
0x18000d69c  mov     r10, cs:WPP_GLOBAL_Control
0x18000d6a3  mov     edi, 3Ch ; '<'
0x18000d6a8  jmp     short loc_18000D6DD
0x18000d6aa  cmp     r10, r15
0x18000d6ad  jz      short loc_18000D6D8
0x18000d6af  test    byte ptr [r10+1Ch], 4
0x18000d6b4  jz      short loc_18000D6D8
0x18000d6b6  mov     rcx, [r10+10h]
0x18000d6ba  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000d6c1  mov     edx, 52h ; 'R'
0x18000d6c6  mov     r9d, 23h ; '#'
0x18000d6cc  call    WPP_SF_d
0x18000d6d1  mov     r10, cs:WPP_GLOBAL_Control
0x18000d6d8  mov     edi, 80000001h
0x18000d6dd  mov     [rsp+120h+var_B0], 0
0x18000d6e6  jmp     short loc_18000D6F6
0x18000d6e8  mov     r10, cs:WPP_GLOBAL_Control
0x18000d6ef  lea     r15, WPP_GLOBAL_Control
0x18000d6f6  mov     rcx, [rsp+120h+var_B8]
0x18000d6fb  test    rcx, rcx
  ... truncated ...
```
