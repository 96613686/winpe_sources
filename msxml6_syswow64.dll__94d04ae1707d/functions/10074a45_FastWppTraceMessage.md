# _FastWppTraceMessage

- ea: `0x10074a45`
- end: `0x10074bb4`
- name: `_FastWppTraceMessage`
- size: `367`
- prototype: `void(unsigned __int16 MessageLevelKeyword, unsigned __int16 MessageNumber, const _GUID *MessageGuid, ...)`
- caller_count: `69`
- callee_count: `3`
- tags: ``

## callers

- `0x10180006`
- `0x1018002a`
- `0x10180060`
- `0x10180080`
- `0x101800b3`
- `0x101800e9`
- `0x10180125`
- `0x101801c6`
- `0x1018027f`
- `0x101803ae`
- `0x10180543`
- `0x101805ae`
- `0x101805e2`
- `0x10180623`
- `0x10180652`
- `0x1018067c`
- `0x101806b8`
- `0x101806e8`
- `0x10180724`
- `0x10180765`
- `0x101807a1`
- `0x10180813`
- `0x10180854`
- `0x10180880`
- `0x101808bc`
- `0x101809e7`
- `0x10180a46`
- `0x10180a84`
- `0x10180abe`
- `0x10180b02`
- `0x10180b36`
- `0x10180b6f`
- `0x10180b95`
- `0x10180bce`
- `0x10180c07`
- `0x10180c5f`
- `0x10180cb4`
- `0x10180cee`
- `0x10180d90`
- `0x10180dc0`
- `0x10180df4`
- `0x10180e24`
- `0x10180e56`
- `0x10180e8d`
- `0x10180ec1`
- `0x10180efc`
- `0x10180f38`
- `0x10180f9d`
- `0x1018104b`
- `0x101810fb`

## callees

- `0x1006b510`
- `0x100749d8`
- `0x10074a45`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10074b9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10074b9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10074b32`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10074b32`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x10074b8a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x10074b8a`

## pseudocode

```c
void FastWppTraceMessage(
        unsigned __int16 MessageLevelKeyword,
        unsigned __int16 MessageNumber,
        const _GUID *MessageGuid,
        ...)
{
  unsigned __int8 *v3; // esi
  int v4; // ecx
  _EVENT_DESCRIPTOR Event; // [esp+10h] [ebp-13Ch] BYREF
  _EVENT_DATA_DESCRIPTOR EventData[2]; // [esp+20h] [ebp-12Ch] BYREF
  unsigned __int8 EventDataBuffer[260]; // [esp+40h] [ebp-10Ch] BYREF
  va_list Arguments; // [esp+160h] [ebp+14h] BYREF

  va_start(Arguments, MessageGuid);
  memset(&Event, 0, sizeof(Event));
  v3 = 0;
  memset(&EventData[0].Size, 0, 0x18u);
  if ( FastWppInitState == FastWppStateInitialized )
  {
    Event.Id = MessageNumber;
    v4 = 0;
    Event.Level = HIBYTE(MessageLevelKeyword);
    EventData[0].Type = 4;
    HIDWORD(EventData[0].Ptr) = 0;
    EventData[0].Size = 16;
    EventData[1].Type = 0;
    if ( (unsigned __int8)MessageLevelKeyword >= 0x20u )
      v4 = 1 << MessageLevelKeyword;
    HIDWORD(EventData[1].Ptr) = 0;
    EventData[1].Size = 256;
    LODWORD(Event.Keyword) = v4 ^ (1 << MessageLevelKeyword);
    if ( (unsigned __int8)MessageLevelKeyword >= 0x40u )
      v4 ^= 1 << MessageLevelKeyword;
    LODWORD(EventData[1].Ptr) = EventDataBuffer;
    LODWORD(EventData[0].Ptr) = MessageGuid;
    HIDWORD(Event.Keyword) = v4;
    FastWppPackEvent(Arguments, EventDataBuffer, 0x100u, &EventData[1].Size);
    if ( EventData[1].Size > 0x100 )
    {
      v3 = (unsigned __int8 *)HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, EventData[1].Size);
      if ( v3 )
      {
        EventData[1].Ptr = (unsigned int)v3;
        FastWppPackEvent(Arguments, v3, EventData[1].Size, &EventData[1].Size);
      }
      else
      {
        EventData[1].Size = 256;
      }
    }
    EventWriteEx(FastWppRegHandle, &Event, 0, 0, 0, 0, 2u, EventData);
    if ( v3 )
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v3);
  }
}

