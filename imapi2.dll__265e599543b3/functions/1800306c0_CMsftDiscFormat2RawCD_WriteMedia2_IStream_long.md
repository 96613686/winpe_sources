# CMsftDiscFormat2RawCD::WriteMedia2(IStream *,long)

- ea: `0x1800306c0`
- end: `0x18003122a`
- name: `?WriteMedia2@CMsftDiscFormat2RawCD@@UEAAJPEAUIStream@@J@Z`
- size: `2922`
- prototype: `__int64 __fastcall(CMsftDiscFormat2RawCD *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002fc8`
- `0x1800140f4`
- `0x180014134`
- `0x180014180`
- `0x180016778`
- `0x1800236b4`
- `0x180023ac8`
- `0x180023b14`
- `0x18002fe88`
- `0x1800303d8`
- `0x1800306c0`
- `0x1800323f0`
- `0x180046a94`
- `0x180046bf4`
- `0x180047408`
- `0x180047598`
- `0x1800486e4`
- `0x18004984a`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180030d5a`
- `ole32!CoTaskMemFree` at `0x180030d5a`
- `KERNEL32!GetTickCount` at `0x1800306f9`
- `KERNEL32!GetTickCount` at `0x1800311a6`
- `KERNEL32!GetTickCount` at `0x1800306f9`
- `KERNEL32!GetTickCount` at `0x1800311a6`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2RawCD::WriteMedia2(CMsftDiscFormat2RawCD *this, struct IStream *a2, int a3)
{
  enum _IMAPI_MEDIA_PHYSICAL_TYPE v4; // ebx
  unsigned int v5; // r15d
  __int64 v8; // r8
  DWORD TickCount; // r13d
  PVOID *v10; // rcx
  __int64 v11; // r9
  unsigned int v12; // esi
  __int64 v13; // rdx
  int v14; // r14d
  int v15; // eax
  int v16; // r9d
  PVOID *v17; // rcx
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rax
  void *v20; // rax
  unsigned int v21; // edi
  __int64 v22; // rax
  int started; // eax
  struct IDiscRecorder2Ex *v24; // rdx
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  int v27; // eax
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  int v30; // eax
  int v31; // eax
  struct IDiscRecorder2Ex *v32; // rdx
  unsigned int v33; // r8d
  unsigned __int8 v34; // r9
  int v35; // esi
  int DiscInfo; // eax
  int v37; // edi
  PVOID *v38; // rcx
  __int64 v39; // rdx
  int v40; // ecx
  DWORD v41; // eax
  void (*v43)(void *, struct _SENSE_DATA *); // [rsp+20h] [rbp-C8h]
  int v44[4]; // [rsp+40h] [rbp-A8h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-98h] BYREF
  unsigned __int64 v46; // [rsp+60h] [rbp-88h]

  v4 = IMAPI_MEDIA_TYPE_UNKNOWN;
  v5 = 0;
  TickCount = GetTickCount();
  if ( a2 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 47), 53, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    v4 = -2147467261;
  }
  if ( a3 <= 4650 )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 388) & 4) != 0 && *((_BYTE *)v10 + 385) >= 3u )
      WPP_SF_(v10[47], 54, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
    v4 = -1062599155;
    goto LABEL_119;
  }
  if ( v4 < IMAPI_MEDIA_TYPE_UNKNOWN )
    goto LABEL_119;
  if ( !*((_QWORD *)this + 22) )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 388) & 4) != 0 && *((_BYTE *)v10 + 385) )
      WPP_SF_(v10[47], 55, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
    v4 = -1062600701;
    goto LABEL_119;
  }
  if ( !*((_WORD *)this + 96) )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 388) & 4) != 0 && *((_BYTE *)v10 + 385) >= 3u )
      WPP_SF_(v10[47], 56, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
    v4 = -1062599166;
    goto LABEL_119;
  }
  if ( *((_WORD *)this + 80) )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 388) & 4) != 0 && *((_BYTE *)v10 + 385) >= 3u )
      WPP_SF_(v10[47], 57, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
    v4 = -1062599168;
    goto LABEL_119;
  }
  if ( *((_WORD *)this + 97) )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 388) & 4) != 0 && *((_BYTE *)v10 + 385) >= 3u )
      WPP_SF_(v10[47], 58, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
    v4 = -1062599162;
    goto LABEL_119;
  }
  v8 = *((unsigned int *)this + 70);
  if ( (int)v8 >= 0 )
  {
    v4 = -1062599162;
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 388) & 4) != 0 && *((_BYTE *)v10 + 385) >= 3u )
      WPP_SF_d(v10[47], 59, &WPP_465922b870433540ecd6931719c7292a_Traceguids, 3232368134LL);
    goto LABEL_119;
  }
  if ( (int)v8 + a3 < 0 )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 388) & 4) != 0 && *((_BYTE *)v10 + 385) >= 3u )
    {
      LODWORD(v43) = a3;
      WPP_SF_DDDd(v10[47], 60, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
    }
    v4 = -1062599153;
    goto LABEL_119;
  }
  v11 = *((unsigned int *)this + 54);
  if ( (_DWORD)v11 == 1 )
  {
    v12 = 2368;
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 388) & 4) != 0 && *((_BYTE *)v10 + 385) >= 4u )
    {
      v13 = 61;
      LODWORD(v43) = 1;
LABEL_65:
      WPP_SF_LddD(v10[47], v13, v8, v11);
    }
  }
  else if ( (_DWORD)v11 == 3 )
  {
    v12 = 2448;
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 388) & 4) != 0 && *((_BYTE *)v10 + 385) >= 4u )
    {
      v13 = 62;
      v11 = 3;
      LODWORD(v43) = 3;
      goto LABEL_65;
    }
  }
  else
  {
    v8 = 2;
    if ( (_DWORD)v11 == 2 )
    {
      v12 = 2448;
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 388) & 4) != 0 && *((_BYTE *)v10 + 385) >= 4u )
      {
        v13 = 63;
        v11 = 2;
        LODWORD(v43) = 2;
        goto LABEL_65;
      }
    }
    else
    {
      v12 = 0;
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 388) & 4) != 0 && *((_BYTE *)v10 + 385) >= 2u )
        WPP_SF_Dd(v10[47], 64, &WPP_465922b870433540ecd6931719c7292a_Traceguids, v11, *((_DWORD *)this + 54));
      v4 = -2147024809;
    }
  }
  if ( v4 < IMAPI_MEDIA_TYPE_UNKNOWN )
    goto LABEL_119;
  v14 = 0;
  memset_0(pv, 0, 0x50u);
  v15 = (*(__int64 (__fastcall **)(struct IStream *, LPVOID *, __int64))(*(_QWORD *)a2 + 96LL))(a2, pv, 1);
  v16 = v15;
  v4 = -1062599155;
  if ( v15 < 0 )
  {
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 385) < 3u )
    {
      goto LABEL_93;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 47),
      65,
      &WPP_465922b870433540ecd6931719c7292a_Traceguids,
      (unsigned int)v15);
    goto LABEL_92;
  }
  v18 = v46 % v12;
  if ( v18 )
  {
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 385) < 3u )
    {
      goto LABEL_93;
    }
    WPP_SF_iidD(
      *((_QWORD *)WPP_GLOBAL_Control + 47),
      66,
      &WPP_465922b870433540ecd6931719c7292a_Traceguids,
      v46,
      v46,
      v18,
      v18);
    goto LABEL_92;
  }
  v19 = v46 / v12;
  if ( v19 > 0x7FFFFFFF )
  {
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 385) < 3u )
    {
      goto LABEL_93;
    }
    WPP_SF_ii(*((_QWORD *)WPP_GLOBAL_Control + 47), 67, &WPP_465922b870433540ecd6931719c7292a_Traceguids, v19, v19);
    goto LABEL_92;
  }
  if ( v46 )
  {
    v17 = (PVOID *)WPP_GLOBAL_Control;
    v14 = v19;
    goto LABEL_95;
  }
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
  {
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 47),
      (unsigned int)(v46 + 68),
      &WPP_465922b870433540ecd6931719c7292a_Traceguids);
LABEL_92:
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_93:
  v16 = -1062599155;
LABEL_95:
  v8 = (unsigned int)(v14 - a3);
  if ( (int)v8 >= 6900 )
  {
    v4 = v16;
    if ( v16 >= 0 && (int)v8 > *((_DWORD *)this + 71) + 6750 )
    {
      if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 388) & 4) != 0 && *((_BYTE *)v17 + 385) >= 3u )
      {
        LODWORD(v43) = *((_DWORD *)this + 72) + 6750;
        WPP_SF_DDDd(v17[47], 70, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
      v4 = -1062599159;
    }
  }
  else if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 388) & 4) != 0 && *((_BYTE *)v17 + 385) >= 3u )
  {
    WPP_SF_Dd(v17[47], 69, &WPP_465922b870433540ecd6931719c7292a_Traceguids, (unsigned int)v8, v8);
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  v20 = pv[0];
  if ( pv[0] )
  {
    if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 388) & 4) != 0 && *((_BYTE *)v17 + 385) >= 3u )
    {
      WPP_SF_(v17[47], 71, &WPP_465922b870433540ecd6931719c7292a_Traceguids);
      v20 = pv[0];
    }
    CoTaskMemFree(v20);
  }
  if ( v4 >= IMAPI_MEDIA_TYPE_UNKNOWN )
  {
    v21 = *((_DWORD *)this + 70) + a3;
    v22 = *(_QWORD *)a2;
    *(_QWORD *)v44 = 0;
    v4 = (*(unsigned int (__fastcall **)(struct IStream *, unsigned __int64, _QWORD, int *))(v22 + 40))(
           a2,
           v12 * (unsigned __int64)v21,
           0,
           v44);
    if ( v4 < IMAPI_MEDIA_TYPE_UNKNOWN
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 47),
        72,
        &WPP_465922b870433540ecd6931719c7292a_Traceguids,
        (unsigned int)v4);
      v5 = v14 - v21;
      goto LABEL_119;
    }
    v5 = v14 - v21;
    if ( v4 >= IMAPI_MEDIA_TYPE_UNKNOWN )
    {
      v27 = CMsftDiscFormat2RawCD::SendModifiedModePage(
              this,
              *((struct IDiscRecorder2Ex **)this + 23),
              (enum _IMAPI_FORMAT2_RAW_CD_DATA_SECTOR_TYPE)*((_DWORD *)this + 54));
      v4 = v27;
      if ( v27 < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 385) < 3u )
        {
          goto LABEL_119;
        }
        v29 = 73;
        goto LABEL_136;
      }
      v27 = CMsftDiscFormat2RawCD::ValidateModePageParametersStuck(this, *((struct IDiscRecorder2Ex **)this + 23));
      v4 = v27;
      if ( v27 < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 385) < 3u )
        {
          goto LABEL_119;
        }
        v29 = 74;
LABEL_136:
        WPP_SF_d(v28[47], v29, &WPP_465922b870433540ecd6931719c7292a_Traceguids, (unsigned int)v27);
        goto LABEL_119;
      }
      v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 34) + 136LL))(*((_QWORD *)this + 34), v12);
      v4 = v30;
      if ( v30 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
      {
        WPP_SF_ddD(
          *((_QWORD *)WPP_GLOBAL_Control + 47),
          75,
          &WPP_465922b870433540ecd6931719c7292a_Traceguids,
          v12,
          v12,
          v30);
      }
    }
  }
LABEL_119:
  *((_WORD *)this + 97) = -1;
  *((_WORD *)this + 80) = -1;
  if ( v4 < IMAPI_MEDIA_TYPE_UNKNOWN )
    goto LABEL_177;
  started = Imapi2Utility::SendStartStopUnitCommand(*((_QWORD *)this + 23));
  v4 = started;
  if ( started < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 385) < 3u )
    {
      goto LABEL_177;
    }
    v26 = 76;
    goto LABEL_147;
  }
  started = Imapi2Utility::RequestAutomaticOPC(*((Imapi2Utility **)this + 23), v24);
  v4 = started;
  if ( started < 0 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 385) < 3u )
    {
      goto LABEL_177;
    }
    v26 = 77;
LABEL_147:
    WPP_SF_d(v25[47], v26, &WPP_465922b870433540ecd6931719c7292a_Traceguids, (unsigned int)started);
    goto LABEL_177;
  }
  v31 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *, _QWORD, _QWORD))(**((_QWORD **)this + 34) + 56LL))(
          *((_QWORD *)this + 34),
          a2,
          *((unsigned int *)this + 70),
          v5);
  v35 = v31;
  if ( v31 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 47),
      78,
      &WPP_465922b870433540ecd6931719c7292a_Traceguids,
      (unsigned int)v31);
  }
  LOBYTE(v33) = 1;
  DiscInfo = Imapi2Utility::SendSynchronizeCacheCommand(*((Imapi2Utility **)this + 23), v32, v33, v34);
  v37 = DiscInfo;
  if ( DiscInfo >= 0 )
  {
    DiscInfo = Imapi2Utility::WaitForReadDiscInfo(
                 *((Imapi2Utility **)this + 23),
                 (struct IDiscRecorder2Ex *)0x10E,
                 0,
                 0,
                 v43);
    v37 = DiscInfo;
    if ( DiscInfo >= 0 )
    {
LABEL_164:
      v38 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_165;
    }
    v38 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
    {
      v39 = 80;
      goto LABEL_163;
    }
  }
  else
  {
    v38 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 388) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 385) >= 3u )
    {
      v39 = 79;
LABEL_163:
      WPP_SF_d(v38[47], v39, &WPP_465922b870433540ecd6931719c7292a_Traceguids, (unsigned int)DiscInfo);
      goto LABEL_164;
    }
  }
LABEL_165:
  if ( v35 >= 0 )
  {
    if ( v37 < 0 )
    {
      if ( v38 != &WPP_GLOBAL_Control && (*((_BYTE *)v38 + 388) & 4) != 0 && *((_BYTE *)v38 + 385) >= 3u )
        WPP_SF_d(v38[47], 82, &WPP_465922b870433540ecd6931719c7292a_Traceguids, (unsigned int)v37);
      v4 = v37;
    }
  }
  else
  {
    if ( v38 != &WPP_GLOBAL_Control && (*((_BYTE *)v38 + 388) & 4) != 0 && *((_BYTE *)v38 + 385) >= 3u )
      WPP_SF_d(v38[47], 81, &WPP_465922b870433540ecd6931719c7292a_Traceguids, (unsigned int)v35);
    v4 = v35;
  }
LABEL_177:
  *((_WORD *)this + 80) = 0;
  if ( v4 != -2147467261 )
  {
    if ( v4 == -1062600701
      || (unsigned int)(v4 + 1062599168) <= 0xD && (v40 = 8709, _bittest(&v40, v4 + 1062599168))
      || (v41 = GetTickCount(),
          Imapi2Utility::SQMLogImapiSession(
            *((Imapi2Utility **)this + 22),
            (struct IDiscRecorder2 *)2,
            0,
            v4,
            v41 - TickCount,
            0xFFFFFFFF,
            0,
            0,
            v44[0]),
          (v4 & 0x80FF0000) == 0x80AA0000) )
    {
      Imapi2Utility::SetErrorDescription(v4, (int)&CLSID_MsftDiscFormat2RawCD, (const struct _GUID *)v8);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800306c0  mov     [rsp+arg_18], rbx
0x1800306c5  push    rbp
0x1800306c6  push    rsi
0x1800306c7  push    rdi
0x1800306c8  push    r12
0x1800306ca  push    r13
0x1800306cc  push    r14
0x1800306ce  push    r15
0x1800306d0  sub     rsp, 0B0h
0x1800306d7  mov     rax, cs:__security_cookie
0x1800306de  xor     rax, rsp
0x1800306e1  mov     [rsp+0E8h+var_48], rax
0x1800306e9  xor     eax, eax
0x1800306eb  mov     edi, r8d
0x1800306ee  mov     ebx, eax
0x1800306f0  mov     r15d, eax
0x1800306f3  mov     r12, rdx
0x1800306f6  mov     rbp, rcx
0x1800306f9  call    cs:__imp_GetTickCount
0x1800306ff  xor     edx, edx
0x180030701  lea     r10, WPP_GLOBAL_Control
0x180030708  mov     r13d, eax
0x18003070b  mov     r14b, 4
0x18003070e  lea     r11d, [rdx+3]
0x180030712  test    r12, r12
0x180030715  jnz     short loc_180030768
0x180030717  mov     rcx, cs:WPP_GLOBAL_Control
0x18003071e  cmp     rcx, r10
0x180030721  jz      short loc_180030761
0x180030723  test    [rcx+184h], r14b
0x18003072a  jz      short loc_180030761
0x18003072c  cmp     [rcx+181h], r11b
0x180030733  jb      short loc_180030761
0x180030735  mov     rcx, [rcx+178h]
0x18003073c  lea     edx, [r11+32h]
0x180030740  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x180030747  call    WPP_SF_
0x18003074c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030753  lea     r10, WPP_GLOBAL_Control
0x18003075a  xor     edx, edx
0x18003075c  lea     r11d, [r12+3]
0x180030761  mov     ebx, 80004003h
0x180030766  jmp     short loc_18003076F
0x180030768  mov     rcx, cs:WPP_GLOBAL_Control
0x18003076f  cmp     edi, 122Ah
0x180030775  jg      short loc_1800307B0
0x180030777  cmp     rcx, r10
0x18003077a  jz      short loc_1800307A6
0x18003077c  test    [rcx+184h], r14b
0x180030783  jz      short loc_1800307A6
0x180030785  cmp     [rcx+181h], r11b
0x18003078c  jb      short loc_1800307A6
0x18003078e  mov     rcx, [rcx+178h]
0x180030795  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18003079c  mov     edx, 36h ; '6'
0x1800307a1  call    WPP_SF_
0x1800307a6  mov     ebx, 0C0AA060Dh
0x1800307ab  jmp     loc_180030DF2
0x1800307b0  test    ebx, ebx
0x1800307b2  js      loc_180030DF2
0x1800307b8  cmp     [rbp+0B0h], rdx
0x1800307bf  jnz     short loc_1800307FA
0x1800307c1  cmp     rcx, r10
0x1800307c4  jz      short loc_1800307F0
0x1800307c6  test    [rcx+184h], r14b
0x1800307cd  jz      short loc_1800307F0
0x1800307cf  cmp     byte ptr [rcx+181h], 1
0x1800307d6  jb      short loc_1800307F0
0x1800307d8  mov     rcx, [rcx+178h]
0x1800307df  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x1800307e6  mov     edx, 37h ; '7'
0x1800307eb  call    WPP_SF_
0x1800307f0  mov     ebx, 0C0AA0003h
0x1800307f5  jmp     loc_180030DF2
0x1800307fa  cmp     [rbp+0C0h], dx
0x180030801  jnz     short loc_18003083C
0x180030803  cmp     rcx, r10
0x180030806  jz      short loc_180030832
0x180030808  test    [rcx+184h], r14b
0x18003080f  jz      short loc_180030832
0x180030811  cmp     [rcx+181h], r11b
0x180030818  jb      short loc_180030832
0x18003081a  mov     rcx, [rcx+178h]
0x180030821  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x180030828  mov     edx, 38h ; '8'
0x18003082d  call    WPP_SF_
0x180030832  mov     ebx, 0C0AA0602h
0x180030837  jmp     loc_180030DF2
0x18003083c  cmp     [rbp+0A0h], dx
0x180030843  jz      short loc_18003087E
0x180030845  cmp     rcx, r10
0x180030848  jz      short loc_180030874
0x18003084a  test    [rcx+184h], r14b
0x180030851  jz      short loc_180030874
0x180030853  cmp     [rcx+181h], r11b
0x18003085a  jb      short loc_180030874
0x18003085c  mov     rcx, [rcx+178h]
0x180030863  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x18003086a  mov     edx, 39h ; '9'
0x18003086f  call    WPP_SF_
0x180030874  mov     ebx, 0C0AA0600h
0x180030879  jmp     loc_180030DF2
0x18003087e  cmp     [rbp+0C2h], dx
0x180030885  jz      short loc_1800308C0
0x180030887  cmp     rcx, r10
0x18003088a  jz      short loc_1800308B6
0x18003088c  test    [rcx+184h], r14b
0x180030893  jz      short loc_1800308B6
0x180030895  cmp     [rcx+181h], r11b
0x18003089c  jb      short loc_1800308B6
0x18003089e  mov     rcx, [rcx+178h]
0x1800308a5  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x1800308ac  mov     edx, 3Ah ; ':'
0x1800308b1  call    WPP_SF_
0x1800308b6  mov     ebx, 0C0AA0606h
0x1800308bb  jmp     loc_180030DF2
0x1800308c0  mov     r8d, [rbp+118h]
0x1800308c7  test    r8d, r8d
0x1800308ca  js      short loc_180030914
0x1800308cc  mov     ebx, 0C0AA0606h
0x1800308d1  cmp     rcx, r10
0x1800308d4  jz      loc_180030DF2
0x1800308da  test    [rcx+184h], r14b
0x1800308e1  jz      loc_180030DF2
0x1800308e7  cmp     [rcx+181h], r11b
0x1800308ee  jb      loc_180030DF2
0x1800308f4  mov     rcx, [rcx+178h]
0x1800308fb  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x180030902  mov     edx, 3Bh ; ';'
0x180030907  mov     r9d, ebx
0x18003090a  call    WPP_SF_d
0x18003090f  jmp     loc_180030DF2
0x180030914  lea     eax, [r8+rdi]
0x180030918  test    eax, eax
0x18003091a  jns     short loc_180030969
0x18003091c  cmp     rcx, r10
0x18003091f  jz      short loc_18003095F
0x180030921  test    [rcx+184h], r14b
0x180030928  jz      short loc_18003095F
0x18003092a  cmp     [rcx+181h], r11b
0x180030931  jb      short loc_18003095F
0x180030933  mov     rcx, [rcx+178h]
0x18003093a  neg     r8d
0x18003093d  mov     [rsp+0E8h+var_B8], r8d
0x180030942  mov     edx, 3Ch ; '<'
0x180030947  mov     [rsp+0E8h+var_C0], r8d
0x18003094c  mov     r9d, edi
0x18003094f  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x180030956  mov     dword ptr [rsp+0E8h+var_C8], edi
0x18003095a  call    WPP_SF_DDDd
0x18003095f  mov     ebx, 0C0AA060Fh
0x180030964  jmp     loc_180030DF2
0x180030969  mov     r9d, [rbp+0D8h]
0x180030970  cmp     r9d, 1
0x180030974  jnz     short loc_1800309B6
0x180030976  mov     esi, 940h
0x18003097b  cmp     rcx, r10
0x18003097e  jz      loc_180030A86
0x180030984  test    [rcx+184h], r14b
0x18003098b  jz      loc_180030A86
0x180030991  cmp     [rcx+181h], r14b
0x180030998  jb      loc_180030A86
0x18003099e  mov     [rsp+0E8h+var_B8], esi
0x1800309a2  lea     edx, [r9+3Ch]
0x1800309a6  mov     eax, r9d
0x1800309a9  mov     [rsp+0E8h+var_C0], esi
0x1800309ad  mov     dword ptr [rsp+0E8h+var_C8], eax
0x1800309b1  jmp     loc_180030A39
0x1800309b6  cmp     r9d, r11d
0x1800309b9  jnz     short loc_1800309FC
0x1800309bb  mov     eax, 990h
0x1800309c0  mov     esi, eax
0x1800309c2  cmp     rcx, r10
0x1800309c5  jz      loc_180030A86
0x1800309cb  test    [rcx+184h], r14b
0x1800309d2  jz      loc_180030A86
0x1800309d8  cmp     [rcx+181h], r14b
0x1800309df  jb      loc_180030A86
0x1800309e5  mov     [rsp+0E8h+var_B8], eax
0x1800309e9  mov     edx, 3Eh ; '>'
0x1800309ee  mov     [rsp+0E8h+var_C0], eax
0x1800309f2  mov     r9d, r11d
0x1800309f5  mov     dword ptr [rsp+0E8h+var_C8], r11d
0x1800309fa  jmp     short loc_180030A39
0x1800309fc  mov     r8d, 2
0x180030a02  cmp     r9d, r8d
0x180030a05  jnz     short loc_180030A49
0x180030a07  mov     eax, 990h
0x180030a0c  mov     esi, eax
0x180030a0e  cmp     rcx, r10
0x180030a11  jz      short loc_180030A86
0x180030a13  test    [rcx+184h], r14b
0x180030a1a  jz      short loc_180030A86
0x180030a1c  cmp     [rcx+181h], r14b
0x180030a23  jb      short loc_180030A86
0x180030a25  mov     [rsp+0E8h+var_B8], eax
0x180030a29  lea     edx, [r8+3Dh]
0x180030a2d  mov     [rsp+0E8h+var_C0], eax
0x180030a31  mov     r9d, r8d
0x180030a34  mov     dword ptr [rsp+0E8h+var_C8], r8d
0x180030a39  mov     rcx, [rcx+178h]
0x180030a40  call    WPP_SF_LddD
0x180030a45  xor     edx, edx
0x180030a47  jmp     short loc_180030A86
0x180030a49  mov     esi, edx
0x180030a4b  cmp     rcx, r10
0x180030a4e  jz      short loc_180030A81
0x180030a50  test    [rcx+184h], r14b
0x180030a57  jz      short loc_180030A81
0x180030a59  cmp     [rcx+181h], r8b
0x180030a60  jb      short loc_180030A81
0x180030a62  mov     rcx, [rcx+178h]
0x180030a69  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x180030a70  mov     edx, 40h ; '@'
0x180030a75  mov     dword ptr [rsp+0E8h+var_C8], r9d
0x180030a7a  call    WPP_SF_Dd
0x180030a7f  xor     edx, edx
0x180030a81  mov     ebx, 80070057h
0x180030a86  test    ebx, ebx
0x180030a88  js      loc_180030DF2
0x180030a8e  mov     r14d, edx
0x180030a91  lea     rcx, [rsp+0E8h+pv]; void *
0x180030a96  xor     edx, edx; Val
0x180030a98  lea     r8d, [rdx+50h]; Size
0x180030a9c  call    memset_0
0x180030aa1  mov     rax, [r12]
0x180030aa5  lea     rdx, [rsp+0E8h+pv]
0x180030aaa  mov     r8d, 1
0x180030ab0  mov     rcx, r12
0x180030ab3  mov     rax, [rax+60h]
0x180030ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030abc  mov     r9d, eax
0x180030abf  mov     ebx, 0C0AA060Dh
0x180030ac4  test    eax, eax
0x180030ac6  jns     short loc_180030B16
0x180030ac8  mov     rcx, cs:WPP_GLOBAL_Control
0x180030acf  lea     rax, WPP_GLOBAL_Control
0x180030ad6  cmp     rcx, rax
0x180030ad9  jz      loc_180030C2A
0x180030adf  test    byte ptr [rcx+184h], 4
0x180030ae6  jz      loc_180030C2A
0x180030aec  cmp     byte ptr [rcx+181h], 3
0x180030af3  jb      loc_180030C2A
0x180030af9  mov     rcx, [rcx+178h]
0x180030b00  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x180030b07  mov     edx, 41h ; 'A'
0x180030b0c  call    WPP_SF_d
0x180030b11  jmp     loc_180030C23
0x180030b16  mov     r8, [rsp+0E8h+var_88]
0x180030b1b  xor     edx, edx
0x180030b1d  mov     rax, r8
0x180030b20  mov     ecx, esi
0x180030b22  div     rcx
0x180030b25  mov     r10, rdx
0x180030b28  test    rdx, rdx
0x180030b2b  jz      short loc_180030B8D
0x180030b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b34  lea     rax, WPP_GLOBAL_Control
0x180030b3b  cmp     rcx, rax
0x180030b3e  jz      loc_180030C2A
0x180030b44  test    byte ptr [rcx+184h], 4
0x180030b4b  jz      loc_180030C2A
0x180030b51  cmp     byte ptr [rcx+181h], 3
0x180030b58  jb      loc_180030C2A
0x180030b5e  mov     rcx, [rcx+178h]
0x180030b65  mov     r9, r8
0x180030b68  mov     [rsp+0E8h+var_B8], r10d
0x180030b6d  mov     edx, 42h ; 'B'
0x180030b72  mov     [rsp+0E8h+var_C0], r10d
0x180030b77  mov     [rsp+0E8h+var_C8], r8
0x180030b7c  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x180030b83  call    WPP_SF_iidD
0x180030b88  jmp     loc_180030C23
0x180030b8d  mov     rax, r8
0x180030b90  div     rcx
0x180030b93  cmp     rax, 7FFFFFFFh
0x180030b99  jbe     short loc_180030BE2
0x180030b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ba2  lea     rdx, WPP_GLOBAL_Control
0x180030ba9  cmp     rcx, rdx
0x180030bac  jz      short loc_180030C2A
0x180030bae  test    byte ptr [rcx+184h], 4
0x180030bb5  jz      short loc_180030C2A
0x180030bb7  cmp     byte ptr [rcx+181h], 3
0x180030bbe  jb      short loc_180030C2A
0x180030bc0  mov     rcx, [rcx+178h]
0x180030bc7  lea     r8, WPP_465922b870433540ecd6931719c7292a_Traceguids
0x180030bce  mov     edx, 43h ; 'C'
0x180030bd3  mov     [rsp+0E8h+var_C8], rax
0x180030bd8  mov     r9, rax
0x180030bdb  call    WPP_SF_ii
0x180030be0  jmp     short loc_180030C23
0x180030be2  test    r8, r8
0x180030be5  jnz     short loc_180030C2F
0x180030be7  mov     rcx, cs:WPP_GLOBAL_Control
0x180030bee  lea     rax, WPP_GLOBAL_Control
0x180030bf5  cmp     rcx, rax
0x180030bf8  jz      short loc_180030C2A
0x180030bfa  test    byte ptr [rcx+184h], 4
0x180030c01  jz      short loc_180030C2A
  ... truncated ...
```
