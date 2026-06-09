# HotpatchMonitor::StopService(void)

- ea: `0x18000b620`
- end: `0x18000b685`
- name: `?StopService@HotpatchMonitor@@UEAAXXZ`
- size: `101`
- prototype: `void __fastcall(HotpatchMonitor *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x180001008`
- `0x18000b620`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b679`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b679`

## pseudocode

```c
void __fastcall HotpatchMonitor::StopService(HotpatchMonitor *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  void *v5; // rcx
  const char *v6; // [rsp+40h] [rbp+8h] BYREF

  (*(void (__fastcall **)(HotpatchMonitor *, __int64, _QWORD, __int64))(*(_QWORD *)this + 32LL))(this, 3, 0, 5000);
  if ( (unsigned int)dword_18001E048 > 5 )
  {
    v6 = "Context";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v2,
      (__int64)byte_180018F59,
      v3,
      v4,
      (const unsigned __int16 **)&v6);
  }
  v5 = (void *)*((_QWORD *)this + 6);
  if ( v5 != (void *)-1LL )
    SetEvent(v5);
}

```

## disassembly

```asm
0x18000b620  push    rbx
0x18000b622  sub     rsp, 30h
0x18000b626  mov     rax, [rcx]
0x18000b629  xor     r8d, r8d
0x18000b62c  mov     r9d, 1388h
0x18000b632  mov     rbx, rcx
0x18000b635  mov     rax, [rax+20h]
0x18000b639  lea     edx, [r8+3]
0x18000b63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b642  mov     eax, cs:dword_18001E048
0x18000b648  cmp     eax, 5
0x18000b64b  jbe     short loc_18000B66F
0x18000b64d  lea     rax, aContext; "Context"
0x18000b654  mov     [rsp+38h+arg_0], rax
0x18000b659  lea     rdx, byte_180018F59
0x18000b660  lea     rax, [rsp+38h+arg_0]
0x18000b665  mov     [rsp+38h+var_18], rax
0x18000b66a  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000b66f  mov     rcx, [rbx+30h]; hEvent
0x18000b673  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b677  jz      short loc_18000B67F
0x18000b679  call    cs:__imp_SetEvent
0x18000b67f  add     rsp, 30h
0x18000b683  pop     rbx
0x18000b684  retn
```
