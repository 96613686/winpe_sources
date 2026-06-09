# SdoSetProfileData

- ea: `0x18007fd2c`
- end: `0x18007ff6d`
- name: `SdoSetProfileData`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180027044`

## callees

- `0x18007fd2c`
- `0x18007ff74`
- `0x1800814b4`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18007fdb2`
- `OLEAUT32!__imp_VariantInit` at `0x18007fdc2`
- `OLEAUT32!__imp_VariantInit` at `0x18007fdd2`
- `OLEAUT32!__imp_VariantInit` at `0x18007fdb2`
- `OLEAUT32!__imp_VariantInit` at `0x18007fdc2`
- `OLEAUT32!__imp_VariantInit` at `0x18007fdd2`
- `OLEAUT32!__imp_VariantClear` at `0x18007fef0`
- `OLEAUT32!__imp_VariantClear` at `0x18007ff00`
- `OLEAUT32!__imp_VariantClear` at `0x18007ff10`
- `OLEAUT32!__imp_VariantClear` at `0x18007fef0`
- `OLEAUT32!__imp_VariantClear` at `0x18007ff00`
- `OLEAUT32!__imp_VariantClear` at `0x18007ff10`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18007fe6b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18007fe6b`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18007fe89`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18007fe89`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007feb4`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18007feb4`

## pseudocode

```c
__int64 __fastcall SdoSetProfileData(__int64 a1, struct _SDO_PROFILE *a2, unsigned int a3)
{
  signed int v5; // esi
  SAFEARRAY *v6; // r14
  HRESULT v7; // ebx
  __int64 result; // rax
  LONG rgIndices; // [rsp+28h] [rbp-59h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp-51h] BYREF
  VARIANTARG v11; // [rsp+38h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-31h] BYREF
  VARIANTARG v13; // [rsp+68h] [rbp-19h] BYREF
  __int128 pv; // [rsp+80h] [rbp-1h] BYREF
  __int64 v15; // [rsp+90h] [rbp+Fh]
  int v16; // [rsp+98h] [rbp+17h]
  int v17; // [rsp+9Ch] [rbp+1Bh]
  int v18; // [rsp+A0h] [rbp+1Fh]
  int v19; // [rsp+A4h] [rbp+23h]
  int v20; // [rsp+A8h] [rbp+27h]

  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v11, 0, sizeof(v11));
  memset(&v13, 0, sizeof(v13));
  if ( (_QWORD)xmmword_1800D0F60 )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSdoWrapperTemplateFunc)(
      gSdoWrapperEtwContext,
      xmmword_1800D0F60,
      L"SdoSetProfileData: entered\n");
  if ( (a3 & 0xC) != 0 )
    return SdoSetProfileToForceEncryption(a1, a2, (a3 >> 2) & 1);
  VariantInit(&pvarg);
  VariantInit(&v11);
  VariantInit(&v13);
  v11.lVal = 14;
  pvarg.vt = 3;
  v11.vt = 3;
  v16 = 3;
  if ( (a3 & 1) != 0 )
  {
    v5 = 4;
    pvarg.lVal = 2;
    v17 = 4;
    v18 = 9;
    v19 = 10;
  }
  else
  {
    pvarg.lVal = 1;
    v5 = 5;
    v17 = 4;
    v18 = 1;
    v19 = 9;
    v20 = 10;
  }
  rgsabound.cElements = v5;
  v13.vt = 8204;
  rgsabound.lLbound = 0;
  pv = 0;
  v15 = 0;
  rgIndices = 0;
  v6 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  while ( 1 )
  {
    if ( SafeArrayGetElement(v6, &rgIndices, &pv) >= 0 )
    {
      LOWORD(pv) = 3;
      DWORD2(pv) = *(&v16 + rgIndices);
      v7 = SafeArrayPutElement(v6, &rgIndices, &pv);
      if ( v7 < 0 )
        break;
    }
    if ( ++rgIndices >= v5 )
    {
      v13.llVal = (LONGLONG)v6;
      v7 = SdoWrapSetProfileValues(a2, &pvarg, &v11, &v13);
      break;
    }
  }
  VariantClear(&pvarg);
  VariantClear(&v11);
  VariantClear(&v13);
  result = (unsigned __int16)v7;
  if ( (v7 & 0x1FFF0000) != 0x70000 )
    return (unsigned int)v7;
  return result;
}

