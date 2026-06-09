# IsGetThreadDesktopPresent

- ea: `0x18000293c`
- end: `0x18000298a`
- name: `IsGetThreadDesktopPresent`
- size: `78`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a9c4`

## callees

- `0x18000293c`
- `0x180002990`

## pseudocode

```c
char IsGetThreadDesktopPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_18001229C == 1 )
    return 1;
  if ( dword_18001229C == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"LN", &v1) < 0 )
    return 0;
  result = v1;
  dword_18001229C = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x18000293c  sub     rsp, 28h
0x180002940  mov     ecx, cs:dword_18001229C
0x180002946  sub     ecx, 1
0x180002949  jz      short loc_180002983
0x18000294b  cmp     ecx, 1
0x18000294e  jz      short loc_18000297F
0x180002950  lea     rdx, [rsp+28h+arg_0]
0x180002955  mov     [rsp+28h+arg_0], 0
0x18000295a  lea     rcx, aLn; "LN"
0x180002961  call    ApiSetQueryApiSetPresence_0
0x180002966  test    eax, eax
0x180002968  js      short loc_18000297F
0x18000296a  mov     al, [rsp+28h+arg_0]
0x18000296e  mov     cl, al
0x180002970  neg     cl
0x180002972  sbb     edx, edx
0x180002974  add     edx, 2
0x180002977  mov     cs:dword_18001229C, edx
0x18000297d  jmp     short loc_180002985
0x18000297f  xor     al, al
0x180002981  jmp     short loc_180002985
0x180002983  mov     al, 1
0x180002985  add     rsp, 28h
0x180002989  retn
```
