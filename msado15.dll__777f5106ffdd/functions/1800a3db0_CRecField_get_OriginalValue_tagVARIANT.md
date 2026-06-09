# CRecField::get_OriginalValue(tagVARIANT *)

- ea: `0x1800a3db0`
- end: `0x1800a3f31`
- name: `?get_OriginalValue@CRecField@@UEAAJPEAUtagVARIANT@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(CRecField *__hidden this, VARIANTARG *pvargDest)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800a3f40`

## callees

- `0x180018788`
- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x18006a22c`
- `0x18009f940`
- `0x1800a3db0`
- `0x1800c8f34`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800a3e67`
- `OLEAUT32!__imp_VariantInit` at `0x1800a3e67`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a3e99`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a3e99`

## pseudocode

```c
__int64 __fastcall CRecField::get_OriginalValue(CRecField *this, VARIANTARG *pvargDest)
{
  unsigned int BidObjectID; // eax
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-58h]
  _BYTE v12[40]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v13; // [rsp+58h] [rbp-20h]
  int v14; // [rsp+80h] [rbp+8h] BYREF

  CXLockContext::CXLockContext(
    (CXLockContext *)v12,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 8)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 8) + 8LL),
    (const char *)this + 8);
  if ( pvargDest || (v14 = -2146825287, !(unsigned int)CContext::Failed((CContext *)v12, &v14)) )
  {
    VariantInit(pvargDest);
    if ( (unsigned int)CRecField::IsPropReadable(this) )
    {
      CVar::UpdateVariant((CRecField *)((char *)this + 288));
      v14 = VariantCopy(pvargDest, (const VARIANTARG *)(v8 + 16));
      if ( (unsigned int)CContext::Failed((CContext *)v12, &v14) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
            v5 = 597001;
            v11 = 583;
            goto LABEL_6;
          }
          v6 = 583;
          v7 = 597001;
LABEL_14:
          bidTraceW(off_18012A200[0], v7, L"<CRecField::get_OriginalValue|ADO|ERR>  line %d\n", v6);
        }
      }
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecField *)((char *)this + 88));
      v5 = 589833;
      v11 = 576;
LABEL_6:
      bidTraceW(off_18012A200[0], v5, L"<CRecField::get_OriginalValue|ADO|ERR> %u#, line %d\n", BidObjectID, v11);
      goto LABEL_15;
    }
    v6 = 576;
    v7 = 589833;
    goto LABEL_14;
  }
LABEL_15:
  v9 = v13;
  CXLockContext::~CXLockContext((CXLockContext *)v12);
  return v9;
}

```

## disassembly

```asm
0x1800a3db0  mov     [rsp+arg_8], rbx
0x1800a3db5  push    rdi
0x1800a3db6  sub     rsp, 70h
0x1800a3dba  mov     r8, [rcx+40h]
0x1800a3dbe  lea     r9, [rcx+8]; char *
0x1800a3dc2  mov     rax, rcx
0x1800a3dc5  mov     rdi, rdx
0x1800a3dc8  add     r8, 8; struct CCriticalSection **
0x1800a3dcc  mov     rbx, rcx
0x1800a3dcf  neg     rax
0x1800a3dd2  lea     rcx, [rsp+78h+var_48]; this
0x1800a3dd7  sbb     rdx, rdx
0x1800a3dda  and     rdx, r9; struct CStdComObjectRoot *
0x1800a3ddd  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800a3de2  test    rdi, rdi
0x1800a3de5  jnz     short loc_1800A3E64
0x1800a3de7  lea     rdx, [rsp+78h+arg_0]; int *
0x1800a3def  mov     [rsp+78h+arg_0], 800A0BB9h
0x1800a3dfa  lea     rcx, [rsp+78h+var_48]; this
0x1800a3dff  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a3e04  test    eax, eax
0x1800a3e06  jz      short loc_1800A3E64
0x1800a3e08  test    byte ptr cs:_bidGblFlags, 2
0x1800a3e0f  jz      loc_1800A3F12
0x1800a3e15  lea     rcx, [rbx+58h]; this
0x1800a3e19  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a3e1e  cmp     eax, 0FFFFFFFFh
0x1800a3e21  jz      short loc_1800A3E54
0x1800a3e23  lea     rcx, [rbx+58h]; this
0x1800a3e27  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a3e2c  mov     edx, 90009h
0x1800a3e31  mov     [rsp+78h+var_58], 240h
0x1800a3e39  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a3e40  lea     r8, aCrecfieldGetOr_0; "<CRecField::get_OriginalValue|ADO|ERR> "...
0x1800a3e47  mov     r9d, eax
0x1800a3e4a  call    _bidTraceW
0x1800a3e4f  jmp     loc_1800A3F12
0x1800a3e54  mov     r9d, 240h
0x1800a3e5a  mov     edx, 90009h
0x1800a3e5f  jmp     loc_1800A3EFF
0x1800a3e64  mov     rcx, rdi; pvarg
0x1800a3e67  call    cs:__imp_VariantInit
0x1800a3e6e  nop     dword ptr [rax+rax+00h]
0x1800a3e73  mov     rcx, rbx; this
0x1800a3e76  call    ?IsPropReadable@CRecField@@AEAAHXZ; CRecField::IsPropReadable(void)
0x1800a3e7b  test    eax, eax
0x1800a3e7d  jz      loc_1800A3F12
0x1800a3e83  lea     r8, [rbx+120h]
0x1800a3e8a  mov     rcx, r8; this
0x1800a3e8d  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x1800a3e92  lea     rdx, [r8+10h]; pvargSrc
0x1800a3e96  mov     rcx, rdi; pvargDest
0x1800a3e99  call    cs:__imp_VariantCopy
0x1800a3ea0  nop     dword ptr [rax+rax+00h]
0x1800a3ea5  lea     rdx, [rsp+78h+arg_0]; int *
0x1800a3ead  mov     [rsp+78h+arg_0], eax
0x1800a3eb4  lea     rcx, [rsp+78h+var_48]; this
0x1800a3eb9  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a3ebe  test    eax, eax
0x1800a3ec0  jz      short loc_1800A3F12
0x1800a3ec2  test    byte ptr cs:_bidGblFlags, 2
0x1800a3ec9  jz      short loc_1800A3F12
0x1800a3ecb  lea     rcx, [rbx+58h]; this
0x1800a3ecf  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a3ed4  cmp     eax, 0FFFFFFFFh
0x1800a3ed7  jz      short loc_1800A3EF4
0x1800a3ed9  lea     rcx, [rbx+58h]; this
0x1800a3edd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a3ee2  mov     edx, 91C09h
0x1800a3ee7  mov     [rsp+78h+var_58], 247h
0x1800a3eef  jmp     loc_1800A3E39
0x1800a3ef4  mov     r9d, 247h
0x1800a3efa  mov     edx, 91C09h
0x1800a3eff  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a3f06  lea     r8, aCrecfieldGetOr; "<CRecField::get_OriginalValue|ADO|ERR> "...
0x1800a3f0d  call    _bidTraceW
0x1800a3f12  mov     ebx, [rsp+78h+var_20]
0x1800a3f16  lea     rcx, [rsp+78h+var_48]; this
0x1800a3f1b  call    ??1CXLockContext@@QEAA@XZ; CXLockContext::~CXLockContext(void)
0x1800a3f20  mov     eax, ebx
0x1800a3f22  mov     rbx, [rsp+78h+arg_8]
0x1800a3f2a  add     rsp, 70h
0x1800a3f2e  pop     rdi
0x1800a3f2f  retn
```
