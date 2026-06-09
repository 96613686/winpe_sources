# CCommand::put_Name(ushort *)

- ea: `0x180088c70`
- end: `0x1800892a8`
- name: `?put_Name@CCommand@@UEAAJPEAG@Z`
- size: `1592`
- prototype: `__int64 __fastcall(CCommand *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800892b0`

## callees

- `0x180009240`
- `0x18001a820`
- `0x180020e20`
- `0x1800265d0`
- `0x180027790`
- `0x180042a04`
- `0x18004f1b0`
- `0x18004f370`
- `0x180053d40`
- `0x18006a22c`
- `0x180088c70`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `msvcrt!iswalnum` at `0x180088e9b`
- `msvcrt!iswalnum` at `0x180088e9b`
- `msvcrt!iswalpha` at `0x180088e04`
- `msvcrt!iswalpha` at `0x180088e04`
- `msvcrt!_wcsicmp` at `0x1800890b1`
- `msvcrt!_wcsicmp` at `0x1800890cc`
- `msvcrt!_wcsicmp` at `0x1800890b1`
- `msvcrt!_wcsicmp` at `0x1800890cc`
- `MSDART!UMSEnterCSWraper` at `0x180088d20`
- `MSDART!UMSEnterCSWraper` at `0x180088d20`
- `KERNEL32!LeaveCriticalSection` at `0x1800891ff`
- `KERNEL32!LeaveCriticalSection` at `0x1800891ff`
- `OLEAUT32!__imp_SysStringLen` at `0x180088d56`
- `OLEAUT32!__imp_SysStringLen` at `0x180088d56`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180088f2e`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180088f2e`

## string_xrefs

