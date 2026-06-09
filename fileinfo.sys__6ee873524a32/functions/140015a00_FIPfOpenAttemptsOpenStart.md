# FIPfOpenAttemptsOpenStart

- ea: `0x140015a00`
- end: `0x140015a40`
- name: `FIPfOpenAttemptsOpenStart`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017700`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x140015a00`

## pseudocode

```c
__int64 __fastcall FIPfOpenAttemptsOpenStart(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx

  FILockExclusiveAcquire(a2);
  if ( *(_DWORD *)(a1 + 36) )
  {
    v4 = -1073740024;
  }
  else
  {
    ++*(_DWORD *)(a1 + 40);
    v4 = 0;
  }
  FILockExclusiveRelease(a2);
  return v4;
}

```

## disassembly

```asm
0x140015a00  mov     [rsp+arg_0], rbx
0x140015a05  push    rdi
0x140015a06  sub     rsp, 20h
0x140015a0a  mov     rbx, rcx
0x140015a0d  mov     rdi, rdx
0x140015a10  mov     rcx, rdx
0x140015a13  call    FILockExclusiveAcquire
0x140015a18  cmp     dword ptr [rbx+24h], 0
0x140015a1c  jnz     short loc_140015A39
0x140015a1e  inc     dword ptr [rbx+28h]
0x140015a21  xor     ebx, ebx
0x140015a23  mov     rcx, rdi
0x140015a26  call    FILockExclusiveRelease
0x140015a2b  mov     eax, ebx
0x140015a2d  mov     rbx, [rsp+28h+arg_0]
0x140015a32  add     rsp, 20h
0x140015a36  pop     rdi
0x140015a37  retn
0x140015a39  mov     ebx, 0C0000708h
0x140015a3e  jmp     short loc_140015A23
```
