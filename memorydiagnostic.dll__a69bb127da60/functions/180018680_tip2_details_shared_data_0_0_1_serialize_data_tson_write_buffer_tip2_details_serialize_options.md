# tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x180018680`
- end: `0x18001883e`
- name: `?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `446`
- prototype: `__int64 __fastcall(_QWORD *, struct tson::write_buffer *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180015f9c`
- `0x180018c48`

## callees

- `0x180002e50`
- `0x180003f2c`
- `0x1800041cc`
- `0x180006954`
- `0x18000741c`
- `0x180016818`
- `0x180018680`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<0,0,1>::serialize_data(
        _QWORD *a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rdi
  _QWORD *v7; // rax
  _QWORD *v8; // rdx
  __int64 v9; // rcx
  const char *v11; // [rsp+20h] [rbp-E0h] BYREF
  char v12; // [rsp+28h] [rbp-D8h]
  _QWORD *v13; // [rsp+30h] [rbp-D0h]
  const char *v14; // [rsp+38h] [rbp-C8h] BYREF
  char v15; // [rsp+40h] [rbp-C0h]
  _QWORD *v16; // [rsp+48h] [rbp-B8h]
  __int64 v17; // [rsp+50h] [rbp-B0h]
  __int16 v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+5Ah] [rbp-A6h]
  __int16 v20; // [rsp+5Eh] [rbp-A2h]
  const char *v21; // [rsp+60h] [rbp-A0h] BYREF
  char v22; // [rsp+68h] [rbp-98h]
  _QWORD *v23; // [rsp+70h] [rbp-90h]
  _BYTE v24[160]; // [rsp+80h] [rbp-80h] BYREF

  if ( !a3 )
    return 0;
  v6 = (char *)a1 + 33;
  tson::output_archive::output_archive((tson::output_archive *)v24, a2, *((_BYTE *)a1 + 33));
  if ( (a3 & 4) != 0 && *v6 )
  {
    v11 = "version";
    v12 = 7;
    v13 = v6;
    tson::output_archive::operator()<tson::nvp<unsigned char &>>(v24, &v11);
  }
  if ( (a3 & 1) != 0 )
  {
    if ( (*((_DWORD *)a1 + 5) & 0x40000) == 0 )
    {
LABEL_15:
      v11 = "flags";
      v12 = 5;
      v13 = a1 + 15;
      v21 = "errors";
      v22 = 6;
      v23 = a1 + 9;
      v14 = "log";
      v15 = 3;
      v16 = a1 + 12;
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        (tson *)v24,
        (__int64)&v14,
        (__int64 *)&v21);
      goto LABEL_16;
    }
    v7 = (_QWORD *)a1[1];
    if ( v7 )
    {
      v8 = (_QWORD *)a1[1];
    }
    else
    {
      v7 = (_QWORD *)a1[3];
      v8 = v7;
      if ( !v7 )
      {
        v9 = 0;
LABEL_14:
        *(_DWORD *)((char *)&v13 + 1) = 0;
        *(_WORD *)((char *)&v13 + 5) = 0;
        HIBYTE(v13) = 0;
        v14 = "name";
        v15 = 4;
        v16 = v8;
        v17 = v9;
        v18 = 0;
        v19 = 0;
        v20 = 0;
        tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>((tson::output_archive *)v24);
        goto LABEL_15;
      }
    }
    v9 = -1;
    do
      ++v9;
    while ( *((_BYTE *)v7 + v9) );
    goto LABEL_14;
  }
LABEL_16:
  (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD))(*(_QWORD *)*a1 + 8LL))(*a1, v24, a3);
  if ( (int)tson::output_archive::finish((tson::output_archive *)v24) >= 0 )
    return *((_QWORD *)a2 + 258);
  *((_DWORD *)a1 + 16) |= 0x100000u;
  return 0;
}

```

## disassembly

```asm
0x180018680  push    rbp
0x180018682  push    rbx
0x180018683  push    rsi
0x180018684  push    rdi
0x180018685  push    r14
0x180018687  lea     rbp, [rsp-30h]
0x18001868c  sub     rsp, 130h
0x180018693  mov     rax, cs:__security_cookie
0x18001869a  xor     rax, rsp
0x18001869d  mov     [rbp+50h+var_30], rax
0x1800186a1  mov     esi, r8d
0x1800186a4  mov     r14, rdx
0x1800186a7  mov     rbx, rcx
0x1800186aa  test    r8d, r8d
0x1800186ad  jz      loc_180018822
0x1800186b3  lea     rdi, [rcx+21h]
0x1800186b7  mov     r8b, [rdi]; unsigned __int8
0x1800186ba  lea     rcx, [rbp+50h+var_D0]; this
0x1800186be  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x1800186c3  test    sil, 4
0x1800186c7  jz      short loc_1800186F2
0x1800186c9  cmp     byte ptr [rdi], 0
0x1800186cc  jbe     short loc_1800186F2
0x1800186ce  lea     rax, aVersion; "version"
0x1800186d5  mov     [rsp+150h+var_130], rax
0x1800186da  mov     [rsp+150h+var_128], 7
0x1800186df  mov     [rsp+150h+var_120], rdi
0x1800186e4  lea     rdx, [rsp+150h+var_130]
0x1800186e9  lea     rcx, [rbp+50h+var_D0]
0x1800186ed  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x1800186f2  test    sil, 1
0x1800186f6  jz      loc_1800187F0
0x1800186fc  test    dword ptr [rbx+14h], 40000h
0x180018703  jz      loc_180018789
0x180018709  mov     rax, [rbx+8]
0x18001870d  test    rax, rax
0x180018710  jz      short loc_180018717
0x180018712  mov     rdx, rax
0x180018715  jmp     short loc_180018723
0x180018717  mov     rax, [rbx+18h]
0x18001871b  mov     rdx, rax
0x18001871e  test    rax, rax
0x180018721  jz      short loc_180018732
0x180018723  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180018727  inc     rcx
0x18001872a  cmp     byte ptr [rax+rcx], 0
0x18001872e  jnz     short loc_180018727
0x180018730  jmp     short loc_180018734
0x180018732  xor     ecx, ecx
0x180018734  xor     r8d, r8d
0x180018737  mov     dword ptr [rsp+150h+var_120+1], r8d
0x18001873c  mov     word ptr [rsp+150h+var_120+5], r8w
0x180018742  mov     byte ptr [rsp+150h+var_120+7], r8b
0x180018747  lea     r8, aName; "name"
0x18001874e  mov     [rsp+150h+var_118], r8
0x180018753  mov     [rsp+150h+var_110], 4
0x180018758  mov     [rsp+150h+var_108], rdx
0x18001875d  mov     [rsp+150h+var_100], rcx
0x180018762  mov     [rsp+150h+var_F8], 0
0x180018769  mov     eax, dword ptr [rsp+150h+var_120+2]
0x18001876d  mov     [rsp+150h+var_F6], eax
0x180018771  movzx   eax, word ptr [rsp+150h+var_120+6]
0x180018776  mov     [rsp+150h+var_F2], ax
0x18001877b  lea     rdx, [rsp+150h+var_118]
0x180018780  lea     rcx, [rbp+50h+var_D0]; this
0x180018784  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x180018789  lea     rax, aFlags; "flags"
0x180018790  mov     [rsp+150h+var_130], rax
0x180018795  mov     [rsp+150h+var_128], 5
0x18001879a  lea     rax, [rbx+78h]
0x18001879e  mov     [rsp+150h+var_120], rax
0x1800187a3  lea     rax, aErrors; "errors"
0x1800187aa  mov     [rsp+150h+var_F0], rax
0x1800187af  mov     [rsp+150h+var_E8], 6
0x1800187b4  lea     rax, [rbx+48h]
0x1800187b8  mov     [rsp+150h+var_E0], rax
0x1800187bd  lea     rax, aLog; "log"
0x1800187c4  mov     [rsp+150h+var_118], rax
0x1800187c9  mov     [rsp+150h+var_110], 3
0x1800187ce  lea     rax, [rbx+60h]
0x1800187d2  mov     [rsp+150h+var_108], rax
0x1800187d7  lea     r9, [rsp+150h+var_130]
0x1800187dc  lea     r8, [rsp+150h+var_F0]
0x1800187e1  lea     rdx, [rsp+150h+var_118]
0x1800187e6  lea     rcx, [rbp+50h+var_D0]; this
0x1800187ea  call    ??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x1800187ef  nop
0x1800187f0  mov     rcx, [rbx]
0x1800187f3  mov     rdx, [rcx]
0x1800187f6  mov     rax, [rdx+8]
0x1800187fa  mov     r8d, esi
0x1800187fd  lea     rdx, [rbp+50h+var_D0]
0x180018801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018806  nop
0x180018807  lea     rcx, [rbp+50h+var_D0]; this
0x18001880b  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x180018810  test    eax, eax
0x180018812  js      short loc_18001881D
0x180018814  mov     rax, [r14+810h]
0x18001881b  jmp     short loc_180018824
0x18001881d  bts     dword ptr [rbx+40h], 14h
0x180018822  xor     eax, eax
0x180018824  mov     rcx, [rbp+50h+var_30]
0x180018828  xor     rcx, rsp; StackCookie
0x18001882b  call    __security_check_cookie
0x180018830  add     rsp, 130h
0x180018837  pop     r14
0x180018839  pop     rdi
0x18001883a  pop     rsi
0x18001883b  pop     rbx
0x18001883c  pop     rbp
0x18001883d  retn
```
