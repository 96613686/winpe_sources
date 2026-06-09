# CSourcePluginBufferReader::AddBuffer(unsigned __int64,IMFMediaBuffer *)

- ea: `0x18005b030`
- end: `0x18005b687`
- name: `?AddBuffer@CSourcePluginBufferReader@@QEAAJ_KPEAUIMFMediaBuffer@@@Z`
- size: `1623`
- prototype: `__int64 __fastcall(CSourcePluginBufferReader *__hidden this, unsigned __int64, struct IMFMediaBuffer *)`
- caller_count: `8`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x18005b690`
- `0x1800c18f0`
- `0x1800de1b0`
- `0x1800debc0`
- `0x1800ecb30`
- `0x180104f00`
- `0x180106020`
- `0x180148050`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180035bb0`
- `0x18003b238`
- `0x18005b030`
- `0x180077708`
- `0x180079680`
- `0x1801394f8`
- `0x18013fe10`
- `0x1801500fc`
- `0x18016c9f4`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b1a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b265`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b332`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b405`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b4c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b56d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b1a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b265`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b332`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b405`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b4c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005b56d`

## string_xrefs

- `0x18005b080`: `CSourcePluginBufferReader::AddBuffer`
- `0x18005b0e0`: `CSourcePluginBufferReader::AddBuffer`
- `0x18005b1fd`: `CSourcePluginBufferReader::AddBuffer`
- `0x18005b2c2`: `CSourcePluginBufferReader::AddBuffer`
- `0x18005b38f`: `CSourcePluginBufferReader::AddBuffer`
- `0x18005b462`: `CSourcePluginBufferReader::AddBuffer`
- `0x18005b520`: `CSourcePluginBufferReader::AddBuffer`
- `0x18005b5ca`: `CSourcePluginBufferReader::AddBuffer`

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
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  unsigned __int64 v13; // rcx
  wchar_t *v14; // rcx
  int v15; // edi
  CallStackTracing *v16; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v18; // ecx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // r15d
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  CVPtrList *v30; // rcx
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  int v40; // [rsp+20h] [rbp-58h]
  char v41; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v42; // [rsp+90h] [rbp+18h] BYREF

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
  v42 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v41, "CSourcePluginBufferReader::AddBuffer", 407);
  v9 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, unsigned int *))a3->lpVtbl->GetCurrentLength)(a3, &v42);
  if ( v9 >= 0 )
  {
    if ( (unsigned __int8)byte_1801BA109 >= 0x20u )
      WPP_SF_qId(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        38,
        WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids,
        this,
        a2,
        v42);
    if ( !v6 )
    {
      if ( v7 )
      {
        v13 = *((_QWORD *)this + 57);
        v8 = v13 + *((unsigned int *)this + 116);
        if ( v8 < v13 )
        {
          v14 = (wchar_t *)CallStackTracing::s_wpInstance;
          v15 = -2147024362;
          v9 = -2147024362;
          if ( !CallStackTracing::s_wpInstance )
          {
            v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
            CallStackTracing::s_wpInstance = v16;
            if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
            {
              v14 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v14 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v14 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024362 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CSourcePluginBufferReader::AddBuffer",
                419,
                -2147024362);
          }
          if ( !g_wppLevels )
            goto LABEL_98;
          v12 = 39;
          goto LABEL_29;
        }
        if ( v8 == a2 )
          goto LABEL_45;
      }
      else
      {
        v18 = v42;
        v8 = a2 + v42;
        if ( v8 < a2 )
        {
          v19 = (wchar_t *)CallStackTracing::s_wpInstance;
          v15 = -2147024362;
          v9 = -2147024362;
          if ( !CallStackTracing::s_wpInstance )
          {
            v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
            CallStackTracing::s_wpInstance = v20;
            if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
            {
              v19 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v19 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v19 + 8) )
          {
            v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
            if ( *((_DWORD *)v21 + 499) != -2147024362 )
              CallStackContext::TraceFailure(v21, "CSourcePluginBufferReader::AddBuffer", 425, -2147024362);
          }
          if ( !g_wppLevels )
            goto LABEL_98;
          v12 = 40;
          goto LABEL_29;
        }
        if ( v8 == *((_QWORD *)this + 57) )
        {
LABEL_46:
          v22 = *((_DWORD *)this + 116);
          v23 = v22 + v18;
          if ( v22 + v18 < v22 )
          {
            v24 = (wchar_t *)CallStackTracing::s_wpInstance;
            v15 = -2147024362;
            v9 = -2147024362;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
              CallStackTracing::s_wpInstance = v25;
              if ( v25
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
              {
                v24 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v24 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v24 + 8) )
            {
              v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
              if ( *((_DWORD *)v26 + 499) != -2147024362 )
                CallStackContext::TraceFailure(v26, "CSourcePluginBufferReader::AddBuffer", 439, -2147024362);
            }
            if ( !g_wppLevels )
              goto LABEL_98;
            v12 = 41;
            goto LABEL_29;
          }
          if ( v23 > 0xBEBC200 )
          {
            if ( (unsigned __int8)byte_1801BA109 >= 0x20u )
              WPP_SF_qDD(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                42,
                WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids,
                this,
                v18,
                *((_DWORD *)this + 116));
            v27 = (wchar_t *)CallStackTracing::s_wpInstance;
            v9 = -1072875854;
            if ( !CallStackTracing::s_wpInstance )
            {
              v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
              CallStackTracing::s_wpInstance = v28;
              if ( v28
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
              {
                v27 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v27 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v27 + 8) )
            {
              v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
              if ( *((_DWORD *)v29 + 499) != -1072875854 )
                CallStackContext::TraceFailure(v29, "CSourcePluginBufferReader::AddBuffer", 443, -1072875854);
            }
            if ( g_wppLevels )
            {
              v12 = 43;
              v40 = -1072875854;
              goto LABEL_13;
            }
            goto LABEL_98;
          }
          v30 = (CSourcePluginBufferReader *)((char *)this + 8);
          if ( v7 )
          {
            if ( !CVPtrList::AddTail(v30, a3) )
            {
              v32 = (wchar_t *)CallStackTracing::s_wpInstance;
              v15 = -2147024882;
              v9 = -2147024882;
              if ( !CallStackTracing::s_wpInstance )
              {
                v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
                CallStackTracing::s_wpInstance = v33;
                if ( v33
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
                {
                  v32 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v32 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v32 + 8) )
              {
                v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
                if ( *((_DWORD *)v34 + 499) != -2147024882 )
                  CallStackContext::TraceFailure(v34, "CSourcePluginBufferReader::AddBuffer", 449, -2147024882);
              }
              if ( !g_wppLevels )
                goto LABEL_98;
              v12 = 44;
              goto LABEL_29;
            }
LABEL_94:
            v9 = 0;
            ((void (__fastcall *)(struct IMFMediaBuffer *))a3->lpVtbl->AddRef)(a3);
            *((_DWORD *)this + 116) = v23;
            if ( v6 )
              *((_QWORD *)this + 59) = a2;
            if ( (unsigned __int8)byte_1801BA109 >= 0x20u )
              WPP_SF_qidi(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                46,
                WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids,
                this,
                *((_QWORD *)this + 57),
                v23,
                *((_QWORD *)this + 59));
            goto LABEL_98;
          }
          if ( CVPtrList::AddHead(v30, a3) )
          {
            *((_QWORD *)this + 57) = a2;
            goto LABEL_94;
          }
          v36 = (wchar_t *)CallStackTracing::s_wpInstance;
          v15 = -2147024882;
          v9 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
            CallStackTracing::s_wpInstance = v37;
            if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
            {
              v36 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v36 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v36 + 8) )
          {
            v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
            if ( *((_DWORD *)v38 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v38, "CSourcePluginBufferReader::AddBuffer", 453, -2147024882);
          }
          if ( !g_wppLevels )
            goto LABEL_98;
          v12 = 45;
LABEL_29:
          v40 = v15;
          goto LABEL_13;
        }
      }
      CSourcePluginBufferReader::RemoveAllBuffers(this);
      v6 = 1;
      v7 = 0;
    }
LABEL_45:
    v18 = v42;
    goto LABEL_46;
  }
  v10 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v10 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v10 + 8) )
  {
    v11 = CallStackTracing::GetThreadRelativeContext(v10);
    if ( *((_DWORD *)v11 + 499) != v9 )
      CallStackContext::TraceFailure(v11, "CSourcePluginBufferReader::AddBuffer", 407, v9);
  }
  if ( g_wppLevels )
  {
    v12 = 37;
    v40 = v9;
LABEL_13:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids, this, v40);
  }
LABEL_98:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v41);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005b030  mov     [rsp+arg_8], rbx
0x18005b035  push    rbp
0x18005b036  push    rsi
0x18005b037  push    rdi
0x18005b038  push    r12
0x18005b03a  push    r13
0x18005b03c  push    r14
0x18005b03e  push    r15
0x18005b040  sub     rsp, 40h
0x18005b044  xor     r15d, r15d
0x18005b047  mov     r13, r8
0x18005b04a  mov     rdi, rdx
0x18005b04d  mov     rbx, rcx
0x18005b050  cmp     [rcx+1C0h], r15d
0x18005b057  jnz     short loc_18005B05E
0x18005b059  mov     r12b, 1
0x18005b05c  jmp     short loc_18005B06D
0x18005b05e  mov     r12b, r15b
0x18005b061  mov     r14b, 1
0x18005b064  cmp     rdi, [rcx+1C8h]
0x18005b06b  jnb     short loc_18005B070
0x18005b06d  mov     r14b, r15b
0x18005b070  mov     ebp, 197h
0x18005b075  mov     [rsp+78h+arg_10], r15d
0x18005b07d  mov     r8d, ebp; int
0x18005b080  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x18005b087  lea     rcx, [rsp+78h+arg_0]; this
0x18005b08f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005b094  mov     rax, [r13+0]
0x18005b098  lea     rdx, [rsp+78h+arg_10]
0x18005b0a0  mov     rcx, r13
0x18005b0a3  mov     rax, [rax+28h]
0x18005b0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b0ac  mov     esi, eax
0x18005b0ae  test    eax, eax
0x18005b0b0  jns     short loc_18005B127
0x18005b0b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b0b9  test    rcx, rcx
0x18005b0bc  jnz     short loc_18005B0CA
0x18005b0be  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005b0c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005b0ca  cmp     [rcx+8], r15b
0x18005b0ce  jz      short loc_18005B0F2
0x18005b0d0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b0d5  cmp     [rax+7CCh], esi
0x18005b0db  jz      short loc_18005B0F2
0x18005b0dd  mov     r9d, esi; int
0x18005b0e0  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x18005b0e7  mov     r8d, ebp; int
0x18005b0ea  mov     rcx, rax; this
0x18005b0ed  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b0f2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b0f9  jb      loc_18005B65F
0x18005b0ff  mov     edx, 25h ; '%'
0x18005b104  mov     dword ptr [rsp+78h+var_58], esi
0x18005b108  lea     r8, WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids
0x18005b10f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b116  mov     r9, rbx
0x18005b119  mov     rcx, [rcx+10h]
0x18005b11d  call    WPP_SF_qD
0x18005b122  jmp     loc_18005B65F
0x18005b127  cmp     cs:byte_1801BA109, 20h ; ' '
0x18005b12e  lea     rbp, WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids
0x18005b135  jb      short loc_18005B162
0x18005b137  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b13e  mov     edx, 26h ; '&'
0x18005b143  mov     eax, [rsp+78h+arg_10]
0x18005b14a  mov     r9, rbx
0x18005b14d  mov     [rsp+78h+var_50], eax
0x18005b151  mov     r8, rbp
0x18005b154  mov     [rsp+78h+var_58], rdi
0x18005b159  mov     rcx, [rcx+38h]
0x18005b15d  call    WPP_SF_qId
0x18005b162  test    r12b, r12b
0x18005b165  jnz     loc_18005B305
0x18005b16b  test    r14b, r14b
0x18005b16e  jz      loc_18005B23E
0x18005b174  mov     rcx, [rbx+1C8h]
0x18005b17b  mov     edx, [rbx+1D0h]
0x18005b181  add     rdx, rcx
0x18005b184  cmp     rdx, rcx
0x18005b187  jnb     loc_18005B230
0x18005b18d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b194  mov     edi, 80070216h
0x18005b199  mov     esi, edi
0x18005b19b  test    rcx, rcx
0x18005b19e  jnz     short loc_18005B1E7
0x18005b1a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b1a7  nop     dword ptr [rax+rax+00h]
0x18005b1ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b1b3  mov     rcx, rax
0x18005b1b6  test    rax, rax
0x18005b1b9  jz      short loc_18005B1D9
0x18005b1bb  mov     rax, [rax]
0x18005b1be  mov     edx, 7F0h
0x18005b1c3  mov     rax, [rax+8]
0x18005b1c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b1cc  test    eax, eax
0x18005b1ce  jz      short loc_18005B1D9
0x18005b1d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b1d7  jmp     short loc_18005B1E7
0x18005b1d9  lea     rcx, qword_1801B97E0; this
0x18005b1e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b1e7  cmp     [rcx+8], r15b
0x18005b1eb  jz      short loc_18005B212
0x18005b1ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b1f2  cmp     [rax+7CCh], edi
0x18005b1f8  jz      short loc_18005B212
0x18005b1fa  mov     r9d, edi; int
0x18005b1fd  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x18005b204  mov     r8d, 1A3h; int
0x18005b20a  mov     rcx, rax; this
0x18005b20d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b212  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b219  jb      loc_18005B65F
0x18005b21f  mov     edx, 27h ; '''
0x18005b224  mov     dword ptr [rsp+78h+var_58], edi
0x18005b228  mov     r8, rbp
0x18005b22b  jmp     loc_18005B10F
0x18005b230  cmp     rdx, rdi
0x18005b233  jnz     loc_18005B2F7
0x18005b239  jmp     loc_18005B305
0x18005b23e  mov     ecx, [rsp+78h+arg_10]
0x18005b245  lea     rdx, [rdi+rcx]
0x18005b249  cmp     rdx, rdi
0x18005b24c  jnb     loc_18005B2EE
0x18005b252  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b259  mov     edi, 80070216h
0x18005b25e  mov     esi, edi
0x18005b260  test    rcx, rcx
0x18005b263  jnz     short loc_18005B2AC
0x18005b265  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b26c  nop     dword ptr [rax+rax+00h]
0x18005b271  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b278  mov     rcx, rax
0x18005b27b  test    rax, rax
0x18005b27e  jz      short loc_18005B29E
0x18005b280  mov     rax, [rax]
0x18005b283  mov     edx, 7F0h
0x18005b288  mov     rax, [rax+8]
0x18005b28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b291  test    eax, eax
0x18005b293  jz      short loc_18005B29E
0x18005b295  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b29c  jmp     short loc_18005B2AC
0x18005b29e  lea     rcx, qword_1801B97E0; this
0x18005b2a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b2ac  cmp     [rcx+8], r15b
0x18005b2b0  jz      short loc_18005B2D7
0x18005b2b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b2b7  cmp     [rax+7CCh], edi
0x18005b2bd  jz      short loc_18005B2D7
0x18005b2bf  mov     r9d, edi; int
0x18005b2c2  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x18005b2c9  mov     r8d, 1A9h; int
0x18005b2cf  mov     rcx, rax; this
0x18005b2d2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b2d7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b2de  jb      loc_18005B65F
0x18005b2e4  mov     edx, 28h ; '('
0x18005b2e9  jmp     loc_18005B224
0x18005b2ee  cmp     rdx, [rbx+1C8h]
0x18005b2f5  jz      short loc_18005B30C
0x18005b2f7  mov     rcx, rbx; this
0x18005b2fa  call    ?RemoveAllBuffers@CSourcePluginBufferReader@@QEAAXXZ; CSourcePluginBufferReader::RemoveAllBuffers(void)
0x18005b2ff  mov     r12b, 1
0x18005b302  mov     r14b, r15b
0x18005b305  mov     ecx, [rsp+78h+arg_10]
0x18005b30c  mov     eax, [rbx+1D0h]
0x18005b312  lea     r15d, [rax+rcx]
0x18005b316  cmp     r15d, eax
0x18005b319  jnb     loc_18005B3BB
0x18005b31f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b326  mov     edi, 80070216h
0x18005b32b  mov     esi, edi
0x18005b32d  test    rcx, rcx
0x18005b330  jnz     short loc_18005B379
0x18005b332  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b339  nop     dword ptr [rax+rax+00h]
0x18005b33e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b345  mov     rcx, rax
0x18005b348  test    rax, rax
0x18005b34b  jz      short loc_18005B36B
0x18005b34d  mov     rax, [rax]
0x18005b350  mov     edx, 7F0h
0x18005b355  mov     rax, [rax+8]
0x18005b359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b35e  test    eax, eax
0x18005b360  jz      short loc_18005B36B
0x18005b362  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b369  jmp     short loc_18005B379
0x18005b36b  lea     rcx, qword_1801B97E0; this
0x18005b372  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b379  cmp     byte ptr [rcx+8], 0
0x18005b37d  jz      short loc_18005B3A4
0x18005b37f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b384  cmp     [rax+7CCh], edi
0x18005b38a  jz      short loc_18005B3A4
0x18005b38c  mov     r9d, edi; int
0x18005b38f  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x18005b396  mov     r8d, 1B7h; int
0x18005b39c  mov     rcx, rax; this
0x18005b39f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b3a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b3ab  jb      loc_18005B65F
0x18005b3b1  mov     edx, 29h ; ')'
0x18005b3b6  jmp     loc_18005B224
0x18005b3bb  cmp     r15d, 0BEBC200h
0x18005b3c2  jbe     loc_18005B492
0x18005b3c8  cmp     cs:byte_1801BA109, 20h ; ' '
0x18005b3cf  jb      short loc_18005B3F4
0x18005b3d1  mov     [rsp+78h+var_50], eax
0x18005b3d5  mov     edx, 2Ah ; '*'
0x18005b3da  mov     dword ptr [rsp+78h+var_58], ecx
0x18005b3de  mov     r9, rbx
0x18005b3e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b3e8  mov     r8, rbp
0x18005b3eb  mov     rcx, [rcx+38h]
0x18005b3ef  call    WPP_SF_qDD
0x18005b3f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b3fb  mov     esi, 0C00D36B2h
0x18005b400  test    rcx, rcx
0x18005b403  jnz     short loc_18005B44C
0x18005b405  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b40c  nop     dword ptr [rax+rax+00h]
0x18005b411  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b418  mov     rcx, rax
0x18005b41b  test    rax, rax
0x18005b41e  jz      short loc_18005B43E
0x18005b420  mov     rax, [rax]
0x18005b423  mov     edx, 7F0h
0x18005b428  mov     rax, [rax+8]
0x18005b42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b431  test    eax, eax
0x18005b433  jz      short loc_18005B43E
0x18005b435  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b43c  jmp     short loc_18005B44C
0x18005b43e  lea     rcx, qword_1801B97E0; this
0x18005b445  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b44c  cmp     byte ptr [rcx+8], 0
0x18005b450  jz      short loc_18005B477
0x18005b452  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b457  cmp     [rax+7CCh], esi
0x18005b45d  jz      short loc_18005B477
0x18005b45f  mov     r9d, esi; int
0x18005b462  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x18005b469  mov     r8d, 1BBh; int
0x18005b46f  mov     rcx, rax; this
0x18005b472  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b477  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b47e  jb      loc_18005B65F
0x18005b484  mov     edx, 2Bh ; '+'
0x18005b489  mov     dword ptr [rsp+78h+var_58], esi
0x18005b48d  jmp     loc_18005B228
0x18005b492  lea     rcx, [rbx+8]; this
0x18005b496  mov     rdx, r13; void *
0x18005b499  test    r14b, r14b
0x18005b49c  jz      loc_18005B54C
0x18005b4a2  call    ?AddTail@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddTail(void *)
0x18005b4a7  test    rax, rax
0x18005b4aa  jnz     loc_18005B5F9
0x18005b4b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b4b7  mov     edi, 8007000Eh
0x18005b4bc  mov     esi, edi
0x18005b4be  test    rcx, rcx
0x18005b4c1  jnz     short loc_18005B50A
0x18005b4c3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005b4ca  nop     dword ptr [rax+rax+00h]
0x18005b4cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b4d6  mov     rcx, rax
0x18005b4d9  test    rax, rax
0x18005b4dc  jz      short loc_18005B4FC
0x18005b4de  mov     rax, [rax]
0x18005b4e1  mov     edx, 7F0h
0x18005b4e6  mov     rax, [rax+8]
0x18005b4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b4ef  test    eax, eax
0x18005b4f1  jz      short loc_18005B4FC
0x18005b4f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b4fa  jmp     short loc_18005B50A
0x18005b4fc  lea     rcx, qword_1801B97E0; this
0x18005b503  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005b50a  cmp     byte ptr [rcx+8], 0
0x18005b50e  jz      short loc_18005B535
0x18005b510  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005b515  cmp     [rax+7CCh], edi
0x18005b51b  jz      short loc_18005B535
0x18005b51d  mov     r9d, edi; int
0x18005b520  lea     rdx, aCsourcepluginb_2; "CSourcePluginBufferReader::AddBuffer"
0x18005b527  mov     r8d, 1C1h; int
0x18005b52d  mov     rcx, rax; this
0x18005b530  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005b535  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005b53c  jb      loc_18005B65F
0x18005b542  mov     edx, 2Ch ; ','
0x18005b547  jmp     loc_18005B224
0x18005b54c  call    ?AddHead@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddHead(void *)
0x18005b551  test    rax, rax
0x18005b554  jnz     loc_18005B5F2
0x18005b55a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
