# CWwanTranslator::StopListening(void)

- ea: `0x18003b4bc`
- end: `0x18003b7cf`
- name: `?StopListening@CWwanTranslator@@QEAAJXZ`
- size: `787`
- prototype: `__int64 __fastcall(CWwanTranslator *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18001743c`
- `0x18001b2c0`

## callees

- `0x18000178c`
- `0x1800028b0`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800172bc`
- `0x1800174f0`
- `0x18001dd10`
- `0x18003b4bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b6ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003b6ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b6fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b6fc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanRegisterNotification` at `0x18003b66a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanRegisterNotification` at `0x18003b66a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003b697`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003b697`

## string_xrefs

- `0x18003b5cb`: `Listening has stopped already.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall CWwanTranslator::StopListening(RTL_SRWLOCK *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  PVOID Ptr; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // eax
  __int64 v10; // rdx
  struct _RTL_CRITICAL_SECTION *v12; // rsi
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+20h] [rbp-40h]
  unsigned int v17[2]; // [rsp+20h] [rbp-40h]
  unsigned int v18[2]; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v19[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v21[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v22; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v24; // [rsp+80h] [rbp+20h] BYREF
  unsigned __int16 *v25; // [rsp+88h] [rbp+28h] BYREF

  *(_OWORD *)v21 = 0;
  v22 = 0;
  *(_OWORD *)v19 = 0;
  v20 = 0;
  std::vector<unsigned short>::resize(v21);
  std::vector<unsigned short>::resize(v19);
  StringCchPrintfW(v21[0], v21[1] - v21[0], L"Enter");
  v16 = 335;
  StringCchPrintfW(v19[0], v19[1] - v19[0], L"%S(%d):%s", "CWwanTranslator::StopListening", v16, v21[0]);
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    v25 = v19[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)qword_180078638,
      v3,
      v4,
      (const unsigned __int16 **)&v25);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v19);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v21);
  Ptr = this[10].Ptr;
  if ( Ptr )
  {
    v24 = 0;
    v9 = WwanRegisterNotification(Ptr, 0, CWwanTranslator::s_ProcessWwanNotification, 0, 0, &v24, v19[0]);
    if ( v9 )
    {
      v10 = 345;
    }
    else
    {
      v9 = WwanCloseHandle(this[10].Ptr, 0);
      if ( !v9 )
      {
        this[10].Ptr = 0;
        AcquireSRWLockExclusive(this + 19);
        this[4].Ptr = 0;
        v12 = (struct _RTL_CRITICAL_SECTION *)this[17].Ptr;
        this[17].Ptr = 0;
        if ( v12 )
        {
          SlotBindingMap::~SlotBindingMap(v12);
          operator delete(v12);
        }
        if ( this != (RTL_SRWLOCK *)-152LL )
          ReleaseSRWLockExclusive(this + 19);
        *(_OWORD *)v19 = 0;
        v20 = 0;
        *(_OWORD *)v21 = 0;
        v22 = 0;
        std::vector<unsigned short>::resize(v19);
        std::vector<unsigned short>::resize(v21);
        StringCchPrintfW(v19[0], v19[1] - v19[0], L"Exit");
        v18[0] = 356;
        StringCchPrintfW(
          v21[0],
          v21[1] - v21[0],
          L"%S(%d):%s",
          "CWwanTranslator::StopListening",
          *(_QWORD *)v18,
          v19[0]);
        v13 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v13 > 5u )
        {
          v25 = v21[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v13,
            (__int64)word_1800785F2,
            v14,
            v15,
            (const unsigned __int16 **)&v25);
        }
        goto LABEL_18;
      }
      v10 = 347;
    }
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v10,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
             (const char *)v9,
             v18[0]);
  }
  *(_OWORD *)v19 = 0;
  v20 = 0;
  *(_OWORD *)v21 = 0;
  v22 = 0;
  std::vector<unsigned short>::resize(v19);
  std::vector<unsigned short>::resize(v21);
  StringCchPrintfW(v19[0], v19[1] - v19[0], L"Listening has stopped already.");
  v17[0] = 339;
  StringCchPrintfW(v21[0], v21[1] - v21[0], L"%S(%d):%s", "CWwanTranslator::StopListening", *(_QWORD *)v17, v19[0]);
  v6 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v6 > 4u )
  {
    v25 = v21[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)word_1800785D2,
      v7,
      v8,
      (const unsigned __int16 **)&v25);
  }
LABEL_18:
  std::vector<unsigned short>::~vector<unsigned short>((char **)v21);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v19);
  return 0;
}

```

## disassembly

