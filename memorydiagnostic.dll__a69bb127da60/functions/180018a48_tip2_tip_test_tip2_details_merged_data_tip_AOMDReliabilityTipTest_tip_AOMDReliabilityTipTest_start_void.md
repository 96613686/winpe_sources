# tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::start(void)

- ea: `0x180018a48`
- end: `0x180018c40`
- name: `?start@?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `504`
- prototype: `_OWORD *__fastcall(__int64 *, _OWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180015010`

## callees

- `0x180002e50`
- `0x180007c18`
- `0x180015e38`
- `0x180018844`
- `0x180018a48`
- `0x180019640`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180018ba2`
- `KERNEL32!GetModuleHandleW` at `0x180018ba2`
- `KERNEL32!GetProcAddress` at `0x180018bb9`
- `KERNEL32!GetProcAddress` at `0x180018bb9`
- `KERNEL32!GetLastError` at `0x180018b7b`
- `KERNEL32!GetLastError` at `0x180018b7b`
- `KERNEL32!LeaveCriticalSection` at `0x180018c0d`
- `KERNEL32!LeaveCriticalSection` at `0x180018c0d`
- `KERNEL32!EnterCriticalSection` at `0x180018ad4`
- `KERNEL32!EnterCriticalSection` at `0x180018ad4`
- `KERNEL32!SetLastError` at `0x180018bd5`
- `KERNEL32!SetLastError` at `0x180018bd5`
- `ole32!CoTaskMemFree` at `0x180018ab9`
- `ole32!CoTaskMemFree` at `0x180018bff`
- `ole32!CoTaskMemFree` at `0x180018ab9`
- `ole32!CoTaskMemFree` at `0x180018bff`

## string_xrefs

- `0x180018b9b`: `kernelbase.dll`

## pseudocode

```c
_OWORD *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::start(
        __int64 *a1,
        _OWORD *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdi
  int v6; // edx
  int v7; // r8d
  char v8; // al
  __int64 v9; // rax
  __int64 v10; // r13
  __int64 v11; // r12
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  char v17; // [rsp+48h] [rbp-B8h]
  int v18; // [rsp+49h] [rbp-B7h] BYREF
  char v19; // [rsp+4Dh] [rbp-B3h]
  char v20; // [rsp+4Eh] [rbp-B2h] BYREF
  char v21; // [rsp+849h] [rbp+749h] BYREF
  int *v22; // [rsp+850h] [rbp+750h]
  char *v23; // [rsp+858h] [rbp+758h]
  char *v24; // [rsp+860h] [rbp+760h]

  v4 = *a1;
  if ( *a1 && (*(_QWORD *)(v4 + 248) || (*(_DWORD *)(v4 + 72) & 0x100) != 0) )
  {
    *a1 = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 272), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
  }
  v5 = *tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::ensure_data(a1);
  EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 200));
  pv = 0;
  v17 = 0;
  v22 = &v18;
  v24 = &v21;
  v18 = -2143256512;
  v19 = 0;
  v23 = &v20;
  if ( (*(_DWORD *)(v5 + 72) & 0x800) == 0 || (v8 = 1, (*(_DWORD *)(v5 + 28) & 0x8000) != 0) )
    v8 = 0;
  if ( v8 )
    v9 = tip2::details::shared_data<0,0,0>::serialize_data((__int64 *)(v5 + 8), (struct tson::write_buffer *)&pv, 1u);
  else
    v9 = 0;
  LOBYTE(v7) = *(_BYTE *)(v5 + 40);
  v10 = TestCreate(*(_DWORD *)(v5 + 24), v6, v7, *(_DWORD *)(v5 + 28), v9, v5 + 152);
  v11 = *(_QWORD *)(v5 + 248);
  if ( v11 )
  {
    LastError = GetLastError();
    ProcAddress = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
    if ( `TestClose'::`2'::s_pfnTestClose )
      goto LABEL_17;
    ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "TestClose");
    `TestClose'::`2'::s_pfnTestClose = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_17:
      ((void (__fastcall *)(__int64))ProcAddress)(v11);
    SetLastError(LastError);
  }
  *(_QWORD *)(v5 + 248) = v10;
  *(_DWORD *)(v5 + 192) = 1;
  *a2 = *(_OWORD *)(v5 + 152);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v5 != -200 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 200));
  return a2;
}

