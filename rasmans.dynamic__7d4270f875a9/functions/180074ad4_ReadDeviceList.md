# ReadDeviceList

- ea: `0x180074ad4`
- end: `0x18007650c`
- name: `ReadDeviceList`
- size: `6712`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180076948`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000c3c0`
- `0x18005fc8c`
- `0x1800711a4`
- `0x180074ad4`
- `0x18007c354`
- `0x18007c418`
- `0x18007ca10`
- `0x18007d27c`
- `0x180084144`
- `0x180093744`
- `0x180093854`
- `0x180094810`
- `0x1800e8e96`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180075098`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800750fd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007545e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180075e1c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180075098`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800750fd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007545e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180075e1c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075080`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800750de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075497`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800754c7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800754f7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075527`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075557`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075587`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800755b7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800755e7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075613`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007563f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075080`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800750de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075497`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800754c7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800754f7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075527`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075557`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075587`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800755b7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800755e7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180075613`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007563f`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180074c32`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180074e5b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180074ffc`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180075242`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180075278`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800752df`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18007544d`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180074c32`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180074e5b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180074ffc`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180075242`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180075278`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800752df`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18007544d`

## string_xrefs

- `0x180074db9`: `EnableCompression`
- `0x180074f3e`: `Protocol`
- `0x180074f5d`: `Compression`
- `0x180074fb5`: `MdmProtocol`

## pseudocode

```c
__int64 __fastcall ReadDeviceList(
        unsigned int a1,
        __int64 (__fastcall *a2)(CHAR *),
        int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        _DWORD *a7)
{
  int v7; // ebx
  int v11; // edx
  int v12; // r9d
  int v13; // r15d
  int v14; // r14d
  __int64 v15; // rax
  int v16; // edx
  int v17; // edx
  int v18; // r9d
  _BYTE *v19; // r11
  const char *v20; // rax
  int i; // ecx
  int v22; // edx
  int v23; // r8d
  int v24; // r9d
  unsigned int PhoneList; // eax
  unsigned int String; // ebx
  unsigned int Long; // eax
  unsigned int Flag; // eax
  unsigned int v29; // eax
  _DWORD *v30; // r14
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  struct _LIST_ENTRY *v35; // rcx
  __int64 v36; // rdx
  int v37; // edx
  int v38; // r8d
  int v39; // r9d
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  _DWORD *v47; // r9
  unsigned int v48; // eax
  unsigned int v49; // eax
  WCHAR *v50; // rbx
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  _WORD *v54; // rax
  int v55; // edx
  int v56; // r8d
  int v57; // r9d
  unsigned int v58; // eax
  unsigned int v59; // eax
  unsigned int v60; // eax
  unsigned int v61; // eax
  CHAR *v62; // r15
  __int64 v63; // rax
  const WCHAR *v64; // r14
  int v65; // ebx
  int v66; // r8d
  unsigned int v67; // eax
  unsigned int v68; // eax
  unsigned int v69; // eax
  unsigned int v70; // eax
  int Line; // eax
  WCHAR *v73; // rcx
  struct _LIST_ENTRY *v74; // rcx
  __int64 v75; // rdx
  struct _LIST_ENTRY *v76; // rcx
  __int64 v77; // rdx
  struct _LIST_ENTRY *v78; // rcx
  __int64 v79; // rdx
  int v81; // [rsp+44h] [rbp-BCh] BYREF
  int v82; // [rsp+48h] [rbp-B8h]
  int v83; // [rsp+4Ch] [rbp-B4h]
  int v84; // [rsp+50h] [rbp-B0h]
  int v85; // [rsp+54h] [rbp-ACh] BYREF
  PCNZWCH lpString2; // [rsp+58h] [rbp-A8h] BYREF
  CHAR String2[1552]; // [rsp+60h] [rbp-A0h] BYREF

  v7 = a3;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 347, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
  }
  memset_0(String2, 0, 0x602u);
  v13 = 0;
  v84 = 0;
  v14 = 0;
  v83 = 0;
  v82 = 0;
  while ( 2 )
  {
    LOBYTE(v12) = 3;
    LOBYTE(v11) = 2;
    Line = rasFindLine(a1, v11, 1, v12, 1);
    v16 = 0;
    if ( Line )
    {
      v15 = RasfileGetLine(a1, 0);
      if ( v15 )
      {
        if ( !(unsigned int)IsMediaLine(v15) )
        {
          v20 = "DEVICE=";
          for ( i = 0; i < 7; ++i )
          {
            if ( *v19 != *v20 )
              goto LABEL_379;
            if ( !*v19 )
              break;
            ++v19;
            ++v20;
          }
          if ( (unsigned int)RasfileGetKeyValueFields(a1, 0, 0, String2) )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 349, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, String2);
            }
            if ( CompareStringA(0x7Fu, 1u, "isdn", -1, String2, -1) == 2 )
            {
              *(_QWORD *)(a5 + 32) = a2(String2);
              *(_DWORD *)(a5 + 40) = 6;
              PhoneList = ReadPhoneList(a1, v22, v23, v24, (__int64)a2, v7, a5 + 168);
              String = PhoneList;
              if ( PhoneList )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control[1].Flink,
                    350,
                    &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
                    PhoneList);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 351;
                goto LABEL_183;
              }
              Long = ReadLong(a1, 2, "LastSelectedPhone", a5 + 176);
              String = Long;
              if ( Long )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 352, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, Long);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 353;
                goto LABEL_183;
              }
              Flag = ReadFlag(a1, 2, "PromoteAlternates", a5 + 180);
              String = Flag;
              if ( Flag )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 354, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, Flag);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 355;
                goto LABEL_183;
              }
              v29 = ReadFlag(a1, 2, "TryNextAlternateOnFail", a5 + 184);
              String = v29;
              if ( v29 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 356, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v29);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 357;
                goto LABEL_183;
              }
              v30 = (_DWORD *)(a5 + 132);
              String = ReadLong(a1, 2, "LineType", a5 + 132);
              if ( String )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 358, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, String);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 359;
                goto LABEL_183;
              }
              if ( *v30 > 2u )
                *v30 = 0;
              v31 = ReadFlag(a1, 2, "Fallback", a5 + 136);
              String = v31;
              if ( v31 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 360, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v31);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 361;
                goto LABEL_183;
              }
              *(_DWORD *)(a5 + 128) = 1;
              v32 = ReadFlag(a1, 2, "Proprietary", a5 + 128);
              String = v32;
              if ( v32 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 362, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v32);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 363;
                goto LABEL_183;
              }
              v81 = -1;
              v33 = ReadLong(a1, 2, "ChannelAggregation", &v81);
              String = v33;
              if ( v33 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 364, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v33);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 365;
                goto LABEL_183;
              }
              if ( v81 == -1 )
                *(_DWORD *)(a5 + 128) = 0;
              else
                *(_DWORD *)(a5 + 144) = v81;
              v34 = ReadFlag(a1, 2, "EnableCompression", a5 + 140);
              String = v34;
              if ( v34 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 366, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v34);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 367;
