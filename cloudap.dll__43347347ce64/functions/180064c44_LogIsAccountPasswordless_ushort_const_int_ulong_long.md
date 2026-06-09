# LogIsAccountPasswordless(ushort const *,int,ulong,long)

- ea: `0x180064c44`
- end: `0x180064eff`
- name: `?LogIsAccountPasswordless@@YAXPEBGHKJ@Z`
- size: `699`
- prototype: `void __fastcall(LPCWSTR StringSid, int, unsigned int, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003a3bc`

## callees

- `0x180002d70`
- `0x1800331d0`
- `0x180033314`
- `0x180034b84`
- `0x180036940`
- `0x18003b944`
- `0x18003b964`
- `0x18003be3c`
- `0x18003be94`
- `0x18003bf28`
- `0x18003c73c`
- `0x18003fc88`
- `0x1800427c0`
- `0x1800429c0`
- `0x180042a28`
- `0x180064770`
- `0x180064c44`
- `0x180065054`
- `0x180066214`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180064d45`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180064d45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064d2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064d2a`

## string_xrefs

- `0x180064c90`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x180064ccf`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x180064cff`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LogIsAccountPasswordless(LPCWSTR StringSid, int a2, int a3, int a4)
{
  unsigned int DevicePasswordLessBuildVersion; // eax
  int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // edi
  __int64 v12; // r8
  int EnterprisePasswordLessPolicyValue; // r14d
  int v14; // ebx
  __int64 v15; // r8
  int v16; // [rsp+20h] [rbp-99h]
  bool v17; // [rsp+80h] [rbp-39h] BYREF
  bool v18; // [rsp+81h] [rbp-38h] BYREF
  unsigned int v19; // [rsp+84h] [rbp-35h] BYREF
  int v20; // [rsp+88h] [rbp-31h] BYREF
  unsigned int v21; // [rsp+8Ch] [rbp-2Dh] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-29h] BYREF
  int v23; // [rsp+98h] [rbp-21h] BYREF
  unsigned int v24; // [rsp+9Ch] [rbp-1Dh] BYREF
  int v25; // [rsp+A0h] [rbp-19h] BYREF
  int v26; // [rsp+A4h] [rbp-15h] BYREF
  int PasswordLessPolicyValue; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v28; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v29; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v30; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v31[9]; // [rsp+C8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v20 = 0;
  DevicePasswordLessBuildVersion = QueryDevicePasswordLessBuildVersion((enum DevicePasswordLessBuildVersion *)&v20);
  wil::details::in1diag3::Log_IfFailedWithExpected(
    retaddr,
    (void *)0x2A4,
    (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
    (const char *)DevicePasswordLessBuildVersion,
    1,
    2);
  v19 = 0;
  v9 = QueryDevicePasswordLessData(1, &v19);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = v19;
    v10 = 0;
  }
  else
  {
    v11 = 0;
    if ( v9 == -2147024894 )
      v10 = -2147024894;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BD,
        (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
        (const char *)(unsigned int)v9,
        v16);
  }
  wil::details::in1diag3::Log_IfFailedWithExpected(
    retaddr,
    (void *)0x2A9,
    (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
    (const char *)v10,
    1,
    2);
  hMem = 0;
  ConvertStringSidToSidW(StringSid, &hMem);
  v21 = 0;
  GetLsaUserAccountType(StringSid, (enum _LSA_USER_ACCOUNT_TYPE *)&v21);
  v19 = 0;
  IsAccountCloudPasswordLessInternal(hMem, v21, &v19);
  EnterprisePasswordLessPolicyValue = GetEnterprisePasswordLessPolicyValue();
  if ( __TSS0__1__GetInstance_PasswordlessPolicyProvider__SAAEAV2_XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                       + (unsigned int)tls_index)
                                                                                     + 4LL) )
  {
    Init_thread_header(&__TSS0__1__GetInstance_PasswordlessPolicyProvider__SAAEAV2_XZ_4HA);
    if ( __TSS0__1__GetInstance_PasswordlessPolicyProvider__SAAEAV2_XZ_4HA == -1 )
    {
      *(_QWORD *)&`PasswordlessPolicyProvider::GetInstance'::`2'::instance = &`PasswordlessPolicyProvider::StaticHandle::StaticHandle'::`2'::__hInner;
      TlgRegisterAggregateProviderEx(&`PasswordlessPolicyProvider::StaticHandle::StaticHandle'::`2'::__hInner);
      atexit(`PasswordlessPolicyProvider::GetInstance'::`2'::`dynamic atexit destructor for 'instance'');
      Init_thread_footer(&__TSS0__1__GetInstance_PasswordlessPolicyProvider__SAAEAV2_XZ_4HA);
    }
  }
  v14 = `PasswordlessPolicyProvider::GetInstance'::`2'::instance;
  if ( **(_DWORD **)&`PasswordlessPolicyProvider::GetInstance'::`2'::instance > 5u
    && (unsigned __int8)tlgKeywordOn(
                          *(_QWORD *)&`PasswordlessPolicyProvider::GetInstance'::`2'::instance,
                          0x800000000000LL,
                          v12) )
  {
    v23 = a4;
    v24 = v11;
    v25 = a3;
    v17 = v19 != 0;
    v18 = a2 != 0;
    v19 = v21;
    v26 = EnterprisePasswordLessPolicyValue;
    PasswordLessPolicyValue = GetPasswordLessPolicyValue();
    LODWORD(v28) = GetPlatformType();
    v29 = (__int64)StringSid;
    v30 = 16779264;
    v31[0] = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v14,
      (int)word_18009040A,
      v15,
      (__int64)v31,
      (__int64)&v30,
      (const WCHAR **)&v29,
      (__int64)&v28,
      (__int64)&PasswordLessPolicyValue,
      (__int64)&v26,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v17,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
}

