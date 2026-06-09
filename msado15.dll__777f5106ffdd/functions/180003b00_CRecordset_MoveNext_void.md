# CRecordset::MoveNext(void)

- ea: `0x180003b00`
- end: `0x180003f8b`
- name: `?MoveNext@CRecordset@@UEAAJXZ`
- size: `1163`
- prototype: `__int64 __fastcall(CRecordset *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18006ec30`

## callees

- `0x180003b00`
- `0x180003fa0`
- `0x180020fc0`
- `0x18004c8d0`
- `0x1800608b0`
- `0x18006a22c`
- `0x1800b5c04`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x180003b3b`
- `MSDART!UMSEnterCSWraper` at `0x180003b3b`
- `KERNEL32!LeaveCriticalSection` at `0x180003bd7`
- `KERNEL32!LeaveCriticalSection` at `0x180003bd7`
- `KERNEL32!TlsSetValue` at `0x180003cef`
- `KERNEL32!TlsSetValue` at `0x180003d45`
- `KERNEL32!TlsSetValue` at `0x180003cef`
- `KERNEL32!TlsSetValue` at `0x180003d45`
- `KERNEL32!TlsGetValue` at `0x180003cac`
- `KERNEL32!TlsGetValue` at `0x180003cac`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180003d5e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180003d5e`

## string_xrefs

