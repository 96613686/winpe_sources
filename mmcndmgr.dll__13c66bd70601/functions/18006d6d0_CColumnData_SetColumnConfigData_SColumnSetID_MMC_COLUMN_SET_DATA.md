# CColumnData::SetColumnConfigData(_SColumnSetID *,_MMC_COLUMN_SET_DATA *)

- ea: `0x18006d6d0`
- end: `0x18006d890`
- name: `?SetColumnConfigData@CColumnData@@UEAAJPEAU_SColumnSetID@@PEAU_MMC_COLUMN_SET_DATA@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(CColumnData *__hidden this, struct _SColumnSetID *, struct _MMC_COLUMN_SET_DATA *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task`

## callees

- `0x180035a00`
- `0x1800496d4`
- `0x18004c0b0`
- `0x18004c1c8`
- `0x18006d6d0`
- `0x180080600`
- `0x1800806cc`
- `0x180080aa4`

## import_xrefs

- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x18006d725`
- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x18006d725`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18006d71b`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18006d71b`
- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x18006d763`
- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x18006d763`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18006d76d`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18006d807`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18006d846`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18006d76d`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18006d807`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18006d846`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18006d6f2`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18006d6f2`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006d739`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006d752`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006d77f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006d7fe`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006d83c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006d739`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006d752`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006d77f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006d7fe`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006d83c`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18006d703`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18006d703`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006d87a`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006d87a`

## string_xrefs

- `0x18006d6f8`: `IColumnData::SetColumnConfigData`

## pseudocode

```c
__int64 __fastcall CColumnData::SetColumnConfigData(
        CColumnData *this,
        struct _SColumnSetID *a2,
        struct _MMC_COLUMN_SET_DATA *a3)
{
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // rcx
  unsigned int v8; // ebx
  int i; // ebx
  MMC_COLUMN_DATA *pColData; // rcx
  char dwFlags; // r8
  char v12; // r8
  mmcerror::SC *v13; // rax
  unsigned int v14; // eax
  _BYTE v16[24]; // [rsp+20h] [rbp-79h] BYREF
  void **v17; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v18[3]; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v19[2]; // [rsp+58h] [rbp-41h] BYREF
  int nColIndex; // [rsp+68h] [rbp-31h]
  int nWidth; // [rsp+6Ch] [rbp-2Dh]
  BOOL v22; // [rsp+70h] [rbp-29h]
  _BYTE v23[24]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v24[88]; // [rsp+98h] [rbp-1h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v16, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v16, L"IColumnData::SetColumnConfigData");
  v6 = (const unsigned __int16 *)((char *)this + 8);
  if ( *((_QWORD *)this + 4) >= 8u )
    v6 = *(const unsigned __int16 **)v6;
  mmcerror::SC::SetSnapinName((mmcerror::SC *)v16, v6);
  mmcerror::SC::CheckCallingThreadID((mmcerror::SC *)v16);
  if ( !a2 )
  {
    mmcerror::SC::operator=(v16, 2147942487LL);
    v7 = L"NULL SColumnSetID ptr";
LABEL_7:
    TraceSnapinError(v7, (const struct mmcerror::SC *)v16);
    v8 = mmcerror::SC::ToHr((mmcerror::SC *)v16);
    goto LABEL_16;
  }
  if ( !a3 )
  {
    mmcerror::SC::operator=(v16, 2147942487LL);
    v7 = L"NULL MMC_COLUMN_SET_DATA ptr";
    goto LABEL_7;
  }
  mmcerror::SC::operator=(v16, 1);
  CColumnInfoList::CColumnInfoList((CColumnInfoList *)&v17);
  for ( i = 0; i < a3->nNumCols; ++i )
  {
    pColData = a3->pColData;
    v19[0] = &CColumnInfo::`vftable'{for `CSerialObject'};
    v19[1] = &CColumnInfo::`vftable'{for `CXMLObject'};
    dwFlags = pColData[i].dwFlags;
    nWidth = pColData[i].nWidth;
    v12 = dwFlags & 1;
    v22 = v12 != 0;
    nColIndex = pColData[i].nColIndex;
    if ( !nColIndex && v12 )
    {
      v13 = (mmcerror::SC *)mmcerror::SC::operator=(v16, 2147942487LL);
      v8 = mmcerror::SC::ToHr(v13);
      goto LABEL_15;
    }
    std::list<CColumnInfo>::_Insert<CColumnInfo const &>(v18, v18[0], v19);
  }
  CColumnSetData::CColumnSetData((CColumnSetData *)v23);
  CColumnInfoList::operator=(v24, &v17);
  v14 = CColumnData::SetColumnData(this, a2, (struct CColumnSetData *)v23);
  mmcerror::SC::operator=(v16, v14);
  v8 = mmcerror::SC::ToHr((mmcerror::SC *)v16);
  CColumnSetData::~CColumnSetData((CColumnSetData *)v23);
LABEL_15:
  v17 = &CColumnInfoList::`vftable'{for `XMLListCollectionImp<std::list<CColumnInfo>>'};
  v18[2] = &CColumnInfoList::`vftable'{for `CSerialObject'};
  std::list<CTaskStatus *>::~list<CTaskStatus *>(v18);
LABEL_16:
  mmcerror::SC::~SC((mmcerror::SC *)v16);
  return v8;
}

