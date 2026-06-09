# CDCM::CreatePooledSession(_GUID)

- ea: `0x180072f30`
- end: `0x180073549`
- name: `?CreatePooledSession@CDCM@@UEAAJU_GUID@@@Z`
- size: `1561`
- prototype: `__int64 __fastcall(CDCM *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x180013870`
- `0x180022bf8`
- `0x180029560`
- `0x18002ec0c`
- `0x18003c2e8`
- `0x180072cec`
- `0x180072f30`
- `0x180073dec`
- `0x180087010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180072f6b`
- `KERNEL32!EnterCriticalSection` at `0x180072f6b`
- `KERNEL32!LeaveCriticalSection` at `0x180073503`
- `KERNEL32!LeaveCriticalSection` at `0x180073503`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180073211`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800733be`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180073211`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800733be`

## string_xrefs

- `0x180072f9b`: `<CDCM::CreatePooledSession|OLEDB|ERR> `
- `0x180072fd6`: `<CDCM::CreatePooledSession|OLEDB|ERR> `
- `0x180073035`: `<CDCM::CreatePooledSession|OLEDB|ERR> `
- `0x180073053`: `<CDCM::CreatePooledSession|OLEDB|ERR> `
- `0x1800730e1`: `<CDCM::CreatePooledSession|OLEDB|ERR> `
- `0x1800730ff`: `<CDCM::CreatePooledSession|OLEDB|ERR> `
- `0x18007317c`: `<CDCM::CreatePooledSession|OLEDB|ERR> `
- `0x18007319a`: `<CDCM::CreatePooledSession|OLEDB|ERR> `
- `0x18007322c`: `<CDCM::CreatePooledSession|OLEDB|ERR> `
- `0x1800732db`: `<CDCM::CreatePooledSession|OLEDB|ERR> `
- `0x1800732f9`: `<CDCM::CreatePooledSession|OLEDB|ERR> `
- `0x1800733d4`: `<CDCM::CreatePooledSession|OLEDB|ERR> `
- `0x18007306e`: `<CDCM::CreatePooledSession|Trace|HR> `
- `0x18007311a`: `<CDCM::CreatePooledSession|Trace|HR> `
- `0x1800731b5`: `<CDCM::CreatePooledSession|Trace|HR> `
- `0x180073247`: `<CDCM::CreatePooledSession|Trace|HR> `
- `0x180073314`: `<CDCM::CreatePooledSession|Trace|HR> `
- `0x1800733ef`: `<CDCM::CreatePooledSession|Trace|HR> `
- `0x180073515`: `<CDCM::CreatePooledSession|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CDCM::CreatePooledSession(unsigned __int64 this, struct _GUID *a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  _QWORD *v4; // r14
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  int CM; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  int v11; // ebx
  int v12; // edi
  int v13; // edi
  __int64 Provider; // rax
  __int64 v15; // r14
  int v16; // edi
  int v17; // edi
  __int64 v19; // [rsp+30h] [rbp-78h] BYREF
  int pExceptionObject; // [rsp+38h] [rbp-70h] BYREF
  int v21; // [rsp+3Ch] [rbp-6Ch] BYREF
  int v22; // [rsp+40h] [rbp-68h] BYREF
  int v23; // [rsp+44h] [rbp-64h] BYREF
  unsigned int v24; // [rsp+48h] [rbp-60h] BYREF
  int v25; // [rsp+4Ch] [rbp-5Ch] BYREF
  __int64 v26; // [rsp+58h] [rbp-50h] BYREF
  __int64 v27; // [rsp+60h] [rbp-48h]
  char *v28; // [rsp+68h] [rbp-40h]
  char *v29; // [rsp+70h] [rbp-38h]
  __int64 v30; // [rsp+C8h] [rbp+20h] BYREF

  v30 = 0;
  v19 = 0;
  v27 = 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)(this - 160);
  v28 = (char *)(this - 160);
  EnterCriticalSection((LPCRITICAL_SECTION)(this - 160));
  v4 = (_QWORD *)(this + 248);
  v29 = (char *)(this + 248);
  CM = NewCM<CSCM>::CoCreateCM(v6, v5, v7, this + 248);
  v9 = CM;
  if ( CM >= 0 )
  {
    v10 = *(_QWORD *)(this - 184 + 432);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
      *(_BYTE *)(this + 256) = 1;
      v26 = 0;
      if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v4)(*v4, &IID_IJoinSessionPool, &v26) < 0 )
      {
        v11 = -2147418113;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147418113, L"<CDCM::CreatePooledSession|OLEDB|ERR> ", 0xA9u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147418113, L"<CDCM::CreatePooledSession|OLEDB|ERR> ", 0xA9u);
            if ( (bidGblFlags & 2) != 0 )
              v11 = bidTraceHR(off_1800C84C8[0], 173065, L"<CDCM::CreatePooledSession|Trace|HR> ", 2147549183LL);
          }
        }
        pExceptionObject = v11;
        throw (long *)&pExceptionObject;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 24LL))(
              v26,
              this & ((unsigned __int128)-(__int128)(this - 184) >> 64));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v12 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v12, L"<CDCM::CreatePooledSession|OLEDB|ERR> ", 0xAEu);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v12, L"<CDCM::CreatePooledSession|OLEDB|ERR> ", 0xAEu);
            if ( (bidGblFlags & 2) != 0 )
              v12 = bidTraceHR(off_1800C84C8[0], 178185, L"<CDCM::CreatePooledSession|Trace|HR> ", (unsigned int)v12);
          }
        }
        v21 = v12;
        throw (long *)&v21;
      }
      v13 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v4)(*v4, &IID_IService, &v30);
      if ( v13 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v13, L"<CDCM::CreatePooledSession|OLEDB|ERR> ", 0xB2u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v13, L"<CDCM::CreatePooledSession|OLEDB|ERR> ", 0xB2u);
            if ( (bidGblFlags & 2) != 0 )
              v13 = bidTraceHR(off_1800C84C8[0], 182281, L"<CDCM::CreatePooledSession|Trace|HR> ", (unsigned int)v13);
          }
        }
        v22 = v13;
        throw (long *)&v22;
      }
      Provider = GetProviderPointer<CDCM>(this - 184, &IID_IDBCreateSession);
      v15 = Provider;
      v27 = Provider;
      if ( !Provider )
      {
        CDCM::ReleaseErrorObject((CDCM *)(this - 184));
        GetErrorInfo(0, (IErrorInfo **)(this + 296));
        v16 = -2147467259;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147467259, L"<CDCM::CreatePooledSession|OLEDB|ERR> ", 0xC3u);
          if ( (bidGblFlags & 2) != 0 )
            v16 = bidTraceHR(off_1800C84C8[0], 199689, L"<CDCM::CreatePooledSession|Trace|HR> ", 2147500037LL);
        }
        v23 = v16;
        throw (long *)&v23;
      }
      v17 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)Provider + 24LL))(
              Provider,
              v30,
              &IID_IUnknown,
              &v19);
      if ( v17 < 0 || !v19 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800C8CF8[0] )
          bidTraceA(off_1800C84C8[0], 206848, off_1800C8CF8[0], 0);
        CDCM::ReleaseErrorObject((CDCM *)(this - 184));
        GetErrorInfo(0, (IErrorInfo **)(this + 296));
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v17, L"<CDCM::CreatePooledSession|OLEDB|ERR> ", 0xD1u);
          if ( (bidGblFlags & 2) != 0 )
            v17 = bidTraceHR(off_1800C84C8[0], 214025, L"<CDCM::CreatePooledSession|Trace|HR> ", (unsigned int)v17);
        }
        v25 = v17;
        throw (long *)&v25;
      }
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 24LL))(v30);
      if ( (v9 & 0x80000000) != 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v9, L"<CDCM::CreatePooledSession|OLEDB|ERR> ", 0xD5u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v9, L"<CDCM::CreatePooledSession|OLEDB|ERR> ", 0xD5u);
            if ( (bidGblFlags & 2) != 0 )
              v9 = bidTraceHR(off_1800C84C8[0], 218121, L"<CDCM::CreatePooledSession|Trace|HR> ", v9);
          }
        }
        v24 = v9;
        throw (long *)&v24;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    else
    {
      v9 = -2147467259;
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(-2147467259, L"<CDCM::CreatePooledSession|OLEDB|ERR> ", 0x90u);
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(CM, L"<CDCM::CreatePooledSession|OLEDB|ERR> ", 0x8Au);
  }
  LeaveCriticalSection(v3);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C84C8[0], 248841, L"<CDCM::CreatePooledSession|Trace|HR> ", v9);
  return v9;
}

```

