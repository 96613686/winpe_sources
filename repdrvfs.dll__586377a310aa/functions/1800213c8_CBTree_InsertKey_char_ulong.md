# CBTree::InsertKey(char *,ulong)

- ea: `0x1800213c8`
- end: `0x1800216c1`
- name: `?InsertKey@CBTree@@QEAAKPEADK@Z`
- size: `761`
- prototype: `unsigned int __fastcall(CBTree *__hidden this, char *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021250`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180010fe4`
- `0x180012590`
- `0x1800129a0`
- `0x1800213c8`
- `0x180029d4c`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180021495`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180021495`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021571`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800215c6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021657`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800216a4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021571`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800215c6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021657`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800216a4`
- `wbemcomn!GetMemLogObject` at `0x18002142f`
- `wbemcomn!GetMemLogObject` at `0x1800214a3`
- `wbemcomn!GetMemLogObject` at `0x18002152d`
- `wbemcomn!GetMemLogObject` at `0x180021585`
- `wbemcomn!GetMemLogObject` at `0x180021616`
- `wbemcomn!GetMemLogObject` at `0x180021660`
- `wbemcomn!GetMemLogObject` at `0x18002142f`
- `wbemcomn!GetMemLogObject` at `0x1800214a3`
- `wbemcomn!GetMemLogObject` at `0x18002152d`
- `wbemcomn!GetMemLogObject` at `0x180021585`
- `wbemcomn!GetMemLogObject` at `0x180021616`
- `wbemcomn!GetMemLogObject` at `0x180021660`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002143a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800214b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002153d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021590`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021621`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021670`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002143a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800214b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002153d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021590`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021621`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021670`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CBTree::InsertKey(CBTree *this, char *a2, int a3)
{
  unsigned int v5; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v7; // rcx
  __int64 v8; // rdx
  unsigned int *v10; // rax
  unsigned int *v11; // rbx
  CMemoryLog *v12; // rax
  unsigned int inserted; // edi
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  char *v16; // r9
  SIdxKeyTable *v17; // rsi
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  unsigned int v20; // [rsp+20h] [rbp-58h]
  int v21; // [rsp+80h] [rbp+8h] BYREF
  int v22; // [rsp+90h] [rbp+18h] BYREF
  SIdxKeyTable *v23; // [rsp+98h] [rbp+20h] BYREF

  v22 = a3;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids);
  }
  if ( !*((_QWORD *)this + 1) )
  {
    v5 = CBTree::RebuildCacheIfMissing(this);
    if ( v5 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v5);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v5;
      }
      v8 = 106;
LABEL_11:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v5);
      return v5;
    }
  }
  LOWORD(v22) = 0;
  v23 = 0;
  v21 = -1;
  v10 = (unsigned int *)CWin32DefaultArena::WbemMemAlloc(0x1000u);
  v11 = v10;
  if ( !v10 )
  {
    v12 = GetMemLogObject();
    v5 = 8;
    CMemoryLog::Write(v12, 8);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v8 = 107;
    goto LABEL_11;
  }
  if ( a2 && *a2 )
  {
    inserted = CBTree::Search(this, a2, &v23, (unsigned __int16 *)&v22, v10, &v21);
    if ( inserted )
    {
      if ( inserted == 1168 )
      {
        v16 = a2;
        v17 = v23;
        inserted = CBTree::InsertPhase2(this, v23, v22, v16, v20, v11, &v21);
        if ( v17 )
          SIdxKeyTable::Release(v17);
        if ( inserted )
        {
          v18 = GetMemLogObject();
          CMemoryLog::Write(v18, inserted);
        }
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, inserted);
        }
      }
      else
      {
        v15 = GetMemLogObject();
        CMemoryLog::Write(v15, inserted);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, inserted);
        }
      }
    }
    else
    {
      SIdxKeyTable::Release(v23);
      v14 = GetMemLogObject();
      inserted = 183;
      CMemoryLog::Write(v14, 183);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 183);
      }
    }
  }
  else
  {
    v19 = GetMemLogObject();
    inserted = 87;
    CMemoryLog::Write(v19, 87);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 87);
    }
  }
  CWin32DefaultArena::WbemMemFree(v11);
  return inserted;
}

