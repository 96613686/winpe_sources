# _FastWppTraceMessage

- ea: `0x10074a75`
- end: `0x10074be4`
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

- `0x1006b470`
- `0x10074a08`
- `0x10074a75`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10074bcf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10074bcf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10074b62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10074b62`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x10074bba`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x10074bba`

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
0x10074a75  mov     edi, edi
0x10074a77  push    ebp
0x10074a78  mov     ebp, esp
0x10074a7a  sub     esp, 140h
0x10074a80  mov     eax, ___security_cookie
0x10074a85  xor     eax, ebp
0x10074a87  mov     [ebp+var_8], eax
0x10074a8a  push    ebx
0x10074a8b  push    esi
0x10074a8c  push    edi
0x10074a8d  xor     eax, eax
0x10074a8f  lea     edi, [ebp+Event]
0x10074a95  stosd
0x10074a96  xor     ebx, ebx
0x10074a98  push    6
0x10074a9a  pop     ecx
0x10074a9b  mov     esi, ebx
0x10074a9d  stosd
0x10074a9e  stosd
0x10074a9f  stosd
0x10074aa0  xor     eax, eax
0x10074aa2  cmp     ?FastWppInitState@@3W4_FAST_WPP_STATE@@C, 2; _FAST_WPP_STATE volatile FastWppInitState
0x10074aa9  lea     edi, [ebp+EventData.Size]
0x10074aaf  rep stosd
0x10074ab1  jnz     loc_10074BD5
0x10074ab7  mov     ax, [ebp+MessageNumber]
0x10074abb  mov     edi, 100h
0x10074ac0  mov     ecx, [ebp+MessageLevelKeyword]
0x10074ac3  mov     [ebp+Event.Id], ax
0x10074aca  mov     eax, ecx
0x10074acc  shr     eax, 8
0x10074acf  movzx   edx, cl
0x10074ad2  xor     ecx, ecx
0x10074ad4  mov     [ebp+Event.Level], al
0x10074ada  add     edx, ebx
0x10074adc  xor     eax, eax
0x10074ade  mov     byte ptr [ebp+EventData.___u2], 4
0x10074ae5  bts     eax, edx
0x10074ae8  mov     dword ptr [ebp+EventData.Ptr+4], ebx
0x10074aee  cmp     edx, 20h ; ' '
0x10074af1  mov     [ebp+EventData.Size], 10h
0x10074afb  mov     byte ptr [ebp+EventData.___u2+10h], bl
0x10074b01  cmovnb  ecx, eax
0x10074b04  mov     dword ptr [ebp+EventData.Ptr+14h], ebx
0x10074b0a  xor     eax, ecx
0x10074b0c  mov     [ebp+EventData.Size+10h], edi
0x10074b12  cmp     edx, 40h ; '@'
0x10074b15  mov     dword ptr [ebp+Event.Keyword], eax
0x10074b1b  lea     edx, [ebp+EventDataBuffer]; TraceMessageBuffer
0x10074b21  cmovnb  ecx, eax
0x10074b24  mov     dword ptr [ebp+EventData.Ptr+10h], edx
0x10074b2a  mov     eax, [ebp+MessageGuid]
0x10074b2d  mov     dword ptr [ebp+EventData.Ptr], eax
0x10074b33  lea     eax, [ebp+EventData.Size+10h]
0x10074b39  push    eax; TraceMessageSize
0x10074b3a  mov     dword ptr [ebp+Event.Keyword+4], ecx
0x10074b40  lea     ecx, [ebp+Arguments]; Arguments
0x10074b43  push    edi; TraceMessageBufferSize
0x10074b44  call    _FastWppPackEvent@16; FastWppPackEvent(x,x,x,x)
0x10074b49  cmp     [ebp+EventData.Size+10h], edi
0x10074b4f  jbe     short loc_10074B99
0x10074b51  push    [ebp+EventData.Size+10h]; dwBytes
0x10074b57  mov     eax, large fs:30h
0x10074b5d  push    8; dwFlags
0x10074b5f  push    dword ptr [eax+18h]; hHeap
0x10074b62  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x10074b68  mov     esi, eax
0x10074b6a  test    esi, esi
0x10074b6c  jz      short loc_10074B93
0x10074b6e  lea     eax, [ebp+EventData.Size+10h]
0x10074b74  mov     dword ptr [ebp+EventData.Ptr+10h], esi
0x10074b7a  push    eax; TraceMessageSize
0x10074b7b  push    [ebp+EventData.Size+10h]; TraceMessageBufferSize
0x10074b81  mov     edx, esi; TraceMessageBuffer
0x10074b83  mov     dword ptr [ebp+EventData.Ptr+14h], ebx
0x10074b89  lea     ecx, [ebp+Arguments]; Arguments
0x10074b8c  call    _FastWppPackEvent@16; FastWppPackEvent(x,x,x,x)
0x10074b91  jmp     short loc_10074B99
0x10074b93  mov     [ebp+EventData.Size+10h], edi
0x10074b99  lea     eax, [ebp+EventData]
0x10074b9f  push    eax; UserData
0x10074ba0  push    2; UserDataCount
0x10074ba2  push    ebx; RelatedActivityId
0x10074ba3  push    ebx; ActivityId
0x10074ba4  push    ebx; Flags
0x10074ba5  push    ebx
0x10074ba6  push    ebx; Filter
0x10074ba7  lea     eax, [ebp+Event]
0x10074bad  push    eax; EventDescriptor
0x10074bae  push    dword ptr ?FastWppRegHandle@@3_KA+4; unsigned __int64 FastWppRegHandle
0x10074bb4  push    dword ptr ?FastWppRegHandle@@3_KA; RegHandle
0x10074bba  call    ds:__imp__EventWriteEx@40; EventWriteEx(x,x,x,x,x,x,x,x,x,x)
0x10074bc0  test    esi, esi
0x10074bc2  jz      short loc_10074BD5
0x10074bc4  mov     eax, large fs:30h
0x10074bca  push    esi; lpMem
0x10074bcb  push    ebx; dwFlags
0x10074bcc  push    dword ptr [eax+18h]; hHeap
0x10074bcf  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10074bd5  mov     ecx, [ebp+var_8]
0x10074bd8  pop     edi
0x10074bd9  pop     esi
0x10074bda  xor     ecx, ebp; cookie
0x10074bdc  pop     ebx
0x10074bdd  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10074be2  leave
0x10074be3  retn
```
