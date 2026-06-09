# CWapDPUHelper::ProcessNode(IConfigManager2 *,ushort const *,IDomNode *)

- ea: `0x1800278c0`
- end: `0x180027cd2`
- name: `?ProcessNode@CWapDPUHelper@@UEAAJPEAUIConfigManager2@@PEBGPEAUIDomNode@@@Z`
- size: `1042`
- prototype: `int(CWapDPUHelper *__hidden this, struct IConfigManager2 *, const unsigned __int16 *, struct IDomNode *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000169c`
- `0x1800110bc`
- `0x1800146e4`
- `0x180027230`
- `0x1800278c0`
- `0x18002e4d4`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027ac4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027adf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027ac4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027adf`
- `OLEAUT32!__imp_SysFreeString` at `0x180027c63`
- `OLEAUT32!__imp_SysFreeString` at `0x180027c96`
- `OLEAUT32!__imp_SysFreeString` at `0x180027ca7`
- `OLEAUT32!__imp_SysFreeString` at `0x180027c63`
- `OLEAUT32!__imp_SysFreeString` at `0x180027c96`
- `OLEAUT32!__imp_SysFreeString` at `0x180027ca7`
- `OLEAUT32!__imp_VariantInit` at `0x180027920`
- `OLEAUT32!__imp_VariantInit` at `0x180027920`
- `OLEAUT32!__imp_VariantClear` at `0x180027c73`
- `OLEAUT32!__imp_VariantClear` at `0x180027c73`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002798c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002798c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWapDPUHelper::ProcessNode(
        CWapDPUHelper *this,
        struct IConfigManager2 *a2,
        const unsigned __int16 *a3,
        struct IDomNode *a4)
{
  unsigned __int16 *v8; // rdi
  HRESULT v9; // ebx
  CWapDPUHelper *v10; // rcx
  wchar_t *v11; // rbx
  int v12; // eax
  __int64 (__fastcall *v13)(CWapDPUHelper *, struct IConfigManager2 *, unsigned __int16 *, _QWORD, VARIANTARG *, LPVOID); // rax
  bool v14; // sf
  int v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  const struct std::nothrow_t *v19; // rdx
  unsigned __int16 *v21; // [rsp+50h] [rbp-49h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-41h] BYREF
  BSTR v23; // [rsp+60h] [rbp-39h] BYREF
  wchar_t *String2; // [rsp+68h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int16 *v27; // [rsp+90h] [rbp-9h] BYREF
  const unsigned __int16 *v28; // [rsp+98h] [rbp-1h] BYREF
  BSTR v29; // [rsp+A0h] [rbp+7h] BYREF
  wchar_t *v30; // [rsp+A8h] [rbp+Fh] BYREF
  VARIANTARG v31; // [rsp+B0h] [rbp+17h] BYREF
  unsigned int v32; // [rsp+118h] [rbp+7Fh] BYREF

  String2 = 0;
  v23 = 0;
  ppv = 0;
  v32 = 10;
  memset(&pvarg, 0, sizeof(pvarg));
  v8 = 0;
  v21 = 0;
  VariantInit(&pvarg);
  v9 = (*(__int64 (__fastcall **)(struct IDomNode *, wchar_t **))(*(_QWORD *)a4 + 40LL))(a4, &String2);
  if ( v9 < 0 )
    goto LABEL_32;
  v9 = (*(__int64 (__fastcall **)(struct IDomNode *, LPVOID *))(*(_QWORD *)a4 + 136LL))(a4, &ppv);
  if ( v9 < 0 )
    goto LABEL_32;
  if ( !ppv )
  {
    v9 = CoCreateInstance(
           &GUID_dab7ccb2_ec94_4c7e_ab52_826d6acd5249,
           0,
           1u,
           &GUID_dfcdb0e8_cb00_417b_82fb_1b6ac10a44a9,
           &ppv);
    if ( v9 < 0 )
      goto LABEL_32;
    v9 = (*(__int64 (__fastcall **)(struct IDomNode *, LPVOID))(*(_QWORD *)a4 + 128LL))(a4, ppv);
    if ( v9 < 0 )
      goto LABEL_32;
  }
  v9 = CWapDPUHelper::ModifyNodePathForScope(v10, a3, a4, &v21);
  if ( v9 < 0 )
    goto LABEL_31;
  v11 = String2;
  if ( !wcscmp_0(L"characteristic", String2) )
  {
    v8 = v21;
    v12 = (*(__int64 (__fastcall **)(CWapDPUHelper *, struct IConfigManager2 *, unsigned __int16 *, __int64, LPVOID))(*(_QWORD *)this + 32LL))(
            this,
            a2,
            v21,
            8,
            ppv);
LABEL_27:
    v9 = v12;
    v14 = v12 < 0;
LABEL_28:
    if ( !v14 )
      goto LABEL_35;
    goto LABEL_32;
  }
  if ( !wcscmp_0(L"parm", v11) )
  {
    v9 = (*(__int64 (__fastcall **)(CWapDPUHelper *, struct IDomNode *, unsigned int *))(*(_QWORD *)this + 80LL))(
           this,
           a4,
           &v32);
    if ( v9 >= 0 )
    {
      pvarg.vt = 8;
      v9 = (*(__int64 (__fastcall **)(struct IDomNode *, const wchar_t *, CY *))(*(_QWORD *)a4 + 88LL))(
             a4,
             L"value",
             &pvarg.cyVal);
      if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147023728 )
      {
        v9 = (*(__int64 (__fastcall **)(struct IDomNode *, const wchar_t *, BSTR *))(*(_QWORD *)a4 + 88LL))(
               a4,
               L"exec",
               &v23);
        v8 = v21;
        if ( v9 == -2147023728 || (unsigned int)_o__wcsicmp(v23, L"1") )
        {
          v13 = *(__int64 (__fastcall **)(CWapDPUHelper *, struct IConfigManager2 *, unsigned __int16 *, _QWORD, VARIANTARG *, LPVOID))(*(_QWORD *)this + 56LL);
        }
        else
        {
          if ( (unsigned int)_o__wcsicmp(v23, L"1") )
          {
LABEL_19:
            v14 = v9 < 0;
            goto LABEL_28;
          }
          v13 = *(__int64 (__fastcall **)(CWapDPUHelper *, struct IConfigManager2 *, unsigned __int16 *, _QWORD, VARIANTARG *, LPVOID))(*(_QWORD *)this + 48LL);
        }
        v31 = pvarg;
        v9 = v13(this, a2, v8, v32, &v31, ppv);
        goto LABEL_19;
      }
    }
LABEL_31:
    v8 = v21;
    goto LABEL_32;
  }
  if ( !wcscmp_0(L"nocharacteristic", v11) || !wcscmp_0(L"noparm", v11) )
  {
    v8 = v21;
    v12 = (*(__int64 (__fastcall **)(CWapDPUHelper *, struct IConfigManager2 *, unsigned __int16 *, LPVOID))(*(_QWORD *)this + 40LL))(
            this,
            a2,
            v21,
            ppv);
    goto LABEL_27;
  }
  if ( !wcscmp_0(L"characteristic-query", v11) )
  {
    v8 = v21;
LABEL_26:
    v12 = (*(__int64 (__fastcall **)(CWapDPUHelper *, struct IConfigManager2 *, unsigned __int16 *, struct IDomNode *))(*(_QWORD *)this + 64LL))(
            this,
            a2,
            v8,
            a4);
    goto LABEL_27;
  }
  v15 = wcscmp_0(L"parm-query", v11);
  v8 = v21;
  if ( !v15 )
    goto LABEL_26;
  v9 = -2147024809;
LABEL_32:
  bstrString = 0;
  (*(void (__fastcall **)(struct IDomNode *, _QWORD))(*(_QWORD *)a4 + 24LL))(a4, (unsigned int)v9);
  (*(void (__fastcall **)(struct IDomNode *, BSTR *))(*(_QWORD *)a4 + 64LL))(a4, &bstrString);
  if ( (unsigned int)dword_18003E080 > 2 )
  {
    v27 = v8;
    v28 = a3;
    v29 = bstrString;
    v30 = String2;
    LODWORD(v21) = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v16,
      (unsigned int)&unk_180037728,
      v17,
      v18,
      (__int64)&v21,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27);
  }
  SysFreeString(bstrString);
LABEL_35:
  VariantClear(&pvarg);
  operator delete(v8, v19);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&ppv);
  SysFreeString(v23);
  SysFreeString(String2);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800278c0  mov     [rsp-8+arg_0], rbx
0x1800278c5  mov     [rsp-8+arg_8], rsi
0x1800278ca  push    rbp
0x1800278cb  push    rdi
0x1800278cc  push    r12
0x1800278ce  push    r14
0x1800278d0  push    r15
0x1800278d2  lea     rbp, [rsp-37h]
0x1800278d7  sub     rsp, 0D0h
0x1800278de  mov     rsi, r9
0x1800278e1  mov     r12, r8
0x1800278e4  mov     r15, rdx
0x1800278e7  mov     r14, rcx
0x1800278ea  mov     [rbp+57h+String2], 0
0x1800278f2  mov     [rbp+57h+var_90], 0
0x1800278fa  mov     [rbp+57h+var_98], 0
0x180027902  mov     [rbp+57h+arg_18], 0Ah
0x180027909  xorps   xmm0, xmm0
0x18002790c  xor     eax, eax
0x18002790e  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180027912  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180027916  xor     edi, edi
0x180027918  mov     [rbp+57h+var_A0], rdi
0x18002791c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180027920  call    cs:__imp_VariantInit
0x180027927  nop     dword ptr [rax+rax+00h]
0x18002792c  mov     rax, [rsi]
0x18002792f  lea     rdx, [rbp+57h+String2]
0x180027933  mov     rcx, rsi
0x180027936  mov     rax, [rax+28h]
0x18002793a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002793f  mov     ebx, eax
0x180027941  test    eax, eax
0x180027943  js      loc_180027BD3
0x180027949  mov     rax, [rsi]
0x18002794c  lea     rdx, [rbp+57h+var_98]
0x180027950  mov     rcx, rsi
0x180027953  mov     rax, [rax+88h]
0x18002795a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002795f  mov     ebx, eax
0x180027961  test    eax, eax
0x180027963  js      loc_180027BD3
0x180027969  cmp     [rbp+57h+var_98], rdi
0x18002796d  jnz     short loc_1800279C2
0x18002796f  lea     rax, [rbp+57h+var_98]
0x180027973  mov     [rsp+0F0h+ppv], rax; ppv
0x180027978  lea     r9, _GUID_dfcdb0e8_cb00_417b_82fb_1b6ac10a44a9; riid
0x18002797f  xor     edx, edx; pUnkOuter
0x180027981  lea     r8d, [rdi+1]; dwClsContext
0x180027985  lea     rcx, _GUID_dab7ccb2_ec94_4c7e_ab52_826d6acd5249; rclsid
0x18002798c  call    cs:__imp_CoCreateInstance
0x180027993  nop     dword ptr [rax+rax+00h]
0x180027998  mov     ebx, eax
0x18002799a  test    eax, eax
0x18002799c  js      loc_180027BD3
0x1800279a2  mov     rax, [rsi]
0x1800279a5  mov     rdx, [rbp+57h+var_98]
0x1800279a9  mov     rcx, rsi
0x1800279ac  mov     rax, [rax+80h]
0x1800279b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279b8  mov     ebx, eax
0x1800279ba  test    eax, eax
0x1800279bc  js      loc_180027BD3
0x1800279c2  lea     r9, [rbp+57h+var_A0]; unsigned __int16 **
0x1800279c6  mov     r8, rsi; struct IDomNode *
0x1800279c9  mov     rdx, r12; unsigned __int16 *
0x1800279cc  call    ?ModifyNodePathForScope@CWapDPUHelper@@AEAAJPEBGPEAUIDomNode@@PEAPEAG@Z; CWapDPUHelper::ModifyNodePathForScope(ushort const *,IDomNode *,ushort * *)
0x1800279d1  mov     ebx, eax
0x1800279d3  test    eax, eax
0x1800279d5  js      loc_180027BCF
0x1800279db  mov     rbx, [rbp+57h+String2]
0x1800279df  mov     rdx, rbx; String2
0x1800279e2  lea     rcx, aCharacteristic_0; "characteristic"
0x1800279e9  call    wcscmp_0
0x1800279ee  test    eax, eax
0x1800279f0  jnz     short loc_180027A1F
0x1800279f2  mov     rcx, [rbp+57h+var_98]
0x1800279f6  mov     rax, [r14]
0x1800279f9  mov     [rsp+0F0h+ppv], rcx
0x1800279fe  mov     r9d, 8
0x180027a04  mov     rdi, [rbp+57h+var_A0]
0x180027a08  mov     r8, rdi
0x180027a0b  mov     rdx, r15
0x180027a0e  mov     rcx, r14
0x180027a11  mov     rax, [rax+20h]
0x180027a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a1a  jmp     loc_180027BBD
0x180027a1f  mov     rdx, rbx; String2
0x180027a22  lea     rcx, aParm; "parm"
0x180027a29  call    wcscmp_0
0x180027a2e  test    eax, eax
0x180027a30  jnz     loc_180027B3E
0x180027a36  mov     rax, [r14]
0x180027a39  lea     r8, [rbp+57h+arg_18]
0x180027a3d  mov     rdx, rsi
0x180027a40  mov     rcx, r14
0x180027a43  mov     rax, [rax+50h]
0x180027a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a4c  mov     ebx, eax
0x180027a4e  test    eax, eax
0x180027a50  js      loc_180027BCF
0x180027a56  mov     ecx, 8
0x180027a5b  mov     word ptr [rbp+57h+pvarg], cx
0x180027a5f  mov     rax, [rsi]
0x180027a62  lea     r8, [rbp+57h+pvarg+8]
0x180027a66  lea     rdx, aValue; "value"
0x180027a6d  mov     rcx, rsi
0x180027a70  mov     rax, [rax+58h]
0x180027a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a79  mov     ebx, eax
0x180027a7b  mov     ecx, 80000000h
0x180027a80  add     eax, ecx
0x180027a82  test    ecx, eax
0x180027a84  jnz     short loc_180027A92
0x180027a86  cmp     ebx, 80070490h
0x180027a8c  jnz     loc_180027BCF
0x180027a92  mov     rax, [rsi]
0x180027a95  lea     r8, [rbp+57h+var_90]
0x180027a99  lea     rdx, aExec; "exec"
0x180027aa0  mov     rcx, rsi
0x180027aa3  mov     rax, [rax+58h]
0x180027aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027aac  mov     ebx, eax
0x180027aae  mov     rdi, [rbp+57h+var_A0]
0x180027ab2  cmp     eax, 80070490h
0x180027ab7  jz      short loc_180027AF8
0x180027ab9  lea     rdx, a1; "1"
0x180027ac0  mov     rcx, [rbp+57h+var_90]
0x180027ac4  call    cs:__imp__o__wcsicmp
0x180027acb  nop     dword ptr [rax+rax+00h]
0x180027ad0  test    eax, eax
0x180027ad2  jnz     short loc_180027AF8
0x180027ad4  lea     rdx, a1; "1"
0x180027adb  mov     rcx, [rbp+57h+var_90]
0x180027adf  call    cs:__imp__o__wcsicmp
0x180027ae6  nop     dword ptr [rax+rax+00h]
0x180027aeb  test    eax, eax
0x180027aed  jnz     short loc_180027B37
0x180027aef  mov     rax, [r14]
0x180027af2  mov     rax, [rax+30h]
0x180027af6  jmp     short loc_180027AFF
0x180027af8  mov     rax, [r14]
0x180027afb  mov     rax, [rax+38h]
0x180027aff  mov     rcx, [rbp+57h+var_98]
0x180027b03  mov     [rsp+0F0h+var_C8], rcx
0x180027b08  lea     rcx, [rbp+57h+var_40]
0x180027b0c  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180027b10  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180027b15  mov     [rsp+0F0h+ppv], rcx
0x180027b1a  movaps  [rbp+57h+var_40], xmm0
0x180027b1e  movsd   [rbp+57h+var_30], xmm1
0x180027b23  mov     r9d, [rbp+57h+arg_18]
0x180027b27  mov     r8, rdi
0x180027b2a  mov     rdx, r15
0x180027b2d  mov     rcx, r14
0x180027b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b35  mov     ebx, eax
0x180027b37  test    ebx, ebx
0x180027b39  jmp     loc_180027BC1
0x180027b3e  mov     rdx, rbx; String2
0x180027b41  lea     rcx, aNocharacterist; "nocharacteristic"
0x180027b48  call    wcscmp_0
0x180027b4d  test    eax, eax
0x180027b4f  jnz     short loc_180027B62
0x180027b51  mov     rax, [r14]
0x180027b54  mov     r9, [rbp+57h+var_98]
0x180027b58  mov     rdi, [rbp+57h+var_A0]
0x180027b5c  mov     rax, [rax+28h]
0x180027b60  jmp     short loc_180027BAF
0x180027b62  mov     rdx, rbx; String2
0x180027b65  lea     rcx, aNoparm; "noparm"
0x180027b6c  call    wcscmp_0
0x180027b71  test    eax, eax
0x180027b73  jz      short loc_180027B51
0x180027b75  mov     rdx, rbx; String2
0x180027b78  lea     rcx, aCharacteristic; "characteristic-query"
0x180027b7f  call    wcscmp_0
0x180027b84  test    eax, eax
0x180027b86  jnz     short loc_180027B8E
0x180027b88  mov     rdi, [rbp+57h+var_A0]
0x180027b8c  jmp     short loc_180027BA5
0x180027b8e  mov     rdx, rbx; String2
0x180027b91  lea     rcx, aParmQuery; "parm-query"
0x180027b98  call    wcscmp_0
0x180027b9d  mov     rdi, [rbp+57h+var_A0]
0x180027ba1  test    eax, eax
0x180027ba3  jnz     short loc_180027BC8
0x180027ba5  mov     r9, rsi
0x180027ba8  mov     rax, [r14]
0x180027bab  mov     rax, [rax+40h]
0x180027baf  mov     r8, rdi
0x180027bb2  mov     rdx, r15
0x180027bb5  mov     rcx, r14
0x180027bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bbd  mov     ebx, eax
0x180027bbf  test    eax, eax
0x180027bc1  js      short loc_180027BD3
0x180027bc3  jmp     loc_180027C6F
0x180027bc8  mov     ebx, 80070057h
0x180027bcd  jmp     short loc_180027BD3
0x180027bcf  mov     rdi, [rbp+57h+var_A0]
0x180027bd3  mov     [rbp+57h+bstrString], 0
0x180027bdb  mov     rax, [rsi]
0x180027bde  mov     edx, ebx
0x180027be0  mov     rcx, rsi
0x180027be3  mov     rax, [rax+18h]
0x180027be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bec  mov     rax, [rsi]
0x180027bef  lea     rdx, [rbp+57h+bstrString]
0x180027bf3  mov     rcx, rsi
0x180027bf6  mov     rax, [rax+40h]
0x180027bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bff  mov     eax, cs:dword_18003E080
0x180027c05  cmp     eax, 2
0x180027c08  jbe     short loc_180027C5F
0x180027c0a  mov     [rbp+57h+var_60], rdi
0x180027c0e  mov     [rbp+57h+var_58], r12
0x180027c12  mov     rax, [rbp+57h+bstrString]
0x180027c16  mov     [rbp+57h+var_50], rax
0x180027c1a  mov     rax, [rbp+57h+String2]
0x180027c1e  mov     [rbp+57h+var_48], rax
0x180027c22  mov     dword ptr [rbp+57h+var_A0], ebx
0x180027c25  lea     rax, [rbp+57h+var_60]
0x180027c29  mov     [rsp+0F0h+var_B0], rax
0x180027c2e  lea     rax, [rbp+57h+var_58]
0x180027c32  mov     [rsp+0F0h+var_B8], rax
0x180027c37  lea     rax, [rbp+57h+var_50]
0x180027c3b  mov     [rsp+0F0h+var_C0], rax
0x180027c40  lea     rax, [rbp+57h+var_48]
0x180027c44  mov     [rsp+0F0h+var_C8], rax
0x180027c49  lea     rax, [rbp+57h+var_A0]
0x180027c4d  mov     [rsp+0F0h+ppv], rax
0x180027c52  lea     rdx, unk_180037728
0x180027c59  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180027c5e  nop
0x180027c5f  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180027c63  call    cs:__imp_SysFreeString
0x180027c6a  nop     dword ptr [rax+rax+00h]
0x180027c6f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180027c73  call    cs:__imp_VariantClear
0x180027c7a  nop     dword ptr [rax+rax+00h]
0x180027c7f  mov     rcx, rdi; void *
0x180027c82  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180027c87  nop
0x180027c88  lea     rcx, [rbp+57h+var_98]
0x180027c8c  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180027c91  nop
0x180027c92  mov     rcx, [rbp+57h+var_90]; bstrString
0x180027c96  call    cs:__imp_SysFreeString
0x180027c9d  nop     dword ptr [rax+rax+00h]
0x180027ca2  nop
0x180027ca3  mov     rcx, [rbp+57h+String2]; bstrString
0x180027ca7  call    cs:__imp_SysFreeString
0x180027cae  nop     dword ptr [rax+rax+00h]
0x180027cb3  mov     eax, ebx
0x180027cb5  lea     r11, [rsp+0F0h+var_20]
0x180027cbd  mov     rbx, [r11+30h]
0x180027cc1  mov     rsi, [r11+38h]
0x180027cc5  mov     rsp, r11
0x180027cc8  pop     r15
0x180027cca  pop     r14
0x180027ccc  pop     r12
0x180027cce  pop     rdi
0x180027ccf  pop     rbp
0x180027cd0  retn
```
