# CMFContentDecryptorContext::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x1800391a0`
- end: `0x1800399cb`
- name: `?GetService@CMFContentDecryptorContext@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `2091`
- prototype: `__int64 __fastcall(CMFContentDecryptorContext *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800391a0`
- `0x180082e30`
- `0x1800fcd50`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800391c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800391c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039350`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039350`

## string_xrefs

- `0x1800391cd`: `CMFContentDecryptorContext::GetService`
- `0x180039559`: `CMFContentDecryptorContext::GetService`
- `0x18003960e`: `CMFContentDecryptorContext::GetService`
- `0x18003969c`: `CMFContentDecryptorContext::GetService`
- `0x18003972a`: `CMFContentDecryptorContext::GetService`
- `0x1800397b8`: `CMFContentDecryptorContext::GetService`
- `0x1800397ef`: `CMFContentDecryptorContext::GetService`
- `0x180039880`: `CMFContentDecryptorContext::GetService`
- `0x1800398b7`: `CMFContentDecryptorContext::GetService`
- `0x1800398e5`: `CMFContentDecryptorContext::GetService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFContentDecryptorContext::GetService(
        CMFContentDecryptorContext *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  int ContentProtectionDevice; // ebx
  CallStackTracing *v12; // rcx
  __int64 v13; // rdx
  char *v14; // r9
  CallStackTracing *v15; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 (__fastcall ***v22)(_QWORD, const struct _GUID *, void **); // rcx
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rcx
  __int64 v25; // rdx
  struct CallStackContext *v26; // rax
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  struct CallStackContext *v35; // rax
  CallStackTracing *v36; // rcx
  struct CallStackContext *v37; // rax
  struct CallStackContext *v38; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v40; // [rsp+80h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v40, "CMFContentDecryptorContext::GetService", 203);
  *a4 = 0;
  v8 = *(_QWORD *)&MF_CONTENT_DECRYPTOR_SERVICE.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&MF_CONTENT_DECRYPTOR_SERVICE.Data1 == *(_QWORD *)&a2->Data1 )
    v8 = *(_QWORD *)MF_CONTENT_DECRYPTOR_SERVICE.Data4 - *(_QWORD *)a2->Data4;
  if ( v8 )
  {
    ContentProtectionDevice = -1072875846;
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v15);
      if ( ThreadRelativeContext->m_result != -1072875846 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFContentDecryptorContext::GetService",
          245,
          -1072875846);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v14 = (char *)this - 24;
      v13 = 50;
      goto LABEL_23;
    }
    goto LABEL_25;
  }
  if ( *((_QWORD *)this + 5) )
  {
    v40 = 0;
    ContentProtectionDevice = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 5))(
                                *((_QWORD *)this + 5),
                                &GUID_fa993888_4383_415a_a930_dd472a8cf6f7,
                                &v40);
    if ( ContentProtectionDevice < 0 )
    {
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
        v26 = CallStackTracing::GetThreadRelativeContext(v24);
        if ( v26->m_result != ContentProtectionDevice )
          CallStackContext::TraceFailure(v26, "CMFContentDecryptorContext::GetService", 212, ContentProtectionDevice);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_68;
      v25 = 42;
    }
    else
    {
      ContentProtectionDevice = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, const struct _GUID *, void **))(*(_QWORD *)v40 + 24LL))(
                                  v40,
                                  a2,
                                  a3,
                                  a4);
      if ( ContentProtectionDevice >= 0 )
        goto LABEL_68;
      v27 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v27 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v27->m_fEnabled )
      {
        v28 = CallStackTracing::GetThreadRelativeContext(v27);
        if ( v28->m_result != ContentProtectionDevice )
          CallStackContext::TraceFailure(v28, "CMFContentDecryptorContext::GetService", 213, ContentProtectionDevice);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_68;
      v25 = 43;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v25,
      &WPP_140556a5762535acbe84c7dbcbc943ae_Traceguids,
      (char *)this - 24,
      ContentProtectionDevice);
