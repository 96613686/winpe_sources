# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x14000d390`
- end: `0x14000d539`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x140007f54`

## callees

- `0x140004b80`
- `0x140005044`
- `0x1400050bc`
- `0x140005460`
- `0x1400060e4`
- `0x14000d1bc`
- `0x14000d390`
- `0x14000dde4`
- `0x14000e13c`
- `0x140025d70`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000d47c`
- `KERNEL32!GetProcAddress` at `0x14000d47c`

## string_xrefs

- `0x14000d475`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  __int64 v4; // r8
  bool v5; // al
  _OWORD *v6; // rsi
  __int64 v7; // r14
  unsigned int v8; // edi
  char v9; // r12
  unsigned int v10; // r13d
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  __int64 v13; // r14
  __int64 v14; // rdi
  _BYTE v16[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v18; // [rsp+50h] [rbp-B0h] BYREF
  char v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+59h] [rbp-A7h] BYREF
  char v21; // [rsp+5Dh] [rbp-A3h]
  char v22; // [rsp+5Eh] [rbp-A2h] BYREF
  char v23; // [rsp+859h] [rbp+759h] BYREF
  int *v24; // [rsp+860h] [rbp+760h]
  char *v25; // [rsp+868h] [rbp+768h]
  char *v26; // [rsp+870h] [rbp+770h]

  wil::EnterCriticalSection(v17, a1 + 192);
  v18 = 0;
  v19 = 0;
  v24 = &v20;
  v26 = &v23;
  v20 = -2143256512;
  v21 = 0;
  v25 = &v22;
  v5 = (*(_DWORD *)(a1 + 64) & 0x800) != 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0;
  v6 = (_OWORD *)(a1 + 144);
  if ( v5 )
    v7 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v18, 1);
  else
    v7 = 0;
  v8 = *(_DWORD *)(a1 + 20);
  v9 = *(_BYTE *)(a1 + 32);
  v10 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestCreate"),
        (`TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress) != 0) )
  {
    LOBYTE(v4) = v9;
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))ProcAddress)(
            v10,
            0,
            v4,
            v8,
            v7,
            a1 + 144);
  }
  else
  {
    *v6 = 0;
    v13 = 0;
  }
  v14 = *(_QWORD *)(a1 + 240);
  if ( v14 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v16);
    TestClose(v14);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v16);
  }
  *(_QWORD *)(a1 + 240) = v13;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *v6;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v17);
  return a2;
}

```

## disassembly

```asm
0x14000d390  mov     [rsp-8+arg_10], rbx
0x14000d395  push    rbp
0x14000d396  push    rsi
0x14000d397  push    rdi
0x14000d398  push    r12
0x14000d39a  push    r13
0x14000d39c  push    r14
0x14000d39e  push    r15
0x14000d3a0  lea     rbp, [rsp-790h]
0x14000d3a8  sub     rsp, 890h
0x14000d3af  mov     rax, cs:__security_cookie
0x14000d3b6  xor     rax, rsp
0x14000d3b9  mov     [rbp+7C0h+var_40], rax
0x14000d3c0  mov     r15, rdx
0x14000d3c3  mov     rbx, rcx
0x14000d3c6  lea     rdx, [rcx+0C0h]
0x14000d3cd  lea     rcx, [rsp+8C0h+var_878]
0x14000d3d2  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x14000d3d7  mov     [rsp+8C0h+var_870], 0
0x14000d3e0  mov     [rsp+8C0h+var_868], 0
0x14000d3e5  lea     rax, [rsp+8C0h+var_867]
0x14000d3ea  mov     [rbp+7C0h+var_60], rax
0x14000d3f1  lea     rax, [rbp+7C0h+var_67]
0x14000d3f8  mov     [rbp+7C0h+var_50], rax
0x14000d3ff  mov     [rsp+8C0h+var_867], 80408040h
0x14000d407  mov     [rsp+8C0h+var_863], 0
0x14000d40c  lea     rax, [rsp+8C0h+var_862]
0x14000d411  mov     [rbp+7C0h+var_58], rax
0x14000d418  test    dword ptr [rbx+40h], 800h
0x14000d41f  jz      short loc_14000D42E
0x14000d421  test    dword ptr [rbx+14h], 8000h
0x14000d428  jnz     short loc_14000D42E
0x14000d42a  mov     al, 1
0x14000d42c  jmp     short loc_14000D430
0x14000d42e  xor     al, al
0x14000d430  lea     rsi, [rbx+90h]
0x14000d437  test    al, al
0x14000d439  jz      short loc_14000D453
0x14000d43b  mov     r8d, 1
0x14000d441  lea     rdx, [rsp+8C0h+var_870]
0x14000d446  mov     rcx, rbx
0x14000d449  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x14000d44e  mov     r14, rax
0x14000d451  jmp     short loc_14000D456
0x14000d453  xor     r14d, r14d
0x14000d456  mov     edi, [rbx+14h]
0x14000d459  mov     r12b, [rbx+20h]
0x14000d45d  mov     r13d, [rbx+10h]
0x14000d461  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x14000d468  test    rax, rax
0x14000d46b  jnz     short loc_14000D49A
0x14000d46d  call    tip_details_GetKernelBaseModuleHandle
0x14000d472  mov     rcx, rax; hModule
0x14000d475  lea     rdx, aTestcreate; "TestCreate"
0x14000d47c  call    cs:__imp_GetProcAddress
0x14000d482  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x14000d489  test    rax, rax
0x14000d48c  jnz     short loc_14000D49A
0x14000d48e  xorps   xmm0, xmm0
0x14000d491  movdqu  xmmword ptr [rsi], xmm0
0x14000d495  xor     r14d, r14d
0x14000d498  jmp     short loc_14000D4B7
0x14000d49a  mov     [rsp+8C0h+var_898], rsi
0x14000d49f  mov     [rsp+8C0h+var_8A0], r14
0x14000d4a4  mov     r9d, edi
0x14000d4a7  mov     r8b, r12b
0x14000d4aa  xor     edx, edx
0x14000d4ac  mov     ecx, r13d
0x14000d4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d4b4  mov     r14, rax
0x14000d4b7  mov     rdi, [rbx+0F0h]
0x14000d4be  test    rdi, rdi
0x14000d4c1  jz      short loc_14000D4DF
0x14000d4c3  lea     rcx, [rsp+8C0h+var_880]; this
0x14000d4c8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000d4cd  mov     rcx, rdi
0x14000d4d0  call    TestClose
0x14000d4d5  lea     rcx, [rsp+8C0h+var_880]; this
0x14000d4da  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000d4df  mov     [rbx+0F0h], r14
0x14000d4e6  mov     dword ptr [rbx+0B8h], 1
0x14000d4f0  movups  xmm0, xmmword ptr [rsi]
0x14000d4f3  movdqu  xmmword ptr [r15], xmm0
0x14000d4f8  lea     rcx, [rsp+8C0h+var_870]
0x14000d4fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000d502  lea     rcx, [rsp+8C0h+var_878]
0x14000d507  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x14000d50c  mov     rax, r15
0x14000d50f  mov     rcx, [rbp+7C0h+var_40]
0x14000d516  xor     rcx, rsp; StackCookie
0x14000d519  call    __security_check_cookie
0x14000d51e  mov     rbx, [rsp+8C0h+arg_10]
0x14000d526  add     rsp, 890h
0x14000d52d  pop     r15
0x14000d52f  pop     r14
0x14000d531  pop     r13
0x14000d533  pop     r12
0x14000d535  pop     rdi
0x14000d536  pop     rsi
0x14000d537  pop     rbp
0x14000d538  retn
```
