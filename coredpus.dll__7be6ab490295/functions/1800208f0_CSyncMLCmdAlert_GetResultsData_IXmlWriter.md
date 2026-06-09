# CSyncMLCmdAlert::GetResultsData(IXmlWriter *)

- ea: `0x1800208f0`
- end: `0x180020b28`
- name: `?GetResultsData@CSyncMLCmdAlert@@UEAAJPEAUIXmlWriter@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(CSyncMLCmdAlert *__hidden this, struct IXmlWriter *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002590`
- `0x1800034d0`
- `0x180003cd0`
- `0x1800043c0`
- `0x180004780`
- `0x180004ab0`
- `0x18000e490`
- `0x1800145f0`
- `0x1800208f0`
- `0x180020f48`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020ae0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020ae0`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMUI_SyncMLAlertGetResults` at `0x180020998`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMUI_SyncMLAlertGetResults` at `0x180020998`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMUI_SyncMLAlertGetStatusCode` at `0x180020977`
- `ext-ms-win-devmgmt-dm-l1-1-0!DMUI_SyncMLAlertGetStatusCode` at `0x180020977`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdAlert::GetResultsData(CSyncMLCmdAlert *this, struct IXmlWriter *a2)
{
  int ResultsDataGeneric; // edi
  struct IXmlWriter *v5; // rdx
  CSyncMLCmd *v6; // rcx
  void (__fastcall ***v7)(_QWORD, __int64); // rax
  void (__fastcall ***v8)(_QWORD, __int64); // rbx
  unsigned int v9; // edi
  __int64 v10; // rcx
  int v11; // r15d
  const unsigned __int16 *ElementName; // rax
  int v13; // r8d
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v17; // [rsp+A8h] [rbp+48h] BYREF
  struct CSyncMLItem *v18; // [rsp+B0h] [rbp+50h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp+58h] BYREF

  v17 = 0;
  hMem = 0;
  v18 = 0;
  if ( !a2 )
  {
    ResultsDataGeneric = -2147467261;
    goto LABEL_23;
  }
  if ( (int)CSyncMLCmd::GetCmdPreExecHresult(this) < 0 )
    goto LABEL_4;
  if ( (unsigned int)CSyncMLCmdAlert::IsUIAlert(v6) )
  {
    if ( (unsigned int)CSyncMLCmd::IsInAtomic(this)
      && (int)CSyncMLCmd::GetCmdPreExecHresult(*((CSyncMLCmd **)this + 17)) < 0 )
    {
      v5 = a2;
      v6 = this;
LABEL_4:
      ResultsDataGeneric = CSyncMLCmd::GetResultsDataGeneric(v6, v5);
      goto LABEL_23;
    }
    ResultsDataGeneric = DMUI_SyncMLAlertGetStatusCode(*((_QWORD *)this + 26), &v17);
    if ( ResultsDataGeneric >= 0 )
    {
      ResultsDataGeneric = DMUI_SyncMLAlertGetResults(*((_QWORD *)this + 26), &hMem);
      if ( ResultsDataGeneric >= 0 )
      {
        if ( hMem )
        {
          v7 = (void (__fastcall ***)(_QWORD, __int64))operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
          v8 = v7;
          if ( !v7 )
          {
            ResultsDataGeneric = -2147024882;
            goto LABEL_23;
          }
          v7[1] = 0;
          *v7 = (void (__fastcall **)(_QWORD, __int64))&CSyncMLItem::`vftable';
          v7[2] = 0;
          v7[3] = 0;
          v7[8] = 0;
          v7[9] = 0;
          v7[10] = 0;
          v7[11] = 0;
          *((_DWORD *)v7 + 24) = 0;
          *((_DWORD *)v7 + 25) = 15;
          v7[13] = (void (__fastcall **)(_QWORD, __int64))2;
          *((_DWORD *)v7 + 28) = 0;
          v7[4] = 0;
          v7[5] = 0;
          *((_OWORD *)v7 + 3) = 0;
          v18 = (struct CSyncMLItem *)v7;
          ResultsDataGeneric = CSyncMLItem::SetData((HLOCAL *)v7, (const unsigned __int16 *)hMem);
          if ( ResultsDataGeneric < 0 )
            goto LABEL_21;
          v9 = 1;
        }
        else
        {
          v9 = 0;
          v8 = 0;
        }
        v10 = *((unsigned int *)this + 23);
        v11 = *(_DWORD *)(*((_QWORD *)this + 10) + 44LL);
        if ( (_DWORD)v10 == 73 )
          ElementName = (const unsigned __int16 *)*((_QWORD *)this + 14);
        else
          ElementName = (const unsigned __int16 *)GetElementName(v10);
        v13 = CSyncMLDPU::s_dwCurrClientCmdID++;
        ResultsDataGeneric = AddStatus(
                               a2,
                               v17,
                               v13,
                               CSyncMLDPU::s_dwCurrServerMsgID,
                               *((const unsigned __int16 **)this + 13),
                               ElementName,
                               0,
                               0,
                               &v18,
                               v9,
                               0,
                               v11);
        if ( !v8 )
          goto LABEL_23;
LABEL_21:
        (**v8)(v8, 1);
      }
    }
  }
  else
  {
    ResultsDataGeneric = 0;
  }
LABEL_23:
  LocalFree(hMem);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    LODWORD(v18) = ResultsDataGeneric;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)&byte_180036EC7,
      v14,
      v15,
      (__int64)&v18);
  }
  return (unsigned int)ResultsDataGeneric;
}

```

## disassembly

```asm
0x1800208f0  push    rbp
0x1800208f2  push    rbx
0x1800208f3  push    rsi
0x1800208f4  push    rdi
0x1800208f5  push    r12
0x1800208f7  push    r14
0x1800208f9  push    r15
0x1800208fb  mov     rbp, rsp
0x1800208fe  sub     rsp, 60h
0x180020902  xor     r12d, r12d
0x180020905  mov     r14, rdx
0x180020908  mov     [rbp+arg_8], r12d
0x18002090c  mov     rsi, rcx
0x18002090f  mov     [rbp+hMem], r12
0x180020913  mov     [rbp+arg_10], r12
0x180020917  test    rdx, rdx
0x18002091a  jnz     short loc_180020926
0x18002091c  mov     edi, 80004003h
0x180020921  jmp     loc_180020ADC
0x180020926  call    ?GetCmdPreExecHresult@CSyncMLCmd@@QEBAJXZ; CSyncMLCmd::GetCmdPreExecHresult(void)
0x18002092b  test    eax, eax
0x18002092d  jns     short loc_18002093B
0x18002092f  call    ?GetResultsDataGeneric@CSyncMLCmd@@IEBAJPEAUIXmlWriter@@@Z; CSyncMLCmd::GetResultsDataGeneric(IXmlWriter *)
0x180020934  mov     edi, eax
0x180020936  jmp     loc_180020ADC
0x18002093b  call    ?IsUIAlert@CSyncMLCmdAlert@@AEAAHXZ; CSyncMLCmdAlert::IsUIAlert(void)
0x180020940  test    eax, eax
0x180020942  jz      loc_180020AD9
0x180020948  mov     rcx, rsi; this
0x18002094b  call    ?IsInAtomic@CSyncMLCmd@@IEBAHXZ; CSyncMLCmd::IsInAtomic(void)
0x180020950  test    eax, eax
0x180020952  jz      short loc_18002096C
0x180020954  mov     rcx, [rsi+88h]; this
0x18002095b  call    ?GetCmdPreExecHresult@CSyncMLCmd@@QEBAJXZ; CSyncMLCmd::GetCmdPreExecHresult(void)
0x180020960  test    eax, eax
0x180020962  jns     short loc_18002096C
0x180020964  mov     rdx, r14
0x180020967  mov     rcx, rsi
0x18002096a  jmp     short loc_18002092F
0x18002096c  mov     rcx, [rsi+0D0h]
0x180020973  lea     rdx, [rbp+arg_8]
0x180020977  call    cs:__imp_DMUI_SyncMLAlertGetStatusCode
0x18002097e  nop     dword ptr [rax+rax+00h]
0x180020983  mov     edi, eax
0x180020985  test    eax, eax
0x180020987  js      loc_180020ADC
0x18002098d  mov     rcx, [rsi+0D0h]
0x180020994  lea     rdx, [rbp+hMem]
0x180020998  call    cs:__imp_DMUI_SyncMLAlertGetResults
0x18002099f  nop     dword ptr [rax+rax+00h]
0x1800209a4  mov     edi, eax
0x1800209a6  test    eax, eax
0x1800209a8  js      loc_180020ADC
0x1800209ae  cmp     [rbp+hMem], r12
0x1800209b2  jz      loc_180020A4A
0x1800209b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800209bf  mov     ecx, 78h ; 'x'; unsigned __int64
0x1800209c4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800209c9  mov     rbx, rax
0x1800209cc  test    rax, rax
0x1800209cf  jz      short loc_180020A40
0x1800209d1  mov     [rbx+8], r12
0x1800209d5  lea     rax, ??_7CSyncMLItem@@6B@; const CSyncMLItem::`vftable'
0x1800209dc  mov     [rbx], rax
0x1800209df  xorps   xmm0, xmm0
0x1800209e2  mov     [rbx+10h], r12
0x1800209e6  xor     eax, eax
0x1800209e8  mov     [rbx+18h], r12
0x1800209ec  mov     rcx, rbx; this
0x1800209ef  mov     [rbx+40h], r12
0x1800209f3  mov     [rbx+48h], r12
0x1800209f7  mov     [rbx+50h], r12
0x1800209fb  mov     [rbx+58h], r12
0x1800209ff  mov     [rbx+60h], r12d
0x180020a03  mov     dword ptr [rbx+64h], 0Fh
0x180020a0a  mov     qword ptr [rbx+68h], 2
0x180020a12  mov     [rbx+70h], r12d
0x180020a16  mov     [rbx+20h], rax
0x180020a1a  mov     [rbx+28h], rax
0x180020a1e  movups  xmmword ptr [rbx+30h], xmm0
0x180020a22  mov     rdx, [rbp+hMem]; unsigned __int16 *
0x180020a26  mov     [rbp+arg_10], rbx
0x180020a2a  call    ?SetData@CSyncMLItem@@QEAA?BJPEBG@Z; CSyncMLItem::SetData(ushort const *)
0x180020a2f  mov     edi, eax
0x180020a31  test    eax, eax
0x180020a33  js      loc_180020AC4
0x180020a39  mov     edi, 1
0x180020a3e  jmp     short loc_180020A50
0x180020a40  mov     edi, 8007000Eh
0x180020a45  jmp     loc_180020ADC
0x180020a4a  mov     edi, r12d
0x180020a4d  mov     rbx, r12
0x180020a50  mov     rax, [rsi+50h]
0x180020a54  mov     ecx, [rsi+5Ch]
0x180020a57  mov     r15d, [rax+2Ch]
0x180020a5b  cmp     ecx, 49h ; 'I'
0x180020a5e  jnz     short loc_180020A66
0x180020a60  mov     rax, [rsi+70h]
0x180020a64  jmp     short loc_180020A6B
0x180020a66  call    GetElementName
0x180020a6b  mov     r8d, cs:?s_dwCurrClientCmdID@CSyncMLDPU@@0KA; unsigned int
0x180020a72  mov     r9d, cs:?s_dwCurrServerMsgID@CSyncMLDPU@@0KA; unsigned int
0x180020a79  mov     edx, [rbp+arg_8]; unsigned int
0x180020a7c  mov     [rsp+60h+var_8], r15d; int
0x180020a81  mov     [rsp+60h+var_10], r12d; int
0x180020a86  lea     ecx, [r8+1]
0x180020a8a  mov     [rsp+60h+var_18], edi; unsigned int
0x180020a8e  mov     cs:?s_dwCurrClientCmdID@CSyncMLDPU@@0KA, ecx; ulong CSyncMLDPU::s_dwCurrClientCmdID
0x180020a94  lea     rcx, [rbp+arg_10]
0x180020a98  mov     [rsp+60h+var_20], rcx; struct CSyncMLItem **
0x180020a9d  mov     rcx, r14; struct IXmlWriter *
0x180020aa0  mov     [rsp+60h+var_28], r12; unsigned __int16 *
0x180020aa5  mov     [rsp+60h+var_30], r12; unsigned __int16 *
0x180020aaa  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x180020aaf  mov     rax, [rsi+68h]
0x180020ab3  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x180020ab8  call    ?AddStatus@@YAJPEAUIXmlWriter@@KKKPEBG111PEAPEAVCSyncMLItem@@KJH@Z; AddStatus(IXmlWriter *,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,CSyncMLItem * *,ulong,long,int)
0x180020abd  mov     edi, eax
0x180020abf  test    rbx, rbx
0x180020ac2  jz      short loc_180020ADC
0x180020ac4  mov     rax, [rbx]
0x180020ac7  mov     edx, 1
0x180020acc  mov     rcx, rbx
0x180020acf  mov     rax, [rax]
0x180020ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ad7  jmp     short loc_180020ADC
0x180020ad9  mov     edi, r12d
0x180020adc  mov     rcx, [rbp+hMem]; hMem
0x180020ae0  call    cs:__imp_LocalFree
0x180020ae7  nop     dword ptr [rax+rax+00h]
0x180020aec  mov     eax, cs:dword_18003E048
0x180020af2  cmp     eax, 5
0x180020af5  jbe     short loc_180020B16
0x180020af7  lea     rax, [rbp+arg_10]
0x180020afb  mov     dword ptr [rbp+arg_10], edi
0x180020afe  lea     rdx, byte_180036EC7
0x180020b05  mov     [rsp+60h+var_40], rax
0x180020b0a  lea     rcx, dword_18003E048
0x180020b11  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180020b16  mov     eax, edi
0x180020b18  add     rsp, 60h
0x180020b1c  pop     r15
0x180020b1e  pop     r14
0x180020b20  pop     r12
0x180020b22  pop     rdi
0x180020b23  pop     rsi
0x180020b24  pop     rbx
0x180020b25  pop     rbp
0x180020b26  retn
```
