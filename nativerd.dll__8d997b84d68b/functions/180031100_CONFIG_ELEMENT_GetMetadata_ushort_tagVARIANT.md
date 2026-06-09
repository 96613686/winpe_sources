# CONFIG_ELEMENT::GetMetadata(ushort *,tagVARIANT *)

- ea: `0x180031100`
- end: `0x1800316a2`
- name: `?GetMetadata@CONFIG_ELEMENT@@UEAAJPEAGPEAUtagVARIANT@@@Z`
- size: `1442`
- prototype: `__int64 __fastcall(CONFIG_ELEMENT *__hidden this, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x1800293d4`
- `0x1800299d8`
- `0x18002f724`
- `0x180031100`
- `0x1800316a8`
- `0x180031df8`
- `0x18004ab70`
- `0x180059bf6`
- `0x18005b010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180031296`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180031296`
- `OLEAUT32!__imp_SysAllocString` at `0x18003129f`
- `OLEAUT32!__imp_SysAllocString` at `0x180031573`
- `OLEAUT32!__imp_SysAllocString` at `0x18003129f`
- `OLEAUT32!__imp_SysAllocString` at `0x180031573`

## string_xrefs

- `0x1800311da`: `configSource`
- `0x18003119a`: `deepestPathSet`
- `0x1800312f0`: `collectionItemFileConfigPath`
- `0x180031346`: `collectionItemLocationConfigPath`
- `0x180031495`: `configSectionDefinition`
- `0x180031554`: `availableReadableMetadata`
- `0x180031567`: `availableReadableMetadata,availableWritableMetadata,overrideMode,effectiveOverrideMode,isLocked,deepestPathSet,configSource,childSource,deepestFileNameSet,deepestFileLineNumberSet,collectionItemFileConfigPath,collectionItemLocationConfigPath,lockItem,lockAllElementsExcept,lockElements,lockAllAttributesExcept,lockAttributes,parentElement,configSectionDefinition,inheritInChildApplications,isPresent`
- `0x1800315a3`: `overrideMode,lockItem,lockItem,lockAllElementsExcept,lockElements,lockAllAttributesExcept,lockAttributes,configSource,childSource,inheritInChildApplications,isEmptyElementVisible`

## pseudocode

```c
__int64 __fastcall CONFIG_ELEMENT::GetMetadata(LONGLONG *this, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  unsigned __int16 *v3; // r14
  unsigned int LockingAttributeValue; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  LONGLONG v11; // rax
  STRU *v12; // rcx
  LONGLONG v13; // rax
  LONGLONG v14; // rax
  const OLECHAR *Str; // rcx
  LONGLONG v16; // rax
  LONGLONG v17; // rax
  LONGLONG v18; // rax
  LONGLONG v19; // rax
  LOCKING_ATTRIBUTES **v20; // rax
  SHORT v21; // cx
  LONGLONG v22; // rcx
  LONGLONG v23; // rax
  const OLECHAR *v24; // rcx
  BSTR v25; // rax
  LONGLONG v26; // rax
  METADATA_LIST *v27; // rcx
  LOCKING_ATTRIBUTES **v28; // rax
  int OverrideMode; // ecx
  unsigned __int16 *v31; // [rsp+48h] [rbp+10h] BYREF

  v3 = 0;
  v31 = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  LockingAttributeValue = CONFIG_ELEMENT::InitializeFromExtension((CONFIG_ELEMENT *)this);
  if ( (LockingAttributeValue & 0x80000000) == 0 )
  {
    if ( !wcscmp_0(a2, L"overrideMode") || !wcscmp_0(a2, L"effectiveOverrideMode") )
    {
      if ( *a2 == 101 )
        OverrideMode = (int)(*((_DWORD *)this + 34) << 28) >> 28;
      else
        OverrideMode = CONFIG_ELEMENT::QueryOverrideMode(this, v8, v9);
      a3->vt = 8;
      switch ( OverrideMode )
      {
        case 1:
          Str = L"Allow";
          goto LABEL_27;
        case 2:
          Str = L"Deny";
          goto LABEL_27;
        case 3:
          Str = L"Inherit";
          goto LABEL_27;
      }
      return (unsigned int)-2147024846;
    }
    if ( !wcscmp_0(a2, L"isLocked") )
    {
      a3->vt = 11;
      v10 = this[17] & 0xF0000;
LABEL_70:
      a3->iVal = -(v10 != 0);
      return LockingAttributeValue;
    }
    if ( !wcscmp_0(a2, L"deepestPathSet") )
    {
      v11 = this[15];
      if ( v11 && *(_QWORD *)(v11 + 24) )
      {
        a3->vt = 8;
        v12 = (STRU *)(*(_QWORD *)(this[15] + 24) + 16LL);
LABEL_26:
        Str = STRU::QueryStr(v12);
        goto LABEL_27;
      }
      return (unsigned int)-2147024846;
    }
    if ( !wcscmp_0(a2, L"configSource") )
    {
      v13 = this[14];
      if ( v13 && *(_QWORD *)(v13 + 8) && (*((_BYTE *)this + 36) & 1) == 0 )
      {
LABEL_21:
        a3->vt = 8;
        Str = *(const OLECHAR **)(this[14] + 8);
LABEL_27:
        a3->llVal = (LONGLONG)SysAllocString(Str);
        return LockingAttributeValue;
      }
LABEL_86:
      a3->vt = 0;
      return LockingAttributeValue;
    }
    if ( !wcscmp_0(a2, L"childSource") )
    {
      v14 = this[14];
      if ( v14 && *(_QWORD *)(v14 + 8) && (*((_BYTE *)this + 36) & 1) != 0 )
        goto LABEL_21;
      goto LABEL_86;
    }
    if ( !wcscmp_0(a2, L"deepestFileNameSet") )
    {
      v16 = this[15];
      if ( v16 && *(_QWORD *)(v16 + 24) )
      {
        a3->vt = 8;
        v12 = (STRU *)(*(_QWORD *)(this[15] + 24) + 72LL);
        goto LABEL_26;
      }
      return (unsigned int)-2147024846;
    }
    if ( !wcscmp_0(a2, L"deepestFileLineNumberSet") )
    {
      v17 = this[15];
      if ( v17 && *(_QWORD *)(v17 + 24) )
      {
        a3->vt = 19;
        a3->lVal = *(_DWORD *)(*(_QWORD *)(this[15] + 24) + 12LL);
        return LockingAttributeValue;
      }
      return (unsigned int)-2147024846;
    }
    if ( !wcscmp_0(a2, L"collectionItemFileConfigPath") )
    {
      if ( (unsigned int)((int)(*((_DWORD *)this + 34) << 16) >> 28) > 2 )
        return (unsigned int)-2147024846;
      if ( this[19] )
      {
        a3->vt = 8;
        Str = &szDomain;
        v18 = this[19];
        if ( *(_QWORD *)(v18 + 16) )
          Str = *(const OLECHAR **)(v18 + 16);
        goto LABEL_27;
      }
      goto LABEL_86;
    }
    if ( !wcscmp_0(a2, L"collectionItemLocationConfigPath") )
    {
      if ( (unsigned int)((int)(*((_DWORD *)this + 34) << 16) >> 28) > 2 )
        return (unsigned int)-2147024846;
      if ( this[19] )
      {
        a3->vt = 8;
        Str = &szDomain;
        v19 = this[19];
        if ( *(_QWORD *)(v19 + 24) )
          Str = *(const OLECHAR **)(v19 + 24);
        goto LABEL_27;
      }
      goto LABEL_86;
    }
    if ( !wcscmp_0(a2, L"lockItem") )
    {
      v20 = (LOCKING_ATTRIBUTES **)this[13];
      if ( v20 && *v20 )
      {
        LockingAttributeValue = LOCKING_ATTRIBUTES::GetLockingAttributeValue(
                                  *v20,
                                  L"lockItem",
                                  (const unsigned __int16 **)&v31);
        if ( (LockingAttributeValue & 0x80000000) != 0 )
          return LockingAttributeValue;
        v3 = v31;
      }
      if ( !v3 )
        goto LABEL_86;
      a3->vt = 11;
      v21 = (wcscmp_0(L"true", v3) != 0) - 1;
LABEL_65:
      a3->iVal = v21;
      return LockingAttributeValue;
    }
    if ( !wcscmp_0(a2, L"lockAllElementsExcept")
      || !wcscmp_0(a2, L"lockElements")
      || !wcscmp_0(a2, L"lockAllAttributesExcept")
      || !wcscmp_0(a2, L"lockAttributes") )
    {
      v28 = (LOCKING_ATTRIBUTES **)this[13];
      if ( v28 && *v28 )
      {
        LockingAttributeValue = LOCKING_ATTRIBUTES::GetLockingAttributeValue(*v28, a2, (const unsigned __int16 **)&v31);
        if ( (LockingAttributeValue & 0x80000000) != 0 )
          return LockingAttributeValue;
        v3 = v31;
      }
      if ( v3 )
      {
        a3->vt = 8;
        Str = v3;
        goto LABEL_27;
      }
      goto LABEL_86;
    }
    if ( !wcscmp_0(a2, L"parentElement") )
    {
      a3->vt = 13;
      a3->llVal = this[18];
      v22 = this[18];
LABEL_61:
      if ( v22 )
        (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v22 + 8LL))(v22);
      return LockingAttributeValue;
    }
    if ( !wcscmp_0(a2, L"configSectionDefinition") )
    {
      a3->vt = 13;
      v23 = this[15];
      if ( !v23 )
      {
        a3->llVal = 0;
        return LockingAttributeValue;
      }
      a3->llVal = *(_QWORD *)(v23 + 16);
      v22 = *(_QWORD *)(this[15] + 16);
      goto LABEL_61;
    }
    if ( !wcscmp_0(a2, L"inheritInChildApplications") )
    {
      a3->vt = 11;
      v21 = -((unsigned int)CONFIG_ELEMENT::QueryInheritInChildApplications((CONFIG_ELEMENT *)this) != 0);
      goto LABEL_65;
    }
    if ( !wcscmp_0(a2, L"isPresent") )
    {
      a3->vt = 11;
      if ( (*((_BYTE *)this + 36) & 0x40) != 0
        || (v10 = CONFIG_ELEMENT::ContainsSerializableData((CONFIG_ELEMENT *)this)) != 0 )
      {
        v10 = 1;
      }
      goto LABEL_70;
    }
    if ( !wcscmp_0(a2, L"availableReadableMetadata") )
    {
      v24 = L"availableReadableMetadata,availableWritableMetadata,overrideMode,effectiveOverrideMode,isLocked,deepestPathS"
             "et,configSource,childSource,deepestFileNameSet,deepestFileLineNumberSet,collectionItemFileConfigPath,collec"
             "tionItemLocationConfigPath,lockItem,lockAllElementsExcept,lockElements,lockAllAttributesExcept,lockAttribut"
             "es,parentElement,configSectionDefinition,inheritInChildApplications,isPresent";
      goto LABEL_73;
    }
    if ( !wcscmp_0(a2, L"availableWritableMetadata") )
    {
      v24 = L"overrideMode,lockItem,lockItem,lockAllElementsExcept,lockElements,lockAllAttributesExcept,lockAttributes,con"
             "figSource,childSource,inheritInChildApplications,isEmptyElementVisible";
LABEL_73:
      a3->vt = 8;
      v25 = SysAllocString(v24);
      a3->llVal = (LONGLONG)v25;
      if ( !v25 )
        return (unsigned int)-2147024882;
      return LockingAttributeValue;
    }
    v26 = this[16];
    if ( !v26 )
      return (unsigned int)-2147024846;
    v27 = *(METADATA_LIST **)(v26 + 8);
    if ( !v27 )
      return (unsigned int)-2147024846;
    LockingAttributeValue = METADATA_LIST::GetMetadata(v27, a2, a3);
    if ( LockingAttributeValue == -2147023483 )
      return (unsigned int)-2147024846;
  }
  return LockingAttributeValue;
}

