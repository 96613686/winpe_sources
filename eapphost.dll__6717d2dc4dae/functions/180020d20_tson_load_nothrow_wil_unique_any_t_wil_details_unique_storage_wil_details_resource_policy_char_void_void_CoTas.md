# tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::input_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x180020d20`
- end: `0x180020dcf`
- name: `??$load_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180021348`

## callees

- `0x180020260`
- `0x180020d20`
- `0x180021990`
- `0x180022ca0`
- `0x18002b1d8`
- `0x18002cdd4`

## pseudocode

```c
__int64 __fastcall tson::load_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 *a2)
{
  __int64 result; // rax
  __int64 v5; // rbx
  unsigned __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // [rsp+40h] [rbp+18h] BYREF

  v11 = 0;
  tson::input_archive::operator()<tson::size_tag &>(this, &v11);
  result = tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(a2);
  v5 = v11;
  while ( v5 )
  {
    v11 = 0;
    --v5;
    tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(this);
    v6 = a2[1];
    if ( a2[2] < v6 )
      goto LABEL_6;
    v7 = 2 * v6;
    if ( !v6 )
      v7 = 10;
    if ( (unsigned __int8)tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::reserve(
                            a2,
                            v7) )
    {
LABEL_6:
      v8 = a2[2];
      v9 = v11;
      v10 = *a2;
      v11 = 0;
      *(_QWORD *)(v10 + 8 * v8) = v9;
      ++a2[2];
    }
    result = wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v11);
  }
  return result;
}

```

## disassembly

```asm
0x180020d20  mov     rax, rsp
0x180020d23  mov     [rax+8], rbx
0x180020d27  mov     [rax+10h], rsi
0x180020d2b  push    rdi
0x180020d2c  sub     rsp, 20h
0x180020d30  mov     rdi, rdx
0x180020d33  mov     qword ptr [rax+18h], 0
0x180020d3b  lea     rdx, [rax+18h]
0x180020d3f  mov     rsi, rcx
0x180020d42  call    ??$?RAEAUsize_tag@tson@@@input_archive@tson@@QEAAAEAV01@AEAUsize_tag@1@@Z; tson::input_archive::operator()<tson::size_tag &>(tson::size_tag &)
0x180020d47  mov     rcx, rdi
0x180020d4a  call    ?clear@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAAXXZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(void)
0x180020d4f  mov     rbx, [rsp+28h+arg_10]
0x180020d54  jmp     short loc_180020DBA
0x180020d56  lea     rdx, [rsp+28h+arg_10]
0x180020d5b  mov     [rsp+28h+arg_10], 0
0x180020d64  mov     rcx, rsi; this
0x180020d67  dec     rbx
0x180020d6a  call    ??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)
0x180020d6f  mov     rax, [rdi+8]
0x180020d73  cmp     [rdi+10h], rax
0x180020d77  jb      short loc_180020D93
0x180020d79  lea     rdx, [rax+rax]
0x180020d7d  test    rax, rax
0x180020d80  jnz     short loc_180020D87
0x180020d82  mov     edx, 0Ah
0x180020d87  mov     rcx, rdi
0x180020d8a  call    ?reserve@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA_N_K@Z; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::reserve(unsigned __int64)
0x180020d8f  test    al, al
0x180020d91  jz      short loc_180020DB0
0x180020d93  mov     rdx, [rdi+10h]
0x180020d97  mov     rax, [rsp+28h+arg_10]
0x180020d9c  mov     rcx, [rdi]
0x180020d9f  mov     [rsp+28h+arg_10], 0
0x180020da8  mov     [rcx+rdx*8], rax
0x180020dac  inc     qword ptr [rdi+10h]
0x180020db0  lea     rcx, [rsp+28h+arg_10]
0x180020db5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180020dba  test    rbx, rbx
0x180020dbd  jnz     short loc_180020D56
0x180020dbf  mov     rbx, [rsp+28h+arg_0]
0x180020dc4  mov     rsi, [rsp+28h+arg_8]
0x180020dc9  add     rsp, 20h
0x180020dcd  pop     rdi
0x180020dce  retn
```
