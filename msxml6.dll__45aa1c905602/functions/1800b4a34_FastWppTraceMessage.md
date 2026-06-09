# FastWppTraceMessage

- ea: `0x1800b4a34`
- end: `0x1800b4bc9`
- name: `FastWppTraceMessage`
- size: `405`
- prototype: `void(unsigned __int16 MessageLevelKeyword, unsigned __int16 MessageNumber, const _GUID *MessageGuid, ...)`
- caller_count: `71`
- callee_count: `3`
- tags: ``

## callers

- `0x180189008`
- `0x180189040`
- `0x180189090`
- `0x1801890e0`
- `0x180189118`
- `0x18018912c`
- `0x180189178`
- `0x1801891e0`
- `0x18018924c`
- `0x180189314`
- `0x18018941c`
- `0x1801895d8`
- `0x1801897c0`
- `0x18018984c`
- `0x1801898b4`
- `0x18018993c`
- `0x180189994`
- `0x1801899dc`
- `0x180189a40`
- `0x180189a94`
- `0x180189b00`
- `0x180189b78`
- `0x180189bfc`
- `0x180189c50`
- `0x180189d04`
- `0x180189d98`
- `0x180189ddc`
- `0x180189e3c`
- `0x180189fd8`
- `0x18018a028`
- `0x18018a080`
- `0x18018a0ec`
- `0x18018a154`
- `0x18018a1c8`
- `0x18018a224`
- `0x18018a280`
- `0x18018a2dc`
- `0x18018a390`
- `0x18018a438`
- `0x18018a498`
- `0x18018a554`
- `0x18018a5a8`
- `0x18018a5f8`
- `0x18018a654`
- `0x18018a6a8`
- `0x18018a714`
- `0x18018a798`
- `0x18018a810`
- `0x18018a900`
- `0x18018aa08`

## callees

- `0x1800b4a34`
- `0x1800cc6c0`
- `0x1800d601c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b4ba1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b4ba1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4b10`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b4b10`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x1800b4b7e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x1800b4b7e`

## pseudocode

