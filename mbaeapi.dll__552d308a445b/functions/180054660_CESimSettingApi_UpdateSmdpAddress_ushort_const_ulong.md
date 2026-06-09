# CESimSettingApi::UpdateSmdpAddress(ushort const *,ulong)

- ea: `0x180054660`
- end: `0x180054ad9`
- name: `?UpdateSmdpAddress@CESimSettingApi@@UEAAJPEBGK@Z`
- size: `1145`
- prototype: `__int64 __fastcall(CESimSettingApi *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800172bc`
- `0x18001dd10`
- `0x180050618`
- `0x180054660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054748`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054748`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800548b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054905`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054ab8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800548b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054905`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054ab8`
- `luiapi!LuiSetDefaultSmdpAddress` at `0x1800548d9`
- `luiapi!LuiSetDefaultSmdpAddress` at `0x1800548d9`

## string_xrefs

- `0x1800546cf`: `CESimSettingApi::UpdateSmdpAddress`

## pseudocode

```c
__int64 __fastcall CESimSettingApi::UpdateSmdpAddress(
        CESimSettingApi *this,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  __int64 v3; // rdi
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int16 *v13; // rdx
  int v15; // eax
  unsigned int v16; // edi
  _DWORD *v17; // rax
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  const struct _tlgProvider_t *v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // [rsp+20h] [rbp-40h]
  int v25[2]; // [rsp+20h] [rbp-40h]
  int v26[2]; // [rsp+20h] [rbp-40h]
  int v27[2]; // [rsp+20h] [rbp-40h]
  __int64 v28; // [rsp+28h] [rbp-38h]
  unsigned __int16 *v29[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v30; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v31[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v32; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int v34; // [rsp+90h] [rbp+30h] BYREF
  unsigned __int16 *v35; // [rsp+A8h] [rbp+48h] BYREF

  v3 = a3;
  v32 = 0;
  v30 = 0;
  *(_OWORD *)v31 = 0;
  *(_OWORD *)v29 = 0;
  std::vector<unsigned short>::resize(v31);
  std::vector<unsigned short>::resize(v29);
  StringCchPrintfW(v31[0], v31[1] - v31[0], L"Enter");
  v24 = 276;
  StringCchPrintfW(v29[0], v29[1] - v29[0], L"%S(%d):%s", "CESimSettingApi::UpdateSmdpAddress", v24, v31[0]);
  v6 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    v35 = v29[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)&byte_180079CBF,
      v7,
      v8,
      (const unsigned __int16 **)&v35);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v29);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v31);
  AcquireSRWLockExclusive((PSRWLOCK)this + 23);
  v9 = *((_QWORD *)this + 19);
  if ( !v9 )
  {
    v30 = 0;
    v32 = 0;
    *(_OWORD *)v29 = 0;
    *(_OWORD *)v31 = 0;
    std::vector<unsigned short>::resize(v29);
    std::vector<unsigned short>::resize(v31);
    StringCchPrintfW(v29[0], v29[1] - v29[0], L"Trying to call ESimSettingApi without a valid LpaSvc handle.");
    v25[0] = 278;
    StringCchPrintfW(
      v31[0],
      v31[1] - v31[0],
      L"%S(%d):%s",
      "CESimSettingApi::UpdateSmdpAddress",
      *(_QWORD *)v25,
      v29[0]);
    v10 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v10 > 2u )
    {
      v13 = word_180079CE2;
LABEL_9:
      v35 = v31[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v10,
        (__int64)v13,
        v11,
        v12,
        (const unsigned __int16 **)&v35);
      goto LABEL_10;
    }
    goto LABEL_10;
  }
  if ( !*((_WORD *)this + 32) )
  {
    v30 = 0;
    v32 = 0;
    *(_OWORD *)v29 = 0;
    *(_OWORD *)v31 = 0;
    std::vector<unsigned short>::resize(v29);
    std::vector<unsigned short>::resize(v31);
    StringCchPrintfW(v29[0], v29[1] - v29[0], L"Trying to call ESimSettingApi without a valid eSim Id");
    v25[0] = 278;
    StringCchPrintfW(
      v31[0],
      v31[1] - v31[0],
      L"%S(%d):%s",
      "CESimSettingApi::UpdateSmdpAddress",
      *(_QWORD *)v25,
      v29[0]);
    v10 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v10 > 2u )
    {
      v13 = &word_180079C7E;
      goto LABEL_9;
    }
LABEL_10:
    std::vector<unsigned short>::~vector<unsigned short>((char **)v31);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v29);
    if ( this != (CESimSettingApi *)-184LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 23);
    return 2147500037LL;
  }
  v34 = 0;
  v15 = LuiSetDefaultSmdpAddress(v9, v3, (char *)this + 64, a2);
  v16 = v15;
  if ( v15 >= 0 )
  {
    v17 = (_DWORD *)std::map<unsigned long,enum ESimSettingOperation>::operator[]((__int64 *)this + 24, &v34);
    v30 = 0;
    v32 = 0;
    *v17 = 8;
    *((_DWORD *)this + 54) = v34;
    *(_OWORD *)v29 = 0;
    *(_OWORD *)v31 = 0;
    std::vector<unsigned short>::resize(v29);
    std::vector<unsigned short>::resize(v31);
    LODWORD(v28) = v34;
    StringCchPrintfW(
      v29[0],
      v29[1] - v29[0],
      L"Set SMDP address eSim=%s, smdpAddress=%s, [Transaction ID] %d",
      (char *)this + 64,
      a2,
      v28);
    v26[0] = 287;
    StringCchPrintfW(
      v31[0],
      v31[1] - v31[0],
      L"%S(%d):%s",
      "CESimSettingApi::UpdateSmdpAddress",
      *(_QWORD *)v26,
      v29[0]);
    v18 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v18 > 4u )
    {
      v35 = v31[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v18,
        (__int64)&byte_180079C9F,
        v19,
        v20,
        (const unsigned __int16 **)&v35);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v31);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v29);
    v30 = 0;
    v32 = 0;
    *(_OWORD *)v29 = 0;
    *(_OWORD *)v31 = 0;
    std::vector<unsigned short>::resize(v29);
    std::vector<unsigned short>::resize(v31);
    StringCchPrintfW(v29[0], v29[1] - v29[0], L"Exit");
    v27[0] = 289;
    StringCchPrintfW(
      v31[0],
      v31[1] - v31[0],
      L"%S(%d):%s",
      "CESimSettingApi::UpdateSmdpAddress",
      *(_QWORD *)v27,
      v29[0]);
    v21 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v21 > 5u )
    {
      v35 = v31[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v21,
        (__int64)qword_180079C38,
        v22,
        v23,
        (const unsigned __int16 **)&v35);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v31);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v29);
    if ( this != (CESimSettingApi *)-184LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 23);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11B,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingapi.cpp",
      (const char *)(unsigned int)v15,
      (int)&v34);
    if ( this != (CESimSettingApi *)-184LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 23);
    return v16;
  }
}

```

