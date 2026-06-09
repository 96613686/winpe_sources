# CRecord::get_Source(tagVARIANT *)

- ea: `0x180092580`
- end: `0x180092782`
- name: `?get_Source@CRecord@@UEAAJPEAUtagVARIANT@@@Z`
- size: `514`
- prototype: `int(CRecord *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180092790`

## callees

- `0x180018788`
- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x180057938`
- `0x18006a22c`
- `0x180092580`
- `0x1800c8f34`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800926f2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800926f2`
- `OLEAUT32!__imp_VariantInit` at `0x180092653`
- `OLEAUT32!__imp_VariantInit` at `0x180092653`
- `OLEAUT32!__imp_VariantCopy` at `0x18009267e`
- `OLEAUT32!__imp_VariantCopy` at `0x18009267e`

## pseudocode

```c
__int64 __fastcall CRecord::get_Source(CRecord *this, struct tagVARIANT *a2)
{
  unsigned int BidObjectID; // eax
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rdx
  CVar *v8; // rcx
  __int64 v9; // r8
  BSTR v10; // rax
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-58h]
  _BYTE v14[40]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v15; // [rsp+58h] [rbp-20h]
  int v16; // [rsp+A0h] [rbp+28h] BYREF

  CXLockContext::CXLockContext(
    (CXLockContext *)v14,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 18) + 8LL),
    (const char *)this + 32);
  if ( a2 || (v16 = -2146825287, !(unsigned int)CContext::Failed((CContext *)v14, &v16)) )
  {
    VariantInit(a2);
    if ( (unsigned int)CVar::HasValue((CRecord *)((char *)this + 216)) )
    {
      CVar::UpdateVariant(v8);
      v16 = VariantCopy(a2, (const VARIANTARG *)(v9 + 16));
      if ( (unsigned int)CContext::Failed((CContext *)v14, &v16) && (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v5 = 320521;
          v13 = 313;
          goto LABEL_6;
        }
        v6 = 313;
        v7 = 320521;
LABEL_8:
        bidTraceW(off_18012A1E8[0], v7, L"<CRecord::get_Source|ADO|ERR>  line %d\n", v6);
      }
    }
    else
    {
      v10 = SysAllocStringLen(0, 0);
      a2->llVal = (LONGLONG)v10;
      if ( v10 || (v16 = -2147024882, !(unsigned int)CContext::Failed((CContext *)v14, &v16)) )
      {
        a2->vt = 8;
        goto LABEL_22;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
          v5 = 327689;
          v13 = 320;
          goto LABEL_6;
        }
        v6 = 320;
        v7 = 327689;
        goto LABEL_8;
      }
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecord *)((char *)this + 152));
      v5 = 313353;
      v13 = 306;
LABEL_6:
      bidTraceW(off_18012A1E8[0], v5, L"<CRecord::get_Source|ADO|ERR> %u#, line %d\n", BidObjectID, v13);
      goto LABEL_22;
    }
    v6 = 306;
    v7 = 313353;
    goto LABEL_8;
  }
LABEL_22:
  v11 = v15;
  CXLockContext::~CXLockContext((CXLockContext *)v14);
  return v11;
}

```

## disassembly

