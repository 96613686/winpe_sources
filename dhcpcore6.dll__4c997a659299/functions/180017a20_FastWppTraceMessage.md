# FastWppTraceMessage

- ea: `0x180017a20`
- end: `0x180017bbc`
- name: `FastWppTraceMessage`
- size: `412`
- prototype: ``
- caller_count: `108`
- callee_count: `3`
- tags: ``

## callers

- `0x180031008`
- `0x180031040`
- `0x1800310e4`
- `0x180031170`
- `0x1800311c4`
- `0x18003120c`
- `0x18003130c`
- `0x180031628`
- `0x180031694`
- `0x1800316f8`
- `0x18003176c`
- `0x180031820`
- `0x1800318c8`
- `0x180031920`
- `0x180031a24`
- `0x180031a8c`
- `0x180031ae8`
- `0x180031b48`
- `0x180031bb8`
- `0x180031c1c`
- `0x180031c54`
- `0x180031d08`
- `0x180031d64`
- `0x180031dcc`
- `0x180031e24`
- `0x180031ee4`
- `0x180031f44`
- `0x180031fa4`
- `0x180031ff0`
- `0x18003205c`
- `0x1800320f0`
- `0x180032184`
- `0x1800321ec`
- `0x180032254`
- `0x1800322c0`
- `0x18003232c`
- `0x1800323c0`
- `0x180032460`
- `0x180032520`
- `0x1800325cc`
- `0x18003261c`
- `0x180032688`
- `0x1800326e4`
- `0x180032740`
- `0x18003280c`
- `0x1800328c4`
- `0x180032994`
- `0x180032a24`
- `0x180032ab8`
- `0x180032afc`

## callees

- `0x180017a20`
- `0x180019ad0`
- `0x18001c698`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017b03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017b03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017b94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017b94`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180017b71`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180017b71`

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
0x180017a20  mov     [rsp-8+arg_10], r8
0x180017a25  mov     [rsp-8+arg_18], r9
0x180017a2a  push    rbp
0x180017a2b  push    rbx
0x180017a2c  push    r14
0x180017a2e  lea     rbp, [rsp-90h]
0x180017a36  sub     rsp, 190h
0x180017a3d  mov     rax, cs:__security_cookie
0x180017a44  xor     rax, rsp
0x180017a47  mov     [rbp+0A0h+var_20], rax
0x180017a4e  mov     eax, cs:FastWppInitState
0x180017a54  xorps   xmm1, xmm1
0x180017a57  mov     [rsp+1A0h+var_160], 0
0x180017a60  xorps   xmm0, xmm0
0x180017a63  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Id], xmm0
0x180017a68  movups  xmmword ptr [rsp+1A0h+var_148.Ptr], xmm1
0x180017a6d  movups  xmmword ptr [rsp+1A0h+dwBytes], xmm1
0x180017a72  cmp     eax, 2
0x180017a75  jnz     loc_180017BA0
0x180017a7b  movzx   eax, cx
0x180017a7e  mov     [rsp+1A0h+EventDescriptor.Id], dx
0x180017a83  shr     ax, 8
0x180017a87  lea     r14, [rbp+0A0h+arg_18]
0x180017a8e  mov     [rsp+1A0h+EventDescriptor.Level], al
0x180017a92  lea     r9, [rsp+1A0h+dwBytes+8]
0x180017a97  xor     ebx, ebx
0x180017a99  mov     byte ptr [rsp+1A0h+var_148.0Ch], 4
0x180017a9e  mov     r8d, 100h
0x180017aa4  mov     [rsp+1A0h+var_148.Size], 10h
0x180017aac  lea     rdx, [rbp+0A0h+var_120]
0x180017ab0  mov     byte ptr [rsp+1A0h+dwBytes+0Ch], bl
0x180017ab4  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x180017abc  lea     eax, [rbx+1]
0x180017abf  shl     rax, cl
0x180017ac2  mov     rcx, r14
0x180017ac5  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x180017aca  mov     rax, [rbp+0A0h+arg_10]
0x180017ad1  mov     [rsp+1A0h+var_148.Ptr], rax
0x180017ad6  lea     rax, [rbp+0A0h+var_120]
0x180017ada  mov     [rsp+1A0h+dwBytes], rax
0x180017adf  call    FastWppPackEvent
0x180017ae4  cmp     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x180017aec  jbe     short loc_180017B3B
0x180017aee  mov     rcx, gs:60h
0x180017af7  lea     edx, [rbx+8]; dwFlags
0x180017afa  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]; dwBytes
0x180017aff  mov     rcx, [rcx+30h]; hHeap
0x180017b03  call    cs:__imp_HeapAlloc
0x180017b0a  nop     dword ptr [rax+rax+00h]
0x180017b0f  mov     rbx, rax
0x180017b12  test    rax, rax
0x180017b15  jz      short loc_180017B33
0x180017b17  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]
0x180017b1c  lea     r9, [rsp+1A0h+dwBytes+8]
0x180017b21  mov     rdx, rax
0x180017b24  mov     [rsp+1A0h+dwBytes], rax
0x180017b29  mov     rcx, r14
0x180017b2c  call    FastWppPackEvent
0x180017b31  jmp     short loc_180017B3B
0x180017b33  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x180017b3b  mov     rcx, cs:FastWppRegHandle; RegHandle
0x180017b42  lea     rax, [rsp+1A0h+var_148]
0x180017b47  mov     [rsp+1A0h+UserData], rax; UserData
0x180017b4c  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x180017b51  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x180017b59  xor     r9d, r9d; Flags
0x180017b5c  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x180017b65  xor     r8d, r8d; Filter
0x180017b68  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x180017b71  call    cs:__imp_EventWriteEx
0x180017b78  nop     dword ptr [rax+rax+00h]
0x180017b7d  test    rbx, rbx
0x180017b80  jz      short loc_180017BA0
0x180017b82  mov     rcx, gs:60h
0x180017b8b  mov     r8, rbx; lpMem
0x180017b8e  xor     edx, edx; dwFlags
0x180017b90  mov     rcx, [rcx+30h]; hHeap
0x180017b94  call    cs:__imp_HeapFree
0x180017b9b  nop     dword ptr [rax+rax+00h]
0x180017ba0  mov     rcx, [rbp+0A0h+var_20]
0x180017ba7  xor     rcx, rsp; StackCookie
0x180017baa  call    __security_check_cookie
0x180017baf  add     rsp, 190h
0x180017bb6  pop     r14
0x180017bb8  pop     rbx
0x180017bb9  pop     rbp
0x180017bba  retn
```
