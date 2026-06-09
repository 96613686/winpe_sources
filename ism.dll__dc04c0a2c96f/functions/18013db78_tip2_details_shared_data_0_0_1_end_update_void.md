# tip2::details::shared_data<0,0,1>::end_update(void)

- ea: `0x18013db78`
- end: `0x18013dca6`
- name: `?end_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXXZ`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18013d6b0`

## callees

- `0x1800f0990`
- `0x1800f7788`
- `0x1800f961c`
- `0x18013db78`
- `0x18013e758`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013dc80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013dc80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013dc6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013dc6d`

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
0x18013db78  mov     [rsp-8+arg_8], rbx
0x18013db7d  push    rbp
0x18013db7e  lea     rbp, [rsp-790h]
0x18013db86  sub     rsp, 890h
0x18013db8d  mov     rax, cs:__security_cookie
0x18013db94  xor     rax, rsp
0x18013db97  mov     [rbp+790h+var_10], rax
0x18013db9e  bts     dword ptr [rcx+40h], 0Bh
0x18013dba3  mov     rbx, rcx
0x18013dba6  cmp     qword ptr [rcx+0F0h], 0
0x18013dbae  jz      loc_18013DC73
0x18013dbb4  test    dword ptr [rcx+40h], 100h
0x18013dbbb  jnz     loc_18013DC73
0x18013dbc1  test    dword ptr [rcx+14h], 8000h
0x18013dbc8  jnz     loc_18013DC73
0x18013dbce  xorps   xmm0, xmm0
0x18013dbd1  mov     [rsp+890h+var_840], 0
0x18013dbda  lea     rax, [rsp+890h+var_837]
0x18013dbdf  mov     [rsp+890h+var_838], 0
0x18013dbe4  mov     [rbp+790h+var_30], rax
0x18013dbeb  lea     rdx, [rsp+890h+var_840]
0x18013dbf0  lea     rax, [rbp+790h+var_37]
0x18013dbf7  mov     [rsp+890h+var_837], 80408040h
0x18013dbff  mov     [rbp+790h+var_20], rax
0x18013dc06  mov     r8d, 1
0x18013dc0c  lea     rax, [rsp+890h+var_832]
0x18013dc11  mov     [rsp+890h+var_833], 0
0x18013dc16  mov     [rbp+790h+var_28], rax
0x18013dc1d  movups  [rsp+890h+var_870], xmm0
0x18013dc22  movups  xmmword ptr [rsp+890h+pv], xmm0
0x18013dc27  movups  [rsp+890h+var_850], xmm0
0x18013dc2c  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18013dc31  mov     rcx, [rbx+0F0h]
0x18013dc38  lea     r9, [rsp+890h+var_870]
0x18013dc3d  mov     r8, rax
0x18013dc40  call    TestUnlockData
0x18013dc45  mov     eax, dword ptr [rsp+890h+pv+4]
0x18013dc49  or      [rbx+40h], eax
0x18013dc4c  cmp     [rsp+890h+pv+8], 0
0x18013dc52  jnz     short loc_18013DC5E
0x18013dc54  mov     eax, dword ptr [rsp+890h+pv]
0x18013dc58  mov     [rbx+0B8h], eax
0x18013dc5e  lea     rcx, [rsp+890h+var_840]
0x18013dc63  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18013dc68  mov     rcx, [rsp+890h+pv+8]; pv
0x18013dc6d  call    cs:__imp_CoTaskMemFree
0x18013dc73  dec     dword ptr [rbx+0E8h]
0x18013dc79  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18013dc80  call    cs:__imp_LeaveCriticalSection
0x18013dc86  mov     rcx, [rbp+790h+var_10]
0x18013dc8d  xor     rcx, rsp; StackCookie
0x18013dc90  call    __security_check_cookie
0x18013dc95  mov     rbx, [rsp+890h+arg_8]
0x18013dc9d  add     rsp, 890h
0x18013dca4  pop     rbp
0x18013dca5  retn
```
