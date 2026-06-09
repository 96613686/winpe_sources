# CFveApiBase::GetStandardValidationInfo(bool,bool,_FVE_DATUM_VALIDATION_INFO * *)

- ea: `0x18009c910`
- end: `0x18009d0ae`
- name: `?GetStandardValidationInfo@CFveApiBase@@QEAAJ_N0PEAPEAU_FVE_DATUM_VALIDATION_INFO@@@Z`
- size: `1950`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this, bool, bool, struct _FVE_DATUM_VALIDATION_INFO **)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config`

## callers

- `0x18009e2f8`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180009468`
- `0x180018b10`
- `0x18001b260`
- `0x18001d0a0`
- `0x180047570`
- `0x18004f700`
- `0x1800566a4`
- `0x1800600c0`
- `0x18009ba80`
- `0x18009c910`
- `0x18009d858`
- `0x18009dc94`
- `0x18009e740`
- `0x18009f384`
- `0x1800ff770`
- `0x18011f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18009d012`
- `msvcrt!??3@YAXPEAX@Z` at `0x18012489e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009d012`
- `msvcrt!??3@YAXPEAX@Z` at `0x18012489e`
- `bcd!BcdCloseObject` at `0x18009d03f`
- `bcd!BcdCloseObject` at `0x1801248c6`
- `bcd!BcdCloseObject` at `0x18009d03f`
- `bcd!BcdCloseObject` at `0x1801248c6`
- `bcd!BcdGetElementData` at `0x18009ce1d`
- `bcd!BcdGetElementData` at `0x18009ce1d`
- `bcd!BcdOpenObject` at `0x18009cd20`
- `bcd!BcdOpenObject` at `0x18009cd20`
- `bcd!BcdCloseStore` at `0x18009d056`
- `bcd!BcdCloseStore` at `0x1801248d9`
- `bcd!BcdCloseStore` at `0x18009d056`
- `bcd!BcdCloseStore` at `0x1801248d9`
- `bcd!BcdOpenSystemStore` at `0x18009ca30`
- `bcd!BcdOpenSystemStore` at `0x18009ca30`

## pseudocode

