# CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::GetVariableSizeFromStrings(CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::CStrings *)

- ea: `0x18000683c`
- end: `0x180006866`
- name: `?GetVariableSizeFromStrings@?$CDescriptor@VCInfoLevelStringEnum_WKSTA_INFO@@@@QEAAKPEAVCStrings@1@@Z`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001020`
- `0x180006750`

## callees

- `0x18000683c`

## pseudocode

```c
__int64 __fastcall CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::GetVariableSizeFromStrings(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 i; // r9

  result = 0;
  for ( i = 0; i != 3; ++i )
  {
    if ( *(_DWORD *)(a1 + 4 * i + 20) != -1 )
      result = (unsigned int)*(unsigned __int16 *)(a2 + 16 * i) + (_DWORD)result + 2;
  }
  return result;
}

```

## disassembly

```asm
0x18000683c  xor     eax, eax
0x18000683e  mov     r10, rcx
0x180006841  xor     r9d, r9d
0x180006844  cmp     dword ptr [r10+r9*4+14h], 0FFFFFFFFh
0x18000684a  jz      short loc_18000685C
0x18000684c  mov     r8, r9
0x18000684f  add     eax, 2
0x180006852  add     r8, r8
0x180006855  movzx   ecx, word ptr [rdx+r8*8]
0x18000685a  add     eax, ecx
0x18000685c  inc     r9
0x18000685f  cmp     r9, 3
0x180006863  jnz     short loc_180006844
0x180006865  retn
```
