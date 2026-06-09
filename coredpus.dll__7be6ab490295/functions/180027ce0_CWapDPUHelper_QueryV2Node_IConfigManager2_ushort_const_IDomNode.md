# CWapDPUHelper::QueryV2Node(IConfigManager2 *,ushort const *,IDomNode *)

- ea: `0x180027ce0`
- end: `0x180028078`
- name: `?QueryV2Node@CWapDPUHelper@@UEAAJPEAUIConfigManager2@@PEBGPEAUIDomNode@@@Z`
- size: `920`
- prototype: `__int64 __fastcall(CWapDPUHelper *__hidden this, struct IConfigManager2 *, const unsigned __int16 *, struct IDomNode *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001488`
- `0x1800110bc`
- `0x180027550`
- `0x180027ce0`
- `0x18002e4d4`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027e80`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027e9b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027e80`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027e9b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002802d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002803e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002804f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002802d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002803e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002804f`
- `OLEAUT32!__imp_VariantInit` at `0x180027d40`
- `OLEAUT32!__imp_VariantInit` at `0x180027d40`
- `OLEAUT32!__imp_VariantClear` at `0x18002801c`
- `OLEAUT32!__imp_VariantClear` at `0x18002801c`
- `DMCfgUtils!CfgUtilGetConfigDataTypeName` at `0x180027fb5`
- `DMCfgUtils!CfgUtilGetConfigDataTypeName` at `0x180027fb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWapDPUHelper::QueryV2Node(
        CWapDPUHelper *this,
        struct IConfigManager2 *a2,
        const unsigned __int16 *a3,
        struct IDomNode *a4)
{
  int v8; // ebx
  int v9; // r8d
  int v10; // r9d
  int v11; // eax
  BOOL v12; // eax
  int v13; // eax
  __int64 (__fastcall *v14)(struct IDomNode *, const wchar_t *, __int64); // rbx
  __int64 ConfigDataTypeName; // rax
  const wchar_t *v16; // rdx
  unsigned int v18; // [rsp+40h] [rbp-59h] BYREF
  wchar_t *String2; // [rsp+48h] [rbp-51h] BYREF
  struct IConfigNode *v20; // [rsp+50h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-41h] BYREF
  int v22; // [rsp+60h] [rbp-39h] BYREF
  BSTR v23; // [rsp+68h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-29h] BYREF
  const wchar_t *v25; // [rsp+88h] [rbp-11h] BYREF
  const unsigned __int16 *v26; // [rsp+90h] [rbp-9h] BYREF
  VARIANTARG v27; // [rsp+A0h] [rbp+7h] BYREF
  int v28; // [rsp+108h] [rbp+6Fh] BYREF

