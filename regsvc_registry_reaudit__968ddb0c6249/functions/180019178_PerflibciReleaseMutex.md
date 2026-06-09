# PerflibciReleaseMutex

- ea: `0x180019178`
- end: `0x1800191a2`
- name: `PerflibciReleaseMutex`
- size: `42`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180018960`
- `0x180018c80`
- `0x180018dd0`
- `0x180019060`

## callees

- `0x180019178`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019186`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019197`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019197`

## pseudocode

```c
DWORD __fastcall PerflibciReleaseMutex(void *a1)
{
  DWORD result; // eax

  result = 87;
  if ( a1 )
  {
    if ( ReleaseMutex(a1) )
      return 0;
    else
      return GetLastError();
  }
  return result;
}

```

## disassembly

```asm
0x180019178  sub     rsp, 28h
0x18001917c  mov     eax, 57h ; 'W'
0x180019181  test    rcx, rcx
0x180019184  jz      short loc_18001919D
0x180019186  call    cs:__imp_ReleaseMutex
0x18001918c  test    eax, eax
0x18001918e  jz      short loc_180019197
0x180019190  xor     eax, eax
0x180019192  add     rsp, 28h
0x180019196  retn
0x180019197  call    cs:__imp_GetLastError
0x18001919d  add     rsp, 28h
0x1800191a1  retn
```
