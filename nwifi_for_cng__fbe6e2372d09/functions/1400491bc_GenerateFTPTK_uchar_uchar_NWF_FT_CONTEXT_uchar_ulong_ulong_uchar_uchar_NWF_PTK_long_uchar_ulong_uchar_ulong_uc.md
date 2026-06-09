# GenerateFTPTK(uchar *,uchar *,NWF_FT_CONTEXT *,uchar *,ulong,ulong,uchar *,uchar *,NWF_PTK *,long (*)(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong),long (*)(uchar *,ulong,uchar *,ulong))

- ea: `0x1400491bc`
- end: `0x1400497d1`
- name: `?GenerateFTPTK@@YAJPEAE0PEAUNWF_FT_CONTEXT@@0KK00PEAUNWF_PTK@@P6AJ0K0K0K0K@ZP6AJ0K0K@Z@Z`
- size: `1557`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int8 *, struct NWF_FT_CONTEXT *, unsigned __int8 *, unsigned int, unsigned int, unsigned __int8 *, unsigned __int8 *, struct NWF_PTK *, int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int), int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int))`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140049b6c`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140020f20`
- `0x1400491bc`
- `0x14005476c`
- `0x14008f7d0`
- `0x14008f940`
- `0x14009bbb0`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140049364`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140049364`
- `ntoskrnl!ExAllocatePool2` at `0x14004937c`
- `ntoskrnl!ExAllocatePool2` at `0x14004937c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049791`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140049791`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400497a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400497a2`

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
    v13 = 443;
    v14 = a6;
LABEL_4:
    WPP_SF_d(v12->AttachedDevice, v13, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v14);
    goto LABEL_5;
  }
  if ( a5 < 0x20 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_5;
    v14 = a5;
    v13 = 444;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 445, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
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
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_25;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v17, 2053731191);
LABEL_27:
  if ( !Pool2 )
  {
LABEL_46:
    v15 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        447,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
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
    v27 = 448;
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
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 453, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
        }
        else
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v27 = 452;
            goto LABEL_31;
          }
        }
      }
      else
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v27 = 451;
          goto LABEL_31;
        }
      }
    }
    else
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v27 = 450;
        goto LABEL_31;
      }
    }
  }
  else
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v27 = 449;
LABEL_31:
      WPP_SF_d(v26->AttachedDevice, v27, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, (unsigned int)v25);
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
0x1400491bc  push    rbp
0x1400491be  push    rbx
0x1400491bf  push    rsi
0x1400491c0  push    rdi
0x1400491c1  push    r12
0x1400491c3  push    r13
0x1400491c5  push    r14
0x1400491c7  push    r15
0x1400491c9  lea     rbp, [rsp-7]
0x1400491ce  sub     rsp, 0F8h
0x1400491d5  mov     rax, cs:__security_cookie
0x1400491dc  xor     rax, rsp
0x1400491df  mov     [rbp+3Fh+var_48], rax
0x1400491e3  mov     rax, [rbp+3Fh+arg_40]
0x1400491ea  xor     edi, edi
0x1400491ec  mov     r12d, [rbp+3Fh+arg_28]
0x1400491f0  xor     r15d, r15d
0x1400491f3  mov     [rsp+130h+var_D0], r9
0x1400491f8  mov     r14, r8
0x1400491fb  mov     [rsp+130h+var_C8], rdx
0x140049200  mov     r8, rdx
0x140049203  mov     [rsp+130h+var_F0], rcx
0x140049208  mov     [rsp+130h+var_C0], rax
0x14004920d  cmp     r12d, 20h ; ' '
0x140049211  jbe     short loc_140049248
0x140049213  mov     rcx, cs:WPP_GLOBAL_Control
0x14004921a  lea     rsi, WPP_GLOBAL_Control
0x140049221  cmp     rcx, rsi
0x140049224  jz      short loc_14004923E
0x140049226  mov     edx, 1BBh
0x14004922b  mov     r9d, r12d
0x14004922e  mov     rcx, [rcx+18h]
0x140049232  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140049239  call    WPP_SF_d
0x14004923e  mov     ebx, 0C000000Dh
0x140049243  jmp     loc_140049762
0x140049248  cmp     [rbp+3Fh+arg_20], 20h ; ' '
0x14004924c  jnb     short loc_14004926C
0x14004924e  mov     rcx, cs:WPP_GLOBAL_Control
0x140049255  lea     rsi, WPP_GLOBAL_Control
0x14004925c  cmp     rcx, rsi
0x14004925f  jz      short loc_14004923E
0x140049261  mov     r9d, [rbp+3Fh+arg_20]
0x140049265  mov     edx, 1BCh
0x14004926a  jmp     short loc_14004922E
0x14004926c  test    r14, r14
0x14004926f  jnz     short loc_14004929B
0x140049271  mov     rcx, cs:WPP_GLOBAL_Control
0x140049278  lea     rsi, WPP_GLOBAL_Control
0x14004927f  cmp     rcx, rsi
0x140049282  jz      short loc_14004923E
0x140049284  mov     rcx, [rcx+18h]
0x140049288  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004928f  mov     edx, 1BDh
0x140049294  call    WPP_SF_
0x140049299  jmp     short loc_14004923E
0x14004929b  mov     rdx, cs:WPP_GLOBAL_Control
0x1400492a2  lea     rsi, WPP_GLOBAL_Control
0x1400492a9  cmp     rdx, rsi
0x1400492ac  jz      short loc_1400492EE
0x1400492ae  movzx   eax, word ptr [r14]
0x1400492b2  xorps   xmm0, xmm0
0x1400492b5  movups  [rsp+130h+var_E0], xmm0
0x1400492ba  mov     word ptr [rsp+130h+var_E0], ax
0x1400492bf  mov     r9, rcx
0x1400492c2  lea     rax, [r14+4]
0x1400492c6  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1400492cb  lea     rax, [rsp+130h+var_E0]
0x1400492d0  movaps  xmm0, [rsp+130h+var_E0]
0x1400492d5  movdqa  [rsp+130h+var_E0], xmm0
0x1400492db  mov     rcx, [rdx+18h]
0x1400492df  mov     qword ptr [rsp+130h+var_108], rax
0x1400492e4  mov     [rsp+130h+var_110], r8
0x1400492e9  call    WPP_SF__MAC__MAC__HEX_
0x1400492ee  mov     rax, [r14+0B8h]
0x1400492f5  mov     r13d, [r14]
0x1400492f8  add     r13d, 0Ah
0x1400492fc  movzx   ecx, byte ptr [rax+1]
0x140049300  add     r13d, ecx
0x140049303  cmp     r13d, 4Ch ; 'L'
0x140049307  ja      short loc_140049311
0x140049309  mov     r15d, 4Ch ; 'L'
0x14004930f  jmp     short loc_14004933A
0x140049311  lea     eax, [r13+10h]
0x140049315  mov     r15d, r13d
0x140049318  cmp     eax, 10h
0x14004931b  jb      loc_140049735
0x140049321  mov     ecx, 40h ; '@'
0x140049326  cmp     eax, ecx
0x140049328  ja      short loc_140049333
0x14004932a  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140049331  jmp     short loc_140049361
0x140049333  cmp     eax, 100h
0x140049338  ja      short loc_140049343
0x14004933a  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140049341  jmp     short loc_140049361
0x140049343  cmp     eax, 400h
0x140049348  ja      short loc_140049353
0x14004934a  lea     rbx, Lookaside
0x140049351  jmp     short loc_140049361
0x140049353  cmp     eax, 800h
0x140049358  ja      short loc_140049372
0x14004935a  lea     rbx, stru_1400B31C0
0x140049361  mov     rcx, rbx; Lookaside
0x140049364  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004936b  nop     dword ptr [rax+rax+00h]
0x140049370  jmp     short loc_140049388
0x140049372  xor     ebx, ebx
0x140049374  mov     edx, eax
0x140049376  mov     r8d, 7A697377h
0x14004937c  call    cs:__imp_ExAllocatePool2
0x140049383  nop     dword ptr [rax+rax+00h]
0x140049388  test    rax, rax
0x14004938b  jz      loc_140049735
0x140049391  lea     rdi, [rax+10h]
0x140049395  mov     r8d, r15d; Size
0x140049398  mov     rcx, rdi; void *
0x14004939b  mov     [rax], rbx
0x14004939e  xor     edx, edx; Val
0x1400493a0  mov     dword ptr [rax+8], 7A697377h
0x1400493a7  call    memset
0x1400493ac  mov     al, [r14]
0x1400493af  lea     rdx, [r14+4]; Src
0x1400493b3  mov     [rdi], al
0x1400493b5  lea     rcx, [rdi+1]; void *
0x1400493b9  mov     r8d, [r14]; Size
0x1400493bc  call    memmove
0x1400493c1  mov     edx, [r14]
0x1400493c4  mov     rax, [r14+40h]
0x1400493c8  inc     edx
0x1400493ca  movzx   eax, word ptr [rax+2]
0x1400493ce  mov     [rdx+rdi], ax
0x1400493d2  add     edx, 2
0x1400493d5  mov     rax, [r14+0B8h]
0x1400493dc  lea     ebx, [rdx+1]
0x1400493df  mov     al, [rax+1]
0x1400493e2  mov     [rdx+rdi], al
0x1400493e5  mov     rdx, [r14+0B8h]
0x1400493ec  mov     ecx, ebx
0x1400493ee  add     rcx, rdi; void *
0x1400493f1  movzx   r8d, byte ptr [rdx+1]; Size
0x1400493f6  add     rdx, 2; Src
0x1400493fa  call    memmove
0x1400493ff  mov     rax, [r14+0B8h]
0x140049406  lea     r8, aFtR0; "FT-R0"
0x14004940d  mov     rcx, [rsp+130h+var_F0]
0x140049412  mov     r9d, 5; int
0x140049418  mov     [rsp+130h+var_F8], 30h ; '0'; unsigned int
0x140049420  movzx   edx, byte ptr [rax+1]
0x140049424  mov     eax, [rcx]
0x140049426  add     edx, ebx
0x140049428  mov     [rdx+rdi], eax
0x14004942b  movzx   eax, word ptr [rcx+4]
0x14004942f  mov     rcx, [rsp+130h+var_D0]; int
0x140049434  mov     [rdx+rdi+4], ax
0x140049439  lea     rax, [rbp+3Fh+var_78]
0x14004943d  mov     edx, [rbp+3Fh+arg_20]; int
0x140049440  mov     [rsp+130h+var_100], rax; unsigned __int8 *
0x140049445  mov     [rsp+130h+var_108], r13d; unsigned int
0x14004944a  mov     [rsp+130h+var_110], rdi; unsigned __int8 *
0x14004944f  call    SSN_SHA256_PRF
0x140049454  mov     ebx, eax
0x140049456  test    eax, eax
0x140049458  jns     short loc_140049487
0x14004945a  mov     rcx, cs:WPP_GLOBAL_Control
0x140049461  cmp     rcx, rsi
0x140049464  jz      loc_140049762
0x14004946a  mov     edx, 1C0h
0x14004946f  mov     rcx, [rcx+18h]
0x140049473  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004947a  mov     r9d, eax
0x14004947d  call    WPP_SF_d
0x140049482  jmp     loc_140049762
0x140049487  xorps   xmm0, xmm0
0x14004948a  mov     r8d, r15d; Size
0x14004948d  xor     edx, edx; Val
0x14004948f  mov     r13d, r15d
0x140049492  mov     rcx, rdi; void *
0x140049495  movups  xmmword ptr [rbp+3Fh+var_B8], xmm0
0x140049499  movups  [rbp+3Fh+var_A8], xmm0
0x14004949d  call    memset
0x1400494a2  mov     eax, dword ptr cs:aFtR0n; "FT-R0N"
0x1400494a8  lea     r8, [rbp+3Fh+var_B8]; unsigned __int8 *
0x1400494ac  mov     [rdi], eax
0x1400494ae  mov     r9d, 20h ; ' '; unsigned int
0x1400494b4  movzx   eax, word ptr cs:aFtR0n+4; "0N"
0x1400494bb  mov     rcx, rdi; unsigned __int8 *
0x1400494be  mov     [rdi+4], ax
0x1400494c2  movups  xmm0, [rbp+3Fh+var_58]
0x1400494c6  lea     edx, [r9-0Ah]; unsigned int
0x1400494ca  movdqu  xmmword ptr [rdi+6], xmm0
0x1400494cf  call    WL_SHA256
0x1400494d4  mov     ebx, eax
0x1400494d6  test    eax, eax
0x1400494d8  jns     short loc_1400494F4
0x1400494da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400494e1  cmp     rcx, rsi
0x1400494e4  jz      loc_140049762
0x1400494ea  mov     edx, 1C1h
0x1400494ef  jmp     loc_14004946F
0x1400494f4  movups  xmm0, xmmword ptr [rbp+3Fh+var_B8]
0x1400494f8  mov     r8, r13; Size
0x1400494fb  xor     edx, edx; Val
0x1400494fd  mov     rcx, rdi; void *
0x140049500  movdqu  xmmword ptr [r14+68h], xmm0
0x140049506  call    memset
0x14004950b  mov     rdx, [r14+0B0h]
0x140049512  mov     rcx, rdi; void *
0x140049515  movzx   r8d, byte ptr [rdx+1]; Size
0x14004951a  add     rdx, 2; Src
0x14004951e  call    memmove
0x140049523  mov     rax, [r14+0B0h]
0x14004952a  lea     r8, aFtR1; "FT-R1"
0x140049531  mov     r13, [rsp+130h+var_F0]
0x140049536  movzx   ecx, byte ptr [rax+1]
0x14004953a  mov     eax, [r13+0]
0x14004953e  mov     [rcx+rdi], eax
0x140049541  movzx   eax, word ptr [r13+4]
0x140049546  mov     [rcx+rdi+4], ax
0x14004954b  mov     ecx, 20h ; ' '
0x140049550  mov     [rsp+130h+var_F8], ecx; unsigned int
0x140049554  lea     rax, [rbp+3Fh+var_98]
0x140049558  mov     [rsp+130h+var_100], rax; unsigned __int8 *
0x14004955d  mov     edx, ecx; int
0x14004955f  mov     [rsp+130h+var_108], 0Ch; unsigned int
0x140049567  lea     r9d, [rcx-1Bh]; int
0x14004956b  mov     [rsp+130h+var_110], rdi; unsigned __int8 *
0x140049570  lea     rcx, [rbp+3Fh+var_78]; int
0x140049574  call    SSN_SHA256_PRF
0x140049579  mov     ebx, eax
0x14004957b  test    eax, eax
0x14004957d  jns     short loc_140049599
0x14004957f  mov     rcx, cs:WPP_GLOBAL_Control
0x140049586  cmp     rcx, rsi
0x140049589  jz      loc_140049762
0x14004958f  mov     edx, 1C2h
0x140049594  jmp     loc_14004946F
0x140049599  xorps   xmm0, xmm0
0x14004959c  mov     r8d, r15d; Size
0x14004959f  xor     edx, edx; Val
0x1400495a1  mov     rcx, rdi; void *
0x1400495a4  movups  xmmword ptr [rbp+3Fh+var_B8], xmm0
0x1400495a8  movups  [rbp+3Fh+var_A8], xmm0
0x1400495ac  call    memset
0x1400495b1  mov     eax, dword ptr cs:aFtR1n; "FT-R1N"
0x1400495b7  lea     rcx, [rdi+16h]; void *
0x1400495bb  mov     [rdi], eax
0x1400495bd  movzx   eax, word ptr cs:aFtR1n+4; "1N"
0x1400495c4  mov     [rdi+4], ax
0x1400495c8  movups  xmm0, xmmword ptr [r14+68h]
0x1400495cd  movdqu  xmmword ptr [rdi+6], xmm0
0x1400495d2  mov     rdx, [r14+0B0h]
0x1400495d9  movzx   r8d, byte ptr [rdx+1]; Size
0x1400495de  add     rdx, 2; Src
0x1400495e2  call    memmove
0x1400495e7  mov     rax, [r14+0B0h]
0x1400495ee  lea     r8, [rbp+3Fh+var_B8]; unsigned __int8 *
0x1400495f2  mov     r9d, 20h ; ' '; unsigned int
0x1400495f8  movzx   ecx, byte ptr [rax+1]
0x1400495fc  mov     eax, [r13+0]
0x140049600  lea     edx, [r9+2]; unsigned int
0x140049604  mov     [rcx+rdi+16h], eax
0x140049608  movzx   eax, word ptr [r13+4]
0x14004960d  mov     [rcx+rdi+1Ah], ax
0x140049612  mov     rcx, rdi; unsigned __int8 *
0x140049615  call    WL_SHA256
0x14004961a  mov     ebx, eax
0x14004961c  test    eax, eax
0x14004961e  jns     short loc_14004963A
0x140049620  mov     rcx, cs:WPP_GLOBAL_Control
0x140049627  cmp     rcx, rsi
0x14004962a  jz      loc_140049762
0x140049630  mov     edx, 1C3h
0x140049635  jmp     loc_14004946F
0x14004963a  movups  xmm0, xmmword ptr [rbp+3Fh+var_B8]
0x14004963e  movzx   ecx, byte ptr [r14+0DAh]
0x140049646  xor     edx, edx; Val
0x140049648  mov     rax, [r14+50h]
0x14004964c  movdqu  xmmword ptr [r14+78h], xmm0
0x140049652  mov     r8d, r15d; Size
0x140049655  movdqu  xmmword ptr [rcx+rax+2], xmm0
0x14004965b  mov     rcx, rdi; void *
0x14004965e  call    memset
0x140049663  mov     rax, [rbp+3Fh+arg_30]
0x140049667  lea     r8, aFtPtk; "FT-PTK"
0x14004966e  mov     rcx, [rsp+130h+var_C8]
0x140049673  mov     r9d, 6; int
0x140049679  movups  xmm0, xmmword ptr [rax]
0x14004967c  lea     edx, [r9+1Ah]; int
0x140049680  movups  xmmword ptr [rdi], xmm0
0x140049683  movups  xmm1, xmmword ptr [rax+10h]
0x140049687  mov     rax, [rbp+3Fh+arg_38]
0x14004968e  movups  xmmword ptr [rdi+10h], xmm1
0x140049692  movups  xmm0, xmmword ptr [rax]
0x140049695  movups  xmmword ptr [rdi+20h], xmm0
0x140049699  movups  xmm1, xmmword ptr [rax+10h]
0x14004969d  movups  xmmword ptr [rdi+30h], xmm1
0x1400496a1  mov     eax, [rcx]
0x1400496a3  mov     [rdi+40h], eax
0x1400496a6  movzx   eax, word ptr [rcx+4]
  ... truncated ...
```
