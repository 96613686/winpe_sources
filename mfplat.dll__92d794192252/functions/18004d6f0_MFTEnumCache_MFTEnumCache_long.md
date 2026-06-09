# MFTEnumCache::MFTEnumCache(long *)

- ea: `0x18004d6f0`
- end: `0x18004dafc`
- name: `??0MFTEnumCache@@QEAA@PEAJ@Z`
- size: `1036`
- prototype: `MFTEnumCache *__fastcall(MFTEnumCache *__hidden this, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18004d49c`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18004d6f0`
- `0x18004dc00`
- `0x18004e2b4`
- `0x18004e39c`
- `0x18004e470`
- `0x1801200d0`
- `0x180120ecc`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004d71d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004d743`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004d71d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004d743`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d796`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004d796`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18004d7f2`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18004d7f2`

## string_xrefs

- `0x18004d79c`: `MFTEnumCache::MFTEnumCache`

## pseudocode

```c
MFTEnumCache *__fastcall MFTEnumCache::MFTEnumCache(MFTEnumCache *this, int *a2)
{
  int inited; // ebx
  char v5; // al
  CallStackTracing *v7; // rcx
  __int64 v8; // rdx
  CallStackTracing *v9; // rcx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  CallStackTracing *v12; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v14; // rax
  struct CallStackContext *v15; // rax
  CallStackScopeTrace v16; // [rsp+30h] [rbp-1D8h] BYREF
  int v17; // [rsp+40h] [rbp-1C8h] BYREF
  __int64 v18; // [rsp+44h] [rbp-1C4h]
  int v19; // [rsp+4Ch] [rbp-1BCh]

  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 38) = 0;
  *((_DWORD *)this + 39) = 1;
  MFTEnumCache::OnRegChangeAsyncCallback::OnRegChangeAsyncCallback((MFTEnumCache *)((char *)this + 160));
  memset_0(&v17, 0, 0x1A0u);
  *((_QWORD *)this + 16) = CreateEventW(0, 0, 0, 0);
  CallStackScopeTrace::CallStackScopeTrace(&v16, "MFTEnumCache::MFTEnumCache", 3454);
  if ( *((_QWORD *)this + 16) )
  {
    v17 = 416;
    v18 = 1;
    v19 = 0;
    if ( (unsigned int)CM_Register_Notification(&v17, this, &MFTEnumCache::EventCallback, (char *)this + 64) )
    {
      v12 = CallStackTracing::s_wpInstance;
      inited = -2147467259;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v12 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v12->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v12);
        if ( ThreadRelativeContext->m_result != -2147467259 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MFTEnumCache::MFTEnumCache", 3464, -2147467259);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 84;
        goto LABEL_16;
      }
    }
    else
    {
      inited = MFTEnumCache::InitRegListener(this);
      if ( inited < 0 )
      {
        v9 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v9 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v9 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v9->m_fEnabled )
        {
          v14 = CallStackTracing::GetThreadRelativeContext(v9);
          if ( v14->m_result != inited )
            CallStackContext::TraceFailure(v14, "MFTEnumCache::MFTEnumCache", 3466, inited);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v8 = 85;
          goto LABEL_16;
        }
      }
      else
      {
        if ( byte_1801FD8ED )
        {
          v5 = byte_1801FD8EC;
        }
        else
        {
          v5 = MatchesModule(L"realsensedcm");
          byte_1801FD8EC = v5;
          byte_1801FD8ED = 1;
        }
        if ( !v5 )
        {
          inited = MFPutWorkItem__lambda_ddc02965d4f9b3a8bded5f8075a91c83_();
          if ( inited < 0 )
          {
            v7 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v7 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v7 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v7->m_fEnabled )
            {
              v15 = CallStackTracing::GetThreadRelativeContext(v7);
              if ( v15->m_result != inited )
                CallStackContext::TraceFailure(v15, "MFTEnumCache::MFTEnumCache", 3476, inited);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v8 = 86;
LABEL_16:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v8,
                &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
                this,
                inited);
            }
          }
        }
      }
    }
  }
  else
  {
    v10 = CallStackTracing::s_wpInstance;
    inited = -2147024882;
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
      v11 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( v11->m_result != -2147024882 )
        CallStackContext::TraceFailure(v11, "MFTEnumCache::MFTEnumCache", 3454, -2147024882);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v8 = 83;
      goto LABEL_16;
    }
  }
  *a2 = inited;
  CallStackScopeTrace::~CallStackScopeTrace(&v16);
  return this;
}

