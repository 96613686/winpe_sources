# ServiceHandler::ServiceControlHandler(ulong,ulong,void *)

- ea: `0x1800d7d70`
- end: `0x1800d7e20`
- name: `?ServiceControlHandler@ServiceHandler@@AEAAKKKPEAX@Z`
- size: `176`
- prototype: `unsigned int(ServiceHandler *__hidden this, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1800d7e30`

## callees

- `0x180001010`
- `0x180073154`
- `0x1800d7d70`
- `0x1800d8504`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d7e12`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d7e12`

## string_xrefs

- `0x1800d7dc7`: `LpaServiceHost`
- `0x1800d7db4`: `ServiceHandler::ServiceControlHandler`

## pseudocode

```c
__int64 __fastcall ServiceHandler::ServiceControlHandler(ServiceHandler *this, int a2, unsigned int a3, const char *a4)
{
  int v5; // edx
  int v6; // edx
  int v7; // edx
  const char *v9; // [rsp+30h] [rbp-18h] BYREF
  const char *v10; // [rsp+68h] [rbp+20h] BYREF

  v10 = a4;
  v5 = a2 - 1;
  if ( !v5 )
    goto LABEL_14;
  v6 = v5 - 4;
  if ( !v6 )
    goto LABEL_14;
  v7 = v6 - 8;
  if ( !v7 )
  {
    LPA::CoreLpa::OnPowerEvent(*((LPA::CoreLpa **)this + 11), a3);
    return 0;
  }
  if ( v7 == 2 )
  {
LABEL_14:
    if ( !_InterlockedExchange((volatile __int32 *)this + 38, 1) )
    {
      if ( *((_DWORD *)this + 5) == 2 )
      {
        if ( (_DWORD)CallbackContext )
        {
          v10 = "ServiceHandler::ServiceControlHandler";
          v9 = "LpaServiceHost";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (_DWORD)this,
            (unsigned int)word_180134912,
            a3,
            (_DWORD)a4,
            (__int64)&v9,
            (__int64)&v10);
        }
      }
      else
      {
        ServiceHandler::UpdateServiceStatus(this, 3, 0, 10000);
        SetEvent(*((HANDLE *)this + 7));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800d7d70  mov     [rsp+arg_18], r9
0x1800d7d75  push    rbx
0x1800d7d76  sub     rsp, 40h
0x1800d7d7a  mov     rbx, rcx
0x1800d7d7d  sub     edx, 1
0x1800d7d80  jz      short loc_1800D7D95
0x1800d7d82  sub     edx, 4
0x1800d7d85  jz      short loc_1800D7D95
0x1800d7d87  sub     edx, 8
0x1800d7d8a  jz      short loc_1800D7DEE
0x1800d7d8c  cmp     edx, 2
0x1800d7d8f  jnz     loc_1800D7E18
0x1800d7d95  mov     eax, 1
0x1800d7d9a  xchg    eax, [rcx+98h]
0x1800d7da0  test    eax, eax
0x1800d7da2  jnz     short loc_1800D7E18
0x1800d7da4  cmp     dword ptr [rcx+14h], 2
0x1800d7da8  jnz     short loc_1800D7DFC
0x1800d7daa  mov     eax, cs:CallbackContext
0x1800d7db0  test    eax, eax
0x1800d7db2  jz      short loc_1800D7E18
0x1800d7db4  lea     rax, aServicehandler; "ServiceHandler::ServiceControlHandler"
0x1800d7dbb  mov     [rsp+48h+arg_18], rax
0x1800d7dc0  lea     rdx, word_180134912
0x1800d7dc7  lea     rax, aLpaservicehost; "LpaServiceHost"
0x1800d7dce  mov     [rsp+48h+var_18], rax
0x1800d7dd3  lea     rax, [rsp+48h+arg_18]
0x1800d7dd8  mov     [rsp+48h+var_20], rax
0x1800d7ddd  lea     rax, [rsp+48h+var_18]
0x1800d7de2  mov     [rsp+48h+var_28], rax
0x1800d7de7  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800d7dec  jmp     short loc_1800D7E18
0x1800d7dee  mov     rcx, [rcx+58h]; this
0x1800d7df2  mov     edx, r8d; unsigned int
0x1800d7df5  call    ?OnPowerEvent@CoreLpa@LPA@@QEAAXK@Z; LPA::CoreLpa::OnPowerEvent(ulong)
0x1800d7dfa  jmp     short loc_1800D7E18
0x1800d7dfc  xor     r8d, r8d; unsigned int
0x1800d7dff  mov     r9d, 2710h; unsigned int
0x1800d7e05  lea     edx, [r8+3]; unsigned int
0x1800d7e09  call    ?UpdateServiceStatus@ServiceHandler@@AEAAXKKK@Z; ServiceHandler::UpdateServiceStatus(ulong,ulong,ulong)
0x1800d7e0e  mov     rcx, [rbx+38h]; hEvent
0x1800d7e12  call    cs:__imp_SetEvent
0x1800d7e18  xor     eax, eax
0x1800d7e1a  add     rsp, 40h
0x1800d7e1e  pop     rbx
0x1800d7e1f  retn
```
