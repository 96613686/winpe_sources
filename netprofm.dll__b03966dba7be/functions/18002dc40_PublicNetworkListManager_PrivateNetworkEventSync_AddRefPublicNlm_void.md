# PublicNetworkListManager::PrivateNetworkEventSync::AddRefPublicNlm(void)

- ea: `0x18002dc40`
- end: `0x18002dc95`
- name: `?AddRefPublicNlm@PrivateNetworkEventSync@PublicNetworkListManager@@AEAA?AV?$CComPtr@VPublicNetworkListManager@@@ATL@@XZ`
- size: `85`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d580`
- `0x18002d6ec`
- `0x18002d858`
- `0x18002d9c4`
- `0x18002e22c`
- `0x18002e3b0`
- `0x18002e570`
- `0x18002e700`
- `0x18002e800`
- `0x18002e920`
- `0x18002ea30`
- `0x18002ecd0`
- `0x18002ee80`
- `0x18002ef90`
- `0x18002f150`
- `0x18002f270`

## callees

- `0x18002db30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dc7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dc7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dc5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dc5f`

## pseudocode

```c
_QWORD *__fastcall PublicNetworkListManager::PrivateNetworkEventSync::AddRefPublicNlm(__int64 a1, _QWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 608);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 608));
  *a2 = 0;
  ATL::CComPtrBase<PublicNetworkListManager>::CComPtrBase<PublicNetworkListManager>(a2, *(_QWORD *)(a1 + 648));
  LeaveCriticalSection(v2);
  return a2;
}

```

## disassembly

```asm
0x18002dc40  mov     [rsp+arg_0], rbx
0x18002dc45  mov     [rsp+arg_8], rsi
0x18002dc4a  push    rdi
0x18002dc4b  sub     rsp, 20h
0x18002dc4f  lea     rdi, [rcx+260h]
0x18002dc56  mov     rbx, rcx
0x18002dc59  mov     rcx, rdi; lpCriticalSection
0x18002dc5c  mov     rsi, rdx
0x18002dc5f  call    cs:__imp_EnterCriticalSection
0x18002dc65  xor     eax, eax
0x18002dc67  mov     rcx, rsi
0x18002dc6a  mov     [rsi], rax
0x18002dc6d  mov     rdx, [rbx+288h]
0x18002dc74  call    ??0?$CComPtrBase@VPublicNetworkListManager@@@ATL@@IEAA@PEAVPublicNetworkListManager@@@Z; ATL::CComPtrBase<PublicNetworkListManager>::CComPtrBase<PublicNetworkListManager>(PublicNetworkListManager *)
0x18002dc79  mov     rcx, rdi; lpCriticalSection
0x18002dc7c  call    cs:__imp_LeaveCriticalSection
0x18002dc82  mov     rbx, [rsp+28h+arg_0]
0x18002dc87  mov     rax, rsi
0x18002dc8a  mov     rsi, [rsp+28h+arg_8]
0x18002dc8f  add     rsp, 20h
0x18002dc93  pop     rdi
0x18002dc94  retn
```
