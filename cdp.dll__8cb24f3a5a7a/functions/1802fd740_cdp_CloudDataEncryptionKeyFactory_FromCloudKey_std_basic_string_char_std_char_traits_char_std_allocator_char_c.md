# cdp::CloudDataEncryptionKeyFactory::FromCloudKey(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1802fd740`
- end: `0x1802fdb87`
- name: `?FromCloudKey@CloudDataEncryptionKeyFactory@cdp@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z`
- size: `1095`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802fd6d0`

## callees

- `0x18000aec4`
- `0x18000b724`
- `0x18000d098`
- `0x18001ce80`
- `0x18003d0e0`
- `0x1800624cc`
- `0x18007039c`
- `0x1800ad100`
- `0x1800fd420`
- `0x18011d8c4`
- `0x18017b5a0`
- `0x1801f6fb0`
- `0x1802fd740`
- `0x1802fe214`
- `0x180354010`

## import_xrefs

- `SHCORE!IStream_Write` at `0x1802fd7d2`
- `SHCORE!IStream_Write` at `0x1802fd7d2`
- `SHCORE!IStream_ReadStr` at `0x1802fdaca`
- `SHCORE!IStream_ReadStr` at `0x1802fdaca`
- `SHCORE!IStream_WriteStr` at `0x1802fd8f1`
- `SHCORE!IStream_WriteStr` at `0x1802fd8f1`
- `SHCORE!IStream_Reset` at `0x1802fd810`
- `SHCORE!IStream_Reset` at `0x1802fd92f`
- `SHCORE!IStream_Reset` at `0x1802fda75`
- `SHCORE!IStream_Reset` at `0x1802fd810`
- `SHCORE!IStream_Reset` at `0x1802fd92f`
- `SHCORE!IStream_Reset` at `0x1802fda75`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall cdp::CloudDataEncryptionKeyFactory::FromCloudKey(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rax
  HRESULT v9; // eax
  __int64 v10; // rax
  HRESULT v11; // eax
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rax
  HRESULT v21; // eax
  __int64 v22; // rax
  HRESULT v23; // eax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  HRESULT v33; // eax
  __int64 v34; // rax
  HRESULT v35; // eax
  __int64 v36; // rax
  __int64 v37; // rax
  IStream *v39; // [rsp+30h] [rbp-79h] BYREF
  IStream *v40; // [rsp+38h] [rbp-71h] BYREF
  IStream *pstm; // [rsp+40h] [rbp-69h] BYREF
  PWSTR ppsz; // [rsp+48h] [rbp-61h] BYREF
  __int64 v43; // [rsp+50h] [rbp-59h] BYREF
  LPVOID v44; // [rsp+58h] [rbp-51h] BYREF
  __int64 v45; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v46[56]; // [rsp+70h] [rbp-39h] BYREF
  void *pv; // [rsp+A8h] [rbp-1h] BYREF
  int v48; // [rsp+B0h] [rbp+7h]
  const char *v49; // [rsp+C0h] [rbp+17h] BYREF
  int v50; // [rsp+C8h] [rbp+1Fh]

  v45 = a2;
  cdp::DecodeBase64(&pv, a3);
  pstm = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pstm);
  v7 = SHCreateMemoryStream(v6, v5, &pstm);
  if ( v7 < 0 )
  {
    v49 = ".\\clouddataencryptionkeyfactory.cpp";
    v50 = 378;
    v8 = cdp::MakeException<cdp::hresult_exception>(v46, &v49, (unsigned int)v7);
    cdp::CdpThrow<cdp::hresult_exception>(&v49, v8);
  }
  v9 = IStream_Write(pstm, pv, v48 - (_DWORD)pv);
  if ( v9 < 0 )
  {
    v49 = ".\\clouddataencryptionkeyfactory.cpp";
    v50 = 379;
    v10 = cdp::MakeException<cdp::hresult_exception>(v46, &v49, (unsigned int)v9);
    cdp::CdpThrow<cdp::hresult_exception>(&v49, v10);
  }
  v11 = IStream_Reset(pstm);
  if ( v11 < 0 )
  {
    v49 = ".\\clouddataencryptionkeyfactory.cpp";
    v50 = 380;
    v12 = cdp::MakeException<cdp::hresult_exception>(v46, &v49, (unsigned int)v11);
    cdp::CdpThrow<cdp::hresult_exception>(&v49, v12);
  }
  v40 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
  v15 = SHCreateMemoryStream(v14, v13, &v40);
  if ( v15 < 0 )
  {
    v49 = ".\\clouddataencryptionkeyfactory.cpp";
    v50 = 383;
    v16 = cdp::MakeException<cdp::hresult_exception>(v46, &v49, (unsigned int)v15);
    cdp::CdpThrow<cdp::hresult_exception>(&v49, v16);
  }
  v39 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
  v19 = SHCreateMemoryStream(v18, v17, &v39);
  if ( v19 < 0 )
  {
    v49 = ".\\clouddataencryptionkeyfactory.cpp";
    v50 = 391;
    v20 = cdp::MakeException<cdp::hresult_exception>(v46, &v49, (unsigned int)v19);
    cdp::CdpThrow<cdp::hresult_exception>(&v49, v20);
  }
  v21 = IStream_WriteStr(v39, L"foo");
  if ( v21 < 0 )
  {
    v49 = ".\\clouddataencryptionkeyfactory.cpp";
    v50 = 392;
    v22 = cdp::MakeException<cdp::hresult_exception>(v46, &v49, (unsigned int)v21);
    cdp::CdpThrow<cdp::hresult_exception>(&v49, v22);
  }
  v23 = IStream_Reset(v39);
  if ( v23 < 0 )
  {
    v49 = ".\\clouddataencryptionkeyfactory.cpp";
    v50 = 393;
    v24 = cdp::MakeException<cdp::hresult_exception>(v46, &v49, (unsigned int)v23);
    cdp::CdpThrow<cdp::hresult_exception>(&v49, v24);
  }
  v43 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
  v27 = SHCreateMemoryStream(v26, v25, &v43);
  if ( v27 < 0 )
  {
    v49 = ".\\clouddataencryptionkeyfactory.cpp";
    v50 = 396;
    v28 = cdp::MakeException<cdp::hresult_exception>(v46, &v49, (unsigned int)v27);
    cdp::CdpThrow<cdp::hresult_exception>(&v49, v28);
  }
  cdp::CloudDataEncryptionKeyFactory::GetRoamingSecurity(a1, &v44);
  v29 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, IStream *, __int64))(*(_QWORD *)v44 + 32LL))(v44, 0, v39, v43);
  if ( v29 < 0 )
  {
    v49 = ".\\clouddataencryptionkeyfactory.cpp";
    v50 = 398;
    v30 = cdp::MakeException<cdp::hresult_exception>(v46, &v49, (unsigned int)v29);
    cdp::CdpThrow<cdp::hresult_exception>(&v49, v30);
  }
  v45 = 0;
  v31 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, IStream *, IStream *, __int64 *))(*(_QWORD *)v44 + 40LL))(
          v44,
          0,
          pstm,
          v40,
          &v45);
  if ( v31 < 0 )
  {
    v49 = ".\\clouddataencryptionkeyfactory.cpp";
    v50 = 401;
    v32 = cdp::MakeException<cdp::hresult_exception>(v46, &v49, (unsigned int)v31);
    cdp::CdpThrow<cdp::hresult_exception>(&v49, v32);
  }
  v33 = IStream_Reset(v40);
  if ( v33 < 0 )
  {
    v49 = ".\\clouddataencryptionkeyfactory.cpp";
    v50 = 403;
    v34 = cdp::MakeException<cdp::hresult_exception>(v46, &v49, (unsigned int)v33);
    cdp::CdpThrow<cdp::hresult_exception>(&v49, v34);
  }
  ppsz = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppsz,
    0,
    (unsigned int)v33);
  v35 = IStream_ReadStr(v40, &ppsz);
  if ( v35 < 0 )
  {
    v49 = ".\\clouddataencryptionkeyfactory.cpp";
    v50 = 407;
    v36 = cdp::MakeException<cdp::hresult_exception>(v46, &v49, (unsigned int)v35);
    cdp::CdpThrow<cdp::hresult_exception>(&v49, v36);
  }
  v37 = std::wstring::wstring(&v49, ppsz);
  cdp::ToUtf8(a2, v37);
  std::wstring::_Tidy_deallocate(&v49);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppsz);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pstm);
  std::vector<unsigned char>::_Tidy(&pv);
  return a2;
}

```

