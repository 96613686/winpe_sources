# tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x180019660`
- end: `0x18001981a`
- name: `?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `442`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180016b34`
- `0x180019a18`

## callees

- `0x1800026b0`
- `0x180003990`
- `0x1800067e4`
- `0x180007494`
- `0x180017444`
- `0x1800189d0`
- `0x180019660`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall tip2::details::shared_data<0,0,1>::serialize_data(
        _QWORD *a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  __int128 v10; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD *v11; // [rsp+30h] [rbp-D0h]
  __int128 v12; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v13; // [rsp+50h] [rbp-B0h]
  const char *v14; // [rsp+60h] [rbp-A0h]
  char v15; // [rsp+68h] [rbp-98h]
  _QWORD *v16; // [rsp+70h] [rbp-90h]
  const char *v17; // [rsp+80h] [rbp-80h] BYREF
  char v18; // [rsp+88h] [rbp-78h]

  if ( !a3 )
    return 0;
  v6 = (char *)a1 + 33;
  tson::output_archive::output_archive((tson::output_archive *)&v17, a2, *((_BYTE *)a1 + 33));
  if ( (a3 & 4) != 0 && *v6 )
  {
    *(_QWORD *)&v10 = "version";
    BYTE8(v10) = 7;
    v11 = v6;
    tson::output_archive::operator()<tson::nvp<unsigned char &>>(&v17, &v10);
  }
  if ( (a3 & 1) != 0 )
  {
    if ( (*((_DWORD *)a1 + 5) & 0x40000) == 0 )
    {
LABEL_15:
      *(_QWORD *)&v10 = "flags";
      BYTE8(v10) = 5;
      v11 = a1 + 15;
      v14 = "errors";
      v15 = 6;
      v16 = a1 + 9;
      *(_QWORD *)&v12 = "log";
      BYTE8(v12) = 3;
      v13 = a1 + 12;
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>((tson *)&v17);
      goto LABEL_16;
    }
    v7 = a1[1];
    if ( v7 )
    {
      *(_QWORD *)&v10 = a1[1];
    }
    else
    {
      v7 = a1[3];
      *(_QWORD *)&v10 = v7;
      if ( !v7 )
      {
        v10 = 0u;
LABEL_14:
        v11 = 0;
        v17 = "name";
        v18 = 4;
        v12 = v10;
        v13 = 0;
        tson::output_archive::saveValue(&v17, &v12);
        goto LABEL_15;
      }
    }
    v8 = -1;
    do
      ++v8;
    while ( *(_BYTE *)(v7 + v8) );
    *((_QWORD *)&v10 + 1) = v8;
    goto LABEL_14;
  }
LABEL_16:
  (*(void (__fastcall **)(_QWORD, const char **, _QWORD))(*(_QWORD *)*a1 + 8LL))(*a1, &v17, a3);
  if ( (int)tson::output_archive::finish((tson::output_archive *)&v17) >= 0 )
    return *((_QWORD *)a2 + 258);
  *((_DWORD *)a1 + 16) |= 0x100000u;
  return 0;
}

