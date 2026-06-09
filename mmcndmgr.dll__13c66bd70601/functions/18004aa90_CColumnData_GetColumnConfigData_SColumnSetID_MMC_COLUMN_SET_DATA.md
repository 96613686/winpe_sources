# CColumnData::GetColumnConfigData(_SColumnSetID *,_MMC_COLUMN_SET_DATA * *)

- ea: `0x18004aa90`
- end: `0x18004ac3a`
- name: `?GetColumnConfigData@CColumnData@@UEAAJPEAU_SColumnSetID@@PEAPEAU_MMC_COLUMN_SET_DATA@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(CColumnData *__hidden this, struct _SColumnSetID *, struct _MMC_COLUMN_SET_DATA **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x18004aa90`
- `0x18004c0b0`
- `0x18004c1c8`
- `0x180080700`

## import_xrefs

- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x18004aae3`
- `mmcbase!?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ` at `0x18004aae3`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18004aad9`
- `mmcbase!?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18004aad9`
- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x18004ab21`
- `mmcbase!?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x18004ab21`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18004ab2b`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18004ab6f`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18004ab91`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18004ab2b`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18004ab6f`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18004ab91`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18004aab0`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18004aab0`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18004aaf7`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18004ab10`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18004ab3a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18004ab65`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18004ab87`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18004aaf7`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18004ab10`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18004ab3a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18004ab65`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18004ab87`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18004aac1`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18004aac1`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004aba6`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18004aba6`
- `ole32!CoTaskMemAlloc` at `0x18004abc7`
- `ole32!CoTaskMemAlloc` at `0x18004abc7`

## string_xrefs

- `0x18004aab6`: `IColumnData::GetColumnConfigData`

## pseudocode

```c
__int64 __fastcall CColumnData::GetColumnConfigData(
        CColumnData *this,
        struct _SColumnSetID *a2,
        struct _MMC_COLUMN_SET_DATA **a3)
{
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // rcx
  unsigned int v8; // ebx
  unsigned int ColumnData; // eax
  int v10; // ebx
  __int64 v11; // rdx
  char *v13; // rax
  int v14; // r8d
  __int64 *v15; // rcx
  MMC_COLUMN_DATA *pColData; // r9
  __int64 *v17; // rax
  __int64 v18; // rdx
  _BYTE v19[32]; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v20[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v21; // [rsp+60h] [rbp+7h]
  int v22; // [rsp+68h] [rbp+Fh]

  mmcerror::SC::SC((mmcerror::SC *)v19, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v19, L"IColumnData::GetColumnConfigData");
  v6 = (const unsigned __int16 *)((char *)this + 8);
  if ( *((_QWORD *)this + 4) >= 8u )
    v6 = *(const unsigned __int16 **)v6;
  mmcerror::SC::SetSnapinName((mmcerror::SC *)v19, v6);
  mmcerror::SC::CheckCallingThreadID((mmcerror::SC *)v19);
  if ( a2 )
  {
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
        v13 = (char *)CoTaskMemAlloc(24 * v22 + 16);
        if ( v13 )
        {
          *a3 = (struct _MMC_COLUMN_SET_DATA *)v13;
          *(_DWORD *)v13 = 16;
          v14 = 0;
          (*a3)->nNumCols = v10;
          (*a3)->pColData = (MMC_COLUMN_DATA *)(v13 + 16);
          v15 = v21;
          pColData = (*a3)->pColData;
          v17 = (__int64 *)*v21;
          while ( v17 != v15 )
          {
            v18 = v14;
            pColData[v18].nWidth = *((_DWORD *)v17 + 9);
            pColData[v18].dwFlags = v17[5] & 1;
            ++v14;
            pColData[v18].nColIndex = *((_DWORD *)v17 + 8);
            v17 = (__int64 *)*v17;
            v15 = v21;
          }
          goto LABEL_12;
        }
        v11 = 2147942414LL;
      }
      else
      {
        v11 = 1;
      }
      mmcerror::SC::operator=(v19, v11);
    }
LABEL_12:
    v8 = mmcerror::SC::ToHr((mmcerror::SC *)v19);
    CColumnSetData::~CColumnSetData((CColumnSetData *)v20);
    goto LABEL_13;
  }
  mmcerror::SC::operator=(v19, 2147942487LL);
  v7 = L"NULL SColumnSetID ptr";
LABEL_7:
  TraceSnapinError(v7, (const struct mmcerror::SC *)v19);
  v8 = mmcerror::SC::ToHr((mmcerror::SC *)v19);
LABEL_13:
  mmcerror::SC::~SC((mmcerror::SC *)v19);
  return v8;
}

