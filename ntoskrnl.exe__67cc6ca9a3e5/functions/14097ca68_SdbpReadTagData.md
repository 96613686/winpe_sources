# SdbpReadTagData

- ea: `0x14097ca68`
- end: `0x14097cb03`
- name: `SdbpReadTagData`
- size: `155`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1408239d4`
- `0x140978aa4`
- `0x14097cd84`
- `0x14097d280`
- `0x14097d324`

## callees

- `0x14097ca68`
- `0x14097cb0c`
- `0x14097cedc`
- `0x14097d158`
- `0x14097d194`

## string_xrefs

- `0x14097cace`: `SdbpReadTagData`
- `0x14097caf0`: `SdbpReadTagData`
- `0x14097cae3`: `Error reading tag data`

## pseudocode

```c
__int64 __fastcall SdbpReadTagData(__int64 a1, unsigned int a2, void *a3, unsigned int a4)
{
  unsigned int TagDataSize; // ebx
  int TagHeadSize; // eax

  TagDataSize = SdbGetTagDataSize(a1, a2);
  if ( TagDataSize > a4 )
  {
    AslLogCallPrintf(1, (unsigned int)"SdbpReadTagData", 439, (unsigned int)"Buffer too small. Avail: %d, Need: %d");
  }
  else
  {
    TagHeadSize = SdbpGetTagHeadSize(a1, a2);
    if ( (unsigned int)SdbpReadMappedData(a1, a2 + TagHeadSize, a3, TagDataSize) )
      return 1;
    AslLogCallPrintf(1, (unsigned int)"SdbpReadTagData", 446, (unsigned int)"Error reading tag data");
  }
  return 0;
}

```

## disassembly

```asm
0x14097ca68  push    rbx
0x14097ca6a  push    rbp
0x14097ca6b  push    rsi
0x14097ca6c  push    rdi
0x14097ca6d  push    r14
0x14097ca6f  sub     rsp, 30h
0x14097ca73  mov     edi, r9d
0x14097ca76  mov     r14, r8
0x14097ca79  mov     esi, edx
0x14097ca7b  mov     rbp, rcx
0x14097ca7e  call    SdbGetTagDataSize
0x14097ca83  mov     ebx, eax
0x14097ca85  cmp     eax, edi
0x14097ca87  ja      short loc_14097CAB9
0x14097ca89  mov     edx, esi
0x14097ca8b  mov     rcx, rbp
0x14097ca8e  call    SdbpGetTagHeadSize
0x14097ca93  mov     r9d, ebx
0x14097ca96  mov     r8, r14
0x14097ca99  mov     rcx, rbp
0x14097ca9c  lea     edx, [rsi+rax]
0x14097ca9f  call    SdbpReadMappedData
0x14097caa4  test    eax, eax
0x14097caa6  jz      short loc_14097CAE3
0x14097caa8  mov     eax, 1
0x14097caad  add     rsp, 30h
0x14097cab1  pop     r14
0x14097cab3  pop     rdi
0x14097cab4  pop     rsi
0x14097cab5  pop     rbp
0x14097cab6  pop     rbx
0x14097cab7  retn
0x14097cab9  mov     [rsp+58h+var_30], ebx
0x14097cabd  lea     r9, aBufferTooSmall; "Buffer too small. Avail: %d, Need: %d"
0x14097cac4  mov     r8d, 1B7h
0x14097caca  mov     [rsp+58h+var_38], edi
0x14097cace  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x14097cad5  mov     ecx, 1
0x14097cada  call    AslLogCallPrintf
0x14097cadf  xor     eax, eax
0x14097cae1  jmp     short loc_14097CAAD
0x14097cae3  lea     r9, aErrorReadingTa; "Error reading tag data"
0x14097caea  mov     r8d, 1BEh
0x14097caf0  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x14097caf7  mov     ecx, 1
0x14097cafc  call    AslLogCallPrintf
0x14097cb01  jmp     short loc_14097CADF
```
