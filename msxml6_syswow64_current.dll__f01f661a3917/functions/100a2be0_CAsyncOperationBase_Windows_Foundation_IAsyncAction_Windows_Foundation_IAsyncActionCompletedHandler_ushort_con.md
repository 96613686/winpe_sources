# CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&ushort const * const SaveToFileAsyncOperationName>::OnStart(void)

- ea: `0x100a2be0`
- end: `0x100a2cb1`
- name: `?OnStart@?$CAsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?SaveToFileAsyncOperationName@@3QBGB@@UAEJXZ`
- size: `209`
- prototype: `HRESULT __thiscall(CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x10067bc0`
- `0x100a2be0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x100a2bf0`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x100a2bf0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100a2c4b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100a2c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a2bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a2c76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a2bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a2c76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a2c9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a2c9e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x100a2c38`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x100a2c38`

## pseudocode

```c
HRESULT __thiscall CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&unsigned short const * const SaveToFileAsyncOperationName>::OnStart(
        CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> *this)
{
  HANDLE Event; // eax
  HRESULT result; // eax
  signed int v4; // edi
  signed int LastError; // eax

  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  this->_threadInit = (HRESULT)Event;
  if ( Event )
  {
    (*(void (__thiscall **)(_DWORD, volatile int *))(this[-1]._stm._fAbort + 4))(
      *(_DWORD *)(this[-1]._stm._fAbort + 4),
      &this[-1]._stm._fAbort);
    if ( QueueUserWorkItem(
           CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&unsigned short const * const SaveToFileAsyncOperationName>::DoWorkStub,
           (PVOID)&this[-1]._stm._fAbort,
           0x100u) )
    {
      if ( WaitForSingleObject((HANDLE)this->_threadInit, 0x1388u) )
      {
        v4 = -2147418113;
        ((void (__thiscall *)(CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> *))this->Microsoft::WRL::Implements<Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IAsyncAction,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&SaveToFileAsyncOperationName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Windows::Foundation::IAsyncAction::IInspectable::IUnknown::__vftable[1].get_Completed)(this);
        return v4;
      }
      v4 = *(_DWORD *)&this->gap54;
      if ( v4 >= 0 )
      {
LABEL_12:
        CloseHandle((HANDLE)this->_threadInit);
        this->_threadInit = 0;
        return v4;
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    (*(void (__thiscall **)(_DWORD, volatile int *))(this[-1]._stm._fAbort + 8))(
      *(_DWORD *)(this[-1]._stm._fAbort + 8),
      &this[-1]._stm._fAbort);
    goto LABEL_12;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x100a2be0  mov     edi, edi
0x100a2be2  push    ebx
0x100a2be3  push    1F0003h; dwDesiredAccess
0x100a2be8  push    1; dwFlags
0x100a2bea  push    0; lpName
0x100a2bec  push    0; lpEventAttributes
0x100a2bee  mov     ebx, this
0x100a2bf0  call    ds:__imp__CreateEventExW@16; CreateEventExW(x,x,x,x)
0x100a2bf6  mov     [ebx+58h], eax
0x100a2bf9  test    eax, eax
0x100a2bfb  jnz     short loc_100A2C15
0x100a2bfd  call    ds:__imp__GetLastError@0; GetLastError()
0x100a2c03  test    eax, eax
0x100a2c05  jle     loc_100A2CAF
0x100a2c0b  movzx   eax, ax
0x100a2c0e  or      eax, 80070000h
0x100a2c13  pop     ebx
0x100a2c14  retn
0x100a2c15  lea     this, [ebx-4]
0x100a2c18  mov     eax, [this]
0x100a2c1a  push    esi
0x100a2c1b  push    edi
0x100a2c1c  push    this
0x100a2c1d  mov     esi, [eax+4]
0x100a2c20  mov     this, esi; this
0x100a2c22  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a2c28  call    esi
0x100a2c2a  push    100h; Flags
0x100a2c2f  lea     esi, [ebx-4]
0x100a2c32  push    esi; Context
0x100a2c33  push    offset ?DoWorkStub@?$CAsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?SaveToFileAsyncOperationName@@3QBGB@@KGKPAX@Z; Function
0x100a2c38  call    ds:__imp__QueueUserWorkItem@12; QueueUserWorkItem(x,x,x)
0x100a2c3e  cmp     eax, 1
0x100a2c41  jnz     short loc_100A2C76
0x100a2c43  push    1388h; dwMilliseconds
0x100a2c48  push    dword ptr [ebx+58h]; hHandle
0x100a2c4b  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x100a2c51  test    eax, eax
0x100a2c53  jnz     short loc_100A2C5E
0x100a2c55  mov     edi, [ebx+54h]
0x100a2c58  test    edi, edi
0x100a2c5a  jns     short loc_100A2C9B
0x100a2c5c  jmp     short loc_100A2C8B
0x100a2c5e  mov     eax, [ebx]
0x100a2c60  mov     edi, 8000FFFFh
0x100a2c65  mov     esi, [eax+4Ch]
0x100a2c68  mov     this, esi; this
0x100a2c6a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a2c70  mov     this, ebx
0x100a2c72  call    esi
0x100a2c74  jmp     short Exit_0
0x100a2c76  call    ds:__imp__GetLastError@0; GetLastError()
0x100a2c7c  mov     edi, eax
0x100a2c7e  test    edi, edi
0x100a2c80  jle     short loc_100A2C8B
0x100a2c82  movzx   edi, di
0x100a2c85  or      edi, 80070000h
0x100a2c8b  mov     eax, [esi]
0x100a2c8d  push    esi
0x100a2c8e  mov     esi, [eax+8]
0x100a2c91  mov     this, esi; this
0x100a2c93  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a2c99  call    esi
0x100a2c9b  push    dword ptr [ebx+58h]; hObject
0x100a2c9e  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100a2ca4  mov     dword ptr [ebx+58h], 0
0x100a2cab  mov     eax, edi
0x100a2cad  pop     edi
0x100a2cae  pop     esi
0x100a2caf  pop     ebx
0x100a2cb0  retn
```
