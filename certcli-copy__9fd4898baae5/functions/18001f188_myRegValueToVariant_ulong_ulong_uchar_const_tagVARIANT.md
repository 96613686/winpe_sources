# myRegValueToVariant(ulong,ulong,uchar const *,tagVARIANT *)

- ea: `0x18001f188`
- end: `0x18001f259`
- name: `?myRegValueToVariant@@YAJKKPEBEPEAUtagVARIANT@@@Z`
- size: `209`
- prototype: `int(unsigned int, unsigned int, const unsigned __int8 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180028a64`

## callees

- `0x18001f188`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001f244`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f244`
- `OLEAUT32!__imp_VariantInit` at `0x18001f1ac`
- `OLEAUT32!__imp_VariantInit` at `0x18001f1ac`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001f1cb`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001f1cb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001f231`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001f231`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001f209`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18001f209`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001f1e5`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001f228`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001f1e5`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001f228`

## pseudocode

```c
__int64 __fastcall myRegValueToVariant(LONG a1, ULONG a2, const unsigned __int8 *a3, struct tagVARIANT *a4)
{
  SAFEARRAY *v7; // rdi
  unsigned int v8; // ebx
  ULONG i; // eax
  HRESULT v10; // eax
  LONG rgIndices; // [rsp+40h] [rbp+8h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp+18h] BYREF

  rgIndices = a1;
  rgsabound = 0;
  VariantInit(a4);
  rgsabound.cElements = a2;
  rgsabound.lLbound = 0;
  v7 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  if ( v7 )
  {
    v8 = 0;
    rgIndices = 0;
    for ( i = 0; i < rgsabound.cElements; i = ++rgIndices )
    {
      v10 = SafeArrayPutElement(v7, &rgIndices, (void *)&a3[i]);
      v8 = v10;
      if ( v10 )
      {
        CSPrintErrorLineFile(0x7EC019Au, v10);
        SafeArrayDestroy(v7);
        goto LABEL_9;
      }
    }
    a4->vt = 8209;
    a4->llVal = (LONGLONG)v7;
  }
  else
  {
    v8 = -2147024882;
    CSPrintErrorLineFile(0x7E7019Au, -2147024882);
  }
LABEL_9:
  SysFreeString(0);
  return v8;
}

```

## disassembly

```asm
0x18001f188  mov     [rsp+arg_8], rbx
0x18001f18d  mov     [rsp+rgIndices], ecx
0x18001f191  push    rbp
0x18001f192  push    rsi
0x18001f193  push    rdi
0x18001f194  sub     rsp, 20h
0x18001f198  mov     rcx, r9; pvarg
0x18001f19b  mov     qword ptr [rsp+38h+rgsabound.cElements], 0
0x18001f1a4  mov     rsi, r9
0x18001f1a7  mov     rbp, r8
0x18001f1aa  mov     ebx, edx
0x18001f1ac  call    cs:__imp_VariantInit
0x18001f1b2  mov     ecx, 11h; vt
0x18001f1b7  mov     [rsp+38h+rgsabound.cElements], ebx
0x18001f1bb  lea     r8, [rsp+38h+rgsabound]; rgsabound
0x18001f1c0  mov     [rsp+38h+rgsabound.lLbound], 0
0x18001f1c8  lea     edx, [rcx-10h]; cDims
0x18001f1cb  call    cs:__imp_SafeArrayCreate
0x18001f1d1  mov     rdi, rax
0x18001f1d4  test    rax, rax
0x18001f1d7  jnz     short loc_18001F1ED
0x18001f1d9  mov     ebx, 8007000Eh
0x18001f1de  mov     ecx, 7E7019Ah
0x18001f1e3  mov     edx, ebx
0x18001f1e5  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001f1eb  jmp     short loc_18001F242
0x18001f1ed  xor     ebx, ebx
0x18001f1ef  mov     [rsp+38h+rgIndices], ebx
0x18001f1f3  xor     eax, eax
0x18001f1f5  cmp     eax, [rsp+38h+rgsabound.cElements]
0x18001f1f9  jnb     short loc_18001F239
0x18001f1fb  mov     r8d, eax
0x18001f1fe  lea     rdx, [rsp+38h+rgIndices]; rgIndices
0x18001f203  add     r8, rbp; pv
0x18001f206  mov     rcx, rdi; psa
0x18001f209  call    cs:__imp_SafeArrayPutElement
0x18001f20f  mov     ebx, eax
0x18001f211  test    eax, eax
0x18001f213  jnz     short loc_18001F221
0x18001f215  mov     eax, [rsp+38h+rgIndices]
0x18001f219  inc     eax
0x18001f21b  mov     [rsp+38h+rgIndices], eax
0x18001f21f  jmp     short loc_18001F1F5
0x18001f221  mov     edx, eax
0x18001f223  mov     ecx, 7EC019Ah
0x18001f228  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001f22e  mov     rcx, rdi; psa
0x18001f231  call    cs:__imp_SafeArrayDestroy
0x18001f237  jmp     short loc_18001F242
0x18001f239  mov     word ptr [rsi], 2011h
0x18001f23e  mov     [rsi+8], rdi
0x18001f242  xor     ecx, ecx; bstrString
0x18001f244  call    cs:__imp_SysFreeString
0x18001f24a  mov     eax, ebx
0x18001f24c  mov     rbx, [rsp+38h+arg_8]
0x18001f251  add     rsp, 20h
0x18001f255  pop     rdi
0x18001f256  pop     rsi
0x18001f257  pop     rbp
0x18001f258  retn
```
