# CParameters::Delete(tagVARIANT)

- ea: `0x180079720`
- end: `0x1800799b0`
- name: `?Delete@CParameters@@UEAAJUtagVARIANT@@@Z`
- size: `656`
- prototype: `__int64 __fastcall(CParameters *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800799c0`

## callees

- `0x180009240`
- `0x180012bb0`
- `0x180020e20`
- `0x180027790`
- `0x180042a04`
- `0x1800649c0`
- `0x18006a22c`
- `0x180079720`
- `0x180087114`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x1800797bc`
- `MSDART!UMSEnterCSWraper` at `0x1800797bc`
- `KERNEL32!LeaveCriticalSection` at `0x18007990a`
- `KERNEL32!LeaveCriticalSection` at `0x18007990a`

## string_xrefs

- `0x180079843`: `<CParameters::Delete|ADO|ERR> %u#, line %d\n`
- `0x180079869`: `<CParameters::Delete|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CParameters::Delete(CParameters *this, struct tagVARIANT *a2)
{
  CStdCollection *v2; // rsi
  unsigned int BidObjectID; // eax
  CStdCollection *v6; // rcx
  CCommand *v7; // rbx
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rdx
  char v12; // r15
  unsigned __int8 v13; // dl
  __int64 v14; // rcx
  unsigned int v15; // ebx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  __int64 v19; // [rsp+20h] [rbp-40h]
  _BYTE v20[32]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v21; // [rsp+50h] [rbp-10h]
  unsigned int v22; // [rsp+58h] [rbp-8h]
  int AvailableOutputParams; // [rsp+90h] [rbp+30h] BYREF
  __int64 v24; // [rsp+A0h] [rbp+40h] BYREF

  v2 = (CParameters *)((char *)this + 24);
  v21 = ((unsigned __int64)this + 24) & -(__int64)(this != 0);
  CContext::Init((CContext *)v20);
  v24 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012AA28[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
    bidScopeEnterW(&v24, off_18012AA28[0], BidObjectID, a2, v19);
  }
  v6 = (CStdCollection *)*((_QWORD *)v2 + 4);
  if ( v2 == v6 )
    v6 = 0;
  v7 = (CCommand *)(((unsigned __int64)v6 - 32) & -(__int64)(v6 != 0));
  UMSEnterCSWraper((char *)this + 144);
  if ( !v7 || *((_BYTE *)v7 + 544) != 1 )
  {
    AvailableOutputParams = CParameters::GetAvailableOutputParams(this);
    if ( (unsigned int)CContext::Failed((CContext *)v20, &AvailableOutputParams) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112)) != -1 )
        {
          v8 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
          v9 = 3816457;
          LODWORD(v19) = 3727;
LABEL_13:
          bidTraceW(off_18012A1D0[0], v9, L"<CParameters::Delete|ADO|ERR> %u#, line %d\n", v8, v19);
          goto LABEL_22;
        }
        v10 = 3727;
        v11 = 3816457;
        goto LABEL_15;
      }
    }
    else
    {
      v12 = *((_BYTE *)this + 128);
      *((_BYTE *)this + 128) = 1;
      AvailableOutputParams = CStdCollection::Delete(v2, a2);
      if ( !(unsigned int)CContext::Failed((CContext *)v20, &AvailableOutputParams) )
      {
        *((_BYTE *)this + 160) = 1;
        CCommand::SetCmdInputDirty(v7, v13);
        goto LABEL_22;
      }
      *((_BYTE *)this + 128) = v12;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112)) != -1 )
        {
          v8 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
          v9 = 3825673;
          LODWORD(v19) = 3736;
          goto LABEL_13;
        }
        v10 = 3736;
        v11 = 3825673;
LABEL_15:
        bidTraceW(off_18012A1D0[0], v11, L"<CParameters::Delete|ADO|ERR>  line %d\n", v10);
      }
    }
LABEL_22:
    v14 = *((_QWORD *)this + 18);
    --*(_DWORD *)(v14 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
    goto LABEL_23;
  }
  AvailableOutputParams = -2146824577;
  CContext::FailedPushWarning((CContext *)v20, &AvailableOutputParams);
LABEL_23:
  if ( (bidGblFlags & 2) != 0 && off_18012A468[0] )
  {
    v15 = v22;
    v16 = CBidGenericBase::GetBidObjectID((CParameters *)((char *)this + 112));
    LODWORD(v19) = v15;
    bidTraceW(off_18012A1D0[0], 3838976, off_18012A468[0], v16, v19);
  }
  if ( (bidGblFlags & 4) != 0 && v24 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v24);
  v17 = v22;
  CContext::~CContext((CContext *)v20);
  return v17;
}

```