LABEL_183:
                WPP_SF_d(v35[1].Flink, v36, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, String);
                return String;
              }
LABEL_115:
              v14 = v83;
              goto LABEL_116;
            }
            if ( CompareStringA(0x7Fu, 1u, "modem", -1, String2, -1) == 2 )
            {
              *(_QWORD *)(a5 + 32) = a2(String2);
              *(_DWORD *)(a5 + 40) = 3;
              v40 = ReadPhoneList(a1, v37, v38, v39, (__int64)a2, v7, a5 + 168);
              String = v40;
              if ( v40 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 368, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v40);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 369;
                goto LABEL_183;
              }
              v41 = ReadLong(a1, 2, "LastSelectedPhone", a5 + 176);
              String = v41;
              if ( v41 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 370, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v41);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 371;
                goto LABEL_183;
              }
              v42 = ReadFlag(a1, 2, "PromoteAlternates", a5 + 180);
              String = v42;
              if ( v42 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 372, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v42);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 373;
                goto LABEL_183;
              }
              v43 = ReadFlag(a1, 2, "TryNextAlternateOnFail", a5 + 184);
              String = v43;
              if ( v43 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 374, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v43);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 375;
                goto LABEL_183;
              }
              v44 = ReadFlag(a1, 2, "HwFlowControl", a5 + 108);
              String = v44;
              if ( v44 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 376, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v44);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 377;
                goto LABEL_183;
              }
              v45 = ReadFlag(a1, 2, "Protocol", a5 + 112);
              String = v45;
              if ( v45 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 378, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v45);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 379;
                goto LABEL_183;
              }
              v46 = ReadFlag(a1, 2, "Compression", a5 + 116);
              String = v46;
              if ( v46 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 380, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v46);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 381;
                goto LABEL_183;
              }
              v47 = (_DWORD *)(a5 + 120);
              if ( a7 )
              {
                *v47 = *a7 == 0;
              }
              else
              {
                v48 = ReadFlag(a1, 2, "Speaker", v47);
                String = v48;
                if ( v48 )
                {
                  v35 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                    return String;
                  if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 382, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v48);
                    v35 = WPP_GLOBAL_Control;
                  }
                  if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    || SBYTE4(v35[1].Blink) >= 0
                    || BYTE1(v35[1].Blink) < 6u )
                  {
                    return String;
                  }
                  v36 = 383;
                  goto LABEL_183;
                }
              }
              v49 = ReadLong(a1, 2, "MdmProtocol", a5 + 124);
              String = v49;
              if ( v49 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 384, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v49);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 385;
                goto LABEL_183;
              }
              v14 = 1;
              v83 = 1;
              goto LABEL_116;
            }
            if ( CompareStringA(0x7Fu, 1u, "switch", -1, String2, -1) == 2 )
            {
              lpString2 = 0;
              String = ReadString(a1, (_DWORD)a2, 2, (unsigned int)"Type", (__int64)&lpString2);
              if ( String )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 386, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, String);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 387;
                goto LABEL_183;
              }
              v50 = (WCHAR *)lpString2;
              if ( lpString2 )
              {
                if ( !v13 && !v14 )
                {
                  v13 = 1;
                  if ( CompareStringW(0x7Fu, 1u, L"Terminal", -1, lpString2, -1) == 2 )
                  {
                    *(_DWORD *)(a5 + 88) = 1;
                    GlobalFree(v50);
                  }
                  else
                  {
                    *(_DWORD *)(a5 + 92) = 1;
                    *(_QWORD *)(a5 + 96) = v50;
                  }
                  goto LABEL_61;
                }
                if ( !v82 )
                {
                  if ( CompareStringW(0x7Fu, 1u, L"Terminal", -1, lpString2, -1) == 2 )
                  {
                    *(_DWORD *)(a4 + 212) = 1;
                    GlobalFree(v50);
                  }
                  else
                  {
                    *(_DWORD *)(a4 + 216) = 1;
                    *(_QWORD *)(a4 + 224) = v50;
                  }
                  goto LABEL_66;
                }
                v73 = (WCHAR *)lpString2;
                *(_DWORD *)(a4 + 536) = 1;
                GlobalFree(v73);
                v74 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
                  || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
                {
                  return 0;
                }
                v75 = 388;
              }
              else
              {
                v85 = 0;
                v81 = 0;
                lpString2 = 0;
                v51 = ReadFlag(a1, 2, "Terminal", &v85);
                String = v51;
                if ( v51 )
                {
                  v35 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                    return String;
                  if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 389, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v51);
                    v35 = WPP_GLOBAL_Control;
                  }
                  if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    || SBYTE4(v35[1].Blink) >= 0
                    || BYTE1(v35[1].Blink) < 6u )
                  {
                    return String;
                  }
                  v36 = 390;
                  goto LABEL_183;
                }
                v52 = ReadFlag(a1, 2, "Script", &v81);
                String = v52;
                if ( v52 )
                {
                  v35 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                    return String;
                  if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 391, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v52);
                    v35 = WPP_GLOBAL_Control;
                  }
                  if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    || SBYTE4(v35[1].Blink) >= 0
                    || BYTE1(v35[1].Blink) < 6u )
                  {
                    return String;
                  }
                  v36 = 392;
                  goto LABEL_183;
                }
                v53 = ReadLong(a1, 2, "CustomScript", a4 + 232);
                String = v53;
                if ( v53 )
                {
                  v35 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                    return String;
                  if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 393, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v53);
                    v35 = WPP_GLOBAL_Control;
                  }
                  if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    || SBYTE4(v35[1].Blink) >= 0
                    || BYTE1(v35[1].Blink) < 6u )
                  {
                    return String;
                  }
                  v36 = 394;
                  goto LABEL_183;
                }
                String = ReadString(a1, (_DWORD)a2, 2, (unsigned int)"Name", (__int64)&lpString2);
                if ( String )
                {
                  v35 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                    return String;
                  if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 395, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, String);
                    v35 = WPP_GLOBAL_Control;
                  }
                  if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    || SBYTE4(v35[1].Blink) >= 0
                    || BYTE1(v35[1].Blink) < 6u )
                  {
                    return String;
                  }
                  v36 = 396;
                  goto LABEL_183;
                }
                if ( !v13 && !v14 )
                {
                  v13 = 1;
                  *(_DWORD *)(a5 + 88) = v85;
                  *(_DWORD *)(a5 + 92) = v81;
                  *(_QWORD *)(a5 + 96) = lpString2;
LABEL_61:
                  v84 = 1;
                  goto LABEL_116;
                }
                if ( !v82 )
                {
                  *(_DWORD *)(a4 + 212) = v85;
                  *(_DWORD *)(a4 + 216) = v81;
                  *(_QWORD *)(a4 + 224) = lpString2;
LABEL_66:
                  v82 = 1;
                  goto LABEL_116;
                }
                *(_DWORD *)(a4 + 536) = 1;
                v74 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
                  || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
                {
                  return 0;
                }
                v75 = 397;
              }
              goto LABEL_391;
            }
            if ( CompareStringA(0x7Fu, 1u, "pad", -1, String2, -1) == 2 )
              continue;
            if ( CompareStringA(0x7Fu, 1u, "null", -1, String2, -1) == 2 )
            {
              *(_QWORD *)(a5 + 32) = a2(String2);
              *(_DWORD *)(a5 + 40) = 1;
              continue;
            }
            v54 = *(_WORD **)(a5 + 16);
            if ( v54 && !*v54 && CompareStringA(0x7Fu, 1u, "ATM", -1, String2, -1) == 2 )
            {
              *(_QWORD *)(a5 + 32) = a2(String2);
              *(_DWORD *)(a5 + 40) = 13;
              v58 = ReadPhoneList(a1, v55, v56, v57, (__int64)a2, v7, a5 + 168);
              String = v58;
              if ( v58 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 398, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v58);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 399;
                goto LABEL_183;
              }
              v59 = ReadLong(a1, 2, "LastSelectedPhone", a5 + 176);
              String = v59;
              if ( v59 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 400, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v59);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 401;
                goto LABEL_183;
              }
              v60 = ReadFlag(a1, 2, "PromoteAlternates", a5 + 180);
              String = v60;
              if ( v60 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 402, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v60);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 403;
                goto LABEL_183;
              }
              v61 = ReadFlag(a1, 2, "TryNextAlternateOnFail", a5 + 184);
              String = v61;
              if ( v61 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                  return String;
                if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 404, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v61);
                  v35 = WPP_GLOBAL_Control;
                }
                if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  || SBYTE4(v35[1].Blink) >= 0
                  || BYTE1(v35[1].Blink) < 6u )
                {
                  return String;
                }
                v36 = 405;
                goto LABEL_183;
              }
