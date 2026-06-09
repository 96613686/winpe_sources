# _TlgWrite(x,x,x,x,x,x)

- ea: `0x10008c60`
- end: `0x10008cfa`
- name: `__TlgWrite@24`
- size: `154`
- prototype: `TLG_STATUS __stdcall(TraceLoggingHProvider hProvider, const void *pEventMetadata, LPCGUID pActivityId, LPCGUID pRelatedActivityId, UINT32 cData, EVENT_DATA_DESCRIPTOR *pData)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x10015000`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x10008ced`
- `ADVAPI32!EventWriteTransfer` at `0x10008ced`

## pseudocode

```c
TLG_STATUS __stdcall _TlgWrite(
        TraceLoggingHProvider hProvider,
        const void *pEventMetadata,
        LPCGUID pActivityId,
        LPCGUID pRelatedActivityId,
        UINT32 cData,
        EVENT_DATA_DESCRIPTOR *pData)
{
  EVENT_DESCRIPTOR EventDescriptor; // [esp+4h] [ebp-10h] BYREF

  *(_DWORD *)&EventDescriptor.Id = ((_BYTE *)pEventMetadata - (_BYTE *)&_TraceLoggingMetadata)
                                 | (*(unsigned __int8 *)pEventMetadata << 24);
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)((char *)pEventMetadata + 1);
  EventDescriptor.Keyword = *(_QWORD *)((char *)pEventMetadata + 3);
  pData->Ptr = *((unsigned int *)hProvider + 1);
  pData->Size = **((unsigned __int16 **)hProvider + 1);
  pData->Reserved = 2;
  LODWORD(pData[1].Ptr) = (char *)pEventMetadata + 11;
  HIDWORD(pData[1].Ptr) = 0;
  pData[1].Size = *(unsigned __int16 *)((char *)pEventMetadata + 11);
  pData[1].Reserved = 1;
  return EventWriteTransfer(*((_QWORD *)hProvider + 3), &EventDescriptor, pActivityId, pRelatedActivityId, cData, pData);
}

```

## disassembly

```asm
0x10008c60  sub     esp, 10h
0x10008c63  mov     al, ds:__TraceLoggingMetadataEnd
0x10008c68  mov     edx, [esp+10h+pEventMetadata]
0x10008c6c  mov     ecx, edx
0x10008c6e  push    esi
0x10008c6f  mov     esi, [esp+14h+hProvider]
0x10008c73  sub     ecx, offset __TraceLoggingMetadata
0x10008c79  movzx   eax, byte ptr [edx]
0x10008c7c  shl     eax, 18h
0x10008c7f  or      eax, ecx
0x10008c81  mov     ecx, [esp+14h+pData]
0x10008c85  mov     dword ptr [esp+14h+EventDescriptor.Id], eax
0x10008c89  movzx   eax, word ptr [edx+1]
0x10008c8d  mov     dword ptr [esp+14h+EventDescriptor.Level], eax
0x10008c91  mov     eax, [edx+3]
0x10008c94  mov     dword ptr [esp+14h+EventDescriptor.Keyword], eax
0x10008c98  mov     eax, [edx+7]
0x10008c9b  add     edx, 0Bh
0x10008c9e  mov     dword ptr [esp+14h+EventDescriptor.Keyword+4], eax
0x10008ca2  mov     eax, [esi+4]
0x10008ca5  mov     [ecx], eax
0x10008ca7  mov     dword ptr [ecx+4], 0
0x10008cae  mov     eax, [esi+4]
0x10008cb1  push    ecx; UserData
0x10008cb2  push    [esp+18h+cData]; UserDataCount
0x10008cb6  movzx   eax, word ptr [eax]
0x10008cb9  push    [esp+1Ch+pRelatedActivityId]; RelatedActivityId
0x10008cbd  mov     [ecx+8], eax
0x10008cc0  push    [esp+20h+pActivityId]; ActivityId
0x10008cc4  mov     dword ptr [ecx+0Ch], 2
0x10008ccb  mov     [ecx+10h], edx
0x10008cce  mov     dword ptr [ecx+14h], 0
0x10008cd5  movzx   eax, word ptr [edx]
0x10008cd8  mov     [ecx+18h], eax
0x10008cdb  lea     eax, [esp+24h+EventDescriptor]
0x10008cdf  push    eax; EventDescriptor
0x10008ce0  mov     dword ptr [ecx+1Ch], 1
0x10008ce7  push    dword ptr [esi+1Ch]
0x10008cea  push    dword ptr [esi+18h]; RegHandle
0x10008ced  call    ds:__imp__EventWriteTransfer@28; EventWriteTransfer(x,x,x,x,x,x,x)
0x10008cf3  pop     esi
0x10008cf4  add     esp, 10h
0x10008cf7  retn    18h
```
