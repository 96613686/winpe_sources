# tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)

- ea: `0x18002b548`
- end: `0x18002b6d3`
- name: `?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z`
- size: `395`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18002b088`
- `0x18002b304`
- `0x18002b6dc`
- `0x18002c7f4`

## callees

- `0x180002a90`
- `0x18002071c`
- `0x1800207a0`
- `0x180021348`
- `0x18002272c`
- `0x180022878`
- `0x18002b3bc`
- `0x18002b4d8`
- `0x18002b548`

## pseudocode

```c
char __fastcall tip2::details::shared_data<1,0,0>::deserialize_data(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rsi
  bool v5; // zf
  _BYTE *v6; // rcx
  int v7; // eax
  char v9; // [rsp+20h] [rbp-E0h] BYREF
  const char *v10; // [rsp+28h] [rbp-D8h] BYREF
  char v11; // [rsp+30h] [rbp-D0h]
  char *v12; // [rsp+38h] [rbp-C8h]
  const char *v13; // [rsp+40h] [rbp-C0h] BYREF
  char v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  const char *v16; // [rsp+58h] [rbp-A8h] BYREF
  char v17; // [rsp+60h] [rbp-A0h]
  __int64 v18; // [rsp+68h] [rbp-98h]
  _BYTE v19[32]; // [rsp+70h] [rbp-90h] BYREF
  tson::read_buffer *v20; // [rsp+90h] [rbp-70h] BYREF
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
        (__int64)&v20,
        (__int64)&v10);
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
  tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
    (tson *)&v20,
    (__int64)&v16,
    (__int64 *)&v13,
    (__int64 *)&v10);
  v6 = (_BYTE *)*((_QWORD *)v20 + 1);
  if ( (unsigned __int64)v6 >= *((_QWORD *)v20 + 2) )
    goto LABEL_10;
  if ( *v6 == 8 )
    LOBYTE(v7) = tson::input_archive::consume_expected_marker(&v20);
  else
LABEL_10:
    LOBYTE(v7) = tip2::details::shared_data<1,0,0>::deserialize((__int64 *)a1, (__int64)&v20);
  if ( v21 < 0 || (LOBYTE(v7) = (_BYTE)v20, *((_BYTE *)v20 + 24)) || v22 )
  {
LABEL_15:
    *(_DWORD *)(a1 + 64) |= 0x80000u;
  }
  else
  {
    v7 = *(_DWORD *)(a2 + 16);
    *(_DWORD *)(a1 + 184) = v7;
  }
  return v7;
}

