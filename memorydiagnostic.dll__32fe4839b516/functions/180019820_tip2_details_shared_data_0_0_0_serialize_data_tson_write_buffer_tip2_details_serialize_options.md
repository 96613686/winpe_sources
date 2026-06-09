# tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x180019820`
- end: `0x180019a11`
- name: `?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `497`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180006a0c`
- `0x180016dfc`
- `0x1800180cc`

## callees

- `0x1800026b0`
- `0x180003990`
- `0x1800067e4`
- `0x180007494`
- `0x180017444`
- `0x1800189d0`
- `0x180019820`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::details::shared_data<0,0,0>::serialize_data(
        __int64 *a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int128 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v12; // [rsp+40h] [rbp-C0h]
  __int128 v13; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v14; // [rsp+60h] [rbp-A0h]
  const char *v15; // [rsp+70h] [rbp-90h]
  char v16; // [rsp+78h] [rbp-88h]
  __int64 *v17; // [rsp+80h] [rbp-80h]
  const char *v18; // [rsp+90h] [rbp-70h] BYREF
  char v19; // [rsp+98h] [rbp-68h]

  if ( !a3 )
    return 0;
  v6 = (char *)a1 + 33;
  tson::output_archive::output_archive((tson::output_archive *)&v18, a2, *((_BYTE *)a1 + 33));
  if ( (a3 & 4) != 0 && *v6 )
  {
    *(_QWORD *)&v11 = "version";
    BYTE8(v11) = 7;
    v12 = v6;
    tson::output_archive::operator()<tson::nvp<unsigned char &>>(&v18, &v11);
  }
  if ( (a3 & 1) != 0 )
  {
    if ( (*((_DWORD *)a1 + 5) & 0x40000) == 0 )
    {
LABEL_15:
      *(_QWORD *)&v11 = "flags";
      BYTE8(v11) = 5;
      v12 = a1 + 15;
      v15 = "errors";
      v16 = 6;
      v17 = a1 + 9;
      *(_QWORD *)&v13 = "log";
      BYTE8(v13) = 3;
      v14 = a1 + 12;
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson *)&v18);
      goto LABEL_16;
    }
    v7 = a1[1];
    if ( v7 )
    {
      *(_QWORD *)&v11 = a1[1];
    }
    else
    {
      v7 = a1[3];
      *(_QWORD *)&v11 = v7;
      if ( !v7 )
      {
        v11 = 0u;
LABEL_14:
        v12 = 0;
        v18 = "name";
        v19 = 4;
        v13 = v11;
        v14 = 0;
        tson::output_archive::saveValue(&v18, &v13);
        goto LABEL_15;
      }
    }
    v8 = -1;
    do
      ++v8;
    while ( *(_BYTE *)(v7 + v8) );
    *((_QWORD *)&v11 + 1) = v8;
    goto LABEL_14;
  }
LABEL_16:
  v9 = *a1;
  if ( tip2::details::g_test_interface_exception_guard )
  {
    if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v9, &v18, a3, 0, 0) )
    {
      *((_BYTE *)a1 + 160) = 3;
      *((_WORD *)a1 + 81) = 16396;
      a1[21] = 0;
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64, const char **, _QWORD))(*(_QWORD *)v9 + 8LL))(v9, &v18, a3);
  }
  if ( (int)tson::output_archive::finish((tson::output_archive *)&v18) >= 0 )
    return *((_QWORD *)a2 + 258);
  *((_DWORD *)a1 + 16) |= 0x100000u;
  return 0;
}

