# MotionTurboJpeg::CMJPGMFTDataHandler::OnInputTypeChanged(void)

- ea: `0x180041e20`
- end: `0x18004243a`
- name: `?OnInputTypeChanged@CMJPGMFTDataHandler@MotionTurboJpeg@@UEAAJXZ`
- size: `1562`
- prototype: `__int64 __fastcall(MotionTurboJpeg::CMJPGMFTDataHandler *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180014874`
- `0x180014bac`
- `0x180014c80`
- `0x18001b320`
- `0x18001c990`
- `0x18001eb58`
- `0x180020598`
- `0x180024220`
- `0x180041e20`
- `0x18004570c`
- `0x180070010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180041f7d`
- `MFPlat!MFCreateMediaType` at `0x1800420e9`
- `MFPlat!MFCreateMediaType` at `0x180041f7d`
- `MFPlat!MFCreateMediaType` at `0x1800420e9`
- `MFPlat!MFCalculateImageSize` at `0x180041ef1`
- `MFPlat!MFCalculateImageSize` at `0x180041ef1`

## pseudocode

```c
__int64 __fastcall MotionTurboJpeg::CMJPGMFTDataHandler::OnInputTypeChanged(MotionTurboJpeg::CMJPGMFTDataHandler *this)
{
  __int64 v1; // rax
  __int64 *v3; // r14
  __int64 v4; // rdx
  int v5; // ecx
  unsigned int inited; // ebx
  int v7; // r8d
  int v8; // r9d
  UINT32 v9; // esi
  int v10; // eax
  UINT32 v11; // edx
  UINT32 v12; // r8d
  int v13; // esi
  __int64 v14; // rax
  unsigned int v15; // r15d
  __int64 v16; // rsi
  unsigned int v17; // r12d
  unsigned int v18; // edx
  __int64 v19; // rsi
  unsigned int v20; // edx
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // r8
  GUID *v25; // rax
  __int64 v26; // rcx
  int v27; // ecx
  UINT32 v28; // r8d
  int v30; // [rsp+20h] [rbp-A9h]
  IMFMediaType *ppMFType; // [rsp+60h] [rbp-69h] BYREF
  unsigned int v32; // [rsp+68h] [rbp-61h] BYREF
  UINT32 unHeight; // [rsp+6Ch] [rbp-5Dh] BYREF
  UINT32 unWidth; // [rsp+70h] [rbp-59h] BYREF
  int v35; // [rsp+74h] [rbp-55h] BYREF
  unsigned int v36; // [rsp+78h] [rbp-51h] BYREF
  __int64 v37; // [rsp+80h] [rbp-49h] BYREF
  char *v38; // [rsp+88h] [rbp-41h] BYREF
  int v39; // [rsp+90h] [rbp-39h]
  int v40; // [rsp+94h] [rbp-35h]
  _QWORD v41[2]; // [rsp+98h] [rbp-31h] BYREF
  __int128 v42; // [rsp+A8h] [rbp-21h] BYREF
  GUID v43; // [rsp+B8h] [rbp-11h] BYREF
  _DWORD v44[4]; // [rsp+C8h] [rbp-1h] BYREF

  v1 = *((_QWORD *)this + 1);
  qmemcpy(v41, "NV12YUY2AYUV", 12);
  v3 = *(__int64 **)(v1 + 48);
  v42 = 0;
  inited = (*(__int64 (__fastcall **)(__int64 *, const GUID *, __int128 *))(*v3 + 80))(v3, &MF_MT_SUBTYPE, &v42);
  if ( !inited )
  {
    unWidth = 0;
    unHeight = 0;
    inited = MFGetAttribute2UINT32asUINT64(v3, v4, &unWidth, &unHeight);
    if ( !inited )
    {
      v9 = unHeight;
      v10 = v42;
      v11 = unWidth;
      v12 = unHeight;
      *((_DWORD *)this + 124) = 40;
      *((_WORD *)this + 255) = 24;
      *((_DWORD *)this + 128) = v10;
      *((_DWORD *)this + 126) = v9;
      *((_DWORD *)this + 125) = v11;
      inited = MFCalculateImageSize(&MFVideoFormat_RGB24, v11, v12, (UINT32 *)this + 129);
      if ( !inited )
      {
        v13 = v9 & 1;
        inited = CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(*((CMFTSimpleTypeHandler **)this + 61), 3 - v13);
        if ( !inited )
        {
          ppMFType = 0;
          v14 = *v3;
          v32 = 7;
          if ( (*(int (__fastcall **)(__int64 *, const GUID *, unsigned int *))(v14 + 56))(
                 v3,
                 &MF_MT_INTERLACE_MODE,
                 &v32) < 0 )
            v32 = 7;
          if ( v13 )
          {
            v15 = 0;
            v16 = 0;
            while ( 1 )
            {
              v17 = *((_DWORD *)v41 + v16);
              if ( v17 != 842094158 )
              {
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
                inited = MFCreateMediaType(&ppMFType);
                if ( inited )
                  goto LABEL_27;
                inited = (*(__int64 (__fastcall **)(__int64 *, IMFMediaType *))(*v3 + 256))(v3, ppMFType);
                if ( inited )
                  goto LABEL_27;
                ((void (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->DeleteItem)(
                  ppMFType,
                  &MF_MT_SAMPLE_SIZE);
                ((void (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->DeleteItem)(
                  ppMFType,
                  &MF_MT_AVG_BITRATE);
                ((void (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->DeleteItem)(
                  ppMFType,
                  &MF_MT_COMPRESSED);
                v39 = -1442840448;
                v40 = 1905997824;
                v38 = (char *)(v17 | 0x10000000000000LL);
                inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, char **))ppMFType->lpVtbl->SetGUID)(
                           ppMFType,
                           &MF_MT_SUBTYPE,
                           &v38);
                if ( inited )
                  goto LABEL_27;
                inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                           ppMFType,
                           &MF_MT_ALL_SAMPLES_INDEPENDENT,
                           1);
                if ( inited )
                  goto LABEL_27;
                inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                           ppMFType,
                           &MF_MT_INTERLACE_MODE,
                           v32);
                if ( inited )
                  goto LABEL_27;
                inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                           ppMFType,
                           &MF_MT_VIDEO_NOMINAL_RANGE,
                           1);
                if ( inited )
                  goto LABEL_27;
                v18 = v15++;
                CMFTSimpleTypeHandler::SetAvailableOutputType(*((CMFTSimpleTypeHandler **)this + 61), v18, ppMFType);
              }
              v16 = (unsigned int)(v16 + 1);
              if ( (unsigned int)v16 >= 3 )
                goto LABEL_27;
            }
          }
          v19 = 0;
          do
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
            inited = MFCreateMediaType(&ppMFType);
            if ( inited )
              break;
            inited = (*(__int64 (__fastcall **)(__int64 *, IMFMediaType *))(*v3 + 256))(v3, ppMFType);
            if ( inited )
              break;
            ((void (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->DeleteItem)(
              ppMFType,
              &MF_MT_SAMPLE_SIZE);
            ((void (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->DeleteItem)(
              ppMFType,
              &MF_MT_AVG_BITRATE);
            ((void (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->DeleteItem)(
              ppMFType,
              &MF_MT_COMPRESSED);
            LODWORD(v38) = *((_DWORD *)v41 + v19);
            HIDWORD(v38) = 0x100000;
            v39 = -1442840448;
            v40 = 1905997824;
            inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, char **))ppMFType->lpVtbl->SetGUID)(
                       ppMFType,
                       &MF_MT_SUBTYPE,
                       &v38);
            if ( inited )
              break;
            inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                       ppMFType,
                       &MF_MT_ALL_SAMPLES_INDEPENDENT,
                       1);
            if ( inited )
              break;
            inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                       ppMFType,
                       &MF_MT_INTERLACE_MODE,
                       v32);
            if ( inited )
              break;
            inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                       ppMFType,
                       &MF_MT_VIDEO_NOMINAL_RANGE,
                       1);
            if ( inited )
              break;
            v20 = v19;
            v19 = (unsigned int)(v19 + 1);
            CMFTSimpleTypeHandler::SetAvailableOutputType(*((CMFTSimpleTypeHandler **)this + 61), v20, ppMFType);
          }
          while ( (unsigned int)v19 < 3 );
LABEL_27:
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::__private_IsEnabled() )
          {
            v22 = *((_QWORD *)this + 91);
            if ( !v22
              || !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 320LL))(
                    v22,
                    MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT) )
            {
              v23 = *((_QWORD *)this + 91);
              v24 = 0;
              v43 = GUID_NULL;
              if ( v23 )
              {
                v25 = (GUID *)(*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v23 + 280LL))(
                                v23,
                                v41,
                                0);
                v26 = *((_QWORD *)this + 91);
                v43 = *v25;
                v24 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v26 + 296LL))(v26);
              }
              if ( (unsigned int)dword_18009C060 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_18009C060, 0x400000000000LL, v24) )
              {
                v37 = 0x1000000;
                v38 = (char *)this + 712;
                unWidth = v28;
                v41[0] = &v43;
                unHeight = *((_DWORD *)this + 128);
                v35 = *((_DWORD *)this + 126);
                v36 = *((_DWORD *)this + 125);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
                  v27,
                  (unsigned int)word_180093B0A,
                  v28,
                  v21,
                  (__int64)&v36,
                  (__int64)&v35,
                  (__int64)&unHeight,
                  (__int64)v41,
                  (__int64)&unWidth,
                  (__int64)&v38,
                  (__int64)&v37);
              }
              v44[0] = *((_DWORD *)this + 125);
              LOBYTE(v21) = 1;
              v44[1] = *((_DWORD *)this + 126);
              LOBYTE(v30) = 1;
              (*(void (__fastcall **)(char *, __int64, _DWORD *, __int64, int))(*((_QWORD *)this + 92) + 56LL))(
                (char *)this + 736,
                1,
                v44,
                v21,
                v30);
            }
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
        }
      }
    }
  }
  if ( (unsigned int)dword_18009C028 > 5 )
  {
    LOWORD(v32) = *((_WORD *)this + 255);
    v35 = *((_DWORD *)this + 128);
    unWidth = *((_DWORD *)this + 125);
    unHeight = *((_DWORD *)this + 126);
    v36 = inited;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)&word_180093CDE,
      v7,
      v8,
      (__int64)&unHeight,
      (__int64)&unWidth,
      (__int64)&v35,
      (__int64)&v32,
      (__int64)&v36);
  }
  return inited;
}

```

