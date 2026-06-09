# DusmConnection::EvaluateConnection(void)

- ea: `0x1800186fc`
- end: `0x180018a4a`
- name: `?EvaluateConnection@DusmConnection@@QEAAXXZ`
- size: `846`
- prototype: `void __fastcall(DusmConnection *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18001efd0`
- `0x18001f708`

## callees

- `0x180001294`
- `0x180002ae8`
- `0x18000310c`
- `0x180007c90`
- `0x18000f214`
- `0x180012fcc`
- `0x180013444`
- `0x1800173ac`
- `0x180018080`
- `0x1800186fc`
- `0x180019040`
- `0x1800193d8`
- `0x180019520`
- `0x18001b7c0`
- `0x18003e258`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800187d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800187d1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800187e5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800187e5`

## pseudocode

```c
void __fastcall DusmConnection::EvaluateConnection(DusmConnection *this)
{
  int v1; // r14d
  bool IsBackgroundRestricted; // al
  __int64 v4; // rcx
  int v5; // edi
  char v6; // r12
  int v7; // r8d
  __int64 v8; // rcx
  bool v9; // zf
  __int64 v10; // rsi
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // eax
  int v16; // r9d
  __int64 v17; // rax
  int v18; // edi
  int v19; // r8d
  __int64 v20; // rax
  int v21; // edi
  _DWORD *v22; // rcx
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // rcx
  int v26; // r8d
  char v27; // [rsp+28h] [rbp-D8h]
  _BYTE v28[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v32[320]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  _DWORD v34[3]; // [rsp+1B4h] [rbp+B4h] BYREF

  v1 = *((_DWORD *)this + 3);
  IsBackgroundRestricted = DusmConnection::IsBackgroundRestricted(this);
  v4 = *((_QWORD *)this + 30);
  v5 = 3;
  v6 = IsBackgroundRestricted;
  if ( v4 )
  {
    v7 = *((_DWORD *)this + 4);
    v27 = *((_BYTE *)this + 316);
    v28[0] = 0;
    DusmDataPlan::EvaluateUsageState(
      v4,
      (_DWORD)this + 32,
      v7,
      (_DWORD)this + 176,
      (__int64)this + 308,
      v27,
      (__int64)v28);
    v8 = *((_QWORD *)this + 30);
    *((_DWORD *)this + 3) = *(_DWORD *)(v8 + 68);
    v9 = v28[0] == 0;
    *((_BYTE *)this + 1) = *(_DWORD *)(v8 + 152) != 0;
    if ( !v9 )
    {
      if ( *((_BYTE *)this + 272) )
      {
        v10 = *(_QWORD *)(v8 + 52);
        *(_QWORD *)&v34[1] = 0;
        GetSystemTimeAsFileTime((LPFILETIME)&v34[1]);
        if ( CompareFileTime((const FILETIME *)&v34[1], (const FILETIME *)((char *)this + 300)) > 0 )
        {
          *(_QWORD *)((char *)this + 300) = v10;
          DusmConnection::PublishMbaeNotification(this, 4);
        }
      }
    }
  }
  else
  {
    v15 = 3;
    if ( *((_DWORD *)this + 4) != 3 )
      v15 = 5;
    *((_DWORD *)this + 3) = v15;
    *((_BYTE *)this + 1) = 0;
  }
  v11 = *((_DWORD *)this + 3);
  if ( v1 != v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
          v5 = v14 == 1;
        else
          v5 = 2;
      }
    }
    else
    {
      v5 = 4;
    }
    v16 = *((_DWORD *)this + 4);
    v34[0] = v5;
    v17 = DusmConnection::DusmConnection((__int64)v32, (_OWORD *)this + 2, 0, v16, 0);
    v18 = DusmPublishToWcm(v17, 296, v34, 4);
    DusmConnection::~DusmConnection((DusmConnection *)v32);
    if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8) > 5u )
    {
      v29 = DusmDpuStateToSz(*((unsigned int *)this + 3));
      v34[1] = v18;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v19,
        (__int64)&v34[1],
        (__int64)&v29);
    }
  }
  v33[0] = DusmConnection::IsBackgroundRestricted(this);
  if ( v6 != v33[0] )
  {
    v20 = DusmConnection::DusmConnection((__int64)v32, (_OWORD *)this + 2, 0, *((_DWORD *)this + 4), 0);
    v21 = DusmPublishToWcm(v20, 297, v33, 1);
    DusmConnection::~DusmConnection((DusmConnection *)v32);
    v22 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
    if ( *v22 > 5u )
    {
      v34[1] = v33[0];
      v34[0] = v21;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v22,
        (unsigned int)byte_180056741,
        v23,
        v24,
        (__int64)v34,
        (__int64)&v34[1]);
    }
  }
  DusmConnection::PublishSetDataPlanToast(this);
  if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8) > 5u )
  {
    v25 = *((unsigned int *)this + 3);
    v34[1] = *((_QWORD *)this + 30) != 0;
    v34[0] = v33[0];
    v29 = DusmDpuStateToSz(v25);
    v30 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 48);
    v31 = (__int64)this + 32;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v26,
      (int)&byte_1800566B9,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)v34,
      (__int64)&v34[1]);
  }
}

