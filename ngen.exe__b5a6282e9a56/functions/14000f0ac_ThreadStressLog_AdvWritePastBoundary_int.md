# ThreadStressLog::AdvWritePastBoundary(int)

- ea: `0x14000f0ac`
- end: `0x14000f1b7`
- name: `?AdvWritePastBoundary@ThreadStressLog@@AEAAPEAUStressMsg@@H@Z`
- size: `267`
- prototype: `struct StressMsg *__fastcall(ThreadStressLog *__hidden this, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000f7a8`

## callees

- `0x14000a23c`
- `0x14000f0ac`
- `0x14000f6e0`
- `0x140011df4`
- `0x140013ce8`

## pseudocode

```c
struct StressMsg *__fastcall ThreadStressLog::AdvWritePastBoundary(ThreadStressLog *this, int a2)
{
  __int64 v2; // rdi
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 *v6; // rax
  __int64 v7; // rdx
  struct StressMsg *result; // rax
  __int64 v9; // [rsp+20h] [rbp-18h] BYREF
  char v10; // [rsp+28h] [rbp-10h]

  v2 = a2;
  memset_0((void *)(*((_QWORD *)this + 8) + 16LL), 0, *((_QWORD *)this + 2) - *((_QWORD *)this + 8) - 16LL);
  if ( *((_QWORD *)this + 8) == *((_QWORD *)this + 5) && (unsigned int)StressLog::AllowNewChunk(*((_DWORD *)this + 18)) )
  {
    if ( (unsigned int)IsInCantAllocStressLogRegion() )
    {
      v4 = 0;
    }
    else
    {
      v9 = 32792;
      v10 = 0;
      v4 = ClrHeapAlloc(StressLogChunk::s_LogChunkHeap, 0, &v9);
    }
    if ( v4 )
    {
      v5 = *((_QWORD *)this + 5);
      *(_QWORD *)v4 = *((_QWORD *)this + 6);
      *(_QWORD *)(v4 + 8) = v5;
      *(_DWORD *)(v4 + 32784) = -808464433;
      *(_DWORD *)(v4 + 32788) = -808464433;
      _InterlockedIncrement(&dword_140027120);
      ++*((_DWORD *)this + 18);
      **((_QWORD **)this + 5) = v4;
      *(_QWORD *)(*((_QWORD *)this + 6) + 8LL) = v4;
      *((_QWORD *)this + 5) = v4;
    }
  }
  v6 = (__int64 *)*((_QWORD *)this + 8);
  v7 = *v6;
  *((_QWORD *)this + 8) = *v6;
  if ( v7 == *((_QWORD *)this + 6) )
    *((_DWORD *)this + 9) = 1;
  result = (struct StressMsg *)(v7 + 8 * (4095 - v2));
  *((_QWORD *)this + 2) = result;
  return result;
}

```

## disassembly

```asm
0x14000f0ac  mov     [rsp+arg_8], rbx
0x14000f0b1  push    rdi
0x14000f0b2  sub     rsp, 30h
0x14000f0b6  movsxd  rdi, edx
0x14000f0b9  mov     rbx, rcx
0x14000f0bc  mov     rcx, [rcx+40h]
0x14000f0c0  mov     r8, [rbx+10h]
0x14000f0c4  sub     r8, rcx
0x14000f0c7  sub     r8, 10h; Size
0x14000f0cb  add     rcx, 10h; void *
0x14000f0cf  xor     edx, edx; Val
0x14000f0d1  call    memset_0
0x14000f0d6  mov     rax, [rbx+28h]
0x14000f0da  cmp     [rbx+40h], rax
0x14000f0de  jnz     loc_14000F184
0x14000f0e4  mov     ecx, [rbx+48h]; int
0x14000f0e7  call    ?AllowNewChunk@StressLog@@SAHJ@Z; StressLog::AllowNewChunk(long)
0x14000f0ec  test    eax, eax
0x14000f0ee  jz      loc_14000F184
0x14000f0f4  call    ?IsInCantAllocStressLogRegion@@YAHXZ; IsInCantAllocStressLogRegion(void)
0x14000f0f9  test    eax, eax
0x14000f0fb  jz      short loc_14000F107
0x14000f0fd  xor     r8d, r8d
0x14000f100  mov     [rsp+38h+arg_0], r8
0x14000f105  jmp     short loc_14000F13B
0x14000f107  mov     qword ptr [rsp+38h+var_18], 8018h
0x14000f110  mov     byte ptr [rsp+38h+var_18+8], 0
0x14000f115  movaps  xmm0, [rsp+38h+var_18]
0x14000f11a  movdqa  [rsp+38h+var_18], xmm0
0x14000f120  lea     r8, [rsp+38h+var_18]
0x14000f125  xor     edx, edx
0x14000f127  mov     rcx, cs:?s_LogChunkHeap@StressLogChunk@@2PEAXEA; void * StressLogChunk::s_LogChunkHeap
0x14000f12e  call    ?ClrHeapAlloc@@YAPEAXPEAXKV?$ClrSafeInt@_K@@@Z; ClrHeapAlloc(void *,ulong,ClrSafeInt<unsigned __int64>)
0x14000f133  mov     r8, rax
0x14000f136  mov     [rsp+38h+arg_0], rax
0x14000f13b  test    r8, r8
0x14000f13e  jz      short loc_14000F162
0x14000f140  mov     rdx, [rbx+28h]
0x14000f144  mov     rcx, [rbx+30h]
0x14000f148  mov     [r8], rcx
0x14000f14b  mov     [r8+8], rdx
0x14000f14f  mov     eax, 0CFCFCFCFh
0x14000f154  mov     [r8+8010h], eax
0x14000f15b  mov     [r8+8014h], eax
0x14000f162  test    r8, r8
0x14000f165  jz      short loc_14000F184
0x14000f167  lock inc cs:dword_140027120
0x14000f16e  inc     dword ptr [rbx+48h]
0x14000f171  mov     rax, [rbx+28h]
0x14000f175  mov     [rax], r8
0x14000f178  mov     rax, [rbx+30h]
0x14000f17c  mov     [rax+8], r8
0x14000f180  mov     [rbx+28h], r8
0x14000f184  mov     rax, [rbx+40h]
0x14000f188  mov     rdx, [rax]
0x14000f18b  mov     [rbx+40h], rdx
0x14000f18f  cmp     rdx, [rbx+30h]
0x14000f193  jnz     short loc_14000F19C
0x14000f195  mov     dword ptr [rbx+24h], 1
0x14000f19c  mov     ecx, 0FFFh
0x14000f1a1  sub     rcx, rdi
0x14000f1a4  lea     rax, [rdx+rcx*8]
0x14000f1a8  mov     [rbx+10h], rax
0x14000f1ac  mov     rbx, [rsp+38h+arg_8]
0x14000f1b1  add     rsp, 30h
0x14000f1b5  pop     rdi
0x14000f1b6  retn
```
