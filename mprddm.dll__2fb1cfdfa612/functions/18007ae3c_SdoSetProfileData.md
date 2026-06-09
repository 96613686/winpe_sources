# SdoSetProfileData

- ea: `0x18007ae3c`
- end: `0x18007b031`
- name: `SdoSetProfileData`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180024eb0`

## callees

- `0x18007ae3c`
- `0x18007b038`
- `0x18007c4f0`
- `0x18008e010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18007aec1`
- `OLEAUT32!__imp_VariantInit` at `0x18007aecb`
- `OLEAUT32!__imp_VariantInit` at `0x18007aed5`
- `OLEAUT32!__imp_VariantInit` at `0x18007aec1`
- `OLEAUT32!__imp_VariantInit` at `0x18007aecb`
- `OLEAUT32!__imp_VariantInit` at `0x18007aed5`
- `OLEAUT32!__imp_VariantClear` at `0x18007afd9`
- `OLEAUT32!__imp_VariantClear` at `0x18007afe3`
- `OLEAUT32!__imp_VariantClear` at `0x18007afed`
- `OLEAUT32!__imp_VariantClear` at `0x18007afd9`
- `OLEAUT32!__imp_VariantClear` at `0x18007afe3`
- `OLEAUT32!__imp_VariantClear` at `0x18007afed`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18007af63`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18007af63`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18007af7e`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18007af7e`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007afa3`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007afa3`

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
  if ( (_QWORD)xmmword_1800C9F60 )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSdoWrapperTemplateFunc)(
      gSdoWrapperEtwContext,
      xmmword_1800C9F60,
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
0x18007ae3c  mov     [rsp-8+arg_8], rbx
0x18007ae41  mov     qword ptr [rsp-8+rgsabound.cElements], rcx
0x18007ae46  push    rbp
0x18007ae47  push    rsi
0x18007ae48  push    rdi
0x18007ae49  push    r14
0x18007ae4b  push    r15
0x18007ae4d  lea     rbp, [rsp-37h]
0x18007ae52  sub     rsp, 0A0h
0x18007ae59  xor     eax, eax
0x18007ae5b  xorps   xmm0, xmm0
0x18007ae5e  mov     r14, rdx
0x18007ae61  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18007ae65  mov     rdx, qword ptr cs:xmmword_1800C9F60
0x18007ae6c  xorps   xmm1, xmm1
0x18007ae6f  mov     qword ptr [rbp+57h+var_A0+10h], rax
0x18007ae73  mov     ebx, r8d
0x18007ae76  mov     qword ptr [rbp+57h+var_50+10h], rax
0x18007ae7a  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18007ae7e  movups  xmmword ptr [rbp+57h+var_A0], xmm1
0x18007ae82  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18007ae86  test    rdx, rdx
0x18007ae89  jz      short loc_18007AEA5
0x18007ae8b  mov     rcx, cs:gSdoWrapperEtwContext
0x18007ae92  lea     r8, aSdosetprofiled; "SdoSetProfileData: entered\n"
0x18007ae99  mov     rax, cs:gSdoWrapperTemplateFunc
0x18007aea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aea5  mov     eax, ebx
0x18007aea7  mov     esi, 4
0x18007aeac  and     eax, esi
0x18007aeae  jnz     loc_18007B009
0x18007aeb4  test    bl, 8
0x18007aeb7  jnz     loc_18007B009
0x18007aebd  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18007aec1  call    cs:__imp_VariantInit
0x18007aec7  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18007aecb  call    cs:__imp_VariantInit
0x18007aed1  lea     rcx, [rbp+57h+var_50]; pvarg
0x18007aed5  call    cs:__imp_VariantInit
0x18007aedb  mov     dword ptr [rbp+57h+var_A0+8], 0Eh
0x18007aee2  lea     r15d, [rsi-1]
0x18007aee6  mov     word ptr [rbp+57h+pvarg], r15w
0x18007aeeb  mov     word ptr [rbp+57h+var_A0], r15w
0x18007aef0  mov     [rbp+57h+var_88], r15d
0x18007aef4  mov     [rbp+57h+var_84], esi
0x18007aef7  test    bl, 1
0x18007aefa  jz      short loc_18007AF15
0x18007aefc  mov     dword ptr [rbp+57h+pvarg+8], 2
0x18007af03  mov     edi, esi
0x18007af05  mov     [rbp+57h+var_80], 9
0x18007af0c  mov     [rbp+57h+var_7C], 0Ah
0x18007af13  jmp     short loc_18007AF36
0x18007af15  mov     dword ptr [rbp+57h+pvarg+8], 1
0x18007af1c  mov     edi, 5
0x18007af21  mov     [rbp+57h+var_80], 1
0x18007af28  mov     [rbp+57h+var_7C], 9
0x18007af2f  mov     [rbp+57h+var_78], 0Ah
0x18007af36  mov     eax, 200Ch
0x18007af3b  mov     [rbp+57h+rgIndices], 0
0x18007af42  mov     word ptr [rbp+57h+var_50], ax
0x18007af46  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x18007af4a  xor     eax, eax
0x18007af4c  mov     [rbp+57h+rgsabound.cElements], edi
0x18007af4f  xorps   xmm0, xmm0
0x18007af52  mov     [rbp+57h+var_28], rax
0x18007af56  movups  [rbp+57h+pv], xmm0
0x18007af5a  mov     [rbp+57h+rgsabound.lLbound], eax
0x18007af5d  lea     ecx, [rax+0Ch]; vt
0x18007af60  lea     edx, [rax+1]; cDims
0x18007af63  call    cs:__imp_SafeArrayCreate
0x18007af69  mov     rsi, rax
0x18007af6c  mov     [rbp+57h+rgIndices], 0
0x18007af73  lea     r8, [rbp+57h+pv]; pv
0x18007af77  mov     rcx, rsi; psa
0x18007af7a  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x18007af7e  call    cs:__imp_SafeArrayGetElement
0x18007af84  test    eax, eax
0x18007af86  js      short loc_18007AFAF
0x18007af88  movsxd  rax, [rbp+57h+rgIndices]
0x18007af8c  lea     r8, [rbp+57h+pv]; pv
0x18007af90  mov     word ptr [rbp+57h+pv], r15w
0x18007af95  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x18007af99  mov     ecx, [rbp+rax*4+57h+var_88]
0x18007af9d  mov     dword ptr [rbp+57h+pv+8], ecx
0x18007afa0  mov     rcx, rsi; psa
0x18007afa3  call    cs:__imp_SafeArrayPutElement
0x18007afa9  mov     ebx, eax
0x18007afab  test    eax, eax
0x18007afad  js      short loc_18007AFD5
0x18007afaf  mov     eax, [rbp+57h+rgIndices]
0x18007afb2  inc     eax
0x18007afb4  mov     [rbp+57h+rgIndices], eax
0x18007afb7  cmp     eax, edi
0x18007afb9  jl      short loc_18007AF73
0x18007afbb  lea     r9, [rbp+57h+var_50]; struct tagVARIANT *
0x18007afbf  mov     qword ptr [rbp+57h+var_50+8], rsi
0x18007afc3  lea     r8, [rbp+57h+var_A0]; struct tagVARIANT *
0x18007afc7  mov     rcx, r14; struct _SDO_PROFILE *
0x18007afca  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x18007afce  call    SdoWrapSetProfileValues
0x18007afd3  mov     ebx, eax
0x18007afd5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18007afd9  call    cs:__imp_VariantClear
0x18007afdf  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18007afe3  call    cs:__imp_VariantClear
0x18007afe9  lea     rcx, [rbp+57h+var_50]; pvarg
0x18007afed  call    cs:__imp_VariantClear
0x18007aff3  mov     ecx, ebx
0x18007aff5  movzx   eax, bx
0x18007aff8  and     ecx, 1FFF0000h
0x18007affe  cmp     ecx, 70000h
0x18007b004  cmovnz  eax, ebx
0x18007b007  jmp     short loc_18007B01A
0x18007b009  xor     r8d, r8d
0x18007b00c  mov     rdx, r14
0x18007b00f  test    eax, eax
0x18007b011  setnz   r8b
0x18007b015  call    SdoSetProfileToForceEncryption
0x18007b01a  mov     rbx, [rsp+0C0h+arg_8]
0x18007b022  add     rsp, 0A0h
0x18007b029  pop     r15
0x18007b02b  pop     r14
0x18007b02d  pop     rdi
0x18007b02e  pop     rsi
0x18007b02f  pop     rbp
0x18007b030  retn
```
