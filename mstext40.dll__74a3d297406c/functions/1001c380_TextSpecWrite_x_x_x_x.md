# TextSpecWrite(x,x,x,x)

- ea: `0x1001c380`
- end: `0x1001c394`
- name: `_TextSpecWrite@16`
- size: `20`
- prototype: `int __stdcall(LPCWSTR lpFileName, LPCWCH lpWideCharStr, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100133f0`

## callees

- `0x1001ad40`

## pseudocode

```c
int __stdcall TextSpecWrite(LPCWSTR lpFileName, WCHAR *lpWideCharStr, int a3, int a4)
{
  return INIFileSpecWrite(lpFileName, lpWideCharStr, a3);
}

```

## disassembly

```asm
0x1001c380  push    [esp+arg_8]; int
0x1001c384  push    [esp+4+lpWideCharStr]; lpWideCharStr
0x1001c388  push    [esp+8+lpFileName]; lpFileName
0x1001c38c  call    INIFileSpecWrite
0x1001c391  retn    10h
```
