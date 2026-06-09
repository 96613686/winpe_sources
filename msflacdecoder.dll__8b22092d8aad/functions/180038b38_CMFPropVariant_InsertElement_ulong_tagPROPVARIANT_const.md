# CMFPropVariant::InsertElement(ulong,tagPROPVARIANT const *)

- ea: `0x180038b38`
- end: `0x180039267`
- name: `?InsertElement@CMFPropVariant@@QEAAJKPEBUtagPROPVARIANT@@@Z`
- size: `1839`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800342f0`

## callees

- `0x180001e80`
- `0x1800028ac`
- `0x180016b0c`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180034a04`
- `0x18003733c`
- `0x180038298`
- `0x180038598`
- `0x180038840`
- `0x180038b38`
- `0x180039448`
- `0x180039e60`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038f25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039232`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038f25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039232`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038e32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038e32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038bcd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038c89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038da1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038e55`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038f57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003901d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800390c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039197`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038bcd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038c89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038da1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038e55`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038f57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003901d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800390c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039197`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::InsertElement(CMFPropVariant *this, unsigned int a2, struct tagPROPVARIANT *a3)
{
  __int16 v4; // cx
  __int64 v6; // rdx
  __int64 *v7; // rcx
  int VarTypeSize; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  CMFPropVariant *v12; // r8
  __int16 v13; // r10
  unsigned int ElementCount; // r15d
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int16 v19; // cx
  __int16 v20; // dx
  const void **v21; // r14
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  int v26; // r12d
  size_t v27; // rcx
  char *v28; // rax
  __int64 v29; // rdx
  char *v30; // rbx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  PROPVARIANT *v34; // rdx
  __int64 v35; // rdx
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  const void *p_pvarDest; // r8
  __int64 v40; // rdx
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  char v53[8]; // [rsp+30h] [rbp-40h] BYREF
  size_t Size; // [rsp+38h] [rbp-38h] BYREF
  void *Src; // [rsp+40h] [rbp-30h] BYREF
  PROPVARIANT *pvarSrc; // [rsp+48h] [rbp-28h]
  PROPVARIANT pvarDest; // [rsp+50h] [rbp-20h] BYREF

  pvarSrc = a3;
  LODWORD(Size) = 0;
  v4 = *(_WORD *)this;
  Src = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  if ( (v4 & 0x1000) != 0 || !*(_WORD *)this )
  {
    ElementCount = CMFPropVariant::GetElementCount(this);
    if ( this == v12 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v53, "CMFPropVariant::InsertElement", 1991);
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      VarTypeSize = -2147467261;
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::InsertElement", 1991, -2147467261);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 130;
        goto LABEL_106;
      }
    }
    else
    {
      v19 = *(_WORD *)v12;
      if ( !*(_WORD *)v12
        || *(_WORD *)this && (v20 = *(_WORD *)this & 0xFFF, v20 != 12) && (v19 & 0xFFF) != v20
        || ElementCount < a2 )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v53, "CMFPropVariant::InsertElement", 1998);
        v49 = (__int64 *)CallStackTracing::s_wpInstance;
        VarTypeSize = -2147024809;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v49 + 8) )
        {
          v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
          if ( *((_DWORD *)v51 + 499) != -2147024809 )
            CallStackContext::TraceFailure(v51, "CMFPropVariant::InsertElement", 1998, -2147024809);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 131;
          goto LABEL_106;
        }
        goto LABEL_107;
      }
      v21 = (const void **)((char *)this + 16);
      if ( !*(_WORD *)this )
      {
        *((_DWORD *)this + 2) = 0;
        *v21 = 0;
        *(_WORD *)this = v13 | v19 & 0xFFF;
      }
      VarTypeSize = CMFPropVariantConvert::GetVarTypeSize(this, (unsigned int *)&Size);
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v53, "CMFPropVariant::InsertElement", 2015);
      if ( VarTypeSize >= 0 )
      {
        v26 = Size;
        v27 = (unsigned int)Size * (ElementCount + 1);
        Size = v27;
        v28 = (char *)CoTaskMemAlloc(v27);
        v30 = v28;
        if ( v28 )
        {
          memset_0(v28, 0, Size);
          if ( a2 )
            memcpy_0(v30, *v21, v26 * a2);
          if ( ElementCount > a2 )
            memcpy_0(&v30[v26 * (a2 + 1)], (char *)*v21 + v26 * a2, v26 * (ElementCount - a2));
          CoTaskMemFree((LPVOID)*v21);
          v34 = pvarSrc;
          ++*((_DWORD *)this + 2);
          *v21 = v30;
          VarTypeSize = CMFPropVariant::Copy(&pvarDest, v34);
          if ( VarTypeSize >= 0 )
          {
            if ( (*(_WORD *)this & 0xFFF) == 0xC )
            {
              p_pvarDest = &pvarDest;
            }
            else
            {
              VarTypeSize = CMFPropVariant::GetElementDataPtr((CMFPropVariant *)&pvarDest, 0, &Src);
              if ( VarTypeSize < 0 )
              {
                v41 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
                  CallStackTracing::s_wpInstance = v42;
                  if ( v42
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
                  {
                    v41 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v41 = &qword_18006EB20;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                  }
                }
                if ( *((_BYTE *)v41 + 8) )
                {
                  v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
                  if ( *((_DWORD *)v43 + 499) != VarTypeSize )
                    CallStackContext::TraceFailure(v43, "CMFPropVariant::InsertElement", 2086, VarTypeSize);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v11 = 135;
                  goto LABEL_106;
                }
                goto LABEL_107;
              }
              p_pvarDest = Src;
            }
            VarTypeSize = CMFPropVariant::SetElementData(this, a2, p_pvarDest);
            if ( VarTypeSize >= 0 )
            {
              if ( (*(_WORD *)this & 0xFFF) == 0xC || pvarDest.vt != 72 )
                memset(&pvarDest, 0, sizeof(pvarDest));
            }
            else
            {
              v45 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
                CallStackTracing::s_wpInstance = v46;
                if ( v46
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
                {
                  v45 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v45 = &qword_18006EB20;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
                }
              }
              if ( *((_BYTE *)v45 + 8) )
              {
                v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
                if ( *((_DWORD *)v47 + 499) != VarTypeSize )
                  CallStackContext::TraceFailure(v47, "CMFPropVariant::InsertElement", 2093, VarTypeSize);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v11 = 136;
                goto LABEL_106;
              }
            }
            goto LABEL_107;
          }
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
            CallStackTracing::s_wpInstance = v37;
            if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
            {
              v36 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v36 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v36 + 8) )
          {
            v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
            if ( *((_DWORD *)v38 + 499) != VarTypeSize )
              CallStackContext::TraceFailure(v38, "CMFPropVariant::InsertElement", 2068, VarTypeSize);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v11 = 134;
            goto LABEL_106;
          }
        }
        else
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
          VarTypeSize = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
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
            if ( *((_DWORD *)v33 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v33, "CMFPropVariant::InsertElement", 2021, -2147024882);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v11 = 133;
            goto LABEL_106;
          }
        }
      }
      else
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != VarTypeSize )
            CallStackContext::TraceFailure(v25, "CMFPropVariant::InsertElement", 2015, VarTypeSize);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 132;
          goto LABEL_106;
        }
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v53, "CMFPropVariant::InsertElement", 1978);
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    VarTypeSize = -1072875796;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v10 + 499) != -1072875796 )
        CallStackContext::TraceFailure(v10, "CMFPropVariant::InsertElement", 1978, -1072875796);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 129;
