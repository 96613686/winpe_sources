# Rdp::Avenc::SinkWriter::CMFEncoder::EncodeFrame(Rdp::Avenc::IFrameBuffer1 *,uint &)

- ea: `0x18003670c`
- end: `0x180036cbc`
- name: `?EncodeFrame@CMFEncoder@SinkWriter@Avenc@Rdp@@QEAAXPEAUIFrameBuffer1@34@AEAI@Z`
- size: `1456`
- prototype: `void __fastcall(Rdp::Avenc::SinkWriter::CMFEncoder *__hidden this, struct Rdp::Avenc::IFrameBuffer1 *, unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180035720`
- `0x180035ce4`

## callees

- `0x18000154c`
- `0x180006580`
- `0x1800069a0`
- `0x180007018`
- `0x1800072b0`
- `0x1800080cc`
- `0x180008dc0`
- `0x18000e848`
- `0x18000ec04`
- `0x1800199cc`
- `0x18003670c`
- `0x180036e48`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180036ba4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180036ba4`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180036864`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x180036864`
- `MFPlat!MFCreateSample` at `0x180036958`
- `MFPlat!MFCreateSample` at `0x180036958`

## string_xrefs

- `0x180036c51`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180036c66`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180036771`: `Failed to get moves and dirties`
- `0x180036c99`: `onecoreuap\termsrv\rdp_bin\win\common/inc/GraphicsUtils.h`
- `0x18003686e`: `Failed to create media buffer`
- `0x180036962`: `Failed to create media sample`
- `0x180036a0b`: `Failed to set MFSampleExtension_FrameNumber`
- `0x180036780`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x18003687d`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x180036a68`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterframeprocessor.cpp`
- `0x180036b79`: `Failed to write sample`
- `0x180036ad1`: `Rdp::Avenc::SinkWriter::CMFEncoder::EncodeFrame`
- `0x180036bc0`: `Timeout while waiting for sample completion`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Rdp::Avenc::SinkWriter::CMFEncoder::EncodeFrame(
        Rdp::Avenc::SinkWriter::CMFEncoder *this,
        struct Rdp::Avenc::IFrameBuffer1 *a2,
        unsigned int *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int *v8; // rsi
  unsigned int v9; // r9d
  char v10; // r14
  unsigned int i; // eax
  __int64 v12; // rcx
  int v13; // r10d
  int v14; // edx
  IUnknown *v15; // rax
  unsigned int v16; // eax
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rax
  int v18; // eax
  int v19; // edx
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  IMFSample *v25; // rdi
  HRESULT (__stdcall *SetSampleTime)(IMFSample *, LONGLONG); // rbx
  __int64 v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // eax
  int v30; // r8d
  int v31; // r9d
  unsigned int v32; // eax
  DWORD v33; // eax
  const char *v34; // r9
  unsigned int v35; // eax
  int v36; // edx
  int ppBuffer; // [rsp+20h] [rbp-99h]
  int ppBuffera; // [rsp+20h] [rbp-99h]
  int ppBufferb; // [rsp+20h] [rbp-99h]
  char *v40; // [rsp+28h] [rbp-91h]
  char *v41; // [rsp+28h] [rbp-91h]
  char *v42; // [rsp+28h] [rbp-91h]
  char *v43; // [rsp+28h] [rbp-91h]
  char *v44; // [rsp+28h] [rbp-91h]
  char *v45; // [rsp+28h] [rbp-91h]
  char *v46; // [rsp+28h] [rbp-91h]
  char *v47; // [rsp+28h] [rbp-91h]
  char *v48; // [rsp+28h] [rbp-91h]
  char *v49; // [rsp+30h] [rbp-89h]
  unsigned int v50; // [rsp+50h] [rbp-69h] BYREF
  IMFSample *ppIMFSample; // [rsp+58h] [rbp-61h] BYREF
  char v52[4]; // [rsp+60h] [rbp-59h] BYREF
  IMFMediaBuffer *v53; // [rsp+68h] [rbp-51h] BYREF
  __int64 v54; // [rsp+70h] [rbp-49h] BYREF
  int v55; // [rsp+78h] [rbp-41h] BYREF
  __int64 v56; // [rsp+80h] [rbp-39h] BYREF
  const char *v57; // [rsp+88h] [rbp-31h] BYREF
  char v58[8]; // [rsp+90h] [rbp-29h] BYREF
  _QWORD v59[2]; // [rsp+98h] [rbp-21h] BYREF
  _OWORD v60[3]; // [rsp+A8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v50 = 0;
  v56 = 0;
  v6 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *, _QWORD, _QWORD, __int64 *, unsigned int *))(*(_QWORD *)a2 + 208LL))(
         a2,
         0,
         0,
         &v56,
         &v50);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x33D,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
    (const char *)v6,
    (int)"Failed to get moves and dirties",
    v40);
  v7 = 16 * v50 + 8;
  v8 = (unsigned int *)operator new[](v7);
  memset_0(v8, 0, v7);
  v59[1] = v8;
  *(_QWORD *)v8 = (*(unsigned int (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *))(*(_QWORD *)a2 + 192LL))(a2);
  v9 = 0;
  v10 = 1;
  for ( i = v50; v9 < i; ++v9 )
  {
    v12 = 16LL * v9;
    v13 = *(_DWORD *)(v12 + v56 + 8) - *(_DWORD *)(v12 + v56);
    if ( v13 )
    {
      v14 = *(_DWORD *)(v12 + v56 + 12) - *(_DWORD *)(v12 + v56 + 4);
      if ( v14 )
      {
        *(_OWORD *)&v8[4 * v8[1]++ + 2] = *(_OWORD *)(v12 + v56);
        *a3 += v13 * v14;
        i = v50;
      }
    }
  }
  if ( *a3 )
  {
    v53 = 0;
    v15 = (IUnknown *)(*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *))(*(_QWORD *)a2 + 216LL))(a2);
    v16 = MFCreateDXGISurfaceBuffer(&IID_ID3D11Texture2D, v15, 0, 1, &v53);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x364,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      (const char *)v16,
      (int)"Failed to create media buffer",
      v41);
    v17 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *))(*(_QWORD *)a2 + 216LL))(a2);
    v54 = 0;
    v18 = (**v17)(v17, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v54);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v18,
        ppBuffer);
    memset(v60, 0, 44);
    (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v54 + 80LL))(v54, v60);
    if ( LODWORD(v60[1]) == 10 )
    {
      v19 = 8;
    }
    else
    {
      if ( LODWORD(v60[1]) != 87 )
      {
        v35 = wil::verify_hresult<long>(2147942487LL);
        LODWORD(v42) = v36;
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x89,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/GraphicsUtils.h",
          (const char *)v35,
          (int)"Unsupported DXGI_FORMAT: %d",
          v42);
      }
      v19 = 4;
    }
    v20 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))v53->lpVtbl->SetCurrentLength)(
            v53,
            (unsigned int)(LODWORD(v60[0]) * DWORD1(v60[0]) * v19));
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x36E,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      (const char *)v20,
      (int)"Failed to set buffer size",
      v42);
    ppIMFSample = 0;
    v21 = MFCreateSample(&ppIMFSample);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x372,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      (const char *)v21,
      (int)"Failed to create media sample",
      v43);
    v22 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample, v53);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x374,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
        (const char *)(unsigned int)v22,
        ppBuffera);
    v23 = ((__int64 (__fastcall *)(IMFSample *, __int64 *, unsigned int *, _QWORD))ppIMFSample->lpVtbl->SetBlob)(
            ppIMFSample,
            MFSampleExtension_DirtyRects,
            v8,
            16 * v8[1] + 8);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x37E,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      (const char *)v23,
      (int)"Failed to set dirty rect info",
      v44);
    v24 = ((__int64 (__fastcall *)(IMFSample *, __int64 *, _QWORD))ppIMFSample->lpVtbl->SetUINT64)(
            ppIMFSample,
            MFSampleExtension_FrameNumber,
            *v8);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x381,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      (const char *)v24,
      (int)"Failed to set MFSampleExtension_FrameNumber",
      v45);
    v25 = ppIMFSample;
    SetSampleTime = ppIMFSample->lpVtbl->SetSampleTime;
    v27 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *))(*(_QWORD *)a2 + 200LL))(a2);
    v28 = ((__int64 (__fastcall *)(IMFSample *, __int64))SetSampleTime)(v25, v27);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x384,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      (const char *)v28,
      (int)"Failed to set sample time",
      v46);
    v29 = ((__int64 (__fastcall *)(IMFSample *, _QWORD))ppIMFSample->lpVtbl->SetSampleDuration)(
            ppIMFSample,
            *((_QWORD *)this + 17));
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x387,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
      (const char *)v29,
      (int)"Failed to set sample duration",
      v47);
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v55 = *v8;
      v57 = "EncodeFrameStart";
      *(_QWORD *)v58 = "Rdp::Avenc::SinkWriter::CMFEncoder::EncodeFrame";
      *(_DWORD *)v52 = 908;
      v59[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&word_1800AF376,
        v30,
        v31,
        (__int64)v59,
        (__int64)v52,
        (__int64)v58,
        (__int64)&v57,
        (__int64)&v55);
    }
    v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, IMFSample *))(**((_QWORD **)this + 11) + 48LL))(
            *((_QWORD *)this + 11),
            0,
            ppIMFSample);
    if ( v32 == -2147023673 )
    {
      if ( ppIMFSample )
        ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
      if ( v54 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
    else
    {
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x396,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
        (const char *)v32,
        (int)"Failed to write sample",
        v48);
      v33 = WaitForSingleObjectEx(*((HANDLE *)this + 18), 0x9C4u, 0);
      if ( v33 != 258 )
      {
        if ( v33 )
          wil::details::in1diag3::FailFast_Unexpected(
            retaddr,
            (void *)0xB0F,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v34);
        v10 = 0;
      }
      LOBYTE(ppBufferb) = v10;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x39F,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterframeprocessor.cpp",
        (const char *)0x800705B4LL,
        ppBufferb,
        (bool)"Timeout while waiting for sample completion",
        v49);
      if ( ppIMFSample )
        ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
      if ( v54 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
    if ( v53 )
      ((void (__fastcall *)(IMFMediaBuffer *))v53->lpVtbl->Release)(v53);
  }
  operator delete(v8);
}

