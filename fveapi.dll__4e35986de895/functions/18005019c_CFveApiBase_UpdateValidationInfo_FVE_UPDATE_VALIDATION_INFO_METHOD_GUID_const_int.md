# CFveApiBase::UpdateValidationInfo(_FVE_UPDATE_VALIDATION_INFO_METHOD,_GUID const *,int)

- ea: `0x18005019c`
- end: `0x180050954`
- name: `?UpdateValidationInfo@CFveApiBase@@QEAAJW4_FVE_UPDATE_VALIDATION_INFO_METHOD@@PEBU_GUID@@H@Z`
- size: `1976`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, installer_update`

## callers

- `0x1800c1e98`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180018b10`
- `0x18001b260`
- `0x18001d0a0`
- `0x180044da4`
- `0x180046a90`
- `0x18004f700`
- `0x18004fce0`
- `0x18005019c`
- `0x1800566a4`
- `0x1800600c0`
- `0x180099a58`
- `0x18009aca8`
- `0x18009d858`
- `0x18009f384`
- `0x18009f3d0`
- `0x180119c58`
- `0x18011f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800504ba`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800504ba`
- `bcd!BcdQueryObject` at `0x180050612`
- `bcd!BcdQueryObject` at `0x180050612`
- `bcd!BcdCloseObject` at `0x1800502a5`
- `bcd!BcdCloseObject` at `0x1800502a5`
- `bcd!BcdOpenObject` at `0x1800505ae`
- `bcd!BcdOpenObject` at `0x1800505ae`
- `bcd!BcdCloseStore` at `0x1800502b5`
- `bcd!BcdCloseStore` at `0x1800502b5`
- `bcd!BcdOpenSystemStore` at `0x180050563`
- `bcd!BcdOpenSystemStore` at `0x180050563`

## pseudocode

```c
__int64 __fastcall CFveApiBase::UpdateValidationInfo(CFveApiBase *a1, int a2, struct _GUID *a3, int a4)
{
  int BootEntryValidationOverride; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // ebx
  PVOID *v12; // r10
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rcx
  unsigned __int8 v17; // di
  __int64 v18; // rdx
  struct _FVE_DATUM_VALIDATION_ENTRY *v19; // r15
  int First; // eax
  int refreshed; // eax
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // r14d
  int v33; // eax
  unsigned __int16 v34; // r8
  int appended; // eax
  unsigned __int8 v36; // [rsp+40h] [rbp-39h] BYREF
  char v37; // [rsp+41h] [rbp-38h] BYREF
  _BYTE v38[6]; // [rsp+42h] [rbp-37h] BYREF
  __int64 v39; // [rsp+48h] [rbp-31h] BYREF
  __int64 v40; // [rsp+50h] [rbp-29h] BYREF
  __int64 v41; // [rsp+58h] [rbp-21h] BYREF
  __int64 v42; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int16 v43; // [rsp+68h] [rbp-11h] BYREF
  struct _GUID v44; // [rsp+70h] [rbp-9h] BYREF
  _OWORD v45[2]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v46; // [rsp+A0h] [rbp+27h]

  v36 = 0;
  v46 = 0;
  v38[0] = 0;
  v44 = 0;
  memset(v45, 0, sizeof(v45));
  v37 = 0;
  v39 = 0;
  v40 = 0;
  v43 = 0;
  v41 = 0;
  v42 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_1559182127783aab3882fe828952d989_Traceguids);
  BootEntryValidationOverride = CFveApiBase::GetBootEntryValidationOverride(a3, &v36);
  v11 = BootEntryValidationOverride;
  if ( BootEntryValidationOverride < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v13 = 33;
      v14 = (unsigned int)BootEntryValidationOverride;
LABEL_8:
      WPP_SF_d(v12[2], v13, &WPP_1559182127783aab3882fe828952d989_Traceguids, v14);
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  v17 = v36;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF__guid_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v10, a3, a2, a4 != 0, v36 != 0);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a4 )
  {
    if ( v17 )
    {
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 )
      {
        v18 = 35;
LABEL_32:
        WPP_SF_(v12[2], v18, &WPP_1559182127783aab3882fe828952d989_Traceguids);
      }
    }
    else if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    {
      v18 = 36;
      goto LABEL_32;
    }
  }
  else
  {
    if ( !v17 )
    {
      if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 8) == 0 )
        goto LABEL_9;
      v19 = 0;
      WPP_SF_(v12[2], 38, &WPP_1559182127783aab3882fe828952d989_Traceguids);
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_44;
    }
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    {
      v18 = 37;
      goto LABEL_32;
    }
  }
  v19 = (struct _FVE_DATUM_VALIDATION_ENTRY *)operator new[](0x3AE8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v19 )
  {
    First = FveDatasetGetFirst(*((_QWORD *)a1 + 146), 4, 7, &v39);
    refreshed = FromNtStatus(First);
    v11 = refreshed;
    if ( refreshed < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_44;
      v22 = 40;
      goto LABEL_41;
    }
    v24 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_CURRENT_BOOT_ENTRY.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_CURRENT_BOOT_ENTRY.Data1 )
      v24 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_CURRENT_BOOT_ENTRY.Data4;
    if ( v24 )
    {
      v25 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_DEFAULT_BOOT_ENTRY.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_DEFAULT_BOOT_ENTRY.Data1 )
        v25 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_DEFAULT_BOOT_ENTRY.Data4;
      if ( v25 )
      {
        v44 = *a3;
        goto LABEL_57;
      }
    }
    v27 = BcdOpenSystemStore(&v41, v9);
    refreshed = FromNtStatus(v27);
    v11 = refreshed;
    if ( refreshed >= 0 )
    {
      v28 = BcdOpenObject(v41, a3, &v42);
      v29 = FromNtStatus(v28);
      v11 = v29;
      if ( v29 < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_44;
        WPP_SF__guid_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          42,
          &WPP_1559182127783aab3882fe828952d989_Traceguids,
          a3,
          v29);
        goto LABEL_43;
      }
      v30 = BcdQueryObject(v42, 0, 0, &v44);
      refreshed = FromNtStatus(v30);
      v11 = refreshed;
      if ( refreshed >= 0 )
      {
LABEL_57:
        v26 = FveDatumValidationInfoDataEntry(0, &v44, 16, v45);
        refreshed = FromNtStatus(v26);
        v11 = refreshed;
        if ( refreshed < 0 )
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_44;
          v22 = 44;
          goto LABEL_41;
        }
        LODWORD(v45[0]) = 131076;
        v31 = FveDatumCheckEntryInValidationInfo(v39, v45, v38, &v37);
        v11 = FromNtStatus(v31);
        if ( v11 < 0 )
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_44;
          v22 = 45;
          goto LABEL_77;
        }
        if ( v37 && a2 == 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_1559182127783aab3882fe828952d989_Traceguids);
        }
        else if ( a2 )
        {
          v32 = a2 - 1;
          if ( v32 )
          {
            if ( v32 == 1 )
            {
              v11 = CFveApiBase::DeleteValidationInfoForBootApp(a1, a3, 0, 0x179u, v19, &v43);
              if ( v11 >= 0 )
                goto LABEL_101;
              v12 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_44;
              v22 = 49;
            }
            else
            {
              v11 = -2147024883;
              v12 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_44;
              v22 = 50;
            }
          }
          else
          {
            v11 = CFveApiBase::AddValidationInfoForBootApp(a1, a3, 0, 0x179u, v19, &v43);
            if ( v11 >= 0 )
              goto LABEL_101;
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_44;
            v22 = 48;
          }
LABEL_77:
          v23 = (unsigned int)v11;
          goto LABEL_42;
        }
        refreshed = CFveApiBase::RefreshValidationInfoForBootApp(a1, a3, 0x179u, v19, &v43);
        v11 = refreshed;
        if ( refreshed < 0 )
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_44;
          v22 = 47;
          goto LABEL_41;
        }
