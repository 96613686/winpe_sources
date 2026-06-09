# FlightIdUtils::RegisterFlightId(ushort const *,ushort const *)

- ea: `0x180083ae4`
- end: `0x180083c19`
- name: `?RegisterFlightId@FlightIdUtils@@YAJPEBG0@Z`
- size: `309`
- prototype: `__int64 __fastcall(FlightIdUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180083a40`

## callees

- `0x18000949c`
- `0x1800107b0`
- `0x180083ae4`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180083b22`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180083b22`

## string_xrefs

- `0x180083b35`: `onecore\base\flighting\common\inc\FlightIdUtility.h`
- `0x180083b93`: `onecore\base\flighting\common\inc\FlightIdUtility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FlightIdUtils::RegisterFlightId(
        FlightIdUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HRESULT Instance; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  const unsigned __int16 *v12; // [rsp+48h] [rbp+18h] BYREF
  __int64 *v13; // [rsp+50h] [rbp+20h] BYREF

  v12 = a2;
  v13 = 0;
  Instance = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, (LPVOID *)&v13);
  v5 = Instance;
  if ( Instance >= 0 )
  {
    v12 = 0;
    v6 = *v13;
    v12 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, FlightIdUtils *, _QWORD))(v6 + 88))(v13, L"FT", this, 0);
    v5 = v7;
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(const unsigned __int16 *, const wchar_t *, const wchar_t *))(*(_QWORD *)v12 + 80LL))(
             v12,
             L"Triggered",
             L"0");
      v5 = v7;
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v12 + 88LL))(v12);
        v5 = v7;
        if ( v7 >= 0 )
        {
          wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v12);
          v5 = 0;
          goto LABEL_11;
        }
        v8 = 286;
      }
      else
      {
        v8 = 284;
      }
    }
    else
    {
      v8 = 282;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
      (const char *)(unsigned int)v7,
      (int)&v12);
    wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v12);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
      (const char *)(unsigned int)Instance,
      v10);
  }
LABEL_11:
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v13);
  return v5;
}

```

## disassembly

```asm
0x180083ae4  mov     r11, rsp
0x180083ae7  mov     [r11+8], rbx
0x180083aeb  mov     [r11+20h], rdi
0x180083aef  mov     [r11+10h], rdx
0x180083af3  push    rbp
0x180083af4  mov     rbp, rsp
0x180083af7  sub     rsp, 30h
0x180083afb  mov     rdi, rcx
0x180083afe  mov     [rbp+arg_10], 0
0x180083b06  lea     rax, [rbp+arg_10]
0x180083b0a  mov     [r11-18h], rax
0x180083b0e  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x180083b15  xor     edx, edx; pUnkOuter
0x180083b17  lea     r8d, [rdx+1]; dwClsContext
0x180083b1b  lea     rcx, CLSID_FlightClientAPI; rclsid
0x180083b22  call    cs:__imp_CoCreateInstance
0x180083b28  mov     ebx, eax
0x180083b2a  test    eax, eax
0x180083b2c  jns     short loc_180083B4B
0x180083b2e  mov     rcx, [rbp+8]; this
0x180083b32  mov     r9d, eax; char *
0x180083b35  lea     r8, aOnecoreBaseFli_46; "onecore\\base\\flighting\\common\\inc\\"...
0x180083b3c  mov     edx, 117h; void *
0x180083b41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083b46  jmp     loc_180083BFE
0x180083b4b  mov     [rbp+arg_8], 0
0x180083b53  mov     rcx, [rbp+arg_10]
0x180083b57  mov     rax, [rcx]
0x180083b5a  mov     [rbp+arg_8], 0
0x180083b62  lea     rdx, [rbp+arg_8]
0x180083b66  mov     qword ptr [rsp+30h+var_10], rdx; int
0x180083b6b  xor     r9d, r9d
0x180083b6e  mov     r8, rdi
0x180083b71  lea     rdx, aFt; "FT"
0x180083b78  mov     rax, [rax+58h]
0x180083b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b81  mov     ebx, eax
0x180083b83  test    eax, eax
0x180083b85  jns     short loc_180083BAB
0x180083b87  mov     edx, 11Ah; void *
0x180083b8c  mov     rcx, [rbp+8]; this
0x180083b90  mov     r9d, eax; char *
0x180083b93  lea     r8, aOnecoreBaseFli_46; "onecore\\base\\flighting\\common\\inc\\"...
0x180083b9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083b9f  nop
0x180083ba0  lea     rcx, [rbp+arg_8]
0x180083ba4  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180083ba9  jmp     short loc_180083BFE
0x180083bab  mov     rcx, [rbp+arg_8]
0x180083baf  mov     rax, [rcx]
0x180083bb2  lea     r8, a0; "0"
0x180083bb9  lea     rdx, aTriggered; "Triggered"
0x180083bc0  mov     rax, [rax+50h]
0x180083bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083bc9  mov     ebx, eax
0x180083bcb  test    eax, eax
0x180083bcd  jns     short loc_180083BD6
0x180083bcf  mov     edx, 11Ch
0x180083bd4  jmp     short loc_180083B8C
0x180083bd6  mov     rcx, [rbp+arg_8]
0x180083bda  mov     rax, [rcx]
0x180083bdd  mov     rax, [rax+58h]
0x180083be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083be6  mov     ebx, eax
0x180083be8  test    eax, eax
0x180083bea  jns     short loc_180083BF3
0x180083bec  mov     edx, 11Eh
0x180083bf1  jmp     short loc_180083B8C
0x180083bf3  lea     rcx, [rbp+arg_8]
0x180083bf7  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180083bfc  xor     ebx, ebx
0x180083bfe  lea     rcx, [rbp+arg_10]
0x180083c02  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180083c07  mov     eax, ebx
0x180083c09  mov     rbx, [rsp+30h+arg_0]
0x180083c0e  mov     rdi, [rsp+30h+arg_18]
0x180083c13  add     rsp, 30h
0x180083c17  pop     rbp
0x180083c18  retn
```
