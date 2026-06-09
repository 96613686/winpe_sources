# tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x180021920`
- end: `0x1800219d0`
- name: `??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180021f4c`

## callees

- `0x180020e40`
- `0x180021920`
- `0x18002259c`
- `0x1800238d8`
- `0x18002c128`
- `0x18002ddfc`

## pseudocode

```c
void __fastcall tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 *a2)
{
  char *v4; // rbx
  unsigned __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rdx
  char *v8; // rax
  __int64 v9; // rcx
  char *v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = 0;
  tson::input_archive::operator()<tson::size_tag &>(this, &v10);
  tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(a2);
  v4 = v10;
  while ( v4 )
  {
    v10 = 0;
    --v4;
    tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
      this,
      (__int64)&v10);
    v5 = a2[1];
    if ( a2[2] < v5 )
      goto LABEL_6;
    v6 = 2 * v5;
    if ( !v5 )
      v6 = 10;
    if ( (unsigned __int8)tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::reserve(
                            a2,
                            v6) )
    {
LABEL_6:
      v7 = a2[2];
      v8 = v10;
      v9 = *a2;
      v10 = 0;
      *(_QWORD *)(v9 + 8 * v7) = v8;
      ++a2[2];
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v10);
  }
}

```

## disassembly

```asm
0x180021920  mov     rax, rsp
0x180021923  mov     [rax+8], rbx
0x180021927  mov     [rax+10h], rsi
0x18002192b  push    rdi
0x18002192c  sub     rsp, 20h
0x180021930  mov     rdi, rdx
0x180021933  mov     qword ptr [rax+18h], 0
0x18002193b  lea     rdx, [rax+18h]
0x18002193f  mov     rsi, rcx
0x180021942  call    ??$?RAEAUsize_tag@tson@@@input_archive@tson@@QEAAAEAV01@AEAUsize_tag@1@@Z; tson::input_archive::operator()<tson::size_tag &>(tson::size_tag &)
0x180021947  mov     rcx, rdi
0x18002194a  call    ?clear@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAAXXZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(void)
0x18002194f  mov     rbx, [rsp+28h+arg_10]
0x180021954  jmp     short loc_1800219BA
0x180021956  lea     rdx, [rsp+28h+arg_10]
0x18002195b  mov     [rsp+28h+arg_10], 0
0x180021964  mov     rcx, rsi; this
0x180021967  dec     rbx
0x18002196a  call    ??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x18002196f  mov     rax, [rdi+8]
0x180021973  cmp     [rdi+10h], rax
0x180021977  jb      short loc_180021993
0x180021979  lea     rdx, [rax+rax]
0x18002197d  test    rax, rax
0x180021980  jnz     short loc_180021987
0x180021982  mov     edx, 0Ah
0x180021987  mov     rcx, rdi
0x18002198a  call    ?reserve@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA_N_K@Z; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::reserve(unsigned __int64)
0x18002198f  test    al, al
0x180021991  jz      short loc_1800219B0
0x180021993  mov     rdx, [rdi+10h]
0x180021997  mov     rax, [rsp+28h+arg_10]
0x18002199c  mov     rcx, [rdi]
0x18002199f  mov     [rsp+28h+arg_10], 0
0x1800219a8  mov     [rcx+rdx*8], rax
0x1800219ac  inc     qword ptr [rdi+10h]
0x1800219b0  lea     rcx, [rsp+28h+arg_10]
0x1800219b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800219ba  test    rbx, rbx
0x1800219bd  jnz     short loc_180021956
0x1800219bf  mov     rbx, [rsp+28h+arg_0]
0x1800219c4  mov     rsi, [rsp+28h+arg_8]
0x1800219c9  add     rsp, 20h
0x1800219cd  pop     rdi
0x1800219ce  retn
```
