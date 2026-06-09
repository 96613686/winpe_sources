# CWwanTranslator::StartListening(ICellularSettingEvents *)

- ea: `0x18003b004`
- end: `0x18003b4b5`
- name: `?StartListening@CWwanTranslator@@QEAAJPEAUICellularSettingEvents@@@Z`
- size: `1201`
- prototype: `__int64 __fastcall(CWwanTranslator *__hidden this, struct ICellularSettingEvents *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180017d70`

## callees

- `0x18000178c`
- `0x1800028b0`
- `0x1800028ec`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x1800174f0`
- `0x18001dd10`
- `0x18003b004`
- `0x1800458c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003b1ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003b1ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b0dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b0dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b1b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b1b8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18003b157`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18003b157`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b180`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b180`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b165`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b165`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanRegisterNotification` at `0x18003b268`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanRegisterNotification` at `0x18003b268`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003b340`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003b340`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18003b221`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18003b221`

## string_xrefs

- `0x18003b426`: `CWwanTranslator has already been started`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
int __fastcall CWwanTranslator::StartListening(RTL_SRWLOCK *this, struct ICellularSettingEvents *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  struct _RTL_CRITICAL_SECTION *v7; // r15
  PVOID Ptr; // rdi
  struct _RTL_CRITICAL_SECTION_DEBUG *v9; // rax
  _QWORD *v10; // rax
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  HANDLE EventW; // rax
  signed int v13; // ebx
  RTL_SRWLOCK *v15; // rdi
  unsigned int v16; // eax
  int v17; // eax
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  const struct _tlgProvider_t *v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  const struct _tlgProvider_t *v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  unsigned int v27[2]; // [rsp+20h] [rbp-50h]
  unsigned int v28[2]; // [rsp+20h] [rbp-50h]
  struct _RTL_CRITICAL_SECTION *v29; // [rsp+30h] [rbp-40h]
  unsigned __int16 *v30[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v31; // [rsp+48h] [rbp-28h]
  unsigned __int16 *v32[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v33; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v35; // [rsp+B0h] [rbp+40h] BYREF
  int v36; // [rsp+B8h] [rbp+48h] BYREF
  unsigned __int16 *v37; // [rsp+C0h] [rbp+50h] BYREF
  struct _RTL_CRITICAL_SECTION *v38; // [rsp+C8h] [rbp+58h]

  *(_OWORD *)v32 = 0;
  v33 = 0;
  *(_OWORD *)v30 = 0;
  v31 = 0;
  std::vector<unsigned short>::resize(v32);
  std::vector<unsigned short>::resize(v30);
  StringCchPrintfW(v32[0], v32[1] - v32[0], L"Enter");
  v27[0] = 289;
  StringCchPrintfW(v30[0], v30[1] - v30[0], L"%S(%d):%s", "CWwanTranslator::StartListening");
  v4 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    v37 = v30[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)&dword_18007867C,
      v5,
      v6,
      (const unsigned __int16 **)&v37);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v30);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v32);
  AcquireSRWLockExclusive(this + 19);
  v37 = (unsigned __int16 *)&this[19];
  this[4].Ptr = a2;
  v7 = (struct _RTL_CRITICAL_SECTION *)operator new(0x50u);
  v38 = v7;
  Ptr = this[4].Ptr;
  v7->DebugInfo = 0;
  *(_QWORD *)&v7->LockCount = 0;
  v9 = (struct _RTL_CRITICAL_SECTION_DEBUG *)operator new(0x48u);
  *(_QWORD *)&v9->Type = v9;
  v9->CriticalSection = (struct _RTL_CRITICAL_SECTION *)v9;
  v9->ProcessLocksList.Flink = (struct _LIST_ENTRY *)v9;
  LOWORD(v9->ProcessLocksList.Blink) = 257;
  v7->DebugInfo = v9;
  v7->OwningThread = 0;
  v7->LockSemaphore = 0;
  v10 = operator new(0x48u);
  *v10 = v10;
  v10[1] = v10;
  v10[2] = v10;
  *((_WORD *)v10 + 12) = 257;
  v7->OwningThread = v10;
  InitializeCriticalSectionEx(v7 + 1, 0, 0);
  v7->SpinCount = (ULONG_PTR)Ptr;
  EnterCriticalSection(v7 + 1);
  v29 = v7 + 1;
  SlotBindingMap::_RefreshSlotBinding((SlotBindingMap *)v7);
  if ( v7 != (struct _RTL_CRITICAL_SECTION *)-40LL )
    LeaveCriticalSection(v7 + 1);
  v11 = (struct _RTL_CRITICAL_SECTION *)this[17].Ptr;
  this[17].Ptr = v7;
  if ( v11 )
  {
    SlotBindingMap::~SlotBindingMap(v11);
    operator delete(v11);
  }
  if ( this != (RTL_SRWLOCK *)-152LL )
    ReleaseSRWLockExclusive(this + 19);
  EventW = CreateEventW(0, 1, 1, 0);
  this[18].Ptr = EventW;
  if ( !EventW )
  {
    v13 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
      (const char *)0x80004005LL,
      v27[0]);
    return v13;
  }
  v35 = 0;
  v36 = 0;
  v15 = this + 10;
  if ( this[10].Ptr )
  {
    *(_OWORD *)v30 = 0;
    v31 = 0;
    *(_OWORD *)v32 = 0;
    v33 = 0;
    std::vector<unsigned short>::resize(v30);
    std::vector<unsigned short>::resize(v32);
    StringCchPrintfW(v30[0], v30[1] - v30[0], L"CWwanTranslator has already been started");
    v27[0] = 310;
    StringCchPrintfW(
      v32[0],
      v32[1] - v32[0],
      L"%S(%d):%s",
      "CWwanTranslator::StartListening",
      *(_QWORD *)v27,
      v30[0],
      v29);
    v24 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v24 > 4u )
    {
      v37 = v32[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v24,
        (__int64)&byte_18007869F,
        v25,
        v26,
        (const unsigned __int16 **)&v37);
    }
  }
  else
  {
    v16 = WwanOpenHandle(1, 0, &v35, &this[10]);
    if ( v16 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x131,
               (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
               (const char *)v16,
               v27[0]);
    v17 = WwanRegisterNotification(v15->Ptr, 6, CWwanTranslator::s_ProcessWwanNotification, this, 0, &v36, v29);
    v13 = v17;
    if ( v17 > 0 )
      v13 = (unsigned __int16)v17 | 0x80070000;
    v31 = 0;
    *(_OWORD *)v30 = 0;
    if ( v13 < 0 )
    {
      *(_OWORD *)v32 = 0;
      v33 = 0;
      std::vector<unsigned short>::resize(v30);
      std::vector<unsigned short>::resize(v32);
      StringCchPrintfW(v30[0], v30[1] - v30[0], L"WwanRegisterNotification failed with hr=0x%08x.", (unsigned int)v13);
      v28[0] = 323;
      StringCchPrintfW(v32[0], v32[1] - v32[0], L"%S(%d):%s", "CWwanTranslator::StartListening", *(_QWORD *)v28, v30[0]);
      v18 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v18 > 2u )
      {
        v37 = v32[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v18,
          (__int64)byte_18007865B,
          v19,
          v20,
          (const unsigned __int16 **)&v37);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v32);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v30);
      WwanCloseHandle(v15->Ptr, 0);
      v15->Ptr = 0;
      return v13;
    }
    *(_OWORD *)v32 = 0;
    v33 = 0;
    std::vector<unsigned short>::resize(v30);
    std::vector<unsigned short>::resize(v32);
    StringCchPrintfW(v30[0], v30[1] - v30[0], L"Exit");
    v28[0] = 329;
    StringCchPrintfW(v32[0], v32[1] - v32[0], L"%S(%d):%s", "CWwanTranslator::StartListening", *(_QWORD *)v28, v30[0]);
    v21 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v21 > 5u )
    {
      v37 = v32[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v21,
        (__int64)byte_180078615,
        v22,
        v23,
        (const unsigned __int16 **)&v37);
    }
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v32);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v30);
  return 0;
}

