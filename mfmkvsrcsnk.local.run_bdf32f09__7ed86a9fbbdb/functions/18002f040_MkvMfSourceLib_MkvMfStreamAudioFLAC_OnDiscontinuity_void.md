# MkvMfSourceLib::MkvMfStreamAudioFLAC::OnDiscontinuity(void)

- ea: `0x18002f040`
- end: `0x18002f667`
- name: `?OnDiscontinuity@MkvMfStreamAudioFLAC@MkvMfSourceLib@@MEAAJXZ`
- size: `1575`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStreamAudioFLAC *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800036c5`
- `0x180005ab8`
- `0x1800097f0`
- `0x18002110c`
- `0x18002148c`
- `0x180023adc`
- `0x1800240f0`
- `0x18002f040`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f08b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f131`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f1dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f264`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f2ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f395`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f423`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f4b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f541`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f5c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f08b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f131`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f1dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f264`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f2ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f395`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f423`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f4b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f541`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f5c3`
- `MFPlat!MFCreateSample` at `0x18002f24c`
- `MFPlat!MFCreateSample` at `0x18002f24c`
- `MFPlat!MFCreateMemoryBuffer` at `0x18002f06f`
- `MFPlat!MFCreateMemoryBuffer` at `0x18002f06f`

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
          v15 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v22 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                    v59 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                    v54 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v49 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                v44 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v39 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v34 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v27 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v9 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18002f040  mov     [rsp-28h+arg_10], rbx
