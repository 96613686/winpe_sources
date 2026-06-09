# IsEnumerateInstalledLocalExperiencePacksPresent

- ea: `0x140002d78`
- end: `0x140002dc6`
- name: `IsEnumerateInstalledLocalExperiencePacksPresent`
- size: `78`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000c36c`

## callees

- `0x140002d78`
- `0x140002fc1`

## pseudocode

```c
char IsEnumerateInstalledLocalExperiencePacksPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_140018404 == 1 )
    return 1;
  if ( dword_140018404 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"VX", &v1) < 0 )
    return 0;
  result = v1;
  dword_140018404 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x140002d78  sub     rsp, 28h
0x140002d7c  mov     ecx, cs:dword_140018404
0x140002d82  sub     ecx, 1
0x140002d85  jz      short loc_140002DBF
0x140002d87  cmp     ecx, 1
0x140002d8a  jz      short loc_140002DBB
0x140002d8c  lea     rdx, [rsp+28h+arg_0]
0x140002d91  mov     [rsp+28h+arg_0], 0
0x140002d96  lea     rcx, aVx_0; "VX"
0x140002d9d  call    ApiSetQueryApiSetPresence_0
0x140002da2  test    eax, eax
0x140002da4  js      short loc_140002DBB
0x140002da6  mov     al, [rsp+28h+arg_0]
0x140002daa  mov     cl, al
0x140002dac  neg     cl
0x140002dae  sbb     edx, edx
0x140002db0  add     edx, 2
0x140002db3  mov     cs:dword_140018404, edx
0x140002db9  jmp     short loc_140002DC1
0x140002dbb  xor     al, al
0x140002dbd  jmp     short loc_140002DC1
0x140002dbf  mov     al, 1
0x140002dc1  add     rsp, 28h
0x140002dc5  retn
```
