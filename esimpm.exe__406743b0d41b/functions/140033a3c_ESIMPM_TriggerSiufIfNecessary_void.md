# ESIMPM::TriggerSiufIfNecessary(void)

- ea: `0x140033a3c`
- end: `0x140033d45`
- name: `?TriggerSiufIfNecessary@ESIMPM@@YAXXZ`
- size: `777`
- prototype: `void __fastcall(ESIMPM *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140024d88`
- `0x140028774`
- `0x140028e5c`

## callees

- `0x1400011d8`
- `0x140001308`
- `0x140002f60`
- `0x140020620`
- `0x140023158`
- `0x1400282f4`
- `0x1400307e0`
- `0x1400338a0`
- `0x140033a3c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140033a6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140033a6d`

## string_xrefs

- `0x140033cdd`: `Succeeded in saving last shown SIUF data to the registry`

## pseudocode

```c
void __fastcall ESIMPM::TriggerSiufIfNecessary(ESIMPM *this)
{
  unsigned int Value; // eax
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rcx
  unsigned int DWORD; // eax
  const unsigned __int16 *v6; // r8
  __int16 *v7; // rdx
  unsigned __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned __int64 v10; // r14
  char v11; // al
  int v12; // ebx
  int v13; // esi
  int v14; // eax
  int v15; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v16[3]; // [rsp+44h] [rbp-35h] BYREF
  unsigned int v17; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int64 v18; // [rsp+58h] [rbp-21h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20[2]; // [rsp+68h] [rbp-11h] BYREF
  unsigned int *v21; // [rsp+88h] [rbp+Fh]
  __int64 v22; // [rsp+90h] [rbp+17h]

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v18 = 0;
  v17 = 8;
  Value = StateSeparation::GetValue(
            *((StateSeparation **)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 120),
            L"SIUFTriggerData",
            L"StartDate",
            0x48u,
            0,
            &v18,
            &v17);
  v4 = Value;
  if ( Value || v17 != 8 )
  {
    if ( (unsigned int)dword_140075078 <= 2 )
      return;
    v7 = (__int16 *)&dword_14006C784;
  }
  else
  {
    v16[0] = 0;
    DWORD = StateSeparation::GetDWORD(
              *((StateSeparation **)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 120),
              L"SIUFTriggerData",
              L"LastShownSIUF",
              v16);
    v4 = DWORD;
    if ( DWORD == 2 )
    {
      ESIMPM::Log::Verbose(
        "ESIMPM::TriggerSiufIfNecessary",
        0,
        L"Reg key %ws not found, so we assume that SIUF has not been shown before",
        L"LastShownSIUF");
      v6 = 0;
      v16[0] = 0;
LABEL_9:
      if ( v18 >= *(_QWORD *)&SystemTimeAsFileTime )
        v8 = v18 - *(_QWORD *)&SystemTimeAsFileTime;
      else
        v8 = *(_QWORD *)&SystemTimeAsFileTime - v18;
      v9 = 3;
      v10 = v8 / 0xC92A69C000LL;
      v11 = 0;
      v12 = 14;
      if ( (unsigned int)(v8 / 0xC92A69C000LL) < 0xE )
      {
        v12 = 7;
        if ( (unsigned int)v10 < 7 )
        {
          v12 = 0;
          if ( (unsigned int)v10 >= 3 )
            v12 = 3;
        }
      }
      if ( v12 > (int)v6 )
      {
        if ( (unsigned int)dword_140075040 > 5
          && (qword_140075050 & 0x200000000000LL) != 0
          && (qword_140075058 & 0x200000000000LL) == qword_140075058 )
        {
          *(_QWORD *)&v16[1] = 0x1000000;
          v21 = &v16[1];
          v22 = 8;
          tlgWriteTransfer_EventWriteTransfer(
            (__int64)&dword_140075040,
            (unsigned __int8 *)&dword_14006C6FC,
            0,
            0,
            3u,
            v20);
          v9 = 3;
        }
        v6 = (const unsigned __int16 *)v16[0];
        v11 = 1;
      }
      v13 = 10;
      if ( (unsigned int)v10 < 0xA )
      {
        v13 = 0;
        if ( (unsigned int)v10 >= 5 )
          v13 = 5;
      }
      if ( v13 <= (int)v6 )
      {
        if ( !v11 )
          return;
      }
      else if ( (unsigned int)dword_140075040 > 5
             && (qword_140075050 & 0x200000000000LL) != 0
             && (qword_140075058 & 0x200000000000LL) == qword_140075058 )
      {
        *(_QWORD *)&v16[1] = 0x1000000;
        v21 = &v16[1];
        v22 = 8;
        tlgWriteTransfer_EventWriteTransfer(
          (__int64)&dword_140075040,
          (unsigned __int8 *)&word_14006C6BE,
          0,
          0,
          3u,
          v20);
      }
      if ( v12 <= (unsigned int)v13 )
        v12 = v13;
      v14 = StateSeparation::SetDWORD(
              *((StateSeparation **)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 120),
              (const unsigned __int16 *)v9,
              v6,
              v12);
      if ( !v14 )
      {
        ESIMPM::Log::Info(
          "ESIMPM::TriggerSiufIfNecessary",
          0,
          L"Succeeded in saving last shown SIUF data to the registry");
        return;
      }
      v4 = (unsigned int)dword_140075078;
      if ( (unsigned int)dword_140075078 <= 2 )
        return;
      v15 = v14;
      v7 = &word_14006C66E;
      goto LABEL_40;
    }
    if ( !DWORD )
    {
      v6 = (const unsigned __int16 *)v16[0];
      goto LABEL_9;
    }
    if ( (unsigned int)dword_140075078 <= 2 )
      return;
    v7 = (__int16 *)byte_14006C735;
  }
  v15 = v4;
LABEL_40:
  *(_QWORD *)&v16[1] = "ESIMPM::TriggerSiufIfNecessary";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
    v4,
    (__int64)v7,
    v2,
    v3,
    (__int64)&v15,
    (const unsigned __int16 **)&v16[1]);
}

```

