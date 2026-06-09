# CSnapinThreadTable::Dump(BookKeepingXml &)

- ea: `0x18000f02c`
- end: `0x18000f184`
- name: `?Dump@CSnapinThreadTable@@QEAAJAEAVBookKeepingXml@@@Z`
- size: `344`
- prototype: `int(CSnapinThreadTable *__hidden this, struct BookKeepingXml *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000d370`

## callees

- `0x180008224`
- `0x180008630`
- `0x18000c64c`
- `0x18000cb94`
- `0x18000f02c`
- `0x18000f680`
- `0x18000fbd4`
- `0x18000fc04`
- `0x18000fc44`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSnapinThreadTable::Dump(CSnapinThreadTable *this, struct BookKeepingXml *a2)
{
  LKRhash::CLKRLinearHashTable *v3; // rdi
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rcx
  int v7; // eax
  int v8; // eax
  unsigned int v9; // esi
  _BYTE v11[8]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v12; // [rsp+28h] [rbp-30h]
  __int16 v13; // [rsp+34h] [rbp-24h]
  _BYTE v14[8]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v15; // [rsp+40h] [rbp-18h]
  __int16 v16; // [rsp+4Ch] [rbp-Ch]

  v3 = BookKeeping::s_pSnapinThreadTable;
  v4 = BookKeepingXml::OpenTable(a2, 2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::begin(
      v3,
      v11);
    LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::end(v6, v14);
    while ( v12 != v15 || v13 != v16 )
    {
      v7 = CSnapinThread::Dump(*(CSnapinThread **)(v12 + 8LL * v13 + 24), a2);
      v5 = v7;
      if ( v7 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            41,
            WPP_8949107765ef31f55290197bfd8c288d_Traceguids,
            (unsigned int)v7);
        break;
      }
      LKRhash::CLKRLinearHashTable_Iterator::Increment((LKRhash::CLKRLinearHashTable_Iterator *)v11);
    }
    LKRhash::CLKRLinearHashTable_Iterator::_AddRef((LKRhash::CLKRLinearHashTable_Iterator *)v14, -1);
    LKRhash::CLKRLinearHashTable_Iterator::_AddRef((LKRhash::CLKRLinearHashTable_Iterator *)v11, -1);
    v8 = BookKeepingXml::CloseTable(a2);
    v9 = v8;
    if ( v8 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        42,
        WPP_8949107765ef31f55290197bfd8c288d_Traceguids,
        (unsigned int)v8);
    if ( v5 >= 0 )
      return v9;
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      40,
      WPP_8949107765ef31f55290197bfd8c288d_Traceguids,
      (unsigned int)v4);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f02c  mov     [rsp+arg_0], rbx
