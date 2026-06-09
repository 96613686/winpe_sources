# GetIEsForFTContext(int,uchar const *,ulong,uchar const *,ulong,ulong &,uchar * *,NWF_FT_CONTEXT *)

- ea: `0x14004b344`
- end: `0x14004b88b`
- name: `?GetIEsForFTContext@@YAHHPEBEK0KAEAKPEAPEAEPEAUNWF_FT_CONTEXT@@@Z`
- size: `1351`
- prototype: `__int64 __fastcall(int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, unsigned int *, unsigned __int8 **, struct NWF_FT_CONTEXT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14004a904`

## callees

- `0x140020dc0`
- `0x140020f20`
- `0x14002f44c`
- `0x140030244`
- `0x14003af50`
- `0x140048cc8`
- `0x14004b344`
- `0x14004cfe8`
- `0x140057a60`
- `0x140097988`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b50d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004b50d`
- `ntoskrnl!ExAllocatePool2` at `0x14004b52a`
- `ntoskrnl!ExAllocatePool2` at `0x14004b52a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004b591`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004b591`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b5a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004b5a2`

## pseudocode

```c
__int64 __fastcall GetIEsForFTContext(
        int a1,
        const unsigned __int8 *a2,
        unsigned int a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned __int8 **a7,
        struct NWF_FT_CONTEXT *a8)
{
  struct NWF_FT_CONTEXT *v8; // rbx
  int v9; // r15d
  unsigned __int8 **p_pMDDIE; // r9
  unsigned int uResponseIEsLength; // edx
  const unsigned __int8 *v13; // rcx
  unsigned int Dot11InfoElement; // r14d
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned __int8 *pMDDIE; // rcx
  int v21; // edx
  __int64 v22; // r9
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  unsigned __int8 **p_pFTEIE; // r12
  unsigned __int8 *v26; // r8
  int v27; // eax
  unsigned int responseIEsOffset; // eax
  unsigned int v29; // eax
  unsigned int v30; // r15d
  unsigned int v31; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // r14
  _DWORD *Pool2; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  unsigned __int8 *v36; // r14
  unsigned __int8 *pReassembledFTEIE; // rcx
  unsigned __int8 *v38; // rcx
  int v39; // eax
  __int16 FTEIELength; // ax
  _DEVICE_OBJECT *AttachedDevice; // rcx
  const unsigned __int8 *v42; // r14
  int v43; // ecx
  unsigned int v44; // eax
  PDEVICE_OBJECT v45; // rcx
  __int64 v46; // rdx
  unsigned int v47; // [rsp+38h] [rbp-69h] BYREF
  unsigned int v48; // [rsp+3Ch] [rbp-65h]
  __int128 v49; // [rsp+48h] [rbp-59h] BYREF
  _DWORD v50[32]; // [rsp+58h] [rbp-49h] BYREF

