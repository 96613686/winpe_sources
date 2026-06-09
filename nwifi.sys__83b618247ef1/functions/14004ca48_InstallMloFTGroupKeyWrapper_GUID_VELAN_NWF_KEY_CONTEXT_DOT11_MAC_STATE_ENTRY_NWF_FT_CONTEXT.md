# InstallMloFTGroupKeyWrapper(_GUID *,_VELAN *,_NWF_KEY_CONTEXT *,DOT11_MAC_STATE_ENTRY *,NWF_FT_CONTEXT *)

- ea: `0x14004ca48`
- end: `0x14004d45e`
- name: `?InstallMloFTGroupKeyWrapper@@YAJPEAU_GUID@@PEAU_VELAN@@PEAU_NWF_KEY_CONTEXT@@PEAUDOT11_MAC_STATE_ENTRY@@PEAUNWF_FT_CONTEXT@@@Z`
- size: `2582`
- prototype: `int(struct _GUID *, struct _VELAN *, struct _NWF_KEY_CONTEXT *, struct DOT11_MAC_STATE_ENTRY *, struct NWF_FT_CONTEXT *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140046bf0`

## callees

- `0x14000a8a8`
- `0x14000d22c`
- `0x1400160e0`
- `0x1400165c4`
- `0x14001a320`
- `0x140020dc0`
- `0x14002ffb4`
- `0x14003f1a0`
- `0x140040a18`
- `0x140047858`
- `0x14004a058`
- `0x14004a60c`
- `0x14004ca48`
- `0x1400500b0`
- `0x140052afc`
- `0x14005304c`
- `0x1400532e0`
- `0x14008ddb4`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004cc40`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004cc40`
- `ntoskrnl!ExAllocatePool2` at `0x14004cc59`
- `ntoskrnl!ExAllocatePool2` at `0x14004cc59`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004d2c4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004d423`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004d2c4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004d423`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d3ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d434`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d3ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d434`

## pseudocode

