# GetFTContextInformation(_DOT11_SSID const *,int,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,ulong)

- ea: `0x14004967c`
- end: `0x140049c71`
- name: `?GetFTContextInformation@@YAPEAUNWF_FT_CONTEXT@@PEBU_DOT11_SSID@@HPEBEK1K1KK@Z`
- size: `1525`
- prototype: `struct NWF_FT_CONTEXT *(const struct _DOT11_SSID *, int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140041f8c`
- `0x140045a90`
- `0x140046bf0`

## callees

- `0x14000d22c`
- `0x140020f20`
- `0x14002ffb4`
- `0x14003125c`
- `0x140047a40`
- `0x14004967c`
- `0x140049c78`
- `0x14004a0bc`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004970f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400499eb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004970f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400499eb`
- `ntoskrnl!ExAllocatePool2` at `0x140049727`
- `ntoskrnl!ExAllocatePool2` at `0x140049727`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049a3a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049bf3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049a3a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049bf3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049c08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049c08`

## pseudocode

```c
struct NWF_FT_CONTEXT *__fastcall GetFTContextInformation(
        const struct _DOT11_SSID *a1,
        int a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        const unsigned __int8 *a5,
        unsigned int a6,
        const unsigned __int8 *a7,
        unsigned int a8,
        unsigned int a9)
{
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  size_t v10; // rsi
  __int64 v14; // r9
  unsigned int v15; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // r12
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v18; // r14
  char *v19; // rdi
  __int64 v20; // rcx
  bool v21; // zf
  unsigned int v22; // r8d
  unsigned int v23; // esi
  unsigned __int8 *v24; // rbx
  __int64 v25; // rax
  const unsigned __int8 *v26; // r15
  unsigned int v27; // r13d
  size_t v28; // rbp
  unsigned __int8 v29; // si
  unsigned int v30; // eax
  char *v31; // rax
  _BYTE *v32; // rbx
  __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned __int8 v35; // al
  unsigned __int8 v36; // r9
  unsigned __int8 v37; // r8
  unsigned __int8 v38; // al
  __int64 v39; // rax
  _OWORD *v40; // rax
  void *Src; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v43[136]; // [rsp+50h] [rbp-88h] BYREF
  unsigned int v45; // [rsp+F8h] [rbp+20h] BYREF

  p_WaitListHead = 0;
  v10 = a4;
  v45 = 0;
  memset(v43, 0, 0x48u);
  v15 = v10 + 392;
  if ( (unsigned int)(v10 + 392) < 0x10 )
  {
LABEL_59:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 422, WPP_e90d411d816e312466897e39e745b158_Traceguids, 376, v10);
    goto LABEL_61;
  }
  p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  if ( v15 <= 0x40 )
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_10:
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_12;
  }
  if ( v15 <= 0x100 )
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_10;
  }
  if ( v15 <= 0x400 )
  {
    p_WaitListHead = &Lookaside;
    goto LABEL_10;
  }
  if ( v15 <= 0x800 )
  {
    p_WaitListHead = &stru_1400B0180;
    goto LABEL_10;
  }
  Pool2 = (_DWORD *)ExAllocatePool2(64, v15, 2053731191, v14);
LABEL_12:
  v18 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( !Pool2 )
    goto LABEL_59;
  Pool2[2] = 2053731191;
  v19 = (char *)(Pool2 + 4);
  *(_QWORD *)Pool2 = p_WaitListHead;
  memset(Pool2 + 4, 0, v10 + 376);
  *(_OWORD *)v19 = *(_OWORD *)&a1->uSSIDLength;
  *((_OWORD *)v19 + 1) = *(_OWORD *)&a1->ucSSID[12];
  *((_DWORD *)v19 + 8) = *(_DWORD *)&a1->ucSSID[28];
  *((_DWORD *)v19 + 93) = 376;
  *((_DWORD *)v19 + 92) = v10;
  memmove(v19 + 376, a3, v10);
  Src = 0;
  if ( (unsigned int)GetIEsForFTContext(
                       a2,
                       a5,
                       a6,
                       a7,
                       a8,
                       &v45,
                       (unsigned __int8 **)&Src,
                       (struct NWF_FT_CONTEXT *)v19) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 423, WPP_e90d411d816e312466897e39e745b158_Traceguids);
LABEL_56:
    if ( *v18 )
      ExFreeToNPagedLookasideList(*v18, v18);
    else
      ExFreePoolWithTag(v18, *((_DWORD *)v18 + 2));
LABEL_61:
    v19 = 0;
    goto LABEL_62;
  }
  v20 = *((_QWORD *)v19 + 9);
  *((_QWORD *)v19 + 18) = v20 + 2;
  *((_QWORD *)v19 + 19) = v20 + 4;
  *((_QWORD *)v19 + 20) = v20 + 20;
  *((_QWORD *)v19 + 21) = v20 + 52;
  if ( a2 )
  {
    v21 = a9 == 0;
    *(_WORD *)(v20 + 2) = 0;
    *(_BYTE *)(*((_QWORD *)v19 + 18) + 1LL) = !v21 + 3;
  }
  v22 = *((_DWORD *)v19 + 14);
  if ( v22 >= 0x56 )
  {
    v23 = 84;
    v24 = (unsigned __int8 *)(*((_QWORD *)v19 + 9) + 84LL);
    do
    {
      if ( v22 < v24[1] + (unsigned __int64)v23 + 2 )
        break;
      GetFTSubElementInfo(v19[56] - v23, v24, (struct NWF_FT_CONTEXT *)v19);
      v25 = v24[1];
      v23 += v25 + 2;
      v22 = *((_DWORD *)v19 + 14);
      v24 += v25 + 2;
    }
    while ( v22 >= (unsigned __int64)v23 + 2 );
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_lll(
      WPP_GLOBAL_Control->AttachedDevice,
      424,
      WPP_e90d411d816e312466897e39e745b158_Traceguids,
      (unsigned __int8)v19[219],
      (unsigned __int8)v19[220],
      (unsigned __int8)v19[221]);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_lll(
        WPP_GLOBAL_Control->AttachedDevice,
        425,
        WPP_e90d411d816e312466897e39e745b158_Traceguids,
        (unsigned __int8)v19[222],
        (unsigned __int8)v19[222],
        (unsigned __int8)v19[312]);
  }
  if ( !*((_QWORD *)v19 + 23) || !*((_QWORD *)v19 + 22) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 426, WPP_e90d411d816e312466897e39e745b158_Traceguids);
    goto LABEL_56;
  }
  v26 = (const unsigned __int8 *)Src;
  v27 = v45 & 0x40;
  v28 = (unsigned __int8)(*((_BYTE *)Src + 1) + 2);
  if ( Src == a5 )
    v29 = v28 + (v27 == 0 ? 2 : 0) + (~(unsigned __int8)(v45 >> 4) & 2 | 0x10) - 16 * v19[216];
  else
    v29 = *((_BYTE *)Src + 1) + 2;
  LODWORD(Src) = v29;
  v30 = v29 + 16;
  if ( v30 > 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    if ( v30 > 0x100 )
      p_DeviceQueue = &Lookaside;
  }
  v31 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
  if ( !v31 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        427,
        WPP_e90d411d816e312466897e39e745b158_Traceguids,
        (unsigned int)Src,
        a6);
    goto LABEL_56;
  }
  v32 = v31 + 16;
  *(_QWORD *)v31 = p_DeviceQueue;
  *((_DWORD *)v31 + 2) = 2053731191;
  memset(v31 + 16, 0, v29);
  v33 = *((_QWORD *)v19 + 11);
  if ( v33 )
  {
    v34 = v33 - 16;
    if ( *(_QWORD *)v34 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v34, (PVOID)v34);
    else
      ExFreePoolWithTag((PVOID)v34, *(_DWORD *)(v34 + 8));
  }
  *((_QWORD *)v19 + 11) = v32;
  *((_QWORD *)v19 + 10) = v32;
  if ( v26 == a5 )
  {
    if ( !v27 )
      v19[218] = v28 + (~(unsigned __int8)(v45 >> 4) & 2);
    v35 = v28;
    if ( (unsigned __int8)v19[218] < (unsigned __int8)v28 )
      v35 = v19[218];
    memmove(v32, v26, v35);
    *((_DWORD *)v19 + 15) = (_DWORD)Src;
    v32[1] = v29 - 2;
    *(_WORD *)&v32[(unsigned __int8)v19[218]] = 1;
    v36 = v19[218];
    v37 = v36 + 2;
    if ( *((_WORD *)v19 + 108) && v28 >= (unsigned __int64)v37 + 16 )
    {
      *(_OWORD *)&v32[v37] = *(_OWORD *)&v26[v37];
      v36 = *((_BYTE *)v18 + 234);
    }
    v38 = v37 + 16 * v19[216];
    if ( (unsigned __int8)v28 > v38 )
      memmove(&v32[v36 + 18], &v26[v38], v28 - v38);
    *((_QWORD *)v19 + 12) = &v32[(unsigned __int8)v19[218] + 2];
  }
  else
  {
    memmove(v32, v26, v28);
    *((_DWORD *)v19 + 15) = v28;
    v39 = *((unsigned __int8 *)v18 + 234);
    if ( a2 )
    {
      *(_OWORD *)(v19 + 104) = *(_OWORD *)&v32[v39 + 2];
    }
    else
    {
      v40 = &v32[v39 + 2];
      *(_OWORD *)(v19 + 120) = *v40;
      *((_QWORD *)v19 + 12) = v40;
    }
  }
LABEL_62:
  FreeRSNIEContent((struct DOT11_RSN_IE_INFO *)v43);
  return (struct NWF_FT_CONTEXT *)v19;
}

```

