# CMFByteStreamMediaSource::GetIBXDataStorePath(ushort *,ulong)

- ea: `0x1800b3fcc`
- end: `0x1800b42c1`
- name: `?GetIBXDataStorePath@CMFByteStreamMediaSource@@AEAAJPEAGK@Z`
- size: `757`
- prototype: `int(CMFByteStreamMediaSource *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18010accc`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x1800b3fcc`
- `0x1801107b0`
- `0x18013fe74`
- `0x18017c010`

## import_xrefs

- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800b419d`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800b419d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4036`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b410c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b41d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b4036`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b410c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b41d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b428f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b428f`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800b4014`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800b4014`

## string_xrefs

- `0x1800b3fea`: `CMFByteStreamMediaSource::GetIBXDataStorePath`
- `0x1800b4093`: `CMFByteStreamMediaSource::GetIBXDataStorePath`
- `0x1800b4169`: `CMFByteStreamMediaSource::GetIBXDataStorePath`
- `0x1800b4230`: `CMFByteStreamMediaSource::GetIBXDataStorePath`

## pseudocode

```c
__int64 __fastcall CMFByteStreamMediaSource::GetIBXDataStorePath(CMFByteStreamMediaSource *this, unsigned __int16 *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  wchar_t *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  int v14; // eax
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v20; // [rsp+50h] [rbp+18h] BYREF
  PWSTR ppszPath; // [rsp+58h] [rbp+20h] BYREF

  ppszPath = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v20,
    "CMFByteStreamMediaSource::GetIBXDataStorePath",
    5408);
  v5 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0x14000u, 0, &ppszPath);
  if ( v5 >= 0 )
  {
    v5 = StringCchPrintfW(a2, 0x104u, L"%s\\Microsoft\\MF", ppszPath);
    if ( v5 >= 0 )
    {
      v14 = SHCreateDirectoryExW(0, a2, 0);
      v5 = v14;
      if ( v14 == 80 || v14 == 183 )
      {
        v5 = 0;
      }
      else if ( v14 < 0 )
      {
        v16 = (wchar_t *)CallStackTracing::s_wpInstance;
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CMFByteStreamMediaSource::GetIBXDataStorePath",
              5415,
              v5);
        }
        if ( g_wppLevels )
        {
          v9 = 536;
          goto LABEL_12;
        }
        goto LABEL_40;
      }
      if ( (unsigned __int8)byte_1801BA10B >= 4u )
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          537,
          (unsigned int)&WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
          (_DWORD)this,
          (__int64)a2);
      goto LABEL_40;
    }
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
        CallStackContext::TraceFailure(v13, "CMFByteStreamMediaSource::GetIBXDataStorePath", 5409, v5);
    }
    if ( g_wppLevels )
    {
      v9 = 535;
      goto LABEL_12;
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
        CallStackContext::TraceFailure(v8, "CMFByteStreamMediaSource::GetIBXDataStorePath", 5408, v5);
    }
    if ( g_wppLevels )
    {
      v9 = 534;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, this, v5);
    }
  }
LABEL_40:
  CoTaskMemFree(ppszPath);
  ppszPath = 0;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v20);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800b3fcc  mov     rax, rsp
