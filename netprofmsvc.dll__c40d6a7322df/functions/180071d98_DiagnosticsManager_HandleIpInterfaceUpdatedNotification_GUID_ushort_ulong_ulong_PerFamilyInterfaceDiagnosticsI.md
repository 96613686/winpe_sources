# DiagnosticsManager::HandleIpInterfaceUpdatedNotification(_GUID,ushort,ulong,ulong,PerFamilyInterfaceDiagnosticsInfo)

- ea: `0x180071d98`
- end: `0x180071f3e`
- name: `?HandleIpInterfaceUpdatedNotification@DiagnosticsManager@@SAXU_GUID@@GKKUPerFamilyInterfaceDiagnosticsInfo@@@Z`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800270c8`

## callees

- `0x1800097ec`
- `0x180009990`
- `0x18000e190`
- `0x1800713b8`
- `0x180071d98`
- `0x1800a88a0`
- `0x18010e618`
- `0x18010e6bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071ebd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071eee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071ebd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071eee`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180071f03`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180071f03`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180071e2d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180071e2d`

## string_xrefs

- `0x180071df5`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DiagnosticsManager::HandleIpInterfaceUpdatedNotification(
        __int128 *a1,
        __int16 a2,
        int a3,
        int a4,
        __int64 a5)
{
  __int64 v9; // rbx
  const char *v10; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v12; // [rsp+28h] [rbp-A0h]
  __int64 v13; // [rsp+40h] [rbp-88h] BYREF
  __int128 v14; // [rsp+48h] [rbp-80h]
  __int64 v15; // [rsp+58h] [rbp-70h]
  int v16; // [rsp+60h] [rbp-68h]
  __int16 v17; // [rsp+64h] [rbp-64h]
  __int16 v18; // [rsp+66h] [rbp-62h]
  int v19; // [rsp+68h] [rbp-60h]
  LARGE_INTEGER v20; // [rsp+70h] [rbp-58h]
  LARGE_INTEGER PerformanceCount; // [rsp+78h] [rbp-50h] BYREF
  __int128 v22; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v22 = 0;
  std::weak_ptr<DiagnosticsManager>::lock(a1, &v22);
  v9 = v22;
  if ( (_QWORD)v22 )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    HIWORD(v12) = 0;
    LODWORD(v12) = *(_DWORD *)a5;
    WORD2(v12) = *(_WORD *)(a5 + 4);
    v13 = v9;
    v14 = *a1;
    v15 = v12;
    v16 = a3;
    v17 = a2;
    v18 = 0;
    v19 = a4;
    v20 = PerformanceCount;
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, v9 + 1264);
    try
    {
      if ( *(_BYTE *)(v9 + 1528) )
      {
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
      }
      else
      {
        if ( *(_DWORD *)(v9 + 1256) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DiagnosticsManager::HandleIpInterfaceUpdatedNotification_::_3_::_lambda_1___(
            v9 + 1408,
            &v13);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DiagnosticsManager::HandleIpInterfaceUpdatedNotification_::_3_::_lambda_1___(
            v9 + 1488,
            &v13);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        _InterlockedIncrement64((volatile signed __int64 *)(v9 + 1392));
        SubmitThreadpoolWork(*(PTP_WORK *)(v9 + 1384));
      }
      if ( *((_QWORD *)&v22 + 1) )
        std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v22 + 1));
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x2DA,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
        v10);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x2AF,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
      (const char *)0x45B,
      (unsigned int)lpCriticalSection);
    if ( *((_QWORD *)&v22 + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v22 + 1));
  }
}

