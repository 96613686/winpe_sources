# IsShellExecuteWPresent

- ea: `0x18000772c`
- end: `0x18000777a`
- name: `IsShellExecuteWPresent`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800049c0`
- `0x180005390`

## callees

- `0x18000772c`
- `0x180007acd`

## pseudocode

```c
char IsShellExecuteWPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1800155D0 == 1 )
    return 1;
  if ( dword_1800155D0 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L">@", &v1) < 0 )
    return 0;
  result = v1;
  dword_1800155D0 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x18000772c  sub     rsp, 28h
0x180007730  mov     ecx, cs:dword_1800155D0
0x180007736  sub     ecx, 1
0x180007739  jz      short loc_180007773
0x18000773b  cmp     ecx, 1
0x18000773e  jz      short loc_18000776F
0x180007740  lea     rdx, [rsp+28h+arg_0]
0x180007745  mov     [rsp+28h+arg_0], 0
0x18000774a  lea     rcx, asc_18000B0C0; ">@"
0x180007751  call    ApiSetQueryApiSetPresence_0
0x180007756  test    eax, eax
0x180007758  js      short loc_18000776F
0x18000775a  mov     al, [rsp+28h+arg_0]
0x18000775e  mov     cl, al
0x180007760  neg     cl
0x180007762  sbb     edx, edx
0x180007764  add     edx, 2
0x180007767  mov     cs:dword_1800155D0, edx
0x18000776d  jmp     short loc_180007775
0x18000776f  xor     al, al
0x180007771  jmp     short loc_180007775
0x180007773  mov     al, 1
0x180007775  add     rsp, 28h
0x180007779  retn
```
