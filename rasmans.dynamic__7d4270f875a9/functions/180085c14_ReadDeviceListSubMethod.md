# ReadDeviceListSubMethod

- ea: `0x180085c14`
- end: `0x1800876b0`
- name: `ReadDeviceListSubMethod`
- size: `6812`
- prototype: `__int64 __usercall@<rax>(HKEY hkey@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18008d0ec`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000c3c0`
- `0x18005fc8c`
- `0x180084144`
- `0x180085c14`
- `0x18008c988`
- `0x18008ca30`
- `0x18008d214`
- `0x18008d2bc`
- `0x18008d698`
- `0x18008db70`
- `0x1800e8e96`
- `0x1800e8eae`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008623d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008629d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800865b9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180086faf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008623d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008629d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800865b9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180086faf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086226`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086283`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800865ee`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008661a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086646`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086672`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008669e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800866ca`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800866f6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086722`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008674a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086772`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086226`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086283`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800865ee`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008661a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086646`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086672`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008669e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800866ca`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800866f6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086722`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008674a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180086772`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180085db5`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180085f99`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800861af`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800863e1`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180086419`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180086481`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800865a8`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180085db5`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180085f99`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800861af`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800863e1`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180086419`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180086481`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800865a8`

## string_xrefs

- `0x180085f53`: `EnableCompression`
- `0x180086092`: `Protocol`
- `0x1800860b3`: `Compression`
- `0x18008610f`: `MdmProtocol`

## pseudocode

```c
__int64 __fastcall ReadDeviceListSubMethod(
        HKEY hkey,
        __int64 (__fastcall *a2)(char *),
        int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        _DWORD *a7)
{
  __int64 v7; // r13
  __int64 (__fastcall *v8)(char *); // rbx
  int v11; // r12d
  DWORD v12; // eax
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  unsigned int PhoneList; // eax
  unsigned int String; // ebx
  unsigned int Long; // eax
  unsigned int Flag; // eax
  unsigned int v20; // eax
  _DWORD *v21; // r12
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // edx
  int v27; // r8d
  int v28; // r9d
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  _DWORD *v36; // r8
  unsigned int v37; // eax
  unsigned int v38; // eax
  struct _LIST_ENTRY *v39; // rcx
  __int64 v40; // rdx
  WCHAR *v41; // rbx
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  _WORD *v46; // rax
  int v47; // edx
  int v48; // r8d
  int v49; // r9d
  unsigned int v50; // eax
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  CHAR *v54; // r13
  __int64 v55; // rax
  const WCHAR *v56; // r12
  int v57; // ebx
  int v58; // edx
  int v59; // r8d
  int v60; // r9d
  unsigned int v61; // eax
  unsigned int v62; // eax
  unsigned int v63; // eax
  unsigned int v64; // eax
  WCHAR *v65; // rcx
  struct _LIST_ENTRY *v66; // rcx
  __int64 v67; // rdx
  struct _LIST_ENTRY *v68; // rcx
  __int64 v69; // rdx
  int lpString2; // [rsp+20h] [rbp-E0h]
  int lpString2a; // [rsp+20h] [rbp-E0h]
  int lpString2b; // [rsp+20h] [rbp-E0h]
  int v73; // [rsp+40h] [rbp-C0h] BYREF
  int v74; // [rsp+44h] [rbp-BCh]
  int v75; // [rsp+48h] [rbp-B8h]
  int v76; // [rsp+4Ch] [rbp-B4h]
  int v77; // [rsp+50h] [rbp-B0h]
  __int64 (__fastcall *v78)(char *); // [rsp+58h] [rbp-A8h]
  int v79; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  PCNZWCH v81; // [rsp+68h] [rbp-98h]
  DWORD i; // [rsp+70h] [rbp-90h]
  __int64 v83; // [rsp+78h] [rbp-88h]
  char Destination[1552]; // [rsp+80h] [rbp-80h] BYREF
  char Source[1552]; // [rsp+690h] [rbp+590h] BYREF

  v7 = a4;
  v83 = a4;
  v8 = a2;
  v76 = a3;
  v78 = a2;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 282, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids);
  }
  memset_0(Source, 0, 0x602u);
  cSubKeys = 0;
  if ( (unsigned int)RegGetNumberOfSubkeys(hkey, &cSubKeys) )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 283, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, 1);
    }
    return 1;
  }
  v11 = 0;
  v74 = 0;
  v12 = 0;
  v77 = 0;
  v75 = 0;
  for ( i = 0; v12 < cSubKeys; i = v12 )
  {
    if ( !(unsigned int)RegGetIthSectionName(hkey, v12, Source) )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 284, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids);
      }
      return 635;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 285, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, Source);
    }
    strncpy_0(Destination, Source, 0x601u);
    if ( CompareStringA(0x7Fu, 1u, "isdn", -1, Source, -1) == 2 )
    {
      *(_QWORD *)(a5 + 32) = v8(Source);
      lpString2 = v76;
      *(_DWORD *)(a5 + 40) = 6;
      PhoneList = RegReadPhoneList((_DWORD)hkey, v13, v14, v15, lpString2, a5 + 168, (__int64)Destination);
      String = PhoneList;
      if ( PhoneList )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 286, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, PhoneList);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 287;
            goto LABEL_180;
          }
        }
        return String;
      }
      Long = RegReadLong(hkey, "LastSelectedPhone");
      String = Long;
      if ( Long )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 288, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, Long);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 289;
            goto LABEL_180;
          }
        }
        return String;
      }
      Flag = RegReadFlag(hkey, "PromoteAlternates", a5 + 180, Destination);
      String = Flag;
      if ( Flag )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 290, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, Flag);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 291;
            goto LABEL_180;
          }
        }
        return String;
      }
      v20 = RegReadFlag(hkey, "TryNextAlternateOnFail", a5 + 184, Destination);
      String = v20;
      if ( v20 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 292, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v20);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 293;
            goto LABEL_180;
          }
        }
        return String;
      }
      v21 = (_DWORD *)(a5 + 132);
      String = RegReadLong(hkey, "LineType");
      if ( String )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 294, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, String);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 295;
            goto LABEL_180;
          }
        }
        return String;
      }
      if ( *v21 > 2u )
        *v21 = 0;
      v22 = RegReadFlag(hkey, "Fallback", a5 + 136, Destination);
      String = v22;
      if ( v22 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 296, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v22);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 297;
            goto LABEL_180;
          }
        }
        return String;
      }
      *(_DWORD *)(a5 + 128) = 1;
      v23 = RegReadFlag(hkey, "Proprietary", a5 + 128, Destination);
      String = v23;
      if ( v23 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 298, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v23);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 299;
            goto LABEL_180;
          }
        }
        return String;
      }
      v73 = -1;
      v24 = RegReadLong(hkey, "ChannelAggregation");
      String = v24;
      if ( v24 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 300, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v24);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 301;
            goto LABEL_180;
          }
        }
        return String;
      }
      if ( v73 == -1 )
        *(_DWORD *)(a5 + 128) = 0;
      else
        *(_DWORD *)(a5 + 144) = v73;
      v25 = RegReadFlag(hkey, "EnableCompression", a5 + 140, Destination);
      String = v25;
      if ( v25 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 302, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v25);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 303;
            goto LABEL_180;
          }
        }
        return String;
      }
      goto LABEL_32;
    }
    if ( CompareStringA(0x7Fu, 1u, "modem", -1, Source, -1) == 2 )
    {
      *(_QWORD *)(a5 + 32) = v8(Source);
      lpString2a = v76;
      *(_DWORD *)(a5 + 40) = 3;
      v29 = RegReadPhoneList((_DWORD)hkey, v26, v27, v28, lpString2a, a5 + 168, (__int64)Destination);
      String = v29;
      if ( v29 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 304, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v29);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 305;
            goto LABEL_180;
          }
        }
        return String;
      }
      v30 = RegReadLong(hkey, "LastSelectedPhone");
      String = v30;
      if ( v30 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 306, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v30);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 307;
            goto LABEL_180;
          }
        }
        return String;
      }
      v31 = RegReadFlag(hkey, "PromoteAlternates", a5 + 180, Destination);
      String = v31;
      if ( v31 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 308, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v31);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 309;
            goto LABEL_180;
          }
        }
        return String;
      }
      v32 = RegReadFlag(hkey, "TryNextAlternateOnFail", a5 + 184, Destination);
      String = v32;
      if ( v32 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 310, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v32);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 311;
            goto LABEL_180;
          }
        }
        return String;
      }
      v33 = RegReadFlag(hkey, "HwFlowControl", a5 + 108, Destination);
      String = v33;
      if ( v33 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 312, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v33);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 313;
            goto LABEL_180;
          }
        }
        return String;
      }
      v34 = RegReadFlag(hkey, "Protocol", a5 + 112, Destination);
      String = v34;
      if ( v34 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 314, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v34);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 315;
            goto LABEL_180;
          }
        }
        return String;
      }
      v35 = RegReadFlag(hkey, "Compression", a5 + 116, Destination);
      String = v35;
      if ( v35 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 316, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v35);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 317;
            goto LABEL_180;
          }
        }
        return String;
      }
      v36 = (_DWORD *)(a5 + 120);
      if ( a7 )
      {
        *v36 = *a7 == 0;
      }
      else
      {
        v37 = RegReadFlag(hkey, "Speaker", v36, Destination);
        String = v37;
        if ( v37 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 318, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v37);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 319;
              goto LABEL_180;
            }
          }
          return String;
        }
      }
      v38 = RegReadLong(hkey, "MdmProtocol");
      String = v38;
      if ( v38 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 320, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v38);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 321;
            goto LABEL_180;
          }
        }
        return String;
      }
      v11 = 1;
      v77 = 1;
    }
    else if ( CompareStringA(0x7Fu, 1u, "switch", -1, Source, -1) == 2 )
    {
      v81 = 0;
      String = RegReadString(hkey, "Type");
      if ( String )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 322, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, String);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 323;
            goto LABEL_180;
          }
        }
        return String;
      }
      v41 = (WCHAR *)v81;
      if ( !v81 )
      {
        v79 = 0;
        v73 = 0;
        v81 = 0;
        v42 = RegReadFlag(hkey, "Terminal", &v79, Destination);
        String = v42;
        if ( v42 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 325, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v42);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 326;
              goto LABEL_180;
            }
          }
          return String;
        }
        v43 = RegReadFlag(hkey, "Script", &v73, Destination);
        String = v43;
        if ( v43 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 327, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v43);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 328;
              goto LABEL_180;
            }
          }
          return String;
        }
        v44 = RegReadLong(hkey, "CustomScript");
        String = v44;
        if ( v44 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 329, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v44);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 330;
              goto LABEL_180;
            }
          }
          return String;
        }
        v45 = RegReadString(hkey, "Name");
        String = v45;
        if ( v45 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 331, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v45);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 332;
              goto LABEL_180;
            }
          }
          return String;
        }
        if ( v74 || v11 )
        {
          if ( v75 )
          {
            *(_DWORD *)(v7 + 536) = 1;
            v66 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
            {
              v67 = 333;
              goto LABEL_389;
            }
            return 0;
          }
          *(_DWORD *)(v7 + 212) = v79;
          *(_DWORD *)(v7 + 216) = v73;
          *(_QWORD *)(v7 + 224) = v81;
          v75 = 1;
        }
        else
        {
          *(_DWORD *)(a5 + 88) = v79;
          *(_DWORD *)(a5 + 92) = v73;
          *(_QWORD *)(a5 + 96) = v81;
          v74 = 1;
        }
        goto LABEL_86;
      }
      if ( v74 || v11 )
      {
        if ( v75 )
        {
          v65 = (WCHAR *)v81;
          *(_DWORD *)(v7 + 536) = 1;
          GlobalFree(v65);
          v66 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
          {
            v67 = 324;
            goto LABEL_389;
          }
          return 0;
        }
        if ( CompareStringW(0x7Fu, 1u, L"Terminal", -1, v81, -1) == 2 )
        {
          *(_DWORD *)(v7 + 212) = 1;
          GlobalFree(v41);
        }
        else
        {
          *(_DWORD *)(v7 + 216) = 1;
          *(_QWORD *)(v7 + 224) = v41;
        }
        v75 = 1;
      }
      else
      {
        if ( CompareStringW(0x7Fu, 1u, L"Terminal", -1, v81, -1) == 2 )
        {
          *(_DWORD *)(a5 + 88) = 1;
          GlobalFree(v41);
        }
        else
        {
          *(_DWORD *)(a5 + 92) = 1;
          *(_QWORD *)(a5 + 96) = v41;
        }
        v74 = 1;
      }
    }
    else
    {
      if ( CompareStringA(0x7Fu, 1u, "pad", -1, Source, -1) == 2 )
        goto LABEL_47;
      if ( CompareStringA(0x7Fu, 1u, "null", -1, Source, -1) == 2 )
      {
        *(_QWORD *)(a5 + 32) = v8(Source);
        *(_DWORD *)(a5 + 40) = 1;
        goto LABEL_47;
      }
      v46 = *(_WORD **)(a5 + 16);
      if ( v46 && !*v46 && CompareStringA(0x7Fu, 1u, "ATM", -1, Source, -1) == 2 )
      {
        *(_QWORD *)(a5 + 32) = v8(Source);
        lpString2b = v76;
        *(_DWORD *)(a5 + 40) = 13;
        v50 = RegReadPhoneList((_DWORD)hkey, v47, v48, v49, lpString2b, a5 + 168, (__int64)Destination);
        String = v50;
        if ( v50 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 334, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v50);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 335;
              goto LABEL_180;
            }
          }
          return String;
        }
        v51 = RegReadLong(hkey, "LastSelectedPhone");
        String = v51;
        if ( v51 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 336, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v51);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 337;
              goto LABEL_180;
            }
          }
          return String;
        }
        v52 = RegReadFlag(hkey, "PromoteAlternates", a5 + 180, Destination);
        String = v52;
        if ( v52 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 338, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v52);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 339;
              goto LABEL_180;
            }
          }
          return String;
        }
        v53 = RegReadFlag(hkey, "TryNextAlternateOnFail", a5 + 184, Destination);
        String = v53;
        if ( v53 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 340, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v53);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 341;
              goto LABEL_180;
            }
          }
          return String;
        }
        goto LABEL_86;
      }
      v54 = (CHAR *)StrDupAFromTInternal(*(LPCWCH *)(a5 + 24));
      if ( !v54 )
      {
        v68 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 342, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, 8);
            v68 = WPP_GLOBAL_Control;
          }
          if ( v68 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v68[1].Blink) < 0 && BYTE1(v68[1].Blink) >= 6u )
          {
            v69 = 343;
LABEL_378:
            WPP_SF_d(v68[1].Flink, v69, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, 8);
          }
        }
        return 8;
      }
      v55 = v8(Source);
      *(_QWORD *)(a5 + 32) = v55;
      v56 = (const WCHAR *)v55;
      if ( !v55 )
      {
        v68 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
        {
          v69 = 344;
          goto LABEL_378;
        }
        return 8;
      }
      v57 = CompareStringA(0x7Fu, 1u, Source, -1, v54, -1);
      GlobalFree(v54);
      if ( v57 == 2
        || CompareStringW(0x7Fu, 1u, L"SERIAL", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"vpn", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"GENERIC", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"FRAMERELAY", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"ATM", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"SONET", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"SW56", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"IRDA", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"PARALLEL", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"PPPoE", -1, v56, -1) == 2 )
      {
        if ( !*(_DWORD *)(a5 + 40) )
          *(_DWORD *)(a5 + 40) = PbdevicetypeFromPszTypeA(Source);
        v61 = RegReadPhoneList((_DWORD)hkey, v58, v59, v60, v76, a5 + 168, (__int64)Source);
        String = v61;
        if ( v61 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 345, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v61);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 346;
              goto LABEL_180;
            }
          }
          return String;
        }
        v62 = RegReadLong(hkey, "LastSelectedPhone");
        String = v62;
        if ( v62 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 347, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v62);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 348;
              goto LABEL_180;
            }
          }
          return String;
        }
        v63 = RegReadFlag(hkey, "PromoteAlternates", a5 + 180, Source);
        String = v63;
        if ( v63 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 349, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v63);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 350;
              goto LABEL_180;
            }
          }
          return String;
        }
        v64 = RegReadFlag(hkey, "TryNextAlternateOnFail", a5 + 184, Source);
        String = v64;
        if ( v64 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 351, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v64);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 352;
              goto LABEL_180;
            }
          }
          return String;
        }
        v7 = v83;
