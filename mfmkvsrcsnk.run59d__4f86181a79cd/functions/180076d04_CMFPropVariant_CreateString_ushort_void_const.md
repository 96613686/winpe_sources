# CMFPropVariant::CreateString(ushort,void const *)

- ea: `0x180076d04`
- end: `0x180077291`
- name: `?CreateString@CMFPropVariant@@QEAAJGPEBX@Z`
- size: `1421`
- prototype: `int(CMFPropVariant *__hidden this, unsigned __int16, const void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010540`
- `0x1800748fc`

## callees

- `0x180006e70`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180076d04`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800771a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800771a8`
- `OLEAUT32!__imp_SysAllocString` at `0x18007717a`
- `OLEAUT32!__imp_SysAllocString` at `0x18007717a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180076f3f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180076f3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180076e3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180076e3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076d87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076e7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076f97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077023`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800770f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800771d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076d87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076e7f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076f97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077023`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800770f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800771d7`

## string_xrefs

- `0x180076d5b`: `CMFPropVariant::CreateString`
- `0x180076e1f`: `CMFPropVariant::CreateString`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::CreateString(CMFPropVariant *this, __int16 a2, const CHAR *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  signed int v11; // ebx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  _WORD *v18; // rax
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  signed int LastError; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  BSTR v37; // rax
  signed int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  WCHAR *lpWideCharStr; // [rsp+20h] [rbp-10h]
  unsigned int v47; // [rsp+60h] [rbp+30h]
  char v48; // [rsp+68h] [rbp+38h] BYREF

  *(_WORD *)this = a2;
  if ( a2 == 30 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
  }
  else
  {
    if ( a2 != 31 && a2 != 8 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v48, "CMFPropVariant::CreateString", 1854);
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      v11 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v8, v9);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::CreateString", 1854, -2147024809);
      }
      if ( !g_wppLevels )
        goto LABEL_83;
      v14 = 123;
      goto LABEL_82;
    }
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&a3[2 * v6] );
  }
  if ( (unsigned __int16)(a2 - 30) <= 1u )
  {
    v47 = 2 * v6 + 2;
    *((_QWORD *)this + 1) = CoTaskMemAlloc(v47);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v48, "CMFPropVariant::CreateString", 1861);
    v18 = (_WORD *)*((_QWORD *)this + 1);
    if ( !v18 )
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      v11 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v21, "CMFPropVariant::CreateString", 1861, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_83;
      v14 = 124;
