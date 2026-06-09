# ResourceCache::LastError(void)

- ea: `0x18000b95c`
- end: `0x18000b977`
- name: `?LastError@ResourceCache@@CAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005890`
- `0x18000b838`

## callees

- `0x18000b95c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b960`

## pseudocode

```c
signed int ResourceCache::LastError(void)
{
  signed int result; // eax

  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000b95c  sub     rsp, 28h
0x18000b960  call    cs:__imp_GetLastError
0x18000b966  test    eax, eax
0x18000b968  jle     short loc_18000B972
0x18000b96a  movzx   eax, ax
0x18000b96d  or      eax, 80070000h
0x18000b972  add     rsp, 28h
0x18000b976  retn
```