```

## disassembly

```asm
0x180018a48  mov     [rsp-8+arg_10], rbx
0x180018a4d  push    rbp
0x180018a4e  push    rsi
0x180018a4f  push    rdi
0x180018a50  push    r12
0x180018a52  push    r13
0x180018a54  push    r14
0x180018a56  push    r15
0x180018a58  lea     rbp, [rsp-780h]
0x180018a60  sub     rsp, 880h
0x180018a67  mov     rax, cs:__security_cookie
0x180018a6e  xor     rax, rsp
0x180018a71  mov     [rbp+7B0h+var_40], rax
0x180018a78  mov     r14, rdx
0x180018a7b  mov     rdi, rcx
0x180018a7e  mov     rbx, [rcx]
0x180018a81  xor     r12d, r12d
0x180018a84  test    rbx, rbx
0x180018a87  jz      short loc_180018ABF
0x180018a89  cmp     [rbx+0F8h], r12
0x180018a90  jnz     short loc_180018A9B
0x180018a92  test    dword ptr [rbx+48h], 100h
0x180018a99  jz      short loc_180018ABF
0x180018a9b  mov     [rcx], r12
0x180018a9e  or      eax, 0FFFFFFFFh
0x180018aa1  lock xadd [rbx+110h], eax
0x180018aa9  cmp     eax, 1
0x180018aac  jnz     short loc_180018ABF
0x180018aae  mov     rcx, rbx
0x180018ab1  call    ??1?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(void)
0x180018ab6  mov     rcx, rbx; pv
0x180018ab9  call    cs:__imp_CoTaskMemFree
0x180018abf  mov     rcx, rdi
0x180018ac2  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::ensure_data(void)
0x180018ac7  mov     rdi, [rax]
0x180018aca  lea     rsi, [rdi+0C8h]
0x180018ad1  mov     rcx, rsi; lpCriticalSection
0x180018ad4  call    cs:__imp_EnterCriticalSection
0x180018ada  mov     [rsp+8B0h+pv], r12
0x180018adf  mov     [rsp+8B0h+var_868], r12b
0x180018ae4  lea     rax, [rsp+8B0h+var_867]
0x180018ae9  mov     [rbp+7B0h+var_60], rax
0x180018af0  lea     rax, [rbp+7B0h+var_67]
0x180018af7  mov     [rbp+7B0h+var_50], rax
0x180018afe  mov     [rsp+8B0h+var_867], 80408040h
0x180018b06  mov     [rsp+8B0h+var_863], r12b
0x180018b0b  lea     rax, [rsp+8B0h+var_862]
0x180018b10  mov     [rbp+7B0h+var_58], rax
0x180018b17  test    dword ptr [rdi+48h], 800h
0x180018b1e  jz      short loc_180018B2B
0x180018b20  test    dword ptr [rdi+1Ch], 8000h
0x180018b27  mov     al, 1
0x180018b29  jz      short loc_180018B2E
0x180018b2b  mov     al, r12b
0x180018b2e  lea     r15, [rdi+98h]
0x180018b35  test    al, al
0x180018b37  jz      short loc_180018B4F
0x180018b39  mov     r8d, 1
0x180018b3f  lea     rdx, [rsp+8B0h+pv]
0x180018b44  lea     rcx, [rdi+8]
0x180018b48  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180018b4d  jmp     short loc_180018B52
0x180018b4f  mov     rax, r12
0x180018b52  mov     [rsp+8B0h+var_888], r15
0x180018b57  mov     [rsp+8B0h+var_890], rax
0x180018b5c  mov     r9d, [rdi+1Ch]
0x180018b60  mov     r8b, [rdi+28h]
0x180018b64  mov     ecx, [rdi+18h]
0x180018b67  call    TestCreate
0x180018b6c  mov     r13, rax
0x180018b6f  mov     r12, [rdi+0F8h]
0x180018b76  test    r12, r12
0x180018b79  jz      short loc_180018BDB
0x180018b7b  call    cs:__imp_GetLastError
0x180018b81  mov     ebx, eax
0x180018b83  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180018b8a  test    rax, rax
0x180018b8d  jnz     short loc_180018BCB
0x180018b8f  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180018b96  test    rax, rax
0x180018b99  jnz     short loc_180018BAF
0x180018b9b  lea     rcx, ModuleName; "kernelbase.dll"
0x180018ba2  call    cs:__imp_GetModuleHandleW
0x180018ba8  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180018baf  lea     rdx, ProcName; "TestClose"
0x180018bb6  mov     rcx, rax; hModule
0x180018bb9  call    cs:__imp_GetProcAddress
0x180018bbf  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180018bc6  test    rax, rax
0x180018bc9  jz      short loc_180018BD3
0x180018bcb  mov     rcx, r12
0x180018bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bd3  mov     ecx, ebx; dwErrCode
0x180018bd5  call    cs:__imp_SetLastError
0x180018bdb  mov     [rdi+0F8h], r13
0x180018be2  mov     dword ptr [rdi+0C0h], 1
0x180018bec  movups  xmm0, xmmword ptr [r15]
0x180018bf0  movdqu  xmmword ptr [r14], xmm0
0x180018bf5  mov     rcx, [rsp+8B0h+pv]; pv
0x180018bfa  test    rcx, rcx
0x180018bfd  jz      short loc_180018C05
0x180018bff  call    cs:__imp_CoTaskMemFree
0x180018c05  test    rsi, rsi
0x180018c08  jz      short loc_180018C13
0x180018c0a  mov     rcx, rsi; lpCriticalSection
0x180018c0d  call    cs:__imp_LeaveCriticalSection
0x180018c13  mov     rax, r14
0x180018c16  mov     rcx, [rbp+7B0h+var_40]
0x180018c1d  xor     rcx, rsp; StackCookie
0x180018c20  call    __security_check_cookie
0x180018c25  mov     rbx, [rsp+8B0h+arg_10]
0x180018c2d  add     rsp, 880h
0x180018c34  pop     r15
0x180018c36  pop     r14
0x180018c38  pop     r13
0x180018c3a  pop     r12
0x180018c3c  pop     rdi
0x180018c3d  pop     rsi
0x180018c3e  pop     rbp
0x180018c3f  retn
```
