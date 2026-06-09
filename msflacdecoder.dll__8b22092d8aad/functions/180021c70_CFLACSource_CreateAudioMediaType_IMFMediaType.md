# CFLACSource::CreateAudioMediaType(IMFMediaType * *)

- ea: `0x180021c70`
- end: `0x1800220f6`
- name: `?CreateAudioMediaType@CFLACSource@@AEAAJPEAPEAUIMFMediaType@@@Z`
- size: `1158`
- prototype: `__int64 __fastcall(CFLACSource *__hidden this, struct IMFMediaType **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180022730`

## callees

- `0x180016e48`
- `0x180020398`
- `0x180020484`
- `0x180021c70`
- `0x180056010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180021cdf`
- `MFPlat!MFCreateMediaType` at `0x180021cdf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFLACSource::CreateAudioMediaType(CFLACSource *this, struct IMFMediaType **a2)
{
  int v5; // ecx
  __int64 v6; // rdx
  unsigned __int64 v7; // rdi
  __int64 v8; // rcx
  IMFMediaType *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v13[4]; // [rsp+40h] [rbp-20h] BYREF
  HRESULT v14; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v15; // [rsp+A0h] [rbp+40h] BYREF
  IMFMediaType *ppMFType; // [rsp+A8h] [rbp+48h] BYREF

  v14 = 0;
  v13[1] = this;
  v13[2] = &v14;
  ppMFType = 0;
  v11 = 0;
  v12 = 0;
  v15 = 0;
  if ( (*((_BYTE *)this + 390) & 1) == 0 )
  {
    ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v11);
    return 3222091444LL;
  }
  v14 = MFCreateMediaType(&ppMFType);
  if ( v14 >= 0 )
  {
    v14 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
            ppMFType,
            &MF_MT_MAJOR_TYPE,
            &MFMediaType_Audio);
    if ( v14 >= 0 )
    {
      v14 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int128 *))ppMFType->lpVtbl->SetGUID)(
              ppMFType,
              &MF_MT_SUBTYPE,
              &MFAudioFormat_FLAC);
      if ( v14 >= 0 )
      {
        v14 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                ppMFType,
                &MF_MT_AUDIO_SAMPLES_PER_SECOND,
                *((unsigned int *)this + 126));
        if ( v14 >= 0 )
        {
          if ( !*((_DWORD *)this + 126) )
          {
            v14 = -1072875852;
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              WPP_SF_qd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                266,
                &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids,
                this,
                -1072875852);
            goto LABEL_50;
          }
          v14 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 34) + 328LL))(
                  *((_QWORD *)this + 34),
                  &v11);
          if ( v14 >= 0 )
          {
            v14 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, unsigned int *))(*(_QWORD *)v11 + 24LL))(
                    v11,
                    &v12,
                    0,
                    &v15);
            if ( v14 >= 0 )
            {
              v14 = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *, __int64, _QWORD))ppMFType->lpVtbl->SetBlob)(
                      ppMFType,
                      MF_MT_FLAC_METADATA_BLOCKS,
                      v12,
                      v15);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 32LL))(v11);
              if ( v14 >= 0 )
              {
                v14 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                        ppMFType,
                        &MF_MT_AUDIO_NUM_CHANNELS,
                        *((unsigned int *)this + 127));
                if ( v14 >= 0 )
                {
                  v14 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                          ppMFType,
                          &MF_MT_AUDIO_BITS_PER_SAMPLE,
                          *((unsigned int *)this + 128));
                  if ( v14 >= 0 )
                  {
                    v14 = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                            ppMFType,
                            MF_MT_AUDIO_FLAC_MAX_BLOCK_SIZE,
                            *((unsigned int *)this + 123));
                    if ( v14 >= 0 )
                    {
                      v14 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                              ppMFType,
                              &MF_MT_AUDIO_BLOCK_ALIGNMENT,
                              (unsigned int)(*((_DWORD *)this + 127) * (*((_DWORD *)this + 128) >> 3)));
                      if ( v14 >= 0 )
                      {
                        v7 = *((_QWORD *)this + 65) / (unsigned __int64)*((unsigned int *)this + 126);
                        *((_QWORD *)this + 45) = 10000000LL * (unsigned int)v7;
                        v13[0] = 0;
                        v8 = *((_QWORD *)this + 39);
                        if ( v8
                          && (*(int (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v8 + 32LL))(v8, v13) >= 0
                          && v13[0] != -1
                          && (_DWORD)v7 )
                        {
                          *((_DWORD *)this + 76) = (v13[0] - (unsigned __int64)*((unsigned int *)this + 98))
                                                 / (unsigned int)v7;
                        }
                        v14 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                                ppMFType,
                                &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
                                *((unsigned int *)this + 76));
                        if ( v14 >= 0 )
                        {
                          v9 = ppMFType;
                          *a2 = ppMFType;
                          ((void (__fastcall *)(IMFMediaType *))v9->lpVtbl->AddRef)(v9);
                        }
                        else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        {
                          v6 = 274;
                          goto LABEL_6;
                        }
                      }
                      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                      {
                        v6 = 273;
                        goto LABEL_6;
                      }
                    }
                    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    {
                      v6 = 272;
                      goto LABEL_6;
                    }
                  }
                  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  {
                    v6 = 271;
                    goto LABEL_6;
                  }
                }
                else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v6 = 270;
                  goto LABEL_6;
                }
              }
              else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v6 = 269;
                goto LABEL_6;
              }
            }
            else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v6 = 268;
              goto LABEL_6;
            }
          }
          else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v6 = 267;
            goto LABEL_6;
          }
        }
        else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v6 = 265;
          goto LABEL_6;
        }
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v6 = 264;
        goto LABEL_6;
      }
    }
    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v6 = 263;
      goto LABEL_6;
    }
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v6 = 262;
LABEL_6:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v5);
  }
LABEL_50:
  if ( ppMFType )
  {
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
    ppMFType = 0;
  }
  v10 = v14;
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v11);
  return v10;
}

```

