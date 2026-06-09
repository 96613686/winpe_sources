# CRecord::get_ActiveConnectionEx(tagVARIANT *)

- ea: `0x1800919a0`
- end: `0x180091b40`
- name: `?get_ActiveConnectionEx@CRecord@@UEAAJPEAUtagVARIANT@@@Z`
- size: `416`
- prototype: `int(CRecord *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180018788`
- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x180057938`
- `0x18006a22c`
- `0x1800919a0`
- `0x1800c8f34`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180091a65`
- `OLEAUT32!__imp_VariantInit` at `0x180091a65`
- `OLEAUT32!__imp_VariantCopy` at `0x180091aa2`
- `OLEAUT32!__imp_VariantCopy` at `0x180091aa2`

## pseudocode

```c
__int64 __fastcall CRecord::get_ActiveConnectionEx(CRecord *this, struct tagVARIANT *a2)
{
  unsigned int BidObjectID; // eax
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rdx
  CVar *v8; // rcx
  __int64 v9; // r8
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-58h]
  _BYTE v13[40]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v14; // [rsp+58h] [rbp-20h]
  int v15; // [rsp+80h] [rbp+8h] BYREF

  CXLockContext::CXLockContext(
    (CXLockContext *)v13,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 24)
                               & ((unsigned __int128)-(__int128)((unsigned __int64)this - 8) >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 17) + 8LL),
    (const char *)this + 24);
  if ( a2 || (v15 = -2146825287, !(unsigned int)CContext::Failed((CContext *)v13, &v15)) )
  {
    VariantInit(a2);
    if ( !(unsigned int)CVar::HasValue((CRecord *)((char *)this + 160)) )
    {
      a2->vt = 9;
      a2->llVal = 0;
      goto LABEL_16;
    }
    CVar::UpdateVariant(v8);
    v15 = VariantCopy(a2, (const VARIANTARG *)(v9 + 16));
    if ( (unsigned int)CContext::Failed((CContext *)v13, &v15) && (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 144)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 144));
        v5 = 229385;
        v12 = 224;
        goto LABEL_6;
      }
      v6 = 224;
      v7 = 229385;
LABEL_15:
      bidTraceW(off_18012A1E8[0], v7, L"<CRecord::get_ActiveConnectionEx|ADO|ERR>  line %d\n", v6);
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 144)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 144));
      v5 = 217097;
      v12 = 212;
LABEL_6:
      bidTraceW(off_18012A1E8[0], v5, L"<CRecord::get_ActiveConnectionEx|ADO|ERR> %u#, line %d\n", BidObjectID, v12);
      goto LABEL_16;
    }
    v6 = 212;
    v7 = 217097;
    goto LABEL_15;
  }
LABEL_16:
  v10 = v14;
  CXLockContext::~CXLockContext((CXLockContext *)v13);
  return v10;
}

```

## disassembly

```asm
0x1800919a0  mov     [rsp+arg_8], rbx
0x1800919a5  push    rdi
0x1800919a6  sub     rsp, 70h
0x1800919aa  mov     r8, [rcx+88h]
0x1800919b1  lea     rax, [rcx-8]
0x1800919b5  mov     rbx, rdx
0x1800919b8  lea     r9, [rcx+18h]; char *
0x1800919bc  add     r8, 8; struct CCriticalSection **
0x1800919c0  mov     rdi, rcx
0x1800919c3  neg     rax
0x1800919c6  lea     rcx, [rsp+78h+var_48]; this
0x1800919cb  sbb     rdx, rdx
0x1800919ce  and     rdx, r9; struct CStdComObjectRoot *
0x1800919d1  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800919d6  test    rbx, rbx
0x1800919d9  jnz     loc_180091A62
0x1800919df  lea     rdx, [rsp+78h+arg_0]; int *
0x1800919e7  mov     [rsp+78h+arg_0], 800A0BB9h
0x1800919f2  lea     rcx, [rsp+78h+var_48]; this
0x1800919f7  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800919fc  test    eax, eax
0x1800919fe  jz      short loc_180091A62
0x180091a00  test    byte ptr cs:_bidGblFlags, 2
0x180091a07  jz      loc_180091B21
0x180091a0d  lea     rcx, [rdi+90h]; this
0x180091a14  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180091a19  cmp     eax, 0FFFFFFFFh
0x180091a1c  jz      short loc_180091A52
0x180091a1e  lea     rcx, [rdi+90h]; this
0x180091a25  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180091a2a  mov     edx, 35009h
0x180091a2f  mov     [rsp+78h+var_58], 0D4h
0x180091a37  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180091a3e  lea     r8, aCrecordGetActi; "<CRecord::get_ActiveConnectionEx|ADO|ER"...
0x180091a45  mov     r9d, eax
0x180091a48  call    _bidTraceW
0x180091a4d  jmp     loc_180091B21
0x180091a52  mov     r9d, 0D4h
0x180091a58  mov     edx, 35009h
0x180091a5d  jmp     loc_180091B0E
0x180091a62  mov     rcx, rbx; pvarg
0x180091a65  call    cs:__imp_VariantInit
0x180091a6c  nop     dword ptr [rax+rax+00h]
0x180091a71  lea     r8, [rdi+0A0h]
0x180091a78  mov     rcx, r8; this
0x180091a7b  call    ?HasValue@CVar@@QEBAHXZ; CVar::HasValue(void)
0x180091a80  test    eax, eax
0x180091a82  jnz     short loc_180091A96
0x180091a84  mov     word ptr [rbx], 9
0x180091a89  mov     qword ptr [rbx+8], 0
0x180091a91  jmp     loc_180091B21
0x180091a96  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x180091a9b  lea     rdx, [r8+10h]; pvargSrc
0x180091a9f  mov     rcx, rbx; pvargDest
0x180091aa2  call    cs:__imp_VariantCopy
0x180091aa9  nop     dword ptr [rax+rax+00h]
0x180091aae  lea     rdx, [rsp+78h+arg_0]; int *
0x180091ab6  mov     [rsp+78h+arg_0], eax
0x180091abd  lea     rcx, [rsp+78h+var_48]; this
0x180091ac2  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180091ac7  test    eax, eax
0x180091ac9  jz      short loc_180091B21
0x180091acb  test    byte ptr cs:_bidGblFlags, 2
0x180091ad2  jz      short loc_180091B21
0x180091ad4  lea     rcx, [rdi+90h]; this
0x180091adb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180091ae0  cmp     eax, 0FFFFFFFFh
0x180091ae3  jz      short loc_180091B03
0x180091ae5  lea     rcx, [rdi+90h]; this
0x180091aec  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180091af1  mov     edx, 38009h
0x180091af6  mov     [rsp+78h+var_58], 0E0h
0x180091afe  jmp     loc_180091A37
0x180091b03  mov     r9d, 0E0h
0x180091b09  mov     edx, 38009h
0x180091b0e  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180091b15  lea     r8, aCrecordGetActi_0; "<CRecord::get_ActiveConnectionEx|ADO|ER"...
0x180091b1c  call    _bidTraceW
0x180091b21  mov     ebx, [rsp+78h+var_20]
0x180091b25  lea     rcx, [rsp+78h+var_48]; this
0x180091b2a  call    ??1CXLockContext@@QEAA@XZ; CXLockContext::~CXLockContext(void)
0x180091b2f  mov     eax, ebx
0x180091b31  mov     rbx, [rsp+78h+arg_8]
0x180091b39  add     rsp, 70h
0x180091b3d  pop     rdi
0x180091b3e  retn
```
