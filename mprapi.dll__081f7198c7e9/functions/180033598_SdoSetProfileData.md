# SdoSetProfileData

- ea: `0x180033598`
- end: `0x18003378d`
- name: `SdoSetProfileData`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002a684`

## callees

- `0x180033598`
- `0x180033794`
- `0x180035430`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003361d`
- `OLEAUT32!__imp_VariantInit` at `0x180033627`
- `OLEAUT32!__imp_VariantInit` at `0x180033631`
- `OLEAUT32!__imp_VariantInit` at `0x18003361d`
- `OLEAUT32!__imp_VariantInit` at `0x180033627`
- `OLEAUT32!__imp_VariantInit` at `0x180033631`
- `OLEAUT32!__imp_VariantClear` at `0x180033735`
- `OLEAUT32!__imp_VariantClear` at `0x18003373f`
- `OLEAUT32!__imp_VariantClear` at `0x180033749`
- `OLEAUT32!__imp_VariantClear` at `0x180033735`
- `OLEAUT32!__imp_VariantClear` at `0x18003373f`
- `OLEAUT32!__imp_VariantClear` at `0x180033749`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800336bf`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800336bf`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800336da`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800336da`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800336ff`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800336ff`

## pseudocode

```c
__int64 __fastcall SdoSetProfileData(SAFEARRAYBOUND a1, struct _SDO_PROFILE *a2, char a3)
{
  signed int v5; // edi
  SAFEARRAY *v6; // rsi
  HRESULT v7; // ebx
  __int64 result; // rax
  VARIANTARG v9; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v10[2]; // [rsp+38h] [rbp-31h]
  int v11; // [rsp+40h] [rbp-29h]
  int v12; // [rsp+44h] [rbp-25h]
  int v13; // [rsp+48h] [rbp-21h]
  VARIANTARG pvarg; // [rsp+58h] [rbp-11h] BYREF
  VARIANTARG v15; // [rsp+70h] [rbp+7h] BYREF
  __int128 pv; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v17; // [rsp+98h] [rbp+2Fh]
  SAFEARRAYBOUND rgsabound; // [rsp+D0h] [rbp+67h] BYREF
  LONG rgIndices; // [rsp+E0h] [rbp+77h] BYREF

  rgsabound = a1;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v9, 0, sizeof(v9));
  memset(&v15, 0, sizeof(v15));
  if ( (_QWORD)xmmword_180078D60 )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSdoWrapperTemplateFunc)(
      gSdoWrapperEtwContext,
      xmmword_180078D60,
      L"SdoSetProfileData: entered\n");
  if ( (a3 & 4) != 0 || (a3 & 8) != 0 )
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SdoSetProfileToForceEncryption)(a1, a2, (a3 & 4) != 0);
  VariantInit(&pvarg);
  VariantInit(&v9);
  VariantInit(&v15);
  v9.lVal = 14;
  pvarg.vt = 3;
  v9.vt = 3;
  v10[0] = 3;
  v10[1] = 4;
  if ( (a3 & 1) != 0 )
  {
    pvarg.lVal = 2;
    v5 = 4;
    v11 = 9;
    v12 = 10;
  }
  else
  {
    pvarg.lVal = 1;
    v5 = 5;
    v11 = 1;
    v12 = 9;
    v13 = 10;
  }
  rgIndices = 0;
  v15.vt = 8204;
  rgsabound.cElements = v5;
  v17 = 0;
  pv = 0;
  rgsabound.lLbound = 0;
  v6 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  rgIndices = 0;
  while ( 1 )
  {
    if ( SafeArrayGetElement(v6, &rgIndices, &pv) >= 0 )
    {
      LOWORD(pv) = 3;
      DWORD2(pv) = v10[rgIndices];
      v7 = SafeArrayPutElement(v6, &rgIndices, &pv);
      if ( v7 < 0 )
        break;
    }
    if ( ++rgIndices >= v5 )
    {
      v15.llVal = (LONGLONG)v6;
      v7 = SdoWrapSetProfileValues(a2, &pvarg, &v9, &v15);
      break;
    }
  }
  VariantClear(&pvarg);
  VariantClear(&v9);
  VariantClear(&v15);
  result = (unsigned __int16)v7;
  if ( (v7 & 0x1FFF0000) != 0x70000 )
    return (unsigned int)v7;
  return result;
}

```

## disassembly

