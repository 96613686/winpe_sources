# CdWriteIoOutput

- ea: `0x14000cd40`
- end: `0x14000ce5c`
- name: `CdWriteIoOutput`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c870`

## callees

- `0x140001154`
- `0x140001500`
- `0x14000cd40`
- `0x14000d3e0`
- `0x14000d4a0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cdd7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cdd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ce36`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ce36`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000cde8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000cde8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ce2a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ce2a`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14000cd7e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14000cd7e`
- `ntoskrnl!ProbeForRead` at `0x14000cdca`
- `ntoskrnl!ProbeForRead` at `0x14000cdca`

## pseudocode

```c
__int64 __fastcall CdWriteIoOutput(_QWORD *a1, unsigned __int8 a2, void *a3, int a4, __int64 a5)
{
  __int64 v8; // rax
  unsigned int v9; // ebx
  volatile void *Address[2]; // [rsp+28h] [rbp-20h] BYREF
  SIZE_T Length; // [rsp+38h] [rbp-10h]

  *(_OWORD *)Address = 0;
  Length = 0;
  if ( a4 != 24 )
    return 3221225990LL;
  if ( a2 )
  {
    if ( ((unsigned __int8)a3 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(Address, a3, 0x18u);
  }
  else
  {
    RtlCopyVolatileMemory(Address, a3, 0x18u);
  }
  if ( a2 )
    ProbeForRead(Address[1], (unsigned int)Length, 1u);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*a1, 0);
  v8 = CdpLookupIo(a1 + 5, Address);
  if ( v8 )
    v9 = CdpWriteIoOutput(v8, a2, &Address[1], a5);
  else
    v9 = -1073741536;
  ExReleasePushLockExclusiveEx(*a1, 0);
  KeLeaveCriticalRegion();
  return v9;
}

```

## disassembly

```asm
0x14000cd40  mov     [rsp+arg_0], rbx
0x14000cd45  mov     [rsp+arg_8], dl
0x14000cd49  push    rdi
0x14000cd4a  sub     rsp, 40h
0x14000cd4e  mov     rax, r8
0x14000cd51  movzx   ebx, dl
0x14000cd54  mov     rdi, rcx
0x14000cd57  xorps   xmm0, xmm0
0x14000cd5a  xor     ecx, ecx
0x14000cd5c  movups  xmmword ptr [rsp+48h+Address], xmm0
0x14000cd61  mov     [rsp+48h+Length], rcx
0x14000cd66  cmp     r9d, 18h
0x14000cd6a  jz      short loc_14000CD76
0x14000cd6c  mov     eax, 0C0000206h
0x14000cd71  jmp     loc_14000CE50
0x14000cd76  test    bl, bl
0x14000cd78  jz      short loc_14000CDA4
0x14000cd7a  test    al, 3
0x14000cd7c  jz      short loc_14000CD8B
0x14000cd7e  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14000cd85  nop     dword ptr [rax+rax+00h]
0x14000cd8a  int     3; Trap to Debugger
0x14000cd8b  test    bl, bl
0x14000cd8d  jz      short loc_14000CDA4
0x14000cd8f  mov     r8d, 18h; Size
0x14000cd95  mov     rdx, rax; Src
0x14000cd98  lea     rcx, [rsp+48h+Address]; void *
0x14000cd9d  call    RtlCopyFromUser
0x14000cda2  jmp     short loc_14000CDB7
0x14000cda4  mov     r8d, 18h; Size
0x14000cdaa  mov     rdx, rax; Src
0x14000cdad  lea     rcx, [rsp+48h+Address]; void *
0x14000cdb2  call    RtlCopyVolatileMemory
0x14000cdb7  test    bl, bl
0x14000cdb9  jz      short loc_14000CDD7
0x14000cdbb  mov     edx, dword ptr [rsp+48h+Length]; Length
0x14000cdbf  mov     r8d, 1; Alignment
0x14000cdc5  mov     rcx, [rsp+48h+Address+8]; Address
0x14000cdca  call    cs:__imp_ProbeForRead
0x14000cdd1  nop     dword ptr [rax+rax+00h]
0x14000cdd6  nop
0x14000cdd7  call    cs:__imp_KeEnterCriticalRegion
0x14000cdde  nop     dword ptr [rax+rax+00h]
0x14000cde3  xor     edx, edx
0x14000cde5  mov     rcx, [rdi]
0x14000cde8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000cdef  nop     dword ptr [rax+rax+00h]
0x14000cdf4  lea     rcx, [rdi+28h]
0x14000cdf8  lea     rdx, [rsp+48h+Address]
0x14000cdfd  call    CdpLookupIo
0x14000ce02  test    rax, rax
0x14000ce05  jnz     short loc_14000CE0E
0x14000ce07  mov     ebx, 0C0000120h
0x14000ce0c  jmp     short loc_14000CE25
0x14000ce0e  mov     r9, [rsp+48h+arg_20]
0x14000ce13  lea     r8, [rsp+48h+Address+8]
0x14000ce18  movzx   edx, bl
0x14000ce1b  mov     rcx, rax
0x14000ce1e  call    CdpWriteIoOutput
0x14000ce23  mov     ebx, eax
0x14000ce25  xor     edx, edx
0x14000ce27  mov     rcx, [rdi]
0x14000ce2a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000ce31  nop     dword ptr [rax+rax+00h]
0x14000ce36  call    cs:__imp_KeLeaveCriticalRegion
0x14000ce3d  nop     dword ptr [rax+rax+00h]
0x14000ce42  mov     eax, ebx
0x14000ce44  mov     rbx, [rsp+48h+arg_0]
0x14000ce49  add     rsp, 40h
0x14000ce4d  pop     rdi
0x14000ce4e  retn
0x14000ce50  mov     rbx, [rsp+48h+arg_0]
0x14000ce55  add     rsp, 40h
0x14000ce59  pop     rdi
0x14000ce5a  retn
0x14000e740  push    rbp
0x14000e742  sub     rsp, 20h
0x14000e746  mov     rbp, rdx
0x14000e749  xor     eax, eax
0x14000e74b  cmp     [rbp+58h], al
0x14000e74e  setnz   al
0x14000e751  mov     [rbp+20h], eax
0x14000e754  mov     eax, [rbp+20h]
0x14000e757  add     rsp, 20h
0x14000e75b  pop     rbp
0x14000e75c  retn
```
