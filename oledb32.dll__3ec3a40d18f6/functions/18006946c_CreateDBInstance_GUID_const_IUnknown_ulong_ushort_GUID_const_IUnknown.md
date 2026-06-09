# CreateDBInstance(_GUID const &,IUnknown *,ulong,ushort *,_GUID const &,IUnknown * *)

- ea: `0x18006946c`
- end: `0x180069744`
- name: `?CreateDBInstance@@YAJAEBU_GUID@@PEAUIUnknown@@KPEAG0PEAPEAU2@@Z`
- size: `728`
- prototype: `__int64 __fastcall(const struct _GUID *, struct IUnknown *, unsigned int, unsigned __int16 *, IID *riid, struct IUnknown **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021610`

## callees

- `0x180013870`
- `0x180014674`
- `0x1800285d8`
- `0x180029560`
- `0x18002ec0c`
- `0x18005640c`
- `0x18005b5c8`
- `0x18006946c`

## string_xrefs

- `0x1800694c5`: `<CreateDBInstance|OLEDB|ERR> `
- `0x1800694e3`: `<CreateDBInstance|OLEDB|ERR> `
- `0x180069580`: `<CreateDBInstance|OLEDB|ERR> `
- `0x18006959e`: `<CreateDBInstance|OLEDB|ERR> `
- `0x180069605`: `<CreateDBInstance|OLEDB|ERR> `
- `0x18006967f`: `<CreateDBInstance|OLEDB|ERR> `
- `0x18006969d`: `<CreateDBInstance|OLEDB|ERR> `
- `0x1800694fe`: `<CreateDBInstance|Trace|HR> `
- `0x1800695b9`: `<CreateDBInstance|Trace|HR> `
- `0x180069620`: `<CreateDBInstance|Trace|HR> `
- `0x1800696b8`: `<CreateDBInstance|Trace|HR> `
- `0x18006971c`: `<CreateDBInstance|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CreateDBInstance(
        const struct _GUID *a1,
        struct IUnknown *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        IID *riid,
        struct IUnknown **a6)
{
  int ProviderInfoFromCLSID; // edi
  CCMProviderInfo *v10; // rbx
  int DPO; // edi
  int v12; // edi
  int v15; // ebx
  int pExceptionObject; // [rsp+30h] [rbp-58h] BYREF
  int v17; // [rsp+34h] [rbp-54h] BYREF
  int v18; // [rsp+38h] [rbp-50h] BYREF
  int v19; // [rsp+3Ch] [rbp-4Ch] BYREF
  _DWORD v20[2]; // [rsp+40h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-40h] BYREF
  CCMProviderInfo *v22; // [rsp+50h] [rbp-38h] BYREF

  v22 = 0;
  ppv = 0;
  try
  {
    ProviderInfoFromCLSID = CCMProviderInfoManager::GetProviderInfoFromCLSID(_ProviderInitInfoMap, a1, a3, 0, &v22);
    if ( ProviderInfoFromCLSID < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(ProviderInfoFromCLSID, L"<CreateDBInstance|OLEDB|ERR> ", 0x700u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(ProviderInfoFromCLSID, L"<CreateDBInstance|OLEDB|ERR> ", 0x700u);
          if ( (bidGblFlags & 2) != 0 )
            ProviderInfoFromCLSID = bidTraceHR(
                                      off_1800C8468[0],
                                      1835017,
                                      L"<CreateDBInstance|Trace|HR> ",
                                      (unsigned int)ProviderInfoFromCLSID);
        }
      }
      pExceptionObject = ProviderInfoFromCLSID;
      throw (long *)&pExceptionObject;
    }
    v10 = v22;
    if ( *((_BYTE *)v22 + 17) )
    {
      DPO = CreateDPO(v22, a2, a3, a4, riid, (struct IUnknown **)&ppv);
      if ( DPO < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(DPO, L"<CreateDBInstance|OLEDB|ERR> ", 0x706u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(DPO, L"<CreateDBInstance|OLEDB|ERR> ", 0x706u);
            if ( (bidGblFlags & 2) != 0 )
              DPO = bidTraceHR(off_1800C8468[0], 1841161, L"<CreateDBInstance|Trace|HR> ", (unsigned int)DPO);
          }
        }
        v17 = DPO;
        throw (long *)&v17;
      }
    }
    else
    {
      if ( *((_BYTE *)v22 + 18) )
      {
        v12 = -2147217886;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147217886, L"<CreateDBInstance|OLEDB|ERR> ", 0x711u);
          if ( (bidGblFlags & 2) != 0 )
            v12 = bidTraceHR(off_1800C8468[0], 1852425, L"<CreateDBInstance|Trace|HR> ", 2147749410LL);
        }
        v18 = v12;
        throw (long *)&v18;
      }
      DPO = CCMProviderInfo::CreateProvider(v22, a2, riid, &ppv);
      if ( DPO < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(DPO, L"<CreateDBInstance|OLEDB|ERR> ", 0x714u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(DPO, L"<CreateDBInstance|OLEDB|ERR> ", 0x714u);
            if ( (bidGblFlags & 2) != 0 )
              DPO = bidTraceHR(off_1800C8468[0], 1855497, L"<CreateDBInstance|Trace|HR> ", (unsigned int)DPO);
          }
        }
        v19 = DPO;
        throw (long *)&v19;
      }
    }
    *a6 = (struct IUnknown *)ppv;
  }
  catch ( long v20 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1800C8A88[0] )
    {
      v15 = v20[0];
      bidTraceA(off_1800C8468[0], 1862656, off_1800C8A88[0], v20[0]);
    }
    else
    {
      v15 = v20[0];
    }
    v20[1] = v15;
    DPO = v15;
    v10 = v22;
  }
  if ( v10 )
    CCMProviderInfo::Release(v10);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C8468[0], 1869833, L"<CreateDBInstance|Trace|HR> ", (unsigned int)DPO);
  return (unsigned int)DPO;
}

```

