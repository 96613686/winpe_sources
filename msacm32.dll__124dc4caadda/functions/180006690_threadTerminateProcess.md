# threadTerminateProcess

- ea: `0x180006690`
- end: `0x1800066a3`
- name: `threadTerminateProcess`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800063d0`
- `0x1800064a0`

## callees

- `0x180006690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000669b`

## pseudocode

```c
BOOL __fastcall threadTerminateProcess(__int64 a1)
{
  DWORD v1; // ecx
  BOOL result; // eax

  v1 = *(_DWORD *)(a1 + 208);
  if ( v1 != -1 )
    return TlsFree(v1);
  return result;
}

```

## disassembly

```asm
0x180006690  mov     ecx, [rcx+0D0h]
0x180006696  cmp     ecx, 0FFFFFFFFh
0x180006699  jz      short locret_1800066A2
0x18000669b  jmp     cs:__imp_TlsFree
0x1800066a2  retn
```
