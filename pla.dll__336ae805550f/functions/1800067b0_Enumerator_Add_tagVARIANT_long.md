# Enumerator::Add(tagVARIANT *,long *)

- ea: `0x1800067b0`
- end: `0x180006c9a`
- name: `?Add@Enumerator@@QEAAJPEAUtagVARIANT@@PEAJ@Z`
- size: `1258`
- prototype: `int(Enumerator *__hidden this, struct tagVARIANT *, int *)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x180005200`
- `0x180006ca0`
- `0x1800584f0`
- `0x180059700`
- `0x180079dd0`
- `0x180084960`
- `0x1800873c0`
- `0x1800aaff0`
- `0x1800bfd20`
- `0x1800d2c70`
- `0x1800fa9f0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800067b0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006838`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006838`
- `OLEAUT32!__imp_VariantCopy` at `0x180006888`
- `OLEAUT32!__imp_VariantCopy` at `0x180006888`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180006a2f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180006a2f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180006866`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180006866`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800068e8`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800068e8`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180006acc`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180006acc`

## pseudocode

```c
__int64 __fastcall Enumerator::Add(Enumerator *this, struct tagVARIANT *a2, int *a3)
{
  int v3; // eax
  unsigned int v7; // eax
  SAFEARRAY **v8; // rsi
  HRESULT v9; // eax
  unsigned int v10; // edi
  HRESULT v11; // eax
  __int64 v13; // rax
  bool v14; // zf
  SAFEARRAY *v15; // rcx
  SAFEARRAY *v16; // rax
  __int64 v17; // rax
  HRESULT v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // [rsp+78h] [rbp-90h] BYREF
  Enumerator *v22; // [rsp+80h] [rbp-88h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+88h] [rbp-80h] BYREF
  void *ppvData; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int16 v25[64]; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int16 v26[64]; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 v27[64]; // [rsp+198h] [rbp+90h] BYREF
  unsigned __int16 v28[64]; // [rsp+218h] [rbp+110h] BYREF

  v3 = *((_DWORD *)this + 14);
  ppvData = 0;
  rgsabound = 0;
  LODWORD(v21) = v3;
  v22 = this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "Enumerator::Add", 16, &v22, 8, &v21, 4);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v7 = *((_DWORD *)this + 20);
  if ( *((_DWORD *)this + 19) < v7 )
  {
LABEL_6:
    v8 = (SAFEARRAY **)((char *)this + 64);
    v9 = SafeArrayAccessData(*((SAFEARRAY **)this + 8), &ppvData);
    v10 = v9;
    if ( v9 < 0 )
    {
      LODWORD(v22) = 0;
      LODWORD(v21) = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_11;
      }
      PlaiWhoAmI(v27, 0x4000000000000800uLL);
      v20 = -1;
      do
        v14 = v27[++v20] == 0;
      while ( !v14 );
    }
    else
    {
      v11 = VariantCopy((VARIANTARG *)ppvData + *((unsigned int *)this + 19), a2);
      v10 = v11;
      if ( v11 >= 0 )
      {
        if ( a3 )
          *a3 = *((_DWORD *)this + 19);
        ++*((_DWORD *)this + 19);
        goto LABEL_11;
      }
      LODWORD(v22) = 0;
      LODWORD(v21) = v11;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_11;
      }
      PlaiWhoAmI(v28, 0x4000000000000800uLL);
      v13 = -1;
      do
        v14 = v28[++v13] == 0;
      while ( !v14 );
    }
LABEL_21:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v21, 4, byte_180147320, 1, &v22, 4);
    goto LABEL_11;
  }
  v15 = (SAFEARRAY *)*((_QWORD *)this + 8);
  v8 = (SAFEARRAY **)((char *)this + 64);
  rgsabound.lLbound = 0;
  rgsabound.cElements = v7 + 16;
  if ( !v15 )
  {
    v16 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    *v8 = v16;
    if ( !v16 )
    {
      v10 = -2147024882;
      LODWORD(v21) = -2147024882;
      LODWORD(v22) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_11;
      }
      PlaiWhoAmI(v26, 0x4000000000000800uLL);
      v17 = -1;
      do
        v14 = v26[++v17] == 0;
      while ( !v14 );
      goto LABEL_21;
    }
    goto LABEL_24;
  }
  v18 = SafeArrayRedim(v15, &rgsabound);
  v10 = v18;
  if ( v18 >= 0 )
  {
LABEL_24:
    *((_DWORD *)this + 20) = rgsabound.cElements;
    goto LABEL_6;
  }
  LODWORD(v21) = 0;
  LODWORD(v22) = v18;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v25, 0x4000000000000800uLL);
    v19 = -1;
    do
      v14 = v25[++v19] == 0;
    while ( !v14 );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v22, 4, byte_180147320, 1, &v21, 4);
  }
