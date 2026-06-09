# tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x14000d1bc`
- end: `0x14000d350`
- name: `?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `404`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x14000b8cc`
- `0x14000bd74`
- `0x14000d390`

## callees

- `0x1400035c0`
- `0x1400037dc`
- `0x140004240`
- `0x1400043f8`
- `0x140004ba4`
- `0x14000c0d4`
- `0x14000c140`
- `0x14000c260`
- `0x14000d158`
- `0x14000d1bc`
- `0x14000d540`
- `0x140025d70`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<0,0,0>::serialize_data(
        __int64 a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rsi
  __int64 v7; // rdx
  __int64 string_tag; // rax
  __int64 v9; // xmm1_8
  const char *v11; // [rsp+20h] [rbp-E0h] BYREF
  char v12; // [rsp+28h] [rbp-D8h]
  __int128 v13; // [rsp+30h] [rbp-D0h]
  __int64 v14; // [rsp+40h] [rbp-C0h]
  const char *v15; // [rsp+48h] [rbp-B8h] BYREF
  char v16; // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  const char *v18; // [rsp+60h] [rbp-A0h] BYREF
  char v19; // [rsp+68h] [rbp-98h]

  if ( a3 )
  {
    v6 = (_BYTE *)(a1 + 33);
    tson::output_archive::output_archive((tson::output_archive *)&v18, a2, *(_BYTE *)(a1 + 33));
    if ( (a3 & 4) != 0 && *v6 )
    {
      v12 = 7;
      v11 = "version";
      *(_QWORD *)&v13 = v6;
      tson::output_archive::operator()<tson::nvp<unsigned char &>>(&v18, &v11);
    }
    if ( (a3 & 1) != 0 )
    {
      if ( (*(_DWORD *)(a1 + 20) & 0x40000) != 0 )
      {
        v7 = *(_QWORD *)(a1 + 8);
        if ( !v7 )
          v7 = *(_QWORD *)(a1 + 24);
        string_tag = tson::make_string_tag(&v15, v7);
        v12 = 4;
        v11 = "name";
        v9 = *(_QWORD *)(string_tag + 16);
        v13 = *(_OWORD *)string_tag;
        v14 = v9;
        tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(&v18, &v11);
      }
      v12 = 5;
      v11 = "flags";
      v16 = 6;
      *(_QWORD *)&v13 = a1 + 120;
      v15 = "errors";
      v17 = a1 + 72;
      v18 = "log";
      v19 = 3;
      tson::output_archive::startNode((tson::output_archive *)&v18);
      tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>((tson::output_archive *)&v18);
      tson::output_archive::finishNode((tson::output_archive *)&v18);
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson *)&v18);
    }
    tip2::details::shared_data<0,0,0>::serialize(a1, &v18, a3);
    if ( (int)tson::output_archive::finish((tson::output_archive *)&v18) >= 0 )
      return *((_QWORD *)a2 + 258);
    *(_DWORD *)(a1 + 64) |= 0x100000u;
  }
  return 0;
}

