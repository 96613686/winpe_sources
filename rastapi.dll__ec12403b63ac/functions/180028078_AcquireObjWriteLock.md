# AcquireObjWriteLock

- ea: `0x180028078`
- end: `0x1800281a4`
- name: `AcquireObjWriteLock`
- size: `300`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1800226f0`
- `0x180023a14`
- `0x180023e24`

## callees

- `0x180028078`
- `0x1800281ac`
- `0x180028d84`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800280cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800280cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800280bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800280bc`
- `rtutils!TracePrintfA` at `0x18002816c`
- `rtutils!TracePrintfA` at `0x18002816c`

## string_xrefs

- `0x18002811d`: `AcquireObjWriteLock: Bad handle (0x%x)`
- `0x180028165`: `AcquireObjWriteLock: Bad handle (0x%x)`

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
  EnterCriticalSection(&CriticalSection);
  ++dword_18003EBB0;
  LeaveCriticalSection(&CriticalSection);
  if ( (unsigned __int16)v2 < (unsigned int)dword_18003EBBC
    && (v3 = (struct _RTL_CRITICAL_SECTION *)((char *)lpMem + 72 * (unsigned __int16)v2),
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
      if ( qword_18003EC40 )
      {
        LOWORD(v5) = 0;
        FormatRRASErrorString(&v5, L"AcquireObjWriteLock: Bad handle (0x%x)", a1);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v5);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "AcquireObjWriteLock: Bad handle (0x%x)", a1);
    }
    ReleaseReadLock(&CriticalSection);
    return 6;
  }
}

```

## disassembly

```asm
0x180028078  mov     [rsp+arg_8], rbx
0x18002807d  push    rdi
0x18002807e  sub     rsp, 830h
0x180028085  mov     rax, cs:__security_cookie
0x18002808c  xor     rax, rsp
0x18002808f  mov     [rsp+838h+var_18], rax
0x180028097  mov     ebx, ecx
0x180028099  mov     edi, ecx
0x18002809b  xor     eax, eax
0x18002809d  shr     ebx, 1
0x18002809f  lea     rcx, [rsp+838h+var_814]; void *
0x1800280a4  mov     [rsp+838h+var_818], eax
0x1800280a8  xor     edx, edx; Val
0x1800280aa  mov     r8d, 7FCh; Size
0x1800280b0  call    memset_0
0x1800280b5  lea     rcx, CriticalSection; lpCriticalSection
0x1800280bc  call    cs:__imp_EnterCriticalSection
0x1800280c2  inc     cs:dword_18003EBB0
0x1800280c8  lea     rcx, CriticalSection; lpCriticalSection
0x1800280cf  call    cs:__imp_LeaveCriticalSection
0x1800280d5  movzx   eax, bx
0x1800280d8  cmp     eax, cs:dword_18003EBBC
0x1800280de  jnb     short loc_180028108
0x1800280e0  lea     rcx, [rax+rax*8]
0x1800280e4  shr     ebx, 10h
0x1800280e7  mov     rax, cs:lpMem
0x1800280ee  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800280f2  cmp     bx, [rcx+40h]
0x1800280f6  jnz     short loc_180028108
0x1800280f8  cmp     qword ptr [rcx+38h], 0
0x1800280fd  jz      short loc_180028108
0x1800280ff  call    AcquireWriteLock
0x180028104  xor     eax, eax
0x180028106  jmp     short loc_180028183
0x180028108  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x18002810f  jz      short loc_180028157
0x180028111  cmp     cs:qword_18003EC40, 0
0x180028119  jz      short loc_180028172
0x18002811b  xor     eax, eax
0x18002811d  lea     rdx, aAcquireobjwrit; "AcquireObjWriteLock: Bad handle (0x%x)"
0x180028124  mov     r8d, edi
0x180028127  mov     word ptr [rsp+838h+var_818], ax
0x18002812c  lea     rcx, [rsp+838h+var_818]
0x180028131  call    FormatRRASErrorString
0x180028136  mov     rdx, cs:qword_18003EC40
0x18002813d  lea     r8, [rsp+838h+var_818]
0x180028142  mov     rcx, cs:gNdpspEtwContext
0x180028149  mov     rax, cs:gNdpspTemplateFunc
0x180028150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028155  jmp     short loc_180028172
0x180028157  mov     ecx, cs:dwTraceId; dwTraceID
0x18002815d  cmp     ecx, 0FFFFFFFFh
0x180028160  jz      short loc_180028172
0x180028162  mov     r8d, edi
0x180028165  lea     rdx, aAcquireobjwrit_0; "AcquireObjWriteLock: Bad handle (0x%x)"
0x18002816c  call    cs:__imp_TracePrintfA
0x180028172  lea     rcx, CriticalSection
0x180028179  call    ReleaseReadLock
0x18002817e  mov     eax, 6
0x180028183  mov     rcx, [rsp+838h+var_18]
0x18002818b  xor     rcx, rsp; StackCookie
0x18002818e  call    __security_check_cookie
0x180028193  mov     rbx, [rsp+838h+arg_8]
0x18002819b  add     rsp, 830h
0x1800281a2  pop     rdi
0x1800281a3  retn
```
