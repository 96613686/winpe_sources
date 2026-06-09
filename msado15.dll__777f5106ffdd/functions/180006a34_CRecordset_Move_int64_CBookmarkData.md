# CRecordset::_Move(__int64,CBookmarkData &)

- ea: `0x180006a34`
- end: `0x180006c6a`
- name: `?_Move@CRecordset@@QEAAJ_JAEAVCBookmarkData@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, __int64, struct CBookmarkData *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180002990`
- `0x1800307e0`
- `0x1800ae220`

## callees

- `0x180004de0`
- `0x180006610`
- `0x180006a34`
- `0x180020fc0`
- `0x180027790`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x180006abb`
- `KERNEL32!TlsSetValue` at `0x180006c38`
- `KERNEL32!TlsSetValue` at `0x180006abb`
- `KERNEL32!TlsSetValue` at `0x180006c38`
- `KERNEL32!TlsGetValue` at `0x180006a77`
- `KERNEL32!TlsGetValue` at `0x180006a77`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180006c02`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180006c02`

## string_xrefs

- `0x180006b41`: `<CRecordset::_Move|ADO|ERR> %u#, line %d\n`
- `0x180006b92`: `<CRecordset::_Move|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRecordset::_Move(CRecordset *this, signed __int64 a2, struct CBookmarkData *a3)
{
  _DWORD *Value; // rax
  unsigned int BidObjectID; // eax
  __int64 v8; // r8
  unsigned __int8 *v9; // r9
  int v10; // ebx
  _DWORD *v12; // rax
  IErrorInfo *v13; // rdx
  _DWORD *TlsValue; // [rsp+30h] [rbp-30h] BYREF
  int v16; // [rsp+38h] [rbp-28h]
  __int64 v17; // [rsp+40h] [rbp-20h]
  int v18; // [rsp+48h] [rbp-18h]
  __int16 v19; // [rsp+4Ch] [rbp-14h]
  char v20; // [rsp+4Eh] [rbp-12h]
  unsigned __int64 v21; // [rsp+50h] [rbp-10h]
  int v22; // [rsp+58h] [rbp-8h]
  int v23; // [rsp+5Ch] [rbp-4h]
  __int64 v24; // [rsp+80h] [rbp+20h] BYREF

  v21 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  v23 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v22 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v16 = 1;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  if ( (*((_BYTE *)this + 328) & 4) != 0 )
  {
    if ( !*((_QWORD *)this + 40) )
      goto LABEL_6;
LABEL_13:
    v22 = 0;
    goto LABEL_14;
  }
  v24 = 0;
  if ( (int)CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface((char *)this + 312, &v24) >= 0 )
  {
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    goto LABEL_13;
  }
LABEL_6:
  v22 = -2146825037;
  TlsValue[11] = 10020;
  if ( (unsigned int)CContext::PushError((CContext *)&TlsValue) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 9807881, L"<CRecordset::_Move|ADO|ERR>  line %d\n", 9578);
      }
      else
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        bidTraceW(off_18012A208[0], 9807881, L"<CRecordset::_Move|ADO|ERR> %u#, line %d\n", BidObjectID, 9578);
      }
    }
    v10 = v22;
    CContext::~CContext((CContext *)&TlsValue);
    return (unsigned int)v10;
  }
LABEL_14:
  v8 = *((_QWORD *)a3 + 1);
  if ( v8 )
    v9 = *(unsigned __int8 **)a3;
  else
    v9 = 0;
  v10 = CRecordset::MoveAbsolute(this, a2, v8, v9, a2 < 0);
  v22 = v10;
  if ( v10 < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    v10 = v22;
  }
  if ( TlsValue[2]-- == 1 )
  {
    v12 = TlsValue;
    v13 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v13 )
    {
      SetErrorInfo(0, v13);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v12 = TlsValue;
    }
    if ( *((_BYTE *)v12 + 30) )
    {
      *((_QWORD *)v12 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180006a34  mov     [rsp-18h+arg_8], rbx
0x180006a39  mov     [rsp-18h+arg_10], rsi
0x180006a3e  push    rbp
0x180006a3f  push    rdi
0x180006a40  push    r14
0x180006a42  mov     rbp, rsp
0x180006a45  sub     rsp, 60h
0x180006a49  mov     rdi, r8
0x180006a4c  mov     rsi, rdx
0x180006a4f  mov     rbx, rcx
0x180006a52  mov     rax, rcx
0x180006a55  lea     r10, [rcx+20h]
0x180006a59  neg     rax
0x180006a5c  sbb     r9, r9
0x180006a5f  and     r9, r10
0x180006a62  mov     [rbp+var_10], r9
0x180006a66  xor     r14d, r14d
0x180006a69  mov     [rbp+var_4], r14d
0x180006a6d  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180006a74  mov     ecx, [rcx+14h]; dwTlsIndex
0x180006a77  call    cs:__imp_TlsGetValue
0x180006a7e  nop     dword ptr [rax+rax+00h]
0x180006a83  mov     [rbp+TlsValue], rax
0x180006a87  mov     [rbp+var_8], r14d
0x180006a8b  test    rax, rax
0x180006a8e  jz      short loc_180006A95
0x180006a90  inc     dword ptr [rax+8]
0x180006a93  jmp     short loc_180006ACF
0x180006a95  mov     [rbp+var_28], 1
0x180006a9c  mov     [rbp+var_20], r14
0x180006aa0  mov     [rbp+var_18], r14d
0x180006aa4  mov     [rbp+var_14], r14w
0x180006aa9  mov     [rbp+var_12], r14b
0x180006aad  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x180006ab1  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180006ab8  mov     ecx, [rcx+14h]; dwTlsIndex
0x180006abb  call    cs:__imp_TlsSetValue
0x180006ac2  nop     dword ptr [rax+rax+00h]
0x180006ac7  lea     rax, [rbp+TlsValue]
0x180006acb  mov     [rbp+TlsValue], rax
0x180006acf  lea     rcx, [rbx+138h]
0x180006ad6  test    byte ptr [rcx+10h], 4
0x180006ada  jz      short loc_180006B54
0x180006adc  cmp     [rcx+8], r14
0x180006ae0  jnz     loc_180006B7A
0x180006ae6  mov     [rbp+var_8], 800A0CB3h
0x180006aed  mov     rax, [rbp+TlsValue]
0x180006af1  mov     dword ptr [rax+2Ch], 2724h
0x180006af8  lea     rcx, [rbp+TlsValue]; this
0x180006afc  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180006b01  test    eax, eax
0x180006b03  jz      short loc_180006B7E
0x180006b05  test    byte ptr cs:_bidGblFlags, 2
0x180006b0c  jz      loc_180006BAA
0x180006b12  lea     rcx, [rbx+618h]; this
0x180006b19  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180006b1e  cmp     eax, 0FFFFFFFFh
0x180006b21  jz      short loc_180006B8C
0x180006b23  lea     rcx, [rbx+618h]; this
0x180006b2a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180006b2f  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180006b36  mov     dword ptr [rsp+60h+var_40], 256Ah
0x180006b3e  mov     r9d, eax
0x180006b41  lea     r8, aCrecordsetMove_4; "<CRecordset::_Move|ADO|ERR> %u#, line %"...
0x180006b48  mov     edx, 95A809h
0x180006b4d  call    _bidTraceW
0x180006b52  jmp     short loc_180006BAA
0x180006b54  mov     [rbp+arg_0], r14
0x180006b58  lea     rdx, [rbp+arg_0]
0x180006b5c  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetLocate@@$1?IID_IRowsetLocate@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetLocate@@@Z; CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(IRowsetLocate * *)
0x180006b61  test    eax, eax
0x180006b63  js      short loc_180006AE6
0x180006b65  mov     rcx, [rbp+arg_0]
0x180006b69  test    rcx, rcx
0x180006b6c  jz      short loc_180006B7A
0x180006b6e  mov     rax, [rcx]
0x180006b71  mov     rax, [rax+10h]
0x180006b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b7a  mov     [rbp+var_8], r14d
0x180006b7e  mov     r8, [rdi+8]; unsigned __int64
0x180006b82  test    r8, r8
0x180006b85  jz      short loc_180006BBB
0x180006b87  mov     r9, [rdi]
0x180006b8a  jmp     short loc_180006BBE
0x180006b8c  mov     r9d, 256Ah
0x180006b92  lea     r8, aCrecordsetMove_27; "<CRecordset::_Move|ADO|ERR>  line %d\n"
0x180006b99  mov     edx, 95A809h
0x180006b9e  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180006ba5  call    _bidTraceW
0x180006baa  mov     ebx, [rbp+var_8]
0x180006bad  lea     rcx, [rbp+TlsValue]; this
0x180006bb1  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x180006bb6  jmp     loc_180006C52
0x180006bbb  mov     r9, r14; unsigned __int8 *
0x180006bbe  mov     rax, rsi
0x180006bc1  shr     rax, 3Fh
0x180006bc5  mov     [rsp+60h+var_40], al; bool
0x180006bc9  mov     rdx, rsi; __int64
0x180006bcc  mov     rcx, rbx; this
0x180006bcf  call    ?MoveAbsolute@CRecordset@@AEAAJ_J_KPEAE_N@Z; CRecordset::MoveAbsolute(__int64,unsigned __int64,uchar *,bool)
0x180006bd4  mov     ebx, eax
0x180006bd6  mov     [rbp+var_8], eax
0x180006bd9  test    eax, eax
0x180006bdb  jns     short loc_180006BE9
0x180006bdd  lea     rcx, [rbp+TlsValue]; this
0x180006be1  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180006be6  mov     ebx, [rbp+var_8]
0x180006be9  mov     rax, [rbp+TlsValue]
0x180006bed  add     dword ptr [rax+8], 0FFFFFFFFh
0x180006bf1  jnz     short loc_180006C52
0x180006bf3  mov     rax, [rbp+TlsValue]
0x180006bf7  mov     rdx, [rax+10h]; perrinfo
0x180006bfb  test    rdx, rdx
0x180006bfe  jz      short loc_180006C26
0x180006c00  xor     ecx, ecx; dwReserved
0x180006c02  call    cs:__imp_SetErrorInfo
0x180006c09  nop     dword ptr [rax+rax+00h]
0x180006c0e  mov     rax, [rbp+TlsValue]
0x180006c12  mov     rcx, [rax+10h]
0x180006c16  mov     rax, [rcx]
0x180006c19  mov     rax, [rax+10h]
0x180006c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c22  mov     rax, [rbp+TlsValue]
0x180006c26  cmp     [rax+1Eh], r14b
0x180006c2a  jnz     short loc_180006C46
0x180006c2c  xor     edx, edx; lpTlsValue
0x180006c2e  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180006c35  mov     ecx, [rcx+14h]; dwTlsIndex
0x180006c38  call    cs:__imp_TlsSetValue
0x180006c3f  nop     dword ptr [rax+rax+00h]
0x180006c44  jmp     short loc_180006C52
0x180006c46  mov     [rax+10h], r14
0x180006c4a  mov     rax, [rbp+TlsValue]
0x180006c4e  mov     [rax+18h], r14d
0x180006c52  mov     eax, ebx
0x180006c54  lea     r11, [rsp+60h+var_s0]
0x180006c59  mov     rbx, [r11+28h]
0x180006c5d  mov     rsi, [r11+30h]
0x180006c61  mov     rsp, r11
0x180006c64  pop     r14
0x180006c66  pop     rdi
0x180006c67  pop     rbp
0x180006c68  retn
```