LABEL_82:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, this, v11);
LABEL_83:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v48);
      return (unsigned int)v11;
    }
    *v18 = 0;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v48);
    if ( a2 == 30 )
    {
      lpWideCharStr = (WCHAR *)*((_QWORD *)this + 1);
      v11 = 0;
      *(_WORD *)this = 31;
      if ( !MultiByteToWideChar(0, 0, a3, -1, lpWideCharStr, v47 >> 1) )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v48, "CMFPropVariant::CreateString", 1881);
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        v26 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( v11 >= 0 )
        {
          v11 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v26 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v26 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v26 + 8) )
          {
            v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
            if ( *((_DWORD *)v30 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v30, "CMFPropVariant::CreateString", 1882, -2147418113);
          }
          if ( !g_wppLevels )
            goto LABEL_83;
          v14 = 126;
        }
        else
        {
          if ( !CallStackTracing::s_wpInstance )
          {
            v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
            CallStackTracing::s_wpInstance = v27;
            if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
            {
              v26 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v26 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v26 + 8) )
          {
            v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
            if ( *((_DWORD *)v28 + 499) != v11 )
              CallStackContext::TraceFailure(v28, "CMFPropVariant::CreateString", 1881, v11);
          }
          if ( !g_wppLevels )
            goto LABEL_83;
          v14 = 125;
        }
        goto LABEL_82;
      }
      return (unsigned int)v11;
    }
    if ( a2 == 31 )
    {
      v11 = StringCchCopyW(*((unsigned __int16 **)this + 1), (unsigned __int64)v47 >> 1, (const unsigned __int16 *)a3);
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v48, "CMFPropVariant::CreateString", 1888);
      if ( v11 >= 0 )
        goto LABEL_83;
      v34 = (__int64 *)CallStackTracing::s_wpInstance;
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
          v34 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v34 + 8) )
      {
        v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
        if ( *((_DWORD *)v36 + 499) != v11 )
          CallStackContext::TraceFailure(v36, "CMFPropVariant::CreateString", 1888, v11);
      }
      if ( !g_wppLevels )
        goto LABEL_83;
      v14 = 127;
      goto LABEL_82;
    }
  }
  v11 = 0;
  v37 = SysAllocString((const OLECHAR *)a3);
  *((_QWORD *)this + 1) = v37;
  if ( !v37 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v48, "CMFPropVariant::CreateString", 1895);
    v38 = GetLastError();
    v11 = v38;
    if ( v38 > 0 )
      v11 = (unsigned __int16)v38 | 0x80070000;
    if ( v11 >= 0 )
      goto LABEL_83;
    v42 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
      CallStackTracing::s_wpInstance = v43;
      if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
      {
        v42 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v42 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v42 + 8) )
    {
      v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
      if ( *((_DWORD *)v44 + 499) != v11 )
        CallStackContext::TraceFailure(v44, "CMFPropVariant::CreateString", 1895, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_83;
    v14 = 128;
    goto LABEL_82;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180076d04  mov     [rsp-28h+arg_10], rbx
0x180076d09  mov     [rsp-28h+arg_18], rsi
0x180076d0e  push    rbp
0x180076d0f  push    rdi
0x180076d10  push    r12
0x180076d12  push    r13
0x180076d14  push    r15
0x180076d16  mov     rbp, rsp
0x180076d19  sub     rsp, 30h
0x180076d1d  mov     [rcx], dx
0x180076d20  mov     r12, r8
0x180076d23  movzx   ebx, dx
0x180076d26  mov     r15, rcx
0x180076d29  mov     eax, 1Fh
0x180076d2e  cmp     dx, 1Eh
0x180076d32  jnz     short loc_180076D48
0x180076d34  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180076d38  xor     edi, edi
0x180076d3a  inc     rdx
0x180076d3d  cmp     [r8+rdx], dil
0x180076d41  jnz     short loc_180076D3A
0x180076d43  jmp     loc_180076E1C
0x180076d48  cmp     bx, ax
0x180076d4b  jz      loc_180076E0C
0x180076d51  cmp     bx, 8
0x180076d55  jz      loc_180076E0C
0x180076d5b  lea     rsi, aCmfpropvariant_6; "CMFPropVariant::CreateString"
0x180076d62  mov     r8d, 73Eh; int
0x180076d68  mov     rdx, rsi; char *
0x180076d6b  lea     rcx, [rbp+arg_8]; this
0x180076d6f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180076d74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076d7b  xor     edi, edi
0x180076d7d  mov     ebx, 80070057h
0x180076d82  test    rcx, rcx
0x180076d85  jnz     short loc_180076DCE
0x180076d87  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076d8e  nop     dword ptr [rax+rax+00h]
0x180076d93  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076d9a  mov     rcx, rax
0x180076d9d  test    rax, rax
0x180076da0  jz      short loc_180076DC0
0x180076da2  mov     rax, [rax]
0x180076da5  mov     edx, 7F0h
0x180076daa  mov     rax, [rax+8]
0x180076dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076db3  test    eax, eax
0x180076db5  jz      short loc_180076DC0
0x180076db7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076dbe  jmp     short loc_180076DCE
0x180076dc0  lea     rcx, qword_1800DBF70; this
0x180076dc7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076dce  cmp     [rcx+8], dil
0x180076dd2  jz      short loc_180076DF5
0x180076dd4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076dd9  cmp     [rax+7CCh], ebx
0x180076ddf  jz      short loc_180076DF5
0x180076de1  mov     r9d, ebx; int
0x180076de4  mov     r8d, 73Eh; int
0x180076dea  mov     rdx, rsi; char *
0x180076ded  mov     rcx, rax; this
0x180076df0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076df5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076dfc  jb      loc_18007726E
0x180076e02  mov     edx, 7Bh ; '{'
0x180076e07  jmp     loc_180077250
0x180076e0c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180076e10  xor     edi, edi
0x180076e12  inc     rdx
0x180076e15  cmp     [r8+rdx*2], di
0x180076e1a  jnz     short loc_180076E12
0x180076e1c  lea     eax, [rbx-1Eh]
0x180076e1f  lea     rsi, aCmfpropvariant_6; "CMFPropVariant::CreateString"
0x180076e26  cmp     ax, 1
0x180076e2a  ja      loc_180077175
0x180076e30  lea     edx, ds:2[rdx*2]
0x180076e37  mov     ecx, edx; cb
0x180076e39  mov     [rbp+arg_0], edx
0x180076e3c  mov     r13d, edx
0x180076e3f  call    cs:__imp_CoTaskMemAlloc
0x180076e46  nop     dword ptr [rax+rax+00h]
0x180076e4b  mov     r8d, 745h; int
0x180076e51  lea     rcx, [rbp+arg_8]; this
0x180076e55  mov     rdx, rsi; char *
0x180076e58  mov     [r15+8], rax
0x180076e5c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180076e61  mov     rax, [r15+8]
0x180076e65  test    rax, rax
0x180076e68  jnz     loc_180076F04
0x180076e6e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076e75  mov     ebx, 8007000Eh
0x180076e7a  test    rcx, rcx
0x180076e7d  jnz     short loc_180076EC6
0x180076e7f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076e86  nop     dword ptr [rax+rax+00h]
0x180076e8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076e92  mov     rcx, rax
0x180076e95  test    rax, rax
0x180076e98  jz      short loc_180076EB8
0x180076e9a  mov     rax, [rax]
0x180076e9d  mov     edx, 7F0h
0x180076ea2  mov     rax, [rax+8]
0x180076ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076eab  test    eax, eax
0x180076ead  jz      short loc_180076EB8
0x180076eaf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076eb6  jmp     short loc_180076EC6
0x180076eb8  lea     rcx, qword_1800DBF70; this
0x180076ebf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076ec6  cmp     [rcx+8], dil
0x180076eca  jz      short loc_180076EED
0x180076ecc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076ed1  cmp     [rax+7CCh], ebx
0x180076ed7  jz      short loc_180076EED
0x180076ed9  mov     r9d, ebx; int
0x180076edc  mov     r8d, 745h; int
0x180076ee2  mov     rdx, rsi; char *
0x180076ee5  mov     rcx, rax; this
0x180076ee8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076eed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076ef4  jb      loc_18007726E
0x180076efa  mov     edx, 7Ch ; '|'
0x180076eff  jmp     loc_180077250
0x180076f04  lea     rcx, [rbp+arg_8]; this
0x180076f08  mov     [rax], di
0x180076f0b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180076f10  cmp     bx, 1Eh
0x180076f14  jnz     loc_1800770A8
0x180076f1a  mov     eax, [rbp+arg_0]
0x180076f1d  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180076f21  shr     eax, 1
0x180076f23  mov     r8, r12; lpMultiByteStr
0x180076f26  mov     [rsp+30h+cchWideChar], eax; cchWideChar
0x180076f2a  xor     edx, edx; dwFlags
0x180076f2c  mov     rax, [r15+8]
0x180076f30  xor     ecx, ecx; CodePage
0x180076f32  mov     [rsp+30h+lpWideCharStr], rax; lpWideCharStr
0x180076f37  mov     ebx, edi
0x180076f39  mov     word ptr [r15], 1Fh
0x180076f3f  call    cs:__imp_MultiByteToWideChar
0x180076f46  nop     dword ptr [rax+rax+00h]
0x180076f4b  test    eax, eax
0x180076f4d  jnz     loc_180077277
0x180076f53  mov     r12d, 759h
0x180076f59  lea     rcx, [rbp+arg_8]; this
0x180076f5d  mov     r8d, r12d; int
0x180076f60  mov     rdx, rsi; char *
0x180076f63  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180076f68  call    cs:__imp_GetLastError
0x180076f6f  nop     dword ptr [rax+rax+00h]
0x180076f74  mov     ebx, eax
0x180076f76  test    eax, eax
0x180076f78  jle     short loc_180076F83
0x180076f7a  movzx   ebx, ax
0x180076f7d  or      ebx, 80070000h
0x180076f83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076f8a  test    ebx, ebx
0x180076f8c  jns     loc_180077019
0x180076f92  test    rcx, rcx
0x180076f95  jnz     short loc_180076FDE
0x180076f97  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076f9e  nop     dword ptr [rax+rax+00h]
0x180076fa3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076faa  mov     rcx, rax
0x180076fad  test    rax, rax
0x180076fb0  jz      short loc_180076FD0
0x180076fb2  mov     rax, [rax]
0x180076fb5  mov     edx, 7F0h
0x180076fba  mov     rax, [rax+8]
0x180076fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076fc3  test    eax, eax
0x180076fc5  jz      short loc_180076FD0
0x180076fc7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076fce  jmp     short loc_180076FDE
0x180076fd0  lea     rcx, qword_1800DBF70; this
0x180076fd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076fde  cmp     [rcx+8], dil
0x180076fe2  jz      short loc_180077002
0x180076fe4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076fe9  cmp     [rax+7CCh], ebx
0x180076fef  jz      short loc_180077002
0x180076ff1  mov     r9d, ebx; int
0x180076ff4  mov     r8d, r12d; int
0x180076ff7  mov     rdx, rsi; char *
0x180076ffa  mov     rcx, rax; this
0x180076ffd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077002  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180077009  jb      loc_18007726E
0x18007700f  mov     edx, 7Dh ; '}'
0x180077014  jmp     loc_180077250
0x180077019  mov     ebx, 8000FFFFh
0x18007701e  test    rcx, rcx
0x180077021  jnz     short loc_18007706A
0x180077023  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007702a  nop     dword ptr [rax+rax+00h]
0x18007702f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077036  mov     rcx, rax
0x180077039  test    rax, rax
0x18007703c  jz      short loc_18007705C
0x18007703e  mov     rax, [rax]
0x180077041  mov     edx, 7F0h
0x180077046  mov     rax, [rax+8]
0x18007704a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007704f  test    eax, eax
0x180077051  jz      short loc_18007705C
0x180077053  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007705a  jmp     short loc_18007706A
0x18007705c  lea     rcx, qword_1800DBF70; this
0x180077063  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007706a  cmp     [rcx+8], dil
0x18007706e  jz      short loc_180077091
0x180077070  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077075  cmp     [rax+7CCh], ebx
0x18007707b  jz      short loc_180077091
0x18007707d  mov     r9d, ebx; int
0x180077080  mov     r8d, 75Ah; int
0x180077086  mov     rdx, rsi; char *
0x180077089  mov     rcx, rax; this
0x18007708c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077091  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180077098  jb      loc_18007726E
0x18007709e  mov     edx, 7Eh ; '~'
0x1800770a3  jmp     loc_180077250
0x1800770a8  mov     eax, 1Fh
0x1800770ad  cmp     bx, ax
0x1800770b0  jnz     loc_180077175
0x1800770b6  mov     rcx, [r15+8]; unsigned __int16 *
0x1800770ba  mov     r8, r12; unsigned __int16 *
0x1800770bd  shr     r13, 1
0x1800770c0  mov     rdx, r13; unsigned __int64
0x1800770c3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800770c8  mov     r12d, 760h
0x1800770ce  lea     rcx, [rbp+arg_8]; this
0x1800770d2  mov     r8d, r12d; int
0x1800770d5  mov     rdx, rsi; char *
0x1800770d8  mov     ebx, eax
0x1800770da  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800770df  test    ebx, ebx
0x1800770e1  jns     loc_18007726E
0x1800770e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800770ee  test    rcx, rcx
0x1800770f1  jnz     short loc_18007713A
0x1800770f3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800770fa  nop     dword ptr [rax+rax+00h]
0x1800770ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077106  mov     rcx, rax
0x180077109  test    rax, rax
0x18007710c  jz      short loc_18007712C
0x18007710e  mov     rax, [rax]
0x180077111  mov     edx, 7F0h
0x180077116  mov     rax, [rax+8]
0x18007711a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007711f  test    eax, eax
0x180077121  jz      short loc_18007712C
0x180077123  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007712a  jmp     short loc_18007713A
0x18007712c  lea     rcx, qword_1800DBF70; this
0x180077133  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007713a  cmp     [rcx+8], dil
0x18007713e  jz      short loc_18007715E
0x180077140  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077145  cmp     [rax+7CCh], ebx
0x18007714b  jz      short loc_18007715E
0x18007714d  mov     r9d, ebx; int
0x180077150  mov     r8d, r12d; int
0x180077153  mov     rdx, rsi; char *
0x180077156  mov     rcx, rax; this
0x180077159  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007715e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180077165  jb      loc_18007726E
0x18007716b  mov     edx, 7Fh
0x180077170  jmp     loc_180077250
0x180077175  mov     rcx, r12; psz
0x180077178  mov     ebx, edi
0x18007717a  call    cs:__imp_SysAllocString
0x180077181  nop     dword ptr [rax+rax+00h]
0x180077186  mov     [r15+8], rax
0x18007718a  test    rax, rax
0x18007718d  jnz     loc_180077277
0x180077193  mov     r12d, 767h
0x180077199  lea     rcx, [rbp+arg_8]; this
0x18007719d  mov     r8d, r12d; int
0x1800771a0  mov     rdx, rsi; char *
0x1800771a3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800771a8  call    cs:__imp_GetLastError
0x1800771af  nop     dword ptr [rax+rax+00h]
0x1800771b4  mov     ebx, eax
0x1800771b6  test    eax, eax
0x1800771b8  jle     short loc_1800771C3
0x1800771ba  movzx   ebx, ax
0x1800771bd  or      ebx, 80070000h
0x1800771c3  test    ebx, ebx
0x1800771c5  jns     loc_18007726E
0x1800771cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800771d2  test    rcx, rcx
0x1800771d5  jnz     short loc_18007721E
0x1800771d7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800771de  nop     dword ptr [rax+rax+00h]
0x1800771e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800771ea  mov     rcx, rax
  ... truncated ...
```
