# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::Invoke(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,ABI::Windows::Foundation::AsyncStatus)

- ea: `0x140007810`
- end: `0x140007844`
- name: `?Invoke@CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAAJ0W4AsyncStatus@56ABI@@@Z`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007810`
- `0x14000bfd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000781c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000781c`

## pseudocode

```c
__int64 __fastcall `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *>'::`2'::CompletionDelegate::Invoke(
        __int64 a1,
        __int64 a2,
        int a3)
{
  unsigned int v3; // r8d
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_DWORD *)(a1 + 48) = a3;
  if ( !SetEvent(*(HANDLE *)(a1 + 56)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v3, v4);
  return 0;
}

```

## disassembly

```asm
0x140007810  sub     rsp, 28h
0x140007814  mov     [rcx+30h], r8d
0x140007818  mov     rcx, [rcx+38h]; hEvent
0x14000781c  call    cs:__imp_SetEvent
0x140007823  nop     dword ptr [rax+rax+00h]
0x140007828  test    eax, eax
0x14000782a  jz      short loc_140007834
0x14000782c  xor     eax, eax
0x14000782e  add     rsp, 28h
0x140007832  retn
0x140007834  mov     rcx, [rsp+28h]; this
0x140007839  mov     edx, 0A01h; void *
0x14000783e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
