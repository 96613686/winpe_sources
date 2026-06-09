# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x18004f468`
- end: `0x18004f598`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180029d0c`

## callees

- `0x18000c444`
- `0x1800278ac`
- `0x180028168`
- `0x18002a3d0`
- `0x180033d3c`
- `0x18004f468`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f572`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f572`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f55f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f55f`

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
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &v7, 1);
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
0x18004f468  mov     [rsp-8+arg_8], rbx
0x18004f46d  push    rbp
0x18004f46e  lea     rbp, [rsp-790h]
0x18004f476  sub     rsp, 890h
0x18004f47d  mov     rax, cs:__security_cookie
0x18004f484  xor     rax, rsp
0x18004f487  mov     [rbp+790h+var_10], rax
0x18004f48e  bts     dword ptr [rcx+40h], 0Bh
0x18004f493  mov     rbx, rcx
0x18004f496  cmp     qword ptr [rcx+0F0h], 0
0x18004f49e  jz      loc_18004F565
0x18004f4a4  test    dword ptr [rcx+40h], 100h
0x18004f4ab  jnz     loc_18004F565
0x18004f4b1  xorps   xmm0, xmm0
0x18004f4b4  mov     [rsp+890h+var_840], 0
0x18004f4bd  lea     rax, [rsp+890h+var_837]
0x18004f4c2  mov     [rsp+890h+var_838], 0
0x18004f4c7  mov     [rbp+790h+var_30], rax
0x18004f4ce  lea     rdx, [rsp+890h+var_840]
0x18004f4d3  lea     rax, [rbp+790h+var_37]
0x18004f4da  mov     [rsp+890h+var_837], 80408040h
0x18004f4e2  mov     [rbp+790h+var_20], rax
0x18004f4e9  mov     r8d, 1
0x18004f4ef  lea     rax, [rsp+890h+var_832]
0x18004f4f4  mov     [rsp+890h+var_833], 0
0x18004f4f9  mov     [rbp+790h+var_28], rax
0x18004f500  movups  [rsp+890h+var_870], xmm0
0x18004f505  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18004f50a  movups  [rsp+890h+var_850], xmm0
0x18004f50f  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18004f514  mov     rcx, [rbx+0F0h]
0x18004f51b  lea     r9, [rsp+890h+var_870]
0x18004f520  mov     r8, rax
0x18004f523  call    TestUnlockData
0x18004f528  mov     eax, dword ptr [rsp+890h+pv+4]
0x18004f52c  or      [rbx+40h], eax
0x18004f52f  cmp     [rsp+890h+pv+8], 0
0x18004f535  jz      short loc_18004F546
0x18004f537  lea     rdx, [rsp+890h+var_870]
0x18004f53c  mov     rcx, rbx
0x18004f53f  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18004f544  jmp     short loc_18004F550
0x18004f546  mov     eax, dword ptr [rsp+890h+pv]
0x18004f54a  mov     [rbx+0B8h], eax
0x18004f550  lea     rcx, [rsp+890h+var_840]
0x18004f555  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004f55a  mov     rcx, [rsp+890h+pv+8]; pv
0x18004f55f  call    cs:__imp_CoTaskMemFree
0x18004f565  dec     dword ptr [rbx+0E8h]
0x18004f56b  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18004f572  call    cs:__imp_LeaveCriticalSection
0x18004f578  mov     rcx, [rbp+790h+var_10]
0x18004f57f  xor     rcx, rsp; StackCookie
0x18004f582  call    __security_check_cookie
0x18004f587  mov     rbx, [rsp+890h+arg_8]
0x18004f58f  add     rsp, 890h
0x18004f596  pop     rbp
0x18004f597  retn
```
