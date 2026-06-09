# MoveToTier(ushort * const,ulong,unsigned __int64,CSxRefPtr<IVolume> &,CSxRefPtr<IFreeSpaceManager> &,ATL::CComPtr<ITieringEngine> &,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 &,__MIDL___MIDL_itf_tieringengine_0000_0000_0010 &,bool &,bool,unsigned __int64)

- ea: `0x18005b594`
- end: `0x18005c28b`
- name: `?MoveToTier@@YAJQEAGK_KAEAV?$CSxRefPtr@UIVolume@@@@AEAV?$CSxRefPtr@UIFreeSpaceManager@@@@AEAV?$CComPtr@UITieringEngine@@@ATL@@AEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@AEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0010@@AEA_N_N_K@Z`
- size: `3319`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, void *Source, __int64, __int64, char, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18005c2a0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001f22c`
- `0x180038c3c`
- `0x180046494`
- `0x18004b73c`
- `0x18005b31c`
- `0x18005b594`
- `0x18005ef10`
- `0x18005f3d0`
- `0x18005f45c`
- `0x18005f4e8`
- `0x180066d54`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18005b6fa`
- `msvcrt!memcpy_s` at `0x18005b6fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005b9bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005b9bd`

## string_xrefs

- `0x18005b65f`: `MoveToTier`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MoveToTier(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *Source,
        _QWORD *a8,
        _BYTE *a9,
        unsigned __int8 a10,
        ULONGLONG a11)
{
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // r15
  _QWORD *v13; // r8
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rdi
  CSxGlobalTracer *v16; // r10
  __int64 v17; // r13
  __int64 v18; // rbx
  unsigned __int64 v19; // rcx
  __int64 v20; // rsi
  int v21; // r15d
  unsigned int v22; // edx
  int v23; // edi
  __int64 v24; // r8
  int v25; // eax
  __int64 v26; // r8
  int v27; // eax
  __int64 v28; // r8
  int v29; // eax
  unsigned int v30; // edi
  int v31; // edi
  __int16 v32; // ax
  unsigned int v33; // edi
  _QWORD *v34; // rbx
  _QWORD *v35; // r8
  unsigned __int64 v36; // rdi
  unsigned __int64 v37; // r13
  __int64 v39; // [rsp+20h] [rbp-7A8h]
  __int64 v40; // [rsp+40h] [rbp-788h]
  char v41; // [rsp+50h] [rbp-778h]
  unsigned __int64 v42; // [rsp+58h] [rbp-770h] BYREF
  unsigned int v43; // [rsp+60h] [rbp-768h] BYREF
  __int64 v44; // [rsp+68h] [rbp-760h]
  __int16 v45; // [rsp+70h] [rbp-758h]
  __int64 v46; // [rsp+78h] [rbp-750h] BYREF
  _BYTE *v47; // [rsp+80h] [rbp-748h]
  _QWORD *v48; // [rsp+88h] [rbp-740h]
  unsigned __int64 v49; // [rsp+90h] [rbp-738h]
  __int16 v50; // [rsp+98h] [rbp-730h]
  int v51; // [rsp+9Ch] [rbp-72Ch]
  _WORD *v52; // [rsp+A0h] [rbp-728h]
  _QWORD *v53; // [rsp+A8h] [rbp-720h]
  _QWORD *v54; // [rsp+B0h] [rbp-718h]
  unsigned __int64 v55; // [rsp+B8h] [rbp-710h]
  unsigned int v56; // [rsp+C0h] [rbp-708h]
  _QWORD *v57; // [rsp+C8h] [rbp-700h]
  _QWORD *v58; // [rsp+D0h] [rbp-6F8h]
  unsigned int v59; // [rsp+D8h] [rbp-6F0h]
  _QWORD *v60; // [rsp+E0h] [rbp-6E8h]
  __int64 v61; // [rsp+E8h] [rbp-6E0h]
  _QWORD *v62; // [rsp+F0h] [rbp-6D8h]
  _QWORD *v63; // [rsp+F8h] [rbp-6D0h]
  __int128 v64; // [rsp+100h] [rbp-6C8h] BYREF
  __int64 v65; // [rsp+110h] [rbp-6B8h]
  int v66; // [rsp+120h] [rbp-6A8h] BYREF
  __int16 v67; // [rsp+124h] [rbp-6A4h]
  __int16 v68; // [rsp+126h] [rbp-6A2h]
  __int64 v69; // [rsp+158h] [rbp-670h]
  _QWORD *v70; // [rsp+160h] [rbp-668h]
  _QWORD *v71; // [rsp+168h] [rbp-660h]
  __int128 Destination; // [rsp+170h] [rbp-658h] BYREF
  _QWORD v73[192]; // [rsp+180h] [rbp-648h] BYREF

  v53 = a4;
  v11 = a2;
  v56 = a2;
  v61 = a1;
  v63 = a6;
  v62 = a8;
  v69 = a1;
  v59 = a2;
  v70 = a4;
  v54 = a5;
  v71 = a6;
  v48 = Source;
  v60 = a8;
  v47 = a9;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v66, "MoveToTier", 145, 1);
  v46 = 0;
  v49 = v11;
  v58 = Source + 2;
  v12 = Source[2] / v11;
  v44 = v12;
  v43 = 64;
  v52 = Source + 4;
  v45 = Source[4] & 0x10;
  v50 = v45;
  v64 = 0;
  v65 = 0;
  *a9 = 0;
  Destination = 0;
  memcpy_s(&Destination, 0x10u, Source, 0x10u);
  v13 = Source + 3;
  v57 = Source + 3;
  if ( Source[3] == -1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v13 = v57;
  }
  v14 = *v13 % v11;
  v15 = *v13 / v11;
  v55 = v15;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_8953dd03939f3641260d1d1f678e0bff_Traceguids, a10);
      v16 = WPP_GLOBAL_Control;
      v13 = v57;
    }
    if ( v16 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x8000000) != 0 )
    {
      WPP_SF_iiiiDD(
        *((_QWORD *)v16 + 2),
        v14,
        v13,
        *((_QWORD *)&Destination + 1),
        Destination,
        *v58,
        *v13,
        (unsigned __int16)*v52,
        *((_DWORD *)Source + 9));
      v16 = WPP_GLOBAL_Control;
    }
  }
  v17 = *((_QWORD *)&v64 + 1);
  v18 = v64;
  v19 = v49;
  while ( v15 )
  {
    v20 = v15;
    v42 = v15;
    v41 = 0;
    if ( v16 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x8000000) != 0 )
    {
      WPP_SF_i(*((_QWORD *)v16 + 2), 12, WPP_8953dd03939f3641260d1d1f678e0bff_Traceguids, v55);
      v20 = v42;
      v19 = v49;
    }
    *v52 = 8;
    if ( v20 * v19 > 0x100000 )
    {
      v20 = 0x100000 / v56;
      v42 = v20;
    }
    LODWORD(v39) = 64;
    v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, unsigned __int64, __int64, __int64, unsigned __int64 *, unsigned int *, _QWORD *))(*(_QWORD *)*v53 + 288LL))(
            *v53,
            v48,
            v12,
            v20,
            v39,
            &v42,
            &v43,
            v73);
    if ( v21 >= 0 )
    {
      v20 = 0;
      v22 = 0;
      if ( !v43 )
        goto LABEL_84;
      do
        v20 += v73[3 * v22++ + 1];
      while ( v22 < v43 );
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        HIDWORD(v39) = HIDWORD(v55);
        WPP_SF_II(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_8953dd03939f3641260d1d1f678e0bff_Traceguids);
      }
      v43 = 0;
      v42 = v20;
    }
    if ( !v20 )
    {
LABEL_84:
      if ( v42 )
      {
        *v52 = 2;
      }
      else
      {
        *v52 = 32;
        v42 = v55;
      }
      goto LABEL_87;
    }
    v23 = 0;
    if ( a3 )
    {
      if ( a3 == 1 )
      {
        if ( *((_DWORD *)v48 + 9) != 2 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        *v62 += v20 * v49;
      }
    }
    else
    {
      if ( *((_DWORD *)v48 + 9) != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v60[1] += v20 * v49;
    }
    while ( 1 )
    {
      if ( GetTickCount64() > a11 )
      {
        *v47 = 1;
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_iiiiii(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            v24,
            *((_QWORD *)&Destination + 1),
            Destination,
            v44,
            v46,
            v42,
            v20);
        }
        v31 = -2147023436;
        v32 = 258;
LABEL_82:
        v66 = v31;
        goto LABEL_83;
      }
      v25 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(*(_QWORD *)*v54 + 40LL))(
              *v54,
              *((unsigned int *)v48 + 9),
              v20,
              &v46);
      v21 = v25;
      if ( v25 == 1 )
      {
        v21 = -2147024882;
        v41 = 1;
        goto LABEL_87;
      }
      if ( v25 < 0 )
        goto LABEL_62;
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_iiiiii(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          v26,
          *((_QWORD *)&Destination + 1),
          Destination,
          v44,
          v46,
          v42,
          v20);
      }
      v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, unsigned __int64, __int64))(*(_QWORD *)*v53 + 136LL))(
              *v53,
              v48,
              v44,
              v42,
              v46);
      v21 = v27;
      if ( v27 != 1 )
        break;
      v29 = v23;
      v30 = v23 + 1;
      v51 = v30;
      if ( v29 == 20 )
      {
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_iiiiii(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            v28,
            *((_QWORD *)&Destination + 1),
            Destination,
            v44,
            v46,
            v42,
            v20);
        }
        v31 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v54 + 24LL))(*v54);
        v66 = v31;
        v32 = 304;
        if ( v31 < 0 )
          goto LABEL_83;
        v67 = 304;
        v23 = v51;
      }
      else
      {
        if ( v30 > 0x14 )
        {
          v21 = -2147467259;
          if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
          {
            WPP_SF_iiiiii(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              v28,
              *((_QWORD *)&Destination + 1),
              Destination,
              v44,
              v46,
              v42,
              v20);
          }
          goto LABEL_87;
        }
        v23 = v30 + 1;
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_iiiiii(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            v28,
            *((_QWORD *)&Destination + 1),
            Destination,
            v44,
            v46,
            v42,
            v20);
        }
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v54 + 64LL))(*v54, v46, v20);
      }
    }
    if ( v27 == -2147023728 )
    {
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_iiiiii(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          v28,
          *((_QWORD *)&Destination + 1),
          Destination,
          v44,
          v46,
          v42,
          v20);
      }