## disassembly

```asm
0x14004967c  mov     rax, rsp
0x14004967f  mov     [rax+8], rbx
0x140049683  mov     [rax+10h], edx
0x140049686  push    rbp
0x140049687  push    rsi
0x140049688  push    rdi
0x140049689  push    r12
0x14004968b  push    r13
0x14004968d  push    r14
0x14004968f  push    r15
0x140049691  sub     rsp, 0A0h
0x140049698  xor     ebx, ebx
0x14004969a  mov     esi, r9d
0x14004969d  mov     r15, r8
0x1400496a0  mov     [rax+20h], ebx
0x1400496a3  mov     r13d, edx
0x1400496a6  mov     rbp, rcx
0x1400496a9  xor     edx, edx; Val
0x1400496ab  lea     rcx, [rsp+0D8h+var_88]; void *
0x1400496b0  lea     r8d, [rbx+48h]; Size
0x1400496b4  call    memset
0x1400496b9  lea     eax, [rsi+188h]
0x1400496bf  cmp     eax, 10h
0x1400496c2  jb      loc_140049C16
0x1400496c8  lea     r12, WPP_MAIN_CB.DeviceQueue
0x1400496cf  mov     edi, 7A697377h
0x1400496d4  cmp     eax, 40h ; '@'
0x1400496d7  ja      short loc_1400496DE
0x1400496d9  mov     rbx, r12
0x1400496dc  jmp     short loc_14004970C
0x1400496de  cmp     eax, 100h
0x1400496e3  ja      short loc_1400496EE
0x1400496e5  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400496ec  jmp     short loc_14004970C
0x1400496ee  cmp     eax, 400h
0x1400496f3  ja      short loc_1400496FE
0x1400496f5  lea     rbx, Lookaside
0x1400496fc  jmp     short loc_14004970C
0x1400496fe  cmp     eax, 800h
0x140049703  ja      short loc_14004971D
0x140049705  lea     rbx, stru_1400B0180
0x14004970c  mov     rcx, rbx; Lookaside
0x14004970f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140049716  nop     dword ptr [rax+rax+00h]
0x14004971b  jmp     short loc_140049733
0x14004971d  mov     edx, eax
0x14004971f  mov     r8d, edi
0x140049722  mov     ecx, 40h ; '@'
0x140049727  call    cs:__imp_ExAllocatePool2
0x14004972e  nop     dword ptr [rax+rax+00h]
0x140049733  mov     r14, rax
0x140049736  test    rax, rax
0x140049739  jz      loc_140049C16
0x14004973f  mov     [rax+8], edi
0x140049742  lea     r8, [rsi+178h]; Size
0x140049749  lea     rdi, [rax+10h]
0x14004974d  mov     [rax], rbx
0x140049750  mov     rcx, rdi; void *
0x140049753  xor     edx, edx; Val
0x140049755  call    memset
0x14004975a  movups  xmm0, xmmword ptr [rbp+0]
0x14004975e  lea     rcx, [rdi+178h]; void *
0x140049765  mov     r8, rsi; Size
0x140049768  mov     rdx, r15; Src
0x14004976b  movups  xmmword ptr [rdi], xmm0
0x14004976e  movups  xmm1, xmmword ptr [rbp+10h]
0x140049772  movups  xmmword ptr [rdi+10h], xmm1
0x140049776  mov     eax, [rbp+20h]
0x140049779  mov     [rdi+20h], eax
0x14004977c  mov     dword ptr [rdi+174h], 178h
0x140049786  mov     [rdi+170h], esi
0x14004978c  call    memmove
0x140049791  mov     r9, [rsp+0D8h+arg_30]; unsigned __int8 *
0x140049799  lea     rax, [rsp+0D8h+Src]
0x14004979e  mov     r8d, [rsp+0D8h+arg_28]; unsigned int
0x1400497a6  xor     ebx, ebx
0x1400497a8  mov     rdx, [rsp+0D8h+arg_20]; unsigned __int8 *
0x1400497b0  mov     ecx, r13d; int
0x1400497b3  mov     [rsp+0D8h+var_A0], rdi; struct NWF_FT_CONTEXT *
0x1400497b8  mov     [rsp+0D8h+var_A8], rax; unsigned __int8 **
0x1400497bd  lea     rax, [rsp+0D8h+arg_18]
0x1400497c5  mov     [rsp+0D8h+var_B0], rax; unsigned int *
0x1400497ca  mov     eax, [rsp+0D8h+arg_38]
0x1400497d1  mov     [rsp+0D8h+var_B8], eax; unsigned int
0x1400497d5  mov     [rsp+0D8h+Src], rbx
0x1400497da  call    ?GetIEsForFTContext@@YAHHPEBEK0KAEAKPEAPEAEPEAUNWF_FT_CONTEXT@@@Z; GetIEsForFTContext(int,uchar const *,ulong,uchar const *,ulong,ulong &,uchar * *,NWF_FT_CONTEXT *)
0x1400497df  test    eax, eax
0x1400497e1  jz      short loc_140049814
0x1400497e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400497ea  lea     rbx, WPP_GLOBAL_Control
0x1400497f1  cmp     rcx, rbx
0x1400497f4  jz      loc_140049BE8
0x1400497fa  mov     rcx, [rcx+18h]
0x1400497fe  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140049805  mov     edx, 1A7h
0x14004980a  call    WPP_SF_
0x14004980f  jmp     loc_140049BE8
0x140049814  mov     rcx, [rdi+48h]
0x140049818  lea     rax, [rcx+4]
0x14004981c  lea     rdx, [rcx+2]
0x140049820  mov     [rdi+90h], rdx
0x140049827  mov     [rdi+98h], rax
0x14004982e  lea     rax, [rcx+14h]
0x140049832  mov     [rdi+0A0h], rax
0x140049839  lea     rax, [rcx+34h]
0x14004983d  mov     [rdi+0A8h], rax
0x140049844  test    r13d, r13d
0x140049847  jz      short loc_140049862
0x140049849  cmp     [rsp+0D8h+arg_40], ebx
0x140049850  mov     [rdx], bx
0x140049853  mov     rcx, [rdi+90h]
0x14004985a  setnbe  al
0x14004985d  add     al, 3
0x14004985f  mov     [rcx+1], al
0x140049862  mov     r8d, [rdi+38h]
0x140049866  cmp     r8d, 56h ; 'V'
0x14004986a  jb      short loc_1400498BF
0x14004986c  mov     rbx, [rdi+48h]
0x140049870  mov     esi, 54h ; 'T'
0x140049875  add     rbx, rsi
0x140049878  movzx   ecx, byte ptr [rbx+1]
0x14004987c  mov     edx, esi
0x14004987e  add     rdx, 2
0x140049882  mov     eax, r8d
0x140049885  add     rdx, rcx
0x140049888  cmp     rax, rdx
0x14004988b  jb      short loc_1400498BF
0x14004988d  mov     cl, [rdi+38h]
0x140049890  mov     r8, rdi; struct NWF_FT_CONTEXT *
0x140049893  sub     cl, sil; unsigned __int8
0x140049896  mov     rdx, rbx; unsigned __int8 *
0x140049899  call    ?GetFTSubElementInfo@@YAXEPEAEPEAUNWF_FT_CONTEXT@@@Z; GetFTSubElementInfo(uchar,uchar *,NWF_FT_CONTEXT *)
0x14004989e  movzx   eax, byte ptr [rbx+1]
0x1400498a2  add     esi, 2
0x1400498a5  mov     ecx, [rdi+38h]
0x1400498a8  add     esi, eax
0x1400498aa  add     rax, 2
0x1400498ae  mov     r8d, ecx
0x1400498b1  add     rbx, rax
0x1400498b4  mov     eax, esi
0x1400498b6  add     rax, 2
0x1400498ba  cmp     rcx, rax
0x1400498bd  jnb     short loc_140049878
0x1400498bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400498c6  lea     rbx, WPP_GLOBAL_Control
0x1400498cd  cmp     rcx, rbx
0x1400498d0  jz      short loc_140049940
0x1400498d2  movzx   r8d, byte ptr [rdi+0DCh]
0x1400498da  mov     edx, 1A8h
0x1400498df  movzx   eax, byte ptr [rdi+0DDh]
0x1400498e6  movzx   r9d, byte ptr [rdi+0DBh]
0x1400498ee  mov     rcx, [rcx+18h]
0x1400498f2  mov     dword ptr [rsp+0D8h+var_B0], eax
0x1400498f6  mov     [rsp+0D8h+var_B8], r8d
0x1400498fb  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140049902  call    WPP_SF_lll
0x140049907  mov     rcx, cs:WPP_GLOBAL_Control
0x14004990e  cmp     rcx, rbx
0x140049911  jz      short loc_140049940
0x140049913  movzx   eax, byte ptr [rdi+138h]
0x14004991a  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140049921  movzx   r9d, byte ptr [rdi+0DEh]
0x140049929  mov     edx, 1A9h
0x14004992e  mov     rcx, [rcx+18h]
0x140049932  mov     dword ptr [rsp+0D8h+var_B0], eax
0x140049936  mov     [rsp+0D8h+var_B8], r9d
0x14004993b  call    WPP_SF_lll
0x140049940  mov     r9, [rdi+0B8h]
0x140049947  xor     ecx, ecx
0x140049949  test    r9, r9
0x14004994c  jz      loc_140049BBB
0x140049952  cmp     [rdi+0B0h], rcx
0x140049959  jz      loc_140049BBB
0x14004995f  mov     r15, [rsp+0D8h+Src]
0x140049964  mov     esi, [rsp+0D8h+arg_18]
0x14004996b  mov     r13d, esi
0x14004996e  and     r13d, 40h
0x140049972  mov     al, [r15+1]
0x140049976  add     al, 2
0x140049978  movzx   ebp, al
0x14004997b  cmp     r15, [rsp+0D8h+arg_20]
0x140049983  jnz     short loc_1400499B3
0x140049985  mov     al, [rdi+0D8h]
0x14004998b  shr     esi, 4
0x14004998e  not     sil
0x140049991  shl     al, 4
0x140049994  and     sil, 2
0x140049998  or      sil, 10h
0x14004999c  sub     sil, al
0x14004999f  mov     eax, r13d
0x1400499a2  neg     eax
0x1400499a4  sbb     cl, cl
0x1400499a6  not     cl
0x1400499a8  and     cl, 2
0x1400499ab  add     sil, cl
0x1400499ae  add     sil, bpl
0x1400499b1  jmp     short loc_1400499B6
0x1400499b3  mov     sil, bpl
0x1400499b6  movzx   r8d, sil
0x1400499ba  mov     dword ptr [rsp+0D8h+Src], r8d
0x1400499bf  lea     eax, [r8+10h]
0x1400499c3  cmp     eax, 10h
0x1400499c6  jb      loc_140049B8A
0x1400499cc  cmp     eax, 40h ; '@'
0x1400499cf  jbe     short loc_1400499E8
0x1400499d1  cmp     eax, 100h
0x1400499d6  lea     r12, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400499dd  lea     rax, Lookaside
0x1400499e4  cmova   r12, rax
0x1400499e8  mov     rcx, r12; Lookaside
0x1400499eb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400499f2  nop     dword ptr [rax+rax+00h]
0x1400499f7  test    rax, rax
0x1400499fa  jz      loc_140049B85
0x140049a00  lea     rbx, [rax+10h]
0x140049a04  movzx   r8d, sil; Size
0x140049a08  mov     rcx, rbx; void *
0x140049a0b  mov     [rax], r12
0x140049a0e  xor     edx, edx; Val
0x140049a10  mov     dword ptr [rax+8], 7A697377h
0x140049a17  call    memset
0x140049a1c  mov     rcx, [rdi+58h]
0x140049a20  xor     r12d, r12d
0x140049a23  test    rcx, rcx
0x140049a26  jz      short loc_140049A57
0x140049a28  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140049a2c  mov     rax, [rcx]
0x140049a2f  test    rax, rax
0x140049a32  jz      short loc_140049A48
0x140049a34  mov     rdx, rcx; Entry
0x140049a37  mov     rcx, rax; Lookaside
0x140049a3a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140049a41  nop     dword ptr [rax+rax+00h]
0x140049a46  jmp     short loc_140049A57
0x140049a48  mov     edx, [rcx+8]; Tag
0x140049a4b  call    cs:__imp_ExFreePoolWithTag
0x140049a52  nop     dword ptr [rax+rax+00h]
0x140049a57  mov     [rdi+58h], rbx
0x140049a5b  mov     [rdi+50h], rbx
0x140049a5f  cmp     r15, [rsp+0D8h+arg_20]
0x140049a67  jnz     loc_140049B3B
0x140049a6d  test    r13d, r13d
0x140049a70  jnz     short loc_140049A89
0x140049a72  mov     eax, [rsp+0D8h+arg_18]
0x140049a79  shr     eax, 4
0x140049a7c  not     al
0x140049a7e  and     al, 2
0x140049a80  add     al, bpl
0x140049a83  mov     [rdi+0DAh], al
0x140049a89  movzx   ecx, byte ptr [rdi+0DAh]
0x140049a90  mov     eax, ebp
0x140049a92  cmp     cl, bpl
0x140049a95  mov     rdx, r15; Src
0x140049a98  cmovb   eax, ecx
0x140049a9b  mov     rcx, rbx; void *
0x140049a9e  movzx   r8d, al; Size
0x140049aa2  call    memmove
0x140049aa7  mov     eax, dword ptr [rsp+0D8h+Src]
0x140049aab  sub     sil, 2
0x140049aaf  mov     [rdi+3Ch], eax
0x140049ab2  mov     [rbx+1], sil
0x140049ab6  movzx   eax, byte ptr [rdi+0DAh]
0x140049abd  mov     word ptr [rax+rbx], 1
0x140049ac3  mov     r9b, [rdi+0DAh]
0x140049aca  lea     r8d, [r9+2]
0x140049ace  cmp     [rdi+0D8h], r12w
0x140049ad6  jbe     short loc_140049AF6
0x140049ad8  movzx   edx, r8b
0x140049adc  lea     rcx, [rdx+10h]
0x140049ae0  cmp     rbp, rcx
0x140049ae3  jb      short loc_140049AF6
0x140049ae5  movups  xmm0, xmmword ptr [rdx+r15]
0x140049aea  movdqu  xmmword ptr [rdx+rbx], xmm0
0x140049aef  mov     r9b, [r14+0EAh]
0x140049af6  mov     al, [rdi+0D8h]
0x140049afc  shl     al, 4
0x140049aff  add     al, r8b
0x140049b02  cmp     bpl, al
0x140049b05  jbe     short loc_140049B24
0x140049b07  movzx   eax, al
0x140049b0a  mov     r8, rbp
0x140049b0d  movzx   ecx, r9b
0x140049b11  sub     r8, rax; Size
0x140049b14  add     rcx, 12h
0x140049b18  add     rcx, rbx; void *
0x140049b1b  lea     rdx, [rax+r15]; Src
0x140049b1f  call    memmove
0x140049b24  movzx   ecx, byte ptr [rdi+0DAh]
0x140049b2b  add     rcx, 2
0x140049b2f  add     rcx, rbx
0x140049b32  mov     [rdi+60h], rcx
0x140049b36  jmp     loc_140049C48
0x140049b3b  mov     r8, rbp; Size
0x140049b3e  mov     rdx, r15; Src
0x140049b41  mov     rcx, rbx; void *
0x140049b44  call    memmove
0x140049b49  mov     [rdi+3Ch], ebp
0x140049b4c  movzx   eax, byte ptr [r14+0EAh]
0x140049b54  cmp     [rsp+0D8h+arg_8], r12d
0x140049b5c  jz      short loc_140049B6D
  ... truncated ...
```