## disassembly

```asm
0x180041e20  push    rbp
0x180041e22  push    rbx
0x180041e23  push    rsi
0x180041e24  push    rdi
0x180041e25  push    r12
0x180041e27  push    r13
0x180041e29  push    r14
0x180041e2b  push    r15
0x180041e2d  lea     rbp, [rsp-1Fh]
0x180041e32  sub     rsp, 0E8h
0x180041e39  mov     rax, cs:__security_cookie
0x180041e40  xor     rax, rsp
0x180041e43  mov     [rbp+57h+var_48], rax
0x180041e47  mov     rax, [rcx+8]
0x180041e4b  lea     r8, [rbp+57h+var_78]
0x180041e4f  mov     rdi, rcx
0x180041e52  mov     dword ptr [rbp+57h+var_88], 3231564Eh
0x180041e59  xorps   xmm0, xmm0
0x180041e5c  mov     dword ptr [rbp+57h+var_88+4], 32595559h
0x180041e63  lea     rdx, MF_MT_SUBTYPE
0x180041e6a  mov     [rbp+57h+var_80], 56555941h
0x180041e71  mov     r14, [rax+30h]
0x180041e75  mov     rcx, r14
0x180041e78  movups  [rbp+57h+var_78], xmm0
0x180041e7c  mov     rax, [r14]
0x180041e7f  mov     rax, [rax+50h]
0x180041e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e88  mov     ebx, eax
0x180041e8a  test    eax, eax
0x180041e8c  jnz     loc_1800423AB
0x180041e92  lea     r9, [rbp+57h+unHeight]
0x180041e96  mov     [rbp+57h+unWidth], eax
0x180041e99  lea     r8, [rbp+57h+unWidth]
0x180041e9d  mov     [rbp+57h+unHeight], eax
0x180041ea0  mov     rcx, r14
0x180041ea3  call    MFGetAttribute2UINT32asUINT64
0x180041ea8  mov     ebx, eax
0x180041eaa  test    eax, eax
0x180041eac  jnz     loc_1800423AB
0x180041eb2  mov     esi, [rbp+57h+unHeight]
0x180041eb5  lea     r9, [rdi+204h]; pcbImageSize
0x180041ebc  mov     eax, dword ptr [rbp+57h+var_78]
0x180041ebf  lea     rcx, MFVideoFormat_RGB24; guidSubtype
0x180041ec6  mov     edx, [rbp+57h+unWidth]; unWidth
0x180041ec9  mov     r8d, esi; unHeight
0x180041ecc  mov     dword ptr [rdi+1F0h], 28h ; '('
0x180041ed6  mov     word ptr [rdi+1FEh], 18h
0x180041edf  mov     [rdi+200h], eax
0x180041ee5  mov     [rdi+1F8h], esi
0x180041eeb  mov     [rdi+1F4h], edx
0x180041ef1  call    cs:__imp_MFCalculateImageSize
0x180041ef7  mov     ebx, eax
0x180041ef9  test    eax, eax
0x180041efb  jnz     loc_1800423AB
0x180041f01  mov     rcx, [rdi+1E8h]; this
0x180041f08  lea     edx, [rax+3]
0x180041f0b  and     esi, 1
0x180041f0e  sub     edx, esi; unsigned int
0x180041f10  call    ?InitAvailableOutputTypeArray@CMFTSimpleTypeHandler@@IEAAJK@Z; CMFTSimpleTypeHandler::InitAvailableOutputTypeArray(ulong)
0x180041f15  mov     ebx, eax
0x180041f17  test    eax, eax
0x180041f19  jnz     loc_1800423AB
0x180041f1f  lea     r15d, [rax+7]
0x180041f23  mov     [rbp+57h+ppMFType], 0
0x180041f2b  mov     rax, [r14]
0x180041f2e  lea     r8, [rbp+57h+var_B8]
0x180041f32  lea     rdx, MF_MT_INTERLACE_MODE
0x180041f39  mov     [rbp+57h+var_B8], r15d
0x180041f3d  mov     rcx, r14
0x180041f40  mov     rax, [rax+38h]
0x180041f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f49  test    eax, eax
0x180041f4b  jns     short loc_180041F51
0x180041f4d  mov     [rbp+57h+var_B8], r15d
0x180041f51  test    esi, esi
0x180041f53  jz      loc_1800420DA
0x180041f59  xor     r15d, r15d
0x180041f5c  xor     esi, esi
0x180041f5e  mov     r12d, dword ptr [rbp+rsi*4+57h+var_88]
0x180041f63  cmp     r12d, 3231564Eh
0x180041f6a  jz      loc_1800420CA
0x180041f70  lea     rcx, [rbp+57h+ppMFType]
0x180041f74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041f79  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x180041f7d  call    cs:__imp_MFCreateMediaType
0x180041f83  mov     ebx, eax
0x180041f85  test    eax, eax
0x180041f87  jnz     loc_180042234
0x180041f8d  mov     rax, [r14]
0x180041f90  mov     rcx, r14
0x180041f93  mov     rdx, [rbp+57h+ppMFType]
0x180041f97  mov     rax, [rax+100h]
0x180041f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fa3  mov     ebx, eax
0x180041fa5  test    eax, eax
0x180041fa7  jnz     loc_180042234
0x180041fad  mov     rcx, [rbp+57h+ppMFType]
0x180041fb1  lea     rdx, MF_MT_SAMPLE_SIZE
0x180041fb8  mov     rax, [rcx]
0x180041fbb  mov     rax, [rax+98h]
0x180041fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fc7  mov     rcx, [rbp+57h+ppMFType]
0x180041fcb  lea     rdx, MF_MT_AVG_BITRATE
0x180041fd2  mov     rax, [rcx]
0x180041fd5  mov     rax, [rax+98h]
0x180041fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fe1  mov     rcx, [rbp+57h+ppMFType]
0x180041fe5  lea     rdx, MF_MT_COMPRESSED
0x180041fec  mov     rax, [rcx]
0x180041fef  mov     rax, [rax+98h]
0x180041ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ffb  mov     rcx, [rbp+57h+ppMFType]
0x180041fff  lea     r8, [rbp+57h+var_98]
0x180042003  mov     dword ptr [rbp+57h+var_98+4], 100000h
0x18004200a  lea     rdx, MF_MT_SUBTYPE
0x180042011  mov     [rbp+57h+var_90], 0AA000080h
0x180042018  mov     [rbp+57h+var_8C], 719B3800h
0x18004201f  mov     dword ptr [rbp+57h+var_98], r12d
0x180042023  mov     rax, [rcx]
0x180042026  mov     rax, [rax+0C0h]
0x18004202d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042032  mov     ebx, eax
0x180042034  test    eax, eax
0x180042036  jnz     loc_180042234
0x18004203c  mov     rcx, [rbp+57h+ppMFType]
0x180042040  lea     r8d, [rbx+1]
0x180042044  lea     rdx, MF_MT_ALL_SAMPLES_INDEPENDENT
0x18004204b  mov     rax, [rcx]
0x18004204e  mov     rax, [rax+0A8h]
0x180042055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004205a  mov     ebx, eax
0x18004205c  test    eax, eax
0x18004205e  jnz     loc_180042234
0x180042064  mov     rcx, [rbp+57h+ppMFType]
0x180042068  lea     rdx, MF_MT_INTERLACE_MODE
0x18004206f  mov     r8d, [rbp+57h+var_B8]
0x180042073  mov     rax, [rcx]
0x180042076  mov     rax, [rax+0A8h]
0x18004207d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042082  mov     ebx, eax
0x180042084  test    eax, eax
0x180042086  jnz     loc_180042234
0x18004208c  mov     rcx, [rbp+57h+ppMFType]
0x180042090  lea     r8d, [rbx+1]
0x180042094  lea     rdx, MF_MT_VIDEO_NOMINAL_RANGE
0x18004209b  mov     rax, [rcx]
0x18004209e  mov     rax, [rax+0A8h]
0x1800420a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800420aa  mov     ebx, eax
0x1800420ac  test    eax, eax
0x1800420ae  jnz     loc_180042234
0x1800420b4  mov     r8, [rbp+57h+ppMFType]; struct IMFMediaType *
0x1800420b8  mov     edx, r15d; unsigned int
0x1800420bb  mov     rcx, [rdi+1E8h]; this
0x1800420c2  inc     r15d
0x1800420c5  call    ?SetAvailableOutputType@CMFTSimpleTypeHandler@@QEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleTypeHandler::SetAvailableOutputType(ulong,IMFMediaType *)
0x1800420ca  inc     esi
0x1800420cc  cmp     esi, 3
0x1800420cf  jb      loc_180041F5E
0x1800420d5  jmp     loc_180042234
0x1800420da  xor     esi, esi
0x1800420dc  lea     rcx, [rbp+57h+ppMFType]
0x1800420e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800420e5  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x1800420e9  call    cs:__imp_MFCreateMediaType
0x1800420ef  mov     ebx, eax
0x1800420f1  test    eax, eax
0x1800420f3  jnz     loc_180042234
0x1800420f9  mov     rax, [r14]
0x1800420fc  mov     rcx, r14
0x1800420ff  mov     rdx, [rbp+57h+ppMFType]
0x180042103  mov     rax, [rax+100h]
0x18004210a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004210f  mov     ebx, eax
0x180042111  test    eax, eax
0x180042113  jnz     loc_180042234
0x180042119  mov     rcx, [rbp+57h+ppMFType]
0x18004211d  lea     rdx, MF_MT_SAMPLE_SIZE
0x180042124  mov     rax, [rcx]
0x180042127  mov     rax, [rax+98h]
0x18004212e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042133  mov     rcx, [rbp+57h+ppMFType]
0x180042137  lea     rdx, MF_MT_AVG_BITRATE
0x18004213e  mov     rax, [rcx]
0x180042141  mov     rax, [rax+98h]
0x180042148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004214d  mov     rcx, [rbp+57h+ppMFType]
0x180042151  lea     rdx, MF_MT_COMPRESSED
0x180042158  mov     rax, [rcx]
0x18004215b  mov     rax, [rax+98h]
0x180042162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042167  mov     ecx, dword ptr [rbp+rsi*4+57h+var_88]
0x18004216b  lea     r8, [rbp+57h+var_98]
0x18004216f  mov     dword ptr [rbp+57h+var_98], ecx
0x180042172  lea     rdx, MF_MT_SUBTYPE
0x180042179  mov     rcx, [rbp+57h+ppMFType]
0x18004217d  mov     dword ptr [rbp+57h+var_98+4], 100000h
0x180042184  mov     [rbp+57h+var_90], 0AA000080h
0x18004218b  mov     [rbp+57h+var_8C], 719B3800h
0x180042192  mov     rax, [rcx]
0x180042195  mov     rax, [rax+0C0h]
0x18004219c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421a1  mov     ebx, eax
0x1800421a3  test    eax, eax
0x1800421a5  jnz     loc_180042234
0x1800421ab  mov     rcx, [rbp+57h+ppMFType]
0x1800421af  lea     r8d, [rbx+1]
0x1800421b3  lea     rdx, MF_MT_ALL_SAMPLES_INDEPENDENT
0x1800421ba  mov     rax, [rcx]
0x1800421bd  mov     rax, [rax+0A8h]
0x1800421c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421c9  mov     ebx, eax
0x1800421cb  test    eax, eax
0x1800421cd  jnz     short loc_180042234
0x1800421cf  mov     rcx, [rbp+57h+ppMFType]
0x1800421d3  lea     rdx, MF_MT_INTERLACE_MODE
0x1800421da  mov     r8d, [rbp+57h+var_B8]
0x1800421de  mov     rax, [rcx]
0x1800421e1  mov     rax, [rax+0A8h]
0x1800421e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421ed  mov     ebx, eax
0x1800421ef  test    eax, eax
0x1800421f1  jnz     short loc_180042234
0x1800421f3  mov     rcx, [rbp+57h+ppMFType]
0x1800421f7  lea     r8d, [rbx+1]
0x1800421fb  lea     rdx, MF_MT_VIDEO_NOMINAL_RANGE
0x180042202  mov     rax, [rcx]
0x180042205  mov     rax, [rax+0A8h]
0x18004220c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042211  mov     ebx, eax
0x180042213  test    eax, eax
0x180042215  jnz     short loc_180042234
0x180042217  mov     r8, [rbp+57h+ppMFType]; struct IMFMediaType *
0x18004221b  mov     edx, esi; unsigned int
0x18004221d  mov     rcx, [rdi+1E8h]; this
0x180042224  inc     esi
0x180042226  call    ?SetAvailableOutputType@CMFTSimpleTypeHandler@@QEAAXKPEAUIMFMediaType@@@Z; CMFTSimpleTypeHandler::SetAvailableOutputType(ulong,IMFMediaType *)
0x18004222b  cmp     esi, 3
0x18004222e  jb      loc_1800420DC
0x180042234  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CD_MJPEG_MFT_Decoder>::__private_IsEnabled(void)
0x180042239  test    al, al
0x18004223b  jz      loc_1800423A2
0x180042241  mov     rcx, [rdi+2D8h]
0x180042248  test    rcx, rcx
0x18004224b  jz      short loc_18004226B
0x18004224d  mov     rax, [rcx]
0x180042250  lea     rdx, MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT
0x180042257  mov     rax, [rax+140h]
0x18004225e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042263  test    eax, eax
0x180042265  jnz     loc_1800423A2
0x18004226b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180042272  mov     rcx, [rdi+2D8h]
0x180042279  xor     r8d, r8d
0x18004227c  movdqu  [rbp+57h+var_68], xmm0
0x180042281  test    rcx, rcx
0x180042284  jz      short loc_1800422BA
0x180042286  mov     rax, [rcx]
0x180042289  lea     rdx, [rbp+57h+var_88]
0x18004228d  mov     rax, [rax+118h]
0x180042294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042299  mov     rcx, [rdi+2D8h]
0x1800422a0  movups  xmm0, xmmword ptr [rax]
0x1800422a3  movdqu  [rbp+57h+var_68], xmm0
0x1800422a8  mov     rax, [rcx]
0x1800422ab  mov     rax, [rax+128h]
0x1800422b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800422b7  mov     r8d, eax
0x1800422ba  mov     ecx, cs:dword_18009C060
0x1800422c0  cmp     ecx, 5
0x1800422c3  jbe     loc_18004236C
0x1800422c9  mov     rdx, 400000000000h
0x1800422d3  lea     rcx, dword_18009C060
0x1800422da  call    _tlgKeywordOn
0x1800422df  test    al, al
0x1800422e1  jz      loc_18004236C
0x1800422e7  lea     rax, [rdi+2C8h]
0x1800422ee  mov     [rbp+57h+var_A0], 1000000h
0x1800422f6  mov     [rbp+57h+var_98], rax
0x1800422fa  lea     rdx, word_180093B0A
0x180042301  lea     rax, [rbp+57h+var_68]
0x180042305  mov     [rbp+57h+unWidth], r8d
0x180042309  mov     [rbp+57h+var_88], rax
0x18004230d  mov     eax, [rdi+200h]
0x180042313  mov     [rbp+57h+unHeight], eax
0x180042316  mov     eax, [rdi+1F8h]
0x18004231c  mov     [rbp+57h+var_AC], eax
0x18004231f  mov     eax, [rdi+1F4h]
0x180042325  mov     [rbp+57h+var_A8], eax
0x180042328  lea     rax, [rbp+57h+var_A0]
0x18004232c  mov     [rsp+120h+var_D0], rax
0x180042331  lea     rax, [rbp+57h+var_98]
0x180042335  mov     [rsp+120h+var_D8], rax
0x18004233a  lea     rax, [rbp+57h+unWidth]
0x18004233e  mov     [rsp+120h+var_E0], rax
0x180042343  lea     rax, [rbp+57h+var_88]
0x180042347  mov     [rsp+120h+var_E8], rax
0x18004234c  lea     rax, [rbp+57h+unHeight]
0x180042350  mov     [rsp+120h+var_F0], rax
0x180042355  lea     rax, [rbp+57h+var_AC]
  ... truncated ...
```
