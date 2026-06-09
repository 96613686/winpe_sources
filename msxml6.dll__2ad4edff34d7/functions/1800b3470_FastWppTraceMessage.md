# FastWppTraceMessage

- ea: `0x1800b3470`
- end: `0x1800b35f2`
- name: `FastWppTraceMessage`
- size: `386`
- prototype: `void(unsigned __int16 MessageLevelKeyword, unsigned __int16 MessageNumber, const _GUID *MessageGuid, ...)`
- caller_count: `71`
- callee_count: `3`
- tags: ``

## callers

- `0x180185008`
- `0x180185040`
- `0x180185090`
- `0x1801850e0`
- `0x180185118`
- `0x18018512c`
- `0x180185174`
- `0x1801851d8`
- `0x180185244`
- `0x18018530c`
- `0x180185410`
- `0x1801855cc`
- `0x1801857b4`
- `0x180185840`
- `0x1801858a8`
- `0x180185930`
- `0x180185988`
- `0x1801859d0`
- `0x180185a34`
- `0x180185a88`
- `0x180185af4`
- `0x180185b6c`
- `0x180185bf0`
- `0x180185c44`
- `0x180185cf8`
- `0x180185d8c`
- `0x180185dd0`
- `0x180185e30`
- `0x180185fc8`
- `0x180186018`
- `0x180186070`
- `0x1801860dc`
- `0x180186140`
- `0x1801861b4`
- `0x18018620c`
- `0x180186268`
- `0x1801862c4`
- `0x180186378`
- `0x18018641c`
- `0x18018647c`
- `0x180186534`
- `0x180186588`
- `0x1801865d8`
- `0x180186634`
- `0x180186684`
- `0x1801866f0`
- `0x180186774`
- `0x1801867e8`
- `0x1801868d8`
- `0x1801869dc`

## callees

- `0x1800b3470`
- `0x1800cada0`
- `0x1800d43d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b35d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b35d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b354c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b354c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x1800b35b4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x1800b35b4`

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
0x1800b3470  mov     [rsp-8+arg_10], MessageGuid
0x1800b3475  mov     qword ptr [rsp-8+arg_18], r9
0x1800b347a  push    rbp
0x1800b347b  push    rbx
0x1800b347c  push    r14
0x1800b347e  lea     rbp, [rsp-90h]
0x1800b3486  sub     rsp, 190h
0x1800b348d  mov     rax, cs:__security_cookie
0x1800b3494  xor     rax, rsp
0x1800b3497  mov     [rbp+0A0h+var_20], rax
0x1800b349e  xor     eax, eax
0x1800b34a0  xorps   xmm0, xmm0
0x1800b34a3  mov     qword ptr [rsp+1A0h+EventData.Size+10h], rax
0x1800b34a8  xorps   xmm1, xmm1
0x1800b34ab  mov     eax, cs:?FastWppInitState@@3W4_FAST_WPP_STATE@@C; _FAST_WPP_STATE volatile FastWppInitState
0x1800b34b1  movups  xmmword ptr [rsp+1A0h+Event.Id], xmm0
0x1800b34b6  movups  xmmword ptr [rsp+1A0h+EventData.Size], xmm1
0x1800b34bb  cmp     eax, 2
0x1800b34be  jnz     loc_1800B35D7
0x1800b34c4  movzx   eax, MessageLevelKeyword
0x1800b34c7  mov     [rsp+1A0h+Event.Id], MessageNumber
0x1800b34cc  shr     ax, 8
0x1800b34d0  lea     r14, [rbp+0A0h+arg_18]
0x1800b34d7  mov     [rsp+1A0h+Event.Level], al
0x1800b34db  lea     r9, [rsp+1A0h+EventData.Size+10h]; TraceMessageSize
0x1800b34e0  xor     ebx, ebx
0x1800b34e2  mov     byte ptr [rsp+1A0h+EventData.___u2], 4
0x1800b34e7  mov     r8d, 100h; TraceMessageBufferSize
0x1800b34ed  mov     [rsp+1A0h+EventData.Size], 10h
0x1800b34f5  lea     rdx, [rbp+0A0h+EventDataBuffer]; TraceMessageBuffer
0x1800b34f9  mov     byte ptr [rsp+1A0h+EventData.___u2+10h], bl
0x1800b34fd  mov     [rsp+1A0h+EventData.Size+10h], 100h
0x1800b3505  lea     eax, [rbx+1]
0x1800b3508  shl     rax, cl
0x1800b350b  mov     rcx, r14; Arguments
0x1800b350e  mov     [rsp+1A0h+Event.Keyword], rax
0x1800b3513  mov     rax, [rbp+0A0h+arg_10]
0x1800b351a  mov     [rsp+1A0h+EventData.Ptr], rax
0x1800b351f  lea     rax, [rbp+0A0h+EventDataBuffer]
0x1800b3523  mov     [rsp+1A0h+EventData.Ptr+10h], rax
0x1800b3528  call    FastWppPackEvent
0x1800b352d  cmp     [rsp+1A0h+EventData.Size+10h], 100h
0x1800b3535  jbe     short loc_1800B357E
0x1800b3537  mov     rcx, gs:60h
0x1800b3540  lea     edx, [rbx+8]; dwFlags
0x1800b3543  mov     r8d, [rsp+1A0h+EventData.Size+10h]; dwBytes
0x1800b3548  mov     rcx, [rcx+30h]; hHeap
0x1800b354c  call    cs:__imp_HeapAlloc
0x1800b3552  mov     rbx, rax
0x1800b3555  test    rax, rax
0x1800b3558  jz      short loc_1800B3576
0x1800b355a  mov     r8d, [rsp+1A0h+EventData.Size+10h]; TraceMessageBufferSize
0x1800b355f  lea     r9, [rsp+1A0h+EventData.Size+10h]; TraceMessageSize
0x1800b3564  mov     rdx, rax; TraceMessageBuffer
0x1800b3567  mov     [rsp+1A0h+EventData.Ptr+10h], rax
0x1800b356c  mov     rcx, r14; Arguments
0x1800b356f  call    FastWppPackEvent
0x1800b3574  jmp     short loc_1800B357E
0x1800b3576  mov     [rsp+1A0h+EventData.Size+10h], 100h
0x1800b357e  mov     rcx, cs:?FastWppRegHandle@@3_KA; RegHandle
0x1800b3585  lea     rax, [rsp+1A0h+EventData]
0x1800b358a  mov     [rsp+1A0h+UserData], rax; UserData
0x1800b358f  lea     rdx, [rsp+1A0h+Event]; EventDescriptor
0x1800b3594  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x1800b359c  xor     r9d, r9d; Flags
0x1800b359f  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x1800b35a8  xor     r8d, r8d; Filter
0x1800b35ab  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x1800b35b4  call    cs:__imp_EventWriteEx
0x1800b35ba  test    rbx, rbx
0x1800b35bd  jz      short loc_1800B35D7
0x1800b35bf  mov     rcx, gs:60h
0x1800b35c8  mov     MessageGuid, rbx; lpMem
0x1800b35cb  xor     edx, edx; dwFlags
0x1800b35cd  mov     rcx, [rcx+30h]; hHeap
0x1800b35d1  call    cs:__imp_HeapFree
0x1800b35d7  mov     rcx, [rbp+0A0h+var_20]
0x1800b35de  xor     rcx, rsp; StackCookie
0x1800b35e1  call    __security_check_cookie
0x1800b35e6  add     rsp, 190h
0x1800b35ed  pop     r14
0x1800b35ef  pop     rbx
0x1800b35f0  pop     rbp
0x1800b35f1  retn
```
