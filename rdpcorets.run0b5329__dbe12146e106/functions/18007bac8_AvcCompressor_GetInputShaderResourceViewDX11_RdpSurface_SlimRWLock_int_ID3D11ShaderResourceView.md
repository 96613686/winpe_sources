# AvcCompressor::GetInputShaderResourceViewDX11(RdpSurface *,SlimRWLock * *,int &,ID3D11ShaderResourceView * *)

- ea: `0x18007bac8`
- end: `0x18007c285`
- name: `?GetInputShaderResourceViewDX11@AvcCompressor@@IEAAJPEAVRdpSurface@@PEAPEAVSlimRWLock@@AEAHPEAPEAUID3D11ShaderResourceView@@@Z`
- size: `1981`
- prototype: `__int64 __fastcall(AvcCompressor *__hidden this, struct RdpSurface *, struct SlimRWLock **, int *, struct ID3D11ShaderResourceView **)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007d060`
- `0x18007d5a0`

## callees

- `0x1800015f0`
- `0x1800071c0`
- `0x1800071f0`
- `0x180059838`
- `0x18007bac8`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007c05c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007c05c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007c1fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007c1fd`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18007bd7f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18007bd7f`
- `RDPSERVERBASE!?GetGraphicsSourceContext@RdpSurface@@QEAAJPEAPEAUIRdpGFXSourceUpdateContext@@@Z` at `0x18007bb32`
- `RDPSERVERBASE!?GetGraphicsSourceContext@RdpSurface@@QEAAJPEAPEAUIRdpGFXSourceUpdateContext@@@Z` at `0x18007bb32`

## string_xrefs

- `0x18007bb78`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007bc0b`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007bd0d`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007be4a`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007bebf`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007bf4e`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007c00c`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007c0be`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007c174`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007bb51`: `Failed to get update context`
- `0x18007bbe7`: `spGfxSrcUpdateContext is NULL`
- `0x18007be23`: `CreateShaderResourceView failed`

## pseudocode

```c
__int64 __fastcall AvcCompressor::GetInputShaderResourceViewDX11(
        AvcCompressor *this,
        struct RdpSurface *a2,
        PSRWLOCK *a3,
        int *a4,
        struct ID3D11ShaderResourceView **a5)
{
  __int64 v8; // rdx
  int GraphicsSourceContext; // ebx
  __int64 v10; // r8
  int v11; // r9d
  int v12; // ecx
  const char *v13; // rax
  __int16 *v14; // rdx
  const char *v15; // rax
  __int64 v16; // rcx
  unsigned int ActivityIdPrefix; // eax
  int v18; // ecx
  int v19; // r9d
  int v20; // ecx
  const char *v21; // rax
  __int16 *v22; // rdx
  const char *v23; // rax
  const char *v24; // rcx
  const char *v25; // rcx
  __int64 v26; // rdx
  const char *v27; // rcx
  struct ID3D11ShaderResourceView *v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 (__fastcall ***v32)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v33; // rdx
  __int64 v34; // r8
  struct IRdpGFXSourceUpdateContext *v35; // rcx
  const char *v37; // [rsp+50h] [rbp-51h] BYREF
  const char *v38; // [rsp+58h] [rbp-49h] BYREF
  const char *v39; // [rsp+60h] [rbp-41h] BYREF
  const char *v40; // [rsp+68h] [rbp-39h] BYREF
  const char *v41; // [rsp+70h] [rbp-31h] BYREF
  __int64 v42; // [rsp+78h] [rbp-29h] BYREF
  struct ID3D11ShaderResourceView *v43; // [rsp+80h] [rbp-21h] BYREF
  struct IRdpGFXSourceUpdateContext *v44; // [rsp+88h] [rbp-19h] BYREF
  PSRWLOCK SRWLock; // [rsp+90h] [rbp-11h] BYREF
  __int64 v46; // [rsp+98h] [rbp-9h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64 *); // [rsp+A0h] [rbp-1h] BYREF
  __int64 v48; // [rsp+A8h] [rbp+7h] BYREF
  int v49; // [rsp+B0h] [rbp+Fh] BYREF
  __int64 v50; // [rsp+B4h] [rbp+13h]
  int v51; // [rsp+BCh] [rbp+1Bh]
  __int64 v52; // [rsp+C0h] [rbp+1Fh]
  AvcCompressor *v53; // [rsp+100h] [rbp+5Fh] BYREF
  int v54; // [rsp+118h] [rbp+77h] BYREF

