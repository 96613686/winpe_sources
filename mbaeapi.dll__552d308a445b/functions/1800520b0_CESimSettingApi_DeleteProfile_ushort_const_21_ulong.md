# CESimSettingApi::DeleteProfile(ushort const (*)[21],ulong)

- ea: `0x1800520b0`
- end: `0x1800525a4`
- name: `?DeleteProfile@CESimSettingApi@@UEAAJPEAY0BF@$$CBGK@Z`
- size: `1268`
- prototype: `__int64 __fastcall(CESimSettingApi *__hidden this, const unsigned __int16 (*)[21], unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800171b8`
- `0x1800172bc`
- `0x18001dd10`
- `0x18001e058`
- `0x180050618`
- `0x1800520b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800521a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800521a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052305`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800523bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052575`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052305`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800523bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052575`
- `luiapi!LuiDeleteProfile` at `0x180052386`
- `luiapi!LuiDeleteProfile` at `0x180052386`

## string_xrefs

- `0x180052439`: `Delete profile eSim=%s, profileId=%s, [Transaction ID] %d`
- `0x18005212b`: `CESimSettingApi::DeleteProfile`

## pseudocode

```c
__int64 __fastcall CESimSettingApi::DeleteProfile(
        CESimSettingApi *this,
        const unsigned __int16 (*a2)[21],
        unsigned int a3)
{
  __int64 v3; // r15
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int16 *v13; // rdx
  __int64 v15; // rax
  __int128 v16; // xmm0
  __int128 *v17; // r9
  int v18; // eax
  unsigned int v19; // esi
  _DWORD *v20; // rax
  __int128 *v21; // r8
  const struct _tlgProvider_t *v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  const struct _tlgProvider_t *v25; // rax
  __int64 v26; // r8
  __int64 v27; // r9
  int v28; // [rsp+20h] [rbp-59h]
  int v29[2]; // [rsp+20h] [rbp-59h]
  int v30[2]; // [rsp+20h] [rbp-59h]
  int v31[2]; // [rsp+20h] [rbp-59h]
  __int64 v32; // [rsp+28h] [rbp-51h]
  unsigned __int16 *v33; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int16 *v34[2]; // [rsp+38h] [rbp-41h] BYREF
  __int64 v35; // [rsp+48h] [rbp-31h]
  unsigned __int16 *v36[2]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v37; // [rsp+60h] [rbp-19h]
  int v38; // [rsp+68h] [rbp-11h] BYREF
  __int128 v39; // [rsp+70h] [rbp-9h] BYREF
  __int128 v40; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v3 = a3;
  v37 = 0;
  *(_OWORD *)v36 = 0;
  v35 = 0;
  *(_OWORD *)v34 = 0;
  std::vector<unsigned short>::resize(v36);
  std::vector<unsigned short>::resize(v34);
  StringCchPrintfW(v36[0], v36[1] - v36[0], L"Enter");
  v28 = 166;
  StringCchPrintfW(v34[0], v34[1] - v34[0], L"%S(%d):%s", "CESimSettingApi::DeleteProfile", v28, v36[0]);
  v6 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    v33 = v34[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)byte_18007A06B,
      v7,
      v8,
      (const unsigned __int16 **)&v33);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v34);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v36);
  AcquireSRWLockExclusive((PSRWLOCK)this + 23);
  if ( !*((_QWORD *)this + 19) )
  {
    v35 = 0;
    *(_OWORD *)v34 = 0;
    v37 = 0;
    *(_OWORD *)v36 = 0;
    std::vector<unsigned short>::resize(v34);
    std::vector<unsigned short>::resize(v36);
    StringCchPrintfW(v34[0], v34[1] - v34[0], L"Trying to call ESimSettingApi without a valid LpaSvc handle.");
    v29[0] = 168;
    StringCchPrintfW(v36[0], v36[1] - v36[0], L"%S(%d):%s", "CESimSettingApi::DeleteProfile", *(_QWORD *)v29, v34[0]);
    v10 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v10 > 2u )
    {
      v13 = &word_18007A006;
LABEL_9:
      v33 = v36[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v10,
        (__int64)v13,
        v11,
        v12,
        (const unsigned __int16 **)&v33);
      goto LABEL_10;
    }
    goto LABEL_10;
  }
  if ( !*((_WORD *)this + 32) )
  {
    v35 = 0;
    *(_OWORD *)v34 = 0;
    v37 = 0;
    *(_OWORD *)v36 = 0;
    std::vector<unsigned short>::resize(v34);
    std::vector<unsigned short>::resize(v36);
    StringCchPrintfW(v34[0], v34[1] - v34[0], L"Trying to call ESimSettingApi without a valid eSim Id");
    v29[0] = 168;
    StringCchPrintfW(v36[0], v36[1] - v36[0], L"%S(%d):%s", "CESimSettingApi::DeleteProfile", *(_QWORD *)v29, v34[0]);
    v10 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v10 > 2u )
    {
      v13 = (__int16 *)&byte_18007A027;
      goto LABEL_9;
    }
