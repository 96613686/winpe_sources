# IsMoveWindowPresent

- ea: `0x18000a580`
- end: `0x18000a5ce`
- name: `IsMoveWindowPresent`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010e18`

## callees

- `0x18000a580`
- `0x18000ac86`

## pseudocode

```c
char IsMoveWindowPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18001A23C == 1 )
    return 1;
  if ( dword_18001A23C == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L">@", &v1) < 0 )
    return 0;
  result = v1;
  dword_18001A23C = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x18000a580  sub     rsp, 28h
0x18000a584  mov     ecx, cs:dword_18001A23C
0x18000a58a  sub     ecx, 1
0x18000a58d  jz      short loc_18000A5C7
0x18000a58f  cmp     ecx, 1
0x18000a592  jz      short loc_18000A5C3
0x18000a594  lea     rdx, [rsp+28h+arg_0]
0x18000a599  mov     [rsp+28h+arg_0], 0
0x18000a59e  lea     rcx, asc_1800140D0; ">@"
0x18000a5a5  call    ApiSetQueryApiSetPresence_0
0x18000a5aa  test    eax, eax
0x18000a5ac  js      short loc_18000A5C3
0x18000a5ae  mov     al, [rsp+28h+arg_0]
0x18000a5b2  mov     cl, al
0x18000a5b4  neg     cl
0x18000a5b6  sbb     edx, edx
0x18000a5b8  add     edx, 2
0x18000a5bb  mov     cs:dword_18001A23C, edx
0x18000a5c1  jmp     short loc_18000A5C9
0x18000a5c3  xor     al, al
0x18000a5c5  jmp     short loc_18000A5C9
0x18000a5c7  mov     al, 1
0x18000a5c9  add     rsp, 28h
0x18000a5cd  retn
```