## disassembly

```asm
0x1802fd740  push    rbp
0x1802fd742  push    rbx
0x1802fd743  push    rdi
0x1802fd744  lea     rbp, [rsp-47h]
0x1802fd749  sub     rsp, 0F0h
0x1802fd750  mov     rax, cs:__security_cookie
0x1802fd757  xor     rax, rsp
0x1802fd75a  mov     [rbp+57h+var_20], rax
0x1802fd75e  mov     rbx, rdx
0x1802fd761  mov     rdi, rcx
0x1802fd764  mov     [rbp+57h+var_A0], rdx
0x1802fd768  mov     rdx, r8
0x1802fd76b  lea     rcx, [rbp+57h+pv]
0x1802fd76f  call    ?DecodeBase64@cdp@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::DecodeBase64(std::string const &)
0x1802fd774  nop
0x1802fd775  mov     [rbp+57h+pstm], 0
0x1802fd77d  lea     rcx, [rbp+57h+pstm]
0x1802fd781  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fd786  lea     r8, [rbp+57h+pstm]
0x1802fd78a  call    SHCreateMemoryStream
0x1802fd78f  mov     r8d, eax
0x1802fd792  test    eax, eax
0x1802fd794  jns     short loc_1802FD7C3
0x1802fd796  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fd79d  mov     [rbp+57h+var_40], rax
0x1802fd7a1  mov     [rbp+57h+var_38], 17Ah
0x1802fd7a8  lea     rdx, [rbp+57h+var_40]
0x1802fd7ac  lea     rcx, [rbp+57h+var_90]
0x1802fd7b0  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fd7b5  nop
0x1802fd7b6  mov     rdx, rax
0x1802fd7b9  lea     rcx, [rbp+57h+var_40]
0x1802fd7bd  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fd7c3  mov     rdx, [rbp+57h+pv]; pv
0x1802fd7c7  mov     r8d, [rbp+57h+var_50]
0x1802fd7cb  sub     r8d, edx; cb
0x1802fd7ce  mov     rcx, [rbp+57h+pstm]; pstm
0x1802fd7d2  call    cs:__imp_IStream_Write
0x1802fd7d8  mov     r8d, eax
0x1802fd7db  test    eax, eax
0x1802fd7dd  jns     short loc_1802FD80C
0x1802fd7df  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fd7e6  mov     [rbp+57h+var_40], rax
0x1802fd7ea  mov     [rbp+57h+var_38], 17Bh
0x1802fd7f1  lea     rdx, [rbp+57h+var_40]
0x1802fd7f5  lea     rcx, [rbp+57h+var_90]
0x1802fd7f9  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fd7fe  nop
0x1802fd7ff  mov     rdx, rax
0x1802fd802  lea     rcx, [rbp+57h+var_40]
0x1802fd806  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fd80c  mov     rcx, [rbp+57h+pstm]; pstm
0x1802fd810  call    cs:__imp_IStream_Reset
0x1802fd816  mov     r8d, eax
0x1802fd819  test    eax, eax
0x1802fd81b  jns     short loc_1802FD84A
0x1802fd81d  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fd824  mov     [rbp+57h+var_40], rax
0x1802fd828  mov     [rbp+57h+var_38], 17Ch
0x1802fd82f  lea     rdx, [rbp+57h+var_40]
0x1802fd833  lea     rcx, [rbp+57h+var_90]
0x1802fd837  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fd83c  nop
0x1802fd83d  mov     rdx, rax
0x1802fd840  lea     rcx, [rbp+57h+var_40]
0x1802fd844  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fd84a  mov     [rbp+57h+var_C8], 0
0x1802fd852  lea     rcx, [rbp+57h+var_C8]
0x1802fd856  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fd85b  lea     r8, [rbp+57h+var_C8]
0x1802fd85f  call    SHCreateMemoryStream
0x1802fd864  mov     r8d, eax
0x1802fd867  test    eax, eax
0x1802fd869  jns     short loc_1802FD898
0x1802fd86b  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fd872  mov     [rbp+57h+var_40], rax
0x1802fd876  mov     [rbp+57h+var_38], 17Fh
0x1802fd87d  lea     rdx, [rbp+57h+var_40]
0x1802fd881  lea     rcx, [rbp+57h+var_90]
0x1802fd885  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fd88a  nop
0x1802fd88b  mov     rdx, rax
0x1802fd88e  lea     rcx, [rbp+57h+var_40]
0x1802fd892  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fd898  mov     [rbp+57h+var_D0], 0
0x1802fd8a0  lea     rcx, [rbp+57h+var_D0]
0x1802fd8a4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fd8a9  lea     r8, [rbp+57h+var_D0]
0x1802fd8ad  call    SHCreateMemoryStream
0x1802fd8b2  mov     r8d, eax
0x1802fd8b5  test    eax, eax
0x1802fd8b7  jns     short loc_1802FD8E6
0x1802fd8b9  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fd8c0  mov     [rbp+57h+var_40], rax
0x1802fd8c4  mov     [rbp+57h+var_38], 187h
0x1802fd8cb  lea     rdx, [rbp+57h+var_40]
0x1802fd8cf  lea     rcx, [rbp+57h+var_90]
0x1802fd8d3  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fd8d8  nop
0x1802fd8d9  mov     rdx, rax
0x1802fd8dc  lea     rcx, [rbp+57h+var_40]
0x1802fd8e0  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fd8e6  lea     rdx, psz; "foo"
0x1802fd8ed  mov     rcx, [rbp+57h+var_D0]; pstm
0x1802fd8f1  call    cs:__imp_IStream_WriteStr
0x1802fd8f7  mov     r8d, eax
0x1802fd8fa  test    eax, eax
0x1802fd8fc  jns     short loc_1802FD92B
0x1802fd8fe  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fd905  mov     [rbp+57h+var_40], rax
0x1802fd909  mov     [rbp+57h+var_38], 188h
0x1802fd910  lea     rdx, [rbp+57h+var_40]
0x1802fd914  lea     rcx, [rbp+57h+var_90]
0x1802fd918  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fd91d  nop
0x1802fd91e  mov     rdx, rax
0x1802fd921  lea     rcx, [rbp+57h+var_40]
0x1802fd925  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fd92b  mov     rcx, [rbp+57h+var_D0]; pstm
0x1802fd92f  call    cs:__imp_IStream_Reset
0x1802fd935  mov     r8d, eax
0x1802fd938  test    eax, eax
0x1802fd93a  jns     short loc_1802FD969
0x1802fd93c  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fd943  mov     [rbp+57h+var_40], rax
0x1802fd947  mov     [rbp+57h+var_38], 189h
0x1802fd94e  lea     rdx, [rbp+57h+var_40]
0x1802fd952  lea     rcx, [rbp+57h+var_90]
0x1802fd956  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fd95b  nop
0x1802fd95c  mov     rdx, rax
0x1802fd95f  lea     rcx, [rbp+57h+var_40]
0x1802fd963  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fd969  mov     [rbp+57h+var_B0], 0
0x1802fd971  lea     rcx, [rbp+57h+var_B0]
0x1802fd975  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fd97a  lea     r8, [rbp+57h+var_B0]
0x1802fd97e  call    SHCreateMemoryStream
0x1802fd983  mov     r8d, eax
0x1802fd986  test    eax, eax
0x1802fd988  jns     short loc_1802FD9B7
0x1802fd98a  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fd991  mov     [rbp+57h+var_40], rax
0x1802fd995  mov     [rbp+57h+var_38], 18Ch
0x1802fd99c  lea     rdx, [rbp+57h+var_40]
0x1802fd9a0  lea     rcx, [rbp+57h+var_90]
0x1802fd9a4  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fd9a9  nop
0x1802fd9aa  mov     rdx, rax
0x1802fd9ad  lea     rcx, [rbp+57h+var_40]
0x1802fd9b1  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fd9b7  lea     rdx, [rbp+57h+var_A8]
0x1802fd9bb  mov     rcx, rdi
0x1802fd9be  call    ?GetRoamingSecurity@CloudDataEncryptionKeyFactory@cdp@@AEAA?AV?$ComPtr@UIRoamingSecurity@@@WRL@Microsoft@@XZ; cdp::CloudDataEncryptionKeyFactory::GetRoamingSecurity(void)
0x1802fd9c3  nop
0x1802fd9c4  mov     rcx, [rbp+57h+var_A8]
0x1802fd9c8  mov     rax, [rcx]
0x1802fd9cb  mov     r9, [rbp+57h+var_B0]
0x1802fd9cf  mov     r8, [rbp+57h+var_D0]
0x1802fd9d3  xor     edx, edx
0x1802fd9d5  mov     rax, [rax+20h]
0x1802fd9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fd9de  mov     r8d, eax
0x1802fd9e1  test    eax, eax
0x1802fd9e3  jns     short loc_1802FDA12
0x1802fd9e5  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fd9ec  mov     [rbp+57h+var_40], rax
0x1802fd9f0  mov     [rbp+57h+var_38], 18Eh
0x1802fd9f7  lea     rdx, [rbp+57h+var_40]
0x1802fd9fb  lea     rcx, [rbp+57h+var_90]
0x1802fd9ff  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fda04  nop
0x1802fda05  mov     rdx, rax
0x1802fda08  lea     rcx, [rbp+57h+var_40]
0x1802fda0c  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fda12  mov     [rbp+57h+var_A0], 0
0x1802fda1a  mov     rcx, [rbp+57h+var_A8]
0x1802fda1e  mov     rax, [rcx]
0x1802fda21  lea     rdx, [rbp+57h+var_A0]
0x1802fda25  mov     [rsp+100h+var_E0], rdx
0x1802fda2a  mov     r9, [rbp+57h+var_C8]
0x1802fda2e  mov     r8, [rbp+57h+pstm]
0x1802fda32  xor     edx, edx
0x1802fda34  mov     rax, [rax+28h]
0x1802fda38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fda3d  mov     r8d, eax
0x1802fda40  test    eax, eax
0x1802fda42  jns     short loc_1802FDA71
0x1802fda44  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fda4b  mov     [rbp+57h+var_40], rax
0x1802fda4f  mov     [rbp+57h+var_38], 191h
0x1802fda56  lea     rdx, [rbp+57h+var_40]
0x1802fda5a  lea     rcx, [rbp+57h+var_90]
0x1802fda5e  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fda63  nop
0x1802fda64  mov     rdx, rax
0x1802fda67  lea     rcx, [rbp+57h+var_40]
0x1802fda6b  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fda71  mov     rcx, [rbp+57h+var_C8]; pstm
0x1802fda75  call    cs:__imp_IStream_Reset
0x1802fda7b  mov     r8d, eax
0x1802fda7e  test    eax, eax
0x1802fda80  jns     short loc_1802FDAAF
0x1802fda82  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fda89  mov     [rbp+57h+var_40], rax
0x1802fda8d  mov     [rbp+57h+var_38], 193h
0x1802fda94  lea     rdx, [rbp+57h+var_40]
0x1802fda98  lea     rcx, [rbp+57h+var_90]
0x1802fda9c  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fdaa1  nop
0x1802fdaa2  mov     rdx, rax
0x1802fdaa5  lea     rcx, [rbp+57h+var_40]
0x1802fdaa9  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fdaaf  mov     [rbp+57h+ppsz], 0
0x1802fdab7  xor     edx, edx
0x1802fdab9  lea     rcx, [rbp+57h+ppsz]
0x1802fdabd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1802fdac2  lea     rdx, [rbp+57h+ppsz]; ppsz
0x1802fdac6  mov     rcx, [rbp+57h+var_C8]; pstm
0x1802fdaca  call    cs:__imp_IStream_ReadStr
0x1802fdad0  mov     r8d, eax
0x1802fdad3  test    eax, eax
0x1802fdad5  jns     short loc_1802FDB04
0x1802fdad7  lea     rax, aClouddataencry_0; ".\\clouddataencryptionkeyfactory.cpp"
0x1802fdade  mov     [rbp+57h+var_40], rax
0x1802fdae2  mov     [rbp+57h+var_38], 197h
0x1802fdae9  lea     rdx, [rbp+57h+var_40]
0x1802fdaed  lea     rcx, [rbp+57h+var_90]
0x1802fdaf1  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1802fdaf6  nop
0x1802fdaf7  mov     rdx, rax
0x1802fdafa  lea     rcx, [rbp+57h+var_40]
0x1802fdafe  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1802fdb04  mov     rdx, [rbp+57h+ppsz]
0x1802fdb08  lea     rcx, [rbp+57h+var_40]
0x1802fdb0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1802fdb11  nop
0x1802fdb12  mov     rdx, rax
0x1802fdb15  mov     rcx, rbx
0x1802fdb18  call    ?ToUtf8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; cdp::ToUtf8(std::wstring const &)
0x1802fdb1d  nop
0x1802fdb1e  lea     rcx, [rbp+57h+var_40]
0x1802fdb22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802fdb27  nop
0x1802fdb28  lea     rcx, [rbp+57h+ppsz]
0x1802fdb2c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802fdb31  nop
0x1802fdb32  lea     rcx, [rbp+57h+var_A8]
0x1802fdb36  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fdb3b  nop
0x1802fdb3c  lea     rcx, [rbp+57h+var_B0]
0x1802fdb40  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fdb45  nop
0x1802fdb46  lea     rcx, [rbp+57h+var_D0]
0x1802fdb4a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fdb4f  nop
0x1802fdb50  lea     rcx, [rbp+57h+var_C8]
0x1802fdb54  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fdb59  nop
0x1802fdb5a  lea     rcx, [rbp+57h+pstm]
0x1802fdb5e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1802fdb63  nop
0x1802fdb64  lea     rcx, [rbp+57h+pv]
0x1802fdb68  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1802fdb6d  mov     rax, rbx
0x1802fdb70  mov     rcx, [rbp+57h+var_20]
0x1802fdb74  xor     rcx, rsp; StackCookie
0x1802fdb77  call    __security_check_cookie
0x1802fdb7c  add     rsp, 0F0h
0x1802fdb83  pop     rdi
0x1802fdb84  pop     rbx
0x1802fdb85  pop     rbp
0x1802fdb86  retn
```
