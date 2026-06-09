# SnapinRecord::Dump(BookKeepingXml &)

- ea: `0x180010290`
- end: `0x180010d13`
- name: `?Dump@SnapinRecord@@QEBAJAEAVBookKeepingXml@@@Z`
- size: `2691`
- prototype: `int(SnapinRecord *__hidden this, struct BookKeepingXml *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18000c914`
- `0x18000f2fc`

## callees

- `0x18000b980`
- `0x18000bdb8`
- `0x18000be1c`
- `0x18000be80`
- `0x18000bf18`
- `0x18000bf80`
- `0x18000c60c`
- `0x18000caf0`
- `0x18000cfbc`
- `0x18000ecd8`
- `0x180010290`
- `0x180010fb4`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall SnapinRecord::Dump(SnapinRecord *this, struct BookKeepingXml *a2)
{
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  __int64 v7; // rcx
  int v8; // edx
  __int64 v9; // r9
  int v10; // r12d
  char v11; // al
  const wchar_t *v12; // r12
  const wchar_t *v13; // r8
  char v14; // al
  char v15; // al
  const wchar_t *v16; // r8
  char v17; // al
  const wchar_t *v18; // r8
  char v19; // al
  const wchar_t *v20; // r8
  int v21; // eax
  int v22; // r13d
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 ErrorDescription; // r12
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // r13
  int v33; // eax
  unsigned int v34; // r15d
  char v36; // [rsp+20h] [rbp-58h]

  v4 = BookKeepingXml::OpenRecord(a2, 4, *((unsigned int *)this + 458), *((_QWORD *)this + 34));
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        62,
        (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
        *((_QWORD *)this + 34),
        v4);
    return (unsigned int)v5;
  }
  v6 = BookKeepingXml::AddProperty(a2, 11, (char *)this + 8);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 63;
    LODWORD(v9) = (_DWORD)this + 8;
    goto LABEL_9;
  }
  v10 = (_DWORD)this + 1064;
  v6 = BookKeepingXml::AddProperty(a2, 12, (char *)this + 1064);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 64;
    goto LABEL_15;
  }
  v10 = (_DWORD)this + 296;
  v6 = BookKeepingXml::AddProperty(a2, 42, (char *)this + 296);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 65;
    goto LABEL_15;
  }
  v10 = (_DWORD)this + 808;
  v6 = BookKeepingXml::AddProperty(a2, 40, (char *)this + 808);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 66;
    goto LABEL_15;
  }
  v10 = (_DWORD)this + 552;
  v6 = BookKeepingXml::AddProperty(a2, 41, (char *)this + 552);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 67;
    goto LABEL_15;
  }
  v11 = (*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 40LL))(this);
  v12 = L"true";
  v13 = L"true";
  if ( !v11 )
    v13 = L"false";
  v5 = BookKeepingXml::AddProperty(a2, 14, v13);
  if ( v5 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v14 = (*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 40LL))(this);
    v8 = 68;
    goto LABEL_34;
  }
  v15 = (*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 56LL))(this);
  v16 = L"true";
  if ( !v15 )
    v16 = L"false";
  v5 = BookKeepingXml::AddProperty(a2, 16, v16);
  if ( v5 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v14 = (*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 56LL))(this);
    v8 = 69;
    goto LABEL_34;
  }
  v17 = (*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 48LL))(this);
  v18 = L"true";
  if ( !v17 )
    v18 = L"false";
  v5 = BookKeepingXml::AddProperty(a2, 15, v18);
  if ( v5 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v14 = (*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 48LL))(this);
    v8 = 70;
    goto LABEL_34;
  }
  v19 = (*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 64LL))(this);
  v20 = L"true";
  if ( !v19 )
    v20 = L"false";
  v5 = BookKeepingXml::AddProperty(a2, 17, v20);
  if ( v5 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v14 = (*(__int64 (__fastcall **)(SnapinRecord *))(*(_QWORD *)this + 64LL))(this);
    v8 = 71;
LABEL_34:
    v7 = WPP_GLOBAL_Control;
    v36 = v5;
    if ( !v14 )
      v12 = L"false";
    LODWORD(v9) = (_DWORD)v12;
    goto LABEL_10;
  }
  v10 = (_DWORD)this + 1320;
  v6 = BookKeepingXml::AddProperty(a2, 13, (char *)this + 1320);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 72;
    goto LABEL_15;
  }
  v10 = (_DWORD)this + 1576;
  v6 = BookKeepingXml::AddProperty(a2, 18, (char *)this + 1576);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 73;
    goto LABEL_15;
  }
  v10 = (_DWORD)this + 2872;
  v6 = BookKeepingXml::AddProperty(a2, 20, (char *)this + 2872);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 74;
    goto LABEL_15;
  }
  v10 = (_DWORD)this + 1848;
  v6 = BookKeepingXml::AddProperty(a2, 21, (char *)this + 1848);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 75;
    goto LABEL_15;
  }
  v10 = (_DWORD)this + 2104;
  v6 = BookKeepingXml::AddProperty(a2, 22, (char *)this + 2104);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 76;
    goto LABEL_15;
  }
  v10 = (_DWORD)this + 2360;
  v6 = BookKeepingXml::AddProperty(a2, 23, (char *)this + 2360);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 77;
    goto LABEL_15;
  }
  v10 = (_DWORD)this + 2616;
  v6 = BookKeepingXml::AddProperty(a2, 24, (char *)this + 2616);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 78;
    goto LABEL_15;
  }
  v10 = (_DWORD)this + 3128;
  v6 = BookKeepingXml::AddProperty(a2, 25, (char *)this + 3128);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 79;
    goto LABEL_15;
  }
  v21 = BookKeepingXml::AddProperty(a2, 19, *((unsigned int *)this + 461));
  v5 = v21;
  if ( v21 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_dd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        80,
        WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
        *((unsigned int *)this + 461),
        v21);
    goto LABEL_158;
  }
  v22 = (_DWORD)this + 3384;
  v23 = BookKeepingXml::AddProperty(a2, 26, *((unsigned int *)this + 1006));
  v5 = v23;
  if ( v23 < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v25 = *((unsigned int *)this + 1006);
    v26 = 81;
    goto LABEL_95;
  }
  v6 = BookKeepingXml::AddProperty(a2, 38, (char *)this + 3384);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 82;
    goto LABEL_100;
  }
  v10 = (_DWORD)this + 3512;
  v6 = BookKeepingXml::AddProperty(a2, 39, (char *)this + 3512);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 83;
    goto LABEL_15;
  }
  ErrorDescription = SnapinRecord::GetErrorDescription(*((unsigned int *)this + 1006));
  v6 = BookKeepingXml::AddProperty(a2, 27, *(_QWORD *)(ErrorDescription + 8));
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v9 = *(_QWORD *)(ErrorDescription + 8);
    v8 = 84;
    goto LABEL_9;
  }
  v6 = BookKeepingXml::AddProperty(a2, 28, *(_QWORD *)(ErrorDescription + 16));
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v9 = *(_QWORD *)(ErrorDescription + 16);
    v8 = 85;
    goto LABEL_9;
  }
  v23 = BookKeepingXml::AddProperty(a2, 29, *((unsigned int *)this + 1007));
  v5 = v23;
  if ( v23 < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v25 = *((unsigned int *)this + 1007);
    v26 = 86;
    goto LABEL_95;
  }
  v28 = BookKeepingXml::AddProperty(a2, 30, *((_QWORD *)this + 504));
  v5 = v28;
  if ( v28 < 0 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v30 = *((_QWORD *)this + 504);
    v31 = 87;
    goto LABEL_157;
  }
  v10 = (_DWORD)this + 3640;
  v6 = BookKeepingXml::AddProperty(a2, 31, (char *)this + 3640);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 88;
