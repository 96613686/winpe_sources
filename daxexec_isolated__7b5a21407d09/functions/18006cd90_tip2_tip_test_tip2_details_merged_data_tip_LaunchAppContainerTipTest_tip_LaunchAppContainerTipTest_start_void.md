# tip2::tip_test<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>>::start(void)

- ea: `0x18006cd90`
- end: `0x18006cfd3`
- name: `?start@?$tip_test@V?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006980c`

## callees

- `0x180004f70`
- `0x180066840`
- `0x180068b50`
- `0x18006cacc`
- `0x18006cd90`
- `0x18006d628`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006cecf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006cecf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ceec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ceec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cf99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cf99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ce2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ce2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cf54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cf54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cf3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cf3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cf85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006cf85`

## string_xrefs

- `0x18006cec8`: `kernelbase.dll`
- `0x18006cee2`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>>::start(
        struct _RTL_CRITICAL_SECTION **a1,
        _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  struct _RTL_CRITICAL_SECTION **v5; // rax
  struct _RTL_CRITICAL_SECTION *v6; // rdx
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  struct _RTL_CRITICAL_SECTION *v9; // rsi
  __int64 v10; // r8
  ULONG_PTR *p_SpinCount; // r12
  __int64 v12; // rbx
  unsigned int LockSemaphore_high; // r14d
  char DebugInfo; // r13
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v17; // r13
  __int64 v18; // r14
  DWORD LastError; // ebx
  LPVOID v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  char v23; // [rsp+58h] [rbp-A8h]
  int v24; // [rsp+59h] [rbp-A7h] BYREF
  char v25; // [rsp+5Dh] [rbp-A3h]
  char v26; // [rsp+5Eh] [rbp-A2h] BYREF
  char v27; // [rsp+859h] [rbp+759h] BYREF
  int *v28; // [rsp+860h] [rbp+760h]
  char *v29; // [rsp+868h] [rbp+768h]
  char *v30; // [rsp+870h] [rbp+770h]

  v4 = *a1;
  if ( v4 && (*(_QWORD *)&v4[6].LockCount || (v4[1].SpinCount & 0x100) != 0) )
  {
    *a1 = 0;
    tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(v4);
  }
  if ( !*a1 )
  {
    v5 = (struct _RTL_CRITICAL_SECTION **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>,>(v21);
    v6 = *v5;
    *v5 = 0;
    v7 = *a1;
    *a1 = v6;
    if ( v7 )
      tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(v7);
    if ( v21[0] )
      tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(v21[0]);
  }
  v8 = *a1;
  v9 = *a1 + 5;
  EnterCriticalSection(v9);
  pv = 0;
  v23 = 0;
  v28 = &v24;
  v30 = &v27;
  v24 = -2143256512;
  v25 = 0;
  v29 = &v26;
  p_SpinCount = &v8[3].SpinCount;
  if ( (v8[1].SpinCount & 0x800) != 0 )
    v12 = tip2::details::shared_data<1,0,0>::serialize_data(&v8->LockCount, &pv, 1);
  else
    v12 = 0;
  LockSemaphore_high = HIDWORD(v8->LockSemaphore);
  DebugInfo = (char)v8[1].DebugInfo;
  LODWORD(v21[0]) = v8->LockSemaphore;
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
    goto LABEL_18;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestCreate");
  `TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_18:
    LOBYTE(v10) = DebugInfo;
    v17 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, ULONG_PTR *))ProcAddress)(
            LODWORD(v21[0]),
            0,
            v10,
            LockSemaphore_high,
            v12,
            &v8[3].SpinCount);
  }
  else
  {
    *(_OWORD *)p_SpinCount = 0;
    v17 = 0;
  }
  v18 = *(_QWORD *)&v8[6].LockCount;
  if ( v18 )
  {
    LastError = GetLastError();
    TestClose(v18);
    SetLastError(LastError);
  }
  *(_QWORD *)&v8[6].LockCount = v17;
  LODWORD(v8[4].SpinCount) = 1;
  *a2 = *(_OWORD *)p_SpinCount;
  if ( pv )
    CoTaskMemFree(pv);
  if ( v9 )
    LeaveCriticalSection(v9);
  return a2;
}

