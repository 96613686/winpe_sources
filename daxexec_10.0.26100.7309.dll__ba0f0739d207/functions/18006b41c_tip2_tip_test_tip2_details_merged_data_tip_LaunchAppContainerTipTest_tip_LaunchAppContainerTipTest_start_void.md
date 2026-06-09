# tip2::tip_test<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>>::start(void)

- ea: `0x18006b41c`
- end: `0x18006b657`
- name: `?start@?$tip_test@V?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180067e48`

## callees

- `0x1800053a0`
- `0x180064e7c`
- `0x180067118`
- `0x18006b194`
- `0x18006b41c`
- `0x18006bcdc`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b570`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b570`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006b553`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006b553`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b4b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b4b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b61d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b5c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b5d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b5d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b609`

## string_xrefs

- `0x18006b54c`: `kernelbase.dll`
- `0x18006b566`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>>::start(
        void **a1,
        _OWORD *a2)
{
  void *v4; // rcx
  __int64 v5; // rbx
  void **v6; // rax
  void *v7; // rdx
  void *v8; // rcx
  char *v9; // rdi
  __int64 v10; // r8
  _OWORD *v11; // r12
  unsigned int v12; // r14d
  char v13; // r13
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v16; // r13
  __int64 v17; // r14
  DWORD LastError; // ebx
  LPVOID v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  char v22; // [rsp+58h] [rbp-A8h]
  int v23; // [rsp+59h] [rbp-A7h] BYREF
  char v24; // [rsp+5Dh] [rbp-A3h]
  char v25; // [rsp+5Eh] [rbp-A2h] BYREF
  char v26; // [rsp+859h] [rbp+759h] BYREF
  int *v27; // [rsp+860h] [rbp+760h]
  char *v28; // [rsp+868h] [rbp+768h]
  char *v29; // [rsp+870h] [rbp+770h]

  v4 = *a1;
  v5 = 0;
  if ( v4 && (*((_QWORD *)v4 + 30) || (*((_DWORD *)v4 + 18) & 0x100) != 0) )
  {
    *a1 = 0;
    tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(v4);
  }
  if ( !*a1 )
  {
    v6 = (void **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>,>(v20);
    v7 = *v6;
    *v6 = 0;
    v8 = *a1;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(v8);
    if ( v20[0] )
      tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(v20[0]);
  }
  v9 = (char *)*a1;
  EnterCriticalSection((LPCRITICAL_SECTION)v9 + 5);
  pv = 0;
  v22 = 0;
  v27 = &v23;
  v29 = &v26;
  v23 = -2143256512;
  v24 = 0;
  v28 = &v25;
  v11 = v9 + 152;
  if ( (*((_DWORD *)v9 + 18) & 0x800) != 0 )
    v5 = tip2::details::shared_data<1,0,0>::serialize_data(v9 + 8, &pv, 1);
  v12 = *((_DWORD *)v9 + 7);
  v13 = v9[40];
  LODWORD(v20[0]) = *((_DWORD *)v9 + 6);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
    goto LABEL_17;
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
LABEL_17:
    LOBYTE(v10) = v13;
    v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, char *))ProcAddress)(
            LODWORD(v20[0]),
            0,
            v10,
            v12,
            v5,
            v9 + 152);
  }
  else
  {
    *v11 = 0;
    v16 = 0;
  }
  v17 = *((_QWORD *)v9 + 30);
  if ( v17 )
  {
    LastError = GetLastError();
    TestClose(v17);
    SetLastError(LastError);
  }
  *((_QWORD *)v9 + 30) = v16;
  *((_DWORD *)v9 + 48) = 1;
  *a2 = *v11;
  if ( pv )
    CoTaskMemFree(pv);
  if ( v9 != (char *)-200LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)v9 + 5);
  return a2;
}

```

## disassembly

