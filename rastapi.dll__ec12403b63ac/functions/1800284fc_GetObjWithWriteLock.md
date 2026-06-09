# GetObjWithWriteLock

- ea: `0x1800284fc`
- end: `0x180028640`
- name: `GetObjWithWriteLock`
- size: `324`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180027414`
- `0x180027ba4`

## callees

- `0x1800281ac`
- `0x1800284fc`
- `0x180028d84`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028559`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028559`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028546`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028546`
- `rtutils!TracePrintfA` at `0x180028605`
- `rtutils!TracePrintfA` at `0x180028605`

## string_xrefs

- `0x1800285b6`: `GetObjWithWriteLock: Bad handle (0x%x)`
- `0x1800285fe`: `GetObjWithWriteLock: Bad handle (0x%x)`

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
  EnterCriticalSection(&CriticalSection);
  ++dword_18003EBB0;
  LeaveCriticalSection(&CriticalSection);
  if ( (unsigned __int16)v4 < (unsigned int)dword_18003EBBC
    && (v5 = (struct _RTL_CRITICAL_SECTION *)((char *)lpMem + 72 * (unsigned __int16)v4),
        HIWORD(v4) == LOWORD(v5[1].LockSemaphore))
    && v5[1].OwningThread )
  {
    AcquireWriteLock(v5);
    result = 0;
    *a2 = *((_QWORD *)lpMem + 9 * (unsigned __int16)v4 + 7);
  }
  else
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v7) = 0;
        FormatRRASErrorString(&v7, L"GetObjWithWriteLock: Bad handle (0x%x)", a1);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v7);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetObjWithWriteLock: Bad handle (0x%x)", a1);
    }
    ReleaseReadLock(&CriticalSection);
    return 6;
  }
  return result;
}

```

## disassembly

```asm
0x1800284fc  mov     [rsp+arg_10], rbx
0x180028501  push    rsi
0x180028502  push    rdi
0x180028503  push    r14
0x180028505  sub     rsp, 830h
0x18002850c  mov     rax, cs:__security_cookie
0x180028513  xor     rax, rsp
0x180028516  mov     [rsp+848h+var_28], rax
0x18002851e  mov     ebx, ecx
0x180028520  mov     r14, rdx
0x180028523  mov     esi, ecx
0x180028525  shr     ebx, 1
0x180028527  xor     eax, eax
0x180028529  lea     rcx, [rsp+848h+var_824]; void *
0x18002852e  xor     edx, edx; Val
0x180028530  mov     [rsp+848h+var_828], eax
0x180028534  mov     r8d, 7FCh; Size
0x18002853a  call    memset_0
0x18002853f  lea     rcx, CriticalSection; lpCriticalSection
0x180028546  call    cs:__imp_EnterCriticalSection
0x18002854c  inc     cs:dword_18003EBB0
0x180028552  lea     rcx, CriticalSection; lpCriticalSection
0x180028559  call    cs:__imp_LeaveCriticalSection
0x18002855f  movzx   eax, bx
0x180028562  cmp     eax, cs:dword_18003EBBC
0x180028568  jnb     short loc_1800285A1
0x18002856a  lea     rdi, [rax+rax*8]
0x18002856e  shr     ebx, 10h
0x180028571  mov     rax, cs:lpMem
0x180028578  lea     rcx, [rax+rdi*8]; lpCriticalSection
0x18002857c  cmp     bx, [rcx+40h]
0x180028580  jnz     short loc_1800285A1
0x180028582  cmp     qword ptr [rcx+38h], 0
0x180028587  jz      short loc_1800285A1
0x180028589  call    AcquireWriteLock
0x18002858e  mov     rax, cs:lpMem
0x180028595  mov     rcx, [rax+rdi*8+38h]
0x18002859a  xor     eax, eax
0x18002859c  mov     [r14], rcx
0x18002859f  jmp     short loc_18002861C
0x1800285a1  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x1800285a8  jz      short loc_1800285F0
0x1800285aa  cmp     cs:qword_18003EC40, 0
0x1800285b2  jz      short loc_18002860B
0x1800285b4  xor     eax, eax
0x1800285b6  lea     rdx, aGetobjwithwrit_0; "GetObjWithWriteLock: Bad handle (0x%x)"
0x1800285bd  mov     r8d, esi
0x1800285c0  mov     word ptr [rsp+848h+var_828], ax
0x1800285c5  lea     rcx, [rsp+848h+var_828]
0x1800285ca  call    FormatRRASErrorString
0x1800285cf  mov     rdx, cs:qword_18003EC40
0x1800285d6  lea     r8, [rsp+848h+var_828]
0x1800285db  mov     rcx, cs:gNdpspEtwContext
0x1800285e2  mov     rax, cs:gNdpspTemplateFunc
0x1800285e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285ee  jmp     short loc_18002860B
0x1800285f0  mov     ecx, cs:dwTraceId; dwTraceID
0x1800285f6  cmp     ecx, 0FFFFFFFFh
0x1800285f9  jz      short loc_18002860B
0x1800285fb  mov     r8d, esi
0x1800285fe  lea     rdx, aGetobjwithwrit; "GetObjWithWriteLock: Bad handle (0x%x)"
0x180028605  call    cs:__imp_TracePrintfA
0x18002860b  lea     rcx, CriticalSection
0x180028612  call    ReleaseReadLock
0x180028617  mov     eax, 6
0x18002861c  mov     rcx, [rsp+848h+var_28]
0x180028624  xor     rcx, rsp; StackCookie
0x180028627  call    __security_check_cookie
0x18002862c  mov     rbx, [rsp+848h+arg_10]
0x180028634  add     rsp, 830h
0x18002863b  pop     r14
0x18002863d  pop     rdi
0x18002863e  pop     rsi
0x18002863f  retn
```
