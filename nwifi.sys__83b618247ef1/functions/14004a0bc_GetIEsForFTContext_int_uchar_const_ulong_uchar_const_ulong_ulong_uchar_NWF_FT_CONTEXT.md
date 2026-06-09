# GetIEsForFTContext(int,uchar const *,ulong,uchar const *,ulong,ulong &,uchar * *,NWF_FT_CONTEXT *)

- ea: `0x14004a0bc`
- end: `0x14004a603`
- name: `?GetIEsForFTContext@@YAHHPEBEK0KAEAKPEAPEAEPEAUNWF_FT_CONTEXT@@@Z`
- size: `1351`
- prototype: `__int64 __fastcall(int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, unsigned int *, unsigned __int8 **, struct NWF_FT_CONTEXT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14004967c`

## callees

- `0x140020dc0`
- `0x140020f20`
- `0x14002f1bc`
- `0x14002ffb4`
- `0x14003ad30`
- `0x140047a40`
- `0x14004a0bc`
- `0x14004bd60`
- `0x140056240`
- `0x1400961a8`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004a285`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004a285`
- `ntoskrnl!ExAllocatePool2` at `0x14004a2a2`
- `ntoskrnl!ExAllocatePool2` at `0x14004a2a2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004a309`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004a309`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a31a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a31a`

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
  __int64 v30; // r9
  unsigned int v31; // r15d
  unsigned int v32; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // r14
  char *Pool2; // rax
  __int64 v35; // rcx
  unsigned int v36; // edx
  unsigned __int8 *v37; // r14
  unsigned __int8 *pReassembledFTEIE; // rcx
  unsigned __int8 *v39; // rcx
  int v40; // eax
  __int16 FTEIELength; // ax
  _DEVICE_OBJECT *AttachedDevice; // rcx
  const unsigned __int8 *v43; // r14
  int v44; // ecx
  unsigned int v45; // eax
  PDEVICE_OBJECT v46; // rcx
  __int64 v47; // rdx
  unsigned int v48; // [rsp+38h] [rbp-69h] BYREF
  unsigned int v49; // [rsp+3Ch] [rbp-65h]
  __int128 v50; // [rsp+48h] [rbp-59h] BYREF
  _DWORD v51[32]; // [rsp+58h] [rbp-49h] BYREF

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
    WPP_SF_d(v15->AttachedDevice, v17, WPP_e90d411d816e312466897e39e745b158_Traceguids, v16);
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
        WPP_SF_d(v23->AttachedDevice, v24, WPP_e90d411d816e312466897e39e745b158_Traceguids, v22);
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
  v48 = 0;
  v49 = v29;
  if ( (unsigned int)Dot11GetReassembledIE((__int64)&a8, v29, v26, &v48, (unsigned int *)&a8, 0) )
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
      v43 = a2;
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
      v43 = (const unsigned __int8 *)a8;
    }
    memset(v51, 0, 0x48u);
    v44 = v43[1];
    if ( (unsigned __int8)(v44 - 1) > 0xEAu
      || (unsigned int)IEPRSNParseIE((unsigned __int8 *)v43 + 2, v44, a6, (struct DOT11_RSN_IE_INFO *)v51) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_lll(
          WPP_GLOBAL_Control->AttachedDevice,
          419,
          WPP_e90d411d816e312466897e39e745b158_Traceguids,
          v43[1],
          v8->uResponseIEsLength,
          235);
      return 3221226021LL;
    }
    v45 = *a6;
    if ( (*a6 & 0x10) != 0 )
    {
      v8->UcastCipher = v51[4];
      v8->McastCipher = v51[1];
      v8->GroupMgmtCipher = v51[17];
      if ( (*a6 & 0x40) != 0 )
      {
        v8->PMKIDCount = HIWORD(v51[10]);
        v8->PMKIDCountOffset = LOBYTE(v51[16]) + 2;
      }
      if ( v43 == a2 || v8->PMKIDCount )
      {
        *a7 = (unsigned __int8 *)v43;
        FreeRSNIEContent((struct DOT11_RSN_IE_INFO *)v51);
        return 0;
      }
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_65;
      v45 = v8->uResponseIEsLength;
      v47 = 421;
    }
    else
    {
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
LABEL_65:
        FreeRSNIEContent((struct DOT11_RSN_IE_INFO *)v51);
        return 3221226021LL;
      }
      v47 = 420;
    }
    WPP_SF_Dd(v46->AttachedDevice, v47, WPP_e90d411d816e312466897e39e745b158_Traceguids, v43[1], v45);
    goto LABEL_65;
  }
  v31 = (unsigned int)a8;
  if ( v48 == (_DWORD)a8 )
  {
LABEL_35:
    v9 = a1;
    goto LABEL_36;
  }
  v32 = (_DWORD)a8 + 16;
  if ( (unsigned int)a8 < 0xFFFFFFF0 )
  {
    if ( v32 > 0x40 )
    {
      if ( v32 > 0x100 )
      {
        if ( v32 > 0x400 )
        {
          if ( v32 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (char *)ExAllocatePool2(64, v32, 2053731191, v30);
LABEL_26:
            if ( Pool2 )
            {
              v36 = v49;
              *(_QWORD *)Pool2 = p_WaitListHead;
              v37 = (unsigned __int8 *)(Pool2 + 16);
              *((_DWORD *)Pool2 + 2) = 2053731191;
              if ( !(unsigned int)Dot11GetReassembledIE(v35, v36, *p_pFTEIE, &v48, (unsigned int *)&a8, Pool2 + 16) )
              {
                pReassembledFTEIE = v8->pReassembledFTEIE;
                if ( pReassembledFTEIE )
                {
                  v39 = pReassembledFTEIE - 16;
                  if ( *(_QWORD *)v39 )
                    ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v39, v39);
                  else
                    ExFreePoolWithTag(v39, *((_DWORD *)v39 + 2));
                }
                v40 = (int)a8;
                v8->FTEIELength = (unsigned int)a8;
                v8->pReassembledFTEIE = v37;
                *p_pFTEIE = v37;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  WPP_SF_Dd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    414,
                    WPP_e90d411d816e312466897e39e745b158_Traceguids,
                    v48,
                    v40);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    FTEIELength = v8->FTEIELength;
                    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
                    v50 = 0;
                    LOWORD(v50) = FTEIELength;
                    *((_QWORD *)&v50 + 1) = *p_pFTEIE;
                    WPP_SF__HEX_(AttachedDevice, 415, WPP_e90d411d816e312466897e39e745b158_Traceguids, &v50);
                  }
                }
              }
              goto LABEL_35;
            }
            goto LABEL_41;
          }
          p_WaitListHead = &stru_1400B0180;
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
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_26;
  }
