# CDShowSBEWrapper::Initialize(IPropertyStore *)

- ea: `0x18006a8d0`
- end: `0x18006abd9`
- name: `?Initialize@CDShowSBEWrapper@@UEAAJPEAUIPropertyStore@@@Z`
- size: `777`
- prototype: `__int64 __fastcall(CDShowSBEWrapper *__hidden this, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x180032a50`
- `0x180051ce4`
- `0x18006a8d0`
- `0x180074160`
- `0x180097eb0`
- `0x180099248`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a994`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a994`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18006a978`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18006a978`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a9c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006aa6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ab11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a9c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006aa6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ab11`

## pseudocode

```c
__int64 __fastcall CDShowSBEWrapper::Initialize(CDShowSBEWrapper *this, struct IPropertyStore *a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v4; // ebx
  __int128 v5; // xmm0
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax
  signed int Graph; // ebx
  CallStackTracing *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  CallStackTracing *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  CallStackTracing *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  _BYTE v20[8]; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v21[16]; // [rsp+38h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v20, "CDShowSBEWrapper::Initialize", 139);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 60) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 296LL))(*((_QWORD *)this + 60));
    v5 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 60) + 280LL))(
                      *((_QWORD *)this + 60),
                      v21);
    *((_DWORD *)ThreadRelativeContext + 504) = v4;
    *((_OWORD *)ThreadRelativeContext + 125) = v5;
  }
  ThreadpoolWait = CreateThreadpoolWait(CDShowWrapper::FilterGraphEventCallback, this, 0);
  *((_QWORD *)this + 52) = ThreadpoolWait;
  if ( ThreadpoolWait )
    goto LABEL_18;
  LastError = GetLastError();
  Graph = LastError;
  if ( LastError > 0 )
    Graph = (unsigned __int16)LastError | 0x80070000;
  if ( Graph >= 0 )
  {
LABEL_18:
    Graph = CDShowSBEWrapper::CreateGraph(this);
    if ( Graph >= 0 )
    {
      Graph = CDShowSBEWrapper::RegisterForBroadcastEvents(this);
      if ( Graph < 0 )
      {
        v16 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext(v16);
          if ( *((_DWORD *)v18 + 499) != Graph )
            CallStackContext::TraceFailure(v18, "CDShowSBEWrapper::Initialize", 159, Graph);
        }
        if ( g_wppLevels )
        {
          v12 = 14;
          goto LABEL_40;
        }
      }
    }
    else
    {
      v13 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext(v13);
        if ( *((_DWORD *)v15 + 499) != Graph )
          CallStackContext::TraceFailure(v15, "CDShowSBEWrapper::Initialize", 157, Graph);
      }
      if ( g_wppLevels )
      {
        v12 = 13;
        goto LABEL_40;
      }
    }
  }
  else
  {
    v9 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(v9);
      if ( *((_DWORD *)v11 + 499) != Graph )
        CallStackContext::TraceFailure(v11, "CDShowSBEWrapper::Initialize", 154, Graph);
    }
    if ( g_wppLevels )
    {
      v12 = 12;
LABEL_40:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_37ff27b5f7033090a0d8eec054f7c30c_Traceguids, this, Graph);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v20);
  return (unsigned int)Graph;
}

