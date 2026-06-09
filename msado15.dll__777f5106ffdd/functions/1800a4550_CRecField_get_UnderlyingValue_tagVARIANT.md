# CRecField::get_UnderlyingValue(tagVARIANT *)

- ea: `0x1800a4550`
- end: `0x1800a474e`
- name: `?get_UnderlyingValue@CRecField@@UEAAJPEAUtagVARIANT@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(CRecField *__hidden this, VARIANTARG *pvargDest)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800a4760`

## callees

- `0x180018788`
- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x18006a22c`
- `0x18009f940`
- `0x1800a4550`
- `0x1800c8f34`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800a4605`
- `OLEAUT32!__imp_VariantInit` at `0x1800a4605`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a4640`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a46bd`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a4640`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a46bd`

## pseudocode

```c
__int64 __fastcall CRecField::get_UnderlyingValue(CRecField *this, VARIANTARG *pvargDest)
{
  unsigned int BidObjectID; // eax
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r8
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-50h]
  _BYTE v13[40]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v14; // [rsp+58h] [rbp-18h]
  int v15; // [rsp+80h] [rbp+10h] BYREF

  CXLockContext::CXLockContext(
    (CXLockContext *)v13,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 8)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 8) + 8LL),
    (const char *)this + 8);
  if ( pvargDest || (v15 = -2146825287, !(unsigned int)CContext::Failed((CContext *)v13, &v15)) )
  {
    VariantInit(pvargDest);
    if ( !(unsigned int)CRecField::IsPropReadable(this) )
      goto LABEL_21;
    if ( (*((_BYTE *)this + 336) & 4) != 0 )
    {
      CVar::UpdateVariant((CRecField *)((char *)this + 240));
      v15 = VariantCopy(pvargDest, (const VARIANTARG *)(v8 + 16));
      if ( (unsigned int)CContext::Failed((CContext *)v13, &v15) && (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
          v5 = 619529;
          v12 = 605;
          goto LABEL_6;
        }
        v6 = 605;
        v7 = 619529;
LABEL_20:
        bidTraceW(off_18012A200[0], v7, L"<CRecField::get_UnderlyingValue|ADO|ERR>  line %d\n", v6);
      }
    }
    else
    {
      CVar::UpdateVariant((CRecField *)((char *)this + 288));
      v15 = VariantCopy(pvargDest, (const VARIANTARG *)(v9 + 16));
      if ( (unsigned int)CContext::Failed((CContext *)v13, &v15) && (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
          v5 = 621577;
          v12 = 607;
          goto LABEL_6;
        }
        v6 = 607;
        v7 = 621577;
        goto LABEL_20;
      }
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
      v5 = 611337;
      v12 = 597;
LABEL_6:
      bidTraceW(off_18012A200[0], v5, L"<CRecField::get_UnderlyingValue|ADO|ERR> %u#, line %d\n", BidObjectID, v12);
      goto LABEL_21;
    }
    v6 = 597;
    v7 = 611337;
    goto LABEL_20;
  }
LABEL_21:
  v10 = v14;
  CXLockContext::~CXLockContext((CXLockContext *)v13);
  return v10;
}

```

## disassembly

