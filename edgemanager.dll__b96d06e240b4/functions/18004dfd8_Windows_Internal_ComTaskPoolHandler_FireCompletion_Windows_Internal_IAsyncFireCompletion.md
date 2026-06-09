# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x18004dfd8`
- end: `0x18004e117`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `319`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180049ad0`

## callees

- `0x1800090b4`
- `0x18000b0ec`
- `0x18002be64`
- `0x180035580`
- `0x18004d97c`
- `0x18004dfd8`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e06f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e06f`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18004e08a`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18004e08a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::_FireCompletion(
        struct Windows::Internal::IAsyncFireCompletion *a1)
{
  __int64 v2; // rdi
  unsigned int v3; // ebp
  __int64 *v4; // rax
  __int64 v5; // rbx
  DWORD CurrentThreadId; // eax
  int v7; // ebx
  bool v8; // bl
  struct Windows::Internal::IAsyncFireCompletion *v10; // [rsp+68h] [rbp+10h] BYREF
  __int64 v11; // [rsp+70h] [rbp+18h] BYREF
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( !*(_BYTE *)(v2 + 8) )
    _dyn_tls_on_demand_init();
  if ( *(int *)(v2 + 12) <= 4 )
    goto LABEL_19;
  v3 = 0;
  v10 = a1;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v10);
  v10 = a1;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v10);
  v4 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
                    &v11,
                    &v10);
  v5 = *v4;
  v12 = *v4;
  *v4 = 0;
  if ( v11 )
  {
    v11 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v7 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v5, 0);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  v8 = v7 >= 0;
  if ( v10 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( a1 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( !v8 )
  {
LABEL_19:
    if ( !*(_BYTE *)(v2 + 8) )
      _dyn_tls_on_demand_init();
    ++*(_DWORD *)(v2 + 12);
    v3 = (*(__int64 (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 24LL))(a1);
    if ( !*(_BYTE *)(v2 + 8) )
      _dyn_tls_on_demand_init();
    --*(_DWORD *)(v2 + 12);
  }
  return v3;
}

```

## disassembly

```asm
0x18004dfd8  mov     [rsp+arg_0], rbx
0x18004dfdd  push    rbp
0x18004dfde  push    rsi
0x18004dfdf  push    rdi
0x18004dfe0  push    r12
0x18004dfe2  push    r15
0x18004dfe4  sub     rsp, 30h
0x18004dfe8  mov     rsi, rcx
0x18004dfeb  mov     edx, cs:_tls_index
0x18004dff1  mov     rax, gs:58h
0x18004dffa  mov     rdi, [rax+rdx*8]
0x18004dffe  mov     r12d, 8
0x18004e004  cmp     byte ptr [r12+rdi], 0
0x18004e009  jnz     short loc_18004E010
0x18004e00b  call    __dyn_tls_on_demand_init
0x18004e010  mov     r15d, 0Ch
0x18004e016  cmp     dword ptr [r15+rdi], 4
0x18004e01b  jle     loc_18004E0D3
0x18004e021  xor     ebp, ebp
0x18004e023  mov     [rsp+58h+arg_8], rsi
0x18004e028  lea     rcx, [rsp+58h+arg_8]
0x18004e02d  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18004e032  mov     [rsp+58h+arg_8], rsi
0x18004e037  lea     rcx, [rsp+58h+arg_8]
0x18004e03c  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18004e041  lea     rdx, [rsp+58h+arg_8]
0x18004e046  lea     rcx, [rsp+58h+arg_10]
0x18004e04b  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x18004e050  mov     rbx, [rax]
0x18004e053  mov     [rsp+58h+arg_18], rbx
0x18004e058  mov     [rax], rbp
0x18004e05b  mov     rcx, [rsp+58h+arg_10]
0x18004e060  test    rcx, rcx
0x18004e063  jz      short loc_18004E06F
0x18004e065  mov     [rsp+58h+arg_10], rbp
0x18004e06a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::Release(void)
0x18004e06f  call    cs:__imp_GetCurrentThreadId
0x18004e075  mov     [rsp+58h+var_30], rbp
0x18004e07a  mov     [rsp+58h+var_38], rbx
0x18004e07f  xor     r9d, r9d
0x18004e082  mov     r8d, eax
0x18004e085  xor     edx, edx
0x18004e087  lea     ecx, [rdx+3]
0x18004e08a  call    cs:__imp_SHTaskPoolQueueTask
0x18004e090  mov     ebx, eax
0x18004e092  lea     rcx, [rsp+58h+arg_18]
0x18004e097  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e09c  nop
0x18004e09d  shr     ebx, 1Fh
0x18004e0a0  xor     bl, 1
0x18004e0a3  mov     rcx, [rsp+58h+arg_8]
0x18004e0a8  test    rcx, rcx
0x18004e0ab  jz      short loc_18004E0BA
0x18004e0ad  mov     rax, [rcx]
0x18004e0b0  mov     rax, [rax+10h]
0x18004e0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0b9  nop
0x18004e0ba  test    rsi, rsi
0x18004e0bd  jz      short loc_18004E0CF
0x18004e0bf  mov     rax, [rsi]
0x18004e0c2  mov     rcx, rsi
0x18004e0c5  mov     rax, [rax+10h]
0x18004e0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0ce  nop
0x18004e0cf  test    bl, bl
0x18004e0d1  jnz     short loc_18004E104
0x18004e0d3  cmp     byte ptr [r12+rdi], 0
0x18004e0d8  jnz     short loc_18004E0DF
0x18004e0da  call    __dyn_tls_on_demand_init
0x18004e0df  inc     dword ptr [r15+rdi]
0x18004e0e3  mov     rax, [rsi]
0x18004e0e6  mov     rcx, rsi
0x18004e0e9  mov     rax, [rax+18h]
0x18004e0ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0f2  mov     ebp, eax
0x18004e0f4  cmp     byte ptr [r12+rdi], 0
0x18004e0f9  jnz     short loc_18004E100
0x18004e0fb  call    __dyn_tls_on_demand_init
0x18004e100  dec     dword ptr [r15+rdi]
0x18004e104  mov     eax, ebp
0x18004e106  mov     rbx, [rsp+58h+arg_0]
0x18004e10b  add     rsp, 30h
0x18004e10f  pop     r15
0x18004e111  pop     r12
0x18004e113  pop     rdi
0x18004e114  pop     rsi
0x18004e115  pop     rbp
0x18004e116  retn
```
