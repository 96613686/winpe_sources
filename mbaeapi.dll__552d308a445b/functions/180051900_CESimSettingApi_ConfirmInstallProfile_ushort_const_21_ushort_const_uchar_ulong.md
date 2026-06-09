# CESimSettingApi::ConfirmInstallProfile(ushort const (*)[21],ushort const *,uchar,ulong)

- ea: `0x180051900`
- end: `0x180051d93`
- name: `?ConfirmInstallProfile@CESimSettingApi@@UEAAJPEAY0BF@$$CBGPEBGEK@Z`
- size: `1171`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, const unsigned __int16 (*)[21], const unsigned __int16 *, char, unsigned int)`
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
- `0x180051900`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800519e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800519e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051b54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051bb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051d77`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051b54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051bb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051d77`
- `luiapi!LuiInstallProfile` at `0x180051b8a`
- `luiapi!LuiInstallProfile` at `0x180051b8a`

## string_xrefs

- `0x180051c35`: `ConfirmInstallProfile with eSim=%s, profileId=%s, confirmationCode=%s, Install=%d, [Transaction ID] %d`
- `0x18005196c`: `CESimSettingApi::ConfirmInstallProfile`
- `0x180051a40`: `CESimSettingApi::ConfirmInstallProfile`
- `0x180051ae0`: `CESimSettingApi::ConfirmInstallProfile`
- `0x180051c4f`: `CESimSettingApi::ConfirmInstallProfile`
- `0x180051d03`: `CESimSettingApi::ConfirmInstallProfile`

## pseudocode

```c
__int64 __fastcall CESimSettingApi::ConfirmInstallProfile(
        RTL_SRWLOCK *this,
        const unsigned __int16 (*a2)[21],
        const unsigned __int16 *a3,
        char a4,
        unsigned int a5)
{
  const struct _tlgProvider_t *v9; // rax
  int v10; // r8d
  int v11; // r9d
  PVOID Ptr; // rcx
  const struct _tlgProvider_t *v13; // rax
  int v14; // r8d
  int v15; // r9d
  __int16 *v16; // rdx
  int v18; // eax
  unsigned int v19; // edi
  _DWORD *v20; // rax
  const struct _tlgProvider_t *v21; // rax
  int v22; // r8d
  int v23; // r9d
  const struct _tlgProvider_t *v24; // rax
  int v25; // r8d
  int v26; // r9d
  int v27; // [rsp+20h] [rbp-51h]
  int v28[2]; // [rsp+20h] [rbp-51h]
  int v29[2]; // [rsp+20h] [rbp-51h]
  int v30[2]; // [rsp+20h] [rbp-51h]
  int *v31; // [rsp+30h] [rbp-41h]
  int v32; // [rsp+38h] [rbp-39h]
  unsigned __int16 *v33; // [rsp+40h] [rbp-31h] BYREF
  unsigned __int16 *v34[2]; // [rsp+48h] [rbp-29h] BYREF
  __int64 v35; // [rsp+58h] [rbp-19h]
  unsigned __int16 *v36[2]; // [rsp+60h] [rbp-11h] BYREF
  __int64 v37; // [rsp+70h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]
  int v39; // [rsp+D0h] [rbp+5Fh] BYREF

  *(_OWORD *)v36 = 0;
  v37 = 0;
  *(_OWORD *)v34 = 0;
  v35 = 0;
  std::vector<unsigned short>::resize(v36);
  std::vector<unsigned short>::resize(v34);
  StringCchPrintfW(v36[0], v36[1] - v36[0], L"Enter");
  v27 = 207;
  StringCchPrintfW(v34[0], v34[1] - v34[0], L"%S(%d):%s", "CESimSettingApi::ConfirmInstallProfile", v27, v36[0]);
  v9 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v9 > 5u )
  {
    v33 = v34[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v9,
      (unsigned int)&byte_180079ED7,
      v10,
      v11,
      (__int64)&v33);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v34);
  std::vector<unsigned short>::~vector<unsigned short>(v36);
  AcquireSRWLockExclusive(this + 23);
  Ptr = this[19].Ptr;
  if ( !Ptr )
  {
    v35 = 0;
    v37 = 0;
    *(_OWORD *)v34 = 0;
    *(_OWORD *)v36 = 0;
    std::vector<unsigned short>::resize(v34);
    std::vector<unsigned short>::resize(v36);
    StringCchPrintfW(v34[0], v34[1] - v34[0], L"Trying to call ESimSettingApi without a valid LpaSvc handle.");
    v28[0] = 209;
    StringCchPrintfW(
      v36[0],
      v36[1] - v36[0],
      L"%S(%d):%s",
      "CESimSettingApi::ConfirmInstallProfile",
      *(_QWORD *)v28,
      v34[0]);
    v13 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v13 > 2u )
    {
      v16 = word_180079EFA;
LABEL_9:
      v33 = v36[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v13,
        (_DWORD)v16,
        v14,
        v15,
        (__int64)&v33);
      goto LABEL_10;
    }
    goto LABEL_10;
  }
  if ( !LOWORD(this[8].Ptr) )
  {
    v35 = 0;
    v37 = 0;
    *(_OWORD *)v34 = 0;
    *(_OWORD *)v36 = 0;
    std::vector<unsigned short>::resize(v34);
    std::vector<unsigned short>::resize(v36);
    StringCchPrintfW(v34[0], v34[1] - v34[0], L"Trying to call ESimSettingApi without a valid eSim Id");
    v28[0] = 209;
    StringCchPrintfW(
      v36[0],
      v36[1] - v36[0],
      L"%S(%d):%s",
      "CESimSettingApi::ConfirmInstallProfile",
      *(_QWORD *)v28,
      v34[0]);
    v13 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v13 > 2u )
    {
      v16 = &word_180079EB6;
      goto LABEL_9;
    }
