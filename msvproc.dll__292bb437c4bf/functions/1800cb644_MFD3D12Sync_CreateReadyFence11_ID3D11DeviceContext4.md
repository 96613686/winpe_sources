# MFD3D12Sync::CreateReadyFence11(ID3D11DeviceContext4 *)

- ea: `0x1800cb644`
- end: `0x1800cb8ab`
- name: `?CreateReadyFence11@MFD3D12Sync@@IEAAJPEAUID3D11DeviceContext4@@@Z`
- size: `615`
- prototype: `__int64 __fastcall(MFD3D12Sync *__hidden this, struct ID3D11DeviceContext4 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800ce3c0`
- `0x1800cebd0`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x1800cacd4`
- `0x1800cb644`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cb682`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cb682`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cb86b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cb86b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb88f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb88f`

## string_xrefs

- `0x1800cb68e`: `MFD3D12Sync::CreateReadyFence11`
- `0x1800cb703`: `MFD3D12Sync::CreateReadyFence11`
- `0x1800cb78f`: `MFD3D12Sync::CreateReadyFence11`
- `0x1800cb81e`: `MFD3D12Sync::CreateReadyFence11`

## pseudocode

```c
__int64 __fastcall MFD3D12Sync::CreateReadyFence11(struct _RTL_CRITICAL_SECTION *this, struct ID3D11DeviceContext4 *a2)
{
  int v2; // ebx
  HANDLE *p_OwningThread; // r15
  struct _RTL_CRITICAL_SECTION *v6; // r14
  CallStackTracing *v7; // rcx
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  void (__stdcall *GetDevice)(ID3D11DeviceContext4 *, ID3D11Device **); // rbx
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HANDLE, GUID *, HANDLE *); // rbx
  CallStackTracing *v15; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  HANDLE hObject[2]; // [rsp+40h] [rbp-10h] BYREF
  char v19; // [rsp+80h] [rbp+30h] BYREF
  __int64 v20; // [rsp+90h] [rbp+40h] BYREF
  __int64 v21; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  p_OwningThread = &this[3].OwningThread;
  hObject[0] = 0;
  if ( this[3].OwningThread )
    return (unsigned int)v2;
  v6 = this + 2;
  v20 = 0;
  v21 = 0;
  EnterCriticalSection(this + 2);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v19, "MFD3D12Sync::CreateReadyFence11", 449);
  v2 = (*(__int64 (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD, _QWORD, __int64, _QWORD, HANDLE *))(*(_QWORD *)this[3].DebugInfo + 248LL))(
         this[3].DebugInfo,
         *(_QWORD *)&this[3].LockCount,
         0,
         0x10000000,
         0,
         hObject);
  if ( v2 >= 0 )
  {
    GetDevice = a2->lpVtbl->GetDevice;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    ((void (__fastcall *)(struct ID3D11DeviceContext4 *, __int64 *))GetDevice)(a2, &v20);
    v2 = Microsoft::WRL::ComPtr<ID3D11Device>::As<ID3D11Device5>(&v20, &v21);
    if ( v2 >= 0 )
    {
      v13 = v21;
      v14 = *(__int64 (__fastcall **)(__int64, HANDLE, GUID *, HANDLE *))(*(_QWORD *)v21 + 536LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(p_OwningThread);
      v2 = v14(v13, hObject[0], &GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80, p_OwningThread);
      if ( v2 >= 0 )
        goto LABEL_27;
      v15 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v15 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v15);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v2 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MFD3D12Sync::CreateReadyFence11", 452, v2);
      }
      if ( !g_wppLevels )
        goto LABEL_27;
      v9 = 86;
    }
    else
    {
      v11 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v11 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext(v11);
        if ( *((_DWORD *)v12 + 499) != v2 )
          CallStackContext::TraceFailure(v12, "MFD3D12Sync::CreateReadyFence11", 451, v2);
      }
      if ( !g_wppLevels )
        goto LABEL_27;
      v9 = 85;
    }
  }
  else
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v7 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)v8 + 499) != v2 )
        CallStackContext::TraceFailure(v8, "MFD3D12Sync::CreateReadyFence11", 449, v2);
    }
    if ( !g_wppLevels )
      goto LABEL_27;
    v9 = 84;
  }
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids, this, v2);
LABEL_27:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v19);
  LeaveCriticalSection(v6);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800cb644  mov     [rsp-28h+arg_8], rbx
0x1800cb649  push    rbp
0x1800cb64a  push    rsi
0x1800cb64b  push    rdi
0x1800cb64c  push    r14
0x1800cb64e  push    r15
0x1800cb650  mov     rbp, rsp
0x1800cb653  sub     rsp, 50h
0x1800cb657  xor     ebx, ebx
0x1800cb659  lea     r15, [rcx+88h]
0x1800cb660  mov     rdi, rdx
0x1800cb663  mov     rsi, rcx
0x1800cb666  mov     [rbp+hObject], rbx
0x1800cb66a  cmp     [r15], rbx
0x1800cb66d  jnz     loc_1800CB895
0x1800cb673  lea     r14, [rcx+50h]
0x1800cb677  mov     [rbp+arg_10], rbx
0x1800cb67b  mov     rcx, r14; lpCriticalSection
0x1800cb67e  mov     [rbp+arg_18], rbx
0x1800cb682  call    cs:__imp_EnterCriticalSection
0x1800cb688  mov     r8d, 1C1h; int
0x1800cb68e  lea     rdx, aMfd3d12syncCre; "MFD3D12Sync::CreateReadyFence11"
0x1800cb695  lea     rcx, [rbp+arg_0]; this
0x1800cb699  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800cb69e  mov     rcx, [rsi+78h]
0x1800cb6a2  lea     rdx, [rbp+hObject]
0x1800cb6a6  mov     [rsp+50h+var_28], rdx
0x1800cb6ab  mov     r9d, 10000000h
0x1800cb6b1  mov     rdx, [rsi+80h]
0x1800cb6b8  xor     r8d, r8d
0x1800cb6bb  mov     [rsp+50h+var_30], rbx
0x1800cb6c0  mov     rax, [rcx]
0x1800cb6c3  mov     rax, [rax+0F8h]
0x1800cb6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb6cf  mov     ebx, eax
0x1800cb6d1  test    eax, eax
0x1800cb6d3  jns     short loc_1800CB72F
0x1800cb6d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb6dc  test    rcx, rcx
0x1800cb6df  jnz     short loc_1800CB6ED
0x1800cb6e1  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cb6e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cb6ed  cmp     byte ptr [rcx+8], 0
0x1800cb6f1  jz      short loc_1800CB718
0x1800cb6f3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cb6f8  cmp     [rax+7CCh], ebx
0x1800cb6fe  jz      short loc_1800CB718
0x1800cb700  mov     r9d, ebx; int
0x1800cb703  lea     rdx, aMfd3d12syncCre; "MFD3D12Sync::CreateReadyFence11"
0x1800cb70a  mov     r8d, 1C1h; int
0x1800cb710  mov     rcx, rax; this
0x1800cb713  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cb718  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb71f  jb      loc_1800CB85F
0x1800cb725  mov     edx, 54h ; 'T'
0x1800cb72a  jmp     loc_1800CB841
0x1800cb72f  mov     rax, [rdi]
0x1800cb732  lea     rcx, [rbp+arg_10]
0x1800cb736  mov     rbx, [rax+18h]
0x1800cb73a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cb73f  lea     rdx, [rbp+arg_10]
0x1800cb743  mov     rcx, rdi
0x1800cb746  mov     rax, rbx
0x1800cb749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb74e  lea     rdx, [rbp+arg_18]
0x1800cb752  lea     rcx, [rbp+arg_10]
0x1800cb756  call    ??$As@UID3D11Device5@@@?$ComPtr@UID3D11Device@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UID3D11Device5@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID3D11Device>::As<ID3D11Device5>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ID3D11Device5>>)
0x1800cb75b  mov     ebx, eax
0x1800cb75d  test    eax, eax
0x1800cb75f  jns     short loc_1800CB7BB
0x1800cb761  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb768  test    rcx, rcx
0x1800cb76b  jnz     short loc_1800CB779
0x1800cb76d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cb772  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cb779  cmp     byte ptr [rcx+8], 0
0x1800cb77d  jz      short loc_1800CB7A4
0x1800cb77f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cb784  cmp     [rax+7CCh], ebx
0x1800cb78a  jz      short loc_1800CB7A4
0x1800cb78c  mov     r9d, ebx; int
0x1800cb78f  lea     rdx, aMfd3d12syncCre; "MFD3D12Sync::CreateReadyFence11"
0x1800cb796  mov     r8d, 1C3h; int
0x1800cb79c  mov     rcx, rax; this
0x1800cb79f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cb7a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb7ab  jb      loc_1800CB85F
0x1800cb7b1  mov     edx, 55h ; 'U'
0x1800cb7b6  jmp     loc_1800CB841
0x1800cb7bb  mov     rdi, [rbp+arg_18]
0x1800cb7bf  mov     rcx, r15
0x1800cb7c2  mov     rax, [rdi]
0x1800cb7c5  mov     rbx, [rax+218h]
0x1800cb7cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cb7d1  mov     rdx, [rbp+hObject]
0x1800cb7d5  lea     r8, _GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80
0x1800cb7dc  mov     r9, r15
0x1800cb7df  mov     rcx, rdi
0x1800cb7e2  mov     rax, rbx
0x1800cb7e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb7ea  mov     ebx, eax
0x1800cb7ec  test    eax, eax
0x1800cb7ee  jns     short loc_1800CB85F
0x1800cb7f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800cb7f7  test    rcx, rcx
0x1800cb7fa  jnz     short loc_1800CB808
0x1800cb7fc  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800cb801  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800cb808  cmp     byte ptr [rcx+8], 0
0x1800cb80c  jz      short loc_1800CB833
0x1800cb80e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800cb813  cmp     [rax+7CCh], ebx
0x1800cb819  jz      short loc_1800CB833
0x1800cb81b  mov     r9d, ebx; int
0x1800cb81e  lea     rdx, aMfd3d12syncCre; "MFD3D12Sync::CreateReadyFence11"
0x1800cb825  mov     r8d, 1C4h; int
0x1800cb82b  mov     rcx, rax; this
0x1800cb82e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800cb833  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb83a  jb      short loc_1800CB85F
0x1800cb83c  mov     edx, 56h ; 'V'
0x1800cb841  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb848  lea     r8, WPP_fb0656c5b13f3c5e1eb6232bc9370e01_Traceguids
0x1800cb84f  mov     r9, rsi
0x1800cb852  mov     dword ptr [rsp+50h+var_30], ebx
0x1800cb856  mov     rcx, [rcx+10h]
0x1800cb85a  call    WPP_SF_qD
0x1800cb85f  lea     rcx, [rbp+arg_0]; this
0x1800cb863  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800cb868  mov     rcx, r14; lpCriticalSection
0x1800cb86b  call    cs:__imp_LeaveCriticalSection
0x1800cb871  lea     rcx, [rbp+arg_18]
0x1800cb875  lea     rdi, [rbp+arg_10]
0x1800cb879  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cb87e  mov     rcx, rdi
0x1800cb881  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cb886  mov     rcx, [rbp+hObject]; hObject
0x1800cb88a  test    rcx, rcx
0x1800cb88d  jz      short loc_1800CB895
0x1800cb88f  call    cs:__imp_CloseHandle
0x1800cb895  mov     eax, ebx
0x1800cb897  mov     rbx, [rsp+50h+arg_8]
0x1800cb89f  add     rsp, 50h
0x1800cb8a3  pop     r15
0x1800cb8a5  pop     r14
0x1800cb8a7  pop     rdi
0x1800cb8a8  pop     rsi
0x1800cb8a9  pop     rbp
0x1800cb8aa  retn
```
