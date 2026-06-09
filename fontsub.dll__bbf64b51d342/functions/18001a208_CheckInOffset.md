# CheckInOffset

- ea: `0x18001a208`
- end: `0x18001a22e`
- name: `CheckInOffset`
- size: `38`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180019804`
- `0x18001986c`
- `0x1800198f8`
- `0x18001a138`
- `0x18001a348`
- `0x18001a380`
- `0x18001a620`
- `0x18001a680`

## callees

- `0x18001a208`

## pseudocode

```c
__int64 __fastcall CheckInOffset(__int64 a1, unsigned int a2, unsigned __int64 a3)
{
  if ( *(_QWORD *)a1 && a3 <= 0xFFFFFFFF && (unsigned int)a3 + a2 >= a2 && (unsigned int)a3 + a2 <= *(_DWORD *)(a1 + 8) )
    return 0;
  else
    return 1001;
}

```

## disassembly

```asm
0x18001a208  cmp     qword ptr [rcx], 0
0x18001a20c  jz      short loc_18001A228
0x18001a20e  mov     eax, 0FFFFFFFFh
0x18001a213  cmp     r8, rax
0x18001a216  ja      short loc_18001A228
0x18001a218  lea     eax, [r8+rdx]
0x18001a21c  cmp     eax, edx
0x18001a21e  jb      short loc_18001A228
0x18001a220  cmp     eax, [rcx+8]
0x18001a223  ja      short loc_18001A228
0x18001a225  xor     eax, eax
0x18001a227  retn
0x18001a228  mov     eax, 3E9h
0x18001a22d  retn
```
