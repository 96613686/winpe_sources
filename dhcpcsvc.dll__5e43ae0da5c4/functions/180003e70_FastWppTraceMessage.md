# FastWppTraceMessage

- ea: `0x180003e70`
- end: `0x18000400e`
- name: `FastWppTraceMessage`
- size: `414`
- prototype: ``
- caller_count: `52`
- callee_count: `3`
- tags: ``

## callers

- `0x180011010`
- `0x180011060`
- `0x1800110a8`
- `0x1800110f8`
- `0x180011190`
- `0x1800111e4`
- `0x180011260`
- `0x180011298`
- `0x1800112d0`
- `0x180011324`
- `0x180011374`
- `0x1800113f8`
- `0x180011498`
- `0x180011598`
- `0x180011614`
- `0x1800116d4`
- `0x180011784`
- `0x180011894`
- `0x18001190c`
- `0x180011a1c`
- `0x180011afc`
- `0x180011bd0`
- `0x180011ce0`
- `0x180011e08`
- `0x180011ec4`
- `0x180011f08`
- `0x180011f50`
- `0x180011ffc`
- `0x180012060`
- `0x180012118`
- `0x1800121e0`
- `0x180012230`
- `0x1800123a4`
- `0x180012500`
- `0x18001259c`
- `0x180012628`
- `0x18001268c`
- `0x1800126dc`
- `0x180012794`
- `0x1800127f0`
- `0x180012850`
- `0x1800128d0`
- `0x180012a00`
- `0x180012a40`
- `0x180012ad0`
- `0x180012b80`
- `0x180012ba0`
- `0x180012d20`
- `0x180012df0`
- `0x180012e30`

## callees

- `0x180003e70`
- `0x1800048c0`
- `0x18000da80`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!HeapFree` at `0x180003fe8`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapFree` at `0x180003fe8`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapAlloc` at `0x180003f5b`
- `api-ms-win-downlevel-kernel32-l1-1-0!HeapAlloc` at `0x180003f5b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180003fc3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180003fc3`

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
0x180003e70  mov     r11, rsp
0x180003e73  mov     [r11+18h], r8
0x180003e77  mov     [r11+20h], r9
0x180003e7b  push    rbp
0x180003e7c  lea     rbp, [r11-0A8h]
0x180003e83  sub     rsp, 1A0h
0x180003e8a  mov     rax, cs:__security_cookie
0x180003e91  xor     rax, rsp
0x180003e94  mov     [rbp+0A0h+var_20], rax
0x180003e9b  mov     eax, cs:FastWppInitState
0x180003ea1  xorps   xmm1, xmm1
0x180003ea4  mov     qword ptr [rsp+1A0h+EventDescriptor.Id], 0
0x180003ead  xorps   xmm0, xmm0
0x180003eb0  movups  xmmword ptr [rsp+1A0h+EventDescriptor.Keyword], xmm0
0x180003eb5  movups  xmmword ptr [rsp+1A0h+var_150.Size], xmm1
0x180003eba  movups  [rsp+1A0h+var_140+8], xmm1
0x180003ebf  cmp     eax, 2
0x180003ec2  jnz     loc_180003FF6
0x180003ec8  movzx   eax, cx
0x180003ecb  mov     [r11-10h], rbx
0x180003ecf  shr     ax, 8
0x180003ed3  lea     r9, [rsp+70h]
0x180003ed8  mov     byte ptr [rsp+1A0h+EventDescriptor.Keyword+4], al
0x180003edc  xor     ebx, ebx
0x180003ede  mov     [r11-18h], rsi
0x180003ee2  mov     eax, 1
0x180003ee7  shl     rax, cl
0x180003eea  lea     rsi, [rbp+0A0h+arg_18]
0x180003ef1  mov     [rsp+1A0h+var_150.Ptr], rax
0x180003ef6  mov     r8d, 100h
0x180003efc  mov     rax, [rbp+0A0h+arg_10]
0x180003f03  mov     rcx, rsi
0x180003f06  mov     qword ptr [rsp+1A0h+var_150.Size], rax
0x180003f0b  lea     rax, [rbp+0A0h+var_120]
0x180003f0f  mov     word ptr [rsp+1A0h+EventDescriptor.Keyword], dx
0x180003f14  lea     rdx, [rbp+0A0h+var_120]
0x180003f18  mov     qword ptr [rsp+1A0h+var_140+8], rax
0x180003f1d  mov     byte ptr [rsp+1A0h+var_140+4], 4
0x180003f22  mov     dword ptr [rsp+1A0h+var_140], 10h
0x180003f2a  mov     [rsp+74h], bl
0x180003f2e  mov     dword ptr [rsp+70h], 100h
0x180003f36  call    FastWppPackEvent
0x180003f3b  mov     eax, [rsp+70h]
0x180003f3f  cmp     eax, 100h
0x180003f44  jbe     short loc_180003F8D
0x180003f46  mov     rcx, gs:60h
0x180003f4f  mov     r8d, eax; dwBytes
0x180003f52  mov     edx, 8; dwFlags
0x180003f57  mov     rcx, [rcx+30h]; hHeap
0x180003f5b  call    cs:__imp_HeapAlloc
0x180003f61  mov     rbx, rax
0x180003f64  test    rax, rax
0x180003f67  jz      short loc_180003F85
0x180003f69  mov     r8d, [rsp+70h]
0x180003f6e  lea     r9, [rsp+70h]
0x180003f73  mov     rdx, rax
0x180003f76  mov     qword ptr [rsp+1A0h+var_140+8], rax
0x180003f7b  mov     rcx, rsi
0x180003f7e  call    FastWppPackEvent
0x180003f83  jmp     short loc_180003F8D
0x180003f85  mov     dword ptr [rsp+70h], 100h
0x180003f8d  mov     rcx, cs:FastWppRegHandle; RegHandle
0x180003f94  lea     rax, [rsp+1A0h+var_150.Size]
0x180003f99  mov     [rsp+1A0h+UserData], rax; UserData
0x180003f9e  lea     rdx, [rsp+1A0h+EventDescriptor.Keyword]; EventDescriptor
0x180003fa3  mov     [rsp+1A0h+UserDataCount], 2; UserDataCount
0x180003fab  xor     r9d, r9d; Flags
0x180003fae  mov     [rsp+1A0h+RelatedActivityId], 0; RelatedActivityId
0x180003fb7  xor     r8d, r8d; Filter
0x180003fba  mov     [rsp+1A0h+ActivityId], 0; ActivityId
0x180003fc3  call    cs:__imp_EventWriteEx
0x180003fc9  mov     rsi, [rsp+1A0h+var_10]
0x180003fd1  test    rbx, rbx
0x180003fd4  jz      short loc_180003FEE
0x180003fd6  mov     rcx, gs:60h
0x180003fdf  mov     r8, rbx; lpMem
0x180003fe2  xor     edx, edx; dwFlags
0x180003fe4  mov     rcx, [rcx+30h]; hHeap
0x180003fe8  call    cs:__imp_HeapFree
0x180003fee  mov     rbx, [rsp+198h]
0x180003ff6  mov     rcx, [rbp+0A0h+var_20]
0x180003ffd  xor     rcx, rsp; StackCookie
0x180004000  call    __security_check_cookie
0x180004005  add     rsp, 1A0h
0x18000400c  pop     rbp
0x18000400d  retn
```
