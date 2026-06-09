# SIdxKeyTable::StealKeyFromSibling(SIdxKeyTable *,SIdxKeyTable *)

- ea: `0x180038570`
- end: `0x180038c2a`
- name: `?StealKeyFromSibling@SIdxKeyTable@@QEAAKPEAV1@0@Z`
- size: `1722`
- prototype: `unsigned int __fastcall(SIdxKeyTable *__hidden this, struct SIdxKeyTable *, struct SIdxKeyTable *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180011904`

## callees

- `0x1800012b8`
- `0x18000eee0`
- `0x1800109d0`
- `0x180010fa0`
- `0x1800114bc`
- `0x180019e00`
- `0x180038570`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800385f9`
- `wbemcomn!GetMemLogObject` at `0x18003867d`
- `wbemcomn!GetMemLogObject` at `0x1800386dd`
- `wbemcomn!GetMemLogObject` at `0x18003873e`
- `wbemcomn!GetMemLogObject` at `0x18003879f`
- `wbemcomn!GetMemLogObject` at `0x180038810`
- `wbemcomn!GetMemLogObject` at `0x180038890`
- `wbemcomn!GetMemLogObject` at `0x180038900`
- `wbemcomn!GetMemLogObject` at `0x18003897b`
- `wbemcomn!GetMemLogObject` at `0x1800389e3`
- `wbemcomn!GetMemLogObject` at `0x180038a44`
- `wbemcomn!GetMemLogObject` at `0x180038ab4`
- `wbemcomn!GetMemLogObject` at `0x180038b33`
- `wbemcomn!GetMemLogObject` at `0x180038bae`
- `wbemcomn!GetMemLogObject` at `0x1800385f9`
- `wbemcomn!GetMemLogObject` at `0x18003867d`
- `wbemcomn!GetMemLogObject` at `0x1800386dd`
- `wbemcomn!GetMemLogObject` at `0x18003873e`
- `wbemcomn!GetMemLogObject` at `0x18003879f`
- `wbemcomn!GetMemLogObject` at `0x180038810`
- `wbemcomn!GetMemLogObject` at `0x180038890`
- `wbemcomn!GetMemLogObject` at `0x180038900`
- `wbemcomn!GetMemLogObject` at `0x18003897b`
- `wbemcomn!GetMemLogObject` at `0x1800389e3`
- `wbemcomn!GetMemLogObject` at `0x180038a44`
- `wbemcomn!GetMemLogObject` at `0x180038ab4`
- `wbemcomn!GetMemLogObject` at `0x180038b33`
- `wbemcomn!GetMemLogObject` at `0x180038bae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038604`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038688`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800386e8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038749`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800387aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003881b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003889b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003890b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038986`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800389ee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038a4f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038abf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038b3e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038bb9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038604`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038688`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800386e8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038749`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800387aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003881b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003889b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003890b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038986`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800389ee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038a4f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038abf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038b3e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038bb9`

## pseudocode

```c
__int64 __fastcall SIdxKeyTable::StealKeyFromSibling(
        SIdxKeyTable *this,
        struct SIdxKeyTable *a2,
        struct SIdxKeyTable *a3)
{
  int v4; // edx
  int v6; // r8d
  unsigned __int16 v8; // si
  __int64 v9; // rcx
  __int64 v10; // r12
  __int64 v11; // rax
  unsigned int KeyAt; // edi
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v14; // r10
  __int64 v15; // rdx
  __int64 v16; // rcx
  char *v18; // r14
  unsigned int Key; // eax
  CMemoryLog *v20; // rax
  CVarObjHeap *v21; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  int v25; // r14d
  CMemoryLog *v26; // rax
  unsigned __int16 v27; // r8
  char *v28; // rsi
  CMemoryLog *v29; // rax
  int v30; // ecx
  CMemoryLog *v31; // rax
  char *v32; // r14
  unsigned int v33; // eax
  CMemoryLog *v34; // rax
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  unsigned __int16 v37; // r14
  CMemoryLog *v38; // rax
  CMemoryLog *v39; // rax
  unsigned __int16 v40; // r8
  CMemoryLog *v41; // rax
  unsigned int v42; // [rsp+20h] [rbp-28h]
  char *v43; // [rsp+28h] [rbp-20h] BYREF
  __int64 v44; // [rsp+30h] [rbp-18h]
  unsigned __int16 v45; // [rsp+90h] [rbp+48h] BYREF
  unsigned int v46; // [rsp+98h] [rbp+50h]
  int v47; // [rsp+A0h] [rbp+58h]
  int v48; // [rsp+A8h] [rbp+60h]

