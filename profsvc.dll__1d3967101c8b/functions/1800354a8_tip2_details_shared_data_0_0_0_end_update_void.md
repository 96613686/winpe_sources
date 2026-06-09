# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x1800354a8`
- end: `0x18003561e`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `374`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800303cc`
- `0x180045220`

## callees

- `0x180025b50`
- `0x180025bbc`
- `0x1800354a8`
- `0x180035624`
- `0x18003a730`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035585`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035585`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800355fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800355fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800355e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800355e9`

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
  void *v10; // [rsp+60h] [rbp-A0h] BYREF
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
0x1800354a8  push    rbp
0x1800354aa  push    rbx
0x1800354ab  push    rsi
0x1800354ac  push    rdi
0x1800354ad  lea     rbp, [rsp-7A8h]
0x1800354b5  sub     rsp, 8A8h
0x1800354bc  mov     rax, cs:__security_cookie
0x1800354c3  xor     rax, rsp
0x1800354c6  mov     [rbp+7C0h+var_30], rax
0x1800354cd  mov     rbx, rcx
0x1800354d0  bts     dword ptr [rcx+40h], 0Bh
0x1800354d5  cmp     qword ptr [rcx+0F0h], 0
0x1800354dd  jz      loc_1800355EF
0x1800354e3  test    dword ptr [rcx+40h], 100h
0x1800354ea  jnz     loc_1800355EF
0x1800354f0  test    dword ptr [rcx+14h], 8000h
0x1800354f7  jnz     loc_1800355EF
0x1800354fd  xorps   xmm0, xmm0
0x180035500  movups  [rsp+8C0h+var_890], xmm0
0x180035505  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x18003550a  movups  [rsp+8C0h+var_870], xmm0
0x18003550f  mov     [rsp+8C0h+var_860], 0
0x180035518  mov     [rsp+8C0h+var_858], 0
0x18003551d  lea     rax, [rsp+8C0h+var_857]
0x180035522  mov     [rbp+7C0h+var_50], rax
0x180035529  lea     rax, [rbp+7C0h+var_57]
0x180035530  mov     [rbp+7C0h+var_40], rax
0x180035537  mov     [rsp+8C0h+var_857], 80408040h
0x18003553f  mov     [rsp+8C0h+var_853], 0
0x180035544  lea     rax, [rsp+8C0h+var_852]
0x180035549  mov     [rbp+7C0h+var_48], rax
0x180035550  mov     r8d, 1
0x180035556  lea     rdx, [rsp+8C0h+var_860]
0x18003555b  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180035560  mov     rdi, rax
0x180035563  mov     rsi, [rbx+0F0h]
0x18003556a  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180035571  test    rax, rax
0x180035574  jnz     short loc_1800355AB
0x180035576  call    tip_details_GetKernelBaseModuleHandle
0x18003557b  mov     rcx, rax; hModule
0x18003557e  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180035585  call    cs:__imp_GetProcAddress
0x18003558b  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180035592  test    rax, rax
0x180035595  jnz     short loc_1800355AB
0x180035597  xorps   xmm0, xmm0
0x18003559a  movups  [rsp+8C0h+var_890], xmm0
0x18003559f  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x1800355a4  movups  [rsp+8C0h+var_870], xmm0
0x1800355a9  jmp     short loc_1800355BD
0x1800355ab  lea     r9, [rsp+8C0h+var_890]
0x1800355b0  mov     r8, rdi
0x1800355b3  xor     edx, edx
0x1800355b5  mov     rcx, rsi
0x1800355b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355bd  mov     rcx, [rsp+8C0h+pv]
0x1800355c2  mov     rax, rcx
0x1800355c5  shr     rax, 20h
0x1800355c9  or      [rbx+40h], eax
0x1800355cc  cmp     [rsp+8C0h+pv+8], 0
0x1800355d2  jnz     short loc_1800355DA
0x1800355d4  mov     [rbx+0B8h], ecx
0x1800355da  lea     rcx, [rsp+8C0h+var_860]
0x1800355df  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800355e4  mov     rcx, [rsp+8C0h+pv+8]; pv
0x1800355e9  call    cs:__imp_CoTaskMemFree
0x1800355ef  dec     dword ptr [rbx+0E8h]
0x1800355f5  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800355fc  call    cs:__imp_LeaveCriticalSection
0x180035602  nop
0x180035603  mov     rcx, [rbp+7C0h+var_30]
0x18003560a  xor     rcx, rsp; StackCookie
0x18003560d  call    __security_check_cookie
0x180035612  add     rsp, 8A8h
0x180035619  pop     rdi
0x18003561a  pop     rsi
0x18003561b  pop     rbx
0x18003561c  pop     rbp
0x18003561d  retn
```
