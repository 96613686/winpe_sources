# Math::Rand(void)

- ea: `0x180096d9c`
- end: `0x180096e3f`
- name: `?Rand@Math@@SA_KXZ`
- size: `163`
- prototype: `unsigned __int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180040894`
- `0x180096028`
- `0x18009cab8`
- `0x1801990a4`
- `0x18019dc30`

## callees

- `0x180096d9c`

## import_xrefs

- `msvcrt!rand` at `0x180096dc7`
- `msvcrt!rand` at `0x180096e1f`
- `msvcrt!rand` at `0x180096dc7`
- `msvcrt!rand` at `0x180096e1f`
- `msvcrt!srand` at `0x180096e13`
- `msvcrt!srand` at `0x180096e13`
- `KERNEL32!EncodeSystemPointer` at `0x180096e31`
- `KERNEL32!EncodeSystemPointer` at `0x180096e31`
- `KERNEL32!QueryPerformanceCounter` at `0x180096df9`
- `KERNEL32!QueryPerformanceCounter` at `0x180096df9`
- `KERNEL32!GetTickCount` at `0x180096db2`
- `KERNEL32!GetTickCount` at `0x180096db2`

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
0x180096d9c  mov     [rsp+arg_0], rbx
0x180096da1  push    rdi
0x180096da2  sub     rsp, 30h
0x180096da6  mov     rdi, cs:?RandSeed@Math@@0_KC; unsigned __int64 volatile Math::RandSeed
0x180096dad  test    rdi, rdi
0x180096db0  jz      short loc_180096DEB
0x180096db2  call    cs:__imp_GetTickCount
0x180096db9  nop     dword ptr [rax+rax+00h]
0x180096dbe  mov     ebx, eax
0x180096dc0  xor     rbx, rdi
0x180096dc3  rol     rbx, 0Dh
0x180096dc7  call    cs:__imp_rand
0x180096dce  nop     dword ptr [rax+rax+00h]
0x180096dd3  cdqe
0x180096dd5  xor     rax, rbx
0x180096dd8  mov     rbx, [rsp+38h+arg_0]
0x180096ddd  mov     cs:?RandSeed@Math@@0_KC, rax; unsigned __int64 volatile Math::RandSeed
0x180096de4  add     rsp, 30h
0x180096de8  pop     rdi
0x180096de9  retn
0x180096deb  lea     rcx, [rsp+38h+PerformanceCount]; lpPerformanceCount
0x180096df0  mov     qword ptr [rsp+38h+PerformanceCount], 0
0x180096df9  call    cs:__imp_QueryPerformanceCounter
0x180096e00  nop     dword ptr [rax+rax+00h]
0x180096e05  mov     eax, dword ptr [rsp+38h+PerformanceCount]
0x180096e09  movsxd  rbx, dword ptr [rsp+38h+PerformanceCount+4]
0x180096e0e  xor     rbx, rax
0x180096e11  mov     ecx, ebx; Seed
0x180096e13  call    cs:__imp_srand
0x180096e1a  nop     dword ptr [rax+rax+00h]
0x180096e1f  call    cs:__imp_rand
0x180096e26  nop     dword ptr [rax+rax+00h]
0x180096e2b  movsxd  rcx, eax
0x180096e2e  xor     rcx, rbx; Ptr
0x180096e31  call    cs:__imp_EncodeSystemPointer
0x180096e38  nop     dword ptr [rax+rax+00h]
0x180096e3d  jmp     short loc_180096DD8
```
