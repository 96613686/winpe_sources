# CMFPropVariant::ConvertToBaseTypeArray(void)

- ea: `0x180036d48`
- end: `0x180037336`
- name: `?ConvertToBaseTypeArray@CMFPropVariant@@QEAAJXZ`
- size: `1518`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800212c8`

## callees

- `0x180001e80`
- `0x1800028ac`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180034a04`
- `0x180036d48`
- `0x18003733c`
- `0x180038598`
- `0x180038840`
- `0x180039448`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800370f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800370f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036dc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036e7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036f1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036fba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037075`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003711d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800371ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037271`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036dc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036e7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036f1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180036fba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037075`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003711d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800371ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037271`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::ConvertToBaseTypeArray(PROPVARIANT *pvar)
{
  __int64 v2; // rdx
  __int64 *v3; // rcx
  int VarTypeSize; // ebx
  CallStackTracing *v5; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rdx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  VARTYPE vt; // ax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  size_t v24; // rbx
  BYTE *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  _BYTE v39[4]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int cb[3]; // [rsp+34h] [rbp-2Ch] BYREF
  PROPVARIANT pvarDest; // [rsp+40h] [rbp-20h] BYREF

  memset(cb, 0, sizeof(cb));
  memset(&pvarDest, 0, sizeof(pvarDest));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v39, "CMFPropVariant::ConvertToBaseTypeArray", 1502);
  if ( (pvar->vt & 0x1000) != 0 )
  {
    v3 = (__int64 *)CallStackTracing::s_wpInstance;
    VarTypeSize = -1072875797;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
      CallStackTracing::s_wpInstance = v5;
      if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
      {
        v3 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v3 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v3 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v3);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875797 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFPropVariant::ConvertToBaseTypeArray",
          1511,
          -1072875797);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = 92;
LABEL_12:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        pvar,
        VarTypeSize);
    }
  }
  else if ( pvar->vt )
  {
    VarTypeSize = CMFPropVariant::Copy(&pvarDest, pvar);
    if ( VarTypeSize >= 0 )
    {
      VarTypeSize = CMFPropVariant::Clear(pvar);
      if ( VarTypeSize >= 0 )
      {
        vt = pvarDest.vt;
        pvar->lVal = 1;
        pvar->vt = vt & 0xFFF | 0x1000;
        VarTypeSize = CMFPropVariantConvert::GetVarTypeSize((const struct CMFPropVariant *)pvar, cb);
        if ( VarTypeSize >= 0 )
        {
          v24 = cb[0];
          v25 = (BYTE *)CoTaskMemAlloc(cb[0]);
          pvar->bstrblobVal.pData = v25;
          if ( v25 )
          {
            memset_0(v25, 0, v24);
            VarTypeSize = CMFPropVariant::GetElementDataPtr((CMFPropVariant *)&pvarDest, 0, (void **)&cb[1]);
            if ( VarTypeSize >= 0 )
            {
              VarTypeSize = CMFPropVariant::SetElementData((CMFPropVariant *)pvar, 0, *(const void **)&cb[1]);
              if ( VarTypeSize >= 0 )
              {
                if ( pvarDest.vt != 72 )
                  memset(&pvarDest, 0, sizeof(pvarDest));
              }
              else
              {
                v35 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
                  CallStackTracing::s_wpInstance = v36;
                  if ( v36
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
                  {
                    v35 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v35 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v35 + 8) )
                {
                  v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
                  if ( *((_DWORD *)v37 + 499) != VarTypeSize )
                    CallStackContext::TraceFailure(v37, "CMFPropVariant::ConvertToBaseTypeArray", 1560, VarTypeSize);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v7 = 99;
                  goto LABEL_12;
                }
              }
            }
            else
            {
              v31 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
                CallStackTracing::s_wpInstance = v32;
                if ( v32
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
                {
                  v31 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v31 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v31 + 8) )
              {
                v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
                if ( *((_DWORD *)v33 + 499) != VarTypeSize )
                  CallStackContext::TraceFailure(v33, "CMFPropVariant::ConvertToBaseTypeArray", 1554, VarTypeSize);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v7 = 98;
                goto LABEL_12;
              }
            }
          }
          else
          {
            v27 = (__int64 *)CallStackTracing::s_wpInstance;
            VarTypeSize = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
              CallStackTracing::s_wpInstance = v28;
              if ( v28
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
              {
                v27 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v27 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v27 + 8) )
            {
              v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
              if ( *((_DWORD *)v29 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v29, "CMFPropVariant::ConvertToBaseTypeArray", 1547, -2147024882);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v7 = 97;
              goto LABEL_12;
            }
          }
        }
        else
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
            CallStackTracing::s_wpInstance = v22;
            if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
            {
              v21 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v21 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v21 + 8) )
          {
            v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
            if ( *((_DWORD *)v23 + 499) != VarTypeSize )
              CallStackContext::TraceFailure(v23, "CMFPropVariant::ConvertToBaseTypeArray", 1541, VarTypeSize);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v7 = 96;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v18 + 499) != VarTypeSize )
            CallStackContext::TraceFailure(v18, "CMFPropVariant::ConvertToBaseTypeArray", 1529, VarTypeSize);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v7 = 95;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)v14 + 499) != VarTypeSize )
          CallStackContext::TraceFailure(v14, "CMFPropVariant::ConvertToBaseTypeArray", 1523, VarTypeSize);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 94;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    VarTypeSize = -1072875799;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v10 + 499) != -1072875799 )
        CallStackContext::TraceFailure(v10, "CMFPropVariant::ConvertToBaseTypeArray", 1516, -1072875799);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = 93;
      goto LABEL_12;
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v39);
  CMFPropVariant::Clear(&pvarDest);
  return (unsigned int)VarTypeSize;
}

