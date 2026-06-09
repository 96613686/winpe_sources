# CMSMQQueue::InternalReceive(ulong,void *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,IMSMQMessage4 * *)

- ea: `0x18001af00`
- end: `0x18001b1c7`
- name: `?InternalReceive@CMSMQQueue@@QEAAJKPEAXPEAUtagVARIANT@@11111PEAPEAUIMSMQMessage4@@@Z`
- size: `711`
- prototype: `__int64 __fastcall(CMSMQQueue *this, DWORD, void *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *pvargDest, struct tagVARIANT *, struct tagVARIANT *, struct IMSMQMessage4 **)`
- caller_count: `11`
- callee_count: `9`
- tags: ``

## callers

- `0x18001b1d0`
- `0x18001b380`
- `0x18001b4f0`
- `0x18001b5b0`
- `0x18001b7f0`
- `0x18001b960`
- `0x18001baf0`
- `0x18001bca0`
- `0x18001bee0`
- `0x18001bfb0`
- `0x18001c370`

## callees

- `0x1800142a8`
- `0x180015038`
- `0x180016c54`
- `0x1800171f4`
- `0x18001ad30`
- `0x18001af00`
- `0x18001b2b4`
- `0x180026934`
- `0x180029010`

## import_xrefs

- `msvcrt!_snwscanf_s` at `0x18001b0a0`
- `msvcrt!_snwscanf_s` at `0x18001b0a0`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b075`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b075`
- `mqrt!MQReceiveMessage` at `0x18001b0e0`
- `mqrt!MQReceiveMessage` at `0x18001b0e0`
- `mqrt!MQReceiveMessageByLookupId` at `0x18001b060`
- `mqrt!MQReceiveMessageByLookupId` at `0x18001b060`

## pseudocode

```c

```
