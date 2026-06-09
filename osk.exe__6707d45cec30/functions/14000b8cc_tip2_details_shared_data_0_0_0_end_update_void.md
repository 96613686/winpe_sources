# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x14000b8cc`
- end: `0x14000b9fa`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140004fd8`
- `0x140007c20`

## callees

- `0x140005044`
- `0x14000b8cc`
- `0x14000d1bc`
- `0x14000de7c`
- `0x140025d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000b9d4`
- `KERNEL32!LeaveCriticalSection` at `0x14000b9d4`
- `ole32!CoTaskMemFree` at `0x14000b9c1`
- `ole32!CoTaskMemFree` at `0x14000b9c1`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int128 v4; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h]
  __int128 v6; // [rsp+40h] [rbp-C0h]
  __int64 v7; // [rsp+50h] [rbp-B0h] BYREF
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
0x14000b8cc  mov     [rsp-8+arg_8], rbx
0x14000b8d1  push    rbp
0x14000b8d2  lea     rbp, [rsp-790h]
0x14000b8da  sub     rsp, 890h
0x14000b8e1  mov     rax, cs:__security_cookie
0x14000b8e8  xor     rax, rsp
0x14000b8eb  mov     [rbp+790h+var_10], rax
0x14000b8f2  bts     dword ptr [rcx+40h], 0Bh
0x14000b8f7  mov     rbx, rcx
0x14000b8fa  cmp     qword ptr [rcx+0F0h], 0
0x14000b902  jz      loc_14000B9C7
0x14000b908  test    dword ptr [rcx+40h], 100h
0x14000b90f  jnz     loc_14000B9C7
0x14000b915  test    dword ptr [rcx+14h], 8000h
0x14000b91c  jnz     loc_14000B9C7
0x14000b922  xorps   xmm0, xmm0
0x14000b925  mov     [rsp+890h+var_840], 0
0x14000b92e  lea     rax, [rsp+890h+var_837]
0x14000b933  mov     [rsp+890h+var_838], 0
0x14000b938  mov     [rbp+790h+var_30], rax
0x14000b93f  lea     rdx, [rsp+890h+var_840]
0x14000b944  lea     rax, [rbp+790h+var_37]
0x14000b94b  mov     [rsp+890h+var_837], 80408040h
0x14000b953  mov     [rbp+790h+var_20], rax
0x14000b95a  mov     r8d, 1
0x14000b960  lea     rax, [rsp+890h+var_832]
0x14000b965  mov     [rsp+890h+var_833], 0
0x14000b96a  mov     [rbp+790h+var_28], rax
0x14000b971  movups  [rsp+890h+var_870], xmm0
0x14000b976  movups  xmmword ptr [rsp+890h+pv], xmm0
0x14000b97b  movups  [rsp+890h+var_850], xmm0
0x14000b980  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x14000b985  mov     rcx, [rbx+0F0h]
0x14000b98c  lea     r9, [rsp+890h+var_870]
0x14000b991  mov     r8, rax
0x14000b994  call    TestUnlockData
0x14000b999  mov     eax, dword ptr [rsp+890h+pv+4]
0x14000b99d  or      [rbx+40h], eax
0x14000b9a0  cmp     [rsp+890h+pv+8], 0
0x14000b9a6  jnz     short loc_14000B9B2
0x14000b9a8  mov     eax, dword ptr [rsp+890h+pv]
0x14000b9ac  mov     [rbx+0B8h], eax
0x14000b9b2  lea     rcx, [rsp+890h+var_840]
0x14000b9b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000b9bc  mov     rcx, [rsp+890h+pv+8]; pv
0x14000b9c1  call    cs:__imp_CoTaskMemFree
0x14000b9c7  dec     dword ptr [rbx+0E8h]
0x14000b9cd  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x14000b9d4  call    cs:__imp_LeaveCriticalSection
0x14000b9da  mov     rcx, [rbp+790h+var_10]
0x14000b9e1  xor     rcx, rsp; StackCookie
0x14000b9e4  call    __security_check_cookie
0x14000b9e9  mov     rbx, [rsp+890h+arg_8]
0x14000b9f1  add     rsp, 890h
0x14000b9f8  pop     rbp
0x14000b9f9  retn
```
