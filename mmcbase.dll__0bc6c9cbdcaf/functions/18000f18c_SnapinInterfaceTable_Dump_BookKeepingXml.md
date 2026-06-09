# SnapinInterfaceTable::Dump(BookKeepingXml &)

- ea: `0x18000f18c`
- end: `0x18000f2f6`
- name: `?Dump@SnapinInterfaceTable@@QEAAJAEAVBookKeepingXml@@@Z`
- size: `362`
- prototype: `int(SnapinInterfaceTable *__hidden this, struct BookKeepingXml *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000d370`

## callees

- `0x18000813c`
- `0x180008224`
- `0x180008630`
- `0x18000c64c`
- `0x18000cb94`
- `0x18000ed28`
- `0x18000f18c`
- `0x18000f680`
- `0x18000fdcc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SnapinInterfaceTable::Dump(SnapinInterfaceTable *this, struct BookKeepingXml *a2)
{
  struct SnapinInterfaceTable *v3; // rdi
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  unsigned int v9; // esi
  __int128 v11; // [rsp+20h] [rbp-58h] BYREF
  int v12; // [rsp+30h] [rbp-48h]
  __int16 v13; // [rsp+34h] [rbp-44h]
  _BYTE v14[8]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v15; // [rsp+40h] [rbp-38h]
  __int16 v16; // [rsp+4Ch] [rbp-2Ch]
  _BYTE v17[8]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v18; // [rsp+58h] [rbp-20h]
  __int16 v19; // [rsp+64h] [rbp-14h]

  v3 = BookKeeping::s_pInterfaceTable;
  v4 = BookKeepingXml::OpenTable(a2, 1);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = LKRhash::CLKRLinearHashTable::Begin(v3, &v11);
    LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::iterator::iterator(
      v14,
      v6);
    v11 = 0;
    v12 = 0;
    v13 = 0;
    LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::iterator::iterator(
      v17,
      &v11);
    while ( v15 != v18 || v16 != v19 )
    {
      v7 = InterfaceRecord::Dump(*(InterfaceRecord **)(v15 + 8LL * v16 + 24), a2);
      v5 = v7;
      if ( v7 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            14,
            WPP_8949107765ef31f55290197bfd8c288d_Traceguids,
            (unsigned int)v7);
        break;
      }
      LKRhash::CLKRLinearHashTable_Iterator::Increment((LKRhash::CLKRLinearHashTable_Iterator *)v14);
    }
    LKRhash::CLKRLinearHashTable_Iterator::_AddRef((LKRhash::CLKRLinearHashTable_Iterator *)v17, -1);
    LKRhash::CLKRLinearHashTable_Iterator::_AddRef((LKRhash::CLKRLinearHashTable_Iterator *)v14, -1);
    v8 = BookKeepingXml::CloseTable(a2);
    v9 = v8;
    if ( v8 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        15,
        WPP_8949107765ef31f55290197bfd8c288d_Traceguids,
        (unsigned int)v8);
    if ( v5 >= 0 )
      return v9;
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      13,
      WPP_8949107765ef31f55290197bfd8c288d_Traceguids,
      (unsigned int)v4);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f18c  push    rbp
0x18000f18e  push    rbx
0x18000f18f  push    rsi
0x18000f190  push    rdi
0x18000f191  mov     rbp, rsp
0x18000f194  sub     rsp, 78h
0x18000f198  mov     rsi, rdx
0x18000f19b  mov     rdi, cs:?s_pInterfaceTable@BookKeeping@@0PEAVSnapinInterfaceTable@@EA; SnapinInterfaceTable * BookKeeping::s_pInterfaceTable
0x18000f1a2  mov     edx, 1
0x18000f1a7  mov     rcx, rsi
0x18000f1aa  call    ?OpenTable@BookKeepingXml@@QEAAJW4_XmlNameId@1@@Z; BookKeepingXml::OpenTable(BookKeepingXml::_XmlNameId)
0x18000f1af  mov     ebx, eax
0x18000f1b1  test    eax, eax
0x18000f1b3  jns     short loc_18000F1F3
0x18000f1b5  lea     rdi, WPP_GLOBAL_Control
0x18000f1bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1c3  cmp     rcx, rdi
0x18000f1c6  jz      loc_18000F2EB
0x18000f1cc  cmp     byte ptr [rcx+19h], 2
0x18000f1d0  jb      loc_18000F2EB
0x18000f1d6  mov     edx, 0Dh
0x18000f1db  mov     r9d, eax
0x18000f1de  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f1e5  mov     rcx, [rcx+10h]
0x18000f1e9  call    WPP_SF_d
0x18000f1ee  jmp     loc_18000F2EB
0x18000f1f3  lea     rdx, [rbp+var_58]
0x18000f1f7  mov     rcx, rdi
0x18000f1fa  call    ?Begin@CLKRLinearHashTable@LKRhash@@QEAA?AVCLKRLinearHashTable_Iterator@2@XZ; LKRhash::CLKRLinearHashTable::Begin(void)
0x18000f1ff  mov     rdx, rax
0x18000f202  lea     rcx, [rbp+var_40]
0x18000f206  call    ??0iterator@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@IEAA@VCLKRLinearHashTable_Iterator@2@@Z; LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::iterator::iterator(LKRhash::CLKRLinearHashTable_Iterator)
0x18000f20b  nop
0x18000f20c  xorps   xmm0, xmm0
0x18000f20f  movdqu  [rbp+var_58], xmm0
0x18000f214  mov     [rbp+var_48], 0
0x18000f21b  xor     eax, eax
0x18000f21d  mov     [rbp+var_44], ax
0x18000f221  lea     rdx, [rbp+var_58]
0x18000f225  lea     rcx, [rbp+var_28]
0x18000f229  call    ??0iterator@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@IEAA@VCLKRLinearHashTable_Iterator@2@@Z; LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::iterator::iterator(LKRhash::CLKRLinearHashTable_Iterator)
0x18000f22e  nop
0x18000f22f  lea     rdi, WPP_GLOBAL_Control
0x18000f236  movsx   rax, [rbp+var_2C]
0x18000f23b  mov     r8, [rbp+var_38]
0x18000f23f  cmp     r8, [rbp+var_20]
0x18000f243  jnz     short loc_18000F24B
0x18000f245  cmp     ax, [rbp+var_14]
0x18000f249  jz      short loc_18000F294
0x18000f24b  mov     rdx, rsi; struct BookKeepingXml *
0x18000f24e  mov     rcx, [r8+rax*8+18h]; this
0x18000f253  call    ?Dump@InterfaceRecord@@QEBAJAEAVBookKeepingXml@@@Z; InterfaceRecord::Dump(BookKeepingXml &)
0x18000f258  mov     ebx, eax
0x18000f25a  test    eax, eax
0x18000f25c  js      short loc_18000F269
0x18000f25e  lea     rcx, [rbp+var_40]; this
0x18000f262  call    ?Increment@CLKRLinearHashTable_Iterator@LKRhash@@QEAA_NXZ; LKRhash::CLKRLinearHashTable_Iterator::Increment(void)
0x18000f267  jmp     short loc_18000F22F
0x18000f269  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f270  cmp     rcx, rdi
0x18000f273  jz      short loc_18000F294
0x18000f275  cmp     byte ptr [rcx+19h], 2
0x18000f279  jb      short loc_18000F294
0x18000f27b  mov     edx, 0Eh
0x18000f280  mov     r9d, eax
0x18000f283  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f28a  mov     rcx, [rcx+10h]
0x18000f28e  call    WPP_SF_d
0x18000f293  nop
0x18000f294  or      edx, 0FFFFFFFFh; int
0x18000f297  lea     rcx, [rbp+var_28]; this
0x18000f29b  call    ?_AddRef@CLKRLinearHashTable_Iterator@LKRhash@@IEBAXH@Z; LKRhash::CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000f2a0  nop
0x18000f2a1  or      edx, 0FFFFFFFFh; int
0x18000f2a4  lea     rcx, [rbp+var_40]; this
0x18000f2a8  call    ?_AddRef@CLKRLinearHashTable_Iterator@LKRhash@@IEBAXH@Z; LKRhash::CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000f2ad  nop
0x18000f2ae  mov     rcx, rsi; this
0x18000f2b1  call    ?CloseTable@BookKeepingXml@@QEAAJXZ; BookKeepingXml::CloseTable(void)
0x18000f2b6  mov     esi, eax
0x18000f2b8  test    eax, eax
0x18000f2ba  jns     short loc_18000F2E6
0x18000f2bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2c3  cmp     rcx, rdi
0x18000f2c6  jz      short loc_18000F2E6
0x18000f2c8  cmp     byte ptr [rcx+19h], 2
0x18000f2cc  jb      short loc_18000F2E6
0x18000f2ce  mov     edx, 0Fh
0x18000f2d3  mov     r9d, eax
0x18000f2d6  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f2dd  mov     rcx, [rcx+10h]
0x18000f2e1  call    WPP_SF_d
0x18000f2e6  test    ebx, ebx
0x18000f2e8  cmovns  ebx, esi
0x18000f2eb  mov     eax, ebx
0x18000f2ed  add     rsp, 78h
0x18000f2f1  pop     rdi
0x18000f2f2  pop     rsi
0x18000f2f3  pop     rbx
0x18000f2f4  pop     rbp
0x18000f2f5  retn
```
