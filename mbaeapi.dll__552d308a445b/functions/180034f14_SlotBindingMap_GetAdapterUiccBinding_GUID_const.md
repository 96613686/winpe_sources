# SlotBindingMap::GetAdapterUiccBinding(_GUID const &)

- ea: `0x180034f14`
- end: `0x18003526b`
- name: `?GetAdapterUiccBinding@SlotBindingMap@@QEAAJAEBU_GUID@@@Z`
- size: `855`
- prototype: `__int64 __fastcall(SlotBindingMap *__hidden this, const struct _GUID *Buf1)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003b9e8`

## callees

- `0x18000178c`
- `0x1800040cd`
- `0x180009ffc`
- `0x18001105c`
- `0x1800172bc`
- `0x18001dd10`
- `0x180033184`
- `0x180034f14`
- `0x1800458c4`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003517a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003524b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003517a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003524b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034f36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034f36`

## string_xrefs

- `0x180034fb5`: `Adapter-slot cache becomes out-of-date!`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SlotBindingMap::GetAdapterUiccBinding(struct _RTL_CRITICAL_SECTION *this, const struct _GUID *Buf1)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // rbx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // [rsp+20h] [rbp-40h]
  int v18; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v19[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v21[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v22; // [rsp+58h] [rbp-8h]
  unsigned __int16 *v23; // [rsp+80h] [rbp+20h] BYREF
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+90h] [rbp+30h]

  v4 = this + 1;
  EnterCriticalSection(this + 1);
  v24 = v4;
  std::_Tree<std::_Tmap_traits<_GUID,SlotBindingMap::AdapterParameters,GUID_COMP,std::allocator<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>,0>>::_Find_lower_bound<_GUID>(
    (__int64)this,
    v21,
    Buf1);
  v5 = v22;
  if ( !*(_BYTE *)(v22 + 25)
    && memcmp_0(Buf1, (const void *)(v22 + 28), 0x10u) >= 0
    && (PRTL_CRITICAL_SECTION_DEBUG)v5 != this->DebugInfo )
  {
    goto LABEL_9;
  }
  *(_OWORD *)v21 = 0;
  v22 = 0;
  *(_OWORD *)v19 = 0;
  v20 = 0;
  std::vector<unsigned short>::resize(v21);
  std::vector<unsigned short>::resize(v19);
  StringCchPrintfW(v21[0], v21[1] - v21[0], L"Adapter-slot cache becomes out-of-date!");
  v18 = 165;
  StringCchPrintfW(v19[0], v19[1] - v19[0], L"%S(%d):%s", "SlotBindingMap::GetAdapterUiccBinding", v18, v21[0]);
  v6 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v6 > 3u )
  {
    v23 = v19[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)&word_180078866,
      v7,
      v8,
      (const unsigned __int16 **)&v23);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v19);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v21);
  SlotBindingMap::_RefreshSlotBinding((SlotBindingMap *)this);
  std::_Tree<std::_Tmap_traits<_GUID,SlotBindingMap::AdapterParameters,GUID_COMP,std::allocator<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>,0>>::_Find_lower_bound<_GUID>(
    (__int64)this,
    v21,
    Buf1);
  v5 = v22;
  if ( *(_BYTE *)(v22 + 25)
    || memcmp_0(Buf1, (const void *)(v22 + 28), 0x10u) < 0
    || (PRTL_CRITICAL_SECTION_DEBUG)v5 == this->DebugInfo )
  {
    *(_OWORD *)v19 = 0;
    v20 = 0;
    *(_OWORD *)v21 = 0;
    v22 = 0;
    std::vector<unsigned short>::resize(v19);
    std::vector<unsigned short>::resize(v21);
    StringCchPrintfW(v19[0], v19[1] - v19[0], L"Got notification with an adapter ID which is not enumeratable!");
    LODWORD(v17) = 170;
    StringCchPrintfW(v21[0], v21[1] - v21[0], L"%S(%d):%s", "SlotBindingMap::GetAdapterUiccBinding", v17, v19[0]);
    v14 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v14 > 2u )
    {
      v23 = v21[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v14,
        (__int64)&byte_1800787FF,
        v15,
        v16,
        (const unsigned __int16 **)&v23);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v21);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v19);
    if ( v4 )
      LeaveCriticalSection(v4);
    return 2147500037LL;
  }
  else
  {
LABEL_9:
    v9 = *(unsigned int *)(v5 + 64);
    if ( (_DWORD)v9 == -1 )
    {
      *(_OWORD *)v19 = 0;
      v20 = 0;
      *(_OWORD *)v21 = 0;
      v22 = 0;
      std::vector<unsigned short>::resize(v19);
      std::vector<unsigned short>::resize(v21);
      StringCchPrintfW(v19[0], v19[1] - v19[0], L"The adapter is not associated with a slot duing the initialization.");
      LODWORD(v17) = 177;
      StringCchPrintfW(v21[0], v21[1] - v21[0], L"%S(%d):%s", "SlotBindingMap::GetAdapterUiccBinding", v17, v19[0]);
      v10 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v10 > 3u )
      {
        v23 = v21[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v10,
          (__int64)qword_180078820,
          v11,
          v12,
          (const unsigned __int16 **)&v23);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v21);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v19);
      (*(void (__fastcall **)(ULONG_PTR, __int64, __int64))(*(_QWORD *)this->SpinCount + 232LL))(
        this->SpinCount,
        v5 + 28,
        3);
    }
    else
    {
      (*(void (__fastcall **)(ULONG_PTR, __int64, __int64))(*(_QWORD *)this->SpinCount + 288LL))(
        this->SpinCount,
        v5 + 28,
        v9);
    }
    if ( v4 )
      LeaveCriticalSection(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x180034f14  mov     [rsp-18h+arg_8], rbx
0x180034f19  mov     [rsp-18h+arg_18], rsi
0x180034f1e  push    rbp
0x180034f1f  push    rdi
0x180034f20  push    r14
0x180034f22  mov     rbp, rsp
0x180034f25  sub     rsp, 60h
0x180034f29  mov     r14, rdx
0x180034f2c  mov     rdi, rcx
0x180034f2f  lea     rsi, [rcx+28h]
0x180034f33  mov     rcx, rsi; lpCriticalSection
0x180034f36  call    cs:__imp_EnterCriticalSection
0x180034f3c  mov     [rbp+arg_10], rsi
0x180034f40  mov     r8, r14
0x180034f43  lea     rdx, [rbp+var_18]
0x180034f47  mov     rcx, rdi
0x180034f4a  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UAdapterParameters@SlotBindingMap@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,SlotBindingMap::AdapterParameters,GUID_COMP,std::allocator<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x180034f4f  mov     rbx, [rbp+var_8]
0x180034f53  cmp     byte ptr [rbx+19h], 0
0x180034f57  jnz     short loc_180034F78
0x180034f59  lea     rdx, [rbx+1Ch]; Buf2
0x180034f5d  mov     r8d, 10h; Size
0x180034f63  mov     rcx, r14; Buf1
0x180034f66  call    memcmp_0
0x180034f6b  test    eax, eax
0x180034f6d  js      short loc_180034F78
0x180034f6f  cmp     rbx, [rdi]
0x180034f72  jnz     loc_18003507B
0x180034f78  xorps   xmm0, xmm0
0x180034f7b  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180034f80  mov     [rbp+var_8], 0
0x180034f88  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180034f8d  mov     [rbp+var_20], 0
0x180034f95  lea     rcx, [rbp+var_18]
0x180034f99  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180034f9e  lea     rcx, [rbp+var_30]
0x180034fa2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180034fa7  mov     rdx, [rbp+var_18+8]
0x180034fab  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180034faf  sub     rdx, rcx
0x180034fb2  sar     rdx, 1; unsigned __int64
0x180034fb5  lea     r8, aAdapterSlotCac; "Adapter-slot cache becomes out-of-date!"
0x180034fbc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034fc1  mov     rdx, [rbp+var_30+8]
0x180034fc5  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x180034fc9  sub     rdx, rcx
0x180034fcc  sar     rdx, 1; unsigned __int64
0x180034fcf  mov     rax, [rbp+var_18]
0x180034fd3  mov     [rsp+60h+var_38], rax
0x180034fd8  mov     dword ptr [rsp+60h+var_40], 0A5h
0x180034fe0  lea     r9, aSlotbindingmap_1; "SlotBindingMap::GetAdapterUiccBinding"
0x180034fe7  lea     r8, aSDS; "%S(%d):%s"
0x180034fee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034ff3  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180034ff8  mov     ecx, [rax]
0x180034ffa  cmp     ecx, 3
0x180034ffd  jbe     short loc_180035020
0x180034fff  mov     rcx, [rbp+var_30]
0x180035003  mov     [rbp+arg_0], rcx
0x180035007  lea     rcx, [rbp+arg_0]
0x18003500b  mov     [rsp+60h+var_40], rcx
0x180035010  lea     rdx, word_180078866
0x180035017  mov     rcx, rax
0x18003501a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003501f  nop
0x180035020  lea     rcx, [rbp+var_30]
0x180035024  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180035029  nop
0x18003502a  lea     rcx, [rbp+var_18]
0x18003502e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180035033  mov     rcx, rdi; this
0x180035036  call    ?_RefreshSlotBinding@SlotBindingMap@@AEAAJXZ; SlotBindingMap::_RefreshSlotBinding(void)
0x18003503b  mov     r8, r14
0x18003503e  lea     rdx, [rbp+var_18]
0x180035042  mov     rcx, rdi
0x180035045  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UAdapterParameters@SlotBindingMap@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,SlotBindingMap::AdapterParameters,GUID_COMP,std::allocator<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18003504a  mov     rbx, [rbp+var_8]
0x18003504e  cmp     byte ptr [rbx+19h], 0
0x180035052  jnz     loc_180035187
0x180035058  lea     rdx, [rbx+1Ch]; Buf2
0x18003505c  mov     r8d, 10h; Size
0x180035062  mov     rcx, r14; Buf1
0x180035065  call    memcmp_0
0x18003506a  test    eax, eax
0x18003506c  js      loc_180035187
0x180035072  cmp     rbx, [rdi]
0x180035075  jz      loc_180035187
0x18003507b  mov     r8d, [rbx+40h]
0x18003507f  cmp     r8d, 0FFFFFFFFh
0x180035083  jnz     loc_18003515A
0x180035089  xorps   xmm0, xmm0
0x18003508c  movdqu  xmmword ptr [rbp+var_30], xmm0
0x180035091  mov     [rbp+var_20], 0
0x180035099  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18003509e  mov     [rbp+var_8], 0
0x1800350a6  lea     rcx, [rbp+var_30]
0x1800350aa  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800350af  lea     rcx, [rbp+var_18]
0x1800350b3  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800350b8  mov     rdx, [rbp+var_30+8]
0x1800350bc  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x1800350c0  sub     rdx, rcx
0x1800350c3  sar     rdx, 1; unsigned __int64
0x1800350c6  lea     r8, aTheAdapterIsNo; "The adapter is not associated with a sl"...
0x1800350cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800350d2  mov     rdx, [rbp+var_18+8]
0x1800350d6  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x1800350da  sub     rdx, rcx
0x1800350dd  sar     rdx, 1; unsigned __int64
0x1800350e0  mov     rax, [rbp+var_30]
0x1800350e4  mov     [rsp+60h+var_38], rax
0x1800350e9  mov     dword ptr [rsp+60h+var_40], 0B1h
0x1800350f1  lea     r9, aSlotbindingmap_1; "SlotBindingMap::GetAdapterUiccBinding"
0x1800350f8  lea     r8, aSDS; "%S(%d):%s"
0x1800350ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035104  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180035109  mov     ecx, [rax]
0x18003510b  cmp     ecx, 3
0x18003510e  jbe     short loc_180035131
0x180035110  mov     rcx, [rbp+var_18]
0x180035114  mov     [rbp+arg_0], rcx
0x180035118  lea     rcx, [rbp+arg_0]
0x18003511c  mov     [rsp+60h+var_40], rcx
0x180035121  lea     rdx, qword_180078820
0x180035128  mov     rcx, rax
0x18003512b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180035130  nop
0x180035131  lea     rcx, [rbp+var_18]
0x180035135  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003513a  nop
0x18003513b  lea     rcx, [rbp+var_30]
0x18003513f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180035144  mov     rcx, [rdi+20h]
0x180035148  mov     rax, [rcx]
0x18003514b  mov     r8d, 3
0x180035151  mov     rax, [rax+0E8h]
0x180035158  jmp     short loc_180035168
0x18003515a  mov     rcx, [rdi+20h]
0x18003515e  mov     rax, [rcx]
0x180035161  mov     rax, [rax+120h]
0x180035168  lea     rdx, [rbx+1Ch]
0x18003516c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035171  nop
0x180035172  test    rsi, rsi
0x180035175  jz      short loc_180035180
0x180035177  mov     rcx, rsi; lpCriticalSection
0x18003517a  call    cs:__imp_LeaveCriticalSection
0x180035180  xor     eax, eax
0x180035182  jmp     loc_180035256
0x180035187  xorps   xmm0, xmm0
0x18003518a  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18003518f  mov     [rbp+var_20], 0
0x180035197  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18003519c  mov     [rbp+var_8], 0
0x1800351a4  lea     rcx, [rbp+var_30]
0x1800351a8  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800351ad  lea     rcx, [rbp+var_18]
0x1800351b1  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800351b6  mov     rdx, [rbp+var_30+8]
0x1800351ba  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x1800351be  sub     rdx, rcx
0x1800351c1  sar     rdx, 1; unsigned __int64
0x1800351c4  lea     r8, aGotNotificatio; "Got notification with an adapter ID whi"...
0x1800351cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800351d0  mov     rdx, [rbp+var_18+8]
0x1800351d4  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x1800351d8  sub     rdx, rcx
0x1800351db  sar     rdx, 1; unsigned __int64
0x1800351de  mov     rax, [rbp+var_30]
0x1800351e2  mov     [rsp+60h+var_38], rax
0x1800351e7  mov     dword ptr [rsp+60h+var_40], 0AAh
0x1800351ef  lea     r9, aSlotbindingmap_1; "SlotBindingMap::GetAdapterUiccBinding"
0x1800351f6  lea     r8, aSDS; "%S(%d):%s"
0x1800351fd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035202  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180035207  mov     ecx, [rax]
0x180035209  cmp     ecx, 2
0x18003520c  jbe     short loc_18003522F
0x18003520e  mov     rcx, [rbp+var_18]
0x180035212  mov     [rbp+arg_0], rcx
0x180035216  lea     rcx, [rbp+arg_0]
0x18003521a  mov     [rsp+60h+var_40], rcx
0x18003521f  lea     rdx, byte_1800787FF
0x180035226  mov     rcx, rax
0x180035229  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003522e  nop
0x18003522f  lea     rcx, [rbp+var_18]
0x180035233  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180035238  nop
0x180035239  lea     rcx, [rbp+var_30]
0x18003523d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180035242  nop
0x180035243  test    rsi, rsi
0x180035246  jz      short loc_180035251
0x180035248  mov     rcx, rsi; lpCriticalSection
0x18003524b  call    cs:__imp_LeaveCriticalSection
0x180035251  mov     eax, 80004005h
0x180035256  lea     r11, [rsp+60h+var_s0]
0x18003525b  mov     rbx, [r11+28h]
0x18003525f  mov     rsi, [r11+38h]
0x180035263  mov     rsp, r11
0x180035266  pop     r14
0x180035268  pop     rdi
0x180035269  pop     rbp
0x18003526a  retn
```
