# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x18009eaf0`
- end: `0x18009ec66`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009b9ec`

## callees

- `0x180069998`
- `0x180075fa0`
- `0x18007f2ec`
- `0x18009eaf0`
- `0x18009fc94`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009ebcd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009ebcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ec44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ec44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ec31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ec31`

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
0x18009eaf0  push    rbp
0x18009eaf2  push    rbx
0x18009eaf3  push    rsi
0x18009eaf4  push    rdi
0x18009eaf5  lea     rbp, [rsp-7A8h]
0x18009eafd  sub     rsp, 8A8h
0x18009eb04  mov     rax, cs:__security_cookie
0x18009eb0b  xor     rax, rsp
0x18009eb0e  mov     [rbp+7C0h+var_30], rax
0x18009eb15  mov     rbx, rcx
0x18009eb18  bts     dword ptr [rcx+40h], 0Bh
0x18009eb1d  cmp     qword ptr [rcx+0F0h], 0
0x18009eb25  jz      loc_18009EC37
0x18009eb2b  test    dword ptr [rcx+40h], 100h
0x18009eb32  jnz     loc_18009EC37
0x18009eb38  test    dword ptr [rcx+14h], 8000h
0x18009eb3f  jnz     loc_18009EC37
0x18009eb45  xorps   xmm0, xmm0
0x18009eb48  movups  [rsp+8C0h+var_890], xmm0
0x18009eb4d  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x18009eb52  movups  [rsp+8C0h+var_870], xmm0
0x18009eb57  mov     [rsp+8C0h+var_860], 0
0x18009eb60  mov     [rsp+8C0h+var_858], 0
0x18009eb65  lea     rax, [rsp+8C0h+var_857]
0x18009eb6a  mov     [rbp+7C0h+var_50], rax
0x18009eb71  lea     rax, [rbp+7C0h+var_57]
0x18009eb78  mov     [rbp+7C0h+var_40], rax
0x18009eb7f  mov     [rsp+8C0h+var_857], 80408040h
0x18009eb87  mov     [rsp+8C0h+var_853], 0
0x18009eb8c  lea     rax, [rsp+8C0h+var_852]
0x18009eb91  mov     [rbp+7C0h+var_48], rax
0x18009eb98  mov     r8d, 1
0x18009eb9e  lea     rdx, [rsp+8C0h+var_860]
0x18009eba3  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18009eba8  mov     rdi, rax
0x18009ebab  mov     rsi, [rbx+0F0h]
0x18009ebb2  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18009ebb9  test    rax, rax
0x18009ebbc  jnz     short loc_18009EBF3
0x18009ebbe  call    tip_details_GetKernelBaseModuleHandle
0x18009ebc3  mov     rcx, rax; hModule
0x18009ebc6  lea     rdx, aTestunlockdata; "TestUnlockData"
0x18009ebcd  call    cs:__imp_GetProcAddress
0x18009ebd3  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18009ebda  test    rax, rax
0x18009ebdd  jnz     short loc_18009EBF3
0x18009ebdf  xorps   xmm0, xmm0
0x18009ebe2  movups  [rsp+8C0h+var_890], xmm0
0x18009ebe7  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x18009ebec  movups  [rsp+8C0h+var_870], xmm0
0x18009ebf1  jmp     short loc_18009EC05
0x18009ebf3  lea     r9, [rsp+8C0h+var_890]
0x18009ebf8  mov     r8, rdi
0x18009ebfb  xor     edx, edx
0x18009ebfd  mov     rcx, rsi
0x18009ec00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ec05  mov     rcx, [rsp+8C0h+pv]
0x18009ec0a  mov     rax, rcx
0x18009ec0d  shr     rax, 20h
0x18009ec11  or      [rbx+40h], eax
0x18009ec14  cmp     [rsp+8C0h+pv+8], 0
0x18009ec1a  jnz     short loc_18009EC22
0x18009ec1c  mov     [rbx+0B8h], ecx
0x18009ec22  lea     rcx, [rsp+8C0h+var_860]
0x18009ec27  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18009ec2c  mov     rcx, [rsp+8C0h+pv+8]; pv
0x18009ec31  call    cs:__imp_CoTaskMemFree
0x18009ec37  dec     dword ptr [rbx+0E8h]
0x18009ec3d  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18009ec44  call    cs:__imp_LeaveCriticalSection
0x18009ec4a  nop
0x18009ec4b  mov     rcx, [rbp+7C0h+var_30]
0x18009ec52  xor     rcx, rsp; StackCookie
0x18009ec55  call    __security_check_cookie
0x18009ec5a  add     rsp, 8A8h
0x18009ec61  pop     rdi
0x18009ec62  pop     rsi
0x18009ec63  pop     rbx
0x18009ec64  pop     rbp
0x18009ec65  retn
```
