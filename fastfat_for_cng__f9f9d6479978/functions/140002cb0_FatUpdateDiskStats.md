# FatUpdateDiskStats

- ea: `0x140002cb0`
- end: `0x140002de3`
- name: `FatUpdateDiskStats`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14002d918`

## callees

- `0x140002cb0`

## import_xrefs

- `ntoskrnl!PsUpdateDiskCounters` at `0x140002dcb`
- `ntoskrnl!PsUpdateDiskCounters` at `0x140002dcb`
- `ntoskrnl!PsGetThreadProcess` at `0x140002da7`
- `ntoskrnl!PsGetThreadProcess` at `0x140002da7`
- `ntoskrnl!IoIsSystemThread` at `0x140002cdb`
- `ntoskrnl!IoIsSystemThread` at `0x140002d00`
- `ntoskrnl!IoIsSystemThread` at `0x140002d1d`
- `ntoskrnl!IoIsSystemThread` at `0x140002d72`
- `ntoskrnl!IoIsSystemThread` at `0x140002cdb`
- `ntoskrnl!IoIsSystemThread` at `0x140002d00`
- `ntoskrnl!IoIsSystemThread` at `0x140002d1d`
- `ntoskrnl!IoIsSystemThread` at `0x140002d72`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140002d31`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140002d55`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140002d87`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140002d31`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140002d55`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140002d87`

## pseudocode

```c
char __fastcall FatUpdateDiskStats(__int64 a1, IRP *a2, unsigned int a3)
{
  PIRP TopLevelIrp; // rax
  struct _KTHREAD *v5; // rcx
  int v6; // edi
  __int64 v7; // rsi
  __int64 v8; // r14
  unsigned int v9; // ebp
  struct _KTHREAD *CurrentThread; // rcx
  bool v11; // zf
  struct _KTHREAD *Thread; // rcx
  PEPROCESS ThreadProcess; // rax

  LOBYTE(TopLevelIrp) = *(_BYTE *)(a1 + 64);
  if ( (_BYTE)TopLevelIrp != 3 )
  {
    if ( (_BYTE)TopLevelIrp != 4 )
      return (char)TopLevelIrp;
    v9 = 0;
    v7 = a3;
    v8 = 0;
    v6 = 1;
    TopLevelIrp = IoGetTopLevelIrp();
    if ( TopLevelIrp == a2 )
    {
      Thread = a2->Tail.Overlay.Thread;
      if ( Thread )
      {
        LOBYTE(TopLevelIrp) = IoIsSystemThread(Thread);
        if ( !(_BYTE)TopLevelIrp )
          goto LABEL_4;
      }
      goto LABEL_15;
    }
    TopLevelIrp = IoGetTopLevelIrp();
    v11 = TopLevelIrp == (PIRP)3;
LABEL_14:
    if ( !v11 )
      return (char)TopLevelIrp;
LABEL_15:
    CurrentThread = KeGetCurrentThread();
    goto LABEL_16;
  }
  v5 = a2->Tail.Overlay.Thread;
  v6 = 0;
  v7 = 0;
  v8 = a3;
  v9 = 1;
  if ( v5 )
  {
    LOBYTE(TopLevelIrp) = IoIsSystemThread(v5);
    if ( !(_BYTE)TopLevelIrp )
    {
LABEL_4:
      CurrentThread = a2->Tail.Overlay.Thread;
      goto LABEL_16;
    }
  }
  LOBYTE(TopLevelIrp) = IoIsSystemThread(KeGetCurrentThread());
  CurrentThread = KeGetCurrentThread();
  if ( (_BYTE)TopLevelIrp )
  {
    LOBYTE(TopLevelIrp) = IoIsSystemThread(CurrentThread);
    if ( !(_BYTE)TopLevelIrp )
      return (char)TopLevelIrp;
    TopLevelIrp = IoGetTopLevelIrp();
    v11 = TopLevelIrp == a2;
    goto LABEL_14;
  }
LABEL_16:
  if ( CurrentThread )
  {
    ThreadProcess = PsGetThreadProcess(CurrentThread);
    LOBYTE(TopLevelIrp) = PsUpdateDiskCounters(ThreadProcess, v8, v7, v9, v6, 0);
  }
  return (char)TopLevelIrp;
}

