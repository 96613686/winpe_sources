# CRecordset::FieldListToAccessor(unsigned __int64,CRsetField * * const,unsigned __int64 *,bool)

- ea: `0x180031a90`
- end: `0x180031f89`
- name: `?FieldListToAccessor@CRecordset@@AEAAJ_KQEAPEAVCRsetField@@PEA_K_N@Z`
- size: `1273`
- prototype: `int(CRecordset *__hidden this, unsigned __int64, struct CRsetField **const, unsigned __int64 *, bool)`
- caller_count: `5`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x180002990`
- `0x18001cc80`
- `0x18002e050`
- `0x18002f5e0`
- `0x1800af92c`

## callees

- `0x180009240`
- `0x18000cd80`
- `0x18000d0e0`
- `0x180011530`
- `0x180020e20`
- `0x180020fc0`
- `0x180027790`
- `0x18002ce00`
- `0x180031a90`
- `0x180042a04`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180031d01`
- `MSDART!MpHeapAlloc` at `0x180031d01`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180031ae9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180031ae9`
- `OLEAUT32!__imp_SysFreeString` at `0x180031cb8`
- `OLEAUT32!__imp_SysFreeString` at `0x180031f3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180031cb8`
- `OLEAUT32!__imp_SysFreeString` at `0x180031f3f`

## string_xrefs

- `0x180031b7e`: `<CRecordset::FieldListToAccessor|ADO|ERR> %u#, line %d\n`
- `0x180031eb5`: `<CRecordset::FieldListToAccessor|ADO|ERR> %u#, line %d\n`
- `0x180031b9a`: `<CRecordset::FieldListToAccessor|ADO|ERR>  line %d\n`
- `0x180031ece`: `<CRecordset::FieldListToAccessor|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRecordset::FieldListToAccessor(
        CRecordset *this,
        unsigned __int64 a2,
        struct CRsetField **const a3,
        unsigned __int64 *a4,
        bool a5)
{
  OLECHAR *v8; // rsi
  char v9; // bl
  int v10; // r14d
  unsigned int BidObjectID; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  unsigned __int64 v15; // rdx
  struct CRsetField **v16; // r9
  bool v17; // zf
  __int64 *v18; // rbx
  unsigned int v19; // edi
  __int64 v20; // rax
  _QWORD *v21; // r15
  __int64 v22; // rdx
  __int64 v23; // r10
  _QWORD *v24; // rcx
  unsigned __int64 v25; // r8
  struct CRsetField **v26; // rax
  struct CRsetField *v27; // r9
  __int64 *v28; // r12
  __int64 v29; // rax
  bool v30; // cf
  unsigned int v31; // eax
  int v33; // [rsp+20h] [rbp-60h]
  __int64 v34; // [rsp+20h] [rbp-60h]
  OLECHAR *v35; // [rsp+40h] [rbp-40h] BYREF
  char v36; // [rsp+48h] [rbp-38h]
  _BYTE v37[32]; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v38; // [rsp+70h] [rbp-10h]
  int v39; // [rsp+78h] [rbp-8h]
  int v40; // [rsp+C0h] [rbp+40h] BYREF
  __int64 *v41; // [rsp+C8h] [rbp+48h] BYREF
  struct CRsetField **v42; // [rsp+D0h] [rbp+50h]

  v42 = a3;
  v38 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  CContext::Init((CContext *)v37);
  v41 = 0;
  if ( (_DWORD)a2 == -1 )
  {
    v8 = 0;
    v35 = 0;
    v9 = 7;
  }
  else
  {
    v8 = SysAllocStringLen(0, (int)a2 + 1);
    v35 = v8;
    v9 = v8 != 0 ? 7 : 3;
  }
  v36 = v9;
  v10 = v9 & 4;
  if ( (v9 & 4) == 0 )
  {
    v40 = -2147024882;
    if ( (unsigned int)CContext::FailedPushWarning((CContext *)v37, &v40) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v33 = 11756;
          v12 = 12038153;
LABEL_9:
          bidTraceW(
            off_18012A208[0],
            v12,
            L"<CRecordset::FieldListToAccessor|ADO|ERR> %u#, line %d\n",
            BidObjectID,
            v33);
          goto LABEL_52;
        }
        v13 = 11756;
        v14 = 12038153;
        goto LABEL_11;
      }
LABEL_52:
      v19 = v39;
      if ( (v9 & 2) != 0 )
        SysFreeString(v8);
      if ( v41 )
        (*(void (__fastcall **)(__int64 *))(*v41 + 16))(v41);
      goto LABEL_56;
    }
  }
  if ( (int)CRsetOptionalInterface<IAccessor,&_GUID const IID_IAccessor>::GetInterface((char *)this + 336, &v41) < 0 )
  {
    v40 = -2146825037;
    if ( (unsigned int)CContext::Failed((CContext *)v37, &v40) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_52;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v33 = 11761;
        v12 = 12043273;
        goto LABEL_9;
      }
      v13 = 11761;
      v14 = 12043273;
LABEL_11:
      bidTraceW(off_18012A208[0], v14, L"<CRecordset::FieldListToAccessor|ADO|ERR>  line %d\n", v13);
      goto LABEL_52;
    }
  }
  *(_WORD *)((unsigned __int64)v8 & -(__int64)(v10 != 0)) = 65;
  v15 = 0;
  if ( a2 )
  {
    v16 = v42;
    do
    {
      *(_WORD *)(((unsigned __int64)v8 & -(__int64)(v10 != 0)) + 2 * v15 + 2) = *((_WORD *)v16[v15] + 52);
      ++v15;
    }
    while ( v15 < a2 );
  }
  if ( (v9 & 4) == 0 )
    goto LABEL_30;
  v39 = CCollectionMap::LookUp((CRecordset *)((char *)this + 1464), v8, a4);
  v17 = v39 == 0;
  if ( v39 < 0 )
  {
    CContext::PushError((CContext *)v37);
    v17 = v39 == 0;
  }
  if ( !v17 )
  {
LABEL_30:
    v20 = 88 * a2;
    if ( !is_mul_ok(a2, 0x58u) )
      v20 = -1;
    v21 = (_QWORD *)MpHeapAlloc(g_hHeapHandle, 10485760, v20);
    if ( v21 || (v40 = -2147024882, !(unsigned int)CContext::FailedPushWarning((CContext *)v37, &v40)) )
    {
      v22 = 0;
      v23 = 0;
      v24 = v21;
      v25 = 0;
      if ( a2 )
      {
        v26 = v42;
        do
        {
          v27 = v26[v25];
          if ( (*((_DWORD *)v27 + 33) & 0x2000) == 0 )
          {
            v24[9] = 24;
            *((_WORD *)v24 + 42) = 12;
            v24[1] = v22;
            v24[2] = 0;
            v24[3] = 0;
            *((_DWORD *)v24 + 14) = 1;
            *((_DWORD *)v24 + 16) = 0;
            *v24 = *((_QWORD *)v27 + 13);
            *((_DWORD *)v24 + 15) = 0;
            v24[4] = 0;
            v24[5] = 0;
            v24[6] = 0;
            *((_BYTE *)v24 + 86) = *((_BYTE *)v27 + 128);
            *((_BYTE *)v24 + 87) = *((_BYTE *)v27 + 129);
            *((_DWORD *)v24 + 20) = 0;
            v24 += 11;
            ++v23;
            v26 = v42;
          }
          v22 += 24;
          ++v25;
        }
        while ( v25 < a2 );
      }
      v28 = v41;
      v29 = *v41;
      v30 = a5;
      a5 = -a5;
      v39 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, _QWORD *, __int64, unsigned __int64 *, _QWORD))(v29 + 32))(
              v41,
              2,
              v23,
              v21,
              v22 & -(__int64)v30,
              a4,
              0);
      if ( v39 >= 0 )
      {
        if ( (v9 & 4) != 0 )
        {
          v40 = 0;
          (*(void (__fastcall **)(__int64 *, _QWORD, int *))(*v28 + 24))(v28, *a4, &v40);
          CCollectionMap::Insert((CRecordset *)((char *)this + 1464), (const struct CSysString *)&v35, *a4);
          v9 = v36;
          v8 = v35;
        }
      }
      else
      {
        CContext::PushError((CContext *)v37);
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
          {
            bidTraceW(off_18012A208[0], 12117001, L"<CRecordset::FieldListToAccessor|ADO|ERR>  line %d\n", 11833);
          }
          else
          {
            v31 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            LODWORD(v34) = 11833;
            bidTraceW(off_18012A208[0], 12117001, L"<CRecordset::FieldListToAccessor|ADO|ERR> %u#, line %d\n", v31, v34);
          }
        }
      }
      if ( v21 )
        operator delete(v21);
      goto LABEL_52;
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v33 = 11783;
        v12 = 12065801;
        goto LABEL_9;
      }
      v13 = 11783;
      v14 = 12065801;
      goto LABEL_11;
    }
    goto LABEL_52;
  }
  v40 = 0;
  v18 = v41;
  (*(void (__fastcall **)(__int64 *, _QWORD, int *))(*v41 + 24))(v41, *a4, &v40);
  v19 = v39;
  SysFreeString(v8);
  if ( v18 )
    (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
LABEL_56:
  CContext::~CContext((CContext *)v37);
  return v19;
}

```

