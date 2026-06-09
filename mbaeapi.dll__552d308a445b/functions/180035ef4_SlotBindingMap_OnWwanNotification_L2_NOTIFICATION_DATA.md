# SlotBindingMap::OnWwanNotification(_L2_NOTIFICATION_DATA *)

- ea: `0x180035ef4`
- end: `0x18003642f`
- name: `?OnWwanNotification@SlotBindingMap@@QEAAJPEAU_L2_NOTIFICATION_DATA@@@Z`
- size: `1339`
- prototype: `__int64 __fastcall(SlotBindingMap *__hidden this, struct _L2_NOTIFICATION_DATA *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003812c`

## callees

- `0x18000178c`
- `0x1800018cc`
- `0x1800040cd`
- `0x180009ffc`
- `0x18001105c`
- `0x1800172bc`
- `0x18001dd10`
- `0x180033184`
- `0x180035ef4`
- `0x1800458c4`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036291`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003640b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036291`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003640b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800360f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800360f0`

## string_xrefs

- `0x180036167`: `Adapter-slot cache becomes out-of-date!`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SlotBindingMap::OnWwanNotification(
        struct _RTL_CRITICAL_SECTION *this,
        struct _L2_NOTIFICATION_DATA *a2)
{
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  _DWORD *pData; // r15
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  GUID *p_InterfaceGuid; // r14
  __int64 v16; // rbx
  const struct _tlgProvider_t *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // r8d
  __int64 *SpinCount; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  const struct _tlgProvider_t *v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  const struct _tlgProvider_t *v27; // rax
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // [rsp+20h] [rbp-40h]
  __int64 v31; // [rsp+20h] [rbp-40h]
  __int64 v32; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v33[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v34; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v35[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v36; // [rsp+58h] [rbp-8h]
  unsigned __int16 *v37; // [rsp+98h] [rbp+38h] BYREF
  GUID *v38; // [rsp+A0h] [rbp+40h] BYREF

  if ( a2->NotificationCode != 67 )
    return 0;
  *(_OWORD *)v35 = 0;
  v36 = 0;
  *(_OWORD *)v33 = 0;
  v34 = 0;
  std::vector<unsigned short>::resize(v35);
  std::vector<unsigned short>::resize(v33);
  StringCchPrintfW(v35[0], v35[1] - v35[0], L"Enter");
  v30 = 101;
  StringCchPrintfW(v33[0], v33[1] - v33[0], L"%S(%d):%s", "SlotBindingMap::OnWwanNotification", v30, v35[0]);
  v5 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v5 > 5u )
  {
    v37 = v33[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v5,
      (__int64)byte_180078915,
      v6,
      v7,
      (const unsigned __int16 **)&v37);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v33);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v35);
  if ( a2->dwDataSize == 16 )
  {
    pData = a2->pData;
    v12 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v12 <= 4u )
    {
      p_InterfaceGuid = &a2->InterfaceGuid;
    }
    else
    {
      LODWORD(v37) = *pData;
      p_InterfaceGuid = &a2->InterfaceGuid;
      v38 = &a2->InterfaceGuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        (__int64)v12,
        (__int64)word_1800788AA,
        v13,
        v14,
        &v38,
        (__int64)&v37);
    }
    EnterCriticalSection(this + 1);
    v38 = (GUID *)&this[1];
    std::_Tree<std::_Tmap_traits<_GUID,SlotBindingMap::AdapterParameters,GUID_COMP,std::allocator<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>,0>>::_Find_lower_bound<_GUID>(
      (__int64)this,
      v35,
      p_InterfaceGuid);
    v16 = v36;
    if ( !*(_BYTE *)(v36 + 25)
      && memcmp_0(p_InterfaceGuid, (const void *)(v36 + 28), 0x10u) >= 0
      && (PRTL_CRITICAL_SECTION_DEBUG)v16 != this->DebugInfo )
    {
      goto LABEL_20;
    }
    *(_OWORD *)v33 = 0;
    v34 = 0;
    *(_OWORD *)v35 = 0;
    v36 = 0;
    std::vector<unsigned short>::resize(v33);
    std::vector<unsigned short>::resize(v35);
    StringCchPrintfW(v33[0], v33[1] - v33[0], L"Adapter-slot cache becomes out-of-date!");
    LODWORD(v31) = 126;
    StringCchPrintfW(v35[0], v35[1] - v35[0], L"%S(%d):%s", "SlotBindingMap::OnWwanNotification", v31, v33[0]);
    v17 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v17 > 3u )
    {
      v37 = v35[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v17,
        (__int64)word_1800788F2,
        v18,
        v19,
        (const unsigned __int16 **)&v37);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v35);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v33);
    SlotBindingMap::_RefreshSlotBinding((SlotBindingMap *)this);
    std::_Tree<std::_Tmap_traits<_GUID,SlotBindingMap::AdapterParameters,GUID_COMP,std::allocator<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>,0>>::_Find_lower_bound<_GUID>(
      (__int64)this,
      v35,
      p_InterfaceGuid);
    v16 = v36;
    if ( !*(_BYTE *)(v36 + 25)
      && memcmp_0(p_InterfaceGuid, (const void *)(v36 + 28), 0x10u) >= 0
      && (PRTL_CRITICAL_SECTION_DEBUG)v16 != this->DebugInfo )
    {
LABEL_20:
      v20 = *pData;
      if ( *(_DWORD *)(v16 + 64) != *pData )
      {
        *(_DWORD *)(v16 + 64) = v20;
        SpinCount = (__int64 *)this->SpinCount;
        v22 = *SpinCount;
        v23 = v16 + 28;
        if ( v20 == -1 )
        {
          (*(void (__fastcall **)(__int64 *, __int64, __int64))(v22 + 232))(SpinCount, v23, 3);
          (*(void (__fastcall **)(ULONG_PTR, __int64, const unsigned __int16 *))(*(_QWORD *)this->SpinCount + 96LL))(
            this->SpinCount,
            v16 + 28,
            &dword_1800684AC);
        }
        else
        {
          (*(void (__fastcall **)(__int64 *, __int64))(v22 + 288))(SpinCount, v23);
        }
      }
      if ( this != (struct _RTL_CRITICAL_SECTION *)-40LL )
        LeaveCriticalSection(this + 1);
      *(_OWORD *)v33 = 0;
      v34 = 0;
      *(_OWORD *)v35 = 0;
      v36 = 0;
      std::vector<unsigned short>::resize(v33);
      std::vector<unsigned short>::resize(v35);
      StringCchPrintfW(v33[0], v33[1] - v33[0], L"Exit");
      LODWORD(v31) = 155;
      StringCchPrintfW(v35[0], v35[1] - v35[0], L"%S(%d):%s", "SlotBindingMap::OnWwanNotification", v31, v33[0]);
      v24 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v24 > 5u )
      {
        v37 = v35[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v24,
          (__int64)byte_180078843,
          v25,
          v26,
          (const unsigned __int16 **)&v37);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v35);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v33);
      return 0;
    }
    *(_OWORD *)v33 = 0;
    v34 = 0;
    *(_OWORD *)v35 = 0;
    v36 = 0;
    std::vector<unsigned short>::resize(v33);
    std::vector<unsigned short>::resize(v35);
    StringCchPrintfW(v33[0], v33[1] - v33[0], L"Got notification with an adapter ID which is not enumeratable!");
    LODWORD(v31) = 131;
    StringCchPrintfW(v35[0], v35[1] - v35[0], L"%S(%d):%s", "SlotBindingMap::OnWwanNotification", v31, v33[0]);
    v27 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v27 > 2u )
    {
      v37 = v35[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v27,
        (__int64)byte_180078889,
        v28,
        v29,
        (const unsigned __int16 **)&v37);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v35);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v33);
    if ( this != (struct _RTL_CRITICAL_SECTION *)-40LL )
      LeaveCriticalSection(this + 1);
  }
  else
  {
    *(_OWORD *)v33 = 0;
    v34 = 0;
    *(_OWORD *)v35 = 0;
    v36 = 0;
    std::vector<unsigned short>::resize(v33);
    std::vector<unsigned short>::resize(v35);
    LODWORD(v31) = 16;
    StringCchPrintfW(
      v33[0],
      v33[1] - v33[0],
      L"Got notification with bad sizes. Size: %d, expected: %d.",
      a2->dwDataSize,
      v31);
    LODWORD(v32) = 108;
    StringCchPrintfW(v35[0], v35[1] - v35[0], L"%S(%d):%s", "SlotBindingMap::OnWwanNotification", v32, v33[0]);
    v8 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v8 > 2u )
    {
      v37 = v35[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v8,
        (__int64)qword_180078938,
        v9,
        v10,
        (const unsigned __int16 **)&v37);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v35);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v33);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180035ef4  mov     [rsp-28h+arg_0], rbx
0x180035ef9  mov     [rsp-28h+arg_18], rsi
0x180035efe  push    rbp
0x180035eff  push    rdi
0x180035f00  push    r12
0x180035f02  push    r14
0x180035f04  push    r15
0x180035f06  mov     rbp, rsp
0x180035f09  sub     rsp, 60h
0x180035f0d  mov     rbx, rdx
0x180035f10  mov     rdi, rcx
0x180035f13  cmp     dword ptr [rdx+4], 43h ; 'C'
0x180035f17  jz      short loc_180035F20
0x180035f19  xor     eax, eax
0x180035f1b  jmp     loc_180036416
0x180035f20  xorps   xmm0, xmm0
0x180035f23  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180035f28  xor     r12d, r12d
0x180035f2b  mov     [rbp+var_8], r12
0x180035f2f  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180035f34  mov     [rbp+var_20], r12
0x180035f38  lea     rcx, [rbp+var_18]
0x180035f3c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180035f41  lea     rcx, [rbp+var_30]
0x180035f45  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180035f4a  mov     rdx, [rbp+var_18+8]
0x180035f4e  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180035f52  sub     rdx, rcx
0x180035f55  sar     rdx, 1; unsigned __int64
0x180035f58  lea     r8, aEnter; "Enter"
0x180035f5f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035f64  mov     rdx, [rbp+var_30+8]
0x180035f68  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180035f6c  sub     rdx, rcx
0x180035f6f  sar     rdx, 1; unsigned __int64
0x180035f72  mov     rax, [rbp+var_18]
0x180035f76  mov     [rsp+60h+var_38], rax
0x180035f7b  mov     dword ptr [rsp+60h+var_40], 65h ; 'e'
0x180035f83  lea     r9, aSlotbindingmap_0; "SlotBindingMap::OnWwanNotification"
0x180035f8a  lea     r8, aSDS; "%S(%d):%s"
0x180035f91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035f96  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180035f9b  mov     ecx, [rax]
0x180035f9d  cmp     ecx, 5
0x180035fa0  jbe     short loc_180035FC3
0x180035fa2  mov     rcx, [rbp+var_30]
0x180035fa6  mov     [rbp+arg_8], rcx
0x180035faa  lea     rcx, [rbp+arg_8]
0x180035fae  mov     [rsp+60h+var_40], rcx
0x180035fb3  lea     rdx, byte_180078915
0x180035fba  mov     rcx, rax
0x180035fbd  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180035fc2  nop
0x180035fc3  lea     rcx, [rbp+var_30]
0x180035fc7  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180035fcc  nop
0x180035fcd  lea     rcx, [rbp+var_18]
0x180035fd1  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180035fd6  cmp     dword ptr [rbx+18h], 10h
0x180035fda  jz      loc_1800360A4
0x180035fe0  xorps   xmm0, xmm0
0x180035fe3  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180035fe8  mov     [rbp+var_20], r12
0x180035fec  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180035ff1  mov     [rbp+var_8], r12
0x180035ff5  lea     rcx, [rbp+var_30]
0x180035ff9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180035ffe  lea     rcx, [rbp+var_18]
0x180036002  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180036007  mov     rdx, [rbp+var_30+8]
0x18003600b  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18003600f  sub     rdx, rcx
0x180036012  sar     rdx, 1; unsigned __int64
0x180036015  mov     dword ptr [rsp+60h+var_40], 10h
0x18003601d  mov     r9d, [rbx+18h]
0x180036021  lea     r8, aGotNotificatio_0; "Got notification with bad sizes. Size: "...
0x180036028  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003602d  mov     rdx, [rbp+var_18+8]
0x180036031  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180036035  sub     rdx, rcx
0x180036038  sar     rdx, 1; unsigned __int64
0x18003603b  mov     rax, [rbp+var_30]
0x18003603f  mov     [rsp+60h+var_38], rax
0x180036044  mov     dword ptr [rsp+60h+var_40], 6Ch ; 'l'
0x18003604c  lea     r9, aSlotbindingmap_0; "SlotBindingMap::OnWwanNotification"
0x180036053  lea     r8, aSDS; "%S(%d):%s"
0x18003605a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003605f  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180036064  mov     ecx, [rax]
0x180036066  cmp     ecx, 2
0x180036069  jbe     short loc_18003608C
0x18003606b  mov     rcx, [rbp+var_18]
0x18003606f  mov     [rbp+arg_8], rcx
0x180036073  lea     rcx, [rbp+arg_8]
0x180036077  mov     [rsp+60h+var_40], rcx
0x18003607c  lea     rdx, qword_180078938
0x180036083  mov     rcx, rax
0x180036086  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003608b  nop
0x18003608c  lea     rcx, [rbp+var_18]
0x180036090  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180036095  nop
0x180036096  lea     rcx, [rbp+var_30]
0x18003609a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003609f  jmp     loc_180036411
0x1800360a4  mov     r15, [rbx+20h]
0x1800360a8  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800360ad  mov     ecx, [rax]
0x1800360af  cmp     ecx, 4
0x1800360b2  jbe     short loc_1800360E5
0x1800360b4  mov     ecx, [r15]
0x1800360b7  mov     dword ptr [rbp+arg_8], ecx
0x1800360ba  lea     r14, [rbx+8]
0x1800360be  mov     [rbp+arg_10], r14
0x1800360c2  lea     rcx, [rbp+arg_8]
0x1800360c6  mov     [rsp+60h+var_38], rcx
0x1800360cb  lea     rcx, [rbp+arg_10]
0x1800360cf  mov     [rsp+60h+var_40], rcx
0x1800360d4  lea     rdx, word_1800788AA
0x1800360db  mov     rcx, rax
0x1800360de  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800360e3  jmp     short loc_1800360E9
0x1800360e5  lea     r14, [rbx+8]
0x1800360e9  lea     rsi, [rdi+28h]
0x1800360ed  mov     rcx, rsi; lpCriticalSection
0x1800360f0  call    cs:__imp_EnterCriticalSection
0x1800360f6  mov     [rbp+arg_10], rsi
0x1800360fa  mov     r8, r14
0x1800360fd  lea     rdx, [rbp+var_18]
0x180036101  mov     rcx, rdi
0x180036104  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UAdapterParameters@SlotBindingMap@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,SlotBindingMap::AdapterParameters,GUID_COMP,std::allocator<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x180036109  mov     rbx, [rbp+var_8]
0x18003610d  cmp     [rbx+19h], r12b
0x180036111  jnz     short loc_180036132
0x180036113  lea     rdx, [rbx+1Ch]; Buf2
0x180036117  mov     r8d, 10h; Size
0x18003611d  mov     rcx, r14; Buf1
0x180036120  call    memcmp_0
0x180036125  test    eax, eax
0x180036127  js      short loc_180036132
0x180036129  cmp     rbx, [rdi]
0x18003612c  jnz     loc_18003622D
0x180036132  xorps   xmm0, xmm0
0x180036135  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18003613a  mov     [rbp+var_20], r12
0x18003613e  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180036143  mov     [rbp+var_8], r12
0x180036147  lea     rcx, [rbp+var_30]
0x18003614b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180036150  lea     rcx, [rbp+var_18]
0x180036154  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180036159  mov     rdx, [rbp+var_30+8]
0x18003615d  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180036161  sub     rdx, rcx
0x180036164  sar     rdx, 1; unsigned __int64
0x180036167  lea     r8, aAdapterSlotCac; "Adapter-slot cache becomes out-of-date!"
0x18003616e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036173  mov     rdx, [rbp+var_18+8]
0x180036177  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18003617b  sub     rdx, rcx
0x18003617e  sar     rdx, 1; unsigned __int64
0x180036181  mov     rax, [rbp+var_30]
0x180036185  mov     [rsp+60h+var_38], rax
0x18003618a  mov     dword ptr [rsp+60h+var_40], 7Eh ; '~'
0x180036192  lea     r9, aSlotbindingmap_0; "SlotBindingMap::OnWwanNotification"
0x180036199  lea     r8, aSDS; "%S(%d):%s"
0x1800361a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800361a5  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800361aa  mov     ecx, [rax]
0x1800361ac  cmp     ecx, 3
0x1800361af  jbe     short loc_1800361D2
0x1800361b1  mov     rcx, [rbp+var_18]
0x1800361b5  mov     [rbp+arg_8], rcx
0x1800361b9  lea     rcx, [rbp+arg_8]
0x1800361bd  mov     [rsp+60h+var_40], rcx
0x1800361c2  lea     rdx, word_1800788F2
0x1800361c9  mov     rcx, rax
0x1800361cc  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800361d1  nop
0x1800361d2  lea     rcx, [rbp+var_18]
0x1800361d6  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800361db  nop
0x1800361dc  lea     rcx, [rbp+var_30]
0x1800361e0  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800361e5  mov     rcx, rdi; this
0x1800361e8  call    ?_RefreshSlotBinding@SlotBindingMap@@AEAAJXZ; SlotBindingMap::_RefreshSlotBinding(void)
0x1800361ed  mov     r8, r14
0x1800361f0  lea     rdx, [rbp+var_18]
0x1800361f4  mov     rcx, rdi
0x1800361f7  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UAdapterParameters@SlotBindingMap@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,SlotBindingMap::AdapterParameters,GUID_COMP,std::allocator<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x1800361fc  mov     rbx, [rbp+var_8]
0x180036200  cmp     [rbx+19h], r12b
0x180036204  jnz     loc_18003634F
0x18003620a  lea     rdx, [rbx+1Ch]; Buf2
0x18003620e  mov     r8d, 10h; Size
0x180036214  mov     rcx, r14; Buf1
0x180036217  call    memcmp_0
0x18003621c  test    eax, eax
0x18003621e  js      loc_18003634F
0x180036224  cmp     rbx, [rdi]
0x180036227  jz      loc_18003634F
0x18003622d  mov     r8d, [r15]
0x180036230  lea     r14, [rbx+1Ch]
0x180036234  cmp     [r14+24h], r8d
0x180036238  jz      short loc_180036289
0x18003623a  mov     [rbx+40h], r8d
0x18003623e  mov     rcx, [rdi+20h]
0x180036242  mov     rax, [rcx]
0x180036245  mov     rdx, r14
0x180036248  cmp     r8d, 0FFFFFFFFh
0x18003624c  jnz     short loc_18003627C
0x18003624e  mov     r8d, 3
0x180036254  mov     rax, [rax+0E8h]
0x18003625b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036260  mov     rcx, [rdi+20h]
0x180036264  mov     rax, [rcx]
0x180036267  lea     r8, dword_1800684AC
0x18003626e  mov     rdx, r14
0x180036271  mov     rax, [rax+60h]
0x180036275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003627a  jmp     short loc_180036289
0x18003627c  mov     rax, [rax+120h]
0x180036283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036288  nop
0x180036289  test    rsi, rsi
0x18003628c  jz      short loc_180036297
0x18003628e  mov     rcx, rsi; lpCriticalSection
0x180036291  call    cs:__imp_LeaveCriticalSection
0x180036297  xorps   xmm0, xmm0
0x18003629a  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18003629f  mov     [rbp+var_20], r12
0x1800362a3  movdqu  xmmword ptr [rbp+var_18], xmm0
0x1800362a8  mov     [rbp+var_8], r12
0x1800362ac  lea     rcx, [rbp+var_30]
0x1800362b0  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800362b5  lea     rcx, [rbp+var_18]
0x1800362b9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800362be  mov     rdx, [rbp+var_30+8]
0x1800362c2  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x1800362c6  sub     rdx, rcx
0x1800362c9  sar     rdx, 1; unsigned __int64
0x1800362cc  lea     r8, aExit; "Exit"
0x1800362d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800362d8  mov     rdx, [rbp+var_18+8]
0x1800362dc  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x1800362e0  sub     rdx, rcx
0x1800362e3  sar     rdx, 1; unsigned __int64
0x1800362e6  mov     rax, [rbp+var_30]
0x1800362ea  mov     [rsp+60h+var_38], rax
0x1800362ef  mov     dword ptr [rsp+60h+var_40], 9Bh
0x1800362f7  lea     r9, aSlotbindingmap_0; "SlotBindingMap::OnWwanNotification"
0x1800362fe  lea     r8, aSDS; "%S(%d):%s"
0x180036305  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003630a  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003630f  mov     ecx, [rax]
0x180036311  cmp     ecx, 5
0x180036314  jbe     short loc_180036337
0x180036316  mov     rcx, [rbp+var_18]
0x18003631a  mov     [rbp+arg_8], rcx
0x18003631e  lea     rcx, [rbp+arg_8]
0x180036322  mov     [rsp+60h+var_40], rcx
0x180036327  lea     rdx, byte_180078843
0x18003632e  mov     rcx, rax
0x180036331  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180036336  nop
0x180036337  lea     rcx, [rbp+var_18]
0x18003633b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180036340  nop
0x180036341  lea     rcx, [rbp+var_30]
0x180036345  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003634a  jmp     loc_180035F19
0x18003634f  xorps   xmm0, xmm0
0x180036352  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180036357  mov     [rbp+var_20], r12
0x18003635b  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180036360  mov     [rbp+var_8], r12
0x180036364  lea     rcx, [rbp+var_30]
0x180036368  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003636d  lea     rcx, [rbp+var_18]
0x180036371  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180036376  mov     rdx, [rbp+var_30+8]
0x18003637a  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18003637e  sub     rdx, rcx
0x180036381  sar     rdx, 1; unsigned __int64
0x180036384  lea     r8, aGotNotificatio; "Got notification with an adapter ID whi"...
0x18003638b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036390  mov     rdx, [rbp+var_18+8]
0x180036394  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180036398  sub     rdx, rcx
0x18003639b  sar     rdx, 1; unsigned __int64
0x18003639e  mov     rax, [rbp+var_30]
0x1800363a2  mov     [rsp+60h+var_38], rax
0x1800363a7  mov     dword ptr [rsp+60h+var_40], 83h
0x1800363af  lea     r9, aSlotbindingmap_0; "SlotBindingMap::OnWwanNotification"
0x1800363b6  lea     r8, aSDS; "%S(%d):%s"
0x1800363bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800363c2  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800363c7  mov     ecx, [rax]
0x1800363c9  cmp     ecx, 2
0x1800363cc  jbe     short loc_1800363EF
  ... truncated ...
```
