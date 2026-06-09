# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x18002b6dc`
- end: `0x18002b80c`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `304`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b2d4`

## callees

- `0x180002a90`
- `0x180022ca0`
- `0x18002b548`
- `0x18002b6dc`
- `0x18002db70`
- `0x18002e55c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b7e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b7e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b7d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b7d3`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int128 v4; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h]
  __int128 v6; // [rsp+40h] [rbp-C0h]
  void *v7; // [rsp+50h] [rbp-B0h] BYREF
  char v8; // [rsp+58h] [rbp-A8h]
  int v9; // [rsp+59h] [rbp-A7h] BYREF
  char v10; // [rsp+5Dh] [rbp-A3h]
  char v11; // [rsp+5Eh] [rbp-A2h] BYREF
  char v12; // [rsp+859h] [rbp+759h] BYREF
  int *v13; // [rsp+860h] [rbp+760h]
  char *v14; // [rsp+868h] [rbp+768h]
  char *v15; // [rsp+870h] [rbp+770h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v7 = 0;
    v8 = 0;
    v13 = &v9;
    v9 = -2143256512;
    v15 = &v12;
    v10 = 0;
    v14 = &v11;
    v4 = 0;
    *(_OWORD *)pv = 0;
    v6 = 0;
    v2 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &v7, 1);
    TestUnlockData(*(_QWORD *)(a1 + 240), v3, v2, &v4);
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( pv[1] )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, (__int64)&v4);
    else
      *(_DWORD *)(a1 + 184) = pv[0];
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v7);
    CoTaskMemFree(pv[1]);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x18002b6dc  mov     [rsp-8+arg_8], rbx
0x18002b6e1  push    rbp
0x18002b6e2  lea     rbp, [rsp-790h]
0x18002b6ea  sub     rsp, 890h
0x18002b6f1  mov     rax, cs:__security_cookie
0x18002b6f8  xor     rax, rsp
0x18002b6fb  mov     [rbp+790h+var_10], rax
0x18002b702  bts     dword ptr [rcx+40h], 0Bh
0x18002b707  mov     rbx, rcx
0x18002b70a  cmp     qword ptr [rcx+0F0h], 0
0x18002b712  jz      loc_18002B7D9
0x18002b718  test    dword ptr [rcx+40h], 100h
0x18002b71f  jnz     loc_18002B7D9
0x18002b725  xorps   xmm0, xmm0
0x18002b728  mov     [rsp+890h+var_840], 0
0x18002b731  lea     rax, [rsp+890h+var_837]
0x18002b736  mov     [rsp+890h+var_838], 0
0x18002b73b  mov     [rbp+790h+var_30], rax
0x18002b742  lea     rdx, [rsp+890h+var_840]
0x18002b747  lea     rax, [rbp+790h+var_37]
0x18002b74e  mov     [rsp+890h+var_837], 80408040h
0x18002b756  mov     [rbp+790h+var_20], rax
0x18002b75d  mov     r8d, 1
0x18002b763  lea     rax, [rsp+890h+var_832]
0x18002b768  mov     [rsp+890h+var_833], 0
0x18002b76d  mov     [rbp+790h+var_28], rax
0x18002b774  movups  [rsp+890h+var_870], xmm0
0x18002b779  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18002b77e  movups  [rsp+890h+var_850], xmm0
0x18002b783  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18002b788  mov     rcx, [rbx+0F0h]
0x18002b78f  lea     r9, [rsp+890h+var_870]
0x18002b794  mov     r8, rax
0x18002b797  call    TestUnlockData
0x18002b79c  mov     eax, dword ptr [rsp+890h+pv+4]
0x18002b7a0  or      [rbx+40h], eax
0x18002b7a3  cmp     [rsp+890h+pv+8], 0
0x18002b7a9  jz      short loc_18002B7BA
0x18002b7ab  lea     rdx, [rsp+890h+var_870]
0x18002b7b0  mov     rcx, rbx
0x18002b7b3  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18002b7b8  jmp     short loc_18002B7C4
0x18002b7ba  mov     eax, dword ptr [rsp+890h+pv]
0x18002b7be  mov     [rbx+0B8h], eax
0x18002b7c4  lea     rcx, [rsp+890h+var_840]
0x18002b7c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b7ce  mov     rcx, [rsp+890h+pv+8]; pv
0x18002b7d3  call    cs:__imp_CoTaskMemFree
0x18002b7d9  dec     dword ptr [rbx+0E8h]
0x18002b7df  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18002b7e6  call    cs:__imp_LeaveCriticalSection
0x18002b7ec  mov     rcx, [rbp+790h+var_10]
0x18002b7f3  xor     rcx, rsp; StackCookie
0x18002b7f6  call    __security_check_cookie
0x18002b7fb  mov     rbx, [rsp+890h+arg_8]
0x18002b803  add     rsp, 890h
0x18002b80a  pop     rbp
0x18002b80b  retn
```
