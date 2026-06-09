# AslTelemetryCreate

- ea: `0x1800050e0`
- end: `0x18000532d`
- name: `AslTelemetryCreate`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180004650`

## callees

- `0x1800033c0`
- `0x1800050e0`
- `0x1800054f0`
- `0x1800069e0`
- `0x180007738`
- `0x18000bffe`

## import_xrefs

- `msvcrt!strcpy_s` at `0x18000519e`
- `msvcrt!strcpy_s` at `0x18000519e`
- `ntdll!RtlInitializeCriticalSection` at `0x180005168`
- `ntdll!RtlInitializeCriticalSection` at `0x180005168`
- `ntdll!RtlAllocateHeap` at `0x180005120`
- `ntdll!RtlAllocateHeap` at `0x180005120`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000523e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000523e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000528a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000528a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052c1`

## string_xrefs

- `0x18000513b`: `AslTelemetryCreate`

## pseudocode

```c
__int64 __fastcall AslTelemetryCreate(_QWORD *a1, const char *a2)
{
  char *Heap; // rax
  char *v5; // rbx
  __int64 result; // rax
  int v7; // edi
  void *v8; // r8
  PVOID ProcessHeap; // r9
  void *v10; // rax
  void *v11; // rdi
  void *v12; // r8
  void *v13; // r8

  if ( _InterlockedIncrement(&dword_180014828) == 1 )
    TraceLoggingRegisterEx_EventRegister_2U();
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xF8u);
  v5 = Heap;
  if ( Heap )
  {
    RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 88));
    *((_QWORD *)v5 + 28) = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                          * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
    strcpy_s(v5, 0x40u, a2);
    v7 = AslAnsiStringCreate((PANSI_STRING)(v5 + 72));
    if ( v7 < 0 )
    {
      AslTelemetryDelete(v5);
      return (unsigned int)v7;
    }
    else
    {
      v8 = (void *)*((_QWORD *)v5 + 21);
      if ( v8 )
        HeapFree(*((HANDLE *)v5 + 16), 0, v8);
      *((_OWORD *)v5 + 8) = 0;
      *((_OWORD *)v5 + 9) = 0;
      *((_OWORD *)v5 + 10) = 0;
      ProcessHeap = NtCurrentPeb()->ProcessHeap;
      *((_QWORD *)v5 + 16) = ProcessHeap;
      *((_QWORD *)v5 + 20) = 64;
      *((_QWORD *)v5 + 17) = 72;
      if ( is_mul_ok(0, 0x48u)
        && is_mul_ok(0x40u, 0x48u)
        && (v10 = HeapAlloc(ProcessHeap, (0x40 * (unsigned __int128)0x48uLL) >> 64, 0x1200u), (v11 = v10) != 0) )
      {
        memset_0(v10, 0, 0x1200u);
        *((_QWORD *)v5 + 21) = v11;
        *((_QWORD *)v5 + 19) = 64;
      }
      else
      {
        v12 = (void *)*((_QWORD *)v5 + 21);
        if ( v12 )
          HeapFree(*((HANDLE *)v5 + 16), 0, v12);
        *((_OWORD *)v5 + 8) = 0;
        *((_OWORD *)v5 + 9) = 0;
        *((_OWORD *)v5 + 10) = 0;
      }
      v13 = (void *)*((_QWORD *)v5 + 27);
      if ( v13 )
        HeapFree(*((HANDLE *)v5 + 22), 0, v13);
      *((_OWORD *)v5 + 11) = 0;
      *((_OWORD *)v5 + 12) = 0;
      *((_OWORD *)v5 + 13) = 0;
      result = 0;
      *((_QWORD *)v5 + 22) = NtCurrentPeb()->ProcessHeap;
      *((_QWORD *)v5 + 26) = 4;
      *((_QWORD *)v5 + 23) = 48;
      *a1 = v5;
    }
  }
  else
  {
    AslLogCallPrintf(1, "AslTelemetryCreate", 204, "Out of memory");
    return 3221225495LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800050e0  push    rbx
0x1800050e2  push    rdi
0x1800050e3  push    r14
0x1800050e5  sub     rsp, 20h
0x1800050e9  mov     rdi, rdx
0x1800050ec  mov     r14, rcx
0x1800050ef  mov     eax, 1
0x1800050f4  lock xadd cs:dword_180014828, eax
0x1800050fc  inc     eax
0x1800050fe  cmp     eax, 1
0x180005101  jnz     short loc_180005108
0x180005103  call    TraceLoggingRegisterEx_EventRegister_2U
0x180005108  mov     rcx, gs:60h
0x180005111  mov     edx, 8; Flags
0x180005116  mov     r8d, 0F8h; Size
0x18000511c  mov     rcx, [rcx+30h]; HeapHandle
0x180005120  call    cs:__imp_RtlAllocateHeap
0x180005126  mov     rbx, rax
0x180005129  test    rax, rax
0x18000512c  jnz     short loc_18000515A
0x18000512e  lea     r9, aOutOfMemory; "Out of memory"
0x180005135  mov     r8d, 0CCh
0x18000513b  lea     rdx, aAsltelemetrycr; "AslTelemetryCreate"
0x180005142  mov     ecx, 1
0x180005147  call    AslLogCallPrintf
0x18000514c  mov     eax, 0C0000017h
0x180005151  add     rsp, 20h
0x180005155  pop     r14
0x180005157  pop     rdi
0x180005158  pop     rbx
0x180005159  retn
0x18000515a  mov     [rsp+38h+arg_0], rsi
0x18000515f  lea     rcx, [rax+58h]; CriticalSection
0x180005163  mov     [rsp+38h+arg_8], r15
0x180005168  call    cs:__imp_RtlInitializeCriticalSection
0x18000516e  mov     ecx, ds:7FFE0004h
0x180005175  mov     eax, 7FFE0320h
0x18000517a  shl     rcx, 20h
0x18000517e  mov     r15d, 40h ; '@'
0x180005184  mov     r8, rdi; Source
0x180005187  mov     rax, [rax]
0x18000518a  shl     rax, 8
0x18000518e  mul     rcx
0x180005191  mov     rcx, rbx; Destination
0x180005194  mov     [rbx+0E0h], rdx
0x18000519b  mov     edx, r15d; SizeInBytes
0x18000519e  call    cs:__imp_strcpy_s
0x1800051a4  lea     rcx, [rbx+48h]; DestinationString
0x1800051a8  call    AslAnsiStringCreate
0x1800051ad  mov     edi, eax
0x1800051af  test    eax, eax
0x1800051b1  js      loc_180005310
0x1800051b7  mov     r8, [rbx+0A8h]; lpMem
0x1800051be  test    r8, r8
0x1800051c1  jz      short loc_1800051D2
0x1800051c3  mov     rcx, [rbx+80h]; hHeap
0x1800051ca  xor     edx, edx; dwFlags
0x1800051cc  call    cs:__imp_HeapFree
0x1800051d2  xorps   xmm0, xmm0
0x1800051d5  mov     [rsp+38h+arg_10], 0
0x1800051de  movups  xmmword ptr [rbx+80h], xmm0
0x1800051e5  xor     ecx, ecx
0x1800051e7  movups  xmmword ptr [rbx+90h], xmm0
0x1800051ee  movups  xmmword ptr [rbx+0A0h], xmm0
0x1800051f5  mov     rax, gs:60h
0x1800051fe  mov     r9, [rax+30h]
0x180005202  mov     eax, 48h ; 'H'
0x180005207  mul     rcx
0x18000520a  mov     [rbx+80h], r9
0x180005211  mov     [rbx+0A0h], r15
0x180005218  mov     qword ptr [rbx+88h], 48h ; 'H'
0x180005223  test    rdx, rdx
0x180005226  jnz     short loc_180005270
0x180005228  mov     eax, 48h ; 'H'
0x18000522d  mul     r15
0x180005230  mov     rsi, rax
0x180005233  test    rdx, rdx
0x180005236  jnz     short loc_180005270
0x180005238  mov     r8, rax; dwBytes
0x18000523b  mov     rcx, r9; hHeap
0x18000523e  call    cs:__imp_HeapAlloc
0x180005244  mov     rdi, rax
0x180005247  test    rax, rax
0x18000524a  jz      short loc_180005269
0x18000524c  mov     r8, rsi; Size
0x18000524f  xor     edx, edx; Val
0x180005251  mov     rcx, rax; void *
0x180005254  call    memset_0
0x180005259  mov     [rbx+0A8h], rdi
0x180005260  mov     [rbx+98h], r15
0x180005267  jmp     short loc_1800052AC
0x180005269  mov     edi, 0Eh
0x18000526e  jmp     short loc_180005275
0x180005270  mov     edi, 216h
0x180005275  mov     r8, [rbx+0A8h]; lpMem
0x18000527c  test    r8, r8
0x18000527f  jz      short loc_180005290
0x180005281  mov     rcx, [rbx+80h]; hHeap
0x180005288  xor     edx, edx; dwFlags
0x18000528a  call    cs:__imp_HeapFree
0x180005290  xorps   xmm0, xmm0
0x180005293  movups  xmmword ptr [rbx+80h], xmm0
0x18000529a  movups  xmmword ptr [rbx+90h], xmm0
0x1800052a1  movups  xmmword ptr [rbx+0A0h], xmm0
0x1800052a8  test    edi, edi
0x1800052aa  js      short loc_180005310
0x1800052ac  mov     r8, [rbx+0D8h]; lpMem
0x1800052b3  test    r8, r8
0x1800052b6  jz      short loc_1800052C7
0x1800052b8  mov     rcx, [rbx+0B0h]; hHeap
0x1800052bf  xor     edx, edx; dwFlags
0x1800052c1  call    cs:__imp_HeapFree
0x1800052c7  xorps   xmm0, xmm0
0x1800052ca  movups  xmmword ptr [rbx+0B0h], xmm0
0x1800052d1  movups  xmmword ptr [rbx+0C0h], xmm0
0x1800052d8  movups  xmmword ptr [rbx+0D0h], xmm0
0x1800052df  mov     rax, gs:60h
0x1800052e8  mov     rcx, [rax+30h]
0x1800052ec  xor     eax, eax
0x1800052ee  mov     [rbx+0B0h], rcx
0x1800052f5  mov     qword ptr [rbx+0D0h], 4
0x180005300  mov     qword ptr [rbx+0B8h], 30h ; '0'
0x18000530b  mov     [r14], rbx
0x18000530e  jmp     short loc_18000531A
0x180005310  mov     rcx, rbx; P
0x180005313  call    AslTelemetryDelete
0x180005318  mov     eax, edi
0x18000531a  mov     rsi, [rsp+38h+arg_0]
0x18000531f  mov     r15, [rsp+38h+arg_8]
0x180005324  add     rsp, 20h
0x180005328  pop     r14
0x18000532a  pop     rdi
0x18000532b  pop     rbx
0x18000532c  retn
```
