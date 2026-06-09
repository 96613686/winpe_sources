# MRxSmbCopyAndTranslatePipeState

- ea: `0x140052f50`
- end: `0x140052f96`
- name: `MRxSmbCopyAndTranslatePipeState`
- size: `70`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14003889c`
- `0x140038ad0`
- `0x140038d60`
- `0x140038f6c`

## callees

- `0x140052f50`

## pseudocode

```c
__int64 __fastcall MRxSmbCopyAndTranslatePipeState(__int64 a1, unsigned int a2)
{
  __int64 v2; // r9
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 648);
  if ( *(_BYTE *)(v2 + 77) == 1 )
  {
    *(_DWORD *)(v2 + 104) = *(_DWORD *)(RdrConfigurationBlock + 108);
    *(_DWORD *)(a1 + 720) = (a2 >> 10) & 1;
    result = (a2 >> 8) & 1;
    *(_DWORD *)(a1 + 724) = result;
    *(_DWORD *)(a1 + 728) = (a2 >> 15) & 1;
  }
  return result;
}

```

## disassembly

```asm
0x140052f50  mov     r9, [rcx+288h]
0x140052f57  cmp     byte ptr [r9+4Dh], 1
0x140052f5c  jnz     short locret_140052F95
0x140052f5e  mov     rax, cs:RdrConfigurationBlock
0x140052f65  mov     r8d, [rax+6Ch]
0x140052f69  mov     eax, edx
0x140052f6b  shr     eax, 0Ah
0x140052f6e  and     eax, 1
0x140052f71  mov     [r9+68h], r8d
0x140052f75  mov     [rcx+2D0h], eax
0x140052f7b  mov     eax, edx
0x140052f7d  shr     eax, 8
0x140052f80  and     eax, 1
0x140052f83  shr     edx, 0Fh
0x140052f86  and     edx, 1
0x140052f89  mov     [rcx+2D4h], eax
0x140052f8f  mov     [rcx+2D8h], edx
0x140052f95  retn
```