```

## disassembly

```asm
0x10074a45  mov     edi, edi
0x10074a47  push    ebp
0x10074a48  mov     ebp, esp
0x10074a4a  sub     esp, 140h
0x10074a50  mov     eax, ___security_cookie
0x10074a55  xor     eax, ebp
0x10074a57  mov     [ebp+var_8], eax
0x10074a5a  push    ebx
0x10074a5b  push    esi
0x10074a5c  push    edi
0x10074a5d  xor     eax, eax
0x10074a5f  lea     edi, [ebp+Event]
0x10074a65  stosd
0x10074a66  xor     ebx, ebx
0x10074a68  push    6
0x10074a6a  pop     ecx
0x10074a6b  mov     esi, ebx
0x10074a6d  stosd
0x10074a6e  stosd
0x10074a6f  stosd
0x10074a70  xor     eax, eax
0x10074a72  cmp     ?FastWppInitState@@3W4_FAST_WPP_STATE@@C, 2; _FAST_WPP_STATE volatile FastWppInitState
0x10074a79  lea     edi, [ebp+EventData.Size]
0x10074a7f  rep stosd
0x10074a81  jnz     loc_10074BA5
0x10074a87  mov     ax, [ebp+MessageNumber]
0x10074a8b  mov     edi, 100h
0x10074a90  mov     ecx, [ebp+MessageLevelKeyword]
0x10074a93  mov     [ebp+Event.Id], ax
0x10074a9a  mov     eax, ecx
0x10074a9c  shr     eax, 8
0x10074a9f  movzx   edx, cl
0x10074aa2  xor     ecx, ecx
0x10074aa4  mov     [ebp+Event.Level], al
0x10074aaa  add     edx, ebx
0x10074aac  xor     eax, eax
0x10074aae  mov     byte ptr [ebp+EventData.___u2], 4
0x10074ab5  bts     eax, edx
0x10074ab8  mov     dword ptr [ebp+EventData.Ptr+4], ebx
0x10074abe  cmp     edx, 20h ; ' '
0x10074ac1  mov     [ebp+EventData.Size], 10h
0x10074acb  mov     byte ptr [ebp+EventData.___u2+10h], bl
0x10074ad1  cmovnb  ecx, eax
0x10074ad4  mov     dword ptr [ebp+EventData.Ptr+14h], ebx
0x10074ada  xor     eax, ecx
0x10074adc  mov     [ebp+EventData.Size+10h], edi
0x10074ae2  cmp     edx, 40h ; '@'
0x10074ae5  mov     dword ptr [ebp+Event.Keyword], eax
0x10074aeb  lea     edx, [ebp+EventDataBuffer]; TraceMessageBuffer
0x10074af1  cmovnb  ecx, eax
0x10074af4  mov     dword ptr [ebp+EventData.Ptr+10h], edx
0x10074afa  mov     eax, [ebp+MessageGuid]
0x10074afd  mov     dword ptr [ebp+EventData.Ptr], eax
0x10074b03  lea     eax, [ebp+EventData.Size+10h]
0x10074b09  push    eax; TraceMessageSize
0x10074b0a  mov     dword ptr [ebp+Event.Keyword+4], ecx
0x10074b10  lea     ecx, [ebp+Arguments]; Arguments
0x10074b13  push    edi; TraceMessageBufferSize
0x10074b14  call    _FastWppPackEvent@16; FastWppPackEvent(x,x,x,x)
0x10074b19  cmp     [ebp+EventData.Size+10h], edi
0x10074b1f  jbe     short loc_10074B69
0x10074b21  push    [ebp+EventData.Size+10h]; dwBytes
0x10074b27  mov     eax, large fs:30h
0x10074b2d  push    8; dwFlags
0x10074b2f  push    dword ptr [eax+18h]; hHeap
0x10074b32  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x10074b38  mov     esi, eax
0x10074b3a  test    esi, esi
0x10074b3c  jz      short loc_10074B63
0x10074b3e  lea     eax, [ebp+EventData.Size+10h]
0x10074b44  mov     dword ptr [ebp+EventData.Ptr+10h], esi
0x10074b4a  push    eax; TraceMessageSize
0x10074b4b  push    [ebp+EventData.Size+10h]; TraceMessageBufferSize
0x10074b51  mov     edx, esi; TraceMessageBuffer
0x10074b53  mov     dword ptr [ebp+EventData.Ptr+14h], ebx
0x10074b59  lea     ecx, [ebp+Arguments]; Arguments
0x10074b5c  call    _FastWppPackEvent@16; FastWppPackEvent(x,x,x,x)
0x10074b61  jmp     short loc_10074B69
0x10074b63  mov     [ebp+EventData.Size+10h], edi
0x10074b69  lea     eax, [ebp+EventData]
0x10074b6f  push    eax; UserData
0x10074b70  push    2; UserDataCount
0x10074b72  push    ebx; RelatedActivityId
0x10074b73  push    ebx; ActivityId
0x10074b74  push    ebx; Flags
0x10074b75  push    ebx
0x10074b76  push    ebx; Filter
0x10074b77  lea     eax, [ebp+Event]
0x10074b7d  push    eax; EventDescriptor
0x10074b7e  push    dword ptr ?FastWppRegHandle@@3_KA+4; unsigned __int64 FastWppRegHandle
0x10074b84  push    dword ptr ?FastWppRegHandle@@3_KA; RegHandle
0x10074b8a  call    ds:__imp__EventWriteEx@40; EventWriteEx(x,x,x,x,x,x,x,x,x,x)
0x10074b90  test    esi, esi
0x10074b92  jz      short loc_10074BA5
0x10074b94  mov     eax, large fs:30h
0x10074b9a  push    esi; lpMem
0x10074b9b  push    ebx; dwFlags
0x10074b9c  push    dword ptr [eax+18h]; hHeap
0x10074b9f  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10074ba5  mov     ecx, [ebp+var_8]
0x10074ba8  pop     edi
0x10074ba9  pop     esi
0x10074baa  xor     ecx, ebp; cookie
0x10074bac  pop     ebx
0x10074bad  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10074bb2  leave
0x10074bb3  retn
```
