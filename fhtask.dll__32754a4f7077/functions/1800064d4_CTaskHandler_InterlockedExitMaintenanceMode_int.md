# CTaskHandler::InterlockedExitMaintenanceMode(int)

- ea: `0x1800064d4`
- end: `0x180006516`
- name: `?InterlockedExitMaintenanceMode@CTaskHandler@@AEAAXH@Z`
- size: `66`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x1800061ec`
- `0x180006580`
- `0x1800066c0`

## callees

- `0x180006070`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800064ec`
- `KERNEL32!EnterCriticalSection` at `0x1800064ec`
- `KERNEL32!LeaveCriticalSection` at `0x18000650f`

## pseudocode

```c
void __fastcall CTaskHandler::InterlockedExitMaintenanceMode(struct _RTL_CRITICAL_SECTION *this, int a2)
{
  EnterCriticalSection(this + 2);
  CTaskHandler::ExitMaintenanceMode((CTaskHandler *)this, a2);
  LeaveCriticalSection(this + 2);
}

```

## disassembly

```asm
0x1800064d4  mov     [rsp+arg_0], rbx
0x1800064d9  mov     [rsp+arg_8], rsi
0x1800064de  push    rdi
0x1800064df  sub     rsp, 20h
0x1800064e3  mov     rdi, rcx
0x1800064e6  mov     ebx, edx
0x1800064e8  add     rcx, 50h ; 'P'; lpCriticalSection
0x1800064ec  call    cs:__imp_EnterCriticalSection
0x1800064f2  mov     edx, ebx; int
0x1800064f4  mov     rcx, rdi; this
0x1800064f7  call    ?ExitMaintenanceMode@CTaskHandler@@AEAAXH@Z; CTaskHandler::ExitMaintenanceMode(int)
0x1800064fc  lea     rcx, [rdi+50h]
0x180006500  mov     rbx, [rsp+28h+arg_0]
0x180006505  mov     rsi, [rsp+28h+arg_8]
0x18000650a  add     rsp, 20h
0x18000650e  pop     rdi
0x18000650f  jmp     cs:__imp_LeaveCriticalSection
```
