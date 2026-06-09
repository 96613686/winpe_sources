# _tlgWriteTransfer_EventWriteTransfer(x,x,x,x,x,x)

- ea: `0x10005fa8`
- end: `0x1000603d`
- name: `__tlgWriteTransfer_EventWriteTransfer@24`
- size: `149`
- prototype: `int __stdcall(int, int, LPCGUID ActivityId, LPCGUID RelatedActivityId, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x10006043`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x10006032`
- `ADVAPI32!EventWriteTransfer` at `0x10006032`

## pseudocode

```c
ULONG __stdcall _tlgWriteTransfer_EventWriteTransfer(
        int a1,
        unsigned __int8 *a2,
        LPCGUID ActivityId,
        LPCGUID RelatedActivityId,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  int v6; // ecx
  unsigned int v7; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [esp+4h] [ebp-14h] BYREF
  int v10; // [esp+14h] [ebp-4h]

  v6 = *(_DWORD *)(a2 + 7);
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  LODWORD(EventDescriptor.Keyword) = *(_DWORD *)(a2 + 3);
  v7 = *(_DWORD *)(a1 + 4);
  HIDWORD(EventDescriptor.Keyword) = v6;
  UserData->Ptr = v7;
  UserData->Size = **(unsigned __int16 **)(a1 + 4);
  UserData->Reserved = 2;
  LODWORD(UserData[1].Ptr) = a2 + 11;
  HIDWORD(UserData[1].Ptr) = 0;
  UserData[1].Size = *(unsigned __int16 *)(a2 + 11);
  UserData[1].Reserved = 1;
  v10 = &_TraceLoggingMetadataEnd - (const UINT8 *)&_TraceLoggingMetadata;
  return EventWriteTransfer(
           *(_QWORD *)(a1 + 24),
           &EventDescriptor,
           ActivityId,
           RelatedActivityId,
           UserDataCount,
           UserData);
}

```

## disassembly

```asm
0x10005fa8  mov     edi, edi
0x10005faa  push    ebp
0x10005fab  mov     ebp, esp
0x10005fad  sub     esp, 14h
0x10005fb0  mov     ecx, [ebp+arg_4]
0x10005fb3  push    esi
0x10005fb4  mov     esi, [ebp+arg_0]
0x10005fb7  movzx   eax, byte ptr [ecx]
0x10005fba  lea     edx, [ecx+1]
0x10005fbd  mov     ecx, [edx+6]
0x10005fc0  shl     eax, 18h
0x10005fc3  mov     dword ptr [ebp+EventDescriptor.Id], eax
0x10005fc6  movzx   eax, word ptr [edx]
0x10005fc9  mov     dword ptr [ebp+EventDescriptor.Level], eax
0x10005fcc  mov     eax, [edx+2]
0x10005fcf  add     edx, 0Ah
0x10005fd2  mov     dword ptr [ebp+EventDescriptor.Keyword], eax
0x10005fd5  mov     eax, [esi+4]
0x10005fd8  mov     dword ptr [ebp+EventDescriptor.Keyword+4], ecx
0x10005fdb  mov     ecx, [ebp+UserData]
0x10005fde  push    ecx; UserData
0x10005fdf  push    [ebp+UserDataCount]; UserDataCount
0x10005fe2  push    [ebp+RelatedActivityId]; RelatedActivityId
0x10005fe5  mov     [ecx], eax
0x10005fe7  push    [ebp+ActivityId]; ActivityId
0x10005fea  mov     dword ptr [ecx+4], 0
0x10005ff1  mov     eax, [esi+4]
0x10005ff4  movzx   eax, word ptr [eax]
0x10005ff7  mov     [ecx+8], eax
0x10005ffa  mov     dword ptr [ecx+0Ch], 2
0x10006001  mov     [ecx+10h], edx
0x10006004  mov     dword ptr [ecx+14h], 0
0x1000600b  movzx   eax, word ptr [edx]
0x1000600e  mov     [ecx+18h], eax
0x10006011  mov     eax, offset __TraceLoggingMetadataEnd
0x10006016  sub     eax, offset __TraceLoggingMetadata
0x1000601b  mov     dword ptr [ecx+1Ch], 1
0x10006022  mov     [ebp+var_4], eax
0x10006025  mov     eax, [ebp+var_4]
0x10006028  lea     eax, [ebp+EventDescriptor]
0x1000602b  push    eax; EventDescriptor
0x1000602c  push    dword ptr [esi+1Ch]
0x1000602f  push    dword ptr [esi+18h]; RegHandle
0x10006032  call    ds:__imp__EventWriteTransfer@28; EventWriteTransfer(x,x,x,x,x,x,x)
0x10006038  pop     esi
0x10006039  leave
0x1000603a  retn    18h
```
