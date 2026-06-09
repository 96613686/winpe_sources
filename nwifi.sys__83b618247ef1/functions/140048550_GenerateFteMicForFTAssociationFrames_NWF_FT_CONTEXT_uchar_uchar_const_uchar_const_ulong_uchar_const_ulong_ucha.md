# GenerateFteMicForFTAssociationFrames(NWF_FT_CONTEXT *,uchar,uchar const *,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar *)

- ea: `0x140048550`
- end: `0x1400488de`
- name: `?GenerateFteMicForFTAssociationFrames@@YAJPEAUNWF_FT_CONTEXT@@EPEBE1K1K1KPEAE@Z`
- size: `910`
- prototype: `__int64 __fastcall(struct NWF_FT_CONTEXT *, unsigned __int8, const unsigned __int8 *, const unsigned __int8 *, size_t Size, const unsigned __int8 *, size_t, const unsigned __int8 *, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140041f8c`
- `0x140046bf0`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140020f20`
- `0x14002f1bc`
- `0x140048550`
- `0x14008e068`
- `0x14009a3d0`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140048626`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140048626`
- `ntoskrnl!ExAllocatePool2` at `0x14004863b`
- `ntoskrnl!ExAllocatePool2` at `0x14004863b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048796`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004885b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048796`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004885b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400487aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004886f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400487aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004886f`

## pseudocode

```c
__int64 __fastcall GenerateFteMicForFTAssociationFrames(
        struct NWF_FT_CONTEXT *a1,
        char a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        size_t Size,
        unsigned __int8 *a6,
        size_t a7,
        unsigned __int8 *a8,
        unsigned int a9,
        unsigned __int8 *a10)
{
  unsigned int MDDIELength; // ecx
  unsigned int v12; // esi
  unsigned int v13; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  char *v16; // rdi
  const unsigned __int8 *v17; // rcx
  char *v18; // r15
  __int16 v19; // ax
  const unsigned __int8 *v20; // rcx
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // r12d
  _DEVICE_OBJECT *AttachedDevice; // rcx
  _DEVICE_OBJECT *v28; // rcx
  __int64 v30; // [rsp+40h] [rbp-49h] BYREF
  __int128 *v31; // [rsp+48h] [rbp-41h]
  const unsigned __int8 *v32; // [rsp+50h] [rbp-39h]
  const unsigned __int8 *v33; // [rsp+58h] [rbp-31h]
  void *Src; // [rsp+60h] [rbp-29h]
  void *v35; // [rsp+68h] [rbp-21h]
  __int128 v36; // [rsp+70h] [rbp-19h] BYREF

  MDDIELength = a1->MDDIELength;
  v32 = a3;
  v12 = a1->FTEIELength + MDDIELength + a1->RSNIELength + 13;
  v33 = a4;
  Src = a6;
  v35 = a8;
  v30 = (__int64)a10;
  if ( (_DWORD)Size && a6 )
    v12 += Size;
  if ( (_DWORD)a7 && a8 )
    v12 += a7;
  v13 = v12 + 16;
  if ( v12 >= 0xFFFFFFF0 )
    goto LABEL_41;
  if ( v13 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_16:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_18;
  }
  if ( v13 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_16;
  }
  if ( v13 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_16;
  }
  if ( v13 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_16;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v13, 2053731191, a4);
LABEL_18:
  v16 = Pool2;
  if ( Pool2 )
  {
    v17 = v32;
    *((_DWORD *)Pool2 + 2) = 2053731191;
    v18 = Pool2 + 16;
    *(_QWORD *)Pool2 = p_DeviceQueue;
    *(_OWORD *)a1->pFTE_MIC = 0;
    *((_DWORD *)Pool2 + 4) = *(_DWORD *)v17;
    v19 = *((_WORD *)v17 + 2);
    v20 = v33;
    *((_WORD *)v18 + 2) = v19;
    *(_DWORD *)(v18 + 6) = *(_DWORD *)v20;
    *((_WORD *)v18 + 5) = *((_WORD *)v20 + 2);
    v18[12] = a2;
    memmove(v18 + 13, a1->pRSNIE, a1->RSNIELength);
    v21 = a1->RSNIELength + 13;
    memmove(&v18[v21], a1->pMDDIE, a1->MDDIELength);
    v22 = a1->MDDIELength + v21;
    memmove(&v18[v22], a1->pFTEIE, a1->FTEIELength);
    v23 = a1->FTEIELength + v22;
    if ( (_DWORD)Size && Src )
    {
      memmove(&v18[v23], Src, (unsigned int)Size);
      v23 += Size;
    }
    if ( (_DWORD)a7 && v35 )
      memmove(&v18[v23], v35, (unsigned int)a7);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 440, WPP_e90d411d816e312466897e39e745b158_Traceguids);
    v36 = 0;
    v24 = WL_CMAC_128((_DWORD)v18, v12, v30, a9, (__int64)&v36);
    v25 = v24;
    if ( v24 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        v30 = (unsigned __int16)v12;
        v31 = (__int128 *)v18;
        WPP_SF__HEX_(AttachedDevice, 442, WPP_e90d411d816e312466897e39e745b158_Traceguids, &v30);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v28 = WPP_GLOBAL_Control->AttachedDevice;
          v30 = 16;
          v31 = &v36;
          WPP_SF__HEX_(v28, 443, WPP_e90d411d816e312466897e39e745b158_Traceguids, &v30);
        }
      }
      *(_OWORD *)a1->pFTE_MIC = v36;
      if ( *(_QWORD *)v16 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v16, v16);
      else
        ExFreePoolWithTag(v16, *((_DWORD *)v16 + 2));
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          441,
          WPP_e90d411d816e312466897e39e745b158_Traceguids,
          (unsigned int)v24);
      if ( *(_QWORD *)v16 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v16, v16);
      else
        ExFreePoolWithTag(v16, *((_DWORD *)v16 + 2));
      return v25;
    }
  }
