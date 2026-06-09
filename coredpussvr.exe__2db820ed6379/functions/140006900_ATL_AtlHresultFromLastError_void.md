# ATL::AtlHresultFromLastError(void)

- ea: `0x140006900`
- end: `0x140006922`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `34`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140007880`
- `0x140008460`
- `0x14000878c`

## callees

- `0x140006900`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006904`

## pseudocode

```c
signed int ATL::AtlHresultFromLastError(void)
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
0x140006900  sub     rsp, 28h
0x140006904  call    cs:__imp_GetLastError
0x14000690b  nop     dword ptr [rax+rax+00h]
0x140006910  test    eax, eax
0x140006912  jle     short loc_14000691C
0x140006914  movzx   eax, ax
0x140006917  or      eax, 80070000h
0x14000691c  add     rsp, 28h
0x140006920  retn
```
