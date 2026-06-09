# SetupVcComplete

- ea: `0x140011f9c`
- end: `0x140012042`
- name: `SetupVcComplete`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140010f90`
- `0x140011518`

## callees

- `0x140010318`
- `0x1400109d0`
- `0x140011144`
- `0x140011f9c`
- `0x140012078`
- `0x140015bbc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140012008`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012008`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011fcf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011fcf`
- `NDIS!NdisFreeNetBufferList` at `0x140012022`
- `NDIS!NdisFreeNetBufferList` at `0x140012022`

## pseudocode

```c
__int64 __fastcall SetupVcComplete(__int64 a1, __int64 a2)
{
  char v4; // bl
  __int64 v5; // rdx

  if ( (unsigned int)ReserveCallIdSlot(a2) )
    *(_DWORD *)(a2 + 200) = 8;
  else
    ActivateCallIdSlot(a2);
  *(_BYTE *)(a1 + 40) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
  v4 = ReceiveControlExpected(a1, a2, **(_QWORD **)(a2 + 136), *(_QWORD *)(a2 + 136) + 64LL);
  CompleteVcs(a1);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), *(_BYTE *)(a1 + 40));
  if ( v4 )
    NdisFreeNetBufferList(**(PNET_BUFFER_LIST **)(a2 + 136));
  LOBYTE(v5) = 1;
  return UnlockIcs(a2, v5);
}

```

## disassembly

```asm
0x140011f9c  push    rbx
0x140011f9e  push    rbp
0x140011f9f  push    rsi
0x140011fa0  push    rdi
0x140011fa1  sub     rsp, 28h
0x140011fa5  mov     rbp, rcx
0x140011fa8  mov     rsi, rdx
0x140011fab  mov     rcx, rdx
0x140011fae  call    ReserveCallIdSlot
0x140011fb3  test    eax, eax
0x140011fb5  jnz     short loc_140011FC1
0x140011fb7  mov     rcx, rsi
0x140011fba  call    ActivateCallIdSlot
0x140011fbf  jmp     short loc_140011FCB
0x140011fc1  mov     dword ptr [rsi+0C8h], 8
0x140011fcb  lea     rcx, [rbp+20h]; SpinLock
0x140011fcf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011fd6  nop     dword ptr [rax+rax+00h]
0x140011fdb  mov     [rbp+28h], al
0x140011fde  mov     rdx, rsi
0x140011fe1  mov     r8, [rsi+88h]
0x140011fe8  mov     rcx, rbp
0x140011feb  lea     r9, [r8+40h]
0x140011fef  mov     r8, [r8]
0x140011ff2  call    ReceiveControlExpected
0x140011ff7  mov     rcx, rbp
0x140011ffa  mov     bl, al
0x140011ffc  call    CompleteVcs
0x140012001  mov     dl, [rbp+28h]; NewIrql
0x140012004  lea     rcx, [rbp+20h]; SpinLock
0x140012008  call    cs:__imp_KeReleaseSpinLock
0x14001200f  nop     dword ptr [rax+rax+00h]
0x140012014  test    bl, bl
0x140012016  jz      short loc_14001202E
0x140012018  mov     rcx, [rsi+88h]
0x14001201f  mov     rcx, [rcx]; NetBufferList
0x140012022  call    cs:__imp_NdisFreeNetBufferList
0x140012029  nop     dword ptr [rax+rax+00h]
0x14001202e  mov     dl, 1
0x140012030  mov     rcx, rsi
0x140012033  call    UnlockIcs
0x140012038  add     rsp, 28h
0x14001203c  pop     rdi
0x14001203d  pop     rsi
0x14001203e  pop     rbp
0x14001203f  pop     rbx
0x140012040  retn
```