LABEL_76:
      *v52 = 32;
      goto LABEL_87;
    }
    if ( v27 == -805306077 )
    {
      if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_iiiiii(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          v28,
          *((_QWORD *)&Destination + 1),
          Destination,
          v44,
          v46,
          v42,
          v20);
      }
      *v47 = 1;
      v31 = -805306077;
      v32 = 365;
      goto LABEL_82;
    }
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_8953dd03939f3641260d1d1f678e0bff_Traceguids);
    }
LABEL_62:
    if ( v21 < 0 )
    {
      if ( v21 != -2147023728 )
        goto LABEL_87;
      goto LABEL_76;
    }
    if ( a3 )
    {
      if ( a3 == 1 )
        v60[2] += v20 * v49;
    }
    else
    {
      v60[3] += v20 * v49;
    }
    v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v54 + 64LL))(*v54, v46, v20);
    v33 = 0;
    if ( v43 )
    {
      v34 = v54;
      do
      {
        v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v34 + 72LL))(
                *v34,
                v73[3 * v33],
                v73[3 * v33 + 1]);
        ++v33;
      }
      while ( v33 < v43 );
      v18 = v64;
    }
    *v52 = 2;
LABEL_87:
    *v58 = v44 * v49;
    *v57 = v42 * v49;
    if ( *v52 == 8 )
    {
      *v47 = 1;
    }
    else
    {
      if ( *v52 == 32 )
        *v47 = 1;
      if ( !v45 )
      {
        try
        {
          std::vector<__MIDL___MIDL_itf_tieringengine_0000_0000_0005,com_allocator<__MIDL___MIDL_itf_tieringengine_0000_0000_0005>>::push_back(
            &v64,
            v48);
        }
        catch ( std::bad_alloc )
        {
          v51 = -2147024882;
          v17 = *((_QWORD *)&v64 + 1);
          v18 = v64;
          v21 = -2147024882;
          v56 = v59;
          v61 = v69;
          v35 = v70;
          v53 = v70;
          v45 = v50;
          goto LABEL_95;
        }
        v17 = *((_QWORD *)&v64 + 1);
        v18 = v64;
      }
    }
    v35 = v53;