```

## disassembly

```asm
0x140002cb0  push    rbx
0x140002cb2  push    rbp
0x140002cb3  push    rsi
0x140002cb4  push    rdi
0x140002cb5  push    r14
0x140002cb7  sub     rsp, 30h
0x140002cbb  mov     al, [rcx+40h]
0x140002cbe  mov     rbx, rdx
0x140002cc1  cmp     al, 3
0x140002cc3  jnz     short loc_140002D42
0x140002cc5  mov     rcx, [rdx+98h]; Thread
0x140002ccc  xor     edi, edi
0x140002cce  xor     esi, esi
0x140002cd0  mov     r14d, r8d
0x140002cd3  lea     ebp, [rdi+1]
0x140002cd6  test    rcx, rcx
0x140002cd9  jz      short loc_140002CF7
0x140002cdb  call    cs:__imp_IoIsSystemThread
0x140002ce2  nop     dword ptr [rax+rax+00h]
0x140002ce7  test    al, al
0x140002ce9  jnz     short loc_140002CF7
0x140002ceb  mov     rcx, [rbx+98h]
0x140002cf2  jmp     loc_140002DA2
0x140002cf7  mov     rcx, gs:188h; Thread
0x140002d00  call    cs:__imp_IoIsSystemThread
0x140002d07  nop     dword ptr [rax+rax+00h]
0x140002d0c  mov     rcx, gs:188h; Thread
0x140002d15  test    al, al
0x140002d17  jz      loc_140002DA2
0x140002d1d  call    cs:__imp_IoIsSystemThread
0x140002d24  nop     dword ptr [rax+rax+00h]
0x140002d29  test    al, al
0x140002d2b  jz      loc_140002DD7
0x140002d31  call    cs:__imp_IoGetTopLevelIrp
0x140002d38  nop     dword ptr [rax+rax+00h]
0x140002d3d  cmp     rax, rbx
0x140002d40  jmp     short loc_140002D97
0x140002d42  cmp     al, 4
0x140002d44  jnz     loc_140002DD7
0x140002d4a  xor     ebp, ebp
0x140002d4c  mov     esi, r8d
0x140002d4f  xor     r14d, r14d
0x140002d52  lea     edi, [rbp+1]
0x140002d55  call    cs:__imp_IoGetTopLevelIrp
0x140002d5c  nop     dword ptr [rax+rax+00h]
0x140002d61  cmp     rax, rbx
0x140002d64  jnz     short loc_140002D87
0x140002d66  mov     rcx, [rbx+98h]; Thread
0x140002d6d  test    rcx, rcx
0x140002d70  jz      short loc_140002D99
0x140002d72  call    cs:__imp_IoIsSystemThread
0x140002d79  nop     dword ptr [rax+rax+00h]
0x140002d7e  test    al, al
0x140002d80  jnz     short loc_140002D99
0x140002d82  jmp     loc_140002CEB
0x140002d87  call    cs:__imp_IoGetTopLevelIrp
0x140002d8e  nop     dword ptr [rax+rax+00h]
0x140002d93  cmp     rax, 3
0x140002d97  jnz     short loc_140002DD7
0x140002d99  mov     rcx, gs:188h; Thread
0x140002da2  test    rcx, rcx
0x140002da5  jz      short loc_140002DD7
0x140002da7  call    cs:__imp_PsGetThreadProcess
0x140002dae  nop     dword ptr [rax+rax+00h]
0x140002db3  mov     [rsp+58h+var_30], 0
0x140002dbb  mov     r9d, ebp
0x140002dbe  mov     rcx, rax
0x140002dc1  mov     [rsp+58h+var_38], edi
0x140002dc5  mov     r8, rsi
0x140002dc8  mov     rdx, r14
0x140002dcb  call    cs:__imp_PsUpdateDiskCounters
0x140002dd2  nop     dword ptr [rax+rax+00h]
0x140002dd7  add     rsp, 30h
0x140002ddb  pop     r14
0x140002ddd  pop     rdi
0x140002dde  pop     rsi
0x140002ddf  pop     rbp
0x140002de0  pop     rbx
0x140002de1  retn
```
