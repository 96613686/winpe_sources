# CWMPropHandlerBase::SelectDesiredStreams(IMFPresentationDescriptor *)

- ea: `0x180045b00`
- end: `0x1800461a7`
- name: `?SelectDesiredStreams@CWMPropHandlerBase@@MEAAJPEAUIMFPresentationDescriptor@@@Z`
- size: `1703`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFPresentationDescriptor *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001e80`
- `0x180016b18`
- `0x180017e64`
- `0x180020398`
- `0x180020484`
- `0x18002a100`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x1800453c8`
- `0x180045b00`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045b92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045cec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045d92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045df9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045ed8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045fb7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046046`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800460d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045b92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045cec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045d92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045df9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045ed8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045fb7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046046`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800460d5`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::SelectDesiredStreams(
        CWMPropHandlerBase *this,
        struct IMFPresentationDescriptor *a2)
{
  struct IMFPresentationDescriptorVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetStreamDescriptorCount)(IMFPresentationDescriptor *, DWORD *); // rax
  __int64 v6; // rdx
  int StreamMajorType; // ebx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  int v12; // r12d
  int v13; // r13d
  unsigned int i; // esi
  __int64 v15; // rdx
  __int64 v16; // rdx
  struct IMFPresentationDescriptorVtbl *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  bool v22; // zf
  struct IMFPresentationDescriptorVtbl *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  __int64 v28; // rdx
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v47[4]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v48; // [rsp+34h] [rbp-2Ch] BYREF
  struct IUnknown *v49; // [rsp+38h] [rbp-28h] BYREF
  int v50; // [rsp+40h] [rbp-20h] BYREF
  GUID Buf2; // [rsp+48h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v47, "CWMPropHandlerBase::SelectDesiredStreams", 1137);
  lpVtbl = a2->lpVtbl;
  v48 = 0;
  v49 = 0;
  GetStreamDescriptorCount = lpVtbl->GetStreamDescriptorCount;
  Buf2 = GUID_00000000_0000_0000_0000_000000000000;
  v50 = 0;
  StreamMajorType = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, unsigned int *))GetStreamDescriptorCount)(
                      a2,
                      &v48);
  if ( StreamMajorType >= 0 )
  {
    v12 = 0;
    v13 = 0;
    for ( i = 0; i < v48; ++i )
    {
      if ( v49 )
        ATL::AtlComPtrAssign(&v49, 0);
      StreamMajorType = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD, int *, struct IUnknown **))a2->lpVtbl->GetStreamDescriptorByIndex)(
                          a2,
                          i,
                          &v50,
                          &v49);
      if ( StreamMajorType < 0 )
      {
        v43 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v43 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v43 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != StreamMajorType )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CWMPropHandlerBase::SelectDesiredStreams",
              1159,
              StreamMajorType);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 96;
          goto LABEL_100;
        }
        break;
      }
      StreamMajorType = CWMPropHandlerBase::GetStreamMajorType(this, (struct IMFStreamDescriptor *)v49, &Buf2);
      if ( StreamMajorType < 0 )
      {
        v40 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
          CallStackTracing::s_wpInstance = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v40 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)v42 + 499) != StreamMajorType )
            CallStackContext::TraceFailure(v42, "CWMPropHandlerBase::SelectDesiredStreams", 1161, StreamMajorType);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 97;
          goto LABEL_100;
        }
        break;
      }
      if ( !memcmp_0(&MFMediaType_Audio, &Buf2, 0x10u) )
      {
        v17 = a2->lpVtbl;
        if ( v12 )
        {
          StreamMajorType = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD))v17->DeselectStream)(
                              a2,
                              i);
          if ( StreamMajorType < 0 )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
              CallStackTracing::s_wpInstance = v21;
              if ( v21
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
              {
                v20 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v20 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v20 + 8) )
            {
              v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
              if ( *((_DWORD *)v32 + 499) != StreamMajorType )
                CallStackContext::TraceFailure(v32, "CWMPropHandlerBase::SelectDesiredStreams", 1172, StreamMajorType);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v11 = 99;
              goto LABEL_100;
            }
            break;
          }
        }
        else
        {
          StreamMajorType = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD))v17->SelectStream)(
                              a2,
                              i);
          if ( StreamMajorType < 0 )
          {
            v29 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
              CallStackTracing::s_wpInstance = v30;
              if ( v30
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
              {
                v29 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v29 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v29 + 8) )
            {
              v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
              if ( *((_DWORD *)v31 + 499) != StreamMajorType )
                CallStackContext::TraceFailure(v31, "CWMPropHandlerBase::SelectDesiredStreams", 1167, StreamMajorType);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v11 = 98;
              goto LABEL_100;
            }
            break;
          }
          v12 = 1;
        }
      }
      else
      {
        v22 = memcmp_0(&MFMediaType_Video, &Buf2, 0x10u) == 0;
        v23 = a2->lpVtbl;
        if ( v22 )
        {
          if ( v13 )
          {
            StreamMajorType = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD))v23->DeselectStream)(
                                a2,
                                i);
            if ( StreamMajorType < 0 )
            {
              v26 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
                CallStackTracing::s_wpInstance = v27;
                if ( v27
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
                {
                  v26 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v26 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v26 + 8) )
              {
                v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
                if ( *((_DWORD *)v36 + 499) != StreamMajorType )
                  CallStackContext::TraceFailure(v36, "CWMPropHandlerBase::SelectDesiredStreams", 1184, StreamMajorType);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v11 = 101;
                goto LABEL_100;
              }
              break;
            }
          }
          else
          {
            StreamMajorType = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD))v23->SelectStream)(
                                a2,
                                i);
            if ( StreamMajorType < 0 )
            {
              v33 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
                CallStackTracing::s_wpInstance = v34;
                if ( v34
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
                {
                  v33 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v33 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v33 + 8) )
              {
                v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
                if ( *((_DWORD *)v35 + 499) != StreamMajorType )
                  CallStackContext::TraceFailure(v35, "CWMPropHandlerBase::SelectDesiredStreams", 1179, StreamMajorType);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v11 = 100;
                goto LABEL_100;
              }
              break;
            }
            v13 = 1;
          }
        }
        else
        {
          StreamMajorType = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, _QWORD))v23->DeselectStream)(
                              a2,
                              i);
          if ( StreamMajorType < 0 )
          {
            v37 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
              CallStackTracing::s_wpInstance = v38;
              if ( v38
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
              {
                v37 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v37 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v37 + 8) )
            {
              v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
              if ( *((_DWORD *)v39 + 499) != StreamMajorType )
                CallStackContext::TraceFailure(v39, "CWMPropHandlerBase::SelectDesiredStreams", 1192, StreamMajorType);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v11 = 102;
              goto LABEL_100;
            }
            break;
          }
        }
      }
    }
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v10 + 499) != StreamMajorType )
        CallStackContext::TraceFailure(v10, "CWMPropHandlerBase::SelectDesiredStreams", 1148, StreamMajorType);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 95;
LABEL_100:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_d497573e8d0434bb74893564de0342d6_Traceguids,
        this,
        StreamMajorType);
    }
  }
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v49);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v47);
  return (unsigned int)StreamMajorType;
}

```

