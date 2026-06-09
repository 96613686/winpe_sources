# FastWppTraceMessage

- ea: `0x180002ec0`
- end: `0x18000305e`
- name: `FastWppTraceMessage`
- size: `414`
- prototype: `ULONG(__int16, USHORT, ULONGLONG, ...)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180008008`
- `0x18000809c`
- `0x1800080e4`
- `0x180008170`
- `0x1800081c0`
- `0x180008220`
- `0x1800082b0`
- `0x1800082d0`
- `0x180008310`
- `0x1800083c0`
- `0x180008490`

## callees

- `0x180002ec0`
- `0x180003a90`
- `0x180004798`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002fab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002fab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003038`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003038`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180003013`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180003013`

## pseudocode

```c
ULONG FastWppTraceMessage(__int16 a1, USHORT a2, ULONGLONG a3, ...)
{
  ULONG result; // eax
  void *v4; // rbx
  LPVOID v5; // rax
  EVENT_DESCRIPTOR EventDescriptor_8; // [rsp+50h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v8; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v9[256]; // [rsp+88h] [rbp-80h] BYREF
  va_list va; // [rsp+1D0h] [rbp+C8h] BYREF

  va_start(va, a3);
  result = FastWppInitState;
  EventDescriptor_8 = 0;
  UserData = 0;
  v8 = 0;
  if ( FastWppInitState == 2 )
  {
    EventDescriptor_8.Level = HIBYTE(a1);
    v4 = 0;
    EventDescriptor_8.Keyword = 1LL << a1;
    UserData.Ptr = a3;
    EventDescriptor_8.Id = a2;
    *(_QWORD *)&v8 = v9;
    UserData.Type = 4;
    UserData.Size = 16;
    BYTE12(v8) = 0;
    DWORD2(v8) = 256;
    FastWppPackEvent(va, v9, 256, (char *)&v8 + 8);
    if ( DWORD2(v8) > 0x100 )
    {
      v5 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, DWORD2(v8));
      v4 = v5;
      if ( v5 )
      {
        *(_QWORD *)&v8 = v5;
        FastWppPackEvent(va, v5, DWORD2(v8), (char *)&v8 + 8);
      }
      else
      {
        DWORD2(v8) = 256;
      }
    }
    result = EventWriteEx(FastWppRegHandle, &EventDescriptor_8, 0, 0, 0, 0, 2u, &UserData);
    if ( v4 )
      return HeapFree(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  return result;
}

```

## disassembly

```asm
0x180002ec0  mov     r11, rsp
0x180002ec3  mov     [r11+18h], r8
0x180002ec7  mov     [r11+20h], r9
0x180002ecb  push    rbp
0x180002ecc  lea     rbp, [r11-0A8h]
0x180002ed3  sub     rsp, 1A0h
0x180002eda  mov     rax, cs:__security_cookie
0x180002ee1  xor     rax, rsp
0x180002ee4  mov     [rbp+0A0h+var_20], rax
0x180002eeb  mov     eax, cs:FastWppInitState
0x180002ef1  xorps   xmm1, xmm1
0x180002ef4  mov     qword ptr [rsp+1A0h+EventDescriptor.Id], 0
0x180002efd  xorps   xmm0, xmm0
0x180002f00  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Keyword], xmm0
0x180002f05  movups  xmmword ptr [rsp+1A0h+var_150.Size], xmm1
0x180002f0a  movups  [rsp+1A0h+var_140+8], xmm1
0x180002f0f  cmp     eax, 2
0x180002f12  jnz     loc_180003046
0x180002f18  movzx   eax, cx
0x180002f1b  mov     [r11-10h], rbx
0x180002f1f  shr     ax, 8
0x180002f23  lea     r9, [rsp+70h]
0x180002f28  mov     byte ptr [rsp+1A0h+EventDescriptor.Keyword+4], al
0x180002f2c  xor     ebx, ebx
0x180002f2e  mov     [r11-18h], rsi
0x180002f32  mov     eax, 1
0x180002f37  shl     rax, cl
0x180002f3a  lea     rsi, [rbp+0A0h+arg_18]
0x180002f41  mov     [rsp+1A0h+var_150.Ptr], rax
0x180002f46  mov     r8d, 100h
0x180002f4c  mov     rax, [rbp+0A0h+arg_10]
0x180002f53  mov     rcx, rsi
0x180002f56  mov     qword ptr [rsp+1A0h+var_150.Size], rax
0x180002f5b  lea     rax, [rbp+0A0h+var_120]
0x180002f5f  mov     word ptr [rsp+1A0h+EventDescriptor.Keyword], dx
0x180002f64  lea     rdx, [rbp+0A0h+var_120]
0x180002f68  mov     qword ptr [rsp+1A0h+var_140+8], rax
0x180002f6d  mov     byte ptr [rsp+1A0h+var_140+4], 4
0x180002f72  mov     dword ptr [rsp+1A0h+var_140], 10h
0x180002f7a  mov     [rsp+74h], bl
0x180002f7e  mov     dword ptr [rsp+70h], 100h
0x180002f86  call    FastWppPackEvent
0x180002f8b  mov     eax, [rsp+70h]
0x180002f8f  cmp     eax, 100h
0x180002f94  jbe     short loc_180002FDD
0x180002f96  mov     rcx, gs:60h
0x180002f9f  mov     r8d, eax; dwBytes
0x180002fa2  mov     edx, 8; dwFlags
0x180002fa7  mov     rcx, [rcx+30h]; hHeap
0x180002fab  call    cs:__imp_HeapAlloc
0x180002fb1  mov     rbx, rax
0x180002fb4  test    rax, rax
0x180002fb7  jz      short loc_180002FD5
0x180002fb9  mov     r8d, [rsp+70h]
0x180002fbe  lea     r9, [rsp+70h]
0x180002fc3  mov     rdx, rax
0x180002fc6  mov     qword ptr [rsp+1A0h+var_140+8], rax
0x180002fcb  mov     rcx, rsi
0x180002fce  call    FastWppPackEvent
0x180002fd3  jmp     short loc_180002FDD
0x180002fd5  mov     dword ptr [rsp+70h], 100h
0x180002fdd  mov     rcx, cs:FastWppRegHandle; RegHandle
0x180002fe4  lea     rax, [rsp+1A0h+var_150.Size]
0x180002fe9  mov     [rsp+1A0h+UserData], rax; UserData
0x180002fee  lea     rdx, [rsp+1A0h+EventDescriptor.Keyword]; EventDescriptor
0x180002ff3  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x180002ffb  xor     r9d, r9d; Flags
0x180002ffe  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x180003007  xor     r8d, r8d; Filter
0x18000300a  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x180003013  call    cs:__imp_EventWriteEx
0x180003019  mov     rsi, [rsp+1A0h+var_10]
0x180003021  test    rbx, rbx
0x180003024  jz      short loc_18000303E
0x180003026  mov     rcx, gs:60h
0x18000302f  mov     r8, rbx; lpMem
0x180003032  xor     edx, edx; dwFlags
0x180003034  mov     rcx, [rcx+30h]; hHeap
0x180003038  call    cs:__imp_HeapFree
0x18000303e  mov     rbx, [rsp+198h]
0x180003046  mov     rcx, [rbp+0A0h+var_20]
0x18000304d  xor     rcx, rsp; StackCookie
0x180003050  call    __security_check_cookie
0x180003055  add     rsp, 1A0h
0x18000305c  pop     rbp
0x18000305d  retn
```
