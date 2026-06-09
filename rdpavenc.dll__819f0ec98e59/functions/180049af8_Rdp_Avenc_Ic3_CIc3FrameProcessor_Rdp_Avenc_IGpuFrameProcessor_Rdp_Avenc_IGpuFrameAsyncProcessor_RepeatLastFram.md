# Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::RepeatLastFrameThreadProc(void)

- ea: `0x180049af8`
- end: `0x18004a025`
- name: `?RepeatLastFrameThreadProc@?$CIc3FrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@UIGpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAXXZ`
- size: `1325`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180047b10`

## callees

- `0x180004b8c`
- `0x1800065a4`
- `0x1800103c0`
- `0x180010bc8`
- `0x180047b44`
- `0x180047ba8`
- `0x180047df4`
- `0x180048f2c`
- `0x180049498`
- `0x180049af8`
- `0x18004f6f4`
- `0x180054f34`
- `0x180058a88`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049fef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049fef`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180049bf2`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180049dd2`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180049bf2`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180049dd2`

## string_xrefs

- `0x180049ca4`: `Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncProcessor>::RepeatLastFrameThreadProc`
- `0x180049ee5`: `Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncProcessor>::RepeatLastFrameThreadProc`

## pseudocode

```c
void __fastcall Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::RepeatLastFrameThreadProc(
        __int64 a1)
{
  __int64 v2; // r14
  _QWORD *v3; // rax
  __int64 v4; // rsi
  char *v5; // rsi
  char *v6; // rcx
  unsigned __int64 v7; // rbx
  __int64 v8; // rax
  int v9; // r8d
  int v10; // r9d
  struct Rdp::Avenc::Ic3::CDsStreamSample *v11; // r15
  __int64 v12; // rcx
  __int64 v13; // rdx
  char v14; // bl
  __int64 v15; // r8
  char *v16; // rcx
  char *v17; // rcx
  Rdp::Avenc::Ic3::CVideoSourceProvider *v18; // rcx
  struct IVirtualVideoSink *Sink; // r15
  unsigned __int64 v20; // r13
  void (__fastcall ***v21)(_QWORD); // rax
  void (__fastcall ***v22)(_QWORD); // rsi
  __int64 v23; // rbx
  __int64 v24; // rax
  char v25; // bl
  __int64 v26; // rdx
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rax
  __int64 v30; // r8
  __int64 v32; // [rsp+60h] [rbp-49h] BYREF
  const char *v33; // [rsp+68h] [rbp-41h] BYREF
  int v34; // [rsp+70h] [rbp-39h] BYREF
  int v35; // [rsp+74h] [rbp-35h] BYREF
  const char *v36; // [rsp+78h] [rbp-31h] BYREF
  const char *v37; // [rsp+80h] [rbp-29h] BYREF
  const char *v38; // [rsp+88h] [rbp-21h] BYREF
  __int64 v39; // [rsp+90h] [rbp-19h] BYREF
  char v40; // [rsp+98h] [rbp-11h]
  __int64 v41; // [rsp+A0h] [rbp-9h] BYREF
  char v42[8]; // [rsp+A8h] [rbp-1h] BYREF
  Rdp::Avenc::Ic3::CDsStreamSample *v43; // [rsp+B0h] [rbp+7h]
  void *v44; // [rsp+B8h] [rbp+Fh]
  int v45; // [rsp+110h] [rbp+67h] BYREF
  int v46; // [rsp+118h] [rbp+6Fh] BYREF
  int v47; // [rsp+120h] [rbp+77h] BYREF
  int v48; // [rsp+128h] [rbp+7Fh] BYREF

  v2 = a1 + 256;
  v39 = a1 + 256;
  v40 = 0;
  if ( (unsigned int)mtx_do_lock(a1 + 256) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v2 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v2 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v40 = 1;
  if ( !*(_BYTE *)(a1 + 432) )
  {
    do
    {
      v32 = 18;
      v3 = (_QWORD *)std::_To_absolute_time<__int64,std::ratio<1,1000>>(v42, &v32);
      if ( (unsigned int)std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
                           (RTL_CONDITION_VARIABLE *)(a1 + 336),
                           &v39,
                           v3) == 1 )
      {
        v4 = *(_QWORD *)(a1 + 208);
        if ( v4 )
        {
          v5 = *(char **)(v4 + 280);
          v33 = v5;
          if ( v5 )
          {
            v6 = &v5[*(int *)(*((_QWORD *)v5 + 1) + 4LL) + 8];
            (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
            if ( *(_QWORD *)(a1 + 240) )
            {
              v32 = 0;
              GetSystemTimePreciseAsFileTime(&v32);
              v7 = (unsigned int)v32
                 + ((unsigned __int64)HIDWORD(v32) << 32)
                 - *(_QWORD *)(a1 + 424)
                 - 116444736000000000LL;
              if ( v7 - 180001 <= 0x2F8315E )
              {
                v43 = (Rdp::Avenc::Ic3::CDsStreamSample *)operator new(0xA8u);
                v8 = Rdp::Avenc::Ic3::CDsStreamSample::CDsStreamSample(
                       v43,
                       *(const struct Rdp::Avenc::Ic3::CDsStreamSample **)(a1 + 240),
                       v7);
                v11 = (struct Rdp::Avenc::Ic3::CDsStreamSample *)v8;
                if ( v8 )
                {
                  v12 = v8 + *(int *)(*(_QWORD *)(v8 + 8) + 4LL) + 8LL;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
                }
                if ( (unsigned int)dword_1800C1058 > 5 )
                {
                  v32 = v7;
                  v36 = (const char *)*((_QWORD *)v11 + 16);
                  v13 = *(_QWORD *)(a1 + 176);
                  v45 = *(_DWORD *)(*(_QWORD *)(v13 + 104) + 136LL);
                  v46 = *(_DWORD *)(v13 + 128);
                  v37 = "RepeatFrame";
                  v38 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGp"
                        "uFrameAsyncProcessor>::RepeatLastFrameThreadProc";
                  v47 = 672;
                  v33 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                    (unsigned int)&dword_1800C1058,
                    (unsigned int)byte_1800B0BA3,
                    v9,
                    v10,
                    (__int64)&v33,
                    (__int64)&v47,
                    (__int64)&v38,
                    (__int64)&v37,
                    (__int64)&v46,
                    (__int64)&v45,
                    (__int64)&v36,
                    (__int64)&v32);
                }
                v14 = Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(
                        a1,
                        *((_QWORD *)v11 + 16),
                        *((_QWORD *)v11 + 17));
                Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession::ProcessFrame(
                  (Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession *)v5,
                  v11);
                if ( v14 )
                {
                  LOBYTE(v15) = 1;
                  Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::RaiseFirstFrameDoneEvent(
                    a1,
                    *((_QWORD *)v11 + 16),
                    v15);
                }
                v16 = (char *)v11 + *(int *)(*((_QWORD *)v11 + 1) + 4LL) + 8;
                (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 16LL))(v16);
              }
            }
          }
          if ( v5 )
          {
            v17 = &v5[*(int *)(*((_QWORD *)v5 + 1) + 4LL) + 8];
            (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))(v17);
          }
        }
        else
        {
          v18 = *(Rdp::Avenc::Ic3::CVideoSourceProvider **)(a1 + 216);
          if ( v18 )
          {
            Sink = Rdp::Avenc::Ic3::CVideoSourceProvider::GetSink(v18);
            if ( Sink )
            {
              if ( *(_QWORD *)(a1 + 248) )
              {
                v32 = 0;
                GetSystemTimePreciseAsFileTime(&v32);
                v20 = (unsigned int)v32
                    + ((unsigned __int64)HIDWORD(v32) << 32)
                    - *(_QWORD *)(a1 + 424)
                    - 116444736000000000LL;
                if ( v20 - 180001 <= 0x2F8315E )
                {
                  v44 = operator new(0xD0u);
                  v21 = (void (__fastcall ***)(_QWORD))Rdp::Avenc::Ic3::CVirtualFrame::CVirtualFrame(v44, a1 + 248, v20);
                  v22 = v21;
                  v32 = (__int64)v21;
                  if ( v21 )
                    (**v21)(v21);
                  v22[24] = (void (__fastcall **)(_QWORD))((*(__int64 (__fastcall **)(struct IVirtualVideoSink *))(*(_QWORD *)Sink + 16LL))(Sink)
                                                         - (_QWORD)v22[25]);
                  v23 = ((__int64 (__fastcall *)(_QWORD))(*v22)[8])(v22);
                  v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v22[2] + 200LL))(*v22[2]);
                  v25 = Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(
                          a1,
                          (char *)v22[10] + v24,
                          v23);
                  if ( (unsigned int)dword_1800C1058 > 5 )
                  {
                    v33 = (const char *)v20;
                    v41 = ((__int64 (__fastcall *)(_QWORD))(*v22)[8])(v22);
                    v26 = *(_QWORD *)(a1 + 176);
                    v48 = *(_DWORD *)(*(_QWORD *)(v26 + 104) + 136LL);
                    v34 = *(_DWORD *)(v26 + 128);
                    v38 = "RepeatFrame";
                    v37 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::I"
                          "GpuFrameAsyncProcessor>::RepeatLastFrameThreadProc";
                    v35 = 712;
                    v36 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                      (unsigned int)&dword_1800C1058,
                      (unsigned int)&word_1800B0B36,
                      v27,
                      v28,
                      (__int64)&v36,
                      (__int64)&v35,
                      (__int64)&v37,
                      (__int64)&v38,
                      (__int64)&v34,
                      (__int64)&v48,
                      (__int64)&v41,
                      (__int64)&v33);
                  }
                  (*(void (__fastcall **)(struct IVirtualVideoSink *, void (__fastcall ***)(_QWORD)))(*(_QWORD *)Sink + 128LL))(
                    Sink,
                    v22);
                  if ( v25 )
                  {
                    v29 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v22[2] + 200LL))(*v22[2]);
                    LOBYTE(v30) = 1;
                    Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::RaiseFirstFrameDoneEvent(
                      a1,
                      (char *)v22[10] + v29,
                      v30);
                  }
                  (*v22)[1](v22);
                }
              }
            }
          }
        }
      }
    }
    while ( !*(_BYTE *)(a1 + 432) );
    v2 = v39;
  }
  if ( (*(_DWORD *)(v2 + 76))-- == 1 )
  {
    *(_DWORD *)(v2 + 72) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)(v2 + 16));
  }
}

```

