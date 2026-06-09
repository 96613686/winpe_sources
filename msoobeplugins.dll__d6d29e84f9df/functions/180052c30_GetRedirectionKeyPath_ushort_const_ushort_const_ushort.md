# GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)

- ea: `0x180052c30`
- end: `0x180052d0c`
- name: `?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z`
- size: `220`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800516c8`
- `0x180051c54`
- `0x180051d8c`
- `0x180051ec4`
- `0x180052dc4`
- `0x1800553b8`
- `0x1800554e0`
- `0x180055608`
- `0x180072730`

## callees

- `0x180008544`
- `0x18000b358`
- `0x18001e9a4`
- `0x180052c30`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180052c61`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180052c98`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180052c61`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180052c98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052c72`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetRedirectionKeyPath(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbx
  __int64 v10; // r9
  int v11; // eax
  unsigned int v12; // ebx
  SIZE_T *p_cb; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  SIZE_T cb; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int16 *v17; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  LODWORD(cb) = 0;
  p_cb = &cb;
  if ( (unsigned int)GetPersistedRegistryLocationW(a1, a2, a3, 0) == 234 )
  {
    v8 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)cb);
    v17 = v8;
    v9 = v8;
    if ( v8 )
    {
      LODWORD(p_cb) = 0;
      if ( !(unsigned int)GetPersistedRegistryLocationW(a1, a2, v8, (unsigned int)cb) )
      {
        v17 = 0;
        *a3 = v9;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
  }
  if ( *a3 )
    return 0;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  v11 = _AllocStringWorker<CTCoAllocPolicy>(v7, v6, a2);
  v12 = v11;
  if ( v11 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2E,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\OobeRedirectionKeyHelper.h",
    (const char *)(unsigned int)v11,
    (int)p_cb);
  return v12;
}

```

## disassembly

```asm
0x180052c30  mov     r11, rsp
0x180052c33  mov     [r11+8], rbx
0x180052c37  mov     [r11+10h], rbp
0x180052c3b  push    rsi
0x180052c3c  push    rdi
0x180052c3d  push    r14
0x180052c3f  sub     rsp, 30h
0x180052c43  xor     r14d, r14d
0x180052c46  lea     rax, [r11+18h]
0x180052c4a  xor     r9d, r9d
0x180052c4d  mov     [r8], r14
0x180052c50  mov     [r11+18h], r14d
0x180052c54  mov     rdi, r8
0x180052c57  mov     [r11-28h], rax
0x180052c5b  mov     rsi, rdx
0x180052c5e  mov     rbp, rcx
0x180052c61  call    cs:__imp_GetPersistedRegistryLocationW
0x180052c67  cmp     eax, 0EAh
0x180052c6c  jnz     short loc_180052CB4
0x180052c6e  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x180052c72  call    cs:__imp_CoTaskMemAlloc
0x180052c78  mov     [rsp+48h+arg_18], rax
0x180052c7d  mov     rbx, rax
0x180052c80  test    rax, rax
0x180052c83  jz      short loc_180052CAA
0x180052c85  mov     r9d, dword ptr [rsp+48h+cb]
0x180052c8a  mov     r8, rax
0x180052c8d  mov     rdx, rsi
0x180052c90  mov     qword ptr [rsp+48h+var_28], r14; int
0x180052c95  mov     rcx, rbp
0x180052c98  call    cs:__imp_GetPersistedRegistryLocationW
0x180052c9e  test    eax, eax
0x180052ca0  jnz     short loc_180052CAA
0x180052ca2  mov     [rsp+48h+arg_18], r14
0x180052ca7  mov     [rdi], rbx
0x180052caa  lea     rcx, [rsp+48h+arg_18]
0x180052caf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180052cb4  cmp     [rdi], r14
0x180052cb7  jnz     short loc_180052CF7
0x180052cb9  or      r9, 0FFFFFFFFFFFFFFFFh
0x180052cbd  inc     r9
0x180052cc0  cmp     [rsi+r9*2], r14w
0x180052cc5  jnz     short loc_180052CBD
0x180052cc7  mov     r8, rsi
0x180052cca  mov     [rsp+48h+var_20], rdi
0x180052ccf  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180052cd4  mov     ebx, eax
0x180052cd6  test    eax, eax
0x180052cd8  jns     short loc_180052CF7
0x180052cda  mov     rcx, [rsp+48h]; this
0x180052cdf  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\shell\\inc\\OobeR"...
0x180052ce6  mov     r9d, eax; char *
0x180052ce9  mov     edx, 2Eh ; '.'; void *
0x180052cee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052cf3  mov     eax, ebx
0x180052cf5  jmp     short loc_180052CF9
0x180052cf7  xor     eax, eax
0x180052cf9  mov     rbx, [rsp+48h+arg_0]
0x180052cfe  mov     rbp, [rsp+48h+arg_8]
0x180052d03  add     rsp, 30h
0x180052d07  pop     r14
0x180052d09  pop     rdi
0x180052d0a  pop     rsi
0x180052d0b  retn
```
