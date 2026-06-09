# DusmNla::Uninitialize(void)

- ea: `0x180030c68`
- end: `0x180030cee`
- name: `?Uninitialize@DusmNla@@SAXXZ`
- size: `134`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x180016dc8`

## callees

- `0x1800021e4`
- `0x180008060`
- `0x180013444`
- `0x1800303c0`
- `0x180030bf0`
- `0x180030c68`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180030c83`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180030c83`

## pseudocode

```c
void __fastcall DusmNla::Uninitialize(__int64 a1, __int64 a2)
{
  DusmNla *v2; // rbx
  __int64 v3; // rcx
  DusmNla *v4; // rbx
  _DWORD *v5; // rcx

  v2 = DusmNla::s_pInstance;
  if ( DusmNla::s_pInstance )
  {
    v3 = *((_QWORD *)DusmNla::s_pInstance + 2);
    if ( v3 )
    {
      UnsubscribeServiceChangeNotifications(v3);
      *((_QWORD *)v2 + 2) = 0;
      v2 = DusmNla::s_pInstance;
    }
    DusmNla::Stop(v2);
    v4 = DusmNla::s_pInstance;
    if ( DusmNla::s_pInstance )
    {
      DusmNla::~DusmNla(DusmNla::s_pInstance);
      operator delete(v4, 0x60u);
    }
    DusmNla::s_pInstance = 0;
  }
  v5 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(a1, a2) + 8);
  if ( *v5 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (int)v5,
      (int)byte_180058E33);
}

```

## disassembly

```asm
0x180030c68  push    rbx
0x180030c6a  sub     rsp, 20h
0x180030c6e  mov     rbx, cs:?s_pInstance@DusmNla@@0PEAV1@EA; DusmNla * DusmNla::s_pInstance
0x180030c75  test    rbx, rbx
0x180030c78  jz      short loc_180030CCC
0x180030c7a  mov     rcx, [rbx+10h]
0x180030c7e  test    rcx, rcx
0x180030c81  jz      short loc_180030C98
0x180030c83  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x180030c89  mov     qword ptr [rbx+10h], 0
0x180030c91  mov     rbx, cs:?s_pInstance@DusmNla@@0PEAV1@EA; DusmNla * DusmNla::s_pInstance
0x180030c98  mov     rcx, rbx; this
0x180030c9b  call    ?Stop@DusmNla@@AEAAXXZ; DusmNla::Stop(void)
0x180030ca0  mov     rbx, cs:?s_pInstance@DusmNla@@0PEAV1@EA; DusmNla * DusmNla::s_pInstance
0x180030ca7  test    rbx, rbx
0x180030caa  jz      short loc_180030CC1
0x180030cac  mov     rcx, rbx; this
0x180030caf  call    ??1DusmNla@@AEAA@XZ; DusmNla::~DusmNla(void)
0x180030cb4  mov     edx, 60h ; '`'; unsigned __int64
0x180030cb9  mov     rcx, rbx; void *
0x180030cbc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180030cc1  mov     cs:?s_pInstance@DusmNla@@0PEAV1@EA, 0; DusmNla * DusmNla::s_pInstance
0x180030ccc  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180030cd1  mov     rcx, [rax+8]
0x180030cd5  mov     eax, [rcx]
0x180030cd7  cmp     eax, 5
0x180030cda  jbe     short loc_180030CE8
0x180030cdc  lea     rdx, byte_180058E33
0x180030ce3  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180030ce8  add     rsp, 20h
0x180030cec  pop     rbx
0x180030ced  retn
```
