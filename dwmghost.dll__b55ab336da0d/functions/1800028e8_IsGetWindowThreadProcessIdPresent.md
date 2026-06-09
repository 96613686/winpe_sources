# IsGetWindowThreadProcessIdPresent

- ea: `0x1800028e8`
- end: `0x180002936`
- name: `IsGetWindowThreadProcessIdPresent`
- size: `78`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000a9c4`

## callees

- `0x1800028e8`
- `0x180002990`

## pseudocode

```c
char IsGetWindowThreadProcessIdPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_180012280 == 1 )
    return 1;
  if ( dword_180012280 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L">@", &v1) < 0 )
    return 0;
  result = v1;
  dword_180012280 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x1800028e8  sub     rsp, 28h
0x1800028ec  mov     ecx, cs:dword_180012280
0x1800028f2  sub     ecx, 1
0x1800028f5  jz      short loc_18000292F
0x1800028f7  cmp     ecx, 1
0x1800028fa  jz      short loc_18000292B
0x1800028fc  lea     rdx, [rsp+28h+arg_0]
0x180002901  mov     [rsp+28h+arg_0], 0
0x180002906  lea     rcx, asc_18000D080; ">@"
0x18000290d  call    ApiSetQueryApiSetPresence_0
0x180002912  test    eax, eax
0x180002914  js      short loc_18000292B
0x180002916  mov     al, [rsp+28h+arg_0]
0x18000291a  mov     cl, al
0x18000291c  neg     cl
0x18000291e  sbb     edx, edx
0x180002920  add     edx, 2
0x180002923  mov     cs:dword_180012280, edx
0x180002929  jmp     short loc_180002931
0x18000292b  xor     al, al
0x18000292d  jmp     short loc_180002931
0x18000292f  mov     al, 1
0x180002931  add     rsp, 28h
0x180002935  retn
```
