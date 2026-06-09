# CExeModule::Unlock(void)

- ea: `0x1400029d8`
- end: `0x140002a0a`
- name: `?Unlock@CExeModule@@QEAAJXZ`
- size: `50`
- prototype: `__int64 __fastcall(CExeModule *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140001aa4`
- `0x140001b98`
- `0x140002650`
- `0x140002820`
- `0x1400028d0`

## callees

- `0x1400029d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400029fc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400029fc`

## pseudocode

```c
__int64 __fastcall CExeModule::Unlock(CExeModule *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(&dword_14000A798);
  if ( !v1 )
  {
    byte_14000A878 = 1;
    SetEvent(hEvent);
  }
  return v1;
}

```

## disassembly

```asm
0x1400029d8  push    rbx
0x1400029da  sub     rsp, 20h
0x1400029de  or      ebx, 0FFFFFFFFh
0x1400029e1  lock xadd cs:dword_14000A798, ebx
0x1400029e9  sub     ebx, 1
0x1400029ec  jnz     short loc_140002A02
0x1400029ee  mov     rcx, cs:hEvent; hEvent
0x1400029f5  mov     cs:byte_14000A878, 1
0x1400029fc  call    cs:__imp_SetEvent
0x140002a02  mov     eax, ebx
0x140002a04  add     rsp, 20h
0x140002a08  pop     rbx
0x140002a09  retn
```