## disassembly

```asm
0x180049af8  push    rbp
0x180049afa  push    rbx
0x180049afb  push    rsi
0x180049afc  push    rdi
0x180049afd  push    r12
0x180049aff  push    r13
0x180049b01  push    r14
0x180049b03  push    r15
0x180049b05  lea     rbp, [rsp-1Fh]
0x180049b0a  sub     rsp, 0C8h
0x180049b11  mov     rdi, rcx
0x180049b14  lea     r14, [rcx+100h]
0x180049b1b  mov     [rbp+57h+var_70], r14
0x180049b1f  xor     r12d, r12d
0x180049b22  mov     [rbp+57h+var_68], r12b
0x180049b26  mov     rcx, r14
0x180049b29  call    mtx_do_lock
0x180049b2e  test    eax, eax
0x180049b30  jnz     loc_18004A01A
0x180049b36  mov     eax, [r14+4Ch]
0x180049b3a  cmp     eax, 7FFFFFFFh
0x180049b3f  jz      loc_18004A009
0x180049b45  mov     [rbp+57h+var_68], 1
0x180049b49  cmp     [rdi+1B0h], r12b
0x180049b50  jnz     loc_180049FDC
0x180049b56  mov     rbx, 0FE624E212AC18000h
0x180049b60  lea     r13, aRepeatframe; "RepeatFrame"
0x180049b67  mov     [rbp+57h+var_A0], 12h
0x180049b6f  lea     rdx, [rbp+57h+var_A0]
0x180049b73  lea     rcx, [rbp+57h+var_58]
0x180049b77  call    ??$_To_absolute_time@_JU?$ratio@$00$0DOI@@std@@@std@@YA?A_PAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@0@@Z
0x180049b7c  mov     r8, rax
0x180049b7f  lea     rdx, [rbp+57h+var_70]
0x180049b83  lea     rcx, [rdi+150h]
0x180049b8a  call    ??$wait_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@condition_variable@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vmutex@std@@@1@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z; std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::unique_lock<std::mutex> &,std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)
0x180049b8f  cmp     eax, 1
0x180049b92  jnz     loc_180049FC1
0x180049b98  mov     rsi, [rdi+0D0h]
0x180049b9f  test    rsi, rsi
0x180049ba2  jz      loc_180049D9C
0x180049ba8  mov     rsi, [rsi+118h]
0x180049baf  mov     [rbp+57h+var_98], rsi
0x180049bb3  test    rsi, rsi
0x180049bb6  jz      short loc_180049BD4
0x180049bb8  mov     rax, [rsi+8]
0x180049bbc  movsxd  rcx, dword ptr [rax+4]
0x180049bc0  add     rcx, 8
0x180049bc4  add     rcx, rsi
0x180049bc7  mov     rax, [rcx]
0x180049bca  mov     rax, [rax+8]
0x180049bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bd3  nop
0x180049bd4  test    rsi, rsi
0x180049bd7  jz      loc_180049D73
0x180049bdd  cmp     [rdi+0F0h], r12
0x180049be4  jz      loc_180049D73
0x180049bea  mov     [rbp+57h+var_A0], r12
0x180049bee  lea     rcx, [rbp+57h+var_A0]
0x180049bf2  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180049bf8  mov     eax, dword ptr [rbp+57h+var_A0+4]
0x180049bfb  shl     rax, 20h
0x180049bff  sub     rax, [rdi+1A8h]
0x180049c06  mov     ecx, dword ptr [rbp+57h+var_A0]
0x180049c09  add     rbx, rax
0x180049c0c  add     rbx, rcx
0x180049c0f  lea     rax, [rbx-2BF21h]
0x180049c16  cmp     rax, 2F8315Eh
0x180049c1c  ja      loc_180049D73
0x180049c22  mov     ecx, 0A8h; Size
0x180049c27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049c2c  mov     [rbp+57h+var_50], rax
0x180049c30  mov     r8, rbx; unsigned __int64
0x180049c33  mov     rdx, [rdi+0F0h]; struct Rdp::Avenc::Ic3::CDsStreamSample *
0x180049c3a  mov     rcx, rax; this
0x180049c3d  call    ??0CDsStreamSample@Ic3@Avenc@Rdp@@QEAA@PEBV0123@_K@Z; Rdp::Avenc::Ic3::CDsStreamSample::CDsStreamSample(Rdp::Avenc::Ic3::CDsStreamSample const *,unsigned __int64)
0x180049c42  mov     r15, rax
0x180049c45  test    rax, rax
0x180049c48  jz      short loc_180049C65
0x180049c4a  mov     rcx, [rax+8]
0x180049c4e  movsxd  rcx, dword ptr [rcx+4]
0x180049c52  add     rcx, 8
0x180049c56  add     rcx, rax
0x180049c59  mov     rdx, [rcx]
0x180049c5c  mov     rax, [rdx+8]
0x180049c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c65  mov     eax, cs:dword_1800C1058
0x180049c6b  cmp     eax, 5
0x180049c6e  jbe     loc_180049D1C
0x180049c74  mov     [rbp+57h+var_A0], rbx
0x180049c78  mov     rax, [r15+80h]
0x180049c7f  mov     [rbp+57h+var_88], rax
0x180049c83  mov     rdx, [rdi+0B0h]
0x180049c8a  mov     rax, [rdx+68h]
0x180049c8e  mov     ecx, [rax+88h]
0x180049c94  mov     [rbp+57h+arg_0], ecx
0x180049c97  mov     eax, [rdx+80h]
0x180049c9d  mov     [rbp+57h+arg_8], eax
0x180049ca0  mov     [rbp+57h+var_80], r13
0x180049ca4  lea     rax, aRdpAvencIc3Cic_6; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x180049cab  mov     [rbp+57h+var_78], rax
0x180049caf  mov     [rbp+57h+arg_10], 2A0h
0x180049cb6  lea     rax, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180049cbd  mov     [rbp+57h+var_98], rax
0x180049cc1  lea     rax, [rbp+57h+var_A0]
0x180049cc5  mov     [rsp+100h+var_A8], rax
0x180049cca  lea     rax, [rbp+57h+var_88]
0x180049cce  mov     [rsp+100h+var_B0], rax
0x180049cd3  lea     rax, [rbp+57h+arg_0]
0x180049cd7  mov     [rsp+100h+var_B8], rax
0x180049cdc  lea     rax, [rbp+57h+arg_8]
0x180049ce0  mov     [rsp+100h+var_C0], rax
0x180049ce5  lea     rax, [rbp+57h+var_80]
0x180049ce9  mov     [rsp+100h+var_C8], rax
0x180049cee  lea     rax, [rbp+57h+var_78]
0x180049cf2  mov     [rsp+100h+var_D0], rax
0x180049cf7  lea     rax, [rbp+57h+arg_10]
0x180049cfb  mov     [rsp+100h+var_D8], rax
0x180049d00  lea     rax, [rbp+57h+var_98]
0x180049d04  mov     [rsp+100h+var_E0], rax
0x180049d09  lea     rdx, byte_1800B0BA3
0x180049d10  lea     rcx, dword_1800C1058
0x180049d17  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180049d1c  mov     r8, [r15+88h]
0x180049d23  mov     rdx, [r15+80h]
0x180049d2a  mov     rcx, rdi
0x180049d2d  call    ?CheckFirstFrameAndRaiseEvent@?$CIc3FrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@UIGpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAA_N_K0@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(unsigned __int64,unsigned __int64)
0x180049d32  mov     bl, al
0x180049d34  mov     rdx, r15; struct Rdp::Avenc::Ic3::CDsStreamSample *
0x180049d37  mov     rcx, rsi; this
0x180049d3a  call    ?ProcessFrame@CDsSourceStreamProcessingSession@Ic3@Avenc@Rdp@@QEAAJPEAVCDsStreamSample@234@@Z; Rdp::Avenc::Ic3::CDsSourceStreamProcessingSession::ProcessFrame(Rdp::Avenc::Ic3::CDsStreamSample *)
0x180049d3f  test    bl, bl
0x180049d41  jz      short loc_180049D55
0x180049d43  mov     r8b, 1
0x180049d46  mov     rdx, [r15+80h]
0x180049d4d  mov     rcx, rdi
0x180049d50  call    ?RaiseFirstFrameDoneEvent@?$CIc3FrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@UIGpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAX_K_N@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::RaiseFirstFrameDoneEvent(unsigned __int64,bool)
0x180049d55  mov     rax, [r15+8]
0x180049d59  movsxd  rcx, dword ptr [rax+4]
0x180049d5d  add     rcx, 8
0x180049d61  add     rcx, r15
0x180049d64  mov     rax, [rcx]
0x180049d67  mov     rax, [rax+10h]
0x180049d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d70  xor     r12d, r12d
0x180049d73  test    rsi, rsi
0x180049d76  jz      loc_180049FC1
0x180049d7c  mov     rax, [rsi+8]
0x180049d80  movsxd  rcx, dword ptr [rax+4]
0x180049d84  add     rcx, 8
0x180049d88  add     rcx, rsi
0x180049d8b  mov     rax, [rcx]
0x180049d8e  mov     rax, [rax+10h]
0x180049d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d97  jmp     loc_180049FC1
0x180049d9c  mov     rcx, [rdi+0D8h]; this
0x180049da3  test    rcx, rcx
0x180049da6  jz      loc_180049FC1
0x180049dac  call    ?GetSink@CVideoSourceProvider@Ic3@Avenc@Rdp@@QEAAPEAVIVirtualVideoSink@@XZ; Rdp::Avenc::Ic3::CVideoSourceProvider::GetSink(void)
0x180049db1  mov     r15, rax
0x180049db4  test    rax, rax
0x180049db7  jz      loc_180049FC1
0x180049dbd  cmp     [rdi+0F8h], r12
0x180049dc4  jz      loc_180049FC1
0x180049dca  mov     [rbp+57h+var_A0], r12
0x180049dce  lea     rcx, [rbp+57h+var_A0]
0x180049dd2  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180049dd8  mov     r13d, dword ptr [rbp+57h+var_A0+4]
0x180049ddc  shl     r13, 20h
0x180049de0  sub     r13, [rdi+1A8h]
0x180049de7  mov     ecx, dword ptr [rbp+57h+var_A0]
0x180049dea  add     r13, rbx
0x180049ded  add     r13, rcx
0x180049df0  lea     rax, [r13-2BF21h]
0x180049df7  cmp     rax, 2F8315Eh
0x180049dfd  ja      loc_180049FBA
0x180049e03  mov     ecx, 0D0h; Size
0x180049e08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049e0d  mov     [rbp+57h+var_48], rax
0x180049e11  lea     rdx, [rdi+0F8h]
0x180049e18  mov     r8, r13
0x180049e1b  mov     rcx, rax
0x180049e1e  call    ??0CVirtualFrame@Ic3@Avenc@Rdp@@QEAA@AEBV?$com_ptr_t@VCVirtualFrame@Ic3@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@_K@Z; Rdp::Avenc::Ic3::CVirtualFrame::CVirtualFrame(wil::com_ptr_t<Rdp::Avenc::Ic3::CVirtualFrame,wil::err_exception_policy> const &,unsigned __int64)
0x180049e23  mov     rsi, rax
0x180049e26  mov     [rbp+57h+var_A0], rax
0x180049e2a  test    rax, rax
0x180049e2d  jz      short loc_180049E3E
0x180049e2f  mov     rcx, [rax]
0x180049e32  mov     rax, [rcx]
0x180049e35  mov     rcx, rsi
0x180049e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e3d  nop
0x180049e3e  mov     rax, [r15]
0x180049e41  mov     rcx, r15
0x180049e44  mov     rax, [rax+10h]
0x180049e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e4d  sub     rax, [rsi+0C8h]
0x180049e54  mov     [rsi+0C0h], rax
0x180049e5b  mov     rax, [rsi]
0x180049e5e  mov     rcx, rsi
0x180049e61  mov     rax, [rax+40h]
0x180049e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e6a  mov     rbx, rax
0x180049e6d  mov     rcx, [rsi+10h]
0x180049e71  mov     rcx, [rcx]
0x180049e74  mov     rdx, [rcx]
0x180049e77  mov     rax, [rdx+0C8h]
0x180049e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e83  mov     rdx, [rsi+50h]
0x180049e87  add     rdx, rax
0x180049e8a  mov     r8, rbx
0x180049e8d  mov     rcx, rdi
0x180049e90  call    ?CheckFirstFrameAndRaiseEvent@?$CIc3FrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@UIGpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAA_N_K0@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CheckFirstFrameAndRaiseEvent(unsigned __int64,unsigned __int64)
0x180049e95  mov     bl, al
0x180049e97  mov     ecx, cs:dword_1800C1058
0x180049e9d  cmp     ecx, 5
0x180049ea0  jbe     loc_180049F5F
0x180049ea6  mov     [rbp+57h+var_98], r13
0x180049eaa  mov     rcx, [rsi]
0x180049ead  mov     rax, [rcx+40h]
0x180049eb1  mov     rcx, rsi
0x180049eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049eb9  mov     [rbp+57h+var_60], rax
0x180049ebd  mov     rdx, [rdi+0B0h]
0x180049ec4  mov     rax, [rdx+68h]
0x180049ec8  mov     ecx, [rax+88h]
0x180049ece  mov     [rbp+57h+arg_18], ecx
0x180049ed1  mov     eax, [rdx+80h]
0x180049ed7  mov     [rbp+57h+var_90], eax
0x180049eda  lea     r13, aRepeatframe; "RepeatFrame"
0x180049ee1  mov     [rbp+57h+var_78], r13
0x180049ee5  lea     rax, aRdpAvencIc3Cic_6; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x180049eec  mov     [rbp+57h+var_80], rax
0x180049ef0  mov     [rbp+57h+var_8C], 2C8h
0x180049ef7  lea     rax, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180049efe  mov     [rbp+57h+var_88], rax
0x180049f02  lea     rax, [rbp+57h+var_98]
0x180049f06  mov     [rsp+100h+var_A8], rax
0x180049f0b  lea     rax, [rbp+57h+var_60]
0x180049f0f  mov     [rsp+100h+var_B0], rax
0x180049f14  lea     rax, [rbp+57h+arg_18]
0x180049f18  mov     [rsp+100h+var_B8], rax
0x180049f1d  lea     rax, [rbp+57h+var_90]
0x180049f21  mov     [rsp+100h+var_C0], rax
0x180049f26  lea     rax, [rbp+57h+var_78]
0x180049f2a  mov     [rsp+100h+var_C8], rax
0x180049f2f  lea     rax, [rbp+57h+var_80]
0x180049f33  mov     [rsp+100h+var_D0], rax
0x180049f38  lea     rax, [rbp+57h+var_8C]
0x180049f3c  mov     [rsp+100h+var_D8], rax
0x180049f41  lea     rax, [rbp+57h+var_88]
0x180049f45  mov     [rsp+100h+var_E0], rax
0x180049f4a  lea     rdx, word_1800B0B36
0x180049f51  lea     rcx, dword_1800C1058
0x180049f58  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180049f5d  jmp     short loc_180049F66
0x180049f5f  lea     r13, aRepeatframe; "RepeatFrame"
0x180049f66  mov     rax, [r15]
0x180049f69  mov     rdx, rsi
0x180049f6c  mov     rcx, r15
0x180049f6f  mov     rax, [rax+80h]
0x180049f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f7b  test    bl, bl
0x180049f7d  jz      short loc_180049FA8
0x180049f7f  mov     rax, [rsi+10h]
0x180049f83  mov     rcx, [rax]
0x180049f86  mov     rax, [rcx]
0x180049f89  mov     rax, [rax+0C8h]
0x180049f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f95  mov     rdx, [rsi+50h]
0x180049f99  add     rdx, rax
0x180049f9c  mov     r8b, 1
0x180049f9f  mov     rcx, rdi
0x180049fa2  call    ?RaiseFirstFrameDoneEvent@?$CIc3FrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@UIGpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAX_K_N@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::RaiseFirstFrameDoneEvent(unsigned __int64,bool)
0x180049fa7  nop
0x180049fa8  mov     rax, [rsi]
0x180049fab  mov     rcx, rsi
0x180049fae  mov     rax, [rax+8]
0x180049fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049fb7  nop
0x180049fb8  jmp     short loc_180049FC1
0x180049fba  lea     r13, aRepeatframe; "RepeatFrame"
0x180049fc1  cmp     [rdi+1B0h], r12b
0x180049fc8  mov     rbx, 0FE624E212AC18000h
0x180049fd2  jz      loc_180049B67
0x180049fd8  mov     r14, [rbp+57h+var_70]
0x180049fdc  sub     dword ptr [r14+4Ch], 1
0x180049fe1  jnz     short loc_180049FF5
0x180049fe3  mov     dword ptr [r14+48h], 0FFFFFFFFh
0x180049feb  lea     rcx, [r14+10h]; SRWLock
0x180049fef  call    cs:__imp_ReleaseSRWLockExclusive
0x180049ff5  add     rsp, 0C8h
0x180049ffc  pop     r15
0x180049ffe  pop     r14
0x18004a000  pop     r13
0x18004a002  pop     r12
0x18004a004  pop     rdi
0x18004a005  pop     rsi
0x18004a006  pop     rbx
0x18004a007  pop     rbp
0x18004a008  retn
  ... truncated ...
```
