# WriteCharKey

- ea: `0x1001c3a0`
- end: `0x1001c3c5`
- name: `WriteCharKey`
- size: `37`
- prototype: `int __stdcall(HANDLE hFile, LPCWCH lpWideCharStr, WCHAR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1001ad40`

## callees

- `0x1001c420`

## pseudocode

```c
int __stdcall WriteCharKey(HANDLE hFile, LPCWCH lpWideCharStr, int a3)
{
  HIWORD(a3) = 0;
  return WriteStringKey(hFile, lpWideCharStr, (LPCWCH)&a3);
}

```

## disassembly

```asm
0x1001c3a0  mov     eax, [esp+arg_8]
0x1001c3a4  mov     word ptr [esp+arg_8], ax
0x1001c3a9  xor     eax, eax
0x1001c3ab  mov     word ptr [esp+arg_8+2], ax
0x1001c3b0  lea     eax, [esp+arg_8]
0x1001c3b4  push    eax; LPCWCH
0x1001c3b5  push    [esp+4+lpWideCharStr]; lpWideCharStr
0x1001c3b9  push    [esp+8+hFile]; hFile
0x1001c3bd  call    WriteStringKey
0x1001c3c2  retn    0Ch
```
