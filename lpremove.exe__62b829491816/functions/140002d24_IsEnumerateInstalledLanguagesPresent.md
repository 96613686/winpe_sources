# IsEnumerateInstalledLanguagesPresent

- ea: `0x140002d24`
- end: `0x140002d72`
- name: `IsEnumerateInstalledLanguagesPresent`
- size: `78`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000eac8`

## callees

- `0x140002d24`
- `0x140002fc1`

## pseudocode

```c
char IsEnumerateInstalledLanguagesPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_140018414 == 1 )
    return 1;
  if ( dword_140018414 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"VX", &v1) < 0 )
    return 0;
  result = v1;
  dword_140018414 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x140002d24  sub     rsp, 28h
0x140002d28  mov     ecx, cs:dword_140018414
0x140002d2e  sub     ecx, 1
0x140002d31  jz      short loc_140002D6B
0x140002d33  cmp     ecx, 1
0x140002d36  jz      short loc_140002D67
0x140002d38  lea     rdx, [rsp+28h+arg_0]
0x140002d3d  mov     [rsp+28h+arg_0], 0
0x140002d42  lea     rcx, aVx; "VX"
0x140002d49  call    ApiSetQueryApiSetPresence_0
0x140002d4e  test    eax, eax
0x140002d50  js      short loc_140002D67
0x140002d52  mov     al, [rsp+28h+arg_0]
0x140002d56  mov     cl, al
0x140002d58  neg     cl
0x140002d5a  sbb     edx, edx
0x140002d5c  add     edx, 2
0x140002d5f  mov     cs:dword_140018414, edx
0x140002d65  jmp     short loc_140002D6D
0x140002d67  xor     al, al
0x140002d69  jmp     short loc_140002D6D
0x140002d6b  mov     al, 1
0x140002d6d  add     rsp, 28h
0x140002d71  retn
```