## disassembly

```asm
0x180045b00  mov     [rsp-28h+arg_10], rbx
0x180045b05  mov     [rsp-28h+arg_18], rsi
0x180045b0a  push    rbp
0x180045b0b  push    r12
0x180045b0d  push    r13
0x180045b0f  push    r14
0x180045b11  push    r15
0x180045b13  mov     rbp, rsp
0x180045b16  sub     rsp, 60h
0x180045b1a  mov     rax, cs:__security_cookie
0x180045b21  xor     rax, rsp
0x180045b24  mov     [rbp+var_8], rax
0x180045b28  mov     r14, rdx
0x180045b2b  mov     r15, rcx
0x180045b2e  lea     rdx, aCwmprophandler_5; "CWMPropHandlerBase::SelectDesiredStream"...
0x180045b35  mov     r8d, 471h; int
0x180045b3b  lea     rcx, [rbp+var_30]; this
0x180045b3f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180045b44  mov     rax, [r14]
0x180045b47  lea     rdx, [rbp+var_2C]
0x180045b4b  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180045b52  mov     rcx, r14
0x180045b55  mov     [rbp+var_2C], 0
0x180045b5c  mov     [rbp+var_28], 0
0x180045b64  mov     rax, [rax+108h]
0x180045b6b  movdqu  [rbp+Buf2], xmm0
0x180045b70  mov     [rbp+var_20], 0
0x180045b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b7c  mov     ebx, eax
0x180045b7e  test    eax, eax
0x180045b80  jns     loc_180045C15
0x180045b86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045b8d  test    rcx, rcx
0x180045b90  jnz     short loc_180045BD3
0x180045b92  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045b98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045b9f  mov     rcx, rax
0x180045ba2  test    rax, rax
0x180045ba5  jz      short loc_180045BC5
0x180045ba7  mov     rax, [rax]
0x180045baa  mov     edx, 7F0h
0x180045baf  mov     rax, [rax+8]
0x180045bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bb8  test    eax, eax
0x180045bba  jz      short loc_180045BC5
0x180045bbc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045bc3  jmp     short loc_180045BD3
0x180045bc5  lea     rcx, qword_18006EB20; this
0x180045bcc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045bd3  cmp     byte ptr [rcx+8], 0
0x180045bd7  jz      short loc_180045BFE
0x180045bd9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045bde  cmp     [rax+7CCh], ebx
0x180045be4  jz      short loc_180045BFE
0x180045be6  mov     r9d, ebx; int
0x180045be9  lea     rdx, aCwmprophandler_5; "CWMPropHandlerBase::SelectDesiredStream"...
0x180045bf0  mov     r8d, 47Ch; int
0x180045bf6  mov     rcx, rax; this
0x180045bf9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045bfe  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045c03  cmp     al, 1
0x180045c05  jb      loc_18004616D
0x180045c0b  mov     edx, 5Fh ; '_'
0x180045c10  jmp     loc_18004614F
0x180045c15  xor     r12d, r12d
0x180045c18  xor     r13d, r13d
0x180045c1b  xor     esi, esi
0x180045c1d  cmp     esi, [rbp+var_2C]
0x180045c20  jnb     loc_18004616D
0x180045c26  cmp     [rbp+var_28], 0
0x180045c2b  jz      short loc_180045C38
0x180045c2d  xor     edx, edx; struct IUnknown *
0x180045c2f  lea     rcx, [rbp+var_28]; struct IUnknown **
0x180045c33  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180045c38  mov     rax, [r14]
0x180045c3b  lea     r9, [rbp+var_28]
0x180045c3f  lea     r8, [rbp+var_20]
0x180045c43  mov     edx, esi
0x180045c45  mov     rcx, r14
0x180045c48  mov     rax, [rax+110h]
0x180045c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c54  mov     ebx, eax
0x180045c56  test    eax, eax
0x180045c58  js      loc_1800460C9
0x180045c5e  mov     rdx, [rbp+var_28]; struct IMFStreamDescriptor *
0x180045c62  lea     r8, [rbp+Buf2]; struct _GUID *
0x180045c66  mov     rcx, r15; this
0x180045c69  call    ?GetStreamMajorType@CWMPropHandlerBase@@IEAAJPEAUIMFStreamDescriptor@@PEAU_GUID@@@Z; CWMPropHandlerBase::GetStreamMajorType(IMFStreamDescriptor *,_GUID *)
0x180045c6e  mov     ebx, eax
0x180045c70  test    eax, eax
0x180045c72  js      loc_18004603A
0x180045c78  mov     ebx, 10h
0x180045c7d  lea     rdx, [rbp+Buf2]; Buf2
0x180045c81  mov     r8d, ebx; Size
0x180045c84  lea     rcx, MFMediaType_Audio; Buf1
0x180045c8b  call    memcmp_0
0x180045c90  test    eax, eax
0x180045c92  jnz     loc_180045D2A
0x180045c98  mov     rax, [r14]
0x180045c9b  mov     edx, esi
0x180045c9d  mov     rcx, r14
0x180045ca0  test    r12d, r12d
0x180045ca3  jnz     short loc_180045CC6
0x180045ca5  mov     rax, [rax+118h]
0x180045cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cb1  mov     ebx, eax
0x180045cb3  test    eax, eax
0x180045cb5  js      loc_180045DED
0x180045cbb  mov     r12d, 1
0x180045cc1  jmp     loc_180045DE6
0x180045cc6  mov     rax, [rax+120h]
0x180045ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045cd2  mov     ebx, eax
0x180045cd4  test    eax, eax
0x180045cd6  jns     loc_180045DE6
0x180045cdc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045ce3  test    rcx, rcx
0x180045ce6  jnz     loc_180045E8A
0x180045cec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045cf2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045cf9  mov     rcx, rax
0x180045cfc  test    rax, rax
0x180045cff  jz      loc_180045E7C
0x180045d05  mov     rax, [rax]
0x180045d08  mov     edx, 7F0h
0x180045d0d  mov     rax, [rax+8]
0x180045d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d16  test    eax, eax
0x180045d18  jz      loc_180045E7C
0x180045d1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d25  jmp     loc_180045E8A
0x180045d2a  mov     r8, rbx; Size
0x180045d2d  lea     rdx, [rbp+Buf2]; Buf2
0x180045d31  lea     rcx, MFMediaType_Video; Buf1
0x180045d38  call    memcmp_0
0x180045d3d  test    eax, eax
0x180045d3f  mov     edx, esi
0x180045d41  mov     rax, [r14]
0x180045d44  mov     rcx, r14
0x180045d47  jnz     loc_180045DD0
0x180045d4d  test    r13d, r13d
0x180045d50  jnz     short loc_180045D70
0x180045d52  mov     rax, [rax+118h]
0x180045d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d5e  mov     ebx, eax
0x180045d60  test    eax, eax
0x180045d62  js      loc_180045ECC
0x180045d68  mov     r13d, 1
0x180045d6e  jmp     short loc_180045DE6
0x180045d70  mov     rax, [rax+120h]
0x180045d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d7c  mov     ebx, eax
0x180045d7e  test    eax, eax
0x180045d80  jns     short loc_180045DE6
0x180045d82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d89  test    rcx, rcx
0x180045d8c  jnz     loc_180045F69
0x180045d92  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045d98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045d9f  mov     rcx, rax
0x180045da2  test    rax, rax
0x180045da5  jz      loc_180045F5B
0x180045dab  mov     rax, [rax]
0x180045dae  mov     edx, 7F0h
0x180045db3  mov     rax, [rax+8]
0x180045db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045dbc  test    eax, eax
0x180045dbe  jz      loc_180045F5B
0x180045dc4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045dcb  jmp     loc_180045F69
0x180045dd0  mov     rax, [rax+120h]
0x180045dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ddc  mov     ebx, eax
0x180045dde  test    eax, eax
0x180045de0  js      loc_180045FAB
0x180045de6  inc     esi
0x180045de8  jmp     loc_180045C1D
0x180045ded  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045df4  test    rcx, rcx
0x180045df7  jnz     short loc_180045E3A
0x180045df9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045dff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e06  mov     rcx, rax
0x180045e09  test    rax, rax
0x180045e0c  jz      short loc_180045E2C
0x180045e0e  mov     rax, [rax]
0x180045e11  mov     edx, 7F0h
0x180045e16  mov     rax, [rax+8]
0x180045e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e1f  test    eax, eax
0x180045e21  jz      short loc_180045E2C
0x180045e23  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e2a  jmp     short loc_180045E3A
0x180045e2c  lea     rcx, qword_18006EB20; this
0x180045e33  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e3a  cmp     byte ptr [rcx+8], 0
0x180045e3e  jz      short loc_180045E65
0x180045e40  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045e45  cmp     [rax+7CCh], ebx
0x180045e4b  jz      short loc_180045E65
0x180045e4d  mov     r9d, ebx; int
0x180045e50  lea     rdx, aCwmprophandler_5; "CWMPropHandlerBase::SelectDesiredStream"...
0x180045e57  mov     r8d, 48Fh; int
0x180045e5d  mov     rcx, rax; this
0x180045e60  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045e65  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045e6a  cmp     al, 1
0x180045e6c  jb      loc_18004616D
0x180045e72  mov     edx, 62h ; 'b'
0x180045e77  jmp     loc_18004614F
0x180045e7c  lea     rcx, qword_18006EB20; this
0x180045e83  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045e8a  cmp     byte ptr [rcx+8], 0
0x180045e8e  jz      short loc_180045EB5
0x180045e90  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045e95  cmp     [rax+7CCh], ebx
0x180045e9b  jz      short loc_180045EB5
0x180045e9d  mov     r9d, ebx; int
0x180045ea0  lea     rdx, aCwmprophandler_5; "CWMPropHandlerBase::SelectDesiredStream"...
0x180045ea7  mov     r8d, 494h; int
0x180045ead  mov     rcx, rax; this
0x180045eb0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045eb5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045eba  cmp     al, 1
0x180045ebc  jb      loc_18004616D
0x180045ec2  mov     edx, 63h ; 'c'
0x180045ec7  jmp     loc_18004614F
0x180045ecc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045ed3  test    rcx, rcx
0x180045ed6  jnz     short loc_180045F19
0x180045ed8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045ede  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045ee5  mov     rcx, rax
0x180045ee8  test    rax, rax
0x180045eeb  jz      short loc_180045F0B
0x180045eed  mov     rax, [rax]
0x180045ef0  mov     edx, 7F0h
0x180045ef5  mov     rax, [rax+8]
0x180045ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045efe  test    eax, eax
0x180045f00  jz      short loc_180045F0B
0x180045f02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045f09  jmp     short loc_180045F19
0x180045f0b  lea     rcx, qword_18006EB20; this
0x180045f12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045f19  cmp     byte ptr [rcx+8], 0
0x180045f1d  jz      short loc_180045F44
0x180045f1f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045f24  cmp     [rax+7CCh], ebx
0x180045f2a  jz      short loc_180045F44
0x180045f2c  mov     r9d, ebx; int
0x180045f2f  lea     rdx, aCwmprophandler_5; "CWMPropHandlerBase::SelectDesiredStream"...
0x180045f36  mov     r8d, 49Bh; int
0x180045f3c  mov     rcx, rax; this
0x180045f3f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045f44  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045f49  cmp     al, 1
0x180045f4b  jb      loc_18004616D
0x180045f51  mov     edx, 64h ; 'd'
0x180045f56  jmp     loc_18004614F
0x180045f5b  lea     rcx, qword_18006EB20; this
0x180045f62  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045f69  cmp     byte ptr [rcx+8], 0
0x180045f6d  jz      short loc_180045F94
0x180045f6f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045f74  cmp     [rax+7CCh], ebx
0x180045f7a  jz      short loc_180045F94
0x180045f7c  mov     r9d, ebx; int
0x180045f7f  lea     rdx, aCwmprophandler_5; "CWMPropHandlerBase::SelectDesiredStream"...
0x180045f86  mov     r8d, 4A0h; int
0x180045f8c  mov     rcx, rax; this
0x180045f8f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045f94  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045f99  cmp     al, 1
0x180045f9b  jb      loc_18004616D
0x180045fa1  mov     edx, 65h ; 'e'
0x180045fa6  jmp     loc_18004614F
0x180045fab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045fb2  test    rcx, rcx
0x180045fb5  jnz     short loc_180045FF8
0x180045fb7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045fbd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045fc4  mov     rcx, rax
0x180045fc7  test    rax, rax
0x180045fca  jz      short loc_180045FEA
0x180045fcc  mov     rax, [rax]
0x180045fcf  mov     edx, 7F0h
0x180045fd4  mov     rax, [rax+8]
0x180045fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fdd  test    eax, eax
0x180045fdf  jz      short loc_180045FEA
0x180045fe1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045fe8  jmp     short loc_180045FF8
0x180045fea  lea     rcx, qword_18006EB20; this
0x180045ff1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045ff8  cmp     byte ptr [rcx+8], 0
0x180045ffc  jz      short loc_180046023
0x180045ffe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046003  cmp     [rax+7CCh], ebx
0x180046009  jz      short loc_180046023
  ... truncated ...
```
