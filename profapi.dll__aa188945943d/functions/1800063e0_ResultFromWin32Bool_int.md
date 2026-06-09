# ResultFromWin32Bool(int)

- ea: `0x1800063e0`
- end: `0x1800063f6`
- name: `?ResultFromWin32Bool@@YAJH@Z`
- size: `22`
- prototype: `signed int __fastcall(int)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180006250`
- `0x1800064b0`
- `0x180006690`
- `0x180006ad0`
- `0x180006de0`
- `0x18000b9c4`
- `0x18000cba8`
- `0x18000d620`
- `0x18000e874`
- `0x1800121fc`
- `0x180016834`
- `0x180016960`

## callees

- `0x1800063e0`
- `0x180006a9c`

## pseudocode

```c
signed int __fastcall ResultFromWin32Bool(int a1)
{
  if ( a1 )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x1800063e0  sub     rsp, 28h
0x1800063e4  test    ecx, ecx
0x1800063e6  jz      short loc_1800063EF
0x1800063e8  xor     eax, eax
0x1800063ea  add     rsp, 28h
0x1800063ee  retn
0x1800063ef  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800063f4  jmp     short loc_1800063EA
```
