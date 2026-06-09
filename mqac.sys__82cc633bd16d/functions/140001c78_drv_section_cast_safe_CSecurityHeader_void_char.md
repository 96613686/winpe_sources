# drv_section_cast_safe<CSecurityHeader *>(void *,char *)

- ea: `0x140001c78`
- end: `0x140001c8b`
- name: `??$drv_section_cast_safe@PEAUCSecurityHeader@@@@YAPEAUCSecurityHeader@@PEAXPEAD@Z`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002d24`
- `0x14001e6e8`

## callees

- `0x140001c78`

## pseudocode

```c
unsigned __int64 __fastcall drv_section_cast_safe<CSecurityHeader *>(unsigned __int64 a1, unsigned __int64 a2)
{
  unsigned __int64 result; // rax

  result = 0;
  if ( a1 + 16 <= a2 && a1 + 16 >= a1 )
    return a1;
  return result;
}

```

## disassembly

```asm
0x140001c78  lea     r8, [rcx+10h]
0x140001c7c  xor     eax, eax
0x140001c7e  cmp     r8, rdx
0x140001c81  ja      short locret_140001C8A
0x140001c83  cmp     r8, rcx
0x140001c86  cmovnb  rax, rcx
0x140001c8a  retn
```
