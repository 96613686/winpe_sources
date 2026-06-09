# SQLCreateDataSourceExW

- ea: `0x180002ce0`
- end: `0x180002d1a`
- name: `SQLCreateDataSourceExW`
- size: `58`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000c440`

## callees

- `0x180001740`
- `0x18000295c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002d0c`
- `KERNEL32!LeaveCriticalSection` at `0x180002d0c`
- `KERNEL32!EnterCriticalSection` at `0x180002cf0`
- `KERNEL32!EnterCriticalSection` at `0x180002cf0`

## pseudocode

```c
__int64 __fastcall SQLCreateDataSourceExW(__int64 a1)
{
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  LODWORD(a1) = SQLCreateDataSourceCover(a1);
  LeaveCriticalSection(&g_csInstaller);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180002ce0  push    rbx
0x180002ce2  sub     rsp, 20h
0x180002ce6  mov     rbx, rcx
0x180002ce9  lea     rcx, g_csInstaller; lpCriticalSection
0x180002cf0  call    cs:__imp_EnterCriticalSection
0x180002cf6  call    FreeErrorQueue
0x180002cfb  mov     rcx, rbx
0x180002cfe  call    SQLCreateDataSourceCover
0x180002d03  lea     rcx, g_csInstaller; lpCriticalSection
0x180002d0a  mov     ebx, eax
0x180002d0c  call    cs:__imp_LeaveCriticalSection
0x180002d12  mov     eax, ebx
0x180002d14  add     rsp, 20h
0x180002d18  pop     rbx
0x180002d19  retn
```