LABEL_95:
    v14 = 0xCCCCCCCCCCCCCCCDuLL;
    if ( *v47 )
    {
      v36 = 0xCCCCCCCCCCCCCCCDuLL * ((v17 - v18) >> 3);
      if ( v36 >= 0x2710 || v36 && v41 )
      {
        (*(void (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*v35 + 248LL))(*v35, 0xCCCCCCCCCCCCCCCDuLL);
        v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(*(_QWORD *)*v63 + 112LL))(
                *v63,
                v61,
                (unsigned int)v36,
                v18);
        if ( v18 != v17 )
          v17 = v18;
        *((_QWORD *)&v64 + 1) = v17;
      }
    }
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      LODWORD(v40) = *((_DWORD *)v48 + 9);
      WPP_SF_diiiiD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        v35,
        (unsigned int)v21,
        *((_QWORD *)&Destination + 1),
        Destination,
        *v58,
        *v57,
        v40);
    }
    LOBYTE(v14) = v41;
    v12 = v44;
    v15 = v55;
    if ( !v41 )
    {
      v12 = v42 + v44;
      v44 += v42;
      v15 = v55 - v42;
      v55 -= v42;
    }
    v19 = v49;
    *v58 = v12 * v49;
    *v57 = v15 * v19;
    if ( v41 )
    {
      v31 = -1996488673;
      v32 = 503;
      goto LABEL_82;
    }
    v16 = WPP_GLOBAL_Control;
  }
  if ( v16 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x8000000) != 0 )
    WPP_SF_i(*((_QWORD *)v16 + 2), 23, WPP_8953dd03939f3641260d1d1f678e0bff_Traceguids, 0);
  if ( *v47 && (v37 = 0xCCCCCCCCCCCCCCCDuLL * ((v17 - v18) >> 3)) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, unsigned __int64))(*(_QWORD *)*v53 + 248LL))(*v53, v14);
    v31 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(*(_QWORD *)*v71 + 112LL))(
            *v71,
            v61,
            (unsigned int)v37,
            v18);
    v66 = v31;
    v32 = 515;
    if ( v31 < 0 )