0x18002f045  push    rbp
0x18002f046  push    rsi
0x18002f047  push    rdi
0x18002f048  push    r14
0x18002f04a  push    r15
0x18002f04c  mov     rbp, rsp
0x18002f04f  sub     rsp, 40h
0x18002f053  mov     rsi, rcx
0x18002f056  mov     rax, [rcx+48h]
0x18002f05a  mov     rdi, [rax+70h]
0x18002f05e  mov     r14, [rax+68h]
0x18002f062  xor     r15d, r15d
0x18002f065  mov     [rbp+ppBuffer], r15
0x18002f069  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x18002f06d  mov     ecx, edi; cbMaxLength
0x18002f06f  call    cs:__imp_MFCreateMemoryBuffer
0x18002f075  mov     ebx, eax
0x18002f077  test    eax, eax
0x18002f079  jns     loc_18002F104
0x18002f07f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f086  test    rcx, rcx
0x18002f089  jnz     short loc_18002F0CC
0x18002f08b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f091  mov     rcx, rax
0x18002f094  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f09b  test    rax, rax
0x18002f09e  jz      short loc_18002F0BE
0x18002f0a0  mov     rax, [rax]
0x18002f0a3  mov     edx, 7F0h
0x18002f0a8  mov     rax, [rax+8]
0x18002f0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0b1  test    eax, eax
0x18002f0b3  jz      short loc_18002F0BE
0x18002f0b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f0bc  jmp     short loc_18002F0CC
0x18002f0be  lea     rcx, qword_1800D6F70; this
0x18002f0c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f0cc  cmp     [rcx+8], r15b
0x18002f0d0  jz      loc_18002F648
0x18002f0d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f0db  cmp     [rax+7CCh], ebx
0x18002f0e1  jz      loc_18002F648
0x18002f0e7  mov     r9d, ebx; int
0x18002f0ea  mov     r8d, 21Eh; int
0x18002f0f0  lea     rdx, aMkvmfsourcelib_94; "MkvMfSourceLib::MkvMfStreamAudioFLAC::O"...
0x18002f0f7  mov     rcx, rax; this
0x18002f0fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002f0ff  jmp     loc_18002F648
0x18002f104  mov     rdx, [rbp+ppBuffer]; struct IMFMediaBuffer *
0x18002f108  lea     rcx, [rbp+var_20]; this
0x18002f10c  call    ??0CSmartMFBufferLock@@QEAA@PEAUIMFMediaBuffer@@@Z; CSmartMFBufferLock::CSmartMFBufferLock(IMFMediaBuffer *)
0x18002f111  nop
0x18002f112  lea     rcx, [rbp+var_20]; this
0x18002f116  call    ?Lock@CSmartMFBufferLock@@QEAAJXZ; CSmartMFBufferLock::Lock(void)
0x18002f11b  mov     ebx, eax
0x18002f11d  test    eax, eax
0x18002f11f  jns     loc_18002F1AA
0x18002f125  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f12c  test    rcx, rcx
0x18002f12f  jnz     short loc_18002F172
0x18002f131  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f137  mov     rcx, rax
0x18002f13a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f141  test    rax, rax
0x18002f144  jz      short loc_18002F164
0x18002f146  mov     rax, [rax]
0x18002f149  mov     edx, 7F0h
0x18002f14e  mov     rax, [rax+8]
0x18002f152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f157  test    eax, eax
0x18002f159  jz      short loc_18002F164
0x18002f15b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f162  jmp     short loc_18002F172
0x18002f164  lea     rcx, qword_1800D6F70; this
0x18002f16b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f172  cmp     [rcx+8], r15b
0x18002f176  jz      loc_18002F63E
0x18002f17c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f181  cmp     [rax+7CCh], ebx
0x18002f187  jz      loc_18002F63E
0x18002f18d  mov     r8d, 221h; int
0x18002f193  mov     r9d, ebx; int
0x18002f196  lea     rdx, aMkvmfsourcelib_94; "MkvMfSourceLib::MkvMfStreamAudioFLAC::O"...
0x18002f19d  mov     rcx, rax; this
0x18002f1a0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002f1a5  jmp     loc_18002F63E
0x18002f1aa  mov     r8, rdi; Size
0x18002f1ad  mov     rdx, r14; Src
0x18002f1b0  mov     rcx, [rbp+var_10]; void *
0x18002f1b4  call    memcpy_0
0x18002f1b9  mov     rcx, [rbp+ppBuffer]
0x18002f1bd  mov     rax, [rcx]
0x18002f1c0  mov     edx, edi
0x18002f1c2  mov     rax, [rax+30h]
0x18002f1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1cb  mov     ebx, eax
0x18002f1cd  test    eax, eax
0x18002f1cf  jns     short loc_18002F244
0x18002f1d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f1d8  test    rcx, rcx
0x18002f1db  jnz     short loc_18002F21E
0x18002f1dd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f1e3  mov     rcx, rax
0x18002f1e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f1ed  test    rax, rax
0x18002f1f0  jz      short loc_18002F210
0x18002f1f2  mov     rax, [rax]
0x18002f1f5  mov     edx, 7F0h
0x18002f1fa  mov     rax, [rax+8]
0x18002f1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f203  test    eax, eax
0x18002f205  jz      short loc_18002F210
0x18002f207  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f20e  jmp     short loc_18002F21E
0x18002f210  lea     rcx, qword_1800D6F70; this
0x18002f217  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f21e  cmp     [rcx+8], r15b
0x18002f222  jz      loc_18002F63E
0x18002f228  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f22d  cmp     [rax+7CCh], ebx
0x18002f233  jz      loc_18002F63E
0x18002f239  mov     r8d, 225h
0x18002f23f  jmp     loc_18002F193
0x18002f244  mov     [rbp+ppIMFSample], r15
0x18002f248  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x18002f24c  call    cs:__imp_MFCreateSample
0x18002f252  mov     ebx, eax
0x18002f254  test    eax, eax
0x18002f256  jns     short loc_18002F2CB
0x18002f258  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f25f  test    rcx, rcx
0x18002f262  jnz     short loc_18002F2A5
0x18002f264  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f26a  mov     rcx, rax
0x18002f26d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f274  test    rax, rax
0x18002f277  jz      short loc_18002F297
0x18002f279  mov     rax, [rax]
0x18002f27c  mov     edx, 7F0h
0x18002f281  mov     rax, [rax+8]
0x18002f285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f28a  test    eax, eax
0x18002f28c  jz      short loc_18002F297
0x18002f28e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f295  jmp     short loc_18002F2A5
0x18002f297  lea     rcx, qword_1800D6F70; this
0x18002f29e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f2a5  cmp     [rcx+8], r15b
0x18002f2a9  jz      loc_18002F634
0x18002f2af  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f2b4  cmp     [rax+7CCh], ebx
0x18002f2ba  jz      loc_18002F634
0x18002f2c0  mov     r8d, 228h
0x18002f2c6  jmp     loc_18002F61D
0x18002f2cb  mov     rcx, [rbp+ppIMFSample]
0x18002f2cf  mov     rax, [rcx]
0x18002f2d2  mov     edi, 1
0x18002f2d7  mov     r8d, edi
0x18002f2da  lea     rdx, MFSampleExtension_CleanPoint
0x18002f2e1  mov     rax, [rax+0A8h]
0x18002f2e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2ed  mov     ebx, eax
0x18002f2ef  test    eax, eax
0x18002f2f1  jns     short loc_18002F366
0x18002f2f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f2fa  test    rcx, rcx
0x18002f2fd  jnz     short loc_18002F340
0x18002f2ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f305  mov     rcx, rax
0x18002f308  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f30f  test    rax, rax
0x18002f312  jz      short loc_18002F332
0x18002f314  mov     rax, [rax]
0x18002f317  mov     edx, 7F0h
0x18002f31c  mov     rax, [rax+8]
0x18002f320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f325  test    eax, eax
0x18002f327  jz      short loc_18002F332
0x18002f329  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f330  jmp     short loc_18002F340
0x18002f332  lea     rcx, qword_1800D6F70; this
0x18002f339  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f340  cmp     [rcx+8], r15b
0x18002f344  jz      loc_18002F634
0x18002f34a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f34f  cmp     [rax+7CCh], ebx
0x18002f355  jz      loc_18002F634
0x18002f35b  mov     r8d, 22Ah
0x18002f361  jmp     loc_18002F61D
0x18002f366  mov     rcx, [rbp+ppIMFSample]
0x18002f36a  mov     rax, [rcx]
0x18002f36d  mov     r8d, edi
0x18002f370  lea     rdx, MFSampleExtension_Discontinuity
0x18002f377  mov     rax, [rax+0A8h]
0x18002f37e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f383  mov     ebx, eax
0x18002f385  test    eax, eax
0x18002f387  jns     short loc_18002F3FC
0x18002f389  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f390  test    rcx, rcx
0x18002f393  jnz     short loc_18002F3D6
0x18002f395  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f39b  mov     rcx, rax
0x18002f39e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f3a5  test    rax, rax
0x18002f3a8  jz      short loc_18002F3C8
0x18002f3aa  mov     rax, [rax]
0x18002f3ad  mov     edx, 7F0h
0x18002f3b2  mov     rax, [rax+8]
0x18002f3b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3bb  test    eax, eax
0x18002f3bd  jz      short loc_18002F3C8
0x18002f3bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f3c6  jmp     short loc_18002F3D6
0x18002f3c8  lea     rcx, qword_1800D6F70; this
0x18002f3cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f3d6  cmp     [rcx+8], r15b
0x18002f3da  jz      loc_18002F634
0x18002f3e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f3e5  cmp     [rax+7CCh], ebx
0x18002f3eb  jz      loc_18002F634
0x18002f3f1  mov     r8d, 22Bh
0x18002f3f7  jmp     loc_18002F61D
0x18002f3fc  mov     rcx, [rbp+ppIMFSample]
0x18002f400  mov     rax, [rcx]
0x18002f403  xor     edx, edx
0x18002f405  mov     rax, [rax+120h]
0x18002f40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f411  mov     ebx, eax
0x18002f413  test    eax, eax
0x18002f415  jns     short loc_18002F48A
0x18002f417  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f41e  test    rcx, rcx
0x18002f421  jnz     short loc_18002F464
0x18002f423  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f429  mov     rcx, rax
0x18002f42c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f433  test    rax, rax
0x18002f436  jz      short loc_18002F456
0x18002f438  mov     rax, [rax]
0x18002f43b  mov     edx, 7F0h
0x18002f440  mov     rax, [rax+8]
0x18002f444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f449  test    eax, eax
0x18002f44b  jz      short loc_18002F456
0x18002f44d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f454  jmp     short loc_18002F464
0x18002f456  lea     rcx, qword_1800D6F70; this
0x18002f45d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f464  cmp     [rcx+8], r15b
0x18002f468  jz      loc_18002F634
0x18002f46e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f473  cmp     [rax+7CCh], ebx
0x18002f479  jz      loc_18002F634
0x18002f47f  mov     r8d, 22Ch
0x18002f485  jmp     loc_18002F61D
0x18002f48a  mov     rcx, [rbp+ppIMFSample]
0x18002f48e  mov     rax, [rcx]
0x18002f491  xor     edx, edx
0x18002f493  mov     rax, [rax+130h]
0x18002f49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f49f  mov     ebx, eax
0x18002f4a1  test    eax, eax
0x18002f4a3  jns     short loc_18002F518
0x18002f4a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f4ac  test    rcx, rcx
0x18002f4af  jnz     short loc_18002F4F2
0x18002f4b1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f4b7  mov     rcx, rax
0x18002f4ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f4c1  test    rax, rax
0x18002f4c4  jz      short loc_18002F4E4
0x18002f4c6  mov     rax, [rax]
0x18002f4c9  mov     edx, 7F0h
0x18002f4ce  mov     rax, [rax+8]
0x18002f4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4d7  test    eax, eax
0x18002f4d9  jz      short loc_18002F4E4
0x18002f4db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f4e2  jmp     short loc_18002F4F2
0x18002f4e4  lea     rcx, qword_1800D6F70; this
0x18002f4eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f4f2  cmp     [rcx+8], r15b
0x18002f4f6  jz      loc_18002F634
0x18002f4fc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002f501  cmp     [rax+7CCh], ebx
0x18002f507  jz      loc_18002F634
0x18002f50d  mov     r8d, 22Dh
0x18002f513  jmp     loc_18002F61D
0x18002f518  mov     rcx, [rbp+ppIMFSample]
0x18002f51c  mov     rax, [rcx]
0x18002f51f  mov     rdx, [rbp+ppBuffer]
0x18002f523  mov     rax, [rax+150h]
0x18002f52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f52f  mov     ebx, eax
0x18002f531  test    eax, eax
0x18002f533  jns     short loc_18002F5A5
0x18002f535  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002f53c  test    rcx, rcx
  ... truncated ...
```
