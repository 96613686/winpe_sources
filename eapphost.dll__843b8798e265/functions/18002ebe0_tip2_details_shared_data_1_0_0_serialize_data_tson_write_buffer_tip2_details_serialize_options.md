# tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x18002ebe0`
- end: `0x18002ed75`
- name: `?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `405`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18002c650`
- `0x18002ca94`
- `0x18002edb4`

## callees

- `0x180002af0`
- `0x18002112c`
- `0x180021424`
- `0x180021ff0`
- `0x1800229e8`
- `0x180023440`
- `0x18002cdf8`
- `0x18002ceb4`
- `0x18002d6b0`
- `0x18002eb7c`
- `0x18002ebe0`
- `0x18002ef70`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<1,0,0>::serialize_data(
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
    tip2::details::shared_data<1,0,0>::serialize(a1, &v18, a3);
    if ( (int)tson::output_archive::finish((tson::output_archive *)&v18) >= 0 )
      return *((_QWORD *)a2 + 258);
    *(_DWORD *)(a1 + 64) |= 0x100000u;
  }
  return 0;
}

```

## disassembly

```asm
0x18002ebe0  push    rbp
0x18002ebe2  push    rbx
0x18002ebe3  push    rsi
0x18002ebe4  push    rdi
0x18002ebe5  push    r14
0x18002ebe7  lea     rbp, [rsp-10h]
0x18002ebec  sub     rsp, 110h
0x18002ebf3  mov     rax, cs:__security_cookie
0x18002ebfa  xor     rax, rsp
0x18002ebfd  mov     [rbp+30h+var_30], rax
0x18002ec01  mov     edi, r8d
0x18002ec04  mov     r14, rdx
0x18002ec07  mov     rbx, rcx
0x18002ec0a  test    r8d, r8d
0x18002ec0d  jz      loc_18002ED58
0x18002ec13  lea     rsi, [rcx+21h]
0x18002ec17  mov     r8b, [rsi]; unsigned __int8
0x18002ec1a  lea     rcx, [rsp+130h+var_D0]; this
0x18002ec1f  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x18002ec24  test    dil, 4
0x18002ec28  jz      short loc_18002EC54
0x18002ec2a  cmp     byte ptr [rsi], 0
0x18002ec2d  jbe     short loc_18002EC54
0x18002ec2f  lea     rax, aVersion; "version"
0x18002ec36  mov     [rsp+130h+var_108], 7
0x18002ec3b  lea     rdx, [rsp+130h+var_110]
0x18002ec40  mov     [rsp+130h+var_110], rax
0x18002ec45  lea     rcx, [rsp+130h+var_D0]
0x18002ec4a  mov     qword ptr [rsp+130h+var_100], rsi
0x18002ec4f  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x18002ec54  test    dil, 1
0x18002ec58  jz      loc_18002ED2C
0x18002ec5e  test    dword ptr [rbx+14h], 40000h
0x18002ec65  jz      short loc_18002ECB1
0x18002ec67  mov     rdx, [rbx+8]
0x18002ec6b  test    rdx, rdx
0x18002ec6e  jnz     short loc_18002EC74
0x18002ec70  mov     rdx, [rbx+18h]
0x18002ec74  lea     rcx, [rsp+130h+var_E8]
0x18002ec79  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x18002ec7e  lea     rcx, aName_0; "name"
0x18002ec85  mov     [rsp+130h+var_108], 4
0x18002ec8a  mov     [rsp+130h+var_110], rcx
0x18002ec8f  lea     rdx, [rsp+130h+var_110]
0x18002ec94  lea     rcx, [rsp+130h+var_D0]
0x18002ec99  movups  xmm0, xmmword ptr [rax]
0x18002ec9c  movsd   xmm1, qword ptr [rax+10h]
0x18002eca1  movups  [rsp+130h+var_100], xmm0
0x18002eca6  movsd   [rsp+130h+var_F0], xmm1
0x18002ecac  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x18002ecb1  lea     rax, aFlags; "flags"
0x18002ecb8  mov     [rsp+130h+var_108], 5
0x18002ecbd  mov     [rsp+130h+var_110], rax
0x18002ecc2  lea     rcx, [rsp+130h+var_D0]; this
0x18002ecc7  lea     rax, [rbx+78h]
0x18002eccb  mov     [rsp+130h+var_E0], 6
0x18002ecd0  mov     qword ptr [rsp+130h+var_100], rax
0x18002ecd5  lea     rax, aErrors; "errors"
0x18002ecdc  mov     [rsp+130h+var_E8], rax
0x18002ece1  lea     rax, [rbx+48h]
0x18002ece5  mov     [rsp+130h+var_D8], rax
0x18002ecea  lea     rax, aLog; "log"
0x18002ecf1  mov     [rsp+130h+var_D0], rax
0x18002ecf6  mov     [rsp+130h+var_C8], 3
0x18002ecfb  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18002ed00  lea     rdx, [rbx+60h]
0x18002ed04  lea     rcx, [rsp+130h+var_D0]; this
0x18002ed09  call    ??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x18002ed0e  lea     rcx, [rsp+130h+var_D0]; this
0x18002ed13  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18002ed18  lea     r8, [rsp+130h+var_110]
0x18002ed1d  lea     rdx, [rsp+130h+var_E8]
0x18002ed22  lea     rcx, [rsp+130h+var_D0]; this
0x18002ed27  call    ??$process@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x18002ed2c  mov     r8d, edi
0x18002ed2f  lea     rdx, [rsp+130h+var_D0]
0x18002ed34  mov     rcx, rbx
0x18002ed37  call    ?serialize@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEAVoutput_archive@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize(tson::output_archive &,tip2::details::serialize_options)
0x18002ed3c  lea     rcx, [rsp+130h+var_D0]; this
0x18002ed41  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x18002ed46  test    eax, eax
0x18002ed48  js      short loc_18002ED53
0x18002ed4a  mov     rax, [r14+810h]
0x18002ed51  jmp     short loc_18002ED5A
0x18002ed53  bts     dword ptr [rbx+40h], 14h
0x18002ed58  xor     eax, eax
0x18002ed5a  mov     rcx, [rbp+30h+var_30]
0x18002ed5e  xor     rcx, rsp; StackCookie
0x18002ed61  call    __security_check_cookie
0x18002ed66  add     rsp, 110h
0x18002ed6d  pop     r14
0x18002ed6f  pop     rdi
0x18002ed70  pop     rsi
0x18002ed71  pop     rbx
0x18002ed72  pop     rbp
0x18002ed73  retn
```
