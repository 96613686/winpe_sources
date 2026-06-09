# WriterGetSessionInfo

- ea: `0x1800134e8`
- end: `0x180013c43`
- name: `WriterGetSessionInfo`
- size: `1883`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x18000b650`
- `0x18000fe20`

## callees

- `0x180007bac`
- `0x180007bd4`
- `0x180007c14`
- `0x180007d40`
- `0x180007d80`
- `0x1800127ec`
- `0x180012a2c`
- `0x180012a8c`
- `0x1800134e8`
- `0x180017f24`
- `0x180017f58`
- `0x180018204`
- `0x180018350`
- `0x1800183b8`
- `0x180018430`

## pseudocode

```c
__int64 __fastcall WriterGetSessionInfo(__int64 a1, _BYTE *a2, _BYTE *a3, _DWORD *a4, int *a5, int *a6)
{
  __int64 v7; // rsi
  _QWORD *v8; // r10
  int v9; // ebx
  _QWORD *v10; // r10
  __int64 v11; // rdx
  int v12; // ecx
  _BYTE *v13; // rdi
  unsigned int v14; // esi
  unsigned int FirstTrackOfLastSession; // r14d
  unsigned int LastTrackOfLastSession; // r12d
  __int64 v17; // rdx
  _QWORD *v19; // rcx
  unsigned int v20; // edx
  int v21; // eax
  BOOL v22; // r10d
  int LastPossibleLeadoutStartTimeAsLba; // eax
  __int64 v24; // r8
  __int64 v25; // r9
  unsigned __int8 v26; // al
  bool v27; // di
  int v28; // eax
  int v29; // r8d
  int v30; // eax
  _QWORD *v31; // rcx
  unsigned __int8 *v32; // rdi
  int v33; // eax
  int v34; // ecx
  int v35; // eax
  int v36; // ecx
  unsigned __int8 v37; // al
  __int64 v38; // r9
  int v39; // ecx
  int v40; // [rsp+20h] [rbp-50h]
  _BYTE *v41; // [rsp+40h] [rbp-30h] BYREF
  __int64 v42; // [rsp+48h] [rbp-28h]
  unsigned __int8 *v43; // [rsp+50h] [rbp-20h] BYREF
  __int64 v44; // [rsp+58h] [rbp-18h]
  unsigned __int8 *v45; // [rsp+60h] [rbp-10h] BYREF
  __int64 v46; // [rsp+68h] [rbp-8h]

  v41 = 0;
  v7 = a1;
  v42 = 0;
  v45 = 0;
  v46 = 0;
  v43 = 0;
  v44 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !v7 || !*(_QWORD *)v7 )
  {
    v9 = -2147024809;
    goto LABEL_21;
  }
  v9 = CMsftDiscInformation::Init((CMsftDiscInformation *)&v41, *(struct IDiscRecorder2Ex **)(v7 + 8));
  if ( v9 >= 0 )
  {
    v12 = 0;
    v13 = v41;
    if ( (unsigned int)v42 >= 0xA )
      v12 = (unsigned __int8)v41[9] << 8;
    v14 = v12 + (unsigned __int8)v41[4];
    FirstTrackOfLastSession = CMsftDiscInformation::get_FirstTrackOfLastSession((CMsftDiscInformation *)&v41);
    LastTrackOfLastSession = CMsftDiscInformation::get_LastTrackOfLastSession((CMsftDiscInformation *)&v41);
    if ( v14 > 0xFF )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_19;
      v17 = 24;
LABEL_18:
      WPP_SF_d(v8[7], v17, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, v14);
      v8 = WPP_GLOBAL_Control;
LABEL_19:
      v9 = -2147220978;
LABEL_20:
      v7 = a1;
      goto LABEL_21;
    }
    *a2 = v14;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          25,
          &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
          v13[2] & 3,
          v14);
        v19 = WPP_GLOBAL_Control;
      }
      if ( v19 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v19 + 68) & 1) != 0 )
        {
          WPP_SF_DD(
            v19[7],
            26,
            &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
            FirstTrackOfLastSession,
            LastTrackOfLastSession);
          v19 = WPP_GLOBAL_Control;
        }
        if ( v19 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v19 + 68) & 1) != 0 )
          {
            v20 = (unsigned __int8)v13[7];
            v21 = 0;
            if ( (unsigned int)v42 >= 0x20 )
              v21 = (v20 >> 6) & 1;
            v22 = (v20 & 0x80u) != 0 && (unsigned int)v42 >= 0x10;
            WPP_SF_DDDD(
              v19[7],
              27,
              ((unsigned __int8)v13[7] >> 5) & 1,
              (unsigned __int8)v13[8],
              v22,
              v21,
              ((unsigned __int8)v13[7] >> 5) & 1);
            v19 = WPP_GLOBAL_Control;
          }
          if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 68) & 1) != 0 )
            WPP_SF_DD(
              v19[7],
              28,
              &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
              v13[7] & 3,
              ((unsigned __int8)v13[7] >> 2) & 1);
        }
      }
    }
    LastPossibleLeadoutStartTimeAsLba = CMsftDiscInformation::get_LastPossibleLeadoutStartTimeAsLba((CMsftDiscInformation *)&v41);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, v24, v14, LastPossibleLeadoutStartTimeAsLba, v13[2] & 3);
      v8 = WPP_GLOBAL_Control;
    }
    if ( LastTrackOfLastSession > 0xFF )
    {
      if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 68) & 1) == 0 )
        goto LABEL_19;
      v17 = 30;
      goto LABEL_18;
    }
    *a3 = LastTrackOfLastSession;
    v26 = v13[2] & 3;
    v27 = v26 < 2u;
    if ( LastTrackOfLastSession <= 1 && v26 < 2u || v14 <= 1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
      v7 = a1;
      *a4 = 0;
    }
    else
    {
      if ( v26 < 2u )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
        --FirstTrackOfLastSession;
      }
      v7 = a1;
      v9 = CMsftTrackInformation::Init(
             (CMsftTrackInformation *)&v45,
             *(struct IDiscRecorder2Ex **)(a1 + 8),
             FirstTrackOfLastSession,
             (enum _IMAPI_READ_TRACK_ADDRESS_TYPE)v25,
             v40);
      if ( v9 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_11;
        v11 = 32;
        goto LABEL_10;
      }
      v28 = 0;
      if ( (unsigned int)v46 >= 0x21 )
        v28 = v45[32] << 8;
      v29 = v45[2];
      if ( v29 + v28 != FirstTrackOfLastSession )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_71;
        v30 = 0;
        if ( (unsigned int)v46 >= 0x21 )
          v30 = v45[32] << 8;
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          33,
          &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
          (unsigned int)(v30 + v29),
          FirstTrackOfLastSession);
        goto LABEL_70;
      }
      v25 = v45[11] | ((v45[10] | ((v45[9] | (v45[8] << 8)) << 8)) << 8);
      *a4 = v25;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_80:
        if ( !v27 )
        {
          if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 68) & 1) != 0 )
            WPP_SF_(v31[7], 42, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
          *a5 = 0;
          *a6 = 0;
          v8 = WPP_GLOBAL_Control;
          goto LABEL_21;
        }
        if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 68) & 1) != 0 )
          WPP_SF_(v31[7], 36, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
        v9 = CMsftTrackInformation::Init(
               (CMsftTrackInformation *)&v43,
               *(struct IDiscRecorder2Ex **)(v7 + 8),
               LastTrackOfLastSession,
               (enum _IMAPI_READ_TRACK_ADDRESS_TYPE)v25,
               v40);
        if ( v9 < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_11;
          v11 = 37;
          goto LABEL_10;
        }
        v32 = v43;
        v33 = 0;
        if ( (unsigned int)v44 >= 0x21 )
          v33 = v43[32] << 8;
        v34 = v43[2];
        if ( v34 + v33 == LastTrackOfLastSession )
        {
          if ( (v43[7] & 1) != 0 )
          {
            *a5 = v43[15] | ((v43[14] | ((v43[13] | (v43[12] << 8)) << 8)) << 8);
            v36 = v32[19] | ((v32[18] | ((v32[17] | (v32[16] << 8)) << 8)) << 8);
            *a6 = v36;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              WPP_SF_DD(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                40,
                &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
                (unsigned int)*a5,
                v36);
              v8 = WPP_GLOBAL_Control;
            }
            v37 = v32[6];
            if ( (v37 & 0x20) != 0 && (v37 & 0x10) != 0 )
            {
              v38 = (unsigned int)(7 * *a6) >> 5;
              v39 = v38 + *a6;
              *a6 = v39;
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                goto LABEL_24;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                WPP_SF_DD(
                  *((_QWORD *)WPP_GLOBAL_Control + 7),
                  41,
                  &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
                  v38,
                  v39);
                v8 = WPP_GLOBAL_Control;
              }
            }
            goto LABEL_20;
          }
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          {
LABEL_71:
            v9 = -2147220978;
            goto LABEL_21;
          }
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 39, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_71;
          v35 = 0;
          if ( (unsigned int)v44 >= 0x21 )
            v35 = v43[32] << 8;
          WPP_SF_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            38,
            &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
            (unsigned int)(v35 + v34),
            LastTrackOfLastSession);
        }
