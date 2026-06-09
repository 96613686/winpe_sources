# ESIMPM::EsimPoMgr::s_OobeCompletedCallback(void *)

- ea: `0x140025910`
- end: `0x140025953`
- name: `?s_OobeCompletedCallback@EsimPoMgr@ESIMPM@@CAXPEAX@Z`
- size: `67`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001278`
- `0x140025910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002594c`

## string_xrefs

- `0x14002591f`: `ESIMPM::EsimPoMgr::s_OobeCompletedCallback`

## pseudocode

```c
void __fastcall ESIMPM::EsimPoMgr::s_OobeCompletedCallback(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  const char *v4; // [rsp+48h] [rbp+10h] BYREF

  if ( (unsigned int)dword_140075078 > 4 )
  {
    v4 = "ESIMPM::EsimPoMgr::s_OobeCompletedCallback";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      a1,
      (__int64)word_14006A6F2,
      a3,
      a4,
      (const unsigned __int16 **)&v4);
  }
  SetEvent(ESIMPM::EsimPoMgr::m_waitOobeHandle);
}

```

## disassembly

```asm
0x140025910  sub     rsp, 38h
0x140025914  mov     eax, cs:dword_140075078
0x14002591a  cmp     eax, 4
0x14002591d  jbe     short loc_140025941
0x14002591f  lea     rax, aEsimpmEsimpomg_8; "ESIMPM::EsimPoMgr::s_OobeCompletedCallb"...
0x140025926  mov     [rsp+38h+arg_8], rax
0x14002592b  lea     rdx, word_14006A6F2
0x140025932  lea     rax, [rsp+38h+arg_8]
0x140025937  mov     [rsp+38h+var_18], rax
0x14002593c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140025941  mov     rcx, cs:?m_waitOobeHandle@EsimPoMgr@ESIMPM@@0V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@A; tlx::unique_any<tlx::file_handle_traits> ESIMPM::EsimPoMgr::m_waitOobeHandle
0x140025948  add     rsp, 38h
0x14002594c  jmp     cs:__imp_SetEvent
```
