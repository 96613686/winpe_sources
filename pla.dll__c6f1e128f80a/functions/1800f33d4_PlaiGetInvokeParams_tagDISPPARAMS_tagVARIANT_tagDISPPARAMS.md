# PlaiGetInvokeParams(tagDISPPARAMS *,tagVARIANT *,tagDISPPARAMS *)

- ea: `0x1800f33d4`
- end: `0x1800f38c3`
- name: `?PlaiGetInvokeParams@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@0@Z`
- size: `1263`
- prototype: `int(struct tagDISPPARAMS *, struct tagVARIANT *, struct tagDISPPARAMS *)`
- caller_count: `18`
- callee_count: `7`
- tags: ``

## callers

- `0x180052dd0`
- `0x180054d50`
- `0x18006eaa0`
- `0x180074070`
- `0x18007c700`
- `0x18007e970`
- `0x18009fe80`
- `0x1800b12f0`
- `0x1800b7e90`
- `0x1800b90c0`
- `0x1800c3f30`
- `0x1800caf00`
- `0x1800dd450`
- `0x1800e2000`
- `0x1800e4a30`
- `0x1800e8030`
- `0x180100790`
- `0x180105f50`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180018420`
- `0x180024ea0`
- `0x180026850`
- `0x1800f33d4`
- `0x18013aee0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800f3428`
- `OLEAUT32!__imp_VariantInit` at `0x1800f3428`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800f36f7`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800f36f7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f388d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f388d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f3496`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f3646`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f3496`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f3646`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f3862`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f3875`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f3862`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f3875`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800f35a8`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800f35a8`

## pseudocode

