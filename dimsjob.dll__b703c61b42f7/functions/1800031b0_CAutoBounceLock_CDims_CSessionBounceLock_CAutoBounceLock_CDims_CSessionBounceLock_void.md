# CAutoBounceLock<CDims::_CSessionBounceLock>::~CAutoBounceLock<CDims::_CSessionBounceLock>(void)

- ea: `0x1800031b0`
- end: `0x1800031d9`
- name: `??1?$CAutoBounceLock@U_CSessionBounceLock@CDims@@@@QEAA@XZ`
- size: `41`
- prototype: `LSTATUS __fastcall(LPCWSTR **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000b4b8`

## callees

- `0x1800031b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800031d1`

## pseudocode

```c
LSTATUS __fastcall CAutoBounceLock<CDims::_CSessionBounceLock>::~CAutoBounceLock<CDims::_CSessionBounceLock>(
        LPCWSTR **a1)
{
  LSTATUS result; // eax

  if ( *((_BYTE *)*a1 + 8) )
    return RegDeleteKeyExW((HKEY)((*((_BYTE *)*a1 + 9) != 0) - 0x7FFFFFFFLL), **a1, 0, 0);
  return result;
}

```

## disassembly

```asm
0x1800031b0  mov     rdx, [rcx]
0x1800031b3  cmp     byte ptr [rdx+8], 0
0x1800031b7  jz      short locret_1800031D8
0x1800031b9  xor     ecx, ecx
0x1800031bb  cmp     [rdx+9], cl
0x1800031be  mov     rdx, [rdx]
0x1800031c1  setnz   cl
0x1800031c4  xor     r9d, r9d
0x1800031c7  add     rcx, 0FFFFFFFF80000001h
0x1800031ce  xor     r8d, r8d
0x1800031d1  jmp     cs:__imp_RegDeleteKeyExW
0x1800031d8  retn
```
