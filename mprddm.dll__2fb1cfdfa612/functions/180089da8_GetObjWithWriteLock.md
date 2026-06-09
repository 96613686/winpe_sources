# GetObjWithWriteLock

- ea: `0x180089da8`
- end: `0x180089eec`
- name: `GetObjWithWriteLock`
- size: `324`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180088cc0`
- `0x180089450`

## callees

- `0x180071cec`
- `0x180089a58`
- `0x180089da8`
- `0x18008a630`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180089e05`
- `KERNEL32!LeaveCriticalSection` at `0x180089e05`
- `KERNEL32!EnterCriticalSection` at `0x180089df2`
- `KERNEL32!EnterCriticalSection` at `0x180089df2`
- `rtutils!TracePrintfA` at `0x180089eb1`
- `rtutils!TracePrintfA` at `0x180089eb1`

## string_xrefs

- `0x180089eaa`: `GetObjWithWriteLock: Bad handle (0x%x)`
- `0x180089e62`: `GetObjWithWriteLock: Bad handle (0x%x)`

## pseudocode

```c
__int64 __fastcall GetObjWithWriteLock(unsigned int a1, _QWORD *a2)
{
  unsigned int v4; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  __int64 result; // rax
  int v7; // [rsp+20h] [rbp-828h] BYREF
  _BYTE v8[2044]; // [rsp+24h] [rbp-824h] BYREF

  v4 = a1 >> 1;
  v7 = 0;
  memset_0(v8, 0, sizeof(v8));
  EnterCriticalSection(&stru_1800C9800);
  ++dword_1800C9830;
  LeaveCriticalSection(&stru_1800C9800);
  if ( (unsigned __int16)v4 < (unsigned int)dword_1800C983C
    && (v5 = (struct _RTL_CRITICAL_SECTION *)((char *)qword_1800C9848 + 72 * (unsigned __int16)v4),
        HIWORD(v4) == LOWORD(v5[1].LockSemaphore))
    && v5[1].OwningThread )
  {
    AcquireWriteLock(v5);
    result = 0;
    *a2 = *((_QWORD *)qword_1800C9848 + 9 * (unsigned __int16)v4 + 7);
  }
  else
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v7) = 0;
        FormatRRASErrorString(&v7, L"GetObjWithWriteLock: Bad handle (0x%x)", a1);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v7);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetObjWithWriteLock: Bad handle (0x%x)", a1);
    }
    ReleaseReadLock(&stru_1800C9800);
    return 6;
  }
  return result;
}

```

## disassembly

```asm
0x180089da8  mov     [rsp+arg_10], rbx
0x180089dad  push    rsi
0x180089dae  push    rdi
0x180089daf  push    r14
0x180089db1  sub     rsp, 830h
0x180089db8  mov     rax, cs:__security_cookie
0x180089dbf  xor     rax, rsp
0x180089dc2  mov     [rsp+848h+var_28], rax
0x180089dca  mov     ebx, ecx
0x180089dcc  mov     r14, rdx
0x180089dcf  mov     esi, ecx
0x180089dd1  shr     ebx, 1
0x180089dd3  xor     eax, eax
0x180089dd5  lea     rcx, [rsp+848h+var_824]; void *
0x180089dda  xor     edx, edx; Val
0x180089ddc  mov     [rsp+848h+var_828], eax
0x180089de0  mov     r8d, 7FCh; Size
0x180089de6  call    memset_0
0x180089deb  lea     rcx, stru_1800C9800; lpCriticalSection
0x180089df2  call    cs:__imp_EnterCriticalSection
0x180089df8  inc     cs:dword_1800C9830
0x180089dfe  lea     rcx, stru_1800C9800; lpCriticalSection
0x180089e05  call    cs:__imp_LeaveCriticalSection
0x180089e0b  movzx   eax, bx
0x180089e0e  cmp     eax, cs:dword_1800C983C
0x180089e14  jnb     short loc_180089E4D
0x180089e16  lea     rdi, [rax+rax*8]
0x180089e1a  shr     ebx, 10h
0x180089e1d  mov     rax, cs:qword_1800C9848
0x180089e24  lea     rcx, [rax+rdi*8]; lpCriticalSection
0x180089e28  cmp     bx, [rcx+40h]
0x180089e2c  jnz     short loc_180089E4D
0x180089e2e  cmp     qword ptr [rcx+38h], 0
0x180089e33  jz      short loc_180089E4D
0x180089e35  call    AcquireWriteLock
0x180089e3a  mov     rax, cs:qword_1800C9848
0x180089e41  mov     rcx, [rax+rdi*8+38h]
0x180089e46  xor     eax, eax
0x180089e48  mov     [r14], rcx
0x180089e4b  jmp     short loc_180089EC8
0x180089e4d  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180089e54  jz      short loc_180089E9C
0x180089e56  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180089e5e  jz      short loc_180089EB7
0x180089e60  xor     eax, eax
0x180089e62  lea     rdx, aGetobjwithwrit_0; "GetObjWithWriteLock: Bad handle (0x%x)"
0x180089e69  mov     r8d, esi
0x180089e6c  mov     word ptr [rsp+848h+var_828], ax
0x180089e71  lea     rcx, [rsp+848h+var_828]
0x180089e76  call    FormatRRASErrorString
0x180089e7b  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180089e82  lea     r8, [rsp+848h+var_828]
0x180089e87  mov     rcx, cs:gNdpspEtwContext
0x180089e8e  mov     rax, cs:gNdpspTemplateFunc
0x180089e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089e9a  jmp     short loc_180089EB7
0x180089e9c  mov     ecx, cs:dwTraceId; dwTraceID
0x180089ea2  cmp     ecx, 0FFFFFFFFh
0x180089ea5  jz      short loc_180089EB7
0x180089ea7  mov     r8d, esi
0x180089eaa  lea     rdx, aGetobjwithwrit; "GetObjWithWriteLock: Bad handle (0x%x)"
0x180089eb1  call    cs:__imp_TracePrintfA
0x180089eb7  lea     rcx, stru_1800C9800
0x180089ebe  call    ReleaseReadLock
0x180089ec3  mov     eax, 6
0x180089ec8  mov     rcx, [rsp+848h+var_28]
0x180089ed0  xor     rcx, rsp; StackCookie
0x180089ed3  call    __security_check_cookie
0x180089ed8  mov     rbx, [rsp+848h+arg_10]
0x180089ee0  add     rsp, 830h
0x180089ee7  pop     r14
0x180089ee9  pop     rdi
0x180089eea  pop     rsi
0x180089eeb  retn
```
