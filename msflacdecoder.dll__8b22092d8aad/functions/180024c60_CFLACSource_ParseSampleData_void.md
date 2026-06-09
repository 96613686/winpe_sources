# CFLACSource::ParseSampleData(void)

- ea: `0x180024c60`
- end: `0x180025136`
- name: `?ParseSampleData@CFLACSource@@AEAAJXZ`
- size: `1238`
- prototype: `__int64 __fastcall(CFLACSource *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002471c`
- `0x180024a08`

## callees

- `0x180016e48`
- `0x18001c638`
- `0x180020398`
- `0x180020484`
- `0x1800230b8`
- `0x180024c60`
- `0x1800264ac`
- `0x180027dcc`
- `0x180028490`
- `0x180028d6c`
- `0x180056010`

## import_xrefs

- `MFPlat!MFCreateMemoryBuffer` at `0x180024d79`
- `MFPlat!MFCreateMemoryBuffer` at `0x180024d79`
- `MFPlat!MFllMulDiv` at `0x180024d1f`
- `MFPlat!MFllMulDiv` at `0x180024d1f`
- `MFPlat!MFCreateSample` at `0x180024e15`
- `MFPlat!MFCreateSample` at `0x180024e15`

## pseudocode

```c
__int64 __fastcall CFLACSource::ParseSampleData(CFLACSource *this)
{
  __int64 v2; // rax
  __int64 v3; // r15
  DWORD v4; // esi
  unsigned int v5; // eax
  DWORD v6; // r14d
  int v7; // ecx
  __int64 v8; // rdx
  int v9; // r8d
  int v10; // ecx
  int v11; // ecx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rcx
  IMFMediaBuffer *ppBuffer; // [rsp+30h] [rbp-40h] BYREF
  IMFSample *ppIMFSample; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+40h] [rbp-30h] BYREF
  void *Destination; // [rsp+48h] [rbp-28h] BYREF
  __int64 v20; // [rsp+50h] [rbp-20h]
  CFLACSource *v21; // [rsp+58h] [rbp-18h]
  HRESULT *v22; // [rsp+60h] [rbp-10h]
  HRESULT v23; // [rsp+B8h] [rbp+48h] BYREF
  int v24; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v25; // [rsp+C8h] [rbp+58h] BYREF

  v23 = 0;
  v21 = this;
  v22 = &v23;
  ppBuffer = 0;
  ppIMFSample = 0;
  Destination = 0;
  v24 = 0;
  v2 = *((_QWORD *)this + 22);
  if ( !v2 || !*(_DWORD *)(v2 + 52) )
  {
    v23 = -1072875854;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      return (unsigned int)v23;
    v12 = 213;
    goto LABEL_62;
  }
  while ( 1 )
  {
    if ( *((_DWORD *)this + 56) != 1
      && (*((_DWORD *)this + 56) == 5 || !(unsigned int)CFLACStream::NeedsData(*((CFLACStream **)this + 22))) )
    {
      goto LABEL_63;
    }
    v3 = *((unsigned int *)this + 86);
    v4 = *((_DWORD *)this + 87) - v3;
    if ( !v4 )
      break;
    v20 = *((_QWORD *)this + 41);
    v5 = *((_DWORD *)this + 76);
    if ( v5 )
      *((_QWORD *)this + 44) += MFllMulDiv(v4, 10000000, v5, 0);
    v25 = 0;
    v6 = *((_DWORD *)this + 72);
    if ( v6 >= v4 )
      v6 = v4;
    v18 = 0;
    v23 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 39) + 48LL))(*((_QWORD *)this + 39), &v18);
    if ( v23 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v10);
      goto LABEL_53;
    }
    v18 -= v4;
    v23 = MFCreateMemoryBuffer(v6, &ppBuffer);
    if ( v23 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = 216;
LABEL_31:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v7);
      }
LABEL_53:
      ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v25);
      goto LABEL_63;
    }
    v23 = ((__int64 (__fastcall *)(IMFMediaBuffer *, void **, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
            ppBuffer,
            &Destination,
            0,
            0);
    if ( v23 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = 217;
        goto LABEL_31;
      }
      goto LABEL_53;
    }
    if ( memcpy_s(Destination, v6, (const void *const)(v20 + v3), v6) )
    {
      v23 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = 218;
        goto LABEL_31;
      }
      goto LABEL_53;
    }
    v23 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
    if ( v23 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = 219;
        goto LABEL_31;
      }
      goto LABEL_53;
    }
    v23 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer, v6);
    if ( v23 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = 220;
        goto LABEL_31;
      }
      goto LABEL_53;
    }
    v23 = MFCreateSample(&ppIMFSample);
    if ( v23 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = 221;
        goto LABEL_31;
      }
      goto LABEL_53;
    }
    v23 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample, ppBuffer);
    if ( v23 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = 222;
        goto LABEL_31;
      }
      goto LABEL_53;
    }
    if ( *((_DWORD *)this + 71) )
    {
      v23 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
              ppIMFSample,
              &MFSampleExtension_Discontinuity,
              1);
      if ( v23 < 0 )
      {
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v8 = 223;
          goto LABEL_31;
        }
        goto LABEL_53;
      }
      v23 = ((__int64 (__fastcall *)(IMFSample *, _QWORD))ppIMFSample->lpVtbl->SetSampleTime)(
              ppIMFSample,
              *((_QWORD *)this + 46));
      if ( v23 < 0 )
      {
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v8 = 224;
          goto LABEL_31;
        }
        goto LABEL_53;
      }
      *((_DWORD *)this + 71) = 0;
    }
    v23 = CFLACStream::DeliverPayload(*((CFLACStream **)this + 22), ppIMFSample);
    if ( v23 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 225, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v9);
      goto LABEL_53;
    }
    CBuffReader::MoveStart((CFLACSource *)((char *)this + 328), v6);
    if ( ppBuffer )
    {
      ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Release)(ppBuffer);
      ppBuffer = 0;
    }
    if ( ppIMFSample )
    {
      ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
      ppIMFSample = 0;
    }
    ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v25);
  }
  (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 39) + 64LL))(*((_QWORD *)this + 39), &v24);
  if ( v24 )
  {
    v23 = CFLACSource::EndOfStream(this);
    goto LABEL_63;
  }
  v23 = CFLACSource::RequestData(this);
  if ( v23 >= 0 )
  {
    v13 = 1;
    goto LABEL_64;
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v12 = 214;
LABEL_62:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v11);
  }
LABEL_63:
  v13 = 0;
LABEL_64:
  if ( v23 >= 0 && !(_DWORD)v13 )
  {
    v14 = *((_QWORD *)this + 33);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      *((_QWORD *)this + 33) = 0;
    }
  }
  if ( ppBuffer )
  {
    ((void (__fastcall *)(IMFMediaBuffer *, __int64))ppBuffer->lpVtbl->Release)(ppBuffer, v13);
    ppBuffer = 0;
  }
  if ( ppIMFSample )
    ((void (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->Release)(ppIMFSample, v13);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x180024c60  push    rbp
0x180024c62  push    rbx
0x180024c63  push    rsi
0x180024c64  push    r12
0x180024c66  push    r13
0x180024c68  push    r14
0x180024c6a  push    r15
0x180024c6c  mov     rbp, rsp
0x180024c6f  sub     rsp, 70h
0x180024c73  mov     rbx, rcx
0x180024c76  xor     r12d, r12d
0x180024c79  mov     [rbp+arg_8], r12d
0x180024c7d  mov     [rbp+var_18], rcx
0x180024c81  lea     rax, [rbp+arg_8]
0x180024c85  mov     [rbp+var_10], rax
0x180024c89  mov     [rbp+ppBuffer], r12
0x180024c8d  mov     [rbp+ppIMFSample], r12
0x180024c91  mov     [rbp+Destination], r12
0x180024c95  mov     [rbp+arg_0], r12d
0x180024c99  mov     [rbp+arg_10], r12d
0x180024c9d  mov     rax, [rcx+0B0h]
0x180024ca4  test    rax, rax
0x180024ca7  jz      loc_180025094
0x180024cad  cmp     [rax+34h], r12d
0x180024cb1  jz      loc_180025094
0x180024cb7  mov     ecx, [rbx+0E0h]
0x180024cbd  sub     ecx, 1
0x180024cc0  jz      short loc_180024CDF
0x180024cc2  cmp     ecx, 4
0x180024cc5  jz      loc_1800250C8
0x180024ccb  mov     rcx, [rbx+0B0h]; this
0x180024cd2  call    ?NeedsData@CFLACStream@@QEAAHXZ; CFLACStream::NeedsData(void)
0x180024cd7  test    eax, eax
0x180024cd9  jz      loc_1800250C8
0x180024cdf  mov     r15d, [rbx+158h]
0x180024ce6  mov     esi, [rbx+15Ch]
0x180024cec  sub     esi, r15d
0x180024cef  jz      loc_180025045
0x180024cf5  lea     r13, [rbx+148h]
0x180024cfc  mov     rax, [r13+0]
0x180024d00  mov     [rbp+var_20], rax
0x180024d04  mov     eax, [rbx+130h]
0x180024d0a  mov     r12d, esi
0x180024d0d  test    eax, eax
0x180024d0f  jz      short loc_180024D2C
0x180024d11  mov     r8d, eax; c
0x180024d14  xor     r9d, r9d; d
0x180024d17  mov     edx, 989680h; b
0x180024d1c  mov     ecx, r12d; a
0x180024d1f  call    cs:__imp_MFllMulDiv
0x180024d25  add     [rbx+160h], rax
0x180024d2c  mov     [rbp+arg_18], 0
0x180024d34  mov     r14d, [rbx+120h]
0x180024d3b  cmp     r14d, esi
0x180024d3e  cmovnb  r14d, esi
0x180024d42  mov     [rbp+var_30], 0
0x180024d4a  mov     rcx, [rbx+138h]
0x180024d51  mov     rax, [rcx]
0x180024d54  lea     rdx, [rbp+var_30]
0x180024d58  mov     rax, [rax+30h]
0x180024d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d61  mov     ecx, eax
0x180024d63  mov     [rbp+arg_8], eax
0x180024d66  test    eax, eax
0x180024d68  js      loc_180025007
0x180024d6e  sub     [rbp+var_30], r12
0x180024d72  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x180024d76  mov     ecx, r14d; cbMaxLength
0x180024d79  call    cs:__imp_MFCreateMemoryBuffer
0x180024d7f  mov     ecx, eax
0x180024d81  mov     [rbp+arg_8], eax
0x180024d84  xor     r12d, r12d
0x180024d87  test    eax, eax
0x180024d89  js      loc_180024FF0
0x180024d8f  mov     rcx, [rbp+ppBuffer]
0x180024d93  mov     rax, [rcx]
0x180024d96  xor     r9d, r9d
0x180024d99  xor     r8d, r8d
0x180024d9c  lea     rdx, [rbp+Destination]
0x180024da0  mov     rax, [rax+18h]
0x180024da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024da9  mov     ecx, eax
0x180024dab  mov     [rbp+arg_8], eax
0x180024dae  test    eax, eax
0x180024db0  js      loc_180024FD9
0x180024db6  mov     edx, r14d; DestinationSize
0x180024db9  mov     r8, r15
0x180024dbc  add     r8, [rbp+var_20]; Source
0x180024dc0  mov     r9d, r14d; SourceSize
0x180024dc3  mov     rcx, [rbp+Destination]; Destination
0x180024dc7  call    memcpy_s
0x180024dcc  test    eax, eax
0x180024dce  jnz     loc_180024FBA
0x180024dd4  mov     rcx, [rbp+ppBuffer]
0x180024dd8  mov     rax, [rcx]
0x180024ddb  mov     rax, [rax+20h]
0x180024ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024de4  mov     ecx, eax
0x180024de6  mov     [rbp+arg_8], eax
0x180024de9  test    eax, eax
0x180024deb  js      loc_180024FA7
0x180024df1  mov     rcx, [rbp+ppBuffer]
0x180024df5  mov     rax, [rcx]
0x180024df8  mov     edx, r14d
0x180024dfb  mov     rax, [rax+30h]
0x180024dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e04  mov     ecx, eax
0x180024e06  mov     [rbp+arg_8], eax
0x180024e09  test    eax, eax
0x180024e0b  js      loc_180024F94
0x180024e11  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x180024e15  call    cs:__imp_MFCreateSample
0x180024e1b  mov     ecx, eax
0x180024e1d  mov     [rbp+arg_8], eax
0x180024e20  test    eax, eax
0x180024e22  js      loc_180024F84
0x180024e28  mov     rcx, [rbp+ppIMFSample]
0x180024e2c  mov     rax, [rcx]
0x180024e2f  mov     rdx, [rbp+ppBuffer]
0x180024e33  mov     rax, [rax+150h]
0x180024e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e3f  mov     ecx, eax
0x180024e41  mov     [rbp+arg_8], eax
0x180024e44  test    eax, eax
0x180024e46  js      loc_180024F74
0x180024e4c  cmp     [rbx+11Ch], r12d
0x180024e53  jz      short loc_180024EAB
0x180024e55  mov     rcx, [rbp+ppIMFSample]
0x180024e59  mov     rax, [rcx]
0x180024e5c  lea     r8d, [r12+1]
0x180024e61  lea     rdx, MFSampleExtension_Discontinuity
0x180024e68  mov     rax, [rax+0A8h]
0x180024e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e74  mov     ecx, eax
0x180024e76  mov     [rbp+arg_8], eax
0x180024e79  test    eax, eax
0x180024e7b  js      loc_180024F4F
0x180024e81  mov     rcx, [rbp+ppIMFSample]
0x180024e85  mov     rax, [rcx]
0x180024e88  mov     rdx, [rbx+170h]
0x180024e8f  mov     rax, [rax+120h]
0x180024e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e9b  mov     ecx, eax
0x180024e9d  mov     [rbp+arg_8], eax
0x180024ea0  test    eax, eax
0x180024ea2  js      short loc_180024F14
0x180024ea4  mov     [rbx+11Ch], r12d
0x180024eab  mov     rdx, [rbp+ppIMFSample]; struct IMFSample *
0x180024eaf  mov     rcx, [rbx+0B0h]; this
0x180024eb6  call    ?DeliverPayload@CFLACStream@@QEAAJPEAUIMFSample@@@Z; CFLACStream::DeliverPayload(IMFSample *)
0x180024ebb  mov     r8d, eax
0x180024ebe  mov     [rbp+arg_8], eax
0x180024ec1  test    eax, eax
0x180024ec3  js      loc_180024F5F
0x180024ec9  mov     edx, r14d; unsigned int
0x180024ecc  mov     rcx, r13; this
0x180024ecf  call    ?MoveStart@CBuffReader@@QEAAJK@Z; CBuffReader::MoveStart(ulong)
0x180024ed4  mov     rcx, [rbp+ppBuffer]
0x180024ed8  test    rcx, rcx
0x180024edb  jz      short loc_180024EED
0x180024edd  mov     rax, [rcx]
0x180024ee0  mov     rax, [rax+10h]
0x180024ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ee9  mov     [rbp+ppBuffer], r12
0x180024eed  mov     rcx, [rbp+ppIMFSample]
0x180024ef1  test    rcx, rcx
0x180024ef4  jz      short loc_180024F06
0x180024ef6  mov     rax, [rcx]
0x180024ef9  mov     rax, [rax+10h]
0x180024efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f02  mov     [rbp+ppIMFSample], r12
0x180024f06  lea     rcx, [rbp+arg_18]
0x180024f0a  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x180024f0f  jmp     loc_180024CB7
0x180024f14  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024f19  cmp     al, 1
0x180024f1b  jb      short loc_180024F41
0x180024f1d  mov     edx, 0E0h
0x180024f22  mov     [rsp+70h+var_50], ecx
0x180024f26  mov     r9, rbx
0x180024f29  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x180024f30  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f37  mov     rcx, [rcx+10h]
0x180024f3b  call    WPP_SF_qd
0x180024f40  nop
0x180024f41  lea     rcx, [rbp+arg_18]
0x180024f45  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x180024f4a  jmp     loc_1800250C8
0x180024f4f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024f54  cmp     al, 1
0x180024f56  jb      short loc_180024F41
0x180024f58  mov     edx, 0DFh
0x180024f5d  jmp     short loc_180024F22
0x180024f5f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024f64  cmp     al, 1
0x180024f66  jb      short loc_180024F41
0x180024f68  mov     edx, 0E1h
0x180024f6d  mov     [rsp+70h+var_50], r8d
0x180024f72  jmp     short loc_180024F26
0x180024f74  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024f79  cmp     al, 1
0x180024f7b  jb      short loc_180024F41
0x180024f7d  mov     edx, 0DEh
0x180024f82  jmp     short loc_180024F22
0x180024f84  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024f89  cmp     al, 1
0x180024f8b  jb      short loc_180024F41
0x180024f8d  mov     edx, 0DDh
0x180024f92  jmp     short loc_180024F22
0x180024f94  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024f99  cmp     al, 1
0x180024f9b  jb      short loc_180024F41
0x180024f9d  mov     edx, 0DCh
0x180024fa2  jmp     loc_180024F22
0x180024fa7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024fac  cmp     al, 1
0x180024fae  jb      short loc_180024F41
0x180024fb0  mov     edx, 0DBh
0x180024fb5  jmp     loc_180024F22
0x180024fba  mov     ecx, 8007000Eh
0x180024fbf  mov     [rbp+arg_8], ecx
0x180024fc2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024fc7  cmp     al, 1
0x180024fc9  jb      loc_180024F41
0x180024fcf  mov     edx, 0DAh
0x180024fd4  jmp     loc_180024F22
0x180024fd9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024fde  cmp     al, 1
0x180024fe0  jb      loc_180024F41
0x180024fe6  mov     edx, 0D9h
0x180024feb  jmp     loc_180024F22
0x180024ff0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024ff5  cmp     al, 1
0x180024ff7  jb      loc_180024F41
0x180024ffd  mov     edx, 0D8h
0x180025002  jmp     loc_180024F22
0x180025007  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002500c  cmp     al, 1
0x18002500e  jb      short loc_180025034
0x180025010  mov     edx, 0D7h
0x180025015  mov     [rsp+70h+var_50], ecx
0x180025019  mov     r9, rbx
0x18002501c  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x180025023  mov     rcx, cs:WPP_GLOBAL_Control
0x18002502a  mov     rcx, [rcx+10h]
0x18002502e  call    WPP_SF_qd
0x180025033  nop
0x180025034  lea     rcx, [rbp+arg_18]
0x180025038  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18002503d  xor     r12d, r12d
0x180025040  jmp     loc_1800250C8
0x180025045  mov     rcx, [rbx+138h]
0x18002504c  mov     rax, [rcx]
0x18002504f  lea     rdx, [rbp+arg_10]
0x180025053  mov     rax, [rax+40h]
0x180025057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002505c  mov     rcx, rbx; this
0x18002505f  cmp     [rbp+arg_10], r12d
0x180025063  jz      short loc_18002506F
0x180025065  call    ?EndOfStream@CFLACSource@@AEAAJXZ; CFLACSource::EndOfStream(void)
0x18002506a  mov     [rbp+arg_8], eax
0x18002506d  jmp     short loc_1800250C8
0x18002506f  call    ?RequestData@CFLACSource@@AEAAJXZ; CFLACSource::RequestData(void)
0x180025074  mov     ecx, eax
0x180025076  mov     [rbp+arg_8], eax
0x180025079  test    eax, eax
0x18002507b  jns     short loc_18002508D
0x18002507d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180025082  cmp     al, 1
0x180025084  jb      short loc_1800250C8
0x180025086  mov     edx, 0D6h
0x18002508b  jmp     short loc_1800250AA
0x18002508d  mov     edx, 1
0x180025092  jmp     short loc_1800250CB
0x180025094  mov     ecx, 0C00D36B2h
0x180025099  mov     [rbp+arg_8], ecx
0x18002509c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800250a1  cmp     al, 1
0x1800250a3  jb      short loc_180025123
0x1800250a5  mov     edx, 0D5h
0x1800250aa  mov     [rsp+70h+var_50], ecx
0x1800250ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800250b5  mov     r9, rbx
0x1800250b8  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x1800250bf  mov     rcx, [rcx+10h]
0x1800250c3  call    WPP_SF_qd
0x1800250c8  mov     edx, [rbp+arg_0]
0x1800250cb  cmp     [rbp+arg_8], r12d
0x1800250cf  jl      short loc_1800250F4
0x1800250d1  test    edx, edx
0x1800250d3  jnz     short loc_1800250F4
0x1800250d5  mov     rcx, [rbx+108h]
0x1800250dc  test    rcx, rcx
0x1800250df  jz      short loc_1800250F4
0x1800250e1  mov     rax, [rcx]
0x1800250e4  mov     rax, [rax+10h]
0x1800250e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250ed  mov     [rbx+108h], r12
0x1800250f4  mov     rcx, [rbp+ppBuffer]
0x1800250f8  test    rcx, rcx
  ... truncated ...
```
