# FastWppTraceMessage

- ea: `0x18003ed24`
- end: `0x18003eead`
- name: `FastWppTraceMessage`
- size: `393`
- prototype: ``
- caller_count: `285`
- callee_count: `3`
- tags: ``

## callers

- `0x18007a008`
- `0x18007a0d8`
- `0x18007a184`
- `0x18007a2cc`
- `0x18007a354`
- `0x18007a3dc`
- `0x18007a470`
- `0x18007a4ec`
- `0x18007a57c`
- `0x18007a66c`
- `0x18007a6e8`
- `0x18007a760`
- `0x18007a7d0`
- `0x18007a83c`
- `0x18007a8a8`
- `0x18007a994`
- `0x18007aa5c`
- `0x18007ab28`
- `0x18007abf8`
- `0x18007acc0`
- `0x18007ad74`
- `0x18007ae2c`
- `0x18007aec8`
- `0x18007af64`
- `0x18007afe8`
- `0x18007b074`
- `0x18007b0bc`
- `0x18007b150`
- `0x18007b1cc`
- `0x18007b1fc`
- `0x18007b294`
- `0x18007b2f8`
- `0x18007b414`
- `0x18007b4a4`
- `0x18007b514`
- `0x18007b68c`
- `0x18007b76c`
- `0x18007b800`
- `0x18007ba50`
- `0x18007bb50`
- `0x18007bc48`
- `0x18007bcb4`
- `0x18007bda4`
- `0x18007be34`
- `0x18007bee0`
- `0x18007bf5c`
- `0x18007c108`
- `0x18007c1ec`
- `0x18007c350`
- `0x18007c3dc`

## callees

