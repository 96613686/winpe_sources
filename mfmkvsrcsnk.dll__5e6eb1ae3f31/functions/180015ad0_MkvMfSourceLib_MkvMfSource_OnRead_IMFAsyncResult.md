# MkvMfSourceLib::MkvMfSource::OnRead(IMFAsyncResult *)

- ea: `0x180015ad0`
- end: `0x180015dc3`
- name: `?OnRead@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncResult@@@Z`
- size: `755`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180014880`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180015ad0`
- `0x180019b10`
- `0x18001ac70`
- `0x180020d84`
- `0x18004237c`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015c56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015c56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015d26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015d75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015d90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015d26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015d75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015d90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015ba1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015c7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015ba1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015c7e`

## string_xrefs

- `0x180015b06`: `MkvMfSourceLib::MkvMfSource::OnRead`
- `0x180015c05`: `MkvMfSourceLib::MkvMfSource::OnRead`
- `0x180015ce2`: `MkvMfSourceLib::MkvMfSource::OnRead`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfSource::OnRead(MkvMfSourceLib::MkvMfSource *this, struct IMFAsyncResult *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  unsigned int Operations; // ebx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  char v19; // bl
  int v21; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v22[4]; // [rsp+34h] [rbp-2Ch] BYREF
  MkvMfSourceLib::MkvMfSource *v23; // [rsp+38h] [rbp-28h]
  int *v24; // [rsp+40h] [rbp-20h]
  char *v25; // [rsp+48h] [rbp-18h] BYREF

  v21 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v22, "MkvMfSourceLib::MkvMfSource::OnRead", 1346);
  v7 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 86) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 86) + 296LL))(*((_QWORD *)this + 86));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, char **))(**((_QWORD **)this + 86) + 280LL))(
                                                            *((_QWORD *)this + 86),
                                                            &v25);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  v23 = this;
  v24 = &v21;
  if ( a2 )
  {
    v25 = (char *)this + 104;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    if ( *((_QWORD *)this + 18) )
    {
      v19 = *((_BYTE *)this + 192);
      *((_DWORD *)this + 120) = MkvReader::AsyncReadCompletion((MkvMfSourceLib::MkvMfSource *)((char *)this + 184), a2);
      if ( v19 )
      {
        *((_BYTE *)this + 486) = 0;
        if ( !*((_BYTE *)this + 485) )
        {
          *((_BYTE *)this + 485) = 1;
          MkvMfSourceLib::MkvMfSource::QueueOperation(this, (struct IMFAsyncCallback *)this + 63);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
        Operations = 0;
      }
      else
      {
        Operations = MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations((struct IMFAsyncCallback *)this, a2);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
      }
    }
    else
    {
      v21 = -1072873851;
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( v21 < 0 && *((_DWORD *)v18 + 499) != v21 )
          CallStackContext::TraceFailure(v18, "MkvMfSourceLib::MkvMfSource::OnRead", 1356, v21);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v21);
      Operations = v21;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    }
  }
  else
  {
    v21 = -2147024809;
    if ( !v7 )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( v21 < 0 && *((_DWORD *)v11 + 499) != v21 )
        CallStackContext::TraceFailure(v11, "MkvMfSourceLib::MkvMfSource::OnRead", 1350, v21);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v21);
    Operations = v21;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v22);
  return Operations;
}

```

## disassembly