```

## disassembly

```asm
0x18006cd90  mov     [rsp-8+arg_10], rbx
0x18006cd95  push    rbp
0x18006cd96  push    rsi
0x18006cd97  push    rdi
0x18006cd98  push    r12
0x18006cd9a  push    r13
0x18006cd9c  push    r14
0x18006cd9e  push    r15
0x18006cda0  lea     rbp, [rsp-790h]
0x18006cda8  sub     rsp, 890h
0x18006cdaf  mov     rax, cs:__security_cookie
0x18006cdb6  xor     rax, rsp
0x18006cdb9  mov     [rbp+7C0h+var_40], rax
0x18006cdc0  mov     r15, rdx
0x18006cdc3  mov     rbx, rcx
0x18006cdc6  mov     rcx, [rcx]; pv
0x18006cdc9  xor     r14d, r14d
0x18006cdcc  test    rcx, rcx
0x18006cdcf  jz      short loc_18006CDEB
0x18006cdd1  cmp     [rcx+0F8h], r14
0x18006cdd8  jnz     short loc_18006CDE3
0x18006cdda  test    dword ptr [rcx+48h], 100h
0x18006cde1  jz      short loc_18006CDEB
0x18006cde3  mov     [rbx], r14
0x18006cde6  call    ?Release@?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(void)
0x18006cdeb  cmp     [rbx], r14
0x18006cdee  jnz     short loc_18006CE1F
0x18006cdf0  lea     rcx, [rsp+8C0h+var_880]
0x18006cdf5  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>,>(void)
0x18006cdfa  mov     rdx, [rax]
0x18006cdfd  mov     [rax], r14
0x18006ce00  mov     rcx, [rbx]; pv
0x18006ce03  mov     [rbx], rdx
0x18006ce06  test    rcx, rcx
0x18006ce09  jz      short loc_18006CE10
0x18006ce0b  call    ?Release@?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(void)
0x18006ce10  mov     rcx, [rsp+8C0h+var_880]; pv
0x18006ce15  test    rcx, rcx
0x18006ce18  jz      short loc_18006CE1F
0x18006ce1a  call    ?Release@?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(void)
0x18006ce1f  mov     rdi, [rbx]
0x18006ce22  lea     rsi, [rdi+0C8h]
0x18006ce29  mov     rcx, rsi; lpCriticalSection
0x18006ce2c  call    cs:__imp_EnterCriticalSection
0x18006ce33  nop     dword ptr [rax+rax+00h]
0x18006ce38  mov     [rsp+8C0h+pv], r14
0x18006ce3d  mov     [rsp+8C0h+var_868], r14b
0x18006ce42  lea     rax, [rsp+8C0h+var_867]
0x18006ce47  mov     [rbp+7C0h+var_60], rax
0x18006ce4e  lea     rax, [rbp+7C0h+var_67]
0x18006ce55  mov     [rbp+7C0h+var_50], rax
0x18006ce5c  mov     [rsp+8C0h+var_867], 80408040h
0x18006ce64  mov     [rsp+8C0h+var_863], r14b
0x18006ce69  lea     rax, [rsp+8C0h+var_862]
0x18006ce6e  mov     [rbp+7C0h+var_58], rax
0x18006ce75  lea     r12, [rdi+98h]
0x18006ce7c  test    dword ptr [rdi+48h], 800h
0x18006ce83  jz      short loc_18006CE9E
0x18006ce85  mov     r8d, 1
0x18006ce8b  lea     rdx, [rsp+8C0h+pv]
0x18006ce90  lea     rcx, [rdi+8]
0x18006ce94  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18006ce99  mov     rbx, rax
0x18006ce9c  jmp     short loc_18006CEA1
0x18006ce9e  mov     rbx, r14
0x18006cea1  mov     r14d, [rdi+1Ch]
0x18006cea5  mov     r13b, [rdi+28h]
0x18006cea9  mov     eax, [rdi+18h]
0x18006ceac  mov     dword ptr [rsp+8C0h+var_880], eax
0x18006ceb0  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18006ceb7  test    rax, rax
0x18006ceba  jnz     short loc_18006CF12
0x18006cebc  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18006cec3  test    rax, rax
0x18006cec6  jnz     short loc_18006CEE2
0x18006cec8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18006cecf  call    cs:__imp_GetModuleHandleW
0x18006ced6  nop     dword ptr [rax+rax+00h]
0x18006cedb  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18006cee2  lea     rdx, aTestcreate; "TestCreate"
0x18006cee9  mov     rcx, rax; hModule
0x18006ceec  call    cs:__imp_GetProcAddress
0x18006cef3  nop     dword ptr [rax+rax+00h]
0x18006cef8  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18006ceff  test    rax, rax
0x18006cf02  jnz     short loc_18006CF12
0x18006cf04  xorps   xmm0, xmm0
0x18006cf07  movdqu  xmmword ptr [r12], xmm0
0x18006cf0d  xor     r13d, r13d
0x18006cf10  jmp     short loc_18006CF30
0x18006cf12  mov     [rsp+8C0h+var_898], r12
0x18006cf17  mov     [rsp+8C0h+var_8A0], rbx
0x18006cf1c  mov     r9d, r14d
0x18006cf1f  mov     r8b, r13b
0x18006cf22  xor     edx, edx
0x18006cf24  mov     ecx, dword ptr [rsp+8C0h+var_880]
0x18006cf28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf2d  mov     r13, rax
0x18006cf30  mov     r14, [rdi+0F8h]
0x18006cf37  test    r14, r14
0x18006cf3a  jz      short loc_18006CF60
0x18006cf3c  call    cs:__imp_GetLastError
0x18006cf43  nop     dword ptr [rax+rax+00h]
0x18006cf48  mov     ebx, eax
0x18006cf4a  mov     rcx, r14
0x18006cf4d  call    TestClose
0x18006cf52  mov     ecx, ebx; dwErrCode
0x18006cf54  call    cs:__imp_SetLastError
0x18006cf5b  nop     dword ptr [rax+rax+00h]
0x18006cf60  mov     [rdi+0F8h], r13
0x18006cf67  mov     dword ptr [rdi+0C0h], 1
0x18006cf71  movups  xmm0, xmmword ptr [r12]
0x18006cf76  movdqu  xmmword ptr [r15], xmm0
0x18006cf7b  mov     rcx, [rsp+8C0h+pv]; pv
0x18006cf80  test    rcx, rcx
0x18006cf83  jz      short loc_18006CF91
0x18006cf85  call    cs:__imp_CoTaskMemFree
0x18006cf8c  nop     dword ptr [rax+rax+00h]
0x18006cf91  test    rsi, rsi
0x18006cf94  jz      short loc_18006CFA5
0x18006cf96  mov     rcx, rsi; lpCriticalSection
0x18006cf99  call    cs:__imp_LeaveCriticalSection
0x18006cfa0  nop     dword ptr [rax+rax+00h]
0x18006cfa5  mov     rax, r15
0x18006cfa8  mov     rcx, [rbp+7C0h+var_40]
0x18006cfaf  xor     rcx, rsp; StackCookie
0x18006cfb2  call    __security_check_cookie
0x18006cfb7  mov     rbx, [rsp+8C0h+arg_10]
0x18006cfbf  add     rsp, 890h
0x18006cfc6  pop     r15
0x18006cfc8  pop     r14
0x18006cfca  pop     r13
0x18006cfcc  pop     r12
0x18006cfce  pop     rdi
0x18006cfcf  pop     rsi
0x18006cfd0  pop     rbp
0x18006cfd1  retn
```
