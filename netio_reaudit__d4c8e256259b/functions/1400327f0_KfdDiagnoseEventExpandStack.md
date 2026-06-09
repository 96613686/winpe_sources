# KfdDiagnoseEventExpandStack

- ea: `0x1400327f0`
- end: `0x14003392b`
- name: `KfdDiagnoseEventExpandStack`
- size: `4411`
- prototype: `EXPAND_STACK_CALLOUT`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation`

## callers

- `0x140032770`

## callees

- `0x14000afa0`
- `0x14002a4c0`
- `0x14002a9a0`
- `0x14002dab0`
- `0x1400327f0`
- `0x140037600`
- `0x14003af30`
- `0x14004efd4`
- `0x140074f74`
- `0x1400750b8`
- `0x1400751cc`
- `0x140075234`
- `0x1400753ac`
- `0x140075534`
- `0x1400757b8`
- `0x140077fa0`
- `0x140078400`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140033841`
- `ntoskrnl!EtwWrite` at `0x140033841`
- `ntoskrnl!EtwEventEnabled` at `0x1400328e7`
- `ntoskrnl!EtwEventEnabled` at `0x140032f0a`
- `ntoskrnl!EtwEventEnabled` at `0x1400328e7`
- `ntoskrnl!EtwEventEnabled` at `0x140032f0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400338c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033902`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400338c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033902`

## string_xrefs

- `0x140033870`: `EtwWrite`

## pseudocode

```c
void __fastcall KfdDiagnoseEventExpandStack(unsigned int *Parameter)
{
  __int16 v2; // di
  int v3; // eax
  REGHANDLE v4; // rcx
  __int128 v5; // xmm0
  ULONGLONG v6; // rax
  int v7; // edx
  int v8; // edx
  __int16 v9; // ax
  __int16 v10; // ax
  bool v11; // zf
  __int16 v12; // ax
  unsigned int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  unsigned int v18; // ecx
  unsigned int v19; // edi
  unsigned __int64 v20; // rax
  __int128 *v21; // rax
  unsigned __int64 v22; // rax
  __int64 v23; // rdx
  int v24; // ecx
  __int64 v25; // rax
  unsigned int v26; // eax
  unsigned int v27; // edi
  _QWORD *v28; // rax
  _QWORD *v29; // r9
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r8
  __int64 v33; // r14
  REGHANDLE *v34; // r15
  REGHANDLE v35; // rcx
  int v36; // esi
  ULONGLONG v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  PDEVICE_OBJECT v44; // rcx
  int v45; // edx
  const char *v46; // r11
  unsigned __int32 v47; // r8d
  unsigned __int32 v48; // edx
  const char *v49; // r11
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  __int16 v52; // ax
  NTSTATUS v53; // eax
  __int64 i; // rbx
  void *v55; // rcx
  int v56; // [rsp+28h] [rbp-E8h]
  _QWORD v57[30]; // [rsp+90h] [rbp-80h] BYREF
  __int128 v58; // [rsp+180h] [rbp+70h] BYREF
  __int128 v59; // [rsp+190h] [rbp+80h]
  __int128 v60; // [rsp+1A0h] [rbp+90h]
  __int64 v61; // [rsp+1B0h] [rbp+A0h]
  __int128 v62; // [rsp+1C0h] [rbp+B0h] BYREF
  __int128 v63; // [rsp+1D0h] [rbp+C0h]
  __int128 v64; // [rsp+1E0h] [rbp+D0h]
  __int128 v65; // [rsp+1F0h] [rbp+E0h]
  __int128 v66; // [rsp+200h] [rbp+F0h]
  __int128 v67; // [rsp+210h] [rbp+100h]
  __int64 v68; // [rsp+220h] [rbp+110h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+230h] [rbp+120h] BYREF
  __int128 v70; // [rsp+240h] [rbp+130h] BYREF
  __int128 v71; // [rsp+250h] [rbp+140h]
  _QWORD UserDataCount[52]; // [rsp+260h] [rbp+150h] BYREF

  memset(v57, 0, sizeof(v57));
  v2 = *((_WORD *)Parameter + 4);
  v58 = 0;
  v61 = 0;
  v59 = 0;
  v68 = 0;
  v60 = 0;
  v70 = 0;
  v71 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  if ( *((_BYTE *)Parameter + 704) )
  {
    v3 = 3;
    if ( v2 == 33 )
      v3 = 9;
  }
  else
  {
    v3 = 6;
  }
  LODWORD(v57[17]) = v3;
  v4 = *(_QWORD *)gDiagnosticHandle;
  v5 = *(_OWORD *)&BFE_NET_EVENT_TYPES[2 * v3];
  v6 = Parameter[90];
  *(_QWORD *)&EventDescriptor.Id = v5;
  EventDescriptor.Keyword = v6;
  if ( !EtwEventEnabled(v4, &EventDescriptor) )
    return;
  v7 = 0;
  LOBYTE(v57[2]) = 0;
  if ( v2 == 2 )
  {
    LOBYTE(v57[2]) = *((_BYTE *)Parameter + 272);
    HIDWORD(v57[2]) = _byteswap_ulong(Parameter[3]);
    v10 = __ROR2__(*((_WORD *)Parameter + 5), 8);
    v11 = v10 == 0;
    WORD2(v57[6]) = v10;
    HIDWORD(v57[4]) = _byteswap_ulong(Parameter[35]);
    v12 = *((_WORD *)Parameter + 69);
    HIDWORD(v57[1]) = 0;
    LODWORD(v57[11]) = 0;
    if ( !v11 )
      v7 = 8;
    HIWORD(v57[6]) = __ROR2__(v12, 8);
    if ( HIWORD(v57[6]) )
      v7 |= 0x10u;
    goto LABEL_19;
  }
  if ( v2 == 23 )
  {
    LOBYTE(v57[2]) = *((_BYTE *)Parameter + 272);
    *(_QWORD *)((char *)&v57[2] + 4) = *((_QWORD *)Parameter + 2);
    *(_QWORD *)((char *)&v57[3] + 4) = *((_QWORD *)Parameter + 3);
    WORD2(v57[6]) = __ROR2__(*((_WORD *)Parameter + 5), 8);
    *(_QWORD *)((char *)&v57[4] + 4) = *((_QWORD *)Parameter + 18);
    *(_QWORD *)((char *)&v57[5] + 4) = *((_QWORD *)Parameter + 19);
    v7 = (WORD2(v57[6]) != 0 ? 8 : 0) | 0x10;
    v9 = __ROR2__(*((_WORD *)Parameter + 69), 8);
    HIDWORD(v57[1]) = 1;
    LODWORD(v57[11]) = 1;
    if ( !v9 )
      v7 = WORD2(v57[6]) != 0 ? 8 : 0;
    HIWORD(v57[6]) = v9;
LABEL_19:
    v8 = v7 | 0x107;
    goto LABEL_20;
  }
  if ( v2 != 33 )
    __fastfail(5u);
  HIDWORD(v57[1]) = 2;
  v8 = 256;
  LODWORD(v57[11]) = 2;
LABEL_20:
  v13 = Parameter[85];
  LODWORD(v57[1]) = v8;
  LODWORD(v57[7]) = v13;
  if ( v13 )
  {
    v8 |= 0x80u;
    LODWORD(v57[1]) = v8;
  }
  v14 = *((_QWORD *)Parameter + 38);
  if ( v14 )
  {
    v15 = *((unsigned __int16 *)Parameter + 149);
    v8 |= 0x20u;
    LODWORD(v57[1]) = v8;
    LODWORD(v57[8]) = v15;
    v57[9] = v14;
  }
  if ( *((_QWORD *)Parameter + 39) )
  {
    v8 |= 0x40u;
    v57[10] = *((_QWORD *)Parameter + 39);
    LODWORD(v57[1]) = v8;
  }
  if ( *((_QWORD *)Parameter + 89) )
  {
    v8 |= 0x400u;
    v57[12] = *((_QWORD *)Parameter + 89);
    LODWORD(v57[1]) = v8;
  }
  if ( *((_QWORD *)Parameter + 94) )
  {
    v8 |= 0x800u;
    v57[13] = *((_QWORD *)Parameter + 94);
    LODWORD(v57[1]) = v8;
  }
  if ( *((_QWORD *)Parameter + 95) )
  {
    v8 |= 0x1000u;
    v57[14] = *((_QWORD *)Parameter + 95);
    LODWORD(v57[1]) = v8;
  }
  v16 = *((_QWORD *)Parameter + 97);
  if ( v16 )
  {
    v17 = *((unsigned __int16 *)Parameter + 385);
    v8 |= 0x2000u;
    LODWORD(v57[1]) = v8;
    LODWORD(v57[15]) = v17;
    v57[16] = v16;
  }
  v18 = Parameter[96];
  if ( v18 )
  {
    v8 |= 0x200u;
    LODWORD(v57[1]) = v8;
  }
  v19 = v57[17];
  switch ( LODWORD(v57[17]) )
  {
    case 9:
      LODWORD(v62) = *(unsigned int *)((char *)Parameter + 10);
      WORD2(v62) = *((_WORD *)Parameter + 7);
      *(_DWORD *)((char *)&v62 + 6) = *(unsigned int *)((char *)Parameter + 138);
      WORD5(v62) = *((_WORD *)Parameter + 71);
      WORD2(v63) = *((_WORD *)Parameter + 136);
      LOWORD(v64) = *((_WORD *)Parameter + 204);
      v66 = *(_OWORD *)(Parameter + 97);
      *(_QWORD *)&v65 = *((_QWORD *)Parameter + 35);
      WORD4(v65) = *((_WORD *)Parameter + 132);
      v20 = *((_QWORD *)Parameter + 33) - 56LL;
      LODWORD(v57[1]) = v8 & 0xFFFFFF7F;
      HIDWORD(v65) = v18;
      HIDWORD(v62) = Parameter[103];
      LODWORD(v63) = Parameter[101];
      if ( v20 <= 3 )
      {
        *((_QWORD *)&v64 + 1) = *((_QWORD *)Parameter + 47);
        DWORD2(v63) = Parameter[104];
      }
      else
      {
        LODWORD(v67) = *((unsigned __int16 *)Parameter + 340);
        *((_QWORD *)&v67 + 1) = *((_QWORD *)Parameter + 86);
        v68 = *((_QWORD *)Parameter + 87);
      }
      v21 = &v62;
      break;
    case 3:
      v59 = *(_OWORD *)(Parameter + 97);
      *(_QWORD *)&v58 = *((_QWORD *)Parameter + 35);
      WORD4(v58) = *((_WORD *)Parameter + 132);
      v22 = *((_QWORD *)Parameter + 33) - 74LL;
      HIDWORD(v58) = v18;
      if ( v22 <= 3 )
      {
        LODWORD(v60) = *((unsigned __int16 *)Parameter + 340);
        *((_QWORD *)&v60 + 1) = *((_QWORD *)Parameter + 86);
        v61 = *((_QWORD *)Parameter + 87);
      }
      v21 = &v58;
      break;
    case 6:
      *(_QWORD *)&v70 = *((_QWORD *)Parameter + 35);
      WORD4(v70) = *((_WORD *)Parameter + 132);
      v71 = *(_OWORD *)(Parameter + 97);
      v21 = &v70;
      HIDWORD(v70) = v18;
      break;
    default:
      goto LABEL_48;
  }
  v57[18] = v21;
LABEL_48:
  v23 = *((_QWORD *)Parameter + 91);
  v24 = v57[19];
  HIDWORD(v57[19]) = *((unsigned __int8 *)Parameter + 785);
  if ( v23 )
  {
    v25 = *((_QWORD *)Parameter + 90);
    v24 = LODWORD(v57[19]) | 1;
    LODWORD(v57[19]) |= 1u;
    v57[20] = v25;
    v57[21] = v23;
  }
  if ( *((_WORD *)Parameter + 404) && *((_QWORD *)Parameter + 102) )
  {
    v24 |= 2u;
    v57[24] = *((_QWORD *)Parameter + 102);
    LODWORD(v57[19]) = v24;
  }
  v11 = *((_WORD *)Parameter + 368) == 0;
  v57[25] = *((_QWORD *)Parameter + 47);
  if ( !v11 && *((_QWORD *)Parameter + 93) )
  {
    v24 |= 4u;
    v57[26] = *((_QWORD *)Parameter + 93);
    LODWORD(v57[19]) = v24;
  }
  v11 = *((_WORD *)Parameter + 420) == 0;
  v57[27] = *((_QWORD *)Parameter + 104);
  LODWORD(v57[28]) = Parameter[88];
  if ( !v11 && *((_QWORD *)Parameter + 106) )
  {
    v57[29] = *((_QWORD *)Parameter + 106);
    LODWORD(v57[19]) = v24 | 8;
  }
  v26 = *((unsigned __int16 *)Parameter + 400);
  if ( !(_WORD)v26 || !*((_QWORD *)Parameter + 99) )
  {
LABEL_69:
    v33 = *((_QWORD *)Parameter + 46);
    v34 = (REGHANDLE *)gDiagnosticHandle;
    memset(UserDataCount, 0, 0x19Cu);
    v35 = *(_QWORD *)gDiagnosticHandle;
    v36 = 0;
    v37 = Parameter[90];
    *(_QWORD *)&EventDescriptor.Id = BFE_NET_EVENT_TYPES[2 * v19];
    EventDescriptor.Keyword = v37;
    if ( !EtwEventEnabled(v35, &EventDescriptor) )
      goto LABEL_160;
    v40 = LOBYTE(v57[17]) | (unsigned __int16)(BYTE4(v57[1]) << 8);
    if ( v40 > 0x104 )
    {
      v50 = v40 - 262;
      if ( v50 )
      {
        v51 = v50 - 259;
        if ( v51 )
        {
          if ( v51 == 1
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
          {
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, v38, v39, *(unsigned int *)v57[18]);
          }
        }
        else if ( LODWORD(v57[11]) == 2 )
        {
          v52 = *(_WORD *)(v57[18] + 56LL);
          if ( v52 == 56 || v52 == 59 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
            {
              WPP_SF_H_MAC__MAC_DDHIDIH(
                WPP_GLOBAL_Control->AttachedDevice,
                LODWORD(v57[18]) + 6,
                v39,
                *(unsigned __int16 *)(v57[18] + 20LL),
                v57[18],
                v57[18] + 6LL,
                *(_DWORD *)(v57[18] + 12LL),
                *(_DWORD *)(v57[18] + 16LL),
                *(_WORD *)(v57[18] + 32LL),
                *(_QWORD *)(v57[18] + 40LL),
                *(_DWORD *)(v57[18] + 24LL),
                *(_QWORD *)v57[18],
                *(_WORD *)(v57[18] + 8LL));
            }
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
          {
            WPP_SF_H_MAC__MAC_DDHIH(
              WPP_GLOBAL_Control->AttachedDevice,
              LODWORD(v57[18]) + 6,
              v39,
              *(unsigned __int16 *)(v57[18] + 20LL),
              v57[18],
              v57[18] + 6LL,
              *(_DWORD *)(v57[18] + 12LL),
              *(_DWORD *)(v57[18] + 16LL),
              *(_WORD *)(v57[18] + 32LL),
              *(_QWORD *)v57[18],
              *(_WORD *)(v57[18] + 8LL));
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
          WPP_SF_qDh_IPV6__IPV6_HHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x16u,
            LOBYTE(v57[2]),
            (__int64)v57,
            v57[1],
            v57[2],
            (__int64)&v57[2] + 4,
            (__int64)&v57[4] + 4,
            SBYTE4(v57[6]),
            SBYTE6(v57[6]),
            v57[7],
            (unsigned int *)&v57[8],
            (__int64 *)v57[10],
            v57[11],
            (__int64 *)v57[12],
            (const wchar_t *)v57[13],
            v57[14],
            (unsigned int *)&v57[15]);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
          {
            LOWORD(v56) = *(_WORD *)(v57[18] + 8LL);
            WPP_SF_qIHDDDDd(
              WPP_GLOBAL_Control->AttachedDevice,
              23,
              v57[18],
              v57,
              *(_QWORD *)v57[18],
              v56,
              *(_DWORD *)(v57[18] + 12LL),
              *(_DWORD *)(v57[18] + 16LL),
              *(_DWORD *)(v57[18] + 20LL),
              *(_DWORD *)(v57[18] + 24LL),
              *(_DWORD *)(v57[18] + 28LL));
          }
          v44 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
          {
            v45 = 24;
            goto LABEL_154;
          }
        }
      }
    }
    else if ( v40 == 260 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        v49 = "INBOUND";
        if ( *(_DWORD *)(v57[18] + 4LL) != 1 )
          v49 = "OUTBOUND";
        WPP_SF_h_IPV6__IPV6_HHdsLIH(
          WPP_GLOBAL_Control->AttachedDevice,
          v57[18],
          (unsigned int)"OUTBOUND",
          LOBYTE(v57[2]),
          (__int64)&v57[2] + 4,
          (__int64)&v57[4] + 4,
          SBYTE4(v57[6]),
          SBYTE6(v57[6]),
          *(_DWORD *)v57[18],
          (__int64)v49,
          *(_DWORD *)(v57[18] + 8LL),
          *(_QWORD *)(v57[18] + 16LL),
          *(_WORD *)(v57[18] + 24LL));
      }
    }
    else
    {
      v41 = v40 - 3;
      if ( v41 )
      {
        v42 = v41 - 1;
        if ( v42 )
        {
          v43 = v42 - 2;
          if ( v43 )
          {
            if ( v43 == 253 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
                WPP_SF_qDh_IPV6__IPV6_HHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_(
                  (__int64)WPP_GLOBAL_Control->AttachedDevice,
                  0x10u,
                  LOBYTE(v57[2]),
                  (__int64)v57,
                  v57[1],
                  v57[2],
                  (__int64)&v57[2] + 4,
                  (__int64)&v57[4] + 4,
                  SBYTE4(v57[6]),
                  SBYTE6(v57[6]),
                  v57[7],
                  (unsigned int *)&v57[8],
                  (__int64 *)v57[10],
                  v57[11],
                  (__int64 *)v57[12],
                  (const wchar_t *)v57[13],
                  v57[14],
                  (unsigned int *)&v57[15]);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
                  WPP_SF_qIHDDDDd_FWP_BYTE_BLOB_DD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    17,
                    v57[18],
                    (unsigned int)v57,
                    *(_QWORD *)v57[18],
                    *(_WORD *)(v57[18] + 8LL),
                    *(_DWORD *)(v57[18] + 12LL),
                    *(_DWORD *)(v57[18] + 16LL),
                    *(_DWORD *)(v57[18] + 20LL),
                    *(_DWORD *)(v57[18] + 24LL),
                    *(_DWORD *)(v57[18] + 28LL),
                    v57[18] + 32LL,
                    *(_DWORD *)(v57[18] + 48LL),
                    *(_DWORD *)(v57[18] + 52LL));
                v44 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
                {
                  v45 = 18;
LABEL_154:
                  WPP_SF_qLLISSISIL(
                    v44->AttachedDevice,
                    v45,
                    v39,
                    (unsigned int)v57,
                    v57[19],
                    SBYTE4(v57[19]),
                    v57[20],
                    v57[21],
                    v57[24],
                    v57[25],
                    v57[26],
                    v57[27],
                    v57[28]);
                }
              }
            }
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
              WPP_SF_qDhDDHHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_(
                (__int64)WPP_GLOBAL_Control->AttachedDevice,
                0x13u,
                LOBYTE(v57[2]),
                (__int64)v57,
                v57[1],
                v57[2],
                _byteswap_ulong(HIDWORD(v57[2])),
                _byteswap_ulong(HIDWORD(v57[4])),
                SBYTE4(v57[6]),
                SBYTE6(v57[6]),
                v57[7],
                (unsigned int *)&v57[8],
                (__int64 *)v57[10],
                v57[11],
                (__int64 *)v57[12],
                (const wchar_t *)v57[13],
                v57[14],
                (unsigned int *)&v57[15]);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
              {
                LOWORD(v56) = *(_WORD *)(v57[18] + 8LL);
                WPP_SF_qIHDDDDd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  20,
                  v57[18],
                  v57,
                  *(_QWORD *)v57[18],
                  v56,
                  *(_DWORD *)(v57[18] + 12LL),
                  *(_DWORD *)(v57[18] + 16LL),
                  *(_DWORD *)(v57[18] + 20LL),
                  *(_DWORD *)(v57[18] + 24LL),
                  *(_DWORD *)(v57[18] + 28LL));
              }
              v44 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
              {
                v45 = 21;
                goto LABEL_154;
              }
            }
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          v46 = "INBOUND";
          if ( *(_DWORD *)(v57[18] + 4LL) != 1 )
            v46 = "OUTBOUND";
          v47 = _byteswap_ulong(HIDWORD(v57[4]));
          v48 = _byteswap_ulong(HIDWORD(v57[2]));
          WPP_SF_hDDHHdsLIH(
            WPP_GLOBAL_Control->AttachedDevice,
            v48,
            v47,
            LOBYTE(v57[2]),
            v48,
            v47,
            SBYTE4(v57[6]),
            SBYTE6(v57[6]),
            *(_DWORD *)v57[18],
            (__int64)v46,
            *(_DWORD *)(v57[18] + 8LL),
            *(_QWORD *)(v57[18] + 16LL),
            *(_WORD *)(v57[18] + 24LL));
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
          WPP_SF_qDhDDHHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0xDu,
            LOBYTE(v57[2]),
            (__int64)v57,
            v57[1],
            v57[2],
            _byteswap_ulong(HIDWORD(v57[2])),
            _byteswap_ulong(HIDWORD(v57[4])),
            SBYTE4(v57[6]),
            SBYTE6(v57[6]),
            v57[7],
            (unsigned int *)&v57[8],
            (__int64 *)v57[10],
            v57[11],
            (__int64 *)v57[12],
            (const wchar_t *)v57[13],
            v57[14],
            (unsigned int *)&v57[15]);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
            WPP_SF_qIHDDDDd_FWP_BYTE_BLOB_DD(
              WPP_GLOBAL_Control->AttachedDevice,
              14,
              v57[18],
              (unsigned int)v57,
              *(_QWORD *)v57[18],
              *(_WORD *)(v57[18] + 8LL),
              *(_DWORD *)(v57[18] + 12LL),
              *(_DWORD *)(v57[18] + 16LL),
              *(_DWORD *)(v57[18] + 20LL),
              *(_DWORD *)(v57[18] + 24LL),
              *(_DWORD *)(v57[18] + 28LL),
              v57[18] + 32LL,
              *(_DWORD *)(v57[18] + 48LL),
              *(_DWORD *)(v57[18] + 52LL));
          v44 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
          {
            v45 = 15;
            goto LABEL_154;
          }
        }
      }
    }
    BfeNetEventConvertToData((__int64)v57, (unsigned int *)UserDataCount);
    v36 = 1;
    v53 = EtwWrite(*v34, &EventDescriptor, 0, UserDataCount[0], (PEVENT_DATA_DESCRIPTOR)&UserDataCount[1]);
    if ( v53 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"EtwWrite",
          v53);
      }
      goto LABEL_161;
    }
