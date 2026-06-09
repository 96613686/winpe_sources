# TeredoUPnP::DeletePortMapping(IUPnPService *,ushort)

- ea: `0x180029978`
- end: `0x180029cb6`
- name: `?DeletePortMapping@TeredoUPnP@@AEAAJPEAUIUPnPService@@G@Z`
- size: `830`
- prototype: `__int64 __fastcall(TeredoUPnP *__hidden this, struct IUPnPService *, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180028544`

## callees

- `0x18000d7c0`
- `0x1800190f0`
- `0x180029978`
- `0x180043334`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029b82`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029bc8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029b82`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029bc8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800299d7`
- `OLEAUT32!__imp_SysAllocString` at `0x180029aae`
- `OLEAUT32!__imp_SysAllocString` at `0x1800299d7`
- `OLEAUT32!__imp_SysAllocString` at `0x180029aae`
- `OLEAUT32!__imp_SysFreeString` at `0x180029c07`
- `OLEAUT32!__imp_SysFreeString` at `0x180029c07`
- `OLEAUT32!__imp_VariantInit` at `0x1800299a4`
- `OLEAUT32!__imp_VariantInit` at `0x1800299b4`
- `OLEAUT32!__imp_VariantInit` at `0x1800299c4`
- `OLEAUT32!__imp_VariantInit` at `0x180029a62`
- `OLEAUT32!__imp_VariantInit` at `0x180029afb`
- `OLEAUT32!__imp_VariantInit` at `0x1800299a4`
- `OLEAUT32!__imp_VariantInit` at `0x1800299b4`
- `OLEAUT32!__imp_VariantInit` at `0x1800299c4`
- `OLEAUT32!__imp_VariantInit` at `0x180029a62`
- `OLEAUT32!__imp_VariantInit` at `0x180029afb`
- `OLEAUT32!__imp_VariantClear` at `0x180029aeb`
- `OLEAUT32!__imp_VariantClear` at `0x180029b0f`
- `OLEAUT32!__imp_VariantClear` at `0x180029b3d`
- `OLEAUT32!__imp_VariantClear` at `0x180029b68`
- `OLEAUT32!__imp_VariantClear` at `0x180029c17`
- `OLEAUT32!__imp_VariantClear` at `0x180029c27`
- `OLEAUT32!__imp_VariantClear` at `0x180029c37`
- `OLEAUT32!__imp_VariantClear` at `0x180029c68`
- `OLEAUT32!__imp_VariantClear` at `0x180029c78`
- `OLEAUT32!__imp_VariantClear` at `0x180029c88`
- `OLEAUT32!__imp_VariantClear` at `0x180029aeb`
- `OLEAUT32!__imp_VariantClear` at `0x180029b0f`
- `OLEAUT32!__imp_VariantClear` at `0x180029b3d`
- `OLEAUT32!__imp_VariantClear` at `0x180029b68`
- `OLEAUT32!__imp_VariantClear` at `0x180029c17`
- `OLEAUT32!__imp_VariantClear` at `0x180029c27`
- `OLEAUT32!__imp_VariantClear` at `0x180029c37`
- `OLEAUT32!__imp_VariantClear` at `0x180029c68`
- `OLEAUT32!__imp_VariantClear` at `0x180029c78`
- `OLEAUT32!__imp_VariantClear` at `0x180029c88`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180029ad9`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180029ad9`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180029a0d`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180029a0d`

## string_xrefs

- `0x180029c4a`: `Port mapping for %u deleted successfully.`
- `0x1800299d0`: `DeletePortMapping`
- `0x180029bf8`: `DeletePortMapping action returned 0x%x`

## pseudocode

```c
__int64 __fastcall TeredoUPnP::DeletePortMapping(TeredoUPnP *this, struct IUPnPService *a2, unsigned __int16 a3)
{
  unsigned int v4; // r14d
  BSTR v6; // rax
  OLECHAR *v7; // rbx
  HRESULT v8; // esi
  int i; // eax
  const OLECHAR *v10; // rcx
  LONGLONG llVal; // rax
  int TickCount64; // edi
  HRESULT (__stdcall *InvokeAction)(IUPnPService *, BSTR, VARIANT, VARIANT *, VARIANT *); // rax
  int v14; // eax
  VARIANTARG pv; // [rsp+30h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-31h] BYREF
  VARIANTARG v18; // [rsp+60h] [rbp-19h] BYREF
  VARIANTARG v19; // [rsp+78h] [rbp-1h] BYREF
  VARIANTARG v20; // [rsp+90h] [rbp+17h] BYREF
  LONG rgIndices; // [rsp+E8h] [rbp+6Fh] BYREF
  BSTR v22; // [rsp+F8h] [rbp+7Fh] BYREF

  v4 = a3;
  VariantInit(&pvarg);
  VariantInit(&v19);
  VariantInit(&v18);
  v6 = SysAllocString(L"DeletePortMapping");
  v22 = v6;
  v7 = v6;
  if ( !a2 )
  {
    v8 = -2147024809;
LABEL_22:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
    goto LABEL_25;
  }
  if ( !v6 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
    VariantClear(&v18);
    VariantClear(&v19);
    VariantClear(&pvarg);
    return 2147942414LL;
  }
  pvarg.llVal = (LONGLONG)SafeArrayCreateVector(0xCu, 0, 3u);
  if ( !pvarg.llVal )
  {
    v8 = -2147024882;
    EventWriteError0(0x100000, L"InitActionParams returned 0x%x", 2147942414LL);
    goto LABEL_22;
  }
  rgIndices = 0;
  pvarg.vt = 8204;
  for ( i = 0; i < 3; i = ++rgIndices )
  {
    VariantInit(&pv);
    switch ( rgIndices )
    {
      case 0:
        v10 = &word_180087660;
        goto LABEL_15;
      case 1:
        pv.iVal = v4;
        pv.vt = 18;
        goto LABEL_18;
      case 2:
        v10 = L"UDP";
LABEL_15:
        pv.vt = 8;
        llVal = (LONGLONG)SysAllocString(v10);
        pv.llVal = llVal;
        goto LABEL_16;
    }
    llVal = pv.llVal;
LABEL_16:
    if ( pv.vt == 8 && !llVal )
    {
      EventWriteError0(0x100000, L"Failed to allocate string. iteration:%u");
      VariantClear(&pv);
      v8 = -2147024882;
      goto LABEL_22;
    }
LABEL_18:
    v8 = SafeArrayPutElement(pvarg.parray, &rgIndices, &pv);
    VariantClear(&pv);
    VariantInit(&pv);
    if ( v8 < 0 )
    {
      EventWriteError0(0x100000, L"SafeArrayPutElement returned 0x%x", (unsigned int)v8);
      VariantClear(&pv);
      goto LABEL_22;
    }
    VariantClear(&pv);
  }
  TickCount64 = GetTickCount64();
  InvokeAction = a2->lpVtbl->InvokeAction;
  v20 = pvarg;
  v8 = ((__int64 (__fastcall *)(struct IUPnPService *, OLECHAR *, VARIANTARG *, VARIANTARG *, VARIANTARG *))InvokeAction)(
         a2,
         v7,
         &v20,
         &v19,
         &v18);
  v14 = GetTickCount64();
  *((_DWORD *)this + 41) = v8;
  *((_BYTE *)this + 156) = 1;
  *((_DWORD *)this + 40) = v14 - TickCount64;
  if ( v8 >= 0 )
  {
    EventWrite0(0x100000, L"Port mapping for %u deleted successfully.", v4);
    goto LABEL_22;
  }
  EventWriteError0(0x100000, L"DeletePortMapping action returned 0x%x", (unsigned int)v8);
  SysFreeString(v7);
LABEL_25:
  VariantClear(&v18);
  VariantClear(&v19);
  VariantClear(&pvarg);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180029978  mov     [rsp-8+arg_0], rbx
0x18002997d  mov     [rsp-8+arg_10], rsi
0x180029982  push    rbp
0x180029983  push    rdi
0x180029984  push    r13
0x180029986  push    r14
0x180029988  push    r15
0x18002998a  lea     rbp, [rsp-37h]
0x18002998f  sub     rsp, 0B0h
0x180029996  mov     r13, rcx
0x180029999  movzx   r14d, r8w
0x18002999d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800299a1  mov     r15, rdx
0x1800299a4  call    cs:__imp_VariantInit
0x1800299ab  nop     dword ptr [rax+rax+00h]
0x1800299b0  lea     rcx, [rbp+57h+var_58]; pvarg
0x1800299b4  call    cs:__imp_VariantInit
0x1800299bb  nop     dword ptr [rax+rax+00h]
0x1800299c0  lea     rcx, [rbp+57h+var_70]; pvarg
0x1800299c4  call    cs:__imp_VariantInit
0x1800299cb  nop     dword ptr [rax+rax+00h]
0x1800299d0  lea     rcx, aDeleteportmapp_1; "DeletePortMapping"
0x1800299d7  call    cs:__imp_SysAllocString
0x1800299de  nop     dword ptr [rax+rax+00h]
0x1800299e3  mov     [rbp+57h+arg_18], rax
0x1800299e7  mov     rbx, rax
0x1800299ea  test    r15, r15
0x1800299ed  jnz     short loc_1800299F9
0x1800299ef  mov     esi, 80070057h
0x1800299f4  jmp     loc_180029B74
0x1800299f9  test    rbx, rbx
0x1800299fc  jz      loc_180029C5B
0x180029a02  mov     ecx, 0Ch; vt
0x180029a07  xor     edx, edx; lLbound
0x180029a09  lea     r8d, [rcx-9]; cElements
0x180029a0d  call    cs:__imp_SafeArrayCreateVector
0x180029a14  nop     dword ptr [rax+rax+00h]
0x180029a19  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180029a1d  test    rax, rax
0x180029a20  jnz     short loc_180029A40
0x180029a22  mov     esi, 8007000Eh
0x180029a27  lea     rdx, aInitactionpara; "InitActionParams returned 0x%x"
0x180029a2e  mov     r8d, esi
0x180029a31  mov     ecx, 100000h
0x180029a36  call    EventWriteError0
0x180029a3b  jmp     loc_180029B74
0x180029a40  mov     eax, 200Ch
0x180029a45  mov     [rbp+57h+rgIndices], 0
0x180029a4c  mov     word ptr [rbp+57h+pvarg], ax
0x180029a50  xor     eax, eax
0x180029a52  lea     edi, [rax+8]
0x180029a55  cmp     eax, 3
0x180029a58  jge     loc_180029B82
0x180029a5e  lea     rcx, [rbp+57h+pv]; pvarg
0x180029a62  call    cs:__imp_VariantInit
0x180029a69  nop     dword ptr [rax+rax+00h]
0x180029a6e  mov     r8d, [rbp+57h+rgIndices]
0x180029a72  mov     ecx, r8d
0x180029a75  test    r8d, r8d
0x180029a78  jz      short loc_180029AA3
0x180029a7a  sub     ecx, 1
0x180029a7d  jz      short loc_180029A93
0x180029a7f  cmp     ecx, 1
0x180029a82  jnz     short loc_180029A8D
0x180029a84  lea     rcx, aUdp; "UDP"
0x180029a8b  jmp     short loc_180029AAA
0x180029a8d  mov     rax, qword ptr [rbp+57h+pv+8]
0x180029a91  jmp     short loc_180029AC2
0x180029a93  mov     eax, 12h
0x180029a98  mov     word ptr [rbp+57h+pv+8], r14w
0x180029a9d  mov     word ptr [rbp+57h+pv], ax
0x180029aa1  jmp     short loc_180029ACD
0x180029aa3  lea     rcx, word_180087660; psz
0x180029aaa  mov     word ptr [rbp+57h+pv], di
0x180029aae  call    cs:__imp_SysAllocString
0x180029ab5  nop     dword ptr [rax+rax+00h]
0x180029aba  mov     r8d, [rbp+57h+rgIndices]
0x180029abe  mov     qword ptr [rbp+57h+pv+8], rax
0x180029ac2  cmp     word ptr [rbp+57h+pv], di
0x180029ac6  jnz     short loc_180029ACD
0x180029ac8  test    rax, rax
0x180029acb  jz      short loc_180029B28
0x180029acd  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x180029ad1  lea     r8, [rbp+57h+pv]; pv
0x180029ad5  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180029ad9  call    cs:__imp_SafeArrayPutElement
0x180029ae0  nop     dword ptr [rax+rax+00h]
0x180029ae5  lea     rcx, [rbp+57h+pv]; pvarg
0x180029ae9  mov     esi, eax
0x180029aeb  call    cs:__imp_VariantClear
0x180029af2  nop     dword ptr [rax+rax+00h]
0x180029af7  lea     rcx, [rbp+57h+pv]; pvarg
0x180029afb  call    cs:__imp_VariantInit
0x180029b02  nop     dword ptr [rax+rax+00h]
0x180029b07  test    esi, esi
0x180029b09  js      short loc_180029B50
0x180029b0b  lea     rcx, [rbp+57h+pv]; pvarg
0x180029b0f  call    cs:__imp_VariantClear
0x180029b16  nop     dword ptr [rax+rax+00h]
0x180029b1b  mov     eax, [rbp+57h+rgIndices]
0x180029b1e  inc     eax
0x180029b20  mov     [rbp+57h+rgIndices], eax
0x180029b23  jmp     loc_180029A55
0x180029b28  lea     rdx, aFailedToAlloca_0; "Failed to allocate string. iteration:%u"
0x180029b2f  mov     ecx, 100000h
0x180029b34  call    EventWriteError0
0x180029b39  lea     rcx, [rbp+57h+pv]; pvarg
0x180029b3d  call    cs:__imp_VariantClear
0x180029b44  nop     dword ptr [rax+rax+00h]
0x180029b49  mov     esi, 8007000Eh
0x180029b4e  jmp     short loc_180029B74
0x180029b50  mov     r8d, esi
0x180029b53  lea     rdx, aSafearrayputel; "SafeArrayPutElement returned 0x%x"
0x180029b5a  mov     ecx, 100000h
0x180029b5f  call    EventWriteError0
0x180029b64  lea     rcx, [rbp+57h+pv]; pvarg
0x180029b68  call    cs:__imp_VariantClear
0x180029b6f  nop     dword ptr [rax+rax+00h]
0x180029b74  lea     rcx, [rbp+57h+arg_18]
0x180029b78  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029b7d  jmp     loc_180029C13
0x180029b82  call    cs:__imp_GetTickCount64
0x180029b89  nop     dword ptr [rax+rax+00h]
0x180029b8e  mov     rcx, [r15]
0x180029b91  lea     r9, [rbp+57h+var_58]
0x180029b95  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180029b99  lea     r8, [rbp+57h+var_40]
0x180029b9d  mov     rdi, rax
0x180029ba0  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180029ba5  mov     rdx, rbx
0x180029ba8  mov     rax, [rcx+40h]
0x180029bac  lea     rcx, [rbp+57h+var_70]
0x180029bb0  mov     [rsp+0D0h+var_B0], rcx
0x180029bb5  mov     rcx, r15
0x180029bb8  movaps  [rbp+57h+var_40], xmm0
0x180029bbc  movsd   [rbp+57h+var_30], xmm1
0x180029bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bc6  mov     esi, eax
0x180029bc8  call    cs:__imp_GetTickCount64
0x180029bcf  nop     dword ptr [rax+rax+00h]
0x180029bd4  mov     [r13+0A4h], esi
0x180029bdb  mov     ecx, 100000h
0x180029be0  sub     eax, edi
0x180029be2  mov     byte ptr [r13+9Ch], 1
0x180029bea  mov     [r13+0A0h], eax
0x180029bf1  test    esi, esi
0x180029bf3  jns     short loc_180029C47
0x180029bf5  mov     r8d, esi
0x180029bf8  lea     rdx, aDeleteportmapp_0; "DeletePortMapping action returned 0x%x"
0x180029bff  call    EventWriteError0
0x180029c04  mov     rcx, rbx; bstrString
0x180029c07  call    cs:__imp_SysFreeString
0x180029c0e  nop     dword ptr [rax+rax+00h]
0x180029c13  lea     rcx, [rbp+57h+var_70]; pvarg
0x180029c17  call    cs:__imp_VariantClear
0x180029c1e  nop     dword ptr [rax+rax+00h]
0x180029c23  lea     rcx, [rbp+57h+var_58]; pvarg
0x180029c27  call    cs:__imp_VariantClear
0x180029c2e  nop     dword ptr [rax+rax+00h]
0x180029c33  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180029c37  call    cs:__imp_VariantClear
0x180029c3e  nop     dword ptr [rax+rax+00h]
0x180029c43  mov     eax, esi
0x180029c45  jmp     short loc_180029C99
0x180029c47  mov     r8d, r14d
0x180029c4a  lea     rdx, aPortMappingFor; "Port mapping for %u deleted successfull"...
0x180029c51  call    EventWrite0
0x180029c56  jmp     loc_180029B74
0x180029c5b  lea     rcx, [rbp+57h+arg_18]
0x180029c5f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029c64  lea     rcx, [rbp+57h+var_70]; pvarg
0x180029c68  call    cs:__imp_VariantClear
0x180029c6f  nop     dword ptr [rax+rax+00h]
0x180029c74  lea     rcx, [rbp+57h+var_58]; pvarg
0x180029c78  call    cs:__imp_VariantClear
0x180029c7f  nop     dword ptr [rax+rax+00h]
0x180029c84  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180029c88  call    cs:__imp_VariantClear
0x180029c8f  nop     dword ptr [rax+rax+00h]
0x180029c94  mov     eax, 8007000Eh
0x180029c99  lea     r11, [rsp+0D0h+var_20]
0x180029ca1  mov     rbx, [r11+30h]
0x180029ca5  mov     rsi, [r11+40h]
0x180029ca9  mov     rsp, r11
0x180029cac  pop     r15
0x180029cae  pop     r14
0x180029cb0  pop     r13
0x180029cb2  pop     rdi
0x180029cb3  pop     rbp
0x180029cb4  retn
```
