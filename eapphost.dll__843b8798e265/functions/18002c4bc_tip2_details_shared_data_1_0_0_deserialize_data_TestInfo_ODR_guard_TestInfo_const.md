# tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)

- ea: `0x18002c4bc`
- end: `0x18002c648`
- name: `?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z`
- size: `396`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18002bfb4`
- `0x18002c26c`
- `0x18002c650`
- `0x18002d79c`

## callees

- `0x180002af0`
- `0x180021304`
- `0x180021388`
- `0x180021f4c`
- `0x1800233a8`
- `0x1800234f4`
- `0x18002c32c`
- `0x18002c448`
- `0x18002c4bc`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<1,0,0>::deserialize_data(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rsi
  bool v5; // zf
  __int64 v6; // rdx
  _BYTE *v7; // rcx
  __int64 result; // rax
  char v9; // [rsp+20h] [rbp-E0h] BYREF
  const char *v10; // [rsp+28h] [rbp-D8h] BYREF
  char v11; // [rsp+30h] [rbp-D0h]
  char *v12; // [rsp+38h] [rbp-C8h]
  const char *v13; // [rsp+40h] [rbp-C0h]
  char v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  const char *v16; // [rsp+58h] [rbp-A8h]
  char v17; // [rsp+60h] [rbp-A0h]
  __int64 v18; // [rsp+68h] [rbp-98h]
  _BYTE v19[32]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v20; // [rsp+90h] [rbp-70h] BYREF
  int v21; // [rsp+98h] [rbp-68h]
  char v22; // [rsp+B0h] [rbp-50h]

  if ( (*(_DWORD *)(a2 + 20) & 0x1000) == 0 )
    goto LABEL_15;
  tson::read_buffer::read_buffer((tson::read_buffer *)v19, *(const char **)(a2 + 24));
  v4 = (_QWORD *)(a1 + 8);
  tson::input_archive::input_archive((tson::input_archive *)&v20, (struct tson::read_buffer *)v19, *(_BYTE *)(a1 + 33));
  if ( (*(_DWORD *)(a1 + 20) & 0x40000) != 0 )
  {
    v5 = *(_QWORD *)(a1 + 24) == 0;
    v10 = "name";
    v11 = 4;
    if ( v5 )
    {
      v12 = (char *)(a1 + 8);
      tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(
        &v20,
        &v10);
      if ( *v4 )
        *(_QWORD *)(a1 + 24) = *v4;
    }
    else
    {
      v9 = 0;
      v12 = &v9;
      tson::input_archive::operator()<tson::nvp<tson::ansistring_skip_tag &>>((tson::input_archive *)&v20);
    }
  }
  v11 = 5;
  v10 = "flags";
  v14 = 6;
  v12 = (char *)(a1 + 120);
  v17 = 3;
  v13 = "errors";
  v15 = a1 + 72;
  v16 = "log";
  v18 = a1 + 96;
  tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson *)&v20);
  v7 = *(_BYTE **)(v20 + 8);
  if ( (unsigned __int64)v7 >= *(_QWORD *)(v20 + 16) )
    goto LABEL_10;
  LOBYTE(v6) = 8;
  if ( *v7 == 8 )
    result = tson::input_archive::consume_expected_marker(&v20, v6, 2147944029LL);
  else
LABEL_10:
    result = tip2::details::shared_data<1,0,0>::deserialize(a1, &v20);
  if ( v21 < 0 || (result = v20, *(_BYTE *)(v20 + 24)) || v22 )
  {
LABEL_15:
    *(_DWORD *)(a1 + 64) |= 0x80000u;
  }
  else
  {
    result = *(unsigned int *)(a2 + 16);
    *(_DWORD *)(a1 + 184) = result;
  }
  return result;
}

```

## disassembly

