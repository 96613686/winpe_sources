# ReferenceTunnel

- ea: `0x14001c400`
- end: `0x14001c465`
- name: `ReferenceTunnel`
- size: `101`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fd0c`
- `0x140011288`
- `0x140011518`
- `0x140012400`
- `0x140015050`
- `0x140015de4`
- `0x1400171e0`
- `0x1400175f0`
- `0x140019a80`
- `0x14001a640`
- `0x14001ac30`

## callees

- `0x14001c400`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001c443`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c443`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c41d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c41d`

## pseudocode

```c
__int64 __fastcall ReferenceTunnel(__int64 a1, char a2)
{
  __int64 v3; // rdi
  unsigned int v4; // ebx

  if ( a2 )
  {
    return (unsigned int)++*(_DWORD *)(a1 + 20);
  }
  else
  {
    v3 = *(_QWORD *)(a1 + 24);
    *(_BYTE *)(v3 + 152) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 144));
    v4 = ++*(_DWORD *)(a1 + 20);
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 144), *(_BYTE *)(v3 + 152));
    return v4;
  }
}

```

## disassembly

```asm
0x14001c400  push    rbx
0x14001c402  sub     rsp, 20h
0x14001c406  mov     rbx, rcx
0x14001c409  test    dl, dl
0x14001c40b  jnz     short loc_14001C45D
0x14001c40d  mov     [rsp+28h+arg_0], rdi
0x14001c412  mov     rdi, [rcx+18h]
0x14001c416  lea     rcx, [rdi+90h]; SpinLock
0x14001c41d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001c424  nop     dword ptr [rax+rax+00h]
0x14001c429  mov     [rdi+98h], al
0x14001c42f  lea     rcx, [rdi+90h]; SpinLock
0x14001c436  inc     dword ptr [rbx+14h]
0x14001c439  movzx   edx, byte ptr [rdi+98h]; NewIrql
0x14001c440  mov     ebx, [rbx+14h]
0x14001c443  call    cs:__imp_KeReleaseSpinLock
0x14001c44a  nop     dword ptr [rax+rax+00h]
0x14001c44f  mov     rdi, [rsp+28h+arg_0]
0x14001c454  mov     eax, ebx
0x14001c456  add     rsp, 20h
0x14001c45a  pop     rbx
0x14001c45b  retn
0x14001c45d  inc     dword ptr [rcx+14h]
0x14001c460  mov     eax, [rcx+14h]
0x14001c463  jmp     short loc_14001C456
```
