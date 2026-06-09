# cdp::CloudDataEncryptionKeyFactory::ToCloudKey(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1802fded8`
- end: `0x1802fe1d0`
- name: `?ToCloudKey@CloudDataEncryptionKeyFactory@cdp@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1802fd650`

## callees

- `0x18000b724`
- `0x18000cbc0`
- `0x18001ce80`
- `0x18003d0e0`
- `0x1800624cc`
- `0x1800a11bc`
- `0x1800ad100`
- `0x1800e932c`
- `0x18011d8c4`
- `0x1801f6fb0`
- `0x1802fded8`
- `0x1802fe214`
- `0x180354010`

## import_xrefs

- `SHCORE!IStream_Read` at `0x1802fe140`
- `SHCORE!IStream_Read` at `0x1802fe140`
- `SHCORE!IStream_Size` at `0x1802fe0ec`
- `SHCORE!IStream_Size` at `0x1802fe0ec`
- `SHCORE!IStream_WriteStr` at `0x1802fdf72`
- `SHCORE!IStream_WriteStr` at `0x1802fdf72`
- `SHCORE!IStream_Reset` at `0x1802fdfbb`
- `SHCORE!IStream_Reset` at `0x1802fe0a2`
- `SHCORE!IStream_Reset` at `0x1802fdfbb`
- `SHCORE!IStream_Reset` at `0x1802fe0a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void *__fastcall cdp::CloudDataEncryptionKeyFactory::ToCloudKey(__int64 a1, void *a2, __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rax
  HRESULT v11; // edi
  __int64 v12; // rax
  HRESULT v13; // eax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rax
  HRESULT v21; // eax
  __int64 v22; // rax
  HRESULT v23; // eax
  __int64 v24; // rax
  HRESULT v25; // eax
  __int64 v26; // rax
  const char *v28; // [rsp+30h] [rbp-69h] BYREF
  int v29; // [rsp+38h] [rbp-61h]
  IStream *v30; // [rsp+40h] [rbp-59h] BYREF
  IStream *pstm; // [rsp+48h] [rbp-51h] BYREF
  ULARGE_INTEGER pui; // [rsp+50h] [rbp-49h] BYREF
  LPVOID v33[2]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v34[56]; // [rsp+68h] [rbp-31h] BYREF
  void *pv[7]; // [rsp+A0h] [rbp+7h] BYREF

  v33[0] = a2;
  pstm = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pstm);
  v8 = SHCreateMemoryStream(v7, v6, &pstm);
  if ( v8 < 0 )
  {
    v28 = ".\\clouddataencryptionkeyfactory.cpp";
    v29 = 417;
    v9 = cdp::MakeException<cdp::hresult_exception>(pv, &v28, (unsigned int)v8);
    cdp::CdpThrow<cdp::hresult_exception>(&v28, v9);
  }
  v10 = cdp::ToWstring(pv, a3);
  if ( *(_QWORD *)(v10 + 24) > 7u )
    v10 = *(_QWORD *)v10;
  v11 = IStream_WriteStr(pstm, (PCWSTR)v10);
  std::wstring::_Tidy_deallocate(pv);
  if ( v11 < 0 )
  {
    v28 = ".\\clouddataencryptionkeyfactory.cpp";
    v29 = 418;
    v12 = cdp::MakeException<cdp::hresult_exception>(pv, &v28, (unsigned int)v11);
    cdp::CdpThrow<cdp::hresult_exception>(&v28, v12);
  }
  v13 = IStream_Reset(pstm);
  if ( v13 < 0 )
  {
    v28 = ".\\clouddataencryptionkeyfactory.cpp";
    v29 = 420;
    v14 = cdp::MakeException<cdp::hresult_exception>(pv, &v28, (unsigned int)v13);
    cdp::CdpThrow<cdp::hresult_exception>(&v28, v14);
  }
  v30 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  v17 = SHCreateMemoryStream(v16, v15, &v30);
  if ( v17 < 0 )
  {
    v28 = ".\\clouddataencryptionkeyfactory.cpp";
    v29 = 422;
    v18 = cdp::MakeException<cdp::hresult_exception>(pv, &v28, (unsigned int)v17);
    cdp::CdpThrow<cdp::hresult_exception>(&v28, v18);
  }
  cdp::CloudDataEncryptionKeyFactory::GetRoamingSecurity(a1, v33);
  v19 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, IStream *, IStream *))(*(_QWORD *)v33[0] + 32LL))(
          v33[0],
          0,
          pstm,
          v30);
  if ( v19 < 0 )
  {
    v28 = ".\\clouddataencryptionkeyfactory.cpp";
    v29 = 426;
    v20 = cdp::MakeException<cdp::hresult_exception>(pv, &v28, (unsigned int)v19);
    cdp::CdpThrow<cdp::hresult_exception>(&v28, v20);
  }
  v21 = IStream_Reset(v30);
  if ( v21 < 0 )
  {
    v28 = ".\\clouddataencryptionkeyfactory.cpp";
    v29 = 427;
    v22 = cdp::MakeException<cdp::hresult_exception>(pv, &v28, (unsigned int)v21);
    cdp::CdpThrow<cdp::hresult_exception>(&v28, v22);
  }
  pui.QuadPart = 0;
  v23 = IStream_Size(v30, &pui);
  if ( v23 < 0 )
  {
    v28 = ".\\clouddataencryptionkeyfactory.cpp";
    v29 = 431;
    v24 = cdp::MakeException<cdp::hresult_exception>(pv, &v28, (unsigned int)v23);
    cdp::CdpThrow<cdp::hresult_exception>(&v28, v24);
  }
  ((void (__fastcall *)(_QWORD, _QWORD))std::vector<unsigned char>::vector<unsigned char>)(
    pv,
    (ULARGE_INTEGER)pui.QuadPart);
  v25 = IStream_Read(v30, pv[0], pui.LowPart);
  if ( v25 < 0 )
  {
    v28 = ".\\clouddataencryptionkeyfactory.cpp";
    v29 = 433;
    v26 = cdp::MakeException<cdp::hresult_exception>(v34, &v28, (unsigned int)v25);
    cdp::CdpThrow<cdp::hresult_exception>(&v28, v26);
  }
  cdp::EncodeBase64(a2, pv, (unsigned int)v25);
  std::vector<unsigned char>::_Tidy(pv);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v33);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pstm);
  return a2;
}

```

