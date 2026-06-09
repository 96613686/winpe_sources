# MkvMfSourceLib::MkvMfStreamAudioFLAC::OnDiscontinuity(void)

- ea: `0x180030570`
- end: `0x180030be7`
- name: `?OnDiscontinuity@MkvMfStreamAudioFLAC@MkvMfSourceLib@@MEAAJXZ`
- size: `1655`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStreamAudioFLAC *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003705`
- `0x180005c68`
- `0x180009b04`
- `0x180021f8c`
- `0x18002230c`
- `0x180024a5c`
- `0x180025090`
- `0x180030570`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800305c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003066d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003071f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800307b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030853`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800308ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030983`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030a17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030aad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030b3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800305c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003066d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003071f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800307b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030853`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800308ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030983`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030a17`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030aad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030b3c`
- `MFPlat!MFCreateSample` at `0x180030794`
- `MFPlat!MFCreateSample` at `0x180030794`
- `MFPlat!MFCreateMemoryBuffer` at `0x18003059f`
- `MFPlat!MFCreateMemoryBuffer` at `0x18003059f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfStreamAudioFLAC::OnDiscontinuity(MkvMfSourceLib::MkvMfStreamAudioFLAC *this)
{
  __int64 v2; // rax
  size_t v3; // rdi
  const void *v4; // r14
  __int64 v5; // rdx
  HRESULT v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v18; // r8d
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  int v30; // r8d
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  _BYTE v62[16]; // [rsp+20h] [rbp-20h] BYREF
  void *v63; // [rsp+30h] [rbp-10h]
  IMFSample *ppIMFSample; // [rsp+70h] [rbp+30h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+78h] [rbp+38h] BYREF

  v2 = *((_QWORD *)this + 9);
  v3 = *(_QWORD *)(v2 + 112);
  v4 = *(const void **)(v2 + 104);
  ppBuffer = 0;
  v6 = MFCreateMemoryBuffer(v3, &ppBuffer);
  if ( v6 >= 0 )
  {
    CSmartMFBufferLock::CSmartMFBufferLock((CSmartMFBufferLock *)v62, ppBuffer);
    v6 = CSmartMFBufferLock::Lock((CSmartMFBufferLock *)v62);
    if ( v6 < 0 )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( !*((_BYTE *)v15 + 8) )
        goto LABEL_95;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == v6 )
        goto LABEL_95;
      v18 = 545;
      goto LABEL_19;
    }
    memcpy_0(v63, v4, v3);
    v6 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
           ppBuffer,
           (unsigned int)v3);
    if ( v6 < 0 )
    {
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( !*((_BYTE *)v22 + 8) )
        goto LABEL_95;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == v6 )
        goto LABEL_95;
      v18 = 549;
LABEL_19:
      CallStackContext::TraceFailure(
        ThreadRelativeContext,
        "MkvMfSourceLib::MkvMfStreamAudioFLAC::OnDiscontinuity",
        v18,
        v6);
