# CSyncConflict::GetProperty(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x18001d2f0`
- end: `0x18001d522`
- name: `?GetProperty@CSyncConflict@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `562`
- prototype: `int(CSyncConflict *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180013dfc`
- `0x18001d2f0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d505`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d505`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x18001d4c1`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x18001d4c1`

## pseudocode

```c
__int64 __fastcall CSyncConflict::GetProperty(
        CSyncConflict *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3)
{
  int v5; // ebx
  unsigned int v6; // ecx
  __int64 v7; // rdx
  __int64 v8; // rax
  int v10; // [rsp+3Ch] [rbp-C4h]
  const PROPERTYKEY *v11; // [rsp+40h] [rbp-C0h]
  __int64 (__fastcall *v12)(CSyncConflict *__hidden, struct tagPROPVARIANT *); // [rsp+48h] [rbp-B8h]
  _DWORD v13[2]; // [rsp+50h] [rbp-B0h]
  const PROPERTYKEY *v14; // [rsp+58h] [rbp-A8h]
  int (*v15)(CSyncConflict *__hidden, struct tagPROPVARIANT *); // [rsp+60h] [rbp-A0h]
  int v16; // [rsp+68h] [rbp-98h]
  int v17; // [rsp+6Ch] [rbp-94h]
  const PROPERTYKEY *v18; // [rsp+70h] [rbp-90h]
  int (*v19)(CSyncConflict *__hidden, struct tagPROPVARIANT *); // [rsp+78h] [rbp-88h]
  int v20; // [rsp+80h] [rbp-80h]
  int v21; // [rsp+84h] [rbp-7Ch]
  const PROPERTYKEY *v22; // [rsp+88h] [rbp-78h]
  int (*v23)(CSyncConflict *__hidden, struct tagPROPVARIANT *); // [rsp+90h] [rbp-70h]
  int v24; // [rsp+98h] [rbp-68h]
  int v25; // [rsp+9Ch] [rbp-64h]
  const PROPERTYKEY *v26; // [rsp+A0h] [rbp-60h]
  int (*v27)(CSyncConflict *__hidden, struct tagPROPVARIANT *); // [rsp+A8h] [rbp-58h]
  int v28; // [rsp+B0h] [rbp-50h]
  int v29; // [rsp+B4h] [rbp-4Ch]
  const PROPERTYKEY *v30; // [rsp+B8h] [rbp-48h]
  int (*v31)(CSyncConflict *__hidden, struct tagPROPVARIANT *); // [rsp+C0h] [rbp-40h]
  int v32; // [rsp+C8h] [rbp-38h]
  int v33; // [rsp+CCh] [rbp-34h]
  const PROPERTYKEY *v34; // [rsp+D0h] [rbp-30h]
  int (*v35)(CSyncConflict *__hidden, struct tagPROPVARIANT *); // [rsp+D8h] [rbp-28h]
  int v36; // [rsp+E0h] [rbp-20h]
  int v37; // [rsp+E4h] [rbp-1Ch]
  const PROPERTYKEY *v38; // [rsp+E8h] [rbp-18h]
  int (*v39)(CSyncConflict *__hidden, struct tagPROPVARIANT *); // [rsp+F0h] [rbp-10h]
  int v40; // [rsp+F8h] [rbp-8h]
  int v41; // [rsp+FCh] [rbp-4h]
  const PROPERTYKEY *v42; // [rsp+100h] [rbp+0h]
  __int64 (__fastcall *v43)(CSyncConflict *__hidden, struct tagPROPVARIANT *); // [rsp+108h] [rbp+8h]
  int v44; // [rsp+110h] [rbp+10h]
  int v45; // [rsp+114h] [rbp+14h]
  PWSTR ppszCanonicalName; // [rsp+148h] [rbp+48h] BYREF

  v13[0] = 0;
  v11 = &PKEY_ItemNameDisplay;
  v16 = 0;
  v12 = CSyncConflict::_GetConflictName;
  v13[1] = v10;
  v5 = -2147467259;
  v20 = 0;
  v14 = &PKEY_Sync_ConflictDescription;
  v6 = 0;
  v24 = 0;
  v15 = CSyncConflict::_GetConflictDescription;
  v17 = v10;
  v18 = &PKEY_Sync_HandlerName;
  v19 = CSyncConflict::_GetConflictSyncHandler;
  v21 = v10;
  v22 = &PKEY_Sync_ItemName;
  v23 = CSyncConflict::_GetConflictSyncItem;
  v25 = v10;
  v26 = &PKEY_Sync_ItemID;
  v27 = CSyncConflict::_GetConflictSyncItemID;
  v29 = v10;
  v30 = &PKEY_Sync_ConflictFirstLocation;
  v31 = CSyncConflict::_GetConflictFirstLocation;
  v33 = v10;
  v34 = &PKEY_Sync_ConflictSecondLocation;
  v35 = CSyncConflict::_GetConflictSecondLocation;
  v37 = v10;
  v38 = &PKEY_Sync_HandlerID;
  v39 = CSyncConflict::_GetSyncHandlerID;
  v41 = v10;
  v42 = &PKEY_DateModified;
  v43 = CSyncConflict::_GetConflictTime;
  v45 = v10;
  v28 = 0;
  v32 = 0;
  v36 = 0;
  v40 = 0;
  v44 = 0;
  while ( v6 < 9 )
  {
    v7 = (__int64)*(&v11 + 3 * (int)v6);
    if ( a2->pid == *(_DWORD *)(v7 + 16) )
    {
      v8 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)v7;
      if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)v7 )
        v8 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)(v7 + 8);
      if ( !v8 )
      {
        v5 = (*(__int64 (__fastcall **)(char *, struct tagPROPVARIANT *))&v13[6 * v6 - 2])(
               (CSyncConflict *)((char *)this + (int)v13[6 * v6]),
               a3);
        if ( v5 >= 0 )
          return (unsigned int)v5;
        break;
      }
    }
    ++v6;
  }
  ppszCanonicalName = 0;
  if ( PSGetNameFromPropertyKey(a2, &ppszCanonicalName) >= 0 )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids,
        (_DWORD)ppszCanonicalName,
        v5);
    }
    CoTaskMemFree(ppszCanonicalName);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001d2f0  mov     [rsp-8+arg_0], rbx
0x18001d2f5  mov     [rsp-8+arg_8], rdi
0x18001d2fa  push    rbp
0x18001d2fb  lea     rbp, [rsp-20h]
0x18001d300  sub     rsp, 120h
0x18001d307  lea     rax, PKEY_ItemNameDisplay
0x18001d30e  mov     [rsp+120h+var_D0], 0
0x18001d316  mov     [rsp+120h+var_E0], rax
0x18001d31b  mov     r10, rcx
0x18001d31e  lea     rax, ?_GetConflictName@CSyncConflict@@AEAAJPEAUtagPROPVARIANT@@@Z; CSyncConflict::_GetConflictName(tagPROPVARIANT *)
0x18001d325  mov     [rsp+120h+var_B8], 0
0x18001d32d  mov     [rsp+120h+var_D8], rax
0x18001d332  mov     r9, r8
0x18001d335  mov     eax, [rsp+120h+var_E4]
0x18001d339  mov     rdi, rdx
0x18001d33c  mov     [rsp+120h+var_CC], eax
0x18001d340  mov     ebx, 80004005h
0x18001d345  lea     rax, PKEY_Sync_ConflictDescription
0x18001d34c  mov     [rbp+20h+var_A0], 0
0x18001d353  mov     [rsp+120h+var_C8], rax
0x18001d358  xor     ecx, ecx
0x18001d35a  lea     rax, ?_GetConflictDescription@CSyncConflict@@AEAAJPEAUtagPROPVARIANT@@@Z; CSyncConflict::_GetConflictDescription(tagPROPVARIANT *)
0x18001d361  mov     [rbp+20h+var_88], 0
0x18001d368  mov     [rsp+120h+var_C0], rax
0x18001d36d  mov     eax, [rsp+120h+var_E4]
0x18001d371  mov     [rsp+120h+var_B4], eax
0x18001d375  lea     rax, PKEY_Sync_HandlerName
0x18001d37c  mov     [rsp+120h+var_B0], rax
0x18001d381  lea     rax, ?_GetConflictSyncHandler@CSyncConflict@@AEAAJPEAUtagPROPVARIANT@@@Z; CSyncConflict::_GetConflictSyncHandler(tagPROPVARIANT *)
0x18001d388  mov     [rsp+120h+var_A8], rax
0x18001d38d  mov     eax, [rsp+120h+var_E4]
0x18001d391  mov     [rbp+20h+var_9C], eax
0x18001d394  lea     rax, PKEY_Sync_ItemName
0x18001d39b  mov     [rbp+20h+var_98], rax
0x18001d39f  lea     rax, ?_GetConflictSyncItem@CSyncConflict@@AEAAJPEAUtagPROPVARIANT@@@Z; CSyncConflict::_GetConflictSyncItem(tagPROPVARIANT *)
0x18001d3a6  mov     [rbp+20h+var_90], rax
0x18001d3aa  mov     eax, [rsp+120h+var_E4]
0x18001d3ae  mov     [rbp+20h+var_84], eax
0x18001d3b1  lea     rax, PKEY_Sync_ItemID
0x18001d3b8  mov     [rbp+20h+var_80], rax
0x18001d3bc  lea     rax, ?_GetConflictSyncItemID@CSyncConflict@@AEAAJPEAUtagPROPVARIANT@@@Z; CSyncConflict::_GetConflictSyncItemID(tagPROPVARIANT *)
0x18001d3c3  mov     [rbp+20h+var_78], rax
0x18001d3c7  mov     eax, [rsp+120h+var_E4]
0x18001d3cb  mov     [rbp+20h+var_6C], eax
0x18001d3ce  lea     rax, PKEY_Sync_ConflictFirstLocation
0x18001d3d5  mov     [rbp+20h+var_68], rax
0x18001d3d9  lea     rax, ?_GetConflictFirstLocation@CSyncConflict@@AEAAJPEAUtagPROPVARIANT@@@Z; CSyncConflict::_GetConflictFirstLocation(tagPROPVARIANT *)
0x18001d3e0  mov     [rbp+20h+var_60], rax
0x18001d3e4  mov     eax, [rsp+120h+var_E4]
0x18001d3e8  mov     [rbp+20h+var_54], eax
0x18001d3eb  lea     rax, PKEY_Sync_ConflictSecondLocation
0x18001d3f2  mov     [rbp+20h+var_50], rax
0x18001d3f6  lea     rax, ?_GetConflictSecondLocation@CSyncConflict@@AEAAJPEAUtagPROPVARIANT@@@Z; CSyncConflict::_GetConflictSecondLocation(tagPROPVARIANT *)
0x18001d3fd  mov     [rbp+20h+var_48], rax
0x18001d401  mov     eax, [rsp+120h+var_E4]
0x18001d405  mov     [rbp+20h+var_3C], eax
0x18001d408  lea     rax, PKEY_Sync_HandlerID
0x18001d40f  mov     [rbp+20h+var_38], rax
0x18001d413  lea     rax, ?_GetSyncHandlerID@CSyncConflict@@AEAAJPEAUtagPROPVARIANT@@@Z; CSyncConflict::_GetSyncHandlerID(tagPROPVARIANT *)
0x18001d41a  mov     [rbp+20h+var_30], rax
0x18001d41e  mov     eax, [rsp+120h+var_E4]
0x18001d422  mov     [rbp+20h+var_24], eax
0x18001d425  lea     rax, PKEY_DateModified
0x18001d42c  mov     [rbp+20h+var_20], rax
0x18001d430  lea     rax, ?_GetConflictTime@CSyncConflict@@AEAAJPEAUtagPROPVARIANT@@@Z; CSyncConflict::_GetConflictTime(tagPROPVARIANT *)
0x18001d437  mov     [rbp+20h+var_18], rax
0x18001d43b  mov     eax, [rsp+120h+var_E4]
0x18001d43f  mov     [rbp+20h+var_C], eax
0x18001d442  mov     [rbp+20h+var_70], 0
0x18001d449  mov     [rbp+20h+var_58], 0
0x18001d450  mov     [rbp+20h+var_40], 0
0x18001d457  mov     [rbp+20h+var_28], 0
0x18001d45e  mov     [rbp+20h+var_10], 0
0x18001d465  cmp     ecx, 9
0x18001d468  jnb     short loc_18001D4B2
0x18001d46a  movsxd  rax, ecx
0x18001d46d  lea     r8, [rax+rax*2]
0x18001d471  mov     rdx, [rsp+r8*8+120h+var_E0]
0x18001d476  mov     eax, [rdx+10h]
0x18001d479  cmp     [rdi+10h], eax
0x18001d47c  jnz     short loc_18001D493
0x18001d47e  mov     rax, [rdi]
0x18001d481  sub     rax, [rdx]
0x18001d484  jnz     short loc_18001D48E
0x18001d486  mov     rax, [rdi+8]
0x18001d48a  sub     rax, [rdx+8]
0x18001d48e  test    rax, rax
0x18001d491  jz      short loc_18001D497
0x18001d493  inc     ecx
0x18001d495  jmp     short loc_18001D465
0x18001d497  movsxd  rcx, [rsp+r8*8+120h+var_D0]
0x18001d49c  mov     rdx, r9
0x18001d49f  mov     rax, [rsp+r8*8+120h+var_D8]
0x18001d4a4  add     rcx, r10
0x18001d4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4ac  mov     ebx, eax
0x18001d4ae  test    eax, eax
0x18001d4b0  jns     short loc_18001D50B
0x18001d4b2  lea     rdx, [rbp+20h+ppszCanonicalName]; ppszCanonicalName
0x18001d4b6  mov     [rbp+20h+ppszCanonicalName], 0
0x18001d4be  mov     rcx, rdi; propkey
0x18001d4c1  call    cs:__imp_PSGetNameFromPropertyKey
0x18001d4c7  test    eax, eax
0x18001d4c9  js      short loc_18001D50B
0x18001d4cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4d2  lea     rax, WPP_GLOBAL_Control
0x18001d4d9  cmp     rcx, rax
0x18001d4dc  jz      short loc_18001D501
0x18001d4de  test    byte ptr [rcx+1Ch], 2
0x18001d4e2  jz      short loc_18001D501
0x18001d4e4  mov     r9, [rbp+20h+ppszCanonicalName]
0x18001d4e8  lea     r8, WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids
0x18001d4ef  mov     rcx, [rcx+10h]
0x18001d4f3  mov     edx, 17h
0x18001d4f8  mov     [rsp+120h+var_100], ebx
0x18001d4fc  call    WPP_SF_Sd
0x18001d501  mov     rcx, [rbp+20h+ppszCanonicalName]; pv
0x18001d505  call    cs:__imp_CoTaskMemFree
0x18001d50b  lea     r11, [rsp+120h+var_s0]
0x18001d513  mov     eax, ebx
0x18001d515  mov     rbx, [r11+10h]
0x18001d519  mov     rdi, [r11+18h]
0x18001d51d  mov     rsp, r11
0x18001d520  pop     rbp
0x18001d521  retn
```