## disassembly

```asm
0x1802fded8  mov     [rsp-8+arg_18], rbx
0x1802fdedd  push    rbp
0x1802fdede  push    rsi
0x1802fdedf  push    rdi
0x1802fdee0  lea     rbp, [rsp-47h]
0x1802fdee5  sub     rsp, 0E0h
0x1802fdeec  mov     rax, cs:__security_cookie
0x1802fdef3  xor     rax, rsp
0x1802fdef6  mov     [rbp+57h+var_18], rax
0x1802fdefa  mov     rdi, r8
0x1802fdefd  mov     rbx, rdx
0x1802fdf00  mov     rsi, rcx
0x1802fdf03  mov     [rbp+57h+var_98], rdx
0x1802fdf07  mov     [rbp+57h+pstm], 0
0x1802fdf0f  lea     rcx, [rbp+57h+pstm]
0x1802fdf13  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fdf18  lea     r8, [rbp+57h+pstm]
0x1802fdf1c  call    SHCreateMemoryStream
0x1802fdf21  mov     r8d, eax
0x1802fdf24  test    eax, eax
0x1802fdf26  jns     short loc_1802FDF55
0x1802fdf28  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fdf2f  mov     [rbp+57h+var_C0], rax
0x1802fdf33  mov     [rbp+57h+var_B8], 1A1h
0x1802fdf3a  lea     rdx, [rbp+57h+var_C0]
0x1802fdf3e  lea     rcx, [rbp+57h+pv]
0x1802fdf42  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fdf47  nop
0x1802fdf48  mov     rdx, rax
0x1802fdf4b  lea     rcx, [rbp+57h+var_C0]
0x1802fdf4f  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fdf55  mov     rdx, rdi
0x1802fdf58  lea     rcx, [rbp+57h+pv]
0x1802fdf5c  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x1802fdf61  cmp     qword ptr [rax+18h], 7
0x1802fdf66  jbe     short loc_1802FDF6B
0x1802fdf68  mov     rax, [rax]
0x1802fdf6b  mov     rdx, rax; psz
0x1802fdf6e  mov     rcx, [rbp+57h+pstm]; pstm
0x1802fdf72  call    cs:__imp_IStream_WriteStr
0x1802fdf78  mov     edi, eax
0x1802fdf7a  lea     rcx, [rbp+57h+pv]
0x1802fdf7e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802fdf83  test    edi, edi
0x1802fdf85  jns     short loc_1802FDFB7
0x1802fdf87  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fdf8e  mov     [rbp+57h+var_C0], rax
0x1802fdf92  mov     [rbp+57h+var_B8], 1A2h
0x1802fdf99  mov     r8d, edi
0x1802fdf9c  lea     rdx, [rbp+57h+var_C0]
0x1802fdfa0  lea     rcx, [rbp+57h+pv]
0x1802fdfa4  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fdfa9  nop
0x1802fdfaa  mov     rdx, rax
0x1802fdfad  lea     rcx, [rbp+57h+var_C0]
0x1802fdfb1  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fdfb7  mov     rcx, [rbp+57h+pstm]; pstm
0x1802fdfbb  call    cs:__imp_IStream_Reset
0x1802fdfc1  mov     r8d, eax
0x1802fdfc4  test    eax, eax
0x1802fdfc6  jns     short loc_1802FDFF5
0x1802fdfc8  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fdfcf  mov     [rbp+57h+var_C0], rax
0x1802fdfd3  mov     [rbp+57h+var_B8], 1A4h
0x1802fdfda  lea     rdx, [rbp+57h+var_C0]
0x1802fdfde  lea     rcx, [rbp+57h+pv]
0x1802fdfe2  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fdfe7  nop
0x1802fdfe8  mov     rdx, rax
0x1802fdfeb  lea     rcx, [rbp+57h+var_C0]
0x1802fdfef  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fdff5  mov     [rbp+57h+var_B0], 0
0x1802fdffd  lea     rcx, [rbp+57h+var_B0]
0x1802fe001  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fe006  lea     r8, [rbp+57h+var_B0]
0x1802fe00a  call    SHCreateMemoryStream
0x1802fe00f  mov     r8d, eax
0x1802fe012  test    eax, eax
0x1802fe014  jns     short loc_1802FE043
0x1802fe016  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fe01d  mov     [rbp+57h+var_C0], rax
0x1802fe021  mov     [rbp+57h+var_B8], 1A6h
0x1802fe028  lea     rdx, [rbp+57h+var_C0]
0x1802fe02c  lea     rcx, [rbp+57h+pv]
0x1802fe030  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fe035  nop
0x1802fe036  mov     rdx, rax
0x1802fe039  lea     rcx, [rbp+57h+var_C0]
0x1802fe03d  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fe043  lea     rdx, [rbp+57h+var_98]
0x1802fe047  mov     rcx, rsi
0x1802fe04a  call    ?GetRoamingSecurity@CloudDataEncryptionKeyFactory@cdp@@AEAA?AV?$ComPtr@UIRoamingSecurity@@@WRL@Microsoft@@XZ; cdp::CloudDataEncryptionKeyFactory::GetRoamingSecurity(void)
0x1802fe04f  nop
0x1802fe050  mov     rcx, [rbp+57h+var_98]
0x1802fe054  mov     rax, [rcx]
0x1802fe057  mov     r9, [rbp+57h+var_B0]
0x1802fe05b  mov     r8, [rbp+57h+pstm]
0x1802fe05f  xor     edx, edx
0x1802fe061  mov     rax, [rax+20h]
0x1802fe065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fe06a  mov     r8d, eax
0x1802fe06d  test    eax, eax
0x1802fe06f  jns     short loc_1802FE09E
0x1802fe071  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fe078  mov     [rbp+57h+var_C0], rax
0x1802fe07c  mov     [rbp+57h+var_B8], 1AAh
0x1802fe083  lea     rdx, [rbp+57h+var_C0]
0x1802fe087  lea     rcx, [rbp+57h+pv]
0x1802fe08b  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fe090  nop
0x1802fe091  mov     rdx, rax
0x1802fe094  lea     rcx, [rbp+57h+var_C0]
0x1802fe098  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fe09e  mov     rcx, [rbp+57h+var_B0]; pstm
0x1802fe0a2  call    cs:__imp_IStream_Reset
0x1802fe0a8  mov     r8d, eax
0x1802fe0ab  test    eax, eax
0x1802fe0ad  jns     short loc_1802FE0DC
0x1802fe0af  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fe0b6  mov     [rbp+57h+var_C0], rax
0x1802fe0ba  mov     [rbp+57h+var_B8], 1ABh
0x1802fe0c1  lea     rdx, [rbp+57h+var_C0]
0x1802fe0c5  lea     rcx, [rbp+57h+pv]
0x1802fe0c9  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fe0ce  nop
0x1802fe0cf  mov     rdx, rax
0x1802fe0d2  lea     rcx, [rbp+57h+var_C0]
0x1802fe0d6  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fe0dc  mov     qword ptr [rbp+57h+pui], 0
0x1802fe0e4  lea     rdx, [rbp+57h+pui]; pui
0x1802fe0e8  mov     rcx, [rbp+57h+var_B0]; pstm
0x1802fe0ec  call    cs:__imp_IStream_Size
0x1802fe0f2  mov     r8d, eax
0x1802fe0f5  test    eax, eax
0x1802fe0f7  jns     short loc_1802FE126
0x1802fe0f9  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fe100  mov     [rbp+57h+var_C0], rax
0x1802fe104  mov     [rbp+57h+var_B8], 1AFh
0x1802fe10b  lea     rdx, [rbp+57h+var_C0]
0x1802fe10f  lea     rcx, [rbp+57h+pv]
0x1802fe113  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fe118  nop
0x1802fe119  mov     rdx, rax
0x1802fe11c  lea     rcx, [rbp+57h+var_C0]
0x1802fe120  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fe126  mov     rdx, qword ptr [rbp+57h+pui]
0x1802fe12a  lea     rcx, [rbp+57h+pv]
0x1802fe12e  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1802fe133  nop
0x1802fe134  mov     r8d, dword ptr [rbp+57h+pui]; cb
0x1802fe138  mov     rdx, [rbp+57h+pv]; pv
0x1802fe13c  mov     rcx, [rbp+57h+var_B0]; pstm
0x1802fe140  call    cs:__imp_IStream_Read
0x1802fe146  mov     r8d, eax
0x1802fe149  test    eax, eax
0x1802fe14b  jns     short loc_1802FE17A
0x1802fe14d  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fe154  mov     [rbp+57h+var_C0], rax
0x1802fe158  mov     [rbp+57h+var_B8], 1B1h
0x1802fe15f  lea     rdx, [rbp+57h+var_C0]
0x1802fe163  lea     rcx, [rbp+57h+var_88]
0x1802fe167  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fe16c  nop
0x1802fe16d  mov     rdx, rax
0x1802fe170  lea     rcx, [rbp+57h+var_C0]
0x1802fe174  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fe17a  lea     rdx, [rbp+57h+pv]
0x1802fe17e  mov     rcx, rbx
0x1802fe181  call    ?EncodeBase64@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@3@@Z; cdp::EncodeBase64(std::vector<uchar> const &)
0x1802fe186  nop
0x1802fe187  lea     rcx, [rbp+57h+pv]
0x1802fe18b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1802fe190  nop
0x1802fe191  lea     rcx, [rbp+57h+var_98]
0x1802fe195  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fe19a  nop
0x1802fe19b  lea     rcx, [rbp+57h+var_B0]
0x1802fe19f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fe1a4  nop
0x1802fe1a5  lea     rcx, [rbp+57h+pstm]
0x1802fe1a9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fe1ae  mov     rax, rbx
0x1802fe1b1  mov     rcx, [rbp+57h+var_18]
0x1802fe1b5  xor     rcx, rsp; StackCookie
0x1802fe1b8  call    __security_check_cookie
0x1802fe1bd  mov     rbx, [rsp+0F0h+arg_18]
0x1802fe1c5  add     rsp, 0E0h
0x1802fe1cc  pop     rdi
0x1802fe1cd  pop     rsi
0x1802fe1ce  pop     rbp
0x1802fe1cf  retn
```