```asm
0x1800a4550  mov     [rsp-8+arg_8], rbx
0x1800a4555  mov     [rsp-8+arg_10], rdi
0x1800a455a  push    rbp
0x1800a455b  mov     rbp, rsp
0x1800a455e  sub     rsp, 70h
0x1800a4562  mov     r8, [rcx+40h]
0x1800a4566  lea     r9, [rcx+8]; char *
0x1800a456a  mov     rax, rcx
0x1800a456d  mov     rdi, rdx
0x1800a4570  add     r8, 8; struct CCriticalSection **
0x1800a4574  mov     rbx, rcx
0x1800a4577  neg     rax
0x1800a457a  lea     rcx, [rbp+var_40]; this
0x1800a457e  sbb     rdx, rdx
0x1800a4581  and     rdx, r9; struct CStdComObjectRoot *
0x1800a4584  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800a4589  test    rdi, rdi
0x1800a458c  jnz     short loc_1800A4602
0x1800a458e  lea     rdx, [rbp+arg_0]; int *
0x1800a4592  mov     [rbp+arg_0], 800A0BB9h
0x1800a4599  lea     rcx, [rbp+var_40]; this
0x1800a459d  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a45a2  test    eax, eax
0x1800a45a4  jz      short loc_1800A4602
0x1800a45a6  test    byte ptr cs:_bidGblFlags, 2
0x1800a45ad  jz      loc_1800A472D
0x1800a45b3  lea     rcx, [rbx+58h]; this
0x1800a45b7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a45bc  cmp     eax, 0FFFFFFFFh
0x1800a45bf  jz      short loc_1800A45F2
0x1800a45c1  lea     rcx, [rbx+58h]; this
0x1800a45c5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a45ca  mov     edx, 95409h
0x1800a45cf  mov     [rsp+70h+var_50], 255h
0x1800a45d7  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a45de  lea     r8, aCrecfieldGetUn_0; "<CRecField::get_UnderlyingValue|ADO|ERR"...
0x1800a45e5  mov     r9d, eax
0x1800a45e8  call    _bidTraceW
0x1800a45ed  jmp     loc_1800A472D
0x1800a45f2  mov     r9d, 255h
0x1800a45f8  mov     edx, 95409h
0x1800a45fd  jmp     loc_1800A471A
0x1800a4602  mov     rcx, rdi; pvarg
0x1800a4605  call    cs:__imp_VariantInit
0x1800a460c  nop     dword ptr [rax+rax+00h]
0x1800a4611  mov     rcx, rbx; this
0x1800a4614  call    ?IsPropReadable@CRecField@@AEAAHXZ; CRecField::IsPropReadable(void)
0x1800a4619  test    eax, eax
0x1800a461b  jz      loc_1800A472D
0x1800a4621  test    byte ptr [rbx+150h], 4
0x1800a4628  jz      short loc_1800A46A7
0x1800a462a  lea     r8, [rbx+0F0h]
0x1800a4631  mov     rcx, r8; this
0x1800a4634  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x1800a4639  lea     rdx, [r8+10h]; pvargSrc
0x1800a463d  mov     rcx, rdi; pvargDest
0x1800a4640  call    cs:__imp_VariantCopy
0x1800a4647  nop     dword ptr [rax+rax+00h]
0x1800a464c  lea     rdx, [rbp+arg_0]; int *
0x1800a4650  mov     [rbp+arg_0], eax
0x1800a4653  lea     rcx, [rbp+var_40]; this
0x1800a4657  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a465c  test    eax, eax
0x1800a465e  jz      loc_1800A472D
0x1800a4664  test    byte ptr cs:_bidGblFlags, 2
0x1800a466b  jz      loc_1800A472D
0x1800a4671  lea     rcx, [rbx+58h]; this
0x1800a4675  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a467a  cmp     eax, 0FFFFFFFFh
0x1800a467d  jz      short loc_1800A469A
0x1800a467f  lea     rcx, [rbx+58h]; this
0x1800a4683  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a4688  mov     edx, 97409h
0x1800a468d  mov     [rsp+70h+var_50], 25Dh
0x1800a4695  jmp     loc_1800A45D7
0x1800a469a  mov     r9d, 25Dh
0x1800a46a0  mov     edx, 97409h
0x1800a46a5  jmp     short loc_1800A471A
0x1800a46a7  lea     r8, [rbx+120h]
0x1800a46ae  mov     rcx, r8; this
0x1800a46b1  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x1800a46b6  lea     rdx, [r8+10h]; pvargSrc
0x1800a46ba  mov     rcx, rdi; pvargDest
0x1800a46bd  call    cs:__imp_VariantCopy
0x1800a46c4  nop     dword ptr [rax+rax+00h]
0x1800a46c9  lea     rdx, [rbp+arg_0]; int *
0x1800a46cd  mov     [rbp+arg_0], eax
0x1800a46d0  lea     rcx, [rbp+var_40]; this
0x1800a46d4  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a46d9  test    eax, eax
0x1800a46db  jz      short loc_1800A472D
0x1800a46dd  test    byte ptr cs:_bidGblFlags, 2
0x1800a46e4  jz      short loc_1800A472D
0x1800a46e6  lea     rcx, [rbx+58h]; this
0x1800a46ea  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a46ef  cmp     eax, 0FFFFFFFFh
0x1800a46f2  jz      short loc_1800A470F
0x1800a46f4  lea     rcx, [rbx+58h]; this
0x1800a46f8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a46fd  mov     edx, 97C09h
0x1800a4702  mov     [rsp+70h+var_50], 25Fh
0x1800a470a  jmp     loc_1800A45D7
0x1800a470f  mov     r9d, 25Fh
0x1800a4715  mov     edx, 97C09h
0x1800a471a  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a4721  lea     r8, aCrecfieldGetUn; "<CRecField::get_UnderlyingValue|ADO|ERR"...
0x1800a4728  call    _bidTraceW
0x1800a472d  mov     ebx, [rbp+var_18]
0x1800a4730  lea     rcx, [rbp+var_40]; this
0x1800a4734  call    ??1CXLockContext@@QEAA@XZ; CXLockContext::~CXLockContext(void)
0x1800a4739  lea     r11, [rsp+70h+var_s0]
0x1800a473e  mov     eax, ebx
0x1800a4740  mov     rbx, [r11+18h]
0x1800a4744  mov     rdi, [r11+20h]
0x1800a4748  mov     rsp, r11
0x1800a474b  pop     rbp
0x1800a474c  retn
```