```

## disassembly

```asm
0x18004d6f0  mov     [rsp+arg_10], rbx
0x18004d6f5  mov     [rsp+arg_18], rbp
0x18004d6fa  push    rsi
0x18004d6fb  push    rdi
0x18004d6fc  push    r15
0x18004d6fe  sub     rsp, 1F0h
0x18004d705  mov     rax, cs:__security_cookie
0x18004d70c  xor     rax, rsp
0x18004d70f  mov     [rsp+208h+var_28], rax
0x18004d717  mov     rsi, rdx
0x18004d71a  mov     rdi, rcx
0x18004d71d  call    cs:__imp_InitializeCriticalSection
0x18004d723  xor     ebp, ebp
0x18004d725  lea     rcx, [rdi+58h]; lpCriticalSection
0x18004d729  mov     [rdi+28h], rbp
0x18004d72d  xor     eax, eax
0x18004d72f  mov     [rdi+30h], rbp
0x18004d733  mov     [rdi+38h], rbp
0x18004d737  mov     [rdi+40h], rbp
0x18004d73b  mov     [rdi+48h], rax
0x18004d73f  mov     [rdi+50h], rbp
0x18004d743  call    cs:__imp_InitializeCriticalSection
0x18004d749  mov     [rdi+80h], rbp
0x18004d750  lea     rcx, [rdi+0A0h]; this
0x18004d757  mov     [rdi+88h], rbp
0x18004d75e  mov     [rdi+90h], rbp
0x18004d765  mov     [rdi+98h], ebp
0x18004d76b  mov     dword ptr [rdi+9Ch], 1
0x18004d775  call    ??0OnRegChangeAsyncCallback@MFTEnumCache@@QEAA@XZ; MFTEnumCache::OnRegChangeAsyncCallback::OnRegChangeAsyncCallback(void)
0x18004d77a  xor     edx, edx; Val
0x18004d77c  lea     rcx, [rsp+208h+var_1C8]; void *
0x18004d781  mov     r8d, 1A0h; Size
0x18004d787  call    memset_0
0x18004d78c  xor     r9d, r9d; lpName
0x18004d78f  xor     r8d, r8d; bInitialState
0x18004d792  xor     edx, edx; bManualReset
0x18004d794  xor     ecx, ecx; lpEventAttributes
0x18004d796  call    cs:__imp_CreateEventW
0x18004d79c  lea     r15, aMftenumcacheMf; "MFTEnumCache::MFTEnumCache"
0x18004d7a3  mov     r8d, 0D7Eh; int
0x18004d7a9  lea     rcx, [rsp+208h+var_1D8]; this
0x18004d7ae  mov     [rdi+80h], rax
0x18004d7b5  mov     rdx, r15; char *
0x18004d7b8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004d7bd  cmp     [rdi+80h], rbp
0x18004d7c4  jz      loc_18004D978
0x18004d7ca  lea     r9, [rdi+40h]
0x18004d7ce  mov     [rsp+208h+var_1C8], 1A0h
0x18004d7d6  lea     r8, ?EventCallback@MFTEnumCache@@SAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; MFTEnumCache::EventCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18004d7dd  mov     [rsp+208h+var_1C4], 1
0x18004d7e6  mov     rdx, rdi
0x18004d7e9  mov     [rsp+208h+var_1BC], ebp
0x18004d7ed  lea     rcx, [rsp+208h+var_1C8]
0x18004d7f2  call    cs:__imp_CM_Register_Notification
0x18004d7f8  test    eax, eax
0x18004d7fa  jnz     loc_18004DA0A
0x18004d800  mov     rcx, rdi; this
0x18004d803  call    ?InitRegListener@MFTEnumCache@@QEAAJXZ; MFTEnumCache::InitRegListener(void)
0x18004d808  mov     ebx, eax
0x18004d80a  test    eax, eax
0x18004d80c  js      loc_18004D90B
0x18004d812  cmp     cs:byte_1801FD8ED, bpl
0x18004d819  jnz     short loc_18004D871
0x18004d81b  xor     edx, edx
0x18004d81d  lea     rcx, aRealsensedcm; "realsensedcm"
0x18004d824  call    MatchesModule
0x18004d829  mov     cs:byte_1801FD8EC, al
0x18004d82f  mov     cs:byte_1801FD8ED, 1
0x18004d836  test    al, al
0x18004d838  jz      short loc_18004D879
0x18004d83a  lea     rcx, [rsp+208h+var_1D8]; this
0x18004d83f  mov     [rsi], ebx
0x18004d841  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004d846  mov     rax, rdi
0x18004d849  mov     rcx, [rsp+208h+var_28]
0x18004d851  xor     rcx, rsp; StackCookie
0x18004d854  call    __security_check_cookie
0x18004d859  lea     r11, [rsp+208h+var_18]
0x18004d861  mov     rbx, [r11+30h]
0x18004d865  mov     rbp, [r11+38h]
0x18004d869  mov     rsp, r11
0x18004d86c  pop     r15
0x18004d86e  pop     rdi
0x18004d86f  pop     rsi
0x18004d870  retn
0x18004d871  mov     al, cs:byte_1801FD8EC
0x18004d877  jmp     short loc_18004D836
0x18004d879  call    MFPutWorkItem__lambda_ddc02965d4f9b3a8bded5f8075a91c83___; MFPutWorkItem__lambda_ddc02965d4f9b3a8bded5f8075a91c83_
0x18004d87e  mov     ebx, eax
0x18004d880  test    eax, eax
0x18004d882  jns     short loc_18004D83A
0x18004d884  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d88b  test    rcx, rcx
0x18004d88e  jnz     short loc_18004D8CC
0x18004d890  mov     rax, cs:stru_1801FC290.__vftable
0x18004d897  lea     r8, stru_1801FC290
0x18004d89e  mov     edx, 7F0h
0x18004d8a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d8aa  mov     rcx, r8
0x18004d8ad  mov     rax, [rax+8]
0x18004d8b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8b6  test    eax, eax
0x18004d8b8  jnz     loc_18004DAC6
0x18004d8be  lea     rcx, stru_1801F8A30; this
0x18004d8c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d8cc  cmp     [rcx+8], bpl
0x18004d8d0  jnz     loc_18004DAD2
0x18004d8d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d8dd  jb      loc_18004D83A
0x18004d8e3  mov     edx, 56h ; 'V'
0x18004d8e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d8ef  lea     r8, WPP_aba25f5d0023316200c116552e7e9732_Traceguids
0x18004d8f6  mov     r9, rdi
0x18004d8f9  mov     [rsp+208h+var_1E8], ebx
0x18004d8fd  mov     rcx, [rcx+10h]
0x18004d901  call    WPP_SF_qD
0x18004d906  jmp     loc_18004D83A
0x18004d90b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004d912  test    rcx, rcx
0x18004d915  jz      short loc_18004D935
0x18004d917  cmp     [rcx+8], bpl
0x18004d91b  jnz     loc_18004DA9C
0x18004d921  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d928  jb      loc_18004D83A
0x18004d92e  mov     edx, 55h ; 'U'
0x18004d933  jmp     short loc_18004D8E8
0x18004d935  mov     rcx, cs:stru_1801FC290.__vftable
0x18004d93c  lea     r8, stru_1801FC290
0x18004d943  mov     edx, 7F0h
0x18004d948  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d94f  mov     rax, [rcx+8]
0x18004d953  mov     rcx, r8
0x18004d956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d95b  test    eax, eax
0x18004d95d  jnz     short loc_18004D96F
0x18004d95f  lea     rcx, stru_1801F8A30
0x18004d966  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d96d  jmp     short loc_18004D917
0x18004d96f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d976  jmp     short loc_18004D917
0x18004d978  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d97f  mov     ebx, 8007000Eh
0x18004d984  test    rcx, rcx
0x18004d987  jnz     short loc_18004D9C1
0x18004d989  mov     rax, cs:stru_1801FC290.__vftable
0x18004d990  lea     r8, stru_1801FC290
0x18004d997  mov     edx, 7F0h
0x18004d99c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d9a3  mov     rcx, r8
0x18004d9a6  mov     rax, [rax+8]
0x18004d9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d9af  test    eax, eax
0x18004d9b1  jnz     short loc_18004D9DE
0x18004d9b3  lea     rcx, stru_1801F8A30; this
0x18004d9ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d9c1  cmp     [rcx+8], bpl
0x18004d9c5  jnz     short loc_18004D9E7
0x18004d9c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d9ce  jb      loc_18004D83A
0x18004d9d4  mov     edx, 53h ; 'S'
0x18004d9d9  jmp     loc_18004D8E8
0x18004d9de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d9e5  jmp     short loc_18004D9C1
0x18004d9e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d9ec  cmp     [rax+7CCh], ebx
0x18004d9f2  jz      short loc_18004D9C7
0x18004d9f4  mov     r9d, ebx; int
0x18004d9f7  mov     r8d, 0D7Eh; int
0x18004d9fd  mov     rdx, r15; char *
0x18004da00  mov     rcx, rax; this
0x18004da03  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004da08  jmp     short loc_18004D9C7
0x18004da0a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004da11  mov     ebx, 80004005h
0x18004da16  test    rcx, rcx
0x18004da19  jnz     short loc_18004DA53
0x18004da1b  mov     rax, cs:stru_1801FC290.__vftable
0x18004da22  lea     r8, stru_1801FC290
0x18004da29  mov     edx, 7F0h
0x18004da2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18004da35  mov     rcx, r8
0x18004da38  mov     rax, [rax+8]
0x18004da3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da41  test    eax, eax
0x18004da43  jnz     short loc_18004DA70
0x18004da45  lea     rcx, stru_1801F8A30; this
0x18004da4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004da53  cmp     [rcx+8], bpl
0x18004da57  jnz     short loc_18004DA79
0x18004da59  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004da60  jb      loc_18004D83A
0x18004da66  mov     edx, 54h ; 'T'
0x18004da6b  jmp     loc_18004D8E8
0x18004da70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004da77  jmp     short loc_18004DA53
0x18004da79  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004da7e  cmp     [rax+7CCh], ebx
0x18004da84  jz      short loc_18004DA59
0x18004da86  mov     r9d, ebx; int
0x18004da89  mov     r8d, 0D88h; int
0x18004da8f  mov     rdx, r15; char *
0x18004da92  mov     rcx, rax; this
0x18004da95  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004da9a  jmp     short loc_18004DA59
0x18004da9c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004daa1  cmp     [rax+7CCh], ebx
0x18004daa7  jz      loc_18004D921
0x18004daad  mov     r9d, ebx; int
0x18004dab0  mov     r8d, 0D8Ah; int
0x18004dab6  mov     rdx, r15; char *
0x18004dab9  mov     rcx, rax; this
0x18004dabc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004dac1  jmp     loc_18004D921
0x18004dac6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dacd  jmp     loc_18004D8CC
0x18004dad2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004dad7  cmp     [rax+7CCh], ebx
0x18004dadd  jz      loc_18004D8D6
0x18004dae3  mov     r9d, ebx; int
0x18004dae6  mov     r8d, 0D94h; int
0x18004daec  mov     rdx, r15; char *
0x18004daef  mov     rcx, rax; this
0x18004daf2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004daf7  jmp     loc_18004D8D6
```
