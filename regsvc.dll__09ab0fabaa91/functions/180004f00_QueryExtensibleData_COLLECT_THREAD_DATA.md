# QueryExtensibleData(COLLECT_THREAD_DATA *)

- ea: `0x180004f00`
- end: `0x180005678`
- name: `?QueryExtensibleData@@YAJPEAUCOLLECT_THREAD_DATA@@@Z`
- size: `1912`
- prototype: `__int64 __fastcall(struct COLLECT_THREAD_DATA *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting`

## callers

- `0x1800093a8`

## callees

- `0x180004f00`
- `0x180006a50`
- `0x180007180`
- `0x180007320`
- `0x180008080`
- `0x18000aaa0`
- `0x18000aac8`
- `0x18000ab64`
- `0x18000b1fc`
- `0x18000c774`
- `0x18000ca0c`
- `0x180011888`
- `0x180011b08`
- `0x180011b88`
- `0x180011d10`
- `0x180012604`
- `0x18001335c`

## import_xrefs

- `ntdll!RtlWakeAddressAll` at `0x1800055ec`
- `ntdll!RtlWakeAddressAll` at `0x1800055ec`

## pseudocode

```c
__int64 __fastcall QueryExtensibleData(struct COLLECT_THREAD_DATA *a1)
{
  unsigned int *v1; // rax
  __int64 v3; // r15
  unsigned int v4; // edi
  unsigned int v5; // ebx
  __int64 v6; // r14
  unsigned __int8 v7; // si
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 result; // rax
  __int16 v12; // ax
  __int64 v13; // rdx
  __int64 v14; // r9
  _QWORD *v15; // r10
  unsigned int v16; // r13d
  unsigned __int16 *v17; // r8
  unsigned int NextNumberFromList; // eax
  struct EXT_OBJ_LIST *v19; // r13
  struct EXT_OBJ_LIST *v20; // rdi
  struct EXT_OBJ_LIST *v21; // rbx
  unsigned int v22; // r14d
  struct EXT_OBJECT *i; // rsi
  __int64 v24; // r15
  struct EXT_OBJ_LIST *j; // rax
  struct EXT_OBJ_LIST *k; // rax
  struct EXT_OBJECT *v27; // rax
  struct EXT_OBJECT *v28; // rbx
  __int64 v29; // r8
  const wchar_t *v30; // r9
  int v31; // edi
  _DWORD *v32; // rsi
  int v33; // ecx
  int V2Provider; // eax
  int v35; // eax
  const unsigned __int16 *v36; // rcx
  bool v37; // zf
  unsigned __int32 v38; // ebx
  __int64 v39; // [rsp+40h] [rbp-29h]
  __int64 v40; // [rsp+48h] [rbp-21h]
  __int64 v41; // [rsp+50h] [rbp-19h]
  _DWORD v42[2]; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int16 *v43; // [rsp+60h] [rbp-9h] BYREF
  void *Block[4]; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int8 IsDisabled; // [rsp+D0h] [rbp+67h]
  unsigned int v46; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int v47; // [rsp+E0h] [rbp+77h]
  __int64 v48; // [rsp+E8h] [rbp+7Fh] BYREF

  v1 = (unsigned int *)*((_QWORD *)a1 + 3);
  v3 = *((_QWORD *)a1 + 2);
  v4 = *(unsigned __int16 *)a1;
  v41 = v3;
  if ( v1 )
    v5 = *v1;
  else
    v5 = 0;
  v40 = **((_QWORD **)a1 + 4);
  v48 = v40;
  v6 = v40;
  IsDisabled = PerflibciIsDisabled();
  v7 = IsDisabled;
  if ( (v40 & 7) != 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 1784;
    v9 = 28;
    v10 = v40;
LABEL_8:
    WPP_SF_q(v8[2], v9, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, v10);
    return 1784;
  }
  if ( (v3 & 7) != 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 1784;
    v9 = 29;
    v10 = v3;
    goto LABEL_8;
  }
  v12 = *((_WORD *)a1 + 1);
  v13 = v3 + v5;
  LOWORD(v46) = v12;
  v47 = v4;
  v39 = v13;
  if ( IsDisabled && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
    v13 = v3 + v5;
    v12 = v46;
  }
  v14 = (unsigned int)_InterlockedIncrement(&dwExtObjListRefCount);
  v15 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, v14);
    v15 = WPP_GLOBAL_Control;
    v13 = v3 + v5;
    v12 = v46;
  }
  v16 = 234;
  if ( v4 != 2 || IsDisabled )
  {
    if ( v12 || ((v4 - 1) & 0xFFFFFFF7) != 0 )
      goto LABEL_86;
    V2Provider = QueryV2Provider(L"Global", 0, 0, (__int64)&v48, v3 + 28);
    v6 = v48;
    if ( V2Provider == 234 )
      goto LABEL_127;
    v15 = WPP_GLOBAL_Control;
  }
  else
  {
    v43 = (unsigned __int16 *)*((_QWORD *)a1 + 1);
    utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>(
      Block,
      v13,
      v43,
      v14);
    while ( *v17 )
    {
      NextNumberFromList = GetNextNumberFromList(v17, (const unsigned __int16 **)&v43);
      if ( NextNumberFromList )
      {
        v42[0] = NextNumberFromList;
        v42[1] = 0;
        if ( !(unsigned __int8)utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::_PushBackOne<EXT_OBJ_LIST>(
                                 Block,
                                 v42) )
        {
          v16 = 14;
          utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::_Uninit(Block);
          goto LABEL_127;
        }
      }
      v17 = v43;
    }
    v19 = (struct EXT_OBJ_LIST *)Block[0];
    v20 = (struct EXT_OBJ_LIST *)Block[1];
    v21 = (struct EXT_OBJ_LIST *)Block[0];
    v15 = WPP_GLOBAL_Control;
    while ( v21 != v20 )
    {
      v22 = *(_DWORD *)v21;
      if ( (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 5u )
      {
        WPP_SF_d(v15[2], 31, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, v22);
        v15 = WPP_GLOBAL_Control;
      }
      for ( i = ExtensibleObjects; i; i = *(struct EXT_OBJECT **)i )
      {
        if ( *((_DWORD *)i + 28) )
        {
          v24 = 0;
          do
          {
            if ( *(_DWORD *)v21 == *((_DWORD *)i + v24 + 29) )
            {
              *((_DWORD *)v21 + 1) |= 1u;
              *((_DWORD *)i + 95) |= 0x80000000;
              v15 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  32,
                  WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
                  *((_QWORD *)i + 49));
                v15 = WPP_GLOBAL_Control;
              }
            }
            v24 = (unsigned int)(v24 + 1);
          }
          while ( (unsigned int)v24 < *((_DWORD *)i + 28) );
        }
        else if ( v22 >= *((_DWORD *)i + 93) && v22 <= *((_DWORD *)i + 94) )
        {
          *((_DWORD *)v21 + 1) |= 1u;
          *((_DWORD *)i + 95) |= 0x80000000;
          v15 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
              *((_QWORD *)i + 49));
            v15 = WPP_GLOBAL_Control;
          }
        }
      }
      v21 = (struct EXT_OBJ_LIST *)((char *)v21 + 8);
    }
    for ( j = v19; ; j = (struct EXT_OBJ_LIST *)((char *)j + 8) )
    {
      if ( j == v20 )
      {
        v6 = v40;
        v3 = v41;
        goto LABEL_82;
      }
      if ( (*((_BYTE *)j + 4) & 1) == 0 )
        break;
    }
    if ( (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 5u )
    {
      WPP_SF_(v15[2], 34, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
      v15 = WPP_GLOBAL_Control;
    }
    if ( (_WORD)v46 )
    {
      v6 = v40;
      v3 = v41;
    }
    else
    {
      if ( (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 4u )
        WPP_SF_(v15[2], 35, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
      v3 = v41;
      if ( (unsigned int)QueryV2Provider(*((unsigned __int16 **)a1 + 1), v19, (v20 - v19) >> 3, (__int64)&v48, v41 + 28) == 234 )
      {
        utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::_Uninit(Block);
        v6 = v48;
        v16 = 234;
        v7 = IsDisabled;
        goto LABEL_127;
      }
      for ( k = v19; ; k = (struct EXT_OBJ_LIST *)((char *)k + 8) )
      {
        if ( k == v20 )
        {
          v6 = v48;
          v15 = WPP_GLOBAL_Control;
          goto LABEL_82;
        }
        if ( (*((_BYTE *)k + 4) & 1) == 0 )
          break;
      }
      v15 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
        v15 = WPP_GLOBAL_Control;
        v6 = v48;
      }
      else
      {
        v6 = v48;
      }
    }
    if ( (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 3u )
    {
      WPP_SF_(v15[2], 37, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
      v15 = WPP_GLOBAL_Control;
    }
    v27 = ExtensibleObjects;
    if ( ExtensibleObjects )
    {
      do
      {
        if ( !*((_DWORD *)v27 + 28) )
          *((_DWORD *)v27 + 95) |= 0x80000000;
        v27 = *(struct EXT_OBJECT **)v27;
      }
      while ( v27 );
      v15 = WPP_GLOBAL_Control;
    }
LABEL_82:
    if ( v19 != (struct EXT_OBJ_LIST *)-1LL )
    {
      operator delete(v19);
      v15 = WPP_GLOBAL_Control;
    }
    v7 = IsDisabled;
    v16 = 234;
  }
  v13 = v39;
LABEL_86:
  v28 = ExtensibleObjects;
  v29 = v47;
  v30 = L"Costly";
  v31 = v7;
  while ( v28 )
  {
    if ( (_DWORD)v29 == 2 )
    {
      if ( !v7 )
      {
        v35 = *((_DWORD *)v28 + 95);
        if ( v35 < 0 && (v35 & 0x10) == 0 )
          goto LABEL_90;
      }
    }
    else if ( !v7 )
    {
      goto LABEL_90;
    }
    if ( *((_QWORD *)v28 + 11) )
    {
      if ( (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 4u )
        WPP_SF_Sd(v15[2], 38, (unsigned int)WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, *((_QWORD *)v28 + 49), v29);
      if ( (unsigned int)PerfpLockExtObject(v28, v13, v29, v30) )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            39,
            WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
            *((_QWORD *)v28 + 49));
      }
      else
      {
        CloseExtObjectLibrary(v28, v31);
        PerfpUnlockExtObject(v28);
      }
      v32 = (_DWORD *)((char *)v28 + 380);
      goto LABEL_123;
    }
LABEL_90:
    v32 = (_DWORD *)((char *)v28 + 380);
    v33 = *((_DWORD *)v28 + 95);
    if ( (v33 & 0x10) != 0 )
      goto LABEL_124;
    switch ( (int)v29 )
    {
      case 1:
        v36 = L"Global";
        goto LABEL_121;
      case 2:
        if ( v33 >= 0 )
          goto LABEL_124;
        v36 = (const unsigned __int16 *)*((_QWORD *)a1 + 1);
        goto LABEL_120;
      case 3:
        v36 = L"Foreigh";
        goto LABEL_121;
      case 4:
        v36 = L"Costly";
        goto LABEL_121;
      case 9:
        v37 = (v33 & 0x80u) == 0;
        v36 = L"MetadataGlobal";
        if ( v37 )
          v36 = L"Global";
        goto LABEL_120;
      case 10:
        v37 = (v33 & 0x80u) == 0;
        v36 = L"MetadataCostly";
        if ( v37 )
          v36 = L"Costly";
LABEL_120:
        if ( !v36 )
          goto LABEL_124;
LABEL_121:
        LODWORD(v48) = 0;
        v46 = 0;
        if ( (unsigned int)QueryV1Provider(v36, v28, v29, v6, (int)v13 - (int)v6, &v46, &v48) == 234 )
        {
          v7 = IsDisabled;
          goto LABEL_127;
        }
        v6 += v46;
        *(_DWORD *)(v3 + 28) += v48;
        break;
      default:
        goto LABEL_124;
    }
LABEL_123:
    v29 = v47;
    v13 = v39;
    v30 = L"Costly";
LABEL_124:
    *v32 &= ~0x80000000;
    v15 = WPP_GLOBAL_Control;
    v7 = IsDisabled;
    v28 = *(struct EXT_OBJECT **)v28;
  }
  v16 = 0;
LABEL_127:
  v38 = _InterlockedDecrement(&dwExtObjListRefCount);
  if ( !v38 )
    RtlWakeAddressAll(&dwExtObjListRefCount);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, v38);
  if ( v7 )
    v16 = 1058;
  result = v16;
  **((_QWORD **)a1 + 4) = v6;
  return result;
}

```

