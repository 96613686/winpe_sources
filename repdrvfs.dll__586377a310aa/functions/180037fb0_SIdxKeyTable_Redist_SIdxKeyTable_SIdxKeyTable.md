# SIdxKeyTable::Redist(SIdxKeyTable *,SIdxKeyTable *)

- ea: `0x180037fb0`
- end: `0x180038408`
- name: `?Redist@SIdxKeyTable@@QEAAKPEAV1@0@Z`
- size: `1112`
- prototype: `unsigned int __fastcall(SIdxKeyTable *__hidden this, struct SIdxKeyTable *, struct SIdxKeyTable *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010fe4`

## callees

- `0x1800012b8`
- `0x18000eee0`
- `0x1800109d0`
- `0x180010fa0`
- `0x1800114bc`
- `0x180019e00`
- `0x180037fb0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180037fea`
- `wbemcomn!GetMemLogObject` at `0x1800380d4`
- `wbemcomn!GetMemLogObject` at `0x18003811a`
- `wbemcomn!GetMemLogObject` at `0x18003816b`
- `wbemcomn!GetMemLogObject` at `0x1800381a2`
- `wbemcomn!GetMemLogObject` at `0x180038212`
- `wbemcomn!GetMemLogObject` at `0x180038290`
- `wbemcomn!GetMemLogObject` at `0x1800382f0`
- `wbemcomn!GetMemLogObject` at `0x180038346`
- `wbemcomn!GetMemLogObject` at `0x1800383aa`
- `wbemcomn!GetMemLogObject` at `0x180037fea`
- `wbemcomn!GetMemLogObject` at `0x1800380d4`
- `wbemcomn!GetMemLogObject` at `0x18003811a`
- `wbemcomn!GetMemLogObject` at `0x18003816b`
- `wbemcomn!GetMemLogObject` at `0x1800381a2`
- `wbemcomn!GetMemLogObject` at `0x180038212`
- `wbemcomn!GetMemLogObject` at `0x180038290`
- `wbemcomn!GetMemLogObject` at `0x1800382f0`
- `wbemcomn!GetMemLogObject` at `0x180038346`
- `wbemcomn!GetMemLogObject` at `0x1800383aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037ffa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800380df`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038125`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038176`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800381ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003821d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003829b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800382fb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038351`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800383ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180037ffa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800380df`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038125`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038176`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800381ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003821d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003829b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800382fb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180038351`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800383ba`

## pseudocode

