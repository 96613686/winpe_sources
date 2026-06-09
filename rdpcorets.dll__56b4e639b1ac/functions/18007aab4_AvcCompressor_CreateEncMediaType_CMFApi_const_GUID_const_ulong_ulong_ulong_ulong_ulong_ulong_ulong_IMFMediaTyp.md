# AvcCompressor::CreateEncMediaType(CMFApi const *,_GUID const &,ulong,ulong,ulong,ulong,ulong,ulong,ulong,IMFMediaType * *)

- ea: `0x18007aab4`
- end: `0x18007b254`
- name: `?CreateEncMediaType@AvcCompressor@@SAJPEBVCMFApi@@AEBU_GUID@@KKKKKKKPEAPEAUIMFMediaType@@@Z`
- size: `1952`
- prototype: `__int64 __fastcall(const struct CMFApi *, const struct _GUID *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007d5a0`

## callees

- `0x1800015f0`
- `0x1800071c0`
- `0x180059838`
- `0x18007aab4`
- `0x18014d010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18007b20a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18007b20a`

## string_xrefs

- `0x18007ab27`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007abc4`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007ac6a`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007ad1d`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007adcc`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007ae86`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007af3c`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007afee`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007b0a0`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007b171`: `onecoreuap\termsrv\rdp\win\codecs\h264codec\avccompressor.cpp`
- `0x18007ac40`: `MFCreateMediaType failed`
- `0x18007ab1c`: `CreateEncMediaType`
- `0x18007abb9`: `CreateEncMediaType`
- `0x18007ac5c`: `CreateEncMediaType`
- `0x18007ad0f`: `CreateEncMediaType`
- `0x18007adbe`: `CreateEncMediaType`
- `0x18007ae78`: `CreateEncMediaType`
- `0x18007af2e`: `CreateEncMediaType`
- `0x18007afe0`: `CreateEncMediaType`
- `0x18007b092`: `CreateEncMediaType`
- `0x18007b163`: `CreateEncMediaType`

## pseudocode

```c
__int64 __fastcall AvcCompressor::CreateEncMediaType(
        __int64 (__fastcall **a1)(struct IMFMediaType **),
        const struct _GUID *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        struct IMFMediaType **a10)
{
  struct IMFMediaType **v10; // rsi
  __int64 v12; // r14
  __int64 v13; // r15
  int v14; // ebx
  char *v15; // rdx
  const char **v16; // rax
  int v17; // r9d
  int v18; // ecx
  int v19; // r9d
  int v20; // ecx
  int v21; // r9d
  int v22; // ecx
  int v23; // r9d
  int v24; // ecx
  int v25; // r9d
  int v26; // ecx
  int v27; // r9d
  int v28; // ecx
  int v29; // r9d
  int v30; // ecx
  int v31; // r9d
  unsigned int ActivityIdPrefix; // eax
  const char **v34; // [rsp+40h] [rbp-38h]
  struct IMFMediaType *v35; // [rsp+50h] [rbp-28h] BYREF
  const char *v36; // [rsp+58h] [rbp-20h] BYREF
  const char *v37; // [rsp+60h] [rbp-18h] BYREF
  _QWORD v38[2]; // [rsp+68h] [rbp-10h] BYREF

  v10 = a10;
  v12 = a4;
  v13 = (unsigned int)a3;
  v35 = 0;
  if ( a10 )
  {
    if ( a1 )
    {
      *a10 = 0;
      v14 = a1[11](&v35);
      if ( v14 >= 0 )
      {
        v14 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, const GUID *))v35->lpVtbl->SetGUID)(
                v35,
                &MF_MT_MAJOR_TYPE,
                &MFMediaType_Video);
        if ( v14 >= 0 )
        {
          v14 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, const struct _GUID *))v35->lpVtbl->SetGUID)(
                  v35,
                  &MF_MT_SUBTYPE,
                  a2);
          if ( v14 >= 0 )
          {
            v14 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned __int64))v35->lpVtbl->SetUINT64)(
                    v35,
                    &MF_MT_FRAME_RATE,
                    a7 | ((unsigned __int64)a6 << 32));
            if ( v14 >= 0 )
            {
              v14 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int64))v35->lpVtbl->SetUINT64)(
                      v35,
                      &MF_MT_FRAME_SIZE,
                      v12 | (v13 << 32));
              if ( v14 >= 0 )
              {
                v14 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int64))v35->lpVtbl->SetUINT32)(
                        v35,
                        &MF_MT_MPEG2_PROFILE,
                        77);
                if ( v14 >= 0 )
                {
                  v14 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int64))v35->lpVtbl->SetUINT32)(
                          v35,
                          &MF_MT_INTERLACE_MODE,
                          2);
                  if ( v14 >= 0 )
                  {
                    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&MFVideoFormat_H264.Data1
                      && *(_QWORD *)a2->Data4 == *(_QWORD *)MFVideoFormat_H264.Data4
                      && (v14 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, _QWORD))v35->lpVtbl->SetUINT32)(
                                  v35,
                                  &MF_MT_AVG_BITRATE,
                                  a9),
                          v14 < 0) )
                    {
                      if ( (unsigned int)dword_1801B76C8 > 2 )
                      {
                        a5 = 587;
                        a10 = (struct IMFMediaType **)"MF_MT_AVG_BITRATE failed";
                        a8 = v14;
                        v38[0] = "CreateEncMediaType";
                        v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
                        v36 = "Error HResult failed";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                          v30,
                          (unsigned int)byte_18019E583,
                          a3,
                          v31,
                          (__int64)&v36,
                          (__int64)&a8,
                          (__int64)&v37,
                          (__int64)&a5,
                          (__int64)v38,
                          (__int64)&a10);
                      }
                    }
                    else
                    {
                      v14 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int64))v35->lpVtbl->SetUINT32)(
                              v35,
                              &MF_MT_VIDEO_NOMINAL_RANGE,
                              1);
                      if ( v14 < 0 )
                      {
                        v14 = 0;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                        {
                          ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            10,
                            &WPP_1c5fb9514b053585536f3862527bab66_Traceguids,
                            ActivityIdPrefix);
                        }
                      }
                      *v10 = v35;
                      v35 = 0;
                    }
                  }
                  else if ( (unsigned int)dword_1801B76C8 > 2 )
                  {
                    a5 = 582;
                    a10 = (struct IMFMediaType **)"MF_MT_INTERLACE_MODE failed";
                    a8 = v14;
                    v38[0] = "CreateEncMediaType";
                    v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
                    v36 = "Error HResult failed";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                      v28,
                      (unsigned int)&byte_18019E5D7,
                      a3,
                      v29,
                      (__int64)&v36,
                      (__int64)&a8,
                      (__int64)&v37,
                      (__int64)&a5,
                      (__int64)v38,
                      (__int64)&a10);
                  }
                }
                else if ( (unsigned int)dword_1801B76C8 > 2 )
                {
                  a5 = 579;
                  a10 = (struct IMFMediaType **)"MF_MT_MPEG2_PROFILE failed";
                  a8 = v14;
                  v38[0] = "CreateEncMediaType";
                  v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
                  v36 = "Error HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v26,
                    (unsigned int)byte_18019E62B,
                    a3,
                    v27,
                    (__int64)&v36,
                    (__int64)&a8,
                    (__int64)&v37,
                    (__int64)&a5,
                    (__int64)v38,
                    (__int64)&a10);
                }
              }
              else if ( (unsigned int)dword_1801B76C8 > 2 )
              {
                a5 = 576;
                a10 = (struct IMFMediaType **)"MF_MT_FRAME_SIZE failed";
                a8 = v14;
                v38[0] = "CreateEncMediaType";
                v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
                v36 = "Error HResult failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  v24,
                  (unsigned int)byte_18019E6D3,
                  a3,
                  v25,
                  (__int64)&v36,
                  (__int64)&a8,
                  (__int64)&v37,
                  (__int64)&a5,
                  (__int64)v38,
                  (__int64)&a10);
              }
            }
            else if ( (unsigned int)dword_1801B76C8 > 2 )
            {
              a5 = 573;
              a10 = (struct IMFMediaType **)"MF_MT_FRAME_RATE failed";
              a8 = v14;
              v38[0] = "CreateEncMediaType";
              v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
              v36 = "Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v22,
                (unsigned int)&byte_18019E67F,
                a3,
                v23,
                (__int64)&v36,
                (__int64)&a8,
                (__int64)&v37,
                (__int64)&a5,
                (__int64)v38,
                (__int64)&a10);
            }
          }
          else if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            a5 = 570;
            a10 = (struct IMFMediaType **)"MF_MT_SUBTYPE failed";
            a8 = v14;
            v38[0] = "CreateEncMediaType";
            v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
            v36 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v20,
              (unsigned int)byte_18019E77B,
              a3,
              v21,
              (__int64)&v36,
              (__int64)&a8,
              (__int64)&v37,
              (__int64)&a5,
              (__int64)v38,
              (__int64)&a10);
          }
        }
        else if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          a5 = 567;
          a10 = (struct IMFMediaType **)"MF_MT_MAJOR_TYPE failed";
          a8 = v14;
          v38[0] = "CreateEncMediaType";
          v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
          v36 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v18,
            (unsigned int)&byte_18019E727,
            a3,
            v19,
            (__int64)&v36,
            (__int64)&a8,
            (__int64)&v37,
            (__int64)&a5,
            (__int64)v38,
            (__int64)&a10);
        }
      }
      else if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        a5 = 564;
        a10 = (struct IMFMediaType **)"MFCreateMediaType failed";
        a8 = v14;
        v38[0] = "CreateEncMediaType";
        v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
        v36 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          dword_1801B76C8,
          (unsigned int)byte_18019E823,
          a3,
          v17,
          (__int64)&v36,
          (__int64)&a8,
          (__int64)&v37,
          (__int64)&a5,
          (__int64)v38,
          (__int64)&a10);
      }
    }
    else
    {
      v14 = -2147467261;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        a5 = 558;
        a10 = (struct IMFMediaType **)"pMFApi is NULL";
        v15 = &byte_18019E7CF;
        v38[0] = "CreateEncMediaType";
        v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
        v36 = "Error condition failed";
        v34 = (const char **)v38;
        v16 = &v36;
        goto LABEL_4;
      }
    }
  }
  else
  {
    v14 = -2147467261;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      a5 = 557;
      a10 = (struct IMFMediaType **)"ppMediaType is NULL";
      v15 = &byte_18019E877;
      v36 = "CreateEncMediaType";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avccompressor.cpp";
      v38[0] = "Error condition failed";
      v34 = &v36;
      v16 = (const char **)v38;
LABEL_4:
      a8 = -2147467261;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147467261,
        (_DWORD)v15,
        a3,
        a4,
        (__int64)v16,
        (__int64)&a8,
        (__int64)&v37,
        (__int64)&a5,
        (__int64)v34,
        (__int64)&a10);
    }
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v35, a2, a3);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18007aab4  mov     r11, rsp
0x18007aab7  push    rbp
0x18007aab8  push    rbx
0x18007aab9  push    rsi
0x18007aaba  push    rdi
0x18007aabb  push    r14
0x18007aabd  push    r15
0x18007aabf  mov     rbp, rsp
0x18007aac2  sub     rsp, 78h
0x18007aac6  mov     rsi, [rbp+arg_48]
0x18007aacd  mov     rdi, rdx
0x18007aad0  mov     r14d, r9d
0x18007aad3  mov     rax, rcx
0x18007aad6  mov     r15d, r8d
0x18007aad9  mov     [rbp+var_28], 0
0x18007aae1  test    rsi, rsi
0x18007aae4  jnz     loc_18007AB7E
0x18007aaea  mov     eax, cs:dword_1801B76C8
0x18007aaf0  mov     ecx, 80004003h
0x18007aaf5  mov     ebx, ecx
0x18007aaf7  cmp     eax, 2
0x18007aafa  jbe     loc_18007B23C
0x18007ab00  lea     rax, aPpmediatypeIsN; "ppMediaType is NULL"
0x18007ab07  mov     [rbp+arg_20], 22Dh
0x18007ab0e  mov     [rbp+arg_48], rax
0x18007ab15  lea     rdx, byte_18019E877
0x18007ab1c  lea     rax, aCreateencmedia; "CreateEncMediaType"
0x18007ab23  mov     [rbp+var_20], rax
0x18007ab27  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007ab2e  mov     [rbp+var_18], rax
0x18007ab32  lea     rax, aErrorCondition; "Error condition failed"
0x18007ab39  mov     [rbp+var_10], rax
0x18007ab3d  lea     rax, [rbp+arg_48]
0x18007ab44  mov     [r11-60h], rax
0x18007ab48  lea     rax, [rbp+var_20]
0x18007ab4c  mov     [r11-68h], rax
0x18007ab50  lea     rax, [rbp+arg_20]
0x18007ab54  mov     [r11-70h], rax
0x18007ab58  lea     rax, [rbp+var_18]
0x18007ab5c  mov     [r11-78h], rax
0x18007ab60  lea     rax, [rbp+arg_38]
0x18007ab64  mov     [r11-80h], rax
0x18007ab68  lea     rax, [rbp+var_10]
0x18007ab6c  mov     [rbp+arg_38], ecx
0x18007ab6f  mov     [rsp+78h+var_58], rax
0x18007ab74  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18007ab79  jmp     loc_18007B23C
0x18007ab7e  test    rax, rax
0x18007ab81  jnz     loc_18007AC13
0x18007ab87  mov     eax, cs:dword_1801B76C8
0x18007ab8d  mov     ecx, 80004003h
0x18007ab92  mov     ebx, ecx
0x18007ab94  cmp     eax, 2
0x18007ab97  jbe     loc_18007B23C
0x18007ab9d  lea     rax, aPmfapiIsNull; "pMFApi is NULL"
0x18007aba4  mov     [rbp+arg_20], 22Eh
0x18007abab  mov     [rbp+arg_48], rax
0x18007abb2  lea     rdx, byte_18019E7CF
0x18007abb9  lea     rax, aCreateencmedia; "CreateEncMediaType"
0x18007abc0  mov     [rbp+var_10], rax
0x18007abc4  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007abcb  mov     [rbp+var_18], rax
0x18007abcf  lea     rax, aErrorCondition; "Error condition failed"
0x18007abd6  mov     [rbp+var_20], rax
0x18007abda  lea     rax, [rbp+arg_48]
0x18007abe1  mov     [rsp+78h+var_30], rax
0x18007abe6  lea     rax, [rbp+var_10]
0x18007abea  mov     [rsp+78h+var_38], rax
0x18007abef  lea     rax, [rbp+arg_20]
0x18007abf3  mov     [rsp+78h+var_40], rax
0x18007abf8  lea     rax, [rbp+var_18]
0x18007abfc  mov     [rsp+78h+var_48], rax
0x18007ac01  lea     rax, [rbp+arg_38]
0x18007ac05  mov     [rsp+78h+var_50], rax
0x18007ac0a  lea     rax, [rbp+var_20]
0x18007ac0e  jmp     loc_18007AB6C
0x18007ac13  mov     qword ptr [rsi], 0
0x18007ac1a  lea     rcx, [rbp+var_28]
0x18007ac1e  mov     rax, [rax+58h]
0x18007ac22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ac27  mov     ebx, eax
0x18007ac29  test    eax, eax
0x18007ac2b  jns     loc_18007ACB9
0x18007ac31  mov     ecx, cs:dword_1801B76C8
0x18007ac37  cmp     ecx, 2
0x18007ac3a  jbe     loc_18007B23C
0x18007ac40  lea     rax, aMfcreatemediat_0; "MFCreateMediaType failed"
0x18007ac47  mov     [rbp+arg_20], 234h
0x18007ac4e  mov     [rbp+arg_48], rax
0x18007ac55  lea     rdx, byte_18019E823
0x18007ac5c  lea     rax, aCreateencmedia; "CreateEncMediaType"
0x18007ac63  mov     [rbp+arg_38], ebx
0x18007ac66  mov     [rbp+var_10], rax
0x18007ac6a  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007ac71  mov     [rbp+var_18], rax
0x18007ac75  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007ac7c  mov     [rbp+var_20], rax
0x18007ac80  lea     rax, [rbp+arg_48]
0x18007ac87  mov     [rsp+78h+var_30], rax
0x18007ac8c  lea     rax, [rbp+var_10]
0x18007ac90  mov     [rsp+78h+var_38], rax
0x18007ac95  lea     rax, [rbp+arg_20]
0x18007ac99  mov     [rsp+78h+var_40], rax
0x18007ac9e  lea     rax, [rbp+var_18]
0x18007aca2  mov     [rsp+78h+var_48], rax
0x18007aca7  lea     rax, [rbp+arg_38]
0x18007acab  mov     [rsp+78h+var_50], rax
0x18007acb0  lea     rax, [rbp+var_20]
0x18007acb4  jmp     loc_18007AB6F
0x18007acb9  mov     rcx, [rbp+var_28]
0x18007acbd  lea     r8, MFMediaType_Video
0x18007acc4  lea     rdx, MF_MT_MAJOR_TYPE
0x18007accb  mov     rax, [rcx]
0x18007acce  mov     rax, [rax+0C0h]
0x18007acd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007acda  mov     ebx, eax
0x18007acdc  test    eax, eax
0x18007acde  jns     loc_18007AD6C
0x18007ace4  mov     eax, cs:dword_1801B76C8
0x18007acea  cmp     eax, 2
0x18007aced  jbe     loc_18007B23C
0x18007acf3  lea     rax, aMfMtMajorTypeF; "MF_MT_MAJOR_TYPE failed"
0x18007acfa  mov     [rbp+arg_20], 237h
0x18007ad01  mov     [rbp+arg_48], rax
0x18007ad08  lea     rdx, byte_18019E727
0x18007ad0f  lea     rax, aCreateencmedia; "CreateEncMediaType"
0x18007ad16  mov     [rbp+arg_38], ebx
0x18007ad19  mov     [rbp+var_10], rax
0x18007ad1d  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007ad24  mov     [rbp+var_18], rax
0x18007ad28  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007ad2f  mov     [rbp+var_20], rax
0x18007ad33  lea     rax, [rbp+arg_48]
0x18007ad3a  mov     [rsp+78h+var_30], rax
0x18007ad3f  lea     rax, [rbp+var_10]
0x18007ad43  mov     [rsp+78h+var_38], rax
0x18007ad48  lea     rax, [rbp+arg_20]
0x18007ad4c  mov     [rsp+78h+var_40], rax
0x18007ad51  lea     rax, [rbp+var_18]
0x18007ad55  mov     [rsp+78h+var_48], rax
0x18007ad5a  lea     rax, [rbp+arg_38]
0x18007ad5e  mov     [rsp+78h+var_50], rax
0x18007ad63  lea     rax, [rbp+var_20]
0x18007ad67  jmp     loc_18007AB6F
0x18007ad6c  mov     rcx, [rbp+var_28]
0x18007ad70  lea     rdx, MF_MT_SUBTYPE
0x18007ad77  mov     r8, rdi
0x18007ad7a  mov     rax, [rcx]
0x18007ad7d  mov     rax, [rax+0C0h]
0x18007ad84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ad89  mov     ebx, eax
0x18007ad8b  test    eax, eax
0x18007ad8d  jns     loc_18007AE1B
0x18007ad93  mov     eax, cs:dword_1801B76C8
0x18007ad99  cmp     eax, 2
0x18007ad9c  jbe     loc_18007B23C
0x18007ada2  lea     rax, aMfMtSubtypeFai; "MF_MT_SUBTYPE failed"
0x18007ada9  mov     [rbp+arg_20], 23Ah
0x18007adb0  mov     [rbp+arg_48], rax
0x18007adb7  lea     rdx, byte_18019E77B
0x18007adbe  lea     rax, aCreateencmedia; "CreateEncMediaType"
0x18007adc5  mov     [rbp+arg_38], ebx
0x18007adc8  mov     [rbp+var_10], rax
0x18007adcc  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007add3  mov     [rbp+var_18], rax
0x18007add7  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007adde  mov     [rbp+var_20], rax
0x18007ade2  lea     rax, [rbp+arg_48]
0x18007ade9  mov     [rsp+78h+var_30], rax
0x18007adee  lea     rax, [rbp+var_10]
0x18007adf2  mov     [rsp+78h+var_38], rax
0x18007adf7  lea     rax, [rbp+arg_20]
0x18007adfb  mov     [rsp+78h+var_40], rax
0x18007ae00  lea     rax, [rbp+var_18]
0x18007ae04  mov     [rsp+78h+var_48], rax
0x18007ae09  lea     rax, [rbp+arg_38]
0x18007ae0d  mov     [rsp+78h+var_50], rax
0x18007ae12  lea     rax, [rbp+var_20]
0x18007ae16  jmp     loc_18007AB6F
0x18007ae1b  mov     rcx, [rbp+var_28]
0x18007ae1f  lea     rdx, MF_MT_FRAME_RATE
0x18007ae26  mov     eax, [rbp+arg_30]
0x18007ae29  mov     r8d, [rbp+arg_28]
0x18007ae2d  shl     r8, 20h
0x18007ae31  mov     r9, [rcx]
0x18007ae34  or      r8, rax
0x18007ae37  mov     rax, [r9+0B0h]
0x18007ae3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ae43  mov     ebx, eax
0x18007ae45  test    eax, eax
0x18007ae47  jns     loc_18007AED5
0x18007ae4d  mov     eax, cs:dword_1801B76C8
0x18007ae53  cmp     eax, 2
0x18007ae56  jbe     loc_18007B23C
0x18007ae5c  lea     rax, aMfMtFrameRateF; "MF_MT_FRAME_RATE failed"
0x18007ae63  mov     [rbp+arg_20], 23Dh
0x18007ae6a  mov     [rbp+arg_48], rax
0x18007ae71  lea     rdx, byte_18019E67F
0x18007ae78  lea     rax, aCreateencmedia; "CreateEncMediaType"
0x18007ae7f  mov     [rbp+arg_38], ebx
0x18007ae82  mov     [rbp+var_10], rax
0x18007ae86  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007ae8d  mov     [rbp+var_18], rax
0x18007ae91  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007ae98  mov     [rbp+var_20], rax
0x18007ae9c  lea     rax, [rbp+arg_48]
0x18007aea3  mov     [rsp+78h+var_30], rax
0x18007aea8  lea     rax, [rbp+var_10]
0x18007aeac  mov     [rsp+78h+var_38], rax
0x18007aeb1  lea     rax, [rbp+arg_20]
0x18007aeb5  mov     [rsp+78h+var_40], rax
0x18007aeba  lea     rax, [rbp+var_18]
0x18007aebe  mov     [rsp+78h+var_48], rax
0x18007aec3  lea     rax, [rbp+arg_38]
0x18007aec7  mov     [rsp+78h+var_50], rax
0x18007aecc  lea     rax, [rbp+var_20]
0x18007aed0  jmp     loc_18007AB6F
0x18007aed5  mov     rcx, [rbp+var_28]
0x18007aed9  lea     rdx, MF_MT_FRAME_SIZE
0x18007aee0  mov     r8, r15
0x18007aee3  shl     r8, 20h
0x18007aee7  or      r8, r14
0x18007aeea  mov     r9, [rcx]
0x18007aeed  mov     rax, [r9+0B0h]
0x18007aef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aef9  mov     ebx, eax
0x18007aefb  test    eax, eax
0x18007aefd  jns     loc_18007AF8B
0x18007af03  mov     eax, cs:dword_1801B76C8
0x18007af09  cmp     eax, 2
0x18007af0c  jbe     loc_18007B23C
0x18007af12  lea     rax, aMfMtFrameSizeF; "MF_MT_FRAME_SIZE failed"
0x18007af19  mov     [rbp+arg_20], 240h
0x18007af20  mov     [rbp+arg_48], rax
0x18007af27  lea     rdx, byte_18019E6D3
0x18007af2e  lea     rax, aCreateencmedia; "CreateEncMediaType"
0x18007af35  mov     [rbp+arg_38], ebx
0x18007af38  mov     [rbp+var_10], rax
0x18007af3c  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007af43  mov     [rbp+var_18], rax
0x18007af47  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007af4e  mov     [rbp+var_20], rax
0x18007af52  lea     rax, [rbp+arg_48]
0x18007af59  mov     [rsp+78h+var_30], rax
0x18007af5e  lea     rax, [rbp+var_10]
0x18007af62  mov     [rsp+78h+var_38], rax
0x18007af67  lea     rax, [rbp+arg_20]
0x18007af6b  mov     [rsp+78h+var_40], rax
0x18007af70  lea     rax, [rbp+var_18]
0x18007af74  mov     [rsp+78h+var_48], rax
0x18007af79  lea     rax, [rbp+arg_38]
0x18007af7d  mov     [rsp+78h+var_50], rax
0x18007af82  lea     rax, [rbp+var_20]
0x18007af86  jmp     loc_18007AB6F
0x18007af8b  mov     rcx, [rbp+var_28]
0x18007af8f  lea     rdx, MF_MT_MPEG2_PROFILE
0x18007af96  mov     r8d, 4Dh ; 'M'
0x18007af9c  mov     rax, [rcx]
0x18007af9f  mov     rax, [rax+0A8h]
0x18007afa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007afab  mov     ebx, eax
0x18007afad  test    eax, eax
0x18007afaf  jns     loc_18007B03D
0x18007afb5  mov     eax, cs:dword_1801B76C8
0x18007afbb  cmp     eax, 2
0x18007afbe  jbe     loc_18007B23C
0x18007afc4  lea     rax, aMfMtMpeg2Profi; "MF_MT_MPEG2_PROFILE failed"
0x18007afcb  mov     [rbp+arg_20], 243h
0x18007afd2  mov     [rbp+arg_48], rax
0x18007afd9  lea     rdx, byte_18019E62B
0x18007afe0  lea     rax, aCreateencmedia; "CreateEncMediaType"
0x18007afe7  mov     [rbp+arg_38], ebx
0x18007afea  mov     [rbp+var_10], rax
0x18007afee  lea     rax, aOnecoreuapTerm_9; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18007aff5  mov     [rbp+var_18], rax
0x18007aff9  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007b000  mov     [rbp+var_20], rax
0x18007b004  lea     rax, [rbp+arg_48]
0x18007b00b  mov     [rsp+78h+var_30], rax
0x18007b010  lea     rax, [rbp+var_10]
0x18007b014  mov     [rsp+78h+var_38], rax
0x18007b019  lea     rax, [rbp+arg_20]
0x18007b01d  mov     [rsp+78h+var_40], rax
0x18007b022  lea     rax, [rbp+var_18]
0x18007b026  mov     [rsp+78h+var_48], rax
0x18007b02b  lea     rax, [rbp+arg_38]
0x18007b02f  mov     [rsp+78h+var_50], rax
0x18007b034  lea     rax, [rbp+var_20]
0x18007b038  jmp     loc_18007AB6F
0x18007b03d  mov     rcx, [rbp+var_28]
0x18007b041  lea     rdx, MF_MT_INTERLACE_MODE
0x18007b048  mov     r8d, 2
0x18007b04e  mov     rax, [rcx]
0x18007b051  mov     rax, [rax+0A8h]
0x18007b058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b05d  mov     ebx, eax
0x18007b05f  test    eax, eax
0x18007b061  jns     loc_18007B0EF
0x18007b067  mov     eax, cs:dword_1801B76C8
0x18007b06d  cmp     eax, 2
  ... truncated ...
```
