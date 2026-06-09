# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180055904`
- end: `0x180055a7a`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `374`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180052f60`
- `0x18005625c`
- `0x180058e44`
- `0x18005b8a8`

## callees

- `0x18004b460`
- `0x180052fcc`
- `0x180055904`
- `0x180056da4`
- `0x180058440`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800559e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800559e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055a58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055a58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055a45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055a45`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  int v6; // ecx
  __int128 v7; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h]
  __int128 v9; // [rsp+50h] [rbp-B0h]
  __int64 v10; // [rsp+60h] [rbp-A0h] BYREF
  char v11; // [rsp+68h] [rbp-98h]
  int v12; // [rsp+69h] [rbp-97h] BYREF
  char v13; // [rsp+6Dh] [rbp-93h]
  char v14; // [rsp+6Eh] [rbp-92h] BYREF
  char v15; // [rsp+869h] [rbp+769h] BYREF
  int *v16; // [rsp+870h] [rbp+770h]
  char *v17; // [rsp+878h] [rbp+778h]
  char *v18; // [rsp+880h] [rbp+780h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
  {
    v7 = 0;
    *(_OWORD *)pv = 0;
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v16 = &v12;
    v18 = &v15;
    v12 = -2143256512;
    v13 = 0;
    v17 = &v14;
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v10, 1);
    v3 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData
      || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
          ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestUnlockData"),
          (`TestUnlockData'::`2'::s_pfnTestUnlockData = (__int64)ProcAddress) != 0) )
    {
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v3, 0, v2, &v7);
    }
    else
    {
      v7 = 0;
      *(_OWORD *)pv = 0;
      v9 = 0;
    }
    v6 = (int)pv[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( !pv[1] )
      *(_DWORD *)(a1 + 184) = v6;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v10);
    CoTaskMemFree(pv[1]);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x180055904  push    rbp
0x180055906  push    rbx
0x180055907  push    rsi
0x180055908  push    rdi
0x180055909  lea     rbp, [rsp-7A8h]
0x180055911  sub     rsp, 8A8h
0x180055918  mov     rax, cs:__security_cookie
0x18005591f  xor     rax, rsp
0x180055922  mov     [rbp+7C0h+var_30], rax
0x180055929  mov     rbx, rcx
0x18005592c  bts     dword ptr [rcx+40h], 0Bh
0x180055931  cmp     qword ptr [rcx+0F0h], 0
0x180055939  jz      loc_180055A4B
0x18005593f  test    dword ptr [rcx+40h], 100h
0x180055946  jnz     loc_180055A4B
0x18005594c  test    dword ptr [rcx+14h], 8000h
0x180055953  jnz     loc_180055A4B
0x180055959  xorps   xmm0, xmm0
0x18005595c  movups  [rsp+8C0h+var_890], xmm0
0x180055961  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x180055966  movups  [rsp+8C0h+var_870], xmm0
0x18005596b  mov     [rsp+8C0h+var_860], 0
0x180055974  mov     [rsp+8C0h+var_858], 0
0x180055979  lea     rax, [rsp+8C0h+var_857]
0x18005597e  mov     [rbp+7C0h+var_50], rax
0x180055985  lea     rax, [rbp+7C0h+var_57]
0x18005598c  mov     [rbp+7C0h+var_40], rax
0x180055993  mov     [rsp+8C0h+var_857], 80408040h
0x18005599b  mov     [rsp+8C0h+var_853], 0
0x1800559a0  lea     rax, [rsp+8C0h+var_852]
0x1800559a5  mov     [rbp+7C0h+var_48], rax
0x1800559ac  mov     r8d, 1
0x1800559b2  lea     rdx, [rsp+8C0h+var_860]
0x1800559b7  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800559bc  mov     rdi, rax
0x1800559bf  mov     rsi, [rbx+0F0h]
0x1800559c6  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800559cd  test    rax, rax
0x1800559d0  jnz     short loc_180055A07
0x1800559d2  call    tip_details_GetKernelBaseModuleHandle
0x1800559d7  mov     rcx, rax; hModule
0x1800559da  lea     rdx, aTestunlockdata; "TestUnlockData"
0x1800559e1  call    cs:__imp_GetProcAddress
0x1800559e7  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800559ee  test    rax, rax
0x1800559f1  jnz     short loc_180055A07
0x1800559f3  xorps   xmm0, xmm0
0x1800559f6  movups  [rsp+8C0h+var_890], xmm0
0x1800559fb  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x180055a00  movups  [rsp+8C0h+var_870], xmm0
0x180055a05  jmp     short loc_180055A19
0x180055a07  lea     r9, [rsp+8C0h+var_890]
0x180055a0c  mov     r8, rdi
0x180055a0f  xor     edx, edx
0x180055a11  mov     rcx, rsi
0x180055a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a19  mov     rcx, [rsp+8C0h+pv]
0x180055a1e  mov     rax, rcx
0x180055a21  shr     rax, 20h
0x180055a25  or      [rbx+40h], eax
0x180055a28  cmp     [rsp+8C0h+pv+8], 0
0x180055a2e  jnz     short loc_180055A36
0x180055a30  mov     [rbx+0B8h], ecx
0x180055a36  lea     rcx, [rsp+8C0h+var_860]
0x180055a3b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180055a40  mov     rcx, [rsp+8C0h+pv+8]; pv
0x180055a45  call    cs:__imp_CoTaskMemFree
0x180055a4b  dec     dword ptr [rbx+0E8h]
0x180055a51  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180055a58  call    cs:__imp_LeaveCriticalSection
0x180055a5e  nop
0x180055a5f  mov     rcx, [rbp+7C0h+var_30]
0x180055a66  xor     rcx, rsp; StackCookie
0x180055a69  call    __security_check_cookie
0x180055a6e  add     rsp, 8A8h
0x180055a75  pop     rdi
0x180055a76  pop     rsi
0x180055a77  pop     rbx
0x180055a78  pop     rbp
0x180055a79  retn
```
