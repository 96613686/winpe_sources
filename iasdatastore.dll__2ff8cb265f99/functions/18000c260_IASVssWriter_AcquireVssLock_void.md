# IASVssWriter::AcquireVssLock(void)

- ea: `0x18000c260`
- end: `0x18000c2a2`
- name: `?AcquireVssLock@IASVssWriter@@UEAAXXZ`
- size: `66`
- prototype: `void __fastcall(IASVssWriter *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c260`

## import_xrefs

- `KERNEL32!TryEnterCriticalSection` at `0x18000c282`
- `KERNEL32!TryEnterCriticalSection` at `0x18000c282`
- `KERNEL32!SwitchToThread` at `0x18000c279`
- `KERNEL32!SwitchToThread` at `0x18000c279`
- `KERNEL32!EnterCriticalSection` at `0x18000c291`
- `KERNEL32!EnterCriticalSection` at `0x18000c291`

## pseudocode

```c
void __fastcall IASVssWriter::AcquireVssLock(IASVssWriter *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  int v2; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v2 = 0;
  while ( !TryEnterCriticalSection(v1) )
  {
    if ( ++v2 >= 100 )
    {
      EnterCriticalSection(v1);
      return;
    }
    SwitchToThread();
  }
}

```

## disassembly

```asm
0x18000c260  mov     [rsp+arg_0], rbx
0x18000c265  push    rdi
0x18000c266  sub     rsp, 20h
0x18000c26a  lea     rdi, [rcx+8]
0x18000c26e  xor     ebx, ebx
0x18000c270  jmp     short loc_18000C27F
0x18000c272  inc     ebx
0x18000c274  cmp     ebx, 64h ; 'd'
0x18000c277  jge     short loc_18000C28E
0x18000c279  call    cs:__imp_SwitchToThread
0x18000c27f  mov     rcx, rdi; lpCriticalSection
0x18000c282  call    cs:__imp_TryEnterCriticalSection
0x18000c288  test    eax, eax
0x18000c28a  jz      short loc_18000C272
0x18000c28c  jmp     short loc_18000C297
0x18000c28e  mov     rcx, rdi; lpCriticalSection
0x18000c291  call    cs:__imp_EnterCriticalSection
0x18000c297  mov     rbx, [rsp+28h+arg_0]
0x18000c29c  add     rsp, 20h
0x18000c2a0  pop     rdi
0x18000c2a1  retn
```