## disassembly

```asm
0x180004f00  push    rbp
0x180004f02  push    rbx
0x180004f03  push    rsi
0x180004f04  push    rdi
0x180004f05  push    r12
0x180004f07  push    r14
0x180004f09  push    r15
0x180004f0b  lea     rbp, [rsp-27h]
0x180004f10  sub     rsp, 90h
0x180004f17  mov     rax, [rcx+18h]
0x180004f1b  mov     r12, rcx
0x180004f1e  mov     r15, [rcx+10h]
0x180004f22  movzx   edi, word ptr [rcx]
0x180004f25  mov     [rbp+57h+var_70], r15
0x180004f29  test    rax, rax
0x180004f2c  jz      short loc_180004F32
0x180004f2e  mov     ebx, [rax]
0x180004f30  jmp     short loc_180004F34
0x180004f32  xor     ebx, ebx
0x180004f34  mov     rax, [rcx+20h]
0x180004f38  mov     r14, [rax]
0x180004f3b  mov     [rbp+57h+var_78], r14
0x180004f3f  mov     [rbp+57h+arg_18], r14
0x180004f43  call    ?PerflibciIsDisabled@@YAEXZ; PerflibciIsDisabled(void)
0x180004f48  mov     [rbp+57h+arg_0], al
0x180004f4b  movzx   esi, al
0x180004f4e  test    r14b, 7
0x180004f52  jz      short loc_180004F89
0x180004f54  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f5b  test    byte ptr [rcx+1Ch], 2
0x180004f5f  jz      short loc_180004F7F
0x180004f61  cmp     byte ptr [rcx+19h], 2
0x180004f65  jb      short loc_180004F7F
0x180004f67  mov     edx, 1Ch
0x180004f6c  mov     r9, r14
0x180004f6f  mov     rcx, [rcx+10h]
0x180004f73  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180004f7a  call    WPP_SF_q
0x180004f7f  mov     eax, 6F8h
0x180004f84  jmp     loc_18000563C
0x180004f89  test    r15b, 7
0x180004f8d  jz      short loc_180004FAC
0x180004f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f96  test    byte ptr [rcx+1Ch], 2
0x180004f9a  jz      short loc_180004F7F
0x180004f9c  cmp     byte ptr [rcx+19h], 2
0x180004fa0  jb      short loc_180004F7F
0x180004fa2  mov     edx, 1Dh
0x180004fa7  mov     r9, r15
0x180004faa  jmp     short loc_180004F6F
0x180004fac  movzx   eax, word ptr [r12+2]
0x180004fb2  mov     edx, ebx
0x180004fb4  add     rdx, r15
0x180004fb7  mov     [rsp+0C0h+var_38], r13
0x180004fbf  mov     word ptr [rbp+57h+arg_8], ax
0x180004fc3  mov     [rbp+57h+arg_10], edi
0x180004fc6  mov     [rbp+57h+var_80], rdx
0x180004fca  test    sil, sil
0x180004fcd  jz      short loc_180004FFF
0x180004fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fd6  test    byte ptr [rcx+1Ch], 2
0x180004fda  jz      short loc_180004FFF
0x180004fdc  cmp     byte ptr [rcx+19h], 3
0x180004fe0  jb      short loc_180004FFF
0x180004fe2  mov     rcx, [rcx+10h]
0x180004fe6  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180004fed  mov     edx, 1Eh
0x180004ff2  call    WPP_SF_
0x180004ff7  mov     rdx, [rbp+57h+var_80]
0x180004ffb  movzx   eax, word ptr [rbp+57h+arg_8]
0x180004fff  mov     r9d, 1
0x180005005  lock xadd cs:?dwExtObjListRefCount@@3JC, r9d; long volatile dwExtObjListRefCount
0x18000500e  inc     r9d
0x180005011  mov     r10, cs:WPP_GLOBAL_Control
0x180005018  test    byte ptr [r10+1Ch], 20h
0x18000501d  jz      short loc_18000504A
0x18000501f  cmp     byte ptr [r10+19h], 4
0x180005024  jb      short loc_18000504A
0x180005026  mov     rcx, [r10+10h]
0x18000502a  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180005031  mov     edx, 0Dh
0x180005036  call    WPP_SF_d
0x18000503b  mov     r10, cs:WPP_GLOBAL_Control
0x180005042  mov     rdx, [rbp+57h+var_80]
0x180005046  movzx   eax, word ptr [rbp+57h+arg_8]
0x18000504a  mov     r13d, 0EAh
0x180005050  cmp     edi, 2
0x180005053  jnz     loc_18000540C
0x180005059  test    sil, sil
0x18000505c  jnz     loc_18000540C
0x180005062  mov     r8, [r12+8]
0x180005067  lea     rcx, [rbp+57h+Block]
0x18000506b  mov     [rbp+57h+var_60], r8
0x18000506f  call    ??0?$vector@UEXT_OBJ_LIST@@V?$allocator@UEXT_OBJ_LIST@@@utl@@@utl@@QEAA@XZ; utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>(void)
0x180005074  cmp     word ptr [r8], 0
0x180005079  jz      short loc_1800050C0
0x18000507b  lea     rdx, [rbp+57h+var_60]; unsigned __int16 **
0x18000507f  mov     rcx, r8; unsigned __int16 *
0x180005082  call    ?GetNextNumberFromList@@YAKPEBGPEAPEBG@Z; GetNextNumberFromList(ushort const *,ushort const * *)
0x180005087  test    eax, eax
0x180005089  jz      short loc_1800050A6
0x18000508b  lea     rdx, [rbp+57h+var_68]
0x18000508f  mov     [rbp+57h+var_68], eax
0x180005092  lea     rcx, [rbp+57h+Block]
0x180005096  mov     [rbp+57h+var_64], 0
0x18000509d  call    ??$_PushBackOne@UEXT_OBJ_LIST@@@?$vector@UEXT_OBJ_LIST@@V?$allocator@UEXT_OBJ_LIST@@@utl@@@utl@@AEAA_N$$QEAUEXT_OBJ_LIST@@@Z; utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::_PushBackOne<EXT_OBJ_LIST>(EXT_OBJ_LIST &&)
0x1800050a2  test    al, al
0x1800050a4  jz      short loc_1800050AC
0x1800050a6  mov     r8, [rbp+57h+var_60]
0x1800050aa  jmp     short loc_180005074
0x1800050ac  lea     rcx, [rbp+57h+Block]
0x1800050b0  mov     r13d, 0Eh
0x1800050b6  call    ?_Uninit@?$vector@UEXT_OBJ_LIST@@V?$allocator@UEXT_OBJ_LIST@@@utl@@@utl@@AEAAXXZ; utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::_Uninit(void)
0x1800050bb  jmp     loc_1800055D3
0x1800050c0  mov     r13, [rbp+57h+Block]
0x1800050c4  mov     rdi, [rbp+57h+var_50]
0x1800050c8  mov     rbx, r13
0x1800050cb  mov     r10, cs:WPP_GLOBAL_Control
0x1800050d2  cmp     rbx, rdi
0x1800050d5  jz      loc_1800051F0
0x1800050db  mov     r14d, [rbx]
0x1800050de  test    byte ptr [r10+1Ch], 2
0x1800050e3  jz      short loc_18000510B
0x1800050e5  cmp     byte ptr [r10+19h], 5
0x1800050ea  jb      short loc_18000510B
0x1800050ec  mov     rcx, [r10+10h]
0x1800050f0  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x1800050f7  mov     edx, 1Fh
0x1800050fc  mov     r9d, r14d
0x1800050ff  call    WPP_SF_d
0x180005104  mov     r10, cs:WPP_GLOBAL_Control
0x18000510b  mov     rsi, cs:?ExtensibleObjects@@3PEAUEXT_OBJECT@@EA; EXT_OBJECT * ExtensibleObjects
0x180005112  test    rsi, rsi
0x180005115  jz      loc_1800051E7
0x18000511b  nop     dword ptr [rax+rax+00h]
0x180005120  cmp     dword ptr [rsi+70h], 0
0x180005124  jbe     short loc_180005183
0x180005126  xor     r15d, r15d
0x180005129  mov     ecx, [rsi+r15*4+74h]
0x18000512e  cmp     [rbx], ecx
0x180005130  jnz     short loc_180005178
0x180005132  or      dword ptr [rbx+4], 1
0x180005136  or      dword ptr [rsi+17Ch], 80000000h
0x180005140  mov     r10, cs:WPP_GLOBAL_Control
0x180005147  test    byte ptr [r10+1Ch], 2
0x18000514c  jz      short loc_180005178
0x18000514e  cmp     byte ptr [r10+19h], 5
0x180005153  jb      short loc_180005178
0x180005155  mov     r9, [rsi+188h]
0x18000515c  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180005163  mov     rcx, [r10+10h]
0x180005167  mov     edx, 20h ; ' '
0x18000516c  call    WPP_SF_S
0x180005171  mov     r10, cs:WPP_GLOBAL_Control
0x180005178  inc     r15d
0x18000517b  cmp     r15d, [rsi+70h]
0x18000517f  jb      short loc_180005129
0x180005181  jmp     short loc_1800051DB
0x180005183  cmp     r14d, [rsi+174h]
0x18000518a  jb      short loc_1800051DB
0x18000518c  cmp     r14d, [rsi+178h]
0x180005193  ja      short loc_1800051DB
0x180005195  or      dword ptr [rbx+4], 1
0x180005199  or      dword ptr [rsi+17Ch], 80000000h
0x1800051a3  mov     r10, cs:WPP_GLOBAL_Control
0x1800051aa  test    byte ptr [r10+1Ch], 2
0x1800051af  jz      short loc_1800051DB
0x1800051b1  cmp     byte ptr [r10+19h], 5
0x1800051b6  jb      short loc_1800051DB
0x1800051b8  mov     r9, [rsi+188h]
0x1800051bf  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x1800051c6  mov     rcx, [r10+10h]
0x1800051ca  mov     edx, 21h ; '!'
0x1800051cf  call    WPP_SF_S
0x1800051d4  mov     r10, cs:WPP_GLOBAL_Control
0x1800051db  mov     rsi, [rsi]
0x1800051de  test    rsi, rsi
0x1800051e1  jnz     loc_180005120
0x1800051e7  add     rbx, 8
0x1800051eb  jmp     loc_1800050D2
0x1800051f0  mov     rax, r13
0x1800051f3  cmp     rax, rdi
0x1800051f6  jz      loc_180005375
0x1800051fc  test    byte ptr [rax+4], 1
0x180005200  jz      short loc_180005208
0x180005202  add     rax, 8
0x180005206  jmp     short loc_1800051F3
0x180005208  test    byte ptr [r10+1Ch], 2
0x18000520d  jz      short loc_180005232
0x18000520f  cmp     byte ptr [r10+19h], 5
0x180005214  jb      short loc_180005232
0x180005216  mov     rcx, [r10+10h]
0x18000521a  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180005221  mov     edx, 22h ; '"'
0x180005226  call    WPP_SF_
0x18000522b  mov     r10, cs:WPP_GLOBAL_Control
0x180005232  cmp     word ptr [rbp+57h+arg_8], 0
0x180005237  jnz     loc_180005316
0x18000523d  test    byte ptr [r10+1Ch], 2
0x180005242  jz      short loc_180005260
0x180005244  cmp     byte ptr [r10+19h], 4
0x180005249  jb      short loc_180005260
0x18000524b  mov     rcx, [r10+10h]
0x18000524f  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180005256  mov     edx, 23h ; '#'
0x18000525b  call    WPP_SF_
0x180005260  mov     r9d, dword ptr [rbp+57h+var_80]
0x180005264  mov     r8, rdi
0x180005267  mov     r15, [rbp+57h+var_70]
0x18000526b  sub     r8, r13
0x18000526e  sub     r9d, dword ptr [rbp+57h+var_78]
0x180005272  mov     rdx, r13; struct EXT_OBJ_LIST *
0x180005275  mov     rcx, [r12+8]; unsigned __int16 *
0x18000527a  sar     r8, 3; unsigned int
0x18000527e  lea     rax, [r15+1Ch]
0x180005282  mov     [rsp+0C0h+var_98], rax; __int64
0x180005287  lea     rax, [rbp+57h+arg_18]
0x18000528b  mov     [rsp+0C0h+var_A0], rax; __int64
0x180005290  call    QueryV2Provider
0x180005295  cmp     eax, 0EAh
0x18000529a  jnz     short loc_1800052B8
0x18000529c  lea     rcx, [rbp+57h+Block]
0x1800052a0  call    ?_Uninit@?$vector@UEXT_OBJ_LIST@@V?$allocator@UEXT_OBJ_LIST@@@utl@@@utl@@AEAAXXZ; utl::vector<EXT_OBJ_LIST,utl::allocator<EXT_OBJ_LIST>>::_Uninit(void)
0x1800052a5  mov     r14, [rbp+57h+arg_18]
0x1800052a9  mov     r13d, 0EAh
0x1800052af  movzx   esi, [rbp+57h+arg_0]
0x1800052b3  jmp     loc_1800055D3
0x1800052b8  mov     rax, r13
0x1800052bb  cmp     rax, rdi
0x1800052be  jz      short loc_180005309
0x1800052c0  test    byte ptr [rax+4], 1
0x1800052c4  jz      short loc_1800052CC
0x1800052c6  add     rax, 8
0x1800052ca  jmp     short loc_1800052BB
0x1800052cc  mov     r10, cs:WPP_GLOBAL_Control
0x1800052d3  test    byte ptr [r10+1Ch], 2
0x1800052d8  jz      short loc_180005303
0x1800052da  cmp     byte ptr [r10+19h], 3
0x1800052df  jb      short loc_180005303
0x1800052e1  mov     rcx, [r10+10h]
0x1800052e5  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x1800052ec  mov     edx, 24h ; '$'
0x1800052f1  call    WPP_SF_
0x1800052f6  mov     r10, cs:WPP_GLOBAL_Control
0x1800052fd  mov     r14, [rbp+57h+arg_18]
0x180005301  jmp     short loc_18000531E
0x180005303  mov     r14, [rbp+57h+arg_18]
0x180005307  jmp     short loc_18000531E
0x180005309  mov     r14, [rbp+57h+arg_18]
0x18000530d  mov     r10, cs:WPP_GLOBAL_Control
0x180005314  jmp     short loc_18000537D
0x180005316  mov     r14, [rbp+57h+var_78]
0x18000531a  mov     r15, [rbp+57h+var_70]
0x18000531e  test    byte ptr [r10+1Ch], 2
0x180005323  jz      short loc_180005348
0x180005325  cmp     byte ptr [r10+19h], 3
0x18000532a  jb      short loc_180005348
0x18000532c  mov     rcx, [r10+10h]
0x180005330  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180005337  mov     edx, 25h ; '%'
0x18000533c  call    WPP_SF_
0x180005341  mov     r10, cs:WPP_GLOBAL_Control
0x180005348  mov     rax, cs:?ExtensibleObjects@@3PEAUEXT_OBJECT@@EA; EXT_OBJECT * ExtensibleObjects
0x18000534f  test    rax, rax
0x180005352  jz      short loc_18000537D
0x180005354  cmp     dword ptr [rax+70h], 0
0x180005358  jnz     short loc_180005364
0x18000535a  or      dword ptr [rax+17Ch], 80000000h
0x180005364  mov     rax, [rax]
0x180005367  test    rax, rax
0x18000536a  jnz     short loc_180005354
0x18000536c  mov     r10, cs:WPP_GLOBAL_Control
0x180005373  jmp     short loc_18000537D
0x180005375  mov     r14, [rbp+57h+var_78]
0x180005379  mov     r15, [rbp+57h+var_70]
0x18000537d  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180005381  jz      short loc_180005399
0x180005383  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000538a  mov     rcx, r13; Block
0x18000538d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005392  mov     r10, cs:WPP_GLOBAL_Control
0x180005399  movzx   esi, [rbp+57h+arg_0]
0x18000539d  mov     r13d, 0EAh
0x1800053a3  mov     rdx, [rbp+57h+var_80]
0x1800053a7  mov     rbx, cs:?ExtensibleObjects@@3PEAUEXT_OBJECT@@EA; EXT_OBJECT * ExtensibleObjects
0x1800053ae  lea     r11, __ImageBase
0x1800053b5  mov     r8d, [rbp+57h+arg_10]
0x1800053b9  lea     r9, ?COSTLY_STRING@@3QBGB; "Costly"
0x1800053c0  movzx   edi, sil
0x1800053c4  test    rbx, rbx
0x1800053c7  jz      loc_1800055D0
0x1800053cd  cmp     r8d, 2
0x1800053d1  jz      loc_18000545D
0x1800053d7  test    sil, sil
0x1800053da  jnz     loc_180005474
0x1800053e0  lea     rsi, [rbx+17Ch]
0x1800053e7  mov     ecx, [rsi]
0x1800053e9  test    cl, 10h
0x1800053ec  jnz     def_18000540A; jumptable 000000018000540A default case, cases 5-8
0x1800053f2  lea     eax, [r8-1]; switch 10 cases
  ... truncated ...
```
