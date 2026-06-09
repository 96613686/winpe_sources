# shared::ComObjectCreator::UserMgrAwareGetHandlerInternal(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,unsigned __int64,_GUID const &,void * *)

- ea: `0x1801eaacc`
- end: `0x1801eace6`
- name: `?UserMgrAwareGetHandlerInternal@ComObjectCreator@shared@@CAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_KAEBU_GUID@@PEAPEAX@Z`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180212100`

## callees

- `0x18000b724`
- `0x1800624cc`
- `0x1800a11bc`
- `0x1800f6608`
- `0x1800fc534`
- `0x1800fd6c4`
- `0x18011d5d0`
- `0x18011d808`
- `0x1801eaacc`
- `0x1801eacec`
- `0x1801ead90`
- `0x1801f6fb0`

## import_xrefs

- `combase!__imp_CoCreateInstanceAsUser` at `0x1801eabd3`
- `combase!__imp_CoCreateInstanceAsUser` at `0x1801eabd3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801eab53`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801eab53`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801eac3f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801eac3f`

## string_xrefs

- `0x1801eab04`: `.\comobjectcreator.cpp`
- `0x1801eab60`: `.\comobjectcreator.cpp`
- `0x1801eabe4`: `.\comobjectcreator.cpp`
- `0x1801eac4c`: `.\comobjectcreator.cpp`
- `0x1801eac75`: `Failed to CoCreateInstance COM object with CLSID %s`
- `0x1801eab89`: `Failed to convert string %s to CLSID, cannot CoCreateInstance`
- `0x1801eab16`: `clsid was empty`
- `0x1801eacb6`: `{"text":"CoCreated object from CLSID %ws"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall shared::ComObjectCreator::UserMgrAwareGetHandlerInternal(
        _QWORD *a1,
        _QWORD *a2,
        const IID *a3,
        LPVOID *a4)
{
  _QWORD *v7; // rbx
  __int64 v8; // rax
  const OLECHAR *v9; // rcx
  HRESULT v10; // r8d
  __int64 v11; // rax
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rax
  HRESULT v15; // r8d
  __int64 v16; // rax
  __int64 v17; // rcx
  LPCOLESTR *v18; // rax
  const char *v20; // [rsp+30h] [rbp-79h] BYREF
  int v21; // [rsp+38h] [rbp-71h]
  _QWORD *v22; // [rsp+40h] [rbp-69h] BYREF
  _QWORD *v23; // [rsp+48h] [rbp-61h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-59h] BYREF
  int v25; // [rsp+58h] [rbp-51h]
  _BYTE v26[56]; // [rsp+68h] [rbp-41h] BYREF
  LPCOLESTR lpsz[3]; // [rsp+A0h] [rbp-9h] BYREF
  unsigned __int64 v28; // [rsp+B8h] [rbp+Fh]
  GUID pclsid; // [rsp+C0h] [rbp+17h] BYREF

  v7 = a1;
  v22 = a2;
  if ( !a1[2] )
  {
    v20 = ".\\comobjectcreator.cpp";
    v21 = 118;
    v8 = cdp::MakeException<std::invalid_argument,>(&TokenHandle, a2, "clsid was empty");
    cdp::CdpThrow<std::invalid_argument>(&v20, v8);
  }
  cdp::ToWstring(lpsz, a1);
  v9 = (const OLECHAR *)lpsz;
  if ( v28 > 7 )
    v9 = lpsz[0];
  v10 = CLSIDFromString(v9, &pclsid);
  if ( v10 < 0 )
  {
    TokenHandle = ".\\comobjectcreator.cpp";
    v25 = 124;
    if ( v7[3] > 0xFu )
      v7 = (_QWORD *)*v7;
    v22 = v7;
    v11 = cdp::MakeException<cdp::hresult_exception,unsigned short const *>(
            (unsigned int)v26,
            (unsigned int)&TokenHandle,
            v10,
            (unsigned int)"Failed to convert string %s to CLSID, cannot CoCreateInstance",
            (__int64)&v22);
    cdp::CdpThrow<cdp::hresult_exception>(&TokenHandle, v11);
  }
  shared::SuspendImpersonationScope::SuspendImpersonationScope(&TokenHandle);
  if ( a2 )
  {
    v12 = CoCreateInstanceAsUser(&pclsid, 0, 1048580, a2, a3, a4);
    if ( v12 < 0 )
    {
      v20 = ".\\comobjectcreator.cpp";
      v21 = 137;
      if ( v7[3] > 0xFu )
        v7 = (_QWORD *)*v7;
      v23 = v7;
      v14 = cdp::MakeException<cdp::hresult_exception,char const *,unsigned __int64 &>(
              (unsigned int)v26,
              (unsigned int)&v20,
              v12,
              v13,
              (__int64)&v23,
              (__int64)&v22);
      cdp::CdpThrow<cdp::hresult_exception>(&v20, v14);
    }
  }
  else
  {
    v15 = CoCreateInstance(&pclsid, 0, 0x100017u, a3, a4);
    if ( v15 < 0 )
    {
      v20 = ".\\comobjectcreator.cpp";
      v21 = 142;
      if ( v7[3] > 0xFu )
        v7 = (_QWORD *)*v7;
      v23 = v7;
      v16 = cdp::MakeException<cdp::hresult_exception,unsigned short const *>(
              (unsigned int)v26,
              (unsigned int)&v20,
              v15,
              (unsigned int)"Failed to CoCreateInstance COM object with CLSID %s",
              (__int64)&v23);
      cdp::CdpThrow<cdp::hresult_exception>(&v20, v16);
    }
  }
  shared::SuspendImpersonationScope::~SuspendImpersonationScope((shared::SuspendImpersonationScope *)&TokenHandle);
  v18 = lpsz;
  if ( v28 > 7 )
    v18 = (LPCOLESTR *)lpsz[0];
  TokenHandle = v18;
  Log<unsigned short const *>(v17, "{\"text\":\"CoCreated object from CLSID %ws\"}", &TokenHandle);
  return std::wstring::_Tidy_deallocate(lpsz);
}

```

## disassembly

```asm
0x1801eaacc  push    rbp
0x1801eaace  push    rbx
0x1801eaacf  push    rsi
0x1801eaad0  push    rdi
0x1801eaad1  push    r14
0x1801eaad3  lea     rbp, [rsp-37h]
0x1801eaad8  sub     rsp, 0E0h
0x1801eaadf  mov     rax, cs:__security_cookie
0x1801eaae6  xor     rax, rsp
0x1801eaae9  mov     [rbp+57h+var_30], rax
0x1801eaaed  mov     r14, r9
0x1801eaaf0  mov     rsi, r8
0x1801eaaf3  mov     rdi, rdx
0x1801eaaf6  mov     rbx, rcx
0x1801eaaf9  mov     [rbp+57h+var_C0], rdx
0x1801eaafd  cmp     qword ptr [rcx+10h], 0
0x1801eab02  ja      short loc_1801EAB34
0x1801eab04  lea     rax, aComobjectcreat; ".\\comobjectcreator.cpp"
0x1801eab0b  mov     [rbp+57h+var_D0], rax
0x1801eab0f  mov     [rbp+57h+var_C8], 76h ; 'v'
0x1801eab16  lea     r8, aClsidWasEmpty; "clsid was empty"
0x1801eab1d  lea     rcx, [rbp+57h+TokenHandle]
0x1801eab21  call    ??$MakeException@Vinvalid_argument@std@@$$V@cdp@@YA?AVinvalid_argument@std@@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<std::invalid_argument,>(cdp::CDPSourceLocationInfo const &,char const *)
0x1801eab26  nop
0x1801eab27  mov     rdx, rax
0x1801eab2a  lea     rcx, [rbp+57h+var_D0]
0x1801eab2e  call    ??$CdpThrow@Vinvalid_argument@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVinvalid_argument@std@@@Z; cdp::CdpThrow<std::invalid_argument>(cdp::CDPSourceLocationInfo const &,std::invalid_argument &&)
0x1801eab34  mov     rdx, rbx
0x1801eab37  lea     rcx, [rbp+57h+lpsz]
0x1801eab3b  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x1801eab40  nop
0x1801eab41  lea     rcx, [rbp+57h+lpsz]
0x1801eab45  cmp     [rbp+57h+var_48], 7
0x1801eab4a  cmova   rcx, [rbp+57h+lpsz]; lpsz
0x1801eab4f  lea     rdx, [rbp+57h+pclsid]; pclsid
0x1801eab53  call    cs:__imp_CLSIDFromString
0x1801eab59  mov     r8d, eax
0x1801eab5c  test    eax, eax
0x1801eab5e  jns     short loc_1801EABAB
0x1801eab60  lea     rax, aComobjectcreat; ".\\comobjectcreator.cpp"
0x1801eab67  mov     [rbp+57h+TokenHandle], rax
0x1801eab6b  mov     [rbp+57h+var_A8], 7Ch ; '|'
0x1801eab72  cmp     qword ptr [rbx+18h], 0Fh
0x1801eab77  jbe     short loc_1801EAB7C
0x1801eab79  mov     rbx, [rbx]
0x1801eab7c  mov     [rbp+57h+var_C0], rbx
0x1801eab80  lea     rax, [rbp+57h+var_C0]
0x1801eab84  mov     [rsp+100h+ppv], rax
0x1801eab89  lea     r9, aFailedToConver_5; "Failed to convert string %s to CLSID, c"...
0x1801eab90  lea     rdx, [rbp+57h+TokenHandle]
0x1801eab94  lea     rcx, [rbp+57h+var_98]
0x1801eab98  call    ??$MakeException@Vhresult_exception@cdp@@PEBG@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD$$QEAPEBG@Z; cdp::MakeException<cdp::hresult_exception,ushort const *>(cdp::CDPSourceLocationInfo const &,int,char const *,ushort const * &&)
0x1801eab9d  nop
0x1801eab9e  mov     rdx, rax
0x1801eaba1  lea     rcx, [rbp+57h+TokenHandle]
0x1801eaba5  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801eabab  lea     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1801eabaf  call    ??0SuspendImpersonationScope@shared@@QEAA@XZ; shared::SuspendImpersonationScope::SuspendImpersonationScope(void)
0x1801eabb4  nop
0x1801eabb5  xor     edx, edx; pUnkOuter
0x1801eabb7  lea     rcx, [rbp+57h+pclsid]; rclsid
0x1801eabbb  test    rdi, rdi
0x1801eabbe  jz      short loc_1801EAC31
0x1801eabc0  mov     [rsp+100h+var_D8], r14
0x1801eabc5  mov     [rsp+100h+ppv], rsi
0x1801eabca  mov     r9, rdi
0x1801eabcd  mov     r8d, 100004h
0x1801eabd3  call    cs:__imp_CoCreateInstanceAsUser
0x1801eabd9  mov     r8d, eax
0x1801eabdc  test    eax, eax
0x1801eabde  jns     loc_1801EAC97
0x1801eabe4  lea     rax, aComobjectcreat; ".\\comobjectcreator.cpp"
0x1801eabeb  mov     [rbp+57h+var_D0], rax
0x1801eabef  mov     [rbp+57h+var_C8], 89h
0x1801eabf6  cmp     qword ptr [rbx+18h], 0Fh
0x1801eabfb  jbe     short loc_1801EAC00
0x1801eabfd  mov     rbx, [rbx]
0x1801eac00  mov     [rbp+57h+var_B8], rbx
0x1801eac04  lea     rax, [rbp+57h+var_C0]
0x1801eac08  mov     [rsp+100h+var_D8], rax
0x1801eac0d  lea     rax, [rbp+57h+var_B8]
0x1801eac11  mov     [rsp+100h+ppv], rax
0x1801eac16  lea     rdx, [rbp+57h+var_D0]
0x1801eac1a  lea     rcx, [rbp+57h+var_98]
0x1801eac1e  call    ??$MakeException@Vhresult_exception@cdp@@PEBDAEA_K@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD$$QEAPEBDAEA_K@Z; cdp::MakeException<cdp::hresult_exception,char const *,unsigned __int64 &>(cdp::CDPSourceLocationInfo const &,int,char const *,char const * &&,unsigned __int64 &)
0x1801eac23  nop
0x1801eac24  mov     rdx, rax
0x1801eac27  lea     rcx, [rbp+57h+var_D0]
0x1801eac2b  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801eac31  mov     [rsp+100h+ppv], r14; ppv
0x1801eac36  mov     r9, rsi; riid
0x1801eac39  mov     r8d, 100017h; dwClsContext
0x1801eac3f  call    cs:__imp_CoCreateInstance
0x1801eac45  mov     r8d, eax
0x1801eac48  test    eax, eax
0x1801eac4a  jns     short loc_1801EAC97
0x1801eac4c  lea     rax, aComobjectcreat; ".\\comobjectcreator.cpp"
0x1801eac53  mov     [rbp+57h+var_D0], rax
0x1801eac57  mov     [rbp+57h+var_C8], 8Eh
0x1801eac5e  cmp     qword ptr [rbx+18h], 0Fh
0x1801eac63  jbe     short loc_1801EAC68
0x1801eac65  mov     rbx, [rbx]
0x1801eac68  mov     [rbp+57h+var_B8], rbx
0x1801eac6c  lea     rax, [rbp+57h+var_B8]
0x1801eac70  mov     [rsp+100h+ppv], rax
0x1801eac75  lea     r9, aFailedToCocrea_2; "Failed to CoCreateInstance COM object w"...
0x1801eac7c  lea     rdx, [rbp+57h+var_D0]
0x1801eac80  lea     rcx, [rbp+57h+var_98]
0x1801eac84  call    ??$MakeException@Vhresult_exception@cdp@@PEBG@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD$$QEAPEBG@Z; cdp::MakeException<cdp::hresult_exception,ushort const *>(cdp::CDPSourceLocationInfo const &,int,char const *,ushort const * &&)
0x1801eac89  nop
0x1801eac8a  mov     rdx, rax
0x1801eac8d  lea     rcx, [rbp+57h+var_D0]
0x1801eac91  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801eac97  lea     rcx, [rbp+57h+TokenHandle]; this
0x1801eac9b  call    ??1SuspendImpersonationScope@shared@@QEAA@XZ; shared::SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x1801eaca0  lea     rax, [rbp+57h+lpsz]
0x1801eaca4  cmp     [rbp+57h+var_48], 7
0x1801eaca9  cmova   rax, [rbp+57h+lpsz]
0x1801eacae  mov     [rbp+57h+TokenHandle], rax
0x1801eacb2  lea     r8, [rbp+57h+TokenHandle]
0x1801eacb6  lea     rdx, aTextCocreatedO; "{\"text\":\"CoCreated object from CLSID"...
0x1801eacbd  call    ??$Log@PEBG@@YAXW4CDPLogLevel@@PEBD$$QEAPEBG@Z; Log<ushort const *>(CDPLogLevel,char const *,ushort const * &&)
0x1801eacc2  nop
0x1801eacc3  lea     rcx, [rbp+57h+lpsz]
0x1801eacc7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801eaccc  mov     rcx, [rbp+57h+var_30]
0x1801eacd0  xor     rcx, rsp; StackCookie
0x1801eacd3  call    __security_check_cookie
0x1801eacd8  add     rsp, 0E0h
0x1801eacdf  pop     r14
0x1801eace1  pop     rdi
0x1801eace2  pop     rsi
0x1801eace3  pop     rbx
0x1801eace4  pop     rbp
0x1801eace5  retn
```