  v53 = this;
  SRWLock = 0;
  *a4 = 0;
  v44 = 0;
  v48 = 0;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v48);
  v42 = 0;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v42);
  v47 = 0;
  v43 = 0;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v43);
  v46 = 0;
  GraphicsSourceContext = RdpSurface::GetGraphicsSourceContext(a2, &v44);
  if ( GraphicsSourceContext < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v53) = 2102;
      v37 = "Failed to get update context";
      v54 = GraphicsSourceContext;
      v38 = "GetInputShaderResourceViewDX11";
      v39 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
      v40 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)word_18019D7AA,
        v10,
        v11,
        (__int64)&v40,
        (__int64)&v54,
        (__int64)&v39,
        (__int64)&v53,
        (__int64)&v38,
        (__int64)&v37);
    }
    goto LABEL_60;
  }
  if ( v44 )
  {
    if ( (**(int (__fastcall ***)(struct IRdpGFXSourceUpdateContext *, GUID *, __int64 *))v44)(
           v44,
           &IID_IRdpGfxSrcDxTextureProvider,
           &v46) >= 0 )
    {
      if ( !v46 )
      {
        v12 = -2147467261;
        GraphicsSourceContext = -2147467261;
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_60;
        v13 = "spGfxSrcDxTextureProvider is NULL";
        LODWORD(v53) = 2108;
        v14 = &word_18019D756;
        goto LABEL_7;
      }
      GraphicsSourceContext = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v46 + 24LL))(
                                v46,
                                *((unsigned int *)a2 + 156),
                                &v42);
      if ( GraphicsSourceContext < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_60;
        LODWORD(v53) = 2113;
        v40 = "Failed to get DX texture";
        v14 = &word_18019D6AE;
        v54 = GraphicsSourceContext;
        v39 = "GetInputShaderResourceViewDX11";
        v38 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
        v15 = "Error HResult failed";
        goto LABEL_8;
      }
      v16 = v42;
      if ( !v42 )
      {
        v12 = -2147467261;
        GraphicsSourceContext = -2147467261;
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_60;
        v13 = "spD3D11Texture2D is NULL";
        LODWORD(v53) = 2115;
        v14 = word_18019D702;
        goto LABEL_7;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(v42);
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          &WPP_1c5fb9514b053585536f3862527bab66_Traceguids,
          ActivityIdPrefix);
        v16 = v42;
      }
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 24LL))(v16, &v48);
      v52 = 0;
      v49 = 87;
      v50 = 4;
      v51 = 1;
      GraphicsSourceContext = (*(__int64 (__fastcall **)(__int64, __int64, int *, struct ID3D11ShaderResourceView **))(*(_QWORD *)v48 + 56LL))(
                                v48,
                                v42,
                                &v49,
                                &v43);
      if ( GraphicsSourceContext < 0 )
      {
        if ( v42 )
        {
          TCntPtr<IRdpSQMLogger>::SafeRelease(&v42, v8, v10);
          v42 = 0;
          TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v42);
        }
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_60;
        LODWORD(v53) = 2137;
        v40 = "CreateShaderResourceView failed";
        v14 = word_18019D65A;
        v54 = GraphicsSourceContext;
        v39 = "GetInputShaderResourceViewDX11";
        v38 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
        v15 = "Error HResult failed";
        goto LABEL_8;
      }