```

## disassembly

```asm
0x180064c44  push    rbp
0x180064c46  push    rbx
0x180064c47  push    rsi
0x180064c48  push    rdi
0x180064c49  push    r12
0x180064c4b  push    r13
0x180064c4d  push    r14
0x180064c4f  push    r15
0x180064c51  lea     rbp, [rsp-1Fh]
0x180064c56  sub     rsp, 0D8h
0x180064c5d  mov     r15d, r9d
0x180064c60  mov     r12d, r8d
0x180064c63  mov     r13d, edx
0x180064c66  mov     rsi, rcx
0x180064c69  xor     r14d, r14d
0x180064c6c  mov     dword ptr [rbp+57h+var_88], r14d
0x180064c70  lea     rcx, [rbp+57h+var_88]; enum DevicePasswordLessBuildVersion *
0x180064c74  call    ?QueryDevicePasswordLessBuildVersion@@YAJPEAW4DevicePasswordLessBuildVersion@@@Z; QueryDevicePasswordLessBuildVersion(DevicePasswordLessBuildVersion *)
0x180064c79  mov     rcx, [rbp+5Fh]; this
0x180064c7d  mov     dword ptr [rsp+110h+var_E8], 80070002h; char
0x180064c85  mov     dword ptr [rsp+110h+var_F0], 1; int
0x180064c8d  mov     r9d, eax; char *
0x180064c90  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180064c97  mov     edx, 2A4h; void *
0x180064c9c  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180064ca1  mov     dword ptr [rbp+57h+var_90+4], r14d
0x180064ca5  lea     rdx, [rbp+57h+var_90+4]
0x180064ca9  lea     ecx, [r14+1]
0x180064cad  call    ?QueryDevicePasswordLessData@@YAJW4PasswordLessDataType@@PEAK@Z; QueryDevicePasswordLessData(PasswordLessDataType,ulong *)
0x180064cb2  mov     ebx, eax
0x180064cb4  test    eax, eax
0x180064cb6  jns     short loc_180064CE2
0x180064cb8  mov     edi, r14d
0x180064cbb  mov     ecx, 80070002h
0x180064cc0  cmp     eax, ecx
0x180064cc2  jnz     short loc_180064CC8
0x180064cc4  mov     ebx, ecx
0x180064cc6  jmp     short loc_180064CE8
0x180064cc8  mov     rcx, [rbp+5Fh]; this
0x180064ccc  mov     r9d, eax; char *
0x180064ccf  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180064cd6  mov     edx, 1BDh; void *
0x180064cdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064ce0  jmp     short loc_180064CE8
0x180064ce2  mov     edi, dword ptr [rbp+57h+var_90+4]
0x180064ce5  mov     ebx, r14d
0x180064ce8  mov     rcx, [rbp+5Fh]; this
0x180064cec  mov     dword ptr [rsp+110h+var_E8], 80070002h; char
0x180064cf4  mov     dword ptr [rsp+110h+var_F0], 1; int
0x180064cfc  mov     r9d, ebx; char *
0x180064cff  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x180064d06  mov     edx, 2A9h; void *
0x180064d0b  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180064d10  nop
0x180064d11  mov     [rbp+57h+hMem], r14
0x180064d15  mov     rbx, [rbp+57h+hMem]
0x180064d19  test    rbx, rbx
0x180064d1c  jz      short loc_180064D3A
0x180064d1e  lea     rcx, [rbp+57h+var_60]; this
0x180064d22  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180064d27  mov     rcx, rbx; hMem
0x180064d2a  call    cs:__imp_LocalFree
0x180064d30  lea     rcx, [rbp+57h+var_60]; this
0x180064d34  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180064d39  nop
0x180064d3a  mov     [rbp+57h+hMem], r14
0x180064d3e  lea     rdx, [rbp+57h+hMem]; Sid
0x180064d42  mov     rcx, rsi; StringSid
0x180064d45  call    cs:__imp_ConvertStringSidToSidW
0x180064d4b  mov     dword ptr [rbp+57h+var_88+4], r14d
0x180064d4f  lea     rdx, [rbp+57h+var_88+4]; enum _LSA_USER_ACCOUNT_TYPE *
0x180064d53  mov     rcx, rsi; StringSid
0x180064d56  call    ?GetLsaUserAccountType@@YAJPEBGPEAW4_LSA_USER_ACCOUNT_TYPE@@@Z; GetLsaUserAccountType(ushort const *,_LSA_USER_ACCOUNT_TYPE *)
0x180064d5b  mov     dword ptr [rbp+57h+var_90+4], r14d
0x180064d5f  lea     r8, [rbp+57h+var_90+4]
0x180064d63  mov     edx, dword ptr [rbp+57h+var_88+4]
0x180064d66  mov     rcx, [rbp+57h+hMem]
0x180064d6a  call    ?IsAccountCloudPasswordLessInternal@@YAJQEAXW4_LSA_USER_ACCOUNT_TYPE@@PEAH@Z; IsAccountCloudPasswordLessInternal(void * const,_LSA_USER_ACCOUNT_TYPE,int *)
0x180064d6f  call    GetEnterprisePasswordLessPolicyValue
0x180064d74  mov     r14d, eax
0x180064d77  mov     edx, cs:_tls_index
0x180064d7d  mov     rcx, gs:58h
0x180064d86  mov     eax, 4
0x180064d8b  mov     rcx, [rcx+rdx*8]
0x180064d8f  mov     ecx, [rax+rcx]
0x180064d92  cmp     cs:?$TSS0@?1??GetInstance@PasswordlessPolicyProvider@@SAAEAV2@XZ@4HA, ecx
0x180064d98  jg      loc_180064EB6
0x180064d9e  mov     rbx, cs:?instance@?1??GetInstance@PasswordlessPolicyProvider@@SAAEAV2@XZ@4V2@A; PasswordlessPolicyProvider `PasswordlessPolicyProvider::GetInstance(void)'::`2'::instance
0x180064da5  mov     eax, [rbx]
0x180064da7  cmp     eax, 5
0x180064daa  jbe     loc_180064E98
0x180064db0  mov     rdx, 800000000000h
0x180064dba  mov     rcx, rbx
0x180064dbd  call    _tlgKeywordOn
0x180064dc2  test    al, al
0x180064dc4  jz      loc_180064E98
0x180064dca  mov     dword ptr [rbp+57h+var_78], r15d
0x180064dce  mov     dword ptr [rbp+57h+var_78+4], edi
0x180064dd1  mov     dword ptr [rbp+57h+var_70], r12d
0x180064dd5  cmp     dword ptr [rbp+57h+var_90+4], 0
0x180064dd9  setnz   byte ptr [rbp+57h+var_90]
0x180064ddd  test    r13d, r13d
0x180064de0  setnz   byte ptr [rbp+57h+var_90+1]
0x180064de4  mov     eax, dword ptr [rbp+57h+var_88+4]
0x180064de7  mov     dword ptr [rbp+57h+var_90+4], eax
0x180064dea  mov     eax, dword ptr [rbp+57h+var_88]
0x180064ded  mov     dword ptr [rbp+57h+var_88], eax
0x180064df0  mov     dword ptr [rbp+57h+var_70+4], r14d
0x180064df4  call    GetPasswordLessPolicyValue
0x180064df9  mov     [rbp+57h+var_68], eax
0x180064dfc  call    GetPlatformType
0x180064e01  mov     dword ptr [rbp+57h+var_60], eax
0x180064e04  mov     [rbp+57h+var_58], rsi
0x180064e08  mov     [rbp+57h+var_50], 1000800h
0x180064e10  mov     [rbp+57h+var_48], 1
0x180064e18  lea     rax, [rbp+57h+var_78]
0x180064e1c  mov     [rsp+110h+var_98], rax; __int64
0x180064e21  lea     rax, [rbp+57h+var_78+4]
0x180064e25  mov     [rsp+110h+var_A0], rax; __int64
0x180064e2a  lea     rax, [rbp+57h+var_70]
0x180064e2e  mov     [rsp+110h+var_A8], rax; __int64
0x180064e33  lea     rax, [rbp+57h+var_90]
0x180064e37  mov     [rsp+110h+var_B0], rax; __int64
0x180064e3c  lea     rax, [rbp+57h+var_90+1]
0x180064e40  mov     [rsp+110h+var_B8], rax; __int64
0x180064e45  lea     rax, [rbp+57h+var_90+4]
0x180064e49  mov     [rsp+110h+var_C0], rax; __int64
0x180064e4e  lea     rax, [rbp+57h+var_88]
0x180064e52  mov     [rsp+110h+var_C8], rax; __int64
0x180064e57  lea     rax, [rbp+57h+var_70+4]
0x180064e5b  mov     [rsp+110h+var_D0], rax; __int64
0x180064e60  lea     rax, [rbp+57h+var_68]
0x180064e64  mov     [rsp+110h+var_D8], rax; __int64
0x180064e69  lea     rax, [rbp+57h+var_60]
0x180064e6d  mov     [rsp+110h+var_E0], rax; __int64
0x180064e72  lea     rax, [rbp+57h+var_58]
0x180064e76  mov     qword ptr [rsp+110h+var_E8], rax; __int64
0x180064e7b  lea     rax, [rbp+57h+var_50]
0x180064e7f  mov     [rsp+110h+var_F0], rax; __int64
0x180064e84  lea     r9, [rbp+57h+var_48]
0x180064e88  lea     rdx, word_18009040A
0x180064e8f  mov     rcx, rbx; int
0x180064e92  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U?$_tlgWrapperByVal@$00@@U4@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4444AEBU?$_tlgWrapperByVal@$00@@5444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180064e97  nop
0x180064e98  lea     rcx, [rbp+57h+hMem]
0x180064e9c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180064ea1  nop
0x180064ea2  add     rsp, 0D8h
0x180064ea9  pop     r15
0x180064eab  pop     r14
0x180064ead  pop     r13
0x180064eaf  pop     r12
0x180064eb1  pop     rdi
0x180064eb2  pop     rsi
0x180064eb3  pop     rbx
0x180064eb4  pop     rbp
0x180064eb5  retn
0x180064eb6  lea     rcx, ?$TSS0@?1??GetInstance@PasswordlessPolicyProvider@@SAAEAV2@XZ@4HA
0x180064ebd  call    _Init_thread_header
0x180064ec2  cmp     cs:?$TSS0@?1??GetInstance@PasswordlessPolicyProvider@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180064ec9  jnz     loc_180064D9E
0x180064ecf  lea     rcx, ?__hInner@?1???0StaticHandle@PasswordlessPolicyProvider@@QEAA@XZ@4U_tlgProvider_t@@A; CallbackContext
0x180064ed6  mov     cs:?instance@?1??GetInstance@PasswordlessPolicyProvider@@SAAEAV2@XZ@4V2@A, rcx; PasswordlessPolicyProvider `PasswordlessPolicyProvider::GetInstance(void)'::`2'::instance
0x180064edd  call    TlgRegisterAggregateProviderEx
0x180064ee2  lea     rcx, ??__Finstance@?1??GetInstance@PasswordlessPolicyProvider@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x180064ee9  call    atexit
0x180064eee  lea     rcx, ?$TSS0@?1??GetInstance@PasswordlessPolicyProvider@@SAAEAV2@XZ@4HA
0x180064ef5  call    _Init_thread_footer
0x180064efa  jmp     loc_180064D9E
```
