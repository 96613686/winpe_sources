# FlightIdUtils::UnregisterFlightId(ushort const *)

- ea: `0x18008556c`
- end: `0x180085600`
- name: `?UnregisterFlightId@FlightIdUtils@@YAJPEBG@Z`
- size: `148`
- prototype: `__int64 __fastcall(FlightIdUtils *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180083a40`

## callees

- `0x18000949c`
- `0x1800107b0`
- `0x18008556c`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008559f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008559f`

## string_xrefs

- `0x1800855d1`: `onecore\base\flighting\common\inc\FlightIdUtility.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FlightIdUtils::UnregisterFlightId(FlightIdUtils *this, const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v9; // [rsp+48h] [rbp+10h] BYREF

  v9 = 0;
  v3 = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, &v9);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(LPVOID, FlightIdUtils *))(*(_QWORD *)v9 + 104LL))(v9, this);
    v4 = v3;
    if ( v3 >= 0 )
    {
      v4 = 0;
      goto LABEL_7;
    }
    v5 = 296;
  }
  else
  {
    v5 = 294;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\flighting\\common\\inc\\FlightIdUtility.h",
    (const char *)(unsigned int)v3,
    v7);
LABEL_7:
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v9);
  return v4;
}

```

## disassembly

```asm
0x18008556c  mov     r11, rsp
0x18008556f  mov     [r11+8], rbx
0x180085573  push    rdi
0x180085574  sub     rsp, 30h
0x180085578  mov     rdi, rcx
0x18008557b  mov     qword ptr [r11+10h], 0
0x180085583  lea     rax, [r11+10h]
0x180085587  mov     [r11-18h], rax
0x18008558b  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x180085592  xor     edx, edx; pUnkOuter
0x180085594  lea     r8d, [rdx+1]; dwClsContext
0x180085598  lea     rcx, CLSID_FlightClientAPI; rclsid
0x18008559f  call    cs:__imp_CoCreateInstance
0x1800855a5  mov     ebx, eax
0x1800855a7  test    eax, eax
0x1800855a9  jns     short loc_1800855B2
0x1800855ab  mov     edx, 126h
0x1800855b0  jmp     short loc_1800855D1
0x1800855b2  mov     rcx, [rsp+38h+arg_8]
0x1800855b7  mov     rax, [rcx]
0x1800855ba  mov     rdx, rdi
0x1800855bd  mov     rax, [rax+68h]
0x1800855c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800855c6  mov     ebx, eax
0x1800855c8  test    eax, eax
0x1800855ca  jns     short loc_1800855E7
0x1800855cc  mov     edx, 128h; void *
0x1800855d1  lea     r8, aOnecoreBaseFli_46; "onecore\\base\\flighting\\common\\inc\\"...
0x1800855d8  mov     r9d, eax; char *
0x1800855db  mov     rcx, [rsp+38h]; this
0x1800855e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800855e5  jmp     short loc_1800855E9
0x1800855e7  xor     ebx, ebx
0x1800855e9  lea     rcx, [rsp+38h+arg_8]
0x1800855ee  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800855f3  mov     eax, ebx
0x1800855f5  mov     rbx, [rsp+38h+arg_0]
0x1800855fa  add     rsp, 30h
0x1800855fe  pop     rdi
0x1800855ff  retn
```