- `0x180003df9`: `<CRecordset::MoveNext|ADO|ERR> %u#, line %d\n`
- `0x180003e15`: `<CRecordset::MoveNext|ADO|ERR>  line %d\n`
- `0x180003c76`: `<CRecordset::MoveNext|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180003e9a`: `<CRecordset::MoveNext|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180003e3d`: `<CRecordset::MoveNext|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180003ebb`: `<CRecordset::MoveNext|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecordset::MoveNext(CRecordset *this)
{
  char v2; // si
  int v3; // edi
  __int64 v4; // rcx
  unsigned int v6; // eax
  char *v7; // rcx
  _DWORD *Value; // rax
  _DWORD *v10; // rax
  IErrorInfo *v11; // rdx
  unsigned int BidObjectID; // eax
  __int64 v13; // r9
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // [rsp+20h] [rbp-40h]
  _DWORD *TlsValue; // [rsp+30h] [rbp-30h] BYREF
  int v19; // [rsp+38h] [rbp-28h]
  __int64 v20; // [rsp+40h] [rbp-20h]
  int v21; // [rsp+48h] [rbp-18h]
  __int16 v22; // [rsp+4Ch] [rbp-14h]
  char v23; // [rsp+4Eh] [rbp-12h]
  char *v24; // [rsp+50h] [rbp-10h]
  int v25; // [rsp+58h] [rbp-8h]
  int v26; // [rsp+5Ch] [rbp-4h]
  __int64 v27; // [rsp+88h] [rbp+28h] BYREF

  v27 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012AC78[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
    bidScopeEnterW(&v27, off_18012AC78[0], BidObjectID, v13, v17);
  }
  v2 = 0;
  UMSEnterCSWraper(*((_QWORD *)this + 38) + 8LL);
  if ( *((_DWORD *)this + 315) )
  {
    if ( *((_QWORD *)this + 242) && (v3 = CRecordset::_RequestPosition(this, 13, 0, 0), v3 < 0) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          LODWORD(v17) = 3312;
          bidTraceW(
            off_18012A208[0],
            3391497,
            L"<CRecordset::MoveNext|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            (unsigned int)v3,
            v17);
        }
        else
        {
          v6 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v17) = v3;
          bidTraceW(
            off_18012A208[0],
            3391497,
            L"<CRecordset::MoveNext|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v6,
            v17,
            3312);
        }
      }
    }
    else
    {
      v2 = 1;
      v3 = (*(__int64 (__fastcall **)(CRecordset *))(*(_QWORD *)this + 752LL))(this);
      if ( v3 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
          {
            LODWORD(v17) = 3317;
            bidTraceW(
              off_18012A208[0],
              3396617,
              L"<CRecordset::MoveNext|ADO|ERR> 0x%08x{HRESULT} line %d\n",
              (unsigned int)v3,
              v17);
          }
          else
          {
            v15 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            LODWORD(v17) = v3;
            bidTraceW(
              off_18012A208[0],
              3396617,
              L"<CRecordset::MoveNext|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
              v15,
              v17,
              3317);
          }
        }
      }
      else
      {
        v3 = CRecordset::MoveRelative(this, 1);
      }
    }
    if ( v3 >= 0 )
    {
      if ( v2 )
      {
        if ( *((_QWORD *)this + 242) )
          CRecordset::_AnnouncePosition(this, 13, 1);
        if ( *((_QWORD *)this + 153) )
          (*(void (__fastcall **)(CRecordset *))(*(_QWORD *)this + 768LL))(this);
      }
      goto LABEL_12;
    }
  }
  else
  {
    v3 = -2146824584;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 3388425, L"<CRecordset::MoveNext|ADO|ERR>  line %d\n", 3309);
      }
      else
      {
        v14 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v17) = 3309;
        bidTraceW(off_18012A208[0], 3388425, L"<CRecordset::MoveNext|ADO|ERR> %u#, line %d\n", v14, v17);
      }
    }
  }
  v7 = (char *)this + 32;
  if ( !this )
    v7 = 0;
  v24 = v7;
  v26 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v25 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v19 = 1;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v25 = v3;
  CContext::PushError((CContext *)&TlsValue);
  if ( v2 )
    CRecordset::AnnouncePosition(this, 13, 1);
  if ( TlsValue[2]-- == 1 )
  {
    v10 = TlsValue;
    v11 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v11 )
    {
      SetErrorInfo(0, v11);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v10 = TlsValue;
    }
    if ( *((_BYTE *)v10 + 30) )
    {
      *((_QWORD *)v10 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
LABEL_12:
  v4 = *(_QWORD *)(*((_QWORD *)this + 38) + 8LL);
  --*(_DWORD *)(v4 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  if ( (bidGblFlags & 2) != 0 && off_18012A850[0] )
  {
    v16 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
    LODWORD(v17) = v3;
    bidTraceW(off_18012A208[0], 3424256, off_18012A850[0], v16, v17);
  }
  if ( (bidGblFlags & 4) != 0 && v27 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v27);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003b00  mov     [rsp-18h+arg_10], rbx
0x180003b05  mov     [rsp-18h+arg_18], rsi
0x180003b0a  push    rbp
0x180003b0b  push    rdi
0x180003b0c  push    r14
0x180003b0e  mov     rbp, rsp
0x180003b11  sub     rsp, 60h
0x180003b15  mov     rbx, rcx
0x180003b18  mov     [rbp+arg_8], 0FFFFFFFFFFFFFFFFh
0x180003b20  test    byte ptr cs:_bidGblFlags, 4
0x180003b27  jnz     loc_180003D84
0x180003b2d  xor     sil, sil
0x180003b30  mov     rcx, [rbx+130h]
0x180003b37  add     rcx, 8
0x180003b3b  call    cs:__imp_UMSEnterCSWraper
0x180003b42  nop     dword ptr [rax+rax+00h]
0x180003b47  cmp     dword ptr [rbx+4ECh], 0
0x180003b4e  jz      loc_180003DB8
0x180003b54  cmp     qword ptr [rbx+790h], 0
0x180003b5c  jnz     loc_180003C15
0x180003b62  mov     sil, 1
0x180003b65  mov     rax, [rbx]
0x180003b68  mov     rcx, rbx
0x180003b6b  mov     rax, [rax+2F0h]
0x180003b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b77  mov     edi, eax
0x180003b79  test    eax, eax
0x180003b7b  js      loc_180003E5A
0x180003b81  mov     edx, 1; __int64
0x180003b86  mov     rcx, rbx; this
0x180003b89  call    ?MoveRelative@CRecordset@@AEAAJ_J@Z; CRecordset::MoveRelative(__int64)
0x180003b8e  mov     edi, eax
0x180003b90  test    edi, edi
0x180003b92  js      loc_180003C8C
0x180003b98  test    sil, sil
0x180003b9b  jz      short loc_180003BC5
0x180003b9d  cmp     qword ptr [rbx+790h], 0
0x180003ba5  jz      short loc_180003BB7
0x180003ba7  mov     r8b, 1; bool
0x180003baa  mov     edx, 0Dh; int
0x180003baf  mov     rcx, rbx; this
0x180003bb2  call    ?_AnnouncePosition@CRecordset@@AEAAJJ_N@Z; CRecordset::_AnnouncePosition(long,bool)
0x180003bb7  cmp     qword ptr [rbx+4C8h], 0
0x180003bbf  jnz     loc_180003EFE
0x180003bc5  mov     rax, [rbx+130h]
0x180003bcc  mov     rcx, [rax+8]
0x180003bd0  dec     dword ptr [rcx+30h]
0x180003bd3  add     rcx, 8; lpCriticalSection
0x180003bd7  call    cs:__imp_LeaveCriticalSection
0x180003bde  nop     dword ptr [rax+rax+00h]
0x180003be3  test    byte ptr cs:_bidGblFlags, 2
0x180003bea  jnz     loc_180003F15
0x180003bf0  test    byte ptr cs:_bidGblFlags, 4
0x180003bf7  jnz     loc_180003F55
0x180003bfd  mov     eax, edi
0x180003bff  lea     r11, [rsp+60h+var_s0]
0x180003c04  mov     rbx, [r11+30h]
0x180003c08  mov     rsi, [r11+38h]
0x180003c0c  mov     rsp, r11
0x180003c0f  pop     r14
0x180003c11  pop     rdi
0x180003c12  pop     rbp
0x180003c13  retn
0x180003c15  xor     r9d, r9d; bool
0x180003c18  xor     r8d, r8d; bool *
0x180003c1b  mov     edx, 0Dh; int
0x180003c20  mov     rcx, rbx; this
0x180003c23  call    ?_RequestPosition@CRecordset@@AEAAJJPEA_N_N@Z; CRecordset::_RequestPosition(long,bool *,bool)
0x180003c28  mov     edi, eax
0x180003c2a  test    eax, eax
0x180003c2c  jns     loc_180003B62
0x180003c32  test    byte ptr cs:_bidGblFlags, 2
0x180003c39  jz      loc_180003B90
0x180003c3f  lea     rcx, [rbx+618h]; this
0x180003c46  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180003c4b  cmp     eax, 0FFFFFFFFh
0x180003c4e  jz      loc_180003E32
0x180003c54  lea     rcx, [rbx+618h]; this
0x180003c5b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180003c60  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180003c67  mov     [rsp+60h+var_38], 0CF0h
0x180003c6f  mov     dword ptr [rsp+60h+var_40], edi
0x180003c73  mov     r9d, eax
0x180003c76  lea     r8, aCrecordsetMove_26; "<CRecordset::MoveNext|ADO|ERR> %u#,0x%0"...
0x180003c7d  mov     edx, 33C009h
0x180003c82  call    _bidTraceW
0x180003c87  jmp     loc_180003B90
0x180003c8c  lea     rcx, [rbx+20h]
0x180003c90  xor     r14d, r14d
0x180003c93  test    rbx, rbx
0x180003c96  cmovz   rcx, r14
0x180003c9a  mov     [rbp+var_10], rcx
0x180003c9e  mov     [rbp+var_4], r14d
0x180003ca2  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180003ca9  mov     ecx, [rcx+14h]; dwTlsIndex
0x180003cac  call    cs:__imp_TlsGetValue
0x180003cb3  nop     dword ptr [rax+rax+00h]
0x180003cb8  mov     [rbp+TlsValue], rax
0x180003cbc  mov     [rbp+var_8], r14d
0x180003cc0  test    rax, rax
0x180003cc3  jnz     loc_180003D57
0x180003cc9  mov     [rbp+var_28], 1
0x180003cd0  mov     [rbp+var_20], r14
0x180003cd4  mov     [rbp+var_18], r14d
0x180003cd8  mov     [rbp+var_14], r14w
0x180003cdd  mov     [rbp+var_12], r14b
0x180003ce1  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x180003ce5  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180003cec  mov     ecx, [rcx+14h]; dwTlsIndex
0x180003cef  call    cs:__imp_TlsSetValue
0x180003cf6  nop     dword ptr [rax+rax+00h]
0x180003cfb  lea     rax, [rbp+TlsValue]
0x180003cff  mov     [rbp+TlsValue], rax
0x180003d03  mov     [rbp+var_8], edi
0x180003d06  lea     rcx, [rbp+TlsValue]; this
0x180003d0a  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180003d0f  test    sil, sil
0x180003d12  jnz     loc_180003ED8
0x180003d18  mov     rax, [rbp+TlsValue]
0x180003d1c  add     dword ptr [rax+8], 0FFFFFFFFh
0x180003d20  jnz     short loc_180003D52
0x180003d22  mov     rax, [rbp+TlsValue]
0x180003d26  mov     rdx, [rax+10h]; perrinfo
0x180003d2a  test    rdx, rdx
0x180003d2d  jnz     short loc_180003D5C
0x180003d2f  cmp     byte ptr [rax+1Eh], 0
0x180003d33  jnz     loc_180003EED
0x180003d39  xor     edx, edx; lpTlsValue
0x180003d3b  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180003d42  mov     ecx, [rcx+14h]; dwTlsIndex
0x180003d45  call    cs:__imp_TlsSetValue
0x180003d4c  nop     dword ptr [rax+rax+00h]
0x180003d51  nop
0x180003d52  jmp     loc_180003BC5
0x180003d57  inc     dword ptr [rax+8]
0x180003d5a  jmp     short loc_180003D03
0x180003d5c  xor     ecx, ecx; dwReserved
0x180003d5e  call    cs:__imp_SetErrorInfo
0x180003d65  nop     dword ptr [rax+rax+00h]
0x180003d6a  mov     rax, [rbp+TlsValue]
0x180003d6e  mov     rcx, [rax+10h]
0x180003d72  mov     rax, [rcx]
0x180003d75  mov     rax, [rax+10h]
0x180003d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d7e  mov     rax, [rbp+TlsValue]
0x180003d82  jmp     short loc_180003D2F
0x180003d84  mov     rax, cs:off_18012AC78; "<CRecordset::MoveNext|API|ADO> %u#\n"
0x180003d8b  test    rax, rax
0x180003d8e  jz      loc_180003B2D
0x180003d94  add     rcx, 618h; this
0x180003d9b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180003da0  mov     rdx, cs:off_18012AC78; "<CRecordset::MoveNext|API|ADO> %u#\n"
0x180003da7  mov     r8d, eax
0x180003daa  lea     rcx, [rbp+arg_8]
0x180003dae  call    _bidScopeEnterW
0x180003db3  jmp     loc_180003B2D
0x180003db8  mov     edi, 800A0E78h
0x180003dbd  test    byte ptr cs:_bidGblFlags, 2
0x180003dc4  jz      loc_180003C8C
0x180003dca  lea     rcx, [rbx+618h]; this
0x180003dd1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180003dd6  cmp     eax, 0FFFFFFFFh
0x180003dd9  jz      short loc_180003E0F
0x180003ddb  lea     rcx, [rbx+618h]; this
0x180003de2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180003de7  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180003dee  mov     dword ptr [rsp+60h+var_40], 0CEDh
0x180003df6  mov     r9d, eax
0x180003df9  lea     r8, aCrecordsetMove; "<CRecordset::MoveNext|ADO|ERR> %u#, lin"...
0x180003e00  mov     edx, 33B409h
0x180003e05  call    _bidTraceW
0x180003e0a  jmp     loc_180003C8C
0x180003e0f  mov     r9d, 0CEDh
0x180003e15  lea     r8, aCrecordsetMove_15; "<CRecordset::MoveNext|ADO|ERR>  line %d"...
0x180003e1c  mov     edx, 33B409h
0x180003e21  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180003e28  call    _bidTraceW
0x180003e2d  jmp     loc_180003C8C
0x180003e32  mov     dword ptr [rsp+60h+var_40], 0CF0h
0x180003e3a  mov     r9d, edi
0x180003e3d  lea     r8, aCrecordsetMove_13; "<CRecordset::MoveNext|ADO|ERR> 0x%08x{H"...
0x180003e44  mov     edx, 33C009h
0x180003e49  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180003e50  call    _bidTraceW
0x180003e55  jmp     loc_180003B90
0x180003e5a  test    byte ptr cs:_bidGblFlags, 2
0x180003e61  jz      loc_180003B90
0x180003e67  lea     rcx, [rbx+618h]; this
0x180003e6e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180003e73  cmp     eax, 0FFFFFFFFh
0x180003e76  jz      short loc_180003EB0
0x180003e78  lea     rcx, [rbx+618h]; this
0x180003e7f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180003e84  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180003e8b  mov     [rsp+60h+var_38], 0CF5h
0x180003e93  mov     dword ptr [rsp+60h+var_40], edi
0x180003e97  mov     r9d, eax
0x180003e9a  lea     r8, aCrecordsetMove_26; "<CRecordset::MoveNext|ADO|ERR> %u#,0x%0"...
0x180003ea1  mov     edx, 33D409h
0x180003ea6  call    _bidTraceW
0x180003eab  jmp     loc_180003B90
0x180003eb0  mov     dword ptr [rsp+60h+var_40], 0CF5h
0x180003eb8  mov     r9d, edi
0x180003ebb  lea     r8, aCrecordsetMove_13; "<CRecordset::MoveNext|ADO|ERR> 0x%08x{H"...
0x180003ec2  mov     edx, 33D409h
0x180003ec7  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180003ece  call    _bidTraceW
0x180003ed3  jmp     loc_180003B90
0x180003ed8  mov     r8b, 1; bool
0x180003edb  mov     edx, 0Dh; int
0x180003ee0  mov     rcx, rbx; this
0x180003ee3  call    ?AnnouncePosition@CRecordset@@AEAAJJ_N@Z; CRecordset::AnnouncePosition(long,bool)
0x180003ee8  jmp     loc_180003D18
0x180003eed  mov     [rax+10h], r14
0x180003ef1  mov     rax, [rbp+TlsValue]
0x180003ef5  mov     [rax+18h], r14d
0x180003ef9  jmp     loc_180003D52
0x180003efe  mov     rax, [rbx]
0x180003f01  mov     rcx, rbx
0x180003f04  mov     rax, [rax+300h]
0x180003f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f10  jmp     loc_180003BC5
0x180003f15  mov     rax, cs:off_18012A850; "<CRecordset::MoveNext|API|ADO|RET> %u#,"...
0x180003f1c  test    rax, rax
0x180003f1f  jz      loc_180003BF0
0x180003f25  lea     rcx, [rbx+618h]; this
0x180003f2c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180003f31  mov     r8, cs:off_18012A850; "<CRecordset::MoveNext|API|ADO|RET> %u#,"...
0x180003f38  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180003f3f  mov     dword ptr [rsp+60h+var_40], edi
0x180003f43  mov     r9d, eax
0x180003f46  mov     edx, 344000h
0x180003f4b  call    _bidTraceW
0x180003f50  jmp     loc_180003BF0
0x180003f55  cmp     [rbp+arg_8], 0FFFFFFFFFFFFFFFFh
0x180003f5a  jz      loc_180003BFD
0x180003f60  mov     rcx, cs:_bidID
0x180003f67  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003f6b  jz      loc_180003BFD
0x180003f71  lea     r9, [rbp+arg_8]
0x180003f75  xor     r8d, r8d
0x180003f78  xor     edx, edx
0x180003f7a  mov     rax, cs:off_180121248
0x180003f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f86  jmp     loc_180003BFD
```
