# IsConsole(void *)

- ea: `0x14000a0f0`
- end: `0x14000a111`
- name: `?IsConsole@@YA_NPEAX@Z`
- size: `33`
- prototype: `bool __fastcall(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140002a70`
- `0x140007f50`
- `0x1400083e0`

## import_xrefs

- `KERNEL32!GetConsoleMode` at `0x14000a101`
- `KERNEL32!GetConsoleMode` at `0x14000a101`

## pseudocode

```c
bool __fastcall IsConsole(void *a1)
{
  DWORD Mode; // [rsp+38h] [rbp+10h] BYREF

  Mode = 0;
  return GetConsoleMode(a1, &Mode);
}

```

## disassembly

```asm
0x14000a0f0  sub     rsp, 28h
0x14000a0f4  lea     rdx, [rsp+28h+Mode]; lpMode
0x14000a0f9  mov     [rsp+28h+Mode], 0
0x14000a101  call    cs:__imp_GetConsoleMode
0x14000a107  test    eax, eax
0x14000a109  setnz   al
0x14000a10c  add     rsp, 28h
0x14000a110  retn
```