```

## disassembly

```asm
0x180019820  push    rbp
0x180019822  push    rbx
0x180019823  push    rsi
0x180019824  push    rdi
0x180019825  push    r14
0x180019827  lea     rbp, [rsp-40h]
0x18001982c  sub     rsp, 140h
0x180019833  mov     rax, cs:__security_cookie
0x18001983a  xor     rax, rsp
0x18001983d  mov     [rbp+60h+var_30], rax
0x180019841  mov     esi, r8d
0x180019844  mov     r14, rdx
0x180019847  mov     rbx, rcx
0x18001984a  test    r8d, r8d
0x18001984d  jz      loc_1800199F4
0x180019853  lea     rdi, [rcx+21h]
0x180019857  mov     r8b, [rdi]; unsigned __int8
0x18001985a  lea     rcx, [rbp+60h+var_D0]; this
0x18001985e  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x180019863  test    sil, 4
0x180019867  jz      short loc_180019892
0x180019869  cmp     byte ptr [rdi], 0
0x18001986c  jbe     short loc_180019892
0x18001986e  lea     rax, aVersion; "version"
0x180019875  mov     qword ptr [rsp+160h+var_130], rax
0x18001987a  mov     byte ptr [rsp+160h+var_130+8], 7
0x18001987f  mov     [rsp+160h+var_120], rdi
0x180019884  lea     rdx, [rsp+160h+var_130]
0x180019889  lea     rcx, [rbp+60h+var_D0]
0x18001988d  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x180019892  test    sil, 1
0x180019896  jz      loc_18001998A
0x18001989c  test    dword ptr [rbx+14h], 40000h
0x1800198a3  jz      short loc_180019924
0x1800198a5  mov     rax, [rbx+8]
0x1800198a9  test    rax, rax
0x1800198ac  jz      short loc_1800198B5
0x1800198ae  mov     qword ptr [rsp+160h+var_130], rax
0x1800198b3  jmp     short loc_1800198C3
0x1800198b5  mov     rax, [rbx+18h]
0x1800198b9  mov     qword ptr [rsp+160h+var_130], rax
0x1800198be  test    rax, rax
0x1800198c1  jz      short loc_1800198D7
0x1800198c3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800198c7  inc     rcx
0x1800198ca  cmp     byte ptr [rax+rcx], 0
0x1800198ce  jnz     short loc_1800198C7
0x1800198d0  mov     qword ptr [rsp+160h+var_130+8], rcx
0x1800198d5  jmp     short loc_1800198DD
0x1800198d7  and     qword ptr [rsp+160h+var_130+8], 0
0x1800198dd  mov     byte ptr [rsp+160h+var_120], 0
0x1800198e2  xor     eax, eax
0x1800198e4  mov     dword ptr [rsp+160h+var_120+1], eax
0x1800198e8  mov     word ptr [rsp+160h+var_120+5], ax
0x1800198ed  mov     byte ptr [rsp+160h+var_120+7], al
0x1800198f1  lea     rax, aName; "name"
0x1800198f8  mov     [rbp+60h+var_D0], rax
0x1800198fc  mov     [rbp+60h+var_C8], 4
0x180019900  movups  xmm0, [rsp+160h+var_130]
0x180019905  movaps  [rsp+160h+var_110], xmm0
0x18001990a  movsd   xmm1, [rsp+160h+var_120]
0x180019910  movsd   [rsp+160h+var_100], xmm1
0x180019916  lea     rdx, [rsp+160h+var_110]
0x18001991b  lea     rcx, [rbp+60h+var_D0]
0x18001991f  call    ?saveValue@output_archive@tson@@QEAAXUansistring_tag@2@@Z; tson::output_archive::saveValue(tson::ansistring_tag)
0x180019924  lea     rax, aFlags; "flags"
0x18001992b  mov     qword ptr [rsp+160h+var_130], rax
0x180019930  mov     byte ptr [rsp+160h+var_130+8], 5
0x180019935  lea     rax, [rbx+78h]
0x180019939  mov     [rsp+160h+var_120], rax
0x18001993e  lea     rax, aErrors; "errors"
0x180019945  mov     [rsp+160h+var_F0], rax
0x18001994a  mov     [rsp+160h+var_E8], 6
0x18001994f  lea     rax, [rbx+48h]
0x180019953  mov     [rbp+60h+var_E0], rax
0x180019957  lea     rax, aLog; "log"
0x18001995e  mov     qword ptr [rsp+160h+var_110], rax
0x180019963  mov     byte ptr [rsp+160h+var_110+8], 3
0x180019968  lea     rax, [rbx+60h]
0x18001996c  mov     [rsp+160h+var_100], rax
0x180019971  lea     r9, [rsp+160h+var_130]
0x180019976  lea     r8, [rsp+160h+var_F0]
0x18001997b  lea     rdx, [rsp+160h+var_110]
0x180019980  lea     rcx, [rbp+60h+var_D0]; this
0x180019984  call    ??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x180019989  nop
0x18001998a  mov     rcx, [rbx]
0x18001998d  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x180019994  mov     r8d, esi
0x180019997  lea     rdx, [rbp+60h+var_D0]
0x18001999b  test    rax, rax
0x18001999e  jz      short loc_1800199CC
0x1800199a0  and     [rsp+160h+var_140], 0
0x1800199a6  xor     r9d, r9d
0x1800199a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199ae  test    al, al
0x1800199b0  jnz     short loc_1800199D9
0x1800199b2  mov     byte ptr [rbx+0A0h], 3
0x1800199b9  mov     word ptr [rbx+0A2h], 400Ch
0x1800199c2  and     qword ptr [rbx+0A8h], 0
0x1800199ca  jmp     short loc_1800199D9
0x1800199cc  mov     rax, [rcx]
0x1800199cf  mov     rax, [rax+8]
0x1800199d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199d8  nop
0x1800199d9  lea     rcx, [rbp+60h+var_D0]; this
0x1800199dd  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x1800199e2  test    eax, eax
0x1800199e4  js      short loc_1800199EF
0x1800199e6  mov     rax, [r14+810h]
0x1800199ed  jmp     short loc_1800199F6
0x1800199ef  bts     dword ptr [rbx+40h], 14h
0x1800199f4  xor     eax, eax
0x1800199f6  mov     rcx, [rbp+60h+var_30]
0x1800199fa  xor     rcx, rsp; StackCookie
0x1800199fd  call    __security_check_cookie
0x180019a02  add     rsp, 140h
0x180019a09  pop     r14
0x180019a0b  pop     rdi
0x180019a0c  pop     rsi
0x180019a0d  pop     rbx
0x180019a0e  pop     rbp
0x180019a0f  retn
```
