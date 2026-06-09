# WriterQueryMediaType

- ea: `0x180014288`
- end: `0x180014c47`
- name: `WriterQueryMediaType`
- size: `2495`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x180010090`
- `0x180013c4c`
- `0x180013dcc`

## callees

- `0x180007bac`
- `0x180007bd4`
- `0x180007c14`
- `0x180007d40`
- `0x180012548`
- `0x180012a2c`
- `0x180012a8c`
- `0x180014288`
- `0x1800171d8`
- `0x180017f24`
- `0x180017f58`
- `0x180018350`
- `0x180018430`
- `0x180019010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180014b41`
- `ole32!CoTaskMemFree` at `0x180014c1e`
- `ole32!CoTaskMemFree` at `0x180014b41`
- `ole32!CoTaskMemFree` at `0x180014c1e`

## pseudocode

```c
__int64 __fastcall WriterQueryMediaType(
        __int64 a1,
        struct IDiscRecorder2Ex *a2,
        enum _IMAPI_MEDIA_PHYSICAL_TYPE *a3,
        unsigned int *a4)
{
  unsigned int v4; // ebx
  unsigned int v5; // r12d
  unsigned int *v6; // rax
  _QWORD *v9; // rcx
  int CurrentPhysicalMediaType; // edi
  int v11; // eax
  unsigned int v12; // esi
  int v13; // ecx
  _BYTE *v14; // rdi
  int v15; // r12d
  unsigned int v16; // r15d
  unsigned int LastTrackOfLastSession; // r14d
  _QWORD *v18; // rcx
  unsigned int v19; // edx
  int v20; // eax
  BOOL v21; // r10d
  __int64 v22; // r9
  _BYTE *v23; // rdx
  unsigned int v24; // edi
  unsigned int v25; // r14d
  int v26; // r15d
  char v27; // al
  _QWORD *v28; // rcx
  _QWORD *v29; // rcx
  IDiscRecorder2Ex v31; // [rsp+40h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-28h] BYREF
  unsigned int FirstTrackOfLastSession; // [rsp+50h] [rbp-20h] BYREF
  LPVOID v34; // [rsp+58h] [rbp-18h] BYREF
  _BYTE *v35; // [rsp+60h] [rbp-10h] BYREF
  __int64 v36; // [rsp+68h] [rbp-8h]
  enum _IMAPI_MEDIA_PHYSICAL_TYPE *v38; // [rsp+C0h] [rbp+50h]

  v38 = a3;
  v4 = 0;
  v35 = 0;
  v5 = 0;
  HIDWORD(v31.lpVtbl) = 0;
  v6 = a4;
  v36 = 0;
  v34 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 70, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a2);
    v9 = WPP_GLOBAL_Control;
    v6 = a4;
    a3 = v38;
  }
  if ( a1 && a2 && a3 && v6 )
  {
    LODWORD(v31.lpVtbl) = 0;
    CurrentPhysicalMediaType = Imapi2Utility::GetCurrentPhysicalMediaType(a2, &v31, a3);
    if ( CurrentPhysicalMediaType >= 0 && (unsigned int)(LODWORD(v31.lpVtbl) - 1) > 2 )
    {
      v4 = 8;
LABEL_11:
      *v38 = v5;
      *a4 = v4;
LABEL_14:
      v9 = WPP_GLOBAL_Control;
      goto LABEL_166;
    }
    v11 = CMsftDiscInformation::Init((CMsftDiscInformation *)&v35, a2);
    if ( v11 == -1062599937 )
    {
      CurrentPhysicalMediaType = -2147220978;
      goto LABEL_14;
    }
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          72,
          &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
          (unsigned int)v11);
      CurrentPhysicalMediaType = 0;
      goto LABEL_11;
    }
    v12 = v36;
    v13 = 0;
    v14 = v35;
    if ( (unsigned int)v36 >= 0xA )
      v13 = (unsigned __int8)v35[9] << 8;
    v15 = v13 + (unsigned __int8)v35[4];
    LODWORD(pv) = v15;
    FirstTrackOfLastSession = CMsftDiscInformation::get_FirstTrackOfLastSession((CMsftDiscInformation *)&v35);
    v16 = FirstTrackOfLastSession;
    LastTrackOfLastSession = CMsftDiscInformation::get_LastTrackOfLastSession((CMsftDiscInformation *)&v35);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          73,
          &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
          v14[2] & 3,
          v15);
        v18 = WPP_GLOBAL_Control;
      }
      if ( v18 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v18 + 68) & 1) != 0 )
        {
          WPP_SF_DD(v18[7], 74, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, v16, LastTrackOfLastSession);
          v18 = WPP_GLOBAL_Control;
        }
        if ( v18 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v18 + 68) & 1) != 0 )
          {
            v19 = (unsigned __int8)v14[7];
            v20 = 0;
            if ( v12 >= 0x20 )
              v20 = (v19 >> 6) & 1;
            v21 = (v19 & 0x80u) != 0 && v12 >= 0x10;
            WPP_SF_DDDD(
              v18[7],
              75,
              ((unsigned __int8)v14[7] >> 5) & 1,
              (unsigned __int8)v14[8],
              v21,
              v20,
              ((unsigned __int8)v14[7] >> 5) & 1);
            v18 = WPP_GLOBAL_Control;
          }
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
          {
            WPP_SF_DD(
              v18[7],
              76,
              &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
              v14[7] & 3,
              ((unsigned __int8)v14[7] >> 2) & 1);
            v18 = WPP_GLOBAL_Control;
          }
        }
      }
    }
    v5 = 5;
    if ( (v14[2] & 3) != 0 )
    {
      if ( (v14[2] & 3) == 1 )
      {
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
        {
          WPP_SF_(v18[7], 78, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
          v18 = WPP_GLOBAL_Control;
        }
        v4 = 4;
      }
      else if ( (v14[2] & 3) == 2 )
      {
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
        {
          WPP_SF_(v18[7], 79, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
          goto LABEL_46;
        }
      }
      else if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
      {
        WPP_SF_d(v18[7], 80, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, v14[2] & 3);
LABEL_46:
        v18 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
      {
        WPP_SF_(v18[7], 77, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
        v18 = WPP_GLOBAL_Control;
      }
      v4 = 5;
    }
    if ( (((unsigned __int8)v14[2] >> 2) & 3) != 0 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
      {
        WPP_SF_d(v18[7], 82, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, v14[2] & 3);
        v18 = WPP_GLOBAL_Control;
      }
      v4 = v4 & 0xFFFFFFF6 | 8;
    }
    else if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
    {
      WPP_SF_(v18[7], 81, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
      v18 = WPP_GLOBAL_Control;
    }
    if ( (v14[2] & 0x10) != 0 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
      {
        WPP_SF_(v18[7], 83, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
        v18 = WPP_GLOBAL_Control;
      }
      v4 |= 2u;
    }
    v22 = (unsigned __int8)v14[8];
    if ( v14[8] )
    {
      switch ( (_BYTE)v22 )
      {
        case 0x10:
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
          {
            WPP_SF_(v18[7], 85, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
            v18 = WPP_GLOBAL_Control;
          }
          v5 = 3;
          break;
        case 0x20:
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
          {
            WPP_SF_(v18[7], 86, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
            v18 = WPP_GLOBAL_Control;
          }
          v5 = 2;
          break;
        case 0xFF:
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
          {
            WPP_SF_(v18[7], 87, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
            v18 = WPP_GLOBAL_Control;
          }
          break;
        default:
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
          {
            WPP_SF_d(v18[7], 88, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, v22);
            v18 = WPP_GLOBAL_Control;
          }
          v5 = 6;
          break;
      }
    }
    else
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
      {
        WPP_SF_(v18[7], 84, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
        v18 = WPP_GLOBAL_Control;
      }
      v5 = 1;
    }
    if ( (v4 & 0xD) != 4 )
      goto LABEL_134;
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
    {
      WPP_SF_(v18[7], 89, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
      v18 = WPP_GLOBAL_Control;
    }
    if ( (_DWORD)pv == LastTrackOfLastSession )
    {
      if ( v16 == LastTrackOfLastSession )
      {
        if ( ((int (__fastcall *)(struct IDiscRecorder2Ex *, _QWORD, __int64, LPVOID *, char *))a2->lpVtbl->GetTrackInformation)(
               a2,
               LastTrackOfLastSession,
               1,
               &v34,
               (char *)&v31.lpVtbl + 4) >= 0 )
        {
          v23 = v34;
          if ( HIDWORD(v31.lpVtbl) < 0x21 )
            v24 = *((unsigned __int8 *)v34 + 2);
          else
            v24 = *((unsigned __int8 *)v34 + 2) | (*((unsigned __int8 *)v34 + 32) << 8);
          v25 = *((unsigned __int8 *)v34 + 15)
              | ((*((unsigned __int8 *)v34 + 14)
                | ((*((unsigned __int8 *)v34 + 13) | (*((unsigned __int8 *)v34 + 12) << 8)) << 8)) << 8);
          v26 = *((unsigned __int8 *)v34 + 11)
              | ((*((unsigned __int8 *)v34 + 10)
                | ((*((unsigned __int8 *)v34 + 9) | (*((unsigned __int8 *)v34 + 8) << 8)) << 8)) << 8);
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 7), 93, &WPP_GLOBAL_Control, v24, v25, v26);
            v23 = v34;
            v18 = WPP_GLOBAL_Control;
          }
          if ( FirstTrackOfLastSession == v24 )
          {
            v27 = v23[6];
            if ( v27 >= 0 )
            {
              if ( (v27 & 0x10) != 0 && v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
              {
                WPP_SF_(v18[7], 96, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
                v18 = WPP_GLOBAL_Control;
              }
              if ( v25 == v26 )
                goto LABEL_134;
              if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 68) & 1) == 0 )
              {
LABEL_133:
                v4 |= 8u;
LABEL_134:
                pv = 0;
                FirstTrackOfLastSession = 0;
                if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 68) & 1) != 0 )
                  WPP_SF_(v18[7], 98, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
                CurrentPhysicalMediaType = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, unsigned int *))a2->lpVtbl->GetFeaturePage)(
                                             a2,
                                             45,
                                             0,
                                             &pv,
                                             &FirstTrackOfLastSession);
                if ( CurrentPhysicalMediaType < 0 )
                {
                  CurrentPhysicalMediaType = 0;
                }
                else
                {
                  v28 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 99, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
                    v28 = WPP_GLOBAL_Control;
                  }
                  if ( (*((_BYTE *)pv + 2) & 1) != 0 )
                  {
                    if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 68) & 1) != 0 )
                      WPP_SF_(v28[7], 101, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
                  }
                  else
                  {
                    if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 68) & 1) != 0 )
                      WPP_SF_(v28[7], 100, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
                    v4 |= 8u;
                  }
                  CoTaskMemFree(pv);
                }
                if ( (unsigned __int8)PrvWriterIsFileSystemReadWrite(a1) )
                {
                  v29 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 102, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
                    v29 = WPP_GLOBAL_Control;
                  }
                  v4 |= 8u;
                }
                else
                {
                  v29 = WPP_GLOBAL_Control;
                }
                if ( (v4 & 4) == 0 )
                {
                  if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 68) & 1) != 0 )
                    WPP_SF_(v29[7], 103, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
                  v4 &= ~8u;
                }
                goto LABEL_11;
              }
              WPP_SF_DD(v18[7], 97, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, v25, v26);
            }
            else
            {
              if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 68) & 1) == 0 )
                goto LABEL_133;
              WPP_SF_(v18[7], 95, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
            }
          }
          else
          {
            if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 68) & 1) == 0 )
              goto LABEL_133;
            WPP_SF_DD(v18[7], 94, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, v24, FirstTrackOfLastSession);
          }
        }
        else
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_133;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            92,
            &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
            LastTrackOfLastSession);
        }
      }
      else
      {
        if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 68) & 1) == 0 )
          goto LABEL_133;
        WPP_SF_DD(v18[7], 91, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, v16, LastTrackOfLastSession);
      }
    }
    else
    {
      if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 68) & 1) == 0 )
        goto LABEL_133;
      WPP_SF_DD(v18[7], 90, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, (unsigned int)pv, LastTrackOfLastSession);
    }
    v18 = WPP_GLOBAL_Control;
    goto LABEL_133;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 1) != 0 )
  {
    WPP_SF_(v9[7], 71, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  CurrentPhysicalMediaType = -2147024809;
LABEL_166:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 1) != 0 )
    WPP_SF_DDD(v9[7], 104, a3, v5, v4, CurrentPhysicalMediaType);
  if ( v34 )
    CoTaskMemFree(v34);
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)&v35);
  return (unsigned int)CurrentPhysicalMediaType;
}

