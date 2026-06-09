# CreateFileAsyncCallback::Invoke(IMFAsyncResult *)

- ea: `0x180097fd0`
- end: `0x1800981af`
- name: `?Invoke@CreateFileAsyncCallback@@UEAAJPEAUIMFAsyncResult@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(CreateFileAsyncCallback *__hidden this, struct IMFAsyncResult *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x18000eee0`
- `0x180019124`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x180097fd0`
- `0x1800b18fc`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009800f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009815a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009800f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009815a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009817b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009817b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180098035`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180098035`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098025`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098047`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098167`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098167`

## string_xrefs

- `0x180097fdf`: `CreateFileAsyncCallback::Invoke`
- `0x180098114`: `CreateFileAsyncCallback::Invoke`

## pseudocode

```c
__int64 __fastcall CreateFileAsyncCallback::Invoke(CreateFileAsyncCallback *this, struct IMFAsyncResult *a2)
{
  IUnknown *v4; // rdi
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  signed int File; // ebx
  DWORD CurrentThreadId; // eax
  IUnknown_vtbl *v8; // rax
  signed int LastError; // eax
  __int64 v10; // rax
  CallStackTracing *v11; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackScopeTrace v14; // [rsp+68h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(&v14, "CreateFileAsyncCallback::Invoke", 2419);
  v4 = a2->GetStateNoAddRef(a2);
  v5 = (struct _RTL_CRITICAL_SECTION *)&v4[13];
  EnterCriticalSection((LPCRITICAL_SECTION)&v4[13]);
  if ( LODWORD(v4[19].__vftable) )
  {
    File = 0;
LABEL_17:
    LeaveCriticalSection(v5);
    goto LABEL_18;
  }
  CurrentThreadId = GetCurrentThreadId();
  v8 = (IUnknown_vtbl *)OpenThread(0x1FFFFFu, 0, CurrentThreadId);
  v4[18].__vftable = v8;
  if ( !v8 )
  {
    LastError = GetLastError();
    File = LastError;
    if ( LastError > 0 )
      File = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_17;
  }
  LeaveCriticalSection(v5);
  v10 = CMFBaseStringT<unsigned short>::PContents(&v4[21]);
  File = CMFFile::_CreateFile(
           HIDWORD(v4[19].__vftable),
           LODWORD(v4[20].__vftable),
           HIDWORD(v4[20].__vftable),
           v10,
           -1,
           &v4[24]);
  if ( File >= 0 )
  {
    EnterCriticalSection(v5);
    CloseHandle(v4[18].__vftable);
    v4[18].__vftable = 0;
    goto LABEL_17;
  }
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
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v11);
    if ( ThreadRelativeContext->m_result != File )
      CallStackContext::TraceFailure(ThreadRelativeContext, "CreateFileAsyncCallback::Invoke", 2455, File);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids, this, File);
LABEL_18:
  CAsyncResult::InvokeCallback((struct tagMFASYNCRESULT *)v4, File);
  v4->Release(v4);
  CallStackScopeTrace::~CallStackScopeTrace(&v14);
  return 0;
}

