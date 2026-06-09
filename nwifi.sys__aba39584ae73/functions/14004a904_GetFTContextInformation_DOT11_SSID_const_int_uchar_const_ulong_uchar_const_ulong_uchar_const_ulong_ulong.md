# GetFTContextInformation(_DOT11_SSID const *,int,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,ulong)

- ea: `0x14004a904`
- end: `0x14004aef9`
- name: `?GetFTContextInformation@@YAPEAUNWF_FT_CONTEXT@@PEBU_DOT11_SSID@@HPEBEK1K1KK@Z`
- size: `1525`
- prototype: `struct NWF_FT_CONTEXT *(const struct _DOT11_SSID *, int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140042a1c`
- `0x140046610`
- `0x140047794`
- `0x140047e48`

## callees

- `0x14000d21c`
- `0x140020f20`
- `0x140030244`
- `0x1400314ec`
- `0x140048cc8`
- `0x14004a904`
- `0x14004af00`
- `0x14004b344`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004a997`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ac73`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004a997`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ac73`
- `ntoskrnl!ExAllocatePool2` at `0x14004a9af`
- `ntoskrnl!ExAllocatePool2` at `0x14004a9af`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004acc2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004ae7b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004acc2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004ae7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004acd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ae90`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004acd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ae90`

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
  unsigned int v14; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // r12
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v17; // r14
  char *v18; // rdi
  __int64 v19; // rcx
  bool v20; // zf
  unsigned int v21; // r8d
  unsigned int v22; // esi
  unsigned __int8 *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // r9
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
  v14 = v10 + 400;
  if ( (unsigned int)(v10 + 400) < 0x10 )
  {
LABEL_59:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 422, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, 384, v10);
    goto LABEL_61;
  }
  p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  if ( v14 <= 0x40 )
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_10:
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_12;
  }
  if ( v14 <= 0x100 )
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_10;
  }
  if ( v14 <= 0x400 )
  {
    p_WaitListHead = &Lookaside;
    goto LABEL_10;
  }
  if ( v14 <= 0x800 )
  {
    p_WaitListHead = &stru_1400B31C0;
    goto LABEL_10;
  }
  Pool2 = (_DWORD *)ExAllocatePool2(64, v14, 2053731191);