LABEL_101:
        v33 = FveDatumValidationInfoCreate(v19, v43, *(unsigned __int16 *)(v39 + 6), &v40);
        v11 = FromNtStatus(v33);
        if ( v11 >= 0 )
        {
          v11 = CFveApiBase::EraseAll(a1, 4u, v34);
          if ( v11 >= 0 )
          {
            appended = FveDatasetAppendDatum(*((_QWORD *)a1 + 146), v40, 4);
            v11 = FromNtStatus(appended);
            if ( v11 >= 0 )
              goto LABEL_43;
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_44;
            v22 = 53;
          }
          else
          {
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_44;
            v22 = 52;
          }
        }
        else
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_44;
          v22 = 51;
        }
        goto LABEL_77;
      }
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_44;
      v22 = 43;
    }
    else
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_44;
      v22 = 41;
    }
LABEL_41:
    v23 = (unsigned int)refreshed;
LABEL_42:
    WPP_SF_d(v12[2], v22, &WPP_1559182127783aab3882fe828952d989_Traceguids, v23);
LABEL_43:
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_44:
    if ( v39 )
    {
      FveDatumFree(v39);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v40 )
    {
      FveDatumFree(v40);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v19 )
    {
      operator delete(v19);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_9;
  }
  v11 = -2147024882;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v13 = 39;
    v14 = 2147942414LL;
    goto LABEL_8;
  }
