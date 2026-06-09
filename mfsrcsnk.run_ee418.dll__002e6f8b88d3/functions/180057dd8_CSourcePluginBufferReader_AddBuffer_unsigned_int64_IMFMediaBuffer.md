# CSourcePluginBufferReader::AddBuffer(unsigned __int64,IMFMediaBuffer *)

- ea: `0x180057dd8`
- end: `0x18005840a`
- name: `?AddBuffer@CSourcePluginBufferReader@@QEAAJ_KPEAUIMFMediaBuffer@@@Z`
- size: `1586`
- prototype: `__int64 __fastcall(CSourcePluginBufferReader *__hidden this, unsigned __int64, struct IMFMediaBuffer *)`
- caller_count: `8`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x180058410`
- `0x1800bbde0`
- `0x1800d7eb0`
- `0x1800d8870`
- `0x1800e6180`
- `0x1800fdf40`
- `0x1800ff030`
- `0x180140360`

## callees

- `0x1800086c8`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180015238`
- `0x180018b90`
- `0x180057dd8`
- `0x180071a44`
- `0x180073b14`
- `0x180131eb8`
- `0x180138540`
- `0x180147f70`
- `0x180163b04`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057f48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058007`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800580ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005819b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058253`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800582f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057f48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058007`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800580ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005819b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058253`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800582f7`

## string_xrefs

- `0x180057e28`: `CSourcePluginBufferReader::AddBuffer`
- `0x180057e88`: `CSourcePluginBufferReader::AddBuffer`
- `0x180057f9f`: `CSourcePluginBufferReader::AddBuffer`
- `0x18005805e`: `CSourcePluginBufferReader::AddBuffer`
- `0x180058125`: `CSourcePluginBufferReader::AddBuffer`
- `0x1800581f2`: `CSourcePluginBufferReader::AddBuffer`
- `0x1800582aa`: `CSourcePluginBufferReader::AddBuffer`
- `0x18005834e`: `CSourcePluginBufferReader::AddBuffer`

## pseudocode

```c
__int64 __fastcall CSourcePluginBufferReader::AddBuffer(
        CSourcePluginBufferReader *this,
        unsigned __int64 a2,
        struct IMFMediaBuffer *a3)
{
  char v6; // r12
  char v7; // r14
  unsigned __int64 v8; // rdx
  int v9; // esi
  __int64 v10; // r8
  __int64 v11; // r9
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  wchar_t *v16; // rcx
  int v17; // edi
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v20; // ecx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  unsigned int v24; // eax
  unsigned int v25; // r15d
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  CVPtrList *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  int v46; // [rsp+20h] [rbp-58h]
  char v47; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v48; // [rsp+90h] [rbp+18h] BYREF