```

## disassembly

```asm
0x180019660  push    rbp
0x180019662  push    rbx
0x180019663  push    rsi
0x180019664  push    rdi
0x180019665  push    r14
0x180019667  lea     rbp, [rsp-30h]
0x18001966c  sub     rsp, 130h
0x180019673  mov     rax, cs:__security_cookie
0x18001967a  xor     rax, rsp
0x18001967d  mov     [rbp+50h+var_30], rax
0x180019681  mov     esi, r8d
0x180019684  mov     r14, rdx
0x180019687  mov     rbx, rcx
0x18001968a  test    r8d, r8d
0x18001968d  jz      loc_1800197FD
0x180019693  lea     rdi, [rcx+21h]
0x180019697  mov     r8b, [rdi]; unsigned __int8
0x18001969a  lea     rcx, [rbp+50h+var_D0]; this
0x18001969e  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x1800196a3  test    sil, 4
0x1800196a7  jz      short loc_1800196D2
0x1800196a9  cmp     byte ptr [rdi], 0
0x1800196ac  jbe     short loc_1800196D2
0x1800196ae  lea     rax, aVersion; "version"
0x1800196b5  mov     qword ptr [rsp+150h+var_130], rax
0x1800196ba  mov     byte ptr [rsp+150h+var_130+8], 7
0x1800196bf  mov     [rsp+150h+var_120], rdi
0x1800196c4  lea     rdx, [rsp+150h+var_130]
0x1800196c9  lea     rcx, [rbp+50h+var_D0]
0x1800196cd  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x1800196d2  test    sil, 1
0x1800196d6  jz      loc_1800197CB
0x1800196dc  test    dword ptr [rbx+14h], 40000h
0x1800196e3  jz      short loc_180019764
0x1800196e5  mov     rax, [rbx+8]
0x1800196e9  test    rax, rax
0x1800196ec  jz      short loc_1800196F5
0x1800196ee  mov     qword ptr [rsp+150h+var_130], rax
0x1800196f3  jmp     short loc_180019703
0x1800196f5  mov     rax, [rbx+18h]
0x1800196f9  mov     qword ptr [rsp+150h+var_130], rax
0x1800196fe  test    rax, rax
0x180019701  jz      short loc_180019717
0x180019703  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180019707  inc     rcx
0x18001970a  cmp     byte ptr [rax+rcx], 0
0x18001970e  jnz     short loc_180019707
0x180019710  mov     qword ptr [rsp+150h+var_130+8], rcx
0x180019715  jmp     short loc_18001971D
0x180019717  and     qword ptr [rsp+150h+var_130+8], 0
0x18001971d  mov     byte ptr [rsp+150h+var_120], 0
0x180019722  xor     eax, eax
0x180019724  mov     dword ptr [rsp+150h+var_120+1], eax
0x180019728  mov     word ptr [rsp+150h+var_120+5], ax
0x18001972d  mov     byte ptr [rsp+150h+var_120+7], al
0x180019731  lea     rax, aName; "name"
0x180019738  mov     [rbp+50h+var_D0], rax
0x18001973c  mov     [rbp+50h+var_C8], 4
0x180019740  movups  xmm0, [rsp+150h+var_130]
0x180019745  movaps  [rsp+150h+var_110], xmm0
0x18001974a  movsd   xmm1, [rsp+150h+var_120]
0x180019750  movsd   [rsp+150h+var_100], xmm1
0x180019756  lea     rdx, [rsp+150h+var_110]
0x18001975b  lea     rcx, [rbp+50h+var_D0]
0x18001975f  call    ?saveValue@output_archive@tson@@QEAAXUansistring_tag@2@@Z; tson::output_archive::saveValue(tson::ansistring_tag)
0x180019764  lea     rax, aFlags; "flags"
0x18001976b  mov     qword ptr [rsp+150h+var_130], rax
0x180019770  mov     byte ptr [rsp+150h+var_130+8], 5
0x180019775  lea     rax, [rbx+78h]
0x180019779  mov     [rsp+150h+var_120], rax
0x18001977e  lea     rax, aErrors; "errors"
0x180019785  mov     [rsp+150h+var_F0], rax
0x18001978a  mov     [rsp+150h+var_E8], 6
0x18001978f  lea     rax, [rbx+48h]
0x180019793  mov     [rsp+150h+var_E0], rax
0x180019798  lea     rax, aLog; "log"
0x18001979f  mov     qword ptr [rsp+150h+var_110], rax
0x1800197a4  mov     byte ptr [rsp+150h+var_110+8], 3
0x1800197a9  lea     rax, [rbx+60h]
0x1800197ad  mov     [rsp+150h+var_100], rax
0x1800197b2  lea     r9, [rsp+150h+var_130]
0x1800197b7  lea     r8, [rsp+150h+var_F0]
0x1800197bc  lea     rdx, [rsp+150h+var_110]
0x1800197c1  lea     rcx, [rbp+50h+var_D0]; this
0x1800197c5  call    ??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x1800197ca  nop
0x1800197cb  mov     rcx, [rbx]
0x1800197ce  mov     rax, [rcx]
0x1800197d1  mov     r8d, esi
0x1800197d4  lea     rdx, [rbp+50h+var_D0]
0x1800197d8  mov     rax, [rax+8]
0x1800197dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197e1  nop
0x1800197e2  lea     rcx, [rbp+50h+var_D0]; this
0x1800197e6  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x1800197eb  test    eax, eax
0x1800197ed  js      short loc_1800197F8
0x1800197ef  mov     rax, [r14+810h]
0x1800197f6  jmp     short loc_1800197FF
0x1800197f8  bts     dword ptr [rbx+40h], 14h
0x1800197fd  xor     eax, eax
0x1800197ff  mov     rcx, [rbp+50h+var_30]
0x180019803  xor     rcx, rsp; StackCookie
0x180019806  call    __security_check_cookie
0x18001980b  add     rsp, 130h
0x180019812  pop     r14
0x180019814  pop     rdi
0x180019815  pop     rsi
0x180019816  pop     rbx
0x180019817  pop     rbp
0x180019818  retn
```