LABEL_68:
    ATL::CComPtrBase<CMFSimulatedContentProtectionDevice>::~CComPtrBase<CMFSimulatedContentProtectionDevice>(&v40);
    goto LABEL_25;
  }
  v9 = *(_QWORD *)&GUID_a7f026da_a5f8_4487_a564_15e34357651e.Data1 - *(_QWORD *)&a3->Data1;
  if ( *(_QWORD *)&GUID_a7f026da_a5f8_4487_a564_15e34357651e.Data1 == *(_QWORD *)&a3->Data1 )
    v9 = *(_QWORD *)GUID_a7f026da_a5f8_4487_a564_15e34357651e.Data4 - *(_QWORD *)a3->Data4;
  if ( !v9 )
    goto LABEL_11;
  v10 = *(_QWORD *)&GUID_61f21c45_3c0e_4a74_9cea_67100d9ad5e4.Data1 - *(_QWORD *)&a3->Data1;
  if ( *(_QWORD *)&GUID_61f21c45_3c0e_4a74_9cea_67100d9ad5e4.Data1 == *(_QWORD *)&a3->Data1 )
    v10 = *(_QWORD *)GUID_61f21c45_3c0e_4a74_9cea_67100d9ad5e4.Data4 - *(_QWORD *)a3->Data4;
  if ( v10 )
  {
    v17 = *(_QWORD *)&GUID_9b32f9ad_bdcc_40a6_a39d_d5c865845720.Data1 - *(_QWORD *)&a3->Data1;
    if ( *(_QWORD *)&GUID_9b32f9ad_bdcc_40a6_a39d_d5c865845720.Data1 == *(_QWORD *)&a3->Data1 )
      v17 = *(_QWORD *)GUID_9b32f9ad_bdcc_40a6_a39d_d5c865845720.Data4 - *(_QWORD *)a3->Data4;
    if ( v17 )
    {
      v18 = *(_QWORD *)&GUID_10ec4d5b_975a_4689_b9e4_d0aac30fe333.Data1 - *(_QWORD *)&a3->Data1;
      if ( *(_QWORD *)&GUID_10ec4d5b_975a_4689_b9e4_d0aac30fe333.Data1 == *(_QWORD *)&a3->Data1 )
        v18 = *(_QWORD *)GUID_10ec4d5b_975a_4689_b9e4_d0aac30fe333.Data4 - *(_QWORD *)a3->Data4;
      if ( !v18 )
        goto LABEL_123;
      v19 = *(_QWORD *)&GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140.Data1 - *(_QWORD *)&a3->Data1;
      if ( *(_QWORD *)&GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140.Data1 == *(_QWORD *)&a3->Data1 )
        v19 = *(_QWORD *)GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140.Data4 - *(_QWORD *)a3->Data4;
      if ( v19 )
      {
        v20 = *(_QWORD *)&GUID_e6257174_a060_4c9a_a088_3b1b471cad28.Data1 - *(_QWORD *)&a3->Data1;
        if ( *(_QWORD *)&GUID_e6257174_a060_4c9a_a088_3b1b471cad28.Data1 == *(_QWORD *)&a3->Data1 )
          v20 = *(_QWORD *)GUID_e6257174_a060_4c9a_a088_3b1b471cad28.Data4 - *(_QWORD *)a3->Data4;
        if ( v20 )
        {
          ContentProtectionDevice = 0;
          v21 = *(_QWORD *)&GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0.Data1 - *(_QWORD *)&a3->Data1;
          if ( *(_QWORD *)&GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0.Data1 == *(_QWORD *)&a3->Data1 )
            v21 = *(_QWORD *)GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0.Data4 - *(_QWORD *)a3->Data4;
          if ( !v21 )
          {
            v22 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)this + 4);
            if ( v22 )
            {
              ContentProtectionDevice = (**v22)(v22, a3, a4);
              if ( ContentProtectionDevice < 0 )
              {
                v23 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::s_wpInstance = &stru_1801FC290;
                  if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                  {
                    v23 = CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v23 = &stru_1801F8A30;
                    CallStackTracing::s_wpInstance = &stru_1801F8A30;
                  }
                }
                if ( v23->m_fEnabled )
                {
                  v35 = CallStackTracing::GetThreadRelativeContext(v23);
                  if ( v35->m_result != ContentProtectionDevice )
                    CallStackContext::TraceFailure(
                      v35,
                      "CMFContentDecryptorContext::GetService",
                      239,
                      ContentProtectionDevice);
                }
                if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                {
                  v13 = 49;
                  goto LABEL_18;
                }
              }
            }
          }
        }
        else if ( *((_QWORD *)this + 6)
               || (ContentProtectionDevice = DoCreateContentProtectionDevice(
                                               (const struct _GUID *)((char *)this + 56),
                                               (struct IMFContentDecryptorContext *)(((unsigned __int64)this - 8)
                                                                                   & ((unsigned __int128)-(__int128)((unsigned __int64)this - 24) >> 64)),
                                               (struct IMFContentProtectionDevice **)this + 6),
                   ContentProtectionDevice >= 0) )
        {
          ContentProtectionDevice = (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 6))(
                                      *((_QWORD *)this + 6),
                                      a3,
                                      a4);
          if ( ContentProtectionDevice < 0 )
          {
            v33 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v33 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v33 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v33->m_fEnabled )
            {
              v34 = CallStackTracing::GetThreadRelativeContext(v33);
              if ( v34->m_result != ContentProtectionDevice )
                CallStackContext::TraceFailure(
                  v34,
                  "CMFContentDecryptorContext::GetService",
                  235,
                  ContentProtectionDevice);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v13 = 48;
              goto LABEL_18;
            }
          }
        }
        else
        {
          v31 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v31 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v31->m_fEnabled )
          {
            v32 = CallStackTracing::GetThreadRelativeContext(v31);
            if ( v32->m_result != ContentProtectionDevice )
              CallStackContext::TraceFailure(
                v32,
                "CMFContentDecryptorContext::GetService",
                233,
                ContentProtectionDevice);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v13 = 47;
            goto LABEL_18;
          }
        }
      }
      else
      {
LABEL_123:
        ContentProtectionDevice = (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 3))(
                                    *((_QWORD *)this + 3),
                                    a3,
                                    a4);
        if ( ContentProtectionDevice < 0 )
        {
          v36 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v36 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v36 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v36->m_fEnabled )
          {
            v37 = CallStackTracing::GetThreadRelativeContext(v36);
            if ( v37->m_result != ContentProtectionDevice )
              CallStackContext::TraceFailure(
                v37,
                "CMFContentDecryptorContext::GetService",
                227,
                ContentProtectionDevice);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v13 = 46;
            goto LABEL_18;
          }
        }
      }
    }
    else
    {
      ContentProtectionDevice = (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 2))(
                                  *((_QWORD *)this + 2),
                                  a3,
                                  a4);
      if ( ContentProtectionDevice < 0 )
      {
        v29 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v29 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v29 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v29->m_fEnabled )
        {
          v30 = CallStackTracing::GetThreadRelativeContext(v29);
          if ( v30->m_result != ContentProtectionDevice )
            CallStackContext::TraceFailure(v30, "CMFContentDecryptorContext::GetService", 223, ContentProtectionDevice);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v13 = 45;
          goto LABEL_18;
        }
      }
    }
  }
  else
  {
LABEL_11:
    ContentProtectionDevice = (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 1))(
                                *((_QWORD *)this + 1),
                                a3,
                                a4);
    if ( ContentProtectionDevice < 0 )
    {
      v12 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v12 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v12->m_fEnabled )
      {
        v38 = CallStackTracing::GetThreadRelativeContext(v12);
        if ( v38->m_result != ContentProtectionDevice )
          CallStackContext::TraceFailure(v38, "CMFContentDecryptorContext::GetService", 219, ContentProtectionDevice);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v13 = 44;
LABEL_18:
        v14 = (char *)this - 24;
LABEL_23:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          &WPP_140556a5762535acbe84c7dbcbc943ae_Traceguids,
          v14,
          ContentProtectionDevice);
      }
    }
  }