  v20 = 0;
  String2 = 0;
  v23 = 0;
  bstrString = 0;
  v28 = 0;
  v18 = 10;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !a2 || !a3 )
    goto LABEL_32;
  v8 = (*(__int64 (__fastcall **)(struct IConfigManager2 *, const unsigned __int16 *, struct IConfigNode **))(*(_QWORD *)a2 + 80LL))(
         a2,
         a3,
         &v20);
  if ( v8 < 0 )
    goto LABEL_33;
  v8 = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v20 + 224LL))(v20, &v28);
  if ( (int)(v8 + 0x80000000) >= 0 && v8 != -2147023728 )
    goto LABEL_33;
  if ( (unsigned int)dword_18003E080 > 5 )
  {
    v25 = L"QueryV2Node";
    v26 = a3;
    v22 = v28;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      0x80000000,
      (unsigned int)qword_180037800,
      v9,
      v10,
      (__int64)&v22,
      (__int64)&v26,
      (__int64)&v25);
  }
  v8 = (*(__int64 (__fastcall **)(struct IDomNode *, wchar_t **))(*(_QWORD *)a4 + 40LL))(a4, &String2);
  if ( v8 < 0 )
    goto LABEL_33;
  v11 = wcscmp_0(L"characteristic-query", String2);
  if ( !v28 )
  {
    if ( !v11 )
    {
      v16 = L"nocharacteristic";
LABEL_29:
      v13 = (*(__int64 (__fastcall **)(struct IDomNode *, const wchar_t *))(*(_QWORD *)a4 + 48LL))(a4, v16);
      goto LABEL_26;
    }
    if ( !wcscmp_0(L"parm-query", String2) )
    {
      v16 = L"noparm";
      goto LABEL_29;
    }
LABEL_32:
    v8 = -2147024809;
    goto LABEL_33;
  }
  if ( v11 )
  {
    if ( wcscmp_0(L"parm-query", String2) )
      goto LABEL_33;
    v8 = (*(__int64 (__fastcall **)(struct IConfigNode *, VARIANTARG *))(*(_QWORD *)v20 + 104LL))(v20, &pvarg);
    if ( v8 < 0 )
      goto LABEL_33;
    v8 = (*(__int64 (__fastcall **)(CWapDPUHelper *, struct IConfigNode *, unsigned int *))(*(_QWORD *)this + 88LL))(
           this,
           v20,
           &v18);
    if ( v8 < 0 )
      goto LABEL_33;
    v27 = pvarg;
    v8 = (*(__int64 (__fastcall **)(CWapDPUHelper *, _QWORD, VARIANTARG *, BSTR *))(*(_QWORD *)this + 96LL))(
           this,
           v18,
           &v27,
           &v23);
    if ( v8 < 0 )
      goto LABEL_33;
    v8 = (*(__int64 (__fastcall **)(struct IDomNode *, const wchar_t *))(*(_QWORD *)a4 + 48LL))(a4, L"parm");
    if ( v8 < 0 )
      goto LABEL_33;
    v8 = (*(__int64 (__fastcall **)(struct IDomNode *, const wchar_t *, BSTR))(*(_QWORD *)a4 + 96LL))(a4, L"value", v23);
    if ( v8 < 0 || ((v18 - 8) & 0xFFFFFFFD) == 0 )
      goto LABEL_33;
    v14 = *(__int64 (__fastcall **)(struct IDomNode *, const wchar_t *, __int64))(*(_QWORD *)a4 + 96LL);
    ConfigDataTypeName = CfgUtilGetConfigDataTypeName();
    v13 = v14(a4, L"datatype", ConfigDataTypeName);
LABEL_26:
    v8 = v13;
    goto LABEL_33;
  }
  v8 = (*(__int64 (__fastcall **)(struct IDomNode *, const wchar_t *))(*(_QWORD *)a4 + 48LL))(a4, L"characteristic");
  if ( v8 >= 0 )
  {
    v12 = (*(unsigned int (__fastcall **)(struct IDomNode *, const wchar_t *, BSTR *))(*(_QWORD *)a4 + 88LL))(
            a4,
            L"recursive",
            &bstrString) == -2147023728
       || !(unsigned int)_o__wcsicmp(L"true", bstrString)
       || !(unsigned int)_o__wcsicmp(L"1", bstrString);
    v13 = CWapDPUHelper::PopulateChildNodes(this, a2, a3, v20, a4, v12);
    goto LABEL_26;
  }
LABEL_33:
  VariantClear(&pvarg);
  SysFreeString(bstrString);
  SysFreeString(v23);
  SysFreeString(String2);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180027ce0  push    rbp