LABEL_83:
      v68 = v32;
    else
      v67 = 515;
  }
  else
  {
    v31 = v66;
  }
  std::vector<__MIDL___MIDL_itf_tieringengine_0000_0000_0005,com_allocator<__MIDL___MIDL_itf_tieringengine_0000_0000_0005>>::~vector<__MIDL___MIDL_itf_tieringengine_0000_0000_0005,com_allocator<__MIDL___MIDL_itf_tieringengine_0000_0000_0005>>((__int64)&v64);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v66);
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x18005b594  mov     [rsp+arg_10], r8
0x18005b599  push    rbx
0x18005b59a  push    rsi
0x18005b59b  push    rdi
0x18005b59c  push    r12
0x18005b59e  push    r13
0x18005b5a0  push    r14
0x18005b5a2  push    r15
0x18005b5a4  sub     rsp, 790h
0x18005b5ab  mov     rax, cs:__security_cookie
0x18005b5b2  xor     rax, rsp
0x18005b5b5  mov     [rsp+7C8h+var_48], rax
0x18005b5bd  mov     rax, r9
0x18005b5c0  mov     [rsp+7C8h+var_720], rax
0x18005b5c8  mov     ebx, edx
0x18005b5ca  mov     [rsp+7C8h+var_708], ebx
0x18005b5d1  mov     rdx, rcx
0x18005b5d4  mov     [rsp+7C8h+var_6E0], rcx
0x18005b5dc  mov     r8, [rsp+7C8h+arg_28]
0x18005b5e4  mov     [rsp+7C8h+var_6D0], r8
0x18005b5ec  mov     rcx, [rsp+7C8h+arg_38]
0x18005b5f4  mov     [rsp+7C8h+var_6D8], rcx
0x18005b5fc  mov     [rsp+7C8h+var_670], rdx
0x18005b604  mov     [rsp+7C8h+var_6F0], ebx
0x18005b60b  mov     [rsp+7C8h+var_668], rax
0x18005b613  mov     rax, [rsp+7C8h+arg_20]
0x18005b61b  mov     [rsp+7C8h+var_718], rax
0x18005b623  mov     [rsp+7C8h+var_660], r8
0x18005b62b  mov     r13, [rsp+7C8h+Source]
0x18005b633  mov     [rsp+7C8h+var_740], r13
0x18005b63b  mov     [rsp+7C8h+var_6E8], rcx
0x18005b643  mov     rdi, [rsp+7C8h+arg_40]
0x18005b64b  mov     [rsp+7C8h+var_748], rdi
0x18005b653  mov     r9d, 1; unsigned __int16
0x18005b659  mov     r8d, 91h; unsigned __int16
0x18005b65f  lea     rdx, aMovetotier; "MoveToTier"
0x18005b666  lea     rcx, [rsp+7C8h+var_6A8]; this
0x18005b66e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005b673  nop
0x18005b674  xor     r14d, r14d
0x18005b677  mov     [rsp+7C8h+var_750], r14
0x18005b67c  mov     [rsp+7C8h+var_738], rbx
0x18005b684  lea     rax, [r13+10h]
0x18005b688  mov     [rsp+7C8h+var_6F8], rax
0x18005b690  xor     edx, edx
0x18005b692  mov     rax, [rax]
0x18005b695  div     rbx
0x18005b698  mov     r15, rax
0x18005b69b  mov     [rsp+7C8h+var_760], rax
0x18005b6a0  mov     [rsp+7C8h+var_768], 40h ; '@'
0x18005b6a8  lea     rax, [r13+20h]
0x18005b6ac  mov     [rsp+7C8h+var_728], rax
0x18005b6b4  movzx   eax, word ptr [rax]
0x18005b6b7  lea     ecx, [r14+10h]
0x18005b6bb  and     ax, cx
0x18005b6be  mov     [rsp+7C8h+var_758], ax
0x18005b6c3  mov     [rsp+7C8h+var_730], ax
0x18005b6cb  xorps   xmm0, xmm0
0x18005b6ce  movdqu  [rsp+7C8h+var_6C8], xmm0
0x18005b6d7  mov     [rsp+7C8h+var_6B8], r14
0x18005b6df  mov     [rdi], r14b
0x18005b6e2  movups  [rsp+7C8h+Destination], xmm0
0x18005b6ea  mov     r9d, ecx; SourceSize
0x18005b6ed  mov     r8, r13; Source
0x18005b6f0  mov     edx, ecx; DestinationSize
0x18005b6f2  lea     rcx, [rsp+7C8h+Destination]; Destination
0x18005b6fa  call    cs:__imp_memcpy_s
0x18005b700  lea     r8, [r13+18h]
0x18005b704  mov     [rsp+7C8h+var_700], r8
0x18005b70c  cmp     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x18005b710  jnz     short loc_18005B71F
0x18005b712  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005b717  mov     r8, [rsp+7C8h+var_700]
0x18005b71f  xor     edx, edx
0x18005b721  mov     rax, [r8]
0x18005b724  div     rbx
0x18005b727  mov     rdi, rax
0x18005b72a  mov     [rsp+7C8h+var_710], rax
0x18005b732  lea     rsi, WPP_GLOBAL_Control
0x18005b739  mov     r10, cs:WPP_GLOBAL_Control
0x18005b740  mov     r12d, 8000000h
0x18005b746  cmp     r10, rsi
0x18005b749  jz      loc_18005B7E1
0x18005b74f  test    [r10+1Ch], r12d
0x18005b753  jz      short loc_18005B782
0x18005b755  movzx   r9d, [rsp+7C8h+arg_48]
0x18005b75e  mov     edx, 0Ah
0x18005b763  lea     r8, WPP_8953dd03939f3641260d1d1f678e0bff_Traceguids
0x18005b76a  mov     rcx, [r10+10h]
0x18005b76e  call    WPP_SF_d
0x18005b773  mov     r10, cs:WPP_GLOBAL_Control
0x18005b77a  mov     r8, [rsp+7C8h+var_700]
0x18005b782  cmp     r10, rsi
0x18005b785  jz      short loc_18005B7E1
0x18005b787  test    [r10+1Ch], r12d
0x18005b78b  jz      short loc_18005B7E1
0x18005b78d  mov     rax, [rsp+7C8h+var_728]
0x18005b795  movzx   ecx, word ptr [rax]
0x18005b798  mov     eax, [r13+24h]
0x18005b79c  mov     dword ptr [rsp+7C8h+var_788], eax
0x18005b7a0  mov     dword ptr [rsp+7C8h+var_790], ecx
0x18005b7a4  mov     rax, [r8]
0x18005b7a7  mov     [rsp+7C8h+var_798], rax
0x18005b7ac  mov     rax, [rsp+7C8h+var_6F8]
0x18005b7b4  mov     rax, [rax]
0x18005b7b7  mov     [rsp+7C8h+var_7A0], rax
0x18005b7bc  mov     rax, qword ptr [rsp+7C8h+Destination]
0x18005b7c4  mov     [rsp+7C8h+var_7A8], rax
0x18005b7c9  mov     r9, qword ptr [rsp+7C8h+Destination+8]
0x18005b7d1  mov     rcx, [r10+10h]
0x18005b7d5  call    WPP_SF_iiiiDD
0x18005b7da  mov     r10, cs:WPP_GLOBAL_Control
0x18005b7e1  mov     r13, qword ptr [rsp+7C8h+var_6C8+8]
0x18005b7e9  mov     rbx, qword ptr [rsp+7C8h+var_6C8]
0x18005b7f1  mov     rcx, [rsp+7C8h+var_738]
0x18005b7f9  test    rdi, rdi
0x18005b7fc  jz      loc_18005C19B
0x18005b802  mov     rsi, rdi
0x18005b805  mov     [rsp+7C8h+var_770], rdi
0x18005b80a  mov     [rsp+7C8h+var_778], r14b
0x18005b80f  lea     rdi, WPP_GLOBAL_Control
0x18005b816  cmp     r10, rdi
0x18005b819  jz      short loc_18005B84B
0x18005b81b  test    [r10+1Ch], r12d
0x18005b81f  jz      short loc_18005B84B
0x18005b821  mov     edx, 0Ch
0x18005b826  mov     r9, [rsp+7C8h+var_710]
0x18005b82e  lea     r8, WPP_8953dd03939f3641260d1d1f678e0bff_Traceguids
0x18005b835  mov     rcx, [r10+10h]
0x18005b839  call    WPP_SF_i
0x18005b83e  mov     rsi, [rsp+7C8h+var_770]
0x18005b843  mov     rcx, [rsp+7C8h+var_738]
0x18005b84b  mov     rax, [rsp+7C8h+var_728]
0x18005b853  mov     word ptr [rax], 8
0x18005b858  mov     rax, rcx
0x18005b85b  imul    rax, rsi
0x18005b85f  cmp     rax, 100000h
0x18005b865  jbe     short loc_18005B87C
0x18005b867  xor     edx, edx
0x18005b869  mov     eax, 100000h
0x18005b86e  div     [rsp+7C8h+var_708]
0x18005b875  mov     esi, eax
0x18005b877  mov     [rsp+7C8h+var_770], rsi
0x18005b87c  mov     rcx, [rsp+7C8h+var_720]
0x18005b884  mov     rcx, [rcx]
0x18005b887  mov     rax, [rcx]
0x18005b88a  lea     rdx, [rsp+7C8h+var_648]
0x18005b892  mov     [rsp+7C8h+var_790], rdx
0x18005b897  lea     rdx, [rsp+7C8h+var_768]
0x18005b89c  mov     [rsp+7C8h+var_798], rdx
0x18005b8a1  lea     rdx, [rsp+7C8h+var_770]
0x18005b8a6  mov     [rsp+7C8h+var_7A0], rdx
0x18005b8ab  mov     dword ptr [rsp+7C8h+var_7A8], 40h ; '@'
0x18005b8b3  mov     r9, rsi
0x18005b8b6  mov     r8, r15
0x18005b8b9  mov     rdx, [rsp+7C8h+var_740]
0x18005b8c1  mov     rax, [rax+120h]
0x18005b8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b8cd  mov     r15d, eax
0x18005b8d0  test    eax, eax
0x18005b8d2  jns     short loc_18005B919
0x18005b8d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b8db  cmp     rcx, rdi
0x18005b8de  jz      short loc_18005B90D
0x18005b8e0  test    [rcx+1Ch], r12d
0x18005b8e4  jz      short loc_18005B90D
0x18005b8e6  mov     edx, 0Dh
0x18005b8eb  mov     rax, [rsp+7C8h+var_710]
0x18005b8f3  mov     [rsp+7C8h+var_7A8], rax
0x18005b8f8  mov     r9, [rsp+7C8h+var_760]
0x18005b8fd  lea     r8, WPP_8953dd03939f3641260d1d1f678e0bff_Traceguids
0x18005b904  mov     rcx, [rcx+10h]
0x18005b908  call    WPP_SF_II
0x18005b90d  mov     [rsp+7C8h+var_768], r14d
0x18005b912  mov     [rsp+7C8h+var_770], rsi
0x18005b917  jmp     short loc_18005B940
0x18005b919  mov     rsi, r14
0x18005b91c  mov     edx, r14d
0x18005b91f  cmp     [rsp+7C8h+var_768], r14d
0x18005b924  jbe     loc_18005BF0B
0x18005b92a  mov     eax, edx
0x18005b92c  lea     rcx, [rax+rax*2]
0x18005b930  add     rsi, [rsp+rcx*8+7C8h+var_640]
0x18005b938  inc     edx
0x18005b93a  cmp     edx, [rsp+7C8h+var_768]
0x18005b93e  jb      short loc_18005B92A
0x18005b940  test    rsi, rsi
0x18005b943  jz      loc_18005BF0B
0x18005b949  mov     edi, r14d
0x18005b94c  mov     rax, [rsp+7C8h+arg_10]
0x18005b954  test    rax, rax
0x18005b957  jnz     short loc_18005B986
0x18005b959  mov     rax, [rsp+7C8h+var_740]
0x18005b961  cmp     dword ptr [rax+24h], 1
0x18005b965  jz      short loc_18005B96C
0x18005b967  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005b96c  mov     rax, [rsp+7C8h+var_738]
0x18005b974  imul    rax, rsi
0x18005b978  mov     rcx, [rsp+7C8h+var_6E8]
0x18005b980  add     [rcx+8], rax
0x18005b984  jmp     short loc_18005B9B6
0x18005b986  cmp     rax, 1
0x18005b98a  jnz     short loc_18005B9B6
0x18005b98c  mov     rax, [rsp+7C8h+var_740]
0x18005b994  cmp     dword ptr [rax+24h], 2
0x18005b998  jz      short loc_18005B99F
0x18005b99a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005b99f  mov     rax, [rsp+7C8h+var_738]
0x18005b9a7  imul    rax, rsi
0x18005b9ab  mov     rcx, [rsp+7C8h+var_6D8]
0x18005b9b3  add     [rcx], rax
0x18005b9b6  lea     r15, WPP_GLOBAL_Control
0x18005b9bd  call    cs:__imp_GetTickCount64
0x18005b9c3  cmp     rax, [rsp+7C8h+arg_50]
0x18005b9cb  ja      loc_18005BE8A
0x18005b9d1  mov     rax, [rsp+7C8h+var_718]
0x18005b9d9  mov     rcx, [rax]
0x18005b9dc  mov     rax, [rcx]
0x18005b9df  lea     r9, [rsp+7C8h+var_750]
0x18005b9e4  mov     r8, rsi
0x18005b9e7  mov     rdx, [rsp+7C8h+var_740]
0x18005b9ef  mov     edx, [rdx+24h]
0x18005b9f2  mov     rax, [rax+28h]
0x18005b9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9fb  mov     r15d, eax
0x18005b9fe  cmp     eax, 1
0x18005ba01  jz      loc_18005BE7D
0x18005ba07  test    eax, eax
0x18005ba09  js      loc_18005BD1B
0x18005ba0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ba16  lea     rax, WPP_GLOBAL_Control
0x18005ba1d  cmp     rcx, rax
0x18005ba20  jz      short loc_18005BA6E
0x18005ba22  test    [rcx+1Ch], r12d
0x18005ba26  jz      short loc_18005BA6E
0x18005ba28  mov     edx, 0Fh
0x18005ba2d  mov     [rsp+7C8h+var_788], rsi
0x18005ba32  mov     rax, [rsp+7C8h+var_770]
0x18005ba37  mov     [rsp+7C8h+var_790], rax
0x18005ba3c  mov     rax, [rsp+7C8h+var_750]
0x18005ba41  mov     [rsp+7C8h+var_798], rax
0x18005ba46  mov     rax, [rsp+7C8h+var_760]
0x18005ba4b  mov     [rsp+7C8h+var_7A0], rax
0x18005ba50  mov     rax, qword ptr [rsp+7C8h+Destination]
0x18005ba58  mov     [rsp+7C8h+var_7A8], rax
0x18005ba5d  mov     r9, qword ptr [rsp+7C8h+Destination+8]
0x18005ba65  mov     rcx, [rcx+10h]
0x18005ba69  call    WPP_SF_iiiiii
0x18005ba6e  mov     rax, [rsp+7C8h+var_720]
0x18005ba76  mov     rcx, [rax]
0x18005ba79  mov     rdx, [rsp+7C8h+var_750]
0x18005ba7e  mov     rax, [rcx]
0x18005ba81  mov     [rsp+7C8h+var_7A8], rdx
0x18005ba86  mov     r9, [rsp+7C8h+var_770]
0x18005ba8b  mov     r8, [rsp+7C8h+var_760]
0x18005ba90  mov     rdx, [rsp+7C8h+var_740]
0x18005ba98  mov     rax, [rax+88h]
0x18005ba9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005baa4  mov     r15d, eax
0x18005baa7  cmp     eax, 1
0x18005baaa  jnz     loc_18005BC62
0x18005bab0  mov     eax, edi
0x18005bab2  inc     edi
0x18005bab4  mov     [rsp+7C8h+var_72C], edi
0x18005babb  cmp     eax, 14h
0x18005babe  jnz     loc_18005BB62
0x18005bac4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bacb  lea     r15, WPP_GLOBAL_Control
0x18005bad2  cmp     rcx, r15
0x18005bad5  jz      short loc_18005BB21
0x18005bad7  test    [rcx+1Ch], r12d
0x18005badb  jz      short loc_18005BB21
0x18005badd  lea     edx, [rax-4]
0x18005bae0  mov     [rsp+7C8h+var_788], rsi
0x18005bae5  mov     rax, [rsp+7C8h+var_770]
0x18005baea  mov     [rsp+7C8h+var_790], rax
0x18005baef  mov     rax, [rsp+7C8h+var_750]
0x18005baf4  mov     [rsp+7C8h+var_798], rax
0x18005baf9  mov     rax, [rsp+7C8h+var_760]
0x18005bafe  mov     [rsp+7C8h+var_7A0], rax
0x18005bb03  mov     rax, qword ptr [rsp+7C8h+Destination]
0x18005bb0b  mov     [rsp+7C8h+var_7A8], rax
0x18005bb10  mov     r9, qword ptr [rsp+7C8h+Destination+8]
0x18005bb18  mov     rcx, [rcx+10h]
0x18005bb1c  call    WPP_SF_iiiiii
0x18005bb21  mov     rax, [rsp+7C8h+var_718]
0x18005bb29  mov     rcx, [rax]
0x18005bb2c  mov     rax, [rcx]
0x18005bb2f  mov     rax, [rax+18h]
0x18005bb33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb38  mov     edi, eax
0x18005bb3a  mov     [rsp+7C8h+var_6A8], eax
0x18005bb41  test    eax, eax
0x18005bb43  mov     eax, 130h
0x18005bb48  js      loc_18005BEFE
0x18005bb4e  mov     [rsp+7C8h+var_6A4], ax
0x18005bb56  mov     edi, [rsp+7C8h+var_72C]
0x18005bb5d  jmp     loc_18005B9BD
0x18005bb62  cmp     edi, 14h
0x18005bb65  ja      loc_18005BBF0
  ... truncated ...
```