  v8 = a8;
  v9 = a1;
  p_pMDDIE = &a8->pMDDIE;
  uResponseIEsLength = a8->uResponseIEsLength;
  v13 = (const unsigned __int8 *)a8 + a8->responseIEsOffset;
  *a7 = 0;
  Dot11InfoElement = GetDot11InfoElement(v13, uResponseIEsLength, 0x36u, (struct DOT11_INFO_ELEMENT **)p_pMDDIE);
  if ( Dot11InfoElement )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return Dot11InfoElement;
    v16 = v8->uResponseIEsLength;
    v17 = 410;
LABEL_4:
    WPP_SF_d(v15->AttachedDevice, v17, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v16);
    return Dot11InfoElement;
  }
  IsEnabledDeviceUsageNoInline = Feature_57277348__private_IsEnabledDeviceUsageNoInline();
  pMDDIE = v8->pMDDIE;
  v21 = pMDDIE[1];
  if ( IsEnabledDeviceUsageNoInline )
  {
    v22 = (unsigned int)(v21 + 2);
    v8->MDDIELength = v22;
    if ( (unsigned int)v22 < 5 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v24 = 411;
LABEL_71:
        WPP_SF_d(v23->AttachedDevice, v24, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v22);
        return 3221226021LL;
      }
      return 3221226021LL;
    }
  }
  else
  {
    v8->MDDIELength = v21 + 2;
  }
  p_pFTEIE = &v8->pFTEIE;
  v8->MDID = *((_WORD *)pMDDIE + 1);
  if ( (unsigned int)GetDot11InfoElement(
                       (const unsigned __int8 *)v8 + v8->responseIEsOffset,
                       v8->uResponseIEsLength,
                       0x37u,
                       (struct DOT11_INFO_ELEMENT **)&v8->pFTEIE)
    || (v26 = *p_pFTEIE, v27 = (*p_pFTEIE)[1], (unsigned __int8)v27 < 0x52u) )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v22 = v8->uResponseIEsLength;
      v24 = 412;
      goto LABEL_71;
    }
    return 3221226021LL;
  }
  v8->FTEIELength = v27 + 2;
  responseIEsOffset = v8->responseIEsOffset;
  LODWORD(a8) = 0;
  v29 = v8->uResponseIEsLength + (_DWORD)v8 - (_DWORD)v26 + responseIEsOffset;
  v47 = 0;
  v48 = v29;
  if ( (unsigned int)Dot11GetReassembledIE(&a8, v29, v26, &v47, &a8, 0) )
  {
LABEL_36:
    a8 = 0;
    if ( a2 && a3 )
    {
      if ( a3 < 2 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v24 = 416;
          v22 = a3;
          goto LABEL_71;
        }
        return 3221226021LL;
      }
      v42 = a2;
    }
    else
    {
      if ( v9 )
      {
        Dot11InfoElement = GetDot11InfoElement(a4, a5, 0x30u, (struct DOT11_INFO_ELEMENT **)&a8);
        if ( Dot11InfoElement )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            return Dot11InfoElement;
          v16 = a5;
          v17 = 417;
          goto LABEL_4;
        }
      }
      else
      {
        Dot11InfoElement = GetDot11InfoElement(
                             (const unsigned __int8 *)v8 + v8->responseIEsOffset,
                             v8->uResponseIEsLength,
                             0x30u,
                             (struct DOT11_INFO_ELEMENT **)&a8);
        if ( Dot11InfoElement )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            return Dot11InfoElement;
          v16 = v8->uResponseIEsLength;
          v17 = 418;
          goto LABEL_4;
        }
      }
      v42 = (const unsigned __int8 *)a8;
    }
    memset(v50, 0, 0x48u);
    v43 = v42[1];
    if ( (unsigned __int8)(v43 - 1) > 0xEAu
      || (unsigned int)IEPRSNParseIE((unsigned __int8 *)v42 + 2, v43, a6, (struct DOT11_RSN_IE_INFO *)v50) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_lll(
          WPP_GLOBAL_Control->AttachedDevice,
          419,
          WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
          v42[1],
          v8->uResponseIEsLength,
          235);
      return 3221226021LL;
    }
    v44 = *a6;
    if ( (*a6 & 0x10) != 0 )
    {
      v8->UcastCipher = v50[4];
      v8->McastCipher = v50[1];
      v8->GroupMgmtCipher = v50[17];
      if ( (*a6 & 0x40) != 0 )
      {
        v8->PMKIDCount = HIWORD(v50[10]);
        v8->PMKIDCountOffset = LOBYTE(v50[16]) + 2;
      }
      if ( v42 == a2 || v8->PMKIDCount )
      {
        *a7 = (unsigned __int8 *)v42;
        FreeRSNIEContent((struct DOT11_RSN_IE_INFO *)v50);
        return 0;
      }
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_65;
      v44 = v8->uResponseIEsLength;
      v46 = 421;
    }
    else
    {
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
LABEL_65:
        FreeRSNIEContent((struct DOT11_RSN_IE_INFO *)v50);
        return 3221226021LL;
      }
      v46 = 420;
    }
    WPP_SF_Dd(v45->AttachedDevice, v46, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v42[1], v44);
    goto LABEL_65;
  }
  v30 = (unsigned int)a8;
  if ( v47 == (_DWORD)a8 )
  {
LABEL_35:
    v9 = a1;
    goto LABEL_36;
  }
  v31 = (_DWORD)a8 + 16;
  if ( (unsigned int)a8 < 0xFFFFFFF0 )
  {
    if ( v31 > 0x40 )
    {
      if ( v31 > 0x100 )
      {
        if ( v31 > 0x400 )
        {
          if ( v31 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v31, 2053731191);
LABEL_26:
            if ( Pool2 )
            {
              v35 = v48;
              *(_QWORD *)Pool2 = p_WaitListHead;
              v36 = (unsigned __int8 *)(Pool2 + 4);
              Pool2[2] = 2053731191;
              if ( !(unsigned int)Dot11GetReassembledIE(v34, v35, *p_pFTEIE, &v47, &a8, Pool2 + 4) )
              {
                pReassembledFTEIE = v8->pReassembledFTEIE;
                if ( pReassembledFTEIE )
                {
                  v38 = pReassembledFTEIE - 16;
                  if ( *(_QWORD *)v38 )
                    ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v38, v38);
                  else
                    ExFreePoolWithTag(v38, *((_DWORD *)v38 + 2));
                }
                v39 = (int)a8;
                v8->FTEIELength = (unsigned int)a8;
                v8->pReassembledFTEIE = v36;
                *p_pFTEIE = v36;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  WPP_SF_Dd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    414,
                    WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                    v47,
                    v39);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    FTEIELength = v8->FTEIELength;
                    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
                    v49 = 0;
                    LOWORD(v49) = FTEIELength;
                    *((_QWORD *)&v49 + 1) = *p_pFTEIE;
                    WPP_SF__HEX_(AttachedDevice, 415, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, &v49);
                  }
                }
              }
              goto LABEL_35;
            }
            goto LABEL_41;
          }
          p_WaitListHead = &stru_1400B31C0;
        }
        else
        {
          p_WaitListHead = &Lookaside;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_26;
  }
