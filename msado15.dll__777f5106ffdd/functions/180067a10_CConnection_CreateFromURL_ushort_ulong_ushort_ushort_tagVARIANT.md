# CConnection::CreateFromURL(ushort *,ulong,ushort *,ushort *,tagVARIANT *)

- ea: `0x180067a10`
- end: `0x180067ff1`
- name: `?CreateFromURL@CConnection@@UEAAJPEAGK00PEAUtagVARIANT@@@Z`
- size: `1505`
- prototype: `__int64 __usercall@<rax>(CConnection *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned __int16 *@<r9>, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180009240`
- `0x180020e20`
- `0x180024d1c`
- `0x180027790`
- `0x18003d270`
- `0x180042a04`
- `0x180057bdc`
- `0x180067a10`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800ca824`
- `0x1800cd638`
- `0x1800cd800`
- `0x1800cd890`
- `0x1800cd920`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180067cc6`
- `MSDART!MpHeapAlloc` at `0x180067cc6`
- `OLEAUT32!__imp_VariantClear` at `0x180067afa`
- `OLEAUT32!__imp_VariantClear` at `0x180067afa`

## string_xrefs

- `0x180067ac0`: `<CConnection::CreateFromURL|ADO|ERR> %u#, line %d\n`
- `0x180067ae6`: `<CConnection::CreateFromURL|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CConnection::CreateFromURL(
        CConnection *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct tagVARIANT *pvarg)
{
  CAuthenticateInfo *v7; // rsi
  struct tagVARIANT *v10; // r14
  unsigned int BidObjectID; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  unsigned int v15; // r15d
  CAuthenticateInfo *v16; // rax
  CAuthenticateInfo *v17; // rdi
  __int64 v18; // rcx
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v22; // [rsp+20h] [rbp-69h]
  __int64 v23; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v24[32]; // [rsp+68h] [rbp-21h] BYREF
  unsigned __int64 v25; // [rsp+88h] [rbp-1h]
  unsigned int v26; // [rsp+90h] [rbp+7h]
  int v27; // [rsp+E0h] [rbp+57h] BYREF
  unsigned __int16 *v28; // [rsp+E8h] [rbp+5Fh]

  v28 = a2;
  v23 = 0;
  v7 = 0;
  v25 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  CContext::Init((CContext *)v24);
  v10 = pvarg;
  if ( pvarg )
  {
    LODWORD(pvarg) = VariantClear(pvarg);
    if ( (unsigned int)CContext::Failed((CContext *)v24, (const int *)&pvarg) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_65;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        v12 = 7579657;
        LODWORD(v22) = 7402;
        goto LABEL_5;
      }
      v13 = 7402;
      v14 = 7579657;
LABEL_7:
      bidTraceW(off_18012A1C0[0], v14, L"<CConnection::CreateFromURL|ADO|ERR>  line %d\n", v13);
      goto LABEL_65;
    }
    if ( *((_BYTE *)this + 1041) )
    {
      LODWORD(pvarg) = -2146824575;
LABEL_15:
      CContext::FailedPushWarning((CContext *)v24, (const int *)&pvarg);
      goto LABEL_69;
    }
    if ( CConnection::GetExecState(this) == 1 )
    {
      LODWORD(pvarg) = -2146824577;
      goto LABEL_15;
    }
    if ( (unsigned int)CContext::FailIfClosed((CContext *)v24, *((unsigned __int8 *)this + 390)) )
      goto LABEL_69;
    if ( (unsigned int)CContext::OpFailed((CContext *)v24, *((_QWORD *)this + 36) != 0) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_65;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        v12 = 7583753;
        LODWORD(v22) = 7406;
        goto LABEL_5;
      }
      v13 = 7406;
      v14 = 7583753;
      goto LABEL_7;
    }
    if ( !*((_QWORD *)this + 37) )
    {
      LODWORD(pvarg) = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))this + 36))(
                         *((_QWORD *)this + 36),
                         &IID_ICreateRow,
                         (char *)this + 296);
      if ( (unsigned int)CContext::Failed((CContext *)v24, (const int *)&pvarg) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_65;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          v12 = 7588873;
          LODWORD(v22) = 7411;
          goto LABEL_5;
        }
        v13 = 7411;
        v14 = 7588873;
        goto LABEL_7;
      }
    }
    v15 = a3 | 2;
    if ( (a3 & 0x6000000) == 0 )
      v15 = a3;
    v16 = (CAuthenticateInfo *)MpHeapAlloc(g_hHeapHandle, 10485760, 32);
    if ( v16 )
    {
      v7 = CAuthenticateInfo::CAuthenticateInfo(v16);
      v17 = v7;
      if ( v7 )
      {
LABEL_34:
        LODWORD(pvarg) = CAuthenticateInfo::PutUserID(v17, a4);
        if ( (unsigned int)CContext::Failed((CContext *)v24, (const int *)&pvarg) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_65;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            v12 = 7603209;
            LODWORD(v22) = 7425;
            goto LABEL_5;
          }
          v13 = 7425;
          v14 = 7603209;
          goto LABEL_7;
        }
        LODWORD(pvarg) = CAuthenticateInfo::PutPassword(v17, a5);
        if ( (unsigned int)CContext::Failed((CContext *)v24, (const int *)&pvarg) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_65;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            v12 = 7604233;
            LODWORD(v22) = 7426;
            goto LABEL_5;
          }
          v13 = 7426;
          v14 = 7604233;
          goto LABEL_7;
        }
        v18 = *((_QWORD *)this + 37);
        LODWORD(pvarg) = 0;
        v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, _QWORD, const GUID *, GUID *, CAuthenticateInfo *, _QWORD, struct tagVARIANT **, _QWORD, __int64 *))(*(_QWORD *)v18 + 24LL))(
                v18,
                0,
                v28,
                v15,
                &DBGUID_ROW,
                &IID_IRow,
                v17,
                0,
                &pvarg,
                0,
                &v23);
        if ( v27 == 265946 )
        {
          v19 = MapOLEDBStatusToADOErrorDirect(
                  (unsigned int)pvarg,
                  (const struct OLEDBStatusMap *)&g_BindResourceStatusMap);
          if ( v19 != -2147217887 )
          {
            v27 = v19;
            if ( v23 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
              v23 = 0;
            }
          }
        }
        if ( (unsigned int)CContext::Failed((CContext *)v24, &v27) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_65;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            v12 = 7620617;
            LODWORD(v22) = 7442;
            goto LABEL_5;
          }
          v13 = 7442;
          v14 = 7620617;
          goto LABEL_7;
        }
        LODWORD(pvarg) = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))v23)(
                           v23,
                           &IID_IUnknown,
                           (__int64)&v10->llVal);
        if ( !(unsigned int)CContext::Failed((CContext *)v24, (const int *)&pvarg) )
        {
          v10->vt = 13;
          goto LABEL_65;
        }
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            v12 = 7622665;
            LODWORD(v22) = 7444;
            goto LABEL_5;
          }
          v13 = 7444;
          v14 = 7622665;
          goto LABEL_7;
        }
        goto LABEL_65;
      }
    }
    else
    {
      v17 = 0;
    }
    LODWORD(pvarg) = -2147024882;
    if ( (unsigned int)CContext::Failed((CContext *)v24, (const int *)&pvarg) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_65;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        v12 = 7601161;
        LODWORD(v22) = 7423;
        goto LABEL_5;
      }
      v13 = 7423;
      v14 = 7601161;
      goto LABEL_7;
    }
    goto LABEL_34;
  }
  LODWORD(pvarg) = -2146825287;
  CContext::FailedPushWarning((CContext *)v24, (const int *)&pvarg);
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      v12 = 7577609;
      LODWORD(v22) = 7400;
LABEL_5:
      bidTraceW(off_18012A1C0[0], v12, L"<CConnection::CreateFromURL|ADO|ERR> %u#, line %d\n", BidObjectID, v22);
      goto LABEL_65;
    }
    v13 = 7400;
    v14 = 7577609;
    goto LABEL_7;
  }
LABEL_65:
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v7 )
    CAuthenticateInfo::Release(v7);
LABEL_69:
  v20 = v26;
  CContext::~CContext((CContext *)v24);
  return v20;
}

```

