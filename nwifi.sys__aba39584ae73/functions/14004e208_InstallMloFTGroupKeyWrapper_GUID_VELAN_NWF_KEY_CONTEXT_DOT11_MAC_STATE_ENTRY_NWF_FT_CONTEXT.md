# InstallMloFTGroupKeyWrapper(_GUID *,_VELAN *,_NWF_KEY_CONTEXT *,DOT11_MAC_STATE_ENTRY *,NWF_FT_CONTEXT *)

- ea: `0x14004e208`
- end: `0x14004ec1e`
- name: `?InstallMloFTGroupKeyWrapper@@YAJPEAU_GUID@@PEAU_VELAN@@PEAU_NWF_KEY_CONTEXT@@PEAUDOT11_MAC_STATE_ENTRY@@PEAUNWF_FT_CONTEXT@@@Z`
- size: `2582`
- prototype: `__int64 __fastcall(struct _GUID *, struct _VELAN *, struct _NWF_KEY_CONTEXT *, struct DOT11_MAC_STATE_ENTRY *, struct NWF_FT_CONTEXT *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140047e48`

## callees

- `0x14000a898`
- `0x14000d21c`
- `0x1400160d0`
- `0x1400165b4`
- `0x14001a320`
- `0x140020dc0`
- `0x140030244`
- `0x14003f3c0`
- `0x1400414b4`
- `0x140048ad0`
- `0x14004b2e0`
- `0x14004b894`
- `0x14004e208`
- `0x140051878`
- `0x14005431c`
- `0x14005486c`
- `0x140054b00`
- `0x14008f5e4`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004e400`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004e400`
- `ntoskrnl!ExAllocatePool2` at `0x14004e419`
- `ntoskrnl!ExAllocatePool2` at `0x14004e419`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004ea84`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004ebe3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004ea84`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004ebe3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ebae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ebf4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ebae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ebf4`

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
  unsigned int v16; // ebx
  unsigned int v17; // esi
  int v18; // ecx
  unsigned int v19; // r13d
  unsigned int v20; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  unsigned __int8 *v23; // rbx
  unsigned __int8 *v24; // r13
  unsigned __int16 CipherKeyStructLength; // ax
  int v26; // r9d
  unsigned int v27; // r10d
  int v28; // eax
  _BYTE *v29; // rbx
  int v30; // edx
  int v31; // ecx
  unsigned int v32; // ecx
  unsigned __int8 *v33; // r13
  char *v34; // rbx
  unsigned int numMloIGtkSubelements; // eax
  unsigned int v36; // ecx
  unsigned __int8 *v37; // r13
  char *v38; // rbx
  unsigned int numMloBIGtkSubelements; // eax
  _DWORD *v40; // rax
  ULONG *v41; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v42; // rax
  PDEVICE_OBJECT v43; // rcx
  __int64 v44; // rdx
  PDEVICE_OBJECT v45; // rcx
  __int64 v46; // r8
  __int64 v47; // rdx
  int v48; // [rsp+28h] [rbp-58h]
  size_t v49; // [rsp+30h] [rbp-50h]
  unsigned int v50[2]; // [rsp+40h] [rbp-40h]
  int v51; // [rsp+50h] [rbp-30h]
  unsigned int Size; // [rsp+54h] [rbp-2Ch] BYREF
  unsigned int Size_4; // [rsp+58h] [rbp-28h]
  unsigned int v54; // [rsp+5Ch] [rbp-24h]
  void *v55; // [rsp+60h] [rbp-20h]
  unsigned __int8 *Src; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int8 *v57; // [rsp+70h] [rbp-10h]
  int v58; // [rsp+C0h] [rbp+40h]

  v58 = (int)a1;
  v5 = a5;
  v6 = 0;
  if ( !a5->numMloGtkSubelements )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 487, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
    return 3221225701LL;
  }
  Size_4 = GetGTKCipherKeyLength(a3->McastCipher);
  if ( !(_BYTE)Size_4 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      McastCipher = (unsigned int)a3->McastCipher;
      v11 = 488;
LABEL_11:
      WPP_SF_d(v9->AttachedDevice, v11, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, McastCipher);
      return 3221225701LL;
    }
    return 3221225701LL;
  }
  IGTKCipherKeyLength = GetIGTKCipherKeyLength(a3->McastMgmtCipher);
  v54 = IGTKCipherKeyLength;
  if ( v5->numMloIGtkSubelements )
  {
    if ( !(_BYTE)IGTKCipherKeyLength )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        McastCipher = (unsigned int)a3->McastMgmtCipher;
        v11 = 489;
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
        490,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        v5->numMloBIGtkSubelements);
    return 3221225701LL;
  }
  Size = 0;
  Src = 0;
  v14 = 0;
  v15 = AllocateBuffersForFTGroupKeys(v5, &Size, &Src);
  v16 = v15;
  if ( v15 < 0 )
  {
    v17 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        491,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        (unsigned int)v15);
    v6 = a5;
    goto LABEL_66;
  }
  v18 = v5->numMloIGtkSubelements + v5->numMloGtkSubelements + v5->numMloBIGtkSubelements;
  v51 = 73 * v18 + 8;
  v19 = 73 * v18 + 352;
  v20 = 73 * v18 + 368;
  if ( v20 < 0x10 )
    goto LABEL_32;
  if ( v20 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_29:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_31;
  }
  if ( v20 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_29;
  }
  if ( v20 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_29;
  }
  if ( v20 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_29;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v20, 2053731191);
LABEL_31:
  if ( !Pool2 )
  {
LABEL_32:
    v16 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 492, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v19);
    goto LABEL_65;
  }
  v6 = (struct NWF_FT_CONTEXT *)(Pool2 + 16);
  LODWORD(a5) = 0;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  *((_DWORD *)Pool2 + 2) = 2053731191;
  memset(Pool2 + 16, 0, v19);
  v23 = Src;
  v6->ppFTE_Mlo_BIGTKSubElements[0] = (unsigned __int8 *)a2;
  v6->ppFTE_Mlo_IGTKSubElements[4] = (unsigned __int8 *)&v6->ppFTE_Mlo_BIGTKSubElements[3];
  v55 = &v6->ppFTE_Mlo_BIGTKSubElements[3];
  *(_DWORD *)&v6->numMloBIGtkSubelements = v51;
  LODWORD(v6->ppFTE_Mlo_BIGTKSubElements[2]) = 0;
  if ( v5->numMloGtkSubelements )
  {
    while ( 1 )
    {
      v24 = v5->ppFTE_Mlo_GTKSubElements[(unsigned int)v14];
      CipherKeyStructLength = ValidateAndGetCipherKeyStructLength(a3->McastCipher, v24[5]);
      LOWORD(a5) = CipherKeyStructLength;
      if ( (_BYTE)Size_4 != (_BYTE)v26 || !CipherKeyStructLength )
        break;
      memset(v23, 0, Size);
      v28 = AES_UNWRAP(
              (int)a3 + a3->TempPTK.KCKLength + 1044,
              a3->TempPTK.KEKLength,
              (int)v24 + 14,
              (unsigned int)v24[1] - 12,
              (__int64)v23);
      v16 = v28;
      if ( v28 < 0 )
      {
        v43 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v44 = 494;
LABEL_71:
          WPP_SF_d(v43->AttachedDevice, v44, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, (unsigned int)v28);
        }
        goto LABEL_64;
      }
      v29 = (char *)v55 + 73 * (unsigned int)v14 + 8;
      v57 = v29;
      memset(v29, 0, 0x49u);
      *v29 = v24[4] & 0xF;
      LODWORD(v49) = v24[5];
      LODWORD(a5) = FillCipherDefaultKeyValues(
                      a3->McastCipher,
                      (const unsigned __int8 (*)[6])a4->MacHashEntry.MacKey,
                      v24[2] & 3,
                      v24 + 6,
                      0,
                      (unsigned __int16)a5,
                      v49,
                      Src,
                      v50[0],
                      (struct DOT11_CIPHER_DEFAULT_KEY_VALUE *)(v29 + 1));
      v16 = (unsigned int)a5;
      if ( (int)a5 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_lll(
            WPP_GLOBAL_Control->AttachedDevice,
            495,
            WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
            (unsigned int)v14,
            a3->McastCipher,
            v24[5]);
        goto LABEL_64;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        *(_QWORD *)v50 = *(_QWORD *)(v24 + 6);
        WPP_SF_ddDddi(
          WPP_GLOBAL_Control->AttachedDevice,
          v24[5],
          v24[2] & 3,
          (unsigned int)v14,
          v24[4] & 0xF,
          a3->McastCipher,
          v24[5],
          v24[2] & 3);
      }
      v23 = Src;
      CacheNewGroupKey(a3, *v57, DOT11_CIPHER_KEY_TYPE_GROUP_KEY, a3->McastCipher, v24[5], Src);
      LODWORD(v14) = (_DWORD)v14 + 1;
      if ( (byte_1400B2804 & 8) != 0 )
        McTemplateK0qquq_EtwWriteTransfer(v31, v30, v58, v24[2] & 3, a3->McastCipher, v48, v24[5]);
      if ( (unsigned int)v14 >= v5->numMloGtkSubelements )
        goto LABEL_44;
    }
    v16 = -1073741595;
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_64;
    v46 = (unsigned __int8)Size_4;
    v47 = 493;
  }
  else
  {
LABEL_44:
    v32 = 0;
    Size_4 = 0;
    if ( v5->numMloIGtkSubelements )
    {
      while ( 1 )
      {
        v33 = v5->ppFTE_Mlo_IGTKSubElements[v32];
        CipherKeyStructLength = ValidateAndGetCipherKeyStructLength(a3->McastMgmtCipher, v33[11]);
        LOWORD(a5) = CipherKeyStructLength;
        if ( (_BYTE)v54 != (_BYTE)v26 || !CipherKeyStructLength )
          break;
        memset(v23, 0, Size);
        v28 = AES_UNWRAP(
                (int)a3 + a3->TempPTK.KCKLength + 1044,
                a3->TempPTK.KEKLength,
                (int)v33 + 12,
                (unsigned int)v33[1] - 10,
                (__int64)v23);
        v16 = v28;
        if ( v28 < 0 )
        {
          v43 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_64;
          v44 = 498;
          goto LABEL_71;
        }
        v34 = (char *)v55 + 73 * (unsigned int)v14;
        memset(v34 + 8, 0, 0x49u);
        v34[8] = v33[10] & 0xF;
        LODWORD(v49) = v33[11];
        v28 = FillCipherDefaultKeyValues(
                a3->McastMgmtCipher,
                (const unsigned __int8 (*)[6])a4->MacHashEntry.MacKey,
                *((unsigned __int16 *)v33 + 1),
                0,
                v33 + 4,
                (unsigned __int16)a5,
                v49,
                Src,
                v50[0],
                (struct DOT11_CIPHER_DEFAULT_KEY_VALUE *)(v34 + 9));
        LODWORD(a5) = v28;
        v16 = v28;
        if ( v28 < 0 )
        {
          v43 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_64;
          v44 = 499;
          goto LABEL_71;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_dDddd(
            WPP_GLOBAL_Control->AttachedDevice,
            501,
            v33[11],
            (unsigned int)v14,
            v33[10] & 0xF,
            a3->McastMgmtCipher,
            v33[11],
            *((unsigned __int16 *)v33 + 1));
        v23 = Src;
        CacheNewGroupKey(a3, v33[10] & 0xF, DOT11_CIPHER_KEY_TYPE_IGTK, a3->McastMgmtCipher, v33[11], Src);
        LODWORD(v14) = (_DWORD)v14 + 1;
        numMloIGtkSubelements = v5->numMloIGtkSubelements;
        v32 = Size_4 + 1;
        Size_4 = v32;
        if ( v32 >= numMloIGtkSubelements )
          goto LABEL_52;
      }
      v16 = -1073741595;
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_64;
      v46 = (unsigned __int8)v54;
      v47 = 497;
    }
    else
    {
LABEL_52:
      v36 = 0;
      Size_4 = 0;
      if ( !v5->numMloBIGtkSubelements )
      {
LABEL_60:
        v40 = v55;
        v17 = v51;
        *((_DWORD *)v55 + 1) = 0;
        *v40 = (_DWORD)v14;
        Dot11BuildNdisRequest(
          (struct DOT11_NDIS_REQUEST *)v6,
          1u,
          0xE010305u,
          v51,
          v40,
          (void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *))FreeOidRequestBuffer,
          &v6->ppFTE_Mlo_IGTKSubElements[4],
          0);
        _InterlockedIncrement((volatile signed __int32 *)&a4->uRefCnt);
        v6->ppFTE_Mlo_BIGTKSubElements[1] = (unsigned __int8 *)a4;
        Dot11Request((int *)&a5, a2->pAdapt, *(struct _NDIS_OID_REQUEST **)&v6->Ssid.ucSSID[4]);
        v16 = (unsigned int)a5;
        if ( (_DWORD)a5 == 259 )
          v16 = 0;
        else
          Dot11RequestComplete(a2->pAdapt, *(struct _NDIS_OID_REQUEST **)&v6->Ssid.ucSSID[4], (int)a5);
        v6 = 0;
        v14 = 0;
        goto LABEL_66;
      }
      while ( 1 )
      {
        v37 = v5->ppFTE_Mlo_BIGTKSubElements[v36];
        CipherKeyStructLength = ValidateAndGetCipherKeyStructLength(a3->McastMgmtCipher, v37[11]);
        LOWORD(a5) = CipherKeyStructLength;
        if ( (_BYTE)v54 != (_BYTE)v26 || !CipherKeyStructLength )
          break;
        memset(v23, 0, Size);
        v28 = AES_UNWRAP(
                (int)a3 + a3->TempPTK.KCKLength + 1044,
                a3->TempPTK.KEKLength,
                (int)v37 + 12,
                (unsigned int)v37[1] - 10,
                (__int64)v23);
        v16 = v28;
        if ( v28 < 0 )
        {
          v43 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_64;
          v44 = 503;
          goto LABEL_71;
        }
        v38 = (char *)v55 + 73 * (unsigned int)v14;
        memset(v38 + 8, 0, 0x49u);
        v38[8] = v37[10] & 0xF;
        LODWORD(v49) = v37[11];
        v28 = FillCipherDefaultKeyValues(
                a3->McastMgmtCipher,
                (const unsigned __int8 (*)[6])a4->MacHashEntry.MacKey,
                *((unsigned __int16 *)v37 + 1),
                0,
                v37 + 4,
                (unsigned __int16)a5,
                v49,
                Src,
                v50[0],
                (struct DOT11_CIPHER_DEFAULT_KEY_VALUE *)(v38 + 9));
        LODWORD(a5) = v28;
        v16 = v28;
        if ( v28 < 0 )
        {
          v43 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_64;
          v44 = 504;
          goto LABEL_71;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_dDddd(
            WPP_GLOBAL_Control->AttachedDevice,
            506,
            v37[11],
            (unsigned int)v14,
            v37[10] & 0xF,
            a3->McastMgmtCipher,
            v37[11],
            *((unsigned __int16 *)v37 + 1));
        v23 = Src;
        CacheNewGroupKey(a3, v37[10] & 0xF, DOT11_CIPHER_KEY_TYPE_BIGTK, a3->McastMgmtCipher, v37[11], Src);
        LODWORD(v14) = (_DWORD)v14 + 1;
        numMloBIGtkSubelements = v5->numMloBIGtkSubelements;
        v36 = Size_4 + 1;
        Size_4 = v36;
        if ( v36 >= numMloBIGtkSubelements )
          goto LABEL_60;
      }
      v16 = -1073741595;
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_64;
      v46 = (unsigned __int8)v54;
      v47 = 502;
    }
  }
  WPP_SF_dDDd(v45->AttachedDevice, v47, v46, v27, v46, v26, CipherKeyStructLength);
LABEL_64:
  v14 = v55;
LABEL_65:
  v17 = v51;
LABEL_66:
  if ( Src )
  {
    v41 = (ULONG *)(Src - 16);
    v42 = (struct _NPAGED_LOOKASIDE_LIST *)*((_QWORD *)Src - 2);
    if ( v42 )
      ExFreeToNPagedLookasideList(v42, v41);
    else
      ExFreePoolWithTag(v41, v41[2]);
  }
  if ( v14 )
    memset(v14, 0, v17);
  if ( v6 )
  {
    if ( *(_QWORD *)&v6[-1].uResponseIEsLength )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&v6[-1].uResponseIEsLength, &v6[-1].uResponseIEsLength);
    else
      ExFreePoolWithTag(&v6[-1].uResponseIEsLength, *(_DWORD *)v6[-1].ucResponseIEsOld);
  }
  return v16;
}

```