```asm
0x180092580  push    rbp
0x180092582  push    rbx
0x180092583  push    rsi
0x180092584  push    rdi
0x180092585  mov     rbp, rsp
0x180092588  sub     rsp, 78h
0x18009258c  mov     r8, [rcx+90h]
0x180092593  lea     r9, [rcx+20h]; char *
0x180092597  mov     rax, rcx
0x18009259a  mov     rdi, rdx
0x18009259d  mov     rbx, rcx
0x1800925a0  mov     esi, 8
0x1800925a5  add     r8, rsi; struct CCriticalSection **
0x1800925a8  lea     rcx, [rbp+var_48]; this
0x1800925ac  neg     rax
0x1800925af  sbb     rdx, rdx
0x1800925b2  and     rdx, r9; struct CStdComObjectRoot *
0x1800925b5  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800925ba  test    rdi, rdi
0x1800925bd  jnz     loc_180092650
0x1800925c3  lea     rdx, [rbp+arg_0]; int *
0x1800925c7  mov     [rbp+arg_0], 800A0BB9h
0x1800925ce  lea     rcx, [rbp+var_48]; this
0x1800925d2  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800925d7  test    eax, eax
0x1800925d9  jz      short loc_180092650
0x1800925db  test    byte ptr cs:_bidGblFlags, 2
0x1800925e2  jz      loc_18009276A
0x1800925e8  lea     rcx, [rbx+98h]; this
0x1800925ef  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800925f4  cmp     eax, 0FFFFFFFFh
0x1800925f7  jz      short loc_18009262D
0x1800925f9  lea     rcx, [rbx+98h]; this
0x180092600  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180092605  mov     edx, 4C809h
0x18009260a  mov     [rsp+78h+var_58], 132h
0x180092612  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180092619  lea     r8, aCrecordGetSour_0; "<CRecord::get_Source|ADO|ERR> %u#, line"...
0x180092620  mov     r9d, eax
0x180092623  call    _bidTraceW
0x180092628  jmp     loc_18009276A
0x18009262d  mov     r9d, 132h
0x180092633  mov     edx, 4C809h
0x180092638  mov     rcx, cs:off_18012A1E8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18009263f  lea     r8, aCrecordGetSour; "<CRecord::get_Source|ADO|ERR>  line %d"...
0x180092646  call    _bidTraceW
0x18009264b  jmp     loc_18009276A
0x180092650  mov     rcx, rdi; pvarg
0x180092653  call    cs:__imp_VariantInit
0x18009265a  nop     dword ptr [rax+rax+00h]
0x18009265f  lea     r8, [rbx+0D8h]
0x180092666  mov     rcx, r8; this
0x180092669  call    ?HasValue@CVar@@QEBAHXZ; CVar::HasValue(void)
0x18009266e  test    eax, eax
0x180092670  jz      short loc_1800926EE
0x180092672  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x180092677  lea     rdx, [r8+10h]; pvargSrc
0x18009267b  mov     rcx, rdi; pvargDest
0x18009267e  call    cs:__imp_VariantCopy
0x180092685  nop     dword ptr [rax+rax+00h]
0x18009268a  lea     rdx, [rbp+arg_0]; int *
0x18009268e  mov     [rbp+arg_0], eax
0x180092691  lea     rcx, [rbp+var_48]; this
0x180092695  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009269a  test    eax, eax
0x18009269c  jz      loc_18009276A
0x1800926a2  test    byte ptr cs:_bidGblFlags, 2
0x1800926a9  jz      loc_18009276A
0x1800926af  lea     rcx, [rbx+98h]; this
0x1800926b6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800926bb  cmp     eax, 0FFFFFFFFh
0x1800926be  jz      short loc_1800926DE
0x1800926c0  lea     rcx, [rbx+98h]; this
0x1800926c7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800926cc  mov     edx, 4E409h
0x1800926d1  mov     [rsp+78h+var_58], 139h
0x1800926d9  jmp     loc_180092612
0x1800926de  mov     r9d, 139h
0x1800926e4  mov     edx, 4E409h
0x1800926e9  jmp     loc_180092638
0x1800926ee  xor     edx, edx; ui
0x1800926f0  xor     ecx, ecx; strIn
0x1800926f2  call    cs:__imp_SysAllocStringLen
0x1800926f9  nop     dword ptr [rax+rax+00h]
0x1800926fe  mov     [rdi+8], rax
0x180092702  test    rax, rax
0x180092705  jnz     short loc_180092767
0x180092707  lea     rdx, [rbp+arg_0]; int *
0x18009270b  mov     [rbp+arg_0], 8007000Eh
0x180092712  lea     rcx, [rbp+var_48]; this
0x180092716  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18009271b  test    eax, eax
0x18009271d  jz      short loc_180092767
0x18009271f  test    byte ptr cs:_bidGblFlags, 2
0x180092726  jz      short loc_18009276A
0x180092728  lea     rcx, [rbx+98h]; this
0x18009272f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180092734  cmp     eax, 0FFFFFFFFh
0x180092737  jz      short loc_180092757
0x180092739  lea     rcx, [rbx+98h]; this
0x180092740  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180092745  mov     edx, 50009h
0x18009274a  mov     [rsp+78h+var_58], 140h
0x180092752  jmp     loc_180092612
0x180092757  mov     r9d, 140h
0x18009275d  mov     edx, 50009h
0x180092762  jmp     loc_180092638
0x180092767  mov     [rdi], si
0x18009276a  mov     ebx, [rbp+var_20]
0x18009276d  lea     rcx, [rbp+var_48]; this
0x180092771  call    ??1CXLockContext@@QEAA@XZ; CXLockContext::~CXLockContext(void)
0x180092776  mov     eax, ebx
0x180092778  add     rsp, 78h
0x18009277c  pop     rdi
0x18009277d  pop     rsi
0x18009277e  pop     rbx
0x18009277f  pop     rbp
0x180092780  retn
```
