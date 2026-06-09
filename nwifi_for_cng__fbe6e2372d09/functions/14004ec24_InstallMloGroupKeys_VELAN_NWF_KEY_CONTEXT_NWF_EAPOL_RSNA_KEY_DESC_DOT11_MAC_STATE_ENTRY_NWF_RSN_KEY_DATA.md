# InstallMloGroupKeys(_VELAN *,_NWF_KEY_CONTEXT *,NWF_EAPOL_RSNA_KEY_DESC *,DOT11_MAC_STATE_ENTRY *,NWF_RSN_KEY_DATA *)

- ea: `0x14004ec24`
- end: `0x14004f54a`
- name: `?InstallMloGroupKeys@@YAJPEAU_VELAN@@PEAU_NWF_KEY_CONTEXT@@PEAUNWF_EAPOL_RSNA_KEY_DESC@@PEAUDOT11_MAC_STATE_ENTRY@@PEAUNWF_RSN_KEY_DATA@@@Z`
- size: `2342`
- prototype: `int(struct _VELAN *, struct _NWF_KEY_CONTEXT *, struct NWF_EAPOL_RSNA_KEY_DESC *, struct DOT11_MAC_STATE_ENTRY *, struct NWF_RSN_KEY_DATA *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004e13c`

## callees

- `0x1400160d0`
- `0x1400165b4`
- `0x14001a320`
- `0x140030244`
- `0x1400414b4`
- `0x140048ad0`
- `0x14004ec24`
- `0x140050cd4`
- `0x140050d24`
- `0x140051878`
- `0x140054144`
- `0x140054980`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ecd6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ecd6`
- `ntoskrnl!ExAllocatePool2` at `0x14004ecec`
- `ntoskrnl!ExAllocatePool2` at `0x14004ecec`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004f461`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004f461`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f475`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f475`

## pseudocode

```c
__int64 __fastcall InstallMloGroupKeys(
        struct _VELAN *a1,
        struct _NWF_KEY_CONTEXT *a2,
        struct NWF_EAPOL_RSNA_KEY_DESC *a3,
        struct DOT11_MAC_STATE_ENTRY *a4,
        struct NWF_RSN_KEY_DATA *a5)
{
  struct NWF_RSN_KEY_DATA *v5; // rsi
  unsigned int v7; // r12d
  int v9; // edx
  unsigned int v11; // edi
  unsigned int v12; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  char *Pool2; // rax
  char *v15; // r15
  unsigned int v16; // r14d
  unsigned int v17; // r13d
  struct _DEVICE_OBJECT *v18; // r10
  int v19; // r11d
  __int64 v20; // r15
  unsigned int v21; // ebx
  enum _DOT11_CIPHER_ALGORITHM McastCipher; // r11d
  __int64 v23; // r8
  char *v24; // rbx
  int v25; // ebx
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  _DOT11_CIPHER_ALGORITHM *p_McastMgmtCipher; // rbx
  unsigned __int16 *v29; // r13
  struct _DEVICE_OBJECT *v30; // r10
  __int64 v31; // r15
  unsigned int v32; // r11d
  __int64 v33; // r9
  char *v34; // rbx
  enum _DOT11_CIPHER_ALGORITHM v35; // ebx
  struct _DEVICE_OBJECT *v36; // r10
  __int64 v37; // r15
  unsigned int v38; // r11d
  __int64 v39; // r9
  char *v40; // rbx
  struct _NDIS_OID_REQUEST *Request; // r8
  size_t Size; // [rsp+30h] [rbp-88h]
  unsigned int v43; // [rsp+40h] [rbp-78h]
  unsigned __int16 v44[2]; // [rsp+50h] [rbp-68h]
  unsigned __int16 v45; // [rsp+50h] [rbp-68h]
  enum _DOT11_CIPHER_ALGORITHM McastMgmtCipher; // [rsp+54h] [rbp-64h]
  enum _DOT11_CIPHER_ALGORITHM v47; // [rsp+54h] [rbp-64h]
  unsigned __int16 v48[2]; // [rsp+58h] [rbp-60h]
  unsigned __int16 v49; // [rsp+58h] [rbp-60h]
  enum _DOT11_CIPHER_ALGORITHM *v50; // [rsp+60h] [rbp-58h]
  _QWORD *v51; // [rsp+68h] [rbp-50h]
  struct DOT11_NDIS_REQUEST *v52; // [rsp+70h] [rbp-48h]

