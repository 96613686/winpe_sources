# Guard<Guardable>::Guard<Guardable>(Guardable const &)

- ea: `0x180017d20`
- end: `0x180017d72`
- name: `??0?$Guard@VGuardable@@@@QEAA@AEBVGuardable@@@Z`
- size: `82`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180017fec`
- `0x180018330`
- `0x180018460`
- `0x1800227d8`
- `0x180022840`

## callees

- `0x180017d20`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180017d59`
- `KERNEL32!EnterCriticalSection` at `0x180017d59`
- `KERNEL32!TryEnterCriticalSection` at `0x180017d3d`
- `KERNEL32!TryEnterCriticalSection` at `0x180017d3d`
- `KERNEL32!SwitchToThread` at `0x180017d4e`
- `KERNEL32!SwitchToThread` at `0x180017d4e`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION **__fastcall Guard<Guardable>::Guard<Guardable>(
        struct _RTL_CRITICAL_SECTION **a1,
        struct _RTL_CRITICAL_SECTION *a2)
{
  int v4; // ebx

  *a1 = a2;
  v4 = 0;
  while ( !TryEnterCriticalSection(a2) )
  {
    if ( ++v4 >= 100 )
    {
      EnterCriticalSection(a2);
      return a1;
    }
    SwitchToThread();
  }
  return a1;
}

```

## disassembly

```asm
0x180017d20  mov     [rsp+arg_0], rbx
0x180017d25  mov     [rsp+arg_8], rsi
0x180017d2a  push    rdi
0x180017d2b  sub     rsp, 20h
0x180017d2f  mov     rdi, rdx
0x180017d32  mov     [rcx], rdx
0x180017d35  mov     rsi, rcx
0x180017d38  xor     ebx, ebx
0x180017d3a  mov     rcx, rdi; lpCriticalSection
0x180017d3d  call    cs:__imp_TryEnterCriticalSection
0x180017d43  test    eax, eax
0x180017d45  jnz     short loc_180017D5F
0x180017d47  inc     ebx
0x180017d49  cmp     ebx, 64h ; 'd'
0x180017d4c  jge     short loc_180017D56
0x180017d4e  call    cs:__imp_SwitchToThread
0x180017d54  jmp     short loc_180017D3A
0x180017d56  mov     rcx, rdi; lpCriticalSection
0x180017d59  call    cs:__imp_EnterCriticalSection
0x180017d5f  mov     rbx, [rsp+28h+arg_0]
0x180017d64  mov     rax, rsi
0x180017d67  mov     rsi, [rsp+28h+arg_8]
0x180017d6c  add     rsp, 20h
0x180017d70  pop     rdi
0x180017d71  retn
```