LABEL_160:
    WfpWriteNeteventToUnifiedTrace(v57, v33);
    if ( !v36 )
    {
LABEL_165:
      if ( v57[23] )
        ExFreePoolWithTag((PVOID)v57[23], 0);
      return;
    }
LABEL_161:
    for ( i = 0; i != 2; ++i )
    {
      v55 = (void *)UserDataCount[i + 50];
      if ( v55 )
        ExFreePoolWithTag(v55, 0x70707746u);
      UserDataCount[i + 50] = 0xBADBADFABADBADFAuLL;
    }
    goto LABEL_165;
  }
  LOWORD(v57[22]) = *((_WORD *)Parameter + 400);
  WfpPoolAllocNonPaged(16LL * v26, 1718896215, &v57[23]);
  if ( v57[23] )
  {
    v27 = 0;
    memset((void *)v57[23], 0, 16LL * LOWORD(v57[22]));
    v28 = (_QWORD *)*((_QWORD *)Parameter + 99);
    v29 = (_QWORD *)*v28;
    if ( (_QWORD *)*v28 != v28 )
    {
      do
      {
        v30 = v29[2];
        v31 = v27++;
        v32 = v57[23] + 16 * v31;
        *(_QWORD *)v32 = **(_QWORD **)(v30 + 24);
        *(_DWORD *)(v32 + 8) = *(unsigned __int16 *)(*(_QWORD *)(v30 + 24) + 24LL);
        *(_DWORD *)(v32 + 12) = *((_DWORD *)v29 + 6);
        v29 = (_QWORD *)*v29;
      }
      while ( v29 != *((_QWORD **)Parameter + 99) );
    }
    v19 = v57[17];
    goto LABEL_69;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"KfdDiagnoseEventExpandStack",
      23);
    goto LABEL_165;
  }
}

