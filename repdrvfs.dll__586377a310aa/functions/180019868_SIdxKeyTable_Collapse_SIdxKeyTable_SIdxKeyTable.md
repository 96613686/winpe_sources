# SIdxKeyTable::Collapse(SIdxKeyTable *,SIdxKeyTable *)

- ea: `0x180019868`
- end: `0x180019df4`
- name: `?Collapse@SIdxKeyTable@@QEAAKPEAV1@0@Z`
- size: `1420`
- prototype: `__int64 __fastcall(SIdxKeyTable *this, struct SIdxKeyTable *, struct SIdxKeyTable *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011904`

## callees

- `0x1800012b8`
- `0x18000eee0`
- `0x1800109d0`
- `0x180010fa0`
- `0x1800114bc`
- `0x180019868`
- `0x180019e00`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800198fb`
- `wbemcomn!GetMemLogObject` at `0x18001996f`
- `wbemcomn!GetMemLogObject` at `0x1800199e1`
- `wbemcomn!GetMemLogObject` at `0x180019b05`
- `wbemcomn!GetMemLogObject` at `0x180019b70`
- `wbemcomn!GetMemLogObject` at `0x180019beb`
- `wbemcomn!GetMemLogObject` at `0x180019c56`
- `wbemcomn!GetMemLogObject` at `0x180019cb9`
- `wbemcomn!GetMemLogObject` at `0x180019d07`
- `wbemcomn!GetMemLogObject` at `0x180019d5b`
- `wbemcomn!GetMemLogObject` at `0x1800198fb`
- `wbemcomn!GetMemLogObject` at `0x18001996f`
- `wbemcomn!GetMemLogObject` at `0x1800199e1`
- `wbemcomn!GetMemLogObject` at `0x180019b05`
- `wbemcomn!GetMemLogObject` at `0x180019b70`
- `wbemcomn!GetMemLogObject` at `0x180019beb`
- `wbemcomn!GetMemLogObject` at `0x180019c56`
- `wbemcomn!GetMemLogObject` at `0x180019cb9`
- `wbemcomn!GetMemLogObject` at `0x180019d07`
- `wbemcomn!GetMemLogObject` at `0x180019d5b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019906`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001997a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800199ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019b10`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019b7b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019bf6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019c61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019cc4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019d17`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019d66`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019906`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001997a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800199ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019b10`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019b7b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019bf6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019c61`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019cc4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019d17`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019d66`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SIdxKeyTable::Collapse(SIdxKeyTable *this, struct SIdxKeyTable *a2, struct SIdxKeyTable *a3)
{
  int v3; // r9d
  int v5; // edx
  int v6; // r13d
  unsigned __int16 v7; // r14
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned int KeyAt; // esi
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v14; // r10
  __int64 v15; // rdx
  __int64 result; // rax
  int v17; // r13d
  CMemoryLog *v18; // rax
  char *v19; // rsi
  char *v20; // rdx
  int v21; // r14d
  unsigned int v22; // edi
  CMemoryLog *v23; // rax
  CVarObjHeap *v24; // r10
  __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned __int16 v27; // r12
  unsigned __int16 i; // si
  __int64 v29; // rax
  char *v30; // r14
  int v31; // edi
  CMemoryLog *v32; // rax
  int v33; // r13d
  CMemoryLog *v34; // rax
  char *v35; // rsi
  char *v36; // rdx
  unsigned int Key; // eax
  CMemoryLog *v38; // rax
  CVarObjHeap *v39; // rax
  CMemoryLog *v40; // rax
  CMemoryLog *v41; // rax
  CMemoryLog *v42; // rax
  CMemoryLog *v43; // rax
  _DWORD *v44; // rax
  unsigned __int16 v45; // [rsp+60h] [rbp+40h] BYREF
  char *v46; // [rsp+68h] [rbp+48h] BYREF
  char *v47; // [rsp+70h] [rbp+50h] BYREF

  v3 = *((_DWORD *)a3 + 1);
  v45 = 0;
  v5 = *((_DWORD *)this + 1);
  v6 = 0;
  v47 = 0;
  v7 = 0;
  LODWORD(v46) = v5;
  while ( 1 )
  {
    if ( v7 >= *((_WORD *)a2 + 6) )
      goto LABEL_29;
    v10 = *((_QWORD *)a2 + 5);
    v11 = (unsigned __int16)(v7 + 1);
    if ( *(_DWORD *)(v10 + 4LL * v7) == v3 && *(_DWORD *)(v10 + 4 * v11) == v5 )
    {
      KeyAt = SIdxKeyTable::GetKeyAt(a2, v7, &v47);
      if ( KeyAt )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, KeyAt);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 43;
          goto LABEL_13;
        }
        return KeyAt;
      }
      v17 = *(_DWORD *)(*((_QWORD *)a2 + 4) + 4LL * v7);
      KeyAt = SIdxKeyTable::RemoveKey(a2, v7);
      if ( KeyAt )
      {
        _BtrMemFree(v47);
        v18 = GetMemLogObject();
        CMemoryLog::Write(v18, KeyAt);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 44;
          goto LABEL_13;
        }
        return KeyAt;
      }
      v19 = v47;
      v20 = v47;
      *(_DWORD *)(*((_QWORD *)a2 + 5) + 4LL * v7) = (_DWORD)v46;
      v21 = *(_DWORD *)(*((_QWORD *)a3 + 5) + 4LL * *((unsigned int *)a3 + 3));
      v22 = SIdxKeyTable::AddKey((void **)this, v20, 0, v17);
      if ( v22 )
      {
        _BtrMemFree(v19);
        v23 = GetMemLogObject();
        CMemoryLog::Write(v23, v22);
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return v22;
        }
        v25 = 45;
        goto LABEL_25;
      }
      **((_DWORD **)this + 5) = v21;
      _BtrMemFree(v19);
      v6 = 0;
LABEL_29:
      v27 = *((_WORD *)a3 + 6);
      for ( i = 0; ; ++i )
      {
        if ( i >= v27 )
        {
          if ( v6 )
            *(_DWORD *)(*((_QWORD *)this + 5) + 4LL * *((unsigned __int16 *)this + 6)) = *(_DWORD *)(*((_QWORD *)a3 + 5) + 4LL * *((unsigned int *)a3 + 3));
          v44 = (_DWORD *)*((_QWORD *)a3 + 8);
          *v44 = 0;
          v44[9] = 0;
          result = 0;
          *((_DWORD *)a3 + 15) = 0;
          *((_DWORD *)a3 + 3) = 0;
          return result;
        }
        v46 = 0;
        v22 = SIdxKeyTable::GetKeyAt(a3, i, &v46);
        if ( v22 )
          break;
        v29 = *((_QWORD *)a3 + 4);
        v30 = v46;
        v47 = (char *)i;
        v31 = *(_DWORD *)(v29 + 4LL * i);
        if ( SIdxKeyTable::FindKey(this, v46, &v45) != 1168 )
        {
          _BtrMemFree(v30);
          v42 = GetMemLogObject();
          CMemoryLog::Write(v42, 11);
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 11);
          }
          return 11;
        }
        v22 = SIdxKeyTable::AddKey((void **)this, v30, v45, v31);
        if ( v22 )
        {
          _BtrMemFree(v30);
          v41 = GetMemLogObject();
          CMemoryLog::Write(v41, v22);
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v25 = 52;
            goto LABEL_51;
          }
          return v22;
        }
        *(_DWORD *)(*((_QWORD *)this + 5) + 4LL * v45) = *(_DWORD *)(*((_QWORD *)a3 + 5) + 4LL * (_QWORD)v47);
        _BtrMemFree(v30);
      }
      v43 = GetMemLogObject();
      CMemoryLog::Write(v43, v22);
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = 50;
        goto LABEL_51;
      }
      return v22;
    }
    if ( *(_DWORD *)(v10 + 4LL * v7) == v5 && *(_DWORD *)(v10 + 4 * v11) == v3 )
      break;
    ++v7;
  }
  KeyAt = SIdxKeyTable::GetKeyAt(a2, v7, &v47);
  if ( KeyAt )
  {
    v32 = GetMemLogObject();
    CMemoryLog::Write(v32, KeyAt);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 46;
      goto LABEL_13;
    }
    return KeyAt;
  }
  v33 = *(_DWORD *)(*((_QWORD *)a2 + 4) + 4LL * v7);
  KeyAt = SIdxKeyTable::RemoveKey(a2, v7);
  if ( KeyAt )
  {
    _BtrMemFree(v47);
    v34 = GetMemLogObject();
    CMemoryLog::Write(v34, KeyAt);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 47;
LABEL_13:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, KeyAt);
    }
    return KeyAt;
  }
  v35 = v47;
  v36 = v47;
  *(_DWORD *)(*((_QWORD *)a2 + 5) + 4LL * v7) = (_DWORD)v46;
  Key = SIdxKeyTable::FindKey(this, v36, &v45);
  v22 = Key;
  if ( !Key || Key == 1168 )
  {
    v22 = SIdxKeyTable::AddKey((void **)this, v35, v45, v33);
    if ( v22 )
    {
      _BtrMemFree(v35);
      v40 = GetMemLogObject();
      CMemoryLog::Write(v40, v22);
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v22;
      }
      v25 = 49;
LABEL_25:
      v26 = *((_QWORD *)v24 + 2);
LABEL_26:
      WPP_SF_d(v26, v25, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v22);
      return v22;
    }
    _BtrMemFree(v35);
    v6 = 1;
    goto LABEL_29;
  }
  _BtrMemFree(v35);
  v38 = GetMemLogObject();
  CMemoryLog::Write(v38, v22);
  v39 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v25 = 48;
LABEL_51:
    v26 = *((_QWORD *)v39 + 2);
    goto LABEL_26;
  }
  return v22;
}

```

