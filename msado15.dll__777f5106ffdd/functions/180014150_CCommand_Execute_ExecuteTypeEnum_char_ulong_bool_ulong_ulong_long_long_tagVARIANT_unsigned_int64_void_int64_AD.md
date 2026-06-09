# CCommand::_Execute(ExecuteTypeEnum,char,ulong,bool,ulong,ulong,long,long,tagVARIANT *,unsigned __int64,void *,__int64 *,_ADORecordset * *)

- ea: `0x180014150`
- end: `0x1800145c4`
- name: `?_Execute@CCommand@@UEAAJW4ExecuteTypeEnum@@DK_NKKJJPEAUtagVARIANT@@_KPEAXPEA_JPEAPEAU_ADORecordset@@@Z`
- size: `1140`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800139d0`
- `0x180014150`
- `0x1800145d0`
- `0x180020fc0`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x1800143c6`
- `MSDART!UMSEnterCSWraper` at `0x1800143c6`
- `KERNEL32!LeaveCriticalSection` at `0x1800144a5`
- `KERNEL32!LeaveCriticalSection` at `0x1800144a5`
- `KERNEL32!TlsSetValue` at `0x1800141d8`
- `KERNEL32!TlsSetValue` at `0x18001432b`
- `KERNEL32!TlsSetValue` at `0x1800141d8`
- `KERNEL32!TlsSetValue` at `0x18001432b`
- `KERNEL32!TlsGetValue` at `0x180014195`
- `KERNEL32!TlsGetValue` at `0x180014195`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014391`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014391`

## string_xrefs