```asm
0x180015ad0  mov     [rsp-18h+arg_10], rbx
0x180015ad5  mov     [rsp-18h+arg_18], rsi
0x180015ada  push    rbp
0x180015adb  push    rdi
0x180015adc  push    r14
0x180015ade  mov     rbp, rsp
0x180015ae1  sub     rsp, 60h
0x180015ae5  mov     rax, cs:__security_cookie
0x180015aec  xor     rax, rsp
0x180015aef  mov     [rbp+var_8], rax
0x180015af3  mov     r14, rdx
0x180015af6  mov     rsi, rcx
0x180015af9  mov     [rbp+var_30], 0
0x180015b00  mov     r8d, 542h; int
0x180015b06  lea     rdx, aMkvmfsourcelib_26; "MkvMfSourceLib::MkvMfSource::OnRead"
0x180015b0d  lea     rcx, [rbp+var_2C]; this
0x180015b11  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180015b16  nop
0x180015b17  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180015b1e  cmp     byte ptr [rcx+8], 0
0x180015b22  jz      short loc_180015B80
0x180015b24  cmp     qword ptr [rsi+2B0h], 0
0x180015b2c  jz      short loc_180015B80
0x180015b2e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015b33  mov     rdi, rax
0x180015b36  mov     rcx, [rsi+2B0h]
0x180015b3d  mov     rdx, [rcx]
0x180015b40  mov     rax, [rdx+128h]
0x180015b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b4c  mov     ebx, eax
0x180015b4e  mov     rcx, [rsi+2B0h]
0x180015b55  mov     rdx, [rcx]
0x180015b58  mov     rax, [rdx+118h]
0x180015b5f  lea     rdx, [rbp+var_18]
0x180015b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b68  movups  xmm0, xmmword ptr [rax]
0x180015b6b  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180015b73  mov     [rdi+7E0h], ebx
0x180015b79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015b80  mov     [rbp+var_28], rsi
0x180015b84  lea     rax, [rbp+var_30]
0x180015b88  mov     [rbp+var_20], rax
0x180015b8c  test    r14, r14
0x180015b8f  jnz     loc_180015C4B
0x180015b95  mov     [rbp+var_30], 80070057h
0x180015b9c  test    rcx, rcx
0x180015b9f  jnz     short loc_180015BE2
0x180015ba1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015ba7  mov     rcx, rax
0x180015baa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015bb1  test    rax, rax
0x180015bb4  jz      short loc_180015BD4
0x180015bb6  mov     rax, [rax]
0x180015bb9  mov     edx, 7F0h
0x180015bbe  mov     rax, [rax+8]
0x180015bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bc7  test    eax, eax
0x180015bc9  jz      short loc_180015BD4
0x180015bcb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015bd2  jmp     short loc_180015BE2
0x180015bd4  lea     rcx, qword_1800D6F70; this
0x180015bdb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015be2  cmp     byte ptr [rcx+8], 0
0x180015be6  jz      short loc_180015C14
0x180015be8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015bed  mov     r9d, [rbp+var_30]; int
0x180015bf1  test    r9d, r9d
0x180015bf4  jns     short loc_180015C14
0x180015bf6  cmp     [rax+7CCh], r9d
0x180015bfd  jz      short loc_180015C14
0x180015bff  mov     r8d, 546h; int
0x180015c05  lea     rdx, aMkvmfsourcelib_26; "MkvMfSourceLib::MkvMfSource::OnRead"
0x180015c0c  mov     rcx, rax; this
0x180015c0f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180015c14  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015c1b  jb      short loc_180015C43
0x180015c1d  mov     edx, 94h
0x180015c22  mov     eax, [rbp+var_30]
0x180015c25  mov     [rsp+60h+var_40], eax
0x180015c29  mov     r9, rsi
0x180015c2c  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180015c33  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c3a  mov     rcx, [rcx+10h]
0x180015c3e  call    WPP_SF_qD
0x180015c43  mov     ebx, [rbp+var_30]
0x180015c46  jmp     loc_180015D2D
0x180015c4b  lea     rdi, [rsi+68h]
0x180015c4f  mov     [rbp+var_18], rdi
0x180015c53  mov     rcx, rdi; lpCriticalSection
0x180015c56  call    cs:__imp_EnterCriticalSection
0x180015c5c  nop
0x180015c5d  cmp     qword ptr [rsi+90h], 0
0x180015c65  jnz     loc_180015D2F
0x180015c6b  mov     [rbp+var_30], 0C00D3E85h
0x180015c72  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015c79  test    rcx, rcx
0x180015c7c  jnz     short loc_180015CBF
0x180015c7e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015c84  mov     rcx, rax
0x180015c87  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015c8e  test    rax, rax
0x180015c91  jz      short loc_180015CB1
0x180015c93  mov     rax, [rax]
0x180015c96  mov     edx, 7F0h
0x180015c9b  mov     rax, [rax+8]
0x180015c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ca4  test    eax, eax
0x180015ca6  jz      short loc_180015CB1
0x180015ca8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015caf  jmp     short loc_180015CBF
0x180015cb1  lea     rcx, qword_1800D6F70; this
0x180015cb8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015cbf  cmp     byte ptr [rcx+8], 0
0x180015cc3  jz      short loc_180015CF1
0x180015cc5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015cca  mov     r9d, [rbp+var_30]; int
0x180015cce  test    r9d, r9d
0x180015cd1  jns     short loc_180015CF1
0x180015cd3  cmp     [rax+7CCh], r9d
0x180015cda  jz      short loc_180015CF1
0x180015cdc  mov     r8d, 54Ch; int
0x180015ce2  lea     rdx, aMkvmfsourcelib_26; "MkvMfSourceLib::MkvMfSource::OnRead"
0x180015ce9  mov     rcx, rax; this
0x180015cec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180015cf1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015cf8  jb      short loc_180015D20
0x180015cfa  mov     edx, 95h
0x180015cff  mov     eax, [rbp+var_30]
0x180015d02  mov     [rsp+60h+var_40], eax
0x180015d06  mov     r9, rsi
0x180015d09  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180015d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d17  mov     rcx, [rcx+10h]
0x180015d1b  call    WPP_SF_qD
0x180015d20  mov     ebx, [rbp+var_30]
0x180015d23  mov     rcx, rdi; lpCriticalSection
0x180015d26  call    cs:__imp_LeaveCriticalSection
0x180015d2c  nop
0x180015d2d  jmp     short loc_180015D97
0x180015d2f  lea     rcx, [rsi+0B8h]; this
0x180015d36  mov     bl, [rcx+8]
0x180015d39  mov     rdx, r14; struct IMFAsyncResult *
0x180015d3c  call    ?AsyncReadCompletion@MkvReader@@QEAAJPEAUIMFAsyncResult@@@Z; MkvReader::AsyncReadCompletion(IMFAsyncResult *)
0x180015d41  mov     [rsi+1E0h], eax
0x180015d47  test    bl, bl
0x180015d49  jz      short loc_180015D80
0x180015d4b  mov     byte ptr [rsi+1E6h], 0
0x180015d52  cmp     byte ptr [rsi+1E5h], 0
0x180015d59  jnz     short loc_180015D72
0x180015d5b  mov     byte ptr [rsi+1E5h], 1
0x180015d62  lea     rdx, [rsi+1F8h]; struct IMFAsyncCallback *
0x180015d69  mov     rcx, rsi; this
0x180015d6c  call    ?QueueOperation@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncCallback@@@Z; MkvMfSourceLib::MkvMfSource::QueueOperation(IMFAsyncCallback *)
0x180015d71  nop
0x180015d72  mov     rcx, rdi; lpCriticalSection
0x180015d75  call    cs:__imp_LeaveCriticalSection
0x180015d7b  nop
0x180015d7c  xor     ebx, ebx
0x180015d7e  jmp     short loc_180015D97
0x180015d80  mov     rdx, r14; struct IMFAsyncResult *
0x180015d83  mov     rcx, rsi; this
0x180015d86  call    ?ProcessAsyncReadOperations@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncResult@@@Z; MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations(IMFAsyncResult *)
0x180015d8b  mov     ebx, eax
0x180015d8d  mov     rcx, rdi; lpCriticalSection
0x180015d90  call    cs:__imp_LeaveCriticalSection
0x180015d96  nop
0x180015d97  lea     rcx, [rbp+var_2C]; this
0x180015d9b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180015da0  mov     eax, ebx
0x180015da2  mov     rcx, [rbp+var_8]
0x180015da6  xor     rcx, rsp; StackCookie
0x180015da9  call    __security_check_cookie
0x180015dae  lea     r11, [rsp+60h+var_s0]
0x180015db3  mov     rbx, [r11+30h]
0x180015db7  mov     rsi, [r11+38h]
0x180015dbb  mov     rsp, r11
0x180015dbe  pop     r14
0x180015dc0  pop     rdi
0x180015dc1  pop     rbp
0x180015dc2  retn
```
