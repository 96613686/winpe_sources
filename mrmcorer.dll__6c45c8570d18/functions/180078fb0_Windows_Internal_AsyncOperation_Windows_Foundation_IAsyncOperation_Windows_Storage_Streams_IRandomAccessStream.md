# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::Streams::IRandomAccessStream>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(void)

- ea: `0x180078fb0`
- end: `0x180079070`
- name: `?OnStart@?$AsyncOperation@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@V?$CMarshaledInterfaceResult@UIRandomAccessStream@Streams@Storage@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180057e4c`
- `0x180078fb0`
- `0x1800b7b38`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180078fe7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180078fe7`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180079027`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180079027`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::Streams::IRandomAccessStream>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(
        __int64 a1)
{
  unsigned int v2; // ebx
  DWORD CurrentThreadId; // eax

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 256) + 8LL))(
         *(_QWORD *)(a1 + 256),
         0,
         0,
         a1 + 280);
  if ( (v2 & 0x80000000) != 0 )
  {
LABEL_4:
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      a1,
      v2);
    return v2;
  }
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 336) = CurrentThreadId;
  v2 = SHTaskPoolQueueTask(*(unsigned int *)(a1 + 328), *(unsigned int *)(a1 + 332), CurrentThreadId, 0);
  if ( (v2 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)(a1 + 248) )
    {
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        a1,
        v2);
      return 0;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::Streams::IRandomAccessStream>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
      a1 - 8,
      1,
      v2);
    goto LABEL_4;
  }
  return v2;
}

```

## disassembly

```asm
0x180078fb0  mov     [rsp+arg_0], rbx
0x180078fb5  mov     [rsp+arg_8], rsi
0x180078fba  push    rdi
0x180078fbb  sub     rsp, 30h
0x180078fbf  mov     rdi, rcx
0x180078fc2  xor     r8d, r8d
0x180078fc5  mov     rcx, [rcx+100h]
0x180078fcc  xor     edx, edx
0x180078fce  lea     r9, [rdi+118h]
0x180078fd5  mov     rax, [rcx]
0x180078fd8  mov     rax, [rax+8]
0x180078fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078fe1  mov     ebx, eax
0x180078fe3  test    eax, eax
0x180078fe5  js      short loc_180079045
0x180078fe7  call    cs:__imp_GetCurrentThreadId
0x180078fed  lea     rdx, [rdi+0C8h]
0x180078ff4  mov     [rsp+38h+var_10], 0
0x180078ffd  lea     rcx, [rdi-8]
0x180079001  mov     [rdi+150h], eax
0x180079007  neg     rcx
0x18007900a  mov     ecx, [rdi+148h]
0x180079010  sbb     r8, r8
0x180079013  xor     r9d, r9d
0x180079016  and     r8, rdx
0x180079019  mov     edx, [rdi+14Ch]
0x18007901f  mov     [rsp+38h+var_18], r8
0x180079024  mov     r8d, eax
0x180079027  call    cs:__imp_SHTaskPoolQueueTask
0x18007902d  mov     ebx, eax
0x18007902f  test    eax, eax
0x180079031  js      short loc_180079051
0x180079033  mov     rsi, [rsp+38h+arg_8]
0x180079038  mov     eax, ebx
0x18007903a  mov     rbx, [rsp+38h+arg_0]
0x18007903f  add     rsp, 30h
0x180079043  pop     rdi
0x180079044  retn
0x180079045  mov     edx, ebx
0x180079047  mov     rcx, rdi
0x18007904a  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18007904f  jmp     short loc_180079033
0x180079051  mov     eax, [rdi+0F8h]
0x180079057  test    eax, eax
0x180079059  jnz     loc_1800C4C92
0x18007905f  mov     r8d, ebx
0x180079062  lea     edx, [rax+1]
0x180079065  lea     rcx, [rdi-8]
0x180079069  call    ?_Run@?$AsyncOperation@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@V?$CMarshaledInterfaceResult@UIRandomAccessStream@Streams@Storage@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::Streams::IRandomAccessStream>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)
0x18007906e  jmp     short loc_180079045
0x1800c4c92  mov     edx, ebx
0x1800c4c94  mov     rcx, rdi
0x1800c4c97  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1800c4c9c  xor     ebx, ebx
0x1800c4c9e  jmp     loc_180079033
```
