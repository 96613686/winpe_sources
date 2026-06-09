# CMFAppServiceConnectorBase::RuntimeClassInitialize(IMFAttributes *)

- ea: `0x180165ffc`
- end: `0x18016658d`
- name: `?RuntimeClassInitialize@CMFAppServiceConnectorBase@@QEAAJPEAUIMFAttributes@@@Z`
- size: `1425`
- prototype: `int(CMFAppServiceConnectorBase *__hidden this, struct IMFAttributes *)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180118d98`
- `0x180159474`
- `0x180166594`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003f178`
- `0x180040cb0`
- `0x180122d9c`
- `0x180159a08`
- `0x180165ffc`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016655e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180166568`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180166572`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016655e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180166568`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180166572`
- `ext-ms-win-media-codecpack-mounting-l1-1-0!MountMediaCodecAppServicePackage` at `0x180166324`
- `ext-ms-win-media-codecpack-mounting-l1-1-0!MountMediaCodecAppServicePackage` at `0x180166324`

## string_xrefs

- `0x180166027`: `CMFAppServiceConnectorBase::RuntimeClassInitialize`

## pseudocode

```c
__int64 __fastcall CMFAppServiceConnectorBase::RuntimeClassInitialize(
        CMFAppServiceConnectorBase *this,
        struct IMFAttributes *a2)
{
  int v4; // ebx
  CallStackTracing *v5; // rcx
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  IMFAttributes_vtbl *v8; // rax
  CallStackTracing *v9; // rcx
  struct CallStackContext *v10; // rax
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  LPVOID v23; // [rsp+38h] [rbp-18h] BYREF
  LPVOID v24[2]; // [rsp+40h] [rbp-10h] BYREF
  CallStackScopeTrace v25; // [rsp+80h] [rbp+30h] BYREF
  int v26; // [rsp+88h] [rbp+38h] BYREF

  v24[0] = 0;
  v23 = 0;
  pv = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v25, "CMFAppServiceConnectorBase::RuntimeClassInitialize", 133);
  v4 = DeployPackageIfNeeded(a2);
  if ( v4 >= 0 )
  {
    v8 = a2->__vftable;
    v26 = 0;
    v4 = v8->GetAllocatedString(a2, &MF_MEDIA_EXTENSION_APP_SERVICE_NAME, (wchar_t **)v24, (unsigned int *)&v26);
    if ( v4 >= 0 )
    {
      v4 = a2->GetAllocatedString(
             a2,
             (const _GUID *)&MF_MEDIA_EXTENSION_PACKAGE_FAMILY_NAME,
             (wchar_t **)&v23,
             (unsigned int *)&v26);
      if ( v4 >= 0 )
      {
        v4 = a2->GetAllocatedString(
               a2,
               (const _GUID *)&MF_MEDIA_EXTENSION_PACKAGE_FULL_NAME,
               (wchar_t **)&pv,
               (unsigned int *)&v26);
        if ( v4 >= 0 )
        {
          if ( (unsigned __int8)IsMountMediaCodecAppServicePackagePresent() )
            MountMediaCodecAppServicePackage(pv);
          v4 = Microsoft::WRL::Wrappers::HString::Set<TSmartCoTaskMemory<unsigned short>>((char *)this + 80, v24);
          if ( v4 >= 0 )
          {
            v4 = Microsoft::WRL::Wrappers::HString::Set<TSmartCoTaskMemory<unsigned short>>((char *)this + 88, &v23);
            if ( v4 >= 0 )
            {
              v4 = Microsoft::WRL::Wrappers::HString::Set<TSmartCoTaskMemory<unsigned short>>((char *)this + 96, &pv);
              if ( v4 >= 0 )
              {
                a2->GetGUID(a2, (const _GUID *)&MF_TELEMETRY_OBJECT_INSTANCE_ATTRIBUTE, (_GUID *)((char *)this + 104));
                *((_BYTE *)this + 120) = (unsigned int)MFGetAttributeUINT32(
                                                         a2,
                                                         &MF_MEDIA_EXTENSION_OPEN_APPSERVICE_CONNECTION_VIA_BROKER,
                                                         0) != 0;
                *((_BYTE *)this + 121) = (unsigned int)MFGetAttributeUINT32(
                                                         a2,
                                                         &MF_MEDIA_EXTENSION_WEB_PLATFORM_ALLOWED,
                                                         0) != 0;
                goto LABEL_75;
              }
              v19 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v19 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v19 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v19->m_fEnabled )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v19);
                if ( ThreadRelativeContext->m_result != v4 )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "CMFAppServiceConnectorBase::RuntimeClassInitialize",
                    149,
                    v4);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              {
                v7 = 21;
                goto LABEL_11;
              }
            }
            else
            {
              v17 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v17 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v17 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v17->m_fEnabled )
              {
                v18 = CallStackTracing::GetThreadRelativeContext(v17);
                if ( v18->m_result != v4 )
                  CallStackContext::TraceFailure(v18, "CMFAppServiceConnectorBase::RuntimeClassInitialize", 148, v4);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              {
                v7 = 20;
                goto LABEL_11;
              }
            }
          }
          else
          {
            v15 = CallStackTracing::s_wpInstance;
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
              if ( v16->m_result != v4 )
                CallStackContext::TraceFailure(v16, "CMFAppServiceConnectorBase::RuntimeClassInitialize", 147, v4);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v7 = 19;
              goto LABEL_11;
            }
          }
        }
        else
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
            if ( v14->m_result != v4 )
              CallStackContext::TraceFailure(v14, "CMFAppServiceConnectorBase::RuntimeClassInitialize", 138, v4);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v7 = 18;
            goto LABEL_11;
          }
        }
      }
      else
      {
        v11 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v11 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v11 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v11->m_fEnabled )
        {
          v12 = CallStackTracing::GetThreadRelativeContext(v11);
          if ( v12->m_result != v4 )
            CallStackContext::TraceFailure(v12, "CMFAppServiceConnectorBase::RuntimeClassInitialize", 137, v4);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v7 = 17;
          goto LABEL_11;
        }
      }
    }
    else
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
        if ( v10->m_result != v4 )
          CallStackContext::TraceFailure(v10, "CMFAppServiceConnectorBase::RuntimeClassInitialize", 136, v4);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v7 = 16;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v5 = CallStackTracing::s_wpInstance;
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
      v6 = CallStackTracing::GetThreadRelativeContext(v5);
      if ( v6->m_result != v4 )
        CallStackContext::TraceFailure(v6, "CMFAppServiceConnectorBase::RuntimeClassInitialize", 133, v4);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v7 = 15;