  v4 = *((_DWORD *)a3 + 1);
  v6 = *((_DWORD *)this + 1);
  v48 = v6;
  v8 = 0;
  v45 = 0;
  v43 = 0;
  v47 = v4;
  while ( 1 )
  {
    if ( v8 >= *((_WORD *)a2 + 6) )
      return 0;
    v9 = *((_QWORD *)a2 + 5);
    v10 = v8;
    v11 = (unsigned __int16)(v8 + 1);
    v44 = v11;
    if ( *(_DWORD *)(v9 + 4LL * v8) == v6 && *(_DWORD *)(v9 + 4 * v11) == v4 )
    {
      KeyAt = SIdxKeyTable::GetKeyAt(a2, v8, &v43);
      if ( KeyAt )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, KeyAt);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 29;
          goto LABEL_13;
        }
        return KeyAt;
      }
      v18 = v43;
      v46 = *(_DWORD *)(*((_QWORD *)a2 + 4) + 4LL * v8);
      Key = SIdxKeyTable::FindKey(this, v43, &v45);
      KeyAt = Key;
      if ( Key && Key != 1168 )
      {
        _BtrMemFree(v18);
        v20 = GetMemLogObject();
        CMemoryLog::Write(v20, KeyAt);
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return KeyAt;
        }
        v15 = 30;
        goto LABEL_22;
      }
      KeyAt = SIdxKeyTable::AddKey((void **)this, v18, v45, v46);
      if ( KeyAt )
      {
        _BtrMemFree(v18);
        v22 = GetMemLogObject();
        CMemoryLog::Write(v22, KeyAt);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 31;
          goto LABEL_13;
        }
        return KeyAt;
      }
      KeyAt = SIdxKeyTable::RemoveKey(a2, v8);
      if ( KeyAt )
      {
        _BtrMemFree(v18);
        v23 = GetMemLogObject();
        CMemoryLog::Write(v23, KeyAt);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 32;
          goto LABEL_13;
        }
        return KeyAt;
      }
      _BtrMemFree(v18);
      KeyAt = SIdxKeyTable::GetKeyAt(a3, 0, &v43);
      if ( KeyAt )
      {
        v24 = GetMemLogObject();
        CMemoryLog::Write(v24, KeyAt);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 33;
          goto LABEL_13;
        }
        return KeyAt;
      }
      v25 = **((_DWORD **)a3 + 4);
      v46 = **((_DWORD **)a3 + 5);
      KeyAt = SIdxKeyTable::RemoveKey(a3, 0);
      if ( KeyAt )
      {
        _BtrMemFree(v43);
        v26 = GetMemLogObject();
        CMemoryLog::Write(v26, KeyAt);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 34;
          goto LABEL_13;
        }
        return KeyAt;
      }
      v27 = v8;
      v28 = v43;
      *(_DWORD *)(*((_QWORD *)this + 5) + 4LL * (unsigned __int16)(v45 + 1)) = v46;
      KeyAt = SIdxKeyTable::AddKey((void **)a2, v28, v27, v25);
      if ( KeyAt )
      {
        _BtrMemFree(v28);
        v29 = GetMemLogObject();
        CMemoryLog::Write(v29, KeyAt);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 35;
          goto LABEL_13;
        }
        return KeyAt;
      }
      *(_DWORD *)(*((_QWORD *)a2 + 5) + 4 * v10) = v48;
      v30 = v47;
      goto LABEL_86;
    }
    if ( *(_DWORD *)(v9 + 4LL * v8) == v4 && *(_DWORD *)(v9 + 4 * v11) == v6 )
      break;
    v8 = v11;
  }
  KeyAt = SIdxKeyTable::GetKeyAt(a2, v8, &v43);
  if ( KeyAt )
  {
    v31 = GetMemLogObject();
    CMemoryLog::Write(v31, KeyAt);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 36;
      goto LABEL_13;
    }
    return KeyAt;
  }
  v32 = v43;
  v46 = *(_DWORD *)(*((_QWORD *)a2 + 4) + 4LL * v8);
  v33 = SIdxKeyTable::FindKey(this, v43, &v45);
  KeyAt = v33;
  if ( v33 && v33 != 1168 )
  {
    _BtrMemFree(v32);
    v34 = GetMemLogObject();
    CMemoryLog::Write(v34, KeyAt);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return KeyAt;
    }
    v15 = 37;