0x18000f031  mov     [rsp+arg_8], rsi
0x18000f036  push    rdi
0x18000f037  sub     rsp, 50h
0x18000f03b  mov     rsi, rdx
0x18000f03e  mov     rdi, cs:?s_pSnapinThreadTable@BookKeeping@@0PEAVCSnapinThreadTable@@EA; CSnapinThreadTable * BookKeeping::s_pSnapinThreadTable
0x18000f045  mov     edx, 2
0x18000f04a  mov     rcx, rsi
0x18000f04d  call    ?OpenTable@BookKeepingXml@@QEAAJW4_XmlNameId@1@@Z; BookKeepingXml::OpenTable(BookKeepingXml::_XmlNameId)
0x18000f052  mov     ebx, eax
0x18000f054  test    eax, eax
0x18000f056  jns     short loc_18000F096
0x18000f058  lea     rdi, WPP_GLOBAL_Control
0x18000f05f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f066  cmp     rcx, rdi
0x18000f069  jz      loc_18000F172
0x18000f06f  cmp     byte ptr [rcx+19h], 2
0x18000f073  jb      loc_18000F172
0x18000f079  mov     edx, 28h ; '('
0x18000f07e  mov     r9d, eax
0x18000f081  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f088  mov     rcx, [rcx+10h]
0x18000f08c  call    WPP_SF_d
0x18000f091  jmp     loc_18000F172
0x18000f096  lea     rdx, [rsp+58h+var_38]
0x18000f09b  mov     rcx, rdi
0x18000f09e  call    ?begin@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@QEAA?AViterator@12@XZ; LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::begin(void)
0x18000f0a3  nop
0x18000f0a4  lea     rdx, [rsp+58h+var_20]
0x18000f0a9  call    ?end@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@QEAA?AViterator@12@XZ; LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::end(void)
0x18000f0ae  nop
0x18000f0af  lea     rdi, WPP_GLOBAL_Control
0x18000f0b6  movsx   rax, [rsp+58h+var_24]
0x18000f0bc  mov     r8, [rsp+58h+var_30]
0x18000f0c1  cmp     r8, [rsp+58h+var_18]
0x18000f0c6  jnz     short loc_18000F0CF
0x18000f0c8  cmp     ax, [rsp+58h+var_C]
0x18000f0cd  jz      short loc_18000F119
0x18000f0cf  mov     rdx, rsi; struct BookKeepingXml *
0x18000f0d2  mov     rcx, [r8+rax*8+18h]; this
0x18000f0d7  call    ?Dump@CSnapinThread@@QEBAJAEAVBookKeepingXml@@@Z; CSnapinThread::Dump(BookKeepingXml &)
0x18000f0dc  mov     ebx, eax
0x18000f0de  test    eax, eax
0x18000f0e0  js      short loc_18000F0EE
0x18000f0e2  lea     rcx, [rsp+58h+var_38]; this
0x18000f0e7  call    ?Increment@CLKRLinearHashTable_Iterator@LKRhash@@QEAA_NXZ; LKRhash::CLKRLinearHashTable_Iterator::Increment(void)
0x18000f0ec  jmp     short loc_18000F0AF
0x18000f0ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0f5  cmp     rcx, rdi
0x18000f0f8  jz      short loc_18000F119
0x18000f0fa  cmp     byte ptr [rcx+19h], 2
0x18000f0fe  jb      short loc_18000F119
0x18000f100  mov     edx, 29h ; ')'
0x18000f105  mov     r9d, eax
0x18000f108  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f10f  mov     rcx, [rcx+10h]
0x18000f113  call    WPP_SF_d
0x18000f118  nop
0x18000f119  or      edx, 0FFFFFFFFh; int
0x18000f11c  lea     rcx, [rsp+58h+var_20]; this
0x18000f121  call    ?_AddRef@CLKRLinearHashTable_Iterator@LKRhash@@IEBAXH@Z; LKRhash::CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000f126  nop
0x18000f127  or      edx, 0FFFFFFFFh; int
0x18000f12a  lea     rcx, [rsp+58h+var_38]; this
0x18000f12f  call    ?_AddRef@CLKRLinearHashTable_Iterator@LKRhash@@IEBAXH@Z; LKRhash::CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000f134  nop
0x18000f135  mov     rcx, rsi; this
0x18000f138  call    ?CloseTable@BookKeepingXml@@QEAAJXZ; BookKeepingXml::CloseTable(void)
0x18000f13d  mov     esi, eax
0x18000f13f  test    eax, eax
0x18000f141  jns     short loc_18000F16D
0x18000f143  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f14a  cmp     rcx, rdi
0x18000f14d  jz      short loc_18000F16D
0x18000f14f  cmp     byte ptr [rcx+19h], 2
0x18000f153  jb      short loc_18000F16D
0x18000f155  mov     edx, 2Ah ; '*'
0x18000f15a  mov     r9d, eax
0x18000f15d  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f164  mov     rcx, [rcx+10h]
0x18000f168  call    WPP_SF_d
0x18000f16d  test    ebx, ebx
0x18000f16f  cmovns  ebx, esi
0x18000f172  mov     eax, ebx
0x18000f174  mov     rbx, [rsp+58h+arg_0]
0x18000f179  mov     rsi, [rsp+58h+arg_8]
0x18000f17e  add     rsp, 50h
0x18000f182  pop     rdi
0x18000f183  retn
```
