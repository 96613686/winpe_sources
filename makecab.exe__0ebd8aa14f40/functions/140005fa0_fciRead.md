# fciRead

- ea: `0x140005fa0`
- end: `0x140005fdd`
- name: `fciRead`
- size: `61`
- prototype: `UINT __cdecl(INT_PTR hf, void *memory, UINT cb, int *err, void *pv)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140005fa0`

## import_xrefs

- `msvcrt!_errno` at `0x140005fc1`
- `msvcrt!_errno` at `0x140005fc1`
- `msvcrt!_read` at `0x140005fb5`
- `msvcrt!_read` at `0x140005fb5`

## pseudocode

```c
__int64 __fastcall fciRead(INT_PTR hf, void *memory, UINT cb, int *err)
{
  unsigned int v6; // edi

  v6 = _read(hf, memory, cb);
  if ( v6 != cb )
    *err = *_errno();
  return v6;
}

```

## disassembly

```asm
0x140005fa0  mov     [rsp+arg_0], rbx
0x140005fa5  mov     [rsp+arg_8], rsi
0x140005faa  push    rdi
0x140005fab  sub     rsp, 20h
0x140005faf  mov     rsi, r9
0x140005fb2  mov     ebx, r8d
0x140005fb5  call    cs:__imp__read
0x140005fbb  mov     edi, eax
0x140005fbd  cmp     eax, ebx
0x140005fbf  jz      short loc_140005FCB
0x140005fc1  call    cs:__imp__errno
0x140005fc7  mov     ecx, [rax]
0x140005fc9  mov     [rsi], ecx
0x140005fcb  mov     rbx, [rsp+28h+arg_0]
0x140005fd0  mov     eax, edi
0x140005fd2  mov     rsi, [rsp+28h+arg_8]
0x140005fd7  add     rsp, 20h
0x140005fdb  pop     rdi
0x140005fdc  retn
```