```

## disassembly

```asm
0x18006a8d0  mov     [rsp+arg_8], rbx
0x18006a8d5  mov     [rsp+arg_10], rsi
0x18006a8da  push    rdi
0x18006a8db  sub     rsp, 50h
0x18006a8df  mov     rax, cs:__security_cookie
0x18006a8e6  xor     rax, rsp
0x18006a8e9  mov     [rsp+58h+var_10], rax
0x18006a8ee  mov     rsi, rcx
0x18006a8f1  lea     rdx, aCdshowsbewrapp_2; "CDShowSBEWrapper::Initialize"
0x18006a8f8  lea     rcx, [rsp+58h+var_28]; this
0x18006a8fd  mov     r8d, 8Bh; int
0x18006a903  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006a908  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006a90f  cmp     byte ptr [rcx+8], 0
0x18006a913  jz      short loc_18006A96B
0x18006a915  cmp     qword ptr [rsi+1E0h], 0
0x18006a91d  jz      short loc_18006A96B
0x18006a91f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006a924  mov     rcx, [rsi+1E0h]
0x18006a92b  mov     rdi, rax
0x18006a92e  mov     rdx, [rcx]
0x18006a931  mov     rax, [rdx+128h]
0x18006a938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a93d  mov     rcx, [rsi+1E0h]
0x18006a944  mov     ebx, eax
0x18006a946  mov     rdx, [rcx]
0x18006a949  mov     rax, [rdx+118h]
0x18006a950  lea     rdx, [rsp+58h+var_20]
0x18006a955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a95a  movups  xmm0, xmmword ptr [rax]
0x18006a95d  mov     [rdi+7E0h], ebx
0x18006a963  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006a96b  xor     r8d, r8d; pcbe
0x18006a96e  lea     rcx, ?FilterGraphEventCallback@CDShowWrapper@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x18006a975  mov     rdx, rsi; pv
0x18006a978  call    cs:__imp_CreateThreadpoolWait
0x18006a97f  nop     dword ptr [rax+rax+00h]
0x18006a984  mov     [rsi+1A0h], rax
0x18006a98b  test    rax, rax
0x18006a98e  jnz     loc_18006AA4C
0x18006a994  call    cs:__imp_GetLastError
0x18006a99b  nop     dword ptr [rax+rax+00h]
0x18006a9a0  mov     ebx, eax
0x18006a9a2  test    eax, eax
0x18006a9a4  jle     short loc_18006A9AF
0x18006a9a6  movzx   ebx, ax
0x18006a9a9  or      ebx, 80070000h
0x18006a9af  test    ebx, ebx
0x18006a9b1  jns     loc_18006AA4C
0x18006a9b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a9be  test    rcx, rcx
0x18006a9c1  jnz     short loc_18006AA0A
0x18006a9c3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006a9ca  nop     dword ptr [rax+rax+00h]
0x18006a9cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a9d6  mov     rcx, rax
0x18006a9d9  test    rax, rax
0x18006a9dc  jz      short loc_18006A9FC
0x18006a9de  mov     rax, [rax]
0x18006a9e1  mov     edx, 7F0h
0x18006a9e6  mov     rax, [rax+8]
0x18006a9ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a9ef  test    eax, eax
0x18006a9f1  jz      short loc_18006A9FC
0x18006a9f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a9fa  jmp     short loc_18006AA0A
0x18006a9fc  lea     rcx, qword_1800EB130; this
0x18006aa03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006aa0a  cmp     byte ptr [rcx+8], 0
0x18006aa0e  jz      short loc_18006AA35
0x18006aa10  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006aa15  cmp     [rax+7CCh], ebx
0x18006aa1b  jz      short loc_18006AA35
0x18006aa1d  mov     r9d, ebx; int
0x18006aa20  lea     rdx, aCdshowsbewrapp_2; "CDShowSBEWrapper::Initialize"
0x18006aa27  mov     r8d, 9Ah; int
0x18006aa2d  mov     rcx, rax; this
0x18006aa30  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006aa35  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006aa3c  jb      loc_18006ABAF
0x18006aa42  mov     edx, 0Ch
0x18006aa47  jmp     loc_18006AB91
0x18006aa4c  mov     rcx, rsi; this
0x18006aa4f  call    ?CreateGraph@CDShowSBEWrapper@@EEAAJXZ; CDShowSBEWrapper::CreateGraph(void)
0x18006aa54  mov     ebx, eax
0x18006aa56  test    eax, eax
0x18006aa58  jns     loc_18006AAF3
0x18006aa5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006aa65  test    rcx, rcx
0x18006aa68  jnz     short loc_18006AAB1
0x18006aa6a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006aa71  nop     dword ptr [rax+rax+00h]
0x18006aa76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006aa7d  mov     rcx, rax
0x18006aa80  test    rax, rax
0x18006aa83  jz      short loc_18006AAA3
0x18006aa85  mov     rax, [rax]
0x18006aa88  mov     edx, 7F0h
0x18006aa8d  mov     rax, [rax+8]
0x18006aa91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa96  test    eax, eax
0x18006aa98  jz      short loc_18006AAA3
0x18006aa9a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006aaa1  jmp     short loc_18006AAB1
0x18006aaa3  lea     rcx, qword_1800EB130; this
0x18006aaaa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006aab1  cmp     byte ptr [rcx+8], 0
0x18006aab5  jz      short loc_18006AADC
0x18006aab7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006aabc  cmp     [rax+7CCh], ebx
0x18006aac2  jz      short loc_18006AADC
0x18006aac4  mov     r9d, ebx; int
0x18006aac7  lea     rdx, aCdshowsbewrapp_2; "CDShowSBEWrapper::Initialize"
0x18006aace  mov     r8d, 9Dh; int
0x18006aad4  mov     rcx, rax; this
0x18006aad7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006aadc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006aae3  jb      loc_18006ABAF
0x18006aae9  mov     edx, 0Dh
0x18006aaee  jmp     loc_18006AB91
0x18006aaf3  mov     rcx, rsi; this
0x18006aaf6  call    ?RegisterForBroadcastEvents@CDShowSBEWrapper@@AEAAJXZ; CDShowSBEWrapper::RegisterForBroadcastEvents(void)
0x18006aafb  mov     ebx, eax
0x18006aafd  test    eax, eax
0x18006aaff  jns     loc_18006ABAF
0x18006ab05  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ab0c  test    rcx, rcx
0x18006ab0f  jnz     short loc_18006AB58
0x18006ab11  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006ab18  nop     dword ptr [rax+rax+00h]
0x18006ab1d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ab24  mov     rcx, rax
0x18006ab27  test    rax, rax
0x18006ab2a  jz      short loc_18006AB4A
0x18006ab2c  mov     rax, [rax]
0x18006ab2f  mov     edx, 7F0h
0x18006ab34  mov     rax, [rax+8]
0x18006ab38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab3d  test    eax, eax
0x18006ab3f  jz      short loc_18006AB4A
0x18006ab41  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ab48  jmp     short loc_18006AB58
0x18006ab4a  lea     rcx, qword_1800EB130; this
0x18006ab51  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ab58  cmp     byte ptr [rcx+8], 0
0x18006ab5c  jz      short loc_18006AB83
0x18006ab5e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006ab63  cmp     [rax+7CCh], ebx
0x18006ab69  jz      short loc_18006AB83
0x18006ab6b  mov     r9d, ebx; int
0x18006ab6e  lea     rdx, aCdshowsbewrapp_2; "CDShowSBEWrapper::Initialize"
0x18006ab75  mov     r8d, 9Fh; int
0x18006ab7b  mov     rcx, rax; this
0x18006ab7e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006ab83  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ab8a  jb      short loc_18006ABAF
0x18006ab8c  mov     edx, 0Eh
0x18006ab91  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ab98  lea     r8, WPP_37ff27b5f7033090a0d8eec054f7c30c_Traceguids
0x18006ab9f  mov     r9, rsi
0x18006aba2  mov     [rsp+58h+var_38], ebx
0x18006aba6  mov     rcx, [rcx+10h]
0x18006abaa  call    WPP_SF_qD
0x18006abaf  lea     rcx, [rsp+58h+var_28]; this
0x18006abb4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006abb9  mov     eax, ebx
0x18006abbb  mov     rcx, [rsp+58h+var_10]
0x18006abc0  xor     rcx, rsp; StackCookie
0x18006abc3  call    __security_check_cookie
0x18006abc8  mov     rbx, [rsp+58h+arg_8]
0x18006abcd  mov     rsi, [rsp+58h+arg_10]
0x18006abd2  add     rsp, 50h
0x18006abd6  pop     rdi
0x18006abd7  retn
```
