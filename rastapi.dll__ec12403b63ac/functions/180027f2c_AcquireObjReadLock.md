# AcquireObjReadLock

- ea: `0x180027f2c`
- end: `0x180028071`
- name: `AcquireObjReadLock`
- size: `325`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800257e4`
- `0x1800275b8`

## callees

- `0x180027f2c`
- `0x180028d84`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027f88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027fc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027f88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027fc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027f75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027fbb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027f75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027fbb`
- `rtutils!TracePrintfA` at `0x180028035`
- `rtutils!TracePrintfA` at `0x180028035`

## string_xrefs

- `0x180027fe6`: `AcquireObjReadLock: Bad handle (0x%x)`
- `0x18002802e`: `AcquireObjReadLock: Bad handle (0x%x)`

## pseudocode

```c
__int64 __fastcall AcquireObjReadLock(unsigned int a1)
{
  unsigned int v2; // edi
  char *v3; // rbx
  int v5; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v6[2044]; // [rsp+24h] [rbp-814h] BYREF

  v2 = a1 >> 1;
  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  EnterCriticalSection(&CriticalSection);
  ++dword_18003EBB0;
  LeaveCriticalSection(&CriticalSection);
  if ( (unsigned __int16)v2 < (unsigned int)dword_18003EBBC
    && (v3 = (char *)lpMem + 72 * (unsigned __int16)v2, HIWORD(v2) == *((_WORD *)v3 + 32))
    && *((_QWORD *)v3 + 7) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 72 * (unsigned __int16)v2));
    ++*((_DWORD *)v3 + 12);
    LeaveCriticalSection((LPCRITICAL_SECTION)v3);
    return 0;
  }
  else
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v5) = 0;
        FormatRRASErrorString(&v5, L"AcquireObjReadLock: Bad handle (0x%x)", a1);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v5);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "AcquireObjReadLock: Bad handle (0x%x)", a1);
    }
    ReleaseReadLock(&CriticalSection);
    return 6;
  }
}

```

## disassembly

```asm
0x180027f2c  mov     [rsp+arg_8], rbx
0x180027f31  mov     [rsp+arg_10], rsi
0x180027f36  push    rdi
0x180027f37  sub     rsp, 830h
0x180027f3e  mov     rax, cs:__security_cookie
0x180027f45  xor     rax, rsp
0x180027f48  mov     [rsp+838h+var_18], rax
0x180027f50  mov     edi, ecx
0x180027f52  mov     esi, ecx
0x180027f54  xor     eax, eax
0x180027f56  shr     edi, 1
0x180027f58  lea     rcx, [rsp+838h+var_814]; void *
0x180027f5d  mov     [rsp+838h+var_818], eax
0x180027f61  xor     edx, edx; Val
0x180027f63  mov     r8d, 7FCh; Size
0x180027f69  call    memset_0
0x180027f6e  lea     rcx, CriticalSection; lpCriticalSection
0x180027f75  call    cs:__imp_EnterCriticalSection
0x180027f7b  inc     cs:dword_18003EBB0
0x180027f81  lea     rcx, CriticalSection; lpCriticalSection
0x180027f88  call    cs:__imp_LeaveCriticalSection
0x180027f8e  movzx   eax, di
0x180027f91  cmp     eax, cs:dword_18003EBBC
0x180027f97  jnb     short loc_180027FD1
0x180027f99  lea     rcx, [rax+rax*8]
0x180027f9d  shr     edi, 10h
0x180027fa0  mov     rax, cs:lpMem
0x180027fa7  lea     rbx, [rax+rcx*8]
0x180027fab  cmp     di, [rbx+40h]
0x180027faf  jnz     short loc_180027FD1
0x180027fb1  cmp     qword ptr [rbx+38h], 0
0x180027fb6  jz      short loc_180027FD1
0x180027fb8  mov     rcx, rbx; lpCriticalSection
0x180027fbb  call    cs:__imp_EnterCriticalSection
0x180027fc1  inc     dword ptr [rbx+30h]
0x180027fc4  mov     rcx, rbx; lpCriticalSection
0x180027fc7  call    cs:__imp_LeaveCriticalSection
0x180027fcd  xor     eax, eax
0x180027fcf  jmp     short loc_18002804C
0x180027fd1  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180027fd8  jz      short loc_180028020
0x180027fda  cmp     cs:qword_18003EC40, 0
0x180027fe2  jz      short loc_18002803B
0x180027fe4  xor     eax, eax
0x180027fe6  lea     rdx, aAcquireobjread; "AcquireObjReadLock: Bad handle (0x%x)"
0x180027fed  mov     r8d, esi
0x180027ff0  mov     word ptr [rsp+838h+var_818], ax
0x180027ff5  lea     rcx, [rsp+838h+var_818]
0x180027ffa  call    FormatRRASErrorString
0x180027fff  mov     rdx, cs:qword_18003EC40
0x180028006  lea     r8, [rsp+838h+var_818]
0x18002800b  mov     rcx, cs:gNdpspEtwContext
0x180028012  mov     rax, cs:gNdpspTemplateFunc
0x180028019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002801e  jmp     short loc_18002803B
0x180028020  mov     ecx, cs:dwTraceId; dwTraceID
0x180028026  cmp     ecx, 0FFFFFFFFh
0x180028029  jz      short loc_18002803B
0x18002802b  mov     r8d, esi
0x18002802e  lea     rdx, aAcquireobjread_0; "AcquireObjReadLock: Bad handle (0x%x)"
0x180028035  call    cs:__imp_TracePrintfA
0x18002803b  lea     rcx, CriticalSection
0x180028042  call    ReleaseReadLock
0x180028047  mov     eax, 6
0x18002804c  mov     rcx, [rsp+838h+var_18]
0x180028054  xor     rcx, rsp; StackCookie
0x180028057  call    __security_check_cookie
0x18002805c  lea     r11, [rsp+838h+var_8]
0x180028064  mov     rbx, [r11+18h]
0x180028068  mov     rsi, [r11+20h]
0x18002806c  mov     rsp, r11
0x18002806f  pop     rdi
0x180028070  retn
```
