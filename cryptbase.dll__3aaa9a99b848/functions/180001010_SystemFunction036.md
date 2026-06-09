# SystemFunction036

- ea: `0x180001010`
- end: `0x18000102d`
- name: `SystemFunction036`
- size: `29`
- prototype: `BOOLEAN __stdcall(PVOID RandomBuffer, ULONG RandomBufferLength)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `bcryptPrimitives!ProcessPrng` at `0x180001016`
- `bcryptPrimitives!ProcessPrng` at `0x180001016`

## pseudocode

```c
BOOLEAN __stdcall SystemFunction036(PVOID RandomBuffer, ULONG RandomBufferLength)
{
  return (unsigned int)ProcessPrng(RandomBuffer, RandomBufferLength) != 0;
}

```

## disassembly

```asm
0x180001010  sub     rsp, 28h
0x180001014  mov     edx, edx
0x180001016  call    cs:__imp_ProcessPrng
0x18000101d  nop     dword ptr [rax+rax+00h]
0x180001022  test    eax, eax
0x180001024  setnz   al
0x180001027  add     rsp, 28h
0x18000102b  retn
```
