# CFveApiBase::GetBootEntryValidationOverride(_GUID const *,uchar *)

- ea: `0x1800566a4`
- end: `0x1800569bb`
- name: `?GetBootEntryValidationOverride@CFveApiBase@@SAJPEBU_GUID@@PEAE@Z`
- size: `791`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18005019c`
- `0x18009c910`
- `0x18009e2f8`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x18000ba30`
- `0x180018b10`
- `0x180047570`
- `0x1800566a4`
- `0x18009ba80`
- `0x18009befc`
- `0x18009f384`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseObject` at `0x18005694f`
- `bcd!BcdCloseObject` at `0x1801213ec`
- `bcd!BcdCloseObject` at `0x18005694f`
- `bcd!BcdCloseObject` at `0x1801213ec`
- `bcd!BcdOpenObject` at `0x180056819`
- `bcd!BcdOpenObject` at `0x180056819`
- `bcd!BcdCloseStore` at `0x180056963`
- `bcd!BcdCloseStore` at `0x1801213fc`
- `bcd!BcdCloseStore` at `0x180056963`
- `bcd!BcdCloseStore` at `0x1801213fc`
- `bcd!BcdOpenSystemStore` at `0x180056731`
- `bcd!BcdOpenSystemStore` at `0x180056731`

## pseudocode

```c
__int64 __fastcall CFveApiBase::GetBootEntryValidationOverride(const struct _GUID *a1, unsigned __int8 *a2)
{
  int v4; // eax
  int DoesRegKeyExist; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  int BcdElementData; // ebx
  PVOID *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  void *v15; // rax
  int v17; // [rsp+34h] [rbp-54h] BYREF
  void *lpMem; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v19; // [rsp+40h] [rbp-48h] BYREF
  void *v20; // [rsp+48h] [rbp-40h] BYREF
  void *v21; // [rsp+50h] [rbp-38h] BYREF
  struct _GUID v22; // [rsp+58h] [rbp-30h] BYREF

  v20 = 0;
  v21 = 0;
  lpMem = 0;
  v19 = 0;
  *a2 = 0;
  v17 = 0;
  v22 = *a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, &WPP_1559182127783aab3882fe828952d989_Traceguids);
  v4 = BcdOpenSystemStore(&v20, a2);
  DoesRegKeyExist = FromNtStatus(v4);
  BcdElementData = DoesRegKeyExist;
  if ( DoesRegKeyExist < 0 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = 194;
LABEL_8:
      v11 = (unsigned int)DoesRegKeyExist;
LABEL_40:
      WPP_SF_d(v9[2], v10, &WPP_1559182127783aab3882fe828952d989_Traceguids, v11);
      goto LABEL_41;
    }
    goto LABEL_42;
  }
  v12 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&GUID_CURRENT_BOOT_ENTRY.Data1;
  if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_CURRENT_BOOT_ENTRY.Data1 )
    v12 = *(_QWORD *)a1->Data4 - *(_QWORD *)GUID_CURRENT_BOOT_ENTRY.Data4;
  if ( v12 )
  {
LABEL_21:
    v13 = BcdOpenObject(v20, &v22, &v21);
    BcdElementData = FromNtStatus(v13);
    if ( BcdElementData >= 0 )
    {
      BcdElementData = CFveApiBase::GetBcdElementData(v21, 0x16BDEDECu, &lpMem, &v19);
      if ( BcdElementData >= 0 && *(_BYTE *)lpMem )
      {
        *a2 = 1;
      }
      else
      {
        if ( BcdElementData != -2147023728 )
        {
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_42;
          v10 = 199;
LABEL_39:
          v11 = (unsigned int)BcdElementData;
          goto LABEL_40;
        }
        BcdElementData = 0;
      }
    }
    else
    {
      v14 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&GUID_CURRENT_BOOT_ENTRY.Data1;
      if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_CURRENT_BOOT_ENTRY.Data1 )
        v14 = *(_QWORD *)a1->Data4 - *(_QWORD *)GUID_CURRENT_BOOT_ENTRY.Data4;
      if ( !v14 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_42;
        v10 = 197;
        goto LABEL_39;
      }
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_42;
      WPP_SF__guid_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        198,
        &WPP_1559182127783aab3882fe828952d989_Traceguids,
        a1,
        BcdElementData);
    }
