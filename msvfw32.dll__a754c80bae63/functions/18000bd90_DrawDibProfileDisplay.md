# DrawDibProfileDisplay

- ea: `0x18000bd90`
- end: `0x18000bdb8`
- name: `DrawDibProfileDisplay`
- size: `40`
- prototype: `LONG_PTR __stdcall(LPBITMAPINFOHEADER lpbi)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180002a90`
- `0x180008400`
- `0x18000ab84`

## callees

- `0x18000bd90`
- `0x18000be48`
- `0x18000c13c`

## pseudocode

```c
LONG_PTR __stdcall DrawDibProfileDisplay(LPBITMAPINFOHEADER lpbi)
{
  if ( lpbi )
    return (unsigned int)ProfDispCanDrawDib((LPCSTR)lpbi);
  InitProfDisp(1u);
  return (LONG_PTR)qword_180023DB0;
}

```

## disassembly

```asm
0x18000bd90  sub     rsp, 28h
0x18000bd94  test    rcx, rcx
0x18000bd97  jnz     short loc_18000BDAC
0x18000bd99  mov     ecx, 1
0x18000bd9e  call    InitProfDisp
0x18000bda3  lea     rax, qword_180023DB0
0x18000bdaa  jmp     short loc_18000BDB3
0x18000bdac  call    ProfDispCanDrawDib
0x18000bdb1  mov     eax, eax
0x18000bdb3  add     rsp, 28h
0x18000bdb7  retn
```
