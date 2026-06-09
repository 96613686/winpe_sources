# NgcUtils::IsNgcIsoPackagePresent(void)

- ea: `0x180023894`
- end: `0x180023958`
- name: `?IsNgcIsoPackagePresent@NgcUtils@@YA_NXZ`
- size: `196`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023454`

## callees

- `0x18001069c`
- `0x18001d6c8`
- `0x18002234c`
- `0x180023894`
- `0x180023c6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180023930`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002394b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180023930`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002394b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800238ed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800238ed`

## string_xrefs

- `0x1800238b3`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18002390e`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

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
0x180023894  sub     rsp, 38h
0x180023898  mov     [rsp+38h+arg_0], 0
0x18002389d  lea     rcx, [rsp+38h+arg_0]; this
0x1800238a2  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x1800238a7  mov     rcx, [rsp+38h]; this
0x1800238ac  test    eax, eax
0x1800238ae  jns     short loc_1800238C6
0x1800238b0  mov     r9d, eax; char *
0x1800238b3  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800238ba  mov     edx, 0A0h; void *
0x1800238bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800238c4  jmp     short loc_180023929
0x1800238c6  mov     [rsp+38h+arg_8], 0
0x1800238cf  lea     rax, [rsp+38h+arg_8]
0x1800238d4  mov     [rsp+38h+ppv], rax; ppv
0x1800238d9  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x1800238e0  xor     edx, edx; pUnkOuter
0x1800238e2  lea     r8d, [rdx+1]; dwClsContext
0x1800238e6  lea     rcx, _GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9; rclsid
0x1800238ed  call    cs:__imp_CoCreateInstance
0x1800238f3  test    eax, eax
0x1800238f5  jns     short loc_18002393A
0x1800238f7  mov     rcx, [rsp+38h]; this
0x1800238fc  lea     rax, aNgcisoctnrCoul; "NgcIsoCtnr could not be instantiated."
0x180023903  mov     [rsp+38h+ppv], rax; int
0x180023908  mov     r9d, 80090029h; char *
0x18002390e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180023915  mov     edx, 0A9h; void *
0x18002391a  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002391f  lea     rcx, [rsp+38h+arg_8]
0x180023924  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180023929  cmp     [rsp+38h+arg_0], 0
0x18002392e  jz      short loc_180023936
0x180023930  call    cs:__imp_CoUninitialize
0x180023936  xor     al, al
0x180023938  jmp     short loc_180023953
0x18002393a  lea     rcx, [rsp+38h+arg_8]
0x18002393f  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180023944  cmp     [rsp+38h+arg_0], 0
0x180023949  jz      short loc_180023951
0x18002394b  call    cs:__imp_CoUninitialize
0x180023951  mov     al, 1
0x180023953  add     rsp, 38h
0x180023957  retn
```