LABEL_22:
    v16 = *((_QWORD *)v21 + 2);
LABEL_14:
    WPP_SF_d(v16, v15, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, KeyAt);
    return KeyAt;
  }
  KeyAt = SIdxKeyTable::AddKey((void **)this, v32, v45, v46);
  if ( KeyAt )
  {
    _BtrMemFree(v32);
    v35 = GetMemLogObject();
    CMemoryLog::Write(v35, KeyAt);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return KeyAt;
    }
    v15 = 38;
    goto LABEL_13;
  }
  KeyAt = SIdxKeyTable::RemoveKey(a2, v8);
  if ( KeyAt )
  {
    _BtrMemFree(v32);
    v36 = GetMemLogObject();
    CMemoryLog::Write(v36, KeyAt);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return KeyAt;
    }
    v15 = 39;
    goto LABEL_13;
  }
  _BtrMemFree(v32);
  LOWORD(v46) = *((_WORD *)a3 + 6);
  v37 = v46 - 1;
  KeyAt = SIdxKeyTable::GetKeyAt(a3, (unsigned __int16)v46 - 1, &v43);
  if ( KeyAt )
  {
    v38 = GetMemLogObject();
    CMemoryLog::Write(v38, KeyAt);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return KeyAt;
    }
    v15 = 40;
    goto LABEL_13;
  }
  v42 = *(_DWORD *)(*((_QWORD *)a3 + 4) + 4LL * v37);
  v46 = *(_DWORD *)(*((_QWORD *)a3 + 5) + 4LL * (unsigned __int16)v46);
  KeyAt = SIdxKeyTable::RemoveKey(a3, v37);
  if ( KeyAt )
  {
    _BtrMemFree(v43);
    v39 = GetMemLogObject();
    CMemoryLog::Write(v39, KeyAt);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return KeyAt;
    }
    v15 = 41;
    goto LABEL_13;
  }
  v40 = v8;
  v28 = v43;
  *(_DWORD *)(*((_QWORD *)this + 5) + 4LL * v45) = v46;
  KeyAt = SIdxKeyTable::AddKey((void **)a2, v28, v40, v42);
  if ( KeyAt )
  {
    _BtrMemFree(v28);
    v41 = GetMemLogObject();
    CMemoryLog::Write(v41, KeyAt);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return KeyAt;
    }
    v15 = 42;
LABEL_13:
    v16 = *((_QWORD *)v14 + 2);
    goto LABEL_14;
  }
  *(_DWORD *)(*((_QWORD *)a2 + 5) + 4 * v10) = v47;
  v30 = v48;
LABEL_86:
  *(_DWORD *)(*((_QWORD *)a2 + 5) + 4 * v44) = v30;
  _BtrMemFree(v28);
  return 0;
}

