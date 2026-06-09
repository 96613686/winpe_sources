# CDCMPool::CreateResource(unsigned __int64,unsigned __int64 *,long *)

- ea: `0x180064720`
- end: `0x180064e22`
- name: `?CreateResource@CDCMPool@@UEAAJ_KPEA_KPEAJ@Z`
- size: `1794`
- prototype: `__int64 __fastcall(CDCMPool *__hidden this, unsigned __int64, unsigned __int64 *, int *)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180013870`
- `0x180013e30`
- `0x18001adec`
- `0x180022bf8`
- `0x180022fd0`
- `0x180029560`
- `0x180029b58`
- `0x180029c30`
- `0x18002ec0c`
- `0x18003c1f8`
- `0x18003c2e8`
- `0x18005bb94`
- `0x18005d710`
- `0x180063e3c`
- `0x180064720`
- `0x180065390`
- `0x1800655cc`
- `0x180066a10`
- `0x180072968`
- `0x180073f4c`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180064a8a`
- `OLEAUT32!__imp_VariantInit` at `0x180064a8a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180064b14`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180064b14`

## string_xrefs

- `0x180064830`: `<CDCMPool::CreateResource|OLEDB|ERR> `
- `0x18006484e`: `<CDCMPool::CreateResource|OLEDB|ERR> `
- `0x1800648ca`: `<CDCMPool::CreateResource|OLEDB|ERR> `
- `0x1800648e8`: `<CDCMPool::CreateResource|OLEDB|ERR> `
- `0x18006495a`: `<CDCMPool::CreateResource|OLEDB|ERR> `
- `0x180064978`: `<CDCMPool::CreateResource|OLEDB|ERR> `
- `0x180064d4e`: `<CDCMPool::CreateResource|OLEDB|ERR> `
- `0x180064869`: `<CDCMPool::CreateResource|Trace|HR> `
- `0x180064903`: `<CDCMPool::CreateResource|Trace|HR> `
- `0x180064993`: `<CDCMPool::CreateResource|Trace|HR> `
- `0x180064d68`: `<CDCMPool::CreateResource|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CDCMPool::CreateResource(CDCMPool *this, __int64 a2, unsigned __int64 *a3, int *a4)
{
  unsigned __int64 *v4; // rax
  CDCMPool *v6; // r13
  unsigned int BidTraceID; // eax
  __int64 v8; // r12
  __int64 v9; // r14
  int v10; // edi
  int v11; // edi
  int v12; // edi
  unsigned int v13; // edi
  int v14; // eax
  __int64 v15; // rax
  int v16; // r8d
  int v17; // edi
  __int64 Provider; // rax
  bool ShouldDoEnlistment; // al
  int CurrentToken; // edi
  char CanIBePooled_ThreadingModel; // al
  CDCMPool *v22; // rcx
  __int64 v23; // r15
  _QWORD *v24; // rsi
  int *v25; // r15
  signed __int32 v26; // ecx
  unsigned int v27; // eax
  int v29; // ebx
  int v30; // [rsp+28h] [rbp-140h]
  __int64 v31; // [rsp+30h] [rbp-138h] BYREF
  int v32; // [rsp+38h] [rbp-130h] BYREF
  unsigned int *v33; // [rsp+40h] [rbp-128h] BYREF
  __int64 v34; // [rsp+48h] [rbp-120h] BYREF
  int pExceptionObject; // [rsp+50h] [rbp-118h] BYREF
  int v36; // [rsp+54h] [rbp-114h] BYREF
  int v37; // [rsp+58h] [rbp-110h] BYREF
  unsigned int v38; // [rsp+5Ch] [rbp-10Ch] BYREF
  unsigned __int64 *v39; // [rsp+60h] [rbp-108h]
  __int64 v40; // [rsp+68h] [rbp-100h] BYREF
  int *v41; // [rsp+70h] [rbp-F8h]
  __int64 v42; // [rsp+78h] [rbp-F0h]
  struct tagDBPROPSET *v43[2]; // [rsp+80h] [rbp-E8h] BYREF
  CDCMPool *v44; // [rsp+90h] [rbp-D8h]
  unsigned __int64 *v45; // [rsp+98h] [rbp-D0h]
  int *v46; // [rsp+A0h] [rbp-C8h]
  int *v47; // [rsp+A8h] [rbp-C0h] BYREF
  int v48; // [rsp+B0h] [rbp-B8h]
  GUID v49; // [rsp+B4h] [rbp-B4h]
  int v50; // [rsp+D0h] [rbp-98h] BYREF
  __int64 v51; // [rsp+D4h] [rbp-94h]
  DBID v52; // [rsp+E0h] [rbp-88h]
  VARIANTARG pvarg; // [rsp+100h] [rbp-68h] BYREF

  v41 = a4;
  v4 = a3;
  v39 = a3;
  v6 = this;
  v44 = this;
  v45 = a3;
  v46 = a4;
  v40 = -1;
  if ( (bidGblFlags & 4) != 0 )
  {
    if ( off_1800C8E80[0] )
    {
      BidTraceID = CDCMPool::getBidTraceID((CDCMPool *)((char *)this - 8));
      bidScopeEnterA(&v40, off_1800C8E80[0], BidTraceID);
      v4 = v39;
      a4 = v41;
    }
    else
    {
      v4 = a3;
    }
  }
  v31 = 0;
  if ( a2 && v4 && a4 )
  {
    v8 = *(_QWORD *)(a2 + 32);
    v34 = 0;
    v9 = 0;
    v42 = 0;
    try
    {
      v10 = CreateDCM(*(IID **)a2, 0, *(_DWORD *)(a2 + 16), *(_QWORD *)(a2 + 24), *(CDPO **)(a2 + 32), &v31);
      if ( v10 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v10, L"<CDCMPool::CreateResource|OLEDB|ERR> ", 0x3F4u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v10, L"<CDCMPool::CreateResource|OLEDB|ERR> ", 0x3F4u);
            if ( (bidGblFlags & 2) != 0 )
              v10 = bidTraceHR(off_1800C8440[0], 1036297, L"<CDCMPool::CreateResource|Trace|HR> ", (unsigned int)v10);
          }
        }
        pExceptionObject = v10;
        throw (long *)&pExceptionObject;
      }
      v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v31)(v31, &IID_IDBInitialize, &v34);
      if ( v11 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v11, L"<CDCMPool::CreateResource|OLEDB|ERR> ", 0x3F6u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v11, L"<CDCMPool::CreateResource|OLEDB|ERR> ", 0x3F6u);
            if ( (bidGblFlags & 2) != 0 )
              v11 = bidTraceHR(off_1800C8440[0], 1038345, L"<CDCMPool::CreateResource|Trace|HR> ", (unsigned int)v11);
          }
        }
        v36 = v11;
        throw (long *)&v36;
      }
      v33 = 0;
      v12 = StoreTouchState((struct CDSLPropertySetArray *)(v8 + 144), &v33);
      if ( v12 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v12, L"<CDCMPool::CreateResource|OLEDB|ERR> ", 0x3FAu);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v12, L"<CDCMPool::CreateResource|OLEDB|ERR> ", 0x3FAu);
            if ( (bidGblFlags & 2) != 0 )
              v12 = bidTraceHR(off_1800C8440[0], 1042441, L"<CDCMPool::CreateResource|Trace|HR> ", (unsigned int)v12);
          }
        }
        v37 = v12;
        throw (long *)&v37;
      }
      v13 = *(_DWORD *)(v8 + 144);
      v43[0] = *(struct tagDBPROPSET **)(v8 + 152);
      v32 = CDCM::SetPropertiesPrivate((CDCM *)(v31 + 24), (struct CDPOPropertySetArray *)(v8 + 144));
      FixupHRForOLEDBServices(v13, v43[0], &v32);
      RestoreTouchState((struct CDSLPropertySetArray *)(v8 + 144), &v33);
      v14 = v32;
      if ( v32 < 0 )
      {
        CurrentToken = v32;
      }
      else
      {
        if ( *(_BYTE *)(*(_QWORD *)(v8 + 120) + 19LL) )
        {
          v15 = TDSLSetArray<CDSLPropertySet,CDSLProperty>::Find(v8 + 144, &DBPROPSET_DBINIT, 248);
          if ( v15 && *(_WORD *)(v15 + 48) == 3 )
            v17 = *(_DWORD *)(v15 + 56);
          else
            v17 = -1;
          v50 = v16;
          v51 = 1;
          v52 = DB_NULLID;
          VariantInit(&pvarg);
          pvarg.vt = 3;
          pvarg.lVal = v17 & 0xFFFFFFFD;
          v47 = &v50;
          v48 = 1;
          v49 = DBPROPSET_DBINIT;
          Provider = GetProviderPointer<CDCM>(v31 + 24, &IID_IDBProperties);
          v9 = Provider;
          v42 = Provider;
          if ( Provider )
          {
            if ( (*(int (__fastcall **)(__int64, __int64, int **))(*(_QWORD *)Provider + 40LL))(Provider, 1, &v47) < 0 )
              SetErrorInfo(0, 0);
          }
        }
        ShouldDoEnlistment = CDPO::ShouldDoEnlistment((CDPO *)v8);
        *(_BYTE *)(v31 + 477) = ShouldDoEnlistment;
        CurrentToken = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 24LL))(v34);
        v14 = v32;
      }
      if ( CurrentToken )
      {
        *(_DWORD *)(v8 + 200) = CurrentToken;
        if ( CurrentToken < 0 )
        {
          *(_DWORD *)(a2 + 44) = 5;
          CDCM::RestoreErrorObject((CDCM *)(v31 + 24));
          goto LABEL_55;
        }
        *(_DWORD *)(a2 + 44) = 3;
      }
      else
      {
        *(_DWORD *)(v8 + 200) = v14;
        CanIBePooled_ThreadingModel = *((_BYTE *)v6 + 240);
        if ( !CanIBePooled_ThreadingModel )
        {
          CanIBePooled_ThreadingModel = CDCM::CanIBePooled_ThreadingModel((CDCM *)(v31 + 24));
          *((_BYTE *)v6 + 240) = CanIBePooled_ThreadingModel;
        }
        if ( CanIBePooled_ThreadingModel == 1 )
        {
          *(GUID *)v43 = CLSID_SCM;
          CurrentToken = (*(__int64 (__fastcall **)(__int64, struct tagDBPROPSET **))(*(_QWORD *)(v31 + 208) + 24LL))(
                           v31 + 208,
                           v43);
          if ( CurrentToken < 0 )
            goto LABEL_49;
          v23 = v31;
          v33 = 0;
          if ( g_pfnNtCompareTokens )
          {
            CurrentToken = CDCMPool::GetCurrentToken(v22, (void **)&v33);
            if ( CurrentToken >= 0 )
              *(_QWORD *)(v23 + 520) = v33;
          }
          else
          {
            CurrentToken = CDCMPool::GetCurrentSID(v22, (void **)&v33);
            if ( CurrentToken >= 0 )
              *(_QWORD *)(v23 + 512) = v33;
          }
          if ( CurrentToken < 0 )
          {
LABEL_49:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 32LL))(v34);
            *(_DWORD *)(a2 + 44) = 4;
            CDCM::RestoreErrorObject((CDCM *)(v31 + 24));
          }
          goto LABEL_55;
        }
        *(_DWORD *)(a2 + 44) = 2;
      }
      CurrentToken = -2147467259;
LABEL_55:
      *(_QWORD *)(a2 + 48) = v31;
      *(_BYTE *)(a2 + 40) = 1;
    }
    catch ( long v38 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800C8990[0] )
      {
        v29 = v38;
        bidTraceA(off_1800C8440[0], 1186816, off_1800C8990[0], v38);
      }
      else
      {
        v29 = v38;
      }
      v32 = v29;
      if ( v31 )
      {
        CDCM::RestoreErrorObject((CDCM *)(v31 + 24));
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        v31 = 0;
      }
      CurrentToken = v32;
      v9 = v42;
      v6 = v44;
      v24 = v45;
      v25 = v46;
      goto LABEL_57;
    }
    v24 = v39;
    v25 = v41;
LABEL_57:
    if ( v34 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      v34 = 0;
    }
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    if ( CurrentToken >= 0 )
    {
      *v24 = v31;
      *v25 = *((_DWORD *)v6 + 27);
      v26 = _InterlockedIncrement((volatile signed __int32 *)v6 + 25);
      if ( (bidGblFlags & 0x1000) != 0 )
      {
        if ( off_1800C92D0[0] )
          bidTraceW(off_1800C8440[0], 1204224, off_1800C92D0[0], (char *)v6 - 8, v26, v30, v31);
      }
    }
    goto LABEL_68;
  }
  CurrentToken = -2147024809;
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_71;
  OLEDBTraceErr(-2147024809, L"<CDCMPool::CreateResource|OLEDB|ERR> ", 0x3E2u);
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_71;
  CurrentToken = bidTraceHR(off_1800C8440[0], 1017865, L"<CDCMPool::CreateResource|Trace|HR> ", 2147942487LL);
LABEL_68:
  if ( (bidGblFlags & 2) != 0 && off_1800C8988[0] )
  {
    v27 = CDCMPool::getBidTraceID((CDCMPool *)((char *)v6 - 8));
    bidTraceA(off_1800C8440[0], 1208320, off_1800C8988[0], v27);
  }
LABEL_71:
  if ( (bidGblFlags & 4) != 0 && v40 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v40);
  return (unsigned int)CurrentToken;
}

```