LABEL_11:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( ppvData )
    SafeArrayUnaccessData(*v8);
  return v10;
}

```

## disassembly

```asm
0x1800067b0  mov     r11, rsp
0x1800067b3  push    rbp
0x1800067b4  lea     rbp, [r11-1D8h]
0x1800067bb  sub     rsp, 2D0h
0x1800067c2  mov     rax, cs:__security_cookie
0x1800067c9  xor     rax, rsp
0x1800067cc  mov     [rbp+1D0h+var_40], rax
0x1800067d3  mov     eax, [rcx+38h]
0x1800067d6  mov     [r11+20h], rbx
0x1800067da  mov     rbx, rcx
0x1800067dd  mov     [r11-20h], r12
0x1800067e1  xor     r12d, r12d
0x1800067e4  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800067eb  mov     [r11-28h], r13
0x1800067ef  lea     r13, aEnumeratorAdd; "Enumerator::Add"
0x1800067f6  mov     [r11-30h], r14
0x1800067fa  mov     r14, rdx
0x1800067fd  mov     [r11-38h], r15
0x180006801  mov     r15, r8
0x180006804  mov     [rbp+1D0h+ppvData], r12
0x180006808  mov     qword ptr [rbp+1D0h+rgsabound.cElements], r12
0x18000680c  mov     dword ptr [rsp+2D0h+var_260], eax
0x180006810  mov     [rsp+2D0h+var_258], rcx
0x180006815  jz      short loc_18000682E
0x180006817  mov     rdx, 4000000000000400h
0x180006821  test    qword ptr cs:xmmword_180169738+8, rdx
0x180006828  jnz     loc_180006BB7
0x18000682e  cmp     [rbx+8], r12d
0x180006832  jz      short loc_18000683E
0x180006834  lea     rcx, [rbx+10h]; lpCriticalSection
0x180006838  call    cs:__imp_EnterCriticalSection
0x18000683e  mov     eax, [rbx+50h]
0x180006841  mov     [rsp+2C8h], rsi
0x180006849  mov     [rsp+2D0h+var_10], rdi
0x180006851  cmp     [rbx+4Ch], eax
0x180006854  jnb     loc_180006A06
0x18000685a  mov     rcx, [rbx+40h]; psa
0x18000685e  lea     rsi, [rbx+40h]
0x180006862  lea     rdx, [rbp+1D0h+ppvData]; ppvData
0x180006866  call    cs:__imp_SafeArrayAccessData
0x18000686c  mov     edi, eax
0x18000686e  test    eax, eax
0x180006870  js      loc_180006C6B
0x180006876  mov     eax, [rbx+4Ch]
0x180006879  mov     rdx, r14; pvargSrc
0x18000687c  lea     rcx, [rax+rax*2]
0x180006880  mov     rax, [rbp+1D0h+ppvData]
0x180006884  lea     rcx, [rax+rcx*8]; pvargDest
0x180006888  call    cs:__imp_VariantCopy
0x18000688e  mov     edi, eax
0x180006890  test    eax, eax
0x180006892  js      loc_180006918
0x180006898  test    r15, r15
0x18000689b  jz      short loc_1800068A3
0x18000689d  mov     eax, [rbx+4Ch]
0x1800068a0  mov     [r15], eax
0x1800068a3  inc     dword ptr [rbx+4Ch]
0x1800068a6  cmp     dword ptr [rbx+8], 0
0x1800068aa  mov     r15, [rsp+2D0h+var_30]
0x1800068b2  mov     r14, [rsp+2D0h+var_28]
0x1800068ba  mov     r13, [rsp+2D0h+var_20]
0x1800068c2  mov     r12, [rsp+2D0h+var_18]
0x1800068ca  jz      short loc_1800068D6
0x1800068cc  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800068d0  call    cs:__imp_LeaveCriticalSection
0x1800068d6  cmp     [rbp+1D0h+ppvData], 0
0x1800068db  mov     rbx, [rsp+2D0h+arg_18]
0x1800068e3  jz      short loc_1800068EE
0x1800068e5  mov     rcx, [rsi]; psa
0x1800068e8  call    cs:__imp_SafeArrayUnaccessData
0x1800068ee  mov     rsi, [rsp+2C8h]
0x1800068f6  mov     eax, edi
0x1800068f8  mov     rdi, [rsp+2D0h+var_10]
0x180006900  mov     rcx, [rbp+1D0h+var_40]
0x180006907  xor     rcx, rsp; StackCookie
0x18000690a  call    __security_check_cookie
0x18000690f  add     rsp, 2D0h
0x180006916  pop     rbp
0x180006917  retn
0x180006918  cmp     dword ptr cs:xmmword_180169738, r12d
0x18000691f  mov     dword ptr [rsp+2D0h+var_258], r12d
0x180006924  mov     dword ptr [rsp+2D0h+var_260], eax
0x180006928  jz      loc_1800068A6
0x18000692e  mov     rdx, 4000000000000800h; unsigned __int64
0x180006938  test    qword ptr cs:xmmword_180169738+8, rdx
0x18000693f  jz      loc_1800068A6
0x180006945  mov     rax, cs:qword_180169748
0x18000694c  and     rax, rdx
0x18000694f  cmp     cs:qword_180169748, rax
0x180006956  jnz     loc_1800068A6
0x18000695c  lea     rcx, [rbp+1D0h+var_C0]; unsigned __int16 *
0x180006963  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180006968  lea     rcx, [rbp+1D0h+var_C0]
0x18000696f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006976  nop     word ptr [rax+rax+00000000h]
0x180006980  cmp     [rcx+rax*2+2], r12w
0x180006986  lea     rax, [rax+1]
0x18000698a  jnz     short loc_180006980
0x18000698c  lea     ecx, [rax+rax]
0x18000698f  lea     rax, [rbp+1D0h+var_C0]
0x180006996  add     rcx, 2
0x18000699a  lea     r9, [rsp+2D0h+var_260]
0x18000699f  mov     [rsp+60h], rcx
0x1800069a4  lea     rdx, PLA_EVENT_ERROR
0x1800069ab  mov     [rsp+2D0h+var_278], rax
0x1800069b0  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800069b7  mov     [rsp+2D0h+var_280], 10h
0x1800069c0  lea     rax, [rsp+2D0h+var_258]
0x1800069c5  mov     [rsp+2D0h+var_288], r13
0x1800069ca  mov     r8d, 5
0x1800069d0  mov     [rsp+2D0h+var_290], 4
0x1800069d9  mov     [rsp+2D0h+var_298], rax
0x1800069de  lea     rax, byte_180147320
0x1800069e5  mov     [rsp+2D0h+var_2A0], 1
0x1800069ee  mov     [rsp+2D0h+var_2A8], rax
0x1800069f3  mov     [rsp+2D0h+var_2B0], 4
0x1800069fc  call    EventingWriteEvent
0x180006a01  jmp     loc_1800068A6
0x180006a06  mov     rcx, [rbx+40h]; psa
0x180006a0a  lea     rsi, [rbx+40h]
0x180006a0e  add     eax, 10h
0x180006a11  mov     [rbp+1D0h+rgsabound.lLbound], r12d
0x180006a15  mov     [rbp+1D0h+rgsabound.cElements], eax
0x180006a18  test    rcx, rcx
0x180006a1b  jnz     loc_180006AC8
0x180006a21  mov     ecx, 0Ch; vt
0x180006a26  lea     r8, [rbp+1D0h+rgsabound]; rgsabound
0x180006a2a  mov     edx, 1; cDims
0x180006a2f  call    cs:__imp_SafeArrayCreate
0x180006a35  mov     [rsi], rax
0x180006a38  test    rax, rax
0x180006a3b  jz      short loc_180006A48
0x180006a3d  mov     eax, [rbp+1D0h+rgsabound.cElements]
0x180006a40  mov     [rbx+50h], eax
0x180006a43  jmp     loc_18000685A
0x180006a48  cmp     dword ptr cs:xmmword_180169738, r12d
0x180006a4f  mov     edi, 8007000Eh
0x180006a54  mov     dword ptr [rsp+2D0h+var_260], edi
0x180006a58  mov     dword ptr [rsp+2D0h+var_258], r12d
0x180006a5d  jz      loc_1800068A6
0x180006a63  mov     rdx, 4000000000000800h; unsigned __int64
0x180006a6d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180006a74  jz      loc_1800068A6
0x180006a7a  mov     rax, cs:qword_180169748
0x180006a81  and     rax, rdx
0x180006a84  cmp     cs:qword_180169748, rax
0x180006a8b  jnz     loc_1800068A6
0x180006a91  lea     rcx, [rbp+1D0h+var_1C0]; unsigned __int16 *
0x180006a95  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180006a9a  lea     rcx, [rbp+1D0h+var_1C0]
0x180006a9e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006aa5  nop     word ptr [rax+rax+00000000h]
0x180006ab0  cmp     [rcx+rax*2+2], r12w
0x180006ab6  lea     rax, [rax+1]
0x180006aba  jnz     short loc_180006AB0
0x180006abc  lea     ecx, [rax+rax]
0x180006abf  lea     rax, [rbp+1D0h+var_1C0]
0x180006ac3  jmp     loc_180006996
0x180006ac8  lea     rdx, [rbp+1D0h+rgsabound]; psaboundNew
0x180006acc  call    cs:__imp_SafeArrayRedim
0x180006ad2  mov     edi, eax
0x180006ad4  test    eax, eax
0x180006ad6  jns     loc_180006A3D
0x180006adc  cmp     dword ptr cs:xmmword_180169738, r12d
0x180006ae3  mov     dword ptr [rsp+2D0h+var_260], r12d
0x180006ae8  mov     dword ptr [rsp+2D0h+var_258], eax
0x180006aec  jz      loc_1800068A6
0x180006af2  mov     rdx, 4000000000000800h; unsigned __int64
0x180006afc  test    qword ptr cs:xmmword_180169738+8, rdx
0x180006b03  jz      loc_1800068A6
0x180006b09  mov     rax, cs:qword_180169748
0x180006b10  and     rax, rdx
0x180006b13  cmp     cs:qword_180169748, rax
0x180006b1a  jnz     loc_1800068A6
0x180006b20  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x180006b24  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180006b29  lea     rcx, [rbp+1D0h+var_240]
0x180006b2d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006b34  cmp     [rcx+rax*2+2], r12w
0x180006b3a  lea     rax, [rax+1]
0x180006b3e  jnz     short loc_180006B34
0x180006b40  lea     ecx, [rax+rax]
0x180006b43  mov     r8d, 5
0x180006b49  add     rcx, 2
0x180006b4d  lea     rax, [rbp+1D0h+var_240]
0x180006b51  mov     [rsp+60h], rcx
0x180006b56  lea     r9, [rsp+2D0h+var_258]
0x180006b5b  mov     [rsp+2D0h+var_278], rax
0x180006b60  lea     rdx, PLA_EVENT_ERROR
0x180006b67  mov     [rsp+2D0h+var_280], 10h
0x180006b70  lea     rax, [rsp+2D0h+var_260]
0x180006b75  mov     [rsp+2D0h+var_288], r13
0x180006b7a  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180006b81  mov     [rsp+2D0h+var_290], 4
0x180006b8a  mov     [rsp+2D0h+var_298], rax
0x180006b8f  lea     rax, byte_180147320
0x180006b96  mov     [rsp+2D0h+var_2A0], 1
0x180006b9f  mov     [rsp+2D0h+var_2A8], rax
0x180006ba4  mov     [rsp+2D0h+var_2B0], 4
0x180006bad  call    EventingWriteEvent
0x180006bb2  jmp     loc_1800068A6
0x180006bb7  mov     rax, cs:qword_180169748
0x180006bbe  and     rax, rdx
0x180006bc1  cmp     cs:qword_180169748, rax
0x180006bc8  jnz     loc_18000682E
0x180006bce  mov     [rsp+2D0h+var_290], 4
0x180006bd7  lea     rax, [rsp+2D0h+var_260]
0x180006bdc  mov     [rsp+2D0h+var_298], rax
0x180006be1  lea     rdx, PLA_EVENT_METHOD
0x180006be8  lea     rax, [rsp+2D0h+var_258]
0x180006bed  mov     [rsp+2D0h+var_2A0], 8
0x180006bf6  mov     [rsp+2D0h+var_2A8], rax
0x180006bfb  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180006c02  mov     r9, r13
0x180006c05  mov     [rsp+2D0h+var_2B0], 10h
0x180006c0e  mov     r8d, 3
0x180006c14  call    EventingWriteEvent
0x180006c19  jmp     loc_18000682E
0x180006c1e  mov     rax, cs:qword_180169748
0x180006c25  and     rax, rdx
0x180006c28  cmp     cs:qword_180169748, rax
0x180006c2f  jnz     loc_1800068A6
0x180006c35  lea     rcx, [rbp+1D0h+var_140]; unsigned __int16 *
0x180006c3c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180006c41  lea     rcx, [rbp+1D0h+var_140]
0x180006c48  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006c4f  nop
0x180006c50  cmp     [rcx+rax*2+2], r12w
0x180006c56  lea     rax, [rax+1]
0x180006c5a  jnz     short loc_180006C50
0x180006c5c  lea     ecx, [rax+rax]
0x180006c5f  lea     rax, [rbp+1D0h+var_140]
0x180006c66  jmp     loc_180006996
0x180006c6b  cmp     dword ptr cs:xmmword_180169738, r12d
0x180006c72  mov     dword ptr [rsp+2D0h+var_258], r12d
0x180006c77  mov     dword ptr [rsp+2D0h+var_260], eax
0x180006c7b  jz      loc_1800068A6
0x180006c81  mov     rdx, 4000000000000800h; unsigned __int64
0x180006c8b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180006c92  jz      loc_1800068A6
0x180006c98  jmp     short loc_180006C1E
```
