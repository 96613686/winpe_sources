# InstallMloGroupKeys(_VELAN *,_NWF_KEY_CONTEXT *,NWF_EAPOL_RSNA_KEY_DESC *,DOT11_MAC_STATE_ENTRY *,NWF_RSN_KEY_DATA *)

- ea: `0x14004d464`
- end: `0x14004dd8a`
- name: `?InstallMloGroupKeys@@YAJPEAU_VELAN@@PEAU_NWF_KEY_CONTEXT@@PEAUNWF_EAPOL_RSNA_KEY_DESC@@PEAUDOT11_MAC_STATE_ENTRY@@PEAUNWF_RSN_KEY_DATA@@@Z`
- size: `2342`
- prototype: `__int64 __fastcall(struct _VELAN *, struct _NWF_KEY_CONTEXT *, struct NWF_EAPOL_RSNA_KEY_DESC *, struct DOT11_MAC_STATE_ENTRY *, struct NWF_RSN_KEY_DATA *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004c97c`

## callees

- `0x1400160e0`
- `0x1400165c4`
- `0x14001a320`
- `0x14002ffb4`
- `0x140040a18`
- `0x140047858`
- `0x14004d464`
- `0x14004f50c`
- `0x14004f55c`
- `0x1400500b0`
- `0x140052924`
- `0x140053160`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d516`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004d516`
- `ntoskrnl!ExAllocatePool2` at `0x14004d52c`
- `ntoskrnl!ExAllocatePool2` at `0x14004d52c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004dca1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004dca1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004dcb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004dcb5`

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
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_12;
  }
  p_DeviceQueue = 0;
  Pool2 = (char *)ExAllocatePool2(64, v12, 2053731191, a4);
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
          WPP_e90d411d816e312466897e39e745b158_Traceguids,
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
    WPP_e90d411d816e312466897e39e745b158_Traceguids,
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
0x14004d464  mov     rax, rsp
0x14004d467  mov     [rax+10h], rbx
0x14004d46b  mov     [rax+20h], r9
0x14004d46f  mov     [rax+18h], r8
0x14004d473  mov     [rax+8], rcx
0x14004d477  push    rbp
0x14004d478  push    rsi
0x14004d479  push    rdi
0x14004d47a  push    r12
0x14004d47c  push    r13
0x14004d47e  push    r14
0x14004d480  push    r15
0x14004d482  sub     rsp, 80h
0x14004d489  mov     rsi, [rsp+0B8h+arg_20]
0x14004d491  mov     rbp, rdx
0x14004d494  xor     r12d, r12d
0x14004d497  mov     r14, rcx
0x14004d49a  mov     edx, [rsi+88h]
0x14004d4a0  add     edx, [rsi+98h]
0x14004d4a6  add     edx, [rsi+0A8h]
0x14004d4ac  jnz     short loc_14004D4B8
0x14004d4ae  mov     eax, 0C00000E5h
0x14004d4b3  jmp     loc_14004DD6E
0x14004d4b8  imul    edi, edx, 49h ; 'I'
0x14004d4bb  add     edi, 8
0x14004d4be  lea     eax, [rdi+168h]
0x14004d4c4  cmp     eax, 10h
0x14004d4c7  jb      loc_14004DD67
0x14004d4cd  mov     ecx, 40h ; '@'
0x14004d4d2  mov     r15d, 7A697377h
0x14004d4d8  cmp     eax, ecx
0x14004d4da  ja      short loc_14004D4E5
0x14004d4dc  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004d4e3  jmp     short loc_14004D513
0x14004d4e5  cmp     eax, 100h
0x14004d4ea  ja      short loc_14004D4F5
0x14004d4ec  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004d4f3  jmp     short loc_14004D513
0x14004d4f5  cmp     eax, 400h
0x14004d4fa  ja      short loc_14004D505
0x14004d4fc  lea     rbx, Lookaside
0x14004d503  jmp     short loc_14004D513
0x14004d505  cmp     eax, 800h
0x14004d50a  ja      short loc_14004D524
0x14004d50c  lea     rbx, stru_1400B0180
0x14004d513  mov     rcx, rbx; Lookaside
0x14004d516  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004d51d  nop     dword ptr [rax+rax+00h]
0x14004d522  jmp     short loc_14004D538
0x14004d524  mov     edx, eax
0x14004d526  mov     r8d, r15d
0x14004d529  mov     rbx, r12
0x14004d52c  call    cs:__imp_ExAllocatePool2
0x14004d533  nop     dword ptr [rax+rax+00h]
0x14004d538  test    rax, rax
0x14004d53b  jz      loc_14004DD67
0x14004d541  mov     [rax+8], r15d
0x14004d545  xor     edx, edx; Val
0x14004d547  lea     r15, [rax+10h]
0x14004d54b  mov     r8d, edi
0x14004d54e  mov     rcx, r15; void *
0x14004d551  mov     [rax], rbx
0x14004d554  add     r8, 158h; Size
0x14004d55b  mov     [rsp+0B8h+var_48], r15
0x14004d560  call    memset
0x14004d565  lea     rcx, [r15+130h]
0x14004d56c  xor     r9d, r9d
0x14004d56f  lea     rax, [rcx+28h]
0x14004d573  mov     [rcx+10h], r14
0x14004d577  mov     [rcx], rax
0x14004d57a  lea     r10, WPP_GLOBAL_Control
0x14004d581  mov     [rsp+0B8h+var_50], rcx
0x14004d586  mov     r14d, r9d
0x14004d589  mov     [rcx+8], edi
0x14004d58c  mov     [rcx+20h], r9d
0x14004d590  cmp     r14d, [rsi+88h]
0x14004d597  jnb     loc_14004D7C0
0x14004d59d  movzx   r13d, word ptr [rsi]
0x14004d5a1  mov     r11d, [rbp+14h]
0x14004d5a5  mov     edx, r13d; unsigned int
0x14004d5a8  mov     ecx, r11d; enum _DOT11_CIPHER_ALGORITHM
0x14004d5ab  call    ?ValidateAndGetCipherKeyStructLength@@YAGW4_DOT11_CIPHER_ALGORITHM@@K@Z; ValidateAndGetCipherKeyStructLength(_DOT11_CIPHER_ALGORITHM,ulong)
0x14004d5b0  mov     word ptr [rsp+0B8h+arg_20], ax
0x14004d5b8  test    ax, ax
0x14004d5bb  jz      loc_14004D797
0x14004d5c1  mov     rcx, [rsi+90h]
0x14004d5c8  mov     edx, r14d
0x14004d5cb  mov     r15, [rcx+rdx*8]
0x14004d5cf  mov     rdx, [rbp+58h]; struct DOT11_CONNECTION_INFO *
0x14004d5d3  movzx   ebx, byte ptr [r15+6]
0x14004d5d8  mov     cl, bl
0x14004d5da  shr     cl, 4; unsigned __int8
0x14004d5dd  call    ?IsLinkIdInAssociatedLinks@@YAHEPEAUDOT11_CONNECTION_INFO@@@Z; IsLinkIdInAssociatedLinks(uchar,DOT11_CONNECTION_INFO *)
0x14004d5e2  mov     dword ptr [rsp+0B8h+var_68], eax
0x14004d5e6  mov     r8d, eax
0x14004d5e9  test    eax, eax
0x14004d5eb  jz      loc_14004D731
0x14004d5f1  lea     rax, [r15+0Dh]
0x14004d5f5  mov     edx, ebx
0x14004d5f7  mov     [rsp+0B8h+var_90], rax; unsigned __int8 *
0x14004d5fc  mov     r9d, r11d; enum _DOT11_CIPHER_ALGORITHM
0x14004d5ff  shr     edx, 4; unsigned int
0x14004d602  mov     r8d, 2; enum _DOT11_CIPHER_KEY_TYPE
0x14004d608  mov     rcx, rbp; struct _NWF_KEY_CONTEXT *
0x14004d60b  mov     word ptr [rsp+0B8h+var_98], r13w; unsigned __int16
0x14004d611  call    ?IsNewGroupKeyDifferent@@YAHPEAU_NWF_KEY_CONTEXT@@KW4_DOT11_CIPHER_KEY_TYPE@@W4_DOT11_CIPHER_ALGORITHM@@GPEAE@Z; IsNewGroupKeyDifferent(_NWF_KEY_CONTEXT *,ulong,_DOT11_CIPHER_KEY_TYPE,_DOT11_CIPHER_ALGORITHM,ushort,uchar *)
0x14004d616  test    eax, eax
0x14004d618  jz      loc_14004D724
0x14004d61e  mov     eax, r12d
0x14004d621  xor     edx, edx; Val
0x14004d623  imul    rbx, rax, 49h ; 'I'
0x14004d627  lea     r8d, [rdx+49h]; Size
0x14004d62b  add     rbx, [rsp+0B8h+var_50]
0x14004d630  lea     rcx, [rbx+30h]; void *
0x14004d634  call    memset
0x14004d639  mov     al, [r15+6]
0x14004d63d  lea     r9, [r15+7]
0x14004d641  mov     r10, [rsp+0B8h+arg_10]
0x14004d649  lea     r13, [r15+0Dh]
0x14004d64d  mov     rdx, [rsp+0B8h+arg_18]
0x14004d655  shr     al, 4
0x14004d658  add     rdx, 10h; unsigned __int8 (*)[6]
0x14004d65c  mov     [rbx+30h], al
0x14004d65f  lea     rax, [rbx+31h]
0x14004d663  movzx   ecx, word ptr [rsi]
0x14004d666  movzx   r8d, byte ptr [r15+6]
0x14004d66b  mov     [rsp+0B8h+var_70], rax; struct DOT11_CIPHER_DEFAULT_KEY_VALUE *
0x14004d670  and     r8d, 3; unsigned int
0x14004d674  movzx   eax, word ptr [rsp+0B8h+arg_20]
0x14004d67c  mov     [rsp+0B8h+Src], r13; Src
0x14004d681  mov     dword ptr [rsp+0B8h+Size], ecx; Size
0x14004d685  mov     ecx, [rbp+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004d688  mov     word ptr [rsp+0B8h+var_90], ax; unsigned __int16
0x14004d68d  mov     [rsp+0B8h+var_98], r9; unsigned __int8 *
0x14004d692  lea     r9, [r10+3Dh]; unsigned __int8 *
0x14004d696  call    ?FillCipherDefaultKeyValues@@YAHW4_DOT11_CIPHER_ALGORITHM@@PEAY05$$CBEKPEBE2GK2KPEAUDOT11_CIPHER_DEFAULT_KEY_VALUE@@@Z; FillCipherDefaultKeyValues(_DOT11_CIPHER_ALGORITHM,uchar const (*)[6],ulong,uchar const *,uchar const *,ushort,ulong,uchar const *,ulong,DOT11_CIPHER_DEFAULT_KEY_VALUE *)
0x14004d69b  mov     ebx, eax
0x14004d69d  test    eax, eax
0x14004d69f  js      loc_14004D776
0x14004d6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d6ac  lea     rax, WPP_GLOBAL_Control
0x14004d6b3  cmp     rcx, rax
0x14004d6b6  jz      short loc_14004D6F8
0x14004d6b8  movzx   r9d, byte ptr [r15+6]
0x14004d6bd  mov     edx, 10Eh
0x14004d6c2  movzx   r8d, word ptr [rsi]
0x14004d6c6  and     r9d, 3
0x14004d6ca  mov     rax, [rsp+0B8h+arg_10]
0x14004d6d2  mov     rcx, [rcx+18h]
0x14004d6d6  mov     rax, [rax+3Dh]
0x14004d6da  mov     [rsp+0B8h+Src], rax
0x14004d6df  mov     eax, [rbp+14h]
0x14004d6e2  mov     dword ptr [rsp+0B8h+Size], r9d
0x14004d6e7  mov     r9d, r12d
0x14004d6ea  mov     dword ptr [rsp+0B8h+var_90], r8d
0x14004d6ef  mov     dword ptr [rsp+0B8h+var_98], eax
0x14004d6f3  call    WPP_SF_dDddi
0x14004d6f8  movzx   edx, byte ptr [r15+6]
0x14004d6fd  mov     r8d, 2; enum _DOT11_CIPHER_KEY_TYPE
0x14004d703  movzx   eax, word ptr [rsi]
0x14004d706  mov     rcx, rbp; struct _NWF_KEY_CONTEXT *
0x14004d709  mov     r9d, [rbp+14h]; enum _DOT11_CIPHER_ALGORITHM
0x14004d70d  shr     edx, 4; unsigned int
0x14004d710  mov     [rsp+0B8h+var_90], r13; unsigned __int8 *
0x14004d715  mov     word ptr [rsp+0B8h+var_98], ax; unsigned __int16
0x14004d71a  call    ?CacheNewGroupKey@@YAHPEAU_NWF_KEY_CONTEXT@@KW4_DOT11_CIPHER_KEY_TYPE@@W4_DOT11_CIPHER_ALGORITHM@@GPEAE@Z; CacheNewGroupKey(_NWF_KEY_CONTEXT *,ulong,_DOT11_CIPHER_KEY_TYPE,_DOT11_CIPHER_ALGORITHM,ushort,uchar *)
0x14004d71f  inc     r12d
0x14004d722  jmp     short loc_14004D764
0x14004d724  mov     r11d, [rbp+14h]
0x14004d728  mov     bl, [r15+6]
0x14004d72c  mov     r8d, dword ptr [rsp+0B8h+var_68]
0x14004d731  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d738  lea     r10, WPP_GLOBAL_Control
0x14004d73f  cmp     rcx, r10
0x14004d742  jz      short loc_14004D76B
0x14004d744  mov     rcx, [rcx+18h]
0x14004d748  mov     edx, 10Ch
0x14004d74d  movzx   eax, bl
0x14004d750  mov     r9d, r8d
0x14004d753  shr     eax, 4
0x14004d756  mov     dword ptr [rsp+0B8h+var_90], r11d
0x14004d75b  mov     dword ptr [rsp+0B8h+var_98], eax
0x14004d75f  call    WPP_SF_DDd
0x14004d764  lea     r10, WPP_GLOBAL_Control
0x14004d76b  inc     r14d
0x14004d76e  xor     r9d, r9d
0x14004d771  jmp     loc_14004D590
0x14004d776  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d77d  lea     rax, WPP_GLOBAL_Control
0x14004d784  cmp     rcx, rax
0x14004d787  jz      loc_14004DC69
0x14004d78d  mov     edx, 10Dh
0x14004d792  jmp     loc_14004DC48
0x14004d797  mov     ebx, 0C00000E5h
0x14004d79c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d7a3  cmp     rcx, r10
0x14004d7a6  jz      loc_14004DC69
0x14004d7ac  mov     dword ptr [rsp+0B8h+var_90], r13d
0x14004d7b1  mov     edx, 10Bh
0x14004d7b6  mov     dword ptr [rsp+0B8h+var_98], r11d
0x14004d7bb  jmp     loc_14004DC56
0x14004d7c0  lea     rbx, [rbp+18h]
0x14004d7c4  mov     r14d, r9d
0x14004d7c7  mov     [rsp+0B8h+var_58], rbx
0x14004d7cc  lea     r13, [rsi+2]
0x14004d7d0  cmp     r14d, [rsi+98h]
0x14004d7d7  jnb     loc_14004DA13
0x14004d7dd  lea     rbx, [rbp+18h]
0x14004d7e1  mov     ecx, [rbx]; enum _DOT11_CIPHER_ALGORITHM
0x14004d7e3  lea     r13, [rsi+2]
0x14004d7e7  movzx   eax, word ptr [r13+0]
0x14004d7ec  mov     edx, eax; unsigned int
0x14004d7ee  mov     dword ptr [rsp+0B8h+var_68], eax
0x14004d7f2  mov     [rsp+0B8h+var_58], rbx
0x14004d7f7  mov     [rsp+0B8h+var_64], ecx
0x14004d7fb  call    ?ValidateAndGetCipherKeyStructLength@@YAGW4_DOT11_CIPHER_ALGORITHM@@K@Z; ValidateAndGetCipherKeyStructLength(_DOT11_CIPHER_ALGORITHM,ulong)
0x14004d800  mov     word ptr [rsp+0B8h+arg_20], ax
0x14004d808  test    ax, ax
0x14004d80b  jz      loc_14004D9F4
0x14004d811  mov     rcx, [rsi+0A0h]
0x14004d818  mov     edx, r14d
0x14004d81b  mov     r15, [rcx+rdx*8]
0x14004d81f  mov     rdx, [rbp+58h]; struct DOT11_CONNECTION_INFO *
0x14004d823  movzx   r11d, byte ptr [r15+0Eh]
0x14004d828  mov     cl, r11b
0x14004d82b  shr     cl, 4; unsigned __int8
0x14004d82e  call    ?IsLinkIdInAssociatedLinks@@YAHEPEAUDOT11_CONNECTION_INFO@@@Z; IsLinkIdInAssociatedLinks(uchar,DOT11_CONNECTION_INFO *)
0x14004d833  mov     dword ptr [rsp+0B8h+var_60], eax
0x14004d837  mov     r9d, eax
0x14004d83a  test    eax, eax
0x14004d83c  jz      loc_14004D98C
0x14004d842  mov     ecx, dword ptr [rsp+0B8h+var_68]
0x14004d846  lea     rax, [r15+0Fh]
0x14004d84a  mov     r9d, [rsp+0B8h+var_64]; enum _DOT11_CIPHER_ALGORITHM
0x14004d84f  mov     edx, r11d
0x14004d852  mov     [rsp+0B8h+var_90], rax; unsigned __int8 *
0x14004d857  mov     r8d, 3; enum _DOT11_CIPHER_KEY_TYPE
0x14004d85d  mov     word ptr [rsp+0B8h+var_98], cx; unsigned __int16
0x14004d862  mov     rcx, rbp; struct _NWF_KEY_CONTEXT *
0x14004d865  shr     edx, 4; unsigned int
0x14004d868  call    ?IsNewGroupKeyDifferent@@YAHPEAU_NWF_KEY_CONTEXT@@KW4_DOT11_CIPHER_KEY_TYPE@@W4_DOT11_CIPHER_ALGORITHM@@GPEAE@Z; IsNewGroupKeyDifferent(_NWF_KEY_CONTEXT *,ulong,_DOT11_CIPHER_KEY_TYPE,_DOT11_CIPHER_ALGORITHM,ushort,uchar *)
0x14004d86d  test    eax, eax
0x14004d86f  jz      loc_14004D983
0x14004d875  mov     eax, r12d
0x14004d878  xor     edx, edx; Val
0x14004d87a  imul    rbx, rax, 49h ; 'I'
0x14004d87e  lea     r8d, [rdx+49h]; Size
0x14004d882  add     rbx, [rsp+0B8h+var_50]
0x14004d887  lea     rcx, [rbx+30h]; void *
0x14004d88b  call    memset
0x14004d890  mov     al, [r15+0Eh]
0x14004d894  lea     r9, [r15+8]
0x14004d898  mov     r10, [rsp+0B8h+arg_10]
0x14004d8a0  mov     rdx, [rsp+0B8h+arg_18]
0x14004d8a8  shr     al, 4
0x14004d8ab  add     rdx, 10h; unsigned __int8 (*)[6]
0x14004d8af  mov     [rbx+30h], al
0x14004d8b2  lea     rax, [rbx+31h]
0x14004d8b6  movzx   ecx, word ptr [r13+0]
0x14004d8bb  movzx   r8d, word ptr [r15+6]; unsigned int
0x14004d8c0  mov     [rsp+0B8h+var_70], rax; struct DOT11_CIPHER_DEFAULT_KEY_VALUE *
0x14004d8c5  lea     rax, [r15+0Fh]
0x14004d8c9  mov     [rsp+0B8h+Src], rax; Src
0x14004d8ce  movzx   eax, word ptr [rsp+0B8h+arg_20]
0x14004d8d6  mov     dword ptr [rsp+0B8h+Size], ecx; Size
0x14004d8da  mov     rcx, [rsp+0B8h+var_58]
0x14004d8df  mov     word ptr [rsp+0B8h+var_90], ax; unsigned __int16
0x14004d8e4  mov     [rsp+0B8h+var_98], r9; unsigned __int8 *
0x14004d8e9  lea     r9, [r10+3Dh]; unsigned __int8 *
0x14004d8ed  mov     ecx, [rcx]; enum _DOT11_CIPHER_ALGORITHM
0x14004d8ef  call    ?FillCipherDefaultKeyValues@@YAHW4_DOT11_CIPHER_ALGORITHM@@PEAY05$$CBEKPEBE2GK2KPEAUDOT11_CIPHER_DEFAULT_KEY_VALUE@@@Z; FillCipherDefaultKeyValues(_DOT11_CIPHER_ALGORITHM,uchar const (*)[6],ulong,uchar const *,uchar const *,ushort,ulong,uchar const *,ulong,DOT11_CIPHER_DEFAULT_KEY_VALUE *)
0x14004d8f4  mov     ebx, eax
0x14004d8f6  test    eax, eax
0x14004d8f8  js      loc_14004D9D3
0x14004d8fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d905  lea     rax, WPP_GLOBAL_Control
0x14004d90c  cmp     rcx, rax
0x14004d90f  jz      short loc_14004D94D
0x14004d911  movzx   r9d, word ptr [rsi]
0x14004d915  mov     edx, 112h
0x14004d91a  movzx   r8d, word ptr [r15+6]
0x14004d91f  mov     rax, [rsp+0B8h+arg_10]
0x14004d927  mov     rcx, [rcx+18h]
0x14004d92b  mov     rax, [rax+3Dh]
0x14004d92f  mov     [rsp+0B8h+Src], rax
0x14004d934  mov     eax, [rbp+14h]
0x14004d937  mov     dword ptr [rsp+0B8h+Size], r8d
0x14004d93c  mov     dword ptr [rsp+0B8h+var_90], r9d
0x14004d941  mov     r9d, r12d
0x14004d944  mov     dword ptr [rsp+0B8h+var_98], eax
0x14004d948  call    WPP_SF_dDddi
0x14004d94d  movzx   edx, byte ptr [r15+0Eh]
0x14004d952  lea     rax, [r15+0Fh]
0x14004d956  mov     rbx, [rsp+0B8h+var_58]
0x14004d95b  mov     r8d, 3; enum _DOT11_CIPHER_KEY_TYPE
0x14004d961  mov     [rsp+0B8h+var_90], rax; unsigned __int8 *
0x14004d966  mov     rcx, rbp; struct _NWF_KEY_CONTEXT *
0x14004d969  movzx   eax, word ptr [r13+0]
0x14004d96e  shr     edx, 4; unsigned int
0x14004d971  mov     r9d, [rbx]; enum _DOT11_CIPHER_ALGORITHM
  ... truncated ...
```