```c
__int64 __fastcall CFveApiBase::GetStandardValidationInfo(
        const wchar_t **this,
        char a2,
        char a3,
        struct _FVE_DATUM_VALIDATION_INFO **a4)
{
  const wchar_t *v7; // rdx
  struct _FVE_DATUM_VALIDATION_ENTRY *v8; // r12
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  int DoesRegKeyExist; // eax
  __int64 v15; // rcx
  int v16; // eax
  int First; // eax
  int v18; // eax
  int v19; // eax
  int ElementData; // eax
  int v21; // eax
  void *v22; // rax
  int v24; // [rsp+20h] [rbp-D8h]
  int v25; // [rsp+20h] [rbp-D8h]
  int v26; // [rsp+38h] [rbp-C0h]
  int v27; // [rsp+38h] [rbp-C0h]
  int v28; // [rsp+40h] [rbp-B8h]
  int v29; // [rsp+40h] [rbp-B8h]
  unsigned __int8 v30[4]; // [rsp+54h] [rbp-A4h] BYREF
  int v31; // [rsp+58h] [rbp-A0h] BYREF
  int v32; // [rsp+5Ch] [rbp-9Ch] BYREF
  struct _FVE_DATUM_VALIDATION_INFO *v33; // [rsp+60h] [rbp-98h] BYREF
  __int64 v34; // [rsp+68h] [rbp-90h] BYREF
  struct _FVE_DATUM_VALIDATION_ENTRY *v35; // [rsp+70h] [rbp-88h]
  struct _FVE_DATUM_VALIDATION_INFO **v36; // [rsp+78h] [rbp-80h]
  void *v37; // [rsp+80h] [rbp-78h] BYREF
  __int64 v38; // [rsp+88h] [rbp-70h] BYREF
  unsigned __int16 v39[2]; // [rsp+90h] [rbp-68h] BYREF
  int v40; // [rsp+94h] [rbp-64h] BYREF
  struct _GUID v41; // [rsp+98h] [rbp-60h] BYREF
  __int128 v42; // [rsp+A8h] [rbp-50h] BYREF

  v36 = a4;
  v42 = 0;
  v40 = 0;
  v35 = 0;
  v33 = 0;
  v37 = 0;
  v38 = 0;
  v39[0] = 0;
  v41 = GUID_CURRENT_BOOT_ENTRY;
  v31 = 0;
  v32 = 0;
  v34 = 0;
  v30[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, &WPP_1559182127783aab3882fe828952d989_Traceguids);
  v8 = (struct _FVE_DATUM_VALIDATION_ENTRY *)operator new[](0x3AE8u, (const struct std::nothrow_t *)&std::nothrow);
  v35 = v8;
  if ( !v8 )
  {
    v9 = -2147024882;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = 219;
LABEL_8:
      v12 = v9;
LABEL_9:
      WPP_SF_d(v10[2], v11, &WPP_1559182127783aab3882fe828952d989_Traceguids, v12);
LABEL_83:
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_84;
    }
    goto LABEL_84;
  }
  v13 = BcdOpenSystemStore(&v37, v7);
  DoesRegKeyExist = FromNtStatus(v13);
  v9 = DoesRegKeyExist;
  if ( DoesRegKeyExist < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_84;
    v11 = 220;
    goto LABEL_14;
  }
  DoesRegKeyExist = NgscbpDoesRegKeyExist(v15, v7, &v31);
  v9 = DoesRegKeyExist;
  if ( DoesRegKeyExist < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_84;
    v11 = 221;
    goto LABEL_14;
  }
  if ( v31 )
  {
    DoesRegKeyExist = CFveApiBase::GetAssociatedOs(v37, &v41);
    v9 = DoesRegKeyExist;
    if ( DoesRegKeyExist < 0 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_84;
      v11 = 222;
      goto LABEL_14;
    }
  }
  LOBYTE(v7) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Validation_Info_SecureBoot_On_OverlayBoot>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Validation_Info_SecureBoot_On_OverlayBoot>::GetImpl'::`2'::impl,
    v7);
  DoesRegKeyExist = CFveApiBase::ResolveVolumeMountName((CFveApiBase *)this);
  v9 = DoesRegKeyExist;
  if ( DoesRegKeyExist < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_84;
    v11 = 223;
    goto LABEL_14;
  }
  v16 = IsOverlayConfigurationPresent(this[49], v7, &v32);
  DoesRegKeyExist = FromNtStatus(v16);
  v9 = DoesRegKeyExist;
  if ( DoesRegKeyExist < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_84;
    v11 = 224;
    goto LABEL_14;
  }
  DoesRegKeyExist = CFveApiBase::GetBootEntryValidationOverride(&v41, v30);
  v9 = DoesRegKeyExist;
  if ( DoesRegKeyExist < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_84;
    v11 = 225;
    goto LABEL_14;
  }
  First = FveDatasetGetFirst(this[146], 4, 7, &v34);
  v9 = FromNtStatus(First);
  if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147023728 )
  {
    if ( a2 && (v9 & 0x80000000) == 0 && (v32 || v30[0]) )
    {
      DoesRegKeyExist = CFveApiBase::RefreshValidationInfoForBootApp((CFveApiBase *)this, &v41, 0x179u, v8, v39);
      v9 = DoesRegKeyExist;
      if ( DoesRegKeyExist < 0 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_84;
        v11 = 227;
        goto LABEL_14;
      }
    }
    else
    {
      DoesRegKeyExist = CFveApiBase::StoreValidationDataForAppEx(this, v37, 0, 0, 377, v8, v39, 1, 0);
      v9 = DoesRegKeyExist;
      if ( DoesRegKeyExist < 0 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_84;
        v11 = 228;
        goto LABEL_14;
      }
      v18 = BcdOpenObject(v37, &v41, &v38);
      v19 = FromNtStatus(v18);
      v9 = v19;
      if ( v19 < 0 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF__guid_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            229,
            &WPP_1559182127783aab3882fe828952d989_Traceguids,
            &v41,
            v19);
          goto LABEL_83;
        }
        goto LABEL_84;
      }
      LOBYTE(v28) = a3;
      LOBYTE(v26) = 1;
      LOWORD(v24) = 377;
      DoesRegKeyExist = CFveApiBase::StoreValidationDataForAppEx(this, v37, &v41, 1, v24, v8, v39, v26, v28);
      v9 = DoesRegKeyExist;
      if ( DoesRegKeyExist < 0 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_84;
        v11 = 230;
        goto LABEL_14;
      }
      v40 = 16;
      ElementData = BcdGetElementData(v38, 587202563, &v42, &v40);
      DoesRegKeyExist = FromNtStatus(ElementData);
      v9 = DoesRegKeyExist;
      if ( DoesRegKeyExist != -2147023728 )
      {
        if ( DoesRegKeyExist < 0 )
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_84;
          v11 = 231;
          goto LABEL_14;
        }
        LOBYTE(v29) = a3;
        LOBYTE(v27) = 1;
        LOWORD(v25) = 377;
        DoesRegKeyExist = CFveApiBase::StoreValidationDataForAppEx(this, v37, &v42, 2, v25, v8, v39, v27, v29);
        v9 = DoesRegKeyExist;
        if ( DoesRegKeyExist < 0 && DoesRegKeyExist != -2147023728 && DoesRegKeyExist != -2147024894 )
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_84;
          v11 = 232;
          goto LABEL_14;
        }
      }
      LOBYTE(v29) = 0;
      LOBYTE(v27) = 1;
      LOWORD(v25) = 377;
      DoesRegKeyExist = CFveApiBase::StoreValidationDataForAppEx(
                          this,
                          v37,
                          &GUID_WINDOWS_MEMORY_TESTER,
                          3,
                          v25,
                          v8,
                          v39,
                          v27,
                          v29);
      v9 = DoesRegKeyExist;
      if ( DoesRegKeyExist < 0 && DoesRegKeyExist != -2147023728 && DoesRegKeyExist != -2147024894 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_84;
        v11 = 233;
        goto LABEL_14;
      }
    }
    v21 = FveDatumValidationInfoCreate(v8, v39[0], 0, &v33);
    DoesRegKeyExist = FromNtStatus(v21);
    v9 = DoesRegKeyExist;
    if ( DoesRegKeyExist >= 0 )
    {
      *v36 = v33;
      v33 = 0;
      goto LABEL_83;
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_84;
    v11 = 234;
LABEL_14:
    v12 = (unsigned int)DoesRegKeyExist;
    goto LABEL_9;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v11 = 226;
    goto LABEL_8;
  }
