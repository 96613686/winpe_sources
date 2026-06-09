# CStoreByteStreamRegistrar::RuntimeClassInitialize(void)

- ea: `0x18004cf18`
- end: `0x18004d0f9`
- name: `?RuntimeClassInitialize@CStoreByteStreamRegistrar@@QEAAJXZ`
- size: `481`
- prototype: `__int64 __fastcall(CStoreByteStreamRegistrar *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800589e8`

## callees

- `0x180004870`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18004cf18`
- `0x1800adad8`
- `0x1801768f0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cf37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cf37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d02c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d02c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004cf79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004cf79`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004cf82`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004cf82`
- `CompPkgSup!GetMediaExtensionCommunicationFactory` at `0x18004cf54`
- `CompPkgSup!GetMediaExtensionCommunicationFactory` at `0x18004cf54`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CStoreByteStreamRegistrar::RuntimeClassInitialize(CStoreByteStreamRegistrar *this)
{
  unsigned int v2; // esi
  __int64 v3; // rdi
  int (__fastcall *v4)(__int64, _QWORD, char *); // rbx
  HANDLE CurrentProcess; // rax
  DWORD ProcessId; // eax
  _QWORD *v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rcx
  CallStackTracing *v11; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v13[8]; // [rsp+38h] [rbp-8h] BYREF
  CallStackScopeTrace v14; // [rsp+88h] [rbp+48h] BYREF
  __int64 v15; // [rsp+90h] [rbp+50h] BYREF
  __int64 v16; // [rsp+98h] [rbp+58h] BYREF

  EnterCriticalSection(&CStoreByteStreamRegistrar::s_lock);
  v2 = 0;
  v15 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
  if ( (int)GetMediaExtensionCommunicationFactory(&v15) >= 0 )
  {
    v3 = v15;
    v4 = *(int (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v15 + 88LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 80);
    CurrentProcess = GetCurrentProcess();
    ProcessId = GetProcessId(CurrentProcess);
    if ( v4(v3, ProcessId, (char *)this + 80) >= 0 )
    {
      v7 = (_QWORD *)lambda_3eea67a1cc0dc209d062e9f1c684165f_::_lambda_3eea67a1cc0dc209d062e9f1c684165f_(v13, this);
      MakeAgileCallback_Windows::Foundation::ITypedEventHandler_Windows::Media::MediaExtensionAppServices::MediaExtensionBroker___IInspectable_____lambda_3eea67a1cc0dc209d062e9f1c684165f___(
        &v16,
        *v7);
      CallStackScopeTrace::CallStackScopeTrace(&v14, "CStoreByteStreamRegistrar::RuntimeClassInitialize", 107);
      v8 = v16;
      if ( v16 )
      {
        (*(void (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 10) + 48LL))(
          *((_QWORD *)this + 10),
          v16,
          (char *)this + 88);
        CallStackScopeTrace::~CallStackScopeTrace(&v14);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      else
      {
        v2 = -2147024882;
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
          if ( ThreadRelativeContext->m_result != -2147024882 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CStoreByteStreamRegistrar::RuntimeClassInitialize",
              107,
              -2147024882);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids,
            this,
            -2147024882);
        CallStackScopeTrace::~CallStackScopeTrace(&v14);
      }
    }
  }
  v9 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  LeaveCriticalSection(&CStoreByteStreamRegistrar::s_lock);
  return v2;
}

```

## disassembly

