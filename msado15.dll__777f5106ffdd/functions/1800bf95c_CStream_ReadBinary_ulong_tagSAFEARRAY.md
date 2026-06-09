# CStream::ReadBinary(ulong,tagSAFEARRAY * *)

- ea: `0x1800bf95c`
- end: `0x1800bfcf0`
- name: `?ReadBinary@CStream@@AEAAJKPEAPEAUtagSAFEARRAY@@@Z`
- size: `916`
- prototype: `__int64 __fastcall(CStream *__hidden this, unsigned int, struct tagSAFEARRAY **)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800bf180`
- `0x1800bf630`

## callees

- `0x180020e20`
- `0x180031760`
- `0x180032710`
- `0x18006a22c`
- `0x1800bf95c`
- `0x1800c8f34`
- `0x1800cdaea`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800bfb17`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800bfb17`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800bfcb6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800bfcb6`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800bfc3d`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800bfc3d`

## string_xrefs

- `0x1800bfa40`: `<CStream::ReadBinary|ADO|ERR> %u#, line %d\n`
- `0x1800bfc00`: `<CStream::ReadBinary|ADO|ERR> %u#, line %d\n`
- `0x1800bfa5c`: `<CStream::ReadBinary|ADO|ERR>  line %d\n`
- `0x1800bfca0`: `<CStream::ReadBinary|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStream::ReadBinary(CStream *this, unsigned int a2, struct tagSAFEARRAY **a3)
{
  unsigned __int64 v4; // rdi
  const char *v6; // r9
  unsigned int BidObjectID; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdx
  SAFEARRAY *v11; // rsi
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rdx
  unsigned int v16; // ebx
  int v18; // [rsp+20h] [rbp-89h]
  int v19; // [rsp+20h] [rbp-89h]
  int v20; // [rsp+30h] [rbp-79h] BYREF
  ULONG v21; // [rsp+34h] [rbp-75h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-71h] BYREF
  __int64 v23; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v24[40]; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v25; // [rsp+70h] [rbp-39h]
  _BYTE v26[16]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v27; // [rsp+90h] [rbp-19h]

  v4 = a2;
  v23 = 0;
  memset_0(v26, 0, 0x50u);
  rgsabound = 0;
  v21 = 0;
  CXLockContext::CXLockContext(
    (CXLockContext *)v24,
    (struct CStdComObjectRoot *)(((unsigned __int64)this + 32)
                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
    (struct CCriticalSection **)(*((_QWORD *)this + 18) + 8LL),
    v6);
  *a3 = 0;
  v20 = (*(__int64 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 1) + 72LL))((char *)this + 8, &v23);
  if ( !(unsigned int)CContext::Failed((CContext *)v24, &v20) )
  {
    v20 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(**((_QWORD **)this + 21) + 96LL))(
            *((_QWORD *)this + 21),
            v26,
            1);
    if ( (unsigned int)CContext::Failed((CContext *)v24, &v20) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_37;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
        v18 = 1927;
        v8 = 1973257;
        goto LABEL_5;
      }
      v9 = 1927;
      v10 = 1973257;
LABEL_7:
      bidTraceW(off_18012A210[0], v10, L"<CStream::ReadBinary|ADO|ERR>  line %d\n", v9);
      goto LABEL_37;
    }
    if ( v4 > v27 - v23 )
      LODWORD(v4) = v27 - v23;
    rgsabound.lLbound = 0;
    rgsabound.cElements = v4;
    v11 = SafeArrayCreate(0x11u, 1u, &rgsabound);
    if ( !v11 )
    {
      v20 = -2147024882;
      if ( (unsigned int)CContext::Failed((CContext *)v24, &v20) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_37;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v18 = 1952;
          v8 = 1998857;
          goto LABEL_5;
        }
        v9 = 1952;
        v10 = 1998857;
        goto LABEL_7;
      }
    }
    if ( (_DWORD)v4 )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD, PVOID, _QWORD, ULONG *))(**((_QWORD **)this + 21) + 24LL))(
              *((_QWORD *)this + 21),
              v11->pvData,
              (unsigned int)v4,
              &v21);
      if ( (unsigned int)CContext::Failed((CContext *)v24, &v20) )
      {
        if ( (bidGblFlags & 2) == 0 )
        {
LABEL_35:
          SafeArrayDestroy(v11);
          goto LABEL_37;
        }
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
        {
          v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
          v19 = 1957;
          v13 = 2003977;
LABEL_26:
          bidTraceW(off_18012A210[0], v13, L"<CStream::ReadBinary|ADO|ERR> %u#, line %d\n", v12, v19);
          goto LABEL_35;
        }
        v14 = 1957;
        v15 = 2003977;
        goto LABEL_34;
      }
      if ( (_DWORD)v4 != v21 )
      {
        rgsabound.cElements = v21;
        v20 = SafeArrayRedim(v11, &rgsabound);
        if ( (unsigned int)CContext::Failed((CContext *)v24, &v20) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_35;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
          {
            v12 = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
            v19 = 1961;
            v13 = 2008073;
            goto LABEL_26;
          }
          v14 = 1961;
          v15 = 2008073;
LABEL_34:
          bidTraceW(off_18012A210[0], v15, L"<CStream::ReadBinary|ADO|ERR>  line %d\n", v14);
          goto LABEL_35;
        }
      }
    }
    *a3 = v11;
    goto LABEL_37;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CStream *)((char *)this + 152));
      v18 = 1926;
      v8 = 1972233;
LABEL_5:
      bidTraceW(off_18012A210[0], v8, L"<CStream::ReadBinary|ADO|ERR> %u#, line %d\n", BidObjectID, v18);
      goto LABEL_37;
    }
    v9 = 1926;
    v10 = 1972233;
    goto LABEL_7;
  }
LABEL_37:
  v16 = v25;
  CXLockContext::~CXLockContext((CXLockContext *)v24);
  return v16;
}

```

