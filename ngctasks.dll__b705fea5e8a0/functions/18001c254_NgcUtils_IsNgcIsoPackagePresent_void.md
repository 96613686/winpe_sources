# NgcUtils::IsNgcIsoPackagePresent(void)

- ea: `0x18001c254`
- end: `0x18001c31e`
- name: `?IsNgcIsoPackagePresent@NgcUtils@@YA_NXZ`
- size: `202`
- prototype: `char __fastcall(NgcUtils *this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bdbc`

## callees

- `0x18000ebc0`
- `0x180017868`
- `0x18001c254`
- `0x18001c520`
- `0x18001db3c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c2f3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c310`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c2f3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c310`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c2ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c2ae`

## string_xrefs

- `0x18001c273`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18001c2cf`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall NgcUtils::IsNgcIsoPackagePresent(NgcUtils *this, unsigned int a2)
{
  int v2; // eax
  const char *v4; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v6; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  v2 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)&v6, a2);
  if ( v2 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA0,
      (int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)(unsigned int)v2);
LABEL_5:
    if ( v6 )
      CoUninitialize();
    return 0;
  }
  ppv = 0;
  if ( CoCreateInstance(
         &GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9,
         0,
         1u,
         &GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00,
         &ppv) < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)0x80090029LL,
      (int)"NgcIsoCtnr could not be instantiated.",
      v4);
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&ppv);
    goto LABEL_5;
  }
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&ppv);
  if ( v6 )
    CoUninitialize();
  return 1;
}

```

## disassembly

```asm
0x18001c254  sub     rsp, 38h
0x18001c258  mov     [rsp+38h+arg_0], 0
0x18001c25d  lea     rcx, [rsp+38h+arg_0]; this
0x18001c262  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x18001c267  mov     rcx, [rsp+38h]; this
0x18001c26c  test    eax, eax
0x18001c26e  jns     short loc_18001C287
0x18001c270  mov     r9d, eax; char *
0x18001c273  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001c27a  mov     edx, 0A0h; void *
0x18001c27f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c284  nop
0x18001c285  jmp     short loc_18001C2EC
0x18001c287  mov     [rsp+38h+arg_8], 0
0x18001c290  lea     rax, [rsp+38h+arg_8]
0x18001c295  mov     [rsp+38h+ppv], rax; ppv
0x18001c29a  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x18001c2a1  xor     edx, edx; pUnkOuter
0x18001c2a3  lea     r8d, [rdx+1]; dwClsContext
0x18001c2a7  lea     rcx, _GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9; rclsid
0x18001c2ae  call    cs:__imp_CoCreateInstance
0x18001c2b4  test    eax, eax
0x18001c2b6  jns     short loc_18001C2FE
0x18001c2b8  mov     rcx, [rsp+38h]; this
0x18001c2bd  lea     rax, aNgcisoctnrCoul; "NgcIsoCtnr could not be instantiated."
0x18001c2c4  mov     [rsp+38h+ppv], rax; int
0x18001c2c9  mov     r9d, 80090029h; char *
0x18001c2cf  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001c2d6  mov     edx, 0A9h; void *
0x18001c2db  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001c2e0  nop
0x18001c2e1  lea     rcx, [rsp+38h+arg_8]
0x18001c2e6  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001c2eb  nop
0x18001c2ec  cmp     [rsp+38h+arg_0], 0
0x18001c2f1  jz      short loc_18001C2FA
0x18001c2f3  call    cs:__imp_CoUninitialize
0x18001c2f9  nop
0x18001c2fa  xor     al, al
0x18001c2fc  jmp     short loc_18001C319
0x18001c2fe  lea     rcx, [rsp+38h+arg_8]
0x18001c303  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001c308  nop
0x18001c309  cmp     [rsp+38h+arg_0], 0
0x18001c30e  jz      short loc_18001C317
0x18001c310  call    cs:__imp_CoUninitialize
0x18001c316  nop
0x18001c317  mov     al, 1
0x18001c319  add     rsp, 38h
0x18001c31d  retn
```