```

## disassembly

```asm
0x180038570  push    rbp
0x180038572  push    rbx
0x180038573  push    rsi
0x180038574  push    rdi
0x180038575  push    r12
0x180038577  push    r13
0x180038579  push    r14
0x18003857b  push    r15
0x18003857d  mov     rbp, rsp
0x180038580  sub     rsp, 48h
0x180038584  xor     eax, eax
0x180038586  mov     rbx, rdx
0x180038589  mov     edx, [r8+4]
0x18003858d  mov     r15, r8
0x180038590  mov     r8d, [rcx+4]
0x180038594  mov     r13, rcx
0x180038597  mov     [rbp+arg_18], r8d
0x18003859b  xor     esi, esi
0x18003859d  mov     [rbp+arg_0], ax
0x1800385a1  mov     [rbp+var_20], rax
0x1800385a5  mov     [rbp+arg_10], edx
0x1800385a8  cmp     si, [rbx+0Ch]
0x1800385ac  jnb     loc_180038C17
0x1800385b2  mov     rcx, [rbx+28h]
0x1800385b6  lea     eax, [rsi+1]
0x1800385b9  movzx   r12d, si
0x1800385bd  movzx   eax, ax
0x1800385c0  mov     [rbp+var_18], rax
0x1800385c4  cmp     [rcx+r12*4], r8d
0x1800385c8  jnz     short loc_1800385CF
0x1800385ca  cmp     [rcx+rax*4], edx
0x1800385cd  jz      short loc_1800385E4
0x1800385cf  cmp     [rcx+r12*4], edx
0x1800385d3  jnz     short loc_1800385DF
0x1800385d5  cmp     [rcx+rax*4], r8d
0x1800385d9  jz      loc_1800388EB
0x1800385df  movzx   esi, ax
0x1800385e2  jmp     short loc_1800385A8
0x1800385e4  lea     r8, [rbp+var_20]; char **
0x1800385e8  movzx   edx, si; unsigned __int16
0x1800385eb  mov     rcx, rbx; this
0x1800385ee  call    ?GetKeyAt@SIdxKeyTable@@QEAAKGPEAPEAD@Z; SIdxKeyTable::GetKeyAt(ushort,char * *)
0x1800385f3  mov     edi, eax
0x1800385f5  test    eax, eax
0x1800385f7  jz      short loc_18003864A
0x1800385f9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800385ff  mov     rcx, rax
0x180038602  mov     edx, edi
0x180038604  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003860a  mov     r10, cs:WPP_GLOBAL_Control
0x180038611  lea     rcx, WPP_GLOBAL_Control
0x180038618  cmp     r10, rcx
0x18003861b  jz      short loc_180038643
0x18003861d  test    byte ptr [r10+1Ch], 1
0x180038622  jz      short loc_180038643
0x180038624  cmp     byte ptr [r10+19h], 2
0x180038629  jb      short loc_180038643
0x18003862b  mov     edx, 1Dh
0x180038630  mov     rcx, [r10+10h]
0x180038634  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18003863b  mov     r9d, edi
0x18003863e  call    WPP_SF_d
0x180038643  mov     eax, edi
0x180038645  jmp     loc_180038C19
0x18003864a  mov     rax, [rbx+20h]
0x18003864e  lea     r8, [rbp+arg_0]; unsigned __int16 *
0x180038652  mov     r14, [rbp+var_20]
0x180038656  mov     rcx, r13; this
0x180038659  mov     rdx, r14; char *
0x18003865c  mov     eax, [rax+r12*4]
0x180038660  mov     [rbp+arg_8], eax
0x180038663  call    ?FindKey@SIdxKeyTable@@QEAAKPEADPEAG@Z; SIdxKeyTable::FindKey(char *,ushort *)
0x180038668  mov     edi, eax
0x18003866a  test    eax, eax
0x18003866c  jz      short loc_1800386BB
0x18003866e  cmp     eax, 490h
0x180038673  jz      short loc_1800386BB
0x180038675  mov     rcx, r14; void *
0x180038678  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18003867d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180038683  mov     rcx, rax
0x180038686  mov     edx, edi
0x180038688  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003868e  mov     rax, cs:WPP_GLOBAL_Control
0x180038695  lea     rcx, WPP_GLOBAL_Control
0x18003869c  cmp     rax, rcx
0x18003869f  jz      short loc_180038643
0x1800386a1  test    byte ptr [rax+1Ch], 1
0x1800386a5  jz      short loc_180038643
0x1800386a7  cmp     byte ptr [rax+19h], 2
0x1800386ab  jb      short loc_180038643
0x1800386ad  mov     edx, 1Eh
0x1800386b2  mov     rcx, [rax+10h]
0x1800386b6  jmp     loc_180038634
0x1800386bb  mov     r9d, [rbp+arg_8]; unsigned int
0x1800386bf  mov     rdx, r14; char *
0x1800386c2  movzx   r8d, [rbp+arg_0]; unsigned __int16
0x1800386c7  mov     rcx, r13; this
0x1800386ca  call    ?AddKey@SIdxKeyTable@@QEAAKPEADGK@Z; SIdxKeyTable::AddKey(char *,ushort,ulong)
0x1800386cf  mov     edi, eax
0x1800386d1  test    eax, eax
0x1800386d3  jz      short loc_180038725
0x1800386d5  mov     rcx, r14; void *
0x1800386d8  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x1800386dd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800386e3  mov     rcx, rax
0x1800386e6  mov     edx, edi
0x1800386e8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800386ee  mov     r10, cs:WPP_GLOBAL_Control
0x1800386f5  lea     rcx, WPP_GLOBAL_Control
0x1800386fc  cmp     r10, rcx
0x1800386ff  jz      loc_180038643
0x180038705  test    byte ptr [r10+1Ch], 1
0x18003870a  jz      loc_180038643
0x180038710  cmp     byte ptr [r10+19h], 2
0x180038715  jb      loc_180038643
0x18003871b  mov     edx, 1Fh
0x180038720  jmp     loc_180038630
0x180038725  movzx   edx, si; unsigned __int16
0x180038728  mov     rcx, rbx; this
0x18003872b  call    ?RemoveKey@SIdxKeyTable@@QEAAKG@Z; SIdxKeyTable::RemoveKey(ushort)
0x180038730  mov     edi, eax
0x180038732  mov     rcx, r14; void *
0x180038735  test    eax, eax
0x180038737  jz      short loc_180038786
0x180038739  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18003873e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180038744  mov     rcx, rax
0x180038747  mov     edx, edi
0x180038749  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003874f  mov     r10, cs:WPP_GLOBAL_Control
0x180038756  lea     rcx, WPP_GLOBAL_Control
0x18003875d  cmp     r10, rcx
0x180038760  jz      loc_180038643
0x180038766  test    byte ptr [r10+1Ch], 1
0x18003876b  jz      loc_180038643
0x180038771  cmp     byte ptr [r10+19h], 2
0x180038776  jb      loc_180038643
0x18003877c  mov     edx, 20h ; ' '
0x180038781  jmp     loc_180038630
0x180038786  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18003878b  xor     edx, edx; unsigned __int16
0x18003878d  lea     r8, [rbp+var_20]; char **
0x180038791  mov     rcx, r15; this
0x180038794  call    ?GetKeyAt@SIdxKeyTable@@QEAAKGPEAPEAD@Z; SIdxKeyTable::GetKeyAt(ushort,char * *)
0x180038799  mov     edi, eax
0x18003879b  test    eax, eax
0x18003879d  jz      short loc_1800387E7
0x18003879f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800387a5  mov     rcx, rax
0x1800387a8  mov     edx, edi
0x1800387aa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800387b0  mov     r10, cs:WPP_GLOBAL_Control
0x1800387b7  lea     rcx, WPP_GLOBAL_Control
0x1800387be  cmp     r10, rcx
0x1800387c1  jz      loc_180038643
0x1800387c7  test    byte ptr [r10+1Ch], 1
0x1800387cc  jz      loc_180038643
0x1800387d2  cmp     byte ptr [r10+19h], 2
0x1800387d7  jb      loc_180038643
0x1800387dd  mov     edx, 21h ; '!'
0x1800387e2  jmp     loc_180038630
0x1800387e7  mov     rax, [r15+20h]
0x1800387eb  xor     edx, edx; unsigned __int16
0x1800387ed  mov     rcx, r15; this
0x1800387f0  mov     r14d, [rax]
0x1800387f3  mov     rax, [r15+28h]
0x1800387f7  mov     eax, [rax]
0x1800387f9  mov     [rbp+arg_8], eax
0x1800387fc  call    ?RemoveKey@SIdxKeyTable@@QEAAKG@Z; SIdxKeyTable::RemoveKey(ushort)
0x180038801  mov     edi, eax
0x180038803  test    eax, eax
0x180038805  jz      short loc_180038858
0x180038807  mov     rcx, [rbp+var_20]; void *
0x18003880b  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180038810  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180038816  mov     rcx, rax
0x180038819  mov     edx, edi
0x18003881b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180038821  mov     r10, cs:WPP_GLOBAL_Control
0x180038828  lea     rcx, WPP_GLOBAL_Control
0x18003882f  cmp     r10, rcx
0x180038832  jz      loc_180038643
0x180038838  test    byte ptr [r10+1Ch], 1
0x18003883d  jz      loc_180038643
0x180038843  cmp     byte ptr [r10+19h], 2
0x180038848  jb      loc_180038643
0x18003884e  mov     edx, 22h ; '"'
0x180038853  jmp     loc_180038630
0x180038858  movzx   eax, [rbp+arg_0]
0x18003885c  movzx   r8d, si; unsigned __int16
0x180038860  mov     edx, [rbp+arg_8]
0x180038863  inc     ax
0x180038866  mov     rsi, [rbp+var_20]
0x18003886a  mov     r9d, r14d; unsigned int
0x18003886d  movzx   ecx, ax
0x180038870  mov     rax, [r13+28h]
0x180038874  mov     [rax+rcx*4], edx
0x180038877  mov     rdx, rsi; char *
0x18003887a  mov     rcx, rbx; this
0x18003887d  call    ?AddKey@SIdxKeyTable@@QEAAKPEADGK@Z; SIdxKeyTable::AddKey(char *,ushort,ulong)
0x180038882  mov     edi, eax
0x180038884  test    eax, eax
0x180038886  jz      short loc_1800388D8
0x180038888  mov     rcx, rsi; void *
0x18003888b  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180038890  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180038896  mov     rcx, rax
0x180038899  mov     edx, edi
0x18003889b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800388a1  mov     r10, cs:WPP_GLOBAL_Control
0x1800388a8  lea     rcx, WPP_GLOBAL_Control
0x1800388af  cmp     r10, rcx
0x1800388b2  jz      loc_180038643
0x1800388b8  test    byte ptr [r10+1Ch], 1
0x1800388bd  jz      loc_180038643
0x1800388c3  cmp     byte ptr [r10+19h], 2
0x1800388c8  jb      loc_180038643
0x1800388ce  mov     edx, 23h ; '#'
0x1800388d3  jmp     loc_180038630
0x1800388d8  mov     ecx, [rbp+arg_18]
0x1800388db  mov     rax, [rbx+28h]
0x1800388df  mov     [rax+r12*4], ecx
0x1800388e3  mov     ecx, [rbp+arg_10]
0x1800388e6  jmp     loc_180038C04
0x1800388eb  lea     r8, [rbp+var_20]; char **
0x1800388ef  movzx   edx, si; unsigned __int16
0x1800388f2  mov     rcx, rbx; this
0x1800388f5  call    ?GetKeyAt@SIdxKeyTable@@QEAAKGPEAPEAD@Z; SIdxKeyTable::GetKeyAt(ushort,char * *)
0x1800388fa  mov     edi, eax
0x1800388fc  test    eax, eax
0x1800388fe  jz      short loc_180038948
0x180038900  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180038906  mov     rcx, rax
0x180038909  mov     edx, edi
0x18003890b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180038911  mov     r10, cs:WPP_GLOBAL_Control
0x180038918  lea     rcx, WPP_GLOBAL_Control
0x18003891f  cmp     r10, rcx
0x180038922  jz      loc_180038643
0x180038928  test    byte ptr [r10+1Ch], 1
0x18003892d  jz      loc_180038643
0x180038933  cmp     byte ptr [r10+19h], 2
0x180038938  jb      loc_180038643
0x18003893e  mov     edx, 24h ; '$'
0x180038943  jmp     loc_180038630
0x180038948  mov     rax, [rbx+20h]
0x18003894c  lea     r8, [rbp+arg_0]; unsigned __int16 *
0x180038950  mov     r14, [rbp+var_20]
0x180038954  mov     rcx, r13; this
0x180038957  mov     rdx, r14; char *
0x18003895a  mov     eax, [rax+r12*4]
0x18003895e  mov     [rbp+arg_8], eax
0x180038961  call    ?FindKey@SIdxKeyTable@@QEAAKPEADPEAG@Z; SIdxKeyTable::FindKey(char *,ushort *)
0x180038966  mov     edi, eax
0x180038968  test    eax, eax
0x18003896a  jz      short loc_1800389C1
0x18003896c  cmp     eax, 490h
0x180038971  jz      short loc_1800389C1
0x180038973  mov     rcx, r14; void *
0x180038976  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18003897b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180038981  mov     rcx, rax
0x180038984  mov     edx, edi
0x180038986  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003898c  mov     rax, cs:WPP_GLOBAL_Control
0x180038993  lea     rcx, WPP_GLOBAL_Control
0x18003899a  cmp     rax, rcx
0x18003899d  jz      loc_180038643
0x1800389a3  test    byte ptr [rax+1Ch], 1
0x1800389a7  jz      loc_180038643
0x1800389ad  cmp     byte ptr [rax+19h], 2
0x1800389b1  jb      loc_180038643
0x1800389b7  mov     edx, 25h ; '%'
0x1800389bc  jmp     loc_1800386B2
0x1800389c1  mov     r9d, [rbp+arg_8]; unsigned int
0x1800389c5  mov     rdx, r14; char *
0x1800389c8  movzx   r8d, [rbp+arg_0]; unsigned __int16
0x1800389cd  mov     rcx, r13; this
0x1800389d0  call    ?AddKey@SIdxKeyTable@@QEAAKPEADGK@Z; SIdxKeyTable::AddKey(char *,ushort,ulong)
0x1800389d5  mov     edi, eax
0x1800389d7  test    eax, eax
0x1800389d9  jz      short loc_180038A2B
0x1800389db  mov     rcx, r14; void *
0x1800389de  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x1800389e3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800389e9  mov     rcx, rax
0x1800389ec  mov     edx, edi
0x1800389ee  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800389f4  mov     r10, cs:WPP_GLOBAL_Control
0x1800389fb  lea     rcx, WPP_GLOBAL_Control
0x180038a02  cmp     r10, rcx
0x180038a05  jz      loc_180038643
0x180038a0b  test    byte ptr [r10+1Ch], 1
0x180038a10  jz      loc_180038643
0x180038a16  cmp     byte ptr [r10+19h], 2
0x180038a1b  jb      loc_180038643
0x180038a21  mov     edx, 26h ; '&'
0x180038a26  jmp     loc_180038630
0x180038a2b  movzx   edx, si; unsigned __int16
  ... truncated ...
```