LABEL_9:
  v15 = v41;
  if ( v41 )
  {
    if ( v42 )
    {
      BcdCloseObject(v42);
      v15 = v41;
    }
    BcdCloseStore(v15, v9);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x20) != 0 )
    WPP_SF_d(v12[2], 54, &WPP_1559182127783aab3882fe828952d989_Traceguids, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18005019c  mov     [rsp-8+arg_8], rbx
0x1800501a1  mov     [rsp-8+arg_18], rsi
0x1800501a6  push    rbp
0x1800501a7  push    rdi
0x1800501a8  push    r13
0x1800501aa  push    r14
0x1800501ac  push    r15
0x1800501ae  lea     rbp, [rsp-37h]
0x1800501b3  sub     rsp, 0B0h
0x1800501ba  mov     rax, cs:__security_cookie
0x1800501c1  xor     rax, rsp
0x1800501c4  mov     [rbp+57h+var_28], rax
0x1800501c8  xor     eax, eax
0x1800501ca  mov     [rbp+57h+var_90], 0
0x1800501ce  xorps   xmm1, xmm1
0x1800501d1  mov     [rbp+57h+var_30], rax
0x1800501d5  xorps   xmm0, xmm0
0x1800501d8  mov     [rbp+57h+var_8E], al
0x1800501db  movdqa  [rbp+57h+var_60], xmm0
0x1800501e0  mov     r15d, r9d
0x1800501e3  movups  [rbp+57h+var_50], xmm1
0x1800501e7  mov     [rbp+57h+var_8F], al
0x1800501ea  mov     rsi, r8
0x1800501ed  movups  [rbp+57h+var_40], xmm1
0x1800501f1  mov     [rbp+57h+var_88], rax
0x1800501f5  mov     r14d, edx
0x1800501f8  mov     [rbp+57h+var_80], rax
0x1800501fc  mov     r13, rcx
0x1800501ff  mov     [rbp+57h+var_68], ax
0x180050203  mov     [rbp+57h+var_78], 0
0x18005020b  mov     [rbp+57h+var_70], 0
0x180050213  mov     rcx, cs:WPP_GLOBAL_Control
0x18005021a  lea     rdi, WPP_GLOBAL_Control
0x180050221  cmp     rcx, rdi
0x180050224  jz      short loc_18005023F
0x180050226  test    byte ptr [rcx+1Ch], 20h
0x18005022a  jz      short loc_18005023F
0x18005022c  mov     rcx, [rcx+10h]
0x180050230  lea     edx, [rax+20h]
0x180050233  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18005023a  call    WPP_SF_
0x18005023f  lea     rdx, [rbp+57h+var_90]; unsigned __int8 *
0x180050243  mov     rcx, rsi; struct _GUID *
0x180050246  call    ?GetBootEntryValidationOverride@CFveApiBase@@SAJPEBU_GUID@@PEAE@Z; CFveApiBase::GetBootEntryValidationOverride(_GUID const *,uchar *)
0x18005024b  mov     ebx, eax
0x18005024d  test    eax, eax
0x18005024f  jns     loc_180050317
0x180050255  mov     r10, cs:WPP_GLOBAL_Control
0x18005025c  cmp     r10, rdi
0x18005025f  jz      short loc_180050290
0x180050261  mov     edi, 2
0x180050266  test    [r10+1Ch], dil
0x18005026a  jz      short loc_180050289
0x18005026c  lea     edx, [rdi+1Fh]
0x18005026f  mov     r9d, eax
0x180050272  mov     rcx, [r10+10h]
0x180050276  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18005027d  call    WPP_SF_d
0x180050282  mov     r10, cs:WPP_GLOBAL_Control
0x180050289  lea     rdi, WPP_GLOBAL_Control
0x180050290  mov     rcx, [rbp+57h+var_78]
0x180050294  test    rcx, rcx
0x180050297  jz      short loc_1800502C8
0x180050299  mov     rax, [rbp+57h+var_70]
0x18005029d  test    rax, rax
0x1800502a0  jz      short loc_1800502B5
0x1800502a2  mov     rcx, rax
0x1800502a5  call    cs:__imp_BcdCloseObject
0x1800502ac  nop     dword ptr [rax+rax+00h]
0x1800502b1  mov     rcx, [rbp+57h+var_78]
0x1800502b5  call    cs:__imp_BcdCloseStore
0x1800502bc  nop     dword ptr [rax+rax+00h]
0x1800502c1  mov     r10, cs:WPP_GLOBAL_Control
0x1800502c8  cmp     r10, rdi
0x1800502cb  jz      short loc_1800502EC
0x1800502cd  test    byte ptr [r10+1Ch], 20h
0x1800502d2  jz      short loc_1800502EC
0x1800502d4  mov     rcx, [r10+10h]
0x1800502d8  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x1800502df  mov     edx, 36h ; '6'
0x1800502e4  mov     r9d, ebx
0x1800502e7  call    WPP_SF_d
0x1800502ec  mov     eax, ebx
0x1800502ee  mov     rcx, [rbp+57h+var_28]
0x1800502f2  xor     rcx, rsp; StackCookie
0x1800502f5  call    __security_check_cookie
0x1800502fa  lea     r11, [rsp+0D0h+var_20]
0x180050302  mov     rbx, [r11+38h]
0x180050306  mov     rsi, [r11+48h]
0x18005030a  mov     rsp, r11
0x18005030d  pop     r15
0x18005030f  pop     r14
0x180050311  pop     r13
0x180050313  pop     rdi
0x180050314  pop     rbp
0x180050315  retn
0x180050317  mov     r10, cs:WPP_GLOBAL_Control
0x18005031e  lea     rax, WPP_GLOBAL_Control
0x180050325  mov     dil, [rbp+57h+var_90]
0x180050329  cmp     r10, rax
0x18005032c  jz      short loc_18005036A
0x18005032e  test    byte ptr [r10+1Ch], 8
0x180050333  jz      short loc_18005036A
0x180050335  xor     ecx, ecx
0x180050337  mov     edx, 22h ; '"'
0x18005033c  test    dil, dil
0x18005033f  mov     r9, rsi
0x180050342  setnz   cl
0x180050345  xor     eax, eax
0x180050347  mov     [rsp+0D0h+var_A0], ecx
0x18005034b  test    r15d, r15d
0x18005034e  mov     rcx, [r10+10h]
0x180050352  setnz   al
0x180050355  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180050359  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x18005035e  call    WPP_SF__guid_ddd
0x180050363  mov     r10, cs:WPP_GLOBAL_Control
0x18005036a  test    r15d, r15d
0x18005036d  jz      short loc_1800503A8
0x18005036f  test    dil, dil
0x180050372  jz      short loc_18005038E
0x180050374  lea     rdi, WPP_GLOBAL_Control
0x18005037b  cmp     r10, rdi
0x18005037e  jz      short loc_1800503D9
0x180050380  test    byte ptr [r10+1Ch], 4
0x180050385  jz      short loc_1800503D9
0x180050387  mov     edx, 23h ; '#'
0x18005038c  jmp     short loc_1800503C9
0x18005038e  lea     rdi, WPP_GLOBAL_Control
0x180050395  cmp     r10, rdi
0x180050398  jz      short loc_1800503D9
0x18005039a  test    byte ptr [r10+1Ch], 8
0x18005039f  jz      short loc_1800503D9
0x1800503a1  mov     edx, 24h ; '$'
0x1800503a6  jmp     short loc_1800503C9
0x1800503a8  test    dil, dil
0x1800503ab  jz      loc_180050916
0x1800503b1  lea     rdi, WPP_GLOBAL_Control
0x1800503b8  cmp     r10, rdi
0x1800503bb  jz      short loc_1800503D9
0x1800503bd  test    byte ptr [r10+1Ch], 8
0x1800503c2  jz      short loc_1800503D9
0x1800503c4  mov     edx, 25h ; '%'
0x1800503c9  mov     rcx, [r10+10h]
0x1800503cd  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x1800503d4  call    WPP_SF_
0x1800503d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800503e0  mov     ecx, 3AE8h; unsigned __int64
0x1800503e5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800503ea  mov     r15, rax
0x1800503ed  test    rax, rax
0x1800503f0  jnz     short loc_18005041F
0x1800503f2  mov     ebx, 8007000Eh
0x1800503f7  mov     r10, cs:WPP_GLOBAL_Control
0x1800503fe  cmp     r10, rdi
0x180050401  jz      loc_180050290
0x180050407  lea     edi, [rax+2]
0x18005040a  test    [r10+1Ch], dil
0x18005040e  jz      loc_180050289
0x180050414  lea     edx, [rax+27h]
0x180050417  mov     r9d, ebx
0x18005041a  jmp     loc_180050272
0x18005041f  mov     rcx, [r13+490h]
0x180050426  lea     r9, [rbp+57h+var_88]
0x18005042a  mov     edx, 4
0x18005042f  lea     r8d, [rdx+3]
0x180050433  call    FveDatasetGetFirst
0x180050438  mov     ecx, eax; int
0x18005043a  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18005043f  mov     ebx, eax
0x180050441  test    eax, eax
0x180050443  jns     loc_1800504D2
0x180050449  mov     r10, cs:WPP_GLOBAL_Control
0x180050450  cmp     r10, rdi
0x180050453  jz      short loc_180050484
0x180050455  mov     edi, 2
0x18005045a  test    [r10+1Ch], dil
0x18005045e  jz      short loc_18005047D
0x180050460  lea     edx, [rdi+26h]
0x180050463  mov     r9d, eax
0x180050466  mov     rcx, [r10+10h]
0x18005046a  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x180050471  call    WPP_SF_d
0x180050476  mov     r10, cs:WPP_GLOBAL_Control
0x18005047d  lea     rdi, WPP_GLOBAL_Control
0x180050484  mov     rcx, [rbp+57h+var_88]
0x180050488  test    rcx, rcx
0x18005048b  jz      short loc_180050499
0x18005048d  call    FveDatumFree
0x180050492  mov     r10, cs:WPP_GLOBAL_Control
0x180050499  mov     rcx, [rbp+57h+var_80]
0x18005049d  test    rcx, rcx
0x1800504a0  jz      short loc_1800504AE
0x1800504a2  call    FveDatumFree
0x1800504a7  mov     r10, cs:WPP_GLOBAL_Control
0x1800504ae  test    r15, r15
0x1800504b1  jz      loc_180050290
0x1800504b7  mov     rcx, r15
0x1800504ba  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800504c1  nop     dword ptr [rax+rax+00h]
0x1800504c6  mov     r10, cs:WPP_GLOBAL_Control
0x1800504cd  jmp     loc_180050290
0x1800504d2  mov     rax, [rsi]
0x1800504d5  sub     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data1
0x1800504dc  jnz     short loc_1800504E9
0x1800504de  mov     rax, [rsi+8]
0x1800504e2  sub     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data4
0x1800504e9  test    rax, rax
0x1800504ec  jz      short loc_18005055F
0x1800504ee  mov     rax, [rsi]
0x1800504f1  sub     rax, qword ptr cs:GUID_DEFAULT_BOOT_ENTRY.Data1
0x1800504f8  jnz     short loc_180050505
0x1800504fa  mov     rax, [rsi+8]
0x1800504fe  sub     rax, qword ptr cs:GUID_DEFAULT_BOOT_ENTRY.Data4
0x180050505  test    rax, rax
0x180050508  jz      short loc_18005055F
0x18005050a  movups  xmm0, xmmword ptr [rsi]
0x18005050d  movdqu  [rbp+57h+var_60], xmm0
0x180050512  lea     r9, [rbp+57h+var_50]
0x180050516  mov     r8d, 10h
0x18005051c  lea     rdx, [rbp+57h+var_60]
0x180050520  xor     ecx, ecx
0x180050522  call    FveDatumValidationInfoDataEntry
0x180050527  mov     ecx, eax; int
0x180050529  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18005052e  mov     ebx, eax
0x180050530  test    eax, eax
0x180050532  jns     loc_180050656
0x180050538  mov     r10, cs:WPP_GLOBAL_Control
0x18005053f  cmp     r10, rdi
0x180050542  jz      loc_180050484
0x180050548  mov     edi, 2
0x18005054d  test    [r10+1Ch], dil
0x180050551  jz      loc_18005047D
0x180050557  lea     edx, [rdi+2Ah]
0x18005055a  jmp     loc_180050463
0x18005055f  lea     rcx, [rbp+57h+var_78]
0x180050563  call    cs:__imp_BcdOpenSystemStore
0x18005056a  nop     dword ptr [rax+rax+00h]
0x18005056f  mov     ecx, eax; int
0x180050571  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180050576  mov     ebx, eax
0x180050578  test    eax, eax
0x18005057a  jns     short loc_1800505A3
0x18005057c  mov     r10, cs:WPP_GLOBAL_Control
0x180050583  cmp     r10, rdi
0x180050586  jz      loc_180050484
0x18005058c  mov     edi, 2
0x180050591  test    [r10+1Ch], dil
0x180050595  jz      loc_18005047D
0x18005059b  lea     edx, [rdi+27h]
0x18005059e  jmp     loc_180050463
0x1800505a3  mov     rcx, [rbp+57h+var_78]
0x1800505a7  lea     r8, [rbp+57h+var_70]
0x1800505ab  mov     rdx, rsi
0x1800505ae  call    cs:__imp_BcdOpenObject
0x1800505b5  nop     dword ptr [rax+rax+00h]
0x1800505ba  mov     ecx, eax; int
0x1800505bc  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800505c1  mov     ebx, eax
0x1800505c3  test    eax, eax
0x1800505c5  jns     short loc_180050605
0x1800505c7  mov     r10, cs:WPP_GLOBAL_Control
0x1800505ce  cmp     r10, rdi
0x1800505d1  jz      loc_180050484
0x1800505d7  mov     edi, 2
0x1800505dc  test    [r10+1Ch], dil
0x1800505e0  jz      loc_18005047D
0x1800505e6  mov     rcx, [r10+10h]
0x1800505ea  lea     edx, [rdi+28h]
0x1800505ed  mov     r9, rsi
0x1800505f0  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800505f4  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x1800505fb  call    WPP_SF__guid_D
0x180050600  jmp     loc_180050476
0x180050605  mov     rcx, [rbp+57h+var_70]
0x180050609  lea     r9, [rbp+57h+var_60]
0x18005060d  xor     r8d, r8d
0x180050610  xor     edx, edx
0x180050612  call    cs:__imp_BcdQueryObject
0x180050619  nop     dword ptr [rax+rax+00h]
0x18005061e  mov     ecx, eax; int
0x180050620  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180050625  mov     ebx, eax
0x180050627  test    eax, eax
0x180050629  jns     loc_180050512
0x18005062f  mov     r10, cs:WPP_GLOBAL_Control
0x180050636  cmp     r10, rdi
0x180050639  jz      loc_180050484
0x18005063f  mov     edi, 2
0x180050644  test    [r10+1Ch], dil
0x180050648  jz      loc_18005047D
0x18005064e  lea     edx, [rdi+29h]
0x180050651  jmp     loc_180050463
0x180050656  mov     rcx, [rbp+57h+var_88]
0x18005065a  lea     r9, [rbp+57h+var_8F]
0x18005065e  lea     r8, [rbp+57h+var_8E]
0x180050662  mov     dword ptr [rbp+57h+var_50], 20004h
0x180050669  lea     rdx, [rbp+57h+var_50]
0x18005066d  mov     edi, 2
  ... truncated ...
```
