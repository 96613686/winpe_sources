# SdbpReadTagData

- ea: `0x1408c2898`
- end: `0x1408c2933`
- name: `SdbpReadTagData`
- size: `155`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140825944`
- `0x1408be86c`
- `0x1408c2bb4`
- `0x1408c30b0`
- `0x1408c3154`

## callees

- `0x1408c2898`
- `0x1408c293c`
- `0x1408c2d0c`
- `0x1408c2f88`
- `0x1408c2fc4`

## string_xrefs

- `0x1408c28fe`: `SdbpReadTagData`
- `0x1408c2920`: `SdbpReadTagData`
- `0x1408c2913`: `Error reading tag data`

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
0x1408c2898  push    rbx
0x1408c289a  push    rbp
0x1408c289b  push    rsi
0x1408c289c  push    rdi
0x1408c289d  push    r14
0x1408c289f  sub     rsp, 30h
0x1408c28a3  mov     edi, r9d
0x1408c28a6  mov     r14, r8
0x1408c28a9  mov     esi, edx
0x1408c28ab  mov     rbp, rcx
0x1408c28ae  call    SdbGetTagDataSize
0x1408c28b3  mov     ebx, eax
0x1408c28b5  cmp     eax, edi
0x1408c28b7  ja      short loc_1408C28E9
0x1408c28b9  mov     edx, esi
0x1408c28bb  mov     rcx, rbp
0x1408c28be  call    SdbpGetTagHeadSize
0x1408c28c3  mov     r9d, ebx
0x1408c28c6  mov     r8, r14
0x1408c28c9  mov     rcx, rbp
0x1408c28cc  lea     edx, [rsi+rax]
0x1408c28cf  call    SdbpReadMappedData
0x1408c28d4  test    eax, eax
0x1408c28d6  jz      short loc_1408C2913
0x1408c28d8  mov     eax, 1
0x1408c28dd  add     rsp, 30h
0x1408c28e1  pop     r14
0x1408c28e3  pop     rdi
0x1408c28e4  pop     rsi
0x1408c28e5  pop     rbp
0x1408c28e6  pop     rbx
0x1408c28e7  retn
0x1408c28e9  mov     [rsp+58h+var_30], ebx
0x1408c28ed  lea     r9, aBufferTooSmall; "Buffer too small. Avail: %d, Need: %d"
0x1408c28f4  mov     r8d, 1B7h
0x1408c28fa  mov     [rsp+58h+var_38], edi
0x1408c28fe  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x1408c2905  mov     ecx, 1
0x1408c290a  call    AslLogCallPrintf
0x1408c290f  xor     eax, eax
0x1408c2911  jmp     short loc_1408C28DD
0x1408c2913  lea     r9, aErrorReadingTa; "Error reading tag data"
0x1408c291a  mov     r8d, 1BEh
0x1408c2920  lea     rdx, aSdbpreadtagdat; "SdbpReadTagData"
0x1408c2927  mov     ecx, 1
0x1408c292c  call    AslLogCallPrintf
0x1408c2931  jmp     short loc_1408C290F
```