## disassembly

```asm
0x140033a3c  push    rbp
0x140033a3e  push    rbx
0x140033a3f  push    rsi
0x140033a40  push    rdi
0x140033a41  push    r12
0x140033a43  push    r13
0x140033a45  push    r14
0x140033a47  lea     rbp, [rsp-27h]
0x140033a4c  sub     rsp, 0A0h
0x140033a53  mov     rax, cs:__security_cookie
0x140033a5a  xor     rax, rsp
0x140033a5d  mov     [rbp+57h+var_38], rax
0x140033a61  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140033a65  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x140033a6d  call    cs:__imp_GetSystemTimeAsFileTime
0x140033a73  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x140033a7a  lea     rax, [rbp+57h+var_80]
0x140033a7e  mov     [rsp+0D0h+var_A0], rax; unsigned int *
0x140033a83  lea     r8, aStartdate; "StartDate"
0x140033a8a  mov     esi, 8
0x140033a8f  mov     [rbp+57h+var_78], 0
0x140033a97  lea     rax, [rbp+57h+var_78]
0x140033a9b  mov     [rbp+57h+var_80], esi
0x140033a9e  mov     rcx, [rcx+3C0h]; this
0x140033aa5  lea     rdx, aSiuftriggerdat; "SIUFTriggerData"
0x140033aac  mov     [rsp+0D0h+var_A8], rax; void *
0x140033ab1  lea     r9d, [rsi+40h]; unsigned int
0x140033ab5  mov     [rsp+0D0h+var_B0], 0; unsigned int *
0x140033abe  call    ?GetValue@StateSeparation@@QEAAKPEBG0KPEAKPEAX1@Z; StateSeparation::GetValue(ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x140033ac3  mov     ecx, eax
0x140033ac5  test    eax, eax
0x140033ac7  jnz     loc_140033CF0
0x140033acd  cmp     [rbp+57h+var_80], esi
0x140033ad0  jnz     loc_140033CF0
0x140033ad6  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x140033add  lea     r9, [rbp+57h+var_8C]; unsigned int *
0x140033ae1  mov     dword ptr [rbp+57h+var_8C], eax
0x140033ae4  lea     r8, ValueName; "LastShownSIUF"
0x140033aeb  lea     rdx, aSiuftriggerdat; "SIUFTriggerData"
0x140033af2  mov     rcx, [rcx+3C0h]; this
0x140033af9  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x140033afe  lea     rdi, aEsimpmTriggers; "ESIMPM::TriggerSiufIfNecessary"
0x140033b05  mov     ecx, eax
0x140033b07  cmp     eax, 2
0x140033b0a  jnz     short loc_140033B2D
0x140033b0c  lea     r9, ValueName; "LastShownSIUF"
0x140033b13  xor     edx, edx; struct _GUID *
0x140033b15  lea     r8, aRegKeyWsNotFou; "Reg key %ws not found, so we assume tha"...
0x140033b1c  mov     rcx, rdi; char *
0x140033b1f  call    ?Verbose@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Verbose(char const *,_GUID const *,ushort const *,...)
0x140033b24  xor     r8d, r8d
0x140033b27  mov     dword ptr [rbp+57h+var_8C], r8d
0x140033b2b  jmp     short loc_140033B50
0x140033b2d  test    ecx, ecx
0x140033b2f  jz      short loc_140033B4C
0x140033b31  mov     eax, cs:dword_140075078
0x140033b37  cmp     eax, 2
0x140033b3a  jbe     loc_140033D27
0x140033b40  lea     rdx, byte_14006C735
0x140033b47  jmp     loc_140033D09
0x140033b4c  mov     r8d, dword ptr [rbp+57h+var_8C]
0x140033b50  mov     rax, [rbp+57h+var_78]
0x140033b54  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x140033b58  cmp     rax, rcx
0x140033b5b  jnb     short loc_140033B62
0x140033b5d  sub     rcx, rax
0x140033b60  jmp     short loc_140033B68
0x140033b62  sub     rax, rcx
0x140033b65  mov     rcx, rax
0x140033b68  xor     edx, edx
0x140033b6a  mov     rax, rcx
0x140033b6d  mov     rcx, 0C92A69C000h
0x140033b77  div     rcx
0x140033b7a  mov     edx, 3
0x140033b7f  mov     r14, rax
0x140033b82  xor     al, al
0x140033b84  lea     ebx, [rdx+0Bh]
0x140033b87  cmp     r14d, ebx
0x140033b8a  jnb     short loc_140033B9C
0x140033b8c  lea     ebx, [rdx+4]
0x140033b8f  cmp     r14d, ebx
0x140033b92  jnb     short loc_140033B9C
0x140033b94  xor     ebx, ebx
0x140033b96  cmp     r14d, edx
0x140033b99  cmovnb  ebx, edx
0x140033b9c  mov     r13d, 5
0x140033ba2  mov     r12, 200000000000h
0x140033bac  cmp     ebx, r8d
0x140033baf  jle     short loc_140033C1E
0x140033bb1  mov     eax, cs:dword_140075040
0x140033bb7  cmp     eax, r13d
0x140033bba  jbe     short loc_140033C18
0x140033bbc  mov     rcx, cs:qword_140075058
0x140033bc3  mov     rax, cs:qword_140075050
0x140033bca  test    r12, rax
0x140033bcd  jz      short loc_140033C18
0x140033bcf  mov     rax, rcx
0x140033bd2  and     rax, r12
0x140033bd5  cmp     rax, rcx
0x140033bd8  jnz     short loc_140033C18
0x140033bda  lea     rax, [rbp+57h+var_8C+4]
0x140033bde  mov     qword ptr [rbp+57h+var_8C+4], 1000000h
0x140033be6  mov     [rbp+57h+var_48], rax
0x140033bea  lea     rcx, dword_140075040
0x140033bf1  lea     rax, [rbp+57h+var_68]
0x140033bf5  mov     [rbp+57h+var_40], rsi
0x140033bf9  mov     [rsp+0D0h+var_A8], rax
0x140033bfe  xor     r9d, r9d
0x140033c01  mov     dword ptr [rsp+0D0h+var_B0], edx
0x140033c05  xor     r8d, r8d
0x140033c08  lea     rdx, dword_14006C6FC
0x140033c0f  call    _tlgWriteTransfer_EventWriteTransfer
0x140033c14  lea     edx, [r13-2]; unsigned __int16 *
0x140033c18  mov     r8d, dword ptr [rbp+57h+var_8C]; unsigned __int16 *
0x140033c1c  mov     al, 1
0x140033c1e  mov     esi, 0Ah
0x140033c23  cmp     r14d, esi
0x140033c26  jnb     short loc_140033C31
0x140033c28  xor     esi, esi
0x140033c2a  cmp     r14d, r13d
0x140033c2d  cmovnb  esi, r13d
0x140033c31  cmp     esi, r8d
0x140033c34  jle     short loc_140033C9F
0x140033c36  mov     eax, cs:dword_140075040
0x140033c3c  cmp     eax, r13d
0x140033c3f  jbe     short loc_140033CA7
0x140033c41  mov     rcx, cs:qword_140075058
0x140033c48  mov     rax, cs:qword_140075050
0x140033c4f  test    r12, rax
0x140033c52  jz      short loc_140033CA7
0x140033c54  mov     rax, rcx
0x140033c57  and     rax, r12
0x140033c5a  cmp     rax, rcx
0x140033c5d  jnz     short loc_140033CA7
0x140033c5f  lea     rax, [rbp+57h+var_8C+4]
0x140033c63  mov     qword ptr [rbp+57h+var_8C+4], 1000000h
0x140033c6b  mov     [rbp+57h+var_48], rax
0x140033c6f  lea     rcx, dword_140075040
0x140033c76  lea     rax, [rbp+57h+var_68]
0x140033c7a  mov     [rbp+57h+var_40], 8
0x140033c82  mov     [rsp+0D0h+var_A8], rax
0x140033c87  xor     r9d, r9d
0x140033c8a  mov     dword ptr [rsp+0D0h+var_B0], edx
0x140033c8e  xor     r8d, r8d
0x140033c91  lea     rdx, word_14006C6BE
0x140033c98  call    _tlgWriteTransfer_EventWriteTransfer
0x140033c9d  jmp     short loc_140033CA7
0x140033c9f  test    al, al
0x140033ca1  jz      loc_140033D27
0x140033ca7  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x140033cae  cmp     ebx, esi
0x140033cb0  cmovbe  ebx, esi
0x140033cb3  mov     r9d, ebx; unsigned int
0x140033cb6  mov     rcx, [rcx+3C0h]; this
0x140033cbd  call    ?SetDWORD@StateSeparation@@QEAAKPEBG0K@Z; StateSeparation::SetDWORD(ushort const *,ushort const *,ulong)
0x140033cc2  test    eax, eax
0x140033cc4  jz      short loc_140033CDD
0x140033cc6  mov     ecx, cs:dword_140075078
0x140033ccc  cmp     ecx, 2
0x140033ccf  jbe     short loc_140033D27
0x140033cd1  mov     [rbp+57h+var_90], eax
0x140033cd4  lea     rdx, word_14006C66E
0x140033cdb  jmp     short loc_140033D0C
0x140033cdd  lea     r8, aSucceededInSav; "Succeeded in saving last shown SIUF dat"...
0x140033ce4  xor     edx, edx; struct _GUID *
0x140033ce6  mov     rcx, rdi; char *
0x140033ce9  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140033cee  jmp     short loc_140033D27
0x140033cf0  mov     eax, cs:dword_140075078
0x140033cf6  cmp     eax, 2
0x140033cf9  jbe     short loc_140033D27
0x140033cfb  lea     rdi, aEsimpmTriggers; "ESIMPM::TriggerSiufIfNecessary"
0x140033d02  lea     rdx, dword_14006C784
0x140033d09  mov     [rbp+57h+var_90], ecx
0x140033d0c  lea     rax, [rbp+57h+var_8C+4]
0x140033d10  mov     [rsp+0D0h+var_A8], rax
0x140033d15  lea     rax, [rbp+57h+var_90]
0x140033d19  mov     [rsp+0D0h+var_B0], rax
0x140033d1e  mov     qword ptr [rbp+57h+var_8C+4], rdi
0x140033d22  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140033d27  mov     rcx, [rbp+57h+var_38]
0x140033d2b  xor     rcx, rsp; StackCookie
0x140033d2e  call    __security_check_cookie
0x140033d33  add     rsp, 0A0h
0x140033d3a  pop     r14
0x140033d3c  pop     r13
0x140033d3e  pop     r12
0x140033d40  pop     rdi
0x140033d41  pop     rsi
0x140033d42  pop     rbx
0x140033d43  pop     rbp
0x140033d44  retn
```
