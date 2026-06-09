# IsSHGetKnownFolderPathPresent

- ea: `0x1800019e4`
- end: `0x180001a32`
- name: `IsSHGetKnownFolderPathPresent`
- size: `78`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003118`

## callees

- `0x1800019e4`
- `0x180001a38`

## pseudocode

```c
char IsSHGetKnownFolderPathPresent()
{
  char result; // al

  if ( dword_180008668 == 1 )
    return 1;
  if ( dword_180008668 == 2 || (int)ApiSetQueryApiSetPresence_0() < 0 )
    return 0;
  result = 0;
  dword_180008668 = 2;
  return result;
}

```

## disassembly

```asm
0x1800019e4  sub     rsp, 28h
0x1800019e8  mov     ecx, cs:dword_180008668
0x1800019ee  sub     ecx, 1
0x1800019f1  jz      short loc_180001A2B
0x1800019f3  cmp     ecx, 1
0x1800019f6  jz      short loc_180001A27
0x1800019f8  lea     rdx, [rsp+28h+arg_0]
0x1800019fd  mov     [rsp+28h+arg_0], 0
0x180001a02  lea     rcx, aLn; "LN"
0x180001a09  call    ApiSetQueryApiSetPresence_0
0x180001a0e  test    eax, eax
0x180001a10  js      short loc_180001A27
0x180001a12  mov     al, [rsp+28h+arg_0]
0x180001a16  mov     cl, al
0x180001a18  neg     cl
0x180001a1a  sbb     edx, edx
0x180001a1c  add     edx, 2
0x180001a1f  mov     cs:dword_180008668, edx
0x180001a25  jmp     short loc_180001A2D
0x180001a27  xor     al, al
0x180001a29  jmp     short loc_180001A2D
0x180001a2b  mov     al, 1
0x180001a2d  add     rsp, 28h
0x180001a31  retn
```