LABEL_59:
      v28 = v43;
      v43 = 0;
      *a5 = v28;
      *a3 = SRWLock;
      goto LABEL_62;
    }
    v37 = 0;
    GraphicsSourceContext = (**(__int64 (__fastcall ***)(struct IRdpGFXSourceUpdateContext *, GUID *, const char **))v44)(
                              v44,
                              &IID_ICaGfxSourceProgressive,
                              &v37);
    if ( GraphicsSourceContext < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v53) = 2144;
        v40 = "Failed to query ICaGfxSourceProgressive";
        v54 = GraphicsSourceContext;
        v39 = "GetInputShaderResourceViewDX11";
        v38 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
        v41 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v18,
          (unsigned int)word_18019D5B2,
          v10,
          v19,
          (__int64)&v41,
          (__int64)&v54,
          (__int64)&v38,
          (__int64)&v53,
          (__int64)&v39,
          (__int64)&v40);
      }
      goto LABEL_37;
    }
    if ( !v37 )
    {
      v20 = -2147467261;
      GraphicsSourceContext = -2147467261;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_37;
      v21 = "spCaGfxProvider is NULL";
      LODWORD(v53) = 2146;
      v22 = &word_18019D606;
      goto LABEL_35;
    }
    GraphicsSourceContext = (*(__int64 (__fastcall **)(const char *, PSRWLOCK *))(*(_QWORD *)v37 + 56LL))(v37, &SRWLock);
    if ( GraphicsSourceContext < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v53) = 2149;
        v41 = "Failed to obtain device context lock";
        v22 = word_18019D50A;
        v54 = GraphicsSourceContext;
        v40 = "GetInputShaderResourceViewDX11";
        v39 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
        v23 = "Error HResult failed";
        goto LABEL_36;
      }
LABEL_37:
      v24 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v24 + 16LL))(v24);
      }
      goto LABEL_60;
    }
    if ( SRWLock )
    {
      AcquireSRWLockExclusive(SRWLock);
      v25 = v37;
      v26 = *((unsigned int *)a2 + 156);
      *a4 = 1;
      GraphicsSourceContext = (*(__int64 (__fastcall **)(const char *, __int64, struct ID3D11ShaderResourceView **))(*(_QWORD *)v25 + 48LL))(
                                v25,
                                v26,
                                &v43);
      if ( GraphicsSourceContext < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v53) = 2157;
          v41 = "Failed to get encoding input surface X11";
          v22 = &word_18019D4B6;
          v54 = GraphicsSourceContext;
          v40 = "GetInputShaderResourceViewDX11";
          v39 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
          v23 = "Error HResult failed";
          goto LABEL_36;
        }
        goto LABEL_37;
      }
      if ( v43 )
      {
        ((void (__fastcall *)(struct ID3D11ShaderResourceView *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))v43->lpVtbl->GetResource)(
          v43,
          &v47);
        GraphicsSourceContext = (**v47)(v47, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v42);
        if ( GraphicsSourceContext < 0 )
        {
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v53) = 2164;
            v41 = "Failed to query ID3D11Texture2D";
            v22 = word_18019D462;
            v54 = GraphicsSourceContext;
            v40 = "GetInputShaderResourceViewDX11";
            v39 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
            v23 = "Error HResult failed";
            goto LABEL_36;
          }
          goto LABEL_37;
        }
        if ( v42 )
        {
          v27 = v37;
          if ( v37 )
          {
            v37 = 0;
            (*(void (__fastcall **)(const char *))(*(_QWORD *)v27 + 16LL))(v27);
          }
          goto LABEL_59;
        }
        v20 = -2147467261;
        GraphicsSourceContext = -2147467261;
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_37;
        v21 = "spD3D11Texture2D is NULL";
        LODWORD(v53) = 2166;
        v22 = &word_18019D366;
      }
      else
      {
        v20 = -2147467261;
        GraphicsSourceContext = -2147467261;
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_37;
        v21 = "spInputSRV is NULL";
        LODWORD(v53) = 2159;
        v22 = &word_18019D40E;
      }
    }
    else
    {
      v20 = -2147467261;
      GraphicsSourceContext = -2147467261;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_37;
      v21 = "pDeviceCtxLock is NULL";
      LODWORD(v53) = 2151;
      v22 = &word_18019D55E;
    }
LABEL_35:
    v41 = v21;
    v40 = "GetInputShaderResourceViewDX11";
    v39 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
    v23 = "Error condition failed";
    v54 = -2147467261;
