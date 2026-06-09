# threadInitialize

- ea: `0x1800065c0`
- end: `0x1800065da`
- name: `threadInitialize`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800064a0`

## callees

- `0x1800065c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800065d2`

## pseudocode

```c
BOOL __fastcall threadInitialize(__int64 a1)
{
  DWORD v1; // ecx
  BOOL result; // eax

  if ( a1 )
  {
    v1 = *(_DWORD *)(a1 + 208);
    if ( v1 != -1 )
      return TlsSetValue(v1, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800065c0  test    rcx, rcx
0x1800065c3  jz      short locret_1800065D9
0x1800065c5  mov     ecx, [rcx+0D0h]
0x1800065cb  cmp     ecx, 0FFFFFFFFh
0x1800065ce  jz      short locret_1800065D9
0x1800065d0  xor     edx, edx
0x1800065d2  jmp     cs:__imp_TlsSetValue
0x1800065d9  retn
```
