# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180059184`
- end: `0x18005930d`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `393`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800566ec`
- `0x180059af8`
- `0x18005c7bc`
- `0x18005f2c8`

## callees

- `0x18004e850`
- `0x180056758`
- `0x180059184`
- `0x18005a674`
- `0x18005bd8c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059261`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059261`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800592e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800592e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800592cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800592cb`

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
0x180059184  push    rbp
0x180059186  push    rbx
0x180059187  push    rsi
0x180059188  push    rdi
0x180059189  lea     rbp, [rsp-7A8h]
0x180059191  sub     rsp, 8A8h
0x180059198  mov     rax, cs:__security_cookie
0x18005919f  xor     rax, rsp
0x1800591a2  mov     [rbp+7C0h+var_30], rax
0x1800591a9  mov     rbx, rcx
0x1800591ac  bts     dword ptr [rcx+40h], 0Bh
0x1800591b1  cmp     qword ptr [rcx+0F0h], 0
0x1800591b9  jz      loc_1800592D7
0x1800591bf  test    dword ptr [rcx+40h], 100h
0x1800591c6  jnz     loc_1800592D7
0x1800591cc  test    dword ptr [rcx+14h], 8000h
0x1800591d3  jnz     loc_1800592D7
0x1800591d9  xorps   xmm0, xmm0
0x1800591dc  movups  [rsp+8C0h+var_890], xmm0
0x1800591e1  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x1800591e6  movups  [rsp+8C0h+var_870], xmm0
0x1800591eb  mov     [rsp+8C0h+var_860], 0
0x1800591f4  mov     [rsp+8C0h+var_858], 0
0x1800591f9  lea     rax, [rsp+8C0h+var_857]
0x1800591fe  mov     [rbp+7C0h+var_50], rax
0x180059205  lea     rax, [rbp+7C0h+var_57]
0x18005920c  mov     [rbp+7C0h+var_40], rax
0x180059213  mov     [rsp+8C0h+var_857], 80408040h
0x18005921b  mov     [rsp+8C0h+var_853], 0
0x180059220  lea     rax, [rsp+8C0h+var_852]
0x180059225  mov     [rbp+7C0h+var_48], rax
0x18005922c  mov     r8d, 1
0x180059232  lea     rdx, [rsp+8C0h+var_860]
0x180059237  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18005923c  mov     rdi, rax
0x18005923f  mov     rsi, [rbx+0F0h]
0x180059246  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18005924d  test    rax, rax
0x180059250  jnz     short loc_18005928D
0x180059252  call    tip_details_GetKernelBaseModuleHandle
0x180059257  mov     rcx, rax; hModule
0x18005925a  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180059261  call    cs:__imp_GetProcAddress
0x180059268  nop     dword ptr [rax+rax+00h]
0x18005926d  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180059274  test    rax, rax
0x180059277  jnz     short loc_18005928D
0x180059279  xorps   xmm0, xmm0
0x18005927c  movups  [rsp+8C0h+var_890], xmm0
0x180059281  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x180059286  movups  [rsp+8C0h+var_870], xmm0
0x18005928b  jmp     short loc_18005929F
0x18005928d  lea     r9, [rsp+8C0h+var_890]
0x180059292  mov     r8, rdi
0x180059295  xor     edx, edx
0x180059297  mov     rcx, rsi
0x18005929a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005929f  mov     rcx, [rsp+8C0h+pv]
0x1800592a4  mov     rax, rcx
0x1800592a7  shr     rax, 20h
0x1800592ab  or      [rbx+40h], eax
0x1800592ae  cmp     [rsp+8C0h+pv+8], 0
0x1800592b4  jnz     short loc_1800592BC
0x1800592b6  mov     [rbx+0B8h], ecx
0x1800592bc  lea     rcx, [rsp+8C0h+var_860]
0x1800592c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800592c6  mov     rcx, [rsp+8C0h+pv+8]; pv
0x1800592cb  call    cs:__imp_CoTaskMemFree
0x1800592d2  nop     dword ptr [rax+rax+00h]
0x1800592d7  dec     dword ptr [rbx+0E8h]
0x1800592dd  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800592e4  call    cs:__imp_LeaveCriticalSection
0x1800592eb  nop     dword ptr [rax+rax+00h]
0x1800592f0  nop
0x1800592f1  mov     rcx, [rbp+7C0h+var_30]
0x1800592f8  xor     rcx, rsp; StackCookie
0x1800592fb  call    __security_check_cookie
0x180059300  add     rsp, 8A8h
0x180059307  pop     rdi
0x180059308  pop     rsi
0x180059309  pop     rbx
0x18005930a  pop     rbp
0x18005930b  retn
```