```

## disassembly

```asm
0x18007fd2c  mov     rax, rsp
0x18007fd2f  mov     [rax+8], rbx
0x18007fd33  mov     [rax+18h], rsi
0x18007fd37  mov     [rax+20h], r12
0x18007fd3b  push    rbp
0x18007fd3c  push    r14
0x18007fd3e  push    r15
0x18007fd40  lea     rbp, [rax-5Fh]
0x18007fd44  sub     rsp, 0C0h
0x18007fd4b  mov     rax, cs:__security_cookie
0x18007fd52  xor     rax, rsp
0x18007fd55  mov     [rbp+57h+var_20], rax
0x18007fd59  xor     eax, eax
0x18007fd5b  xorps   xmm0, xmm0
0x18007fd5e  mov     r15, rdx
0x18007fd61  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18007fd65  mov     rdx, qword ptr cs:xmmword_1800D0F60
0x18007fd6c  xorps   xmm1, xmm1
0x18007fd6f  mov     qword ptr [rbp+57h+var_A0+10h], rax
0x18007fd73  mov     ebx, r8d
0x18007fd76  mov     qword ptr [rbp+57h+var_70+10h], rax
0x18007fd7a  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18007fd7e  movups  xmmword ptr [rbp+57h+var_A0], xmm1
0x18007fd82  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18007fd86  test    rdx, rdx
0x18007fd89  jz      short loc_18007FDA5
0x18007fd8b  mov     rcx, cs:gSdoWrapperEtwContext
0x18007fd92  lea     r8, aSdosetprofiled; "SdoSetProfileData: entered\n"
0x18007fd99  mov     rax, cs:gSdoWrapperTemplateFunc
0x18007fda0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fda5  test    bl, 0Ch
0x18007fda8  jnz     loc_18007FF32
0x18007fdae  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18007fdb2  call    cs:__imp_VariantInit
0x18007fdb9  nop     dword ptr [rax+rax+00h]
0x18007fdbe  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18007fdc2  call    cs:__imp_VariantInit
0x18007fdc9  nop     dword ptr [rax+rax+00h]
0x18007fdce  lea     rcx, [rbp+57h+var_70]; pvarg
0x18007fdd2  call    cs:__imp_VariantInit
0x18007fdd9  nop     dword ptr [rax+rax+00h]
0x18007fdde  mov     dword ptr [rbp+57h+var_A0+8], 0Eh
0x18007fde5  mov     r12d, 3
0x18007fdeb  mov     word ptr [rbp+57h+pvarg], r12w
0x18007fdf0  mov     word ptr [rbp+57h+var_A0], r12w
0x18007fdf5  mov     [rbp+57h+var_40], r12d
0x18007fdf9  test    bl, 1
0x18007fdfc  jz      short loc_18007FE1D
0x18007fdfe  lea     esi, [r12+1]
0x18007fe03  mov     dword ptr [rbp+57h+pvarg+8], 2
0x18007fe0a  mov     [rbp+57h+var_3C], esi
0x18007fe0d  mov     [rbp+57h+var_38], 9
0x18007fe14  mov     [rbp+57h+var_34], 0Ah
0x18007fe1b  jmp     short loc_18007FE45
0x18007fe1d  mov     dword ptr [rbp+57h+pvarg+8], 1
0x18007fe24  mov     esi, 5
0x18007fe29  mov     [rbp+57h+var_3C], 4
0x18007fe30  mov     [rbp+57h+var_38], 1
0x18007fe37  mov     [rbp+57h+var_34], 9
0x18007fe3e  mov     [rbp+57h+var_30], 0Ah
0x18007fe45  mov     eax, 200Ch
0x18007fe4a  mov     [rbp+57h+rgsabound.cElements], esi
0x18007fe4d  mov     word ptr [rbp+57h+var_70], ax
0x18007fe51  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x18007fe55  xor     eax, eax
0x18007fe57  xorps   xmm0, xmm0
0x18007fe5a  and     [rbp+57h+rgsabound.lLbound], eax
0x18007fe5d  movups  [rbp+57h+pv], xmm0
0x18007fe61  mov     [rbp+57h+var_48], rax
0x18007fe65  lea     ecx, [rax+0Ch]; vt
0x18007fe68  lea     edx, [rax+1]; cDims
0x18007fe6b  call    cs:__imp_SafeArrayCreate
0x18007fe72  nop     dword ptr [rax+rax+00h]
0x18007fe77  and     [rbp+57h+rgIndices], 0
0x18007fe7b  mov     r14, rax
0x18007fe7e  lea     r8, [rbp+57h+pv]; pv
0x18007fe82  mov     rcx, r14; psa
0x18007fe85  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x18007fe89  call    cs:__imp_SafeArrayGetElement
0x18007fe90  nop     dword ptr [rax+rax+00h]
0x18007fe95  test    eax, eax
0x18007fe97  js      short loc_18007FEC6
0x18007fe99  movsxd  rax, [rbp+57h+rgIndices]
0x18007fe9d  lea     r8, [rbp+57h+pv]; pv
0x18007fea1  mov     word ptr [rbp+57h+pv], r12w
0x18007fea6  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x18007feaa  mov     ecx, [rbp+rax*4+57h+var_40]
0x18007feae  mov     dword ptr [rbp+57h+pv+8], ecx
0x18007feb1  mov     rcx, r14; psa
0x18007feb4  call    cs:__imp_SafeArrayPutElement
0x18007febb  nop     dword ptr [rax+rax+00h]
0x18007fec0  mov     ebx, eax
0x18007fec2  test    eax, eax
0x18007fec4  js      short loc_18007FEEC
0x18007fec6  mov     eax, [rbp+57h+rgIndices]
0x18007fec9  inc     eax
0x18007fecb  mov     [rbp+57h+rgIndices], eax
0x18007fece  cmp     eax, esi
0x18007fed0  jl      short loc_18007FE7E
0x18007fed2  lea     r9, [rbp+57h+var_70]; struct tagVARIANT *
0x18007fed6  mov     qword ptr [rbp+57h+var_70+8], r14
0x18007feda  lea     r8, [rbp+57h+var_A0]; struct tagVARIANT *
0x18007fede  mov     rcx, r15; struct _SDO_PROFILE *
0x18007fee1  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x18007fee5  call    SdoWrapSetProfileValues
0x18007feea  mov     ebx, eax
0x18007feec  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18007fef0  call    cs:__imp_VariantClear
0x18007fef7  nop     dword ptr [rax+rax+00h]
0x18007fefc  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18007ff00  call    cs:__imp_VariantClear
0x18007ff07  nop     dword ptr [rax+rax+00h]
0x18007ff0c  lea     rcx, [rbp+57h+var_70]; pvarg
0x18007ff10  call    cs:__imp_VariantClear
0x18007ff17  nop     dword ptr [rax+rax+00h]
0x18007ff1c  mov     ecx, ebx
0x18007ff1e  movzx   eax, bx
0x18007ff21  and     ecx, 1FFF0000h
0x18007ff27  cmp     ecx, 70000h
0x18007ff2d  cmovnz  eax, ebx
0x18007ff30  jmp     short loc_18007FF43
0x18007ff32  shr     ebx, 2
0x18007ff35  mov     rdx, r15
0x18007ff38  and     ebx, 1
0x18007ff3b  mov     r8d, ebx
0x18007ff3e  call    SdoSetProfileToForceEncryption
0x18007ff43  mov     rcx, [rbp+57h+var_20]
0x18007ff47  xor     rcx, rsp; StackCookie
0x18007ff4a  call    __security_check_cookie
0x18007ff4f  lea     r11, [rsp+0D0h+var_10]
0x18007ff57  mov     rbx, [r11+20h]
0x18007ff5b  mov     rsi, [r11+30h]
0x18007ff5f  mov     r12, [r11+38h]
0x18007ff63  mov     rsp, r11
0x18007ff66  pop     r15
0x18007ff68  pop     r14
0x18007ff6a  pop     rbp
0x18007ff6b  retn
```