## disassembly

```asm
0x180079720  mov     [rsp-28h+arg_8], rbx
0x180079725  mov     [rsp-28h+arg_18], rsi
0x18007972a  push    rbp
0x18007972b  push    rdi
0x18007972c  push    r12
0x18007972e  push    r14
0x180079730  push    r15
0x180079732  mov     rbp, rsp
0x180079735  sub     rsp, 60h
0x180079739  mov     rax, rcx
0x18007973c  lea     rsi, [rcx+18h]
0x180079740  neg     rax
0x180079743  mov     rdi, rcx
0x180079746  lea     rcx, [rbp+var_30]; this
0x18007974a  mov     r14, rdx
0x18007974d  sbb     r8, r8
0x180079750  and     r8, rsi
0x180079753  mov     [rbp+var_10], r8
0x180079757  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x18007975c  test    byte ptr cs:_bidGblFlags, 4
0x180079763  mov     [rbp+arg_10], 0FFFFFFFFFFFFFFFFh
0x18007976b  jz      short loc_180079798
0x18007976d  mov     rax, cs:off_18012AA28; "<CParameters::Delete|API|ADO> %u#, %p{V"...
0x180079774  test    rax, rax
0x180079777  jz      short loc_180079798
0x180079779  lea     rcx, [rdi+70h]; this
0x18007977d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180079782  mov     rdx, cs:off_18012AA28; "<CParameters::Delete|API|ADO> %u#, %p{V"...
0x180079789  lea     rcx, [rbp+arg_10]
0x18007978d  mov     r9, r14
0x180079790  mov     r8d, eax
0x180079793  call    _bidScopeEnterW
0x180079798  mov     rcx, [rsi+20h]
0x18007979c  lea     r12, [rdi+90h]
0x1800797a3  xor     eax, eax
0x1800797a5  cmp     rsi, rcx
0x1800797a8  cmovz   rcx, rax
0x1800797ac  lea     rax, [rcx-20h]
0x1800797b0  neg     rcx
0x1800797b3  mov     rcx, r12
0x1800797b6  sbb     rbx, rbx
0x1800797b9  and     rbx, rax
0x1800797bc  call    cs:__imp_UMSEnterCSWraper
0x1800797c3  nop     dword ptr [rax+rax+00h]
0x1800797c8  test    rbx, rbx
0x1800797cb  jz      short loc_1800797EF
0x1800797cd  cmp     byte ptr [rbx+220h], 1
0x1800797d4  jnz     short loc_1800797EF
0x1800797d6  lea     rdx, [rbp+arg_0]; int *
0x1800797da  mov     [rbp+arg_0], 800A0E7Fh
0x1800797e1  lea     rcx, [rbp+var_30]; this
0x1800797e5  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x1800797ea  jmp     loc_180079916
0x1800797ef  mov     rcx, rdi; this
0x1800797f2  call    ?GetAvailableOutputParams@CParameters@@QEAAJXZ; CParameters::GetAvailableOutputParams(void)
0x1800797f7  lea     rdx, [rbp+arg_0]; int *
0x1800797fb  mov     [rbp+arg_0], eax
0x1800797fe  lea     rcx, [rbp+var_30]; this
0x180079802  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180079807  test    eax, eax
0x180079809  jz      short loc_18007987A
0x18007980b  test    byte ptr cs:_bidGblFlags, 2
0x180079812  jz      loc_1800798FF
0x180079818  lea     rcx, [rdi+70h]; this
0x18007981c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180079821  cmp     eax, 0FFFFFFFFh
0x180079824  jz      short loc_180079857
0x180079826  lea     rcx, [rdi+70h]; this
0x18007982a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007982f  mov     edx, 3A3C09h
0x180079834  mov     [rsp+60h+var_40], 0E8Fh
0x18007983c  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180079843  lea     r8, aCparametersDel; "<CParameters::Delete|ADO|ERR> %u#, line"...
0x18007984a  mov     r9d, eax
0x18007984d  call    _bidTraceW
0x180079852  jmp     loc_1800798FF
0x180079857  mov     r9d, 0E8Fh
0x18007985d  mov     edx, 3A3C09h
0x180079862  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180079869  lea     r8, aCparametersDel_1; "<CParameters::Delete|ADO|ERR>  line %d"...
0x180079870  call    _bidTraceW
0x180079875  jmp     loc_1800798FF
0x18007987a  mov     r15b, [rdi+80h]
0x180079881  mov     rdx, r14; struct tagVARIANT *
0x180079884  mov     rcx, rsi; this
0x180079887  mov     byte ptr [rdi+80h], 1
0x18007988e  call    ?Delete@CStdCollection@@UEAAJAEAUtagVARIANT@@@Z; CStdCollection::Delete(tagVARIANT &)
0x180079893  lea     rdx, [rbp+arg_0]; int *
0x180079897  mov     [rbp+arg_0], eax
0x18007989a  lea     rcx, [rbp+var_30]; this
0x18007989e  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800798a3  test    eax, eax
0x1800798a5  jz      short loc_1800798F0
0x1800798a7  mov     [rdi+80h], r15b
0x1800798ae  test    byte ptr cs:_bidGblFlags, 2
0x1800798b5  jz      short loc_1800798FF
0x1800798b7  lea     rcx, [rdi+70h]; this
0x1800798bb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800798c0  cmp     eax, 0FFFFFFFFh
0x1800798c3  jz      short loc_1800798E0
0x1800798c5  lea     rcx, [rdi+70h]; this
0x1800798c9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800798ce  mov     edx, 3A6009h
0x1800798d3  mov     [rsp+60h+var_40], 0E98h
0x1800798db  jmp     loc_18007983C
0x1800798e0  mov     r9d, 0E98h
0x1800798e6  mov     edx, 3A6009h
0x1800798eb  jmp     loc_180079862
0x1800798f0  mov     rcx, rbx; this
0x1800798f3  mov     byte ptr [rdi+0A0h], 1
0x1800798fa  call    ?SetCmdInputDirty@CCommand@@QEAAXE@Z; CCommand::SetCmdInputDirty(uchar)
0x1800798ff  mov     rcx, [r12]
0x180079903  dec     dword ptr [rcx+30h]
0x180079906  add     rcx, 8; lpCriticalSection
0x18007990a  call    cs:__imp_LeaveCriticalSection
0x180079911  nop     dword ptr [rax+rax+00h]
0x180079916  test    byte ptr cs:_bidGblFlags, 2
0x18007991d  jz      short loc_180079956
0x18007991f  mov     rax, cs:off_18012A468; "<CParameters::Delete|API|ADO|RET> %u#, "...
0x180079926  test    rax, rax
0x180079929  jz      short loc_180079956
0x18007992b  mov     ebx, [rbp+var_8]
0x18007992e  lea     rcx, [rdi+70h]; this
0x180079932  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180079937  mov     r8, cs:off_18012A468; "<CParameters::Delete|API|ADO|RET> %u#, "...
0x18007993e  mov     r9d, eax
0x180079941  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180079948  mov     edx, 3A9400h
0x18007994d  mov     [rsp+60h+var_40], ebx
0x180079951  call    _bidTraceW
0x180079956  test    byte ptr cs:_bidGblFlags, 4
0x18007995d  jz      short loc_180079988
0x18007995f  cmp     [rbp+arg_10], 0FFFFFFFFFFFFFFFFh
0x180079964  jz      short loc_180079988
0x180079966  mov     rcx, cs:_bidID
0x18007996d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180079971  jz      short loc_180079988
0x180079973  mov     rax, cs:off_180121248
0x18007997a  lea     r9, [rbp+arg_10]
0x18007997e  xor     r8d, r8d
0x180079981  xor     edx, edx
0x180079983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079988  mov     ebx, [rbp+var_8]
0x18007998b  lea     rcx, [rbp+var_30]; this
0x18007998f  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x180079994  lea     r11, [rsp+60h+var_s0]
0x180079999  mov     eax, ebx
0x18007999b  mov     rbx, [r11+38h]
0x18007999f  mov     rsi, [r11+48h]
0x1800799a3  mov     rsp, r11
0x1800799a6  pop     r15
0x1800799a8  pop     r14
0x1800799aa  pop     r12
0x1800799ac  pop     rdi
0x1800799ad  pop     rbp
0x1800799ae  retn
```
