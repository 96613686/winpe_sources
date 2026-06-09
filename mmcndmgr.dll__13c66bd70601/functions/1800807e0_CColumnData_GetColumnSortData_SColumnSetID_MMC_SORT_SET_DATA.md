# CColumnData::GetColumnSortData(_SColumnSetID *,_MMC_SORT_SET_DATA * *)

- ea: `0x1800807e0`
- end: `0x18008098d`
- name: `?GetColumnSortData@CColumnData@@UEAAJPEAU_SColumnSetID@@PEAPEAU_MMC_SORT_SET_DATA@@@Z`
- size: `429`
- prototype: `__int64 __fastcall(CColumnData *__hidden this, struct _SColumnSetID *, struct _MMC_SORT_SET_DATA **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18004c0b0`
- `0x18004c1c8`
- `0x180080700`
- `0x1800807e0`

## import_xrefs

- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x180080833`
- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x180080833`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180080829`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180080829`
- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x180080871`
- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x180080871`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18008087b`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800808c2`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180080964`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18008087b`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800808c2`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x180080964`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180080800`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180080800`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180080847`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180080860`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008088d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800808b8`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008095a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180080847`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180080860`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008088d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800808b8`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008095a`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180080811`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180080811`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180080979`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180080979`
- `ole32!CoTaskMemAlloc` at `0x1800808e5`
- `ole32!CoTaskMemAlloc` at `0x1800808e5`

## pseudocode

```c
__int64 __fastcall CColumnData::GetColumnSortData(
        CColumnData *this,
        struct _SColumnSetID *a2,
        struct _MMC_SORT_SET_DATA **a3)
{
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // rcx
  unsigned int v8; // ebx
  unsigned int ColumnData; // eax
  int v10; // edi
  __int64 v11; // rdx
  char *v12; // rax
  int v13; // r8d
  __int64 *v14; // rcx
  MMC_SORT_DATA *pSortData; // r9
  __int64 *v16; // rax
  __int64 v17; // rdx
  _BYTE v19[32]; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v20[64]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v21; // [rsp+80h] [rbp+27h]
  int v22; // [rsp+88h] [rbp+2Fh]

  mmcerror::SC::SC((mmcerror::SC *)v19, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v19, L"IColumnData::SetColumnSortData");
  v6 = (const unsigned __int16 *)((char *)this + 8);
  if ( *((_QWORD *)this + 4) >= 8u )
    v6 = *(const unsigned __int16 **)v6;
  mmcerror::SC::SetSnapinName((mmcerror::SC *)v19, v6);
  mmcerror::SC::CheckCallingThreadID((mmcerror::SC *)v19);
  if ( !a2 )
  {
    mmcerror::SC::operator=(v19, 2147942487LL);
    v7 = L"NULL SColumnSetID ptr";
LABEL_7:
    TraceSnapinError(v7, (const struct mmcerror::SC *)v19);
    v8 = mmcerror::SC::ToHr((mmcerror::SC *)v19);
    goto LABEL_19;
  }
  if ( !a3 )
  {
    mmcerror::SC::operator=(v19, 2147942487LL);
    v7 = L"NULL MMC_COLUMN_SET_DATA ptr";
    goto LABEL_7;
  }
  mmcerror::SC::operator=(v19, 1);
  *a3 = 0;
  CColumnSetData::CColumnSetData((CColumnSetData *)v20);
  ColumnData = CColumnData::GetColumnData(this, a2, (struct CColumnSetData *)v20);
  mmcerror::SC::operator=(v19, ColumnData);
  if ( !mmcerror::SC::ToHr((mmcerror::SC *)v19) )
  {
    v10 = v22;
    if ( v22 > 0 )
    {
      v12 = (char *)CoTaskMemAlloc(16 * (v22 + 1));
      if ( v12 )
      {
        *a3 = (struct _MMC_SORT_SET_DATA *)v12;
        *(_DWORD *)v12 = 16;
        v13 = 0;
        (*a3)->nNumItems = v10;
        (*a3)->pSortData = (MMC_SORT_DATA *)(v12 + 16);
        v14 = v21;
        pSortData = (*a3)->pSortData;
        v16 = (__int64 *)*v21;
        while ( v16 != v14 )
        {
          v17 = v13++;
          pSortData[v17].nColIndex = *((_DWORD *)v16 + 8);
          pSortData[v17].dwSortOptions = *((_DWORD *)v16 + 9);
          pSortData[v17].ulReserved = v16[5];
          v16 = (__int64 *)*v16;
          v14 = v21;
        }
        v11 = 0;
      }
      else
      {
        v11 = 2147942414LL;
      }
    }
    else
    {
      v11 = 1;
    }
    mmcerror::SC::operator=(v19, v11);
  }
  v8 = mmcerror::SC::ToHr((mmcerror::SC *)v19);
  CColumnSetData::~CColumnSetData((CColumnSetData *)v20);
LABEL_19:
  mmcerror::SC::~SC((mmcerror::SC *)v19);
  return v8;
}

