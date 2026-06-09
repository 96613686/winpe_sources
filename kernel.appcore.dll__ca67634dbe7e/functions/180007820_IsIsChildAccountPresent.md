# IsIsChildAccountPresent

- ea: `0x180007820`
- end: `0x18000786e`
- name: `IsIsChildAccountPresent`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001380`
- `0x180001d20`

## callees

- `0x180007820`
- `0x180007acd`

## pseudocode

```c
char IsIsChildAccountPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1800155E8 == 1 )
    return 1;
  if ( dword_1800155E8 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"VX", &v1) < 0 )
    return 0;
  result = v1;
  dword_1800155E8 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x180007820  sub     rsp, 28h
0x180007824  mov     ecx, cs:dword_1800155E8
0x18000782a  sub     ecx, 1
0x18000782d  jz      short loc_180007867
0x18000782f  cmp     ecx, 1
0x180007832  jz      short loc_180007863
0x180007834  lea     rdx, [rsp+28h+arg_0]
0x180007839  mov     [rsp+28h+arg_0], 0
0x18000783e  lea     rcx, aVx; "VX"
0x180007845  call    ApiSetQueryApiSetPresence_0
0x18000784a  test    eax, eax
0x18000784c  js      short loc_180007863
0x18000784e  mov     al, [rsp+28h+arg_0]
0x180007852  mov     cl, al
0x180007854  neg     cl
0x180007856  sbb     edx, edx
0x180007858  add     edx, 2
0x18000785b  mov     cs:dword_1800155E8, edx
0x180007861  jmp     short loc_180007869
0x180007863  xor     al, al
0x180007865  jmp     short loc_180007869
0x180007867  mov     al, 1
0x180007869  add     rsp, 28h
0x18000786d  retn
```
