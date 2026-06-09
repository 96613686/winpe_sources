# CDRollback_GetRsnAndRsnXeIEsAfterAssociation(_NWF_KEY_CONTEXT *,uchar const * const,uchar,ulong,uchar *,ulong,uchar *)

- ea: `0x140040460`
- end: `0x140040a10`
- name: `?CDRollback_GetRsnAndRsnXeIEsAfterAssociation@@YAJPEAU_NWF_KEY_CONTEXT@@QEBEEKPEAEK2@Z`
- size: `1456`
- prototype: `__int64 __fastcall(struct _NWF_KEY_CONTEXT *, const unsigned __int8 *const, unsigned __int8, unsigned int, unsigned __int8 *Src, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140045a90`

## callees

- `0x140020dc0`
- `0x14003ae2c`
- `0x140040460`
- `0x1400537c8`
- `0x140056240`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400405b0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004064b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140040760`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140040856`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400405b0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004064b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140040760`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140040856`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004070a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400407c0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400408cf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004090f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004094f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140040993`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004070a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400407c0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400408cf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004090f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004094f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140040993`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004071b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400408a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400408e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040920`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040960`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400409a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004071b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400408a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400408e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040920`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040960`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400409a4`

## pseudocode

```c
__int64 __fastcall CDRollback_GetRsnAndRsnXeIEsAfterAssociation(
        struct _NWF_KEY_CONTEXT *a1,
        const unsigned __int8 *a2,
        unsigned __int8 a3,
        int a4,
        unsigned __int8 *Src,
        unsigned int a6,
        unsigned __int8 *a7)
{
  unsigned __int8 *v7; // r15
  int v9; // esi
  __int64 v12; // rcx
  unsigned int v13; // edi
  const unsigned __int8 *v14; // r12
  __int64 v15; // rcx
  unsigned int v16; // r14d
  int v17; // edx
  unsigned int Dot11InfoElement; // edi
  int v19; // r8d
  unsigned __int8 *v21; // r15
  unsigned int v22; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rsi
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  _DWORD *v25; // rax
  void *v26; // rcx
  unsigned int v27; // eax
  unsigned __int8 *v28; // r14
  unsigned int v29; // eax
  struct _NPAGED_LOOKASIDE_LIST *v30; // rdi
  _DWORD *v31; // rax
  void *v32; // rcx
  unsigned int v33; // eax
  unsigned int v34; // edi
  unsigned __int8 *v35; // r12
  unsigned int v36; // r15d
  unsigned __int8 *v37; // r14
  unsigned int v38; // eax
  struct _NPAGED_LOOKASIDE_LIST *v39; // rdi
  unsigned __int8 *pAssocRequestRsnIE; // rcx
  unsigned __int8 *v41; // rcx
  _DWORD *v42; // rax
  unsigned __int8 *v43; // rcx
  unsigned __int8 *v44; // rcx
  void *v45; // rcx
  unsigned int v46; // eax
  unsigned __int8 *v47; // r14
  unsigned int v48; // eax
  char *v49; // rax
  unsigned __int8 *pAssocRequestRsnXeIE; // rcx
  unsigned __int8 *v51; // rcx
  unsigned __int8 *pBeaconRsnIE; // rcx
  unsigned __int8 *v53; // rcx
  unsigned __int8 *pBeaconRsnXeIE; // rcx
  unsigned __int8 *v55; // rcx
  DOT11_CONNECTION_INFO *pConnectionInfo; // rcx
  ULONG *p_Rssi; // rcx
  size_t v58; // r8

  v7 = Src;
  v9 = a3;
  a1->assocRequestRsnIELength = 0;
  a1->pAssocRequestRsnIE = 0;
  a1->pAssocRequestRsnXeIE = 0;
  a1->assocRequestRsnXeIELength = 0;
  a1->pBeaconRsnIE = 0;
  a1->beaconRsnIELength = 0;
  a1->pBeaconRsnXeIE = 0;
  a1->beaconRsnXeIELength = 0;
  Src = 0;
  v12 = a3 != 0 ? 10 : 4;
  v13 = a4 - v12;
  v14 = &v7[v12];
  if ( (unsigned int)GetDot11InfoElement(&v7[v12], a4 - (int)v12, 0x30u, (struct DOT11_INFO_ELEMENT **)&Src) )
  {
    v15 = (_BYTE)v9 != 0 ? 4 : 10;
    v16 = a4 - v15;
    v14 = &v7[v15];
    Dot11InfoElement = GetDot11InfoElement(&v7[v15], v16, 0x30u, (struct DOT11_INFO_ELEMENT **)&Src);
    if ( Dot11InfoElement )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 361, WPP_e90d411d816e312466897e39e745b158_Traceguids, a2);
      return Dot11InfoElement;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_l_MAC_(WPP_GLOBAL_Control->AttachedDevice, v17, v19, v9, (__int64)a2);
  }
  else
  {
    v16 = v13;
  }
  v21 = Src;
  v22 = Src[1] + 18;
  a1->pAssocRequestRsnIE = 0;
  if ( v22 < 0x10 )
    return 3221225626LL;
  p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  if ( v22 > 0x40 )
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    if ( v22 > 0x100 )
      p_WaitListHead = &Lookaside;
  }
  else
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  }
  v25 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
  if ( !v25 )
    return 3221225626LL;
  *(_QWORD *)v25 = p_WaitListHead;
  v26 = v25 + 4;
  v25[2] = 2053731191;
  a1->pAssocRequestRsnIE = (unsigned __int8 *)(v25 + 4);
  v27 = v21[1] + 2;
  a1->assocRequestRsnIELength = v27;
  memmove(v26, v21, v27);
  if ( (unsigned int)GetDot11InfoElement(v14, v16, 0xF4u, (struct DOT11_INFO_ELEMENT **)&Src) )
    goto LABEL_23;
  v28 = Src;
  v29 = Src[1] + 18;
  a1->pAssocRequestRsnXeIE = 0;
  if ( v29 < 0x10 )
    goto LABEL_28;
  if ( v29 > 0x40 )
  {
    v30 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    if ( v29 > 0x100 )
      v30 = &Lookaside;
  }
  else
  {
    v30 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  }
  v31 = ExAllocateFromNPagedLookasideList(v30);
  if ( !v31 )
  {
LABEL_28:
    pAssocRequestRsnIE = a1->pAssocRequestRsnIE;
    if ( pAssocRequestRsnIE )
    {
      v41 = pAssocRequestRsnIE - 16;
      if ( *(_QWORD *)v41 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v41, v41);
      else
        ExFreePoolWithTag(v41, *((_DWORD *)v41 + 2));
      a1->pAssocRequestRsnIE = 0;
    }
    a1->assocRequestRsnIELength = 0;
    return 3221225626LL;
  }
  *(_QWORD *)v31 = v30;
  v32 = v31 + 4;
  v31[2] = 2053731191;
  a1->pAssocRequestRsnXeIE = (unsigned __int8 *)(v31 + 4);
  v33 = v28[1] + 2;
  a1->assocRequestRsnXeIELength = v33;
  memmove(v32, v28, v33);
