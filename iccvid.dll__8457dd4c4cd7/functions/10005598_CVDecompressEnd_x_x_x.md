# CVDecompressEnd(x,x,x)

- ea: `0x10005598`
- end: `0x100055cb`
- name: `_CVDecompressEnd@12`
- size: `51`
- prototype: `int __thiscall(HLOCAL hMem, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100101f2`

## callees

- `0x10005598`
- `0x1000a50e`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x100055b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x100055bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x100055b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x100055bd`

## pseudocode

```c
int __fastcall CVDecompressEnd(HLOCAL *hMem, int a2, int a3)
{
  int v4; // edi

  if ( a2 )
    v4 = EndingCodeBooksFromContext(hMem, a3);
  else
    v4 = 0;
  LocalFree(hMem[7]);
  LocalFree(hMem);
  return v4;
}

```

## disassembly

```asm
0x10005598  mov     edi, edi
0x1000559a  push    ebp
0x1000559b  mov     ebp, esp
0x1000559d  push    esi
0x1000559e  mov     esi, ecx
0x100055a0  push    edi
0x100055a1  test    edx, edx
0x100055a3  jz      short loc_100055B1
0x100055a5  mov     edx, [ebp+arg_0]
0x100055a8  call    _EndingCodeBooksFromContext@8; EndingCodeBooksFromContext(x,x)
0x100055ad  mov     edi, eax
0x100055af  jmp     short loc_100055B3
0x100055b1  xor     edi, edi
0x100055b3  push    dword ptr [esi+1Ch]; hMem
0x100055b6  call    ds:__imp__LocalFree@4; LocalFree(x)
0x100055bc  push    esi; hMem
0x100055bd  call    ds:__imp__LocalFree@4; LocalFree(x)
0x100055c3  mov     eax, edi
0x100055c5  pop     edi
0x100055c6  pop     esi
0x100055c7  pop     ebp
0x100055c8  retn    4
```