```

## disassembly

```asm
0x18006d6d0  push    rbp
0x18006d6d2  push    rbx
0x18006d6d3  push    rsi
0x18006d6d4  push    rdi
0x18006d6d5  push    r14
0x18006d6d7  lea     rbp, [rsp-37h]
0x18006d6dc  sub     rsp, 0D0h
0x18006d6e3  mov     rsi, rdx
0x18006d6e6  mov     r14, rcx
0x18006d6e9  xor     edx, edx
0x18006d6eb  lea     rcx, [rbp+57h+var_D0]
0x18006d6ef  mov     rdi, r8
0x18006d6f2  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18006d6f8  lea     rdx, aIcolumndataSet; "IColumnData::SetColumnConfigData"
0x18006d6ff  lea     rcx, [rbp+57h+var_D0]
0x18006d703  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18006d709  lea     rdx, [r14+8]
0x18006d70d  cmp     qword ptr [rdx+18h], 8
0x18006d712  jb      short loc_18006D717
0x18006d714  mov     rdx, [rdx]
0x18006d717  lea     rcx, [rbp+57h+var_D0]
0x18006d71b  call    cs:__imp_?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetSnapinName(ushort const *)
0x18006d721  lea     rcx, [rbp+57h+var_D0]
0x18006d725  call    cs:__imp_?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ; mmcerror::SC::CheckCallingThreadID(void)
0x18006d72b  lea     rcx, [rbp+57h+var_D0]
0x18006d72f  test    rsi, rsi
0x18006d732  jnz     short loc_18006D748
0x18006d734  mov     edx, 80070057h
0x18006d739  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18006d73f  lea     rcx, aNullScolumnset; "NULL SColumnSetID ptr"
0x18006d746  jmp     short loc_18006D75F
0x18006d748  test    rdi, rdi
0x18006d74b  jnz     short loc_18006D77A
0x18006d74d  mov     edx, 80070057h
0x18006d752  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18006d758  lea     rcx, aNullMmcColumnS; "NULL MMC_COLUMN_SET_DATA ptr"
0x18006d75f  lea     rdx, [rbp+57h+var_D0]
0x18006d763  call    cs:__imp_?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z; TraceSnapinError(ushort const *,mmcerror::SC const &)
0x18006d769  lea     rcx, [rbp+57h+var_D0]
0x18006d76d  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18006d773  mov     ebx, eax
0x18006d775  jmp     loc_18006D876
0x18006d77a  mov     edx, 1
0x18006d77f  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18006d785  lea     rcx, [rbp+57h+var_B8]; this
0x18006d789  call    ??0CColumnInfoList@@QEAA@XZ; CColumnInfoList::CColumnInfoList(void)
0x18006d78e  xor     ebx, ebx
0x18006d790  cmp     ebx, [rdi+4]
0x18006d793  jge     short loc_18006D811
0x18006d795  mov     rcx, [rdi+8]
0x18006d799  lea     rax, ??_7CColumnInfo@@6BCSerialObject@@@; const CColumnInfo::`vftable'{for `CSerialObject'}
0x18006d7a0  mov     [rbp+57h+var_98], rax
0x18006d7a4  lea     rax, ??_7CColumnInfo@@6BCXMLObject@@@; const CColumnInfo::`vftable'{for `CXMLObject'}
0x18006d7ab  mov     [rbp+57h+var_90], rax
0x18006d7af  movsxd  rax, ebx
0x18006d7b2  lea     rdx, [rax+rax*2]
0x18006d7b6  mov     eax, [rcx+rdx*8+8]
0x18006d7ba  mov     r8b, [rcx+rdx*8+4]
0x18006d7bf  mov     [rbp+57h+var_84], eax
0x18006d7c2  and     r8b, 1
0x18006d7c6  mov     eax, 0
0x18006d7cb  setnz   al
0x18006d7ce  mov     [rbp+57h+var_80], eax
0x18006d7d1  mov     eax, [rcx+rdx*8]
0x18006d7d4  mov     [rbp+57h+var_88], eax
0x18006d7d7  test    eax, eax
0x18006d7d9  jnz     short loc_18006D7E0
0x18006d7db  test    r8b, r8b
0x18006d7de  jnz     short loc_18006D7F5
0x18006d7e0  mov     rdx, [rbp+57h+var_B0]
0x18006d7e4  lea     r8, [rbp+57h+var_98]
0x18006d7e8  lea     rcx, [rbp+57h+var_B0]
0x18006d7ec  call    ??$_Insert@AEBVCColumnInfo@@@?$list@VCColumnInfo@@V?$allocator@VCColumnInfo@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@VCColumnInfo@@@std@@@std@@U_Iterator_base0@2@@1@AEBVCColumnInfo@@@Z; std::list<CColumnInfo>::_Insert<CColumnInfo const &>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<CColumnInfo>>,std::_Iterator_base0>,CColumnInfo const &)
0x18006d7f1  inc     ebx
0x18006d7f3  jmp     short loc_18006D790
0x18006d7f5  mov     edx, 80070057h
0x18006d7fa  lea     rcx, [rbp+57h+var_D0]
0x18006d7fe  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18006d804  mov     rcx, rax
0x18006d807  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18006d80d  mov     ebx, eax
0x18006d80f  jmp     short loc_18006D857
0x18006d811  lea     rcx, [rbp+57h+var_70]; this
0x18006d815  call    ??0CColumnSetData@@QEAA@XZ; CColumnSetData::CColumnSetData(void)
0x18006d81a  lea     rdx, [rbp+57h+var_B8]
0x18006d81e  lea     rcx, [rbp+57h+var_58]
0x18006d822  call    ??4CColumnInfoList@@QEAAAEAV0@AEBV0@@Z; CColumnInfoList::operator=(CColumnInfoList const &)
0x18006d827  lea     r8, [rbp+57h+var_70]; struct CColumnSetData *
0x18006d82b  mov     rdx, rsi; struct _SColumnSetID *
0x18006d82e  mov     rcx, r14; this
0x18006d831  call    ?SetColumnData@CColumnData@@AEAAJPEAU_SColumnSetID@@AEAVCColumnSetData@@@Z; CColumnData::SetColumnData(_SColumnSetID *,CColumnSetData &)
0x18006d836  mov     edx, eax
0x18006d838  lea     rcx, [rbp+57h+var_D0]
0x18006d83c  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18006d842  lea     rcx, [rbp+57h+var_D0]
0x18006d846  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18006d84c  lea     rcx, [rbp+57h+var_70]; this
0x18006d850  mov     ebx, eax
0x18006d852  call    ??1CColumnSetData@@QEAA@XZ; CColumnSetData::~CColumnSetData(void)
0x18006d857  lea     rax, ??_7CColumnInfoList@@6B?$XMLListCollectionImp@V?$list@VCColumnInfo@@V?$allocator@VCColumnInfo@@@std@@@std@@@@@; const CColumnInfoList::`vftable'{for `XMLListCollectionImp<std::list<CColumnInfo>>'}
0x18006d85e  mov     [rbp+57h+var_B8], rax
0x18006d862  lea     rcx, [rbp+57h+var_B0]
0x18006d866  lea     rax, ??_7CColumnInfoList@@6BCSerialObject@@@; const CColumnInfoList::`vftable'{for `CSerialObject'}
0x18006d86d  mov     [rbp+57h+var_A0], rax
0x18006d871  call    ??1?$list@PEAVCTaskStatus@@V?$allocator@PEAVCTaskStatus@@@std@@@std@@QEAA@XZ; std::list<CTaskStatus *>::~list<CTaskStatus *>(void)
0x18006d876  lea     rcx, [rbp+57h+var_D0]
0x18006d87a  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18006d880  mov     eax, ebx
0x18006d882  add     rsp, 0D0h
0x18006d889  pop     r14
0x18006d88b  pop     rdi
0x18006d88c  pop     rsi
0x18006d88d  pop     rbx
0x18006d88e  pop     rbp
0x18006d88f  retn
```