LABEL_15:
    LODWORD(v9) = v10;
LABEL_9:
    v36 = v6;
LABEL_10:
    WPP_SF_Sd(*(_QWORD *)(v7 + 16), v8, (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids, v9, v36);
    goto LABEL_158;
  }
  v6 = BookKeepingXml::AddProperty(a2, 32, (char *)this + 3768);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 89;
    LODWORD(v9) = (_DWORD)this + 3768;
    goto LABEL_9;
  }
  v22 = (_DWORD)this + 4040;
  v23 = BookKeepingXml::AddProperty(a2, 33, *((unsigned int *)this + 1074));
  v5 = v23;
  if ( v23 < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v25 = *((unsigned int *)this + 1074);
    v26 = 90;
    goto LABEL_95;
  }
  v6 = BookKeepingXml::AddProperty(a2, 43, (char *)this + 4040);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 91;
LABEL_100:
    LODWORD(v9) = v22;
    goto LABEL_9;
  }
  v6 = BookKeepingXml::AddProperty(a2, 44, (char *)this + 4168);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v8 = 92;
    LODWORD(v9) = (_DWORD)this + 4168;
    goto LABEL_9;
  }
  v32 = SnapinRecord::GetErrorDescription(*((unsigned int *)this + 1074));
  v6 = BookKeepingXml::AddProperty(a2, 34, *(_QWORD *)(v32 + 8));
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v9 = *(_QWORD *)(v32 + 8);
    v8 = 93;
    goto LABEL_9;
  }
  v6 = BookKeepingXml::AddProperty(a2, 35, *(_QWORD *)(v32 + 16));
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v9 = *(_QWORD *)(v32 + 16);
    v8 = 94;
    goto LABEL_9;
  }
  v23 = BookKeepingXml::AddProperty(a2, 36, *((unsigned int *)this + 1075));
  v5 = v23;
  if ( v23 < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_158;
    v25 = *((unsigned int *)this + 1075);
    v26 = 95;
LABEL_95:
    WPP_SF_dd(*(_QWORD *)(v24 + 16), v26, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids, v25, v23);
    goto LABEL_158;
  }
  v28 = BookKeepingXml::AddProperty(a2, 37, *((_QWORD *)this + 538));
  v5 = v28;
  if ( v28 >= 0 )
    goto LABEL_158;
  v29 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
    goto LABEL_158;
  v30 = *((_QWORD *)this + 538);
  v31 = 96;
