# CFLACDecMFT::ConfigOutputTypes(void)

- ea: `0x18001ced8`
- end: `0x18001d264`
- name: `?ConfigOutputTypes@CFLACDecMFT@@AEAAJXZ`
- size: `908`
- prototype: `__int64 __fastcall(CFLACDecMFT *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e370`

## callees

- `0x180016e48`
- `0x18001ced8`
- `0x18001efc4`
- `0x18001f620`
- `0x180056010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18001cf40`
- `MFPlat!MFCreateMediaType` at `0x18001cf40`

## string_xrefs

- `0x18001cef7`: `ConfigOutputTypes`
- `0x18001cf09`: `CFLACDecMFT::ConfigOutputTypes`
- `0x18001d1fe`: `CFLACDecMFT::ConfigOutputTypes`
- `0x18001d245`: `CFLACDecMFT::ConfigOutputTypes`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFLACDecMFT::ConfigOutputTypes(CFLACDecMFT *this)
{
  TraceLoggingHelperBase *v2; // r14
  HRESULT inited; // ebx
  IMFMediaType *v4; // rsi
  __int64 v5; // rcx
  _DWORD v7[12]; // [rsp+40h] [rbp-30h]
  IMFMediaType *ppMFType; // [rsp+90h] [rbp+20h] BYREF

  v2 = (CFLACDecMFT *)((char *)this + 960);
  TraceLoggingHelperBase::TraceVA(
    (CFLACDecMFT *)((char *)this + 960),
    4u,
    "CFLACDecMFT::ConfigOutputTypes",
    0x437u,
    "ConfigOutputTypes");
  ppMFType = 0;
  inited = CMFTSimpleBase::_InitAvailableOutputTypeArray(this, 1u);
  if ( inited >= 0 )
  {
    inited = MFCreateMediaType(&ppMFType);
    if ( inited >= 0 )
    {
      inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                 ppMFType,
                 &MF_MT_MAJOR_TYPE,
                 &MFMediaType_Audio);
      if ( inited >= 0 )
      {
        inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                   ppMFType,
                   &MF_MT_SUBTYPE,
                   &MFAudioFormat_PCM);
        if ( inited >= 0 )
        {
          if ( !*((_DWORD *)this + 73) || !*((_DWORD *)this + 72) || !*((_DWORD *)this + 74) )
          {
            TraceLoggingHelperBase::TraceVA(
              v2,
              2u,
              "CFLACDecMFT::ConfigOutputTypes",
              0x448u,
              "MF_E_INVALIDMEDIATYPE - Input sampling rate or channels or bits per sample not set");
            inited = -1072875852;
            goto LABEL_22;
          }
          if ( !*((_QWORD *)this + 5) )
            goto LABEL_27;
          inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->SetUINT32)(
                     ppMFType,
                     &MF_MT_AUDIO_SAMPLES_PER_SECOND);
          if ( inited >= 0 )
          {
            inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                       ppMFType,
                       &MF_MT_AUDIO_NUM_CHANNELS,
                       *((unsigned int *)this + 72));
            if ( inited >= 0 )
            {
              inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                         ppMFType,
                         &MF_MT_AUDIO_BITS_PER_SAMPLE,
                         *((unsigned int *)this + 74));
              if ( inited >= 0 )
              {
                inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                           ppMFType,
                           &MF_MT_AUDIO_VALID_BITS_PER_SAMPLE,
                           *((unsigned int *)this + 74));
                if ( inited >= 0 )
                {
                  v7[0] = -1;
                  v7[1] = 4;
                  v7[2] = 3;
                  v7[3] = 7;
                  v7[4] = 51;
                  v7[5] = 55;
                  v7[6] = 63;
                  v7[7] = 1807;
                  v7[8] = 1599;
                  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                             ppMFType,
                             &MF_MT_AUDIO_CHANNEL_MASK,
                             (unsigned int)v7[*((unsigned int *)this + 72)]);
                  if ( inited >= 0 )
                  {
                    inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                               ppMFType,
                               &MF_MT_AUDIO_AVG_BYTES_PER_SECOND,
                               (unsigned int)(*((_DWORD *)this + 72)
                                            * *((_DWORD *)this + 73)
                                            * (*((_DWORD *)this + 74) >> 3)));
                    if ( inited >= 0 )
                    {
                      inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                                 ppMFType,
                                 &MF_MT_AUDIO_BLOCK_ALIGNMENT,
                                 (unsigned int)(*((_DWORD *)this + 72) * (*((_DWORD *)this + 74) >> 3)));
                      if ( inited >= 0 )
                      {
                        inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
                                   ppMFType,
                                   &MF_MT_ALL_SAMPLES_INDEPENDENT,
                                   1);
                        if ( inited >= 0 )
                        {
LABEL_27:
                          if ( *((_DWORD *)this + 6) )
                          {
                            v4 = ppMFType;
                            v5 = **((_QWORD **)this + 4);
                            if ( v5 )
                            {
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
                              **((_QWORD **)this + 4) = 0;
                            }
                            **((_QWORD **)this + 4) = v4;
                            (*(void (__fastcall **)(_QWORD))(***((_QWORD ***)this + 4) + 8LL))(**((_QWORD **)this + 4));
                            *(_DWORD *)(*((_QWORD *)this + 4) + 8LL) = 1;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( inited )
LABEL_22:
    TraceLoggingHelperBase::TraceVA(
      v2,
      2u,
      "CFLACDecMFT::ConfigOutputTypes",
      0x466u,
      "Error %08X returned: File: %s, Line: %d",
      inited,
      "avcore\\codecdsp\\audio\\flac\\flacdec\\mft\\flacdecmft.cpp",
      1126);
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&ppMFType);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001ced8  mov     [rsp-18h+arg_8], rbx
0x18001cedd  mov     [rsp-18h+arg_10], rsi
0x18001cee2  push    rbp
0x18001cee3  push    rdi
0x18001cee4  push    r14
0x18001cee6  mov     rbp, rsp
0x18001cee9  sub     rsp, 70h
0x18001ceed  mov     rdi, rcx
0x18001cef0  lea     r14, [rcx+3C0h]
0x18001cef7  lea     rax, aConfigoutputty; "ConfigOutputTypes"
0x18001cefe  mov     [rsp+70h+Format], rax; Format
0x18001cf03  mov     r9d, 437h; unsigned int
0x18001cf09  lea     r8, aCflacdecmftCon; "CFLACDecMFT::ConfigOutputTypes"
0x18001cf10  mov     esi, 4
0x18001cf15  mov     edx, esi; unsigned __int8
0x18001cf17  mov     rcx, r14; this
0x18001cf1a  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001cf1f  mov     [rbp+ppMFType], 0
0x18001cf27  lea     edx, [rsi-3]; unsigned int
0x18001cf2a  mov     rcx, rdi; this
0x18001cf2d  call    ?_InitAvailableOutputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableOutputTypeArray(ulong)
0x18001cf32  mov     ebx, eax
0x18001cf34  test    eax, eax
0x18001cf36  js      loc_18001D1D3
0x18001cf3c  lea     rcx, [rbp+ppMFType]; ppMFType
0x18001cf40  call    cs:__imp_MFCreateMediaType
0x18001cf46  mov     ebx, eax
0x18001cf48  test    eax, eax
0x18001cf4a  js      loc_18001D1D3
0x18001cf50  mov     rcx, [rbp+ppMFType]
0x18001cf54  mov     rax, [rcx]
0x18001cf57  lea     r8, MFMediaType_Audio
0x18001cf5e  lea     rdx, MF_MT_MAJOR_TYPE
0x18001cf65  mov     rax, [rax+0C0h]
0x18001cf6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf71  mov     ebx, eax
0x18001cf73  test    eax, eax
0x18001cf75  js      loc_18001D1D3
0x18001cf7b  mov     rcx, [rbp+ppMFType]
0x18001cf7f  mov     rax, [rcx]
0x18001cf82  lea     r8, MFAudioFormat_PCM
0x18001cf89  lea     rdx, MF_MT_SUBTYPE
0x18001cf90  mov     rax, [rax+0C0h]
0x18001cf97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf9c  mov     ebx, eax
0x18001cf9e  test    eax, eax
0x18001cfa0  js      loc_18001D1D3
0x18001cfa6  mov     r8d, [rdi+124h]
0x18001cfad  test    r8d, r8d
0x18001cfb0  jz      loc_18001D233
0x18001cfb6  cmp     dword ptr [rdi+120h], 0
0x18001cfbd  jz      loc_18001D233
0x18001cfc3  cmp     dword ptr [rdi+128h], 0
0x18001cfca  jz      loc_18001D233
0x18001cfd0  cmp     qword ptr [rdi+28h], 0
0x18001cfd5  jz      loc_18001D181
0x18001cfdb  mov     rcx, [rbp+ppMFType]
0x18001cfdf  mov     rax, [rcx]
0x18001cfe2  lea     rdx, MF_MT_AUDIO_SAMPLES_PER_SECOND
0x18001cfe9  mov     rax, [rax+0A8h]
0x18001cff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cff5  mov     ebx, eax
0x18001cff7  test    eax, eax
0x18001cff9  js      loc_18001D1D3
0x18001cfff  mov     rcx, [rbp+ppMFType]
0x18001d003  mov     rax, [rcx]
0x18001d006  mov     r8d, [rdi+120h]
0x18001d00d  lea     rdx, MF_MT_AUDIO_NUM_CHANNELS
0x18001d014  mov     rax, [rax+0A8h]
0x18001d01b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d020  mov     ebx, eax
0x18001d022  test    eax, eax
0x18001d024  js      loc_18001D1D3
0x18001d02a  mov     rcx, [rbp+ppMFType]
0x18001d02e  mov     rax, [rcx]
0x18001d031  mov     r8d, [rdi+128h]
0x18001d038  lea     rdx, MF_MT_AUDIO_BITS_PER_SAMPLE
0x18001d03f  mov     rax, [rax+0A8h]
0x18001d046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d04b  mov     ebx, eax
0x18001d04d  test    eax, eax
0x18001d04f  js      loc_18001D1D3
0x18001d055  mov     rcx, [rbp+ppMFType]
0x18001d059  mov     rax, [rcx]
0x18001d05c  mov     r8d, [rdi+128h]
0x18001d063  lea     rdx, MF_MT_AUDIO_VALID_BITS_PER_SAMPLE
0x18001d06a  mov     rax, [rax+0A8h]
0x18001d071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d076  mov     ebx, eax
0x18001d078  test    eax, eax
0x18001d07a  js      loc_18001D1D3
0x18001d080  mov     [rbp+var_30], 0FFFFFFFFh
0x18001d087  mov     [rbp+var_2C], esi
0x18001d08a  mov     [rbp+var_28], 3
0x18001d091  mov     [rbp+var_24], 7
0x18001d098  mov     [rbp+var_20], 33h ; '3'
0x18001d09f  mov     [rbp+var_1C], 37h ; '7'
0x18001d0a6  mov     [rbp+var_18], 3Fh ; '?'
0x18001d0ad  mov     [rbp+var_14], 70Fh
0x18001d0b4  mov     [rbp+var_10], 63Fh
0x18001d0bb  mov     rcx, [rbp+ppMFType]
0x18001d0bf  mov     rax, [rcx]
0x18001d0c2  mov     r8d, [rdi+120h]
0x18001d0c9  mov     r8d, [rbp+r8*4+var_30]
0x18001d0ce  lea     rdx, MF_MT_AUDIO_CHANNEL_MASK
0x18001d0d5  mov     rax, [rax+0A8h]
0x18001d0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0e1  mov     ebx, eax
0x18001d0e3  test    eax, eax
0x18001d0e5  js      loc_18001D1D3
0x18001d0eb  mov     rcx, [rbp+ppMFType]
0x18001d0ef  mov     rax, [rcx]
0x18001d0f2  mov     r8d, [rdi+128h]
0x18001d0f9  shr     r8d, 3
0x18001d0fd  imul    r8d, [rdi+124h]
0x18001d105  imul    r8d, [rdi+120h]
0x18001d10d  lea     rdx, MF_MT_AUDIO_AVG_BYTES_PER_SECOND
0x18001d114  mov     rax, [rax+0A8h]
0x18001d11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d120  mov     ebx, eax
0x18001d122  test    eax, eax
0x18001d124  js      loc_18001D1D3
0x18001d12a  mov     rcx, [rbp+ppMFType]
0x18001d12e  mov     rax, [rcx]
0x18001d131  mov     r8d, [rdi+128h]
0x18001d138  shr     r8d, 3
0x18001d13c  imul    r8d, [rdi+120h]
0x18001d144  lea     rdx, MF_MT_AUDIO_BLOCK_ALIGNMENT
0x18001d14b  mov     rax, [rax+0A8h]
0x18001d152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d157  mov     ebx, eax
0x18001d159  test    eax, eax
0x18001d15b  js      short loc_18001D1D3
0x18001d15d  mov     rcx, [rbp+ppMFType]
0x18001d161  mov     rax, [rcx]
0x18001d164  lea     r8d, [rsi-3]
0x18001d168  lea     rdx, MF_MT_ALL_SAMPLES_INDEPENDENT
0x18001d16f  mov     rax, [rax+0A8h]
0x18001d176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d17b  mov     ebx, eax
0x18001d17d  test    eax, eax
0x18001d17f  js      short loc_18001D1D3
0x18001d181  cmp     dword ptr [rdi+18h], 0
0x18001d185  jbe     short loc_18001D1D3
0x18001d187  mov     rsi, [rbp+ppMFType]
0x18001d18b  mov     rax, [rdi+20h]
0x18001d18f  mov     rcx, [rax]
0x18001d192  test    rcx, rcx
0x18001d195  jz      short loc_18001D1AE
0x18001d197  mov     rax, [rcx]
0x18001d19a  mov     rax, [rax+10h]
0x18001d19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1a3  mov     rax, [rdi+20h]
0x18001d1a7  mov     qword ptr [rax], 0
0x18001d1ae  mov     rax, [rdi+20h]
0x18001d1b2  mov     [rax], rsi
0x18001d1b5  mov     rax, [rdi+20h]
0x18001d1b9  mov     rcx, [rax]
0x18001d1bc  mov     rax, [rcx]
0x18001d1bf  mov     rax, [rax+8]
0x18001d1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1c8  mov     rax, [rdi+20h]
0x18001d1cc  mov     dword ptr [rax+8], 1
0x18001d1d3  test    ebx, ebx
0x18001d1d5  jz      short loc_18001D213
0x18001d1d7  mov     r9d, 466h; unsigned int
0x18001d1dd  mov     [rsp+70h+var_38], r9d
0x18001d1e2  lea     rax, aAvcoreCodecdsp; "avcore\\codecdsp\\audio\\flac\\flacdec"...
0x18001d1e9  mov     [rsp+70h+var_40], rax
0x18001d1ee  mov     [rsp+70h+var_48], ebx
0x18001d1f2  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x18001d1f9  mov     [rsp+70h+Format], rax; Format
0x18001d1fe  lea     r8, aCflacdecmftCon; "CFLACDecMFT::ConfigOutputTypes"
0x18001d205  mov     edx, 2; unsigned __int8
0x18001d20a  mov     rcx, r14; this
0x18001d20d  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001d212  nop
0x18001d213  lea     rcx, [rbp+ppMFType]
0x18001d217  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18001d21c  mov     eax, ebx
0x18001d21e  lea     r11, [rsp+70h+var_s0]
0x18001d223  mov     rbx, [r11+28h]
0x18001d227  mov     rsi, [r11+30h]
0x18001d22b  mov     rsp, r11
0x18001d22e  pop     r14
0x18001d230  pop     rdi
0x18001d231  pop     rbp
0x18001d232  retn
0x18001d233  lea     rax, aMfEInvalidmedi; "MF_E_INVALIDMEDIATYPE - Input sampling "...
0x18001d23a  mov     [rsp+70h+Format], rax; Format
0x18001d23f  mov     r9d, 448h; unsigned int
0x18001d245  lea     r8, aCflacdecmftCon; "CFLACDecMFT::ConfigOutputTypes"
0x18001d24c  mov     edx, 2; unsigned __int8
0x18001d251  mov     rcx, r14; this
0x18001d254  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001d259  mov     ebx, 0C00D36B4h
0x18001d25e  jmp     loc_18001D1D7
```
