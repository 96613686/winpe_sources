# CxCodeVideoProcD3D12DataHandler::EnsureCopyResources(void)

- ea: `0x1800a24e0`
- end: `0x1800a26a1`
- name: `?EnsureCopyResources@CxCodeVideoProcD3D12DataHandler@@IEAAJXZ`
- size: `449`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3D12DataHandler *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800a1800`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x1800a09f0`
- `0x1800a24e0`
- `0x1800be5b8`
- `0x1800bea5c`
- `0x1800d1010`

## string_xrefs

- `0x1800a25b6`: `XVP Copy Command List`
- `0x1800a266e`: `XVP Copy output Sync fence`
- `0x1800a250b`: `CxCodeVideoProcD3D12DataHandler::EnsureCopyResources`
- `0x1800a256c`: `CxCodeVideoProcD3D12DataHandler::EnsureCopyResources`
- `0x1800a2643`: `CxCodeVideoProcD3D12DataHandler::EnsureCopyResources`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D12DataHandler::EnsureCopyResources(
        CxCodeVideoProcD3D12DataHandler *this,
        __int64 a2,
        unsigned int a3)
{
  MFD3D::DX12CommandAllocatorManager *v3; // rbx
  int v5; // ebx
  CallStackTracing *v6; // rcx
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, _QWORD, GUID *, __int64); // rbx
  __int64 v11; // rax
  CallStackTracing *v12; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  char v15; // [rsp+60h] [rbp+8h] BYREF

  v3 = (CxCodeVideoProcD3D12DataHandler *)((char *)this + 4344);
  MFD3D::DX12CommandAllocatorManager::CreateAllocators(
    (CxCodeVideoProcD3D12DataHandler *)((char *)this + 4344),
    D3D12_COMMAND_LIST_TYPE_DIRECT,
    a3,
    *((struct ID3D12Device **)this + 506));
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v15,
    "CxCodeVideoProcD3D12DataHandler::EnsureCopyResources",
    499);
  v5 = MFD3D::DX12CommandListManager<ID3D12GraphicsCommandList,0>::Create(
         (void **)this + 554,
         *((struct ID3D12Device **)this + 506),
         v3);
  if ( v5 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 554) + 48LL))(
      *((_QWORD *)this + 554),
      L"XVP Copy Command List");
    if ( !*((_QWORD *)this + 557) )
    {
      v9 = *((_QWORD *)this + 506);
      v10 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, GUID *, __int64))(*(_QWORD *)v9 + 288LL);
      v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ID3D12Fence>>((char *)this + 4456);
      v5 = v10(v9, 0, 0, &GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76, v11);
      if ( v5 >= 0 )
      {
        (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 557) + 48LL))(
          *((_QWORD *)this + 557),
          L"XVP Copy output Sync fence");
        *((_DWORD *)this + 1116) = 0;
        goto LABEL_20;
      }
      v12 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v12 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v12);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CxCodeVideoProcD3D12DataHandler::EnsureCopyResources",
            504,
            v5);
      }
      if ( g_wppLevels )
      {
        v8 = 22;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v6 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext(v6);
      if ( *((_DWORD *)v7 + 499) != v5 )
        CallStackContext::TraceFailure(v7, "CxCodeVideoProcD3D12DataHandler::EnsureCopyResources", 499, v5);
    }
    if ( g_wppLevels )
    {
      v8 = 21;
LABEL_9:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_dede7ec529653c28119a7df0a5ed8741_Traceguids, this, v5);
    }
  }