LABEL_12:
  v17 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( !Pool2 )
    goto LABEL_59;
  Pool2[2] = 2053731191;
  v18 = (char *)(Pool2 + 4);
  *(_QWORD *)Pool2 = p_WaitListHead;
  memset(Pool2 + 4, 0, v10 + 384);
  *(_OWORD *)v18 = *(_OWORD *)&a1->uSSIDLength;
  *((_OWORD *)v18 + 1) = *(_OWORD *)&a1->ucSSID[12];
  *((_DWORD *)v18 + 8) = *(_DWORD *)&a1->ucSSID[28];
  *((_DWORD *)v18 + 93) = 384;
  *((_DWORD *)v18 + 92) = v10;
  memmove(v18 + 384, a3, v10);
  Src = 0;
  if ( (unsigned int)GetIEsForFTContext(
                       a2,
                       a5,
                       a6,
                       a7,
                       a8,
                       &v45,
                       (unsigned __int8 **)&Src,
                       (struct NWF_FT_CONTEXT *)v18) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 423, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
LABEL_56:
    if ( *v17 )
      ExFreeToNPagedLookasideList(*v17, v17);
    else
      ExFreePoolWithTag(v17, *((_DWORD *)v17 + 2));
LABEL_61:
    v18 = 0;
    goto LABEL_62;
  }
  v19 = *((_QWORD *)v18 + 9);
  *((_QWORD *)v18 + 18) = v19 + 2;
  *((_QWORD *)v18 + 19) = v19 + 4;
  *((_QWORD *)v18 + 20) = v19 + 20;
  *((_QWORD *)v18 + 21) = v19 + 52;
  if ( a2 )
  {
    v20 = a9 == 0;
    *(_WORD *)(v19 + 2) = 0;
    *(_BYTE *)(*((_QWORD *)v18 + 18) + 1LL) = !v20 + 3;
  }
  v21 = *((_DWORD *)v18 + 14);
  if ( v21 >= 0x56 )
  {
    v22 = 84;
    v23 = (unsigned __int8 *)(*((_QWORD *)v18 + 9) + 84LL);
    do
    {
      if ( v21 < v23[1] + (unsigned __int64)v22 + 2 )
        break;
      GetFTSubElementInfo(v18[56] - v22, v23, (struct NWF_FT_CONTEXT *)v18);
      v24 = v23[1];
      v22 += v24 + 2;
      v21 = *((_DWORD *)v18 + 14);
      v23 += v24 + 2;
    }
    while ( v21 >= (unsigned __int64)v22 + 2 );
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_lll(
      WPP_GLOBAL_Control->AttachedDevice,
      424,
      WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
      (unsigned __int8)v18[219],
      (unsigned __int8)v18[220],
      (unsigned __int8)v18[221]);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_lll(
        WPP_GLOBAL_Control->AttachedDevice,
        425,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        (unsigned __int8)v18[222],
        (unsigned __int8)v18[222],
        (unsigned __int8)v18[312]);
  }
  v25 = *((_QWORD *)v18 + 23);
  if ( !v25 || !*((_QWORD *)v18 + 22) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        426,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        v25,
        *((_QWORD *)v18 + 22));
    goto LABEL_56;
  }
  v26 = (const unsigned __int8 *)Src;
  v27 = v45 & 0x40;
  v28 = (unsigned __int8)(*((_BYTE *)Src + 1) + 2);
  if ( Src == a5 )
    v29 = v28 + (v27 == 0 ? 2 : 0) + (~(unsigned __int8)(v45 >> 4) & 2 | 0x10) - 16 * v18[216];
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
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        (unsigned int)Src,
        a6);
    goto LABEL_56;
  }
  v32 = v31 + 16;
  *(_QWORD *)v31 = p_DeviceQueue;
  *((_DWORD *)v31 + 2) = 2053731191;
  memset(v31 + 16, 0, v29);
  v33 = *((_QWORD *)v18 + 11);
  if ( v33 )
  {
    v34 = v33 - 16;
    if ( *(_QWORD *)v34 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v34, (PVOID)v34);
    else
      ExFreePoolWithTag((PVOID)v34, *(_DWORD *)(v34 + 8));
  }
  *((_QWORD *)v18 + 11) = v32;
  *((_QWORD *)v18 + 10) = v32;
  if ( v26 == a5 )
  {
    if ( !v27 )
      v18[218] = v28 + (~(unsigned __int8)(v45 >> 4) & 2);
    v35 = v28;
    if ( (unsigned __int8)v18[218] < (unsigned __int8)v28 )
      v35 = v18[218];
    memmove(v32, v26, v35);
    *((_DWORD *)v18 + 15) = (_DWORD)Src;
    v32[1] = v29 - 2;
    *(_WORD *)&v32[(unsigned __int8)v18[218]] = 1;
    v36 = v18[218];
    v37 = v36 + 2;
    if ( *((_WORD *)v18 + 108) && v28 >= (unsigned __int64)v37 + 16 )
    {
      *(_OWORD *)&v32[v37] = *(_OWORD *)&v26[v37];
      v36 = *((_BYTE *)v17 + 234);
    }
    v38 = v37 + 16 * v18[216];
    if ( (unsigned __int8)v28 > v38 )
      memmove(&v32[v36 + 18], &v26[v38], v28 - v38);
    *((_QWORD *)v18 + 12) = &v32[(unsigned __int8)v18[218] + 2];
  }
  else
  {
    memmove(v32, v26, v28);
    *((_DWORD *)v18 + 15) = v28;
    v39 = *((unsigned __int8 *)v17 + 234);
    if ( a2 )
    {
      *(_OWORD *)(v18 + 104) = *(_OWORD *)&v32[v39 + 2];
    }
    else
    {
      v40 = &v32[v39 + 2];
      *(_OWORD *)(v18 + 120) = *v40;
      *((_QWORD *)v18 + 12) = v40;
    }
  }
LABEL_62:
  FreeRSNIEContent((struct DOT11_RSN_IE_INFO *)v43);
  return (struct NWF_FT_CONTEXT *)v18;
}

