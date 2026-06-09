# CSnapinThreadTable::UnregisterAllSnapinInstanceThreads(int)

- ea: `0x18000f8dc`
- end: `0x18000f9d2`
- name: `?UnregisterAllSnapinInstanceThreads@CSnapinThreadTable@@QEAAJH@Z`
- size: `246`
- prototype: `__int64 __fastcall(CSnapinThreadTable *__hidden this, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000e360`

## callees

- `0x18000585c`
- `0x180008224`
- `0x18000b980`
- `0x18000f680`
- `0x18000f8dc`
- `0x18000fbd4`
- `0x18000fc04`
- `0x180019c50`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18000f953`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18000f953`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSnapinThreadTable::UnregisterAllSnapinInstanceThreads(CSnapinThreadTable *this, int a2)
{
  LKRhash::CLKRLinearHashTable *v3; // rdi
  unsigned int v4; // ebp
  volatile __int32 *v5; // rsi
  __int64 v6; // rcx
  _DWORD *v7; // rbx
  _BYTE v9[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v10; // [rsp+38h] [rbp-50h]
  __int16 v11; // [rsp+44h] [rbp-44h]
  _BYTE v12[8]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v13; // [rsp+50h] [rbp-38h]
  __int16 v14; // [rsp+5Ch] [rbp-2Ch]

  v3 = BookKeeping::s_pSnapinThreadTable;
  v4 = 0;
  v5 = (volatile __int32 *)((char *)BookKeeping::s_pSnapinThreadTable + 176);
  CSmallSpinLock::WriteLock((LKRhash::CLKRLinearHashTable *)((char *)BookKeeping::s_pSnapinThreadTable + 176));
  LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::begin(v3, v9);
  LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::end(v6, v12);
  while ( v10 != v13 || v11 != v14 )
  {
    v7 = *(_DWORD **)(v10 + 8LL * v11 + 24);
    if ( v7[1] == a2 )
    {
      if ( !LKRhash::CLKRLinearHashTable::Erase(v3, (struct LKRhash::CLKRLinearHashTable_Iterator *)v9) )
      {
        v4 = -2147023537;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          WPP_SF_dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            35,
            WPP_8949107765ef31f55290197bfd8c288d_Traceguids,
            (unsigned int)v7[2],
            a2);
        break;
      }
      operator delete(v7);
    }
    else
    {
      LKRhash::CLKRLinearHashTable_Iterator::Increment((LKRhash::CLKRLinearHashTable_Iterator *)v9);
    }
  }
  LKRhash::CLKRLinearHashTable_Iterator::_AddRef((LKRhash::CLKRLinearHashTable_Iterator *)v12, -1);
  LKRhash::CLKRLinearHashTable_Iterator::_AddRef((LKRhash::CLKRLinearHashTable_Iterator *)v9, -1);
  _InterlockedExchange(v5, 0);
  return v4;
}

```

## disassembly

```asm
0x18000f8dc  push    rbx
0x18000f8de  push    rbp
0x18000f8df  push    rsi
0x18000f8e0  push    rdi
0x18000f8e1  push    r14
0x18000f8e3  sub     rsp, 60h
0x18000f8e7  mov     r14d, edx
0x18000f8ea  mov     rdi, cs:?s_pSnapinThreadTable@BookKeeping@@0PEAVCSnapinThreadTable@@EA; CSnapinThreadTable * BookKeeping::s_pSnapinThreadTable
0x18000f8f1  xor     ebp, ebp
0x18000f8f3  lea     rsi, [rdi+0B0h]
0x18000f8fa  mov     rcx, rsi; this
0x18000f8fd  call    ?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x18000f902  lea     rdx, [rsp+88h+var_58]
0x18000f907  mov     rcx, rdi
0x18000f90a  call    ?begin@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@QEAA?AViterator@12@XZ; LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::begin(void)
0x18000f90f  nop
0x18000f910  lea     rdx, [rsp+88h+var_40]
0x18000f915  call    ?end@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@QEAA?AViterator@12@XZ; LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::end(void)
0x18000f91a  nop
0x18000f91b  movsx   rax, [rsp+88h+var_44]
0x18000f921  mov     rbx, [rsp+88h+var_50]
0x18000f926  cmp     rbx, [rsp+88h+var_38]
0x18000f92b  jnz     short loc_18000F934
0x18000f92d  cmp     ax, [rsp+88h+var_2C]
0x18000f932  jz      short loc_18000F9A4
0x18000f934  mov     rbx, [rbx+rax*8+18h]
0x18000f939  cmp     [rbx+4], r14d
0x18000f93d  jnz     short loc_18000F95B
0x18000f93f  lea     rdx, [rsp+88h+var_58]; struct LKRhash::CLKRLinearHashTable_Iterator *
0x18000f944  mov     rcx, rdi; this
0x18000f947  call    ?Erase@CLKRLinearHashTable@LKRhash@@QEAA_NAEAVCLKRLinearHashTable_Iterator@2@@Z; LKRhash::CLKRLinearHashTable::Erase(LKRhash::CLKRLinearHashTable_Iterator &)
0x18000f94c  test    al, al
0x18000f94e  jz      short loc_18000F967
0x18000f950  mov     rcx, rbx
0x18000f953  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f959  jmp     short loc_18000F91B
0x18000f95b  lea     rcx, [rsp+88h+var_58]; this
0x18000f960  call    ?Increment@CLKRLinearHashTable_Iterator@LKRhash@@QEAA_NXZ; LKRhash::CLKRLinearHashTable_Iterator::Increment(void)
0x18000f965  jmp     short loc_18000F91B
0x18000f967  mov     ebp, 8007054Fh
0x18000f96c  lea     rax, WPP_GLOBAL_Control
0x18000f973  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f97a  cmp     rcx, rax
0x18000f97d  jz      short loc_18000F9A4
0x18000f97f  cmp     byte ptr [rcx+19h], 2
0x18000f983  jb      short loc_18000F9A4
0x18000f985  mov     edx, 23h ; '#'
0x18000f98a  mov     [rsp+88h+var_68], r14d
0x18000f98f  mov     r9d, [rbx+8]
0x18000f993  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f99a  mov     rcx, [rcx+10h]
0x18000f99e  call    WPP_SF_dd
0x18000f9a3  nop
0x18000f9a4  or      ebx, 0FFFFFFFFh
0x18000f9a7  mov     edx, ebx; int
0x18000f9a9  lea     rcx, [rsp+88h+var_40]; this
0x18000f9ae  call    ?_AddRef@CLKRLinearHashTable_Iterator@LKRhash@@IEBAXH@Z; LKRhash::CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000f9b3  nop
0x18000f9b4  mov     edx, ebx; int
0x18000f9b6  lea     rcx, [rsp+88h+var_58]; this
0x18000f9bb  call    ?_AddRef@CLKRLinearHashTable_Iterator@LKRhash@@IEBAXH@Z; LKRhash::CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000f9c0  nop
0x18000f9c1  xor     ecx, ecx
0x18000f9c3  xchg    ecx, [rsi]
0x18000f9c5  mov     eax, ebp
0x18000f9c7  add     rsp, 60h
0x18000f9cb  pop     r14
0x18000f9cd  pop     rdi
0x18000f9ce  pop     rsi
0x18000f9cf  pop     rbp
0x18000f9d0  pop     rbx
0x18000f9d1  retn
```
