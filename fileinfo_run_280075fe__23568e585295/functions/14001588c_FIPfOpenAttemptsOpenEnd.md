# FIPfOpenAttemptsOpenEnd

- ea: `0x14001588c`
- end: `0x140015947`
- name: `FIPfOpenAttemptsOpenEnd`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017700`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x14001588c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001592f`
- `ntoskrnl!KeSetEvent` at `0x14001592f`

## pseudocode

```c
__int64 __fastcall FIPfOpenAttemptsOpenEnd(__int64 a1, __int64 a2)
{
  __int64 *v5; // rsi
  struct _KEVENT *i; // rbx
  __int64 v8; // [rsp+30h] [rbp+8h]

  FILockExclusiveAcquire(a2);
  if ( (*(_DWORD *)(a1 + 40))-- == 1 )
  {
    v5 = (__int64 *)(a1 + 16);
    HIDWORD(v8) = _InterlockedIncrement(&dword_140009640);
    LODWORD(v8) = ((MEMORY[0xFFFFF78000000004] * MEMORY[0xFFFFF78000000324]) << 8)
                + ((MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
    *(_QWORD *)a1 = v8;
    for ( i = *(struct _KEVENT **)(a1 + 16); i != (struct _KEVENT *)v5; i = *(struct _KEVENT **)&i->Header.Lock )
    {
      KeSetEvent(i + 2, 2, 0);
      _InterlockedIncrement(&dword_1400097F4);
    }
  }
  return FILockExclusiveRelease(a2);
}

```

## disassembly

```asm
0x14001588c  mov     [rsp+arg_8], rbx
0x140015891  mov     [rsp+arg_10], rsi
0x140015896  push    rdi
0x140015897  sub     rsp, 20h
0x14001589b  mov     rbx, rcx
0x14001589e  mov     rdi, rdx
0x1400158a1  mov     rcx, rdx
0x1400158a4  call    FILockExclusiveAcquire
0x1400158a9  add     dword ptr [rbx+28h], 0FFFFFFFFh
0x1400158ad  jnz     short loc_14001590B
0x1400158af  mov     eax, 1
0x1400158b4  lock xadd cs:dword_140009640, eax
0x1400158bc  inc     eax
0x1400158be  lea     rsi, [rbx+10h]
0x1400158c2  mov     dword ptr [rsp+28h+arg_0+4], eax
0x1400158c6  mov     rcx, 0FFFFF78000000320h
0x1400158d0  mov     rcx, [rcx]
0x1400158d3  mov     eax, ds:0FFFFF78000000004h
0x1400158dc  mov     edx, ecx
0x1400158de  mov     r8d, eax
0x1400158e1  shr     rcx, 20h
0x1400158e5  imul    ecx, eax
0x1400158e8  imul    r8, rdx
0x1400158ec  shl     ecx, 8
0x1400158ef  shr     r8, 18h
0x1400158f3  add     r8d, ecx
0x1400158f6  mov     dword ptr [rsp+28h+arg_0], r8d
0x1400158fb  mov     rax, [rsp+28h+arg_0]
0x140015900  mov     [rbx], rax
0x140015903  mov     rbx, [rsi]
0x140015906  cmp     rbx, rsi
0x140015909  jnz     short loc_140015924
0x14001590b  mov     rcx, rdi
0x14001590e  call    FILockExclusiveRelease
0x140015913  mov     rbx, [rsp+28h+arg_8]
0x140015918  mov     rsi, [rsp+28h+arg_10]
0x14001591d  add     rsp, 20h
0x140015921  pop     rdi
0x140015922  retn
0x140015924  xor     r8d, r8d; Wait
0x140015927  lea     rcx, [rbx+30h]; Event
0x14001592b  lea     edx, [r8+2]; Increment
0x14001592f  call    cs:__imp_KeSetEvent
0x140015936  nop     dword ptr [rax+rax+00h]
0x14001593b  lock inc cs:dword_1400097F4
0x140015942  mov     rbx, [rbx]
0x140015945  jmp     short loc_140015906
```