```asm
0x18002c4bc  mov     [rsp-8+arg_10], rbx
0x18002c4c1  push    rbp
0x18002c4c2  push    rsi
0x18002c4c3  push    rdi
0x18002c4c4  lea     rbp, [rsp-30h]
0x18002c4c9  sub     rsp, 130h
0x18002c4d0  mov     rax, cs:__security_cookie
0x18002c4d7  xor     rax, rsp
0x18002c4da  mov     [rbp+40h+var_20], rax
0x18002c4de  test    dword ptr [rdx+14h], 1000h
0x18002c4e5  mov     rdi, rdx
0x18002c4e8  mov     rbx, rcx
0x18002c4eb  jz      loc_18002C623
0x18002c4f1  mov     rdx, [rdx+18h]; char *
0x18002c4f5  lea     rcx, [rsp+140h+var_D0]; this
0x18002c4fa  call    ??0read_buffer@tson@@QEAA@PEBD@Z; tson::read_buffer::read_buffer(char const *)
0x18002c4ff  lea     rsi, [rbx+8]
0x18002c503  mov     r8b, [rsi+19h]; unsigned __int8
0x18002c507  lea     rdx, [rsp+140h+var_D0]; struct tson::read_buffer *
0x18002c50c  lea     rcx, [rbp+40h+var_B0]; this
0x18002c510  call    ??0input_archive@tson@@QEAA@AEAVread_buffer@1@E@Z; tson::input_archive::input_archive(tson::read_buffer &,uchar)
0x18002c515  test    dword ptr [rbx+14h], 40000h
0x18002c51c  jz      short loc_18002C56B
0x18002c51e  cmp     qword ptr [rbx+18h], 0
0x18002c523  lea     rax, aName_0; "name"
0x18002c52a  mov     [rsp+140h+var_118], rax
0x18002c52f  lea     rdx, [rsp+140h+var_118]
0x18002c534  mov     [rsp+140h+var_110], 4
0x18002c539  lea     rcx, [rbp+40h+var_B0]; this
0x18002c53d  jnz     short loc_18002C557
0x18002c53f  mov     [rsp+140h+var_108], rsi
0x18002c544  call    ??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z; tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &> &&)
0x18002c549  mov     rax, [rsi]
0x18002c54c  test    rax, rax
0x18002c54f  jz      short loc_18002C56B
0x18002c551  mov     [rbx+18h], rax
0x18002c555  jmp     short loc_18002C56B
0x18002c557  lea     rax, [rsp+140h+var_120]
0x18002c55c  mov     [rsp+140h+var_120], 0
0x18002c561  mov     [rsp+140h+var_108], rax
0x18002c566  call    ??$?RV?$nvp@AEAUansistring_skip_tag@tson@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAUansistring_skip_tag@tson@@@1@@Z; tson::input_archive::operator()<tson::nvp<tson::ansistring_skip_tag &>>(tson::nvp<tson::ansistring_skip_tag &> &&)
0x18002c56b  lea     rax, aFlags; "flags"
0x18002c572  mov     [rsp+140h+var_110], 5
0x18002c577  mov     [rsp+140h+var_118], rax
0x18002c57c  lea     r9, [rsp+140h+var_118]
0x18002c581  lea     rax, [rbx+78h]
0x18002c585  mov     [rsp+140h+var_F8], 6
0x18002c58a  mov     [rsp+140h+var_108], rax
0x18002c58f  lea     r8, [rsp+140h+var_100]
0x18002c594  lea     rax, aErrors; "errors"
0x18002c59b  mov     [rsp+140h+var_E0], 3
0x18002c5a0  mov     [rsp+140h+var_100], rax
0x18002c5a5  lea     rdx, [rsp+140h+var_E8]
0x18002c5aa  lea     rax, [rbx+48h]
0x18002c5ae  mov     [rsp+140h+var_F0], rax
0x18002c5b3  lea     rcx, [rbp+40h+var_B0]; this
0x18002c5b7  lea     rax, aLog; "log"
0x18002c5be  mov     [rsp+140h+var_E8], rax
0x18002c5c3  lea     rax, [rbx+60h]
0x18002c5c7  mov     [rsp+140h+var_D8], rax
0x18002c5cc  call    ??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x18002c5d1  mov     rax, [rbp+40h+var_B0]
0x18002c5d5  mov     rcx, [rax+8]
0x18002c5d9  cmp     rcx, [rax+10h]
0x18002c5dd  jnb     short loc_18002C5F6
0x18002c5df  mov     dl, 8
0x18002c5e1  cmp     [rcx], dl
0x18002c5e3  jnz     short loc_18002C5F6
0x18002c5e5  mov     r8d, 8007065Dh
0x18002c5eb  lea     rcx, [rbp+40h+var_B0]
0x18002c5ef  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x18002c5f4  jmp     short loc_18002C602
0x18002c5f6  lea     rdx, [rbp+40h+var_B0]
0x18002c5fa  mov     rcx, rbx
0x18002c5fd  call    ?deserialize@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEAVinput_archive@tson@@@Z; tip2::details::shared_data<1,0,0>::deserialize(tson::input_archive &)
0x18002c602  cmp     [rbp+40h+var_A8], 0
0x18002c606  jl      short loc_18002C623
0x18002c608  mov     rax, [rbp+40h+var_B0]
0x18002c60c  cmp     byte ptr [rax+18h], 0
0x18002c610  jnz     short loc_18002C623
0x18002c612  cmp     [rbp+40h+var_90], 0
0x18002c616  jnz     short loc_18002C623
0x18002c618  mov     eax, [rdi+10h]
0x18002c61b  mov     [rbx+0B8h], eax
0x18002c621  jmp     short loc_18002C628
0x18002c623  bts     dword ptr [rbx+40h], 13h
0x18002c628  mov     rcx, [rbp+40h+var_20]
0x18002c62c  xor     rcx, rsp; StackCookie
0x18002c62f  call    __security_check_cookie
0x18002c634  mov     rbx, [rsp+140h+arg_10]
0x18002c63c  add     rsp, 130h
0x18002c643  pop     rdi
0x18002c644  pop     rsi
0x18002c645  pop     rbp
0x18002c646  retn
```
