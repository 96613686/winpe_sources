# FastWppTraceMessage

- ea: `0x1800750c0`
- end: `0x18007525c`
- name: `FastWppTraceMessage`
- size: `412`
- prototype: ``
- caller_count: `456`
- callee_count: `3`
- tags: ``

## callers

- `0x1800cc008`
- `0x1800cc0d8`
- `0x1800cc1a8`
- `0x1800cc234`
- `0x1800cc2e4`
- `0x1800cc388`
- `0x1800cc48c`
- `0x1800cc528`
- `0x1800cc5bc`
- `0x1800cc5fc`
- `0x1800cc684`
- `0x1800cc70c`
- `0x1800cc790`
- `0x1800cc824`
- `0x1800cc8bc`
- `0x1800cc9d0`
- `0x1800cca4c`
- `0x1800ccac4`
- `0x1800ccb3c`
- `0x1800ccbbc`
- `0x1800ccc38`
- `0x1800cccb0`
- `0x1800ccdb0`
- `0x1800cce90`
- `0x1800ccf00`
- `0x1800cd010`
- `0x1800cd0e8`
- `0x1800cd158`
- `0x1800cd1c8`
- `0x1800cd238`
- `0x1800cd2a4`
- `0x1800cd388`
- `0x1800cd44c`
- `0x1800cd504`
- `0x1800cd5b4`
- `0x1800cd630`
- `0x1800cd6cc`
- `0x1800cd768`
- `0x1800cd7f4`
- `0x1800cd890`
- `0x1800cd924`
- `0x1800cd9b8`
- `0x1800cda48`
- `0x1800cdb14`
- `0x1800cdb90`
- `0x1800cdc20`
- `0x1800cdcb4`
- `0x1800cdd3c`
- `0x1800cddc4`
- `0x1800cde8c`

## callees

- `0x1800750c0`
- `0x180080af8`
- `0x18008b5f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180075234`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180075234`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800751a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800751a3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180075211`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180075211`

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
0x1800750c0  mov     [rsp-8+arg_10], r8
0x1800750c5  mov     [rsp-8+arg_18], r9
0x1800750ca  push    rbp
0x1800750cb  push    rbx
0x1800750cc  push    r14
0x1800750ce  lea     rbp, [rsp-90h]
0x1800750d6  sub     rsp, 190h
0x1800750dd  mov     rax, cs:__security_cookie
0x1800750e4  xor     rax, rsp
0x1800750e7  mov     [rbp+0A0h+var_20], rax
0x1800750ee  mov     eax, cs:FastWppInitState
0x1800750f4  xorps   xmm1, xmm1
0x1800750f7  mov     [rsp+1A0h+var_160], 0
0x180075100  xorps   xmm0, xmm0
0x180075103  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Id], xmm0
0x180075108  movups  xmmword ptr [rsp+1A0h+var_148.Ptr], xmm1
0x18007510d  movups  xmmword ptr [rsp+1A0h+dwBytes], xmm1
0x180075112  cmp     eax, 2
0x180075115  jnz     loc_180075240
0x18007511b  movzx   eax, cx
0x18007511e  mov     [rsp+1A0h+EventDescriptor.Id], dx
0x180075123  shr     ax, 8
0x180075127  lea     r14, [rbp+0A0h+arg_18]
0x18007512e  mov     [rsp+1A0h+EventDescriptor.Level], al
0x180075132  lea     r9, [rsp+1A0h+dwBytes+8]
0x180075137  xor     ebx, ebx
0x180075139  mov     byte ptr [rsp+1A0h+var_148.0Ch], 4
0x18007513e  mov     r8d, 100h
0x180075144  mov     [rsp+1A0h+var_148.Size], 10h
0x18007514c  lea     rdx, [rbp+0A0h+var_120]
0x180075150  mov     byte ptr [rsp+1A0h+dwBytes+0Ch], bl
0x180075154  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18007515c  lea     eax, [rbx+1]
0x18007515f  shl     rax, cl
0x180075162  mov     rcx, r14
0x180075165  mov     [rsp+1A0h+EventDescriptor.Keyword], rax
0x18007516a  mov     rax, [rbp+0A0h+arg_10]
0x180075171  mov     [rsp+1A0h+var_148.Ptr], rax
0x180075176  lea     rax, [rbp+0A0h+var_120]
0x18007517a  mov     [rsp+1A0h+dwBytes], rax
0x18007517f  call    FastWppPackEvent
0x180075184  cmp     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18007518c  jbe     short loc_1800751DB
0x18007518e  mov     rcx, gs:60h
0x180075197  lea     edx, [rbx+8]; dwFlags
0x18007519a  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]; dwBytes
0x18007519f  mov     rcx, [rcx+30h]; hHeap
0x1800751a3  call    cs:__imp_HeapAlloc
0x1800751aa  nop     dword ptr [rax+rax+00h]
0x1800751af  mov     rbx, rax
0x1800751b2  test    rax, rax
0x1800751b5  jz      short loc_1800751D3
0x1800751b7  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]
0x1800751bc  lea     r9, [rsp+1A0h+dwBytes+8]
0x1800751c1  mov     rdx, rax
0x1800751c4  mov     [rsp+1A0h+dwBytes], rax
0x1800751c9  mov     rcx, r14
0x1800751cc  call    FastWppPackEvent
0x1800751d1  jmp     short loc_1800751DB
0x1800751d3  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x1800751db  mov     rcx, cs:FastWppRegHandle; RegHandle
0x1800751e2  lea     rax, [rsp+1A0h+var_148]
0x1800751e7  mov     [rsp+1A0h+UserData], rax; UserData
0x1800751ec  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x1800751f1  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x1800751f9  xor     r9d, r9d; Flags
0x1800751fc  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x180075205  xor     r8d, r8d; Filter
0x180075208  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x180075211  call    cs:__imp_EventWriteEx
0x180075218  nop     dword ptr [rax+rax+00h]
0x18007521d  test    rbx, rbx
0x180075220  jz      short loc_180075240
0x180075222  mov     rcx, gs:60h
0x18007522b  mov     r8, rbx; lpMem
0x18007522e  xor     edx, edx; dwFlags
0x180075230  mov     rcx, [rcx+30h]; hHeap
0x180075234  call    cs:__imp_HeapFree
0x18007523b  nop     dword ptr [rax+rax+00h]
0x180075240  mov     rcx, [rbp+0A0h+var_20]
0x180075247  xor     rcx, rsp; StackCookie
0x18007524a  call    __security_check_cookie
0x18007524f  add     rsp, 190h
0x180075256  pop     r14
0x180075258  pop     rbx
0x180075259  pop     rbp
0x18007525a  retn
```
