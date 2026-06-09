# NetworkPropertyMaps::InternalUpdateNsiTables(std::vector<_GUID,std::allocator<_GUID>>,ulong,tagNLA_SIGNATURE *,_GUID,std::basic_string<char,std::char_traits<char>,std::allocator<char>>)

- ea: `0x180086a28`
- end: `0x180086b9a`
- name: `?InternalUpdateNsiTables@NetworkPropertyMaps@@AEAAXV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@KPEAUtagNLA_SIGNATURE@@U_GUID@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z`
- size: `370`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001f640`
- `0x1800d67ec`

## callees

- `0x180015ab0`
- `0x18001f600`
- `0x18002061c`
- `0x18006df14`
- `0x180086a28`
- `0x1800a88a0`
- `0x1800d4194`
- `0x1800d4238`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180086ad3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180086ad3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180086af3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180086b1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180086af3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180086b1e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180086b33`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180086b33`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NetworkPropertyMaps::InternalUpdateNsiTables(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int128 *a4,
        __int128 *a5,
        __int64 a6)
{
  __int64 v6; // rsi
  __int64 v8; // r14
  int v9; // r11d
  const char *v10; // r9
  __int64 v12; // [rsp+30h] [rbp-C8h] BYREF
  __int128 v13; // [rsp+38h] [rbp-C0h]
  __int128 v14; // [rsp+48h] [rbp-B0h]
  __int128 v15; // [rsp+58h] [rbp-A0h]
  int v16; // [rsp+68h] [rbp-90h]
  _BYTE v17[24]; // [rsp+70h] [rbp-88h] BYREF
  int v18; // [rsp+88h] [rbp-70h]
  __int128 v19; // [rsp+8Ch] [rbp-6Ch]
  _BYTE v20[32]; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v21; // [rsp+C0h] [rbp-38h]
  __int64 v22; // [rsp+C8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v6 = a2;
  v21 = a2;
  v8 = a6;
  v22 = a6;
  v12 = a1;
  v13 = *a4;
  v14 = a4[1];
  v15 = a4[2];
  v16 = *((_DWORD *)a4 + 12);
  std::vector<InterfaceData>::vector<InterfaceData>(v17, a2);
  v18 = v9;
  v19 = *a5;
  std::string::string(v20, a6);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  try
  {
    if ( *(_BYTE *)(a1 + 272) )
    {
      if ( a1 != -8 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    }
    else
    {
      if ( *(_DWORD *)a1 == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__NetworkPropertyMaps::InternalUpdateNsiTables_::_3_::_lambda_1___(
          a1 + 152,
          &v12);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__NetworkPropertyMaps::InternalUpdateNsiTables_::_3_::_lambda_1___(
          a1 + 232,
          &v12);
      if ( a1 != -8 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
      _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
      SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    }
    std::string::~string(v20);
    std::vector<_GUID>::~vector<_GUID>(v17);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xB88,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
      v10);
    v6 = v21;
    v8 = v22;
  }
  std::vector<_GUID>::~vector<_GUID>(v6);
  return std::string::~string(v8);
}

```

## disassembly