LABEL_70:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_71;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, v25);
    }
    v31 = WPP_GLOBAL_Control;
    goto LABEL_80;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
    goto LABEL_11;
  v11 = 23;
LABEL_10:
  WPP_SF_(v10[7], v11, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
LABEL_11:
  v9 = TranslateIMAPI2Error((unsigned int)v9);
LABEL_21:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 68) & 1) != 0 )
    WPP_SF_qD(v8[7], 43, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, v7, v9);
LABEL_24:
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)&v43);
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)&v45);
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)&v41);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800134e8  mov     [rsp-38h+arg_18], r9
0x1800134ed  mov     [rsp-38h+arg_10], r8
0x1800134f2  mov     [rsp-38h+arg_0], rcx
0x1800134f7  push    rbp
0x1800134f8  push    rbx
0x1800134f9  push    rsi
0x1800134fa  push    rdi
0x1800134fb  push    r12
0x1800134fd  push    r13
0x1800134ff  push    r14
0x180013501  mov     rbp, rsp
0x180013504  sub     rsp, 70h
0x180013508  xor     edi, edi
0x18001350a  mov     r13, rdx
0x18001350d  mov     [rbp+var_30], rdi
0x180013511  mov     rsi, rcx
0x180013514  mov     [rbp+var_28], rdi
0x180013518  mov     [rbp+var_10], rdi
0x18001351c  mov     [rbp+var_8], rdi
0x180013520  mov     [rbp+var_20], rdi
0x180013524  mov     [rbp+var_18], rdi
0x180013528  mov     r10, cs:WPP_GLOBAL_Control
0x18001352f  lea     rax, WPP_GLOBAL_Control
0x180013536  cmp     r10, rax
0x180013539  jz      short loc_18001355F
0x18001353b  test    byte ptr [r10+44h], 1
0x180013540  jz      short loc_18001355F
0x180013542  mov     r9, rcx
0x180013545  lea     edx, [rdi+16h]
0x180013548  mov     rcx, [r10+38h]
0x18001354c  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180013553  call    WPP_SF_q
0x180013558  mov     r10, cs:WPP_GLOBAL_Control
0x18001355f  test    rsi, rsi
0x180013562  jz      loc_180013C39
0x180013568  cmp     [rsi], rdi
0x18001356b  jz      loc_180013C39
0x180013571  mov     rdx, [rsi+8]; struct IDiscRecorder2Ex *
0x180013575  lea     rcx, [rbp+var_30]; this
0x180013579  call    ?Init@CMsftDiscInformation@@QEAAJPEAUIDiscRecorder2Ex@@@Z; CMsftDiscInformation::Init(IDiscRecorder2Ex *)
0x18001357e  mov     ebx, eax
0x180013580  test    eax, eax
0x180013582  jns     short loc_1800135C5
0x180013584  mov     r10, cs:WPP_GLOBAL_Control
0x18001358b  lea     rax, WPP_GLOBAL_Control
0x180013592  cmp     r10, rax
0x180013595  jz      short loc_1800135BA
0x180013597  test    byte ptr [r10+44h], 1
0x18001359c  jz      short loc_1800135BA
0x18001359e  mov     edx, 17h
0x1800135a3  mov     rcx, [r10+38h]
0x1800135a7  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800135ae  call    WPP_SF_
0x1800135b3  mov     r10, cs:WPP_GLOBAL_Control
0x1800135ba  mov     ecx, ebx
0x1800135bc  call    TranslateIMAPI2Error
0x1800135c1  mov     ebx, eax
0x1800135c3  jmp     short loc_180013644
0x1800135c5  cmp     dword ptr [rbp+var_28], 0Ah
0x1800135c9  mov     ecx, edi
0x1800135cb  mov     rdi, [rbp+var_30]
0x1800135cf  jb      short loc_1800135D8
0x1800135d1  movzx   ecx, byte ptr [rdi+9]
0x1800135d5  shl     ecx, 8
0x1800135d8  movzx   esi, byte ptr [rdi+4]
0x1800135dc  add     esi, ecx
0x1800135de  lea     rcx, [rbp+var_30]; this
0x1800135e2  call    ?get_FirstTrackOfLastSession@CMsftDiscInformation@@QEAAKXZ; CMsftDiscInformation::get_FirstTrackOfLastSession(void)
0x1800135e7  lea     rcx, [rbp+var_30]; this
0x1800135eb  mov     r14d, eax
0x1800135ee  call    ?get_LastTrackOfLastSession@CMsftDiscInformation@@QEAAKXZ; CMsftDiscInformation::get_LastTrackOfLastSession(void)
0x1800135f3  mov     r12d, eax
0x1800135f6  cmp     esi, 0FFh
0x1800135fc  jbe     loc_18001369F
0x180013602  mov     r10, cs:WPP_GLOBAL_Control
0x180013609  lea     rax, WPP_GLOBAL_Control
0x180013610  cmp     r10, rax
0x180013613  jz      short loc_18001363B
0x180013615  test    byte ptr [r10+44h], 1
0x18001361a  jz      short loc_18001363B
0x18001361c  mov     edx, 18h
0x180013621  mov     rcx, [r10+38h]
0x180013625  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001362c  mov     r9d, esi
0x18001362f  call    WPP_SF_d
0x180013634  mov     r10, cs:WPP_GLOBAL_Control
0x18001363b  mov     ebx, 8004020Eh
0x180013640  mov     rsi, [rbp+arg_0]
0x180013644  lea     rax, WPP_GLOBAL_Control
0x18001364b  cmp     r10, rax
0x18001364e  jz      short loc_180013673
0x180013650  test    byte ptr [r10+44h], 1
0x180013655  jz      short loc_180013673
0x180013657  mov     rcx, [r10+38h]
0x18001365b  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180013662  mov     edx, 2Bh ; '+'
0x180013667  mov     dword ptr [rsp+70h+var_50], ebx
0x18001366b  mov     r9, rsi
0x18001366e  call    WPP_SF_qD
0x180013673  lea     rcx, [rbp+var_20]; this
0x180013677  call    ??1CMsftDiscInformation@@QEAA@XZ; CMsftDiscInformation::~CMsftDiscInformation(void)
0x18001367c  lea     rcx, [rbp+var_10]; this
0x180013680  call    ??1CMsftDiscInformation@@QEAA@XZ; CMsftDiscInformation::~CMsftDiscInformation(void)
0x180013685  lea     rcx, [rbp+var_30]; this
0x180013689  call    ??1CMsftDiscInformation@@QEAA@XZ; CMsftDiscInformation::~CMsftDiscInformation(void)
0x18001368e  mov     eax, ebx
0x180013690  add     rsp, 70h
0x180013694  pop     r14
0x180013696  pop     r13
0x180013698  pop     r12
0x18001369a  pop     rdi
0x18001369b  pop     rsi
0x18001369c  pop     rbx
0x18001369d  pop     rbp
0x18001369e  retn
0x18001369f  mov     [r13+0], sil
0x1800136a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136aa  lea     rax, WPP_GLOBAL_Control
0x1800136b1  mov     r13d, 1
0x1800136b7  cmp     rcx, rax
0x1800136ba  jz      loc_1800137D3
0x1800136c0  test    [rcx+44h], r13b
0x1800136c4  jz      short loc_1800136F5
0x1800136c6  movzx   r9d, byte ptr [rdi+2]
0x1800136cb  lea     edx, [r13+18h]
0x1800136cf  mov     rcx, [rcx+38h]
0x1800136d3  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800136da  and     r9d, 3
0x1800136de  mov     dword ptr [rsp+70h+var_50], esi
0x1800136e2  call    WPP_SF_DD
0x1800136e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136ee  lea     rax, WPP_GLOBAL_Control
0x1800136f5  cmp     rcx, rax
0x1800136f8  jz      loc_1800137D3
0x1800136fe  test    [rcx+44h], r13b
0x180013702  jz      short loc_18001372F
0x180013704  mov     rcx, [rcx+38h]
0x180013708  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001370f  mov     edx, 1Ah
0x180013714  mov     dword ptr [rsp+70h+var_50], r12d
0x180013719  mov     r9d, r14d
0x18001371c  call    WPP_SF_DD
0x180013721  mov     rcx, cs:WPP_GLOBAL_Control
0x180013728  lea     rax, WPP_GLOBAL_Control
0x18001372f  cmp     rcx, rax
0x180013732  jz      loc_1800137D3
0x180013738  test    [rcx+44h], r13b
0x18001373c  jz      short loc_18001379D
0x18001373e  movzx   edx, byte ptr [rdi+7]
0x180013742  xor     eax, eax
0x180013744  mov     r8d, edx
0x180013747  shr     r8d, 5
0x18001374b  and     r8d, r13d
0x18001374e  cmp     dword ptr [rbp+var_28], 20h ; ' '
0x180013752  jb      short loc_18001375C
0x180013754  mov     eax, edx
0x180013756  shr     eax, 6
0x180013759  and     eax, r13d
0x18001375c  test    dl, dl
0x18001375e  jns     short loc_18001376B
0x180013760  cmp     dword ptr [rbp+var_28], 10h
0x180013764  jb      short loc_18001376B
0x180013766  mov     r10d, r13d
0x180013769  jmp     short loc_18001376E
0x18001376b  xor     r10d, r10d
0x18001376e  movzx   r9d, byte ptr [rdi+8]
0x180013773  mov     edx, 1Bh
0x180013778  mov     rcx, [rcx+38h]
0x18001377c  mov     [rsp+70h+var_40], r8d
0x180013781  mov     [rsp+70h+var_48], eax
0x180013785  mov     dword ptr [rsp+70h+var_50], r10d
0x18001378a  call    WPP_SF_DDDD
0x18001378f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013796  lea     rax, WPP_GLOBAL_Control
0x18001379d  cmp     rcx, rax
0x1800137a0  jz      short loc_1800137D3
0x1800137a2  test    [rcx+44h], r13b
0x1800137a6  jz      short loc_1800137D3
0x1800137a8  movzx   r9d, byte ptr [rdi+7]
0x1800137ad  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800137b4  mov     rcx, [rcx+38h]
0x1800137b8  mov     eax, r9d
0x1800137bb  shr     eax, 2
0x1800137be  and     r9d, 3
0x1800137c2  and     eax, r13d
0x1800137c5  mov     edx, 1Ch
0x1800137ca  mov     dword ptr [rsp+70h+var_50], eax
0x1800137ce  call    WPP_SF_DD
0x1800137d3  lea     rcx, [rbp+var_30]; this
0x1800137d7  call    ?get_LastPossibleLeadoutStartTimeAsLba@CMsftDiscInformation@@QEAAJXZ; CMsftDiscInformation::get_LastPossibleLeadoutStartTimeAsLba(void)
0x1800137dc  mov     r10, cs:WPP_GLOBAL_Control
0x1800137e3  lea     rdx, WPP_GLOBAL_Control
0x1800137ea  cmp     r10, rdx
0x1800137ed  jz      short loc_180013823
0x1800137ef  test    [r10+44h], r13b
0x1800137f3  jz      short loc_180013823
0x1800137f5  movzx   ecx, byte ptr [rdi+2]
0x1800137f9  mov     edx, 1Dh
0x1800137fe  and     ecx, 3
0x180013801  mov     r9d, esi
0x180013804  mov     [rsp+70h+var_48], ecx
0x180013808  mov     rcx, [r10+38h]
0x18001380c  mov     dword ptr [rsp+70h+var_50], eax; unsigned __int8
0x180013810  call    WPP_SF_DDD
0x180013815  mov     r10, cs:WPP_GLOBAL_Control
0x18001381c  lea     rdx, WPP_GLOBAL_Control
0x180013823  cmp     r12d, 0FFh
0x18001382a  jbe     short loc_180013849
0x18001382c  cmp     r10, rdx
0x18001382f  jz      loc_18001363B
0x180013835  test    [r10+44h], r13b
0x180013839  jz      loc_18001363B
0x18001383f  mov     edx, 1Eh
0x180013844  jmp     loc_180013621
0x180013849  mov     rax, [rbp+arg_10]
0x18001384d  mov     [rax], r12b
0x180013850  mov     al, [rdi+2]
0x180013853  and     al, 3
0x180013855  cmp     al, 2
0x180013857  setb    dil
0x18001385b  cmp     r12d, r13d
0x18001385e  ja      short loc_180013869
0x180013860  test    dil, dil
0x180013863  jnz     loc_1800139BA
0x180013869  cmp     esi, r13d
0x18001386c  jbe     loc_1800139BA
0x180013872  test    dil, dil
0x180013875  jz      short loc_1800138A1
0x180013877  mov     rcx, cs:WPP_GLOBAL_Control
0x18001387e  cmp     rcx, rdx
0x180013881  jz      short loc_18001389E
0x180013883  test    [rcx+44h], r13b
0x180013887  jz      short loc_18001389E
0x180013889  mov     rcx, [rcx+38h]
0x18001388d  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180013894  mov     edx, 1Fh
0x180013899  call    WPP_SF_
0x18001389e  dec     r14d
0x1800138a1  mov     rsi, [rbp+arg_0]
0x1800138a5  lea     rcx, [rbp+var_10]; this
0x1800138a9  mov     r8d, r14d; unsigned int
0x1800138ac  mov     rdx, [rsi+8]; struct IDiscRecorder2Ex *
0x1800138b0  call    ?Init@CMsftTrackInformation@@QEAAJPEAUIDiscRecorder2Ex@@KW4_IMAPI_READ_TRACK_ADDRESS_TYPE@@E@Z; CMsftTrackInformation::Init(IDiscRecorder2Ex *,ulong,_IMAPI_READ_TRACK_ADDRESS_TYPE,uchar)
0x1800138b5  mov     ebx, eax
0x1800138b7  test    eax, eax
0x1800138b9  jns     short loc_1800138E6
0x1800138bb  mov     r10, cs:WPP_GLOBAL_Control
0x1800138c2  lea     rax, WPP_GLOBAL_Control
0x1800138c9  cmp     r10, rax
0x1800138cc  jz      loc_1800135BA
0x1800138d2  test    [r10+44h], r13b
0x1800138d6  jz      loc_1800135BA
0x1800138dc  mov     edx, 20h ; ' '
0x1800138e1  jmp     loc_1800135A3
0x1800138e6  mov     rcx, [rbp+var_10]
0x1800138ea  xor     eax, eax
0x1800138ec  cmp     dword ptr [rbp+var_8], 21h ; '!'
0x1800138f0  jb      short loc_1800138F9
0x1800138f2  movzx   eax, byte ptr [rcx+20h]
0x1800138f6  shl     eax, 8
0x1800138f9  movzx   r8d, byte ptr [rcx+2]
0x1800138fe  add     eax, r8d
0x180013901  cmp     eax, r14d
0x180013904  jz      short loc_18001395D
0x180013906  mov     r10, cs:WPP_GLOBAL_Control
0x18001390d  lea     rax, WPP_GLOBAL_Control
0x180013914  cmp     r10, rax
0x180013917  jz      short loc_180013953
0x180013919  test    [r10+44h], r13b
0x18001391d  jz      short loc_180013953
0x18001391f  xor     eax, eax
0x180013921  cmp     dword ptr [rbp+var_8], 21h ; '!'
0x180013925  jb      short loc_18001392E
0x180013927  movzx   eax, byte ptr [rcx+20h]
0x18001392b  shl     eax, 8
0x18001392e  lea     r9d, [rax+r8]
0x180013932  mov     dword ptr [rsp+70h+var_50], r14d
0x180013937  mov     edx, 21h ; '!'
0x18001393c  mov     rcx, [r10+38h]
0x180013940  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180013947  call    WPP_SF_DD
0x18001394c  mov     r10, cs:WPP_GLOBAL_Control
0x180013953  mov     ebx, 8004020Eh
0x180013958  jmp     loc_180013644
0x18001395d  movzx   eax, byte ptr [rcx+9]
0x180013961  movzx   r9d, byte ptr [rcx+8]
0x180013966  shl     r9d, 8
0x18001396a  or      r9d, eax
0x18001396d  movzx   eax, byte ptr [rcx+0Ah]
0x180013971  shl     r9d, 8
0x180013975  or      r9d, eax
0x180013978  movzx   eax, byte ptr [rcx+0Bh]
0x18001397c  shl     r9d, 8
0x180013980  or      r9d, eax
0x180013983  mov     rax, [rbp+arg_18]
0x180013987  mov     [rax], r9d
0x18001398a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013991  lea     rax, WPP_GLOBAL_Control
0x180013998  cmp     rcx, rax
0x18001399b  jz      short loc_1800139FD
  ... truncated ...
```