## disassembly

```asm
0x180019868  mov     [rsp-38h+arg_18], rbx
0x18001986d  push    rbp
0x18001986e  push    rsi
0x18001986f  push    rdi
0x180019870  push    r12
0x180019872  push    r13
0x180019874  push    r14
0x180019876  push    r15
0x180019878  mov     rbp, rsp
0x18001987b  sub     rsp, 20h
0x18001987f  mov     r9d, [r8+4]
0x180019883  xor     eax, eax
0x180019885  mov     rdi, rdx
0x180019888  mov     [rbp+arg_0], ax
0x18001988c  mov     edx, [rcx+4]
0x18001988f  xor     r13d, r13d
0x180019892  mov     [rbp+arg_10], rax
0x180019896  xor     r14d, r14d
0x180019899  mov     dword ptr [rbp+arg_8], edx
0x18001989c  mov     rbx, r8
0x18001989f  mov     r15, rcx
0x1800198a2  mov     r8d, 1
0x1800198a8  cmp     r14w, [rdi+0Ch]
0x1800198ad  jnb     loc_180019A41
0x1800198b3  mov     rcx, [rdi+28h]
0x1800198b7  lea     eax, [r8+r14]
0x1800198bb  movzx   r12d, r14w
0x1800198bf  movzx   r8d, ax
0x1800198c3  cmp     [rcx+r12*4], r9d
0x1800198c7  jnz     short loc_1800198CF
0x1800198c9  cmp     [rcx+r8*4], edx
0x1800198cd  jz      short loc_1800198E5
0x1800198cf  cmp     [rcx+r12*4], edx
0x1800198d3  jnz     short loc_1800198DF
0x1800198d5  cmp     [rcx+r8*4], r9d
0x1800198d9  jz      loc_180019AEF
0x1800198df  movzx   r14d, r8w
0x1800198e3  jmp     short loc_1800198A2
0x1800198e5  lea     r8, [rbp+arg_10]; char **
0x1800198e9  movzx   edx, r14w; unsigned __int16
0x1800198ed  mov     rcx, rdi; this
0x1800198f0  call    ?GetKeyAt@SIdxKeyTable@@QEAAKGPEAPEAD@Z; SIdxKeyTable::GetKeyAt(ushort,char * *)
0x1800198f5  mov     esi, eax
0x1800198f7  test    eax, eax
0x1800198f9  jz      short loc_18001994C
0x1800198fb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180019901  mov     rcx, rax
0x180019904  mov     edx, esi
0x180019906  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001990c  mov     r10, cs:WPP_GLOBAL_Control
0x180019913  lea     rcx, WPP_GLOBAL_Control
0x18001991a  cmp     r10, rcx
0x18001991d  jz      short loc_180019945
0x18001991f  test    byte ptr [r10+1Ch], 1
0x180019924  jz      short loc_180019945
0x180019926  cmp     byte ptr [r10+19h], 2
0x18001992b  jb      short loc_180019945
0x18001992d  mov     edx, 2Bh ; '+'
0x180019932  mov     rcx, [r10+10h]
0x180019936  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18001993d  mov     r9d, esi
0x180019940  call    WPP_SF_d
0x180019945  mov     eax, esi
0x180019947  jmp     loc_180019DDF
0x18001994c  mov     rax, [rdi+20h]
0x180019950  movzx   edx, r14w; unsigned __int16
0x180019954  mov     rcx, rdi; this
0x180019957  mov     r13d, [rax+r12*4]
0x18001995b  call    ?RemoveKey@SIdxKeyTable@@QEAAKG@Z; SIdxKeyTable::RemoveKey(ushort)
0x180019960  mov     esi, eax
0x180019962  test    eax, eax
0x180019964  jz      short loc_1800199A8
0x180019966  mov     rcx, [rbp+arg_10]; void *
0x18001996a  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18001996f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180019975  mov     rcx, rax
0x180019978  mov     edx, esi
0x18001997a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180019980  mov     r10, cs:WPP_GLOBAL_Control
0x180019987  lea     rcx, WPP_GLOBAL_Control
0x18001998e  cmp     r10, rcx
0x180019991  jz      short loc_180019945
0x180019993  test    byte ptr [r10+1Ch], 1
0x180019998  jz      short loc_180019945
0x18001999a  cmp     byte ptr [r10+19h], 2
0x18001999f  jb      short loc_180019945
0x1800199a1  mov     edx, 2Ch ; ','
0x1800199a6  jmp     short loc_180019932
0x1800199a8  mov     rax, [rdi+28h]
0x1800199ac  xor     r8d, r8d; unsigned __int16
0x1800199af  mov     ecx, dword ptr [rbp+arg_8]
0x1800199b2  mov     r9d, r13d; unsigned int
0x1800199b5  mov     rsi, [rbp+arg_10]
0x1800199b9  mov     rdx, rsi; char *
0x1800199bc  mov     [rax+r12*4], ecx
0x1800199c0  mov     ecx, [rbx+0Ch]
0x1800199c3  mov     rax, [rbx+28h]
0x1800199c7  mov     r14d, [rax+rcx*4]
0x1800199cb  mov     rcx, r15; this
0x1800199ce  call    ?AddKey@SIdxKeyTable@@QEAAKPEADGK@Z; SIdxKeyTable::AddKey(char *,ushort,ulong)
0x1800199d3  mov     edi, eax
0x1800199d5  mov     rcx, rsi; void *
0x1800199d8  test    eax, eax
0x1800199da  jz      short loc_180019A32
0x1800199dc  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x1800199e1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800199e7  mov     rcx, rax
0x1800199ea  mov     edx, edi
0x1800199ec  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800199f2  mov     r10, cs:WPP_GLOBAL_Control
0x1800199f9  lea     rcx, WPP_GLOBAL_Control
0x180019a00  cmp     r10, rcx
0x180019a03  jz      short loc_180019A2B
0x180019a05  test    byte ptr [r10+1Ch], 1
0x180019a0a  jz      short loc_180019A2B
0x180019a0c  cmp     byte ptr [r10+19h], 2
0x180019a11  jb      short loc_180019A2B
0x180019a13  mov     edx, 2Dh ; '-'
0x180019a18  mov     rcx, [r10+10h]
0x180019a1c  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180019a23  mov     r9d, edi
0x180019a26  call    WPP_SF_d
0x180019a2b  mov     eax, edi
0x180019a2d  jmp     loc_180019DDF
0x180019a32  mov     rax, [r15+28h]
0x180019a36  mov     [rax], r14d
0x180019a39  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180019a3e  xor     r13d, r13d
0x180019a41  mov     r14d, 1
0x180019a47  movzx   r12d, word ptr [rbx+0Ch]
0x180019a4c  xor     esi, esi
0x180019a4e  cmp     si, r12w
0x180019a52  jnb     loc_180019DA1
0x180019a58  lea     r8, [rbp+arg_8]; char **
0x180019a5c  mov     [rbp+arg_8], 0
0x180019a64  movzx   edx, si; unsigned __int16
0x180019a67  mov     rcx, rbx; this
0x180019a6a  call    ?GetKeyAt@SIdxKeyTable@@QEAAKGPEAPEAD@Z; SIdxKeyTable::GetKeyAt(ushort,char * *)
0x180019a6f  mov     edi, eax
0x180019a71  test    eax, eax
0x180019a73  jnz     loc_180019D5B
0x180019a79  mov     rax, [rbx+20h]
0x180019a7d  lea     r8, [rbp+arg_0]; unsigned __int16 *
0x180019a81  mov     r14, [rbp+arg_8]
0x180019a85  movzx   ecx, si
0x180019a88  mov     rdx, r14; char *
0x180019a8b  mov     [rbp+arg_10], rcx
0x180019a8f  mov     edi, [rax+rcx*4]
0x180019a92  mov     rcx, r15; this
0x180019a95  call    ?FindKey@SIdxKeyTable@@QEAAKPEADPEAG@Z; SIdxKeyTable::FindKey(char *,ushort *)
0x180019a9a  cmp     eax, 490h
0x180019a9f  jnz     loc_180019CFF
0x180019aa5  movzx   r8d, [rbp+arg_0]; unsigned __int16
0x180019aaa  mov     r9d, edi; unsigned int
0x180019aad  mov     rdx, r14; char *
0x180019ab0  mov     rcx, r15; this
0x180019ab3  call    ?AddKey@SIdxKeyTable@@QEAAKPEADGK@Z; SIdxKeyTable::AddKey(char *,ushort,ulong)
0x180019ab8  mov     edi, eax
0x180019aba  test    eax, eax
0x180019abc  jnz     loc_180019CB1
0x180019ac2  mov     rax, [rbx+28h]
0x180019ac6  mov     rcx, [rbp+arg_10]
0x180019aca  movzx   r8d, [rbp+arg_0]
0x180019acf  mov     rdx, [r15+28h]
0x180019ad3  mov     eax, [rax+rcx*4]
0x180019ad6  mov     rcx, r14; void *
0x180019ad9  mov     [rdx+r8*4], eax
0x180019add  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180019ae2  lea     r14d, [rdi+1]
0x180019ae6  add     si, r14w
0x180019aea  jmp     loc_180019A4E
0x180019aef  lea     r8, [rbp+arg_10]; char **
0x180019af3  movzx   edx, r14w; unsigned __int16
0x180019af7  mov     rcx, rdi; this
0x180019afa  call    ?GetKeyAt@SIdxKeyTable@@QEAAKGPEAPEAD@Z; SIdxKeyTable::GetKeyAt(ushort,char * *)
0x180019aff  mov     esi, eax
0x180019b01  test    eax, eax
0x180019b03  jz      short loc_180019B4D
0x180019b05  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180019b0b  mov     rcx, rax
0x180019b0e  mov     edx, esi
0x180019b10  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180019b16  mov     r10, cs:WPP_GLOBAL_Control
0x180019b1d  lea     rcx, WPP_GLOBAL_Control
0x180019b24  cmp     r10, rcx
0x180019b27  jz      loc_180019945
0x180019b2d  test    byte ptr [r10+1Ch], 1
0x180019b32  jz      loc_180019945
0x180019b38  cmp     byte ptr [r10+19h], 2
0x180019b3d  jb      loc_180019945
0x180019b43  mov     edx, 2Eh ; '.'
0x180019b48  jmp     loc_180019932
0x180019b4d  mov     rax, [rdi+20h]
0x180019b51  movzx   edx, r14w; unsigned __int16
0x180019b55  mov     rcx, rdi; this
0x180019b58  mov     r13d, [rax+r12*4]
0x180019b5c  call    ?RemoveKey@SIdxKeyTable@@QEAAKG@Z; SIdxKeyTable::RemoveKey(ushort)
0x180019b61  mov     esi, eax
0x180019b63  test    eax, eax
0x180019b65  jz      short loc_180019BB8
0x180019b67  mov     rcx, [rbp+arg_10]; void *
0x180019b6b  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180019b70  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180019b76  mov     rcx, rax
0x180019b79  mov     edx, esi
0x180019b7b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180019b81  mov     r10, cs:WPP_GLOBAL_Control
0x180019b88  lea     rcx, WPP_GLOBAL_Control
0x180019b8f  cmp     r10, rcx
0x180019b92  jz      loc_180019945
0x180019b98  test    byte ptr [r10+1Ch], 1
0x180019b9d  jz      loc_180019945
0x180019ba3  cmp     byte ptr [r10+19h], 2
0x180019ba8  jb      loc_180019945
0x180019bae  mov     edx, 2Fh ; '/'
0x180019bb3  jmp     loc_180019932
0x180019bb8  mov     rax, [rdi+28h]
0x180019bbc  lea     r8, [rbp+arg_0]; unsigned __int16 *
0x180019bc0  mov     ecx, dword ptr [rbp+arg_8]
0x180019bc3  mov     rsi, [rbp+arg_10]
0x180019bc7  mov     rdx, rsi; char *
0x180019bca  mov     [rax+r12*4], ecx
0x180019bce  mov     rcx, r15; this
0x180019bd1  call    ?FindKey@SIdxKeyTable@@QEAAKPEADPEAG@Z; SIdxKeyTable::FindKey(char *,ushort *)
0x180019bd6  mov     edi, eax
0x180019bd8  test    eax, eax
0x180019bda  jz      short loc_180019C35
0x180019bdc  cmp     eax, 490h
0x180019be1  jz      short loc_180019C35
0x180019be3  mov     rcx, rsi; void *
0x180019be6  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180019beb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180019bf1  mov     rcx, rax
0x180019bf4  mov     edx, edi
0x180019bf6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180019bfc  mov     rax, cs:WPP_GLOBAL_Control
0x180019c03  lea     rcx, WPP_GLOBAL_Control
0x180019c0a  cmp     rax, rcx
0x180019c0d  jz      loc_180019A2B
0x180019c13  test    byte ptr [rax+1Ch], 1
0x180019c17  jz      loc_180019A2B
0x180019c1d  cmp     byte ptr [rax+19h], 2
0x180019c21  jb      loc_180019A2B
0x180019c27  mov     edx, 30h ; '0'
0x180019c2c  mov     rcx, [rax+10h]
0x180019c30  jmp     loc_180019A1C
0x180019c35  movzx   r8d, [rbp+arg_0]; unsigned __int16
0x180019c3a  mov     r9d, r13d; unsigned int
0x180019c3d  mov     rdx, rsi; char *
0x180019c40  mov     rcx, r15; this
0x180019c43  call    ?AddKey@SIdxKeyTable@@QEAAKPEADGK@Z; SIdxKeyTable::AddKey(char *,ushort,ulong)
0x180019c48  mov     edi, eax
0x180019c4a  mov     rcx, rsi; void *
0x180019c4d  test    eax, eax
0x180019c4f  jz      short loc_180019C9E
0x180019c51  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180019c56  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180019c5c  mov     rcx, rax
0x180019c5f  mov     edx, edi
0x180019c61  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180019c67  mov     r10, cs:WPP_GLOBAL_Control
0x180019c6e  lea     rcx, WPP_GLOBAL_Control
0x180019c75  cmp     r10, rcx
0x180019c78  jz      loc_180019A2B
0x180019c7e  test    byte ptr [r10+1Ch], 1
0x180019c83  jz      loc_180019A2B
0x180019c89  cmp     byte ptr [r10+19h], 2
0x180019c8e  jb      loc_180019A2B
0x180019c94  mov     edx, 31h ; '1'
0x180019c99  jmp     loc_180019A18
0x180019c9e  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180019ca3  mov     r14d, 1
0x180019ca9  mov     r13d, r14d
0x180019cac  jmp     loc_180019A47
0x180019cb1  mov     rcx, r14; void *
0x180019cb4  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180019cb9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180019cbf  mov     rcx, rax
0x180019cc2  mov     edx, edi
0x180019cc4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180019cca  mov     rax, cs:WPP_GLOBAL_Control
0x180019cd1  lea     rcx, WPP_GLOBAL_Control
0x180019cd8  cmp     rax, rcx
0x180019cdb  jz      loc_180019A2B
0x180019ce1  test    byte ptr [rax+1Ch], 1
0x180019ce5  jz      loc_180019A2B
0x180019ceb  cmp     byte ptr [rax+19h], 2
0x180019cef  jb      loc_180019A2B
0x180019cf5  mov     edx, 34h ; '4'
0x180019cfa  jmp     loc_180019C2C
0x180019cff  mov     rcx, r14; void *
0x180019d02  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180019d07  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180019d0d  mov     ebx, 0Bh
0x180019d12  mov     rcx, rax
0x180019d15  mov     edx, ebx
0x180019d17  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180019d1d  mov     r10, cs:WPP_GLOBAL_Control
0x180019d24  lea     rcx, WPP_GLOBAL_Control
0x180019d2b  cmp     r10, rcx
  ... truncated ...
```
