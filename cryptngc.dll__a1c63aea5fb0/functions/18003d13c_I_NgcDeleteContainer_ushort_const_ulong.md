# I_NgcDeleteContainer(ushort const *,ulong)

- ea: `0x18003d13c`
- end: `0x18003d3f0`
- name: `?I_NgcDeleteContainer@@YAJPEBGK@Z`
- size: `692`
- prototype: `__int64 __fastcall(LPCWSTR StringSid, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800350a8`

## callees

- `0x18000102c`
- `0x1800046e0`
- `0x180006538`
- `0x18000edb0`
- `0x180016818`
- `0x1800171fc`
- `0x180017df0`
- `0x180018790`
- `0x18002494c`
- `0x180025010`
- `0x18002b0f0`
- `0x18002e02c`
- `0x180032fcc`
- `0x180036b04`
- `0x18003d13c`
- `0x18003d5c8`
- `0x18004120c`
- `0x180046ce0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d28e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d28e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003d2ad`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003d2ad`

## string_xrefs

- `0x18003d1fb`: `onecore\ds\security\ngc\ctnrsvc\client\provisioning\ngcprovisioninghandlerclient.cpp`
- `0x18003d2bb`: `onecore\ds\security\ngc\ctnrsvc\client\provisioning\ngcprovisioninghandlerclient.cpp`
- `0x18003d2fb`: `onecore\ds\security\ngc\ctnrsvc\client\provisioning\ngcprovisioninghandlerclient.cpp`
- `0x18003d342`: `onecore\ds\security\ngc\ctnrsvc\client\provisioning\ngcprovisioninghandlerclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall I_NgcDeleteContainer(LPCWSTR StringSid, unsigned int a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  DWORD v6; // r9d
  __int64 v7; // rax
  int v8; // esi
  __int64 v9; // rdx
  volatile signed __int32 *v10; // rdi
  enum NgcUserAccountType *v12; // r8
  const char *v13; // r9
  int UserAccountType; // eax
  int v15; // eax
  volatile signed __int32 *v16; // rdi
  int v17; // [rsp+20h] [rbp-49h]
  HLOCAL hMem; // [rsp+40h] [rbp-29h] BYREF
  int v19; // [rsp+48h] [rbp-21h]
  struct _GUID v20; // [rsp+50h] [rbp-19h] BYREF
  NgcUtils::RpcClient *v21; // [rsp+60h] [rbp-9h] BYREF
  volatile signed __int32 *v22; // [rsp+68h] [rbp-1h]
  WCHAR StringSecurityDescriptor[16]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *(_QWORD *)&v20.Data1 = operator new(0x60u);
  std::wstring::wstring(StringSecurityDescriptor, L"D:(A;;GR;;;LS)");
  v7 = NgcUtils::RpcClient::RpcClient(
         *(__int64 *)&v20.Data1,
         v4,
         v5,
         v6,
         3,
         StringSecurityDescriptor,
         qword_180057D18,
         (__int64)&qword_18004ECC0);
  std::shared_ptr<NgcUtils::RpcClient>::shared_ptr<NgcUtils::RpcClient>(&v21, v7);
  v19 = 0;
  std::wstring::~wstring(StringSecurityDescriptor);
  v8 = NgcUtils::RpcClient::Bind(v21);
  if ( v8 < 0 )
  {
    v9 = 232;
    goto LABEL_3;
  }
  v8 = I_c_NgcRpcDeleteContainer(&v21, StringSid, a2);
  if ( v8 < 0 )
  {
    v9 = 237;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\client\\provisioning\\ngcprovisioninghandlerclient.cpp",
      (const char *)(unsigned int)v8,
      v17);
    v10 = v22;
    if ( v22 && _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
    return (unsigned int)v8;
  }
  hMem = 0;
  if ( !ConvertStringSidToSidW(StringSid, &hMem) )
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0xF3,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\client\\provisioning\\ngcprovisioninghandlerclient.cpp",
      v13);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
    goto LABEL_20;
  }
  v20.Data1 = 0;
  UserAccountType = NgcUtils::GetUserAccountType((NgcUtils *)hMem, &v20, v12);
  if ( UserAccountType < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\client\\provisioning\\ngcprovisioninghandlerclient.cpp",
      (const char *)(unsigned int)UserAccountType,
      v17);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
    goto LABEL_20;
  }
  if ( v20.Data1 == 2 )
  {
    v20 = CLSID_CWLIDCredentialProvider;
    v15 = NgcMgmtSetLastCredProv(&v20, StringSid);
    if ( v15 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x105,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\client\\provisioning\\ngcprovisioninghandlerclient.cpp",
        (const char *)(unsigned int)v15,
        v17);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
      goto LABEL_20;
    }
    if ( (unsigned int)dword_18006E000 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18006E000,
        &byte_1800614EF,
        0);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
