# CAsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Data::Xml::Dom::XmlDocument *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Data::Xml::Dom::XmlDocument *>,0>::OnStart(void)

- ea: `0x1800edb50`
- end: `0x1800edc5a`
- name: `?OnStart@?$CAsyncOperationBase@U?$IAsyncOperation@PEAVXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVXmlDocument@Dom@Xml@Data@Windows@@@23@$0A@@@UEAAJXZ`
- size: `266`
- prototype: `HRESULT __fastcall(CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800edb50`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800edb6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800edb6b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800edbd5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800edbd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edb81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edc13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edb81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edc13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800edc41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800edc41`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800edbbb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800edbbb`

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
0x1800edb50  push    rbx
0x1800edb52  push    rsi
0x1800edb53  push    rdi
0x1800edb54  push    r14
0x1800edb56  sub     rsp, 28h
0x1800edb5a  xor     edx, edx; lpName
0x1800edb5c  mov     rdi, this
0x1800edb5f  xor     ecx, ecx; lpEventAttributes
0x1800edb61  mov     r9d, 1F0003h; dwDesiredAccess
0x1800edb67  lea     r8d, [rdx+1]; dwFlags
0x1800edb6b  call    cs:__imp_CreateEventExW
0x1800edb71  lea     rsi, [rdi-8]
0x1800edb75  mov     [rsi+0A8h], rax
0x1800edb7c  test    rax, rax
0x1800edb7f  jnz     short loc_1800EDB9C
0x1800edb81  call    cs:__imp_GetLastError
0x1800edb87  test    eax, eax
0x1800edb89  jle     loc_1800EDC50
0x1800edb8f  movzx   eax, ax
0x1800edb92  or      eax, 80070000h
0x1800edb97  jmp     loc_1800EDC50
0x1800edb9c  mov     rax, [rsi]
0x1800edb9f  mov     this, rsi
0x1800edba2  mov     rax, [rax+8]
0x1800edba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edbab  mov     r8d, 100h; Flags
0x1800edbb1  lea     this, ?DoWorkStub@?$CAsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?SaveToFileAsyncOperationName@@3QBGB@@KAKPEAX@Z; Function
0x1800edbb8  mov     rdx, rsi; Context
0x1800edbbb  call    cs:__imp_QueueUserWorkItem
0x1800edbc1  cmp     eax, 1
0x1800edbc4  jnz     short loc_1800EDC13
0x1800edbc6  lea     r14, [rdi+0A0h]
0x1800edbcd  mov     edx, 1388h; dwMilliseconds
0x1800edbd2  mov     this, [r14]; hHandle
0x1800edbd5  call    cs:__imp_WaitForSingleObject
0x1800edbdb  test    eax, eax
0x1800edbdd  jnz     short loc_1800EDBFA
0x1800edbdf  mov     ebx, [rdi+98h]
0x1800edbe5  test    ebx, ebx
0x1800edbe7  jns     short loc_1800EDC3E
0x1800edbe9  mov     rax, [rsi]
0x1800edbec  mov     this, rsi
0x1800edbef  mov     rax, [rax+10h]
0x1800edbf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edbf8  jmp     short loc_1800EDC3E
0x1800edbfa  mov     rax, [rdi]
0x1800edbfd  mov     this, rdi
0x1800edc00  mov     ebx, 8000FFFFh
0x1800edc05  mov     rax, [rax+98h]
0x1800edc0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edc11  jmp     short $Exit_0
0x1800edc13  call    cs:__imp_GetLastError
0x1800edc19  mov     ebx, eax
0x1800edc1b  test    eax, eax
0x1800edc1d  jle     short loc_1800EDC28
0x1800edc1f  movzx   ebx, ax
0x1800edc22  or      ebx, 80070000h
0x1800edc28  mov     this, [rsi]
0x1800edc2b  mov     rax, [this+10h]
0x1800edc2f  mov     this, rsi
0x1800edc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edc37  lea     r14, [rdi+0A0h]
0x1800edc3e  mov     this, [r14]; hObject
0x1800edc41  call    cs:__imp_CloseHandle
0x1800edc47  mov     qword ptr [r14], 0
0x1800edc4e  mov     eax, ebx
0x1800edc50  add     rsp, 28h
0x1800edc54  pop     r14
0x1800edc56  pop     rdi
0x1800edc57  pop     rsi
0x1800edc58  pop     rbx
0x1800edc59  retn
```
