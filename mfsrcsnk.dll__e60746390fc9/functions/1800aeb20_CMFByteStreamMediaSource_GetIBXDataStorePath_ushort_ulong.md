# CMFByteStreamMediaSource::GetIBXDataStorePath(ushort *,ulong)

- ea: `0x1800aeb20`
- end: `0x1800aedf0`
- name: `?GetIBXDataStorePath@CMFByteStreamMediaSource@@AEAAJPEAGK@Z`
- size: `720`
- prototype: `int(CMFByteStreamMediaSource *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180103ad4`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x1800aeb20`
- `0x1801092cc`
- `0x18013859c`
- `0x180173010`

## import_xrefs

- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800aecdf`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800aecdf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aeb84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aec54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aed0f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aeb84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aec54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aed0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aedc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aedc5`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800aeb68`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800aeb68`

## string_xrefs

- `0x1800aeb3e`: `CMFByteStreamMediaSource::GetIBXDataStorePath`
- `0x1800aebdb`: `CMFByteStreamMediaSource::GetIBXDataStorePath`
- `0x1800aecab`: `CMFByteStreamMediaSource::GetIBXDataStorePath`
- `0x1800aed66`: `CMFByteStreamMediaSource::GetIBXDataStorePath`

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
            v16 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      if ( (unsigned __int8)byte_1801B110B >= 4u )
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
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v6 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800aeb20  mov     rax, rsp
0x1800aeb23  mov     [rax+8], rbx
0x1800aeb27  mov     [rax+10h], rsi
0x1800aeb2b  push    rdi
0x1800aeb2c  sub     rsp, 30h
0x1800aeb30  mov     rdi, rdx
0x1800aeb33  mov     qword ptr [rax+20h], 0
0x1800aeb3b  mov     rsi, rcx
0x1800aeb3e  lea     rdx, aCmfbytestreamm_9; "CMFByteStreamMediaSource::GetIBXDataSto"...
0x1800aeb45  lea     rcx, [rax+18h]; this
0x1800aeb49  mov     r8d, 1520h; int
0x1800aeb4f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800aeb54  lea     r9, [rsp+38h+ppszPath]; ppszPath
0x1800aeb59  xor     r8d, r8d; hToken
0x1800aeb5c  mov     edx, 14000h; dwFlags
0x1800aeb61  lea     rcx, FOLDERID_LocalAppData; rfid
0x1800aeb68  call    cs:__imp_SHGetKnownFolderPath
0x1800aeb6e  mov     ebx, eax
0x1800aeb70  test    eax, eax
0x1800aeb72  jns     loc_1800AEC25
0x1800aeb78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aeb7f  test    rcx, rcx
0x1800aeb82  jnz     short loc_1800AEBC5
0x1800aeb84  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800aeb8a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aeb91  mov     rcx, rax
0x1800aeb94  test    rax, rax
0x1800aeb97  jz      short loc_1800AEBB7
0x1800aeb99  mov     rax, [rax]
0x1800aeb9c  mov     edx, 7F0h
0x1800aeba1  mov     rax, [rax+8]
0x1800aeba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aebaa  test    eax, eax
0x1800aebac  jz      short loc_1800AEBB7
0x1800aebae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aebb5  jmp     short loc_1800AEBC5
0x1800aebb7  lea     rcx, qword_1801B07E0; this
0x1800aebbe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aebc5  cmp     byte ptr [rcx+8], 0
0x1800aebc9  jz      short loc_1800AEBF0
0x1800aebcb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aebd0  cmp     [rax+7CCh], ebx
0x1800aebd6  jz      short loc_1800AEBF0
0x1800aebd8  mov     r9d, ebx; int
0x1800aebdb  lea     rdx, aCmfbytestreamm_9; "CMFByteStreamMediaSource::GetIBXDataSto"...
0x1800aebe2  mov     r8d, 1520h; int
0x1800aebe8  mov     rcx, rax; this
0x1800aebeb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aebf0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800aebf7  jb      loc_1800AEDC0
0x1800aebfd  mov     edx, 216h
0x1800aec02  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aec09  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800aec10  mov     r9, rsi
0x1800aec13  mov     dword ptr [rsp+38h+var_18], ebx
0x1800aec17  mov     rcx, [rcx+10h]
0x1800aec1b  call    WPP_SF_qD
0x1800aec20  jmp     loc_1800AEDC0
0x1800aec25  mov     r9, [rsp+38h+ppszPath]
0x1800aec2a  lea     r8, aSMicrosoftMf; "%s\\Microsoft\\MF"
0x1800aec31  mov     edx, 104h; unsigned __int64
0x1800aec36  mov     rcx, rdi; unsigned __int16 *
0x1800aec39  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800aec3e  mov     ebx, eax
0x1800aec40  test    eax, eax
0x1800aec42  jns     loc_1800AECD7
0x1800aec48  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aec4f  test    rcx, rcx
0x1800aec52  jnz     short loc_1800AEC95
0x1800aec54  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800aec5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aec61  mov     rcx, rax
0x1800aec64  test    rax, rax
0x1800aec67  jz      short loc_1800AEC87
0x1800aec69  mov     rax, [rax]
0x1800aec6c  mov     edx, 7F0h
0x1800aec71  mov     rax, [rax+8]
0x1800aec75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aec7a  test    eax, eax
0x1800aec7c  jz      short loc_1800AEC87
0x1800aec7e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aec85  jmp     short loc_1800AEC95
0x1800aec87  lea     rcx, qword_1801B07E0; this
0x1800aec8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aec95  cmp     byte ptr [rcx+8], 0
0x1800aec99  jz      short loc_1800AECC0
0x1800aec9b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aeca0  cmp     [rax+7CCh], ebx
0x1800aeca6  jz      short loc_1800AECC0
0x1800aeca8  mov     r9d, ebx; int
0x1800aecab  lea     rdx, aCmfbytestreamm_9; "CMFByteStreamMediaSource::GetIBXDataSto"...
0x1800aecb2  mov     r8d, 1521h; int
0x1800aecb8  mov     rcx, rax; this
0x1800aecbb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aecc0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800aecc7  jb      loc_1800AEDC0
0x1800aeccd  mov     edx, 217h
0x1800aecd2  jmp     loc_1800AEC02
0x1800aecd7  xor     r8d, r8d; psa
0x1800aecda  mov     rdx, rdi; pszPath
0x1800aecdd  xor     ecx, ecx; hwnd
0x1800aecdf  call    cs:__imp_SHCreateDirectoryExW
0x1800aece5  mov     ebx, eax
0x1800aece7  cmp     eax, 50h ; 'P'
0x1800aecea  jz      loc_1800AED8E
0x1800aecf0  cmp     eax, 0B7h
0x1800aecf5  jz      loc_1800AED8E
0x1800aecfb  test    eax, eax
0x1800aecfd  jns     loc_1800AED90
0x1800aed03  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aed0a  test    rcx, rcx
0x1800aed0d  jnz     short loc_1800AED50
0x1800aed0f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800aed15  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aed1c  mov     rcx, rax
0x1800aed1f  test    rax, rax
0x1800aed22  jz      short loc_1800AED42
0x1800aed24  mov     rax, [rax]
0x1800aed27  mov     edx, 7F0h
0x1800aed2c  mov     rax, [rax+8]
0x1800aed30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aed35  test    eax, eax
0x1800aed37  jz      short loc_1800AED42
0x1800aed39  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aed40  jmp     short loc_1800AED50
0x1800aed42  lea     rcx, qword_1801B07E0; this
0x1800aed49  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aed50  cmp     byte ptr [rcx+8], 0
0x1800aed54  jz      short loc_1800AED7B
0x1800aed56  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aed5b  cmp     [rax+7CCh], ebx
0x1800aed61  jz      short loc_1800AED7B
0x1800aed63  mov     r9d, ebx; int
0x1800aed66  lea     rdx, aCmfbytestreamm_9; "CMFByteStreamMediaSource::GetIBXDataSto"...
0x1800aed6d  mov     r8d, 1527h; int
0x1800aed73  mov     rcx, rax; this
0x1800aed76  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aed7b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800aed82  jb      short loc_1800AEDC0
0x1800aed84  mov     edx, 218h
0x1800aed89  jmp     loc_1800AEC02
0x1800aed8e  xor     ebx, ebx
0x1800aed90  cmp     cs:byte_1801B110B, 4
0x1800aed97  jb      short loc_1800AEDC0
0x1800aed99  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aeda0  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800aeda7  mov     edx, 219h
0x1800aedac  mov     [rsp+38h+var_18], rdi
0x1800aedb1  mov     r9, rsi
0x1800aedb4  mov     rcx, [rcx+88h]
0x1800aedbb  call    WPP_SF_qS
0x1800aedc0  mov     rcx, [rsp+38h+ppszPath]; pv
0x1800aedc5  call    cs:__imp_CoTaskMemFree
0x1800aedcb  lea     rcx, [rsp+38h+arg_10]; this
0x1800aedd0  mov     [rsp+38h+ppszPath], 0
0x1800aedd9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800aedde  mov     rsi, [rsp+38h+arg_8]
0x1800aede3  mov     eax, ebx
0x1800aede5  mov     rbx, [rsp+38h+arg_0]
0x1800aedea  add     rsp, 30h
0x1800aedee  pop     rdi
0x1800aedef  retn
```