## disassembly

```asm
0x180054660  mov     [rsp-28h+arg_8], rbx
0x180054665  mov     [rsp-28h+arg_10], rsi
0x18005466a  push    rbp
0x18005466b  push    rdi
0x18005466c  push    r13
0x18005466e  push    r14
0x180054670  push    r15
0x180054672  mov     rbp, rsp
0x180054675  sub     rsp, 60h
0x180054679  xorps   xmm0, xmm0
0x18005467c  mov     edi, r8d
0x18005467f  mov     rsi, rcx
0x180054682  mov     [rbp+var_8], 0
0x18005468a  lea     rcx, [rbp+var_18]
0x18005468e  mov     [rbp+var_20], 0
0x180054696  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18005469b  mov     r15, rdx
0x18005469e  movdqu  xmmword ptr [rbp+var_30], xmm0
0x1800546a3  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800546a8  lea     rcx, [rbp+var_30]
0x1800546ac  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800546b1  mov     rdx, [rbp+var_18+8]
0x1800546b5  lea     r8, aEnter; "Enter"
0x1800546bc  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x1800546c0  sub     rdx, rcx
0x1800546c3  sar     rdx, 1; unsigned __int64
0x1800546c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800546cb  mov     rdx, [rbp+var_30+8]
0x1800546cf  lea     r13, aCesimsettingap_6; "CESimSettingApi::UpdateSmdpAddress"
0x1800546d6  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x1800546da  lea     r8, aSDS; "%S(%d):%s"
0x1800546e1  mov     rax, [rbp+var_18]
0x1800546e5  sub     rdx, rcx
0x1800546e8  mov     [rsp+60h+var_38], rax
0x1800546ed  mov     r9, r13
0x1800546f0  sar     rdx, 1; unsigned __int64
0x1800546f3  mov     [rsp+60h+var_40], 114h
0x1800546fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180054700  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180054705  mov     ecx, [rax]
0x180054707  cmp     ecx, 5
0x18005470a  jbe     short loc_18005472C
0x18005470c  mov     rcx, [rbp+var_30]
0x180054710  lea     rdx, byte_180079CBF
0x180054717  mov     [rbp+arg_18], rcx
0x18005471b  lea     rcx, [rbp+arg_18]
0x18005471f  mov     qword ptr [rsp+60h+var_40], rcx
0x180054724  mov     rcx, rax
0x180054727  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18005472c  lea     rcx, [rbp+var_30]
0x180054730  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180054735  lea     rcx, [rbp+var_18]
0x180054739  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18005473e  lea     rbx, [rsi+0B8h]
0x180054745  mov     rcx, rbx; SRWLock
0x180054748  call    cs:__imp_AcquireSRWLockExclusive
0x18005474e  mov     rcx, [rsi+98h]
0x180054755  test    rcx, rcx
0x180054758  jnz     loc_1800547EC
0x18005475e  xorps   xmm0, xmm0
0x180054761  mov     [rbp+var_20], rcx
0x180054765  xorps   xmm1, xmm1
0x180054768  mov     [rbp+var_8], rcx
0x18005476c  lea     rcx, [rbp+var_30]
0x180054770  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180054775  movdqu  xmmword ptr [rbp+var_18], xmm1
0x18005477a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18005477f  lea     rcx, [rbp+var_18]
0x180054783  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180054788  mov     rdx, [rbp+var_30+8]
0x18005478c  lea     r8, aTryingToCallEs_0; "Trying to call ESimSettingApi without a"...
0x180054793  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180054797  sub     rdx, rcx
0x18005479a  sar     rdx, 1; unsigned __int64
0x18005479d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800547a2  mov     rdx, [rbp+var_18+8]
0x1800547a6  lea     r8, aSDS; "%S(%d):%s"
0x1800547ad  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x1800547b1  mov     r9, r13
0x1800547b4  mov     rax, [rbp+var_30]
0x1800547b8  sub     rdx, rcx
0x1800547bb  mov     [rsp+60h+var_38], rax
0x1800547c0  sar     rdx, 1; unsigned __int64
0x1800547c3  mov     [rsp+60h+var_40], 116h
0x1800547cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800547d0  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800547d5  mov     ecx, [rax]
0x1800547d7  cmp     ecx, 2
0x1800547da  jbe     loc_18005489A
0x1800547e0  lea     rdx, word_180079CE2
0x1800547e7  jmp     loc_180054881
0x1800547ec  lea     r14, [rsi+40h]
0x1800547f0  xor     eax, eax
0x1800547f2  cmp     ax, [r14]
0x1800547f6  jnz     loc_1800548C4
0x1800547fc  xorps   xmm0, xmm0
0x1800547ff  mov     [rbp+var_20], rax
0x180054803  xorps   xmm1, xmm1
0x180054806  mov     [rbp+var_8], rax
0x18005480a  lea     rcx, [rbp+var_30]
0x18005480e  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180054813  movdqu  xmmword ptr [rbp+var_18], xmm1
0x180054818  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18005481d  lea     rcx, [rbp+var_18]
0x180054821  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180054826  mov     rdx, [rbp+var_30+8]
0x18005482a  lea     r8, aTryingToCallEs; "Trying to call ESimSettingApi without a"...
0x180054831  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180054835  sub     rdx, rcx
0x180054838  sar     rdx, 1; unsigned __int64
0x18005483b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180054840  mov     rdx, [rbp+var_18+8]
0x180054844  lea     r8, aSDS; "%S(%d):%s"
0x18005484b  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18005484f  mov     r9, r13
0x180054852  mov     rax, [rbp+var_30]
0x180054856  sub     rdx, rcx
0x180054859  mov     [rsp+60h+var_38], rax
0x18005485e  sar     rdx, 1; unsigned __int64
0x180054861  mov     [rsp+60h+var_40], 116h
0x180054869  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005486e  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180054873  mov     ecx, [rax]
0x180054875  cmp     ecx, 2
0x180054878  jbe     short loc_18005489A
0x18005487a  lea     rdx, word_180079C7E
0x180054881  mov     rcx, [rbp+var_18]
0x180054885  mov     [rbp+arg_18], rcx
0x180054889  lea     rcx, [rbp+arg_18]
0x18005488d  mov     qword ptr [rsp+60h+var_40], rcx
0x180054892  mov     rcx, rax
0x180054895  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18005489a  lea     rcx, [rbp+var_18]
0x18005489e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800548a3  lea     rcx, [rbp+var_30]
0x1800548a7  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800548ac  test    rbx, rbx
0x1800548af  jz      short loc_1800548BA
0x1800548b1  mov     rcx, rbx; SRWLock
0x1800548b4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800548ba  mov     eax, 80004005h
0x1800548bf  jmp     loc_180054AC0
0x1800548c4  mov     [rbp+arg_0], eax
0x1800548c7  mov     rdx, rdi
0x1800548ca  lea     rax, [rbp+arg_0]
0x1800548ce  mov     r9, r15
0x1800548d1  mov     r8, r14
0x1800548d4  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800548d9  call    cs:__imp_LuiSetDefaultSmdpAddress
0x1800548df  mov     edi, eax
0x1800548e1  test    eax, eax
0x1800548e3  jns     short loc_180054912
0x1800548e5  mov     rcx, [rbp+28h]; this
0x1800548e9  lea     r8, aOnecoreuapNetM_7; "onecoreuap\\net\\mobilebroadbandexperie"...
0x1800548f0  mov     r9d, eax; char *
0x1800548f3  mov     edx, 11Bh; void *
0x1800548f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800548fd  test    rbx, rbx
0x180054900  jz      short loc_18005490B
0x180054902  mov     rcx, rbx; SRWLock
0x180054905  call    cs:__imp_ReleaseSRWLockExclusive
0x18005490b  mov     eax, edi
0x18005490d  jmp     loc_180054AC0
0x180054912  lea     rcx, [rsi+0C0h]
0x180054919  lea     rdx, [rbp+arg_0]
0x18005491d  call    ??A?$map@KW4ESimSettingOperation@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKW4ESimSettingOperation@@@std@@@3@@std@@QEAAAEAW4ESimSettingOperation@@AEBK@Z; std::map<ulong,ESimSettingOperation>::operator[](ulong const &)
0x180054922  xorps   xmm0, xmm0
0x180054925  mov     [rbp+var_20], 0
0x18005492d  xorps   xmm1, xmm1
0x180054930  mov     [rbp+var_8], 0
0x180054938  lea     rcx, [rbp+var_30]
0x18005493c  mov     dword ptr [rax], 8
0x180054942  mov     eax, [rbp+arg_0]
0x180054945  mov     [rsi+0D8h], eax
0x18005494b  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180054950  movdqu  xmmword ptr [rbp+var_18], xmm1
0x180054955  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18005495a  lea     rcx, [rbp+var_18]
0x18005495e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180054963  mov     rdx, [rbp+var_30+8]
0x180054967  lea     r8, aSetSmdpAddress; "Set SMDP address eSim=%s, smdpAddress=%"...
0x18005496e  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180054972  mov     r9, r14
0x180054975  mov     eax, [rbp+arg_0]
0x180054978  sub     rdx, rcx
0x18005497b  mov     dword ptr [rsp+60h+var_38], eax
0x18005497f  sar     rdx, 1; unsigned __int64
0x180054982  mov     qword ptr [rsp+60h+var_40], r15
0x180054987  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005498c  mov     rdx, [rbp+var_18+8]
0x180054990  lea     r8, aSDS; "%S(%d):%s"
0x180054997  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18005499b  mov     r9, r13
0x18005499e  mov     rax, [rbp+var_30]
0x1800549a2  sub     rdx, rcx
0x1800549a5  mov     [rsp+60h+var_38], rax
0x1800549aa  sar     rdx, 1; unsigned __int64
0x1800549ad  mov     [rsp+60h+var_40], 11Fh
0x1800549b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800549ba  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800549bf  mov     ecx, [rax]
0x1800549c1  cmp     ecx, 4
0x1800549c4  jbe     short loc_1800549E6
0x1800549c6  mov     rcx, [rbp+var_18]
0x1800549ca  lea     rdx, byte_180079C9F
0x1800549d1  mov     [rbp+arg_18], rcx
0x1800549d5  lea     rcx, [rbp+arg_18]
0x1800549d9  mov     qword ptr [rsp+60h+var_40], rcx
0x1800549de  mov     rcx, rax
0x1800549e1  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800549e6  lea     rcx, [rbp+var_18]
0x1800549ea  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800549ef  lea     rcx, [rbp+var_30]
0x1800549f3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800549f8  xorps   xmm0, xmm0
0x1800549fb  mov     [rbp+var_20], 0
0x180054a03  xorps   xmm1, xmm1
0x180054a06  mov     [rbp+var_8], 0
0x180054a0e  lea     rcx, [rbp+var_30]
0x180054a12  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180054a17  movdqu  xmmword ptr [rbp+var_18], xmm1
0x180054a1c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180054a21  lea     rcx, [rbp+var_18]
0x180054a25  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180054a2a  mov     rdx, [rbp+var_30+8]
0x180054a2e  lea     r8, aExit; "Exit"
0x180054a35  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180054a39  sub     rdx, rcx
0x180054a3c  sar     rdx, 1; unsigned __int64
0x180054a3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180054a44  mov     rdx, [rbp+var_18+8]
0x180054a48  lea     r8, aSDS; "%S(%d):%s"
0x180054a4f  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180054a53  mov     r9, r13
0x180054a56  mov     rax, [rbp+var_30]
0x180054a5a  sub     rdx, rcx
0x180054a5d  mov     [rsp+60h+var_38], rax
0x180054a62  sar     rdx, 1; unsigned __int64
0x180054a65  mov     [rsp+60h+var_40], 121h
0x180054a6d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180054a72  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180054a77  mov     ecx, [rax]
0x180054a79  cmp     ecx, 5
0x180054a7c  jbe     short loc_180054A9E
0x180054a7e  mov     rcx, [rbp+var_18]
0x180054a82  lea     rdx, qword_180079C38
0x180054a89  mov     [rbp+arg_18], rcx
0x180054a8d  lea     rcx, [rbp+arg_18]
0x180054a91  mov     qword ptr [rsp+60h+var_40], rcx
0x180054a96  mov     rcx, rax
0x180054a99  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180054a9e  lea     rcx, [rbp+var_18]
0x180054aa2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180054aa7  lea     rcx, [rbp+var_30]
0x180054aab  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180054ab0  test    rbx, rbx
0x180054ab3  jz      short loc_180054ABE
0x180054ab5  mov     rcx, rbx; SRWLock
0x180054ab8  call    cs:__imp_ReleaseSRWLockExclusive
0x180054abe  xor     eax, eax
0x180054ac0  lea     r11, [rsp+60h+var_s0]
0x180054ac5  mov     rbx, [r11+38h]
0x180054ac9  mov     rsi, [r11+40h]
0x180054acd  mov     rsp, r11
0x180054ad0  pop     r15
0x180054ad2  pop     r14
0x180054ad4  pop     r13
0x180054ad6  pop     rdi
0x180054ad7  pop     rbp
0x180054ad8  retn
```
