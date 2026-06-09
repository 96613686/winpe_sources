# ClipboardDataObjectTask::~ClipboardDataObjectTask(void)

- ea: `0x180033300`
- end: `0x1800333fb`
- name: `??1ClipboardDataObjectTask@@UEAA@XZ`
- size: `251`
- prototype: `void __fastcall(ClipboardDataObjectTask *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008eaf0`

## callees

- `0x1800085a8`
- `0x180033300`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800333d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800333d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033329`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033329`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800333ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800333ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180033355`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180033355`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180033345`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180033345`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003337c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003337c`

## pseudocode

```c
void __fastcall ClipboardDataObjectTask::~ClipboardDataObjectTask(ClipboardDataObjectTask *this)
{
  bool v1; // zf
  Microsoft::WRL::ComPtr<IOSTaskCompletion> *p_m_spTaskCompletion; // rdi
  IOSTaskCompletion *ptr; // rdx
  _TP_TIMER *ThreadpoolTimer; // rax
  _FILETIME ftTime; // [rsp+30h] [rbp+8h] BYREF

  v1 = this->m_pCancellationTimer == 0;
  this->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::IClipboardTaskCompletion::IUnknown::lpVtbl = (struct IUnknownVtbl *)ClipboardDataObjectTask::`vftable'{for `IClipboardTaskCompletion'};
  this->Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> >::Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase> > >::Microsoft::WRL::FtmBase::Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMarshal>::IMarshal::IUnknown::lpVtbl = (struct IUnknownVtbl *)Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( !v1 )
  {
    if ( this->m_dwCancellationThreadId != GetCurrentThreadId() )
      WaitForThreadpoolTimerCallbacks(this->m_pCancellationTimer, 1);
    CloseThreadpoolTimer(this->m_pCancellationTimer);
    this->m_pCancellationTimer = 0;
  }
  p_m_spTaskCompletion = &this->m_spTaskCompletion;
  ptr = this->m_spTaskCompletion.ptr_;
  if ( ptr )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(ClipboardDataObjectTask::MTATaskCleanupWorker, ptr, 0);
    if ( ThreadpoolTimer )
    {
      p_m_spTaskCompletion->ptr_ = 0;
      ftTime.dwHighDateTime = -1;
      ftTime.dwLowDateTime = -30000000;
      SetThreadpoolTimer(ThreadpoolTimer, &ftTime, 0, 0);
    }
    else
    {
      ((void (__fastcall *)(IOSTaskCompletion *))p_m_spTaskCompletion->ptr_->lpVtbl[1].Release)(p_m_spTaskCompletion->ptr_);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&this->m_spTaskCompletion);
  DeleteCriticalSection(&this->m_CallCS.cs_);
  this->refcount_ = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&this->marshaller_);
}

```

## disassembly

```asm
0x180033300  mov     [rsp+arg_8], rbx
0x180033305  push    rdi
0x180033306  sub     rsp, 20h
0x18003330a  cmp     qword ptr [this+60h], 0
0x18003330f  lea     rax, ??_7ClipboardDataObjectTask@@6BIClipboardTaskCompletion@@@; const ClipboardDataObjectTask::`vftable'{for `IClipboardTaskCompletion'}
0x180033316  mov     [this], rax
0x180033319  mov     rbx, this
0x18003331c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIClipboardTaskCompletion@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClipboardTaskCompletion,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180033323  mov     [this+8], rax
0x180033327  jz      short loc_180033366
0x180033329  call    cs:__imp_GetCurrentThreadId
0x180033330  nop     dword ptr [rax+rax+00h]
0x180033335  mov     edx, [rbx+6Ch]
0x180033338  cmp     edx, eax
0x18003333a  jz      short loc_180033351
0x18003333c  mov     this, [rbx+60h]; pti
0x180033340  mov     edx, 1; fCancelPendingCallbacks
0x180033345  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003334c  nop     dword ptr [rax+rax+00h]
0x180033351  mov     this, [rbx+60h]; pti
0x180033355  call    cs:__imp_CloseThreadpoolTimer
0x18003335c  nop     dword ptr [rax+rax+00h]
0x180033361  and     qword ptr [rbx+60h], 0
0x180033366  lea     rdi, [rbx+78h]
0x18003336a  mov     rdx, [rdi]; pv
0x18003336d  test    rdx, rdx
0x180033370  jz      short loc_1800333C9
0x180033372  xor     r8d, r8d; pcbe
0x180033375  lea     this, ?MTATaskCleanupWorker@ClipboardDataObjectTask@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003337c  call    cs:__imp_CreateThreadpoolTimer
0x180033383  nop     dword ptr [rax+rax+00h]
0x180033388  test    rax, rax
0x18003338b  jz      short loc_1800333BA
0x18003338d  and     qword ptr [rdi], 0
0x180033391  lea     rdx, [rsp+28h+ftTime]; pftDueTime
0x180033396  or      [rsp+28h+ftTime.dwHighDateTime], 0FFFFFFFFh
0x18003339b  xor     r9d, r9d; msWindowLength
0x18003339e  xor     r8d, r8d; msPeriod
0x1800333a1  mov     [rsp+28h+ftTime.dwLowDateTime], 0FE363C80h
0x1800333a9  mov     this, rax; pti
0x1800333ac  call    cs:__imp_SetThreadpoolTimer
0x1800333b3  nop     dword ptr [rax+rax+00h]
0x1800333b8  jmp     short loc_1800333C9
0x1800333ba  mov     this, [rdi]
0x1800333bd  mov     rax, [this]
0x1800333c0  mov     rax, [rax+28h]
0x1800333c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333c9  mov     this, rdi; this
0x1800333cc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800333d1  lea     this, [rbx+30h]; lpCriticalSection
0x1800333d5  call    cs:__imp_DeleteCriticalSection
0x1800333dc  nop     dword ptr [rax+rax+00h]
0x1800333e1  lea     this, [rbx+20h]
0x1800333e5  mov     dword ptr [rbx+2Ch], 0C0000001h
0x1800333ec  mov     rbx, [rsp+28h+arg_8]
0x1800333f1  add     rsp, 20h
0x1800333f5  pop     rdi
0x1800333f6  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