```asm
0x18003b4bc  mov     [rsp-18h+arg_10], rbx
0x18003b4c1  push    rbp
0x18003b4c2  push    rsi
0x18003b4c3  push    rdi
0x18003b4c4  mov     rbp, rsp
0x18003b4c7  sub     rsp, 60h
0x18003b4cb  mov     rbx, rcx
0x18003b4ce  xorps   xmm0, xmm0
0x18003b4d1  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18003b4d6  mov     [rbp+var_8], 0
0x18003b4de  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18003b4e3  mov     [rbp+var_20], 0
0x18003b4eb  lea     rcx, [rbp+var_18]
0x18003b4ef  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b4f4  lea     rcx, [rbp+var_30]
0x18003b4f8  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b4fd  mov     rdx, [rbp+var_18+8]
0x18003b501  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18003b505  sub     rdx, rcx
0x18003b508  sar     rdx, 1; unsigned __int64
0x18003b50b  lea     r8, aEnter; "Enter"
0x18003b512  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b517  mov     rdx, [rbp+var_30+8]
0x18003b51b  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18003b51f  sub     rdx, rcx
0x18003b522  sar     rdx, 1; unsigned __int64
0x18003b525  mov     rax, [rbp+var_18]
0x18003b529  mov     [rsp+60h+var_38], rax
0x18003b52e  mov     [rsp+60h+var_40], 14Fh
0x18003b536  lea     r9, aCwwantranslato_0; "CWwanTranslator::StopListening"
0x18003b53d  lea     r8, aSDS; "%S(%d):%s"
0x18003b544  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b549  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003b54e  mov     ecx, [rax]
0x18003b550  cmp     ecx, 5
0x18003b553  jbe     short loc_18003B576
0x18003b555  mov     rcx, [rbp+var_30]
0x18003b559  mov     [rbp+arg_8], rcx
0x18003b55d  lea     rcx, [rbp+arg_8]
0x18003b561  mov     qword ptr [rsp+60h+var_40], rcx
0x18003b566  lea     rdx, qword_180078638
0x18003b56d  mov     rcx, rax
0x18003b570  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003b575  nop
0x18003b576  lea     rcx, [rbp+var_30]
0x18003b57a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003b57f  nop
0x18003b580  lea     rcx, [rbp+var_18]
0x18003b584  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003b589  mov     rcx, [rbx+50h]
0x18003b58d  test    rcx, rcx
0x18003b590  jnz     loc_18003B645
0x18003b596  xorps   xmm0, xmm0
0x18003b599  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18003b59e  mov     [rbp+var_20], rcx
0x18003b5a2  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18003b5a7  mov     [rbp+var_8], rcx
0x18003b5ab  lea     rcx, [rbp+var_30]
0x18003b5af  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b5b4  lea     rcx, [rbp+var_18]
0x18003b5b8  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b5bd  mov     rdx, [rbp+var_30+8]
0x18003b5c1  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18003b5c5  sub     rdx, rcx
0x18003b5c8  sar     rdx, 1; unsigned __int64
0x18003b5cb  lea     r8, aListeningHasSt; "Listening has stopped already."
0x18003b5d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b5d7  mov     rdx, [rbp+var_18+8]
0x18003b5db  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18003b5df  sub     rdx, rcx
0x18003b5e2  sar     rdx, 1; unsigned __int64
0x18003b5e5  mov     rax, [rbp+var_30]
0x18003b5e9  mov     [rsp+60h+var_38], rax
0x18003b5ee  mov     [rsp+60h+var_40], 153h
0x18003b5f6  lea     r9, aCwwantranslato_0; "CWwanTranslator::StopListening"
0x18003b5fd  lea     r8, aSDS; "%S(%d):%s"
0x18003b604  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b609  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003b60e  mov     ecx, [rax]
0x18003b610  cmp     ecx, 4
0x18003b613  jbe     short loc_18003B636
0x18003b615  mov     rcx, [rbp+var_18]
0x18003b619  mov     [rbp+arg_8], rcx
0x18003b61d  lea     rcx, [rbp+arg_8]
0x18003b621  mov     qword ptr [rsp+60h+var_40], rcx
0x18003b626  lea     rdx, word_1800785D2
0x18003b62d  mov     rcx, rax
0x18003b630  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003b635  nop
0x18003b636  lea     rcx, [rbp+var_18]
0x18003b63a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003b63f  nop
0x18003b640  jmp     loc_18003B7B4
0x18003b645  mov     [rbp+arg_0], 0
0x18003b64c  lea     rax, [rbp+arg_0]
0x18003b650  mov     [rsp+60h+var_38], rax
0x18003b655  mov     qword ptr [rsp+60h+var_40], 0; unsigned int
0x18003b65e  xor     r9d, r9d
0x18003b661  lea     r8, ?s_ProcessWwanNotification@CWwanTranslator@@CAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; CWwanTranslator::s_ProcessWwanNotification(_L2_NOTIFICATION_DATA *,void *)
0x18003b668  xor     edx, edx
0x18003b66a  call    cs:__imp_WwanRegisterNotification
0x18003b670  test    eax, eax
0x18003b672  jz      short loc_18003B691
0x18003b674  mov     edx, 159h; void *
0x18003b679  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003b680  mov     r9d, eax; char *
0x18003b683  mov     rcx, [rbp+18h]; this
0x18003b687  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003b68c  jmp     loc_18003B7BF
0x18003b691  xor     edx, edx
0x18003b693  mov     rcx, [rbx+50h]
0x18003b697  call    cs:__imp_WwanCloseHandle
0x18003b69d  test    eax, eax
0x18003b69f  jz      short loc_18003B6A8
0x18003b6a1  mov     edx, 15Bh
0x18003b6a6  jmp     short loc_18003B679
0x18003b6a8  mov     qword ptr [rbx+50h], 0
0x18003b6b0  lea     rdi, [rbx+98h]
0x18003b6b7  mov     rcx, rdi; SRWLock
0x18003b6ba  call    cs:__imp_AcquireSRWLockExclusive
0x18003b6c0  mov     qword ptr [rbx+20h], 0
0x18003b6c8  mov     rsi, [rbx+88h]
0x18003b6cf  mov     qword ptr [rbx+88h], 0
0x18003b6da  test    rsi, rsi
0x18003b6dd  jz      short loc_18003B6F4
0x18003b6df  mov     rcx, rsi; this
0x18003b6e2  call    ??1SlotBindingMap@@QEAA@XZ; SlotBindingMap::~SlotBindingMap(void)
0x18003b6e7  mov     edx, 50h ; 'P'
0x18003b6ec  mov     rcx, rsi; Block
0x18003b6ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003b6f4  test    rdi, rdi
0x18003b6f7  jz      short loc_18003B702
0x18003b6f9  mov     rcx, rdi; SRWLock
0x18003b6fc  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b702  xorps   xmm0, xmm0
0x18003b705  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18003b70a  mov     [rbp+var_20], 0
0x18003b712  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18003b717  mov     [rbp+var_8], 0
0x18003b71f  lea     rcx, [rbp+var_30]
0x18003b723  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b728  lea     rcx, [rbp+var_18]
0x18003b72c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003b731  mov     rdx, [rbp+var_30+8]
0x18003b735  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18003b739  sub     rdx, rcx
0x18003b73c  sar     rdx, 1; unsigned __int64
0x18003b73f  lea     r8, aExit; "Exit"
0x18003b746  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b74b  mov     rdx, [rbp+var_18+8]
0x18003b74f  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18003b753  sub     rdx, rcx
0x18003b756  sar     rdx, 1; unsigned __int64
0x18003b759  mov     rax, [rbp+var_30]
0x18003b75d  mov     [rsp+60h+var_38], rax
0x18003b762  mov     [rsp+60h+var_40], 164h
0x18003b76a  lea     r9, aCwwantranslato_0; "CWwanTranslator::StopListening"
0x18003b771  lea     r8, aSDS; "%S(%d):%s"
0x18003b778  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b77d  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003b782  mov     ecx, [rax]
0x18003b784  cmp     ecx, 5
0x18003b787  jbe     short loc_18003B7AA
0x18003b789  mov     rcx, [rbp+var_18]
0x18003b78d  mov     [rbp+arg_8], rcx
0x18003b791  lea     rcx, [rbp+arg_8]
0x18003b795  mov     qword ptr [rsp+60h+var_40], rcx
0x18003b79a  lea     rdx, word_1800785F2
0x18003b7a1  mov     rcx, rax
0x18003b7a4  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003b7a9  nop
0x18003b7aa  lea     rcx, [rbp+var_18]
0x18003b7ae  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003b7b3  nop
0x18003b7b4  lea     rcx, [rbp+var_30]
0x18003b7b8  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003b7bd  xor     eax, eax
0x18003b7bf  mov     rbx, [rsp+60h+arg_10]
0x18003b7c7  add     rsp, 60h
0x18003b7cb  pop     rdi
0x18003b7cc  pop     rsi
0x18003b7cd  pop     rbp
0x18003b7ce  retn
```
