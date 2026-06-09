# IsPerfRegQueryValuePresent

- ea: `0x1800084bc`
- end: `0x18000850a`
- name: `IsPerfRegQueryValuePresent`
- size: `78`
- prototype: `char()`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800059a0`
- `0x180016cd0`
- `0x18001b9c0`
- `0x18001bedc`
- `0x18001c734`

## callees

- `0x1800084bc`
- `0x180008510`

## pseudocode

```c
char IsPerfRegQueryValuePresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18002B550 == 1 )
    return 1;
  if ( dword_18002B550 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"FH", &v1) < 0 )
    return 0;
  result = v1;
  dword_18002B550 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x1800084bc  sub     rsp, 28h
0x1800084c0  mov     ecx, cs:dword_18002B550
0x1800084c6  sub     ecx, 1
0x1800084c9  jz      short loc_180008503
0x1800084cb  cmp     ecx, 1
0x1800084ce  jz      short loc_1800084FF
0x1800084d0  lea     rdx, [rsp+28h+arg_0]
0x1800084d5  mov     [rsp+28h+arg_0], 0
0x1800084da  lea     rcx, aFh; "FH"
0x1800084e1  call    ApiSetQueryApiSetPresence_0
0x1800084e6  test    eax, eax
0x1800084e8  js      short loc_1800084FF
0x1800084ea  mov     al, [rsp+28h+arg_0]
0x1800084ee  mov     cl, al
0x1800084f0  neg     cl
0x1800084f2  sbb     edx, edx
0x1800084f4  add     edx, 2
0x1800084f7  mov     cs:dword_18002B550, edx
0x1800084fd  jmp     short loc_180008505
0x1800084ff  xor     al, al
0x180008501  jmp     short loc_180008505
0x180008503  mov     al, 1
0x180008505  add     rsp, 28h
0x180008509  retn
```
