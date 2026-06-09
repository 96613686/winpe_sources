# TeredoUPnP::DeletePortMapping(IUPnPService *,ushort)

- ea: `0x180029968`
- end: `0x180029ca6`
- name: `?DeletePortMapping@TeredoUPnP@@AEAAJPEAUIUPnPService@@G@Z`
- size: `830`
- prototype: `__int64 __fastcall(TeredoUPnP *__hidden this, struct IUPnPService *, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180028534`

## callees

- `0x18000d7b0`
- `0x1800190e0`
- `0x180029968`
- `0x180043374`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029b72`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029bb8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029b72`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180029bb8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800299c7`
- `OLEAUT32!__imp_SysAllocString` at `0x180029a9e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800299c7`
- `OLEAUT32!__imp_SysAllocString` at `0x180029a9e`
- `OLEAUT32!__imp_SysFreeString` at `0x180029bf7`
- `OLEAUT32!__imp_SysFreeString` at `0x180029bf7`
- `OLEAUT32!__imp_VariantInit` at `0x180029994`
- `OLEAUT32!__imp_VariantInit` at `0x1800299a4`
- `OLEAUT32!__imp_VariantInit` at `0x1800299b4`
- `OLEAUT32!__imp_VariantInit` at `0x180029a52`
- `OLEAUT32!__imp_VariantInit` at `0x180029aeb`
- `OLEAUT32!__imp_VariantInit` at `0x180029994`
- `OLEAUT32!__imp_VariantInit` at `0x1800299a4`
- `OLEAUT32!__imp_VariantInit` at `0x1800299b4`
- `OLEAUT32!__imp_VariantInit` at `0x180029a52`
- `OLEAUT32!__imp_VariantInit` at `0x180029aeb`
- `OLEAUT32!__imp_VariantClear` at `0x180029adb`
- `OLEAUT32!__imp_VariantClear` at `0x180029aff`
- `OLEAUT32!__imp_VariantClear` at `0x180029b2d`
- `OLEAUT32!__imp_VariantClear` at `0x180029b58`
- `OLEAUT32!__imp_VariantClear` at `0x180029c07`
- `OLEAUT32!__imp_VariantClear` at `0x180029c17`
- `OLEAUT32!__imp_VariantClear` at `0x180029c27`
- `OLEAUT32!__imp_VariantClear` at `0x180029c58`
- `OLEAUT32!__imp_VariantClear` at `0x180029c68`
- `OLEAUT32!__imp_VariantClear` at `0x180029c78`
- `OLEAUT32!__imp_VariantClear` at `0x180029adb`
- `OLEAUT32!__imp_VariantClear` at `0x180029aff`
- `OLEAUT32!__imp_VariantClear` at `0x180029b2d`
- `OLEAUT32!__imp_VariantClear` at `0x180029b58`
- `OLEAUT32!__imp_VariantClear` at `0x180029c07`
- `OLEAUT32!__imp_VariantClear` at `0x180029c17`
- `OLEAUT32!__imp_VariantClear` at `0x180029c27`
- `OLEAUT32!__imp_VariantClear` at `0x180029c58`
- `OLEAUT32!__imp_VariantClear` at `0x180029c68`
- `OLEAUT32!__imp_VariantClear` at `0x180029c78`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180029ac9`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180029ac9`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800299fd`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800299fd`

## string_xrefs

- `0x180029c3a`: `Port mapping for %u deleted successfully.`
- `0x1800299c0`: `DeletePortMapping`
- `0x180029be8`: `DeletePortMapping action returned 0x%x`

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
0x180029968  mov     [rsp-8+arg_0], rbx
0x18002996d  mov     [rsp-8+arg_10], rsi
0x180029972  push    rbp
0x180029973  push    rdi
0x180029974  push    r13
0x180029976  push    r14
0x180029978  push    r15
0x18002997a  lea     rbp, [rsp-37h]
0x18002997f  sub     rsp, 0B0h
0x180029986  mov     r13, rcx
0x180029989  movzx   r14d, r8w
0x18002998d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180029991  mov     r15, rdx
0x180029994  call    cs:__imp_VariantInit
0x18002999b  nop     dword ptr [rax+rax+00h]
0x1800299a0  lea     rcx, [rbp+57h+var_58]; pvarg
0x1800299a4  call    cs:__imp_VariantInit
0x1800299ab  nop     dword ptr [rax+rax+00h]
0x1800299b0  lea     rcx, [rbp+57h+var_70]; pvarg
0x1800299b4  call    cs:__imp_VariantInit
0x1800299bb  nop     dword ptr [rax+rax+00h]
0x1800299c0  lea     rcx, aDeleteportmapp_1; "DeletePortMapping"
0x1800299c7  call    cs:__imp_SysAllocString
0x1800299ce  nop     dword ptr [rax+rax+00h]
0x1800299d3  mov     [rbp+57h+arg_18], rax
0x1800299d7  mov     rbx, rax
0x1800299da  test    r15, r15
0x1800299dd  jnz     short loc_1800299E9
0x1800299df  mov     esi, 80070057h
0x1800299e4  jmp     loc_180029B64
0x1800299e9  test    rbx, rbx
0x1800299ec  jz      loc_180029C4B
0x1800299f2  mov     ecx, 0Ch; vt
0x1800299f7  xor     edx, edx; lLbound
0x1800299f9  lea     r8d, [rcx-9]; cElements
0x1800299fd  call    cs:__imp_SafeArrayCreateVector
0x180029a04  nop     dword ptr [rax+rax+00h]
0x180029a09  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180029a0d  test    rax, rax
0x180029a10  jnz     short loc_180029A30
0x180029a12  mov     esi, 8007000Eh
0x180029a17  lea     rdx, aInitactionpara; "InitActionParams returned 0x%x"
0x180029a1e  mov     r8d, esi
0x180029a21  mov     ecx, 100000h
0x180029a26  call    EventWriteError0
0x180029a2b  jmp     loc_180029B64
0x180029a30  mov     eax, 200Ch
0x180029a35  mov     [rbp+57h+rgIndices], 0
0x180029a3c  mov     word ptr [rbp+57h+pvarg], ax
0x180029a40  xor     eax, eax
0x180029a42  lea     edi, [rax+8]
0x180029a45  cmp     eax, 3
0x180029a48  jge     loc_180029B72
0x180029a4e  lea     rcx, [rbp+57h+pv]; pvarg
0x180029a52  call    cs:__imp_VariantInit
0x180029a59  nop     dword ptr [rax+rax+00h]
0x180029a5e  mov     r8d, [rbp+57h+rgIndices]
0x180029a62  mov     ecx, r8d
0x180029a65  test    r8d, r8d
0x180029a68  jz      short loc_180029A93
0x180029a6a  sub     ecx, 1
0x180029a6d  jz      short loc_180029A83
0x180029a6f  cmp     ecx, 1
0x180029a72  jnz     short loc_180029A7D
0x180029a74  lea     rcx, aUdp; "UDP"
0x180029a7b  jmp     short loc_180029A9A
0x180029a7d  mov     rax, qword ptr [rbp+57h+pv+8]
0x180029a81  jmp     short loc_180029AB2
0x180029a83  mov     eax, 12h
0x180029a88  mov     word ptr [rbp+57h+pv+8], r14w
0x180029a8d  mov     word ptr [rbp+57h+pv], ax
0x180029a91  jmp     short loc_180029ABD
0x180029a93  lea     rcx, word_180087660; psz
0x180029a9a  mov     word ptr [rbp+57h+pv], di
0x180029a9e  call    cs:__imp_SysAllocString
0x180029aa5  nop     dword ptr [rax+rax+00h]
0x180029aaa  mov     r8d, [rbp+57h+rgIndices]
0x180029aae  mov     qword ptr [rbp+57h+pv+8], rax
0x180029ab2  cmp     word ptr [rbp+57h+pv], di
0x180029ab6  jnz     short loc_180029ABD
0x180029ab8  test    rax, rax
0x180029abb  jz      short loc_180029B18
0x180029abd  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x180029ac1  lea     r8, [rbp+57h+pv]; pv
0x180029ac5  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180029ac9  call    cs:__imp_SafeArrayPutElement
0x180029ad0  nop     dword ptr [rax+rax+00h]
0x180029ad5  lea     rcx, [rbp+57h+pv]; pvarg
0x180029ad9  mov     esi, eax
0x180029adb  call    cs:__imp_VariantClear
0x180029ae2  nop     dword ptr [rax+rax+00h]
0x180029ae7  lea     rcx, [rbp+57h+pv]; pvarg
0x180029aeb  call    cs:__imp_VariantInit
0x180029af2  nop     dword ptr [rax+rax+00h]
0x180029af7  test    esi, esi
0x180029af9  js      short loc_180029B40
0x180029afb  lea     rcx, [rbp+57h+pv]; pvarg
0x180029aff  call    cs:__imp_VariantClear
0x180029b06  nop     dword ptr [rax+rax+00h]
0x180029b0b  mov     eax, [rbp+57h+rgIndices]
0x180029b0e  inc     eax
0x180029b10  mov     [rbp+57h+rgIndices], eax
0x180029b13  jmp     loc_180029A45
0x180029b18  lea     rdx, aFailedToAlloca_0; "Failed to allocate string. iteration:%u"
0x180029b1f  mov     ecx, 100000h
0x180029b24  call    EventWriteError0
0x180029b29  lea     rcx, [rbp+57h+pv]; pvarg
0x180029b2d  call    cs:__imp_VariantClear
0x180029b34  nop     dword ptr [rax+rax+00h]
0x180029b39  mov     esi, 8007000Eh
0x180029b3e  jmp     short loc_180029B64
0x180029b40  mov     r8d, esi
0x180029b43  lea     rdx, aSafearrayputel; "SafeArrayPutElement returned 0x%x"
0x180029b4a  mov     ecx, 100000h
0x180029b4f  call    EventWriteError0
0x180029b54  lea     rcx, [rbp+57h+pv]; pvarg
0x180029b58  call    cs:__imp_VariantClear
0x180029b5f  nop     dword ptr [rax+rax+00h]
0x180029b64  lea     rcx, [rbp+57h+arg_18]
0x180029b68  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029b6d  jmp     loc_180029C03
0x180029b72  call    cs:__imp_GetTickCount64
0x180029b79  nop     dword ptr [rax+rax+00h]
0x180029b7e  mov     rcx, [r15]
0x180029b81  lea     r9, [rbp+57h+var_58]
0x180029b85  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180029b89  lea     r8, [rbp+57h+var_40]
0x180029b8d  mov     rdi, rax
0x180029b90  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180029b95  mov     rdx, rbx
0x180029b98  mov     rax, [rcx+40h]
0x180029b9c  lea     rcx, [rbp+57h+var_70]
0x180029ba0  mov     [rsp+0D0h+var_B0], rcx
0x180029ba5  mov     rcx, r15
0x180029ba8  movaps  [rbp+57h+var_40], xmm0
0x180029bac  movsd   [rbp+57h+var_30], xmm1
0x180029bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bb6  mov     esi, eax
0x180029bb8  call    cs:__imp_GetTickCount64
0x180029bbf  nop     dword ptr [rax+rax+00h]
0x180029bc4  mov     [r13+0A4h], esi
0x180029bcb  mov     ecx, 100000h
0x180029bd0  sub     eax, edi
0x180029bd2  mov     byte ptr [r13+9Ch], 1
0x180029bda  mov     [r13+0A0h], eax
0x180029be1  test    esi, esi
0x180029be3  jns     short loc_180029C37
0x180029be5  mov     r8d, esi
0x180029be8  lea     rdx, aDeleteportmapp_0; "DeletePortMapping action returned 0x%x"
0x180029bef  call    EventWriteError0
0x180029bf4  mov     rcx, rbx; bstrString
0x180029bf7  call    cs:__imp_SysFreeString
0x180029bfe  nop     dword ptr [rax+rax+00h]
0x180029c03  lea     rcx, [rbp+57h+var_70]; pvarg
0x180029c07  call    cs:__imp_VariantClear
0x180029c0e  nop     dword ptr [rax+rax+00h]
0x180029c13  lea     rcx, [rbp+57h+var_58]; pvarg
0x180029c17  call    cs:__imp_VariantClear
0x180029c1e  nop     dword ptr [rax+rax+00h]
0x180029c23  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180029c27  call    cs:__imp_VariantClear
0x180029c2e  nop     dword ptr [rax+rax+00h]
0x180029c33  mov     eax, esi
0x180029c35  jmp     short loc_180029C89
0x180029c37  mov     r8d, r14d
0x180029c3a  lea     rdx, aPortMappingFor; "Port mapping for %u deleted successfull"...
0x180029c41  call    EventWrite0
0x180029c46  jmp     loc_180029B64
0x180029c4b  lea     rcx, [rbp+57h+arg_18]
0x180029c4f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029c54  lea     rcx, [rbp+57h+var_70]; pvarg
0x180029c58  call    cs:__imp_VariantClear
0x180029c5f  nop     dword ptr [rax+rax+00h]
0x180029c64  lea     rcx, [rbp+57h+var_58]; pvarg
0x180029c68  call    cs:__imp_VariantClear
0x180029c6f  nop     dword ptr [rax+rax+00h]
0x180029c74  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180029c78  call    cs:__imp_VariantClear
0x180029c7f  nop     dword ptr [rax+rax+00h]
0x180029c84  mov     eax, 8007000Eh
0x180029c89  lea     r11, [rsp+0D0h+var_20]
0x180029c91  mov     rbx, [r11+30h]
0x180029c95  mov     rsi, [r11+40h]
0x180029c99  mov     rsp, r11
0x180029c9c  pop     r15
0x180029c9e  pop     r14
0x180029ca0  pop     r13
0x180029ca2  pop     rdi
0x180029ca3  pop     rbp
0x180029ca4  retn
```
