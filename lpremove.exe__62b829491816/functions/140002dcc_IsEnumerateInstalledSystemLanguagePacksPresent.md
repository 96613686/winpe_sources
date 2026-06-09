# IsEnumerateInstalledSystemLanguagePacksPresent

- ea: `0x140002dcc`
- end: `0x140002e1a`
- name: `IsEnumerateInstalledSystemLanguagePacksPresent`
- size: `78`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000c36c`
- `0x14000ee3c`

## callees

- `0x140002dcc`
- `0x140002fc1`

## pseudocode

```c
char IsEnumerateInstalledSystemLanguagePacksPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_140018410 == 1 )
    return 1;
  if ( dword_140018410 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"VX", &v1) < 0 )
    return 0;
  result = v1;
  dword_140018410 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x140002dcc  sub     rsp, 28h
0x140002dd0  mov     ecx, cs:dword_140018410
0x140002dd6  sub     ecx, 1
0x140002dd9  jz      short loc_140002E13
0x140002ddb  cmp     ecx, 1
0x140002dde  jz      short loc_140002E0F
0x140002de0  lea     rdx, [rsp+28h+arg_0]
0x140002de5  mov     [rsp+28h+arg_0], 0
0x140002dea  lea     rcx, aVx_1; "VX"
0x140002df1  call    ApiSetQueryApiSetPresence_0
0x140002df6  test    eax, eax
0x140002df8  js      short loc_140002E0F
0x140002dfa  mov     al, [rsp+28h+arg_0]
0x140002dfe  mov     cl, al
0x140002e00  neg     cl
0x140002e02  sbb     edx, edx
0x140002e04  add     edx, 2
0x140002e07  mov     cs:dword_140018410, edx
0x140002e0d  jmp     short loc_140002E15
0x140002e0f  xor     al, al
0x140002e11  jmp     short loc_140002E15
0x140002e13  mov     al, 1
0x140002e15  add     rsp, 28h
0x140002e19  retn
```