LABEL_23:
  v34 = a6;
  if ( a6 >= 0xC )
  {
    v35 = a7;
    v36 = a6 - 12;
    if ( !(unsigned int)GetDot11InfoElement(a7 + 12, a6 - 12, 0x30u, (struct DOT11_INFO_ELEMENT **)&Src) )
    {
      v37 = Src;
      v38 = Src[1] + 18;
      a1->pBeaconRsnIE = 0;
      if ( v38 < 0x10 )
        goto LABEL_38;
      if ( v38 > 0x40 )
      {
        v39 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
        if ( v38 > 0x100 )
          v39 = &Lookaside;
      }
      else
      {
        v39 = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
      }
      v42 = ExAllocateFromNPagedLookasideList(v39);
      if ( !v42 )
      {
LABEL_38:
        Dot11InfoElement = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 365, WPP_e90d411d816e312466897e39e745b158_Traceguids, a2);
LABEL_40:
        v43 = a1->pAssocRequestRsnIE;
        if ( v43 )
        {
          v44 = v43 - 16;
          if ( *(_QWORD *)v44 )
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v44, v44);
          else
            ExFreePoolWithTag(v44, *((_DWORD *)v44 + 2));
          a1->pAssocRequestRsnIE = 0;
        }
        pAssocRequestRsnXeIE = a1->pAssocRequestRsnXeIE;
        a1->assocRequestRsnIELength = 0;
        if ( pAssocRequestRsnXeIE )
        {
          v51 = pAssocRequestRsnXeIE - 16;
          if ( *(_QWORD *)v51 )
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v51, v51);
          else
            ExFreePoolWithTag(v51, *((_DWORD *)v51 + 2));
          a1->pAssocRequestRsnXeIE = 0;
          a1->assocRequestRsnXeIELength = 0;
        }
        pBeaconRsnIE = a1->pBeaconRsnIE;
        if ( pBeaconRsnIE )
        {
          v53 = pBeaconRsnIE - 16;
          if ( *(_QWORD *)v53 )
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v53, v53);
          else
            ExFreePoolWithTag(v53, *((_DWORD *)v53 + 2));
          a1->pBeaconRsnIE = 0;
          a1->beaconRsnIELength = 0;
        }
        pBeaconRsnXeIE = a1->pBeaconRsnXeIE;
        if ( pBeaconRsnXeIE )
        {
          v55 = pBeaconRsnXeIE - 16;
          if ( *(_QWORD *)v55 )
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v55, v55);
          else
            ExFreePoolWithTag(v55, *((_DWORD *)v55 + 2));
          a1->pBeaconRsnXeIE = 0;
          a1->beaconRsnXeIELength = 0;
        }
        pConnectionInfo = a1->pConnectionInfo;
        if ( pConnectionInfo )
        {
          p_Rssi = (ULONG *)&pConnectionInfo[-1].LinkInfo[0].Rssi;
          if ( *(_QWORD *)p_Rssi )
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_Rssi, p_Rssi);
          else
            ExFreePoolWithTag(p_Rssi, p_Rssi[2]);
          a1->pConnectionInfo = 0;
        }
        return Dot11InfoElement;
      }
      *(_QWORD *)v42 = v39;
      v45 = v42 + 4;
      v42[2] = 2053731191;
      a1->pBeaconRsnIE = (unsigned __int8 *)(v42 + 4);
      Dot11InfoElement = 0;
      v46 = v37[1] + 2;
      a1->beaconRsnIELength = v46;
      memmove(v45, v37, v46);
      if ( !(unsigned int)GetDot11InfoElement(v35 + 12, v36, 0xF4u, (struct DOT11_INFO_ELEMENT **)&Src) )
      {
        v47 = Src;
        v48 = Src[1] + 18;
        a1->pBeaconRsnXeIE = 0;
        if ( v48 < 0x10 )
          goto LABEL_49;
        if ( v48 > 0x40 )
        {
          p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
          if ( v48 > 0x100 )
            p_DeviceQueue = &Lookaside;
        }
        v49 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
        if ( !v49 )
        {
LABEL_49:
          Dot11InfoElement = -1073741670;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 364, WPP_e90d411d816e312466897e39e745b158_Traceguids, a2);
          goto LABEL_40;
        }
        *(_QWORD *)v49 = p_DeviceQueue;
        *((_DWORD *)v49 + 2) = 2053731191;
        a1->pBeaconRsnXeIE = (unsigned __int8 *)(v49 + 16);
        v58 = (unsigned int)v47[1] + 2;
        a1->beaconRsnXeIELength = v58;
        memmove(v49 + 16, v47, v58);
      }
      return Dot11InfoElement;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 363, WPP_e90d411d816e312466897e39e745b158_Traceguids, v34);
  return 0;
}

