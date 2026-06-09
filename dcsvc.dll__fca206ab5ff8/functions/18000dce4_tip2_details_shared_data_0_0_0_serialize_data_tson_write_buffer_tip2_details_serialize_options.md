# tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x18000dce4`
- end: `0x18000dfa1`
- name: `?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `701`
- prototype: `__int64 __fastcall(__int64 *, struct tson::write_buffer *, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18000c6b0`
- `0x18000c990`
- `0x18000dfa8`

## callees

- `0x180001cf0`
- `0x18000a12c`
- `0x18000ae80`
- `0x18000b194`
- `0x18000b5c0`
- `0x18000d160`
- `0x18000dce4`
- `0x18000e224`
- `0x18000e438`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<0,0,0>::serialize_data(
        __int64 *a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rdi
  void *v7; // rax
  void *v8; // r15
  unsigned __int64 v9; // rsi
  tson::write_buffer *v10; // rdi
  __int64 v11; // rcx
  wil::details::in1diag3 *v12; // rcx
  tson::write_buffer *v13; // rax
  _DWORD *v14; // r9
  unsigned __int64 v15; // r8
  const char *v17; // [rsp+30h] [rbp-D0h] BYREF
  char v18; // [rsp+38h] [rbp-C8h]
  _BYTE *v19; // [rsp+40h] [rbp-C0h]
  const char *v20; // [rsp+48h] [rbp-B8h] BYREF
  char v21; // [rsp+50h] [rbp-B0h]
  __int64 *v22; // [rsp+58h] [rbp-A8h]
  const char *v23; // [rsp+60h] [rbp-A0h] BYREF
  char v24; // [rsp+68h] [rbp-98h]
  __int64 *v25; // [rsp+70h] [rbp-90h]
  const char *v26; // [rsp+80h] [rbp-80h] BYREF
  char v27; // [rsp+88h] [rbp-78h]
  char v28; // [rsp+98h] [rbp-68h]
  int v29; // [rsp+108h] [rbp+8h]
  tson::write_buffer *v30; // [rsp+110h] [rbp+10h]

  if ( !a3 )
    return 0;
  v6 = (char *)a1 + 33;
  tson::output_archive::output_archive((tson::output_archive *)&v26, a2, *((_BYTE *)a1 + 33));
  if ( (a3 & 4) != 0 && *v6 )
  {
    v17 = "version";
    v18 = 7;
    v19 = v6;
    tson::output_archive::operator()<tson::nvp<unsigned char &>>(&v26, &v17);
  }
  if ( (a3 & 1) != 0 )
  {
    if ( (*((_DWORD *)a1 + 5) & 0x40000) == 0 )
    {
LABEL_19:
      v17 = "flags";
      v18 = 5;
      v19 = a1 + 15;
      v23 = "errors";
      v24 = 6;
      v25 = a1 + 9;
      v20 = "log";
      v21 = 3;
      v22 = a1 + 12;
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        (tson *)&v26,
        (__int64)&v20,
        (__int64 *)&v23,
        (__int64 *)&v17);
      goto LABEL_20;
    }
    v7 = (void *)a1[1];
    if ( v7 )
    {
      v8 = (void *)a1[1];
    }
    else
    {
      v7 = (void *)a1[3];
      v8 = v7;
      if ( !v7 )
      {
        v9 = 0;
        goto LABEL_14;
      }
    }
    v9 = -1;
    do
      ++v9;
    while ( *((_BYTE *)v7 + v9) );
LABEL_14:
    *(_DWORD *)((char *)&v22 + 1) = 0;
    *(_WORD *)((char *)&v22 + 5) = 0;
    HIBYTE(v22) = 0;
    v26 = "name";
    v27 = 4;
    if ( tson::output_archive::write_name((tson::output_archive *)&v26, v8 == 0) )
    {
      v10 = v30;
      if ( *((_QWORD *)v30 + 259) < *((_QWORD *)v30 + 260) || tson::write_buffer::reserve(v30, 1u) )
        *(_BYTE *)(*((_QWORD *)v10 + 259))++ = 23;
      tson::output_archive::write_string_bytes((tson::output_archive *)&v26, v9, v8, v9);
    }
    goto LABEL_19;
  }
LABEL_20:
  v11 = *a1;
  if ( tip2::details::g_test_interface_exception_guard )
  {
    if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v11, &v26, a3, 0, 0) )
    {
      *((_BYTE *)a1 + 160) = 3;
      *((_WORD *)a1 + 81) = 16396;
      a1[21] = 0;
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64, const char **, _QWORD))(*(_QWORD *)v11 + 8LL))(v11, &v26, a3);
  }
  if ( v29 < 0 || v28 )
    goto LABEL_30;
  v13 = v30;
  if ( *((_BYTE *)v30 + 8) )
  {
    *((_QWORD *)v30 + 258) = 0;
    *((_QWORD *)v13 + 259) = 0;
    *((_QWORD *)v13 + 260) = 0;
LABEL_30:
    *((_DWORD *)a1 + 16) |= 0x100000u;
    return 0;
  }
  v14 = (_DWORD *)*((_QWORD *)v30 + 258);
  v15 = (unsigned int)*((_QWORD *)v30 + 259) - (unsigned int)v14;
  if ( v15 > 0xFFFFFF )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v12);
  *v14 = v15 & 0x3F | (4 * (_WORD)v15) & 0x3F00 | ((_DWORD)v15 << 6) & 0x3F000000 | (16 * v15) & 0x3F0000 | 0x80408040;
  return *((_QWORD *)a2 + 258);
}

```

## disassembly

```asm
0x18000dce4  push    rbp
0x18000dce6  push    rbx
0x18000dce7  push    rsi
0x18000dce8  push    rdi
0x18000dce9  push    r13
0x18000dceb  push    r14
0x18000dced  push    r15
0x18000dcef  lea     rbp, [rsp-30h]
0x18000dcf4  sub     rsp, 130h
0x18000dcfb  mov     rax, cs:__security_cookie
0x18000dd02  xor     rax, rsp
0x18000dd05  mov     [rbp+60h+var_40], rax
0x18000dd09  mov     r14d, r8d
0x18000dd0c  mov     r13, rdx
0x18000dd0f  mov     rbx, rcx
0x18000dd12  test    r8d, r8d
0x18000dd15  jz      loc_18000DF7B
0x18000dd1b  lea     rdi, [rcx+21h]
0x18000dd1f  mov     r8b, [rdi]; unsigned __int8
0x18000dd22  lea     rcx, [rbp+60h+var_E0]; this
0x18000dd26  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x18000dd2b  test    r14b, 4
0x18000dd2f  jz      short loc_18000DD5A
0x18000dd31  cmp     byte ptr [rdi], 0
0x18000dd34  jbe     short loc_18000DD5A
0x18000dd36  lea     rax, aVersion; "version"
0x18000dd3d  mov     [rsp+160h+var_130], rax
0x18000dd42  mov     [rsp+160h+var_128], 7
0x18000dd47  mov     [rsp+160h+var_120], rdi
0x18000dd4c  lea     rdx, [rsp+160h+var_130]
0x18000dd51  lea     rcx, [rbp+60h+var_E0]
0x18000dd55  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x18000dd5a  test    r14b, 1
0x18000dd5e  jz      loc_18000DE7C
0x18000dd64  test    dword ptr [rbx+14h], 40000h
0x18000dd6b  jz      loc_18000DE15
0x18000dd71  mov     rax, [rbx+8]
0x18000dd75  test    rax, rax
0x18000dd78  jz      short loc_18000DD7F
0x18000dd7a  mov     r15, rax
0x18000dd7d  jmp     short loc_18000DD8B
0x18000dd7f  mov     rax, [rbx+18h]
0x18000dd83  mov     r15, rax
0x18000dd86  test    rax, rax
0x18000dd89  jz      short loc_18000DD9A
0x18000dd8b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000dd8f  inc     rsi
0x18000dd92  cmp     byte ptr [rax+rsi], 0
0x18000dd96  jnz     short loc_18000DD8F
0x18000dd98  jmp     short loc_18000DD9C
0x18000dd9a  xor     esi, esi
0x18000dd9c  xor     eax, eax
0x18000dd9e  mov     [rsp+160h+var_107], eax
0x18000dda2  mov     [rsp+160h+var_103], ax
0x18000dda7  mov     [rsp+160h+var_101], al
0x18000ddab  lea     rax, aName; "name"
0x18000ddb2  mov     [rbp+60h+var_E0], rax
0x18000ddb6  mov     [rbp+60h+var_D8], 4
0x18000ddba  test    r15, r15
0x18000ddbd  setz    dl; bool
0x18000ddc0  lea     rcx, [rbp+60h+var_E0]; this
0x18000ddc4  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000ddc9  test    al, al
0x18000ddcb  jz      short loc_18000DE15
0x18000ddcd  mov     rdi, [rbp+60h+var_50]
0x18000ddd1  mov     rax, [rdi+820h]
0x18000ddd8  cmp     [rdi+818h], rax
0x18000dddf  jb      short loc_18000DDF2
0x18000dde1  mov     edx, 1; unsigned __int64
0x18000dde6  mov     rcx, rdi; this
0x18000dde9  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000ddee  test    al, al
0x18000ddf0  jz      short loc_18000DE03
0x18000ddf2  mov     rax, [rdi+818h]
0x18000ddf9  mov     byte ptr [rax], 17h
0x18000ddfc  inc     qword ptr [rdi+818h]
0x18000de03  mov     r9, rsi; unsigned __int64
0x18000de06  mov     r8, r15; void *
0x18000de09  mov     rdx, rsi; unsigned __int64
0x18000de0c  lea     rcx, [rbp+60h+var_E0]; this
0x18000de10  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x18000de15  lea     rax, aFlags; "flags"
0x18000de1c  mov     [rsp+160h+var_130], rax
0x18000de21  mov     [rsp+160h+var_128], 5
0x18000de26  lea     rax, [rbx+78h]
0x18000de2a  mov     [rsp+160h+var_120], rax
0x18000de2f  lea     rax, aErrors; "errors"
0x18000de36  mov     [rsp+160h+var_100], rax
0x18000de3b  mov     [rsp+160h+var_F8], 6
0x18000de40  lea     rax, [rbx+48h]
0x18000de44  mov     [rsp+160h+var_F0], rax
0x18000de49  lea     rax, aLog; "log"
0x18000de50  mov     [rsp+160h+var_118], rax
0x18000de55  mov     [rsp+160h+var_110], 3
0x18000de5a  lea     rax, [rbx+60h]
0x18000de5e  mov     [rsp+58h], rax
0x18000de63  lea     r9, [rsp+160h+var_130]
0x18000de68  lea     r8, [rsp+160h+var_100]
0x18000de6d  lea     rdx, [rsp+160h+var_118]
0x18000de72  lea     rcx, [rbp+60h+var_E0]; this
0x18000de76  call    ??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x18000de7b  nop
0x18000de7c  mov     rcx, [rbx]
0x18000de7f  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x18000de86  mov     r8d, r14d
0x18000de89  lea     rdx, [rbp+60h+var_E0]
0x18000de8d  test    rax, rax
0x18000de90  jz      short loc_18000DEC4
0x18000de92  mov     [rsp+160h+var_140], 0
0x18000de9b  xor     r9d, r9d
0x18000de9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dea3  test    al, al
0x18000dea5  jnz     short loc_18000DED1
0x18000dea7  mov     byte ptr [rbx+0A0h], 3
0x18000deae  mov     word ptr [rbx+0A2h], 400Ch
0x18000deb7  mov     qword ptr [rbx+0A8h], 0
0x18000dec2  jmp     short loc_18000DED1
0x18000dec4  mov     rax, [rcx]
0x18000dec7  mov     rax, [rax+8]
0x18000decb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ded0  nop
0x18000ded1  cmp     [rbp+60h+var_58], 0
0x18000ded5  jl      loc_18000DF76
0x18000dedb  cmp     [rbp+60h+var_C8], 0
0x18000dedf  jnz     loc_18000DF76
0x18000dee5  mov     rax, [rbp+60h+var_50]
0x18000dee9  cmp     byte ptr [rax+8], 0
0x18000deed  jnz     short loc_18000DF55
0x18000deef  mov     r9, [rax+810h]
0x18000def6  mov     r8, [rax+818h]
0x18000defd  sub     r8, r9
0x18000df00  mov     r8d, r8d
0x18000df03  cmp     r8, 0FFFFFFh
0x18000df0a  ja      loc_18000DF9B
0x18000df10  mov     edx, r8d
0x18000df13  shl     rdx, 4
0x18000df17  and     edx, 3F0000h
0x18000df1d  mov     ecx, r8d
0x18000df20  shl     rcx, 6
0x18000df24  and     ecx, 3F000000h
0x18000df2a  or      edx, ecx
0x18000df2c  lea     rcx, ds:0[r8*4]
0x18000df34  and     ecx, 3F00h
0x18000df3a  or      edx, ecx
0x18000df3c  and     r8d, 3Fh
0x18000df40  or      edx, r8d
0x18000df43  or      edx, 80408040h
0x18000df49  mov     [r9], edx
0x18000df4c  mov     rax, [r13+810h]
0x18000df53  jmp     short loc_18000DF7D
0x18000df55  mov     qword ptr [rax+810h], 0
0x18000df60  mov     qword ptr [rax+818h], 0
0x18000df6b  mov     qword ptr [rax+820h], 0
0x18000df76  bts     dword ptr [rbx+40h], 14h
0x18000df7b  xor     eax, eax
0x18000df7d  mov     rcx, [rbp+60h+var_40]
0x18000df81  xor     rcx, rsp; StackCookie
0x18000df84  call    __security_check_cookie
0x18000df89  add     rsp, 130h
0x18000df90  pop     r15
0x18000df92  pop     r14
0x18000df94  pop     r13
0x18000df96  pop     rdi
0x18000df97  pop     rsi
0x18000df98  pop     rbx
0x18000df99  pop     rbp
0x18000df9a  retn
0x18000df9b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