LABEL_20:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800a24e0  push    rbx
0x1800a24e2  push    rsi
0x1800a24e3  push    rdi
0x1800a24e4  push    r14
0x1800a24e6  sub     rsp, 38h
0x1800a24ea  mov     r9, [rcx+0FD0h]; struct ID3D12Device *
0x1800a24f1  lea     rbx, [rcx+10F8h]
0x1800a24f8  mov     rsi, rcx
0x1800a24fb  xor     edx, edx; enum D3D12_COMMAND_LIST_TYPE
0x1800a24fd  mov     rcx, rbx; this
0x1800a2500  call    ?CreateAllocators@DX12CommandAllocatorManager@MFD3D@@QEAAJW4D3D12_COMMAND_LIST_TYPE@@IPEAUID3D12Device@@@Z; MFD3D::DX12CommandAllocatorManager::CreateAllocators(D3D12_COMMAND_LIST_TYPE,uint,ID3D12Device *)
0x1800a2505  mov     r14d, 1F3h
0x1800a250b  lea     rdx, aCxcodevideopro_173; "CxCodeVideoProcD3D12DataHandler::Ensure"...
0x1800a2512  mov     r8d, r14d; int
0x1800a2515  lea     rcx, [rsp+58h+arg_0]; this
0x1800a251a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a251f  mov     rdx, [rsi+0FD0h]; struct ID3D12Device *
0x1800a2526  lea     rdi, [rsi+1150h]
0x1800a252d  mov     rcx, rdi; void **
0x1800a2530  mov     r8, rbx; this
0x1800a2533  call    ?Create@?$DX12CommandListManager@UID3D12GraphicsCommandList@@$0A@@MFD3D@@QEAAJPEAUID3D12Device@@PEAVDX12CommandAllocatorManager@2@@Z; MFD3D::DX12CommandListManager<ID3D12GraphicsCommandList,0>::Create(ID3D12Device *,MFD3D::DX12CommandAllocatorManager *)
0x1800a2538  mov     ebx, eax
0x1800a253a  test    eax, eax
0x1800a253c  jns     short loc_1800A25B3
0x1800a253e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a2545  test    rcx, rcx
0x1800a2548  jnz     short loc_1800A2556
0x1800a254a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800a254f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a2556  cmp     byte ptr [rcx+8], 0
0x1800a255a  jz      short loc_1800A257E
0x1800a255c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a2561  cmp     [rax+7CCh], ebx
0x1800a2567  jz      short loc_1800A257E
0x1800a2569  mov     r9d, ebx; int
0x1800a256c  lea     rdx, aCxcodevideopro_173; "CxCodeVideoProcD3D12DataHandler::Ensure"...
0x1800a2573  mov     r8d, r14d; int
0x1800a2576  mov     rcx, rax; this
0x1800a2579  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a257e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a2585  jb      loc_1800A268B
0x1800a258b  mov     edx, 15h
0x1800a2590  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2597  lea     r8, WPP_dede7ec529653c28119a7df0a5ed8741_Traceguids
0x1800a259e  mov     r9, rsi
0x1800a25a1  mov     dword ptr [rsp+58h+var_38], ebx
0x1800a25a5  mov     rcx, [rcx+10h]
0x1800a25a9  call    WPP_SF_qD
0x1800a25ae  jmp     loc_1800A268B
0x1800a25b3  mov     rcx, [rdi]
0x1800a25b6  lea     rdx, aXvpCopyCommand; "XVP Copy Command List"
0x1800a25bd  mov     rax, [rcx]
0x1800a25c0  mov     rax, [rax+30h]
0x1800a25c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a25c9  lea     r14, [rsi+1168h]
0x1800a25d0  cmp     qword ptr [r14], 0
0x1800a25d4  jnz     loc_1800A268B
0x1800a25da  mov     rdi, [rsi+0FD0h]
0x1800a25e1  mov     rcx, r14
0x1800a25e4  mov     rax, [rdi]
0x1800a25e7  mov     rbx, [rax+120h]
0x1800a25ee  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UID3D12Fence@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UID3D12Fence@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ID3D12Fence>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ID3D12Fence>>)
0x1800a25f3  mov     [rsp+58h+var_38], rax
0x1800a25f8  lea     r9, _GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76
0x1800a25ff  mov     rax, rbx
0x1800a2602  xor     r8d, r8d
0x1800a2605  xor     edx, edx
0x1800a2607  mov     rcx, rdi
0x1800a260a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a260f  mov     ebx, eax
0x1800a2611  test    eax, eax
0x1800a2613  jns     short loc_1800A266B
0x1800a2615  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a261c  test    rcx, rcx
0x1800a261f  jnz     short loc_1800A262D
0x1800a2621  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800a2626  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a262d  cmp     byte ptr [rcx+8], 0
0x1800a2631  jz      short loc_1800A2658
0x1800a2633  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a2638  cmp     [rax+7CCh], ebx
0x1800a263e  jz      short loc_1800A2658
0x1800a2640  mov     r9d, ebx; int
0x1800a2643  lea     rdx, aCxcodevideopro_173; "CxCodeVideoProcD3D12DataHandler::Ensure"...
0x1800a264a  mov     r8d, 1F8h; int
0x1800a2650  mov     rcx, rax; this
0x1800a2653  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a2658  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a265f  jb      short loc_1800A268B
0x1800a2661  mov     edx, 16h
0x1800a2666  jmp     loc_1800A2590
0x1800a266b  mov     rcx, [r14]
0x1800a266e  lea     rdx, aXvpCopyOutputS; "XVP Copy output Sync fence"
0x1800a2675  mov     rax, [rcx]
0x1800a2678  mov     rax, [rax+30h]
0x1800a267c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2681  mov     dword ptr [rsi+1170h], 0
0x1800a268b  lea     rcx, [rsp+58h+arg_0]; this
0x1800a2690  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a2695  mov     eax, ebx
0x1800a2697  add     rsp, 38h
0x1800a269b  pop     r14
0x1800a269d  pop     rdi
0x1800a269e  pop     rsi
0x1800a269f  pop     rbx
0x1800a26a0  retn
```