LABEL_95:
      CSmartMFBufferLock::~CSmartMFBufferLock((CSmartMFBufferLock *)v62);
      goto LABEL_96;
    }
    ppIMFSample = 0;
    v6 = MFCreateSample(&ppIMFSample);
    if ( v6 >= 0 )
    {
      v6 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
             ppIMFSample,
             &MFSampleExtension_CleanPoint,
             1);
      if ( v6 >= 0 )
      {
        v6 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
               ppIMFSample,
               &MFSampleExtension_Discontinuity,
               1);
        if ( v6 >= 0 )
        {
          v6 = ((__int64 (__fastcall *)(IMFSample *, _QWORD))ppIMFSample->lpVtbl->SetSampleTime)(ppIMFSample, 0);
          if ( v6 >= 0 )
          {
            v6 = ((__int64 (__fastcall *)(IMFSample *, _QWORD))ppIMFSample->lpVtbl->SetSampleDuration)(ppIMFSample, 0);
            if ( v6 >= 0 )
            {
              v6 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
                     ppIMFSample,
                     ppBuffer);
              if ( v6 >= 0 )
              {
                v6 = MkvMfSourceLib::MkvMfStream::QueueSample(this, ppIMFSample);
                if ( v6 >= 0 )
                {
                  v6 = 0;
                  goto LABEL_94;
                }
                v59 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56, v57, v58);
                  CallStackTracing::s_wpInstance = v60;
                  if ( v60
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
                  {
                    v59 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v59 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                  }
                }
                if ( !*((_BYTE *)v59 + 8) )
                  goto LABEL_94;
                v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
                if ( *((_DWORD *)v29 + 499) == v6 )
                  goto LABEL_94;
                v30 = 560;
              }
              else
              {
                v54 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                  CallStackTracing::s_wpInstance = v55;
                  if ( v55
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
                  {
                    v54 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v54 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                  }
                }
                if ( !*((_BYTE *)v54 + 8) )
                  goto LABEL_94;
                v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
                if ( *((_DWORD *)v29 + 499) == v6 )
                  goto LABEL_94;
                v30 = 558;
              }
            }
            else
            {
              v49 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47, v48);
                CallStackTracing::s_wpInstance = v50;
                if ( v50
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
                {
                  v49 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v49 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              if ( !*((_BYTE *)v49 + 8) )
                goto LABEL_94;
              v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
              if ( *((_DWORD *)v29 + 499) == v6 )
                goto LABEL_94;
              v30 = 557;
            }
          }
          else
          {
            v44 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
              CallStackTracing::s_wpInstance = v45;
              if ( v45
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
              {
                v44 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v44 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( !*((_BYTE *)v44 + 8) )
              goto LABEL_94;
            v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
            if ( *((_DWORD *)v29 + 499) == v6 )
              goto LABEL_94;
            v30 = 556;
          }
        }
        else
        {
          v39 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
            CallStackTracing::s_wpInstance = v40;
            if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
            {
              v39 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v39 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( !*((_BYTE *)v39 + 8) )
            goto LABEL_94;
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
          if ( *((_DWORD *)v29 + 499) == v6 )
            goto LABEL_94;
          v30 = 555;
        }
      }
      else
      {
        v34 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( !*((_BYTE *)v34 + 8) )
          goto LABEL_94;
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
        if ( *((_DWORD *)v29 + 499) == v6 )
          goto LABEL_94;
        v30 = 554;
      }
    }
    else
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( !*((_BYTE *)v27 + 8) )
        goto LABEL_94;
      v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
      if ( *((_DWORD *)v29 + 499) == v6 )
        goto LABEL_94;
      v30 = 552;
    }
    CallStackContext::TraceFailure(v29, "MkvMfSourceLib::MkvMfStreamAudioFLAC::OnDiscontinuity", v30, v6);
LABEL_94:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIMFSample);
    goto LABEL_95;
  }
  v9 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v7, v8);
    CallStackTracing::s_wpInstance = v10;
    if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v9 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v9 + 8) )
  {
    v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
    if ( *((_DWORD *)v11 + 499) != v6 )
      CallStackContext::TraceFailure(v11, "MkvMfSourceLib::MkvMfStreamAudioFLAC::OnDiscontinuity", 542, v6);
  }
