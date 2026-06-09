# GenerateFTPTK(uchar *,uchar *,NWF_FT_CONTEXT *,uchar *,ulong,ulong,uchar *,uchar *,NWF_PTK *,long (*)(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong),long (*)(uchar *,ulong,uchar *,ulong))

- ea: `0x140047f34`
- end: `0x140048549`
- name: `?GenerateFTPTK@@YAJPEAE0PEAUNWF_FT_CONTEXT@@0KK00PEAUNWF_PTK@@P6AJ0K0K0K0K@ZP6AJ0K0K@Z@Z`
- size: `1557`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int8 *, struct NWF_FT_CONTEXT *, unsigned __int8 *, unsigned int, unsigned int, unsigned __int8 *, unsigned __int8 *, struct NWF_PTK *, int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int), int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int))`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1400488e4`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140020f20`
- `0x140047f34`
- `0x140052f4c`
- `0x14008dfa0`
- `0x14008e160`
- `0x14009a3d0`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400480dc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400480dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400480f4`
- `ntoskrnl!ExAllocatePool2` at `0x1400480f4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048509`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048509`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004851a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004851a`

## pseudocode

```c
__int64 __fastcall GenerateFTPTK(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        struct NWF_FT_CONTEXT *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned __int8 *a8,
        struct NWF_PTK *a9)
{
  char *v9; // rdi
  unsigned int v10; // r15d
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned int v15; // ebx
  unsigned int v16; // r13d
  unsigned int v17; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  int v22; // ebx
  __int64 v23; // rdx
  int v24; // ecx
  int v25; // eax
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int128 v30; // xmm0
  __int64 PMKIDCountOffset; // rcx
  unsigned __int8 *pRSNIE; // rax
  unsigned __int8 *v33; // rcx
  struct NWF_PTK *v34; // r13
  _QWORD v37[2]; // [rsp+50h] [rbp-A1h] BYREF
  unsigned __int8 *v38; // [rsp+60h] [rbp-91h]
  unsigned __int8 *v39; // [rsp+68h] [rbp-89h]
  struct NWF_PTK *v40; // [rsp+70h] [rbp-81h]
  unsigned __int8 v41[16]; // [rsp+78h] [rbp-79h] BYREF
  __int128 v42; // [rsp+88h] [rbp-69h]
  unsigned __int8 v43[32]; // [rsp+98h] [rbp-59h] BYREF
  unsigned __int8 v44[32]; // [rsp+B8h] [rbp-39h] BYREF
  __int128 v45; // [rsp+D8h] [rbp-19h]

  v9 = 0;
  v10 = 0;
  v38 = a4;
  v39 = a2;
  v40 = a9;
  if ( a6 > 0x20 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
LABEL_5:
      v15 = -1073741811;
      goto LABEL_48;
    }
    v13 = 428;
    v14 = a6;
LABEL_4:
    WPP_SF_d(v12->AttachedDevice, v13, WPP_e90d411d816e312466897e39e745b158_Traceguids, v14);
    goto LABEL_5;
  }
  if ( a5 < 0x20 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_5;
    v14 = a5;
    v13 = 429;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 430, WPP_e90d411d816e312466897e39e745b158_Traceguids);
    goto LABEL_5;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v37[0] = LOWORD(a3->Ssid.uSSIDLength);
    v37[1] = a3->Ssid.ucSSID;
    WPP_SF__MAC__MAC__HEX_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)WPP_GLOBAL_Control,
      (_DWORD)a2,
      (_DWORD)a1,
      (__int64)a2,
      (__int64)v37);
  }
  v16 = a3->pFTE_R0KH_IDSubElement[1] + a3->Ssid.uSSIDLength + 10;
  if ( v16 <= 0x4C )
  {
    v10 = 76;
    goto LABEL_20;
  }
  v17 = v16 + 16;
  v10 = a3->pFTE_R0KH_IDSubElement[1] + a3->Ssid.uSSIDLength + 10;
  if ( v16 >= 0xFFFFFFF0 )
    goto LABEL_46;
  if ( v17 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_25:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_27;
  }
  if ( v17 <= 0x100 )
  {
LABEL_20:
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_25;
  }
  if ( v17 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_25;
  }
  if ( v17 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_25;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v17, 2053731191, a4);
LABEL_27:
  if ( !Pool2 )
  {
LABEL_46:
    v15 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        432,
        WPP_e90d411d816e312466897e39e745b158_Traceguids,
        v10,
        -1073741670);
    goto LABEL_48;
  }
  v9 = (char *)(Pool2 + 4);
  *(_QWORD *)Pool2 = p_DeviceQueue;
  Pool2[2] = 2053731191;
  memset(Pool2 + 4, 0, v10);
  *v9 = a3->Ssid.uSSIDLength;
  memmove(v9 + 1, a3->Ssid.ucSSID, a3->Ssid.uSSIDLength);
  v20 = a3->Ssid.uSSIDLength + 1;
  *(_WORD *)&v9[v20] = *((_WORD *)a3->pMDDIE + 1);
  v21 = (unsigned int)(v20 + 2);
  v22 = v21 + 1;
  v9[v21] = a3->pFTE_R0KH_IDSubElement[1];
  memmove(&v9[(unsigned int)(v21 + 1)], a3->pFTE_R0KH_IDSubElement + 2, a3->pFTE_R0KH_IDSubElement[1]);
  v23 = v22 + (unsigned int)a3->pFTE_R0KH_IDSubElement[1];
  *(_DWORD *)&v9[v23] = *(_DWORD *)a1;
  v24 = (int)v38;
  *(_WORD *)&v9[v23 + 4] = *((_WORD *)a1 + 2);
  v25 = SSN_SHA256_PRF(v24, a5, (int)"FT-R0", 5, (unsigned __int8 *)v9, v16, v44, 0x30u);
  v15 = v25;
  if ( v25 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_48;
    v27 = 433;
    goto LABEL_31;
  }
  *(_OWORD *)v41 = 0;
  v42 = 0;
  memset(v9, 0, v10);
  qmemcpy(v9, "FT-R0N", 6);
  *(_OWORD *)(v9 + 6) = v45;
  v25 = WL_SHA256((unsigned __int8 *)v9, 0x16u, v41, 0x20u);
  v15 = v25;
  if ( v25 >= 0 )
  {
    *(_OWORD *)a3->PmkR0Name = *(_OWORD *)v41;
    memset(v9, 0, v10);
    memmove(v9, a3->pFTE_R1KH_IDSubElement + 2, a3->pFTE_R1KH_IDSubElement[1]);
    v28 = a3->pFTE_R1KH_IDSubElement[1];
    *(_DWORD *)&v9[v28] = *(_DWORD *)a1;
    *(_WORD *)&v9[v28 + 4] = *((_WORD *)a1 + 2);
    v25 = SSN_SHA256_PRF((int)v44, 32, (int)"FT-R1", 5, (unsigned __int8 *)v9, 0xCu, v43, 0x20u);
    v15 = v25;
    if ( v25 >= 0 )
    {
      *(_OWORD *)v41 = 0;
      v42 = 0;
      memset(v9, 0, v10);
      qmemcpy(v9, "FT-R1N", 6);
      *(_OWORD *)(v9 + 6) = *(_OWORD *)a3->PmkR0Name;
      memmove(v9 + 22, a3->pFTE_R1KH_IDSubElement + 2, a3->pFTE_R1KH_IDSubElement[1]);
      v29 = a3->pFTE_R1KH_IDSubElement[1];
      *(_DWORD *)&v9[v29 + 22] = *(_DWORD *)a1;
      *(_WORD *)&v9[v29 + 26] = *((_WORD *)a1 + 2);
      v25 = WL_SHA256((unsigned __int8 *)v9, 0x22u, v41, 0x20u);
      v15 = v25;
      if ( v25 >= 0 )
      {
        v30 = *(_OWORD *)v41;
        PMKIDCountOffset = a3->PMKIDCountOffset;
        pRSNIE = a3->pRSNIE;
        *(_OWORD *)a3->PmkR1Name = *(_OWORD *)v41;
        *(_OWORD *)&pRSNIE[PMKIDCountOffset + 2] = v30;
        memset(v9, 0, v10);
        v33 = v39;
        *(_OWORD *)v9 = *(_OWORD *)a7;
        *((_OWORD *)v9 + 1) = *((_OWORD *)a7 + 1);
        *((_OWORD *)v9 + 2) = *(_OWORD *)a8;
        *((_OWORD *)v9 + 3) = *((_OWORD *)a8 + 1);
        *((_DWORD *)v9 + 16) = *(_DWORD *)v33;
        *((_WORD *)v9 + 34) = *((_WORD *)v33 + 2);
        *(_DWORD *)(v9 + 70) = *(_DWORD *)a1;
        v34 = v40;
        *((_WORD *)v9 + 37) = *((_WORD *)a1 + 2);
        v25 = SSN_SHA256_PRF((int)v43, 32, (int)"FT-PTK", 6, (unsigned __int8 *)v9, 0x4Cu, v34->PTK, a6 + 32);
        v15 = v25;
        if ( v25 >= 0 )
        {
          a3->uTKLength = a6;
          v34->TKLength = a6;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 438, WPP_e90d411d816e312466897e39e745b158_Traceguids);
        }
        else
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v27 = 437;
            goto LABEL_31;
          }
        }
      }
      else
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v27 = 436;
          goto LABEL_31;
        }
      }
    }
    else
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v27 = 435;
        goto LABEL_31;
      }
    }
  }
  else
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v27 = 434;
LABEL_31:
      WPP_SF_d(v26->AttachedDevice, v27, WPP_e90d411d816e312466897e39e745b158_Traceguids, (unsigned int)v25);
    }
  }
LABEL_48:
  *(_OWORD *)v41 = 0;
  v42 = 0;
  memset(v9, 0, v10);
  if ( v9 )
  {
    if ( *((_QWORD *)v9 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v9 - 2), v9 - 16);
    else
      ExFreePoolWithTag(v9 - 16, *((_DWORD *)v9 - 2));
  }
  return v15;
}

```