LABEL_41:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      439,
      WPP_e90d411d816e312466897e39e745b158_Traceguids,
      v12,
      -1073741670);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140048550  mov     [rsp-8+arg_8], rbx
0x140048555  mov     [rsp-8+arg_10], rsi
0x14004855a  push    rbp
0x14004855b  push    rdi
0x14004855c  push    r12
0x14004855e  push    r13
0x140048560  push    r15
0x140048562  lea     rbp, [rsp-7]
0x140048567  sub     rsp, 90h
0x14004856e  mov     rax, cs:__security_cookie
0x140048575  xor     rax, rsp
0x140048578  mov     [rbp+27h+var_30], rax
0x14004857c  mov     r12d, dword ptr [rbp+27h+Size]
0x140048580  mov     r13, rcx
0x140048583  mov     ecx, [rcx+34h]
0x140048586  mov     rax, [rbp+27h+arg_48]
0x14004858a  mov     [rbp+27h+var_60], r8
0x14004858e  add     ecx, [r13+38h]
0x140048592  mov     esi, [r13+3Ch]
0x140048596  mov     r8, [rbp+27h+arg_28]
0x14004859a  add     esi, 0Dh
0x14004859d  add     esi, ecx
0x14004859f  mov     [rbp+27h+var_80], dl
0x1400485a2  mov     rdx, [rbp+27h+arg_38]
0x1400485a6  mov     [rbp+27h+var_58], r9
0x1400485aa  mov     [rbp+27h+Src], r8
0x1400485ae  mov     [rbp+27h+var_48], rdx
0x1400485b2  mov     qword ptr [rbp+27h+var_70], rax
0x1400485b6  test    r12d, r12d
0x1400485b9  jz      short loc_1400485C3
0x1400485bb  test    r8, r8
0x1400485be  jz      short loc_1400485C3
0x1400485c0  add     esi, r12d
0x1400485c3  cmp     dword ptr [rbp+27h+arg_30], 0
0x1400485c7  jbe     short loc_1400485D1
0x1400485c9  test    rdx, rdx
0x1400485cc  jz      short loc_1400485D1
0x1400485ce  add     esi, dword ptr [rbp+27h+arg_30]
0x1400485d1  lea     eax, [rsi+10h]
0x1400485d4  cmp     eax, 10h
0x1400485d7  jb      loc_14004887F
0x1400485dd  mov     ecx, 40h ; '@'
0x1400485e2  mov     r15d, 7A697377h
0x1400485e8  cmp     eax, ecx
0x1400485ea  ja      short loc_1400485F5
0x1400485ec  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400485f3  jmp     short loc_140048623
0x1400485f5  cmp     eax, 100h
0x1400485fa  ja      short loc_140048605
0x1400485fc  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140048603  jmp     short loc_140048623
0x140048605  cmp     eax, 400h
0x14004860a  ja      short loc_140048615
0x14004860c  lea     rbx, Lookaside
0x140048613  jmp     short loc_140048623
0x140048615  cmp     eax, 800h
0x14004861a  ja      short loc_140048634
0x14004861c  lea     rbx, stru_1400B0180
0x140048623  mov     rcx, rbx; Lookaside
0x140048626  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004862d  nop     dword ptr [rax+rax+00h]
0x140048632  jmp     short loc_140048647
0x140048634  xor     ebx, ebx
0x140048636  mov     edx, eax
0x140048638  mov     r8d, r15d
0x14004863b  call    cs:__imp_ExAllocatePool2
0x140048642  nop     dword ptr [rax+rax+00h]
0x140048647  mov     rdi, rax
0x14004864a  test    rax, rax
0x14004864d  jz      loc_14004887F
0x140048653  mov     rcx, [rbp+27h+var_60]
0x140048657  xorps   xmm0, xmm0
0x14004865a  mov     [rax+8], r15d
0x14004865e  lea     r15, [rax+10h]
0x140048662  mov     [rax], rbx
0x140048665  mov     rax, [r13+98h]
0x14004866c  movups  xmmword ptr [rax], xmm0
0x14004866f  mov     eax, [rcx]
0x140048671  mov     [r15], eax
0x140048674  movzx   eax, word ptr [rcx+4]
0x140048678  mov     rcx, [rbp+27h+var_58]
0x14004867c  mov     [r15+4], ax
0x140048681  mov     eax, [rcx]
0x140048683  mov     [r15+6], eax
0x140048687  movzx   eax, word ptr [rcx+4]
0x14004868b  lea     rcx, [r15+0Dh]; void *
0x14004868f  mov     [r15+0Ah], ax
0x140048694  mov     al, [rbp+27h+var_80]
0x140048697  mov     [r15+0Ch], al
0x14004869b  mov     r8d, [r13+3Ch]; Size
0x14004869f  mov     rdx, [r13+50h]; Src
0x1400486a3  call    memmove
0x1400486a8  mov     ebx, [r13+3Ch]
0x1400486ac  mov     r8d, [r13+34h]; Size
0x1400486b0  add     ebx, 0Dh
0x1400486b3  mov     rdx, [r13+40h]; Src
0x1400486b7  mov     ecx, ebx
0x1400486b9  add     rcx, r15; void *
0x1400486bc  call    memmove
0x1400486c1  add     ebx, [r13+34h]
0x1400486c5  mov     r8d, [r13+38h]; Size
0x1400486c9  mov     rdx, [r13+48h]; Src
0x1400486cd  mov     ecx, ebx
0x1400486cf  add     rcx, r15; void *
0x1400486d2  call    memmove
0x1400486d7  add     ebx, [r13+38h]
0x1400486db  test    r12d, r12d
0x1400486de  jz      short loc_1400486F9
0x1400486e0  mov     rdx, [rbp+27h+Src]; Src
0x1400486e4  test    rdx, rdx
0x1400486e7  jz      short loc_1400486F9
0x1400486e9  mov     ecx, ebx
0x1400486eb  mov     r8, r12; Size
0x1400486ee  add     rcx, r15; void *
0x1400486f1  call    memmove
0x1400486f6  add     ebx, r12d
0x1400486f9  cmp     dword ptr [rbp+27h+arg_30], 0
0x1400486fd  jbe     short loc_140048716
0x1400486ff  mov     rdx, [rbp+27h+var_48]; Src
0x140048703  test    rdx, rdx
0x140048706  jz      short loc_140048716
0x140048708  mov     r8d, dword ptr [rbp+27h+arg_30]; Size
0x14004870c  mov     ecx, ebx
0x14004870e  add     rcx, r15; void *
0x140048711  call    memmove
0x140048716  mov     rcx, cs:WPP_GLOBAL_Control
0x14004871d  lea     rbx, WPP_GLOBAL_Control
0x140048724  cmp     rcx, rbx
0x140048727  jz      short loc_14004873E
0x140048729  mov     rcx, [rcx+18h]
0x14004872d  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140048734  mov     edx, 1B8h
0x140048739  call    WPP_SF_
0x14004873e  mov     r9d, [rbp+27h+arg_40]
0x140048742  lea     rax, [rbp+27h+var_40]
0x140048746  mov     r8, qword ptr [rbp+27h+var_70]
0x14004874a  xorps   xmm0, xmm0
0x14004874d  mov     edx, esi
0x14004874f  mov     [rsp+0B0h+var_90], rax
0x140048754  mov     rcx, r15
0x140048757  movups  [rbp+27h+var_40], xmm0
0x14004875b  call    WL_CMAC_128
0x140048760  mov     r12d, eax
0x140048763  test    eax, eax
0x140048765  jns     short loc_1400487BE
0x140048767  mov     rcx, cs:WPP_GLOBAL_Control
0x14004876e  cmp     rcx, rbx
0x140048771  jz      short loc_14004878B
0x140048773  mov     rcx, [rcx+18h]
0x140048777  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004877e  mov     edx, 1B9h
0x140048783  mov     r9d, eax
0x140048786  call    WPP_SF_d
0x14004878b  mov     rcx, [rdi]; Lookaside
0x14004878e  test    rcx, rcx
0x140048791  jz      short loc_1400487A4
0x140048793  mov     rdx, rdi; Entry
0x140048796  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004879d  nop     dword ptr [rax+rax+00h]
0x1400487a2  jmp     short loc_1400487B6
0x1400487a4  mov     edx, [rdi+8]; Tag
0x1400487a7  mov     rcx, rdi; P
0x1400487aa  call    cs:__imp_ExFreePoolWithTag
0x1400487b1  nop     dword ptr [rax+rax+00h]
0x1400487b6  mov     eax, r12d
0x1400487b9  jmp     loc_1400488B5
0x1400487be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400487c5  cmp     rcx, rbx
0x1400487c8  jz      short loc_140048841
0x1400487ca  mov     rcx, [rcx+18h]
0x1400487ce  lea     r9, [rbp+27h+var_70]
0x1400487d2  xorps   xmm0, xmm0
0x1400487d5  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x1400487dc  movups  [rbp+27h+var_70], xmm0
0x1400487e0  mov     word ptr [rbp+27h+var_70], si
0x1400487e4  mov     edx, 1BAh
0x1400487e9  mov     qword ptr [rbp+27h+var_70+8], r15
0x1400487ed  movaps  xmm0, [rbp+27h+var_70]
0x1400487f1  movdqa  [rbp+27h+var_70], xmm0
0x1400487f6  call    WPP_SF__HEX_
0x1400487fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140048802  cmp     rcx, rbx
0x140048805  jz      short loc_140048841
0x140048807  mov     rcx, [rcx+18h]
0x14004880b  lea     r9, [rbp+27h+var_70]
0x14004880f  xorps   xmm0, xmm0
0x140048812  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140048819  movups  [rbp+27h+var_70], xmm0
0x14004881d  mov     eax, 10h
0x140048822  mov     edx, 1BBh
0x140048827  mov     word ptr [rbp+27h+var_70], ax
0x14004882b  lea     rax, [rbp+27h+var_40]
0x14004882f  mov     qword ptr [rbp+27h+var_70+8], rax
0x140048833  movaps  xmm0, [rbp+27h+var_70]
0x140048837  movdqa  [rbp+27h+var_70], xmm0
0x14004883c  call    WPP_SF__HEX_
0x140048841  mov     rax, [r13+98h]
0x140048848  movups  xmm0, [rbp+27h+var_40]
0x14004884c  movdqu  xmmword ptr [rax], xmm0
0x140048850  mov     rcx, [rdi]; Lookaside
0x140048853  test    rcx, rcx
0x140048856  jz      short loc_140048869
0x140048858  mov     rdx, rdi; Entry
0x14004885b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048862  nop     dword ptr [rax+rax+00h]
0x140048867  jmp     short loc_14004887B
0x140048869  mov     edx, [rdi+8]; Tag
0x14004886c  mov     rcx, rdi; P
0x14004886f  call    cs:__imp_ExFreePoolWithTag
0x140048876  nop     dword ptr [rax+rax+00h]
0x14004887b  xor     eax, eax
0x14004887d  jmp     short loc_1400488B5
0x14004887f  mov     rcx, cs:WPP_GLOBAL_Control
0x140048886  lea     rbx, WPP_GLOBAL_Control
0x14004888d  mov     edi, 0C000009Ah
0x140048892  cmp     rcx, rbx
0x140048895  jz      short loc_1400488B3
0x140048897  mov     rcx, [rcx+18h]
0x14004889b  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x1400488a2  mov     edx, 1B7h
0x1400488a7  mov     dword ptr [rsp+0B0h+var_90], edi
0x1400488ab  mov     r9d, esi
0x1400488ae  call    WPP_SF_Dd
0x1400488b3  mov     eax, edi
0x1400488b5  mov     rcx, [rbp+27h+var_30]
0x1400488b9  xor     rcx, rsp; StackCookie
0x1400488bc  call    __security_check_cookie
0x1400488c1  lea     r11, [rsp+0B0h+var_20]
0x1400488c9  mov     rbx, [r11+38h]
0x1400488cd  mov     rsi, [r11+40h]
0x1400488d1  mov     rsp, r11
0x1400488d4  pop     r15
0x1400488d6  pop     r13
0x1400488d8  pop     r12
0x1400488da  pop     rdi
0x1400488db  pop     rbp
0x1400488dc  retn
```
