# tip2::details::shared_data<0,0,1>::end_update(void)

- ea: `0x180024908`
- end: `0x180024a36`
- name: `?end_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180025334`

## callees

- `0x180003220`
- `0x180024098`
- `0x180024908`
- `0x180026008`
- `0x1800270d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024a10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024a10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800249fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800249fd`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,1>::end_update(__int64 a1)
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
    v2 = tip2::details::shared_data<0,0,1>::serialize_data(a1, &v7, 1);
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
0x180024908  mov     [rsp-8+arg_8], rbx
0x18002490d  push    rbp
0x18002490e  lea     rbp, [rsp-790h]
0x180024916  sub     rsp, 890h
0x18002491d  mov     rax, cs:__security_cookie
0x180024924  xor     rax, rsp
0x180024927  mov     [rbp+790h+var_10], rax
0x18002492e  bts     dword ptr [rcx+40h], 0Bh
0x180024933  mov     rbx, rcx
0x180024936  cmp     qword ptr [rcx+0F0h], 0
0x18002493e  jz      loc_180024A03
0x180024944  test    dword ptr [rcx+40h], 100h
0x18002494b  jnz     loc_180024A03
0x180024951  test    dword ptr [rcx+14h], 8000h
0x180024958  jnz     loc_180024A03
0x18002495e  xorps   xmm0, xmm0
0x180024961  mov     [rsp+890h+var_840], 0
0x18002496a  lea     rax, [rsp+890h+var_837]
0x18002496f  mov     [rsp+890h+var_838], 0
0x180024974  mov     [rbp+790h+var_30], rax
0x18002497b  lea     rdx, [rsp+890h+var_840]
0x180024980  lea     rax, [rbp+790h+var_37]
0x180024987  mov     [rsp+890h+var_837], 80408040h
0x18002498f  mov     [rbp+790h+var_20], rax
0x180024996  mov     r8d, 1
0x18002499c  lea     rax, [rsp+890h+var_832]
0x1800249a1  mov     [rsp+890h+var_833], 0
0x1800249a6  mov     [rbp+790h+var_28], rax
0x1800249ad  movups  [rsp+890h+var_870], xmm0
0x1800249b2  movups  xmmword ptr [rsp+890h+pv], xmm0
0x1800249b7  movups  [rsp+890h+var_850], xmm0
0x1800249bc  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800249c1  mov     rcx, [rbx+0F0h]
0x1800249c8  lea     r9, [rsp+890h+var_870]
0x1800249cd  mov     r8, rax
0x1800249d0  call    TestUnlockData
0x1800249d5  mov     eax, dword ptr [rsp+890h+pv+4]
0x1800249d9  or      [rbx+40h], eax
0x1800249dc  cmp     [rsp+890h+pv+8], 0
0x1800249e2  jnz     short loc_1800249EE
0x1800249e4  mov     eax, dword ptr [rsp+890h+pv]
0x1800249e8  mov     [rbx+0B8h], eax
0x1800249ee  lea     rcx, [rsp+890h+var_840]
0x1800249f3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800249f8  mov     rcx, [rsp+890h+pv+8]; pv
0x1800249fd  call    cs:__imp_CoTaskMemFree
0x180024a03  dec     dword ptr [rbx+0E8h]
0x180024a09  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180024a10  call    cs:__imp_LeaveCriticalSection
0x180024a16  mov     rcx, [rbp+790h+var_10]
0x180024a1d  xor     rcx, rsp; StackCookie
0x180024a20  call    __security_check_cookie
0x180024a25  mov     rbx, [rsp+890h+arg_8]
0x180024a2d  add     rsp, 890h
0x180024a34  pop     rbp
0x180024a35  retn
```
