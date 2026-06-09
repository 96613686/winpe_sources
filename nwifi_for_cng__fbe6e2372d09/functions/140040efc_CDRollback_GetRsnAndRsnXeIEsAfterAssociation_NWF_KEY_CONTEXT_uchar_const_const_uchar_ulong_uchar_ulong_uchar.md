# CDRollback_GetRsnAndRsnXeIEsAfterAssociation(_NWF_KEY_CONTEXT *,uchar const * const,uchar,ulong,uchar *,ulong,uchar *)

- ea: `0x140040efc`
- end: `0x1400414ac`
- name: `?CDRollback_GetRsnAndRsnXeIEsAfterAssociation@@YAJPEAU_NWF_KEY_CONTEXT@@QEBEEKPEAEK2@Z`
- size: `1456`
- prototype: `__int64 __fastcall(struct _NWF_KEY_CONTEXT *, const unsigned __int8 *, unsigned __int8, int, unsigned __int8 *Src, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140046610`

## callees

- `0x140020dc0`
- `0x14003b04c`
- `0x140040efc`
- `0x140054fe8`
- `0x140057a60`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004104c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400410e7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400411fc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400412f2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004104c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400410e7`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400411fc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400412f2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400411a6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004125c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004136b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400413ab`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400413eb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004142f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400411a6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004125c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004136b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400413ab`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400413eb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004142f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400411b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004133c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004137c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400413bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400413fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041440`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400411b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004133c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004137c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400413bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400413fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041440`

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
        WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 361, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, a2);
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
          WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 365, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, a2);
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
            WPP_SF__MAC_(WPP_GLOBAL_Control->AttachedDevice, 364, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, a2);
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 363, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v34);
  return 0;
}

```

## disassembly

