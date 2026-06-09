# SetStringArrayProperty(IWbemClassObject *,ushort const *,ATL::CComBSTR *,ulong)

- ea: `0x180035058`
- end: `0x180035140`
- name: `?SetStringArrayProperty@@YAJPEAUIWbemClassObject@@PEBGPEAVCComBSTR@ATL@@K@Z`
- size: `232`
- prototype: `__int64 __fastcall(struct IWbemClassObject *, const unsigned __int16 *, struct ATL::CComBSTR *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180035970`

## callees

- `0x180035058`
- `0x180037010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180035085`
- `OLEAUT32!__imp_VariantInit` at `0x180035085`
- `OLEAUT32!__imp_VariantClear` at `0x180035122`
- `OLEAUT32!__imp_VariantClear` at `0x180035122`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800350a1`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800350a1`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800350d6`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800350d6`

## pseudocode

```c
__int64 __fastcall SetStringArrayProperty(struct IWbemClassObject *a1, const unsigned __int16 *a2, void **a3)
{
  SAFEARRAY *v5; // rsi
  unsigned int v6; // ebx
  LONG v7; // edi
  HRESULT v8; // eax
  VARIANTARG pvarg; // [rsp+30h] [rbp-38h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+78h] [rbp+10h] BYREF
  LONG rgIndices; // [rsp+88h] [rbp+20h] BYREF

  rgsabound = (SAFEARRAYBOUND)a2;
  rgIndices = 0;
  VariantInit(&pvarg);
  rgsabound = (SAFEARRAYBOUND)1LL;
  v5 = SafeArrayCreate(8u, 1u, &rgsabound);
  if ( v5 )
  {
    v7 = 0;
    while ( v7 < 1 )
    {
      rgIndices = v7;
      v8 = SafeArrayPutElement(v5, &rgIndices, a3[v7++]);
      v6 = v8;
      if ( v8 < 0 )
        goto LABEL_8;
    }
    pvarg.llVal = (LONGLONG)v5;
    pvarg.vt = 8200;
    v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))a1->lpVtbl->Put)(
           a1,
           L"UNMServers",
           0,
           &pvarg,
           0);
  }
  else
  {
    v6 = -2147217402;
  }
LABEL_8:
  VariantClear(&pvarg);
  return v6;
}

```

## disassembly

```asm
0x180035058  mov     rax, rsp
0x18003505b  mov     [rax+8], rbx
0x18003505f  mov     [rax+18h], rsi
0x180035063  mov     [rax+20h], r9d
0x180035067  mov     [rax+10h], rdx
0x18003506b  push    rdi
0x18003506c  push    r14
0x18003506e  push    r15
0x180035070  sub     rsp, 50h
0x180035074  mov     r14, rcx
0x180035077  mov     dword ptr [rax+20h], 0
0x18003507e  lea     rcx, [rax-38h]; pvarg
0x180035082  mov     r15, r8
0x180035085  call    cs:__imp_VariantInit
0x18003508b  mov     ecx, 8; vt
0x180035090  mov     qword ptr [rsp+68h+rgsabound.cElements], 1
0x180035099  lea     r8, [rsp+68h+rgsabound]; rgsabound
0x18003509e  lea     edx, [rcx-7]; cDims
0x1800350a1  call    cs:__imp_SafeArrayCreate
0x1800350a7  mov     rsi, rax
0x1800350aa  test    rax, rax
0x1800350ad  jnz     short loc_1800350B6
0x1800350af  mov     ebx, 80041006h
0x1800350b4  jmp     short loc_18003511D
0x1800350b6  xor     edi, edi
0x1800350b8  cmp     edi, 1
0x1800350bb  jge     short loc_1800350E6
0x1800350bd  movsxd  r8, edi
0x1800350c0  lea     rdx, [rsp+68h+rgIndices]; rgIndices
0x1800350c8  mov     rcx, rsi; psa
0x1800350cb  mov     [rsp+68h+rgIndices], edi
0x1800350d2  mov     r8, [r15+r8*8]; pv
0x1800350d6  call    cs:__imp_SafeArrayPutElement
0x1800350dc  inc     edi
0x1800350de  mov     ebx, eax
0x1800350e0  test    eax, eax
0x1800350e2  jns     short loc_1800350B8
0x1800350e4  jmp     short loc_18003511D
0x1800350e6  mov     eax, 2008h
0x1800350eb  mov     qword ptr [rsp+68h+pvarg+8], rsi
0x1800350f0  mov     word ptr [rsp+68h+pvarg], ax
0x1800350f5  lea     r9, [rsp+68h+pvarg]
0x1800350fa  mov     rax, [r14]
0x1800350fd  lea     rdx, aUnmservers; "UNMServers"
0x180035104  xor     r8d, r8d
0x180035107  mov     [rsp+68h+var_48], 0
0x18003510f  mov     rcx, r14
0x180035112  mov     rax, [rax+28h]
0x180035116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003511b  mov     ebx, eax
0x18003511d  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180035122  call    cs:__imp_VariantClear
0x180035128  lea     r11, [rsp+68h+var_18]
0x18003512d  mov     eax, ebx
0x18003512f  mov     rbx, [r11+20h]
0x180035133  mov     rsi, [r11+30h]
0x180035137  mov     rsp, r11
0x18003513a  pop     r15
0x18003513c  pop     r14
0x18003513e  pop     rdi
0x18003513f  retn
```