## disassembly

```asm
0x14004e208  mov     rax, rsp
0x14004e20b  mov     [rax+18h], rbx
0x14004e20f  mov     [rax+20h], r9
0x14004e213  mov     [rax+10h], rdx
0x14004e217  mov     [rax+8], rcx
0x14004e21b  push    rbp
0x14004e21c  push    rsi
0x14004e21d  push    rdi
0x14004e21e  push    r12
0x14004e220  push    r13
0x14004e222  push    r14
0x14004e224  push    r15
0x14004e226  mov     rbp, rsp
0x14004e229  sub     rsp, 80h
0x14004e230  mov     r14, [rbp+arg_20]
0x14004e234  xor     r15d, r15d
0x14004e237  mov     rsi, r8
0x14004e23a  mov     rdi, rdx
0x14004e23d  cmp     [r14+0DEh], r15b
0x14004e244  jnz     short loc_14004E277
0x14004e246  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e24d  lea     rdi, WPP_GLOBAL_Control
0x14004e254  cmp     rcx, rdi
0x14004e257  jz      loc_14004E326
0x14004e25d  mov     rcx, [rcx+18h]
0x14004e261  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004e268  mov     edx, 1E7h
0x14004e26d  call    WPP_SF_
0x14004e272  jmp     loc_14004E326
0x14004e277  mov     ecx, [r8+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004e27b  call    ?GetGTKCipherKeyLength@@YAKW4_DOT11_CIPHER_ALGORITHM@@@Z; GetGTKCipherKeyLength(_DOT11_CIPHER_ALGORITHM)
0x14004e280  mov     dword ptr [rbp+Size+4], eax
0x14004e283  test    al, al
0x14004e285  jnz     short loc_14004E2A9
0x14004e287  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e28e  lea     rdi, WPP_GLOBAL_Control
0x14004e295  cmp     rcx, rdi
0x14004e298  jz      loc_14004E326
0x14004e29e  mov     r9d, [rsi+14h]
0x14004e2a2  mov     edx, 1E8h
0x14004e2a7  jmp     short loc_14004E2DD
0x14004e2a9  mov     ecx, [rsi+18h]; enum _DOT11_CIPHER_ALGORITHM
0x14004e2ac  call    ?GetIGTKCipherKeyLength@@YAKW4_DOT11_CIPHER_ALGORITHM@@@Z; GetIGTKCipherKeyLength(_DOT11_CIPHER_ALGORITHM)
0x14004e2b1  mov     [rbp+var_24], eax
0x14004e2b4  cmp     [r14+108h], r15b
0x14004e2bb  jbe     short loc_14004E2EF
0x14004e2bd  test    al, al
0x14004e2bf  jnz     short loc_14004E330
0x14004e2c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e2c8  lea     rdi, WPP_GLOBAL_Control
0x14004e2cf  cmp     rcx, rdi
0x14004e2d2  jz      short loc_14004E326
0x14004e2d4  mov     r9d, [rsi+18h]
0x14004e2d8  mov     edx, 1E9h
0x14004e2dd  mov     rcx, [rcx+18h]
0x14004e2e1  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004e2e8  call    WPP_SF_d
0x14004e2ed  jmp     short loc_14004E326
0x14004e2ef  movzx   eax, byte ptr [r14+138h]
0x14004e2f7  test    al, al
0x14004e2f9  jz      short loc_14004E330
0x14004e2fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e302  lea     rdi, WPP_GLOBAL_Control
0x14004e309  cmp     rcx, rdi
0x14004e30c  jz      short loc_14004E326
0x14004e30e  mov     rcx, [rcx+18h]
0x14004e312  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004e319  mov     r9d, eax
0x14004e31c  mov     edx, 1EAh
0x14004e321  call    WPP_SF_d
0x14004e326  mov     eax, 0C00000E5h
0x14004e32b  jmp     loc_14004EC02
0x14004e330  lea     r8, [rbp+var_18]; unsigned __int8 **
0x14004e334  mov     dword ptr [rbp+Size], r15d
0x14004e338  lea     rdx, [rbp+Size]; unsigned int *
0x14004e33c  mov     [rbp+var_18], r15
0x14004e340  mov     rcx, r14; struct NWF_FT_CONTEXT *
0x14004e343  mov     r12, r15
0x14004e346  call    ?AllocateBuffersForFTGroupKeys@@YAJPEAUNWF_FT_CONTEXT@@PEAKPEAPEAE@Z; AllocateBuffersForFTGroupKeys(NWF_FT_CONTEXT *,ulong *,uchar * *)
0x14004e34b  mov     ebx, eax
0x14004e34d  test    eax, eax
0x14004e34f  jns     short loc_14004E388
0x14004e351  mov     esi, r15d
0x14004e354  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e35b  lea     rdi, WPP_GLOBAL_Control
0x14004e362  cmp     rcx, rdi
0x14004e365  jz      short loc_14004E37F
0x14004e367  mov     rcx, [rcx+18h]
0x14004e36b  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004e372  mov     edx, 1EBh
0x14004e377  mov     r9d, eax
0x14004e37a  call    WPP_SF_d
0x14004e37f  mov     r15, [rbp+arg_20]
0x14004e383  jmp     loc_14004EA61
0x14004e388  movzx   eax, byte ptr [r14+0DEh]
0x14004e390  movzx   ecx, byte ptr [r14+138h]
0x14004e398  add     ecx, eax
0x14004e39a  movzx   eax, byte ptr [r14+108h]
0x14004e3a2  add     ecx, eax
0x14004e3a4  imul    edx, ecx, 49h ; 'I'
0x14004e3a7  add     edx, 8
0x14004e3aa  mov     [rbp+var_30], edx
0x14004e3ad  lea     r13d, [rdx+158h]
0x14004e3b4  lea     eax, [r13+10h]
0x14004e3b8  cmp     eax, 10h
0x14004e3bb  jb      short loc_14004E42A
0x14004e3bd  mov     ecx, 40h ; '@'
0x14004e3c2  cmp     eax, ecx
0x14004e3c4  ja      short loc_14004E3CF
0x14004e3c6  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004e3cd  jmp     short loc_14004E3FD
0x14004e3cf  cmp     eax, 100h
0x14004e3d4  ja      short loc_14004E3DF
0x14004e3d6  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004e3dd  jmp     short loc_14004E3FD
0x14004e3df  cmp     eax, 400h
0x14004e3e4  ja      short loc_14004E3EF
0x14004e3e6  lea     rbx, Lookaside
0x14004e3ed  jmp     short loc_14004E3FD
0x14004e3ef  cmp     eax, 800h
0x14004e3f4  ja      short loc_14004E40E
0x14004e3f6  lea     rbx, stru_1400B31C0
0x14004e3fd  mov     rcx, rbx; Lookaside
0x14004e400  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004e407  nop     dword ptr [rax+rax+00h]
0x14004e40c  jmp     short loc_14004E425
0x14004e40e  mov     edx, eax
0x14004e410  mov     r8d, 7A697377h
0x14004e416  mov     rbx, r15
0x14004e419  call    cs:__imp_ExAllocatePool2
0x14004e420  nop     dword ptr [rax+rax+00h]
0x14004e425  test    rax, rax
0x14004e428  jnz     short loc_14004E463
0x14004e42a  mov     ebx, 0C000009Ah
0x14004e42f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e436  lea     rdi, WPP_GLOBAL_Control
0x14004e43d  cmp     rcx, rdi
0x14004e440  jz      loc_14004EA5E
0x14004e446  mov     rcx, [rcx+18h]
0x14004e44a  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004e451  mov     edx, 1ECh
0x14004e456  mov     r9d, r13d
0x14004e459  call    WPP_SF_d
0x14004e45e  jmp     loc_14004EA5E
0x14004e463  xor     ecx, ecx
0x14004e465  mov     r8d, r13d; Size
0x14004e468  lea     r15, [rax+10h]
0x14004e46c  mov     dword ptr [rbp+arg_20], ecx
0x14004e46f  mov     rcx, r15; void *
0x14004e472  mov     [rax], rbx
0x14004e475  xor     edx, edx; Val
0x14004e477  mov     dword ptr [rax+8], 7A697377h
0x14004e47e  call    memset
0x14004e483  mov     rbx, [rbp+var_18]
0x14004e487  lea     rcx, [r15+130h]
0x14004e48e  lea     rax, [rcx+28h]
0x14004e492  mov     [rcx+10h], rdi
0x14004e496  mov     [rcx], rax
0x14004e499  lea     rdi, WPP_GLOBAL_Control
0x14004e4a0  xor     edx, edx
0x14004e4a2  mov     [rbp+var_20], rax
0x14004e4a6  mov     eax, [rbp+var_30]
0x14004e4a9  mov     [rcx+8], eax
0x14004e4ac  mov     [rcx+20h], edx
0x14004e4af  cmp     [r14+0DEh], dl
0x14004e4b6  jbe     loc_14004E676
0x14004e4bc  mov     r10d, [rsi+14h]
0x14004e4c0  mov     ecx, r10d; enum _DOT11_CIPHER_ALGORITHM
0x14004e4c3  mov     eax, r12d
0x14004e4c6  mov     r13, [r14+rax*8+0E0h]
0x14004e4ce  movzx   r9d, byte ptr [r13+5]
0x14004e4d3  mov     edx, r9d; unsigned int
0x14004e4d6  call    ?ValidateAndGetCipherKeyStructLength@@YAGW4_DOT11_CIPHER_ALGORITHM@@K@Z; ValidateAndGetCipherKeyStructLength(_DOT11_CIPHER_ALGORITHM,ulong)
0x14004e4db  mov     edx, dword ptr [rbp+Size+4]
0x14004e4de  mov     word ptr [rbp+arg_20], ax
0x14004e4e2  cmp     dl, r9b
0x14004e4e5  jnz     loc_14004EABB
0x14004e4eb  test    ax, ax
0x14004e4ee  jz      loc_14004EABB
0x14004e4f4  mov     r8d, dword ptr [rbp+Size]; Size
0x14004e4f8  xor     edx, edx; Val
0x14004e4fa  mov     rcx, rbx; void *
0x14004e4fd  call    memset
0x14004e502  mov     ecx, [rsi+408h]
0x14004e508  lea     r8, [r13+0Eh]
0x14004e50c  movzx   r9d, byte ptr [r13+1]
0x14004e511  add     rcx, 414h
0x14004e518  mov     edx, [rsi+40Ch]
0x14004e51e  add     rcx, rsi
0x14004e521  sub     r9d, 0Ch
0x14004e525  mov     [rsp+80h+var_60], rbx
0x14004e52a  call    AES_UNWRAP
0x14004e52f  mov     ebx, eax
0x14004e531  test    eax, eax
0x14004e533  js      loc_14004EA95
0x14004e539  mov     rbx, [rbp+var_20]
0x14004e53d  xor     edx, edx; Val
0x14004e53f  mov     eax, r12d
0x14004e542  add     rbx, 8
0x14004e546  imul    rax, 49h ; 'I'
0x14004e54a  lea     r8d, [rdx+49h]; Size
0x14004e54e  add     rbx, rax
0x14004e551  mov     rcx, rbx; void *
0x14004e554  mov     [rbp+var_10], rbx
0x14004e558  call    memset
0x14004e55d  mov     al, [r13+4]
0x14004e561  lea     r9, [r13+6]; unsigned __int8 *
0x14004e565  mov     rdx, [rbp+arg_18]
0x14004e569  and     al, 0Fh
0x14004e56b  mov     [rbx], al
0x14004e56d  add     rdx, 10h; unsigned __int8 (*)[6]
0x14004e571  movzx   ecx, byte ptr [r13+5]
0x14004e576  lea     rax, [rbx+1]
0x14004e57a  movzx   r8d, byte ptr [r13+2]
0x14004e57f  mov     [rsp+80h+var_38], rax; struct DOT11_CIPHER_DEFAULT_KEY_VALUE *
0x14004e584  and     r8d, 3; unsigned int
0x14004e588  mov     rax, [rbp+var_18]
0x14004e58c  mov     [rsp+80h+Src], rax; Src
0x14004e591  movzx   eax, word ptr [rbp+arg_20]
0x14004e595  mov     dword ptr [rsp+80h+var_50], ecx; Size
0x14004e599  mov     ecx, [rsi+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004e59c  mov     word ptr [rsp+80h+var_58], ax; unsigned __int16
0x14004e5a1  mov     [rsp+80h+var_60], 0; unsigned __int8 *
0x14004e5aa  call    ?FillCipherDefaultKeyValues@@YAHW4_DOT11_CIPHER_ALGORITHM@@PEAY05$$CBEKPEBE2GK2KPEAUDOT11_CIPHER_DEFAULT_KEY_VALUE@@@Z; FillCipherDefaultKeyValues(_DOT11_CIPHER_ALGORITHM,uchar const (*)[6],ulong,uchar const *,uchar const *,ushort,ulong,uchar const *,ulong,DOT11_CIPHER_DEFAULT_KEY_VALUE *)
0x14004e5af  mov     dword ptr [rbp+arg_20], eax
0x14004e5b2  mov     ebx, eax
0x14004e5b4  test    eax, eax
0x14004e5b6  js      loc_14004EA26
0x14004e5bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e5c3  cmp     rcx, rdi
0x14004e5c6  jz      short loc_14004E609
0x14004e5c8  mov     rax, [r13+6]
0x14004e5cc  movzx   r8d, byte ptr [r13+2]
0x14004e5d1  movzx   edx, byte ptr [r13+5]
0x14004e5d6  and     r8d, 3
0x14004e5da  movzx   r9d, byte ptr [r13+4]
0x14004e5df  mov     rcx, [rcx+18h]
0x14004e5e3  and     r9d, 0Fh
0x14004e5e7  mov     qword ptr [rsp+80h+var_40], rax; unsigned int
0x14004e5ec  mov     eax, [rsi+14h]
0x14004e5ef  mov     dword ptr [rsp+80h+Src], r8d
0x14004e5f4  mov     dword ptr [rsp+80h+var_50], edx
0x14004e5f8  mov     dword ptr [rsp+80h+var_58], eax
0x14004e5fc  mov     dword ptr [rsp+80h+var_60], r9d
0x14004e601  mov     r9d, r12d
0x14004e604  call    WPP_SF_ddDddi
0x14004e609  mov     rcx, [rbp+var_10]
0x14004e60d  mov     r8d, 2; enum _DOT11_CIPHER_KEY_TYPE
0x14004e613  movzx   eax, byte ptr [r13+5]
0x14004e618  mov     rbx, [rbp+var_18]
0x14004e61c  mov     r9d, [rsi+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004e620  movzx   edx, byte ptr [rcx]; unsigned int
0x14004e623  mov     rcx, rsi; struct _NWF_KEY_CONTEXT *
0x14004e626  mov     [rsp+80h+var_58], rbx; unsigned __int8 *
0x14004e62b  mov     word ptr [rsp+80h+var_60], ax; unsigned __int16
0x14004e630  call    ?CacheNewGroupKey@@YAHPEAU_NWF_KEY_CONTEXT@@KW4_DOT11_CIPHER_KEY_TYPE@@W4_DOT11_CIPHER_ALGORITHM@@GPEAE@Z; CacheNewGroupKey(_NWF_KEY_CONTEXT *,ulong,_DOT11_CIPHER_KEY_TYPE,_DOT11_CIPHER_ALGORITHM,ushort,uchar *)
0x14004e635  inc     r12d
0x14004e638  test    cs:byte_1400B2804, 8
0x14004e63f  jz      short loc_14004E663
0x14004e641  movzx   eax, byte ptr [r13+5]
0x14004e646  movzx   r9d, byte ptr [r13+2]
0x14004e64b  mov     r8, [rbp+arg_0]
0x14004e64f  and     r9d, 3
0x14004e653  mov     dword ptr [rsp+80h+var_50], eax
0x14004e657  mov     eax, [rsi+14h]
0x14004e65a  mov     dword ptr [rsp+80h+var_60], eax
0x14004e65e  call    McTemplateK0qquq_EtwWriteTransfer
0x14004e663  movzx   eax, byte ptr [r14+0DEh]
0x14004e66b  cmp     r12d, eax
0x14004e66e  jb      loc_14004E4BC
0x14004e674  xor     edx, edx
0x14004e676  mov     ecx, edx
0x14004e678  mov     dword ptr [rbp+Size+4], edx
0x14004e67b  cmp     [r14+108h], dl
0x14004e682  jbe     loc_14004E808
0x14004e688  mov     r10d, [rsi+18h]
0x14004e68c  mov     eax, ecx
0x14004e68e  mov     ecx, r10d; enum _DOT11_CIPHER_ALGORITHM
0x14004e691  mov     r13, [r14+rax*8+110h]
0x14004e699  movzx   r9d, byte ptr [r13+0Bh]
0x14004e69e  mov     edx, r9d; unsigned int
0x14004e6a1  call    ?ValidateAndGetCipherKeyStructLength@@YAGW4_DOT11_CIPHER_ALGORITHM@@K@Z; ValidateAndGetCipherKeyStructLength(_DOT11_CIPHER_ALGORITHM,ulong)
0x14004e6a6  mov     edx, [rbp+var_24]
0x14004e6a9  mov     word ptr [rbp+arg_20], ax
0x14004e6ad  cmp     dl, r9b
0x14004e6b0  jnz     loc_14004EB25
0x14004e6b6  test    ax, ax
0x14004e6b9  jz      loc_14004EB25
0x14004e6bf  mov     r8d, dword ptr [rbp+Size]; Size
0x14004e6c3  xor     edx, edx; Val
0x14004e6c5  mov     rcx, rbx; void *
0x14004e6c8  call    memset
0x14004e6cd  mov     ecx, [rsi+408h]
0x14004e6d3  lea     r8, [r13+0Ch]
0x14004e6d7  movzx   r9d, byte ptr [r13+1]
0x14004e6dc  add     rcx, 414h
0x14004e6e3  mov     edx, [rsi+40Ch]
0x14004e6e9  add     rcx, rsi
0x14004e6ec  sub     r9d, 0Ah
0x14004e6f0  mov     [rsp+80h+var_60], rbx
  ... truncated ...
```