```

## disassembly

```asm
0x180031100  mov     [rsp+arg_0], rbx
0x180031105  mov     [rsp+arg_10], rbp
0x18003110a  push    rsi
0x18003110b  push    rdi
0x18003110c  push    r14
0x18003110e  sub     rsp, 20h
0x180031112  xor     r14d, r14d
0x180031115  mov     rdi, r8
0x180031118  mov     [rsp+38h+arg_8], r14
0x18003111d  mov     rbp, rdx
0x180031120  mov     rsi, rcx
0x180031123  test    rdx, rdx
0x180031126  jz      loc_180031688
0x18003112c  test    r8, r8
0x18003112f  jz      loc_180031688
0x180031135  call    ?InitializeFromExtension@CONFIG_ELEMENT@@AEAAJXZ; CONFIG_ELEMENT::InitializeFromExtension(void)
0x18003113a  mov     ebx, eax
0x18003113c  test    eax, eax
0x18003113e  js      loc_18003168D
0x180031144  lea     rdx, aOverridemode; "overrideMode"
0x18003114b  mov     rcx, rbp; String1
0x18003114e  call    wcscmp_0
0x180031153  test    eax, eax
0x180031155  jz      loc_180031629
0x18003115b  lea     rdx, aEffectiveoverr; "effectiveOverrideMode"
0x180031162  mov     rcx, rbp; String1
0x180031165  call    wcscmp_0
0x18003116a  test    eax, eax
0x18003116c  jz      loc_180031629
0x180031172  lea     rdx, aIslocked; "isLocked"
0x180031179  mov     rcx, rbp; String1
0x18003117c  call    wcscmp_0
0x180031181  test    eax, eax
0x180031183  jnz     short loc_18003119A
0x180031185  mov     word ptr [rdi], 0Bh
0x18003118a  mov     eax, [rsi+88h]
0x180031190  and     eax, 0F0000h
0x180031195  jmp     loc_180031546
0x18003119a  lea     rdx, aDeepestpathset; "deepestPathSet"
0x1800311a1  mov     rcx, rbp; String1
0x1800311a4  call    wcscmp_0
0x1800311a9  test    eax, eax
0x1800311ab  jnz     short loc_1800311DA
0x1800311ad  mov     rax, [rsi+78h]
0x1800311b1  test    rax, rax
0x1800311b4  jz      loc_1800315D9
0x1800311ba  cmp     [rax+18h], r14
0x1800311be  jz      loc_1800315D9
0x1800311c4  mov     word ptr [rdi], 8
0x1800311c9  mov     rax, [rsi+78h]
0x1800311cd  mov     rcx, [rax+18h]
0x1800311d1  add     rcx, 10h
0x1800311d5  jmp     loc_180031296
0x1800311da  lea     rdx, aConfigsource; "configSource"
0x1800311e1  mov     rcx, rbp; String1
0x1800311e4  call    wcscmp_0
0x1800311e9  test    eax, eax
0x1800311eb  jnz     short loc_180031214
0x1800311ed  mov     rax, [rsi+70h]
0x1800311f1  test    rax, rax
0x1800311f4  jz      loc_180031615
0x1800311fa  cmp     [rax+8], r14
0x1800311fe  jz      loc_180031615
0x180031204  mov     eax, 1
0x180031209  test    [rsi+24h], al
0x18003120c  jnz     loc_180031615
0x180031212  jmp     short loc_18003124C
0x180031214  lea     rdx, aChildsource; "childSource"
0x18003121b  mov     rcx, rbp; String1
0x18003121e  call    wcscmp_0
0x180031223  test    eax, eax
0x180031225  jnz     short loc_18003125B
0x180031227  mov     rax, [rsi+70h]
0x18003122b  test    rax, rax
0x18003122e  jz      loc_180031615
0x180031234  cmp     [rax+8], r14
0x180031238  jz      loc_180031615
0x18003123e  mov     eax, 1
0x180031243  test    [rsi+24h], al
0x180031246  jz      loc_180031615
0x18003124c  mov     word ptr [rdi], 8
0x180031251  mov     rcx, [rsi+70h]
0x180031255  mov     rcx, [rcx+8]
0x180031259  jmp     short loc_18003129F
0x18003125b  lea     rdx, aDeepestfilenam; "deepestFileNameSet"
0x180031262  mov     rcx, rbp; String1
0x180031265  call    wcscmp_0
0x18003126a  test    eax, eax
0x18003126c  jnz     short loc_1800312AE
0x18003126e  mov     rax, [rsi+78h]
0x180031272  test    rax, rax
0x180031275  jz      loc_1800315D9
0x18003127b  cmp     [rax+18h], r14
0x18003127f  jz      loc_1800315D9
0x180031285  mov     word ptr [rdi], 8
0x18003128a  mov     rax, [rsi+78h]
0x18003128e  mov     rcx, [rax+18h]
0x180031292  add     rcx, 48h ; 'H'
0x180031296  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18003129c  mov     rcx, rax; psz
0x18003129f  call    cs:__imp_SysAllocString
0x1800312a5  mov     [rdi+8], rax
0x1800312a9  jmp     loc_18003168D
0x1800312ae  lea     rdx, aDeepestfilelin; "deepestFileLineNumberSet"
0x1800312b5  mov     rcx, rbp; String1
0x1800312b8  call    wcscmp_0
0x1800312bd  test    eax, eax
0x1800312bf  jnz     short loc_1800312F0
0x1800312c1  mov     rax, [rsi+78h]
0x1800312c5  test    rax, rax
0x1800312c8  jz      loc_1800315D9
0x1800312ce  cmp     [rax+18h], r14
0x1800312d2  jz      loc_1800315D9
0x1800312d8  mov     word ptr [rdi], 13h
0x1800312dd  mov     rax, [rsi+78h]
0x1800312e1  mov     rcx, [rax+18h]
0x1800312e5  mov     eax, [rcx+0Ch]
0x1800312e8  mov     [rdi+8], eax
0x1800312eb  jmp     loc_18003168D
0x1800312f0  lea     rdx, aCollectionitem; "collectionItemFileConfigPath"
0x1800312f7  mov     rcx, rbp; String1
0x1800312fa  call    wcscmp_0
0x1800312ff  test    eax, eax
0x180031301  jnz     short loc_180031346
0x180031303  mov     eax, [rsi+88h]
0x180031309  shl     eax, 10h
0x18003130c  sar     eax, 1Ch
0x18003130f  cmp     eax, 2
0x180031312  ja      loc_1800315D9
0x180031318  cmp     [rsi+98h], r14
0x18003131f  jz      loc_180031615
0x180031325  mov     word ptr [rdi], 8
0x18003132a  lea     rcx, szDomain
0x180031331  mov     rax, [rsi+98h]
0x180031338  cmp     [rax+10h], r14
0x18003133c  cmovnz  rcx, [rax+10h]
0x180031341  jmp     loc_18003129F
0x180031346  lea     rdx, aCollectionitem_0; "collectionItemLocationConfigPath"
0x18003134d  mov     rcx, rbp; String1
0x180031350  call    wcscmp_0
0x180031355  test    eax, eax
0x180031357  jnz     short loc_18003139C
0x180031359  mov     eax, [rsi+88h]
0x18003135f  shl     eax, 10h
0x180031362  sar     eax, 1Ch
0x180031365  cmp     eax, 2
0x180031368  ja      loc_1800315D9
0x18003136e  cmp     [rsi+98h], r14
0x180031375  jz      loc_180031615
0x18003137b  mov     word ptr [rdi], 8
0x180031380  lea     rcx, szDomain
0x180031387  mov     rax, [rsi+98h]
0x18003138e  cmp     [rax+18h], r14
0x180031392  cmovnz  rcx, [rax+18h]
0x180031397  jmp     loc_18003129F
0x18003139c  lea     rdx, aLockitem; "lockItem"
0x1800313a3  mov     rcx, rbp; String1
0x1800313a6  call    wcscmp_0
0x1800313ab  test    eax, eax
0x1800313ad  jnz     short loc_18003140D
0x1800313af  mov     rax, [rsi+68h]
0x1800313b3  test    rax, rax
0x1800313b6  jz      short loc_1800313E0
0x1800313b8  mov     rcx, [rax]; this
0x1800313bb  test    rcx, rcx
0x1800313be  jz      short loc_1800313E0
0x1800313c0  lea     r8, [rsp+38h+arg_8]; unsigned __int16 **
0x1800313c5  lea     rdx, aLockitem; "lockItem"
0x1800313cc  call    ?GetLockingAttributeValue@LOCKING_ATTRIBUTES@@QEAAJPEBGPEAPEBG@Z; LOCKING_ATTRIBUTES::GetLockingAttributeValue(ushort const *,ushort const * *)
0x1800313d1  mov     ebx, eax
0x1800313d3  test    eax, eax
0x1800313d5  js      loc_18003168D
0x1800313db  mov     r14, [rsp+38h+arg_8]
0x1800313e0  test    r14, r14
0x1800313e3  jz      loc_180031615
0x1800313e9  mov     rdx, r14; String2
0x1800313ec  mov     word ptr [rdi], 0Bh
0x1800313f1  lea     rcx, aTrue; "true"
0x1800313f8  call    wcscmp_0
0x1800313fd  neg     eax
0x1800313ff  sbb     cx, cx
0x180031402  neg     cx
0x180031405  dec     cx
0x180031408  jmp     loc_18003150E
0x18003140d  lea     rdx, aLockallelement; "lockAllElementsExcept"
0x180031414  mov     rcx, rbp; String1
0x180031417  call    wcscmp_0
0x18003141c  test    eax, eax
0x18003141e  jz      loc_1800315E3
0x180031424  lea     rdx, aLockelements; "lockElements"
0x18003142b  mov     rcx, rbp; String1
0x18003142e  call    wcscmp_0
0x180031433  test    eax, eax
0x180031435  jz      loc_1800315E3
0x18003143b  lea     rdx, aLockallattribu; "lockAllAttributesExcept"
0x180031442  mov     rcx, rbp; String1
0x180031445  call    wcscmp_0
0x18003144a  test    eax, eax
0x18003144c  jz      loc_1800315E3
0x180031452  lea     rdx, aLockattributes; "lockAttributes"
0x180031459  mov     rcx, rbp; String1
0x18003145c  call    wcscmp_0
0x180031461  test    eax, eax
0x180031463  jz      loc_1800315E3
0x180031469  lea     rdx, aParentelement; "parentElement"
0x180031470  mov     rcx, rbp; String1
0x180031473  call    wcscmp_0
0x180031478  test    eax, eax
0x18003147a  jnz     short loc_180031495
0x18003147c  mov     word ptr [rdi], 0Dh
0x180031481  mov     rax, [rsi+90h]
0x180031488  mov     [rdi+8], rax
0x18003148c  mov     rcx, [rsi+90h]
0x180031493  jmp     short loc_1800314CF
0x180031495  lea     rdx, aConfigsectiond; "configSectionDefinition"
0x18003149c  mov     rcx, rbp; String1
0x18003149f  call    wcscmp_0
0x1800314a4  test    eax, eax
0x1800314a6  jnz     short loc_1800314E9
0x1800314a8  mov     word ptr [rdi], 0Dh
0x1800314ad  mov     rax, [rsi+78h]
0x1800314b1  test    rax, rax
0x1800314b4  jnz     short loc_1800314BF
0x1800314b6  mov     [rdi+8], r14
0x1800314ba  jmp     loc_18003168D
0x1800314bf  mov     rax, [rax+10h]
0x1800314c3  mov     [rdi+8], rax
0x1800314c7  mov     rax, [rsi+78h]
0x1800314cb  mov     rcx, [rax+10h]
0x1800314cf  test    rcx, rcx
0x1800314d2  jz      loc_18003168D
0x1800314d8  mov     rax, [rcx]
0x1800314db  mov     rax, [rax+8]
0x1800314df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314e4  jmp     loc_18003168D
0x1800314e9  lea     rdx, aInheritinchild; "inheritInChildApplications"
0x1800314f0  mov     rcx, rbp; String1
0x1800314f3  call    wcscmp_0
0x1800314f8  test    eax, eax
0x1800314fa  jnz     short loc_180031517
0x1800314fc  mov     rcx, rsi; this
0x1800314ff  mov     word ptr [rdi], 0Bh
0x180031504  call    ?QueryInheritInChildApplications@CONFIG_ELEMENT@@QEBAHXZ; CONFIG_ELEMENT::QueryInheritInChildApplications(void)
0x180031509  neg     eax
0x18003150b  sbb     cx, cx
0x18003150e  mov     [rdi+8], cx
0x180031512  jmp     loc_18003168D
0x180031517  lea     rdx, aIspresent; "isPresent"
0x18003151e  mov     rcx, rbp; String1
0x180031521  call    wcscmp_0
0x180031526  test    eax, eax
0x180031528  jnz     short loc_180031554
0x18003152a  mov     word ptr [rdi], 0Bh
0x18003152f  test    byte ptr [rsi+24h], 40h
0x180031533  jnz     short loc_180031541
0x180031535  mov     rcx, rsi; this
0x180031538  call    ?ContainsSerializableData@CONFIG_ELEMENT@@QEAAHXZ; CONFIG_ELEMENT::ContainsSerializableData(void)
0x18003153d  test    eax, eax
0x18003153f  jz      short loc_180031546
0x180031541  mov     eax, 1
0x180031546  neg     eax
0x180031548  sbb     ax, ax
0x18003154b  mov     [rdi+8], ax
0x18003154f  jmp     loc_18003168D
0x180031554  lea     rdx, aAvailablereada_1; "availableReadableMetadata"
0x18003155b  mov     rcx, rbp; String1
0x18003155e  call    wcscmp_0
0x180031563  test    eax, eax
0x180031565  jnz     short loc_180031590
0x180031567  lea     rcx, aAvailablereada_0; "availableReadableMetadata,availableWrit"...
0x18003156e  mov     word ptr [rdi], 8
0x180031573  call    cs:__imp_SysAllocString
0x180031579  mov     [rdi+8], rax
0x18003157d  test    rax, rax
0x180031580  jnz     loc_18003168D
0x180031586  mov     ebx, 8007000Eh
0x18003158b  jmp     loc_18003168D
0x180031590  lea     rdx, aAvailablewrita; "availableWritableMetadata"
0x180031597  mov     rcx, rbp; String1
0x18003159a  call    wcscmp_0
0x18003159f  test    eax, eax
0x1800315a1  jnz     short loc_1800315AC
0x1800315a3  lea     rcx, aOverridemodeLo; "overrideMode,lockItem,lockItem,lockAllE"...
0x1800315aa  jmp     short loc_18003156E
0x1800315ac  mov     rax, [rsi+80h]
0x1800315b3  test    rax, rax
0x1800315b6  jz      short loc_1800315D9
0x1800315b8  mov     rcx, [rax+8]; this
0x1800315bc  test    rcx, rcx
0x1800315bf  jz      short loc_1800315D9
0x1800315c1  mov     r8, rdi; struct tagVARIANT *
0x1800315c4  mov     rdx, rbp; unsigned __int16 *
0x1800315c7  call    ?GetMetadata@METADATA_LIST@@QEAAJPEBGPEAUtagVARIANT@@@Z; METADATA_LIST::GetMetadata(ushort const *,tagVARIANT *)
0x1800315cc  mov     ebx, eax
0x1800315ce  cmp     eax, 80070585h
0x1800315d3  jnz     loc_18003168D
0x1800315d9  mov     ebx, 80070032h
0x1800315de  jmp     loc_18003168D
0x1800315e3  mov     rax, [rsi+68h]
0x1800315e7  test    rax, rax
  ... truncated ...
```
