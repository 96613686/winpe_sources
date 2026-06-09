# IsWTSQueryUserTokenPresent

- ea: `0x180020ce0`
- end: `0x180020d2e`
- name: `IsWTSQueryUserTokenPresent`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ac0`
- `0x180002a30`
- `0x18001abb4`
- `0x18001b044`

## callees

- `0x180020ce0`
- `0x18002133d`

## pseudocode

```c
char IsWTSQueryUserTokenPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18003A318 == 1 )
    return 1;
  if ( dword_18003A318 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"DF", &v1) < 0 )
    return 0;
  result = v1;
  dword_18003A318 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180020ce0  sub     rsp, 28h
0x180020ce4  mov     ecx, cs:dword_18003A318
0x180020cea  sub     ecx, 1
0x180020ced  jz      short loc_180020D27
0x180020cef  cmp     ecx, 1
0x180020cf2  jz      short loc_180020D23
0x180020cf4  lea     rdx, [rsp+28h+arg_0]
0x180020cf9  mov     [rsp+28h+arg_0], 0
0x180020cfe  lea     rcx, aDf; "DF"
0x180020d05  call    ApiSetQueryApiSetPresence_0
0x180020d0a  test    eax, eax
0x180020d0c  js      short loc_180020D23
0x180020d0e  mov     al, [rsp+28h+arg_0]
0x180020d12  mov     cl, al
0x180020d14  neg     cl
0x180020d16  sbb     edx, edx
0x180020d18  add     edx, 2
0x180020d1b  mov     cs:dword_18003A318, edx
0x180020d21  jmp     short loc_180020D29
0x180020d23  xor     al, al
0x180020d25  jmp     short loc_180020D29
0x180020d27  mov     al, 1
0x180020d29  add     rsp, 28h
0x180020d2d  retn
```
