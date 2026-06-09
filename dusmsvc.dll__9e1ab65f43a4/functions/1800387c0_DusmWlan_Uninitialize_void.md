# DusmWlan::Uninitialize(void)

- ea: `0x1800387c0`
- end: `0x180038847`
- name: `?Uninitialize@DusmWlan@@SAXXZ`
- size: `135`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x180016dc8`
- `0x1800378cc`

## callees

- `0x1800021e4`
- `0x180008060`
- `0x180013444`
- `0x180036b04`
- `0x180038768`
- `0x1800387c0`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800387db`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800387db`

## pseudocode

```c
void __fastcall DusmWlan::Uninitialize(__int64 a1, __int64 a2)
{
  LPCRITICAL_SECTION v2; // rbx
  ULONG_PTR SpinCount; // rcx
  LPCRITICAL_SECTION v4; // rbx
  _DWORD *v5; // rcx

  v2 = DusmWlan::s_pInstance;
  if ( DusmWlan::s_pInstance )
  {
    SpinCount = DusmWlan::s_pInstance[1].SpinCount;
    if ( SpinCount )
    {
      UnsubscribeServiceChangeNotifications(SpinCount);
      v2[1].SpinCount = 0;
      v2 = DusmWlan::s_pInstance;
    }
    DusmWlan::Stop((DusmWlan *)v2);
    v4 = DusmWlan::s_pInstance;
    if ( DusmWlan::s_pInstance )
    {
      DusmWlan::~DusmWlan((DusmWlan *)DusmWlan::s_pInstance);
      operator delete(v4, 0x50u);
    }
    DusmWlan::s_pInstance = 0;
  }
  v5 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(a1, a2) + 8);
  if ( *v5 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (int)v5,
      (int)&dword_1800596EC);
}

```

## disassembly

```asm
0x1800387c0  push    rbx
0x1800387c2  sub     rsp, 20h
0x1800387c6  mov     rbx, cs:?s_pInstance@DusmWlan@@0PEAV1@EA; DusmWlan * DusmWlan::s_pInstance
0x1800387cd  test    rbx, rbx
0x1800387d0  jz      short loc_180038824
0x1800387d2  mov     rcx, [rbx+48h]
0x1800387d6  test    rcx, rcx
0x1800387d9  jz      short loc_1800387F0
0x1800387db  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x1800387e1  mov     qword ptr [rbx+48h], 0
0x1800387e9  mov     rbx, cs:?s_pInstance@DusmWlan@@0PEAV1@EA; DusmWlan * DusmWlan::s_pInstance
0x1800387f0  mov     rcx, rbx; this
0x1800387f3  call    ?Stop@DusmWlan@@AEAAXXZ; DusmWlan::Stop(void)
0x1800387f8  mov     rbx, cs:?s_pInstance@DusmWlan@@0PEAV1@EA; DusmWlan * DusmWlan::s_pInstance
0x1800387ff  test    rbx, rbx
0x180038802  jz      short loc_180038819
0x180038804  mov     rcx, rbx; this
0x180038807  call    ??1DusmWlan@@AEAA@XZ; DusmWlan::~DusmWlan(void)
0x18003880c  mov     edx, 50h ; 'P'; unsigned __int64
0x180038811  mov     rcx, rbx; void *
0x180038814  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180038819  mov     cs:?s_pInstance@DusmWlan@@0PEAV1@EA, 0; DusmWlan * DusmWlan::s_pInstance
0x180038824  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180038829  mov     rcx, [rax+8]
0x18003882d  mov     eax, [rcx]
0x18003882f  cmp     eax, 5
0x180038832  jbe     short loc_180038841
0x180038834  lea     rdx, dword_1800596EC
0x18003883b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180038840  nop
0x180038841  add     rsp, 20h
0x180038845  pop     rbx
0x180038846  retn
```