```c
__int64 __fastcall PlaiGetInvokeParams(struct tagDISPPARAMS *a1, struct tagVARIANT *a2, struct tagDISPPARAMS *a3)
{
  ULONG v4; // r15d
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rcx
  SAFEARRAY *llVal; // r12
  HRESULT v9; // eax
  HRESULT v10; // ebx
  SAFEARRAY *v11; // rdi
  __int64 v12; // rax
  int *v13; // r9
  int *v14; // rcx
  ULONG cElements; // r8d
  VARTYPE v16; // si
  SAFEARRAY *Vector; // rax
  __int64 v18; // rax
  HRESULT v19; // eax
  int v20; // r8d
  __int64 v21; // rax
  unsigned __int16 *v22; // rax
  __int64 v23; // rax
  int v25; // [rsp+70h] [rbp-90h] BYREF
  HRESULT v26; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  void *v28; // [rsp+88h] [rbp-78h] BYREF
  SAFEARRAY *v29; // [rsp+90h] [rbp-70h]
  VARIANTARG pvargDest; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v31[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v32[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v33[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v34[64]; // [rsp+230h] [rbp+130h] BYREF

  v4 = 0;
  memset(&pvargDest, 0, sizeof(pvargDest));
  ppvData = 0;
  v28 = 0;
  VariantInit(a2);
  a2->llVal = 0;
  *a1 = *a3;
  if ( a1->cArgs != 1 || ((a1->rgvarg->vt - 8204) & 0xBFFF) != 0 )
    return 0;
  PlaiVariantInit(&pvargDest);
  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a1->rgvarg->llVal;
  if ( (a1->rgvarg->vt & 0x4000) != 0 )
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)p_llVal->llVal;
  llVal = (SAFEARRAY *)p_llVal->llVal;
  v29 = llVal;
  v9 = SafeArrayAccessData(llVal, &ppvData);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 0;
    v25 = 0;
    v26 = v9;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_45;
    }
    PlaiWhoAmI(v31, 0x4000000000000800uLL);
    v12 = -1;
    do
      ++v12;
    while ( v31[v12] );
    v13 = &v26;
    v14 = &v25;
LABEL_12:
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, v13, 4, qword_180147320, 1, v14, 4, "PlaiGetInvokeParams", 20);
    goto LABEL_45;
  }
  cElements = llVal->rgsabound[0].cElements;
  v16 = 8;
  LOWORD(v25) = *(_WORD *)ppvData;
  if ( (_WORD)v25 != 8 )
    v16 = 17;
  Vector = SafeArrayCreateVector(v16, 0, cElements);
  v11 = Vector;
  if ( !Vector )
  {
    v10 = -2147024882;
    v25 = -2147024882;
    v26 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_45;
    }
    PlaiWhoAmI(v32, 0x4000000000000800uLL);
    v18 = -1;
    do
      ++v18;
    while ( v32[v18] );
LABEL_21:
    v13 = &v25;
    v14 = &v26;
    goto LABEL_12;
  }
  v19 = SafeArrayAccessData(Vector, &v28);
  v10 = v19;
  if ( v19 < 0 )
  {
    v26 = 0;
    v25 = v19;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_45;
    }
    PlaiWhoAmI(v33, 0x4000000000000800uLL);
    v21 = -1;
    do
      ++v21;
    while ( v33[v21] );
    goto LABEL_21;
  }
  while ( 1 )
  {
    if ( v4 >= llVal->rgsabound[0].cElements )
    {
      a1->rgvarg = a2;
      a2->vt = v16 | 0x2000;
      a2->llVal = (LONGLONG)v11;
      goto LABEL_45;
    }
    if ( (_WORD)v25 == 8 )
      break;
    v10 = VariantChangeType(&pvargDest, (const VARIANTARG *)ppvData + v4, 0, 0x11u);
    if ( v10 < 0 )
    {
      v10 = 0;
      goto LABEL_44;
    }
    *((_BYTE *)v28 + v4) = pvargDest.bVal;
LABEL_35:
    llVal = v29;
    ++v4;
  }
  if ( *((_WORD *)ppvData + 12 * v4) != 8 )
    goto LABEL_44;
  v22 = PlaiAllocStringEx(*((const unsigned __int16 **)ppvData + 3 * v4 + 1), (const char *)8, v20);
  *((_QWORD *)v28 + v4) = v22;
  if ( *((_QWORD *)v28 + v4) )
    goto LABEL_35;
  v10 = -2147024882;
  v26 = 0;
  v25 = -2147024882;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v34, 0x4000000000000800uLL);
    v23 = -1;
    do
      ++v23;
    while ( v34[v23] );
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v25, 4, qword_180147320, 1, &v26, 4, "PlaiGetInvokeParams", 20);
  }
LABEL_44:
  llVal = v29;
LABEL_45:
  PlaiVariantClear(&pvargDest);
  if ( ppvData )
  {
    SafeArrayUnaccessData(llVal);
    ppvData = 0;
  }
  if ( v28 )
  {
    SafeArrayUnaccessData(v11);
    v28 = 0;
  }
  if ( a2->parray != v11 )
  {
    if ( v11 )
      SafeArrayDestroy(v11);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800f33d4  mov     [rsp-8+arg_10], rbx
0x1800f33d9  push    rbp
0x1800f33da  push    rsi
0x1800f33db  push    rdi
0x1800f33dc  push    r12
0x1800f33de  push    r13
0x1800f33e0  push    r14
0x1800f33e2  push    r15
0x1800f33e4  lea     rbp, [rsp-1C0h]
0x1800f33ec  sub     rsp, 2C0h
0x1800f33f3  mov     rax, cs:__security_cookie
0x1800f33fa  xor     rax, rsp
0x1800f33fd  mov     [rbp+1F0h+var_40], rax
0x1800f3404  mov     r14, rcx
0x1800f3407  xorps   xmm0, xmm0
0x1800f340a  xor     eax, eax
0x1800f340c  xor     r15d, r15d
0x1800f340f  mov     rcx, rdx; pvarg
0x1800f3412  mov     qword ptr [rbp+1F0h+pvargDest+10h], rax
0x1800f3416  movups  xmmword ptr [rbp+1F0h+pvargDest], xmm0
0x1800f341a  mov     [rbp+1F0h+ppvData], r15
0x1800f341e  mov     rbx, r8
0x1800f3421  mov     [rbp+1F0h+var_268], r15
0x1800f3425  mov     r13, rdx
0x1800f3428  call    cs:__imp_VariantInit
0x1800f342e  mov     [r13+8], r15
0x1800f3432  movups  xmm0, xmmword ptr [rbx]
0x1800f3435  movups  xmmword ptr [r14], xmm0
0x1800f3439  movsd   xmm1, qword ptr [rbx+10h]
0x1800f343e  movsd   qword ptr [r14+10h], xmm1
0x1800f3444  cmp     dword ptr [r14+10h], 1
0x1800f3449  jnz     loc_1800F3897
0x1800f344f  mov     rax, [r14]
0x1800f3452  mov     edx, 200Ch
0x1800f3457  movzx   ecx, word ptr [rax]
0x1800f345a  mov     eax, 0BFFFh
0x1800f345f  sub     cx, dx
0x1800f3462  test    ax, cx
0x1800f3465  jnz     loc_1800F3897
0x1800f346b  lea     rcx, [rbp+1F0h+pvargDest]; struct tagVARIANT *
0x1800f346f  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800f3474  mov     rax, [r14]
0x1800f3477  mov     edx, 4000h
0x1800f347c  lea     rcx, [rax+8]
0x1800f3480  test    [rax], dx
0x1800f3483  jz      short loc_1800F3488
0x1800f3485  mov     rcx, [rcx]
0x1800f3488  mov     r12, [rcx]
0x1800f348b  lea     rdx, [rbp+1F0h+ppvData]; ppvData
0x1800f348f  mov     rcx, r12; psa
0x1800f3492  mov     [rbp+1F0h+var_260], r12
0x1800f3496  call    cs:__imp_SafeArrayAccessData
0x1800f349c  mov     ebx, eax
0x1800f349e  test    eax, eax
0x1800f34a0  jns     loc_1800F3581
0x1800f34a6  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f34ad  mov     rdi, r15
0x1800f34b0  mov     [rsp+2F0h+var_280], r15d
0x1800f34b5  mov     [rsp+2F0h+var_278], eax
0x1800f34b9  jz      loc_1800F3850
0x1800f34bf  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f34c9  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f34d0  jz      loc_1800F3850
0x1800f34d6  mov     rax, cs:qword_180169748
0x1800f34dd  and     rax, rdx
0x1800f34e0  cmp     cs:qword_180169748, rax
0x1800f34e7  jnz     loc_1800F3850
0x1800f34ed  lea     rcx, [rbp+1F0h+var_240]; unsigned __int16 *
0x1800f34f1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f34f6  lea     rcx, [rbp+1F0h+var_240]
0x1800f34fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f34fe  inc     rax
0x1800f3501  cmp     [rcx+rax*2], r15w
0x1800f3506  jnz     short loc_1800F34FE
0x1800f3508  lea     ecx, [rax+rax]
0x1800f350b  add     rcx, 2
0x1800f350f  lea     rax, [rbp+1F0h+var_240]
0x1800f3513  mov     [rsp+2F0h+var_290], rcx
0x1800f3518  lea     r9, [rsp+2F0h+var_278]
0x1800f351d  lea     rcx, [rsp+2F0h+var_280]
0x1800f3522  mov     [rsp+2F0h+var_298], rax
0x1800f3527  lea     rdx, PLA_EVENT_ERROR
0x1800f352e  mov     [rsp+2F0h+var_2A0], 14h
0x1800f3537  lea     rax, aPlaigetinvokep; "PlaiGetInvokeParams"
0x1800f353e  mov     [rsp+2F0h+var_2A8], rax
0x1800f3543  mov     eax, 4
0x1800f3548  mov     [rsp+2F0h+var_2B0], rax
0x1800f354d  mov     [rsp+2F0h+var_2B8], rcx
0x1800f3552  lea     rcx, qword_180147320
0x1800f3559  mov     [rsp+2F0h+var_2C0], 1
0x1800f3562  mov     [rsp+2F0h+var_2C8], rcx
0x1800f3567  lea     r8d, [rax+1]
0x1800f356b  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f3572  mov     [rsp+2F0h+var_2D0], rax
0x1800f3577  call    EventingWriteEvent
0x1800f357c  jmp     loc_1800F3850
0x1800f3581  mov     rax, [rbp+1F0h+ppvData]
0x1800f3585  mov     ecx, 8
0x1800f358a  mov     r8d, [r12+18h]; cElements
0x1800f358f  mov     esi, ecx
0x1800f3591  movzx   eax, word ptr [rax]
0x1800f3594  lea     edx, [rcx+9]
0x1800f3597  cmp     cx, ax
0x1800f359a  mov     word ptr [rsp+2F0h+var_280], ax
0x1800f359f  cmovnz  si, dx
0x1800f35a3  xor     edx, edx; lLbound
0x1800f35a5  movzx   ecx, si; vt
0x1800f35a8  call    cs:__imp_SafeArrayCreateVector
0x1800f35ae  mov     rdi, rax
0x1800f35b1  test    rax, rax
0x1800f35b4  jnz     loc_1800F363F
0x1800f35ba  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f35c1  mov     ecx, 8007000Eh
0x1800f35c6  mov     ebx, ecx
0x1800f35c8  mov     [rsp+2F0h+var_280], ecx
0x1800f35cc  mov     [rsp+2F0h+var_278], r15d
0x1800f35d1  jz      loc_1800F3850
0x1800f35d7  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f35e1  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f35e8  jz      loc_1800F3850
0x1800f35ee  mov     rax, cs:qword_180169748
0x1800f35f5  and     rax, rdx
0x1800f35f8  cmp     cs:qword_180169748, rax
0x1800f35ff  jnz     loc_1800F3850
0x1800f3605  lea     rcx, [rbp+1F0h+var_1C0]; unsigned __int16 *
0x1800f3609  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f360e  lea     rcx, [rbp+1F0h+var_1C0]
0x1800f3612  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f3616  inc     rax
0x1800f3619  cmp     [rcx+rax*2], r15w
0x1800f361e  jnz     short loc_1800F3616
0x1800f3620  lea     ecx, [rax+rax]
0x1800f3623  lea     rax, [rbp+1F0h+var_1C0]
0x1800f3627  add     rcx, 2
0x1800f362b  lea     r9, [rsp+2F0h+var_280]
0x1800f3630  mov     [rsp+2F0h+var_290], rcx
0x1800f3635  lea     rcx, [rsp+2F0h+var_278]
0x1800f363a  jmp     loc_1800F3522
0x1800f363f  lea     rdx, [rbp+1F0h+var_268]; ppvData
0x1800f3643  mov     rcx, rdi; psa
0x1800f3646  call    cs:__imp_SafeArrayAccessData
0x1800f364c  mov     ebx, eax
0x1800f364e  test    eax, eax
0x1800f3650  jns     short loc_1800F36C6
0x1800f3652  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f3659  mov     [rsp+2F0h+var_278], r15d
0x1800f365e  mov     [rsp+2F0h+var_280], eax
0x1800f3662  jz      loc_1800F3850
0x1800f3668  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f3672  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f3679  jz      loc_1800F3850
0x1800f367f  mov     rax, cs:qword_180169748
0x1800f3686  and     rax, rdx
0x1800f3689  cmp     cs:qword_180169748, rax
0x1800f3690  jnz     loc_1800F3850
0x1800f3696  lea     rcx, [rbp+1F0h+var_140]; unsigned __int16 *
0x1800f369d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f36a2  lea     rcx, [rbp+1F0h+var_140]
0x1800f36a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f36ad  inc     rax
0x1800f36b0  cmp     [rcx+rax*2], r15w
0x1800f36b5  jnz     short loc_1800F36AD
0x1800f36b7  lea     ecx, [rax+rax]
0x1800f36ba  lea     rax, [rbp+1F0h+var_140]
0x1800f36c1  jmp     loc_1800F3627
0x1800f36c6  cmp     r15d, [r12+18h]
0x1800f36cb  jnb     loc_1800F3833
0x1800f36d1  mov     rax, [rbp+1F0h+ppvData]
0x1800f36d5  mov     edx, 8; char *
0x1800f36da  mov     r12d, r15d
0x1800f36dd  lea     rcx, [r12+r12*2]
0x1800f36e1  cmp     dx, word ptr [rsp+2F0h+var_280]
0x1800f36e6  jz      short loc_1800F3710
0x1800f36e8  lea     r9d, [rdx+9]; vt
0x1800f36ec  xor     r8d, r8d; wFlags
0x1800f36ef  lea     rdx, [rax+rcx*8]; pvarSrc
0x1800f36f3  lea     rcx, [rbp+1F0h+pvargDest]; pvargDest
0x1800f36f7  call    cs:__imp_VariantChangeType
0x1800f36fd  mov     ebx, eax
0x1800f36ff  test    eax, eax
0x1800f3701  js      short loc_1800F3740
0x1800f3703  mov     rcx, [rbp+1F0h+var_268]
0x1800f3707  mov     al, byte ptr [rbp+1F0h+pvargDest+8]
0x1800f370a  mov     [r12+rcx], al
0x1800f370e  jmp     short loc_1800F3737
0x1800f3710  cmp     dx, [rax+rcx*8]
0x1800f3714  jnz     loc_1800F3849
0x1800f371a  mov     rcx, [rax+rcx*8+8]; unsigned __int16 *
0x1800f371f  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x1800f3724  mov     rcx, [rbp+1F0h+var_268]
0x1800f3728  mov     [rcx+r12*8], rax
0x1800f372c  mov     rax, [rbp+1F0h+var_268]
0x1800f3730  cmp     qword ptr [rax+r12*8], 0
0x1800f3735  jz      short loc_1800F374B
0x1800f3737  mov     r12, [rbp+1F0h+var_260]
0x1800f373b  inc     r15d
0x1800f373e  jmp     short loc_1800F36C6
0x1800f3740  xor     r15d, r15d
0x1800f3743  mov     ebx, r15d
0x1800f3746  jmp     loc_1800F384C
0x1800f374b  xor     r15d, r15d
0x1800f374e  mov     ecx, 8007000Eh
0x1800f3753  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f375a  mov     ebx, ecx
0x1800f375c  mov     [rsp+2F0h+var_278], r15d
0x1800f3761  mov     [rsp+2F0h+var_280], ecx
0x1800f3765  jz      loc_1800F384C
0x1800f376b  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f3775  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f377c  jz      loc_1800F384C
0x1800f3782  mov     rax, cs:qword_180169748
0x1800f3789  and     rax, rdx
0x1800f378c  cmp     cs:qword_180169748, rax
0x1800f3793  jnz     loc_1800F384C
0x1800f3799  lea     rcx, [rbp+1F0h+var_C0]; unsigned __int16 *
0x1800f37a0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f37a5  lea     rcx, [rbp+1F0h+var_C0]
0x1800f37ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f37b0  inc     rax
0x1800f37b3  cmp     [rcx+rax*2], r15w
0x1800f37b8  jnz     short loc_1800F37B0
0x1800f37ba  lea     ecx, [rax+rax]
0x1800f37bd  add     rcx, 2
0x1800f37c1  lea     rax, [rbp+1F0h+var_C0]
0x1800f37c8  mov     [rsp+2F0h+var_290], rcx
0x1800f37cd  lea     r9, [rsp+2F0h+var_280]
0x1800f37d2  mov     [rsp+2F0h+var_298], rax
0x1800f37d7  lea     rcx, [rsp+2F0h+var_278]
0x1800f37dc  mov     [rsp+2F0h+var_2A0], 14h
0x1800f37e5  lea     rax, aPlaigetinvokep; "PlaiGetInvokeParams"
0x1800f37ec  mov     [rsp+2F0h+var_2A8], rax
0x1800f37f1  lea     rdx, PLA_EVENT_ERROR
0x1800f37f8  mov     eax, 4
0x1800f37fd  mov     [rsp+2F0h+var_2B0], rax
0x1800f3802  mov     [rsp+2F0h+var_2B8], rcx
0x1800f3807  lea     rcx, qword_180147320
0x1800f380e  mov     [rsp+2F0h+var_2C0], 1
0x1800f3817  mov     [rsp+2F0h+var_2C8], rcx
0x1800f381c  lea     r8d, [rax+1]
0x1800f3820  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f3827  mov     [rsp+2F0h+var_2D0], rax
0x1800f382c  call    EventingWriteEvent
0x1800f3831  jmp     short loc_1800F384C
0x1800f3833  or      si, 2000h
0x1800f3838  mov     [r14], r13
0x1800f383b  mov     [r13+0], si
0x1800f3840  xor     r15d, r15d
0x1800f3843  mov     [r13+8], rdi
0x1800f3847  jmp     short loc_1800F3850
0x1800f3849  xor     r15d, r15d
0x1800f384c  mov     r12, [rbp+1F0h+var_260]
0x1800f3850  lea     rcx, [rbp+1F0h+pvargDest]; struct tagVARIANT *
0x1800f3854  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800f3859  cmp     [rbp+1F0h+ppvData], r15
0x1800f385d  jz      short loc_1800F386C
0x1800f385f  mov     rcx, r12; psa
0x1800f3862  call    cs:__imp_SafeArrayUnaccessData
0x1800f3868  mov     [rbp+1F0h+ppvData], r15
0x1800f386c  cmp     [rbp+1F0h+var_268], r15
0x1800f3870  jz      short loc_1800F387F
0x1800f3872  mov     rcx, rdi; psa
0x1800f3875  call    cs:__imp_SafeArrayUnaccessData
0x1800f387b  mov     [rbp+1F0h+var_268], r15
0x1800f387f  cmp     [r13+8], rdi
0x1800f3883  jz      short loc_1800F3893
0x1800f3885  test    rdi, rdi
0x1800f3888  jz      short loc_1800F3893
0x1800f388a  mov     rcx, rdi; psa
0x1800f388d  call    cs:__imp_SafeArrayDestroy
0x1800f3893  mov     eax, ebx
0x1800f3895  jmp     short loc_1800F3899
0x1800f3897  xor     eax, eax
0x1800f3899  mov     rcx, [rbp+1F0h+var_40]
0x1800f38a0  xor     rcx, rsp; StackCookie
0x1800f38a3  call    __security_check_cookie
0x1800f38a8  mov     rbx, [rsp+2F0h+arg_10]
0x1800f38b0  add     rsp, 2C0h
0x1800f38b7  pop     r15
0x1800f38b9  pop     r14
0x1800f38bb  pop     r13
0x1800f38bd  pop     r12
0x1800f38bf  pop     rdi
0x1800f38c0  pop     rsi
0x1800f38c1  pop     rbp
0x1800f38c2  retn
```