LABEL_84:
  if ( v33 )
  {
    FveDatumFree(v33);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v34 )
  {
    FveDatumFree(v34);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    operator delete(v8);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v22 = v37;
  if ( v37 )
  {
    if ( v38 )
    {
      BcdCloseObject(v38);
      v22 = v37;
    }
    BcdCloseStore(v22, v7);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 )
    WPP_SF_d(v10[2], 235, &WPP_1559182127783aab3882fe828952d989_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18009c910  mov     r11, rsp
0x18009c913  push    rbx
0x18009c914  push    rsi
0x18009c915  push    rdi
0x18009c916  push    r12
0x18009c918  push    r13
0x18009c91a  push    r14
0x18009c91c  push    r15
0x18009c91e  sub     rsp, 0C0h
0x18009c925  mov     rax, cs:__security_cookie
0x18009c92c  xor     rax, rsp
0x18009c92f  mov     [rsp+0F8h+var_40], rax
0x18009c937  mov     [rsp+0F8h+var_80], r9
0x18009c93c  mov     r13b, r8b
0x18009c93f  mov     r14b, dl
0x18009c942  mov     r15, rcx
0x18009c945  xorps   xmm0, xmm0
0x18009c948  movups  xmmword ptr [r11-50h], xmm0
0x18009c94d  mov     dword ptr [r11-64h], 0
0x18009c955  mov     [rsp+0F8h+var_88], 0
0x18009c95e  mov     [rsp+0F8h+var_98], 0
0x18009c967  mov     qword ptr [r11-78h], 0
0x18009c96f  mov     qword ptr [r11-70h], 0
0x18009c977  xor     eax, eax
0x18009c979  mov     [r11-68h], ax
0x18009c97e  movups  xmm0, xmmword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data1
0x18009c985  movdqu  xmmword ptr [r11-60h], xmm0
0x18009c98b  mov     [rsp+0F8h+var_A0], eax
0x18009c98f  mov     [rsp+0F8h+var_9C], eax
0x18009c993  mov     [rsp+0F8h+var_90], rax
0x18009c998  mov     [rsp+0F8h+var_A4], al
0x18009c99c  lea     rsi, WPP_GLOBAL_Control
0x18009c9a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c9aa  lea     rdi, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009c9b1  cmp     rcx, rsi
0x18009c9b4  jz      short loc_18009C9CE
0x18009c9b6  test    byte ptr [rcx+1Ch], 20h
0x18009c9ba  jz      short loc_18009C9CE
0x18009c9bc  mov     edx, 0DAh
0x18009c9c1  mov     r8, rdi
0x18009c9c4  mov     rcx, [rcx+10h]
0x18009c9c8  call    WPP_SF_
0x18009c9cd  nop
0x18009c9ce  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009c9d5  mov     ecx, 3AE8h; unsigned __int64
0x18009c9da  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18009c9df  mov     r12, rax
0x18009c9e2  mov     [rsp+0F8h+var_88], rax
0x18009c9e7  test    rax, rax
0x18009c9ea  jnz     short loc_18009CA28
0x18009c9ec  mov     ebx, 8007000Eh
0x18009c9f1  mov     [rsp+0F8h+var_A8], ebx
0x18009c9f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c9fc  cmp     rcx, rsi
0x18009c9ff  jz      loc_18009CFD8
0x18009ca05  test    byte ptr [rcx+1Ch], 2
0x18009ca09  jz      loc_18009CFD8
0x18009ca0f  mov     edx, 0DBh
0x18009ca14  mov     r9d, ebx
0x18009ca17  mov     r8, rdi
0x18009ca1a  mov     rcx, [rcx+10h]
0x18009ca1e  call    WPP_SF_d
0x18009ca23  jmp     loc_18009CFD1
0x18009ca28  lea     rcx, [rsp+0F8h+var_78]
0x18009ca30  call    cs:__imp_BcdOpenSystemStore
0x18009ca37  nop     dword ptr [rax+rax+00h]
0x18009ca3c  mov     ecx, eax; int
0x18009ca3e  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009ca43  mov     ebx, eax
0x18009ca45  mov     [rsp+0F8h+var_A8], eax
0x18009ca49  test    eax, eax
0x18009ca4b  jns     short loc_18009CA71
0x18009ca4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ca54  cmp     rcx, rsi
0x18009ca57  jz      loc_18009CFD8
0x18009ca5d  test    byte ptr [rcx+1Ch], 2
0x18009ca61  jz      loc_18009CFD8
0x18009ca67  mov     edx, 0DCh
0x18009ca6c  mov     r9d, eax
0x18009ca6f  jmp     short loc_18009CA17
0x18009ca71  lea     r8, [rsp+0F8h+var_A0]
0x18009ca76  call    NgscbpDoesRegKeyExist
0x18009ca7b  mov     ebx, eax
0x18009ca7d  mov     [rsp+0F8h+var_A8], eax
0x18009ca81  test    eax, eax
0x18009ca83  jns     short loc_18009CAA6
0x18009ca85  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ca8c  cmp     rcx, rsi
0x18009ca8f  jz      loc_18009CFD8
0x18009ca95  test    byte ptr [rcx+1Ch], 2
0x18009ca99  jz      loc_18009CFD8
0x18009ca9f  mov     edx, 0DDh
0x18009caa4  jmp     short loc_18009CA6C
0x18009caa6  cmp     [rsp+0F8h+var_A0], 0
0x18009caab  jz      short loc_18009CAF0
0x18009caad  lea     rdx, [rsp+0F8h+var_60]; struct _GUID *
0x18009cab5  mov     rcx, [rsp+0F8h+var_78]; void *
0x18009cabd  call    ?GetAssociatedOs@CFveApiBase@@KAJPEAXPEAU_GUID@@@Z; CFveApiBase::GetAssociatedOs(void *,_GUID *)
0x18009cac2  mov     ebx, eax
0x18009cac4  mov     [rsp+0F8h+var_A8], eax
0x18009cac8  test    eax, eax
0x18009caca  jns     short loc_18009CAF0
0x18009cacc  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cad3  cmp     rcx, rsi
0x18009cad6  jz      loc_18009CFD8
0x18009cadc  test    byte ptr [rcx+1Ch], 2
0x18009cae0  jz      loc_18009CFD8
0x18009cae6  mov     edx, 0DEh
0x18009caeb  jmp     loc_18009CA6C
0x18009caf0  mov     dl, 1
0x18009caf2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BitLocker_Validation_Info_SecureBoot_On_OverlayBoot@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Validation_Info_SecureBoot_On_OverlayBoot@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Validation_Info_SecureBoot_On_OverlayBoot> `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Validation_Info_SecureBoot_On_OverlayBoot>::GetImpl(void)'::`2'::impl
0x18009caf9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Validation_Info_SecureBoot_On_OverlayBoot@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Validation_Info_SecureBoot_On_OverlayBoot>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18009cafe  mov     rcx, r15; this
0x18009cb01  call    ?ResolveVolumeMountName@CFveApiBase@@QEAAJXZ; CFveApiBase::ResolveVolumeMountName(void)
0x18009cb06  mov     ebx, eax
0x18009cb08  mov     [rsp+0F8h+var_A8], eax
0x18009cb0c  test    eax, eax
0x18009cb0e  jns     short loc_18009CB34
0x18009cb10  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cb17  cmp     rcx, rsi
0x18009cb1a  jz      loc_18009CFD8
0x18009cb20  test    byte ptr [rcx+1Ch], 2
0x18009cb24  jz      loc_18009CFD8
0x18009cb2a  mov     edx, 0DFh
0x18009cb2f  jmp     loc_18009CA6C
0x18009cb34  lea     r8, [rsp+0F8h+var_9C]; int *
0x18009cb39  mov     rcx, [r15+188h]; wchar_t *
0x18009cb40  call    ?IsOverlayConfigurationPresent@@YAJQEB_W0PEAH@Z; IsOverlayConfigurationPresent(wchar_t const * const,wchar_t const * const,int *)
0x18009cb45  mov     ecx, eax; int
0x18009cb47  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009cb4c  mov     ebx, eax
0x18009cb4e  mov     [rsp+0F8h+var_A8], eax
0x18009cb52  test    eax, eax
0x18009cb54  jns     short loc_18009CB7A
0x18009cb56  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cb5d  cmp     rcx, rsi
0x18009cb60  jz      loc_18009CFD8
0x18009cb66  test    byte ptr [rcx+1Ch], 2
0x18009cb6a  jz      loc_18009CFD8
0x18009cb70  mov     edx, 0E0h
0x18009cb75  jmp     loc_18009CA6C
0x18009cb7a  lea     rdx, [rsp+0F8h+var_A4]; unsigned __int8 *
0x18009cb7f  lea     rcx, [rsp+0F8h+var_60]; struct _GUID *
0x18009cb87  call    ?GetBootEntryValidationOverride@CFveApiBase@@SAJPEBU_GUID@@PEAE@Z; CFveApiBase::GetBootEntryValidationOverride(_GUID const *,uchar *)
0x18009cb8c  mov     ebx, eax
0x18009cb8e  mov     [rsp+0F8h+var_A8], eax
0x18009cb92  test    eax, eax
0x18009cb94  jns     short loc_18009CBBA
0x18009cb96  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cb9d  cmp     rcx, rsi
0x18009cba0  jz      loc_18009CFD8
0x18009cba6  test    byte ptr [rcx+1Ch], 2
0x18009cbaa  jz      loc_18009CFD8
0x18009cbb0  mov     edx, 0E1h
0x18009cbb5  jmp     loc_18009CA6C
0x18009cbba  mov     edx, 4
0x18009cbbf  lea     r8d, [rdx+3]
0x18009cbc3  lea     r9, [rsp+0F8h+var_90]
0x18009cbc8  mov     rcx, [r15+490h]
0x18009cbcf  call    FveDatasetGetFirst
0x18009cbd4  mov     ecx, eax; int
0x18009cbd6  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009cbdb  mov     ebx, eax
0x18009cbdd  mov     [rsp+0F8h+var_A8], eax
0x18009cbe1  mov     ecx, 80000000h
0x18009cbe6  add     eax, ecx
0x18009cbe8  mov     esi, 80070490h
0x18009cbed  test    ecx, eax
0x18009cbef  jnz     short loc_18009CC20
0x18009cbf1  cmp     ebx, esi
0x18009cbf3  jz      short loc_18009CC20
0x18009cbf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cbfc  lea     rsi, WPP_GLOBAL_Control
0x18009cc03  cmp     rcx, rsi
0x18009cc06  jz      loc_18009CFD8
0x18009cc0c  test    byte ptr [rcx+1Ch], 2
0x18009cc10  jz      loc_18009CFD8
0x18009cc16  mov     edx, 0E2h
0x18009cc1b  jmp     loc_18009CA14
0x18009cc20  xor     eax, eax
0x18009cc22  test    r14b, r14b
0x18009cc25  jz      short loc_18009CC96
0x18009cc27  test    ebx, ebx
0x18009cc29  js      short loc_18009CC96
0x18009cc2b  cmp     [rsp+0F8h+var_9C], eax
0x18009cc2f  jnz     short loc_18009CC37
0x18009cc31  cmp     [rsp+0F8h+var_A4], al
0x18009cc35  jz      short loc_18009CC96
0x18009cc37  mov     r8d, 179h; unsigned __int16
0x18009cc3d  lea     rax, [rsp+0F8h+var_68]
0x18009cc45  mov     [rsp+0F8h+var_D8], rax; unsigned __int16 *
0x18009cc4a  mov     r9, r12; struct _FVE_DATUM_VALIDATION_ENTRY *
0x18009cc4d  lea     rdx, [rsp+0F8h+var_60]; struct _GUID *
0x18009cc55  mov     rcx, r15; this
0x18009cc58  call    ?RefreshValidationInfoForBootApp@CFveApiBase@@QEAAJPEBU_GUID@@GPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG@Z; CFveApiBase::RefreshValidationInfoForBootApp(_GUID const *,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *)
0x18009cc5d  mov     ebx, eax
0x18009cc5f  mov     [rsp+0F8h+var_A8], eax
0x18009cc63  test    eax, eax
0x18009cc65  jns     loc_18009CF68
0x18009cc6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cc72  lea     rsi, WPP_GLOBAL_Control
0x18009cc79  cmp     rcx, rsi
0x18009cc7c  jz      loc_18009CFD8
0x18009cc82  test    byte ptr [rcx+1Ch], 2
0x18009cc86  jz      loc_18009CFD8
0x18009cc8c  mov     edx, 0E3h
0x18009cc91  jmp     loc_18009CA6C
0x18009cc96  mov     r14d, 179h
0x18009cc9c  mov     byte ptr [rsp+0F8h+var_B8], al
0x18009cca0  mov     [rsp+0F8h+var_C0], 1
0x18009cca5  lea     rax, [rsp+0F8h+var_68]
0x18009ccad  mov     [rsp+0F8h+var_C8], rax
0x18009ccb2  mov     [rsp+0F8h+var_D0], r12
0x18009ccb7  mov     word ptr [rsp+0F8h+var_D8], r14w
0x18009ccbd  xor     r9d, r9d
0x18009ccc0  xor     r8d, r8d
0x18009ccc3  mov     rdx, [rsp+0F8h+var_78]
0x18009cccb  mov     rcx, r15
0x18009ccce  call    ?StoreValidationDataForAppEx@CFveApiBase@@QEAAJPEAXPEBU_GUID@@W4eFveBootApplicationPolicy@@GPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG_N5@Z; CFveApiBase::StoreValidationDataForAppEx(void *,_GUID const *,eFveBootApplicationPolicy,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *,bool,bool)
0x18009ccd3  mov     ebx, eax
0x18009ccd5  mov     [rsp+0F8h+var_A8], eax
0x18009ccd9  test    eax, eax
0x18009ccdb  jns     short loc_18009CD08
0x18009ccdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cce4  lea     rsi, WPP_GLOBAL_Control
0x18009cceb  cmp     rcx, rsi
0x18009ccee  jz      loc_18009CFD8
0x18009ccf4  test    byte ptr [rcx+1Ch], 2
0x18009ccf8  jz      loc_18009CFD8
0x18009ccfe  mov     edx, 0E4h
0x18009cd03  jmp     loc_18009CA6C
0x18009cd08  lea     r8, [rsp+0F8h+var_70]
0x18009cd10  lea     rdx, [rsp+0F8h+var_60]
0x18009cd18  mov     rcx, [rsp+0F8h+var_78]
0x18009cd20  call    cs:__imp_BcdOpenObject
0x18009cd27  nop     dword ptr [rax+rax+00h]
0x18009cd2c  mov     ecx, eax; int
0x18009cd2e  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009cd33  mov     ebx, eax
0x18009cd35  mov     [rsp+0F8h+var_A8], eax
0x18009cd39  test    eax, eax
0x18009cd3b  jns     short loc_18009CD80
0x18009cd3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cd44  lea     rsi, WPP_GLOBAL_Control
0x18009cd4b  cmp     rcx, rsi
0x18009cd4e  jz      loc_18009CFD8
0x18009cd54  test    byte ptr [rcx+1Ch], 2
0x18009cd58  jz      loc_18009CFD8
0x18009cd5e  mov     edx, 0E5h
0x18009cd63  mov     dword ptr [rsp+0F8h+var_D8], eax
0x18009cd67  lea     r9, [rsp+0F8h+var_60]
0x18009cd6f  mov     r8, rdi
0x18009cd72  mov     rcx, [rcx+10h]
0x18009cd76  call    WPP_SF__guid_D
0x18009cd7b  jmp     loc_18009CFD1
0x18009cd80  mov     byte ptr [rsp+0F8h+var_B8], r13b
0x18009cd85  mov     [rsp+0F8h+var_C0], 1
0x18009cd8a  lea     rax, [rsp+0F8h+var_68]
0x18009cd92  mov     [rsp+0F8h+var_C8], rax
0x18009cd97  mov     [rsp+0F8h+var_D0], r12
0x18009cd9c  mov     word ptr [rsp+0F8h+var_D8], r14w
0x18009cda2  mov     r9d, 1
0x18009cda8  lea     r8, [rsp+0F8h+var_60]
0x18009cdb0  mov     rdx, [rsp+0F8h+var_78]
0x18009cdb8  mov     rcx, r15
0x18009cdbb  call    ?StoreValidationDataForAppEx@CFveApiBase@@QEAAJPEAXPEBU_GUID@@W4eFveBootApplicationPolicy@@GPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG_N5@Z; CFveApiBase::StoreValidationDataForAppEx(void *,_GUID const *,eFveBootApplicationPolicy,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *,bool,bool)
0x18009cdc0  mov     ebx, eax
0x18009cdc2  mov     [rsp+0F8h+var_A8], eax
0x18009cdc6  test    eax, eax
0x18009cdc8  jns     short loc_18009CDF5
0x18009cdca  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cdd1  lea     rsi, WPP_GLOBAL_Control
0x18009cdd8  cmp     rcx, rsi
0x18009cddb  jz      loc_18009CFD8
0x18009cde1  test    byte ptr [rcx+1Ch], 2
0x18009cde5  jz      loc_18009CFD8
0x18009cdeb  mov     edx, 0E6h
0x18009cdf0  jmp     loc_18009CA6C
0x18009cdf5  mov     [rsp+0F8h+var_64], 10h
0x18009ce00  lea     r9, [rsp+0F8h+var_64]
0x18009ce08  lea     r8, [rsp+0F8h+var_50]
0x18009ce10  mov     edx, 23000003h
0x18009ce15  mov     rcx, [rsp+0F8h+var_70]
0x18009ce1d  call    cs:__imp_BcdGetElementData
0x18009ce24  nop     dword ptr [rax+rax+00h]
0x18009ce29  mov     ecx, eax; int
0x18009ce2b  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009ce30  mov     ebx, eax
0x18009ce32  mov     [rsp+0F8h+var_A8], eax
0x18009ce36  cmp     eax, esi
0x18009ce38  jz      loc_18009CEED
0x18009ce3e  test    eax, eax
0x18009ce40  jns     short loc_18009CE6D
0x18009ce42  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ce49  lea     rsi, WPP_GLOBAL_Control
0x18009ce50  cmp     rcx, rsi
0x18009ce53  jz      loc_18009CFD8
0x18009ce59  test    byte ptr [rcx+1Ch], 2
0x18009ce5d  jz      loc_18009CFD8
0x18009ce63  mov     edx, 0E7h
  ... truncated ...
```
