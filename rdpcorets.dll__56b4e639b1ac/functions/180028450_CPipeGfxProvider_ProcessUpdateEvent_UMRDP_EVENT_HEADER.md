# CPipeGfxProvider::ProcessUpdateEvent(UMRDP_EVENT_HEADER *)

- ea: `0x180028450`
- end: `0x18002a58c`
- name: `?ProcessUpdateEvent@CPipeGfxProvider@@IEAAJPEAUUMRDP_EVENT_HEADER@@@Z`
- size: `8508`
- prototype: `__int64 __fastcall(CPipeGfxProvider *this, struct UMRDP_EVENT_HEADER *, __int64)`
- caller_count: `1`
- callee_count: `45`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800125d0`

## callees

- `0x180001008`
- `0x1800014d8`
- `0x1800015f0`
- `0x180002510`
- `0x180003fd4`
- `0x180004520`
- `0x1800046e0`
- `0x1800047f4`
- `0x1800071c0`
- `0x1800071f0`
- `0x1800074d0`
- `0x180009628`
- `0x18000f784`
- `0x180010960`
- `0x180010aa0`
- `0x180012200`
- `0x180012228`
- `0x18001b3e8`
- `0x180026aa8`
- `0x1800273a4`
- `0x180027658`
- `0x18002782c`
- `0x180027a40`
- `0x180028450`
- `0x18002e348`
- `0x18002ebe8`
- `0x18002ecd4`
- `0x18002f5b0`
- `0x18002f768`
- `0x180033964`
- `0x180034970`
- `0x1800b8d88`
- `0x1800b9290`
- `0x1800b9900`
- `0x1800b9e08`
- `0x1800ba840`
- `0x1800bb944`
- `0x1800bbab0`
- `0x1800bbe2c`
- `0x1800bc9c0`
- `0x1800bc9e8`
- `0x18013aa18`
- `0x18013b9cc`
- `0x18014c328`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002933d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002a4cb`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002933d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002a4cb`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180028490`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180028490`

## string_xrefs

- `0x18002854d`: `ProcessUpdateEvent`
- `0x1800285de`: `ProcessUpdateEvent`
- `0x180028875`: `ProcessUpdateEvent`
- `0x180028f49`: `ProcessUpdateEvent`
- `0x180029a5e`: `ProcessUpdateEvent`
- `0x180029e8d`: `ProcessUpdateEvent`
- `0x180029b27`: `Processing UMRDP_CREATE_SURFACE.`
- `0x180029e25`: `Mapping create surface buffer`
- `0x1800287b7`: `Processing UMRDP_CREATE_SURFACE_DXTEXTURE.`
- `0x18002a4af`: `UMRDP_CREATE_SURFACE stop`
- `0x180028855`: `Failed to create the D3D11 device from shared texture`
- `0x18002883a`: `D3D11 device successfully created`
- `0x180028938`: `spD3D11Device1->OpenSharedResource1 failed`
- `0x1800289b1`: `CRdpDX11ImmutableTexture2D_CreateInstance failed!`
- `0x180028b29`: `Failed to open shared Dx texture resource. Creating local texture`
- `0x180028f04`: `UMRDP_CREATE_SURFACE_DXTEXTURE stop`
- `0x18002908c`: `RDPGFX_PROVIDER_ASSOCIATE_SURFACE_WITH_SCALED_WINDOW_UPDATE allocation failed`
- `0x180029356`: `Surface unmaped and deleted`
- `0x1800292cd`: `Processing UMRDP_DELETE_SURFACE`
- `0x18002963d`: `Updating AssociateUpdate in surface object`
- `0x1800293b3`: `Ignoring UMRDP_DELETE_SURFACE - surface not found`
- `0x1800296ed`: `Updated AssociateUpdate in surface object`
- `0x180029a6f`: `Invalid update Type`
- `0x180029ae5`: `Legacy command. Ignored`

## pseudocode

```c
__int64 __fastcall CPipeGfxProvider::ProcessUpdateEvent(
        CPipeGfxProvider *this,
        struct UMRDP_EVENT_HEADER *a2,
        __int64 a3)
{
  int v3; // r15d
  unsigned int v4; // r12d
  __int64 v6; // rbx
  SurfaceNode *v7; // rcx
  __int64 v9; // rdi
  _DWORD *v10; // rdx
  __int64 v11; // r8
  int v12; // r9d
  __int64 v13; // rcx
  PixelMapBitmapSource *v14; // rdi
  char *v15; // rax
  char *v16; // rdx
  unsigned __int8 *v17; // rax
  int v18; // ecx
  int v19; // ecx
  int v20; // r9d
  __int64 v21; // r15
  size_t v22; // r13
  _DWORD *v23; // rax
  _DWORD *v24; // rbx
  _DWORD *v25; // rax
  SurfaceNode *v26; // rax
  _DWORD *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  int v30; // r9d
  SurfaceNode *v31; // r13
  void *v32; // r12
  int D3D11DeviceFromSharedHandle; // eax
  const char *v34; // rcx
  int v35; // r8d
  int v36; // r9d
  struct ID3D11Device *v37; // rbx
  char *v38; // rax
  char *v39; // rdx
  int v40; // eax
  int v41; // r8d
  int v42; // r9d
  int v43; // ecx
  _QWORD *v44; // r12
  int v45; // ecx
  int v46; // r9d
  const char *v47; // rcx
  int v48; // ebx
  PixelMapBitmapSource *v49; // rax
  PixelMapBitmapSource *v50; // rbx
  const char *v51; // rax
  char *v52; // rdx
  unsigned int v53; // edx
  int v54; // ecx
  int v55; // r8d
  int v56; // r9d
  int v57; // ecx
  int v58; // r8d
  int v59; // r9d
  const char *v60; // rax
  _DWORD *v61; // rax
  int v62; // ecx
  int v63; // r9d
  __int64 v64; // rdx
  __int64 v65; // r8
  struct SurfaceNode *v66; // rax
  int v67; // r8d
  int v68; // r9d
  struct SurfaceNode *v69; // r13
  __int64 v70; // rcx
  int v71; // ecx
  unsigned int *v72; // rax
  unsigned int *v73; // rbx
  __int64 v74; // rdx
  _OWORD *v75; // rcx
  unsigned int *v76; // rax
  __int128 v77; // xmm1
  char *v78; // rbx
  int v79; // ecx
  int v80; // r8d
  int v81; // r9d
  const void *v82; // rcx
  unsigned int v83; // edx
  _DWORD *v84; // rax
  unsigned int v85; // eax
  unsigned int *v86; // rax
  unsigned int *v87; // rbx
  struct SurfaceNode *Surface; // rax
  int v89; // r8d
  int v90; // r9d
  int v91; // ecx
  struct SurfaceNode *v92; // r13
  unsigned int v93; // ecx
  unsigned int v94; // ecx
  int v95; // r8d
  char *v96; // rax
  char *v97; // rdx
  SurfaceNode *v98; // rax
  SurfaceNode *v99; // rax
  SurfaceNode *v100; // r13
  PixelMapBitmapSource *v101; // rax
  PixelMapBitmapSource **v102; // r15
  HardwareWicFallbackSubsampler *v103; // rax
  __int64 v104; // rcx
  unsigned __int64 v105; // rax
  __int64 *v106; // r15
  __int64 v107; // rdi
  WicSubsampler *v108; // rax
  __int64 v109; // rcx
  unsigned __int64 v110; // rax
  __int64 *v111; // r15
  __int64 v112; // rdi
  int v113; // eax
  int v114; // ecx
  int v115; // r8d
  int v116; // r9d
  unsigned int v117; // edx
  int v118; // ecx
  int v119; // r8d
  int v120; // r9d
  const char *v121; // rax
  char *v122; // rdx
  int v123; // ecx
  unsigned __int8 *v124; // rdx
  PixelMap *v125; // rcx
  int v126; // ecx
  unsigned int v127; // eax
  __int64 *v128; // rcx
  __int64 v129; // rdx
  __int64 v130; // rax
  int v131; // eax
  __int64 v132; // rcx
  _DWORD *v133; // rax
  int v134; // eax
  int v135; // eax
  int v136; // ecx
  const void *v137; // rcx
  unsigned __int8 v139; // [rsp+28h] [rbp-71h]
  unsigned __int8 v140; // [rsp+28h] [rbp-71h]
  const char **v141; // [rsp+30h] [rbp-69h]
  unsigned __int8 v142[8]; // [rsp+70h] [rbp-29h] BYREF
  const char *v143; // [rsp+78h] [rbp-21h] BYREF
  __int64 v144; // [rsp+80h] [rbp-19h] BYREF
  const char *v145; // [rsp+88h] [rbp-11h] BYREF
  _QWORD v146[2]; // [rsp+90h] [rbp-9h] BYREF
  const char *v147; // [rsp+A0h] [rbp+7h] BYREF
  int v148; // [rsp+A8h] [rbp+Fh]
  int v149; // [rsp+ACh] [rbp+13h]
  SurfaceNode *v150; // [rsp+100h] [rbp+67h] BYREF
  const char *v151; // [rsp+108h] [rbp+6Fh] BYREF
  struct ID3D11Texture2D *v152; // [rsp+110h] [rbp+77h] BYREF
  struct ID3D11Device *v153; // [rsp+118h] [rbp+7Fh] BYREF

  v3 = *(_DWORD *)a2;
  v4 = 0;
  v6 = 0;
  v7 = (CPipeGfxProvider *)((char *)this + 9696);
  v144 = 0;
  v150 = v7;
  if ( *((_DWORD *)v7 + 2) )
    PAL_System_CritSecEnter(*(_QWORD *)v7, a2, a3);
  v9 = 0;
  if ( *((_QWORD *)this + 1576) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v144, a2, a3);
    v144 = *((_QWORD *)this + 1576);
    v6 = v144;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v144);
    v9 = v6;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v150);
  if ( !v9 )
  {
    LODWORD(v13) = -2147467261;
    LODWORD(v14) = -2147467261;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v15 = "spVideoDriver is NULL";
      LODWORD(v150) = 2131;
      LODWORD(v151) = -2147467261;
      v16 = byte_1801A46DB;
LABEL_8:
      v152 = (struct ID3D11Texture2D *)v15;
      v143 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
      *(_QWORD *)v142 = "Error condition failed";
      v141 = &v143;
      v17 = v142;
LABEL_9:
      v153 = (struct ID3D11Device *)"ProcessUpdateEvent";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (_DWORD)v16,
        v11,
        v12,
        (__int64)v17,
        (__int64)&v151,
        (__int64)v141,
        (__int64)&v150,
        (__int64)&v153,
        (__int64)&v152);
      goto LABEL_287;
    }
    goto LABEL_287;
  }
  if ( v3 == 4 )
  {
    CPipeGfxProvider::MapFrameBuffer(this, (unsigned __int16 *)a2 + 8, *((unsigned int *)a2 + 36), *((_DWORD *)a2 + 37));
LABEL_17:
    LODWORD(v14) = 0;
    goto LABEL_287;
  }
  v18 = *((_DWORD *)this + 3849);
  if ( !v18 && v3 == 20 )
  {
    v19 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)v9 + 120LL))(
            v9,
            (char *)a2 + 16,
            *((unsigned int *)a2 + 36));
    if ( v19 < 0 && (unsigned int)dword_1801B76C8 > 3 )
    {
      LODWORD(v150) = v19;
      v152 = (struct ID3D11Texture2D *)"Failed to MapCursorSharedBuffer";
      v151 = "ProcessUpdateEvent";
      v153 = (struct ID3D11Device *)"HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v19,
        (unsigned int)byte_1801A472D,
        v11,
        v20,
        (__int64)&v153,
        (__int64)&v152,
        (__int64)&v150,
        (__int64)&v151);
    }
    goto LABEL_17;
  }
  v14 = 0;
  switch ( v3 )
  {
    case 0:
      CPipeGfxProvider::ProcessDirtyRegionEvent(this, a2);
      goto LABEL_287;
    case 5:
      v21 = (unsigned int)(*((_DWORD *)a2 + 1) - 16);
      v22 = (unsigned int)v21;
      v23 = operator new(v21 + 1072);
      v24 = v23;
      if ( !v23 )
      {
        LODWORD(v14) = -2147024882;
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_287;
        v15 = "BYTE allocation failed";
        LODWORD(v150) = 2170;
        LODWORD(v151) = -2147024882;
        v16 = &byte_1801A4637;
        goto LABEL_8;
      }
      v23[1] = 8;
      goto LABEL_30;
    case 6:
      v21 = (unsigned int)(*((_DWORD *)a2 + 1) - 16);
      v22 = (unsigned int)v21;
      v25 = operator new(v21 + 1072);
      v24 = v25;
      if ( !v25 )
      {
        LODWORD(v14) = -2147024882;
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_287;
        v15 = "BYTE allocation failed";
        LODWORD(v150) = 2189;
        LODWORD(v151) = -2147024882;
        v16 = byte_1801A4689;
        goto LABEL_8;
      }
      v25[1] = 7;
LABEL_30:
      *v24 = v21 + 1072;
      memcpy_0(v24 + 268, (char *)a2 + 16, v22);
      (*(void (__fastcall **)(char *, _DWORD *))(*((_QWORD *)this + 1558) + 8LL))((char *)this + 12464, v24);
      goto LABEL_287;
    case 1:
      *((_DWORD *)this + 3100) = *((_DWORD *)a2 + 4);
      *((_DWORD *)this + 3101) = *((_DWORD *)a2 + 5);
      *((_DWORD *)this + 3149) = 1;
      goto LABEL_287;
  }
  if ( (unsigned int)(v3 - 2) <= 1 )
  {
    LODWORD(v14) = CPipeGfxProvider::ProcessLegacyPointerShapeEvent(this, a2);
    goto LABEL_287;
  }
  if ( v3 != 10 )
  {
    if ( v18 )
    {
LABEL_130:
      if ( v3 == 11 )
      {
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          v150 = (SurfaceNode *)*((_QWORD *)a2 + 2);
          v151 = "Processing UMRDP_DELETE_SURFACE";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v18,
            (unsigned int)byte_1801A3C65,
            v11,
            v12,
            (__int64)&v151,
            (__int64)&v150);
        }
        v78 = (char *)this + 12560;
        *((_BYTE *)this + 15420) = 0;
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1570) + 64LL))((char *)this + 12560);
        v150 = 0;
        while ( (*(unsigned int (__fastcall **)(char *, SurfaceNode **))(*(_QWORD *)v78 + 72LL))(
                  (char *)this + 12560,
                  &v150) )
        {
          if ( *(_QWORD *)v150 == *((_QWORD *)a2 + 2) )
          {
            v82 = (const void *)*((_QWORD *)v150 + 2);
            if ( v82 )
            {
              UnmapViewOfFile(v82);
              *((_QWORD *)v150 + 2) = 0;
            }
            if ( (unsigned int)dword_1801B76C8 > 4 )
            {
              v151 = "Surface unmaped and deleted";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                (_DWORD)v82,
                (unsigned int)&byte_1801A3C8F,
                v80,
                v81,
                (__int64)&v151);
            }
            (*(void (__fastcall **)(char *, SurfaceNode *))(*(_QWORD *)v78 + 16LL))((char *)this + 12560, v150);
            if ( v150 )
              SurfaceNode::`scalar deleting destructor'(v150, v83);
            goto LABEL_144;
          }
        }
        if ( (unsigned int)dword_1801B76C8 > 3 )
        {
          v151 = (const char *)*((_QWORD *)a2 + 2);
          v152 = (struct ID3D11Texture2D *)"Ignoring UMRDP_DELETE_SURFACE - surface not found";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            v79,
            (unsigned int)byte_1801A3BE9,
            v80,
            v81,
            (__int64)&v152,
            (__int64)&v151);
        }
LABEL_144:
        v84 = operator new(0x438u);
        v10 = v84;
        if ( !v84 )
        {
          LODWORD(v14) = -2147024882;
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_287;
          LODWORD(v150) = 2742;
          v152 = (struct ID3D11Texture2D *)"BYTE allocation failed";
          v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
          v146[0] = "Error condition failed";
          v16 = byte_1801A3C13;
          LODWORD(v151) = -2147024882;
          v141 = &v147;
          v17 = (unsigned __int8 *)v146;
          goto LABEL_9;
        }
        *v84 = 1080;
        v84[1] = 12;
        *((_QWORD *)v84 + 1) = *((_QWORD *)a2 + 2);
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1562) + 8LL))((char *)this + 12496);
        v10 = (_DWORD *)*((_QWORD *)a2 + 2);
        v85 = 0;
        while ( *((_DWORD **)this + v85 + 1177) != v10 )
        {
          if ( (int)++v85 >= 16 )
            goto LABEL_287;
        }
        *((_QWORD *)this + v85 + 1177) = -1;
        goto LABEL_287;
      }
      if ( v3 == 15 )
      {
        v86 = (unsigned int *)operator new(0x448u);
        v87 = v86;
        if ( !v86 )
        {
          LODWORD(v14) = -2147024882;
          if ( (unsigned int)dword_1801B76C8 <= 2 )
            goto LABEL_287;
          LODWORD(v150) = 2770;
          v152 = (struct ID3D11Texture2D *)"BYTE allocation failed";
          v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
          v146[0] = "Error condition failed";
          v16 = byte_1801A3B25;
          LODWORD(v151) = -2147024882;
          v141 = &v147;
          v17 = (unsigned __int8 *)v146;
          goto LABEL_9;
        }
        *((_QWORD *)v86 + 1) = *(_QWORD *)((char *)a2 + 20);
        *v86 = 1096;
        v86[1] = 26;
        v86[266] = 0;
        v86[270] = 1;
        v86[268] = *((_DWORD *)this + 5 * *((unsigned int *)a2 + 4) + 32) - *((_DWORD *)this + 2352);
        v86[269] = *((_DWORD *)this + 5 * *((unsigned int *)a2 + 4) + 33) - *((_DWORD *)this + 2353);
        v86[271] = *((_DWORD *)this + 5 * *((unsigned int *)a2 + 4) + 34)
                 - *((_DWORD *)this + 5 * *((unsigned int *)a2 + 4) + 32)
                 + 1;
        v86[272] = *((_DWORD *)this + 5 * *((unsigned int *)a2 + 4) + 35)
                 - *((_DWORD *)this + 5 * *((unsigned int *)a2 + 4) + 33)
                 + 1;
        *((_QWORD *)this + *((unsigned int *)a2 + 4) + 1177) = *(_QWORD *)((char *)a2 + 20);
        Surface = CPipeGfxProvider::GetSurface(this, *(_QWORD *)((char *)a2 + 20));
        v91 = dword_1801B76C8;
        v92 = Surface;
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          v93 = *v87;
          LODWORD(v143) = v87[268];
          v146[0] = *((_QWORD *)v87 + 1);
          v145 = "Updating AssociateUpdate in surface object";
          LODWORD(v151) = v93;
          LODWORD(v152) = v87[272];
          LODWORD(v153) = v87[271];
          v94 = v87[269];
          LODWORD(v150) = 1096;
          *(_DWORD *)v142 = v94;
          v147 = (const char *)Surface;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v94,
            (unsigned int)&byte_1801A3B77,
            v89,
            v90,
            (__int64)&v145,
            (__int64)v146,
            (__int64)&v147,
            (__int64)&v143,
            (__int64)v142,
            (__int64)&v153,
            (__int64)&v152,
            (__int64)&v151,
            (__int64)&v150);
        }
        if ( v92 && *v87 <= 0x448 )
        {
          if ( (unsigned int)dword_1801B76C8 > 4 )
          {
            LODWORD(v150) = *v87;
            v151 = (const char *)*((_QWORD *)v87 + 1);
            v152 = (struct ID3D11Texture2D *)"Updated AssociateUpdate in surface object";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              v91,
              (unsigned int)byte_1801A3A9D,
              v89,
              v90,
              (__int64)&v152,
              (__int64)&v151,
              (__int64)&v150);
          }
          memcpy_0((char *)v92 + 1192, v87, *v87);
          *((_QWORD *)v92 + 286) = *v87;
        }
        (*(void (__fastcall **)(char *, unsigned int *))(*((_QWORD *)this + 1562) + 8LL))((char *)this + 12496, v87);
        if ( *((_DWORD *)this + 3850) )
        {
          LODWORD(v14) = CPipeGfxProvider::ProcessProtectSurfaceEvent(this, *(_QWORD *)((char *)a2 + 20), 1);
          if ( (int)v14 < 0 )
          {
            if ( (unsigned int)dword_1801B76C8 <= 2 )
              goto LABEL_287;
            LODWORD(v150) = 2822;
            v152 = (struct ID3D11Texture2D *)"ProcessProtectSurfaceEvent failed.";
            v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
            v146[0] = "Error HResult failed";
            v16 = byte_1801A3AD3;
            LODWORD(v151) = (_DWORD)v14;
            v141 = &v147;
            v17 = (unsigned __int8 *)v146;
            goto LABEL_9;
          }
        }
        if ( *((_DWORD *)this + 3851) )
        {
          LODWORD(v14) = CPipeGfxProvider::ProcessWatermarkingSurfaceEvent(
                           this,
                           *(_QWORD *)((char *)a2 + 20),
                           *((_DWORD *)this + 5 * *((unsigned int *)a2 + 4) + 115));
          if ( (int)v14 < 0 && (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v150) = 2835;
            v152 = (struct ID3D11Texture2D *)"ProcessWatermarkingSurfaceEvent failed.";
            v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
            v146[0] = "Error HResult failed";
            v16 = byte_1801A39F9;
            LODWORD(v151) = (_DWORD)v14;
            v141 = &v147;
            v17 = (unsigned __int8 *)v146;
            goto LABEL_9;
          }
        }
        goto LABEL_287;
      }
      if ( !v18 && v3 == 22 )
      {
        LODWORD(v14) = CPipeGfxProvider::ProcessProtectSurfaceEvent(this, *((_QWORD *)a2 + 2), *((_DWORD *)a2 + 6));
        if ( (int)v14 < 0 && (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v150) = 2845;
          v152 = (struct ID3D11Texture2D *)"ProcessProtectSurfaceEvent failed.";
          v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
          v146[0] = "Error HResult failed";
          v16 = byte_1801A3A4B;
          LODWORD(v151) = (_DWORD)v14;
          v141 = &v147;
          v17 = (unsigned __int8 *)v146;
          goto LABEL_9;
        }
        goto LABEL_287;
      }
      switch ( v3 )
      {
        case 16:
          LODWORD(v14) = CPipeGfxProvider::ProcessFrameMarkerEvent(this, a2);
          if ( (int)v14 < 0 && (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v150) = 2851;
            v152 = (struct ID3D11Texture2D *)"ProcessFrameMarkerEvent failed.";
            v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
            v146[0] = "Error HResult failed";
            v16 = byte_1801A3981;
            LODWORD(v151) = (_DWORD)v14;
            v141 = &v147;
            v17 = (unsigned __int8 *)v146;
            goto LABEL_9;
          }
          goto LABEL_287;
        case 12:
          *((_DWORD *)this + 3438) = 1;
          *(_OWORD *)((char *)this + 13688) = *((_OWORD *)a2 + 1);
          *(_OWORD *)((char *)this + 13704) = *((_OWORD *)a2 + 2);
          *(_OWORD *)((char *)this + 13720) = *((_OWORD *)a2 + 3);
          *(_OWORD *)((char *)this + 13736) = *((_OWORD *)a2 + 4);
          goto LABEL_287;
        case 14:
          v95 = 0;
LABEL_187:
          CPipeGfxProvider::ProcessVideoHintEvent(this, a2, v95);
          goto LABEL_287;
      }
      if ( !v18 && v3 == 23 )
      {
        v95 = 1;
        goto LABEL_187;
      }
      if ( v3 != 13 && (unsigned int)(v3 - 7) > 2 )
      {
        LODWORD(v14) = -2147418113;
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v150) = *(_DWORD *)a2;
          v153 = (struct ID3D11Device *)"ProcessUpdateEvent";
          v146[0] = "Invalid update Type";
          LODWORD(v151) = 2892;
          v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
          LODWORD(v152) = -2147418113;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v18,
            (unsigned int)byte_1801A3931,
            v11,
            v12,
            (__int64)v146,
            (__int64)&v152,
            (__int64)&v147,
            (__int64)&v151,
            (__int64)&v153,
            (__int64)&v150);
        }
        goto LABEL_287;
      }
      LODWORD(v14) = 1;
      if ( (unsigned int)dword_1801B76C8 <= 4 )
        goto LABEL_287;
      v96 = "Legacy command. Ignored";
      v97 = byte_1801A39D3;
LABEL_194:
      v150 = (SurfaceNode *)v96;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v18,
        (_DWORD)v97,
        v11,
        v12,
        (__int64)&v150);
      goto LABEL_287;
    }
    if ( v3 != 19 )
    {
      switch ( v3 )
      {
        case 21:
          if ( (unsigned int)dword_1801B76C8 > 4 )
          {
            v150 = (SurfaceNode *)*((_QWORD *)a2 + 3);
            v151 = "Processing UMRDP_CREATE_SURFACE_DXTEXTURE.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
              0,
              (unsigned int)byte_1801A4215,
              v11,
              v12,
              (__int64)&v151,
              (__int64)&v150);
          }
          v153 = 0;
          v152 = 0;
          v26 = (SurfaceNode *)operator new(0x900u);
          if ( !v26 || (v31 = SurfaceNode::SurfaceNode(v26)) == 0 )
          {
            LODWORD(v14) = -2147024882;
            if ( (unsigned int)dword_1801B76C8 > 2 )
            {
              v51 = "PSurfaceNode allocation failed";
              LODWORD(v150) = 2451;
              v52 = &byte_1801A4177;
              goto LABEL_108;
            }
            goto LABEL_110;
          }
          *(_QWORD *)v31 = *((_QWORD *)a2 + 3);
          v32 = (void *)*((_QWORD *)a2 + 4);
          D3D11DeviceFromSharedHandle = CPipeGfxProvider::GetD3D11DeviceFromSharedHandle(
                                          (CPipeGfxProvider *)v28,
                                          &v153,
                                          v32);
          v37 = v153;
          LODWORD(v14) = D3D11DeviceFromSharedHandle;
          if ( D3D11DeviceFromSharedHandle || !v153 )
          {
            if ( (unsigned int)dword_1801B76C8 <= 3 )
              goto LABEL_49;
            v38 = "Failed to create the D3D11 device from shared texture";
            v39 = byte_1801A4151;
          }
          else
          {
            LODWORD(v34) = dword_1801B76C8;
            if ( (unsigned int)dword_1801B76C8 <= 4 )
              goto LABEL_49;
            v38 = "D3D11 device successfully created";
            v39 = byte_1801A41C9;
          }
          v150 = (SurfaceNode *)v38;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (_DWORD)v34,
            (_DWORD)v39,
            v35,
            v36,
            (__int64)&v150);
LABEL_49:
          if ( !v37 )
            goto LABEL_69;
          v143 = 0;
          v40 = ((__int64 (__fastcall *)(struct ID3D11Device *, GUID *, const char **))v37->lpVtbl->QueryInterface)(
                  v37,
                  &GUID_a04bfb29_08ef_43d6_a49c_a9bdbdcbe686,
                  &v143);
          if ( v40 < 0 && (unsigned int)dword_1801B76C8 > 3 )
          {
            LODWORD(v150) = v40;
            v151 = "ProcessUpdateEvent";
            *(_QWORD *)v142 = "QueryInterface ID3D11Device1 failed";
            v145 = "HResult failed but continue";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              dword_1801B76C8,
              (unsigned int)byte_1801A4111,
              v41,
              v42,
              (__int64)&v145,
              (__int64)v142,
              (__int64)&v150,
              (__int64)&v151);
          }
          LODWORD(v14) = (*(__int64 (__fastcall **)(const char *, void *, GUID *, struct ID3D11Texture2D **))(*(_QWORD *)v143 + 384LL))(
                           v143,
                           v32,
                           &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c,
                           &v152);
          if ( (int)v14 >= 0 )
          {
            if ( v152 )
            {
              v44 = (_QWORD *)((char *)v31 + 40);
              LODWORD(v14) = CRdpDX11ImmutableTexture2D_CreateInstance(
                               v152,
                               (struct CRdpDX11ImmutableTexture2D **)v31 + 5);
              if ( (int)v14 >= 0 )
              {
                if ( *v44 )
                {
                  v48 = *((_DWORD *)a2 + 5);
                  if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v44 + 32LL))(*v44) == v48 )
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v44 + 40LL))(*v44);
                  goto LABEL_67;
                }
                LODWORD(v14) = -2147467261;
                if ( (unsigned int)dword_1801B76C8 > 2 )
                {
                  v146[0] = "ProcessUpdateEvent";
                  v147 = "pSurface->m_spSrcRdpDxTexture is NULL";
                  LODWORD(v150) = 2490;
                  *(_QWORD *)v142 = "Error condition failed";
                  v145 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
                  LODWORD(v151) = -2147467261;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    -2147467261,
                    (unsigned int)byte_1801A402D,
                    v29,
                    v46,
                    (__int64)v142,
                    (__int64)&v151,
                    (__int64)&v145,
                    (__int64)&v150,
                    (__int64)v146,
                    (__int64)&v147);
                }
              }
              else if ( (unsigned int)dword_1801B76C8 > 2 )
              {
                *(_QWORD *)v142 = "ProcessUpdateEvent";
                v145 = "CRdpDX11ImmutableTexture2D_CreateInstance failed!";
                LODWORD(v150) = 2488;
                v147 = "Error HResult failed";
                v146[0] = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
                LODWORD(v151) = (_DWORD)v14;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  v45,
                  (unsigned int)&byte_1801A40BF,
                  v29,
                  v46,
                  (__int64)&v147,
                  (__int64)&v151,
                  (__int64)v146,
                  (__int64)&v150,
                  (__int64)v142,
                  (__int64)&v145);
              }
              v47 = v143;
              if ( v143 )
              {
                v143 = 0;
                (*(void (__fastcall **)(const char *))(*(_QWORD *)v47 + 16LL))(v47);
              }
              goto LABEL_110;
            }
          }
          else if ( (unsigned int)dword_1801B76C8 > 3 )
          {
            v151 = "ProcessUpdateEvent";
            v145 = "spD3D11Device1->OpenSharedResource1 failed";
            LODWORD(v150) = (_DWORD)v14;
            *(_QWORD *)v142 = "HResult failed but continue";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v43,
              (unsigned int)&byte_1801A407F,
              v35,
              v36,
              (__int64)v142,
              (__int64)&v145,
              (__int64)&v150,
              (__int64)&v151);
          }
LABEL_67:
          v34 = v143;
          if ( v143 )
          {
            v143 = 0;
            (*(void (__fastcall **)(const char *))(*(_QWORD *)v34 + 16LL))(v34);
          }
LABEL_69:
          if ( (int)v14 < 0 )
          {
            if ( (unsigned int)dword_1801B76C8 > 3 )
            {
              v150 = (SurfaceNode *)"Failed to open shared Dx texture resource. Creating local texture";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                (_DWORD)v34,
                (unsigned int)byte_1801A3FB5,
                v35,
                v36,
                (__int64)&v150);
            }
            if ( *((_QWORD *)v31 + 5) )
            {
              TCntPtr<CRdpDX11ImmutableTexture2D>::SafeRelease((char *)v31 + 40);
              *((_QWORD *)v31 + 5) = 0;
              TCntPtr<CRdpDX11ImmutableTexture2D>::SafeAddRef((char *)v31 + 40);
            }
            v49 = (PixelMapBitmapSource *)operator new(0x58u);
            if ( v49 )
              v50 = PixelMapBitmapSource::PixelMapBitmapSource(v49);
            else
              v50 = 0;
            v14 = (SurfaceNode *)((char *)v31 + 24);
            if ( v50 != *((PixelMapBitmapSource **)v31 + 3) )
            {
              TCntPtr<WicSubsampler>::SafeRelease((char *)v31 + 24);
              *(_QWORD *)v14 = v50;
              if ( v50 )
                (*(void (__fastcall **)(__int64))(*((_QWORD *)v50 + 6) + 8LL))((__int64)v50 + 48);
            }
            v28 = *(_QWORD *)v14;
            if ( !*(_QWORD *)v14 )
            {
              LODWORD(v14) = -2147024882;
              if ( (unsigned int)dword_1801B76C8 > 2 )
              {
                v51 = "PixelMapBitmapSource allocation failed";
                LODWORD(v150) = 2514;
                v52 = byte_1801A3FDB;
LABEL_108:
                v147 = v51;
                v60 = "Error condition failed";
                LODWORD(v151) = -2147024882;
                goto LABEL_109;
              }
              goto LABEL_110;
            }
            if ( !PixelMap::SetupImage(
                    (PixelMap *)(v28 + 56),
                    *((_DWORD *)a2 + 5),
                    *((_DWORD *)a2 + 4),
                    32,
                    (4 * *((_DWORD *)a2 + 5) + 15) & 0xFFFFFFF0,
                    v139) )
            {
              LODWORD(v14) = -2147024882;
              if ( (unsigned int)dword_1801B76C8 > 2 )
              {
                v147 = "ProcessUpdateEvent";
                v145 = "SetupImageForSIMD failed!";
                LODWORD(v150) = 2524;
                v146[0] = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
                LODWORD(v151) = -2147024882;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  v54,
                  (unsigned int)byte_1801A3F45,
                  v55,
                  v56,
                  (__int64)&v145,
                  (__int64)&v151,
                  (__int64)v146,
                  (__int64)&v150,
                  (__int64)&v147);
              }
              SurfaceNode::`scalar deleting destructor'(v31, v53);
              goto LABEL_110;
            }
            PixelMap::Fill((PixelMap *)(*(_QWORD *)v14 + 56LL), 16711680);
            LODWORD(v14) = 0;
            *((_DWORD *)v31 + 575) = 1;
            if ( (unsigned int)dword_1801B76C8 > 5 )
            {
              v150 = (SurfaceNode *)"Using dummy pixelmap until DX texture sharing is successful";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                v57,
                (unsigned int)&byte_1801A3F8F,
                v58,
                v59,
                (__int64)&v150);
            }