LABEL_41:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_42;
  }
  DoesRegKeyExist = NgscbpDoesRegKeyExist(v7, v6, &v17);
  BcdElementData = DoesRegKeyExist;
  if ( DoesRegKeyExist >= 0 )
  {
    if ( v17 )
    {
      DoesRegKeyExist = CFveApiBase::GetAssociatedOs(v20, &v22);
      BcdElementData = DoesRegKeyExist;
      if ( DoesRegKeyExist < 0 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v10 = 196;
          goto LABEL_8;
        }
        goto LABEL_42;
      }
    }
    goto LABEL_21;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v10 = 195;
    goto LABEL_8;
  }
LABEL_42:
  if ( lpMem )
  {
    CFveApiBase::FastFree(lpMem);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v15 = v20;
  if ( v20 )
  {
    if ( v21 )
    {
      BcdCloseObject(v21);
      v15 = v20;
    }
    BcdCloseStore(v15, v6);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x20) != 0 )
    WPP_SF_d(v9[2], 200, &WPP_1559182127783aab3882fe828952d989_Traceguids, (unsigned int)BcdElementData);
  return (unsigned int)BcdElementData;
}

```

## disassembly

```asm
0x1800566a4  mov     r11, rsp
0x1800566a7  mov     [r11+18h], rbx
0x1800566ab  push    rsi
0x1800566ac  push    r12
0x1800566ae  push    r14
0x1800566b0  sub     rsp, 70h
0x1800566b4  mov     rax, cs:__security_cookie
0x1800566bb  xor     rax, rsp
0x1800566be  mov     [rsp+88h+var_20], rax
0x1800566c3  mov     r14, rdx
0x1800566c6  mov     rsi, rcx
0x1800566c9  mov     qword ptr [r11-40h], 0
0x1800566d1  mov     qword ptr [r11-38h], 0
0x1800566d9  mov     qword ptr [r11-50h], 0
0x1800566e1  mov     [rsp+88h+var_48], 0
0x1800566e9  mov     byte ptr [rdx], 0
0x1800566ec  mov     [rsp+88h+var_54], 0
0x1800566f4  movups  xmm0, xmmword ptr [rcx]
0x1800566f7  movdqu  xmmword ptr [rsp+88h+var_30.Data1], xmm0
0x1800566fd  lea     r12, WPP_GLOBAL_Control
0x180056704  mov     rcx, cs:WPP_GLOBAL_Control
0x18005670b  cmp     rcx, r12
0x18005670e  jz      short loc_18005672C
0x180056710  test    byte ptr [rcx+1Ch], 20h
0x180056714  jz      short loc_18005672C
0x180056716  mov     edx, 0C1h
0x18005671b  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x180056722  mov     rcx, [rcx+10h]
0x180056726  call    WPP_SF_
0x18005672b  nop
0x18005672c  lea     rcx, [rsp+88h+var_40]
0x180056731  call    cs:__imp_BcdOpenSystemStore
0x180056738  nop     dword ptr [rax+rax+00h]
0x18005673d  mov     ecx, eax; int
0x18005673f  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180056744  mov     ebx, eax
0x180056746  mov     [rsp+88h+var_58], eax
0x18005674a  test    eax, eax
0x18005674c  jns     short loc_180056775
0x18005674e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056755  cmp     rcx, r12
0x180056758  jz      loc_180056922
0x18005675e  test    byte ptr [rcx+1Ch], 2
0x180056762  jz      loc_180056922
0x180056768  mov     edx, 0C2h
0x18005676d  mov     r9d, eax
0x180056770  jmp     loc_18005690B
0x180056775  mov     rax, [rsi]
0x180056778  sub     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data1
0x18005677f  jnz     short loc_18005678C
0x180056781  mov     rax, [rsi+8]
0x180056785  sub     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data4
0x18005678c  test    rax, rax
0x18005678f  jnz     short loc_18005680A
0x180056791  lea     r8, [rsp+88h+var_54]
0x180056796  call    NgscbpDoesRegKeyExist
0x18005679b  mov     ebx, eax
0x18005679d  mov     [rsp+88h+var_58], eax
0x1800567a1  test    eax, eax
0x1800567a3  jns     short loc_1800567C6
0x1800567a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800567ac  cmp     rcx, r12
0x1800567af  jz      loc_180056922
0x1800567b5  test    byte ptr [rcx+1Ch], 2
0x1800567b9  jz      loc_180056922
0x1800567bf  mov     edx, 0C3h
0x1800567c4  jmp     short loc_18005676D
0x1800567c6  cmp     [rsp+88h+var_54], 0
0x1800567cb  jz      short loc_18005680A
0x1800567cd  lea     rdx, [rsp+88h+var_30]; struct _GUID *
0x1800567d2  mov     rcx, [rsp+88h+var_40]; void *
0x1800567d7  call    ?GetAssociatedOs@CFveApiBase@@KAJPEAXPEAU_GUID@@@Z; CFveApiBase::GetAssociatedOs(void *,_GUID *)
0x1800567dc  mov     ebx, eax
0x1800567de  mov     [rsp+88h+var_58], eax
0x1800567e2  test    eax, eax
0x1800567e4  jns     short loc_18005680A
0x1800567e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800567ed  cmp     rcx, r12
0x1800567f0  jz      loc_180056922
0x1800567f6  test    byte ptr [rcx+1Ch], 2
0x1800567fa  jz      loc_180056922
0x180056800  mov     edx, 0C4h
0x180056805  jmp     loc_18005676D
0x18005680a  lea     r8, [rsp+88h+var_38]
0x18005680f  lea     rdx, [rsp+88h+var_30]
0x180056814  mov     rcx, [rsp+88h+var_40]
0x180056819  call    cs:__imp_BcdOpenObject
0x180056820  nop     dword ptr [rax+rax+00h]
0x180056825  mov     ecx, eax; int
0x180056827  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18005682c  mov     ebx, eax
0x18005682e  mov     [rsp+88h+var_58], eax
0x180056832  test    eax, eax
0x180056834  jns     short loc_1800568AE
0x180056836  mov     rax, [rsi]
0x180056839  sub     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data1
0x180056840  jnz     short loc_18005684D
0x180056842  mov     rax, [rsi+8]
0x180056846  sub     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data4
0x18005684d  test    rax, rax
0x180056850  jnz     short loc_180056876
0x180056852  mov     rcx, cs:WPP_GLOBAL_Control
0x180056859  cmp     rcx, r12
0x18005685c  jz      loc_180056922
0x180056862  test    byte ptr [rcx+1Ch], 2
0x180056866  jz      loc_180056922
0x18005686c  mov     edx, 0C5h
0x180056871  jmp     loc_180056908
0x180056876  mov     rcx, cs:WPP_GLOBAL_Control
0x18005687d  cmp     rcx, r12
0x180056880  jz      loc_180056922
0x180056886  test    byte ptr [rcx+1Ch], 2
0x18005688a  jz      loc_180056922
0x180056890  mov     edx, 0C6h
0x180056895  mov     [rsp+88h+var_68], ebx
0x180056899  mov     r9, rsi
0x18005689c  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x1800568a3  mov     rcx, [rcx+10h]
0x1800568a7  call    WPP_SF__guid_D
0x1800568ac  jmp     short loc_18005691B
0x1800568ae  lea     r9, [rsp+88h+var_48]; unsigned int *
0x1800568b3  lea     r8, [rsp+88h+lpMem]; void **
0x1800568b8  mov     edx, 16BDEDECh; unsigned int
0x1800568bd  mov     rcx, [rsp+88h+var_38]; void *
0x1800568c2  call    ?GetBcdElementData@CFveApiBase@@SAJPEAXKPEAPEAXPEAK@Z; CFveApiBase::GetBcdElementData(void *,ulong,void * *,ulong *)
0x1800568c7  mov     ebx, eax
0x1800568c9  mov     [rsp+88h+var_58], eax
0x1800568cd  test    eax, eax
0x1800568cf  js      short loc_1800568E1
0x1800568d1  mov     rax, [rsp+88h+lpMem]
0x1800568d6  cmp     byte ptr [rax], 0
0x1800568d9  jz      short loc_1800568E1
0x1800568db  mov     byte ptr [r14], 1
0x1800568df  jmp     short loc_18005691B
0x1800568e1  cmp     ebx, 80070490h
0x1800568e7  jnz     short loc_1800568F1
0x1800568e9  xor     ebx, ebx
0x1800568eb  mov     [rsp+88h+var_58], ebx
0x1800568ef  jmp     short loc_18005691B
0x1800568f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800568f8  cmp     rcx, r12
0x1800568fb  jz      short loc_180056922
0x1800568fd  test    byte ptr [rcx+1Ch], 2
0x180056901  jz      short loc_180056922
0x180056903  mov     edx, 0C7h
0x180056908  mov     r9d, ebx
0x18005690b  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x180056912  mov     rcx, [rcx+10h]
0x180056916  call    WPP_SF_d
0x18005691b  mov     rcx, cs:WPP_GLOBAL_Control
0x180056922  mov     rax, [rsp+88h+lpMem]
0x180056927  test    rax, rax
0x18005692a  jz      short loc_18005693B
0x18005692c  mov     rcx, rax; lpMem
0x18005692f  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180056934  mov     rcx, cs:WPP_GLOBAL_Control
0x18005693b  mov     rax, [rsp+88h+var_40]
0x180056940  test    rax, rax
0x180056943  jz      short loc_180056976
0x180056945  mov     rcx, [rsp+88h+var_38]
0x18005694a  test    rcx, rcx
0x18005694d  jz      short loc_180056960
0x18005694f  call    cs:__imp_BcdCloseObject
0x180056956  nop     dword ptr [rax+rax+00h]
0x18005695b  mov     rax, [rsp+88h+var_40]
0x180056960  mov     rcx, rax
0x180056963  call    cs:__imp_BcdCloseStore
0x18005696a  nop     dword ptr [rax+rax+00h]
0x18005696f  mov     rcx, cs:WPP_GLOBAL_Control
0x180056976  cmp     rcx, r12
0x180056979  jz      short loc_180056999
0x18005697b  test    byte ptr [rcx+1Ch], 20h
0x18005697f  jz      short loc_180056999
0x180056981  mov     edx, 0C8h
0x180056986  mov     r9d, ebx
0x180056989  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x180056990  mov     rcx, [rcx+10h]
0x180056994  call    WPP_SF_d
0x180056999  mov     eax, ebx
0x18005699b  mov     rcx, [rsp+88h+var_20]
0x1800569a0  xor     rcx, rsp; StackCookie
0x1800569a3  call    __security_check_cookie
0x1800569a8  mov     rbx, [rsp+88h+arg_10]
0x1800569b0  add     rsp, 70h
0x1800569b4  pop     r14
0x1800569b6  pop     r12
0x1800569b8  pop     rsi
0x1800569b9  retn
0x1801213bf  push    rbp
0x1801213c1  sub     rsp, 30h
0x1801213c5  mov     rbp, rdx
0x1801213c8  mov     rcx, [rbp+38h]; lpMem
0x1801213cc  test    rcx, rcx
0x1801213cf  jz      short loc_1801213D7
0x1801213d1  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x1801213d6  nop
0x1801213d7  mov     rcx, [rbp+48h]
0x1801213db  test    rcx, rcx
0x1801213de  jz      short loc_180121409
0x1801213e0  mov     rax, [rbp+50h]
0x1801213e4  test    rax, rax
0x1801213e7  jz      short loc_1801213FC
0x1801213e9  mov     rcx, rax
0x1801213ec  call    cs:__imp_BcdCloseObject
0x1801213f3  nop     dword ptr [rax+rax+00h]
0x1801213f8  mov     rcx, [rbp+48h]
0x1801213fc  call    cs:__imp_BcdCloseStore
0x180121403  nop     dword ptr [rax+rax+00h]
0x180121408  nop
0x180121409  add     rsp, 30h
0x18012140d  pop     rbp
0x18012140e  retn
```