```

## disassembly

```asm
0x180071d98  mov     r11, rsp
0x180071d9b  push    rbx
0x180071d9c  push    rsi
0x180071d9d  push    rdi
0x180071d9e  push    r14
0x180071da0  push    r15
0x180071da2  sub     rsp, 0A0h
0x180071da9  mov     rax, cs:__security_cookie
0x180071db0  xor     rax, rsp
0x180071db3  mov     [rsp+0C8h+var_38], rax
0x180071dbb  mov     edi, r9d
0x180071dbe  mov     esi, r8d
0x180071dc1  movzx   r14d, dx
0x180071dc5  mov     r15, rcx
0x180071dc8  xorps   xmm0, xmm0
0x180071dcb  movups  xmmword ptr [r11-48h], xmm0
0x180071dd0  lea     rdx, [r11-48h]
0x180071dd4  call    ?lock@?$weak_ptr@VDiagnosticsManager@@@std@@QEBA?AV?$shared_ptr@VDiagnosticsManager@@@2@XZ; std::weak_ptr<DiagnosticsManager>::lock(void)
0x180071dd9  nop
0x180071dda  mov     rbx, [rsp+0C8h+var_48]
0x180071de2  test    rbx, rbx
0x180071de5  jnz     short loc_180071E1F
0x180071de7  mov     rcx, [rsp+0C8h]; this
0x180071def  mov     r9d, 45Bh; char *
0x180071df5  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x180071dfc  mov     edx, 2AFh; void *
0x180071e01  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180071e06  nop
0x180071e07  mov     rcx, [rsp+0C8h+var_40]; this
0x180071e0f  test    rcx, rcx
0x180071e12  jz      short loc_180071E1A
0x180071e14  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071e19  nop
0x180071e1a  jmp     loc_180071F1F
0x180071e1f  mov     qword ptr [rsp+0C8h+PerformanceCount], 0
0x180071e28  lea     rcx, [rsp+0C8h+PerformanceCount]; lpPerformanceCount
0x180071e2d  call    cs:__imp_QueryPerformanceCounter
0x180071e33  xor     eax, eax
0x180071e35  mov     word ptr [rsp+0C8h+var_A0+6], ax
0x180071e3a  xor     edx, edx
0x180071e3c  mov     rcx, [rsp+0C8h+arg_20]
0x180071e44  mov     eax, [rcx]
0x180071e46  mov     dword ptr [rsp+0C8h+var_A0], eax
0x180071e4a  movzx   eax, word ptr [rcx+4]
0x180071e4e  mov     word ptr [rsp+0C8h+var_A0+4], ax
0x180071e53  mov     [rsp+0C8h+var_88], rbx
0x180071e58  movaps  xmm0, xmmword ptr [r15]
0x180071e5c  movdqu  [rsp+0C8h+var_80], xmm0
0x180071e62  mov     rax, [rsp+0C8h+var_A0]
0x180071e67  mov     [rsp+0C8h+var_70], rax
0x180071e6c  mov     [rsp+0C8h+var_68], esi
0x180071e70  mov     [rsp+0C8h+var_64], r14w
0x180071e76  mov     [rsp+0C8h+var_62], dx
0x180071e7b  mov     [rsp+0C8h+var_60], edi
0x180071e7f  mov     eax, dword ptr [rsp+0C8h+PerformanceCount]
0x180071e83  mov     dword ptr [rsp+0C8h+var_58], eax
0x180071e87  mov     eax, dword ptr [rsp+0C8h+PerformanceCount+4]
0x180071e8b  mov     dword ptr [rsp+0C8h+var_58+4], eax
0x180071e8f  mov     [rsp+0C8h+lpCriticalSection], rdx
0x180071e94  lea     rdx, [rbx+4F0h]
0x180071e9b  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x180071ea0  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180071ea5  nop
0x180071ea6  lea     rcx, [rbx+580h]
0x180071ead  cmp     byte ptr [rcx+78h], 0
0x180071eb1  jz      short loc_180071EC5
0x180071eb3  mov     rcx, [rsp+0C8h+lpCriticalSection]; lpCriticalSection
0x180071eb8  test    rcx, rcx
0x180071ebb  jz      short loc_180071F0A
0x180071ebd  call    cs:__imp_LeaveCriticalSection
0x180071ec3  jmp     short loc_180071F0A
0x180071ec5  lea     rdx, [rsp+0C8h+var_88]
0x180071eca  cmp     dword ptr [rbx+4E8h], 1
0x180071ed1  jnz     short loc_180071EDA
0x180071ed3  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DiagnosticsManager__HandleIpInterfaceUpdatedNotification____3____lambda_1___
0x180071ed8  jmp     short loc_180071EE4
0x180071eda  add     rcx, 50h ; 'P'
0x180071ede  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DiagnosticsManager__HandleIpInterfaceUpdatedNotification____3____lambda_1___
0x180071ee3  nop
0x180071ee4  mov     rcx, [rsp+0C8h+lpCriticalSection]; lpCriticalSection
0x180071ee9  test    rcx, rcx
0x180071eec  jz      short loc_180071EF4
0x180071eee  call    cs:__imp_LeaveCriticalSection
0x180071ef4  lock inc qword ptr [rbx+570h]
0x180071efc  mov     rcx, [rbx+568h]; pwk
0x180071f03  call    cs:__imp_SubmitThreadpoolWork
0x180071f09  nop
0x180071f0a  mov     rcx, [rsp+0C8h+var_40]; this
0x180071f12  test    rcx, rcx
0x180071f15  jz      short loc_180071F1D
0x180071f17  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071f1c  nop
0x180071f1d  jmp     short $+2
0x180071f1f  mov     rcx, [rsp+0C8h+var_38]
0x180071f27  xor     rcx, rsp; StackCookie
0x180071f2a  call    __security_check_cookie
0x180071f2f  add     rsp, 0A0h
0x180071f36  pop     r15
0x180071f38  pop     r14
0x180071f3a  pop     rdi
0x180071f3b  pop     rsi
0x180071f3c  pop     rbx
0x180071f3d  retn
```