## disassembly

```asm
0x180031a90  mov     [rsp-38h+arg_18], rbx
0x180031a95  mov     [rsp-38h+arg_10], r8
0x180031a9a  push    rbp
0x180031a9b  push    rsi
0x180031a9c  push    rdi
0x180031a9d  push    r12
0x180031a9f  push    r13
0x180031aa1  push    r14
0x180031aa3  push    r15
0x180031aa5  mov     rbp, rsp
0x180031aa8  sub     rsp, 80h
0x180031aaf  mov     r13, r9
0x180031ab2  mov     r12, rdx
0x180031ab5  mov     rdi, rcx
0x180031ab8  mov     rax, rcx
0x180031abb  lea     r11, [rcx+20h]
0x180031abf  neg     rax
0x180031ac2  sbb     r10, r10
0x180031ac5  and     r10, r11
0x180031ac8  mov     [rbp+var_10], r10
0x180031acc  lea     rcx, [rbp+var_30]; this
0x180031ad0  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x180031ad5  nop
0x180031ad6  mov     [rbp+arg_8], 0
0x180031ade  lea     edx, [r12+1]; ui
0x180031ae3  test    edx, edx
0x180031ae5  jz      short loc_180031B09
0x180031ae7  xor     ecx, ecx; strIn
0x180031ae9  call    cs:__imp_SysAllocStringLen
0x180031af0  nop     dword ptr [rax+rax+00h]
0x180031af5  mov     rsi, rax
0x180031af8  mov     [rbp+var_40], rax
0x180031afc  neg     rax
0x180031aff  sbb     bl, bl
0x180031b01  and     bl, 4
0x180031b04  add     bl, 3
0x180031b07  jmp     short loc_180031B11
0x180031b09  xor     esi, esi
0x180031b0b  mov     [rbp+var_40], rsi
0x180031b0f  mov     bl, 7
0x180031b11  mov     [rbp+var_38], bl
0x180031b14  movzx   r15d, bl
0x180031b18  mov     r14d, r15d
0x180031b1b  and     r14d, 4
0x180031b1f  jnz     loc_180031BB2
0x180031b25  mov     [rbp+arg_0], 8007000Eh
0x180031b2c  lea     rdx, [rbp+arg_0]; int *
0x180031b30  lea     rcx, [rbp+var_30]; this
0x180031b34  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x180031b39  test    eax, eax
0x180031b3b  jz      short loc_180031BB2
0x180031b3d  test    byte ptr cs:_bidGblFlags, 2
0x180031b44  jz      loc_180031F34
0x180031b4a  lea     rcx, [rdi+618h]; this
0x180031b51  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180031b56  cmp     eax, 0FFFFFFFFh
0x180031b59  jz      short loc_180031B8F
0x180031b5b  lea     rcx, [rdi+618h]; this
0x180031b62  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180031b67  mov     dword ptr [rsp+80h+var_60], 2DECh
0x180031b6f  mov     edx, 0B7B009h
0x180031b74  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180031b7b  mov     r9d, eax
0x180031b7e  lea     r8, aCrecordsetFiel; "<CRecordset::FieldListToAccessor|ADO|ER"...
0x180031b85  call    _bidTraceW
0x180031b8a  jmp     loc_180031F34
0x180031b8f  mov     r9d, 2DECh
0x180031b95  mov     edx, 0B7B009h
0x180031b9a  lea     r8, aCrecordsetFiel_0; "<CRecordset::FieldListToAccessor|ADO|ER"...
0x180031ba1  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180031ba8  call    _bidTraceW
0x180031bad  jmp     loc_180031F34
0x180031bb2  lea     rcx, [rdi+150h]
0x180031bb9  lea     rdx, [rbp+arg_8]
0x180031bbd  call    ?GetInterface@?$CRsetOptionalInterface@UIAccessor@@$1?IID_IAccessor@@3U_GUID@@B@@QEAAJPEAPEAUIAccessor@@@Z; CRsetOptionalInterface<IAccessor,&_GUID const IID_IAccessor>::GetInterface(IAccessor * *)
0x180031bc2  test    eax, eax
0x180031bc4  jns     short loc_180031C2A
0x180031bc6  mov     [rbp+arg_0], 800A0CB3h
0x180031bcd  lea     rdx, [rbp+arg_0]; int *
0x180031bd1  lea     rcx, [rbp+var_30]; this
0x180031bd5  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180031bda  test    eax, eax
0x180031bdc  jz      short loc_180031C2A
0x180031bde  test    byte ptr cs:_bidGblFlags, 2
0x180031be5  jz      loc_180031F34
0x180031beb  lea     rcx, [rdi+618h]; this
0x180031bf2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180031bf7  cmp     eax, 0FFFFFFFFh
0x180031bfa  jz      short loc_180031C1A
0x180031bfc  lea     rcx, [rdi+618h]; this
0x180031c03  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180031c08  mov     dword ptr [rsp+80h+var_60], 2DF1h
0x180031c10  mov     edx, 0B7C409h
0x180031c15  jmp     loc_180031B74
0x180031c1a  mov     r9d, 2DF1h
0x180031c20  mov     edx, 0B7C409h
0x180031c25  jmp     loc_180031B9A
0x180031c2a  mov     eax, r14d
0x180031c2d  neg     eax
0x180031c2f  sbb     r8, r8
0x180031c32  and     r8, rsi
0x180031c35  mov     word ptr [r8], 41h ; 'A'
0x180031c3b  xor     edx, edx
0x180031c3d  test    r12, r12
0x180031c40  jz      short loc_180031C5C
0x180031c42  mov     r9, [rbp+arg_10]
0x180031c46  mov     rax, [r9+rdx*8]
0x180031c4a  movzx   ecx, word ptr [rax+68h]
0x180031c4e  mov     [r8+rdx*2+2], cx
0x180031c54  inc     rdx
0x180031c57  cmp     rdx, r12
0x180031c5a  jb      short loc_180031C46
0x180031c5c  test    r14d, r14d
0x180031c5f  jz      short loc_180031CDF
0x180031c61  lea     rcx, [rdi+5B8h]; this
0x180031c68  mov     r8, r13; unsigned __int64 *
0x180031c6b  mov     rdx, rsi; unsigned __int16 *
0x180031c6e  call    ?LookUp@CCollectionMap@@QEAAJQEAGPEA_K@Z; CCollectionMap::LookUp(ushort * const,unsigned __int64 *)
0x180031c73  mov     [rbp+var_8], eax
0x180031c76  test    eax, eax
0x180031c78  jns     short loc_180031C88
0x180031c7a  lea     rcx, [rbp+var_30]; this
0x180031c7e  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180031c83  mov     eax, [rbp+var_8]
0x180031c86  test    eax, eax
0x180031c88  jnz     short loc_180031CDF
0x180031c8a  mov     [rbp+arg_0], 0
0x180031c91  mov     rbx, [rbp+arg_8]
0x180031c95  mov     rax, [rbx]
0x180031c98  lea     r8, [rbp+arg_0]
0x180031c9c  mov     rdx, [r13+0]
0x180031ca0  mov     rcx, rbx
0x180031ca3  mov     rax, [rax+18h]
0x180031ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031cac  mov     edi, [rbp+var_8]
0x180031caf  test    r15b, 2
0x180031cb3  jz      short loc_180031CC5
0x180031cb5  mov     rcx, rsi; bstrString
0x180031cb8  call    cs:__imp_SysFreeString
0x180031cbf  nop     dword ptr [rax+rax+00h]
0x180031cc4  nop
0x180031cc5  test    rbx, rbx
0x180031cc8  jz      short loc_180031CDA
0x180031cca  mov     rax, [rbx]
0x180031ccd  mov     rcx, rbx
0x180031cd0  mov     rax, [rax+10h]
0x180031cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031cd9  nop
0x180031cda  jmp     loc_180031F62
0x180031cdf  mov     eax, 58h ; 'X'
0x180031ce4  mul     r12
0x180031ce7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180031cee  cmovb   rax, rcx
0x180031cf2  mov     r8, rax
0x180031cf5  mov     edx, 0A00000h
0x180031cfa  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180031d01  call    cs:__imp_MpHeapAlloc
0x180031d08  nop     dword ptr [rax+rax+00h]
0x180031d0d  mov     r15, rax
0x180031d10  test    rax, rax
0x180031d13  jnz     short loc_180031D79
0x180031d15  mov     [rbp+arg_0], 8007000Eh
0x180031d1c  lea     rdx, [rbp+arg_0]; int *
0x180031d20  lea     rcx, [rbp+var_30]; this
0x180031d24  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x180031d29  test    eax, eax
0x180031d2b  jz      short loc_180031D79
0x180031d2d  test    byte ptr cs:_bidGblFlags, 2
0x180031d34  jz      loc_180031F34
0x180031d3a  lea     rcx, [rdi+618h]; this
0x180031d41  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180031d46  cmp     eax, 0FFFFFFFFh
0x180031d49  jz      short loc_180031D69
0x180031d4b  lea     rcx, [rdi+618h]; this
0x180031d52  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180031d57  mov     dword ptr [rsp+80h+var_60], 2E07h
0x180031d5f  mov     edx, 0B81C09h
0x180031d64  jmp     loc_180031B74
0x180031d69  mov     r9d, 2E07h
0x180031d6f  mov     edx, 0B81C09h
0x180031d74  jmp     loc_180031B9A
0x180031d79  xor     edx, edx
0x180031d7b  xor     r10d, r10d
0x180031d7e  mov     rcx, r15
0x180031d81  xor     r8d, r8d
0x180031d84  test    r12, r12
0x180031d87  jz      loc_180031E2E
0x180031d8d  mov     rax, [rbp+arg_10]
0x180031d91  mov     r9, [rax+r8*8]
0x180031d95  test    dword ptr [r9+84h], 2000h
0x180031da0  jnz     short loc_180031E1E
0x180031da2  mov     qword ptr [rcx+48h], 18h
0x180031daa  mov     word ptr [rcx+54h], 0Ch
0x180031db0  mov     [rcx+8], rdx
0x180031db4  mov     qword ptr [rcx+10h], 0
0x180031dbc  mov     qword ptr [rcx+18h], 0
0x180031dc4  mov     dword ptr [rcx+38h], 1
0x180031dcb  mov     dword ptr [rcx+40h], 0
0x180031dd2  mov     rax, [r9+68h]
0x180031dd6  mov     [rcx], rax
0x180031dd9  mov     dword ptr [rcx+3Ch], 0
0x180031de0  mov     qword ptr [rcx+20h], 0
0x180031de8  mov     qword ptr [rcx+28h], 0
0x180031df0  mov     qword ptr [rcx+30h], 0
0x180031df8  mov     al, [r9+80h]
0x180031dff  mov     [rcx+56h], al
0x180031e02  mov     al, [r9+81h]
0x180031e09  mov     [rcx+57h], al
0x180031e0c  mov     dword ptr [rcx+50h], 0
0x180031e13  add     rcx, 58h ; 'X'
0x180031e17  inc     r10
0x180031e1a  mov     rax, [rbp+arg_10]
0x180031e1e  add     rdx, 18h
0x180031e22  inc     r8
0x180031e25  cmp     r8, r12
0x180031e28  jb      loc_180031D91
0x180031e2e  mov     r12, [rbp+arg_8]
0x180031e32  mov     rax, [r12]
0x180031e36  neg     [rbp+arg_20]
0x180031e39  sbb     rcx, rcx
0x180031e3c  and     rcx, rdx
0x180031e3f  mov     [rsp+80h+var_50], 0
0x180031e48  mov     [rsp+80h+var_58], r13
0x180031e4d  mov     [rsp+80h+var_60], rcx
0x180031e52  mov     r9, r15
0x180031e55  mov     r8, r10
0x180031e58  mov     edx, 2
0x180031e5d  mov     rcx, r12
0x180031e60  mov     rax, [rax+20h]
0x180031e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e69  mov     [rbp+var_8], eax
0x180031e6c  test    eax, eax
0x180031e6e  jns     short loc_180031EE8
0x180031e70  lea     rcx, [rbp+var_30]; this
0x180031e74  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180031e79  test    byte ptr cs:_bidGblFlags, 2
0x180031e80  jz      loc_180031F27
0x180031e86  lea     rcx, [rdi+618h]; this
0x180031e8d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180031e92  cmp     eax, 0FFFFFFFFh
0x180031e95  jz      short loc_180031EC8
0x180031e97  lea     rcx, [rdi+618h]; this
0x180031e9e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180031ea3  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180031eaa  mov     dword ptr [rsp+80h+var_60], 2E39h
0x180031eb2  mov     r9d, eax
0x180031eb5  lea     r8, aCrecordsetFiel; "<CRecordset::FieldListToAccessor|ADO|ER"...
0x180031ebc  mov     edx, 0B8E409h
0x180031ec1  call    _bidTraceW
0x180031ec6  jmp     short loc_180031F27
0x180031ec8  mov     r9d, 2E39h
0x180031ece  lea     r8, aCrecordsetFiel_0; "<CRecordset::FieldListToAccessor|ADO|ER"...
0x180031ed5  mov     edx, 0B8E409h
0x180031eda  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180031ee1  call    _bidTraceW
0x180031ee6  jmp     short loc_180031F27
0x180031ee8  test    r14d, r14d
0x180031eeb  jz      short loc_180031F27
0x180031eed  mov     [rbp+arg_0], 0
0x180031ef4  mov     rax, [r12]
0x180031ef8  lea     r8, [rbp+arg_0]
0x180031efc  mov     rdx, [r13+0]
0x180031f00  mov     rcx, r12
0x180031f03  mov     rax, [rax+18h]
0x180031f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f0c  lea     rcx, [rdi+5B8h]; this
0x180031f13  mov     r8, [r13+0]; unsigned __int64
0x180031f17  lea     rdx, [rbp+var_40]; struct CSysString *
0x180031f1b  call    ?Insert@CCollectionMap@@QEAAJAEBVCSysString@@_K@Z; CCollectionMap::Insert(CSysString const &,unsigned __int64)
0x180031f20  mov     bl, [rbp+var_38]
0x180031f23  mov     rsi, [rbp+var_40]
0x180031f27  test    r15, r15
0x180031f2a  jz      short loc_180031F34
0x180031f2c  mov     rcx, r15; void *
0x180031f2f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031f34  mov     edi, [rbp+var_8]
0x180031f37  test    bl, 2
0x180031f3a  jz      short loc_180031F4C
0x180031f3c  mov     rcx, rsi; bstrString
0x180031f3f  call    cs:__imp_SysFreeString
0x180031f46  nop     dword ptr [rax+rax+00h]
0x180031f4b  nop
0x180031f4c  mov     rcx, [rbp+arg_8]
0x180031f50  test    rcx, rcx
0x180031f53  jz      short loc_180031F62
0x180031f55  mov     rdx, [rcx]
0x180031f58  mov     rax, [rdx+10h]
0x180031f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f61  nop
0x180031f62  lea     rcx, [rbp+var_30]; this
0x180031f66  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x180031f6b  mov     eax, edi
0x180031f6d  mov     rbx, [rsp+80h+arg_18]
0x180031f75  add     rsp, 80h
0x180031f7c  pop     r15
0x180031f7e  pop     r14
0x180031f80  pop     r13
0x180031f82  pop     r12
0x180031f84  pop     rdi
0x180031f85  pop     rsi
  ... truncated ...
```