- `0x180088db8`: `<CCommand::put_Name|ADO|ERR> %u#, line %d\n`
- `0x180088dde`: `<CCommand::put_Name|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CCommand::put_Name(CCommand *this, unsigned __int16 *a2)
{
  char **v2; // rsi
  BSTR v4; // rbx
  unsigned int BidObjectID; // eax
  __int64 v6; // rcx
  signed int v7; // r15d
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // ebx
  BOOL v13; // edx
  BSTR v14; // rsi
  int v15; // r14d
  BOOL v16; // edx
  int v17; // eax
  const struct CSysString *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // ebx
  unsigned int v22; // eax
  unsigned int v23; // ebx
  ITypeLib **pptlib; // [rsp+20h] [rbp-39h]
  ITypeLib *v26; // [rsp+30h] [rbp-29h] BYREF
  __int64 v27; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v28[16]; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v29[32]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v30; // [rsp+70h] [rbp+17h]
  int v31; // [rsp+78h] [rbp+1Fh]
  int v32; // [rsp+C0h] [rbp+67h] BYREF
  BSTR pbstr; // [rsp+C8h] [rbp+6Fh] BYREF
  int v34; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v35; // [rsp+D8h] [rbp+7Fh] BYREF

  pbstr = a2;
  v2 = (char **)((char *)this + 32);
  v30 = ((unsigned __int64)this + 32) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  CContext::Init((CContext *)v29);
  CSysString::CSysString((CSysString *)v28, pbstr, 4u);
  v32 = 0;
  v26 = 0;
  v35 = 0;
  v27 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012AA90[0] )
  {
    v4 = pbstr;
    BidObjectID = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
    bidScopeEnterW(&v27, off_18012AA90[0], BidObjectID, v4, (_DWORD)pptlib);
  }
  v6 = *((_QWORD *)this + 14);
  if ( v6 )
    UMSEnterCSWraper(v6 + 8);
  if ( v2 != (char **)v2[4] && v2[4] )
  {
    v34 = -2146825069;
    CContext::Failed((CContext *)v29, &v34);
    goto LABEL_68;
  }
  v7 = SysStringLen(pbstr);
  if ( (unsigned int)CContext::ArgFailed((CContext *)v29, pbstr != 0) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_68;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
    {
      v8 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      v9 = 2397193;
      LODWORD(pptlib) = 2341;
LABEL_13:
      bidTraceW(off_18012A1E0[0], v9, L"<CCommand::put_Name|ADO|ERR> %u#, line %d\n", v8, pptlib);
      goto LABEL_68;
    }
    v10 = 2341;
    v11 = 2397193;
    goto LABEL_15;
  }
  v12 = 1;
  v13 = *pbstr > 0x7Fu || iswalpha(*pbstr) || *pbstr == 95;
  if ( !(unsigned int)CContext::ArgFailed((CContext *)v29, v13) )
  {
    v14 = pbstr;
    v15 = 0;
    while ( ++v15 < v7 )
    {
      ++v14;
      v16 = *v14 > 0x7Fu || iswalnum(*v14) || *v14 == 95;
      if ( (unsigned int)CContext::ArgFailed((CContext *)v29, v16) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_68;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
        {
          v8 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
          v9 = 2409481;
          LODWORD(pptlib) = 2353;
          goto LABEL_13;
        }
        v10 = 2353;
        v11 = 2409481;
        goto LABEL_15;
      }
    }
    v34 = LoadRegTypeLib(&LIBID_ADO60, 6u, 1u, 0, &v26);
    if ( (unsigned int)CContext::Failed((CContext *)v29, &v34) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_68;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
      {
        v8 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        v9 = 2420745;
        LODWORD(pptlib) = 2364;
        goto LABEL_13;
      }
      v10 = 2364;
      v11 = 2420745;
    }
    else
    {
      v34 = ((__int64 (__fastcall *)(ITypeLib *, GUID *, __int64 *))v26->lpVtbl->GetTypeInfoOfGuid)(
              v26,
              &CLSID_CADOConnection,
              &v35);
      if ( (unsigned int)CContext::Failed((CContext *)v29, &v34) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_68;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
        {
          v8 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
          v9 = 2422793;
          LODWORD(pptlib) = 2366;
          goto LABEL_13;
        }
        v10 = 2366;
        v11 = 2422793;
      }
      else
      {
        v17 = (*(__int64 (__fastcall **)(__int64, BSTR *, __int64, int *))(*(_QWORD *)v35 + 80LL))(v35, &pbstr, 1, &v32);
        v31 = v17;
        if ( (int)(v17 + 0x80000000) < 0 || v17 == -2147352570 )
        {
          v31 = 0;
          if ( !_wcsicmp(pbstr, L"OnStartPage") || !_wcsicmp(pbstr, L"OnEndPage") )
            v12 = 0;
          if ( (unsigned int)CContext::ArgFailed((CContext *)v29, v12) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_68;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
            {
              v8 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
              v9 = 2453513;
              LODWORD(pptlib) = 2396;
              goto LABEL_13;
            }
            v10 = 2396;
            v11 = 2453513;
          }
          else
          {
            if ( !(unsigned int)CContext::ArgFailed((CContext *)v29, v32 == -1) )
            {
              v18 = (const struct CSysString *)CSysString::operator=((char *)this + 160, v28);
              CContext::StringFailed((CContext *)v29, v18);
              goto LABEL_68;
            }
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_68;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
            {
              v8 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
              v9 = 2455561;
              LODWORD(pptlib) = 2398;
              goto LABEL_13;
            }
            v10 = 2398;
            v11 = 2455561;
          }
        }
        else
        {
          v34 = v17;
          CContext::FailedPushWarning((CContext *)v29, &v34);
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_68;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
          {
            v8 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
            v9 = 2448393;
            LODWORD(pptlib) = 2391;
            goto LABEL_13;
          }
          v10 = 2391;
          v11 = 2448393;
        }
      }
    }
LABEL_15:
    bidTraceW(off_18012A1E0[0], v11, L"<CCommand::put_Name|ADO|ERR>  line %d\n", v10);
    goto LABEL_68;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) != -1 )
    {
      v8 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      v9 = 2404361;
      LODWORD(pptlib) = 2348;
      goto LABEL_13;
    }
    v10 = 2348;
    v11 = 2404361;
    goto LABEL_15;
  }
LABEL_68:
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  if ( v26 )
  {
    ((void (__fastcall *)(ITypeLib *))v26->lpVtbl->Release)(v26);
    v26 = 0;
  }
  v19 = *((_QWORD *)this + 14);
  if ( v19 )
  {
    v20 = *(_QWORD *)(v19 + 8);
    --*(_DWORD *)(v20 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v20 + 8));
  }
  if ( (bidGblFlags & 2) != 0 && off_18012A540[0] )
  {
    v21 = v31;
    v22 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
    LODWORD(pptlib) = v21;
    bidTraceW(off_18012A1E0[0], 2472960, off_18012A540[0], v22, pptlib);
  }
  if ( (bidGblFlags & 4) != 0 && v27 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v27);
  v23 = v31;
  CSysString::~CSysString((CSysString *)v28);
  CContext::~CContext((CContext *)v29);
  return v23;
}

```

