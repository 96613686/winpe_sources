# memory_pool<4096,task_allocator>::deallocate(void *)

- ea: `0x180014580`
- end: `0x1800145e5`
- name: `?deallocate@?$memory_pool@$0BAAA@Vtask_allocator@@@@QEAAXPEAX@Z`
- size: `101`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180012898`
- `0x180015938`
- `0x18002ec8a`

## callees

- `0x180014580`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800145bb`
- `KERNEL32!EnterCriticalSection` at `0x1800145bb`
- `KERNEL32!LeaveCriticalSection` at `0x1800145cf`
- `KERNEL32!LeaveCriticalSection` at `0x1800145cf`
- `KERNEL32!TryEnterCriticalSection` at `0x18001459f`
- `KERNEL32!TryEnterCriticalSection` at `0x18001459f`
- `KERNEL32!SwitchToThread` at `0x1800145b0`
- `KERNEL32!SwitchToThread` at `0x1800145b0`

## pseudocode

```c
void __fastcall memory_pool<4096,task_allocator>::deallocate(
        LPCRITICAL_SECTION lpCriticalSection,
        struct _RTL_CRITICAL_SECTION_DEBUG *a2)
{
  int v4; // edi

  if ( a2 )
  {
    v4 = 0;
    while ( !TryEnterCriticalSection(lpCriticalSection) )
    {
      if ( ++v4 >= 100 )
      {
        EnterCriticalSection(lpCriticalSection);
        break;
      }
      SwitchToThread();
    }
    *(_QWORD *)&a2->Type = lpCriticalSection[1].DebugInfo;
    lpCriticalSection[1].DebugInfo = a2;
    LeaveCriticalSection(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x180014580  test    rdx, rdx
0x180014583  jz      short locret_1800145E4
0x180014585  mov     [rsp+arg_0], rbx
0x18001458a  mov     [rsp+arg_8], rsi
0x18001458f  push    rdi
0x180014590  sub     rsp, 20h
0x180014594  mov     rsi, rdx
0x180014597  mov     rbx, rcx
0x18001459a  xor     edi, edi
0x18001459c  mov     rcx, rbx; lpCriticalSection
0x18001459f  call    cs:__imp_TryEnterCriticalSection
0x1800145a5  test    eax, eax
0x1800145a7  jnz     short loc_1800145C1
0x1800145a9  inc     edi
0x1800145ab  cmp     edi, 64h ; 'd'
0x1800145ae  jge     short loc_1800145B8
0x1800145b0  call    cs:__imp_SwitchToThread
0x1800145b6  jmp     short loc_18001459C
0x1800145b8  mov     rcx, rbx; lpCriticalSection
0x1800145bb  call    cs:__imp_EnterCriticalSection
0x1800145c1  mov     rax, [rbx+28h]
0x1800145c5  mov     rcx, rbx; lpCriticalSection
0x1800145c8  mov     [rsi], rax
0x1800145cb  mov     [rbx+28h], rsi
0x1800145cf  call    cs:__imp_LeaveCriticalSection
0x1800145d5  mov     rbx, [rsp+28h+arg_0]
0x1800145da  mov     rsi, [rsp+28h+arg_8]
0x1800145df  add     rsp, 20h
0x1800145e3  pop     rdi
0x1800145e4  retn
```
