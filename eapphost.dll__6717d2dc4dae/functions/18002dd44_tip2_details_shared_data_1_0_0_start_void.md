# tip2::details::shared_data<1,0,0>::start(void)

- ea: `0x18002dd44`
- end: `0x18002dec4`
- name: `?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18002a4fc`

## callees

- `0x180002a90`
- `0x18000a780`
- `0x18000b4cc`
- `0x180022ca0`
- `0x18002d108`
- `0x18002db70`
- `0x18002dd44`
- `0x18002e844`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002de2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002de2a`

## string_xrefs

- `0x18002de23`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<1,0,0>::start(__int64 a1, _OWORD *a2)
{
  __int64 v4; // r8
  _OWORD *v5; // rdi
  __int64 v6; // r15
  unsigned int v7; // r13d
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  char v11; // [rsp+40h] [rbp-C0h]
  unsigned int v12; // [rsp+44h] [rbp-BCh]
  _BYTE v13[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v14; // [rsp+50h] [rbp-B0h] BYREF
  char v15; // [rsp+58h] [rbp-A8h]
  int v16; // [rsp+59h] [rbp-A7h] BYREF
  char v17; // [rsp+5Dh] [rbp-A3h]
  char v18; // [rsp+5Eh] [rbp-A2h] BYREF
  char v19; // [rsp+859h] [rbp+759h] BYREF
  int *v20; // [rsp+860h] [rbp+760h]
  char *v21; // [rsp+868h] [rbp+768h]
  char *v22; // [rsp+870h] [rbp+770h]

  wil::EnterCriticalSection(v13, a1 + 192);
  v14 = 0;
  v15 = 0;
  v20 = &v16;
  v22 = &v19;
  v16 = -2143256512;
  v17 = 0;
  v21 = &v18;
  v5 = (_OWORD *)(a1 + 144);
  if ( (*(_DWORD *)(a1 + 64) & 0x800) != 0 )
    v6 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &v14, 1);
  else
    v6 = 0;
  v7 = *(_DWORD *)(a1 + 20);
  v11 = *(_BYTE *)(a1 + 32);
  v12 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestCreate"),
        (`TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress) != 0) )
  {
    LOBYTE(v4) = v11;
    ProcAddress = (FARPROC)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, _OWORD *))ProcAddress)(
                             v12,
                             0,
                             v4,
                             v7,
                             v6,
                             v5);
  }
  else
  {
    *v5 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(
    a1 + 240,
    ProcAddress);
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *v5;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v13);
  return a2;
}

```

## disassembly

```asm
0x18002dd44  mov     [rsp-8+arg_10], rbx
0x18002dd49  push    rbp
0x18002dd4a  push    rsi
0x18002dd4b  push    rdi
0x18002dd4c  push    r12
0x18002dd4e  push    r13
0x18002dd50  push    r14
0x18002dd52  push    r15
0x18002dd54  lea     rbp, [rsp-790h]
0x18002dd5c  sub     rsp, 890h
0x18002dd63  mov     rax, cs:__security_cookie
0x18002dd6a  xor     rax, rsp
0x18002dd6d  mov     [rbp+7C0h+var_40], rax
0x18002dd74  mov     r14, rdx
0x18002dd77  mov     rbx, rcx
0x18002dd7a  lea     rdx, [rcx+0C0h]
0x18002dd81  lea     rcx, [rsp+8C0h+var_878]
0x18002dd86  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18002dd8b  mov     [rsp+8C0h+var_870], 0
0x18002dd94  mov     [rsp+8C0h+var_868], 0
0x18002dd99  lea     rax, [rsp+8C0h+var_867]
0x18002dd9e  mov     [rbp+7C0h+var_60], rax
0x18002dda5  lea     rax, [rbp+7C0h+var_67]
0x18002ddac  mov     [rbp+7C0h+var_50], rax
0x18002ddb3  mov     [rsp+8C0h+var_867], 80408040h
0x18002ddbb  mov     [rsp+8C0h+var_863], 0
0x18002ddc0  lea     rax, [rsp+8C0h+var_862]
0x18002ddc5  mov     [rbp+7C0h+var_58], rax
0x18002ddcc  lea     rdi, [rbx+90h]
0x18002ddd3  test    dword ptr [rbx+40h], 800h
0x18002ddda  jz      short loc_18002DDF4
0x18002dddc  mov     r8d, 1
0x18002dde2  lea     rdx, [rsp+8C0h+var_870]
0x18002dde7  mov     rcx, rbx
0x18002ddea  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18002ddef  mov     r15, rax
0x18002ddf2  jmp     short loc_18002DDF7
0x18002ddf4  xor     r15d, r15d
0x18002ddf7  mov     rsi, rdi
0x18002ddfa  mov     r12, rdi
0x18002ddfd  mov     r13d, [rbx+14h]
0x18002de01  mov     al, [rbx+20h]
0x18002de04  mov     [rsp+8C0h+var_880], al
0x18002de08  mov     eax, [rbx+10h]
0x18002de0b  mov     [rsp+8C0h+var_87C], eax
0x18002de0f  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18002de16  test    rax, rax
0x18002de19  jnz     short loc_18002DE45
0x18002de1b  call    tip_details_GetKernelBaseModuleHandle
0x18002de20  mov     rcx, rax; hModule
0x18002de23  lea     rdx, aTestcreate; "TestCreate"
0x18002de2a  call    cs:__imp_GetProcAddress
0x18002de30  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18002de37  test    rax, rax
0x18002de3a  jnz     short loc_18002DE45
0x18002de3c  xorps   xmm0, xmm0
0x18002de3f  movdqu  xmmword ptr [rdi], xmm0
0x18002de43  jmp     short loc_18002DE62
0x18002de45  mov     [rsp+8C0h+var_898], r12
0x18002de4a  mov     [rsp+8C0h+var_8A0], r15
0x18002de4f  mov     r9d, r13d
0x18002de52  mov     r8b, [rsp+8C0h+var_880]
0x18002de57  xor     edx, edx
0x18002de59  mov     ecx, [rsp+8C0h+var_87C]
0x18002de5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de62  lea     rcx, [rbx+0F0h]
0x18002de69  mov     rdx, rax
0x18002de6c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x18002de71  mov     dword ptr [rbx+0B8h], 1
0x18002de7b  movups  xmm0, xmmword ptr [rsi]
0x18002de7e  movdqu  xmmword ptr [r14], xmm0
0x18002de83  lea     rcx, [rsp+8C0h+var_870]
0x18002de88  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002de8d  lea     rcx, [rsp+8C0h+var_878]
0x18002de92  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002de97  mov     rax, r14
0x18002de9a  mov     rcx, [rbp+7C0h+var_40]
0x18002dea1  xor     rcx, rsp; StackCookie
0x18002dea4  call    __security_check_cookie
0x18002dea9  mov     rbx, [rsp+8C0h+arg_10]
0x18002deb1  add     rsp, 890h
0x18002deb8  pop     r15
0x18002deba  pop     r14
0x18002debc  pop     r13
0x18002debe  pop     r12
0x18002dec0  pop     rdi
0x18002dec1  pop     rsi
0x18002dec2  pop     rbp
0x18002dec3  retn
```
