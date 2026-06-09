# ESIMPM::SaveStartDate(void)

- ea: `0x14003377c`
- end: `0x140033897`
- name: `?SaveStartDate@ESIMPM@@YAXXZ`
- size: `283`
- prototype: `void __fastcall(ESIMPM *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140024d88`

## callees

- `0x140001308`
- `0x140020620`
- `0x140023158`
- `0x1400307e0`
- `0x14003287c`
- `0x14003377c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400337f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400337f5`

## string_xrefs

- `0x1400337d6`: `Not writing start date to registry, it already exists`
- `0x14003387d`: `Succeeded in saving current date to the registry`

## pseudocode

```c
void __fastcall ESIMPM::SaveStartDate(ESIMPM *this)
{
  int v1; // eax
  __int64 v2; // r8
  __int64 v3; // r9
  unsigned int v4; // [rsp+50h] [rbp+8h] BYREF
  int v5; // [rsp+58h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+18h] BYREF
  const char *v7; // [rsp+68h] [rbp+20h] BYREF

  SystemTimeAsFileTime = 0;
  v4 = 8;
  if ( StateSeparation::GetValue(
         *((StateSeparation **)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 120),
         L"SIUFTriggerData",
         L"StartDate",
         0x48u,
         0,
         &SystemTimeAsFileTime,
         &v4) )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v4 = 8;
    v1 = StateSeparation::SetValue(
           *((StateSeparation **)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 120),
           L"SIUFTriggerData",
           L"StartDate",
           0xBu,
           (const unsigned __int8 *)&SystemTimeAsFileTime,
           8u);
    if ( v1 )
    {
      if ( (unsigned int)dword_140075078 > 2 )
      {
        v5 = v1;
        v7 = "ESIMPM::SaveStartDate";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (__int64)"ESIMPM::SaveStartDate",
          (__int64)&word_14006C7CE,
          v2,
          v3,
          (__int64)&v5,
          (const unsigned __int16 **)&v7);
      }
    }
    else
    {
      ESIMPM::Log::Info("ESIMPM::SaveStartDate", 0, L"Succeeded in saving current date to the registry");
    }
  }
  else
  {
    ESIMPM::Log::Verbose("ESIMPM::SaveStartDate", 0, L"Not writing start date to registry, it already exists");
  }
}

```

## disassembly

```asm
0x14003377c  mov     r11, rsp
0x14003377f  sub     rsp, 48h
0x140033783  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x14003378a  lea     rax, [r11+8]
0x14003378e  mov     [r11-18h], rax
0x140033792  lea     r8, aStartdate; "StartDate"
0x140033799  lea     rax, [r11+18h]
0x14003379d  mov     qword ptr [r11+18h], 0
0x1400337a5  mov     [rsp+48h+arg_0], 8
0x1400337ad  lea     rdx, aSiuftriggerdat; "SIUFTriggerData"
0x1400337b4  mov     rcx, [rcx+3C0h]; this
0x1400337bb  mov     r9d, 48h ; 'H'; unsigned int
0x1400337c1  mov     [r11-20h], rax
0x1400337c5  mov     qword ptr [r11-28h], 0
0x1400337cd  call    ?GetValue@StateSeparation@@QEAAKPEBG0KPEAKPEAX1@Z; StateSeparation::GetValue(ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x1400337d2  test    eax, eax
0x1400337d4  jnz     short loc_1400337F0
0x1400337d6  lea     r8, aNotWritingStar; "Not writing start date to registry, it "...
0x1400337dd  xor     edx, edx; struct _GUID *
0x1400337df  lea     rcx, aEsimpmSavestar; "ESIMPM::SaveStartDate"
0x1400337e6  call    ?Verbose@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Verbose(char const *,_GUID const *,ushort const *,...)
0x1400337eb  jmp     loc_140033892
0x1400337f0  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400337f5  call    cs:__imp_GetSystemTimeAsFileTime
0x1400337fb  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x140033802  lea     rax, [rsp+48h+SystemTimeAsFileTime]
0x140033807  mov     [rsp+48h+arg_0], 8
0x14003380f  lea     r8, aStartdate; "StartDate"
0x140033816  mov     [rsp+48h+var_20], 8; unsigned int
0x14003381e  lea     rdx, aSiuftriggerdat; "SIUFTriggerData"
0x140033825  mov     r9d, 0Bh; unsigned int
0x14003382b  mov     [rsp+48h+var_28], rax; unsigned __int8 *
0x140033830  mov     rcx, [rcx+3C0h]; this
0x140033837  call    ?SetValue@StateSeparation@@QEAAKPEBG0KPEBEK@Z; StateSeparation::SetValue(ushort const *,ushort const *,ulong,uchar const *,ulong)
0x14003383c  test    eax, eax
0x14003383e  jz      short loc_14003387D
0x140033840  mov     ecx, cs:dword_140075078
0x140033846  cmp     ecx, 2
0x140033849  jbe     short loc_140033892
0x14003384b  mov     [rsp+48h+arg_8], eax
0x14003384f  lea     rcx, aEsimpmSavestar; "ESIMPM::SaveStartDate"
0x140033856  lea     rax, [rsp+48h+arg_18]
0x14003385b  mov     [rsp+48h+arg_18], rcx
0x140033860  mov     qword ptr [rsp+48h+var_20], rax
0x140033865  lea     rdx, word_14006C7CE
0x14003386c  lea     rax, [rsp+48h+arg_8]
0x140033871  mov     [rsp+48h+var_28], rax
0x140033876  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14003387b  jmp     short loc_140033892
0x14003387d  lea     r8, aSucceededInSav_0; "Succeeded in saving current date to the"...
0x140033884  xor     edx, edx; struct _GUID *
0x140033886  lea     rcx, aEsimpmSavestar; "ESIMPM::SaveStartDate"
0x14003388d  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140033892  add     rsp, 48h
0x140033896  retn
```
