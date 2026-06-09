# tip2::details::shared_data<1,0,0>::start(void)

- ea: `0x18002edb4`
- end: `0x18002ef3b`
- name: `?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18002b310`

## callees

- `0x180002af0`
- `0x18000abe4`
- `0x18000b9ac`
- `0x1800238d8`
- `0x18002e17c`
- `0x18002ebe0`
- `0x18002edb4`
- `0x18002f92c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ee9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ee9a`

## string_xrefs

- `0x18002ee93`: `TestCreate`

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
0x18002edb4  mov     [rsp-8+arg_10], rbx
0x18002edb9  push    rbp
0x18002edba  push    rsi
0x18002edbb  push    rdi
0x18002edbc  push    r12
0x18002edbe  push    r13
0x18002edc0  push    r14
0x18002edc2  push    r15
0x18002edc4  lea     rbp, [rsp-790h]
0x18002edcc  sub     rsp, 890h
0x18002edd3  mov     rax, cs:__security_cookie
0x18002edda  xor     rax, rsp
0x18002eddd  mov     [rbp+7C0h+var_40], rax
0x18002ede4  mov     r14, rdx
0x18002ede7  mov     rbx, rcx
0x18002edea  lea     rdx, [rcx+0C0h]
0x18002edf1  lea     rcx, [rsp+8C0h+var_878]
0x18002edf6  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18002edfb  mov     [rsp+8C0h+var_870], 0
0x18002ee04  mov     [rsp+8C0h+var_868], 0
0x18002ee09  lea     rax, [rsp+8C0h+var_867]
0x18002ee0e  mov     [rbp+7C0h+var_60], rax
0x18002ee15  lea     rax, [rbp+7C0h+var_67]
0x18002ee1c  mov     [rbp+7C0h+var_50], rax
0x18002ee23  mov     [rsp+8C0h+var_867], 80408040h
0x18002ee2b  mov     [rsp+8C0h+var_863], 0
0x18002ee30  lea     rax, [rsp+8C0h+var_862]
0x18002ee35  mov     [rbp+7C0h+var_58], rax
0x18002ee3c  lea     rdi, [rbx+90h]
0x18002ee43  test    dword ptr [rbx+40h], 800h
0x18002ee4a  jz      short loc_18002EE64
0x18002ee4c  mov     r8d, 1
0x18002ee52  lea     rdx, [rsp+8C0h+var_870]
0x18002ee57  mov     rcx, rbx
0x18002ee5a  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18002ee5f  mov     r15, rax
0x18002ee62  jmp     short loc_18002EE67
0x18002ee64  xor     r15d, r15d
0x18002ee67  mov     rsi, rdi
0x18002ee6a  mov     r12, rdi
0x18002ee6d  mov     r13d, [rbx+14h]
0x18002ee71  mov     al, [rbx+20h]
0x18002ee74  mov     [rsp+8C0h+var_880], al
0x18002ee78  mov     eax, [rbx+10h]
0x18002ee7b  mov     [rsp+8C0h+var_87C], eax
0x18002ee7f  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18002ee86  test    rax, rax
0x18002ee89  jnz     short loc_18002EEBB
0x18002ee8b  call    tip_details_GetKernelBaseModuleHandle
0x18002ee90  mov     rcx, rax; hModule
0x18002ee93  lea     rdx, aTestcreate; "TestCreate"
0x18002ee9a  call    cs:__imp_GetProcAddress
0x18002eea1  nop     dword ptr [rax+rax+00h]
0x18002eea6  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18002eead  test    rax, rax
0x18002eeb0  jnz     short loc_18002EEBB
0x18002eeb2  xorps   xmm0, xmm0
0x18002eeb5  movdqu  xmmword ptr [rdi], xmm0
0x18002eeb9  jmp     short loc_18002EED8
0x18002eebb  mov     [rsp+8C0h+var_898], r12
0x18002eec0  mov     [rsp+8C0h+var_8A0], r15
0x18002eec5  mov     r9d, r13d
0x18002eec8  mov     r8b, [rsp+8C0h+var_880]
0x18002eecd  xor     edx, edx
0x18002eecf  mov     ecx, [rsp+8C0h+var_87C]
0x18002eed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eed8  lea     rcx, [rbx+0F0h]
0x18002eedf  mov     rdx, rax
0x18002eee2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHTIPTEST__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::reset(HTIPTEST__ *)
0x18002eee7  mov     dword ptr [rbx+0B8h], 1
0x18002eef1  movups  xmm0, xmmword ptr [rsi]
0x18002eef4  movdqu  xmmword ptr [r14], xmm0
0x18002eef9  lea     rcx, [rsp+8C0h+var_870]
0x18002eefe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002ef03  lea     rcx, [rsp+8C0h+var_878]
0x18002ef08  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002ef0d  mov     rax, r14
0x18002ef10  mov     rcx, [rbp+7C0h+var_40]
0x18002ef17  xor     rcx, rsp; StackCookie
0x18002ef1a  call    __security_check_cookie
0x18002ef1f  mov     rbx, [rsp+8C0h+arg_10]
0x18002ef27  add     rsp, 890h
0x18002ef2e  pop     r15
0x18002ef30  pop     r14
0x18002ef32  pop     r13
0x18002ef34  pop     r12
0x18002ef36  pop     rdi
0x18002ef37  pop     rsi
0x18002ef38  pop     rbp
0x18002ef39  retn
```