  v5 = a5;
  v7 = 0;
  v9 = *((_DWORD *)a5 + 42) + *((_DWORD *)a5 + 38) + *((_DWORD *)a5 + 34);
  if ( !v9 )
    return 3221225701LL;
  v11 = 73 * v9 + 8;
  v12 = 73 * v9 + 368;
  if ( v12 < 0x10 )
    return (unsigned int)-1073741670;
  if ( v12 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_12:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_14;
  }
  if ( v12 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_12;
  }
  if ( v12 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_12;
  }
  if ( v12 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_12;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v12, 2053731191);
LABEL_14:
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  *((_DWORD *)Pool2 + 2) = 2053731191;
  v15 = Pool2 + 16;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  v52 = (struct DOT11_NDIS_REQUEST *)(Pool2 + 16);
  memset(Pool2 + 16, 0, v11 + 344LL);
  *((_QWORD *)v15 + 40) = a1;
  *((_QWORD *)v15 + 38) = v15 + 344;
  v51 = v15 + 304;
  v16 = 0;
  *((_DWORD *)v15 + 78) = v11;
  *((_DWORD *)v15 + 84) = 0;
  while ( v16 < *((_DWORD *)v5 + 34) )
  {
    v17 = *(unsigned __int16 *)v5;
    LOWORD(a5) = ValidateAndGetCipherKeyStructLength(a2->McastCipher, v17);
    if ( !(_WORD)a5 )
    {
      v25 = -1073741595;
      if ( WPP_GLOBAL_Control != v18 )
        WPP_SF_lll(
          WPP_GLOBAL_Control->AttachedDevice,
          267,
          WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
          v16,
          v19,
          v17);
      goto LABEL_67;
    }
    v20 = *(_QWORD *)(*((_QWORD *)v5 + 18) + 8LL * v16);
    v21 = *(unsigned __int8 *)(v20 + 6);
    *(_DWORD *)v44 = IsLinkIdInAssociatedLinks(*(_BYTE *)(v20 + 6) >> 4, a2->pConnectionInfo);
    v23 = *(unsigned int *)v44;
    if ( !*(_DWORD *)v44 )
      goto LABEL_25;
    if ( !IsNewGroupKeyDifferent(
            a2,
            v21 >> 4,
            DOT11_CIPHER_KEY_TYPE_GROUP_KEY,
            McastCipher,
            v17,
            (unsigned __int8 *)(v20 + 13)) )
    {
      McastCipher = a2->McastCipher;
      LOBYTE(v21) = *(_BYTE *)(v20 + 6);
      v23 = *(unsigned int *)v44;
LABEL_25:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_DDd(
          WPP_GLOBAL_Control->AttachedDevice,
          268,
          v23,
          (unsigned int)v23,
          (unsigned __int8)v21 >> 4,
          McastCipher);
      goto LABEL_27;
    }
    v24 = (char *)v51 + 73 * v7;
    memset(v24 + 48, 0, 0x49u);
    v24[48] = *(_BYTE *)(v20 + 6) >> 4;
    LODWORD(Size) = *(unsigned __int16 *)v5;
    v25 = FillCipherDefaultKeyValues(
            a2->McastCipher,
            (const unsigned __int8 (*)[6])a4->MacHashEntry.MacKey,
            *(_BYTE *)(v20 + 6) & 3,
            (const unsigned __int8 *)a3 + 61,
            (const unsigned __int8 *)(v20 + 7),
            (unsigned __int16)a5,
            Size,
            (const unsigned __int8 *)(v20 + 13),
            v43,
            (struct DOT11_CIPHER_DEFAULT_KEY_VALUE *)(v24 + 49));
    if ( v25 < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v27 = 269;
        goto LABEL_66;
      }
      goto LABEL_67;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_dDddi(
        WPP_GLOBAL_Control->AttachedDevice,
        270,
        *(unsigned __int16 *)v5,
        v7,
        a2->McastCipher,
        *(unsigned __int16 *)v5,
        *(_BYTE *)(v20 + 6) & 3,
        *(_QWORD *)((char *)a3 + 61));
    CacheNewGroupKey(
      a2,
      *(unsigned __int8 *)(v20 + 6) >> 4,
      DOT11_CIPHER_KEY_TYPE_GROUP_KEY,
      a2->McastCipher,
      *(_WORD *)v5,
      (unsigned __int8 *)(v20 + 13));
    ++v7;
LABEL_27:
    ++v16;
  }
  p_McastMgmtCipher = &a2->McastMgmtCipher;
  v16 = 0;
  v50 = &a2->McastMgmtCipher;
  v29 = (unsigned __int16 *)((char *)v5 + 2);
  while ( v16 < *((_DWORD *)v5 + 38) )
  {
    p_McastMgmtCipher = &a2->McastMgmtCipher;
    v29 = (unsigned __int16 *)((char *)v5 + 2);
    v45 = *((_WORD *)v5 + 1);
    v50 = &a2->McastMgmtCipher;
    McastMgmtCipher = a2->McastMgmtCipher;
    LOWORD(a5) = ValidateAndGetCipherKeyStructLength(McastMgmtCipher, v45);
    if ( !(_WORD)a5 )
    {
      v25 = -1073741595;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != v30 )
      {
        v27 = 271;
        goto LABEL_66;
      }
      goto LABEL_67;
    }
    v31 = *(_QWORD *)(*((_QWORD *)v5 + 20) + 8LL * v16);
    *(_DWORD *)v48 = IsLinkIdInAssociatedLinks(*(_BYTE *)(v31 + 14) >> 4, a2->pConnectionInfo);
    v33 = *(unsigned int *)v48;
    if ( !*(_DWORD *)v48 )
      goto LABEL_42;
    if ( !IsNewGroupKeyDifferent(
            a2,
            v32 >> 4,
            DOT11_CIPHER_KEY_TYPE_IGTK,
            McastMgmtCipher,
            v45,
            (unsigned __int8 *)(v31 + 15)) )
    {
      LOBYTE(v32) = *(_BYTE *)(v31 + 14);
      v33 = *(unsigned int *)v48;
LABEL_42:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_DDd(
          WPP_GLOBAL_Control->AttachedDevice,
          272,
          (unsigned __int8)v32 >> 4,
          v33,
          (unsigned __int8)v32 >> 4,
          a2->McastCipher);
      goto LABEL_44;
    }
    v34 = (char *)v51 + 73 * v7;
    memset(v34 + 48, 0, 0x49u);
    v34[48] = *(_BYTE *)(v31 + 14) >> 4;
    LODWORD(Size) = *v29;
    v25 = FillCipherDefaultKeyValues(
            *v50,
            (const unsigned __int8 (*)[6])a4->MacHashEntry.MacKey,
            *(unsigned __int16 *)(v31 + 6),
            (const unsigned __int8 *)a3 + 61,
            (const unsigned __int8 *)(v31 + 8),
            (unsigned __int16)a5,
            Size,
            (const unsigned __int8 *)(v31 + 15),
            v43,
            (struct DOT11_CIPHER_DEFAULT_KEY_VALUE *)(v34 + 49));
    if ( v25 < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v27 = 273;
        goto LABEL_66;
      }
      goto LABEL_67;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_dDddi(
        WPP_GLOBAL_Control->AttachedDevice,
        274,
        *(unsigned __int16 *)(v31 + 6),
        v7,
        a2->McastCipher,
        *(unsigned __int16 *)v5,
        *(unsigned __int16 *)(v31 + 6),
        *(_QWORD *)((char *)a3 + 61));
    p_McastMgmtCipher = &a2->McastMgmtCipher;
    CacheNewGroupKey(
      a2,
      *(unsigned __int8 *)(v31 + 14) >> 4,
      DOT11_CIPHER_KEY_TYPE_IGTK,
      *v50,
      *v29,
      (unsigned __int8 *)(v31 + 15));
    ++v7;
LABEL_44:
    ++v16;
  }
  v16 = 0;
  while ( 1 )
  {
    if ( v16 >= *((_DWORD *)v5 + 42) )
    {
      *((_DWORD *)v51 + 11) = 0;
      *((_DWORD *)v51 + 10) = v7;
      Dot11BuildNdisRequest(
        v52,
        1u,
        0xE010305u,
        v11,
        v51 + 5,
        (void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *))FreeOidRequestBuffer,
        v51,
        0);
      _InterlockedIncrement((volatile signed __int32 *)&a4->uRefCnt);
      v51[3] = a4;
      Request = v52->Request;
      LODWORD(a5) = 0;
      Dot11Request((int *)&a5, a1->pAdapt, Request);
      v25 = (int)a5;
      if ( (_DWORD)a5 == 259 )
        return 0;
      else
        Dot11RequestComplete(a1->pAdapt, v52->Request, (int)a5);
      return (unsigned int)v25;
    }
    v35 = *p_McastMgmtCipher;
    v49 = *v29;
    LOWORD(a5) = ValidateAndGetCipherKeyStructLength(v35, *v29);
    if ( !(_WORD)a5 )
      break;
    v37 = *(_QWORD *)(*((_QWORD *)v5 + 22) + 8LL * v16);
    v47 = (unsigned int)IsLinkIdInAssociatedLinks(*(_BYTE *)(v37 + 14) >> 4, a2->pConnectionInfo);
    v39 = (unsigned int)v47;
    if ( v47 == DOT11_CIPHER_ALGO_NONE )
      goto LABEL_59;
    if ( !IsNewGroupKeyDifferent(a2, v38 >> 4, DOT11_CIPHER_KEY_TYPE_BIGTK, v35, v49, (unsigned __int8 *)(v37 + 15)) )
    {
      LOBYTE(v38) = *(_BYTE *)(v37 + 14);
      v39 = (unsigned int)v47;
LABEL_59:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_DDd(
          WPP_GLOBAL_Control->AttachedDevice,
          276,
          (unsigned __int8)v38 >> 4,
          v39,
          (unsigned __int8)v38 >> 4,
          a2->McastCipher);
      goto LABEL_61;
    }
    v40 = (char *)v51 + 73 * v7;
    memset(v40 + 48, 0, 0x49u);
    v40[48] = *(_BYTE *)(v37 + 14) >> 4;
    LODWORD(Size) = *v29;
    v25 = FillCipherDefaultKeyValues(
            *v50,
            (const unsigned __int8 (*)[6])a4->MacHashEntry.MacKey,
            *(unsigned __int16 *)(v37 + 6),
            (const unsigned __int8 *)a3 + 61,
            (const unsigned __int8 *)(v37 + 8),
            (unsigned __int16)a5,
            Size,
            (const unsigned __int8 *)(v37 + 15),
            v43,
            (struct DOT11_CIPHER_DEFAULT_KEY_VALUE *)(v40 + 49));
    if ( v25 < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_67;
      v27 = 277;
      goto LABEL_66;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_dDddi(
        WPP_GLOBAL_Control->AttachedDevice,
        278,
        *(unsigned __int16 *)(v37 + 6),
        v7,
        a2->McastCipher,
        *(unsigned __int16 *)v5,
        *(unsigned __int16 *)(v37 + 6),
        *(_QWORD *)((char *)a3 + 61));
    CacheNewGroupKey(
      a2,
      *(unsigned __int8 *)(v37 + 14) >> 4,
      DOT11_CIPHER_KEY_TYPE_BIGTK,
      *v50,
      *v29,
      (unsigned __int8 *)(v37 + 15));
    ++v7;
LABEL_61:
    ++v16;
    p_McastMgmtCipher = &a2->McastMgmtCipher;
    v50 = &a2->McastMgmtCipher;
    v29 = (unsigned __int16 *)((char *)v5 + 2);
  }
  v25 = -1073741595;
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == v36 )
    goto LABEL_67;
  v27 = 275;