LABEL_32:
        v11 = v77;
LABEL_86:
        v8 = v78;
        goto LABEL_47;
      }
      v7 = v83;
      v11 = v77;
      *(_DWORD *)(v83 + 536) = 1;
    }
    v8 = v78;
LABEL_47:
    v12 = i + 1;
  }
  if ( *(_DWORD *)(a5 + 40) )
  {
    v66 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v67 = 354;
LABEL_389:
      WPP_SF_d(v66[1].Flink, v67, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, 0);
    }
    return 0;
  }
  else
  {
    v39 = WPP_GLOBAL_Control;
    String = 625;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v40 = 353;
LABEL_180:
      WPP_SF_d(v39[1].Flink, v40, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, String);
    }
    return String;
  }
}

```

## disassembly

```asm
0x180085c14  push    rbp
0x180085c16  push    rbx
0x180085c17  push    rsi
0x180085c18  push    rdi
0x180085c19  push    r12
0x180085c1b  push    r13
0x180085c1d  push    r14
0x180085c1f  push    r15
0x180085c21  lea     rbp, [rsp-0BB8h]
0x180085c29  sub     rsp, 0CB8h
0x180085c30  mov     rax, cs:__security_cookie
0x180085c37  xor     rax, rsp
0x180085c3a  mov     [rbp+0BF0h+var_50], rax
0x180085c41  mov     r14, [rbp+0BF0h+arg_20]
0x180085c48  mov     r13, r9
0x180085c4b  mov     [rsp+0CF0h+var_C78], r9
0x180085c50  mov     rbx, rdx
0x180085c53  mov     [rsp+0CF0h+var_CA4], r8d
0x180085c58  mov     r15, rcx
0x180085c5b  mov     [rsp+0CF0h+var_C98], rdx
0x180085c60  mov     rcx, cs:WPP_GLOBAL_Control
0x180085c67  lea     rdi, WPP_GLOBAL_Control
0x180085c6e  cmp     rcx, rdi
0x180085c71  jz      short loc_180085C94
0x180085c73  test    byte ptr [rcx+1Ch], 80h
0x180085c77  jz      short loc_180085C94
0x180085c79  cmp     byte ptr [rcx+19h], 6
0x180085c7d  jb      short loc_180085C94
0x180085c7f  mov     rcx, [rcx+10h]
0x180085c83  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x180085c8a  mov     edx, 11Ah
0x180085c8f  call    WPP_SF_
0x180085c94  xor     edx, edx; Val
0x180085c96  lea     rcx, [rbp+0BF0h+Source]; void *
0x180085c9d  mov     r8d, 602h; Size
0x180085ca3  call    memset_0
0x180085ca8  lea     rdx, [rsp+0CF0h+cSubKeys]; lpcSubKeys
0x180085cad  mov     [rsp+0CF0h+cSubKeys], 0
0x180085cb5  mov     rcx, r15; hKey
0x180085cb8  call    RegGetNumberOfSubkeys
0x180085cbd  xor     ecx, ecx
0x180085cbf  test    eax, eax
0x180085cc1  jz      short loc_180085D00
0x180085cc3  lea     esi, [rcx+1]
0x180085cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180085ccd  cmp     rcx, rdi
0x180085cd0  jz      short loc_180085CF9
0x180085cd2  test    byte ptr [rcx+1Ch], 80h
0x180085cd6  jz      short loc_180085CF9
0x180085cd8  lea     edi, [rsi+1]
0x180085cdb  cmp     [rcx+19h], dil
0x180085cdf  jb      short loc_180085CF9
0x180085ce1  mov     rcx, [rcx+10h]
0x180085ce5  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x180085cec  mov     edx, 11Bh
0x180085cf1  mov     r9d, esi
0x180085cf4  call    WPP_SF_d
0x180085cf9  mov     eax, esi
0x180085cfb  jmp     loc_18008768C
0x180085d00  mov     r12d, ecx
0x180085d03  mov     [rsp+0CF0h+var_CAC], ecx
0x180085d07  mov     eax, ecx
0x180085d09  mov     [rsp+0CF0h+var_CA0], ecx
0x180085d0d  mov     [rsp+0CF0h+var_CA8], ecx
0x180085d11  mov     [rsp+0CF0h+var_C80], ecx
0x180085d15  cmp     [rsp+0CF0h+cSubKeys], ecx
0x180085d19  jbe     loc_18008614E
0x180085d1f  mov     edi, 2
0x180085d24  lea     esi, [rdi-1]
0x180085d27  lea     r8, [rbp+0BF0h+Source]
0x180085d2e  mov     edx, eax
0x180085d30  mov     rcx, r15
0x180085d33  call    RegGetIthSectionName
0x180085d38  test    eax, eax
0x180085d3a  jz      loc_18008761F
0x180085d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180085d47  lea     rax, WPP_GLOBAL_Control
0x180085d4e  cmp     rcx, rax
0x180085d51  jz      short loc_180085D7B
0x180085d53  test    byte ptr [rcx+1Ch], 80h
0x180085d57  jz      short loc_180085D7B
0x180085d59  cmp     byte ptr [rcx+19h], 5
0x180085d5d  jb      short loc_180085D7B
0x180085d5f  mov     rcx, [rcx+10h]
0x180085d63  lea     r9, [rbp+0BF0h+Source]
0x180085d6a  mov     edx, 11Dh
0x180085d6f  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x180085d76  call    WPP_SF_s
0x180085d7b  mov     r8d, 601h; Count
0x180085d81  lea     rdx, [rbp+0BF0h+Source]; Source
0x180085d88  lea     rcx, [rbp+0BF0h+Destination]; Destination
0x180085d8c  call    strncpy_0
0x180085d91  or      ecx, 0FFFFFFFFh
0x180085d94  lea     rax, [rbp+0BF0h+Source]
0x180085d9b  mov     [rsp+0CF0h+cchCount2], ecx; cchCount2
0x180085d9f  lea     r8, aIsdn_0; "isdn"
0x180085da6  mov     r9d, ecx; cchCount1
0x180085da9  mov     [rsp+0CF0h+lpString2], rax; lpString2
0x180085dae  mov     ecx, 7Fh; Locale
0x180085db3  mov     edx, esi; dwCmpFlags
0x180085db5  call    cs:__imp_CompareStringA
0x180085dbc  nop     dword ptr [rax+rax+00h]
0x180085dc1  cmp     eax, edi
0x180085dc3  jnz     loc_180085F75
0x180085dc9  lea     rcx, [rbp+0BF0h+Source]
0x180085dd0  mov     rax, rbx
0x180085dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085dd8  mov     [r14+20h], rax
0x180085ddc  lea     rcx, [rbp+0BF0h+Destination]
0x180085de0  mov     [rsp+0CF0h+var_CC0], rcx
0x180085de5  lea     rax, [r14+0A8h]
0x180085dec  mov     qword ptr [rsp+0CF0h+cchCount2], rax
0x180085df1  mov     r12d, 6
0x180085df7  mov     eax, [rsp+0CF0h+var_CA4]
0x180085dfb  mov     rcx, r15
0x180085dfe  mov     dword ptr [rsp+0CF0h+lpString2], eax
0x180085e02  mov     [r14+28h], r12d
0x180085e06  call    RegReadPhoneList
0x180085e0b  mov     ebx, eax
0x180085e0d  test    eax, eax
0x180085e0f  jnz     loc_180086B9D
0x180085e15  lea     r8, [r14+0B0h]
0x180085e1c  mov     rcx, r15; hkey
0x180085e1f  lea     r9, [rbp+0BF0h+Destination]
0x180085e23  lea     rdx, aLastselectedph; "LastSelectedPhone"
0x180085e2a  call    RegReadLong
0x180085e2f  mov     ebx, eax
0x180085e31  test    eax, eax
0x180085e33  jnz     loc_180086B43
0x180085e39  lea     r8, [r14+0B4h]
0x180085e40  mov     rcx, r15
0x180085e43  lea     r9, [rbp+0BF0h+Destination]
0x180085e47  lea     rdx, aPromotealterna; "PromoteAlternates"
0x180085e4e  call    RegReadFlag
0x180085e53  mov     ebx, eax
0x180085e55  test    eax, eax
0x180085e57  jnz     loc_180086ADA
0x180085e5d  lea     r8, [r14+0B8h]
0x180085e64  mov     rcx, r15
0x180085e67  lea     r9, [rbp+0BF0h+Destination]
0x180085e6b  lea     rdx, aTrynextalterna; "TryNextAlternateOnFail"
0x180085e72  call    RegReadFlag
0x180085e77  mov     ebx, eax
0x180085e79  test    eax, eax
0x180085e7b  jnz     loc_180086A71
0x180085e81  lea     r12, [r14+84h]
0x180085e88  mov     rcx, r15; hkey
0x180085e8b  mov     r8, r12
0x180085e8e  lea     r9, [rbp+0BF0h+Destination]
0x180085e92  lea     rdx, aLinetype; "LineType"
0x180085e99  call    RegReadLong
0x180085e9e  mov     ebx, eax
0x180085ea0  xor     eax, eax
0x180085ea2  test    ebx, ebx
0x180085ea4  jnz     loc_180086A08
0x180085eaa  cmp     [r12], edi
0x180085eae  jbe     short loc_180085EB4
0x180085eb0  mov     [r12], eax
0x180085eb4  lea     r8, [r14+88h]
0x180085ebb  mov     rcx, r15
0x180085ebe  lea     r9, [rbp+0BF0h+Destination]
0x180085ec2  lea     rdx, aFallback; "Fallback"
0x180085ec9  call    RegReadFlag
0x180085ece  mov     ebx, eax
0x180085ed0  test    eax, eax
0x180085ed2  jnz     loc_18008699F
0x180085ed8  lea     r12, [r14+80h]
0x180085edf  mov     rcx, r15
0x180085ee2  mov     r8, r12
0x180085ee5  mov     [r12], esi
0x180085ee9  lea     r9, [rbp+0BF0h+Destination]
0x180085eed  lea     rdx, aProprietary; "Proprietary"
0x180085ef4  call    RegReadFlag
0x180085ef9  mov     ebx, eax
0x180085efb  test    eax, eax
0x180085efd  jnz     loc_180086936
0x180085f03  lea     r9, [rbp+0BF0h+Destination]
0x180085f07  mov     [rsp+0CF0h+var_CB0], 0FFFFFFFFh
0x180085f0f  lea     r8, [rsp+0CF0h+var_CB0]
0x180085f14  mov     rcx, r15; hkey
0x180085f17  lea     rdx, aChannelaggrega; "ChannelAggregation"
0x180085f1e  call    RegReadLong
0x180085f23  xor     ecx, ecx
0x180085f25  mov     ebx, eax
0x180085f27  test    eax, eax
0x180085f29  jnz     loc_1800868CD
0x180085f2f  mov     eax, [rsp+0CF0h+var_CB0]
0x180085f33  cmp     eax, 0FFFFFFFFh
0x180085f36  jnz     short loc_180085F3E
0x180085f38  mov     [r12], ecx
0x180085f3c  jmp     short loc_180085F45
0x180085f3e  mov     [r14+90h], eax
0x180085f45  lea     r8, [r14+8Ch]
0x180085f4c  mov     rcx, r15
0x180085f4f  lea     r9, [rbp+0BF0h+Destination]
0x180085f53  lea     rdx, aEnablecompress; "EnableCompression"
0x180085f5a  call    RegReadFlag
0x180085f5f  xor     ecx, ecx
0x180085f61  mov     ebx, eax
0x180085f63  test    eax, eax
0x180085f65  jnz     loc_180086864
0x180085f6b  mov     r12d, [rsp+0CF0h+var_CA0]
0x180085f70  jmp     loc_18008654D
0x180085f75  or      ecx, 0FFFFFFFFh
0x180085f78  lea     rax, [rbp+0BF0h+Source]
0x180085f7f  mov     [rsp+0CF0h+cchCount2], ecx; cchCount2
0x180085f83  lea     r8, aModem_0; "modem"
0x180085f8a  mov     r9d, ecx; cchCount1
0x180085f8d  mov     [rsp+0CF0h+lpString2], rax; lpString2
0x180085f92  mov     ecx, 7Fh; Locale
0x180085f97  mov     edx, esi; dwCmpFlags
0x180085f99  call    cs:__imp_CompareStringA
0x180085fa0  nop     dword ptr [rax+rax+00h]
0x180085fa5  cmp     eax, edi
0x180085fa7  jnz     loc_18008618B
0x180085fad  lea     rcx, [rbp+0BF0h+Source]
0x180085fb4  mov     rax, rbx
0x180085fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085fbc  mov     [r14+20h], rax
0x180085fc0  lea     rcx, [rbp+0BF0h+Destination]
0x180085fc4  mov     [rsp+0CF0h+var_CC0], rcx
0x180085fc9  lea     rax, [r14+0A8h]
0x180085fd0  mov     qword ptr [rsp+0CF0h+cchCount2], rax
0x180085fd5  mov     rcx, r15
0x180085fd8  mov     eax, [rsp+0CF0h+var_CA4]
0x180085fdc  mov     dword ptr [rsp+0CF0h+lpString2], eax
0x180085fe0  mov     dword ptr [r14+28h], 3
0x180085fe8  call    RegReadPhoneList
0x180085fed  xor     r12d, r12d
0x180085ff0  mov     ebx, eax
0x180085ff2  test    eax, eax
0x180085ff4  jnz     loc_180086F3C
0x180085ffa  lea     r8, [r14+0B0h]
0x180086001  mov     rcx, r15; hkey
0x180086004  lea     r9, [rbp+0BF0h+Destination]
0x180086008  lea     rdx, aLastselectedph; "LastSelectedPhone"
0x18008600f  call    RegReadLong
0x180086014  mov     ebx, eax
0x180086016  test    eax, eax
0x180086018  jnz     loc_180086ED3
0x18008601e  lea     r8, [r14+0B4h]
0x180086025  mov     rcx, r15
0x180086028  lea     r9, [rbp+0BF0h+Destination]
0x18008602c  lea     rdx, aPromotealterna; "PromoteAlternates"
0x180086033  call    RegReadFlag
0x180086038  mov     ebx, eax
0x18008603a  test    eax, eax
0x18008603c  jnz     loc_180086E6A
0x180086042  lea     r8, [r14+0B8h]
0x180086049  mov     rcx, r15
0x18008604c  lea     r9, [rbp+0BF0h+Destination]
0x180086050  lea     rdx, aTrynextalterna; "TryNextAlternateOnFail"
0x180086057  call    RegReadFlag
0x18008605c  mov     ebx, eax
0x18008605e  test    eax, eax
0x180086060  jnz     loc_180086E01
0x180086066  lea     r8, [r14+6Ch]
0x18008606a  mov     rcx, r15
0x18008606d  lea     r9, [rbp+0BF0h+Destination]
0x180086071  lea     rdx, aHwflowcontrol; "HwFlowControl"
0x180086078  call    RegReadFlag
0x18008607d  mov     ebx, eax
0x18008607f  test    eax, eax
0x180086081  jnz     loc_180086D98
0x180086087  lea     r8, [r14+70h]
0x18008608b  mov     rcx, r15
0x18008608e  lea     r9, [rbp+0BF0h+Destination]
0x180086092  lea     rdx, aProtocol; "Protocol"
0x180086099  call    RegReadFlag
0x18008609e  mov     ebx, eax
0x1800860a0  test    eax, eax
0x1800860a2  jnz     loc_180086D2F
0x1800860a8  lea     r8, [r14+74h]
0x1800860ac  mov     rcx, r15
0x1800860af  lea     r9, [rbp+0BF0h+Destination]
0x1800860b3  lea     rdx, aCompression; "Compression"
0x1800860ba  call    RegReadFlag
0x1800860bf  mov     ebx, eax
0x1800860c1  test    eax, eax
0x1800860c3  jnz     loc_180086CC6
0x1800860c9  mov     rcx, [rbp+0BF0h+arg_30]
0x1800860d0  lea     r8, [r14+78h]
0x1800860d4  test    rcx, rcx
0x1800860d7  jz      short loc_1800860E7
0x1800860d9  cmp     [rcx], r12d
0x1800860dc  mov     eax, r12d
0x1800860df  setz    al
0x1800860e2  mov     [r8], eax
0x1800860e5  jmp     short loc_180086104
0x1800860e7  lea     r9, [rbp+0BF0h+Destination]
0x1800860eb  mov     rcx, r15
0x1800860ee  lea     rdx, aSpeaker; "Speaker"
0x1800860f5  call    RegReadFlag
0x1800860fa  mov     ebx, eax
0x1800860fc  test    eax, eax
0x1800860fe  jnz     loc_180086C61
0x180086104  lea     r8, [r14+7Ch]
0x180086108  mov     rcx, r15; hkey
0x18008610b  lea     r9, [rbp+0BF0h+Destination]
0x18008610f  lea     rdx, aMdmprotocol; "MdmProtocol"
  ... truncated ...
```