0x1800b3fcf  mov     [rax+8], rbx
0x1800b3fd3  mov     [rax+10h], rsi
0x1800b3fd7  push    rdi
0x1800b3fd8  sub     rsp, 30h
0x1800b3fdc  mov     rdi, rdx
0x1800b3fdf  mov     qword ptr [rax+20h], 0
0x1800b3fe7  mov     rsi, rcx
0x1800b3fea  lea     rdx, aCmfbytestreamm_9; "CMFByteStreamMediaSource::GetIBXDataSto"...
0x1800b3ff1  lea     rcx, [rax+18h]; this
0x1800b3ff5  mov     r8d, 1520h; int
0x1800b3ffb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b4000  lea     r9, [rsp+38h+ppszPath]; ppszPath
0x1800b4005  xor     r8d, r8d; hToken
0x1800b4008  mov     edx, 14000h; dwFlags
0x1800b400d  lea     rcx, FOLDERID_LocalAppData; rfid
0x1800b4014  call    cs:__imp_SHGetKnownFolderPath
0x1800b401b  nop     dword ptr [rax+rax+00h]
0x1800b4020  mov     ebx, eax
0x1800b4022  test    eax, eax
0x1800b4024  jns     loc_1800B40DD
0x1800b402a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4031  test    rcx, rcx
0x1800b4034  jnz     short loc_1800B407D
0x1800b4036  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b403d  nop     dword ptr [rax+rax+00h]
0x1800b4042  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4049  mov     rcx, rax
0x1800b404c  test    rax, rax
0x1800b404f  jz      short loc_1800B406F
0x1800b4051  mov     rax, [rax]
0x1800b4054  mov     edx, 7F0h
0x1800b4059  mov     rax, [rax+8]
0x1800b405d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4062  test    eax, eax
0x1800b4064  jz      short loc_1800B406F
0x1800b4066  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b406d  jmp     short loc_1800B407D
0x1800b406f  lea     rcx, qword_1801B97E0; this
0x1800b4076  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b407d  cmp     byte ptr [rcx+8], 0
0x1800b4081  jz      short loc_1800B40A8
0x1800b4083  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4088  cmp     [rax+7CCh], ebx
0x1800b408e  jz      short loc_1800B40A8
0x1800b4090  mov     r9d, ebx; int
0x1800b4093  lea     rdx, aCmfbytestreamm_9; "CMFByteStreamMediaSource::GetIBXDataSto"...
0x1800b409a  mov     r8d, 1520h; int
0x1800b40a0  mov     rcx, rax; this
0x1800b40a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b40a8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b40af  jb      loc_1800B428A
0x1800b40b5  mov     edx, 216h
0x1800b40ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b40c1  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800b40c8  mov     r9, rsi
0x1800b40cb  mov     dword ptr [rsp+38h+var_18], ebx
0x1800b40cf  mov     rcx, [rcx+10h]
0x1800b40d3  call    WPP_SF_qD
0x1800b40d8  jmp     loc_1800B428A
0x1800b40dd  mov     r9, [rsp+38h+ppszPath]
0x1800b40e2  lea     r8, aSMicrosoftMf; "%s\\Microsoft\\MF"
0x1800b40e9  mov     edx, 104h; unsigned __int64
0x1800b40ee  mov     rcx, rdi; unsigned __int16 *
0x1800b40f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b40f6  mov     ebx, eax
0x1800b40f8  test    eax, eax
0x1800b40fa  jns     loc_1800B4195
0x1800b4100  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4107  test    rcx, rcx
0x1800b410a  jnz     short loc_1800B4153
0x1800b410c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b4113  nop     dword ptr [rax+rax+00h]
0x1800b4118  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b411f  mov     rcx, rax
0x1800b4122  test    rax, rax
0x1800b4125  jz      short loc_1800B4145
0x1800b4127  mov     rax, [rax]
0x1800b412a  mov     edx, 7F0h
0x1800b412f  mov     rax, [rax+8]
0x1800b4133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4138  test    eax, eax
0x1800b413a  jz      short loc_1800B4145
0x1800b413c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4143  jmp     short loc_1800B4153
0x1800b4145  lea     rcx, qword_1801B97E0; this
0x1800b414c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4153  cmp     byte ptr [rcx+8], 0
0x1800b4157  jz      short loc_1800B417E
0x1800b4159  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b415e  cmp     [rax+7CCh], ebx
0x1800b4164  jz      short loc_1800B417E
0x1800b4166  mov     r9d, ebx; int
0x1800b4169  lea     rdx, aCmfbytestreamm_9; "CMFByteStreamMediaSource::GetIBXDataSto"...
0x1800b4170  mov     r8d, 1521h; int
0x1800b4176  mov     rcx, rax; this
0x1800b4179  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b417e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b4185  jb      loc_1800B428A
0x1800b418b  mov     edx, 217h
0x1800b4190  jmp     loc_1800B40BA
0x1800b4195  xor     r8d, r8d; psa
0x1800b4198  mov     rdx, rdi; pszPath
0x1800b419b  xor     ecx, ecx; hwnd
0x1800b419d  call    cs:__imp_SHCreateDirectoryExW
0x1800b41a4  nop     dword ptr [rax+rax+00h]
0x1800b41a9  mov     ebx, eax
0x1800b41ab  cmp     eax, 50h ; 'P'
0x1800b41ae  jz      loc_1800B4258
0x1800b41b4  cmp     eax, 0B7h
0x1800b41b9  jz      loc_1800B4258
0x1800b41bf  test    eax, eax
0x1800b41c1  jns     loc_1800B425A
0x1800b41c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b41ce  test    rcx, rcx
0x1800b41d1  jnz     short loc_1800B421A
0x1800b41d3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b41da  nop     dword ptr [rax+rax+00h]
0x1800b41df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b41e6  mov     rcx, rax
0x1800b41e9  test    rax, rax
0x1800b41ec  jz      short loc_1800B420C
0x1800b41ee  mov     rax, [rax]
0x1800b41f1  mov     edx, 7F0h
0x1800b41f6  mov     rax, [rax+8]
0x1800b41fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b41ff  test    eax, eax
0x1800b4201  jz      short loc_1800B420C
0x1800b4203  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b420a  jmp     short loc_1800B421A
0x1800b420c  lea     rcx, qword_1801B97E0; this
0x1800b4213  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b421a  cmp     byte ptr [rcx+8], 0
0x1800b421e  jz      short loc_1800B4245
0x1800b4220  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4225  cmp     [rax+7CCh], ebx
0x1800b422b  jz      short loc_1800B4245
0x1800b422d  mov     r9d, ebx; int
0x1800b4230  lea     rdx, aCmfbytestreamm_9; "CMFByteStreamMediaSource::GetIBXDataSto"...
0x1800b4237  mov     r8d, 1527h; int
0x1800b423d  mov     rcx, rax; this
0x1800b4240  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b4245  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b424c  jb      short loc_1800B428A
0x1800b424e  mov     edx, 218h
0x1800b4253  jmp     loc_1800B40BA
0x1800b4258  xor     ebx, ebx
0x1800b425a  cmp     cs:byte_1801BA10B, 4
0x1800b4261  jb      short loc_1800B428A
0x1800b4263  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b426a  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800b4271  mov     edx, 219h
0x1800b4276  mov     [rsp+38h+var_18], rdi
0x1800b427b  mov     r9, rsi
0x1800b427e  mov     rcx, [rcx+88h]
0x1800b4285  call    WPP_SF_qS
0x1800b428a  mov     rcx, [rsp+38h+ppszPath]; pv
0x1800b428f  call    cs:__imp_CoTaskMemFree
0x1800b4296  nop     dword ptr [rax+rax+00h]
0x1800b429b  lea     rcx, [rsp+38h+arg_10]; this
0x1800b42a0  mov     [rsp+38h+ppszPath], 0
0x1800b42a9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b42ae  mov     rsi, [rsp+38h+arg_8]
0x1800b42b3  mov     eax, ebx
0x1800b42b5  mov     rbx, [rsp+38h+arg_0]
0x1800b42ba  add     rsp, 30h
0x1800b42be  pop     rdi
0x1800b42bf  retn
```
