# Microsoft::IoT::ShellExtension::CCBT::CCBT(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)

- ea: `0x180015858`
- end: `0x180015929`
- name: `??0CCBT@ShellExtension@IoT@Microsoft@@QEAA@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@5@@Z`
- size: `209`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015e98`

## callees

- `0x18000a2ac`
- `0x18000ab5c`
- `0x18000d1cc`
- `0x180015858`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001587c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001587c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBT::CCBT(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 *v6; // rcx
  char v7; // bl
  __int64 v8; // rax
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF
  int v11; // [rsp+48h] [rbp+10h]
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  v10 = a1;
  v11 = 0;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = GetTickCount64();
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    (_QWORD *)(a1 + 16),
    a2);
  *(_QWORD *)(a1 + 32) = 0;
  if ( *a3 )
  {
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v12);
    v6 = &v12;
    v7 = 6;
    v8 = v12;
  }
  else
  {
    v10 = 0;
    v6 = &v10;
    v7 = 1;
    v8 = 0;
  }
  *(_QWORD *)(a1 + 40) = v8;
  *v6 = 0;
  if ( (v7 & 2) != 0 )
  {
    v7 &= ~2u;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
  }
  if ( (v7 & 1) != 0 )
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = -2147483638;
  *(GUID *)(a1 + 60) = GUID_NULL;
  *(_DWORD *)(a1 + 76) = 0;
  *(_BYTE *)(a1 + 80) = 1;
  return a1;
}

```

## disassembly

```asm
0x180015858  mov     [rsp+arg_0], rcx
0x18001585d  push    rbx
0x18001585e  push    rsi
0x18001585f  push    rdi
0x180015860  sub     rsp, 20h
0x180015864  mov     rdi, r8
0x180015867  mov     rbx, rdx
0x18001586a  mov     rsi, rcx
0x18001586d  mov     [rsp+38h+arg_8], 0
0x180015875  mov     qword ptr [rcx], 0
0x18001587c  call    cs:__imp_GetTickCount64
0x180015882  mov     [rsi+8], rax
0x180015886  lea     rcx, [rsi+10h]
0x18001588a  mov     rdx, rbx
0x18001588d  call    ??0?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> const &)
0x180015892  nop
0x180015893  mov     qword ptr [rsi+20h], 0
0x18001589b  mov     rdx, [rdi]
0x18001589e  test    rdx, rdx
0x1800158a1  jnz     short loc_1800158B4
0x1800158a3  mov     [rsp+38h+arg_0], rdx
0x1800158a8  lea     rcx, [rsp+38h+arg_0]
0x1800158ad  lea     ebx, [rdx+1]
0x1800158b0  xor     eax, eax
0x1800158b2  jmp     short loc_1800158CD
0x1800158b4  lea     rcx, [rsp+38h+arg_10]
0x1800158b9  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800158be  lea     rcx, [rsp+38h+arg_10]
0x1800158c3  mov     ebx, 6
0x1800158c8  mov     rax, [rsp+38h+arg_10]
0x1800158cd  mov     [rsi+28h], rax
0x1800158d1  mov     qword ptr [rcx], 0
0x1800158d8  test    bl, 2
0x1800158db  jz      short loc_1800158EB
0x1800158dd  and     ebx, 0FFFFFFFDh
0x1800158e0  lea     rcx, [rsp+38h+arg_10]
0x1800158e5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800158ea  nop
0x1800158eb  test    bl, 1
0x1800158ee  jz      short loc_1800158FA
0x1800158f0  lea     rcx, [rsp+38h+arg_0]
0x1800158f5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800158fa  mov     qword ptr [rsi+30h], 0
0x180015902  mov     dword ptr [rsi+38h], 8000000Ah
0x180015909  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180015910  movdqu  xmmword ptr [rsi+3Ch], xmm0
0x180015915  xor     eax, eax
0x180015917  mov     [rsi+4Ch], eax
0x18001591a  mov     byte ptr [rsi+50h], 1
0x18001591e  mov     rax, rsi
0x180015921  add     rsp, 20h
0x180015925  pop     rdi
0x180015926  pop     rsi
0x180015927  pop     rbx
0x180015928  retn
```
