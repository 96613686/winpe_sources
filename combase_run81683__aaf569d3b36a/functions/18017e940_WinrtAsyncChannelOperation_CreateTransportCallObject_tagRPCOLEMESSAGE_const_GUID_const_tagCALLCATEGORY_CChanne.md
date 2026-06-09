# WinrtAsyncChannelOperation::CreateTransportCallObject(tagRPCOLEMESSAGE const *,_GUID const &,tagCALLCATEGORY,CChannelHandle *,CDestObject &&,_RTL_WORK_ON_BEHALF_TICKET,uint,CAsyncCall * *)

- ea: `0x18017e940`
- end: `0x18017ee6f`
- name: `?CreateTransportCallObject@WinrtAsyncChannelOperation@@UEAAJPEBUtagRPCOLEMESSAGE@@AEBU_GUID@@W4tagCALLCATEGORY@@PEAVCChannelHandle@@$$QEAVCDestObject@@U_RTL_WORK_ON_BEHALF_TICKET@@IPEAPEAVCAsyncCall@@@Z`
- size: `1327`
- prototype: `HRESULT __fastcall(WinrtAsyncChannelOperation *this, const tagRPCOLEMESSAGE *pMessage, const _GUID *iidWire, tagCALLCATEGORY callcat, CChannelHandle *pHandle, CDestObject *destObject, _RTL_WORK_ON_BEHALF_TICKET workOnBehalfTicket, unsigned int retryCount, CAsyncCall **ppAsyncCall)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18009e258`

## callees

- `0x180006710`
- `0x18003a8bc`
- `0x180083028`
- `0x18009e7d0`
- `0x18009e8c4`
- `0x1800a601c`
- `0x1800cd968`
- `0x1800cf078`
- `0x1800dc380`
- `0x1800e6614`
- `0x1800eb428`
- `0x1800eb70c`
- `0x1800f8bfc`
- `0x180139ef8`
- `0x18016dd64`
- `0x18016e0ac`
- `0x18017e940`
- `0x1801999b0`
- `0x180199d80`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017e9eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017eaef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017ec2a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017ecd9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017e9eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017eaef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017ec2a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18017ecd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017ee0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017ee0f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017ed71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017ed71`

## string_xrefs

- `0x18017ebc1`: `onecore\com\combase\dcomrem\winrtasyncchannel.cpp`

## pseudocode

```c

```