```

## disassembly

```asm
0x14000d1bc  push    rbp
0x14000d1be  push    rbx
0x14000d1bf  push    rsi
0x14000d1c0  push    rdi
0x14000d1c1  push    r14
0x14000d1c3  lea     rbp, [rsp-10h]
0x14000d1c8  sub     rsp, 110h
0x14000d1cf  mov     rax, cs:__security_cookie
0x14000d1d6  xor     rax, rsp
0x14000d1d9  mov     [rbp+30h+var_30], rax
0x14000d1dd  mov     edi, r8d
0x14000d1e0  mov     r14, rdx
0x14000d1e3  mov     rbx, rcx
0x14000d1e6  test    r8d, r8d
0x14000d1e9  jz      loc_14000D334
0x14000d1ef  lea     rsi, [rcx+21h]
0x14000d1f3  mov     r8b, [rsi]; unsigned __int8
0x14000d1f6  lea     rcx, [rsp+130h+var_D0]; this
0x14000d1fb  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x14000d200  test    dil, 4
0x14000d204  jz      short loc_14000D230
0x14000d206  cmp     byte ptr [rsi], 0
0x14000d209  jbe     short loc_14000D230
0x14000d20b  lea     rax, aVersion; "version"
0x14000d212  mov     [rsp+130h+var_108], 7
0x14000d217  lea     rdx, [rsp+130h+var_110]
0x14000d21c  mov     [rsp+130h+var_110], rax
0x14000d221  lea     rcx, [rsp+130h+var_D0]
0x14000d226  mov     qword ptr [rsp+130h+var_100], rsi
0x14000d22b  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x14000d230  test    dil, 1
0x14000d234  jz      loc_14000D308
0x14000d23a  test    dword ptr [rbx+14h], 40000h
0x14000d241  jz      short loc_14000D28D
0x14000d243  mov     rdx, [rbx+8]
0x14000d247  test    rdx, rdx
0x14000d24a  jnz     short loc_14000D250
0x14000d24c  mov     rdx, [rbx+18h]
0x14000d250  lea     rcx, [rsp+130h+var_E8]
0x14000d255  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x14000d25a  lea     rcx, aName; "name"
0x14000d261  mov     [rsp+130h+var_108], 4
0x14000d266  mov     [rsp+130h+var_110], rcx
0x14000d26b  lea     rdx, [rsp+130h+var_110]
0x14000d270  lea     rcx, [rsp+130h+var_D0]
0x14000d275  movups  xmm0, xmmword ptr [rax]
0x14000d278  movsd   xmm1, qword ptr [rax+10h]
0x14000d27d  movups  [rsp+130h+var_100], xmm0
0x14000d282  movsd   [rsp+130h+var_F0], xmm1
0x14000d288  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x14000d28d  lea     rax, aFlags; "flags"
0x14000d294  mov     [rsp+130h+var_108], 5
0x14000d299  mov     [rsp+130h+var_110], rax
0x14000d29e  lea     rcx, [rsp+130h+var_D0]; this
0x14000d2a3  lea     rax, [rbx+78h]
0x14000d2a7  mov     [rsp+130h+var_E0], 6
0x14000d2ac  mov     qword ptr [rsp+130h+var_100], rax
0x14000d2b1  lea     rax, aErrors; "errors"
0x14000d2b8  mov     [rsp+130h+var_E8], rax
0x14000d2bd  lea     rax, [rbx+48h]
0x14000d2c1  mov     [rsp+130h+var_D8], rax
0x14000d2c6  lea     rax, aLog; "log"
0x14000d2cd  mov     [rsp+130h+var_D0], rax
0x14000d2d2  mov     [rsp+130h+var_C8], 3
0x14000d2d7  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x14000d2dc  lea     rdx, [rbx+60h]
0x14000d2e0  lea     rcx, [rsp+130h+var_D0]; this
0x14000d2e5  call    ??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x14000d2ea  lea     rcx, [rsp+130h+var_D0]; this
0x14000d2ef  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x14000d2f4  lea     r8, [rsp+130h+var_110]
0x14000d2f9  lea     rdx, [rsp+130h+var_E8]
0x14000d2fe  lea     rcx, [rsp+130h+var_D0]; this
0x14000d303  call    ??$process@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x14000d308  mov     r8d, edi
0x14000d30b  lea     rdx, [rsp+130h+var_D0]
0x14000d310  mov     rcx, rbx
0x14000d313  call    ?serialize@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXAEAVoutput_archive@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize(tson::output_archive &,tip2::details::serialize_options)
0x14000d318  lea     rcx, [rsp+130h+var_D0]; this
0x14000d31d  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x14000d322  test    eax, eax
0x14000d324  js      short loc_14000D32F
0x14000d326  mov     rax, [r14+810h]
0x14000d32d  jmp     short loc_14000D336
0x14000d32f  bts     dword ptr [rbx+40h], 14h
0x14000d334  xor     eax, eax
0x14000d336  mov     rcx, [rbp+30h+var_30]
0x14000d33a  xor     rcx, rsp; StackCookie
0x14000d33d  call    __security_check_cookie
0x14000d342  add     rsp, 110h
0x14000d349  pop     r14
0x14000d34b  pop     rdi
0x14000d34c  pop     rsi
0x14000d34d  pop     rbx
0x14000d34e  pop     rbp
0x14000d34f  retn
```
