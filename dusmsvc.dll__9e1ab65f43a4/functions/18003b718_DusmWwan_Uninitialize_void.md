# DusmWwan::Uninitialize(void)

- ea: `0x18003b718`
- end: `0x18003b79f`
- name: `?Uninitialize@DusmWwan@@SAXXZ`
- size: `135`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x180016dc8`
- `0x180039db4`

## callees

- `0x1800021e4`
- `0x180008060`
- `0x180013444`
- `0x180039888`
- `0x18003b5ec`
- `0x18003b718`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x18003b733`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x18003b733`

## pseudocode

```c
void __fastcall DusmWwan::Uninitialize(__int64 a1, __int64 a2)
{
  DusmWwan *v2; // rbx
  __int64 v3; // rcx
  DusmWwan *v4; // rbx
  _DWORD *v5; // rcx

  v2 = DusmWwan::s_pInstance;
  if ( DusmWwan::s_pInstance )
  {
    v3 = *((_QWORD *)DusmWwan::s_pInstance + 2);
    if ( v3 )
    {
      UnsubscribeServiceChangeNotifications(v3);
      *((_QWORD *)v2 + 2) = 0;
      v2 = DusmWwan::s_pInstance;
    }
    DusmWwan::Stop(v2);
    v4 = DusmWwan::s_pInstance;
    if ( DusmWwan::s_pInstance )
    {
      DusmWwan::~DusmWwan(DusmWwan::s_pInstance);
      operator delete(v4, 0x50u);
    }
    DusmWwan::s_pInstance = 0;
  }
  v5 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(a1, a2) + 8);
  if ( *v5 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (int)v5,
      (int)qword_18005A408);
}

```

## disassembly

```asm
0x18003b718  push    rbx
0x18003b71a  sub     rsp, 20h
0x18003b71e  mov     rbx, cs:?s_pInstance@DusmWwan@@0PEAV1@EA; DusmWwan * DusmWwan::s_pInstance
0x18003b725  test    rbx, rbx
0x18003b728  jz      short loc_18003B77C
0x18003b72a  mov     rcx, [rbx+10h]
0x18003b72e  test    rcx, rcx
0x18003b731  jz      short loc_18003B748
0x18003b733  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x18003b739  mov     qword ptr [rbx+10h], 0
0x18003b741  mov     rbx, cs:?s_pInstance@DusmWwan@@0PEAV1@EA; DusmWwan * DusmWwan::s_pInstance
0x18003b748  mov     rcx, rbx; this
0x18003b74b  call    ?Stop@DusmWwan@@AEAAXXZ; DusmWwan::Stop(void)
0x18003b750  mov     rbx, cs:?s_pInstance@DusmWwan@@0PEAV1@EA; DusmWwan * DusmWwan::s_pInstance
0x18003b757  test    rbx, rbx
0x18003b75a  jz      short loc_18003B771
0x18003b75c  mov     rcx, rbx; this
0x18003b75f  call    ??1DusmWwan@@AEAA@XZ; DusmWwan::~DusmWwan(void)
0x18003b764  mov     edx, 50h ; 'P'; unsigned __int64
0x18003b769  mov     rcx, rbx; void *
0x18003b76c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003b771  mov     cs:?s_pInstance@DusmWwan@@0PEAV1@EA, 0; DusmWwan * DusmWwan::s_pInstance
0x18003b77c  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003b781  mov     rcx, [rax+8]
0x18003b785  mov     eax, [rcx]
0x18003b787  cmp     eax, 5
0x18003b78a  jbe     short loc_18003B799
0x18003b78c  lea     rdx, qword_18005A408
0x18003b793  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003b798  nop
0x18003b799  add     rsp, 20h
0x18003b79d  pop     rbx
0x18003b79e  retn
```