LABEL_10:
    std::vector<unsigned short>::~vector<unsigned short>(v36);
    std::vector<unsigned short>::~vector<unsigned short>(v34);
    if ( this != (RTL_SRWLOCK *)-184LL )
      ReleaseSRWLockExclusive(this + 23);
    return 2147500037LL;
  }
  v31 = &v39;
  v39 = 0;
  v18 = LuiInstallProfile(Ptr, a5, &this[8], (const unsigned __int16 *)a2);
  v19 = v18;
  if ( v18 >= 0 )
  {
    v20 = (_DWORD *)std::map<unsigned long,enum ESimSettingOperation>::operator[](&this[24], &v39);
    *(_OWORD *)v34 = 0;
    *v20 = 6;
    LODWORD(this[27].Ptr) = v39;
    v35 = 0;
    *(_OWORD *)v36 = 0;
    v37 = 0;
    std::vector<unsigned short>::resize(v34);
    std::vector<unsigned short>::resize(v36);
    v32 = v39;
    LODWORD(v31) = a4 != 0;
    StringCchPrintfW(
      v34[0],
      v34[1] - v34[0],
      L"ConfirmInstallProfile with eSim=%s, profileId=%s, confirmationCode=%s, Install=%d, [Transaction ID] %d",
      &this[8],
      a2,
      a3,
      v31,
      v32);
    v29[0] = 231;
    StringCchPrintfW(
      v36[0],
      v36[1] - v36[0],
      L"%S(%d):%s",
      "CESimSettingApi::ConfirmInstallProfile",
      *(_QWORD *)v29,
      v34[0]);
    v21 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v21 > 4u )
    {
      v33 = v36[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v21,
        (unsigned int)byte_180079E73,
        v22,
        v23,
        (__int64)&v33);
    }
    std::vector<unsigned short>::~vector<unsigned short>(v36);
    std::vector<unsigned short>::~vector<unsigned short>(v34);
    v35 = 0;
    v37 = 0;
    *(_OWORD *)v34 = 0;
    *(_OWORD *)v36 = 0;
    std::vector<unsigned short>::resize(v34);
    std::vector<unsigned short>::resize(v36);
    StringCchPrintfW(v34[0], v34[1] - v34[0], L"Exit");
    v30[0] = 233;
    StringCchPrintfW(
      v36[0],
      v36[1] - v36[0],
      L"%S(%d):%s",
      "CESimSettingApi::ConfirmInstallProfile",
      *(_QWORD *)v30,
      v34[0]);
    v24 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v24 > 5u )
    {
      v33 = v36[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v24,
        (unsigned int)byte_180079E93,
        v25,
        v26,
        (__int64)&v33);
    }
    std::vector<unsigned short>::~vector<unsigned short>(v36);
    std::vector<unsigned short>::~vector<unsigned short>(v34);
    if ( this != (RTL_SRWLOCK *)-184LL )
      ReleaseSRWLockExclusive(this + 23);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingapi.cpp",
      (const char *)(unsigned int)v18,
      a4 == 0);
    if ( this != (RTL_SRWLOCK *)-184LL )
      ReleaseSRWLockExclusive(this + 23);
    return v19;
  }
}