## disassembly

```asm
0x18006946c  mov     r11, rsp
0x18006946f  push    rbx
0x180069470  push    rsi
0x180069471  push    rdi
0x180069472  push    r14
0x180069474  push    r15
0x180069476  sub     rsp, 60h
0x18006947a  mov     r15, r9
0x18006947d  mov     r14d, r8d
0x180069480  mov     rsi, rdx
0x180069483  mov     qword ptr [r11-38h], 0
0x18006948b  mov     qword ptr [r11-40h], 0
0x180069493  lea     rax, [r11-38h]
0x180069497  mov     [r11-68h], rax
0x18006949b  xor     r9d, r9d; unsigned __int16 *
0x18006949e  mov     rdx, rcx; struct _GUID *
0x1800694a1  mov     rcx, cs:?_ProviderInitInfoMap@@3PEAVCCMProviderInfoManager@@EA; this
0x1800694a8  call    ?GetProviderInfoFromCLSID@CCMProviderInfoManager@@QEAAJAEBU_GUID@@KPEBGPEAPEAVCCMProviderInfo@@@Z; CCMProviderInfoManager::GetProviderInfoFromCLSID(_GUID const &,ulong,ushort const *,CCMProviderInfo * *)
0x1800694ad  mov     edi, eax
0x1800694af  test    eax, eax
0x1800694b1  jns     short loc_18006952D
0x1800694b3  mov     eax, cs:_bidGblFlags
0x1800694b9  mov     bl, 2
0x1800694bb  test    bl, al
0x1800694bd  jz      short loc_180069518
0x1800694bf  mov     r8d, 700h; unsigned int
0x1800694c5  lea     rdx, aCreatedbinstan_1; "<CreateDBInstance|OLEDB|ERR> "
0x1800694cc  mov     ecx, edi; int
0x1800694ce  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800694d3  mov     eax, cs:_bidGblFlags
0x1800694d9  test    bl, al
0x1800694db  jz      short loc_180069518
0x1800694dd  mov     r8d, 700h; unsigned int
0x1800694e3  lea     rdx, aCreatedbinstan_1; "<CreateDBInstance|OLEDB|ERR> "
0x1800694ea  mov     ecx, edi; int
0x1800694ec  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800694f1  mov     eax, cs:_bidGblFlags
0x1800694f7  test    bl, al
0x1800694f9  jz      short loc_180069518
0x1800694fb  mov     r9d, edi
0x1800694fe  lea     r8, aCreatedbinstan_0; "<CreateDBInstance|Trace|HR> "
0x180069505  mov     edx, 1C0009h
0x18006950a  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180069511  call    _bidTraceHR
0x180069516  mov     edi, eax
0x180069518  mov     [rsp+88h+pExceptionObject], edi
0x18006951c  lea     rdx, _TI1J; pThrowInfo
0x180069523  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180069528  call    _CxxThrowException_0
0x18006952d  mov     rbx, [rsp+88h+var_38]
0x180069532  cmp     byte ptr [rbx+11h], 0
0x180069536  jz      loc_1800695E8
0x18006953c  lea     rax, [rsp+88h+ppv]
0x180069541  mov     [rsp+88h+var_60], rax; struct IUnknown **
0x180069546  mov     rax, [rsp+88h+riid]
0x18006954e  mov     [rsp+88h+var_68], rax; struct _GUID *
0x180069553  mov     r9, r15; unsigned __int16 *
0x180069556  mov     r8d, r14d; unsigned int
0x180069559  mov     rdx, rsi; struct IUnknown *
0x18006955c  mov     rcx, rbx; struct CCMProviderInfo *
0x18006955f  call    ?CreateDPO@@YAJPEAVCCMProviderInfo@@PEAUIUnknown@@KPEAGAEBU_GUID@@PEAPEAU2@@Z; CreateDPO(CCMProviderInfo *,IUnknown *,ulong,ushort *,_GUID const &,IUnknown * *)
0x180069564  mov     edi, eax
0x180069566  test    eax, eax
0x180069568  jns     loc_1800696E7
0x18006956e  mov     eax, cs:_bidGblFlags
0x180069574  mov     bl, 2
0x180069576  test    bl, al
0x180069578  jz      short loc_1800695D3
0x18006957a  mov     r8d, 706h; unsigned int
0x180069580  lea     rdx, aCreatedbinstan_1; "<CreateDBInstance|OLEDB|ERR> "
0x180069587  mov     ecx, edi; int
0x180069589  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006958e  mov     eax, cs:_bidGblFlags
0x180069594  test    bl, al
0x180069596  jz      short loc_1800695D3
0x180069598  mov     r8d, 706h; unsigned int
0x18006959e  lea     rdx, aCreatedbinstan_1; "<CreateDBInstance|OLEDB|ERR> "
0x1800695a5  mov     ecx, edi; int
0x1800695a7  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800695ac  mov     eax, cs:_bidGblFlags
0x1800695b2  test    bl, al
0x1800695b4  jz      short loc_1800695D3
0x1800695b6  mov     r9d, edi
0x1800695b9  lea     r8, aCreatedbinstan_0; "<CreateDBInstance|Trace|HR> "
0x1800695c0  mov     edx, 1C1809h
0x1800695c5  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800695cc  call    _bidTraceHR
0x1800695d1  mov     edi, eax
0x1800695d3  mov     [rsp+88h+var_54], edi
0x1800695d7  lea     rdx, _TI1J; pThrowInfo
0x1800695de  lea     rcx, [rsp+88h+var_54]; pExceptionObject
0x1800695e3  call    _CxxThrowException_0
0x1800695e8  cmp     byte ptr [rbx+12h], 0
0x1800695ec  jz      short loc_18006964F
0x1800695ee  mov     eax, cs:_bidGblFlags
0x1800695f4  mov     bl, 2
0x1800695f6  mov     edi, 80040E22h
0x1800695fb  test    bl, al
0x1800695fd  jz      short loc_18006963A
0x1800695ff  mov     r8d, 711h; unsigned int
0x180069605  lea     rdx, aCreatedbinstan_1; "<CreateDBInstance|OLEDB|ERR> "
0x18006960c  mov     ecx, edi; int
0x18006960e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180069613  mov     eax, cs:_bidGblFlags
0x180069619  test    bl, al
0x18006961b  jz      short loc_18006963A
0x18006961d  mov     r9d, edi
0x180069620  lea     r8, aCreatedbinstan_0; "<CreateDBInstance|Trace|HR> "
0x180069627  mov     edx, 1C4409h
0x18006962c  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180069633  call    _bidTraceHR
0x180069638  mov     edi, eax
0x18006963a  mov     [rsp+88h+var_50], edi
0x18006963e  lea     rdx, _TI1J; pThrowInfo
0x180069645  lea     rcx, [rsp+88h+var_50]; pExceptionObject
0x18006964a  call    _CxxThrowException_0
0x18006964f  lea     r9, [rsp+88h+ppv]; ppv
0x180069654  mov     r8, [rsp+88h+riid]; riid
0x18006965c  mov     rdx, rsi; pUnkOuter
0x18006965f  mov     rcx, rbx; this
0x180069662  call    ?CreateProvider@CCMProviderInfo@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CCMProviderInfo::CreateProvider(IUnknown *,_GUID const &,void * *)
0x180069667  mov     edi, eax
0x180069669  test    eax, eax
0x18006966b  jns     short loc_1800696E7
0x18006966d  mov     eax, cs:_bidGblFlags
0x180069673  mov     bl, 2
0x180069675  test    bl, al
0x180069677  jz      short loc_1800696D2
0x180069679  mov     r8d, 714h; unsigned int
0x18006967f  lea     rdx, aCreatedbinstan_1; "<CreateDBInstance|OLEDB|ERR> "
0x180069686  mov     ecx, edi; int
0x180069688  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006968d  mov     eax, cs:_bidGblFlags
0x180069693  test    bl, al
0x180069695  jz      short loc_1800696D2
0x180069697  mov     r8d, 714h; unsigned int
0x18006969d  lea     rdx, aCreatedbinstan_1; "<CreateDBInstance|OLEDB|ERR> "
0x1800696a4  mov     ecx, edi; int
0x1800696a6  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800696ab  mov     eax, cs:_bidGblFlags
0x1800696b1  test    bl, al
0x1800696b3  jz      short loc_1800696D2
0x1800696b5  mov     r9d, edi
0x1800696b8  lea     r8, aCreatedbinstan_0; "<CreateDBInstance|Trace|HR> "
0x1800696bf  mov     edx, 1C5009h
0x1800696c4  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800696cb  call    _bidTraceHR
0x1800696d0  mov     edi, eax
0x1800696d2  mov     [rsp+88h+var_4C], edi
0x1800696d6  lea     rdx, _TI1J; pThrowInfo
0x1800696dd  lea     rcx, [rsp+88h+var_4C]; pExceptionObject
0x1800696e2  call    _CxxThrowException_0
0x1800696e7  mov     rcx, [rsp+88h+arg_28]
0x1800696ef  mov     rax, [rsp+88h+ppv]
0x1800696f4  mov     [rcx], rax
0x1800696f7  jmp     short loc_180069702
0x1800696f9  mov     edi, [rsp+88h+var_44]
0x1800696fd  mov     rbx, [rsp+88h+var_38]
0x180069702  test    rbx, rbx
0x180069705  jz      short loc_18006970F
0x180069707  mov     rcx, rbx; this
0x18006970a  call    ?Release@CCMProviderInfo@@QEAAKXZ; CCMProviderInfo::Release(void)
0x18006970f  mov     bl, 2
0x180069711  test    byte ptr cs:_bidGblFlags, bl
0x180069717  jz      short loc_180069736
0x180069719  mov     r9d, edi
0x18006971c  lea     r8, aCreatedbinstan_0; "<CreateDBInstance|Trace|HR> "
0x180069723  mov     edx, 1C8809h
0x180069728  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006972f  call    _bidTraceHR
0x180069734  mov     edi, eax
0x180069736  mov     eax, edi
0x180069738  add     rsp, 60h
0x18006973c  pop     r15
0x18006973e  pop     r14
0x180069740  pop     rdi
0x180069741  pop     rsi
0x180069742  pop     rbx
0x180069743  retn
```
