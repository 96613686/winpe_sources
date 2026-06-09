# CMF2DMediaBuffer::Copy2DTo(IMF2DBuffer2 *)

- ea: `0x1800a4400`
- end: `0x1800a4d50`
- name: `?Copy2DTo@CMF2DMediaBuffer@@UEAAJPEAUIMF2DBuffer2@@@Z`
- size: `2384`
- prototype: `__int64 __fastcall(CMF2DMediaBuffer *__hidden this, struct IMF2DBuffer2 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180015b20`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800a4400`
- `0x1800a4d58`
- `0x1800a5054`
- `0x1800a56c0`
- `0x1801a7d18`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a442a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a442a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a48b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a48b0`

## string_xrefs

- `0x1800a4433`: `CMF2DMediaBuffer::Copy2DTo`
- `0x1800a47f4`: `CMF2DMediaBuffer::Copy2DTo`
- `0x1800a4977`: `CMF2DMediaBuffer::Copy2DTo`
- `0x1800a4a9d`: `CMF2DMediaBuffer::Copy2DTo`
- `0x1800a4b9f`: `CMF2DMediaBuffer::Copy2DTo`
- `0x1800a4c59`: `CMF2DMediaBuffer::Copy2DTo`
- `0x1800a4d24`: `CMF2DMediaBuffer::Copy2DTo`

## pseudocode