```asm
0x140040efc  mov     r11, rsp
0x140040eff  push    rbx
0x140040f00  push    rbp
0x140040f01  push    rsi
0x140040f02  push    rdi
0x140040f03  push    r12
0x140040f05  push    r13
0x140040f07  push    r14
0x140040f09  push    r15
0x140040f0b  sub     rsp, 38h
0x140040f0f  mov     r15, [rsp+78h+Src]
0x140040f17  mov     rbx, rcx
0x140040f1a  movzx   esi, r8b
0x140040f1e  mov     r13, rdx
0x140040f21  xor     edx, edx
0x140040f23  mov     edi, r9d
0x140040f26  mov     [rcx+40h], edx
0x140040f29  mov     al, sil
0x140040f2c  mov     [rcx+38h], rdx
0x140040f30  neg     al
0x140040f32  mov     [rcx+48h], rdx
0x140040f36  mov     r14d, r9d
0x140040f39  mov     [rcx+50h], edx
0x140040f3c  lea     r9, [r11+28h]; struct DOT11_INFO_ELEMENT **
0x140040f40  mov     [rcx+60h], rdx
0x140040f44  mov     r8b, 30h ; '0'; unsigned __int8
0x140040f47  mov     [rcx+68h], edx
0x140040f4a  mov     [rcx+70h], rdx
0x140040f4e  mov     [rcx+78h], edx
0x140040f51  sbb     ecx, ecx
0x140040f53  and     ecx, 6
0x140040f56  mov     [r11+28h], rdx
0x140040f5a  add     ecx, 4
0x140040f5d  sub     edi, ecx
0x140040f5f  mov     edx, edi; unsigned int
0x140040f61  lea     r12, [rcx+r15]
0x140040f65  mov     rcx, r12; unsigned __int8 *
0x140040f68  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x140040f6d  lea     rbp, WPP_GLOBAL_Control
0x140040f74  test    eax, eax
0x140040f76  jz      loc_140040FFD
0x140040f7c  mov     al, sil
0x140040f7f  lea     r9, [rsp+78h+Src]; struct DOT11_INFO_ELEMENT **
0x140040f87  neg     al
0x140040f89  mov     r8b, 30h ; '0'; unsigned __int8
0x140040f8c  sbb     ecx, ecx
0x140040f8e  and     ecx, 0FFFFFFFAh
0x140040f91  add     ecx, 0Ah
0x140040f94  sub     r14d, ecx
0x140040f97  mov     edx, r14d; unsigned int
0x140040f9a  lea     r12, [rcx+r15]
0x140040f9e  mov     rcx, r12; unsigned __int8 *
0x140040fa1  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x140040fa6  mov     edi, eax
0x140040fa8  test    eax, eax
0x140040faa  jz      short loc_140040FDE
0x140040fac  mov     rcx, cs:WPP_GLOBAL_Control
0x140040fb3  lea     rbp, WPP_GLOBAL_Control
0x140040fba  cmp     rcx, rbp
0x140040fbd  jz      short loc_140040FD7
0x140040fbf  mov     rcx, [rcx+18h]
0x140040fc3  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140040fca  mov     edx, 169h
0x140040fcf  mov     r9, r13
0x140040fd2  call    WPP_SF__MAC_
0x140040fd7  mov     eax, edi
0x140040fd9  jmp     loc_1400411D0
0x140040fde  mov     rcx, cs:WPP_GLOBAL_Control
0x140040fe5  cmp     rcx, rbp
0x140040fe8  jz      short loc_140041000
0x140040fea  mov     rcx, [rcx+18h]
0x140040fee  mov     r9d, esi
0x140040ff1  mov     [rsp+78h+var_58], r13
0x140040ff6  call    WPP_SF_l_MAC_
0x140040ffb  jmp     short loc_140041000
0x140040ffd  mov     r14d, edi
0x140041000  mov     r15, [rsp+78h+Src]
0x140041008  movzx   eax, byte ptr [r15+1]
0x14004100d  add     eax, 12h
0x140041010  mov     qword ptr [rbx+38h], 0
0x140041018  cmp     eax, 10h
0x14004101b  jb      loc_1400411CB
0x140041021  lea     rcx, Lookaside
0x140041028  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x14004102f  cmp     eax, 40h ; '@'
0x140041032  ja      short loc_140041039
0x140041034  mov     rdi, rsi
0x140041037  jmp     short loc_140041049
0x140041039  cmp     eax, 100h
0x14004103e  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140041045  cmova   rdi, rcx
0x140041049  mov     rcx, rdi; Lookaside
0x14004104c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140041053  nop     dword ptr [rax+rax+00h]
0x140041058  test    rax, rax
0x14004105b  jz      loc_1400411CB
0x140041061  mov     [rax], rdi
0x140041064  lea     rcx, [rax+10h]; void *
0x140041068  mov     dword ptr [rax+8], 7A697377h
0x14004106f  mov     rdx, r15; Src
0x140041072  mov     [rbx+38h], rcx
0x140041076  movzx   eax, byte ptr [r15+1]
0x14004107b  add     eax, 2
0x14004107e  mov     r8d, eax; Size
0x140041081  mov     [rbx+40h], eax
0x140041084  call    memmove
0x140041089  lea     r9, [rsp+78h+Src]; struct DOT11_INFO_ELEMENT **
0x140041091  mov     r8b, 0F4h; unsigned __int8
0x140041094  mov     edx, r14d; unsigned int
0x140041097  mov     rcx, r12; unsigned __int8 *
0x14004109a  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x14004109f  xor     r15d, r15d
0x1400410a2  test    eax, eax
0x1400410a4  jnz     short loc_140041124
0x1400410a6  mov     r14, [rsp+78h+Src]
0x1400410ae  movzx   eax, byte ptr [r14+1]
0x1400410b3  add     eax, 12h
0x1400410b6  mov     [rbx+48h], r15
0x1400410ba  cmp     eax, 10h
0x1400410bd  jb      loc_14004118B
0x1400410c3  cmp     eax, 40h ; '@'
0x1400410c6  ja      short loc_1400410CD
0x1400410c8  mov     rdi, rsi
0x1400410cb  jmp     short loc_1400410E4
0x1400410cd  cmp     eax, 100h
0x1400410d2  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400410d9  lea     rax, Lookaside
0x1400410e0  cmova   rdi, rax
0x1400410e4  mov     rcx, rdi; Lookaside
0x1400410e7  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400410ee  nop     dword ptr [rax+rax+00h]
0x1400410f3  test    rax, rax
0x1400410f6  jz      loc_14004118B
0x1400410fc  mov     [rax], rdi
0x1400410ff  lea     rcx, [rax+10h]; void *
0x140041103  mov     dword ptr [rax+8], 7A697377h
0x14004110a  mov     rdx, r14; Src
0x14004110d  mov     [rbx+48h], rcx
0x140041111  movzx   eax, byte ptr [r14+1]
0x140041116  add     eax, 2
0x140041119  mov     r8d, eax; Size
0x14004111c  mov     [rbx+50h], eax
0x14004111f  call    memmove
0x140041124  mov     edi, [rsp+78h+arg_28]
0x14004112b  cmp     edi, 0Ch
0x14004112e  jb      loc_140041481
0x140041134  mov     r12, [rsp+78h+arg_30]
0x14004113c  lea     r15d, [rdi-0Ch]
0x140041140  lea     r9, [rsp+78h+Src]; struct DOT11_INFO_ELEMENT **
0x140041148  mov     r8b, 30h ; '0'; unsigned __int8
0x14004114b  mov     edx, r15d; unsigned int
0x14004114e  lea     rcx, [r12+0Ch]; unsigned __int8 *
0x140041153  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x140041158  test    eax, eax
0x14004115a  jnz     loc_140041481
0x140041160  mov     r14, [rsp+78h+Src]
0x140041168  movzx   eax, byte ptr [r14+1]
0x14004116d  add     eax, 12h
0x140041170  mov     qword ptr [rbx+60h], 0
0x140041178  cmp     eax, 10h
0x14004117b  jb      loc_14004120D
0x140041181  cmp     eax, 40h ; '@'
0x140041184  ja      short loc_1400411E2
0x140041186  mov     rdi, rsi
0x140041189  jmp     short loc_1400411F9
0x14004118b  mov     rcx, [rbx+38h]
0x14004118f  test    rcx, rcx
0x140041192  jz      short loc_1400411C7
0x140041194  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140041198  mov     rax, [rcx]
0x14004119b  test    rax, rax
0x14004119e  jz      short loc_1400411B4
0x1400411a0  mov     rdx, rcx; Entry
0x1400411a3  mov     rcx, rax; Lookaside
0x1400411a6  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400411ad  nop     dword ptr [rax+rax+00h]
0x1400411b2  jmp     short loc_1400411C3
0x1400411b4  mov     edx, [rcx+8]; Tag
0x1400411b7  call    cs:__imp_ExFreePoolWithTag
0x1400411be  nop     dword ptr [rax+rax+00h]
0x1400411c3  mov     [rbx+38h], r15
0x1400411c7  mov     [rbx+40h], r15d
0x1400411cb  mov     eax, 0C000009Ah
0x1400411d0  add     rsp, 38h
0x1400411d4  pop     r15
0x1400411d6  pop     r14
0x1400411d8  pop     r13
0x1400411da  pop     r12
0x1400411dc  pop     rdi
0x1400411dd  pop     rsi
0x1400411de  pop     rbp
0x1400411df  pop     rbx
0x1400411e0  retn
0x1400411e2  cmp     eax, 100h
0x1400411e7  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400411ee  lea     rax, Lookaside
0x1400411f5  cmova   rdi, rax
0x1400411f9  mov     rcx, rdi; Lookaside
0x1400411fc  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140041203  nop     dword ptr [rax+rax+00h]
0x140041208  test    rax, rax
0x14004120b  jnz     short loc_14004126D
0x14004120d  mov     edi, 0C000009Ah
0x140041212  mov     rcx, cs:WPP_GLOBAL_Control
0x140041219  cmp     rcx, rbp
0x14004121c  jz      short loc_140041236
0x14004121e  mov     rcx, [rcx+18h]
0x140041222  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140041229  mov     edx, 16Dh
0x14004122e  mov     r9, r13
0x140041231  call    WPP_SF__MAC_
0x140041236  xor     r15d, r15d
0x140041239  mov     rcx, [rbx+38h]
0x14004123d  test    rcx, rcx
0x140041240  jz      loc_14004134C
0x140041246  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004124a  mov     rax, [rcx]
0x14004124d  test    rax, rax
0x140041250  jz      loc_140041339
0x140041256  mov     rdx, rcx; Entry
0x140041259  mov     rcx, rax; Lookaside
0x14004125c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041263  nop     dword ptr [rax+rax+00h]
0x140041268  jmp     loc_140041348
0x14004126d  mov     [rax], rdi
0x140041270  lea     rcx, [rax+10h]; void *
0x140041274  mov     dword ptr [rax+8], 7A697377h
0x14004127b  mov     rdx, r14; Src
0x14004127e  mov     [rbx+60h], rcx
0x140041282  xor     edi, edi
0x140041284  movzx   eax, byte ptr [r14+1]
0x140041289  add     eax, 2
0x14004128c  mov     r8d, eax; Size
0x14004128f  mov     [rbx+68h], eax
0x140041292  call    memmove
0x140041297  lea     r9, [rsp+78h+Src]; struct DOT11_INFO_ELEMENT **
0x14004129f  mov     r8b, 0F4h; unsigned __int8
0x1400412a2  mov     edx, r15d; unsigned int
0x1400412a5  lea     rcx, [r12+0Ch]; unsigned __int8 *
0x1400412aa  call    ?GetDot11InfoElement@@YAHPEBEKEPEAPEAUDOT11_INFO_ELEMENT@@@Z; GetDot11InfoElement(uchar const *,ulong,uchar,DOT11_INFO_ELEMENT * *)
0x1400412af  xor     r15d, r15d
0x1400412b2  test    eax, eax
0x1400412b4  jnz     loc_140040FD7
0x1400412ba  mov     r14, [rsp+78h+Src]
0x1400412c2  movzx   eax, byte ptr [r14+1]
0x1400412c7  add     eax, 12h
0x1400412ca  mov     [rbx+70h], r15
0x1400412ce  cmp     eax, 10h
0x1400412d1  jb      short loc_140041307
0x1400412d3  cmp     eax, 40h ; '@'
0x1400412d6  jbe     short loc_1400412EF
0x1400412d8  cmp     eax, 100h
0x1400412dd  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400412e4  lea     rax, Lookaside
0x1400412eb  cmova   rsi, rax
0x1400412ef  mov     rcx, rsi; Lookaside
0x1400412f2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400412f9  nop     dword ptr [rax+rax+00h]
0x1400412fe  test    rax, rax
0x140041301  jnz     loc_140041455
0x140041307  mov     edi, 0C000009Ah
0x14004130c  mov     rcx, cs:WPP_GLOBAL_Control
0x140041313  cmp     rcx, rbp
0x140041316  jz      loc_140041239
0x14004131c  mov     rcx, [rcx+18h]
0x140041320  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140041327  mov     edx, 16Ch
0x14004132c  mov     r9, r13
0x14004132f  call    WPP_SF__MAC_
0x140041334  jmp     loc_140041239
0x140041339  mov     edx, [rcx+8]; Tag
0x14004133c  call    cs:__imp_ExFreePoolWithTag
0x140041343  nop     dword ptr [rax+rax+00h]
0x140041348  mov     [rbx+38h], r15
0x14004134c  mov     rcx, [rbx+48h]
0x140041350  mov     [rbx+40h], r15d
0x140041354  test    rcx, rcx
0x140041357  jz      short loc_140041390
0x140041359  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004135d  mov     rax, [rcx]
0x140041360  test    rax, rax
0x140041363  jz      short loc_140041379
0x140041365  mov     rdx, rcx; Entry
0x140041368  mov     rcx, rax; Lookaside
0x14004136b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041372  nop     dword ptr [rax+rax+00h]
0x140041377  jmp     short loc_140041388
0x140041379  mov     edx, [rcx+8]; Tag
0x14004137c  call    cs:__imp_ExFreePoolWithTag
0x140041383  nop     dword ptr [rax+rax+00h]
0x140041388  mov     [rbx+48h], r15
0x14004138c  mov     [rbx+50h], r15d
0x140041390  mov     rcx, [rbx+60h]
0x140041394  test    rcx, rcx
0x140041397  jz      short loc_1400413D0
0x140041399  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004139d  mov     rax, [rcx]
0x1400413a0  test    rax, rax
0x1400413a3  jz      short loc_1400413B9
0x1400413a5  mov     rdx, rcx; Entry
  ... truncated ...
```
