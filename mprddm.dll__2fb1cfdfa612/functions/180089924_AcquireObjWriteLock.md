# AcquireObjWriteLock

- ea: `0x180089924`
- end: `0x180089a50`
- name: `AcquireObjWriteLock`
- size: `300`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180084ae0`
- `0x180085e4c`
- `0x18008625c`

## callees

- `0x180071cec`
- `0x180089924`
- `0x180089a58`
- `0x18008a630`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18008997b`
- `KERNEL32!LeaveCriticalSection` at `0x18008997b`
- `KERNEL32!EnterCriticalSection` at `0x180089968`
- `KERNEL32!EnterCriticalSection` at `0x180089968`
- `rtutils!TracePrintfA` at `0x180089a18`
- `rtutils!TracePrintfA` at `0x180089a18`

## string_xrefs

- `0x180089a11`: `AcquireObjWriteLock: Bad handle (0x%x)`
- `0x1800899c9`: `AcquireObjWriteLock: Bad handle (0x%x)`

## pseudocode

```c
__int64 __fastcall AcquireObjWriteLock(unsigned int a1)
{
  unsigned int v2; // ebx
  struct _RTL_CRITICAL_SECTION *v3; // rcx
  int v5; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v6[2044]; // [rsp+24h] [rbp-814h] BYREF

  v2 = a1 >> 1;
  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  EnterCriticalSection(&stru_1800C9800);
  ++dword_1800C9830;
  LeaveCriticalSection(&stru_1800C9800);
  if ( (unsigned __int16)v2 < (unsigned int)dword_1800C983C
    && (v3 = (struct _RTL_CRITICAL_SECTION *)((char *)qword_1800C9848 + 72 * (unsigned __int16)v2),
        HIWORD(v2) == LOWORD(v3[1].LockSemaphore))
    && v3[1].OwningThread )
  {
    AcquireWriteLock(v3);
    return 0;
  }
  else
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v5) = 0;
        FormatRRASErrorString(&v5, L"AcquireObjWriteLock: Bad handle (0x%x)", a1);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v5);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "AcquireObjWriteLock: Bad handle (0x%x)", a1);
    }
    ReleaseReadLock(&stru_1800C9800);
    return 6;
  }
}

```

## disassembly

```asm
0x180089924  mov     [rsp+arg_8], rbx
0x180089929  push    rdi
0x18008992a  sub     rsp, 830h
0x180089931  mov     rax, cs:__security_cookie
0x180089938  xor     rax, rsp
0x18008993b  mov     [rsp+838h+var_18], rax
0x180089943  mov     ebx, ecx
0x180089945  mov     edi, ecx
0x180089947  xor     eax, eax
0x180089949  shr     ebx, 1
0x18008994b  lea     rcx, [rsp+838h+var_814]; void *
0x180089950  mov     [rsp+838h+var_818], eax
0x180089954  xor     edx, edx; Val
0x180089956  mov     r8d, 7FCh; Size
0x18008995c  call    memset_0
0x180089961  lea     rcx, stru_1800C9800; lpCriticalSection
0x180089968  call    cs:__imp_EnterCriticalSection
0x18008996e  inc     cs:dword_1800C9830
0x180089974  lea     rcx, stru_1800C9800; lpCriticalSection
0x18008997b  call    cs:__imp_LeaveCriticalSection
0x180089981  movzx   eax, bx
0x180089984  cmp     eax, cs:dword_1800C983C
0x18008998a  jnb     short loc_1800899B4
0x18008998c  lea     rcx, [rax+rax*8]
0x180089990  shr     ebx, 10h
0x180089993  mov     rax, cs:qword_1800C9848
0x18008999a  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18008999e  cmp     bx, [rcx+40h]
0x1800899a2  jnz     short loc_1800899B4
0x1800899a4  cmp     qword ptr [rcx+38h], 0
0x1800899a9  jz      short loc_1800899B4
0x1800899ab  call    AcquireWriteLock
0x1800899b0  xor     eax, eax
0x1800899b2  jmp     short loc_180089A2F
0x1800899b4  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800899bb  jz      short loc_180089A03
0x1800899bd  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x1800899c5  jz      short loc_180089A1E
0x1800899c7  xor     eax, eax
0x1800899c9  lea     rdx, aAcquireobjwrit; "AcquireObjWriteLock: Bad handle (0x%x)"
0x1800899d0  mov     r8d, edi
0x1800899d3  mov     word ptr [rsp+838h+var_818], ax
0x1800899d8  lea     rcx, [rsp+838h+var_818]
0x1800899dd  call    FormatRRASErrorString
0x1800899e2  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x1800899e9  lea     r8, [rsp+838h+var_818]
0x1800899ee  mov     rcx, cs:gNdpspEtwContext
0x1800899f5  mov     rax, cs:gNdpspTemplateFunc
0x1800899fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089a01  jmp     short loc_180089A1E
0x180089a03  mov     ecx, cs:dwTraceId; dwTraceID
0x180089a09  cmp     ecx, 0FFFFFFFFh
0x180089a0c  jz      short loc_180089A1E
0x180089a0e  mov     r8d, edi
0x180089a11  lea     rdx, aAcquireobjwrit_0; "AcquireObjWriteLock: Bad handle (0x%x)"
0x180089a18  call    cs:__imp_TracePrintfA
0x180089a1e  lea     rcx, stru_1800C9800
0x180089a25  call    ReleaseReadLock
0x180089a2a  mov     eax, 6
0x180089a2f  mov     rcx, [rsp+838h+var_18]
0x180089a37  xor     rcx, rsp; StackCookie
0x180089a3a  call    __security_check_cookie
0x180089a3f  mov     rbx, [rsp+838h+arg_8]
0x180089a47  add     rsp, 830h
0x180089a4e  pop     rdi
0x180089a4f  retn
```
