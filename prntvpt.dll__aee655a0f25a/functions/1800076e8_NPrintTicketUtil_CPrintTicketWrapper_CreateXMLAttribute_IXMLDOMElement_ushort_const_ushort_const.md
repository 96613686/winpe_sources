# NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(IXMLDOMElement *,ushort const *,ushort const *)

- ea: `0x1800076e8`
- end: `0x1800077a6`
- name: `?CreateXMLAttribute@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1@Z`
- size: `190`
- prototype: `int(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, struct IXMLDOMElement *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003c20`
- `0x180006130`
- `0x180006b10`
- `0x180006c74`
- `0x1800077f0`
- `0x180007a04`
- `0x180008acc`
- `0x180009da8`
- `0x18000e084`
- `0x18001c060`
- `0x18001c2b0`

## callees

- `0x1800076e8`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007719`
- `OLEAUT32!__imp_SysAllocString` at `0x180007719`
- `OLEAUT32!__imp_VariantInit` at `0x18000773b`
- `OLEAUT32!__imp_VariantInit` at `0x18000773b`
- `OLEAUT32!__imp_VariantClear` at `0x180007787`
- `OLEAUT32!__imp_VariantClear` at `0x180007787`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::CreateXMLAttribute(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned int v6; // ebx
  BSTR v7; // rsi
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  HRESULT (__stdcall *setAttribute)(IXMLDOMElement *, BSTR, VARIANT); // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  __int128 v12; // [rsp+40h] [rbp-28h] BYREF
  IRecordInfo *pRecInfo; // [rsp+50h] [rbp-18h]

  if ( a2 && a3 && a4 )
  {
    v7 = SysAllocString(a4);
    if ( v7 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      pvarg.llVal = (LONGLONG)v7;
      pvarg.vt = 8;
      lpVtbl = a2->lpVtbl;
      pRecInfo = pvarg.pRecInfo;
      setAttribute = lpVtbl->setAttribute;
      v12 = *(_OWORD *)&pvarg.vt;
      v6 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const unsigned __int16 *, __int128 *))setAttribute)(
             a2,
             a3,
             &v12);
      VariantClear(&pvarg);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x1800076e8  mov     [rsp+arg_0], rbx
0x1800076ed  mov     [rsp+arg_8], rsi
0x1800076f2  push    rdi
0x1800076f3  sub     rsp, 60h
0x1800076f7  mov     rbx, r8
0x1800076fa  mov     rdi, rdx
0x1800076fd  test    rdx, rdx
0x180007700  jnz     short loc_18000770C
0x180007702  mov     ebx, 80070057h
0x180007707  jmp     loc_18000778D
0x18000770c  test    rbx, rbx
0x18000770f  jz      short loc_180007702
0x180007711  test    r9, r9
0x180007714  jz      short loc_180007702
0x180007716  mov     rcx, r9; psz
0x180007719  call    cs:__imp_SysAllocString
0x18000771f  mov     rsi, rax
0x180007722  test    rax, rax
0x180007725  jz      short loc_18000779F
0x180007727  xorps   xmm0, xmm0
0x18000772a  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18000772f  xor     eax, eax
0x180007731  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x180007736  mov     qword ptr [rsp+68h+pvarg+10h], rax
0x18000773b  call    cs:__imp_VariantInit
0x180007741  movsd   xmm1, qword ptr [rsp+68h+pvarg+10h]
0x180007747  lea     r8, [rsp+68h+var_28]
0x18000774c  mov     eax, 8
0x180007751  mov     qword ptr [rsp+68h+pvarg+8], rsi
0x180007756  mov     word ptr [rsp+68h+pvarg], ax
0x18000775b  mov     rdx, rbx
0x18000775e  mov     rax, [rdi]
0x180007761  mov     rcx, rdi
0x180007764  movups  xmm0, xmmword ptr [rsp+68h+pvarg]
0x180007769  movsd   [rsp+68h+var_18], xmm1
0x18000776f  mov     rax, [rax+168h]
0x180007776  movaps  [rsp+68h+var_28], xmm0
0x18000777b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007780  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180007785  mov     ebx, eax
0x180007787  call    cs:__imp_VariantClear
0x18000778d  mov     rsi, [rsp+68h+arg_8]
0x180007792  mov     eax, ebx
0x180007794  mov     rbx, [rsp+68h+arg_0]
0x180007799  add     rsp, 60h
0x18000779d  pop     rdi
0x18000779e  retn
0x18000779f  mov     ebx, 8007000Eh
0x1800077a4  jmp     short loc_18000778D
```