```

## disassembly

```asm
0x180036d48  mov     [rsp-18h+arg_8], rbx
0x180036d4d  mov     [rsp-18h+arg_10], rdi
0x180036d52  push    rbp
0x180036d53  push    r14
0x180036d55  push    r15
0x180036d57  mov     rbp, rsp
0x180036d5a  sub     rsp, 60h
0x180036d5e  mov     rax, cs:__security_cookie
0x180036d65  xor     rax, rsp
0x180036d68  mov     [rbp+var_8], rax
0x180036d6c  xor     eax, eax
0x180036d6e  lea     r14, aCmfpropvariant_7; "CMFPropVariant::ConvertToBaseTypeArray"
0x180036d75  mov     rdi, rcx
0x180036d78  mov     qword ptr [rbp+pvarDest+10h], rax
0x180036d7c  xorps   xmm0, xmm0
0x180036d7f  mov     dword ptr [rbp+cb], eax
0x180036d82  mov     rdx, r14; char *
0x180036d85  mov     qword ptr [rbp+cb+4], rax
0x180036d89  mov     r8d, 5DEh; int
0x180036d8f  lea     rcx, [rbp+var_30]; this
0x180036d93  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180036d97  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180036d9c  movzx   ecx, word ptr [rdi]
0x180036d9f  mov     r15d, 1000h
0x180036da5  and     cx, r15w
0x180036da9  xor     eax, eax
0x180036dab  cmp     ax, cx
0x180036dae  jz      loc_180036E62
0x180036db4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036dbb  mov     ebx, 0C00D36EBh
0x180036dc0  test    rcx, rcx
0x180036dc3  jnz     short loc_180036E06
0x180036dc5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036dcb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036dd2  mov     rcx, rax
0x180036dd5  test    rax, rax
0x180036dd8  jz      short loc_180036DF8
0x180036dda  mov     rax, [rax]
0x180036ddd  mov     edx, 7F0h
0x180036de2  mov     rax, [rax+8]
0x180036de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036deb  test    eax, eax
0x180036ded  jz      short loc_180036DF8
0x180036def  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036df6  jmp     short loc_180036E06
0x180036df8  lea     rcx, qword_18006EB20; this
0x180036dff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036e06  cmp     byte ptr [rcx+8], 0
0x180036e0a  jz      short loc_180036E2D
0x180036e0c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180036e11  cmp     [rax+7CCh], ebx
0x180036e17  jz      short loc_180036E2D
0x180036e19  mov     r9d, ebx; int
0x180036e1c  mov     r8d, 5E7h; int
0x180036e22  mov     rdx, r14; char *
0x180036e25  mov     rcx, rax; this
0x180036e28  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180036e2d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180036e32  cmp     al, 1
0x180036e34  jb      loc_180037300
0x180036e3a  mov     edx, 5Ch ; '\'
0x180036e3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e46  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180036e4d  mov     r9, rdi
0x180036e50  mov     [rsp+60h+var_40], ebx
0x180036e54  mov     rcx, [rcx+10h]
0x180036e58  call    WPP_SF_qd
0x180036e5d  jmp     loc_180037300
0x180036e62  cmp     ax, [rdi]
0x180036e65  jnz     loc_180036EFB
0x180036e6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036e72  mov     ebx, 0C00D36E9h
0x180036e77  test    rcx, rcx
0x180036e7a  jnz     short loc_180036EBD
0x180036e7c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036e82  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036e89  mov     rcx, rax
0x180036e8c  test    rax, rax
0x180036e8f  jz      short loc_180036EAF
0x180036e91  mov     rax, [rax]
0x180036e94  mov     edx, 7F0h
0x180036e99  mov     rax, [rax+8]
0x180036e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ea2  test    eax, eax
0x180036ea4  jz      short loc_180036EAF
0x180036ea6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036ead  jmp     short loc_180036EBD
0x180036eaf  lea     rcx, qword_18006EB20; this
0x180036eb6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036ebd  cmp     byte ptr [rcx+8], 0
0x180036ec1  jz      short loc_180036EE4
0x180036ec3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180036ec8  cmp     [rax+7CCh], ebx
0x180036ece  jz      short loc_180036EE4
0x180036ed0  mov     r9d, ebx; int
0x180036ed3  mov     r8d, 5ECh; int
0x180036ed9  mov     rdx, r14; char *
0x180036edc  mov     rcx, rax; this
0x180036edf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180036ee4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180036ee9  cmp     al, 1
0x180036eeb  jb      loc_180037300
0x180036ef1  mov     edx, 5Dh ; ']'
0x180036ef6  jmp     loc_180036E3F
0x180036efb  mov     rdx, rdi; pvarSrc
0x180036efe  lea     rcx, [rbp+pvarDest]; pvarDest
0x180036f02  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180036f07  mov     ebx, eax
0x180036f09  test    eax, eax
0x180036f0b  jns     loc_180036F9C
0x180036f11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036f18  test    rcx, rcx
0x180036f1b  jnz     short loc_180036F5E
0x180036f1d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036f23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036f2a  mov     rcx, rax
0x180036f2d  test    rax, rax
0x180036f30  jz      short loc_180036F50
0x180036f32  mov     rax, [rax]
0x180036f35  mov     edx, 7F0h
0x180036f3a  mov     rax, [rax+8]
0x180036f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f43  test    eax, eax
0x180036f45  jz      short loc_180036F50
0x180036f47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036f4e  jmp     short loc_180036F5E
0x180036f50  lea     rcx, qword_18006EB20; this
0x180036f57  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036f5e  cmp     byte ptr [rcx+8], 0
0x180036f62  jz      short loc_180036F85
0x180036f64  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180036f69  cmp     [rax+7CCh], ebx
0x180036f6f  jz      short loc_180036F85
0x180036f71  mov     r9d, ebx; int
0x180036f74  mov     r8d, 5F3h; int
0x180036f7a  mov     rdx, r14; char *
0x180036f7d  mov     rcx, rax; this
0x180036f80  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180036f85  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180036f8a  cmp     al, 1
0x180036f8c  jb      loc_180037300
0x180036f92  mov     edx, 5Eh ; '^'
0x180036f97  jmp     loc_180036E3F
0x180036f9c  mov     rcx, rdi; pvar
0x180036f9f  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180036fa4  mov     ebx, eax
0x180036fa6  test    eax, eax
0x180036fa8  jns     loc_180037039
0x180036fae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036fb5  test    rcx, rcx
0x180036fb8  jnz     short loc_180036FFB
0x180036fba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036fc0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180036fc7  mov     rcx, rax
0x180036fca  test    rax, rax
0x180036fcd  jz      short loc_180036FED
0x180036fcf  mov     rax, [rax]
0x180036fd2  mov     edx, 7F0h
0x180036fd7  mov     rax, [rax+8]
0x180036fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fe0  test    eax, eax
0x180036fe2  jz      short loc_180036FED
0x180036fe4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036feb  jmp     short loc_180036FFB
0x180036fed  lea     rcx, qword_18006EB20; this
0x180036ff4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180036ffb  cmp     byte ptr [rcx+8], 0
0x180036fff  jz      short loc_180037022
0x180037001  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037006  cmp     [rax+7CCh], ebx
0x18003700c  jz      short loc_180037022
0x18003700e  mov     r9d, ebx; int
0x180037011  mov     r8d, 5F9h; int
0x180037017  mov     rdx, r14; char *
0x18003701a  mov     rcx, rax; this
0x18003701d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037022  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037027  cmp     al, 1
0x180037029  jb      loc_180037300
0x18003702f  mov     edx, 5Fh ; '_'
0x180037034  jmp     loc_180036E3F
0x180037039  movzx   eax, word ptr [rbp+pvarDest]
0x18003703d  lea     rdx, [rbp+cb]; unsigned int *
0x180037041  mov     ecx, 0FFFh
0x180037046  mov     dword ptr [rdi+8], 1
0x18003704d  and     ax, cx
0x180037050  mov     rcx, rdi; struct CMFPropVariant *
0x180037053  or      ax, r15w
0x180037057  mov     [rdi], ax
0x18003705a  call    ?GetVarTypeSize@CMFPropVariantConvert@@SAJPEBVCMFPropVariant@@PEAK@Z; CMFPropVariantConvert::GetVarTypeSize(CMFPropVariant const *,ulong *)
0x18003705f  mov     ebx, eax
0x180037061  test    eax, eax
0x180037063  jns     loc_1800370F4
0x180037069  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037070  test    rcx, rcx
0x180037073  jnz     short loc_1800370B6
0x180037075  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003707b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037082  mov     rcx, rax
0x180037085  test    rax, rax
0x180037088  jz      short loc_1800370A8
0x18003708a  mov     rax, [rax]
0x18003708d  mov     edx, 7F0h
0x180037092  mov     rax, [rax+8]
0x180037096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003709b  test    eax, eax
0x18003709d  jz      short loc_1800370A8
0x18003709f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800370a6  jmp     short loc_1800370B6
0x1800370a8  lea     rcx, qword_18006EB20; this
0x1800370af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800370b6  cmp     byte ptr [rcx+8], 0
0x1800370ba  jz      short loc_1800370DD
0x1800370bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800370c1  cmp     [rax+7CCh], ebx
0x1800370c7  jz      short loc_1800370DD
0x1800370c9  mov     r9d, ebx; int
0x1800370cc  mov     r8d, 605h; int
0x1800370d2  mov     rdx, r14; char *
0x1800370d5  mov     rcx, rax; this
0x1800370d8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800370dd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800370e2  cmp     al, 1
0x1800370e4  jb      loc_180037300
0x1800370ea  mov     edx, 60h ; '`'
0x1800370ef  jmp     loc_180036E3F
0x1800370f4  mov     ebx, dword ptr [rbp+cb]
0x1800370f7  mov     ecx, ebx; cb
0x1800370f9  call    cs:__imp_CoTaskMemAlloc
0x1800370ff  mov     [rdi+10h], rax
0x180037103  test    rax, rax
0x180037106  jnz     loc_18003719C
0x18003710c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037113  mov     ebx, 8007000Eh
0x180037118  test    rcx, rcx
0x18003711b  jnz     short loc_18003715E
0x18003711d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037123  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003712a  mov     rcx, rax
0x18003712d  test    rax, rax
0x180037130  jz      short loc_180037150
0x180037132  mov     rax, [rax]
0x180037135  mov     edx, 7F0h
0x18003713a  mov     rax, [rax+8]
0x18003713e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037143  test    eax, eax
0x180037145  jz      short loc_180037150
0x180037147  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003714e  jmp     short loc_18003715E
0x180037150  lea     rcx, qword_18006EB20; this
0x180037157  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003715e  cmp     byte ptr [rcx+8], 0
0x180037162  jz      short loc_180037185
0x180037164  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037169  cmp     [rax+7CCh], ebx
0x18003716f  jz      short loc_180037185
0x180037171  mov     r9d, ebx; int
0x180037174  mov     r8d, 60Bh; int
0x18003717a  mov     rdx, r14; char *
0x18003717d  mov     rcx, rax; this
0x180037180  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037185  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003718a  cmp     al, 1
0x18003718c  jb      loc_180037300
0x180037192  mov     edx, 61h ; 'a'
0x180037197  jmp     loc_180036E3F
0x18003719c  mov     r8, rbx; Size
0x18003719f  xor     edx, edx; Val
0x1800371a1  mov     rcx, rax; void *
0x1800371a4  call    memset_0
0x1800371a9  lea     r8, [rbp+cb+4]; void **
0x1800371ad  xor     edx, edx; unsigned int
0x1800371af  lea     rcx, [rbp+pvarDest]; this
0x1800371b3  call    ?GetElementDataPtr@CMFPropVariant@@IEBAJKPEAPEAX@Z; CMFPropVariant::GetElementDataPtr(ulong,void * *)
0x1800371b8  mov     ebx, eax
0x1800371ba  test    eax, eax
0x1800371bc  jns     loc_18003724D
0x1800371c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800371c9  test    rcx, rcx
0x1800371cc  jnz     short loc_18003720F
0x1800371ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800371d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800371db  mov     rcx, rax
0x1800371de  test    rax, rax
0x1800371e1  jz      short loc_180037201
0x1800371e3  mov     rax, [rax]
0x1800371e6  mov     edx, 7F0h
0x1800371eb  mov     rax, [rax+8]
0x1800371ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371f4  test    eax, eax
0x1800371f6  jz      short loc_180037201
0x1800371f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800371ff  jmp     short loc_18003720F
0x180037201  lea     rcx, qword_18006EB20; this
0x180037208  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003720f  cmp     byte ptr [rcx+8], 0
0x180037213  jz      short loc_180037236
0x180037215  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003721a  cmp     [rax+7CCh], ebx
0x180037220  jz      short loc_180037236
  ... truncated ...
```