LABEL_10:
    std::vector<unsigned short>::~vector<unsigned short>((char **)v36);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v34);
    if ( this != (CESimSettingApi *)-184LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 23);
    return 2147500037LL;
  }
  v38 = 0;
  v39 = 0;
  v33 = (unsigned __int16 *)23;
  v40 = 0;
  v15 = std::wstring::_Allocate_for_capacity<0>(v9, &v33);
  v16 = *(_OWORD *)a2;
  v17 = &v39;
  *(_QWORD *)&v39 = v15;
  *((_QWORD *)&v40 + 1) = v33;
  *(_QWORD *)&v40 = 21;
  *(_OWORD *)v15 = v16;
  *(_OWORD *)(v15 + 16) = *(_OWORD *)&(*a2)[8];
  *(_OWORD *)(v15 + 26) = *(_OWORD *)&(*a2)[13];
  *(_WORD *)(v15 + 42) = 0;
  if ( *((_QWORD *)&v40 + 1) > 7u )
    v17 = (__int128 *)v39;
  v18 = LuiDeleteProfile(*((_QWORD *)this + 19), v3, (char *)this + 64, v17);
  v19 = v18;
  if ( v18 >= 0 )
  {
    v20 = (_DWORD *)std::map<unsigned long,enum ESimSettingOperation>::operator[]((__int64 *)this + 24, &v38);
    v35 = 0;
    v37 = 0;
    *v20 = 4;
    *((_DWORD *)this + 54) = v38;
    *(_OWORD *)v34 = 0;
    *(_OWORD *)v36 = 0;
    std::vector<unsigned short>::resize(v34);
    std::vector<unsigned short>::resize(v36);
    v21 = &v39;
    if ( *((_QWORD *)&v40 + 1) > 7u )
      v21 = (__int128 *)v39;
    LODWORD(v32) = v38;
    StringCchPrintfW(
      v34[0],
      v34[1] - v34[0],
      L"Delete profile eSim=%s, profileId=%s, [Transaction ID] %d",
      (char *)this + 64,
      v21,
      v32);
    v30[0] = 178;
    StringCchPrintfW(v36[0], v36[1] - v36[0], L"%S(%d):%s", "CESimSettingApi::DeleteProfile", *(_QWORD *)v30, v34[0]);
    v22 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v22 > 4u )
    {
      v33 = v36[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v22,
        (__int64)&word_180079FE6,
        v23,
        v24,
        (const unsigned __int16 **)&v33);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v36);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v34);
    v35 = 0;
    v37 = 0;
    *(_OWORD *)v34 = 0;
    *(_OWORD *)v36 = 0;
    std::vector<unsigned short>::resize(v34);
    std::vector<unsigned short>::resize(v36);
    StringCchPrintfW(v34[0], v34[1] - v34[0], L"Exit");
    v31[0] = 180;
    StringCchPrintfW(v36[0], v36[1] - v36[0], L"%S(%d):%s", "CESimSettingApi::DeleteProfile", *(_QWORD *)v31, v34[0]);
    v25 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v25 > 5u )
    {
      v33 = v36[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v25,
        (__int64)qword_180079FA0,
        v26,
        v27,
        (const unsigned __int16 **)&v33);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v36);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v34);
    std::wstring::~wstring((char **)&v39);
    if ( this != (CESimSettingApi *)-184LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 23);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingapi.cpp",
      (const char *)(unsigned int)v18,
      (int)&v38);
    std::wstring::~wstring((char **)&v39);
    if ( this != (CESimSettingApi *)-184LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 23);
    return v19;
  }
}

