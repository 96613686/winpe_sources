# Rdp::Avenc::Hevc::CHevc420Compressor::EncodeFrame(Rdp::Avenc::IFrameBuffer1 *,bool,uint &)

- ea: `0x18002e960`
- end: `0x18002f053`
- name: `?EncodeFrame@CHevc420Compressor@Hevc@Avenc@Rdp@@QEAAXPEAUIFrameBuffer1@34@_NAEAI@Z`
- size: `1779`
- prototype: `void __fastcall(Rdp::Avenc::Hevc::CHevc420Compressor *__hidden this, struct Rdp::Avenc::IFrameBuffer1 *, bool, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800293c8`
- `0x180029df8`

## callees

- `0x180006580`
- `0x1800069a0`
- `0x180007018`
- `0x1800072b0`
- `0x1800080cc`
- `0x18000e848`
- `0x18000ec04`
- `0x1800199cc`
- `0x18002bc04`
- `0x18002e2f4`
- `0x18002e960`
- `0x180089010`

## string_xrefs

- `0x18002f00e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18002e9d7`: `Failed to get moves and dirties`
- `0x18002f041`: `onecoreuap\termsrv\rdp_bin\win\common/inc/GraphicsUtils.h`
- `0x18002e9e6`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\hevcprocessor\hevccompressor.cpp`
- `0x18002eb40`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\hevcprocessor\hevccompressor.cpp`
- `0x18002ed30`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\hevcprocessor\hevccompressor.cpp`
- `0x18002ed6e`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\hevcprocessor\hevccompressor.cpp`
- `0x18002ef3f`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\hevcprocessor\hevccompressor.cpp`
- `0x18002eb31`: `Failed to create media buffer`
- `0x18002ec2a`: `Failed to create media sample`
- `0x18002ecd3`: `Failed to set MFSampleExtension_FrameNumber`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall Rdp::Avenc::Hevc::CHevc420Compressor::EncodeFrame(
        Rdp::Avenc::Hevc::CHevc420Compressor *this,
        struct Rdp::Avenc::IFrameBuffer1 *a2,
        char a3,
        unsigned int *a4)
{
  unsigned int v7; // eax
  __int64 v8; // rax
  _DWORD *v9; // rbx
  unsigned int v10; // eax
  unsigned int v11; // edx
  unsigned int v12; // ebx
  unsigned int *v13; // rsi
  __int64 v14; // rdx
  __int128 *v15; // r8
  __int64 v16; // r9
  unsigned int i; // eax
  __int64 v18; // rcx
  int v19; // r10d
  __int64 (__fastcall *v20)(GUID *, __int64, _QWORD, __int64, __int64 *); // rbx
  __int64 v21; // rax
  __int64 v22; // r9
  unsigned int v23; // eax
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // rax
  int v25; // eax
  int v26; // edx
  unsigned int v27; // eax
  __int64 (__fastcall *v28)(struct IMFSample **); // rax
  unsigned int v29; // eax
  int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  struct IMFSample *v33; // rdi
  HRESULT (__stdcall *SetSampleTime)(IMFSample *, LONGLONG); // rbx
  __int64 v35; // rax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int j; // ebx
  unsigned int v39; // r9d
  unsigned int v40; // r8d
  int v41; // r10d
  unsigned int k; // edx
  unsigned int m; // r11d
  unsigned __int64 v44; // rbx
  void *v45; // rdi
  struct IMFSample *v46; // rbx
  unsigned __int64 v47; // rax
  __int64 v48; // r12
  __int64 v49; // r13
  __int64 v50; // rcx
  int v51; // ebx
  int v52; // eax
  unsigned int v53; // eax
  unsigned int v54; // eax
  unsigned int v55; // eax
  int v56; // edx
  int v57; // [rsp+20h] [rbp-99h]
  int v58; // [rsp+20h] [rbp-99h]
  struct IMFSample *v59; // [rsp+28h] [rbp-91h]
  struct IMFSample *v60; // [rsp+28h] [rbp-91h]
  struct IMFSample *v61; // [rsp+28h] [rbp-91h]
  struct IMFSample *v62; // [rsp+28h] [rbp-91h]
  struct IMFSample *v63; // [rsp+28h] [rbp-91h]
  struct IMFSample *v64; // [rsp+28h] [rbp-91h]
  struct IMFSample *v65; // [rsp+28h] [rbp-91h]
  struct IMFSample *v66; // [rsp+28h] [rbp-91h]
  struct IMFSample *v67; // [rsp+28h] [rbp-91h]
  int v68; // [rsp+40h] [rbp-79h] BYREF
  struct IMFSample *v69; // [rsp+48h] [rbp-71h] BYREF
  char *v70; // [rsp+50h] [rbp-69h]
  __int64 v71; // [rsp+58h] [rbp-61h] BYREF
  __int128 *v72; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v73; // [rsp+68h] [rbp-51h] BYREF
  __int64 v74; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v75[4]; // [rsp+78h] [rbp-41h] BYREF
  __int128 v76; // [rsp+98h] [rbp-21h] BYREF
  _OWORD v77[3]; // [rsp+A8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v68 = 0;
  v72 = 0;
  v76 = 0;
  if ( a3 )
  {
    v7 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *, _QWORD, _QWORD, __int128 **, int *))(*(_QWORD *)a2 + 208LL))(
           a2,
           0,
           0,
           &v72,
           &v68);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevccompressor.cpp",
      (const char *)v7,
      (int)"Failed to get moves and dirties",
      (const char *)v59);
  }
  else
  {
    v8 = *((_QWORD *)this + 26);
    v9 = *(_DWORD **)(v8 + 136);
    if ( v9 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 8LL))(*(_QWORD *)(v8 + 136));
    v10 = v9[37];
    v11 = v9[38];
    *(_QWORD *)&v76 = 0;
    *((_QWORD *)&v76 + 1) = __PAIR64__(v11, v10);
    v72 = &v76;
    v68 = 1;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v12 = 16 * v68 + 8;
  v13 = (unsigned int *)operator new[](v12);
  memset_0(v13, 0, v12);
  v75[1] = v13;
  *(_QWORD *)v13 = (*(unsigned int (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *))(*(_QWORD *)a2 + 192LL))(a2);
  v16 = 0;
  for ( i = v68; (unsigned int)v16 < i; v16 = (unsigned int)(v16 + 1) )
  {
    v18 = (unsigned int)v16;
    v15 = v72;
    v19 = DWORD2(v72[v18]) - LODWORD(v72[v18]);
    if ( v19 )
    {
      v14 = (unsigned int)(HIDWORD(v72[v18]) - DWORD1(v72[v18]));
      if ( (_DWORD)v14 )
      {
        *(_OWORD *)&v13[4 * v13[1]++ + 2] = v72[v18];
        v14 = (unsigned int)(v19 * v14);
        *a4 += v14;
        i = v68;
      }
    }
  }
  *((_QWORD *)this + 31) = *v13;
  v71 = 0;
  v20 = *(__int64 (__fastcall **)(GUID *, __int64, _QWORD, __int64, __int64 *))(*((_QWORD *)this + 24) + 40LL);
  v71 = 0;
  v21 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *, __int64, __int128 *, __int64))(*(_QWORD *)a2 + 216LL))(
          a2,
          v14,
          v15,
          v16);
  LOBYTE(v22) = 1;
  v23 = v20(&IID_ID3D11Texture2D, v21, 0, v22, &v71);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xEE,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevccompressor.cpp",
    (const char *)v23,
    (int)"Failed to create media buffer",
    (const char *)v59);
  v24 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *))(*(_QWORD *)a2 + 216LL))(a2);
  v74 = 0;
  v25 = (**v24)(v24, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v74);
  if ( v25 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v25,
      v57);
  memset(v77, 0, 44);
  (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v74 + 80LL))(v74, v77);
  if ( LODWORD(v77[1]) == 10 )
  {
    v26 = 8;
  }
  else
  {
    if ( LODWORD(v77[1]) != 87 )
    {
      v55 = wil::verify_hresult<long>(2147942487LL);
      LODWORD(v60) = v56;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/GraphicsUtils.h",
        (const char *)v55,
        (int)"Unsupported DXGI_FORMAT: %d",
        (const char *)v60);
    }
    v26 = 4;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v71 + 48LL))(
          v71,
          (unsigned int)(LODWORD(v77[0]) * DWORD1(v77[0]) * v26));
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xF8,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevccompressor.cpp",
    (const char *)v27,
    (int)"Failed to set buffer size",
    (const char *)v60);
  v69 = 0;
  v28 = *(__int64 (__fastcall **)(struct IMFSample **))(*((_QWORD *)this + 24) + 16LL);
  v69 = 0;
  v29 = v28(&v69);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xFC,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevccompressor.cpp",
    (const char *)v29,
    (int)"Failed to create media sample",
    (const char *)v61);
  v30 = ((__int64 (__fastcall *)(struct IMFSample *, __int64))v69->lpVtbl->AddBuffer)(v69, v71);
  if ( v30 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevccompressor.cpp",
      (const char *)(unsigned int)v30,
      v58);
  v31 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *, unsigned int *, _QWORD))v69->lpVtbl->SetBlob)(
          v69,
          MFSampleExtension_DirtyRects,
          v13,
          16 * v13[1] + 8);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x108,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevccompressor.cpp",
    (const char *)v31,
    (int)"Failed to set dirty rect info",
    (const char *)v62);
  v32 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *, _QWORD))v69->lpVtbl->SetUINT64)(
          v69,
          MFSampleExtension_FrameNumber,
          *v13);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x10B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevccompressor.cpp",
    (const char *)v32,
    (int)"Failed to set MFSampleExtension_FrameNumber",
    (const char *)v63);
  v33 = v69;
  SetSampleTime = v69->lpVtbl->SetSampleTime;
  v35 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *))(*(_QWORD *)a2 + 200LL))(a2);
  v36 = ((__int64 (__fastcall *)(struct IMFSample *, __int64))SetSampleTime)(v33, v35);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x10E,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevccompressor.cpp",
    (const char *)v36,
    (int)"Failed to set sample time",
    (const char *)v64);
  v37 = ((__int64 (__fastcall *)(struct IMFSample *, _QWORD))v69->lpVtbl->SetSampleDuration)(
          v69,
          *((_QWORD *)this + 30));
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x111,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevccompressor.cpp",
    (const char *)v37,
    (int)"Failed to set sample duration",
    (const char *)v65);
  memset_0(*((void **)this + 16), 3, *((_QWORD *)this + 17) - *((_QWORD *)this + 16));
  for ( j = 0; j < v13[1]; ++j )
  {
    v39 = (int)(v13[4 * j + 4] - 1) >> 4;
    v40 = (int)(v13[4 * j + 5] - 1) >> 4;
    if ( (unsigned __int64)(v39 + *((_DWORD *)this + 39) * v40) >= *((_QWORD *)this + 17) - *((_QWORD *)this + 16) )
    {
      v54 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xEB,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\adancefeaturemap.cpp",
        (const char *)v54,
        (int)"Buffer overflow",
        (const char *)v66);
    }
    v41 = (int)v13[4 * j + 2] >> 4;
    for ( k = (int)v13[4 * j + 3] >> 4; k <= v40; ++k )
    {
      for ( m = v41; m <= v39; ++m )
        *(_BYTE *)(m + *((_DWORD *)this + 39) * k + *((_QWORD *)this + 16)) = 2;
    }
  }
  v73 = 2 * v68;
  v44 = saturated_mul((unsigned int)(2 * v68), 2u);
  v45 = operator new[](v44);
  memset_0(v45, 0, v44);
  v75[2] = v45;
  v46 = v69;
  v47 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *))(*(_QWORD *)a2 + 200LL))(a2);
  Rdp::Avenc::Hevc::CHevc420Compressor::Compress(
    this,
    v47,
    a2,
    (struct Rdp::Protocol::_RDPGFX_AVC420_QUANT_QUALITY *)v45,
    &v73,
    v46);
  v48 = *((_QWORD *)this + 26);
  v49 = (__int64)v72;
  LODWORD(v70) = v68;
  v75[3] = v75;
  v50 = *(_QWORD *)(*((_QWORD *)this + 11) + 296LL);
  v75[0] = v50;
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
  v51 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *))(*(_QWORD *)a2 + 200LL))(a2);
  v52 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameBuffer1 *))(*(_QWORD *)a2 + 192LL))(a2);
  v53 = Rdp::Avenc::Hevc::CHevcFrameProcessor::OnProcessIMFSample(
          v48,
          v52,
          v51,
          (unsigned int)v75,
          (__int64)v45,
          (_DWORD)v70,
          v49);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x135,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevccompressor.cpp",
    (const char *)v53,
    (int)"Hevc OnProcessBuffer failed",
    (const char *)v67);
  operator delete(v45);
  if ( v69 )
    ((void (__fastcall *)(struct IMFSample *))v69->lpVtbl->Release)(v69);
  if ( v74 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
  if ( v71 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
  operator delete(v13);
}

```