```c
__int64 __fastcall InstallMloFTGroupKeyWrapper(
        struct _GUID *a1,
        struct _VELAN *a2,
        struct _NWF_KEY_CONTEXT *a3,
        struct DOT11_MAC_STATE_ENTRY *a4,
        struct NWF_FT_CONTEXT *a5)
{
  struct NWF_FT_CONTEXT *v5; // r14
  struct NWF_FT_CONTEXT *v6; // r15
  PDEVICE_OBJECT v9; // rcx
  __int64 McastCipher; // r9
  __int64 v11; // rdx
  unsigned int IGTKCipherKeyLength; // eax
  void *v14; // r12
  int v15; // eax
  __int64 v16; // r9
  unsigned int v17; // ebx
  unsigned int v18; // esi
  int v19; // ecx
  unsigned int v20; // r13d
  unsigned int v21; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  unsigned __int8 *v24; // rbx
  unsigned __int8 *v25; // r13
  unsigned __int16 CipherKeyStructLength; // ax
  int v27; // r9d
  unsigned int v28; // r10d
  int v29; // eax
  _BYTE *v30; // rbx
  int v31; // edx
  int v32; // ecx
  unsigned int v33; // ecx
  unsigned __int8 *v34; // r13
  char *v35; // rbx
  unsigned int numMloIGtkSubelements; // eax
  unsigned int v37; // ecx
  unsigned __int8 *v38; // r13
  char *v39; // rbx
  unsigned int numMloBIGtkSubelements; // eax
  _DWORD *v41; // rax
  ULONG *v42; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v43; // rax
  PDEVICE_OBJECT v44; // rcx
  __int64 v45; // rdx
  PDEVICE_OBJECT v46; // rcx
  __int64 v47; // r8
  __int64 v48; // rdx
  int v49; // [rsp+28h] [rbp-58h]
  size_t v50; // [rsp+30h] [rbp-50h]
  unsigned int v51[2]; // [rsp+40h] [rbp-40h]
  int v52; // [rsp+50h] [rbp-30h]
  unsigned int Size; // [rsp+54h] [rbp-2Ch] BYREF
  unsigned int Size_4; // [rsp+58h] [rbp-28h]
  unsigned int v55; // [rsp+5Ch] [rbp-24h]
  void *v56; // [rsp+60h] [rbp-20h]
  unsigned __int8 *Src; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int8 *v58; // [rsp+70h] [rbp-10h]
  int v59; // [rsp+C0h] [rbp+40h]

  v59 = (int)a1;
  v5 = a5;
  v6 = 0;
  if ( !a5->numMloGtkSubelements )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 468, WPP_e90d411d816e312466897e39e745b158_Traceguids);
    return 3221225701LL;
  }
  Size_4 = GetGTKCipherKeyLength(a3->McastCipher);
  if ( !(_BYTE)Size_4 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      McastCipher = (unsigned int)a3->McastCipher;
      v11 = 469;
LABEL_11:
      WPP_SF_d(v9->AttachedDevice, v11, WPP_e90d411d816e312466897e39e745b158_Traceguids, McastCipher);
      return 3221225701LL;
    }
    return 3221225701LL;
  }
  IGTKCipherKeyLength = GetIGTKCipherKeyLength(a3->McastMgmtCipher);
  v55 = IGTKCipherKeyLength;
  if ( v5->numMloIGtkSubelements )
  {
    if ( !(_BYTE)IGTKCipherKeyLength )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        McastCipher = (unsigned int)a3->McastMgmtCipher;
        v11 = 470;
        goto LABEL_11;
      }
      return 3221225701LL;
    }
  }
  else if ( v5->numMloBIGtkSubelements )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        471,
        WPP_e90d411d816e312466897e39e745b158_Traceguids,
        v5->numMloBIGtkSubelements);
    return 3221225701LL;
  }
  Size = 0;
  Src = 0;
  v14 = 0;
  v15 = AllocateBuffersForFTGroupKeys(v5, &Size, &Src);
  v17 = v15;
  if ( v15 < 0 )
  {
    v18 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        472,
        WPP_e90d411d816e312466897e39e745b158_Traceguids,
        (unsigned int)v15);
    v6 = a5;
    goto LABEL_66;
  }
  v19 = v5->numMloIGtkSubelements + v5->numMloGtkSubelements + v5->numMloBIGtkSubelements;
  v52 = 73 * v19 + 8;
  v20 = 73 * v19 + 352;
  v21 = 73 * v19 + 368;
  if ( v21 < 0x10 )
    goto LABEL_32;
  if ( v21 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_29:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_31;
  }
  if ( v21 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_29;
  }
  if ( v21 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_29;
  }
  if ( v21 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_29;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v21, 2053731191, v16);
LABEL_31:
  if ( !Pool2 )
  {
LABEL_32:
    v17 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 473, WPP_e90d411d816e312466897e39e745b158_Traceguids, v20);
    goto LABEL_65;
  }
  v6 = (struct NWF_FT_CONTEXT *)(Pool2 + 16);
  LODWORD(a5) = 0;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  *((_DWORD *)Pool2 + 2) = 2053731191;
  memset(Pool2 + 16, 0, v20);
  v24 = Src;
  v6->ppFTE_Mlo_BIGTKSubElements[0] = (unsigned __int8 *)a2;
  v6->ppFTE_Mlo_IGTKSubElements[4] = (unsigned __int8 *)&v6->ppFTE_Mlo_BIGTKSubElements[3];
  v56 = &v6->ppFTE_Mlo_BIGTKSubElements[3];
  *(_DWORD *)&v6->numMloBIGtkSubelements = v52;
  LODWORD(v6->ppFTE_Mlo_BIGTKSubElements[2]) = 0;
  if ( v5->numMloGtkSubelements )
  {
    while ( 1 )
    {
      v25 = v5->ppFTE_Mlo_GTKSubElements[(unsigned int)v14];
      CipherKeyStructLength = ValidateAndGetCipherKeyStructLength(a3->McastCipher, v25[5]);
      LOWORD(a5) = CipherKeyStructLength;
      if ( (_BYTE)Size_4 != (_BYTE)v27 || !CipherKeyStructLength )
        break;
      memset(v24, 0, Size);
      v29 = AES_UNWRAP(
              (int)a3 + a3->TempPTK.KCKLength + 1044,
              a3->TempPTK.KEKLength,
              (int)v25 + 14,
              (unsigned int)v25[1] - 12,
              (__int64)v24);
      v17 = v29;
      if ( v29 < 0 )
      {
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v45 = 475;
LABEL_71:
          WPP_SF_d(v44->AttachedDevice, v45, WPP_e90d411d816e312466897e39e745b158_Traceguids, (unsigned int)v29);
        }
        goto LABEL_64;
      }
      v30 = (char *)v56 + 73 * (unsigned int)v14 + 8;
      v58 = v30;
      memset(v30, 0, 0x49u);
      *v30 = v25[4] & 0xF;
      LODWORD(v50) = v25[5];
      LODWORD(a5) = FillCipherDefaultKeyValues(
                      a3->McastCipher,
                      (const unsigned __int8 (*)[6])a4->MacHashEntry.MacKey,
                      v25[2] & 3,
                      v25 + 6,
                      0,
                      (unsigned __int16)a5,
                      v50,
                      Src,
                      v51[0],
                      (struct DOT11_CIPHER_DEFAULT_KEY_VALUE *)(v30 + 1));
      v17 = (unsigned int)a5;
      if ( (int)a5 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_lll(
            WPP_GLOBAL_Control->AttachedDevice,
            476,
            WPP_e90d411d816e312466897e39e745b158_Traceguids,
            (unsigned int)v14,
            a3->McastCipher,
            v25[5]);
        goto LABEL_64;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        *(_QWORD *)v51 = *(_QWORD *)(v25 + 6);
        WPP_SF_ddDddi(
          WPP_GLOBAL_Control->AttachedDevice,
          v25[5],
          v25[2] & 3,
          (unsigned int)v14,
          v25[4] & 0xF,
          a3->McastCipher,
          v25[5],
          v25[2] & 3);
      }
      v24 = Src;
      CacheNewGroupKey(a3, *v58, DOT11_CIPHER_KEY_TYPE_GROUP_KEY, a3->McastCipher, v25[5], Src);
      LODWORD(v14) = (_DWORD)v14 + 1;
      if ( (byte_1400AF804 & 8) != 0 )
        McTemplateK0qquq_EtwWriteTransfer(v32, v31, v59, v25[2] & 3, a3->McastCipher, v49, v25[5]);
      if ( (unsigned int)v14 >= v5->numMloGtkSubelements )
        goto LABEL_44;
    }
    v17 = -1073741595;
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_64;
    v47 = (unsigned __int8)Size_4;
    v48 = 474;
  }
  else
  {
LABEL_44:
    v33 = 0;
    Size_4 = 0;
    if ( v5->numMloIGtkSubelements )
    {
      while ( 1 )
      {
        v34 = v5->ppFTE_Mlo_IGTKSubElements[v33];
        CipherKeyStructLength = ValidateAndGetCipherKeyStructLength(a3->McastMgmtCipher, v34[11]);
        LOWORD(a5) = CipherKeyStructLength;
        if ( (_BYTE)v55 != (_BYTE)v27 || !CipherKeyStructLength )
          break;
        memset(v24, 0, Size);
        v29 = AES_UNWRAP(
                (int)a3 + a3->TempPTK.KCKLength + 1044,
                a3->TempPTK.KEKLength,
                (int)v34 + 12,
                (unsigned int)v34[1] - 10,
                (__int64)v24);
        v17 = v29;
        if ( v29 < 0 )
        {
          v44 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_64;
          v45 = 479;
          goto LABEL_71;
        }
        v35 = (char *)v56 + 73 * (unsigned int)v14;
        memset(v35 + 8, 0, 0x49u);
        v35[8] = v34[10] & 0xF;
        LODWORD(v50) = v34[11];
        v29 = FillCipherDefaultKeyValues(
                a3->McastMgmtCipher,
                (const unsigned __int8 (*)[6])a4->MacHashEntry.MacKey,
                *((unsigned __int16 *)v34 + 1),
                0,
                v34 + 4,
                (unsigned __int16)a5,
                v50,
                Src,
                v51[0],
                (struct DOT11_CIPHER_DEFAULT_KEY_VALUE *)(v35 + 9));
        LODWORD(a5) = v29;
        v17 = v29;
        if ( v29 < 0 )
        {
          v44 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_64;
          v45 = 480;
          goto LABEL_71;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_dDddd(
            WPP_GLOBAL_Control->AttachedDevice,
            482,
            v34[11],
            (unsigned int)v14,
            v34[10] & 0xF,
            a3->McastMgmtCipher,
            v34[11],
            *((unsigned __int16 *)v34 + 1));
        v24 = Src;
        CacheNewGroupKey(a3, v34[10] & 0xF, DOT11_CIPHER_KEY_TYPE_IGTK, a3->McastMgmtCipher, v34[11], Src);
        LODWORD(v14) = (_DWORD)v14 + 1;
        numMloIGtkSubelements = v5->numMloIGtkSubelements;
        v33 = Size_4 + 1;
        Size_4 = v33;
        if ( v33 >= numMloIGtkSubelements )
          goto LABEL_52;
      }
      v17 = -1073741595;
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_64;
      v47 = (unsigned __int8)v55;
      v48 = 478;
    }
    else
    {
LABEL_52:
      v37 = 0;
      Size_4 = 0;
      if ( !v5->numMloBIGtkSubelements )
      {
LABEL_60:
        v41 = v56;
        v18 = v52;
        *((_DWORD *)v56 + 1) = 0;
        *v41 = (_DWORD)v14;
        Dot11BuildNdisRequest(
          (struct DOT11_NDIS_REQUEST *)v6,
          1u,
          0xE010305u,
          v52,
          v41,
          (void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *))FreeOidRequestBuffer,
          &v6->ppFTE_Mlo_IGTKSubElements[4],
          0);
        _InterlockedIncrement((volatile signed __int32 *)&a4->uRefCnt);
        v6->ppFTE_Mlo_BIGTKSubElements[1] = (unsigned __int8 *)a4;
        Dot11Request((int *)&a5, a2->pAdapt, *(struct _NDIS_OID_REQUEST **)&v6->Ssid.ucSSID[4]);
        v17 = (unsigned int)a5;
        if ( (_DWORD)a5 == 259 )
          v17 = 0;
        else
          Dot11RequestComplete(a2->pAdapt, *(struct _NDIS_OID_REQUEST **)&v6->Ssid.ucSSID[4], (int)a5);
        v6 = 0;
        v14 = 0;
        goto LABEL_66;
      }
      while ( 1 )
      {
        v38 = v5->ppFTE_Mlo_BIGTKSubElements[v37];
        CipherKeyStructLength = ValidateAndGetCipherKeyStructLength(a3->McastMgmtCipher, v38[11]);
        LOWORD(a5) = CipherKeyStructLength;
        if ( (_BYTE)v55 != (_BYTE)v27 || !CipherKeyStructLength )
          break;
        memset(v24, 0, Size);
        v29 = AES_UNWRAP(
                (int)a3 + a3->TempPTK.KCKLength + 1044,
                a3->TempPTK.KEKLength,
                (int)v38 + 12,
                (unsigned int)v38[1] - 10,
                (__int64)v24);
        v17 = v29;
        if ( v29 < 0 )
        {
          v44 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_64;
          v45 = 484;
          goto LABEL_71;
        }
        v39 = (char *)v56 + 73 * (unsigned int)v14;
        memset(v39 + 8, 0, 0x49u);
        v39[8] = v38[10] & 0xF;
        LODWORD(v50) = v38[11];
        v29 = FillCipherDefaultKeyValues(
                a3->McastMgmtCipher,
                (const unsigned __int8 (*)[6])a4->MacHashEntry.MacKey,
                *((unsigned __int16 *)v38 + 1),
                0,
                v38 + 4,
                (unsigned __int16)a5,
                v50,
                Src,
                v51[0],
                (struct DOT11_CIPHER_DEFAULT_KEY_VALUE *)(v39 + 9));
        LODWORD(a5) = v29;
        v17 = v29;
        if ( v29 < 0 )
        {
          v44 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_64;
          v45 = 485;
          goto LABEL_71;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_dDddd(
            WPP_GLOBAL_Control->AttachedDevice,
            487,
            v38[11],
            (unsigned int)v14,
            v38[10] & 0xF,
            a3->McastMgmtCipher,
            v38[11],
            *((unsigned __int16 *)v38 + 1));
        v24 = Src;
        CacheNewGroupKey(a3, v38[10] & 0xF, DOT11_CIPHER_KEY_TYPE_BIGTK, a3->McastMgmtCipher, v38[11], Src);
        LODWORD(v14) = (_DWORD)v14 + 1;
        numMloBIGtkSubelements = v5->numMloBIGtkSubelements;
        v37 = Size_4 + 1;
        Size_4 = v37;
        if ( v37 >= numMloBIGtkSubelements )
          goto LABEL_60;
      }
      v17 = -1073741595;
      v46 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_64;
      v47 = (unsigned __int8)v55;
      v48 = 483;
    }
  }
  WPP_SF_dDDd(v46->AttachedDevice, v48, v47, v28, v47, v27, CipherKeyStructLength);
LABEL_64:
  v14 = v56;
LABEL_65:
  v18 = v52;
LABEL_66:
  if ( Src )
  {
    v42 = (ULONG *)(Src - 16);
    v43 = (struct _NPAGED_LOOKASIDE_LIST *)*((_QWORD *)Src - 2);
    if ( v43 )
      ExFreeToNPagedLookasideList(v43, v42);
    else
      ExFreePoolWithTag(v42, v42[2]);
  }
  if ( v14 )
    memset(v14, 0, v18);
  if ( v6 )
  {
    if ( v6[-1].pReassembledFTEIE )
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v6[-1].pReassembledFTEIE, &v6[-1].pReassembledFTEIE);
    else
      ExFreePoolWithTag(&v6[-1].pReassembledFTEIE, v6[-1].uResponseIEsLength);
  }
  return v17;
}

```

