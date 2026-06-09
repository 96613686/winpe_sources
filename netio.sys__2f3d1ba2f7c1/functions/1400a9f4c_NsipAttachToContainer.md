# NsipAttachToContainer

- ea: `0x1400a9f4c`
- end: `0x1400a9fd6`
- name: `NsipAttachToContainer`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400205f0`

## callees

- `0x1400a9f4c`

## import_xrefs

- `ntoskrnl!PsGetSiloContext` at `0x1400a9f8a`
- `ntoskrnl!PsGetSiloContext` at `0x1400a9f8a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400a9fb1`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400a9fb1`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x1400a9f6d`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x1400a9f6d`

## pseudocode

```c
__int64 __fastcall NsipAttachToContainer(_QWORD *a1, unsigned int a2, _QWORD *a3)
{
  __int64 v4; // rbx
  unsigned int SiloMonitorContextSlot; // eax
  __int64 v7; // rbp
  int SiloContext; // ebx
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  v4 = a2;
  v10 = 0;
  SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(NsiContainerMonitor);
  v7 = (unsigned int)v4;
  SiloContext = PsGetSiloContext(*(_QWORD *)(a1[2] + 8 * v4), SiloMonitorContextSlot, &v10);
  if ( SiloContext >= 0 )
  {
    if ( a3 )
      *a3 = v10;
    a1[3] = PsAttachSiloToCurrentThread(*(_QWORD *)(a1[2] + 8 * v7));
    a1[4] = v10;
  }
  return (unsigned int)SiloContext;
}

```

## disassembly

```asm
0x1400a9f4c  push    rbx
0x1400a9f4e  push    rbp
0x1400a9f4f  push    rsi
0x1400a9f50  push    rdi
0x1400a9f51  sub     rsp, 28h
0x1400a9f55  mov     rdi, rcx
0x1400a9f58  mov     ebx, edx
0x1400a9f5a  mov     rcx, cs:NsiContainerMonitor
0x1400a9f61  mov     rsi, r8
0x1400a9f64  mov     [rsp+48h+arg_0], 0
0x1400a9f6d  call    cs:__imp_PsGetSiloMonitorContextSlot
0x1400a9f74  nop     dword ptr [rax+rax+00h]
0x1400a9f79  mov     rcx, [rdi+10h]
0x1400a9f7d  lea     r8, [rsp+48h+arg_0]
0x1400a9f82  mov     edx, eax
0x1400a9f84  mov     ebp, ebx
0x1400a9f86  mov     rcx, [rcx+rbx*8]
0x1400a9f8a  call    cs:__imp_PsGetSiloContext
0x1400a9f91  nop     dword ptr [rax+rax+00h]
0x1400a9f96  mov     ebx, eax
0x1400a9f98  test    eax, eax
0x1400a9f9a  js      short loc_1400A9FCA
0x1400a9f9c  test    rsi, rsi
0x1400a9f9f  jz      short loc_1400A9FA9
0x1400a9fa1  mov     rcx, [rsp+48h+arg_0]
0x1400a9fa6  mov     [rsi], rcx
0x1400a9fa9  mov     rcx, [rdi+10h]
0x1400a9fad  mov     rcx, [rcx+rbp*8]
0x1400a9fb1  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400a9fb8  nop     dword ptr [rax+rax+00h]
0x1400a9fbd  mov     [rdi+18h], rax
0x1400a9fc1  mov     rax, [rsp+48h+arg_0]
0x1400a9fc6  mov     [rdi+20h], rax
0x1400a9fca  mov     eax, ebx
0x1400a9fcc  add     rsp, 28h
0x1400a9fd0  pop     rdi
0x1400a9fd1  pop     rsi
0x1400a9fd2  pop     rbp
0x1400a9fd3  pop     rbx
0x1400a9fd4  retn
```
