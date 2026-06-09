# Math::Rand(void)

- ea: `0x180085a38`
- end: `0x180085ab6`
- name: `?Rand@Math@@SA_KXZ`
- size: `126`
- prototype: `unsigned __int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180084cc8`
- `0x1800c84a4`
- `0x1800cb878`
- `0x180196a40`
- `0x18019bc10`

## callees

- `0x180085a38`

## import_xrefs

- `msvcrt!rand` at `0x180085a5d`
- `msvcrt!rand` at `0x180085aa2`
- `msvcrt!rand` at `0x180085a5d`
- `msvcrt!rand` at `0x180085aa2`
- `msvcrt!srand` at `0x180085a9c`
- `msvcrt!srand` at `0x180085a9c`
- `KERNEL32!EncodeSystemPointer` at `0x180085aae`
- `KERNEL32!EncodeSystemPointer` at `0x180085aae`
- `KERNEL32!QueryPerformanceCounter` at `0x180085a88`
- `KERNEL32!QueryPerformanceCounter` at `0x180085a88`
- `KERNEL32!GetTickCount` at `0x180085a4e`
- `KERNEL32!GetTickCount` at `0x180085a4e`

## pseudocode

```c
PVOID Math::Rand(void)
{
  __int64 v0; // rbx
  PVOID result; // rax
  unsigned __int64 v2; // rbx
  int v3; // eax
  LARGE_INTEGER PerformanceCount; // [rsp+20h] [rbp-18h] BYREF

  if ( Math::RandSeed )
  {
    v0 = __ROL8__(Math::RandSeed ^ GetTickCount(), 13);
    result = (PVOID)(v0 ^ rand());
  }
  else
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v2 = PerformanceCount.LowPart ^ (unsigned __int64)PerformanceCount.HighPart;
    srand(PerformanceCount.LowPart ^ PerformanceCount.HighPart);
    v3 = rand();
    result = EncodeSystemPointer((PVOID)(v2 ^ v3));
  }
  Math::RandSeed = (volatile unsigned __int64)result;
  return result;
}

```

## disassembly

```asm
0x180085a38  mov     [rsp+arg_0], rbx
0x180085a3d  push    rdi
0x180085a3e  sub     rsp, 30h
0x180085a42  mov     rdi, cs:?RandSeed@Math@@0_KC; unsigned __int64 volatile Math::RandSeed
0x180085a49  test    rdi, rdi
0x180085a4c  jz      short loc_180085A7A
0x180085a4e  call    cs:__imp_GetTickCount
0x180085a54  mov     ebx, eax
0x180085a56  xor     rbx, rdi
0x180085a59  rol     rbx, 0Dh
0x180085a5d  call    cs:__imp_rand
0x180085a63  cdqe
0x180085a65  xor     rax, rbx
0x180085a68  mov     rbx, [rsp+38h+arg_0]
0x180085a6d  mov     cs:?RandSeed@Math@@0_KC, rax; unsigned __int64 volatile Math::RandSeed
0x180085a74  add     rsp, 30h
0x180085a78  pop     rdi
0x180085a79  retn
0x180085a7a  lea     rcx, [rsp+38h+PerformanceCount]; lpPerformanceCount
0x180085a7f  mov     qword ptr [rsp+38h+PerformanceCount], 0
0x180085a88  call    cs:__imp_QueryPerformanceCounter
0x180085a8e  mov     eax, dword ptr [rsp+38h+PerformanceCount]
0x180085a92  movsxd  rbx, dword ptr [rsp+38h+PerformanceCount+4]
0x180085a97  xor     rbx, rax
0x180085a9a  mov     ecx, ebx; Seed
0x180085a9c  call    cs:__imp_srand
0x180085aa2  call    cs:__imp_rand
0x180085aa8  movsxd  rcx, eax
0x180085aab  xor     rcx, rbx; Ptr
0x180085aae  call    cs:__imp_EncodeSystemPointer
0x180085ab4  jmp     short loc_180085A68
```
