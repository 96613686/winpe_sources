# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x18002c650`
- end: `0x18002c78d`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002c23c`

## callees

- `0x180002af0`
- `0x1800238d8`
- `0x18002c4bc`
- `0x18002c650`
- `0x18002ebe0`
- `0x18002f61c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c760`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c747`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c747`

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
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v4);
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
0x18002c650  mov     [rsp-8+arg_8], rbx
0x18002c655  push    rbp
0x18002c656  lea     rbp, [rsp-790h]
0x18002c65e  sub     rsp, 890h
0x18002c665  mov     rax, cs:__security_cookie
0x18002c66c  xor     rax, rsp
0x18002c66f  mov     [rbp+790h+var_10], rax
0x18002c676  bts     dword ptr [rcx+40h], 0Bh
0x18002c67b  mov     rbx, rcx
0x18002c67e  cmp     qword ptr [rcx+0F0h], 0
0x18002c686  jz      loc_18002C753
0x18002c68c  test    dword ptr [rcx+40h], 100h
0x18002c693  jnz     loc_18002C753
0x18002c699  xorps   xmm0, xmm0
0x18002c69c  mov     [rsp+890h+var_840], 0
0x18002c6a5  lea     rax, [rsp+890h+var_837]
0x18002c6aa  mov     [rsp+890h+var_838], 0
0x18002c6af  mov     [rbp+790h+var_30], rax
0x18002c6b6  lea     rdx, [rsp+890h+var_840]
0x18002c6bb  lea     rax, [rbp+790h+var_37]
0x18002c6c2  mov     [rsp+890h+var_837], 80408040h
0x18002c6ca  mov     [rbp+790h+var_20], rax
0x18002c6d1  mov     r8d, 1
0x18002c6d7  lea     rax, [rsp+890h+var_832]
0x18002c6dc  mov     [rsp+890h+var_833], 0
0x18002c6e1  mov     [rbp+790h+var_28], rax
0x18002c6e8  movups  [rsp+890h+var_870], xmm0
0x18002c6ed  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18002c6f2  movups  [rsp+890h+var_850], xmm0
0x18002c6f7  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18002c6fc  mov     rcx, [rbx+0F0h]
0x18002c703  lea     r9, [rsp+890h+var_870]
0x18002c708  mov     r8, rax
0x18002c70b  call    TestUnlockData
0x18002c710  mov     eax, dword ptr [rsp+890h+pv+4]
0x18002c714  or      [rbx+40h], eax
0x18002c717  cmp     [rsp+890h+pv+8], 0
0x18002c71d  jz      short loc_18002C72E
0x18002c71f  lea     rdx, [rsp+890h+var_870]
0x18002c724  mov     rcx, rbx
0x18002c727  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18002c72c  jmp     short loc_18002C738
0x18002c72e  mov     eax, dword ptr [rsp+890h+pv]
0x18002c732  mov     [rbx+0B8h], eax
0x18002c738  lea     rcx, [rsp+890h+var_840]
0x18002c73d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002c742  mov     rcx, [rsp+890h+pv+8]; pv
0x18002c747  call    cs:__imp_CoTaskMemFree
0x18002c74e  nop     dword ptr [rax+rax+00h]
0x18002c753  dec     dword ptr [rbx+0E8h]
0x18002c759  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18002c760  call    cs:__imp_LeaveCriticalSection
0x18002c767  nop     dword ptr [rax+rax+00h]
0x18002c76c  mov     rcx, [rbp+790h+var_10]
0x18002c773  xor     rcx, rsp; StackCookie
0x18002c776  call    __security_check_cookie
0x18002c77b  mov     rbx, [rsp+890h+arg_8]
0x18002c783  add     rsp, 890h
0x18002c78a  pop     rbp
0x18002c78b  retn
```