LABEL_66:
  WPP_SF_lll(
    v26->AttachedDevice,
    v27,
    WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
    v16,
    a2->McastCipher,
    *(unsigned __int16 *)v5);
LABEL_67:
  if ( v51 != (_QWORD *)-40LL )
    memset(v51 + 5, 0, v11);
  if ( v52 )
  {
    if ( v52[-1].pCompletion )
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v52[-1].pCompletion, &v52[-1].pCompletion);
    else
      ExFreePoolWithTag(&v52[-1].pCompletion, (ULONG)v52[-1].pVElan);
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x14004ec24  mov     rax, rsp
0x14004ec27  mov     [rax+10h], rbx
0x14004ec2b  mov     [rax+20h], r9
0x14004ec2f  mov     [rax+18h], r8
0x14004ec33  mov     [rax+8], rcx
0x14004ec37  push    rbp
0x14004ec38  push    rsi
0x14004ec39  push    rdi
0x14004ec3a  push    r12
0x14004ec3c  push    r13
0x14004ec3e  push    r14
0x14004ec40  push    r15
0x14004ec42  sub     rsp, 80h
0x14004ec49  mov     rsi, [rsp+0B8h+arg_20]
0x14004ec51  mov     rbp, rdx
0x14004ec54  xor     r12d, r12d
0x14004ec57  mov     r14, rcx
0x14004ec5a  mov     edx, [rsi+88h]
0x14004ec60  add     edx, [rsi+98h]
0x14004ec66  add     edx, [rsi+0A8h]
0x14004ec6c  jnz     short loc_14004EC78
0x14004ec6e  mov     eax, 0C00000E5h
0x14004ec73  jmp     loc_14004F52E
0x14004ec78  imul    edi, edx, 49h ; 'I'
0x14004ec7b  add     edi, 8
0x14004ec7e  lea     eax, [rdi+168h]
0x14004ec84  cmp     eax, 10h
0x14004ec87  jb      loc_14004F527
0x14004ec8d  mov     ecx, 40h ; '@'
0x14004ec92  mov     r15d, 7A697377h
0x14004ec98  cmp     eax, ecx
0x14004ec9a  ja      short loc_14004ECA5
0x14004ec9c  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004eca3  jmp     short loc_14004ECD3
0x14004eca5  cmp     eax, 100h
0x14004ecaa  ja      short loc_14004ECB5
0x14004ecac  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004ecb3  jmp     short loc_14004ECD3
0x14004ecb5  cmp     eax, 400h
0x14004ecba  ja      short loc_14004ECC5
0x14004ecbc  lea     rbx, Lookaside
0x14004ecc3  jmp     short loc_14004ECD3
0x14004ecc5  cmp     eax, 800h
0x14004ecca  ja      short loc_14004ECE4
0x14004eccc  lea     rbx, stru_1400B31C0
0x14004ecd3  mov     rcx, rbx; Lookaside
0x14004ecd6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004ecdd  nop     dword ptr [rax+rax+00h]
0x14004ece2  jmp     short loc_14004ECF8
0x14004ece4  mov     edx, eax
0x14004ece6  mov     r8d, r15d
0x14004ece9  mov     rbx, r12
0x14004ecec  call    cs:__imp_ExAllocatePool2
0x14004ecf3  nop     dword ptr [rax+rax+00h]
0x14004ecf8  test    rax, rax
0x14004ecfb  jz      loc_14004F527
0x14004ed01  mov     [rax+8], r15d
0x14004ed05  xor     edx, edx; Val
0x14004ed07  lea     r15, [rax+10h]
0x14004ed0b  mov     r8d, edi
0x14004ed0e  mov     rcx, r15; void *
0x14004ed11  mov     [rax], rbx
0x14004ed14  add     r8, 158h; Size
0x14004ed1b  mov     [rsp+0B8h+var_48], r15
0x14004ed20  call    memset
0x14004ed25  lea     rcx, [r15+130h]
0x14004ed2c  xor     r9d, r9d
0x14004ed2f  lea     rax, [rcx+28h]
0x14004ed33  mov     [rcx+10h], r14
0x14004ed37  mov     [rcx], rax
0x14004ed3a  lea     r10, WPP_GLOBAL_Control
0x14004ed41  mov     [rsp+0B8h+var_50], rcx
0x14004ed46  mov     r14d, r9d
0x14004ed49  mov     [rcx+8], edi
0x14004ed4c  mov     [rcx+20h], r9d
0x14004ed50  cmp     r14d, [rsi+88h]
0x14004ed57  jnb     loc_14004EF80
0x14004ed5d  movzx   r13d, word ptr [rsi]
0x14004ed61  mov     r11d, [rbp+14h]
0x14004ed65  mov     edx, r13d; unsigned int
0x14004ed68  mov     ecx, r11d; enum _DOT11_CIPHER_ALGORITHM
0x14004ed6b  call    ?ValidateAndGetCipherKeyStructLength@@YAGW4_DOT11_CIPHER_ALGORITHM@@K@Z; ValidateAndGetCipherKeyStructLength(_DOT11_CIPHER_ALGORITHM,ulong)
0x14004ed70  mov     word ptr [rsp+0B8h+arg_20], ax
0x14004ed78  test    ax, ax
0x14004ed7b  jz      loc_14004EF57
0x14004ed81  mov     rcx, [rsi+90h]
0x14004ed88  mov     edx, r14d
0x14004ed8b  mov     r15, [rcx+rdx*8]
0x14004ed8f  mov     rdx, [rbp+58h]; struct DOT11_CONNECTION_INFO *
0x14004ed93  movzx   ebx, byte ptr [r15+6]
0x14004ed98  mov     cl, bl
0x14004ed9a  shr     cl, 4; unsigned __int8
0x14004ed9d  call    ?IsLinkIdInAssociatedLinks@@YAHEPEAUDOT11_CONNECTION_INFO@@@Z; IsLinkIdInAssociatedLinks(uchar,DOT11_CONNECTION_INFO *)
0x14004eda2  mov     dword ptr [rsp+0B8h+var_68], eax
0x14004eda6  mov     r8d, eax
0x14004eda9  test    eax, eax
0x14004edab  jz      loc_14004EEF1
0x14004edb1  lea     rax, [r15+0Dh]
0x14004edb5  mov     edx, ebx
0x14004edb7  mov     [rsp+0B8h+var_90], rax; unsigned __int8 *
0x14004edbc  mov     r9d, r11d; enum _DOT11_CIPHER_ALGORITHM
0x14004edbf  shr     edx, 4; unsigned int
0x14004edc2  mov     r8d, 2; enum _DOT11_CIPHER_KEY_TYPE
0x14004edc8  mov     rcx, rbp; struct _NWF_KEY_CONTEXT *
0x14004edcb  mov     word ptr [rsp+0B8h+var_98], r13w; unsigned __int16
0x14004edd1  call    ?IsNewGroupKeyDifferent@@YAHPEAU_NWF_KEY_CONTEXT@@KW4_DOT11_CIPHER_KEY_TYPE@@W4_DOT11_CIPHER_ALGORITHM@@GPEAE@Z; IsNewGroupKeyDifferent(_NWF_KEY_CONTEXT *,ulong,_DOT11_CIPHER_KEY_TYPE,_DOT11_CIPHER_ALGORITHM,ushort,uchar *)
0x14004edd6  test    eax, eax
0x14004edd8  jz      loc_14004EEE4
0x14004edde  mov     eax, r12d
0x14004ede1  xor     edx, edx; Val
0x14004ede3  imul    rbx, rax, 49h ; 'I'
0x14004ede7  lea     r8d, [rdx+49h]; Size
0x14004edeb  add     rbx, [rsp+0B8h+var_50]
0x14004edf0  lea     rcx, [rbx+30h]; void *
0x14004edf4  call    memset
0x14004edf9  mov     al, [r15+6]
0x14004edfd  lea     r9, [r15+7]
0x14004ee01  mov     r10, [rsp+0B8h+arg_10]
0x14004ee09  lea     r13, [r15+0Dh]
0x14004ee0d  mov     rdx, [rsp+0B8h+arg_18]
0x14004ee15  shr     al, 4
0x14004ee18  add     rdx, 10h; unsigned __int8 (*)[6]
0x14004ee1c  mov     [rbx+30h], al
0x14004ee1f  lea     rax, [rbx+31h]
0x14004ee23  movzx   ecx, word ptr [rsi]
0x14004ee26  movzx   r8d, byte ptr [r15+6]
0x14004ee2b  mov     [rsp+0B8h+var_70], rax; struct DOT11_CIPHER_DEFAULT_KEY_VALUE *
0x14004ee30  and     r8d, 3; unsigned int
0x14004ee34  movzx   eax, word ptr [rsp+0B8h+arg_20]
0x14004ee3c  mov     [rsp+0B8h+Src], r13; Src
0x14004ee41  mov     dword ptr [rsp+0B8h+Size], ecx; Size
0x14004ee45  mov     ecx, [rbp+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004ee48  mov     word ptr [rsp+0B8h+var_90], ax; unsigned __int16
0x14004ee4d  mov     [rsp+0B8h+var_98], r9; unsigned __int8 *
0x14004ee52  lea     r9, [r10+3Dh]; unsigned __int8 *
0x14004ee56  call    ?FillCipherDefaultKeyValues@@YAHW4_DOT11_CIPHER_ALGORITHM@@PEAY05$$CBEKPEBE2GK2KPEAUDOT11_CIPHER_DEFAULT_KEY_VALUE@@@Z; FillCipherDefaultKeyValues(_DOT11_CIPHER_ALGORITHM,uchar const (*)[6],ulong,uchar const *,uchar const *,ushort,ulong,uchar const *,ulong,DOT11_CIPHER_DEFAULT_KEY_VALUE *)
0x14004ee5b  mov     ebx, eax
0x14004ee5d  test    eax, eax
0x14004ee5f  js      loc_14004EF36
0x14004ee65  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ee6c  lea     rax, WPP_GLOBAL_Control
0x14004ee73  cmp     rcx, rax
0x14004ee76  jz      short loc_14004EEB8
0x14004ee78  movzx   r9d, byte ptr [r15+6]
0x14004ee7d  mov     edx, 10Eh
0x14004ee82  movzx   r8d, word ptr [rsi]
0x14004ee86  and     r9d, 3
0x14004ee8a  mov     rax, [rsp+0B8h+arg_10]
0x14004ee92  mov     rcx, [rcx+18h]
0x14004ee96  mov     rax, [rax+3Dh]
0x14004ee9a  mov     [rsp+0B8h+Src], rax
0x14004ee9f  mov     eax, [rbp+14h]
0x14004eea2  mov     dword ptr [rsp+0B8h+Size], r9d
0x14004eea7  mov     r9d, r12d
0x14004eeaa  mov     dword ptr [rsp+0B8h+var_90], r8d
0x14004eeaf  mov     dword ptr [rsp+0B8h+var_98], eax
0x14004eeb3  call    WPP_SF_dDddi
0x14004eeb8  movzx   edx, byte ptr [r15+6]
0x14004eebd  mov     r8d, 2; enum _DOT11_CIPHER_KEY_TYPE
0x14004eec3  movzx   eax, word ptr [rsi]
0x14004eec6  mov     rcx, rbp; struct _NWF_KEY_CONTEXT *
0x14004eec9  mov     r9d, [rbp+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004eecd  shr     edx, 4; unsigned int
0x14004eed0  mov     [rsp+0B8h+var_90], r13; unsigned __int8 *
0x14004eed5  mov     word ptr [rsp+0B8h+var_98], ax; unsigned __int16
0x14004eeda  call    ?CacheNewGroupKey@@YAHPEAU_NWF_KEY_CONTEXT@@KW4_DOT11_CIPHER_KEY_TYPE@@W4_DOT11_CIPHER_ALGORITHM@@GPEAE@Z; CacheNewGroupKey(_NWF_KEY_CONTEXT *,ulong,_DOT11_CIPHER_KEY_TYPE,_DOT11_CIPHER_ALGORITHM,ushort,uchar *)
0x14004eedf  inc     r12d
0x14004eee2  jmp     short loc_14004EF24
0x14004eee4  mov     r11d, [rbp+14h]
0x14004eee8  mov     bl, [r15+6]
0x14004eeec  mov     r8d, dword ptr [rsp+0B8h+var_68]
0x14004eef1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004eef8  lea     r10, WPP_GLOBAL_Control
0x14004eeff  cmp     rcx, r10
0x14004ef02  jz      short loc_14004EF2B
0x14004ef04  mov     rcx, [rcx+18h]
0x14004ef08  mov     edx, 10Ch
0x14004ef0d  movzx   eax, bl
0x14004ef10  mov     r9d, r8d
0x14004ef13  shr     eax, 4
0x14004ef16  mov     dword ptr [rsp+0B8h+var_90], r11d
0x14004ef1b  mov     dword ptr [rsp+0B8h+var_98], eax
0x14004ef1f  call    WPP_SF_DDd
0x14004ef24  lea     r10, WPP_GLOBAL_Control
0x14004ef2b  inc     r14d
0x14004ef2e  xor     r9d, r9d
0x14004ef31  jmp     loc_14004ED50
0x14004ef36  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ef3d  lea     rax, WPP_GLOBAL_Control
0x14004ef44  cmp     rcx, rax
0x14004ef47  jz      loc_14004F429
0x14004ef4d  mov     edx, 10Dh
0x14004ef52  jmp     loc_14004F408
0x14004ef57  mov     ebx, 0C00000E5h
0x14004ef5c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ef63  cmp     rcx, r10
0x14004ef66  jz      loc_14004F429
0x14004ef6c  mov     dword ptr [rsp+0B8h+var_90], r13d
0x14004ef71  mov     edx, 10Bh
0x14004ef76  mov     dword ptr [rsp+0B8h+var_98], r11d
0x14004ef7b  jmp     loc_14004F416
0x14004ef80  lea     rbx, [rbp+18h]
0x14004ef84  mov     r14d, r9d
0x14004ef87  mov     [rsp+0B8h+var_58], rbx
0x14004ef8c  lea     r13, [rsi+2]
0x14004ef90  cmp     r14d, [rsi+98h]
0x14004ef97  jnb     loc_14004F1D3
0x14004ef9d  lea     rbx, [rbp+18h]
0x14004efa1  mov     ecx, [rbx]; enum _DOT11_CIPHER_ALGORITHM
0x14004efa3  lea     r13, [rsi+2]
0x14004efa7  movzx   eax, word ptr [r13+0]
0x14004efac  mov     edx, eax; unsigned int
0x14004efae  mov     dword ptr [rsp+0B8h+var_68], eax
0x14004efb2  mov     [rsp+0B8h+var_58], rbx
0x14004efb7  mov     [rsp+0B8h+var_64], ecx
0x14004efbb  call    ?ValidateAndGetCipherKeyStructLength@@YAGW4_DOT11_CIPHER_ALGORITHM@@K@Z; ValidateAndGetCipherKeyStructLength(_DOT11_CIPHER_ALGORITHM,ulong)
0x14004efc0  mov     word ptr [rsp+0B8h+arg_20], ax
0x14004efc8  test    ax, ax
0x14004efcb  jz      loc_14004F1B4
0x14004efd1  mov     rcx, [rsi+0A0h]
0x14004efd8  mov     edx, r14d
0x14004efdb  mov     r15, [rcx+rdx*8]
0x14004efdf  mov     rdx, [rbp+58h]; struct DOT11_CONNECTION_INFO *
0x14004efe3  movzx   r11d, byte ptr [r15+0Eh]
0x14004efe8  mov     cl, r11b
0x14004efeb  shr     cl, 4; unsigned __int8
0x14004efee  call    ?IsLinkIdInAssociatedLinks@@YAHEPEAUDOT11_CONNECTION_INFO@@@Z; IsLinkIdInAssociatedLinks(uchar,DOT11_CONNECTION_INFO *)
0x14004eff3  mov     dword ptr [rsp+0B8h+var_60], eax
0x14004eff7  mov     r9d, eax
0x14004effa  test    eax, eax
0x14004effc  jz      loc_14004F14C
0x14004f002  mov     ecx, dword ptr [rsp+0B8h+var_68]
0x14004f006  lea     rax, [r15+0Fh]
0x14004f00a  mov     r9d, [rsp+0B8h+var_64]; enum _DOT11_CIPHER_ALGORITHM
0x14004f00f  mov     edx, r11d
0x14004f012  mov     [rsp+0B8h+var_90], rax; unsigned __int8 *
0x14004f017  mov     r8d, 3; enum _DOT11_CIPHER_KEY_TYPE
0x14004f01d  mov     word ptr [rsp+0B8h+var_98], cx; unsigned __int16
0x14004f022  mov     rcx, rbp; struct _NWF_KEY_CONTEXT *
0x14004f025  shr     edx, 4; unsigned int
0x14004f028  call    ?IsNewGroupKeyDifferent@@YAHPEAU_NWF_KEY_CONTEXT@@KW4_DOT11_CIPHER_KEY_TYPE@@W4_DOT11_CIPHER_ALGORITHM@@GPEAE@Z; IsNewGroupKeyDifferent(_NWF_KEY_CONTEXT *,ulong,_DOT11_CIPHER_KEY_TYPE,_DOT11_CIPHER_ALGORITHM,ushort,uchar *)
0x14004f02d  test    eax, eax
0x14004f02f  jz      loc_14004F143
0x14004f035  mov     eax, r12d
0x14004f038  xor     edx, edx; Val
0x14004f03a  imul    rbx, rax, 49h ; 'I'
0x14004f03e  lea     r8d, [rdx+49h]; Size
0x14004f042  add     rbx, [rsp+0B8h+var_50]
0x14004f047  lea     rcx, [rbx+30h]; void *
0x14004f04b  call    memset
0x14004f050  mov     al, [r15+0Eh]
0x14004f054  lea     r9, [r15+8]
0x14004f058  mov     r10, [rsp+0B8h+arg_10]
0x14004f060  mov     rdx, [rsp+0B8h+arg_18]
0x14004f068  shr     al, 4
0x14004f06b  add     rdx, 10h; unsigned __int8 (*)[6]
0x14004f06f  mov     [rbx+30h], al
0x14004f072  lea     rax, [rbx+31h]
0x14004f076  movzx   ecx, word ptr [r13+0]
0x14004f07b  movzx   r8d, word ptr [r15+6]; unsigned int
0x14004f080  mov     [rsp+0B8h+var_70], rax; struct DOT11_CIPHER_DEFAULT_KEY_VALUE *
0x14004f085  lea     rax, [r15+0Fh]
0x14004f089  mov     [rsp+0B8h+Src], rax; Src
0x14004f08e  movzx   eax, word ptr [rsp+0B8h+arg_20]
0x14004f096  mov     dword ptr [rsp+0B8h+Size], ecx; Size
0x14004f09a  mov     rcx, [rsp+0B8h+var_58]
0x14004f09f  mov     word ptr [rsp+0B8h+var_90], ax; unsigned __int16
0x14004f0a4  mov     [rsp+0B8h+var_98], r9; unsigned __int8 *
0x14004f0a9  lea     r9, [r10+3Dh]; unsigned __int8 *
0x14004f0ad  mov     ecx, [rcx]; enum _DOT11_CIPHER_ALGORITHM
0x14004f0af  call    ?FillCipherDefaultKeyValues@@YAHW4_DOT11_CIPHER_ALGORITHM@@PEAY05$$CBEKPEBE2GK2KPEAUDOT11_CIPHER_DEFAULT_KEY_VALUE@@@Z; FillCipherDefaultKeyValues(_DOT11_CIPHER_ALGORITHM,uchar const (*)[6],ulong,uchar const *,uchar const *,ushort,ulong,uchar const *,ulong,DOT11_CIPHER_DEFAULT_KEY_VALUE *)
0x14004f0b4  mov     ebx, eax
0x14004f0b6  test    eax, eax
0x14004f0b8  js      loc_14004F193
0x14004f0be  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f0c5  lea     rax, WPP_GLOBAL_Control
0x14004f0cc  cmp     rcx, rax
0x14004f0cf  jz      short loc_14004F10D
0x14004f0d1  movzx   r9d, word ptr [rsi]
0x14004f0d5  mov     edx, 112h
0x14004f0da  movzx   r8d, word ptr [r15+6]
0x14004f0df  mov     rax, [rsp+0B8h+arg_10]
0x14004f0e7  mov     rcx, [rcx+18h]
0x14004f0eb  mov     rax, [rax+3Dh]
0x14004f0ef  mov     [rsp+0B8h+Src], rax
0x14004f0f4  mov     eax, [rbp+14h]
0x14004f0f7  mov     dword ptr [rsp+0B8h+Size], r8d
0x14004f0fc  mov     dword ptr [rsp+0B8h+var_90], r9d
0x14004f101  mov     r9d, r12d
0x14004f104  mov     dword ptr [rsp+0B8h+var_98], eax
0x14004f108  call    WPP_SF_dDddi
0x14004f10d  movzx   edx, byte ptr [r15+0Eh]
0x14004f112  lea     rax, [r15+0Fh]
0x14004f116  mov     rbx, [rsp+0B8h+var_58]
0x14004f11b  mov     r8d, 3; enum _DOT11_CIPHER_KEY_TYPE
0x14004f121  mov     [rsp+0B8h+var_90], rax; unsigned __int8 *
0x14004f126  mov     rcx, rbp; struct _NWF_KEY_CONTEXT *
0x14004f129  movzx   eax, word ptr [r13+0]
0x14004f12e  shr     edx, 4; unsigned int
0x14004f131  mov     r9d, [rbx]; enum _DOT11_CIPHER_ALGORITHM
  ... truncated ...
```
