# IsGetDlgItemPresent

- ea: `0x180009fec`
- end: `0x18000a03a`
- name: `IsGetDlgItemPresent`
- size: `78`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e300`
- `0x18000f330`
- `0x18000f6d8`

## callees

- `0x180009fec`
- `0x18000ac86`

## pseudocode

```c
char IsGetDlgItemPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18001A1E0 == 1 )
    return 1;
  if ( dword_18001A1E0 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"DF", &v1) < 0 )
    return 0;
  result = v1;
  dword_18001A1E0 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180009fec  sub     rsp, 28h
0x180009ff0  mov     ecx, cs:dword_18001A1E0
0x180009ff6  sub     ecx, 1
0x180009ff9  jz      short loc_18000A033
0x180009ffb  cmp     ecx, 1
0x180009ffe  jz      short loc_18000A02F
0x18000a000  lea     rdx, [rsp+28h+arg_0]
0x18000a005  mov     [rsp+28h+arg_0], 0
0x18000a00a  lea     rcx, aDf; "DF"
0x18000a011  call    ApiSetQueryApiSetPresence_0
0x18000a016  test    eax, eax
0x18000a018  js      short loc_18000A02F
0x18000a01a  mov     al, [rsp+28h+arg_0]
0x18000a01e  mov     cl, al
0x18000a020  neg     cl
0x18000a022  sbb     edx, edx
0x18000a024  add     edx, 2
0x18000a027  mov     cs:dword_18001A1E0, edx
0x18000a02d  jmp     short loc_18000A035
0x18000a02f  xor     al, al
0x18000a031  jmp     short loc_18000A035
0x18000a033  mov     al, 1
0x18000a035  add     rsp, 28h
0x18000a039  retn
```
