# FastWppTraceMessage

- ea: `0x18001a154`
- end: `0x18001a2dd`
- name: `FastWppTraceMessage`
- size: `393`
- prototype: `ULONG(__int16, USHORT, ULONGLONG, ...)`
- caller_count: `166`
- callee_count: `3`
- tags: ``

## callers

- `0x180049008`
- `0x1800490b0`
- `0x180049168`
- `0x180049270`
- `0x1800492fc`
- `0x180049374`
- `0x180049404`
- `0x180049470`
- `0x1800494dc`
- `0x180049534`
- `0x180049588`
- `0x1800495e8`
- `0x180049654`
- `0x1800496f4`
- `0x180049750`
- `0x180049798`
- `0x1800497f0`
- `0x18004984c`
- `0x180049884`
- `0x1800498e4`
- `0x1800499b8`
- `0x180049a80`
- `0x180049ae8`
- `0x180049b44`
- `0x180049bac`
- `0x180049c24`
- `0x180049c98`
- `0x180049cf4`
- `0x180049d54`
- `0x180049de0`
- `0x180049e40`
- `0x180049eb8`
- `0x180049f54`
- `0x18004a010`
- `0x18004a09c`
- `0x18004a114`
- `0x18004a180`
- `0x18004a254`
- `0x18004a29c`
- `0x18004a310`
- `0x18004a364`
- `0x18004a450`
- `0x18004a4b0`
- `0x18004a51c`
- `0x18004a57c`
- `0x18004a5e8`
- `0x18004a63c`
- `0x18004a6a0`
- `0x18004a734`
- `0x18004a7e0`

## callees

- `0x18001a154`
- `0x18001cef0`
- `0x180022724`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a237`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a237`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a2bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a2bc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18001a29f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18001a29f`

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
0x18001a154  mov     [rsp-8+arg_10], r8
0x18001a159  mov     [rsp-8+arg_18], r9
0x18001a15e  push    rbp
0x18001a15f  push    rbx
0x18001a160  push    r14
0x18001a162  lea     rbp, [rsp-90h]
0x18001a16a  sub     rsp, 190h
0x18001a171  mov     rax, cs:__security_cookie
0x18001a178  xor     rax, rsp
0x18001a17b  mov     [rbp+0A0h+var_20], rax
0x18001a182  mov     eax, cs:FastWppInitState
0x18001a188  xorps   xmm1, xmm1
0x18001a18b  mov     [rsp+1A0h+var_160], 0
0x18001a194  xorps   xmm0, xmm0
0x18001a197  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Id], xmm0
0x18001a19c  movups  xmmword ptr [rsp+1A0h+var_148.Ptr], xmm1
0x18001a1a1  movups  xmmword ptr [rsp+1A0h+dwBytes], xmm1
0x18001a1a6  cmp     eax, 2
0x18001a1a9  jnz     loc_18001A2C2
0x18001a1af  movzx   eax, cx
0x18001a1b2  mov     [rsp+1A0h+EventDescriptor.Id], dx
0x18001a1b7  shr     ax, 8
0x18001a1bb  lea     r14, [rbp+0A0h+arg_18]
0x18001a1c2  mov     [rsp+1A0h+EventDescriptor.Level], al
0x18001a1c6  lea     r9, [rsp+1A0h+dwBytes+8]
0x18001a1cb  xor     ebx, ebx
0x18001a1cd  mov     byte ptr [rsp+1A0h+var_148.0Ch], 4
0x18001a1d2  mov     r8d, 100h
0x18001a1d8  mov     [rsp+1A0h+var_148.Size], 10h
0x18001a1e0  lea     rdx, [rbp+0A0h+var_120]
0x18001a1e4  mov     byte ptr [rsp+1A0h+dwBytes+0Ch], bl
0x18001a1e8  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18001a1f0  lea     eax, [rbx+1]
0x18001a1f3  shl     rax, cl
0x18001a1f6  mov     rcx, r14
0x18001a1f9  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x18001a1fe  mov     rax, [rbp+0A0h+arg_10]
0x18001a205  mov     [rsp+1A0h+var_148.Ptr], rax
0x18001a20a  lea     rax, [rbp+0A0h+var_120]
0x18001a20e  mov     [rsp+1A0h+dwBytes], rax
0x18001a213  call    FastWppPackEvent
0x18001a218  cmp     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18001a220  jbe     short loc_18001A269
0x18001a222  mov     rcx, gs:60h
0x18001a22b  lea     edx, [rbx+8]; dwFlags
0x18001a22e  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]; dwBytes
0x18001a233  mov     rcx, [rcx+30h]; hHeap
0x18001a237  call    cs:__imp_HeapAlloc
0x18001a23d  mov     rbx, rax
0x18001a240  test    rax, rax
0x18001a243  jz      short loc_18001A261
0x18001a245  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]
0x18001a24a  lea     r9, [rsp+1A0h+dwBytes+8]
0x18001a24f  mov     rdx, rax
0x18001a252  mov     [rsp+1A0h+dwBytes], rax
0x18001a257  mov     rcx, r14
0x18001a25a  call    FastWppPackEvent
0x18001a25f  jmp     short loc_18001A269
0x18001a261  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18001a269  mov     rcx, cs:FastWppRegHandle; RegHandle
0x18001a270  lea     rax, [rsp+1A0h+var_148]
0x18001a275  mov     [rsp+1A0h+UserData], rax; UserData
0x18001a27a  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x18001a27f  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x18001a287  xor     r9d, r9d; Flags
0x18001a28a  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x18001a293  xor     r8d, r8d; Filter
0x18001a296  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x18001a29f  call    cs:__imp_EventWriteEx
0x18001a2a5  test    rbx, rbx
0x18001a2a8  jz      short loc_18001A2C2
0x18001a2aa  mov     rcx, gs:60h
0x18001a2b3  mov     r8, rbx; lpMem
0x18001a2b6  xor     edx, edx; dwFlags
0x18001a2b8  mov     rcx, [rcx+30h]; hHeap
0x18001a2bc  call    cs:__imp_HeapFree
0x18001a2c2  mov     rcx, [rbp+0A0h+var_20]
0x18001a2c9  xor     rcx, rsp; StackCookie
0x18001a2cc  call    __security_check_cookie
0x18001a2d1  add     rsp, 190h
0x18001a2d8  pop     r14
0x18001a2da  pop     rbx
0x18001a2db  pop     rbp
0x18001a2dc  retn
```
