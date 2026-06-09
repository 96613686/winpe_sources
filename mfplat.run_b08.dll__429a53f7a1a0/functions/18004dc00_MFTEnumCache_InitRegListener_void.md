# MFTEnumCache::InitRegListener(void)

- ea: `0x18004dc00`
- end: `0x18004e283`
- name: `?InitRegListener@MFTEnumCache@@QEAAJXZ`
- size: `1667`
- prototype: `__int64 __fastcall(MFTEnumCache *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004d6f0`
- `0x18004db40`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x18004dc00`
- `0x18004e368`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004dcb8`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004dcb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004dddd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004debd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004dddd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004debd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dc6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dd28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dc6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dd28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dd02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dd4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dd02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dd4f`
- `RTWorkQ!RtwqPutWaitingWorkItem` at `0x18004dd1d`
- `RTWorkQ!RtwqPutWaitingWorkItem` at `0x18004dd1d`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x18004dce1`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x18004dce1`

## string_xrefs

- `0x18004dc35`: `MFTEnumCache::InitRegListener`
- `0x18004e01e`: `MFTEnumCache::InitRegListener`
- `0x18004e0c8`: `MFTEnumCache::InitRegListener`
- `0x18004e0f6`: `MFTEnumCache::InitRegListener`
- `0x18004e124`: `MFTEnumCache::InitRegListener`
- `0x18004e1ad`: `MFTEnumCache::InitRegListener`
- `0x18004e23e`: `MFTEnumCache::InitRegListener`
- `0x18004e269`: `MFTEnumCache::InitRegListener`

## pseudocode

```c
__int64 __fastcall MFTEnumCache::InitRegListener(MFTEnumCache *this)
{
  CallStackTracing *v2; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 m_dwDepth; // rcx
  __int64 v5; // rcx
  int v6; // eax
  LSTATUS v7; // eax
  int v8; // ebx
  CallStackTracing *v10; // rcx
  __int64 v11; // rdx
  LSTATUS v12; // eax
  CallStackTracing *v13; // rcx
  __int64 v14; // rdx
  CallStackTracing *v15; // rcx
  LSTATUS v16; // eax
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  struct CallStackContext *v20; // rax
  struct CallStackContext *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rcx
  struct CallStackContext *v24; // rax
  CallStackTracing *v25; // rcx
  struct CallStackContext *v26; // rax
  struct CallStackContext *v27; // rax
  HKEY *fAsynchronous; // [rsp+20h] [rbp-38h]
  CallStackScopeTrace v29; // [rsp+60h] [rbp+8h] BYREF
  IRtwqAsyncResult *asyncResult; // [rsp+68h] [rbp+10h] BYREF

  v2 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v2 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v2 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v2->m_fEnabled )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v2);
    m_dwDepth = ThreadRelativeContext->m_dwDepth;
    if ( (unsigned int)m_dwDepth < ThreadRelativeContext->m_dwMaxDepth )
    {
      v5 = m_dwDepth;
      ThreadRelativeContext->m_rgInfo[v5].m_pszFunction = "MFTEnumCache::InitRegListener";
      ThreadRelativeContext->m_rgInfo[v5].m_lineNumber = 3362;
    }
    ++ThreadRelativeContext->m_dwDepth;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v6 = *((_DWORD *)this + 38);
  asyncResult = 0;
  if ( v6 )
  {
    v10 = CallStackTracing::s_wpInstance;
    v8 = -1072873851;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v10 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v10->m_fEnabled )
    {
      v20 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( v20->m_result != -1072873851 )
        CallStackContext::TraceFailure(v20, "MFTEnumCache::InitRegListener", 3375, -1072873851);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_14;
    v11 = 76;
    goto LABEL_87;
  }
  if ( *((_QWORD *)this + 17) )
    goto LABEL_8;
  fAsynchronous = (HKEY *)((char *)this + 136);
  if ( IsCoreWindowApplication() )
  {
    v16 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Classes\\MediaFoundation\\Transforms",
            0,
            0x20019u,
            fAsynchronous);
    v8 = v16;
    if ( v16 > 0 )
      v8 = (unsigned __int16)v16 | 0x80070000;
    if ( v8 < 0 )
    {
      v17 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v17 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v17->m_fEnabled )
      {
        v21 = CallStackTracing::GetThreadRelativeContext(v17);
        if ( v21->m_result != v8 )
          CallStackContext::TraceFailure(v21, "MFTEnumCache::InitRegListener", 3388, v8);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v14 = 77;
        goto LABEL_33;
      }
      goto LABEL_14;
    }
    goto LABEL_8;
  }
  v12 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"MediaFoundation\\Transforms", 0, 0x20019u, fAsynchronous);
  v8 = v12;
  if ( v12 > 0 )
    v8 = (unsigned __int16)v12 | 0x80070000;
  if ( v8 >= 0 )
  {
LABEL_8:
    v7 = RegNotifyChangeKeyValue(*((HKEY *)this + 17), 1, 0x10000005u, *((HANDLE *)this + 16), 1);
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v8 < 0 )
    {
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
        if ( v19->m_result != v8 )
          CallStackContext::TraceFailure(v19, "MFTEnumCache::InitRegListener", 3398, v8);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v14 = 79;
        goto LABEL_33;
      }
      goto LABEL_14;
    }
    v8 = RtwqCreateAsyncResult(0, (IRtwqAsyncCallback *)((char *)this + 160), 0, &asyncResult);
    if ( v8 < 0 )
    {
      v23 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
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
        if ( v24->m_result != v8 )
          CallStackContext::TraceFailure(v24, "MFTEnumCache::InitRegListener", 3400, v8);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v14 = 80;
        goto LABEL_33;
      }
      goto LABEL_14;
    }
    if ( !*((_DWORD *)this + 38) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      v8 = RtwqPutWaitingWorkItem(*((HANDLE *)this + 16), 0, asyncResult, (RTWQWORKITEM_KEY *)this + 18);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      if ( v8 < 0 )
      {
        v15 = CallStackTracing::s_wpInstance;
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
          v27 = CallStackTracing::GetThreadRelativeContext(v15);
          if ( v27->m_result != v8 )
            CallStackContext::TraceFailure(v27, "MFTEnumCache::InitRegListener", 3417, v8);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v14 = 82;
          goto LABEL_33;
        }
      }
      goto LABEL_14;
    }
    v25 = CallStackTracing::s_wpInstance;
    v8 = -1072873851;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v25 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v25 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v25->m_fEnabled )
    {
      v26 = CallStackTracing::GetThreadRelativeContext(v25);
      if ( v26->m_result != -1072873851 )
        CallStackContext::TraceFailure(v26, "MFTEnumCache::InitRegListener", 3408, -1072873851);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_14;
    v11 = 81;
LABEL_87:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
      this,
      -1072873851);
    goto LABEL_14;
  }
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
      CallStackContext::TraceFailure(v22, "MFTEnumCache::InitRegListener", 3392, v8);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v14 = 78;