```

## disassembly

```asm
0x180051900  push    rbp
0x180051902  push    rbx
0x180051903  push    rsi
0x180051904  push    rdi
0x180051905  push    r12
0x180051907  push    r13
0x180051909  push    r14
0x18005190b  push    r15
0x18005190d  lea     rbp, [rsp-17h]
0x180051912  sub     rsp, 88h
0x180051919  xorps   xmm0, xmm0
0x18005191c  mov     rsi, rcx
0x18005191f  xor     edi, edi
0x180051921  lea     rcx, [rbp+4Fh+var_60]
0x180051925  movdqu  xmmword ptr [rbp+4Fh+var_60], xmm0
0x18005192a  mov     [rbp+4Fh+var_50], rdi
0x18005192e  mov     r15b, r9b
0x180051931  movdqu  xmmword ptr [rbp+4Fh+var_78], xmm0
0x180051936  mov     [rbp+4Fh+var_68], rdi
0x18005193a  mov     r12, r8
0x18005193d  mov     r13, rdx
0x180051940  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180051945  lea     rcx, [rbp+4Fh+var_78]
0x180051949  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18005194e  mov     rdx, [rbp+4Fh+var_60+8]
0x180051952  lea     r8, aEnter; "Enter"
0x180051959  mov     rcx, [rbp+4Fh+var_60]; unsigned __int16 *
0x18005195d  sub     rdx, rcx
0x180051960  sar     rdx, 1; unsigned __int64
0x180051963  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180051968  mov     rdx, [rbp+4Fh+var_78+8]
0x18005196c  lea     r9, aCesimsettingap_8; "CESimSettingApi::ConfirmInstallProfile"
0x180051973  mov     rcx, [rbp+4Fh+var_78]; unsigned __int16 *
0x180051977  lea     r8, aSDS; "%S(%d):%s"
0x18005197e  mov     rax, [rbp+4Fh+var_60]
0x180051982  sub     rdx, rcx
0x180051985  mov     [rsp+0C0h+var_98], rax
0x18005198a  sar     rdx, 1; unsigned __int64
0x18005198d  mov     [rsp+0C0h+var_A0], 0CFh
0x180051995  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005199a  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18005199f  mov     ecx, [rax]
0x1800519a1  cmp     ecx, 5
0x1800519a4  jbe     short loc_1800519C6
0x1800519a6  mov     rcx, [rbp+4Fh+var_78]
0x1800519aa  lea     rdx, byte_180079ED7
0x1800519b1  mov     [rbp+4Fh+var_80], rcx
0x1800519b5  lea     rcx, [rbp+4Fh+var_80]
0x1800519b9  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x1800519be  mov     rcx, rax
0x1800519c1  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800519c6  lea     rcx, [rbp+4Fh+var_78]
0x1800519ca  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800519cf  lea     rcx, [rbp+4Fh+var_60]
0x1800519d3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800519d8  lea     rbx, [rsi+0B8h]
0x1800519df  mov     rcx, rbx; SRWLock
0x1800519e2  call    cs:__imp_AcquireSRWLockExclusive
0x1800519e8  mov     rcx, [rsi+98h]
0x1800519ef  test    rcx, rcx
0x1800519f2  jnz     loc_180051A8A
0x1800519f8  xorps   xmm0, xmm0
0x1800519fb  mov     [rbp+4Fh+var_68], rdi
0x1800519ff  xorps   xmm1, xmm1
0x180051a02  mov     [rbp+4Fh+var_50], rdi
0x180051a06  lea     rcx, [rbp+4Fh+var_78]
0x180051a0a  movdqu  xmmword ptr [rbp+4Fh+var_78], xmm0
0x180051a0f  movdqu  xmmword ptr [rbp+4Fh+var_60], xmm1
0x180051a14  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180051a19  lea     rcx, [rbp+4Fh+var_60]
0x180051a1d  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180051a22  mov     rdx, [rbp+4Fh+var_78+8]
0x180051a26  lea     r8, aTryingToCallEs_0; "Trying to call ESimSettingApi without a"...
0x180051a2d  mov     rcx, [rbp+4Fh+var_78]; unsigned __int16 *
0x180051a31  sub     rdx, rcx
0x180051a34  sar     rdx, 1; unsigned __int64
0x180051a37  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180051a3c  mov     rdx, [rbp+4Fh+var_60+8]
0x180051a40  lea     r9, aCesimsettingap_8; "CESimSettingApi::ConfirmInstallProfile"
0x180051a47  mov     rcx, [rbp+4Fh+var_60]; unsigned __int16 *
0x180051a4b  lea     r8, aSDS; "%S(%d):%s"
0x180051a52  mov     rax, [rbp+4Fh+var_78]
0x180051a56  sub     rdx, rcx
0x180051a59  mov     [rsp+0C0h+var_98], rax
0x180051a5e  sar     rdx, 1; unsigned __int64
0x180051a61  mov     [rsp+0C0h+var_A0], 0D1h
0x180051a69  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180051a6e  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180051a73  mov     ecx, [rax]
0x180051a75  cmp     ecx, 2
0x180051a78  jbe     loc_180051B3A
0x180051a7e  lea     rdx, word_180079EFA
0x180051a85  jmp     loc_180051B21
0x180051a8a  lea     r14, [rsi+40h]
0x180051a8e  cmp     di, [r14]
0x180051a92  jnz     loc_180051B64
0x180051a98  xorps   xmm0, xmm0
0x180051a9b  mov     [rbp+4Fh+var_68], rdi
0x180051a9f  xorps   xmm1, xmm1
0x180051aa2  mov     [rbp+4Fh+var_50], rdi
0x180051aa6  lea     rcx, [rbp+4Fh+var_78]
0x180051aaa  movdqu  xmmword ptr [rbp+4Fh+var_78], xmm0
0x180051aaf  movdqu  xmmword ptr [rbp+4Fh+var_60], xmm1
0x180051ab4  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180051ab9  lea     rcx, [rbp+4Fh+var_60]
0x180051abd  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180051ac2  mov     rdx, [rbp+4Fh+var_78+8]
0x180051ac6  lea     r8, aTryingToCallEs; "Trying to call ESimSettingApi without a"...
0x180051acd  mov     rcx, [rbp+4Fh+var_78]; unsigned __int16 *
0x180051ad1  sub     rdx, rcx
0x180051ad4  sar     rdx, 1; unsigned __int64
0x180051ad7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180051adc  mov     rdx, [rbp+4Fh+var_60+8]
0x180051ae0  lea     r9, aCesimsettingap_8; "CESimSettingApi::ConfirmInstallProfile"
0x180051ae7  mov     rcx, [rbp+4Fh+var_60]; unsigned __int16 *
0x180051aeb  lea     r8, aSDS; "%S(%d):%s"
0x180051af2  mov     rax, [rbp+4Fh+var_78]
0x180051af6  sub     rdx, rcx
0x180051af9  mov     [rsp+0C0h+var_98], rax
0x180051afe  sar     rdx, 1; unsigned __int64
0x180051b01  mov     [rsp+0C0h+var_A0], 0D1h
0x180051b09  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180051b0e  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180051b13  mov     ecx, [rax]
0x180051b15  cmp     ecx, 2
0x180051b18  jbe     short loc_180051B3A
0x180051b1a  lea     rdx, word_180079EB6
0x180051b21  mov     rcx, [rbp+4Fh+var_60]
0x180051b25  mov     [rbp+4Fh+var_80], rcx
0x180051b29  lea     rcx, [rbp+4Fh+var_80]
0x180051b2d  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x180051b32  mov     rcx, rax
0x180051b35  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180051b3a  lea     rcx, [rbp+4Fh+var_60]
0x180051b3e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180051b43  lea     rcx, [rbp+4Fh+var_78]
0x180051b47  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180051b4c  test    rbx, rbx
0x180051b4f  jz      short loc_180051B5A
0x180051b51  mov     rcx, rbx; SRWLock
0x180051b54  call    cs:__imp_ReleaseSRWLockExclusive
0x180051b5a  mov     eax, 80004005h
0x180051b5f  jmp     loc_180051D7F
0x180051b64  mov     edx, [rbp+4Fh+arg_20]
0x180051b67  lea     r8, [rbp+4Fh+arg_0]
0x180051b6b  mov     [rsp+0C0h+var_90], r8
0x180051b70  mov     eax, edi
0x180051b72  test    r15b, r15b
0x180051b75  mov     [rsp+0C0h+var_98], r12
0x180051b7a  mov     r9, r13
0x180051b7d  mov     [rbp+4Fh+arg_0], edi
0x180051b80  setz    al
0x180051b83  mov     r8, r14
0x180051b86  mov     [rsp+0C0h+var_A0], eax; int
0x180051b8a  call    cs:__imp_LuiInstallProfile
0x180051b90  mov     edi, eax
0x180051b92  test    eax, eax
0x180051b94  jns     short loc_180051BC3
0x180051b96  mov     rcx, [rbp+57h]; this
0x180051b9a  lea     r8, aOnecoreuapNetM_7; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180051ba1  mov     r9d, eax; char *
0x180051ba4  mov     edx, 0DCh; void *
0x180051ba9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051bae  test    rbx, rbx
0x180051bb1  jz      short loc_180051BBC
0x180051bb3  mov     rcx, rbx; SRWLock
0x180051bb6  call    cs:__imp_ReleaseSRWLockExclusive
0x180051bbc  mov     eax, edi
0x180051bbe  jmp     loc_180051D7F
0x180051bc3  lea     rcx, [rsi+0C0h]
0x180051bca  lea     rdx, [rbp+4Fh+arg_0]
0x180051bce  call    ??A?$map@KW4ESimSettingOperation@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKW4ESimSettingOperation@@@std@@@3@@std@@QEAAAEAW4ESimSettingOperation@@AEBK@Z; std::map<ulong,ESimSettingOperation>::operator[](ulong const &)
0x180051bd3  xorps   xmm0, xmm0
0x180051bd6  lea     rcx, [rbp+4Fh+var_78]
0x180051bda  xor     edi, edi
0x180051bdc  xorps   xmm1, xmm1
0x180051bdf  movdqu  xmmword ptr [rbp+4Fh+var_78], xmm0
0x180051be4  mov     dword ptr [rax], 6
0x180051bea  mov     eax, [rbp+4Fh+arg_0]
0x180051bed  mov     [rsi+0D8h], eax
0x180051bf3  mov     [rbp+4Fh+var_68], rdi
0x180051bf7  movdqu  xmmword ptr [rbp+4Fh+var_60], xmm1
0x180051bfc  mov     [rbp+4Fh+var_50], rdi
0x180051c00  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180051c05  lea     rcx, [rbp+4Fh+var_60]
0x180051c09  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180051c0e  mov     rdx, [rbp+4Fh+var_78+8]
0x180051c12  mov     r8d, edi
0x180051c15  mov     rcx, [rbp+4Fh+var_78]; unsigned __int16 *
0x180051c19  test    r15b, r15b
0x180051c1c  mov     eax, [rbp+4Fh+arg_0]
0x180051c1f  mov     r9, r14
0x180051c22  setnz   r8b
0x180051c26  mov     [rsp+0C0h+var_88], eax
0x180051c2a  mov     dword ptr [rsp+0C0h+var_90], r8d
0x180051c2f  sub     rdx, rcx
0x180051c32  sar     rdx, 1; unsigned __int64
0x180051c35  lea     r8, aConfirminstall; "ConfirmInstallProfile with eSim=%s, pro"...
0x180051c3c  mov     [rsp+0C0h+var_98], r12
0x180051c41  mov     qword ptr [rsp+0C0h+var_A0], r13
0x180051c46  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180051c4b  mov     rdx, [rbp+4Fh+var_60+8]
0x180051c4f  lea     r9, aCesimsettingap_8; "CESimSettingApi::ConfirmInstallProfile"
0x180051c56  mov     rcx, [rbp+4Fh+var_60]; unsigned __int16 *
0x180051c5a  lea     r8, aSDS; "%S(%d):%s"
0x180051c61  mov     rax, [rbp+4Fh+var_78]
0x180051c65  sub     rdx, rcx
0x180051c68  mov     [rsp+0C0h+var_98], rax
0x180051c6d  sar     rdx, 1; unsigned __int64
0x180051c70  mov     [rsp+0C0h+var_A0], 0E7h
0x180051c78  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180051c7d  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180051c82  mov     ecx, [rax]
0x180051c84  cmp     ecx, 4
0x180051c87  jbe     short loc_180051CA9
0x180051c89  mov     rcx, [rbp+4Fh+var_60]
0x180051c8d  lea     rdx, byte_180079E73
0x180051c94  mov     [rbp+4Fh+var_80], rcx
0x180051c98  lea     rcx, [rbp+4Fh+var_80]
0x180051c9c  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x180051ca1  mov     rcx, rax
0x180051ca4  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180051ca9  lea     rcx, [rbp+4Fh+var_60]
0x180051cad  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180051cb2  lea     rcx, [rbp+4Fh+var_78]
0x180051cb6  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180051cbb  xorps   xmm0, xmm0
0x180051cbe  mov     [rbp+4Fh+var_68], rdi
0x180051cc2  xorps   xmm1, xmm1
0x180051cc5  mov     [rbp+4Fh+var_50], rdi
0x180051cc9  lea     rcx, [rbp+4Fh+var_78]
0x180051ccd  movdqu  xmmword ptr [rbp+4Fh+var_78], xmm0
0x180051cd2  movdqu  xmmword ptr [rbp+4Fh+var_60], xmm1
0x180051cd7  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180051cdc  lea     rcx, [rbp+4Fh+var_60]
0x180051ce0  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180051ce5  mov     rdx, [rbp+4Fh+var_78+8]
0x180051ce9  lea     r8, aExit; "Exit"
0x180051cf0  mov     rcx, [rbp+4Fh+var_78]; unsigned __int16 *
0x180051cf4  sub     rdx, rcx
0x180051cf7  sar     rdx, 1; unsigned __int64
0x180051cfa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180051cff  mov     rdx, [rbp+4Fh+var_60+8]
0x180051d03  lea     r9, aCesimsettingap_8; "CESimSettingApi::ConfirmInstallProfile"
0x180051d0a  mov     rcx, [rbp+4Fh+var_60]; unsigned __int16 *
0x180051d0e  lea     r8, aSDS; "%S(%d):%s"
0x180051d15  mov     rax, [rbp+4Fh+var_78]
0x180051d19  sub     rdx, rcx
0x180051d1c  mov     [rsp+0C0h+var_98], rax
0x180051d21  sar     rdx, 1; unsigned __int64
0x180051d24  mov     [rsp+0C0h+var_A0], 0E9h
0x180051d2c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180051d31  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180051d36  mov     ecx, [rax]
0x180051d38  cmp     ecx, 5
0x180051d3b  jbe     short loc_180051D5D
0x180051d3d  mov     rcx, [rbp+4Fh+var_60]
0x180051d41  lea     rdx, byte_180079E93
0x180051d48  mov     [rbp+4Fh+var_80], rcx
0x180051d4c  lea     rcx, [rbp+4Fh+var_80]
0x180051d50  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x180051d55  mov     rcx, rax
0x180051d58  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180051d5d  lea     rcx, [rbp+4Fh+var_60]
0x180051d61  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180051d66  lea     rcx, [rbp+4Fh+var_78]
0x180051d6a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180051d6f  test    rbx, rbx
0x180051d72  jz      short loc_180051D7D
0x180051d74  mov     rcx, rbx; SRWLock
0x180051d77  call    cs:__imp_ReleaseSRWLockExclusive
0x180051d7d  xor     eax, eax
0x180051d7f  add     rsp, 88h
0x180051d86  pop     r15
0x180051d88  pop     r14
0x180051d8a  pop     r13
0x180051d8c  pop     r12
0x180051d8e  pop     rdi
0x180051d8f  pop     rsi
0x180051d90  pop     rbx
0x180051d91  pop     rbp
0x180051d92  retn
```