## disassembly

```asm
0x14004ca48  mov     rax, rsp
0x14004ca4b  mov     [rax+18h], rbx
0x14004ca4f  mov     [rax+20h], r9
0x14004ca53  mov     [rax+10h], rdx
0x14004ca57  mov     [rax+8], rcx
0x14004ca5b  push    rbp
0x14004ca5c  push    rsi
0x14004ca5d  push    rdi
0x14004ca5e  push    r12
0x14004ca60  push    r13
0x14004ca62  push    r14
0x14004ca64  push    r15
0x14004ca66  mov     rbp, rsp
0x14004ca69  sub     rsp, 80h
0x14004ca70  mov     r14, [rbp+arg_20]
0x14004ca74  xor     r15d, r15d
0x14004ca77  mov     rsi, r8
0x14004ca7a  mov     rdi, rdx
0x14004ca7d  cmp     [r14+0DEh], r15b
0x14004ca84  jnz     short loc_14004CAB7
0x14004ca86  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ca8d  lea     rdi, WPP_GLOBAL_Control
0x14004ca94  cmp     rcx, rdi
0x14004ca97  jz      loc_14004CB66
0x14004ca9d  mov     rcx, [rcx+18h]
0x14004caa1  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004caa8  mov     edx, 1D4h
0x14004caad  call    WPP_SF_
0x14004cab2  jmp     loc_14004CB66
0x14004cab7  mov     ecx, [r8+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004cabb  call    ?GetGTKCipherKeyLength@@YAKW4_DOT11_CIPHER_ALGORITHM@@@Z; GetGTKCipherKeyLength(_DOT11_CIPHER_ALGORITHM)
0x14004cac0  mov     dword ptr [rbp+Size+4], eax
0x14004cac3  test    al, al
0x14004cac5  jnz     short loc_14004CAE9
0x14004cac7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cace  lea     rdi, WPP_GLOBAL_Control
0x14004cad5  cmp     rcx, rdi
0x14004cad8  jz      loc_14004CB66
0x14004cade  mov     r9d, [rsi+14h]
0x14004cae2  mov     edx, 1D5h
0x14004cae7  jmp     short loc_14004CB1D
0x14004cae9  mov     ecx, [rsi+18h]; enum _DOT11_CIPHER_ALGORITHM
0x14004caec  call    ?GetIGTKCipherKeyLength@@YAKW4_DOT11_CIPHER_ALGORITHM@@@Z; GetIGTKCipherKeyLength(_DOT11_CIPHER_ALGORITHM)
0x14004caf1  mov     [rbp+var_24], eax
0x14004caf4  cmp     [r14+108h], r15b
0x14004cafb  jbe     short loc_14004CB2F
0x14004cafd  test    al, al
0x14004caff  jnz     short loc_14004CB70
0x14004cb01  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cb08  lea     rdi, WPP_GLOBAL_Control
0x14004cb0f  cmp     rcx, rdi
0x14004cb12  jz      short loc_14004CB66
0x14004cb14  mov     r9d, [rsi+18h]
0x14004cb18  mov     edx, 1D6h
0x14004cb1d  mov     rcx, [rcx+18h]
0x14004cb21  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004cb28  call    WPP_SF_d
0x14004cb2d  jmp     short loc_14004CB66
0x14004cb2f  movzx   eax, byte ptr [r14+138h]
0x14004cb37  test    al, al
0x14004cb39  jz      short loc_14004CB70
0x14004cb3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cb42  lea     rdi, WPP_GLOBAL_Control
0x14004cb49  cmp     rcx, rdi
0x14004cb4c  jz      short loc_14004CB66
0x14004cb4e  mov     rcx, [rcx+18h]
0x14004cb52  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004cb59  mov     r9d, eax
0x14004cb5c  mov     edx, 1D7h
0x14004cb61  call    WPP_SF_d
0x14004cb66  mov     eax, 0C00000E5h
0x14004cb6b  jmp     loc_14004D442
0x14004cb70  lea     r8, [rbp+var_18]; unsigned __int8 **
0x14004cb74  mov     dword ptr [rbp+Size], r15d
0x14004cb78  lea     rdx, [rbp+Size]; unsigned int *
0x14004cb7c  mov     [rbp+var_18], r15
0x14004cb80  mov     rcx, r14; struct NWF_FT_CONTEXT *
0x14004cb83  mov     r12, r15
0x14004cb86  call    ?AllocateBuffersForFTGroupKeys@@YAJPEAUNWF_FT_CONTEXT@@PEAKPEAPEAE@Z; AllocateBuffersForFTGroupKeys(NWF_FT_CONTEXT *,ulong *,uchar * *)
0x14004cb8b  mov     ebx, eax
0x14004cb8d  test    eax, eax
0x14004cb8f  jns     short loc_14004CBC8
0x14004cb91  mov     esi, r15d
0x14004cb94  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cb9b  lea     rdi, WPP_GLOBAL_Control
0x14004cba2  cmp     rcx, rdi
0x14004cba5  jz      short loc_14004CBBF
0x14004cba7  mov     rcx, [rcx+18h]
0x14004cbab  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004cbb2  mov     edx, 1D8h
0x14004cbb7  mov     r9d, eax
0x14004cbba  call    WPP_SF_d
0x14004cbbf  mov     r15, [rbp+arg_20]
0x14004cbc3  jmp     loc_14004D2A1
0x14004cbc8  movzx   eax, byte ptr [r14+0DEh]
0x14004cbd0  movzx   ecx, byte ptr [r14+138h]
0x14004cbd8  add     ecx, eax
0x14004cbda  movzx   eax, byte ptr [r14+108h]
0x14004cbe2  add     ecx, eax
0x14004cbe4  imul    edx, ecx, 49h ; 'I'
0x14004cbe7  add     edx, 8
0x14004cbea  mov     [rbp+var_30], edx
0x14004cbed  lea     r13d, [rdx+158h]
0x14004cbf4  lea     eax, [r13+10h]
0x14004cbf8  cmp     eax, 10h
0x14004cbfb  jb      short loc_14004CC6A
0x14004cbfd  mov     ecx, 40h ; '@'
0x14004cc02  cmp     eax, ecx
0x14004cc04  ja      short loc_14004CC0F
0x14004cc06  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004cc0d  jmp     short loc_14004CC3D
0x14004cc0f  cmp     eax, 100h
0x14004cc14  ja      short loc_14004CC1F
0x14004cc16  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004cc1d  jmp     short loc_14004CC3D
0x14004cc1f  cmp     eax, 400h
0x14004cc24  ja      short loc_14004CC2F
0x14004cc26  lea     rbx, Lookaside
0x14004cc2d  jmp     short loc_14004CC3D
0x14004cc2f  cmp     eax, 800h
0x14004cc34  ja      short loc_14004CC4E
0x14004cc36  lea     rbx, stru_1400B0180
0x14004cc3d  mov     rcx, rbx; Lookaside
0x14004cc40  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004cc47  nop     dword ptr [rax+rax+00h]
0x14004cc4c  jmp     short loc_14004CC65
0x14004cc4e  mov     edx, eax
0x14004cc50  mov     r8d, 7A697377h
0x14004cc56  mov     rbx, r15
0x14004cc59  call    cs:__imp_ExAllocatePool2
0x14004cc60  nop     dword ptr [rax+rax+00h]
0x14004cc65  test    rax, rax
0x14004cc68  jnz     short loc_14004CCA3
0x14004cc6a  mov     ebx, 0C000009Ah
0x14004cc6f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cc76  lea     rdi, WPP_GLOBAL_Control
0x14004cc7d  cmp     rcx, rdi
0x14004cc80  jz      loc_14004D29E
0x14004cc86  mov     rcx, [rcx+18h]
0x14004cc8a  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004cc91  mov     edx, 1D9h
0x14004cc96  mov     r9d, r13d
0x14004cc99  call    WPP_SF_d
0x14004cc9e  jmp     loc_14004D29E
0x14004cca3  xor     ecx, ecx
0x14004cca5  mov     r8d, r13d; Size
0x14004cca8  lea     r15, [rax+10h]
0x14004ccac  mov     dword ptr [rbp+arg_20], ecx
0x14004ccaf  mov     rcx, r15; void *
0x14004ccb2  mov     [rax], rbx
0x14004ccb5  xor     edx, edx; Val
0x14004ccb7  mov     dword ptr [rax+8], 7A697377h
0x14004ccbe  call    memset
0x14004ccc3  mov     rbx, [rbp+var_18]
0x14004ccc7  lea     rcx, [r15+130h]
0x14004ccce  lea     rax, [rcx+28h]
0x14004ccd2  mov     [rcx+10h], rdi
0x14004ccd6  mov     [rcx], rax
0x14004ccd9  lea     rdi, WPP_GLOBAL_Control
0x14004cce0  xor     edx, edx
0x14004cce2  mov     [rbp+var_20], rax
0x14004cce6  mov     eax, [rbp+var_30]
0x14004cce9  mov     [rcx+8], eax
0x14004ccec  mov     [rcx+20h], edx
0x14004ccef  cmp     [r14+0DEh], dl
0x14004ccf6  jbe     loc_14004CEB6
0x14004ccfc  mov     r10d, [rsi+14h]
0x14004cd00  mov     ecx, r10d; enum _DOT11_CIPHER_ALGORITHM
0x14004cd03  mov     eax, r12d
0x14004cd06  mov     r13, [r14+rax*8+0E0h]
0x14004cd0e  movzx   r9d, byte ptr [r13+5]
0x14004cd13  mov     edx, r9d; unsigned int
0x14004cd16  call    ?ValidateAndGetCipherKeyStructLength@@YAGW4_DOT11_CIPHER_ALGORITHM@@K@Z; ValidateAndGetCipherKeyStructLength(_DOT11_CIPHER_ALGORITHM,ulong)
0x14004cd1b  mov     edx, dword ptr [rbp+Size+4]
0x14004cd1e  mov     word ptr [rbp+arg_20], ax
0x14004cd22  cmp     dl, r9b
0x14004cd25  jnz     loc_14004D2FB
0x14004cd2b  test    ax, ax
0x14004cd2e  jz      loc_14004D2FB
0x14004cd34  mov     r8d, dword ptr [rbp+Size]; Size
0x14004cd38  xor     edx, edx; Val
0x14004cd3a  mov     rcx, rbx; void *
0x14004cd3d  call    memset
0x14004cd42  mov     ecx, [rsi+408h]
0x14004cd48  lea     r8, [r13+0Eh]
0x14004cd4c  movzx   r9d, byte ptr [r13+1]
0x14004cd51  add     rcx, 414h
0x14004cd58  mov     edx, [rsi+40Ch]
0x14004cd5e  add     rcx, rsi
0x14004cd61  sub     r9d, 0Ch
0x14004cd65  mov     [rsp+80h+var_60], rbx
0x14004cd6a  call    AES_UNWRAP
0x14004cd6f  mov     ebx, eax
0x14004cd71  test    eax, eax
0x14004cd73  js      loc_14004D2D5
0x14004cd79  mov     rbx, [rbp+var_20]
0x14004cd7d  xor     edx, edx; Val
0x14004cd7f  mov     eax, r12d
0x14004cd82  add     rbx, 8
0x14004cd86  imul    rax, 49h ; 'I'
0x14004cd8a  lea     r8d, [rdx+49h]; Size
0x14004cd8e  add     rbx, rax
0x14004cd91  mov     rcx, rbx; void *
0x14004cd94  mov     [rbp+var_10], rbx
0x14004cd98  call    memset
0x14004cd9d  mov     al, [r13+4]
0x14004cda1  lea     r9, [r13+6]; unsigned __int8 *
0x14004cda5  mov     rdx, [rbp+arg_18]
0x14004cda9  and     al, 0Fh
0x14004cdab  mov     [rbx], al
0x14004cdad  add     rdx, 10h; unsigned __int8 (*)[6]
0x14004cdb1  movzx   ecx, byte ptr [r13+5]
0x14004cdb6  lea     rax, [rbx+1]
0x14004cdba  movzx   r8d, byte ptr [r13+2]
0x14004cdbf  mov     [rsp+80h+var_38], rax; struct DOT11_CIPHER_DEFAULT_KEY_VALUE *
0x14004cdc4  and     r8d, 3; unsigned int
0x14004cdc8  mov     rax, [rbp+var_18]
0x14004cdcc  mov     [rsp+80h+Src], rax; Src
0x14004cdd1  movzx   eax, word ptr [rbp+arg_20]
0x14004cdd5  mov     dword ptr [rsp+80h+var_50], ecx; Size
0x14004cdd9  mov     ecx, [rsi+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004cddc  mov     word ptr [rsp+80h+var_58], ax; unsigned __int16
0x14004cde1  mov     [rsp+80h+var_60], 0; unsigned __int8 *
0x14004cdea  call    ?FillCipherDefaultKeyValues@@YAHW4_DOT11_CIPHER_ALGORITHM@@PEAY05$$CBEKPEBE2GK2KPEAUDOT11_CIPHER_DEFAULT_KEY_VALUE@@@Z; FillCipherDefaultKeyValues(_DOT11_CIPHER_ALGORITHM,uchar const (*)[6],ulong,uchar const *,uchar const *,ushort,ulong,uchar const *,ulong,DOT11_CIPHER_DEFAULT_KEY_VALUE *)
0x14004cdef  mov     dword ptr [rbp+arg_20], eax
0x14004cdf2  mov     ebx, eax
0x14004cdf4  test    eax, eax
0x14004cdf6  js      loc_14004D266
0x14004cdfc  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ce03  cmp     rcx, rdi
0x14004ce06  jz      short loc_14004CE49
0x14004ce08  mov     rax, [r13+6]
0x14004ce0c  movzx   r8d, byte ptr [r13+2]
0x14004ce11  movzx   edx, byte ptr [r13+5]
0x14004ce16  and     r8d, 3
0x14004ce1a  movzx   r9d, byte ptr [r13+4]
0x14004ce1f  mov     rcx, [rcx+18h]
0x14004ce23  and     r9d, 0Fh
0x14004ce27  mov     qword ptr [rsp+80h+var_40], rax; unsigned int
0x14004ce2c  mov     eax, [rsi+14h]
0x14004ce2f  mov     dword ptr [rsp+80h+Src], r8d
0x14004ce34  mov     dword ptr [rsp+80h+var_50], edx
0x14004ce38  mov     dword ptr [rsp+80h+var_58], eax
0x14004ce3c  mov     dword ptr [rsp+80h+var_60], r9d
0x14004ce41  mov     r9d, r12d
0x14004ce44  call    WPP_SF_ddDddi
0x14004ce49  mov     rcx, [rbp+var_10]
0x14004ce4d  mov     r8d, 2; enum _DOT11_CIPHER_KEY_TYPE
0x14004ce53  movzx   eax, byte ptr [r13+5]
0x14004ce58  mov     rbx, [rbp+var_18]
0x14004ce5c  mov     r9d, [rsi+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004ce60  movzx   edx, byte ptr [rcx]; unsigned int
0x14004ce63  mov     rcx, rsi; struct _NWF_KEY_CONTEXT *
0x14004ce66  mov     [rsp+80h+var_58], rbx; unsigned __int8 *
0x14004ce6b  mov     word ptr [rsp+80h+var_60], ax; unsigned __int16
0x14004ce70  call    ?CacheNewGroupKey@@YAHPEAU_NWF_KEY_CONTEXT@@KW4_DOT11_CIPHER_KEY_TYPE@@W4_DOT11_CIPHER_ALGORITHM@@GPEAE@Z; CacheNewGroupKey(_NWF_KEY_CONTEXT *,ulong,_DOT11_CIPHER_KEY_TYPE,_DOT11_CIPHER_ALGORITHM,ushort,uchar *)
0x14004ce75  inc     r12d
0x14004ce78  test    cs:byte_1400AF804, 8
0x14004ce7f  jz      short loc_14004CEA3
0x14004ce81  movzx   eax, byte ptr [r13+5]
0x14004ce86  movzx   r9d, byte ptr [r13+2]
0x14004ce8b  mov     r8, [rbp+arg_0]
0x14004ce8f  and     r9d, 3
0x14004ce93  mov     dword ptr [rsp+80h+var_50], eax
0x14004ce97  mov     eax, [rsi+14h]
0x14004ce9a  mov     dword ptr [rsp+80h+var_60], eax
0x14004ce9e  call    McTemplateK0qquq_EtwWriteTransfer
0x14004cea3  movzx   eax, byte ptr [r14+0DEh]
0x14004ceab  cmp     r12d, eax
0x14004ceae  jb      loc_14004CCFC
0x14004ceb4  xor     edx, edx
0x14004ceb6  mov     ecx, edx
0x14004ceb8  mov     dword ptr [rbp+Size+4], edx
0x14004cebb  cmp     [r14+108h], dl
0x14004cec2  jbe     loc_14004D048
0x14004cec8  mov     r10d, [rsi+18h]
0x14004cecc  mov     eax, ecx
0x14004cece  mov     ecx, r10d; enum _DOT11_CIPHER_ALGORITHM
0x14004ced1  mov     r13, [r14+rax*8+110h]
0x14004ced9  movzx   r9d, byte ptr [r13+0Bh]
0x14004cede  mov     edx, r9d; unsigned int
0x14004cee1  call    ?ValidateAndGetCipherKeyStructLength@@YAGW4_DOT11_CIPHER_ALGORITHM@@K@Z; ValidateAndGetCipherKeyStructLength(_DOT11_CIPHER_ALGORITHM,ulong)
0x14004cee6  mov     edx, [rbp+var_24]
0x14004cee9  mov     word ptr [rbp+arg_20], ax
0x14004ceed  cmp     dl, r9b
0x14004cef0  jnz     loc_14004D365
0x14004cef6  test    ax, ax
0x14004cef9  jz      loc_14004D365
0x14004ceff  mov     r8d, dword ptr [rbp+Size]; Size
0x14004cf03  xor     edx, edx; Val
0x14004cf05  mov     rcx, rbx; void *
0x14004cf08  call    memset
0x14004cf0d  mov     ecx, [rsi+408h]
0x14004cf13  lea     r8, [r13+0Ch]
0x14004cf17  movzx   r9d, byte ptr [r13+1]
0x14004cf1c  add     rcx, 414h
0x14004cf23  mov     edx, [rsi+40Ch]
0x14004cf29  add     rcx, rsi
0x14004cf2c  sub     r9d, 0Ah
0x14004cf30  mov     [rsp+80h+var_60], rbx
  ... truncated ...
```
