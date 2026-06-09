# tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)

- ea: `0x1400043f8`
- end: `0x140004485`
- name: `??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(tson::output_archive *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x14000d1bc`

## callees

- `0x1400034e8`
- `0x1400043f8`
- `0x14000c260`
- `0x14000db3c`
- `0x14000dbec`

## pseudocode

```c
void __fastcall tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::output_archive *this,
        __int64 a2)
{
  _QWORD *v3; // r10
  _QWORD *v4; // rbx
  __int64 v5; // rsi
  __int64 string_tag; // rax
  void *v7; // r14
  unsigned __int64 v8; // rbp
  _BYTE v9[56]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+68h] [rbp+10h] BYREF

  v10 = *(_QWORD *)(a2 + 16);
  tson::output_archive::operator()<tson::size_tag>(this, &v10);
  v4 = (_QWORD *)*v3;
  v5 = *v3 + 8LL * v3[2];
  while ( v4 != (_QWORD *)v5 )
  {
    string_tag = tson::make_string_tag(v9, *v4);
    v7 = *(void **)string_tag;
    v8 = *(_QWORD *)(string_tag + 8);
    if ( tson::output_archive::write_type(this, *(_QWORD *)string_tag == 0, 23) )
      tson::output_archive::write_string_bytes(this, v8, v7, v8);
    ++v4;
  }
}

```

## disassembly

```asm
0x1400043f8  mov     r11, rsp
0x1400043fb  mov     [r11+8], rbx
0x1400043ff  mov     [r11+18h], rbp
0x140004403  push    rsi
0x140004404  push    rdi
0x140004405  push    r14
0x140004407  sub     rsp, 40h
0x14000440b  mov     rax, [rdx+10h]
0x14000440f  mov     r10, rdx
0x140004412  lea     rdx, [r11+10h]
0x140004416  mov     [r11+10h], rax
0x14000441a  mov     rdi, rcx
0x14000441d  call    ??$?RUsize_tag@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAUsize_tag@1@@Z; tson::output_archive::operator()<tson::size_tag>(tson::size_tag &&)
0x140004422  mov     rax, [r10+10h]
0x140004426  mov     rbx, [r10]
0x140004429  lea     rsi, [rbx+rax*8]
0x14000442d  jmp     short loc_14000446D
0x14000442f  mov     rdx, [rbx]
0x140004432  lea     rcx, [rsp+58h+var_38]
0x140004437  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x14000443c  mov     r8b, 17h
0x14000443f  mov     rcx, rdi
0x140004442  mov     r14, [rax]
0x140004445  mov     rbp, [rax+8]
0x140004449  test    r14, r14
0x14000444c  setz    dl
0x14000444f  call    ?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z; tson::output_archive::write_type(bool,tson::details::archive_marker)
0x140004454  test    al, al
0x140004456  jz      short loc_140004469
0x140004458  mov     r9, rbp; unsigned __int64
0x14000445b  mov     r8, r14; void *
0x14000445e  mov     rdx, rbp; unsigned __int64
0x140004461  mov     rcx, rdi; this
0x140004464  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x140004469  add     rbx, 8
0x14000446d  cmp     rbx, rsi
0x140004470  jnz     short loc_14000442F
0x140004472  mov     rbx, [rsp+58h+arg_0]
0x140004477  mov     rbp, [rsp+58h+arg_10]
0x14000447c  add     rsp, 40h
0x140004480  pop     r14
0x140004482  pop     rdi
0x140004483  pop     rsi
0x140004484  retn
```