```

## disassembly

```asm
0x18002b548  mov     [rsp-8+arg_10], rbx
0x18002b54d  push    rbp
0x18002b54e  push    rsi
0x18002b54f  push    rdi
0x18002b550  lea     rbp, [rsp-30h]
0x18002b555  sub     rsp, 130h
0x18002b55c  mov     rax, cs:__security_cookie
0x18002b563  xor     rax, rsp
0x18002b566  mov     [rbp+40h+var_20], rax
0x18002b56a  test    dword ptr [rdx+14h], 1000h
0x18002b571  mov     rdi, rdx
0x18002b574  mov     rbx, rcx
0x18002b577  jz      loc_18002B6AF
0x18002b57d  mov     rdx, [rdx+18h]; char *
0x18002b581  lea     rcx, [rsp+140h+var_D0]; this
0x18002b586  call    ??0read_buffer@tson@@QEAA@PEBD@Z; tson::read_buffer::read_buffer(char const *)
0x18002b58b  lea     rsi, [rbx+8]
0x18002b58f  mov     r8b, [rsi+19h]; unsigned __int8
0x18002b593  lea     rdx, [rsp+140h+var_D0]; struct tson::read_buffer *
0x18002b598  lea     rcx, [rbp+40h+var_B0]; this
0x18002b59c  call    ??0input_archive@tson@@QEAA@AEAVread_buffer@1@E@Z; tson::input_archive::input_archive(tson::read_buffer &,uchar)
0x18002b5a1  test    dword ptr [rbx+14h], 40000h
0x18002b5a8  jz      short loc_18002B5F7
0x18002b5aa  cmp     qword ptr [rbx+18h], 0
0x18002b5af  lea     rax, aName_0; "name"
0x18002b5b6  mov     [rsp+140h+var_118], rax
0x18002b5bb  lea     rdx, [rsp+140h+var_118]
0x18002b5c0  mov     [rsp+140h+var_110], 4
0x18002b5c5  lea     rcx, [rbp+40h+var_B0]; this
0x18002b5c9  jnz     short loc_18002B5E3
0x18002b5cb  mov     [rsp+140h+var_108], rsi
0x18002b5d0  call    ??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z; tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &> &&)
0x18002b5d5  mov     rax, [rsi]
0x18002b5d8  test    rax, rax
0x18002b5db  jz      short loc_18002B5F7
0x18002b5dd  mov     [rbx+18h], rax
0x18002b5e1  jmp     short loc_18002B5F7
0x18002b5e3  lea     rax, [rsp+140h+var_120]
0x18002b5e8  mov     [rsp+140h+var_120], 0
0x18002b5ed  mov     [rsp+140h+var_108], rax
0x18002b5f2  call    ??$?RV?$nvp@AEAUansistring_skip_tag@tson@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAUansistring_skip_tag@tson@@@1@@Z; tson::input_archive::operator()<tson::nvp<tson::ansistring_skip_tag &>>(tson::nvp<tson::ansistring_skip_tag &> &&)
0x18002b5f7  lea     rax, aFlags; "flags"
0x18002b5fe  mov     [rsp+140h+var_110], 5
0x18002b603  mov     [rsp+140h+var_118], rax
0x18002b608  lea     r9, [rsp+140h+var_118]
0x18002b60d  lea     rax, [rbx+78h]
0x18002b611  mov     [rsp+140h+var_F8], 6
0x18002b616  mov     [rsp+140h+var_108], rax
0x18002b61b  lea     r8, [rsp+140h+var_100]
0x18002b620  lea     rax, aErrors; "errors"
0x18002b627  mov     [rsp+140h+var_E0], 3
0x18002b62c  mov     [rsp+140h+var_100], rax
0x18002b631  lea     rdx, [rsp+140h+var_E8]
0x18002b636  lea     rax, [rbx+48h]
0x18002b63a  mov     [rsp+140h+var_F0], rax
0x18002b63f  lea     rcx, [rbp+40h+var_B0]; this
0x18002b643  lea     rax, aLog; "log"
0x18002b64a  mov     [rsp+140h+var_E8], rax
0x18002b64f  lea     rax, [rbx+60h]
0x18002b653  mov     [rsp+140h+var_D8], rax
0x18002b658  call    ??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@input_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::input_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x18002b65d  mov     rax, [rbp+40h+var_B0]
0x18002b661  mov     rcx, [rax+8]
0x18002b665  cmp     rcx, [rax+10h]
0x18002b669  jnb     short loc_18002B682
0x18002b66b  mov     dl, 8
0x18002b66d  cmp     [rcx], dl
0x18002b66f  jnz     short loc_18002B682
0x18002b671  mov     r8d, 8007065Dh
0x18002b677  lea     rcx, [rbp+40h+var_B0]
0x18002b67b  call    ?consume_expected_marker@input_archive@tson@@AEAA_NW4archive_marker@details@2@J@Z; tson::input_archive::consume_expected_marker(tson::details::archive_marker,long)
0x18002b680  jmp     short loc_18002B68E
0x18002b682  lea     rdx, [rbp+40h+var_B0]
0x18002b686  mov     rcx, rbx
0x18002b689  call    ?deserialize@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEAVinput_archive@tson@@@Z; tip2::details::shared_data<1,0,0>::deserialize(tson::input_archive &)
0x18002b68e  cmp     [rbp+40h+var_A8], 0
0x18002b692  jl      short loc_18002B6AF
0x18002b694  mov     rax, [rbp+40h+var_B0]
0x18002b698  cmp     byte ptr [rax+18h], 0
0x18002b69c  jnz     short loc_18002B6AF
0x18002b69e  cmp     [rbp+40h+var_90], 0
0x18002b6a2  jnz     short loc_18002B6AF
0x18002b6a4  mov     eax, [rdi+10h]
0x18002b6a7  mov     [rbx+0B8h], eax
0x18002b6ad  jmp     short loc_18002B6B4
0x18002b6af  bts     dword ptr [rbx+40h], 13h
0x18002b6b4  mov     rcx, [rbp+40h+var_20]
0x18002b6b8  xor     rcx, rsp; StackCookie
0x18002b6bb  call    __security_check_cookie
0x18002b6c0  mov     rbx, [rsp+140h+arg_10]
0x18002b6c8  add     rsp, 130h
0x18002b6cf  pop     rdi
0x18002b6d0  pop     rsi
0x18002b6d1  pop     rbp
0x18002b6d2  retn
```
