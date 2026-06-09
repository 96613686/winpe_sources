# CdReadIoInput

- ea: `0x14000cc10`
- end: `0x14000cd2c`
- name: `CdReadIoInput`
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
- `0x14000aa00`
- `0x14000cc10`
- `0x14000d3e0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cca7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cca7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cd06`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cd06`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ccb8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000ccb8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ccfa`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ccfa`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14000cc4e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14000cc4e`
- `ntoskrnl!ProbeForWrite` at `0x14000cc9a`
- `ntoskrnl!ProbeForWrite` at `0x14000cc9a`

## pseudocode

```c
__int64 __fastcall CdReadIoInput(_QWORD *a1, char a2, void *a3, int a4, _QWORD *a5)
{
  __int64 v8; // rax
  unsigned int IoInput; // ebx
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
    ProbeForWrite(Address[1], (unsigned int)Length, 1u);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*a1, 0);
  v8 = CdpLookupIo(a1 + 5, Address);
  if ( v8 )
    IoInput = CdpReadIoInput(v8, a2, (char **)&Address[1], a5);
  else
    IoInput = -1073741536;
  ExReleasePushLockExclusiveEx(*a1, 0);
  KeLeaveCriticalRegion();
  return IoInput;
}

```

## disassembly

```asm
0x14000cc10  mov     [rsp+arg_0], rbx
0x14000cc15  mov     [rsp+arg_8], dl
0x14000cc19  push    rdi
0x14000cc1a  sub     rsp, 40h
0x14000cc1e  mov     rax, r8
0x14000cc21  movzx   ebx, dl
0x14000cc24  mov     rdi, rcx
0x14000cc27  xorps   xmm0, xmm0
0x14000cc2a  xor     ecx, ecx
0x14000cc2c  movups  xmmword ptr [rsp+48h+Address], xmm0
0x14000cc31  mov     [rsp+48h+Length], rcx
0x14000cc36  cmp     r9d, 18h
0x14000cc3a  jz      short loc_14000CC46
0x14000cc3c  mov     eax, 0C0000206h
0x14000cc41  jmp     loc_14000CD20
0x14000cc46  test    bl, bl
0x14000cc48  jz      short loc_14000CC74
0x14000cc4a  test    al, 3
0x14000cc4c  jz      short loc_14000CC5B
0x14000cc4e  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14000cc55  nop     dword ptr [rax+rax+00h]
0x14000cc5a  int     3; Trap to Debugger
0x14000cc5b  test    bl, bl
0x14000cc5d  jz      short loc_14000CC74
0x14000cc5f  mov     r8d, 18h; Size
0x14000cc65  mov     rdx, rax; Src
0x14000cc68  lea     rcx, [rsp+48h+Address]; void *
0x14000cc6d  call    RtlCopyFromUser
0x14000cc72  jmp     short loc_14000CC87
0x14000cc74  mov     r8d, 18h; Size
0x14000cc7a  mov     rdx, rax; Src
0x14000cc7d  lea     rcx, [rsp+48h+Address]; void *
0x14000cc82  call    RtlCopyVolatileMemory
0x14000cc87  test    bl, bl
0x14000cc89  jz      short loc_14000CCA7
0x14000cc8b  mov     edx, dword ptr [rsp+48h+Length]; Length
0x14000cc8f  mov     r8d, 1; Alignment
0x14000cc95  mov     rcx, [rsp+48h+Address+8]; Address
0x14000cc9a  call    cs:__imp_ProbeForWrite
0x14000cca1  nop     dword ptr [rax+rax+00h]
0x14000cca6  nop
0x14000cca7  call    cs:__imp_KeEnterCriticalRegion
0x14000ccae  nop     dword ptr [rax+rax+00h]
0x14000ccb3  xor     edx, edx
0x14000ccb5  mov     rcx, [rdi]
0x14000ccb8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000ccbf  nop     dword ptr [rax+rax+00h]
0x14000ccc4  lea     rcx, [rdi+28h]
0x14000ccc8  lea     rdx, [rsp+48h+Address]
0x14000cccd  call    CdpLookupIo
0x14000ccd2  test    rax, rax
0x14000ccd5  jnz     short loc_14000CCDE
0x14000ccd7  mov     ebx, 0C0000120h
0x14000ccdc  jmp     short loc_14000CCF5
0x14000ccde  mov     r9, [rsp+48h+arg_20]
0x14000cce3  lea     r8, [rsp+48h+Address+8]
0x14000cce8  movzx   edx, bl
0x14000cceb  mov     rcx, rax
0x14000ccee  call    CdpReadIoInput
0x14000ccf3  mov     ebx, eax
0x14000ccf5  xor     edx, edx
0x14000ccf7  mov     rcx, [rdi]
0x14000ccfa  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000cd01  nop     dword ptr [rax+rax+00h]
0x14000cd06  call    cs:__imp_KeLeaveCriticalRegion
0x14000cd0d  nop     dword ptr [rax+rax+00h]
0x14000cd12  mov     eax, ebx
0x14000cd14  mov     rbx, [rsp+48h+arg_0]
0x14000cd19  add     rsp, 40h
0x14000cd1d  pop     rdi
0x14000cd1e  retn
0x14000cd20  mov     rbx, [rsp+48h+arg_0]
0x14000cd25  add     rsp, 40h
0x14000cd29  pop     rdi
0x14000cd2a  retn
0x14000e710  push    rbp
0x14000e712  sub     rsp, 20h
0x14000e716  mov     rbp, rdx
0x14000e719  xor     eax, eax
0x14000e71b  cmp     [rbp+58h], al
0x14000e71e  setnz   al
0x14000e721  mov     [rbp+20h], eax
0x14000e724  mov     eax, [rbp+20h]
0x14000e727  add     rsp, 20h
0x14000e72b  pop     rbp
0x14000e72c  retn
```
