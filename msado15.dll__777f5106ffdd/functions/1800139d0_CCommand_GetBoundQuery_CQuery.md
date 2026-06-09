# CCommand::GetBoundQuery(CQuery * *)

- ea: `0x1800139d0`
- end: `0x180013dfa`
- name: `?GetBoundQuery@CCommand@@QEAAJPEAPEAVCQuery@@@Z`
- size: `1066`
- prototype: `__int64 __fastcall(CCommand *__hidden this, struct CQuery **)`
- caller_count: `14`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180011e40`
- `0x180012f70`
- `0x180014150`
- `0x180017fbc`
- `0x18005410c`
- `0x1800799d0`
- `0x18007a510`
- `0x180083b30`
- `0x180084120`
- `0x1800842a0`
- `0x180087350`
- `0x180087480`
- `0x180088670`
- `0x180089440`

## callees

- `0x1800139d0`
- `0x18001bb80`
- `0x180020e20`
- `0x180020fc0`
- `0x180027790`
- `0x18005c574`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180013b0d`
- `MSDART!MpHeapAlloc` at `0x180013b0d`
- `KERNEL32!TlsSetValue` at `0x180013a55`
- `KERNEL32!TlsSetValue` at `0x180013abf`
- `KERNEL32!TlsSetValue` at `0x180013a55`
- `KERNEL32!TlsSetValue` at `0x180013abf`
- `KERNEL32!TlsGetValue` at `0x180013a12`
- `KERNEL32!TlsGetValue` at `0x180013a12`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180013bf6`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180013bf6`

## string_xrefs