LABEL_11:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_29e89521b84936885e6d012356985b16_Traceguids, this, v4);
    }
  }
LABEL_75:
  CallStackScopeTrace::~CallStackScopeTrace(&v25);
  CoTaskMemFree(pv);
  CoTaskMemFree(v23);
  CoTaskMemFree(v24[0]);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180165ffc  mov     [rsp-18h+arg_0], rbx
0x180166001  mov     [rsp-18h+arg_8], rsi
0x180166006  push    rbp
0x180166007  push    rdi
0x180166008  push    r15
0x18016600a  mov     rbp, rsp
0x18016600d  sub     rsp, 50h
0x180166011  mov     rsi, rdx
0x180166014  mov     [rbp+var_10], 0
0x18016601c  mov     rdi, rcx
0x18016601f  mov     [rbp+var_18], 0
0x180166027  lea     r15, aCmfappservicec_1; "CMFAppServiceConnectorBase::RuntimeClas"...
0x18016602e  mov     [rbp+pv], 0
0x180166036  mov     rdx, r15; char *
0x180166039  lea     rcx, [rbp+arg_10]; this
0x18016603d  mov     r8d, 85h; int
0x180166043  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180166048  mov     rcx, rsi; struct IMFAttributes *
0x18016604b  call    ?DeployPackageIfNeeded@@YAJPEAUIMFAttributes@@@Z; DeployPackageIfNeeded(IMFAttributes *)
0x180166050  mov     ebx, eax
0x180166052  test    eax, eax
0x180166054  jns     loc_180166100
0x18016605a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180166061  test    rcx, rcx
0x180166064  jnz     short loc_1801660A4
0x180166066  mov     rdx, cs:stru_1801FC290.__vftable
0x18016606d  lea     rcx, stru_1801FC290
0x180166074  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016607b  mov     rax, [rdx+8]
0x18016607f  mov     edx, 7F0h
0x180166084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180166089  test    eax, eax
0x18016608b  jnz     short loc_18016609D
0x18016608d  lea     rcx, stru_1801F8A30
0x180166094  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016609b  jmp     short loc_1801660A4
0x18016609d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801660a4  cmp     byte ptr [rcx+8], 0
0x1801660a8  jz      short loc_1801660CB
0x1801660aa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801660af  cmp     [rax+7CCh], ebx
0x1801660b5  jz      short loc_1801660CB
0x1801660b7  mov     r9d, ebx; int
0x1801660ba  mov     r8d, 85h; int
0x1801660c0  mov     rdx, r15; char *
0x1801660c3  mov     rcx, rax; this
0x1801660c6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801660cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801660d2  jb      loc_180166551
0x1801660d8  mov     edx, 0Fh
0x1801660dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1801660e4  lea     r8, WPP_29e89521b84936885e6d012356985b16_Traceguids
0x1801660eb  mov     r9, rdi
0x1801660ee  mov     [rsp+50h+var_30], ebx
0x1801660f2  mov     rcx, [rcx+10h]
0x1801660f6  call    WPP_SF_qD
0x1801660fb  jmp     loc_180166551
0x180166100  mov     rax, [rsi]
0x180166103  lea     r9, [rbp+arg_18]
0x180166107  lea     r8, [rbp+var_10]
0x18016610b  mov     [rbp+arg_18], 0
0x180166112  lea     rdx, MF_MEDIA_EXTENSION_APP_SERVICE_NAME
0x180166119  mov     rcx, rsi
0x18016611c  mov     rax, [rax+68h]
0x180166120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180166125  mov     ebx, eax
0x180166127  test    eax, eax
0x180166129  jns     loc_1801661B7
0x18016612f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180166136  test    rcx, rcx
0x180166139  jnz     short loc_180166179
0x18016613b  mov     rax, cs:stru_1801FC290.__vftable
0x180166142  lea     rcx, stru_1801FC290
0x180166149  mov     edx, 7F0h
0x18016614e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180166155  mov     rax, [rax+8]
0x180166159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016615e  test    eax, eax
0x180166160  jnz     short loc_180166172
0x180166162  lea     rcx, stru_1801F8A30
0x180166169  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180166170  jmp     short loc_180166179
0x180166172  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180166179  cmp     byte ptr [rcx+8], 0
0x18016617d  jz      short loc_1801661A0
0x18016617f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180166184  cmp     [rax+7CCh], ebx
0x18016618a  jz      short loc_1801661A0
0x18016618c  mov     r9d, ebx; int
0x18016618f  mov     r8d, 88h; int
0x180166195  mov     rdx, r15; char *
0x180166198  mov     rcx, rax; this
0x18016619b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801661a0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801661a7  jb      loc_180166551
0x1801661ad  mov     edx, 10h
0x1801661b2  jmp     loc_1801660DD
0x1801661b7  mov     rax, [rsi]
0x1801661ba  lea     r9, [rbp+arg_18]
0x1801661be  lea     r8, [rbp+var_18]
0x1801661c2  mov     rcx, rsi
0x1801661c5  lea     rdx, MF_MEDIA_EXTENSION_PACKAGE_FAMILY_NAME
0x1801661cc  mov     rax, [rax+68h]
0x1801661d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801661d5  mov     ebx, eax
0x1801661d7  test    eax, eax
0x1801661d9  jns     loc_180166267
0x1801661df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801661e6  test    rcx, rcx
0x1801661e9  jnz     short loc_180166229
0x1801661eb  mov     rax, cs:stru_1801FC290.__vftable
0x1801661f2  lea     rcx, stru_1801FC290
0x1801661f9  mov     edx, 7F0h
0x1801661fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180166205  mov     rax, [rax+8]
0x180166209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016620e  test    eax, eax
0x180166210  jnz     short loc_180166222
0x180166212  lea     rcx, stru_1801F8A30
0x180166219  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180166220  jmp     short loc_180166229
0x180166222  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180166229  cmp     byte ptr [rcx+8], 0
0x18016622d  jz      short loc_180166250
0x18016622f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180166234  cmp     [rax+7CCh], ebx
0x18016623a  jz      short loc_180166250
0x18016623c  mov     r9d, ebx; int
0x18016623f  mov     r8d, 89h; int
0x180166245  mov     rdx, r15; char *
0x180166248  mov     rcx, rax; this
0x18016624b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180166250  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180166257  jb      loc_180166551
0x18016625d  mov     edx, 11h
0x180166262  jmp     loc_1801660DD
0x180166267  mov     rax, [rsi]
0x18016626a  lea     r9, [rbp+arg_18]
0x18016626e  lea     r8, [rbp+pv]
0x180166272  mov     rcx, rsi
0x180166275  lea     rdx, MF_MEDIA_EXTENSION_PACKAGE_FULL_NAME
0x18016627c  mov     rax, [rax+68h]
0x180166280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180166285  mov     ebx, eax
0x180166287  test    eax, eax
0x180166289  jns     loc_180166317
0x18016628f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180166296  test    rcx, rcx
0x180166299  jnz     short loc_1801662D9
0x18016629b  mov     rax, cs:stru_1801FC290.__vftable
0x1801662a2  lea     rcx, stru_1801FC290
0x1801662a9  mov     edx, 7F0h
0x1801662ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801662b5  mov     rax, [rax+8]
0x1801662b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801662be  test    eax, eax
0x1801662c0  jnz     short loc_1801662D2
0x1801662c2  lea     rcx, stru_1801F8A30
0x1801662c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801662d0  jmp     short loc_1801662D9
0x1801662d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801662d9  cmp     byte ptr [rcx+8], 0
0x1801662dd  jz      short loc_180166300
0x1801662df  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801662e4  cmp     [rax+7CCh], ebx
0x1801662ea  jz      short loc_180166300
0x1801662ec  mov     r9d, ebx; int
0x1801662ef  mov     r8d, 8Ah; int
0x1801662f5  mov     rdx, r15; char *
0x1801662f8  mov     rcx, rax; this
0x1801662fb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180166300  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180166307  jb      loc_180166551
0x18016630d  mov     edx, 12h
0x180166312  jmp     loc_1801660DD
0x180166317  call    IsMountMediaCodecAppServicePackagePresent
0x18016631c  test    al, al
0x18016631e  jz      short loc_18016632A
0x180166320  mov     rcx, [rbp+pv]
0x180166324  call    cs:__imp_MountMediaCodecAppServicePackage
0x18016632a  lea     rcx, [rdi+50h]
0x18016632e  lea     rdx, [rbp+var_10]
0x180166332  call    ??$Set@V?$TSmartCoTaskMemory@G@@@HString@Wrappers@WRL@Microsoft@@QEAAJAEBV?$TSmartCoTaskMemory@G@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<TSmartCoTaskMemory<ushort>>(TSmartCoTaskMemory<ushort> const &,Microsoft::WRL::Details::Dummy)
0x180166337  mov     ebx, eax
0x180166339  test    eax, eax
0x18016633b  jns     loc_1801663C9
0x180166341  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180166348  test    rcx, rcx
0x18016634b  jnz     short loc_18016638B
0x18016634d  mov     rax, cs:stru_1801FC290.__vftable
0x180166354  lea     rcx, stru_1801FC290
0x18016635b  mov     edx, 7F0h
0x180166360  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180166367  mov     rax, [rax+8]
0x18016636b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180166370  test    eax, eax
0x180166372  jnz     short loc_180166384
0x180166374  lea     rcx, stru_1801F8A30
0x18016637b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180166382  jmp     short loc_18016638B
0x180166384  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18016638b  cmp     byte ptr [rcx+8], 0
0x18016638f  jz      short loc_1801663B2
0x180166391  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180166396  cmp     [rax+7CCh], ebx
0x18016639c  jz      short loc_1801663B2
0x18016639e  mov     r9d, ebx; int
0x1801663a1  mov     r8d, 93h; int
0x1801663a7  mov     rdx, r15; char *
0x1801663aa  mov     rcx, rax; this
0x1801663ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801663b2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801663b9  jb      loc_180166551
0x1801663bf  mov     edx, 13h
0x1801663c4  jmp     loc_1801660DD
0x1801663c9  lea     rcx, [rdi+58h]
0x1801663cd  lea     rdx, [rbp+var_18]
0x1801663d1  call    ??$Set@V?$TSmartCoTaskMemory@G@@@HString@Wrappers@WRL@Microsoft@@QEAAJAEBV?$TSmartCoTaskMemory@G@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<TSmartCoTaskMemory<ushort>>(TSmartCoTaskMemory<ushort> const &,Microsoft::WRL::Details::Dummy)
0x1801663d6  mov     ebx, eax
0x1801663d8  test    eax, eax
0x1801663da  jns     loc_180166468
0x1801663e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801663e7  test    rcx, rcx
0x1801663ea  jnz     short loc_18016642A
0x1801663ec  mov     rax, cs:stru_1801FC290.__vftable
0x1801663f3  lea     rcx, stru_1801FC290
0x1801663fa  mov     edx, 7F0h
0x1801663ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180166406  mov     rax, [rax+8]
0x18016640a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016640f  test    eax, eax
0x180166411  jnz     short loc_180166423
0x180166413  lea     rcx, stru_1801F8A30
0x18016641a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180166421  jmp     short loc_18016642A
0x180166423  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18016642a  cmp     byte ptr [rcx+8], 0
0x18016642e  jz      short loc_180166451
0x180166430  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180166435  cmp     [rax+7CCh], ebx
0x18016643b  jz      short loc_180166451
0x18016643d  mov     r9d, ebx; int
0x180166440  mov     r8d, 94h; int
0x180166446  mov     rdx, r15; char *
0x180166449  mov     rcx, rax; this
0x18016644c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180166451  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180166458  jb      loc_180166551
0x18016645e  mov     edx, 14h
0x180166463  jmp     loc_1801660DD
0x180166468  lea     rcx, [rdi+60h]
0x18016646c  lea     rdx, [rbp+pv]
0x180166470  call    ??$Set@V?$TSmartCoTaskMemory@G@@@HString@Wrappers@WRL@Microsoft@@QEAAJAEBV?$TSmartCoTaskMemory@G@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<TSmartCoTaskMemory<ushort>>(TSmartCoTaskMemory<ushort> const &,Microsoft::WRL::Details::Dummy)
0x180166475  mov     ebx, eax
0x180166477  test    eax, eax
0x180166479  jns     loc_180166503
0x18016647f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180166486  test    rcx, rcx
0x180166489  jnz     short loc_1801664C9
0x18016648b  mov     rax, cs:stru_1801FC290.__vftable
0x180166492  lea     rcx, stru_1801FC290
0x180166499  mov     edx, 7F0h
0x18016649e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801664a5  mov     rax, [rax+8]
0x1801664a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801664ae  test    eax, eax
0x1801664b0  jnz     short loc_1801664C2
0x1801664b2  lea     rcx, stru_1801F8A30
0x1801664b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801664c0  jmp     short loc_1801664C9
0x1801664c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801664c9  cmp     byte ptr [rcx+8], 0
0x1801664cd  jz      short loc_1801664F0
0x1801664cf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801664d4  cmp     [rax+7CCh], ebx
0x1801664da  jz      short loc_1801664F0
0x1801664dc  mov     r9d, ebx; int
0x1801664df  mov     r8d, 95h; int
0x1801664e5  mov     rdx, r15; char *
0x1801664e8  mov     rcx, rax; this
0x1801664eb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801664f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801664f7  jb      short loc_180166551
0x1801664f9  mov     edx, 15h
0x1801664fe  jmp     loc_1801660DD
0x180166503  mov     rax, [rsi]
0x180166506  lea     r8, [rdi+68h]
0x18016650a  lea     rdx, MF_TELEMETRY_OBJECT_INSTANCE_ATTRIBUTE
0x180166511  mov     rcx, rsi
0x180166514  mov     rax, [rax+50h]
0x180166518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016651d  xor     r8d, r8d
0x180166520  lea     rdx, MF_MEDIA_EXTENSION_OPEN_APPSERVICE_CONNECTION_VIA_BROKER
0x180166527  mov     rcx, rsi
0x18016652a  call    MFGetAttributeUINT32
0x18016652f  test    eax, eax
0x180166531  lea     rdx, MF_MEDIA_EXTENSION_WEB_PLATFORM_ALLOWED
0x180166538  mov     rcx, rsi
0x18016653b  setnz   al
0x18016653e  xor     r8d, r8d
  ... truncated ...
```