LABEL_116:
              v7 = a3;
              continue;
            }
            v62 = (CHAR *)StrDupAFromTInternal(*(LPCWCH *)(a5 + 24));
            if ( v62 )
            {
              v63 = a2(String2);
              *(_QWORD *)(a5 + 32) = v63;
              v64 = (const WCHAR *)v63;
              if ( v63 )
              {
                v65 = CompareStringA(0x7Fu, 1u, String2, -1, v62, -1);
                GlobalFree(v62);
                if ( v65 == 2
                  || CompareStringW(0x7Fu, 1u, L"SERIAL", -1, v64, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"vpn", -1, v64, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"GENERIC", -1, v64, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"FRAMERELAY", -1, v64, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"ATM", -1, v64, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"SONET", -1, v64, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"SW56", -1, v64, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"IRDA", -1, v64, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"PARALLEL", -1, v64, -1) == 2
                  || CompareStringW(0x7Fu, 1u, L"PPPoE", -1, v64, -1) == 2 )
                {
                  if ( !*(_DWORD *)(a5 + 40) )
                    *(_DWORD *)(a5 + 40) = PbdevicetypeFromPszTypeA(String2);
                  v67 = ReadPhoneList(a1, v11, v66, v12, (__int64)a2, a3, a5 + 168);
                  String = v67;
                  if ( v67 )
                  {
                    v35 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                      return String;
                    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                    {
                      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 409, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v67);
                      v35 = WPP_GLOBAL_Control;
                    }
                    if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      || SBYTE4(v35[1].Blink) >= 0
                      || BYTE1(v35[1].Blink) < 6u )
                    {
                      return String;
                    }
                    v36 = 410;
                    goto LABEL_183;
                  }
                  v68 = ReadLong(a1, 2, "LastSelectedPhone", a5 + 176);
                  String = v68;
                  if ( v68 )
                  {
                    v35 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                      return String;
                    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                    {
                      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 411, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v68);
                      v35 = WPP_GLOBAL_Control;
                    }
                    if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      || SBYTE4(v35[1].Blink) >= 0
                      || BYTE1(v35[1].Blink) < 6u )
                    {
                      return String;
                    }
                    v36 = 412;
                    goto LABEL_183;
                  }
                  v69 = ReadFlag(a1, 2, "PromoteAlternates", a5 + 180);
                  String = v69;
                  if ( v69 )
                  {
                    v35 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                      return String;
                    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                    {
                      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 413, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v69);
                      v35 = WPP_GLOBAL_Control;
                    }
                    if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      || SBYTE4(v35[1].Blink) >= 0
                      || BYTE1(v35[1].Blink) < 6u )
                    {
                      return String;
                    }
                    v36 = 414;
                    goto LABEL_183;
                  }
                  v70 = ReadFlag(a1, 2, "TryNextAlternateOnFail", a5 + 184);
                  String = v70;
                  if ( v70 )
                  {
                    v35 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                      return String;
                    if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                    {
                      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 415, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v70);
                      v35 = WPP_GLOBAL_Control;
                    }
                    if ( v35 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      || SBYTE4(v35[1].Blink) >= 0
                      || BYTE1(v35[1].Blink) < 6u )
                    {
                      return String;
                    }
                    v36 = 416;
                    goto LABEL_183;
                  }
                }
                else
                {
                  *(_DWORD *)(a4 + 536) = 1;
                }
                v13 = v84;
                goto LABEL_115;
              }
              v76 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
                || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
              {
                return 8;
              }
              v77 = 408;
            }
            else
            {
              v76 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                return 8;
              if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 406, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 8);
                v76 = WPP_GLOBAL_Control;
              }
              if ( v76 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || SBYTE4(v76[1].Blink) >= 0
                || BYTE1(v76[1].Blink) < 6u )
              {
                return 8;
              }
              v77 = 407;
            }
            WPP_SF_d(v76[1].Flink, v77, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 8);
            return 8;
          }
          v78 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
          {
            return 625;
          }
          v79 = 348;
