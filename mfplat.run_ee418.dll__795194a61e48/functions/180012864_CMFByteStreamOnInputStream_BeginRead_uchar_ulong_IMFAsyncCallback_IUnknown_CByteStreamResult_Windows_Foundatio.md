# CMFByteStreamOnInputStream::_BeginRead(uchar *,ulong,IMFAsyncCallback *,IUnknown *,CByteStreamResult<Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>> * *)

- ea: `0x180012864`
- end: `0x180012ee2`
- name: `?_BeginRead@CMFByteStreamOnInputStream@@IEAAJPEAEKPEAUIMFAsyncCallback@@PEAUIUnknown@@PEAPEAV?$CByteStreamResult@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@@Z`
- size: `1662`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012610`
- `0x1801835a0`

## callees

- `0x180004870`
- `0x18000f424`
- `0x180012864`
- `0x180013288`
- `0x1800132ac`
- `0x180013ca0`
- `0x180013cf4`
- `0x180013e34`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1801200d0`
- `0x18012a6a4`
- `0x180184134`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012ea8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012ed7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012ea8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012ed7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800128c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800128c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012a05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012a05`
- `RTWorkQ!RtwqInvokeCallback` at `0x180012e63`
- `RTWorkQ!RtwqInvokeCallback` at `0x180012e63`

## string_xrefs

- `0x18001289c`: `CMFByteStreamOnInputStream::_BeginRead`
- `0x180012ace`: `CMFByteStreamOnInputStream::_BeginRead`
- `0x180012b5f`: `CMFByteStreamOnInputStream::_BeginRead`
- `0x180012bed`: `CMFByteStreamOnInputStream::_BeginRead`
- `0x180012c95`: `CMFByteStreamOnInputStream::_BeginRead`
- `0x180012d23`: `CMFByteStreamOnInputStream::_BeginRead`
- `0x180012dcb`: `CMFByteStreamOnInputStream::_BeginRead`

## pseudocode

```c
__int64 __fastcall CMFByteStreamOnInputStream::_BeginRead(
        __int64 a1,
        unsigned __int8 *a2,
        unsigned int a3,
        struct IMFAsyncCallback *a4,
        struct IUnknown *a5,
        IRtwqAsyncResult **a6)
{
  __int64 v8; // r12
  struct _RTL_CRITICAL_SECTION *v10; // r15
  IRtwqAsyncResult *v11; // rsi
  HRESULT Instance; // ebx
  int v13; // r8d
  IRtwqAsyncResult *v14; // rax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  CallStackTracing *v18; // rcx
  __int64 v19; // rdx
  struct CallStackContext *v20; // rax
  CallStackTracing *v21; // rcx
  __int64 v22; // rdx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  __int64 v30; // r12
  IRtwqAsyncResult *v31; // rcx
  IRtwqAsyncResult *v32; // rax
  int v33; // edx
  int v34; // ecx
  CallStackScopeTrace v35; // [rsp+30h] [rbp-49h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-41h]
  IRtwqAsyncResult *result; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v38; // [rsp+48h] [rbp-31h] BYREF
  CBaseOperation *v39; // [rsp+50h] [rbp-29h] BYREF
  struct IUnknown *v40; // [rsp+58h] [rbp-21h]
  GUID ActivityId; // [rsp+60h] [rbp-19h] BYREF

  v8 = a3;
  *(_QWORD *)&ActivityId.Data1 = a4;
  v40 = a5;
  CallStackScopeTrace::CallStackScopeTrace(&v35, "CMFByteStreamOnInputStream::_BeginRead", 743);
  v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v11 = 0;
  result = 0;
  v39 = 0;
  v38 = 0;
  if ( a6 )
    *a6 = 0;
  if ( *(_DWORD *)(a1 + 600) )
  {
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 0x20u )
      WPP_SF_qdq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        &WPP_be105526232037934c214e06a667adcd_Traceguids,
        a1,
        v8,
        *(_QWORD *)(a1 + 632));
    if ( CByteStreamCache::GetBuffer((CByteStreamCache *)(a1 + 616), *(_QWORD *)(a1 + 632), a2, v8, &v38) < 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&result);
      Instance = CByteStreamResult<Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>>::CreateInstance(
                   *(_QWORD *)(a1 + 632),
                   (int)a2,
                   v8,
                   (struct IMFAsyncCallback *)(a1 + 568),
                   0,
                   (__int64)&result);
      if ( Instance >= 0 )
      {
        v11 = result;
        LOBYTE(result[3].__vftable) = 0;
        Microsoft::WRL::ComPtr<CMFByteStreamOnInputStream::CByteStreamOperation>::InternalRelease(&v39);
        Instance = CMFByteStreamOnInputStream::CByteStreamOperation::CreateInstance(
                     1,
                     (_DWORD)v11,
                     ActivityId.Data1,
                     (_DWORD)v40,
                     (__int64)&v39);
        if ( Instance < 0 )
        {
          v26 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v26 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v26 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v26->m_fEnabled )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v26);
            if ( ThreadRelativeContext->m_result != Instance )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CMFByteStreamOnInputStream::_BeginRead",
                813,
                Instance);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_13;
          v22 = 93;
        }
        else
        {
          Instance = COpQueue::QueueOperation((COpQueue *)(a1 + 80), v39, v13);
          if ( Instance >= 0 )
          {
            if ( (Microsoft_Windows_MediaFoundation_PlatformEnableBits & 8) != 0 )
            {
              ActivityId = 0;
              EventActivityIdControl(4u, &ActivityId);
              if ( (Microsoft_Windows_MediaFoundation_PlatformEnableBits & 8) != 0 )
                McTemplateU0pidp_EventWriteTransfer(v34, v33, a1, *(_QWORD *)(a1 + 632), v8, (char)a2);
              EventActivityIdControl(4u, &ActivityId);
            }
            *(_QWORD *)(a1 + 632) += v8;
            if ( a6 )
            {
              v14 = v11;
              v11 = 0;
              *a6 = v14;
            }
            goto LABEL_13;
          }
          v28 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v28 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v28->m_fEnabled )
          {
            v29 = CallStackTracing::GetThreadRelativeContext(v28);
            if ( v29->m_result != Instance )
              CallStackContext::TraceFailure(v29, "CMFByteStreamOnInputStream::_BeginRead", 815, Instance);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_13;
          v22 = 94;
        }
        goto LABEL_72;
      }
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v24 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v24->m_fEnabled )
      {
        v25 = CallStackTracing::GetThreadRelativeContext(v24);
        if ( v25->m_result != Instance )
          CallStackContext::TraceFailure(v25, "CMFByteStreamOnInputStream::_BeginRead", 800, Instance);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
LABEL_53:
        v11 = result;
LABEL_13:
        v10 = lpCriticalSection;
        goto LABEL_14;
      }
      v19 = 92;
