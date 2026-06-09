# CMFPropVariant::SortElements(void)

- ea: `0x18001428c`
- end: `0x180014d08`
- name: `?SortElements@CMFPropVariant@@QEAAJXZ`
- size: `2684`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026690`
- `0x180080f80`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x1800130d0`
- `0x1800135b0`
- `0x18001428c`
- `0x180014d10`
- `0x180018b90`
- `0x180029a00`
- `0x180071a44`
- `0x180073b14`
- `0x180109590`
- `0x1801095a8`
- `0x1801723e0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800143d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800143d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800144bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800144bf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800143c1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800143c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800145b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001465d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014697`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014782`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800147c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800147fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014834`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001486e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800145b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001465d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014697`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014782`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800147c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800147fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014834`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001486e`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::SortElements(CMFPropVariant *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  const struct CMFPropVariant *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  int VarTypeSize; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // esi
  char *v11; // r13
  unsigned int v12; // r12d
  CallStackTracing *v13; // rsi
  char *v14; // rbx
  DWORD LastError; // r12d
  char *Value; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  struct CallStackContext *v21; // rax
  void *v22; // rsi
  CallStackTracing *v23; // rax
  CallStackTracing *v24; // rcx
  CallStackTracing *v26; // rax
  wchar_t *v27; // rdi
  CallStackTracing *v28; // rax
  CallStackTracing *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rdx
  wchar_t *v32; // rdi
  CallStackTracing *v33; // rax
  wchar_t *v34; // rdi
  CallStackTracing *v35; // rax
  CallStackTracing *v36; // rax
  CallStackTracing *v37; // rax
  wchar_t *v38; // rdi
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  struct CallStackContext *v41; // rax
  struct CallStackContext *v42; // rax
  struct CallStackContext *v43; // rax
  struct CallStackContext *v44; // rax
  struct CallStackContext *v45; // rax
  struct CallStackContext *v46; // rax
  struct CallStackContext *v47; // rax
  struct CallStackContext *v48; // rax
  struct CallStackContext *v49; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v51; // rdx
  __int64 v52; // rdx
  _BYTE v53[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int Size[3]; // [rsp+34h] [rbp-44h] BYREF
  int v55; // [rsp+40h] [rbp-38h] BYREF
  int v56; // [rsp+44h] [rbp-34h]
  int v57; // [rsp+48h] [rbp-30h]
  void *Block; // [rsp+50h] [rbp-28h]
  unsigned int ElementCount; // [rsp+58h] [rbp-20h]
  void *Src; // [rsp+60h] [rbp-18h]

  Size[0] = 0;
  Block = 0;
  v55 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v53, "CMFPropVariant::SortElements", 2625);
  v2 = *(unsigned __int16 *)this;
  if ( !(_WORD)v2 )
  {
    VarTypeSize = 0;
    goto LABEL_46;
  }
  v3 = (unsigned __int16)v2;
  LOWORD(v3) = v2 & 0x1000;
  if ( (v2 & 0x1000) == 0 )
  {
    v27 = (wchar_t *)CallStackTracing::s_wpInstance;
    VarTypeSize = -1072875796;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v3, v2);
      CallStackTracing::s_wpInstance = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v27 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875796 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::SortElements", 2642, -1072875796);
    }
    if ( !g_wppLevels )
      goto LABEL_46;
    v51 = 172;