LABEL_101:
            SurfaceNode::InitDirtyRegionUpdate(v31, *(_QWORD *)v31);
            (*(void (__fastcall **)(char *, SurfaceNode *))(*((_QWORD *)this + 1570) + 8LL))((char *)this + 12560, v31);
            v61 = operator new(0x448u);
            v27 = v61;
            if ( v61 )
            {
              *v61 = 1096;
              v61[1] = 11;
              *((_QWORD *)v61 + 1) = *((_QWORD *)a2 + 3);
              v61[270] = *((_DWORD *)a2 + 5);
              v61[271] = *((_DWORD *)a2 + 4);
              v61[272] = 4;
              *((_DWORD *)v31 + 574) = 4;
              (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1562) + 8LL))((char *)this + 12496);
              if ( (unsigned int)dword_1801B76C8 > 4 )
              {
                v150 = (SurfaceNode *)"UMRDP_CREATE_SURFACE_DXTEXTURE stop";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  v62,
                  (unsigned int)byte_1801A3D59,
                  v29,
                  v63,
                  (__int64)&v150);
              }
              goto LABEL_110;
            }
            LODWORD(v14) = -2147024882;
            if ( (unsigned int)dword_1801B76C8 > 2 )
            {
              v51 = "BYTE allocation failed";
              LODWORD(v150) = 2583;
              v52 = byte_1801A3E05;
              goto LABEL_108;
            }
