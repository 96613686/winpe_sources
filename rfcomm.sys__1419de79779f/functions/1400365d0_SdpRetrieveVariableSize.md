# SdpRetrieveVariableSize

- ea: `0x1400365d0`
- end: `0x140036617`
- name: `SdpRetrieveVariableSize`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1400345fc`
- `0x14003468c`
- `0x140034a80`
- `0x140034e38`
- `0x1400353cc`
- `0x14003573c`
- `0x140035ab8`
- `0x140036444`

## callees

- `0x1400365d0`

## pseudocode

```c
__int64 __fastcall SdpRetrieveVariableSize(unsigned int *a1, char a2, _DWORD *a3, _DWORD *a4)
{
  __int64 result; // rax

  *a4 = 1 << (a2 - 5);
  switch ( a2 )
  {
    case 5:
      result = *(unsigned __int8 *)a1;
      break;
    case 6:
      result = (unsigned __int16)__ROR2__(*(_WORD *)a1, 8);
      break;
    case 7:
      result = _byteswap_ulong(*a1);
      break;
    default:
      result = 0;
      break;
  }
  *a3 = result;
  return result;
}

```

## disassembly

```asm
0x1400365d0  movzx   r10d, dl
0x1400365d4  mov     r11, rcx
0x1400365d7  mov     eax, 1
0x1400365dc  lea     ecx, [r10-5]
0x1400365e0  shl     eax, cl
0x1400365e2  mov     [r9], eax
0x1400365e5  sub     r10d, 5
0x1400365e9  jz      short loc_14003660F
0x1400365eb  sub     r10d, 1
0x1400365ef  jz      short loc_140036602
0x1400365f1  cmp     r10d, 1
0x1400365f5  jz      short loc_1400365FB
0x1400365f7  xor     eax, eax
0x1400365f9  jmp     short loc_140036613
0x1400365fb  mov     eax, [r11]
0x1400365fe  bswap   eax
0x140036600  jmp     short loc_140036613
0x140036602  movzx   eax, word ptr [r11]
0x140036606  ror     ax, 8
0x14003660a  movzx   eax, ax
0x14003660d  jmp     short loc_140036613
0x14003660f  movzx   eax, byte ptr [r11]
0x140036613  mov     [r8], eax
0x140036616  retn
```
