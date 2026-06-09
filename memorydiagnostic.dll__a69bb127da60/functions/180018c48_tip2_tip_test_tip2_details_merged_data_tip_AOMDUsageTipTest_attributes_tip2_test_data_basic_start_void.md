# tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::start(void)

- ea: `0x180018c48`
- end: `0x180018ea2`
- name: `?start@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `602`
- prototype: `_OWORD *__fastcall(__int64 *, _OWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180015010`

## callees

- `0x180002e50`
- `0x180006cb0`
- `0x180007ca4`
- `0x180018680`
- `0x180018c48`
- `0x180019640`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180018e03`
- `KERNEL32!GetModuleHandleW` at `0x180018e03`
- `KERNEL32!GetProcAddress` at `0x180018e1a`
- `KERNEL32!GetProcAddress` at `0x180018e1a`
- `KERNEL32!GetLastError` at `0x180018ddc`
- `KERNEL32!GetLastError` at `0x180018ddc`
- `KERNEL32!LeaveCriticalSection` at `0x180018e6f`
- `KERNEL32!LeaveCriticalSection` at `0x180018e6f`
- `KERNEL32!EnterCriticalSection` at `0x180018d35`
- `KERNEL32!EnterCriticalSection` at `0x180018d35`
- `KERNEL32!SetLastError` at `0x180018e36`
- `KERNEL32!SetLastError` at `0x180018e36`
- `ole32!CoTaskMemFree` at `0x180018cba`
- `ole32!CoTaskMemFree` at `0x180018cf9`
- `ole32!CoTaskMemFree` at `0x180018d22`
- `ole32!CoTaskMemFree` at `0x180018e61`
- `ole32!CoTaskMemFree` at `0x180018cba`
- `ole32!CoTaskMemFree` at `0x180018cf9`
- `ole32!CoTaskMemFree` at `0x180018d22`
- `ole32!CoTaskMemFree` at `0x180018e61`

## string_xrefs

- `0x180018dfc`: `kernelbase.dll`

## pseudocode

```c
_OWORD *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::start(
        __int64 *a1,
        _OWORD *a2)
{
  __int64 v4; // rbx
  __int64 *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  __int64 v9; // rdi
  int v10; // edx
  int v11; // r8d
  char v12; // al
  __int64 v13; // rax
  __int64 v14; // r13
  __int64 v15; // r15
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v21; // [rsp+40h] [rbp-C0h] BYREF
  char v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+49h] [rbp-B7h] BYREF
  char v24; // [rsp+4Dh] [rbp-B3h]
  char v25; // [rsp+4Eh] [rbp-B2h] BYREF
  char v26; // [rsp+849h] [rbp+749h] BYREF
  int *v27; // [rsp+850h] [rbp+750h]
  char *v28; // [rsp+858h] [rbp+758h]
  char *v29; // [rsp+860h] [rbp+760h]

  v4 = *a1;
  if ( *a1 && (*(_QWORD *)(v4 + 248) || (*(_DWORD *)(v4 + 72) & 0x100) != 0) )
  {
    *a1 = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 336), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
  if ( !*a1 )
  {
    v5 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>,>(&pv);
    v6 = *v5;
    *v5 = 0;
    v7 = *a1;
    *a1 = v6;
    if ( v7 && _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 336), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>((struct _RTL_CRITICAL_SECTION *)v7);
      CoTaskMemFree((LPVOID)v7);
    }
    v8 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 84, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(v8);
      CoTaskMemFree(v8);
    }
  }
  v9 = *a1;
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
  v21 = 0;
  v22 = 0;
  v27 = &v23;
  v29 = &v26;
  v23 = -2143256512;
  v24 = 0;
  v28 = &v25;
  if ( (*(_DWORD *)(v9 + 72) & 0x800) == 0 || (v12 = 1, (*(_DWORD *)(v9 + 28) & 0x8000) != 0) )
    v12 = 0;
  if ( v12 )
    v13 = tip2::details::shared_data<0,0,1>::serialize_data((_QWORD *)(v9 + 8), (struct tson::write_buffer *)&v21, 1u);
  else
    v13 = 0;
  LOBYTE(v11) = *(_BYTE *)(v9 + 40);
  v14 = TestCreate(*(_DWORD *)(v9 + 24), v10, v11, *(_DWORD *)(v9 + 28), v13, v9 + 152);
  v15 = *(_QWORD *)(v9 + 248);
  if ( v15 )
  {
    LastError = GetLastError();
    ProcAddress = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
    if ( `TestClose'::`2'::s_pfnTestClose )
      goto LABEL_24;
    ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "TestClose");
    `TestClose'::`2'::s_pfnTestClose = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_24:
      ((void (__fastcall *)(__int64))ProcAddress)(v15);
    SetLastError(LastError);
  }
  *(_QWORD *)(v9 + 248) = v14;
  *(_DWORD *)(v9 + 192) = 1;
  *a2 = *(_OWORD *)(v9 + 152);
  if ( v21 )
    CoTaskMemFree(v21);
  if ( v9 != -200 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
  return a2;
}