```asm
0x180086a28  mov     [rsp+arg_10], rbx
0x180086a2d  push    rsi
0x180086a2e  push    rdi
0x180086a2f  push    r14
0x180086a31  sub     rsp, 0E0h
0x180086a38  mov     rax, cs:__security_cookie
0x180086a3f  xor     rax, rsp
0x180086a42  mov     [rsp+0F8h+var_28], rax
0x180086a4a  mov     r11d, r8d
0x180086a4d  mov     rsi, rdx
0x180086a50  mov     rbx, rcx
0x180086a53  mov     [rsp+0F8h+var_38], rdx
0x180086a5b  mov     r14, [rsp+0F8h+arg_28]
0x180086a63  mov     [rsp+0F8h+var_30], r14
0x180086a6b  mov     [rsp+0F8h+var_C8], rcx
0x180086a70  movups  xmm0, xmmword ptr [r9]
0x180086a74  movups  [rsp+0F8h+var_C0], xmm0
0x180086a79  movups  xmm1, xmmword ptr [r9+10h]
0x180086a7e  movups  [rsp+0F8h+var_B0], xmm1
0x180086a83  movups  xmm0, xmmword ptr [r9+20h]
0x180086a88  movups  [rsp+0F8h+var_A0], xmm0
0x180086a8d  mov     eax, [r9+30h]
0x180086a91  mov     [rsp+0F8h+var_90], eax
0x180086a95  lea     rcx, [rsp+0F8h+var_88]
0x180086a9a  call    ??0?$vector@UInterfaceData@@V?$allocator@UInterfaceData@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<InterfaceData>::vector<InterfaceData>(std::vector<InterfaceData> &&)
0x180086a9f  mov     [rsp+0F8h+var_70], r11d
0x180086aa7  mov     rax, [rsp+0F8h+arg_20]
0x180086aaf  movups  xmm0, xmmword ptr [rax]
0x180086ab2  movdqu  [rsp+0F8h+var_6C], xmm0
0x180086abb  mov     rdx, r14
0x180086abe  lea     rcx, [rsp+0F8h+var_58]
0x180086ac6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x180086acb  nop
0x180086acc  lea     rdi, [rbx+8]
0x180086ad0  mov     rcx, rdi; lpCriticalSection
0x180086ad3  call    cs:__imp_EnterCriticalSection
0x180086ad9  mov     [rsp+0F8h+var_D8], rdi
0x180086ade  lea     rcx, [rbx+98h]
0x180086ae5  cmp     byte ptr [rcx+78h], 0
0x180086ae9  jz      short loc_180086AFB
0x180086aeb  test    rdi, rdi
0x180086aee  jz      short loc_180086B3A
0x180086af0  mov     rcx, rdi; lpCriticalSection
0x180086af3  call    cs:__imp_LeaveCriticalSection
0x180086af9  jmp     short loc_180086B3A
0x180086afb  lea     rdx, [rsp+0F8h+var_C8]
0x180086b00  cmp     dword ptr [rbx], 1
0x180086b03  jnz     short loc_180086B0C
0x180086b05  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__NetworkPropertyMaps__InternalUpdateNsiTables____3____lambda_1___
0x180086b0a  jmp     short loc_180086B16
0x180086b0c  add     rcx, 50h ; 'P'
0x180086b10  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__NetworkPropertyMaps__InternalUpdateNsiTables____3____lambda_1___
0x180086b15  nop
0x180086b16  test    rdi, rdi
0x180086b19  jz      short loc_180086B24
0x180086b1b  mov     rcx, rdi; lpCriticalSection
0x180086b1e  call    cs:__imp_LeaveCriticalSection
0x180086b24  lock inc qword ptr [rbx+88h]
0x180086b2c  mov     rcx, [rbx+80h]; pwk
0x180086b33  call    cs:__imp_SubmitThreadpoolWork
0x180086b39  nop
0x180086b3a  lea     rcx, [rsp+0F8h+var_58]
0x180086b42  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180086b47  lea     rcx, [rsp+0F8h+var_88]
0x180086b4c  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x180086b51  nop
0x180086b52  jmp     short loc_180086B64
0x180086b54  mov     rsi, [rsp+0F8h+var_38]
0x180086b5c  mov     r14, [rsp+0F8h+var_30]
0x180086b64  mov     rcx, rsi
0x180086b67  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x180086b6c  nop
0x180086b6d  mov     rcx, r14
0x180086b70  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180086b75  nop
0x180086b76  mov     rcx, [rsp+0F8h+var_28]
0x180086b7e  xor     rcx, rsp; StackCookie
0x180086b81  call    __security_check_cookie
0x180086b86  mov     rbx, [rsp+0F8h+arg_10]
0x180086b8e  add     rsp, 0E0h
0x180086b95  pop     r14
0x180086b97  pop     rdi
0x180086b98  pop     rsi
0x180086b99  retn
```
