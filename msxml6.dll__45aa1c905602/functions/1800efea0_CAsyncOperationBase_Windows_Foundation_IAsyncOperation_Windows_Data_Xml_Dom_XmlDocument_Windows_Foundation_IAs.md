# CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>::OnStart(void)

- ea: `0x1800efea0`
- end: `0x1800effcf`
- name: `?OnStart@?$CAsyncOperationBase@U?$IAsyncOperation@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@23@$0A@@@UEAAJXZ`
- size: `303`
- prototype: `HRESULT __fastcall(CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800efea0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800efebb`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800efebb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800eff37`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800eff37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eff7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eff7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800effaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800effaf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800eff17`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800eff17`

## pseudocode

```c
HRESULT __fastcall CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>::OnStart(
        CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> *this)
{
  HANDLE Event; // rax
  volatile int *p_fAbort; // rsi
  HRESULT result; // eax
  HRESULT *p_threadInit; // r14
  signed int v6; // ebx
  signed int LastError; // eax

  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  p_fAbort = &this[-1]._stm._fAbort;
  *(_QWORD *)&this->_threadInit = Event;
  if ( Event )
  {
    (*(void (__fastcall **)(volatile int *))(*(_QWORD *)p_fAbort + 8LL))(&this[-1]._stm._fAbort);
    if ( QueueUserWorkItem(
           CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&unsigned short const near * const SaveToFileAsyncOperationName>::DoWorkStub,
           (PVOID)&this[-1]._stm._fAbort,
           0x100u) )
    {
      p_threadInit = &this->_threadInit;
      if ( WaitForSingleObject(*(HANDLE *)&this->_threadInit, 0x1388u) )
      {
        v6 = -2147418113;
        ((void (__fastcall *)(CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> *))this->Microsoft::WRL::Implements<Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Windows::Foundation::IAsyncAction::IInspectable::IUnknown::__vftable[1].get_Completed)(this);
        return v6;
      }
      v6 = *(_DWORD *)&this->gap98;
      if ( v6 < 0 )
        (*(void (__fastcall **)(volatile int *))(*(_QWORD *)p_fAbort + 16LL))(&this[-1]._stm._fAbort);
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      (*(void (__fastcall **)(volatile int *))(*(_QWORD *)p_fAbort + 16LL))(&this[-1]._stm._fAbort);
      p_threadInit = &this->_threadInit;
    }
    CloseHandle(*(HANDLE *)p_threadInit);
    *(_QWORD *)p_threadInit = 0;
    return v6;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800efea0  push    rbx
0x1800efea2  push    rsi
0x1800efea3  push    rdi
0x1800efea4  push    r14
0x1800efea6  sub     rsp, 28h
0x1800efeaa  xor     edx, edx; lpName
0x1800efeac  mov     rdi, this
0x1800efeaf  xor     ecx, ecx; lpEventAttributes
0x1800efeb1  mov     r9d, 1F0003h; dwDesiredAccess
0x1800efeb7  lea     r8d, [rdx+1]; dwFlags
0x1800efebb  call    cs:__imp_CreateEventExW
0x1800efec2  nop     dword ptr [rax+rax+00h]
0x1800efec7  lea     rsi, [rdi-8]
0x1800efecb  mov     [rsi+0A8h], rax
0x1800efed2  test    rax, rax
0x1800efed5  jnz     short loc_1800EFEF8
0x1800efed7  call    cs:__imp_GetLastError
0x1800efede  nop     dword ptr [rax+rax+00h]
0x1800efee3  test    eax, eax
0x1800efee5  jle     loc_1800EFFC4
0x1800efeeb  movzx   eax, ax
0x1800efeee  or      eax, 80070000h
0x1800efef3  jmp     loc_1800EFFC4
0x1800efef8  mov     rax, [rsi]
0x1800efefb  mov     this, rsi
0x1800efefe  mov     rax, [rax+8]
0x1800eff02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eff07  mov     r8d, 100h; Flags
0x1800eff0d  lea     this, ?DoWorkStub@?$CAsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?SaveToFileAsyncOperationName@@3QBGB@@KAKPEAX@Z; Function
0x1800eff14  mov     rdx, rsi; Context
0x1800eff17  call    cs:__imp_QueueUserWorkItem
0x1800eff1e  nop     dword ptr [rax+rax+00h]
0x1800eff23  cmp     eax, 1
0x1800eff26  jnz     short loc_1800EFF7B
0x1800eff28  lea     r14, [rdi+0A0h]
0x1800eff2f  mov     edx, 1388h; dwMilliseconds
0x1800eff34  mov     this, [r14]; hHandle
0x1800eff37  call    cs:__imp_WaitForSingleObject
0x1800eff3e  nop     dword ptr [rax+rax+00h]
0x1800eff43  test    eax, eax
0x1800eff45  jnz     short loc_1800EFF62
0x1800eff47  mov     ebx, [rdi+98h]
0x1800eff4d  test    ebx, ebx
0x1800eff4f  jns     short loc_1800EFFAC
0x1800eff51  mov     rax, [rsi]
0x1800eff54  mov     this, rsi
0x1800eff57  mov     rax, [rax+10h]
0x1800eff5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eff60  jmp     short loc_1800EFFAC
0x1800eff62  mov     rax, [rdi]
0x1800eff65  mov     this, rdi
0x1800eff68  mov     ebx, 8000FFFFh
0x1800eff6d  mov     rax, [rax+98h]
0x1800eff74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eff79  jmp     short $Exit_0
0x1800eff7b  call    cs:__imp_GetLastError
0x1800eff82  nop     dword ptr [rax+rax+00h]
0x1800eff87  mov     ebx, eax
0x1800eff89  test    eax, eax
0x1800eff8b  jle     short loc_1800EFF96
0x1800eff8d  movzx   ebx, ax
0x1800eff90  or      ebx, 80070000h
0x1800eff96  mov     this, [rsi]
0x1800eff99  mov     rax, [this+10h]
0x1800eff9d  mov     this, rsi
0x1800effa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800effa5  lea     r14, [rdi+0A0h]
0x1800effac  mov     this, [r14]; hObject
0x1800effaf  call    cs:__imp_CloseHandle
0x1800effb6  nop     dword ptr [rax+rax+00h]
0x1800effbb  mov     qword ptr [r14], 0
0x1800effc2  mov     eax, ebx
0x1800effc4  add     rsp, 28h
0x1800effc8  pop     r14
0x1800effca  pop     rdi
0x1800effcb  pop     rsi
0x1800effcc  pop     rbx
0x1800effcd  retn
```
