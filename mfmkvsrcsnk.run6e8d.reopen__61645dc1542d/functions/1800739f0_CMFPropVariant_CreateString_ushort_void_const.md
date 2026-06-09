# CMFPropVariant::CreateString(ushort,void const *)

- ea: `0x1800739f0`
- end: `0x180073f3a`
- name: `?CreateString@CMFPropVariant@@QEAAJGPEBX@Z`
- size: `1354`
- prototype: `int(CMFPropVariant *__hidden this, unsigned __int16, const void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fe50`
- `0x180071710`

## callees

- `0x180006c24`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x1800739f0`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073c3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073c3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073e5e`
- `OLEAUT32!__imp_SysAllocString` at `0x180073e36`
- `OLEAUT32!__imp_SysAllocString` at `0x180073e36`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180073c19`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180073c19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073b25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180073b25`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073a73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073b5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073c65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073ceb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073db5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073e87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073a73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073b5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073c65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073ceb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073db5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073e87`

## string_xrefs

- `0x180073a47`: `CMFPropVariant::CreateString`
- `0x180073b05`: `CMFPropVariant::CreateString`

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
          v10 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v19 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v26 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v26 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v34 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v42 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x1800739f0  mov     [rsp-28h+arg_10], rbx
0x1800739f5  mov     [rsp-28h+arg_18], rsi
0x1800739fa  push    rbp
0x1800739fb  push    rdi
0x1800739fc  push    r12
0x1800739fe  push    r13
0x180073a00  push    r15
0x180073a02  mov     rbp, rsp
0x180073a05  sub     rsp, 30h
0x180073a09  mov     [rcx], dx
0x180073a0c  mov     r12, r8
0x180073a0f  movzx   ebx, dx
0x180073a12  mov     r15, rcx
0x180073a15  mov     eax, 1Fh
0x180073a1a  cmp     dx, 1Eh
0x180073a1e  jnz     short loc_180073A34
0x180073a20  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180073a24  xor     edi, edi
0x180073a26  inc     rdx
0x180073a29  cmp     [r8+rdx], dil
0x180073a2d  jnz     short loc_180073A26
0x180073a2f  jmp     loc_180073B02
0x180073a34  cmp     bx, ax
0x180073a37  jz      loc_180073AF2
0x180073a3d  cmp     bx, 8
0x180073a41  jz      loc_180073AF2
0x180073a47  lea     rsi, aCmfpropvariant_6; "CMFPropVariant::CreateString"
0x180073a4e  mov     r8d, 73Eh; int
0x180073a54  mov     rdx, rsi; char *
0x180073a57  lea     rcx, [rbp+arg_8]; this
0x180073a5b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180073a60  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073a67  xor     edi, edi
0x180073a69  mov     ebx, 80070057h
0x180073a6e  test    rcx, rcx
0x180073a71  jnz     short loc_180073AB4
0x180073a73  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073a79  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073a80  mov     rcx, rax
0x180073a83  test    rax, rax
0x180073a86  jz      short loc_180073AA6
0x180073a88  mov     rax, [rax]
0x180073a8b  mov     edx, 7F0h
0x180073a90  mov     rax, [rax+8]
0x180073a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073a99  test    eax, eax
0x180073a9b  jz      short loc_180073AA6
0x180073a9d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073aa4  jmp     short loc_180073AB4
0x180073aa6  lea     rcx, qword_1800D6F70; this
0x180073aad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073ab4  cmp     [rcx+8], dil
0x180073ab8  jz      short loc_180073ADB
0x180073aba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073abf  cmp     [rax+7CCh], ebx
0x180073ac5  jz      short loc_180073ADB
0x180073ac7  mov     r9d, ebx; int
0x180073aca  mov     r8d, 73Eh; int
0x180073ad0  mov     rdx, rsi; char *
0x180073ad3  mov     rcx, rax; this
0x180073ad6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073adb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073ae2  jb      loc_180073F18
0x180073ae8  mov     edx, 7Bh ; '{'
0x180073aed  jmp     loc_180073EFA
0x180073af2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180073af6  xor     edi, edi
0x180073af8  inc     rdx
0x180073afb  cmp     [r8+rdx*2], di
0x180073b00  jnz     short loc_180073AF8
0x180073b02  lea     eax, [rbx-1Eh]
0x180073b05  lea     rsi, aCmfpropvariant_6; "CMFPropVariant::CreateString"
0x180073b0c  cmp     ax, 1
0x180073b10  ja      loc_180073E31
0x180073b16  lea     edx, ds:2[rdx*2]
0x180073b1d  mov     ecx, edx; cb
0x180073b1f  mov     [rbp+arg_0], edx
0x180073b22  mov     r13d, edx
0x180073b25  call    cs:__imp_CoTaskMemAlloc
0x180073b2b  mov     r8d, 745h; int
0x180073b31  lea     rcx, [rbp+arg_8]; this
0x180073b35  mov     rdx, rsi; char *
0x180073b38  mov     [r15+8], rax
0x180073b3c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180073b41  mov     rax, [r15+8]
0x180073b45  test    rax, rax
0x180073b48  jnz     loc_180073BDE
0x180073b4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073b55  mov     ebx, 8007000Eh
0x180073b5a  test    rcx, rcx
0x180073b5d  jnz     short loc_180073BA0
0x180073b5f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073b65  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073b6c  mov     rcx, rax
0x180073b6f  test    rax, rax
0x180073b72  jz      short loc_180073B92
0x180073b74  mov     rax, [rax]
0x180073b77  mov     edx, 7F0h
0x180073b7c  mov     rax, [rax+8]
0x180073b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073b85  test    eax, eax
0x180073b87  jz      short loc_180073B92
0x180073b89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073b90  jmp     short loc_180073BA0
0x180073b92  lea     rcx, qword_1800D6F70; this
0x180073b99  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073ba0  cmp     [rcx+8], dil
0x180073ba4  jz      short loc_180073BC7
0x180073ba6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073bab  cmp     [rax+7CCh], ebx
0x180073bb1  jz      short loc_180073BC7
0x180073bb3  mov     r9d, ebx; int
0x180073bb6  mov     r8d, 745h; int
0x180073bbc  mov     rdx, rsi; char *
0x180073bbf  mov     rcx, rax; this
0x180073bc2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073bc7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073bce  jb      loc_180073F18
0x180073bd4  mov     edx, 7Ch ; '|'
0x180073bd9  jmp     loc_180073EFA
0x180073bde  lea     rcx, [rbp+arg_8]; this
0x180073be2  mov     [rax], di
0x180073be5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180073bea  cmp     bx, 1Eh
0x180073bee  jnz     loc_180073D6A
0x180073bf4  mov     eax, [rbp+arg_0]
0x180073bf7  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180073bfb  shr     eax, 1
0x180073bfd  mov     r8, r12; lpMultiByteStr
0x180073c00  mov     [rsp+30h+cchWideChar], eax; cchWideChar
0x180073c04  xor     edx, edx; dwFlags
0x180073c06  mov     rax, [r15+8]
0x180073c0a  xor     ecx, ecx; CodePage
0x180073c0c  mov     [rsp+30h+lpWideCharStr], rax; lpWideCharStr
0x180073c11  mov     ebx, edi
0x180073c13  mov     word ptr [r15], 1Fh
0x180073c19  call    cs:__imp_MultiByteToWideChar
0x180073c1f  test    eax, eax
0x180073c21  jnz     loc_180073F21
0x180073c27  mov     r12d, 759h
0x180073c2d  lea     rcx, [rbp+arg_8]; this
0x180073c31  mov     r8d, r12d; int
0x180073c34  mov     rdx, rsi; char *
0x180073c37  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180073c3c  call    cs:__imp_GetLastError
0x180073c42  mov     ebx, eax
0x180073c44  test    eax, eax
0x180073c46  jle     short loc_180073C51
0x180073c48  movzx   ebx, ax
0x180073c4b  or      ebx, 80070000h
0x180073c51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073c58  test    ebx, ebx
0x180073c5a  jns     loc_180073CE1
0x180073c60  test    rcx, rcx
0x180073c63  jnz     short loc_180073CA6
0x180073c65  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073c6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073c72  mov     rcx, rax
0x180073c75  test    rax, rax
0x180073c78  jz      short loc_180073C98
0x180073c7a  mov     rax, [rax]
0x180073c7d  mov     edx, 7F0h
0x180073c82  mov     rax, [rax+8]
0x180073c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073c8b  test    eax, eax
0x180073c8d  jz      short loc_180073C98
0x180073c8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073c96  jmp     short loc_180073CA6
0x180073c98  lea     rcx, qword_1800D6F70; this
0x180073c9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073ca6  cmp     [rcx+8], dil
0x180073caa  jz      short loc_180073CCA
0x180073cac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073cb1  cmp     [rax+7CCh], ebx
0x180073cb7  jz      short loc_180073CCA
0x180073cb9  mov     r9d, ebx; int
0x180073cbc  mov     r8d, r12d; int
0x180073cbf  mov     rdx, rsi; char *
0x180073cc2  mov     rcx, rax; this
0x180073cc5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073cca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073cd1  jb      loc_180073F18
0x180073cd7  mov     edx, 7Dh ; '}'
0x180073cdc  jmp     loc_180073EFA
0x180073ce1  mov     ebx, 8000FFFFh
0x180073ce6  test    rcx, rcx
0x180073ce9  jnz     short loc_180073D2C
0x180073ceb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073cf1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073cf8  mov     rcx, rax
0x180073cfb  test    rax, rax
0x180073cfe  jz      short loc_180073D1E
0x180073d00  mov     rax, [rax]
0x180073d03  mov     edx, 7F0h
0x180073d08  mov     rax, [rax+8]
0x180073d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d11  test    eax, eax
0x180073d13  jz      short loc_180073D1E
0x180073d15  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073d1c  jmp     short loc_180073D2C
0x180073d1e  lea     rcx, qword_1800D6F70; this
0x180073d25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073d2c  cmp     [rcx+8], dil
0x180073d30  jz      short loc_180073D53
0x180073d32  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073d37  cmp     [rax+7CCh], ebx
0x180073d3d  jz      short loc_180073D53
0x180073d3f  mov     r9d, ebx; int
0x180073d42  mov     r8d, 75Ah; int
0x180073d48  mov     rdx, rsi; char *
0x180073d4b  mov     rcx, rax; this
0x180073d4e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073d53  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073d5a  jb      loc_180073F18
0x180073d60  mov     edx, 7Eh ; '~'
0x180073d65  jmp     loc_180073EFA
0x180073d6a  mov     eax, 1Fh
0x180073d6f  cmp     bx, ax
0x180073d72  jnz     loc_180073E31
0x180073d78  mov     rcx, [r15+8]; unsigned __int16 *
0x180073d7c  mov     r8, r12; unsigned __int16 *
0x180073d7f  shr     r13, 1
0x180073d82  mov     rdx, r13; unsigned __int64
0x180073d85  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180073d8a  mov     r12d, 760h
0x180073d90  lea     rcx, [rbp+arg_8]; this
0x180073d94  mov     r8d, r12d; int
0x180073d97  mov     rdx, rsi; char *
0x180073d9a  mov     ebx, eax
0x180073d9c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180073da1  test    ebx, ebx
0x180073da3  jns     loc_180073F18
0x180073da9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073db0  test    rcx, rcx
0x180073db3  jnz     short loc_180073DF6
0x180073db5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073dbb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073dc2  mov     rcx, rax
0x180073dc5  test    rax, rax
0x180073dc8  jz      short loc_180073DE8
0x180073dca  mov     rax, [rax]
0x180073dcd  mov     edx, 7F0h
0x180073dd2  mov     rax, [rax+8]
0x180073dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ddb  test    eax, eax
0x180073ddd  jz      short loc_180073DE8
0x180073ddf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073de6  jmp     short loc_180073DF6
0x180073de8  lea     rcx, qword_1800D6F70; this
0x180073def  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073df6  cmp     [rcx+8], dil
0x180073dfa  jz      short loc_180073E1A
0x180073dfc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073e01  cmp     [rax+7CCh], ebx
0x180073e07  jz      short loc_180073E1A
0x180073e09  mov     r9d, ebx; int
0x180073e0c  mov     r8d, r12d; int
0x180073e0f  mov     rdx, rsi; char *
0x180073e12  mov     rcx, rax; this
0x180073e15  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073e1a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073e21  jb      loc_180073F18
0x180073e27  mov     edx, 7Fh
0x180073e2c  jmp     loc_180073EFA
0x180073e31  mov     rcx, r12; psz
0x180073e34  mov     ebx, edi
0x180073e36  call    cs:__imp_SysAllocString
0x180073e3c  mov     [r15+8], rax
0x180073e40  test    rax, rax
0x180073e43  jnz     loc_180073F21
0x180073e49  mov     r12d, 767h
0x180073e4f  lea     rcx, [rbp+arg_8]; this
0x180073e53  mov     r8d, r12d; int
0x180073e56  mov     rdx, rsi; char *
0x180073e59  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180073e5e  call    cs:__imp_GetLastError
0x180073e64  mov     ebx, eax
0x180073e66  test    eax, eax
0x180073e68  jle     short loc_180073E73
0x180073e6a  movzx   ebx, ax
0x180073e6d  or      ebx, 80070000h
0x180073e73  test    ebx, ebx
0x180073e75  jns     loc_180073F18
0x180073e7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073e82  test    rcx, rcx
0x180073e85  jnz     short loc_180073EC8
0x180073e87  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073e8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073e94  mov     rcx, rax
0x180073e97  test    rax, rax
0x180073e9a  jz      short loc_180073EBA
0x180073e9c  mov     rax, [rax]
0x180073e9f  mov     edx, 7F0h
0x180073ea4  mov     rax, [rax+8]
0x180073ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ead  test    eax, eax
0x180073eaf  jz      short loc_180073EBA
0x180073eb1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073eb8  jmp     short loc_180073EC8
0x180073eba  lea     rcx, qword_1800D6F70; this
  ... truncated ...
```
