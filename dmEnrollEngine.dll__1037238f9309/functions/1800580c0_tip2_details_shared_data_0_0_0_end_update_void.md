# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x1800580c0`
- end: `0x180058236`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180054f88`

## callees

- `0x18002d46c`
- `0x18002e1a0`
- `0x1800580c0`
- `0x1800592b8`
- `0x180059a34`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005819d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005819d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058214`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058214`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058201`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058201`

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
0x1800580c0  push    rbp
0x1800580c2  push    rbx
0x1800580c3  push    rsi
0x1800580c4  push    rdi
0x1800580c5  lea     rbp, [rsp-7A8h]
0x1800580cd  sub     rsp, 8A8h
0x1800580d4  mov     rax, cs:__security_cookie
0x1800580db  xor     rax, rsp
0x1800580de  mov     [rbp+7C0h+var_30], rax
0x1800580e5  mov     rbx, rcx
0x1800580e8  bts     dword ptr [rcx+40h], 0Bh
0x1800580ed  cmp     qword ptr [rcx+0F0h], 0
0x1800580f5  jz      loc_180058207
0x1800580fb  test    dword ptr [rcx+40h], 100h
0x180058102  jnz     loc_180058207
0x180058108  test    dword ptr [rcx+14h], 8000h
0x18005810f  jnz     loc_180058207
0x180058115  xorps   xmm0, xmm0
0x180058118  movups  [rsp+8C0h+var_890], xmm0
0x18005811d  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x180058122  movups  [rsp+8C0h+var_870], xmm0
0x180058127  mov     [rsp+8C0h+var_860], 0
0x180058130  mov     [rsp+8C0h+var_858], 0
0x180058135  lea     rax, [rsp+8C0h+var_857]
0x18005813a  mov     [rbp+7C0h+var_50], rax
0x180058141  lea     rax, [rbp+7C0h+var_57]
0x180058148  mov     [rbp+7C0h+var_40], rax
0x18005814f  mov     [rsp+8C0h+var_857], 80408040h
0x180058157  mov     [rsp+8C0h+var_853], 0
0x18005815c  lea     rax, [rsp+8C0h+var_852]
0x180058161  mov     [rbp+7C0h+var_48], rax
0x180058168  mov     r8d, 1
0x18005816e  lea     rdx, [rsp+8C0h+var_860]
0x180058173  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180058178  mov     rdi, rax
0x18005817b  mov     rsi, [rbx+0F0h]
0x180058182  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180058189  test    rax, rax
0x18005818c  jnz     short loc_1800581C3
0x18005818e  call    tip_details_GetKernelBaseModuleHandle
0x180058193  mov     rcx, rax; hModule
0x180058196  lea     rdx, aTestunlockdata; "TestUnlockData"
0x18005819d  call    cs:__imp_GetProcAddress
0x1800581a3  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800581aa  test    rax, rax
0x1800581ad  jnz     short loc_1800581C3
0x1800581af  xorps   xmm0, xmm0
0x1800581b2  movups  [rsp+8C0h+var_890], xmm0
0x1800581b7  movups  xmmword ptr [rsp+8C0h+pv], xmm0
0x1800581bc  movups  [rsp+8C0h+var_870], xmm0
0x1800581c1  jmp     short loc_1800581D5
0x1800581c3  lea     r9, [rsp+8C0h+var_890]
0x1800581c8  mov     r8, rdi
0x1800581cb  xor     edx, edx
0x1800581cd  mov     rcx, rsi
0x1800581d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581d5  mov     rcx, [rsp+8C0h+pv]
0x1800581da  mov     rax, rcx
0x1800581dd  shr     rax, 20h
0x1800581e1  or      [rbx+40h], eax
0x1800581e4  cmp     [rsp+8C0h+pv+8], 0
0x1800581ea  jnz     short loc_1800581F2
0x1800581ec  mov     [rbx+0B8h], ecx
0x1800581f2  lea     rcx, [rsp+8C0h+var_860]
0x1800581f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800581fc  mov     rcx, [rsp+8C0h+pv+8]; pv
0x180058201  call    cs:__imp_CoTaskMemFree
0x180058207  dec     dword ptr [rbx+0E8h]
0x18005820d  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180058214  call    cs:__imp_LeaveCriticalSection
0x18005821a  nop
0x18005821b  mov     rcx, [rbp+7C0h+var_30]
0x180058222  xor     rcx, rsp; StackCookie
0x180058225  call    __security_check_cookie
0x18005822a  add     rsp, 8A8h
0x180058231  pop     rdi
0x180058232  pop     rsi
0x180058233  pop     rbx
0x180058234  pop     rbp
0x180058235  retn
```
