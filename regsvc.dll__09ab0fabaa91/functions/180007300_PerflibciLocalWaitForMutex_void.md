# PerflibciLocalWaitForMutex(void *)

- ea: `0x180007300`
- end: `0x180007317`
- name: `?PerflibciLocalWaitForMutex@@YAKPEAX@Z`
- size: `23`
- prototype: `DWORD __fastcall(void *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180002dd0`
- `0x180003b40`
- `0x180005680`
- `0x18000cb04`
- `0x18000d534`
- `0x18000dc48`
- `0x18000e054`
- `0x180015250`
- `0x180016574`

## callees

- `0x180007300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000730a`

## pseudocode

```c
DWORD __fastcall PerflibciLocalWaitForMutex(void *a1)
{
  if ( a1 )
    return WaitForSingleObject(a1, 0xEA60u);
  else
    return 87;
}

```

## disassembly

```asm
0x180007300  test    rcx, rcx
0x180007303  jz      short loc_180007311
0x180007305  mov     edx, 0EA60h
0x18000730a  jmp     cs:__imp_WaitForSingleObject
0x180007311  mov     eax, 57h ; 'W'
0x180007316  retn
```
