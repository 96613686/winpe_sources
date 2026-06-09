# ConvertURLsAndPaths

- ea: `0x180002ef8`
- end: `0x1800035e2`
- name: `ConvertURLsAndPaths`
- size: `1770`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004a00`
- `0x180018220`

## callees

- `0x180002ef8`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18006fbbc`
- `0x1800916b8`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18000300f`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x1800035b3`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18000300f`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x1800035b3`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x180002fbf`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x1800035ab`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x180002fbf`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x1800035ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002f98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003587`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002f98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003587`

## string_xrefs

- `0x180002f12`: `ConvertURLsAndPaths`
- `0x1800032b5`: `ConvertURLsAndPaths`
- `0x180003346`: `ConvertURLsAndPaths`
- `0x1800033df`: `ConvertURLsAndPaths`
- `0x180003472`: `ConvertURLsAndPaths`
- `0x18000351e`: `ConvertURLsAndPaths`

## pseudocode

```c
__int64 __fastcall ConvertURLsAndPaths(int a1, const WCHAR *a2, unsigned __int16 **a3)
{
  __int64 v6; // rcx
  const WCHAR *v7; // rax
  int v8; // ebx
  unsigned __int64 v9; // rdi
  WCHAR *v10; // rax
  unsigned __int16 *v11; // rsi
  HRESULT v12; // eax
  CallStackTracing *v13; // rcx
  CallStackTracing *v15; // rcx
  int v16; // edi
  __int64 v17; // rdx
  CallStackTracing *v18; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  struct CallStackContext *v22; // rax
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  __int64 v25; // rdx
  struct CallStackContext *v26; // rax
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  CallStackTracing *v29; // rcx
  __int64 v30; // rdx
  struct CallStackContext *v31; // rax
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  WCHAR *v34; // rax
  HRESULT v35; // eax
  DWORD pcchUrl; // [rsp+78h] [rbp+48h] BYREF
  SIZE_T cb; // [rsp+88h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&pcchUrl, "ConvertURLsAndPaths", 307);
  if ( !a2 )
  {
    v18 = CallStackTracing::s_wpInstance;
    v16 = -2147467261;
    v8 = -2147467261;
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v18);
      if ( ThreadRelativeContext->m_result != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "ConvertURLsAndPaths", 316, -2147467261);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_22;
    v17 = 30;
LABEL_72:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids, 0, v16);
    goto LABEL_22;
  }
  if ( !a3 )
  {
    v20 = CallStackTracing::s_wpInstance;
    v16 = -2147467261;
    v8 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v20 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v20->m_fEnabled )
    {
      v21 = CallStackTracing::GetThreadRelativeContext(v20);
      if ( v21->m_result != -2147467261 )
        CallStackContext::TraceFailure(v21, "ConvertURLsAndPaths", 317, -2147467261);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_22;
    v17 = 31;
    goto LABEL_72;
  }
  *a3 = 0;
  v6 = 100000;
  v7 = a2;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = v6 == 0 ? 0x80070057 : 0;
  if ( !v6 )
  {
    v13 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v13 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v13->m_fEnabled )
    {
      v22 = CallStackTracing::GetThreadRelativeContext(v13);
      if ( v22->m_result != v8 )
        CallStackContext::TraceFailure(v22, "ConvertURLsAndPaths", 329, v8);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_22;
    v25 = 32;
LABEL_96:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids, 0, v8);
    goto LABEL_22;
  }
  v9 = (-(__int64)(v6 != 0) & (2 * (100000 - v6))) + 16;
  cb = 2 * v9;
  v10 = (WCHAR *)CoTaskMemAlloc(2 * v9);
  v11 = v10;
  if ( !v10 )
  {
    v15 = CallStackTracing::s_wpInstance;
    v16 = -2147024882;
    v8 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v15 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v15->m_fEnabled )
    {
      v23 = CallStackTracing::GetThreadRelativeContext(v15);
      if ( v23->m_result != -2147024882 )
        CallStackContext::TraceFailure(v23, "ConvertURLsAndPaths", 338, -2147024882);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_22;
    v17 = 33;
    goto LABEL_72;
  }
  pcchUrl = v9;
  if ( a1 )
    v12 = PathCreateFromUrlW(a2, v10, &pcchUrl, 0);
  else
    v12 = UrlCreateFromPathW(a2, v10, &pcchUrl, 0);
  v8 = v12;
  if ( v12 >= 0 )
  {
LABEL_16:
    if ( pcchUrl > v9 )
    {
      v29 = CallStackTracing::s_wpInstance;
      v8 = -2147418113;
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
        v31 = CallStackTracing::GetThreadRelativeContext(v29);
        if ( v31->m_result != -2147418113 )
          CallStackContext::TraceFailure(v31, "ConvertURLsAndPaths", 398, -2147418113);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v30 = 37;
LABEL_91:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids, 0, v8);
      }
    }
    else
    {
      if ( v8 != 1 )
      {
LABEL_18:
        *a3 = v11;
        goto LABEL_22;
      }
      v8 = StringCchCopyW(v11, v9, a2);
      if ( v8 >= 0 )
      {
        v8 = 1;
        goto LABEL_18;
      }
      v32 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v32 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v32 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v32->m_fEnabled )
      {
        v33 = CallStackTracing::GetThreadRelativeContext(v32);
        if ( v33->m_result != v8 )
          CallStackContext::TraceFailure(v33, "ConvertURLsAndPaths", 405, v8);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v30 = 38;
        goto LABEL_91;
      }
    }
    if ( !v11 )
      goto LABEL_22;
    goto LABEL_14;
  }
  if ( v12 != -2147467261 )
  {
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids, 0, v12);
LABEL_14:
    CoTaskMemFree(v11);
    goto LABEL_22;
  }
  CoTaskMemFree(v11);
  v9 = pcchUrl;
  v8 = ULongLongMult(pcchUrl, 2u, &cb);
  if ( v8 < 0 )
  {
    v24 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v24 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v24->m_fEnabled )
    {
      v26 = CallStackTracing::GetThreadRelativeContext(v24);
      if ( v26->m_result != v8 )
        CallStackContext::TraceFailure(v26, "ConvertURLsAndPaths", 372, v8);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_22;
    v25 = 35;
    goto LABEL_96;
  }
  v34 = (WCHAR *)CoTaskMemAlloc(cb);
  v11 = v34;
  if ( v34 )
  {
    if ( a1 )
      v35 = PathCreateFromUrlW(a2, v34, &pcchUrl, 0);
    else
      v35 = UrlCreateFromPathW(a2, v34, &pcchUrl, 0);
    v8 = v35;
    goto LABEL_16;
  }
  v27 = CallStackTracing::s_wpInstance;
  v16 = -2147024882;
  v8 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v27 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v27 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v27->m_fEnabled )
  {
    v28 = CallStackTracing::GetThreadRelativeContext(v27);
    if ( v28->m_result != -2147024882 )
      CallStackContext::TraceFailure(v28, "ConvertURLsAndPaths", 375, -2147024882);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v17 = 36;
    goto LABEL_72;
  }
