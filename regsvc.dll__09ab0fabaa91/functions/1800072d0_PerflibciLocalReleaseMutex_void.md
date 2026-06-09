# PerflibciLocalReleaseMutex(void *)

- ea: `0x1800072d0`
- end: `0x1800072f9`
- name: `?PerflibciLocalReleaseMutex@@YAKPEAX@Z`
- size: `41`
- prototype: `DWORD __fastcall(void *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b40`
- `0x180005680`
- `0x180006bc0`
- `0x18000cb04`
- `0x18000d534`
- `0x18000dc48`
- `0x18000e054`
- `0x180015250`
- `0x180016544`

## callees

- `0x1800072d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800072d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800072d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072e7`

## pseudocode

```c
DWORD __fastcall PerflibciLocalReleaseMutex(void *a1)
{
  if ( !a1 )
    return 87;
  if ( ReleaseMutex(a1) )
    return 0;
  return GetLastError();
}

```

## disassembly

```asm
0x1800072d0  sub     rsp, 28h
0x1800072d4  test    rcx, rcx
0x1800072d7  jz      short loc_1800072EF
0x1800072d9  call    cs:__imp_ReleaseMutex
0x1800072df  test    eax, eax
0x1800072e1  jz      short loc_1800072E7
0x1800072e3  xor     eax, eax
0x1800072e5  jmp     short loc_1800072F4
0x1800072e7  call    cs:__imp_GetLastError
0x1800072ed  jmp     short loc_1800072F4
0x1800072ef  mov     eax, 57h ; 'W'
0x1800072f4  add     rsp, 28h
0x1800072f8  retn
```
