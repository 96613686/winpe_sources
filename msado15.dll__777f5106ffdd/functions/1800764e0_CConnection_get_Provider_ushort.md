# CConnection::get_Provider(ushort * *)

- ea: `0x1800764e0`
- end: `0x1800767e6`
- name: `?get_Provider@CConnection@@UEAAJPEAPEAG@Z`
- size: `774`
- prototype: `__int64 __fastcall(CConnection *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x1800767f0`

## callees

- `0x180009240`
- `0x18001a820`
- `0x180020de0`
- `0x180020e20`
- `0x180027790`
- `0x18002ec00`
- `0x180045580`
- `0x18004f330`
- `0x18005b950`
- `0x1800627e8`
- `0x18006a22c`
- `0x1800764e0`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x18007652d`
- `MSDART!UMSEnterCSWraper` at `0x18007652d`
- `KERNEL32!LeaveCriticalSection` at `0x1800767a2`
- `KERNEL32!LeaveCriticalSection` at `0x1800767a2`
- `ole32!CoTaskMemFree` at `0x18007676d`
- `ole32!CoTaskMemFree` at `0x18007676d`

## pseudocode

```c
__int64 __fastcall CConnection::get_Provider(CConnection *this, unsigned __int16 **a2)
{
  __int64 v4; // r8
  unsigned int BidObjectID; // eax
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-29h]
  __int64 v14; // [rsp+30h] [rbp-19h] BYREF
  char v15; // [rsp+38h] [rbp-11h]
  __int64 v16; // [rsp+40h] [rbp-9h] BYREF
  char v17; // [rsp+48h] [rbp-1h]
  unsigned __int16 *v18; // [rsp+50h] [rbp+7h] BYREF
  char v19; // [rsp+58h] [rbp+Fh]
  _BYTE v20[32]; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int64 v21; // [rsp+80h] [rbp+37h]
  unsigned int v22; // [rsp+88h] [rbp+3Fh]
  int DataInit; // [rsp+B0h] [rbp+67h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp+77h] BYREF

  v21 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  CContext::Init((CContext *)v20);
  v18 = 0;
  v19 = 5;
  UMSEnterCSWraper((char *)this + 1200);
  if ( !*((_QWORD *)this + 121) )
  {
    if ( (*((_BYTE *)this + 360) & 4) != 0 )
      v9 = *((_QWORD *)this + 44);
    else
      v9 = 0;
    CSysString::operator=(&v18, v9);
    goto LABEL_30;
  }
  pv = 0;
  v16 = 0;
  v17 = 7;
  v14 = 0;
  v15 = 7;
  DataInit = CConnection::GetDataInit(this);
  if ( (unsigned int)CContext::Failed((CContext *)v20, &DataInit) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        v6 = 4850697;
        v13 = 4737;
LABEL_21:
        bidTraceW(off_18012A1C0[0], v6, L"<CConnection::get_Provider|ADO|ERR> %u#, line %d\n", BidObjectID, v13);
        goto LABEL_24;
      }
      v7 = 4737;
      v8 = 4850697;
      goto LABEL_23;
    }
  }
  else
  {
    LOBYTE(v4) = 1;
    DataInit = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, LPVOID *))(**((_QWORD **)this + 124) + 32LL))(
                 *((_QWORD *)this + 124),
                 *((_QWORD *)this + 121),
                 v4,
                 &pv);
    if ( (unsigned int)CContext::Failed((CContext *)v20, &DataInit) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          v6 = 4851721;
          v13 = 4738;
          goto LABEL_21;
        }
        v7 = 4738;
        v8 = 4851721;
LABEL_23:
        bidTraceW(off_18012A1C0[0], v8, L"<CConnection::get_Provider|ADO|ERR>  line %d\n", v7);
      }
    }
    else
    {
      CMPString::operator=(&v16, pv);
      if ( (unsigned int)CContext::StringFailed((CContext *)v20, (const struct CMPString *)&v16) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            v6 = 4854793;
            v13 = 4741;
            goto LABEL_21;
          }
          v7 = 4741;
          v8 = 4854793;
          goto LABEL_23;
        }
      }
      else
      {
        CConnection::GetProviderName(this, (const struct CMPString *)&v16, (struct CMPString *)&v14);
        if ( !(unsigned int)CContext::StringFailed((CContext *)v20, (const struct CMPString *)&v14) )
        {
          CSysString::operator=(&v18, v14 & -(__int64)((v15 & 4) != 0));
          CoTaskMemFree(pv);
          goto LABEL_24;
        }
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            v6 = 4857865;
            v13 = 4744;
            goto LABEL_21;
          }
          v7 = 4744;
          v8 = 4857865;
          goto LABEL_23;
        }
      }
    }
  }
LABEL_24:
  CMPString::~CMPString((CMPString *)&v14);
  CMPString::~CMPString((CMPString *)&v16);
LABEL_30:
  v10 = *((_QWORD *)this + 150);
  --*(_DWORD *)(v10 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 8));
  if ( (v19 & 4) != 0 )
    *a2 = v18;
  v11 = v22;
  CSysString::~CSysString((CSysString *)&v18);
  CContext::~CContext((CContext *)v20);
  return v11;
}