LABEL_41:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 413, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v30);
  return 3221225626LL;
}

```

## disassembly

```asm
0x14004b344  mov     rax, rsp
0x14004b347  mov     [rax+18h], rbx
0x14004b34b  mov     [rax+20h], r9
0x14004b34f  mov     [rax+10h], rdx
0x14004b353  mov     [rax+8], ecx
0x14004b356  push    rbp
0x14004b357  push    rsi
0x14004b358  push    rdi
0x14004b359  push    r12
0x14004b35b  push    r13
0x14004b35d  push    r14
0x14004b35f  push    r15
0x14004b361  lea     rbp, [rax-3Fh]
0x14004b365  sub     rsp, 0A0h
0x14004b36c  mov     rbx, [rbp+37h+arg_38]
0x14004b370  mov     r15d, ecx
0x14004b373  mov     rax, [rbp+37h+arg_30]
0x14004b377  mov     r13d, r8d
0x14004b37a  xor     esi, esi
0x14004b37c  mov     r8b, 36h ; '6'; unsigned __int8
0x14004b37f  mov     ecx, [rbx+174h]
0x14004b385  lea     r9, [rbx+40h]; struct DOT11_INFO_ELEMENT **
0x14004b389  mov     edx, [rbx+170h]; unsigned int
0x14004b38f  add     rcx, rbx; unsigned __int8 *
0x14004b392  mov     [rax], rsi
0x14004b395  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x14004b39a  mov     r14d, eax
0x14004b39d  test    eax, eax
0x14004b39f  jz      short loc_14004B3D8
0x14004b3a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b3a8  lea     rdi, WPP_GLOBAL_Control
0x14004b3af  cmp     rcx, rdi
0x14004b3b2  jz      short loc_14004B3D0
0x14004b3b4  mov     r9d, [rbx+170h]
0x14004b3bb  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004b3c2  mov     edx, 19Ah
0x14004b3c7  mov     rcx, [rcx+18h]
0x14004b3cb  call    WPP_SF_d
0x14004b3d0  mov     eax, r14d
0x14004b3d3  jmp     loc_14004B86F
0x14004b3d8  call    Feature_57277348__private_IsEnabledDeviceUsageNoInline
0x14004b3dd  mov     rcx, [rbx+40h]
0x14004b3e1  movzx   edx, byte ptr [rcx+1]
0x14004b3e5  test    eax, eax
0x14004b3e7  jz      short loc_14004B418
0x14004b3e9  lea     r9d, [rdx+2]
0x14004b3ed  mov     [rbx+34h], r9d
0x14004b3f1  cmp     r9d, 5
0x14004b3f5  jnb     short loc_14004B41E
0x14004b3f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b3fe  lea     rdi, WPP_GLOBAL_Control
0x14004b405  cmp     rcx, rdi
0x14004b408  jz      loc_14004B86A
0x14004b40e  mov     edx, 19Bh
0x14004b413  jmp     loc_14004B85A
0x14004b418  lea     eax, [rdx+2]
0x14004b41b  mov     [rbx+34h], eax
0x14004b41e  mov     eax, 2
0x14004b423  lea     r12, [rbx+48h]
0x14004b427  mov     r9, r12; struct DOT11_INFO_ELEMENT **
0x14004b42a  mov     r8b, 37h ; '7'; unsigned __int8
0x14004b42d  movzx   eax, word ptr [rcx+rax]
0x14004b431  mov     [rbx+24h], ax
0x14004b435  mov     ecx, [rbx+174h]
0x14004b43b  mov     edx, [rbx+170h]; unsigned int
0x14004b441  add     rcx, rbx; unsigned __int8 *
0x14004b444  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x14004b449  test    eax, eax
0x14004b44b  jnz     loc_14004B83B
0x14004b451  mov     r8, [r12]
0x14004b455  movzx   eax, byte ptr [r8+1]
0x14004b45a  cmp     al, 52h ; 'R'
0x14004b45c  jb      loc_14004B83B
0x14004b462  add     eax, 2
0x14004b465  mov     [rsp+28h], rsi
0x14004b46a  mov     [rbx+38h], eax
0x14004b46d  lea     r9, [rbp+37h+var_A0]
0x14004b471  mov     eax, [rbx+174h]
0x14004b477  mov     ecx, ebx
0x14004b479  sub     ecx, r8d
0x14004b47c  mov     dword ptr [rbp+37h+arg_38], esi
0x14004b47f  add     ecx, [rbx+170h]
0x14004b485  add     eax, ecx
0x14004b487  mov     [rbp+37h+var_A0], esi
0x14004b48a  lea     rcx, [rbp+37h+arg_38]
0x14004b48e  mov     [rbp+37h+var_9C], eax
0x14004b491  mov     edx, eax
0x14004b493  mov     [rsp+0D0h+var_B0], rcx
0x14004b498  call    Dot11GetReassembledIE
0x14004b49d  lea     rdi, WPP_GLOBAL_Control
0x14004b4a4  lea     rsi, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004b4ab  test    eax, eax
0x14004b4ad  jnz     loc_14004B629
0x14004b4b3  mov     r15d, dword ptr [rbp+37h+arg_38]
0x14004b4b7  cmp     [rbp+37h+var_A0], r15d
0x14004b4bb  jz      loc_14004B625
0x14004b4c1  lea     eax, [r15+10h]
0x14004b4c5  cmp     eax, 10h
0x14004b4c8  jb      loc_14004B665
0x14004b4ce  cmp     eax, 40h ; '@'
0x14004b4d1  ja      short loc_14004B4DC
0x14004b4d3  lea     r14, WPP_MAIN_CB.DeviceQueue
0x14004b4da  jmp     short loc_14004B50A
0x14004b4dc  cmp     eax, 100h
0x14004b4e1  ja      short loc_14004B4EC
0x14004b4e3  lea     r14, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004b4ea  jmp     short loc_14004B50A
0x14004b4ec  cmp     eax, 400h
0x14004b4f1  ja      short loc_14004B4FC
0x14004b4f3  lea     r14, Lookaside
0x14004b4fa  jmp     short loc_14004B50A
0x14004b4fc  cmp     eax, 800h
0x14004b501  ja      short loc_14004B51B
0x14004b503  lea     r14, stru_1400B31C0
0x14004b50a  mov     rcx, r14; Lookaside
0x14004b50d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004b514  nop     dword ptr [rax+rax+00h]
0x14004b519  jmp     short loc_14004B536
0x14004b51b  xor     r14d, r14d
0x14004b51e  mov     edx, eax
0x14004b520  mov     r8d, 7A697377h
0x14004b526  lea     ecx, [r14+40h]
0x14004b52a  call    cs:__imp_ExAllocatePool2
0x14004b531  nop     dword ptr [rax+rax+00h]
0x14004b536  test    rax, rax
0x14004b539  jz      loc_14004B665
0x14004b53f  mov     edx, [rbp+37h+var_9C]
0x14004b542  lea     r9, [rbp+37h+var_A0]
0x14004b546  mov     [rax], r14
0x14004b549  lea     r14, [rax+10h]
0x14004b54d  mov     dword ptr [rax+8], 7A697377h
0x14004b554  lea     rax, [rbp+37h+arg_38]
0x14004b558  mov     r8, [r12]
0x14004b55c  mov     [rsp+28h], r14
0x14004b561  mov     [rsp+0D0h+var_B0], rax
0x14004b566  call    Dot11GetReassembledIE
0x14004b56b  test    eax, eax
0x14004b56d  jnz     loc_14004B625
0x14004b573  mov     rcx, [rbx+168h]
0x14004b57a  test    rcx, rcx
0x14004b57d  jz      short loc_14004B5AE
0x14004b57f  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004b583  mov     rax, [rcx]
0x14004b586  test    rax, rax
0x14004b589  jz      short loc_14004B59F
0x14004b58b  mov     rdx, rcx; Entry
0x14004b58e  mov     rcx, rax; Lookaside
0x14004b591  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004b598  nop     dword ptr [rax+rax+00h]
0x14004b59d  jmp     short loc_14004B5AE
0x14004b59f  mov     edx, [rcx+8]; Tag
0x14004b5a2  call    cs:__imp_ExFreePoolWithTag
0x14004b5a9  nop     dword ptr [rax+rax+00h]
0x14004b5ae  mov     eax, dword ptr [rbp+37h+arg_38]
0x14004b5b1  mov     [rbx+38h], eax
0x14004b5b4  mov     [rbx+168h], r14
0x14004b5bb  mov     [r12], r14
0x14004b5bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b5c6  cmp     rcx, rdi
0x14004b5c9  jz      short loc_14004B625
0x14004b5cb  mov     r9d, [rbp+37h+var_A0]
0x14004b5cf  mov     edx, 19Eh
0x14004b5d4  mov     rcx, [rcx+18h]
0x14004b5d8  mov     r8, rsi
0x14004b5db  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14004b5df  call    WPP_SF_Dd
0x14004b5e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b5eb  cmp     rcx, rdi
0x14004b5ee  jz      short loc_14004B625
0x14004b5f0  movzx   eax, word ptr [rbx+38h]
0x14004b5f4  lea     r9, [rbp+37h+var_90]
0x14004b5f8  mov     rcx, [rcx+18h]
0x14004b5fc  xorps   xmm0, xmm0
0x14004b5ff  movups  [rbp+37h+var_90], xmm0
0x14004b603  mov     word ptr [rbp+37h+var_90], ax
0x14004b607  mov     edx, 19Fh
0x14004b60c  mov     rax, [r12]
0x14004b610  mov     r8, rsi
0x14004b613  mov     qword ptr [rbp+37h+var_90+8], rax
0x14004b617  movaps  xmm0, [rbp+37h+var_90]
0x14004b61b  movdqa  [rbp+37h+var_90], xmm0
0x14004b620  call    WPP_SF__HEX_
0x14004b625  mov     r15d, [rbp+37h+arg_0]
0x14004b629  mov     r12, [rbp+37h+arg_8]
0x14004b62d  mov     [rbp+37h+arg_38], 0
0x14004b635  test    r12, r12
0x14004b638  jz      short loc_14004B6A5
0x14004b63a  test    r13d, r13d
0x14004b63d  jz      short loc_14004B6A5
0x14004b63f  cmp     r13d, 2
0x14004b643  jnb     short loc_14004B69A
0x14004b645  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b64c  cmp     rcx, rdi
0x14004b64f  jz      loc_14004B86A
0x14004b655  mov     edx, 1A0h
0x14004b65a  mov     r9d, r13d
0x14004b65d  mov     r8, rsi
0x14004b660  jmp     loc_14004B861
0x14004b665  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b66c  lea     rdi, WPP_GLOBAL_Control
0x14004b673  cmp     rcx, rdi
0x14004b676  jz      short loc_14004B690
0x14004b678  mov     rcx, [rcx+18h]
0x14004b67c  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004b683  mov     edx, 19Dh
0x14004b688  mov     r9d, r15d
0x14004b68b  call    WPP_SF_d
0x14004b690  mov     eax, 0C000009Ah
0x14004b695  jmp     loc_14004B86F
0x14004b69a  mov     r14, r12
0x14004b69d  xor     r13d, r13d
0x14004b6a0  jmp     loc_14004B725
0x14004b6a5  xor     r13d, r13d
0x14004b6a8  lea     r9, [rbp+37h+arg_38]; struct DOT11_INFO_ELEMENT **
0x14004b6ac  mov     r8b, 30h ; '0'; unsigned __int8
0x14004b6af  test    r15d, r15d
0x14004b6b2  jz      short loc_14004B6E8
0x14004b6b4  mov     edx, [rbp+37h+arg_20]; unsigned int
0x14004b6b7  mov     rcx, [rbp+37h+arg_18]; unsigned __int8 *
0x14004b6bb  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x14004b6c0  mov     r14d, eax
0x14004b6c3  test    eax, eax
0x14004b6c5  jz      short loc_14004B721
0x14004b6c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b6ce  cmp     rcx, rdi
0x14004b6d1  jz      loc_14004B3D0
0x14004b6d7  mov     r9d, [rbp+37h+arg_20]
0x14004b6db  mov     edx, 1A1h
0x14004b6e0  mov     r8, rsi
0x14004b6e3  jmp     loc_14004B3C7
0x14004b6e8  mov     ecx, [rbx+174h]
0x14004b6ee  mov     edx, [rbx+170h]; unsigned int
0x14004b6f4  add     rcx, rbx; unsigned __int8 *
0x14004b6f7  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x14004b6fc  mov     r14d, eax
0x14004b6ff  test    eax, eax
0x14004b701  jz      short loc_14004B721
0x14004b703  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b70a  cmp     rcx, rdi
0x14004b70d  jz      loc_14004B3D0
0x14004b713  mov     r9d, [rbx+170h]
0x14004b71a  mov     edx, 1A2h
0x14004b71f  jmp     short loc_14004B6E0
0x14004b721  mov     r14, [rbp+37h+arg_38]
0x14004b725  xor     edx, edx; Val
0x14004b727  lea     rcx, [rbp+37h+var_80]; void *
0x14004b72b  lea     r8d, [rdx+48h]; Size
0x14004b72f  call    memset
0x14004b734  movzx   ecx, byte ptr [r14+1]
0x14004b739  lea     eax, [rcx-1]
0x14004b73c  cmp     al, 0EAh
0x14004b73e  ja      loc_14004B805
0x14004b744  mov     r15, [rbp+37h+arg_28]
0x14004b748  lea     r9, [rbp+37h+var_80]; struct DOT11_RSN_IE_INFO *
0x14004b74c  mov     edx, ecx; unsigned int
0x14004b74e  mov     r8, r15; unsigned int *
0x14004b751  lea     rcx, [r14+2]; unsigned __int8 *
0x14004b755  call    ?IEPRSNParseIE@@YAJPEAEKPEAKPEAUDOT11_RSN_IE_INFO@@@Z; IEPRSNParseIE(uchar *,ulong,ulong *,DOT11_RSN_IE_INFO *)
0x14004b75a  test    eax, eax
0x14004b75c  jnz     loc_14004B805
0x14004b762  mov     eax, [r15]
0x14004b765  test    al, 10h
0x14004b767  jnz     short loc_14004B77C
0x14004b769  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b770  cmp     rcx, rdi
0x14004b773  jz      short loc_14004B7E6
0x14004b775  mov     edx, 1A4h
0x14004b77a  jmp     short loc_14004B7D1
0x14004b77c  mov     eax, [rbp+37h+var_70]
0x14004b77f  mov     [rbx+28h], eax
0x14004b782  mov     eax, [rbp+37h+var_7C]
0x14004b785  mov     [rbx+2Ch], eax
0x14004b788  mov     eax, [rbp+37h+var_3C]
0x14004b78b  mov     [rbx+30h], eax
0x14004b78e  mov     eax, [r15]
0x14004b791  test    al, 40h
0x14004b793  jz      short loc_14004B7AB
0x14004b795  movzx   eax, [rbp+37h+var_56]
0x14004b799  mov     [rbx+0D8h], ax
0x14004b7a0  mov     al, [rbp+37h+var_40]
0x14004b7a3  add     al, 2
0x14004b7a5  mov     [rbx+0DAh], al
0x14004b7ab  cmp     r14, r12
0x14004b7ae  jz      short loc_14004B7F1
0x14004b7b0  cmp     [rbx+0D8h], r13w
0x14004b7b8  jnz     short loc_14004B7F1
0x14004b7ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b7c1  cmp     rcx, rdi
0x14004b7c4  jz      short loc_14004B7E6
0x14004b7c6  mov     eax, [rbx+170h]
0x14004b7cc  mov     edx, 1A5h
0x14004b7d1  movzx   r9d, byte ptr [r14+1]
0x14004b7d6  mov     r8, rsi
0x14004b7d9  mov     rcx, [rcx+18h]
0x14004b7dd  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14004b7e1  call    WPP_SF_Dd
0x14004b7e6  lea     rcx, [rbp+37h+var_80]; struct DOT11_RSN_IE_INFO *
0x14004b7ea  call    ?FreeRSNIEContent@@YAXPEAUDOT11_RSN_IE_INFO@@@Z; FreeRSNIEContent(DOT11_RSN_IE_INFO *)
0x14004b7ef  jmp     short loc_14004B86A
0x14004b7f1  mov     rax, [rbp+37h+arg_30]
  ... truncated ...
```