LABEL_36:
    v38 = v23;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v20,
      (_DWORD)v22,
      v10,
      v19,
      (__int64)&v38,
      (__int64)&v54,
      (__int64)&v39,
      (__int64)&v53,
      (__int64)&v40,
      (__int64)&v41);
    goto LABEL_37;
  }
  v12 = -2147467261;
  GraphicsSourceContext = -2147467261;
  if ( (unsigned int)dword_1801B76C8 <= 2 )
    goto LABEL_60;
  v13 = "spGfxSrcUpdateContext is NULL";
  LODWORD(v53) = 2104;
  v14 = &word_18019D7FE;
LABEL_7:
  v40 = v13;
  v39 = "GetInputShaderResourceViewDX11";
  v38 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
  v15 = "Error condition failed";
  v54 = -2147467261;
LABEL_8:
  v37 = v15;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
    v12,
    (_DWORD)v14,
    v10,
    v11,
    (__int64)&v37,
    (__int64)&v54,
    (__int64)&v38,
    (__int64)&v53,
    (__int64)&v39,
    (__int64)&v40);
LABEL_60:
  if ( *a4 )
  {
    ReleaseSRWLockExclusive(SRWLock);
    *a4 = 0;
  }
LABEL_62:
  v29 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v43, v8, v10);
  v32 = v47;
  if ( v47 )
  {
    v47 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v32)[2])(v32);
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v42, v30, v31);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v48, v33, v34);
  v35 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(struct IRdpGFXSourceUpdateContext *))(*(_QWORD *)v35 + 16LL))(v35);
  }
  return (unsigned int)GraphicsSourceContext;
}