```c
__int64 __fastcall SIdxKeyTable::Redist(SIdxKeyTable *this, struct SIdxKeyTable *a2, struct SIdxKeyTable *a3)
{
  unsigned int v6; // edi
  CMemoryLog *v7; // rax
  unsigned int v8; // ebx
  CVarObjHeap *v9; // rcx
  __int64 v10; // rdx
  unsigned int i; // edi
  unsigned int KeyAt; // esi
  int v13; // r12d
  CMemoryLog *v14; // rax
  CVarObjHeap *v15; // rcx
  __int64 v16; // rdx
  CMemoryLog *v17; // rax
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  unsigned int Key; // edi
  CMemoryLog *v22; // rax
  CVarObjHeap *v23; // rcx
  __int64 v24; // rdx
  int v25; // esi
  CMemoryLog *v26; // rax
  int v27; // r9d
  __int64 v28; // rsi
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned __int16 v32; // [rsp+58h] [rbp+10h] BYREF
  char *v33; // [rsp+68h] [rbp+20h] BYREF

  v32 = 0;
  if ( !a2 || !a3 )
  {
    MemLogObject = GetMemLogObject();
    v8 = 87;
    CMemoryLog::Write(MemLogObject, 87);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v8;
    }
    v10 = 53;
    goto LABEL_64;
  }
  v6 = *((_DWORD *)this + 3);
  if ( v6 >= 3 )
  {
    for ( i = v6 >> 1; ; --i )
    {
      v33 = 0;
      if ( !i )
        break;
      KeyAt = SIdxKeyTable::GetKeyAt(this, 0, &v33);
      if ( KeyAt )
      {
        v19 = GetMemLogObject();
        CMemoryLog::Write(v19, KeyAt);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return KeyAt;
        }
        v16 = 55;
        goto LABEL_33;
      }
      v13 = **((_DWORD **)this + 4);
      KeyAt = SIdxKeyTable::FindKey(a3, v33, &v32);
      if ( KeyAt != 1168 )
      {
        _BtrMemFree(v33);
        if ( KeyAt )
        {
          v18 = GetMemLogObject();
          CMemoryLog::Write(v18, KeyAt);
        }
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return KeyAt;
        }
        v16 = 56;
LABEL_33:
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, KeyAt);
        return KeyAt;
      }
      KeyAt = SIdxKeyTable::AddKey((void **)a3, v33, v32, v13);
      _BtrMemFree(v33);
      if ( KeyAt )
      {
        v17 = GetMemLogObject();
        CMemoryLog::Write(v17, KeyAt);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return KeyAt;
        }
        v16 = 57;
        goto LABEL_33;
      }
      *(_DWORD *)(*((_QWORD *)a3 + 5) + 4LL * v32) = **((_DWORD **)this + 5);
      KeyAt = SIdxKeyTable::RemoveKey(this, 0);
      if ( KeyAt )
      {
        v14 = GetMemLogObject();
        CMemoryLog::Write(v14, KeyAt);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = 58;
          goto LABEL_33;
        }
        return KeyAt;
      }
    }
    *(_DWORD *)(*((_QWORD *)a3 + 5) + 4LL * *((unsigned __int16 *)a3 + 6)) = **((_DWORD **)this + 5);
    Key = SIdxKeyTable::GetKeyAt(this, 0, &v33);
    if ( Key )
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, Key);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return Key;
      }
      v24 = 59;
    }
    else
    {
      v25 = **((_DWORD **)this + 4);
      Key = SIdxKeyTable::FindKey(a2, v33, &v32);
      if ( Key == 1168 )
      {
        v27 = v25;
        v28 = v32;
        Key = SIdxKeyTable::AddKey((void **)a2, v33, v32, v27);
        _BtrMemFree(v33);
        if ( Key )
        {
          v29 = GetMemLogObject();
          CMemoryLog::Write(v29, Key);
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return Key;
          }
          v24 = 61;
        }
        else
        {
          Key = SIdxKeyTable::RemoveKey(this, 0);
          if ( !Key )
          {
            *(_DWORD *)(*((_QWORD *)a2 + 5) + 4 * v28) = *((_DWORD *)a3 + 1);
            *(_DWORD *)(*((_QWORD *)a2 + 5) + 4LL * (unsigned __int16)(v28 + 1)) = *((_DWORD *)this + 1);
            return 0;
          }
          v30 = GetMemLogObject();
          CMemoryLog::Write(v30, Key);
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return Key;
          }
          v24 = 62;
        }
      }
      else
      {
        _BtrMemFree(v33);
        if ( Key )
        {
          v26 = GetMemLogObject();
          CMemoryLog::Write(v26, Key);
        }
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return Key;
        }
        v24 = 60;
      }
    }
    WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, Key);
    return Key;
  }
  v7 = GetMemLogObject();
  v8 = 13;
  CMemoryLog::Write(v7, 13);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return v8;
  }
  v10 = 54;
LABEL_64:
  WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180037fb0  mov     [rsp+arg_0], rbx
0x180037fb5  push    rbp
0x180037fb6  push    rsi
0x180037fb7  push    rdi
0x180037fb8  push    r12
0x180037fba  push    r15
0x180037fbc  sub     rsp, 20h
0x180037fc0  xor     eax, eax
0x180037fc2  mov     rbp, r8
0x180037fc5  mov     [rsp+48h+arg_8], ax
0x180037fca  mov     r15, rdx
0x180037fcd  mov     rbx, rcx
0x180037fd0  test    rdx, rdx
0x180037fd3  jz      loc_1800383AA
0x180037fd9  test    r8, r8
0x180037fdc  jz      loc_1800383AA
0x180037fe2  mov     edi, [rcx+0Ch]
0x180037fe5  cmp     edi, 3
0x180037fe8  jnb     short loc_180038033
0x180037fea  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037ff0  mov     ebx, 0Dh
0x180037ff5  mov     rcx, rax
0x180037ff8  mov     edx, ebx
0x180037ffa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180038000  mov     rcx, cs:WPP_GLOBAL_Control
0x180038007  lea     rax, WPP_GLOBAL_Control
0x18003800e  cmp     rcx, rax
0x180038011  jz      loc_1800383F5
0x180038017  test    byte ptr [rcx+1Ch], 1
0x18003801b  jz      loc_1800383F5
0x180038021  cmp     byte ptr [rcx+19h], 2
0x180038025  jb      loc_1800383F5
0x18003802b  lea     edx, [rbx+29h]
0x18003802e  jmp     loc_1800383E2
0x180038033  shr     edi, 1
0x180038035  mov     [rsp+48h+arg_18], 0
0x18003803e  lea     r8, [rsp+48h+arg_18]; char **
0x180038043  test    edi, edi
0x180038045  jz      loc_1800381F1
0x18003804b  xor     edx, edx; unsigned __int16
0x18003804d  mov     rcx, rbx; this
0x180038050  call    ?GetKeyAt@SIdxKeyTable@@QEAAKGPEAPEAD@Z; SIdxKeyTable::GetKeyAt(ushort,char * *)
0x180038055  mov     esi, eax
0x180038057  test    eax, eax
0x180038059  jnz     loc_1800381A2
0x18003805f  mov     rax, [rbx+20h]
0x180038063  lea     r8, [rsp+48h+arg_8]; unsigned __int16 *
0x180038068  mov     rdx, [rsp+48h+arg_18]; char *
0x18003806d  mov     rcx, rbp; this
0x180038070  mov     r12d, [rax]
0x180038073  call    ?FindKey@SIdxKeyTable@@QEAAKPEADPEAG@Z; SIdxKeyTable::FindKey(char *,ushort *)
0x180038078  mov     esi, eax
0x18003807a  cmp     eax, 490h
0x18003807f  jnz     loc_18003815D
0x180038085  movzx   r8d, [rsp+48h+arg_8]; unsigned __int16
0x18003808b  mov     r9d, r12d; unsigned int
0x18003808e  mov     rdx, [rsp+48h+arg_18]; char *
0x180038093  mov     rcx, rbp; this
0x180038096  call    ?AddKey@SIdxKeyTable@@QEAAKPEADGK@Z; SIdxKeyTable::AddKey(char *,ushort,ulong)
0x18003809b  mov     rcx, [rsp+48h+arg_18]; void *
0x1800380a0  mov     esi, eax
0x1800380a2  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x1800380a7  test    esi, esi
0x1800380a9  jnz     short loc_18003811A
0x1800380ab  mov     rax, [rbx+28h]
0x1800380af  movzx   edx, [rsp+48h+arg_8]
0x1800380b4  mov     rcx, [rbp+28h]
0x1800380b8  mov     eax, [rax]
0x1800380ba  mov     [rcx+rdx*4], eax
0x1800380bd  xor     edx, edx; unsigned __int16
0x1800380bf  mov     rcx, rbx; this
0x1800380c2  call    ?RemoveKey@SIdxKeyTable@@QEAAKG@Z; SIdxKeyTable::RemoveKey(ushort)
0x1800380c7  mov     esi, eax
0x1800380c9  test    eax, eax
0x1800380cb  jnz     short loc_1800380D4
0x1800380cd  dec     edi
0x1800380cf  jmp     loc_180038035
0x1800380d4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800380da  mov     rcx, rax
0x1800380dd  mov     edx, esi
0x1800380df  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800380e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380ec  lea     rax, WPP_GLOBAL_Control
0x1800380f3  cmp     rcx, rax
0x1800380f6  jz      loc_1800381EA
0x1800380fc  test    byte ptr [rcx+1Ch], 1
0x180038100  jz      loc_1800381EA
0x180038106  cmp     byte ptr [rcx+19h], 2
0x18003810a  jb      loc_1800381EA
0x180038110  mov     edx, 3Ah ; ':'
0x180038115  jmp     loc_1800381D7
0x18003811a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180038120  mov     rcx, rax
0x180038123  mov     edx, esi
0x180038125  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003812b  mov     rcx, cs:WPP_GLOBAL_Control
0x180038132  lea     rax, WPP_GLOBAL_Control
0x180038139  cmp     rcx, rax
0x18003813c  jz      loc_1800381EA
0x180038142  test    byte ptr [rcx+1Ch], 1
0x180038146  jz      loc_1800381EA
0x18003814c  cmp     byte ptr [rcx+19h], 2
0x180038150  jb      loc_1800381EA
0x180038156  mov     edx, 39h ; '9'
0x18003815b  jmp     short loc_1800381D7
0x18003815d  mov     rcx, [rsp+48h+arg_18]; void *
0x180038162  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180038167  test    esi, esi
0x180038169  jz      short loc_18003817C
0x18003816b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180038171  mov     rcx, rax
0x180038174  mov     edx, esi
0x180038176  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003817c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038183  lea     rax, WPP_GLOBAL_Control
0x18003818a  cmp     rcx, rax
0x18003818d  jz      short loc_1800381EA
0x18003818f  test    byte ptr [rcx+1Ch], 1
0x180038193  jz      short loc_1800381EA
0x180038195  cmp     byte ptr [rcx+19h], 2
0x180038199  jb      short loc_1800381EA
0x18003819b  mov     edx, 38h ; '8'
0x1800381a0  jmp     short loc_1800381D7
0x1800381a2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800381a8  mov     rcx, rax
0x1800381ab  mov     edx, esi
0x1800381ad  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800381b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800381ba  lea     rax, WPP_GLOBAL_Control
0x1800381c1  cmp     rcx, rax
0x1800381c4  jz      short loc_1800381EA
0x1800381c6  test    byte ptr [rcx+1Ch], 1
0x1800381ca  jz      short loc_1800381EA
0x1800381cc  cmp     byte ptr [rcx+19h], 2
0x1800381d0  jb      short loc_1800381EA
0x1800381d2  mov     edx, 37h ; '7'
0x1800381d7  mov     rcx, [rcx+10h]
0x1800381db  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x1800381e2  mov     r9d, esi
0x1800381e5  call    WPP_SF_d
0x1800381ea  mov     eax, esi
0x1800381ec  jmp     loc_1800383F7
0x1800381f1  mov     rax, [rbx+28h]
0x1800381f5  movzx   edx, word ptr [rbp+0Ch]
0x1800381f9  mov     rcx, [rbp+28h]
0x1800381fd  mov     eax, [rax]
0x1800381ff  mov     [rcx+rdx*4], eax
0x180038202  xor     edx, edx; unsigned __int16
0x180038204  mov     rcx, rbx; this
0x180038207  call    ?GetKeyAt@SIdxKeyTable@@QEAAKGPEAPEAD@Z; SIdxKeyTable::GetKeyAt(ushort,char * *)
0x18003820c  mov     edi, eax
0x18003820e  test    eax, eax
0x180038210  jz      short loc_180038261
0x180038212  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180038218  mov     rcx, rax
0x18003821b  mov     edx, edi
0x18003821d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180038223  mov     rcx, cs:WPP_GLOBAL_Control
0x18003822a  lea     rax, WPP_GLOBAL_Control
0x180038231  cmp     rcx, rax
0x180038234  jz      short loc_18003825A
0x180038236  test    byte ptr [rcx+1Ch], 1
0x18003823a  jz      short loc_18003825A
0x18003823c  cmp     byte ptr [rcx+19h], 2
0x180038240  jb      short loc_18003825A
0x180038242  mov     edx, 3Bh ; ';'
0x180038247  mov     rcx, [rcx+10h]
0x18003824b  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180038252  mov     r9d, edi
0x180038255  call    WPP_SF_d
0x18003825a  mov     eax, edi
0x18003825c  jmp     loc_1800383F7
0x180038261  mov     rax, [rbx+20h]
0x180038265  lea     r8, [rsp+48h+arg_8]; unsigned __int16 *
0x18003826a  mov     rdx, [rsp+48h+arg_18]; char *
0x18003826f  mov     rcx, r15; this
0x180038272  mov     esi, [rax]
0x180038274  call    ?FindKey@SIdxKeyTable@@QEAAKPEADPEAG@Z; SIdxKeyTable::FindKey(char *,ushort *)
0x180038279  mov     edi, eax
0x18003827b  cmp     eax, 490h
0x180038280  jz      short loc_1800382C7
0x180038282  mov     rcx, [rsp+48h+arg_18]; void *
0x180038287  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18003828c  test    edi, edi
0x18003828e  jz      short loc_1800382A1
0x180038290  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180038296  mov     rcx, rax
0x180038299  mov     edx, edi
0x18003829b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800382a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382a8  lea     rax, WPP_GLOBAL_Control
0x1800382af  cmp     rcx, rax
0x1800382b2  jz      short loc_18003825A
0x1800382b4  test    byte ptr [rcx+1Ch], 1
0x1800382b8  jz      short loc_18003825A
0x1800382ba  cmp     byte ptr [rcx+19h], 2
0x1800382be  jb      short loc_18003825A
0x1800382c0  mov     edx, 3Ch ; '<'
0x1800382c5  jmp     short loc_180038247
0x1800382c7  mov     rdx, [rsp+48h+arg_18]; char *
0x1800382cc  mov     r9d, esi; unsigned int
0x1800382cf  movzx   esi, [rsp+48h+arg_8]
0x1800382d4  mov     rcx, r15; this
0x1800382d7  movzx   r8d, si; unsigned __int16
0x1800382db  call    ?AddKey@SIdxKeyTable@@QEAAKPEADGK@Z; SIdxKeyTable::AddKey(char *,ushort,ulong)
0x1800382e0  mov     rcx, [rsp+48h+arg_18]; void *
0x1800382e5  mov     edi, eax
0x1800382e7  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x1800382ec  test    edi, edi
0x1800382ee  jz      short loc_180038336
0x1800382f0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800382f6  mov     rcx, rax
0x1800382f9  mov     edx, edi
0x1800382fb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180038301  mov     rcx, cs:WPP_GLOBAL_Control
0x180038308  lea     rax, WPP_GLOBAL_Control
0x18003830f  cmp     rcx, rax
0x180038312  jz      loc_18003825A
0x180038318  test    byte ptr [rcx+1Ch], 1
0x18003831c  jz      loc_18003825A
0x180038322  cmp     byte ptr [rcx+19h], 2
0x180038326  jb      loc_18003825A
0x18003832c  mov     edx, 3Dh ; '='
0x180038331  jmp     loc_180038247
0x180038336  xor     edx, edx; unsigned __int16
0x180038338  mov     rcx, rbx; this
0x18003833b  call    ?RemoveKey@SIdxKeyTable@@QEAAKG@Z; SIdxKeyTable::RemoveKey(ushort)
0x180038340  mov     edi, eax
0x180038342  test    eax, eax
0x180038344  jz      short loc_18003838C
0x180038346  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003834c  mov     rcx, rax
0x18003834f  mov     edx, edi
0x180038351  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180038357  mov     rcx, cs:WPP_GLOBAL_Control
0x18003835e  lea     rax, WPP_GLOBAL_Control
0x180038365  cmp     rcx, rax
0x180038368  jz      loc_18003825A
0x18003836e  test    byte ptr [rcx+1Ch], 1
0x180038372  jz      loc_18003825A
0x180038378  cmp     byte ptr [rcx+19h], 2
0x18003837c  jb      loc_18003825A
0x180038382  mov     edx, 3Eh ; '>'
0x180038387  jmp     loc_180038247
0x18003838c  mov     rcx, [r15+28h]
0x180038390  mov     eax, [rbp+4]
0x180038393  mov     [rcx+rsi*4], eax
0x180038396  inc     si
0x180038399  mov     eax, [rbx+4]
0x18003839c  mov     rcx, [r15+28h]
0x1800383a0  movzx   edx, si
0x1800383a3  mov     [rcx+rdx*4], eax
0x1800383a6  xor     eax, eax
0x1800383a8  jmp     short loc_1800383F7
0x1800383aa  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800383b0  mov     ebx, 57h ; 'W'
0x1800383b5  mov     rcx, rax
0x1800383b8  mov     edx, ebx
0x1800383ba  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800383c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383c7  lea     rax, WPP_GLOBAL_Control
0x1800383ce  cmp     rcx, rax
0x1800383d1  jz      short loc_1800383F5
0x1800383d3  test    byte ptr [rcx+1Ch], 1
0x1800383d7  jz      short loc_1800383F5
0x1800383d9  cmp     byte ptr [rcx+19h], 2
0x1800383dd  jb      short loc_1800383F5
0x1800383df  lea     edx, [rbx-22h]
0x1800383e2  mov     rcx, [rcx+10h]
0x1800383e6  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x1800383ed  mov     r9d, ebx
0x1800383f0  call    WPP_SF_d
0x1800383f5  mov     eax, ebx
0x1800383f7  mov     rbx, [rsp+48h+arg_0]
0x1800383fc  add     rsp, 20h
0x180038400  pop     r15
0x180038402  pop     r12
0x180038404  pop     rdi
0x180038405  pop     rsi
0x180038406  pop     rbp
0x180038407  retn
```