LABEL_41:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 413, WPP_e90d411d816e312466897e39e745b158_Traceguids, v31);
  return 3221225626LL;
}

```

## disassembly

```asm
0x14004a0bc  mov     rax, rsp
0x14004a0bf  mov     [rax+18h], rbx
0x14004a0c3  mov     [rax+20h], r9
0x14004a0c7  mov     [rax+10h], rdx
0x14004a0cb  mov     [rax+8], ecx
0x14004a0ce  push    rbp
0x14004a0cf  push    rsi
0x14004a0d0  push    rdi
0x14004a0d1  push    r12
0x14004a0d3  push    r13
0x14004a0d5  push    r14
0x14004a0d7  push    r15
0x14004a0d9  lea     rbp, [rax-3Fh]
0x14004a0dd  sub     rsp, 0A0h
0x14004a0e4  mov     rbx, [rbp+37h+arg_38]
0x14004a0e8  mov     r15d, ecx
0x14004a0eb  mov     rax, [rbp+37h+arg_30]
0x14004a0ef  mov     r13d, r8d
0x14004a0f2  xor     esi, esi
0x14004a0f4  mov     r8b, 36h ; '6'; unsigned __int8
0x14004a0f7  mov     ecx, [rbx+174h]
0x14004a0fd  lea     r9, [rbx+40h]; struct DOT11_INFO_ELEMENT **
0x14004a101  mov     edx, [rbx+170h]; unsigned int
0x14004a107  add     rcx, rbx; unsigned __int8 *
0x14004a10a  mov     [rax], rsi
0x14004a10d  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x14004a112  mov     r14d, eax
0x14004a115  test    eax, eax
0x14004a117  jz      short loc_14004A150
0x14004a119  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a120  lea     rdi, WPP_GLOBAL_Control
0x14004a127  cmp     rcx, rdi
0x14004a12a  jz      short loc_14004A148
0x14004a12c  mov     r9d, [rbx+170h]
0x14004a133  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004a13a  mov     edx, 19Ah
0x14004a13f  mov     rcx, [rcx+18h]
0x14004a143  call    WPP_SF_d
0x14004a148  mov     eax, r14d
0x14004a14b  jmp     loc_14004A5E7
0x14004a150  call    Feature_57277348__private_IsEnabledDeviceUsageNoInline
0x14004a155  mov     rcx, [rbx+40h]
0x14004a159  movzx   edx, byte ptr [rcx+1]
0x14004a15d  test    eax, eax
0x14004a15f  jz      short loc_14004A190
0x14004a161  lea     r9d, [rdx+2]
0x14004a165  mov     [rbx+34h], r9d
0x14004a169  cmp     r9d, 5
0x14004a16d  jnb     short loc_14004A196
0x14004a16f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a176  lea     rdi, WPP_GLOBAL_Control
0x14004a17d  cmp     rcx, rdi
0x14004a180  jz      loc_14004A5E2
0x14004a186  mov     edx, 19Bh
0x14004a18b  jmp     loc_14004A5D2
0x14004a190  lea     eax, [rdx+2]
0x14004a193  mov     [rbx+34h], eax
0x14004a196  mov     eax, 2
0x14004a19b  lea     r12, [rbx+48h]
0x14004a19f  mov     r9, r12; struct DOT11_INFO_ELEMENT **
0x14004a1a2  mov     r8b, 37h ; '7'; unsigned __int8
0x14004a1a5  movzx   eax, word ptr [rcx+rax]
0x14004a1a9  mov     [rbx+24h], ax
0x14004a1ad  mov     ecx, [rbx+174h]
0x14004a1b3  mov     edx, [rbx+170h]; unsigned int
0x14004a1b9  add     rcx, rbx; unsigned __int8 *
0x14004a1bc  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x14004a1c1  test    eax, eax
0x14004a1c3  jnz     loc_14004A5B3
0x14004a1c9  mov     r8, [r12]
0x14004a1cd  movzx   eax, byte ptr [r8+1]
0x14004a1d2  cmp     al, 52h ; 'R'
0x14004a1d4  jb      loc_14004A5B3
0x14004a1da  add     eax, 2
0x14004a1dd  mov     [rsp+28h], rsi
0x14004a1e2  mov     [rbx+38h], eax
0x14004a1e5  lea     r9, [rbp+37h+var_A0]
0x14004a1e9  mov     eax, [rbx+174h]
0x14004a1ef  mov     ecx, ebx
0x14004a1f1  sub     ecx, r8d
0x14004a1f4  mov     dword ptr [rbp+37h+arg_38], esi
0x14004a1f7  add     ecx, [rbx+170h]
0x14004a1fd  add     eax, ecx
0x14004a1ff  mov     [rbp+37h+var_A0], esi
0x14004a202  lea     rcx, [rbp+37h+arg_38]
0x14004a206  mov     [rbp+37h+var_9C], eax
0x14004a209  mov     edx, eax
0x14004a20b  mov     [rsp+0D0h+var_B0], rcx
0x14004a210  call    Dot11GetReassembledIE
0x14004a215  lea     rdi, WPP_GLOBAL_Control
0x14004a21c  lea     rsi, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004a223  test    eax, eax
0x14004a225  jnz     loc_14004A3A1
0x14004a22b  mov     r15d, dword ptr [rbp+37h+arg_38]
0x14004a22f  cmp     [rbp+37h+var_A0], r15d
0x14004a233  jz      loc_14004A39D
0x14004a239  lea     eax, [r15+10h]
0x14004a23d  cmp     eax, 10h
0x14004a240  jb      loc_14004A3DD
0x14004a246  cmp     eax, 40h ; '@'
0x14004a249  ja      short loc_14004A254
0x14004a24b  lea     r14, WPP_MAIN_CB.DeviceQueue
0x14004a252  jmp     short loc_14004A282
0x14004a254  cmp     eax, 100h
0x14004a259  ja      short loc_14004A264
0x14004a25b  lea     r14, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004a262  jmp     short loc_14004A282
0x14004a264  cmp     eax, 400h
0x14004a269  ja      short loc_14004A274
0x14004a26b  lea     r14, Lookaside
0x14004a272  jmp     short loc_14004A282
0x14004a274  cmp     eax, 800h
0x14004a279  ja      short loc_14004A293
0x14004a27b  lea     r14, stru_1400B0180
0x14004a282  mov     rcx, r14; Lookaside
0x14004a285  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004a28c  nop     dword ptr [rax+rax+00h]
0x14004a291  jmp     short loc_14004A2AE
0x14004a293  xor     r14d, r14d
0x14004a296  mov     edx, eax
0x14004a298  mov     r8d, 7A697377h
0x14004a29e  lea     ecx, [r14+40h]
0x14004a2a2  call    cs:__imp_ExAllocatePool2
0x14004a2a9  nop     dword ptr [rax+rax+00h]
0x14004a2ae  test    rax, rax
0x14004a2b1  jz      loc_14004A3DD
0x14004a2b7  mov     edx, [rbp+37h+var_9C]
0x14004a2ba  lea     r9, [rbp+37h+var_A0]
0x14004a2be  mov     [rax], r14
0x14004a2c1  lea     r14, [rax+10h]
0x14004a2c5  mov     dword ptr [rax+8], 7A697377h
0x14004a2cc  lea     rax, [rbp+37h+arg_38]
0x14004a2d0  mov     r8, [r12]
0x14004a2d4  mov     [rsp+28h], r14
0x14004a2d9  mov     [rsp+0D0h+var_B0], rax
0x14004a2de  call    Dot11GetReassembledIE
0x14004a2e3  test    eax, eax
0x14004a2e5  jnz     loc_14004A39D
0x14004a2eb  mov     rcx, [rbx+168h]
0x14004a2f2  test    rcx, rcx
0x14004a2f5  jz      short loc_14004A326
0x14004a2f7  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004a2fb  mov     rax, [rcx]
0x14004a2fe  test    rax, rax
0x14004a301  jz      short loc_14004A317
0x14004a303  mov     rdx, rcx; Entry
0x14004a306  mov     rcx, rax; Lookaside
0x14004a309  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004a310  nop     dword ptr [rax+rax+00h]
0x14004a315  jmp     short loc_14004A326
0x14004a317  mov     edx, [rcx+8]; Tag
0x14004a31a  call    cs:__imp_ExFreePoolWithTag
0x14004a321  nop     dword ptr [rax+rax+00h]
0x14004a326  mov     eax, dword ptr [rbp+37h+arg_38]
0x14004a329  mov     [rbx+38h], eax
0x14004a32c  mov     [rbx+168h], r14
0x14004a333  mov     [r12], r14
0x14004a337  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a33e  cmp     rcx, rdi
0x14004a341  jz      short loc_14004A39D
0x14004a343  mov     r9d, [rbp+37h+var_A0]
0x14004a347  mov     edx, 19Eh
0x14004a34c  mov     rcx, [rcx+18h]
0x14004a350  mov     r8, rsi
0x14004a353  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14004a357  call    WPP_SF_Dd
0x14004a35c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a363  cmp     rcx, rdi
0x14004a366  jz      short loc_14004A39D
0x14004a368  movzx   eax, word ptr [rbx+38h]
0x14004a36c  lea     r9, [rbp+37h+var_90]
0x14004a370  mov     rcx, [rcx+18h]
0x14004a374  xorps   xmm0, xmm0
0x14004a377  movups  [rbp+37h+var_90], xmm0
0x14004a37b  mov     word ptr [rbp+37h+var_90], ax
0x14004a37f  mov     edx, 19Fh
0x14004a384  mov     rax, [r12]
0x14004a388  mov     r8, rsi
0x14004a38b  mov     qword ptr [rbp+37h+var_90+8], rax
0x14004a38f  movaps  xmm0, [rbp+37h+var_90]
0x14004a393  movdqa  [rbp+37h+var_90], xmm0
0x14004a398  call    WPP_SF__HEX_
0x14004a39d  mov     r15d, [rbp+37h+arg_0]
0x14004a3a1  mov     r12, [rbp+37h+arg_8]
0x14004a3a5  mov     [rbp+37h+arg_38], 0
0x14004a3ad  test    r12, r12
0x14004a3b0  jz      short loc_14004A41D
0x14004a3b2  test    r13d, r13d
0x14004a3b5  jz      short loc_14004A41D
0x14004a3b7  cmp     r13d, 2
0x14004a3bb  jnb     short loc_14004A412
0x14004a3bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a3c4  cmp     rcx, rdi
0x14004a3c7  jz      loc_14004A5E2
0x14004a3cd  mov     edx, 1A0h
0x14004a3d2  mov     r9d, r13d
0x14004a3d5  mov     r8, rsi
0x14004a3d8  jmp     loc_14004A5D9
0x14004a3dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a3e4  lea     rdi, WPP_GLOBAL_Control
0x14004a3eb  cmp     rcx, rdi
0x14004a3ee  jz      short loc_14004A408
0x14004a3f0  mov     rcx, [rcx+18h]
0x14004a3f4  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004a3fb  mov     edx, 19Dh
0x14004a400  mov     r9d, r15d
0x14004a403  call    WPP_SF_d
0x14004a408  mov     eax, 0C000009Ah
0x14004a40d  jmp     loc_14004A5E7
0x14004a412  mov     r14, r12
0x14004a415  xor     r13d, r13d
0x14004a418  jmp     loc_14004A49D
0x14004a41d  xor     r13d, r13d
0x14004a420  lea     r9, [rbp+37h+arg_38]; struct DOT11_INFO_ELEMENT **
0x14004a424  mov     r8b, 30h ; '0'; unsigned __int8
0x14004a427  test    r15d, r15d
0x14004a42a  jz      short loc_14004A460
0x14004a42c  mov     edx, [rbp+37h+arg_20]; unsigned int
0x14004a42f  mov     rcx, [rbp+37h+arg_18]; unsigned __int8 *
0x14004a433  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x14004a438  mov     r14d, eax
0x14004a43b  test    eax, eax
0x14004a43d  jz      short loc_14004A499
0x14004a43f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a446  cmp     rcx, rdi
0x14004a449  jz      loc_14004A148
0x14004a44f  mov     r9d, [rbp+37h+arg_20]
0x14004a453  mov     edx, 1A1h
0x14004a458  mov     r8, rsi
0x14004a45b  jmp     loc_14004A13F
0x14004a460  mov     ecx, [rbx+174h]
0x14004a466  mov     edx, [rbx+170h]; unsigned int
0x14004a46c  add     rcx, rbx; unsigned __int8 *
0x14004a46f  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x14004a474  mov     r14d, eax
0x14004a477  test    eax, eax
0x14004a479  jz      short loc_14004A499
0x14004a47b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a482  cmp     rcx, rdi
0x14004a485  jz      loc_14004A148
0x14004a48b  mov     r9d, [rbx+170h]
0x14004a492  mov     edx, 1A2h
0x14004a497  jmp     short loc_14004A458
0x14004a499  mov     r14, [rbp+37h+arg_38]
0x14004a49d  xor     edx, edx; Val
0x14004a49f  lea     rcx, [rbp+37h+var_80]; void *
0x14004a4a3  lea     r8d, [rdx+48h]; Size
0x14004a4a7  call    memset
0x14004a4ac  movzx   ecx, byte ptr [r14+1]
0x14004a4b1  lea     eax, [rcx-1]
0x14004a4b4  cmp     al, 0EAh
0x14004a4b6  ja      loc_14004A57D
0x14004a4bc  mov     r15, [rbp+37h+arg_28]
0x14004a4c0  lea     r9, [rbp+37h+var_80]; struct DOT11_RSN_IE_INFO *
0x14004a4c4  mov     edx, ecx; unsigned int
0x14004a4c6  mov     r8, r15; unsigned int *
0x14004a4c9  lea     rcx, [r14+2]; unsigned __int8 *
0x14004a4cd  call    ?IEPRSNParseIE@@YAJPEAEKPEAKPEAUDOT11_RSN_IE_INFO@@@Z; IEPRSNParseIE(uchar *,ulong,ulong *,DOT11_RSN_IE_INFO *)
0x14004a4d2  test    eax, eax
0x14004a4d4  jnz     loc_14004A57D
0x14004a4da  mov     eax, [r15]
0x14004a4dd  test    al, 10h
0x14004a4df  jnz     short loc_14004A4F4
0x14004a4e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a4e8  cmp     rcx, rdi
0x14004a4eb  jz      short loc_14004A55E
0x14004a4ed  mov     edx, 1A4h
0x14004a4f2  jmp     short loc_14004A549
0x14004a4f4  mov     eax, [rbp+37h+var_70]
0x14004a4f7  mov     [rbx+28h], eax
0x14004a4fa  mov     eax, [rbp+37h+var_7C]
0x14004a4fd  mov     [rbx+2Ch], eax
0x14004a500  mov     eax, [rbp+37h+var_3C]
0x14004a503  mov     [rbx+30h], eax
0x14004a506  mov     eax, [r15]
0x14004a509  test    al, 40h
0x14004a50b  jz      short loc_14004A523
0x14004a50d  movzx   eax, [rbp+37h+var_56]
0x14004a511  mov     [rbx+0D8h], ax
0x14004a518  mov     al, [rbp+37h+var_40]
0x14004a51b  add     al, 2
0x14004a51d  mov     [rbx+0DAh], al
0x14004a523  cmp     r14, r12
0x14004a526  jz      short loc_14004A569
0x14004a528  cmp     [rbx+0D8h], r13w
0x14004a530  jnz     short loc_14004A569
0x14004a532  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a539  cmp     rcx, rdi
0x14004a53c  jz      short loc_14004A55E
0x14004a53e  mov     eax, [rbx+170h]
0x14004a544  mov     edx, 1A5h
0x14004a549  movzx   r9d, byte ptr [r14+1]
0x14004a54e  mov     r8, rsi
0x14004a551  mov     rcx, [rcx+18h]
0x14004a555  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14004a559  call    WPP_SF_Dd
0x14004a55e  lea     rcx, [rbp+37h+var_80]; struct DOT11_RSN_IE_INFO *
0x14004a562  call    ?FreeRSNIEContent@@YAXPEAUDOT11_RSN_IE_INFO@@@Z; FreeRSNIEContent(DOT11_RSN_IE_INFO *)
0x14004a567  jmp     short loc_14004A5E2
0x14004a569  mov     rax, [rbp+37h+arg_30]
  ... truncated ...
```