  if ( *((_DWORD *)this + 112) )
  {
    v6 = 0;
    v7 = 1;
    if ( a2 >= *((_QWORD *)this + 57) )
      goto LABEL_5;
  }
  else
  {
    v6 = 1;
  }
  v7 = 0;
LABEL_5:
  v48 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v47, "CSourcePluginBufferReader::AddBuffer", 407);
  v9 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, unsigned int *))a3->lpVtbl->GetCurrentLength)(a3, &v48);
  if ( v9 >= 0 )
  {
    if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
      WPP_SF_qId(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        38,
        &WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids,
        this,
        a2,
        v48);
    if ( !v6 )
    {
      if ( v7 )
      {
        v15 = *((_QWORD *)this + 57);
        v8 = v15 + *((unsigned int *)this + 116);
        if ( v8 < v15 )
        {
          v16 = (wchar_t *)CallStackTracing::s_wpInstance;
          v17 = -2147024362;
          v9 = -2147024362;
          if ( !CallStackTracing::s_wpInstance )
          {
            v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10, v11);
            CallStackTracing::s_wpInstance = v18;
            if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
            {
              v16 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v16 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v16 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024362 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CSourcePluginBufferReader::AddBuffer",
                419,
                -2147024362);
          }
          if ( !g_wppLevels )
            goto LABEL_98;
          v14 = 39;
          goto LABEL_29;
        }
        if ( v8 == a2 )
          goto LABEL_45;
      }
      else
      {
        v20 = v48;
        v8 = a2 + v48;
        if ( v8 < a2 )
        {
          v21 = (wchar_t *)CallStackTracing::s_wpInstance;
          v17 = -2147024362;
          v9 = -2147024362;
          if ( !CallStackTracing::s_wpInstance )
          {
            v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10, v11);
            CallStackTracing::s_wpInstance = v22;
            if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
            {
              v21 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v21 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v21 + 8) )
          {
            v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
            if ( *((_DWORD *)v23 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v23, "CSourcePluginBufferReader::AddBuffer", 425, -2147024362);
          }
          if ( !g_wppLevels )
            goto LABEL_98;
          v14 = 40;
          goto LABEL_29;
        }
        if ( v8 == *((_QWORD *)this + 57) )
        {
LABEL_46:
          v24 = *((_DWORD *)this + 116);
          v25 = v24 + v20;
          if ( v24 + v20 < v24 )
          {
            v26 = (wchar_t *)CallStackTracing::s_wpInstance;
            v17 = -2147024362;
            v9 = -2147024362;
            if ( !CallStackTracing::s_wpInstance )
            {
              v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10, v11);
              CallStackTracing::s_wpInstance = v27;
              if ( v27
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
              {
                v26 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v26 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v26 + 8) )
            {
              v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
              if ( *((_DWORD *)v28 + 499) != -2147024362 )
                CallStackContext::TraceFailure(v28, "CSourcePluginBufferReader::AddBuffer", 439, -2147024362);
            }
            if ( !g_wppLevels )
              goto LABEL_98;
            v14 = 41;
            goto LABEL_29;
          }
          if ( v25 > 0xBEBC200 )
          {
            if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
              WPP_SF_qDD(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                42,
                &WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids,
                this,
                v20,
                *((_DWORD *)this + 116));
            v29 = (wchar_t *)CallStackTracing::s_wpInstance;
            v9 = -1072875854;
            if ( !CallStackTracing::s_wpInstance )
            {
              v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10, v11);
              CallStackTracing::s_wpInstance = v30;
              if ( v30
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
              {
                v29 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v29 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v29 + 8) )
            {
              v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
              if ( *((_DWORD *)v31 + 499) != -1072875854 )
                CallStackContext::TraceFailure(v31, "CSourcePluginBufferReader::AddBuffer", 443, -1072875854);
            }
            if ( g_wppLevels )
            {
              v14 = 43;
              v46 = -1072875854;
              goto LABEL_13;
            }
            goto LABEL_98;
          }
          v32 = (CSourcePluginBufferReader *)((char *)this + 8);
          if ( v7 )
          {
            if ( !CVPtrList::AddTail(v32, a3) )
            {
              v36 = (wchar_t *)CallStackTracing::s_wpInstance;
              v17 = -2147024882;
              v9 = -2147024882;
              if ( !CallStackTracing::s_wpInstance )
              {
                v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
                CallStackTracing::s_wpInstance = v37;
                if ( v37
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
                {
                  v36 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v36 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v36 + 8) )
              {
                v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
                if ( *((_DWORD *)v38 + 499) != -2147024882 )
                  CallStackContext::TraceFailure(v38, "CSourcePluginBufferReader::AddBuffer", 449, -2147024882);
              }
              if ( !g_wppLevels )
                goto LABEL_98;
              v14 = 44;
              goto LABEL_29;
            }
LABEL_94:
            v9 = 0;
            ((void (__fastcall *)(struct IMFMediaBuffer *))a3->lpVtbl->AddRef)(a3);
            *((_DWORD *)this + 116) = v25;
            if ( v6 )
              *((_QWORD *)this + 59) = a2;
            if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
              WPP_SF_qidi(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                46,
                &WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids,
                this,
                *((_QWORD *)this + 57),
                v25,
                *((_QWORD *)this + 59));
            goto LABEL_98;
          }
          if ( CVPtrList::AddHead(v32, a3) )
          {
            *((_QWORD *)this + 57) = a2;
            goto LABEL_94;
          }
          v42 = (wchar_t *)CallStackTracing::s_wpInstance;
          v17 = -2147024882;
          v9 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
            CallStackTracing::s_wpInstance = v43;
            if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
            {
              v42 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v42 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v42 + 8) )
          {
            v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
            if ( *((_DWORD *)v44 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v44, "CSourcePluginBufferReader::AddBuffer", 453, -2147024882);
          }
          if ( !g_wppLevels )
            goto LABEL_98;
          v14 = 45;
LABEL_29:
          v46 = v17;
          goto LABEL_13;
        }
      }
      CSourcePluginBufferReader::RemoveAllBuffers(this);
      v6 = 1;
      v7 = 0;
    }
LABEL_45:
    v20 = v48;
    goto LABEL_46;
  }
  v12 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v12 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v12 + 8) )
  {
    v13 = CallStackTracing::GetThreadRelativeContext(v12);
    if ( *((_DWORD *)v13 + 499) != v9 )
      CallStackContext::TraceFailure(v13, "CSourcePluginBufferReader::AddBuffer", 407, v9);
  }
  if ( g_wppLevels )
  {
    v14 = 37;
    v46 = v9;
LABEL_13:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids, this, v46);
  }
