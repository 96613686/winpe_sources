# SecFltGetRequestorProcess

- ea: `0x140005f34`
- end: `0x140005f5d`
- name: `SecFltGetRequestorProcess`
- size: `41`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x1400057a8`
- `0x140005a90`
- `0x140005d90`
- `0x140023e10`
- `0x140026d08`
- `0x140026ec4`
- `0x140027278`
- `0x14002792c`
- `0x140027c2c`
- `0x140027ec4`
- `0x1400280f8`
- `0x1400299b8`
- `0x14003e638`
- `0x14003fae4`

## callees

- `0x140005f34`
- `0x1400104f7`

## import_xrefs

- `ntoskrnl!IoThreadToProcess` at `0x140005f4b`
- `ntoskrnl!IoThreadToProcess` at `0x140005f4b`

## pseudocode

```c
PEPROCESS __fastcall SecFltGetRequestorProcess(struct _FLT_CALLBACK_DATA *a1)
{
  PEPROCESS result; // rax

  result = FltGetRequestorProcess_0(a1);
  if ( !result )
    return IoThreadToProcess(KeGetCurrentThread());
  return result;
}

```

## disassembly

```asm
0x140005f34  sub     rsp, 28h
0x140005f38  call    FltGetRequestorProcess_0
0x140005f3d  test    rax, rax
0x140005f40  jnz     short loc_140005F57
0x140005f42  mov     rcx, gs:188h; Thread
0x140005f4b  call    cs:__imp_IoThreadToProcess
0x140005f52  nop     dword ptr [rax+rax+00h]
0x140005f57  add     rsp, 28h
0x140005f5b  retn
```