```

## disassembly

```asm
0x1800186fc  mov     [rsp-8+arg_8], rbx
0x180018701  mov     [rsp-8+arg_10], rsi
0x180018706  push    rbp
0x180018707  push    rdi
0x180018708  push    r12
0x18001870a  push    r14
0x18001870c  push    r15
0x18001870e  lea     rbp, [rsp-0D0h]
0x180018716  sub     rsp, 1D0h
0x18001871d  mov     rax, cs:__security_cookie
0x180018724  xor     rax, rsp
0x180018727  mov     [rbp+0F0h+var_30], rax
0x18001872e  mov     r14d, [rcx+0Ch]
0x180018732  mov     rbx, rcx
0x180018735  call    ?IsBackgroundRestricted@DusmConnection@@QEBA_NXZ; DusmConnection::IsBackgroundRestricted(void)
0x18001873a  mov     rcx, [rbx+0F0h]
0x180018741  lea     r15, [rbx+20h]
0x180018745  mov     edi, 3
0x18001874a  mov     r12b, al
0x18001874d  lea     esi, [rdi+2]
0x180018750  test    rcx, rcx
0x180018753  jz      loc_18001882A
0x180018759  mov     r8d, [rbx+10h]
0x18001875d  lea     rax, [rsp+1F0h+var_1A0]
0x180018762  mov     [rsp+1F0h+var_1C0], rax
0x180018767  lea     rdx, [rbx+134h]
0x18001876e  mov     al, [rbx+13Ch]
0x180018774  lea     r9, [rbx+0B0h]
0x18001877b  mov     byte ptr [rsp+1F0h+var_1C8], al
0x18001877f  mov     [rsp+1F0h+var_1D0], rdx
0x180018784  mov     rdx, r15
0x180018787  mov     [rsp+1F0h+var_1A0], 0
0x18001878c  call    ?EvaluateUsageState@DusmDataPlan@@QEAAXAEBU_GUID@@W4_DUSM_MEDIA_TYPE@@AEBV?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@AEBU_FILETIME@@_NPEA_N@Z; DusmDataPlan::EvaluateUsageState(_GUID const &,_DUSM_MEDIA_TYPE,std::unordered_set<ulong> const &,_FILETIME const &,bool,bool *)
0x180018791  mov     rcx, [rbx+0F0h]
0x180018798  mov     eax, [rcx+44h]
0x18001879b  mov     [rbx+0Ch], eax
0x18001879e  cmp     dword ptr [rcx+98h], 0
0x1800187a5  setnz   al
0x1800187a8  cmp     [rsp+1F0h+var_1A0], 0
0x1800187ad  mov     [rbx+1], al
0x1800187b0  jz      short loc_180018806
0x1800187b2  cmp     byte ptr [rbx+110h], 0
0x1800187b9  jz      short loc_180018806
0x1800187bb  mov     rsi, [rcx+34h]
0x1800187bf  lea     rcx, [rbp+0F0h+var_3C+4]; lpSystemTimeAsFileTime
0x1800187c6  mov     qword ptr [rbp+0F0h+var_3C+4], 0
0x1800187d1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800187d7  lea     rdx, [rbx+12Ch]; lpFileTime2
0x1800187de  lea     rcx, [rbp+0F0h+var_3C+4]; lpFileTime1
0x1800187e5  call    cs:__imp_CompareFileTime
0x1800187eb  test    eax, eax
0x1800187ed  jle     short loc_180018801
0x1800187ef  lea     edx, [rdi+1]
0x1800187f2  mov     [rbx+12Ch], rsi
0x1800187f9  mov     rcx, rbx
0x1800187fc  call    ?PublishMbaeNotification@DusmConnection@@QEBAXW4NotificationMessageType@@@Z; DusmConnection::PublishMbaeNotification(NotificationMessageType)
0x180018801  mov     esi, 5
0x180018806  mov     ecx, [rbx+0Ch]
0x180018809  cmp     r14d, ecx
0x18001880c  jz      loc_1800188DF
0x180018812  sub     ecx, 1
0x180018815  jz      short loc_180018849
0x180018817  sub     ecx, 1
0x18001881a  jz      short loc_18001884E
0x18001881c  sub     ecx, 1
0x18001881f  jz      short loc_180018842
0x180018821  sub     ecx, 1
0x180018824  jz      short loc_18001883B
0x180018826  xor     edi, edi
0x180018828  jmp     short loc_18001884E
0x18001882a  cmp     [rbx+10h], edi
0x18001882d  mov     eax, edi
0x18001882f  cmovnz  eax, esi
0x180018832  mov     [rbx+0Ch], eax
0x180018835  mov     byte ptr [rbx+1], 0
0x180018839  jmp     short loc_180018806
0x18001883b  mov     edi, 1
0x180018840  jmp     short loc_18001884E
0x180018842  mov     edi, 2
0x180018847  jmp     short loc_18001884E
0x180018849  mov     edi, 4
0x18001884e  mov     r9d, [rbx+10h]
0x180018852  lea     rcx, [rsp+1F0h+var_180]
0x180018857  xor     r8d, r8d
0x18001885a  mov     dword ptr [rbp+0F0h+var_3C], edi
0x180018860  mov     rdx, r15
0x180018863  mov     [rsp+1F0h+var_1D0], 0
0x18001886c  call    ??0DusmConnection@@QEAA@PEBU_GUID@@PEB_WW4_DUSM_MEDIA_TYPE@@1@Z; DusmConnection::DusmConnection(_GUID const *,wchar_t const *,_DUSM_MEDIA_TYPE,wchar_t const *)
0x180018871  mov     r9d, 4
0x180018877  lea     r8, [rbp+0F0h+var_3C]
0x18001887e  mov     edx, 128h
0x180018883  mov     rcx, rax
0x180018886  call    ?DusmPublishToWcm@@YAKAEBVDusmConnection@@W4_WCM_OPCODE@@PEBEK@Z; DusmPublishToWcm(DusmConnection const &,_WCM_OPCODE,uchar const *,ulong)
0x18001888b  lea     rcx, [rsp+1F0h+var_180]; this
0x180018890  mov     edi, eax
0x180018892  call    ??1DusmConnection@@QEAA@XZ; DusmConnection::~DusmConnection(void)
0x180018897  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18001889c  mov     r8, [rax+8]
0x1800188a0  mov     edx, [r8]
0x1800188a3  cmp     edx, esi
0x1800188a5  jbe     short loc_1800188DF
0x1800188a7  mov     ecx, [rbx+0Ch]
0x1800188aa  call    ?DusmDpuStateToSz@@YAPEB_WW4_DUSM_DPU_STATE@@@Z; DusmDpuStateToSz(_DUSM_DPU_STATE)
0x1800188af  mov     [rsp+1F0h+var_198], rax
0x1800188b4  lea     rdx, byte_1800567AD
0x1800188bb  lea     rax, [rsp+1F0h+var_198]
0x1800188c0  mov     dword ptr [rbp+0F0h+var_3C+4], edi
0x1800188c6  mov     [rsp+1F0h+var_1C8], rax; __int64
0x1800188cb  mov     rcx, r8; int
0x1800188ce  lea     rax, [rbp+0F0h+var_3C+4]
0x1800188d5  mov     [rsp+1F0h+var_1D0], rax; __int64
0x1800188da  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1800188df  mov     rcx, rbx; this
0x1800188e2  call    ?IsBackgroundRestricted@DusmConnection@@QEBA_NXZ; DusmConnection::IsBackgroundRestricted(void)
0x1800188e7  mov     [rbp+0F0h+var_40], al
0x1800188ed  cmp     r12b, al
0x1800188f0  jz      loc_18001897F
0x1800188f6  mov     r9d, [rbx+10h]
0x1800188fa  lea     rcx, [rsp+1F0h+var_180]
0x1800188ff  xor     r8d, r8d
0x180018902  mov     [rsp+1F0h+var_1D0], 0
0x18001890b  mov     rdx, r15
0x18001890e  call    ??0DusmConnection@@QEAA@PEBU_GUID@@PEB_WW4_DUSM_MEDIA_TYPE@@1@Z; DusmConnection::DusmConnection(_GUID const *,wchar_t const *,_DUSM_MEDIA_TYPE,wchar_t const *)
0x180018913  mov     r9d, 1
0x180018919  lea     r8, [rbp+0F0h+var_40]
0x180018920  mov     edx, 129h
0x180018925  mov     rcx, rax
0x180018928  call    ?DusmPublishToWcm@@YAKAEBVDusmConnection@@W4_WCM_OPCODE@@PEBEK@Z; DusmPublishToWcm(DusmConnection const &,_WCM_OPCODE,uchar const *,ulong)
0x18001892d  lea     rcx, [rsp+1F0h+var_180]; this
0x180018932  mov     edi, eax
0x180018934  call    ??1DusmConnection@@QEAA@XZ; DusmConnection::~DusmConnection(void)
0x180018939  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18001893e  mov     rcx, [rax+8]
0x180018942  mov     edx, [rcx]
0x180018944  cmp     edx, esi
0x180018946  jbe     short loc_18001897F
0x180018948  movzx   edx, [rbp+0F0h+var_40]
0x18001894f  lea     rax, [rbp+0F0h+var_3C+4]
0x180018956  mov     [rsp+1F0h+var_1C8], rax
0x18001895b  lea     rax, [rbp+0F0h+var_3C]
0x180018962  mov     dword ptr [rbp+0F0h+var_3C+4], edx
0x180018968  lea     rdx, byte_180056741
0x18001896f  mov     [rsp+1F0h+var_1D0], rax
0x180018974  mov     dword ptr [rbp+0F0h+var_3C], edi
0x18001897a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001897f  mov     rcx, rbx; this
0x180018982  call    ?PublishSetDataPlanToast@DusmConnection@@QEAAXXZ; DusmConnection::PublishSetDataPlanToast(void)
0x180018987  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18001898c  mov     r8, [rax+8]
0x180018990  mov     eax, [r8]
0x180018993  cmp     eax, esi
0x180018995  jbe     loc_180018A1F
0x18001899b  mov     ecx, [rbx+0Ch]
0x18001899e  xor     eax, eax
0x1800189a0  cmp     [rbx+0F0h], rax
0x1800189a7  setnz   al
0x1800189aa  mov     dword ptr [rbp+0F0h+var_3C+4], eax
0x1800189b0  movzx   eax, [rbp+0F0h+var_40]
0x1800189b7  mov     dword ptr [rbp+0F0h+var_3C], eax
0x1800189bd  call    ?DusmDpuStateToSz@@YAPEB_WW4_DUSM_DPU_STATE@@@Z; DusmDpuStateToSz(_DUSM_DPU_STATE)
0x1800189c2  lea     rcx, [rbx+30h]
0x1800189c6  mov     [rsp+1F0h+var_198], rax
0x1800189cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800189d0  mov     [rsp+1F0h+var_190], rax
0x1800189d5  lea     rdx, byte_1800566B9; int
0x1800189dc  lea     rax, [rbp+0F0h+var_3C+4]
0x1800189e3  mov     [rsp+1F0h+var_188], r15
0x1800189e8  mov     [rsp+1F0h+var_1B0], rax; __int64
0x1800189ed  mov     rcx, r8; int
0x1800189f0  lea     rax, [rbp+0F0h+var_3C]
0x1800189f7  mov     [rsp+1F0h+var_1B8], rax; __int64
0x1800189fc  lea     rax, [rsp+1F0h+var_198]
0x180018a01  mov     [rsp+1F0h+var_1C0], rax; __int64
0x180018a06  lea     rax, [rsp+1F0h+var_190]
0x180018a0b  mov     [rsp+1F0h+var_1C8], rax; __int64
0x180018a10  lea     rax, [rsp+1F0h+var_188]
0x180018a15  mov     [rsp+1F0h+var_1D0], rax; __int64
0x180018a1a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@_W@@U2@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@_W@@4AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018a1f  mov     rcx, [rbp+0F0h+var_30]
0x180018a26  xor     rcx, rsp; StackCookie
0x180018a29  call    __security_check_cookie
0x180018a2e  lea     r11, [rsp+1F0h+var_20]
0x180018a36  mov     rbx, [r11+38h]
0x180018a3a  mov     rsi, [r11+40h]
0x180018a3e  mov     rsp, r11
0x180018a41  pop     r15
0x180018a43  pop     r14
0x180018a45  pop     r12
0x180018a47  pop     rdi
0x180018a48  pop     rbp
0x180018a49  retn
```