LABEL_20:
  v16 = v22;
  if ( v22 )
  {
    if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003d13c  mov     [rsp-8+arg_10], rbx
0x18003d141  push    rbp
0x18003d142  push    rsi
0x18003d143  push    rdi
0x18003d144  push    r14
0x18003d146  push    r15
0x18003d148  lea     rbp, [rsp-37h]
0x18003d14d  sub     rsp, 0A0h
0x18003d154  mov     rax, cs:__security_cookie
0x18003d15b  xor     rax, rsp
0x18003d15e  mov     [rbp+57h+var_30], rax
0x18003d162  mov     r15d, edx
0x18003d165  mov     r14, rcx
0x18003d168  mov     [rbp+57h+var_78], 0
0x18003d16f  mov     ecx, 60h ; '`'; Size
0x18003d174  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d179  mov     rbx, rax
0x18003d17c  mov     qword ptr [rbp+57h+var_70.Data1], rax
0x18003d180  lea     rdx, aDAGrLs_0; "D:(A;;GR;;;LS)"
0x18003d187  lea     rcx, [rbp+57h+var_50]
0x18003d18b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003d190  nop
0x18003d191  mov     edi, 1
0x18003d196  mov     [rbp+57h+var_78], edi
0x18003d199  lea     rax, qword_18004ECC0
0x18003d1a0  mov     [rsp+0C0h+var_88], rax; __int64
0x18003d1a5  lea     rax, qword_180057D18
0x18003d1ac  mov     [rsp+0C0h+pSid], rax; pSid
0x18003d1b1  lea     rax, [rbp+57h+var_50]
0x18003d1b5  mov     [rsp+0C0h+StringSecurityDescriptor], rax; StringSecurityDescriptor
0x18003d1ba  mov     [rsp+0C0h+var_A0], 3; int
0x18003d1c2  mov     rcx, rbx; int
0x18003d1c5  call    ??0RpcClient@NgcUtils@@QEAA@KKKKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_SID@@QEAX@Z; NgcUtils::RpcClient::RpcClient(ulong,ulong,ulong,ulong,std::wstring const &,_SID const *,void * const)
0x18003d1ca  nop
0x18003d1cb  mov     rdx, rax
0x18003d1ce  lea     rcx, [rbp+57h+var_60]
0x18003d1d2  call    ??$?0VRpcClient@NgcUtils@@$0A@@?$shared_ptr@VRpcClient@NgcUtils@@@std@@QEAA@PEAVRpcClient@NgcUtils@@@Z; std::shared_ptr<NgcUtils::RpcClient>::shared_ptr<NgcUtils::RpcClient>(NgcUtils::RpcClient *)
0x18003d1d7  nop
0x18003d1d8  and     edi, 0FFFFFFFEh
0x18003d1db  mov     [rbp+57h+var_78], edi
0x18003d1de  lea     rcx, [rbp+57h+var_50]
0x18003d1e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d1e7  mov     rcx, [rbp+57h+var_60]; this
0x18003d1eb  call    ?Bind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Bind(void)
0x18003d1f0  mov     esi, eax
0x18003d1f2  test    eax, eax
0x18003d1f4  jns     short loc_18003D255
0x18003d1f6  mov     edx, 0E8h; void *
0x18003d1fb  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\ctnrsvc\\cl"...
0x18003d202  mov     r9d, esi; char *
0x18003d205  mov     rcx, [rbp+5Fh]; this
0x18003d209  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d20e  nop
0x18003d20f  mov     rdi, [rbp+57h+var_58]
0x18003d213  test    rdi, rdi
0x18003d216  jz      short loc_18003D24E
0x18003d218  or      ebx, 0FFFFFFFFh
0x18003d21b  mov     eax, ebx
0x18003d21d  lock xadd [rdi+8], eax
0x18003d222  add     eax, ebx
0x18003d224  jnz     short loc_18003D24E
0x18003d226  mov     rax, [rdi]
0x18003d229  mov     rcx, rdi
0x18003d22c  mov     rax, [rax]
0x18003d22f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d234  mov     eax, ebx
0x18003d236  lock xadd [rdi+0Ch], eax
0x18003d23b  add     eax, ebx
0x18003d23d  jnz     short loc_18003D24E
0x18003d23f  mov     rax, [rdi]
0x18003d242  mov     rcx, rdi
0x18003d245  mov     rax, [rax+8]
0x18003d249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d24e  mov     eax, esi
0x18003d250  jmp     loc_18003D3CD
0x18003d255  mov     r8d, r15d
0x18003d258  mov     rdx, r14
0x18003d25b  lea     rcx, [rbp+57h+var_60]
0x18003d25f  call    ?I_c_NgcRpcDeleteContainer@@YAJAEBV?$shared_ptr@VRpcClient@NgcUtils@@@std@@PEBGK@Z; I_c_NgcRpcDeleteContainer(std::shared_ptr<NgcUtils::RpcClient> const &,ushort const *,ulong)
0x18003d264  mov     esi, eax
0x18003d266  test    eax, eax
0x18003d268  jns     short loc_18003D271
0x18003d26a  mov     edx, 0EDh
0x18003d26f  jmp     short loc_18003D1FB
0x18003d271  mov     [rbp+57h+hMem], 0
0x18003d279  mov     rbx, [rbp+57h+hMem]
0x18003d27d  test    rbx, rbx
0x18003d280  jz      short loc_18003D29E
0x18003d282  lea     rcx, [rbp+57h+var_70]; this
0x18003d286  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003d28b  mov     rcx, rbx; hMem
0x18003d28e  call    cs:__imp_LocalFree
0x18003d294  lea     rcx, [rbp+57h+var_70]; this
0x18003d298  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003d29d  nop
0x18003d29e  mov     [rbp+57h+hMem], 0
0x18003d2a6  lea     rdx, [rbp+57h+hMem]; Sid
0x18003d2aa  mov     rcx, r14; StringSid
0x18003d2ad  call    cs:__imp_ConvertStringSidToSidW
0x18003d2b3  mov     rcx, [rbp+5Fh]; this
0x18003d2b7  test    eax, eax
0x18003d2b9  jnz     short loc_18003D2DC
0x18003d2bb  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\ctnrsvc\\cl"...
0x18003d2c2  mov     edx, 0F3h; void *
0x18003d2c7  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18003d2cc  nop
0x18003d2cd  lea     rcx, [rbp+57h+hMem]; void *
0x18003d2d1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003d2d6  nop
0x18003d2d7  jmp     loc_18003D38C
0x18003d2dc  mov     [rbp+57h+var_70.Data1], 0
0x18003d2e3  lea     rdx, [rbp+57h+var_70]; void *
0x18003d2e7  mov     rcx, [rbp+57h+hMem]; this
0x18003d2eb  call    ?GetUserAccountType@NgcUtils@@YAJPEAXPEAW4NgcUserAccountType@@@Z; NgcUtils::GetUserAccountType(void *,NgcUserAccountType *)
0x18003d2f0  mov     rcx, [rbp+5Fh]; this
0x18003d2f4  test    eax, eax
0x18003d2f6  jns     short loc_18003D319
0x18003d2f8  mov     r9d, eax; char *
0x18003d2fb  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\ctnrsvc\\cl"...
0x18003d302  mov     edx, 0FCh; void *
0x18003d307  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d30c  nop
0x18003d30d  lea     rcx, [rbp+57h+hMem]; void *
0x18003d311  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003d316  nop
0x18003d317  jmp     short loc_18003D38C
0x18003d319  cmp     [rbp+57h+var_70.Data1], 2
0x18003d31d  jnz     short loc_18003D382
0x18003d31f  movups  xmm0, xmmword ptr cs:CLSID_CWLIDCredentialProvider.Data1
0x18003d326  movdqu  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x18003d32b  mov     rdx, r14; unsigned __int16 *
0x18003d32e  lea     rcx, [rbp+57h+var_70]; struct _GUID
0x18003d332  call    ?NgcMgmtSetLastCredProv@@YAJU_GUID@@PEBG@Z; NgcMgmtSetLastCredProv(_GUID,ushort const *)
0x18003d337  mov     rcx, [rbp+5Fh]; this
0x18003d33b  test    eax, eax
0x18003d33d  jns     short loc_18003D360
0x18003d33f  mov     r9d, eax; char *
0x18003d342  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\ngc\\ctnrsvc\\cl"...
0x18003d349  mov     edx, 105h; void *
0x18003d34e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003d353  nop
0x18003d354  lea     rcx, [rbp+57h+hMem]; void *
0x18003d358  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003d35d  nop
0x18003d35e  jmp     short loc_18003D38C
0x18003d360  mov     eax, cs:dword_18006E000
0x18003d366  cmp     eax, 4
0x18003d369  jbe     short loc_18003D382
0x18003d36b  xor     r8d, r8d
0x18003d36e  lea     rdx, byte_1800614EF
0x18003d375  lea     rcx, dword_18006E000
0x18003d37c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003d381  nop
0x18003d382  lea     rcx, [rbp+57h+hMem]; void *
0x18003d386  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003d38b  nop
0x18003d38c  mov     rdi, [rbp+57h+var_58]
0x18003d390  test    rdi, rdi
0x18003d393  jz      short loc_18003D3CB
0x18003d395  or      ebx, 0FFFFFFFFh
0x18003d398  mov     eax, ebx
0x18003d39a  lock xadd [rdi+8], eax
0x18003d39f  add     eax, ebx
0x18003d3a1  jnz     short loc_18003D3CB
0x18003d3a3  mov     rax, [rdi]
0x18003d3a6  mov     rcx, rdi
0x18003d3a9  mov     rax, [rax]
0x18003d3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3b1  mov     eax, ebx
0x18003d3b3  lock xadd [rdi+0Ch], eax
0x18003d3b8  add     eax, ebx
0x18003d3ba  jnz     short loc_18003D3CB
0x18003d3bc  mov     rax, [rdi]
0x18003d3bf  mov     rcx, rdi
0x18003d3c2  mov     rax, [rax+8]
0x18003d3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3cb  xor     eax, eax
0x18003d3cd  mov     rcx, [rbp+57h+var_30]
0x18003d3d1  xor     rcx, rsp; StackCookie
0x18003d3d4  call    __security_check_cookie
0x18003d3d9  mov     rbx, [rsp+0C0h+arg_10]
0x18003d3e1  add     rsp, 0A0h
0x18003d3e8  pop     r15
0x18003d3ea  pop     r14
0x18003d3ec  pop     rdi
0x18003d3ed  pop     rsi
0x18003d3ee  pop     rbp
0x18003d3ef  retn
```