LABEL_147:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v51,
      WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
      this,
      VarTypeSize);
    goto LABEL_46;
  }
  LOWORD(v2) = v2 & 0xFFF;
  if ( (_WORD)v2 == 9 || (LOWORD(v2) = v2 - 12, (unsigned __int16)v2 <= 1u) )
  {
    v38 = (wchar_t *)CallStackTracing::s_wpInstance;
    VarTypeSize = -1072875800;
    if ( !CallStackTracing::s_wpInstance )
    {
      v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v3, v2);
      CallStackTracing::s_wpInstance = v39;
      if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
      {
        v38 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v38 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v38 + 8) )
    {
      v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
      if ( *((_DWORD *)v49 + 499) != -1072875800 )
        CallStackContext::TraceFailure(v49, "CMFPropVariant::SortElements", 2650, -1072875800);
    }
    if ( !g_wppLevels )
      goto LABEL_46;
    v51 = 173;
    goto LABEL_147;
  }
  ElementCount = CMFPropVariant::GetElementCount(this);
  VarTypeSize = CMFPropVariantConvert::GetVarTypeSize(v4, Size);
  if ( VarTypeSize < 0 )
  {
    v32 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v6, v5);
      CallStackTracing::s_wpInstance = v33;
      if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
      {
        v32 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v32 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
      if ( *((_DWORD *)v40 + 499) != VarTypeSize )
        CallStackContext::TraceFailure(v40, "CMFPropVariant::SortElements", 2656, VarTypeSize);
    }
    if ( !g_wppLevels )
      goto LABEL_46;
    v51 = 174;
    goto LABEL_147;
  }
  Block = operator new(Size[0]);
  if ( !Block )
  {
    v34 = (wchar_t *)CallStackTracing::s_wpInstance;
    VarTypeSize = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v9, v8);
      CallStackTracing::s_wpInstance = v35;
      if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
      {
        v34 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v34 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v34 + 8) )
    {
      v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
      if ( *((_DWORD *)v41 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v41, "CMFPropVariant::SortElements", 2662, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_46;
    v51 = 175;
    goto LABEL_147;
  }
LABEL_7:
  *(_QWORD *)&Size[1] = 0;
  v10 = 0;
  v56 = 0;
  v11 = 0;
  v57 = 1;
  v12 = 1;
  VarTypeSize = CMFPropVariant::GetElementDataPtr(this, 0, (void **)&Size[1]);
  if ( VarTypeSize < 0 )
  {
    v24 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v24 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v48 = CallStackTracing::GetThreadRelativeContext(v24);
      if ( *((_DWORD *)v48 + 499) != VarTypeSize )
        CallStackContext::TraceFailure(v48, "CMFPropVariant::SortElements", 2681, VarTypeSize);
    }
    if ( !g_wppLevels )
      goto LABEL_46;
    v51 = 176;
    goto LABEL_147;
  }
  Src = *(void **)&Size[1];
  while ( 1 )
  {
    if ( ElementCount <= v12 )
    {
      if ( v10 )
        goto LABEL_7;
      goto LABEL_46;
    }
    Size[1] = 0;
    if ( !CallStackTracing::s_wpInstance )
      CallStackTracing::InitInstance();
    v13 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v14 = (char *)CallStackTracing::s_wpInstance + 208;
      LastError = GetLastError();
      Value = (char *)TlsGetValue(*((_DWORD *)v13 + 3));
      if ( Value )
      {
        v14 = Value;
      }
      else if ( !GetLastError() )
      {
        v29 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v29 = CallStackTracing::s_wpInstance;
        }
        v30 = (**(__int64 (__fastcall ***)(CallStackTracing *))v29)(v29);
        if ( v30 )
          v14 = (char *)v30;
      }
      SetLastError(LastError);
      v17 = *((unsigned int *)v14 + 497);
      v12 = v57;
      if ( (unsigned int)v17 < *((_DWORD *)v14 + 498) )
      {
        v18 = 2 * v17;
        *(_QWORD *)&v14[8 * v18] = "CMFPropVariant::GetElementDataPtr";
        *(_DWORD *)&v14[8 * v18 + 8] = 2903;
      }
      ++*((_DWORD *)v14 + 497);
    }
    v19 = *(unsigned __int16 *)this;
    v20 = (unsigned __int16)v19;
    LOWORD(v20) = v19 & 0x1000;
    if ( (v19 & 0x1000) != 0 )
    {
      if ( (_WORD)v19 && *((_DWORD *)this + 2) > v12 )
      {
        VarTypeSize = CMFPropVariantConvert::GetVarTypeSize(this, &Size[1]);
        if ( VarTypeSize < 0 )
        {
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v20, v19);
            CallStackTracing::s_wpInstance = v36;
            v20 = (unsigned __int64)v36;
            if ( !v36
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            v42 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)v42 + 499) != VarTypeSize )
              CallStackContext::TraceFailure(v42, "CMFPropVariant::GetElementDataPtr", 2951, VarTypeSize);
          }
          if ( g_wppLevels )
          {
            v52 = 189;
LABEL_129:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v52,
              WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
              this,
              VarTypeSize);
          }
        }
        else
        {
          v11 = (char *)(*((_QWORD *)this + 2) + v12 * Size[1]);
        }
      }
      else
      {
        VarTypeSize = -2147024809;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v20, v19);
          CallStackTracing::s_wpInstance = v23;
          v20 = (unsigned __int64)v23;
          if ( !v23 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
        if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
        {
          v43 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
          if ( *((_DWORD *)v43 + 499) != -2147024809 )
            CallStackContext::TraceFailure(v43, "CMFPropVariant::GetElementDataPtr", 2944, -2147024809);
        }
        if ( g_wppLevels )
        {
          v52 = 188;
          goto LABEL_129;
        }
      }
    }
    else if ( v12 )
    {
      VarTypeSize = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v20, v19);
        CallStackTracing::s_wpInstance = v37;
        v20 = (unsigned __int64)v37;
        if ( !v37 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v44 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v44, "CMFPropVariant::GetElementDataPtr", 2911, -2147024809);
      }
      if ( g_wppLevels )
      {
        v52 = 187;
        goto LABEL_129;
      }
    }
    else
    {
      LOWORD(v19) = v19 & 0xFFF;
      if ( (_WORD)v19 == 12 || (v11 = (char *)this + 8, (_WORD)v19 == 72) )
        v11 = (char *)*((_QWORD *)this + 1);
      VarTypeSize = 0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v20 = *((unsigned int *)v21 + 497);
      if ( (_DWORD)v20 )
      {
        v20 = (unsigned int)(v20 - 1);
        *((_DWORD *)v21 + 497) = v20;
        if ( !(_DWORD)v20 )
        {
          *((_DWORD *)v21 + 497) = 0;
          *((_QWORD *)v21 + 252) = 0;
          *((_DWORD *)v21 + 499) = 0;
          *((GUID *)v21 + 125) = GUID_00000000_0000_0000_0000_000000000000;
          *((_DWORD *)v21 + 506) = 0;
          *((_DWORD *)v21 + 496) = GetCurrentThreadId();
        }
      }
    }
    if ( VarTypeSize < 0 )
      break;
    v22 = Src;
    VarTypeSize = CMFPropVariant::CompareByDataPtr(this, *(_WORD *)this & 0xFFF, Src, v11, &v55);
    if ( VarTypeSize < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
        CallStackTracing::InitInstance();
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v45 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v45 + 499) != VarTypeSize )
          CallStackContext::TraceFailure(v45, "CMFPropVariant::SortElements", 2695, VarTypeSize);
      }
      if ( g_wppLevels )
      {
        v31 = 178;
        goto LABEL_68;
      }
      goto LABEL_51;
    }
    if ( v55 <= 0 )
    {
      v10 = v56;
    }
    else
    {
      memcpy_0(Block, v22, Size[0]);
      memcpy_0(v22, v11, Size[0]);
      memcpy_0(v11, Block, Size[0]);
      v10 = 1;
      v56 = 1;
    }
    ++v12;
    Src = v11;
    v57 = v12;
  }
  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v46 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    if ( *((_DWORD *)v46 + 499) != VarTypeSize )
      CallStackContext::TraceFailure(v46, "CMFPropVariant::SortElements", 2689, VarTypeSize);
  }
  if ( g_wppLevels )
  {
    v31 = 177;
LABEL_68:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v31,
      WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
      this,
      VarTypeSize);
  }
