# tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)

- ea: `0x18002c7f4`
- end: `0x18002c917`
- name: `?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022438`

## callees

- `0x180002a90`
- `0x180022cc0`
- `0x18002b548`
- `0x18002c7f4`
- `0x18002d108`
- `0x18002e844`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c84f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c84f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c8ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c8ef`

## string_xrefs

- `0x18002c848`: `TestOpen`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::open_without_lock(__int64 a1, __int64 a2, __int64 a3)
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
        tip2::details::shared_data<1,0,0>::deserialize_data(a1, (__int64)&v11);
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
0x18002c7f4  mov     [rsp-18h+arg_10], rbx
0x18002c7f9  mov     [rsp-18h+arg_18], rsi
0x18002c7fe  push    rbp
0x18002c7ff  push    rdi
0x18002c800  push    r14
0x18002c802  mov     rbp, rsp
0x18002c805  sub     rsp, 70h
0x18002c809  mov     rax, cs:__security_cookie
0x18002c810  xor     rax, rsp
0x18002c813  mov     [rbp+var_8], rax
0x18002c817  mov     rdi, rdx
0x18002c81a  mov     rbx, rcx
0x18002c81d  xorps   xmm0, xmm0
0x18002c820  movups  [rbp+var_38], xmm0
0x18002c824  movups  xmmword ptr [rbp+pv], xmm0
0x18002c828  movups  [rbp+var_18], xmm0
0x18002c82c  mov     sil, [rcx+20h]
0x18002c830  mov     r14d, [rcx+10h]
0x18002c834  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18002c83b  test    rax, rax
0x18002c83e  jnz     short loc_18002C876
0x18002c840  call    tip_details_GetKernelBaseModuleHandle
0x18002c845  mov     rcx, rax; hModule
0x18002c848  lea     rdx, aTestopen; "TestOpen"
0x18002c84f  call    cs:__imp_GetProcAddress
0x18002c855  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18002c85c  test    rax, rax
0x18002c85f  jnz     short loc_18002C876
0x18002c861  xorps   xmm0, xmm0
0x18002c864  movups  [rbp+var_38], xmm0
0x18002c868  movups  xmmword ptr [rbp+pv], xmm0
0x18002c86c  movups  [rbp+var_18], xmm0
0x18002c870  mov     [rbp+var_40], rax
0x18002c874  jmp     short loc_18002C8E2
0x18002c876  lea     rcx, [rbp+var_38]
0x18002c87a  mov     [rsp+70h+var_50], rcx
0x18002c87f  mov     r9, rdi
0x18002c882  mov     r8b, sil
0x18002c885  mov     edx, 200002h
0x18002c88a  mov     ecx, r14d
0x18002c88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c892  mov     [rbp+var_40], rax
0x18002c896  test    rax, rax
0x18002c899  jz      short loc_18002C8E2
0x18002c89b  movups  xmm0, [rbp+var_38]
0x18002c89f  movdqu  xmmword ptr [rbx+90h], xmm0
0x18002c8a7  mov     [rbp+var_40], 0
0x18002c8af  lea     rcx, [rbx+0F0h]
0x18002c8b6  mov     rdx, rax
0x18002c8b9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x18002c8be  mov     eax, dword ptr [rbp+pv+4]
0x18002c8c1  or      [rbx+40h], eax
0x18002c8c4  cmp     [rbp+pv+8], 0
0x18002c8c9  jz      short loc_18002C8D9
0x18002c8cb  lea     rdx, [rbp+var_38]
0x18002c8cf  mov     rcx, rbx
0x18002c8d2  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18002c8d7  jmp     short loc_18002C8E2
0x18002c8d9  mov     eax, dword ptr [rbp+pv]
0x18002c8dc  mov     [rbx+0B8h], eax
0x18002c8e2  lea     rcx, [rbp+var_40]
0x18002c8e6  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18002c8eb  mov     rcx, [rbp+pv+8]; pv
0x18002c8ef  call    cs:__imp_CoTaskMemFree
0x18002c8f5  nop
0x18002c8f6  mov     rcx, [rbp+var_8]
0x18002c8fa  xor     rcx, rsp; StackCookie
0x18002c8fd  call    __security_check_cookie
0x18002c902  lea     r11, [rsp+70h+var_s0]
0x18002c907  mov     rbx, [r11+30h]
0x18002c90b  mov     rsi, [r11+38h]
0x18002c90f  mov     rsp, r11
0x18002c912  pop     r14
0x18002c914  pop     rdi
0x18002c915  pop     rbp
0x18002c916  retn
```