```

## disassembly

```asm
0x1400327f0  push    rbp
0x1400327f2  push    rbx
0x1400327f3  push    rdi
0x1400327f4  push    r12
0x1400327f6  lea     rbp, [rsp-308h]
0x1400327fe  sub     rsp, 418h
0x140032805  mov     rax, cs:__security_cookie
0x14003280c  xor     rax, rsp
0x14003280f  mov     [rbp+320h+var_30], rax
0x140032816  mov     rbx, rcx
0x140032819  xor     edx, edx; Val
0x14003281b  lea     rcx, [rbp+320h+var_3A0]; void *
0x14003281f  mov     r8d, 0F0h; Size
0x140032825  call    memset
0x14003282a  movzx   edi, word ptr [rbx+8]
0x14003282e  xorps   xmm1, xmm1
0x140032831  xorps   xmm0, xmm0
0x140032834  xor     eax, eax
0x140032836  movups  [rbp+320h+var_2B0], xmm0
0x14003283a  mov     [rbp+320h+var_280], rax
0x140032841  movups  [rbp+320h+var_2A0], xmm0
0x140032848  mov     [rbp+320h+var_210], rax
0x14003284f  movups  [rbp+320h+var_290], xmm0
0x140032856  movups  [rbp+320h+var_1F0], xmm0
0x14003285d  movups  [rbp+320h+var_1E0], xmm0
0x140032864  movups  [rbp+320h+var_270], xmm1
0x14003286b  movups  [rbp+320h+var_260], xmm1
0x140032872  movups  [rbp+320h+var_250], xmm1
0x140032879  movups  [rbp+320h+var_240], xmm1
0x140032880  movups  [rbp+320h+var_230], xmm1
0x140032887  movups  [rbp+320h+var_220], xmm1
0x14003288e  cmp     [rbx+2C0h], al
0x140032894  jz      short loc_1400328A9
0x140032896  cmp     di, 21h ; '!'
0x14003289a  mov     eax, 3
0x14003289f  mov     ecx, 9
0x1400328a4  cmovz   eax, ecx
0x1400328a7  jmp     short loc_1400328AE
0x1400328a9  mov     eax, 6
0x1400328ae  mov     rcx, cs:gDiagnosticHandle
0x1400328b5  lea     r12, BFE_NET_EVENT_TYPES
0x1400328bc  mov     [rbp+320h+var_318], eax
0x1400328bf  lea     rdx, [rbp+320h+EventDescriptor]; EventDescriptor
0x1400328c6  cdqe
0x1400328c8  add     rax, rax
0x1400328cb  mov     rcx, [rcx]; RegHandle
0x1400328ce  movups  xmm0, xmmword ptr [r12+rax*8]
0x1400328d3  mov     eax, [rbx+168h]
0x1400328d9  movups  xmmword ptr [rbp+320h+EventDescriptor.Id], xmm0
0x1400328e0  mov     [rbp+320h+EventDescriptor.Keyword], rax
0x1400328e7  call    cs:__imp_EtwEventEnabled
0x1400328ee  nop     dword ptr [rax+rax+00h]
0x1400328f3  test    al, al
0x1400328f5  jz      loc_14003390E
0x1400328fb  xor     edx, edx
0x1400328fd  mov     [rbp+320h+var_390], dl
0x140032900  cmp     di, 2
0x140032904  jz      loc_1400329A3
0x14003290a  cmp     di, 17h
0x14003290e  jz      short loc_140032935
0x140032910  cmp     di, 21h ; '!'
0x140032914  jz      short loc_14003291D
0x140032916  mov     ecx, 5
0x14003291b  int     29h; Win8: RtlFailFast(ecx)
0x14003291d  mov     [rbp+320h+var_394], 2
0x140032924  mov     edx, 100h
0x140032929  mov     [rbp+320h+var_348], 2
0x140032930  jmp     loc_1400329FA
0x140032935  movzx   eax, byte ptr [rbx+110h]
0x14003293c  mov     [rbp+320h+var_390], al
0x14003293f  mov     rax, [rbx+10h]
0x140032943  mov     [rbp+320h+var_38C], rax
0x140032947  mov     rax, [rbx+18h]
0x14003294b  mov     [rbp+320h+var_384], rax
0x14003294f  movzx   eax, word ptr [rbx+0Ah]
0x140032953  ror     ax, 8
0x140032957  mov     [rbp+320h+var_36C], ax
0x14003295b  neg     ax
0x14003295e  mov     rax, [rbx+90h]
0x140032965  sbb     ecx, ecx
0x140032967  mov     [rbp+320h+var_37C], rax
0x14003296b  mov     rax, [rbx+98h]
0x140032972  and     ecx, 8
0x140032975  mov     [rbp+320h+var_374], rax
0x140032979  mov     edx, ecx
0x14003297b  movzx   eax, word ptr [rbx+8Ah]
0x140032982  or      edx, 10h
0x140032985  ror     ax, 8
0x140032989  test    ax, ax
0x14003298c  mov     [rbp+320h+var_394], 1
0x140032993  mov     [rbp+320h+var_348], 1
0x14003299a  cmovz   edx, ecx
0x14003299d  mov     [rbp+320h+var_36A], ax
0x1400329a1  jmp     short loc_1400329F4
0x1400329a3  movzx   eax, byte ptr [rbx+110h]
0x1400329aa  mov     ecx, 8
0x1400329af  mov     [rbp+320h+var_390], al
0x1400329b2  mov     eax, [rbx+0Ch]
0x1400329b5  bswap   eax
0x1400329b7  mov     dword ptr [rbp+320h+var_38C], eax
0x1400329ba  movzx   eax, word ptr [rbx+0Ah]
0x1400329be  ror     ax, 8
0x1400329c2  test    ax, ax
0x1400329c5  mov     [rbp+320h+var_36C], ax
0x1400329c9  mov     eax, [rbx+8Ch]
0x1400329cf  bswap   eax
0x1400329d1  mov     dword ptr [rbp+320h+var_37C], eax
0x1400329d4  movzx   eax, word ptr [rbx+8Ah]
0x1400329db  mov     [rbp+320h+var_394], edx
0x1400329de  mov     [rbp+320h+var_348], edx
0x1400329e1  cmovnz  edx, ecx
0x1400329e4  ror     ax, 8
0x1400329e8  mov     [rbp+320h+var_36A], ax
0x1400329ec  test    ax, ax
0x1400329ef  jz      short loc_1400329F4
0x1400329f1  or      edx, 10h
0x1400329f4  or      edx, 107h
0x1400329fa  mov     eax, [rbx+154h]
0x140032a00  mov     [rbp+320h+var_398], edx
0x140032a03  mov     [rbp+320h+var_368], eax
0x140032a06  test    eax, eax
0x140032a08  jz      short loc_140032A11
0x140032a0a  bts     edx, 7
0x140032a0e  mov     [rbp+320h+var_398], edx
0x140032a11  mov     rcx, [rbx+130h]
0x140032a18  test    rcx, rcx
0x140032a1b  jz      short loc_140032A31
0x140032a1d  movzx   eax, word ptr [rbx+12Ah]
0x140032a24  or      edx, 20h
0x140032a27  mov     [rbp+320h+var_398], edx
0x140032a2a  mov     [rbp+320h+var_360], eax
0x140032a2d  mov     [rbp+320h+var_358], rcx
0x140032a31  mov     rax, [rbx+138h]
0x140032a38  test    rax, rax
0x140032a3b  jz      short loc_140032A47
0x140032a3d  or      edx, 40h
0x140032a40  mov     [rbp+320h+var_350], rax
0x140032a44  mov     [rbp+320h+var_398], edx
0x140032a47  mov     rax, [rbx+2C8h]
0x140032a4e  test    rax, rax
0x140032a51  jz      short loc_140032A5E
0x140032a53  bts     edx, 0Ah
0x140032a57  mov     [rbp+320h+var_340], rax
0x140032a5b  mov     [rbp+320h+var_398], edx
0x140032a5e  mov     rax, [rbx+2F0h]
0x140032a65  test    rax, rax
0x140032a68  jz      short loc_140032A75
0x140032a6a  bts     edx, 0Bh
0x140032a6e  mov     [rbp+320h+var_338], rax
0x140032a72  mov     [rbp+320h+var_398], edx
0x140032a75  mov     rax, [rbx+2F8h]
0x140032a7c  test    rax, rax
0x140032a7f  jz      short loc_140032A8C
0x140032a81  bts     edx, 0Ch
0x140032a85  mov     [rbp+320h+var_330], rax
0x140032a89  mov     [rbp+320h+var_398], edx
0x140032a8c  mov     rcx, [rbx+308h]
0x140032a93  test    rcx, rcx
0x140032a96  jz      short loc_140032AAD
0x140032a98  movzx   eax, word ptr [rbx+302h]
0x140032a9f  bts     edx, 0Dh
0x140032aa3  mov     [rbp+320h+var_398], edx
0x140032aa6  mov     [rbp+320h+var_328], eax
0x140032aa9  mov     [rbp+320h+var_320], rcx
0x140032aad  mov     ecx, [rbx+180h]
0x140032ab3  test    ecx, ecx
0x140032ab5  jz      short loc_140032ABE
0x140032ab7  bts     edx, 9
0x140032abb  mov     [rbp+320h+var_398], edx
0x140032abe  mov     edi, [rbp+320h+var_318]
0x140032ac1  cmp     edi, 9
0x140032ac4  jnz     loc_140032BFB
0x140032aca  mov     eax, [rbx+0Ah]
0x140032acd  btr     edx, 7
0x140032ad1  mov     dword ptr [rbp+320h+var_270], eax
0x140032ad7  movzx   eax, word ptr [rbx+0Eh]
0x140032adb  mov     word ptr [rbp+320h+var_270+4], ax
0x140032ae2  mov     eax, [rbx+8Ah]
0x140032ae8  mov     dword ptr [rbp+320h+var_270+6], eax
0x140032aee  movzx   eax, word ptr [rbx+8Eh]
0x140032af5  mov     word ptr [rbp+320h+var_270+0Ah], ax
0x140032afc  movzx   eax, word ptr [rbx+110h]
0x140032b03  mov     word ptr [rbp+320h+var_260+4], ax
0x140032b0a  movzx   eax, word ptr [rbx+198h]
0x140032b11  mov     word ptr [rbp+320h+var_250], ax
0x140032b18  mov     eax, [rbx+184h]
0x140032b1e  mov     dword ptr [rbp+320h+var_230], eax
0x140032b24  mov     eax, [rbx+188h]
0x140032b2a  mov     dword ptr [rbp+320h+var_230+4], eax
0x140032b30  mov     eax, [rbx+18Ch]
0x140032b36  mov     dword ptr [rbp+320h+var_230+8], eax
0x140032b3c  mov     eax, [rbx+190h]
0x140032b42  mov     dword ptr [rbp+320h+var_230+0Ch], eax
0x140032b48  mov     rax, [rbx+118h]
0x140032b4f  mov     qword ptr [rbp+320h+var_240], rax
0x140032b56  movzx   eax, word ptr [rbx+108h]
0x140032b5d  mov     word ptr [rbp+320h+var_240+8], ax
0x140032b64  mov     rax, [rbx+108h]
0x140032b6b  sub     rax, 38h ; '8'
0x140032b6f  mov     [rbp+320h+var_398], edx
0x140032b72  cmp     rax, 3
0x140032b76  mov     dword ptr [rbp+320h+var_240+0Ch], ecx
0x140032b7c  mov     eax, [rbx+19Ch]
0x140032b82  mov     dword ptr [rbp+320h+var_270+0Ch], eax
0x140032b88  mov     eax, [rbx+194h]
0x140032b8e  mov     dword ptr [rbp+320h+var_260], eax
0x140032b94  jbe     short loc_140032BD5
0x140032b96  movzx   eax, word ptr [rbx+2A8h]
0x140032b9d  mov     dword ptr [rbp+320h+var_220], eax
0x140032ba3  mov     rax, [rbx+2B0h]
0x140032baa  mov     qword ptr [rbp+320h+var_220+8], rax
0x140032bb1  mov     eax, [rbx+2B8h]
0x140032bb7  mov     dword ptr [rbp+320h+var_210], eax
0x140032bbd  mov     eax, [rbx+2BCh]
0x140032bc3  mov     dword ptr [rbp+320h+var_210+4], eax
0x140032bc9  lea     rax, [rbp+320h+var_270]
0x140032bd0  jmp     loc_140032CF5
0x140032bd5  mov     rax, [rbx+178h]
0x140032bdc  mov     qword ptr [rbp+320h+var_250+8], rax
0x140032be3  mov     eax, [rbx+1A0h]
0x140032be9  mov     dword ptr [rbp+320h+var_260+8], eax
0x140032bef  lea     rax, [rbp+320h+var_270]
0x140032bf6  jmp     loc_140032CF5
0x140032bfb  cmp     edi, 3
0x140032bfe  jnz     loc_140032C97
0x140032c04  mov     eax, [rbx+184h]
0x140032c0a  mov     dword ptr [rbp+320h+var_2A0], eax
0x140032c10  mov     eax, [rbx+188h]
0x140032c16  mov     dword ptr [rbp+320h+var_2A0+4], eax
0x140032c1c  mov     eax, [rbx+18Ch]
0x140032c22  mov     dword ptr [rbp+320h+var_2A0+8], eax
0x140032c28  mov     eax, [rbx+190h]
0x140032c2e  mov     dword ptr [rbp+320h+var_2A0+0Ch], eax
0x140032c34  mov     rax, [rbx+118h]
0x140032c3b  mov     qword ptr [rbp+320h+var_2B0], rax
0x140032c3f  movzx   eax, word ptr [rbx+108h]
0x140032c46  mov     word ptr [rbp+320h+var_2B0+8], ax
0x140032c4a  mov     rax, [rbx+108h]
0x140032c51  sub     rax, 4Ah ; 'J'
0x140032c55  mov     dword ptr [rbp+320h+var_2B0+0Ch], ecx
0x140032c58  cmp     rax, 3
0x140032c5c  ja      short loc_140032C91
0x140032c5e  movzx   eax, word ptr [rbx+2A8h]
0x140032c65  mov     dword ptr [rbp+320h+var_290], eax
0x140032c6b  mov     rax, [rbx+2B0h]
0x140032c72  mov     qword ptr [rbp+320h+var_290+8], rax
0x140032c79  mov     eax, [rbx+2B8h]
0x140032c7f  mov     dword ptr [rbp+320h+var_280], eax
0x140032c85  mov     eax, [rbx+2BCh]
0x140032c8b  mov     dword ptr [rbp+320h+var_280+4], eax
0x140032c91  lea     rax, [rbp+320h+var_2B0]
0x140032c95  jmp     short loc_140032CF5
0x140032c97  cmp     edi, 6
0x140032c9a  jnz     short loc_140032CF9
0x140032c9c  mov     rax, [rbx+118h]
0x140032ca3  mov     qword ptr [rbp+320h+var_1F0], rax
0x140032caa  movzx   eax, word ptr [rbx+108h]
0x140032cb1  mov     word ptr [rbp+320h+var_1F0+8], ax
0x140032cb8  mov     eax, [rbx+184h]
0x140032cbe  mov     dword ptr [rbp+320h+var_1E0], eax
0x140032cc4  mov     eax, [rbx+188h]
0x140032cca  mov     dword ptr [rbp+320h+var_1E0+4], eax
0x140032cd0  mov     eax, [rbx+18Ch]
0x140032cd6  mov     dword ptr [rbp+320h+var_1E0+8], eax
0x140032cdc  mov     eax, [rbx+190h]
0x140032ce2  mov     dword ptr [rbp+320h+var_1E0+0Ch], eax
0x140032ce8  lea     rax, [rbp+320h+var_1F0]
0x140032cef  mov     dword ptr [rbp+320h+var_1F0+0Ch], ecx
0x140032cf5  mov     [rbp+320h+var_310], rax
0x140032cf9  mov     rdx, [rbx+2D8h]
0x140032d00  movzx   eax, byte ptr [rbx+311h]
0x140032d07  mov     ecx, [rbp+320h+var_308]
0x140032d0a  mov     [rbp+320h+var_304], eax
0x140032d0d  test    rdx, rdx
0x140032d10  jz      short loc_140032D27
0x140032d12  mov     rax, [rbx+2D0h]
0x140032d19  or      ecx, 1
0x140032d1c  mov     [rbp+320h+var_308], ecx
0x140032d1f  mov     [rbp+320h+var_300], rax
0x140032d23  mov     [rbp+320h+var_2F8], rdx
0x140032d27  cmp     word ptr [rbx+328h], 0
0x140032d2f  jbe     short loc_140032D47
0x140032d31  mov     rax, [rbx+330h]
0x140032d38  test    rax, rax
0x140032d3b  jz      short loc_140032D47
0x140032d3d  or      ecx, 2
0x140032d40  mov     [rbp+320h+var_2E0], rax
0x140032d44  mov     [rbp+320h+var_308], ecx
0x140032d47  cmp     word ptr [rbx+2E0h], 0
0x140032d4f  mov     rax, [rbx+178h]
0x140032d56  mov     [rbp+320h+var_2D8], rax
0x140032d5a  jbe     short loc_140032D72
0x140032d5c  mov     rax, [rbx+2E8h]
0x140032d63  test    rax, rax
0x140032d66  jz      short loc_140032D72
0x140032d68  or      ecx, 4
0x140032d6b  mov     [rbp+320h+var_2D0], rax
0x140032d6f  mov     [rbp+320h+var_308], ecx
0x140032d72  cmp     word ptr [rbx+348h], 0
0x140032d7a  mov     rax, [rbx+340h]
  ... truncated ...
```
