# TenantRestrictionsHelpers::GetJsonArray(ushort const *)

- ea: `0x18000e4b0`
- end: `0x18000e5d7`
- name: `?GetJsonArray@TenantRestrictionsHelpers@@YA?AV?$com_ptr_t@UIJsonArray@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@PEBG@Z`
- size: `295`
- prototype: `__int64 *__fastcall(__int64 *, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e668`
- `0x18000f7cc`

## callees

- `0x180001a50`
- `0x18000c41c`
- `0x18000d0b4`
- `0x18000dcdc`
- `0x18000e068`
- `0x18000e4b0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000e527`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000e527`

## string_xrefs

- `0x18000e507`: `Windows.Data.Json.JsonArray`
- `0x18000e538`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`
- `0x18000e59c`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`

## pseudocode

```c
__int64 *__fastcall TenantRestrictionsHelpers::GetJsonArray(__int64 *a1, __int64 a2)
{
  int ActivationFactory; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, __int64 *); // rsi
  __int64 v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  __int64 v10; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v11[2]; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v13; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v11[1] = a1;
  v11[0] = a2;
  v10 = 0;
  *a1 = 0;
  v13 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonArray",
    0x1Cu,
    0x1Bu);
  ActivationFactory = RoGetActivationFactory(v13, &GUID_db1434a9_e164_499f_93e2_8a8f49bb90ba, &v10);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CE,
      (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)(unsigned int)ActivationFactory,
      1);
  v4 = v10;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v10 + 48LL);
  v6 = *a1;
  *a1 = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v11);
  v8 = v5(v4, *(_QWORD *)(v7 + 24), a1);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1D2,
      (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
      (const char *)(unsigned int)v8,
      1);
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(&v10);
  return a1;
}

```

## disassembly

```asm
0x18000e4b0  mov     [rsp-18h+arg_10], rbx
0x18000e4b5  push    rbp
0x18000e4b6  push    rsi
0x18000e4b7  push    rdi
0x18000e4b8  mov     rbp, rsp
0x18000e4bb  sub     rsp, 70h
0x18000e4bf  mov     rax, cs:__security_cookie
0x18000e4c6  xor     rax, rsp
0x18000e4c9  mov     [rbp+var_10], rax
0x18000e4cd  mov     rbx, rcx
0x18000e4d0  mov     [rbp+var_38], rcx
0x18000e4d4  mov     [rbp+var_40], rdx
0x18000e4d8  mov     [rbp+var_50], 0
0x18000e4df  mov     [rbp+var_48], 0
0x18000e4e7  mov     qword ptr [rcx], 0
0x18000e4ee  mov     [rbp+var_50], 1
0x18000e4f5  mov     [rbp+var_18], 0
0x18000e4fd  mov     r9d, 1Bh; unsigned int
0x18000e503  lea     r8d, [r9+1]; unsigned int
0x18000e507  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x18000e50e  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18000e512  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000e517  nop
0x18000e518  lea     r8, [rbp+var_48]
0x18000e51c  lea     rdx, _GUID_db1434a9_e164_499f_93e2_8a8f49bb90ba
0x18000e523  mov     rcx, [rbp+var_18]
0x18000e527  call    cs:__imp_RoGetActivationFactory
0x18000e52d  mov     rcx, [rbp+18h]; this
0x18000e531  test    eax, eax
0x18000e533  jns     short loc_18000E54A
0x18000e535  mov     r9d, eax; char *
0x18000e538  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e53f  mov     edx, 1CEh; void *
0x18000e544  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e54a  mov     rdi, [rbp+var_48]
0x18000e54e  mov     rax, [rdi]
0x18000e551  mov     rsi, [rax+30h]
0x18000e555  mov     rcx, [rbx]
0x18000e558  mov     qword ptr [rbx], 0
0x18000e55f  test    rcx, rcx
0x18000e562  jz      short loc_18000E571
0x18000e564  mov     rax, [rcx]
0x18000e567  mov     rax, [rax+10h]
0x18000e56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e570  nop
0x18000e571  lea     rdx, [rbp+var_40]
0x18000e575  lea     rcx, [rbp+hstringHeader]
0x18000e579  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000e57e  nop
0x18000e57f  mov     r8, rbx
0x18000e582  mov     rdx, [rax+18h]
0x18000e586  mov     rcx, rdi
0x18000e589  mov     rax, rsi
0x18000e58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e591  mov     rcx, [rbp+18h]; this
0x18000e595  test    eax, eax
0x18000e597  jns     short loc_18000E5AE
0x18000e599  mov     r9d, eax; char *
0x18000e59c  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000e5a3  mov     edx, 1D2h; void *
0x18000e5a8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e5ae  lea     rcx, [rbp+var_48]
0x18000e5b2  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x18000e5b7  mov     rax, rbx
0x18000e5ba  mov     rcx, [rbp+var_10]
0x18000e5be  xor     rcx, rsp; StackCookie
0x18000e5c1  call    __security_check_cookie
0x18000e5c6  mov     rbx, [rsp+70h+arg_10]
0x18000e5ce  add     rsp, 70h
0x18000e5d2  pop     rdi
0x18000e5d3  pop     rsi
0x18000e5d4  pop     rbp
0x18000e5d5  retn
```