```

## disassembly

```asm
0x1800807e0  push    rbp
0x1800807e2  push    rbx
0x1800807e3  push    rsi
0x1800807e4  push    rdi
0x1800807e5  lea     rbp, [rsp-3Fh]
0x1800807ea  sub     rsp, 98h
0x1800807f1  mov     rdi, rdx
0x1800807f4  mov     rsi, rcx
0x1800807f7  xor     edx, edx
0x1800807f9  lea     rcx, [rbp+57h+var_90]
0x1800807fd  mov     rbx, r8
0x180080800  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x180080806  lea     rdx, aIcolumndataSet_0; "IColumnData::SetColumnSortData"
0x18008080d  lea     rcx, [rbp+57h+var_90]
0x180080811  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x180080817  lea     rdx, [rsi+8]
0x18008081b  cmp     qword ptr [rdx+18h], 8
0x180080820  jb      short loc_180080825
0x180080822  mov     rdx, [rdx]
0x180080825  lea     rcx, [rbp+57h+var_90]
0x180080829  call    cs:__imp_?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetSnapinName(ushort const *)
0x18008082f  lea     rcx, [rbp+57h+var_90]
0x180080833  call    cs:__imp_?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ; mmcerror::SC::CheckCallingThreadID(void)
0x180080839  lea     rcx, [rbp+57h+var_90]
0x18008083d  test    rdi, rdi
0x180080840  jnz     short loc_180080856
0x180080842  mov     edx, 80070057h
0x180080847  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18008084d  lea     rcx, aNullScolumnset; "NULL SColumnSetID ptr"
0x180080854  jmp     short loc_18008086D
0x180080856  test    rbx, rbx
0x180080859  jnz     short loc_180080888
0x18008085b  mov     edx, 80070057h
0x180080860  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180080866  lea     rcx, aNullMmcColumnS; "NULL MMC_COLUMN_SET_DATA ptr"
0x18008086d  lea     rdx, [rbp+57h+var_90]
0x180080871  call    cs:__imp_?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z; TraceSnapinError(ushort const *,mmcerror::SC const &)
0x180080877  lea     rcx, [rbp+57h+var_90]
0x18008087b  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180080881  mov     ebx, eax
0x180080883  jmp     loc_180080975
0x180080888  mov     edx, 1
0x18008088d  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180080893  lea     rcx, [rbp+57h+var_70]; this
0x180080897  mov     qword ptr [rbx], 0
0x18008089e  call    ??0CColumnSetData@@QEAA@XZ; CColumnSetData::CColumnSetData(void)
0x1800808a3  lea     r8, [rbp+57h+var_70]; struct CColumnSetData *
0x1800808a7  mov     rdx, rdi; struct _SColumnSetID *
0x1800808aa  mov     rcx, rsi; this
0x1800808ad  call    ?GetColumnData@CColumnData@@AEAAJPEAU_SColumnSetID@@AEAVCColumnSetData@@@Z; CColumnData::GetColumnData(_SColumnSetID *,CColumnSetData &)
0x1800808b2  mov     edx, eax
0x1800808b4  lea     rcx, [rbp+57h+var_90]
0x1800808b8  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800808be  lea     rcx, [rbp+57h+var_90]
0x1800808c2  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1800808c8  test    eax, eax
0x1800808ca  jnz     loc_180080960
0x1800808d0  mov     edi, [rbp+57h+var_28]
0x1800808d3  test    edi, edi
0x1800808d5  jg      short loc_1800808DC
0x1800808d7  lea     edx, [rax+1]
0x1800808da  jmp     short loc_180080956
0x1800808dc  lea     eax, [rdi+1]
0x1800808df  shl     eax, 4
0x1800808e2  movsxd  rcx, eax; cb
0x1800808e5  call    cs:__imp_CoTaskMemAlloc
0x1800808eb  mov     rcx, rax
0x1800808ee  test    rax, rax
0x1800808f1  jnz     short loc_1800808FA
0x1800808f3  mov     edx, 8007000Eh
0x1800808f8  jmp     short loc_180080956
0x1800808fa  mov     [rbx], rcx
0x1800808fd  add     rcx, 10h
0x180080901  mov     dword ptr [rax], 10h
0x180080907  xor     r8d, r8d
0x18008090a  mov     rax, [rbx]
0x18008090d  mov     [rax+4], edi
0x180080910  mov     rax, [rbx]
0x180080913  mov     [rax+8], rcx
0x180080917  mov     rax, [rbx]
0x18008091a  mov     rcx, [rbp+57h+var_30]
0x18008091e  mov     r9, [rax+8]
0x180080922  mov     rax, [rcx]
0x180080925  cmp     rax, rcx
0x180080928  jz      short loc_180080954
0x18008092a  mov     ecx, [rax+20h]
0x18008092d  movsxd  rdx, r8d
0x180080930  add     rdx, rdx
0x180080933  inc     r8d
0x180080936  mov     [r9+rdx*8], ecx
0x18008093a  mov     ecx, [rax+24h]
0x18008093d  mov     [r9+rdx*8+4], ecx
0x180080942  mov     rcx, [rax+28h]
0x180080946  mov     [r9+rdx*8+8], rcx
0x18008094b  mov     rax, [rax]
0x18008094e  mov     rcx, [rbp+57h+var_30]
0x180080952  jmp     short loc_180080925
0x180080954  xor     edx, edx
0x180080956  lea     rcx, [rbp+57h+var_90]
0x18008095a  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180080960  lea     rcx, [rbp+57h+var_90]
0x180080964  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18008096a  lea     rcx, [rbp+57h+var_70]; this
0x18008096e  mov     ebx, eax
0x180080970  call    ??1CColumnSetData@@QEAA@XZ; CColumnSetData::~CColumnSetData(void)
0x180080975  lea     rcx, [rbp+57h+var_90]
0x180080979  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18008097f  mov     eax, ebx
0x180080981  add     rsp, 98h
0x180080988  pop     rdi
0x180080989  pop     rsi
0x18008098a  pop     rbx
0x18008098b  pop     rbp
0x18008098c  retn
```
