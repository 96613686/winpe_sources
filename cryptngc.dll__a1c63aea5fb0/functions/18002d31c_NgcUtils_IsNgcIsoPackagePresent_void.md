# NgcUtils::IsNgcIsoPackagePresent(void)

- ea: `0x18002d31c`
- end: `0x18002d3e0`
- name: `?IsNgcIsoPackagePresent@NgcUtils@@YA_NXZ`
- size: `196`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800433ec`

## callees

- `0x18002d31c`
- `0x18002d3e8`
- `0x180032fcc`
- `0x180041ccc`
- `0x1800438d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d3b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d3d3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d3b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d3d3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d375`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d375`

## string_xrefs

- `0x18002d33b`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18002d396`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall NgcUtils::IsNgcIsoPackagePresent(NgcUtils *this, unsigned int a2)
{
  int v2; // eax
  int ppv; // [rsp+20h] [rbp-18h]
  const char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v7; // [rsp+40h] [rbp+8h] BYREF
  LPVOID v8; // [rsp+48h] [rbp+10h] BYREF

  v7 = 0;
  v2 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)&v7, a2);
  if ( v2 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)(unsigned int)v2,
      ppv);
LABEL_5:
    if ( v7 )
      CoUninitialize();
    return 0;
  }
  v8 = 0;
  if ( CoCreateInstance(
         &GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9,
         0,
         1u,
         &GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00,
         &v8) < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)0x80090029LL,
      (int)"NgcIsoCtnr could not be instantiated.",
      v5);
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v8);
    goto LABEL_5;
  }
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v8);
  if ( v7 )
    CoUninitialize();
  return 1;
}

```

## disassembly

```asm
0x18002d31c  sub     rsp, 38h
0x18002d320  mov     [rsp+38h+arg_0], 0
0x18002d325  lea     rcx, [rsp+38h+arg_0]; this
0x18002d32a  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x18002d32f  mov     rcx, [rsp+38h]; this
0x18002d334  test    eax, eax
0x18002d336  jns     short loc_18002D34E
0x18002d338  mov     r9d, eax; char *
0x18002d33b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002d342  mov     edx, 0A0h; void *
0x18002d347  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d34c  jmp     short loc_18002D3B1
0x18002d34e  mov     [rsp+38h+arg_8], 0
0x18002d357  lea     rax, [rsp+38h+arg_8]
0x18002d35c  mov     [rsp+38h+ppv], rax; ppv
0x18002d361  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x18002d368  xor     edx, edx; pUnkOuter
0x18002d36a  lea     r8d, [rdx+1]; dwClsContext
0x18002d36e  lea     rcx, _GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9; rclsid
0x18002d375  call    cs:__imp_CoCreateInstance
0x18002d37b  test    eax, eax
0x18002d37d  jns     short loc_18002D3C2
0x18002d37f  mov     rcx, [rsp+38h]; this
0x18002d384  lea     rax, aNgcisoctnrCoul; "NgcIsoCtnr could not be instantiated."
0x18002d38b  mov     [rsp+38h+ppv], rax; int
0x18002d390  mov     r9d, 80090029h; char *
0x18002d396  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002d39d  mov     edx, 0A9h; void *
0x18002d3a2  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002d3a7  lea     rcx, [rsp+38h+arg_8]
0x18002d3ac  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18002d3b1  cmp     [rsp+38h+arg_0], 0
0x18002d3b6  jz      short loc_18002D3BE
0x18002d3b8  call    cs:__imp_CoUninitialize
0x18002d3be  xor     al, al
0x18002d3c0  jmp     short loc_18002D3DB
0x18002d3c2  lea     rcx, [rsp+38h+arg_8]
0x18002d3c7  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18002d3cc  cmp     [rsp+38h+arg_0], 0
0x18002d3d1  jz      short loc_18002D3D9
0x18002d3d3  call    cs:__imp_CoUninitialize
0x18002d3d9  mov     al, 1
0x18002d3db  add     rsp, 38h
0x18002d3df  retn
```