LABEL_52:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        &WPP_be105526232037934c214e06a667adcd_Traceguids,
        a1,
        Instance);
      goto LABEL_53;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&result);
    Instance = CByteStreamResult<Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>>::CreateInstance(
                 *(_QWORD *)(a1 + 632),
                 (int)a2,
                 v8,
                 a4,
                 v40,
                 (__int64)&result);
    if ( Instance < 0 )
    {
      v18 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v18 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v18->m_fEnabled )
      {
        v20 = CallStackTracing::GetThreadRelativeContext(v18);
        if ( v20->m_result != Instance )
          CallStackContext::TraceFailure(v20, "CMFByteStreamOnInputStream::_BeginRead", 776, Instance);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_53;
      v19 = 90;
      goto LABEL_52;
    }
    v11 = result;
    v30 = v38;
    v31 = result;
    HIDWORD(result[2].GetStateNoAddRef) = v38;
    Instance = RtwqInvokeCallback(v31);
    if ( Instance < 0 )
    {
      v21 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v21 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v21->m_fEnabled )
      {
        v23 = CallStackTracing::GetThreadRelativeContext(v21);
        if ( v23->m_result != Instance )
          CallStackContext::TraceFailure(v23, "CMFByteStreamOnInputStream::_BeginRead", 780, Instance);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_13;
      v22 = 91;
LABEL_72:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        &WPP_be105526232037934c214e06a667adcd_Traceguids,
        a1,
        Instance);
      goto LABEL_13;
    }
    *(_QWORD *)(a1 + 632) += v30;
    v10 = lpCriticalSection;
    if ( a6 )
    {
      v32 = v11;
      v11 = 0;
      *a6 = v32;
    }
  }
  else
  {
    v16 = CallStackTracing::s_wpInstance;
    Instance = -1072873851;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v16 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v16->m_fEnabled )
    {
      v17 = CallStackTracing::GetThreadRelativeContext(v16);
      if ( v17->m_result != -1072873851 )
        CallStackContext::TraceFailure(v17, "CMFByteStreamOnInputStream::_BeginRead", 756, -1072873851);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        &WPP_be105526232037934c214e06a667adcd_Traceguids,
        a1,
        -1072873851);
  }