```asm
0x18004cf18  push    rbp
0x18004cf1a  push    rbx
0x18004cf1b  push    rsi
0x18004cf1c  push    rdi
0x18004cf1d  push    r13
0x18004cf1f  push    r14
0x18004cf21  push    r15
0x18004cf23  mov     rbp, rsp
0x18004cf26  sub     rsp, 40h
0x18004cf2a  mov     r14, rcx
0x18004cf2d  lea     r13, ?s_lock@CStoreByteStreamRegistrar@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection CStoreByteStreamRegistrar::s_lock
0x18004cf34  mov     rcx, r13; lpCriticalSection
0x18004cf37  call    cs:__imp_EnterCriticalSection
0x18004cf3d  mov     [rbp+var_10], r13
0x18004cf41  xor     esi, esi
0x18004cf43  mov     [rbp+arg_10], rsi
0x18004cf47  lea     rcx, [rbp+arg_10]
0x18004cf4b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004cf50  lea     rcx, [rbp+arg_10]
0x18004cf54  call    cs:__imp_GetMediaExtensionCommunicationFactory
0x18004cf5a  test    eax, eax
0x18004cf5c  js      loc_18004D00B
0x18004cf62  mov     rdi, [rbp+arg_10]
0x18004cf66  mov     rax, [rdi]
0x18004cf69  mov     rbx, [rax+58h]
0x18004cf6d  lea     r15, [r14+50h]
0x18004cf71  mov     rcx, r15
0x18004cf74  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004cf79  call    cs:__imp_GetCurrentProcess
0x18004cf7f  mov     rcx, rax; Process
0x18004cf82  call    cs:__imp_GetProcessId
0x18004cf88  mov     r8, r15
0x18004cf8b  mov     edx, eax
0x18004cf8d  mov     rcx, rdi
0x18004cf90  mov     rax, rbx
0x18004cf93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf98  test    eax, eax
0x18004cf9a  js      short loc_18004D00B
0x18004cf9c  mov     rdx, r14
0x18004cf9f  lea     rcx, [rbp+var_8]
0x18004cfa3  call    _lambda_3eea67a1cc0dc209d062e9f1c684165f____lambda_3eea67a1cc0dc209d062e9f1c684165f_
0x18004cfa8  mov     rdx, [rax]
0x18004cfab  lea     rcx, [rbp+arg_18]
0x18004cfaf  call    MakeAgileCallback_Windows__Foundation__ITypedEventHandler_Windows__Media__MediaExtensionAppServices__MediaExtensionBroker___IInspectable_____lambda_3eea67a1cc0dc209d062e9f1c684165f___
0x18004cfb4  nop
0x18004cfb5  lea     edi, [rsi+6Bh]
0x18004cfb8  mov     r8d, edi; int
0x18004cfbb  lea     rdx, aCstorebytestre_1; "CStoreByteStreamRegistrar::RuntimeClass"...
0x18004cfc2  lea     rcx, [rbp+arg_8]; this
0x18004cfc6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004cfcb  nop
0x18004cfcc  mov     rbx, [rbp+arg_18]
0x18004cfd0  test    rbx, rbx
0x18004cfd3  jz      short loc_18004D043
0x18004cfd5  mov     rcx, [r15]
0x18004cfd8  mov     rax, [rcx]
0x18004cfdb  lea     r8, [r14+58h]
0x18004cfdf  mov     rdx, rbx
0x18004cfe2  mov     rax, [rax+30h]
0x18004cfe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfeb  nop
0x18004cfec  lea     rcx, [rbp+arg_8]; this
0x18004cff0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004cff5  nop
0x18004cff6  test    rbx, rbx
0x18004cff9  jz      short loc_18004D00B
0x18004cffb  mov     rax, [rbx]
0x18004cffe  mov     rcx, rbx
0x18004d001  mov     rax, [rax+10h]
0x18004d005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d00a  nop
0x18004d00b  mov     rcx, [rbp+arg_10]
0x18004d00f  test    rcx, rcx
0x18004d012  jz      short loc_18004D029
0x18004d014  mov     [rbp+arg_10], 0
0x18004d01c  mov     rdx, [rcx]
0x18004d01f  mov     rax, [rdx+10h]
0x18004d023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d028  nop
0x18004d029  mov     rcx, r13; lpCriticalSection
0x18004d02c  call    cs:__imp_LeaveCriticalSection
0x18004d032  mov     eax, esi
0x18004d034  add     rsp, 40h
0x18004d038  pop     r15
0x18004d03a  pop     r14
0x18004d03c  pop     r13
0x18004d03e  pop     rdi
0x18004d03f  pop     rsi
0x18004d040  pop     rbx
0x18004d041  pop     rbp
0x18004d042  retn
0x18004d043  mov     esi, 8007000Eh
0x18004d048  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d04f  test    rcx, rcx
0x18004d052  jnz     short loc_18004D089
0x18004d054  lea     rcx, stru_1801FC290
0x18004d05b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d062  mov     rax, cs:stru_1801FC290.__vftable
0x18004d069  mov     edx, 7F0h
0x18004d06e  mov     rax, [rax+8]
0x18004d072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d077  test    eax, eax
0x18004d079  jnz     short loc_18004D0CB
0x18004d07b  lea     rcx, stru_1801F8A30; this
0x18004d082  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d089  cmp     byte ptr [rcx+8], 0
0x18004d08d  jnz     short loc_18004D0D4
0x18004d08f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d096  jb      short loc_18004D0BC
0x18004d098  mov     edx, 0Ch
0x18004d09d  mov     [rsp+40h+var_20], esi
0x18004d0a1  mov     r9, r14
0x18004d0a4  lea     r8, WPP_b75d7078c4363b03f2a23387d5361fbc_Traceguids
0x18004d0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d0b2  mov     rcx, [rcx+10h]
0x18004d0b6  call    WPP_SF_qD
0x18004d0bb  nop
0x18004d0bc  lea     rcx, [rbp+arg_8]; this
0x18004d0c0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004d0c5  nop
0x18004d0c6  jmp     loc_18004D00B
0x18004d0cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d0d2  jmp     short loc_18004D089
0x18004d0d4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d0d9  cmp     [rax+7CCh], esi
0x18004d0df  jz      short loc_18004D08F
0x18004d0e1  mov     r9d, esi; int
0x18004d0e4  mov     r8d, edi; int
0x18004d0e7  lea     rdx, aCstorebytestre_1; "CStoreByteStreamRegistrar::RuntimeClass"...
0x18004d0ee  mov     rcx, rax; this
0x18004d0f1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d0f6  jmp     short loc_18004D08F
```
