# tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)

- ea: `0x180018844`
- end: `0x180018a3f`
- name: `?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z`
- size: `507`
- prototype: `__int64 __fastcall(__int64 *, struct tson::write_buffer *, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18001625c`
- `0x180017480`
- `0x180018a48`

## callees

- `0x180002e50`
- `0x180003f2c`
- `0x1800041cc`
- `0x180006954`
- `0x18000741c`
- `0x180016818`
- `0x180018844`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall tip2::details::shared_data<0,0,0>::serialize_data(
        __int64 *a1,
        struct tson::write_buffer *a2,
        unsigned int a3)
{
  _BYTE *v6; // rdi
  __int64 *v7; // rax
  __int64 *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  const char *v12; // [rsp+30h] [rbp-D0h] BYREF
  char v13; // [rsp+38h] [rbp-C8h]
  _BYTE *v14; // [rsp+40h] [rbp-C0h]
  const char *v15; // [rsp+48h] [rbp-B8h] BYREF
  char v16; // [rsp+50h] [rbp-B0h]
  __int64 *v17; // [rsp+58h] [rbp-A8h]
  __int64 v18; // [rsp+60h] [rbp-A0h]
  __int16 v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+6Ah] [rbp-96h]
  __int16 v21; // [rsp+6Eh] [rbp-92h]
  const char *v22; // [rsp+70h] [rbp-90h] BYREF
  char v23; // [rsp+78h] [rbp-88h]
  __int64 *v24; // [rsp+80h] [rbp-80h]
  _BYTE v25[160]; // [rsp+90h] [rbp-70h] BYREF

  if ( !a3 )
    return 0;
  v6 = (char *)a1 + 33;
  tson::output_archive::output_archive((tson::output_archive *)v25, a2, *((_BYTE *)a1 + 33));
  if ( (a3 & 4) != 0 && *v6 )
  {
    v12 = "version";
    v13 = 7;
    v14 = v6;
    tson::output_archive::operator()<tson::nvp<unsigned char &>>(v25, &v12);
  }
  if ( (a3 & 1) != 0 )
  {
    if ( (*((_DWORD *)a1 + 5) & 0x40000) == 0 )
    {
LABEL_15:
      v12 = "flags";
      v13 = 5;
      v14 = a1 + 15;
      v22 = "errors";
      v23 = 6;
      v24 = a1 + 9;
      v15 = "log";
      v16 = 3;
      v17 = a1 + 12;
      tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(
        (tson *)v25,
        (__int64)&v15,
        (__int64 *)&v22);
      goto LABEL_16;
    }
    v7 = (__int64 *)a1[1];
    if ( v7 )
    {
      v8 = (__int64 *)a1[1];
    }
    else
    {
      v7 = (__int64 *)a1[3];
      v8 = v7;
      if ( !v7 )
      {
        v9 = 0;
LABEL_14:
        *(_DWORD *)((char *)&v14 + 1) = 0;
        *(_WORD *)((char *)&v14 + 5) = 0;
        HIBYTE(v14) = 0;
        v15 = "name";
        v16 = 4;
        v17 = v8;
        v18 = v9;
        v19 = 0;
        v20 = 0;
        v21 = 0;
        tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>((tson::output_archive *)v25);
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
  v10 = *a1;
  if ( tip2::details::g_test_interface_exception_guard )
  {
    if ( !(unsigned __int8)tip2::details::g_test_interface_exception_guard(v10, v25, a3, 0, 0) )
    {
      *((_BYTE *)a1 + 160) = 3;
      *((_WORD *)a1 + 81) = 16396;
      a1[21] = 0;
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v10 + 8LL))(v10, v25, a3);
  }
  if ( (int)tson::output_archive::finish((tson::output_archive *)v25) >= 0 )
    return *((_QWORD *)a2 + 258);
  *((_DWORD *)a1 + 16) |= 0x100000u;
  return 0;
}

```

## disassembly

```asm
0x180018844  push    rbp
0x180018846  push    rbx
0x180018847  push    rsi
0x180018848  push    rdi
0x180018849  push    r14
0x18001884b  lea     rbp, [rsp-40h]
0x180018850  sub     rsp, 140h
0x180018857  mov     rax, cs:__security_cookie
0x18001885e  xor     rax, rsp
0x180018861  mov     [rbp+60h+var_30], rax
0x180018865  mov     esi, r8d
0x180018868  mov     r14, rdx
0x18001886b  mov     rbx, rcx
0x18001886e  test    r8d, r8d
0x180018871  jz      loc_180018A23
0x180018877  lea     rdi, [rcx+21h]
0x18001887b  mov     r8b, [rdi]; unsigned __int8
0x18001887e  lea     rcx, [rbp+60h+var_D0]; this
0x180018882  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x180018887  test    sil, 4
0x18001888b  jz      short loc_1800188B6
0x18001888d  cmp     byte ptr [rdi], 0
0x180018890  jbe     short loc_1800188B6
0x180018892  lea     rax, aVersion; "version"
0x180018899  mov     [rsp+160h+var_130], rax
0x18001889e  mov     [rsp+160h+var_128], 7
0x1800188a3  mov     [rsp+160h+var_120], rdi
0x1800188a8  lea     rdx, [rsp+160h+var_130]
0x1800188ad  lea     rcx, [rbp+60h+var_D0]
0x1800188b1  call    ??$?RV?$nvp@AEAE@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAE@1@@Z; tson::output_archive::operator()<tson::nvp<uchar &>>(tson::nvp<uchar &> &&)
0x1800188b6  test    sil, 1
0x1800188ba  jz      loc_1800189B3
0x1800188c0  test    dword ptr [rbx+14h], 40000h
0x1800188c7  jz      loc_18001894D
0x1800188cd  mov     rax, [rbx+8]
0x1800188d1  test    rax, rax
0x1800188d4  jz      short loc_1800188DB
0x1800188d6  mov     rdx, rax
0x1800188d9  jmp     short loc_1800188E7
0x1800188db  mov     rax, [rbx+18h]
0x1800188df  mov     rdx, rax
0x1800188e2  test    rax, rax
0x1800188e5  jz      short loc_1800188F6
0x1800188e7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800188eb  inc     rcx
0x1800188ee  cmp     byte ptr [rax+rcx], 0
0x1800188f2  jnz     short loc_1800188EB
0x1800188f4  jmp     short loc_1800188F8
0x1800188f6  xor     ecx, ecx
0x1800188f8  xor     r8d, r8d
0x1800188fb  mov     dword ptr [rsp+160h+var_120+1], r8d
0x180018900  mov     word ptr [rsp+160h+var_120+5], r8w
0x180018906  mov     byte ptr [rsp+160h+var_120+7], r8b
0x18001890b  lea     r8, aName; "name"
0x180018912  mov     [rsp+160h+var_118], r8
0x180018917  mov     [rsp+160h+var_110], 4
0x18001891c  mov     [rsp+160h+var_108], rdx
0x180018921  mov     [rsp+160h+var_100], rcx
0x180018926  mov     [rsp+160h+var_F8], 0
0x18001892d  mov     eax, dword ptr [rsp+160h+var_120+2]
0x180018931  mov     [rsp+160h+var_F6], eax
0x180018935  movzx   eax, word ptr [rsp+160h+var_120+6]
0x18001893a  mov     [rsp+160h+var_F2], ax
0x18001893f  lea     rdx, [rsp+160h+var_118]
0x180018944  lea     rcx, [rbp+60h+var_D0]; this
0x180018948  call    ??$?RV?$nvp@Uansistring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@Uansistring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::ansistring_tag>>(tson::nvp<tson::ansistring_tag> &&)
0x18001894d  lea     rax, aFlags; "flags"
0x180018954  mov     [rsp+160h+var_130], rax
0x180018959  mov     [rsp+160h+var_128], 5
0x18001895e  lea     rax, [rbx+78h]
0x180018962  mov     [rsp+160h+var_120], rax
0x180018967  lea     rax, aErrors; "errors"
0x18001896e  mov     [rsp+160h+var_F0], rax
0x180018973  mov     [rsp+160h+var_E8], 6
0x180018978  lea     rax, [rbx+48h]
0x18001897c  mov     [rbp+60h+var_E0], rax
0x180018980  lea     rax, aLog; "log"
0x180018987  mov     [rsp+160h+var_118], rax
0x18001898c  mov     [rsp+160h+var_110], 3
0x180018991  lea     rax, [rbx+60h]
0x180018995  mov     [rsp+160h+var_108], rax
0x18001899a  lea     r9, [rsp+160h+var_130]
0x18001899f  lea     r8, [rsp+160h+var_F0]
0x1800189a4  lea     rdx, [rsp+160h+var_118]
0x1800189a9  lea     rcx, [rbp+60h+var_D0]; this
0x1800189ad  call    ??$process@V?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@tson@@V?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@2@V?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@2@@output_archive@tson@@AEAAX$$QEAV?$nvp@AEAV?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@@1@$$QEAV?$nvp@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@1@@Z; tson::output_archive::process<tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &>,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &>,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &>>(tson::nvp<tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>> &> &&,tson::nvp<tip2::vector_nothrow<wil::StoredFailureInfo> &> &&,tson::nvp<tip2::vector_nothrow<tip2::test_flag> &> &&)
0x1800189b2  nop
0x1800189b3  mov     rcx, [rbx]
0x1800189b6  mov     rax, cs:?g_test_interface_exception_guard@details@tip2@@3P6A_NAEAUtest_data_interface@12@PEAVoutput_archive@tson@@W4serialize_options@12@PEAVinput_archive@5@PEBUTipReportingInfo@@@_EEA
0x1800189bd  mov     r8d, esi
0x1800189c0  lea     rdx, [rbp+60h+var_D0]
0x1800189c4  test    rax, rax
0x1800189c7  jz      short loc_1800189FB
0x1800189c9  mov     [rsp+160h+var_140], 0
0x1800189d2  xor     r9d, r9d
0x1800189d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189da  test    al, al
0x1800189dc  jnz     short loc_180018A08
0x1800189de  mov     byte ptr [rbx+0A0h], 3
0x1800189e5  mov     word ptr [rbx+0A2h], 400Ch
0x1800189ee  mov     qword ptr [rbx+0A8h], 0
0x1800189f9  jmp     short loc_180018A08
0x1800189fb  mov     rax, [rcx]
0x1800189fe  mov     rax, [rax+8]
0x180018a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a07  nop
0x180018a08  lea     rcx, [rbp+60h+var_D0]; this
0x180018a0c  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x180018a11  test    eax, eax
0x180018a13  js      short loc_180018A1E
0x180018a15  mov     rax, [r14+810h]
0x180018a1c  jmp     short loc_180018A25
0x180018a1e  bts     dword ptr [rbx+40h], 14h
0x180018a23  xor     eax, eax
0x180018a25  mov     rcx, [rbp+60h+var_30]
0x180018a29  xor     rcx, rsp; StackCookie
0x180018a2c  call    __security_check_cookie
0x180018a31  add     rsp, 140h
0x180018a38  pop     r14
0x180018a3a  pop     rdi
0x180018a3b  pop     rsi
0x180018a3c  pop     rbx
0x180018a3d  pop     rbp
0x180018a3e  retn
```