LABEL_157:
  WPP_SF_qd(*(_QWORD *)(v29 + 16), v31, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids, v30, v28);
LABEL_158:
  v33 = BookKeepingXml::CloseRecord(a2);
  v34 = v33;
  if ( v33 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    WPP_SF_Sd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      97,
      (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
      *((_QWORD *)this + 34),
      v33);
  if ( v5 >= 0 )
    return v34;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180010290  push    rbx
0x180010292  push    rbp
0x180010293  push    rsi
0x180010294  push    rdi
0x180010295  push    r12
0x180010297  push    r13
0x180010299  push    r14
0x18001029b  push    r15
0x18001029d  sub     rsp, 38h
0x1800102a1  mov     r9, [rcx+110h]
0x1800102a8  mov     r15, rdx
0x1800102ab  mov     r8d, [rcx+728h]
0x1800102b2  mov     r14, rcx
0x1800102b5  mov     rcx, r15
0x1800102b8  mov     edx, 4
0x1800102bd  call    ?OpenRecord@BookKeepingXml@@QEAAJW4_XmlNameId@1@HPEBG@Z; BookKeepingXml::OpenRecord(BookKeepingXml::_XmlNameId,int,ushort const *)
0x1800102c2  mov     ebx, eax
0x1800102c4  test    eax, eax
0x1800102c6  jns     short loc_180010311
0x1800102c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102cf  lea     rsi, WPP_GLOBAL_Control
0x1800102d6  cmp     rcx, rsi
0x1800102d9  jz      loc_180010D00
0x1800102df  mov     dil, 2
0x1800102e2  cmp     [rcx+19h], dil
0x1800102e6  jb      loc_180010D00
0x1800102ec  mov     r9, [r14+110h]
0x1800102f3  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x1800102fa  mov     rcx, [rcx+10h]
0x1800102fe  mov     edx, 3Eh ; '>'
0x180010303  mov     dword ptr [rsp+78h+var_58], eax
0x180010307  call    WPP_SF_Sd
0x18001030c  jmp     loc_180010D00
0x180010311  lea     r8, [r14+8]
0x180010315  mov     edx, 0Bh
0x18001031a  mov     rcx, r15
0x18001031d  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x180010322  lea     rbp, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180010329  mov     ebx, eax
0x18001032b  lea     rsi, WPP_GLOBAL_Control
0x180010332  mov     dil, 2
0x180010335  test    eax, eax
0x180010337  jns     short loc_180010371
0x180010339  mov     rcx, cs:WPP_GLOBAL_Control
0x180010340  cmp     rcx, rsi
0x180010343  jz      loc_180010CBD
0x180010349  cmp     [rcx+19h], dil
0x18001034d  jb      loc_180010CBD
0x180010353  mov     edx, 3Fh ; '?'
0x180010358  lea     r9, [r14+8]
0x18001035c  mov     dword ptr [rsp+78h+var_58], eax
0x180010360  mov     rcx, [rcx+10h]
0x180010364  mov     r8, rbp
0x180010367  call    WPP_SF_Sd
0x18001036c  jmp     loc_180010CBD
0x180010371  lea     r12, [r14+428h]
0x180010378  mov     edx, 0Ch
0x18001037d  mov     r8, r12
0x180010380  mov     rcx, r15
0x180010383  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x180010388  mov     ebx, eax
0x18001038a  test    eax, eax
0x18001038c  jns     short loc_1800103B2
0x18001038e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010395  cmp     rcx, rsi
0x180010398  jz      loc_180010CBD
0x18001039e  cmp     [rcx+19h], dil
0x1800103a2  jb      loc_180010CBD
0x1800103a8  mov     edx, 40h ; '@'
0x1800103ad  mov     r9, r12
0x1800103b0  jmp     short loc_18001035C
0x1800103b2  lea     r12, [r14+128h]
0x1800103b9  mov     edx, 2Ah ; '*'
0x1800103be  mov     r8, r12
0x1800103c1  mov     rcx, r15
0x1800103c4  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x1800103c9  mov     ebx, eax
0x1800103cb  test    eax, eax
0x1800103cd  jns     short loc_1800103F0
0x1800103cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103d6  cmp     rcx, rsi
0x1800103d9  jz      loc_180010CBD
0x1800103df  cmp     [rcx+19h], dil
0x1800103e3  jb      loc_180010CBD
0x1800103e9  mov     edx, 41h ; 'A'
0x1800103ee  jmp     short loc_1800103AD
0x1800103f0  lea     r12, [r14+328h]
0x1800103f7  mov     edx, 28h ; '('
0x1800103fc  mov     r8, r12
0x1800103ff  mov     rcx, r15
0x180010402  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x180010407  mov     ebx, eax
0x180010409  test    eax, eax
0x18001040b  jns     short loc_180010431
0x18001040d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010414  cmp     rcx, rsi
0x180010417  jz      loc_180010CBD
0x18001041d  cmp     [rcx+19h], dil
0x180010421  jb      loc_180010CBD
0x180010427  mov     edx, 42h ; 'B'
0x18001042c  jmp     loc_1800103AD
0x180010431  lea     r12, [r14+228h]
0x180010438  mov     edx, 29h ; ')'
0x18001043d  mov     r8, r12
0x180010440  mov     rcx, r15
0x180010443  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x180010448  mov     ebx, eax
0x18001044a  test    eax, eax
0x18001044c  jns     short loc_180010472
0x18001044e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010455  cmp     rcx, rsi
0x180010458  jz      loc_180010CBD
0x18001045e  cmp     [rcx+19h], dil
0x180010462  jb      loc_180010CBD
0x180010468  mov     edx, 43h ; 'C'
0x18001046d  jmp     loc_1800103AD
0x180010472  mov     rax, [r14]
0x180010475  mov     rcx, r14
0x180010478  mov     rax, [rax+28h]
0x18001047c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010481  test    al, al
0x180010483  lea     r12, aTrue; "true"
0x18001048a  mov     r8, r12
0x18001048d  lea     r13, aFalse; "false"
0x180010494  cmovz   r8, r13
0x180010498  mov     edx, 0Eh
0x18001049d  mov     rcx, r15
0x1800104a0  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x1800104a5  mov     ebx, eax
0x1800104a7  test    eax, eax
0x1800104a9  jns     short loc_1800104F2
0x1800104ab  mov     rax, cs:WPP_GLOBAL_Control
0x1800104b2  cmp     rax, rsi
0x1800104b5  jz      loc_180010CBD
0x1800104bb  cmp     [rax+19h], dil
0x1800104bf  jb      loc_180010CBD
0x1800104c5  mov     rax, [r14]
0x1800104c8  mov     rcx, r14
0x1800104cb  mov     rax, [rax+28h]
0x1800104cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104d4  mov     edx, 44h ; 'D'
0x1800104d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104e0  test    al, al
0x1800104e2  mov     dword ptr [rsp+78h+var_58], ebx
0x1800104e6  cmovz   r12, r13
0x1800104ea  mov     r9, r12
0x1800104ed  jmp     loc_180010360
0x1800104f2  mov     rax, [r14]
0x1800104f5  mov     rcx, r14
0x1800104f8  mov     rax, [rax+38h]
0x1800104fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010501  test    al, al
0x180010503  mov     r8, r12
0x180010506  mov     edx, 10h
0x18001050b  mov     rcx, r15
0x18001050e  cmovz   r8, r13
0x180010512  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x180010517  mov     ebx, eax
0x180010519  test    eax, eax
0x18001051b  jns     short loc_18001054D
0x18001051d  mov     rax, cs:WPP_GLOBAL_Control
0x180010524  cmp     rax, rsi
0x180010527  jz      loc_180010CBD
0x18001052d  cmp     [rax+19h], dil
0x180010531  jb      loc_180010CBD
0x180010537  mov     rax, [r14]
0x18001053a  mov     rcx, r14
0x18001053d  mov     rax, [rax+38h]
0x180010541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010546  mov     edx, 45h ; 'E'
0x18001054b  jmp     short loc_1800104D9
0x18001054d  mov     rax, [r14]
0x180010550  mov     rcx, r14
0x180010553  mov     rax, [rax+30h]
0x180010557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001055c  test    al, al
0x18001055e  mov     r8, r12
0x180010561  mov     edx, 0Fh
0x180010566  mov     rcx, r15
0x180010569  cmovz   r8, r13
0x18001056d  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x180010572  mov     ebx, eax
0x180010574  test    eax, eax
0x180010576  jns     short loc_1800105AB
0x180010578  mov     rax, cs:WPP_GLOBAL_Control
0x18001057f  cmp     rax, rsi
0x180010582  jz      loc_180010CBD
0x180010588  cmp     [rax+19h], dil
0x18001058c  jb      loc_180010CBD
0x180010592  mov     rax, [r14]
0x180010595  mov     rcx, r14
0x180010598  mov     rax, [rax+30h]
0x18001059c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105a1  mov     edx, 46h ; 'F'
0x1800105a6  jmp     loc_1800104D9
0x1800105ab  mov     rax, [r14]
0x1800105ae  mov     rcx, r14
0x1800105b1  mov     rax, [rax+40h]
0x1800105b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105ba  test    al, al
0x1800105bc  mov     r8, r12
0x1800105bf  mov     edx, 11h
0x1800105c4  mov     rcx, r15
0x1800105c7  cmovz   r8, r13
0x1800105cb  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x1800105d0  mov     ebx, eax
0x1800105d2  test    eax, eax
0x1800105d4  jns     short loc_180010609
0x1800105d6  mov     rax, cs:WPP_GLOBAL_Control
0x1800105dd  cmp     rax, rsi
0x1800105e0  jz      loc_180010CBD
0x1800105e6  cmp     [rax+19h], dil
0x1800105ea  jb      loc_180010CBD
0x1800105f0  mov     rax, [r14]
0x1800105f3  mov     rcx, r14
0x1800105f6  mov     rax, [rax+40h]
0x1800105fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105ff  mov     edx, 47h ; 'G'
0x180010604  jmp     loc_1800104D9
0x180010609  lea     r12, [r14+528h]
0x180010610  mov     edx, 0Dh
0x180010615  mov     r8, r12
0x180010618  mov     rcx, r15
0x18001061b  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x180010620  mov     ebx, eax
0x180010622  test    eax, eax
0x180010624  jns     short loc_18001064A
0x180010626  mov     rcx, cs:WPP_GLOBAL_Control
0x18001062d  cmp     rcx, rsi
0x180010630  jz      loc_180010CBD
0x180010636  cmp     [rcx+19h], dil
0x18001063a  jb      loc_180010CBD
0x180010640  mov     edx, 48h ; 'H'
0x180010645  jmp     loc_1800103AD
0x18001064a  lea     r12, [r14+628h]
0x180010651  mov     edx, 12h
0x180010656  mov     r8, r12
0x180010659  mov     rcx, r15
0x18001065c  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x180010661  mov     ebx, eax
0x180010663  test    eax, eax
0x180010665  jns     short loc_18001068B
0x180010667  mov     rcx, cs:WPP_GLOBAL_Control
0x18001066e  cmp     rcx, rsi
0x180010671  jz      loc_180010CBD
0x180010677  cmp     [rcx+19h], dil
0x18001067b  jb      loc_180010CBD
0x180010681  mov     edx, 49h ; 'I'
0x180010686  jmp     loc_1800103AD
0x18001068b  lea     r12, [r14+0B38h]
0x180010692  mov     edx, 14h
0x180010697  mov     r8, r12
0x18001069a  mov     rcx, r15
0x18001069d  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x1800106a2  mov     ebx, eax
0x1800106a4  test    eax, eax
0x1800106a6  jns     short loc_1800106CC
0x1800106a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106af  cmp     rcx, rsi
0x1800106b2  jz      loc_180010CBD
0x1800106b8  cmp     [rcx+19h], dil
0x1800106bc  jb      loc_180010CBD
0x1800106c2  mov     edx, 4Ah ; 'J'
0x1800106c7  jmp     loc_1800103AD
0x1800106cc  lea     r12, [r14+738h]
0x1800106d3  mov     edx, 15h
0x1800106d8  mov     r8, r12
0x1800106db  mov     rcx, r15
0x1800106de  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x1800106e3  mov     ebx, eax
0x1800106e5  test    eax, eax
0x1800106e7  jns     short loc_18001070D
0x1800106e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106f0  cmp     rcx, rsi
0x1800106f3  jz      loc_180010CBD
0x1800106f9  cmp     [rcx+19h], dil
0x1800106fd  jb      loc_180010CBD
0x180010703  mov     edx, 4Bh ; 'K'
0x180010708  jmp     loc_1800103AD
0x18001070d  lea     r12, [r14+838h]
0x180010714  mov     edx, 16h
0x180010719  mov     r8, r12
0x18001071c  mov     rcx, r15
0x18001071f  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x180010724  mov     ebx, eax
0x180010726  test    eax, eax
0x180010728  jns     short loc_18001074E
0x18001072a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010731  cmp     rcx, rsi
0x180010734  jz      loc_180010CBD
0x18001073a  cmp     [rcx+19h], dil
0x18001073e  jb      loc_180010CBD
0x180010744  mov     edx, 4Ch ; 'L'
0x180010749  jmp     loc_1800103AD
0x18001074e  lea     r12, [r14+938h]
0x180010755  mov     edx, 17h
0x18001075a  mov     r8, r12
0x18001075d  mov     rcx, r15
0x180010760  call    ?AddProperty@BookKeepingXml@@QEAAJW4_XmlNameId@1@PEBG@Z; BookKeepingXml::AddProperty(BookKeepingXml::_XmlNameId,ushort const *)
0x180010765  mov     ebx, eax
  ... truncated ...
```
