# FIPfFilePfContextDereference

- ea: `0x140002d64`
- end: `0x140002e2a`
- name: `FIPfFilePfContextDereference`
- size: `198`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140010350`
- `0x140015460`
- `0x140015950`
- `0x140017510`

## callees

- `0x140002d64`
- `0x1400033f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002df0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002df0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002ddf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002e0d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002ddf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002e0d`
- `ntoskrnl!ExfReleasePushLock` at `0x140002dd3`
- `ntoskrnl!ExfReleasePushLock` at `0x140002e01`
- `ntoskrnl!ExfReleasePushLock` at `0x140002dd3`
- `ntoskrnl!ExfReleasePushLock` at `0x140002e01`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002d89`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002d89`
- `ntoskrnl!ExfAcquirePushLockExclusive` at `0x140002d9c`
- `ntoskrnl!ExfAcquirePushLockExclusive` at `0x140002d9c`

## pseudocode

```c
void __fastcall FIPfFilePfContextDereference(__int64 a1, __int64 a2)
{
  _DWORD *v3; // rsi

  if ( _InterlockedDecrement((volatile signed __int32 *)(a1 + 20)) == 1 )
  {
    KeEnterCriticalRegion();
    ExfAcquirePushLockExclusive(a2 + 40);
    if ( (*(_DWORD *)(a2 + 56) & 0x80u) != 0 && (v3 = *(_DWORD **)(a2 + 72), v3[5] == 1) )
    {
      FIStreamVolatileBitFieldBitSet(a2, 7, 0);
      *(_QWORD *)(a2 + 72) = 0;
      ExfReleasePushLock(a2 + 40);
      KeLeaveCriticalRegion();
      ExFreePoolWithTag(v3, 0);
    }
    else
    {
      ExfReleasePushLock(a2 + 40);
      KeLeaveCriticalRegion();
    }
  }
}

```

## disassembly

```asm
0x140002d64  mov     [rsp+arg_0], rbx
0x140002d69  mov     [rsp+arg_8], rsi
0x140002d6e  push    rdi
0x140002d6f  sub     rsp, 20h
0x140002d73  mov     rbx, rdx
0x140002d76  or      eax, 0FFFFFFFFh
0x140002d79  lock xadd [rcx+14h], eax
0x140002d7e  dec     eax
0x140002d80  cmp     eax, 1
0x140002d83  jnz     loc_140002E19
0x140002d89  call    cs:__imp_KeEnterCriticalRegion
0x140002d90  nop     dword ptr [rax+rax+00h]
0x140002d95  lea     rdi, [rbx+28h]
0x140002d99  mov     rcx, rdi
0x140002d9c  call    cs:__imp_ExfAcquirePushLockExclusive
0x140002da3  nop     dword ptr [rax+rax+00h]
0x140002da8  mov     eax, [rbx+38h]
0x140002dab  test    al, al
0x140002dad  jns     short loc_140002DFE
0x140002daf  mov     rsi, [rbx+48h]
0x140002db3  cmp     dword ptr [rsi+14h], 1
0x140002db7  jnz     short loc_140002DFE
0x140002db9  xor     r8d, r8d
0x140002dbc  mov     rcx, rbx
0x140002dbf  lea     edx, [r8+7]
0x140002dc3  call    FIStreamVolatileBitFieldBitSet
0x140002dc8  mov     rcx, rdi
0x140002dcb  mov     qword ptr [rbx+48h], 0
0x140002dd3  call    cs:__imp_ExfReleasePushLock
0x140002dda  nop     dword ptr [rax+rax+00h]
0x140002ddf  call    cs:__imp_KeLeaveCriticalRegion
0x140002de6  nop     dword ptr [rax+rax+00h]
0x140002deb  xor     edx, edx; Tag
0x140002ded  mov     rcx, rsi; P
0x140002df0  call    cs:__imp_ExFreePoolWithTag
0x140002df7  nop     dword ptr [rax+rax+00h]
0x140002dfc  jmp     short loc_140002E19
0x140002dfe  mov     rcx, rdi
0x140002e01  call    cs:__imp_ExfReleasePushLock
0x140002e08  nop     dword ptr [rax+rax+00h]
0x140002e0d  call    cs:__imp_KeLeaveCriticalRegion
0x140002e14  nop     dword ptr [rax+rax+00h]
0x140002e19  mov     rbx, [rsp+28h+arg_0]
0x140002e1e  mov     rsi, [rsp+28h+arg_8]
0x140002e23  add     rsp, 20h
0x140002e27  pop     rdi
0x140002e28  retn
```