```

## disassembly

```asm
0x18007bac8  mov     [rsp-8+arg_8], rbx
0x18007bacd  mov     [rsp-8+arg_0], rcx
0x18007bad2  push    rbp
0x18007bad3  push    rsi
0x18007bad4  push    rdi
0x18007bad5  push    r14
0x18007bad7  push    r15
0x18007bad9  lea     rbp, [rsp-2Fh]
0x18007bade  sub     rsp, 0D0h
0x18007bae5  xor     r15d, r15d
0x18007bae8  lea     rcx, [rbp+4Fh+var_48]
0x18007baec  mov     [rbp+4Fh+SRWLock], r15
0x18007baf0  mov     rsi, r9
0x18007baf3  mov     [r9], r15d
0x18007baf6  mov     r14, r8
0x18007baf9  mov     [rbp+4Fh+var_68], r15
0x18007bafd  mov     rdi, rdx
0x18007bb00  mov     [rbp+4Fh+var_48], r15
0x18007bb04  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18007bb09  lea     rcx, [rbp+4Fh+var_78]
0x18007bb0d  mov     [rbp+4Fh+var_78], r15
0x18007bb11  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18007bb16  lea     rcx, [rbp+4Fh+var_70]
0x18007bb1a  mov     [rbp+4Fh+var_50], r15
0x18007bb1e  mov     [rbp+4Fh+var_70], r15
0x18007bb22  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18007bb27  lea     rdx, [rbp+4Fh+var_68]
0x18007bb2b  mov     [rbp+4Fh+var_58], r15
0x18007bb2f  mov     rcx, rdi
0x18007bb32  call    cs:__imp_?GetGraphicsSourceContext@RdpSurface@@QEAAJPEAPEAUIRdpGFXSourceUpdateContext@@@Z; RdpSurface::GetGraphicsSourceContext(IRdpGFXSourceUpdateContext * *)
0x18007bb38  mov     ebx, eax
0x18007bb3a  test    eax, eax
0x18007bb3c  jns     loc_18007BBC4
0x18007bb42  mov     ecx, cs:dword_1801B76C8
0x18007bb48  cmp     ecx, 2
0x18007bb4b  jbe     loc_18007C1F4
0x18007bb51  lea     rax, aFailedToGetUpd; "Failed to get update context"
0x18007bb58  mov     dword ptr [rbp+4Fh+arg_0], 836h
0x18007bb5f  mov     [rbp+4Fh+var_A0], rax
0x18007bb63  lea     rdx, word_18019D7AA
0x18007bb6a  lea     rax, aGetinputshader; "GetInputShaderResourceViewDX11"
0x18007bb71  mov     [rbp+4Fh+arg_18], ebx
0x18007bb74  mov     [rbp+4Fh+var_98], rax
0x18007bb78  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007bb7f  mov     [rbp+4Fh+var_90], rax
0x18007bb83  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007bb8a  mov     [rbp+4Fh+var_88], rax
0x18007bb8e  lea     rax, [rbp+4Fh+var_A0]
0x18007bb92  mov     [rsp+0F0h+var_A8], rax
0x18007bb97  lea     rax, [rbp+4Fh+var_98]
0x18007bb9b  mov     [rsp+0F0h+var_B0], rax
0x18007bba0  lea     rax, [rbp+4Fh+arg_0]
0x18007bba4  mov     [rsp+0F0h+var_B8], rax
0x18007bba9  lea     rax, [rbp+4Fh+var_90]
0x18007bbad  mov     [rsp+0F0h+var_C0], rax
0x18007bbb2  lea     rax, [rbp+4Fh+arg_18]
0x18007bbb6  mov     [rsp+0F0h+var_C8], rax
0x18007bbbb  lea     rax, [rbp+4Fh+var_88]
0x18007bbbf  jmp     loc_18007BC55
0x18007bbc4  mov     rcx, [rbp+4Fh+var_68]
0x18007bbc8  test    rcx, rcx
0x18007bbcb  jnz     loc_18007BC64
0x18007bbd1  mov     eax, cs:dword_1801B76C8
0x18007bbd7  mov     ecx, 80004003h
0x18007bbdc  mov     ebx, ecx
0x18007bbde  cmp     eax, 2
0x18007bbe1  jbe     loc_18007C1F4
0x18007bbe7  lea     rax, aSpgfxsrcupdate; "spGfxSrcUpdateContext is NULL"
0x18007bbee  mov     dword ptr [rbp+4Fh+arg_0], 838h
0x18007bbf5  lea     rdx, word_18019D7FE
0x18007bbfc  mov     [rbp+4Fh+var_88], rax
0x18007bc00  lea     rax, aGetinputshader; "GetInputShaderResourceViewDX11"
0x18007bc07  mov     [rbp+4Fh+var_90], rax
0x18007bc0b  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007bc12  mov     [rbp+4Fh+var_98], rax
0x18007bc16  lea     rax, aErrorCondition; "Error condition failed"
0x18007bc1d  mov     [rbp+4Fh+arg_18], ecx
0x18007bc20  mov     [rbp+4Fh+var_A0], rax
0x18007bc24  lea     rax, [rbp+4Fh+var_88]
0x18007bc28  mov     [rsp+0F0h+var_A8], rax
0x18007bc2d  lea     rax, [rbp+4Fh+var_90]
0x18007bc31  mov     [rsp+0F0h+var_B0], rax
0x18007bc36  lea     rax, [rbp+4Fh+arg_0]
0x18007bc3a  mov     [rsp+0F0h+var_B8], rax
0x18007bc3f  lea     rax, [rbp+4Fh+var_98]
0x18007bc43  mov     [rsp+0F0h+var_C0], rax
0x18007bc48  lea     rax, [rbp+4Fh+arg_18]
0x18007bc4c  mov     [rsp+0F0h+var_C8], rax
0x18007bc51  lea     rax, [rbp+4Fh+var_A0]
0x18007bc55  mov     [rsp+0F0h+var_D0], rax
0x18007bc5a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18007bc5f  jmp     loc_18007C1F4
0x18007bc64  mov     rax, [rcx]
0x18007bc67  lea     r8, [rbp+4Fh+var_58]
0x18007bc6b  lea     rdx, IID_IRdpGfxSrcDxTextureProvider
0x18007bc72  mov     rax, [rax]
0x18007bc75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bc7a  test    eax, eax
0x18007bc7c  js      loc_18007BE61
0x18007bc82  mov     rcx, [rbp+4Fh+var_58]
0x18007bc86  test    rcx, rcx
0x18007bc89  jnz     short loc_18007BCBB
0x18007bc8b  mov     eax, cs:dword_1801B76C8
0x18007bc91  mov     ecx, 80004003h
0x18007bc96  mov     ebx, ecx
0x18007bc98  cmp     eax, 2
0x18007bc9b  jbe     loc_18007C1F4
0x18007bca1  lea     rax, aSpgfxsrcdxtext; "spGfxSrcDxTextureProvider is NULL"
0x18007bca8  mov     dword ptr [rbp+4Fh+arg_0], 83Ch
0x18007bcaf  lea     rdx, word_18019D756
0x18007bcb6  jmp     loc_18007BBFC
0x18007bcbb  mov     rax, [rcx]
0x18007bcbe  lea     r8, [rbp+4Fh+var_78]
0x18007bcc2  mov     edx, [rdi+270h]
0x18007bcc8  mov     rax, [rax+18h]
0x18007bccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bcd1  mov     ebx, eax
0x18007bcd3  test    eax, eax
0x18007bcd5  jns     short loc_18007BD24
0x18007bcd7  mov     eax, cs:dword_1801B76C8
0x18007bcdd  cmp     eax, 2
0x18007bce0  jbe     loc_18007C1F4
0x18007bce6  lea     rax, aFailedToGetDxT; "Failed to get DX texture"
0x18007bced  mov     dword ptr [rbp+4Fh+arg_0], 841h
0x18007bcf4  mov     [rbp+4Fh+var_88], rax
0x18007bcf8  lea     rdx, word_18019D6AE
0x18007bcff  lea     rax, aGetinputshader; "GetInputShaderResourceViewDX11"
0x18007bd06  mov     [rbp+4Fh+arg_18], ebx
0x18007bd09  mov     [rbp+4Fh+var_90], rax
0x18007bd0d  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007bd14  mov     [rbp+4Fh+var_98], rax
0x18007bd18  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007bd1f  jmp     loc_18007BC20
0x18007bd24  mov     rcx, [rbp+4Fh+var_78]
0x18007bd28  test    rcx, rcx
0x18007bd2b  jnz     short loc_18007BD5D
0x18007bd2d  mov     eax, cs:dword_1801B76C8
0x18007bd33  mov     ecx, 80004003h
0x18007bd38  mov     ebx, ecx
0x18007bd3a  cmp     eax, 2
0x18007bd3d  jbe     loc_18007C1F4
0x18007bd43  lea     rax, aSpd3d11texture; "spD3D11Texture2D is NULL"
0x18007bd4a  mov     dword ptr [rbp+4Fh+arg_0], 843h
0x18007bd51  lea     rdx, word_18019D702
0x18007bd58  jmp     loc_18007BBFC
0x18007bd5d  mov     rax, cs:WPP_GLOBAL_Control
0x18007bd64  lea     rdx, WPP_GLOBAL_Control
0x18007bd6b  cmp     rax, rdx
0x18007bd6e  jz      short loc_18007BDA8
0x18007bd70  test    dword ptr [rax+1Ch], 100h
0x18007bd77  jz      short loc_18007BDA8
0x18007bd79  cmp     byte ptr [rax+19h], 5
0x18007bd7d  jb      short loc_18007BDA8
0x18007bd7f  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18007bd85  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bd8c  lea     r8, WPP_1c5fb9514b053585536f3862527bab66_Traceguids
0x18007bd93  mov     edx, 30h ; '0'
0x18007bd98  mov     r9d, eax
0x18007bd9b  mov     rcx, [rcx+10h]
0x18007bd9f  call    WPP_SF_d
0x18007bda4  mov     rcx, [rbp+4Fh+var_78]
0x18007bda8  mov     rax, [rcx]
0x18007bdab  lea     rdx, [rbp+4Fh+var_48]
0x18007bdaf  mov     rax, [rax+18h]
0x18007bdb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bdb8  mov     rcx, [rbp+4Fh+var_48]
0x18007bdbc  lea     r9, [rbp+4Fh+var_70]
0x18007bdc0  mov     rdx, [rbp+4Fh+var_78]
0x18007bdc4  lea     r8, [rbp+4Fh+var_40]
0x18007bdc8  mov     [rbp+4Fh+var_30], r15
0x18007bdcc  mov     [rbp+4Fh+var_40], 57h ; 'W'
0x18007bdd3  mov     [rbp+4Fh+var_3C], 4
0x18007bddb  mov     [rbp+4Fh+var_34], 1
0x18007bde2  mov     rax, [rcx]
0x18007bde5  mov     rax, [rax+38h]
0x18007bde9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bdee  mov     ebx, eax
0x18007bdf0  test    eax, eax
0x18007bdf2  jns     loc_18007C1DA
0x18007bdf8  cmp     [rbp+4Fh+var_78], r15
0x18007bdfc  jz      short loc_18007BE14
0x18007bdfe  lea     rcx, [rbp+4Fh+var_78]
0x18007be02  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18007be07  lea     rcx, [rbp+4Fh+var_78]
0x18007be0b  mov     [rbp+4Fh+var_78], r15
0x18007be0f  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18007be14  mov     eax, cs:dword_1801B76C8
0x18007be1a  cmp     eax, 2
0x18007be1d  jbe     loc_18007C1F4
0x18007be23  lea     rax, aCreateshaderre; "CreateShaderResourceView failed"
0x18007be2a  mov     dword ptr [rbp+4Fh+arg_0], 859h
0x18007be31  mov     [rbp+4Fh+var_88], rax
0x18007be35  lea     rdx, word_18019D65A
0x18007be3c  lea     rax, aGetinputshader; "GetInputShaderResourceViewDX11"
0x18007be43  mov     [rbp+4Fh+arg_18], ebx
0x18007be46  mov     [rbp+4Fh+var_90], rax
0x18007be4a  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007be51  mov     [rbp+4Fh+var_98], rax
0x18007be55  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007be5c  jmp     loc_18007BC20
0x18007be61  mov     rcx, [rbp+4Fh+var_68]
0x18007be65  lea     r8, [rbp+4Fh+var_A0]
0x18007be69  mov     [rbp+4Fh+var_A0], r15
0x18007be6d  lea     rdx, IID_ICaGfxSourceProgressive
0x18007be74  mov     rax, [rcx]
0x18007be77  mov     rax, [rax]
0x18007be7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007be7f  mov     ebx, eax
0x18007be81  test    eax, eax
0x18007be83  jns     loc_18007BF0B
0x18007be89  mov     eax, cs:dword_1801B76C8
0x18007be8f  cmp     eax, 2
0x18007be92  jbe     loc_18007BFA2
0x18007be98  lea     rax, aFailedToQueryI_2; "Failed to query ICaGfxSourceProgressive"
0x18007be9f  mov     dword ptr [rbp+4Fh+arg_0], 860h
0x18007bea6  mov     [rbp+4Fh+var_88], rax
0x18007beaa  lea     rdx, word_18019D5B2
0x18007beb1  lea     rax, aGetinputshader; "GetInputShaderResourceViewDX11"
0x18007beb8  mov     [rbp+4Fh+arg_18], ebx
0x18007bebb  mov     [rbp+4Fh+var_90], rax
0x18007bebf  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007bec6  mov     [rbp+4Fh+var_98], rax
0x18007beca  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007bed1  mov     [rbp+4Fh+var_80], rax
0x18007bed5  lea     rax, [rbp+4Fh+var_88]
0x18007bed9  mov     [rsp+0F0h+var_A8], rax
0x18007bede  lea     rax, [rbp+4Fh+var_90]
0x18007bee2  mov     [rsp+0F0h+var_B0], rax
0x18007bee7  lea     rax, [rbp+4Fh+arg_0]
0x18007beeb  mov     [rsp+0F0h+var_B8], rax
0x18007bef0  lea     rax, [rbp+4Fh+var_98]
0x18007bef4  mov     [rsp+0F0h+var_C0], rax
0x18007bef9  lea     rax, [rbp+4Fh+arg_18]
0x18007befd  mov     [rsp+0F0h+var_C8], rax
0x18007bf02  lea     rax, [rbp+4Fh+var_80]
0x18007bf06  jmp     loc_18007BF98
0x18007bf0b  mov     rcx, [rbp+4Fh+var_A0]
0x18007bf0f  test    rcx, rcx
0x18007bf12  jnz     loc_18007BFC4
0x18007bf18  mov     eax, cs:dword_1801B76C8
0x18007bf1e  mov     ecx, 80004003h
0x18007bf23  mov     ebx, ecx
0x18007bf25  cmp     eax, 2
0x18007bf28  jbe     short loc_18007BFA2
0x18007bf2a  lea     rax, aSpcagfxprovide; "spCaGfxProvider is NULL"
0x18007bf31  mov     dword ptr [rbp+4Fh+arg_0], 862h
0x18007bf38  lea     rdx, word_18019D606
0x18007bf3f  mov     [rbp+4Fh+var_80], rax
0x18007bf43  lea     rax, aGetinputshader; "GetInputShaderResourceViewDX11"
0x18007bf4a  mov     [rbp+4Fh+var_88], rax
0x18007bf4e  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007bf55  mov     [rbp+4Fh+var_90], rax
0x18007bf59  lea     rax, aErrorCondition; "Error condition failed"
0x18007bf60  mov     [rbp+4Fh+arg_18], ecx
0x18007bf63  mov     [rbp+4Fh+var_98], rax
0x18007bf67  lea     rax, [rbp+4Fh+var_80]
0x18007bf6b  mov     [rsp+0F0h+var_A8], rax
0x18007bf70  lea     rax, [rbp+4Fh+var_88]
0x18007bf74  mov     [rsp+0F0h+var_B0], rax
0x18007bf79  lea     rax, [rbp+4Fh+arg_0]
0x18007bf7d  mov     [rsp+0F0h+var_B8], rax
0x18007bf82  lea     rax, [rbp+4Fh+var_90]
0x18007bf86  mov     [rsp+0F0h+var_C0], rax
0x18007bf8b  lea     rax, [rbp+4Fh+arg_18]
0x18007bf8f  mov     [rsp+0F0h+var_C8], rax
0x18007bf94  lea     rax, [rbp+4Fh+var_98]
0x18007bf98  mov     [rsp+0F0h+var_D0], rax
0x18007bf9d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18007bfa2  mov     rcx, [rbp+4Fh+var_A0]
0x18007bfa6  test    rcx, rcx
0x18007bfa9  jz      loc_18007C1F4
0x18007bfaf  mov     [rbp+4Fh+var_A0], r15
0x18007bfb3  mov     rax, [rcx]
0x18007bfb6  mov     rax, [rax+10h]
0x18007bfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bfbf  jmp     loc_18007C1F4
0x18007bfc4  mov     rax, [rcx]
0x18007bfc7  lea     rdx, [rbp+4Fh+SRWLock]
0x18007bfcb  mov     rax, [rax+38h]
0x18007bfcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bfd4  mov     ebx, eax
0x18007bfd6  test    eax, eax
0x18007bfd8  jns     short loc_18007C023
0x18007bfda  mov     eax, cs:dword_1801B76C8
0x18007bfe0  cmp     eax, 2
0x18007bfe3  jbe     short loc_18007BFA2
0x18007bfe5  lea     rax, aFailedToObtain; "Failed to obtain device context lock"
0x18007bfec  mov     dword ptr [rbp+4Fh+arg_0], 865h
0x18007bff3  mov     [rbp+4Fh+var_80], rax
0x18007bff7  lea     rdx, word_18019D50A
0x18007bffe  lea     rax, aGetinputshader; "GetInputShaderResourceViewDX11"
0x18007c005  mov     [rbp+4Fh+arg_18], ebx
0x18007c008  mov     [rbp+4Fh+var_88], rax
0x18007c00c  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007c013  mov     [rbp+4Fh+var_90], rax
0x18007c017  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007c01e  jmp     loc_18007BF63
0x18007c023  mov     rcx, [rbp+4Fh+SRWLock]; SRWLock
0x18007c027  test    rcx, rcx
0x18007c02a  jnz     short loc_18007C05C
  ... truncated ...
```