- `0x18003ed24`
- `0x180046ec0`
- `0x18005d644`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ee8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ee8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ee07`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ee07`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18003ee6f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18003ee6f`

## pseudocode

```c
ULONG FastWppTraceMessage(__int16 a1, USHORT a2, ULONGLONG a3, ...)
{
  ULONG result; // eax
  void *v4; // rbx
  LPVOID v5; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-A8h] BYREF
  SIZE_T dwBytes[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v9[256]; // [rsp+80h] [rbp-80h] BYREF
  va_list va; // [rsp+1C8h] [rbp+C8h] BYREF

  va_start(va, a3);
  result = FastWppInitState;
  EventDescriptor = 0;
  UserData = 0;
  *(_OWORD *)dwBytes = 0;
  if ( FastWppInitState == 2 )
  {
    EventDescriptor.Id = a2;
    EventDescriptor.Level = HIBYTE(a1);
    v4 = 0;
    UserData.Type = 4;
    UserData.Size = 16;
    BYTE4(dwBytes[1]) = 0;
    LODWORD(dwBytes[1]) = 256;
    EventDescriptor.Keyword = 1LL << a1;
    UserData.Ptr = a3;
    dwBytes[0] = (SIZE_T)v9;
    FastWppPackEvent((__int64 *)va, v9, 256, &dwBytes[1]);
    if ( LODWORD(dwBytes[1]) > 0x100 )
    {
      v5 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, LODWORD(dwBytes[1]));
      v4 = v5;
      if ( v5 )
      {
        dwBytes[0] = (SIZE_T)v5;
        FastWppPackEvent((__int64 *)va, v5, LODWORD(dwBytes[1]), &dwBytes[1]);
      }
      else
      {
        LODWORD(dwBytes[1]) = 256;
      }
    }
    result = EventWriteEx(FastWppRegHandle, &EventDescriptor, 0, 0, 0, 0, 2u, &UserData);
    if ( v4 )
      return HeapFree(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  return result;
}

```

## disassembly

```asm
0x18003ed24  mov     [rsp-8+arg_10], r8
0x18003ed29  mov     [rsp-8+arg_18], r9
0x18003ed2e  push    rbp
0x18003ed2f  push    rbx
0x18003ed30  push    r14
0x18003ed32  lea     rbp, [rsp-90h]
0x18003ed3a  sub     rsp, 190h
0x18003ed41  mov     rax, cs:__security_cookie
0x18003ed48  xor     rax, rsp
0x18003ed4b  mov     [rbp+0A0h+var_20], rax
0x18003ed52  mov     eax, cs:FastWppInitState
0x18003ed58  xorps   xmm1, xmm1
0x18003ed5b  mov     [rsp+1A0h+var_160], 0
0x18003ed64  xorps   xmm0, xmm0
0x18003ed67  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Id], xmm0
0x18003ed6c  movups  xmmword ptr [rsp+1A0h+var_148.Ptr], xmm1
0x18003ed71  movups  xmmword ptr [rsp+1A0h+dwBytes], xmm1
0x18003ed76  cmp     eax, 2
0x18003ed79  jnz     loc_18003EE92
0x18003ed7f  movzx   eax, cx
0x18003ed82  mov     [rsp+1A0h+EventDescriptor.Id], dx
0x18003ed87  shr     ax, 8
0x18003ed8b  lea     r14, [rbp+0A0h+arg_18]
0x18003ed92  mov     [rsp+1A0h+EventDescriptor.Level], al
0x18003ed96  lea     r9, [rsp+1A0h+dwBytes+8]
0x18003ed9b  xor     ebx, ebx
0x18003ed9d  mov     byte ptr [rsp+1A0h+var_148.0Ch], 4
0x18003eda2  mov     r8d, 100h
0x18003eda8  mov     [rsp+1A0h+var_148.Size], 10h
0x18003edb0  lea     rdx, [rbp+0A0h+var_120]
0x18003edb4  mov     byte ptr [rsp+1A0h+dwBytes+0Ch], bl
0x18003edb8  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18003edc0  lea     eax, [rbx+1]
0x18003edc3  shl     rax, cl
0x18003edc6  mov     rcx, r14
0x18003edc9  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x18003edce  mov     rax, [rbp+0A0h+arg_10]
0x18003edd5  mov     [rsp+1A0h+var_148.Ptr], rax
0x18003edda  lea     rax, [rbp+0A0h+var_120]
0x18003edde  mov     [rsp+1A0h+dwBytes], rax
0x18003ede3  call    FastWppPackEvent
0x18003ede8  cmp     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18003edf0  jbe     short loc_18003EE39
0x18003edf2  mov     rcx, gs:60h
0x18003edfb  lea     edx, [rbx+8]; dwFlags
0x18003edfe  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]; dwBytes
0x18003ee03  mov     rcx, [rcx+30h]; hHeap
0x18003ee07  call    cs:__imp_HeapAlloc
0x18003ee0d  mov     rbx, rax
0x18003ee10  test    rax, rax
0x18003ee13  jz      short loc_18003EE31
0x18003ee15  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]
0x18003ee1a  lea     r9, [rsp+1A0h+dwBytes+8]
0x18003ee1f  mov     rdx, rax
0x18003ee22  mov     [rsp+1A0h+dwBytes], rax
0x18003ee27  mov     rcx, r14
0x18003ee2a  call    FastWppPackEvent
0x18003ee2f  jmp     short loc_18003EE39
0x18003ee31  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18003ee39  mov     rcx, cs:FastWppRegHandle; RegHandle
0x18003ee40  lea     rax, [rsp+1A0h+var_148]
0x18003ee45  mov     [rsp+1A0h+UserData], rax; UserData
0x18003ee4a  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x18003ee4f  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x18003ee57  xor     r9d, r9d; Flags
0x18003ee5a  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x18003ee63  xor     r8d, r8d; Filter
0x18003ee66  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x18003ee6f  call    cs:__imp_EventWriteEx
0x18003ee75  test    rbx, rbx
0x18003ee78  jz      short loc_18003EE92
0x18003ee7a  mov     rcx, gs:60h
0x18003ee83  mov     r8, rbx; lpMem
0x18003ee86  xor     edx, edx; dwFlags
0x18003ee88  mov     rcx, [rcx+30h]; hHeap
0x18003ee8c  call    cs:__imp_HeapFree
0x18003ee92  mov     rcx, [rbp+0A0h+var_20]
0x18003ee99  xor     rcx, rsp; StackCookie
0x18003ee9c  call    __security_check_cookie
0x18003eea1  add     rsp, 190h
0x18003eea8  pop     r14
0x18003eeaa  pop     rbx
0x18003eeab  pop     rbp
0x18003eeac  retn
```
