# NbtDereferenceName

- ea: `0x140007ed8`
- end: `0x140007ff2`
- name: `NbtDereferenceName`
- size: `282`
- prototype: `__int64 __usercall@<rax>(PVOID P@<rcx>, __int64)`
- caller_count: `31`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140004038`
- `0x14000699c`
- `0x140006e2c`
- `0x140007354`
- `0x140008160`
- `0x140009844`
- `0x140009ee0`
- `0x14000ebe0`
- `0x14000efd4`
- `0x140014a40`
- `0x140015818`
- `0x140017214`
- `0x140017a3c`
- `0x140017d80`
- `0x140018ea0`
- `0x14001e8f4`
- `0x140020900`
- `0x140021ff8`
- `0x140022d04`
- `0x1400232bc`
- `0x140025c84`
- `0x140028580`
- `0x1400288b8`
- `0x140029d28`
- `0x14002a8c0`
- `0x14002ab80`
- `0x14002b9c8`
- `0x14002e5a8`
- `0x140044334`
- `0x140045570`
- `0x1400485e8`

## callees

- `0x140007ed8`
- `0x140007ff8`
- `0x140008110`
- `0x1400089c8`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007f73`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007f73`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007f5e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007fe1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007f5e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007fe1`

## pseudocode

```c
void __fastcall NbtDereferenceName(PVOID P, int a2, char a3, char a4, __int64 a5)
{
  KIRQL v8; // si

  v8 = -1;
  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      (_DWORD)P,
      81,
      (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
      (_DWORD)P,
      *((_DWORD *)P + 5),
      *((_DWORD *)P + 5) - 1,
      a4,
      a5);
  if ( !a3 )
    v8 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( *((_DWORD *)P + 4) == -87097344 )
  {
    if ( a2 == 1 )
    {
      --dword_140039760;
    }
    else if ( ((a2 - 2) & 0xFFFFFFFB) == 0 )
    {
      ++dword_140039760;
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 5, 0xFFFFFFFF) == 1 )
  {
    NbtUnlinkNameFromHashTable((__int64 *)P);
    if ( !a3 )
      KeReleaseSpinLock(&SpinLock, v8);
    NbtFreeNameAddr(P);
  }
  else
  {
    NbtCheckNameAddrTimer(P);
    if ( !a3 )
      KeReleaseSpinLock(&SpinLock, v8);
  }
}

```

## disassembly

```asm
0x140007ed8  push    rbx
0x140007eda  push    rbp
0x140007edb  push    rsi
0x140007edc  push    rdi
0x140007edd  sub     rsp, 48h
0x140007ee1  mov     dil, r8b
0x140007ee4  mov     ebp, edx
0x140007ee6  mov     rbx, rcx
0x140007ee9  mov     sil, 0FFh
0x140007eec  test    byte ptr cs:xmmword_140038420+9, 40h
0x140007ef3  jnz     loc_140007F8F
0x140007ef9  test    dil, dil
0x140007efc  jz      short loc_140007F6C
0x140007efe  cmp     dword ptr [rbx+10h], 0FACF0000h
0x140007f05  jnz     short loc_140007F1A
0x140007f07  cmp     ebp, 1
0x140007f0a  jz      short loc_140007F87
0x140007f0c  lea     eax, [rbp-2]
0x140007f0f  test    eax, 0FFFFFFFBh
0x140007f14  jz      loc_140007FCC
0x140007f1a  or      eax, 0FFFFFFFFh
0x140007f1d  lock xadd [rbx+14h], eax
0x140007f22  mov     rcx, rbx
0x140007f25  cmp     eax, 1
0x140007f28  jnz     short loc_140007F4A
0x140007f2a  call    NbtUnlinkNameFromHashTable
0x140007f2f  test    dil, dil
0x140007f32  jz      loc_140007FD7
0x140007f38  mov     rcx, rbx; P
0x140007f3b  call    NbtFreeNameAddr
0x140007f40  add     rsp, 48h
0x140007f44  pop     rdi
0x140007f45  pop     rsi
0x140007f46  pop     rbp
0x140007f47  pop     rbx
0x140007f48  retn
0x140007f4a  call    NbtCheckNameAddrTimer
0x140007f4f  test    dil, dil
0x140007f52  jnz     short loc_140007F40
0x140007f54  mov     dl, sil; NewIrql
0x140007f57  lea     rcx, SpinLock; SpinLock
0x140007f5e  call    cs:__imp_KeReleaseSpinLock
0x140007f65  nop     dword ptr [rax+rax+00h]
0x140007f6a  jmp     short loc_140007F40
0x140007f6c  lea     rcx, SpinLock; SpinLock
0x140007f73  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007f7a  nop     dword ptr [rax+rax+00h]
0x140007f7f  mov     sil, al
0x140007f82  jmp     loc_140007EFE
0x140007f87  dec     cs:dword_140039760
0x140007f8d  jmp     short loc_140007F1A
0x140007f8f  mov     r11d, [rcx+14h]
0x140007f93  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x140007f9a  mov     rax, [rsp+68h+arg_20]
0x140007fa2  mov     edx, 51h ; 'Q'
0x140007fa7  mov     [rsp+68h+var_30], rax
0x140007fac  mov     [rsp+68h+var_38], r9d
0x140007fb1  mov     r9, rbx
0x140007fb4  lea     r10d, [r11-1]
0x140007fb8  mov     [rsp+68h+var_40], r10d
0x140007fbd  mov     [rsp+68h+var_48], r11d
0x140007fc2  call    WPP_SF_qddds
0x140007fc7  jmp     loc_140007EF9
0x140007fcc  inc     cs:dword_140039760
0x140007fd2  jmp     loc_140007F1A
0x140007fd7  mov     dl, sil; NewIrql
0x140007fda  lea     rcx, SpinLock; SpinLock
0x140007fe1  call    cs:__imp_KeReleaseSpinLock
0x140007fe8  nop     dword ptr [rax+rax+00h]
0x140007fed  jmp     loc_140007F38
```
