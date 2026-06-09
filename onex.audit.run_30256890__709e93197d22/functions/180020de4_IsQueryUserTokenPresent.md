# IsQueryUserTokenPresent

- ea: `0x180020de4`
- end: `0x180020e32`
- name: `IsQueryUserTokenPresent`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ac0`
- `0x180002a30`
- `0x18001abb4`
- `0x180028ef0`

## callees

- `0x180020de4`
- `0x18002133d`

## pseudocode

```c
char IsQueryUserTokenPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18003A330 == 1 )
    return 1;
  if ( dword_18003A330 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"FH", &v1) < 0 )
    return 0;
  result = v1;
  dword_18003A330 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180020de4  sub     rsp, 28h
0x180020de8  mov     ecx, cs:dword_18003A330
0x180020dee  sub     ecx, 1
0x180020df1  jz      short loc_180020E2B
0x180020df3  cmp     ecx, 1
0x180020df6  jz      short loc_180020E27
0x180020df8  lea     rdx, [rsp+28h+arg_0]
0x180020dfd  mov     [rsp+28h+arg_0], 0
0x180020e02  lea     rcx, aFh; "FH"
0x180020e09  call    ApiSetQueryApiSetPresence_0
0x180020e0e  test    eax, eax
0x180020e10  js      short loc_180020E27
0x180020e12  mov     al, [rsp+28h+arg_0]
0x180020e16  mov     cl, al
0x180020e18  neg     cl
0x180020e1a  sbb     edx, edx
0x180020e1c  add     edx, 2
0x180020e1f  mov     cs:dword_18003A330, edx
0x180020e25  jmp     short loc_180020E2D
0x180020e27  xor     al, al
0x180020e29  jmp     short loc_180020E2D
0x180020e2b  mov     al, 1
0x180020e2d  add     rsp, 28h
0x180020e31  retn
```