LABEL_96:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180030570  mov     [rsp-28h+arg_10], rbx
0x180030575  push    rbp
0x180030576  push    rsi
0x180030577  push    rdi
0x180030578  push    r14
0x18003057a  push    r15
0x18003057c  mov     rbp, rsp
0x18003057f  sub     rsp, 40h
0x180030583  mov     rsi, rcx
0x180030586  mov     rax, [rcx+48h]
0x18003058a  mov     rdi, [rax+70h]
0x18003058e  mov     r14, [rax+68h]
0x180030592  xor     r15d, r15d
0x180030595  mov     [rbp+ppBuffer], r15
0x180030599  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x18003059d  mov     ecx, edi; cbMaxLength
0x18003059f  call    cs:__imp_MFCreateMemoryBuffer
0x1800305a6  nop     dword ptr [rax+rax+00h]
0x1800305ab  mov     ebx, eax
0x1800305ad  test    eax, eax
0x1800305af  jns     loc_180030640
0x1800305b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800305bc  test    rcx, rcx
0x1800305bf  jnz     short loc_180030608
0x1800305c1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800305c8  nop     dword ptr [rax+rax+00h]
0x1800305cd  mov     rcx, rax
0x1800305d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800305d7  test    rax, rax
0x1800305da  jz      short loc_1800305FA
0x1800305dc  mov     rax, [rax]
0x1800305df  mov     edx, 7F0h
0x1800305e4  mov     rax, [rax+8]
0x1800305e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305ed  test    eax, eax
0x1800305ef  jz      short loc_1800305FA
0x1800305f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800305f8  jmp     short loc_180030608
0x1800305fa  lea     rcx, qword_1800DBF70; this
0x180030601  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030608  cmp     [rcx+8], r15b
0x18003060c  jz      loc_180030BC7
0x180030612  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030617  cmp     [rax+7CCh], ebx
0x18003061d  jz      loc_180030BC7
0x180030623  mov     r9d, ebx; int
0x180030626  mov     r8d, 21Eh; int
0x18003062c  lea     rdx, aMkvmfsourcelib_94; "MkvMfSourceLib::MkvMfStreamAudioFLAC::O"...
0x180030633  mov     rcx, rax; this
0x180030636  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003063b  jmp     loc_180030BC7
0x180030640  mov     rdx, [rbp+ppBuffer]; struct IMFMediaBuffer *
0x180030644  lea     rcx, [rbp+var_20]; this
0x180030648  call    ??0CSmartMFBufferLock@@QEAA@PEAUIMFMediaBuffer@@@Z; CSmartMFBufferLock::CSmartMFBufferLock(IMFMediaBuffer *)
0x18003064d  nop
0x18003064e  lea     rcx, [rbp+var_20]; this
0x180030652  call    ?Lock@CSmartMFBufferLock@@QEAAJXZ; CSmartMFBufferLock::Lock(void)
0x180030657  mov     ebx, eax
0x180030659  test    eax, eax
0x18003065b  jns     loc_1800306EC
0x180030661  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030668  test    rcx, rcx
0x18003066b  jnz     short loc_1800306B4
0x18003066d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030674  nop     dword ptr [rax+rax+00h]
0x180030679  mov     rcx, rax
0x18003067c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030683  test    rax, rax
0x180030686  jz      short loc_1800306A6
0x180030688  mov     rax, [rax]
0x18003068b  mov     edx, 7F0h
0x180030690  mov     rax, [rax+8]
0x180030694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030699  test    eax, eax
0x18003069b  jz      short loc_1800306A6
0x18003069d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800306a4  jmp     short loc_1800306B4
0x1800306a6  lea     rcx, qword_1800DBF70; this
0x1800306ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800306b4  cmp     [rcx+8], r15b
0x1800306b8  jz      loc_180030BBD
0x1800306be  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800306c3  cmp     [rax+7CCh], ebx
0x1800306c9  jz      loc_180030BBD
0x1800306cf  mov     r8d, 221h; int
0x1800306d5  mov     r9d, ebx; int
0x1800306d8  lea     rdx, aMkvmfsourcelib_94; "MkvMfSourceLib::MkvMfStreamAudioFLAC::O"...
0x1800306df  mov     rcx, rax; this
0x1800306e2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800306e7  jmp     loc_180030BBD
0x1800306ec  mov     r8, rdi; Size
0x1800306ef  mov     rdx, r14; Src
0x1800306f2  mov     rcx, [rbp+var_10]; void *
0x1800306f6  call    memcpy_0
0x1800306fb  mov     rcx, [rbp+ppBuffer]
0x1800306ff  mov     rax, [rcx]
0x180030702  mov     edx, edi
0x180030704  mov     rax, [rax+30h]
0x180030708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003070d  mov     ebx, eax
0x18003070f  test    eax, eax
0x180030711  jns     short loc_18003078C
0x180030713  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003071a  test    rcx, rcx
0x18003071d  jnz     short loc_180030766
0x18003071f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030726  nop     dword ptr [rax+rax+00h]
0x18003072b  mov     rcx, rax
0x18003072e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030735  test    rax, rax
0x180030738  jz      short loc_180030758
0x18003073a  mov     rax, [rax]
0x18003073d  mov     edx, 7F0h
0x180030742  mov     rax, [rax+8]
0x180030746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003074b  test    eax, eax
0x18003074d  jz      short loc_180030758
0x18003074f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030756  jmp     short loc_180030766
0x180030758  lea     rcx, qword_1800DBF70; this
0x18003075f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030766  cmp     [rcx+8], r15b
0x18003076a  jz      loc_180030BBD
0x180030770  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030775  cmp     [rax+7CCh], ebx
0x18003077b  jz      loc_180030BBD
0x180030781  mov     r8d, 225h
0x180030787  jmp     loc_1800306D5
0x18003078c  mov     [rbp+ppIMFSample], r15
0x180030790  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x180030794  call    cs:__imp_MFCreateSample
0x18003079b  nop     dword ptr [rax+rax+00h]
0x1800307a0  mov     ebx, eax
0x1800307a2  test    eax, eax
0x1800307a4  jns     short loc_18003081F
0x1800307a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800307ad  test    rcx, rcx
0x1800307b0  jnz     short loc_1800307F9
0x1800307b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800307b9  nop     dword ptr [rax+rax+00h]
0x1800307be  mov     rcx, rax
0x1800307c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800307c8  test    rax, rax
0x1800307cb  jz      short loc_1800307EB
0x1800307cd  mov     rax, [rax]
0x1800307d0  mov     edx, 7F0h
0x1800307d5  mov     rax, [rax+8]
0x1800307d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307de  test    eax, eax
0x1800307e0  jz      short loc_1800307EB
0x1800307e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800307e9  jmp     short loc_1800307F9
0x1800307eb  lea     rcx, qword_1800DBF70; this
0x1800307f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800307f9  cmp     [rcx+8], r15b
0x1800307fd  jz      loc_180030BB3
0x180030803  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030808  cmp     [rax+7CCh], ebx
0x18003080e  jz      loc_180030BB3
0x180030814  mov     r8d, 228h
0x18003081a  jmp     loc_180030B9C
0x18003081f  mov     rcx, [rbp+ppIMFSample]
0x180030823  mov     rax, [rcx]
0x180030826  mov     edi, 1
0x18003082b  mov     r8d, edi
0x18003082e  lea     rdx, MFSampleExtension_CleanPoint
0x180030835  mov     rax, [rax+0A8h]
0x18003083c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030841  mov     ebx, eax
0x180030843  test    eax, eax
0x180030845  jns     short loc_1800308C0
0x180030847  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003084e  test    rcx, rcx
0x180030851  jnz     short loc_18003089A
0x180030853  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003085a  nop     dword ptr [rax+rax+00h]
0x18003085f  mov     rcx, rax
0x180030862  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030869  test    rax, rax
0x18003086c  jz      short loc_18003088C
0x18003086e  mov     rax, [rax]
0x180030871  mov     edx, 7F0h
0x180030876  mov     rax, [rax+8]
0x18003087a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003087f  test    eax, eax
0x180030881  jz      short loc_18003088C
0x180030883  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003088a  jmp     short loc_18003089A
0x18003088c  lea     rcx, qword_1800DBF70; this
0x180030893  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003089a  cmp     [rcx+8], r15b
0x18003089e  jz      loc_180030BB3
0x1800308a4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800308a9  cmp     [rax+7CCh], ebx
0x1800308af  jz      loc_180030BB3
0x1800308b5  mov     r8d, 22Ah
0x1800308bb  jmp     loc_180030B9C
0x1800308c0  mov     rcx, [rbp+ppIMFSample]
0x1800308c4  mov     rax, [rcx]
0x1800308c7  mov     r8d, edi
0x1800308ca  lea     rdx, MFSampleExtension_Discontinuity
0x1800308d1  mov     rax, [rax+0A8h]
0x1800308d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308dd  mov     ebx, eax
0x1800308df  test    eax, eax
0x1800308e1  jns     short loc_18003095C
0x1800308e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800308ea  test    rcx, rcx
0x1800308ed  jnz     short loc_180030936
0x1800308ef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800308f6  nop     dword ptr [rax+rax+00h]
0x1800308fb  mov     rcx, rax
0x1800308fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030905  test    rax, rax
0x180030908  jz      short loc_180030928
0x18003090a  mov     rax, [rax]
0x18003090d  mov     edx, 7F0h
0x180030912  mov     rax, [rax+8]
0x180030916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003091b  test    eax, eax
0x18003091d  jz      short loc_180030928
0x18003091f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030926  jmp     short loc_180030936
0x180030928  lea     rcx, qword_1800DBF70; this
0x18003092f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030936  cmp     [rcx+8], r15b
0x18003093a  jz      loc_180030BB3
0x180030940  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030945  cmp     [rax+7CCh], ebx
0x18003094b  jz      loc_180030BB3
0x180030951  mov     r8d, 22Bh
0x180030957  jmp     loc_180030B9C
0x18003095c  mov     rcx, [rbp+ppIMFSample]
0x180030960  mov     rax, [rcx]
0x180030963  xor     edx, edx
0x180030965  mov     rax, [rax+120h]
0x18003096c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030971  mov     ebx, eax
0x180030973  test    eax, eax
0x180030975  jns     short loc_1800309F0
0x180030977  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003097e  test    rcx, rcx
0x180030981  jnz     short loc_1800309CA
0x180030983  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003098a  nop     dword ptr [rax+rax+00h]
0x18003098f  mov     rcx, rax
0x180030992  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030999  test    rax, rax
0x18003099c  jz      short loc_1800309BC
0x18003099e  mov     rax, [rax]
0x1800309a1  mov     edx, 7F0h
0x1800309a6  mov     rax, [rax+8]
0x1800309aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309af  test    eax, eax
0x1800309b1  jz      short loc_1800309BC
0x1800309b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800309ba  jmp     short loc_1800309CA
0x1800309bc  lea     rcx, qword_1800DBF70; this
0x1800309c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800309ca  cmp     [rcx+8], r15b
0x1800309ce  jz      loc_180030BB3
0x1800309d4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800309d9  cmp     [rax+7CCh], ebx
0x1800309df  jz      loc_180030BB3
0x1800309e5  mov     r8d, 22Ch
0x1800309eb  jmp     loc_180030B9C
0x1800309f0  mov     rcx, [rbp+ppIMFSample]
0x1800309f4  mov     rax, [rcx]
0x1800309f7  xor     edx, edx
0x1800309f9  mov     rax, [rax+130h]
0x180030a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a05  mov     ebx, eax
0x180030a07  test    eax, eax
0x180030a09  jns     short loc_180030A84
0x180030a0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030a12  test    rcx, rcx
0x180030a15  jnz     short loc_180030A5E
0x180030a17  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030a1e  nop     dword ptr [rax+rax+00h]
0x180030a23  mov     rcx, rax
0x180030a26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030a2d  test    rax, rax
0x180030a30  jz      short loc_180030A50
0x180030a32  mov     rax, [rax]
0x180030a35  mov     edx, 7F0h
0x180030a3a  mov     rax, [rax+8]
0x180030a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a43  test    eax, eax
0x180030a45  jz      short loc_180030A50
0x180030a47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030a4e  jmp     short loc_180030A5E
0x180030a50  lea     rcx, qword_1800DBF70; this
0x180030a57  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030a5e  cmp     [rcx+8], r15b
0x180030a62  jz      loc_180030BB3
0x180030a68  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030a6d  cmp     [rax+7CCh], ebx
0x180030a73  jz      loc_180030BB3
0x180030a79  mov     r8d, 22Dh
0x180030a7f  jmp     loc_180030B9C
  ... truncated ...
```