```

## disassembly

```asm
0x18004aa90  push    rbp
0x18004aa92  push    rbx
0x18004aa93  push    rsi
0x18004aa94  push    rdi
0x18004aa95  lea     rbp, [rsp-3Fh]
0x18004aa9a  sub     rsp, 98h
0x18004aaa1  mov     rbx, rdx
0x18004aaa4  mov     rsi, rcx
0x18004aaa7  xor     edx, edx
0x18004aaa9  lea     rcx, [rbp+57h+var_90]
0x18004aaad  mov     rdi, r8
0x18004aab0  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18004aab6  lea     rdx, aIcolumndataGet; "IColumnData::GetColumnConfigData"
0x18004aabd  lea     rcx, [rbp+57h+var_90]
0x18004aac1  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18004aac7  lea     rdx, [rsi+8]
0x18004aacb  cmp     qword ptr [rdx+18h], 8
0x18004aad0  jb      short loc_18004AAD5
0x18004aad2  mov     rdx, [rdx]
0x18004aad5  lea     rcx, [rbp+57h+var_90]
0x18004aad9  call    cs:__imp_?SetSnapinName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetSnapinName(ushort const *)
0x18004aadf  lea     rcx, [rbp+57h+var_90]
0x18004aae3  call    cs:__imp_?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ; mmcerror::SC::CheckCallingThreadID(void)
0x18004aae9  lea     rcx, [rbp+57h+var_90]
0x18004aaed  test    rbx, rbx
0x18004aaf0  jnz     short loc_18004AB06
0x18004aaf2  mov     edx, 80070057h
0x18004aaf7  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18004aafd  lea     rcx, aNullScolumnset; "NULL SColumnSetID ptr"
0x18004ab04  jmp     short loc_18004AB1D
0x18004ab06  test    rdi, rdi
0x18004ab09  jnz     short loc_18004AB35
0x18004ab0b  mov     edx, 80070057h
0x18004ab10  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18004ab16  lea     rcx, aNullMmcColumnS; "NULL MMC_COLUMN_SET_DATA ptr"
0x18004ab1d  lea     rdx, [rbp+57h+var_90]
0x18004ab21  call    cs:__imp_?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z; TraceSnapinError(ushort const *,mmcerror::SC const &)
0x18004ab27  lea     rcx, [rbp+57h+var_90]
0x18004ab2b  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18004ab31  mov     ebx, eax
0x18004ab33  jmp     short loc_18004ABA2
0x18004ab35  mov     edx, 1
0x18004ab3a  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18004ab40  lea     rcx, [rbp+57h+var_70]; this
0x18004ab44  mov     qword ptr [rdi], 0
0x18004ab4b  call    ??0CColumnSetData@@QEAA@XZ; CColumnSetData::CColumnSetData(void)
0x18004ab50  lea     r8, [rbp+57h+var_70]; struct CColumnSetData *
0x18004ab54  mov     rdx, rbx; struct _SColumnSetID *
0x18004ab57  mov     rcx, rsi; this
0x18004ab5a  call    ?GetColumnData@CColumnData@@AEAAJPEAU_SColumnSetID@@AEAVCColumnSetData@@@Z; CColumnData::GetColumnData(_SColumnSetID *,CColumnSetData &)
0x18004ab5f  mov     edx, eax
0x18004ab61  lea     rcx, [rbp+57h+var_90]
0x18004ab65  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18004ab6b  lea     rcx, [rbp+57h+var_90]
0x18004ab6f  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18004ab75  test    eax, eax
0x18004ab77  jnz     short loc_18004AB8D
0x18004ab79  mov     ebx, [rbp+57h+var_48]
0x18004ab7c  test    ebx, ebx
0x18004ab7e  jg      short loc_18004ABBA
0x18004ab80  lea     edx, [rax+1]
0x18004ab83  lea     rcx, [rbp+57h+var_90]
0x18004ab87  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18004ab8d  lea     rcx, [rbp+57h+var_90]
0x18004ab91  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18004ab97  lea     rcx, [rbp+57h+var_70]; this
0x18004ab9b  mov     ebx, eax
0x18004ab9d  call    ??1CColumnSetData@@QEAA@XZ; CColumnSetData::~CColumnSetData(void)
0x18004aba2  lea     rcx, [rbp+57h+var_90]
0x18004aba6  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18004abac  mov     eax, ebx
0x18004abae  add     rsp, 98h
0x18004abb5  pop     rdi
0x18004abb6  pop     rsi
0x18004abb7  pop     rbx
0x18004abb8  pop     rbp
0x18004abb9  retn
0x18004abba  lea     eax, [rbx+rbx*2]
0x18004abbd  lea     eax, ds:10h[rax*8]
0x18004abc4  movsxd  rcx, eax; cb
0x18004abc7  call    cs:__imp_CoTaskMemAlloc
0x18004abcd  mov     rcx, rax
0x18004abd0  test    rax, rax
0x18004abd3  jnz     short loc_18004ABDC
0x18004abd5  mov     edx, 8007000Eh
0x18004abda  jmp     short loc_18004AB83
0x18004abdc  mov     [rdi], rcx
0x18004abdf  add     rcx, 10h
0x18004abe3  mov     dword ptr [rax], 10h
0x18004abe9  xor     r8d, r8d
0x18004abec  mov     rax, [rdi]
0x18004abef  mov     [rax+4], ebx
0x18004abf2  mov     rax, [rdi]
0x18004abf5  mov     [rax+8], rcx
0x18004abf9  mov     rax, [rdi]
0x18004abfc  mov     rcx, [rbp+57h+var_50]
0x18004ac00  mov     r9, [rax+8]
0x18004ac04  mov     rax, [rcx]
0x18004ac07  cmp     rax, rcx
0x18004ac0a  jz      short loc_18004AB8D
0x18004ac0c  movsxd  rcx, r8d
0x18004ac0f  lea     rdx, [rcx+rcx*2]
0x18004ac13  mov     ecx, [rax+24h]
0x18004ac16  mov     [r9+rdx*8+8], ecx
0x18004ac1b  movzx   ecx, byte ptr [rax+28h]
0x18004ac1f  and     ecx, 1
0x18004ac22  mov     [r9+rdx*8+4], ecx
0x18004ac27  inc     r8d
0x18004ac2a  mov     ecx, [rax+20h]
0x18004ac2d  mov     [r9+rdx*8], ecx
0x18004ac31  mov     rax, [rax]
0x18004ac34  mov     rcx, [rbp+57h+var_50]
0x18004ac38  jmp     short loc_18004AC07
```
