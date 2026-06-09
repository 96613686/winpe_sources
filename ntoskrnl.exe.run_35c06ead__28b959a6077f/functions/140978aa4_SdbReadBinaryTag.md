# SdbReadBinaryTag

- ea: `0x140978aa4`
- end: `0x140978b44`
- name: `SdbReadBinaryTag`
- size: `160`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140820f8c`
- `0x140822954`
- `0x140822a94`
- `0x140823968`
- `0x1409789b4`

## callees

- `0x140978aa4`
- `0x14097ca68`
- `0x14097ce8c`
- `0x14097d158`

## string_xrefs

- `0x140978b05`: `SdbReadBinaryTag`
- `0x140978b31`: `SdbReadBinaryTag`
- `0x140978b24`: `Error reading buffer`

## pseudocode

```c
__int64 __fastcall SdbReadBinaryTag(__int64 a1, unsigned int a2, void *a3, unsigned int a4)
{
  unsigned int v9; // [rsp+20h] [rbp-38h]
  int TagFromTagID; // [rsp+28h] [rbp-30h]

  if ( (((__int64 (*)(void))SdbGetTagFromTagID)() & 0xF000) == 0x9000 )
  {
    if ( (unsigned int)SdbpReadTagData(a1, a2, a3, a4) )
      return 1;
    AslLogCallPrintf(1, (unsigned int)"SdbReadBinaryTag", 1010, (unsigned int)"Error reading buffer");
  }
  else
  {
    TagFromTagID = (unsigned __int16)SdbGetTagFromTagID(a1, a2);
    v9 = a2;
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbReadBinaryTag",
      1005,
      (unsigned int)"TagID 0x%08X, Tag %04X not BINARY type",
      v9,
      TagFromTagID);
  }
  return 0;
}

```

## disassembly

```asm
0x140978aa4  push    rbx
0x140978aa6  push    rbp
0x140978aa7  push    rsi
0x140978aa8  push    rdi
0x140978aa9  sub     rsp, 38h
0x140978aad  mov     esi, r9d
0x140978ab0  mov     rbp, r8
0x140978ab3  mov     ebx, edx
0x140978ab5  mov     rdi, rcx
0x140978ab8  call    SdbGetTagFromTagID
0x140978abd  mov     ecx, 0F000h
0x140978ac2  mov     edx, ebx
0x140978ac4  and     ax, cx
0x140978ac7  mov     ecx, 9000h
0x140978acc  cmp     ax, cx
0x140978acf  mov     rcx, rdi
0x140978ad2  jnz     short loc_140978AF2
0x140978ad4  mov     r9d, esi
0x140978ad7  mov     r8, rbp
0x140978ada  call    SdbpReadTagData
0x140978adf  test    eax, eax
0x140978ae1  jz      short loc_140978B24
0x140978ae3  mov     eax, 1
0x140978ae8  add     rsp, 38h
0x140978aec  pop     rdi
0x140978aed  pop     rsi
0x140978aee  pop     rbp
0x140978aef  pop     rbx
0x140978af0  retn
0x140978af2  call    SdbGetTagFromTagID
0x140978af7  movzx   eax, ax
0x140978afa  lea     r9, aTagid0x08xTag0_0; "TagID 0x%08X, Tag %04X not BINARY type"
0x140978b01  mov     [rsp+58h+var_30], eax
0x140978b05  lea     rdx, aSdbreadbinaryt; "SdbReadBinaryTag"
0x140978b0c  mov     r8d, 3EDh
0x140978b12  mov     [rsp+58h+var_38], ebx
0x140978b16  mov     ecx, 1
0x140978b1b  call    AslLogCallPrintf
0x140978b20  xor     eax, eax
0x140978b22  jmp     short loc_140978AE8
0x140978b24  lea     r9, aErrorReadingBu; "Error reading buffer"
0x140978b2b  mov     r8d, 3F2h
0x140978b31  lea     rdx, aSdbreadbinaryt; "SdbReadBinaryTag"
0x140978b38  mov     ecx, 1
0x140978b3d  call    AslLogCallPrintf
0x140978b42  jmp     short loc_140978B20
```
