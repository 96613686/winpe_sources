# FastWppTraceMessage

- ea: `0x180021264`
- end: `0x180021400`
- name: `FastWppTraceMessage`
- size: `412`
- prototype: ``
- caller_count: `91`
- callee_count: `3`
- tags: ``

## callers

- `0x180038008`
- `0x180038058`
- `0x1800380b0`
- `0x180038104`
- `0x180038118`
- `0x180038150`
- `0x1800381a0`
- `0x180038258`
- `0x1800382b8`
- `0x180038318`
- `0x180038384`
- `0x1800383fc`
- `0x18003847c`
- `0x1800384d4`
- `0x180038570`
- `0x1800385e4`
- `0x180038634`
- `0x18003868c`
- `0x180038718`
- `0x180038774`
- `0x1800387e8`
- `0x180038874`
- `0x1800388f4`
- `0x180038944`
- `0x180038988`
- `0x1800389d8`
- `0x180038a20`
- `0x180038a68`
- `0x180038ac8`
- `0x180038b18`
- `0x180038b88`
- `0x180038bdc`
- `0x180038c40`
- `0x180038c94`
- `0x180038cf4`
- `0x180038d60`
- `0x180038dc4`
- `0x180038e30`
- `0x180038ea4`
- `0x180038f00`
- `0x180038f54`
- `0x180038fb4`
- `0x180038ffc`
- `0x180039060`
- `0x1800390c8`
- `0x180039134`
- `0x1800391c4`
- `0x18003926c`
- `0x1800392cc`
- `0x18003932c`

## callees

- `0x180021264`
- `0x1800222f0`
- `0x18002fd00`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x1800213b5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x1800213b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021347`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021347`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800213d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800213d8`

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
0x180021264  mov     [rsp-8+arg_10], r8
0x180021269  mov     [rsp-8+arg_18], r9
0x18002126e  push    rbp
0x18002126f  push    rbx
0x180021270  push    r14
0x180021272  lea     rbp, [rsp-90h]
0x18002127a  sub     rsp, 190h
0x180021281  mov     rax, cs:__security_cookie
0x180021288  xor     rax, rsp
0x18002128b  mov     [rbp+0A0h+var_20], rax
0x180021292  mov     eax, cs:FastWppInitState
0x180021298  xorps   xmm1, xmm1
0x18002129b  mov     [rsp+1A0h+var_160], 0
0x1800212a4  xorps   xmm0, xmm0
0x1800212a7  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Id], xmm0
0x1800212ac  movups  xmmword ptr [rsp+1A0h+var_148.Ptr], xmm1
0x1800212b1  movups  xmmword ptr [rsp+1A0h+dwBytes], xmm1
0x1800212b6  cmp     eax, 2
0x1800212b9  jnz     loc_1800213E4
0x1800212bf  movzx   eax, cx
0x1800212c2  mov     [rsp+1A0h+EventDescriptor.Id], dx
0x1800212c7  shr     ax, 8
0x1800212cb  lea     r14, [rbp+0A0h+arg_18]
0x1800212d2  mov     [rsp+1A0h+EventDescriptor.Level], al
0x1800212d6  lea     r9, [rsp+1A0h+dwBytes+8]
0x1800212db  xor     ebx, ebx
0x1800212dd  mov     byte ptr [rsp+1A0h+var_148.0Ch], 4
0x1800212e2  mov     r8d, 100h
0x1800212e8  mov     [rsp+1A0h+var_148.Size], 10h
0x1800212f0  lea     rdx, [rbp+0A0h+var_120]
0x1800212f4  mov     byte ptr [rsp+1A0h+dwBytes+0Ch], bl
0x1800212f8  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x180021300  lea     eax, [rbx+1]
0x180021303  shl     rax, cl
0x180021306  mov     rcx, r14
0x180021309  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x18002130e  mov     rax, [rbp+0A0h+arg_10]
0x180021315  mov     [rsp+1A0h+var_148.Ptr], rax
0x18002131a  lea     rax, [rbp+0A0h+var_120]
0x18002131e  mov     [rsp+1A0h+dwBytes], rax
0x180021323  call    FastWppPackEvent
0x180021328  cmp     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x180021330  jbe     short loc_18002137F
0x180021332  mov     rcx, gs:60h
0x18002133b  lea     edx, [rbx+8]; dwFlags
0x18002133e  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]; dwBytes
0x180021343  mov     rcx, [rcx+30h]; hHeap
0x180021347  call    cs:__imp_HeapAlloc
0x18002134e  nop     dword ptr [rax+rax+00h]
0x180021353  mov     rbx, rax
0x180021356  test    rax, rax
0x180021359  jz      short loc_180021377
0x18002135b  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]
0x180021360  lea     r9, [rsp+1A0h+dwBytes+8]
0x180021365  mov     rdx, rax
0x180021368  mov     [rsp+1A0h+dwBytes], rax
0x18002136d  mov     rcx, r14
0x180021370  call    FastWppPackEvent
0x180021375  jmp     short loc_18002137F
0x180021377  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18002137f  mov     rcx, cs:FastWppRegHandle; RegHandle
0x180021386  lea     rax, [rsp+1A0h+var_148]
0x18002138b  mov     [rsp+1A0h+UserData], rax; UserData
0x180021390  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x180021395  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x18002139d  xor     r9d, r9d; Flags
0x1800213a0  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x1800213a9  xor     r8d, r8d; Filter
0x1800213ac  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x1800213b5  call    cs:__imp_EventWriteEx
0x1800213bc  nop     dword ptr [rax+rax+00h]
0x1800213c1  test    rbx, rbx
0x1800213c4  jz      short loc_1800213E4
0x1800213c6  mov     rcx, gs:60h
0x1800213cf  mov     r8, rbx; lpMem
0x1800213d2  xor     edx, edx; dwFlags
0x1800213d4  mov     rcx, [rcx+30h]; hHeap
0x1800213d8  call    cs:__imp_HeapFree
0x1800213df  nop     dword ptr [rax+rax+00h]
0x1800213e4  mov     rcx, [rbp+0A0h+var_20]
0x1800213eb  xor     rcx, rsp; StackCookie
0x1800213ee  call    __security_check_cookie
0x1800213f3  add     rsp, 190h
0x1800213fa  pop     r14
0x1800213fc  pop     rbx
0x1800213fd  pop     rbp
0x1800213fe  retn
```