## disassembly

```asm
0x180067a10  mov     [rsp-8+arg_10], rbx
0x180067a15  mov     [rsp-8+arg_8], rdx
0x180067a1a  push    rbp
0x180067a1b  push    rsi
0x180067a1c  push    rdi
0x180067a1d  push    r12
0x180067a1f  push    r13
0x180067a21  push    r14
0x180067a23  push    r15
0x180067a25  lea     rbp, [rsp-17h]
0x180067a2a  sub     rsp, 0A0h
0x180067a31  mov     rax, rcx
0x180067a34  mov     [rbp+47h+var_70], 0
0x180067a3c  lea     r11, [rcx+20h]
0x180067a40  mov     rbx, rcx
0x180067a43  xor     esi, esi
0x180067a45  lea     rcx, [rbp+47h+var_68]; this
0x180067a49  neg     rax
0x180067a4c  mov     r13, r9
0x180067a4f  mov     edi, r8d
0x180067a52  sbb     r10, r10
0x180067a55  and     r10, r11
0x180067a58  mov     [rbp+47h+var_48], r10
0x180067a5c  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x180067a61  mov     r14, [rbp+47h+pvarg]
0x180067a65  test    r14, r14
0x180067a68  jnz     loc_180067AF7
0x180067a6e  lea     rdx, [rbp+47h+pvarg]; int *
0x180067a72  mov     dword ptr [rbp+47h+pvarg], 800A0BB9h
0x180067a79  lea     rcx, [rbp+47h+var_68]; this
0x180067a7d  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x180067a82  test    byte ptr cs:_bidGblFlags, 2
0x180067a89  jz      loc_180067F9D
0x180067a8f  lea     rcx, [rbx+100h]; this
0x180067a96  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067a9b  cmp     eax, 0FFFFFFFFh
0x180067a9e  jz      short loc_180067AD4
0x180067aa0  lea     rcx, [rbx+100h]; this
0x180067aa7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067aac  mov     edx, 73A009h
0x180067ab1  mov     dword ptr [rsp+0D0h+var_B0], 1CE8h
0x180067ab9  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180067ac0  lea     r8, aCconnectionCre; "<CConnection::CreateFromURL|ADO|ERR> %u"...
0x180067ac7  mov     r9d, eax
0x180067aca  call    _bidTraceW
0x180067acf  jmp     loc_180067F9D
0x180067ad4  mov     r9d, 1CE8h
0x180067ada  mov     edx, 73A009h
0x180067adf  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180067ae6  lea     r8, aCconnectionCre_0; "<CConnection::CreateFromURL|ADO|ERR>  l"...
0x180067aed  call    _bidTraceW
0x180067af2  jmp     loc_180067F9D
0x180067af7  mov     rcx, r14; pvarg
0x180067afa  call    cs:__imp_VariantClear
0x180067b01  nop     dword ptr [rax+rax+00h]
0x180067b06  lea     rdx, [rbp+47h+pvarg]; int *
0x180067b0a  mov     dword ptr [rbp+47h+pvarg], eax
0x180067b0d  lea     rcx, [rbp+47h+var_68]; this
0x180067b11  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180067b16  test    eax, eax
0x180067b18  jz      short loc_180067B66
0x180067b1a  test    byte ptr cs:_bidGblFlags, 2
0x180067b21  jz      loc_180067F9D
0x180067b27  lea     rcx, [rbx+100h]; this
0x180067b2e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067b33  cmp     eax, 0FFFFFFFFh
0x180067b36  jz      short loc_180067B56
0x180067b38  lea     rcx, [rbx+100h]; this
0x180067b3f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067b44  mov     edx, 73A809h
0x180067b49  mov     dword ptr [rsp+0D0h+var_B0], 1CEAh
0x180067b51  jmp     loc_180067AB9
0x180067b56  mov     r9d, 1CEAh
0x180067b5c  mov     edx, 73A809h
0x180067b61  jmp     loc_180067ADF
0x180067b66  cmp     [rbx+411h], sil
0x180067b6d  jz      short loc_180067B88
0x180067b6f  mov     dword ptr [rbp+47h+pvarg], 800A0E81h
0x180067b76  lea     rcx, [rbp+47h+var_68]; this
0x180067b7a  lea     rdx, [rbp+47h+pvarg]; int *
0x180067b7e  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x180067b83  jmp     loc_180067FC7
0x180067b88  mov     rcx, rbx; this
0x180067b8b  call    ?GetExecState@CConnection@@QEAADXZ; CConnection::GetExecState(void)
0x180067b90  lea     rcx, [rbp+47h+var_68]; this
0x180067b94  cmp     al, 1
0x180067b96  jnz     short loc_180067BA1
0x180067b98  mov     dword ptr [rbp+47h+pvarg], 800A0E7Fh
0x180067b9f  jmp     short loc_180067B7A
0x180067ba1  movzx   edx, byte ptr [rbx+186h]; int
0x180067ba8  call    ?FailIfClosed@CContext@@QEAAHH@Z; CContext::FailIfClosed(int)
0x180067bad  test    eax, eax
0x180067baf  jnz     loc_180067FC7
0x180067bb5  xor     edx, edx
0x180067bb7  lea     rcx, [rbp+47h+var_68]; this
0x180067bbb  cmp     [rbx+120h], rdx
0x180067bc2  setnz   dl; int
0x180067bc5  call    ?OpFailed@CContext@@QEAAHH@Z; CContext::OpFailed(int)
0x180067bca  test    eax, eax
0x180067bcc  jz      short loc_180067C1A
0x180067bce  test    byte ptr cs:_bidGblFlags, 2
0x180067bd5  jz      loc_180067F9D
0x180067bdb  lea     rcx, [rbx+100h]; this
0x180067be2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067be7  cmp     eax, 0FFFFFFFFh
0x180067bea  jz      short loc_180067C0A
0x180067bec  lea     rcx, [rbx+100h]; this
0x180067bf3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067bf8  mov     edx, 73B809h
0x180067bfd  mov     dword ptr [rsp+0D0h+var_B0], 1CEEh
0x180067c05  jmp     loc_180067AB9
0x180067c0a  mov     r9d, 1CEEh
0x180067c10  mov     edx, 73B809h
0x180067c15  jmp     loc_180067ADF
0x180067c1a  lea     r12, [rbx+128h]
0x180067c21  cmp     [r12], rsi
0x180067c25  jnz     short loc_180067CA3
0x180067c27  mov     rcx, [rbx+120h]
0x180067c2e  lea     rdx, IID_ICreateRow
0x180067c35  mov     r8, r12
0x180067c38  mov     rax, [rcx]
0x180067c3b  mov     rax, [rax]
0x180067c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c43  lea     rdx, [rbp+47h+pvarg]; int *
0x180067c47  mov     dword ptr [rbp+47h+pvarg], eax
0x180067c4a  lea     rcx, [rbp+47h+var_68]; this
0x180067c4e  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180067c53  test    eax, eax
0x180067c55  jz      short loc_180067CA3
0x180067c57  test    byte ptr cs:_bidGblFlags, 2
0x180067c5e  jz      loc_180067F9D
0x180067c64  lea     rcx, [rbx+100h]; this
0x180067c6b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067c70  cmp     eax, 0FFFFFFFFh
0x180067c73  jz      short loc_180067C93
0x180067c75  lea     rcx, [rbx+100h]; this
0x180067c7c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067c81  mov     edx, 73CC09h
0x180067c86  mov     dword ptr [rsp+0D0h+var_B0], 1CF3h
0x180067c8e  jmp     loc_180067AB9
0x180067c93  mov     r9d, 1CF3h
0x180067c99  mov     edx, 73CC09h
0x180067c9e  jmp     loc_180067ADF
0x180067ca3  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180067caa  mov     r15d, edi
0x180067cad  or      r15d, 2
0x180067cb1  mov     edx, 0A00000h
0x180067cb6  test    edi, 6000000h
0x180067cbc  mov     r8d, 20h ; ' '
0x180067cc2  cmovz   r15d, edi
0x180067cc6  call    cs:__imp_MpHeapAlloc
0x180067ccd  nop     dword ptr [rax+rax+00h]
0x180067cd2  test    rax, rax
0x180067cd5  jz      short loc_180067D50
0x180067cd7  mov     rcx, rax; this
0x180067cda  call    ??0CAuthenticateInfo@@QEAA@XZ; CAuthenticateInfo::CAuthenticateInfo(void)
0x180067cdf  mov     rsi, rax
0x180067ce2  mov     rdi, rax
0x180067ce5  test    rax, rax
0x180067ce8  jz      short loc_180067D52
0x180067cea  mov     rdx, r13; unsigned __int16 *
0x180067ced  mov     rcx, rdi; this
0x180067cf0  call    ?PutUserID@CAuthenticateInfo@@UEAAJPEAG@Z; CAuthenticateInfo::PutUserID(ushort *)
0x180067cf5  lea     rdx, [rbp+47h+pvarg]; int *
0x180067cf9  mov     dword ptr [rbp+47h+pvarg], eax
0x180067cfc  lea     rcx, [rbp+47h+var_68]; this
0x180067d00  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180067d05  xor     r13d, r13d
0x180067d08  test    eax, eax
0x180067d0a  jz      loc_180067DC6
0x180067d10  test    byte ptr cs:_bidGblFlags, 2
0x180067d17  jz      loc_180067F9D
0x180067d1d  lea     rcx, [rbx+100h]; this
0x180067d24  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067d29  cmp     eax, 0FFFFFFFFh
0x180067d2c  jz      loc_180067DB6
0x180067d32  lea     rcx, [rbx+100h]; this
0x180067d39  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067d3e  mov     edx, 740409h
0x180067d43  mov     dword ptr [rsp+0D0h+var_B0], 1D01h
0x180067d4b  jmp     loc_180067AB9
0x180067d50  xor     edi, edi
0x180067d52  lea     rdx, [rbp+47h+pvarg]; int *
0x180067d56  mov     dword ptr [rbp+47h+pvarg], 8007000Eh
0x180067d5d  lea     rcx, [rbp+47h+var_68]; this
0x180067d61  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180067d66  test    eax, eax
0x180067d68  jz      short loc_180067CEA
0x180067d6a  test    byte ptr cs:_bidGblFlags, 2
0x180067d71  jz      loc_180067F9D
0x180067d77  lea     rcx, [rbx+100h]; this
0x180067d7e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067d83  cmp     eax, 0FFFFFFFFh
0x180067d86  jz      short loc_180067DA6
0x180067d88  lea     rcx, [rbx+100h]; this
0x180067d8f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067d94  mov     edx, 73FC09h
0x180067d99  mov     dword ptr [rsp+0D0h+var_B0], 1CFFh
0x180067da1  jmp     loc_180067AB9
0x180067da6  mov     r9d, 1CFFh
0x180067dac  mov     edx, 73FC09h
0x180067db1  jmp     loc_180067ADF
0x180067db6  mov     r9d, 1D01h
0x180067dbc  mov     edx, 740409h
0x180067dc1  jmp     loc_180067ADF
0x180067dc6  mov     rdx, [rbp+47h+arg_20]; unsigned __int16 *
0x180067dca  mov     rcx, rdi; this
0x180067dcd  call    ?PutPassword@CAuthenticateInfo@@UEAAJPEAG@Z; CAuthenticateInfo::PutPassword(ushort *)
0x180067dd2  lea     rdx, [rbp+47h+pvarg]; int *
0x180067dd6  mov     dword ptr [rbp+47h+pvarg], eax
0x180067dd9  lea     rcx, [rbp+47h+var_68]; this
0x180067ddd  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180067de2  test    eax, eax
0x180067de4  jz      short loc_180067E32
0x180067de6  test    byte ptr cs:_bidGblFlags, 2
0x180067ded  jz      loc_180067F9D
0x180067df3  lea     rcx, [rbx+100h]; this
0x180067dfa  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067dff  cmp     eax, 0FFFFFFFFh
0x180067e02  jz      short loc_180067E22
0x180067e04  lea     rcx, [rbx+100h]; this
0x180067e0b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067e10  mov     edx, 740809h
0x180067e15  mov     dword ptr [rsp+0D0h+var_B0], 1D02h
0x180067e1d  jmp     loc_180067AB9
0x180067e22  mov     r9d, 1D02h
0x180067e28  mov     edx, 740809h
0x180067e2d  jmp     loc_180067ADF
0x180067e32  mov     rcx, [r12]
0x180067e36  lea     rdx, [rbp+47h+var_70]
0x180067e3a  mov     r8, [rbp+47h+arg_8]
0x180067e3e  mov     r9d, r15d
0x180067e41  mov     [rsp+0D0h+var_80], rdx
0x180067e46  lea     rdx, [rbp+47h+pvarg]
0x180067e4a  mov     [rsp+0D0h+var_88], r13
0x180067e4f  mov     [rsp+0D0h+var_90], rdx
0x180067e54  lea     rdx, IID_IRow
0x180067e5b  mov     [rsp+0D0h+var_98], r13
0x180067e60  mov     dword ptr [rbp+47h+pvarg], r13d
0x180067e64  mov     rax, [rcx]
0x180067e67  mov     [rsp+0D0h+var_A0], rdi
0x180067e6c  mov     [rsp+0D0h+var_A8], rdx
0x180067e71  lea     rdx, DBGUID_ROW
0x180067e78  mov     [rsp+0D0h+var_B0], rdx
0x180067e7d  xor     edx, edx
0x180067e7f  mov     rax, [rax+18h]
0x180067e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e88  mov     [rbp+47h+arg_0], eax
0x180067e8b  cmp     eax, 40EDAh
0x180067e90  jnz     short loc_180067EC4
0x180067e92  mov     ecx, dword ptr [rbp+47h+pvarg]; unsigned int
0x180067e95  lea     rdx, ?g_BindResourceStatusMap@@3QBUOLEDBStatusMap@@B; struct OLEDBStatusMap *
0x180067e9c  call    ?MapOLEDBStatusToADOErrorDirect@@YAJKPEBUOLEDBStatusMap@@@Z; MapOLEDBStatusToADOErrorDirect(ulong,OLEDBStatusMap const *)
0x180067ea1  cmp     eax, 80040E21h
0x180067ea6  jz      short loc_180067EC4
0x180067ea8  mov     rcx, [rbp+47h+var_70]
0x180067eac  mov     [rbp+47h+arg_0], eax
0x180067eaf  test    rcx, rcx
0x180067eb2  jz      short loc_180067EC4
0x180067eb4  mov     rax, [rcx]
0x180067eb7  mov     rax, [rax+10h]
0x180067ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ec0  mov     [rbp+47h+var_70], r13
0x180067ec4  lea     rdx, [rbp+47h+arg_0]; int *
0x180067ec8  lea     rcx, [rbp+47h+var_68]; this
0x180067ecc  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180067ed1  test    eax, eax
0x180067ed3  jz      short loc_180067F21
0x180067ed5  test    byte ptr cs:_bidGblFlags, 2
0x180067edc  jz      loc_180067F9D
0x180067ee2  lea     rcx, [rbx+100h]; this
0x180067ee9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067eee  cmp     eax, 0FFFFFFFFh
0x180067ef1  jz      short loc_180067F11
0x180067ef3  lea     rcx, [rbx+100h]; this
0x180067efa  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067eff  mov     edx, 744809h
0x180067f04  mov     dword ptr [rsp+0D0h+var_B0], 1D12h
0x180067f0c  jmp     loc_180067AB9
0x180067f11  mov     r9d, 1D12h
0x180067f17  mov     edx, 744809h
0x180067f1c  jmp     loc_180067ADF
0x180067f21  mov     rcx, [rbp+47h+var_70]
0x180067f25  lea     r8, [r14+8]
0x180067f29  lea     rdx, IID_IUnknown
0x180067f30  mov     rax, [rcx]
0x180067f33  mov     rax, [rax]
0x180067f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f3b  lea     rdx, [rbp+47h+pvarg]; int *
0x180067f3f  mov     dword ptr [rbp+47h+pvarg], eax
0x180067f42  lea     rcx, [rbp+47h+var_68]; this
0x180067f46  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180067f4b  test    eax, eax
0x180067f4d  jz      short loc_180067F97
0x180067f4f  test    byte ptr cs:_bidGblFlags, 2
0x180067f56  jz      short loc_180067F9D
0x180067f58  lea     rcx, [rbx+100h]; this
0x180067f5f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180067f64  cmp     eax, 0FFFFFFFFh
0x180067f67  jz      short loc_180067F87
  ... truncated ...
```