LABEL_110:
            TCntPtr<IRdpSQMLogger>::SafeRelease(&v152, v27, v29);
            TCntPtr<IRdpSQMLogger>::SafeRelease(&v153, v64, v65);
            goto LABEL_287;
          }
          LODWORD(v14) = ((__int64 (__fastcall *)(struct ID3D11Texture2D *, GUID *, char *))v152->lpVtbl->QueryInterface)(
                           v152,
                           &GUID_9d8e1289_d7b3_465f_8126_250e349af85d,
                           (char *)v31 + 32);
          if ( (int)v14 < 0 )
          {
            if ( (unsigned int)dword_1801B76C8 <= 2 )
              goto LABEL_110;
            LODWORD(v150) = 2549;
            v147 = "Failed to query IDXGIKeyedMutex to get keyed mutex";
            v52 = byte_1801A3EF3;
            v60 = "Error HResult failed";
            LODWORD(v151) = (_DWORD)v14;
LABEL_109:
            v143 = v60;
            v146[0] = "ProcessUpdateEvent";
            v145 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v28,
              (_DWORD)v52,
              v29,
              v30,
              (__int64)&v143,
              (__int64)&v151,
              (__int64)&v145,
              (__int64)&v150,
              (__int64)v146,
              (__int64)&v147);
            goto LABEL_110;
          }
          LODWORD(v14) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)v31 + 4) + 64LL))(
                           *((_QWORD *)v31 + 4),
                           0,
                           3000);
          if ( (int)v14 < 0 )
          {
            if ( *((_DWORD *)this + 3852) )
            {
              if ( (unsigned int)dword_1801B76C8 <= 2 )
                goto LABEL_110;
              LODWORD(v150) = 2554;
              v147 = "Failed to acquire Dx texture keyed mutex";
              v52 = &byte_1801A3E57;
              v60 = "Error HResult failed";
              LODWORD(v151) = (_DWORD)v14;
              goto LABEL_109;
            }
            if ( (unsigned int)dword_1801B76C8 > 2 )
            {
              v147 = "ProcessUpdateEvent";
              v145 = "Failed to acquire Dx texture keyed mutex";
              LODWORD(v150) = 2559;
              v146[0] = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
              LODWORD(v151) = (_DWORD)v14;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v28,
                (unsigned int)byte_1801A3EA9,
                v29,
                v30,
                (__int64)&v145,
                (__int64)&v151,
                (__int64)v146,
                (__int64)&v150,
                (__int64)&v147);
            }
          }
          if ( (unsigned int)dword_1801B76C8 > 5 )
          {
            v151 = *(const char **)v31;
            v147 = "Dx texture keyed mutex acquired";
            LODWORD(v150) = (_DWORD)v14;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              v28,
              (unsigned int)&word_1801A3DCE,
              v29,
              v30,
              (__int64)&v147,
              (__int64)&v151,
              (__int64)&v150);
          }
          *((_DWORD *)v31 + 575) = 0;
          *((_BYTE *)this + 15420) = 1;
          goto LABEL_101;
        case 18:
          v66 = CPipeGfxProvider::GetSurface(this, *((_QWORD *)a2 + 2));
          v69 = v66;
          if ( v66 )
          {
            v70 = *((_QWORD *)v66 + 3);
            v4 = *(_DWORD *)(v70 + 56);
            v71 = *(_DWORD *)(v70 + 60);
          }
          else
          {
            v71 = 0;
          }
          LODWORD(v150) = v71;
          if ( (unsigned int)dword_1801B76C8 > 4 )
          {
            v153 = (struct ID3D11Device *)*((_QWORD *)a2 + 3);
            v147 = (const char *)*((_QWORD *)a2 + 2);
            v146[0] = "Processing UMRDP_MAP_SURFACE_TO_WINDOW";
            LODWORD(v151) = v71;
            LODWORD(v152) = v4;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v71,
              (unsigned int)&byte_1801A3D7F,
              v67,
              v68,
              (__int64)v146,
              (__int64)&v147,
              (__int64)&v153,
              (__int64)&v152,
              (__int64)&v151);
          }
          v72 = (unsigned int *)operator new(0x448u);
          v73 = v72;
          if ( !v72 )
          {
            LODWORD(v14) = -2147024882;
            if ( (unsigned int)dword_1801B76C8 <= 2 )
              goto LABEL_287;
            LODWORD(v150) = 2648;
            v152 = (struct ID3D11Texture2D *)"RDPGFX_PROVIDER_ASSOCIATE_SURFACE_WITH_SCALED_WINDOW_UPDATE allocation failed";
            v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
            v146[0] = "Error condition failed";
            v16 = byte_1801A3CB5;
            LODWORD(v151) = -2147024882;
            v141 = &v147;
            v17 = (unsigned __int8 *)v146;
            goto LABEL_9;
          }
          memset_0(v72 + 2, 0, 0x440u);
          *v73 = 1096;
          v73[1] = 27;
          *((_QWORD *)v73 + 1) = *((_QWORD *)a2 + 2);
          *((_QWORD *)v73 + 134) = *((_QWORD *)a2 + 3);
          v73[270] = *((_DWORD *)a2 + 9);
          v73[271] = *((_DWORD *)a2 + 8);
          v73[273] = (unsigned int)v150;
          v73[272] = v4;
          if ( v69 )
          {
            v74 = 8;
            v75 = (_OWORD *)((char *)v69 + 1192);
            v76 = v73;
            do
            {
              *v75 = *(_OWORD *)v76;
              v75[1] = *((_OWORD *)v76 + 1);
              v75[2] = *((_OWORD *)v76 + 2);
              v75[3] = *((_OWORD *)v76 + 3);
              v75[4] = *((_OWORD *)v76 + 4);
              v75[5] = *((_OWORD *)v76 + 5);
              v75[6] = *((_OWORD *)v76 + 6);
              v77 = *((_OWORD *)v76 + 7);
              v76 += 32;
              v75[7] = v77;
              v75 += 8;
              --v74;
            }
            while ( v74 );
            *v75 = *(_OWORD *)v76;
            v75[1] = *((_OWORD *)v76 + 1);
            v75[2] = *((_OWORD *)v76 + 2);
            v75[3] = *((_OWORD *)v76 + 3);
            *((_QWORD *)v75 + 8) = *((_QWORD *)v76 + 8);
            *((_QWORD *)v69 + 286) = *v73;
          }
          (*(void (__fastcall **)(char *, unsigned int *))(*((_QWORD *)this + 1562) + 8LL))((char *)this + 12496, v73);
          if ( *((_DWORD *)this + 3850) )
            CPipeGfxProvider::ProcessProtectSurfaceEvent(this, *((_QWORD *)a2 + 2), 1);
          goto LABEL_287;
        case 17:
          LODWORD(v14) = CPipeGfxProvider::ProcessMonitorLayoutChange(this, a2);
          if ( (int)v14 < 0 && (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v150) = 2685;
            v152 = (struct ID3D11Texture2D *)"ProcessMonitorLayoutChange failed.";
            v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
            v146[0] = "Error HResult failed";
            v16 = &byte_1801A3D07;
            LODWORD(v151) = (_DWORD)v14;
            v141 = &v147;
            v17 = (unsigned __int8 *)v146;
            goto LABEL_9;
          }
          goto LABEL_287;
      }
      goto LABEL_130;
    }
  }
  if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    v150 = (SurfaceNode *)*((_QWORD *)a2 + 20);
    v151 = "Processing UMRDP_CREATE_SURFACE.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v18,
      (unsigned int)byte_1801A45BB,
      v11,
      v12,
      (__int64)&v151,
      (__int64)&v150);
  }
  v98 = (SurfaceNode *)operator new(0x900u);
  if ( !v98 || (v99 = SurfaceNode::SurfaceNode(v98), (v100 = v99) == 0) )
  {
    LODWORD(v14) = -2147024882;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_287;
    LODWORD(v150) = 2218;
    v152 = (struct ID3D11Texture2D *)"PSurfaceNode allocation failed";
    v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
    v146[0] = "Error condition failed";
    v16 = byte_1801A45E5;
    LODWORD(v151) = -2147024882;
    v141 = &v147;
    v17 = (unsigned __int8 *)v146;
    goto LABEL_9;
  }
  *(_QWORD *)v99 = *((_QWORD *)a2 + 20);
  v101 = (PixelMapBitmapSource *)operator new(0x58u);
  if ( v101 )
    v14 = PixelMapBitmapSource::PixelMapBitmapSource(v101);
  v102 = (PixelMapBitmapSource **)((char *)v100 + 24);
  if ( v14 != *((PixelMapBitmapSource **)v100 + 3) )
  {
    TCntPtr<WicSubsampler>::SafeRelease((char *)v100 + 24);
    *v102 = v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*((_QWORD *)v14 + 6) + 8LL))((__int64)v14 + 48);
  }
  if ( !*v102 )
  {
    LODWORD(v14) = -2147024882;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_287;
    LODWORD(v150) = 2222;
    v152 = (struct ID3D11Texture2D *)"PixelMapBitmapSource allocation failed";
    v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
    v146[0] = "Error condition failed";
    v16 = byte_1801A4569;
    LODWORD(v151) = -2147024882;
    v141 = &v147;
    v17 = (unsigned __int8 *)v146;
    goto LABEL_9;
  }
  if ( *((_DWORD *)this + 3842) )
  {
    v103 = (HardwareWicFallbackSubsampler *)operator new(0x50u);
    if ( v103 )
      v104 = (__int64)HardwareWicFallbackSubsampler::HardwareWicFallbackSubsampler(
                        v103,
                        (enum WICBitmapInterpolationMode)*((_DWORD *)this + 3846));
    else
      v104 = 0;
    v105 = v104 + 48;
    v13 = -v104;
    v106 = (__int64 *)((char *)v100 + 1184);
    v107 = v105 & -(__int64)(v13 != 0);
    if ( v107 != *((_QWORD *)v100 + 148) )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)v100 + 1184, v10, v11);
      *v106 = v107;
      if ( v107 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 8LL))(v107);
    }
    if ( !*v106 )
    {
      LODWORD(v14) = -2147024882;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_287;
      LODWORD(v150) = 2226;
      v152 = (struct ID3D11Texture2D *)"HardwareWicFallbackSubsampler allocation failed";
      v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
      v146[0] = "Error condition failed";
      v16 = byte_1801A44C5;
      LODWORD(v151) = -2147024882;
      v141 = &v147;
      v17 = (unsigned __int8 *)v146;
      goto LABEL_9;
    }
  }
  else
  {
    v108 = (WicSubsampler *)operator new(0x48u);
    if ( v108 )
      v109 = (__int64)WicSubsampler::WicSubsampler(v108, (enum WICBitmapInterpolationMode)*((_DWORD *)this + 3846));
    else
      v109 = 0;
    v110 = v109 + 48;
    v13 = -v109;
    v111 = (__int64 *)((char *)v100 + 1184);
    v112 = v110 & -(__int64)(v13 != 0);
    if ( v112 != *((_QWORD *)v100 + 148) )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease((char *)v100 + 1184, v10, v11);
      *v111 = v112;
      if ( v112 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 8LL))(v112);
    }
    if ( !*v111 )
    {
      LODWORD(v14) = -2147024882;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_287;
      LODWORD(v150) = 2231;
      v152 = (struct ID3D11Texture2D *)"WicSubsampler allocation failed";
      v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
      v146[0] = "Error condition failed";
      v16 = &byte_1801A4517;
      LODWORD(v151) = -2147024882;
      v141 = &v147;
      v17 = (unsigned __int8 *)v146;
      goto LABEL_9;
    }
  }
  *((_BYTE *)this + 15420) = 0;
  if ( (unsigned int)dword_1801B76C8 <= 4 )
  {
    v14 = (struct UMRDP_EVENT_HEADER *)((char *)a2 + 16);
  }
  else
  {
    v151 = "Mapping create surface buffer";
    v14 = (struct UMRDP_EVENT_HEADER *)((char *)a2 + 16);
    v150 = (struct UMRDP_EVENT_HEADER *)((char *)a2 + 16);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      v13,
      (unsigned int)byte_1801A4473,
      v11,
      v12,
      (__int64)&v151,
      (__int64)&v150);
  }
  v113 = (*(__int64 (__fastcall **)(__int64, bool, PixelMapBitmapSource *, _QWORD, __int64))(*(_QWORD *)v6 + 104LL))(
           v6,
           *((_DWORD *)a2 + 42) == 1,
           v14,
           *((unsigned int *)a2 + 36),
           (__int64)v100 + 16);
  LODWORD(v14) = 0;
  if ( v113 >= 0 )
  {
    v124 = (unsigned __int8 *)*((_QWORD *)v100 + 2);
    v125 = (PixelMap *)(*((_QWORD *)v100 + 3) + 56LL);
    *((_DWORD *)v100 + 2) = 1;
    *((_DWORD *)v100 + 575) = 0;
    if ( PixelMap::Attach(
           v125,
           v124,
           *((_DWORD *)a2 + 39) * *((_DWORD *)a2 + 37),
           *((_DWORD *)a2 + 38),
           *((_DWORD *)a2 + 37),
           *((_DWORD *)a2 + 39),
           32,
           0,
           0,
           *((_DWORD *)a2 + 38),
           *((_DWORD *)a2 + 37)) )
    {
      PixelMap::SetAlpha((PixelMap *)(*((_QWORD *)v100 + 3) + 56LL), *((_DWORD *)a2 + 43) == 1);
      goto LABEL_242;
    }
    LODWORD(v14) = -2147467259;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v150) = 2298;
      v121 = "Error attaching bitmap pixels!";
      LODWORD(v151) = -2147467259;
      v122 = byte_1801A43B9;
      goto LABEL_240;
    }
  }
  else
  {
    if ( (unsigned int)dword_1801B76C8 > 3 )
    {
      v150 = (SurfaceNode *)"Failed to map shared frame buffer.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v114,
        (unsigned int)&byte_1801A449F,
        v115,
        v116,
        (__int64)&v150);
    }
    if ( PixelMap::SetupImage(
           (PixelMap *)(*((_QWORD *)v100 + 3) + 56LL),
           *((_DWORD *)a2 + 38),
           *((_DWORD *)a2 + 37),
           32,
           (4 * *((_DWORD *)a2 + 38) + 15) & 0xFFFFFFF0,
           v139) )
    {
      PixelMap::Fill((PixelMap *)(*((_QWORD *)v100 + 3) + 56LL), 16711680);
      *((_DWORD *)v100 + 575) = 1;
      if ( (unsigned int)dword_1801B76C8 > 5 )
      {
        v150 = (SurfaceNode *)"Using dummy pixelmap until shared buffer is mapped";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v123,
          (unsigned int)byte_1801A4403,
          v119,
          v120,
          (__int64)&v150);
      }
    }
    else
    {
      LODWORD(v14) = -2147024882;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v150) = 2265;
        v121 = "SetupImageForSIMD failed!";
        LODWORD(v151) = -2147024882;
        v122 = byte_1801A4429;