## disassembly

```asm
0x1800bf95c  push    rbp
0x1800bf95e  push    rbx
0x1800bf95f  push    rsi
0x1800bf960  push    rdi
0x1800bf961  push    r14
0x1800bf963  lea     rbp, [rsp-37h]
0x1800bf968  sub     rsp, 0E0h
0x1800bf96f  mov     rax, cs:__security_cookie
0x1800bf976  xor     rax, rsp
0x1800bf979  mov     [rbp+57h+var_30], rax
0x1800bf97d  mov     r14, r8
0x1800bf980  mov     edi, edx
0x1800bf982  mov     rbx, rcx
0x1800bf985  mov     [rbp+57h+var_C0], 0
0x1800bf98d  xor     edx, edx; Val
0x1800bf98f  lea     r8d, [rdx+50h]; Size
0x1800bf993  lea     rcx, [rbp+57h+var_80]; void *
0x1800bf997  call    memset_0
0x1800bf99c  mov     qword ptr [rbp+57h+rgsabound.cElements], 0
0x1800bf9a4  mov     [rbp+57h+var_CC], 0
0x1800bf9ab  mov     r8, [rbx+90h]
0x1800bf9b2  add     r8, 8; struct CCriticalSection **
0x1800bf9b6  mov     rax, rbx
0x1800bf9b9  lea     rcx, [rbx+20h]
0x1800bf9bd  neg     rax
0x1800bf9c0  sbb     rdx, rdx
0x1800bf9c3  and     rdx, rcx; struct CStdComObjectRoot *
0x1800bf9c6  lea     rcx, [rbp+57h+var_B8]; this
0x1800bf9ca  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800bf9cf  nop
0x1800bf9d0  mov     qword ptr [r14], 0
0x1800bf9d7  lea     rcx, [rbx+8]
0x1800bf9db  mov     rax, [rcx]
0x1800bf9de  lea     rdx, [rbp+57h+var_C0]
0x1800bf9e2  mov     rax, [rax+48h]
0x1800bf9e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf9eb  mov     [rbp+57h+var_D0], eax
0x1800bf9ee  lea     rdx, [rbp+57h+var_D0]; int *
0x1800bf9f2  lea     rcx, [rbp+57h+var_B8]; this
0x1800bf9f6  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bf9fb  test    eax, eax
0x1800bf9fd  jz      short loc_1800BFA74
0x1800bf9ff  test    byte ptr cs:_bidGblFlags, 2
0x1800bfa06  jz      loc_1800BFCC7
0x1800bfa0c  lea     rcx, [rbx+98h]; this
0x1800bfa13  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfa18  cmp     eax, 0FFFFFFFFh
0x1800bfa1b  jz      short loc_1800BFA51
0x1800bfa1d  lea     rcx, [rbx+98h]; this
0x1800bfa24  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfa29  mov     [rsp+100h+var_E0], 786h
0x1800bfa31  mov     edx, 1E1809h
0x1800bfa36  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800bfa3d  mov     r9d, eax
0x1800bfa40  lea     r8, aCstreamReadbin_0; "<CStream::ReadBinary|ADO|ERR> %u#, line"...
0x1800bfa47  call    _bidTraceW
0x1800bfa4c  jmp     loc_1800BFCC7
0x1800bfa51  mov     r9d, 786h
0x1800bfa57  mov     edx, 1E1809h
0x1800bfa5c  lea     r8, aCstreamReadbin; "<CStream::ReadBinary|ADO|ERR>  line %d"...
0x1800bfa63  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800bfa6a  call    _bidTraceW
0x1800bfa6f  jmp     loc_1800BFCC7
0x1800bfa74  mov     rcx, [rbx+0A8h]
0x1800bfa7b  mov     rax, [rcx]
0x1800bfa7e  mov     esi, 1
0x1800bfa83  mov     r8d, esi
0x1800bfa86  lea     rdx, [rbp+57h+var_80]
0x1800bfa8a  mov     rax, [rax+60h]
0x1800bfa8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfa93  mov     [rbp+57h+var_D0], eax
0x1800bfa96  lea     rdx, [rbp+57h+var_D0]; int *
0x1800bfa9a  lea     rcx, [rbp+57h+var_B8]; this
0x1800bfa9e  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bfaa3  test    eax, eax
0x1800bfaa5  jz      short loc_1800BFAF3
0x1800bfaa7  test    byte ptr cs:_bidGblFlags, 2
0x1800bfaae  jz      loc_1800BFCC7
0x1800bfab4  lea     rcx, [rbx+98h]; this
0x1800bfabb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfac0  cmp     eax, 0FFFFFFFFh
0x1800bfac3  jz      short loc_1800BFAE3
0x1800bfac5  lea     rcx, [rbx+98h]; this
0x1800bfacc  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfad1  mov     [rsp+100h+var_E0], 787h
0x1800bfad9  mov     edx, 1E1C09h
0x1800bfade  jmp     loc_1800BFA36
0x1800bfae3  mov     r9d, 787h
0x1800bfae9  mov     edx, 1E1C09h
0x1800bfaee  jmp     loc_1800BFA5C
0x1800bfaf3  mov     rcx, [rbp+57h+var_70]
0x1800bfaf7  sub     rcx, [rbp+57h+var_C0]
0x1800bfafb  cmp     rdi, rcx
0x1800bfafe  jbe     short loc_1800BFB02
0x1800bfb00  mov     edi, ecx
0x1800bfb02  mov     [rbp+57h+rgsabound.lLbound], 0
0x1800bfb09  mov     [rbp+57h+rgsabound.cElements], edi
0x1800bfb0c  mov     ecx, 11h; vt
0x1800bfb11  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1800bfb15  mov     edx, esi; cDims
0x1800bfb17  call    cs:__imp_SafeArrayCreate
0x1800bfb1e  nop     dword ptr [rax+rax+00h]
0x1800bfb23  mov     rsi, rax
0x1800bfb26  test    rax, rax
0x1800bfb29  jnz     short loc_1800BFB8F
0x1800bfb2b  mov     [rbp+57h+var_D0], 8007000Eh
0x1800bfb32  lea     rdx, [rbp+57h+var_D0]; int *
0x1800bfb36  lea     rcx, [rbp+57h+var_B8]; this
0x1800bfb3a  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bfb3f  test    eax, eax
0x1800bfb41  jz      short loc_1800BFB8F
0x1800bfb43  test    byte ptr cs:_bidGblFlags, 2
0x1800bfb4a  jz      loc_1800BFCC7
0x1800bfb50  lea     rcx, [rbx+98h]; this
0x1800bfb57  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfb5c  cmp     eax, 0FFFFFFFFh
0x1800bfb5f  jz      short loc_1800BFB7F
0x1800bfb61  lea     rcx, [rbx+98h]; this
0x1800bfb68  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfb6d  mov     [rsp+100h+var_E0], 7A0h
0x1800bfb75  mov     edx, 1E8009h
0x1800bfb7a  jmp     loc_1800BFA36
0x1800bfb7f  mov     r9d, 7A0h
0x1800bfb85  mov     edx, 1E8009h
0x1800bfb8a  jmp     loc_1800BFA5C
0x1800bfb8f  test    edi, edi
0x1800bfb91  jz      loc_1800BFCC4
0x1800bfb97  mov     rcx, [rbx+0A8h]
0x1800bfb9e  mov     rax, [rcx]
0x1800bfba1  lea     r9, [rbp+57h+var_CC]
0x1800bfba5  mov     r8d, edi
0x1800bfba8  mov     rdx, [rsi+10h]
0x1800bfbac  mov     rax, [rax+18h]
0x1800bfbb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfbb5  mov     [rbp+57h+var_D0], eax
0x1800bfbb8  lea     rdx, [rbp+57h+var_D0]; int *
0x1800bfbbc  lea     rcx, [rbp+57h+var_B8]; this
0x1800bfbc0  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bfbc5  test    eax, eax
0x1800bfbc7  jz      short loc_1800BFC28
0x1800bfbc9  test    byte ptr cs:_bidGblFlags, 2
0x1800bfbd0  jz      loc_1800BFCB3
0x1800bfbd6  lea     rcx, [rbx+98h]; this
0x1800bfbdd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfbe2  cmp     eax, 0FFFFFFFFh
0x1800bfbe5  jz      short loc_1800BFC1B
0x1800bfbe7  lea     rcx, [rbx+98h]; this
0x1800bfbee  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfbf3  mov     [rsp+100h+var_E0], 7A5h
0x1800bfbfb  mov     edx, 1E9409h
0x1800bfc00  lea     r8, aCstreamReadbin_0; "<CStream::ReadBinary|ADO|ERR> %u#, line"...
0x1800bfc07  mov     r9d, eax
0x1800bfc0a  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800bfc11  call    _bidTraceW
0x1800bfc16  jmp     loc_1800BFCB3
0x1800bfc1b  mov     r9d, 7A5h
0x1800bfc21  mov     edx, 1E9409h
0x1800bfc26  jmp     short loc_1800BFCA0
0x1800bfc28  mov     eax, [rbp+57h+var_CC]
0x1800bfc2b  cmp     edi, eax
0x1800bfc2d  jz      loc_1800BFCC4
0x1800bfc33  mov     [rbp+57h+rgsabound.cElements], eax
0x1800bfc36  lea     rdx, [rbp+57h+rgsabound]; psaboundNew
0x1800bfc3a  mov     rcx, rsi; psa
0x1800bfc3d  call    cs:__imp_SafeArrayRedim
0x1800bfc44  nop     dword ptr [rax+rax+00h]
0x1800bfc49  mov     [rbp+57h+var_D0], eax
0x1800bfc4c  lea     rdx, [rbp+57h+var_D0]; int *
0x1800bfc50  lea     rcx, [rbp+57h+var_B8]; this
0x1800bfc54  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800bfc59  test    eax, eax
0x1800bfc5b  jz      short loc_1800BFCC4
0x1800bfc5d  test    byte ptr cs:_bidGblFlags, 2
0x1800bfc64  jz      short loc_1800BFCB3
0x1800bfc66  lea     rcx, [rbx+98h]; this
0x1800bfc6d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfc72  cmp     eax, 0FFFFFFFFh
0x1800bfc75  jz      short loc_1800BFC95
0x1800bfc77  lea     rcx, [rbx+98h]; this
0x1800bfc7e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800bfc83  mov     [rsp+100h+var_E0], 7A9h
0x1800bfc8b  mov     edx, 1EA409h
0x1800bfc90  jmp     loc_1800BFC00
0x1800bfc95  mov     r9d, 7A9h
0x1800bfc9b  mov     edx, 1EA409h
0x1800bfca0  lea     r8, aCstreamReadbin; "<CStream::ReadBinary|ADO|ERR>  line %d"...
0x1800bfca7  mov     rcx, cs:off_18012A210; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800bfcae  call    _bidTraceW
0x1800bfcb3  mov     rcx, rsi; psa
0x1800bfcb6  call    cs:__imp_SafeArrayDestroy
0x1800bfcbd  nop     dword ptr [rax+rax+00h]
0x1800bfcc2  jmp     short loc_1800BFCC7
0x1800bfcc4  mov     [r14], rsi
0x1800bfcc7  mov     ebx, [rbp+57h+var_90]
0x1800bfcca  lea     rcx, [rbp+57h+var_B8]; this
0x1800bfcce  call    ??1CXLockContext@@QEAA@XZ; CXLockContext::~CXLockContext(void)
0x1800bfcd3  mov     eax, ebx
0x1800bfcd5  mov     rcx, [rbp+57h+var_30]
0x1800bfcd9  xor     rcx, rsp; StackCookie
0x1800bfcdc  call    __security_check_cookie
0x1800bfce1  add     rsp, 0E0h
0x1800bfce8  pop     r14
0x1800bfcea  pop     rdi
0x1800bfceb  pop     rsi
0x1800bfcec  pop     rbx
0x1800bfced  pop     rbp
0x1800bfcee  retn
```
