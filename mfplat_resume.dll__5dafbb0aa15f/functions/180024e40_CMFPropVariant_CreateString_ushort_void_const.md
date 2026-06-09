# CMFPropVariant::CreateString(ushort,void const *)

- ea: `0x180024e40`
- end: `0x1800255a5`
- name: `?CreateString@CMFPropVariant@@QEAAJGPEBX@Z`
- size: `1893`
- prototype: `int(CMFPropVariant *__hidden this, unsigned __int16, const void *)`
- caller_count: `5`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800289f0`
- `0x18008a764`
- `0x1800e7408`
- `0x18011e9a0`
- `0x18013ec70`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x180024e40`
- `0x1800255b0`
- `0x180038bf0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024eda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024eda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252e8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800250e6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800250e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025035`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025035`
- `OLEAUT32!__imp_SysAllocString` at `0x180024eb1`
- `OLEAUT32!__imp_SysAllocString` at `0x180024eb1`

## string_xrefs

- `0x180024e99`: `CMFPropVariant::CreateString`
- `0x180025061`: `CMFPropVariant::CreateString`
- `0x1800251ee`: `CMFPropVariant::CreateString`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::CreateString(CMFPropVariant *this, unsigned __int16 a2, const CHAR *a3)
{
  const CHAR *v3; // rbx
  __int64 v6; // rax
  bool v7; // zf
  signed int v8; // ebp
  BSTR v9; // rax
  signed int LastError; // eax
  CallStackTracing *v11; // rcx
  __int64 v12; // rdx
  unsigned __int64 v13; // rdi
  wchar_t *v14; // rdx
  __int64 v15; // rax
  wchar_t *v16; // rax
  int v17; // eax
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  LPVOID v22; // rax
  CallStackTracing *v23; // rcx
  struct CallStackContext *v24; // rax
  __int64 m_dwDepth; // rcx
  __int64 v26; // rcx
  wchar_t *bstrVal; // rax
  CallStackTracing *v29; // r13
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v31; // rax
  signed int v32; // eax
  signed int v33; // ebx
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  struct CallStackContext *v36; // rax
  struct CallStackContext *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // r14
  unsigned int v40; // r14d
  WCHAR *lpWideCharStr; // [rsp+20h] [rbp-58h]
  CallStackScopeTrace v42; // [rsp+88h] [rbp+10h] BYREF

  this->vt = a2;
  v3 = a3;
  if ( a2 == 30 )
  {
    v39 = -1;
    do
      v7 = a3[++v39] == 0;
    while ( !v7 );
    v40 = 2 * v39 + 2;
  }
  else
  {
    if ( a2 != 31 && a2 != 8 )
    {
      CallStackScopeTrace::CallStackScopeTrace(&v42, "CMFPropVariant::CreateString", 1854);
      v29 = CallStackTracing::s_wpInstance;
      v8 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v29 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v29->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v29);
        if ( ThreadRelativeContext->m_result != -2147024809 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::CreateString", 1854, -2147024809);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_33;
      v12 = 123;
      goto LABEL_16;
    }
    v6 = -1;
    do
      v7 = *(_WORD *)&a3[2 * v6++ + 2] == 0;
    while ( !v7 );
    if ( a2 != 31 )
    {
      v8 = 0;
      v9 = SysAllocString((const OLECHAR *)a3);
      this->decVal.Lo64 = (unsigned __int64)v9;
      if ( v9 )
        return (unsigned int)v8;
      CallStackScopeTrace::CallStackScopeTrace(&v42, "CMFPropVariant::CreateString", 1895);
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 >= 0 )
        goto LABEL_33;
      v11 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v11 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v11->m_fEnabled )
      {
        v38 = CallStackTracing::GetThreadRelativeContext(v11);
        if ( v38->m_result != v8 )
          CallStackContext::TraceFailure(v38, "CMFPropVariant::CreateString", 1895, v8);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
LABEL_33:
        CallStackScopeTrace::~CallStackScopeTrace(&v42);
        return (unsigned int)v8;
      }
      v12 = 128;
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, this, v8);
      goto LABEL_33;
    }
    v40 = 2 * v6 + 2;
  }
  v22 = CoTaskMemAlloc(v40);
  v23 = CallStackTracing::s_wpInstance;
  this->decVal.Lo64 = (unsigned __int64)v22;
  if ( !v23 )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v23 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v23 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v23->m_fEnabled )
  {
    v24 = CallStackTracing::GetThreadRelativeContext(v23);
    m_dwDepth = v24->m_dwDepth;
    if ( (unsigned int)m_dwDepth < v24->m_dwMaxDepth )
    {
      v26 = m_dwDepth;
      v24->m_rgInfo[v26].m_pszFunction = "CMFPropVariant::CreateString";
      v24->m_rgInfo[v26].m_lineNumber = 1861;
    }
    ++v24->m_dwDepth;
    v23 = CallStackTracing::s_wpInstance;
  }
  bstrVal = this->bstrVal;
  if ( bstrVal )
  {
    v8 = 0;
    *bstrVal = 0;
    CallStackScopeTrace::~CallStackScopeTrace(&v42);
    if ( a2 != 30 )
    {
      v13 = (unsigned __int64)v40 >> 1;
      if ( v13 )
      {
        v14 = this->bstrVal;
        v15 = 2147483646;
        do
        {
          if ( !v15 )
            break;
          if ( !*(_WORD *)v3 )
            break;
          *v14 = *(_WORD *)v3;
          v3 += 2;
          ++v14;
          --v15;
          --v13;
        }
        while ( v13 );
        v16 = v14 - 1;
        if ( v13 )
          v16 = v14;
        *v16 = 0;
        v17 = -2147024774;
        if ( v13 )
          v17 = 0;
        v8 = v17;
      }
      else
      {
        v8 = -2147024809;
      }
      v18 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v18 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v18->m_fEnabled )
      {
        v19 = CallStackTracing::GetThreadRelativeContext(v18);
        v20 = v19->m_dwDepth;
        if ( (unsigned int)v20 < v19->m_dwMaxDepth )
        {
          v21 = v20;
          v19->m_rgInfo[v21].m_pszFunction = "CMFPropVariant::CreateString";
          v19->m_rgInfo[v21].m_lineNumber = 1888;
        }
        ++v19->m_dwDepth;
        v18 = CallStackTracing::s_wpInstance;
      }
      if ( v8 >= 0 )
        goto LABEL_33;
      if ( !v18 )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v18 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v18->m_fEnabled )
      {
        v37 = CallStackTracing::GetThreadRelativeContext(v18);
        if ( v37->m_result != v8 )
          CallStackContext::TraceFailure(v37, "CMFPropVariant::CreateString", 1888, v8);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_33;
      v12 = 127;
      goto LABEL_16;
    }
    lpWideCharStr = this->bstrVal;
    this->vt = 31;
    if ( MultiByteToWideChar(0, 0, v3, -1, lpWideCharStr, v40 >> 1) )
      return (unsigned int)v8;
    CallStackScopeTrace::CallStackScopeTrace(&v42, "CMFPropVariant::CreateString", 1881);
    v32 = GetLastError();
    v33 = v32;
    if ( v32 > 0 )
      v33 = (unsigned __int16)v32 | 0x80070000;
    v34 = CallStackTracing::s_wpInstance;
    if ( v33 < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v34 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v34->m_fEnabled )
      {
        v35 = CallStackTracing::GetThreadRelativeContext(v34);
        if ( v35->m_result != v33 )
          CallStackContext::TraceFailure(v35, "CMFPropVariant::CreateString", 1881, v33);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, this, v33);
      CallStackScopeTrace::~CallStackScopeTrace(&v42);
      return (unsigned int)v33;
    }
    else
    {
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v34 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v34->m_fEnabled )
      {
        v36 = CallStackTracing::GetThreadRelativeContext(v34);
        if ( v36->m_result != -2147418113 )
          CallStackContext::TraceFailure(v36, "CMFPropVariant::CreateString", 1882, -2147418113);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          126,
          &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
          this,
          -2147418113);
      CallStackScopeTrace::~CallStackScopeTrace(&v42);
      return 2147549183LL;
    }
  }
  else
  {
    if ( !v23 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v23 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v23->m_fEnabled )
    {
      v31 = CallStackTracing::GetThreadRelativeContext(v23);
      if ( v31->m_result != -2147024882 )
        CallStackContext::TraceFailure(v31, "CMFPropVariant::CreateString", 1861, -2147024882);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        124,
        &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        this,
        -2147024882);
    CallStackScopeTrace::~CallStackScopeTrace(&v42);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180024e40  push    rbx
0x180024e42  push    rbp
0x180024e43  push    rsi
0x180024e44  push    rdi
0x180024e45  push    r12
0x180024e47  push    r13
0x180024e49  push    r14
0x180024e4b  push    r15
0x180024e4d  sub     rsp, 38h
0x180024e51  mov     [rcx], dx
0x180024e54  mov     rbx, r8
0x180024e57  movzx   esi, dx
0x180024e5a  mov     r15, rcx
0x180024e5d  cmp     dx, 1Eh
0x180024e61  jz      loc_180025533
0x180024e67  cmp     dx, 1Fh
0x180024e6b  jnz     loc_180025553
0x180024e71  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180024e78  nop     dword ptr [rax+rax+00000000h]
0x180024e80  cmp     word ptr [r8+rax*2+2], 0
0x180024e87  lea     rax, [rax+1]
0x180024e8b  jnz     short loc_180024E80
0x180024e8d  cmp     si, 1Fh
0x180024e91  jz      loc_180025562
0x180024e97  xor     ebp, ebp
0x180024e99  lea     r12, aCmfpropvariant_11; "CMFPropVariant::CreateString"
0x180024ea0  lea     r13, stru_1801F8A30
0x180024ea7  mov     rcx, rbx; psz
0x180024eaa  lea     rdi, stru_1801FC290
0x180024eb1  call    cs:__imp_SysAllocString
0x180024eb7  mov     [r15+8], rax
0x180024ebb  test    rax, rax
0x180024ebe  jnz     loc_1800250F4
0x180024ec4  mov     r8d, 767h; int
0x180024eca  lea     rcx, [rsp+78h+arg_8]; this
0x180024ed2  mov     rdx, r12; char *
0x180024ed5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180024eda  call    cs:__imp_GetLastError
0x180024ee0  mov     ebp, eax
0x180024ee2  test    eax, eax
0x180024ee4  jle     short loc_180024EEF
0x180024ee6  movzx   ebp, ax
0x180024ee9  or      ebp, 80070000h
0x180024eef  test    ebp, ebp
0x180024ef1  jns     loc_18002501D
0x180024ef7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024efe  test    rcx, rcx
0x180024f01  jnz     short loc_180024F34
0x180024f03  mov     rax, cs:stru_1801FC290.__vftable
0x180024f0a  mov     edx, 7F0h
0x180024f0f  mov     rcx, rdi
0x180024f12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180024f19  mov     rax, [rax+8]
0x180024f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f22  test    eax, eax
0x180024f24  jnz     loc_1800254FD
0x180024f2a  mov     rcx, r13; this
0x180024f2d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180024f34  cmp     byte ptr [rcx+8], 0
0x180024f38  jnz     loc_180025509
0x180024f3e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024f45  jb      loc_18002501D
0x180024f4b  mov     edx, 80h
0x180024f50  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f57  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180024f5e  mov     r9, r15
0x180024f61  mov     dword ptr [rsp+78h+lpWideCharStr], ebp
0x180024f65  mov     rcx, [rcx+10h]
0x180024f69  call    WPP_SF_qD
0x180024f6e  jmp     loc_18002501D
0x180024f73  cmp     si, 1Fh
0x180024f77  jnz     loc_180024EA7
0x180024f7d  shr     rdi, 1
0x180024f80  jz      loc_18002559B
0x180024f86  mov     rdx, [r15+8]
0x180024f8a  mov     eax, 7FFFFFFEh
0x180024f8f  nop
0x180024f90  test    rax, rax
0x180024f93  jz      short loc_180024FB1
0x180024f95  movzx   ecx, word ptr [rbx]
0x180024f98  test    cx, cx
0x180024f9b  jz      short loc_180024FB1
0x180024f9d  mov     [rdx], cx
0x180024fa0  add     rbx, 2
0x180024fa4  add     rdx, 2
0x180024fa8  dec     rax
0x180024fab  sub     rdi, 1
0x180024faf  jnz     short loc_180024F90
0x180024fb1  test    rdi, rdi
0x180024fb4  lea     rax, [rdx-2]
0x180024fb8  cmovnz  rax, rdx
0x180024fbc  mov     [rax], bp
0x180024fbf  mov     eax, 8007007Ah
0x180024fc4  cmovnz  eax, ebp
0x180024fc7  mov     ebp, eax
0x180024fc9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180024fd0  lea     rdi, stru_1801FC290
0x180024fd7  test    rcx, rcx
0x180024fda  jz      loc_180025107
0x180024fe0  cmp     byte ptr [rcx+8], 0
0x180024fe4  jz      short loc_180025015
0x180024fe6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180024feb  mov     ecx, [rax+7C4h]
0x180024ff1  cmp     ecx, [rax+7C8h]
0x180024ff7  jnb     short loc_180025008
0x180024ff9  add     rcx, rcx
0x180024ffc  mov     [rax+rcx*8], r12
0x180025000  mov     dword ptr [rax+rcx*8+8], 760h
0x180025008  inc     dword ptr [rax+7C4h]
0x18002500e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025015  test    ebp, ebp
0x180025017  js      loc_180025482
0x18002501d  lea     rcx, [rsp+78h+arg_8]; this
0x180025025  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002502a  jmp     loc_1800250F4
0x18002502f  mov     ecx, r14d; cb
0x180025032  mov     edi, r14d
0x180025035  call    cs:__imp_CoTaskMemAlloc
0x18002503b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180025042  lea     r13, stru_1801F8A30
0x180025049  mov     [r15+8], rax
0x18002504d  lea     rbp, stru_1801FC290
0x180025054  test    rcx, rcx
0x180025057  jz      loc_180025136
0x18002505d  cmp     byte ptr [rcx+8], 0
0x180025061  lea     r12, aCmfpropvariant_11; "CMFPropVariant::CreateString"
0x180025068  jz      short loc_180025099
0x18002506a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002506f  mov     ecx, [rax+7C4h]
0x180025075  cmp     ecx, [rax+7C8h]
0x18002507b  jnb     short loc_18002508C
0x18002507d  add     rcx, rcx
0x180025080  mov     [rax+rcx*8], r12
0x180025084  mov     dword ptr [rax+rcx*8+8], 745h
0x18002508c  inc     dword ptr [rax+7C4h]
0x180025092  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180025099  mov     rax, [r15+8]
0x18002509d  test    rax, rax
0x1800250a0  jz      loc_180025183
0x1800250a6  xor     ebp, ebp
0x1800250a8  lea     rcx, [rsp+78h+arg_8]; this
0x1800250b0  mov     [rax], bp
0x1800250b3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800250b8  cmp     si, 1Eh
0x1800250bc  jnz     loc_180024F73
0x1800250c2  mov     rax, [r15+8]
0x1800250c6  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800250cc  shr     r14d, 1
0x1800250cf  mov     r8, rbx; lpMultiByteStr
0x1800250d2  mov     [rsp+78h+cchWideChar], r14d; cchWideChar
0x1800250d7  xor     edx, edx; dwFlags
0x1800250d9  xor     ecx, ecx; CodePage
0x1800250db  mov     [rsp+78h+lpWideCharStr], rax; lpWideCharStr
0x1800250e0  mov     word ptr [r15], 1Fh
0x1800250e6  call    cs:__imp_MultiByteToWideChar
0x1800250ec  test    eax, eax
0x1800250ee  jz      loc_1800252D2
0x1800250f4  mov     eax, ebp
0x1800250f6  add     rsp, 38h
0x1800250fa  pop     r15
0x1800250fc  pop     r14
0x1800250fe  pop     r13
0x180025100  pop     r12
0x180025102  pop     rdi
0x180025103  pop     rsi
0x180025104  pop     rbp
0x180025105  pop     rbx
0x180025106  retn
0x180025107  mov     rax, cs:stru_1801FC290.__vftable
0x18002510e  mov     edx, 7F0h
0x180025113  mov     rcx, rdi
0x180025116  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002511d  mov     rax, [rax+8]
0x180025121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025126  test    eax, eax
0x180025128  jz      short loc_180025165
0x18002512a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025131  jmp     loc_180024FE0
0x180025136  mov     rax, cs:stru_1801FC290.__vftable
0x18002513d  mov     edx, 7F0h
0x180025142  mov     rcx, rbp
0x180025145  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18002514c  mov     rax, [rax+8]
0x180025150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025155  test    eax, eax
0x180025157  jz      short loc_180025174
0x180025159  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025160  jmp     loc_18002505D
0x180025165  mov     rcx, r13
0x180025168  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002516f  jmp     loc_180024FE0
0x180025174  mov     rcx, r13
0x180025177  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002517e  jmp     loc_18002505D
0x180025183  test    rcx, rcx
0x180025186  jz      short loc_1800251B6
0x180025188  cmp     byte ptr [rcx+8], 0
0x18002518c  jnz     loc_1800252A1
0x180025192  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025199  jnb     loc_18002556F
0x18002519f  lea     rcx, [rsp+78h+arg_8]; this
0x1800251a7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800251ac  mov     eax, 8007000Eh
0x1800251b1  jmp     loc_1800250F6
0x1800251b6  mov     rax, cs:stru_1801FC290.__vftable
0x1800251bd  mov     edx, 7F0h
0x1800251c2  mov     rcx, rbp
0x1800251c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x1800251cc  mov     rax, [rax+8]
0x1800251d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251d5  test    eax, eax
0x1800251d7  jnz     short loc_1800251E5
0x1800251d9  mov     rcx, r13
0x1800251dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800251e3  jmp     short loc_180025188
0x1800251e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800251ec  jmp     short loc_180025188
0x1800251ee  lea     r12, aCmfpropvariant_11; "CMFPropVariant::CreateString"
0x1800251f5  mov     r8d, 73Eh; int
0x1800251fb  mov     rdx, r12; char *
0x1800251fe  lea     rcx, [rsp+78h+arg_8]; this
0x180025206  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002520b  mov     r13, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025212  mov     ebp, 80070057h
0x180025217  test    r13, r13
0x18002521a  jnz     short loc_180025254
0x18002521c  mov     rax, cs:stru_1801FC290.__vftable
0x180025223  lea     rdi, stru_1801FC290
0x18002522a  mov     edx, 7F0h
0x18002522f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180025236  mov     rcx, rdi
0x180025239  mov     rax, [rax+8]
0x18002523d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025242  test    eax, eax
0x180025244  jnz     short loc_180025272
0x180025246  lea     r13, stru_1801F8A30
0x18002524d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180025254  cmp     byte ptr [r13+8], 0
0x180025259  jnz     short loc_18002527B
0x18002525b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025262  jb      loc_18002501D
0x180025268  mov     edx, 7Bh ; '{'
0x18002526d  jmp     loc_180024F50
0x180025272  mov     r13, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025279  jmp     short loc_180025254
0x18002527b  mov     rcx, r13; this
0x18002527e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180025283  cmp     [rax+7CCh], ebp
0x180025289  jz      short loc_18002525B
0x18002528b  mov     r9d, ebp; int
0x18002528e  mov     r8d, 73Eh; int
0x180025294  mov     rdx, r12; char *
0x180025297  mov     rcx, rax; this
0x18002529a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002529f  jmp     short loc_18002525B
0x1800252a1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800252a6  cmp     dword ptr [rax+7CCh], 8007000Eh
0x1800252b0  jz      loc_180025192
0x1800252b6  mov     r9d, 8007000Eh; int
0x1800252bc  mov     r8d, 745h; int
0x1800252c2  mov     rdx, r12; char *
0x1800252c5  mov     rcx, rax; this
0x1800252c8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800252cd  jmp     loc_180025192
0x1800252d2  mov     r8d, 759h; int
0x1800252d8  lea     rcx, [rsp+78h+arg_8]; this
0x1800252e0  mov     rdx, r12; char *
0x1800252e3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800252e8  call    cs:__imp_GetLastError
0x1800252ee  mov     ebx, eax
0x1800252f0  test    eax, eax
0x1800252f2  jle     short loc_1800252FD
0x1800252f4  movzx   ebx, ax
0x1800252f7  or      ebx, 80070000h
0x1800252fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025304  test    ebx, ebx
0x180025306  js      loc_18002539A
0x18002530c  test    rcx, rcx
0x18002530f  jnz     short loc_180025349
0x180025311  mov     rax, cs:stru_1801FC290.__vftable
0x180025318  lea     rdi, stru_1801FC290
0x18002531f  mov     edx, 7F0h
0x180025324  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002532b  mov     rcx, rdi
0x18002532e  mov     rax, [rax+8]
0x180025332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025337  test    eax, eax
0x180025339  jnz     loc_180025445
0x18002533f  mov     rcx, r13; this
0x180025342  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180025349  cmp     [rcx+8], bpl
0x18002534d  jnz     loc_180025451
0x180025353  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002535a  jb      short loc_180025383
0x18002535c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025363  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18002536a  mov     edx, 7Eh ; '~'
0x18002536f  mov     dword ptr [rsp+78h+lpWideCharStr], 8000FFFFh
0x180025377  mov     r9, r15
0x18002537a  mov     rcx, [rcx+10h]
  ... truncated ...
```
