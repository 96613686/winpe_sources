# __scrt_get_show_window_mode

- ea: `0x14000177c`
- end: `0x1400017b6`
- name: `__scrt_get_show_window_mode`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400011d0`

## callees

- `0x140001d16`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001798`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140001798`

## pseudocode

```c
WORD _scrt_get_show_window_mode()
{
  WORD result; // ax
  _STARTUPINFOW StartupInfo; // [rsp+20h] [rbp-78h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  GetStartupInfoW(&StartupInfo);
  result = 10;
  if ( (StartupInfo.dwFlags & 1) != 0 )
    return StartupInfo.wShowWindow;
  return result;
}

```

## disassembly

```asm
0x14000177c  sub     rsp, 98h
0x140001783  xor     edx, edx; Val
0x140001785  lea     rcx, [rsp+98h+StartupInfo]; void *
0x14000178a  lea     r8d, [rdx+68h]; Size
0x14000178e  call    memset_0
0x140001793  lea     rcx, [rsp+98h+StartupInfo]; lpStartupInfo
0x140001798  call    cs:__imp_GetStartupInfoW
0x14000179e  test    byte ptr [rsp+98h+StartupInfo.dwFlags], 1
0x1400017a3  mov     eax, 0Ah
0x1400017a8  cmovnz  ax, [rsp+98h+StartupInfo.wShowWindow]
0x1400017ae  add     rsp, 98h
0x1400017b5  retn
```
