# tip2::details::shared_data<1,0,1>::open_without_lock(_GUID *)

- ea: `0x18003d258`
- end: `0x18003d37b`
- name: `?open_without_lock@?$shared_data@$00$0A@$00@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003ba08`

## callees

- `0x180019190`
- `0x18002771c`
- `0x18002a3d0`
- `0x1800305e8`
- `0x180033db8`
- `0x18003d258`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d2b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d2b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d353`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d353`

## string_xrefs

- `0x18003d2ac`: `TestOpen`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,1>::open_without_lock(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // si
  unsigned int v6; // r14d
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  __int64 v9; // rax
  __int64 v10; // [rsp+30h] [rbp-40h] BYREF
  __int128 v11; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+48h] [rbp-28h]
  __int128 v13; // [rsp+58h] [rbp-18h]

  v11 = 0;
  *(_OWORD *)pv = 0;
  v13 = 0;
  v5 = *(_BYTE *)(a1 + 32);
  v6 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestOpen'::`2'::s_pfnTestOpen;
  if ( `TestOpen'::`2'::s_pfnTestOpen
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestOpen"),
        (`TestOpen'::`2'::s_pfnTestOpen = (__int64)ProcAddress) != 0) )
  {
    LOBYTE(a3) = v5;
    v9 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64, __int128 *))ProcAddress)(v6, 2097154, a3, a2, &v11);
    v10 = v9;
    if ( v9 )
    {
      *(_OWORD *)(a1 + 144) = v11;
      v10 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(
        a1 + 240,
        v9);
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( pv[1] )
        tip2::details::shared_data<1,0,1>::deserialize_data(a1, &v11);
      else
        *(_DWORD *)(a1 + 184) = pv[0];
    }
  }
  else
  {
    v11 = 0;
    *(_OWORD *)pv = 0;
    v13 = 0;
    v10 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(&v10);
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x18003d258  mov     [rsp-18h+arg_10], rbx
0x18003d25d  mov     [rsp-18h+arg_18], rsi
0x18003d262  push    rbp
0x18003d263  push    rdi
0x18003d264  push    r14
0x18003d266  mov     rbp, rsp
0x18003d269  sub     rsp, 70h
0x18003d26d  mov     rax, cs:__security_cookie
0x18003d274  xor     rax, rsp
0x18003d277  mov     [rbp+var_8], rax
0x18003d27b  mov     rdi, rdx
0x18003d27e  mov     rbx, rcx
0x18003d281  xorps   xmm0, xmm0
0x18003d284  movups  [rbp+var_38], xmm0
0x18003d288  movups  xmmword ptr [rbp+pv], xmm0
0x18003d28c  movups  [rbp+var_18], xmm0
0x18003d290  mov     sil, [rcx+20h]
0x18003d294  mov     r14d, [rcx+10h]
0x18003d298  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18003d29f  test    rax, rax
0x18003d2a2  jnz     short loc_18003D2DA
0x18003d2a4  call    tip_details_GetKernelBaseModuleHandle
0x18003d2a9  mov     rcx, rax; hModule
0x18003d2ac  lea     rdx, aTestopen; "TestOpen"
0x18003d2b3  call    cs:__imp_GetProcAddress
0x18003d2b9  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18003d2c0  test    rax, rax
0x18003d2c3  jnz     short loc_18003D2DA
0x18003d2c5  xorps   xmm0, xmm0
0x18003d2c8  movups  [rbp+var_38], xmm0
0x18003d2cc  movups  xmmword ptr [rbp+pv], xmm0
0x18003d2d0  movups  [rbp+var_18], xmm0
0x18003d2d4  mov     [rbp+var_40], rax
0x18003d2d8  jmp     short loc_18003D346
0x18003d2da  lea     rcx, [rbp+var_38]
0x18003d2de  mov     [rsp+70h+var_50], rcx
0x18003d2e3  mov     r9, rdi
0x18003d2e6  mov     r8b, sil
0x18003d2e9  mov     edx, 200002h
0x18003d2ee  mov     ecx, r14d
0x18003d2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2f6  mov     [rbp+var_40], rax
0x18003d2fa  test    rax, rax
0x18003d2fd  jz      short loc_18003D346
0x18003d2ff  movups  xmm0, [rbp+var_38]
0x18003d303  movdqu  xmmword ptr [rbx+90h], xmm0
0x18003d30b  mov     [rbp+var_40], 0
0x18003d313  lea     rcx, [rbx+0F0h]
0x18003d31a  mov     rdx, rax
0x18003d31d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x18003d322  mov     eax, dword ptr [rbp+pv+4]
0x18003d325  or      [rbx+40h], eax
0x18003d328  cmp     [rbp+pv+8], 0
0x18003d32d  jz      short loc_18003D33D
0x18003d32f  lea     rdx, [rbp+var_38]
0x18003d333  mov     rcx, rbx
0x18003d336  call    ?deserialize_data@?$shared_data@$00$0A@$00@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,1>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18003d33b  jmp     short loc_18003D346
0x18003d33d  mov     eax, dword ptr [rbp+pv]
0x18003d340  mov     [rbx+0B8h], eax
0x18003d346  lea     rcx, [rbp+var_40]
0x18003d34a  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18003d34f  mov     rcx, [rbp+pv+8]; pv
0x18003d353  call    cs:__imp_CoTaskMemFree
0x18003d359  nop
0x18003d35a  mov     rcx, [rbp+var_8]
0x18003d35e  xor     rcx, rsp; StackCookie
0x18003d361  call    __security_check_cookie
0x18003d366  lea     r11, [rsp+70h+var_s0]
0x18003d36b  mov     rbx, [r11+30h]
0x18003d36f  mov     rsi, [r11+38h]
0x18003d373  mov     rsp, r11
0x18003d376  pop     r14
0x18003d378  pop     rdi
0x18003d379  pop     rbp
0x18003d37a  retn
```