```

## disassembly

```asm
0x18003670c  push    rbp
0x18003670e  push    rbx
0x18003670f  push    rsi
0x180036710  push    rdi
0x180036711  push    r13
0x180036713  push    r14
0x180036715  push    r15
0x180036717  lea     rbp, [rsp-27h]
0x18003671c  sub     rsp, 0E0h
0x180036723  mov     rax, cs:__security_cookie
0x18003672a  xor     rax, rsp
0x18003672d  mov     [rbp+57h+var_38], rax
0x180036731  mov     rdi, r8
0x180036734  mov     r15, rdx
0x180036737  mov     r13, rcx
0x18003673a  mov     [rbp+57h+var_C0], 0
0x180036741  mov     [rbp+57h+var_90], 0
0x180036749  mov     rax, [rdx]
0x18003674c  lea     rcx, [rbp+57h+var_C0]
0x180036750  mov     [rsp+110h+ppBuffer], rcx
0x180036755  lea     r9, [rbp+57h+var_90]
0x180036759  xor     r8d, r8d
0x18003675c  xor     edx, edx
0x18003675e  mov     rcx, r15
0x180036761  mov     rax, [rax+0D0h]
0x180036768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003676d  mov     rcx, [rbp+5Fh]; this
0x180036771  lea     rdx, aFailedToGetMov; "Failed to get moves and dirties"
0x180036778  mov     [rsp+110h+ppBuffer], rdx; int
0x18003677d  mov     r9d, eax; char *
0x180036780  lea     r8, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180036787  mov     edx, 33Dh; void *
0x18003678c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180036791  mov     eax, [rbp+57h+var_C0]
0x180036794  shl     eax, 4
0x180036797  add     eax, 8
0x18003679a  mov     ebx, eax
0x18003679c  mov     ecx, eax; unsigned __int64
0x18003679e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800367a3  mov     rsi, rax
0x1800367a6  mov     r8d, ebx; Size
0x1800367a9  xor     edx, edx; Val
0x1800367ab  mov     rcx, rax; void *
0x1800367ae  call    memset_0
0x1800367b3  mov     [rbp+57h+var_70], rsi
0x1800367b7  mov     rcx, [r15]
0x1800367ba  mov     rax, [rcx+0C0h]
0x1800367c1  mov     rcx, r15
0x1800367c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367c9  mov     [rsi], eax
0x1800367cb  mov     dword ptr [rsi+4], 0
0x1800367d2  xor     r9d, r9d
0x1800367d5  lea     r14d, [r9+1]
0x1800367d9  mov     eax, [rbp+57h+var_C0]
0x1800367dc  test    eax, eax
0x1800367de  jz      short loc_180036828
0x1800367e0  mov     ecx, r9d
0x1800367e3  shl     rcx, 4
0x1800367e7  mov     r8, [rbp+57h+var_90]
0x1800367eb  mov     r10d, [rcx+r8+8]
0x1800367f0  sub     r10d, [rcx+r8]
0x1800367f4  jz      short loc_180036820
0x1800367f6  mov     edx, [rcx+r8+0Ch]
0x1800367fb  sub     edx, [rcx+r8+4]
0x180036800  jz      short loc_180036820
0x180036802  mov     eax, [rsi+4]
0x180036805  add     rax, rax
0x180036808  movups  xmm0, xmmword ptr [rcx+r8]
0x18003680d  movdqu  xmmword ptr [rsi+rax*8+8], xmm0
0x180036813  add     [rsi+4], r14d
0x180036817  imul    edx, r10d
0x18003681b  add     [rdi], edx
0x18003681d  mov     eax, [rbp+57h+var_C0]
0x180036820  add     r9d, r14d
0x180036823  cmp     r9d, eax
0x180036826  jb      short loc_1800367E0
0x180036828  cmp     dword ptr [rdi], 0
0x18003682b  jz      loc_180036C27
0x180036831  mov     [rbp+57h+var_A8], 0
0x180036839  mov     rax, [r15]
0x18003683c  mov     rcx, r15
0x18003683f  mov     rax, [rax+0D8h]
0x180036846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003684b  lea     rcx, [rbp+57h+var_A8]
0x18003684f  mov     [rsp+110h+ppBuffer], rcx; ppBuffer
0x180036854  mov     r9d, r14d; fBottomUpWhenLinear
0x180036857  xor     r8d, r8d; uSubresourceIndex
0x18003685a  mov     rdx, rax; punkSurface
0x18003685d  lea     rcx, IID_ID3D11Texture2D; riid
0x180036864  call    cs:__imp_MFCreateDXGISurfaceBuffer
0x18003686a  mov     rcx, [rbp+5Fh]; this
0x18003686e  lea     rdx, aFailedToCreate_3; "Failed to create media buffer"
0x180036875  mov     [rsp+110h+ppBuffer], rdx; int
0x18003687a  mov     r9d, eax; char *
0x18003687d  lea     rbx, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180036884  mov     r8, rbx; unsigned int
0x180036887  mov     edx, 364h; void *
0x18003688c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180036891  mov     rax, [r15]
0x180036894  mov     rcx, r15
0x180036897  mov     rax, [rax+0D8h]
0x18003689e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368a3  mov     r9, rax
0x1800368a6  mov     [rbp+57h+var_A0], 0
0x1800368ae  mov     rcx, [rax]
0x1800368b1  mov     rax, [rcx]
0x1800368b4  lea     r8, [rbp+57h+var_A0]
0x1800368b8  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x1800368bf  mov     rcx, r9
0x1800368c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368c7  mov     rcx, [rbp+5Fh]; this
0x1800368cb  test    eax, eax
0x1800368cd  js      loc_180036C63
0x1800368d3  xorps   xmm0, xmm0
0x1800368d6  movups  [rbp+57h+var_68], xmm0
0x1800368da  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x1800368de  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x1800368e2  mov     rcx, [rbp+57h+var_A0]
0x1800368e6  mov     rax, [rcx]
0x1800368e9  lea     rdx, [rbp+57h+var_68]
0x1800368ed  mov     rax, [rax+50h]
0x1800368f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368f6  mov     edx, dword ptr [rbp+57h+var_58]
0x1800368f9  cmp     edx, 0Ah
0x1800368fc  jz      short loc_18003690E
0x1800368fe  cmp     edx, 57h ; 'W'
0x180036901  jnz     loc_180036C78
0x180036907  mov     edx, 4
0x18003690c  jmp     short loc_180036913
0x18003690e  mov     edx, 8
0x180036913  mov     rcx, [rbp+57h+var_A8]
0x180036917  mov     rax, [rcx]
0x18003691a  imul    edx, dword ptr [rbp+57h+var_68+4]
0x18003691e  imul    edx, dword ptr [rbp+57h+var_68]
0x180036922  mov     rax, [rax+30h]
0x180036926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003692b  mov     rcx, [rbp+5Fh]; this
0x18003692f  lea     rdx, aFailedToSetBuf; "Failed to set buffer size"
0x180036936  mov     [rsp+110h+ppBuffer], rdx; int
0x18003693b  mov     r9d, eax; char *
0x18003693e  mov     r8, rbx; unsigned int
0x180036941  mov     edx, 36Eh; void *
0x180036946  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003694b  nop
0x18003694c  mov     [rbp+57h+ppIMFSample], 0
0x180036954  lea     rcx, [rbp+57h+ppIMFSample]; ppIMFSample
0x180036958  call    cs:__imp_MFCreateSample
0x18003695e  mov     rcx, [rbp+5Fh]; this
0x180036962  lea     rdx, aFailedToCreate_4; "Failed to create media sample"
0x180036969  mov     [rsp+110h+ppBuffer], rdx; int
0x18003696e  mov     r9d, eax; char *
0x180036971  mov     r8, rbx; unsigned int
0x180036974  mov     edx, 372h; void *
0x180036979  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003697e  mov     rcx, [rbp+57h+ppIMFSample]
0x180036982  mov     rax, [rcx]
0x180036985  mov     rdx, [rbp+57h+var_A8]
0x180036989  mov     rax, [rax+150h]
0x180036990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036995  mov     rcx, [rbp+5Fh]; this
0x180036999  test    eax, eax
0x18003699b  js      loc_180036CAB
0x1800369a1  mov     rcx, [rbp+57h+ppIMFSample]
0x1800369a5  mov     rax, [rcx]
0x1800369a8  mov     r9d, [rsi+4]
0x1800369ac  shl     r9d, 4
0x1800369b0  add     r9d, 8
0x1800369b4  mov     r8, rsi
0x1800369b7  lea     rdx, MFSampleExtension_DirtyRects
0x1800369be  mov     rax, [rax+0D0h]
0x1800369c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369ca  mov     rcx, [rbp+5Fh]; this
0x1800369ce  lea     rdx, aFailedToSetDir; "Failed to set dirty rect info"
0x1800369d5  mov     [rsp+110h+ppBuffer], rdx; int
0x1800369da  mov     r9d, eax; char *
0x1800369dd  mov     r8, rbx; unsigned int
0x1800369e0  mov     edx, 37Eh; void *
0x1800369e5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800369ea  mov     rcx, [rbp+57h+ppIMFSample]
0x1800369ee  mov     rax, [rcx]
0x1800369f1  mov     r8d, [rsi]
0x1800369f4  lea     rdx, MFSampleExtension_FrameNumber
0x1800369fb  mov     rax, [rax+0B0h]
0x180036a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a07  mov     rcx, [rbp+5Fh]; this
0x180036a0b  lea     rdx, aFailedToSetMfs; "Failed to set MFSampleExtension_FrameNu"...
0x180036a12  mov     [rsp+110h+ppBuffer], rdx; int
0x180036a17  mov     r9d, eax; char *
0x180036a1a  mov     r8, rbx; unsigned int
0x180036a1d  mov     edx, 381h; void *
0x180036a22  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180036a27  mov     rdi, [rbp+57h+ppIMFSample]
0x180036a2b  mov     rax, [rdi]
0x180036a2e  mov     rbx, [rax+120h]
0x180036a35  mov     rdx, [r15]
0x180036a38  mov     rcx, r15
0x180036a3b  mov     rax, [rdx+0C8h]
0x180036a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a47  mov     rdx, rax
0x180036a4a  mov     rcx, rdi
0x180036a4d  mov     rax, rbx
0x180036a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a55  mov     rcx, [rbp+5Fh]; this
0x180036a59  lea     rdx, aFailedToSetSam; "Failed to set sample time"
0x180036a60  mov     [rsp+110h+ppBuffer], rdx; int
0x180036a65  mov     r9d, eax; char *
0x180036a68  lea     rbx, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180036a6f  mov     r8, rbx; unsigned int
0x180036a72  mov     edx, 384h; void *
0x180036a77  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180036a7c  mov     rcx, [rbp+57h+ppIMFSample]
0x180036a80  mov     rax, [rcx]
0x180036a83  mov     rdx, [r13+88h]
0x180036a8a  mov     rax, [rax+130h]
0x180036a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a96  mov     rcx, [rbp+5Fh]; this
0x180036a9a  lea     rdx, aFailedToSetSam_0; "Failed to set sample duration"
0x180036aa1  mov     [rsp+110h+ppBuffer], rdx; int
0x180036aa6  mov     r9d, eax; char *
0x180036aa9  mov     r8, rbx; unsigned int
0x180036aac  mov     edx, 387h; void *
0x180036ab1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180036ab6  mov     eax, cs:dword_1800C1058
0x180036abc  cmp     eax, 5
0x180036abf  jbe     short loc_180036B27
0x180036ac1  mov     eax, [rsi]
0x180036ac3  mov     [rbp+57h+var_98], eax
0x180036ac6  lea     rax, aEncodeframesta; "EncodeFrameStart"
0x180036acd  mov     [rbp+57h+var_88], rax
0x180036ad1  lea     rax, aRdpAvencSinkwr_7; "Rdp::Avenc::SinkWriter::CMFEncoder::Enc"...
0x180036ad8  mov     qword ptr [rbp+57h+var_80], rax
0x180036adc  mov     dword ptr [rbp+57h+var_B0], 38Ch
0x180036ae3  mov     [rbp+57h+var_78], rbx
0x180036ae7  lea     rax, [rbp+57h+var_98]
0x180036aeb  mov     [rsp+110h+var_D0], rax
0x180036af0  lea     rax, [rbp+57h+var_88]
0x180036af4  mov     [rsp+110h+var_D8], rax
0x180036af9  lea     rax, [rbp+57h+var_80]
0x180036afd  mov     [rsp+110h+var_E0], rax; char *
0x180036b02  lea     rax, [rbp+57h+var_B0]
0x180036b06  mov     [rsp+110h+var_E8], rax; char *
0x180036b0b  lea     rax, [rbp+57h+var_78]
0x180036b0f  mov     [rsp+110h+ppBuffer], rax
0x180036b14  lea     rdx, word_1800AF376
0x180036b1b  lea     rcx, dword_1800C1058
0x180036b22  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180036b27  mov     rcx, [r13+58h]
0x180036b2b  mov     rax, [rcx]
0x180036b2e  mov     r8, [rbp+57h+ppIMFSample]
0x180036b32  xor     edx, edx
0x180036b34  mov     rax, [rax+30h]
0x180036b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b3d  cmp     eax, 800704C7h
0x180036b42  jnz     short loc_180036B75
0x180036b44  mov     rcx, [rbp+57h+ppIMFSample]
0x180036b48  test    rcx, rcx
0x180036b4b  jz      short loc_180036B5A
0x180036b4d  mov     rax, [rcx]
0x180036b50  mov     rax, [rax+10h]
0x180036b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b59  nop
0x180036b5a  mov     rcx, [rbp+57h+var_A0]
0x180036b5e  test    rcx, rcx
0x180036b61  jz      short loc_180036B70
0x180036b63  mov     rax, [rcx]
0x180036b66  mov     rax, [rax+10h]
0x180036b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b6f  nop
0x180036b70  jmp     loc_180036C11
0x180036b75  mov     rcx, [rbp+5Fh]; this
0x180036b79  lea     rdx, aFailedToWriteS; "Failed to write sample"
0x180036b80  mov     [rsp+110h+ppBuffer], rdx; int
0x180036b85  mov     r9d, eax; char *
0x180036b88  mov     r8, rbx; unsigned int
0x180036b8b  mov     edx, 396h; void *
0x180036b90  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180036b95  xor     r8d, r8d; bAlertable
0x180036b98  mov     edx, 9C4h; dwMilliseconds
0x180036b9d  mov     rcx, [r13+90h]; hHandle
0x180036ba4  call    cs:__imp_WaitForSingleObjectEx
0x180036baa  cmp     eax, 102h
0x180036baf  jz      short loc_180036BBC
0x180036bb1  test    eax, eax
0x180036bb3  jnz     loc_180036C4D
0x180036bb9  xor     r14b, r14b
0x180036bbc  mov     rcx, [rbp+5Fh]; this
0x180036bc0  lea     rax, aTimeoutWhileWa; "Timeout while waiting for sample comple"...
0x180036bc7  mov     [rsp+110h+var_E8], rax; bool
0x180036bcc  mov     byte ptr [rsp+110h+ppBuffer], r14b; int
0x180036bd1  mov     r9d, 800705B4h; char *
0x180036bd7  mov     r8, rbx; unsigned int
0x180036bda  mov     edx, 39Fh; void *
0x180036bdf  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180036be4  nop
0x180036be5  mov     rcx, [rbp+57h+ppIMFSample]
0x180036be9  test    rcx, rcx
0x180036bec  jz      short loc_180036BFB
0x180036bee  mov     rax, [rcx]
0x180036bf1  mov     rax, [rax+10h]
0x180036bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