## disassembly

```asm
0x180064720  push    rbx
0x180064722  push    rsi
0x180064723  push    rdi
0x180064724  push    r12
0x180064726  push    r13
0x180064728  push    r14
0x18006472a  push    r15
0x18006472c  sub     rsp, 130h
0x180064733  mov     rax, cs:__security_cookie
0x18006473a  xor     rax, rsp
0x18006473d  mov     [rsp+168h+var_48], rax
0x180064745  mov     [rsp+168h+var_F8], r9
0x18006474a  mov     rax, r8
0x18006474d  mov     [rsp+168h+var_108], rax
0x180064752  mov     rsi, rdx
0x180064755  mov     r13, rcx
0x180064758  mov     [rsp+168h+var_D8], rcx
0x180064760  mov     [rsp+168h+var_D0], rax
0x180064768  mov     [rsp+168h+var_C8], r9
0x180064770  mov     [rsp+168h+var_100], 0FFFFFFFFFFFFFFFFh
0x180064779  xor     ebx, ebx
0x18006477b  test    byte ptr cs:_bidGblFlags, 4
0x180064782  jz      short loc_1800647BC
0x180064784  mov     rax, cs:off_1800C8E80; "<CDCMPool::CreateResource> %u#"
0x18006478b  test    rax, rax
0x18006478e  jz      short loc_1800647B9
0x180064790  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180064794  call    ?getBidTraceID@CDCMPool@@QEAAHXZ; CDCMPool::getBidTraceID(void)
0x180064799  mov     rdx, cs:off_1800C8E80; "<CDCMPool::CreateResource> %u#"
0x1800647a0  mov     r8d, eax
0x1800647a3  lea     rcx, [rsp+168h+var_100]
0x1800647a8  call    _bidScopeEnterA
0x1800647ad  mov     rax, [rsp+168h+var_108]
0x1800647b2  mov     r9, [rsp+168h+var_F8]
0x1800647b7  jmp     short loc_1800647BC
0x1800647b9  mov     rax, r8
0x1800647bc  mov     [rsp+168h+var_138], rbx
0x1800647c1  test    rsi, rsi
0x1800647c4  jz      loc_180064D36
0x1800647ca  test    rax, rax
0x1800647cd  jz      loc_180064D36
0x1800647d3  test    r9, r9
0x1800647d6  jz      loc_180064D36
0x1800647dc  mov     r12, [rsi+20h]
0x1800647e0  lea     r15, [r12+90h]
0x1800647e8  mov     [rsp+168h+var_120], rbx
0x1800647ed  mov     r14, rbx
0x1800647f0  mov     [rsp+168h+var_F0], rbx
0x1800647f5  lea     rax, [rsp+168h+var_138]
0x1800647fa  mov     [rsp+168h+var_140], rax; __int64
0x1800647ff  mov     rax, [rsi+20h]
0x180064803  mov     [rsp+168h+var_148], rax; CDPO *
0x180064808  mov     r9, [rsi+18h]
0x18006480c  mov     r8d, [rsi+10h]
0x180064810  xor     edx, edx
0x180064812  mov     rcx, [rsi]; rclsid
0x180064815  call    ?CreateDCM@@YAJAEBU_GUID@@PEAUIUnknown@@KPEAGPEAVCDPO@@PEAPEAV?$CACMComPolyObject@VCDCM@@@@@Z; CreateDCM(_GUID const &,IUnknown *,ulong,ushort *,CDPO *,CACMComPolyObject<CDCM> * *)
0x18006481a  mov     edi, eax
0x18006481c  test    eax, eax
0x18006481e  jns     short loc_180064898
0x180064820  mov     eax, cs:_bidGblFlags
0x180064826  test    al, 2
0x180064828  jz      short loc_180064883
0x18006482a  mov     r8d, 3F4h; unsigned int
0x180064830  lea     rdx, aCdcmpoolCreate_2; "<CDCMPool::CreateResource|OLEDB|ERR> "
0x180064837  mov     ecx, edi; int
0x180064839  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006483e  mov     eax, cs:_bidGblFlags
0x180064844  test    al, 2
0x180064846  jz      short loc_180064883
0x180064848  mov     r8d, 3F4h; unsigned int
0x18006484e  lea     rdx, aCdcmpoolCreate_2; "<CDCMPool::CreateResource|OLEDB|ERR> "
0x180064855  mov     ecx, edi; int
0x180064857  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006485c  mov     eax, cs:_bidGblFlags
0x180064862  test    al, 2
0x180064864  jz      short loc_180064883
0x180064866  mov     r9d, edi
0x180064869  lea     r8, aCdcmpoolCreate_3; "<CDCMPool::CreateResource|Trace|HR> "
0x180064870  mov     edx, 0FD009h
0x180064875  mov     rcx, cs:off_1800C8440; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006487c  call    _bidTraceHR
0x180064881  mov     edi, eax
0x180064883  mov     [rsp+168h+pExceptionObject], edi
0x180064887  lea     rdx, _TI1J; pThrowInfo
0x18006488e  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x180064893  call    _CxxThrowException_0
0x180064898  mov     rcx, [rsp+168h+var_138]
0x18006489d  mov     rax, [rcx]
0x1800648a0  lea     r8, [rsp+168h+var_120]
0x1800648a5  lea     rdx, IID_IDBInitialize
0x1800648ac  mov     rax, [rax]
0x1800648af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800648b4  mov     edi, eax
0x1800648b6  test    eax, eax
0x1800648b8  jns     short loc_180064932
0x1800648ba  mov     eax, cs:_bidGblFlags
0x1800648c0  test    al, 2
0x1800648c2  jz      short loc_18006491D
0x1800648c4  mov     r8d, 3F6h; unsigned int
0x1800648ca  lea     rdx, aCdcmpoolCreate_2; "<CDCMPool::CreateResource|OLEDB|ERR> "
0x1800648d1  mov     ecx, edi; int
0x1800648d3  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800648d8  mov     eax, cs:_bidGblFlags
0x1800648de  test    al, 2
0x1800648e0  jz      short loc_18006491D
0x1800648e2  mov     r8d, 3F6h; unsigned int
0x1800648e8  lea     rdx, aCdcmpoolCreate_2; "<CDCMPool::CreateResource|OLEDB|ERR> "
0x1800648ef  mov     ecx, edi; int
0x1800648f1  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800648f6  mov     eax, cs:_bidGblFlags
0x1800648fc  test    al, 2
0x1800648fe  jz      short loc_18006491D
0x180064900  mov     r9d, edi
0x180064903  lea     r8, aCdcmpoolCreate_3; "<CDCMPool::CreateResource|Trace|HR> "
0x18006490a  mov     edx, 0FD809h
0x18006490f  mov     rcx, cs:off_1800C8440; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180064916  call    _bidTraceHR
0x18006491b  mov     edi, eax
0x18006491d  mov     [rsp+168h+var_114], edi
0x180064921  lea     rdx, _TI1J; pThrowInfo
0x180064928  lea     rcx, [rsp+168h+var_114]; pExceptionObject
0x18006492d  call    _CxxThrowException_0
0x180064932  mov     [rsp+168h+var_128], rbx
0x180064937  lea     rdx, [rsp+168h+var_128]; unsigned int **
0x18006493c  mov     rcx, r15; struct CDSLPropertySetArray *
0x18006493f  call    ?StoreTouchState@@YAJPEAVCDSLPropertySetArray@@PEAPEAK@Z; StoreTouchState(CDSLPropertySetArray *,ulong * *)
0x180064944  mov     edi, eax
0x180064946  test    eax, eax
0x180064948  jns     short loc_1800649C2
0x18006494a  mov     eax, cs:_bidGblFlags
0x180064950  test    al, 2
0x180064952  jz      short loc_1800649AD
0x180064954  mov     r8d, 3FAh; unsigned int
0x18006495a  lea     rdx, aCdcmpoolCreate_2; "<CDCMPool::CreateResource|OLEDB|ERR> "
0x180064961  mov     ecx, edi; int
0x180064963  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180064968  mov     eax, cs:_bidGblFlags
0x18006496e  test    al, 2
0x180064970  jz      short loc_1800649AD
0x180064972  mov     r8d, 3FAh; unsigned int
0x180064978  lea     rdx, aCdcmpoolCreate_2; "<CDCMPool::CreateResource|OLEDB|ERR> "
0x18006497f  mov     ecx, edi; int
0x180064981  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180064986  mov     eax, cs:_bidGblFlags
0x18006498c  test    al, 2
0x18006498e  jz      short loc_1800649AD
0x180064990  mov     r9d, edi
0x180064993  lea     r8, aCdcmpoolCreate_3; "<CDCMPool::CreateResource|Trace|HR> "
0x18006499a  mov     edx, 0FE809h
0x18006499f  mov     rcx, cs:off_1800C8440; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800649a6  call    _bidTraceHR
0x1800649ab  mov     edi, eax
0x1800649ad  mov     [rsp+168h+var_110], edi
0x1800649b1  lea     rdx, _TI1J; pThrowInfo
0x1800649b8  lea     rcx, [rsp+168h+var_110]; pExceptionObject
0x1800649bd  call    _CxxThrowException_0
0x1800649c2  mov     edi, [r15]
0x1800649c5  mov     rax, [r15+8]
0x1800649c9  mov     [rsp+168h+var_E8], rax
0x1800649d1  mov     rcx, [rsp+168h+var_138]
0x1800649d6  add     rcx, 18h; this
0x1800649da  mov     rdx, r15; struct CDPOPropertySetArray *
0x1800649dd  call    ?SetPropertiesPrivate@CDCM@@QEAAJPEAVCDPOPropertySetArray@@@Z; CDCM::SetPropertiesPrivate(CDPOPropertySetArray *)
0x1800649e2  mov     [rsp+168h+var_130], eax
0x1800649e6  lea     r8, [rsp+168h+var_130]; int *
0x1800649eb  mov     rdx, [rsp+168h+var_E8]; struct tagDBPROPSET *
0x1800649f3  mov     ecx, edi; unsigned int
0x1800649f5  call    ?FixupHRForOLEDBServices@@YAXKPEAUtagDBPROPSET@@AEAJ@Z; FixupHRForOLEDBServices(ulong,tagDBPROPSET *,long &)
0x1800649fa  lea     rdx, [rsp+168h+var_128]; unsigned int **
0x1800649ff  mov     rcx, r15; struct CDSLPropertySetArray *
0x180064a02  call    ?RestoreTouchState@@YAXPEAVCDSLPropertySetArray@@PEAPEAK@Z; RestoreTouchState(CDSLPropertySetArray *,ulong * *)
0x180064a07  mov     eax, [rsp+168h+var_130]
0x180064a0b  test    eax, eax
0x180064a0d  js      loc_180064B4E
0x180064a13  mov     rax, [r12+78h]
0x180064a18  cmp     [rax+13h], bl
0x180064a1b  jz      loc_180064B1C
0x180064a21  mov     r8d, 0F8h
0x180064a27  lea     rdx, DBPROPSET_DBINIT
0x180064a2e  mov     rcx, r15
0x180064a31  call    ?Find@?$TDSLSetArray@VCDSLPropertySet@@VCDSLProperty@@@@QEBAPEBVCDSLProperty@@AEBU_GUID@@K@Z; TDSLSetArray<CDSLPropertySet,CDSLProperty>::Find(_GUID const &,ulong)
0x180064a36  mov     r15d, 3
0x180064a3c  test    rax, rax
0x180064a3f  jz      short loc_180064A4D
0x180064a41  cmp     [rax+30h], r15w
0x180064a46  jnz     short loc_180064A4D
0x180064a48  mov     edi, [rax+38h]
0x180064a4b  jmp     short loc_180064A50
0x180064a4d  or      edi, 0FFFFFFFFh
0x180064a50  mov     [rsp+168h+var_98], r8d
0x180064a58  mov     [rsp+168h+var_94], 1
0x180064a64  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x180064a6b  movaps  [rsp+168h+var_88], xmm0
0x180064a73  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x180064a7a  movaps  [rsp+168h+var_78], xmm1
0x180064a82  lea     rcx, [rsp+168h+pvarg]; pvarg
0x180064a8a  call    cs:__imp_VariantInit
0x180064a90  mov     word ptr [rsp+168h+pvarg], r15w
0x180064a99  and     edi, 0FFFFFFFDh
0x180064a9c  mov     dword ptr [rsp+168h+pvarg+8], edi
0x180064aa3  lea     rax, [rsp+168h+var_98]
0x180064aab  mov     [rsp+168h+var_C0], rax
0x180064ab3  mov     [rsp+168h+var_B8], 1
0x180064abe  movups  xmm0, xmmword ptr cs:DBPROPSET_DBINIT.Data1
0x180064ac5  movdqu  [rsp+168h+var_B4], xmm0
0x180064ace  mov     rcx, [rsp+168h+var_138]
0x180064ad3  add     rcx, 18h
0x180064ad7  lea     rdx, IID_IDBProperties
0x180064ade  call    ??$GetProviderPointer@VCDCM@@@@YAPEAXPEAV?$CComObject@VCDCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CDCM>(ATL::CComObject<CDCM> *,_GUID const &)
0x180064ae3  mov     r14, rax
0x180064ae6  mov     [rsp+168h+var_F0], rax
0x180064aeb  test    rax, rax
0x180064aee  jz      short loc_180064B22
0x180064af0  mov     rax, [rax]
0x180064af3  lea     r8, [rsp+168h+var_C0]
0x180064afb  mov     edx, 1
0x180064b00  mov     rcx, r14
0x180064b03  mov     rax, [rax+28h]
0x180064b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b0c  test    eax, eax
0x180064b0e  jns     short loc_180064B22
0x180064b10  xor     edx, edx; perrinfo
0x180064b12  xor     ecx, ecx; dwReserved
0x180064b14  call    cs:__imp_SetErrorInfo
0x180064b1a  jmp     short loc_180064B22
0x180064b1c  mov     r15d, 3
0x180064b22  mov     rcx, r12; this
0x180064b25  call    ?ShouldDoEnlistment@CDPO@@QEAA_NXZ; CDPO::ShouldDoEnlistment(void)
0x180064b2a  mov     rcx, [rsp+168h+var_138]
0x180064b2f  mov     [rcx+1DDh], al
0x180064b35  mov     rcx, [rsp+168h+var_120]
0x180064b3a  mov     rax, [rcx]
0x180064b3d  mov     rax, [rax+18h]
0x180064b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b46  mov     edi, eax
0x180064b48  mov     eax, [rsp+168h+var_130]
0x180064b4c  jmp     short loc_180064B56
0x180064b4e  mov     edi, eax
0x180064b50  mov     r15d, 3
0x180064b56  test    edi, edi
0x180064b58  jnz     loc_180064C41
0x180064b5e  mov     [r12+0C8h], eax
0x180064b66  mov     al, [r13+0F0h]
0x180064b6d  test    al, al
0x180064b6f  jnz     short loc_180064B86
0x180064b71  mov     rcx, [rsp+168h+var_138]
0x180064b76  add     rcx, 18h; this
0x180064b7a  call    ?CanIBePooled_ThreadingModel@CDCM@@QEAA_NXZ; CDCM::CanIBePooled_ThreadingModel(void)
0x180064b7f  mov     [r13+0F0h], al
0x180064b86  cmp     al, 1
0x180064b88  jnz     loc_180064C38
0x180064b8e  mov     rcx, [rsp+168h+var_138]
0x180064b93  add     rcx, 0D0h
0x180064b9a  movups  xmm0, xmmword ptr cs:CLSID_SCM.Data1
0x180064ba1  movdqu  xmmword ptr [rsp+168h+var_E8], xmm0
0x180064baa  mov     rax, [rcx]
0x180064bad  lea     rdx, [rsp+168h+var_E8]
0x180064bb5  mov     rax, [rax+18h]
0x180064bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064bbe  mov     edi, eax
0x180064bc0  test    eax, eax
0x180064bc2  js      short loc_180064C10
0x180064bc4  mov     r15, [rsp+168h+var_138]
0x180064bc9  mov     [rsp+168h+var_128], rbx
0x180064bce  lea     rdx, [rsp+168h+var_128]; void **
0x180064bd3  cmp     cs:?g_pfnNtCompareTokens@@3P6AJPEAX0PEAH@ZEA, rbx; long (*g_pfnNtCompareTokens)(void *,void *,int *)
0x180064bda  jz      short loc_180064BF5
0x180064bdc  call    ?GetCurrentToken@CDCMPool@@QEAAJPEAPEAX@Z; CDCMPool::GetCurrentToken(void * *)
0x180064be1  mov     edi, eax
0x180064be3  test    eax, eax
0x180064be5  js      short loc_180064C0C
0x180064be7  mov     rax, [rsp+168h+var_128]
0x180064bec  mov     [r15+208h], rax
0x180064bf3  jmp     short loc_180064C0C
0x180064bf5  call    ?GetCurrentSID@CDCMPool@@QEAAJPEAPEAX@Z; CDCMPool::GetCurrentSID(void * *)
0x180064bfa  mov     edi, eax
0x180064bfc  test    eax, eax
0x180064bfe  js      short loc_180064C0C
0x180064c00  mov     rax, [rsp+168h+var_128]
0x180064c05  mov     [r15+200h], rax
0x180064c0c  test    edi, edi
0x180064c0e  jns     short loc_180064C6D
0x180064c10  mov     rcx, [rsp+168h+var_120]
0x180064c15  mov     rax, [rcx]
0x180064c18  mov     rax, [rax+20h]
0x180064c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064c21  mov     dword ptr [rsi+2Ch], 4
0x180064c28  mov     rcx, [rsp+168h+var_138]
0x180064c2d  add     rcx, 18h; this
0x180064c31  call    ?RestoreErrorObject@CDCM@@QEAAXXZ; CDCM::RestoreErrorObject(void)
0x180064c36  jmp     short loc_180064C6D
0x180064c38  mov     dword ptr [rsi+2Ch], 2
0x180064c3f  jmp     short loc_180064C51
0x180064c41  mov     [r12+0C8h], edi
0x180064c49  test    edi, edi
0x180064c4b  js      short loc_180064C58
0x180064c4d  mov     [rsi+2Ch], r15d
0x180064c51  mov     edi, 80004005h
0x180064c56  jmp     short loc_180064C6D
  ... truncated ...
```
