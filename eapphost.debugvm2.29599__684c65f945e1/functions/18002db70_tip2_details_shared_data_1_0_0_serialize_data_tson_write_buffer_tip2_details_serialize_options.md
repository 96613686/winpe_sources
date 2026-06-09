# tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x18002db70`
- end: `0x18002dd04`
- name: `?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `404`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18002b6dc`
- `0x18002bb04`
- `0x18002dd44`

## callees

- `0x180002a90`
- `0x180020548`
- `0x180020838`
- `0x1800213ec`
- `0x180021dc8`
- `0x1800227c4`
- `0x18002be64`
- `0x18002bf20`
- `0x18002c70c`
- `0x18002db0c`
- `0x18002db70`
- `0x18002def4`

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
0x18002db70  push    rbp
0x18002db72  push    rbx
0x18002db73  push    rsi
0x18002db74  push    rdi
0x18002db75  push    r14
0x18002db77  lea     rbp, [rsp-10h]
0x18002db7c  sub     rsp, 110h
0x18002db83  mov     rax, cs:__security_cookie
0x18002db8a  xor     rax, rsp
0x18002db8d  mov     [rbp+30h+var_30], rax
0x18002db91  mov     edi, r8d
0x18002db94  mov     r14, rdx
0x18002db97  mov     rbx, rcx
0x18002db9a  test    r8d, r8d
0x18002db9d  jz      loc_18002DCE8
0x18002dba3  lea     rsi, [rcx+21h]
0x18002dba7  mov     r8b, [rsi]; unsigned __int8
0x18002dbaa  lea     rcx, [rsp+130h+var_D0]; this
0x18002dbaf  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x18002dbb4  test    dil, 4
0x18002dbb8  jz      short loc_18002DBE4
0x18002dbba  cmp     byte ptr [rsi], 0
0x18002dbbd  jbe     short loc_18002DBE4
0x18002dbbf  lea     rax, aVersion; "version"
0x18002dbc6  mov     [rsp+130h+var_108], 7
0x18002dbcb  lea     rdx, [rsp+130h+var_110]
0x18002dbd0  mov     [rsp+130h+var_110], rax
0x18002dbd5  lea     rcx, [rsp+130h+var_D0]
0x18002dbda  mov     qword ptr [rsp+130h+var_100], rsi
0x18002dbdf  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x18002dbe4  test    dil, 1
0x18002dbe8  jz      loc_18002DCBC
0x18002dbee  test    dword ptr [rbx+14h], 40000h
0x18002dbf5  jz      short loc_18002DC41
0x18002dbf7  mov     rdx, [rbx+8]
0x18002dbfb  test    rdx, rdx
0x18002dbfe  jnz     short loc_18002DC04
0x18002dc00  mov     rdx, [rbx+18h]
0x18002dc04  lea     rcx, [rsp+130h+var_E8]
0x18002dc09  call    ?make_string_tag@tson@@YA?AUansistring_tag@1@PEBD@Z; tson::make_string_tag(char const *)
0x18002dc0e  lea     rcx, aName_0; "name"
0x18002dc15  mov     [rsp+130h+var_108], 4
0x18002dc1a  mov     [rsp+130h+var_110], rcx
0x18002dc1f  lea     rdx, [rsp+130h+var_110]
0x18002dc24  lea     rcx, [rsp+130h+var_D0]
0x18002dc29  movups  xmm0, xmmword ptr [rax]
0x18002dc2c  movsd   xmm1, qword ptr [rax+10h]
0x18002dc31  movups  [rsp+130h+var_100], xmm0
0x18002dc36  movsd   [rsp+130h+var_F0], xmm1
0x18002dc3c  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x18002dc41  lea     rax, aFlags; "flags"
0x18002dc48  mov     [rsp+130h+var_108], 5
0x18002dc4d  mov     [rsp+130h+var_110], rax
0x18002dc52  lea     rcx, [rsp+130h+var_D0]; this
0x18002dc57  lea     rax, [rbx+78h]
0x18002dc5b  mov     [rsp+130h+var_E0], 6
0x18002dc60  mov     qword ptr [rsp+130h+var_100], rax
0x18002dc65  lea     rax, aErrors; "errors"
0x18002dc6c  mov     [rsp+130h+var_E8], rax
0x18002dc71  lea     rax, [rbx+48h]
0x18002dc75  mov     [rsp+130h+var_D8], rax
0x18002dc7a  lea     rax, aLog; "log"
0x18002dc81  mov     [rsp+130h+var_D0], rax
0x18002dc86  mov     [rsp+130h+var_C8], 3
0x18002dc8b  call    ?startNode@output_archive@tson@@QEAAXXZ; tson::output_archive::startNode(void)
0x18002dc90  lea     rdx, [rbx+60h]
0x18002dc94  lea     rcx, [rsp+130h+var_D0]; this
0x18002dc99  call    ??$save_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@YAXAEAVoutput_archive@0@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@Z; tson::save_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(tson::output_archive &,tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &)
0x18002dc9e  lea     rcx, [rsp+130h+var_D0]; this
0x18002dca3  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18002dca8  lea     r8, [rsp+130h+var_110]
0x18002dcad  lea     rdx, [rsp+130h+var_E8]
0x18002dcb2  lea     rcx, [rsp+130h+var_D0]; this
0x18002dcb7  call    ??$process@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x18002dcbc  mov     r8d, edi
0x18002dcbf  lea     rdx, [rsp+130h+var_D0]
0x18002dcc4  mov     rcx, rbx
0x18002dcc7  call    ?serialize@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEAVoutput_archive@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize(tson::output_archive &,tip2::details::serialize_options)
0x18002dccc  lea     rcx, [rsp+130h+var_D0]; this
0x18002dcd1  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x18002dcd6  test    eax, eax
0x18002dcd8  js      short loc_18002DCE3
0x18002dcda  mov     rax, [r14+810h]
0x18002dce1  jmp     short loc_18002DCEA
0x18002dce3  bts     dword ptr [rbx+40h], 14h
0x18002dce8  xor     eax, eax
0x18002dcea  mov     rcx, [rbp+30h+var_30]
0x18002dcee  xor     rcx, rsp; StackCookie
0x18002dcf1  call    __security_check_cookie
0x18002dcf6  add     rsp, 110h
0x18002dcfd  pop     r14
0x18002dcff  pop     rdi
0x18002dd00  pop     rsi
0x18002dd01  pop     rbx
0x18002dd02  pop     rbp
0x18002dd03  retn
```