```

## disassembly

```asm
0x180097fd0  push    rbx
0x180097fd2  push    rbp
0x180097fd3  push    rsi
0x180097fd4  push    rdi
0x180097fd5  sub     rsp, 38h
0x180097fd9  mov     rbx, rdx
0x180097fdc  mov     rbp, rcx
0x180097fdf  lea     rdx, aCreatefileasyn; "CreateFileAsyncCallback::Invoke"
0x180097fe6  mov     r8d, 973h; int
0x180097fec  lea     rcx, [rsp+58h+arg_8]; this
0x180097ff1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180097ff6  mov     rax, [rbx]
0x180097ff9  mov     rcx, rbx
0x180097ffc  mov     rax, [rax+38h]
0x180098000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098005  mov     rdi, rax
0x180098008  lea     rsi, [rax+68h]
0x18009800c  mov     rcx, rsi; lpCriticalSection
0x18009800f  call    cs:__imp_EnterCriticalSection
0x180098015  cmp     dword ptr [rdi+98h], 0
0x18009801c  jz      short loc_180098025
0x18009801e  xor     ebx, ebx
0x180098020  jmp     loc_180098178
0x180098025  call    cs:__imp_GetCurrentThreadId
0x18009802b  xor     edx, edx; bInheritHandle
0x18009802d  mov     ecx, 1FFFFFh; dwDesiredAccess
0x180098032  mov     r8d, eax; dwThreadId
0x180098035  call    cs:__imp_OpenThread
0x18009803b  mov     [rdi+90h], rax
0x180098042  test    rax, rax
0x180098045  jnz     short loc_180098065
0x180098047  call    cs:__imp_GetLastError
0x18009804d  mov     ebx, eax
0x18009804f  test    eax, eax
0x180098051  jle     loc_180098178
0x180098057  movzx   ebx, ax
0x18009805a  or      ebx, 80070000h
0x180098060  jmp     loc_180098178
0x180098065  mov     rcx, rsi; lpCriticalSection
0x180098068  call    cs:__imp_LeaveCriticalSection
0x18009806e  lea     rcx, [rdi+0A8h]
0x180098075  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18009807a  mov     r8d, [rdi+0A4h]
0x180098081  lea     rcx, [rdi+0C0h]
0x180098088  mov     edx, [rdi+0A0h]
0x18009808e  mov     r9, rax
0x180098091  mov     [rsp+58h+var_30], rcx
0x180098096  mov     ecx, [rdi+9Ch]
0x18009809c  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFFh
0x1800980a5  call    ?_CreateFile@CMFFile@@SAJW4__MIDL___MIDL_itf_mfobjects_0000_0018_0001@@W4__MIDL___MIDL_itf_mfobjects_0000_0018_0002@@W4__MIDL___MIDL_itf_mfobjects_0000_0018_0003@@PEBGPEAXPEAPEAUIMFByteStream@@@Z; CMFFile::_CreateFile(__MIDL___MIDL_itf_mfobjects_0000_0018_0001,__MIDL___MIDL_itf_mfobjects_0000_0018_0002,__MIDL___MIDL_itf_mfobjects_0000_0018_0003,ushort const *,void *,IMFByteStream * *)
0x1800980aa  mov     ebx, eax
0x1800980ac  test    eax, eax
0x1800980ae  jns     loc_180098157
0x1800980b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800980bb  test    rcx, rcx
0x1800980be  jnz     short loc_1800980FE
0x1800980c0  mov     rdx, cs:stru_1801FC290.__vftable
0x1800980c7  lea     rcx, stru_1801FC290
0x1800980ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800980d5  mov     rax, [rdx+8]
0x1800980d9  mov     edx, 7F0h
0x1800980de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800980e3  test    eax, eax
0x1800980e5  jnz     short loc_1800980F7
0x1800980e7  lea     rcx, stru_1801F8A30
0x1800980ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800980f5  jmp     short loc_1800980FE
0x1800980f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800980fe  cmp     byte ptr [rcx+8], 0
0x180098102  jz      short loc_180098129
0x180098104  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180098109  cmp     [rax+7CCh], ebx
0x18009810f  jz      short loc_180098129
0x180098111  mov     r9d, ebx; int
0x180098114  lea     rdx, aCreatefileasyn; "CreateFileAsyncCallback::Invoke"
0x18009811b  mov     r8d, 997h; int
0x180098121  mov     rcx, rax; this
0x180098124  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180098129  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180098130  jb      short loc_180098181
0x180098132  mov     rcx, cs:WPP_GLOBAL_Control
0x180098139  lea     r8, WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids
0x180098140  mov     edx, 5Eh ; '^'
0x180098145  mov     dword ptr [rsp+58h+var_38], ebx
0x180098149  mov     r9, rbp
0x18009814c  mov     rcx, [rcx+10h]
0x180098150  call    WPP_SF_qD
0x180098155  jmp     short loc_180098181
0x180098157  mov     rcx, rsi; lpCriticalSection
0x18009815a  call    cs:__imp_EnterCriticalSection
0x180098160  mov     rcx, [rdi+90h]; hObject
0x180098167  call    cs:__imp_CloseHandle
0x18009816d  mov     qword ptr [rdi+90h], 0
0x180098178  mov     rcx, rsi; lpCriticalSection
0x18009817b  call    cs:__imp_LeaveCriticalSection
0x180098181  mov     edx, ebx; int
0x180098183  mov     rcx, rdi; struct tagMFASYNCRESULT *
0x180098186  call    ?InvokeCallback@CAsyncResult@@SAXPEAUtagMFASYNCRESULT@@J@Z; CAsyncResult::InvokeCallback(tagMFASYNCRESULT *,long)
0x18009818b  mov     rax, [rdi]
0x18009818e  mov     rcx, rdi
0x180098191  mov     rax, [rax+10h]
0x180098195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009819a  lea     rcx, [rsp+58h+arg_8]; this
0x18009819f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800981a4  xor     eax, eax
0x1800981a6  add     rsp, 38h
0x1800981aa  pop     rdi
0x1800981ab  pop     rsi
0x1800981ac  pop     rbp
0x1800981ad  pop     rbx
0x1800981ae  retn
```