```

## disassembly

```asm
0x14004a904  mov     rax, rsp
0x14004a907  mov     [rax+8], rbx
0x14004a90b  mov     [rax+10h], edx
0x14004a90e  push    rbp
0x14004a90f  push    rsi
0x14004a910  push    rdi
0x14004a911  push    r12
0x14004a913  push    r13
0x14004a915  push    r14
0x14004a917  push    r15
0x14004a919  sub     rsp, 0A0h
0x14004a920  xor     ebx, ebx
0x14004a922  mov     esi, r9d
0x14004a925  mov     r15, r8
0x14004a928  mov     [rax+20h], ebx
0x14004a92b  mov     r13d, edx
0x14004a92e  mov     rbp, rcx
0x14004a931  xor     edx, edx; Val
0x14004a933  lea     rcx, [rsp+0D8h+var_88]; void *
0x14004a938  lea     r8d, [rbx+48h]; Size
0x14004a93c  call    memset
0x14004a941  lea     eax, [rsi+190h]
0x14004a947  cmp     eax, 10h
0x14004a94a  jb      loc_14004AE9E
0x14004a950  lea     r12, WPP_MAIN_CB.DeviceQueue
0x14004a957  mov     edi, 7A697377h
0x14004a95c  cmp     eax, 40h ; '@'
0x14004a95f  ja      short loc_14004A966
0x14004a961  mov     rbx, r12
0x14004a964  jmp     short loc_14004A994
0x14004a966  cmp     eax, 100h
0x14004a96b  ja      short loc_14004A976
0x14004a96d  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004a974  jmp     short loc_14004A994
0x14004a976  cmp     eax, 400h
0x14004a97b  ja      short loc_14004A986
0x14004a97d  lea     rbx, Lookaside
0x14004a984  jmp     short loc_14004A994
0x14004a986  cmp     eax, 800h
0x14004a98b  ja      short loc_14004A9A5
0x14004a98d  lea     rbx, stru_1400B31C0
0x14004a994  mov     rcx, rbx; Lookaside
0x14004a997  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004a99e  nop     dword ptr [rax+rax+00h]
0x14004a9a3  jmp     short loc_14004A9BB
0x14004a9a5  mov     edx, eax
0x14004a9a7  mov     r8d, edi
0x14004a9aa  mov     ecx, 40h ; '@'
0x14004a9af  call    cs:__imp_ExAllocatePool2
0x14004a9b6  nop     dword ptr [rax+rax+00h]
0x14004a9bb  mov     r14, rax
0x14004a9be  test    rax, rax
0x14004a9c1  jz      loc_14004AE9E
0x14004a9c7  mov     [rax+8], edi
0x14004a9ca  lea     r8, [rsi+180h]; Size
0x14004a9d1  lea     rdi, [rax+10h]
0x14004a9d5  mov     [rax], rbx
0x14004a9d8  mov     rcx, rdi; void *
0x14004a9db  xor     edx, edx; Val
0x14004a9dd  call    memset
0x14004a9e2  movups  xmm0, xmmword ptr [rbp+0]
0x14004a9e6  lea     rcx, [rdi+180h]; void *
0x14004a9ed  mov     r8, rsi; Size
0x14004a9f0  mov     rdx, r15; Src
0x14004a9f3  movups  xmmword ptr [rdi], xmm0
0x14004a9f6  movups  xmm1, xmmword ptr [rbp+10h]
0x14004a9fa  movups  xmmword ptr [rdi+10h], xmm1
0x14004a9fe  mov     eax, [rbp+20h]
0x14004aa01  mov     [rdi+20h], eax
0x14004aa04  mov     dword ptr [rdi+174h], 180h
0x14004aa0e  mov     [rdi+170h], esi
0x14004aa14  call    memmove
0x14004aa19  mov     r9, [rsp+0D8h+arg_30]; unsigned __int8 *
0x14004aa21  lea     rax, [rsp+0D8h+Src]
0x14004aa26  mov     r8d, [rsp+0D8h+arg_28]; unsigned int
0x14004aa2e  xor     ebx, ebx
0x14004aa30  mov     rdx, [rsp+0D8h+arg_20]; unsigned __int8 *
0x14004aa38  mov     ecx, r13d; int
0x14004aa3b  mov     [rsp+0D8h+var_A0], rdi; struct NWF_FT_CONTEXT *
0x14004aa40  mov     [rsp+0D8h+var_A8], rax; unsigned __int8 **
0x14004aa45  lea     rax, [rsp+0D8h+arg_18]
0x14004aa4d  mov     [rsp+0D8h+var_B0], rax; unsigned int *
0x14004aa52  mov     eax, [rsp+0D8h+arg_38]
0x14004aa59  mov     [rsp+0D8h+var_B8], eax; unsigned int
0x14004aa5d  mov     [rsp+0D8h+Src], rbx
0x14004aa62  call    ?GetIEsForFTContext@@YAHHPEBEK0KAEAKPEAPEAEPEAUNWF_FT_CONTEXT@@@Z; GetIEsForFTContext(int,uchar const *,ulong,uchar const *,ulong,ulong &,uchar * *,NWF_FT_CONTEXT *)
0x14004aa67  test    eax, eax
0x14004aa69  jz      short loc_14004AA9C
0x14004aa6b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004aa72  lea     rbx, WPP_GLOBAL_Control
0x14004aa79  cmp     rcx, rbx
0x14004aa7c  jz      loc_14004AE70
0x14004aa82  mov     rcx, [rcx+18h]
0x14004aa86  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004aa8d  mov     edx, 1A7h
0x14004aa92  call    WPP_SF_
0x14004aa97  jmp     loc_14004AE70
0x14004aa9c  mov     rcx, [rdi+48h]
0x14004aaa0  lea     rax, [rcx+4]
0x14004aaa4  lea     rdx, [rcx+2]
0x14004aaa8  mov     [rdi+90h], rdx
0x14004aaaf  mov     [rdi+98h], rax
0x14004aab6  lea     rax, [rcx+14h]
0x14004aaba  mov     [rdi+0A0h], rax
0x14004aac1  lea     rax, [rcx+34h]
0x14004aac5  mov     [rdi+0A8h], rax
0x14004aacc  test    r13d, r13d
0x14004aacf  jz      short loc_14004AAEA
0x14004aad1  cmp     [rsp+0D8h+arg_40], ebx
0x14004aad8  mov     [rdx], bx
0x14004aadb  mov     rcx, [rdi+90h]
0x14004aae2  setnbe  al
0x14004aae5  add     al, 3
0x14004aae7  mov     [rcx+1], al
0x14004aaea  mov     r8d, [rdi+38h]
0x14004aaee  cmp     r8d, 56h ; 'V'
0x14004aaf2  jb      short loc_14004AB47
0x14004aaf4  mov     rbx, [rdi+48h]
0x14004aaf8  mov     esi, 54h ; 'T'
0x14004aafd  add     rbx, rsi
0x14004ab00  movzx   ecx, byte ptr [rbx+1]
0x14004ab04  mov     edx, esi
0x14004ab06  add     rdx, 2
0x14004ab0a  mov     eax, r8d
0x14004ab0d  add     rdx, rcx
0x14004ab10  cmp     rax, rdx
0x14004ab13  jb      short loc_14004AB47
0x14004ab15  mov     cl, [rdi+38h]
0x14004ab18  mov     r8, rdi; struct NWF_FT_CONTEXT *
0x14004ab1b  sub     cl, sil; unsigned __int8
0x14004ab1e  mov     rdx, rbx; unsigned __int8 *
0x14004ab21  call    ?GetFTSubElementInfo@@YAXEPEAEPEAUNWF_FT_CONTEXT@@@Z; GetFTSubElementInfo(uchar,uchar *,NWF_FT_CONTEXT *)
0x14004ab26  movzx   eax, byte ptr [rbx+1]
0x14004ab2a  add     esi, 2
0x14004ab2d  mov     ecx, [rdi+38h]
0x14004ab30  add     esi, eax
0x14004ab32  add     rax, 2
0x14004ab36  mov     r8d, ecx
0x14004ab39  add     rbx, rax
0x14004ab3c  mov     eax, esi
0x14004ab3e  add     rax, 2
0x14004ab42  cmp     rcx, rax
0x14004ab45  jnb     short loc_14004AB00
0x14004ab47  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ab4e  lea     rbx, WPP_GLOBAL_Control
0x14004ab55  cmp     rcx, rbx
0x14004ab58  jz      short loc_14004ABC8
0x14004ab5a  movzx   r8d, byte ptr [rdi+0DCh]
0x14004ab62  mov     edx, 1A8h
0x14004ab67  movzx   eax, byte ptr [rdi+0DDh]
0x14004ab6e  movzx   r9d, byte ptr [rdi+0DBh]
0x14004ab76  mov     rcx, [rcx+18h]
0x14004ab7a  mov     dword ptr [rsp+0D8h+var_B0], eax
0x14004ab7e  mov     [rsp+0D8h+var_B8], r8d
0x14004ab83  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004ab8a  call    WPP_SF_lll
0x14004ab8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ab96  cmp     rcx, rbx
0x14004ab99  jz      short loc_14004ABC8
0x14004ab9b  movzx   eax, byte ptr [rdi+138h]
0x14004aba2  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004aba9  movzx   r9d, byte ptr [rdi+0DEh]
0x14004abb1  mov     edx, 1A9h
0x14004abb6  mov     rcx, [rcx+18h]
0x14004abba  mov     dword ptr [rsp+0D8h+var_B0], eax
0x14004abbe  mov     [rsp+0D8h+var_B8], r9d
0x14004abc3  call    WPP_SF_lll
0x14004abc8  mov     r9, [rdi+0B8h]
0x14004abcf  xor     ecx, ecx
0x14004abd1  test    r9, r9
0x14004abd4  jz      loc_14004AE43
0x14004abda  cmp     [rdi+0B0h], rcx
0x14004abe1  jz      loc_14004AE43
0x14004abe7  mov     r15, [rsp+0D8h+Src]
0x14004abec  mov     esi, [rsp+0D8h+arg_18]
0x14004abf3  mov     r13d, esi
0x14004abf6  and     r13d, 40h
0x14004abfa  mov     al, [r15+1]
0x14004abfe  add     al, 2
0x14004ac00  movzx   ebp, al
0x14004ac03  cmp     r15, [rsp+0D8h+arg_20]
0x14004ac0b  jnz     short loc_14004AC3B
0x14004ac0d  mov     al, [rdi+0D8h]
0x14004ac13  shr     esi, 4
0x14004ac16  not     sil
0x14004ac19  shl     al, 4
0x14004ac1c  and     sil, 2
0x14004ac20  or      sil, 10h
0x14004ac24  sub     sil, al
0x14004ac27  mov     eax, r13d
0x14004ac2a  neg     eax
0x14004ac2c  sbb     cl, cl
0x14004ac2e  not     cl
0x14004ac30  and     cl, 2
0x14004ac33  add     sil, cl
0x14004ac36  add     sil, bpl
0x14004ac39  jmp     short loc_14004AC3E
0x14004ac3b  mov     sil, bpl
0x14004ac3e  movzx   r8d, sil
0x14004ac42  mov     dword ptr [rsp+0D8h+Src], r8d
0x14004ac47  lea     eax, [r8+10h]
0x14004ac4b  cmp     eax, 10h
0x14004ac4e  jb      loc_14004AE12
0x14004ac54  cmp     eax, 40h ; '@'
0x14004ac57  jbe     short loc_14004AC70
0x14004ac59  cmp     eax, 100h
0x14004ac5e  lea     r12, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004ac65  lea     rax, Lookaside
0x14004ac6c  cmova   r12, rax
0x14004ac70  mov     rcx, r12; Lookaside
0x14004ac73  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004ac7a  nop     dword ptr [rax+rax+00h]
0x14004ac7f  test    rax, rax
0x14004ac82  jz      loc_14004AE0D
0x14004ac88  lea     rbx, [rax+10h]
0x14004ac8c  movzx   r8d, sil; Size
0x14004ac90  mov     rcx, rbx; void *
0x14004ac93  mov     [rax], r12
0x14004ac96  xor     edx, edx; Val
0x14004ac98  mov     dword ptr [rax+8], 7A697377h
0x14004ac9f  call    memset
0x14004aca4  mov     rcx, [rdi+58h]
0x14004aca8  xor     r12d, r12d
0x14004acab  test    rcx, rcx
0x14004acae  jz      short loc_14004ACDF
0x14004acb0  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004acb4  mov     rax, [rcx]
0x14004acb7  test    rax, rax
0x14004acba  jz      short loc_14004ACD0
0x14004acbc  mov     rdx, rcx; Entry
0x14004acbf  mov     rcx, rax; Lookaside
0x14004acc2  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004acc9  nop     dword ptr [rax+rax+00h]
0x14004acce  jmp     short loc_14004ACDF
0x14004acd0  mov     edx, [rcx+8]; Tag
0x14004acd3  call    cs:__imp_ExFreePoolWithTag
0x14004acda  nop     dword ptr [rax+rax+00h]
0x14004acdf  mov     [rdi+58h], rbx
0x14004ace3  mov     [rdi+50h], rbx
0x14004ace7  cmp     r15, [rsp+0D8h+arg_20]
0x14004acef  jnz     loc_14004ADC3
0x14004acf5  test    r13d, r13d
0x14004acf8  jnz     short loc_14004AD11
0x14004acfa  mov     eax, [rsp+0D8h+arg_18]
0x14004ad01  shr     eax, 4
0x14004ad04  not     al
0x14004ad06  and     al, 2
0x14004ad08  add     al, bpl
0x14004ad0b  mov     [rdi+0DAh], al
0x14004ad11  movzx   ecx, byte ptr [rdi+0DAh]
0x14004ad18  mov     eax, ebp
0x14004ad1a  cmp     cl, bpl
0x14004ad1d  mov     rdx, r15; Src
0x14004ad20  cmovb   eax, ecx
0x14004ad23  mov     rcx, rbx; void *
0x14004ad26  movzx   r8d, al; Size
0x14004ad2a  call    memmove
0x14004ad2f  mov     eax, dword ptr [rsp+0D8h+Src]
0x14004ad33  sub     sil, 2
0x14004ad37  mov     [rdi+3Ch], eax
0x14004ad3a  mov     [rbx+1], sil
0x14004ad3e  movzx   eax, byte ptr [rdi+0DAh]
0x14004ad45  mov     word ptr [rax+rbx], 1
0x14004ad4b  mov     r9b, [rdi+0DAh]
0x14004ad52  lea     r8d, [r9+2]
0x14004ad56  cmp     [rdi+0D8h], r12w
0x14004ad5e  jbe     short loc_14004AD7E
0x14004ad60  movzx   edx, r8b
0x14004ad64  lea     rcx, [rdx+10h]
0x14004ad68  cmp     rbp, rcx
0x14004ad6b  jb      short loc_14004AD7E
0x14004ad6d  movups  xmm0, xmmword ptr [rdx+r15]
0x14004ad72  movdqu  xmmword ptr [rdx+rbx], xmm0
0x14004ad77  mov     r9b, [r14+0EAh]
0x14004ad7e  mov     al, [rdi+0D8h]
0x14004ad84  shl     al, 4
0x14004ad87  add     al, r8b
0x14004ad8a  cmp     bpl, al
0x14004ad8d  jbe     short loc_14004ADAC
0x14004ad8f  movzx   eax, al
0x14004ad92  mov     r8, rbp
0x14004ad95  movzx   ecx, r9b
0x14004ad99  sub     r8, rax; Size
0x14004ad9c  add     rcx, 12h
0x14004ada0  add     rcx, rbx; void *
0x14004ada3  lea     rdx, [rax+r15]; Src
0x14004ada7  call    memmove
0x14004adac  movzx   ecx, byte ptr [rdi+0DAh]
0x14004adb3  add     rcx, 2
0x14004adb7  add     rcx, rbx
0x14004adba  mov     [rdi+60h], rcx
0x14004adbe  jmp     loc_14004AED0
0x14004adc3  mov     r8, rbp; Size
0x14004adc6  mov     rdx, r15; Src
0x14004adc9  mov     rcx, rbx; void *
0x14004adcc  call    memmove
0x14004add1  mov     [rdi+3Ch], ebp
0x14004add4  movzx   eax, byte ptr [r14+0EAh]
0x14004addc  cmp     [rsp+0D8h+arg_8], r12d
0x14004ade4  jz      short loc_14004ADF5
  ... truncated ...
```
