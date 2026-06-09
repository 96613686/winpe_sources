# CMFPropVariant::CreateString(ushort,void const *)

- ea: `0x180083944`
- end: `0x180083e8e`
- name: `?CreateString@CMFPropVariant@@QEAAJGPEBX@Z`
- size: `1354`
- prototype: `__int64 __fastcall(CMFPropVariant *this, __int16, const CHAR *)`
- caller_count: `12`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180062b30`
- `0x180070e10`
- `0x18009b6d0`
- `0x1800a5fa0`
- `0x1800bc71c`
- `0x1800bf7f0`
- `0x1800c19b0`
- `0x1800df150`
- `0x1800f400c`
- `0x18014d220`
- `0x180150cc0`
- `0x180152a60`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x180012a20`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x180083944`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083db2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180083b6d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180083b6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800839c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180083ab3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180083bb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180083c3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180083d09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180083ddb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800839c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180083ab3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180083bb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180083c3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180083d09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180083ddb`
- `OLEAUT32!__imp_SysAllocString` at `0x180083d8a`
- `OLEAUT32!__imp_SysAllocString` at `0x180083d8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083a79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083a79`

## string_xrefs

- `0x18008399b`: `CMFPropVariant::CreateString`
- `0x180083a59`: `CMFPropVariant::CreateString`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::CreateString(CMFPropVariant *this, __int16 a2, const CHAR *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rdx
  wchar_t *v8; // rcx
  signed int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  _WORD *v14; // rax
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  signed int LastError; // eax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  BSTR v29; // rax
  signed int v30; // eax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  WCHAR *lpWideCharStr; // [rsp+20h] [rbp-10h]
  unsigned int v37; // [rsp+60h] [rbp+30h]
  char v38; // [rsp+68h] [rbp+38h] BYREF

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
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1854);
      v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      v9 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v8 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::CreateString", 1854, -2147024809);
      }
      if ( !g_wppLevels )
        goto LABEL_83;
      v12 = 123;
      goto LABEL_82;
    }
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&a3[2 * v6] );
  }
  if ( (unsigned __int16)(a2 - 30) <= 1u )
  {
    v37 = 2 * v6 + 2;
    *((_QWORD *)this + 1) = CoTaskMemAlloc(v37);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1861);
    v14 = (_WORD *)*((_QWORD *)this + 1);
    if ( !v14 )
    {
      v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      v9 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v17, "CMFPropVariant::CreateString", 1861, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_83;
      v12 = 124;
LABEL_82:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, this, v9);
LABEL_83:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
      return (unsigned int)v9;
    }
    *v14 = 0;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
    if ( a2 == 30 )
    {
      lpWideCharStr = (WCHAR *)*((_QWORD *)this + 1);
      v9 = 0;
      *(_WORD *)this = 31;
      if ( !MultiByteToWideChar(0, 0, a3, -1, lpWideCharStr, v37 >> 1) )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1881);
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( v9 >= 0 )
        {
          v9 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v20 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v24 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v24, "CMFPropVariant::CreateString", 1882, -2147418113);
          }
          if ( !g_wppLevels )
            goto LABEL_83;
          v12 = 126;
        }
        else
        {
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
            CallStackTracing::s_wpInstance = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
            {
              v20 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v22 + 499) != v9 )
              CallStackContext::TraceFailure(v22, "CMFPropVariant::CreateString", 1881, v9);
          }
          if ( !g_wppLevels )
            goto LABEL_83;
          v12 = 125;
        }
        goto LABEL_82;
      }
      return (unsigned int)v9;
    }
    if ( a2 == 31 )
    {
      v9 = StringCchCopyW(*((unsigned __int16 **)this + 1), (unsigned __int64)v37 >> 1, (const unsigned __int16 *)a3);
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1888);
      if ( v9 >= 0 )
        goto LABEL_83;
      v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
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
        if ( *((_DWORD *)v28 + 499) != v9 )
          CallStackContext::TraceFailure(v28, "CMFPropVariant::CreateString", 1888, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_83;
      v12 = 127;
      goto LABEL_82;
    }
  }
  v9 = 0;
  v29 = SysAllocString((const OLECHAR *)a3);
  *((_QWORD *)this + 1) = v29;
  if ( !v29 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CMFPropVariant::CreateString", 1895);
    v30 = GetLastError();
    v9 = v30;
    if ( v30 > 0 )
      v9 = (unsigned __int16)v30 | 0x80070000;
    if ( v9 >= 0 )
      goto LABEL_83;
    v32 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
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
      v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
      if ( *((_DWORD *)v34 + 499) != v9 )
        CallStackContext::TraceFailure(v34, "CMFPropVariant::CreateString", 1895, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_83;
    v12 = 128;
    goto LABEL_82;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180083944  mov     [rsp-28h+arg_10], rbx
0x180083949  mov     [rsp-28h+arg_18], rsi
0x18008394e  push    rbp
0x18008394f  push    rdi
0x180083950  push    r12
0x180083952  push    r13
0x180083954  push    r15
0x180083956  mov     rbp, rsp
0x180083959  sub     rsp, 30h
0x18008395d  mov     [rcx], dx
0x180083960  mov     r12, r8
0x180083963  movzx   ebx, dx
0x180083966  mov     r15, rcx
0x180083969  mov     eax, 1Fh
0x18008396e  cmp     dx, 1Eh
0x180083972  jnz     short loc_180083988
0x180083974  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180083978  xor     edi, edi
0x18008397a  inc     rdx
0x18008397d  cmp     [r8+rdx], dil
0x180083981  jnz     short loc_18008397A
0x180083983  jmp     loc_180083A56
0x180083988  cmp     bx, ax
0x18008398b  jz      loc_180083A46
0x180083991  cmp     bx, 8
0x180083995  jz      loc_180083A46
0x18008399b  lea     rsi, aCmfpropvariant_15; "CMFPropVariant::CreateString"
0x1800839a2  mov     r8d, 73Eh; int
0x1800839a8  mov     rdx, rsi; char *
0x1800839ab  lea     rcx, [rbp+arg_8]; this
0x1800839af  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800839b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800839bb  xor     edi, edi
0x1800839bd  mov     ebx, 80070057h
0x1800839c2  test    rcx, rcx
0x1800839c5  jnz     short loc_180083A08
0x1800839c7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800839cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800839d4  mov     rcx, rax
0x1800839d7  test    rax, rax
0x1800839da  jz      short loc_1800839FA
0x1800839dc  mov     rax, [rax]
0x1800839df  mov     edx, 7F0h
0x1800839e4  mov     rax, [rax+8]
0x1800839e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800839ed  test    eax, eax
0x1800839ef  jz      short loc_1800839FA
0x1800839f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800839f8  jmp     short loc_180083A08
0x1800839fa  lea     rcx, qword_1801B07E0; this
0x180083a01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180083a08  cmp     [rcx+8], dil
0x180083a0c  jz      short loc_180083A2F
0x180083a0e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180083a13  cmp     [rax+7CCh], ebx
0x180083a19  jz      short loc_180083A2F
0x180083a1b  mov     r9d, ebx; int
0x180083a1e  mov     r8d, 73Eh; int
0x180083a24  mov     rdx, rsi; char *
0x180083a27  mov     rcx, rax; this
0x180083a2a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180083a2f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180083a36  jb      loc_180083E6C
0x180083a3c  mov     edx, 7Bh ; '{'
0x180083a41  jmp     loc_180083E4E
0x180083a46  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180083a4a  xor     edi, edi
0x180083a4c  inc     rdx
0x180083a4f  cmp     [r8+rdx*2], di
0x180083a54  jnz     short loc_180083A4C
0x180083a56  lea     eax, [rbx-1Eh]
0x180083a59  lea     rsi, aCmfpropvariant_15; "CMFPropVariant::CreateString"
0x180083a60  cmp     ax, 1
0x180083a64  ja      loc_180083D85
0x180083a6a  lea     edx, ds:2[rdx*2]
0x180083a71  mov     ecx, edx; cb
0x180083a73  mov     [rbp+arg_0], edx
0x180083a76  mov     r13d, edx
0x180083a79  call    cs:__imp_CoTaskMemAlloc
0x180083a7f  mov     r8d, 745h; int
0x180083a85  lea     rcx, [rbp+arg_8]; this
0x180083a89  mov     rdx, rsi; char *
0x180083a8c  mov     [r15+8], rax
0x180083a90  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180083a95  mov     rax, [r15+8]
0x180083a99  test    rax, rax
0x180083a9c  jnz     loc_180083B32
0x180083aa2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180083aa9  mov     ebx, 8007000Eh
0x180083aae  test    rcx, rcx
0x180083ab1  jnz     short loc_180083AF4
0x180083ab3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180083ab9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180083ac0  mov     rcx, rax
0x180083ac3  test    rax, rax
0x180083ac6  jz      short loc_180083AE6
0x180083ac8  mov     rax, [rax]
0x180083acb  mov     edx, 7F0h
0x180083ad0  mov     rax, [rax+8]
0x180083ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083ad9  test    eax, eax
0x180083adb  jz      short loc_180083AE6
0x180083add  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180083ae4  jmp     short loc_180083AF4
0x180083ae6  lea     rcx, qword_1801B07E0; this
0x180083aed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180083af4  cmp     [rcx+8], dil
0x180083af8  jz      short loc_180083B1B
0x180083afa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180083aff  cmp     [rax+7CCh], ebx
0x180083b05  jz      short loc_180083B1B
0x180083b07  mov     r9d, ebx; int
0x180083b0a  mov     r8d, 745h; int
0x180083b10  mov     rdx, rsi; char *
0x180083b13  mov     rcx, rax; this
0x180083b16  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180083b1b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180083b22  jb      loc_180083E6C
0x180083b28  mov     edx, 7Ch ; '|'
0x180083b2d  jmp     loc_180083E4E
0x180083b32  lea     rcx, [rbp+arg_8]; this
0x180083b36  mov     [rax], di
0x180083b39  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180083b3e  cmp     bx, 1Eh
0x180083b42  jnz     loc_180083CBE
0x180083b48  mov     eax, [rbp+arg_0]
0x180083b4b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180083b4f  shr     eax, 1
0x180083b51  mov     r8, r12; lpMultiByteStr
0x180083b54  mov     [rsp+30h+cchWideChar], eax; cchWideChar
0x180083b58  xor     edx, edx; dwFlags
0x180083b5a  mov     rax, [r15+8]
0x180083b5e  xor     ecx, ecx; CodePage
0x180083b60  mov     [rsp+30h+lpWideCharStr], rax; lpWideCharStr
0x180083b65  mov     ebx, edi
0x180083b67  mov     word ptr [r15], 1Fh
0x180083b6d  call    cs:__imp_MultiByteToWideChar
0x180083b73  test    eax, eax
0x180083b75  jnz     loc_180083E75
0x180083b7b  mov     r12d, 759h
0x180083b81  lea     rcx, [rbp+arg_8]; this
0x180083b85  mov     r8d, r12d; int
0x180083b88  mov     rdx, rsi; char *
0x180083b8b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180083b90  call    cs:__imp_GetLastError
0x180083b96  mov     ebx, eax
0x180083b98  test    eax, eax
0x180083b9a  jle     short loc_180083BA5
0x180083b9c  movzx   ebx, ax
0x180083b9f  or      ebx, 80070000h
0x180083ba5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180083bac  test    ebx, ebx
0x180083bae  jns     loc_180083C35
0x180083bb4  test    rcx, rcx
0x180083bb7  jnz     short loc_180083BFA
0x180083bb9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180083bbf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180083bc6  mov     rcx, rax
0x180083bc9  test    rax, rax
0x180083bcc  jz      short loc_180083BEC
0x180083bce  mov     rax, [rax]
0x180083bd1  mov     edx, 7F0h
0x180083bd6  mov     rax, [rax+8]
0x180083bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083bdf  test    eax, eax
0x180083be1  jz      short loc_180083BEC
0x180083be3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180083bea  jmp     short loc_180083BFA
0x180083bec  lea     rcx, qword_1801B07E0; this
0x180083bf3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180083bfa  cmp     [rcx+8], dil
0x180083bfe  jz      short loc_180083C1E
0x180083c00  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180083c05  cmp     [rax+7CCh], ebx
0x180083c0b  jz      short loc_180083C1E
0x180083c0d  mov     r9d, ebx; int
0x180083c10  mov     r8d, r12d; int
0x180083c13  mov     rdx, rsi; char *
0x180083c16  mov     rcx, rax; this
0x180083c19  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180083c1e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180083c25  jb      loc_180083E6C
0x180083c2b  mov     edx, 7Dh ; '}'
0x180083c30  jmp     loc_180083E4E
0x180083c35  mov     ebx, 8000FFFFh
0x180083c3a  test    rcx, rcx
0x180083c3d  jnz     short loc_180083C80
0x180083c3f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180083c45  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180083c4c  mov     rcx, rax
0x180083c4f  test    rax, rax
0x180083c52  jz      short loc_180083C72
0x180083c54  mov     rax, [rax]
0x180083c57  mov     edx, 7F0h
0x180083c5c  mov     rax, [rax+8]
0x180083c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083c65  test    eax, eax
0x180083c67  jz      short loc_180083C72
0x180083c69  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180083c70  jmp     short loc_180083C80
0x180083c72  lea     rcx, qword_1801B07E0; this
0x180083c79  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180083c80  cmp     [rcx+8], dil
0x180083c84  jz      short loc_180083CA7
0x180083c86  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180083c8b  cmp     [rax+7CCh], ebx
0x180083c91  jz      short loc_180083CA7
0x180083c93  mov     r9d, ebx; int
0x180083c96  mov     r8d, 75Ah; int
0x180083c9c  mov     rdx, rsi; char *
0x180083c9f  mov     rcx, rax; this
0x180083ca2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180083ca7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180083cae  jb      loc_180083E6C
0x180083cb4  mov     edx, 7Eh ; '~'
0x180083cb9  jmp     loc_180083E4E
0x180083cbe  mov     eax, 1Fh
0x180083cc3  cmp     bx, ax
0x180083cc6  jnz     loc_180083D85
0x180083ccc  mov     rcx, [r15+8]; unsigned __int16 *
0x180083cd0  mov     r8, r12; unsigned __int16 *
0x180083cd3  shr     r13, 1
0x180083cd6  mov     rdx, r13; unsigned __int64
0x180083cd9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180083cde  mov     r12d, 760h
0x180083ce4  lea     rcx, [rbp+arg_8]; this
0x180083ce8  mov     r8d, r12d; int
0x180083ceb  mov     rdx, rsi; char *
0x180083cee  mov     ebx, eax
0x180083cf0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180083cf5  test    ebx, ebx
0x180083cf7  jns     loc_180083E6C
0x180083cfd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180083d04  test    rcx, rcx
0x180083d07  jnz     short loc_180083D4A
0x180083d09  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180083d0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180083d16  mov     rcx, rax
0x180083d19  test    rax, rax
0x180083d1c  jz      short loc_180083D3C
0x180083d1e  mov     rax, [rax]
0x180083d21  mov     edx, 7F0h
0x180083d26  mov     rax, [rax+8]
0x180083d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083d2f  test    eax, eax
0x180083d31  jz      short loc_180083D3C
0x180083d33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180083d3a  jmp     short loc_180083D4A
0x180083d3c  lea     rcx, qword_1801B07E0; this
0x180083d43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180083d4a  cmp     [rcx+8], dil
0x180083d4e  jz      short loc_180083D6E
0x180083d50  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180083d55  cmp     [rax+7CCh], ebx
0x180083d5b  jz      short loc_180083D6E
0x180083d5d  mov     r9d, ebx; int
0x180083d60  mov     r8d, r12d; int
0x180083d63  mov     rdx, rsi; char *
0x180083d66  mov     rcx, rax; this
0x180083d69  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180083d6e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180083d75  jb      loc_180083E6C
0x180083d7b  mov     edx, 7Fh
0x180083d80  jmp     loc_180083E4E
0x180083d85  mov     rcx, r12; psz
0x180083d88  mov     ebx, edi
0x180083d8a  call    cs:__imp_SysAllocString
0x180083d90  mov     [r15+8], rax
0x180083d94  test    rax, rax
0x180083d97  jnz     loc_180083E75
0x180083d9d  mov     r12d, 767h
0x180083da3  lea     rcx, [rbp+arg_8]; this
0x180083da7  mov     r8d, r12d; int
0x180083daa  mov     rdx, rsi; char *
0x180083dad  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180083db2  call    cs:__imp_GetLastError
0x180083db8  mov     ebx, eax
0x180083dba  test    eax, eax
0x180083dbc  jle     short loc_180083DC7
0x180083dbe  movzx   ebx, ax
0x180083dc1  or      ebx, 80070000h
0x180083dc7  test    ebx, ebx
0x180083dc9  jns     loc_180083E6C
0x180083dcf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180083dd6  test    rcx, rcx
0x180083dd9  jnz     short loc_180083E1C
0x180083ddb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180083de1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180083de8  mov     rcx, rax
0x180083deb  test    rax, rax
0x180083dee  jz      short loc_180083E0E
0x180083df0  mov     rax, [rax]
0x180083df3  mov     edx, 7F0h
0x180083df8  mov     rax, [rax+8]
0x180083dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083e01  test    eax, eax
0x180083e03  jz      short loc_180083E0E
0x180083e05  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180083e0c  jmp     short loc_180083E1C
0x180083e0e  lea     rcx, qword_1801B07E0; this
  ... truncated ...
```
