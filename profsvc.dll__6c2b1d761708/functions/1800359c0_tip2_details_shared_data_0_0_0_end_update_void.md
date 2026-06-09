# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x1800359c0`
- end: `0x180035b49`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `393`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f6b0`
- `0x180047150`

## callees

- `0x1800285e0`
- `0x180028658`
- `0x1800359c0`
- `0x180035b50`
- `0x18003bc70`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035a9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035a9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035b20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035b20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b07`

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
0x1800359c0  push    rbp
0x1800359c2  push    rbx
0x1800359c3  push    rsi
0x1800359c4  push    rdi
0x1800359c5  lea     rbp, [rsp-7A8h]
0x1800359cd  sub     rsp, 8A8h
0x1800359d4  mov     rax, cs:__security_cookie
0x1800359db  xor     rax, rsp
0x1800359de  mov     [rbp+7C0h+var_30], rax
0x1800359e5  mov     rbx, rcx
0x1800359e8  bts     dword ptr [rcx+40h], 0Bh
0x1800359ed  cmp     qword ptr [rcx+0F0h], 0
0x1800359f5  jz      loc_180035B13
0x1800359fb  test    dword ptr [rcx+40h], 100h
0x180035a02  jnz     loc_180035B13
0x180035a08  test    dword ptr [rcx+14h], 8000h
0x180035a0f  jnz     loc_180035B13
0x180035a15  xorps   xmm0, xmm0
0x180035a18  movups  [rsp+8C0h+var_890], xmm0
0x180035a1d  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x180035a22  movups  [rsp+8C0h+var_870], xmm0
0x180035a27  mov     [rsp+8C0h+var_860], 0
0x180035a30  mov     [rsp+8C0h+var_858], 0
0x180035a35  lea     rax, [rsp+8C0h+var_857]
0x180035a3a  mov     [rbp+7C0h+var_50], rax
0x180035a41  lea     rax, [rbp+7C0h+var_57]
0x180035a48  mov     [rbp+7C0h+var_40], rax
0x180035a4f  mov     [rsp+8C0h+var_857], 80408040h
0x180035a57  mov     [rsp+8C0h+var_853], 0
0x180035a5c  lea     rax, [rsp+8C0h+var_852]
0x180035a61  mov     [rbp+7C0h+var_48], rax
0x180035a68  mov     r8d, 1
0x180035a6e  lea     rdx, [rsp+8C0h+var_860]
0x180035a73  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180035a78  mov     rdi, rax
0x180035a7b  mov     rsi, [rbx+0F0h]
0x180035a82  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180035a89  test    rax, rax
0x180035a8c  jnz     short loc_180035AC9
0x180035a8e  call    tip_details_GetKernelBaseModuleHandle
0x180035a93  mov     rcx, rax; hModule
0x180035a96  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180035a9d  call    cs:__imp_GetProcAddress
0x180035aa4  nop     dword ptr [rax+rax+00h]
0x180035aa9  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180035ab0  test    rax, rax
0x180035ab3  jnz     short loc_180035AC9
0x180035ab5  xorps   xmm0, xmm0
0x180035ab8  movups  [rsp+8C0h+var_890], xmm0
0x180035abd  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x180035ac2  movups  [rsp+8C0h+var_870], xmm0
0x180035ac7  jmp     short loc_180035ADB
0x180035ac9  lea     r9, [rsp+8C0h+var_890]
0x180035ace  mov     r8, rdi
0x180035ad1  xor     edx, edx
0x180035ad3  mov     rcx, rsi
0x180035ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035adb  mov     rcx, [rsp+8C0h+pv]
0x180035ae0  mov     rax, rcx
0x180035ae3  shr     rax, 20h
0x180035ae7  or      [rbx+40h], eax
0x180035aea  cmp     [rsp+8C0h+pv+8], 0
0x180035af0  jnz     short loc_180035AF8
0x180035af2  mov     [rbx+0B8h], ecx
0x180035af8  lea     rcx, [rsp+8C0h+var_860]
0x180035afd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180035b02  mov     rcx, [rsp+8C0h+pv+8]; pv
0x180035b07  call    cs:__imp_CoTaskMemFree
0x180035b0e  nop     dword ptr [rax+rax+00h]
0x180035b13  dec     dword ptr [rbx+0E8h]
0x180035b19  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180035b20  call    cs:__imp_LeaveCriticalSection
0x180035b27  nop     dword ptr [rax+rax+00h]
0x180035b2c  nop
0x180035b2d  mov     rcx, [rbp+7C0h+var_30]
0x180035b34  xor     rcx, rsp; StackCookie
0x180035b37  call    __security_check_cookie
0x180035b3c  add     rsp, 8A8h
0x180035b43  pop     rdi
0x180035b44  pop     rsi
0x180035b45  pop     rbx
0x180035b46  pop     rbp
0x180035b47  retn
```
