# HevcCompressor::GetInputDXTextureFromGfxProvider(RdpSurface *,ID3D11Texture2D * *)

- ea: `0x18008e730`
- end: `0x18008ecce`
- name: `?GetInputDXTextureFromGfxProvider@HevcCompressor@@IEAAJPEAVRdpSurface@@PEAPEAUID3D11Texture2D@@@Z`
- size: `1438`
- prototype: `__int64 __fastcall(HevcCompressor *__hidden this, struct RdpSurface *, struct ID3D11Texture2D **)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18008f5d0`
- `0x18008f990`

## callees

- `0x1800015f0`
- `0x180033da0`
- `0x180059838`
- `0x18008e730`
- `0x18014d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18008e891`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18008e891`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008ec38`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008ec38`
- `RDPSERVERBASE!?GetGraphicsSourceContext@RdpSurface@@QEAAJPEAPEAUIRdpGFXSourceUpdateContext@@@Z` at `0x18008e774`
- `RDPSERVERBASE!?GetGraphicsSourceContext@RdpSurface@@QEAAJPEAPEAUIRdpGFXSourceUpdateContext@@@Z` at `0x18008e774`

## string_xrefs

- `0x18008e7a6`: `Failed to get update context`
- `0x18008e8bd`: `spGfxSrcUpdateContext is NULL`
- `0x18008e7e8`: `onecoreuap\termsrv\rdp\win\codecs\hevccodec\hevccompressor.cpp`
- `0x18008e8e8`: `onecoreuap\termsrv\rdp\win\codecs\hevccodec\hevccompressor.cpp`
- `0x18008e9a0`: `onecoreuap\termsrv\rdp\win\codecs\hevccodec\hevccompressor.cpp`
- `0x18008ea4a`: `onecoreuap\termsrv\rdp\win\codecs\hevccodec\hevccompressor.cpp`
- `0x18008eb02`: `onecoreuap\termsrv\rdp\win\codecs\hevccodec\hevccompressor.cpp`
- `0x18008ebac`: `onecoreuap\termsrv\rdp\win\codecs\hevccodec\hevccompressor.cpp`

## pseudocode

```c
__int64 __fastcall HevcCompressor::GetInputDXTextureFromGfxProvider(
        HevcCompressor *this,
        struct RdpSurface *a2,
        struct ID3D11Texture2D **a3)
{
  int GraphicsSourceContext; // eax
  int v6; // r8d
  int v7; // r9d
  int v8; // ebx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  struct ID3D11Texture2D *v15; // rcx
  unsigned int ActivityIdPrefix; // eax
  __int64 v17; // rcx
  struct ID3D11Texture2D *v18; // rcx
  struct IRdpGFXSourceUpdateContext *v19; // rcx
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v22; // [rsp+54h] [rbp-ACh] BYREF
  const char *v23; // [rsp+58h] [rbp-A8h] BYREF
  const char *v24; // [rsp+60h] [rbp-A0h] BYREF
  const char *v25; // [rsp+68h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-90h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h] BYREF
  struct ID3D11Texture2D *v28; // [rsp+88h] [rbp-78h] BYREF
  struct IRdpGFXSourceUpdateContext *v29; // [rsp+90h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-60h] BYREF
  __int16 *v31; // [rsp+B0h] [rbp-50h]
  int v32; // [rsp+B8h] [rbp-48h]
  int v33; // [rsp+BCh] [rbp-44h]
  const char *v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  int *v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  const char *v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+E8h] [rbp-18h]
  const char **v40; // [rsp+F0h] [rbp-10h]
  __int64 v41; // [rsp+F8h] [rbp-8h]
  const char *v42; // [rsp+100h] [rbp+0h]
  __int64 v43; // [rsp+108h] [rbp+8h]
  const char *v44; // [rsp+110h] [rbp+10h]
  __int64 v45; // [rsp+118h] [rbp+18h]

  v29 = 0;
  v28 = 0;
  v27 = 0;
  GraphicsSourceContext = RdpSurface::GetGraphicsSourceContext(a2, &v29);
  v8 = GraphicsSourceContext;
  if ( GraphicsSourceContext >= 0 )
  {
    if ( v29 )
    {
      v8 = (**(__int64 (__fastcall ***)(struct IRdpGFXSourceUpdateContext *, GUID *, __int64 *))v29)(
             v29,
             &IID_IRdpGfxSrcDxTextureProvider,
             &v27);
      if ( v8 >= 0 )
      {
        if ( v27 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct ID3D11Texture2D **))(*(_QWORD *)v27 + 24LL))(
                 v27,
                 *((unsigned int *)a2 + 156),
                 &v28);
          if ( v8 >= 0 )
          {
            v15 = v28;
            if ( v28 )
            {
              *a3 = v28;
              ((void (__fastcall *)(struct ID3D11Texture2D *))v15->lpVtbl->AddRef)(v15);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  65,
                  WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids,
                  ActivityIdPrefix);
              }
            }
            else
            {
              v8 = -2147467261;
              if ( (unsigned int)dword_1801B76C8 > 2 )
              {
                v22 = 1801;
                *(_QWORD *)&EventDescriptor.Id = "spD3DTexture2D is NULL";
                v21 = -2147467261;
                v25 = "GetInputDXTextureFromGfxProvider";
                v24 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevccompressor.cpp";
                v23 = "Error condition failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  0,
                  (unsigned int)&dword_1801A1964,
                  v13,
                  v14,
                  (__int64)&v23,
                  (__int64)&v21,
                  (__int64)&v24,
                  (__int64)&v22,
                  (__int64)&v25,
                  (__int64)&EventDescriptor);
              }
            }
          }
          else if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            v22 = 1799;
            *(_QWORD *)&EventDescriptor.Id = "Failed to get DX texture";
            v21 = v8;
            v25 = "GetInputDXTextureFromGfxProvider";
            v24 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevccompressor.cpp";
            v23 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v12,
              (unsigned int)&byte_1801A190F,
              v13,
              v14,
              (__int64)&v23,
              (__int64)&v21,
              (__int64)&v24,
              (__int64)&v22,
              (__int64)&v25,
              (__int64)&EventDescriptor);
          }
        }
        else
        {
          v8 = -2147467261;
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            v22 = 1796;
            *(_QWORD *)&EventDescriptor.Id = "spGfxSrcDxTextureProvider is NULL";
            v21 = -2147467261;
            v25 = "GetInputDXTextureFromGfxProvider";
            v24 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevccompressor.cpp";
            v23 = "Error condition failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              0,
              (unsigned int)&word_1801A1A0E,
              v10,
              v11,
              (__int64)&v23,
              (__int64)&v21,
              (__int64)&v24,
              (__int64)&v22,
              (__int64)&v25,
              (__int64)&EventDescriptor);
          }
        }
      }
      else if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v22 = 1794;
        *(_QWORD *)&EventDescriptor.Id = "Failed to QI IRdpGfxSrcDxTextureProvider";
        v21 = v8;
        v25 = "GetInputDXTextureFromGfxProvider";
        v24 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevccompressor.cpp";
        v23 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v9,
          (unsigned int)byte_1801A19B9,
          v10,
          v11,
          (__int64)&v23,
          (__int64)&v21,
          (__int64)&v24,
          (__int64)&v22,
          (__int64)&v25,
          (__int64)&EventDescriptor);
      }
    }
    else
    {
      v8 = -2147467261;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v22 = 1791;
        v23 = "spGfxSrcUpdateContext is NULL";
        v21 = -2147467261;
        v24 = "GetInputDXTextureFromGfxProvider";
        v25 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevccompressor.cpp";
        *(_QWORD *)&EventDescriptor.Id = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          0,
          (unsigned int)&unk_1801A1AB8,
          v6,
          v7,
          (__int64)&EventDescriptor,
          (__int64)&v21,
          (__int64)&v25,
          (__int64)&v22,
          (__int64)&v24,
          (__int64)&v23);
      }
    }
  }
  else if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v21 = GraphicsSourceContext;
    LODWORD(v23) = 1789;
    v44 = "Failed to get update context";
    v45 = 29;
    v42 = "GetInputDXTextureFromGfxProvider";
    v43 = 33;
    v40 = &v23;
    v41 = 4;
    v38 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevccompressor.cpp";
    v36 = &v21;
    v34 = "Error HResult failed";
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_1801B76D0;
    v39 = 63;
    v37 = 4;
    v35 = 21;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_1801B76D0;
    v31 = &word_1801A1A6E;
    UserData.Reserved = 2;
    v32 = 73;
    v33 = 1;
    v22 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(qword_1801B76E8, &EventDescriptor, 0, 0, 8u, &UserData);
  }
  v17 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v28;
  if ( v28 )
  {
    v28 = 0;
    ((void (__fastcall *)(struct ID3D11Texture2D *))v18->lpVtbl->Release)(v18);
  }
  v19 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(struct IRdpGFXSourceUpdateContext *))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008e730  mov     [rsp-8+arg_0], rbx