```

## disassembly

```asm
0x180014288  mov     rax, rsp
0x18001428b  mov     [rax+10h], rbx
0x18001428f  mov     [rax+20h], r9
0x180014293  mov     [rax+18h], r8
0x180014297  mov     [rax+8], rcx
0x18001429b  push    rbp
0x18001429c  push    rsi
0x18001429d  push    rdi
0x18001429e  push    r12
0x1800142a0  push    r13
0x1800142a2  push    r14
0x1800142a4  push    r15
0x1800142a6  mov     rbp, rsp
0x1800142a9  sub     rsp, 70h
0x1800142ad  xor     ebx, ebx
0x1800142af  mov     [rbp+var_10], 0
0x1800142b7  xor     r12d, r12d
0x1800142ba  mov     dword ptr [rbp+var_30.lpVtbl+4], ebx
0x1800142bd  mov     rax, r9
0x1800142c0  mov     [rbp+var_8], 0
0x1800142c8  mov     r13, rdx
0x1800142cb  mov     [rbp+var_18], 0
0x1800142d3  mov     rdi, rcx
0x1800142d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142dd  lea     rsi, WPP_GLOBAL_Control
0x1800142e4  lea     r14, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800142eb  cmp     rcx, rsi
0x1800142ee  jz      short loc_180014317
0x1800142f0  test    byte ptr [rcx+44h], 1
0x1800142f4  jz      short loc_180014317
0x1800142f6  mov     rcx, [rcx+38h]
0x1800142fa  lea     edx, [rbx+46h]
0x1800142fd  mov     r9, r13
0x180014300  mov     r8, r14
0x180014303  call    WPP_SF_q
0x180014308  mov     rcx, cs:WPP_GLOBAL_Control
0x18001430f  mov     rax, [rbp+arg_18]
0x180014313  mov     r8, [rbp+arg_10]; enum _IMAPI_MEDIA_PHYSICAL_TYPE *
0x180014317  test    rdi, rdi
0x18001431a  jz      loc_180014BC9
0x180014320  test    r13, r13
0x180014323  jz      loc_180014BC9
0x180014329  test    r8, r8
0x18001432c  jz      loc_180014BC9
0x180014332  test    rax, rax
0x180014335  jz      loc_180014BC9
0x18001433b  lea     rdx, [rbp+var_30]; struct IDiscRecorder2Ex *
0x18001433f  mov     dword ptr [rbp+var_30.lpVtbl], ebx
0x180014342  mov     rcx, r13; this
0x180014345  call    ?GetCurrentPhysicalMediaType@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAW4_IMAPI_MEDIA_PHYSICAL_TYPE@@@Z; Imapi2Utility::GetCurrentPhysicalMediaType(IDiscRecorder2Ex *,_IMAPI_MEDIA_PHYSICAL_TYPE *)
0x18001434a  mov     edi, eax
0x18001434c  test    eax, eax
0x18001434e  js      short loc_180014375
0x180014350  mov     ecx, dword ptr [rbp+var_30.lpVtbl]
0x180014353  dec     ecx
0x180014355  cmp     ecx, 2
0x180014358  jbe     short loc_180014375
0x18001435a  mov     ebx, 8
0x18001435f  lea     rsi, WPP_GLOBAL_Control
0x180014366  mov     rax, [rbp+arg_10]
0x18001436a  mov     [rax], r12d
0x18001436d  mov     rax, [rbp+arg_18]
0x180014371  mov     [rax], ebx
0x180014373  jmp     short loc_18001438D
0x180014375  mov     rdx, r13; struct IDiscRecorder2Ex *
0x180014378  lea     rcx, [rbp+var_10]; this
0x18001437c  call    ?Init@CMsftDiscInformation@@QEAAJPEAUIDiscRecorder2Ex@@@Z; CMsftDiscInformation::Init(IDiscRecorder2Ex *)
0x180014381  cmp     eax, 0C0AA02FFh
0x180014386  jnz     short loc_180014399
0x180014388  mov     edi, 8004020Eh
0x18001438d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014394  jmp     loc_180014BF1
0x180014399  test    eax, eax
0x18001439b  jns     short loc_1800143C7
0x18001439d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143a4  cmp     rcx, rsi
0x1800143a7  jz      short loc_1800143C3
0x1800143a9  test    byte ptr [rcx+44h], 1
0x1800143ad  jz      short loc_1800143C3
0x1800143af  mov     rcx, [rcx+38h]
0x1800143b3  mov     edx, 48h ; 'H'
0x1800143b8  mov     r9d, eax
0x1800143bb  mov     r8, r14
0x1800143be  call    WPP_SF_d
0x1800143c3  xor     edi, edi
0x1800143c5  jmp     short loc_180014366
0x1800143c7  mov     esi, dword ptr [rbp+var_8]
0x1800143ca  xor     ecx, ecx
0x1800143cc  mov     rdi, [rbp+var_10]
0x1800143d0  cmp     esi, 0Ah
0x1800143d3  jb      short loc_1800143DC
0x1800143d5  movzx   ecx, byte ptr [rdi+9]
0x1800143d9  shl     ecx, 8
0x1800143dc  movzx   r12d, byte ptr [rdi+4]
0x1800143e1  add     r12d, ecx
0x1800143e4  lea     rcx, [rbp+var_10]; this
0x1800143e8  mov     dword ptr [rbp+pv], r12d
0x1800143ec  call    ?get_FirstTrackOfLastSession@CMsftDiscInformation@@QEAAKXZ; CMsftDiscInformation::get_FirstTrackOfLastSession(void)
0x1800143f1  lea     rcx, [rbp+var_10]; this
0x1800143f5  mov     [rbp+var_20], eax
0x1800143f8  mov     r15d, eax
0x1800143fb  call    ?get_LastTrackOfLastSession@CMsftDiscInformation@@QEAAKXZ; CMsftDiscInformation::get_LastTrackOfLastSession(void)
0x180014400  mov     r14d, eax
0x180014403  mov     rcx, cs:WPP_GLOBAL_Control
0x18001440a  lea     rdx, WPP_GLOBAL_Control
0x180014411  cmp     rcx, rdx
0x180014414  jz      loc_18001453F
0x18001441a  test    byte ptr [rcx+44h], 1
0x18001441e  jz      short loc_180014451
0x180014420  movzx   r9d, byte ptr [rdi+2]
0x180014425  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001442c  mov     rcx, [rcx+38h]
0x180014430  and     r9d, 3
0x180014434  mov     edx, 49h ; 'I'
0x180014439  mov     dword ptr [rsp+70h+var_50], r12d
0x18001443e  call    WPP_SF_DD
0x180014443  mov     rcx, cs:WPP_GLOBAL_Control
0x18001444a  lea     rdx, WPP_GLOBAL_Control
0x180014451  cmp     rcx, rdx
0x180014454  jz      loc_18001453F
0x18001445a  test    byte ptr [rcx+44h], 1
0x18001445e  jz      short loc_18001448B
0x180014460  mov     rcx, [rcx+38h]
0x180014464  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001446b  mov     edx, 4Ah ; 'J'
0x180014470  mov     dword ptr [rsp+70h+var_50], r14d
0x180014475  mov     r9d, r15d
0x180014478  call    WPP_SF_DD
0x18001447d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014484  lea     rdx, WPP_GLOBAL_Control
0x18001448b  cmp     rcx, rdx
0x18001448e  jz      loc_18001453F
0x180014494  test    byte ptr [rcx+44h], 1
0x180014498  jz      short loc_1800144FB
0x18001449a  movzx   edx, byte ptr [rdi+7]
0x18001449e  xor     eax, eax
0x1800144a0  mov     r8d, edx
0x1800144a3  shr     r8d, 5
0x1800144a7  and     r8d, 1
0x1800144ab  cmp     esi, 20h ; ' '
0x1800144ae  jb      short loc_1800144B8
0x1800144b0  mov     eax, edx
0x1800144b2  shr     eax, 6
0x1800144b5  and     eax, 1
0x1800144b8  test    dl, dl
0x1800144ba  jns     short loc_1800144C9
0x1800144bc  cmp     esi, 10h
0x1800144bf  jb      short loc_1800144C9
0x1800144c1  mov     r10d, 1
0x1800144c7  jmp     short loc_1800144CC
0x1800144c9  xor     r10d, r10d
0x1800144cc  movzx   r9d, byte ptr [rdi+8]
0x1800144d1  mov     edx, 4Bh ; 'K'
0x1800144d6  mov     rcx, [rcx+38h]
0x1800144da  mov     [rsp+70h+var_40], r8d
0x1800144df  mov     [rsp+70h+var_48], eax
0x1800144e3  mov     dword ptr [rsp+70h+var_50], r10d
0x1800144e8  call    WPP_SF_DDDD
0x1800144ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144f4  lea     rdx, WPP_GLOBAL_Control
0x1800144fb  cmp     rcx, rdx
0x1800144fe  jz      short loc_18001453F
0x180014500  test    byte ptr [rcx+44h], 1
0x180014504  jz      short loc_18001453F
0x180014506  movzx   r9d, byte ptr [rdi+7]
0x18001450b  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180014512  mov     rcx, [rcx+38h]
0x180014516  mov     eax, r9d
0x180014519  shr     eax, 2
0x18001451c  and     r9d, 3
0x180014520  and     eax, 1
0x180014523  mov     edx, 4Ch ; 'L'
0x180014528  mov     dword ptr [rsp+70h+var_50], eax
0x18001452c  call    WPP_SF_DD
0x180014531  mov     rcx, cs:WPP_GLOBAL_Control
0x180014538  lea     rdx, WPP_GLOBAL_Control
0x18001453f  movzx   r9d, byte ptr [rdi+2]
0x180014544  mov     r12d, 5
0x18001454a  and     r9d, 3
0x18001454e  mov     eax, r9d
0x180014551  jz      loc_1800145E2
0x180014557  sub     eax, 1
0x18001455a  jz      short loc_1800145B4
0x18001455c  cmp     eax, 1
0x18001455f  jz      short loc_180014592
0x180014561  cmp     rcx, rdx
0x180014564  jz      loc_18001460C
0x18001456a  test    byte ptr [rcx+44h], 1
0x18001456e  jz      loc_18001460C
0x180014574  mov     rcx, [rcx+38h]
0x180014578  lea     edx, [r12+4Bh]
0x18001457d  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180014584  call    WPP_SF_d
0x180014589  mov     rcx, cs:WPP_GLOBAL_Control
0x180014590  jmp     short loc_18001460C
0x180014592  cmp     rcx, rdx
0x180014595  jz      short loc_18001460C
0x180014597  test    byte ptr [rcx+44h], 1
0x18001459b  jz      short loc_18001460C
0x18001459d  mov     rcx, [rcx+38h]
0x1800145a1  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800145a8  mov     edx, 4Fh ; 'O'
0x1800145ad  call    WPP_SF_
0x1800145b2  jmp     short loc_180014589
0x1800145b4  cmp     rcx, rdx
0x1800145b7  jz      short loc_1800145DB
0x1800145b9  test    byte ptr [rcx+44h], 1
0x1800145bd  jz      short loc_1800145DB
0x1800145bf  mov     rcx, [rcx+38h]
0x1800145c3  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800145ca  mov     edx, 4Eh ; 'N'
0x1800145cf  call    WPP_SF_
0x1800145d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145db  mov     ebx, 4
0x1800145e0  jmp     short loc_18001460C
0x1800145e2  cmp     rcx, rdx
0x1800145e5  jz      short loc_180014609
0x1800145e7  test    byte ptr [rcx+44h], 1
0x1800145eb  jz      short loc_180014609
0x1800145ed  mov     rcx, [rcx+38h]
0x1800145f1  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800145f8  mov     edx, 4Dh ; 'M'
0x1800145fd  call    WPP_SF_
0x180014602  mov     rcx, cs:WPP_GLOBAL_Control
0x180014609  mov     ebx, r12d
0x18001460c  movzx   r9d, byte ptr [rdi+2]
0x180014611  mov     esi, 8
0x180014616  mov     eax, r9d
0x180014619  shr     eax, 2
0x18001461c  and     eax, 3
0x18001461f  jz      short loc_180014658
0x180014621  lea     rax, WPP_GLOBAL_Control
0x180014628  cmp     rcx, rax
0x18001462b  jz      short loc_180014651
0x18001462d  test    byte ptr [rcx+44h], 1
0x180014631  jz      short loc_180014651
0x180014633  mov     rcx, [rcx+38h]
0x180014637  lea     edx, [rsi+4Ah]
0x18001463a  and     r9d, 3
0x18001463e  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180014645  call    WPP_SF_d
0x18001464a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014651  and     ebx, 0FFFFFFFEh
0x180014654  or      ebx, esi
0x180014656  jmp     short loc_180014686
0x180014658  lea     rdx, WPP_GLOBAL_Control
0x18001465f  cmp     rcx, rdx
0x180014662  jz      short loc_18001468D
0x180014664  test    byte ptr [rcx+44h], 1
0x180014668  jz      short loc_18001468D
0x18001466a  mov     rcx, [rcx+38h]
0x18001466e  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180014675  mov     edx, 51h ; 'Q'
0x18001467a  call    WPP_SF_
0x18001467f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014686  lea     rdx, WPP_GLOBAL_Control
0x18001468d  test    byte ptr [rdi+2], 10h
0x180014691  jz      short loc_1800146C4
0x180014693  cmp     rcx, rdx
0x180014696  jz      short loc_1800146C1
0x180014698  test    byte ptr [rcx+44h], 1
0x18001469c  jz      short loc_1800146C1
0x18001469e  mov     rcx, [rcx+38h]
0x1800146a2  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800146a9  mov     edx, 53h ; 'S'
0x1800146ae  call    WPP_SF_
0x1800146b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146ba  lea     rdx, WPP_GLOBAL_Control
0x1800146c1  or      ebx, 2
0x1800146c4  movzx   r9d, byte ptr [rdi+8]
0x1800146c9  test    r9d, r9d
0x1800146cc  jz      loc_1800147C8
0x1800146d2  cmp     r9b, 10h
0x1800146d6  jz      loc_180014792
0x1800146dc  cmp     r9b, 20h ; ' '
0x1800146e0  jz      short loc_18001475C
0x1800146e2  cmp     r9b, 0FFh
0x1800146e6  jz      short loc_180014721
0x1800146e8  cmp     rcx, rdx
0x1800146eb  jz      short loc_180014716
0x1800146ed  test    byte ptr [rcx+44h], 1
0x1800146f1  jz      short loc_180014716
0x1800146f3  mov     rcx, [rcx+38h]
0x1800146f7  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800146fe  mov     edx, 58h ; 'X'
0x180014703  call    WPP_SF_d
0x180014708  mov     rcx, cs:WPP_GLOBAL_Control
0x18001470f  lea     rdx, WPP_GLOBAL_Control
0x180014716  mov     r12d, 6
0x18001471c  jmp     loc_1800147FC
0x180014721  cmp     rcx, rdx
0x180014724  jz      loc_1800147FC
0x18001472a  test    byte ptr [rcx+44h], 1
0x18001472e  jz      loc_1800147FC
0x180014734  mov     rcx, [rcx+38h]
0x180014738  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001473f  mov     edx, 57h ; 'W'
0x180014744  call    WPP_SF_
0x180014749  mov     rcx, cs:WPP_GLOBAL_Control
0x180014750  lea     rdx, WPP_GLOBAL_Control
  ... truncated ...
```