```

## disassembly

```asm
0x1800764e0  mov     [rsp-8+arg_8], rbx
0x1800764e5  push    rbp
0x1800764e6  push    rsi
0x1800764e7  push    rdi
0x1800764e8  lea     rbp, [rsp-47h]
0x1800764ed  sub     rsp, 90h
0x1800764f4  mov     rax, rcx
0x1800764f7  lea     r9, [rcx+20h]
0x1800764fb  neg     rax
0x1800764fe  mov     rbx, rcx
0x180076501  lea     rcx, [rbp+57h+var_40]; this
0x180076505  mov     rsi, rdx
0x180076508  sbb     r8, r8
0x18007650b  and     r8, r9
0x18007650e  mov     [rbp+57h+var_20], r8
0x180076512  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x180076517  lea     rdi, [rbx+4B0h]
0x18007651e  mov     [rbp+57h+var_50], 0
0x180076526  mov     rcx, rdi
0x180076529  mov     [rbp+57h+var_48], 5
0x18007652d  call    cs:__imp_UMSEnterCSWraper
0x180076534  nop     dword ptr [rax+rax+00h]
0x180076539  cmp     qword ptr [rbx+3C8h], 0
0x180076541  jz      loc_18007677B
0x180076547  mov     rcx, rbx; this
0x18007654a  mov     [rbp+57h+pv], 0
0x180076552  mov     [rbp+57h+var_60], 0
0x18007655a  mov     [rbp+57h+var_58], 7
0x18007655e  mov     [rbp+57h+var_70], 0
0x180076566  mov     [rbp+57h+var_68], 7
0x18007656a  call    ?GetDataInit@CConnection@@QEAAJXZ; CConnection::GetDataInit(void)
0x18007656f  lea     rdx, [rbp+57h+arg_0]; int *
0x180076573  mov     [rbp+57h+arg_0], eax
0x180076576  lea     rcx, [rbp+57h+var_40]; this
0x18007657a  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18007657f  test    eax, eax
0x180076581  jz      short loc_1800765CF
0x180076583  test    byte ptr cs:_bidGblFlags, 2
0x18007658a  jz      loc_18007673E
0x180076590  lea     rcx, [rbx+100h]; this
0x180076597  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007659c  cmp     eax, 0FFFFFFFFh
0x18007659f  jz      short loc_1800765BF
0x1800765a1  lea     rcx, [rbx+100h]; this
0x1800765a8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800765ad  mov     edx, 4A0409h
0x1800765b2  mov     [rsp+0A0h+var_80], 1281h
0x1800765ba  jmp     loc_180076708
0x1800765bf  mov     r9d, 1281h
0x1800765c5  mov     edx, 4A0409h
0x1800765ca  jmp     loc_18007672B
0x1800765cf  mov     rcx, [rbx+3E0h]
0x1800765d6  lea     r9, [rbp+57h+pv]
0x1800765da  mov     rdx, [rbx+3C8h]
0x1800765e1  mov     r8b, 1
0x1800765e4  mov     rax, [rcx]
0x1800765e7  mov     rax, [rax+20h]
0x1800765eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800765f0  lea     rdx, [rbp+57h+arg_0]; int *
0x1800765f4  mov     [rbp+57h+arg_0], eax
0x1800765f7  lea     rcx, [rbp+57h+var_40]; this
0x1800765fb  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180076600  test    eax, eax
0x180076602  jz      short loc_180076650
0x180076604  test    byte ptr cs:_bidGblFlags, 2
0x18007660b  jz      loc_18007673E
0x180076611  lea     rcx, [rbx+100h]; this
0x180076618  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007661d  cmp     eax, 0FFFFFFFFh
0x180076620  jz      short loc_180076640
0x180076622  lea     rcx, [rbx+100h]; this
0x180076629  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007662e  mov     edx, 4A0809h
0x180076633  mov     [rsp+0A0h+var_80], 1282h
0x18007663b  jmp     loc_180076708
0x180076640  mov     r9d, 1282h
0x180076646  mov     edx, 4A0809h
0x18007664b  jmp     loc_18007672B
0x180076650  mov     rdx, [rbp+57h+pv]
0x180076654  lea     rcx, [rbp+57h+var_60]
0x180076658  call    ??4CMPString@@QEAAAEBV0@PEBG@Z; CMPString::operator=(ushort const *)
0x18007665d  lea     rdx, [rbp+57h+var_60]; struct CMPString *
0x180076661  lea     rcx, [rbp+57h+var_40]; this
0x180076665  call    ?StringFailed@CContext@@QEAAHAEBVCMPString@@@Z; CContext::StringFailed(CMPString const &)
0x18007666a  test    eax, eax
0x18007666c  jz      short loc_1800766B4
0x18007666e  test    byte ptr cs:_bidGblFlags, 2
0x180076675  jz      loc_18007673E
0x18007667b  lea     rcx, [rbx+100h]; this
0x180076682  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180076687  cmp     eax, 0FFFFFFFFh
0x18007668a  jz      short loc_1800766A7
0x18007668c  lea     rcx, [rbx+100h]; this
0x180076693  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180076698  mov     edx, 4A1409h
0x18007669d  mov     [rsp+0A0h+var_80], 1285h
0x1800766a5  jmp     short loc_180076708
0x1800766a7  mov     r9d, 1285h
0x1800766ad  mov     edx, 4A1409h
0x1800766b2  jmp     short loc_18007672B
0x1800766b4  lea     r8, [rbp+57h+var_70]; struct CMPString *
0x1800766b8  mov     rcx, rbx; this
0x1800766bb  lea     rdx, [rbp+57h+var_60]; struct CMPString *
0x1800766bf  call    ?GetProviderName@CConnection@@QEAAJAEBVCMPString@@AEAV2@@Z; CConnection::GetProviderName(CMPString const &,CMPString &)
0x1800766c4  lea     rdx, [rbp+57h+var_70]; struct CMPString *
0x1800766c8  lea     rcx, [rbp+57h+var_40]; this
0x1800766cc  call    ?StringFailed@CContext@@QEAAHAEBVCMPString@@@Z; CContext::StringFailed(CMPString const &)
0x1800766d1  test    eax, eax
0x1800766d3  jz      short loc_180076752
0x1800766d5  test    byte ptr cs:_bidGblFlags, 2
0x1800766dc  jz      short loc_18007673E
0x1800766de  lea     rcx, [rbx+100h]; this
0x1800766e5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800766ea  cmp     eax, 0FFFFFFFFh
0x1800766ed  jz      short loc_180076720
0x1800766ef  lea     rcx, [rbx+100h]; this
0x1800766f6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800766fb  mov     edx, 4A2009h
0x180076700  mov     [rsp+0A0h+var_80], 1288h
0x180076708  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18007670f  lea     r8, aCconnectionGet_5; "<CConnection::get_Provider|ADO|ERR> %u#"...
0x180076716  mov     r9d, eax
0x180076719  call    _bidTraceW
0x18007671e  jmp     short loc_18007673E
0x180076720  mov     r9d, 1288h
0x180076726  mov     edx, 4A2009h
0x18007672b  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180076732  lea     r8, aCconnectionGet_18; "<CConnection::get_Provider|ADO|ERR>  li"...
0x180076739  call    _bidTraceW
0x18007673e  lea     rcx, [rbp+57h+var_70]; this
0x180076742  call    ??1CMPString@@QEAA@XZ; CMPString::~CMPString(void)
0x180076747  lea     rcx, [rbp+57h+var_60]; this
0x18007674b  call    ??1CMPString@@QEAA@XZ; CMPString::~CMPString(void)
0x180076750  jmp     short loc_180076798
0x180076752  mov     al, [rbp+57h+var_68]
0x180076755  lea     rcx, [rbp+57h+var_50]
0x180076759  and     al, 4
0x18007675b  neg     al
0x18007675d  sbb     rdx, rdx
0x180076760  and     rdx, [rbp+57h+var_70]
0x180076764  call    ??4CSysString@@QEAAAEBV0@PEBG@Z; CSysString::operator=(ushort const *)
0x180076769  mov     rcx, [rbp+57h+pv]; pv
0x18007676d  call    cs:__imp_CoTaskMemFree
0x180076774  nop     dword ptr [rax+rax+00h]
0x180076779  jmp     short loc_18007673E
0x18007677b  test    byte ptr [rbx+168h], 4
0x180076782  jz      short loc_18007678D
0x180076784  mov     rdx, [rbx+160h]
0x18007678b  jmp     short loc_18007678F
0x18007678d  xor     edx, edx
0x18007678f  lea     rcx, [rbp+57h+var_50]
0x180076793  call    ??4CSysString@@QEAAAEBV0@PEBG@Z; CSysString::operator=(ushort const *)
0x180076798  mov     rcx, [rdi]
0x18007679b  dec     dword ptr [rcx+30h]
0x18007679e  add     rcx, 8; lpCriticalSection
0x1800767a2  call    cs:__imp_LeaveCriticalSection
0x1800767a9  nop     dword ptr [rax+rax+00h]
0x1800767ae  test    [rbp+57h+var_48], 4
0x1800767b2  jz      short loc_1800767BB
0x1800767b4  mov     rax, [rbp+57h+var_50]
0x1800767b8  mov     [rsi], rax
0x1800767bb  mov     ebx, [rbp+57h+var_18]
0x1800767be  lea     rcx, [rbp+57h+var_50]; this
0x1800767c2  call    ??1CSysString@@QEAA@XZ; CSysString::~CSysString(void)
0x1800767c7  lea     rcx, [rbp+57h+var_40]; this
0x1800767cb  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x1800767d0  mov     eax, ebx
0x1800767d2  mov     rbx, [rsp+0A0h+arg_8]
0x1800767da  add     rsp, 90h
0x1800767e1  pop     rdi
0x1800767e2  pop     rsi
0x1800767e3  pop     rbp
0x1800767e4  retn
```