LABEL_14:
  if ( v39 )
    CBaseOperation::Release(v39);
  if ( v11 )
    v11->Release(v11);
  LeaveCriticalSection(v10);
  CallStackScopeTrace::~CallStackScopeTrace(&v35);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180012864  push    rbp
0x180012866  push    rbx
0x180012867  push    rsi
0x180012868  push    rdi
0x180012869  push    r12
0x18001286b  push    r13
0x18001286d  push    r14
0x18001286f  push    r15
0x180012871  lea     rbp, [rsp-0Fh]
0x180012876  sub     rsp, 88h
0x18001287d  mov     rax, cs:__security_cookie
0x180012884  xor     rax, rsp
0x180012887  mov     [rbp+47h+var_50], rax
0x18001288b  mov     rax, [rbp+47h+arg_20]
0x18001288f  mov     rbx, r9
0x180012892  mov     r14, [rbp+47h+arg_28]
0x180012896  mov     r13, rdx
0x180012899  mov     r12d, r8d
0x18001289c  lea     rdx, aCmfbytestreamo_78; "CMFByteStreamOnInputStream::_BeginRead"
0x1800128a3  mov     rdi, rcx
0x1800128a6  mov     qword ptr [rbp+47h+ActivityId.Data1], rbx
0x1800128aa  mov     r8d, 2E7h; int
0x1800128b0  mov     [rbp+47h+var_68], rax
0x1800128b4  lea     rcx, [rbp+47h+var_90]; this
0x1800128b8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800128bd  lea     r15, [rdi+10h]
0x1800128c1  mov     rcx, r15; lpCriticalSection
0x1800128c4  mov     [rbp+47h+lpCriticalSection], r15
0x1800128c8  call    cs:__imp_EnterCriticalSection
0x1800128ce  xor     esi, esi
0x1800128d0  mov     [rbp+47h+result], rsi
0x1800128d4  mov     [rbp+47h+var_70], rsi
0x1800128d8  mov     [rbp+47h+var_78], esi
0x1800128db  test    r14, r14
0x1800128de  jnz     loc_180012DE2
0x1800128e4  cmp     [rdi+258h], esi
0x1800128ea  jz      loc_180012A36
0x1800128f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x1800128f7  lea     r15, WPP_be105526232037934c214e06a667adcd_Traceguids
0x1800128fe  jnb     loc_180012DEA
0x180012904  mov     rdx, [rdi+278h]; unsigned __int64
0x18001290b  lea     rax, [rbp+47h+var_78]
0x18001290f  lea     rcx, [rdi+268h]; this
0x180012916  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x18001291b  mov     r9d, r12d; unsigned int
0x18001291e  mov     r8, r13; unsigned __int8 *
0x180012921  call    ?GetBuffer@CByteStreamCache@@QEAAJ_KPEAEKPEAK@Z; CByteStreamCache::GetBuffer(unsigned __int64,uchar *,ulong,ulong *)
0x180012926  lea     rcx, [rbp+47h+result]
0x18001292a  test    eax, eax
0x18001292c  jns     loc_180012E1B
0x180012932  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180012937  mov     rcx, [rdi+278h]; int
0x18001293e  lea     rax, [rbp+47h+result]
0x180012942  mov     [rsp+0C0h+var_98], rax; __int64
0x180012947  lea     r9, [rdi+238h]; struct IMFAsyncCallback *
0x18001294e  mov     r8d, r12d; int
0x180012951  mov     [rsp+0C0h+var_A0], rsi; struct IUnknown *
0x180012956  mov     rdx, r13; int
0x180012959  call    ?CreateInstance@?$CByteStreamResult@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@SAJ_KPEAEIPEAUIMFAsyncCallback@@PEAUIUnknown@@PEAPEAV1@@Z; CByteStreamResult<Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>>::CreateInstance(unsigned __int64,uchar *,uint,IMFAsyncCallback *,IUnknown *,CByteStreamResult<Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>> * *)
0x18001295e  mov     ebx, eax
0x180012960  test    eax, eax
0x180012962  js      loc_180012C04
0x180012968  mov     rsi, [rbp+47h+result]
0x18001296c  lea     rcx, [rbp+47h+var_70]
0x180012970  mov     byte ptr [rsi+90h], 0
0x180012977  call    ?InternalRelease@?$ComPtr@VCByteStreamOperation@CMFByteStreamOnInputStream@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CMFByteStreamOnInputStream::CByteStreamOperation>::InternalRelease(void)
0x18001297c  mov     r9, [rbp+47h+var_68]
0x180012980  lea     rax, [rbp+47h+var_70]
0x180012984  mov     r8, qword ptr [rbp+47h+ActivityId.Data1]
0x180012988  mov     rdx, rsi
0x18001298b  mov     ecx, 1
0x180012990  mov     [rsp+0C0h+var_A0], rax
0x180012995  call    ?CreateInstance@CByteStreamOperation@CMFByteStreamOnInputStream@@SAJW4BYTESTREAM_OPERATION@2@PEAV?$CByteStreamResult@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@PEAUIMFAsyncCallback@@PEAUIUnknown@@PEAPEAV12@@Z; CMFByteStreamOnInputStream::CByteStreamOperation::CreateInstance(CMFByteStreamOnInputStream::BYTESTREAM_OPERATION,CByteStreamResult<Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>> *,IMFAsyncCallback *,IUnknown *,CMFByteStreamOnInputStream::CByteStreamOperation * *)
0x18001299a  mov     ebx, eax
0x18001299c  test    eax, eax
0x18001299e  js      loc_180012CAC
0x1800129a4  mov     rdx, [rbp+47h+var_70]; struct CBaseOperation *
0x1800129a8  lea     rcx, [rdi+50h]; this
0x1800129ac  call    ?QueueOperation@COpQueue@@QEAAJPEAVCBaseOperation@@H@Z; COpQueue::QueueOperation(CBaseOperation *,int)
0x1800129b1  mov     ebx, eax
0x1800129b3  test    eax, eax
0x1800129b5  js      loc_180012D3A
0x1800129bb  test    cs:Microsoft_Windows_MediaFoundation_PlatformEnableBits, 8
0x1800129c2  jnz     loc_180012E94
0x1800129c8  add     [rdi+278h], r12
0x1800129cf  test    r14, r14
0x1800129d2  jz      short loc_1800129DC
0x1800129d4  mov     rax, rsi
0x1800129d7  xor     esi, esi
0x1800129d9  mov     [r14], rax
0x1800129dc  mov     r15, [rbp+47h+lpCriticalSection]
0x1800129e0  mov     rcx, [rbp+47h+var_70]; this
0x1800129e4  test    rcx, rcx
0x1800129e7  jz      short loc_1800129EE
0x1800129e9  call    ?Release@CBaseOperation@@QEAAKXZ; CBaseOperation::Release(void)
0x1800129ee  test    rsi, rsi
0x1800129f1  jz      short loc_180012A02
0x1800129f3  mov     rdx, [rsi]
0x1800129f6  mov     rcx, rsi
0x1800129f9  mov     rax, [rdx+10h]
0x1800129fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a02  mov     rcx, r15; lpCriticalSection
0x180012a05  call    cs:__imp_LeaveCriticalSection
0x180012a0b  lea     rcx, [rbp+47h+var_90]; this
0x180012a0f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180012a14  mov     eax, ebx
0x180012a16  mov     rcx, [rbp+47h+var_50]
0x180012a1a  xor     rcx, rsp; StackCookie
0x180012a1d  call    __security_check_cookie
0x180012a22  add     rsp, 88h
0x180012a29  pop     r15
0x180012a2b  pop     r14
0x180012a2d  pop     r13
0x180012a2f  pop     r12
0x180012a31  pop     rdi
0x180012a32  pop     rsi
0x180012a33  pop     rbx
0x180012a34  pop     rbp
0x180012a35  retn
0x180012a36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180012a3d  mov     ebx, 0C00D3E85h
0x180012a42  test    rcx, rcx
0x180012a45  jz      short loc_180012A7E
0x180012a47  cmp     [rcx+8], sil
0x180012a4b  jnz     short loc_180012ABE
0x180012a4d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012a54  jb      short loc_1800129E0
0x180012a56  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a5d  lea     r8, WPP_be105526232037934c214e06a667adcd_Traceguids
0x180012a64  mov     edx, 58h ; 'X'
0x180012a69  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180012a6d  mov     r9, rdi
0x180012a70  mov     rcx, [rcx+10h]
0x180012a74  call    WPP_SF_qD
0x180012a79  jmp     loc_1800129E0
0x180012a7e  mov     rax, cs:stru_1801FC290.__vftable
0x180012a85  lea     rcx, stru_1801FC290
0x180012a8c  mov     edx, 7F0h
0x180012a91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012a98  mov     rax, [rax+8]
0x180012a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012aa1  test    eax, eax
0x180012aa3  jnz     short loc_180012AB5
0x180012aa5  lea     rcx, stru_1801F8A30
0x180012aac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012ab3  jmp     short loc_180012A47
0x180012ab5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012abc  jmp     short loc_180012A47
0x180012abe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012ac3  cmp     [rax+7CCh], ebx
0x180012ac9  jz      short loc_180012A4D
0x180012acb  mov     r9d, ebx; int
0x180012ace  lea     rdx, aCmfbytestreamo_78; "CMFByteStreamOnInputStream::_BeginRead"
0x180012ad5  mov     r8d, 2F4h; int
0x180012adb  mov     rcx, rax; this
0x180012ade  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012ae3  jmp     loc_180012A4D
0x180012ae8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012aef  test    rcx, rcx
0x180012af2  jnz     short loc_180012B29
0x180012af4  mov     rax, cs:stru_1801FC290.__vftable
0x180012afb  lea     rcx, stru_1801FC290
0x180012b02  mov     edx, 7F0h
0x180012b07  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012b0e  mov     rax, [rax+8]
0x180012b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b17  test    eax, eax
0x180012b19  jnz     short loc_180012B46
0x180012b1b  lea     rcx, stru_1801F8A30; this
0x180012b22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012b29  cmp     [rcx+8], sil
0x180012b2d  jnz     short loc_180012B4F
0x180012b2f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012b36  jb      loc_180012C73
0x180012b3c  mov     edx, 5Ah ; 'Z'
0x180012b41  jmp     loc_180012C59
0x180012b46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012b4d  jmp     short loc_180012B29
0x180012b4f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012b54  cmp     [rax+7CCh], ebx
0x180012b5a  jz      short loc_180012B2F
0x180012b5c  mov     r9d, ebx; int
0x180012b5f  lea     rdx, aCmfbytestreamo_78; "CMFByteStreamOnInputStream::_BeginRead"
0x180012b66  mov     r8d, 308h; int
0x180012b6c  mov     rcx, rax; this
0x180012b6f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012b74  jmp     short loc_180012B2F
0x180012b76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012b7d  test    rcx, rcx
0x180012b80  jnz     short loc_180012BB7
0x180012b82  mov     rax, cs:stru_1801FC290.__vftable
0x180012b89  lea     rcx, stru_1801FC290
0x180012b90  mov     edx, 7F0h
0x180012b95  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012b9c  mov     rax, [rax+8]
0x180012ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ba5  test    eax, eax
0x180012ba7  jnz     short loc_180012BD4
0x180012ba9  lea     rcx, stru_1801F8A30; this
0x180012bb0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012bb7  cmp     byte ptr [rcx+8], 0
0x180012bbb  jnz     short loc_180012BDD
0x180012bbd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012bc4  jb      loc_1800129DC
0x180012bca  mov     edx, 5Bh ; '['
0x180012bcf  jmp     loc_180012D93
0x180012bd4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012bdb  jmp     short loc_180012BB7
0x180012bdd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012be2  cmp     [rax+7CCh], ebx
0x180012be8  jz      short loc_180012BBD
0x180012bea  mov     r9d, ebx; int
0x180012bed  lea     rdx, aCmfbytestreamo_78; "CMFByteStreamOnInputStream::_BeginRead"
0x180012bf4  mov     r8d, 30Ch; int
0x180012bfa  mov     rcx, rax; this
0x180012bfd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012c02  jmp     short loc_180012BBD
0x180012c04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012c0b  test    rcx, rcx
0x180012c0e  jnz     short loc_180012C45
0x180012c10  mov     rax, cs:stru_1801FC290.__vftable
0x180012c17  lea     rcx, stru_1801FC290
0x180012c1e  mov     edx, 7F0h
0x180012c23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012c2a  mov     rax, [rax+8]
0x180012c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c33  test    eax, eax
0x180012c35  jnz     short loc_180012C7C
0x180012c37  lea     rcx, stru_1801F8A30; this
0x180012c3e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012c45  cmp     [rcx+8], sil
0x180012c49  jnz     short loc_180012C85
0x180012c4b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012c52  jb      short loc_180012C73
0x180012c54  mov     edx, 5Ch ; '\'
0x180012c59  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c60  mov     r9, rdi
0x180012c63  mov     r8, r15
0x180012c66  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180012c6a  mov     rcx, [rcx+10h]
0x180012c6e  call    WPP_SF_qD
0x180012c73  mov     rsi, [rbp+47h+result]
0x180012c77  jmp     loc_1800129DC
0x180012c7c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012c83  jmp     short loc_180012C45
0x180012c85  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012c8a  cmp     [rax+7CCh], ebx
0x180012c90  jz      short loc_180012C4B
0x180012c92  mov     r9d, ebx; int
0x180012c95  lea     rdx, aCmfbytestreamo_78; "CMFByteStreamOnInputStream::_BeginRead"
0x180012c9c  mov     r8d, 320h; int
0x180012ca2  mov     rcx, rax; this
0x180012ca5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012caa  jmp     short loc_180012C4B
0x180012cac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012cb3  test    rcx, rcx
0x180012cb6  jnz     short loc_180012CED
0x180012cb8  mov     rax, cs:stru_1801FC290.__vftable
0x180012cbf  lea     rcx, stru_1801FC290
0x180012cc6  mov     edx, 7F0h
0x180012ccb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012cd2  mov     rax, [rax+8]
0x180012cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cdb  test    eax, eax
0x180012cdd  jnz     short loc_180012D0A
0x180012cdf  lea     rcx, stru_1801F8A30; this
0x180012ce6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012ced  cmp     byte ptr [rcx+8], 0
0x180012cf1  jnz     short loc_180012D13
0x180012cf3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012cfa  jb      loc_1800129DC
0x180012d00  mov     edx, 5Dh ; ']'
0x180012d05  jmp     loc_180012D93
0x180012d0a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d11  jmp     short loc_180012CED
0x180012d13  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012d18  cmp     [rax+7CCh], ebx
0x180012d1e  jz      short loc_180012CF3
0x180012d20  mov     r9d, ebx; int
0x180012d23  lea     rdx, aCmfbytestreamo_78; "CMFByteStreamOnInputStream::_BeginRead"
0x180012d2a  mov     r8d, 32Dh; int
0x180012d30  mov     rcx, rax; this
0x180012d33  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180012d38  jmp     short loc_180012CF3
0x180012d3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d41  test    rcx, rcx
0x180012d44  jnz     short loc_180012D7B
0x180012d46  mov     rax, cs:stru_1801FC290.__vftable
0x180012d4d  lea     rcx, stru_1801FC290
0x180012d54  mov     edx, 7F0h
0x180012d59  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d60  mov     rax, [rax+8]
0x180012d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d69  test    eax, eax
0x180012d6b  jnz     short loc_180012DB2
0x180012d6d  lea     rcx, stru_1801F8A30; this
0x180012d74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180012d7b  cmp     byte ptr [rcx+8], 0
0x180012d7f  jnz     short loc_180012DBB
0x180012d81  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
  ... truncated ...
```
