# CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&ushort const * const SaveToFileAsyncOperationName>::OnStart(void)

- ea: `0x100a2cf0`
- end: `0x100a2dc1`
- name: `?OnStart@?$CAsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?SaveToFileAsyncOperationName@@3QBGB@@UAEJXZ`
- size: `209`
- prototype: `HRESULT __thiscall(CAsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,&SaveToFileAsyncOperationName> *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x10067b20`
- `0x100a2cf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x100a2d00`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x100a2d00`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100a2d5b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x100a2d5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a2d0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a2d86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a2d0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100a2d86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a2dae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100a2dae`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x100a2d48`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x100a2d48`

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
0x100a2cf0  mov     edi, edi
0x100a2cf2  push    ebx
0x100a2cf3  push    1F0003h; dwDesiredAccess
0x100a2cf8  push    1; dwFlags
0x100a2cfa  push    0; lpName
0x100a2cfc  push    0; lpEventAttributes
0x100a2cfe  mov     ebx, this
0x100a2d00  call    ds:__imp__CreateEventExW@16; CreateEventExW(x,x,x,x)
0x100a2d06  mov     [ebx+58h], eax
0x100a2d09  test    eax, eax
0x100a2d0b  jnz     short loc_100A2D25
0x100a2d0d  call    ds:__imp__GetLastError@0; GetLastError()
0x100a2d13  test    eax, eax
0x100a2d15  jle     loc_100A2DBF
0x100a2d1b  movzx   eax, ax
0x100a2d1e  or      eax, 80070000h
0x100a2d23  pop     ebx
0x100a2d24  retn
0x100a2d25  lea     this, [ebx-4]
0x100a2d28  mov     eax, [this]
0x100a2d2a  push    esi
0x100a2d2b  push    edi
0x100a2d2c  push    this
0x100a2d2d  mov     esi, [eax+4]
0x100a2d30  mov     this, esi; this
0x100a2d32  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a2d38  call    esi
0x100a2d3a  push    100h; Flags
0x100a2d3f  lea     esi, [ebx-4]
0x100a2d42  push    esi; Context
0x100a2d43  push    offset ?DoWorkStub@?$CAsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@$1?SaveToFileAsyncOperationName@@3QBGB@@KGKPAX@Z; Function
0x100a2d48  call    ds:__imp__QueueUserWorkItem@12; QueueUserWorkItem(x,x,x)
0x100a2d4e  cmp     eax, 1
0x100a2d51  jnz     short loc_100A2D86
0x100a2d53  push    1388h; dwMilliseconds
0x100a2d58  push    dword ptr [ebx+58h]; hHandle
0x100a2d5b  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x100a2d61  test    eax, eax
0x100a2d63  jnz     short loc_100A2D6E
0x100a2d65  mov     edi, [ebx+54h]
0x100a2d68  test    edi, edi
0x100a2d6a  jns     short loc_100A2DAB
0x100a2d6c  jmp     short loc_100A2D9B
0x100a2d6e  mov     eax, [ebx]
0x100a2d70  mov     edi, 8000FFFFh
0x100a2d75  mov     esi, [eax+4Ch]
0x100a2d78  mov     this, esi; this
0x100a2d7a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a2d80  mov     this, ebx
0x100a2d82  call    esi
0x100a2d84  jmp     short Exit_0
0x100a2d86  call    ds:__imp__GetLastError@0; GetLastError()
0x100a2d8c  mov     edi, eax
0x100a2d8e  test    edi, edi
0x100a2d90  jle     short loc_100A2D9B
0x100a2d92  movzx   edi, di
0x100a2d95  or      edi, 80070000h
0x100a2d9b  mov     eax, [esi]
0x100a2d9d  push    esi
0x100a2d9e  mov     esi, [eax+8]
0x100a2da1  mov     this, esi; this
0x100a2da3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a2da9  call    esi
0x100a2dab  push    dword ptr [ebx+58h]; hObject
0x100a2dae  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100a2db4  mov     dword ptr [ebx+58h], 0
0x100a2dbb  mov     eax, edi
0x100a2dbd  pop     edi
0x100a2dbe  pop     esi
0x100a2dbf  pop     ebx
0x100a2dc0  retn
```
