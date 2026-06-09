# BripComputeHash

- ea: `0x180003600`
- end: `0x180003623`
- name: `BripComputeHash`
- size: `35`
- prototype: `__int64 __fastcall(PUCHAR Buffer, ULONG Length)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003070`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x18000360c`
- `ntdll!RtlComputeCrc32` at `0x18000360c`

## pseudocode

```c
__int64 __fastcall BripComputeHash(PUCHAR Buffer, ULONG Length)
{
  ULONG v2; // ecx
  __int64 result; // rax

  v2 = RtlComputeCrc32(0, Buffer, Length);
  result = 1;
  if ( v2 )
    return v2;
  return result;
}

```

## disassembly

```asm
0x180003600  sub     rsp, 28h
0x180003604  mov     r8d, edx; Length
0x180003607  mov     rdx, rcx; Buffer
0x18000360a  xor     ecx, ecx; InitialCrc
0x18000360c  call    cs:__imp_RtlComputeCrc32
0x180003612  mov     ecx, eax
0x180003614  mov     eax, 1
0x180003619  test    ecx, ecx
0x18000361b  cmovnz  eax, ecx
0x18000361e  add     rsp, 28h
0x180003622  retn
```
