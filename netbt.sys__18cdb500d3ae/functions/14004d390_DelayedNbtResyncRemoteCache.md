# DelayedNbtResyncRemoteCache

- ea: `0x14004d390`
- end: `0x14004d49f`
- name: `DelayedNbtResyncRemoteCache`
- size: `271`
- prototype: `void()`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140027200`
- `0x140047f20`

## callees

- `0x140014a40`
- `0x14001570c`
- `0x140031140`
- `0x14004d390`
- `0x14004d4b0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d422`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d470`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d422`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d470`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d416`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d464`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d416`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d464`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004d3c5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004d3c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004d3b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004d3b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d491`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004d491`
- `ntoskrnl!ExAllocatePool2` at `0x14004d3fb`
- `ntoskrnl!ExAllocatePool2` at `0x14004d3fb`

## pseudocode

```c
void DelayedNbtResyncRemoteCache()
{
  __int64 v0; // rbx
  __int64 v1; // rdx
  void *Pool2; // rdi

  RemoteHashTimeout(qword_140039468, 0, 0);
  RemovePreloads();
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  if ( !Src )
    goto LABEL_5;
  v0 = -1;
  v1 = -1;
  do
    ++v1;
  while ( *((_BYTE *)Src + v1) );
  Pool2 = (void *)ExAllocatePool2(64, v1 + 1, 858939982);
  if ( Pool2 )
  {
    do
      ++v0;
    while ( *((_BYTE *)Src + v0) );
    memmove(Pool2, Src, v0 + 1);
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    PrimeCache((__int64)Pool2, 0, 10);
    ExFreePoolWithTag(Pool2, 0);
  }
  else
  {
LABEL_5:
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x14004d390  mov     [rsp+arg_0], rbx
0x14004d395  push    rdi
0x14004d396  sub     rsp, 20h
0x14004d39a  mov     rcx, cs:qword_140039468
0x14004d3a1  xor     r8d, r8d
0x14004d3a4  xor     edx, edx
0x14004d3a6  call    RemoteHashTimeout
0x14004d3ab  call    RemovePreloads
0x14004d3b0  call    cs:__imp_KeEnterCriticalRegion
0x14004d3b7  nop     dword ptr [rax+rax+00h]
0x14004d3bc  mov     dl, 1; Wait
0x14004d3be  lea     rcx, Resource; Resource
0x14004d3c5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004d3cc  nop     dword ptr [rax+rax+00h]
0x14004d3d1  mov     rax, cs:Src
0x14004d3d8  test    rax, rax
0x14004d3db  jz      short loc_14004D40F
0x14004d3dd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14004d3e1  mov     rdx, rbx
0x14004d3e4  inc     rdx
0x14004d3e7  cmp     byte ptr [rax+rdx], 0
0x14004d3eb  jnz     short loc_14004D3E4
0x14004d3ed  inc     rdx
0x14004d3f0  mov     ecx, 40h ; '@'
0x14004d3f5  mov     r8d, 3332624Eh
0x14004d3fb  call    cs:__imp_ExAllocatePool2
0x14004d402  nop     dword ptr [rax+rax+00h]
0x14004d407  mov     rdi, rax
0x14004d40a  test    rax, rax
0x14004d40d  jnz     short loc_14004D43A
0x14004d40f  lea     rcx, Resource; Resource
0x14004d416  call    cs:__imp_ExReleaseResourceLite
0x14004d41d  nop     dword ptr [rax+rax+00h]
0x14004d422  call    cs:__imp_KeLeaveCriticalRegion
0x14004d429  nop     dword ptr [rax+rax+00h]
0x14004d42e  mov     rbx, [rsp+28h+arg_0]
0x14004d433  add     rsp, 20h
0x14004d437  pop     rdi
0x14004d438  retn
0x14004d43a  mov     rax, cs:Src
0x14004d441  inc     rbx
0x14004d444  cmp     byte ptr [rax+rbx], 0
0x14004d448  jnz     short loc_14004D441
0x14004d44a  mov     rdx, cs:Src; Src
0x14004d451  lea     r8, [rbx+1]; Size
0x14004d455  mov     rcx, rdi; void *
0x14004d458  call    memmove
0x14004d45d  lea     rcx, Resource; Resource
0x14004d464  call    cs:__imp_ExReleaseResourceLite
0x14004d46b  nop     dword ptr [rax+rax+00h]
0x14004d470  call    cs:__imp_KeLeaveCriticalRegion
0x14004d477  nop     dword ptr [rax+rax+00h]
0x14004d47c  xor     r9d, r9d
0x14004d47f  mov     r8b, 0Ah
0x14004d482  xor     edx, edx
0x14004d484  mov     rcx, rdi
0x14004d487  call    PrimeCache
0x14004d48c  xor     edx, edx; Tag
0x14004d48e  mov     rcx, rdi; P
0x14004d491  call    cs:__imp_ExFreePoolWithTag
0x14004d498  nop     dword ptr [rax+rax+00h]
0x14004d49d  jmp     short loc_14004D42E
```