- `0x180013ce9`: `<CStdComObjectRoot::Initialize|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180013bce`: `<CCommand::GetBoundQuery|ADO|ERR> %u#, line %d\n`
- `0x180013c77`: `<CCommand::GetBoundQuery|ADO|ERR> %u#, line %d\n`
- `0x180013d40`: `<CCommand::GetBoundQuery|ADO|ERR> %u#, line %d\n`
- `0x180013c93`: `<CCommand::GetBoundQuery|ADO|ERR>  line %d\n`
- `0x180013d59`: `<CCommand::GetBoundQuery|ADO|ERR>  line %d\n`
- `0x180013da3`: `<CCommand::GetBoundQuery|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCommand::GetBoundQuery(CCommand *this, struct CQuery **a2)
{
  struct CStdComObjectRoot *v4; // rdi
  char *v5; // r8
  _DWORD *Value; // rax
  char *v7; // rax
  CQuery *v8; // rbx
  int v9; // edi
  _DWORD *v11; // rax
  IErrorInfo *v12; // rdx
  struct CStdComObjectRoot *v14; // r15
  __int64 v15; // rax
  int v16; // eax
  int v17; // edi
  unsigned int v18; // eax
  unsigned int BidObjectID; // eax
  __int64 v20; // r9
  __int64 v21; // rdx
  unsigned int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // [rsp+20h] [rbp-40h]
  int v25; // [rsp+20h] [rbp-40h]
  _DWORD *TlsValue; // [rsp+30h] [rbp-30h] BYREF
  int v27; // [rsp+38h] [rbp-28h]
  __int64 v28; // [rsp+40h] [rbp-20h]
  int v29; // [rsp+48h] [rbp-18h]
  __int16 v30; // [rsp+4Ch] [rbp-14h]
  char v31; // [rsp+4Eh] [rbp-12h]
  char *v32; // [rsp+50h] [rbp-10h]
  int v33; // [rsp+58h] [rbp-8h]
  int v34; // [rsp+5Ch] [rbp-4h]
  __int64 v35; // [rsp+90h] [rbp+30h] BYREF

  v4 = (CCommand *)((char *)this + 32);
  v5 = (char *)this + 32;
  if ( !this )
    v5 = 0;
  v32 = v5;
  v34 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v33 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v27 = 1;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v7 = (char *)*((_QWORD *)v4 + 4);
  if ( v4 == (struct CStdComObjectRoot *)v7 || !v7 )
  {
    LODWORD(v35) = -2146824579;
    if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v35) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
        {
          bidTraceW(off_18012A1E0[0], 985097, L"<CCommand::GetBoundQuery|ADO|ERR>  line %d\n", 962);
        }
        else
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
          bidTraceW(off_18012A1E0[0], 985097, L"<CCommand::GetBoundQuery|ADO|ERR> %u#, line %d\n", BidObjectID, 962);
        }
      }
LABEL_43:
      v23 = v33;
      CContext::~CContext((CContext *)&TlsValue);
      return v23;
    }
  }
  v8 = (CQuery *)*((_QWORD *)this + 15);
  if ( v8 )
  {
    v9 = v33;
    goto LABEL_9;
  }
  v14 = (struct CStdComObjectRoot *)*((_QWORD *)v4 + 4);
  if ( v4 == v14 )
    v14 = 0;
  v15 = MpHeapAlloc(g_hHeapHandle, 10485760, 256);
  v35 = v15;
  if ( v15 )
    v8 = (CQuery *)ATL::CComObject<CQuery>::CComObject<CQuery>(v15);
  else
    v8 = 0;
  if ( !v8 )
  {
    v17 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      v25 = 880;
      v20 = 2147942414LL;
      v21 = 901129;
LABEL_36:
      bidTraceW(off_18012A1B0[0], v21, L"<CStdComObjectRoot::Initialize|ADO|ERR> 0x%08x{HRESULT} line %d\n", v20, v25);
    }
LABEL_37:
    v33 = v17;
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
      {
        bidTraceW(off_18012A1E0[0], 1001481, L"<CCommand::GetBoundQuery|ADO|ERR>  line %d\n", 978);
      }
      else
      {
        v22 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        LODWORD(v24) = 978;
        bidTraceW(off_18012A1E0[0], 1001481, L"<CCommand::GetBoundQuery|ADO|ERR> %u#, line %d\n", v22, v24);
      }
    }
    if ( v8 )
      (*(void (__fastcall **)(CQuery *, __int64))(*(_QWORD *)v8 + 72LL))(v8, 1);
    goto LABEL_43;
  }
  v16 = (*(__int64 (__fastcall **)(CQuery *))(*(_QWORD *)v8 + 112LL))(v8);
  v17 = v16;
  if ( v16 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v25 = 884;
      v20 = (unsigned int)v16;
      v21 = 905225;
      goto LABEL_36;
    }
    goto LABEL_37;
  }
  *((_QWORD *)v8 + 4) = v8;
  v33 = 0;
  (*(void (__fastcall **)(CQuery *))(*(_QWORD *)v8 + 80LL))(v8);
  *((_QWORD *)this + 15) = v8;
  *((_QWORD *)v8 + 17) = this;
  v9 = CQuery::Bind(v8, v14);
  v33 = v9;
  if ( v9 < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
      {
        bidTraceW(off_18012A1E0[0], 1011721, L"<CCommand::GetBoundQuery|ADO|ERR>  line %d\n", 988);
      }
      else
      {
        v18 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        bidTraceW(off_18012A1E0[0], 1011721, L"<CCommand::GetBoundQuery|ADO|ERR> %u#, line %d\n", v18, 988);
      }
    }
    *((_QWORD *)this + 15) = 0;
    *((_QWORD *)v8 + 17) = 0;
    (*(void (__fastcall **)(CQuery *))(*(_QWORD *)v8 + 88LL))(v8);
    goto LABEL_43;
  }
LABEL_9:
  *a2 = v8;
  if ( TlsValue[2]-- == 1 )
  {
    v11 = TlsValue;
    v12 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v12 )
    {
      SetErrorInfo(0, v12);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v11 = TlsValue;
    }
    if ( *((_BYTE *)v11 + 30) )
    {
      *((_QWORD *)v11 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800139d0  mov     [rsp-28h+arg_8], rbx
0x1800139d5  mov     [rsp-28h+arg_10], rsi
0x1800139da  push    rbp
0x1800139db  push    rdi
0x1800139dc  push    r12
0x1800139de  push    r14
0x1800139e0  push    r15
0x1800139e2  mov     rbp, rsp
0x1800139e5  sub     rsp, 60h
0x1800139e9  mov     r14, rdx
0x1800139ec  mov     rsi, rcx
0x1800139ef  lea     rdi, [rcx+20h]
0x1800139f3  mov     r8, rdi
0x1800139f6  xor     r12d, r12d
0x1800139f9  test    rcx, rcx
0x1800139fc  cmovz   r8, r12
0x180013a00  mov     [rbp+var_10], r8
0x180013a04  mov     [rbp+var_4], r12d
0x180013a08  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180013a0f  mov     ecx, [rcx+14h]; dwTlsIndex
0x180013a12  call    cs:__imp_TlsGetValue
0x180013a19  nop     dword ptr [rax+rax+00h]
0x180013a1e  mov     [rbp+TlsValue], rax
0x180013a22  mov     [rbp+var_8], r12d
0x180013a26  test    rax, rax
0x180013a29  jnz     loc_180013AE8
0x180013a2f  mov     [rbp+var_28], 1
0x180013a36  mov     [rbp+var_20], r12
0x180013a3a  mov     [rbp+var_18], r12d
0x180013a3e  mov     [rbp+var_14], r12w
0x180013a43  mov     [rbp+var_12], r12b
0x180013a47  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x180013a4b  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180013a52  mov     ecx, [rcx+14h]; dwTlsIndex
0x180013a55  call    cs:__imp_TlsSetValue
0x180013a5c  nop     dword ptr [rax+rax+00h]
0x180013a61  lea     rax, [rbp+TlsValue]
0x180013a65  mov     [rbp+TlsValue], rax
0x180013a69  mov     rax, [rdi+20h]
0x180013a6d  cmp     rdi, rax
0x180013a70  jz      loc_180013C1F
0x180013a76  test    rax, rax
0x180013a79  jz      loc_180013C1F
0x180013a7f  mov     rbx, [rsi+78h]
0x180013a83  test    rbx, rbx
0x180013a86  jz      short loc_180013AF0
0x180013a88  mov     edi, [rbp+var_8]
0x180013a8b  mov     [r14], rbx
0x180013a8e  mov     rax, [rbp+TlsValue]
0x180013a92  add     dword ptr [rax+8], 0FFFFFFFFh
0x180013a96  jnz     short loc_180013ACC
0x180013a98  mov     rax, [rbp+TlsValue]
0x180013a9c  mov     rdx, [rax+10h]; perrinfo
0x180013aa0  test    rdx, rdx
0x180013aa3  jnz     loc_180013BF4
0x180013aa9  cmp     byte ptr [rax+1Eh], 0
0x180013aad  jnz     loc_180013DE8
0x180013ab3  xor     edx, edx; lpTlsValue
0x180013ab5  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180013abc  mov     ecx, [rcx+14h]; dwTlsIndex
0x180013abf  call    cs:__imp_TlsSetValue
0x180013ac6  nop     dword ptr [rax+rax+00h]
0x180013acb  nop
0x180013acc  mov     eax, edi
0x180013ace  lea     r11, [rsp+60h+var_s0]
0x180013ad3  mov     rbx, [r11+38h]
0x180013ad7  mov     rsi, [r11+40h]
0x180013adb  mov     rsp, r11
0x180013ade  pop     r15
0x180013ae0  pop     r14
0x180013ae2  pop     r12
0x180013ae4  pop     rdi
0x180013ae5  pop     rbp
0x180013ae6  retn
0x180013ae8  inc     dword ptr [rax+8]
0x180013aeb  jmp     loc_180013A69
0x180013af0  mov     r15, [rdi+20h]
0x180013af4  cmp     rdi, r15
0x180013af7  cmovz   r15, r12
0x180013afb  mov     edx, 0A00000h
0x180013b00  mov     r8d, 100h
0x180013b06  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180013b0d  call    cs:__imp_MpHeapAlloc
0x180013b14  nop     dword ptr [rax+rax+00h]
0x180013b19  mov     [rbp+arg_0], rax
0x180013b1d  test    rax, rax
0x180013b20  jnz     loc_180013BE4
0x180013b26  mov     rbx, r12
0x180013b29  test    rbx, rbx
0x180013b2c  jz      loc_180013CB0
0x180013b32  mov     rax, [rbx]
0x180013b35  mov     rcx, rbx
0x180013b38  mov     rax, [rax+70h]
0x180013b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b41  mov     edi, eax
0x180013b43  test    eax, eax
0x180013b45  js      loc_180013CD0
0x180013b4b  mov     [rbx+20h], rbx
0x180013b4f  mov     [rbp+var_8], r12d
0x180013b53  mov     rax, [rbx]
0x180013b56  mov     rcx, rbx
0x180013b59  mov     rax, [rax+50h]
0x180013b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b62  mov     [rsi+78h], rbx
0x180013b66  mov     [rbx+88h], rsi
0x180013b6d  mov     rdx, r15; struct CStdComObjectRoot *
0x180013b70  mov     rcx, rbx; this
0x180013b73  call    ?Bind@CQuery@@QEAAJPEAVCStdComObjectRoot@@@Z; CQuery::Bind(CStdComObjectRoot *)
0x180013b78  mov     edi, eax
0x180013b7a  mov     [rbp+var_8], eax
0x180013b7d  test    eax, eax
0x180013b7f  jns     loc_180013A8B
0x180013b85  lea     rcx, [rbp+TlsValue]; this
0x180013b89  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180013b8e  test    byte ptr cs:_bidGblFlags, 2
0x180013b95  jz      loc_180013DBB
0x180013b9b  lea     rcx, [rsi+90h]; this
0x180013ba2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180013ba7  cmp     eax, 0FFFFFFFFh
0x180013baa  jz      loc_180013D9D
0x180013bb0  lea     rcx, [rsi+90h]; this
0x180013bb7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180013bbc  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180013bc3  mov     [rsp+60h+var_40], 3DCh
0x180013bcb  mov     r9d, eax
0x180013bce  lea     r8, aCcommandGetbou; "<CCommand::GetBoundQuery|ADO|ERR> %u#, "...
0x180013bd5  mov     edx, 0F7009h
0x180013bda  call    _bidTraceW
0x180013bdf  jmp     loc_180013DBB
0x180013be4  mov     rcx, rax
0x180013be7  call    ??0?$CComObject@VCQuery@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CQuery>::CComObject<CQuery>(void *)
0x180013bec  mov     rbx, rax
0x180013bef  jmp     loc_180013B29
0x180013bf4  xor     ecx, ecx; dwReserved
0x180013bf6  call    cs:__imp_SetErrorInfo
0x180013bfd  nop     dword ptr [rax+rax+00h]
0x180013c02  mov     rax, [rbp+TlsValue]
0x180013c06  mov     rcx, [rax+10h]
0x180013c0a  mov     rax, [rcx]
0x180013c0d  mov     rax, [rax+10h]
0x180013c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c16  mov     rax, [rbp+TlsValue]
0x180013c1a  jmp     loc_180013AA9
0x180013c1f  mov     dword ptr [rbp+arg_0], 800A0E7Dh
0x180013c26  lea     rdx, [rbp+arg_0]; int *
0x180013c2a  lea     rcx, [rbp+TlsValue]; this
0x180013c2e  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180013c33  test    eax, eax
0x180013c35  jz      loc_180013A7F
0x180013c3b  test    byte ptr cs:_bidGblFlags, 2
0x180013c42  jz      loc_180013DD5
0x180013c48  lea     rcx, [rsi+90h]; this
0x180013c4f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180013c54  cmp     eax, 0FFFFFFFFh
0x180013c57  jz      short loc_180013C8D
0x180013c59  lea     rcx, [rsi+90h]; this
0x180013c60  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180013c65  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180013c6c  mov     [rsp+60h+var_40], 3C2h
0x180013c74  mov     r9d, eax
0x180013c77  lea     r8, aCcommandGetbou; "<CCommand::GetBoundQuery|ADO|ERR> %u#, "...
0x180013c7e  mov     edx, 0F0809h
0x180013c83  call    _bidTraceW
0x180013c88  jmp     loc_180013DD5
0x180013c8d  mov     r9d, 3C2h
0x180013c93  lea     r8, aCcommandGetbou_0; "<CCommand::GetBoundQuery|ADO|ERR>  line"...
0x180013c9a  mov     edx, 0F0809h
0x180013c9f  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180013ca6  call    _bidTraceW
0x180013cab  jmp     loc_180013DD5
0x180013cb0  mov     edi, 8007000Eh
0x180013cb5  test    byte ptr cs:_bidGblFlags, 2
0x180013cbc  jz      short loc_180013CFC
0x180013cbe  mov     [rsp+60h+var_40], 370h
0x180013cc6  mov     r9d, edi
0x180013cc9  mov     edx, 0DC009h
0x180013cce  jmp     short loc_180013CE9
0x180013cd0  test    byte ptr cs:_bidGblFlags, 2
0x180013cd7  jz      short loc_180013CFC
0x180013cd9  mov     [rsp+60h+var_40], 374h
0x180013ce1  mov     r9d, eax
0x180013ce4  mov     edx, 0DD009h
0x180013ce9  lea     r8, aCstdcomobjectr_0; "<CStdComObjectRoot::Initialize|ADO|ERR>"...
0x180013cf0  mov     rcx, cs:off_18012A1B0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180013cf7  call    _bidTraceW
0x180013cfc  mov     [rbp+var_8], edi
0x180013cff  lea     rcx, [rbp+TlsValue]; this
0x180013d03  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180013d08  test    byte ptr cs:_bidGblFlags, 2
0x180013d0f  jz      short loc_180013D71
0x180013d11  lea     rcx, [rsi+90h]; this
0x180013d18  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180013d1d  cmp     eax, 0FFFFFFFFh
0x180013d20  jz      short loc_180013D53
0x180013d22  lea     rcx, [rsi+90h]; this
0x180013d29  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180013d2e  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180013d35  mov     [rsp+60h+var_40], 3D2h
0x180013d3d  mov     r9d, eax
0x180013d40  lea     r8, aCcommandGetbou; "<CCommand::GetBoundQuery|ADO|ERR> %u#, "...
0x180013d47  mov     edx, 0F4809h
0x180013d4c  call    _bidTraceW
0x180013d51  jmp     short loc_180013D71
0x180013d53  mov     r9d, 3D2h
0x180013d59  lea     r8, aCcommandGetbou_0; "<CCommand::GetBoundQuery|ADO|ERR>  line"...
0x180013d60  mov     edx, 0F4809h
0x180013d65  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180013d6c  call    _bidTraceW
0x180013d71  test    rbx, rbx
0x180013d74  jz      short loc_180013D8A
0x180013d76  mov     rax, [rbx]
0x180013d79  mov     edx, 1
0x180013d7e  mov     rcx, rbx
0x180013d81  mov     rax, [rax+48h]
0x180013d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d8a  mov     ebx, [rbp+var_8]
0x180013d8d  lea     rcx, [rbp+TlsValue]; this
0x180013d91  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x180013d96  mov     eax, ebx
0x180013d98  jmp     loc_180013ACE
0x180013d9d  mov     r9d, 3DCh
0x180013da3  lea     r8, aCcommandGetbou_0; "<CCommand::GetBoundQuery|ADO|ERR>  line"...
0x180013daa  mov     edx, 0F7009h
0x180013daf  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180013db6  call    _bidTraceW
0x180013dbb  mov     [rsi+78h], r12
0x180013dbf  mov     [rbx+88h], r12
0x180013dc6  mov     rax, [rbx]
0x180013dc9  mov     rcx, rbx
0x180013dcc  mov     rax, [rax+58h]
0x180013dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dd5  mov     ebx, [rbp+var_8]
0x180013dd8  lea     rcx, [rbp+TlsValue]; this
0x180013ddc  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x180013de1  mov     eax, ebx
0x180013de3  jmp     loc_180013ACE
0x180013de8  mov     [rax+10h], r12
0x180013dec  mov     rax, [rbp+TlsValue]
0x180013df0  mov     [rax+18h], r12d
0x180013df4  jmp     loc_180013ACC
```
