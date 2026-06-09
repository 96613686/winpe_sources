# tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)

- ea: `0x18002d79c`
- end: `0x18002d8cc`
- name: `?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800230a8`

## callees

- `0x180002af0`
- `0x1800238fc`
- `0x18002c4bc`
- `0x18002d79c`
- `0x18002e17c`
- `0x18002f92c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d7f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d7f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d89d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d89d`

## string_xrefs

- `0x18002d7f0`: `TestOpen`

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
        tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v11);
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
0x18002d79c  mov     [rsp-18h+arg_10], rbx
0x18002d7a1  mov     [rsp-18h+arg_18], rsi
0x18002d7a6  push    rbp
0x18002d7a7  push    rdi
0x18002d7a8  push    r14
0x18002d7aa  mov     rbp, rsp
0x18002d7ad  sub     rsp, 70h
0x18002d7b1  mov     rax, cs:__security_cookie
0x18002d7b8  xor     rax, rsp
0x18002d7bb  mov     [rbp+var_8], rax
0x18002d7bf  mov     rdi, rdx
0x18002d7c2  mov     rbx, rcx
0x18002d7c5  xorps   xmm0, xmm0
0x18002d7c8  movups  [rbp+var_38], xmm0
0x18002d7cc  movups  xmmword ptr [rbp+pv], xmm0
0x18002d7d0  movups  [rbp+var_18], xmm0
0x18002d7d4  mov     sil, [rcx+20h]
0x18002d7d8  mov     r14d, [rcx+10h]
0x18002d7dc  mov     rax, cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18002d7e3  test    rax, rax
0x18002d7e6  jnz     short loc_18002D824
0x18002d7e8  call    tip_details_GetKernelBaseModuleHandle
0x18002d7ed  mov     rcx, rax; hModule
0x18002d7f0  lea     rdx, aTestopen; "TestOpen"
0x18002d7f7  call    cs:__imp_GetProcAddress
0x18002d7fe  nop     dword ptr [rax+rax+00h]
0x18002d803  mov     cs:?s_pfnTestOpen@?1??TestOpen@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@PEAU_GUID@@PEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; HTIPTEST__ * (*`TestOpen'::`2'::s_pfnTestOpen)(uint,TestRetrievalOptions,TestStorage,_GUID *,TestInfo_ODR_guard::TestInfo *)
0x18002d80a  test    rax, rax
0x18002d80d  jnz     short loc_18002D824
0x18002d80f  xorps   xmm0, xmm0
0x18002d812  movups  [rbp+var_38], xmm0
0x18002d816  movups  xmmword ptr [rbp+pv], xmm0
0x18002d81a  movups  [rbp+var_18], xmm0
0x18002d81e  mov     [rbp+var_40], rax
0x18002d822  jmp     short loc_18002D890
0x18002d824  lea     rcx, [rbp+var_38]
0x18002d828  mov     [rsp+70h+var_50], rcx
0x18002d82d  mov     r9, rdi
0x18002d830  mov     r8b, sil
0x18002d833  mov     edx, 200002h
0x18002d838  mov     ecx, r14d
0x18002d83b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d840  mov     [rbp+var_40], rax
0x18002d844  test    rax, rax
0x18002d847  jz      short loc_18002D890
0x18002d849  movups  xmm0, [rbp+var_38]
0x18002d84d  movdqu  xmmword ptr [rbx+90h], xmm0
0x18002d855  mov     [rbp+var_40], 0
0x18002d85d  lea     rcx, [rbx+0F0h]
0x18002d864  mov     rdx, rax
0x18002d867  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x18002d86c  mov     eax, dword ptr [rbp+pv+4]
0x18002d86f  or      [rbx+40h], eax
0x18002d872  cmp     [rbp+pv+8], 0
0x18002d877  jz      short loc_18002D887
0x18002d879  lea     rdx, [rbp+var_38]
0x18002d87d  mov     rcx, rbx
0x18002d880  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18002d885  jmp     short loc_18002D890
0x18002d887  mov     eax, dword ptr [rbp+pv]
0x18002d88a  mov     [rbx+0B8h], eax
0x18002d890  lea     rcx, [rbp+var_40]
0x18002d894  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18002d899  mov     rcx, [rbp+pv+8]; pv
0x18002d89d  call    cs:__imp_CoTaskMemFree
0x18002d8a4  nop     dword ptr [rax+rax+00h]
0x18002d8a9  nop
0x18002d8aa  mov     rcx, [rbp+var_8]
0x18002d8ae  xor     rcx, rsp; StackCookie
0x18002d8b1  call    __security_check_cookie
0x18002d8b6  lea     r11, [rsp+70h+var_s0]
0x18002d8bb  mov     rbx, [r11+30h]
0x18002d8bf  mov     rsi, [r11+38h]
0x18002d8c3  mov     rsp, r11
0x18002d8c6  pop     r14
0x18002d8c8  pop     rdi
0x18002d8c9  pop     rbp
0x18002d8ca  retn
```