LABEL_385:
          WPP_SF_d(v78[1].Flink, v79, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 625);
          return 625;
        }
LABEL_379:
        LOBYTE(v18) = 4;
        LOBYTE(v17) = 63;
        rasFindLine(a1, v17, 1, v18, 2);
        v16 = 0;
      }
    }
    break;
  }
  if ( *(_DWORD *)(a5 + 40) == v16 )
  {
    v78 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
    {
      return 625;
    }
    v79 = 417;
    goto LABEL_385;
  }
  v74 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
    || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
  {
    return 0;
  }
  v75 = 418;
LABEL_391:
  WPP_SF_d(v74[1].Flink, v75, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180074ad4  push    rbp
0x180074ad6  push    rbx
0x180074ad7  push    rsi
0x180074ad8  push    rdi
0x180074ad9  push    r12
0x180074adb  push    r13
0x180074add  push    r14
0x180074adf  push    r15
0x180074ae1  lea     rbp, [rsp-588h]
0x180074ae9  sub     rsp, 688h
0x180074af0  mov     rax, cs:__security_cookie
0x180074af7  xor     rax, rsp
0x180074afa  mov     [rbp+5C0h+var_50], rax
0x180074b01  mov     rdi, [rbp+5C0h+arg_20]
0x180074b08  mov     ebx, r8d
0x180074b0b  mov     [rsp+6C0h+var_680], ebx
0x180074b0f  mov     r13, r9
0x180074b12  mov     r12, rdx
0x180074b15  mov     esi, ecx
0x180074b17  mov     rcx, cs:WPP_GLOBAL_Control
0x180074b1e  lea     rax, WPP_GLOBAL_Control
0x180074b25  cmp     rcx, rax
0x180074b28  jz      short loc_180074B4B
0x180074b2a  test    byte ptr [rcx+1Ch], 80h
0x180074b2e  jz      short loc_180074B4B
0x180074b30  cmp     byte ptr [rcx+19h], 6
0x180074b34  jb      short loc_180074B4B
0x180074b36  mov     rcx, [rcx+10h]
0x180074b3a  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180074b41  mov     edx, 15Bh
0x180074b46  call    WPP_SF_
0x180074b4b  xor     edx, edx; Val
0x180074b4d  lea     rcx, [rsp+6C0h+String2]; void *
0x180074b52  mov     r8d, 602h; Size
0x180074b58  call    memset_0
0x180074b5d  xor     eax, eax
0x180074b5f  mov     r15d, eax
0x180074b62  mov     [rsp+6C0h+var_670], eax
0x180074b66  mov     r14d, eax
0x180074b69  mov     [rsp+6C0h+var_674], eax
0x180074b6d  mov     [rsp+6C0h+var_678], eax
0x180074b71  jmp     loc_180075710
0x180074b76  mov     ecx, esi
0x180074b78  call    RasfileGetLine
0x180074b7d  mov     r11, rax
0x180074b80  test    rax, rax
0x180074b83  jz      loc_180076469
0x180074b89  mov     rcx, rax
0x180074b8c  call    IsMediaLine
0x180074b91  xor     r8d, r8d
0x180074b94  test    eax, eax
0x180074b96  jnz     loc_180076450
0x180074b9c  lea     rax, aDevice_0; "DEVICE="
0x180074ba3  mov     ecx, r8d
0x180074ba6  mov     dl, [r11]
0x180074ba9  cmp     dl, [rax]
0x180074bab  jnz     loc_180076450
0x180074bb1  test    dl, dl
0x180074bb3  jz      short loc_180074BC2
0x180074bb5  inc     r11
0x180074bb8  inc     rax
0x180074bbb  inc     ecx
0x180074bbd  cmp     ecx, 7
0x180074bc0  jl      short loc_180074BA6
0x180074bc2  lea     r9, [rsp+6C0h+String2]
0x180074bc7  xor     edx, edx
0x180074bc9  mov     ecx, esi
0x180074bcb  call    RasfileGetKeyValueFields
0x180074bd0  test    eax, eax
0x180074bd2  jz      loc_18007642A
0x180074bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180074bdf  lea     rax, WPP_GLOBAL_Control
0x180074be6  cmp     rcx, rax
0x180074be9  jz      short loc_180074C11
0x180074beb  test    byte ptr [rcx+1Ch], 80h
0x180074bef  jz      short loc_180074C11
0x180074bf1  cmp     byte ptr [rcx+19h], 5
0x180074bf5  jb      short loc_180074C11
0x180074bf7  mov     rcx, [rcx+10h]
0x180074bfb  lea     r9, [rsp+6C0h+String2]
0x180074c00  mov     edx, 15Dh
0x180074c05  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180074c0c  call    WPP_SF_s
0x180074c11  or      ecx, 0FFFFFFFFh
0x180074c14  lea     rax, [rsp+6C0h+String2]
0x180074c19  mov     [rsp+6C0h+cchCount2], ecx; cchCount2
0x180074c1d  lea     r8, aIsdn_0; "isdn"
0x180074c24  mov     r9d, ecx; cchCount1
0x180074c27  mov     [rsp+6C0h+lpString2], rax; lpString2
0x180074c2c  lea     edx, [rcx+2]; dwCmpFlags
0x180074c2f  lea     ecx, [rdx+7Eh]; Locale
0x180074c32  call    cs:__imp_CompareStringA
0x180074c39  nop     dword ptr [rax+rax+00h]
0x180074c3e  cmp     eax, 2
0x180074c41  jnz     loc_180074E3A
0x180074c47  lea     rcx, [rsp+6C0h+String2]
0x180074c4c  mov     rax, r12
0x180074c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c54  mov     [rdi+20h], rax
0x180074c58  mov     ecx, esi
0x180074c5a  lea     rax, [rdi+0A8h]
0x180074c61  mov     dword ptr [rdi+28h], 6
0x180074c68  mov     [rsp+6C0h+var_690], rax
0x180074c6d  mov     [rsp+6C0h+cchCount2], ebx
0x180074c71  mov     [rsp+6C0h+lpString2], r12
0x180074c76  call    ReadPhoneList
0x180074c7b  mov     ebx, eax
0x180074c7d  test    eax, eax
0x180074c7f  jnz     loc_180075A06
0x180074c85  lea     r14d, [rax+2]
0x180074c89  mov     ecx, esi
0x180074c8b  mov     edx, r14d
0x180074c8e  lea     r9, [rdi+0B0h]
0x180074c95  lea     r8, aLastselectedph; "LastSelectedPhone"
0x180074c9c  call    ReadLong
0x180074ca1  mov     ebx, eax
0x180074ca3  test    eax, eax
0x180074ca5  jnz     loc_1800759AC
0x180074cab  lea     r9, [rdi+0B4h]
0x180074cb2  mov     edx, r14d
0x180074cb5  lea     r8, aPromotealterna; "PromoteAlternates"
0x180074cbc  mov     ecx, esi
0x180074cbe  call    ReadFlag
0x180074cc3  mov     ebx, eax
0x180074cc5  test    eax, eax
0x180074cc7  jnz     loc_180075943
0x180074ccd  lea     r9, [rdi+0B8h]
0x180074cd4  mov     edx, r14d
0x180074cd7  lea     r8, aTrynextalterna; "TryNextAlternateOnFail"
0x180074cde  mov     ecx, esi
0x180074ce0  call    ReadFlag
0x180074ce5  mov     ebx, eax
0x180074ce7  test    eax, eax
0x180074ce9  jnz     loc_1800758DA
0x180074cef  lea     r14, [rdi+84h]
0x180074cf6  mov     ecx, esi
0x180074cf8  mov     r9, r14
0x180074cfb  lea     r8, aLinetype; "LineType"
0x180074d02  lea     edx, [rax+2]
0x180074d05  call    ReadLong
0x180074d0a  mov     ebx, eax
0x180074d0c  xor     eax, eax
0x180074d0e  test    ebx, ebx
0x180074d10  jnz     loc_180075871
0x180074d16  cmp     dword ptr [r14], 2
0x180074d1a  jbe     short loc_180074D1F
0x180074d1c  mov     [r14], eax
0x180074d1f  lea     r9, [rdi+88h]
0x180074d26  mov     edx, 2
0x180074d2b  lea     r8, aFallback; "Fallback"
0x180074d32  mov     ecx, esi
0x180074d34  call    ReadFlag
0x180074d39  mov     ebx, eax
0x180074d3b  test    eax, eax
0x180074d3d  jnz     loc_180075808
0x180074d43  lea     r14, [rdi+80h]
0x180074d4a  mov     ecx, esi
0x180074d4c  mov     r9, r14
0x180074d4f  mov     dword ptr [r14], 1
0x180074d56  lea     r8, aProprietary; "Proprietary"
0x180074d5d  lea     edx, [rax+2]
0x180074d60  call    ReadFlag
0x180074d65  mov     ebx, eax
0x180074d67  test    eax, eax
0x180074d69  jnz     loc_18007579F
0x180074d6f  lea     r9, [rsp+6C0h+var_67C]
0x180074d74  mov     [rsp+6C0h+var_67C], 0FFFFFFFFh
0x180074d7c  lea     r8, aChannelaggrega; "ChannelAggregation"
0x180074d83  mov     ecx, esi
0x180074d85  lea     edx, [rax+2]
0x180074d88  call    ReadLong
0x180074d8d  xor     ecx, ecx
0x180074d8f  mov     ebx, eax
0x180074d91  test    eax, eax
0x180074d93  jnz     loc_180075736
0x180074d99  mov     eax, [rsp+6C0h+var_67C]
0x180074d9d  cmp     eax, 0FFFFFFFFh
0x180074da0  jnz     short loc_180074DA7
0x180074da2  mov     [r14], ecx
0x180074da5  jmp     short loc_180074DAD
0x180074da7  mov     [rdi+90h], eax
0x180074dad  lea     r9, [rdi+8Ch]
0x180074db4  mov     edx, 2
0x180074db9  lea     r8, aEnablecompress; "EnableCompression"
0x180074dc0  mov     ecx, esi
0x180074dc2  call    ReadFlag
0x180074dc7  mov     ebx, eax
0x180074dc9  test    eax, eax
0x180074dcb  jz      loc_180075707
0x180074dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180074dd8  lea     rdi, WPP_GLOBAL_Control
0x180074ddf  cmp     rcx, rdi
0x180074de2  jz      loc_180075A6D
0x180074de8  test    byte ptr [rcx+1Ch], 80h
0x180074dec  jz      short loc_180074E13
0x180074dee  cmp     byte ptr [rcx+19h], 2
0x180074df2  jb      short loc_180074E13
0x180074df4  mov     rcx, [rcx+10h]
0x180074df8  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180074dff  mov     edx, 16Eh
0x180074e04  mov     r9d, eax
0x180074e07  call    WPP_SF_d
0x180074e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180074e13  cmp     rcx, rdi
0x180074e16  jz      loc_180075A6D
0x180074e1c  test    byte ptr [rcx+1Ch], 80h
0x180074e20  jz      loc_180075A6D
0x180074e26  cmp     byte ptr [rcx+19h], 6
0x180074e2a  jb      loc_180075A6D
0x180074e30  mov     edx, 16Fh
0x180074e35  jmp     loc_180075A5A
0x180074e3a  or      ecx, 0FFFFFFFFh
0x180074e3d  lea     rax, [rsp+6C0h+String2]
0x180074e42  mov     [rsp+6C0h+cchCount2], ecx; cchCount2
0x180074e46  lea     r8, aModem_0; "modem"
0x180074e4d  mov     r9d, ecx; cchCount1
0x180074e50  mov     [rsp+6C0h+lpString2], rax; lpString2
0x180074e55  lea     edx, [rcx+2]; dwCmpFlags
0x180074e58  lea     ecx, [rdx+7Eh]; Locale
0x180074e5b  call    cs:__imp_CompareStringA
0x180074e62  nop     dword ptr [rax+rax+00h]
0x180074e67  cmp     eax, 2
0x180074e6a  jnz     loc_180074FDB
0x180074e70  lea     rcx, [rsp+6C0h+String2]
0x180074e75  mov     rax, r12
0x180074e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074e7d  mov     [rdi+20h], rax
0x180074e81  mov     ecx, esi
0x180074e83  lea     rax, [rdi+0A8h]
0x180074e8a  mov     dword ptr [rdi+28h], 3
0x180074e91  mov     [rsp+6C0h+var_690], rax
0x180074e96  mov     [rsp+6C0h+cchCount2], ebx
0x180074e9a  mov     [rsp+6C0h+lpString2], r12
0x180074e9f  call    ReadPhoneList
0x180074ea4  mov     ebx, eax
0x180074ea6  test    eax, eax
0x180074ea8  jnz     loc_180075DA5
0x180074eae  lea     r14d, [rax+2]
0x180074eb2  mov     ecx, esi
0x180074eb4  mov     edx, r14d
0x180074eb7  lea     r9, [rdi+0B0h]
0x180074ebe  lea     r8, aLastselectedph; "LastSelectedPhone"
0x180074ec5  call    ReadLong
0x180074eca  mov     ebx, eax
0x180074ecc  test    eax, eax
0x180074ece  jnz     loc_180075D3C
0x180074ed4  lea     r9, [rdi+0B4h]
0x180074edb  mov     edx, r14d
0x180074ede  lea     r8, aPromotealterna; "PromoteAlternates"
0x180074ee5  mov     ecx, esi
0x180074ee7  call    ReadFlag
0x180074eec  mov     ebx, eax
0x180074eee  test    eax, eax
0x180074ef0  jnz     loc_180075CD3
0x180074ef6  lea     r9, [rdi+0B8h]
0x180074efd  mov     edx, r14d
0x180074f00  lea     r8, aTrynextalterna; "TryNextAlternateOnFail"
0x180074f07  mov     ecx, esi
0x180074f09  call    ReadFlag
0x180074f0e  mov     ebx, eax
0x180074f10  test    eax, eax
0x180074f12  jnz     loc_180075C6A
0x180074f18  lea     r9, [rdi+6Ch]
0x180074f1c  mov     edx, r14d
0x180074f1f  lea     r8, aHwflowcontrol; "HwFlowControl"
0x180074f26  mov     ecx, esi
0x180074f28  call    ReadFlag
0x180074f2d  mov     ebx, eax
0x180074f2f  test    eax, eax
0x180074f31  jnz     loc_180075C01
0x180074f37  lea     r9, [rdi+70h]
0x180074f3b  mov     edx, r14d
0x180074f3e  lea     r8, aProtocol; "Protocol"
0x180074f45  mov     ecx, esi
0x180074f47  call    ReadFlag
0x180074f4c  mov     ebx, eax
0x180074f4e  test    eax, eax
0x180074f50  jnz     loc_180075B98
0x180074f56  lea     r9, [rdi+74h]
0x180074f5a  mov     edx, r14d
0x180074f5d  lea     r8, aCompression; "Compression"
0x180074f64  mov     ecx, esi
0x180074f66  call    ReadFlag
0x180074f6b  xor     edx, edx
0x180074f6d  mov     ebx, eax
0x180074f6f  test    eax, eax
0x180074f71  jnz     loc_180075B2F
0x180074f77  mov     rcx, [rbp+5C0h+arg_30]
0x180074f7e  lea     r9, [rdi+78h]
0x180074f82  test    rcx, rcx
0x180074f85  jz      short loc_180074F93
0x180074f87  cmp     [rcx], edx
0x180074f89  mov     eax, edx
0x180074f8b  setz    al
0x180074f8e  mov     [r9], eax
0x180074f91  jmp     short loc_180074FAE
0x180074f93  lea     r8, aSpeaker; "Speaker"
0x180074f9a  mov     edx, r14d
0x180074f9d  mov     ecx, esi
0x180074f9f  call    ReadFlag
  ... truncated ...
```