LABEL_33:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_aba25f5d0023316200c116552e7e9732_Traceguids, this, v8);
  }
LABEL_14:
  if ( asyncResult )
    asyncResult->Release(asyncResult);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  CallStackScopeTrace::~CallStackScopeTrace(&v29);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004dc00  mov     [rsp+arg_10], rbx
0x18004dc05  push    rbp
0x18004dc06  push    rsi
0x18004dc07  push    rdi
0x18004dc08  push    r13
0x18004dc0a  push    r15
0x18004dc0c  sub     rsp, 30h
0x18004dc10  mov     rsi, rcx
0x18004dc13  lea     r15, stru_1801F8A30
0x18004dc1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004dc21  lea     r13, stru_1801FC290
0x18004dc28  test    rcx, rcx
0x18004dc2b  jz      loc_18004DE72
0x18004dc31  cmp     byte ptr [rcx+8], 0
0x18004dc35  lea     rbx, aMftenumcacheIn; "MFTEnumCache::InitRegListener"
0x18004dc3c  jz      short loc_18004DC66
0x18004dc3e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004dc43  mov     ecx, [rax+7C4h]
0x18004dc49  cmp     ecx, [rax+7C8h]
0x18004dc4f  jnb     short loc_18004DC60
0x18004dc51  add     rcx, rcx
0x18004dc54  mov     [rax+rcx*8], rbx
0x18004dc58  mov     dword ptr [rax+rcx*8+8], 0D22h
0x18004dc60  inc     dword ptr [rax+7C4h]
0x18004dc66  lea     rbp, [rsi+58h]
0x18004dc6a  mov     rcx, rbp; lpCriticalSection
0x18004dc6d  call    cs:__imp_EnterCriticalSection
0x18004dc73  mov     eax, [rsi+98h]
0x18004dc79  mov     [rsp+58h+asyncResult], 0
0x18004dc82  test    eax, eax
0x18004dc84  jnz     loc_18004DD80
0x18004dc8a  lea     rdi, [rsi+88h]
0x18004dc91  cmp     qword ptr [rdi], 0
0x18004dc95  jz      loc_18004DDB4
0x18004dc9b  mov     r9, [rsi+80h]; hEvent
0x18004dca2  mov     edx, 1; bWatchSubtree
0x18004dca7  mov     rcx, [rdi]; hKey
0x18004dcaa  mov     r8d, 10000005h; dwNotifyFilter
0x18004dcb0  mov     [rsp+58h+fAsynchronous], 1; fAsynchronous
0x18004dcb8  call    cs:__imp_RegNotifyChangeKeyValue
0x18004dcbe  mov     ebx, eax
0x18004dcc0  test    eax, eax
0x18004dcc2  jg      loc_18004DD72
0x18004dcc8  test    ebx, ebx
0x18004dcca  js      loc_18004DF11
0x18004dcd0  lea     rdx, [rsi+0A0h]; callback
0x18004dcd7  xor     r8d, r8d; appState
0x18004dcda  lea     r9, [rsp+58h+asyncResult]; asyncResult
0x18004dcdf  xor     ecx, ecx; appObject
0x18004dce1  call    cs:__imp_RtwqCreateAsyncResult
0x18004dce7  mov     ebx, eax
0x18004dce9  test    eax, eax
0x18004dceb  js      loc_18004E13E
0x18004dcf1  mov     eax, [rsi+98h]
0x18004dcf7  test    eax, eax
0x18004dcf9  jnz     loc_18004E1C4
0x18004dcff  mov     rcx, rbp; lpCriticalSection
0x18004dd02  call    cs:__imp_LeaveCriticalSection
0x18004dd08  mov     r8, [rsp+58h+asyncResult]; result
0x18004dd0d  lea     r9, [rsi+90h]; key
0x18004dd14  mov     rcx, [rsi+80h]; hEvent
0x18004dd1b  xor     edx, edx; lPriority
0x18004dd1d  call    cs:__imp_RtwqPutWaitingWorkItem
0x18004dd23  mov     rcx, rbp; lpCriticalSection
0x18004dd26  mov     ebx, eax
0x18004dd28  call    cs:__imp_EnterCriticalSection
0x18004dd2e  test    ebx, ebx
0x18004dd30  js      loc_18004DE23
0x18004dd36  mov     rcx, [rsp+58h+asyncResult]
0x18004dd3b  test    rcx, rcx
0x18004dd3e  jz      short loc_18004DD4C
0x18004dd40  mov     rax, [rcx]
0x18004dd43  mov     rax, [rax+10h]
0x18004dd47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd4c  mov     rcx, rbp; lpCriticalSection
0x18004dd4f  call    cs:__imp_LeaveCriticalSection
0x18004dd55  lea     rcx, [rsp+58h+arg_0]; this
0x18004dd5a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004dd5f  mov     eax, ebx
0x18004dd61  mov     rbx, [rsp+58h+arg_10]
0x18004dd66  add     rsp, 30h
0x18004dd6a  pop     r15
0x18004dd6c  pop     r13
0x18004dd6e  pop     rdi
0x18004dd6f  pop     rsi
0x18004dd70  pop     rbp
0x18004dd71  retn
0x18004dd72  movzx   ebx, ax
0x18004dd75  or      ebx, 80070000h
0x18004dd7b  jmp     loc_18004DCC8
0x18004dd80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004dd87  mov     edi, 0C00D3E85h
0x18004dd8c  mov     ebx, edi
0x18004dd8e  test    rcx, rcx
0x18004dd91  jz      loc_18004DF50
0x18004dd97  cmp     byte ptr [rcx+8], 0
0x18004dd9b  jnz     loc_18004E0B4
0x18004dda1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004dda8  jb      short loc_18004DD36
0x18004ddaa  mov     edx, 4Ch ; 'L'
0x18004ddaf  jmp     loc_18004E21C
0x18004ddb4  call    ?IsCoreWindowApplication@@YA_NXZ; IsCoreWindowApplication(void)
0x18004ddb9  xor     r8d, r8d; ulOptions
0x18004ddbc  mov     qword ptr [rsp+58h+fAsynchronous], rdi; phkResult
0x18004ddc1  mov     r9d, 20019h; samDesired
0x18004ddc7  test    al, al
0x18004ddc9  jnz     loc_18004DEAF
0x18004ddcf  lea     rdx, SubKey; "MediaFoundation\\Transforms"
0x18004ddd6  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18004dddd  call    cs:__imp_RegOpenKeyExW
0x18004dde3  mov     ebx, eax
0x18004dde5  test    eax, eax
0x18004dde7  jg      loc_18004DEA1
0x18004dded  test    ebx, ebx
0x18004ddef  jns     loc_18004DC9B
0x18004ddf5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004ddfc  test    rcx, rcx
0x18004ddff  jz      loc_18004DF8E
0x18004de05  cmp     byte ptr [rcx+8], 0
0x18004de09  jnz     loc_18004E110
0x18004de0f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004de16  jb      loc_18004DD36
0x18004de1c  mov     edx, 4Eh ; 'N'
0x18004de21  jmp     short loc_18004DE4F
0x18004de23  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004de2a  test    rcx, rcx
0x18004de2d  jz      loc_18004DFCC
0x18004de33  cmp     byte ptr [rcx+8], 0
0x18004de37  jnz     loc_18004E255
0x18004de3d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004de44  jb      loc_18004DD36
0x18004de4a  mov     edx, 52h ; 'R'
0x18004de4f  mov     [rsp+58h+fAsynchronous], ebx
0x18004de53  mov     rcx, cs:WPP_GLOBAL_Control
0x18004de5a  lea     r8, WPP_aba25f5d0023316200c116552e7e9732_Traceguids
0x18004de61  mov     r9, rsi
0x18004de64  mov     rcx, [rcx+10h]
0x18004de68  call    WPP_SF_qD
0x18004de6d  jmp     loc_18004DD36
0x18004de72  mov     rax, cs:stru_1801FC290.__vftable
0x18004de79  mov     edx, 7F0h
0x18004de7e  mov     rcx, r13
0x18004de81  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18004de88  mov     rax, [rax+8]
0x18004de8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de91  test    eax, eax
0x18004de93  jz      short loc_18004DF02
0x18004de95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004de9c  jmp     loc_18004DC31
0x18004dea1  movzx   ebx, ax
0x18004dea4  or      ebx, 80070000h
0x18004deaa  jmp     loc_18004DDED
0x18004deaf  lea     rdx, aSoftwareClasse; "Software\\Classes\\MediaFoundation\\Tra"...
0x18004deb6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004debd  call    cs:__imp_RegOpenKeyExW
0x18004dec3  mov     ebx, eax
0x18004dec5  test    eax, eax
0x18004dec7  jg      short loc_18004DF42
0x18004dec9  test    ebx, ebx
0x18004decb  jns     loc_18004DC9B
0x18004ded1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004ded8  test    rcx, rcx
0x18004dedb  jz      loc_18004E038
0x18004dee1  cmp     byte ptr [rcx+8], 0
0x18004dee5  jnz     loc_18004E0E2
0x18004deeb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004def2  jb      loc_18004DD36
0x18004def8  mov     edx, 4Dh ; 'M'
0x18004defd  jmp     loc_18004DE4F
0x18004df02  mov     rcx, r15
0x18004df05  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004df0c  jmp     loc_18004DC31
0x18004df11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004df18  test    rcx, rcx
0x18004df1b  jz      loc_18004E076
0x18004df21  cmp     byte ptr [rcx+8], 0
0x18004df25  jnz     loc_18004E00A
0x18004df2b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004df32  jb      loc_18004DD36
0x18004df38  mov     edx, 4Fh ; 'O'
0x18004df3d  jmp     loc_18004DE4F
0x18004df42  movzx   ebx, ax
0x18004df45  or      ebx, 80070000h
0x18004df4b  jmp     loc_18004DEC9
0x18004df50  mov     rax, cs:stru_1801FC290.__vftable
0x18004df57  mov     edx, 7F0h
0x18004df5c  mov     rcx, r13
0x18004df5f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18004df66  mov     rax, [rax+8]
0x18004df6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df6f  test    eax, eax
0x18004df71  jnz     short loc_18004DF82
0x18004df73  mov     rcx, r15
0x18004df76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004df7d  jmp     loc_18004DD97
0x18004df82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004df89  jmp     loc_18004DD97
0x18004df8e  mov     rax, cs:stru_1801FC290.__vftable
0x18004df95  mov     edx, 7F0h
0x18004df9a  mov     rcx, r13
0x18004df9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dfa4  mov     rax, [rax+8]
0x18004dfa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfad  test    eax, eax
0x18004dfaf  jnz     short loc_18004DFC0
0x18004dfb1  mov     rcx, r15
0x18004dfb4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dfbb  jmp     loc_18004DE05
0x18004dfc0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dfc7  jmp     loc_18004DE05
0x18004dfcc  mov     rax, cs:stru_1801FC290.__vftable
0x18004dfd3  mov     edx, 7F0h
0x18004dfd8  mov     rcx, r13
0x18004dfdb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dfe2  mov     rax, [rax+8]
0x18004dfe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfeb  test    eax, eax
0x18004dfed  jnz     short loc_18004DFFE
0x18004dfef  mov     rcx, r15
0x18004dff2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dff9  jmp     loc_18004DE33
0x18004dffe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e005  jmp     loc_18004DE33
0x18004e00a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e00f  cmp     [rax+7CCh], ebx
0x18004e015  jz      loc_18004DF2B
0x18004e01b  mov     r9d, ebx; int
0x18004e01e  lea     rdx, aMftenumcacheIn; "MFTEnumCache::InitRegListener"
0x18004e025  mov     r8d, 0D46h; int
0x18004e02b  mov     rcx, rax; this
0x18004e02e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e033  jmp     loc_18004DF2B
0x18004e038  mov     rax, cs:stru_1801FC290.__vftable
0x18004e03f  mov     edx, 7F0h
0x18004e044  mov     rcx, r13
0x18004e047  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e04e  mov     rax, [rax+8]
0x18004e052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e057  test    eax, eax
0x18004e059  jnz     short loc_18004E06A
0x18004e05b  mov     rcx, r15
0x18004e05e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e065  jmp     loc_18004DEE1
0x18004e06a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e071  jmp     loc_18004DEE1
0x18004e076  mov     rax, cs:stru_1801FC290.__vftable
0x18004e07d  mov     edx, 7F0h
0x18004e082  mov     rcx, r13
0x18004e085  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e08c  mov     rax, [rax+8]
0x18004e090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e095  test    eax, eax
0x18004e097  jnz     short loc_18004E0A8
0x18004e099  mov     rcx, r15
0x18004e09c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e0a3  jmp     loc_18004DF21
0x18004e0a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e0af  jmp     loc_18004DF21
0x18004e0b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e0b9  cmp     [rax+7CCh], edi
0x18004e0bf  jz      loc_18004DDA1
0x18004e0c5  mov     r9d, edi; int
0x18004e0c8  lea     rdx, aMftenumcacheIn; "MFTEnumCache::InitRegListener"
0x18004e0cf  mov     r8d, 0D2Fh; int
0x18004e0d5  mov     rcx, rax; this
0x18004e0d8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e0dd  jmp     loc_18004DDA1
0x18004e0e2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e0e7  cmp     [rax+7CCh], ebx
0x18004e0ed  jz      loc_18004DEEB
0x18004e0f3  mov     r9d, ebx; int
0x18004e0f6  lea     rdx, aMftenumcacheIn; "MFTEnumCache::InitRegListener"
0x18004e0fd  mov     r8d, 0D3Ch; int
0x18004e103  mov     rcx, rax; this
0x18004e106  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e10b  jmp     loc_18004DEEB
0x18004e110  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e115  cmp     [rax+7CCh], ebx
0x18004e11b  jz      loc_18004DE0F
0x18004e121  mov     r9d, ebx; int
0x18004e124  lea     rdx, aMftenumcacheIn; "MFTEnumCache::InitRegListener"
0x18004e12b  mov     r8d, 0D40h; int
0x18004e131  mov     rcx, rax; this
0x18004e134  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e139  jmp     loc_18004DE0F
0x18004e13e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e145  test    rcx, rcx
0x18004e148  jnz     short loc_18004E177
0x18004e14a  mov     rcx, cs:stru_1801FC290.__vftable
0x18004e151  mov     edx, 7F0h
0x18004e156  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e15d  mov     rax, [rcx+8]
0x18004e161  mov     rcx, r13
0x18004e164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e169  test    eax, eax
0x18004e16b  jnz     short loc_18004E194
0x18004e16d  mov     rcx, r15; this
0x18004e170  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e177  cmp     byte ptr [rcx+8], 0
0x18004e17b  jnz     short loc_18004E19D
  ... truncated ...
```
