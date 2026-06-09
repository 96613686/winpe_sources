# NPrintTicketUtil::CPrintTicketWrapper::CreateParameterInitializer(ushort const *,ushort const *,int,IXMLDOMElement * *)

- ea: `0x18001c1e8`
- end: `0x18001c2a8`
- name: `?CreateParameterInitializer@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0HPEAPEAUIXMLDOMElement@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int, struct IXMLDOMElement **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b9b0`
- `0x180020f00`

## callees

- `0x180007a04`
- `0x18001c1e8`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001c218`
- `OLEAUT32!__imp_VariantInit` at `0x18001c218`
- `OLEAUT32!__imp_VariantClear` at `0x18001c289`
- `OLEAUT32!__imp_VariantClear` at `0x18001c289`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001c23e`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001c23e`

## string_xrefs

- `0x18001c25f`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001c26e`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::CreateParameterInitializer(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        const unsigned __int16 *a2,
        struct IXMLDOMElement *a3,
        LONG a4)
{
  int ParameterInitializer; // ebx
  VARIANTARG pvargDest; // [rsp+40h] [rbp-28h] BYREF

  memset(&pvargDest, 0, sizeof(pvargDest));
  if ( !a3 )
    return 2147942487LL;
  VariantInit(&pvargDest);
  pvargDest.lVal = a4;
  pvargDest.vt = 22;
  ParameterInitializer = VariantChangeType(&pvargDest, &pvargDest, 4u, 8u);
  if ( ParameterInitializer >= 0 )
    ParameterInitializer = NPrintTicketUtil::CPrintTicketWrapper::CreateParameterInitializer(
                             this,
                             L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                             a3,
                             pvargDest.bstrVal,
                             L"http://www.w3.org/2001/XMLSchema",
                             L"integer",
                             0);
  VariantClear(&pvargDest);
  return (unsigned int)ParameterInitializer;
}

```

## disassembly

```asm
0x18001c1e8  mov     r11, rsp
0x18001c1eb  mov     [r11+8], rbx
0x18001c1ef  mov     [r11+10h], rsi
0x18001c1f3  push    rdi
0x18001c1f4  sub     rsp, 60h
0x18001c1f8  xor     eax, eax
0x18001c1fa  xorps   xmm0, xmm0
0x18001c1fd  mov     ebx, r9d
0x18001c200  mov     rdi, r8
0x18001c203  mov     rsi, rcx
0x18001c206  movups  xmmword ptr [rsp+68h+pvargDest], xmm0
0x18001c20b  mov     [r11-18h], rax
0x18001c20f  test    r8, r8
0x18001c212  jz      short loc_18001C293
0x18001c214  lea     rcx, [r11-28h]; pvarg
0x18001c218  call    cs:__imp_VariantInit
0x18001c21e  mov     eax, 16h
0x18001c223  mov     dword ptr [rsp+68h+pvargDest+8], ebx
0x18001c227  lea     rdx, [rsp+68h+pvargDest]; pvarSrc
0x18001c22c  mov     word ptr [rsp+68h+pvargDest], ax
0x18001c231  lea     rcx, [rsp+68h+pvargDest]; pvargDest
0x18001c236  lea     r9d, [rax-0Eh]; vt
0x18001c23a  lea     r8d, [rax-12h]; wFlags
0x18001c23e  call    cs:__imp_VariantChangeType
0x18001c244  mov     ebx, eax
0x18001c246  test    eax, eax
0x18001c248  js      short loc_18001C284
0x18001c24a  mov     r9, qword ptr [rsp+68h+pvargDest+8]; unsigned __int16 *
0x18001c24f  lea     rax, aInteger; "integer"
0x18001c256  mov     [rsp+68h+var_38], 0; struct IXMLDOMElement **
0x18001c25f  lea     rdx, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001c266  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18001c26b  mov     r8, rdi; struct IXMLDOMElement *
0x18001c26e  lea     rax, aHttpWwwW3Org20_1; "http://www.w3.org/2001/XMLSchema"
0x18001c275  mov     rcx, rsi; this
0x18001c278  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001c27d  call    ?CreateParameterInitializer@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEBG0000PEAPEAUIXMLDOMElement@@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateParameterInitializer(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001c282  mov     ebx, eax
0x18001c284  lea     rcx, [rsp+68h+pvargDest]; pvarg
0x18001c289  call    cs:__imp_VariantClear
0x18001c28f  mov     eax, ebx
0x18001c291  jmp     short loc_18001C298
0x18001c293  mov     eax, 80070057h
0x18001c298  mov     rbx, [rsp+68h+arg_0]
0x18001c29d  mov     rsi, [rsp+68h+arg_8]
0x18001c2a2  add     rsp, 60h
0x18001c2a6  pop     rdi
0x18001c2a7  retn
```