```asm
0x18006b41c  mov     [rsp-8+arg_10], rbx
0x18006b421  push    rbp
0x18006b422  push    rsi
0x18006b423  push    rdi
0x18006b424  push    r12
0x18006b426  push    r13
0x18006b428  push    r14
0x18006b42a  push    r15
0x18006b42c  lea     rbp, [rsp-790h]
0x18006b434  sub     rsp, 890h
0x18006b43b  mov     rax, cs:__security_cookie
0x18006b442  xor     rax, rsp
0x18006b445  mov     [rbp+7C0h+var_40], rax
0x18006b44c  mov     r15, rdx
0x18006b44f  mov     rdi, rcx
0x18006b452  mov     rcx, [rcx]; pv
0x18006b455  xor     ebx, ebx
0x18006b457  test    rcx, rcx
0x18006b45a  jz      short loc_18006B476
0x18006b45c  cmp     [rcx+0F0h], rbx
0x18006b463  jnz     short loc_18006B46E
0x18006b465  test    dword ptr [rcx+48h], 100h
0x18006b46c  jz      short loc_18006B476
0x18006b46e  mov     [rdi], rbx
0x18006b471  call    ?Release@?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(void)
0x18006b476  cmp     [rdi], rbx
0x18006b479  jnz     short loc_18006B4AA
0x18006b47b  lea     rcx, [rsp+8C0h+var_880]
0x18006b480  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>,>(void)
0x18006b485  mov     rdx, [rax]
0x18006b488  mov     [rax], rbx
0x18006b48b  mov     rcx, [rdi]; pv
0x18006b48e  mov     [rdi], rdx
0x18006b491  test    rcx, rcx
0x18006b494  jz      short loc_18006B49B
0x18006b496  call    ?Release@?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(void)
0x18006b49b  mov     rcx, [rsp+8C0h+var_880]; pv
0x18006b4a0  test    rcx, rcx
0x18006b4a3  jz      short loc_18006B4AA
0x18006b4a5  call    ?Release@?$merged_data@U_tip_LaunchAppContainerTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_LaunchAppContainerTipTest,_tip_LaunchAppContainerTipTest>::Release(void)
0x18006b4aa  mov     rdi, [rdi]
0x18006b4ad  lea     rsi, [rdi+0C8h]
0x18006b4b4  mov     rcx, rsi; lpCriticalSection
0x18006b4b7  call    cs:__imp_EnterCriticalSection
0x18006b4be  nop     dword ptr [rax+rax+00h]
0x18006b4c3  mov     [rsp+8C0h+pv], rbx
0x18006b4c8  mov     [rsp+8C0h+var_868], bl
0x18006b4cc  lea     rax, [rsp+8C0h+var_867]
0x18006b4d1  mov     [rbp+7C0h+var_60], rax
0x18006b4d8  lea     rax, [rbp+7C0h+var_67]
0x18006b4df  mov     [rbp+7C0h+var_50], rax
0x18006b4e6  mov     [rsp+8C0h+var_867], 80408040h
0x18006b4ee  mov     [rsp+8C0h+var_863], bl
0x18006b4f2  lea     rax, [rsp+8C0h+var_862]
0x18006b4f7  mov     [rbp+7C0h+var_58], rax
0x18006b4fe  lea     r12, [rdi+98h]
0x18006b505  test    dword ptr [rdi+48h], 800h
0x18006b50c  jz      short loc_18006B525
0x18006b50e  mov     r8d, 1
0x18006b514  lea     rdx, [rsp+8C0h+pv]
0x18006b519  lea     rcx, [rdi+8]
0x18006b51d  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18006b522  mov     rbx, rax
0x18006b525  mov     r14d, [rdi+1Ch]
0x18006b529  mov     r13b, [rdi+28h]
0x18006b52d  mov     eax, [rdi+18h]
0x18006b530  mov     dword ptr [rsp+8C0h+var_880], eax
0x18006b534  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18006b53b  test    rax, rax
0x18006b53e  jnz     short loc_18006B596
0x18006b540  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18006b547  test    rax, rax
0x18006b54a  jnz     short loc_18006B566
0x18006b54c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18006b553  call    cs:__imp_GetModuleHandleW
0x18006b55a  nop     dword ptr [rax+rax+00h]
0x18006b55f  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18006b566  lea     rdx, aTestcreate; "TestCreate"
0x18006b56d  mov     rcx, rax; hModule
0x18006b570  call    cs:__imp_GetProcAddress
0x18006b577  nop     dword ptr [rax+rax+00h]
0x18006b57c  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18006b583  test    rax, rax
0x18006b586  jnz     short loc_18006B596
0x18006b588  xorps   xmm0, xmm0
0x18006b58b  movdqu  xmmword ptr [r12], xmm0
0x18006b591  xor     r13d, r13d
0x18006b594  jmp     short loc_18006B5B4
0x18006b596  mov     [rsp+8C0h+var_898], r12
0x18006b59b  mov     [rsp+8C0h+var_8A0], rbx
0x18006b5a0  mov     r9d, r14d
0x18006b5a3  mov     r8b, r13b
0x18006b5a6  xor     edx, edx
0x18006b5a8  mov     ecx, dword ptr [rsp+8C0h+var_880]
0x18006b5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b5b1  mov     r13, rax
0x18006b5b4  mov     r14, [rdi+0F0h]
0x18006b5bb  test    r14, r14
0x18006b5be  jz      short loc_18006B5E4
0x18006b5c0  call    cs:__imp_GetLastError
0x18006b5c7  nop     dword ptr [rax+rax+00h]
0x18006b5cc  mov     ebx, eax
0x18006b5ce  mov     rcx, r14
0x18006b5d1  call    TestClose
0x18006b5d6  mov     ecx, ebx; dwErrCode
0x18006b5d8  call    cs:__imp_SetLastError
0x18006b5df  nop     dword ptr [rax+rax+00h]
0x18006b5e4  mov     [rdi+0F0h], r13
0x18006b5eb  mov     dword ptr [rdi+0C0h], 1
0x18006b5f5  movups  xmm0, xmmword ptr [r12]
0x18006b5fa  movdqu  xmmword ptr [r15], xmm0
0x18006b5ff  mov     rcx, [rsp+8C0h+pv]; pv
0x18006b604  test    rcx, rcx
0x18006b607  jz      short loc_18006B615
0x18006b609  call    cs:__imp_CoTaskMemFree
0x18006b610  nop     dword ptr [rax+rax+00h]
0x18006b615  test    rsi, rsi
0x18006b618  jz      short loc_18006B629
0x18006b61a  mov     rcx, rsi; lpCriticalSection
0x18006b61d  call    cs:__imp_LeaveCriticalSection
0x18006b624  nop     dword ptr [rax+rax+00h]
0x18006b629  mov     rax, r15
0x18006b62c  mov     rcx, [rbp+7C0h+var_40]
0x18006b633  xor     rcx, rsp; StackCookie
0x18006b636  call    __security_check_cookie
0x18006b63b  mov     rbx, [rsp+8C0h+arg_10]
0x18006b643  add     rsp, 890h
0x18006b64a  pop     r15
0x18006b64c  pop     r14
0x18006b64e  pop     r13
0x18006b650  pop     r12
0x18006b652  pop     rdi
0x18006b653  pop     rsi
0x18006b654  pop     rbp
0x18006b655  retn
```