LABEL_22:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&pcchUrl);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002ef8  mov     [rsp-38h+arg_0], rbx
0x180002efd  push    rbp
0x180002efe  push    rsi
0x180002eff  push    rdi
0x180002f00  push    r12
0x180002f02  push    r13
0x180002f04  push    r14
0x180002f06  push    r15
0x180002f08  mov     rbp, rsp
0x180002f0b  sub     rsp, 30h
0x180002f0f  mov     r15, r8
0x180002f12  lea     rsi, aConverturlsand; "ConvertURLsAndPaths"
0x180002f19  mov     r14, rdx
0x180002f1c  mov     r12d, ecx
0x180002f1f  mov     rdx, rsi; char *
0x180002f22  lea     rcx, [rbp+pcchUrl]; this
0x180002f26  mov     r8d, 133h; int
0x180002f2c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180002f31  xor     r13d, r13d
0x180002f34  test    r14, r14
0x180002f37  jz      loc_1800030DB
0x180002f3d  test    r15, r15
0x180002f40  jz      loc_1800031E6
0x180002f46  mov     edx, 186A0h
0x180002f4b  mov     [r15], r13
0x180002f4e  mov     ecx, edx
0x180002f50  mov     rax, r14
0x180002f53  cmp     [rax], r13w
0x180002f57  jz      short loc_180002F63
0x180002f59  add     rax, 2
0x180002f5d  sub     rcx, 1
0x180002f61  jnz     short loc_180002F53
0x180002f63  mov     rax, rcx
0x180002f66  neg     rax
0x180002f69  sbb     ebx, ebx
0x180002f6b  not     ebx
0x180002f6d  and     ebx, 80070057h
0x180002f73  test    rcx, rcx
0x180002f76  jz      loc_180003031
0x180002f7c  sub     rdx, rcx
0x180002f7f  neg     rcx
0x180002f82  sbb     rax, rax
0x180002f85  lea     rdi, [rdx+rdx]
0x180002f89  and     rdi, rax
0x180002f8c  add     rdi, 10h
0x180002f90  lea     rcx, [rdi+rdi]; cb
0x180002f94  mov     [rbp+cb], rcx
0x180002f98  call    cs:__imp_CoTaskMemAlloc
0x180002f9e  mov     rsi, rax
0x180002fa1  test    rax, rax
0x180002fa4  jz      loc_180003074
0x180002faa  xor     r9d, r9d; dwFlags
0x180002fad  mov     [rbp+pcchUrl], edi
0x180002fb0  lea     r8, [rbp+pcchUrl]; pcchPath
0x180002fb4  mov     rdx, rax; pszPath
0x180002fb7  mov     rcx, r14; pszUrl
0x180002fba  test    r12d, r12d
0x180002fbd  jnz     short loc_18000300F
0x180002fbf  call    cs:__imp_UrlCreateFromPathW
0x180002fc5  mov     ebx, eax
0x180002fc7  test    eax, eax
0x180002fc9  jns     short loc_180003017
0x180002fcb  mov     edi, 80004003h
0x180002fd0  cmp     eax, edi
0x180002fd2  jz      loc_18000355D
0x180002fd8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180002fdf  jb      short loc_180003004
0x180002fe1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fe8  lea     r8, WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids
0x180002fef  mov     edx, 22h ; '"'
0x180002ff4  mov     [rsp+30h+var_10], eax
0x180002ff8  xor     r9d, r9d
0x180002ffb  mov     rcx, [rcx+10h]
0x180002fff  call    WPP_SF_qD
0x180003004  mov     rcx, rsi; pv
0x180003007  call    cs:__imp_CoTaskMemFree
0x18000300d  jmp     short loc_180003054
0x18000300f  call    cs:__imp_PathCreateFromUrlW
0x180003015  jmp     short loc_180002FC5
0x180003017  mov     eax, [rbp+pcchUrl]
0x18000301a  cmp     rax, rdi
0x18000301d  ja      loc_1800033F6
0x180003023  cmp     ebx, 1
0x180003026  jz      loc_1800035C0
0x18000302c  mov     [r15], rsi
0x18000302f  jmp     short loc_180003054
0x180003031  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180003038  test    rcx, rcx
0x18000303b  jz      short loc_1800030A8
0x18000303d  cmp     [rcx+8], r13b
0x180003041  jnz     loc_180003277
0x180003047  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000304e  jnb     loc_180003535
0x180003054  lea     rcx, [rbp+pcchUrl]; this
0x180003058  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000305d  mov     eax, ebx
0x18000305f  mov     rbx, [rsp+30h+arg_0]
0x180003064  add     rsp, 30h
0x180003068  pop     r15
0x18000306a  pop     r14
0x18000306c  pop     r13
0x18000306e  pop     r12
0x180003070  pop     rdi
0x180003071  pop     rsi
0x180003072  pop     rbp
0x180003073  retn
0x180003074  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000307b  mov     edi, 8007000Eh
0x180003080  mov     ebx, edi
0x180003082  test    rcx, rcx
0x180003085  jz      loc_180003122
0x18000308b  cmp     [rcx+8], r13b
0x18000308f  jnz     loc_1800032A1
0x180003095  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000309c  jb      short loc_180003054
0x18000309e  mov     edx, 21h ; '!'
0x1800030a3  jmp     loc_1800033BD
0x1800030a8  mov     rax, cs:stru_1801FC290.__vftable
0x1800030af  lea     rcx, stru_1801FC290
0x1800030b6  mov     edx, 7F0h
0x1800030bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800030c2  mov     rax, [rax+8]
0x1800030c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030cb  test    eax, eax
0x1800030cd  jz      short loc_18000310F
0x1800030cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800030d6  jmp     loc_18000303D
0x1800030db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800030e2  mov     edi, 80004003h
0x1800030e7  mov     ebx, edi
0x1800030e9  test    rcx, rcx
0x1800030ec  jz      short loc_180003168
0x1800030ee  cmp     [rcx+8], r13b
0x1800030f2  jnz     loc_1800031BC
0x1800030f8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800030ff  jb      loc_180003054
0x180003105  mov     edx, 1Eh
0x18000310a  jmp     loc_1800033BD
0x18000310f  lea     rcx, stru_1801F8A30
0x180003116  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000311d  jmp     loc_18000303D
0x180003122  mov     rax, cs:stru_1801FC290.__vftable
0x180003129  lea     rcx, stru_1801FC290
0x180003130  mov     edx, 7F0h
0x180003135  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000313c  mov     rax, [rax+8]
0x180003140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003145  test    eax, eax
0x180003147  jnz     short loc_18000315C
0x180003149  lea     rcx, stru_1801F8A30
0x180003150  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180003157  jmp     loc_18000308B
0x18000315c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180003163  jmp     loc_18000308B
0x180003168  mov     rax, cs:stru_1801FC290.__vftable
0x18000316f  lea     rcx, stru_1801FC290
0x180003176  mov     edx, 7F0h
0x18000317b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180003182  mov     rax, [rax+8]
0x180003186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000318b  test    eax, eax
0x18000318d  jnz     short loc_1800031A2
0x18000318f  lea     rcx, stru_1801F8A30
0x180003196  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000319d  jmp     loc_1800030EE
0x1800031a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800031a9  jmp     loc_1800030EE
0x1800031ae  test    rsi, rsi
0x1800031b1  jz      loc_180003054
0x1800031b7  jmp     loc_180003004
0x1800031bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800031c1  cmp     [rax+7CCh], edi
0x1800031c7  jz      loc_1800030F8
0x1800031cd  mov     r9d, edi; int
0x1800031d0  mov     r8d, 13Ch; int
0x1800031d6  mov     rdx, rsi; char *
0x1800031d9  mov     rcx, rax; this
0x1800031dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800031e1  jmp     loc_1800030F8
0x1800031e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800031ed  mov     edi, 80004003h
0x1800031f2  mov     ebx, edi
0x1800031f4  test    rcx, rcx
0x1800031f7  jnz     short loc_18000322E
0x1800031f9  mov     rax, cs:stru_1801FC290.__vftable
0x180003200  lea     rcx, stru_1801FC290
0x180003207  mov     edx, 7F0h
0x18000320c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180003213  mov     rax, [rax+8]
0x180003217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000321c  test    eax, eax
0x18000321e  jnz     short loc_18000324B
0x180003220  lea     rcx, stru_1801F8A30; this
0x180003227  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000322e  cmp     [rcx+8], r13b
0x180003232  jnz     short loc_180003254
0x180003234  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000323b  jb      loc_180003054
0x180003241  mov     edx, 1Fh
0x180003246  jmp     loc_1800033BD
0x18000324b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180003252  jmp     short loc_18000322E
0x180003254  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180003259  cmp     [rax+7CCh], edi
0x18000325f  jz      short loc_180003234
0x180003261  mov     r9d, edi; int
0x180003264  mov     r8d, 13Dh; int
0x18000326a  mov     rdx, rsi; char *
0x18000326d  mov     rcx, rax; this
0x180003270  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180003275  jmp     short loc_180003234
0x180003277  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000327c  cmp     [rax+7CCh], ebx
0x180003282  jz      loc_180003047
0x180003288  mov     r9d, ebx; int
0x18000328b  mov     r8d, 149h; int
0x180003291  mov     rdx, rsi; char *
0x180003294  mov     rcx, rax; this
0x180003297  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000329c  jmp     loc_180003047
0x1800032a1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800032a6  cmp     [rax+7CCh], edi
0x1800032ac  jz      loc_180003095
0x1800032b2  mov     r9d, edi; int
0x1800032b5  lea     rdx, aConverturlsand; "ConvertURLsAndPaths"
0x1800032bc  mov     r8d, 152h; int
0x1800032c2  mov     rcx, rax; this
0x1800032c5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800032ca  jmp     loc_180003095
0x1800032cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800032d6  test    rcx, rcx
0x1800032d9  jnz     short loc_180003310
0x1800032db  mov     rax, cs:stru_1801FC290.__vftable
0x1800032e2  lea     rcx, stru_1801FC290
0x1800032e9  mov     edx, 7F0h
0x1800032ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800032f5  mov     rax, [rax+8]
0x1800032f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032fe  test    eax, eax
0x180003300  jnz     short loc_18000332D
0x180003302  lea     rcx, stru_1801F8A30; this
0x180003309  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180003310  cmp     [rcx+8], r13b
0x180003314  jnz     short loc_180003336
0x180003316  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000331d  jb      loc_180003054
0x180003323  mov     edx, 23h ; '#'
0x180003328  jmp     loc_18000353A
0x18000332d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180003334  jmp     short loc_180003310
0x180003336  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000333b  cmp     [rax+7CCh], ebx
0x180003341  jz      short loc_180003316
0x180003343  mov     r9d, ebx; int
0x180003346  lea     rdx, aConverturlsand; "ConvertURLsAndPaths"
0x18000334d  mov     r8d, 174h; int
0x180003353  mov     rcx, rax; this
0x180003356  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000335b  jmp     short loc_180003316
0x18000335d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180003364  mov     edi, 8007000Eh
0x180003369  mov     ebx, edi
0x18000336b  test    rcx, rcx
0x18000336e  jnz     short loc_1800033A5
0x180003370  mov     rax, cs:stru_1801FC290.__vftable
0x180003377  lea     rcx, stru_1801FC290
0x18000337e  mov     edx, 7F0h
0x180003383  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000338a  mov     rax, [rax+8]
0x18000338e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003393  test    eax, eax
0x180003395  jnz     short loc_1800033C6
0x180003397  lea     rcx, stru_1801F8A30; this
0x18000339e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800033a5  cmp     [rcx+8], r13b
0x1800033a9  jnz     short loc_1800033CF
0x1800033ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800033b2  jb      loc_180003054
0x1800033b8  mov     edx, 24h ; '$'
0x1800033bd  mov     [rsp+30h+var_10], edi
0x1800033c1  jmp     loc_18000353E
0x1800033c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800033cd  jmp     short loc_1800033A5
0x1800033cf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800033d4  cmp     [rax+7CCh], edi
0x1800033da  jz      short loc_1800033AB
0x1800033dc  mov     r9d, edi; int
0x1800033df  lea     rdx, aConverturlsand; "ConvertURLsAndPaths"
0x1800033e6  mov     r8d, 177h; int
0x1800033ec  mov     rcx, rax; this
0x1800033ef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800033f4  jmp     short loc_1800033AB
0x1800033f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800033fd  mov     ebx, 8000FFFFh
0x180003402  test    rcx, rcx
0x180003405  jnz     short loc_18000343C
0x180003407  mov     rax, cs:stru_1801FC290.__vftable
0x18000340e  lea     rcx, stru_1801FC290
0x180003415  mov     edx, 7F0h
0x18000341a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
