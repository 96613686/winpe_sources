# Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)

- ea: `0x180128e28`
- end: `0x180129134`
- name: `?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `780`
- prototype: ``
- caller_count: `10`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f9bb4`
- `0x1801266fc`
- `0x1801293f4`
- `0x180129dc8`
- `0x18012b354`
- `0x18012d6b0`
- `0x1801306f0`
- `0x180131d60`
- `0x180137840`
- `0x18013826c`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800ee898`
- `0x1800f980c`
- `0x1800f9a0c`
- `0x180127644`
- `0x1801282b0`
- `0x180128e28`
- `0x180191010`

## import_xrefs

- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180128e71`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180128e71`

## string_xrefs

- `0x180128eae`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180128f43`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180128fb3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012905d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(_QWORD *a1, _QWORD *a2)
{
  __int64 DatabaseManagerInstance; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // edi
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v8; // rax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v13; // rax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v14; // rax
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, __int64); // rdi
  __int64 v17; // rax
  int v18; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  std::_Ref_count_base *v22; // rcx
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v23; // rax
  std::_Ref_count_base *v24[2]; // [rsp+20h] [rbp-20h] BYREF
  int *v25; // [rsp+30h] [rbp-10h]
  char v26; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int v28; // [rsp+70h] [rbp+30h] BYREF
  __int64 v29; // [rsp+80h] [rbp+40h] BYREF
  __int64 v30; // [rsp+88h] [rbp+48h] BYREF

  v28 = 0;
  v25 = &v28;
  v26 = 1;
  if ( !*a1 || !*(_QWORD *)*a1 )
  {
    v30 = 0;
    v29 = 0;
    DatabaseManagerInstance = GetDatabaseManagerInstance();
    v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
    v6 = v5(DatabaseManagerInstance, 222306401, &v30);
    v7 = v6;
    v28 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v6,
        (int)v24[0]);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
      if ( (int)(v28 + 0x80000000) >= 0 && v28 != -2147023728 )
      {
        v8 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v8, L"GetEnrollmentId failed", v28);
      }
      return v7;
    }
    v10 = v30;
    v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 24LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v29);
    v12 = v11(v10, &v29);
    v7 = v12;
    v28 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v12,
        (int)v24[0]);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
      if ( (int)(v28 + 0x80000000) >= 0 && v28 != -2147023728 )
      {
        v13 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v13, L"GetEnrollmentId failed", v28);
      }
      return v7;
    }
    if ( v12 == 1 )
    {
      v28 = -2147023728;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)0x80070490LL,
        (int)v24[0]);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
      if ( (int)(v28 + 0x80000000) >= 0 && v28 != -2147023728 )
      {
        v14 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v14, L"GetEnrollmentId failed", v28);
      }
      return 2147943568LL;
    }
    v15 = v29;
    v16 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 32LL);
    *(_OWORD *)v24 = 0;
    std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::operator=(
      a1,
      v24);
    if ( v24[1] )
      std::_Ref_count_base::_Decref(v24[1]);
    v17 = wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(a1);
    v18 = v16(v15, v17);
    v7 = v18;
    v28 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v18,
        (int)v24[0]);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
      if ( (int)(v28 + 0x80000000) >= 0 && v28 != -2147023728 )
      {
        v19 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v19, L"GetEnrollmentId failed", v28);
      }
      return v7;
    }
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
  }
  v20 = a1[1];
  if ( v20 )
    _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
  v21 = a1[1];
  *a2 = *a1;
  v22 = (std::_Ref_count_base *)a2[1];
  a2[1] = v21;
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  if ( (int)(v28 + 0x80000000) >= 0 && v28 != -2147023728 )
  {
    v23 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v23, L"GetEnrollmentId failed", v28);
  }
  return 0;
}

