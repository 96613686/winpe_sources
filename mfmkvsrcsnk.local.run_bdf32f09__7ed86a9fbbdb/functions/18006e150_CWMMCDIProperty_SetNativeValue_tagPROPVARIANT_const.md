# CWMMCDIProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x18006e150`
- end: `0x18006e4ef`
- name: `?SetNativeValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `927`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006c24`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18006e150`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006e238`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006e238`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006e2dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006e2dc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006e168`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006e196`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006e168`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006e196`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e1b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e254`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e300`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e3a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e444`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e1b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e254`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e300`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e3a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006e444`

## pseudocode

```c
__int64 __fastcall CWMMCDIProperty::SetNativeValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // edi
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  unsigned __int16 *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  char v38; // [rsp+70h] [rbp+8h] BYREF

  PropVariantClear(this + 4);
  if ( a2->vt == 65 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CWMMCDIProperty::SetNativeValue", 423);
    v5 = PropVariantClear(this + 5);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy(this + 5, a2);
      if ( v5 >= 0 )
      {
        this[4].vt = 31;
        v18 = (unsigned __int16 *)CoTaskMemAlloc(a2->ulVal);
        this[4].hVal.QuadPart = (LONGLONG)v18;
        if ( v18 )
        {
          v5 = StringCchCopyW(v18, (unsigned __int64)a2->ulVal >> 1, a2->caui.pElems);
          if ( v5 < 0 )
          {
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
              CallStackTracing::s_wpInstance = v29;
              if ( v29
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
              {
                v28 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v28 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v28 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMMCDIProperty::SetNativeValue", 446, v5);
            }
            if ( g_wppLevels )
            {
              v11 = 38;
              goto LABEL_56;
            }
          }
        }
        else
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
          v5 = -2147024882;
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
          if ( *((_BYTE *)v22 + 8) )
          {
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)v24 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v24, "CWMMCDIProperty::SetNativeValue", 438, -2147024882);
          }
          if ( g_wppLevels )
          {
            v11 = 37;
            goto LABEL_56;
          }
        }
      }
      else
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
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != v5 )
            CallStackContext::TraceFailure(v17, "CWMMCDIProperty::SetNativeValue", 425, v5);
        }
        if ( g_wppLevels )
        {
          v11 = 36;
          goto LABEL_56;
        }
      }
    }
    else
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)v10 + 499) != v5 )
          CallStackContext::TraceFailure(v10, "CWMMCDIProperty::SetNativeValue", 423, v5);
      }
      if ( g_wppLevels )
      {
        v11 = 35;
LABEL_56:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CWMMCDIProperty::SetNativeValue", 451);
    v34 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147418113;
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
    if ( *((_BYTE *)v34 + 8) )
    {
      v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
      if ( *((_DWORD *)v36 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v36, "CWMMCDIProperty::SetNativeValue", 451, -2147418113);
    }
    if ( g_wppLevels )
    {
      v11 = 39;
      goto LABEL_56;
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006e150  push    rbp
0x18006e152  push    rsi
0x18006e153  push    rdi
0x18006e154  push    r12
0x18006e156  push    r14
0x18006e158  push    r15
0x18006e15a  sub     rsp, 38h
0x18006e15e  mov     rbp, rcx
0x18006e161  mov     rsi, rdx
0x18006e164  add     rcx, 60h ; '`'; pvar
0x18006e168  call    cs:__imp_PropVariantClear
0x18006e16e  cmp     word ptr [rsi], 41h ; 'A'
0x18006e172  lea     r14, aCwmmcdipropert_0; "CWMMCDIProperty::SetNativeValue"
0x18006e179  mov     rdx, r14; char *
0x18006e17c  lea     rcx, [rsp+68h+arg_0]; this
0x18006e181  jnz     loc_18006E426
0x18006e187  mov     r8d, 1A7h; int
0x18006e18d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006e192  lea     rcx, [rbp+78h]; pvar
0x18006e196  call    cs:__imp_PropVariantClear
0x18006e19c  mov     edi, eax
0x18006e19e  test    eax, eax
0x18006e1a0  jns     loc_18006E231
0x18006e1a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e1ad  test    rcx, rcx
0x18006e1b0  jnz     short loc_18006E1F3
0x18006e1b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e1b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e1bf  mov     rcx, rax
0x18006e1c2  test    rax, rax
0x18006e1c5  jz      short loc_18006E1E5
0x18006e1c7  mov     rax, [rax]
0x18006e1ca  mov     edx, 7F0h
0x18006e1cf  mov     rax, [rax+8]
0x18006e1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e1d8  test    eax, eax
0x18006e1da  jz      short loc_18006E1E5
0x18006e1dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e1e3  jmp     short loc_18006E1F3
0x18006e1e5  lea     rcx, qword_1800D6F70; this
0x18006e1ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e1f3  cmp     byte ptr [rcx+8], 0
0x18006e1f7  jz      short loc_18006E21A
0x18006e1f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e1fe  cmp     [rax+7CCh], edi
0x18006e204  jz      short loc_18006E21A
0x18006e206  mov     r9d, edi; int
0x18006e209  mov     r8d, 1A7h; int
0x18006e20f  mov     rdx, r14; char *
0x18006e212  mov     rcx, rax; this
0x18006e215  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e21a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e221  jb      loc_18006E4D5
0x18006e227  mov     edx, 23h ; '#'
0x18006e22c  jmp     loc_18006E4B7
0x18006e231  mov     rdx, rsi; pvarSrc
0x18006e234  lea     rcx, [rbp+78h]; pvarDest
0x18006e238  call    cs:__imp_PropVariantCopy
0x18006e23e  mov     edi, eax
0x18006e240  test    eax, eax
0x18006e242  jns     loc_18006E2D3
0x18006e248  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e24f  test    rcx, rcx
0x18006e252  jnz     short loc_18006E295
0x18006e254  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e25a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e261  mov     rcx, rax
0x18006e264  test    rax, rax
0x18006e267  jz      short loc_18006E287
0x18006e269  mov     rax, [rax]
0x18006e26c  mov     edx, 7F0h
0x18006e271  mov     rax, [rax+8]
0x18006e275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e27a  test    eax, eax
0x18006e27c  jz      short loc_18006E287
0x18006e27e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e285  jmp     short loc_18006E295
0x18006e287  lea     rcx, qword_1800D6F70; this
0x18006e28e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e295  cmp     byte ptr [rcx+8], 0
0x18006e299  jz      short loc_18006E2BC
0x18006e29b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e2a0  cmp     [rax+7CCh], edi
0x18006e2a6  jz      short loc_18006E2BC
0x18006e2a8  mov     r9d, edi; int
0x18006e2ab  mov     r8d, 1A9h; int
0x18006e2b1  mov     rdx, r14; char *
0x18006e2b4  mov     rcx, rax; this
0x18006e2b7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e2bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e2c3  jb      loc_18006E4D5
0x18006e2c9  mov     edx, 24h ; '$'
0x18006e2ce  jmp     loc_18006E4B7
0x18006e2d3  mov     word ptr [rbp+60h], 1Fh
0x18006e2d9  mov     ecx, [rsi+8]; cb
0x18006e2dc  call    cs:__imp_CoTaskMemAlloc
0x18006e2e2  mov     [rbp+68h], rax
0x18006e2e6  test    rax, rax
0x18006e2e9  jnz     loc_18006E37F
0x18006e2ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e2f6  mov     edi, 8007000Eh
0x18006e2fb  test    rcx, rcx
0x18006e2fe  jnz     short loc_18006E341
0x18006e300  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e306  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e30d  mov     rcx, rax
0x18006e310  test    rax, rax
0x18006e313  jz      short loc_18006E333
0x18006e315  mov     rax, [rax]
0x18006e318  mov     edx, 7F0h
0x18006e31d  mov     rax, [rax+8]
0x18006e321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e326  test    eax, eax
0x18006e328  jz      short loc_18006E333
0x18006e32a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e331  jmp     short loc_18006E341
0x18006e333  lea     rcx, qword_1800D6F70; this
0x18006e33a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e341  cmp     byte ptr [rcx+8], 0
0x18006e345  jz      short loc_18006E368
0x18006e347  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e34c  cmp     [rax+7CCh], edi
0x18006e352  jz      short loc_18006E368
0x18006e354  mov     r9d, edi; int
0x18006e357  mov     r8d, 1B6h; int
0x18006e35d  mov     rdx, r14; char *
0x18006e360  mov     rcx, rax; this
0x18006e363  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e368  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e36f  jb      loc_18006E4D5
0x18006e375  mov     edx, 25h ; '%'
0x18006e37a  jmp     loc_18006E4B7
0x18006e37f  mov     edx, [rsi+8]
0x18006e382  mov     rcx, rax; unsigned __int16 *
0x18006e385  mov     r8, [rsi+10h]; unsigned __int16 *
0x18006e389  shr     rdx, 1; unsigned __int64
0x18006e38c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006e391  mov     edi, eax
0x18006e393  test    eax, eax
0x18006e395  jns     loc_18006E4D5
0x18006e39b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e3a2  test    rcx, rcx
0x18006e3a5  jnz     short loc_18006E3E8
0x18006e3a7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e3ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e3b4  mov     rcx, rax
0x18006e3b7  test    rax, rax
0x18006e3ba  jz      short loc_18006E3DA
0x18006e3bc  mov     rax, [rax]
0x18006e3bf  mov     edx, 7F0h
0x18006e3c4  mov     rax, [rax+8]
0x18006e3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3cd  test    eax, eax
0x18006e3cf  jz      short loc_18006E3DA
0x18006e3d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e3d8  jmp     short loc_18006E3E8
0x18006e3da  lea     rcx, qword_1800D6F70; this
0x18006e3e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e3e8  cmp     byte ptr [rcx+8], 0
0x18006e3ec  jz      short loc_18006E40F
0x18006e3ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e3f3  cmp     [rax+7CCh], edi
0x18006e3f9  jz      short loc_18006E40F
0x18006e3fb  mov     r9d, edi; int
0x18006e3fe  mov     r8d, 1BEh; int
0x18006e404  mov     rdx, r14; char *
0x18006e407  mov     rcx, rax; this
0x18006e40a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e40f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e416  jb      loc_18006E4D5
0x18006e41c  mov     edx, 26h ; '&'
0x18006e421  jmp     loc_18006E4B7
0x18006e426  mov     esi, 1C3h
0x18006e42b  mov     r8d, esi; int
0x18006e42e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006e433  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e43a  mov     edi, 8000FFFFh
0x18006e43f  test    rcx, rcx
0x18006e442  jnz     short loc_18006E485
0x18006e444  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006e44a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e451  mov     rcx, rax
0x18006e454  test    rax, rax
0x18006e457  jz      short loc_18006E477
0x18006e459  mov     rax, [rax]
0x18006e45c  mov     edx, 7F0h
0x18006e461  mov     rax, [rax+8]
0x18006e465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e46a  test    eax, eax
0x18006e46c  jz      short loc_18006E477
0x18006e46e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e475  jmp     short loc_18006E485
0x18006e477  lea     rcx, qword_1800D6F70; this
0x18006e47e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006e485  cmp     byte ptr [rcx+8], 0
0x18006e489  jz      short loc_18006E4A9
0x18006e48b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006e490  cmp     [rax+7CCh], edi
0x18006e496  jz      short loc_18006E4A9
0x18006e498  mov     r9d, edi; int
0x18006e49b  mov     r8d, esi; int
0x18006e49e  mov     rdx, r14; char *
0x18006e4a1  mov     rcx, rax; this
0x18006e4a4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006e4a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006e4b0  jb      short loc_18006E4D5
0x18006e4b2  mov     edx, 27h ; '''
0x18006e4b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e4be  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x18006e4c5  mov     r9, rbp
0x18006e4c8  mov     [rsp+68h+var_48], edi
0x18006e4cc  mov     rcx, [rcx+10h]
0x18006e4d0  call    WPP_SF_qD
0x18006e4d5  lea     rcx, [rsp+68h+arg_0]; this
0x18006e4da  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006e4df  mov     eax, edi
0x18006e4e1  add     rsp, 38h
0x18006e4e5  pop     r15
0x18006e4e7  pop     r14
0x18006e4e9  pop     r12
0x18006e4eb  pop     rdi
0x18006e4ec  pop     rsi
0x18006e4ed  pop     rbp
0x18006e4ee  retn
```