- `0x18001443d`: `<CCommand::SetCommandType|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18001445e`: `<CCommand::SetCommandType|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800144fb`: `<CCommand::_Execute|ADO|ERR> %u#, line %d\n`
- `0x180014579`: `<CCommand::_Execute|ADO|ERR> %u#, line %d\n`
- `0x180014517`: `<CCommand::_Execute|ADO|ERR>  line %d\n`
- `0x180014595`: `<CCommand::_Execute|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCommand::_Execute(
        __int64 a1,
        int a2,
        char a3,
        __int16 a4,
        char a5,
        int a6,
        int a7,
        int a8,
        int a9,
        struct tagVARIANT *a10,
        unsigned __int64 a11,
        struct CParameter *a12,
        _QWORD *a13,
        struct _ADORecordset **a14)
{
  __int64 v18; // rcx
  _DWORD *Value; // rax
  struct _ADORecordset **v20; // r14
  int v21; // edi
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned int v24; // edx
  int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ebx
  _DWORD *v29; // rax
  IErrorInfo *v30; // rdx
  unsigned int BidObjectID; // eax
  __int64 v33; // rax
  __int64 v34; // rcx
  unsigned int v35; // eax
  unsigned int v36; // eax
  __int64 v37; // [rsp+20h] [rbp-81h]
  _DWORD *TlsValue; // [rsp+70h] [rbp-31h] BYREF
  int v39; // [rsp+78h] [rbp-29h]
  __int64 v40; // [rsp+80h] [rbp-21h]
  int v41; // [rsp+88h] [rbp-19h]
  __int16 v42; // [rsp+8Ch] [rbp-15h]
  char v43; // [rsp+8Eh] [rbp-13h]
  __int64 v44; // [rsp+90h] [rbp-11h]
  int BoundQuery; // [rsp+98h] [rbp-9h]
  int v46; // [rsp+9Ch] [rbp-5h]
  struct CQuery *v47; // [rsp+F0h] [rbp+4Fh] BYREF

  v18 = a1 + 32;
  if ( !a1 )
    v18 = 0;
  v44 = v18;
  v46 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  BoundQuery = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v39 = 1;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v47 = 0;
  v20 = a14;
  if ( a14 )
    *a14 = 0;
  v21 = 0;
  v22 = *(_QWORD *)(a1 + 112);
  if ( v22 )
    UMSEnterCSWraper(v22 + 8);
  if ( *(_DWORD *)(a1 + 224) != a8 && a8 != -1 )
  {
    if ( *(_BYTE *)(a1 + 216) || (a8 & 0xFFFFFFF6) == 0 )
    {
      *(_DWORD *)(a1 + 224) = a8;
      v33 = *(_QWORD *)(a1 + 120);
      if ( v33 )
        *(_BYTE *)(v33 + 172) = 1;
    }
    else
    {
      v21 = -2146825287;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 144)) == -1 )
        {
          bidTraceW(
            off_18012A1E0[0],
            706569,
            L"<CCommand::SetCommandType|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            2148142009LL,
            690);
        }
        else
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 144));
          bidTraceW(
            off_18012A1E0[0],
            706569,
            L"<CCommand::SetCommandType|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            BidObjectID,
            -2146825287,
            690);
        }
      }
    }
  }
  v23 = *(_QWORD *)(a1 + 112);
  if ( v23 )
  {
    v34 = *(_QWORD *)(v23 + 8);
    --*(_DWORD *)(v34 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v34 + 8));
  }
  BoundQuery = v21;
  if ( v21 < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 144)) == -1 )
      {
        bidTraceW(off_18012A1E0[0], 758793, L"<CCommand::_Execute|ADO|ERR>  line %d\n", 741);
      }
      else
      {
        v35 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 144));
        LODWORD(v37) = 741;
        bidTraceW(off_18012A1E0[0], 758793, L"<CCommand::_Execute|ADO|ERR> %u#, line %d\n", v35, v37);
      }
    }
  }
  else
  {
    BoundQuery = CCommand::GetBoundQuery((CCommand *)a1, &v47);
    if ( BoundQuery < 0 )
    {
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 144)) == -1 )
        {
          bidTraceW(off_18012A1E0[0], 761865, L"<CCommand::_Execute|ADO|ERR>  line %d\n", 744);
        }
        else
        {
          v36 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 144));
          LODWORD(v37) = 744;
          bidTraceW(off_18012A1E0[0], 761865, L"<CCommand::_Execute|ADO|ERR> %u#, line %d\n", v36, v37);
        }
      }
    }
    else
    {
      if ( a7 == -1 )
      {
        v24 = 0;
        v25 = 0;
      }
      else
      {
        v24 = dword_1800E8790[a7 - 1];
        v25 = dword_1800E8748[a7 - 1];
      }
      if ( (unsigned int)(a2 - 4) <= 1 && (a2 == 5 || (v24 = 0x40000, a2 == 4)) )
      {
        v26 = 0;
        v24 = 0x40000;
      }
      else
      {
        v26 = dword_1800E87A0[a6] | v25 | 0x40000;
      }
      BoundQuery = CQuery::Execute(v47, a2, a3, a4, a5, v26, v24, a9, a10, a11, a12, a13, v20);
      if ( BoundQuery < 0 )
        CContext::PushError((CContext *)&TlsValue);
    }
  }
  v27 = BoundQuery;
  if ( TlsValue[2]-- == 1 )
  {
    v29 = TlsValue;
    v30 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v30 )
    {
      SetErrorInfo(0, v30);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v29 = TlsValue;
    }
    if ( *((_BYTE *)v29 + 30) )
    {
      *((_QWORD *)v29 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v27;
}

```

## disassembly