0x180027ce2  push    rbx
0x180027ce3  push    rsi
0x180027ce4  push    rdi
0x180027ce5  push    r14
0x180027ce7  push    r15
0x180027ce9  lea     rbp, [rsp-2Fh]
0x180027cee  sub     rsp, 0C8h
0x180027cf5  mov     rdi, r9
0x180027cf8  mov     rsi, r8
0x180027cfb  mov     r14, rdx
0x180027cfe  mov     r15, rcx
0x180027d01  mov     [rbp+57h+var_A0], 0
0x180027d09  mov     [rbp+57h+String2], 0
0x180027d11  mov     [rbp+57h+var_88], 0
0x180027d19  mov     [rbp+57h+bstrString], 0
0x180027d21  mov     [rbp+57h+arg_8], 0
0x180027d28  mov     [rbp+57h+var_B0], 0Ah
0x180027d2f  xorps   xmm0, xmm0
0x180027d32  xor     eax, eax
0x180027d34  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180027d38  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180027d3c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180027d40  call    cs:__imp_VariantInit
0x180027d47  nop     dword ptr [rax+rax+00h]
0x180027d4c  test    r14, r14
0x180027d4f  jz      loc_180028013
0x180027d55  test    rsi, rsi
0x180027d58  jz      loc_180028013
0x180027d5e  mov     rax, [r14]
0x180027d61  lea     r8, [rbp+57h+var_A0]
0x180027d65  mov     rdx, rsi
0x180027d68  mov     rcx, r14
0x180027d6b  mov     rax, [rax+50h]
0x180027d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d74  mov     ebx, eax
0x180027d76  test    eax, eax
0x180027d78  js      loc_180028018
0x180027d7e  mov     rcx, [rbp+57h+var_A0]
0x180027d82  mov     rax, [rcx]
0x180027d85  lea     rdx, [rbp+57h+arg_8]
0x180027d89  mov     rax, [rax+0E0h]
0x180027d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d95  mov     ebx, eax
0x180027d97  mov     ecx, 80000000h
0x180027d9c  add     eax, ecx
0x180027d9e  test    ecx, eax
0x180027da0  jnz     short loc_180027DAE
0x180027da2  cmp     ebx, 80070490h
0x180027da8  jnz     loc_180028018
0x180027dae  mov     eax, cs:dword_18003E080
0x180027db4  cmp     eax, 5
0x180027db7  jbe     short loc_180027DF5
0x180027db9  lea     rax, aQueryv2node; "QueryV2Node"
0x180027dc0  mov     [rbp+57h+var_68], rax
0x180027dc4  mov     [rbp+57h+var_60], rsi
0x180027dc8  mov     eax, [rbp+57h+arg_8]
0x180027dcb  mov     [rbp+57h+var_90], eax
0x180027dce  lea     rax, [rbp+57h+var_68]
0x180027dd2  mov     [rsp+0F0h+var_C0], rax
0x180027dd7  lea     rax, [rbp+57h+var_60]
0x180027ddb  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180027de0  lea     rax, [rbp+57h+var_90]
0x180027de4  mov     [rsp+0F0h+var_D0], rax
0x180027de9  lea     rdx, qword_180037800
0x180027df0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180027df5  mov     rax, [rdi]
0x180027df8  lea     rdx, [rbp+57h+String2]
0x180027dfc  mov     rcx, rdi
0x180027dff  mov     rax, [rax+28h]
0x180027e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e08  mov     ebx, eax
0x180027e0a  test    eax, eax
0x180027e0c  js      loc_180028018
0x180027e12  mov     rdx, [rbp+57h+String2]; String2
0x180027e16  lea     rcx, aCharacteristic; "characteristic-query"
0x180027e1d  call    wcscmp_0
0x180027e22  cmp     [rbp+57h+arg_8], 0
0x180027e26  jz      loc_180027FDA
0x180027e2c  test    eax, eax
0x180027e2e  jnz     loc_180027ED4
0x180027e34  mov     rax, [rdi]
0x180027e37  lea     rdx, aCharacteristic_0; "characteristic"
0x180027e3e  mov     rcx, rdi
0x180027e41  mov     rax, [rax+30h]
0x180027e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e4a  mov     ebx, eax
0x180027e4c  test    eax, eax
0x180027e4e  js      loc_180028018
0x180027e54  mov     rax, [rdi]
0x180027e57  lea     r8, [rbp+57h+bstrString]
0x180027e5b  lea     rdx, aRecursive; "recursive"
0x180027e62  mov     rcx, rdi
0x180027e65  mov     rax, [rax+58h]
0x180027e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e6e  cmp     eax, 80070490h
0x180027e73  jz      short loc_180027EAF
0x180027e75  mov     rdx, [rbp+57h+bstrString]
0x180027e79  lea     rcx, aTrue; "true"
0x180027e80  call    cs:__imp__o__wcsicmp
0x180027e87  nop     dword ptr [rax+rax+00h]
0x180027e8c  test    eax, eax
0x180027e8e  jz      short loc_180027EAF
0x180027e90  mov     rdx, [rbp+57h+bstrString]
0x180027e94  lea     rcx, a1; "1"
0x180027e9b  call    cs:__imp__o__wcsicmp
0x180027ea2  nop     dword ptr [rax+rax+00h]
0x180027ea7  test    eax, eax
0x180027ea9  jz      short loc_180027EAF
0x180027eab  xor     eax, eax
0x180027ead  jmp     short loc_180027EB4
0x180027eaf  mov     eax, 1
0x180027eb4  mov     [rsp+0F0h+var_C8], eax; int
0x180027eb8  mov     [rsp+0F0h+var_D0], rdi; struct IDomNode *
0x180027ebd  mov     r9, [rbp+57h+var_A0]; struct IConfigNode *
0x180027ec1  mov     r8, rsi; unsigned __int16 *
0x180027ec4  mov     rdx, r14; struct IConfigManager2 *
0x180027ec7  mov     rcx, r15; this
0x180027eca  call    ?PopulateChildNodes@CWapDPUHelper@@AEAAJPEAUIConfigManager2@@PEBGPEAUIConfigNode@@PEAUIDomNode@@H@Z; CWapDPUHelper::PopulateChildNodes(IConfigManager2 *,ushort const *,IConfigNode *,IDomNode *,int)
0x180027ecf  jmp     loc_180027FD6
0x180027ed4  mov     rdx, [rbp+57h+String2]; String2
0x180027ed8  lea     rcx, aParmQuery; "parm-query"
0x180027edf  call    wcscmp_0
0x180027ee4  test    eax, eax
0x180027ee6  jnz     loc_180028018
0x180027eec  mov     rcx, [rbp+57h+var_A0]
0x180027ef0  mov     rax, [rcx]
0x180027ef3  lea     rdx, [rbp+57h+pvarg]
0x180027ef7  mov     rax, [rax+68h]
0x180027efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f00  mov     ebx, eax
0x180027f02  test    eax, eax
0x180027f04  js      loc_180028018
0x180027f0a  mov     rax, [r15]
0x180027f0d  lea     r8, [rbp+57h+var_B0]
0x180027f11  mov     rdx, [rbp+57h+var_A0]
0x180027f15  mov     rcx, r15
0x180027f18  mov     rax, [rax+58h]
0x180027f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f21  mov     ebx, eax
0x180027f23  test    eax, eax
0x180027f25  js      loc_180028018
0x180027f2b  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180027f2f  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180027f34  movaps  [rbp+57h+var_50], xmm0
0x180027f38  movsd   [rbp+57h+var_40], xmm1
0x180027f3d  mov     rax, [r15]
0x180027f40  lea     r9, [rbp+57h+var_88]
0x180027f44  lea     r8, [rbp+57h+var_50]
0x180027f48  mov     edx, [rbp+57h+var_B0]
0x180027f4b  mov     rcx, r15
0x180027f4e  mov     rax, [rax+60h]
0x180027f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f57  mov     ebx, eax
0x180027f59  test    eax, eax
0x180027f5b  js      loc_180028018
0x180027f61  mov     rax, [rdi]
0x180027f64  lea     rdx, aParm; "parm"
0x180027f6b  mov     rcx, rdi
0x180027f6e  mov     rax, [rax+30h]
0x180027f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f77  mov     ebx, eax
0x180027f79  test    eax, eax
0x180027f7b  js      loc_180028018
0x180027f81  mov     rax, [rdi]
0x180027f84  mov     r8, [rbp+57h+var_88]
0x180027f88  lea     rdx, aValue; "value"
0x180027f8f  mov     rcx, rdi
0x180027f92  mov     rax, [rax+60h]
0x180027f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f9b  mov     ebx, eax
0x180027f9d  test    eax, eax
0x180027f9f  js      short loc_180028018
0x180027fa1  mov     ecx, [rbp+57h+var_B0]
0x180027fa4  lea     eax, [rcx-8]
0x180027fa7  test    eax, 0FFFFFFFDh
0x180027fac  jz      short loc_180028018
0x180027fae  mov     rax, [rdi]
0x180027fb1  mov     rbx, [rax+60h]
0x180027fb5  call    cs:__imp_CfgUtilGetConfigDataTypeName
0x180027fbc  nop     dword ptr [rax+rax+00h]
0x180027fc1  mov     r8, rax
0x180027fc4  lea     rdx, aDatatype; "datatype"
0x180027fcb  mov     rcx, rdi
0x180027fce  mov     rax, rbx
0x180027fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fd6  mov     ebx, eax
0x180027fd8  jmp     short loc_180028018
0x180027fda  test    eax, eax
0x180027fdc  jnz     short loc_180027FF6
0x180027fde  lea     rdx, aNocharacterist; "nocharacteristic"
0x180027fe5  mov     rax, [rdi]
0x180027fe8  mov     rcx, rdi
0x180027feb  mov     rax, [rax+30h]
0x180027fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ff4  jmp     short loc_180027FD6
0x180027ff6  mov     rdx, [rbp+57h+String2]; String2
0x180027ffa  lea     rcx, aParmQuery; "parm-query"
0x180028001  call    wcscmp_0
0x180028006  test    eax, eax
0x180028008  jnz     short loc_180028013
0x18002800a  lea     rdx, aNoparm; "noparm"
0x180028011  jmp     short loc_180027FE5
0x180028013  mov     ebx, 80070057h
0x180028018  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002801c  call    cs:__imp_VariantClear
0x180028023  nop     dword ptr [rax+rax+00h]
0x180028028  nop
0x180028029  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002802d  call    cs:__imp_SysFreeString
0x180028034  nop     dword ptr [rax+rax+00h]
0x180028039  nop
0x18002803a  mov     rcx, [rbp+57h+var_88]; bstrString
0x18002803e  call    cs:__imp_SysFreeString
0x180028045  nop     dword ptr [rax+rax+00h]
0x18002804a  nop
0x18002804b  mov     rcx, [rbp+57h+String2]; bstrString
0x18002804f  call    cs:__imp_SysFreeString
0x180028056  nop     dword ptr [rax+rax+00h]
0x18002805b  nop
0x18002805c  lea     rcx, [rbp+57h+var_A0]
0x180028060  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180028065  mov     eax, ebx
0x180028067  add     rsp, 0C8h
0x18002806e  pop     r15
0x180028070  pop     r14
0x180028072  pop     rdi
0x180028073  pop     rsi
0x180028074  pop     rbx
0x180028075  pop     rbp
0x180028076  retn
```