```c
__int64 __fastcall CMF2DMediaBuffer::Copy2DTo(CMF2DMediaBuffer *this, struct IMF2DBuffer2 *a2)
{
  unsigned int *p_m_dwWidth; // rsi
  CallStackTracing *v5; // rcx
  int v6; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rdx
  CallStackTracing *v9; // rcx
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  int v12; // ecx
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  int *p_RecursionCount; // r15
  int *p_LockCount; // r12
  void **p_LockSemaphore; // r14
  CallStackTracing *v20; // rcx
  int v21; // r15d
  struct CallStackContext *v22; // rax
  int v23; // r14d
  int v24; // eax
  int v25; // eax
  int v27; // ecx
  struct CallStackContext *v28; // rax
  int v29; // ecx
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  struct CallStackContext *v32; // rax
  IMF2DBuffer2_vtbl *v33; // rax
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  CallStackTracing *v37; // rcx
  struct CallStackContext *v38; // rax
  int v39; // [rsp+40h] [rbp-29h] BYREF
  int v40; // [rsp+44h] [rbp-25h] BYREF
  unsigned __int8 *v41; // [rsp+48h] [rbp-21h] BYREF
  __int64 v42; // [rsp+50h] [rbp-19h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-11h]
  struct MFBUFFER::CBufferRO v44; // [rsp+60h] [rbp-9h] BYREF
  struct MFBUFFER::CBuffer v45; // [rsp+70h] [rbp+7h] BYREF
  __int64 v46; // [rsp+D0h] [rbp+67h] BYREF
  unsigned int v47; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int v48; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v49; // [rsp+E8h] [rbp+7Fh] BYREF

  lpCriticalSection = (LPCRITICAL_SECTION)&this[-1].m_cbCurrentLength;
  EnterCriticalSection((LPCRITICAL_SECTION)&this[-1].m_cbCurrentLength);
  v41 = 0;
  v48 = 0;
  v47 = 0;
  v49 = 0;
  v39 = 0;
  v42 = 0;
  v40 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v46, "CMF2DMediaBuffer::Copy2DTo", 897);
  p_m_dwWidth = &this[-1].m_dwWidth;
  if ( !a2 )
  {
    v5 = CallStackTracing::s_wpInstance;
    v6 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v5 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v5->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
      if ( ThreadRelativeContext->m_result != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMF2DMediaBuffer::Copy2DTo", 897, -2147024809);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v8 = 67;
LABEL_11:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        &WPP_5a15fd82a1943ae35298d5c4b89d7a7f_Traceguids,
        p_m_dwWidth,
        -2147024809);
      goto LABEL_67;
    }
    goto LABEL_67;
  }
  v6 = a2->GetContiguousLength(a2, &v49);
  if ( v6 < 0 )
  {
    v9 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v9 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v9->m_fEnabled )
    {
      v10 = CallStackTracing::GetThreadRelativeContext(v9);
      if ( v10->m_result != v6 )
        CallStackContext::TraceFailure(v10, "CMF2DMediaBuffer::Copy2DTo", 899, v6);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_67;
    v11 = 68;
    goto LABEL_23;
  }
  v6 = this->GetMaxLength(this, &v47);
  if ( v6 < 0 )
  {
    v13 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v13 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v13->m_fEnabled )
    {
      v14 = CallStackTracing::GetThreadRelativeContext(v13);
      if ( v14->m_result != v6 )
        CallStackContext::TraceFailure(v14, "CMF2DMediaBuffer::Copy2DTo", 900, v6);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_67;
    v11 = 69;
LABEL_23:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      &WPP_5a15fd82a1943ae35298d5c4b89d7a7f_Traceguids,
      p_m_dwWidth,
      v6);
    goto LABEL_67;
  }
  if ( v49 >= v47 )
  {
    p_RecursionCount = &this->m_Lock.m_CritSec.RecursionCount;
    LODWORD(v46) = 0;
    p_LockCount = &this->m_Lock.m_CritSec.LockCount;
    p_LockSemaphore = &this->m_Lock.m_CritSec.LockSemaphore;
    if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
      McTemplateU0pddddd_EventWriteTransfer(
        v12,
        (unsigned int)&Mem2DAlloc_Copy2D_Start,
        (_DWORD)this - 104,
        0,
        *p_LockCount,
        *p_RecursionCount,
        *(_DWORD *)p_LockSemaphore,
        v47);
    v6 = CMF2DMediaBuffer::DoLock2DSize(
           (CMF2DMediaBuffer *)((char *)this - 104),
           MF2DBuffer_LockFlags_Read,
           (unsigned __int8 **)&v44,
           &v39,
           &v41,
           &v48);
    if ( v6 < 0 )
    {
      v20 = CallStackTracing::s_wpInstance;
      v21 = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v20 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v20->m_fEnabled )
      {
        v22 = CallStackTracing::GetThreadRelativeContext(v20);
        if ( v22->m_result != v6 )
          CallStackContext::TraceFailure(v22, "CMF2DMediaBuffer::Copy2DTo", 911, v6);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          &WPP_5a15fd82a1943ae35298d5c4b89d7a7f_Traceguids,
          &this[-1].m_dwWidth,
          v6);
      v23 = 0;
      goto LABEL_57;
    }
    v44.m_size = v48;
    v44.m_pb = v41;
    v6 = a2->Lock2DSize(a2, MF2DBuffer_LockFlags_Write, (unsigned __int8 **)&v42, &v40, &v41, &v48);
    if ( v6 < 0 )
    {
      v20 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v20 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v20->m_fEnabled )
      {
        v28 = CallStackTracing::GetThreadRelativeContext(v20);
        if ( v28->m_result != v6 )
          CallStackContext::TraceFailure(v28, "CMF2DMediaBuffer::Copy2DTo", 915, v6);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          &WPP_5a15fd82a1943ae35298d5c4b89d7a7f_Traceguids,
          &this[-1].m_dwWidth,
          v6);
      v23 = v46;
      goto LABEL_79;
    }
    v45.m_size = v48;
    v45.m_pb = v41;
    LODWORD(v46) = 1;
    if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
      McTemplateU0pddddd_EventWriteTransfer(
        v27,
        (unsigned int)&Mem2DAlloc_Copy_Start,
        (_DWORD)this - 104,
        0,
        *p_LockCount,
        *p_RecursionCount,
        *(_DWORD *)p_LockSemaphore,
        v47);
    v6 = CMF2DMediaBuffer::InternalCopyBuffer((CMF2DMediaBuffer *)((char *)this - 104), &v45, v40, &v44, v39);
    if ( v6 < 0 )
    {
      v20 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v20 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v20->m_fEnabled )
      {
        v30 = CallStackTracing::GetThreadRelativeContext(v20);
        if ( v30->m_result != v6 )
          CallStackContext::TraceFailure(v30, "CMF2DMediaBuffer::Copy2DTo", 921, v6);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_93;
      v31 = 73;
LABEL_92:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v31,
        &WPP_5a15fd82a1943ae35298d5c4b89d7a7f_Traceguids,
        &this[-1].m_dwWidth,
        v6);
LABEL_93:
      v23 = v46;
      v21 = v46;
      goto LABEL_57;
    }
    if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
      McTemplateU0pddddd_EventWriteTransfer(
        v29,
        (unsigned int)&Mem2DAlloc_Copy_End,
        (_DWORD)this - 104,
        0,
        *p_LockCount,
        *p_RecursionCount,
        *(_DWORD *)p_LockSemaphore,
        v47);
    v6 = a2->Unlock2D(a2);
    if ( v6 < 0 )
    {
      v20 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v20 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v20->m_fEnabled )
      {
        v32 = CallStackTracing::GetThreadRelativeContext(v20);
        if ( v32->m_result != v6 )
          CallStackContext::TraceFailure(v32, "CMF2DMediaBuffer::Copy2DTo", 929, v6);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_93;
      v31 = 74;
      goto LABEL_92;
    }
    v33 = a2->__vftable;
    v23 = 0;
    v46 = 0;
    v6 = v33->QueryInterface(a2, &GUID_045fa593_8799_42b8_bc8d_8968c6453507, (void **)&v46);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v46 + 48LL))(v46, v47);
      if ( v6 >= 0 )
        goto LABEL_117;
      v37 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v37 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v37->m_fEnabled )
      {
        v38 = CallStackTracing::GetThreadRelativeContext(v37);
        if ( v38->m_result != v6 )
          CallStackContext::TraceFailure(v38, "CMF2DMediaBuffer::Copy2DTo", 940, v6);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_117;
      v36 = 76;
    }
    else
    {
      v34 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v34 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v34->m_fEnabled )
      {
        v35 = CallStackTracing::GetThreadRelativeContext(v34);
        if ( v35->m_result != v6 )
          CallStackContext::TraceFailure(v35, "CMF2DMediaBuffer::Copy2DTo", 939, v6);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_117;
      v36 = 75;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v36,
      &WPP_5a15fd82a1943ae35298d5c4b89d7a7f_Traceguids,
      &this[-1].m_dwWidth,
      v6);
LABEL_117:
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v46);
LABEL_79:
    v21 = 1;
LABEL_57:
    if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
      McTemplateU0pddddd_EventWriteTransfer(
        (_DWORD)v20,
        (unsigned int)&Mem2DAlloc_Copy2D_End,
        (_DWORD)this - 104,
        0,
        this->m_Lock.m_CritSec.LockCount,
        this->m_Lock.m_CritSec.RecursionCount,
        (char)this->m_Lock.m_CritSec.LockSemaphore,
        v47);
    if ( v21 )
    {
      v24 = CMF2DMediaBuffer::DoUnlock2D((CMF2DMediaBuffer *)((char *)this - 104));
      if ( v24 < 0 && v6 >= 0 )
        v6 = v24;
    }
    if ( v23 )
    {
      v25 = a2->Unlock2D(a2);
      if ( v25 < 0 && v6 >= 0 )
        v6 = v25;
    }
    goto LABEL_67;
  }
  v15 = CallStackTracing::s_wpInstance;
  v6 = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v15 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v15 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v15->m_fEnabled )
  {
    v16 = CallStackTracing::GetThreadRelativeContext(v15);
    if ( v16->m_result != -2147024809 )
      CallStackContext::TraceFailure(v16, "CMF2DMediaBuffer::Copy2DTo", 905, -2147024809);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v8 = 70;
    goto LABEL_11;
  }
LABEL_67:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v46);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800a4400  push    rbp
0x1800a4402  push    rbx
0x1800a4403  push    rsi
0x1800a4404  push    rdi
0x1800a4405  push    r12
0x1800a4407  push    r13
0x1800a4409  push    r14
0x1800a440b  push    r15
0x1800a440d  lea     rbp, [rsp-1Fh]
0x1800a4412  sub     rsp, 88h
0x1800a4419  lea     rax, [rcx-30h]
0x1800a441d  mov     rdi, rcx
0x1800a4420  mov     rcx, rax; lpCriticalSection
0x1800a4423  mov     [rbp+57h+lpCriticalSection], rax
0x1800a4427  mov     r13, rdx
0x1800a442a  call    cs:__imp_EnterCriticalSection
0x1800a4430  xor     r14d, r14d
0x1800a4433  lea     r15, aCmf2dmediabuff_17; "CMF2DMediaBuffer::Copy2DTo"
0x1800a443a  mov     r12d, 381h
0x1800a4440  mov     [rbp+57h+var_78], r14
0x1800a4444  mov     r8d, r12d; int
0x1800a4447  mov     [rbp+57h+arg_10], r14d
0x1800a444b  mov     rdx, r15; char *
0x1800a444e  mov     [rbp+57h+arg_8], r14d
0x1800a4452  lea     rcx, [rbp+57h+arg_0]; this
0x1800a4456  mov     [rbp+57h+arg_18], r14d
0x1800a445a  mov     [rbp+57h+var_80], r14d
0x1800a445e  mov     [rbp+57h+var_70], r14
0x1800a4462  mov     [rbp+57h+var_7C], r14d
0x1800a4466  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a446b  lea     rsi, [rdi-68h]
0x1800a446f  test    r13, r13
0x1800a4472  jnz     loc_1800A4525
0x1800a4478  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a447f  mov     edi, 80070057h
0x1800a4484  mov     ebx, edi
0x1800a4486  test    rcx, rcx
0x1800a4489  jnz     short loc_1800A44CC
0x1800a448b  mov     rax, cs:stru_1801FC290.__vftable
0x1800a4492  lea     r8, stru_1801FC290
0x1800a4499  mov     edx, 7F0h
0x1800a449e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a44a5  mov     rcx, r8
0x1800a44a8  mov     rax, [rax+8]
0x1800a44ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a44b1  test    eax, eax
0x1800a44b3  jnz     short loc_1800A44C5
0x1800a44b5  lea     rcx, stru_1801F8A30
0x1800a44bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a44c3  jmp     short loc_1800A44CC
0x1800a44c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a44cc  cmp     [rcx+8], r14b
0x1800a44d0  jz      short loc_1800A44F0
0x1800a44d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a44d7  cmp     [rax+7CCh], edi
0x1800a44dd  jz      short loc_1800A44F0
0x1800a44df  mov     r9d, edi; int
0x1800a44e2  mov     r8d, r12d; int
0x1800a44e5  mov     rdx, r15; char *
0x1800a44e8  mov     rcx, rax; this
0x1800a44eb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a44f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a44f7  jb      loc_1800A48A3
0x1800a44fd  mov     edx, 43h ; 'C'
0x1800a4502  mov     dword ptr [rsp+0C0h+var_A0], edi
0x1800a4506  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a450d  lea     r8, WPP_5a15fd82a1943ae35298d5c4b89d7a7f_Traceguids
0x1800a4514  mov     r9, rsi
0x1800a4517  mov     rcx, [rcx+10h]
0x1800a451b  call    WPP_SF_qD
0x1800a4520  jmp     loc_1800A48A3
0x1800a4525  mov     rax, [r13+0]
0x1800a4529  lea     rdx, [rbp+57h+arg_18]
0x1800a452d  mov     rcx, r13
0x1800a4530  mov     rax, [rax+38h]
0x1800a4534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4539  mov     ebx, eax
0x1800a453b  test    eax, eax
0x1800a453d  jns     loc_1800A45D2
0x1800a4543  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a454a  test    rcx, rcx
0x1800a454d  jnz     short loc_1800A4590
0x1800a454f  mov     rcx, cs:stru_1801FC290.__vftable
0x1800a4556  lea     r8, stru_1801FC290
0x1800a455d  mov     edx, 7F0h
0x1800a4562  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4569  mov     rax, [rcx+8]
0x1800a456d  mov     rcx, r8
0x1800a4570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4575  test    eax, eax
0x1800a4577  jnz     short loc_1800A4589
0x1800a4579  lea     rcx, stru_1801F8A30
0x1800a4580  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4587  jmp     short loc_1800A4590
0x1800a4589  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a4590  cmp     [rcx+8], r14b
0x1800a4594  jz      short loc_1800A45B7
0x1800a4596  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a459b  cmp     [rax+7CCh], ebx
0x1800a45a1  jz      short loc_1800A45B7
0x1800a45a3  mov     r9d, ebx; int
0x1800a45a6  mov     r8d, 383h; int
0x1800a45ac  mov     rdx, r15; char *
0x1800a45af  mov     rcx, rax; this
0x1800a45b2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a45b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a45be  jb      loc_1800A48A3
0x1800a45c4  mov     edx, 44h ; 'D'
0x1800a45c9  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800a45cd  jmp     loc_1800A4506
0x1800a45d2  mov     rax, [rdi]
0x1800a45d5  lea     rdx, [rbp+57h+arg_8]
0x1800a45d9  mov     rcx, rdi
0x1800a45dc  mov     rax, [rax+38h]
0x1800a45e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a45e5  mov     ebx, eax
0x1800a45e7  test    eax, eax
0x1800a45e9  jns     loc_1800A467A
0x1800a45ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a45f6  test    rcx, rcx
0x1800a45f9  jnz     short loc_1800A463C
0x1800a45fb  mov     rax, cs:stru_1801FC290.__vftable
0x1800a4602  lea     r8, stru_1801FC290
0x1800a4609  mov     edx, 7F0h
0x1800a460e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4615  mov     rcx, r8
0x1800a4618  mov     rax, [rax+8]
0x1800a461c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4621  test    eax, eax
0x1800a4623  jnz     short loc_1800A4635
0x1800a4625  lea     rcx, stru_1801F8A30
0x1800a462c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4633  jmp     short loc_1800A463C
0x1800a4635  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a463c  cmp     [rcx+8], r14b
0x1800a4640  jz      short loc_1800A4663
0x1800a4642  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a4647  cmp     [rax+7CCh], ebx
0x1800a464d  jz      short loc_1800A4663
0x1800a464f  mov     r9d, ebx; int
0x1800a4652  mov     r8d, 384h; int
0x1800a4658  mov     rdx, r15; char *
0x1800a465b  mov     rcx, rax; this
0x1800a465e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a4663  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a466a  jb      loc_1800A48A3
0x1800a4670  mov     edx, 45h ; 'E'
0x1800a4675  jmp     loc_1800A45C9
0x1800a467a  mov     eax, [rbp+57h+arg_8]
0x1800a467d  cmp     [rbp+57h+arg_18], eax
0x1800a4680  jnb     loc_1800A4718
0x1800a4686  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a468d  mov     edi, 80070057h
0x1800a4692  mov     ebx, edi
0x1800a4694  test    rcx, rcx
0x1800a4697  jnz     short loc_1800A46DA
0x1800a4699  mov     rax, cs:stru_1801FC290.__vftable
0x1800a46a0  lea     r8, stru_1801FC290
0x1800a46a7  mov     edx, 7F0h
0x1800a46ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a46b3  mov     rcx, r8
0x1800a46b6  mov     rax, [rax+8]
0x1800a46ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a46bf  test    eax, eax
0x1800a46c1  jnz     short loc_1800A46D3
0x1800a46c3  lea     rcx, stru_1801F8A30
0x1800a46ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a46d1  jmp     short loc_1800A46DA
0x1800a46d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a46da  cmp     [rcx+8], r14b
0x1800a46de  jz      short loc_1800A4701
0x1800a46e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a46e5  cmp     [rax+7CCh], edi
0x1800a46eb  jz      short loc_1800A4701
0x1800a46ed  mov     r9d, edi; int
0x1800a46f0  mov     r8d, 389h; int
0x1800a46f6  mov     rdx, r15; char *
0x1800a46f9  mov     rcx, rax; this
0x1800a46fc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a4701  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a4708  jb      loc_1800A48A3
0x1800a470e  mov     edx, 46h ; 'F'
0x1800a4713  jmp     loc_1800A4502
0x1800a4718  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x1800a471f  lea     r15, [rdi+44h]
0x1800a4723  mov     dword ptr [rbp+57h+arg_0], r14d
0x1800a4727  lea     r12, [rdi+40h]
0x1800a472b  lea     r14, [rdi+50h]
0x1800a472f  jz      short loc_1800A475D
0x1800a4731  mov     [rsp+0C0h+var_88], eax
0x1800a4735  lea     rdx, Mem2DAlloc_Copy2D_Start
0x1800a473c  mov     eax, [r14]
0x1800a473f  xor     r9d, r9d
0x1800a4742  mov     [rsp+0C0h+var_90], eax
0x1800a4746  mov     r8, rsi
0x1800a4749  mov     eax, [r15]
0x1800a474c  mov     dword ptr [rsp+0C0h+var_98], eax
0x1800a4750  mov     eax, [r12]
0x1800a4754  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800a4758  call    McTemplateU0pddddd_EventWriteTransfer
0x1800a475d  lea     rax, [rbp+57h+arg_10]
0x1800a4761  mov     edx, 1; enum _MF2DBuffer_LockFlags
0x1800a4766  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x1800a476b  lea     r9, [rbp+57h+var_80]; int *
0x1800a476f  lea     rax, [rbp+57h+var_78]
0x1800a4773  mov     rcx, rsi; this
0x1800a4776  lea     r8, [rbp+57h+var_60]; unsigned __int8 **
0x1800a477a  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 **
0x1800a477f  call    ?DoLock2DSize@CMF2DMediaBuffer@@AEAAJW4_MF2DBuffer_LockFlags@@PEAPEAEPEAJ1PEAK@Z; CMF2DMediaBuffer::DoLock2DSize(_MF2DBuffer_LockFlags,uchar * *,long *,uchar * *,ulong *)
0x1800a4784  mov     ebx, eax
0x1800a4786  test    eax, eax
0x1800a4788  jns     loc_1800A48CC
0x1800a478e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4795  xor     r15d, r15d
0x1800a4798  test    rcx, rcx
0x1800a479b  jnz     short loc_1800A47DE
0x1800a479d  mov     rax, cs:stru_1801FC290.__vftable
0x1800a47a4  lea     r8, stru_1801FC290
0x1800a47ab  mov     edx, 7F0h
0x1800a47b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a47b7  mov     rcx, r8
0x1800a47ba  mov     rax, [rax+8]
0x1800a47be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a47c3  test    eax, eax
0x1800a47c5  jnz     short loc_1800A47D7
0x1800a47c7  lea     rcx, stru_1801F8A30
0x1800a47ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a47d5  jmp     short loc_1800A47DE
0x1800a47d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a47de  cmp     [rcx+8], r15b
0x1800a47e2  jz      short loc_1800A4809
0x1800a47e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a47e9  cmp     [rax+7CCh], ebx
0x1800a47ef  jz      short loc_1800A4809
0x1800a47f1  mov     r9d, ebx; int
0x1800a47f4  lea     rdx, aCmf2dmediabuff_17; "CMF2DMediaBuffer::Copy2DTo"
0x1800a47fb  mov     r8d, 38Fh; int
0x1800a4801  mov     rcx, rax; this
0x1800a4804  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a4809  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a4810  jb      short loc_1800A4835
0x1800a4812  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4819  lea     r8, WPP_5a15fd82a1943ae35298d5c4b89d7a7f_Traceguids
0x1800a4820  mov     edx, 47h ; 'G'
0x1800a4825  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800a4829  mov     r9, rsi
0x1800a482c  mov     rcx, [rcx+10h]
0x1800a4830  call    WPP_SF_qD
0x1800a4835  mov     r14d, r15d
0x1800a4838  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x1800a483f  jz      short loc_1800A486F
0x1800a4841  mov     eax, [rbp+57h+arg_8]
0x1800a4844  lea     rdx, Mem2DAlloc_Copy2D_End
0x1800a484b  mov     [rsp+0C0h+var_88], eax
0x1800a484f  xor     r9d, r9d
0x1800a4852  mov     eax, [rdi+50h]
0x1800a4855  mov     r8, rsi
0x1800a4858  mov     [rsp+0C0h+var_90], eax
0x1800a485c  mov     eax, [rdi+44h]
0x1800a485f  mov     dword ptr [rsp+0C0h+var_98], eax
0x1800a4863  mov     eax, [rdi+40h]
0x1800a4866  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800a486a  call    McTemplateU0pddddd_EventWriteTransfer
0x1800a486f  test    r15d, r15d
0x1800a4872  jz      short loc_1800A4885
0x1800a4874  mov     rcx, rsi; this
0x1800a4877  call    ?DoUnlock2D@CMF2DMediaBuffer@@AEAAJXZ; CMF2DMediaBuffer::DoUnlock2D(void)
0x1800a487c  test    eax, eax
0x1800a487e  jns     short loc_1800A4885
0x1800a4880  test    ebx, ebx
0x1800a4882  cmovns  ebx, eax
0x1800a4885  test    r14d, r14d
0x1800a4888  jz      short loc_1800A48A3
0x1800a488a  mov     rax, [r13+0]
0x1800a488e  mov     rcx, r13
0x1800a4891  mov     rax, [rax+20h]
0x1800a4895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a489a  test    eax, eax
0x1800a489c  jns     short loc_1800A48A3
0x1800a489e  test    ebx, ebx
0x1800a48a0  cmovns  ebx, eax
0x1800a48a3  lea     rcx, [rbp+57h+arg_0]; this
0x1800a48a7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a48ac  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800a48b0  call    cs:__imp_LeaveCriticalSection
0x1800a48b6  mov     eax, ebx
0x1800a48b8  add     rsp, 88h
0x1800a48bf  pop     r15
0x1800a48c1  pop     r14
0x1800a48c3  pop     r13
0x1800a48c5  pop     r12
0x1800a48c7  pop     rdi
0x1800a48c8  pop     rsi
0x1800a48c9  pop     rbx
0x1800a48ca  pop     rbp
0x1800a48cb  retn
0x1800a48cc  mov     eax, [rbp+57h+arg_10]
0x1800a48cf  lea     rcx, [rbp+57h+arg_10]
0x1800a48d3  mov     [rbp+57h+var_60.m_size], rax
0x1800a48d7  lea     r9, [rbp+57h+var_7C]
  ... truncated ...
```
