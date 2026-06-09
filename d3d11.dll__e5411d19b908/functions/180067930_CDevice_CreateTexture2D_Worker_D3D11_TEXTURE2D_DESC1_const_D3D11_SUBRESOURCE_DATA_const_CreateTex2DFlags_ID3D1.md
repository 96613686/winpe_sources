# CDevice::CreateTexture2D_Worker(D3D11_TEXTURE2D_DESC1 const *,D3D11_SUBRESOURCE_DATA const *,CreateTex2DFlags,ID3D11Texture2D1 * *,SD3D11SharedResourceCreationArgs *,ID3D11LayeredUseCounted *)

- ea: `0x180067930`
- end: `0x1800683f8`
- name: `?CreateTexture2D_Worker@CDevice@@IEAAJPEBUD3D11_TEXTURE2D_DESC1@@PEBUD3D11_SUBRESOURCE_DATA@@W4CreateTex2DFlags@@PEAPEAUID3D11Texture2D1@@PEAUSD3D11SharedResourceCreationArgs@@PEAUID3D11LayeredUseCounted@@@Z`
- size: `2760`
- prototype: ``
- caller_count: `5`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1800131f4`
- `0x180067640`
- `0x1800677e0`
- `0x180067820`
- `0x1800c2bb0`

## callees

- `0x18001a130`
- `0x18001fbd0`
- `0x1800252d8`
- `0x18002e4d0`
- `0x18003f524`
- `0x18004cbe8`
- `0x180050910`
- `0x180067930`
- `0x180074d78`
- `0x180087f4c`
- `0x18008b38c`
- `0x180099980`
- `0x18009aac0`
- `0x18009c0c8`
- `0x1800a9d20`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x1800682c5`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x1800682c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDevice::CreateTexture2D_Worker(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        char a4,
        _QWORD *a5,
        __int64 a6)
{
  __int128 *v7; // rsi
  CDevice *v8; // rbx
  int v9; // r15d
  int v10; // edi
  enum D3D11_TILED_RESOURCES_TIER v11; // eax
  char v12; // r9
  char v13; // r10
  int v14; // eax
  struct IErrorInfo *v15; // r8
  bool v16; // r9
  __int64 result; // rax
  bool v18; // r15
  unsigned int PrimaryVidPnSourceId; // r10d
  __int64 v20; // r13
  int v21; // eax
  int v22; // edx
  int v23; // ecx
  int v24; // edi
  int DriverDDIVersion; // eax
  __int64 v26; // r9
  int v27; // ecx
  int v28; // eax
  int v29; // edx
  int v30; // r8d
  int v31; // eax
  struct IErrorInfo *v32; // r8
  bool v33; // r9
  _OWORD *v34; // r8
  __int128 v35; // xmm1
  __int128 v36; // xmm2
  __m128i v37; // xmm0
  int v38; // eax
  int v39; // ecx
  bool v40; // dl
  bool v41; // al
  __int64 RequirementsTable; // rax
  _QWORD *v43; // r12
  CD3D11TelemetryHelper *v44; // rcx
  int v45; // edi
  __int64 v46; // r15
  __int64 v47; // rdi
  int i; // r8d
  bool v49; // dl
  bool v50; // [rsp+80h] [rbp-2E8h] BYREF
  bool v51; // [rsp+81h] [rbp-2E7h]
  char v52[2]; // [rsp+82h] [rbp-2E6h] BYREF
  int v53; // [rsp+84h] [rbp-2E4h]
  int v54; // [rsp+88h] [rbp-2E0h] BYREF
  int v55; // [rsp+8Ch] [rbp-2DCh] BYREF
  int v56; // [rsp+90h] [rbp-2D8h]
  unsigned int v57[2]; // [rsp+98h] [rbp-2D0h]
  int v58; // [rsp+A0h] [rbp-2C8h] BYREF
  int v59; // [rsp+A4h] [rbp-2C4h]
  int v60; // [rsp+A8h] [rbp-2C0h]
  __int64 v61; // [rsp+B0h] [rbp-2B8h]
  _QWORD *v62; // [rsp+B8h] [rbp-2B0h]
  _QWORD v63[2]; // [rsp+C0h] [rbp-2A8h] BYREF
  __int128 v64; // [rsp+D0h] [rbp-298h]
  bool *v65; // [rsp+E0h] [rbp-288h]
  __int64 v66; // [rsp+E8h] [rbp-280h]
  _OWORD *v67; // [rsp+F0h] [rbp-278h]
  char v68; // [rsp+F8h] [rbp-270h]
  int v69; // [rsp+F9h] [rbp-26Fh]
  __int16 v70; // [rsp+FDh] [rbp-26Bh]
  char v71; // [rsp+FFh] [rbp-269h]
  __int128 *v72; // [rsp+100h] [rbp-268h]
  __int64 v73; // [rsp+108h] [rbp-260h]
  _OWORD *v74; // [rsp+110h] [rbp-258h]
  __int64 v75; // [rsp+118h] [rbp-250h]
  __int64 v76; // [rsp+120h] [rbp-248h]
  CDevice *v77; // [rsp+130h] [rbp-238h]
  __int128 *v78; // [rsp+138h] [rbp-230h]
  __int64 v79; // [rsp+140h] [rbp-228h]
  _OWORD *v80; // [rsp+150h] [rbp-218h]
  _com_error *v81; // [rsp+160h] [rbp-208h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+168h] [rbp-200h] BYREF
  _BYTE v83[32]; // [rsp+188h] [rbp-1E0h] BYREF
  _BYTE v84[32]; // [rsp+1A8h] [rbp-1C0h] BYREF
  _OWORD v85[3]; // [rsp+1C8h] [rbp-1A0h] BYREF
  _OWORD v86[3]; // [rsp+1F8h] [rbp-170h] BYREF
  _OWORD v87[3]; // [rsp+230h] [rbp-138h] BYREF
  __int128 v88; // [rsp+260h] [rbp-108h]
  __int128 v89; // [rsp+270h] [rbp-F8h]
  __int128 v90; // [rsp+280h] [rbp-E8h]
  __int128 v91; // [rsp+290h] [rbp-D8h]
  __int128 v92; // [rsp+2A0h] [rbp-C8h]
  __int64 v93; // [rsp+2B0h] [rbp-B8h]
  __int128 v94; // [rsp+2C0h] [rbp-A8h] BYREF
  __int128 v95; // [rsp+2D0h] [rbp-98h]
  __m128i v96; // [rsp+2E0h] [rbp-88h]
  struct D3D11_TEXTURE2D_DESC1 v97; // [rsp+2F0h] [rbp-78h] BYREF

  v61 = a3;
  v7 = a2;
  v8 = (CDevice *)a1;
  v77 = (CDevice *)a1;
  v78 = a2;
  v79 = a3;
  v62 = a5;
  *(_QWORD *)v57 = a6;
  v80 = (_OWORD *)a6;
  v9 = a4 & 1;
  v60 = a4 & 2;
  v56 = v60;
  v51 = v60 != 0;
  v50 = (a4 & 4) != 0;
  if ( a5 )
    *a5 = 0;
  try
  {
    v54 = 0;
    v10 = 0;
    v53 = 0;
    if ( !a2 )
      goto LABEL_26;
    if ( *((_DWORD *)a2 + 4) == 61 )
    {
      if ( (*(_BYTE *)(a1 + 1257) & 8) != 0 )
        v10 = 16;
      v53 = v10;
    }
    if ( (*((_BYTE *)a2 + 40) & 4) != 0 )
    {
      v50 = 0;
      v11 = CDevice::TiledResourcesTier((CDevice *)a1);
      v14 = CCreateTextureCubeValidator::Validate(
              &v50,
              v7,
              a3,
              (char *)v8 + 16,
              &v54,
              v10 | (*((_BYTE *)v8 + 1136) != 0 ? 0x100 : 0),
              (char *)v8 + 1360,
              *((_DWORD *)v8 + 321),
              *((_DWORD *)v8 + 279),
              v13,
              v11,
              v12,
              *((_BYTE *)v8 + 1138),
              *((_BYTE *)v8 + 1156));
      if ( v14 < 0 )
      {
        _com_error::_com_error((_com_error *)pExceptionObject, v14, v15, v16);
        throw (_com_error *)pExceptionObject;
      }
      if ( v9 )
      {
        _com_error::_com_error((_com_error *)v83, -2147024809, v15, v16);
        throw (_com_error *)v83;
      }
    }
    else
    {
LABEL_26:
      v21 = 0;
      if ( *(int *)(a1 + 1124) >= 2 )
        v21 = 8;
      v22 = v10 | v9 | (a6 != 0 ? 4 : 0) | v21 | (*(_BYTE *)(a1 + 1688) != 0 ? 2 : 0);
      if ( !a6 || (v23 = 32, !*(_DWORD *)(a6 + 64)) )
        v23 = 0;
      v24 = v22 | v23 | (*((_BYTE *)v8 + 1136) != 0 ? 0x100 : 0);
      if ( *((int *)v8 + 321) <= 37632 && *((_BYTE *)v8 + 1112) != 1 )
        v24 |= 0x80u;
      DriverDDIVersion = CDevice::GetDriverDDIVersion((char *)v8 + 48);
      v27 = 64;
      if ( DriverDDIVersion < 3 )
        v27 = 0;
      v10 = v27 | v24;
      v53 = v10;
      LOBYTE(v26) = 0;
      if ( v7 && (*((_DWORD *)v7 + 10) & 0x80000) != 0 && *((_BYTE *)v8 + 1112) >= 7u )
      {
        v58 = 0;
        v55 = 0;
        (*(void (__fastcall **)(__int64, int *, int *, __int64))(*(_QWORD *)(*((_QWORD *)v8 + 154) + 16LL) + 336LL))(
          *((_QWORD *)v8 + 154) + 16LL,
          &v58,
          &v55,
          v26);
        LOBYTE(v26) = v58 != 0;
      }
      v52[0] = 0;
      v28 = *((_DWORD *)v8 + 329);
      v29 = *((_DWORD *)v8 + 321);
      if ( (v28 & 4) != 0 && v29 >= 45312 )
      {
        v30 = 3;
      }
      else if ( (v28 & 2) != 0 && v29 >= 45312 )
      {
        v30 = 2;
      }
      else
      {
        v30 = (v28 & 1) != 0 && v29 >= 45056;
      }
      v31 = CCreateTexture2DValidator::Validate(
              v52,
              v7,
              v61,
              (char *)v8 + 16,
              &v54,
              v10,
              (char *)v8 + 1360,
              v29,
              *((_DWORD *)v8 + 279),
              v51,
              (*((_BYTE *)v8 + 1257) & 4) != 0,
              v30,
              v50,
              *((_BYTE *)v8 + 1138),
              *((_BYTE *)v8 + 1156),
              (_BYTE)v26);
      if ( v31 < 0 )
      {
        _com_error::_com_error((_com_error *)v84, v31, v32, v33);
        throw (_com_error *)v84;
      }
    }
    if ( v62 )
    {
      v18 = 0;
      v50 = 0;
      if ( (v7[2] & 0xE00) == 0
        || (*((_DWORD *)v7 + 10) & 0x902) != 0
        || *((_DWORD *)v7 + 9)
        || *((_DWORD *)v7 + 3) > 0x1Eu )
      {
        v20 = 0xFFFFFFFFLL;
      }
      else
      {
        try
        {
          CContext::QueryVideoDDITable(*((CContext **)v8 + 135));
        }
        catch ( _com_error )
        {
          v20 = 0xFFFFFFFFLL;
          LOBYTE(v10) = v53;
          v18 = v50;
          v8 = v77;
          v7 = v78;
          v61 = v79;
          v34 = v80;
          *(_QWORD *)v57 = v80;
          v60 = v56;
          goto LABEL_55;
        }
        if ( (v7[2] & 0x600) == 0x200
          && !a6
          && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v8 + 154) + 168LL))(*((_QWORD *)v8 + 154)) )
        {
          memset(v86, 0, 44);
          v55 = 0;
          PrimaryVidPnSourceId = NDXGI::CUMDAdapter::GetPrimaryVidPnSourceId(*(NDXGI::CUMDAdapter **)(*((_QWORD *)v8 + 154) + 96LL));
          v20 = 0xFFFFFFFFLL;
          if ( PrimaryVidPnSourceId != -1
            && (*(int (__fastcall **)(__int64, _QWORD, _OWORD *, int *))(*(_QWORD *)(*((_QWORD *)v8 + 154) + 16LL)
                                                                       + 216LL))(
                 *((_QWORD *)v8 + 154) + 16LL,
                 PrimaryVidPnSourceId,
                 v86,
                 &v55) >= 0 )
          {
            if ( DWORD2(v86[0]) )
            {
              v58 = *((_DWORD *)v7 + 4);
              v59 = 0;
              if ( (int)CDevice::CheckFeatureSupport(
                          (CDevice *)((char *)v8 + 16),
                          D3D11_FEATURE_FORMAT_SUPPORT2,
                          &v58,
                          8u) >= 0 )
              {
                v18 = (v59 & 0x4000) != 0;
                v50 = v18;
              }
            }
          }
        }
        else
        {
          v20 = 0xFFFFFFFFLL;
        }
      }
      v34 = *(_OWORD **)v57;