```

## disassembly

```asm
0x180018c48  mov     [rsp-8+arg_10], rbx
0x180018c4d  push    rbp
0x180018c4e  push    rsi
0x180018c4f  push    rdi
0x180018c50  push    r12
0x180018c52  push    r13
0x180018c54  push    r14
0x180018c56  push    r15
0x180018c58  lea     rbp, [rsp-780h]
0x180018c60  sub     rsp, 880h
0x180018c67  mov     rax, cs:__security_cookie
0x180018c6e  xor     rax, rsp
0x180018c71  mov     [rbp+7B0h+var_40], rax
0x180018c78  mov     r12, rdx
0x180018c7b  mov     rdi, rcx
0x180018c7e  mov     rbx, [rcx]
0x180018c81  or      esi, 0FFFFFFFFh
0x180018c84  xor     r15d, r15d
0x180018c87  test    rbx, rbx
0x180018c8a  jz      short loc_180018CC0
0x180018c8c  cmp     [rbx+0F8h], r15
0x180018c93  jnz     short loc_180018C9E
0x180018c95  test    dword ptr [rbx+48h], 100h
0x180018c9c  jz      short loc_180018CC0
0x180018c9e  mov     [rcx], r15
0x180018ca1  mov     eax, esi
0x180018ca3  lock xadd [rbx+150h], eax
0x180018cab  add     eax, esi
0x180018cad  jnz     short loc_180018CC0
0x180018caf  mov     rcx, rbx
0x180018cb2  call    ??1?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(void)
0x180018cb7  mov     rcx, rbx; pv
0x180018cba  call    cs:__imp_CoTaskMemFree
0x180018cc0  cmp     [rdi], r15
0x180018cc3  jnz     short loc_180018D28
0x180018cc5  lea     rcx, [rsp+8B0h+pv]
0x180018cca  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>,>(void)
0x180018ccf  mov     rdx, [rax]
0x180018cd2  mov     [rax], r15
0x180018cd5  mov     rbx, [rdi]
0x180018cd8  mov     [rdi], rdx
0x180018cdb  test    rbx, rbx
0x180018cde  jz      short loc_180018CFF
0x180018ce0  mov     eax, esi
0x180018ce2  lock xadd [rbx+150h], eax
0x180018cea  add     eax, esi
0x180018cec  jnz     short loc_180018CFF
0x180018cee  mov     rcx, rbx
0x180018cf1  call    ??1?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(void)
0x180018cf6  mov     rcx, rbx; pv
0x180018cf9  call    cs:__imp_CoTaskMemFree
0x180018cff  mov     rbx, [rsp+8B0h+pv]
0x180018d04  test    rbx, rbx
0x180018d07  jz      short loc_180018D28
0x180018d09  mov     eax, esi
0x180018d0b  lock xadd [rbx+150h], eax
0x180018d13  add     eax, esi
0x180018d15  jnz     short loc_180018D28
0x180018d17  mov     rcx, rbx
0x180018d1a  call    ??1?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(void)
0x180018d1f  mov     rcx, rbx; pv
0x180018d22  call    cs:__imp_CoTaskMemFree
0x180018d28  mov     rdi, [rdi]
0x180018d2b  lea     rsi, [rdi+0C8h]
0x180018d32  mov     rcx, rsi; lpCriticalSection
0x180018d35  call    cs:__imp_EnterCriticalSection
0x180018d3b  mov     [rsp+8B0h+var_870], r15
0x180018d40  mov     [rsp+8B0h+var_868], r15b
0x180018d45  lea     rax, [rsp+8B0h+var_867]
0x180018d4a  mov     [rbp+7B0h+var_60], rax
0x180018d51  lea     rax, [rbp+7B0h+var_67]
0x180018d58  mov     [rbp+7B0h+var_50], rax
0x180018d5f  mov     [rsp+8B0h+var_867], 80408040h
0x180018d67  mov     [rsp+8B0h+var_863], r15b
0x180018d6c  lea     rax, [rsp+8B0h+var_862]
0x180018d71  mov     [rbp+7B0h+var_58], rax
0x180018d78  test    dword ptr [rdi+48h], 800h
0x180018d7f  jz      short loc_180018D8C
0x180018d81  test    dword ptr [rdi+1Ch], 8000h
0x180018d88  mov     al, 1
0x180018d8a  jz      short loc_180018D8F
0x180018d8c  mov     al, r15b
0x180018d8f  lea     r14, [rdi+98h]
0x180018d96  test    al, al
0x180018d98  jz      short loc_180018DB0
0x180018d9a  mov     r8d, 1
0x180018da0  lea     rdx, [rsp+8B0h+var_870]
0x180018da5  lea     rcx, [rdi+8]
0x180018da9  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180018dae  jmp     short loc_180018DB3
0x180018db0  mov     rax, r15
0x180018db3  mov     [rsp+8B0h+var_888], r14
0x180018db8  mov     [rsp+8B0h+var_890], rax
0x180018dbd  mov     r9d, [rdi+1Ch]
0x180018dc1  mov     r8b, [rdi+28h]
0x180018dc5  mov     ecx, [rdi+18h]
0x180018dc8  call    TestCreate
0x180018dcd  mov     r13, rax
0x180018dd0  mov     r15, [rdi+0F8h]
0x180018dd7  test    r15, r15
0x180018dda  jz      short loc_180018E3C
0x180018ddc  call    cs:__imp_GetLastError
0x180018de2  mov     ebx, eax
0x180018de4  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180018deb  test    rax, rax
0x180018dee  jnz     short loc_180018E2C
0x180018df0  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180018df7  test    rax, rax
0x180018dfa  jnz     short loc_180018E10
0x180018dfc  lea     rcx, ModuleName; "kernelbase.dll"
0x180018e03  call    cs:__imp_GetModuleHandleW
0x180018e09  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180018e10  lea     rdx, ProcName; "TestClose"
0x180018e17  mov     rcx, rax; hModule
0x180018e1a  call    cs:__imp_GetProcAddress
0x180018e20  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180018e27  test    rax, rax
0x180018e2a  jz      short loc_180018E34
0x180018e2c  mov     rcx, r15
0x180018e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e34  mov     ecx, ebx; dwErrCode
0x180018e36  call    cs:__imp_SetLastError
0x180018e3c  mov     [rdi+0F8h], r13
0x180018e43  mov     dword ptr [rdi+0C0h], 1
0x180018e4d  movups  xmm0, xmmword ptr [r14]
0x180018e51  movdqu  xmmword ptr [r12], xmm0
0x180018e57  mov     rcx, [rsp+8B0h+var_870]; pv
0x180018e5c  test    rcx, rcx
0x180018e5f  jz      short loc_180018E67
0x180018e61  call    cs:__imp_CoTaskMemFree
0x180018e67  test    rsi, rsi
0x180018e6a  jz      short loc_180018E75
0x180018e6c  mov     rcx, rsi; lpCriticalSection
0x180018e6f  call    cs:__imp_LeaveCriticalSection
0x180018e75  mov     rax, r12
0x180018e78  mov     rcx, [rbp+7B0h+var_40]
0x180018e7f  xor     rcx, rsp; StackCookie
0x180018e82  call    __security_check_cookie
0x180018e87  mov     rbx, [rsp+8B0h+arg_10]
0x180018e8f  add     rsp, 880h
0x180018e96  pop     r15
0x180018e98  pop     r14
0x180018e9a  pop     r13
0x180018e9c  pop     r12
0x180018e9e  pop     rdi
0x180018e9f  pop     rsi
0x180018ea0  pop     rbp
0x180018ea1  retn
```