0x18008e735  mov     [rsp-8+arg_18], rsi
0x18008e73a  push    rbp
0x18008e73b  push    rdi
0x18008e73c  push    r14
0x18008e73e  lea     rbp, [rsp-30h]
0x18008e743  sub     rsp, 130h
0x18008e74a  mov     rax, cs:__security_cookie
0x18008e751  xor     rax, rsp
0x18008e754  mov     [rbp+40h+var_20], rax
0x18008e758  mov     rdi, rdx
0x18008e75b  xor     r14d, r14d
0x18008e75e  mov     rcx, rdi
0x18008e761  mov     [rbp+40h+var_B0], r14
0x18008e765  lea     rdx, [rbp+40h+var_B0]
0x18008e769  mov     [rbp+40h+var_B8], r14
0x18008e76d  mov     rsi, r8
0x18008e770  mov     [rbp+40h+var_C0], r14
0x18008e774  call    cs:__imp_?GetGraphicsSourceContext@RdpSurface@@QEAAJPEAPEAUIRdpGFXSourceUpdateContext@@@Z; RdpSurface::GetGraphicsSourceContext(IRdpGFXSourceUpdateContext * *)
0x18008e77a  mov     ebx, eax
0x18008e77c  test    eax, eax
0x18008e77e  jns     loc_18008E89C
0x18008e784  mov     ecx, cs:dword_1801B76C8
0x18008e78a  cmp     ecx, 2
0x18008e78d  jbe     loc_18008EC5D
0x18008e793  mov     [rsp+140h+var_F0], eax
0x18008e797  lea     rcx, _TraceLoggingMetadata
0x18008e79e  mov     dword ptr [rsp+140h+var_E8], 6FDh
0x18008e7a6  lea     rax, aFailedToGetUpd; "Failed to get update context"
0x18008e7ad  mov     [rbp+40h+var_30], rax
0x18008e7b1  lea     rdx, [rsp+140h+EventDescriptor]; EventDescriptor
0x18008e7b6  mov     [rbp+40h+var_28], 1Dh
0x18008e7be  lea     rax, aGetinputdxtext; "GetInputDXTextureFromGfxProvider"
0x18008e7c5  mov     [rbp+40h+var_40], rax
0x18008e7c9  xor     r9d, r9d; RelatedActivityId
0x18008e7cc  mov     [rbp+40h+var_38], 21h ; '!'
0x18008e7d4  lea     rax, [rsp+140h+var_E8]
0x18008e7d9  mov     [rbp+40h+var_50], rax
0x18008e7dd  xor     r8d, r8d; ActivityId
0x18008e7e0  mov     [rbp+40h+var_48], 4
0x18008e7e8  lea     rax, aOnecoreuapTerm_4; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18008e7ef  mov     [rbp+40h+var_60], rax
0x18008e7f3  lea     rax, [rsp+140h+var_F0]
0x18008e7f8  mov     [rbp+40h+var_70], rax
0x18008e7fc  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008e803  mov     [rbp+40h+var_80], rax
0x18008e807  movzx   eax, cs:word_1801A1A64
0x18008e80e  mov     dword ptr [rsp+140h+EventDescriptor.Level], eax
0x18008e812  mov     rax, cs:off_1801B76D0
0x18008e819  mov     [rbp+40h+var_A0.Ptr], rax
0x18008e81d  mov     [rbp+40h+var_58], 3Fh ; '?'
0x18008e825  mov     [rbp+40h+var_68], 4
0x18008e82d  mov     [rbp+40h+var_78], 15h
0x18008e835  mov     dword ptr [rsp+140h+EventDescriptor.Id], 0B000000h
0x18008e83d  mov     [rsp+140h+EventDescriptor.Keyword], r14
0x18008e842  movzx   eax, word ptr [rax]
0x18008e845  mov     [rbp+40h+var_A0.Size], eax
0x18008e848  lea     rax, word_1801A1A6E
0x18008e84f  mov     [rbp+40h+var_90], rax
0x18008e853  lea     rax, _TraceLoggingMetadataEnd
0x18008e85a  sub     eax, ecx
0x18008e85c  mov     dword ptr [rbp+40h+var_A0.0Ch], 2
0x18008e863  mov     [rbp+40h+var_88], 49h ; 'I'
0x18008e86a  mov     [rbp+40h+var_84], 1
0x18008e871  mov     [rsp+140h+var_EC], eax
0x18008e875  mov     eax, [rsp+140h+var_EC]
0x18008e879  mov     rcx, cs:qword_1801B76E8; RegHandle
0x18008e880  lea     rax, [rbp+40h+var_A0]
0x18008e884  mov     [rsp+140h+UserData], rax; UserData
0x18008e889  mov     [rsp+140h+UserDataCount], 8; UserDataCount
0x18008e891  call    cs:__imp_EventWriteTransfer
0x18008e897  jmp     loc_18008EC5D
0x18008e89c  mov     rcx, [rbp+40h+var_B0]
0x18008e8a0  test    rcx, rcx
0x18008e8a3  jnz     loc_18008E946
0x18008e8a9  mov     eax, cs:dword_1801B76C8
0x18008e8af  mov     ebx, 80004003h
0x18008e8b4  cmp     eax, 2
0x18008e8b7  jbe     loc_18008EC5D
0x18008e8bd  lea     rax, aSpgfxsrcupdate; "spGfxSrcUpdateContext is NULL"
0x18008e8c4  mov     [rsp+140h+var_EC], 6FFh
0x18008e8cc  mov     [rsp+140h+var_E8], rax
0x18008e8d1  lea     rdx, unk_1801A1AB8
0x18008e8d8  lea     rax, aGetinputdxtext; "GetInputDXTextureFromGfxProvider"
0x18008e8df  mov     [rsp+140h+var_F0], ebx
0x18008e8e3  mov     [rsp+140h+var_E0], rax
0x18008e8e8  lea     rax, aOnecoreuapTerm_4; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18008e8ef  mov     [rsp+140h+var_D8], rax
0x18008e8f4  lea     rax, aErrorCondition; "Error condition failed"
0x18008e8fb  mov     qword ptr [rsp+140h+EventDescriptor.Id], rax
0x18008e900  lea     rax, [rsp+140h+var_E8]
0x18008e905  mov     [rsp+140h+var_F8], rax
0x18008e90a  lea     rax, [rsp+140h+var_E0]
0x18008e90f  mov     [rsp+140h+var_100], rax
0x18008e914  lea     rax, [rsp+140h+var_EC]
0x18008e919  mov     [rsp+140h+var_108], rax
0x18008e91e  lea     rax, [rsp+140h+var_D8]
0x18008e923  mov     [rsp+140h+var_110], rax
0x18008e928  lea     rax, [rsp+140h+var_F0]
0x18008e92d  mov     [rsp+140h+UserData], rax
0x18008e932  lea     rax, [rsp+140h+EventDescriptor]
0x18008e937  mov     qword ptr [rsp+140h+UserDataCount], rax
0x18008e93c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008e941  jmp     loc_18008EC5D
0x18008e946  mov     rax, [rcx]
0x18008e949  lea     r8, [rbp+40h+var_C0]
0x18008e94d  lea     rdx, IID_IRdpGfxSrcDxTextureProvider
0x18008e954  mov     rax, [rax]
0x18008e957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e95c  mov     ebx, eax
0x18008e95e  test    eax, eax
0x18008e960  jns     loc_18008E9FE
0x18008e966  mov     eax, cs:dword_1801B76C8
0x18008e96c  cmp     eax, 2
0x18008e96f  jbe     loc_18008EC5D
0x18008e975  lea     rax, aFailedToQiIrdp; "Failed to QI IRdpGfxSrcDxTextureProvide"...
0x18008e97c  mov     [rsp+140h+var_EC], 702h
0x18008e984  mov     qword ptr [rsp+140h+EventDescriptor.Id], rax
0x18008e989  lea     rdx, byte_1801A19B9
0x18008e990  lea     rax, aGetinputdxtext; "GetInputDXTextureFromGfxProvider"
0x18008e997  mov     [rsp+140h+var_F0], ebx
0x18008e99b  mov     [rsp+140h+var_D8], rax
0x18008e9a0  lea     rax, aOnecoreuapTerm_4; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18008e9a7  mov     [rsp+140h+var_E0], rax
0x18008e9ac  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008e9b3  mov     [rsp+140h+var_E8], rax
0x18008e9b8  lea     rax, [rsp+140h+EventDescriptor]
0x18008e9bd  mov     [rsp+140h+var_F8], rax
0x18008e9c2  lea     rax, [rsp+140h+var_D8]
0x18008e9c7  mov     [rsp+140h+var_100], rax
0x18008e9cc  lea     rax, [rsp+140h+var_EC]
0x18008e9d1  mov     [rsp+140h+var_108], rax
0x18008e9d6  lea     rax, [rsp+140h+var_E0]
0x18008e9db  mov     [rsp+140h+var_110], rax
0x18008e9e0  lea     rax, [rsp+140h+var_F0]
0x18008e9e5  mov     [rsp+140h+UserData], rax
0x18008e9ea  lea     rax, [rsp+140h+var_E8]
0x18008e9ef  mov     qword ptr [rsp+140h+UserDataCount], rax
0x18008e9f4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008e9f9  jmp     loc_18008EC5D
0x18008e9fe  mov     rcx, [rbp+40h+var_C0]
0x18008ea02  test    rcx, rcx
0x18008ea05  jnz     loc_18008EAA8
0x18008ea0b  mov     eax, cs:dword_1801B76C8
0x18008ea11  mov     ebx, 80004003h
0x18008ea16  cmp     eax, 2
0x18008ea19  jbe     loc_18008EC5D
0x18008ea1f  lea     rax, aSpgfxsrcdxtext; "spGfxSrcDxTextureProvider is NULL"
0x18008ea26  mov     [rsp+140h+var_EC], 704h
0x18008ea2e  mov     qword ptr [rsp+140h+EventDescriptor.Id], rax
0x18008ea33  lea     rdx, word_1801A1A0E
0x18008ea3a  lea     rax, aGetinputdxtext; "GetInputDXTextureFromGfxProvider"
0x18008ea41  mov     [rsp+140h+var_F0], ebx
0x18008ea45  mov     [rsp+140h+var_D8], rax
0x18008ea4a  lea     rax, aOnecoreuapTerm_4; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18008ea51  mov     [rsp+140h+var_E0], rax
0x18008ea56  lea     rax, aErrorCondition; "Error condition failed"
0x18008ea5d  mov     [rsp+140h+var_E8], rax
0x18008ea62  lea     rax, [rsp+140h+EventDescriptor]
0x18008ea67  mov     [rsp+140h+var_F8], rax
0x18008ea6c  lea     rax, [rsp+140h+var_D8]
0x18008ea71  mov     [rsp+140h+var_100], rax
0x18008ea76  lea     rax, [rsp+140h+var_EC]
0x18008ea7b  mov     [rsp+140h+var_108], rax
0x18008ea80  lea     rax, [rsp+140h+var_E0]
0x18008ea85  mov     [rsp+140h+var_110], rax
0x18008ea8a  lea     rax, [rsp+140h+var_F0]
0x18008ea8f  mov     [rsp+140h+UserData], rax
0x18008ea94  lea     rax, [rsp+140h+var_E8]
0x18008ea99  mov     qword ptr [rsp+140h+UserDataCount], rax
0x18008ea9e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008eaa3  jmp     loc_18008EC5D
0x18008eaa8  mov     rax, [rcx]
0x18008eaab  lea     r8, [rbp+40h+var_B8]
0x18008eaaf  mov     edx, [rdi+270h]
0x18008eab5  mov     rax, [rax+18h]
0x18008eab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eabe  mov     ebx, eax
0x18008eac0  test    eax, eax
0x18008eac2  jns     loc_18008EB60
0x18008eac8  mov     eax, cs:dword_1801B76C8
0x18008eace  cmp     eax, 2
0x18008ead1  jbe     loc_18008EC5D
0x18008ead7  lea     rax, aFailedToGetDxT; "Failed to get DX texture"
0x18008eade  mov     [rsp+140h+var_EC], 707h
0x18008eae6  mov     qword ptr [rsp+140h+EventDescriptor.Id], rax
0x18008eaeb  lea     rdx, byte_1801A190F
0x18008eaf2  lea     rax, aGetinputdxtext; "GetInputDXTextureFromGfxProvider"
0x18008eaf9  mov     [rsp+140h+var_F0], ebx
0x18008eafd  mov     [rsp+140h+var_D8], rax
0x18008eb02  lea     rax, aOnecoreuapTerm_4; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18008eb09  mov     [rsp+140h+var_E0], rax
0x18008eb0e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008eb15  mov     [rsp+140h+var_E8], rax
0x18008eb1a  lea     rax, [rsp+140h+EventDescriptor]
0x18008eb1f  mov     [rsp+140h+var_F8], rax
0x18008eb24  lea     rax, [rsp+140h+var_D8]
0x18008eb29  mov     [rsp+140h+var_100], rax
0x18008eb2e  lea     rax, [rsp+140h+var_EC]
0x18008eb33  mov     [rsp+140h+var_108], rax
0x18008eb38  lea     rax, [rsp+140h+var_E0]
0x18008eb3d  mov     [rsp+140h+var_110], rax
0x18008eb42  lea     rax, [rsp+140h+var_F0]
0x18008eb47  mov     [rsp+140h+UserData], rax
0x18008eb4c  lea     rax, [rsp+140h+var_E8]
0x18008eb51  mov     qword ptr [rsp+140h+UserDataCount], rax
0x18008eb56  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008eb5b  jmp     loc_18008EC5D
0x18008eb60  mov     rcx, [rbp+40h+var_B8]
0x18008eb64  test    rcx, rcx
0x18008eb67  jnz     loc_18008EC07
0x18008eb6d  mov     eax, cs:dword_1801B76C8
0x18008eb73  mov     ebx, 80004003h
0x18008eb78  cmp     eax, 2
0x18008eb7b  jbe     loc_18008EC5D
0x18008eb81  lea     rax, aSpd3dtexture2d; "spD3DTexture2D is NULL"
0x18008eb88  mov     [rsp+140h+var_EC], 709h
0x18008eb90  mov     qword ptr [rsp+140h+EventDescriptor.Id], rax
0x18008eb95  lea     rdx, dword_1801A1964
0x18008eb9c  lea     rax, aGetinputdxtext; "GetInputDXTextureFromGfxProvider"
0x18008eba3  mov     [rsp+140h+var_F0], ebx
0x18008eba7  mov     [rsp+140h+var_D8], rax
0x18008ebac  lea     rax, aOnecoreuapTerm_4; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18008ebb3  mov     [rsp+140h+var_E0], rax
0x18008ebb8  lea     rax, aErrorCondition; "Error condition failed"
0x18008ebbf  mov     [rsp+140h+var_E8], rax
0x18008ebc4  lea     rax, [rsp+140h+EventDescriptor]
0x18008ebc9  mov     [rsp+140h+var_F8], rax
0x18008ebce  lea     rax, [rsp+140h+var_D8]
0x18008ebd3  mov     [rsp+140h+var_100], rax
0x18008ebd8  lea     rax, [rsp+140h+var_EC]
0x18008ebdd  mov     [rsp+140h+var_108], rax
0x18008ebe2  lea     rax, [rsp+140h+var_E0]
0x18008ebe7  mov     [rsp+140h+var_110], rax
0x18008ebec  lea     rax, [rsp+140h+var_F0]
0x18008ebf1  mov     [rsp+140h+UserData], rax
0x18008ebf6  lea     rax, [rsp+140h+var_E8]
0x18008ebfb  mov     qword ptr [rsp+140h+UserDataCount], rax
0x18008ec00  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008ec05  jmp     short loc_18008EC5D
0x18008ec07  mov     [rsi], rcx
0x18008ec0a  mov     rax, [rcx]
0x18008ec0d  mov     rax, [rax+8]
0x18008ec11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ec16  mov     rax, cs:WPP_GLOBAL_Control
0x18008ec1d  lea     rcx, WPP_GLOBAL_Control
0x18008ec24  cmp     rax, rcx
0x18008ec27  jz      short loc_18008EC5D
0x18008ec29  test    dword ptr [rax+1Ch], 100h
0x18008ec30  jz      short loc_18008EC5D
0x18008ec32  cmp     byte ptr [rax+19h], 5
0x18008ec36  jb      short loc_18008EC5D
0x18008ec38  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18008ec3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ec45  lea     r8, WPP_1a126f0ff7fe37fe5ce8ad6c599778bf_Traceguids
0x18008ec4c  mov     edx, 41h ; 'A'
0x18008ec51  mov     r9d, eax
0x18008ec54  mov     rcx, [rcx+10h]
0x18008ec58  call    WPP_SF_d
0x18008ec5d  mov     rcx, [rbp+40h+var_C0]
0x18008ec61  test    rcx, rcx
0x18008ec64  jz      short loc_18008EC76
0x18008ec66  mov     [rbp+40h+var_C0], r14
0x18008ec6a  mov     rax, [rcx]
0x18008ec6d  mov     rax, [rax+10h]
0x18008ec71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ec76  mov     rcx, [rbp+40h+var_B8]
0x18008ec7a  test    rcx, rcx
0x18008ec7d  jz      short loc_18008EC8F
0x18008ec7f  mov     [rbp+40h+var_B8], r14
0x18008ec83  mov     rax, [rcx]
0x18008ec86  mov     rax, [rax+10h]
0x18008ec8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ec8f  mov     rcx, [rbp+40h+var_B0]
0x18008ec93  test    rcx, rcx
0x18008ec96  jz      short loc_18008ECA8
0x18008ec98  mov     [rbp+40h+var_B0], r14
0x18008ec9c  mov     rax, [rcx]
0x18008ec9f  mov     rax, [rax+10h]
0x18008eca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eca8  mov     eax, ebx
0x18008ecaa  mov     rcx, [rbp+40h+var_20]
0x18008ecae  xor     rcx, rsp; StackCookie
0x18008ecb1  call    __security_check_cookie
0x18008ecb6  lea     r11, [rsp+140h+var_10]
0x18008ecbe  mov     rbx, [r11+20h]
0x18008ecc2  mov     rsi, [r11+38h]
0x18008ecc6  mov     rsp, r11
0x18008ecc9  pop     r14
0x18008eccb  pop     rdi
0x18008eccc  pop     rbp
0x18008eccd  retn
```
