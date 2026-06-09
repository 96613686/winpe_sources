# IsSendMessageWPresent

- ea: `0x18000a250`
- end: `0x18000a29e`
- name: `IsSendMessageWPresent`
- size: `78`
- prototype: ``
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x180005990`
- `0x180006f00`
- `0x1800074d0`
- `0x180008660`
- `0x18000dff8`
- `0x18000e0c4`
- `0x18000e268`
- `0x18000e450`
- `0x18000e520`
- `0x18000e608`
- `0x18000e7d4`
- `0x18000ea7c`
- `0x18000ec20`
- `0x18000ed40`
- `0x18000ef10`
- `0x18000f330`
- `0x18000f8a0`
- `0x18000fba0`
- `0x1800102b0`
- `0x180010548`
- `0x180010cd0`
- `0x180010da8`
- `0x180011018`
- `0x180011578`
- `0x1800115f0`
- `0x1800119c0`

## callees

- `0x18000a250`
- `0x18000ac86`

## pseudocode

```c
char IsSendMessageWPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18001A208 == 1 )
    return 1;
  if ( dword_18001A208 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"@B", &v1) < 0 )
    return 0;
  result = v1;
  dword_18001A208 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x18000a250  sub     rsp, 28h
0x18000a254  mov     ecx, cs:dword_18001A208
0x18000a25a  sub     ecx, 1
0x18000a25d  jz      short loc_18000A297
0x18000a25f  cmp     ecx, 1
0x18000a262  jz      short loc_18000A293
0x18000a264  lea     rdx, [rsp+28h+arg_0]
0x18000a269  mov     [rsp+28h+arg_0], 0
0x18000a26e  lea     rcx, aB; "@B"
0x18000a275  call    ApiSetQueryApiSetPresence_0
0x18000a27a  test    eax, eax
0x18000a27c  js      short loc_18000A293
0x18000a27e  mov     al, [rsp+28h+arg_0]
0x18000a282  mov     cl, al
0x18000a284  neg     cl
0x18000a286  sbb     edx, edx
0x18000a288  add     edx, 2
0x18000a28b  mov     cs:dword_18001A208, edx
0x18000a291  jmp     short loc_18000A299
0x18000a293  xor     al, al
0x18000a295  jmp     short loc_18000A299
0x18000a297  mov     al, 1
0x18000a299  add     rsp, 28h
0x18000a29d  retn
```
