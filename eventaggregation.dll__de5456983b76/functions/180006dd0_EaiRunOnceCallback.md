# EaiRunOnceCallback

- ea: `0x180006dd0`
- end: `0x180006e11`
- name: `EaiRunOnceCallback`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x180006de5`
- `ntdll!RtlInitializeSRWLock` at `0x180006de5`
- `ntdll!RtlCreateHashTable` at `0x180006df7`
- `ntdll!RtlCreateHashTable` at `0x180006df7`

## pseudocode

```c
_BOOL8 EaiRunOnceCallback()
{
  *(_OWORD *)AggregateEventListLock = 0;
  RtlInitializeSRWLock(AggregateEventListLock);
  return (unsigned __int8)RtlCreateHashTable(&qword_180012148, 0, 0) != 0;
}

```

## disassembly

```asm
0x180006dd0  sub     rsp, 28h
0x180006dd4  xorps   xmm0, xmm0
0x180006dd7  lea     rcx, AggregateEventListLock
0x180006dde  movups  xmmword ptr cs:AggregateEventListLock, xmm0
0x180006de5  call    cs:__imp_RtlInitializeSRWLock
0x180006deb  xor     r8d, r8d
0x180006dee  lea     rcx, qword_180012148
0x180006df5  xor     edx, edx
0x180006df7  call    cs:__imp_RtlCreateHashTable
0x180006dfd  movzx   edx, al
0x180006e00  xor     ecx, ecx
0x180006e02  test    dl, dl
0x180006e04  mov     eax, 1
0x180006e09  cmovz   eax, ecx
0x180006e0c  add     rsp, 28h
0x180006e10  retn
```
