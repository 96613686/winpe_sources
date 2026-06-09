# NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)

- ea: `0x18000b0a0`
- end: `0x18000b16e`
- name: `?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z`
- size: `206`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *, int, int, struct IXMLDOMElement **)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c224`
- `0x18001beb8`
- `0x18001ca28`
- `0x18001fcc4`
- `0x180020710`
- `0x180020bd0`

## callees

- `0x18000b0a0`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000b0cb`
- `OLEAUT32!__imp_VariantInit` at `0x18000b0cb`
- `OLEAUT32!__imp_VariantClear` at `0x18000b15b`
- `OLEAUT32!__imp_VariantClear` at `0x18000b15b`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000b0fa`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000b0fa`

## string_xrefs

- `0x18000b124`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        LONG a5,
        int a6)
{
  HRESULT v10; // ebx
  VARIANTARG pvarg; // [rsp+50h] [rbp-48h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 22;
  pvarg.lVal = a5;
  v10 = VariantChangeType(&pvarg, &pvarg, 4u, 8u);
  if ( v10 >= 0 )
    v10 = (*(__int64 (__fastcall **)(NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *, LONGLONG, int, const char *, const wchar_t *, _QWORD))(*(_QWORD *)this + 8LL))(
            this,
            a2,
            a3,
            a4,
            pvarg.llVal,
            a6,
            L"http://www.w3.org/2001/XMLSchema",
            L"integer",
            0);
  VariantClear(&pvarg);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000b0a0  push    rbx
0x18000b0a2  push    rbp
0x18000b0a3  push    rsi
0x18000b0a4  push    rdi
0x18000b0a5  push    r14
0x18000b0a7  sub     rsp, 70h
0x18000b0ab  mov     rdi, rcx
0x18000b0ae  xorps   xmm0, xmm0
0x18000b0b1  xor     eax, eax
0x18000b0b3  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18000b0b8  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x18000b0bd  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x18000b0c2  mov     rsi, r9
0x18000b0c5  mov     rbp, r8
0x18000b0c8  mov     r14, rdx
0x18000b0cb  call    cs:__imp_VariantInit
0x18000b0d1  mov     eax, 16h
0x18000b0d6  lea     rdx, [rsp+98h+pvarg]; pvarSrc
0x18000b0db  mov     r9d, 8; vt
0x18000b0e1  mov     word ptr [rsp+98h+pvarg], ax
0x18000b0e6  mov     eax, [rsp+98h+arg_20]
0x18000b0ed  lea     rcx, [rsp+98h+pvarg]; pvargDest
0x18000b0f2  mov     dword ptr [rsp+98h+pvarg+8], eax
0x18000b0f6  lea     r8d, [r9-4]; wFlags
0x18000b0fa  call    cs:__imp_VariantChangeType
0x18000b100  mov     ebx, eax
0x18000b102  test    eax, eax
0x18000b104  js      short loc_18000B156
0x18000b106  mov     rax, [rdi]
0x18000b109  lea     rcx, aInteger; "integer"
0x18000b110  mov     [rsp+98h+var_58], 0
0x18000b119  mov     r9, rsi
0x18000b11c  mov     [rsp+98h+var_60], rcx
0x18000b121  mov     r8, rbp
0x18000b124  lea     rcx, aHttpWwwW3Org20_1; "http://www.w3.org/2001/XMLSchema"
0x18000b12b  mov     rdx, r14
0x18000b12e  mov     rax, [rax+8]
0x18000b132  mov     [rsp+98h+var_68], rcx
0x18000b137  mov     ecx, [rsp+98h+arg_28]
0x18000b13e  mov     [rsp+98h+var_70], ecx
0x18000b142  mov     rcx, qword ptr [rsp+98h+pvarg+8]
0x18000b147  mov     [rsp+98h+var_78], rcx
0x18000b14c  mov     rcx, rdi
0x18000b14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b154  mov     ebx, eax
0x18000b156  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18000b15b  call    cs:__imp_VariantClear
0x18000b161  mov     eax, ebx
0x18000b163  add     rsp, 70h
0x18000b167  pop     r14
0x18000b169  pop     rdi
0x18000b16a  pop     rsi
0x18000b16b  pop     rbp
0x18000b16c  pop     rbx
0x18000b16d  retn
```