```asm
0x180033598  mov     [rsp-8+arg_8], rbx
0x18003359d  mov     qword ptr [rsp-8+rgsabound.cElements], rcx
0x1800335a2  push    rbp
0x1800335a3  push    rsi
0x1800335a4  push    rdi
0x1800335a5  push    r14
0x1800335a7  push    r15
0x1800335a9  lea     rbp, [rsp-37h]
0x1800335ae  sub     rsp, 0A0h
0x1800335b5  xor     eax, eax
0x1800335b7  xorps   xmm0, xmm0
0x1800335ba  mov     r14, rdx
0x1800335bd  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800335c1  mov     rdx, qword ptr cs:xmmword_180078D60
0x1800335c8  xorps   xmm1, xmm1
0x1800335cb  mov     qword ptr [rbp+57h+var_A0+10h], rax
0x1800335cf  mov     ebx, r8d
0x1800335d2  mov     qword ptr [rbp+57h+var_50+10h], rax
0x1800335d6  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800335da  movups  xmmword ptr [rbp+57h+var_A0], xmm1
0x1800335de  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1800335e2  test    rdx, rdx
0x1800335e5  jz      short loc_180033601
0x1800335e7  mov     rcx, cs:gSdoWrapperEtwContext
0x1800335ee  lea     r8, aSdosetprofiled; "SdoSetProfileData: entered\n"
0x1800335f5  mov     rax, cs:gSdoWrapperTemplateFunc
0x1800335fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033601  mov     eax, ebx
0x180033603  mov     esi, 4
0x180033608  and     eax, esi
0x18003360a  jnz     loc_180033765
0x180033610  test    bl, 8
0x180033613  jnz     loc_180033765
0x180033619  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003361d  call    cs:__imp_VariantInit
0x180033623  lea     rcx, [rbp+57h+var_A0]; pvarg
0x180033627  call    cs:__imp_VariantInit
0x18003362d  lea     rcx, [rbp+57h+var_50]; pvarg
0x180033631  call    cs:__imp_VariantInit
0x180033637  mov     dword ptr [rbp+57h+var_A0+8], 0Eh
0x18003363e  lea     r15d, [rsi-1]
0x180033642  mov     word ptr [rbp+57h+pvarg], r15w
0x180033647  mov     word ptr [rbp+57h+var_A0], r15w
0x18003364c  mov     [rbp+57h+var_88], r15d
0x180033650  mov     [rbp+57h+var_84], esi
0x180033653  test    bl, 1
0x180033656  jz      short loc_180033671
0x180033658  mov     dword ptr [rbp+57h+pvarg+8], 2
0x18003365f  mov     edi, esi
0x180033661  mov     [rbp+57h+var_80], 9
0x180033668  mov     [rbp+57h+var_7C], 0Ah
0x18003366f  jmp     short loc_180033692
0x180033671  mov     dword ptr [rbp+57h+pvarg+8], 1
0x180033678  mov     edi, 5
0x18003367d  mov     [rbp+57h+var_80], 1
0x180033684  mov     [rbp+57h+var_7C], 9
0x18003368b  mov     [rbp+57h+var_78], 0Ah
0x180033692  mov     eax, 200Ch
0x180033697  mov     [rbp+57h+rgIndices], 0
0x18003369e  mov     word ptr [rbp+57h+var_50], ax
0x1800336a2  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1800336a6  xor     eax, eax
0x1800336a8  mov     [rbp+57h+rgsabound.cElements], edi
0x1800336ab  xorps   xmm0, xmm0
0x1800336ae  mov     [rbp+57h+var_28], rax
0x1800336b2  movups  [rbp+57h+pv], xmm0
0x1800336b6  mov     [rbp+57h+rgsabound.lLbound], eax
0x1800336b9  lea     ecx, [rax+0Ch]; vt
0x1800336bc  lea     edx, [rax+1]; cDims
0x1800336bf  call    cs:__imp_SafeArrayCreate
0x1800336c5  mov     rsi, rax
0x1800336c8  mov     [rbp+57h+rgIndices], 0
0x1800336cf  lea     r8, [rbp+57h+pv]; pv
0x1800336d3  mov     rcx, rsi; psa
0x1800336d6  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x1800336da  call    cs:__imp_SafeArrayGetElement
0x1800336e0  test    eax, eax
0x1800336e2  js      short loc_18003370B
0x1800336e4  movsxd  rax, [rbp+57h+rgIndices]
0x1800336e8  lea     r8, [rbp+57h+pv]; pv
0x1800336ec  mov     word ptr [rbp+57h+pv], r15w
0x1800336f1  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x1800336f5  mov     ecx, [rbp+rax*4+57h+var_88]
0x1800336f9  mov     dword ptr [rbp+57h+pv+8], ecx
0x1800336fc  mov     rcx, rsi; psa
0x1800336ff  call    cs:__imp_SafeArrayPutElement
0x180033705  mov     ebx, eax
0x180033707  test    eax, eax
0x180033709  js      short loc_180033731
0x18003370b  mov     eax, [rbp+57h+rgIndices]
0x18003370e  inc     eax
0x180033710  mov     [rbp+57h+rgIndices], eax
0x180033713  cmp     eax, edi
0x180033715  jl      short loc_1800336CF
0x180033717  lea     r9, [rbp+57h+var_50]; struct tagVARIANT *
0x18003371b  mov     qword ptr [rbp+57h+var_50+8], rsi
0x18003371f  lea     r8, [rbp+57h+var_A0]; struct tagVARIANT *
0x180033723  mov     rcx, r14; struct _SDO_PROFILE *
0x180033726  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x18003372a  call    SdoWrapSetProfileValues
0x18003372f  mov     ebx, eax
0x180033731  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180033735  call    cs:__imp_VariantClear
0x18003373b  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18003373f  call    cs:__imp_VariantClear
0x180033745  lea     rcx, [rbp+57h+var_50]; pvarg
0x180033749  call    cs:__imp_VariantClear
0x18003374f  mov     ecx, ebx
0x180033751  movzx   eax, bx
0x180033754  and     ecx, 1FFF0000h
0x18003375a  cmp     ecx, 70000h
0x180033760  cmovnz  eax, ebx
0x180033763  jmp     short loc_180033776
0x180033765  xor     r8d, r8d
0x180033768  mov     rdx, r14
0x18003376b  test    eax, eax
0x18003376d  setnz   r8b
0x180033771  call    SdoSetProfileToForceEncryption
0x180033776  mov     rbx, [rsp+0C0h+arg_8]
0x18003377e  add     rsp, 0A0h
0x180033785  pop     r15
0x180033787  pop     r14
0x180033789  pop     rdi
0x18003378a  pop     rsi
0x18003378b  pop     rbp
0x18003378c  retn
```