```

## disassembly

```asm
0x18003b004  push    rbp
0x18003b006  push    rbx
0x18003b007  push    rsi
0x18003b008  push    rdi
0x18003b009  push    r13
0x18003b00b  push    r14
0x18003b00d  push    r15
0x18003b00f  mov     rbp, rsp
0x18003b012  sub     rsp, 70h
0x18003b016  mov     rbx, rdx
0x18003b019  mov     rsi, rcx
0x18003b01c  xorps   xmm0, xmm0
0x18003b01f  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18003b024  xor     r13d, r13d
0x18003b027  mov     [rbp+var_10], r13
0x18003b02b  movdqu  xmmword ptr [rbp+var_38], xmm0
0x18003b030  mov     [rbp+var_28], r13
0x18003b034  lea     rcx, [rbp+var_20]
0x18003b038  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b03d  lea     rcx, [rbp+var_38]
0x18003b041  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b046  mov     rdx, [rbp+var_20+8]
0x18003b04a  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x18003b04e  sub     rdx, rcx
0x18003b051  sar     rdx, 1; unsigned __int64
0x18003b054  lea     r8, aEnter; "Enter"
0x18003b05b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b060  mov     rdx, [rbp+var_38+8]
0x18003b064  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x18003b068  sub     rdx, rcx
0x18003b06b  sar     rdx, 1; unsigned __int64
0x18003b06e  mov     rax, [rbp+var_20]
0x18003b072  mov     [rsp+70h+var_48], rax
0x18003b077  mov     [rsp+70h+var_50], 121h
0x18003b07f  lea     r9, aCwwantranslato_8; "CWwanTranslator::StartListening"
0x18003b086  lea     r8, aSDS; "%S(%d):%s"
0x18003b08d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b092  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003b097  mov     ecx, [rax]
0x18003b099  cmp     ecx, 5
0x18003b09c  jbe     short loc_18003B0BF
0x18003b09e  mov     rcx, [rbp+var_38]
0x18003b0a2  mov     [rbp+arg_10], rcx
0x18003b0a6  lea     rcx, [rbp+arg_10]
0x18003b0aa  mov     qword ptr [rsp+70h+var_50], rcx; unsigned int
0x18003b0af  lea     rdx, dword_18007867C
0x18003b0b6  mov     rcx, rax
0x18003b0b9  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003b0be  nop
0x18003b0bf  lea     rcx, [rbp+var_38]
0x18003b0c3  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003b0c8  nop
0x18003b0c9  lea     rcx, [rbp+var_20]
0x18003b0cd  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003b0d2  lea     r14, [rsi+98h]
0x18003b0d9  mov     rcx, r14; SRWLock
0x18003b0dc  call    cs:__imp_AcquireSRWLockExclusive
0x18003b0e2  mov     [rbp+arg_10], r14
0x18003b0e6  mov     [rsi+20h], rbx
0x18003b0ea  mov     ecx, 50h ; 'P'; Size
0x18003b0ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b0f4  mov     r15, rax
0x18003b0f7  mov     [rbp+arg_18], rax
0x18003b0fb  mov     rdi, [rsi+20h]
0x18003b0ff  mov     [rax], r13
0x18003b102  mov     [rax+8], r13
0x18003b106  mov     ecx, 48h ; 'H'; Size
0x18003b10b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b110  mov     [rax], rax
0x18003b113  mov     [rax+8], rax
0x18003b117  mov     [rax+10h], rax
0x18003b11b  mov     word ptr [rax+18h], 101h
0x18003b121  mov     [r15], rax
0x18003b124  mov     [r15+10h], r13
0x18003b128  mov     [r15+18h], r13
0x18003b12c  mov     ecx, 48h ; 'H'; Size
0x18003b131  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b136  mov     [rax], rax
0x18003b139  mov     [rax+8], rax
0x18003b13d  mov     [rax+10h], rax
0x18003b141  mov     word ptr [rax+18h], 101h
0x18003b147  mov     [r15+10h], rax
0x18003b14b  lea     rbx, [r15+28h]
0x18003b14f  xor     r8d, r8d; Flags
0x18003b152  xor     edx, edx; dwSpinCount
0x18003b154  mov     rcx, rbx; lpCriticalSection
0x18003b157  call    cs:__imp_InitializeCriticalSectionEx
0x18003b15d  nop
0x18003b15e  mov     [r15+20h], rdi
0x18003b162  mov     rcx, rbx; lpCriticalSection
0x18003b165  call    cs:__imp_EnterCriticalSection
0x18003b16b  mov     [rbp+var_40], rbx
0x18003b16f  mov     rcx, r15; this
0x18003b172  call    ?_RefreshSlotBinding@SlotBindingMap@@AEAAJXZ; SlotBindingMap::_RefreshSlotBinding(void)
0x18003b177  nop
0x18003b178  test    rbx, rbx
0x18003b17b  jz      short loc_18003B187
0x18003b17d  mov     rcx, rbx; lpCriticalSection
0x18003b180  call    cs:__imp_LeaveCriticalSection
0x18003b186  nop
0x18003b187  mov     rbx, [rsi+88h]
0x18003b18e  mov     [rsi+88h], r15
0x18003b195  test    rbx, rbx
0x18003b198  jz      short loc_18003B1B0
0x18003b19a  mov     rcx, rbx; this
0x18003b19d  call    ??1SlotBindingMap@@QEAA@XZ; SlotBindingMap::~SlotBindingMap(void)
0x18003b1a2  mov     edx, 50h ; 'P'
0x18003b1a7  mov     rcx, rbx; Block
0x18003b1aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003b1af  nop
0x18003b1b0  test    r14, r14
0x18003b1b3  jz      short loc_18003B1BE
0x18003b1b5  mov     rcx, r14; SRWLock
0x18003b1b8  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b1be  xor     r9d, r9d; lpName
0x18003b1c1  lea     edx, [r9+1]; bManualReset
0x18003b1c5  xor     ecx, ecx; lpEventAttributes
0x18003b1c7  mov     r8d, edx; bInitialState
0x18003b1ca  call    cs:__imp_CreateEventW
0x18003b1d0  mov     [rsi+90h], rax
0x18003b1d7  test    rax, rax
0x18003b1da  jnz     short loc_18003B200
0x18003b1dc  mov     rcx, [rbp+38h]; this
0x18003b1e0  mov     ebx, 80004005h
0x18003b1e5  mov     r9d, ebx; char *
0x18003b1e8  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003b1ef  mov     edx, 12Bh; void *
0x18003b1f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b1f9  mov     eax, ebx
0x18003b1fb  jmp     loc_18003B4A6
0x18003b200  mov     [rbp+arg_0], r13d
0x18003b204  mov     [rbp+arg_8], r13d
0x18003b208  lea     rdi, [rsi+50h]
0x18003b20c  cmp     [rdi], r13
0x18003b20f  jnz     loc_18003B3F1
0x18003b215  mov     r9, rdi
0x18003b218  lea     r8, [rbp+arg_0]
0x18003b21c  xor     edx, edx
0x18003b21e  lea     ecx, [rdx+1]
0x18003b221  call    cs:__imp_WwanOpenHandle
0x18003b227  test    eax, eax
0x18003b229  jz      short loc_18003B248
0x18003b22b  mov     rcx, [rbp+38h]; this
0x18003b22f  mov     r9d, eax; char *
0x18003b232  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003b239  mov     edx, 131h; void *
0x18003b23e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003b243  jmp     loc_18003B4A6
0x18003b248  lea     rax, [rbp+arg_8]
0x18003b24c  mov     [rsp+70h+var_48], rax
0x18003b251  mov     qword ptr [rsp+70h+var_50], r13
0x18003b256  mov     r9, rsi
0x18003b259  lea     r8, ?s_ProcessWwanNotification@CWwanTranslator@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; CWwanTranslator::s_ProcessWwanNotification(_L2_NOTIFICATION_DATA *,void *)
0x18003b260  mov     edx, 6
0x18003b265  mov     rcx, [rdi]
0x18003b268  call    cs:__imp_WwanRegisterNotification
0x18003b26e  mov     ebx, eax
0x18003b270  test    eax, eax
0x18003b272  jle     short loc_18003B27D
0x18003b274  movzx   ebx, ax
0x18003b277  or      ebx, 80070000h
0x18003b27d  xorps   xmm0, xmm0
0x18003b280  mov     [rbp+var_28], r13
0x18003b284  movdqu  xmmword ptr [rbp+var_38], xmm0
0x18003b289  test    ebx, ebx
0x18003b28b  jns     loc_18003B34E
0x18003b291  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18003b296  mov     [rbp+var_10], r13
0x18003b29a  lea     rcx, [rbp+var_38]
0x18003b29e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b2a3  lea     rcx, [rbp+var_20]
0x18003b2a7  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b2ac  mov     rdx, [rbp+var_38+8]
0x18003b2b0  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x18003b2b4  sub     rdx, rcx
0x18003b2b7  sar     rdx, 1; unsigned __int64
0x18003b2ba  mov     r9d, ebx
0x18003b2bd  lea     r8, aWwanregisterno_0; "WwanRegisterNotification failed with hr"...
0x18003b2c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b2c9  mov     rdx, [rbp+var_20+8]
0x18003b2cd  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x18003b2d1  sub     rdx, rcx
0x18003b2d4  sar     rdx, 1; unsigned __int64
0x18003b2d7  mov     rax, [rbp+var_38]
0x18003b2db  mov     [rsp+70h+var_48], rax
0x18003b2e0  mov     [rsp+70h+var_50], 143h
0x18003b2e8  lea     r9, aCwwantranslato_8; "CWwanTranslator::StartListening"
0x18003b2ef  lea     r8, aSDS; "%S(%d):%s"
0x18003b2f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b2fb  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003b300  mov     ecx, [rax]
0x18003b302  cmp     ecx, 2
0x18003b305  jbe     short loc_18003B328
0x18003b307  mov     rcx, [rbp+var_20]
0x18003b30b  mov     [rbp+arg_10], rcx
0x18003b30f  lea     rcx, [rbp+arg_10]
0x18003b313  mov     qword ptr [rsp+70h+var_50], rcx
0x18003b318  lea     rdx, byte_18007865B
0x18003b31f  mov     rcx, rax
0x18003b322  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003b327  nop
0x18003b328  lea     rcx, [rbp+var_20]
0x18003b32c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003b331  nop
0x18003b332  lea     rcx, [rbp+var_38]
0x18003b336  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003b33b  xor     edx, edx
0x18003b33d  mov     rcx, [rdi]
0x18003b340  call    cs:__imp_WwanCloseHandle
0x18003b346  mov     [rdi], r13
0x18003b349  jmp     loc_18003B1F9
0x18003b34e  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18003b353  mov     [rbp+var_10], r13
0x18003b357  lea     rcx, [rbp+var_38]
0x18003b35b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b360  lea     rcx, [rbp+var_20]
0x18003b364  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b369  mov     rdx, [rbp+var_38+8]
0x18003b36d  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x18003b371  sub     rdx, rcx
0x18003b374  sar     rdx, 1; unsigned __int64
0x18003b377  lea     r8, aExit; "Exit"
0x18003b37e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b383  mov     rdx, [rbp+var_20+8]
0x18003b387  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x18003b38b  sub     rdx, rcx
0x18003b38e  sar     rdx, 1; unsigned __int64
0x18003b391  mov     rax, [rbp+var_38]
0x18003b395  mov     [rsp+70h+var_48], rax
0x18003b39a  mov     [rsp+70h+var_50], 149h
0x18003b3a2  lea     r9, aCwwantranslato_8; "CWwanTranslator::StartListening"
0x18003b3a9  lea     r8, aSDS; "%S(%d):%s"
0x18003b3b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b3b5  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003b3ba  mov     ecx, [rax]
0x18003b3bc  cmp     ecx, 5
0x18003b3bf  jbe     short loc_18003B3E2
0x18003b3c1  mov     rcx, [rbp+var_20]
0x18003b3c5  mov     [rbp+arg_10], rcx
0x18003b3c9  lea     rcx, [rbp+arg_10]
0x18003b3cd  mov     qword ptr [rsp+70h+var_50], rcx
0x18003b3d2  lea     rdx, byte_180078615
0x18003b3d9  mov     rcx, rax
0x18003b3dc  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003b3e1  nop
0x18003b3e2  lea     rcx, [rbp+var_20]
0x18003b3e6  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003b3eb  nop
0x18003b3ec  jmp     loc_18003B49B
0x18003b3f1  xorps   xmm0, xmm0
0x18003b3f4  movdqu  xmmword ptr [rbp+var_38], xmm0
0x18003b3f9  mov     [rbp+var_28], r13
0x18003b3fd  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18003b402  mov     [rbp+var_10], r13
0x18003b406  lea     rcx, [rbp+var_38]
0x18003b40a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b40f  lea     rcx, [rbp+var_20]
0x18003b413  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b418  mov     rdx, [rbp+var_38+8]
0x18003b41c  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x18003b420  sub     rdx, rcx
0x18003b423  sar     rdx, 1; unsigned __int64
0x18003b426  lea     r8, aCwwantranslato_56; "CWwanTranslator has already been starte"...
0x18003b42d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b432  mov     rdx, [rbp+var_20+8]
0x18003b436  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x18003b43a  sub     rdx, rcx
0x18003b43d  sar     rdx, 1; unsigned __int64
0x18003b440  mov     rax, [rbp+var_38]
0x18003b444  mov     [rsp+70h+var_48], rax
0x18003b449  mov     [rsp+70h+var_50], 136h
0x18003b451  lea     r9, aCwwantranslato_8; "CWwanTranslator::StartListening"
0x18003b458  lea     r8, aSDS; "%S(%d):%s"
0x18003b45f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b464  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003b469  mov     ecx, [rax]
0x18003b46b  cmp     ecx, 4
0x18003b46e  jbe     short loc_18003B491
0x18003b470  mov     rcx, [rbp+var_20]
0x18003b474  mov     [rbp+arg_10], rcx
0x18003b478  lea     rcx, [rbp+arg_10]
0x18003b47c  mov     qword ptr [rsp+70h+var_50], rcx
0x18003b481  lea     rdx, byte_18007869F
0x18003b488  mov     rcx, rax
0x18003b48b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003b490  nop
0x18003b491  lea     rcx, [rbp+var_20]
0x18003b495  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003b49a  nop
0x18003b49b  lea     rcx, [rbp+var_38]
0x18003b49f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003b4a4  xor     eax, eax
0x18003b4a6  add     rsp, 70h
0x18003b4aa  pop     r15
0x18003b4ac  pop     r14
0x18003b4ae  pop     r13
0x18003b4b0  pop     rdi
0x18003b4b1  pop     rsi
0x18003b4b2  pop     rbx
0x18003b4b3  pop     rbp
  ... truncated ...
```