```

## disassembly

```asm
0x180128e28  push    rbp
0x180128e2a  push    rbx
0x180128e2b  push    rsi
0x180128e2c  push    rdi
0x180128e2d  push    r14
0x180128e2f  mov     rbp, rsp
0x180128e32  sub     rsp, 40h
0x180128e36  mov     r14, rdx
0x180128e39  mov     rsi, rcx
0x180128e3c  mov     [rbp+arg_0], 0
0x180128e43  lea     rax, [rbp+arg_0]
0x180128e47  mov     [rbp+var_10], rax
0x180128e4b  mov     [rbp+var_8], 1
0x180128e4f  mov     rax, [rcx]
0x180128e52  test    rax, rax
0x180128e55  jz      short loc_180128E61
0x180128e57  cmp     qword ptr [rax], 0
0x180128e5b  jnz     loc_1801290CC
0x180128e61  mov     [rbp+arg_18], 0
0x180128e69  mov     [rbp+arg_10], 0
0x180128e71  call    cs:__imp_GetDatabaseManagerInstance
0x180128e77  mov     rdi, rax
0x180128e7a  mov     rcx, [rax]
0x180128e7d  mov     rbx, [rcx+20h]
0x180128e81  lea     rcx, [rbp+arg_18]
0x180128e85  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180128e8a  lea     r8, [rbp+arg_18]
0x180128e8e  mov     edx, 0D402061h
0x180128e93  mov     rcx, rdi
0x180128e96  mov     rax, rbx
0x180128e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128e9e  mov     edi, eax
0x180128ea0  mov     [rbp+arg_0], eax
0x180128ea3  test    eax, eax
0x180128ea5  jns     short loc_180128F0C
0x180128ea7  mov     rcx, [rbp+28h]; this
0x180128eab  mov     r9d, eax; char *
0x180128eae  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180128eb5  mov     edx, 59h ; 'Y'; void *
0x180128eba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180128ebf  nop
0x180128ec0  lea     rcx, [rbp+arg_10]
0x180128ec4  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180128ec9  nop
0x180128eca  lea     rcx, [rbp+arg_18]
0x180128ece  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180128ed3  nop
0x180128ed4  mov     edx, [rbp+arg_0]
0x180128ed7  mov     ecx, 80000000h
0x180128edc  lea     eax, [rdx+rcx]
0x180128edf  test    ecx, eax
0x180128ee1  jnz     short loc_180128F05
0x180128ee3  mov     ebx, 80070490h
0x180128ee8  cmp     edx, ebx
0x180128eea  jz      short loc_180128F05
0x180128eec  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180128ef1  mov     r8d, [rbp+arg_0]; int
0x180128ef5  lea     rdx, aGetenrollmenti; "GetEnrollmentId failed"
0x180128efc  mov     rcx, rax; this
0x180128eff  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180128f04  nop
0x180128f05  mov     eax, edi
0x180128f07  jmp     loc_180129129
0x180128f0c  mov     rdi, [rbp+arg_18]
0x180128f10  mov     rax, [rdi]
0x180128f13  mov     rbx, [rax+18h]
0x180128f17  lea     rcx, [rbp+arg_10]
0x180128f1b  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180128f20  lea     rdx, [rbp+arg_10]
0x180128f24  mov     rcx, rdi
0x180128f27  mov     rax, rbx
0x180128f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128f2f  mov     edi, eax
0x180128f31  mov     [rbp+arg_0], eax
0x180128f34  test    eax, eax
0x180128f36  jns     short loc_180128F9F
0x180128f38  test    eax, eax
0x180128f3a  jns     short loc_180128F55
0x180128f3c  mov     rcx, [rbp+28h]; this
0x180128f40  mov     r9d, eax; char *
0x180128f43  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180128f4a  mov     edx, 5Ch ; '\'; void *
0x180128f4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180128f54  nop
0x180128f55  lea     rcx, [rbp+arg_10]
0x180128f59  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180128f5e  nop
0x180128f5f  lea     rcx, [rbp+arg_18]
0x180128f63  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180128f68  nop
0x180128f69  mov     edx, [rbp+arg_0]
0x180128f6c  mov     ecx, 80000000h
0x180128f71  lea     eax, [rdx+rcx]
0x180128f74  test    ecx, eax
0x180128f76  jnz     short loc_180128F9A
0x180128f78  mov     ebx, 80070490h
0x180128f7d  cmp     edx, ebx
0x180128f7f  jz      short loc_180128F9A
0x180128f81  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180128f86  mov     r8d, [rbp+arg_0]; int
0x180128f8a  lea     rdx, aGetenrollmenti; "GetEnrollmentId failed"
0x180128f91  mov     rcx, rax; this
0x180128f94  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180128f99  nop
0x180128f9a  jmp     loc_180128F05
0x180128f9f  cmp     edi, 1
0x180128fa2  jnz     short loc_18012900A
0x180128fa4  mov     ebx, 80070490h
0x180128fa9  mov     [rbp+arg_0], ebx
0x180128fac  mov     rcx, [rbp+28h]; this
0x180128fb0  mov     r9d, ebx; char *
0x180128fb3  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180128fba  lea     edx, [rdi+5Ch]; void *
0x180128fbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180128fc2  nop
0x180128fc3  lea     rcx, [rbp+arg_10]
0x180128fc7  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180128fcc  nop
0x180128fcd  lea     rcx, [rbp+arg_18]
0x180128fd1  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180128fd6  nop
0x180128fd7  mov     edx, [rbp+arg_0]
0x180128fda  mov     ecx, 80000000h
0x180128fdf  lea     eax, [rdx+rcx]
0x180128fe2  test    ecx, eax
0x180128fe4  jnz     short loc_180129003
0x180128fe6  cmp     edx, ebx
0x180128fe8  jz      short loc_180129003
0x180128fea  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180128fef  mov     r8d, [rbp+arg_0]; int
0x180128ff3  lea     rdx, aGetenrollmenti; "GetEnrollmentId failed"
0x180128ffa  mov     rcx, rax; this
0x180128ffd  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180129002  nop
0x180129003  mov     eax, ebx
0x180129005  jmp     loc_180129129
0x18012900a  mov     rbx, [rbp+arg_10]
0x18012900e  mov     rax, [rbx]
0x180129011  mov     rdi, [rax+20h]
0x180129015  xorps   xmm0, xmm0
0x180129018  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18012901d  lea     rdx, [rbp+var_20]
0x180129021  mov     rcx, rsi
0x180129024  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x180129029  mov     rcx, [rbp+var_20+8]; this
0x18012902d  test    rcx, rcx
0x180129030  jz      short loc_180129037
0x180129032  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180129037  mov     rcx, rsi
0x18012903a  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEAPEAGXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x18012903f  mov     rdx, rax
0x180129042  mov     rcx, rbx
0x180129045  mov     rax, rdi
0x180129048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012904d  mov     edi, eax
0x18012904f  mov     [rbp+arg_0], eax
0x180129052  test    eax, eax
0x180129054  jns     short loc_1801290B9
0x180129056  mov     rcx, [rbp+28h]; this
0x18012905a  mov     r9d, eax; char *
0x18012905d  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180129064  mov     edx, 5Fh ; '_'; void *
0x180129069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012906e  nop
0x18012906f  lea     rcx, [rbp+arg_10]
0x180129073  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180129078  nop
0x180129079  lea     rcx, [rbp+arg_18]
0x18012907d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180129082  nop
0x180129083  mov     edx, [rbp+arg_0]
0x180129086  mov     ecx, 80000000h
0x18012908b  lea     eax, [rdx+rcx]
0x18012908e  test    ecx, eax
0x180129090  jnz     short loc_1801290B4
0x180129092  mov     ebx, 80070490h
0x180129097  cmp     edx, ebx
0x180129099  jz      short loc_1801290B4
0x18012909b  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x1801290a0  mov     r8d, [rbp+arg_0]; int
0x1801290a4  lea     rdx, aGetenrollmenti; "GetEnrollmentId failed"
0x1801290ab  mov     rcx, rax; this
0x1801290ae  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x1801290b3  nop
0x1801290b4  jmp     loc_180128F05
0x1801290b9  lea     rcx, [rbp+arg_10]
0x1801290bd  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801290c2  nop
0x1801290c3  lea     rcx, [rbp+arg_18]
0x1801290c7  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801290cc  mov     rax, [rsi+8]
0x1801290d0  test    rax, rax
0x1801290d3  jz      short loc_1801290D9
0x1801290d5  lock inc dword ptr [rax+8]
0x1801290d9  mov     rdx, [rsi+8]
0x1801290dd  mov     rax, [rsi]
0x1801290e0  mov     [r14], rax
0x1801290e3  mov     rcx, [r14+8]; this
0x1801290e7  mov     [r14+8], rdx
0x1801290eb  test    rcx, rcx
0x1801290ee  jz      short loc_1801290F6
0x1801290f0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801290f5  nop
0x1801290f6  mov     edx, [rbp+arg_0]
0x1801290f9  mov     ecx, 80000000h
0x1801290fe  lea     eax, [rdx+rcx]
0x180129101  test    ecx, eax
0x180129103  jnz     short loc_180129127
0x180129105  mov     ebx, 80070490h
0x18012910a  cmp     edx, ebx
0x18012910c  jz      short loc_180129127
0x18012910e  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180129113  mov     r8d, [rbp+arg_0]; int
0x180129117  lea     rdx, aGetenrollmenti; "GetEnrollmentId failed"
0x18012911e  mov     rcx, rax; this
0x180129121  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180129126  nop
0x180129127  xor     eax, eax
0x180129129  add     rsp, 40h
0x18012912d  pop     r14
0x18012912f  pop     rdi
0x180129130  pop     rsi
0x180129131  pop     rbx
0x180129132  pop     rbp
0x180129133  retn
```