LABEL_98:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v47);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180057dd8  mov     [rsp+arg_8], rbx
0x180057ddd  push    rbp
0x180057dde  push    rsi
0x180057ddf  push    rdi
0x180057de0  push    r12
0x180057de2  push    r13
0x180057de4  push    r14
0x180057de6  push    r15
0x180057de8  sub     rsp, 40h
0x180057dec  xor     r15d, r15d
0x180057def  mov     r13, r8
0x180057df2  mov     rdi, rdx
0x180057df5  mov     rbx, rcx
0x180057df8  cmp     [rcx+1C0h], r15d
0x180057dff  jnz     short loc_180057E06
0x180057e01  mov     r12b, 1
0x180057e04  jmp     short loc_180057E15
0x180057e06  mov     r12b, r15b
0x180057e09  mov     r14b, 1
0x180057e0c  cmp     rdi, [rcx+1C8h]
0x180057e13  jnb     short loc_180057E18
0x180057e15  mov     r14b, r15b
0x180057e18  mov     ebp, 197h
0x180057e1d  mov     [rsp+78h+arg_10], r15d
0x180057e25  mov     r8d, ebp; int
0x180057e28  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x180057e2f  lea     rcx, [rsp+78h+arg_0]; this
0x180057e37  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180057e3c  mov     rax, [r13+0]
0x180057e40  lea     rdx, [rsp+78h+arg_10]
0x180057e48  mov     rcx, r13
0x180057e4b  mov     rax, [rax+28h]
0x180057e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e54  mov     esi, eax
0x180057e56  test    eax, eax
0x180057e58  jns     short loc_180057ECF
0x180057e5a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057e61  test    rcx, rcx
0x180057e64  jnz     short loc_180057E72
0x180057e66  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180057e6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180057e72  cmp     [rcx+8], r15b
0x180057e76  jz      short loc_180057E9A
0x180057e78  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057e7d  cmp     [rax+7CCh], esi
0x180057e83  jz      short loc_180057E9A
0x180057e85  mov     r9d, esi; int
0x180057e88  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x180057e8f  mov     r8d, ebp; int
0x180057e92  mov     rcx, rax; this
0x180057e95  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180057e9a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180057ea1  jb      loc_1800583E3
0x180057ea7  mov     edx, 25h ; '%'
0x180057eac  mov     dword ptr [rsp+78h+var_58], esi
0x180057eb0  lea     r8, WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids
0x180057eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180057ebe  mov     r9, rbx
0x180057ec1  mov     rcx, [rcx+10h]
0x180057ec5  call    WPP_SF_qD
0x180057eca  jmp     loc_1800583E3
0x180057ecf  cmp     cs:byte_1801B1109, 20h ; ' '
0x180057ed6  lea     rbp, WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids
0x180057edd  jb      short loc_180057F0A
0x180057edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180057ee6  mov     edx, 26h ; '&'
0x180057eeb  mov     eax, [rsp+78h+arg_10]
0x180057ef2  mov     r9, rbx
0x180057ef5  mov     [rsp+78h+var_50], eax
0x180057ef9  mov     r8, rbp
0x180057efc  mov     [rsp+78h+var_58], rdi
0x180057f01  mov     rcx, [rcx+38h]
0x180057f05  call    WPP_SF_qId
0x180057f0a  test    r12b, r12b
0x180057f0d  jnz     loc_1800580A1
0x180057f13  test    r14b, r14b
0x180057f16  jz      loc_180057FE0
0x180057f1c  mov     rcx, [rbx+1C8h]
0x180057f23  mov     edx, [rbx+1D0h]
0x180057f29  add     rdx, rcx
0x180057f2c  cmp     rdx, rcx
0x180057f2f  jnb     loc_180057FD2
0x180057f35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057f3c  mov     edi, 80070216h
0x180057f41  mov     esi, edi
0x180057f43  test    rcx, rcx
0x180057f46  jnz     short loc_180057F89
0x180057f48  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180057f4e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057f55  mov     rcx, rax
0x180057f58  test    rax, rax
0x180057f5b  jz      short loc_180057F7B
0x180057f5d  mov     rax, [rax]
0x180057f60  mov     edx, 7F0h
0x180057f65  mov     rax, [rax+8]
0x180057f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f6e  test    eax, eax
0x180057f70  jz      short loc_180057F7B
0x180057f72  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057f79  jmp     short loc_180057F89
0x180057f7b  lea     rcx, qword_1801B07E0; this
0x180057f82  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180057f89  cmp     [rcx+8], r15b
0x180057f8d  jz      short loc_180057FB4
0x180057f8f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057f94  cmp     [rax+7CCh], edi
0x180057f9a  jz      short loc_180057FB4
0x180057f9c  mov     r9d, edi; int
0x180057f9f  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x180057fa6  mov     r8d, 1A3h; int
0x180057fac  mov     rcx, rax; this
0x180057faf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180057fb4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180057fbb  jb      loc_1800583E3
0x180057fc1  mov     edx, 27h ; '''
0x180057fc6  mov     dword ptr [rsp+78h+var_58], edi
0x180057fca  mov     r8, rbp
0x180057fcd  jmp     loc_180057EB7
0x180057fd2  cmp     rdx, rdi
0x180057fd5  jnz     loc_180058093
0x180057fdb  jmp     loc_1800580A1
0x180057fe0  mov     ecx, [rsp+78h+arg_10]
0x180057fe7  lea     rdx, [rdi+rcx]
0x180057feb  cmp     rdx, rdi
0x180057fee  jnb     loc_18005808A
0x180057ff4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057ffb  mov     edi, 80070216h
0x180058000  mov     esi, edi
0x180058002  test    rcx, rcx
0x180058005  jnz     short loc_180058048
0x180058007  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005800d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058014  mov     rcx, rax
0x180058017  test    rax, rax
0x18005801a  jz      short loc_18005803A
0x18005801c  mov     rax, [rax]
0x18005801f  mov     edx, 7F0h
0x180058024  mov     rax, [rax+8]
0x180058028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005802d  test    eax, eax
0x18005802f  jz      short loc_18005803A
0x180058031  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058038  jmp     short loc_180058048
0x18005803a  lea     rcx, qword_1801B07E0; this
0x180058041  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180058048  cmp     [rcx+8], r15b
0x18005804c  jz      short loc_180058073
0x18005804e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058053  cmp     [rax+7CCh], edi
0x180058059  jz      short loc_180058073
0x18005805b  mov     r9d, edi; int
0x18005805e  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x180058065  mov     r8d, 1A9h; int
0x18005806b  mov     rcx, rax; this
0x18005806e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058073  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005807a  jb      loc_1800583E3
0x180058080  mov     edx, 28h ; '('
0x180058085  jmp     loc_180057FC6
0x18005808a  cmp     rdx, [rbx+1C8h]
0x180058091  jz      short loc_1800580A8
0x180058093  mov     rcx, rbx; this
0x180058096  call    ?RemoveAllBuffers@CSourcePluginBufferReader@@QEAAXXZ; CSourcePluginBufferReader::RemoveAllBuffers(void)
0x18005809b  mov     r12b, 1
0x18005809e  mov     r14b, r15b
0x1800580a1  mov     ecx, [rsp+78h+arg_10]
0x1800580a8  mov     eax, [rbx+1D0h]
0x1800580ae  lea     r15d, [rax+rcx]
0x1800580b2  cmp     r15d, eax
0x1800580b5  jnb     loc_180058151
0x1800580bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800580c2  mov     edi, 80070216h
0x1800580c7  mov     esi, edi
0x1800580c9  test    rcx, rcx
0x1800580cc  jnz     short loc_18005810F
0x1800580ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800580d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800580db  mov     rcx, rax
0x1800580de  test    rax, rax
0x1800580e1  jz      short loc_180058101
0x1800580e3  mov     rax, [rax]
0x1800580e6  mov     edx, 7F0h
0x1800580eb  mov     rax, [rax+8]
0x1800580ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800580f4  test    eax, eax
0x1800580f6  jz      short loc_180058101
0x1800580f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800580ff  jmp     short loc_18005810F
0x180058101  lea     rcx, qword_1801B07E0; this
0x180058108  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005810f  cmp     byte ptr [rcx+8], 0
0x180058113  jz      short loc_18005813A
0x180058115  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005811a  cmp     [rax+7CCh], edi
0x180058120  jz      short loc_18005813A
0x180058122  mov     r9d, edi; int
0x180058125  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x18005812c  mov     r8d, 1B7h; int
0x180058132  mov     rcx, rax; this
0x180058135  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005813a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180058141  jb      loc_1800583E3
0x180058147  mov     edx, 29h ; ')'
0x18005814c  jmp     loc_180057FC6
0x180058151  cmp     r15d, 0BEBC200h
0x180058158  jbe     loc_180058222
0x18005815e  cmp     cs:byte_1801B1109, 20h ; ' '
0x180058165  jb      short loc_18005818A
0x180058167  mov     [rsp+78h+var_50], eax
0x18005816b  mov     edx, 2Ah ; '*'
0x180058170  mov     dword ptr [rsp+78h+var_58], ecx
0x180058174  mov     r9, rbx
0x180058177  mov     rcx, cs:WPP_GLOBAL_Control
0x18005817e  mov     r8, rbp
0x180058181  mov     rcx, [rcx+38h]
0x180058185  call    WPP_SF_qDD
0x18005818a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058191  mov     esi, 0C00D36B2h
0x180058196  test    rcx, rcx
0x180058199  jnz     short loc_1800581DC
0x18005819b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800581a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800581a8  mov     rcx, rax
0x1800581ab  test    rax, rax
0x1800581ae  jz      short loc_1800581CE
0x1800581b0  mov     rax, [rax]
0x1800581b3  mov     edx, 7F0h
0x1800581b8  mov     rax, [rax+8]
0x1800581bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581c1  test    eax, eax
0x1800581c3  jz      short loc_1800581CE
0x1800581c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800581cc  jmp     short loc_1800581DC
0x1800581ce  lea     rcx, qword_1801B07E0; this
0x1800581d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800581dc  cmp     byte ptr [rcx+8], 0
0x1800581e0  jz      short loc_180058207
0x1800581e2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800581e7  cmp     [rax+7CCh], esi
0x1800581ed  jz      short loc_180058207
0x1800581ef  mov     r9d, esi; int
0x1800581f2  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x1800581f9  mov     r8d, 1BBh; int
0x1800581ff  mov     rcx, rax; this
0x180058202  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058207  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005820e  jb      loc_1800583E3
0x180058214  mov     edx, 2Bh ; '+'
0x180058219  mov     dword ptr [rsp+78h+var_58], esi
0x18005821d  jmp     loc_180057FCA
0x180058222  lea     rcx, [rbx+8]; this
0x180058226  mov     rdx, r13; void *
0x180058229  test    r14b, r14b
0x18005822c  jz      loc_1800582D6
0x180058232  call    ?AddTail@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddTail(void *)
0x180058237  test    rax, rax
0x18005823a  jnz     loc_18005837D
0x180058240  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058247  mov     edi, 8007000Eh
0x18005824c  mov     esi, edi
0x18005824e  test    rcx, rcx
0x180058251  jnz     short loc_180058294
0x180058253  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058259  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058260  mov     rcx, rax
0x180058263  test    rax, rax
0x180058266  jz      short loc_180058286
0x180058268  mov     rax, [rax]
0x18005826b  mov     edx, 7F0h
0x180058270  mov     rax, [rax+8]
0x180058274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058279  test    eax, eax
0x18005827b  jz      short loc_180058286
0x18005827d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058284  jmp     short loc_180058294
0x180058286  lea     rcx, qword_1801B07E0; this
0x18005828d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180058294  cmp     byte ptr [rcx+8], 0
0x180058298  jz      short loc_1800582BF
0x18005829a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005829f  cmp     [rax+7CCh], edi
0x1800582a5  jz      short loc_1800582BF
0x1800582a7  mov     r9d, edi; int
0x1800582aa  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x1800582b1  mov     r8d, 1C1h; int
0x1800582b7  mov     rcx, rax; this
0x1800582ba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800582bf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800582c6  jb      loc_1800583E3
0x1800582cc  mov     edx, 2Ch ; ','
0x1800582d1  jmp     loc_180057FC6
0x1800582d6  call    ?AddHead@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddHead(void *)
0x1800582db  test    rax, rax
0x1800582de  jnz     loc_180058376
0x1800582e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800582eb  mov     edi, 8007000Eh
0x1800582f0  mov     esi, edi
0x1800582f2  test    rcx, rcx
0x1800582f5  jnz     short loc_180058338
0x1800582f7  call    cs:__imp_MFGetCallStackTracingWeakReference
  ... truncated ...
```