```c
void FastWppTraceMessage(
        unsigned __int16 MessageLevelKeyword,
        unsigned __int16 MessageNumber,
        const _GUID *MessageGuid,
        ...)
{
  unsigned __int8 *v3; // rbx
  unsigned __int8 *v4; // rax
  _EVENT_DESCRIPTOR Event; // [rsp+48h] [rbp-B8h] BYREF
  _EVENT_DATA_DESCRIPTOR EventData[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 EventDataBuffer[256]; // [rsp+80h] [rbp-80h] BYREF
  va_list va; // [rsp+1C8h] [rbp+C8h] BYREF

  va_start(va, MessageGuid);
  *(_QWORD *)&EventData[1].Size = 0;
  Event = 0;
  *(_OWORD *)&EventData[0].Size = 0;
  if ( FastWppInitState == FastWppStateInitialized )
  {
    Event.Id = MessageNumber;
    Event.Level = HIBYTE(MessageLevelKeyword);
    v3 = 0;
    EventData[0].Type = 4;
    EventData[0].Size = 16;
    EventData[1].Type = 0;
    EventData[1].Size = 256;
    Event.Keyword = 1LL << MessageLevelKeyword;
    EventData[0].Ptr = (unsigned __int64)MessageGuid;
    EventData[1].Ptr = (unsigned __int64)EventDataBuffer;
    FastWppPackEvent(va, EventDataBuffer, 0x100u, &EventData[1].Size);
    if ( EventData[1].Size > 0x100 )
    {
      v4 = (unsigned __int8 *)HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, EventData[1].Size);
      v3 = v4;
      if ( v4 )
      {
        EventData[1].Ptr = (unsigned __int64)v4;
        FastWppPackEvent(va, v4, EventData[1].Size, &EventData[1].Size);
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
0x1800b4a34  mov     [rsp-8+arg_10], MessageGuid
0x1800b4a39  mov     qword ptr [rsp-8+arg_18], r9
0x1800b4a3e  push    rbp
0x1800b4a3f  push    rbx
0x1800b4a40  push    r14
0x1800b4a42  lea     rbp, [rsp-90h]
0x1800b4a4a  sub     rsp, 190h
0x1800b4a51  mov     rax, cs:__security_cookie
0x1800b4a58  xor     rax, rsp
0x1800b4a5b  mov     [rbp+0A0h+var_20], rax
0x1800b4a62  xor     eax, eax
0x1800b4a64  xorps   xmm0, xmm0
0x1800b4a67  mov     qword ptr [rsp+1A0h+EventData.Size+10h], rax
0x1800b4a6c  xorps   xmm1, xmm1
0x1800b4a6f  mov     eax, cs:?FastWppInitState@@3W4_FAST_WPP_STATE@@C; _FAST_WPP_STATE volatile FastWppInitState
0x1800b4a75  movups  xmmword ptr [rsp+1A0h+Event.Id], xmm0
0x1800b4a7a  movups  xmmword ptr [rsp+1A0h+EventData.Size], xmm1
0x1800b4a7f  cmp     eax, 2
0x1800b4a82  jnz     loc_1800B4BAD
0x1800b4a88  movzx   eax, MessageLevelKeyword
0x1800b4a8b  mov     [rsp+1A0h+Event.Id], MessageNumber
0x1800b4a90  shr     ax, 8
0x1800b4a94  lea     r14, [rbp+0A0h+arg_18]
0x1800b4a9b  mov     [rsp+1A0h+Event.Level], al
0x1800b4a9f  lea     r9, [rsp+1A0h+EventData.Size+10h]; TraceMessageSize
0x1800b4aa4  xor     ebx, ebx
0x1800b4aa6  mov     byte ptr [rsp+1A0h+EventData.___u2], 4
0x1800b4aab  mov     r8d, 100h; TraceMessageBufferSize
0x1800b4ab1  mov     [rsp+1A0h+EventData.Size], 10h
0x1800b4ab9  lea     rdx, [rbp+0A0h+EventDataBuffer]; TraceMessageBuffer
0x1800b4abd  mov     byte ptr [rsp+1A0h+EventData.___u2+10h], bl
0x1800b4ac1  mov     [rsp+1A0h+EventData.Size+10h], 100h
0x1800b4ac9  lea     eax, [rbx+1]
0x1800b4acc  shl     rax, cl
0x1800b4acf  mov     rcx, r14; Arguments
0x1800b4ad2  mov     [rsp+1A0h+Event.Keyword], rax
0x1800b4ad7  mov     rax, [rbp+0A0h+arg_10]
0x1800b4ade  mov     [rsp+1A0h+EventData.Ptr], rax
0x1800b4ae3  lea     rax, [rbp+0A0h+EventDataBuffer]
0x1800b4ae7  mov     [rsp+1A0h+EventData.Ptr+10h], rax
0x1800b4aec  call    FastWppPackEvent
0x1800b4af1  cmp     [rsp+1A0h+EventData.Size+10h], 100h
0x1800b4af9  jbe     short loc_1800B4B48
0x1800b4afb  mov     rcx, gs:60h
0x1800b4b04  lea     edx, [rbx+8]; dwFlags
0x1800b4b07  mov     r8d, [rsp+1A0h+EventData.Size+10h]; dwBytes
0x1800b4b0c  mov     rcx, [rcx+30h]; hHeap
0x1800b4b10  call    cs:__imp_HeapAlloc
0x1800b4b17  nop     dword ptr [rax+rax+00h]
0x1800b4b1c  mov     rbx, rax
0x1800b4b1f  test    rax, rax
0x1800b4b22  jz      short loc_1800B4B40
0x1800b4b24  mov     r8d, [rsp+1A0h+EventData.Size+10h]; TraceMessageBufferSize
0x1800b4b29  lea     r9, [rsp+1A0h+EventData.Size+10h]; TraceMessageSize
0x1800b4b2e  mov     rdx, rax; TraceMessageBuffer
0x1800b4b31  mov     [rsp+1A0h+EventData.Ptr+10h], rax
0x1800b4b36  mov     rcx, r14; Arguments
0x1800b4b39  call    FastWppPackEvent
0x1800b4b3e  jmp     short loc_1800B4B48
0x1800b4b40  mov     [rsp+1A0h+EventData.Size+10h], 100h
0x1800b4b48  mov     rcx, cs:?FastWppRegHandle@@3_KA; RegHandle
0x1800b4b4f  lea     rax, [rsp+1A0h+EventData]
0x1800b4b54  mov     [rsp+1A0h+UserData], rax; UserData
0x1800b4b59  lea     rdx, [rsp+1A0h+Event]; EventDescriptor
0x1800b4b5e  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x1800b4b66  xor     r9d, r9d; Flags
0x1800b4b69  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x1800b4b72  xor     r8d, r8d; Filter
0x1800b4b75  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x1800b4b7e  call    cs:__imp_EventWriteEx
0x1800b4b85  nop     dword ptr [rax+rax+00h]
0x1800b4b8a  test    rbx, rbx
0x1800b4b8d  jz      short loc_1800B4BAD
0x1800b4b8f  mov     rcx, gs:60h
0x1800b4b98  mov     MessageGuid, rbx; lpMem
0x1800b4b9b  xor     edx, edx; dwFlags
0x1800b4b9d  mov     rcx, [rcx+30h]; hHeap
0x1800b4ba1  call    cs:__imp_HeapFree
0x1800b4ba8  nop     dword ptr [rax+rax+00h]
0x1800b4bad  mov     rcx, [rbp+0A0h+var_20]
0x1800b4bb4  xor     rcx, rsp; StackCookie
0x1800b4bb7  call    __security_check_cookie
0x1800b4bbc  add     rsp, 190h
0x1800b4bc3  pop     r14
0x1800b4bc5  pop     rbx
0x1800b4bc6  pop     rbp
0x1800b4bc7  retn
```
