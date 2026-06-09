# MFD3D12Sync::CreateReadyFence11(ID3D11DeviceContext4 *)

- ea: `0x180067564`
- end: `0x180067975`
- name: `?CreateReadyFence11@MFD3D12Sync@@IEAAJPEAUID3D11DeviceContext4@@@Z`
- size: `1041`
- prototype: `__int64 __fastcall(MFD3D12Sync *__hidden this, struct ID3D11DeviceContext4 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18006bb00`
- `0x18006c880`

## callees

- `0x18002312c`
- `0x180045060`
- `0x18004a11c`
- `0x180056638`
- `0x180066b4c`
- `0x180067564`
- `0x18006dc78`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800676de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067800`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067925`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006793b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800676de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067800`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067925`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006793b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800675a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800675a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006767e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800677a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800678c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006767e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800677a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800678c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006774b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006788c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006774b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006788c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180067635`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180067757`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006787c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180067635`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180067757`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006787c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006795e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006795e`

## string_xrefs

- `0x1800675b2`: `MFD3D12Sync::CreateReadyFence11`
- `0x180067695`: `MFD3D12Sync::CreateReadyFence11`
- `0x1800677b7`: `MFD3D12Sync::CreateReadyFence11`
- `0x1800678dc`: `MFD3D12Sync::CreateReadyFence11`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MFD3D12Sync::CreateReadyFence11(struct _RTL_CRITICAL_SECTION *this, struct ID3D11DeviceContext4 *a2)
{
  int v4; // ebx
  HANDLE *p_OwningThread; // rsi
  struct _RTL_CRITICAL_SECTION *v6; // r15
  CallStackTracing *v7; // rdi
  CallStackContext *v8; // rsi
  DWORD v9; // r12d
  CallStackContext *v10; // rax
  CallStackTracing *v11; // rcx
  __int64 v12; // rax
  void (__stdcall *GetDevice)(ID3D11DeviceContext4 *, ID3D11Device **); // rbx
  CallStackTracing *v14; // rdi
  CallStackContext *v15; // rsi
  DWORD v16; // r12d
  CallStackContext *v17; // rax
  CallStackTracing *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HANDLE, GUID *, HANDLE *); // rbx
  CallStackTracing *v22; // rdi
  CallStackContext *v23; // rsi
  DWORD LastError; // r12d
  CallStackContext *Value; // rax
  CallStackTracing *v26; // rcx
  __int64 v27; // rax
  HANDLE hObject[2]; // [rsp+40h] [rbp-10h] BYREF
  char v30; // [rsp+90h] [rbp+40h] BYREF
  __int64 v31; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v32; // [rsp+A8h] [rbp+58h] BYREF

  v4 = 0;
  hObject[0] = 0;
  p_OwningThread = &this[3].OwningThread;
  if ( !this[3].OwningThread )
  {
    v31 = 0;
    v32 = 0;
    v6 = this + 2;
    hObject[1] = &this[2];
    EnterCriticalSection(this + 2);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v30, "MFD3D12Sync::CreateReadyFence11", 449);
    v4 = (*(__int64 (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD, _QWORD, __int64, _QWORD, HANDLE *))(*(_QWORD *)this[3].DebugInfo + 248LL))(
           this[3].DebugInfo,
           *(_QWORD *)&this[3].LockCount,
           0,
           0x10000000,
           0,
           hObject);
    if ( v4 >= 0 )
    {
      GetDevice = a2->lpVtbl->GetDevice;
      Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v31);
      ((void (__fastcall *)(struct ID3D11DeviceContext4 *, __int64 *))GetDevice)(a2, &v31);
      v4 = Microsoft::WRL::ComPtr<ID3D11Device>::As<ID3D11Device5>(&v31, &v32);
      if ( v4 >= 0 )
      {
        v20 = v32;
        v21 = *(__int64 (__fastcall **)(__int64, HANDLE, GUID *, HANDLE *))(*(_QWORD *)v32 + 536LL);
        Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(p_OwningThread);
        v4 = v21(v20, hObject[0], &GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80, p_OwningThread);
        if ( v4 < 0 )
        {
          v22 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v22 = (CallStackTracing *)&qword_18009CF60;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
          }
          if ( *((_BYTE *)v22 + 8) )
          {
            v23 = (CallStackTracing *)((char *)v22 + 208);
            LastError = GetLastError();
            Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v22 + 3));
            if ( Value )
            {
              v23 = Value;
            }
            else if ( !GetLastError() )
            {
              v26 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v26 = (CallStackTracing *)&qword_18009CF60;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
              }
              v27 = (**(__int64 (__fastcall ***)(CallStackTracing *))v26)(v26);
              if ( v27 )
                v23 = (CallStackContext *)v27;
            }
            SetLastError(LastError);
            if ( *((_DWORD *)v23 + 499) != v4 )
              CallStackContext::TraceFailure(v23, "MFD3D12Sync::CreateReadyFence11", 452, v4);
          }
          if ( g_wppLevels )
            WPP_SF_qd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              86,
              &WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids,
              this,
              v4);
        }
      }
      else
      {
        v14 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)&qword_18009CF60;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          v15 = (CallStackTracing *)((char *)v14 + 208);
          v16 = GetLastError();
          v17 = (CallStackContext *)TlsGetValue(*((_DWORD *)v14 + 3));
          if ( v17 )
          {
            v15 = v17;
          }
          else if ( !GetLastError() )
          {
            v18 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v18 = (CallStackTracing *)&qword_18009CF60;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
            }
            v19 = (**(__int64 (__fastcall ***)(CallStackTracing *))v18)(v18);
            if ( v19 )
              v15 = (CallStackContext *)v19;
          }
          SetLastError(v16);
          if ( *((_DWORD *)v15 + 499) != v4 )
            CallStackContext::TraceFailure(v15, "MFD3D12Sync::CreateReadyFence11", 451, v4);
        }
        if ( g_wppLevels )
          WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids, this, v4);
      }
    }
    else
    {
      v7 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v7 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        v8 = (CallStackTracing *)((char *)v7 + 208);
        v9 = GetLastError();
        v10 = (CallStackContext *)TlsGetValue(*((_DWORD *)v7 + 3));
        if ( v10 )
        {
          v8 = v10;
        }
        else if ( !GetLastError() )
        {
          v11 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v11 = (CallStackTracing *)&qword_18009CF60;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
          }
          v12 = (**(__int64 (__fastcall ***)(CallStackTracing *))v11)(v11);
          if ( v12 )
            v8 = (CallStackContext *)v12;
        }
        SetLastError(v9);
        if ( *((_DWORD *)v8 + 499) != v4 )
          CallStackContext::TraceFailure(v8, "MFD3D12Sync::CreateReadyFence11", 449, v4);
      }
      if ( g_wppLevels )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids, this, v4);
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v30);
    LeaveCriticalSection(v6);
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v31);
    if ( hObject[0] )
      CloseHandle(hObject[0]);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180067564  push    rbp
0x180067566  push    rbx
0x180067567  push    rsi
0x180067568  push    rdi
0x180067569  push    r12
0x18006756b  push    r14
0x18006756d  push    r15
0x18006756f  mov     rbp, rsp
0x180067572  sub     rsp, 50h
0x180067576  mov     rdi, rdx
0x180067579  mov     r14, rcx
0x18006757c  xor     ebx, ebx
0x18006757e  mov     [rbp+hObject], rbx
0x180067582  lea     rsi, [rcx+88h]
0x180067589  cmp     [rsi], rbx
0x18006758c  jnz     loc_180067964
0x180067592  mov     [rbp+arg_10], rbx
0x180067596  mov     [rbp+arg_18], rbx
0x18006759a  lea     r15, [rcx+50h]
0x18006759e  mov     [rbp+var_8], r15
0x1800675a2  mov     rcx, r15; lpCriticalSection
0x1800675a5  call    cs:__imp_EnterCriticalSection
0x1800675ab  nop
0x1800675ac  mov     r8d, 1C1h; int
0x1800675b2  lea     rdx, aMfd3d12syncCre; "MFD3D12Sync::CreateReadyFence11"
0x1800675b9  lea     rcx, [rbp+arg_0]; this
0x1800675bd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800675c2  nop
0x1800675c3  mov     rcx, [r14+78h]
0x1800675c7  mov     rax, [rcx]
0x1800675ca  lea     rdx, [rbp+hObject]
0x1800675ce  mov     [rsp+50h+var_28], rdx
0x1800675d3  mov     [rsp+50h+var_30], rbx
0x1800675d8  mov     r9d, 10000000h
0x1800675de  xor     r8d, r8d
0x1800675e1  mov     rdx, [r14+80h]
0x1800675e8  mov     rax, [rax+0F8h]
0x1800675ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800675f4  mov     ebx, eax
0x1800675f6  test    eax, eax
0x1800675f8  jns     loc_1800676EA
0x1800675fe  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067605  test    rdi, rdi
0x180067608  jnz     short loc_180067618
0x18006760a  lea     rdi, qword_18009CF60
0x180067611  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180067618  cmp     byte ptr [rdi+8], 0
0x18006761c  jz      loc_1800676A4
0x180067622  lea     rsi, [rdi+0D0h]
0x180067629  call    cs:__imp_GetLastError
0x18006762f  mov     r12d, eax
0x180067632  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180067635  call    cs:__imp_TlsGetValue
0x18006763b  test    rax, rax
0x18006763e  jz      short loc_180067645
0x180067640  mov     rsi, rax
0x180067643  jmp     short loc_18006767B
0x180067645  call    cs:__imp_GetLastError
0x18006764b  test    eax, eax
0x18006764d  jnz     short loc_18006767B
0x18006764f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067656  test    rcx, rcx
0x180067659  jnz     short loc_180067669
0x18006765b  lea     rcx, qword_18009CF60
0x180067662  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067669  mov     rax, [rcx]
0x18006766c  mov     rax, [rax]
0x18006766f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067674  test    rax, rax
0x180067677  cmovnz  rsi, rax
0x18006767b  mov     ecx, r12d; dwErrCode
0x18006767e  call    cs:__imp_SetLastError
0x180067684  cmp     [rsi+7CCh], ebx
0x18006768a  jz      short loc_1800676A4
0x18006768c  mov     r9d, ebx; int
0x18006768f  mov     r8d, 1C1h; int
0x180067695  lea     rdx, aMfd3d12syncCre; "MFD3D12Sync::CreateReadyFence11"
0x18006769c  mov     rcx, rsi; this
0x18006769f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800676a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800676ab  jb      short loc_1800676D1
0x1800676ad  mov     edx, 54h ; 'T'
0x1800676b2  mov     dword ptr [rsp+50h+var_30], ebx
0x1800676b6  mov     r9, r14
0x1800676b9  lea     r8, WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids
0x1800676c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800676c7  mov     rcx, [rcx+10h]
0x1800676cb  call    WPP_SF_qd
0x1800676d0  nop
0x1800676d1  lea     rcx, [rbp+arg_0]; this
0x1800676d5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800676da  nop
0x1800676db  mov     rcx, r15; lpCriticalSection
0x1800676de  call    cs:__imp_LeaveCriticalSection
0x1800676e4  nop
0x1800676e5  jmp     loc_180067942
0x1800676ea  mov     rax, [rdi]
0x1800676ed  mov     rbx, [rax+18h]
0x1800676f1  lea     rcx, [rbp+arg_10]
0x1800676f5  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x1800676fa  lea     rdx, [rbp+arg_10]
0x1800676fe  mov     rcx, rdi
0x180067701  mov     rax, rbx
0x180067704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067709  lea     rdx, [rbp+arg_18]
0x18006770d  lea     rcx, [rbp+arg_10]
0x180067711  call    ??$As@UID3D11Device5@@@?$ComPtr@UID3D11Device@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UID3D11Device5@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID3D11Device>::As<ID3D11Device5>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ID3D11Device5>>)
0x180067716  mov     ebx, eax
0x180067718  test    eax, eax
0x18006771a  jns     loc_18006780C
0x180067720  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067727  test    rdi, rdi
0x18006772a  jnz     short loc_18006773A
0x18006772c  lea     rdi, qword_18009CF60
0x180067733  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006773a  cmp     byte ptr [rdi+8], 0
0x18006773e  jz      loc_1800677C6
0x180067744  lea     rsi, [rdi+0D0h]
0x18006774b  call    cs:__imp_GetLastError
0x180067751  mov     r12d, eax
0x180067754  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180067757  call    cs:__imp_TlsGetValue
0x18006775d  test    rax, rax
0x180067760  jz      short loc_180067767
0x180067762  mov     rsi, rax
0x180067765  jmp     short loc_18006779D
0x180067767  call    cs:__imp_GetLastError
0x18006776d  test    eax, eax
0x18006776f  jnz     short loc_18006779D
0x180067771  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067778  test    rcx, rcx
0x18006777b  jnz     short loc_18006778B
0x18006777d  lea     rcx, qword_18009CF60
0x180067784  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006778b  mov     rax, [rcx]
0x18006778e  mov     rax, [rax]
0x180067791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067796  test    rax, rax
0x180067799  cmovnz  rsi, rax
0x18006779d  mov     ecx, r12d; dwErrCode
0x1800677a0  call    cs:__imp_SetLastError
0x1800677a6  cmp     [rsi+7CCh], ebx
0x1800677ac  jz      short loc_1800677C6
0x1800677ae  mov     r9d, ebx; int
0x1800677b1  mov     r8d, 1C3h; int
0x1800677b7  lea     rdx, aMfd3d12syncCre; "MFD3D12Sync::CreateReadyFence11"
0x1800677be  mov     rcx, rsi; this
0x1800677c1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800677c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800677cd  jb      short loc_1800677F3
0x1800677cf  mov     edx, 55h ; 'U'
0x1800677d4  mov     dword ptr [rsp+50h+var_30], ebx
0x1800677d8  mov     r9, r14
0x1800677db  lea     r8, WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids
0x1800677e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800677e9  mov     rcx, [rcx+10h]
0x1800677ed  call    WPP_SF_qd
0x1800677f2  nop
0x1800677f3  lea     rcx, [rbp+arg_0]; this
0x1800677f7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800677fc  nop
0x1800677fd  mov     rcx, r15; lpCriticalSection
0x180067800  call    cs:__imp_LeaveCriticalSection
0x180067806  nop
0x180067807  jmp     loc_180067942
0x18006780c  mov     rdi, [rbp+arg_18]
0x180067810  mov     rax, [rdi]
0x180067813  mov     rbx, [rax+218h]
0x18006781a  mov     rcx, rsi
0x18006781d  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180067822  mov     r9, rsi
0x180067825  lea     r8, _GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80
0x18006782c  mov     rdx, [rbp+hObject]
0x180067830  mov     rcx, rdi
0x180067833  mov     rax, rbx
0x180067836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006783b  mov     ebx, eax
0x18006783d  test    eax, eax
0x18006783f  jns     loc_18006792E
0x180067845  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006784c  test    rdi, rdi
0x18006784f  jnz     short loc_18006785F
0x180067851  lea     rdi, qword_18009CF60
0x180067858  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18006785f  cmp     byte ptr [rdi+8], 0
0x180067863  jz      loc_1800678EB
0x180067869  lea     rsi, [rdi+0D0h]
0x180067870  call    cs:__imp_GetLastError
0x180067876  mov     r12d, eax
0x180067879  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18006787c  call    cs:__imp_TlsGetValue
0x180067882  test    rax, rax
0x180067885  jz      short loc_18006788C
0x180067887  mov     rsi, rax
0x18006788a  jmp     short loc_1800678C2
0x18006788c  call    cs:__imp_GetLastError
0x180067892  test    eax, eax
0x180067894  jnz     short loc_1800678C2
0x180067896  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006789d  test    rcx, rcx
0x1800678a0  jnz     short loc_1800678B0
0x1800678a2  lea     rcx, qword_18009CF60
0x1800678a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800678b0  mov     rax, [rcx]
0x1800678b3  mov     rax, [rax]
0x1800678b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800678bb  test    rax, rax
0x1800678be  cmovnz  rsi, rax
0x1800678c2  mov     ecx, r12d; dwErrCode
0x1800678c5  call    cs:__imp_SetLastError
0x1800678cb  cmp     [rsi+7CCh], ebx
0x1800678d1  jz      short loc_1800678EB
0x1800678d3  mov     r9d, ebx; int
0x1800678d6  mov     r8d, 1C4h; int
0x1800678dc  lea     rdx, aMfd3d12syncCre; "MFD3D12Sync::CreateReadyFence11"
0x1800678e3  mov     rcx, rsi; this
0x1800678e6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800678eb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800678f2  jb      short loc_180067918
0x1800678f4  mov     edx, 56h ; 'V'
0x1800678f9  mov     dword ptr [rsp+50h+var_30], ebx
0x1800678fd  mov     r9, r14
0x180067900  lea     r8, WPP_18b1d8a13eb8310f1056d7c08509d55f_Traceguids
0x180067907  mov     rcx, cs:WPP_GLOBAL_Control
0x18006790e  mov     rcx, [rcx+10h]
0x180067912  call    WPP_SF_qd
0x180067917  nop
0x180067918  lea     rcx, [rbp+arg_0]; this
0x18006791c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180067921  nop
0x180067922  mov     rcx, r15; lpCriticalSection
0x180067925  call    cs:__imp_LeaveCriticalSection
0x18006792b  nop
0x18006792c  jmp     short loc_180067942
0x18006792e  lea     rcx, [rbp+arg_0]; this
0x180067932  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180067937  nop
0x180067938  mov     rcx, r15; lpCriticalSection
0x18006793b  call    cs:__imp_LeaveCriticalSection
0x180067941  nop
0x180067942  lea     rcx, [rbp+arg_18]
0x180067946  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x18006794b  nop
0x18006794c  lea     rcx, [rbp+arg_10]
0x180067950  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180067955  mov     rcx, [rbp+hObject]; hObject
0x180067959  test    rcx, rcx
0x18006795c  jz      short loc_180067964
0x18006795e  call    cs:__imp_CloseHandle
0x180067964  mov     eax, ebx
0x180067966  add     rsp, 50h
0x18006796a  pop     r15
0x18006796c  pop     r14
0x18006796e  pop     r12
0x180067970  pop     rdi
0x180067971  pop     rsi
0x180067972  pop     rbx
0x180067973  pop     rbp
0x180067974  retn
```