```

## disassembly

```asm
0x1800520b0  mov     [rsp-8+arg_18], rbx
0x1800520b5  push    rbp
0x1800520b6  push    rsi
0x1800520b7  push    rdi
0x1800520b8  push    r12
0x1800520ba  push    r13
0x1800520bc  push    r14
0x1800520be  push    r15
0x1800520c0  lea     rbp, [rsp-27h]
0x1800520c5  sub     rsp, 0A0h
0x1800520cc  mov     rax, cs:__security_cookie
0x1800520d3  xor     rax, rsp
0x1800520d6  mov     [rbp+57h+var_40], rax
0x1800520da  xorps   xmm0, xmm0
0x1800520dd  mov     r15d, r8d
0x1800520e0  mov     rdi, rcx
0x1800520e3  xor     r12d, r12d
0x1800520e6  lea     rcx, [rbp+57h+var_80]
0x1800520ea  mov     [rbp+57h+var_70], r12
0x1800520ee  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x1800520f3  mov     [rbp+57h+var_88], r12
0x1800520f7  mov     rsi, rdx
0x1800520fa  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x1800520ff  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180052104  lea     rcx, [rbp+57h+var_98]
0x180052108  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18005210d  mov     rdx, [rbp+57h+var_80+8]
0x180052111  lea     r8, aEnter; "Enter"
0x180052118  mov     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x18005211c  sub     rdx, rcx
0x18005211f  sar     rdx, 1; unsigned __int64
0x180052122  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052127  mov     rdx, [rbp+57h+var_98+8]
0x18005212b  lea     r13, aCesimsettingap_10; "CESimSettingApi::DeleteProfile"
0x180052132  mov     rcx, [rbp+57h+var_98]; unsigned __int16 *
0x180052136  lea     r8, aSDS; "%S(%d):%s"
0x18005213d  mov     rax, [rbp+57h+var_80]
0x180052141  sub     rdx, rcx
0x180052144  mov     [rsp+0D0h+var_A8], rax
0x180052149  mov     r9, r13
0x18005214c  sar     rdx, 1; unsigned __int64
0x18005214f  mov     [rsp+0D0h+var_B0], 0A6h
0x180052157  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005215c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180052161  mov     ecx, [rax]
0x180052163  cmp     ecx, 5
0x180052166  jbe     short loc_180052188
0x180052168  mov     rcx, [rbp+57h+var_98]
0x18005216c  lea     rdx, byte_18007A06B
0x180052173  mov     [rbp+57h+var_A0], rcx
0x180052177  lea     rcx, [rbp+57h+var_A0]
0x18005217b  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x180052180  mov     rcx, rax
0x180052183  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180052188  lea     rcx, [rbp+57h+var_98]
0x18005218c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180052191  lea     rcx, [rbp+57h+var_80]
0x180052195  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18005219a  lea     rbx, [rdi+0B8h]
0x1800521a1  mov     rcx, rbx; SRWLock
0x1800521a4  call    cs:__imp_AcquireSRWLockExclusive
0x1800521aa  xorps   xmm0, xmm0
0x1800521ad  xorps   xmm1, xmm1
0x1800521b0  cmp     [rdi+98h], r12
0x1800521b7  jnz     loc_180052245
0x1800521bd  lea     rcx, [rbp+57h+var_98]
0x1800521c1  mov     [rbp+57h+var_88], r12
0x1800521c5  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x1800521ca  mov     [rbp+57h+var_70], r12
0x1800521ce  movdqu  xmmword ptr [rbp+57h+var_80], xmm1
0x1800521d3  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800521d8  lea     rcx, [rbp+57h+var_80]
0x1800521dc  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800521e1  mov     rdx, [rbp+57h+var_98+8]
0x1800521e5  lea     r8, aTryingToCallEs_0; "Trying to call ESimSettingApi without a"...
0x1800521ec  mov     rcx, [rbp+57h+var_98]; unsigned __int16 *
0x1800521f0  sub     rdx, rcx
0x1800521f3  sar     rdx, 1; unsigned __int64
0x1800521f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800521fb  mov     rdx, [rbp+57h+var_80+8]
0x1800521ff  lea     r8, aSDS; "%S(%d):%s"
0x180052206  mov     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x18005220a  mov     r9, r13
0x18005220d  mov     rax, [rbp+57h+var_98]
0x180052211  sub     rdx, rcx
0x180052214  mov     [rsp+0D0h+var_A8], rax
0x180052219  sar     rdx, 1; unsigned __int64
0x18005221c  mov     [rsp+0D0h+var_B0], 0A8h
0x180052224  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052229  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18005222e  mov     ecx, [rax]
0x180052230  cmp     ecx, 2
0x180052233  jbe     loc_1800522EB
0x180052239  lea     rdx, word_18007A006
0x180052240  jmp     loc_1800522D2
0x180052245  lea     r14, [rdi+40h]
0x180052249  cmp     r12w, [r14]
0x18005224d  jnz     loc_180052315
0x180052253  lea     rcx, [rbp+57h+var_98]
0x180052257  mov     [rbp+57h+var_88], r12
0x18005225b  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x180052260  mov     [rbp+57h+var_70], r12
0x180052264  movdqu  xmmword ptr [rbp+57h+var_80], xmm1
0x180052269  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18005226e  lea     rcx, [rbp+57h+var_80]
0x180052272  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180052277  mov     rdx, [rbp+57h+var_98+8]
0x18005227b  lea     r8, aTryingToCallEs; "Trying to call ESimSettingApi without a"...
0x180052282  mov     rcx, [rbp+57h+var_98]; unsigned __int16 *
0x180052286  sub     rdx, rcx
0x180052289  sar     rdx, 1; unsigned __int64
0x18005228c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052291  mov     rdx, [rbp+57h+var_80+8]
0x180052295  lea     r8, aSDS; "%S(%d):%s"
0x18005229c  mov     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x1800522a0  mov     r9, r13
0x1800522a3  mov     rax, [rbp+57h+var_98]
0x1800522a7  sub     rdx, rcx
0x1800522aa  mov     [rsp+0D0h+var_A8], rax
0x1800522af  sar     rdx, 1; unsigned __int64
0x1800522b2  mov     [rsp+0D0h+var_B0], 0A8h
0x1800522ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800522bf  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800522c4  mov     ecx, [rax]
0x1800522c6  cmp     ecx, 2
0x1800522c9  jbe     short loc_1800522EB
0x1800522cb  lea     rdx, byte_18007A027
0x1800522d2  mov     rcx, [rbp+57h+var_80]
0x1800522d6  mov     [rbp+57h+var_A0], rcx
0x1800522da  lea     rcx, [rbp+57h+var_A0]
0x1800522de  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x1800522e3  mov     rcx, rax
0x1800522e6  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800522eb  lea     rcx, [rbp+57h+var_80]
0x1800522ef  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800522f4  lea     rcx, [rbp+57h+var_98]
0x1800522f8  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800522fd  test    rbx, rbx
0x180052300  jz      short loc_18005230B
0x180052302  mov     rcx, rbx; SRWLock
0x180052305  call    cs:__imp_ReleaseSRWLockExclusive
0x18005230b  mov     eax, 80004005h
0x180052310  jmp     loc_18005257D
0x180052315  lea     rdx, [rbp+57h+var_A0]
0x180052319  mov     [rbp+57h+var_68], r12d
0x18005231d  movups  [rbp+57h+var_60], xmm0
0x180052321  mov     [rbp+57h+var_A0], 17h
0x180052329  movdqu  [rbp+57h+var_50], xmm1
0x18005232e  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180052333  movups  xmm0, xmmword ptr [rsi]
0x180052336  mov     rcx, [rbp+57h+var_A0]
0x18005233a  lea     r9, [rbp+57h+var_60]
0x18005233e  mov     qword ptr [rbp+57h+var_60], rax
0x180052342  mov     rdx, r15
0x180052345  mov     qword ptr [rbp+57h+var_50+8], rcx
0x180052349  mov     r8, r14
0x18005234c  mov     qword ptr [rbp+57h+var_50], 15h
0x180052354  movups  xmmword ptr [rax], xmm0
0x180052357  movups  xmm1, xmmword ptr [rsi+10h]
0x18005235b  movups  xmmword ptr [rax+10h], xmm1
0x18005235f  movups  xmm0, xmmword ptr [rsi+1Ah]
0x180052363  movups  xmmword ptr [rax+1Ah], xmm0
0x180052367  mov     [rax+2Ah], r12w
0x18005236c  lea     rax, [rbp+57h+var_68]
0x180052370  cmp     qword ptr [rbp+57h+var_50+8], 7
0x180052375  mov     rcx, [rdi+98h]
0x18005237c  cmova   r9, qword ptr [rbp+57h+var_60]
0x180052381  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180052386  call    cs:__imp_LuiDeleteProfile
0x18005238c  mov     esi, eax
0x18005238e  test    eax, eax
0x180052390  jns     short loc_1800523C8
0x180052392  mov     rcx, [rbp+5Fh]; this
0x180052396  lea     r8, aOnecoreuapNetM_7; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18005239d  mov     r9d, eax; char *
0x1800523a0  mov     edx, 0AEh; void *
0x1800523a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800523aa  lea     rcx, [rbp+57h+var_60]
0x1800523ae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800523b3  test    rbx, rbx
0x1800523b6  jz      short loc_1800523C1
0x1800523b8  mov     rcx, rbx; SRWLock
0x1800523bb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800523c1  mov     eax, esi
0x1800523c3  jmp     loc_18005257D
0x1800523c8  lea     rcx, [rdi+0C0h]
0x1800523cf  lea     rdx, [rbp+57h+var_68]
0x1800523d3  call    ??A?$map@KW4ESimSettingOperation@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKW4ESimSettingOperation@@@std@@@3@@std@@QEAAAEAW4ESimSettingOperation@@AEBK@Z; std::map<ulong,ESimSettingOperation>::operator[](ulong const &)
0x1800523d8  xorps   xmm0, xmm0
0x1800523db  mov     [rbp+57h+var_88], r12
0x1800523df  xorps   xmm1, xmm1
0x1800523e2  mov     [rbp+57h+var_70], r12
0x1800523e6  lea     rcx, [rbp+57h+var_98]
0x1800523ea  mov     dword ptr [rax], 4
0x1800523f0  mov     eax, [rbp+57h+var_68]
0x1800523f3  mov     [rdi+0D8h], eax
0x1800523f9  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x1800523fe  movdqu  xmmword ptr [rbp+57h+var_80], xmm1
0x180052403  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180052408  lea     rcx, [rbp+57h+var_80]
0x18005240c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180052411  cmp     qword ptr [rbp+57h+var_50+8], 7
0x180052416  lea     r8, [rbp+57h+var_60]
0x18005241a  mov     rdx, [rbp+57h+var_98+8]
0x18005241e  mov     r9, r14
0x180052421  cmova   r8, qword ptr [rbp+57h+var_60]
0x180052426  mov     rcx, [rbp+57h+var_98]; unsigned __int16 *
0x18005242a  mov     eax, [rbp+57h+var_68]
0x18005242d  sub     rdx, rcx
0x180052430  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180052434  mov     qword ptr [rsp+0D0h+var_B0], r8
0x180052439  lea     r8, aDeleteProfileE; "Delete profile eSim=%s, profileId=%s, ["...
0x180052440  sar     rdx, 1; unsigned __int64
0x180052443  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052448  mov     rdx, [rbp+57h+var_80+8]
0x18005244c  lea     r8, aSDS; "%S(%d):%s"
0x180052453  mov     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x180052457  mov     r9, r13
0x18005245a  mov     rax, [rbp+57h+var_98]
0x18005245e  sub     rdx, rcx
0x180052461  mov     [rsp+0D0h+var_A8], rax
0x180052466  sar     rdx, 1; unsigned __int64
0x180052469  mov     [rsp+0D0h+var_B0], 0B2h
0x180052471  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052476  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18005247b  mov     ecx, [rax]
0x18005247d  cmp     ecx, 4
0x180052480  jbe     short loc_1800524A2
0x180052482  mov     rcx, [rbp+57h+var_80]
0x180052486  lea     rdx, word_180079FE6
0x18005248d  mov     [rbp+57h+var_A0], rcx
0x180052491  lea     rcx, [rbp+57h+var_A0]
0x180052495  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18005249a  mov     rcx, rax
0x18005249d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800524a2  lea     rcx, [rbp+57h+var_80]
0x1800524a6  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800524ab  lea     rcx, [rbp+57h+var_98]
0x1800524af  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800524b4  xorps   xmm0, xmm0
0x1800524b7  mov     [rbp+57h+var_88], r12
0x1800524bb  xorps   xmm1, xmm1
0x1800524be  mov     [rbp+57h+var_70], r12
0x1800524c2  lea     rcx, [rbp+57h+var_98]
0x1800524c6  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x1800524cb  movdqu  xmmword ptr [rbp+57h+var_80], xmm1
0x1800524d0  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800524d5  lea     rcx, [rbp+57h+var_80]
0x1800524d9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800524de  mov     rdx, [rbp+57h+var_98+8]
0x1800524e2  lea     r8, aExit; "Exit"
0x1800524e9  mov     rcx, [rbp+57h+var_98]; unsigned __int16 *
0x1800524ed  sub     rdx, rcx
0x1800524f0  sar     rdx, 1; unsigned __int64
0x1800524f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800524f8  mov     rdx, [rbp+57h+var_80+8]
0x1800524fc  lea     r8, aSDS; "%S(%d):%s"
0x180052503  mov     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x180052507  mov     r9, r13
0x18005250a  mov     rax, [rbp+57h+var_98]
0x18005250e  sub     rdx, rcx
0x180052511  mov     [rsp+0D0h+var_A8], rax
0x180052516  sar     rdx, 1; unsigned __int64
0x180052519  mov     [rsp+0D0h+var_B0], 0B4h
0x180052521  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052526  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18005252b  mov     ecx, [rax]
0x18005252d  cmp     ecx, 5
0x180052530  jbe     short loc_180052552
0x180052532  mov     rcx, [rbp+57h+var_80]
0x180052536  lea     rdx, qword_180079FA0
0x18005253d  mov     [rbp+57h+var_A0], rcx
0x180052541  lea     rcx, [rbp+57h+var_A0]
0x180052545  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18005254a  mov     rcx, rax
0x18005254d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180052552  lea     rcx, [rbp+57h+var_80]
0x180052556  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18005255b  lea     rcx, [rbp+57h+var_98]
0x18005255f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180052564  lea     rcx, [rbp+57h+var_60]
0x180052568  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005256d  test    rbx, rbx
0x180052570  jz      short loc_18005257B
0x180052572  mov     rcx, rbx; SRWLock
0x180052575  call    cs:__imp_ReleaseSRWLockExclusive
0x18005257b  xor     eax, eax
0x18005257d  mov     rcx, [rbp+57h+var_40]
0x180052581  xor     rcx, rsp; StackCookie
0x180052584  call    __security_check_cookie
0x180052589  mov     rbx, [rsp+0D0h+arg_18]
0x180052591  add     rsp, 0A0h
0x180052598  pop     r15
0x18005259a  pop     r14
0x18005259c  pop     r13
0x18005259e  pop     r12
0x1800525a0  pop     rdi
0x1800525a1  pop     rsi
0x1800525a2  pop     rbp
0x1800525a3  retn
  ... truncated ...
```
