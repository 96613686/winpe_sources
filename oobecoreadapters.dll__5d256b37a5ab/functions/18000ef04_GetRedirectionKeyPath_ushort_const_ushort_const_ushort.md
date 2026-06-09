# GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)

- ea: `0x18000ef04`
- end: `0x18000efe0`
- name: `?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z`
- size: `220`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bfc8`
- `0x18000c0d4`
- `0x18000c1e0`
- `0x18000cd14`
- `0x18000ce4c`
- `0x18000cf84`
- `0x18000fcd0`

## callees

- `0x1800076d4`
- `0x180009814`
- `0x18000d0bc`
- `0x18000ef04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ef46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ef46`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000ef35`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000ef6c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000ef35`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000ef6c`

## pseudocode

```c
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
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
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
0x18000ef04  mov     r11, rsp
0x18000ef07  mov     [r11+8], rbx
0x18000ef0b  mov     [r11+10h], rbp
0x18000ef0f  push    rsi
0x18000ef10  push    rdi
0x18000ef11  push    r14
0x18000ef13  sub     rsp, 30h
0x18000ef17  xor     r14d, r14d
0x18000ef1a  lea     rax, [r11+18h]
0x18000ef1e  xor     r9d, r9d
0x18000ef21  mov     [r8], r14
0x18000ef24  mov     [r11+18h], r14d
0x18000ef28  mov     rdi, r8
0x18000ef2b  mov     [r11-28h], rax
0x18000ef2f  mov     rsi, rdx
0x18000ef32  mov     rbp, rcx
0x18000ef35  call    cs:__imp_GetPersistedRegistryLocationW
0x18000ef3b  cmp     eax, 0EAh
0x18000ef40  jnz     short loc_18000EF88
0x18000ef42  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x18000ef46  call    cs:__imp_CoTaskMemAlloc
0x18000ef4c  mov     [rsp+48h+arg_18], rax
0x18000ef51  mov     rbx, rax
0x18000ef54  test    rax, rax
0x18000ef57  jz      short loc_18000EF7E
0x18000ef59  mov     r9d, dword ptr [rsp+48h+cb]
0x18000ef5e  mov     r8, rax
0x18000ef61  mov     rdx, rsi
0x18000ef64  mov     qword ptr [rsp+48h+var_28], r14; int
0x18000ef69  mov     rcx, rbp
0x18000ef6c  call    cs:__imp_GetPersistedRegistryLocationW
0x18000ef72  test    eax, eax
0x18000ef74  jnz     short loc_18000EF7E
0x18000ef76  mov     [rsp+48h+arg_18], r14
0x18000ef7b  mov     [rdi], rbx
0x18000ef7e  lea     rcx, [rsp+48h+arg_18]
0x18000ef83  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ef88  cmp     [rdi], r14
0x18000ef8b  jnz     short loc_18000EFCB
0x18000ef8d  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000ef91  inc     r9
0x18000ef94  cmp     [rsi+r9*2], r14w
0x18000ef99  jnz     short loc_18000EF91
0x18000ef9b  mov     r8, rsi
0x18000ef9e  mov     [rsp+48h+var_20], rdi
0x18000efa3  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18000efa8  mov     ebx, eax
0x18000efaa  test    eax, eax
0x18000efac  jns     short loc_18000EFCB
0x18000efae  mov     rcx, [rsp+48h]; this
0x18000efb3  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\shell\\inc\\OobeR"...
0x18000efba  mov     r9d, eax; char *
0x18000efbd  mov     edx, 2Eh ; '.'; void *
0x18000efc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000efc7  mov     eax, ebx
0x18000efc9  jmp     short loc_18000EFCD
0x18000efcb  xor     eax, eax
0x18000efcd  mov     rbx, [rsp+48h+arg_0]
0x18000efd2  mov     rbp, [rsp+48h+arg_8]
0x18000efd7  add     rsp, 30h
0x18000efdb  pop     r14
0x18000efdd  pop     rdi
0x18000efde  pop     rsi
0x18000efdf  retn
```