## disassembly

```asm
0x180021c70  mov     [rsp-28h+arg_8], rbx
0x180021c75  push    rbp
0x180021c76  push    rsi
0x180021c77  push    rdi
0x180021c78  push    r12
0x180021c7a  push    r14
0x180021c7c  mov     rbp, rsp
0x180021c7f  sub     rsp, 60h
0x180021c83  mov     r14, rdx
0x180021c86  mov     rbx, rcx
0x180021c89  mov     [rbp+arg_0], 0
0x180021c90  mov     [rbp+var_18], rcx
0x180021c94  lea     rax, [rbp+arg_0]
0x180021c98  mov     [rbp+var_10], rax
0x180021c9c  mov     [rbp+ppMFType], 0
0x180021ca4  mov     [rbp+var_30], 0
0x180021cac  mov     [rbp+var_28], 0
0x180021cb4  mov     [rbp+arg_10], 0
0x180021cbb  mov     r12b, 1
0x180021cbe  test    [rcx+186h], r12b
0x180021cc5  jnz     short loc_180021CDB
0x180021cc7  lea     rcx, [rbp+var_30]
0x180021ccb  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x180021cd0  nop
0x180021cd1  mov     eax, 0C00D36B4h
0x180021cd6  jmp     loc_1800220E2
0x180021cdb  lea     rcx, [rbp+ppMFType]; ppMFType
0x180021cdf  call    cs:__imp_MFCreateMediaType
0x180021ce5  mov     ecx, eax
0x180021ce7  mov     [rbp+arg_0], eax
0x180021cea  test    eax, eax
0x180021cec  jns     short loc_180021D24
0x180021cee  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021cf3  cmp     al, r12b
0x180021cf6  jb      loc_1800220B6
0x180021cfc  mov     edx, 106h
0x180021d01  mov     [rsp+60h+var_40], ecx
0x180021d05  mov     r9, rbx
0x180021d08  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x180021d0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d16  mov     rcx, [rcx+10h]
0x180021d1a  call    WPP_SF_qd
0x180021d1f  jmp     loc_1800220B6
0x180021d24  mov     rcx, [rbp+ppMFType]
0x180021d28  mov     rax, [rcx]
0x180021d2b  lea     r8, MFMediaType_Audio
0x180021d32  lea     rdx, MF_MT_MAJOR_TYPE
0x180021d39  mov     rax, [rax+0C0h]
0x180021d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d45  mov     ecx, eax
0x180021d47  mov     [rbp+arg_0], eax
0x180021d4a  test    eax, eax
0x180021d4c  jns     short loc_180021D63
0x180021d4e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021d53  cmp     al, r12b
0x180021d56  jb      loc_1800220B6
0x180021d5c  mov     edx, 107h
0x180021d61  jmp     short loc_180021D01
0x180021d63  mov     rcx, [rbp+ppMFType]
0x180021d67  mov     rax, [rcx]
0x180021d6a  lea     r8, MFAudioFormat_FLAC
0x180021d71  lea     rdx, MF_MT_SUBTYPE
0x180021d78  mov     rax, [rax+0C0h]
0x180021d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d84  mov     ecx, eax
0x180021d86  mov     [rbp+arg_0], eax
0x180021d89  test    eax, eax
0x180021d8b  jns     short loc_180021DA5
0x180021d8d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021d92  cmp     al, r12b
0x180021d95  jb      loc_1800220B6
0x180021d9b  mov     edx, 108h
0x180021da0  jmp     loc_180021D01
0x180021da5  mov     rcx, [rbp+ppMFType]
0x180021da9  mov     rax, [rcx]
0x180021dac  mov     r8d, [rbx+1F8h]
0x180021db3  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x180021dba  mov     rax, [rax+0A8h]
0x180021dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dc6  mov     ecx, eax
0x180021dc8  mov     [rbp+arg_0], eax
0x180021dcb  test    eax, eax
0x180021dcd  jns     short loc_180021DE7
0x180021dcf  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021dd4  cmp     al, r12b
0x180021dd7  jb      loc_1800220B6
0x180021ddd  mov     edx, 109h
0x180021de2  jmp     loc_180021D01
0x180021de7  cmp     dword ptr [rbx+1F8h], 0
0x180021dee  jnz     short loc_180021E17
0x180021df0  mov     [rbp+arg_0], 0C00D36B4h
0x180021df7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021dfc  cmp     al, r12b
0x180021dff  jb      loc_1800220B6
0x180021e05  mov     edx, 10Ah
0x180021e0a  mov     [rsp+60h+var_40], 0C00D36B4h
0x180021e12  jmp     loc_180021D05
0x180021e17  mov     rcx, [rbx+110h]
0x180021e1e  mov     rax, [rcx]
0x180021e21  lea     rdx, [rbp+var_30]
0x180021e25  mov     rax, [rax+148h]
0x180021e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e31  mov     ecx, eax
0x180021e33  mov     [rbp+arg_0], eax
0x180021e36  test    eax, eax
0x180021e38  jns     short loc_180021E52
0x180021e3a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021e3f  cmp     al, r12b
0x180021e42  jb      loc_1800220B6
0x180021e48  mov     edx, 10Bh
0x180021e4d  jmp     loc_180021D01
0x180021e52  mov     rcx, [rbp+var_30]
0x180021e56  mov     rax, [rcx]
0x180021e59  lea     r9, [rbp+arg_10]
0x180021e5d  xor     r8d, r8d
0x180021e60  lea     rdx, [rbp+var_28]
0x180021e64  mov     rax, [rax+18h]
0x180021e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e6d  mov     ecx, eax
0x180021e6f  mov     [rbp+arg_0], eax
0x180021e72  test    eax, eax
0x180021e74  jns     short loc_180021E8E
0x180021e76  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021e7b  cmp     al, r12b
0x180021e7e  jb      loc_1800220B6
0x180021e84  mov     edx, 10Ch
0x180021e89  jmp     loc_180021D01
0x180021e8e  mov     rcx, [rbp+ppMFType]
0x180021e92  mov     rax, [rcx]
0x180021e95  mov     r9d, [rbp+arg_10]
0x180021e99  mov     r8, [rbp+var_28]
0x180021e9d  lea     rdx, MF_MT_FLAC_METADATA_BLOCKS
0x180021ea4  mov     rax, [rax+0D0h]
0x180021eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021eb0  mov     [rbp+arg_0], eax
0x180021eb3  mov     rcx, [rbp+var_30]
0x180021eb7  mov     rax, [rcx]
0x180021eba  mov     rax, [rax+20h]
0x180021ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ec3  mov     ecx, [rbp+arg_0]
0x180021ec6  test    ecx, ecx
0x180021ec8  jns     short loc_180021EE2
0x180021eca  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021ecf  cmp     al, r12b
0x180021ed2  jb      loc_1800220B6
0x180021ed8  mov     edx, 10Dh
0x180021edd  jmp     loc_180021D01
0x180021ee2  mov     rcx, [rbp+ppMFType]
0x180021ee6  mov     rax, [rcx]
0x180021ee9  mov     r8d, [rbx+1FCh]
0x180021ef0  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x180021ef7  mov     rax, [rax+0A8h]
0x180021efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f03  mov     ecx, eax
0x180021f05  mov     [rbp+arg_0], eax
0x180021f08  test    eax, eax
0x180021f0a  jns     short loc_180021F24
0x180021f0c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021f11  cmp     al, r12b
0x180021f14  jb      loc_1800220B6
0x180021f1a  mov     edx, 10Eh
0x180021f1f  jmp     loc_180021D01
0x180021f24  mov     rcx, [rbp+ppMFType]
0x180021f28  mov     rax, [rcx]
0x180021f2b  mov     r8d, [rbx+200h]
0x180021f32  lea     rdx, MF_MT_AUDIO_BITS_PER_SAMPLE
0x180021f39  mov     rax, [rax+0A8h]
0x180021f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f45  mov     ecx, eax
0x180021f47  mov     [rbp+arg_0], eax
0x180021f4a  test    eax, eax
0x180021f4c  jns     short loc_180021F66
0x180021f4e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021f53  cmp     al, r12b
0x180021f56  jb      loc_1800220B6
0x180021f5c  mov     edx, 10Fh
0x180021f61  jmp     loc_180021D01
0x180021f66  mov     rcx, [rbp+ppMFType]
0x180021f6a  mov     rax, [rcx]
0x180021f6d  mov     r8d, [rbx+1ECh]
0x180021f74  lea     rdx, MF_MT_AUDIO_FLAC_MAX_BLOCK_SIZE
0x180021f7b  mov     rax, [rax+0A8h]
0x180021f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f87  mov     ecx, eax
0x180021f89  mov     [rbp+arg_0], eax
0x180021f8c  test    eax, eax
0x180021f8e  jns     short loc_180021FA8
0x180021f90  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021f95  cmp     al, r12b
0x180021f98  jb      loc_1800220B6
0x180021f9e  mov     edx, 110h
0x180021fa3  jmp     loc_180021D01
0x180021fa8  mov     rcx, [rbp+ppMFType]
0x180021fac  mov     rax, [rcx]
0x180021faf  mov     r8d, [rbx+200h]
0x180021fb6  shr     r8d, 3
0x180021fba  imul    r8d, [rbx+1FCh]
0x180021fc2  lea     rdx, MF_MT_AUDIO_BLOCK_ALIGNMENT
0x180021fc9  mov     rax, [rax+0A8h]
0x180021fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fd5  mov     ecx, eax
0x180021fd7  mov     [rbp+arg_0], eax
0x180021fda  test    eax, eax
0x180021fdc  jns     short loc_180021FF6
0x180021fde  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180021fe3  cmp     al, r12b
0x180021fe6  jb      loc_1800220B6
0x180021fec  mov     edx, 111h
0x180021ff1  jmp     loc_180021D01
0x180021ff6  mov     ecx, [rbx+1F8h]
0x180021ffc  xor     edx, edx
0x180021ffe  mov     rax, [rbx+208h]
0x180022005  div     rcx
0x180022008  mov     rdi, rax
0x18002200b  mov     esi, eax
0x18002200d  imul    rcx, rsi, 989680h
0x180022014  mov     [rbx+168h], rcx
0x18002201b  mov     [rbp+var_20], 0
0x180022023  mov     rcx, [rbx+138h]
0x18002202a  test    rcx, rcx
0x18002202d  jz      short loc_180022065
0x18002202f  mov     rdx, [rcx]
0x180022032  mov     rax, [rdx+20h]
0x180022036  lea     rdx, [rbp+var_20]
0x18002203a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002203f  test    eax, eax
0x180022041  js      short loc_180022065
0x180022043  mov     rax, [rbp+var_20]
0x180022047  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002204b  jz      short loc_180022065
0x18002204d  test    edi, edi
0x18002204f  jz      short loc_180022065
0x180022051  mov     ecx, [rbx+188h]
0x180022057  sub     rax, rcx
0x18002205a  xor     edx, edx
0x18002205c  div     rsi
0x18002205f  mov     [rbx+130h], eax
0x180022065  mov     rcx, [rbp+ppMFType]
0x180022069  mov     rax, [rcx]
0x18002206c  mov     r8d, [rbx+130h]
0x180022073  lea     rdx, MF_MT_AUDIO_AVG_BYTES_PER_SECOND
0x18002207a  mov     rax, [rax+0A8h]
0x180022081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022086  mov     ecx, eax
0x180022088  mov     [rbp+arg_0], eax
0x18002208b  test    eax, eax
0x18002208d  jns     short loc_1800220A3
0x18002208f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180022094  cmp     al, r12b
0x180022097  jb      short loc_1800220B6
0x180022099  mov     edx, 112h
0x18002209e  jmp     loc_180021D01
0x1800220a3  mov     rcx, [rbp+ppMFType]
0x1800220a7  mov     [r14], rcx
0x1800220aa  mov     rax, [rcx]
0x1800220ad  mov     rax, [rax+8]
0x1800220b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220b6  mov     rcx, [rbp+ppMFType]
0x1800220ba  test    rcx, rcx
0x1800220bd  jz      short loc_1800220D3
0x1800220bf  mov     rax, [rcx]
0x1800220c2  mov     rax, [rax+10h]
0x1800220c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220cb  mov     [rbp+ppMFType], 0
0x1800220d3  mov     ebx, [rbp+arg_0]
0x1800220d6  lea     rcx, [rbp+var_30]
0x1800220da  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x1800220df  nop
0x1800220e0  mov     eax, ebx
0x1800220e2  mov     rbx, [rsp+60h+arg_8]
0x1800220ea  add     rsp, 60h
0x1800220ee  pop     r14
0x1800220f0  pop     r12
0x1800220f2  pop     rdi
0x1800220f3  pop     rsi
0x1800220f4  pop     rbp
0x1800220f5  retn
```