LABEL_240:
        v147 = v121;
        v153 = (struct ID3D11Device *)"clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
        v152 = (struct ID3D11Texture2D *)"ProcessUpdateEvent";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v118,
          (_DWORD)v122,
          v119,
          v120,
          (__int64)&v147,
          (__int64)&v151,
          (__int64)&v153,
          (__int64)&v150,
          (__int64)&v152);
      }
    }
  }
LABEL_242:
  v126 = 100;
  if ( *((_DWORD *)this + 3849) || *(_DWORD *)a2 != 19 )
  {
    *((_DWORD *)v100 + 295) = 100;
    v127 = 100;
  }
  else
  {
    v127 = *((_DWORD *)a2 + 44);
    *((_DWORD *)v100 + 295) = v127;
    if ( v127 > *((_DWORD *)this + 3844) )
    {
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        LODWORD(v150) = *((_DWORD *)this + 3844);
        LODWORD(v151) = *((_DWORD *)a2 + 44);
        v152 = (struct ID3D11Texture2D *)*((_QWORD *)a2 + 20);
        v153 = (struct ID3D11Device *)"Surface desktopScaleFactor too high, capping it";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          100,
          (unsigned int)&byte_1801A4377,
          v119,
          v120,
          (__int64)&v153,
          (__int64)&v152,
          (__int64)&v151,
          (__int64)&v150);
        v126 = 100;
      }
      v127 = *((_DWORD *)this + 3844);
      *((_DWORD *)v100 + 295) = v127;
    }
  }
  if ( *((_DWORD *)this + 2430) )
  {
    if ( *((_DWORD *)this + 3841) )
      v126 = *((_DWORD *)this + 3845);
    *((_DWORD *)v100 + 295) = v126;
  }
  else
  {
    v126 = v127;
  }
  if ( (int)v14 < 0 )
  {
    v137 = (const void *)*((_QWORD *)v100 + 2);
    if ( v137 )
    {
      UnmapViewOfFile(v137);
      *((_QWORD *)v100 + 2) = 0;
    }
    SurfaceNode::`scalar deleting destructor'(v100, v117);
    goto LABEL_287;
  }
  if ( *((_DWORD *)this + 3840) && (unsigned int)v126 >= *((_DWORD *)this + 3843) )
  {
    LODWORD(v151) = 100 * *((_DWORD *)a2 + 38) / v126;
    LODWORD(v150) = 100 * *((_DWORD *)a2 + 37) / v126;
    if ( PixelMap::SetupImage(
           (SurfaceNode *)((char *)v100 + 1144),
           (int)v151,
           (int)v150,
           32,
           (4 * (_DWORD)v151 + 15) & 0xFFFFFFF0,
           v140) )
    {
      v128 = (__int64 *)*((_QWORD *)v100 + 148);
      v129 = *((_QWORD *)v100 + 3);
      v148 = *((_DWORD *)a2 + 38);
      v149 = *((_DWORD *)a2 + 37);
      v130 = *v128;
      v147 = 0;
      v131 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, const char **))(v130 + 24))(
               v128,
               v129,
               (__int64)v100 + 1144,
               &v147);
      if ( v131 >= 0 )
      {
        *((_DWORD *)v100 + 294) = 1;
        PixelMap::SetAlpha((SurfaceNode *)((char *)v100 + 1144), *((_DWORD *)a2 + 43) == 1);
      }
      else if ( (unsigned int)dword_1801B76C8 > 3 )
      {
        LODWORD(v150) = v131;
        v151 = "ProcessUpdateEvent";
        v152 = (struct ID3D11Texture2D *)"Error pSurface->m_spSubsampler->SubSample Failed!";
        v153 = (struct ID3D11Device *)"HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          dword_1801B76C8,
          (unsigned int)&byte_1801A4337,
          v119,
          v120,
          (__int64)&v153,
          (__int64)&v152,
          (__int64)&v150,
          (__int64)&v151);
      }
    }
    else if ( (unsigned int)dword_1801B76C8 > 3 )
    {
      v152 = (struct ID3D11Texture2D *)"SetupImageForSIMD failed!  Reverting to non-downsampled behavior";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dword_1801B76C8,
        (unsigned int)word_1801A4302,
        v119,
        v120,
        (__int64)&v152,
        (__int64)&v151,
        (__int64)&v150);
    }
    LODWORD(v14) = 0;
  }
  if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    v132 = *((_QWORD *)v100 + 3);
    LODWORD(v150) = *((_DWORD *)v100 + 287);
    LODWORD(v151) = *((_DWORD *)v100 + 286);
    LODWORD(v152) = *((_DWORD *)v100 + 294);
    LODWORD(v153) = *((_DWORD *)a2 + 36);
    LODWORD(v143) = *(_DWORD *)(v132 + 60);
    *(_DWORD *)v142 = *(_DWORD *)(v132 + 56);
    v147 = *(const char **)v100;
    v146[0] = "Surface mapped";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v132,
      (unsigned int)&byte_1801A423F,
      v119,
      v120,
      (__int64)v146,
      (__int64)&v147,
      (__int64)v142,
      (__int64)&v143,
      (__int64)&v153,
      (__int64)&v152,
      (__int64)&v151,
      (__int64)&v150);
  }
  SurfaceNode::InitDirtyRegionUpdate(v100, *(_QWORD *)v100);
  (*(void (__fastcall **)(char *, SurfaceNode *))(*((_QWORD *)this + 1570) + 8LL))((char *)this + 12560, v100);
  v133 = operator new(0x448u);
  v10 = v133;
  if ( !v133 )
  {
    LODWORD(v14) = -2147024882;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_287;
    LODWORD(v150) = 2406;
    v152 = (struct ID3D11Texture2D *)"BYTE allocation failed";
    v16 = (char *)&unk_1801A42B0;
    v147 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
    v146[0] = "Error condition failed";
    v141 = &v147;
    v17 = (unsigned __int8 *)v146;
    LODWORD(v151) = -2147024882;
    goto LABEL_9;
  }
  *v133 = 1096;
  v133[1] = 11;
  *((_QWORD *)v133 + 1) = *((_QWORD *)a2 + 20);
  if ( *((_DWORD *)v100 + 294) )
    v134 = *((_DWORD *)v100 + 286);
  else
    v134 = *((_DWORD *)a2 + 38);
  v10[270] = v134;
  if ( *((_DWORD *)v100 + 294) )
    v135 = *((_DWORD *)v100 + 287);
  else
    v135 = *((_DWORD *)a2 + 37);
  v10[271] = v135;
  if ( *((_DWORD *)a2 + 42) == 1 )
    v136 = (*((_DWORD *)a2 + 43) != 0) + 2;
  else
    v136 = 4;
  v10[272] = v136;
  *((_DWORD *)v100 + 574) = v136;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1562) + 8LL))((char *)this + 12496);
  if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    v96 = "UMRDP_CREATE_SURFACE stop";
    v97 = &byte_1801A41EF;
    goto LABEL_194;
  }
LABEL_287:
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v144, v10, v11);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180028450  push    rbp
0x180028452  push    rbx
0x180028453  push    rsi
0x180028454  push    rdi
0x180028455  push    r12
0x180028457  push    r13
0x180028459  push    r14
0x18002845b  push    r15
0x18002845d  lea     rbp, [rsp-1Fh]
0x180028462  sub     rsp, 0B8h
0x180028469  mov     r15d, [rdx]
0x18002846c  xor     r12d, r12d
0x18002846f  mov     r14, rcx
0x180028472  mov     ebx, r12d
0x180028475  add     rcx, 25E0h
0x18002847c  mov     [rbp+57h+var_70], rbx
0x180028480  mov     rsi, rdx
0x180028483  mov     [rbp+57h+arg_0], rcx
0x180028487  cmp     [rcx+8], r12d
0x18002848b  jz      short loc_180028496
0x18002848d  mov     rcx, [rcx]
0x180028490  call    cs:__imp_PAL_System_CritSecEnter
0x180028496  mov     rdi, r12
0x180028499  cmp     [r14+3140h], r12
0x1800284a0  jz      short loc_1800284C2
0x1800284a2  lea     rcx, [rbp+57h+var_70]
0x1800284a6  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800284ab  mov     rbx, [r14+3140h]
0x1800284b2  lea     rcx, [rbp+57h+var_70]
0x1800284b6  mov     [rbp+57h+var_70], rbx
0x1800284ba  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800284bf  mov     rdi, rbx
0x1800284c2  lea     rcx, [rbp+57h+arg_0]; this
0x1800284c6  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800284cb  test    rdi, rdi
0x1800284ce  jnz     loc_180028567
0x1800284d4  mov     eax, cs:dword_1801B76C8
0x1800284da  mov     ecx, 80004003h
0x1800284df  mov     edi, ecx
0x1800284e1  cmp     eax, 2
0x1800284e4  jbe     loc_18002A56D
0x1800284ea  lea     rax, aSpvideodriverI_0; "spVideoDriver is NULL"
0x1800284f1  mov     dword ptr [rbp+57h+arg_0], 853h
0x1800284f8  mov     dword ptr [rbp+57h+arg_8], ecx
0x1800284fb  lea     rdx, byte_1801A46DB
0x180028502  mov     [rbp+57h+arg_10], rax
0x180028506  lea     r12, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x18002850d  lea     rax, aErrorCondition; "Error condition failed"
0x180028514  mov     [rbp+57h+var_78], r12
0x180028518  mov     qword ptr [rbp+57h+var_80], rax
0x18002851c  lea     rax, [rbp+57h+arg_10]
0x180028520  mov     qword ptr [rsp+0F0h+var_A8], rax
0x180028525  lea     rax, [rbp+57h+arg_18]
0x180028529  mov     qword ptr [rsp+0F0h+var_B0], rax
0x18002852e  lea     rax, [rbp+57h+arg_0]
0x180028532  mov     qword ptr [rsp+0F0h+var_B8], rax
0x180028537  lea     rax, [rbp+57h+var_78]
0x18002853b  mov     qword ptr [rsp+0F0h+var_C0], rax
0x180028540  lea     rax, [rbp+57h+arg_8]
0x180028544  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180028549  lea     rax, [rbp+57h+var_80]
0x18002854d  lea     r15, aProcessupdatee; "ProcessUpdateEvent"
0x180028554  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180028559  mov     [rbp+57h+arg_18], r15
0x18002855d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180028562  jmp     loc_18002A56D
0x180028567  cmp     r15d, 4
0x18002856b  jnz     short loc_18002858C
0x18002856d  mov     r8d, [rsi+90h]; unsigned __int64
0x180028574  lea     rdx, [rsi+10h]; unsigned __int16 *
0x180028578  mov     r9d, [rsi+94h]; unsigned int
0x18002857f  mov     rcx, r14; this
0x180028582  call    ?MapFrameBuffer@CPipeGfxProvider@@IEAAJPEAG_KK@Z; CPipeGfxProvider::MapFrameBuffer(ushort *,unsigned __int64,ulong)
0x180028587  jmp     loc_180028624
0x18002858c  mov     ecx, [r14+3C24h]
0x180028593  test    ecx, ecx
0x180028595  jnz     loc_18002862C
0x18002859b  cmp     r15d, 14h
0x18002859f  jnz     loc_18002862C
0x1800285a5  mov     rax, [rdi]
0x1800285a8  lea     rdx, [rsi+10h]
0x1800285ac  mov     r8d, [rsi+90h]
0x1800285b3  mov     rcx, rdi
0x1800285b6  mov     rax, [rax+78h]
0x1800285ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285bf  mov     ecx, eax
0x1800285c1  test    eax, eax
0x1800285c3  jns     short loc_180028624
0x1800285c5  mov     eax, cs:dword_1801B76C8
0x1800285cb  cmp     eax, 3
0x1800285ce  jbe     short loc_180028624
0x1800285d0  lea     rax, aFailedToMapcur; "Failed to MapCursorSharedBuffer"
0x1800285d7  mov     dword ptr [rbp+57h+arg_0], ecx
0x1800285da  mov     [rbp+57h+arg_10], rax
0x1800285de  lea     r15, aProcessupdatee; "ProcessUpdateEvent"
0x1800285e5  lea     rax, aHresultFailedB; "HResult failed but continue"
0x1800285ec  mov     [rbp+57h+arg_8], r15
0x1800285f0  mov     [rbp+57h+arg_18], rax
0x1800285f4  lea     rdx, byte_1801A472D
0x1800285fb  lea     rax, [rbp+57h+arg_8]
0x1800285ff  mov     qword ptr [rsp+0F0h+var_B8], rax
0x180028604  lea     rax, [rbp+57h+arg_0]
0x180028608  mov     qword ptr [rsp+0F0h+var_C0], rax
0x18002860d  lea     rax, [rbp+57h+arg_10]
0x180028611  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180028616  lea     rax, [rbp+57h+arg_18]
0x18002861a  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18002861f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180028624  mov     edi, r12d
0x180028627  jmp     loc_18002A56D
0x18002862c  mov     edi, r12d
0x18002862f  test    r15d, r15d
0x180028632  jnz     short loc_180028644
0x180028634  mov     rdx, rsi; struct UMRDP_DRAWING_EVENT_HEADER *
0x180028637  mov     rcx, r14; this
0x18002863a  call    ?ProcessDirtyRegionEvent@CPipeGfxProvider@@IEAAJPEAUUMRDP_DRAWING_EVENT_HEADER@@@Z; CPipeGfxProvider::ProcessDirtyRegionEvent(UMRDP_DRAWING_EVENT_HEADER *)
0x18002863f  jmp     loc_18002A56D
0x180028644  cmp     r15d, 5
0x180028648  jnz     short loc_1800286A5
0x18002864a  mov     r15d, [rsi+4]
0x18002864e  add     r15d, 0FFFFFFF0h
0x180028652  mov     r13d, r15d
0x180028655  lea     rcx, [r15+430h]; Size
0x18002865c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028661  mov     rbx, rax
0x180028664  test    rax, rax
0x180028667  jnz     short loc_18002869C
0x180028669  mov     eax, cs:dword_1801B76C8
0x18002866f  mov     ebx, 8007000Eh
0x180028674  mov     edi, ebx
0x180028676  cmp     eax, 2
0x180028679  jbe     loc_18002A56D
0x18002867f  lea     rax, aByteAllocation_0; "BYTE allocation failed"
0x180028686  mov     dword ptr [rbp+57h+arg_0], 87Ah
0x18002868d  mov     dword ptr [rbp+57h+arg_8], ebx
0x180028690  lea     rdx, byte_1801A4637
0x180028697  jmp     loc_180028502
0x18002869c  mov     dword ptr [rbx+4], 8
0x1800286a3  jmp     short loc_180028708
0x1800286a5  cmp     r15d, 6
0x1800286a9  jnz     loc_18002873F
0x1800286af  mov     r15d, [rsi+4]
0x1800286b3  add     r15d, 0FFFFFFF0h
0x1800286b7  mov     r13d, r15d
0x1800286ba  lea     rcx, [r15+430h]; Size
0x1800286c1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800286c6  mov     rbx, rax
0x1800286c9  test    rax, rax
0x1800286cc  jnz     short loc_180028701
0x1800286ce  mov     eax, cs:dword_1801B76C8
0x1800286d4  mov     ebx, 8007000Eh
0x1800286d9  mov     edi, ebx
0x1800286db  cmp     eax, 2
0x1800286de  jbe     loc_18002A56D
0x1800286e4  lea     rax, aByteAllocation_0; "BYTE allocation failed"
0x1800286eb  mov     dword ptr [rbp+57h+arg_0], 88Dh
0x1800286f2  mov     dword ptr [rbp+57h+arg_8], ebx
0x1800286f5  lea     rdx, byte_1801A4689
0x1800286fc  jmp     loc_180028502
0x180028701  mov     dword ptr [rbx+4], 7
0x180028708  lea     eax, [r15+430h]
0x18002870f  mov     r8, r13; Size
0x180028712  lea     rdx, [rsi+10h]; Src
0x180028716  mov     [rbx], eax
0x180028718  lea     rcx, [rbx+430h]; void *
0x18002871f  call    memcpy_0
0x180028724  lea     rcx, [r14+30B0h]
0x18002872b  mov     rdx, rbx
0x18002872e  mov     rax, [rcx]
0x180028731  mov     rax, [rax+8]
0x180028735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002873a  jmp     loc_18002A56D
0x18002873f  mov     r13d, 1
0x180028745  cmp     r15d, r13d
0x180028748  jnz     short loc_18002876A
0x18002874a  mov     eax, [rsi+10h]
0x18002874d  mov     [r14+3070h], eax
0x180028754  mov     eax, [rsi+14h]
0x180028757  mov     [r14+3074h], eax
0x18002875e  mov     [r14+3134h], r13d
0x180028765  jmp     loc_18002A56D
0x18002876a  lea     eax, [r15-2]
0x18002876e  cmp     eax, r13d
0x180028771  jbe     loc_18002A560
0x180028777  cmp     r15d, 0Ah
0x18002877b  jz      loc_180029B0A
0x180028781  test    ecx, ecx
0x180028783  jnz     loc_1800292A9
0x180028789  cmp     r15d, 13h
0x18002878d  jz      loc_180029B0A
0x180028793  cmp     r15d, 15h
0x180028797  jnz     loc_180028FCA
0x18002879d  mov     eax, cs:dword_1801B76C8
0x1800287a3  cmp     eax, 4
0x1800287a6  jbe     short loc_1800287D9
0x1800287a8  mov     rax, [rsi+18h]
0x1800287ac  lea     rdx, byte_1801A4215
0x1800287b3  mov     [rbp+57h+arg_0], rax
0x1800287b7  lea     rax, aProcessingUmrd_1; "Processing UMRDP_CREATE_SURFACE_DXTEXTU"...
0x1800287be  mov     [rbp+57h+arg_8], rax
0x1800287c2  lea     rax, [rbp+57h+arg_0]
0x1800287c6  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1800287cb  lea     rax, [rbp+57h+arg_8]
0x1800287cf  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800287d4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800287d9  mov     ecx, 900h; Size
0x1800287de  mov     [rbp+57h+arg_18], r12
0x1800287e2  mov     [rbp+57h+arg_10], r12
0x1800287e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800287eb  test    rax, rax
0x1800287ee  jz      loc_180028F29
0x1800287f4  mov     rcx, rax; this
0x1800287f7  call    ??0SurfaceNode@@QEAA@XZ; SurfaceNode::SurfaceNode(void)
0x1800287fc  mov     r13, rax
0x1800287ff  test    rax, rax
0x180028802  jz      loc_180028F29
0x180028808  mov     rax, [rsi+18h]
0x18002880c  lea     rdx, [rbp+57h+arg_18]; struct ID3D11Device **
0x180028810  mov     [r13+0], rax
0x180028814  mov     r12, [rsi+20h]
0x180028818  mov     r8, r12; void *
0x18002881b  call    ?GetD3D11DeviceFromSharedHandle@CPipeGfxProvider@@IEAAJPEAPEAUID3D11Device@@PEAX@Z; CPipeGfxProvider::GetD3D11DeviceFromSharedHandle(ID3D11Device * *,void *)
0x180028820  mov     rbx, [rbp+57h+arg_18]
0x180028824  mov     edi, eax
0x180028826  test    eax, eax
0x180028828  jnz     short loc_18002884A
0x18002882a  test    rbx, rbx
0x18002882d  jz      short loc_18002884A
0x18002882f  mov     ecx, cs:dword_1801B76C8
0x180028835  cmp     ecx, 4
0x180028838  jbe     short loc_180028875
0x18002883a  lea     rax, aD3d11DeviceSuc; "D3D11 device successfully created"
0x180028841  lea     rdx, byte_1801A41C9
0x180028848  jmp     short loc_180028863
0x18002884a  mov     eax, cs:dword_1801B76C8
0x180028850  cmp     eax, 3
0x180028853  jbe     short loc_180028875
0x180028855  lea     rax, aFailedToCreate_14; "Failed to create the D3D11 device from "...
0x18002885c  lea     rdx, byte_1801A4151
0x180028863  mov     [rbp+57h+arg_0], rax
0x180028867  lea     rax, [rbp+57h+arg_0]
0x18002886b  mov     qword ptr [rsp+0F0h+var_D0], rax
0x180028870  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180028875  lea     r15, aProcessupdatee; "ProcessUpdateEvent"
0x18002887c  test    rbx, rbx
0x18002887f  jz      loc_180028B0F
0x180028885  mov     [rbp+57h+var_78], 0
0x18002888d  lea     r8, [rbp+57h+var_78]
0x180028891  mov     rax, [rbx]
0x180028894  lea     rdx, _GUID_a04bfb29_08ef_43d6_a49c_a9bdbdcbe686
0x18002889b  mov     rcx, rbx
0x18002889e  mov     rax, [rax]
0x1800288a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288a6  lea     rbx, aHresultFailedB; "HResult failed but continue"
0x1800288ad  test    eax, eax
0x1800288af  jns     short loc_180028902
0x1800288b1  mov     ecx, cs:dword_1801B76C8
0x1800288b7  cmp     ecx, 3
0x1800288ba  jbe     short loc_180028902
0x1800288bc  mov     dword ptr [rbp+57h+arg_0], eax
0x1800288bf  lea     rdx, byte_1801A4111
0x1800288c6  lea     rax, aQueryinterface; "QueryInterface ID3D11Device1 failed"
0x1800288cd  mov     [rbp+57h+arg_8], r15
0x1800288d1  mov     qword ptr [rbp+57h+var_80], rax
0x1800288d5  lea     rax, [rbp+57h+arg_8]
0x1800288d9  mov     qword ptr [rsp+0F0h+var_B8], rax
0x1800288de  lea     rax, [rbp+57h+arg_0]
0x1800288e2  mov     qword ptr [rsp+0F0h+var_C0], rax
0x1800288e7  lea     rax, [rbp+57h+var_80]
0x1800288eb  mov     qword ptr [rsp+0F0h+var_C8], rax; unsigned __int8
0x1800288f0  lea     rax, [rbp+57h+var_68]
0x1800288f4  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1800288f9  mov     [rbp+57h+var_68], rbx
0x1800288fd  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180028902  mov     rcx, [rbp+57h+var_78]
0x180028906  lea     r9, [rbp+57h+arg_10]
0x18002890a  lea     r8, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x180028911  mov     rdx, r12
0x180028914  mov     rax, [rcx]
0x180028917  mov     rax, [rax+180h]
0x18002891e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028923  mov     edi, eax
0x180028925  test    eax, eax
0x180028927  jns     short loc_180028983
0x180028929  mov     eax, cs:dword_1801B76C8
0x18002892f  cmp     eax, 3
0x180028932  jbe     loc_180028AF2
0x180028938  lea     rax, aSpd3d11device1; "spD3D11Device1->OpenSharedResource1 fai"...
0x18002893f  mov     [rbp+57h+arg_8], r15
0x180028943  mov     [rbp+57h+var_68], rax
0x180028947  lea     rdx, byte_1801A407F
0x18002894e  lea     rax, [rbp+57h+arg_8]
0x180028952  mov     dword ptr [rbp+57h+arg_0], edi
0x180028955  mov     qword ptr [rsp+0F0h+var_B8], rax
0x18002895a  lea     rax, [rbp+57h+arg_0]
0x18002895e  mov     qword ptr [rsp+0F0h+var_C0], rax
0x180028963  lea     rax, [rbp+57h+var_68]
0x180028967  mov     qword ptr [rsp+0F0h+var_C8], rax
0x18002896c  lea     rax, [rbp+57h+var_80]
0x180028970  mov     qword ptr [rsp+0F0h+var_D0], rax
  ... truncated ...
```