LABEL_51:
  if ( !CallStackTracing::s_wpInstance )
  {
    v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v20, v19);
    CallStackTracing::s_wpInstance = v26;
    if ( !v26 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
  }
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v47 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    if ( *((_DWORD *)v47 + 499) != VarTypeSize )
      CallStackContext::TraceFailure(v47, "CMFPropVariant::SortElements", 2717, VarTypeSize);
  }
  if ( g_wppLevels )
  {
    v51 = 179;
    goto LABEL_147;
  }
LABEL_46:
  operator delete(Block);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v53);
  return (unsigned int)VarTypeSize;
}

```

## disassembly

```asm
0x18001428c  push    rbp
0x18001428e  push    rbx
0x18001428f  push    rsi
0x180014290  push    rdi
0x180014291  push    r12
0x180014293  push    r13
0x180014295  push    r14
0x180014297  push    r15
0x180014299  mov     rbp, rsp
0x18001429c  sub     rsp, 78h
0x1800142a0  xor     r12d, r12d
0x1800142a3  lea     rsi, aCmfpropvariant_1; "CMFPropVariant::SortElements"
0x1800142aa  mov     r14, rcx
0x1800142ad  mov     dword ptr [rbp+Size], r12d
0x1800142b1  mov     rdx, rsi; char *
0x1800142b4  mov     [rbp+Block], r12
0x1800142b8  mov     r8d, 0A41h; int
0x1800142be  mov     [rbp+var_38], r12d
0x1800142c2  lea     rcx, [rbp+var_48]; this
0x1800142c6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800142cb  movzx   edx, word ptr [r14]
0x1800142cf  cmp     r12w, dx
0x1800142d3  jz      loc_180014AA2
0x1800142d9  movzx   ecx, dx
0x1800142dc  mov     eax, 1000h
0x1800142e1  and     cx, ax
0x1800142e4  cmp     r12w, cx
0x1800142e8  jz      loc_180014682
0x1800142ee  mov     eax, 0FFFh
0x1800142f3  lea     r15d, [r12+1]
0x1800142f8  and     dx, ax
0x1800142fb  cmp     dx, 9
0x1800142ff  jz      loc_180014859
0x180014305  sub     dx, 0Ch
0x180014309  cmp     dx, r15w
0x18001430d  jbe     loc_180014859
0x180014313  mov     rcx, r14; this
0x180014316  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x18001431b  lea     rdx, [rbp+Size]; unsigned int *
0x18001431f  mov     [rbp+var_20], eax
0x180014322  call    ?GetVarTypeSize@CMFPropVariantConvert@@SAJPEBVCMFPropVariant@@PEAK@Z; CMFPropVariantConvert::GetVarTypeSize(CMFPropVariant const *,ulong *)
0x180014327  mov     ebx, eax
0x180014329  test    eax, eax
0x18001432b  js      loc_180014772
0x180014331  mov     ecx, dword ptr [rbp+Size]; Size
0x180014334  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014339  mov     [rbp+Block], rax
0x18001433d  test    rax, rax
0x180014340  jz      loc_1800147AE
0x180014346  lea     rdi, qword_1801B07E0
0x18001434d  mov     qword ptr [rbp+Size+4], r12
0x180014351  lea     r8, [rbp+Size+4]; void **
0x180014355  mov     esi, r12d
0x180014358  mov     [rbp+var_34], r12d
0x18001435c  mov     r13, r12
0x18001435f  mov     [rbp+var_30], r15d
0x180014363  xor     edx, edx; unsigned int
0x180014365  mov     rcx, r14; this
0x180014368  mov     r12d, r15d
0x18001436b  call    ?GetElementDataPtr@CMFPropVariant@@IEBAJKPEAPEAX@Z; CMFPropVariant::GetElementDataPtr(ulong,void * *)
0x180014370  mov     ebx, eax
0x180014372  test    eax, eax
0x180014374  js      loc_1800145D7
0x18001437a  mov     rax, qword ptr [rbp+Size+4]
0x18001437e  mov     [rbp+Src], rax
0x180014382  cmp     [rbp+var_20], r12d
0x180014386  jbe     loc_18001458E
0x18001438c  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180014394  mov     dword ptr [rbp+Size+4], 0
0x18001439b  jz      loc_180014584
0x1800143a1  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800143a8  cmp     byte ptr [rsi+8], 0
0x1800143ac  jz      short loc_18001440B
0x1800143ae  lea     rbx, [rsi+0D0h]
0x1800143b5  call    cs:__imp_GetLastError
0x1800143bb  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x1800143be  mov     r12d, eax
0x1800143c1  call    cs:__imp_TlsGetValue
0x1800143c7  test    rax, rax
0x1800143ca  jz      loc_1800146DE
0x1800143d0  mov     rbx, rax
0x1800143d3  mov     ecx, r12d; dwErrCode
0x1800143d6  call    cs:__imp_SetLastError
0x1800143dc  mov     eax, [rbx+7C4h]
0x1800143e2  mov     r12d, [rbp+var_30]
0x1800143e6  cmp     eax, [rbx+7C8h]
0x1800143ec  jnb     short loc_180014404
0x1800143ee  add     rax, rax
0x1800143f1  lea     rcx, aCmfpropvariant_0; "CMFPropVariant::GetElementDataPtr"
0x1800143f8  mov     [rbx+rax*8], rcx
0x1800143fc  mov     dword ptr [rbx+rax*8+8], 0B57h
0x180014404  add     [rbx+7C4h], r15d
0x18001440b  movzx   edx, word ptr [r14]
0x18001440f  mov     eax, 1000h
0x180014414  movzx   ecx, dx
0x180014417  and     cx, ax
0x18001441a  xor     eax, eax
0x18001441c  cmp     ax, cx
0x18001441f  jz      loc_180014554
0x180014425  cmp     ax, dx
0x180014428  jz      loc_1800145A0
0x18001442e  cmp     [r14+8], r12d
0x180014432  jbe     loc_1800145A0
0x180014438  lea     rdx, [rbp+Size+4]; unsigned int *
0x18001443c  mov     rcx, r14; struct CMFPropVariant *
0x18001443f  call    ?GetVarTypeSize@CMFPropVariantConvert@@SAJPEBVCMFPropVariant@@PEAK@Z; CMFPropVariantConvert::GetVarTypeSize(CMFPropVariant const *,ulong *)
0x180014444  mov     ebx, eax
0x180014446  test    eax, eax
0x180014448  js      loc_1800147EF
0x18001444e  mov     r13d, dword ptr [rbp+Size+4]
0x180014452  imul    r13d, r12d
0x180014456  add     r13, [r14+10h]
0x18001445a  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014461  cmp     byte ptr [rsi+8], 0
0x180014465  jz      short loc_1800144CB
0x180014467  mov     rcx, rsi; this
0x18001446a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001446f  mov     rsi, rax
0x180014472  mov     ecx, [rax+7C4h]
0x180014478  test    ecx, ecx
0x18001447a  jz      short loc_1800144CB
0x18001447c  sub     ecx, r15d
0x18001447f  mov     [rax+7C4h], ecx
0x180014485  jnz     short loc_1800144CB
0x180014487  mov     dword ptr [rax+7C4h], 0
0x180014491  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180014498  mov     qword ptr [rax+7E0h], 0
0x1800144a3  mov     dword ptr [rax+7CCh], 0
0x1800144ad  movdqu  xmmword ptr [rax+7D0h], xmm0
0x1800144b5  mov     dword ptr [rax+7E8h], 0
0x1800144bf  call    cs:__imp_GetCurrentThreadId
0x1800144c5  mov     [rsi+7C0h], eax
0x1800144cb  test    ebx, ebx
0x1800144cd  js      loc_18001471D
0x1800144d3  movzx   edx, word ptr [r14]
0x1800144d7  mov     eax, 0FFFh
0x1800144dc  mov     rsi, [rbp+Src]
0x1800144e0  and     dx, ax; unsigned __int16
0x1800144e3  lea     rax, [rbp+var_38]
0x1800144e7  mov     r9, r13; void *
0x1800144ea  mov     r8, rsi; void *
0x1800144ed  mov     [rsp+78h+var_58], rax; int *
0x1800144f2  mov     rcx, r14; this
0x1800144f5  call    ?CompareByDataPtr@CMFPropVariant@@IEBAJGPEBX0PEAH@Z; CMFPropVariant::CompareByDataPtr(ushort,void const *,void const *,int *)
0x1800144fa  mov     ebx, eax
0x1800144fc  test    eax, eax
0x1800144fe  js      loc_180014623
0x180014504  cmp     [rbp+var_38], 0
0x180014508  jle     loc_18001459B
0x18001450e  mov     r8d, dword ptr [rbp+Size]; Size
0x180014512  mov     rdx, rsi; Src
0x180014515  mov     rcx, [rbp+Block]; void *
0x180014519  call    memcpy_0
0x18001451e  mov     r8d, dword ptr [rbp+Size]; Size
0x180014522  mov     rdx, r13; Src
0x180014525  mov     rcx, rsi; void *
0x180014528  call    memcpy_0
0x18001452d  mov     r8d, dword ptr [rbp+Size]; Size
0x180014531  mov     rcx, r13; void *
0x180014534  mov     rdx, [rbp+Block]; Src
0x180014538  call    memcpy_0
0x18001453d  mov     esi, r15d
0x180014540  mov     [rbp+var_34], r15d
0x180014544  add     r12d, r15d
0x180014547  mov     [rbp+Src], r13
0x18001454b  mov     [rbp+var_30], r12d
0x18001454f  jmp     loc_180014382
0x180014554  test    r12d, r12d
0x180014557  jnz     loc_180014822
0x18001455d  mov     eax, 0FFFh
0x180014562  and     dx, ax
0x180014565  cmp     dx, 0Ch
0x180014569  jz      loc_180014C07
0x18001456f  lea     r13, [r14+8]
0x180014573  cmp     dx, 48h ; 'H'
0x180014577  jz      loc_180014C07
0x18001457d  xor     ebx, ebx
0x18001457f  jmp     loc_18001445A
0x180014584  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180014589  jmp     loc_1800143A1
0x18001458e  xor     r12d, r12d
0x180014591  test    esi, esi
0x180014593  jnz     loc_18001434D
0x180014599  jmp     short loc_1800145FE
0x18001459b  mov     esi, [rbp+var_34]
0x18001459e  jmp     short loc_180014544
0x1800145a0  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800145a7  mov     ebx, 80070057h
0x1800145ac  jnz     loc_180014B83
0x1800145b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800145b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800145bf  mov     rcx, rax
0x1800145c2  test    rax, rax
0x1800145c5  jnz     loc_180014B6A
0x1800145cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800145d2  jmp     loc_180014B83
0x1800145d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800145de  test    rcx, rcx
0x1800145e1  jz      loc_1800146C3
0x1800145e7  cmp     byte ptr [rcx+8], 0
0x1800145eb  jnz     loc_180014A1A
0x1800145f1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800145f8  jnb     loc_180014C5B
0x1800145fe  mov     rcx, [rbp+Block]; Block
0x180014602  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014607  lea     rcx, [rbp+var_48]; this
0x18001460b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180014610  mov     eax, ebx
0x180014612  add     rsp, 78h
0x180014616  pop     r15
0x180014618  pop     r14
0x18001461a  pop     r13
0x18001461c  pop     r12
0x18001461e  pop     rdi
0x18001461f  pop     rsi
0x180014620  pop     rbx
0x180014621  pop     rbp
0x180014622  retn
0x180014623  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18001462b  jz      loc_1800146D4
0x180014631  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014638  cmp     byte ptr [rsi+8], 0
0x18001463c  jnz     loc_180014987
0x180014642  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180014649  jnb     loc_180014C10
0x18001464f  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180014657  jnz     loc_180014C33
0x18001465d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180014663  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001466a  mov     rcx, rax
0x18001466d  test    rax, rax
0x180014670  jnz     loc_180014C1A
0x180014676  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18001467d  jmp     loc_180014C33
0x180014682  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014689  mov     ebx, 0C00D36ECh
0x18001468e  test    rdi, rdi
0x180014691  jnz     loc_180014CC3
0x180014697  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001469d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800146a4  mov     rcx, rax
0x1800146a7  test    rax, rax
0x1800146aa  jnz     loc_180014CA3
0x1800146b0  lea     rdi, qword_1801B07E0
0x1800146b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800146be  jmp     loc_180014CC3
0x1800146c3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800146c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800146cf  jmp     loc_1800145E7
0x1800146d4  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800146d9  jmp     loc_180014631
0x1800146de  call    cs:__imp_GetLastError
0x1800146e4  test    eax, eax
0x1800146e6  jnz     loc_1800143D3
0x1800146ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800146f3  test    rcx, rcx
0x1800146f6  jz      short loc_18001470F
0x1800146f8  mov     rax, [rcx]
0x1800146fb  mov     rax, [rax]
0x1800146fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014703  test    rax, rax
0x180014706  cmovnz  rbx, rax
0x18001470a  jmp     loc_1800143D3
0x18001470f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180014714  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001471b  jmp     short loc_1800146F8
0x18001471d  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180014725  jnz     short loc_18001472C
0x180014727  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001472c  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014733  cmp     byte ptr [rsi+8], 0
0x180014737  jnz     loc_1800149B8
0x18001473d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180014744  jb      loc_18001464F
0x18001474a  mov     edx, 0B1h
0x18001474f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014756  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18001475d  mov     r9, r14
0x180014760  mov     dword ptr [rsp+78h+var_58], ebx
0x180014764  mov     rcx, [rcx+10h]
0x180014768  call    WPP_SF_qD
0x18001476d  jmp     loc_18001464F
0x180014772  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014779  test    rdi, rdi
0x18001477c  jnz     loc_180014ACA
0x180014782  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180014788  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001478f  mov     rcx, rax
0x180014792  test    rax, rax
0x180014795  jnz     loc_180014AAA
0x18001479b  lea     rdi, qword_1801B07E0
0x1800147a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800147a9  jmp     loc_180014ACA
0x1800147ae  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800147b5  mov     ebx, 8007000Eh
0x1800147ba  test    rdi, rdi
0x1800147bd  jnz     loc_180014B0B
0x1800147c3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800147c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800147d0  mov     rcx, rax
  ... truncated ...
```
