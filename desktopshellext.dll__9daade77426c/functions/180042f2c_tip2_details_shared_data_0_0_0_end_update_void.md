# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180042f2c`
- end: `0x18004305a`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d1b4`
- `0x180040af0`
- `0x180040b28`
- `0x18004abbc`
- `0x18004abf4`
- `0x18004ac2c`
- `0x18004ac64`
- `0x180058a1c`

## callees

- `0x18000c444`
- `0x180028168`
- `0x18002a3d0`
- `0x180033d3c`
- `0x180042f2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043034`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043021`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043021`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
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
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
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
    if ( !pv[1] )
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
0x180042f2c  mov     [rsp-8+arg_8], rbx
0x180042f31  push    rbp
0x180042f32  lea     rbp, [rsp-790h]
0x180042f3a  sub     rsp, 890h
0x180042f41  mov     rax, cs:__security_cookie
0x180042f48  xor     rax, rsp
0x180042f4b  mov     [rbp+790h+var_10], rax
0x180042f52  bts     dword ptr [rcx+40h], 0Bh
0x180042f57  mov     rbx, rcx
0x180042f5a  cmp     qword ptr [rcx+0F0h], 0
0x180042f62  jz      loc_180043027
0x180042f68  test    dword ptr [rcx+40h], 100h
0x180042f6f  jnz     loc_180043027
0x180042f75  test    dword ptr [rcx+14h], 8000h
0x180042f7c  jnz     loc_180043027
0x180042f82  xorps   xmm0, xmm0
0x180042f85  mov     [rsp+890h+var_840], 0
0x180042f8e  lea     rax, [rsp+890h+var_837]
0x180042f93  mov     [rsp+890h+var_838], 0
0x180042f98  mov     [rbp+790h+var_30], rax
0x180042f9f  lea     rdx, [rsp+890h+var_840]
0x180042fa4  lea     rax, [rbp+790h+var_37]
0x180042fab  mov     [rsp+890h+var_837], 80408040h
0x180042fb3  mov     [rbp+790h+var_20], rax
0x180042fba  mov     r8d, 1
0x180042fc0  lea     rax, [rsp+890h+var_832]
0x180042fc5  mov     [rsp+890h+var_833], 0
0x180042fca  mov     [rbp+790h+var_28], rax
0x180042fd1  movups  [rsp+890h+var_870], xmm0
0x180042fd6  movups  xmmword ptr [rsp+890h+pv], xmm0
0x180042fdb  movups  [rsp+890h+var_850], xmm0
0x180042fe0  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180042fe5  mov     rcx, [rbx+0F0h]
0x180042fec  lea     r9, [rsp+890h+var_870]
0x180042ff1  mov     r8, rax
0x180042ff4  call    TestUnlockData
0x180042ff9  mov     eax, dword ptr [rsp+890h+pv+4]
0x180042ffd  or      [rbx+40h], eax
0x180043000  cmp     [rsp+890h+pv+8], 0
0x180043006  jnz     short loc_180043012
0x180043008  mov     eax, dword ptr [rsp+890h+pv]
0x18004300c  mov     [rbx+0B8h], eax
0x180043012  lea     rcx, [rsp+890h+var_840]
0x180043017  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004301c  mov     rcx, [rsp+890h+pv+8]; pv
0x180043021  call    cs:__imp_CoTaskMemFree
0x180043027  dec     dword ptr [rbx+0E8h]
0x18004302d  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180043034  call    cs:__imp_LeaveCriticalSection
0x18004303a  mov     rcx, [rbp+790h+var_10]
0x180043041  xor     rcx, rsp; StackCookie
0x180043044  call    __security_check_cookie
0x180043049  mov     rbx, [rsp+890h+arg_8]
0x180043051  add     rsp, 890h
0x180043058  pop     rbp
0x180043059  retn
```