```

## disassembly

```asm
0x140040460  mov     r11, rsp
0x140040463  push    rbx
0x140040464  push    rbp
0x140040465  push    rsi
0x140040466  push    rdi
0x140040467  push    r12
0x140040469  push    r13
0x14004046b  push    r14
0x14004046d  push    r15
0x14004046f  sub     rsp, 38h
0x140040473  mov     r15, [rsp+78h+Src]
0x14004047b  mov     rbx, rcx
0x14004047e  movzx   esi, r8b
0x140040482  mov     r13, rdx
0x140040485  xor     edx, edx
0x140040487  mov     edi, r9d
0x14004048a  mov     [rcx+40h], edx
0x14004048d  mov     al, sil
0x140040490  mov     [rcx+38h], rdx
0x140040494  neg     al
0x140040496  mov     [rcx+48h], rdx
0x14004049a  mov     r14d, r9d
0x14004049d  mov     [rcx+50h], edx
0x1400404a0  lea     r9, [r11+28h]; struct DOT11_INFO_ELEMENT **
0x1400404a4  mov     [rcx+60h], rdx
0x1400404a8  mov     r8b, 30h ; '0'; unsigned __int8
0x1400404ab  mov     [rcx+68h], edx
0x1400404ae  mov     [rcx+70h], rdx
0x1400404b2  mov     [rcx+78h], edx
0x1400404b5  sbb     ecx, ecx
0x1400404b7  and     ecx, 6
0x1400404ba  mov     [r11+28h], rdx
0x1400404be  add     ecx, 4
0x1400404c1  sub     edi, ecx
0x1400404c3  mov     edx, edi; unsigned int
0x1400404c5  lea     r12, [rcx+r15]
0x1400404c9  mov     rcx, r12; unsigned __int8 *
0x1400404cc  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x1400404d1  lea     rbp, WPP_GLOBAL_Control
0x1400404d8  test    eax, eax
0x1400404da  jz      loc_140040561
0x1400404e0  mov     al, sil
0x1400404e3  lea     r9, [rsp+78h+Src]; struct DOT11_INFO_ELEMENT **
0x1400404eb  neg     al
0x1400404ed  mov     r8b, 30h ; '0'; unsigned __int8
0x1400404f0  sbb     ecx, ecx
0x1400404f2  and     ecx, 0FFFFFFFAh
0x1400404f5  add     ecx, 0Ah
0x1400404f8  sub     r14d, ecx
0x1400404fb  mov     edx, r14d; unsigned int
0x1400404fe  lea     r12, [rcx+r15]
0x140040502  mov     rcx, r12; unsigned __int8 *
0x140040505  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x14004050a  mov     edi, eax
0x14004050c  test    eax, eax
0x14004050e  jz      short loc_140040542
0x140040510  mov     rcx, cs:WPP_GLOBAL_Control
0x140040517  lea     rbp, WPP_GLOBAL_Control
0x14004051e  cmp     rcx, rbp
0x140040521  jz      short loc_14004053B
0x140040523  mov     rcx, [rcx+18h]
0x140040527  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004052e  mov     edx, 169h
0x140040533  mov     r9, r13
0x140040536  call    WPP_SF__MAC_
0x14004053b  mov     eax, edi
0x14004053d  jmp     loc_140040734
0x140040542  mov     rcx, cs:WPP_GLOBAL_Control
0x140040549  cmp     rcx, rbp
0x14004054c  jz      short loc_140040564
0x14004054e  mov     rcx, [rcx+18h]
0x140040552  mov     r9d, esi
0x140040555  mov     [rsp+78h+var_58], r13
0x14004055a  call    WPP_SF_l_MAC_
0x14004055f  jmp     short loc_140040564
0x140040561  mov     r14d, edi
0x140040564  mov     r15, [rsp+78h+Src]
0x14004056c  movzx   eax, byte ptr [r15+1]
0x140040571  add     eax, 12h
0x140040574  mov     qword ptr [rbx+38h], 0
0x14004057c  cmp     eax, 10h
0x14004057f  jb      loc_14004072F
0x140040585  lea     rcx, Lookaside
0x14004058c  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x140040593  cmp     eax, 40h ; '@'
0x140040596  ja      short loc_14004059D
0x140040598  mov     rdi, rsi
0x14004059b  jmp     short loc_1400405AD
0x14004059d  cmp     eax, 100h
0x1400405a2  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400405a9  cmova   rdi, rcx
0x1400405ad  mov     rcx, rdi; Lookaside
0x1400405b0  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400405b7  nop     dword ptr [rax+rax+00h]
0x1400405bc  test    rax, rax
0x1400405bf  jz      loc_14004072F
0x1400405c5  mov     [rax], rdi
0x1400405c8  lea     rcx, [rax+10h]; void *
0x1400405cc  mov     dword ptr [rax+8], 7A697377h
0x1400405d3  mov     rdx, r15; Src
0x1400405d6  mov     [rbx+38h], rcx
0x1400405da  movzx   eax, byte ptr [r15+1]
0x1400405df  add     eax, 2
0x1400405e2  mov     r8d, eax; Size
0x1400405e5  mov     [rbx+40h], eax
0x1400405e8  call    memmove
0x1400405ed  lea     r9, [rsp+78h+Src]; struct DOT11_INFO_ELEMENT **
0x1400405f5  mov     r8b, 0F4h; unsigned __int8
0x1400405f8  mov     edx, r14d; unsigned int
0x1400405fb  mov     rcx, r12; unsigned __int8 *
0x1400405fe  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x140040603  xor     r15d, r15d
0x140040606  test    eax, eax
0x140040608  jnz     short loc_140040688
0x14004060a  mov     r14, [rsp+78h+Src]
0x140040612  movzx   eax, byte ptr [r14+1]
0x140040617  add     eax, 12h
0x14004061a  mov     [rbx+48h], r15
0x14004061e  cmp     eax, 10h
0x140040621  jb      loc_1400406EF
0x140040627  cmp     eax, 40h ; '@'
0x14004062a  ja      short loc_140040631
0x14004062c  mov     rdi, rsi
0x14004062f  jmp     short loc_140040648
0x140040631  cmp     eax, 100h
0x140040636  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004063d  lea     rax, Lookaside
0x140040644  cmova   rdi, rax
0x140040648  mov     rcx, rdi; Lookaside
0x14004064b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140040652  nop     dword ptr [rax+rax+00h]
0x140040657  test    rax, rax
0x14004065a  jz      loc_1400406EF
0x140040660  mov     [rax], rdi
0x140040663  lea     rcx, [rax+10h]; void *
0x140040667  mov     dword ptr [rax+8], 7A697377h
0x14004066e  mov     rdx, r14; Src
0x140040671  mov     [rbx+48h], rcx
0x140040675  movzx   eax, byte ptr [r14+1]
0x14004067a  add     eax, 2
0x14004067d  mov     r8d, eax; Size
0x140040680  mov     [rbx+50h], eax
0x140040683  call    memmove
0x140040688  mov     edi, [rsp+78h+arg_28]
0x14004068f  cmp     edi, 0Ch
0x140040692  jb      loc_1400409E5
0x140040698  mov     r12, [rsp+78h+arg_30]
0x1400406a0  lea     r15d, [rdi-0Ch]
0x1400406a4  lea     r9, [rsp+78h+Src]; struct DOT11_INFO_ELEMENT **
0x1400406ac  mov     r8b, 30h ; '0'; unsigned __int8
0x1400406af  mov     edx, r15d; unsigned int
0x1400406b2  lea     rcx, [r12+0Ch]; unsigned __int8 *
0x1400406b7  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x1400406bc  test    eax, eax
0x1400406be  jnz     loc_1400409E5
0x1400406c4  mov     r14, [rsp+78h+Src]
0x1400406cc  movzx   eax, byte ptr [r14+1]
0x1400406d1  add     eax, 12h
0x1400406d4  mov     qword ptr [rbx+60h], 0
0x1400406dc  cmp     eax, 10h
0x1400406df  jb      loc_140040771
0x1400406e5  cmp     eax, 40h ; '@'
0x1400406e8  ja      short loc_140040746
0x1400406ea  mov     rdi, rsi
0x1400406ed  jmp     short loc_14004075D
0x1400406ef  mov     rcx, [rbx+38h]
0x1400406f3  test    rcx, rcx
0x1400406f6  jz      short loc_14004072B
0x1400406f8  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400406fc  mov     rax, [rcx]
0x1400406ff  test    rax, rax
0x140040702  jz      short loc_140040718
0x140040704  mov     rdx, rcx; Entry
0x140040707  mov     rcx, rax; Lookaside
0x14004070a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140040711  nop     dword ptr [rax+rax+00h]
0x140040716  jmp     short loc_140040727
0x140040718  mov     edx, [rcx+8]; Tag
0x14004071b  call    cs:__imp_ExFreePoolWithTag
0x140040722  nop     dword ptr [rax+rax+00h]
0x140040727  mov     [rbx+38h], r15
0x14004072b  mov     [rbx+40h], r15d
0x14004072f  mov     eax, 0C000009Ah
0x140040734  add     rsp, 38h
0x140040738  pop     r15
0x14004073a  pop     r14
0x14004073c  pop     r13
0x14004073e  pop     r12
0x140040740  pop     rdi
0x140040741  pop     rsi
0x140040742  pop     rbp
0x140040743  pop     rbx
0x140040744  retn
0x140040746  cmp     eax, 100h
0x14004074b  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140040752  lea     rax, Lookaside
0x140040759  cmova   rdi, rax
0x14004075d  mov     rcx, rdi; Lookaside
0x140040760  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140040767  nop     dword ptr [rax+rax+00h]
0x14004076c  test    rax, rax
0x14004076f  jnz     short loc_1400407D1
0x140040771  mov     edi, 0C000009Ah
0x140040776  mov     rcx, cs:WPP_GLOBAL_Control
0x14004077d  cmp     rcx, rbp
0x140040780  jz      short loc_14004079A
0x140040782  mov     rcx, [rcx+18h]
0x140040786  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004078d  mov     edx, 16Dh
0x140040792  mov     r9, r13
0x140040795  call    WPP_SF__MAC_
0x14004079a  xor     r15d, r15d
0x14004079d  mov     rcx, [rbx+38h]
0x1400407a1  test    rcx, rcx
0x1400407a4  jz      loc_1400408B0
0x1400407aa  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400407ae  mov     rax, [rcx]
0x1400407b1  test    rax, rax
0x1400407b4  jz      loc_14004089D
0x1400407ba  mov     rdx, rcx; Entry
0x1400407bd  mov     rcx, rax; Lookaside
0x1400407c0  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400407c7  nop     dword ptr [rax+rax+00h]
0x1400407cc  jmp     loc_1400408AC
0x1400407d1  mov     [rax], rdi
0x1400407d4  lea     rcx, [rax+10h]; void *
0x1400407d8  mov     dword ptr [rax+8], 7A697377h
0x1400407df  mov     rdx, r14; Src
0x1400407e2  mov     [rbx+60h], rcx
0x1400407e6  xor     edi, edi
0x1400407e8  movzx   eax, byte ptr [r14+1]
0x1400407ed  add     eax, 2
0x1400407f0  mov     r8d, eax; Size
0x1400407f3  mov     [rbx+68h], eax
0x1400407f6  call    memmove
0x1400407fb  lea     r9, [rsp+78h+Src]; struct DOT11_INFO_ELEMENT **
0x140040803  mov     r8b, 0F4h; unsigned __int8
0x140040806  mov     edx, r15d; unsigned int
0x140040809  lea     rcx, [r12+0Ch]; unsigned __int8 *
0x14004080e  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x140040813  xor     r15d, r15d
0x140040816  test    eax, eax
0x140040818  jnz     loc_14004053B
0x14004081e  mov     r14, [rsp+78h+Src]
0x140040826  movzx   eax, byte ptr [r14+1]
0x14004082b  add     eax, 12h
0x14004082e  mov     [rbx+70h], r15
0x140040832  cmp     eax, 10h
0x140040835  jb      short loc_14004086B
0x140040837  cmp     eax, 40h ; '@'
0x14004083a  jbe     short loc_140040853
0x14004083c  cmp     eax, 100h
0x140040841  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140040848  lea     rax, Lookaside
0x14004084f  cmova   rsi, rax
0x140040853  mov     rcx, rsi; Lookaside
0x140040856  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004085d  nop     dword ptr [rax+rax+00h]
0x140040862  test    rax, rax
0x140040865  jnz     loc_1400409B9
0x14004086b  mov     edi, 0C000009Ah
0x140040870  mov     rcx, cs:WPP_GLOBAL_Control
0x140040877  cmp     rcx, rbp
0x14004087a  jz      loc_14004079D
0x140040880  mov     rcx, [rcx+18h]
0x140040884  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004088b  mov     edx, 16Ch
0x140040890  mov     r9, r13
0x140040893  call    WPP_SF__MAC_
0x140040898  jmp     loc_14004079D
0x14004089d  mov     edx, [rcx+8]; Tag
0x1400408a0  call    cs:__imp_ExFreePoolWithTag
0x1400408a7  nop     dword ptr [rax+rax+00h]
0x1400408ac  mov     [rbx+38h], r15
0x1400408b0  mov     rcx, [rbx+48h]
0x1400408b4  mov     [rbx+40h], r15d
0x1400408b8  test    rcx, rcx
0x1400408bb  jz      short loc_1400408F4
0x1400408bd  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400408c1  mov     rax, [rcx]
0x1400408c4  test    rax, rax
0x1400408c7  jz      short loc_1400408DD
0x1400408c9  mov     rdx, rcx; Entry
0x1400408cc  mov     rcx, rax; Lookaside
0x1400408cf  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400408d6  nop     dword ptr [rax+rax+00h]
0x1400408db  jmp     short loc_1400408EC
0x1400408dd  mov     edx, [rcx+8]; Tag
0x1400408e0  call    cs:__imp_ExFreePoolWithTag
0x1400408e7  nop     dword ptr [rax+rax+00h]
0x1400408ec  mov     [rbx+48h], r15
0x1400408f0  mov     [rbx+50h], r15d
0x1400408f4  mov     rcx, [rbx+60h]
0x1400408f8  test    rcx, rcx
0x1400408fb  jz      short loc_140040934
0x1400408fd  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140040901  mov     rax, [rcx]
0x140040904  test    rax, rax
0x140040907  jz      short loc_14004091D
0x140040909  mov     rdx, rcx; Entry
  ... truncated ...
```
