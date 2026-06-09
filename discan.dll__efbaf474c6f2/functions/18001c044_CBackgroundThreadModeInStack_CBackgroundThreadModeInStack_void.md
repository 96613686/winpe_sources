# CBackgroundThreadModeInStack::~CBackgroundThreadModeInStack(void)

- ea: `0x18001c044`
- end: `0x18001c066`
- name: `??1CBackgroundThreadModeInStack@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(CBackgroundThreadModeInStack *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ec84`
- `0x180038635`

## callees

- `0x18001c044`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x18001c05b`
- `KERNEL32!SetThreadPriority` at `0x18001c05b`
- `KERNEL32!GetCurrentThread` at `0x18001c04d`
- `KERNEL32!GetCurrentThread` at `0x18001c04d`

## pseudocode

```c
void __fastcall CBackgroundThreadModeInStack::~CBackgroundThreadModeInStack(CBackgroundThreadModeInStack *this)
{
  HANDLE CurrentThread; // rax

  if ( *(int *)this >= 0 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 0x20000);
  }
}

```

## disassembly

```asm
0x18001c044  sub     rsp, 28h
0x18001c048  cmp     dword ptr [rcx], 0
0x18001c04b  jl      short loc_18001C061
0x18001c04d  call    cs:__imp_GetCurrentThread
0x18001c053  mov     rcx, rax; hThread
0x18001c056  mov     edx, 20000h; nPriority
0x18001c05b  call    cs:__imp_SetThreadPriority
0x18001c061  add     rsp, 28h
0x18001c065  retn
```