## disassembly

```asm
0x180088c70  mov     [rsp-8+pbstr], rdx
0x180088c75  push    rbp
0x180088c76  push    rbx
0x180088c77  push    rsi
0x180088c78  push    rdi
0x180088c79  push    r14
0x180088c7b  push    r15
0x180088c7d  lea     rbp, [rsp-2Fh]
0x180088c82  sub     rsp, 88h
0x180088c89  mov     rax, rcx
0x180088c8c  lea     rsi, [rcx+20h]
0x180088c90  neg     rax
0x180088c93  mov     rdi, rcx
0x180088c96  lea     rcx, [rbp+57h+var_60]; this
0x180088c9a  sbb     rdx, rdx
0x180088c9d  and     rdx, rsi
0x180088ca0  mov     [rbp+57h+var_40], rdx
0x180088ca4  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x180088ca9  mov     rdx, [rbp+57h+pbstr]; unsigned __int16 *
0x180088cad  lea     rcx, [rbp+57h+var_70]; this
0x180088cb1  mov     r8b, 4; unsigned __int8
0x180088cb4  call    ??0CSysString@@QEAA@PEAGE@Z; CSysString::CSysString(ushort *,uchar)
0x180088cb9  test    byte ptr cs:_bidGblFlags, 4
0x180088cc0  mov     [rbp+57h+arg_0], 0
0x180088cc7  mov     [rbp+57h+var_80], 0
0x180088ccf  mov     [rbp+57h+arg_18], 0
0x180088cd7  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFFh
0x180088cdf  jz      short loc_180088D13
0x180088ce1  mov     rax, cs:off_18012AA90; "<CCommand::put_Name|API|ADO> %u#, Name:"...
0x180088ce8  test    rax, rax
0x180088ceb  jz      short loc_180088D13
0x180088ced  mov     rbx, [rbp+57h+pbstr]
0x180088cf1  lea     rcx, [rdi+90h]; this
0x180088cf8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180088cfd  mov     rdx, cs:off_18012AA90; "<CCommand::put_Name|API|ADO> %u#, Name:"...
0x180088d04  lea     rcx, [rbp+57h+var_78]
0x180088d08  mov     r9, rbx
0x180088d0b  mov     r8d, eax
0x180088d0e  call    _bidScopeEnterW
0x180088d13  mov     rcx, [rdi+70h]
0x180088d17  test    rcx, rcx
0x180088d1a  jz      short loc_180088D2C
0x180088d1c  add     rcx, 8
0x180088d20  call    cs:__imp_UMSEnterCSWraper
0x180088d27  nop     dword ptr [rax+rax+00h]
0x180088d2c  cmp     rsi, [rsi+20h]
0x180088d30  jz      short loc_180088D52
0x180088d32  cmp     qword ptr [rsi+20h], 0
0x180088d37  jz      short loc_180088D52
0x180088d39  lea     rdx, [rbp+57h+arg_10]; int *
0x180088d3d  mov     [rbp+57h+arg_10], 800A0C93h
0x180088d44  lea     rcx, [rbp+57h+var_60]; this
0x180088d48  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180088d4d  jmp     loc_1800891B1
0x180088d52  mov     rcx, [rbp+57h+pbstr]; pbstr
0x180088d56  call    cs:__imp_SysStringLen
0x180088d5d  nop     dword ptr [rax+rax+00h]
0x180088d62  xor     edx, edx
0x180088d64  lea     rcx, [rbp+57h+var_60]; this
0x180088d68  cmp     [rbp+57h+pbstr], rdx
0x180088d6c  mov     r15d, eax
0x180088d6f  setnz   dl; int
0x180088d72  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x180088d77  test    eax, eax
0x180088d79  jz      short loc_180088DEF
0x180088d7b  test    byte ptr cs:_bidGblFlags, 2
0x180088d82  jz      loc_1800891B1
0x180088d88  lea     rbx, [rdi+90h]
0x180088d8f  mov     rcx, rbx; this
0x180088d92  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180088d97  cmp     eax, 0FFFFFFFFh
0x180088d9a  jz      short loc_180088DCC
0x180088d9c  mov     rcx, rbx; this
0x180088d9f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180088da4  mov     edx, 249409h
0x180088da9  mov     dword ptr [rsp+0B0h+pptlib], 925h
0x180088db1  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180088db8  lea     r8, aCcommandPutNam_0; "<CCommand::put_Name|ADO|ERR> %u#, line "...
0x180088dbf  mov     r9d, eax
0x180088dc2  call    _bidTraceW
0x180088dc7  jmp     loc_1800891B1
0x180088dcc  mov     r9d, 925h
0x180088dd2  mov     edx, 249409h
0x180088dd7  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180088dde  lea     r8, aCcommandPutNam_2; "<CCommand::put_Name|ADO|ERR>  line %d\n"
0x180088de5  call    _bidTraceW
0x180088dea  jmp     loc_1800891B1
0x180088def  mov     rax, [rbp+57h+pbstr]
0x180088df3  mov     ebx, 1
0x180088df8  cmp     word ptr [rax], 7Fh
0x180088dfc  lea     esi, [rbx+5Eh]
0x180088dff  ja      short loc_180088E21
0x180088e01  movzx   ecx, word ptr [rax]; C
0x180088e04  call    cs:__imp_iswalpha
0x180088e0b  nop     dword ptr [rax+rax+00h]
0x180088e10  test    eax, eax
0x180088e12  jnz     short loc_180088E21
0x180088e14  mov     rax, [rbp+57h+pbstr]
0x180088e18  cmp     si, [rax]
0x180088e1b  jz      short loc_180088E21
0x180088e1d  xor     edx, edx
0x180088e1f  jmp     short loc_180088E23
0x180088e21  mov     edx, ebx; int
0x180088e23  lea     rcx, [rbp+57h+var_60]; this
0x180088e27  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x180088e2c  test    eax, eax
0x180088e2e  jz      short loc_180088E7B
0x180088e30  test    byte ptr cs:_bidGblFlags, 2
0x180088e37  jz      loc_1800891B1
0x180088e3d  lea     rbx, [rdi+90h]
0x180088e44  mov     rcx, rbx; this
0x180088e47  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180088e4c  cmp     eax, 0FFFFFFFFh
0x180088e4f  jz      short loc_180088E6B
0x180088e51  mov     rcx, rbx; this
0x180088e54  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180088e59  mov     edx, 24B009h
0x180088e5e  mov     dword ptr [rsp+0B0h+pptlib], 92Ch
0x180088e66  jmp     loc_180088DB1
0x180088e6b  mov     r9d, 92Ch
0x180088e71  mov     edx, 24B009h
0x180088e76  jmp     loc_180088DD7
0x180088e7b  mov     rsi, [rbp+57h+pbstr]
0x180088e7f  xor     r14d, r14d
0x180088e82  add     r14d, ebx
0x180088e85  cmp     r14d, r15d
0x180088e88  jge     loc_180088F13
0x180088e8e  add     rsi, 2
0x180088e92  cmp     word ptr [rsi], 7Fh
0x180088e96  ja      short loc_180088EB9
0x180088e98  movzx   ecx, word ptr [rsi]; C
0x180088e9b  call    cs:__imp_iswalnum
0x180088ea2  nop     dword ptr [rax+rax+00h]
0x180088ea7  test    eax, eax
0x180088ea9  jnz     short loc_180088EB9
0x180088eab  mov     eax, 5Fh ; '_'
0x180088eb0  cmp     ax, [rsi]
0x180088eb3  jz      short loc_180088EB9
0x180088eb5  xor     edx, edx
0x180088eb7  jmp     short loc_180088EBB
0x180088eb9  mov     edx, ebx; int
0x180088ebb  lea     rcx, [rbp+57h+var_60]; this
0x180088ebf  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x180088ec4  test    eax, eax
0x180088ec6  jz      short loc_180088E82
0x180088ec8  test    byte ptr cs:_bidGblFlags, 2
0x180088ecf  jz      loc_1800891B1
0x180088ed5  lea     rbx, [rdi+90h]
0x180088edc  mov     rcx, rbx; this
0x180088edf  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180088ee4  cmp     eax, 0FFFFFFFFh
0x180088ee7  jz      short loc_180088F03
0x180088ee9  mov     rcx, rbx; this
0x180088eec  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180088ef1  mov     edx, 24C409h
0x180088ef6  mov     dword ptr [rsp+0B0h+pptlib], 931h
0x180088efe  jmp     loc_180088DB1
0x180088f03  mov     r9d, 931h
0x180088f09  mov     edx, 24C409h
0x180088f0e  jmp     loc_180088DD7
0x180088f13  lea     rax, [rbp+57h+var_80]
0x180088f17  mov     r8d, ebx; wVerMinor
0x180088f1a  mov     edx, 6; wVerMajor
0x180088f1f  mov     [rsp+0B0h+pptlib], rax; pptlib
0x180088f24  xor     r9d, r9d; lcid
0x180088f27  lea     rcx, LIBID_ADO60; rguid
0x180088f2e  call    cs:__imp_LoadRegTypeLib
0x180088f35  nop     dword ptr [rax+rax+00h]
0x180088f3a  lea     rdx, [rbp+57h+arg_10]; int *
0x180088f3e  mov     [rbp+57h+arg_10], eax
0x180088f41  lea     rcx, [rbp+57h+var_60]; this
0x180088f45  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180088f4a  test    eax, eax
0x180088f4c  jz      short loc_180088F99
0x180088f4e  test    byte ptr cs:_bidGblFlags, 2
0x180088f55  jz      loc_1800891B1
0x180088f5b  lea     rbx, [rdi+90h]
0x180088f62  mov     rcx, rbx; this
0x180088f65  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180088f6a  cmp     eax, 0FFFFFFFFh
0x180088f6d  jz      short loc_180088F89
0x180088f6f  mov     rcx, rbx; this
0x180088f72  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180088f77  mov     edx, 24F009h
0x180088f7c  mov     dword ptr [rsp+0B0h+pptlib], 93Ch
0x180088f84  jmp     loc_180088DB1
0x180088f89  mov     r9d, 93Ch
0x180088f8f  mov     edx, 24F009h
0x180088f94  jmp     loc_180088DD7
0x180088f99  mov     rcx, [rbp+57h+var_80]
0x180088f9d  lea     r8, [rbp+57h+arg_18]
0x180088fa1  lea     rdx, CLSID_CADOConnection
0x180088fa8  mov     rax, [rcx]
0x180088fab  mov     rax, [rax+30h]
0x180088faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088fb4  lea     rdx, [rbp+57h+arg_10]; int *
0x180088fb8  mov     [rbp+57h+arg_10], eax
0x180088fbb  lea     rcx, [rbp+57h+var_60]; this
0x180088fbf  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180088fc4  test    eax, eax
0x180088fc6  jz      short loc_180089013
0x180088fc8  test    byte ptr cs:_bidGblFlags, 2
0x180088fcf  jz      loc_1800891B1
0x180088fd5  lea     rbx, [rdi+90h]
0x180088fdc  mov     rcx, rbx; this
0x180088fdf  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180088fe4  cmp     eax, 0FFFFFFFFh
0x180088fe7  jz      short loc_180089003
0x180088fe9  mov     rcx, rbx; this
0x180088fec  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180088ff1  mov     edx, 24F809h
0x180088ff6  mov     dword ptr [rsp+0B0h+pptlib], 93Eh
0x180088ffe  jmp     loc_180088DB1
0x180089003  mov     r9d, 93Eh
0x180089009  mov     edx, 24F809h
0x18008900e  jmp     loc_180088DD7
0x180089013  mov     rcx, [rbp+57h+arg_18]
0x180089017  lea     r9, [rbp+57h+arg_0]
0x18008901b  mov     r8d, ebx
0x18008901e  lea     rdx, [rbp+57h+pbstr]
0x180089022  mov     rax, [rcx]
0x180089025  mov     rax, [rax+50h]
0x180089029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008902e  mov     edx, 80000000h
0x180089033  mov     [rbp+57h+var_38], eax
0x180089036  lea     ecx, [rax+rdx]
0x180089039  test    edx, ecx
0x18008903b  jnz     short loc_18008909F
0x18008903d  cmp     eax, 80020006h
0x180089042  jz      short loc_18008909F
0x180089044  lea     rdx, [rbp+57h+arg_10]; int *
0x180089048  mov     [rbp+57h+arg_10], eax
0x18008904b  lea     rcx, [rbp+57h+var_60]; this
0x18008904f  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x180089054  test    byte ptr cs:_bidGblFlags, 2
0x18008905b  jz      loc_1800891B1
0x180089061  lea     rbx, [rdi+90h]
0x180089068  mov     rcx, rbx; this
0x18008906b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180089070  cmp     eax, 0FFFFFFFFh
0x180089073  jz      short loc_18008908F
0x180089075  mov     rcx, rbx; this
0x180089078  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18008907d  mov     edx, 255C09h
0x180089082  mov     dword ptr [rsp+0B0h+pptlib], 957h
0x18008908a  jmp     loc_180088DB1
0x18008908f  mov     r9d, 957h
0x180089095  mov     edx, 255C09h
0x18008909a  jmp     loc_180088DD7
0x18008909f  mov     rcx, [rbp+57h+pbstr]; String1
0x1800890a3  lea     rdx, aOnstartpage; "OnStartPage"
0x1800890aa  mov     [rbp+57h+var_38], 0
0x1800890b1  call    cs:__imp__wcsicmp
0x1800890b8  nop     dword ptr [rax+rax+00h]
0x1800890bd  test    eax, eax
0x1800890bf  jz      short loc_1800890DC
0x1800890c1  mov     rcx, [rbp+57h+pbstr]; String1
0x1800890c5  lea     rdx, aOnendpage; "OnEndPage"
0x1800890cc  call    cs:__imp__wcsicmp
0x1800890d3  nop     dword ptr [rax+rax+00h]
0x1800890d8  test    eax, eax
0x1800890da  jnz     short loc_1800890DE
0x1800890dc  xor     ebx, ebx
0x1800890de  mov     edx, ebx; int
0x1800890e0  lea     rcx, [rbp+57h+var_60]; this
0x1800890e4  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x1800890e9  test    eax, eax
0x1800890eb  jz      short loc_180089138
0x1800890ed  test    byte ptr cs:_bidGblFlags, 2
0x1800890f4  jz      loc_1800891B1
0x1800890fa  lea     rbx, [rdi+90h]
0x180089101  mov     rcx, rbx; this
0x180089104  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180089109  cmp     eax, 0FFFFFFFFh
0x18008910c  jz      short loc_180089128
0x18008910e  mov     rcx, rbx; this
0x180089111  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180089116  mov     edx, 257009h
0x18008911b  mov     dword ptr [rsp+0B0h+pptlib], 95Ch
0x180089123  jmp     loc_180088DB1
0x180089128  mov     r9d, 95Ch
0x18008912e  mov     edx, 257009h
0x180089133  jmp     loc_180088DD7
0x180089138  xor     edx, edx
0x18008913a  lea     rcx, [rbp+57h+var_60]; this
0x18008913e  cmp     [rbp+57h+arg_0], 0FFFFFFFFh
0x180089142  setz    dl; int
0x180089145  call    ?ArgFailed@CContext@@QEAAHH@Z; CContext::ArgFailed(int)
0x18008914a  test    eax, eax
0x18008914c  jz      short loc_180089195
0x18008914e  test    byte ptr cs:_bidGblFlags, 2
0x180089155  jz      short loc_1800891B1
0x180089157  lea     rbx, [rdi+90h]
0x18008915e  mov     rcx, rbx; this
0x180089161  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180089166  cmp     eax, 0FFFFFFFFh
0x180089169  jz      short loc_180089185
0x18008916b  mov     rcx, rbx; this
0x18008916e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180089173  mov     edx, 257809h
  ... truncated ...
```
