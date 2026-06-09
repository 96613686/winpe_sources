# CWMMCDIProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x1800c3eb0`
- end: `0x1800c4286`
- name: `?SetNativeValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `982`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005670`
- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x1800c3eb0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3f1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3fcc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c4084`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c4131`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c41d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3f1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c3fcc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c4084`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c4131`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c41d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c405a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c405a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800c3faa`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800c3faa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c3ec8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c3efc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c3ec8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800c3efc`

## pseudocode

```c
__int64 __fastcall CWMMCDIProperty::SetNativeValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // edi
  wchar_t *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  char v28; // [rsp+70h] [rbp+8h] BYREF

  PropVariantClear(this + 4);
  if ( a2->vt == 65 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v28, "CWMMCDIProperty::SetNativeValue", 423);
    v5 = PropVariantClear(this + 5);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy(this + 5, a2);
      if ( v5 >= 0 )
      {
        this[4].vt = 31;
        v14 = (unsigned __int16 *)CoTaskMemAlloc(a2->ulVal);
        this[4].hVal.QuadPart = (LONGLONG)v14;
        if ( v14 )
        {
          v5 = StringCchCopyW(v14, (unsigned __int64)a2->ulVal >> 1, a2->caui.pElems);
          if ( v5 < 0 )
          {
            v20 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
              CallStackTracing::s_wpInstance = v21;
              if ( v21
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
              {
                v20 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v20 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v20 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMMCDIProperty::SetNativeValue", 446, v5);
            }
            if ( g_wppLevels )
            {
              v9 = 38;
              goto LABEL_56;
            }
          }
        }
        else
        {
          v16 = (wchar_t *)CallStackTracing::s_wpInstance;
          v5 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
            CallStackTracing::s_wpInstance = v17;
            if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
            {
              v16 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v16 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v16 + 8) )
          {
            v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
            if ( *((_DWORD *)v18 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v18, "CWMMCDIProperty::SetNativeValue", 438, -2147024882);
          }
          if ( g_wppLevels )
          {
            v9 = 37;
            goto LABEL_56;
          }
        }
      }
      else
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
          CallStackTracing::s_wpInstance = v12;
          if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
          {
            v11 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v11 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v11 + 8) )
        {
          v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
          if ( *((_DWORD *)v13 + 499) != v5 )
            CallStackContext::TraceFailure(v13, "CWMMCDIProperty::SetNativeValue", 425, v5);
        }
        if ( g_wppLevels )
        {
          v9 = 36;
          goto LABEL_56;
        }
      }
    }
    else
    {
      v6 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
        CallStackTracing::s_wpInstance = v7;
        if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
        {
          v6 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v6 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v6 + 8) )
      {
        v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
        if ( *((_DWORD *)v8 + 499) != v5 )
          CallStackContext::TraceFailure(v8, "CWMMCDIProperty::SetNativeValue", 423, v5);
      }
      if ( g_wppLevels )
      {
        v9 = 35;
LABEL_56:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v28, "CWMMCDIProperty::SetNativeValue", 451);
    v24 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
      CallStackTracing::s_wpInstance = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
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
      if ( *((_DWORD *)v26 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v26, "CWMMCDIProperty::SetNativeValue", 451, -2147418113);
    }
    if ( g_wppLevels )
    {
      v9 = 39;
      goto LABEL_56;
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800c3eb0  push    rbp
0x1800c3eb2  push    rsi
0x1800c3eb3  push    rdi
0x1800c3eb4  push    r12
0x1800c3eb6  push    r14
0x1800c3eb8  push    r15
0x1800c3eba  sub     rsp, 38h
0x1800c3ebe  mov     rbp, rcx
0x1800c3ec1  mov     rsi, rdx
0x1800c3ec4  add     rcx, 60h ; '`'; pvar
0x1800c3ec8  call    cs:__imp_PropVariantClear
0x1800c3ecf  nop     dword ptr [rax+rax+00h]
0x1800c3ed4  cmp     word ptr [rsi], 41h ; 'A'
0x1800c3ed8  lea     r14, aCwmmcdipropert_0; "CWMMCDIProperty::SetNativeValue"
0x1800c3edf  mov     rdx, r14; char *
0x1800c3ee2  lea     rcx, [rsp+68h+arg_0]; this
0x1800c3ee7  jnz     loc_1800C41B6
0x1800c3eed  mov     r8d, 1A7h; int
0x1800c3ef3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c3ef8  lea     rcx, [rbp+78h]; pvar
0x1800c3efc  call    cs:__imp_PropVariantClear
0x1800c3f03  nop     dword ptr [rax+rax+00h]
0x1800c3f08  mov     edi, eax
0x1800c3f0a  test    eax, eax
0x1800c3f0c  jns     loc_1800C3FA3
0x1800c3f12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3f19  test    rcx, rcx
0x1800c3f1c  jnz     short loc_1800C3F65
0x1800c3f1e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c3f25  nop     dword ptr [rax+rax+00h]
0x1800c3f2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3f31  mov     rcx, rax
0x1800c3f34  test    rax, rax
0x1800c3f37  jz      short loc_1800C3F57
0x1800c3f39  mov     rax, [rax]
0x1800c3f3c  mov     edx, 7F0h
0x1800c3f41  mov     rax, [rax+8]
0x1800c3f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3f4a  test    eax, eax
0x1800c3f4c  jz      short loc_1800C3F57
0x1800c3f4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3f55  jmp     short loc_1800C3F65
0x1800c3f57  lea     rcx, qword_1801B97E0; this
0x1800c3f5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3f65  cmp     byte ptr [rcx+8], 0
0x1800c3f69  jz      short loc_1800C3F8C
0x1800c3f6b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c3f70  cmp     [rax+7CCh], edi
0x1800c3f76  jz      short loc_1800C3F8C
0x1800c3f78  mov     r9d, edi; int
0x1800c3f7b  mov     r8d, 1A7h; int
0x1800c3f81  mov     rdx, r14; char *
0x1800c3f84  mov     rcx, rax; this
0x1800c3f87  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c3f8c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c3f93  jb      loc_1800C426B
0x1800c3f99  mov     edx, 23h ; '#'
0x1800c3f9e  jmp     loc_1800C424D
0x1800c3fa3  mov     rdx, rsi; pvarSrc
0x1800c3fa6  lea     rcx, [rbp+78h]; pvarDest
0x1800c3faa  call    cs:__imp_PropVariantCopy
0x1800c3fb1  nop     dword ptr [rax+rax+00h]
0x1800c3fb6  mov     edi, eax
0x1800c3fb8  test    eax, eax
0x1800c3fba  jns     loc_1800C4051
0x1800c3fc0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3fc7  test    rcx, rcx
0x1800c3fca  jnz     short loc_1800C4013
0x1800c3fcc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c3fd3  nop     dword ptr [rax+rax+00h]
0x1800c3fd8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c3fdf  mov     rcx, rax
0x1800c3fe2  test    rax, rax
0x1800c3fe5  jz      short loc_1800C4005
0x1800c3fe7  mov     rax, [rax]
0x1800c3fea  mov     edx, 7F0h
0x1800c3fef  mov     rax, [rax+8]
0x1800c3ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3ff8  test    eax, eax
0x1800c3ffa  jz      short loc_1800C4005
0x1800c3ffc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c4003  jmp     short loc_1800C4013
0x1800c4005  lea     rcx, qword_1801B97E0; this
0x1800c400c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c4013  cmp     byte ptr [rcx+8], 0
0x1800c4017  jz      short loc_1800C403A
0x1800c4019  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c401e  cmp     [rax+7CCh], edi
0x1800c4024  jz      short loc_1800C403A
0x1800c4026  mov     r9d, edi; int
0x1800c4029  mov     r8d, 1A9h; int
0x1800c402f  mov     rdx, r14; char *
0x1800c4032  mov     rcx, rax; this
0x1800c4035  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c403a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4041  jb      loc_1800C426B
0x1800c4047  mov     edx, 24h ; '$'
0x1800c404c  jmp     loc_1800C424D
0x1800c4051  mov     word ptr [rbp+60h], 1Fh
0x1800c4057  mov     ecx, [rsi+8]; cb
0x1800c405a  call    cs:__imp_CoTaskMemAlloc
0x1800c4061  nop     dword ptr [rax+rax+00h]
0x1800c4066  mov     [rbp+68h], rax
0x1800c406a  test    rax, rax
0x1800c406d  jnz     loc_1800C4109
0x1800c4073  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c407a  mov     edi, 8007000Eh
0x1800c407f  test    rcx, rcx
0x1800c4082  jnz     short loc_1800C40CB
0x1800c4084  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c408b  nop     dword ptr [rax+rax+00h]
0x1800c4090  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c4097  mov     rcx, rax
0x1800c409a  test    rax, rax
0x1800c409d  jz      short loc_1800C40BD
0x1800c409f  mov     rax, [rax]
0x1800c40a2  mov     edx, 7F0h
0x1800c40a7  mov     rax, [rax+8]
0x1800c40ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c40b0  test    eax, eax
0x1800c40b2  jz      short loc_1800C40BD
0x1800c40b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c40bb  jmp     short loc_1800C40CB
0x1800c40bd  lea     rcx, qword_1801B97E0; this
0x1800c40c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c40cb  cmp     byte ptr [rcx+8], 0
0x1800c40cf  jz      short loc_1800C40F2
0x1800c40d1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c40d6  cmp     [rax+7CCh], edi
0x1800c40dc  jz      short loc_1800C40F2
0x1800c40de  mov     r9d, edi; int
0x1800c40e1  mov     r8d, 1B6h; int
0x1800c40e7  mov     rdx, r14; char *
0x1800c40ea  mov     rcx, rax; this
0x1800c40ed  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c40f2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c40f9  jb      loc_1800C426B
0x1800c40ff  mov     edx, 25h ; '%'
0x1800c4104  jmp     loc_1800C424D
0x1800c4109  mov     edx, [rsi+8]
0x1800c410c  mov     rcx, rax; unsigned __int16 *
0x1800c410f  mov     r8, [rsi+10h]; unsigned __int16 *
0x1800c4113  shr     rdx, 1; unsigned __int64
0x1800c4116  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c411b  mov     edi, eax
0x1800c411d  test    eax, eax
0x1800c411f  jns     loc_1800C426B
0x1800c4125  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c412c  test    rcx, rcx
0x1800c412f  jnz     short loc_1800C4178
0x1800c4131  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c4138  nop     dword ptr [rax+rax+00h]
0x1800c413d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c4144  mov     rcx, rax
0x1800c4147  test    rax, rax
0x1800c414a  jz      short loc_1800C416A
0x1800c414c  mov     rax, [rax]
0x1800c414f  mov     edx, 7F0h
0x1800c4154  mov     rax, [rax+8]
0x1800c4158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c415d  test    eax, eax
0x1800c415f  jz      short loc_1800C416A
0x1800c4161  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c4168  jmp     short loc_1800C4178
0x1800c416a  lea     rcx, qword_1801B97E0; this
0x1800c4171  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c4178  cmp     byte ptr [rcx+8], 0
0x1800c417c  jz      short loc_1800C419F
0x1800c417e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c4183  cmp     [rax+7CCh], edi
0x1800c4189  jz      short loc_1800C419F
0x1800c418b  mov     r9d, edi; int
0x1800c418e  mov     r8d, 1BEh; int
0x1800c4194  mov     rdx, r14; char *
0x1800c4197  mov     rcx, rax; this
0x1800c419a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c419f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c41a6  jb      loc_1800C426B
0x1800c41ac  mov     edx, 26h ; '&'
0x1800c41b1  jmp     loc_1800C424D
0x1800c41b6  mov     esi, 1C3h
0x1800c41bb  mov     r8d, esi; int
0x1800c41be  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c41c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c41ca  mov     edi, 8000FFFFh
0x1800c41cf  test    rcx, rcx
0x1800c41d2  jnz     short loc_1800C421B
0x1800c41d4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c41db  nop     dword ptr [rax+rax+00h]
0x1800c41e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c41e7  mov     rcx, rax
0x1800c41ea  test    rax, rax
0x1800c41ed  jz      short loc_1800C420D
0x1800c41ef  mov     rax, [rax]
0x1800c41f2  mov     edx, 7F0h
0x1800c41f7  mov     rax, [rax+8]
0x1800c41fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4200  test    eax, eax
0x1800c4202  jz      short loc_1800C420D
0x1800c4204  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c420b  jmp     short loc_1800C421B
0x1800c420d  lea     rcx, qword_1801B97E0; this
0x1800c4214  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c421b  cmp     byte ptr [rcx+8], 0
0x1800c421f  jz      short loc_1800C423F
0x1800c4221  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c4226  cmp     [rax+7CCh], edi
0x1800c422c  jz      short loc_1800C423F
0x1800c422e  mov     r9d, edi; int
0x1800c4231  mov     r8d, esi; int
0x1800c4234  mov     rdx, r14; char *
0x1800c4237  mov     rcx, rax; this
0x1800c423a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c423f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c4246  jb      short loc_1800C426B
0x1800c4248  mov     edx, 27h ; '''
0x1800c424d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4254  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x1800c425b  mov     r9, rbp
0x1800c425e  mov     [rsp+68h+var_48], edi
0x1800c4262  mov     rcx, [rcx+10h]
0x1800c4266  call    WPP_SF_qD
0x1800c426b  lea     rcx, [rsp+68h+arg_0]; this
0x1800c4270  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800c4275  mov     eax, edi
0x1800c4277  add     rsp, 38h
0x1800c427b  pop     r15
0x1800c427d  pop     r14
0x1800c427f  pop     r12
0x1800c4281  pop     rdi
0x1800c4282  pop     rsi
0x1800c4283  pop     rbp
0x1800c4284  retn
```