LABEL_55:
      v35 = *v7;
      v94 = *v7;
      v36 = v7[1];
      v95 = v36;
      v37 = (__m128i)v7[2];
      v96 = v37;
      if ( !*((_DWORD *)v7 + 2) )
      {
        DWORD2(v94) = v54;
        v35 = v94;
      }
      *(_OWORD *)&v97.Width = v35;
      *(_OWORD *)&v97.Format = v36;
      *(__m128i *)&v97.BindFlags = v37;
      if ( v18 )
        v97.MiscFlags = _mm_cvtsi128_si32(_mm_srli_si128(v37, 8)) | 0x802;
      memset(v87, 0, sizeof(v87));
      v88 = 0;
      v89 = 0;
      v90 = 0;
      v91 = 0;
      v92 = 0;
      v93 = 0;
      if ( !v34 )
      {
        if ( (int)CDevice::InitSharedResource2DCreationParams(v8, &v97, 0, v87) < 0 )
        {
          v34 = *(_OWORD **)v57;
        }
        else
        {
          v34 = v87;
          *(_QWORD *)v57 = v87;
          v38 = HIDWORD(v88);
          if ( v18 )
            v38 = 1;
          HIDWORD(v88) = v38;
        }
      }
      v69 = 0;
      v70 = 0;
      v71 = 0;
      v73 = 0;
      v76 = 0;
      v63[0] = 0;
      v63[1] = 0;
      v64 = 0;
      v65 = 0;
      v72 = &v94;
      v66 = v61;
      v67 = v34;
      v68 = *((_BYTE *)v8 + 1712);
      v74 = 0;
      v75 = 0;
      memset(v85, 0, 44);
      if ( v18 )
      {
        v74 = v85;
        v75 = 44;
      }
      else if ( *((_BYTE *)v8 + 1265) && (*((_DWORD *)v7 + 10) & 0x100000) != 0 )
      {
        v74 = v85;
        v75 = 44;
        if ( (int)CDevice::GetDriverDDIVersion((char *)v8 + 48) < 10 )
        {
          LODWORD(v85[0]) = 1;
          DWORD1(v85[0]) = NDXGI::CUMDAdapter::GetPrimaryVidPnSourceId(*(NDXGI::CUMDAdapter **)(*((_QWORD *)v8 + 154)
                                                                                              + 96LL));
          *((_QWORD *)&v85[0] + 1) = v94;
          LODWORD(v85[1]) = v95;
          *(_QWORD *)((char *)&v85[1] + 4) = 0x3E80000003BLL;
          HIDWORD(v85[1]) = 1;
          LODWORD(v85[2]) = 1;
        }
        v34 = *(_OWORD **)v57;
      }
      if ( (v10 & 4) == 0 )
      {
        if ( v18 )
        {
          LODWORD(v73) = 6;
        }
        else if ( *((_BYTE *)v8 + 1265) )
        {
          v39 = *((_DWORD *)v7 + 10);
          if ( (v39 & 0x100000) != 0 )
          {
            LODWORD(v73) = 32;
            v40 = (NtCurrentPeb()->BitField & 2) != 0 && (NtCurrentPeb()->BitField & 0x40) == 0;
            v41 = *((_BYTE *)v8 + 1712) && (v39 & 0x4000) != 0;
            if ( v40 || (v39 & 0x2000) != 0 || v41 )
              LODWORD(v73) = 34;
          }
        }
      }
      if ( v34 )
      {
        RequirementsTable = CD3D11FormatHelper::GetRequirementsTable(
                              *((unsigned int *)v8 + 321),
                              *((unsigned int *)v8 + 279));
        if ( (unsigned int)v95 < 0xC0 )
          v20 = (unsigned int)v95;
        if ( (*(_DWORD *)(RequirementsTable + 12 * v20 + 4) & 0xC0000) == 0x40000 )
          LODWORD(v73) = v73 | 0x10;
      }
      v50 = 0;
      v65 = &v50;
      v43 = v62;
      v45 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, __int64, _QWORD, GUID *, _QWORD *))(**((_QWORD **)v8 + 31) + 72LL))(
              *((_QWORD *)v8 + 31),
              2,
              v63,
              104,
              0,
              &GUID_51218251_1e33_4617_9ccb_4d3a4367e7bb,
              v62);
      if ( v45 == -2005270523 && v60 )
      {
        v46 = *((_QWORD *)v8 + 135);
        v47 = *((_QWORD *)v8 + 154);
        for ( i = *(_DWORD *)(v47 + 1248);
              *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v47 + 72) + 1080LL) + 39272LL);
              i = *(_DWORD *)(v47 + 1248) )
        {
          if ( i < 0 )
            break;
          SwitchToThread();
        }
        CContext::RemoveContext((CContext *)(v46 + 208), i);
        CContext::CompleteContextRemoval(*((CContext **)v8 + 135), v49);
        v50 = 1;
        v45 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, __int64, _QWORD, GUID *, _QWORD *))(**((_QWORD **)v8 + 31) + 72LL))(
                *((_QWORD *)v8 + 31),
                2,
                v63,
                104,
                0,
                &GUID_51218251_1e33_4617_9ccb_4d3a4367e7bb,
                v43);
      }
      if ( v45 >= 0 )
        CD3D11TelemetryHelper::LogTextureUsage(
          v44,
          *((enum DXGI_FORMAT *)v7 + 4),
          *((enum D3D11_TEXTURE_LAYOUT *)v7 + 11),
          *((_DWORD *)v7 + 10));
      result = (unsigned int)v45;
    }
    else
    {
      result = 1;
    }
  }
  catch ( _com_error *v81 )
  {
    return *((unsigned int *)v81 + 2);
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180067930  push    rbx
0x180067932  push    rsi
0x180067933  push    rdi
0x180067934  push    r12
0x180067936  push    r13
0x180067938  push    r14
0x18006793a  push    r15
0x18006793c  sub     rsp, 330h
0x180067943  mov     rax, cs:__security_cookie
0x18006794a  xor     rax, rsp
0x18006794d  mov     [rsp+368h+var_48], rax
0x180067955  mov     r12, r8
0x180067958  mov     [rsp+368h+var_2B8], r8
0x180067960  mov     rsi, rdx
0x180067963  mov     rbx, rcx
0x180067966  mov     [rsp+368h+var_238], rcx
0x18006796e  mov     [rsp+368h+var_230], rdx
0x180067976  mov     [rsp+368h+var_228], r8
0x18006797e  mov     rax, [rsp+368h+arg_20]
0x180067986  mov     [rsp+368h+var_2B0], rax
0x18006798e  mov     r13, [rsp+368h+arg_28]
0x180067996  mov     qword ptr [rsp+368h+var_2D0], r13
0x18006799e  mov     [rsp+368h+var_218], r13
0x1800679a6  mov     r15d, r9d
0x1800679a9  and     r15d, 1
0x1800679ad  mov     ecx, r9d
0x1800679b0  and     ecx, 2
0x1800679b3  mov     [rsp+368h+var_2C0], ecx
0x1800679ba  mov     [rsp+368h+var_2D8], ecx
0x1800679c1  setnz   r10b
0x1800679c5  mov     [rsp+368h+var_2E7], r10b
0x1800679cd  bt      r9d, 2
0x1800679d2  setb    r9b
0x1800679d6  mov     [rsp+368h+var_2E8], r9b
0x1800679de  xor     r14d, r14d
0x1800679e1  test    rax, rax
0x1800679e4  jz      short loc_1800679E9
0x1800679e6  mov     [rax], r14
0x1800679e9  mov     [rsp+368h+var_2E0], r14d
0x1800679f1  mov     edi, r14d
0x1800679f4  mov     [rsp+368h+var_2E4], r14d
0x1800679fc  test    rsi, rsi
0x1800679ff  jz      loc_180067C41
0x180067a05  cmp     dword ptr [rdx+10h], 3Dh ; '='
0x180067a09  jnz     short loc_180067A21
0x180067a0b  test    byte ptr [rbx+4E9h], 8
0x180067a12  mov     eax, 10h
0x180067a17  cmovnz  edi, eax
0x180067a1a  mov     [rsp+368h+var_2E4], edi
0x180067a21  test    byte ptr [rdx+28h], 4
0x180067a25  jz      loc_180067C41
0x180067a2b  mov     [rsp+368h+var_2E8], 0
0x180067a33  mov     rcx, rbx; this
0x180067a36  call    ?TiledResourcesTier@CDevice@@QEBA?AW4D3D11_TILED_RESOURCES_TIER@@XZ; CDevice::TiledResourcesTier(void)
0x180067a3b  lea     r8, [rbx+550h]
0x180067a42  movzx   ecx, byte ptr [rbx+470h]
0x180067a49  neg     cl
0x180067a4b  sbb     edx, edx
0x180067a4d  and     edx, 100h
0x180067a53  or      edx, edi
0x180067a55  movzx   ecx, byte ptr [rbx+484h]
0x180067a5c  mov     [rsp+368h+var_300], cl
0x180067a60  movzx   ecx, byte ptr [rbx+472h]
0x180067a67  mov     [rsp+368h+var_308], cl
0x180067a6b  mov     byte ptr [rsp+368h+var_310], r9b
0x180067a70  mov     [rsp+368h+var_318], eax
0x180067a74  mov     [rsp+368h+var_320], r10b
0x180067a79  mov     eax, [rbx+45Ch]
0x180067a7f  mov     [rsp+368h+var_328], eax
0x180067a83  mov     eax, [rbx+504h]
0x180067a89  mov     [rsp+368h+var_330], eax
0x180067a8d  mov     [rsp+368h+var_338], r8
0x180067a92  mov     dword ptr [rsp+368h+var_340], edx
0x180067a96  lea     rax, [rsp+368h+var_2E0]
0x180067a9e  mov     [rsp+368h+var_348], rax
0x180067aa3  lea     r9, [rbx+10h]
0x180067aa7  mov     r8, r12
0x180067aaa  mov     rdx, rsi
0x180067aad  lea     rcx, [rsp+368h+var_2E8]
0x180067ab5  call    ?Validate@CCreateTextureCubeValidator@@QEAAJPEBUD3D11_TEXTURE2D_DESC1@@PEBUD3D11_SUBRESOURCE_DATA@@PEAUID3D11Device@@AEAIIPEBVCAPICaps@@W4D3D_FEATURE_LEVEL@@W4eExtendedFormatFeatures@CD3D11FormatHelper@@_NW4D3D11_TILED_RESOURCES_TIER@@777@Z; CCreateTextureCubeValidator::Validate(D3D11_TEXTURE2D_DESC1 const *,D3D11_SUBRESOURCE_DATA const *,ID3D11Device *,uint &,uint,CAPICaps const *,D3D_FEATURE_LEVEL,CD3D11FormatHelper::eExtendedFormatFeatures,bool,D3D11_TILED_RESOURCES_TIER,bool,bool,bool)
0x180067aba  test    eax, eax
0x180067abc  js      loc_18006838A
0x180067ac2  test    r15d, r15d
0x180067ac5  jnz     loc_1800683AD
0x180067acb  mov     r12d, 1
0x180067ad1  cmp     [rsp+368h+var_2B0], 0
0x180067ada  jnz     short loc_180067AE4
0x180067adc  mov     eax, r12d
0x180067adf  jmp     loc_180068367
0x180067ae4  xor     r15b, r15b
0x180067ae7  mov     [rsp+368h+var_2E8], r15b
0x180067aef  test    dword ptr [rsi+20h], 0E00h
0x180067af6  jz      loc_180067E9A
0x180067afc  test    dword ptr [rsi+28h], 902h
0x180067b03  jnz     loc_180067E9A
0x180067b09  cmp     dword ptr [rsi+24h], 0
0x180067b0d  jnz     loc_180067E9A
0x180067b13  cmp     dword ptr [rsi+0Ch], 1Eh
0x180067b17  ja      loc_180067E9A
0x180067b1d  mov     rcx, [rbx+438h]; this
0x180067b24  call    ?QueryVideoDDITable@CContext@@QEAAXXZ; CContext::QueryVideoDDITable(void)
0x180067b29  mov     eax, [rsi+20h]
0x180067b2c  and     eax, 600h
0x180067b31  cmp     eax, 200h
0x180067b36  jnz     loc_180067E33
0x180067b3c  test    r13, r13
0x180067b3f  jnz     loc_180067E33
0x180067b45  mov     rcx, [rbx+4D0h]
0x180067b4c  mov     rax, [rcx]
0x180067b4f  mov     rax, [rax+0A8h]
0x180067b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b5b  test    eax, eax
0x180067b5d  jz      loc_180067E33
0x180067b63  xorps   xmm0, xmm0
0x180067b66  movups  [rsp+368h+var_170], xmm0
0x180067b6e  movups  xmmword ptr [rsp+368h+var_160], xmm0
0x180067b76  movups  xmmword ptr [rsp+368h+var_160+0Ch], xmm0
0x180067b7e  mov     [rsp+368h+var_2DC], r14d
0x180067b86  mov     rcx, [rbx+4D0h]
0x180067b8d  mov     rcx, [rcx+60h]; this
0x180067b91  call    ?GetPrimaryVidPnSourceId@CUMDAdapter@NDXGI@@QEBAIXZ; NDXGI::CUMDAdapter::GetPrimaryVidPnSourceId(void)
0x180067b96  mov     r10d, eax
0x180067b99  mov     r13d, 0FFFFFFFFh
0x180067b9f  cmp     eax, r13d
0x180067ba2  jz      loc_180067E39
0x180067ba8  mov     rcx, [rbx+4D0h]
0x180067baf  add     rcx, 10h
0x180067bb3  mov     rdx, [rcx]
0x180067bb6  mov     rax, [rdx+0D8h]
0x180067bbd  lea     r9, [rsp+368h+var_2DC]
0x180067bc5  lea     r8, [rsp+368h+var_170]
0x180067bcd  mov     edx, r10d
0x180067bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067bd5  test    eax, eax
0x180067bd7  js      loc_180067E39
0x180067bdd  cmp     dword ptr [rsp+368h+var_170+8], 0
0x180067be5  jbe     loc_180067E39
0x180067beb  mov     eax, [rsi+10h]
0x180067bee  mov     [rsp+368h+var_2C8], eax
0x180067bf5  mov     [rsp+368h+var_2C4], r14d
0x180067bfd  mov     r9d, 8; unsigned int
0x180067c03  lea     r8, [rsp+368h+var_2C8]; void *
0x180067c0b  mov     edx, 3; enum D3D11_FEATURE
0x180067c10  lea     rcx, [rbx+10h]; this
0x180067c14  call    ?CheckFeatureSupport@CDevice@@UEAAJW4D3D11_FEATURE@@PEAXI@Z; CDevice::CheckFeatureSupport(D3D11_FEATURE,void *,uint)
0x180067c19  test    eax, eax
0x180067c1b  js      loc_180067E39
0x180067c21  test    [rsp+368h+var_2C4], 4000h
0x180067c2c  movzx   r15d, r15b
0x180067c30  cmovnz  r15d, r12d
0x180067c34  mov     [rsp+368h+var_2E8], r15b
0x180067c3c  jmp     loc_180067E39
0x180067c41  movzx   eax, byte ptr [rbx+698h]
0x180067c48  neg     al
0x180067c4a  sbb     edx, edx
0x180067c4c  and     edx, 2
0x180067c4f  mov     eax, r14d
0x180067c52  mov     ecx, 8
0x180067c57  cmp     dword ptr [rbx+464h], 2
0x180067c5e  cmovge  eax, ecx
0x180067c61  or      edx, eax
0x180067c63  mov     rax, r13
0x180067c66  neg     rax
0x180067c69  sbb     ecx, ecx
0x180067c6b  and     ecx, 4
0x180067c6e  or      edx, ecx
0x180067c70  or      edx, r15d
0x180067c73  or      edx, edi
0x180067c75  test    r13, r13
0x180067c78  jz      short loc_180067C86
0x180067c7a  cmp     dword ptr [r13+40h], 0
0x180067c7f  mov     ecx, 20h ; ' '
0x180067c84  jnz     short loc_180067C89
0x180067c86  mov     ecx, r14d
0x180067c89  movzx   eax, byte ptr [rbx+470h]
0x180067c90  neg     al
0x180067c92  sbb     edi, edi
0x180067c94  and     edi, 100h
0x180067c9a  or      edi, ecx
0x180067c9c  or      edi, edx
0x180067c9e  cmp     dword ptr [rbx+504h], 9300h
0x180067ca8  jg      short loc_180067CB7
0x180067caa  cmp     byte ptr [rbx+458h], 1
0x180067cb1  jz      short loc_180067CB7
0x180067cb3  bts     edi, 7
0x180067cb7  lea     rcx, [rbx+30h]
0x180067cbb  call    ?GetDriverDDIVersion@CDevice@@UEAA?AW4_D3D_DRIVER_DDI_VERSION@@XZ; CDevice::GetDriverDDIVersion(void)
0x180067cc0  mov     ecx, 40h ; '@'
0x180067cc5  cmp     eax, 3
0x180067cc8  cmovl   ecx, r14d
0x180067ccc  or      edi, ecx
0x180067cce  mov     [rsp+368h+var_2E4], edi
0x180067cd5  xor     r9b, r9b
0x180067cd8  test    rsi, rsi
0x180067cdb  jz      short loc_180067D35
0x180067cdd  test    dword ptr [rsi+28h], 80000h
0x180067ce4  jz      short loc_180067D35
0x180067ce6  cmp     byte ptr [rbx+458h], 7
0x180067ced  jb      short loc_180067D35
0x180067cef  mov     [rsp+368h+var_2C8], r14d
0x180067cf7  mov     [rsp+368h+var_2DC], r14d
0x180067cff  mov     rcx, [rbx+4D0h]
0x180067d06  add     rcx, 10h
0x180067d0a  mov     rax, [rcx]
0x180067d0d  lea     r8, [rsp+368h+var_2DC]
0x180067d15  lea     rdx, [rsp+368h+var_2C8]
0x180067d1d  mov     rax, [rax+150h]
0x180067d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d29  cmp     [rsp+368h+var_2C8], 0
0x180067d31  setnz   r9b
0x180067d35  mov     [rsp+368h+var_2E6], 0
0x180067d3d  movzx   r10d, byte ptr [rbx+484h]
0x180067d45  movzx   r11d, byte ptr [rbx+472h]
0x180067d4d  mov     eax, [rbx+524h]
0x180067d53  mov     edx, [rbx+504h]
0x180067d59  test    al, 4
0x180067d5b  jz      short loc_180067D6D
0x180067d5d  cmp     edx, 0B100h
0x180067d63  jl      short loc_180067D6D
0x180067d65  mov     r8d, 3
0x180067d6b  jmp     short loc_180067D9B
0x180067d6d  test    al, 2
0x180067d6f  jz      short loc_180067D81
0x180067d71  cmp     edx, 0B100h
0x180067d77  jl      short loc_180067D81
0x180067d79  mov     r8d, 2
0x180067d7f  jmp     short loc_180067D9B
0x180067d81  test    al, 1
0x180067d83  jz      short loc_180067D98
0x180067d85  cmp     edx, 0B000h
0x180067d8b  jl      short loc_180067D98
0x180067d8d  mov     r12d, 1
0x180067d93  mov     r8d, r12d
0x180067d96  jmp     short loc_180067DA1
0x180067d98  mov     r8d, r14d
0x180067d9b  mov     r12d, 1
0x180067da1  movzx   eax, byte ptr [rbx+4E9h]
0x180067da8  shr     al, 2
0x180067dab  and     al, 1
0x180067dad  lea     rcx, [rbx+550h]
0x180067db4  mov     [rsp+368h+var_2F0], r9b
0x180067db9  mov     [rsp+368h+var_2F8], r10b
0x180067dbe  mov     [rsp+368h+var_300], r11b
0x180067dc3  movzx   r9d, [rsp+368h+var_2E8]
0x180067dcc  mov     [rsp+368h+var_308], r9b
0x180067dd1  mov     [rsp+368h+var_310], r8d
0x180067dd6  mov     byte ptr [rsp+368h+var_318], al
0x180067dda  movzx   eax, [rsp+368h+var_2E7]
0x180067de2  mov     [rsp+368h+var_320], al
0x180067de6  mov     eax, [rbx+45Ch]
0x180067dec  mov     [rsp+368h+var_328], eax
0x180067df0  mov     [rsp+368h+var_330], edx
0x180067df4  mov     [rsp+368h+var_338], rcx
0x180067df9  mov     dword ptr [rsp+368h+var_340], edi
0x180067dfd  lea     rax, [rsp+368h+var_2E0]
0x180067e05  mov     [rsp+368h+var_348], rax
0x180067e0a  lea     r9, [rbx+10h]
0x180067e0e  mov     r8, [rsp+368h+var_2B8]
0x180067e16  mov     rdx, rsi
0x180067e19  lea     rcx, [rsp+368h+var_2E6]
0x180067e21  call    ?Validate@CCreateTexture2DValidator@@QEAAJPEBUD3D11_TEXTURE2D_DESC1@@PEBUD3D11_SUBRESOURCE_DATA@@PEAUID3D11Device2@@AEAIIPEBVCAPICaps@@W4D3D_FEATURE_LEVEL@@W4eExtendedFormatFeatures@CD3D11FormatHelper@@_N7W4D3D11_TILED_RESOURCES_TIER@@7777@Z; CCreateTexture2DValidator::Validate(D3D11_TEXTURE2D_DESC1 const *,D3D11_SUBRESOURCE_DATA const *,ID3D11Device2 *,uint &,uint,CAPICaps const *,D3D_FEATURE_LEVEL,CD3D11FormatHelper::eExtendedFormatFeatures,bool,bool,D3D11_TILED_RESOURCES_TIER,bool,bool,bool,bool)
0x180067e26  test    eax, eax
0x180067e28  js      loc_1800683D3
0x180067e2e  jmp     loc_180067AD1
0x180067e33  mov     r13d, 0FFFFFFFFh
0x180067e39  jmp     short loc_180067EA0
0x180067e3b  xor     r14d, r14d
0x180067e3e  mov     r12d, 1
0x180067e44  mov     r13d, 0FFFFFFFFh
0x180067e4a  mov     edi, [rsp+368h+var_2E4]
0x180067e51  movzx   r15d, [rsp+368h+var_2E8]
0x180067e5a  mov     rbx, [rsp+368h+var_238]
0x180067e62  mov     rsi, [rsp+368h+var_230]
0x180067e6a  mov     rax, [rsp+368h+var_228]
0x180067e72  mov     [rsp+368h+var_2B8], rax
0x180067e7a  mov     r8, [rsp+368h+var_218]
0x180067e82  mov     qword ptr [rsp+368h+var_2D0], r8
0x180067e8a  mov     eax, [rsp+368h+var_2D8]
0x180067e91  mov     [rsp+368h+var_2C0], eax
0x180067e98  jmp     short loc_180067EA8
0x180067e9a  mov     r13d, 0FFFFFFFFh
0x180067ea0  mov     r8, qword ptr [rsp+368h+var_2D0]; unsigned int
0x180067ea8  movups  xmm1, xmmword ptr [rsi]
0x180067eab  movaps  [rsp+368h+var_A8], xmm1
0x180067eb3  movups  xmm2, xmmword ptr [rsi+10h]
0x180067eb7  movaps  [rsp+368h+var_98], xmm2
0x180067ebf  movups  xmm0, xmmword ptr [rsi+20h]
0x180067ec3  movaps  [rsp+368h+var_88], xmm0
0x180067ecb  cmp     dword ptr [rsi+8], 0
0x180067ecf  jnz     short loc_180067EE7
0x180067ed1  mov     eax, [rsp+368h+var_2E0]
0x180067ed8  mov     dword ptr [rsp+368h+var_A8+8], eax
0x180067edf  movaps  xmm1, [rsp+368h+var_A8]
0x180067ee7  movaps  xmmword ptr [rsp+368h+var_78.Width], xmm1
0x180067eef  movaps  xmmword ptr [rsp+368h+var_78.Format], xmm2
0x180067ef7  movaps  xmmword ptr [rsp+368h+var_78.BindFlags], xmm0
0x180067eff  test    r15b, r15b
0x180067f02  jz      short loc_180067F19
0x180067f04  psrldq  xmm0, 8
0x180067f09  movd    eax, xmm0
  ... truncated ...
```
