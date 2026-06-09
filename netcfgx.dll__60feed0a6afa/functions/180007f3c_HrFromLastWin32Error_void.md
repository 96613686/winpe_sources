# HrFromLastWin32Error(void)

- ea: `0x180007f3c`
- end: `0x180007f70`
- name: `?HrFromLastWin32Error@@YAJXZ`
- size: `52`
- prototype: `__int64(void)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180006ac4`
- `0x180006d30`
- `0x180006ecc`
- `0x1800070a8`
- `0x180007838`
- `0x180008260`
- `0x1800082c4`
- `0x18000831c`
- `0x1800083e8`
- `0x18000844c`
- `0x180008cc0`
- `0x180008e2c`
- `0x180011270`

## callees

- `0x180007f3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f40`

## pseudocode

```c
signed int HrFromLastWin32Error(void)
{
  signed int result; // eax

  result = GetLastError();
  if ( (result & 0xE0000000) == 0xE0000000 )
    return (unsigned __int16)result | 0x800F0000;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180007f3c  sub     rsp, 28h
0x180007f40  call    cs:__imp_GetLastError
0x180007f46  mov     ecx, eax
0x180007f48  mov     edx, 0E0000000h
0x180007f4d  and     ecx, edx
0x180007f4f  jz      short loc_180007F5F
0x180007f51  cmp     ecx, edx
0x180007f53  jnz     short loc_180007F5F
0x180007f55  movzx   eax, ax
0x180007f58  or      eax, 800F0000h
0x180007f5d  jmp     short loc_180007F6B
0x180007f5f  test    eax, eax
0x180007f61  jle     short loc_180007F6B
0x180007f63  movzx   eax, ax
0x180007f66  or      eax, 80070000h
0x180007f6b  add     rsp, 28h
0x180007f6f  retn
```