LABEL_25:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v40);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  return (unsigned int)ContentProtectionDevice;
}

```

## disassembly

```asm
0x1800391a0  push    rbx
0x1800391a2  push    rbp
0x1800391a3  push    rsi
0x1800391a4  push    rdi
0x1800391a5  push    r12
0x1800391a7  push    r13
0x1800391a9  push    r14
0x1800391ab  push    r15
0x1800391ad  sub     rsp, 38h
0x1800391b1  mov     r15, r9
0x1800391b4  mov     rdi, r8
0x1800391b7  mov     r14, rdx
0x1800391ba  mov     rsi, rcx
0x1800391bd  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800391c1  call    cs:__imp_EnterCriticalSection
0x1800391c7  mov     r8d, 0CBh; int
0x1800391cd  lea     rdx, aCmfcontentdecr_1; "CMFContentDecryptorContext::GetService"
0x1800391d4  lea     rcx, [rsp+78h+arg_0]; this
0x1800391dc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800391e1  xor     r13d, r13d
0x1800391e4  mov     [r15], r13
0x1800391e7  mov     rax, qword ptr cs:MF_CONTENT_DECRYPTOR_SERVICE.Data1
0x1800391ee  sub     rax, [r14]
0x1800391f1  jnz     short loc_1800391FE
0x1800391f3  mov     rax, qword ptr cs:MF_CONTENT_DECRYPTOR_SERVICE.Data4
0x1800391fa  sub     rax, [r14+8]
0x1800391fe  test    rax, rax
0x180039201  jnz     loc_1800392D2
0x180039207  lea     rbp, [rsi-18h]
0x18003920b  cmp     [rbp+40h], r13
0x18003920f  jnz     loc_1800398F9
0x180039215  mov     rax, qword ptr cs:_GUID_a7f026da_a5f8_4487_a564_15e34357651e.Data1
0x18003921c  sub     rax, [rdi]
0x18003921f  jnz     short loc_18003922C
0x180039221  mov     rax, qword ptr cs:_GUID_a7f026da_a5f8_4487_a564_15e34357651e.Data4
0x180039228  sub     rax, [rdi+8]
0x18003922c  test    rax, rax
0x18003922f  jz      short loc_180039251
0x180039231  mov     rax, qword ptr cs:_GUID_61f21c45_3c0e_4a74_9cea_67100d9ad5e4.Data1
0x180039238  sub     rax, [rdi]
0x18003923b  jnz     short loc_180039248
0x18003923d  mov     rax, qword ptr cs:_GUID_61f21c45_3c0e_4a74_9cea_67100d9ad5e4.Data4
0x180039244  sub     rax, [rdi+8]
0x180039248  test    rax, rax
0x18003924b  jnz     loc_180039369
0x180039251  mov     rcx, [rsi+8]
0x180039255  mov     rax, [rcx]
0x180039258  mov     r8, r15
0x18003925b  mov     rdx, rdi
0x18003925e  mov     rax, [rax]
0x180039261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039266  mov     ebx, eax
0x180039268  test    eax, eax
0x18003926a  jns     loc_18003933F
0x180039270  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039277  test    rcx, rcx
0x18003927a  jnz     short loc_1800392B5
0x18003927c  lea     rcx, stru_1801FC290
0x180039283  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003928a  mov     rax, cs:stru_1801FC290.__vftable
0x180039291  mov     edx, 7F0h
0x180039296  mov     rax, [rax+8]
0x18003929a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003929f  test    eax, eax
0x1800392a1  jnz     loc_180039891
0x1800392a7  lea     rcx, stru_1801F8A30; this
0x1800392ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800392b5  cmp     [rcx+8], r13b
0x1800392b9  jnz     loc_18003989D
0x1800392bf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800392c6  jb      short loc_18003933F
0x1800392c8  mov     edx, 2Ch ; ','
0x1800392cd  mov     r9, rbp
0x1800392d0  jmp     short loc_180039303
0x1800392d2  mov     ebx, 0C00D36BAh
0x1800392d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800392de  test    rcx, rcx
0x1800392e1  jz      loc_180039496
0x1800392e7  cmp     [rcx+8], r13b
0x1800392eb  jnz     loc_1800398CB
0x1800392f1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800392f8  jb      short loc_18003933F
0x1800392fa  lea     r9, [rsi-18h]
0x1800392fe  mov     edx, 32h ; '2'
0x180039303  mov     rcx, cs:WPP_GLOBAL_Control
0x18003930a  mov     [rsp+78h+var_58], ebx
0x18003930e  lea     r8, WPP_140556a5762535acbe84c7dbcbc943ae_Traceguids
0x180039315  mov     rcx, [rcx+10h]
0x180039319  call    WPP_SF_qD
0x18003931e  jmp     short loc_18003933F
0x180039320  mov     rcx, [rsi+10h]
0x180039324  mov     rax, [rcx]
0x180039327  mov     r8, r15
0x18003932a  mov     rdx, rdi
0x18003932d  mov     rax, [rax]
0x180039330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039335  mov     ebx, eax
0x180039337  test    eax, eax
0x180039339  js      loc_18003961F
0x18003933f  lea     rcx, [rsp+78h+arg_0]; this
0x180039347  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003934c  lea     rcx, [rsi+48h]; lpCriticalSection
0x180039350  call    cs:__imp_LeaveCriticalSection
0x180039356  mov     eax, ebx
0x180039358  add     rsp, 38h
0x18003935c  pop     r15
0x18003935e  pop     r14
0x180039360  pop     r13
0x180039362  pop     r12
0x180039364  pop     rdi
0x180039365  pop     rsi
0x180039366  pop     rbp
0x180039367  pop     rbx
0x180039368  retn
0x180039369  mov     rax, qword ptr cs:_GUID_9b32f9ad_bdcc_40a6_a39d_d5c865845720.Data1
0x180039370  sub     rax, [rdi]
0x180039373  jnz     short loc_180039380
0x180039375  mov     rax, qword ptr cs:_GUID_9b32f9ad_bdcc_40a6_a39d_d5c865845720.Data4
0x18003937c  sub     rax, [rdi+8]
0x180039380  test    rax, rax
0x180039383  jz      short loc_180039320
0x180039385  mov     rax, qword ptr cs:_GUID_10ec4d5b_975a_4689_b9e4_d0aac30fe333.Data1
0x18003938c  sub     rax, [rdi]
0x18003938f  jnz     short loc_18003939C
0x180039391  mov     rax, qword ptr cs:_GUID_10ec4d5b_975a_4689_b9e4_d0aac30fe333.Data4
0x180039398  sub     rax, [rdi+8]
0x18003939c  test    rax, rax
0x18003939f  jz      loc_1800399A7
0x1800393a5  mov     rax, qword ptr cs:_GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140.Data1
0x1800393ac  sub     rax, [rdi]
0x1800393af  jnz     short loc_1800393BC
0x1800393b1  mov     rax, qword ptr cs:_GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140.Data4
0x1800393b8  sub     rax, [rdi+8]
0x1800393bc  test    rax, rax
0x1800393bf  jz      loc_1800399A7
0x1800393c5  mov     rax, qword ptr cs:_GUID_e6257174_a060_4c9a_a088_3b1b471cad28.Data1
0x1800393cc  sub     rax, [rdi]
0x1800393cf  jnz     short loc_1800393DC
0x1800393d1  mov     rax, qword ptr cs:_GUID_e6257174_a060_4c9a_a088_3b1b471cad28.Data4
0x1800393d8  sub     rax, [rdi+8]
0x1800393dc  test    rax, rax
0x1800393df  jz      loc_180039955
0x1800393e5  mov     ebx, r13d
0x1800393e8  mov     rax, qword ptr cs:_GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0.Data1
0x1800393ef  sub     rax, [rdi]
0x1800393f2  jnz     short loc_1800393FF
0x1800393f4  mov     rax, qword ptr cs:_GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0.Data4
0x1800393fb  sub     rax, [rdi+8]
0x1800393ff  test    rax, rax
0x180039402  jnz     loc_18003933F
0x180039408  mov     rcx, [rsi+20h]
0x18003940c  test    rcx, rcx
0x18003940f  jz      loc_18003933F
0x180039415  mov     rax, [rcx]
0x180039418  mov     r8, r15
0x18003941b  mov     rdx, rdi
0x18003941e  mov     rax, [rax]
0x180039421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039426  mov     ebx, eax
0x180039428  test    eax, eax
0x18003942a  jns     loc_18003933F
0x180039430  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039437  test    rcx, rcx
0x18003943a  jnz     short loc_180039475
0x18003943c  lea     rcx, stru_1801FC290
0x180039443  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003944a  mov     rax, cs:stru_1801FC290.__vftable
0x180039451  mov     edx, 7F0h
0x180039456  mov     rax, [rax+8]
0x18003945a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003945f  test    eax, eax
0x180039461  jnz     loc_1800397C9
0x180039467  lea     rcx, stru_1801F8A30; this
0x18003946e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039475  cmp     [rcx+8], r13b
0x180039479  jnz     loc_1800397D5
0x18003947f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180039486  jb      loc_18003933F
0x18003948c  mov     edx, 31h ; '1'
0x180039491  jmp     loc_1800392CD
0x180039496  lea     rcx, stru_1801FC290
0x18003949d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800394a4  mov     rax, cs:stru_1801FC290.__vftable
0x1800394ab  mov     edx, 7F0h
0x1800394b0  mov     rax, [rax+8]
0x1800394b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394b9  test    eax, eax
0x1800394bb  jnz     short loc_1800394D0
0x1800394bd  lea     rcx, stru_1801F8A30
0x1800394c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800394cb  jmp     loc_1800392E7
0x1800394d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800394d7  jmp     loc_1800392E7
0x1800394dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800394e3  test    rcx, rcx
0x1800394e6  jnz     short loc_18003951D
0x1800394e8  lea     rcx, stru_1801FC290
0x1800394ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800394f6  mov     rax, cs:stru_1801FC290.__vftable
0x1800394fd  mov     edx, 7F0h
0x180039502  mov     rax, [rax+8]
0x180039506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003950b  test    eax, eax
0x18003950d  jnz     short loc_18003953A
0x18003950f  lea     rcx, stru_1801F8A30; this
0x180039516  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003951d  cmp     [rcx+8], r13b
0x180039521  jnz     short loc_180039543
0x180039523  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003952a  jb      loc_1800395DD
0x180039530  mov     edx, 2Ah ; '*'
0x180039535  jmp     loc_1800395BF
0x18003953a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039541  jmp     short loc_18003951D
0x180039543  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180039548  cmp     [rax+7CCh], ebx
0x18003954e  jz      short loc_180039523
0x180039550  mov     r9d, ebx; int
0x180039553  mov     r8d, 0D4h; int
0x180039559  lea     rdx, aCmfcontentdecr_1; "CMFContentDecryptorContext::GetService"
0x180039560  mov     rcx, rax; this
0x180039563  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039568  jmp     short loc_180039523
0x18003956a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039571  test    rcx, rcx
0x180039574  jnz     short loc_1800395AB
0x180039576  lea     rcx, stru_1801FC290
0x18003957d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039584  mov     rax, cs:stru_1801FC290.__vftable
0x18003958b  mov     edx, 7F0h
0x180039590  mov     rax, [rax+8]
0x180039594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039599  test    eax, eax
0x18003959b  jnz     short loc_1800395EF
0x18003959d  lea     rcx, stru_1801F8A30; this
0x1800395a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800395ab  cmp     [rcx+8], r13b
0x1800395af  jnz     short loc_1800395F8
0x1800395b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800395b8  jb      short loc_1800395DD
0x1800395ba  mov     edx, 2Bh ; '+'
0x1800395bf  mov     [rsp+78h+var_58], ebx
0x1800395c3  mov     r9, rbp
0x1800395c6  lea     r8, WPP_140556a5762535acbe84c7dbcbc943ae_Traceguids
0x1800395cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800395d4  mov     rcx, [rcx+10h]
0x1800395d8  call    WPP_SF_qD
0x1800395dd  lea     rcx, [rsp+78h+arg_0]
0x1800395e5  call    ??1?$CComPtrBase@VCMFSimulatedContentProtectionDevice@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CMFSimulatedContentProtectionDevice>::~CComPtrBase<CMFSimulatedContentProtectionDevice>(void)
0x1800395ea  jmp     loc_18003933F
0x1800395ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800395f6  jmp     short loc_1800395AB
0x1800395f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800395fd  cmp     [rax+7CCh], ebx
0x180039603  jz      short loc_1800395B1
0x180039605  mov     r9d, ebx; int
0x180039608  mov     r8d, 0D5h; int
0x18003960e  lea     rdx, aCmfcontentdecr_1; "CMFContentDecryptorContext::GetService"
0x180039615  mov     rcx, rax; this
0x180039618  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003961d  jmp     short loc_1800395B1
0x18003961f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039626  test    rcx, rcx
0x180039629  jnz     short loc_180039660
0x18003962b  lea     rcx, stru_1801FC290
0x180039632  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039639  mov     rax, cs:stru_1801FC290.__vftable
0x180039640  mov     edx, 7F0h
0x180039645  mov     rax, [rax+8]
0x180039649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003964e  test    eax, eax
0x180039650  jnz     short loc_18003967D
0x180039652  lea     rcx, stru_1801F8A30; this
0x180039659  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039660  cmp     [rcx+8], r13b
0x180039664  jnz     short loc_180039686
0x180039666  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003966d  jb      loc_18003933F
0x180039673  mov     edx, 2Dh ; '-'
0x180039678  jmp     loc_1800392CD
0x18003967d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039684  jmp     short loc_180039660
0x180039686  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003968b  cmp     [rax+7CCh], ebx
0x180039691  jz      short loc_180039666
0x180039693  mov     r9d, ebx; int
0x180039696  mov     r8d, 0DFh; int
0x18003969c  lea     rdx, aCmfcontentdecr_1; "CMFContentDecryptorContext::GetService"
0x1800396a3  mov     rcx, rax; this
0x1800396a6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800396ab  jmp     short loc_180039666
0x1800396ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800396b4  test    rcx, rcx
0x1800396b7  jnz     short loc_1800396EE
0x1800396b9  lea     rcx, stru_1801FC290
0x1800396c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800396c7  mov     rax, cs:stru_1801FC290.__vftable
0x1800396ce  mov     edx, 7F0h
0x1800396d3  mov     rax, [rax+8]
0x1800396d7  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