LABEL_106:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        this,
        VarTypeSize);
    }
  }
LABEL_107:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v53);
  CoTaskMemFree(0);
  CMFPropVariant::Clear(&pvarDest);
  return (unsigned int)VarTypeSize;
}

```

## disassembly

```asm
0x180038b38  mov     [rsp-38h+arg_18], rbx
0x180038b3d  push    rbp
0x180038b3e  push    rsi
0x180038b3f  push    rdi
0x180038b40  push    r12
0x180038b42  push    r13
0x180038b44  push    r14
0x180038b46  push    r15
0x180038b48  mov     rbp, rsp
0x180038b4b  sub     rsp, 70h
0x180038b4f  mov     rax, cs:__security_cookie
0x180038b56  xor     rax, rsp
0x180038b59  mov     [rbp+var_8], rax
0x180038b5d  xor     r12d, r12d
0x180038b60  mov     [rbp+pvarSrc], r8
0x180038b64  mov     rdi, rcx
0x180038b67  mov     dword ptr [rbp+Size], r12d
0x180038b6b  movzx   ecx, word ptr [rcx]
0x180038b6e  xor     eax, eax
0x180038b70  mov     r10d, 1000h
0x180038b76  mov     [rbp+Src], r12
0x180038b7a  and     cx, r10w
0x180038b7e  mov     qword ptr [rbp+pvarDest+10h], rax
0x180038b82  xorps   xmm0, xmm0
0x180038b85  mov     r13d, edx
0x180038b88  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180038b8c  cmp     r12w, cx
0x180038b90  jnz     loc_180038C48
0x180038b96  cmp     r12w, [rdi]
0x180038b9a  jz      loc_180038C48
0x180038ba0  mov     r14d, 7BAh
0x180038ba6  lea     rsi, aCmfpropvariant_10; "CMFPropVariant::InsertElement"
0x180038bad  mov     r8d, r14d; int
0x180038bb0  lea     rcx, [rbp+var_40]; this
0x180038bb4  mov     rdx, rsi; char *
0x180038bb7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180038bbc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038bc3  mov     ebx, 0C00D36ECh
0x180038bc8  test    rcx, rcx
0x180038bcb  jnz     short loc_180038C0D
0x180038bcd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038bd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038bda  mov     rcx, rax
0x180038bdd  test    rax, rax
0x180038be0  jz      short loc_180038BFF
0x180038be2  mov     rax, [rax]
0x180038be5  lea     edx, [r14+36h]
0x180038be9  mov     rax, [rax+8]
0x180038bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bf2  test    eax, eax
0x180038bf4  jz      short loc_180038BFF
0x180038bf6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038bfd  jmp     short loc_180038C0D
0x180038bff  lea     rcx, qword_18006EB20; this
0x180038c06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038c0d  cmp     [rcx+8], r12b
0x180038c11  jz      short loc_180038C31
0x180038c13  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038c18  cmp     [rax+7CCh], ebx
0x180038c1e  jz      short loc_180038C31
0x180038c20  mov     r9d, ebx; int
0x180038c23  mov     r8d, r14d; int
0x180038c26  mov     rdx, rsi; char *
0x180038c29  mov     rcx, rax; this
0x180038c2c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038c31  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180038c36  cmp     al, 1
0x180038c38  jb      loc_180039227
0x180038c3e  mov     edx, 81h
0x180038c43  jmp     loc_180039209
0x180038c48  mov     rcx, rdi; this
0x180038c4b  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x180038c50  mov     r15d, eax
0x180038c53  cmp     rdi, r8
0x180038c56  jnz     loc_180038D04
0x180038c5c  mov     r14d, 7C7h
0x180038c62  lea     rsi, aCmfpropvariant_10; "CMFPropVariant::InsertElement"
0x180038c69  mov     r8d, r14d; int
0x180038c6c  lea     rcx, [rbp+var_40]; this
0x180038c70  mov     rdx, rsi; char *
0x180038c73  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180038c78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038c7f  mov     ebx, 80004003h
0x180038c84  test    rcx, rcx
0x180038c87  jnz     short loc_180038CC9
0x180038c89  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038c8f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038c96  mov     rcx, rax
0x180038c99  test    rax, rax
0x180038c9c  jz      short loc_180038CBB
0x180038c9e  mov     rax, [rax]
0x180038ca1  lea     edx, [r14+29h]
0x180038ca5  mov     rax, [rax+8]
0x180038ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cae  test    eax, eax
0x180038cb0  jz      short loc_180038CBB
0x180038cb2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038cb9  jmp     short loc_180038CC9
0x180038cbb  lea     rcx, qword_18006EB20; this
0x180038cc2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038cc9  cmp     [rcx+8], r12b
0x180038ccd  jz      short loc_180038CED
0x180038ccf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038cd4  cmp     [rax+7CCh], ebx
0x180038cda  jz      short loc_180038CED
0x180038cdc  mov     r9d, ebx; int
0x180038cdf  mov     r8d, r14d; int
0x180038ce2  mov     rdx, rsi; char *
0x180038ce5  mov     rcx, rax; this
0x180038ce8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038ced  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180038cf2  cmp     al, 1
0x180038cf4  jb      loc_180039227
0x180038cfa  mov     edx, 82h
0x180038cff  jmp     loc_180039209
0x180038d04  movzx   ecx, word ptr [r8]
0x180038d08  cmp     r12w, cx
0x180038d0c  jz      loc_18003916A
0x180038d12  mov     r8d, 0FFFh
0x180038d18  mov     r9d, 0Ch
0x180038d1e  cmp     r12w, [rdi]
0x180038d22  jz      short loc_180038D41
0x180038d24  movzx   edx, word ptr [rdi]
0x180038d27  and     dx, r8w
0x180038d2b  cmp     r9w, dx
0x180038d2f  jz      short loc_180038D41
0x180038d31  movzx   eax, cx
0x180038d34  and     ax, r8w
0x180038d38  cmp     ax, dx
0x180038d3b  jnz     loc_18003916A
0x180038d41  cmp     r15d, r13d
0x180038d44  jb      loc_18003916A
0x180038d4a  lea     r14, [rdi+10h]
0x180038d4e  cmp     r12w, [rdi]
0x180038d52  jnz     short loc_180038D66
0x180038d54  and     cx, r8w
0x180038d58  mov     [rdi+8], r12d
0x180038d5c  or      cx, r10w
0x180038d60  mov     [r14], r12
0x180038d63  mov     [rdi], cx
0x180038d66  lea     rdx, [rbp+Size]; unsigned int *
0x180038d6a  mov     rcx, rdi; struct CMFPropVariant *
0x180038d6d  call    ?GetVarTypeSize@CMFPropVariantConvert@@SAJPEBVCMFPropVariant@@PEAK@Z; CMFPropVariantConvert::GetVarTypeSize(CMFPropVariant const *,ulong *)
0x180038d72  lea     rsi, aCmfpropvariant_10; "CMFPropVariant::InsertElement"
0x180038d79  mov     r8d, 7DFh; int
0x180038d7f  mov     rdx, rsi; char *
0x180038d82  lea     rcx, [rbp+var_40]; this
0x180038d86  mov     ebx, eax
0x180038d88  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180038d8d  test    ebx, ebx
0x180038d8f  jns     loc_180038E20
0x180038d95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038d9c  test    rcx, rcx
0x180038d9f  jnz     short loc_180038DE2
0x180038da1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038da7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038dae  mov     rcx, rax
0x180038db1  test    rax, rax
0x180038db4  jz      short loc_180038DD4
0x180038db6  mov     rax, [rax]
0x180038db9  mov     edx, 7F0h
0x180038dbe  mov     rax, [rax+8]
0x180038dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038dc7  test    eax, eax
0x180038dc9  jz      short loc_180038DD4
0x180038dcb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038dd2  jmp     short loc_180038DE2
0x180038dd4  lea     rcx, qword_18006EB20; this
0x180038ddb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038de2  cmp     [rcx+8], r12b
0x180038de6  jz      short loc_180038E09
0x180038de8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038ded  cmp     [rax+7CCh], ebx
0x180038df3  jz      short loc_180038E09
0x180038df5  mov     r9d, ebx; int
0x180038df8  mov     r8d, 7DFh; int
0x180038dfe  mov     rdx, rsi; char *
0x180038e01  mov     rcx, rax; this
0x180038e04  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038e09  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180038e0e  cmp     al, 1
0x180038e10  jb      loc_180039227
0x180038e16  mov     edx, 84h
0x180038e1b  jmp     loc_180039209
0x180038e20  mov     r12d, dword ptr [rbp+Size]
0x180038e24  lea     eax, [r15+1]
0x180038e28  imul    eax, r12d
0x180038e2c  mov     ecx, eax; cb
0x180038e2e  mov     [rbp+Size], rax
0x180038e32  call    cs:__imp_CoTaskMemAlloc
0x180038e38  mov     rbx, rax
0x180038e3b  test    rax, rax
0x180038e3e  jnz     loc_180038ED4
0x180038e44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038e4b  mov     ebx, 8007000Eh
0x180038e50  test    rcx, rcx
0x180038e53  jnz     short loc_180038E96
0x180038e55  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038e5b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038e62  mov     rcx, rax
0x180038e65  test    rax, rax
0x180038e68  jz      short loc_180038E88
0x180038e6a  mov     rax, [rax]
0x180038e6d  mov     edx, 7F0h
0x180038e72  mov     rax, [rax+8]
0x180038e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e7b  test    eax, eax
0x180038e7d  jz      short loc_180038E88
0x180038e7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038e86  jmp     short loc_180038E96
0x180038e88  lea     rcx, qword_18006EB20; this
0x180038e8f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038e96  cmp     byte ptr [rcx+8], 0
0x180038e9a  jz      short loc_180038EBD
0x180038e9c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038ea1  cmp     [rax+7CCh], ebx
0x180038ea7  jz      short loc_180038EBD
0x180038ea9  mov     r9d, ebx; int
0x180038eac  mov     r8d, 7E5h; int
0x180038eb2  mov     rdx, rsi; char *
0x180038eb5  mov     rcx, rax; this
0x180038eb8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038ebd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180038ec2  cmp     al, 1
0x180038ec4  jb      loc_180039227
0x180038eca  mov     edx, 85h
0x180038ecf  jmp     loc_180039209
0x180038ed4  mov     r8, [rbp+Size]; Size
0x180038ed8  xor     edx, edx; Val
0x180038eda  mov     rcx, rbx; void *
0x180038edd  call    memset_0
0x180038ee2  test    r13d, r13d
0x180038ee5  jz      short loc_180038EF9
0x180038ee7  mov     rdx, [r14]; Src
0x180038eea  mov     r8d, r13d
0x180038eed  imul    r8d, r12d; Size
0x180038ef1  mov     rcx, rbx; void *
0x180038ef4  call    memcpy_0
0x180038ef9  cmp     r15d, r13d
0x180038efc  jbe     short loc_180038F22
0x180038efe  sub     r15d, r13d
0x180038f01  lea     ecx, [r13+1]
0x180038f05  mov     edx, r13d
0x180038f08  imul    r15d, r12d
0x180038f0c  imul    edx, r12d
0x180038f10  imul    ecx, r12d
0x180038f14  mov     r8d, r15d; Size
0x180038f17  add     rdx, [r14]; Src
0x180038f1a  add     rcx, rbx; void *
0x180038f1d  call    memcpy_0
0x180038f22  mov     rcx, [r14]; pv
0x180038f25  call    cs:__imp_CoTaskMemFree
0x180038f2b  mov     rdx, [rbp+pvarSrc]; pvarSrc
0x180038f2f  lea     rcx, [rbp+pvarDest]; pvarDest
0x180038f33  inc     dword ptr [rdi+8]
0x180038f36  xor     r15d, r15d
0x180038f39  mov     [r14], rbx
0x180038f3c  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180038f41  mov     ebx, eax
0x180038f43  test    eax, eax
0x180038f45  jns     loc_180038FD6
0x180038f4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038f52  test    rcx, rcx
0x180038f55  jnz     short loc_180038F98
0x180038f57  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038f5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038f64  mov     rcx, rax
0x180038f67  test    rax, rax
0x180038f6a  jz      short loc_180038F8A
0x180038f6c  mov     rax, [rax]
0x180038f6f  mov     edx, 7F0h
0x180038f74  mov     rax, [rax+8]
0x180038f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f7d  test    eax, eax
0x180038f7f  jz      short loc_180038F8A
0x180038f81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038f88  jmp     short loc_180038F98
0x180038f8a  lea     rcx, qword_18006EB20; this
0x180038f91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038f98  cmp     [rcx+8], r15b
0x180038f9c  jz      short loc_180038FBF
0x180038f9e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038fa3  cmp     [rax+7CCh], ebx
0x180038fa9  jz      short loc_180038FBF
0x180038fab  mov     r9d, ebx; int
0x180038fae  mov     r8d, 814h; int
0x180038fb4  mov     rdx, rsi; char *
0x180038fb7  mov     rcx, rax; this
0x180038fba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038fbf  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180038fc4  cmp     al, 1
0x180038fc6  jb      loc_180039227
0x180038fcc  mov     edx, 86h
0x180038fd1  jmp     loc_180039209
0x180038fd6  movzx   eax, word ptr [rdi]
0x180038fd9  mov     r14d, 0FFFh
0x180038fdf  and     ax, r14w
0x180038fe3  mov     r12d, 0Ch
0x180038fe9  cmp     r12w, ax
0x180038fed  jnz     short loc_180038FF8
  ... truncated ...
```