## disassembly

```asm
0x180072f30  mov     rax, rsp
0x180072f33  mov     [rax+10h], rbx
0x180072f37  mov     [rax+8], rcx
0x180072f3b  push    rsi
0x180072f3c  push    rdi
0x180072f3d  push    r12
0x180072f3f  push    r14
0x180072f41  push    r15
0x180072f43  sub     rsp, 80h
0x180072f4a  mov     rsi, rcx
0x180072f4d  xor     ebx, ebx
0x180072f4f  mov     [rax+20h], rbx
0x180072f53  mov     [rax-78h], rbx
0x180072f57  mov     [rsp+0A8h+var_48], rbx
0x180072f5c  lea     r12, [rcx-0A0h]
0x180072f63  mov     [rsp+0A8h+var_40], r12
0x180072f68  mov     rcx, r12; lpCriticalSection
0x180072f6b  call    cs:__imp_EnterCriticalSection
0x180072f71  nop
0x180072f72  lea     r14, [rsi+0F8h]
0x180072f79  mov     [rsp+0A8h+var_38], r14
0x180072f7e  mov     r9, r14
0x180072f81  call    ?CoCreateCM@?$NewCM@VCSCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z; NewCM<CSCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)
0x180072f86  mov     edi, eax
0x180072f88  test    eax, eax
0x180072f8a  jns     short loc_180072FAF
0x180072f8c  test    byte ptr cs:_bidGblFlags, 2
0x180072f93  jz      short loc_180072FAA
0x180072f95  mov     r8d, 8Ah; unsigned int
0x180072f9b  lea     rdx, aCdcmCreatepool; "<CDCM::CreatePooledSession|OLEDB|ERR> "
0x180072fa2  mov     ecx, eax; int
0x180072fa4  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180072fa9  nop
0x180072faa  jmp     loc_180073500
0x180072faf  lea     r15, [rsi-0B8h]
0x180072fb6  mov     rcx, [r15+1B0h]
0x180072fbd  test    rcx, rcx
0x180072fc0  jnz     short loc_180072FEA
0x180072fc2  mov     edi, 80004005h
0x180072fc7  test    byte ptr cs:_bidGblFlags, 2
0x180072fce  jz      short loc_180072FE5
0x180072fd0  mov     r8d, 90h; unsigned int
0x180072fd6  lea     rdx, aCdcmCreatepool; "<CDCM::CreatePooledSession|OLEDB|ERR> "
0x180072fdd  mov     ecx, edi; int
0x180072fdf  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180072fe4  nop
0x180072fe5  jmp     loc_180073500
0x180072fea  mov     rax, [rcx]
0x180072fed  mov     rax, [rax+8]
0x180072ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072ff6  mov     byte ptr [rsi+100h], 1
0x180072ffd  mov     [rsp+0A8h+var_50], rbx
0x180073002  mov     rcx, [r14]
0x180073005  mov     rax, [rcx]
0x180073008  lea     r8, [rsp+0A8h+var_50]
0x18007300d  lea     rdx, IID_IJoinSessionPool
0x180073014  mov     rax, [rax]
0x180073017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007301c  test    eax, eax
0x18007301e  jns     short loc_18007309D
0x180073020  mov     eax, cs:_bidGblFlags
0x180073026  mov     ebx, 8000FFFFh
0x18007302b  test    al, 2
0x18007302d  jz      short loc_180073088
0x18007302f  mov     r8d, 0A9h; unsigned int
0x180073035  lea     rdx, aCdcmCreatepool; "<CDCM::CreatePooledSession|OLEDB|ERR> "
0x18007303c  mov     ecx, ebx; int
0x18007303e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180073043  mov     eax, cs:_bidGblFlags
0x180073049  test    al, 2
0x18007304b  jz      short loc_180073088
0x18007304d  mov     r8d, 0A9h; unsigned int
0x180073053  lea     rdx, aCdcmCreatepool; "<CDCM::CreatePooledSession|OLEDB|ERR> "
0x18007305a  mov     ecx, ebx; int
0x18007305c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180073061  mov     eax, cs:_bidGblFlags
0x180073067  test    al, 2
0x180073069  jz      short loc_180073088
0x18007306b  mov     r9d, ebx
0x18007306e  lea     r8, aCdcmCreatepool_3; "<CDCM::CreatePooledSession|Trace|HR> "
0x180073075  mov     edx, 2A409h
0x18007307a  mov     rcx, cs:off_1800C84C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180073081  call    _bidTraceHR
0x180073086  mov     ebx, eax
0x180073088  mov     [rsp+0A8h+pExceptionObject], ebx
0x18007308c  lea     rdx, _TI1J; pThrowInfo
0x180073093  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180073098  call    _CxxThrowException_0
0x18007309d  mov     rcx, [rsp+0A8h+var_50]
0x1800730a2  mov     r8, [rcx]
0x1800730a5  mov     rax, r15
0x1800730a8  neg     rax
0x1800730ab  sbb     rdx, rdx
0x1800730ae  and     rdx, rsi
0x1800730b1  mov     rax, [r8+18h]
0x1800730b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800730ba  mov     edi, eax
0x1800730bc  mov     rcx, [rsp+0A8h+var_50]
0x1800730c1  mov     rax, [rcx]
0x1800730c4  mov     rax, [rax+10h]
0x1800730c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800730cd  test    edi, edi
0x1800730cf  jns     short loc_180073149
0x1800730d1  mov     eax, cs:_bidGblFlags
0x1800730d7  test    al, 2
0x1800730d9  jz      short loc_180073134
0x1800730db  mov     r8d, 0AEh; unsigned int
0x1800730e1  lea     rdx, aCdcmCreatepool; "<CDCM::CreatePooledSession|OLEDB|ERR> "
0x1800730e8  mov     ecx, edi; int
0x1800730ea  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800730ef  mov     eax, cs:_bidGblFlags
0x1800730f5  test    al, 2
0x1800730f7  jz      short loc_180073134
0x1800730f9  mov     r8d, 0AEh; unsigned int
0x1800730ff  lea     rdx, aCdcmCreatepool; "<CDCM::CreatePooledSession|OLEDB|ERR> "
0x180073106  mov     ecx, edi; int
0x180073108  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007310d  mov     eax, cs:_bidGblFlags
0x180073113  test    al, 2
0x180073115  jz      short loc_180073134
0x180073117  mov     r9d, edi
0x18007311a  lea     r8, aCdcmCreatepool_3; "<CDCM::CreatePooledSession|Trace|HR> "
0x180073121  mov     edx, 2B809h
0x180073126  mov     rcx, cs:off_1800C84C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18007312d  call    _bidTraceHR
0x180073132  mov     edi, eax
0x180073134  mov     [rsp+0A8h+var_6C], edi
0x180073138  lea     rdx, _TI1J; pThrowInfo
0x18007313f  lea     rcx, [rsp+0A8h+var_6C]; pExceptionObject
0x180073144  call    _CxxThrowException_0
0x180073149  mov     rcx, [r14]
0x18007314c  mov     rax, [rcx]
0x18007314f  lea     r8, [rsp+0A8h+arg_18]
0x180073157  lea     rdx, IID_IService
0x18007315e  mov     rax, [rax]
0x180073161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073166  mov     edi, eax
0x180073168  test    eax, eax
0x18007316a  jns     short loc_1800731E4
0x18007316c  mov     eax, cs:_bidGblFlags
0x180073172  test    al, 2
0x180073174  jz      short loc_1800731CF
0x180073176  mov     r8d, 0B2h; unsigned int
0x18007317c  lea     rdx, aCdcmCreatepool; "<CDCM::CreatePooledSession|OLEDB|ERR> "
0x180073183  mov     ecx, edi; int
0x180073185  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007318a  mov     eax, cs:_bidGblFlags
0x180073190  test    al, 2
0x180073192  jz      short loc_1800731CF
0x180073194  mov     r8d, 0B2h; unsigned int
0x18007319a  lea     rdx, aCdcmCreatepool; "<CDCM::CreatePooledSession|OLEDB|ERR> "
0x1800731a1  mov     ecx, edi; int
0x1800731a3  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800731a8  mov     eax, cs:_bidGblFlags
0x1800731ae  test    al, 2
0x1800731b0  jz      short loc_1800731CF
0x1800731b2  mov     r9d, edi
0x1800731b5  lea     r8, aCdcmCreatepool_3; "<CDCM::CreatePooledSession|Trace|HR> "
0x1800731bc  mov     edx, 2C809h
0x1800731c1  mov     rcx, cs:off_1800C84C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800731c8  call    _bidTraceHR
0x1800731cd  mov     edi, eax
0x1800731cf  mov     [rsp+0A8h+var_68], edi
0x1800731d3  lea     rdx, _TI1J; pThrowInfo
0x1800731da  lea     rcx, [rsp+0A8h+var_68]; pExceptionObject
0x1800731df  call    _CxxThrowException_0
0x1800731e4  lea     rdx, IID_IDBCreateSession
0x1800731eb  mov     rcx, r15
0x1800731ee  call    ??$GetProviderPointer@VCDCM@@@@YAPEAXPEAV?$CComObject@VCDCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CDCM>(ATL::CComObject<CDCM> *,_GUID const &)
0x1800731f3  mov     r14, rax
0x1800731f6  mov     [rsp+0A8h+var_48], rax
0x1800731fb  test    rax, rax
0x1800731fe  jnz     short loc_180073276
0x180073200  mov     rcx, r15; this
0x180073203  call    ?ReleaseErrorObject@CDCM@@QEAAXXZ; CDCM::ReleaseErrorObject(void)
0x180073208  lea     rdx, [rsi+128h]; pperrinfo
0x18007320f  xor     ecx, ecx; dwReserved
0x180073211  call    cs:__imp_GetErrorInfo
0x180073217  mov     eax, cs:_bidGblFlags
0x18007321d  mov     edi, 80004005h
0x180073222  test    al, 2
0x180073224  jz      short loc_180073261
0x180073226  mov     r8d, 0C3h; unsigned int
0x18007322c  lea     rdx, aCdcmCreatepool; "<CDCM::CreatePooledSession|OLEDB|ERR> "
0x180073233  mov     ecx, edi; int
0x180073235  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007323a  mov     eax, cs:_bidGblFlags
0x180073240  test    al, 2
0x180073242  jz      short loc_180073261
0x180073244  mov     r9d, edi
0x180073247  lea     r8, aCdcmCreatepool_3; "<CDCM::CreatePooledSession|Trace|HR> "
0x18007324e  mov     edx, 30C09h
0x180073253  mov     rcx, cs:off_1800C84C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18007325a  call    _bidTraceHR
0x18007325f  mov     edi, eax
0x180073261  mov     [rsp+0A8h+var_64], edi
0x180073265  lea     rdx, _TI1J; pThrowInfo
0x18007326c  lea     rcx, [rsp+0A8h+var_64]; pExceptionObject
0x180073271  call    _CxxThrowException_0
0x180073276  mov     rax, [rax]
0x180073279  lea     r9, [rsp+0A8h+var_78]
0x18007327e  lea     r8, IID_IUnknown
0x180073285  mov     rdx, [rsp+0A8h+arg_18]
0x18007328d  mov     rcx, r14
0x180073290  mov     rax, [rax+18h]
0x180073294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073299  mov     edi, eax
0x18007329b  test    eax, eax
0x18007329d  js      loc_18007337D
0x1800732a3  mov     rdx, [rsp+0A8h+var_78]
0x1800732a8  test    rdx, rdx
0x1800732ab  jz      loc_18007337D
0x1800732b1  mov     rcx, [rsp+0A8h+arg_18]
0x1800732b9  mov     rax, [rcx]
0x1800732bc  mov     rax, [rax+18h]
0x1800732c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800732c5  mov     edi, eax
0x1800732c7  test    eax, eax
0x1800732c9  jns     short loc_180073343
0x1800732cb  mov     eax, cs:_bidGblFlags
0x1800732d1  test    al, 2
0x1800732d3  jz      short loc_18007332E
0x1800732d5  mov     r8d, 0D5h; unsigned int
0x1800732db  lea     rdx, aCdcmCreatepool; "<CDCM::CreatePooledSession|OLEDB|ERR> "
0x1800732e2  mov     ecx, edi; int
0x1800732e4  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800732e9  mov     eax, cs:_bidGblFlags
0x1800732ef  test    al, 2
0x1800732f1  jz      short loc_18007332E
0x1800732f3  mov     r8d, 0D5h; unsigned int
0x1800732f9  lea     rdx, aCdcmCreatepool; "<CDCM::CreatePooledSession|OLEDB|ERR> "
0x180073300  mov     ecx, edi; int
0x180073302  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180073307  mov     eax, cs:_bidGblFlags
0x18007330d  test    al, 2
0x18007330f  jz      short loc_18007332E
0x180073311  mov     r9d, edi
0x180073314  lea     r8, aCdcmCreatepool_3; "<CDCM::CreatePooledSession|Trace|HR> "
0x18007331b  mov     edx, 35409h
0x180073320  mov     rcx, cs:off_1800C84C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180073327  call    _bidTraceHR
0x18007332c  mov     edi, eax
0x18007332e  mov     [rsp+0A8h+var_60], edi
0x180073332  lea     rdx, _TI1J; pThrowInfo
0x180073339  lea     rcx, [rsp+0A8h+var_60]; pExceptionObject
0x18007333e  call    _CxxThrowException_0
0x180073343  mov     rcx, [rsp+0A8h+arg_18]
0x18007334b  mov     rax, [rcx]
0x18007334e  mov     rax, [rax+10h]
0x180073352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073357  mov     rcx, [rsp+0A8h+var_78]
0x18007335c  mov     rax, [rcx]
0x18007335f  mov     rax, [rax+10h]
0x180073363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073368  mov     rax, [r14]
0x18007336b  mov     rcx, r14
0x18007336e  mov     rax, [rax+10h]
0x180073372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073377  nop
0x180073378  jmp     loc_180073500
0x18007337d  test    byte ptr cs:_bidGblFlags, 2
0x180073384  jz      short loc_1800733AD
0x180073386  mov     rax, cs:off_1800C8CF8; "<CDCM::CreatePooledSession|ERR> Failed "...
0x18007338d  test    rax, rax
0x180073390  jz      short loc_1800733AD
0x180073392  xor     r9d, r9d
0x180073395  mov     r8, cs:off_1800C8CF8; "<CDCM::CreatePooledSession|ERR> Failed "...
0x18007339c  mov     edx, 32800h
0x1800733a1  mov     rcx, cs:off_1800C84C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800733a8  call    _bidTraceA
0x1800733ad  mov     rcx, r15; this
0x1800733b0  call    ?ReleaseErrorObject@CDCM@@QEAAXXZ; CDCM::ReleaseErrorObject(void)
0x1800733b5  lea     rdx, [rsi+128h]; pperrinfo
0x1800733bc  xor     ecx, ecx; dwReserved
0x1800733be  call    cs:__imp_GetErrorInfo
0x1800733c4  mov     eax, cs:_bidGblFlags
0x1800733ca  test    al, 2
0x1800733cc  jz      short loc_180073409
0x1800733ce  mov     r8d, 0D1h; unsigned int
0x1800733d4  lea     rdx, aCdcmCreatepool; "<CDCM::CreatePooledSession|OLEDB|ERR> "
0x1800733db  mov     ecx, edi; int
0x1800733dd  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800733e2  mov     eax, cs:_bidGblFlags
0x1800733e8  test    al, 2
0x1800733ea  jz      short loc_180073409
0x1800733ec  mov     r9d, edi
0x1800733ef  lea     r8, aCdcmCreatepool_3; "<CDCM::CreatePooledSession|Trace|HR> "
0x1800733f6  mov     edx, 34409h
0x1800733fb  mov     rcx, cs:off_1800C84C8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180073402  call    _bidTraceHR
0x180073407  mov     edi, eax
0x180073409  mov     [rsp+0A8h+var_5C], edi
0x18007340d  lea     rdx, _TI1J; pThrowInfo
0x180073414  lea     rcx, [rsp+0A8h+var_5C]; pExceptionObject
0x180073419  call    _CxxThrowException_0
0x18007341f  jmp     short $+2
0x180073421  mov     rcx, [rsp+0A8h+var_78]
0x180073426  xor     ebx, ebx
0x180073428  test    rcx, rcx
0x18007342b  jz      short loc_180073439
  ... truncated ...
```
