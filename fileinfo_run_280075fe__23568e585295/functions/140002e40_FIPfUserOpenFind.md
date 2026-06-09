# FIPfUserOpenFind

- ea: `0x140002e40`
- end: `0x140002eba`
- name: `FIPfUserOpenFind`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140016b80`

## callees

- `0x140002e40`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002e9f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140002e9f`
- `ntoskrnl!ExfReleasePushLock` at `0x140002e93`
- `ntoskrnl!ExfReleasePushLock` at `0x140002e93`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002e4d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140002e4d`
- `ntoskrnl!ExfAcquirePushLockExclusive` at `0x140002e60`
- `ntoskrnl!ExfAcquirePushLockExclusive` at `0x140002e60`

## pseudocode

```c
__int64 *__fastcall FIPfUserOpenFind(__int64 a1)
{
  __int64 *i; // rbx

  KeEnterCriticalRegion();
  ExfAcquirePushLockExclusive(&qword_140009760);
  for ( i = (__int64 *)qword_140009768; i != &qword_140009768; i = (__int64 *)*i )
  {
    if ( i[9] == a1 )
      goto LABEL_6;
  }
  i = 0;
LABEL_6:
  ExfReleasePushLock(&qword_140009760);
  KeLeaveCriticalRegion();
  return i;
}

```

## disassembly

```asm
0x140002e40  mov     [rsp+arg_0], rbx
0x140002e45  push    rdi
0x140002e46  sub     rsp, 20h
0x140002e4a  mov     rdi, rcx
0x140002e4d  call    cs:__imp_KeEnterCriticalRegion
0x140002e54  nop     dword ptr [rax+rax+00h]
0x140002e59  lea     rcx, qword_140009760
0x140002e60  call    cs:__imp_ExfAcquirePushLockExclusive
0x140002e67  nop     dword ptr [rax+rax+00h]
0x140002e6c  mov     rbx, cs:qword_140009768
0x140002e73  lea     rax, qword_140009768
0x140002e7a  cmp     rbx, rax
0x140002e7d  jz      short loc_140002E8A
0x140002e7f  cmp     [rbx+48h], rdi
0x140002e83  jz      short loc_140002E8C
0x140002e85  mov     rbx, [rbx]
0x140002e88  jmp     short loc_140002E73
0x140002e8a  xor     ebx, ebx
0x140002e8c  lea     rcx, qword_140009760
0x140002e93  call    cs:__imp_ExfReleasePushLock
0x140002e9a  nop     dword ptr [rax+rax+00h]
0x140002e9f  call    cs:__imp_KeLeaveCriticalRegion
0x140002ea6  nop     dword ptr [rax+rax+00h]
0x140002eab  mov     rax, rbx
0x140002eae  mov     rbx, [rsp+28h+arg_0]
0x140002eb3  add     rsp, 20h
0x140002eb7  pop     rdi
0x140002eb8  retn
```