```asm
0x180014150  push    rbp
0x180014152  push    rbx
0x180014153  push    rsi
0x180014154  push    rdi
0x180014155  push    r12
0x180014157  push    r13
0x180014159  push    r14
0x18001415b  push    r15
0x18001415d  lea     rbp, [rsp-7]
0x180014162  sub     rsp, 0A8h
0x180014169  mov     r12d, r9d
0x18001416c  movzx   r13d, r8b
0x180014170  mov     esi, edx
0x180014172  mov     rbx, rcx
0x180014175  add     rcx, 20h ; ' '
0x180014179  xor     r15d, r15d
0x18001417c  test    rbx, rbx
0x18001417f  cmovz   rcx, r15
0x180014183  mov     [rbp+3Fh+var_50], rcx
0x180014187  mov     [rbp+3Fh+var_44], r15d
0x18001418b  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180014192  mov     ecx, [rcx+14h]; dwTlsIndex
0x180014195  call    cs:__imp_TlsGetValue
0x18001419c  nop     dword ptr [rax+rax+00h]
0x1800141a1  mov     [rbp+3Fh+TlsValue], rax
0x1800141a5  mov     [rbp+3Fh+var_48], r15d
0x1800141a9  test    rax, rax
0x1800141ac  jnz     loc_18001434F
0x1800141b2  mov     [rbp+3Fh+var_68], 1
0x1800141b9  mov     [rbp+3Fh+var_60], r15
0x1800141bd  mov     [rbp+3Fh+var_58], r15d
0x1800141c1  mov     [rbp+3Fh+var_54], r15w
0x1800141c6  mov     [rbp+3Fh+var_52], r15b
0x1800141ca  lea     rdx, [rbp+3Fh+TlsValue]; lpTlsValue
0x1800141ce  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x1800141d5  mov     ecx, [rcx+14h]; dwTlsIndex
0x1800141d8  call    cs:__imp_TlsSetValue
0x1800141df  nop     dword ptr [rax+rax+00h]
0x1800141e4  lea     rax, [rbp+3Fh+TlsValue]
0x1800141e8  mov     [rbp+3Fh+TlsValue], rax
0x1800141ec  mov     [rbp+3Fh+arg_0], r15
0x1800141f0  mov     r14, [rbp+3Fh+arg_68]
0x1800141f7  test    r14, r14
0x1800141fa  jnz     loc_1800143BA
0x180014200  mov     edi, r15d
0x180014203  mov     rcx, [rbx+70h]
0x180014207  test    rcx, rcx
0x18001420a  jnz     loc_1800143C2
0x180014210  mov     eax, [rbp+3Fh+arg_38]
0x180014216  cmp     [rbx+0E0h], eax
0x18001421c  jnz     loc_1800143D7
0x180014222  mov     rcx, [rbx+70h]
0x180014226  test    rcx, rcx
0x180014229  jnz     loc_18001449A
0x18001422f  mov     [rbp+3Fh+var_48], edi
0x180014232  test    edi, edi
0x180014234  js      loc_1800144B6
0x18001423a  lea     rdx, [rbp+3Fh+arg_0]; struct CQuery **
0x18001423e  mov     rcx, rbx; this
0x180014241  call    ?GetBoundQuery@CCommand@@QEAAJPEAPEAVCQuery@@@Z; CCommand::GetBoundQuery(CQuery * *)
0x180014246  mov     [rbp+3Fh+var_48], eax
0x180014249  test    eax, eax
0x18001424b  js      loc_180014534
0x180014251  lea     r8, cs:180000000h
0x180014258  mov     eax, [rbp+3Fh+arg_30]
0x18001425b  cmp     eax, 0FFFFFFFFh
0x18001425e  jz      loc_180014384
0x180014264  dec     eax
0x180014266  mov     edx, ds:rva dword_1800E8790[r8+rax*4]
0x18001426e  mov     ecx, ds:rva dword_1800E8748[r8+rax*4]
0x180014276  lea     eax, [rsi-4]
0x180014279  cmp     eax, 1
0x18001427c  ja      loc_180014370
0x180014282  cmp     esi, 5
0x180014285  jnz     loc_180014362
0x18001428b  mov     ecx, r15d
0x18001428e  mov     edx, 40000h
0x180014293  mov     [rsp+0E0h+var_80], r14
0x180014298  mov     rax, [rbp+3Fh+arg_60]
0x18001429f  mov     [rsp+0E0h+var_88], rax
0x1800142a4  mov     rax, [rbp+3Fh+arg_58]
0x1800142ab  mov     [rsp+0E0h+var_90], rax
0x1800142b0  mov     rax, [rbp+3Fh+arg_50]
0x1800142b7  mov     [rsp+0E0h+var_98], rax
0x1800142bc  mov     rax, [rbp+3Fh+arg_48]
0x1800142c3  mov     [rsp+0E0h+var_A0], rax
0x1800142c8  mov     eax, [rbp+3Fh+arg_40]
0x1800142ce  mov     [rsp+0E0h+var_A8], eax
0x1800142d2  mov     [rsp+0E0h+var_B0], edx
0x1800142d6  mov     [rsp+0E0h+var_B8], ecx
0x1800142da  movzx   eax, [rbp+3Fh+arg_20]
0x1800142de  mov     byte ptr [rsp+0E0h+var_C0], al
0x1800142e2  mov     r9d, r12d
0x1800142e5  movzx   r8d, r13b
0x1800142e9  mov     edx, esi
0x1800142eb  mov     rcx, [rbp+3Fh+arg_0]
0x1800142ef  call    ?Execute@CQuery@@QEAAJW4ExecuteTypeEnum@@DK_NKKJPEAUtagVARIANT@@_KPEAXPEA_JPEAPEAU_ADORecordset@@@Z; CQuery::Execute(ExecuteTypeEnum,char,ulong,bool,ulong,ulong,long,tagVARIANT *,unsigned __int64,void *,__int64 *,_ADORecordset * *)
0x1800142f4  mov     [rbp+3Fh+var_48], eax
0x1800142f7  test    eax, eax
0x1800142f9  js      short loc_180014357
0x1800142fb  mov     ebx, [rbp+3Fh+var_48]
0x1800142fe  mov     rax, [rbp+3Fh+TlsValue]
0x180014302  add     dword ptr [rax+8], 0FFFFFFFFh
0x180014306  jnz     short loc_180014338
0x180014308  mov     rax, [rbp+3Fh+TlsValue]
0x18001430c  mov     rdx, [rax+10h]; perrinfo
0x180014310  test    rdx, rdx
0x180014313  jnz     short loc_18001438F
0x180014315  cmp     byte ptr [rax+1Eh], 0
0x180014319  jnz     loc_1800145B2
0x18001431f  xor     edx, edx; lpTlsValue
0x180014321  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180014328  mov     ecx, [rcx+14h]; dwTlsIndex
0x18001432b  call    cs:__imp_TlsSetValue
0x180014332  nop     dword ptr [rax+rax+00h]
0x180014337  nop
0x180014338  mov     eax, ebx
0x18001433a  add     rsp, 0A8h
0x180014341  pop     r15
0x180014343  pop     r14
0x180014345  pop     r13
0x180014347  pop     r12
0x180014349  pop     rdi
0x18001434a  pop     rsi
0x18001434b  pop     rbx
0x18001434c  pop     rbp
0x18001434d  retn
0x18001434f  inc     dword ptr [rax+8]
0x180014352  jmp     loc_1800141EC
0x180014357  lea     rcx, [rbp+3Fh+TlsValue]; this
0x18001435b  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180014360  jmp     short loc_1800142FB
0x180014362  mov     edx, 40000h
0x180014367  cmp     esi, 4
0x18001436a  jz      loc_18001428B
0x180014370  mov     eax, [rbp+3Fh+arg_28]
0x180014373  or      ecx, ds:rva dword_1800E87A0[r8+rax*4]
0x18001437b  bts     ecx, 12h
0x18001437f  jmp     loc_180014293
0x180014384  mov     edx, r15d
0x180014387  mov     ecx, r15d
0x18001438a  jmp     loc_180014276
0x18001438f  xor     ecx, ecx; dwReserved
0x180014391  call    cs:__imp_SetErrorInfo
0x180014398  nop     dword ptr [rax+rax+00h]
0x18001439d  mov     rax, [rbp+3Fh+TlsValue]
0x1800143a1  mov     rcx, [rax+10h]
0x1800143a5  mov     rax, [rcx]
0x1800143a8  mov     rax, [rax+10h]
0x1800143ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143b1  mov     rax, [rbp+3Fh+TlsValue]
0x1800143b5  jmp     loc_180014315
0x1800143ba  mov     [r14], r15
0x1800143bd  jmp     loc_180014200
0x1800143c2  add     rcx, 8
0x1800143c6  call    cs:__imp_UMSEnterCSWraper
0x1800143cd  nop     dword ptr [rax+rax+00h]
0x1800143d2  jmp     loc_180014210
0x1800143d7  cmp     eax, 0FFFFFFFFh
0x1800143da  jz      loc_180014222
0x1800143e0  cmp     [rbx+0D8h], dil
0x1800143e7  jnz     loc_18001447B
0x1800143ed  test    eax, 0FFFFFFF6h
0x1800143f2  jz      loc_18001447B
0x1800143f8  mov     edi, 800A0BB9h
0x1800143fd  test    byte ptr cs:_bidGblFlags, 2
0x180014404  jz      loc_180014222
0x18001440a  lea     rcx, [rbx+90h]; this
0x180014411  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014416  cmp     eax, 0FFFFFFFFh
0x180014419  jz      short loc_180014453
0x18001441b  lea     rcx, [rbx+90h]; this
0x180014422  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014427  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001442e  mov     [rsp+0E0h+var_B8], 2B2h
0x180014436  mov     dword ptr [rsp+0E0h+var_C0], edi
0x18001443a  mov     r9d, eax
0x18001443d  lea     r8, aCcommandSetcom; "<CCommand::SetCommandType|ADO|ERR> %u#,"...
0x180014444  mov     edx, 0AC809h
0x180014449  call    _bidTraceW
0x18001444e  jmp     loc_180014222
0x180014453  mov     dword ptr [rsp+0E0h+var_C0], 2B2h
0x18001445b  mov     r9d, edi
0x18001445e  lea     r8, aCcommandSetcom_0; "<CCommand::SetCommandType|ADO|ERR> 0x%0"...
0x180014465  mov     edx, 0AC809h
0x18001446a  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180014471  call    _bidTraceW
0x180014476  jmp     loc_180014222
0x18001447b  mov     [rbx+0E0h], eax
0x180014481  mov     rax, [rbx+78h]
0x180014485  test    rax, rax
0x180014488  jz      loc_180014222
0x18001448e  mov     byte ptr [rax+0ACh], 1
0x180014495  jmp     loc_180014222
0x18001449a  mov     rcx, [rcx+8]
0x18001449e  dec     dword ptr [rcx+30h]
0x1800144a1  add     rcx, 8; lpCriticalSection
0x1800144a5  call    cs:__imp_LeaveCriticalSection
0x1800144ac  nop     dword ptr [rax+rax+00h]
0x1800144b1  jmp     loc_18001422F
0x1800144b6  lea     rcx, [rbp+3Fh+TlsValue]; this
0x1800144ba  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x1800144bf  test    byte ptr cs:_bidGblFlags, 2
0x1800144c6  jz      loc_1800142FB
0x1800144cc  lea     rcx, [rbx+90h]; this
0x1800144d3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800144d8  cmp     eax, 0FFFFFFFFh
0x1800144db  jz      short loc_180014511
0x1800144dd  lea     rcx, [rbx+90h]; this
0x1800144e4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800144e9  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800144f0  mov     dword ptr [rsp+0E0h+var_C0], 2E5h
0x1800144f8  mov     r9d, eax
0x1800144fb  lea     r8, aCcommandExecut_2; "<CCommand::_Execute|ADO|ERR> %u#, line "...
0x180014502  mov     edx, 0B9409h
0x180014507  call    _bidTraceW
0x18001450c  jmp     loc_1800142FB
0x180014511  mov     r9d, 2E5h
0x180014517  lea     r8, aCcommandExecut_7; "<CCommand::_Execute|ADO|ERR>  line %d\n"
0x18001451e  mov     edx, 0B9409h
0x180014523  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001452a  call    _bidTraceW
0x18001452f  jmp     loc_1800142FB
0x180014534  lea     rcx, [rbp+3Fh+TlsValue]; this
0x180014538  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18001453d  test    byte ptr cs:_bidGblFlags, 2
0x180014544  jz      loc_1800142FB
0x18001454a  lea     rcx, [rbx+90h]; this
0x180014551  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014556  cmp     eax, 0FFFFFFFFh
0x180014559  jz      short loc_18001458F
0x18001455b  lea     rcx, [rbx+90h]; this
0x180014562  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014567  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001456e  mov     dword ptr [rsp+0E0h+var_C0], 2E8h
0x180014576  mov     r9d, eax
0x180014579  lea     r8, aCcommandExecut_2; "<CCommand::_Execute|ADO|ERR> %u#, line "...
0x180014580  mov     edx, 0BA009h
0x180014585  call    _bidTraceW
0x18001458a  jmp     loc_1800142FB
0x18001458f  mov     r9d, 2E8h
0x180014595  lea     r8, aCcommandExecut_7; "<CCommand::_Execute|ADO|ERR>  line %d\n"
0x18001459c  mov     edx, 0BA009h
0x1800145a1  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800145a8  call    _bidTraceW
0x1800145ad  jmp     loc_1800142FB
0x1800145b2  mov     [rax+10h], r15
0x1800145b6  mov     rax, [rbp+3Fh+TlsValue]
0x1800145ba  mov     [rax+18h], r15d
0x1800145be  jmp     loc_180014338
```