## disassembly

```asm
0x18002e960  mov     [rsp-8+arg_10], rbx
0x18002e965  push    rbp
0x18002e966  push    rsi
0x18002e967  push    rdi
0x18002e968  push    r12
0x18002e96a  push    r13
0x18002e96c  push    r14
0x18002e96e  push    r15
0x18002e970  lea     rbp, [rsp-27h]
0x18002e975  sub     rsp, 0E0h
0x18002e97c  mov     rax, cs:__security_cookie
0x18002e983  xor     rax, rsp
0x18002e986  mov     [rbp+57h+var_38], rax
0x18002e98a  mov     rdi, r9
0x18002e98d  mov     r14, rdx
0x18002e990  mov     r15, rcx
0x18002e993  xor     r12d, r12d
0x18002e996  mov     [rbp+57h+var_D0], r12d
0x18002e99a  mov     [rbp+57h+var_B0], r12
0x18002e99e  xorps   xmm0, xmm0
0x18002e9a1  movups  [rbp+57h+var_78], xmm0
0x18002e9a5  lea     r13d, [r12+1]
0x18002e9aa  test    r8b, r8b
0x18002e9ad  jz      short loc_18002E9F9
0x18002e9af  mov     rax, [rdx]
0x18002e9b2  lea     rcx, [rbp+57h+var_D0]
0x18002e9b6  mov     [rsp+110h+var_F0], rcx
0x18002e9bb  lea     r9, [rbp+57h+var_B0]
0x18002e9bf  xor     r8d, r8d
0x18002e9c2  xor     edx, edx
0x18002e9c4  mov     rcx, r14
0x18002e9c7  mov     rax, [rax+0D0h]
0x18002e9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9d3  mov     rcx, [rbp+5Fh]; this
0x18002e9d7  lea     rdx, aFailedToGetMov; "Failed to get moves and dirties"
0x18002e9de  mov     [rsp+110h+var_F0], rdx; int
0x18002e9e3  mov     r9d, eax; char *
0x18002e9e6  lea     r8, aOnecoreuapTerm_47; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002e9ed  mov     edx, 0C5h; void *
0x18002e9f2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002e9f7  jmp     short loc_18002EA4E
0x18002e9f9  mov     rax, [rcx+0D0h]
0x18002ea00  mov     rbx, [rax+88h]
0x18002ea07  test    rbx, rbx
0x18002ea0a  jz      short loc_18002EA1C
0x18002ea0c  mov     rax, [rbx]
0x18002ea0f  mov     rcx, rbx
0x18002ea12  mov     rax, [rax+8]
0x18002ea16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea1b  nop
0x18002ea1c  mov     eax, [rbx+94h]
0x18002ea22  mov     edx, [rbx+98h]
0x18002ea28  mov     qword ptr [rbp+57h+var_78], r12
0x18002ea2c  mov     dword ptr [rbp+57h+var_78+8], eax
0x18002ea2f  mov     dword ptr [rbp+57h+var_78+0Ch], edx
0x18002ea32  lea     rax, [rbp+57h+var_78]
0x18002ea36  mov     [rbp+57h+var_B0], rax
0x18002ea3a  mov     [rbp+57h+var_D0], r13d
0x18002ea3e  mov     rax, [rbx]
0x18002ea41  mov     rcx, rbx
0x18002ea44  mov     rax, [rax+10h]
0x18002ea48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea4d  nop
0x18002ea4e  mov     eax, [rbp+57h+var_D0]
0x18002ea51  shl     eax, 4
0x18002ea54  add     eax, 8
0x18002ea57  mov     ebx, eax
0x18002ea59  mov     ecx, eax; unsigned __int64
0x18002ea5b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002ea60  mov     rsi, rax
0x18002ea63  mov     r8d, ebx; Size
0x18002ea66  xor     edx, edx; Val
0x18002ea68  mov     rcx, rax; void *
0x18002ea6b  call    memset_0
0x18002ea70  mov     [rbp+57h+var_90], rsi
0x18002ea74  mov     rcx, [r14]
0x18002ea77  mov     rax, [rcx+0C0h]
0x18002ea7e  mov     rcx, r14
0x18002ea81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea86  mov     [rsi], eax
0x18002ea88  mov     [rsi+4], r12d
0x18002ea8c  mov     r9d, r12d
0x18002ea8f  mov     eax, [rbp+57h+var_D0]
0x18002ea92  test    eax, eax
0x18002ea94  jz      short loc_18002EADE
0x18002ea96  mov     ecx, r9d
0x18002ea99  shl     rcx, 4
0x18002ea9d  mov     r8, [rbp+57h+var_B0]
0x18002eaa1  mov     r10d, [rcx+r8+8]
0x18002eaa6  sub     r10d, [rcx+r8]
0x18002eaaa  jz      short loc_18002EAD6
0x18002eaac  mov     edx, [rcx+r8+0Ch]
0x18002eab1  sub     edx, [rcx+r8+4]
0x18002eab6  jz      short loc_18002EAD6
0x18002eab8  mov     eax, [rsi+4]
0x18002eabb  add     rax, rax
0x18002eabe  movups  xmm0, xmmword ptr [rcx+r8]
0x18002eac3  movdqu  xmmword ptr [rsi+rax*8+8], xmm0
0x18002eac9  add     [rsi+4], r13d
0x18002eacd  imul    edx, r10d
0x18002ead1  add     [rdi], edx
0x18002ead3  mov     eax, [rbp+57h+var_D0]
0x18002ead6  add     r9d, r13d
0x18002ead9  cmp     r9d, eax
0x18002eadc  jb      short loc_18002EA96
0x18002eade  mov     eax, [rsi]
0x18002eae0  mov     [r15+0F8h], rax
0x18002eae7  mov     [rbp+57h+var_B8], r12
0x18002eaeb  mov     rax, [r15+0C0h]
0x18002eaf2  mov     rbx, [rax+28h]
0x18002eaf6  mov     [rbp+57h+var_B8], r12
0x18002eafa  mov     rcx, [r14]
0x18002eafd  mov     rax, [rcx+0D8h]
0x18002eb04  mov     rcx, r14
0x18002eb07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb0c  lea     rcx, [rbp+57h+var_B8]
0x18002eb10  mov     [rsp+110h+var_F0], rcx
0x18002eb15  mov     r9b, r13b
0x18002eb18  xor     r8d, r8d
0x18002eb1b  mov     rdx, rax
0x18002eb1e  lea     rcx, IID_ID3D11Texture2D
0x18002eb25  mov     rax, rbx
0x18002eb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb2d  mov     rcx, [rbp+5Fh]; this
0x18002eb31  lea     rdx, aFailedToCreate_3; "Failed to create media buffer"
0x18002eb38  mov     [rsp+110h+var_F0], rdx; int
0x18002eb3d  mov     r9d, eax; char *
0x18002eb40  lea     rbx, aOnecoreuapTerm_47; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002eb47  mov     r8, rbx; unsigned int
0x18002eb4a  mov     edx, 0EEh; void *
0x18002eb4f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002eb54  mov     rax, [r14]
0x18002eb57  mov     rcx, r14
0x18002eb5a  mov     rax, [rax+0D8h]
0x18002eb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb66  mov     r9, rax
0x18002eb69  mov     [rbp+57h+var_A0], r12
0x18002eb6d  mov     rcx, [rax]
0x18002eb70  mov     rax, [rcx]
0x18002eb73  lea     r8, [rbp+57h+var_A0]
0x18002eb77  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x18002eb7e  mov     rcx, r9
0x18002eb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb86  mov     rcx, [rbp+5Fh]; this
0x18002eb8a  test    eax, eax
0x18002eb8c  js      loc_18002F00B
0x18002eb92  xorps   xmm0, xmm0
0x18002eb95  movups  [rbp+57h+var_68], xmm0
0x18002eb99  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18002eb9d  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x18002eba1  mov     rcx, [rbp+57h+var_A0]
0x18002eba5  mov     rax, [rcx]
0x18002eba8  lea     rdx, [rbp+57h+var_68]
0x18002ebac  mov     rax, [rax+50h]
0x18002ebb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebb5  mov     edx, dword ptr [rbp+57h+var_58]
0x18002ebb8  cmp     edx, 0Ah
0x18002ebbb  jz      short loc_18002EBCD
0x18002ebbd  cmp     edx, 57h ; 'W'
0x18002ebc0  jnz     loc_18002F020
0x18002ebc6  mov     edx, 4
0x18002ebcb  jmp     short loc_18002EBD2
0x18002ebcd  mov     edx, 8
0x18002ebd2  mov     rcx, [rbp+57h+var_B8]
0x18002ebd6  mov     rax, [rcx]
0x18002ebd9  imul    edx, dword ptr [rbp+57h+var_68+4]
0x18002ebdd  imul    edx, dword ptr [rbp+57h+var_68]
0x18002ebe1  mov     rax, [rax+30h]
0x18002ebe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebea  mov     rcx, [rbp+5Fh]; this
0x18002ebee  lea     rdx, aFailedToSetBuf; "Failed to set buffer size"
0x18002ebf5  mov     [rsp+110h+var_F0], rdx; int
0x18002ebfa  mov     r9d, eax; char *
0x18002ebfd  mov     r8, rbx; unsigned int
0x18002ec00  mov     edx, 0F8h; void *
0x18002ec05  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ec0a  mov     [rbp+57h+var_C8], r12
0x18002ec0e  mov     rax, [r15+0C0h]
0x18002ec15  mov     rax, [rax+10h]
0x18002ec19  mov     [rbp+57h+var_C8], r12
0x18002ec1d  lea     rcx, [rbp+57h+var_C8]
0x18002ec21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec26  mov     rcx, [rbp+5Fh]; this
0x18002ec2a  lea     rdx, aFailedToCreate_4; "Failed to create media sample"
0x18002ec31  mov     [rsp+110h+var_F0], rdx; int
0x18002ec36  mov     r9d, eax; char *
0x18002ec39  mov     r8, rbx; unsigned int
0x18002ec3c  mov     edx, 0FCh; void *
0x18002ec41  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ec46  mov     rcx, [rbp+57h+var_C8]
0x18002ec4a  mov     rax, [rcx]
0x18002ec4d  mov     rdx, [rbp+57h+var_B8]
0x18002ec51  mov     rax, [rax+150h]
0x18002ec58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec5d  mov     rcx, [rbp+5Fh]; this
0x18002ec61  test    eax, eax
0x18002ec63  js      loc_18002EFCB
0x18002ec69  mov     rcx, [rbp+57h+var_C8]
0x18002ec6d  mov     rax, [rcx]
0x18002ec70  mov     r9d, [rsi+4]
0x18002ec74  shl     r9d, 4
0x18002ec78  add     r9d, 8
0x18002ec7c  mov     r8, rsi
0x18002ec7f  lea     rdx, MFSampleExtension_DirtyRects
0x18002ec86  mov     rax, [rax+0D0h]
0x18002ec8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec92  mov     rcx, [rbp+5Fh]; this
0x18002ec96  lea     rdx, aFailedToSetDir; "Failed to set dirty rect info"
0x18002ec9d  mov     [rsp+110h+var_F0], rdx; int
0x18002eca2  mov     r9d, eax; char *
0x18002eca5  mov     r8, rbx; unsigned int
0x18002eca8  mov     edx, 108h; void *
0x18002ecad  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ecb2  mov     rcx, [rbp+57h+var_C8]
0x18002ecb6  mov     rax, [rcx]
0x18002ecb9  mov     r8d, [rsi]
0x18002ecbc  lea     rdx, MFSampleExtension_FrameNumber
0x18002ecc3  mov     rax, [rax+0B0h]
0x18002ecca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eccf  mov     rcx, [rbp+5Fh]; this
0x18002ecd3  lea     rdx, aFailedToSetMfs; "Failed to set MFSampleExtension_FrameNu"...
0x18002ecda  mov     [rsp+110h+var_F0], rdx; int
0x18002ecdf  mov     r9d, eax; char *
0x18002ece2  mov     r8, rbx; unsigned int
0x18002ece5  mov     edx, 10Bh; void *
0x18002ecea  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ecef  mov     rdi, [rbp+57h+var_C8]
0x18002ecf3  mov     rax, [rdi]
0x18002ecf6  mov     rbx, [rax+120h]
0x18002ecfd  mov     rdx, [r14]
0x18002ed00  mov     rcx, r14
0x18002ed03  mov     rax, [rdx+0C8h]
0x18002ed0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed0f  mov     rdx, rax
0x18002ed12  mov     rcx, rdi
0x18002ed15  mov     rax, rbx
0x18002ed18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed1d  mov     rcx, [rbp+5Fh]; this
0x18002ed21  lea     rdx, aFailedToSetSam; "Failed to set sample time"
0x18002ed28  mov     [rsp+110h+var_F0], rdx; int
0x18002ed2d  mov     r9d, eax; char *
0x18002ed30  lea     r8, aOnecoreuapTerm_47; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002ed37  mov     edx, 10Eh; void *
0x18002ed3c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ed41  mov     rcx, [rbp+57h+var_C8]
0x18002ed45  mov     rax, [rcx]
0x18002ed48  mov     rdx, [r15+0F0h]
0x18002ed4f  mov     rax, [rax+130h]
0x18002ed56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed5b  mov     rcx, [rbp+5Fh]; this
0x18002ed5f  lea     rdx, aFailedToSetSam_0; "Failed to set sample duration"
0x18002ed66  mov     [rsp+110h+var_F0], rdx; int
0x18002ed6b  mov     r9d, eax; char *
0x18002ed6e  lea     r8, aOnecoreuapTerm_47; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002ed75  mov     edx, 111h; void *
0x18002ed7a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ed7f  mov     rcx, [r15+80h]; void *
0x18002ed86  mov     r8, [r15+88h]
0x18002ed8d  sub     r8, rcx; Size
0x18002ed90  mov     edx, 3; Val
0x18002ed95  call    memset_0
0x18002ed9a  mov     ebx, r12d
0x18002ed9d  cmp     [rsi+4], r12d
0x18002eda1  jbe     loc_18002EE37
0x18002eda7  mov     edx, ebx
0x18002eda9  add     rdx, rdx
0x18002edac  mov     r9d, [rsi+rdx*8+10h]
0x18002edb1  sub     r9d, r13d
0x18002edb4  sar     r9d, 4
0x18002edb8  mov     r8d, [rsi+rdx*8+14h]
0x18002edbd  sub     r8d, r13d
0x18002edc0  sar     r8d, 4
0x18002edc4  mov     ecx, r8d
0x18002edc7  imul    ecx, [r15+9Ch]
0x18002edcf  add     ecx, r9d
0x18002edd2  mov     rax, [r15+88h]
0x18002edd9  sub     rax, [r15+80h]
0x18002ede0  cmp     rcx, rax
0x18002ede3  jnb     loc_18002EFDC
0x18002ede9  mov     r10d, [rsi+rdx*8+8]
0x18002edee  sar     r10d, 4
0x18002edf2  mov     edx, [rsi+rdx*8+0Ch]
0x18002edf6  sar     edx, 4
0x18002edf9  jmp     short loc_18002EE26
0x18002edfb  mov     r11d, r10d
0x18002edfe  cmp     r10d, r9d
0x18002ee01  ja      short loc_18002EE23
0x18002ee03  mov     ecx, edx
0x18002ee05  imul    ecx, [r15+9Ch]
0x18002ee0d  add     ecx, r11d
0x18002ee10  mov     rax, [r15+80h]
0x18002ee17  mov     byte ptr [rcx+rax], 2
0x18002ee1b  add     r11d, r13d
0x18002ee1e  cmp     r11d, r9d
0x18002ee21  jbe     short loc_18002EE03
0x18002ee23  add     edx, r13d
0x18002ee26  cmp     edx, r8d
0x18002ee29  jbe     short loc_18002EDFB
0x18002ee2b  add     ebx, r13d
0x18002ee2e  cmp     ebx, [rsi+4]
  ... truncated ...
```