```

## disassembly

```asm
0x1800213c8  mov     [rsp+arg_8], rbx
0x1800213cd  mov     [rsp+arg_10], r8d
0x1800213d2  push    rbp
0x1800213d3  push    rsi
0x1800213d4  push    rdi
0x1800213d5  push    r12
0x1800213d7  push    r13
0x1800213d9  sub     rsp, 50h
0x1800213dd  mov     rsi, rdx
0x1800213e0  mov     rbp, rcx
0x1800213e3  lea     r13, WPP_GLOBAL_Control
0x1800213ea  lea     r12, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x1800213f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213f8  cmp     rcx, r13
0x1800213fb  jz      short loc_18002141A
0x1800213fd  test    byte ptr [rcx+1Ch], 1
0x180021401  jz      short loc_18002141A
0x180021403  cmp     byte ptr [rcx+19h], 5
0x180021407  jb      short loc_18002141A
0x180021409  mov     edx, 69h ; 'i'
0x18002140e  mov     r8, r12
0x180021411  mov     rcx, [rcx+10h]
0x180021415  call    WPP_SF_
0x18002141a  cmp     qword ptr [rbp+8], 0
0x18002141f  jnz     short loc_180021473
0x180021421  mov     rcx, rbp; this
0x180021424  call    ?RebuildCacheIfMissing@CBTree@@AEAAKXZ; CBTree::RebuildCacheIfMissing(void)
0x180021429  mov     ebx, eax
0x18002142b  test    eax, eax
0x18002142d  jz      short loc_180021473
0x18002142f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021435  mov     edx, ebx
0x180021437  mov     rcx, rax
0x18002143a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021440  mov     rcx, cs:WPP_GLOBAL_Control
0x180021447  cmp     rcx, r13
0x18002144a  jz      short loc_18002146C
0x18002144c  test    byte ptr [rcx+1Ch], 1
0x180021450  jz      short loc_18002146C
0x180021452  cmp     byte ptr [rcx+19h], 2
0x180021456  jb      short loc_18002146C
0x180021458  mov     edx, 6Ah ; 'j'
0x18002145d  mov     r9d, ebx
0x180021460  mov     r8, r12
0x180021463  mov     rcx, [rcx+10h]
0x180021467  call    WPP_SF_d
0x18002146c  mov     eax, ebx
0x18002146e  jmp     loc_1800216AD
0x180021473  xor     eax, eax
0x180021475  mov     word ptr [rsp+78h+arg_10], ax
0x18002147d  mov     [rsp+78h+arg_18], rax
0x180021485  mov     [rsp+78h+arg_0], 0FFFFFFFFh
0x180021490  mov     ecx, 1000h
0x180021495  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002149b  mov     rbx, rax
0x18002149e  test    rax, rax
0x1800214a1  jnz     short loc_1800214D6
0x1800214a3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800214a9  mov     ebx, 8
0x1800214ae  mov     edx, ebx
0x1800214b0  mov     rcx, rax
0x1800214b3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800214b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214c0  cmp     rcx, r13
0x1800214c3  jz      short loc_18002146C
0x1800214c5  test    byte ptr [rcx+1Ch], 1
0x1800214c9  jz      short loc_18002146C
0x1800214cb  cmp     byte ptr [rcx+19h], 2
0x1800214cf  jb      short loc_18002146C
0x1800214d1  lea     edx, [rbx+63h]
0x1800214d4  jmp     short loc_18002145D
0x1800214d6  mov     [rsp+78h+var_38], rbx
0x1800214db  test    rsi, rsi
0x1800214de  jz      loc_180021660
0x1800214e4  cmp     byte ptr [rsi], 0
0x1800214e7  jz      loc_180021660
0x1800214ed  lea     rax, [rsp+78h+arg_0]
0x1800214f5  mov     [rsp+78h+var_50], rax; int *
0x1800214fa  mov     [rsp+78h+var_58], rbx; unsigned int
0x1800214ff  lea     r9, [rsp+78h+arg_10]; unsigned __int16 *
0x180021507  lea     r8, [rsp+78h+arg_18]; struct SIdxKeyTable **
0x18002150f  mov     rdx, rsi; char *
0x180021512  mov     rcx, rbp; this
0x180021515  call    ?Search@CBTree@@AEAAKPEADPEAPEAVSIdxKeyTable@@PEAGQEAKAEAJ@Z; CBTree::Search(char *,SIdxKeyTable * *,ushort *,ulong * const,long &)
0x18002151a  mov     edi, eax
0x18002151c  test    eax, eax
0x18002151e  jnz     short loc_18002157D
0x180021520  mov     rcx, [rsp+78h+arg_18]; this
0x180021528  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x18002152d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021533  mov     edi, 0B7h
0x180021538  mov     edx, edi
0x18002153a  mov     rcx, rax
0x18002153d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021543  mov     rcx, cs:WPP_GLOBAL_Control
0x18002154a  cmp     rcx, r13
0x18002154d  jz      short loc_18002156E
0x18002154f  test    byte ptr [rcx+1Ch], 1
0x180021553  jz      short loc_18002156E
0x180021555  cmp     byte ptr [rcx+19h], 2
0x180021559  jb      short loc_18002156E
0x18002155b  lea     edx, [rdi-4Ah]
0x18002155e  mov     r9d, edi
0x180021561  mov     r8, r12
0x180021564  mov     rcx, [rcx+10h]
0x180021568  call    WPP_SF_d
0x18002156d  nop
0x18002156e  mov     rcx, rbx
0x180021571  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180021577  nop
0x180021578  jmp     loc_1800216AB
0x18002157d  cmp     edi, 490h
0x180021583  jz      short loc_1800215D2
0x180021585  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002158b  mov     edx, edi
0x18002158d  mov     rcx, rax
0x180021590  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021596  mov     rcx, cs:WPP_GLOBAL_Control
0x18002159d  cmp     rcx, r13
0x1800215a0  jz      short loc_1800215C3
0x1800215a2  test    byte ptr [rcx+1Ch], 1
0x1800215a6  jz      short loc_1800215C3
0x1800215a8  cmp     byte ptr [rcx+19h], 2
0x1800215ac  jb      short loc_1800215C3
0x1800215ae  mov     edx, 6Eh ; 'n'
0x1800215b3  mov     r9d, edi
0x1800215b6  mov     r8, r12
0x1800215b9  mov     rcx, [rcx+10h]
0x1800215bd  call    WPP_SF_d
0x1800215c2  nop
0x1800215c3  mov     rcx, rbx
0x1800215c6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800215cc  nop
0x1800215cd  jmp     loc_1800216AB
0x1800215d2  lea     rax, [rsp+78h+arg_0]
0x1800215da  mov     [rsp+78h+var_48], rax; int *
0x1800215df  mov     [rsp+78h+var_50], rbx; unsigned int *
0x1800215e4  mov     r9, rsi; char *
0x1800215e7  movzx   r8d, word ptr [rsp+78h+arg_10]; unsigned __int16
0x1800215f0  mov     rsi, [rsp+78h+arg_18]
0x1800215f8  mov     rdx, rsi; struct SIdxKeyTable *
0x1800215fb  mov     rcx, rbp; this
0x1800215fe  call    ?InsertPhase2@CBTree@@AEAAKPEAVSIdxKeyTable@@GPEADKQEAKAEAJ@Z; CBTree::InsertPhase2(SIdxKeyTable *,ushort,char *,ulong,ulong * const,long &)
0x180021603  mov     edi, eax
0x180021605  test    rsi, rsi
0x180021608  jz      short loc_180021612
0x18002160a  mov     rcx, rsi; this
0x18002160d  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x180021612  test    edi, edi
0x180021614  jz      short loc_180021627
0x180021616  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002161c  mov     edx, edi
0x18002161e  mov     rcx, rax
0x180021621  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021627  mov     rcx, cs:WPP_GLOBAL_Control
0x18002162e  cmp     rcx, r13
0x180021631  jz      short loc_180021654
0x180021633  test    byte ptr [rcx+1Ch], 1
0x180021637  jz      short loc_180021654
0x180021639  cmp     byte ptr [rcx+19h], 2
0x18002163d  jb      short loc_180021654
0x18002163f  mov     edx, 6Fh ; 'o'
0x180021644  mov     r9d, edi
0x180021647  mov     r8, r12
0x18002164a  mov     rcx, [rcx+10h]
0x18002164e  call    WPP_SF_d
0x180021653  nop
0x180021654  mov     rcx, rbx
0x180021657  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002165d  nop
0x18002165e  jmp     short loc_1800216AB
0x180021660  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021666  mov     edi, 57h ; 'W'
0x18002166b  mov     edx, edi
0x18002166d  mov     rcx, rax
0x180021670  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021676  mov     rcx, cs:WPP_GLOBAL_Control
0x18002167d  cmp     rcx, r13
0x180021680  jz      short loc_1800216A1
0x180021682  test    byte ptr [rcx+1Ch], 1
0x180021686  jz      short loc_1800216A1
0x180021688  cmp     byte ptr [rcx+19h], 2
0x18002168c  jb      short loc_1800216A1
0x18002168e  lea     edx, [rdi+15h]
0x180021691  mov     r9d, edi
0x180021694  mov     r8, r12
0x180021697  mov     rcx, [rcx+10h]
0x18002169b  call    WPP_SF_d
0x1800216a0  nop
0x1800216a1  mov     rcx, rbx
0x1800216a4  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800216aa  nop
0x1800216ab  mov     eax, edi
0x1800216ad  mov     rbx, [rsp+78h+arg_8]
0x1800216b5  add     rsp, 50h
0x1800216b9  pop     r13
0x1800216bb  pop     r12
0x1800216bd  pop     rdi
0x1800216be  pop     rsi
0x1800216bf  pop     rbp
0x1800216c0  retn
```