## disassembly

```asm
0x140047f34  push    rbp
0x140047f36  push    rbx
0x140047f37  push    rsi
0x140047f38  push    rdi
0x140047f39  push    r12
0x140047f3b  push    r13
0x140047f3d  push    r14
0x140047f3f  push    r15
0x140047f41  lea     rbp, [rsp-7]
0x140047f46  sub     rsp, 0F8h
0x140047f4d  mov     rax, cs:__security_cookie
0x140047f54  xor     rax, rsp
0x140047f57  mov     [rbp+3Fh+var_48], rax
0x140047f5b  mov     rax, [rbp+3Fh+arg_40]
0x140047f62  xor     edi, edi
0x140047f64  mov     r12d, [rbp+3Fh+arg_28]
0x140047f68  xor     r15d, r15d
0x140047f6b  mov     [rsp+130h+var_D0], r9
0x140047f70  mov     r14, r8
0x140047f73  mov     [rsp+130h+var_C8], rdx
0x140047f78  mov     r8, rdx
0x140047f7b  mov     [rsp+130h+var_F0], rcx
0x140047f80  mov     [rsp+130h+var_C0], rax
0x140047f85  cmp     r12d, 20h ; ' '
0x140047f89  jbe     short loc_140047FC0
0x140047f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140047f92  lea     rsi, WPP_GLOBAL_Control
0x140047f99  cmp     rcx, rsi
0x140047f9c  jz      short loc_140047FB6
0x140047f9e  mov     edx, 1ACh
0x140047fa3  mov     r9d, r12d
0x140047fa6  mov     rcx, [rcx+18h]
0x140047faa  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140047fb1  call    WPP_SF_d
0x140047fb6  mov     ebx, 0C000000Dh
0x140047fbb  jmp     loc_1400484DA
0x140047fc0  cmp     [rbp+3Fh+arg_20], 20h ; ' '
0x140047fc4  jnb     short loc_140047FE4
0x140047fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x140047fcd  lea     rsi, WPP_GLOBAL_Control
0x140047fd4  cmp     rcx, rsi
0x140047fd7  jz      short loc_140047FB6
0x140047fd9  mov     r9d, [rbp+3Fh+arg_20]
0x140047fdd  mov     edx, 1ADh
0x140047fe2  jmp     short loc_140047FA6
0x140047fe4  test    r14, r14
0x140047fe7  jnz     short loc_140048013
0x140047fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x140047ff0  lea     rsi, WPP_GLOBAL_Control
0x140047ff7  cmp     rcx, rsi
0x140047ffa  jz      short loc_140047FB6
0x140047ffc  mov     rcx, [rcx+18h]
0x140048000  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140048007  mov     edx, 1AEh
0x14004800c  call    WPP_SF_
0x140048011  jmp     short loc_140047FB6
0x140048013  mov     rdx, cs:WPP_GLOBAL_Control
0x14004801a  lea     rsi, WPP_GLOBAL_Control
0x140048021  cmp     rdx, rsi
0x140048024  jz      short loc_140048066
0x140048026  movzx   eax, word ptr [r14]
0x14004802a  xorps   xmm0, xmm0
0x14004802d  movups  [rsp+130h+var_E0], xmm0
0x140048032  mov     word ptr [rsp+130h+var_E0], ax
0x140048037  mov     r9, rcx
0x14004803a  lea     rax, [r14+4]
0x14004803e  mov     qword ptr [rsp+130h+var_E0+8], rax
0x140048043  lea     rax, [rsp+130h+var_E0]
0x140048048  movaps  xmm0, [rsp+130h+var_E0]
0x14004804d  movdqa  [rsp+130h+var_E0], xmm0
0x140048053  mov     rcx, [rdx+18h]
0x140048057  mov     qword ptr [rsp+130h+var_108], rax
0x14004805c  mov     [rsp+130h+var_110], r8
0x140048061  call    WPP_SF__MAC__MAC__HEX_
0x140048066  mov     rax, [r14+0B8h]
0x14004806d  mov     r13d, [r14]
0x140048070  add     r13d, 0Ah
0x140048074  movzx   ecx, byte ptr [rax+1]
0x140048078  add     r13d, ecx
0x14004807b  cmp     r13d, 4Ch ; 'L'
0x14004807f  ja      short loc_140048089
0x140048081  mov     r15d, 4Ch ; 'L'
0x140048087  jmp     short loc_1400480B2
0x140048089  lea     eax, [r13+10h]
0x14004808d  mov     r15d, r13d
0x140048090  cmp     eax, 10h
0x140048093  jb      loc_1400484AD
0x140048099  mov     ecx, 40h ; '@'
0x14004809e  cmp     eax, ecx
0x1400480a0  ja      short loc_1400480AB
0x1400480a2  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400480a9  jmp     short loc_1400480D9
0x1400480ab  cmp     eax, 100h
0x1400480b0  ja      short loc_1400480BB
0x1400480b2  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400480b9  jmp     short loc_1400480D9
0x1400480bb  cmp     eax, 400h
0x1400480c0  ja      short loc_1400480CB
0x1400480c2  lea     rbx, Lookaside
0x1400480c9  jmp     short loc_1400480D9
0x1400480cb  cmp     eax, 800h
0x1400480d0  ja      short loc_1400480EA
0x1400480d2  lea     rbx, stru_1400B0180
0x1400480d9  mov     rcx, rbx; Lookaside
0x1400480dc  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400480e3  nop     dword ptr [rax+rax+00h]
0x1400480e8  jmp     short loc_140048100
0x1400480ea  xor     ebx, ebx
0x1400480ec  mov     edx, eax
0x1400480ee  mov     r8d, 7A697377h
0x1400480f4  call    cs:__imp_ExAllocatePool2
0x1400480fb  nop     dword ptr [rax+rax+00h]
0x140048100  test    rax, rax
0x140048103  jz      loc_1400484AD
0x140048109  lea     rdi, [rax+10h]
0x14004810d  mov     r8d, r15d; Size
0x140048110  mov     rcx, rdi; void *
0x140048113  mov     [rax], rbx
0x140048116  xor     edx, edx; Val
0x140048118  mov     dword ptr [rax+8], 7A697377h
0x14004811f  call    memset
0x140048124  mov     al, [r14]
0x140048127  lea     rdx, [r14+4]; Src
0x14004812b  mov     [rdi], al
0x14004812d  lea     rcx, [rdi+1]; void *
0x140048131  mov     r8d, [r14]; Size
0x140048134  call    memmove
0x140048139  mov     edx, [r14]
0x14004813c  mov     rax, [r14+40h]
0x140048140  inc     edx
0x140048142  movzx   eax, word ptr [rax+2]
0x140048146  mov     [rdx+rdi], ax
0x14004814a  add     edx, 2
0x14004814d  mov     rax, [r14+0B8h]
0x140048154  lea     ebx, [rdx+1]
0x140048157  mov     al, [rax+1]
0x14004815a  mov     [rdx+rdi], al
0x14004815d  mov     rdx, [r14+0B8h]
0x140048164  mov     ecx, ebx
0x140048166  add     rcx, rdi; void *
0x140048169  movzx   r8d, byte ptr [rdx+1]; Size
0x14004816e  add     rdx, 2; Src
0x140048172  call    memmove
0x140048177  mov     rax, [r14+0B8h]
0x14004817e  lea     r8, aFtR0; "FT-R0"
0x140048185  mov     rcx, [rsp+130h+var_F0]
0x14004818a  mov     r9d, 5; int
0x140048190  mov     [rsp+130h+var_F8], 30h ; '0'; unsigned int
0x140048198  movzx   edx, byte ptr [rax+1]
0x14004819c  mov     eax, [rcx]
0x14004819e  add     edx, ebx
0x1400481a0  mov     [rdx+rdi], eax
0x1400481a3  movzx   eax, word ptr [rcx+4]
0x1400481a7  mov     rcx, [rsp+130h+var_D0]; int
0x1400481ac  mov     [rdx+rdi+4], ax
0x1400481b1  lea     rax, [rbp+3Fh+var_78]
0x1400481b5  mov     edx, [rbp+3Fh+arg_20]; int
0x1400481b8  mov     [rsp+130h+var_100], rax; unsigned __int8 *
0x1400481bd  mov     [rsp+130h+var_108], r13d; unsigned int
0x1400481c2  mov     [rsp+130h+var_110], rdi; unsigned __int8 *
0x1400481c7  call    SSN_SHA256_PRF
0x1400481cc  mov     ebx, eax
0x1400481ce  test    eax, eax
0x1400481d0  jns     short loc_1400481FF
0x1400481d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400481d9  cmp     rcx, rsi
0x1400481dc  jz      loc_1400484DA
0x1400481e2  mov     edx, 1B1h
0x1400481e7  mov     rcx, [rcx+18h]
0x1400481eb  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x1400481f2  mov     r9d, eax
0x1400481f5  call    WPP_SF_d
0x1400481fa  jmp     loc_1400484DA
0x1400481ff  xorps   xmm0, xmm0
0x140048202  mov     r8d, r15d; Size
0x140048205  xor     edx, edx; Val
0x140048207  mov     r13d, r15d
0x14004820a  mov     rcx, rdi; void *
0x14004820d  movups  xmmword ptr [rbp+3Fh+var_B8], xmm0
0x140048211  movups  [rbp+3Fh+var_A8], xmm0
0x140048215  call    memset
0x14004821a  mov     eax, dword ptr cs:aFtR0n; "FT-R0N"
0x140048220  lea     r8, [rbp+3Fh+var_B8]; unsigned __int8 *
0x140048224  mov     [rdi], eax
0x140048226  mov     r9d, 20h ; ' '; unsigned int
0x14004822c  movzx   eax, word ptr cs:aFtR0n+4; "0N"
0x140048233  mov     rcx, rdi; unsigned __int8 *
0x140048236  mov     [rdi+4], ax
0x14004823a  movups  xmm0, [rbp+3Fh+var_58]
0x14004823e  lea     edx, [r9-0Ah]; unsigned int
0x140048242  movdqu  xmmword ptr [rdi+6], xmm0
0x140048247  call    WL_SHA256
0x14004824c  mov     ebx, eax
0x14004824e  test    eax, eax
0x140048250  jns     short loc_14004826C
0x140048252  mov     rcx, cs:WPP_GLOBAL_Control
0x140048259  cmp     rcx, rsi
0x14004825c  jz      loc_1400484DA
0x140048262  mov     edx, 1B2h
0x140048267  jmp     loc_1400481E7
0x14004826c  movups  xmm0, xmmword ptr [rbp+3Fh+var_B8]
0x140048270  mov     r8, r13; Size
0x140048273  xor     edx, edx; Val
0x140048275  mov     rcx, rdi; void *
0x140048278  movdqu  xmmword ptr [r14+68h], xmm0
0x14004827e  call    memset
0x140048283  mov     rdx, [r14+0B0h]
0x14004828a  mov     rcx, rdi; void *
0x14004828d  movzx   r8d, byte ptr [rdx+1]; Size
0x140048292  add     rdx, 2; Src
0x140048296  call    memmove
0x14004829b  mov     rax, [r14+0B0h]
0x1400482a2  lea     r8, aFtR1; "FT-R1"
0x1400482a9  mov     r13, [rsp+130h+var_F0]
0x1400482ae  movzx   ecx, byte ptr [rax+1]
0x1400482b2  mov     eax, [r13+0]
0x1400482b6  mov     [rcx+rdi], eax
0x1400482b9  movzx   eax, word ptr [r13+4]
0x1400482be  mov     [rcx+rdi+4], ax
0x1400482c3  mov     ecx, 20h ; ' '
0x1400482c8  mov     [rsp+130h+var_F8], ecx; unsigned int
0x1400482cc  lea     rax, [rbp+3Fh+var_98]
0x1400482d0  mov     [rsp+130h+var_100], rax; unsigned __int8 *
0x1400482d5  mov     edx, ecx; int
0x1400482d7  mov     [rsp+130h+var_108], 0Ch; unsigned int
0x1400482df  lea     r9d, [rcx-1Bh]; int
0x1400482e3  mov     [rsp+130h+var_110], rdi; unsigned __int8 *
0x1400482e8  lea     rcx, [rbp+3Fh+var_78]; int
0x1400482ec  call    SSN_SHA256_PRF
0x1400482f1  mov     ebx, eax
0x1400482f3  test    eax, eax
0x1400482f5  jns     short loc_140048311
0x1400482f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400482fe  cmp     rcx, rsi
0x140048301  jz      loc_1400484DA
0x140048307  mov     edx, 1B3h
0x14004830c  jmp     loc_1400481E7
0x140048311  xorps   xmm0, xmm0
0x140048314  mov     r8d, r15d; Size
0x140048317  xor     edx, edx; Val
0x140048319  mov     rcx, rdi; void *
0x14004831c  movups  xmmword ptr [rbp+3Fh+var_B8], xmm0
0x140048320  movups  [rbp+3Fh+var_A8], xmm0
0x140048324  call    memset
0x140048329  mov     eax, dword ptr cs:aFtR1n; "FT-R1N"
0x14004832f  lea     rcx, [rdi+16h]; void *
0x140048333  mov     [rdi], eax
0x140048335  movzx   eax, word ptr cs:aFtR1n+4; "1N"
0x14004833c  mov     [rdi+4], ax
0x140048340  movups  xmm0, xmmword ptr [r14+68h]
0x140048345  movdqu  xmmword ptr [rdi+6], xmm0
0x14004834a  mov     rdx, [r14+0B0h]
0x140048351  movzx   r8d, byte ptr [rdx+1]; Size
0x140048356  add     rdx, 2; Src
0x14004835a  call    memmove
0x14004835f  mov     rax, [r14+0B0h]
0x140048366  lea     r8, [rbp+3Fh+var_B8]; unsigned __int8 *
0x14004836a  mov     r9d, 20h ; ' '; unsigned int
0x140048370  movzx   ecx, byte ptr [rax+1]
0x140048374  mov     eax, [r13+0]
0x140048378  lea     edx, [r9+2]; unsigned int
0x14004837c  mov     [rcx+rdi+16h], eax
0x140048380  movzx   eax, word ptr [r13+4]
0x140048385  mov     [rcx+rdi+1Ah], ax
0x14004838a  mov     rcx, rdi; unsigned __int8 *
0x14004838d  call    WL_SHA256
0x140048392  mov     ebx, eax
0x140048394  test    eax, eax
0x140048396  jns     short loc_1400483B2
0x140048398  mov     rcx, cs:WPP_GLOBAL_Control
0x14004839f  cmp     rcx, rsi
0x1400483a2  jz      loc_1400484DA
0x1400483a8  mov     edx, 1B4h
0x1400483ad  jmp     loc_1400481E7
0x1400483b2  movups  xmm0, xmmword ptr [rbp+3Fh+var_B8]
0x1400483b6  movzx   ecx, byte ptr [r14+0DAh]
0x1400483be  xor     edx, edx; Val
0x1400483c0  mov     rax, [r14+50h]
0x1400483c4  movdqu  xmmword ptr [r14+78h], xmm0
0x1400483ca  mov     r8d, r15d; Size
0x1400483cd  movdqu  xmmword ptr [rcx+rax+2], xmm0
0x1400483d3  mov     rcx, rdi; void *
0x1400483d6  call    memset
0x1400483db  mov     rax, [rbp+3Fh+arg_30]
0x1400483df  lea     r8, aFtPtk; "FT-PTK"
0x1400483e6  mov     rcx, [rsp+130h+var_C8]
0x1400483eb  mov     r9d, 6; int
0x1400483f1  movups  xmm0, xmmword ptr [rax]
0x1400483f4  lea     edx, [r9+1Ah]; int
0x1400483f8  movups  xmmword ptr [rdi], xmm0
0x1400483fb  movups  xmm1, xmmword ptr [rax+10h]
0x1400483ff  mov     rax, [rbp+3Fh+arg_38]
0x140048406  movups  xmmword ptr [rdi+10h], xmm1
0x14004840a  movups  xmm0, xmmword ptr [rax]
0x14004840d  movups  xmmword ptr [rdi+20h], xmm0
0x140048411  movups  xmm1, xmmword ptr [rax+10h]
0x140048415  movups  xmmword ptr [rdi+30h], xmm1
0x140048419  mov     eax, [rcx]
0x14004841b  mov     [rdi+40h], eax
0x14004841e  movzx   eax, word ptr [rcx+4]
  ... truncated ...
```
